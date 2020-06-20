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
# <a name="add-a-search-box-to-your-intranet-site"></a>Ajout d’une zone de recherche à votre site intranet

Pour permettre à vos utilisateurs d’accéder facilement aux résultats de votre organisation, ajoutez une zone de recherche Microsoft Search dans Bing à un site ou une page intranet. Voici quelques-uns des avantages :

- Une zone de recherche sur votre portail SharePoint ou intranet constitue un point d’entrée de confiance familier pour démarrer la recherche
- Prend en charge tous les principaux navigateurs Web, y compris Google Chrome et Microsoft Edge
- Seules les suggestions de recherche de votre organisation apparaissent, les suggestions Web ne sont jamais incluses.
- Permet aux utilisateurs d’accéder à une page de résultats du travail Microsoft Search dans Bing, qui exclut les publicités et les résultats Web
- Vous contrôlez l’apparence et le comportement de la zone de recherche
  
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
                                                // when absent, ghost text will be "Search work"
                                                // when specified, text will be "Search <companyNameInGhostText>"
    };
</script>
<script async src="https://www.bing.com/business/s?k=sb"></script>
```

## <a name="use-an-iframe-to-embed-a-search-box"></a>Utilisation d’un iFrame pour incorporer une zone de recherche

Si vous ne pouvez pas incorporer un script dans le site, ajoutez la zone de recherche en utilisant un iFrame. Vous ne pourrez pas personnaliser l’apparence de la zone de recherche.
  
```html
<iframe width="564" height="400" src="https://www.bing.com/business/searchbox"></iframe>
```
