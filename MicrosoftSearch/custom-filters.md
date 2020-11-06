---
title: Gérer les filtres personnalisés
ms.author: rodhb
author: rodhb
manager: jeffkizn
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: Gérer les filtres personnalisés
ms.openlocfilehash: 75273035a7825683f626464df7bbc8e294b41b6f
ms.sourcegitcommit: 59435698bece013ae64ca2a68c43455ca10e3fdf
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/05/2020
ms.locfileid: "48927381"
---
# <a name="create-custom-filters"></a>Créer des filtres personnalisés

Vous pouvez créer des filtres pour personnaliser l’expérience de recherche que les utilisateurs voient lorsqu’ils recherchent dans Microsoft [SharePoint](https://sharepoint.com/), Microsoft [Office](https://office.com)et Microsoft Search dans [Bing](https://bing.com). Filtres permet aux utilisateurs d’affiner rapidement le jeu de résultats à partir de leur requête de recherche.

Un filtre personnalisé peut être créé à l’intérieur d’un vertical basé sur une propriété Connection. Par exemple, vous pouvez créer un filtre **publié sur** un filtre pour une connexion ServiceNow à l’intérieur d’un secteur vertical personnalisé.

## <a name="things-to-consider"></a>Informations importantes

1. Pour créer un filtre personnalisé sur la source de contenu de connexion, certaines fonctionnalités supplémentaires sont fournies :
- Vous pouvez également créer un filtre sur un alias pour les propriétés source du connecteur.
- Si votre vertical dispose de plusieurs connexions, vous pouvez créer un filtre commun sur ces connexions. Pour ce faire, vous pouvez créer le filtre sur un alias commun qui aliase les propriétés source sur différentes connexions. Par exemple, vous pouvez créer un filtre **auteur** sur un ServiceNow & une connexion JIRA en créant des alias comme suit :

| Connection | Propriété | Alias |
| --- | --- | --- |
| Service maintenant | Propriétaire | Auteur |
| Jira | Éditeur | Auteur |

2. Les filtres existent dans l’étendue du secteur vertical. Car  
- Si un filtre est créé dans un secteur vertical au niveau de l’organisation, le filtre n’est visible qu’au niveau de l’organisation.
- Si un filtre est créé dans un secteur vertical au niveau du site, le filtre n’est visible qu’au niveau du site.

## <a name="steps-to-create-custom-filter"></a>Étapes de création d’un filtre personnalisé

### <a name="create-filter-in-organizational-level-vertical"></a>Créer un filtre au niveau de l’organisation verticale :

Pour créer un filtre sur Microsoft Search, procédez comme suit :

1. Dans le centre d’administration Microsoft 365, accédez à la page des [secteurs verticaux](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/verticals) .
2. Créez/modifiez le secteur vertical dans lequel vous souhaitez créer le filtre.
3. Accéder à l’étape « filtres » dans l’Assistant
4. Cliquez sur Ajouter un filtre et commencez après avoir ajouté des filtres, vous pouvez consulter et enregistrer le secteur vertical.

## <a name="known-limitations"></a>Limitations connues

1. Vous pouvez actuellement créer des filtres uniquement sur la chaîne & les propriétés gérées de type date.
2. Vous ne pouvez pas créer de filtres hiérarchiques

## <a name="resources"></a>Ressources

[Personnaliser la page des résultats de recherche](customize-search-page.md)