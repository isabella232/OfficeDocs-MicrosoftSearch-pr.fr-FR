---
title: Cluster de résultats de connecteurs
ms.author: manusi
author: manusi
manager: ruppala
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: Détails de l’expérience de cluster de résultats de connecteurs
ms.openlocfilehash: f2355213a0b1821968c801153841c274e539d72e
ms.sourcegitcommit: 7294c953e7939e48f128656cc2f8f22705ae3f3d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/06/2021
ms.locfileid: "49773026"
---
# <a name="graph-connectors-result-cluster"></a>Cluster de résultats de connecteurs Graph

## <a name="overview-of-the-graph-connectors-result-cluster-preview"></a>Vue d’ensemble du cluster de résultats connecteurs Graph (aperçu)  

Avec les clusters de résultats des connecteurs Graph, les entreprises peuvent rechercher du contenu provenant de sources de données tierces dans leur affichage par défaut, l’onglet **tous** , dans SharePoint, Office.com et Microsoft Search dans Bing.

Les clusters de résultats aident les utilisateurs à découvrir tous les contenus tiers à un seul emplacement. Les résultats affichés dans un cluster de résultats sont regroupés en fonction de la configuration du secteur vertical de recherche.

## <a name="how-connector-results-are-selected-and-displayed"></a>Sélection et affichage des résultats du connecteur

Les résultats de connecteur fournis dans le cluster de résultats sont dérivés de secteurs verticaux de recherche individuels avec contenu de connecteur. Chaque secteur vertical de recherche fournit un ensemble de résultats pertinents qui devient un cluster de résultats candidats. Les résultats pertinents sont choisis en fonction de la propriété « Title » et de la propriété « Content » de chaque élément. La propriété Content est marquée comme *IsContent = true* dans le schéma.

Pour vous assurer de la découverte du contenu des secteurs verticaux de recherche, nous vous recommandons de fournir des titres explicites pour vos éléments. Cela a un impact positif sur l’arbitrage des candidats aux clusters de résultats et la probabilité que votre contenu apparaisse dans un cluster de résultats. Par exemple, évitez d’utiliser des ID comme valeurs pour la propriété « Title », sauf si vos utilisateurs utilisent des ID pour rechercher du contenu.

La fréquence à laquelle un cluster de résultats est affiché varie selon les facteurs tels que le nombre de secteurs verticaux de recherche que vous configurez et le type de contenu. En interagissant ou en ignorant un cluster de résultats, les utilisateurs fournissent implicitement des indications qui ajustent son déclenchement dans le temps.

L’expérience des résultats de recherche pour les éléments de connecteur affichés dans votre cluster de résultats utilise les [types de résultats](https://docs.microsoft.com/microsoftsearch/customize-search-page#create-your-own-result-type) que vous avez définis. Si aucun type de résultat n’est configuré, une [mise en page générée](https://docs.microsoft.com/microsoftsearch/customize-search-page#default-search-result-layout) par le système est utilisée. 

Nous vous recommandons d’utiliser la propriété « Title » comme titre du résultat de recherche et la propriété « Content » comme description de la recherche. Cela permettra à vos utilisateurs de bénéficier d’un déclenchement précis du cluster de résultats et de la plupart des résultats pertinents dans le cluster. 

## <a name="enable-result-clusters"></a>Activer les clusters de résultats
  
L’expérience de cluster de résultats est désactivée par défaut.  

Pour activer l’expérience au niveau de l’organisation, procédez comme suit :

1. Dans le [Centre d’administration Microsoft 365](https://admin.microsoft.com), accédez à la [**barre verticale**](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/verticals).
2. Sélectionnez l’option **tous** les secteurs verticaux, puis activer afficher les **résultats du connecteur**. 


Pour activer l’expérience au niveau du site SharePoint, procédez comme suit :

1. Sur le site SharePoint où vous souhaitez obtenir l’expérience de cluster de résultats, accédez à **paramètres**.
2. Accédez à **informations sur le site** > **Afficher tous les paramètres du site**.
3. Accédez à la section Microsoft Search, puis sélectionnez **configurer Microsoft Search pour cette collection de sites**.
4. Dans le volet de navigation, accédez à **expérience personnalisée**, puis sélectionnez **verticales**.
5. Sélectionnez l’option **tous** les secteurs verticaux, puis activer afficher les **résultats du connecteur**.

## <a name="view-the-result-cluster-experience-after-it-is-enabled"></a>Afficher l’expérience de cluster de résultats une fois qu’elle est activée

Une fois que vous avez activé l’expérience de cluster de résultats, l’affichage peut prendre quelques minutes. Si vous souhaitez l’expérience immédiatement, vous pouvez ajouter *cacheClear = true* à l’URL dans SharePoint et Office.
