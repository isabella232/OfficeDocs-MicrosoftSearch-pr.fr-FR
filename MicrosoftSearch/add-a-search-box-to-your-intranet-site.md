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
description: Obtenez des suggestions de recherche pertinentes et trouvez des résultats de travail plus rapidement en ajoutant la zone de recherche Microsoft à une page ou à un site intranet.
ms.openlocfilehash: a66c0cea71cf637209d298f49542864755e92ec9
ms.sourcegitcommit: c18809f57f957de958a87e940dc3904061fe0bd0
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/23/2019
ms.locfileid: "30789312"
---
# <a name="add-a-search-box-to-your-intranet-site"></a>Ajout d’une zone de recherche à votre site intranet

Pour accéder rapidement à des suggestions de recherche et des résultats de travail pertinents, ajoutez une zone de recherche Microsoft à des sites ou à des pages intranet.
  
## <a name="add-a-search-box-to-an-intranet-page"></a>Ajout d’une zone de recherche à une page intranet

Vous devez ajouter deux éléments à la page : un conteneur pour la zone de recherche et le script qui l’alimente.
  
```html
<div id="bfb_searchbox"></div>
<script>
    var bfbSearchBoxConfig = {
        containerSelector: "bfb_searchbox"
    };
</script>
<script async src="https://www.bing.com/business/s?k=sb"></script>
```

Sur un site SharePoint classique, ajoutez un composant WebPart Éditeur de script et faites glisser le script vers ce dernier.
  
## <a name="enable-the-search-box-for-mobile"></a>Activation de la zone de recherche pour la version mobile

Pour les pages ou les sites intranet à disposition des utilisateurs mobiles, ajoutez « isMobile: true » à l’objet des paramètres :
  
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

## <a name="put-focus-on-the-search-box-by-default"></a>Mise en surbrillance par défaut de la zone de recherche

Pour aider les utilisateurs à effectuer plus rapidement leurs recherches, placez le curseur dans la zone de recherche pendant le chargement de la page ou du site, et ajoutez « focus: true » à l’objet des paramètres :
  
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

## <a name="customize-the-appearance-of-the-search-box"></a>Personnaliser l’apparence de la zone de recherche 

Pour aider la zone de recherche à mieux s’insérer au style de votre intranet, il existe de nombreuses options de configuration que vous pouvez utiliser. Combinez et associez les options correspondantes à vos besoins.

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

## <a name="use-an-iframe-to-embed-a-search-box"></a>Utilisation d’un iFrame pour incorporer une zone de recherche

Si vous ne pouvez pas incorporer un script dans le site, ajoutez la zone de recherche en utilisant un iFrame. Vous ne pourrez pas personnaliser l’apparence de la zone de recherche.
  
```html
<iframe width="564" height="400" src="https://www.bing.com/business/searchbox"></iframe>
```