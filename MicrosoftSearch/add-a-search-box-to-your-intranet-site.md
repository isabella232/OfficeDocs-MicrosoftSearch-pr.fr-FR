---
title: Ajouter une zone de recherche à votre site intranet
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
description: Obtenir des suggestions de recherche pertinents et trouvez des résultats de travail plus rapidement en ajoutant une zone de recherche Microsoft Search vers une page ou un site intranet.
ms.openlocfilehash: a27b4d79e8795cdd2749c12119709f97710061e7
ms.sourcegitcommit: bf52cc63b75f2e0324a716fe65da47702956b722
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/18/2019
ms.locfileid: "29378729"
---
# <a name="add-a-search-box-to-your-intranet-site"></a><span data-ttu-id="402a2-103">Ajouter une zone de recherche à votre site intranet</span><span class="sxs-lookup"><span data-stu-id="402a2-103">Add a search box to your intranet site</span></span>

<span data-ttu-id="402a2-104">Pour accéder rapidement à des suggestions de recherche pertinents et les résultats de travail, ajoutez une zone de recherche Microsoft Search vers n’importe quel site intranet ou une page.</span><span class="sxs-lookup"><span data-stu-id="402a2-104">For fast access to relevant search suggestions and work results, add a Microsoft Search search box to any intranet site or page.</span></span>
  
## <a name="add-a-search-box-to-an-intranet-page"></a><span data-ttu-id="402a2-105">Ajouter une zone de recherche à une page intranet</span><span class="sxs-lookup"><span data-stu-id="402a2-105">Add a search box to an intranet page</span></span>

<span data-ttu-id="402a2-106">Vous devez ajouter deux éléments à la page : un conteneur pour la zone de recherche et le script qui il démarre.</span><span class="sxs-lookup"><span data-stu-id="402a2-106">You need to add two elements to the page: a container for the search box and the script that powers it.</span></span>
  
```html
<div id="bfb_searchbox"></div>
<script>
    var bfbSearchBoxConfig = {
        containerSelector: "bfb_searchbox"
    };
</script>
<script async src="https://www.bing.com/business/s?k=sb"></script>
```

<span data-ttu-id="402a2-107">Sur un site classique SharePoint, ajouter un composant WebPart Éditeur de Script et abandonner le script qu’il contient.</span><span class="sxs-lookup"><span data-stu-id="402a2-107">On a SharePoint classic site, add a Script Editor Web Part and drop the script in it.</span></span>
  
## <a name="enable-the-search-box-for-mobile"></a><span data-ttu-id="402a2-108">Activer la zone de recherche pour mobile</span><span class="sxs-lookup"><span data-stu-id="402a2-108">Enable the search box for mobile</span></span>

<span data-ttu-id="402a2-109">Pour les sites intranet ou pages sont disponibles pour les utilisateurs mobiles, ajoutez isMobile : true pour l’objet settings :</span><span class="sxs-lookup"><span data-stu-id="402a2-109">For intranet sites or pages available to mobile users, add isMobile: true to the settings object:</span></span>
  
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

## <a name="put-focus-on-the-search-box-by-default"></a><span data-ttu-id="402a2-110">Placer le focus sur la zone de recherche par défaut</span><span class="sxs-lookup"><span data-stu-id="402a2-110">Put focus on the search box by default</span></span>

<span data-ttu-id="402a2-111">Pour aider les utilisateurs à effectuer des recherches rapides, lorsque le chargement de page ou un site placez le curseur dans la zone de recherche en ajoutant le focus : true pour l’objet settings :</span><span class="sxs-lookup"><span data-stu-id="402a2-111">To help users search faster, when the page or site loads place the cursor in the search box by adding focus: true to the settings object:</span></span>
  
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

## <a name="use-an-iframe-to-embed-a-search-box"></a><span data-ttu-id="402a2-112">Utilisez un iFrame pour incorporer une zone de recherche</span><span class="sxs-lookup"><span data-stu-id="402a2-112">Use an iFrame to embed a search box</span></span>

<span data-ttu-id="402a2-113">Si l’incorporation d’un script n’est pas une option pour le site, utilisez un iFrame pour ajouter la zone de recherche :</span><span class="sxs-lookup"><span data-stu-id="402a2-113">If embedding a script isn't an option for the site, use an iFrame to add the search box:</span></span>
  
```html
<iframe width="564" height="400" src="https://www.bing.com/business/searchbox"></iframe>
```
