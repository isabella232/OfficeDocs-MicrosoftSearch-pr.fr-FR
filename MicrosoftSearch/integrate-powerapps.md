---
title: Intégrer des PowerApps
ms.author: dawholl
author: dawholl
manager: kellis
ms.date: 12/18/2018
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
ms.assetid: 1fadcba3-4a7f-4a55-8476-d4e64d49a15f
ROBOTS: NOINDEX
description: Incluez des applications de navigateur dans les résultats de signet pour la fonctionnalité Recherche Microsoft
ms.openlocfilehash: 1f4cf7512ee176015537be2fbe2f59429cde6578
ms.sourcegitcommit: fe7f3dae4edba97071a4d127e8a27bdf4fa00d81
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/05/2019
ms.locfileid: "34727968"
---
# <a name="integrate-powerapps"></a><span data-ttu-id="571e3-103">Intégrer des PowerApps</span><span class="sxs-lookup"><span data-stu-id="571e3-103">Integrate PowerApps</span></span>

> [!IMPORTANT]
> <span data-ttu-id="571e3-104">Cet article s’applique à la fonctionnalité Recherche Microsoft dans le portail d’administration Bing.</span><span class="sxs-lookup"><span data-stu-id="571e3-104">This article applies to the Microsoft Search in Bing admin portal.</span></span> <span data-ttu-id="571e3-105">Nous déplaçons le portail vers le centre d’administration Microsoft 365. Ensuite, nous le supprimerons.</span><span class="sxs-lookup"><span data-stu-id="571e3-105">We’re moving the portal to the Microsoft 365 admin center, and then it will be removed.</span></span> <span data-ttu-id="571e3-106">Pour commencer, nous vous suggérons d’utiliser le centre d’administration Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="571e3-106">We recommend that you use the Microsoft 365 admin center to get started.</span></span> <span data-ttu-id="571e3-107">[Vue d’ensemble de la fonctionnalité Recherche Microsoft](overview-microsoft-search.md).</span><span class="sxs-lookup"><span data-stu-id="571e3-107">[Overview of Microsoft Search](overview-microsoft-search.md)</span></span>
    
<span data-ttu-id="571e3-108">Aidez vos utilisateurs à accomplir des tâches telles que saisir une période de vacances ou une note de frais en intégrant des PowerApps existants dans vos signets.</span><span class="sxs-lookup"><span data-stu-id="571e3-108">Help your users complete tasks, such as entering vacation time or reporting expenses, by adding existing PowerApps to your bookmarks.</span></span> <span data-ttu-id="571e3-109">Les PowerApps intégrés apparaissent dans un résultat de signet, ce qui élimine le besoin d’accéder à un autre site ou d’ouvrir un outil distinct, les heures enregistrés ainsi que vos efforts.</span><span class="sxs-lookup"><span data-stu-id="571e3-109">Integrated PowerApps appear within a bookmark result, eliminating the need to go to a different site or open a separate tool, which saves times and effort.</span></span>
  
## <a name="what-are-powerapps"></a><span data-ttu-id="571e3-110">Quelles sont les PowerApps ?</span><span class="sxs-lookup"><span data-stu-id="571e3-110">What are PowerApps?</span></span>

<span data-ttu-id="571e3-111">PowerApps est un service qui vous permet de créer des applications métier qui s’exécutent dans un navigateur ou sur un téléphone ou une tablette avec aucune expérience codage requise.</span><span class="sxs-lookup"><span data-stu-id="571e3-111">PowerApps is a service that lets you build business apps that run in a browser or on a phone or tablet with no coding experience required.</span></span> <span data-ttu-id="571e3-112">En savoir plus :</span><span class="sxs-lookup"><span data-stu-id="571e3-112">Learn more:</span></span>
  
- <span data-ttu-id="571e3-113">
  [Formation guidée](https://docs.microsoft.com/fr-FR/learn/browse/?products=powerapps)</span><span class="sxs-lookup"><span data-stu-id="571e3-113">[Guided Learning](https://docs.microsoft.com/en-us/learn/browse/?products=powerapps)</span></span>
    
- <span data-ttu-id="571e3-114">
  [Documentation](https://docs.microsoft.com/fr-FR/powerapps/)</span><span class="sxs-lookup"><span data-stu-id="571e3-114">[Documentation](https://docs.microsoft.com/en-us/powerapps/)</span></span>
    
## <a name="add-a-powerapp-to-a-bookmark"></a><span data-ttu-id="571e3-115">Ajouter un PowerApp à un signet</span><span class="sxs-lookup"><span data-stu-id="571e3-115">Add a PowerApp to a bookmark</span></span>

<span data-ttu-id="571e3-116">Les applications PowerApps fonctionnent dans n’importe quel navigateur ainsi que sur tout appareil, et leur ajout prend moins d’une minute.</span><span class="sxs-lookup"><span data-stu-id="571e3-116">PowerApps work in any browser and on any device and take less than a minute to add.</span></span>
  
1. <span data-ttu-id="571e3-117">
  [Trouvez l’ID du PowerApp](https://docs.microsoft.com/fr-FR/powerapps/maker/canvas-apps/get-sessionid#get-an-app-id) que vous souhaitez intégrer.</span><span class="sxs-lookup"><span data-stu-id="571e3-117">Find the [App ID for the PowerApp](https://docs.microsoft.com/en-us/powerapps/maker/canvas-apps/get-sessionid#get-an-app-id) that you want to add.</span></span> 
    
2. <span data-ttu-id="571e3-118">Dans le portail d’administration de la fonctionnalité Recherche Microsoft, accédez à **Favoris**.</span><span class="sxs-lookup"><span data-stu-id="571e3-118">In the Microsoft Search Admin portal, go to **Bookmarks**</span></span>
    
3. <span data-ttu-id="571e3-119">Ajoutez un signet ou rechercher un signet existant auquel vous souhaitez ajouter un PowerApp.</span><span class="sxs-lookup"><span data-stu-id="571e3-119">Add a bookmark or find an existing bookmark that you want to add a PowerApp to.</span></span>
    
4. <span data-ttu-id="571e3-120">Dans les paramètres du signet, cliquez sur **PowerApp**, puis sur **Ajouter un PowerApp**.</span><span class="sxs-lookup"><span data-stu-id="571e3-120">In Bookmark settings, select Power App, and then Add a Power App.</span></span>
    
5. <span data-ttu-id="571e3-121">Entrez ou collez l’ID de l’application.</span><span class="sxs-lookup"><span data-stu-id="571e3-121">Enter or paste the App ID.</span></span>
    
    <span data-ttu-id="571e3-122">La hauteur et la largeur sont ajoutées automatiquement.</span><span class="sxs-lookup"><span data-stu-id="571e3-122">The height and width are automatically adjusted.</span></span> <span data-ttu-id="571e3-123">Les signets peuvent prendre en charge les orientations portrait et paysage mais il n’est actuellement pas possible de modifier la taille.</span><span class="sxs-lookup"><span data-stu-id="571e3-123">Bookmarks can support both portrait and landscape orientations, but currently the size can't be changed.</span></span>
    
6. <span data-ttu-id="571e3-124">L’aperçu du signet montre comment le PowerApp apparaîtra dans le résultat de signet.</span><span class="sxs-lookup"><span data-stu-id="571e3-124">The bookmark preview shows how the PowerApp will appear in the bookmark result</span></span>
    
    <span data-ttu-id="571e3-125">PowerApp dans l’aperçu est pleinement fonctionnel pour en faciliter le test et l’utilisation.</span><span class="sxs-lookup"><span data-stu-id="571e3-125">The PowerApp in the preview is fully functional to make it easy to test and use.</span></span>
    
7. <span data-ttu-id="571e3-126">Cliquez sur**Publier**.</span><span class="sxs-lookup"><span data-stu-id="571e3-126">Click **Publish**.</span></span>
    
<span data-ttu-id="571e3-127">Quand un utilisateur autorisé de la fonctionnalité Recherche Microsoft cherche sur Bing des mots clés ou mots clés réservés d’un des signets, le PowerApp s’affiche dans le résultat de signet.</span><span class="sxs-lookup"><span data-stu-id="571e3-127">When an authorized Microsoft Search user searches on Bing for any of the bookmark's keywords or reserved keywords, the PowerApp will appear in the bookmark result.</span></span>

  

