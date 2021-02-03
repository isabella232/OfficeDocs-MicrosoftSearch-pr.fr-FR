---
title: Cluster de résultats connecteurs
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
description: Détails de l’expérience du cluster de résultats connecteurs
ms.openlocfilehash: fb29fb9c14811698fb7c5d043853b57231c76a0b
ms.sourcegitcommit: d1bc6c41ecf47584373ce57543502bed55753d0c
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/02/2021
ms.locfileid: "50080836"
---
# <a name="graph-connectors-result-cluster"></a><span data-ttu-id="71e67-103">Cluster de résultats de connecteurs graphiques</span><span class="sxs-lookup"><span data-stu-id="71e67-103">Graph connectors result cluster</span></span>

## <a name="overview-of-the-graph-connectors-result-cluster-preview"></a><span data-ttu-id="71e67-104">Vue d’ensemble du cluster de résultats des connecteurs Graph (aperçu)</span><span class="sxs-lookup"><span data-stu-id="71e67-104">Overview of the Graph connectors result cluster (Preview)</span></span>  

<span data-ttu-id="71e67-105">Avec les clusters de résultats de connecteurs Graph, les entreprises peuvent  rechercher du contenu à partir de sources de données tierces dans leur affichage par défaut, l’onglet Tout, dans SharePoint, Office.com et Recherche Microsoft dans Bing.</span><span class="sxs-lookup"><span data-stu-id="71e67-105">With Graph connectors result clusters, enterprises can search for content from third party data sources in their default view, the **All** tab, in SharePoint, Office.com, and Microsoft Search in Bing.</span></span>

<span data-ttu-id="71e67-106">Les clusters de résultats aident les utilisateurs à découvrir tout le contenu tiers au même endroit.</span><span class="sxs-lookup"><span data-stu-id="71e67-106">Result clusters help users discover all third party content in one place.</span></span> <span data-ttu-id="71e67-107">Les résultats affichés dans un cluster de résultats sont regroupés en fonction de la configuration verticale de recherche.</span><span class="sxs-lookup"><span data-stu-id="71e67-107">The results shown in a result cluster are grouped together based on the search vertical configuration.</span></span>

## <a name="how-connector-results-are-selected-and-displayed"></a><span data-ttu-id="71e67-108">Sélection et affichage des résultats du connecteur</span><span class="sxs-lookup"><span data-stu-id="71e67-108">How connector results are selected and displayed</span></span>

<span data-ttu-id="71e67-109">Les résultats du connecteur fournis dans le cluster de résultats sont dérivés des secteurs verticaux de recherche individuels avec le contenu du connecteur.</span><span class="sxs-lookup"><span data-stu-id="71e67-109">Connector results provided in the result cluster are derived from individual search verticals with connector content.</span></span> <span data-ttu-id="71e67-110">Chaque secteur vertical de recherche fournit un ensemble de résultats pertinents qui devient un cluster de résultats candidat.</span><span class="sxs-lookup"><span data-stu-id="71e67-110">Each search vertical provides a set of relevant results which becomes a candidate result cluster.</span></span> <span data-ttu-id="71e67-111">Les résultats pertinents sont choisis en fonction de la propriété « title » et de la propriété « content » de chaque élément.</span><span class="sxs-lookup"><span data-stu-id="71e67-111">Relevant results are chosen based on the "title" property and "content" property of each item.</span></span> <span data-ttu-id="71e67-112">La propriété de contenu est marquée comme *étant isContent=true* sur le schéma.</span><span class="sxs-lookup"><span data-stu-id="71e67-112">The content property is marked as *isContent=true* on the schema.</span></span>

<span data-ttu-id="71e67-113">Pour garantir la découverte de contenu à partir des secteurs verticaux de recherche, nous vous recommandons de fournir des titres significatifs pour vos éléments.</span><span class="sxs-lookup"><span data-stu-id="71e67-113">To ensure discovery of content from the search verticals, we recommend providing meaningful titles for your items.</span></span> <span data-ttu-id="71e67-114">Cela a un impact positif sur l’arbitrage des candidats au cluster de résultats et la probabilité que votre contenu s’affiche dans un cluster de résultats.</span><span class="sxs-lookup"><span data-stu-id="71e67-114">This positively impacts the arbitration of result cluster candidates and the likelihood of your content showing up in a result cluster.</span></span> <span data-ttu-id="71e67-115">Par exemple, évitez d’utiliser des ID comme valeurs pour la propriété « title », sauf si vos utilisateurs utilisent des ID pour rechercher du contenu.</span><span class="sxs-lookup"><span data-stu-id="71e67-115">For example, avoid the use of IDs as values for the property "title" unless your users are using IDs to look for content.</span></span>

<span data-ttu-id="71e67-116">La fréquence d’utilisation d’un cluster de résultats varie selon des facteurs tels que le nombre de secteurs verticaux de recherche que vous configurez et le type de contenu.</span><span class="sxs-lookup"><span data-stu-id="71e67-116">How often a result cluster is shown varies on factors such as the number of search verticals that you configure and the type of content.</span></span> <span data-ttu-id="71e67-117">En interagissant ou en ignorant un cluster de résultats, les utilisateurs fournissent implicitement des conseils qui ajusteront son déclenchement au fil du temps.</span><span class="sxs-lookup"><span data-stu-id="71e67-117">By either interacting or ignoring a result cluster, users will implicitly provide hints that will adjust its triggering over time.</span></span>

<span data-ttu-id="71e67-118">L’expérience de résultat de recherche pour les éléments de connecteur affichés dans votre cluster de résultats utilise les types de [résultats](https://docs.microsoft.com/microsoftsearch/customize-search-page#create-your-own-result-type) que vous avez définis.</span><span class="sxs-lookup"><span data-stu-id="71e67-118">The search result experience for connector items shown in your result cluster uses [result types](https://docs.microsoft.com/microsoftsearch/customize-search-page#create-your-own-result-type) defined by you.</span></span> <span data-ttu-id="71e67-119">Si aucun type de résultat n’est configuré, une [disposition générée par le](https://docs.microsoft.com/microsoftsearch/customize-search-page#default-search-result-layout) système est utilisée.</span><span class="sxs-lookup"><span data-stu-id="71e67-119">If no result type is configured, a [system generated layout](https://docs.microsoft.com/microsoftsearch/customize-search-page#default-search-result-layout) is used.</span></span> 

<span data-ttu-id="71e67-120">Nous vous recommandons d’utiliser la propriété « title » comme titre de résultat de recherche et la propriété « content » comme description de recherche.</span><span class="sxs-lookup"><span data-stu-id="71e67-120">We recommend using the “title” property as the search result title and the "content" property as the search description.</span></span> <span data-ttu-id="71e67-121">Cela permet à vos utilisateurs de tirer le meilleur résultat du cluster de résultats avec précision et les résultats les plus pertinents dans le cluster.</span><span class="sxs-lookup"><span data-stu-id="71e67-121">This will provide the best experience for your users through accurate triggering of the result cluster and most relevant results in the cluster.</span></span> 

## <a name="enable-result-clusters"></a><span data-ttu-id="71e67-122">Activer les clusters de résultats</span><span class="sxs-lookup"><span data-stu-id="71e67-122">Enable result clusters</span></span>
  
<span data-ttu-id="71e67-123">L’expérience de cluster de résultats est désactivée par défaut.</span><span class="sxs-lookup"><span data-stu-id="71e67-123">The result cluster experience is turned off by default.</span></span>  

<span data-ttu-id="71e67-124">Suivez ces étapes pour activer l’expérience au niveau de l’organisation :</span><span class="sxs-lookup"><span data-stu-id="71e67-124">Follow these steps to turn on the experience at the organization level:</span></span>

1. <span data-ttu-id="71e67-125">Dans le [Centre d’administration Microsoft 365,](https://admin.microsoft.com)allez à [**Verticals**](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/verticals).</span><span class="sxs-lookup"><span data-stu-id="71e67-125">In the [Microsoft 365 admin center](https://admin.microsoft.com), go to [**Verticals**](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/verticals).</span></span>
2. <span data-ttu-id="71e67-126">Sélectionnez le secteur vertical **Tout,** puis **activez afficher les résultats du connecteur.**</span><span class="sxs-lookup"><span data-stu-id="71e67-126">Select  the **All** vertical, then enable **Show connector results**.</span></span> 


<span data-ttu-id="71e67-127">Suivez ces étapes pour activer l’expérience au niveau du site SharePoint :</span><span class="sxs-lookup"><span data-stu-id="71e67-127">Follow these steps to turn on the experience at the SharePoint site level:</span></span>

1. <span data-ttu-id="71e67-128">Sur le site SharePoint où vous souhaitez l’expérience de cluster de résultats, go to **Settings**.</span><span class="sxs-lookup"><span data-stu-id="71e67-128">On the SharePoint site where you want the result cluster experience, go to **Settings**.</span></span>
2. <span data-ttu-id="71e67-129">Go to **Site information** View all > **site settings**.</span><span class="sxs-lookup"><span data-stu-id="71e67-129">Go to **Site information**>**View all site settings**.</span></span>
3. <span data-ttu-id="71e67-130">Go to the Microsoft Search section, then select **Configure Microsoft Search for this site collection**.</span><span class="sxs-lookup"><span data-stu-id="71e67-130">Go to the Microsoft Search section, then select **Configure Microsoft Search for this site collection**.</span></span>
4. <span data-ttu-id="71e67-131">Dans le volet de navigation, sélectionnez **Expérience personnalisée,** puis sélectionnez **Verticals**.</span><span class="sxs-lookup"><span data-stu-id="71e67-131">In the navigation pane, go to **Custom experience**, then select **Verticals**.</span></span>
5. <span data-ttu-id="71e67-132">Sélectionnez le secteur vertical **Tout,** puis **activez afficher les résultats du connecteur.**</span><span class="sxs-lookup"><span data-stu-id="71e67-132">Select the **All** vertical, then enable **Show connector results**.</span></span>

## <a name="view-the-result-cluster-experience-after-it-is-enabled"></a><span data-ttu-id="71e67-133">Afficher l’expérience de cluster de résultats une fois qu’elle est activée</span><span class="sxs-lookup"><span data-stu-id="71e67-133">View the result cluster experience after it is enabled</span></span>

<span data-ttu-id="71e67-134">Une fois que vous avez mis en place l’expérience de cluster de résultats, l’affichage du cluster de résultats peut prendre jusqu’à 12 heures.</span><span class="sxs-lookup"><span data-stu-id="71e67-134">After you turn on the result cluster experience, it can take up to 12 hours before you can view it.</span></span> <span data-ttu-id="71e67-135">Si vous souhaitez que l’expérience soit immédiatement disponible, vous pouvez l’appendre *à l’URL* dans SharePoint et Office.</span><span class="sxs-lookup"><span data-stu-id="71e67-135">If you want the experience immediately, you can append *cacheClear=true* to the URL in SharePoint and Office.</span></span>
