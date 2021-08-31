---
title: Gérer les filtres
ms.author: v-revathib
author: revathi-b
manager: jeffkizn
ms.audience: Admin
ms.topic: article
ms.service: mssearch
ms.localizationpriority: medium
search.appverid:
- BFB160
- MET150
- MOE150
description: Gérer les filtres à utiliser sur le SERP
ms.openlocfilehash: c614d4b60c746f2e18fdb3352281891ea5134373
ms.sourcegitcommit: cc9d743bcf5e998720ce9cd6eefb4061d913dc65
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/30/2021
ms.locfileid: "58702192"
---
# <a name="manage-filters"></a>Gérer les filtres

Les filtres permettent aux utilisateurs d’affiner les résultats de leurs requêtes et d’afficher les résultats affinés. Vous pouvez personnaliser les filtres disponibles pour vos utilisateurs dans le Recherche Microsoft expérience utilisateur.

Deux types de filtres sont disponibles sur la page de recherche.

- Filtres « out of the box
- Filtres personnalisés

> [!NOTE]
> Les filtres personnalisés sont actuellement en prévisualisation pour les administrateurs et les utilisateurs finaux dans la version ciblée. Pour plus d’informations sur la prévisualisation, voir [Les fonctionnalités d’aperçu des connecteurs.](connectors-overview.md#what-are-the-preview-features)

## <a name="out-of-the-box-filters"></a>Filtres « out of the box

Les filtres prêts à l’emploi sont disponibles par défaut dans les secteurs verticaux de recherche tels que Tous, Fichiers, Images et Actualités. Dans les secteurs verticaux « All » et « File », vous pouvez voir le filtre « Type de fichier » sur la propriété FileType et le filtre « Last modified » sur la propriété LastModifiedTime. Ces filtres sont disponibles dans SharePoint Accueil, Office.com, Sites SharePoint et Travail vertical dans Bing.

## <a name="custom-filters"></a>Filtres personnalisés

Des filtres peuvent être ajoutés aux secteurs verticaux de recherche personnalisés au niveau de l’organisation et du site. Les propriétés gérées utilisables dans une recherche refinable sont utilisées pour configurer des filtres dans l’Assistant Administration verticale.  Ensuite, un filtre personnalisé peut être créé à l’intérieur d’un secteur vertical basé sur une propriété de connexion. Par exemple, vous pouvez créer un filtre Publié sur pour une connexion ServiceNow à l’intérieur d’un secteur vertical.

Les filtres configurés pour les secteurs verticaux dans l’étendue Organisation seront disponibles au niveau de l’organisation. Les filtres peuvent également être configurés dans l’étendue du site.  

## <a name="create-organization-level-filters"></a>Créer des filtres au niveau de l’organisation

1. In  [Centre d’administration Microsoft 365](https://admin.microsoft.com/), go to  [**Verticals**](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/verticals)
2. Sélectionnez votre secteur vertical préféré où vous souhaitez créer un filtre, puis cliquez sur **Modifier.**  
3. Accédez à l’étape Filtres dans l’Assistant du secteur vertical.
4. Cliquez **sur Ajouter un filtre pour** configurer des filtres sur les propriétés gérées utilisables dans une recherche dans une recherche dans une recherche.
5. Après avoir ajouté des filtres, vous pouvez examiner et enregistrer le secteur vertical.

## <a name="create-sharepoint-site-level-filters"></a>Créer des SharePoint au niveau du site

1. Dans [SharePoint centre d’administration,](https://sharepoint.com/)Paramètres.
2. Recherchez la section Recherche Microsoft, puis sélectionnez **Configurer Recherche Microsoft pour cette collection de sites.**
3. Dans le volet de navigation, sélectionnez Expérience personnalisée, puis  **sélectionnez Verticals**.
4. Sélectionnez votre secteur vertical préféré pour créer le filtre, puis cliquez sur **Modifier.**
5. Accédez à l’étape Filtres dans l’Assistant du secteur vertical.
6. Cliquez **sur Ajouter un filtre pour** configurer des filtres sur les propriétés gérées utilisables dans une recherche dans une recherche dans une recherche.
7. Après avoir ajouté des filtres, vous pouvez examiner et enregistrer le secteur vertical.

## <a name="filter-across-multiple-properties"></a>Filtrer plusieurs propriétés

Les secteurs verticaux peuvent être créés avec une ou plusieurs sources de contenu. Lorsqu’un secteur vertical est configuré avec plusieurs sources de contenu, la liste des propriétés de l’affinement indique à quelle source de contenu chaque propriété utilisable dans une recherche dans une recherche affinement appartient. Les propriétés gérées courantes sont fusionnées en fonction du nom (ou de l’alias) et du type de données. Les filtres peuvent également être configurés sur ces propriétés communes. Pour ce faire, vous créez le filtre sur un alias commun qui alias les propriétés source sur les différentes connexions. Par exemple, vous pouvez créer un filtre **Auteur** sur ServiceNow et une connexion Jira en créant des alias comme suit :

 | Connection | Propriété | Alias |
 | --- | --- | --- |
 | Service Now | Propriétaire | Auteur |
 | Jira | Éditeur | Auteur |

## <a name="important-details"></a>Détails importants

- Les filtres peuvent uniquement être ajoutés aux secteurs verticaux personnalisés. Les nouveaux filtres ne peuvent pas être ajoutés aux secteurs verticaux tels que Tous, Fichiers, Personnes, Sites, Actualités.
- Les filtres sont configurables sur les propriétés Text et DateTime.
- Vous êtes limité à un total de 50 filtres.
- L’ordre des filtres prêt à l’utilisation ne peut pas être ajusté.
- Les filtres ne sont pas pris en charge OneDrive contenu. Les valeurs de filtre correspondant aux résultats de recherche OneDrive contenu n’apparaissent pas sur les filtres.
- Les valeurs de filtre personnalisées afficheront les options SharePoint contenu et non à partir du contenu One Drive.Par exemple, si vous créez un filtre personnalisé pour « Auteur » et que le contenu SharePoint contient uniquement les résultats d’une auteur, « Amy » et le contenu OneDrive contient uniquement les résultats d’un auteur appelé « John » , le filtre personnalisé Auteur affiche « Amy » comme seule option.
- Une valeur de filtre affichée pour SharePoint contenu s’applique OneDrive contenu lorsqu’il est utilisé.
