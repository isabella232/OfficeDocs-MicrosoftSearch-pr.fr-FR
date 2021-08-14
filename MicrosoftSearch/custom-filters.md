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
ms.openlocfilehash: 256cf9748aa3050aacf48c3562f6f84b4ba2e460
ms.sourcegitcommit: 5151bcd8fd929ef37239b7c229e2fa33b1e0e0b7
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/13/2021
ms.locfileid: "58235920"
---
# <a name="manage-custom-filters"></a>Gérer les filtres personnalisés

Vous pouvez utiliser des filtres pour personnaliser l Recherche Microsoft expérience utilisateur. Les filtres permettent aux utilisateurs d’affiner rapidement l’ensemble des résultats de leur requête de recherche.

Un filtre personnalisé peut être créé à l’intérieur d’un secteur vertical basé sur une propriété de connexion. Par exemple, vous pouvez créer un **filtre Publié sur** pour la connexion ServiceNow à l’intérieur d’un secteur vertical.

> [!NOTE]
> Les filtres personnalisés sont actuellement en prévisualisation pour les administrateurs et les utilisateurs finaux dans la version ciblée. Pour plus d’informations sur la prévisualisation, voir [les fonctionnalités d’aperçu des connecteurs.](connectors-overview.md#what-are-the-preview-features)

## <a name="create-a-filter-in-an-organizational-level-vertical"></a>Créer un filtre dans un secteur vertical au niveau de l’organisation

Pour créer un filtre sur la recherche Microsoft, suivez les étapes suivantes :

1. Dans la Centre d’administration Microsoft 365, allez à [Verticals](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/verticals).
1. Créer/modifier le secteur vertical dans lequel vous souhaitez créer le filtre
1. Accédez à l’étape « Filtres » de l’Assistant
1. Cliquez sur « Ajouter un filtre » et commencer
1. Après avoir ajouté des filtres, vous pouvez examiner et enregistrer le secteur vertical.

## <a name="things-to-consider"></a>Informations importantes

1. Des fonctionnalités de filtre supplémentaires existent sur le contenu de connexion.

    - Vous pouvez également créer un filtre sur un alias pour les propriétés source du connecteur
    - Si un secteur vertical possède plusieurs connexions, vous pouvez créer un filtre commun sur ces connexions. Pour ce faire, vous pouvez créer le filtre sur un alias commun qui alias les propriétés source entre les différentes connexions. Par exemple, vous pouvez créer un filtre **Auteur** sur une connexion ServiceNow et Jira en créant des alias comme suit :

    | Connection | Propriété | Alias |
    | --- | --- | --- |
    | Service Now | Propriétaire | Auteur |
    | Jira | Publisher | Auteur |

1. Les filtres existent dans l’étendue d’un secteur vertical.

    - Si un filtre est créé dans un secteur vertical qui se trouve au niveau de l’organisation, le filtre n’est visible qu’au niveau de l’organisation.
    - Si un filtre est créé dans un secteur vertical qui se trouve au niveau du site, le filtre n’est visible qu’au niveau du site.

## <a name="known-limitations"></a>Limitations connues

1. Vous pouvez actuellement créer des filtres uniquement sur les propriétés gérées & type de date.
1. Vous ne pouvez pas créer de filtres hiérarchiques.

## <a name="resources"></a>Ressources

[Gérer des secteurs verticaux et des types de résultats](customize-search-page.md)
