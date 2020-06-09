---
title: Aperçu des connecteurs
ms.author: mounika.narayanan
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
description: Découvrez l’aperçu des connecteurs Microsoft Graph pour Microsoft Search.
ms.openlocfilehash: 4bcd8360957be69bc701e8b356cd222de32bfc5f
ms.sourcegitcommit: 64eea81f8c1db9ee955013462a7b51612fb7d0b7
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/08/2020
ms.locfileid: "44604382"
---
# <a name="microsoft-graph-connectors-preview"></a><span data-ttu-id="e2e4c-103">Aperçu des connecteurs Microsoft Graph</span><span class="sxs-lookup"><span data-stu-id="e2e4c-103">Microsoft Graph connectors preview</span></span>

<span data-ttu-id="e2e4c-104">Les connecteurs Microsoft Graph et les API Microsoft Search (requête et index) sont actuellement en état d’aperçu.</span><span class="sxs-lookup"><span data-stu-id="e2e4c-104">Microsoft Graph connectors and Microsoft Search APIs (query and index) are currently in preview status.</span></span> <span data-ttu-id="e2e4c-105">Pour accéder à la fonctionnalité connecteurs, vous devez activer l’option publication ciblée dans votre client.</span><span class="sxs-lookup"><span data-stu-id="e2e4c-105">To gain access to connectors functionality, you must turn on the Targeted release option in your tenant.</span></span> <span data-ttu-id="e2e4c-106">Il s’agit d’une préversion préliminaire et il n’existe aucune garantie de niveau de service.</span><span class="sxs-lookup"><span data-stu-id="e2e4c-106">This is an early preview, and there's no service level guarantee.</span></span> <span data-ttu-id="e2e4c-107">Nous encourageons les clients à essayer les fonctionnalités des connecteurs et à fournir des commentaires.</span><span class="sxs-lookup"><span data-stu-id="e2e4c-107">We encourage customers to try connectors functionality and provide feedback.</span></span> <span data-ttu-id="e2e4c-108">Nous vous déconseillons d’utiliser des connecteurs à des fins de production pendant la période d’évaluation.</span><span class="sxs-lookup"><span data-stu-id="e2e4c-108">We don’t recommend using connectors for production purposes during the preview period.</span></span>

## <a name="set-up-targeted-release"></a><span data-ttu-id="e2e4c-109">Configurer la version ciblée</span><span class="sxs-lookup"><span data-stu-id="e2e4c-109">Set up Targeted release</span></span>

<span data-ttu-id="e2e4c-110">Pour tester les connecteurs, vous devez disposer de l’option de **publication ciblée** définie pour tous les utilisateurs de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="e2e4c-110">To try connectors, you must have the **Targeted release** option set for all users in your organization.</span></span> <span data-ttu-id="e2e4c-111">Pour en savoir plus sur l’option de publication ciblée et sur la façon de la définir, consultez [la rubrique Configurer les options de publication standard ou ciblée dans Office 365](https://docs.microsoft.com/office365/admin/manage/release-options-in-office-365?view=o365-worldwide).</span><span class="sxs-lookup"><span data-stu-id="e2e4c-111">To learn more about the Targeted release option and how to set it, see [Set up the Standard or Targeted release options in Office 365](https://docs.microsoft.com/office365/admin/manage/release-options-in-office-365?view=o365-worldwide).</span></span>

## <a name="choose-a-preview-environment"></a><span data-ttu-id="e2e4c-112">Choisir un environnement d’aperçu</span><span class="sxs-lookup"><span data-stu-id="e2e4c-112">Choose a preview environment</span></span>

<span data-ttu-id="e2e4c-113">Pour tester les connecteurs, les API d’indexation et les API de recherche, nous vous recommandons ces deux méthodes :</span><span class="sxs-lookup"><span data-stu-id="e2e4c-113">To try connectors, indexing APIs, and search APIs, we recommend these two methods:</span></span>

1. <span data-ttu-id="e2e4c-114">**Testez le client**.</span><span class="sxs-lookup"><span data-stu-id="e2e4c-114">**Test tenant**.</span></span>  <span data-ttu-id="e2e4c-115">Nous vous encourageons à utiliser un locataire de test pour essayer l’aperçu des connecteurs Microsoft Graph.</span><span class="sxs-lookup"><span data-stu-id="e2e4c-115">We encourage you to use a test tenant to try the Microsoft Graph connectors preview.</span></span>

2. <span data-ttu-id="e2e4c-116">**Collection de sites de test**.</span><span class="sxs-lookup"><span data-stu-id="e2e4c-116">**Test site collection**.</span></span> <span data-ttu-id="e2e4c-117">Si vous n’avez pas de client de test, vous pouvez créer une collection de sites de test pour tester la fonctionnalité de connecteurs.</span><span class="sxs-lookup"><span data-stu-id="e2e4c-117">If you don't have a test tenant, you can create a test site collection to try out connectors functionality.</span></span> <span data-ttu-id="e2e4c-118">Pour afficher les résultats des connecteurs sans impact sur les pages de recherche n’importe où dans votre organisation, personnalisez l’expérience de recherche de cette collection de sites uniquement.</span><span class="sxs-lookup"><span data-stu-id="e2e4c-118">To show results from connectors without impacting the search pages anywhere else in your organization, customize the search experience of only that site collection.</span></span>

## <a name="preview-limitations"></a><span data-ttu-id="e2e4c-119">Limitations de l’aperçu</span><span class="sxs-lookup"><span data-stu-id="e2e4c-119">Preview limitations</span></span>

<span data-ttu-id="e2e4c-120">La version d’évaluation présente les limitations suivantes :</span><span class="sxs-lookup"><span data-stu-id="e2e4c-120">The preview release has the following limitations:</span></span>

* <span data-ttu-id="e2e4c-121">Le débit de l’ingestion est limité à quatre éléments par seconde.</span><span class="sxs-lookup"><span data-stu-id="e2e4c-121">Ingestion throughput is throttled at about four items per second.</span></span>

* <span data-ttu-id="e2e4c-122">Il n’existe pas de prise en charge des mises à jour de schéma.</span><span class="sxs-lookup"><span data-stu-id="e2e4c-122">There's no support for schema updates.</span></span> <span data-ttu-id="e2e4c-123">Une fois que vous avez créé une configuration de connexion, il n’existe aucun moyen de mettre à jour le schéma.</span><span class="sxs-lookup"><span data-stu-id="e2e4c-123">After you create a connection setup, there's no way to update the schema.</span></span> <span data-ttu-id="e2e4c-124">Vous pouvez supprimer et recréer la connexion uniquement.</span><span class="sxs-lookup"><span data-stu-id="e2e4c-124">You can only delete and re-create the connection.</span></span>

* <span data-ttu-id="e2e4c-125">Le contenu indexé apparaît uniquement dans la page des résultats de recherche sous un secteur vertical personnalisé.</span><span class="sxs-lookup"><span data-stu-id="e2e4c-125">Indexed content only shows up in the search results page under a custom vertical.</span></span> <span data-ttu-id="e2e4c-126">Cette restriction s’applique au contenu avec des types personnalisés.</span><span class="sxs-lookup"><span data-stu-id="e2e4c-126">This restriction applies to content with custom types.</span></span>

* <span data-ttu-id="e2e4c-127">Toute connexion que vous configurez pendant la période d’aperçu doit être supprimée et recréée.</span><span class="sxs-lookup"><span data-stu-id="e2e4c-127">Any connection you set up during the preview period might need to be deleted and re-created.</span></span> <span data-ttu-id="e2e4c-128">Ces connexions ne fonctionneront plus si elles sont incompatibles avec les modifications apportées à l’amélioration du produit.</span><span class="sxs-lookup"><span data-stu-id="e2e4c-128">Those connections won't work anymore if they're incompatible with changes made to improve the product.</span></span>

* <span data-ttu-id="e2e4c-129">Il existe une limite de connexions.</span><span class="sxs-lookup"><span data-stu-id="e2e4c-129">There's a connections limit.</span></span> <span data-ttu-id="e2e4c-130">Chaque client peut créer jusqu’à 10 connexions.</span><span class="sxs-lookup"><span data-stu-id="e2e4c-130">Each tenant can create up to 10 connections.</span></span>

* <span data-ttu-id="e2e4c-131">Taille du référentiel source.</span><span class="sxs-lookup"><span data-stu-id="e2e4c-131">Source repository size.</span></span> <span data-ttu-id="e2e4c-132">Nous vous recommandons de prévisualiser les connecteurs avec un référentiel source d’environ 200 000 éléments, car il s’agit de notre limite d’étendue de recherche testée.</span><span class="sxs-lookup"><span data-stu-id="e2e4c-132">We recommend that you preview connectors with a source repository of about 200,000 items as this is our tested search scale limit.</span></span> <span data-ttu-id="e2e4c-133">Nous travaillons sur l’amélioration des performances de la recherche et nous prévoyons de prendre en charge des référentiels plus volumineux dans un futur proche.</span><span class="sxs-lookup"><span data-stu-id="e2e4c-133">We are working on improving the performance of search, and we expect to support for larger repository sizes in the near future.</span></span>

* <span data-ttu-id="e2e4c-134">La modification de la prise en charge de la connexion n’est pas disponible.</span><span class="sxs-lookup"><span data-stu-id="e2e4c-134">Edit support for connection is not available.</span></span> <span data-ttu-id="e2e4c-135">Une fois que la connexion a été créée, vous ne pouvez pas la modifier ni la modifier.</span><span class="sxs-lookup"><span data-stu-id="e2e4c-135">Once the connection has been created, you cannot edit or change it.</span></span> <span data-ttu-id="e2e4c-136">Si vous devez modifier des détails, vous devez supprimer et recréer la connexion.</span><span class="sxs-lookup"><span data-stu-id="e2e4c-136">If you need to change any details, you must delete and recreate the connection.</span></span>

* <span data-ttu-id="e2e4c-137">Le contenu du connecteur ne peut être recherché que sur des secteurs verticaux personnalisés.</span><span class="sxs-lookup"><span data-stu-id="e2e4c-137">Connector content can only be searched on custom verticals.</span></span>

* <span data-ttu-id="e2e4c-138">Le contenu du connecteur à partir d’une seule connexion peut être affiché dans chaque vertical personnalisé et nécessite une création de type de résultat.</span><span class="sxs-lookup"><span data-stu-id="e2e4c-138">Connector content from only one connection can be displayed in each custom vertical and requires result type creation.</span></span>
