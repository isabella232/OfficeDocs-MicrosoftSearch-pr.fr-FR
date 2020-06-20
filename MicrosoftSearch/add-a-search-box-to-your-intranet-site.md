---
title: Ajout d’une zone de recherche à votre site intranet
ms.author: dawholl
author: dawholl
manager: kellis
ms.date: 10/31/2018
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
ms.assetid: f980b90f-95e2-4b66-8b21-69f601ff4b50
ROBOTS: NoIndex
description: Obtenez des suggestions de recherche pertinentes et trouvez des résultats de travail plus rapidement en ajoutant la zone de recherche Microsoft à une page ou à un site intranet.
ms.openlocfilehash: af12ce4d17c2695e196f8e4d79ccd515f002f238
ms.sourcegitcommit: 92206ea179ec00b22496f6fd2866b5406449cf40
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/18/2020
ms.locfileid: "44798224"
---
# <a name="add-a-search-box-to-your-intranet-site"></a><span data-ttu-id="ce9b7-103">Ajout d’une zone de recherche à votre site intranet</span><span class="sxs-lookup"><span data-stu-id="ce9b7-103">Add a search box to your intranet site</span></span>

<span data-ttu-id="ce9b7-104">Pour permettre à vos utilisateurs d’accéder facilement aux résultats de votre organisation, ajoutez une zone de recherche Microsoft Search dans Bing à un site ou une page intranet.</span><span class="sxs-lookup"><span data-stu-id="ce9b7-104">To provide your users with easy access to results from your organization, add a Microsoft Search in Bing search box to any intranet site or page.</span></span> <span data-ttu-id="ce9b7-105">Voici quelques-uns des avantages :</span><span class="sxs-lookup"><span data-stu-id="ce9b7-105">These are some of the benefits:</span></span>

- <span data-ttu-id="ce9b7-106">Une zone de recherche sur votre portail SharePoint ou intranet constitue un point d’entrée de confiance familier pour démarrer la recherche</span><span class="sxs-lookup"><span data-stu-id="ce9b7-106">A search box on your SharePoint or intranet portal provides a familiar, trusted entry point to start searching</span></span>
- <span data-ttu-id="ce9b7-107">Prend en charge tous les principaux navigateurs Web, y compris Google Chrome et Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="ce9b7-107">Supports all major web browsers, including Google Chrome and Microsoft Edge</span></span>
- <span data-ttu-id="ce9b7-108">Seules les suggestions de recherche de votre organisation apparaissent, les suggestions Web ne sont jamais incluses.</span><span class="sxs-lookup"><span data-stu-id="ce9b7-108">Only search suggestions from your organization appear, web suggestions are never included</span></span>
- <span data-ttu-id="ce9b7-109">Permet aux utilisateurs d’accéder à une page de résultats du travail Microsoft Search dans Bing, qui exclut les publicités et les résultats Web</span><span class="sxs-lookup"><span data-stu-id="ce9b7-109">Takes users to a Microsoft Search in Bing work results page, which excludes ads and web results</span></span>
- <span data-ttu-id="ce9b7-110">Vous contrôlez l’apparence et le comportement de la zone de recherche</span><span class="sxs-lookup"><span data-stu-id="ce9b7-110">You control the appearance and behavior of the search box</span></span>
  
## <a name="add-a-search-box-to-an-intranet-page"></a><span data-ttu-id="ce9b7-111">Ajout d’une zone de recherche à une page intranet</span><span class="sxs-lookup"><span data-stu-id="ce9b7-111">Add a search box to an intranet page</span></span>

<span data-ttu-id="ce9b7-112">Vous devez ajouter deux éléments à la page : un conteneur pour la zone de recherche et le script qui l’alimente.</span><span class="sxs-lookup"><span data-stu-id="ce9b7-112">You need to add two elements to the page: a container for the search box and the script that powers it.</span></span>
  
```html
<div id="bfb_searchbox"></div>
<script>
    var bfbSearchBoxConfig = {
        containerSelector: "bfb_searchbox"
    };
</script>
<script async src="https://www.bing.com/business/s?k=sb"></script>
```

<span data-ttu-id="ce9b7-113">Sur un site SharePoint classique, ajoutez un composant WebPart Éditeur de script et faites glisser le script vers ce dernier.</span><span class="sxs-lookup"><span data-stu-id="ce9b7-113">On a SharePoint classic site, add a Script Editor Web Part and drop the script in it.</span></span>
  
## <a name="enable-the-search-box-for-mobile"></a><span data-ttu-id="ce9b7-114">Activation de la zone de recherche pour la version mobile</span><span class="sxs-lookup"><span data-stu-id="ce9b7-114">Enable the search box for mobile</span></span>

<span data-ttu-id="ce9b7-115">Pour les pages ou les sites intranet à disposition des utilisateurs mobiles, ajoutez « isMobile: true » à l’objet des paramètres :</span><span class="sxs-lookup"><span data-stu-id="ce9b7-115">For intranet sites or pages available to mobile users, add isMobile: true to the settings object:</span></span>
  
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

## <a name="put-focus-on-the-search-box-by-default"></a><span data-ttu-id="ce9b7-116">Mise en surbrillance par défaut de la zone de recherche</span><span class="sxs-lookup"><span data-stu-id="ce9b7-116">Put focus on the search box by default</span></span>

<span data-ttu-id="ce9b7-117">Pour aider les utilisateurs à effectuer plus rapidement leurs recherches, placez le curseur dans la zone de recherche pendant le chargement de la page ou du site, et ajoutez « focus: true » à l’objet des paramètres :</span><span class="sxs-lookup"><span data-stu-id="ce9b7-117">To help users search faster, when the page or site loads place the cursor in the search box by adding focus: true to the settings object:</span></span>
  
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

## <a name="customize-the-appearance-of-the-search-box"></a><span data-ttu-id="ce9b7-118">Personnaliser l’apparence de la zone de recherche</span><span class="sxs-lookup"><span data-stu-id="ce9b7-118">Customize the appearance of the search box</span></span> 

<span data-ttu-id="ce9b7-119">Pour aider la zone de recherche à mieux s’insérer au style de votre intranet, il existe de nombreuses options de configuration que vous pouvez utiliser.</span><span class="sxs-lookup"><span data-stu-id="ce9b7-119">To help the search box better fit with the style of your intranet, there are a variety of configuration options you can use.</span></span> <span data-ttu-id="ce9b7-120">Combinez et associez les options correspondantes à vos besoins.</span><span class="sxs-lookup"><span data-stu-id="ce9b7-120">Mix and match options to suit your needs.</span></span>

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
                                                // when absent, ghost text will be "Search work"
                                                // when specified, text will be "Search <companyNameInGhostText>"
    };
</script>
<script async src="https://www.bing.com/business/s?k=sb"></script>
```

## <a name="use-an-iframe-to-embed-a-search-box"></a><span data-ttu-id="ce9b7-121">Utilisation d’un iFrame pour incorporer une zone de recherche</span><span class="sxs-lookup"><span data-stu-id="ce9b7-121">Use an iFrame to embed a search box</span></span>

<span data-ttu-id="ce9b7-122">Si vous ne pouvez pas incorporer un script dans le site, ajoutez la zone de recherche en utilisant un iFrame.</span><span class="sxs-lookup"><span data-stu-id="ce9b7-122">If embedding a script isn't an option for the site, use an iFrame to add the search box.</span></span> <span data-ttu-id="ce9b7-123">Vous ne pourrez pas personnaliser l’apparence de la zone de recherche.</span><span class="sxs-lookup"><span data-stu-id="ce9b7-123">You won't be able to customize the appearance of the search box.</span></span>
  
```html
<iframe width="564" height="400" src="https://www.bing.com/business/searchbox"></iframe>
```
