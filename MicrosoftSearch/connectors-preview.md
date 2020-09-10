---
title: Aperçu des connecteurs
ms.author: monaray
author: monaray97
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
ms.openlocfilehash: 81d169074a316b6ab07f47156e0f057e50c12e3e
ms.sourcegitcommit: 988c37610e71f9784b486660400aecaa7bed40b0
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/09/2020
ms.locfileid: "47422891"
---
# <a name="microsoft-graph-connectors-preview"></a>Aperçu des connecteurs Microsoft Graph

L’état actuel des connecteurs Microsoft Graph et des API Microsoft Search (requête et index) est en aperçu. Pour accéder à la fonctionnalité connecteurs, vous devez activer l’option publication ciblée dans votre client. Il s’agit d’une préversion préliminaire et il n’existe aucune garantie de niveau de service. Nous encourageons les clients à essayer les fonctionnalités des connecteurs et à fournir des commentaires. Nous vous déconseillons d’utiliser des connecteurs à des fins de production pendant la période d’évaluation.

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
