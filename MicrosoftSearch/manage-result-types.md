---
title: Gérer les types de résultats
ms.author: jypal
author: jypal6
manager: jeffkizn
ms.audience: Admin
ms.topic: article
ms.service: mssearch
ms.localizationpriority: medium
search.appverid:
- BFB160
- MET150
- MOE150
ROBOTS: NOINDEX
description: Gérer les types de résultats sur la page des résultats de la recherche
ms.openlocfilehash: ea6926a8923f4436f21047c9ac4cb95625ecb163
ms.sourcegitcommit: 967a02ee932f8a6cee70cfd78bb0c8b1b78d07c4
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/05/2021
ms.locfileid: "60127766"
---
# <a name="manage-result-types"></a>Gérer les types de résultats

Vous pouvez définir la façon dont les résultats de la recherche sont affichés sur la page des résultats de la recherche en concevant [la](customize-results-layout.md) disposition à l’aide de types de résultats. La disposition des résultats vous permet d’afficher des informations utiles directement dans les résultats de la recherche afin que les utilisateurs trouvent rapidement les informations dont ils ont besoin.

Les types de contenu intégrés tels que les fichiers et les personnes ont une disposition standard qui ne peut pas être modifiée. Les types de résultats sont utilisés [pour Graph connecteurs.](connectors-overview.md) Lorsque vous configurez un connecteur avec des mappages de propriétés, Recherche Microsoft utilisera une disposition des résultats de recherche par défaut pour les résultats de recherche du connecteur. Le titre *de l’étiquette* est le plus important . Vous devez toujours avoir une propriété affectée à cette étiquette pour utiliser la disposition des résultats par défaut. Toutefois, la création d’un type de résultat personnalisé pour le contenu de votre connecteur peut rendre ces résultats plus pertinents pour vos utilisateurs.

Lorsque vous utilisez des secteurs verticaux et du contenu de connecteur, vous devez créer un type de résultat ou réaliser les mappages pour une disposition par défaut. Si vous ne le faites pas non plus, le secteur vertical n’affiche aucun résultat de recherche.

## <a name="understanding-result-types"></a>Comprendre les types de résultats

Créez votre propre disposition [des résultats de](customize-results-layout.md) recherche et remplacez la disposition des résultats de recherche par défaut en créant un type de résultat. Un type de résultat de recherche est une règle qui entraîne l’affichage de différents types de résultats de recherche différemment. Il se compose des paramètres suivants :

- **Une ou plusieurs conditions**   pour comparer chaque résultat de recherche. La source de contenu et le titre sont des exemples de conditions.
- Disposition **des résultats à** utiliser pour les résultats de recherche qui   répondent aux conditions. La disposition qui en résulte contrôle la façon dont les résultats qui répondent aux conditions apparaissent sur la page des résultats de la recherche.

Vous pouvez utiliser plusieurs types de résultats pour le contenu affiché dans un secteur vertical. Cela peut être important lorsque vous combinez plusieurs sources de contenu dans un seul secteur vertical. Il peut également être utilisé pour une disposition plus efficace, même s’il n’existe qu’un seul type de contenu. Par exemple, dans un secteur vertical qui affiche les détails de l’incident, vous pouvez personnaliser les incidents de « gravité élevée » pour qu’ils affichent des couleurs plus visibles que les incidents de « faible gravité ». Pour ce faire, vous pouvez définir des conditions sur la propriété « severity » dans la section **Règles.**

## <a name="create-or-update-result-types"></a>Créer ou mettre à jour des types de résultats

L’expérience de gestion des types de résultats est pilotée par l’Assistant. Vous êtes guidé à travers les étapes pour définir le nom, la source de contenu, les règles et la disposition. Les types de résultats peuvent être personnalisés au niveau de l’organisation SharePoint site.

### <a name="manage-organization-level-result-types"></a>Gérer les types de résultats au niveau de l’organisation

1. Dans  [Centre d'administration Microsoft 365,](https://admin.microsoft.com/)allez à la page Types de [**résultats**](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/resulttypes) dans la section **Personnalisation.**
2. Pour créer un type de résultat, cliquez sur **Ajouter** ou sélectionnez un type existant pour le modifier.
3. Après avoir configuré votre type de résultat, vous pouvez l’examiner et l’enregistrer.

### <a name="manage-site-level-result-types"></a>Gérer les types de résultats au niveau du site

1. Dans le site Sharepoint où vous souhaitez gérer les types de résultats, ouvrez le panneau paramètres en cliquant sur l’engrenage.
2. Sélectionnez **Informations sur le** site, puis afficher tous les **paramètres du site.**  
3. Recherchez la section Recherche Microsoft, puis sélectionnez **Configurer les paramètres de recherche.**
4. Dans le volet de navigation, sélectionnez Expérience personnalisée, puis sélectionnez le **type de résultat.**
5. Pour ajouter un type de résultat, cliquez sur **Ajouter.** Ou, pour modifier un type de résultat, sélectionnez le type de résultat dans la liste.
6. Après avoir modifié un type de résultat, vous pouvez passer en revue et enregistrer le type de résultat.

## <a name="troubleshooting"></a>Résolution des problèmes

Voici une liste des problèmes courants que vous pouvez voir et des actions à prendre pour les résoudre.

|Problème  |Action  |
|---------|---------|
| Je ne vois pas ma disposition des résultats sur la page de recherche, même si j’en ai créé une. | Il peut y avoir un délai de quelques minutes car ces paramètres sont mis en cache. Patientez quelques minutes et essayez à nouveau.        |
| Je ne vois aucune source de contenu sur la page de type de résultat. | Assurez-vous que vous avez configuré des connecteurs et des données indexées.   |
