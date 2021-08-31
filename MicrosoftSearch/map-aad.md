---
title: Mappage des identités AAD
ms.author: monaray
author: monaray97
manager: jameslau
ms.audience: Admin
ms.topic: article
ms.service: mssearch
ms.localizationpriority: medium
search.appverid:
- BFB160
- MET150
- MOE150
description: Étapes sur la façon de mameler les identités AAD
ms.openlocfilehash: d0292d77b3a0936ed60682b8388de1bb82ac43bb
ms.sourcegitcommit: cc9d743bcf5e998720ce9cd6eefb4061d913dc65
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/30/2021
ms.locfileid: "58701966"
---
# <a name="map-your-azure-ad-identities"></a>Mapper vos identités Azure AD   

Cet article vous explique les étapes de mappage de vos identités Azure AD à un identificateur unique pour votre source de données (identité non Azure AD) afin que les personnes de votre liste de contrôle d’accès avec des identités non Azure AD peuvent voir les résultats de recherche de connecteur qui leur sont propres.

Ces étapes sont uniquement pertinentes pour les administrateurs de recherche qui sont en train de définir un connecteur [Salesforce](salesforce-connector.md) par Microsoft avec des autorisations de recherche pour « Uniquement les personnes ayant accès à cette source de données » et le type d’identité « AAD ». Les étapes suivantes vous indiquent comment ma cartographier vos propriétés utilisateur Azure AD avec les ID de fédération **de vos utilisateurs.**

>[!NOTE]
>Si vous êtes en train de définir un connecteur [Salesforce](salesforce-connector.md) et sélectionnez uniquement les personnes ayant accès à cette **source** de données et ce type d’identité **non-AAD** sur l’écran d’autorisations de recherche, reportez-vous à l’article Ma cartographier vos [identités non Azure AD pour](map-non-aad.md) obtenir des étapes sur la façon de mameler des identités non Azure AD.  

## <a name="steps-for-mapping-your-azure-ad-properties"></a>Étapes de mappage de vos propriétés Azure AD

### <a name="1-select-azure-ad-user-properties-to-map"></a>1. Sélectionnez les propriétés utilisateur Azure AD à ma map

Vous pouvez sélectionner les propriétés Azure AD que vous devez ma cartographier sur l’ID de fédération.

Vous pouvez sélectionner une propriété utilisateur Azure AD dans ladown. Vous pouvez également ajouter autant de propriétés utilisateur Azure AD que vous le souhaitez si ces propriétés sont nécessaires pour créer le mappage d’ID de fédération pour votre organisation.

### <a name="2-create-formula-to-complete-mapping"></a>2. Créer une formule pour terminer le mappage

Vous pouvez combiner les valeurs des propriétés utilisateur Azure AD pour former l’ID de fédération unique.

Dans la zone de formule, « » correspond à la première propriété {0} Azure AD que vous avez sélectionnée.  « {1} " correspond à la *deuxième* propriété Azure AD que vous avez sélectionnée. « {2} " correspond à la *troisième* propriété Azure AD, etc.  

Voici quelques exemples de formules avec des exemples de sorties d’expression régulière et de sorties de formule :

| Exemple de formule                  | Valeur de propriété pour {0} un exemple d’utilisateur                 | Valeur de propriété pour {1} un exemple d’utilisateur           | Sortie de formule                  |
| :------------------- | :------------------- |:---------------|:---------------|
| {0}.{1} @contoso.com  | firstname | lastname |firstname.lastname@contoso.com
| {0}@domain.com                 | userid                 |             |userid@domain.com

Après avoir fourni votre formule,  vous pouvez éventuellement cliquer sur Aperçu pour afficher un aperçu de 5 utilisateurs aléatoires de votre source de données avec leurs mappages d’utilisateur respectifs appliqués. La sortie de l’aperçu inclut la valeur des propriétés utilisateur Azure AD sélectionnées à l’étape 1 pour ces utilisateurs et la sortie de la formule finale fournie à l’étape 2 pour cet utilisateur. Il indique également si la sortie de la formule peut être résolue vers un utilisateur Azure AD dans votre client via une icône « Réussite » ou « Échec ».  

>[!NOTE]
>Vous pouvez continuer à créer votre connexion si un ou plusieurs mappages utilisateur ont l’état « Échec » après avoir cliqué sur **Aperçu.** L’aperçu montre 5 utilisateurs aléatoires et leurs mappages à partir de votre source de données. Si le mappage que vous fournissez ne ma mappage pas tous les utilisateurs, vous pouvez faire l’expérience de ce cas.

## <a name="sample-azure-ad-mapping"></a>Exemple de mappage Azure AD

Consultez la capture instantanée ci-dessous pour obtenir un exemple de mappage Azure AD.

![Exemple de capture instantanée de la page de mappage Azure AD.](media/aad-mapping.png)

## <a name="limitations"></a>Limites  

- Un seul mappage est pris en charge pour tous les utilisateurs. Les mappages conditionnels ne sont pas pris en charge.  

- Vous ne pouvez pas modifier votre mappage une fois la connexion publiée.  

- Les expressions regex par rapport aux propriétés utilisateur Azure AD ne sont pas pris en charge pour la transformation d’Azure AD en ID de fédération.