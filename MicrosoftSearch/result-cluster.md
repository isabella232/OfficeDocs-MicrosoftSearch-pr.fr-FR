---
title: Cluster de résultats connecteurs
ms.author: masingh
author: maheshsinghania
manager: jeffkizn
ms.audience: Admin
ms.topic: article
ms.service: mssearch
ms.localizationpriority: medium
search.appverid:
- BFB160
- MET150
- MOE150
description: Détails de l’expérience du cluster de résultats connecteurs
ms.openlocfilehash: f815c52681a7fc2027b587be980b5e9125e04917
ms.sourcegitcommit: ca5ee826ba4f4bb9b9baabc9ae8a130011c2a3d0
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/15/2021
ms.locfileid: "59376065"
---
# <a name="graph-connectors-result-cluster"></a>cluster de Graph connecteurs de connexions

## <a name="overview-of-the-graph-connectors-result-cluster"></a>Vue d’ensemble du cluster Graph connecteurs de connexion  

Avec les clusters de résultats de connecteurs Graph, les entreprises peuvent rechercher  du contenu à partir de sources de données tierces dans leur affichage par défaut, l’onglet Tout, dans SharePoint, Office.com et Recherche Microsoft dans Bing.

Les clusters de résultats aident les utilisateurs à découvrir tout le contenu tiers au même endroit. Les résultats affichés dans un cluster de résultats sont regroupés en fonction de la configuration verticale de recherche.

## <a name="how-connector-results-are-selected-and-displayed"></a>Sélection et affichage des résultats du connecteur

Les résultats du connecteur fournis dans le cluster de résultats sont dérivés des secteurs verticaux de recherche individuels avec le contenu du connecteur. Chaque secteur vertical de recherche fournit un ensemble de résultats pertinents qui devient un cluster de résultats candidat. Les résultats pertinents sont choisis en fonction de la propriété « title » et de la propriété « content » de chaque élément. La propriété de contenu est marquée comme *étant isContent=true* sur le schéma.

Pour garantir la découverte de contenu à partir des secteurs verticaux de recherche, nous vous recommandons de fournir des titres significatifs pour vos éléments. Cela a un impact positif sur l’arbitrage des candidats au cluster de résultats et la probabilité que votre contenu s’affiche dans un cluster de résultats. Par exemple, évitez d’utiliser des ID comme valeurs pour la propriété « title », sauf si vos utilisateurs utilisent des ID pour rechercher du contenu.

La fréquence d’un cluster de résultats varie selon des facteurs tels que le nombre de secteurs verticaux de recherche que vous configurez et le type de contenu. En interagissant ou en ignorant un cluster de résultats, les utilisateurs fournissent implicitement des conseils qui ajusteront son déclenchement au fil du temps.

L’expérience de résultat de recherche pour les éléments de connecteur affichés dans votre cluster de résultats utilise les types de [résultats](./customize-search-page.md#create-your-own-result-type) que vous avez définis. Si aucun type de résultat n’est configuré, une [disposition générée par le](./customize-search-page.md#default-search-result-layout) système est utilisée.

Nous vous recommandons d’utiliser la propriété « title » comme titre de résultat de recherche et la propriété « content » comme description de recherche. Cela permet à vos utilisateurs de tirer le meilleur résultat du cluster de résultats avec précision et les résultats les plus pertinents dans le cluster.

Les clusters de résultats sont affichés au milieu de la page dans le secteur vertical All. Par exemple, un cluster de résultats provenant d’un secteur vertical « MediaWiki » s’affiche ci-dessous.

![Exemple de cluster de résultats MediaWiki.](media/result-cluster/result-cluster-example.png)

## <a name="result-clusters-default-settings"></a>Paramètres par défaut des clusters de résultats
  
L’expérience de cluster de résultats est désactivée par défaut.  

Si vous souhaitez la désactiver, suivez ces étapes pour désactiver l’expérience au niveau de l’organisation :

1. Dans la [Centre d'administration Microsoft 365](https://admin.microsoft.com), allez à [**Verticals**](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/verticals).
1. Sélectionnez **le tout** vertical, puis **activez masquer les résultats du connecteur.**

Suivez ces étapes pour désactiver l’expérience au niveau SharePoint site :

1. Go to **Paramètres** in the SharePoint site
2. Go to **Site information** View all > **site settings**.
3. Go to the Recherche Microsoft section, then select **Configure Recherche Microsoft for this site collection**.
4. Dans le volet de navigation, sélectionnez **Expérience personnalisée,** puis sélectionnez **Verticals**.
5. Sélectionnez **le tout** vertical, puis **activez masquer les résultats du connecteur.**
