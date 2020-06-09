---
title: Aperçu des connecteurs
ms.author: mounika.narayanan
author: monaray
manager: shohara
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: Découvrez l’aperçu des connecteurs Microsoft Graph pour Microsoft Search.
ms.openlocfilehash: 4bcd8360957be69bc701e8b356cd222de32bfc5f
ms.sourcegitcommit: 64eea81f8c1db9ee955013462a7b51612fb7d0b7
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/08/2020
ms.locfileid: "44604382"
---
# <a name="microsoft-graph-connectors-preview"></a>Aperçu des connecteurs Microsoft Graph

Les connecteurs Microsoft Graph et les API Microsoft Search (requête et index) sont actuellement en état d’aperçu. Pour accéder à la fonctionnalité connecteurs, vous devez activer l’option publication ciblée dans votre client. Il s’agit d’une préversion préliminaire et il n’existe aucune garantie de niveau de service. Nous encourageons les clients à essayer les fonctionnalités des connecteurs et à fournir des commentaires. Nous vous déconseillons d’utiliser des connecteurs à des fins de production pendant la période d’évaluation.

## <a name="set-up-targeted-release"></a>Configurer la version ciblée

Pour tester les connecteurs, vous devez disposer de l’option de **publication ciblée** définie pour tous les utilisateurs de votre organisation. Pour en savoir plus sur l’option de publication ciblée et sur la façon de la définir, consultez [la rubrique Configurer les options de publication standard ou ciblée dans Office 365](https://docs.microsoft.com/office365/admin/manage/release-options-in-office-365?view=o365-worldwide).

## <a name="choose-a-preview-environment"></a>Choisir un environnement d’aperçu

Pour tester les connecteurs, les API d’indexation et les API de recherche, nous vous recommandons ces deux méthodes :

1. **Testez le client**.  Nous vous encourageons à utiliser un locataire de test pour essayer l’aperçu des connecteurs Microsoft Graph.

2. **Collection de sites de test**. Si vous n’avez pas de client de test, vous pouvez créer une collection de sites de test pour tester la fonctionnalité de connecteurs. Pour afficher les résultats des connecteurs sans impact sur les pages de recherche n’importe où dans votre organisation, personnalisez l’expérience de recherche de cette collection de sites uniquement.

## <a name="preview-limitations"></a>Limitations de l’aperçu

La version d’évaluation présente les limitations suivantes :

* Le débit de l’ingestion est limité à quatre éléments par seconde.

* Il n’existe pas de prise en charge des mises à jour de schéma. Une fois que vous avez créé une configuration de connexion, il n’existe aucun moyen de mettre à jour le schéma. Vous pouvez supprimer et recréer la connexion uniquement.

* Le contenu indexé apparaît uniquement dans la page des résultats de recherche sous un secteur vertical personnalisé. Cette restriction s’applique au contenu avec des types personnalisés.

* Toute connexion que vous configurez pendant la période d’aperçu doit être supprimée et recréée. Ces connexions ne fonctionneront plus si elles sont incompatibles avec les modifications apportées à l’amélioration du produit.

* Il existe une limite de connexions. Chaque client peut créer jusqu’à 10 connexions.

* Taille du référentiel source. Nous vous recommandons de prévisualiser les connecteurs avec un référentiel source d’environ 200 000 éléments, car il s’agit de notre limite d’étendue de recherche testée. Nous travaillons sur l’amélioration des performances de la recherche et nous prévoyons de prendre en charge des référentiels plus volumineux dans un futur proche.

* La modification de la prise en charge de la connexion n’est pas disponible. Une fois que la connexion a été créée, vous ne pouvez pas la modifier ni la modifier. Si vous devez modifier des détails, vous devez supprimer et recréer la connexion.

* Le contenu du connecteur ne peut être recherché que sur des secteurs verticaux personnalisés.

* Le contenu du connecteur à partir d’une seule connexion peut être affiché dans chaque vertical personnalisé et nécessite une création de type de résultat.
