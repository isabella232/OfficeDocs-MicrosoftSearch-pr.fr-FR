---
title: Gérer les filtres personnalisés
ms.author: rodhb
author: rodhb
manager: jeffkizn
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: Gérer les filtres personnalisés
ms.openlocfilehash: 75273035a7825683f626464df7bbc8e294b41b6f
ms.sourcegitcommit: 59435698bece013ae64ca2a68c43455ca10e3fdf
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/05/2020
ms.locfileid: "48927381"
---
# <a name="create-custom-filters"></a><span data-ttu-id="8325a-103">Créer des filtres personnalisés</span><span class="sxs-lookup"><span data-stu-id="8325a-103">Create custom Filters</span></span>

<span data-ttu-id="8325a-104">Vous pouvez créer des filtres pour personnaliser l’expérience de recherche que les utilisateurs voient lorsqu’ils recherchent dans Microsoft [SharePoint](https://sharepoint.com/), Microsoft [Office](https://office.com)et Microsoft Search dans [Bing](https://bing.com).</span><span class="sxs-lookup"><span data-stu-id="8325a-104">You can create filters to customize the search experience that users see when they search in Microsoft [SharePoint](https://sharepoint.com/), Microsoft [Office](https://office.com), and Microsoft Search in [Bing](https://bing.com).</span></span> <span data-ttu-id="8325a-105">Filtres permet aux utilisateurs d’affiner rapidement le jeu de résultats à partir de leur requête de recherche.</span><span class="sxs-lookup"><span data-stu-id="8325a-105">Filters lets users quickly refine the set of results from their search query.</span></span>

<span data-ttu-id="8325a-106">Un filtre personnalisé peut être créé à l’intérieur d’un vertical basé sur une propriété Connection.</span><span class="sxs-lookup"><span data-stu-id="8325a-106">A custom filter can be created inside a vertical based on a connection property.</span></span> <span data-ttu-id="8325a-107">Par exemple, vous pouvez créer un filtre **publié sur** un filtre pour une connexion ServiceNow à l’intérieur d’un secteur vertical personnalisé.</span><span class="sxs-lookup"><span data-stu-id="8325a-107">For example, you can create a **Published On** filter for ServiceNow connection inside a custom vertical.</span></span>

## <a name="things-to-consider"></a><span data-ttu-id="8325a-108">Informations importantes</span><span class="sxs-lookup"><span data-stu-id="8325a-108">Things to consider</span></span>

1. <span data-ttu-id="8325a-109">Pour créer un filtre personnalisé sur la source de contenu de connexion, certaines fonctionnalités supplémentaires sont fournies :</span><span class="sxs-lookup"><span data-stu-id="8325a-109">For creating custom filter on connection content source, some additional capabilities are provided:</span></span>
- <span data-ttu-id="8325a-110">Vous pouvez également créer un filtre sur un alias pour les propriétés source du connecteur.</span><span class="sxs-lookup"><span data-stu-id="8325a-110">You can also create filter on an alias to connector source properties</span></span>
- <span data-ttu-id="8325a-111">Si votre vertical dispose de plusieurs connexions, vous pouvez créer un filtre commun sur ces connexions.</span><span class="sxs-lookup"><span data-stu-id="8325a-111">In case your vertical has multiple connections then you can create a common filter across these connections.</span></span> <span data-ttu-id="8325a-112">Pour ce faire, vous pouvez créer le filtre sur un alias commun qui aliase les propriétés source sur différentes connexions.</span><span class="sxs-lookup"><span data-stu-id="8325a-112">This can be done by creating the filter on an common alias which aliases source properties across across different connections.</span></span> <span data-ttu-id="8325a-113">Par exemple, vous pouvez créer un filtre **auteur** sur un ServiceNow & une connexion JIRA en créant des alias comme suit :</span><span class="sxs-lookup"><span data-stu-id="8325a-113">For example you can create an **Author** filter across a ServiceNow & a Jira connection by creating aliases as follows:</span></span>

| <span data-ttu-id="8325a-114">Connection</span><span class="sxs-lookup"><span data-stu-id="8325a-114">Connection</span></span> | <span data-ttu-id="8325a-115">Propriété</span><span class="sxs-lookup"><span data-stu-id="8325a-115">Property</span></span> | <span data-ttu-id="8325a-116">Alias</span><span class="sxs-lookup"><span data-stu-id="8325a-116">Alias</span></span> |
| --- | --- | --- |
| <span data-ttu-id="8325a-117">Service maintenant</span><span class="sxs-lookup"><span data-stu-id="8325a-117">Service Now</span></span> | <span data-ttu-id="8325a-118">Propriétaire</span><span class="sxs-lookup"><span data-stu-id="8325a-118">Owner</span></span> | <span data-ttu-id="8325a-119">Auteur</span><span class="sxs-lookup"><span data-stu-id="8325a-119">Author</span></span> |
| <span data-ttu-id="8325a-120">Jira</span><span class="sxs-lookup"><span data-stu-id="8325a-120">Jira</span></span> | <span data-ttu-id="8325a-121">Éditeur</span><span class="sxs-lookup"><span data-stu-id="8325a-121">Publisher</span></span> | <span data-ttu-id="8325a-122">Auteur</span><span class="sxs-lookup"><span data-stu-id="8325a-122">Author</span></span> |

2. <span data-ttu-id="8325a-123">Les filtres existent dans l’étendue du secteur vertical.</span><span class="sxs-lookup"><span data-stu-id="8325a-123">Filters exist within the scope of the vertical.</span></span> <span data-ttu-id="8325a-124">Car</span><span class="sxs-lookup"><span data-stu-id="8325a-124">Hence,</span></span>  
- <span data-ttu-id="8325a-125">Si un filtre est créé dans un secteur vertical au niveau de l’organisation, le filtre n’est visible qu’au niveau de l’organisation.</span><span class="sxs-lookup"><span data-stu-id="8325a-125">If a filter is created in a vertical which is at organizational level, then the filter would only be visible at the organizational level</span></span>
- <span data-ttu-id="8325a-126">Si un filtre est créé dans un secteur vertical au niveau du site, le filtre n’est visible qu’au niveau du site.</span><span class="sxs-lookup"><span data-stu-id="8325a-126">If a filter is created in a vertical which is at site level, then the filter would only be visible at the site level.</span></span>

## <a name="steps-to-create-custom-filter"></a><span data-ttu-id="8325a-127">Étapes de création d’un filtre personnalisé</span><span class="sxs-lookup"><span data-stu-id="8325a-127">Steps to Create custom filter</span></span>

### <a name="create-filter-in-organizational-level-vertical"></a><span data-ttu-id="8325a-128">Créer un filtre au niveau de l’organisation verticale :</span><span class="sxs-lookup"><span data-stu-id="8325a-128">Create filter in organizational level vertical:</span></span>

<span data-ttu-id="8325a-129">Pour créer un filtre sur Microsoft Search, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="8325a-129">To create a filter on Microsoft search follow these steps:</span></span>

1. <span data-ttu-id="8325a-130">Dans le centre d’administration Microsoft 365, accédez à la page des [secteurs verticaux](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/verticals) .</span><span class="sxs-lookup"><span data-stu-id="8325a-130">In the Microsoft 365 admin center, go to the [Verticals](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/verticals) page.</span></span>
2. <span data-ttu-id="8325a-131">Créez/modifiez le secteur vertical dans lequel vous souhaitez créer le filtre.</span><span class="sxs-lookup"><span data-stu-id="8325a-131">Create/Edit the vertical in which you want to create the filter</span></span>
3. <span data-ttu-id="8325a-132">Accéder à l’étape « filtres » dans l’Assistant</span><span class="sxs-lookup"><span data-stu-id="8325a-132">Navigate to the 'Filters' step in the wizard</span></span>
4. <span data-ttu-id="8325a-133">Cliquez sur Ajouter un filtre et commencez après avoir ajouté des filtres, vous pouvez consulter et enregistrer le secteur vertical.</span><span class="sxs-lookup"><span data-stu-id="8325a-133">Click on 'Add Filter' and get started After adding filters, you can review and save the vertical.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="8325a-134">Limitations connues</span><span class="sxs-lookup"><span data-stu-id="8325a-134">Known Limitations</span></span>

1. <span data-ttu-id="8325a-135">Vous pouvez actuellement créer des filtres uniquement sur la chaîne & les propriétés gérées de type date.</span><span class="sxs-lookup"><span data-stu-id="8325a-135">You can currently create filters only on String & Date type managed properties.</span></span>
2. <span data-ttu-id="8325a-136">Vous ne pouvez pas créer de filtres hiérarchiques</span><span class="sxs-lookup"><span data-stu-id="8325a-136">You cannot create hierarchical filters</span></span>

## <a name="resources"></a><span data-ttu-id="8325a-137">Ressources</span><span class="sxs-lookup"><span data-stu-id="8325a-137">Resources</span></span>

[<span data-ttu-id="8325a-138">Personnaliser la page des résultats de recherche</span><span class="sxs-lookup"><span data-stu-id="8325a-138">Customize search result page</span></span>](customize-search-page.md)