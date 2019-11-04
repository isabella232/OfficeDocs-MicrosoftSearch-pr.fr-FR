---
title: Aperçu des connecteurs
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
description: Découvrez l’aperçu des connecteurs Microsoft Graph pour Microsoft Search.
ms.openlocfilehash: 025b4f0d7ad4ecae2909f02687c66938d931a2fc
ms.sourcegitcommit: bfcab9d42e93addccd1e3875b41bc9cc1b6986cc
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/04/2019
ms.locfileid: "37949750"
---
# <a name="microsoft-graph-connectors-preview"></a><span data-ttu-id="f46ef-103">Aperçu des connecteurs Microsoft Graph</span><span class="sxs-lookup"><span data-stu-id="f46ef-103">Microsoft Graph connectors preview</span></span>

<span data-ttu-id="f46ef-104">Les connecteurs Microsoft Graph, les API d’indexation et les API de recherche sont actuellement en version préliminaire.</span><span class="sxs-lookup"><span data-stu-id="f46ef-104">Microsoft Graph connectors, indexing APIs, and search APIs are currently in preview.</span></span> <span data-ttu-id="f46ef-105">Pour accéder à la fonctionnalité connecteurs, vous devez demander à rejoindre le programme d’aperçu en envoyant le <a href="https://forms.office.com/Pages/ResponsePage.aspx?id=v4j5cvGGr0GRqy180BHbRxWYgu82J_RFnMMATAS6_chUNVYwNU1CMDNZUDBSSDZKWVo2RDJDRjRLQi4u" target="_blank">formulaire d’aperçu des connecteurs Microsoft Graph</a>.</span><span class="sxs-lookup"><span data-stu-id="f46ef-105">To gain access to connectors functionality, you must request to join the preview program by submitting the <a href="https://forms.office.com/Pages/ResponsePage.aspx?id=v4j5cvGGr0GRqy180BHbRxWYgu82J_RFnMMATAS6_chUNVYwNU1CMDNZUDBSSDZKWVo2RDJDRjRLQi4u" target="_blank">Microsoft Graph Connectors Preview Sign up Form</a>.</span></span> <span data-ttu-id="f46ef-106">Il s’agit d’une préversion préliminaire et il n’existe aucune garantie de niveau de service.</span><span class="sxs-lookup"><span data-stu-id="f46ef-106">This is an early preview, and there is no service level guarantee.</span></span> <span data-ttu-id="f46ef-107">Nous encourageons les clients à essayer les fonctionnalités des connecteurs et à fournir des commentaires.</span><span class="sxs-lookup"><span data-stu-id="f46ef-107">We encourage customers to try connectors functionality and provide feedback.</span></span> <span data-ttu-id="f46ef-108">Nous vous déconseillons d’utiliser des connecteurs à des fins de production pendant la période d’évaluation.</span><span class="sxs-lookup"><span data-stu-id="f46ef-108">We don’t recommend using connectors for production purposes during the preview period.</span></span>

## <a name="set-up-targeted-release"></a><span data-ttu-id="f46ef-109">Configurer la version ciblée</span><span class="sxs-lookup"><span data-stu-id="f46ef-109">Set up targeted release</span></span>
<span data-ttu-id="f46ef-110">Pour tester les connecteurs, vous devez disposer de l’option de **publication ciblée** définie pour tous les utilisateurs de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="f46ef-110">To try connectors, you must have the **Targeted release** option set for all users in your organization.</span></span> <span data-ttu-id="f46ef-111">La configuration requise de la version ciblée n’est pas l’un des environnements d’aperçu suivants que vous choisissez.</span><span class="sxs-lookup"><span data-stu-id="f46ef-111">The Targeted release requirement applies no matter which of the following preview environments you choose.</span></span>
<span data-ttu-id="f46ef-112">Pour en savoir plus sur l’option de publication ciblée et sur la façon de la définir, consultez <a href="https://docs.microsoft.com/office365/admin/manage/release-options-in-office-365?view=o365-worldwide" target="_blank">la rubrique Configurer les options de publication standard ou ciblée dans Office 365</a>.</span><span class="sxs-lookup"><span data-stu-id="f46ef-112">To learn more about the Targeted release option and how to set it, see <a href="https://docs.microsoft.com/office365/admin/manage/release-options-in-office-365?view=o365-worldwide" target="_blank">Set up the Standard or Targeted release options in Office 365</a>.</span></span>

## <a name="choose-a-preview-environment"></a><span data-ttu-id="f46ef-113">Choisir un environnement d’aperçu</span><span class="sxs-lookup"><span data-stu-id="f46ef-113">Choose a preview environment</span></span> 
<span data-ttu-id="f46ef-114">Pour tester les connecteurs, les API d’indexation et les API de recherche, nous vous recommandons ces deux méthodes :</span><span class="sxs-lookup"><span data-stu-id="f46ef-114">To try connectors, indexing APIs, and search APIs, we recommend these two methods:</span></span>
1. <span data-ttu-id="f46ef-115">**Testez le client**.</span><span class="sxs-lookup"><span data-stu-id="f46ef-115">**Test tenant**.</span></span>  <span data-ttu-id="f46ef-116">Nous vous encourageons à utiliser un locataire de test pour essayer l’aperçu des connecteurs Microsoft Graph.</span><span class="sxs-lookup"><span data-stu-id="f46ef-116">We encourage you to use a test tenant to try the Microsoft Graph connectors preview.</span></span>
2. <span data-ttu-id="f46ef-117">**Collection de sites de test**.</span><span class="sxs-lookup"><span data-stu-id="f46ef-117">**Test site collection**.</span></span> <span data-ttu-id="f46ef-118">Si vous n’avez pas de client de test, vous pouvez créer une collection de sites de test pour tester la fonctionnalité de connecteurs.</span><span class="sxs-lookup"><span data-stu-id="f46ef-118">If you don't have a test tenant, you can create a test site collection to try out connectors functionality.</span></span> <span data-ttu-id="f46ef-119">Pour afficher les résultats des connecteurs sans impact sur les pages de recherche n’importe où dans votre organisation, personnalisez l’expérience de recherche de cette collection de sites uniquement.</span><span class="sxs-lookup"><span data-stu-id="f46ef-119">To show results from connectors without impacting the search pages anywhere else in your organization, customize the search experience of only that site collection.</span></span>

## <a name="preview-limitations"></a><span data-ttu-id="f46ef-120">Limitations de l’aperçu</span><span class="sxs-lookup"><span data-stu-id="f46ef-120">Preview limitations</span></span>
<span data-ttu-id="f46ef-121">La version d’évaluation présente les limitations suivantes :</span><span class="sxs-lookup"><span data-stu-id="f46ef-121">The preview release has the following limitations:</span></span>
* <span data-ttu-id="f46ef-122">Le débit de l’ingestion est limité à quatre éléments par seconde.</span><span class="sxs-lookup"><span data-stu-id="f46ef-122">Ingestion throughput is throttled at about four items per second.</span></span>
* <span data-ttu-id="f46ef-123">Il n’existe pas de prise en charge des mises à jour de schéma.</span><span class="sxs-lookup"><span data-stu-id="f46ef-123">There's no support for schema updates.</span></span> <span data-ttu-id="f46ef-124">Une fois que vous avez créé une configuration de connexion, il n’existe aucun moyen de mettre à jour le schéma.</span><span class="sxs-lookup"><span data-stu-id="f46ef-124">After you create a connection setup, there's no way to update the schema.</span></span> <span data-ttu-id="f46ef-125">Vous pouvez supprimer et recréer la connexion uniquement.</span><span class="sxs-lookup"><span data-stu-id="f46ef-125">You can only delete and re-create the connection.</span></span>
* <span data-ttu-id="f46ef-126">Le contenu indexé apparaît uniquement dans la page des résultats de recherche sous un secteur vertical personnalisé.</span><span class="sxs-lookup"><span data-stu-id="f46ef-126">Indexed content only shows up in the search results page under a custom vertical.</span></span> <span data-ttu-id="f46ef-127">Cette restriction s’applique au contenu avec des types personnalisés.</span><span class="sxs-lookup"><span data-stu-id="f46ef-127">This restriction applies to content with custom types.</span></span>
* <span data-ttu-id="f46ef-128">Avant la mise à disposition générale, toute connexion que vous configurez pendant la période d’aperçu doit être supprimée et recréée.</span><span class="sxs-lookup"><span data-stu-id="f46ef-128">Before general availability, any connection you set up during the preview period may need to be deleted and re-created.</span></span> <span data-ttu-id="f46ef-129">Ces connexions ne fonctionneront plus si elles sont incompatibles avec les modifications apportées à l’amélioration du produit.</span><span class="sxs-lookup"><span data-stu-id="f46ef-129">Those connections won't work anymore if they are incompatible with changes made to improve the product.</span></span>
* <span data-ttu-id="f46ef-130">Limite de connexions.</span><span class="sxs-lookup"><span data-stu-id="f46ef-130">Connections limit.</span></span> <span data-ttu-id="f46ef-131">Chaque client peut créer jusqu’à 10 connexions.</span><span class="sxs-lookup"><span data-stu-id="f46ef-131">Each tenant can create up to 10 connections.</span></span>