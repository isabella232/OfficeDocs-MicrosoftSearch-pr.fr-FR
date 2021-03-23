---
title: Créer une page de résultats de recherche personnalisée dans SharePoint Online
ms.author: jeffkizn
author: jeffkizn
manager: jeffkizn
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
description: Créer votre propre page de résultats de recherche pour un site SharePoint Online
ms.openlocfilehash: b5abb25f15795389dd8b6d5683ac336af7422e0a
ms.sourcegitcommit: 5df252e6d0bd67bb1b4c59418aceca8369f5fe42
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51031637"
---
# <a name="create-a-custom-search-results-page-in-sharepoint-online"></a>Créer une page de résultats de recherche personnalisée dans SharePoint Online

Une façon de personnaliser l’expérience de recherche dans SharePoint consiste à créer une page de résultats de recherche personnalisée pour un site. Cela vous permet d’utiliser une page que vous avez créée, plutôt que la page par défaut dans la page de résultats de recherche Microsoft. Cela vous offre plus de flexibilité sur la façon dont l’expérience de résultats de recherche vos utilisateurs.

>[!NOTE]
> Pour apporter des modifications à la page de résultats de recherche Microsoft par défaut qui est disponible par défaut, voir Personnaliser la [page des résultats de la recherche.](customize-search-page.md)

Avec une page de résultats personnalisée, vous pouvez créer une page qui peut être utilisée pour contrôler la disposition et la conception des résultats de recherche afin de répondre aux besoins de votre organisation. Vous pouvez utiliser des composants Web Parts intégrés, des composants Web Parts de recherche open source de la communauté SharePoint Patterns and Practices, ainsi que des composants Web Parts personnalisés que vous avez peut-être développés à l’aide de SharePoint Framework.

## <a name="configure-a-results-page"></a>Configurer une page de résultats

Pour configurer une page de résultats personnalisée dans SharePoint Online, suivez les étapes ci-dessous :

1. Accédez au site où vous souhaitez configurer une page de résultats personnalisée et accédez à Paramètres du site > Paramètres de la collection de sites > **paramètres de recherche.**

2. Dans paramètres de recherche, désérez la sélection à partir de Utiliser les mêmes paramètres de page de résultats que mon **parent,** choisissez Envoyer des requêtes à une **page** de résultats personnalisée et fournissez une valeur pour l’URL de la page de **résultats :**. Ensuite, enregistrez vos modifications. L’URL que vous utilisez ici doit être celle de la page que vous avez créée pour l’utiliser comme page de résultats personnalisée.

>[!NOTE]
> La page de résultats personnalisée doit se trouver sur le même domaine que votre site, mais elle ne doit pas nécessairement se trouver dans la même collection de sites.  

Vous pouvez également utiliser la commande [PowerShell PnP SharePoint Set-PnPSearchSettings](/powershell/module/sharepoint-pnp/set-pnpsearchsettings?view=sharepoint-ps) pour définir la valeur au lieu d’utiliser la page Paramètres du site.

Une fois définie, la page de résultats de recherche personnalisée s’affiche lorsque vous recherchez à l’aide de la zone Recherche Microsoft qui apparaît dans la barre de navigation en haut de la page et est utilisée lorsque vous entrez la recherche à partir des pages du site ou de la page d’accueil du site. Elle n’est pas utilisée lorsque vous recherchez dans une liste, une bibliothèque ou la page de contenu du site. Vous pouvez utiliser le lien pour développer votre recherche à partir des résultats de recherche dans des listes et des bibliothèques afin d’obtenir la page de résultats personnalisée.

## <a name="change-the-layout-of-your-custom-results-page"></a>Modifier la disposition de votre page de résultats personnalisée

Une mise en page nommée **HeaderlessSearchResults** peut être utilisée pour rendre la page de résultats de recherche plus proche de notre expérience de résultats de recherche out-of-box. Cette nouvelle disposition ne peut être active que pour les pages qui sont définies comme page de résultats de recherche personnalisée.

Pour définir la mise en page, vous pouvez utiliser la commande [PowerShell PnP PowerShell Set-PnPClientSidePageSharePoint](/powershell/module/sharepoint-pnp/set-pnpclientsidepage?view=sharepoint-ps) avec -LayoutType HeaderlessSearchResults.

## <a name="use-sharepoint-framework-query-extensions"></a>Utiliser les extensions de requête SharePoint Framework

Les pages de résultats de recherche personnalisées peuvent également utiliser l’extension de requête [SharePoint Framework](/sharepoint/dev/spfx/building-search-extensions) pour modifier la requête avant qu’elle ne soit envoyée au moteur de recherche.

## <a name="additional-resources"></a>Ressources supplémentaires

Pour en savoir plus sur la page des résultats personnalisés, consultez notre session de personnalisation et de développement de recherche [Ignite 2019.](https://myignite.techcommunity.microsoft.com/sessions/85238?source=sessions)

Pour les projets open source, la prise en compte de nos API de recherche Microsoft et d’autres exemples de personnalisation et d’extensibilité, visitez [Microsoft Search (recherche Microsoft) sur GitHub](https://github.com/microsoft-search).