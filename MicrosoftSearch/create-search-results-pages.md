---
title: Créer une page de résultats de recherche personnalisée dans SharePoint Online
ms.author: jeffkizn
author: jeffkizn
manager: jeffkizn
ms.audience: Admin
ms.topic: article
ms.service: mssearch
ms.localizationpriority: medium
description: Créer votre propre page de résultats de recherche pour un site SharePoint Online
ms.openlocfilehash: df99287dbdd9a82c1a8bc66b39e67a37fcb22da8
ms.sourcegitcommit: ca5ee826ba4f4bb9b9baabc9ae8a130011c2a3d0
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/15/2021
ms.locfileid: "59375957"
---
# <a name="create-a-custom-search-results-page-in-sharepoint-online"></a>Créer une page de résultats de recherche personnalisée dans SharePoint Online

L’une des façons de personnaliser l’expérience de SharePoint consiste à créer une page de résultats de recherche personnalisée pour un site. Cela vous permet d’utiliser une page que vous avez créée, plutôt que la page de résultats par Recherche Microsoft par défaut. Cela vous offre plus de flexibilité sur la façon dont l’expérience de résultats de recherche pour vos utilisateurs.

>[!NOTE]
> Pour apporter des modifications à la page de résultats Recherche Microsoft par défaut, voir Personnaliser la [page des résultats de la recherche.](customize-search-page.md)

Avec une page de résultats personnalisée, vous pouvez créer une page qui peut être utilisée pour contrôler la disposition et la conception des résultats de recherche afin de répondre aux besoins de votre organisation. Vous pouvez utiliser des composants Web Parts intégrés, des composants Web Parts de recherche open source de la communauté SharePoint Patterns and Practices, ainsi que des composants Web Parts personnalisés que vous avez peut-être développés à l’aide de SharePoint Framework.

## <a name="configure-a-results-page"></a>Configurer une page de résultats

Pour configurer une page de résultats personnalisée dans SharePoint Online, suivez les étapes ci-dessous :

1. Accédez au site où vous souhaitez configurer une page de résultats personnalisée et accédez à **Site Paramètres > Site Collection** Paramètres > Search Paramètres .

2. Dans la Paramètres de recherche, désinsérez la sélection à partir de Utiliser les mêmes paramètres de page de résultats que mon **parent,** choisissez Envoyer des requêtes à une **page** de résultats personnalisée et fournissez une valeur pour l’URL de la page de résultats **:**. Enregistrez ensuite vos modifications. L’URL que vous utilisez ici doit être celle de la page que vous avez créée pour l’utiliser comme page de résultats personnalisée.

>[!NOTE]
> La page de résultats personnalisée doit se trouver sur le même domaine que votre site, mais elle ne doit pas nécessairement se trouver dans la même collection de sites.  

Vous pouvez également utiliser la commande [Set-PnPSearchSettings SharePoint PowerShell PnP](/powershell/module/sharepoint-pnp/set-pnpsearchsettings?view=sharepoint-ps) pour définir la valeur au lieu d’utiliser la page Paramètres site.

Une fois définie, la page de résultats de recherche personnalisée s’affiche lorsque vous recherchez à l’aide de la zone Recherche Microsoft qui apparaît dans la barre de navigation en haut de la page et qui est utilisée lorsque vous entrez la recherche à partir des pages du site ou de la page d’accueil du site. Elle n’est pas utilisée lorsque vous recherchez dans une liste, une bibliothèque ou la page de contenu du site. Vous pouvez utiliser le lien pour développer votre recherche à partir des résultats de recherche dans des listes et des bibliothèques afin d’obtenir la page de résultats personnalisée.

## <a name="change-the-layout-of-your-custom-results-page"></a>Modifier la disposition de votre page de résultats personnalisée

Une mise en page nommée **HeaderlessSearchResults** peut être utilisée pour rendre la page de résultats de recherche plus proche de notre expérience de résultats de recherche out-of-box. Cette nouvelle disposition ne peut être active que pour les pages qui sont définies comme page de résultats de recherche personnalisée.

Pour définir la mise en page, vous pouvez utiliser la commande [PowerShell PnP PowerShell Set-PnPClientSidePageSharePoint](/powershell/module/sharepoint-pnp/set-pnpclientsidepage?view=sharepoint-ps) avec -LayoutType HeaderlessSearchResults.

## <a name="use-sharepoint-framework-query-extensions"></a>Utiliser SharePoint Framework extensions de requête

Les pages de résultats de recherche personnalisées peuvent également utiliser l’extension [SharePoint Framework requête](/sharepoint/dev/spfx/building-search-extensions) pour modifier la requête avant qu’elle ne soit envoyée au moteur de recherche.

## <a name="additional-resources"></a>Ressources supplémentaires

Pour en savoir plus sur la page des résultats personnalisés, consultez notre session de personnalisation et de développement de recherche [Ignite 2019.](https://myignite.techcommunity.microsoft.com/sessions/85238?source=sessions)

Pour les projets open source, la prise en Recherche Microsoft API Recherche Microsoft et d’autres exemples de personnalisation et d’extensibilité, visitez [Recherche Microsoft sur GitHub](https://github.com/microsoft-search).