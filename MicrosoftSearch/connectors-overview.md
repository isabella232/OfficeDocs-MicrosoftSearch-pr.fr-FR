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
description: Vue d’ensemble des connecteurs Microsoft Graph pour Microsoft Search
ms.openlocfilehash: 7388653927ca6a7af0ba64c3c592f2689780c181
ms.sourcegitcommit: 59cdd3f0f82b7918399bf44d27d9891076090f4f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/20/2020
ms.locfileid: "49367522"
---
# <a name="overview-of-microsoft-graph-connectors"></a>Vue d’ensemble des connecteurs Microsoft Graph

[Microsoft Search](https://docs.microsoft.com/microsoftsearch/overview-microsoft-search) indexe toutes vos données [Microsoft 365](https://www.microsoft.com/microsoft-365) de façon à ce qu’elles puissent être recherchées pour les utilisateurs. Avec les connecteurs Microsoft Graph, votre organisation peut indexer des données tierces afin qu’elles apparaissent dans les résultats de la recherche Microsoft. Cela étend les types de sources de contenu pouvant faire l’objet d’une recherche dans vos applications de productivité Microsoft 365 et l’écosystème Microsoft plus large. Les données tierces peuvent être hébergées sur site ou dans les nuages publics ou privés.

<!---link Microsoft Graph reference in line 19 when we have access to relevant documentation--->

Le reste de cet article est destiné à aider les administrateurs Microsoft 365 à localiser les ressources disponibles pour répondre aux questions suivantes :

* [Quelles sources de données peuvent être connectées à Microsoft Search ?](#what-data-sources-can-be-connected-to-microsoft-search)
* [Comment puis-je gérer mes connexions ?](#how-do-i-manage-my-connections)
* [Quelles sont la licence requise et les conditions d’utilisation des connecteurs Graph ?](#what-are-the-license-requirements-and-terms-of-use-for-graph-connectors)
* [Comment puis-je personnaliser et configurer les résultats de la recherche ?](#how-do-i-customize-and-configure-search-results)
* [Comment rechercher les données de mon connecteur à partir d’une application personnalisée ?](#how-do-i-search-my-connector-data-from-a-custom-application)

<!---Modify to another note that is more accurate--->
> [!IMPORTANT]
> Les connecteurs Microsoft Graph et les API Microsoft Search sont désormais généralement disponibles. Les premiers déploiements seront destinés aux clients configurés pour la version ciblée. Si vous souhaitez utiliser un connecteur Graph dans votre client, les utilisateurs et les administrateurs doivent s’abonner à la [version ciblée](https://docs.microsoft.com/office365/admin/manage/release-options-in-office-365?view=o365-worldwide).

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

## <a name="what-data-sources-can-be-connected-to-microsoft-search"></a>Quelles sources de données peuvent être connectées à Microsoft Search ?

Microsoft propose dix connecteurs Graph et nos partenaires écosystèmes ont créé plus de 100 connecteurs Graph supplémentaires. Vous pouvez également créer votre propre connecteur Graph. 

### <a name="graph-connectors-by-microsoft"></a>Connecteurs Graph par Microsoft

Vous pouvez vous connecter aux sources de données suivantes à l’aide des connecteurs Graph créés par Microsoft :

<!---Need to add a few links below when docs exist--->
* [Azure Data Lake Storage Gen2](azure-data-lake-connector.md)
* [Azure DevOps](azure-devops-connector.md)
* Azure SQL
* [Sites web d’entreprise](enterprise-web-connector.md)
* [MediaWiki](mediawiki-connector.md)
* [Microsoft SQL Server](MSSQL-connector.md)
* [Partage de fichiers](fileshare-connector.md)
* Oracle (aperçu)
* [Salesforce (aperçu)](salesforce-connector.md)
* [ServiceNow](servicenow-connector.md)

La [Galerie de connecteurs Graph](connectors-gallery.md) contient une brève description de chacun de ces connecteurs Graph. Si vous êtes prêt à connecter l’une de ces sources de données à votre client, lisez la présentation de l' [installation](configure-connector.md) et les autres Articles de la section Connecteurs d’installation de Microsoft qui s’appliquent à votre source de données.

### <a name="graph-connectors-by-our-partners"></a>Connecteurs Graph par nos partenaires

La [Galerie de connecteurs Microsoft Graph](connectors-gallery.md) contient une brève description de chacun des connecteurs graphiques créés par nos partenaires, ainsi qu’un lien vers le site Web de chaque partenaire. Pour en savoir plus, contactez chaque partenaire directement.

### <a name="build-your-own-graph-connector"></a>Création de votre propre connecteur Graph

Si vous envisagez de créer votre propre connecteur Graph, reportez-vous à la rubrique [vue d’ensemble de l’API Microsoft Search dans Microsoft Graph](https://docs.microsoft.com/graph/search-concept-overview) pour plus d’informations.

## <a name="how-do-i-manage-my-connections"></a>Comment puis-je gérer mes connexions ?

Vous pouvez gérer vos connexions à partir de l' [onglet Connecteurs](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/Connectors) dans le [Centre d’administration Microsoft 365](https://admin.microsoft.com/). Pour plus d’informations, consultez [la rubrique Manage Your connections](manage-connector.md) .

## <a name="what-are-the-license-requirements-and-terms-of-use-for-graph-connectors"></a>Quelles sont la licence requise et les conditions d’utilisation des connecteurs Graph ?

Pour les utilisateurs de votre organisation, vous avez besoin d’une licence Microsoft 365 ou Office 365 valide et d’un quota de connecteurs graphiques suffisant pour afficher les données des connecteurs dans les résultats de la recherche.

Pour en savoir plus, consultez la rubrique [licences requises et tarifs](licensing.md) et [conditions d’utilisation](terms-of-use.md).

## <a name="how-do-i-customize-and-configure-search-results"></a>Comment puis-je personnaliser et configurer les résultats de la recherche ?

Il existe plusieurs façons de personnaliser et de configurer les résultats de la recherche. Pour en savoir plus, consultez les articles suivants :

* [Gérer des secteurs verticaux et des types de résultats](customize-search-page.md)
* [Gérer les dispositions des résultats de la recherche](customize-results-layout.md)
* [Gérer le cluster de résultats](result-cluster.md)
* [Gérer les filtres personnalisés](custom-filters.md)

## <a name="how-do-i-search-my-connector-data-from-a-custom-application"></a>Comment rechercher les données de mon connecteur à partir d’une application personnalisée ?

Une fois que les données personnalisées sont indexées, les développeurs peuvent [interroger ces données](https://docs.microsoft.com/graph/search-concept-custom-types). Vous pouvez afficher vos données dans n’importe quelle application. Pour plus d’informations, reportez-vous à la rubrique [vue d’ensemble de l’API Microsoft Search dans Microsoft Graph](https://docs.microsoft.com/graph/search-concept-overview).
