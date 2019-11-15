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
ms.openlocfilehash: 3ac27bd1e859f9ffc825e5e77d96f0de56b13647
ms.sourcegitcommit: 21361af7c244ffd6ff8689fd0ff0daa359bf4129
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/14/2019
ms.locfileid: "38626263"
---
# <a name="microsoft-graph-connectors-preview"></a>Aperçu des connecteurs Microsoft Graph

Les connecteurs Microsoft Graph, les API d’indexation et les API de recherche sont actuellement en version préliminaire. Pour accéder à la fonctionnalité connecteurs, vous devez demander à rejoindre le programme d’aperçu en envoyant le <a href="https://forms.office.com/Pages/ResponsePage.aspx?id=v4j5cvGGr0GRqy180BHbRxWYgu82J_RFnMMATAS6_chUNVYwNU1CMDNZUDBSSDZKWVo2RDJDRjRLQi4u" target="_blank">formulaire d’aperçu des connecteurs Microsoft Graph</a>. Il s’agit d’une préversion préliminaire et il n’existe aucune garantie de niveau de service. Nous encourageons les clients à essayer les fonctionnalités des connecteurs et à fournir des commentaires. Nous vous déconseillons d’utiliser des connecteurs à des fins de production pendant la période d’évaluation.

## <a name="set-up-targeted-release"></a>Configurer la version ciblée
Pour tester les connecteurs, vous devez disposer de l’option de **publication ciblée** définie pour tous les utilisateurs de votre organisation. La configuration requise de la version ciblée n’est pas l’un des environnements d’aperçu suivants que vous choisissez.
Pour en savoir plus sur l’option de publication ciblée et sur la façon de la définir, consultez <a href="https://docs.microsoft.com/office365/admin/manage/release-options-in-office-365?view=o365-worldwide" target="_blank">la rubrique Configurer les options de publication standard ou ciblée dans Office 365</a>.

## <a name="choose-a-preview-environment"></a>Choisir un environnement d’aperçu 
Pour tester les connecteurs, les API d’indexation et les API de recherche, nous vous recommandons ces deux méthodes :
1. **Testez le client**.  Nous vous encourageons à utiliser un locataire de test pour essayer l’aperçu des connecteurs Microsoft Graph.
2. **Collection de sites de test**. Si vous n’avez pas de client de test, vous pouvez créer une collection de sites de test pour tester la fonctionnalité de connecteurs. Pour afficher les résultats des connecteurs sans impact sur les pages de recherche n’importe où dans votre organisation, personnalisez l’expérience de recherche de cette collection de sites uniquement.

## <a name="preview-limitations"></a>Limitations de l’aperçu
La version d’évaluation présente les limitations suivantes :
* Le débit de l’ingestion est limité à quatre éléments par seconde.
* Il n’existe pas de prise en charge des mises à jour de schéma. Une fois que vous avez créé une configuration de connexion, il n’existe aucun moyen de mettre à jour le schéma. Vous pouvez supprimer et recréer la connexion uniquement.
* Le contenu indexé apparaît uniquement dans la page des résultats de recherche sous un secteur vertical personnalisé. Cette restriction s’applique au contenu avec des types personnalisés.
* Avant la mise à disposition générale, toute connexion que vous configurez pendant la période d’aperçu doit être supprimée et recréée. Ces connexions ne fonctionneront plus si elles sont incompatibles avec les modifications apportées à l’amélioration du produit.
* Limite de connexions. Chaque client peut créer jusqu’à 10 connexions.
