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
ms.openlocfilehash: edc541e902965472295a835906ef36fcd7fba730
ms.sourcegitcommit: e1215758fd1325526e4b7b1612c3349137c6fbc3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/18/2020
ms.locfileid: "49716984"
---
# <a name="customize-the-search-results-page"></a>Personnaliser la page de résultats de recherche

Vous pouvez créer des secteurs verticaux et des types de résultats de recherche pour personnaliser les résultats de la recherche que les utilisateurs voient lorsqu’ils recherchent dans Microsoft [SharePoint](https://sharepoint.com/), [Microsoft Office](https://office.com)et Microsoft Search dans [Bing](https://bing.com). Les secteurs verticaux permettent aux utilisateurs de trouver plus facilement les informations qu’ils sont autorisés à consulter. Par exemple, vous pouvez créer un secteur vertical de recherche pour les données d’analyse marketing à partir de logiciels tiers pour vos utilisateurs dans le service marketing. Vous pouvez également définir des types de résultats et personnaliser la disposition de ces données.  

Vous pouvez créer des types de résultats verticaux et de résultats aux niveaux suivants :

- **Niveau** de l’Organisation : lorsque vous ajoutez une verticale au niveau de l’organisation, elle apparaît sur la page de résultats de recherche lorsque les utilisateurs recherchent à partir de leur page de démarrage [SharePoint](https://sharepoint.com/) , sur [Office](https://office.com)ou sur [Bing](https://bing.com).
- **Niveau site** – par exemple, vous souhaiterez peut-être autoriser les employés de votre service clientèle à rechercher des incidents de *gravité 1* directement à partir du site SharePoint de leur service.

## <a name="search-verticals-explained"></a>Explication des secteurs verticaux de recherche

En haut de la page résultats de la recherche Microsoft, il existe une rangée d’onglets. Il s’agit des secteurs verticaux de recherche. Un secteur vertical de recherche affiche uniquement les résultats d’un certain type ou de certains contenus. Il s’agit par exemple des **fichiers** ou des **Actualités**. Par défaut, Microsoft Search affiche les informations verticales, les **personnes**, **les** **fichiers**, les **sites** et les **Actualités**.  

Vous pouvez ajouter des secteurs verticaux de recherche pertinents pour votre organisation. Celles-ci apparaissent sur la page des résultats de recherche Microsoft dans [SharePoint](https://sharepoint.com/), [Office](https://Office.com)et [Bing](https://bing.com). Par exemple, vous pouvez créer un secteur vertical pour le contenu lié au marketing et un autre pour les ventes, en fonction du type d’informations dont chaque groupe a besoin. Vous pouvez ajouter des valeurs verticales pour afficher les résultats uniquement à partir du contenu indexé via des connecteurs.  

### <a name="multiple-connections-in-a-vertical"></a>Connexions multiples dans un secteur vertical

Un secteur vertical de recherche peut maintenant faire surface les résultats de plusieurs sources de connecteur. Cela offre davantage de souplesse dans la conception de votre page de résultats de recherche. L’expérience administrative existante du programme d’installation verticale vous permet de sélectionner plusieurs connexions dans l’étape « source de contenu ».
Si vous nommez précisément autant d’étiquettes sémantiques que possible, cette expérience sera améliorée. Vous pouvez ajouter des étiquettes sémantiques lors de la définition et de l’ingestion du schéma.

[Voici](#configure-connector-step-5-assign-property-labels) des informations supplémentaires sur la façon de créer et de gérer les étiquettes sémantiques.

### <a name="things-you-should-know"></a>Éléments que vous devez savoir

1. Une connexion ne peut être ajoutée en tant que source de contenu qu’en un seul vertical. La réutilisation de connexions sous plusieurs VERTICALS n’est pas autorisée.
2. Si vous avez besoin de configurer une requête pour un secteur vertical de recherche pour lequel plusieurs sources de connexion ont été ajoutées, les propriétés sources communes doivent être utilisées pour créer une requête de ce type.

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

1. Dans le [Centre d’administration Microsoft 365](https://admin.microsoft.com), accédez à la [**barre verticale**](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/verticals).
2. Sélectionnez **Ajouter** pour commencer.  

### <a name="create-a-vertical-at-the-site-level"></a>Créer une verticale au niveau du site

1. Sur le site [SharePoint](https://sharepoint.com/) où vous souhaitez utiliser le secteur vertical, accédez à **paramètres**.
2. Sélectionnez **informations sur le site** , puis **Affichez tous les paramètres du site**.
3. Recherchez la section **Microsoft Search** , puis sélectionnez **configurer Microsoft Search pour cette collection de sites**.
4. Dans le volet de navigation, accédez à **expérience personnalisée**, puis sélectionnez l’onglet **verticales** .
5. Pour ajouter un secteur vertical, sélectionnez **Ajouter**.
  Pour modifier un secteur vertical, sélectionnez-le dans la liste.

N’oubliez pas que les secteurs verticaux sont créés dans un état désactivé. Elles doivent être activées pour que les utilisateurs puissent les voir.

## <a name="step-2-create-the-result-types"></a>ÉTAPE 2 : créer les types de résultats

Vous pouvez définir le mode d’affichage des résultats dans le secteur vertical en concevant la disposition à l’aide des types de résultat. La disposition des résultats vous permet d’afficher des informations importantes directement dans les résultats de la recherche, afin que les utilisateurs n’aient pas à sélectionner chaque résultat pour voir s’ils ont trouvé ce qu’ils cherchent.

### <a name="default-search-result-layout"></a>Disposition des résultats de recherche par défaut

Une disposition de résultats de recherche par défaut s’affiche pour le contenu de connecteur si les **étiquettes** et la propriété de **contenu** ont été correctement mappées sur les propriétés source lors de la configuration du connecteur. Le **titre** de l’étiquette est l’étiquette la plus importante. Il est **vivement recommandé** d’attribuer une propriété à cette étiquette pour utiliser la disposition des résultats de la recherche par défaut.

### <a name="create-your-own-result-type"></a>Créer votre propre type de résultat

Vous pouvez choisir de créer votre propre disposition de résultats de recherche et remplacer la disposition par défaut des résultats de recherche en créant un **type de résultat**. Un type de résultat de recherche est une règle qui entraîne l'affichage, sous diverses formes, de différents types de résultats de recherche. Il se compose des éléments suivants :

- **Une ou plusieurs conditions** pour comparer chaque résultat de recherche par rapport à, comme la source de contenu du résultat de la recherche.  
- Une **disposition de résultats** à utiliser pour les résultats de recherche qui remplissent les conditions. La disposition des résultats contrôle la manière dont les résultats qui remplissent les conditions apparaissent et se comportent sur une page de résultats de la recherche.

**Si le mappage approprié n’est pas fait pour afficher la disposition des résultats de la recherche par défaut, yyou doit créer au moins un type de résultat pour les résultats à afficher sur le vertical.** Vous pouvez créer plusieurs types de résultats pour chaque secteur vertical, ce qui vous permet d’utiliser des dispositions différentes selon le type de résultats. Par exemple, vous pouvez personnaliser les incidents de *gravité 1* pour obtenir des couleurs plus visibles et une police plus grande comparée aux incidents de *gravité 3* .

Une fois que vous avez démarré l’Assistant, vous pouvez définir le nom, la source de contenu et les conditions du type de résultat. Vous pouvez définir la priorité du type de résultat à partir de l’affichage de liste.
  
### <a name="create-a-result-type-at-the-organization-level"></a>Créer un type de résultat au niveau de l’Organisation

1. Dans le [Centre d’administration Microsoft 365](https://admin.microsoft.com), accédez à [**types de résultats**](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/resulttypes).
2. Pour ajouter un **type de résultat**, sélectionnez **Ajouter**. Pour modifier un type de résultat, sélectionnez le type de résultat dans la liste correspondante.

### <a name="create-a-results-type-at-the-site-level"></a>Créer un type de résultats au niveau du site

1. Sur le site [SharePoint](https://sharepoint.com/) où vous souhaitez créer le type de résultat, accédez à **paramètres**.
2. Sélectionnez **informations sur le site** , puis **Affichez tous les paramètres du site**.
3. Recherchez la section Microsoft Search, puis sélectionnez **configurer Microsoft Search pour cette collection de sites**.
4. Dans le volet de navigation, accédez à **expérience personnalisée** et sélectionnez l’onglet **type de résultat** .
5. Pour ajouter un type de résultat, sélectionnez **Ajouter**.  Ou, pour modifier un type de résultat, sélectionnez le type de résultat dans la liste.

## <a name="step-3-view-the-vertical-after-its-enabled"></a>ÉTAPE 3 : afficher le secteur vertical après son activation

Une fois que vous avez activé le secteur vertical, il peut prendre un certain temps avant de pouvoir l’afficher. Si vous ne souhaitez pas attendre une fois l’activation effectué, vous pouvez ajouter **cacheClear = true** à l’URL dans [SharePoint](https://sharepoint.com/) et [Office](https://office.com) pour afficher immédiatement la verticale. Pour [Bing](https://bing.com), ajoutez **&features = UNCACHEDVERTICALS** à l’URL de travail vertical Work pour afficher les secteurs verticaux immédiatement. 

## <a name="troubleshooting"></a>Résolution des problèmes

Voici une liste des problèmes courants que vous pouvez rencontrer et des actions à résoudre.

|Erreur  |Action  |
|---------|---------|
| Je vois un message d’erreur « un problème est survenu » sur le secteur vertical. | Les types vertical et de résultat sont tous deux nécessaires pour terminer l’installation. Assurez-vous que vous avez créé les deux pour la même source de contenu. |
| Je ne vois pas ma disposition de résultats, bien que j’en ai créé un. | Ces paramètres sont généralement mis en cache. Patientez quelques minutes, puis réessayez.        |
| Je ne vois aucune source de contenu sur la page de type de résultat ou vertical. | Assurez-vous que vous avez configuré les connecteurs et les données indexées.   |

## <a name="next-steps"></a>Étapes suivantes

[ÉTAPE 3 : personnaliser la disposition des résultats](customize-results-layout.md)
