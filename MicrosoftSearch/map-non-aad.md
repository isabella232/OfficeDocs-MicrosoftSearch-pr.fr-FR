---
title: Mappage des identités non AAD
ms.author: monaray
author: monaray97
manager: jameslau
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
ROBOTS: NOINDEX, NOFOLLOW
description: procédure de mappage des identités non AAD
ms.openlocfilehash: be479cfd9dad585e83b5a39ff3ce4a84b9d41676
ms.sourcegitcommit: 77ec27736f3c8434b2ac47e10897ac2606ee8a03
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/11/2020
ms.locfileid: "48992859"
---
# <a name="map-your-non-azure-ad-identities"></a>Mapper vos identités non Azure AD  

Cet article vous guide tout au long des étapes de mappage de vos identités non Azure AD à vos identités Azure AD, de sorte que les utilisateurs de votre liste de contrôle d’accès avec des identités non Azure AD puissent voir les résultats de la recherche de connecteur étendues à ceux-ci.

Ces étapes s’appliquent uniquement aux administrateurs de recherche qui configurent un [ServiceNow](servicenow-connector.md) ou un connecteur [Salesforce](salesforce-connector.md) par Microsoft avec des autorisations de recherche pour « uniquement les personnes ayant accès à cette source de données » et le type d’identité « non AAD ».

>[!NOTE]
>Si vous configurez un connecteur Salesforce et que vous sélectionnez **uniquement les personnes ayant accès à cette source de données** et le type d’identité **AAD** sur l’écran des autorisations de recherche, reportez-vous à la rubrique mapper votre article d' [identité Azure ad](map-aad.md) pour obtenir la procédure de mappage des identités Azure ad.  

## <a name="steps-for-mapping-your-non-azure-ad-properties"></a>Étapes de mappage de vos propriétés d’annonce non Azure

### <a name="1-select-an-azure-ad-user-property"></a>1. Sélectionnez une propriété utilisateur Azure AD  

Vous pouvez sélectionner la propriété utilisateur Azure AD pour laquelle vous créez le mappage. Il s’agit de la propriété cible que vous souhaitez mapper à vos identités AD non Azure.  

Vous pouvez sélectionner l’une des propriétés Azure AD suivantes :

| Propriété Azure AD    | Définition           | Exemple         |
| :------------------- | :------------------- |:--------------- |
| Nom d’utilisateur principal (UPN)  | Un UPN se compose d’un préfixe UPN (le nom du compte d’utilisateur) et d’un suffixe UPN (nom de domaine DNS). Le préfixe est joint au suffixe en utilisant le symbole « @ ». | us1@contoso.onmicrosoft.com |
| ID Azure AD                 | Un ID Azure AD pour un utilisateur donné est le GUID unique de l’utilisateur.                 | 58006c96-9e6e-45ea-8c88-4a56851eefad            |
| ID de sécurité Active Directory (SID)                  | SID (identificateur de sécurité) est un identificateur unique utilisé par Active Directory pour identifier les objets en tant que principal de sécurité.                  | S-1-5-21-453406510-812318184-4183662089             |

### <a name="2-select-non-azure-ad-user-properties-to-map"></a>2. Sélectionnez les propriétés de l’utilisateur non Azure AD à mapper

Vous pouvez sélectionner les propriétés non Azure AD extraites de votre source de données pour appliquer des expressions régulières. Pour en savoir plus sur l’emplacement de ces propriétés dans votre source de données, voir les pages [ServiceNow](servicenow-connector.md) et [Salesforce](salesforce-connector.md) .  

Vous pouvez sélectionner une propriété d’utilisateur non Azure AD dans la liste déroulante et fournir une expression régulière à appliquer aux valeurs de ces propriétés d’utilisateur. Pour en savoir plus sur les expressions régulières, consultez la rubrique [Regular expression Reference]( https://docs.microsoft.com/dotnet/standard/base-types/regular-expression-language-quick-reference).  

Voici quelques exemples d’expressions régulières et leurs sorties appliquées à un exemple de chaîne : 

| Exemple de chaîne                  | Expression régulière                 | Sortie de l’expression régulière sur l’exemple de chaîne           |
| :------------------- | :------------------- |:---------------|
| Alexis Vasquez  | .* | Alexis Vasquez |
| Alexis Vasquez                 | ..$                 | faciles            |
| Alexis Vasquez                  | (\w +) $                  | Vasquez             |

Vous pouvez ajouter autant de propriétés d’utilisateur non Azure AD que vous le souhaitez pour les expressions. Vous pouvez appliquer différentes expressions régulières à la même propriété utilisateur si votre formule finale garantit que.  

### <a name="3-create-formula-to-complete-mapping"></a>3. créer une formule pour terminer le mappage

Vous pouvez combiner les sorties des expressions régulières appliquées à chacune de vos propriétés d’utilisateur non Azure AD pour former la propriété Azure AD sélectionnée à l’étape 1.

Dans la zone formule, « {0} » correspond à la sortie de l’expression régulière appliquée à la *première* propriété non Azure ad que vous avez sélectionnée. « {1} » correspond à la sortie de l’expression régulière appliquée à la *deuxième* propriété non Azure ad que vous avez sélectionnée. « {2} » correspond à la sortie de l’expression régulière appliquée à la *troisième* propriété non Azure ad, et ainsi de suite.  

Voici quelques exemples de formules avec des résultats d’expressions régulières et des sorties de formule : 

| Exemple de formule                  | Valeur de {0} on Sample User                 | Valeur de {1} on Sample User           | Sortie de la formule                  |
| :------------------- | :------------------- |:---------------|:---------------|
| {0}.{1} @contoso. com  | FirstName | prénom |firstname.lastname@contoso.com
| {0}@domain. com                 | identifi                 |             |userid@domain.com

Une fois que vous avez fourni votre formule, vous pouvez éventuellement cliquer sur **Aperçu** pour afficher un aperçu de 5 utilisateurs aléatoires de votre source de données avec leurs mappages utilisateur respectifs appliqués. La sortie de l’aperçu inclut la valeur des propriétés utilisateur non Azure AD sélectionnées à l’étape 2 pour ces utilisateurs et le résultat de la formule finale fournie à l’étape 3 pour cet utilisateur. Il indique également si la sortie de la formule peut être résolue en utilisateur Azure AD dans votre client via une icône « réussite » ou « échec ».  

>[!NOTE]
>Vous pouvez continuer à créer votre connexion si un ou plusieurs mappages utilisateur ont un État « échec » une fois que vous avez cliqué sur **Aperçu**. L’aperçu montre 5 utilisateurs aléatoires et leurs mappages à partir de votre source de données. Si le mappage que vous fournissez ne mappe pas tous les utilisateurs, vous pouvez observer ce cas.

## <a name="sample-non-azure-ad-mapping"></a>Exemple de mappage de publicités non Azure

Consultez la capture instantanée ci-dessous pour un exemple de mappage de publicités non Azure.

![Exemple de capture instantanée sur la façon de remplir la page de mappage des publicités non Azure](media/non-aad-mapping.png)

## <a name="limitations"></a>Limites  

- Un seul mappage est pris en charge pour tous les utilisateurs. Les mappages conditionnels ne sont pas pris en charge.  

- Vous ne pouvez pas modifier votre mappage une fois la connexion publiée.  

- Seules les expressions régulières par rapport aux propriétés utilisateur non AAD sont actuellement prises en charge pour la transformation.

- Seules 3 identités Azure AD vous pouvez choisir de mapper (UPN, ID Azure AD et SID AD).