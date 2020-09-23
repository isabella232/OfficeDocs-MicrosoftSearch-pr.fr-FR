---
title: Personnaliser la page Microsoft Search
ms.author: jeffkizn
author: jypal
manager: jeffkizn
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: Ajouter des secteurs verticaux de recherche et personnaliser les résultats de la recherche
ms.openlocfilehash: 8b212f385d126b4f6c3513b066936db28387377f
ms.sourcegitcommit: be0c64845477127d73ee24dc727e4583ced3d0e6
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/22/2020
ms.locfileid: "48206967"
---
# <a name="customize-the-search-results-page"></a>Personnaliser la page de résultats de recherche

Vous pouvez créer des secteurs verticaux et des types de résultats de recherche pour personnaliser les résultats de la recherche que les utilisateurs voient lorsqu’ils recherchent dans Microsoft [SharePoint](https://sharepoint.com/), [Microsoft Office](https://office.com)et Microsoft Search dans [Bing](https://bing.com). Les secteurs verticaux permettent aux utilisateurs de trouver plus facilement les informations qu’ils sont autorisés à consulter. Par exemple, vous pouvez créer un secteur vertical de recherche pour les données d’analyse marketing à partir de logiciels tiers pour vos utilisateurs dans le service marketing. Vous pouvez également définir des types de résultats et personnaliser la disposition de ces données.  

Vous pouvez créer des types de résultats verticaux et de résultats aux niveaux suivants :

- **Niveau** de l’Organisation : lorsque vous ajoutez une verticale au niveau de l’organisation, elle apparaît sur la page de résultats de recherche lorsque les utilisateurs recherchent à partir de leur page de démarrage [SharePoint](https://sharepoint.com/) , sur [Office](https://office.com)ou sur [Bing](https://bing.com).
- **Niveau site** – par exemple, vous souhaiterez peut-être autoriser les employés de votre service clientèle à rechercher des incidents de *gravité 1* directement à partir du site SharePoint de leur service.

## <a name="search-verticals-explained"></a>Explication des secteurs verticaux de recherche

En haut de la page résultats de la recherche Microsoft, il existe une rangée d’onglets. Il s’agit des secteurs verticaux de recherche. Un secteur vertical de recherche affiche uniquement les résultats d’un certain type ou de certains contenus. Il s’agit par exemple des **fichiers** ou des **Actualités**. Par défaut, Microsoft Search affiche les informations verticales, les **personnes**, **les** **fichiers**, les **sites**et les **Actualités**.  

Vous pouvez ajouter des secteurs verticaux de recherche pertinents pour votre organisation. Celles-ci apparaissent sur la page des résultats de recherche Microsoft dans [SharePoint](https://sharepoint.com/), [Office](https://Office.com)et [Bing](https://bing.com). Par exemple, vous pouvez créer un secteur vertical pour le contenu lié au marketing et un autre pour les ventes, en fonction du type d’informations dont chaque groupe a besoin. Vous pouvez ajouter des valeurs verticales pour afficher les résultats uniquement à partir du contenu indexé via des connecteurs.  

>[!NOTE]
> Les formes verticales et les types de résultats sont actuellement en aperçu dans le cadre de l’aperçu des connecteurs Microsoft Graph. Pour plus d’informations sur l’aperçu, voir [connecteurs Preview](connectors-preview.md). Pour participer à l’aperçu, vous devez d’abord envoyer le formulaire d’abonnement de l' [aperçu des connecteurs Microsoft Graph](https://forms.office.com/Pages/ResponsePage.aspx?id=v4j5cvGGr0GRqy180BHbRxWYgu82J_RFnMMATAS6_chUNVYwNU1CMDNZUDBSSDZKWVo2RDJDRjRLQi4u).

## <a name="things-to-consider"></a>Informations importantes

Avant de commencer, assurez-vous que le connecteur a été indexé. Cela peut prendre jusqu’à 48 heures, en fonction de la taille du fichier.

Vous ne pouvez pas créer de vertical pour le contenu qui réside dans [SharePoint](https://sharepoint.com/).

Il existe trois étapes de base pour ajouter un secteur vertical :

1. Créez le secteur vertical. Dans cette étape, vous définissez le nom de la verticale, la source de contenu et l’étendue du contenu à rechercher.
2. Définissez à quoi ressemblera les résultats de cette forme verticale.  
3. Activer le secteur vertical (à afficher) à partir de la page de liste verticale.

## <a name="step-1-create-the-search-vertical"></a>ÉTAPE 1 : créer le secteur vertical de recherche

Une fois que vous avez démarré l’Assistant, vous pouvez définir le nom vertical, la source de contenu et l’étendue du contenu à rechercher. Le secteur vertical est créé dans un état désactivé. Vous l’activerez plus tard.

Vous pouvez utiliser un ensemble limité de [langage de requête de mot clé (KQL)](https://docs.microsoft.com/sharepoint/dev/general-development/keyword-query-language-kql-syntax-reference) pour affiner l’étendue. Cette page répertorie les propriétés disponibles. Nous vous recommandons d’utiliser des mots clés FREETEXT et des restrictions de propriété avec des opérateurs booléens pour créer le KQL.

### <a name="create-a-vertical-at-the-organization-level"></a>Créer un secteur vertical au niveau de l’Organisation

Pour créer le secteur vertical sur Microsoft Search dans [SharePoint](https://sharepoint.com/) famille, [Office](https://office.com)ou [Bing](https://bing.com), procédez comme suit :

1. Dans le [Centre d’administration Microsoft 365](https://admin.microsoft.com), accédez à la [**barre verticale**](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/verticals).
1. Sélectionnez **Ajouter** pour commencer.  

### <a name="create-a-vertical-at-the-site-level"></a>Créer une verticale au niveau du site

1. Sur le site [SharePoint](https://sharepoint.com/) où vous souhaitez utiliser le secteur vertical, accédez à **paramètres**.
1. Sélectionnez **informations sur le site** , puis **Affichez tous les paramètres du site**.
1. Recherchez la section **Microsoft Search** , puis sélectionnez **configurer Microsoft Search pour cette collection de sites**.
1. Dans le volet de navigation, accédez à **expérience personnalisée**, puis sélectionnez l’onglet **verticales** .
1. Pour ajouter un secteur vertical, sélectionnez **Ajouter**.
  Pour modifier un secteur vertical, sélectionnez-le dans la liste.

N’oubliez pas que les secteurs verticaux sont créés dans un état désactivé. Elles doivent être activées pour que les utilisateurs puissent les voir.

## <a name="step-2-create-the-result-types"></a>ÉTAPE 2 : créer les types de résultats

Vous pouvez définir le mode d’affichage des résultats dans le secteur vertical en concevant la disposition à l’aide des types de résultat. La disposition des résultats vous permet d’afficher des informations importantes directement dans les résultats de la recherche, afin que les utilisateurs n’aient pas à sélectionner chaque résultat pour voir s’ils ont trouvé ce qu’ils cherchent.

Un type de résultat de recherche est une règle qui entraîne l'affichage, sous diverses formes, de différents types de résultats de recherche. Il se compose des éléments suivants :

- **Une ou plusieurs conditions** pour comparer chaque résultat de recherche par rapport à, comme la source de contenu du résultat de la recherche.  
- Une **disposition de résultats** à utiliser pour les résultats de recherche qui remplissent les conditions. La disposition des résultats contrôle la manière dont les résultats qui remplissent les conditions apparaissent et se comportent sur une page de résultats de la recherche.

**Vous devez créer au moins un type de résultat pour les résultats à afficher sur le vertical.** Vous pouvez créer plusieurs types de résultats pour chaque secteur vertical, ce qui vous permet d’utiliser des dispositions différentes selon le type de résultats. Par exemple, vous pouvez personnaliser les incidents de *gravité 1* pour obtenir des couleurs plus visibles et une police plus grande comparée aux incidents de *gravité 3* .

Une fois que vous avez démarré l’Assistant, vous pouvez définir le nom, la source de contenu et les conditions du type de résultat. Vous pouvez définir la priorité du type de résultat à partir de l’affichage de liste.
  
### <a name="create-a-result-type-at-the-organization-level"></a>Créer un type de résultat au niveau de l’Organisation

1. Dans le [Centre d’administration Microsoft 365](https://admin.microsoft.com), accédez à [**types de résultats**](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/resulttypes).
1. Pour ajouter un **type de résultat**, sélectionnez **Ajouter**. Pour modifier un type de résultat, sélectionnez le type de résultat dans la liste correspondante.

### <a name="create-a-results-type-at-the-site-level"></a>Créer un type de résultats au niveau du site

1. Sur le site [SharePoint](https://sharepoint.com/) où vous souhaitez créer le type de résultat, accédez à **paramètres**.
1. Sélectionnez **informations sur le site** , puis **Affichez tous les paramètres du site**.
1. Recherchez la section Microsoft Search, puis sélectionnez **configurer Microsoft Search pour cette collection de sites**.
1. Dans le volet de navigation, accédez à **expérience personnalisée**et sélectionnez l’onglet **type de résultat** .
1. Pour ajouter un type de résultat, sélectionnez **Ajouter**.  Ou, pour modifier un type de résultat, sélectionnez le type de résultat dans la liste.

### <a name="view-the-vertical-after-its-enabled"></a>Afficher le secteur vertical une fois qu’il est activé

Une fois que vous avez activé le secteur vertical, il peut prendre un certain temps avant de pouvoir l’afficher. Si vous ne souhaitez pas attendre une fois l’activation effectué, vous pouvez ajouter **cacheClear = true** à l’URL dans [SharePoint](https://sharepoint.com/) et [Office](https://office.com) pour afficher immédiatement la verticale.

## <a name="troubleshooting"></a>Résolution des problèmes

Voici une liste des problèmes courants que vous pouvez rencontrer et des actions à résoudre.

|Erreur  |Action  |
|---------|---------|
| Je vois un message d’erreur « un problème est survenu » sur le secteur vertical. | Les types vertical et de résultat sont tous deux nécessaires pour terminer l’installation. Assurez-vous que vous avez créé les deux pour la même source de contenu. |
| Je ne vois pas ma disposition de résultats, bien que j’en ai créé un. | Ces paramètres sont généralement mis en cache. Patientez quelques minutes, puis réessayez.        |
| Je ne vois aucune source de contenu sur la page de type de résultat ou vertical. | Assurez-vous que vous avez configuré les connecteurs et les données indexées.   |

## <a name="next-steps"></a>Étapes suivantes

[ÉTAPE 3 : personnaliser la disposition des résultats](customize-results-layout.md)
