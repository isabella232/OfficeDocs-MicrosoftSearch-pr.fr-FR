---
title: Présentation des connecteurs Graph Microsoft
ms.author: mecampos
author: mecampos
manager: umas
audience: Admin
ms.audience: Admin
ms.topic: article
ms.service: mssearch
ms.localizationpriority: medium
search.appverid:
- BFB160
- MET150
- MOE150
description: Vue d’ensemble des connecteurs Graph Microsoft pour Recherche Microsoft
ms.openlocfilehash: 006ab3f56eb4976b44904e5191ae8fd256c8d5de
ms.sourcegitcommit: 3e069fd920b5fcdfe97a0261930447e9e87d9013
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/10/2021
ms.locfileid: "58973526"
---
<!---Previous ms.author: monaray --->

# <a name="overview-of-microsoft-graph-connectors"></a>Vue d’ensemble des connecteurs Microsoft Graph

[Recherche Microsoft](./overview-microsoft-search.md) indexe toutes vos [données Microsoft 365](https://www.microsoft.com/microsoft-365) pour les rendre utilisables dans une recherche pour les utilisateurs. Avec les connecteurs Graph Microsoft, votre organisation peut indexer des données tierces afin qu’elles apparaissent dans Recherche Microsoft résultats. Cette fonctionnalité élargit les types de sources de contenu disponibles dans vos applications de productivité Microsoft 365 et dans l’écosystème Microsoft plus vaste. Les données tierces peuvent être hébergées en local ou dans les clouds publics ou privés.

<!---link Microsoft Graph reference in line 19 when we have access to relevant documentation--->

Cet article est destiné à aider les administrateurs Microsoft 365 trouver les ressources disponibles pour répondre aux questions suivantes :

* [Quelles sources de données peuvent être connectées à Recherche Microsoft ?](#what-data-sources-can-be-connected-to-microsoft-search)
* [Comment gérer mes connexions ?](#how-do-i-manage-my-connections)
* [Quelles sont les conditions d’utilisation et les conditions d’utilisation des licences pour les connecteurs Graph Microsoft ?](#what-are-the-license-requirements-and-terms-of-use-for-connectors)
* [Quelles sont les fonctionnalités d’aperçu ?](#what-are-the-preview-features)
* [Comment personnaliser et configurer les résultats de la recherche ?](#how-do-i-customize-and-configure-search-results)
* [Comment effectuer une recherche dans les données de mon connecteur à partir d’une application personnalisée ?](#how-do-i-search-my-connector-data-from-a-custom-application)
* [Comment personnaliser les résultats de recherche ?](#how-do-i-customize-search-results)
* [Quelles sont les limitations du connecteur ?](#what-are-the-connector-limitations)

<!---Add Value, scenario, example, and/or graphic in December updates--->
<!---Probably remove architecture section below
## Architecture

The following architectural diagram of the Microsoft Graph platform shows how Graph connector content flows through content indexing to user results in [Microsoft Search](./overview-microsoft-search.md) clients. The rest of this section explains each of the key building blocks in the diagram.

![Diagram: on-premises and cloud-based data is pulled by connectors and indexed by the Microsoft Search API, and then the Microsoft Search service delivers the results to users.](media/connectors-overview/highlevel-connectors.png)
Graph connectors can pull data from cloud-based (SaaS) data sources and on-premises data stores. The above diagram shows connections to only two data sources, but you can add connections to up ten sources per tenant.

The Microsoft Graph Connectors API instantiates one connection per data source. Then, the API indexes and stores the data. Established connections interact with Microsoft Search, so users can get search results.

You can use the Microsoft 365 [admin center](https://admin.microsoft.com) to setup and manage any of the Graph connectors by Microsoft. The admin center has a simple user interface that makes it easy to establish the connection to your data source, and monitor connection status and utilization.

***Edit paragraph below***
To create a **connection** to a data source, admins need authenticated access to the data and the entire content repository. The data is fed to the graph connector service for indexing.--->

## <a name="what-data-sources-can-be-connected-to-microsoft-search"></a>Quelles sources de données peuvent être connectées à Recherche Microsoft ?

Microsoft fournit 9 connecteurs et nos partenaires de l’écosystème ont créé plus de 100 connecteurs. Vous pouvez également créer votre propre connecteur.

### <a name="microsoft-graph-connectors-by-microsoft"></a>Connecteurs Graph Microsoft par Microsoft

Vous pouvez vous connecter aux sources de données suivantes à l’aide de connecteurs créés par Microsoft :

<!---Add links below when new docs are created--->
* [Azure Data Lake Storage Gen2](azure-data-lake-connector.md)
* [Azure DevOps](azure-devops-connector.md)
* [Azure SQL et Microsoft SQL Server](MSSQL-connector.md)
* [Cloud Cloud Cloud (prévisualisation)](confluence-cloud-connector.md)
* [Sites web d’entreprise](enterprise-web-connector.md)
* [MediaWiki](mediawiki-connector.md)
* [Partage de fichiers](fileshare-connector.md)
* [Oracle SQL](OracleSQL-connector.md)
* [Salesforce](salesforce-connector.md)
* [Connaissances ServiceNow](servicenow-knowledge-connector.md)
* [Catalogue ServiceNow (prévisualisation)](servicenow-catalog-connector.md)


La [galerie de connecteurs Graph](https://www.microsoft.com/microsoft-search/connectors) Microsoft contient une brève description de chacun de ces connecteurs. Si vous êtes prêt à connecter l’une de ces sources [](configure-connector.md) de données à votre client, n’oubliez pas de lire la vue d’ensemble du programme d’installation et les autres articles de la section Connecteurs d’installation par Microsoft qui s’appliquent à votre source de données.

### <a name="microsoft-graph-connectors-by-our-partners"></a>Connecteurs Graph Microsoft par nos partenaires

La [galerie de connecteurs](https://www.microsoft.com/microsoft-search/connectors) Graph Microsoft inclut une brève description de chacun des connecteurs créés par nos partenaires et un lien vers le site web de chaque partenaire. Pour en savoir plus, contactez directement chaque partenaire.

### <a name="build-your-own-microsoft-graph-connector"></a>Créer votre propre connecteur Microsoft Graph

Vous pouvez créer votre propre connecteur si vous préférez. Pour plus d’informations sur la création de connecteurs, voir Créer votre premier connecteur [microsoft Graph personnalisé.](/graph/connecting-external-content-build-quickstart)

## <a name="how-do-i-manage-my-connections"></a>Comment gérer mes connexions ?

Vous pouvez gérer vos connexions à partir de [l’onglet Connecteurs](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/Connectors) dans le [Centre d'administration Microsoft 365](https://admin.microsoft.com/). Pour plus d’informations sur la gestion des connexions, voir : [Gérer vos connexions.](manage-connector.md)

## <a name="what-are-the-license-requirements-and-terms-of-use-for-connectors"></a>Quelles sont les conditions d’utilisation et les conditions d’utilisation des licences pour les connecteurs ?

Vous avez besoin d’une licence Microsoft 365 ou Office 365 valide et d’un quota de connecteurs suffisant pour que les utilisateurs de votre organisation visualisent les données des connecteurs dans leurs résultats de recherche.

Pour plus d’informations, voir [Conditions d’utilisation](licensing.md) et conditions [d’utilisation des licences.](terms-of-use.md)

## <a name="what-are-the-preview-features"></a>Quelles sont les fonctionnalités d’aperçu ?

Bien que les connecteurs Graph microsoft et Recherche Microsoft API soient désormais généralement disponibles, plusieurs fonctionnalités sont disponibles en prévisualisation.

L’ensemble des connecteurs et des fonctionnalités de la prévisualisation comprend les éléments suivants :

* [Azure DevOps connecteur](azure-devops-connector.md)
* [Connecteur Cloud De Cloud](confluence-cloud-connector.md)
* [Connecteur de catalogue ServiceNow](servicenow-catalog-connector.md)
* [Gérer les filtres personnalisés](custom-filters.md)
* [Plusieurs connexions dans un secteur vertical](customize-search-page.md#multiple-connections-in-a-vertical)

## <a name="how-do-i-customize-and-configure-search-results"></a>Comment personnaliser et configurer les résultats de la recherche ?

Il existe de nombreuses façons de personnaliser et de configurer les résultats de recherche. Pour en savoir plus, consultez les articles suivants :

* [Gérer des secteurs verticaux et des types de résultats](customize-search-page.md)
* [Gérer les dispositions des résultats de la recherche](customize-results-layout.md)
* [Gérer le cluster de résultat](result-cluster.md)
* [Gérer les filtres personnalisés](custom-filters.md)

## <a name="how-do-i-search-my-connector-data-from-a-custom-application"></a>Comment effectuer une recherche dans les données de mon connecteur à partir d’une application personnalisée ?

Une fois les données personnalisées indexées, les développeurs peuvent [interroger ces données.](/graph/search-concept-custom-types) Vous pouvez afficher vos données dans n’importe quelle application. Pour plus d’informations, voir la [vue d’ensemble de l’API Recherche Microsoft dans Microsoft Graph](/graph/search-concept-overview).

## <a name="how-do-i-customize-search-results"></a>Comment personnaliser les résultats de recherche ?

L’étape suivante consiste à personnaliser les résultats de recherche comme recommandé dans cet article Comment personnaliser et configurer [les résultats de la recherche ?](#how-do-i-customize-and-configure-search-results) Pour en savoir plus sur la personnalisation des résultats de recherche, voir [Personnaliser la page des résultats de la recherche.](customize-search-page.md)

## <a name="what-are-the-connector-limitations"></a>Quelles sont les limitations du connecteur ?

* Lorsque vous **publiez** un connecteur microsoft, la création de la connexion peut prendre quelques minutes. Pendant ce temps, la connexion affiche son état en attente.

* Le débit d’ingestion est limitée à environ quatre éléments par seconde.

* Il n’existe aucune prise en charge des mises à jour de schéma. Après avoir créé une configuration de connexion, il n’existe aucun moyen de mettre à jour le schéma. Vous pouvez uniquement supprimer et re-créer la connexion.

* Il existe une limite de connexion. Chaque client peut créer jusqu’à 10 connexions.

* Vous ne pouvez pas modifier ou modifier une connexion après sa création. Si vous devez modifier des détails, vous devez supprimer et recréer la connexion.
