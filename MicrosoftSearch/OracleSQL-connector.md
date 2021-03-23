---
title: Connecteur Oracle SQL Graph pour Microsoft Search (recherche Microsoft)
ms.author: mecampos
author: mecampos
manager: umas
audience: Admin
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
ROBOTS: NoIndex
description: Configurer le connecteur Oracle SQL Graph pour Microsoft Search (recherche Microsoft).
ms.openlocfilehash: 7ad3d03c73ce051c43f3b3ea094130a837d3177f
ms.sourcegitcommit: 5df252e6d0bd67bb1b4c59418aceca8369f5fe42
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51031421"
---
<!---Previous ms.author:vivg --->

# <a name="oracle-sql-graph-connector"></a>Connecteur Oracle SQL Graph

Le connecteur Oracle SQL Graph permet à votre organisation de découvrir et d’indexer des données à partir d’une base de données Oracle sur site. Le connecteur indexe le contenu spécifié dans Microsoft Search (recherche Microsoft). Pour maintenir l’index à jour avec les données sources, il prend en charge des analyses complètes et incrémentielles périodiques. Avec le connecteur SQL Oracle, vous pouvez également restreindre l’accès aux résultats de recherche pour certains utilisateurs.

> [!NOTE]
> Lisez [**l’article Configuration de votre connecteur Graph**](configure-connector.md) pour comprendre les instructions générales d’installation des connecteurs Graph.

Cet article est réservé à toute personne qui configure, exécute et surveille un connecteur Oracle SQL Graph. Il complète le processus de configuration général et affiche des instructions qui s’appliquent uniquement au connecteur Oracle SQL Graph. Cet article inclut également des informations [sur la résolution des problèmes](#troubleshooting) et les [limitations.](#limitations)

## <a name="before-you-get-started"></a>Avant de commencer

### <a name="install-the-graph-connector-agent"></a>Installer l’agent de connecteur Graph

Pour accéder à vos données tierces sur site, vous devez installer et configurer l’agent de connecteur Graph. Pour plus [d’informations, voir Installer l’agent de](on-prem-agent.md) connecteur Graph.  

## <a name="step-1-add-a-graph-connector-in-the-microsoft-365-admin-center"></a>Étape 1 : Ajouter un connecteur Graph dans le Centre d’administration Microsoft 365

Suivez les [instructions d’installation générales.](./configure-connector.md)
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-2-name-the-connection"></a>Étape 2 : Nommer la connexion

Suivez les [instructions d’installation générales.](./configure-connector.md)
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-3-configure-the-connection-settings"></a>Étape 3 : Configurer les paramètres de connexion

Pour connecter votre connecteur SQL Oracle à une source de données, vous devez configurer le serveur de base de données que vous souhaitez analyser et l’agent de connecteur Graph local. Vous pouvez ensuite vous connecter à la base de données avec la méthode d’authentification requise.

Pour le connecteur SQL Oracle, vous devez spécifier le nom d’hôte, le nom de port et de service (base de données) avec la méthode d’authentification préférée, le nom d’utilisateur et le mot de passe.

> [!NOTE]
> Votre base de données doit exécuter la base de données Oracle version 11g ou ultérieure pour que le connecteur puisse se connecter. Le connecteur prend en charge la base de données Oracle hébergée sur les plateformes d’ordinateurs VM Windows, Linux et Azure.

Pour rechercher le contenu de votre base de données, vous devez spécifier SQL requêtes lorsque vous configurez le connecteur. Ces requêtes SQL doivent nommer toutes les colonnes de base de données que vous souhaitez indexer (c’est-à-dire, les propriétés source), y compris les jointeurs de SQL qui doivent être effectuées pour obtenir toutes les colonnes. Pour restreindre l’accès aux résultats de la recherche, vous devez spécifier des listes de contrôle d’accès dans SQL requêtes lorsque vous configurez le connecteur.

## <a name="step-3a-full-crawl-required"></a>Étape 3a : analyse complète (obligatoire)

Dans cette étape, vous allez configurer la requête SQL qui exécute une analyse complète de la base de données. L’analyse complète sélectionne toutes les colonnes ou propriétés dans laquelle vous souhaitez sélectionner les options **Requête,** Rechercher **ou** **Récupérer.** Vous pouvez également spécifier des colonnes ACL pour restreindre l’accès des résultats de recherche à des utilisateurs ou des groupes spécifiques.

> [!Tip]
> Pour obtenir toutes les colonnes dont vous avez besoin, vous pouvez joindre plusieurs tables.

![Script montrant les propriétés OrderTable et AclTable avec des exemples de propriétés](media/MSSQL-fullcrawl.png)

### <a name="select-data-columns-required-and-acl-columns-optional"></a>Sélectionner des colonnes de données (obligatoire) et des colonnes ACL (facultatif)

L’exemple illustre la sélection de cinq colonnes de données qui détiennent les données de la recherche : OrderId, OrderTitle, OrderDesc, CreatedDateTime et IsDeleted. Pour définir des autorisations d’affichage pour chaque ligne de données, vous pouvez éventuellement sélectionner ces colonnes de la ACL : AllowedUsers, AllowedGroups, DeniedUsers et DeniedGroups. Pour toutes ces colonnes de données, vous pouvez sélectionner les options **de requête,** de **recherche** ou de **récupération.**

Sélectionnez des colonnes de données comme illustré dans cet exemple de requête : `SELECT OrderId, OrderTitle, OrderDesc, AllowedUsers, AllowedGroups, DeniedUsers, DeniedGroups, CreatedDateTime, IsDeleted`

Pour gérer l’accès aux résultats de la recherche, vous pouvez spécifier une ou plusieurs colonnes ACL dans la requête. Le connecteur SQL vous permet de contrôler l’accès à chaque niveau d’enregistrement. Vous pouvez choisir d’avoir le même contrôle d’accès pour tous les enregistrements d’une table. Si les informations de la ACL sont stockées dans une table distincte, vous de devez peut-être joindre ces tables dans votre requête.

L’utilisation de chacune des colonnes ACL dans la requête ci-dessus est décrite ci-dessous. La liste suivante explique les quatre mécanismes **de contrôle d’accès.**

* **AllowedUsers**: cette option spécifie la liste des ID d’utilisateur qui pourront accéder aux résultats de la recherche. Dans l’exemple suivant, la liste des utilisateurs : john@contoso.com, keith@contoso.com et lisa@contoso.com n’ont accès qu’à un enregistrement avec OrderId = 12.
* **AllowedGroups**: cette option spécifie le groupe d’utilisateurs qui pourront accéder aux résultats de la recherche. Dans l’exemple suivant, les sales-team@contoso.com n’ont accès qu’à l’enregistrement avec OrderId = 12.
* **DeniedUsers**: cette option spécifie la liste des utilisateurs qui **n’ont** pas accès aux résultats de la recherche. Dans l’exemple suivant, les utilisateurs john@contoso.com et keith@contoso.com n’ont pas accès à l’enregistrement avec OrderId = 13, alors que tous les autres utilisateurs ont accès à cet enregistrement.
* **DeniedGroups :** cette option spécifie le groupe d’utilisateurs qui **n’ont** pas accès aux résultats de la recherche. Dans l’exemple suivant, les groupes engg-team@contoso.com et pm-team@contoso.com n’ont pas accès à l’enregistrement avec OrderId = 15, alors que tous les autres ont accès à cet enregistrement.  

![Exemple de données montrant les propriétés OrderTable et AclTable avec des exemples de propriétés](media/MSSQL-ACL1.png)

### <a name="supported-data-types"></a>Types de données pris en charge

Le tableau ci-dessous récapitule les types de données pris en charge par le connecteur SQL Oracle. Le tableau récapitule également le type de données d’indexation pour le type SQL données pris en charge. Pour en savoir plus sur les types de données pris en charge par les connecteurs Microsoft Graph pour l’indexation, consultez la documentation sur les [types de ressources de propriété.](/graph/api/resources/property?preserve-view=true&view=graph-rest-beta#properties)

| Catégorie | Type de données source | Type de données d’indexation |
| ------------ | ------------ | ------------ |
| Type de données Number | NUMBER(p,0) | int64 (pour p <= 18) <br> double (pour p > 18) |
| Type de données de nombre à point flottant | NUMBER(p,s) <br> FLOAT(p) | double |
| Type de données Date | DATE <br> TIMESTAMP <br> TIMESTAMP(n) | DateHeure |
| Type de données character | CHAR(n) <br> VARCHAR <br> VARCHAR2 <br> LONG <br> ÎTB <br> NCLOB | string |
| Type de données de caractère Unicode | NCHAR <br> NVARCHAR | string |
| Type de données RowID | ROWID <br> UROWID | string |

Pour tout autre type de données actuellement non directement pris en charge, la colonne doit être explicitement castée vers un type de données pris en charge.

### <a name="watermark-required"></a>Filigrane (obligatoire)

Pour éviter la surcharge de la base de données, le connecteur par lots et reprend les requêtes d’analyse complète avec une colonne filigrane d’analyse complète. En utilisant la valeur de la colonne filigrane, chaque lot suivant est récupéré et l’interrogation reprend à partir du dernier point de contrôle. Il s’agit essentiellement d’un mécanisme permettant de contrôler l’actualisation des données pour les analyse complètes.

Créez des extraits de requête pour les filigranes, comme illustré dans les exemples suivants :

* `WHERE (CreatedDateTime > @watermark)`. Nommez le nom de colonne de filigrane avec le mot clé `@watermark` réservé. Vous ne pouvez trier la colonne filigrane que par ordre croissant.
* `ORDER BY CreatedDateTime ASC`. Tri dans la colonne filigrane dans l’ordre croissant.

Dans la configuration présentée dans l’image suivante, se trouve `CreatedDateTime` la colonne filigrane sélectionnée. Pour extraire le premier lot de lignes, spécifiez le type de données de la colonne filigrane. Dans ce cas, le type de données est `DateTime` .

![Configuration des colonnes de filigrane](media/MSSQL-watermark.png)

La première requête récupère le premier **N** nombre de lignes à l’aide de : « CreatedDateTime > 1er janvier 1753 00:00:00 » (valeur min du type de données DateTime). Une fois le premier lot récupéré, la valeur la plus élevée renvoyée dans le lot est enregistrée en tant que point de contrôle si les lignes sont triées par `CreatedDateTime` ordre croissant. Par exemple, 1er mars 2019 03:00:00. Ensuite, le lot suivant de **lignes N** est récupéré à l’aide de « CreatedDateTime > Mars 1, 2019 03:00:00 » dans la requête.

### <a name="skipping-soft-deleted-rows-optional"></a>Ignorer les lignes supprimées (facultatif)

Pour exclure l’indexation des lignes supprimées (ou non) dans votre base de données, spécifiez le nom et la valeur de la colonne de suppression (suppression totale) qui indiquent que la ligne est supprimée.

![Paramètres de suppression souple : « Supprimer (suppression) » et « Valeur de la colonne suppression (suppression) qui indique une ligne supprimée »](media/MSSQL-softdelete.png)

### <a name="full-crawl-manage-search-permissions"></a>Analyse complète : gérer les autorisations de recherche

Sélectionnez **Gérer les autorisations** pour choisir les différentes colonnes de contrôle d’accès qui spécifient le mécanisme de contrôle d’accès. Sélectionnez le nom de colonne que vous avez spécifié dans l’analyse complète SQL requête.

Chacune des colonnes ACL est attendue comme une colonne à valeurs multiples. Ces valeurs d’ID multiples peuvent être séparées par des séparateurs tels que des points-virgules (;), virgule (,), etc. Vous devez spécifier ce séparateur dans le champ **séparateur de** valeurs.

Les types d’ID suivants sont pris en charge pour l’utilisation en tant que listes de contrôle d’appel :

* **Nom d’utilisateur principal (UPN)**: un nom d’utilisateur principal (UPN) est le nom d’un utilisateur système au format d’adresse de messagerie. Un UPN (par exemple : john.doe@domain.com) se compose du nom d’utilisateur (nom d’connexion), du séparateur (symbole @) et du nom de domaine (suffixe UPN).
* **ID Azure Active Directory (AAD)**: dans Azure AD, chaque utilisateur ou groupe possède un ID d’objet qui ressemble à « e0d3ad3d-0000-1111-2222-3c5f5c52ab9b »
* ID de sécurité **Active Directory (AD)**: dans une configuration AD sur site, chaque utilisateur et groupe ont un identificateur de sécurité unique immuable qui ressemble à « S-1-5-21-3878594291-2115959936-132693609-65242 ».

![Paramètres d’autorisation de recherche pour configurer les listes de contrôle d’accès](media/MSSQL-ACL2.png)

## <a name="step-3b-incremental-crawl-optional"></a>Étape 3b : analyse incrémentielle (facultatif)

Dans cette étape facultative, fournissez une requête SQL pour exécuter une analyse incrémentielle de la base de données. Avec cette requête, le connecteur SQL détermine les modifications apportées aux données depuis la dernière analyse incrémentielle. Comme dans l’analyse complète, sélectionnez entre les options **Requête,** **Rechercher** ou **Récupérer.** Spécifiez le même ensemble de colonnes de liste de contrôle d’accès que vous avez spécifié dans la requête d’analyse complète.

Les composants de l’image suivante ressemblent aux composants d’analyse complets à une exception près. Dans ce cas, « ModifiedDateTime » est la colonne filigrane sélectionnée. Consultez [les étapes d’analyse](#step-3a-full-crawl-required) complètes pour apprendre à écrire votre requête d’analyse incrémentielle et voir l’image suivante en tant qu’exemple.

![Script d’analyse incrémentielle montrant OrderTable, AclTable et des exemples de propriétés qui peuvent être utilisés.](media/MSSQL-incrcrawl.png)

## <a name="step-4-assign-property-labels"></a>Étape 4 : Attribuer des étiquettes de propriété

Suivez les [instructions d’installation générales.](./configure-connector.md)
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-5-manage-schema"></a>Étape 5 : Gérer le schéma

Suivez les [instructions d’installation générales.](./configure-connector.md)
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-6-manage-search-permissions"></a>Étape 6 : Gérer les autorisations de recherche

Vous pouvez choisir d’utiliser les [listes](#full-crawl-manage-search-permissions) de contrôle d’accès spécifiées dans l’écran d’analyse complet ou les remplacer pour rendre votre contenu visible par tout le monde.

## <a name="step-7-choose-refresh-settings"></a>Étape 7 : Choisir les paramètres d’actualisation

Le connecteur SQL Oracle prend en charge les planifications d’actualisation pour les analyses complètes et incrémentielles. Nous vous recommandons de définir les deux.

Une planification d’analyse complète trouve les lignes supprimées qui ont été précédemment synchronisées avec l’index de recherche Microsoft et toutes les lignes qui ont été déplacées hors du filtre de synchronisation. Lorsque vous vous connectez à la base de données pour la première fois, une analyse complète s’exécute pour synchroniser toutes les lignes récupérées à partir de la requête d’analyse complète. Pour synchroniser de nouvelles lignes et effectuer des mises à jour, vous devez planifier des analyses incrémentielles.

## <a name="step-8-review-connection"></a>Étape 8 : Examiner la connexion

Suivez les [instructions d’installation générales.](./configure-connector.md)
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

<!--- ## Next steps: Customize the search results page

Create your own verticals and result types, so end users can view search results from new connections. Without this step, data from your connection won't show up on the search results page.

To learn more about how to create your verticals and MRTs, see [Search results page customization](customize-search-page.md). -->

## <a name="troubleshooting"></a>Résolution des problèmes

Sous-dessous se trouve une liste des erreurs courantes observées lors de la configuration du connecteur et leurs raisons possibles.

| Étape de configuration | Message d’erreur | Raisons possibles |
| ------------ | ------------ | ------------ |
| Paramètres de base de données | Erreur du serveur de base de données : la demande de connexion a été hors délai | Hostname non valide <br> Hôte non accessible |
| Paramètres de base de données | Erreur du serveur de base de données : ORA-12541 : TNS : pas d’écoute | Port non valide |
| Paramètres de base de données | Erreur du serveur de base de données : ORA-12514 : TNS : l’écoute ne connaît pas actuellement le service demandé dans le descripteur de connecteur | Nom de service (base de données) non valide |
| Paramètres de base de données | Erreur du serveur de base de données : échec de connexion pour l’utilisateur ' `user` '. | Nom d’utilisateur ou mot de passe non valide |

## <a name="limitations"></a>Limites

Le connecteur SQL Oracle présente les limitations ci-après dans la version préliminaire :

* La base de données sur site doit exécuter la base de données Oracle version 11g ou ultérieure.
* Les ACA sont uniquement pris en charge à l’aide d’un nom d’utilisateur principal (UPN), d’Azure Active Directory (Azure AD) ou d’Active Directory Security.
* L’indexation de contenu enrichi dans les colonnes de base de données n’est pas prise en charge. Les exemples de contenu de ce type sont html, JSON, XML, blobs et les parsings de document qui existent en tant que liens à l’intérieur des colonnes de base de données.