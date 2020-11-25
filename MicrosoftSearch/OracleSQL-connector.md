---
title: Connecteur Oracle SQL pour Microsoft Search
ms.author: vivg
author: Vivek
manager: harshkum
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
ROBOTS: NoIndex
description: Configurez Oracle SQL Connector pour Microsoft Search.
ms.openlocfilehash: 794ba81778ae5acf30c539f78390872579ac5467
ms.sourcegitcommit: 69a1c544cc8db364991cb58d7818d7158ff108b8
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/25/2020
ms.locfileid: "49408914"
---
# <a name="oracle-sql-connector"></a>Connecteur Oracle SQL

Avec Oracle SQL Connector, votre organisation peut découvrir et indexer des données à partir d’une base de données Oracle locale. Le connecteur indexe le contenu spécifié dans Microsoft Search. Pour conserver l’index à jour avec les données source, il prend en charge les analyses incrémentielles et complètes périodiques. Avec Oracle SQL Connector, vous pouvez également limiter l’accès aux résultats de recherche pour certains utilisateurs.

Cet article est destiné aux administrateurs de Microsoft 365 ou à quiconque configure, exécute et surveille un connecteur Oracle SQL. Elle explique comment configurer les fonctionnalités de connecteur et de connecteur, ainsi que les restrictions et les techniques de résolution des problèmes.

## <a name="install-the-graph-connector-agent"></a>Installer l’agent de connecteur Graph

Pour accéder à vos données tierces locales, vous devez installer et configurer l’agent connecteur Graph. Pour en savoir plus, consultez [la rubrique installer l’agent connecteur Graph](on-prem-agent.md) .  

## <a name="connect-to-a-data-source"></a>Se connecter à une source de données

Pour connecter votre connecteur Oracle SQL à une source de données, vous devez configurer le serveur de base de données que vous souhaitez analyser et l’agent connecteur Graph local. Vous pouvez ensuite vous connecter à la base de données à l’aide de la méthode d’authentification requise.

Pour Oracle SQL Connector, vous devez spécifier le nom d’hôte, le port et le nom de service (base de données), ainsi que la méthode d’authentification préférée, le nom d’utilisateur et le mot de passe.

> [!NOTE]
> Votre base de données doit exécuter la version de base de données Oracle 11g ou une version ultérieure pour que le connecteur puisse se connecter. Le connecteur prend en charge la base de données Oracle hébergée sur les plateformes Windows, Linux et Azure VM.

Pour effectuer une recherche dans le contenu de votre base de données, vous devez spécifier des requêtes SQL lorsque vous configurez le connecteur. Ces requêtes SQL doivent nommer toutes les colonnes de base de données que vous souhaitez indexer (c.-à-d. les propriétés source), y compris toutes les jointures SQL qui doivent être effectuées pour obtenir toutes les colonnes. Pour restreindre l’accès aux résultats de la recherche, vous devez spécifier des listes de contrôle d’accès (ACL) dans les requêtes SQL lorsque vous configurez le connecteur.

## <a name="full-crawl-required"></a>Analyse complète (obligatoire)

Dans cette étape, vous configurez la requête SQL qui exécute une analyse complète de la base de données. L’analyse complète sélectionne toutes les colonnes ou les propriétés que vous souhaitez rendre utilisables ou **pouvant** faire l’objet **retrievable** d’une **requête**. Vous pouvez également spécifier des colonnes ACL pour limiter l’accès aux résultats de la recherche à des utilisateurs ou à des groupes spécifiques.

> [!Tip]
> Pour obtenir toutes les colonnes dont vous avez besoin, vous pouvez joindre plusieurs tables.

![Script illustrant les OrderTable et AclTable avec les propriétés de l’exemple](media/MSSQL-fullcrawl.png)

### <a name="select-data-columns-required-and-acl-columns-optional"></a>Sélectionner des colonnes de données (obligatoires) et des colonnes ACL (facultatif)

L’exemple illustre la sélection de cinq colonnes de données qui contiennent les données pour la recherche : OrderId, OrderTitle, OrderDesc, CreatedDateTime et IsDeleted. Pour définir des autorisations d’affichage pour chaque ligne de données, vous pouvez éventuellement sélectionner les colonnes suivantes : AllowedUsers, AllowedGroups, DeniedUsers et DeniedGroups. Toutes ces colonnes de données peuvent être rendues pouvant faire l’objet d’une **requête**, d’une **recherche** ou d’une **extraction**.

Sélectionnez des colonnes de données comme indiqué dans cet exemple de requête : `SELECT OrderId, OrderTitle, OrderDesc, AllowedUsers, AllowedGroups, DeniedUsers, DeniedGroups, CreatedDateTime, IsDeleted`

Pour gérer l’accès aux résultats de la recherche, vous pouvez spécifier une ou plusieurs colonnes ACL dans la requête. Le connecteur SQL vous permet de contrôler l’accès par niveau d’enregistrement. Vous pouvez choisir d’utiliser le même contrôle d’accès pour tous les enregistrements d’une table. Si les informations de la liste de contrôle d’accès sont stockées dans une table distincte, il se peut que vous deviez effectuer une jointure avec ces tables dans votre requête.

L’utilisation de chacune des colonnes ACL dans la requête ci-dessus est décrite ci-dessous. La liste suivante décrit les 4 **mécanismes de contrôle d’accès**.

* **AllowedUsers**: spécifie la liste des ID utilisateur qui seront en mesure d’accéder aux résultats de la recherche. Dans l’exemple suivant, la liste des utilisateurs : john@contoso.com, keith@contoso.com et lisa@contoso.com n’a accès qu’à un enregistrement avec OrderId = 12.
* **AllowedGroups**: spécifie le groupe d’utilisateurs qui seront en mesure d’accéder aux résultats de la recherche. Dans l’exemple suivant, le groupe sales-team@contoso.com n’a accès qu’à record with OrderId = 12.
* **DeniedUsers**: spécifie la liste des utilisateurs qui n’ont **pas** accès aux résultats de la recherche. Dans l’exemple suivant, les utilisateurs john@contoso.com et keith@contoso.com n’ont pas accès à record avec OrderId = 13, tandis que tous les autres ont accès à cet enregistrement.
* **DeniedGroups**: spécifie le groupe d’utilisateurs qui n’ont **pas** accès aux résultats de la recherche. Dans l’exemple suivant, les groupes engg-team@contoso.com et pm-team@contoso.com n’ont pas accès à record avec OrderId = 15, tandis que les autres utilisateurs ont accès à cet enregistrement.  

![Exemples de données illustrant les OrderTable et AclTable avec des exemples de propriétés](media/MSSQL-ACL1.png)

### <a name="supported-data-types"></a>Types de données pris en charge

Le tableau ci-dessous récapitule les types de données pris en charge par Oracle SQL Connector. Le tableau résume également le type de données d’indexation pour le type de données SQL pris en charge. Pour en savoir plus sur les connecteurs Microsoft Graph types de données pris en charge pour l’indexation, reportez-vous à la documentation sur les [types de ressources de propriétés](https://docs.microsoft.com/graph/api/resources/property?view=graph-rest-beta#properties).

| Catégorie | Type de données source | Index, type de données |
| ------------ | ------------ | ------------ |
| Type de données numérique | NOMBRE (p, 0) | Int64 (pour p <= 18) <br> double (pour p > 18) |
| Type de données de nombre à virgule flottante | NOMBRE (p, s) <br> Virgule flottante (p) | double |
| Type de données date | JOURS <br> DATES <br> TIMESTAMP (n) | DateHeure |
| Type de données de caractère | CHAR (n) <br> VARCHAR <br> VARCHAR2 <br> PLUS <br> CLOB <br> NCLOB | string |
| Type de données caractères Unicode | NCHAR <br> NVARCHAR | string |
| Type de données RowID | ROWID <br> UROWID | string |

Pour tout autre type de données actuellement non pris en charge directement, la colonne doit être explicitement convertie en un type de données pris en charge.

### <a name="watermark-required"></a>Filigrane (obligatoire)

Pour éviter de surcharger la base de données, le connecteur regroupe et reprend les requêtes d’analyse complète avec une colonne de filigrane complète. En utilisant la valeur de la colonne filigrane, chaque lot suivant est extrait et l’interrogation reprend à partir du dernier point de contrôle. Fondamentalement, il s’agit d’un mécanisme de contrôle de l’actualisation des données pour les analyses complètes.

Créez des extraits de code de requête pour les filigranes, comme indiqué dans les exemples suivants :

* `WHERE (CreatedDateTime > @watermark)`. Citez le nom de la colonne filigrane par le mot clé réservé `@watermark` . Vous ne pouvez trier la colonne de filigrane qu’en ordre croissant.
* `ORDER BY CreatedDateTime ASC`. Trier dans l’ordre croissant sur la colonne de filigrane.

Dans la configuration illustrée dans l’image suivante, `CreatedDateTime` est la colonne de filigrane sélectionnée. Pour extraire le premier lot de lignes, spécifiez le type de données de la colonne de filigrane. Dans ce cas, le type de données est `DateTime` .

![Configuration des colonnes en filigrane](media/MSSQL-watermark.png)

La première requête extrait le premier **N** nombre de lignes à l’aide de : « CreatedDateTime > janvier 1, 1753 00:00:00 » (valeur minimale de type de données DateTime). Une fois le premier lot extrait, la valeur la plus élevée `CreatedDateTime` renvoyée dans le lot est enregistrée en tant que point de contrôle si les lignes sont triées par ordre croissant. Par exemple, le 1er mars 2019 03:00:00. Le prochain lot de **N** lignes est extrait en utilisant « CreatedDateTime > mars 1, 2019 03:00:00 » dans la requête.

### <a name="skipping-soft-deleted-rows-optional"></a>Ignorer les lignes supprimées (récupérables) (facultatif)

Pour exclure les lignes supprimées (récupérables) de votre base de données de l’indexation, spécifiez le nom et la valeur de la colonne de suppression récupérable qui indique que la ligne est supprimée.

![Paramètres de suppression douce : « colonne de suppression récupérable » et « valeur de la colonne suppression récupérable qui indique une ligne supprimée »](media/MSSQL-softdelete.png)

### <a name="full-crawl-manage-search-permissions"></a>Analyse complète : gérer les autorisations de recherche

Cliquez sur **gérer les autorisations** pour sélectionner les différentes colonnes de contrôle d’accès (ACL) qui spécifient le mécanisme de contrôle d’accès. Sélectionnez le nom de colonne que vous avez spécifié dans la requête SQL d’analyse complète.

Chacune des colonnes de liste de contrôle d’accès est censée être une colonne à valeurs multiples. Ces valeurs d’ID multiples peuvent être séparées par des séparateurs tels que des points-virgules (;), virgule (,), etc. Vous devez spécifier ce séparateur dans le champ **séparateur de valeur** .

Les types d’ID suivants sont pris en charge pour l’utilisation en tant que listes de Contrã’le d’accès :

* **Nom d’utilisateur principal (UPN)**: un nom d’utilisateur principal (UPN) est le nom d’un utilisateur système dans un format d’adresse de messagerie. Un UPN (par exemple : john.doe@domain.com) est constitué du nom d’utilisateur (nom de connexion), du séparateur (symbole @) et du nom de domaine (suffixe UPN).
* **ID d’Azure Active Directory (AAD)**: dans Azure ad, chaque utilisateur ou groupe possède un ID d’objet qui ressemble à « e0d3ad3d-0000-1111-2222-3c5f5c52ab9b ».
* **ID de sécurité Active Directory (AD)**: dans une configuration AD locale, chaque utilisateur et chaque groupe ont un identificateur de sécurité unique et non modifiable qui ressemble à-1-5-21-3878594291-2115959936-132693609-65242.

![Paramètres d’autorisation de recherche pour configurer les listes de contrôle d’accès](media/MSSQL-ACL2.png)

## <a name="incremental-crawl-optional"></a>Analyse incrémentielle (facultative)

Dans cette étape facultative, fournissez une requête SQL pour exécuter une analyse incrémentielle de la base de données. Avec cette requête, le connecteur SQL détermine les modifications apportées aux données depuis la dernière analyse incrémentielle. Comme dans l’analyse complète, sélectionnez toutes les colonnes que vous souhaitez rendre utilisables dans une **requête**, pouvant faire l’objet d’une **recherche** ou pouvoir être **récupérées**. Spécifiez le même ensemble de colonnes de liste de contrôle d’accès que vous avez spécifié dans la requête d’analyse complète.

Les composants de l’image suivante ressemblent aux composants d’analyse complets avec une exception. Dans ce cas, « ModifiedDateTime » est la colonne de filigrane sélectionnée. Examinez les étapes de l' [analyse complète](#full-crawl-required) pour apprendre à écrire votre requête d’analyse incrémentielle et voir l’image suivante par exemple.

![Script d’analyse incrémentielle affichant OrderTable, AclTable et des exemples de propriétés qui peuvent être utilisés.](media/MSSQL-incrcrawl.png)

## <a name="manage-search-permissions"></a>Gérer les autorisations de recherche

Vous pouvez choisir d’utiliser les [listes de contrã’le d’accès spécifiées dans l’écran d’analyse complète](#full-crawl-manage-search-permissions) ou de les remplacer pour rendre votre contenu visible par tous les utilisateurs.

## <a name="set-the-refresh-schedule"></a>Définir la planification d’actualisation

Oracle SQL Connector prend en charge les planifications d’actualisation pour les analyses complètes et incrémentielles. Nous vous recommandons de définir les deux.

Une planification d’analyse complète recherche les lignes supprimées qui ont été précédemment synchronisées avec l’index Microsoft Search et toutes les lignes qui ont été déplacées à partir du filtre de synchronisation. Lorsque vous vous connectez pour la première fois à la base de données, une analyse complète est exécutée pour synchroniser toutes les lignes récupérées à partir de la requête d’analyse complète. Pour synchroniser de nouvelles lignes et effectuer des mises à jour, vous devez planifier des analyses incrémentielles.

## <a name="next-steps-customize-the-search-results-page"></a>Étapes suivantes : personnaliser la page de résultats de recherche

Créez vos propres types de résultat et de vertical, de sorte que les utilisateurs finaux puissent afficher les résultats de la recherche à partir de nouvelles connexions. Sans cette étape, les données de votre connexion ne s’afficheront pas sur la page des résultats de la recherche.

Pour en savoir plus sur la création de vos secteurs verticaux et MRTs, voir Personnalisation de la [page de résultats de recherche](customize-search-page.md).

## <a name="limitations"></a>Limites

Le connecteur Oracle SQL présente ces limitations dans la version d’évaluation :

* La base de données locale doit exécuter la version de base de données Oracle 11g ou ultérieure.
* Les ACL sont uniquement prises en charge à l’aide d’un nom d’utilisateur principal (UPN), d’Azure Active Directory (Azure AD) ou de la sécurité Active Directory.
* L’indexation de contenu riche dans les colonnes de base de données n’est pas prise en charge. Des exemples de ce type de contenu sont les analyses HTML, JSON, XML, BLOB et de document qui existent sous forme de liens dans les colonnes de base de données.

## <a name="troubleshooting-guide"></a>Guide de dépannage

En dessous se trouve une liste des erreurs courantes observées lors de la configuration du connecteur et de leurs causes possibles.
| Étape de configuration | Message d’erreur | Raison (s) possible (s) |
| ------------ | ------------ | ------------ |
| Paramètres de base de données | Erreur du serveur de base de données : expiration du délai de la demande de connexion | Nom d’hôte non valide <br> Hôte inaccessible |
| Paramètres de base de données | Erreur du serveur de base de données : ORA-12541 : TNS : no listner | Port non valide |
| Paramètres de base de données | Erreur du serveur de base de données : ORA-12514 : TNS : listner ne connaît pas actuellement le service demandé dans le descripteur de connecteur | Nom de service (base de données) non valide |
| Paramètres de base de données | Erreur du serveur de base de données : échec de la connexion de l’utilisateur' `user` '. | Nom d’utilisateur ou mot de passe incorrect |
