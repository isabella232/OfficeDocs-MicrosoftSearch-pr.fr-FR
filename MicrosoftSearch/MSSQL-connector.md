---
title: Connecteur SQL et Microsoft SQL Server Graph Azure pour Recherche Microsoft
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
description: Configurer le connecteur Azure SQL et Microsoft SQL Graph pour Recherche Microsoft.
ms.openlocfilehash: 0f8501e36754235b43846b80d60d4b0156a504b9
ms.sourcegitcommit: 93fc70f0073ab45b4dbd702441ac2fc07a7668bc
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/01/2021
ms.locfileid: "53230915"
---
<!---Previous ms.author: vivg --->

# <a name="azure-sql-and-microsoft-sql-server-graph-connectors"></a>Connecteurs SQL et Microsoft SQL Server Graph Azure

Le connecteur Microsoft SQL Server ou Azure SQL Graph permet à votre organisation de découvrir et d’indexer des données à partir d’une base de données SQL Server sur site ou d’une base de données hébergée dans votre instance Azure SQL dans le cloud.
Le connecteur Graph indexe le contenu spécifié dans Recherche Microsoft. Pour maintenir l’index à jour avec les données sources, il prend en charge des analyses complètes et incrémentielles périodiques. Avec ces connecteurs SQL, vous pouvez également restreindre l’accès aux résultats de recherche pour certains utilisateurs.

> [!NOTE]
> Lisez [**l’article Configurer votre connecteur Graph pour**](configure-connector.md) comprendre les instructions générales Graph d’installation des connecteurs.

Cet article est réservé à toute personne qui configure, exécute et surveille un connecteur d’SQL azure et de serveur Microsoft SQL Graph. Il complète le processus d’installation général et affiche des instructions qui s’appliquent uniquement au connecteur d’installation SQL Azure et Microsoft SQL server Graph. Cet article inclut également des informations [sur les limitations](#limitations) pour le serveur Microsoft SQL et les connecteurs SQL Azure.

## <a name="before-you-get-started"></a>Avant de commencer

### <a name="install-the-graph-connector-agent-required-for-on-premises-microsoft-sql-server-connector-only"></a>Installer l’agent Graph connecteur local (requis pour le connecteur Microsoft SQL Server local uniquement)

Pour accéder à vos données tierces sur site, vous devez installer et configurer l’agent Graph connecteur local. Pour plus [d’informations, voir Installer Graph connecteur](on-prem-agent.md) d’installation.  

## <a name="step-1-add-a-graph-connector-in-the-microsoft-365-admin-center"></a>Étape 1 : Ajouter un connecteur Graph dans le Centre d’administration Microsoft 365

Suivez les [instructions d’installation générales.](./configure-connector.md)
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup 
instructions.-->

## <a name="step-2-name-the-connection"></a>Étape 2 : Nommer la connexion

Suivez les [instructions d’installation générales.](./configure-connector.md)
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup 
instructions.-->

## <a name="step-3-configure-the-connection-settings"></a>Étape 3 : Configurer les paramètres de connexion

### <a name="register-an-app-for-azure-sql-connector-only"></a>Inscrire une application (pour le connecteur azure SQL uniquement)

Pour le connecteur SQL Azure, vous devez inscrire une application dans Azure Active Directory pour permettre Recherche Microsoft’accès aux données pour l’indexation. Pour en savoir plus sur l’inscription d’une application, consultez la documentation microsoft Graph sur l’inscription [d’une application.](/graph/auth-register-app-v2)

Après avoir terminé l’inscription de l’application et pris note du nom de l’application, de l’ID d’application (client) et de l’ID de locataire, vous devez générer une [nouvelle secret client](/azure/healthcare-apis/register-confidential-azure-ad-client-app#application-secret). La secret client ne s’affichera qu’une seule fois. N’oubliez pas & stocker la secret client en toute sécurité. Utilisez l’ID client et la secret client lors de la configuration d’une nouvelle connexion dans Recherche Microsoft.

Pour ajouter l’application inscrite à votre Azure SQL Database, vous devez :

- Connectez-vous à votre SQL DB Azure
- Ouvrir une nouvelle fenêtre de requête
- Créez un utilisateur en exécutant la commande « CREATE USER [app name] FROM EXTERNAL PROVIDER »
- Ajouter un utilisateur au rôle en exécutant la commande « exec sp_addrolemember ' db_datareader ', [nom de l’application] » ou « ALTER ROLE db_datareader ADD MEMBER [nom de l’application] »

>[!NOTE]
>Pour révoquer l’accès à toute application inscrite dans Azure Active Directory, reportez-vous à la documentation Azure pour supprimer [une application inscrite.](/azure/active-directory/develop/quickstart-remove-app)

### <a name="connection-settings"></a>Paramètres de connexion

Pour connecter votre connecteur Microsoft SQL Server à une source de données, vous devez configurer le serveur de base de données que vous souhaitez analyser et l’agent sur site. Vous pouvez ensuite vous connecter à la base de données avec la méthode d’authentification requise.

> [!NOTE] 
> Votre base de données doit SQL Server version 2008 ou ultérieure pour que le connecteur Microsoft SQL Server puisse se connecter.

Pour le connecteur Azure SQL, vous devez uniquement spécifier le nom du serveur ou l’adresse IP à connecter. Le connecteur azure SQL prend uniquement en charge Azure Active Directory’authentification Open ID connect (OIDC) pour se connecter à la base de données.

Pour une sécurité renforcée, vous pouvez configurer des règles de pare-feu IP pour votre base de données ou SQL Server Azure. Pour en savoir plus sur la configuration des règles de pare-feu IP, consultez la documentation sur les [règles de pare-feu IP.](/azure/azure-sql/database/firewall-configure) Ajoutez les plages IP clientes suivantes dans les paramètres de pare-feu.

| Région | Plage d’adresses IP |
| ------------ | ------------ |
| NAM | 52.250.92.252/30, 52.224.250.216/30 |
| EUR | 20.54.41.208/30, 51.105.159.88/30 |
| APC | 52.139.188.212/30, 20.43.146.44/30 |

Pour rechercher le contenu de votre base de données, vous devez spécifier SQL requêtes lorsque vous configurez le connecteur. Ces requêtes SQL doivent nommer toutes les colonnes de base de données que vous souhaitez indexer (c’est-à-dire, les propriétés source), y compris les jointeurs de SQL qui doivent être effectuées pour obtenir toutes les colonnes. Pour restreindre l’accès aux résultats de la recherche, vous devez spécifier des listes de contrôle d’accès dans SQL requêtes lorsque vous configurez le connecteur.

## <a name="step-3a-full-crawl-required"></a>Étape 3a : analyse complète (obligatoire)

Dans cette étape, vous configurez la requête SQL qui exécute une analyse complète de la base de données. L’analyse complète sélectionne toutes les colonnes ou propriétés dans laquelle vous souhaitez sélectionner les options **Requête,** Rechercher **ou** **Récupérer.** Vous pouvez également spécifier des colonnes ACL pour restreindre l’accès des résultats de recherche à des utilisateurs ou des groupes spécifiques.

> [!Tip]
> Pour obtenir toutes les colonnes dont vous avez besoin, vous pouvez joindre plusieurs tables.

![Script montrant les propriétés OrderTable et AclTable avec des exemples de propriétés](media/MSSQL-fullcrawl.png)

### <a name="select-data-columns-required-and-acl-columns-optional"></a>Sélectionner des colonnes de données (obligatoire) et des colonnes ACL (facultatif)

L’exemple illustre une sélection de cinq colonnes de données qui détiennent les données de la recherche : OrderId, OrderTitle, OrderDesc, CreatedDateTime et IsDeleted. Pour définir des autorisations d’affichage pour chaque ligne de données, vous pouvez éventuellement sélectionner ces colonnes de la ACL : AllowedUsers, AllowedGroups, DeniedUsers et DeniedGroups. Toutes ces colonnes de données ont également la possibilité **d’effectuer des** requêtes, **des recherches** ou des **récupérations.**

Sélectionnez des colonnes de données comme illustré dans cet exemple de requête : `SELECT OrderId, OrderTitle, OrderDesc, AllowedUsers, AllowedGroups, DeniedUsers, DeniedGroups, CreatedDateTime, IsDeleted`

Pour gérer l’accès aux résultats de la recherche, vous pouvez spécifier une ou plusieurs colonnes ACL dans la requête. Le connecteur SQL vous permet de contrôler l’accès à chaque niveau d’enregistrement. Vous pouvez choisir d’avoir le même contrôle d’accès pour tous les enregistrements d’une table. Si les informations de la ACL sont stockées dans une table distincte, vous de devez peut-être joindre ces tables dans votre requête.

L’utilisation de chacune des colonnes ACL dans la requête ci-dessus est décrite ci-dessous. La liste suivante explique les quatre mécanismes **de contrôle d’accès.**

- **AllowedUsers**: cette colonne spécifie la liste des ID d’utilisateur qui peuvent accéder aux résultats de la recherche. Dans l’exemple suivant, la liste des utilisateurs : john@contoso.com, keith@contoso.com et lisa@contoso.com n’ont accès qu’à un enregistrement avec OrderId = 12.
- **AllowedGroups**: cette colonne spécifie le groupe d’utilisateurs qui pourront accéder aux résultats de la recherche. Dans l’exemple suivant, les sales-team@contoso.com n’ont accès qu’à l’enregistrement avec OrderId = 12.
- **DeniedUsers**: cette colonne spécifie la liste des utilisateurs qui **n’ont** pas accès aux résultats de la recherche. Dans l’exemple suivant, les utilisateurs john@contoso.com et keith@contoso.com n’ont pas accès à l’enregistrement avec OrderId = 13, alors que tous les autres utilisateurs ont accès à cet enregistrement.
- **DeniedGroups**: cette colonne spécifie le groupe d’utilisateurs qui **n’ont** pas accès aux résultats de la recherche. Dans l’exemple suivant, les groupes engg-team@contoso.com et pm-team@contoso.com n’ont pas accès à l’enregistrement avec OrderId = 15, alors que tous les autres ont accès à cet enregistrement.  

![Exemple de données montrant les propriétés OrderTable et AclTable avec des exemples de propriétés](media/MSSQL-ACL1.png)

### <a name="supported-data-types"></a>Types de données pris en charge

Le tableau ci-dessous récapitule les types SQL données pris en charge dans les connecteurs MS SQL et Azure SQL. Le tableau récapitule également le type de données d’indexation pour le type SQL données pris en charge. Pour en savoir plus sur les connecteurs Graph Microsoft pris en charge pour l’indexation, reportez-vous à la documentation sur les [types de ressources de propriété.](/graph/api/resources/property?preserve-view=true&view=graph-rest-beta#properties)

| Catégorie | Type de données source | Type de données d’indexation |
| ------------ | ------------ | ------------ |
| Date et heure | date <br> DateHeure <br> datetime2 <br> smalldatetime | DateHeure |
| Numérique exact | bigint <br> int <br> smallint <br> tinyint | int64 |
| Numérique exact | bit | valeur booléenne |
| Nombre approximatif | float <br> real | double |
| Chaîne de caractères | char <br> varchar <br> text | string |
| Chaînes de caractères Unicode | nchar <br> nvarchar <br> ntext | chaîne |
| Autres types de données | uniqueidentifier | chaîne |

Pour tout autre type de données actuellement non directement pris en charge, la colonne doit être explicitement castée vers un type de données pris en charge.

### <a name="watermark-required"></a>Filigrane (obligatoire)

Pour éviter la surcharge de la base de données, le connecteur par lots et reprend les requêtes d’analyse complète avec une colonne filigrane d’analyse complète. En utilisant la valeur de la colonne filigrane, chaque lot suivant est récupéré et l’interrogation reprend à partir du dernier point de contrôle. Essentiellement, ces mécanismes contrôlent l’actualisation des données pour les analyse complètes.

Créez des extraits de requête pour les filigranes, comme illustré dans les exemples suivants :

- `WHERE (CreatedDateTime > @watermark)`. Nommez le nom de colonne en filigrane avec le mot clé `@watermark` réservé. Si l’ordre de tri de la colonne de filigrane est croissant, utilisez `>` ; dans le cas contraire, utilisez `<` .
- `ORDER BY CreatedDateTime ASC`. Trier sur la colonne filigrane dans l’ordre croissant ou décroit.

Dans la configuration présentée dans l’image suivante, se trouve `CreatedDateTime` la colonne filigrane sélectionnée. Pour extraire le premier lot de lignes, spécifiez le type de données de la colonne filigrane. Dans ce cas, le type de données est `DateTime` .

![Configuration des colonnes de filigrane](media/MSSQL-watermark.png)

La première requête récupère le premier **N** nombre de lignes à l’aide de : « CreatedDateTime > 1er janvier 1753 00:00:00 » (valeur min du type de données DateTime). Une fois le premier lot récupéré, la valeur la plus élevée renvoyée dans le lot est enregistrée en tant que point de contrôle si les lignes sont triées par `CreatedDateTime` ordre croissant. Par exemple, 1er mars 2019 03:00:00. Ensuite, le lot suivant de **lignes N** est récupéré à l’aide de « CreatedDateTime > Mars 1, 2019 03:00:00 » dans la requête.

### <a name="skipping-soft-deleted-rows-optional"></a>Ignorer les lignes supprimées (facultatif)

Pour exclure l’indexation des lignes supprimées (à l’aide d’une suppression indélémentée) dans votre base de données, spécifiez le nom et la valeur de la colonne de suppression (suppression totale) qui indiquent que la ligne est supprimée.

![Paramètres de suppression souple : « Supprimer (suppression) » et « Valeur de la colonne suppression (suppression) qui indique une ligne supprimée »](media/MSSQL-softdelete.png)

### <a name="full-crawl-manage-search-permissions"></a>Analyse complète : gérer les autorisations de recherche

Sélectionnez **Gérer les autorisations** pour choisir les différentes colonnes de contrôle d’accès qui spécifient le mécanisme de contrôle d’accès. Sélectionnez le nom de colonne que vous avez spécifié dans l’analyse complète SQL requête.

Chacune des colonnes ACL est attendue comme une colonne à valeurs multiples. Ces valeurs d’ID multiples peuvent être séparées par des séparateurs tels que des points-virgules (;), virgule (,), etc. Vous devez spécifier ce séparateur dans le champ **séparateur de** valeurs.

Les types d’ID suivants sont pris en charge pour l’utilisation en tant que listes de contrôle d’appel :

- **Nom d’utilisateur principal (UPN)**: un nom d’utilisateur principal (UPN) est le nom d’un utilisateur système au format d’adresse de messagerie. Un UPN (par exemple : john.doe@domain.com) se compose du nom d’utilisateur (nom d’connexion), du séparateur (symbole @) et du nom de domaine (suffixe UPN).
- **Azure Active Directory (AAD) :** dans Azure AD, chaque utilisateur ou groupe possède un ID d’objet qui ressemble à « e0d3ad3d-0000-1111-2222-3c5f5c52ab9b ».
- ID de sécurité **Active Directory (AD)**: dans une configuration AD sur site, chaque utilisateur et groupe ont un identificateur de sécurité unique immuable qui ressemble à « S-1-5-21-3878594291-2115959936-132693609-65242 ».

![Paramètres d’autorisation de recherche pour configurer les listes de contrôle d’accès](media/MSSQL-ACL2.png)

## <a name="step-3b-incremental-crawl-optional"></a>Étape 3b : analyse incrémentielle (facultatif)

Dans cette étape facultative, fournissez une requête SQL pour exécuter une analyse incrémentielle de la base de données. Avec cette requête, le connecteur SQL détermine les modifications apportées aux données depuis la dernière analyse incrémentielle. Comme dans l’analyse complète, sélectionnez toutes les colonnes dans laquelle vous souhaitez sélectionner les **options** **Requête,** Rechercher ou **Récupérer.** Spécifiez le même ensemble de colonnes de liste de contrôle d’accès que vous avez spécifié dans la requête d’analyse complète.

Les composants de l’image suivante ressemblent aux composants d’analyse complets à une exception près. Dans ce cas, « ModifiedDateTime » est la colonne filigrane sélectionnée. Consultez [les étapes d’analyse](#step-3a-full-crawl-required) complètes pour apprendre à écrire votre requête d’analyse incrémentielle et voir l’image suivante en tant qu’exemple.

![Script d’analyse incrémentielle montrant OrderTable, AclTable et des exemples de propriétés qui peuvent être utilisés.](media/MSSQL-incrcrawl.png)

## <a name="step-4-assign-property-labels"></a>Étape 4 : Attribuer des étiquettes de propriété

Suivez les [instructions d’installation générales.](./configure-connector.md)

<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup 
instructions.-->

## <a name="step-5-manage-schema"></a>Étape 5 : Gérer le schéma

Suivez les [instructions d’installation générales.](./configure-connector.md)
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup 
instructions.-->

## <a name="step-6-manage-search-permissions"></a>Étape 6 : Gérer les autorisations de recherche

Vous pouvez choisir d’utiliser les [listes](#full-crawl-manage-search-permissions) de contrôle d’accès spécifiées dans l’écran d’analyse complet ou les remplacer pour rendre votre contenu visible par tout le monde.

## <a name="step-7-choose-refresh-settings"></a>Étape 7 : Choisir les paramètres d’actualisation

Suivez les [instructions d’installation générales.](./configure-connector.md)
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup 
instructions.-->

## <a name="step-8-review-connection"></a>Étape 8 : Examiner la connexion

Suivez les [instructions d’installation générales.](./configure-connector.md)
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup 
instructions.-->

<!---## Next steps: Customize the search results page

Create your own verticals and result types, so end users can view search results from new connections. Without this step, data from your connection won't show up on the search results page.

To learn more about how to create your verticals and MRTs, see [Search results page customization](customize-search-page.md).-->

## <a name="troubleshooting"></a>Résolution des problèmes

Voici une erreur courante observée lors de la configuration du connecteur et sa raison possible.

| Étape de configuration | Message d’erreur | Raisons possibles |
| ------------ | ------------ | ------------ |
| Analyse complète | `Error from database server: A transport level error has occurred when receiving results from the server.` | Cette erreur survient en raison de problèmes réseau. Il est recommandé de vérifier les journaux réseau à l’aide du moniteur [réseau Microsoft](https://www.microsoft.com/download/details.aspx?id=4865) et de joindre le support technique microsoft. |

## <a name="limitations"></a>Limites

Les connecteurs SQL ont les limitations ci-après dans la version préliminaire :

- Microsoft SQL Server : la base de données sur site doit être SQL Server version 2008 ou ultérieure.

- L’Microsoft 365 et l’abonnement Azure (hébergeant la base de données Azure SQL) doivent se trouver dans le même Azure Active Directory.
- Les ACA sont uniquement pris en charge à l’aide d’un nom d’utilisateur principal (UPN), d Azure Active Directory (Azure AD) ou d’Active Directory Security.
- L’indexation de contenu enrichi dans les colonnes de base de données n’est pas prise en charge. Les exemples de contenu de ce type sont HTML, JSON, XML, blobs et les parsings de document qui existent en tant que liens à l’intérieur des colonnes de base de données.
