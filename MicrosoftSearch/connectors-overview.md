---
title: Vue d’ensemble des connecteurs
ms.author: v-pamcn
author: monaray
manager: shohara
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: Vue d’ensemble des connecteurs Microsoft Graph pour la recherche Microsfot
ms.openlocfilehash: c372d4750c6644f0f98054a2531b6431fb8cd334
ms.sourcegitcommit: 90f82efc3671c477536cbe8d8846132910b64600
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/04/2019
ms.locfileid: "37961951"
---
# <a name="overview-of-microsoft-graph-connectors"></a>Vue d’ensemble des connecteurs Microsoft Graph

Microsoft Search indexe toutes vos données Microsoft 365 de façon à ce qu’elles puissent être recherchées pour les utilisateurs. Avec les connecteurs Microsoft Graph, votre organisation peut indexer des données tierces pour apparaître dans les résultats de recherche de Microsoft. Les données tierces peuvent être hébergées sur site ou dans les nuages publics ou privés. Les connecteurs développent les types de sources de contenu pouvant faire l’objet d’une recherche dans vos applications de productivité Microsoft 365 et l’écosystème Microsoft plus large.

> [!IMPORTANT]
> **Clause d’exclusion de responsabilité**: les connecteurs Microsoft Graph et les API Microsoft Search (index and Search) sont actuellement en version préliminaire. Pour en savoir plus sur l’aperçu, consultez la rubrique [aperçu des connecteurs Microsoft Graph](connectors-preview.md). Pour participer à l’aperçu, vous devez d’abord envoyer le formulaire d’abonnement de l' [aperçu des connecteurs Microsoft Graph](https://forms.office.com/Pages/ResponsePage.aspx?id=v4j5cvGGr0GRqy180BHbRxWYgu82J_RFnMMATAS6_chUNVYwNU1CMDNZUDBSSDZKWVo2RDJDRjRLQi4u).

## <a name="architecture"></a>Architecture
Le diagramme d’architecture suivant de la plateforme Microsoft Graph montre comment le contenu du connecteur passe par l’indexation de contenu aux résultats de l’utilisateur dans les clients [Microsoft Search](https://docs.microsoft.com/microsoftsearch/overview-microsoft-search) . Cet article décrit chacun des blocs de construction clés du processus de flux de données des connecteurs Microsoft Graph.

![](media/highlevel-connectors_FINAL.png)

L’API instancie une connexion par source de données. L’API indexe et stocke les données. Les connexions établies interagissent avec Microsoft Search, afin que les utilisateurs puissent obtenir des résultats de recherche.

Vous pouvez configurer tous les connecteurs créés par Microsoft dans le [Centre d’administration 365 de Microsoft](https://admin.microsoft.com). Le centre d’administration simplifie la configuration de votre connecteur avec une interface utilisateur simple.

Pour créer une **connexion** à une source de données, les administrateurs ont besoin d’un accès authentifié aux données et à l’intégralité du référentiel de contenu. Les données sont chargées pour l’indexation par le service connecteur Graph.

## <a name="available-connectors"></a>Connecteurs disponibles
Il existe actuellement 6 connecteurs créés par Microsoft et plus de 100 connecteurs sont disponibles auprès de nos partenaires pour l’écosystème.

Pour afficher un aperçu des connecteurs de l’un de nos partenaires de l’écosystème, contactez-les directement. Pour plus d’informations, consultez la [Galerie des connecteurs Microsoft Graph](connectors-gallery.md).

Vous pouvez également [créer votre propre connecteur](https://docs.microsoft.com/graph/search-concept-overview).

### <a name="connectors-by-microsoft"></a>Connecteurs par Microsoft
La version d’évaluation des connecteurs Microsoft Graph comprend 6 connecteurs créés par Microsoft. Vous pouvez les configurer dans le [Centre d’administration 365 de Microsoft](https://admin.microsoft.com) et apprendre à [configurer votre connecteur créé par Microsoft](configure-connector.md).

Les sections suivantes fournissent des descriptions succinctes de ces connecteurs créés par Microsoft. Vous pouvez obtenir plus d’informations dans les Articles liés à chaque connecteur.

- **[Azure Data Lake Storage Gen2](https://docs.microsoft.com/azure/storage/blobs/data-lake-storage-introduction)**. Avec ce connecteur Microsoft Graph, les utilisateurs de votre organisation peuvent rechercher des fichiers et du contenu stockés dans des conteneurs d’objets BLOB Azure. Le connecteur Azure Data Lake Storage Gen2 indexe également les dossiers activés dans la hiérarchie dans les comptes Gen2 de stockage Azure Data Lake que vous spécifiez.
En savoir plus sur le [connecteur Azure Data Lake Storage Gen2](azure-data-lake-connector.md).

- **Sites Web d’entreprise**. Avec ce connecteur Microsoft Graph, les utilisateurs de votre organisation peuvent effectuer des recherches dans des pages de n’importe quel site Web d’entreprise non SharePoint.
En savoir plus sur le [connecteur de sites Web d’entreprise](enterprise-web-connector.md).

- **Partage de fichiers**. Avec ce connecteur Microsoft Graph, les utilisateurs de votre organisation peuvent rechercher des fichiers stockés sur des partages de fichiers Windows locaux.
En savoir plus sur le [connecteur de partage de fichiers](file-share-connector.md).

- **[MediaWiki](https://www.mediawiki.org/wiki/MediaWiki)**. Avec ce connecteur Microsoft Graph, les utilisateurs peuvent rechercher des Articles de la base de connaissances sur des sites wiki créés par votre organisation avec MediaWiki.
En savoir plus sur le [connecteur MediaWiki](mediawiki-connector.md).

- **[Microsoft SQL Server](https://www.microsoft.com/sql-server/sql-server-2017)**. Avec ce connecteur Microsoft Graph, les utilisateurs de votre organisation peuvent rechercher des données dans des bases de données SQL Server locales.
En savoir plus sur le [Connecteur Microsoft SQL Server](MSSQL-connector.md).

- **[ServiceNow](https://www.servicenow.com)**. Avec ce connecteur Microsoft Graph, les utilisateurs de votre organisation peuvent rechercher des Articles de la base de connaissances à partir de votre instance ServiceNow.
En savoir plus sur le [connecteur ServiceNow](servicenow-connector.md).

### <a name="connectors-from-our-partners"></a>Connecteurs de nos partenaires
Il existe plus de 100 connecteurs disponibles pour un aperçu auprès de nos partenaires de l’écosystème. Pour afficher un aperçu des connecteurs de l’un de nos partenaires de l’écosystème, contactez-les directement.
Pour en savoir plus sur les connecteurs de nos partenaires, consultez la [Galerie de connecteurs Microsoft Graph](connectors-gallery.md).

### <a name="build-your-own-connector"></a>Créer votre propre connecteur
Pour indexer des fichiers ou des types de données personnalisés, les développeurs peuvent créer des connecteurs dans [Microsoft Graph](https://developer.microsoft.com/graph/). Un connecteur est une application qui [crée une connexion](https://docs.microsoft.com/graph/search-index-manage-connections) et envoie des éléments dans l’index de recherche Microsoft. Pour plus d’informations, reportez-vous à la rubrique [vue d’ensemble de l’expérience Microsoft Search pour les applications sur Microsoft Graph](https://docs.microsoft.com/graph/search-concept-overview).

### <a name="search-results-with-your-custom-built-connector"></a>Résultats de la recherche avec votre connecteur personnalisé
Une fois que les données personnalisées sont indexées, les développeurs peuvent [interroger ces données](https://docs.microsoft.com/graph/search-concept-custom-types). Vous pouvez afficher vos données dans n’importe quelle application. Pour plus d’informations, reportez-vous à la rubrique [vue d’ensemble de l’expérience Microsoft Search pour les applications sur Microsoft Graph](https://docs.microsoft.com/graph/search-concept-overview).

## <a name="license-requirements"></a>Critères de licence
Pour afficher les données des connecteurs dans les résultats de la recherche, les utilisateurs doivent disposer de l’un des abonnements Microsoft 365 suivants :
- <a href="https://www.microsoft.com/microsoft-365/compare-all-microsoft-365-plans" target="_blank">Microsoft 365 pour entreprise E3 ou E5</a>
- <a href="https://www.microsoft.com/microsoft-365/academic/compare-office-365-education-plans?activetab=tab:primaryr1" target="_blank">Microsoft 365 éducation a3 ou a5</a>
