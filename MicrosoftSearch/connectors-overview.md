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
ms.openlocfilehash: c60154e5769e96cf8a6a4a399d344da259f4e7b0
ms.sourcegitcommit: bfcab9d42e93addccd1e3875b41bc9cc1b6986cc
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/04/2019
ms.locfileid: "37949734"
---
# <a name="overview-of-microsoft-graph-connectors"></a><span data-ttu-id="066a8-103">Vue d’ensemble des connecteurs Microsoft Graph</span><span class="sxs-lookup"><span data-stu-id="066a8-103">Overview of Microsoft Graph connectors</span></span>

<span data-ttu-id="066a8-104">Microsoft Search indexe toutes vos données Microsoft 365 de façon à ce qu’elles puissent être recherchées pour les utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="066a8-104">Microsoft Search indexes all your Microsoft 365 data to make it searchable for users.</span></span> <span data-ttu-id="066a8-105">Avec les connecteurs Microsoft Graph, votre organisation peut indexer des données tierces pour apparaître dans les résultats de recherche de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="066a8-105">With Microsoft Graph connectors, your organization can index third-party data to appear in Microsoft Search results.</span></span> <span data-ttu-id="066a8-106">Les données tierces peuvent être hébergées sur site ou dans les nuages publics ou privés.</span><span class="sxs-lookup"><span data-stu-id="066a8-106">The third-party data can be hosted on-premises or in the public or private clouds.</span></span> <span data-ttu-id="066a8-107">Les connecteurs développent les types de sources de contenu pouvant faire l’objet d’une recherche dans vos applications de productivité Microsoft 365 et l’écosystème Microsoft plus large.</span><span class="sxs-lookup"><span data-stu-id="066a8-107">Connectors expand the types of content sources that are searchable in your Microsoft 365 productivity apps and the broader Microsoft ecosystem.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="066a8-108">**Clause d’exclusion de responsabilité**: les connecteurs Microsoft Graph, les API d’indexation et les API de recherche sont actuellement en version préliminaire.</span><span class="sxs-lookup"><span data-stu-id="066a8-108">**DISCLAIMER**: Microsoft Graph connectors, indexing APIs, and search APIs are currently in preview.</span></span> <span data-ttu-id="066a8-109">Pour en savoir plus sur l’aperçu, voir [connecteurs Preview](connectors-preview.md).</span><span class="sxs-lookup"><span data-stu-id="066a8-109">To learn more about the preview, see [Connectors Preview](connectors-preview.md).</span></span> <span data-ttu-id="066a8-110">Pour participer à l’aperçu, vous devez d’abord envoyer le formulaire d’abonnement de l' [aperçu des connecteurs Microsoft Graph](https://forms.office.com/Pages/ResponsePage.aspx?id=v4j5cvGGr0GRqy180BHbRxWYgu82J_RFnMMATAS6_chUNVYwNU1CMDNZUDBSSDZKWVo2RDJDRjRLQi4u).</span><span class="sxs-lookup"><span data-stu-id="066a8-110">To participate in the preview, you must first submit the [Microsoft Graph Connectors Preview Signup form](https://forms.office.com/Pages/ResponsePage.aspx?id=v4j5cvGGr0GRqy180BHbRxWYgu82J_RFnMMATAS6_chUNVYwNU1CMDNZUDBSSDZKWVo2RDJDRjRLQi4u).</span></span>

## <a name="architecture"></a><span data-ttu-id="066a8-111">Architecture</span><span class="sxs-lookup"><span data-stu-id="066a8-111">Architecture</span></span>
<span data-ttu-id="066a8-112">Le diagramme d’architecture suivant de la plateforme Microsoft Graph montre comment le contenu du connecteur passe par l’indexation de contenu aux résultats de l’utilisateur dans les clients [Microsoft Search](https://docs.microsoft.com/microsoftsearch/overview-microsoft-search) .</span><span class="sxs-lookup"><span data-stu-id="066a8-112">The following architectural diagram of the Microsoft Graph platform shows how connector content flows through content indexing to user results in [Microsoft Search](https://docs.microsoft.com/microsoftsearch/overview-microsoft-search) clients.</span></span> <span data-ttu-id="066a8-113">Cet article décrit chacun des blocs de construction clés du processus de flux de données des connecteurs Microsoft Graph.</span><span class="sxs-lookup"><span data-stu-id="066a8-113">This article explains each of the key building blocks in the Microsoft Graph connectors data flow process.</span></span>

<span data-ttu-id="066a8-114">[VOIR LE DIAGRAMME TEMPORAIRE CI-DESSOUS]![](media/highlevel-connectors_FINAL.jpg)</span><span class="sxs-lookup"><span data-stu-id="066a8-114">[SEE TEMPORARY DIAGRAM BELOW] ![](media/highlevel-connectors_FINAL.jpg)</span></span>

<span data-ttu-id="066a8-115">L’API instancie une connexion par source de données.</span><span class="sxs-lookup"><span data-stu-id="066a8-115">The API instantiates one connection per data source.</span></span> <span data-ttu-id="066a8-116">Ensuite, les données sources circulent via l’API d’indexation de contenu de Microsoft pour être indexées et stockées.</span><span class="sxs-lookup"><span data-stu-id="066a8-116">Then the source data flows through Microsoft’s content indexing API to be indexed and stored.</span></span> <span data-ttu-id="066a8-117">Les connexions établies interagissent avec Microsoft Search, afin que les utilisateurs puissent obtenir des résultats de recherche.</span><span class="sxs-lookup"><span data-stu-id="066a8-117">Established connections interact with Microsoft Search, so users can get search results.</span></span>

<span data-ttu-id="066a8-118">Vous pouvez configurer tous les connecteurs créés par Microsoft dans le [Centre d’administration 365 de Microsoft](https://admin.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="066a8-118">You can configure all the Microsoft-built connectors in the [Microsoft 365 admin center](https://admin.microsoft.com).</span></span> <span data-ttu-id="066a8-119">Le centre d’administration simplifie la configuration de votre connecteur avec une interface utilisateur simple.</span><span class="sxs-lookup"><span data-stu-id="066a8-119">The admin center simplifies configuring your connector with a simple user interface.</span></span>

<span data-ttu-id="066a8-120">Pour créer une **connexion** à une source de données, les administrateurs ont besoin d’un accès authentifié aux données et à l’intégralité du référentiel de contenu.</span><span class="sxs-lookup"><span data-stu-id="066a8-120">To create a **connection** to a data source, admins need authenticated access to the data and the entire content repository.</span></span> <span data-ttu-id="066a8-121">Les données sont chargées pour l’indexation par le service connecteur Graph.</span><span class="sxs-lookup"><span data-stu-id="066a8-121">The data is fed to the graph connector service for indexing.</span></span>

## <a name="available-connectors"></a><span data-ttu-id="066a8-122">Connecteurs disponibles</span><span class="sxs-lookup"><span data-stu-id="066a8-122">Available connectors</span></span>
<span data-ttu-id="066a8-123">Il existe actuellement 6 connecteurs créés par Microsoft et plus de 100 connecteurs sont disponibles auprès de nos partenaires pour l’écosystème.</span><span class="sxs-lookup"><span data-stu-id="066a8-123">There are currently 6 Microsoft-built connectors, and over 100 connectors are available from our ecosystem partners.</span></span>

<span data-ttu-id="066a8-124">Pour afficher un aperçu des connecteurs de l’un de nos partenaires de l’écosystème, contactez-les directement.</span><span class="sxs-lookup"><span data-stu-id="066a8-124">To preview connectors from one of our ecosystem partners, contact them directly.</span></span> <span data-ttu-id="066a8-125">Pour plus d’informations, consultez la [Galerie des connecteurs Microsoft Graph](connectors-gallery.md).</span><span class="sxs-lookup"><span data-stu-id="066a8-125">For more information, see the [Microsoft Graph connectors gallery](connectors-gallery.md).</span></span>

<span data-ttu-id="066a8-126">Vous pouvez également créer votre propre connecteur avec l' [API d’indexation Microsoft Graph](/graph/search-index-overview).</span><span class="sxs-lookup"><span data-stu-id="066a8-126">You can also build your own connector with the [Microsoft Graph indexing API](/graph/search-index-overview).</span></span>

### <a name="connectors-by-microsoft"></a><span data-ttu-id="066a8-127">Connecteurs par Microsoft</span><span class="sxs-lookup"><span data-stu-id="066a8-127">Connectors by Microsoft</span></span>
<span data-ttu-id="066a8-128">La version d’évaluation des connecteurs Microsoft Graph comprend 6 connecteurs créés par Microsoft.</span><span class="sxs-lookup"><span data-stu-id="066a8-128">The Microsoft Graph connectors preview release includes 6 Microsoft-built connectors.</span></span> <span data-ttu-id="066a8-129">Vous pouvez les configurer dans le [Centre d’administration 365 de Microsoft](https://admin.microsoft.com) et apprendre à [configurer votre connecteur créé par Microsoft](configure-connector.md).</span><span class="sxs-lookup"><span data-stu-id="066a8-129">You can set them up in the [Microsoft 365 admin center](https://admin.microsoft.com) and learn how to [Set up your Microsoft-built connector](configure-connector.md).</span></span>

<span data-ttu-id="066a8-130">Les sections suivantes fournissent des descriptions succinctes de ces connecteurs créés par Microsoft.</span><span class="sxs-lookup"><span data-stu-id="066a8-130">The following sections provide brief descriptions for these Microsoft-built connectors.</span></span> <span data-ttu-id="066a8-131">Vous pouvez obtenir plus d’informations dans les Articles liés à chaque connecteur.</span><span class="sxs-lookup"><span data-stu-id="066a8-131">You can get more information in the linked articles for each connector.</span></span>

- <span data-ttu-id="066a8-132">**[Azure Data Lake Storage Gen2](https://docs.microsoft.com/azure/storage/blobs/data-lake-storage-introduction)**.</span><span class="sxs-lookup"><span data-stu-id="066a8-132">**[Azure Data Lake Storage Gen2](https://docs.microsoft.com/azure/storage/blobs/data-lake-storage-introduction)**.</span></span> <span data-ttu-id="066a8-133">Avec ce connecteur Microsoft Graph, les utilisateurs de votre organisation peuvent rechercher des fichiers et du contenu stockés dans des conteneurs d’objets BLOB Azure.</span><span class="sxs-lookup"><span data-stu-id="066a8-133">With this Microsoft Graph connector, users in your organization can search for files and content stored in Azure Blob containers.</span></span> <span data-ttu-id="066a8-134">Le connecteur Azure Data Lake Storage Gen2 indexe également les dossiers activés dans la hiérarchie dans les comptes Gen2 de stockage Azure Data Lake que vous spécifiez.</span><span class="sxs-lookup"><span data-stu-id="066a8-134">The Azure Data Lake Storage Gen2 connector also indexes hierarchy-enabled folders in Azure Data Lake Storage Gen2 accounts that you specify.</span></span>
<span data-ttu-id="066a8-135">En savoir plus sur le [connecteur Azure Data Lake Storage Gen2](azure-data-lake-connector.md).</span><span class="sxs-lookup"><span data-stu-id="066a8-135">Learn more about the [Azure Data Lake Storage Gen2 connector](azure-data-lake-connector.md).</span></span>

- <span data-ttu-id="066a8-136">**Sites Web d’entreprise**.</span><span class="sxs-lookup"><span data-stu-id="066a8-136">**Enterprise websites**.</span></span> <span data-ttu-id="066a8-137">Avec ce connecteur Microsoft Graph, les utilisateurs de votre organisation peuvent effectuer des recherches dans des pages de n’importe quel site Web d’entreprise non SharePoint.</span><span class="sxs-lookup"><span data-stu-id="066a8-137">With this Microsoft Graph connector, users in your organization can search over pages in any non-SharePoint enterprise website.</span></span>
<span data-ttu-id="066a8-138">En savoir plus sur le [connecteur de sites Web d’entreprise](enterprise-web-connector.md).</span><span class="sxs-lookup"><span data-stu-id="066a8-138">Learn more about the [Enterprise websites connector](enterprise-web-connector.md).</span></span>

- <span data-ttu-id="066a8-139">**Partage de fichiers**.</span><span class="sxs-lookup"><span data-stu-id="066a8-139">**File share**.</span></span> <span data-ttu-id="066a8-140">Avec ce connecteur Microsoft Graph, les utilisateurs de votre organisation peuvent rechercher des fichiers stockés sur des partages de fichiers Windows locaux.</span><span class="sxs-lookup"><span data-stu-id="066a8-140">With this Microsoft Graph connector, users in your organization can search for files stored on on-premises Windows file shares.</span></span>
<span data-ttu-id="066a8-141">En savoir plus sur le [connecteur de partage de fichiers](file-share-connector.md).</span><span class="sxs-lookup"><span data-stu-id="066a8-141">Learn more about the [File share connector](file-share-connector.md).</span></span>

- <span data-ttu-id="066a8-142">**[MediaWiki](https://www.mediawiki.org/wiki/MediaWiki)**.</span><span class="sxs-lookup"><span data-stu-id="066a8-142">**[MediaWiki](https://www.mediawiki.org/wiki/MediaWiki)**.</span></span> <span data-ttu-id="066a8-143">Avec ce connecteur Microsoft Graph, les utilisateurs peuvent rechercher des Articles de la base de connaissances sur des sites wiki créés par votre organisation avec MediaWiki.</span><span class="sxs-lookup"><span data-stu-id="066a8-143">With this Microsoft Graph connector, users can search for knowledge-base articles on wiki sites your organization creates with MediaWiki.</span></span>
<span data-ttu-id="066a8-144">En savoir plus sur le [connecteur MediaWiki](mediawiki-connector.md).</span><span class="sxs-lookup"><span data-stu-id="066a8-144">Learn more about the [MediaWiki connector](mediawiki-connector.md).</span></span>

- <span data-ttu-id="066a8-145">**[Microsoft SQL Server](https://www.microsoft.com/sql-server/sql-server-2017)**.</span><span class="sxs-lookup"><span data-stu-id="066a8-145">**[Microsoft SQL server](https://www.microsoft.com/sql-server/sql-server-2017)**.</span></span> <span data-ttu-id="066a8-146">Avec ce connecteur Microsoft Graph, les utilisateurs de votre organisation peuvent rechercher des données dans des bases de données SQL Server locales.</span><span class="sxs-lookup"><span data-stu-id="066a8-146">With this Microsoft Graph connector, users in your organization can search for data in on-premises SQL server databases.</span></span>
<span data-ttu-id="066a8-147">En savoir plus sur le [Connecteur Microsoft SQL Server](MSSQL-connector.md).</span><span class="sxs-lookup"><span data-stu-id="066a8-147">Learn more about the [Microsoft SQL server connector](MSSQL-connector.md).</span></span>

- <span data-ttu-id="066a8-148">**[ServiceNow](https://www.servicenow.com)**.</span><span class="sxs-lookup"><span data-stu-id="066a8-148">**[ServiceNow](https://www.servicenow.com)**.</span></span> <span data-ttu-id="066a8-149">Avec ce connecteur Microsoft Graph, les utilisateurs de votre organisation peuvent rechercher des Articles de la base de connaissances à partir de votre instance ServiceNow.</span><span class="sxs-lookup"><span data-stu-id="066a8-149">With this Microsoft Graph connector, users in your organization can search for knowledge-base articles from your ServiceNow instance.</span></span>
<span data-ttu-id="066a8-150">En savoir plus sur le [connecteur ServiceNow](servicenow-connector.md).</span><span class="sxs-lookup"><span data-stu-id="066a8-150">Learn more about the [ServiceNow connector](servicenow-connector.md).</span></span>

### <a name="connectors-from-our-partners"></a><span data-ttu-id="066a8-151">Connecteurs de nos partenaires</span><span class="sxs-lookup"><span data-stu-id="066a8-151">Connectors from our partners</span></span>
<span data-ttu-id="066a8-152">Il existe plus de 100 connecteurs disponibles pour un aperçu auprès de nos partenaires de l’écosystème.</span><span class="sxs-lookup"><span data-stu-id="066a8-152">There are over 100 connectors available for preview from our ecosystem partners.</span></span> <span data-ttu-id="066a8-153">Pour afficher un aperçu des connecteurs de l’un de nos partenaires de l’écosystème, contactez-les directement.</span><span class="sxs-lookup"><span data-stu-id="066a8-153">To preview connectors from one of our ecosystem partners, contact them directly.</span></span>
<span data-ttu-id="066a8-154">Pour en savoir plus sur les connecteurs de nos partenaires, consultez la [Galerie de connecteurs Microsoft Graph](connectors-gallery.md).</span><span class="sxs-lookup"><span data-stu-id="066a8-154">Learn more about connectors from our partners in the [Microsoft Graph connectors gallery](connectors-gallery.md).</span></span>

### <a name="build-your-own-connector"></a><span data-ttu-id="066a8-155">Créer votre propre connecteur</span><span class="sxs-lookup"><span data-stu-id="066a8-155">Build your own connector</span></span>
<span data-ttu-id="066a8-156">Pour indexer des fichiers ou des types de données personnalisés, les développeurs peuvent créer des connecteurs dans [Microsoft Graph](https://developer.microsoft.com/graph/).</span><span class="sxs-lookup"><span data-stu-id="066a8-156">To index custom data types or files, developers can create connectors in [Microsoft Graph](https://developer.microsoft.com/graph/).</span></span> <span data-ttu-id="066a8-157">Un connecteur est une application qui utilise l’API d’indexation Microsoft Graph pour créer une connexion et diffuser des éléments dans l’index de recherche Microsoft.</span><span class="sxs-lookup"><span data-stu-id="066a8-157">A connector is an application that uses the Microsoft Graph indexing API to create a connection and push items into the Microsoft Search index.</span></span> <span data-ttu-id="066a8-158">Pour plus d’informations, consultez la rubrique [Microsoft Graph Indexing API Overview](https://docs.microsoft.com/graph/search-index-overview).</span><span class="sxs-lookup"><span data-stu-id="066a8-158">For more information, see the [Microsoft Graph indexing API overview](https://docs.microsoft.com/graph/search-index-overview).</span></span>

### <a name="search-results-with-your-custom-built-connector"></a><span data-ttu-id="066a8-159">Résultats de la recherche avec votre connecteur personnalisé</span><span class="sxs-lookup"><span data-stu-id="066a8-159">Search results with your custom-built connector</span></span>
<span data-ttu-id="066a8-160">Une fois que les données personnalisées sont indexées, les développeurs peuvent interroger ces données à l’aide de l’API de recherche de Microsoft Graph.</span><span class="sxs-lookup"><span data-stu-id="066a8-160">Once custom data is indexed, developers can query this data using the search API in Microsoft Graph.</span></span> <span data-ttu-id="066a8-161">Vous pouvez afficher vos données dans n’importe quelle application.</span><span class="sxs-lookup"><span data-stu-id="066a8-161">You can view your data in any application.</span></span> <span data-ttu-id="066a8-162">Pour plus d’informations, consultez la rubrique [Microsoft Graph Search API Overview](https://docs.microsoft.com/graph/api/resources/indexing-api-overview).</span><span class="sxs-lookup"><span data-stu-id="066a8-162">For more information, see [Microsoft Graph search API overview](https://docs.microsoft.com/graph/api/resources/indexing-api-overview).</span></span>

## <a name="license-requirements"></a><span data-ttu-id="066a8-163">Critères de licence</span><span class="sxs-lookup"><span data-stu-id="066a8-163">License requirements</span></span>
<span data-ttu-id="066a8-164">Pour afficher les données des connecteurs dans les résultats de la recherche, les utilisateurs doivent disposer de l’un des abonnements Microsoft 365 suivants :</span><span class="sxs-lookup"><span data-stu-id="066a8-164">To view data from connectors in your search results, users must have one of the following Microsoft 365 subscriptions:</span></span>
- <span data-ttu-id="066a8-165"><a href="https://www.microsoft.com/microsoft-365/compare-all-microsoft-365-plans" target="_blank">Microsoft 365 pour entreprise E3 ou E5</a></span><span class="sxs-lookup"><span data-stu-id="066a8-165"><a href="https://www.microsoft.com/microsoft-365/compare-all-microsoft-365-plans" target="_blank">Microsoft 365 for enterprise E3 or E5</a></span></span>
- <span data-ttu-id="066a8-166"><a href="https://www.microsoft.com/microsoft-365/academic/compare-office-365-education-plans?activetab=tab:primaryr1" target="_blank">Microsoft 365 éducation a3 ou a5</a></span><span class="sxs-lookup"><span data-stu-id="066a8-166"><a href="https://www.microsoft.com/microsoft-365/academic/compare-office-365-education-plans?activetab=tab:primaryr1" target="_blank">Microsoft 365 Education A3 or A5</a></span></span>