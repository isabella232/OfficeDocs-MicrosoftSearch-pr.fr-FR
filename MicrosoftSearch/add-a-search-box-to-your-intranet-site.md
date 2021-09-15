---
title: Ajout d’une zone de recherche à votre site intranet
ms.author: dawholl
author: dawholl
manager: kellis
ms.audience: Admin
ms.topic: article
ms.service: mssearch
ms.localizationpriority: medium
search.appverid:
- BFB160
- MET150
- MOE150
ms.assetid: f980b90f-95e2-4b66-8b21-69f601ff4b50
ROBOTS: NoIndex
description: Obtenez des suggestions de recherche pertinentes et trouvez des résultats de travail plus rapidement en ajoutant une zone de Recherche Microsoft à votre site ou page intranet.
ms.openlocfilehash: d9f730eee98291d64e1f860c67be3eb7aa52a4a8
ms.sourcegitcommit: ca5ee826ba4f4bb9b9baabc9ae8a130011c2a3d0
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/15/2021
ms.locfileid: "59375861"
---
# <a name="add-a-search-box-to-your-intranet-site"></a>Ajout d’une zone de recherche à votre site intranet

Pour fournir à vos utilisateurs un accès facile aux résultats de votre organisation, ajoutez une Recherche Microsoft dans Bing de recherche à n’importe quel site ou page intranet. Voici quelques-uns des avantages :

- Une zone de recherche sur votre portail SharePoint ou intranet fournit un point d’entrée familier et fiable pour commencer la recherche
- Prend en charge tous les principaux navigateurs web, y compris Google Chrome et Microsoft Edge
- Seules les suggestions de recherche de votre organisation apparaissent, les suggestions web ne sont jamais incluses
- Permet aux utilisateurs d’Recherche Microsoft dans Bing page de résultats de travail, qui exclut les publicités et les résultats web
- Vous contrôlez l’apparence et le comportement de la zone de recherche, y compris la possibilité d’adrier les utilisateurs sur un secteur vertical par défaut ou un secteur vertical personnalisé que vous avez créé.
  
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
        dropShadow: true,                       // default: false
        iconColor: "#067FA6",                   // default: #067FA6
        title: "Search box",                    // default: "Search box"
        vertical: "Person-people",              // default: not specified, search box directs to the All vertical on the WORK results page
        companyNameInGhostText: "Contoso"       // default: not specified
                                                // when absent, ghost text will be "Search work"
                                                // when specified, text will be "Search <companyNameInGhostText>"
    };
</script>
<script async src="https://www.bing.com/business/s?k=sb"></script>
```

## <a name="direct-users-to-a-default-or-custom-vertical"></a>Diriger les utilisateurs vers un secteur vertical par défaut ou personnalisé

Pour faciliter l’intégration entre vos applications métier ou sites intranet et vos résultats de travail, vous pouvez également personnaliser la zone de recherche en spécifiant un secteur vertical par défaut ou personnalisé sur qui les utilisateurs doivent se poser lorsqu’ils cliquent sur une suggestion de recherche.

Utilisez l’option verticale dans bfbSearchBoxConfig pour définir le secteur vertical de votre choix. Par exemple, si vous souhaitez que les utilisateurs se placent toujours sur le secteur vertical Sites, l’un des secteurs verticaux par défaut, utilisez la valeur « Site-sites ».

:::image type="content" alt-text="Capture d’écran de la page des résultats du travail Recherche Microsoft dans Bing montrant les résultats verticaux et l’URL des sites." source="media/sites-vertical-esb.png" lightbox="media/sites-vertical-esb.png":::

Pour les secteurs verticaux personnalisés, utilisez le hachage à la fin de l’URL. Vous pouvez trouver ces valeurs en recherchant à partir de la page de travail sur Bing, en cliquant sur une étiquette verticale et en copiant la valeur après le signe numérique (#).

:::image type="content" alt-text="Capture d’écran de la page des résultats du travail Recherche Microsoft dans Bing montrant une URL et des résultats verticaux de présentation personnalisés." source="media/custom-vertical-esb.png" lightbox="media/custom-vertical-esb.png":::

## <a name="use-an-iframe-to-embed-a-search-box"></a>Utilisation d’un iFrame pour incorporer une zone de recherche

Si vous ne pouvez pas incorporer un script dans le site, ajoutez la zone de recherche en utilisant un iFrame. Vous ne pourrez pas personnaliser la zone de recherche.
  
```html
<iframe width="564" height="400" src="https://www.bing.com/business/searchbox"></iframe>
```

## <a name="inprivate-mode-and-conditional-access"></a>Mode InPrivate et accès conditionnel

Une zone de recherche incorporée est désactivée si la page ou le site est ouvert dans une fenêtre InPrivate. En outre, avec la prise en charge de l’accès conditionnel Azure AD dans Microsoft Edge, Bing.com ne prend pas en charge la signature AAD lors de l’utilisation du mode InPrivate. Pour plus d’informations sur l’accès conditionnel dans Edge, [voir Microsoft Edge et l’accès conditionnel.](/deployedge/ms-edge-security-conditional-access#accessing-conditional-access-protected-resources-in-microsoft-edge) 
