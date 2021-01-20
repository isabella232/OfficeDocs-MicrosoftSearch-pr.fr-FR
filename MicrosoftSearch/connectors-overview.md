---
title: Vue d’ensemble des connecteurs
ms.author: monaray
author: monaray97
manager: shohara
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: Vue d’ensemble des connecteurs Microsoft Graph pour Microsoft Search (recherche Microsoft)
ms.openlocfilehash: a45a007bbb2774caaaac90fc1549c8ba634b0580
ms.sourcegitcommit: 39bf9f0db7f9bff2ab82c99a059b0ddcf1c98f5f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/19/2021
ms.locfileid: "49905951"
---
# <a name="overview-of-microsoft-graph-connectors"></a>Vue d’ensemble des connecteurs Microsoft Graph

[Microsoft Search](https://docs.microsoft.com/microsoftsearch/overview-microsoft-search) indexe toutes vos [données Microsoft 365](https://www.microsoft.com/microsoft-365) pour les rendre accessibles aux utilisateurs. Avec les connecteurs Microsoft Graph, votre organisation peut indexer des données tierces afin qu’elles apparaissent dans les résultats de recherche Microsoft. Cela étend les types de sources de contenu utilisables dans vos applications de productivité Microsoft 365 et dans l’écosystème Microsoft plus large. Les données tierces peuvent être hébergées en local ou dans les clouds publics ou privés.

<!---link Microsoft Graph reference in line 19 when we have access to relevant documentation--->

Le reste de cet article est destiné à aider les administrateurs Microsoft 365 à trouver les ressources disponibles pour répondre aux questions suivantes :

* [Quelles sources de données peuvent être connectées à Microsoft Search (recherche Microsoft) ?](#what-data-sources-can-be-connected-to-microsoft-search)
* [Comment gérer mes connexions ?](#how-do-i-manage-my-connections)
* [Quelles sont les conditions d’utilisation et les conditions d’utilisation des licences pour les connecteurs Graph ?](#what-are-the-license-requirements-and-terms-of-use-for-graph-connectors)
* [Quelles sont les fonctionnalités d’aperçu ?](#what-are-the-preview-features)
* [Comment personnaliser et configurer les résultats de la recherche ?](#how-do-i-customize-and-configure-search-results)
* [Comment effectuer une recherche dans les données de mon connecteur à partir d’une application personnalisée ?](#how-do-i-search-my-connector-data-from-a-custom-application)

<!---Modify to another note that is more accurate after rollout completion--->
> [!IMPORTANT]
> Les connecteurs Microsoft Graph et les API de recherche Microsoft sont désormais généralement disponibles. Le premier déploiement est prévu pour durer jusqu’en février 2021. En attendant, seuls les clients et [](https://docs.microsoft.com/office365/admin/manage/release-options-in-office-365?view=o365-worldwide&preserve-view=true) les utilisateurs qui ont choisi la version ciblée pourront utiliser les connecteurs Graph. Une fois le déploiement terminé pour tous les clients, l’utilisation du quota d’index à partir du contenu des connecteurs est soumise à facturation. Pour plus [d’informations, voir Exigences](licensing.md) et tarifs en matière de licences.

<!---Add Value, scenario, example, and/or graphic in December updates--->
<!---Probably remove architecture section below
## Architecture

The following architectural diagram of the Microsoft Graph platform shows how Graph connector content flows through content indexing to user results in [Microsoft Search](https://docs.microsoft.com/microsoftsearch/overview-microsoft-search) clients. The rest of this section explains each of the key building blocks in the diagram.

![Diagram: on-premises and cloud-based data is pulled by connectors and indexed by the Microsoft Search API, and then the Microsoft Search service delivers the results to users.](media/connectors-overview/highlevel-connectors.png)
Graph connectors can pull data from cloud-based (SaaS) data sources and on-premises data stores. The above diagram shows connections to only two data sources, but you can add connections to up ten sources per tenant.

The Microsoft Graph Connectors API instantiates one connection per data source. Then, the API indexes and stores the data. Established connections interact with Microsoft Search, so users can get search results.

You can use the Microsoft 365 [admin center](https://admin.microsoft.com) to setup and manage any of the Graph connectors by Microsoft. The admin center has a simple user interface that makes it easy to establish the connection to your data source, and monitor connection status and utilization.

***Edit paragraph below**_
To create a _*connection** to a data source, admins need authenticated access to the data and the entire content repository. The data is fed to the graph connector service for indexing.--->

## <a name="what-data-sources-can-be-connected-to-microsoft-search"></a>Quelles sources de données peuvent être connectées à Microsoft Search (recherche Microsoft) ?

Microsoft fournit dix connecteurs Graph et nos partenaires de l’écosystème ont créé plus de 100 connecteurs Graph supplémentaires. Vous pouvez également créer votre propre connecteur Graph. 

### <a name="graph-connectors-by-microsoft"></a>Connecteurs Graph par Microsoft

Vous pouvez vous connecter aux sources de données suivantes à l’aide de connecteurs Graph créés par Microsoft :

<!---Need to add a few links below when docs exist--->
* [Azure Data Lake Storage Gen2](azure-data-lake-connector.md)
* [Azure DevOps](azure-devops-connector.md)
* Azure SQL
* [Sites web d’entreprise](enterprise-web-connector.md)
* [MediaWiki](mediawiki-connector.md)
* [Microsoft SQL Server](MSSQL-connector.md)
* [Partage de fichiers](fileshare-connector.md)
* Oracle (prévisualisation)
* [Salesforce (préversion)](salesforce-connector.md)
* [ServiceNow](servicenow-connector.md)

La [galerie de connecteurs Graph](connectors-gallery.md) contient une brève description de chacun de ces connecteurs Graph. Si vous êtes prêt à connecter l’une de ces [](configure-connector.md) sources de données à votre client, n’oubliez pas de lire la vue d’ensemble du programme d’installation et les autres articles de la section Connecteurs d’installation par Microsoft qui s’appliquent à votre source de données.

### <a name="graph-connectors-by-our-partners"></a>Connecteurs graph par nos partenaires

La [galerie de connecteurs Microsoft Graph](connectors-gallery.md) comprend une brève description de chacun des connecteurs Graph créés par nos partenaires et un lien vers le site web de chaque partenaire. Contactez directement chaque partenaire pour en savoir plus.

### <a name="build-your-own-graph-connector"></a>Créer votre propre connecteur Graph

Si vous envisagez de créer votre propre connecteur Graph, consultez la vue d’ensemble de [l’API recherche Microsoft dans Microsoft Graph](https://docs.microsoft.com/graph/search-concept-overview) pour plus d’informations.

## <a name="how-do-i-manage-my-connections"></a>Comment gérer mes connexions ?

Vous pouvez gérer vos connexions à partir de [l’onglet Connecteurs](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/Connectors) dans le Centre d’administration [Microsoft 365.](https://admin.microsoft.com/) Pour [plus d’informations, voir](manage-connector.md) Gérer vos connexions.

## <a name="what-are-the-license-requirements-and-terms-of-use-for-graph-connectors"></a>Quelles sont les conditions d’utilisation et les conditions d’utilisation des licences pour les connecteurs Graph ?

Vous avez besoin d’une licence Microsoft 365 ou Office 365 valide et d’un quota de connecteurs Graph suffisant pour que les utilisateurs de votre organisation visualisent les données des connecteurs dans leurs résultats de recherche.

Pour plus d’informations, voir [Conditions d’utilisation](licensing.md) et conditions [d’utilisation des licences.](terms-of-use.md)

## <a name="what-are-the-preview-features"></a>Quelles sont les fonctionnalités d’aperçu ?

Bien que les connecteurs Microsoft Graph et les API de recherche Microsoft soient désormais généralement disponibles, plusieurs fonctionnalités sont en prévisualisation.

L’ensemble des connecteurs et des fonctionnalités de la prévisualisation comprend les éléments suivants :

* [Connecteur Azure DevOps](azure-devops-connector.md)
* [Connecteur Salesforce](salesforce-connector.md)
* [Connecteur ServiceNow avec](servicenow-connector.md) autorisations de recherche qui utilisent des ACA sources
* [Gérer le cluster de résultat](result-cluster.md)

## <a name="how-do-i-customize-and-configure-search-results"></a>Comment personnaliser et configurer les résultats de la recherche ?

Il existe plusieurs façons de personnaliser et de configurer les résultats de la recherche. Pour en savoir plus, consultez les articles suivants :

* [Gérer des secteurs verticaux et des types de résultats](customize-search-page.md)
* [Gérer les dispositions des résultats de la recherche](customize-results-layout.md)
* [Gérer le cluster de résultat](result-cluster.md)
* [Gérer les filtres personnalisés](custom-filters.md)

## <a name="how-do-i-search-my-connector-data-from-a-custom-application"></a>Comment effectuer une recherche dans les données de mon connecteur à partir d’une application personnalisée ?

Une fois les données personnalisées indexées, les développeurs peuvent [interroger ces données.](https://docs.microsoft.com/graph/search-concept-custom-types) Vous pouvez afficher vos données dans n’importe quelle application. Pour plus d’informations, voir la [vue d’ensemble de l’API recherche Microsoft dans Microsoft Graph](https://docs.microsoft.com/graph/search-concept-overview).

## <a name="limitations"></a>Limites

* Lorsque vous **publiez** un connecteur microsoft, la création de la connexion peut prendre quelques minutes. Pendant ce temps, la connexion affiche son état en attente.

* Le [Centre d’administration Microsoft 365](https://admin.microsoft.com) ne prend pas en charge la modification du schéma de recherche après la publication d’une connexion.  Pour modifier le schéma de recherche, supprimez votre connexion, puis créez-en une nouvelle.

* Le débit d’ingestion est limitée à environ quatre éléments par seconde.

* Il n’existe aucune prise en charge des mises à jour de schéma. Après avoir créé une configuration de connexion, il n’existe aucun moyen de mettre à jour le schéma. Vous pouvez uniquement supprimer et re-créer la connexion.

* Il existe une limite de connexions. Chaque client peut créer jusqu’à 10 connexions.

* La prise en charge de la modification de la connexion n’est pas disponible. Une fois la connexion créée, vous ne pouvez pas la modifier. Si vous devez modifier des détails, vous devez supprimer et recréer la connexion.
