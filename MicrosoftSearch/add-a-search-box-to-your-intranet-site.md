---
title: Ajout d’une zone de recherche à votre site intranet
ms.author: dawholl
author: dawholl
manager: kellis
ms.date: 10/31/2018
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Priority
search.appverid:
- BFB160
- MET150
- MOE150
ms.assetid: f980b90f-95e2-4b66-8b21-69f601ff4b50
ROBOTS: NoIndex
description: Obtenez des suggestions de recherche pertinentes et trouvez des résultats de travail plus rapidement en ajoutant la zone de recherche Microsoft à une page ou à un site intranet.
ms.openlocfilehash: 867282393c7a4bffa63363a3455e4f1543c7f8a1
ms.sourcegitcommit: be2e837d9b087bffe6ce40d72d7ae58a8fcdf3fe
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/30/2019
ms.locfileid: "34590692"
---
# <a name="add-a-search-box-to-your-intranet-site"></a><span data-ttu-id="1afa9-103">Ajout d’une zone de recherche à votre site intranet</span><span class="sxs-lookup"><span data-stu-id="1afa9-103">Add a search box to your intranet site</span></span>

> [!IMPORTANT]
> <span data-ttu-id="1afa9-104">Cet article s’applique à la fonctionnalité Recherche Microsoft dans le portail d’administration Bing.</span><span class="sxs-lookup"><span data-stu-id="1afa9-104">This article applies to the Microsoft Search in Bing admin portal.</span></span> <span data-ttu-id="1afa9-105">Nous déplaçons le portail vers le centre d’administration Microsoft 365. Ensuite, nous le supprimerons.</span><span class="sxs-lookup"><span data-stu-id="1afa9-105">We’re moving the portal to the Microsoft 365 admin center, and then it will be removed.</span></span> <span data-ttu-id="1afa9-106">Pour commencer, nous vous suggérons d’utiliser le centre d’administration Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="1afa9-106">We recommend that you use the Microsoft 365 admin center to get started.</span></span> <span data-ttu-id="1afa9-107">[Vue d’ensemble de la fonctionnalité Recherche Microsoft](overview-microsoft-search.md).</span><span class="sxs-lookup"><span data-stu-id="1afa9-107">[Overview of Microsoft Search](overview-microsoft-search.md)</span></span>

<span data-ttu-id="1afa9-108">Pour accéder rapidement à des suggestions de recherche et des résultats de travail pertinents, ajoutez une zone de recherche Microsoft à des sites ou à des pages intranet.</span><span class="sxs-lookup"><span data-stu-id="1afa9-108">For fast access to relevant search suggestions and work results, add a Microsoft Search search box to any intranet site or page.</span></span>
  
## <a name="add-a-search-box-to-an-intranet-page"></a><span data-ttu-id="1afa9-109">Ajout d’une zone de recherche à une page intranet</span><span class="sxs-lookup"><span data-stu-id="1afa9-109">Add a search box to an intranet page</span></span>

<span data-ttu-id="1afa9-110">Vous devez ajouter deux éléments à la page : un conteneur pour la zone de recherche et le script qui l’alimente.</span><span class="sxs-lookup"><span data-stu-id="1afa9-110">You need to add two elements to the page: a container for the search box and the script that powers it.</span></span>
  
```html
<div id="bfb_searchbox"></div>
<script>
    var bfbSearchBoxConfig = {
        containerSelector: "bfb_searchbox"
    };
</script>
<script async src="https://www.bing.com/business/s?k=sb"></script>
```

<span data-ttu-id="1afa9-111">Sur un site SharePoint classique, ajoutez un composant WebPart Éditeur de script et faites glisser le script vers ce dernier.</span><span class="sxs-lookup"><span data-stu-id="1afa9-111">On a SharePoint classic site, add a Script Editor Web Part and drop the script in it.</span></span>
  
## <a name="enable-the-search-box-for-mobile"></a><span data-ttu-id="1afa9-112">Activation de la zone de recherche pour la version mobile</span><span class="sxs-lookup"><span data-stu-id="1afa9-112">Enable the search box for mobile</span></span>

<span data-ttu-id="1afa9-113">Pour les pages ou les sites intranet à disposition des utilisateurs mobiles, ajoutez « isMobile: true » à l’objet des paramètres :</span><span class="sxs-lookup"><span data-stu-id="1afa9-113">For intranet sites or pages available to mobile users, add isMobile: true to the settings object:</span></span>
  
```html
<div id="bfb_searchbox"></div>
<script>
    var bfbSearchBoxConfig = {
        containerSelector: "bfb_searchbox", 
        isMobile: true
    };
</script>
<script async src="https://www.bing.com/business/s?k=sb"></script>
```

## <a name="put-focus-on-the-search-box-by-default"></a><span data-ttu-id="1afa9-114">Mise en surbrillance par défaut de la zone de recherche</span><span class="sxs-lookup"><span data-stu-id="1afa9-114">Put focus on the search box by default</span></span>

<span data-ttu-id="1afa9-115">Pour aider les utilisateurs à effectuer plus rapidement leurs recherches, placez le curseur dans la zone de recherche pendant le chargement de la page ou du site, et ajoutez « focus: true » à l’objet des paramètres :</span><span class="sxs-lookup"><span data-stu-id="1afa9-115">To help users search faster, when the page or site loads place the cursor in the search box by adding focus: true to the settings object:</span></span>
  
```html
<div id="bfb_searchbox"></div>
<script>
    var bfbSearchBoxConfig = {
        containerSelector: "bfb_searchbox",
        focus: true
    };
</script>
<script async src="https://www.bing.com/business/s?k=sb"></script>
```

## <a name="customize-the-appearance-of-the-search-box"></a><span data-ttu-id="1afa9-116">Personnaliser l’apparence de la zone de recherche</span><span class="sxs-lookup"><span data-stu-id="1afa9-116">Customize the appearance of the search box</span></span> 

<span data-ttu-id="1afa9-117">Pour aider la zone de recherche à mieux s’insérer au style de votre intranet, il existe de nombreuses options de configuration que vous pouvez utiliser.</span><span class="sxs-lookup"><span data-stu-id="1afa9-117">To help the search box better fit with the style of your intranet, there are a variety of configuration options you can use.</span></span> <span data-ttu-id="1afa9-118">Combinez et associez les options correspondantes à vos besoins.</span><span class="sxs-lookup"><span data-stu-id="1afa9-118">Mix and match options to suit your needs.</span></span>

```html
<div id="bfb_searchbox"></div>
<script>
    var bfbSearchBoxConfig = {
        containerSelector: "bfb_searchbox",
        width: 560,                             // default: 560, min: 360, max: 650
        height: 40,                             // default: 40, min: 40, max: 72
        cornerRadius: 6,                        // default: 6, min: 0, max: 25                                   
        strokeOutline: true,                    // default: true
        dropShadow: true,                       // default: true
        iconColor: "#067FA6",                   // default: #067FA6
        companyNameInGhostText: "Contoso"       // default: not specified
                                                // when absent, ghost text will be "Search work and the web"
                                                // when specified, text will be "Search the web and [Contoso]"
    };
</script>
<script async src="https://www.bing.com/business/s?k=sb"></script>
```

## <a name="use-an-iframe-to-embed-a-search-box"></a><span data-ttu-id="1afa9-119">Utilisation d’un iFrame pour incorporer une zone de recherche</span><span class="sxs-lookup"><span data-stu-id="1afa9-119">Use an iFrame to embed a search box</span></span>

<span data-ttu-id="1afa9-120">Si vous ne pouvez pas incorporer un script dans le site, ajoutez la zone de recherche en utilisant un iFrame.</span><span class="sxs-lookup"><span data-stu-id="1afa9-120">If embedding a script isn't an option for the site, use an iFrame to add the search box.</span></span> <span data-ttu-id="1afa9-121">Vous ne pourrez pas personnaliser l’apparence de la zone de recherche.</span><span class="sxs-lookup"><span data-stu-id="1afa9-121">You won't be able to customize the appearance of the search box.</span></span>
  
```html
<iframe width="564" height="400" src="https://www.bing.com/business/searchbox"></iframe>
```