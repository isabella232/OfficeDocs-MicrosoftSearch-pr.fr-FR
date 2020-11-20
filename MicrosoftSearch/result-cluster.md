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
ms.openlocfilehash: eac4180a247fe17b4e86b57a69f2b7bdb79e56bb
ms.sourcegitcommit: 59cdd3f0f82b7918399bf44d27d9891076090f4f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/20/2020
ms.locfileid: "49367727"
---
# <a name="graph-connectors-result-cluster"></a>Cluster de résultats de connecteurs Graph

## <a name="overview-of-the-graph-connectors-result-cluster-preview"></a>Vue d’ensemble du cluster de résultats connecteurs Graph (aperçu)  

 Avec les clusters de résultats des connecteurs Graph, les entreprises peuvent rechercher du contenu provenant de sources de données tierces dans leur affichage par défaut (onglet tous) dans SharePoint et Office.com.

Les clusters de résultats aident les utilisateurs à découvrir tous les contenus tiers (previoulsy liés à un connecteur et à la verticale) à un seul endroit. Les résultats affichés dans un cluster de résultats sont regroupés en fonction de la façon dont l’administrateur client les configure dans un secteur vertical de recherche.  

## <a name="how-connector-results-are-selected-and-displayed"></a>Sélection et affichage des résultats du connecteur

Les résultats de connecteur fournis dans le cluster de résultats sont dérivés de secteurs verticaux de recherche individuels avec contenu de connecteur. Chaque secteur vertical de recherche fournit un ensemble de résultats pertinents qui devient un cluster de résultats candidats. Les résultats pertinents sont choisis en fonction de la propriété « Title », de l’extrait de résultats et du composant de contenu de chaque élément.

Pour vous assurer de la découverte du contenu des secteurs verticaux de recherche, nous vous recommandons de fournir des titres explicites pour vos éléments. Cela a un impact positif sur l’arbitrage des candidats aux clusters de résultats et la probabilité que votre contenu apparaisse dans un cluster de résultats. Par exemple, évitez d’utiliser des ID comme valeurs pour la propriété « Title », sauf si vos utilisateurs utilisent des ID pour rechercher du contenu.

La fréquence à laquelle un cluster de résultats est affiché varie selon les facteurs tels que le nombre de secteurs verticaux de recherche que vous configurez et le type de contenu. En sélectionnant ou en ignorant les résultats du cluster de résultats, vous fournissez implicitement des indications qui ajusteront le déclenchement des clusters de résultats au fil du temps.

L’expérience des résultats de recherche pour les éléments de connecteur affichés dans votre cluster de résultats est générée par le système et n’utilise pas de mise en page de résultats personnalisée. Vous devez déclarer la propriété « Title » et le contenu de l’élément lors de l’inscription de la connexion si vous souhaitez que les résultats apparaissent dans votre cluster de résultats.

## <a name="enable-result-clusters"></a>Activer les clusters de résultats
  
L’expérience de cluster de résultats est désactivée par défaut.  
Pour activer l’expérience au niveau de l’organisation, procédez comme suit :

Centre d’administration Microsoft 365

1. Dans le [Centre d’administration 365 de Microsoft](https://admin.microsoft.com/), accédez à **paramètres** de  >  **recherche &** aide au secteur vertical pour la personnalisation de l’intelligence  >  **Customization**  >  **Verticals**.  
2. Sélectionnez le secteur vertical **tout** et accédez à la section **afficher les résultats du connecteur** . Activer l’expérience au niveau du site.

SharePoint

1. Sur le site SharePoint où vous souhaitez obtenir l’expérience de cluster de résultats, accédez à **paramètres**.
2. Accédez à **informations sur le site** > **Afficher tous les paramètres du site**.
3. Accédez à la section Microsoft Search, puis sélectionnez **configurer Microsoft Search pour cette collection de sites**.
4. Dans le volet de navigation, accédez à **expérience personnalisée**, puis sélectionnez **verticales**.
5. Sélectionnez l’option **tous** les secteurs verticaux, puis activer afficher les **résultats du connecteur**.

## <a name="view-the-result-cluster-experience-after-it-is-enabled"></a>Afficher l’expérience de cluster de résultats une fois qu’elle est activée

Une fois que vous avez activé l’expérience de cluster de résultats, l’affichage peut prendre quelques minutes. Si vous souhaitez l’expérience immédiatement, vous pouvez ajouter *cacheClear = true* à l’URL dans SharePoint et Office.
