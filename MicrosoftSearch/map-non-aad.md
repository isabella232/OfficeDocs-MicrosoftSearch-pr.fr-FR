---
title: Mappage des identités non-AAD
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
description: Étapes sur la façon de mameler des identités non-AAD
ms.openlocfilehash: f433da10347ef59acf7675ec65da8acbd7f0f347
ms.sourcegitcommit: ca5ee826ba4f4bb9b9baabc9ae8a130011c2a3d0
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/15/2021
ms.locfileid: "59334478"
---
# <a name="map-your-non-azure-ad-identities"></a>Ma cartographier vos identités autres qu’Azure AD  

Cet article vous explique les étapes de mappage de vos identités non-Azure AD à vos identités Azure AD afin que les personnes de votre liste de contrôle d’accès (ACL) avec des identités non Azure AD peuvent voir les résultats de recherche de connecteur qui leur sont spécifiques.

Ces étapes sont uniquement pertinentes pour les administrateurs de recherche qui sont en train de définir des connecteurs [Cloud](confluence-cloud-connector.md)Cloud, [ServiceNow Knowledge,](servicenow-knowledge-connector.md) [ServiceNow Catalog](servicenow-catalog-connector.md) ou [Salesforce](salesforce-connector.md) par Microsoft avec des autorisations de recherche pour « Uniquement les personnes ayant accès à cette source de données » et le type d’identité « Non-AAD ».

>[!NOTE]
>Si vous devez définir un connecteur Salesforce et sélectionner uniquement les personnes ayant accès à cette **source** de données et au type d’identité **AAD** sur l’écran d’autorisations de recherche, reportez-vous à l’article Ma cartographier vos [identités Azure AD](map-aad.md) pour obtenir des étapes sur la façon de mameler les identités Azure AD.  

## <a name="steps-for-mapping-your-non-azure-ad-properties"></a>Étapes de mappage de propriétés autres qu’Azure AD

### <a name="1-select-an-azure-ad-user-property"></a>1. Sélectionnez une propriété utilisateur Azure AD  

Vous pouvez sélectionner la propriété utilisateur Azure AD pour qui vous créez le mappage. Il s’agit de la propriété cible sur qui vous souhaitez ma cartographier vos identités non Azure AD.  

Vous pouvez sélectionner l’une des propriétés Azure AD suivantes :

| Propriété Azure AD    | Définition           | Exemple         |
| :------------------- | :------------------- |:--------------- |
| Nom d’utilisateur principal (UPN)  | Un upn se compose d’un préfixe UPN (nom du compte d’utilisateur) et d’un suffixe UPN (un nom de domaine DNS). Le préfixe est joint au suffixe à l’aide du symbole « @ ». | us1@contoso.onmicrosoft.com |
| Azure AD ID                 | Un ID Azure AD pour un utilisateur donné est le GUID unique de l’utilisateur.                 | 58006c96-9e6e-45ea-8c88-4a56851eefad            |
| ID de sécurité Active Directory (SID)                  | SID (Security Identifier) est un identificateur unique qu’Active Directory utilise pour identifier les objets en tant que principal de sécurité.                  | S-1-5-21-453406510-812318184-4183662089             |

### <a name="2-select-non-azure-ad-user-properties-to-map"></a>2. Sélectionnez les propriétés utilisateur autres qu’Azure AD à ma choix

Vous pouvez sélectionner des propriétés non Azure AD tirées de votre source de données pour appliquer des expressions régulières. Pour en savoir plus sur l’endroit où trouver ces propriétés dans votre source de données, consultez les pages [Cloud Cloud,](confluence-cloud-connector.md) [ServiceNow Knowledge,](servicenow-knowledge-connector.md) [ServiceNow Catalog](servicenow-catalog-connector.md) et [Salesforce.](salesforce-connector.md)  

Vous pouvez sélectionner une propriété utilisateur non Azure AD dans ladown et fournir une expression régulière à appliquer à ces valeurs de propriété utilisateur.

Voici quelques exemples d’expressions régulières et leurs sorties appliquées à un exemple de chaîne : 

| Exemple de chaîne                  | Expression régulière                 | Sortie de l’expression régulière sur l’exemple de chaîne           |
| :------------------- | :------------------- |:---------------|
| Alexis Vasquez  | .* | Alexis Vasquez |
| Alexis Vasquez                 | ..$                 | ez            |
| Alexis Vasquez                  | (\w+)$                  | Vasquez             |

Vous pouvez ajouter autant de propriétés utilisateur non Azure AD que vous le souhaitez pour les expressions. Vous pouvez appliquer différentes expressions régulières à la même propriété utilisateur si votre formule finale le justifie.  

### <a name="3-create-formula-to-complete-mapping"></a>3. Créer une formule pour terminer le mappage

Vous pouvez combiner les sorties des expressions régulières appliquées à chacune de vos propriétés utilisateur non Azure AD pour former la propriété Azure AD sélectionnée à l’étape 1.

Dans la zone de formule, « » correspond à la sortie de l’expression régulière appliquée à la première propriété {0} non Azure AD que vous avez  sélectionnée. « " correspond à la sortie de l’expression régulière appliquée à la {1} *deuxième* propriété non Azure AD que vous avez sélectionnée. « " correspond à la sortie de l’expression régulière appliquée à la {2} *troisième* propriété non Azure AD, etc.  

Voici quelques exemples de formules avec des exemples de sorties d’expression régulière et de sorties de formule : 

| Exemple de formule                  | Valeur de {0} l’exemple d’utilisateur                 | Valeur de {1} l’exemple d’utilisateur           | Sortie de formule                  |
| :------------------- | :------------------- |:---------------|:---------------|
| {0}.{1} @contoso.com  | firstname | lastname |firstname.lastname@contoso.com
| {0}@domain.com                 | userid                 |             |userid@domain.com

Après avoir fourni votre formule,  vous pouvez éventuellement cliquer sur Aperçu pour afficher un aperçu de 5 utilisateurs aléatoires de votre source de données avec leurs mappages d’utilisateur respectifs appliqués. La sortie de l’aperçu inclut la valeur des propriétés utilisateur non Azure AD sélectionnées à l’étape 2 pour ces utilisateurs et la sortie de la formule finale fournie à l’étape 3 pour cet utilisateur. Il indique également si la sortie de la formule peut être résolue vers un utilisateur Azure AD dans votre client via une icône « Réussite » ou « Échec ».  

>[!NOTE]
>Vous pouvez continuer à créer votre connexion si un ou plusieurs mappages utilisateur ont l’état « Échec » après avoir cliqué sur **Aperçu.** L’aperçu montre 5 utilisateurs aléatoires et leurs mappages à partir de votre source de données. Si le mappage que vous fournissez ne ma mappage pas tous les utilisateurs, vous pouvez faire l’expérience de ce cas.

## <a name="sample-non-azure-ad-mapping"></a>Exemple de mappage non Azure AD

Consultez la capture instantanée ci-dessous pour obtenir un exemple de mappage non Azure AD.

![Exemple d’instantané de la façon de remplir la page de mappage non-Azure AD.](media/non-aad-mapping.png)

## <a name="limitations"></a>Limites  

- Un seul mappage est pris en charge pour tous les utilisateurs. Les mappages conditionnels ne sont pas pris en charge.  

- Vous ne pouvez pas modifier votre mappage une fois la connexion publiée.  

- Seules les expressions regex basées sur les propriétés utilisateur non-AAD sont actuellement pris en charge pour la transformation.

- Vous pouvez choisir d’utiliser uniquement 3 identités Azure AD (UPN, Azure AD ID et AD SID).