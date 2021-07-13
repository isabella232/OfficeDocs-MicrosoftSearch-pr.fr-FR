---
title: Présentation des connecteurs Graph Microsoft
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
description: Vue d’ensemble des connecteurs Graph Microsoft pour Recherche Microsoft
ms.openlocfilehash: 87645e32e274eb166d6ba008c4ac720667105a1f
ms.sourcegitcommit: 52129e0129a201ec056903b2461d012fda6d3636
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/12/2021
ms.locfileid: "53383482"
---
<!---Previous ms.author: monaray --->

# <a name="overview-of-microsoft-graph-connectors"></a><span data-ttu-id="b885e-103">Vue d’ensemble des connecteurs Microsoft Graph</span><span class="sxs-lookup"><span data-stu-id="b885e-103">Overview of Microsoft Graph connectors</span></span>

<span data-ttu-id="b885e-104">[Recherche Microsoft](./overview-microsoft-search.md) indexe toutes vos [données Microsoft 365](https://www.microsoft.com/microsoft-365) pour les rendre utilisables dans une recherche pour les utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="b885e-104">[Microsoft Search](./overview-microsoft-search.md) indexes all your [Microsoft 365](https://www.microsoft.com/microsoft-365) data to make it searchable for users.</span></span> <span data-ttu-id="b885e-105">Avec les connecteurs Graph Microsoft, votre organisation peut indexer des données tierces afin qu’elles apparaissent dans Recherche Microsoft résultats.</span><span class="sxs-lookup"><span data-stu-id="b885e-105">With Microsoft Graph connectors, your organization can index third-party data so it appears in Microsoft Search results.</span></span> <span data-ttu-id="b885e-106">Cette fonctionnalité élargit les types de sources de contenu disponibles dans vos applications de productivité Microsoft 365 et dans l’écosystème Microsoft plus vaste.</span><span class="sxs-lookup"><span data-stu-id="b885e-106">This feature expands the types of content sources that are searchable in your Microsoft 365 productivity apps and the broader Microsoft ecosystem.</span></span> <span data-ttu-id="b885e-107">Les données tierces peuvent être hébergées en local ou dans les clouds publics ou privés.</span><span class="sxs-lookup"><span data-stu-id="b885e-107">The third-party data can be hosted on-premises or in the public or private clouds.</span></span>

<!---link Microsoft Graph reference in line 19 when we have access to relevant documentation--->

<span data-ttu-id="b885e-108">Cet article est destiné à aider les administrateurs Microsoft 365 trouver les ressources disponibles pour répondre aux questions suivantes :</span><span class="sxs-lookup"><span data-stu-id="b885e-108">This article is intended to help Microsoft 365 administrators locate the resources that are available to answer the following questions:</span></span>

* [<span data-ttu-id="b885e-109">Quelles sources de données peuvent être connectées à Recherche Microsoft ?</span><span class="sxs-lookup"><span data-stu-id="b885e-109">What data sources can be connected to Microsoft Search?</span></span>](#what-data-sources-can-be-connected-to-microsoft-search)
* [<span data-ttu-id="b885e-110">Comment gérer mes connexions ?</span><span class="sxs-lookup"><span data-stu-id="b885e-110">How do I manage my connections?</span></span>](#how-do-i-manage-my-connections)
* [<span data-ttu-id="b885e-111">Quelles sont les conditions d’utilisation et les conditions d’utilisation des licences pour les connecteurs Graph Microsoft ?</span><span class="sxs-lookup"><span data-stu-id="b885e-111">What are the license requirements and terms of use for Microsoft Graph connectors?</span></span>](#what-are-the-license-requirements-and-terms-of-use-for-connectors)
* [<span data-ttu-id="b885e-112">Quelles sont les fonctionnalités d’aperçu ?</span><span class="sxs-lookup"><span data-stu-id="b885e-112">What are the preview features?</span></span>](#what-are-the-preview-features)
* [<span data-ttu-id="b885e-113">Comment personnaliser et configurer les résultats de la recherche ?</span><span class="sxs-lookup"><span data-stu-id="b885e-113">How do I customize and configure search results?</span></span>](#how-do-i-customize-and-configure-search-results)
* [<span data-ttu-id="b885e-114">Comment effectuer une recherche dans les données de mon connecteur à partir d’une application personnalisée ?</span><span class="sxs-lookup"><span data-stu-id="b885e-114">How do I search my connector data from a custom application?</span></span>](#how-do-i-search-my-connector-data-from-a-custom-application)
* [<span data-ttu-id="b885e-115">Comment personnaliser les résultats de recherche ?</span><span class="sxs-lookup"><span data-stu-id="b885e-115">How do I customize search results?</span></span>](#how-do-i-customize-search-results)
* [<span data-ttu-id="b885e-116">Quelles sont les limitations du connecteur ?</span><span class="sxs-lookup"><span data-stu-id="b885e-116">What are the connector limitations</span></span>](#what-are-the-connector-limitations)

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

## <a name="what-data-sources-can-be-connected-to-microsoft-search"></a><span data-ttu-id="b885e-117">Quelles sources de données peuvent être connectées à Recherche Microsoft ?</span><span class="sxs-lookup"><span data-stu-id="b885e-117">What data sources can be connected to Microsoft Search?</span></span>

<span data-ttu-id="b885e-118">Microsoft fournit 9 connecteurs et nos partenaires de l’écosystème ont créé plus de 100 connecteurs.</span><span class="sxs-lookup"><span data-stu-id="b885e-118">Microsoft provides 9 connectors and our ecosystem partners have created over 100 more connectors.</span></span> <span data-ttu-id="b885e-119">Vous pouvez également créer votre propre connecteur.</span><span class="sxs-lookup"><span data-stu-id="b885e-119">You can also build your own connector.</span></span>

### <a name="microsoft-graph-connectors-by-microsoft"></a><span data-ttu-id="b885e-120">Connecteurs Graph Microsoft par Microsoft</span><span class="sxs-lookup"><span data-stu-id="b885e-120">Microsoft Graph connectors by Microsoft</span></span>

<span data-ttu-id="b885e-121">Vous pouvez vous connecter aux sources de données suivantes à l’aide de connecteurs créés par Microsoft :</span><span class="sxs-lookup"><span data-stu-id="b885e-121">You can connect to the following data sources using connectors created by Microsoft:</span></span>

<!---Add links below when new docs are created--->
* [<span data-ttu-id="b885e-122">Azure Data Lake Storage Gen2</span><span class="sxs-lookup"><span data-stu-id="b885e-122">Azure Data Lake Storage Gen2</span></span>](azure-data-lake-connector.md)
* [<span data-ttu-id="b885e-123">Azure DevOps</span><span class="sxs-lookup"><span data-stu-id="b885e-123">Azure DevOps</span></span>](azure-devops-connector.md)
* [<span data-ttu-id="b885e-124">Azure SQL et Microsoft SQL Server</span><span class="sxs-lookup"><span data-stu-id="b885e-124">Azure SQL and Microsoft SQL Server</span></span>](MSSQL-connector.md)
* [<span data-ttu-id="b885e-125">Sites web d’entreprise</span><span class="sxs-lookup"><span data-stu-id="b885e-125">Enterprise websites</span></span>](enterprise-web-connector.md)
* [<span data-ttu-id="b885e-126">MediaWiki</span><span class="sxs-lookup"><span data-stu-id="b885e-126">MediaWiki</span></span>](mediawiki-connector.md)
* [<span data-ttu-id="b885e-127">Partage de fichiers</span><span class="sxs-lookup"><span data-stu-id="b885e-127">File share</span></span>](fileshare-connector.md)
* [<span data-ttu-id="b885e-128">Oracle SQL</span><span class="sxs-lookup"><span data-stu-id="b885e-128">Oracle SQL</span></span>](OracleSQL-connector.md)
* [<span data-ttu-id="b885e-129">Salesforce (préversion)</span><span class="sxs-lookup"><span data-stu-id="b885e-129">Salesforce (preview)</span></span>](salesforce-connector.md)
* [<span data-ttu-id="b885e-130">ServiceNow</span><span class="sxs-lookup"><span data-stu-id="b885e-130">ServiceNow</span></span>](servicenow-connector.md)

<span data-ttu-id="b885e-131">La [galerie de connecteurs Graph](https://www.microsoft.com/microsoft-search/connectors) Microsoft contient une brève description de chacun de ces connecteurs.</span><span class="sxs-lookup"><span data-stu-id="b885e-131">The [Microsoft Graph connectors gallery](https://www.microsoft.com/microsoft-search/connectors) contains a brief description of each of these connectors.</span></span> <span data-ttu-id="b885e-132">Si vous êtes prêt à connecter l’une de ces sources [](configure-connector.md) de données à votre client, n’oubliez pas de lire la vue d’ensemble du programme d’installation et les autres articles de la section Connecteurs d’installation par Microsoft qui s’appliquent à votre source de données.</span><span class="sxs-lookup"><span data-stu-id="b885e-132">If you're ready to connect one of these data sources to your tenant, be sure to read the [Setup overview](configure-connector.md) and any other articles in the Setup connectors by Microsoft section that apply to your data source.</span></span>

### <a name="microsoft-graph-connectors-by-our-partners"></a><span data-ttu-id="b885e-133">Connecteurs Graph Microsoft par nos partenaires</span><span class="sxs-lookup"><span data-stu-id="b885e-133">Microsoft Graph connectors by our partners</span></span>

<span data-ttu-id="b885e-134">La [galerie de connecteurs](https://www.microsoft.com/microsoft-search/connectors) Graph Microsoft inclut une brève description de chacun des connecteurs créés par nos partenaires et un lien vers le site web de chaque partenaire.</span><span class="sxs-lookup"><span data-stu-id="b885e-134">The [Microsoft Graph connectors gallery](https://www.microsoft.com/microsoft-search/connectors) includes a brief description of each of the connectors created by our partners, and a link to each partner's website.</span></span> <span data-ttu-id="b885e-135">Pour en savoir plus, contactez directement chaque partenaire.</span><span class="sxs-lookup"><span data-stu-id="b885e-135">To learn more, contact each partner directly.</span></span>

### <a name="build-your-own-microsoft-graph-connector"></a><span data-ttu-id="b885e-136">Créer votre propre connecteur Microsoft Graph</span><span class="sxs-lookup"><span data-stu-id="b885e-136">Build your own Microsoft Graph connector</span></span>

<span data-ttu-id="b885e-137">Vous pouvez créer votre propre connecteur si vous préférez.</span><span class="sxs-lookup"><span data-stu-id="b885e-137">You can build your own connector if you prefer.</span></span> <span data-ttu-id="b885e-138">Pour plus d’informations sur la création de connecteurs, voir Créer votre premier connecteur [microsoft Graph personnalisé.](/graph/connecting-external-content-build-quickstart)</span><span class="sxs-lookup"><span data-stu-id="b885e-138">For more information on building connectors, see  [Build your first custom Microsoft Graph connector](/graph/connecting-external-content-build-quickstart).</span></span>

## <a name="how-do-i-manage-my-connections"></a><span data-ttu-id="b885e-139">Comment gérer mes connexions ?</span><span class="sxs-lookup"><span data-stu-id="b885e-139">How do I manage my connections?</span></span>

<span data-ttu-id="b885e-140">Vous pouvez gérer vos connexions à partir de [l’onglet Connecteurs](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/Connectors) dans le [Centre d’administration Microsoft 365](https://admin.microsoft.com/).</span><span class="sxs-lookup"><span data-stu-id="b885e-140">You can manage your connections from the [Connectors tab](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/Connectors) in the [Microsoft 365 admin center](https://admin.microsoft.com/).</span></span> <span data-ttu-id="b885e-141">Pour plus d’informations sur la gestion des connexions, voir : [Gérer vos connexions.](manage-connector.md)</span><span class="sxs-lookup"><span data-stu-id="b885e-141">For more information about managing connections, see: [Manage your connections](manage-connector.md).</span></span>

## <a name="what-are-the-license-requirements-and-terms-of-use-for-connectors"></a><span data-ttu-id="b885e-142">Quelles sont les conditions d’utilisation et les conditions d’utilisation des licences pour les connecteurs ?</span><span class="sxs-lookup"><span data-stu-id="b885e-142">What are the license requirements and terms of use for connectors?</span></span>

<span data-ttu-id="b885e-143">Vous avez besoin d’une licence Microsoft 365 ou Office 365 valide et d’un quota de connecteurs suffisant pour que les utilisateurs de votre organisation visualisent les données des connecteurs dans leurs résultats de recherche.</span><span class="sxs-lookup"><span data-stu-id="b885e-143">You need a valid Microsoft 365 or Office 365 license and sufficient connectors quota for users in your organization to view data from connectors in their search results.</span></span>

<span data-ttu-id="b885e-144">Pour plus d’informations, voir [Conditions d’utilisation](licensing.md) et conditions [d’utilisation des licences.](terms-of-use.md)</span><span class="sxs-lookup"><span data-stu-id="b885e-144">To learn more, see [License requirements and pricing](licensing.md) and [Terms of use](terms-of-use.md).</span></span>

## <a name="what-are-the-preview-features"></a><span data-ttu-id="b885e-145">Quelles sont les fonctionnalités d’aperçu ?</span><span class="sxs-lookup"><span data-stu-id="b885e-145">What are the preview features?</span></span>

<span data-ttu-id="b885e-146">Bien que les connecteurs Graph microsoft et Recherche Microsoft API soient désormais généralement disponibles, plusieurs fonctionnalités sont disponibles en prévisualisation.</span><span class="sxs-lookup"><span data-stu-id="b885e-146">Although Microsoft Graph connectors and Microsoft Search APIs are now generally available, there are several features that are in preview.</span></span>

<span data-ttu-id="b885e-147">L’ensemble des connecteurs et des fonctionnalités de la prévisualisation comprend les éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="b885e-147">The set of connectors and features in preview include:</span></span>

* [<span data-ttu-id="b885e-148">Azure DevOps connecteur</span><span class="sxs-lookup"><span data-stu-id="b885e-148">Azure DevOps connector</span></span>](azure-devops-connector.md)
* [<span data-ttu-id="b885e-149">Connecteur Salesforce</span><span class="sxs-lookup"><span data-stu-id="b885e-149">Salesforce connector</span></span>](salesforce-connector.md)
* <span data-ttu-id="b885e-150">[Connecteur ServiceNow avec](servicenow-connector.md) autorisations de recherche qui utilisent des ACA sources</span><span class="sxs-lookup"><span data-stu-id="b885e-150">[ServiceNow connector](servicenow-connector.md) with search permissions that use source ACLs</span></span>
* [<span data-ttu-id="b885e-151">Gérer le cluster de résultat</span><span class="sxs-lookup"><span data-stu-id="b885e-151">Manage result cluster</span></span>](result-cluster.md)
* [<span data-ttu-id="b885e-152">Plusieurs connexions dans un secteur vertical</span><span class="sxs-lookup"><span data-stu-id="b885e-152">Multiple connections in a vertical</span></span>](customize-search-page.md#multiple-connections-in-a-vertical)

## <a name="how-do-i-customize-and-configure-search-results"></a><span data-ttu-id="b885e-153">Comment personnaliser et configurer les résultats de la recherche ?</span><span class="sxs-lookup"><span data-stu-id="b885e-153">How do I customize and configure search results?</span></span>

<span data-ttu-id="b885e-154">Il existe de nombreuses façons de personnaliser et de configurer les résultats de recherche.</span><span class="sxs-lookup"><span data-stu-id="b885e-154">There are many ways to customize and configure search results.</span></span> <span data-ttu-id="b885e-155">Pour en savoir plus, consultez les articles suivants :</span><span class="sxs-lookup"><span data-stu-id="b885e-155">See the following articles to learn more:</span></span>

* [<span data-ttu-id="b885e-156">Gérer des secteurs verticaux et des types de résultats</span><span class="sxs-lookup"><span data-stu-id="b885e-156">Manage verticals and result types</span></span>](customize-search-page.md)
* [<span data-ttu-id="b885e-157">Gérer les dispositions des résultats de la recherche</span><span class="sxs-lookup"><span data-stu-id="b885e-157">Manage search result layouts</span></span>](customize-results-layout.md)
* [<span data-ttu-id="b885e-158">Gérer le cluster de résultat</span><span class="sxs-lookup"><span data-stu-id="b885e-158">Manage result cluster</span></span>](result-cluster.md)
* [<span data-ttu-id="b885e-159">Gérer les filtres personnalisés</span><span class="sxs-lookup"><span data-stu-id="b885e-159">Manage custom filters</span></span>](custom-filters.md)

## <a name="how-do-i-search-my-connector-data-from-a-custom-application"></a><span data-ttu-id="b885e-160">Comment effectuer une recherche dans les données de mon connecteur à partir d’une application personnalisée ?</span><span class="sxs-lookup"><span data-stu-id="b885e-160">How do I search my connector data from a custom application?</span></span>

<span data-ttu-id="b885e-161">Une fois les données personnalisées indexées, les développeurs peuvent [interroger ces données.](/graph/search-concept-custom-types)</span><span class="sxs-lookup"><span data-stu-id="b885e-161">After custom data is indexed, developers can [query this data](/graph/search-concept-custom-types).</span></span> <span data-ttu-id="b885e-162">Vous pouvez afficher vos données dans n’importe quelle application.</span><span class="sxs-lookup"><span data-stu-id="b885e-162">You can view your data in any application.</span></span> <span data-ttu-id="b885e-163">Pour plus d’informations, voir la [vue d’ensemble de l’API Recherche Microsoft dans Microsoft Graph](/graph/search-concept-overview).</span><span class="sxs-lookup"><span data-stu-id="b885e-163">For more information, see the [Overview of the Microsoft Search API in Microsoft Graph](/graph/search-concept-overview).</span></span>

## <a name="how-do-i-customize-search-results"></a><span data-ttu-id="b885e-164">Comment personnaliser les résultats de recherche ?</span><span class="sxs-lookup"><span data-stu-id="b885e-164">How do I customize search results?</span></span>

<span data-ttu-id="b885e-165">L’étape suivante consiste à personnaliser les résultats de recherche comme recommandé dans cet article Comment personnaliser et configurer [les résultats de la recherche ?](#how-do-i-customize-and-configure-search-results)</span><span class="sxs-lookup"><span data-stu-id="b885e-165">The next step is to customize the search results as recommended in this article [How do I customize and configure search results?](#how-do-i-customize-and-configure-search-results).</span></span> <span data-ttu-id="b885e-166">Pour en savoir plus sur la personnalisation des résultats de recherche, voir [Personnaliser la page des résultats de la recherche.](customize-search-page.md)</span><span class="sxs-lookup"><span data-stu-id="b885e-166">To learn more about customizing search results, see [Customize the search results page](customize-search-page.md).</span></span>

## <a name="what-are-the-connector-limitations"></a><span data-ttu-id="b885e-167">Quelles sont les limitations du connecteur ?</span><span class="sxs-lookup"><span data-stu-id="b885e-167">What are the connector limitations?</span></span>

* <span data-ttu-id="b885e-168">Lorsque vous **publiez** un connecteur microsoft, la création de la connexion peut prendre quelques minutes.</span><span class="sxs-lookup"><span data-stu-id="b885e-168">When you **publish** a Microsoft-built connector, it can take a few minutes for the connection to be created.</span></span> <span data-ttu-id="b885e-169">Pendant ce temps, la connexion affiche son état en attente.</span><span class="sxs-lookup"><span data-stu-id="b885e-169">During that time, the connection will show its status as pending.</span></span>

* <span data-ttu-id="b885e-170">Le débit d’ingestion est limitée à environ quatre éléments par seconde.</span><span class="sxs-lookup"><span data-stu-id="b885e-170">Ingestion throughput is throttled at approximately four items per second.</span></span>

* <span data-ttu-id="b885e-171">Il n’existe aucune prise en charge des mises à jour de schéma.</span><span class="sxs-lookup"><span data-stu-id="b885e-171">There is no support for schema updates.</span></span> <span data-ttu-id="b885e-172">Après avoir créé une configuration de connexion, il n’existe aucun moyen de mettre à jour le schéma.</span><span class="sxs-lookup"><span data-stu-id="b885e-172">After you create a connection setup, there's no way to update the schema.</span></span> <span data-ttu-id="b885e-173">Vous pouvez uniquement supprimer et re-créer la connexion.</span><span class="sxs-lookup"><span data-stu-id="b885e-173">You can only delete and re-create the connection.</span></span>

* <span data-ttu-id="b885e-174">Il existe une limite de connexion.</span><span class="sxs-lookup"><span data-stu-id="b885e-174">There is a connection limit.</span></span> <span data-ttu-id="b885e-175">Chaque client peut créer jusqu’à 10 connexions.</span><span class="sxs-lookup"><span data-stu-id="b885e-175">Each tenant can create up to 10 connections.</span></span>

* <span data-ttu-id="b885e-176">Vous ne pouvez pas modifier ou modifier une connexion après sa création.</span><span class="sxs-lookup"><span data-stu-id="b885e-176">You cannot edit or change a connection after it has been created.</span></span> <span data-ttu-id="b885e-177">Si vous devez modifier des détails, vous devez supprimer et recréer la connexion.</span><span class="sxs-lookup"><span data-stu-id="b885e-177">If you need to change any details, you must delete and recreate the connection.</span></span>
