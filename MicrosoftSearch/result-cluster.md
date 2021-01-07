---
title: Cluster de résultats de connecteurs
ms.author: manusi
author: manusi
manager: ruppala
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: Détails de l’expérience de cluster de résultats de connecteurs
ms.openlocfilehash: f2355213a0b1821968c801153841c274e539d72e
ms.sourcegitcommit: 7294c953e7939e48f128656cc2f8f22705ae3f3d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/06/2021
ms.locfileid: "49773026"
---
# <a name="graph-connectors-result-cluster"></a><span data-ttu-id="2fc68-103">Cluster de résultats de connecteurs Graph</span><span class="sxs-lookup"><span data-stu-id="2fc68-103">Graph connectors result cluster</span></span>

## <a name="overview-of-the-graph-connectors-result-cluster-preview"></a><span data-ttu-id="2fc68-104">Vue d’ensemble du cluster de résultats connecteurs Graph (aperçu)</span><span class="sxs-lookup"><span data-stu-id="2fc68-104">Overview of the Graph connectors result cluster (Preview)</span></span>  

<span data-ttu-id="2fc68-105">Avec les clusters de résultats des connecteurs Graph, les entreprises peuvent rechercher du contenu provenant de sources de données tierces dans leur affichage par défaut, l’onglet **tous** , dans SharePoint, Office.com et Microsoft Search dans Bing.</span><span class="sxs-lookup"><span data-stu-id="2fc68-105">With Graph connectors result clusters, enterprises can search for content from third party data sources in their default view, the **All** tab, in SharePoint, Office.com, and Microsoft Search in Bing.</span></span>

<span data-ttu-id="2fc68-106">Les clusters de résultats aident les utilisateurs à découvrir tous les contenus tiers à un seul emplacement.</span><span class="sxs-lookup"><span data-stu-id="2fc68-106">Result clusters help users discover all third party content in one place.</span></span> <span data-ttu-id="2fc68-107">Les résultats affichés dans un cluster de résultats sont regroupés en fonction de la configuration du secteur vertical de recherche.</span><span class="sxs-lookup"><span data-stu-id="2fc68-107">The results shown in a result cluster are grouped together based on the search vertical configuration.</span></span>

## <a name="how-connector-results-are-selected-and-displayed"></a><span data-ttu-id="2fc68-108">Sélection et affichage des résultats du connecteur</span><span class="sxs-lookup"><span data-stu-id="2fc68-108">How connector results are selected and displayed</span></span>

<span data-ttu-id="2fc68-109">Les résultats de connecteur fournis dans le cluster de résultats sont dérivés de secteurs verticaux de recherche individuels avec contenu de connecteur.</span><span class="sxs-lookup"><span data-stu-id="2fc68-109">Connector results provided in the result cluster are derived from individual search verticals with connector content.</span></span> <span data-ttu-id="2fc68-110">Chaque secteur vertical de recherche fournit un ensemble de résultats pertinents qui devient un cluster de résultats candidats.</span><span class="sxs-lookup"><span data-stu-id="2fc68-110">Each search vertical provides a set of relevant results which becomes a candidate result cluster.</span></span> <span data-ttu-id="2fc68-111">Les résultats pertinents sont choisis en fonction de la propriété « Title » et de la propriété « Content » de chaque élément.</span><span class="sxs-lookup"><span data-stu-id="2fc68-111">Relevant results are chosen based on the "title" property and "content" property of each item.</span></span> <span data-ttu-id="2fc68-112">La propriété Content est marquée comme *IsContent = true* dans le schéma.</span><span class="sxs-lookup"><span data-stu-id="2fc68-112">The content property is marked as *isContent=true* on the schema.</span></span>

<span data-ttu-id="2fc68-113">Pour vous assurer de la découverte du contenu des secteurs verticaux de recherche, nous vous recommandons de fournir des titres explicites pour vos éléments.</span><span class="sxs-lookup"><span data-stu-id="2fc68-113">To ensure discovery of content from the search verticals, we recommend providing meaningful titles for your items.</span></span> <span data-ttu-id="2fc68-114">Cela a un impact positif sur l’arbitrage des candidats aux clusters de résultats et la probabilité que votre contenu apparaisse dans un cluster de résultats.</span><span class="sxs-lookup"><span data-stu-id="2fc68-114">This positively impacts the arbitration of result cluster candidates and the likelihood of your content showing up in a result cluster.</span></span> <span data-ttu-id="2fc68-115">Par exemple, évitez d’utiliser des ID comme valeurs pour la propriété « Title », sauf si vos utilisateurs utilisent des ID pour rechercher du contenu.</span><span class="sxs-lookup"><span data-stu-id="2fc68-115">For example, avoid the use of IDs as values for the property "title" unless your users are using IDs to look for content.</span></span>

<span data-ttu-id="2fc68-116">La fréquence à laquelle un cluster de résultats est affiché varie selon les facteurs tels que le nombre de secteurs verticaux de recherche que vous configurez et le type de contenu.</span><span class="sxs-lookup"><span data-stu-id="2fc68-116">How often a result cluster is shown varies on factors such as the number of search verticals that you configure and the type of content.</span></span> <span data-ttu-id="2fc68-117">En interagissant ou en ignorant un cluster de résultats, les utilisateurs fournissent implicitement des indications qui ajustent son déclenchement dans le temps.</span><span class="sxs-lookup"><span data-stu-id="2fc68-117">By either interacting or ignoring a result cluster, users will implicitly provide hints that will adjust its triggering over time.</span></span>

<span data-ttu-id="2fc68-118">L’expérience des résultats de recherche pour les éléments de connecteur affichés dans votre cluster de résultats utilise les [types de résultats](https://docs.microsoft.com/microsoftsearch/customize-search-page#create-your-own-result-type) que vous avez définis.</span><span class="sxs-lookup"><span data-stu-id="2fc68-118">The search result experience for connector items shown in your result cluster uses [result types](https://docs.microsoft.com/microsoftsearch/customize-search-page#create-your-own-result-type) defined by you.</span></span> <span data-ttu-id="2fc68-119">Si aucun type de résultat n’est configuré, une [mise en page générée](https://docs.microsoft.com/microsoftsearch/customize-search-page#default-search-result-layout) par le système est utilisée.</span><span class="sxs-lookup"><span data-stu-id="2fc68-119">If no result type is configured, a [system generated layout](https://docs.microsoft.com/microsoftsearch/customize-search-page#default-search-result-layout) is used.</span></span> 

<span data-ttu-id="2fc68-120">Nous vous recommandons d’utiliser la propriété « Title » comme titre du résultat de recherche et la propriété « Content » comme description de la recherche.</span><span class="sxs-lookup"><span data-stu-id="2fc68-120">We recommend using the “title” property as the search result title and the "content" property as the search description.</span></span> <span data-ttu-id="2fc68-121">Cela permettra à vos utilisateurs de bénéficier d’un déclenchement précis du cluster de résultats et de la plupart des résultats pertinents dans le cluster.</span><span class="sxs-lookup"><span data-stu-id="2fc68-121">This will provide the best experience for your users through accurate triggering of the result cluster and most relevant results in the cluster.</span></span> 

## <a name="enable-result-clusters"></a><span data-ttu-id="2fc68-122">Activer les clusters de résultats</span><span class="sxs-lookup"><span data-stu-id="2fc68-122">Enable result clusters</span></span>
  
<span data-ttu-id="2fc68-123">L’expérience de cluster de résultats est désactivée par défaut.</span><span class="sxs-lookup"><span data-stu-id="2fc68-123">The result cluster experience is turned off by default.</span></span>  

<span data-ttu-id="2fc68-124">Pour activer l’expérience au niveau de l’organisation, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="2fc68-124">Follow these steps to turn on the experience at the organization level:</span></span>

1. <span data-ttu-id="2fc68-125">Dans le [Centre d’administration Microsoft 365](https://admin.microsoft.com), accédez à la [**barre verticale**](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/verticals).</span><span class="sxs-lookup"><span data-stu-id="2fc68-125">In the [Microsoft 365 admin center](https://admin.microsoft.com), go to [**Verticals**](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/verticals).</span></span>
2. <span data-ttu-id="2fc68-126">Sélectionnez l’option **tous** les secteurs verticaux, puis activer afficher les **résultats du connecteur**.</span><span class="sxs-lookup"><span data-stu-id="2fc68-126">Select  the **All** vertical, then enable **Show connector results**.</span></span> 


<span data-ttu-id="2fc68-127">Pour activer l’expérience au niveau du site SharePoint, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="2fc68-127">Follow these steps to turn on the experience at the SharePoint site level:</span></span>

1. <span data-ttu-id="2fc68-128">Sur le site SharePoint où vous souhaitez obtenir l’expérience de cluster de résultats, accédez à **paramètres**.</span><span class="sxs-lookup"><span data-stu-id="2fc68-128">On the SharePoint site where you want the result cluster experience, go to **Settings**.</span></span>
2. <span data-ttu-id="2fc68-129">Accédez à **informations sur le site** > **Afficher tous les paramètres du site**.</span><span class="sxs-lookup"><span data-stu-id="2fc68-129">Go to **Site information**>**View all site settings**.</span></span>
3. <span data-ttu-id="2fc68-130">Accédez à la section Microsoft Search, puis sélectionnez **configurer Microsoft Search pour cette collection de sites**.</span><span class="sxs-lookup"><span data-stu-id="2fc68-130">Go to the Microsoft Search section, then select **Configure Microsoft Search for this site collection**.</span></span>
4. <span data-ttu-id="2fc68-131">Dans le volet de navigation, accédez à **expérience personnalisée**, puis sélectionnez **verticales**.</span><span class="sxs-lookup"><span data-stu-id="2fc68-131">In the navigation pane, go to **Custom experience**, then select **Verticals**.</span></span>
5. <span data-ttu-id="2fc68-132">Sélectionnez l’option **tous** les secteurs verticaux, puis activer afficher les **résultats du connecteur**.</span><span class="sxs-lookup"><span data-stu-id="2fc68-132">Select the **All** vertical, then enable **Show connector results**.</span></span>

## <a name="view-the-result-cluster-experience-after-it-is-enabled"></a><span data-ttu-id="2fc68-133">Afficher l’expérience de cluster de résultats une fois qu’elle est activée</span><span class="sxs-lookup"><span data-stu-id="2fc68-133">View the result cluster experience after it is enabled</span></span>

<span data-ttu-id="2fc68-134">Une fois que vous avez activé l’expérience de cluster de résultats, l’affichage peut prendre quelques minutes.</span><span class="sxs-lookup"><span data-stu-id="2fc68-134">After you turn on the result cluster experience, it might take a few minutes before you can view it.</span></span> <span data-ttu-id="2fc68-135">Si vous souhaitez l’expérience immédiatement, vous pouvez ajouter *cacheClear = true* à l’URL dans SharePoint et Office.</span><span class="sxs-lookup"><span data-stu-id="2fc68-135">If you want the experience immediately, you can append *cacheClear=true* to the URL in SharePoint and Office.</span></span>
