---
title: Intégrer Power Apps
ms.author: dawholl
author: dawholl
manager: kellis
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
ms.assetid: 1fadcba3-4a7f-4a55-8476-d4e64d49a15f
description: Inclure des applications basées sur le navigateur dans les résultats des signets pour Microsoft Search (recherche Microsoft)
ms.openlocfilehash: 52fa78c54ab6db74ef1e3679d3d32151a3f5ac10
ms.sourcegitcommit: 5df252e6d0bd67bb1b4c59418aceca8369f5fe42
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51031700"
---
# <a name="integrate-power-apps-in-microsoft-search-bookmarks"></a><span data-ttu-id="a2bb4-103">Intégration de Power Apps dans les signets de Recherche Microsoft</span><span class="sxs-lookup"><span data-stu-id="a2bb4-103">Integrate Power Apps in Microsoft Search bookmarks</span></span>
   
<span data-ttu-id="a2bb4-104">Aidez vos utilisateurs à effectuer des tâches, telles que la saisie de congés ou de rapports de dépenses, en intégrant des [applications Microsoft Power Apps](https://products.office.com/business/microsoft-powerapps) existantes dans vos signets Recherche Microsoft.</span><span class="sxs-lookup"><span data-stu-id="a2bb4-104">Help your users complete tasks, like entering vacation time or reporting expenses, by integrating existing [Microsoft Power Apps](https://products.office.com/business/microsoft-powerapps) into your Microsoft Search bookmarks.</span></span> <span data-ttu-id="a2bb4-105">Les applications Power Apps intégrées apparaissent dans un résultat de signet, ce qui élimine la nécessité d’aller sur un autre site ou d’ouvrir un outil distinct, ce qui permet d’économiser du temps et des efforts.</span><span class="sxs-lookup"><span data-stu-id="a2bb4-105">Integrated Power Apps appear within a bookmark result, eliminating the need to go to a different site or open a separate tool, which saves times and effort.</span></span>
  
## <a name="what-are-power-apps"></a><span data-ttu-id="a2bb4-106">Qu’est-ce que Power Apps ?</span><span class="sxs-lookup"><span data-stu-id="a2bb4-106">What are Power Apps?</span></span>

<span data-ttu-id="a2bb4-107">[Power Apps est](https://products.office.com/business/microsoft-powerapps) un service qui vous permet de créer des applications métier qui s’exécutent dans un navigateur ou sur un téléphone ou une tablette sans expérience de codage requise.</span><span class="sxs-lookup"><span data-stu-id="a2bb4-107">[Power Apps](https://products.office.com/business/microsoft-powerapps) is a service that lets you build business apps that run in a browser or on a phone or tablet with no coding experience required.</span></span> <span data-ttu-id="a2bb4-108">En savoir plus :</span><span class="sxs-lookup"><span data-stu-id="a2bb4-108">Learn more:</span></span>
  
- [<span data-ttu-id="a2bb4-109">Formation guidée</span><span class="sxs-lookup"><span data-stu-id="a2bb4-109">Guided Learning</span></span>](/learn/browse/?products=powerapps)
    
- [<span data-ttu-id="a2bb4-110">Documentation</span><span class="sxs-lookup"><span data-stu-id="a2bb4-110">Documentation</span></span>](/powerapps/)
    
## <a name="add-a-power-app-to-a-bookmark"></a><span data-ttu-id="a2bb4-111">Ajouter une application Power App à un signet</span><span class="sxs-lookup"><span data-stu-id="a2bb4-111">Add a Power App to a bookmark</span></span>

<span data-ttu-id="a2bb4-112">[Power Apps( fonctionne dans n’importe quel navigateur et sur n’importe quel appareil et https://products.office.com/business/microsoft-powerapps) prend moins d’une minute pour l’ajouter.</span><span class="sxs-lookup"><span data-stu-id="a2bb4-112">[Power Apps(https://products.office.com/business/microsoft-powerapps) work in any browser and on any device and take less than a minute to add.</span></span>
  
1. <span data-ttu-id="a2bb4-113">[Recherchez l’ID de l’application Power App](/powerapps/maker/canvas-apps/get-sessionid#get-an-app-id) que vous souhaitez intégrer.</span><span class="sxs-lookup"><span data-stu-id="a2bb4-113">[Find the App ID for the Power App](/powerapps/maker/canvas-apps/get-sessionid#get-an-app-id) you want to integrate.</span></span>
    
2. <span data-ttu-id="a2bb4-114">Dans le Centre d’administration Microsoft 365, go to **Bookmarks**. [](https://admin.microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="a2bb4-114">In the Microsoft 365 [admin center](https://admin.microsoft.com), go to **Bookmarks**.</span></span>
    
3. <span data-ttu-id="a2bb4-115">Ajoutez un signet ou recherchez un signet existant à ajouter à une application Power App.</span><span class="sxs-lookup"><span data-stu-id="a2bb4-115">Add a bookmark or find an existing bookmark that you want to add a Power App to.</span></span>
    
4. <span data-ttu-id="a2bb4-116">Dans les paramètres de signet, **sélectionnez Power App,** puis **ajoutez une application Power App.**</span><span class="sxs-lookup"><span data-stu-id="a2bb4-116">In the bookmark settings, select **Power App**, and then select **Add a Power App**.</span></span>
    
5. <span data-ttu-id="a2bb4-117">Entrez ou collez l’ID de l’application.</span><span class="sxs-lookup"><span data-stu-id="a2bb4-117">Enter or paste the App ID.</span></span>
    
    <span data-ttu-id="a2bb4-118">La hauteur et la largeur sont automatiquement ajoutées.</span><span class="sxs-lookup"><span data-stu-id="a2bb4-118">The height and width are automatically added.</span></span> <span data-ttu-id="a2bb4-119">Les signets peuvent prendre en charge les orientations portrait et paysage, mais actuellement la taille ne peut pas être modifiée.</span><span class="sxs-lookup"><span data-stu-id="a2bb4-119">Bookmarks can support both portrait and landscape orientations, but currently the size can't be changed.</span></span>
    
6. <span data-ttu-id="a2bb4-120">L’aperçu de signet montre l’apparition de Power App dans le résultat du signet.</span><span class="sxs-lookup"><span data-stu-id="a2bb4-120">The bookmark preview shows how the Power App will appear in the bookmark result.</span></span>
    
    <span data-ttu-id="a2bb4-121">Power App dans la prévisualisation est entièrement fonctionnelle pour faciliter le test et l’utilisation.</span><span class="sxs-lookup"><span data-stu-id="a2bb4-121">The Power App in the preview is fully functional to make it easy to test and use.</span></span>
    
7. <span data-ttu-id="a2bb4-122">Sélectionnez **Publier**.</span><span class="sxs-lookup"><span data-stu-id="a2bb4-122">Select **Publish**.</span></span>
    
<span data-ttu-id="a2bb4-123">Lorsqu’un utilisateur microsoft search (recherche Microsoft) autorisé recherche sur [Bing](https://Bing.com) l’un des mots clés du signet ou des mots clés réservés, l’application Power apparaît dans le résultat du signet.</span><span class="sxs-lookup"><span data-stu-id="a2bb4-123">When an authorized Microsoft Search user searches on [Bing](https://Bing.com) for any of the bookmark's keywords or reserved keywords, the Power App will appear in the bookmark result.</span></span>