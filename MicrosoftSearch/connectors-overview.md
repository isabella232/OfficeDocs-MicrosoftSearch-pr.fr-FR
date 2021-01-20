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
# <a name="overview-of-microsoft-graph-connectors"></a><span data-ttu-id="3bf20-103">Vue d’ensemble des connecteurs Microsoft Graph</span><span class="sxs-lookup"><span data-stu-id="3bf20-103">Overview of Microsoft Graph connectors</span></span>

<span data-ttu-id="3bf20-104">[Microsoft Search](https://docs.microsoft.com/microsoftsearch/overview-microsoft-search) indexe toutes vos [données Microsoft 365](https://www.microsoft.com/microsoft-365) pour les rendre accessibles aux utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="3bf20-104">[Microsoft Search](https://docs.microsoft.com/microsoftsearch/overview-microsoft-search) indexes all your [Microsoft 365](https://www.microsoft.com/microsoft-365) data to make it searchable for users.</span></span> <span data-ttu-id="3bf20-105">Avec les connecteurs Microsoft Graph, votre organisation peut indexer des données tierces afin qu’elles apparaissent dans les résultats de recherche Microsoft.</span><span class="sxs-lookup"><span data-stu-id="3bf20-105">With Microsoft Graph connectors, your organization can index third-party data so it appears in Microsoft Search results.</span></span> <span data-ttu-id="3bf20-106">Cela étend les types de sources de contenu utilisables dans vos applications de productivité Microsoft 365 et dans l’écosystème Microsoft plus large.</span><span class="sxs-lookup"><span data-stu-id="3bf20-106">This expands the types of content sources that are searchable in your Microsoft 365 productivity apps and the broader Microsoft ecosystem.</span></span> <span data-ttu-id="3bf20-107">Les données tierces peuvent être hébergées en local ou dans les clouds publics ou privés.</span><span class="sxs-lookup"><span data-stu-id="3bf20-107">The third-party data can be hosted on-premises or in the public or private clouds.</span></span>

<!---link Microsoft Graph reference in line 19 when we have access to relevant documentation--->

<span data-ttu-id="3bf20-108">Le reste de cet article est destiné à aider les administrateurs Microsoft 365 à trouver les ressources disponibles pour répondre aux questions suivantes :</span><span class="sxs-lookup"><span data-stu-id="3bf20-108">The rest of this article is intended to help Microsoft 365 administrators locate the resources that are available to answer the following questions:</span></span>

* [<span data-ttu-id="3bf20-109">Quelles sources de données peuvent être connectées à Microsoft Search (recherche Microsoft) ?</span><span class="sxs-lookup"><span data-stu-id="3bf20-109">What data sources can be connected to Microsoft Search?</span></span>](#what-data-sources-can-be-connected-to-microsoft-search)
* [<span data-ttu-id="3bf20-110">Comment gérer mes connexions ?</span><span class="sxs-lookup"><span data-stu-id="3bf20-110">How do I manage my connections?</span></span>](#how-do-i-manage-my-connections)
* [<span data-ttu-id="3bf20-111">Quelles sont les conditions d’utilisation et les conditions d’utilisation des licences pour les connecteurs Graph ?</span><span class="sxs-lookup"><span data-stu-id="3bf20-111">What are the license requirements and terms of use for Graph connectors?</span></span>](#what-are-the-license-requirements-and-terms-of-use-for-graph-connectors)
* [<span data-ttu-id="3bf20-112">Quelles sont les fonctionnalités d’aperçu ?</span><span class="sxs-lookup"><span data-stu-id="3bf20-112">What are the preview features?</span></span>](#what-are-the-preview-features)
* [<span data-ttu-id="3bf20-113">Comment personnaliser et configurer les résultats de la recherche ?</span><span class="sxs-lookup"><span data-stu-id="3bf20-113">How do I customize and configure search results?</span></span>](#how-do-i-customize-and-configure-search-results)
* [<span data-ttu-id="3bf20-114">Comment effectuer une recherche dans les données de mon connecteur à partir d’une application personnalisée ?</span><span class="sxs-lookup"><span data-stu-id="3bf20-114">How do I search my connector data from a custom application?</span></span>](#how-do-i-search-my-connector-data-from-a-custom-application)

<!---Modify to another note that is more accurate after rollout completion--->
> [!IMPORTANT]
> <span data-ttu-id="3bf20-115">Les connecteurs Microsoft Graph et les API de recherche Microsoft sont désormais généralement disponibles.</span><span class="sxs-lookup"><span data-stu-id="3bf20-115">Microsoft Graph connectors and Microsoft Search APIs are now generally available.</span></span> <span data-ttu-id="3bf20-116">Le premier déploiement est prévu pour durer jusqu’en février 2021.</span><span class="sxs-lookup"><span data-stu-id="3bf20-116">The first rollout is scheduled to last until February 2021.</span></span> <span data-ttu-id="3bf20-117">En attendant, seuls les clients et [](https://docs.microsoft.com/office365/admin/manage/release-options-in-office-365?view=o365-worldwide&preserve-view=true) les utilisateurs qui ont choisi la version ciblée pourront utiliser les connecteurs Graph.</span><span class="sxs-lookup"><span data-stu-id="3bf20-117">Until then, only tenants and users who have opted into [Targeted release](https://docs.microsoft.com/office365/admin/manage/release-options-in-office-365?view=o365-worldwide&preserve-view=true) will be able to use Graph connectors.</span></span> <span data-ttu-id="3bf20-118">Une fois le déploiement terminé pour tous les clients, l’utilisation du quota d’index à partir du contenu des connecteurs est soumise à facturation.</span><span class="sxs-lookup"><span data-stu-id="3bf20-118">Upon rollout completion to all tenants, index quota utilization from connectors content will become subject to billing.</span></span> <span data-ttu-id="3bf20-119">Pour plus [d’informations, voir Exigences](licensing.md) et tarifs en matière de licences.</span><span class="sxs-lookup"><span data-stu-id="3bf20-119">See [Licensing requirements and pricing](licensing.md) for more information.</span></span>

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

## <a name="what-data-sources-can-be-connected-to-microsoft-search"></a><span data-ttu-id="3bf20-120">Quelles sources de données peuvent être connectées à Microsoft Search (recherche Microsoft) ?</span><span class="sxs-lookup"><span data-stu-id="3bf20-120">What data sources can be connected to Microsoft Search?</span></span>

<span data-ttu-id="3bf20-121">Microsoft fournit dix connecteurs Graph et nos partenaires de l’écosystème ont créé plus de 100 connecteurs Graph supplémentaires.</span><span class="sxs-lookup"><span data-stu-id="3bf20-121">Microsoft provides ten Graph connectors and our ecosystem partners have created over 100 additional Graph connectors.</span></span> <span data-ttu-id="3bf20-122">Vous pouvez également créer votre propre connecteur Graph.</span><span class="sxs-lookup"><span data-stu-id="3bf20-122">You can also build your own Graph connector.</span></span> 

### <a name="graph-connectors-by-microsoft"></a><span data-ttu-id="3bf20-123">Connecteurs Graph par Microsoft</span><span class="sxs-lookup"><span data-stu-id="3bf20-123">Graph connectors by Microsoft</span></span>

<span data-ttu-id="3bf20-124">Vous pouvez vous connecter aux sources de données suivantes à l’aide de connecteurs Graph créés par Microsoft :</span><span class="sxs-lookup"><span data-stu-id="3bf20-124">You can connect to the following data sources using Graph connectors created by Microsoft:</span></span>

<!---Need to add a few links below when docs exist--->
* [<span data-ttu-id="3bf20-125">Azure Data Lake Storage Gen2</span><span class="sxs-lookup"><span data-stu-id="3bf20-125">Azure Data Lake Storage Gen2</span></span>](azure-data-lake-connector.md)
* [<span data-ttu-id="3bf20-126">Azure DevOps</span><span class="sxs-lookup"><span data-stu-id="3bf20-126">Azure DevOps</span></span>](azure-devops-connector.md)
* <span data-ttu-id="3bf20-127">Azure SQL</span><span class="sxs-lookup"><span data-stu-id="3bf20-127">Azure SQL</span></span>
* [<span data-ttu-id="3bf20-128">Sites web d’entreprise</span><span class="sxs-lookup"><span data-stu-id="3bf20-128">Enterprise websites</span></span>](enterprise-web-connector.md)
* [<span data-ttu-id="3bf20-129">MediaWiki</span><span class="sxs-lookup"><span data-stu-id="3bf20-129">MediaWiki</span></span>](mediawiki-connector.md)
* [<span data-ttu-id="3bf20-130">Microsoft SQL Server</span><span class="sxs-lookup"><span data-stu-id="3bf20-130">Microsoft SQL Server</span></span>](MSSQL-connector.md)
* [<span data-ttu-id="3bf20-131">Partage de fichiers</span><span class="sxs-lookup"><span data-stu-id="3bf20-131">File share</span></span>](fileshare-connector.md)
* <span data-ttu-id="3bf20-132">Oracle (prévisualisation)</span><span class="sxs-lookup"><span data-stu-id="3bf20-132">Oracle (preview)</span></span>
* [<span data-ttu-id="3bf20-133">Salesforce (préversion)</span><span class="sxs-lookup"><span data-stu-id="3bf20-133">Salesforce (preview)</span></span>](salesforce-connector.md)
* [<span data-ttu-id="3bf20-134">ServiceNow</span><span class="sxs-lookup"><span data-stu-id="3bf20-134">ServiceNow</span></span>](servicenow-connector.md)

<span data-ttu-id="3bf20-135">La [galerie de connecteurs Graph](connectors-gallery.md) contient une brève description de chacun de ces connecteurs Graph.</span><span class="sxs-lookup"><span data-stu-id="3bf20-135">The [Graph connectors gallery](connectors-gallery.md) contains a brief description of each of these Graph connectors.</span></span> <span data-ttu-id="3bf20-136">Si vous êtes prêt à connecter l’une de ces [](configure-connector.md) sources de données à votre client, n’oubliez pas de lire la vue d’ensemble du programme d’installation et les autres articles de la section Connecteurs d’installation par Microsoft qui s’appliquent à votre source de données.</span><span class="sxs-lookup"><span data-stu-id="3bf20-136">If you are ready to connect one of these data sources to your tenant, be sure to read the [Setup overview](configure-connector.md) and any other articles in the Setup connectors by Microsoft section that apply to your data source.</span></span>

### <a name="graph-connectors-by-our-partners"></a><span data-ttu-id="3bf20-137">Connecteurs graph par nos partenaires</span><span class="sxs-lookup"><span data-stu-id="3bf20-137">Graph connectors by our partners</span></span>

<span data-ttu-id="3bf20-138">La [galerie de connecteurs Microsoft Graph](connectors-gallery.md) comprend une brève description de chacun des connecteurs Graph créés par nos partenaires et un lien vers le site web de chaque partenaire.</span><span class="sxs-lookup"><span data-stu-id="3bf20-138">The [Microsoft Graph connectors gallery](connectors-gallery.md) includes a brief descriptions of each of the Graph connectors created by our partners and a link to each partner's website.</span></span> <span data-ttu-id="3bf20-139">Contactez directement chaque partenaire pour en savoir plus.</span><span class="sxs-lookup"><span data-stu-id="3bf20-139">Contact each partner directly to learn more.</span></span>

### <a name="build-your-own-graph-connector"></a><span data-ttu-id="3bf20-140">Créer votre propre connecteur Graph</span><span class="sxs-lookup"><span data-stu-id="3bf20-140">Build your own Graph connector</span></span>

<span data-ttu-id="3bf20-141">Si vous envisagez de créer votre propre connecteur Graph, consultez la vue d’ensemble de [l’API recherche Microsoft dans Microsoft Graph](https://docs.microsoft.com/graph/search-concept-overview) pour plus d’informations.</span><span class="sxs-lookup"><span data-stu-id="3bf20-141">If you plan to build your own Graph connector, see the [Overview of the Microsoft Search API in Microsoft Graph](https://docs.microsoft.com/graph/search-concept-overview) for more information.</span></span>

## <a name="how-do-i-manage-my-connections"></a><span data-ttu-id="3bf20-142">Comment gérer mes connexions ?</span><span class="sxs-lookup"><span data-stu-id="3bf20-142">How do I manage my connections?</span></span>

<span data-ttu-id="3bf20-143">Vous pouvez gérer vos connexions à partir de [l’onglet Connecteurs](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/Connectors) dans le Centre d’administration [Microsoft 365.](https://admin.microsoft.com/)</span><span class="sxs-lookup"><span data-stu-id="3bf20-143">You can manage your connections from the [Connectors tab](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/Connectors) in the [Microsoft 365 admin center](https://admin.microsoft.com/).</span></span> <span data-ttu-id="3bf20-144">Pour [plus d’informations, voir](manage-connector.md) Gérer vos connexions.</span><span class="sxs-lookup"><span data-stu-id="3bf20-144">See [Manage your connections](manage-connector.md) for more information.</span></span>

## <a name="what-are-the-license-requirements-and-terms-of-use-for-graph-connectors"></a><span data-ttu-id="3bf20-145">Quelles sont les conditions d’utilisation et les conditions d’utilisation des licences pour les connecteurs Graph ?</span><span class="sxs-lookup"><span data-stu-id="3bf20-145">What are the license requirements and terms of use for Graph connectors?</span></span>

<span data-ttu-id="3bf20-146">Vous avez besoin d’une licence Microsoft 365 ou Office 365 valide et d’un quota de connecteurs Graph suffisant pour que les utilisateurs de votre organisation visualisent les données des connecteurs dans leurs résultats de recherche.</span><span class="sxs-lookup"><span data-stu-id="3bf20-146">You need a valid Microsoft 365 or Office 365 license and sufficient Graph Connectors quota for users in your organization to view data from connectors in their search results.</span></span>

<span data-ttu-id="3bf20-147">Pour plus d’informations, voir [Conditions d’utilisation](licensing.md) et conditions [d’utilisation des licences.](terms-of-use.md)</span><span class="sxs-lookup"><span data-stu-id="3bf20-147">To learn more, see [License requirements and pricing](licensing.md) and [Terms of use](terms-of-use.md).</span></span>

## <a name="what-are-the-preview-features"></a><span data-ttu-id="3bf20-148">Quelles sont les fonctionnalités d’aperçu ?</span><span class="sxs-lookup"><span data-stu-id="3bf20-148">What are the preview features?</span></span>

<span data-ttu-id="3bf20-149">Bien que les connecteurs Microsoft Graph et les API de recherche Microsoft soient désormais généralement disponibles, plusieurs fonctionnalités sont en prévisualisation.</span><span class="sxs-lookup"><span data-stu-id="3bf20-149">Although Microsoft Graph connectors and Microsoft Search APIs are now generally available, there are several features that are in preview.</span></span>

<span data-ttu-id="3bf20-150">L’ensemble des connecteurs et des fonctionnalités de la prévisualisation comprend les éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="3bf20-150">The set of connectors and features in preview include:</span></span>

* [<span data-ttu-id="3bf20-151">Connecteur Azure DevOps</span><span class="sxs-lookup"><span data-stu-id="3bf20-151">Azure DevOps connector</span></span>](azure-devops-connector.md)
* [<span data-ttu-id="3bf20-152">Connecteur Salesforce</span><span class="sxs-lookup"><span data-stu-id="3bf20-152">Salesforce connector</span></span>](salesforce-connector.md)
* <span data-ttu-id="3bf20-153">[Connecteur ServiceNow avec](servicenow-connector.md) autorisations de recherche qui utilisent des ACA sources</span><span class="sxs-lookup"><span data-stu-id="3bf20-153">[ServiceNow connector](servicenow-connector.md) with search permissions that use source ACLs</span></span>
* [<span data-ttu-id="3bf20-154">Gérer le cluster de résultat</span><span class="sxs-lookup"><span data-stu-id="3bf20-154">Manage result cluster</span></span>](result-cluster.md)

## <a name="how-do-i-customize-and-configure-search-results"></a><span data-ttu-id="3bf20-155">Comment personnaliser et configurer les résultats de la recherche ?</span><span class="sxs-lookup"><span data-stu-id="3bf20-155">How do I customize and configure search results?</span></span>

<span data-ttu-id="3bf20-156">Il existe plusieurs façons de personnaliser et de configurer les résultats de la recherche.</span><span class="sxs-lookup"><span data-stu-id="3bf20-156">There are a number of ways to customize and configure search results.</span></span> <span data-ttu-id="3bf20-157">Pour en savoir plus, consultez les articles suivants :</span><span class="sxs-lookup"><span data-stu-id="3bf20-157">See the following articles to learn more:</span></span>

* [<span data-ttu-id="3bf20-158">Gérer des secteurs verticaux et des types de résultats</span><span class="sxs-lookup"><span data-stu-id="3bf20-158">Manage verticals and result types</span></span>](customize-search-page.md)
* [<span data-ttu-id="3bf20-159">Gérer les dispositions des résultats de la recherche</span><span class="sxs-lookup"><span data-stu-id="3bf20-159">Manage search result layouts</span></span>](customize-results-layout.md)
* [<span data-ttu-id="3bf20-160">Gérer le cluster de résultat</span><span class="sxs-lookup"><span data-stu-id="3bf20-160">Manage result cluster</span></span>](result-cluster.md)
* [<span data-ttu-id="3bf20-161">Gérer les filtres personnalisés</span><span class="sxs-lookup"><span data-stu-id="3bf20-161">Manage custom filters</span></span>](custom-filters.md)

## <a name="how-do-i-search-my-connector-data-from-a-custom-application"></a><span data-ttu-id="3bf20-162">Comment effectuer une recherche dans les données de mon connecteur à partir d’une application personnalisée ?</span><span class="sxs-lookup"><span data-stu-id="3bf20-162">How do I search my connector data from a custom application?</span></span>

<span data-ttu-id="3bf20-163">Une fois les données personnalisées indexées, les développeurs peuvent [interroger ces données.](https://docs.microsoft.com/graph/search-concept-custom-types)</span><span class="sxs-lookup"><span data-stu-id="3bf20-163">After custom data is indexed, developers can [query this data](https://docs.microsoft.com/graph/search-concept-custom-types).</span></span> <span data-ttu-id="3bf20-164">Vous pouvez afficher vos données dans n’importe quelle application.</span><span class="sxs-lookup"><span data-stu-id="3bf20-164">You can view your data in any application.</span></span> <span data-ttu-id="3bf20-165">Pour plus d’informations, voir la [vue d’ensemble de l’API recherche Microsoft dans Microsoft Graph](https://docs.microsoft.com/graph/search-concept-overview).</span><span class="sxs-lookup"><span data-stu-id="3bf20-165">For more information, see the [Overview of the Microsoft Search API in Microsoft Graph](https://docs.microsoft.com/graph/search-concept-overview).</span></span>

## <a name="limitations"></a><span data-ttu-id="3bf20-166">Limites</span><span class="sxs-lookup"><span data-stu-id="3bf20-166">Limitations</span></span>

* <span data-ttu-id="3bf20-167">Lorsque vous **publiez** un connecteur microsoft, la création de la connexion peut prendre quelques minutes.</span><span class="sxs-lookup"><span data-stu-id="3bf20-167">When you **publish** a Microsoft-built connector, it might take a few minutes for the connection to be created.</span></span> <span data-ttu-id="3bf20-168">Pendant ce temps, la connexion affiche son état en attente.</span><span class="sxs-lookup"><span data-stu-id="3bf20-168">During that time, the connection will show its status as pending.</span></span>

* <span data-ttu-id="3bf20-169">Le [Centre d’administration Microsoft 365](https://admin.microsoft.com) ne prend pas en charge la modification du schéma de recherche après la publication d’une connexion. </span><span class="sxs-lookup"><span data-stu-id="3bf20-169">The [Microsoft 365 admin center](https://admin.microsoft.com) doesn't support editing the **search schema** after a connection is published.</span></span> <span data-ttu-id="3bf20-170">Pour modifier le schéma de recherche, supprimez votre connexion, puis créez-en une nouvelle.</span><span class="sxs-lookup"><span data-stu-id="3bf20-170">To edit the search schema, delete your connection and then create a new one.</span></span>

* <span data-ttu-id="3bf20-171">Le débit d’ingestion est limitée à environ quatre éléments par seconde.</span><span class="sxs-lookup"><span data-stu-id="3bf20-171">Ingestion throughput is throttled at about four items per second.</span></span>

* <span data-ttu-id="3bf20-172">Il n’existe aucune prise en charge des mises à jour de schéma.</span><span class="sxs-lookup"><span data-stu-id="3bf20-172">There is no support for schema updates.</span></span> <span data-ttu-id="3bf20-173">Après avoir créé une configuration de connexion, il n’existe aucun moyen de mettre à jour le schéma.</span><span class="sxs-lookup"><span data-stu-id="3bf20-173">After you create a connection setup, there's no way to update the schema.</span></span> <span data-ttu-id="3bf20-174">Vous pouvez uniquement supprimer et re-créer la connexion.</span><span class="sxs-lookup"><span data-stu-id="3bf20-174">You can only delete and re-create the connection.</span></span>

* <span data-ttu-id="3bf20-175">Il existe une limite de connexions.</span><span class="sxs-lookup"><span data-stu-id="3bf20-175">There is a connections limit.</span></span> <span data-ttu-id="3bf20-176">Chaque client peut créer jusqu’à 10 connexions.</span><span class="sxs-lookup"><span data-stu-id="3bf20-176">Each tenant can create up to 10 connections.</span></span>

* <span data-ttu-id="3bf20-177">La prise en charge de la modification de la connexion n’est pas disponible.</span><span class="sxs-lookup"><span data-stu-id="3bf20-177">Edit support for connection is not available.</span></span> <span data-ttu-id="3bf20-178">Une fois la connexion créée, vous ne pouvez pas la modifier.</span><span class="sxs-lookup"><span data-stu-id="3bf20-178">Once the connection has been created, you cannot edit or change it.</span></span> <span data-ttu-id="3bf20-179">Si vous devez modifier des détails, vous devez supprimer et recréer la connexion.</span><span class="sxs-lookup"><span data-stu-id="3bf20-179">If you need to change any details, you must delete and recreate the connection.</span></span>
