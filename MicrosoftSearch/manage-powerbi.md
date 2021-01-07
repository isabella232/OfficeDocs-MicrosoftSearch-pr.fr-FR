---
title: Gérer les réponses Power BI
ms.author: dawholl
author: dawholl
manager: jeffkizn
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
ms.assetid: c0c814d0-f7e4-444e-b18e-09beb45c9322
description: Gérer le mode d’affichage des données et des rapports Power BI dans les résultats de recherche
ms.openlocfilehash: e78b8b5d22f7a91d80832fb4f5b536afc277fb6c
ms.sourcegitcommit: 7294c953e7939e48f128656cc2f8f22705ae3f3d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/06/2021
ms.locfileid: "49773044"
---
# <a name="manage-power-bi-answers"></a>Gérer les réponses Power BI

Pour permettre aux utilisateurs de trouver plus facilement les données et les analyses dont ils ont besoin pour prendre des décisions éclairées, Microsoft Search a ajouté la prise en charge des rapports et des tableaux de bord Power BI. Voici quelques-uns des avantages de la recherche Power BI :

* **Facilité d’utilisation :** Cette expérience de recherche prédéfinie permet aux utilisateurs de trouver facilement et rapidement des tableaux de bord et des rapports Power BI au sein de votre organisation.
* **Contenu plus riche :** Pour que les résultats de la recherche Power BI soient plus utiles, ils incluent des informations clés telles que le type de contenu — tableau de bord ou rapport — et l’équipe ou la personne propriétaire.
* **Protection des données intégrée :** Les résultats Power BI apparaissent uniquement pour les utilisateurs qui ont accès au tableau de bord ou aux rapports.
* **Expérience de recherche unifiée :** Pour conserver une expérience cohésive, les résultats Power BI sont cohérents entre tous les points d’entrée de la recherche. Chaque fois que vous recherchez, vous obtiendrez les mêmes résultats avec la même apparence.

## <a name="what-users-experience"></a>Expérience des utilisateurs

Les utilisateurs de Microsoft Search peuvent trouver les résultats Power BIen effectuant une recherche dans la zone de recherche Windows, SharePoint, Office 365 et Bing. Les utilisateurs peuvent rechercher des rapports et des tableaux de bord à l’aide de requêtes comme celles-ci :

* À propos de Power BI `<topic>`
* Power BI pour `<topic>`
* `<topic>` Tableau de bord Power BI ou Power BI `<topic>`
* `<topic>` Rapport Power BI ou rapport Power BI `<topic>`
* `<topic>` Métriques Power BI ou mesures Power BI `<topic>`
* `<topic>` Carte de performance Power BI ou carte de performance Power BI `<topic>`

Remplacez `<topic>` dans les exemples ci-dessus par les informations que vous recherchez, telles que ventes, utilisation, capacité, 2021, Q1, etc., pour afficher les résultats pertinents de Power bi.

:::image type="content" source="media/powerbi-answers/powerbi-serp.png" alt-text="Capture d’écran d’une SERP avec des réponses Power BI et verticale" border="true":::

## <a name="turn-power-bi-search-on-or-off"></a>Activer ou désactiver la recherche Power BI

Par défaut, les résultats Power BI sont activés pour votre organisation. Votre administrateur Power BI peut les désactiver à tout moment. Dans le portail d’administration de Power BI, accédez à paramètres du client et désactivez le paramètre **utiliser la recherche globale pour Power bi** . Pour plus d’informations, reportez-vous à [la rubrique administration de Power bi dans le portail d’administration](https://docs.microsoft.com/power-bi/admin/service-admin-portal#use-global-search-for-power-bi-preview).

:::image type="content" source="media/powerbi-answers/powerbi-admin.png" alt-text="Capture d’écran du paramètre permettant d’activer ou de désactiver les réponses Power BI" border="true":::

## <a name="frequently-asked-questions"></a>Foire aux questions

**Q : est-ce que la recherche Power BI est activée par défaut ?**

**A :** OK. La recherche Power BI est activée par défaut pour Microsoft Search. Il n’y a pas de configuration de la première fois requise par l’administrateur client pour cette fonctionnalité.

**Q : est-ce que la recherche Power BI peut être activée ou désactivée pour des groupes ou des utilisateurs spécifiques ?**

**A :** Actuellement, il peut uniquement être activé ou désactivé pour l’ensemble de votre organisation.

**Q : si la recherche Power BI est désactivée, la page résultats de la recherche Power BI est-elle masquée ?**

**A :** Nbre. La page des résultats de la recherche Power BI apparaît avec un message informant les utilisateurs qu’il n’est pas disponible pour leur organisation.

**Q : est-ce que je vois la page des résultats de la recherche Power BI si je n’ai pas de licence Power BI ?**

**A :** Nbre. Si un utilisateur de recherche ne dispose pas d’une licence Power BI, la page résultats de la recherche Power BI n’apparaît pas dans les résultats de la recherche Microsoft.

**Q : est-ce que je vois les résultats de la recherche Power BI auxquels je ne peux pas accéder ?**

**A :** Nbre. Microsoft Search ne renverra que les résultats Power BI auxquels vous avez accès.

**Q : puis-je personnaliser les résultats de la recherche Power BI (par exemple, le type de rapport ou le propriétaire du rapport) ?**

**A :** Actuellement, nous ne prenons pas en charge la personnalisation des champs inclus dans les résultats de la recherche Power BI.
