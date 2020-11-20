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
# <a name="overview-of-microsoft-graph-connectors"></a><span data-ttu-id="21ae2-103">Vue d’ensemble des connecteurs Microsoft Graph</span><span class="sxs-lookup"><span data-stu-id="21ae2-103">Overview of Microsoft Graph connectors</span></span>

<span data-ttu-id="21ae2-104">[Microsoft Search](https://docs.microsoft.com/microsoftsearch/overview-microsoft-search) indexe toutes vos données [Microsoft 365](https://www.microsoft.com/microsoft-365) de façon à ce qu’elles puissent être recherchées pour les utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="21ae2-104">[Microsoft Search](https://docs.microsoft.com/microsoftsearch/overview-microsoft-search) indexes all your [Microsoft 365](https://www.microsoft.com/microsoft-365) data to make it searchable for users.</span></span> <span data-ttu-id="21ae2-105">Avec les connecteurs Microsoft Graph, votre organisation peut indexer des données tierces afin qu’elles apparaissent dans les résultats de la recherche Microsoft.</span><span class="sxs-lookup"><span data-stu-id="21ae2-105">With Microsoft Graph connectors, your organization can index third-party data so it appears in Microsoft Search results.</span></span> <span data-ttu-id="21ae2-106">Cela étend les types de sources de contenu pouvant faire l’objet d’une recherche dans vos applications de productivité Microsoft 365 et l’écosystème Microsoft plus large.</span><span class="sxs-lookup"><span data-stu-id="21ae2-106">This expands the types of content sources that are searchable in your Microsoft 365 productivity apps and the broader Microsoft ecosystem.</span></span> <span data-ttu-id="21ae2-107">Les données tierces peuvent être hébergées sur site ou dans les nuages publics ou privés.</span><span class="sxs-lookup"><span data-stu-id="21ae2-107">The third-party data can be hosted on-premises or in the public or private clouds.</span></span>

<!---link Microsoft Graph reference in line 19 when we have access to relevant documentation--->

<span data-ttu-id="21ae2-108">Le reste de cet article est destiné à aider les administrateurs Microsoft 365 à localiser les ressources disponibles pour répondre aux questions suivantes :</span><span class="sxs-lookup"><span data-stu-id="21ae2-108">The rest of this article is intended to help Microsoft 365 administrators locate the resources that are avaiable to answer the following questions:</span></span>

* [<span data-ttu-id="21ae2-109">Quelles sources de données peuvent être connectées à Microsoft Search ?</span><span class="sxs-lookup"><span data-stu-id="21ae2-109">What data sources can be connected to Microsoft Search?</span></span>](#what-data-sources-can-be-connected-to-microsoft-search)
* [<span data-ttu-id="21ae2-110">Comment puis-je gérer mes connexions ?</span><span class="sxs-lookup"><span data-stu-id="21ae2-110">How do I manage my connections?</span></span>](#how-do-i-manage-my-connections)
* [<span data-ttu-id="21ae2-111">Quelles sont la licence requise et les conditions d’utilisation des connecteurs Graph ?</span><span class="sxs-lookup"><span data-stu-id="21ae2-111">What are the license requirements and terms of use for Graph connectors?</span></span>](#what-are-the-license-requirements-and-terms-of-use-for-graph-connectors)
* [<span data-ttu-id="21ae2-112">Comment puis-je personnaliser et configurer les résultats de la recherche ?</span><span class="sxs-lookup"><span data-stu-id="21ae2-112">How do I customize and configure search results?</span></span>](#how-do-i-customize-and-configure-search-results)
* [<span data-ttu-id="21ae2-113">Comment rechercher les données de mon connecteur à partir d’une application personnalisée ?</span><span class="sxs-lookup"><span data-stu-id="21ae2-113">How do I search my connector data from a custom application?</span></span>](#how-do-i-search-my-connector-data-from-a-custom-application)

<!---Modify to another note that is more accurate--->
> [!IMPORTANT]
> <span data-ttu-id="21ae2-114">Les connecteurs Microsoft Graph et les API Microsoft Search sont désormais généralement disponibles.</span><span class="sxs-lookup"><span data-stu-id="21ae2-114">Microsoft Graph connectors and Microsoft Search APIs are now generally available.</span></span> <span data-ttu-id="21ae2-115">Les premiers déploiements seront destinés aux clients configurés pour la version ciblée.</span><span class="sxs-lookup"><span data-stu-id="21ae2-115">The first rollouts will be to customers configured for  targeted release.</span></span> <span data-ttu-id="21ae2-116">Si vous souhaitez utiliser un connecteur Graph dans votre client, les utilisateurs et les administrateurs doivent s’abonner à la [version ciblée](https://docs.microsoft.com/office365/admin/manage/release-options-in-office-365?view=o365-worldwide).</span><span class="sxs-lookup"><span data-stu-id="21ae2-116">If you want to use a Graph connector in your tenant, users and administrators must opt into [Targeted release](https://docs.microsoft.com/office365/admin/manage/release-options-in-office-365?view=o365-worldwide).</span></span>

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

## <a name="what-data-sources-can-be-connected-to-microsoft-search"></a><span data-ttu-id="21ae2-117">Quelles sources de données peuvent être connectées à Microsoft Search ?</span><span class="sxs-lookup"><span data-stu-id="21ae2-117">What data sources can be connected to Microsoft Search?</span></span>

<span data-ttu-id="21ae2-118">Microsoft propose dix connecteurs Graph et nos partenaires écosystèmes ont créé plus de 100 connecteurs Graph supplémentaires.</span><span class="sxs-lookup"><span data-stu-id="21ae2-118">Microsoft provides ten Graph connectors and our ecosystem partners have created over 100 additional Graph connectors.</span></span> <span data-ttu-id="21ae2-119">Vous pouvez également créer votre propre connecteur Graph.</span><span class="sxs-lookup"><span data-stu-id="21ae2-119">You can also build your own Graph connector.</span></span> 

### <a name="graph-connectors-by-microsoft"></a><span data-ttu-id="21ae2-120">Connecteurs Graph par Microsoft</span><span class="sxs-lookup"><span data-stu-id="21ae2-120">Graph connectors by Microsoft</span></span>

<span data-ttu-id="21ae2-121">Vous pouvez vous connecter aux sources de données suivantes à l’aide des connecteurs Graph créés par Microsoft :</span><span class="sxs-lookup"><span data-stu-id="21ae2-121">You can connect to the following data sources using Graph connectors created by Microsoft:</span></span>

<!---Need to add a few links below when docs exist--->
* [<span data-ttu-id="21ae2-122">Azure Data Lake Storage Gen2</span><span class="sxs-lookup"><span data-stu-id="21ae2-122">Azure Data Lake Storage Gen2</span></span>](azure-data-lake-connector.md)
* [<span data-ttu-id="21ae2-123">Azure DevOps</span><span class="sxs-lookup"><span data-stu-id="21ae2-123">Azure DevOps</span></span>](azure-devops-connector.md)
* <span data-ttu-id="21ae2-124">Azure SQL</span><span class="sxs-lookup"><span data-stu-id="21ae2-124">Azure SQL</span></span>
* [<span data-ttu-id="21ae2-125">Sites web d’entreprise</span><span class="sxs-lookup"><span data-stu-id="21ae2-125">Enterprise websites</span></span>](enterprise-web-connector.md)
* [<span data-ttu-id="21ae2-126">MediaWiki</span><span class="sxs-lookup"><span data-stu-id="21ae2-126">MediaWiki</span></span>](mediawiki-connector.md)
* [<span data-ttu-id="21ae2-127">Microsoft SQL Server</span><span class="sxs-lookup"><span data-stu-id="21ae2-127">Microsoft SQL Server</span></span>](MSSQL-connector.md)
* [<span data-ttu-id="21ae2-128">Partage de fichiers</span><span class="sxs-lookup"><span data-stu-id="21ae2-128">File share</span></span>](fileshare-connector.md)
* <span data-ttu-id="21ae2-129">Oracle (aperçu)</span><span class="sxs-lookup"><span data-stu-id="21ae2-129">Oracle (preview)</span></span>
* [<span data-ttu-id="21ae2-130">Salesforce (aperçu)</span><span class="sxs-lookup"><span data-stu-id="21ae2-130">Salesforce (preview)</span></span>](salesforce-connector.md)
* [<span data-ttu-id="21ae2-131">ServiceNow</span><span class="sxs-lookup"><span data-stu-id="21ae2-131">ServiceNow</span></span>](servicenow-connector.md)

<span data-ttu-id="21ae2-132">La [Galerie de connecteurs Graph](connectors-gallery.md) contient une brève description de chacun de ces connecteurs Graph.</span><span class="sxs-lookup"><span data-stu-id="21ae2-132">The [Graph connectors gallery](connectors-gallery.md) contains a brief description of each of these Graph connectors.</span></span> <span data-ttu-id="21ae2-133">Si vous êtes prêt à connecter l’une de ces sources de données à votre client, lisez la présentation de l' [installation](configure-connector.md) et les autres Articles de la section Connecteurs d’installation de Microsoft qui s’appliquent à votre source de données.</span><span class="sxs-lookup"><span data-stu-id="21ae2-133">If you are ready to connect one of these data sources to your tenant, be sure to read the [Setup overview](configure-connector.md) and any other articles in the Setup connectors by Microsoft section that apply to your data source.</span></span>

### <a name="graph-connectors-by-our-partners"></a><span data-ttu-id="21ae2-134">Connecteurs Graph par nos partenaires</span><span class="sxs-lookup"><span data-stu-id="21ae2-134">Graph connectors by our partners</span></span>

<span data-ttu-id="21ae2-135">La [Galerie de connecteurs Microsoft Graph](connectors-gallery.md) contient une brève description de chacun des connecteurs graphiques créés par nos partenaires, ainsi qu’un lien vers le site Web de chaque partenaire.</span><span class="sxs-lookup"><span data-stu-id="21ae2-135">The [Microsoft Graph connectors gallery](connectors-gallery.md) includes a brief descriptions of each of the Graph connectors created by our partners and a link to each partner's website.</span></span> <span data-ttu-id="21ae2-136">Pour en savoir plus, contactez chaque partenaire directement.</span><span class="sxs-lookup"><span data-stu-id="21ae2-136">Contact each partner directly to learn more.</span></span>

### <a name="build-your-own-graph-connector"></a><span data-ttu-id="21ae2-137">Création de votre propre connecteur Graph</span><span class="sxs-lookup"><span data-stu-id="21ae2-137">Build your own Graph connector</span></span>

<span data-ttu-id="21ae2-138">Si vous envisagez de créer votre propre connecteur Graph, reportez-vous à la rubrique [vue d’ensemble de l’API Microsoft Search dans Microsoft Graph](https://docs.microsoft.com/graph/search-concept-overview) pour plus d’informations.</span><span class="sxs-lookup"><span data-stu-id="21ae2-138">If you plan to build your own Graph connector, see the [Overview of the Microsoft Search API in Microsoft Graph](https://docs.microsoft.com/graph/search-concept-overview) for more information.</span></span>

## <a name="how-do-i-manage-my-connections"></a><span data-ttu-id="21ae2-139">Comment puis-je gérer mes connexions ?</span><span class="sxs-lookup"><span data-stu-id="21ae2-139">How do I manage my connections?</span></span>

<span data-ttu-id="21ae2-140">Vous pouvez gérer vos connexions à partir de l' [onglet Connecteurs](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/Connectors) dans le [Centre d’administration Microsoft 365](https://admin.microsoft.com/).</span><span class="sxs-lookup"><span data-stu-id="21ae2-140">You can manage your connections from the [Connectors tab](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/Connectors) in the [Microsoft 365 admin center](https://admin.microsoft.com/).</span></span> <span data-ttu-id="21ae2-141">Pour plus d’informations, consultez [la rubrique Manage Your connections](manage-connector.md) .</span><span class="sxs-lookup"><span data-stu-id="21ae2-141">See [Manage your connections](manage-connector.md) for more information.</span></span>

## <a name="what-are-the-license-requirements-and-terms-of-use-for-graph-connectors"></a><span data-ttu-id="21ae2-142">Quelles sont la licence requise et les conditions d’utilisation des connecteurs Graph ?</span><span class="sxs-lookup"><span data-stu-id="21ae2-142">What are the license requirements and terms of use for Graph connectors?</span></span>

<span data-ttu-id="21ae2-143">Pour les utilisateurs de votre organisation, vous avez besoin d’une licence Microsoft 365 ou Office 365 valide et d’un quota de connecteurs graphiques suffisant pour afficher les données des connecteurs dans les résultats de la recherche.</span><span class="sxs-lookup"><span data-stu-id="21ae2-143">You need a valid Microsoft 365 or Office 365 license and sufficient Graph Connectors quota for users in your organization to view data from connectors in their search results.</span></span>

<span data-ttu-id="21ae2-144">Pour en savoir plus, consultez la rubrique [licences requises et tarifs](licensing.md) et [conditions d’utilisation](terms-of-use.md).</span><span class="sxs-lookup"><span data-stu-id="21ae2-144">To learn more, see [License requirements and pricing](licensing.md) and [Terms of use](terms-of-use.md).</span></span>

## <a name="how-do-i-customize-and-configure-search-results"></a><span data-ttu-id="21ae2-145">Comment puis-je personnaliser et configurer les résultats de la recherche ?</span><span class="sxs-lookup"><span data-stu-id="21ae2-145">How do I customize and configure search results?</span></span>

<span data-ttu-id="21ae2-146">Il existe plusieurs façons de personnaliser et de configurer les résultats de la recherche.</span><span class="sxs-lookup"><span data-stu-id="21ae2-146">There are a number of ways to customize and configure search results.</span></span> <span data-ttu-id="21ae2-147">Pour en savoir plus, consultez les articles suivants :</span><span class="sxs-lookup"><span data-stu-id="21ae2-147">See the following articles to learn more:</span></span>

* [<span data-ttu-id="21ae2-148">Gérer des secteurs verticaux et des types de résultats</span><span class="sxs-lookup"><span data-stu-id="21ae2-148">Manage verticals and result types</span></span>](customize-search-page.md)
* [<span data-ttu-id="21ae2-149">Gérer les dispositions des résultats de la recherche</span><span class="sxs-lookup"><span data-stu-id="21ae2-149">Manage search result layouts</span></span>](customize-results-layout.md)
* [<span data-ttu-id="21ae2-150">Gérer le cluster de résultats</span><span class="sxs-lookup"><span data-stu-id="21ae2-150">Manage result cluster</span></span>](result-cluster.md)
* [<span data-ttu-id="21ae2-151">Gérer les filtres personnalisés</span><span class="sxs-lookup"><span data-stu-id="21ae2-151">Manage custom filters</span></span>](custom-filters.md)

## <a name="how-do-i-search-my-connector-data-from-a-custom-application"></a><span data-ttu-id="21ae2-152">Comment rechercher les données de mon connecteur à partir d’une application personnalisée ?</span><span class="sxs-lookup"><span data-stu-id="21ae2-152">How do I search my connector data from a custom application?</span></span>

<span data-ttu-id="21ae2-153">Une fois que les données personnalisées sont indexées, les développeurs peuvent [interroger ces données](https://docs.microsoft.com/graph/search-concept-custom-types).</span><span class="sxs-lookup"><span data-stu-id="21ae2-153">After custom data is indexed, developers can [query this data](https://docs.microsoft.com/graph/search-concept-custom-types).</span></span> <span data-ttu-id="21ae2-154">Vous pouvez afficher vos données dans n’importe quelle application.</span><span class="sxs-lookup"><span data-stu-id="21ae2-154">You can view your data in any application.</span></span> <span data-ttu-id="21ae2-155">Pour plus d’informations, reportez-vous à la rubrique [vue d’ensemble de l’API Microsoft Search dans Microsoft Graph](https://docs.microsoft.com/graph/search-concept-overview).</span><span class="sxs-lookup"><span data-stu-id="21ae2-155">For more information, see the [Overview of the Microsoft Search API in Microsoft Graph](https://docs.microsoft.com/graph/search-concept-overview).</span></span>
