---
title: Intégrer PowerApps
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
description: Inclure des applications basées sur le navigateur dans les résultats de signets pour Microsoft Search
ms.openlocfilehash: d8d9d099848e719c86e0f3cadee330263566d243
ms.sourcegitcommit: a5fd9d4f46bbb7c539630735ac16e0c786939e5d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/01/2019
ms.locfileid: "33508824"
---
# <a name="integrate-powerapps"></a><span data-ttu-id="ad4b7-103">Intégrer PowerApps</span><span class="sxs-lookup"><span data-stu-id="ad4b7-103">Integrate PowerApps</span></span>

<span data-ttu-id="ad4b7-104">Aidez vos utilisateurs à effectuer des tâches, par exemple en entrant des heures de vacances ou des rapports de frais en intégrant les PowerApp existants dans vos signets.</span><span class="sxs-lookup"><span data-stu-id="ad4b7-104">Help your users complete tasks, such as entering vacation time or reporting expenses by integrating existing PowerApps into your bookmarks.</span></span> <span data-ttu-id="ad4b7-105">Les PowerApp intégrés s'affichent dans un résultat de signet, ce qui évite d'avoir à accéder à un autre site ou d'ouvrir un outil séparé, ce qui permet de gagner du temps et de l'énergie.</span><span class="sxs-lookup"><span data-stu-id="ad4b7-105">Integrated PowerApps appear within a bookmark result, eliminating the need to go to a different site or open a separate tool, which saves times and effort.</span></span>
  
## <a name="what-are-powerapps"></a><span data-ttu-id="ad4b7-106">Qu'est-ce que les PowerApp?</span><span class="sxs-lookup"><span data-stu-id="ad4b7-106">What are PowerApps?</span></span>

<span data-ttu-id="ad4b7-107">PowerApps est un service qui vous permet de créer des applications métier qui s'exécutent dans un navigateur ou sur un téléphone ou une tablette sans intervention de codage.</span><span class="sxs-lookup"><span data-stu-id="ad4b7-107">PowerApps is a service that lets you build business apps that run in a browser or on a phone or tablet with no coding experience required.</span></span> <span data-ttu-id="ad4b7-108">En savoir plus :</span><span class="sxs-lookup"><span data-stu-id="ad4b7-108">Learn more:</span></span>
  
- [<span data-ttu-id="ad4b7-109">Formation guidée</span><span class="sxs-lookup"><span data-stu-id="ad4b7-109">Guided Learning</span></span>](https://docs.microsoft.com/en-us/learn/browse/?products=powerapps)
    
- [<span data-ttu-id="ad4b7-110">Documentation</span><span class="sxs-lookup"><span data-stu-id="ad4b7-110">Documentation</span></span>](https://docs.microsoft.com/en-us/powerapps/)
    
## <a name="add-a-powerapp-to-a-bookmark"></a><span data-ttu-id="ad4b7-111">Ajouter un «PowerApp» à un signet</span><span class="sxs-lookup"><span data-stu-id="ad4b7-111">Add a PowerApp to a bookmark</span></span>

<span data-ttu-id="ad4b7-112">Les PowerApp fonctionnent dans n'importe quel navigateur et sur n'importe quel appareil et prennent moins d'une minute pour les ajouter.</span><span class="sxs-lookup"><span data-stu-id="ad4b7-112">PowerApps work in any browser and on any device and take less than a minute to add.</span></span>
  
1. <span data-ttu-id="ad4b7-113">[Trouver l'ID de l'application pour le PowerApp](https://docs.microsoft.com/en-us/powerapps/maker/canvas-apps/get-sessionid#get-an-app-id) que vous souhaitez intégrer</span><span class="sxs-lookup"><span data-stu-id="ad4b7-113">[Find the App ID for the PowerApp](https://docs.microsoft.com/en-us/powerapps/maker/canvas-apps/get-sessionid#get-an-app-id) you want to integrate</span></span> 
    
2. <span data-ttu-id="ad4b7-114">Dans le portail Microsoft SearchAdmin, accédez à **signets** .</span><span class="sxs-lookup"><span data-stu-id="ad4b7-114">In the Microsoft SearchAdmin portal, go to **Bookmarks**</span></span>
    
3. <span data-ttu-id="ad4b7-115">Ajouter un signet ou Rechercher un signet existant auquel vous souhaitez ajouter un PowerApp</span><span class="sxs-lookup"><span data-stu-id="ad4b7-115">Add a bookmark or find an existing bookmark that you want to add a PowerApp to</span></span>
    
4. <span data-ttu-id="ad4b7-116">Dans les paramètres de signet, cliquez sur **application d'alimentation**, puis sur **Ajouter une application d'alimentation**</span><span class="sxs-lookup"><span data-stu-id="ad4b7-116">In the bookmark settings, click **Power App**, and then click **Add a Power App**</span></span>
    
5. <span data-ttu-id="ad4b7-117">Entrer ou coller l'ID de l'application</span><span class="sxs-lookup"><span data-stu-id="ad4b7-117">Enter or paste the App ID</span></span>
    
    <span data-ttu-id="ad4b7-118">La hauteur et la largeur sont automatiquement ajoutées.</span><span class="sxs-lookup"><span data-stu-id="ad4b7-118">The height and width are automatically added.</span></span> <span data-ttu-id="ad4b7-119">Les signets peuvent prendre en charge les orientations portrait et paysage, mais la taille ne peut pas être modifiée.</span><span class="sxs-lookup"><span data-stu-id="ad4b7-119">Bookmarks can support both portrait and landscape orientations, but currently the size can't be changed.</span></span>
    
6. <span data-ttu-id="ad4b7-120">L'aperçu des signets montre comment l'PowerApp apparaîtra dans le résultat du signet.</span><span class="sxs-lookup"><span data-stu-id="ad4b7-120">The bookmark preview shows how the PowerApp will appear in the bookmark result</span></span>
    
    <span data-ttu-id="ad4b7-121">Le PowerApp dans la version d'évaluation est entièrement fonctionnel pour faciliter le test et l'utilisation.</span><span class="sxs-lookup"><span data-stu-id="ad4b7-121">The PowerApp in the preview is fully functional to make it easy to test and use.</span></span>
    
7. <span data-ttu-id="ad4b7-122">Cliquez sur **publier**</span><span class="sxs-lookup"><span data-stu-id="ad4b7-122">Click **Publish**</span></span>
    
<span data-ttu-id="ad4b7-123">Lorsqu'un utilisateur de Microsoft Search autorisé recherche des mots clés réservés ou des mots clés réservés du signet, le PowerApp apparaît dans le résultat du signet.</span><span class="sxs-lookup"><span data-stu-id="ad4b7-123">When an authorized Microsoft Search user searches on Bing for any of the bookmark's keywords or reserved keywords, the PowerApp will appear in the bookmark result.</span></span>

  

