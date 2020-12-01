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
ms.openlocfilehash: fa6ac2dc720ed43e40454b952526734accd45ea4
ms.sourcegitcommit: a328b9764abf5cd0c1c0a8c7def0c6e334da9a1d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/30/2020
ms.locfileid: "49477112"
---
# <a name="graph-connectors-result-cluster"></a><span data-ttu-id="a0746-103">Cluster de résultats de connecteurs Graph</span><span class="sxs-lookup"><span data-stu-id="a0746-103">Graph connectors result cluster</span></span>

## <a name="overview-of-the-graph-connectors-result-cluster-preview"></a><span data-ttu-id="a0746-104">Vue d’ensemble du cluster de résultats connecteurs Graph (aperçu)</span><span class="sxs-lookup"><span data-stu-id="a0746-104">Overview of the Graph connectors result cluster (Preview)</span></span>  

<span data-ttu-id="a0746-105">Avec les clusters de résultats des connecteurs Graph, les entreprises peuvent rechercher du contenu provenant de sources de données tierces dans leur affichage par défaut (onglet tous) dans SharePoint et Office.com.</span><span class="sxs-lookup"><span data-stu-id="a0746-105">With Graph connectors result clusters, enterprises can search for content from third party data sources in their default view (the All tab) in SharePoint and Office.com.</span></span>

<span data-ttu-id="a0746-106">Les clusters de résultats aident les utilisateurs à découvrir tous les contenus tiers (previoulsy liés à un connecteur et à la verticale) à un seul endroit.</span><span class="sxs-lookup"><span data-stu-id="a0746-106">Result clusters help users discover all third party content (previoulsy tied to a single connector and vertical) in one place.</span></span> <span data-ttu-id="a0746-107">Les résultats affichés dans un cluster de résultats sont regroupés en fonction de la façon dont l’administrateur client les configure dans un secteur vertical de recherche.</span><span class="sxs-lookup"><span data-stu-id="a0746-107">The results shown in a result cluster are grouped together based on how the tenant administrator configures them in a search vertical.</span></span>  

## <a name="how-connector-results-are-selected-and-displayed"></a><span data-ttu-id="a0746-108">Sélection et affichage des résultats du connecteur</span><span class="sxs-lookup"><span data-stu-id="a0746-108">How connector results are selected and displayed</span></span>

<span data-ttu-id="a0746-109">Les résultats de connecteur fournis dans le cluster de résultats sont dérivés de secteurs verticaux de recherche individuels avec contenu de connecteur.</span><span class="sxs-lookup"><span data-stu-id="a0746-109">Connector results provided in the result cluster are derived from individual search verticals with connector content.</span></span> <span data-ttu-id="a0746-110">Chaque secteur vertical de recherche fournit un ensemble de résultats pertinents qui devient un cluster de résultats candidats.</span><span class="sxs-lookup"><span data-stu-id="a0746-110">Each search vertical provides a set of relevant results which becomes a candidate result cluster.</span></span> <span data-ttu-id="a0746-111">Les résultats pertinents sont choisis en fonction de la propriété « Title », de l’extrait de résultats et du composant de contenu de chaque élément.</span><span class="sxs-lookup"><span data-stu-id="a0746-111">Relevant results are chosen based on the "title" property, result snippet, and content component of each item.</span></span>

<span data-ttu-id="a0746-112">Pour vous assurer de la découverte du contenu des secteurs verticaux de recherche, nous vous recommandons de fournir des titres explicites pour vos éléments.</span><span class="sxs-lookup"><span data-stu-id="a0746-112">To ensure discovery of content from the search verticals, we recommend providing meaningful titles for your items.</span></span> <span data-ttu-id="a0746-113">Cela a un impact positif sur l’arbitrage des candidats aux clusters de résultats et la probabilité que votre contenu apparaisse dans un cluster de résultats.</span><span class="sxs-lookup"><span data-stu-id="a0746-113">This positively impacts the arbitration of result cluster candidates and the likelihood of your content showing up in a result cluster.</span></span> <span data-ttu-id="a0746-114">Par exemple, évitez d’utiliser des ID comme valeurs pour la propriété « Title », sauf si vos utilisateurs utilisent des ID pour rechercher du contenu.</span><span class="sxs-lookup"><span data-stu-id="a0746-114">For example, avoid the use of IDs as values for the property "title" unless your users are using IDs to look for content.</span></span>

<span data-ttu-id="a0746-115">La fréquence à laquelle un cluster de résultats est affiché varie selon les facteurs tels que le nombre de secteurs verticaux de recherche que vous configurez et le type de contenu.</span><span class="sxs-lookup"><span data-stu-id="a0746-115">How often a result cluster is shown varies on factors such as the number of search verticals that you configure and the type of content.</span></span> <span data-ttu-id="a0746-116">En sélectionnant ou en ignorant les résultats du cluster de résultats, vous fournissez implicitement des indications qui ajusteront le déclenchement des clusters de résultats au fil du temps.</span><span class="sxs-lookup"><span data-stu-id="a0746-116">By either selecting or ignoring result cluster results, you will implicitly provide hints that will adjust the triggering of result clusters over time.</span></span>

<span data-ttu-id="a0746-117">L’expérience des résultats de recherche pour les éléments de connecteur affichés dans votre cluster de résultats est générée par le système et n’utilise pas de mise en page de résultats personnalisée.</span><span class="sxs-lookup"><span data-stu-id="a0746-117">The search result experience for connector items shown in your result cluster is system generated and does not use custom result layouts.</span></span> <span data-ttu-id="a0746-118">Vous devez déclarer la propriété « Title » et le contenu de l’élément lors de l’inscription de la connexion si vous souhaitez que les résultats apparaissent dans votre cluster de résultats.</span><span class="sxs-lookup"><span data-stu-id="a0746-118">You must declare the "title" property and item content during connection registration if you want results to appear in your result cluster.</span></span>

## <a name="enable-result-clusters"></a><span data-ttu-id="a0746-119">Activer les clusters de résultats</span><span class="sxs-lookup"><span data-stu-id="a0746-119">Enable result clusters</span></span>
  
<span data-ttu-id="a0746-120">L’expérience de cluster de résultats est désactivée par défaut.</span><span class="sxs-lookup"><span data-stu-id="a0746-120">The result cluster experience is turned off by default.</span></span>  

<span data-ttu-id="a0746-121">Pour activer l’expérience au niveau de l’organisation, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="a0746-121">Follow these steps to turn on the experience at the organization level:</span></span>

1. <span data-ttu-id="a0746-122">Dans le [Centre d’administration 365 de Microsoft](https://admin.microsoft.com/), accédez à **paramètres** de  >  **recherche &** aide au secteur vertical pour la personnalisation de l’intelligence  >  **Customization**  >  **Verticals**.</span><span class="sxs-lookup"><span data-stu-id="a0746-122">In the [Microsoft 365 admin center](https://admin.microsoft.com/), go to **Settings** > **Search & intelligence** > **Customization** > **Verticals**.</span></span>  
2. <span data-ttu-id="a0746-123">Sélectionnez l’option **tous** les secteurs verticaux, puis activer afficher les **résultats du connecteur**.</span><span class="sxs-lookup"><span data-stu-id="a0746-123">Select  the **All** vertical, then enable **Show connector results**.</span></span> 


<span data-ttu-id="a0746-124">Pour activer l’expérience au niveau du site, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="a0746-124">Follow these steps to turn on the experience at the site level:</span></span>

1. <span data-ttu-id="a0746-125">Sur le site SharePoint où vous souhaitez obtenir l’expérience de cluster de résultats, accédez à **paramètres**.</span><span class="sxs-lookup"><span data-stu-id="a0746-125">On the SharePoint site where you want the result cluster experience, go to **Settings**.</span></span>
2. <span data-ttu-id="a0746-126">Accédez à **informations sur le site** > **Afficher tous les paramètres du site**.</span><span class="sxs-lookup"><span data-stu-id="a0746-126">Go to **Site information**>**View all site settings**.</span></span>
3. <span data-ttu-id="a0746-127">Accédez à la section Microsoft Search, puis sélectionnez **configurer Microsoft Search pour cette collection de sites**.</span><span class="sxs-lookup"><span data-stu-id="a0746-127">Go to the Microsoft Search section, then select **Configure Microsoft Search for this site collection**.</span></span>
4. <span data-ttu-id="a0746-128">Dans le volet de navigation, accédez à **expérience personnalisée**, puis sélectionnez **verticales**.</span><span class="sxs-lookup"><span data-stu-id="a0746-128">In the navigation pane, go to **Custom experience**, then select **Verticals**.</span></span>
5. <span data-ttu-id="a0746-129">Sélectionnez l’option **tous** les secteurs verticaux, puis activer afficher les **résultats du connecteur**.</span><span class="sxs-lookup"><span data-stu-id="a0746-129">Select the **All** vertical, then enable **Show connector results**.</span></span>

## <a name="view-the-result-cluster-experience-after-it-is-enabled"></a><span data-ttu-id="a0746-130">Afficher l’expérience de cluster de résultats une fois qu’elle est activée</span><span class="sxs-lookup"><span data-stu-id="a0746-130">View the result cluster experience after it is enabled</span></span>

<span data-ttu-id="a0746-131">Une fois que vous avez activé l’expérience de cluster de résultats, l’affichage peut prendre quelques minutes.</span><span class="sxs-lookup"><span data-stu-id="a0746-131">After you turn on the result cluster experience, it might take a few minutes before you can view it.</span></span> <span data-ttu-id="a0746-132">Si vous souhaitez l’expérience immédiatement, vous pouvez ajouter *cacheClear = true* à l’URL dans SharePoint et Office.</span><span class="sxs-lookup"><span data-stu-id="a0746-132">If you want the experience immediately, you can append *cacheClear=true* to the URL in SharePoint and Office.</span></span>
