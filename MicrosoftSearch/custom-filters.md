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
ms.openlocfilehash: a050921058eac50d7588f1e71f5b0f56cc8e5752
ms.sourcegitcommit: a86265684871da86562a76c4961d0a6c1869f517
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/09/2021
ms.locfileid: "49790329"
---
# <a name="manage-custom-filters"></a><span data-ttu-id="d440b-103">Gérer les filtres personnalisés</span><span class="sxs-lookup"><span data-stu-id="d440b-103">Manage custom filters</span></span>

<span data-ttu-id="d440b-104">Vous pouvez utiliser des filtres pour personnaliser l’expérience Recherche Microsoft.</span><span class="sxs-lookup"><span data-stu-id="d440b-104">You can use filters to customize the Microsoft Search experience.</span></span> <span data-ttu-id="d440b-105">Les filtres permettent aux utilisateurs d’affiner rapidement l’ensemble des résultats de leur requête de recherche.</span><span class="sxs-lookup"><span data-stu-id="d440b-105">Filters let users quickly refine the set of results from their search query.</span></span>

<span data-ttu-id="d440b-106">Un filtre personnalisé peut être créé à l’intérieur d’un secteur vertical basé sur une propriété de connexion.</span><span class="sxs-lookup"><span data-stu-id="d440b-106">A custom filter can be created inside a vertical based on a connection property.</span></span> <span data-ttu-id="d440b-107">Par exemple, vous pouvez créer un **filtre Publié sur** pour la connexion ServiceNow à l’intérieur d’un secteur vertical.</span><span class="sxs-lookup"><span data-stu-id="d440b-107">For example, you can create a **Published On** filter for ServiceNow connection inside a vertical.</span></span>

## <a name="create-a-filter-in-an-organizational-level-vertical"></a><span data-ttu-id="d440b-108">Créer un filtre dans un secteur vertical au niveau de l’organisation</span><span class="sxs-lookup"><span data-stu-id="d440b-108">Create a filter in an organizational level vertical</span></span>

<span data-ttu-id="d440b-109">Pour créer un filtre sur la recherche Microsoft, suivez les étapes suivantes :</span><span class="sxs-lookup"><span data-stu-id="d440b-109">To create a filter on Microsoft search follow these steps:</span></span>

1. <span data-ttu-id="d440b-110">Dans le Centre d’administration Microsoft 365, allez à [Verticals](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/verticals).</span><span class="sxs-lookup"><span data-stu-id="d440b-110">In the Microsoft 365 admin center, go to [Verticals](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/verticals).</span></span>
1. <span data-ttu-id="d440b-111">Créer/modifier le secteur vertical dans lequel vous souhaitez créer le filtre</span><span class="sxs-lookup"><span data-stu-id="d440b-111">Create/Edit the vertical in which you want to create the filter</span></span>
1. <span data-ttu-id="d440b-112">Accédez à l’étape « Filtres » de l’Assistant</span><span class="sxs-lookup"><span data-stu-id="d440b-112">Navigate to the 'Filters' step in the wizard</span></span>
1. <span data-ttu-id="d440b-113">Cliquez sur « Ajouter un filtre » et commencer</span><span class="sxs-lookup"><span data-stu-id="d440b-113">Click on 'Add Filter' and get started</span></span>
1. <span data-ttu-id="d440b-114">Après avoir ajouté des filtres, vous pouvez examiner et enregistrer le secteur vertical.</span><span class="sxs-lookup"><span data-stu-id="d440b-114">After adding filters, you can review and save the vertical.</span></span>

## <a name="things-to-consider"></a><span data-ttu-id="d440b-115">Informations importantes</span><span class="sxs-lookup"><span data-stu-id="d440b-115">Things to consider</span></span>

1. <span data-ttu-id="d440b-116">Des fonctionnalités de filtre supplémentaires existent sur le contenu de connexion.</span><span class="sxs-lookup"><span data-stu-id="d440b-116">Additional filter capabilities exist on connection content.</span></span>

    - <span data-ttu-id="d440b-117">Vous pouvez également créer un filtre sur un alias pour les propriétés source du connecteur</span><span class="sxs-lookup"><span data-stu-id="d440b-117">You can also create filter on an alias to connector source properties</span></span>
    - <span data-ttu-id="d440b-118">Si un secteur vertical possède plusieurs connexions, vous pouvez créer un filtre commun sur ces connexions.</span><span class="sxs-lookup"><span data-stu-id="d440b-118">If a vertical has multiple connections, you can create a common filter across these connections.</span></span> <span data-ttu-id="d440b-119">Pour ce faire, vous pouvez créer le filtre sur un alias commun qui alias les propriétés source entre les différentes connexions.</span><span class="sxs-lookup"><span data-stu-id="d440b-119">This can be done by creating the filter on an common alias which aliases source properties across across the different connections.</span></span> <span data-ttu-id="d440b-120">Par exemple, vous pouvez créer un filtre **Auteur** sur une connexion ServiceNow et Jira en créant des alias comme suit :</span><span class="sxs-lookup"><span data-stu-id="d440b-120">For example you can create an **Author** filter across a ServiceNow and a Jira connection by creating aliases as follows:</span></span>

    | <span data-ttu-id="d440b-121">Connection</span><span class="sxs-lookup"><span data-stu-id="d440b-121">Connection</span></span> | <span data-ttu-id="d440b-122">Propriété</span><span class="sxs-lookup"><span data-stu-id="d440b-122">Property</span></span> | <span data-ttu-id="d440b-123">Alias</span><span class="sxs-lookup"><span data-stu-id="d440b-123">Alias</span></span> |
    | --- | --- | --- |
    | <span data-ttu-id="d440b-124">Service Now</span><span class="sxs-lookup"><span data-stu-id="d440b-124">Service Now</span></span> | <span data-ttu-id="d440b-125">Propriétaire</span><span class="sxs-lookup"><span data-stu-id="d440b-125">Owner</span></span> | <span data-ttu-id="d440b-126">Auteur</span><span class="sxs-lookup"><span data-stu-id="d440b-126">Author</span></span> |
    | <span data-ttu-id="d440b-127">Jira</span><span class="sxs-lookup"><span data-stu-id="d440b-127">Jira</span></span> | <span data-ttu-id="d440b-128">Éditeur</span><span class="sxs-lookup"><span data-stu-id="d440b-128">Publisher</span></span> | <span data-ttu-id="d440b-129">Auteur</span><span class="sxs-lookup"><span data-stu-id="d440b-129">Author</span></span> |

1. <span data-ttu-id="d440b-130">Les filtres existent dans l’étendue d’un secteur vertical.</span><span class="sxs-lookup"><span data-stu-id="d440b-130">Filters exist within the scope of a vertical.</span></span>

    - <span data-ttu-id="d440b-131">Si un filtre est créé dans un secteur vertical au niveau de l’organisation, le filtre n’est visible qu’au niveau de l’organisation.</span><span class="sxs-lookup"><span data-stu-id="d440b-131">If a filter is created in a vertical which is at organizational level, then the filter would only be visible at the organizational level</span></span>
    - <span data-ttu-id="d440b-132">Si un filtre est créé dans un secteur vertical qui se trouve au niveau du site, le filtre n’est visible qu’au niveau du site.</span><span class="sxs-lookup"><span data-stu-id="d440b-132">If a filter is created in a vertical which is at site level, then the filter would only be visible at the site level.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="d440b-133">Limitations connues</span><span class="sxs-lookup"><span data-stu-id="d440b-133">Known Limitations</span></span>

1. <span data-ttu-id="d440b-134">Vous pouvez actuellement créer des filtres uniquement sur les propriétés gérées & type de date.</span><span class="sxs-lookup"><span data-stu-id="d440b-134">You can currently create filters only on string & date type managed properties.</span></span>
1. <span data-ttu-id="d440b-135">Vous ne pouvez pas créer de filtres hiérarchiques.</span><span class="sxs-lookup"><span data-stu-id="d440b-135">You cannot create hierarchical filters.</span></span>

## <a name="resources"></a><span data-ttu-id="d440b-136">Ressources</span><span class="sxs-lookup"><span data-stu-id="d440b-136">Resources</span></span>

[<span data-ttu-id="d440b-137">Gérer des secteurs verticaux et des types de résultats</span><span class="sxs-lookup"><span data-stu-id="d440b-137">Manage verticals and result types</span></span>](customize-search-page.md)
