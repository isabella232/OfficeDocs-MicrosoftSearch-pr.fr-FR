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
ms.openlocfilehash: 9b168dccaa6126148c877b5841b91c63f7bdc2ac
ms.sourcegitcommit: 5fb46a04e86fb49477f8ce7ab3caa1b503215b8e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/28/2020
ms.locfileid: "46503238"
---
# <a name="create-a-custom-search-results-page-in-sharepoint-online"></a>Créer une page de résultats de recherche personnalisée dans SharePoint Online

Pour personnaliser l’expérience de recherche dans SharePoint, vous pouvez créer une page de résultats de recherche personnalisée pour un site. Cela vous permet d’utiliser une page que vous avez créée, plutôt que la page de résultats de recherche de Microsoft par défaut. Vous disposez ainsi d’une plus grande flexibilité quant à l’expérience de résultats de recherche pour vos utilisateurs.

>[!NOTE]
> Pour modifier la page de résultats de recherche Microsoft par défaut disponible par défaut, consultez [la page personnaliser les résultats de la recherche](customize-search-page.md).

Avec une page de résultats personnalisée, vous pouvez créer une page qui peut être utilisée pour contrôler la mise en page et la conception des résultats de recherche afin de prendre en charge les besoins de votre organisation. Vous pouvez utiliser n’importe quel composant WebPart intégré, des composants WebPart de recherche Open source de la communauté de modèles et pratiques SharePoint, ainsi que les composants WebPart personnalisés que vous avez pu développer à l’aide de SharePoint Framework.

## <a name="configure-a-results-page"></a>Configurer une page de résultats

Pour configurer une page de résultats personnalisée dans SharePoint Online, procédez comme suit :

1. Accédez au site sur lequel vous souhaitez configurer une page de résultats personnalisée, puis accédez à **paramètres du site > paramètres de la collection de sites > paramètres de recherche**.

2. Dans paramètres de recherche, désactivez la case à **costar utiliser les mêmes paramètres de page de résultats que mon parent**, choisir **Envoyer des requêtes à une page de résultats personnalisée**et fournir une valeur pour l’URL de la **page de résultats :**.Ensuite, enregistrez vos modifications. L’URL que vous utilisez ici doit correspondre à la page que vous avez créée pour une utilisation en tant que page de résultats personnalisée.

>[!NOTE]
> La page de résultats personnalisée doit se trouver sur le même domaine que votre site, mais elle n’a pas besoin d’être dans la même collection de sites.  

Vous pouvez également utiliser la [commande Set-PnPSearchSettings SharePoint PNP PowerShell](https://docs.microsoft.com/powershell/module/sharepoint-pnp/set-pnpsearchsettings?view=sharepoint-ps) pour définir la valeur au lieu d’utiliser la page Paramètres du site.

Une fois défini, la page de résultats de recherche personnalisée s’affiche lorsque vous recherchez à l’aide de la zone de recherche de Microsoft qui s’affiche dans la barre de navigation en haut de la page et est utilisée lorsque vous entrez des pages de recherche à partir de sites ou de la page d’accueil du site. Elle n’est pas utilisée lorsque vous effectuez une recherche dans une liste, une bibliothèque ou la page contenu du site. Vous pouvez utiliser le lien pour étendre votre recherche à partir des résultats de recherche dans des listes et des bibliothèques pour accéder à la page de résultats personnalisée.

## <a name="change-the-layout-of-your-custom-results-page"></a>Modifier la disposition de votre page de résultats personnalisée

Une mise en page nommée **HeaderlessSearchResults** peut être utilisée pour que la page de résultats de recherche s’affiche plus près des résultats de la recherche out of Box.Cette nouvelle disposition ne peut être active que pour les pages qui sont définies comme page de résultats de recherche personnalisée.

Pour définir la mise en page, vous pouvez utiliser la [commande Set-PnPClientSidePageSharePoint PowerShell PNP](https://docs.microsoft.com/powershell/module/sharepoint-pnp/set-pnpclientsidepage?view=sharepoint-ps) avec-LayoutType HeaderlessSearchResults.

## <a name="use-sharepoint-framework-query-extensions"></a>Utiliser les extensions de requête de SharePoint Framework

Les pages de résultats de recherche personnalisées peuvent également utiliser l' [extension de requête de SharePoint Framework](https://docs.microsoft.com/sharepoint/dev/spfx/building-search-extensions) pour modifier la requête avant de l’envoyer au moteur de recherche.

## <a name="additional-resources"></a>Ressources supplémentaires

Pour en savoir plus sur la page de résultats personnalisée, consultez notre [session de personnalisation et de développement de recherche enflamme 2019](https://myignite.techcommunity.microsoft.com/sessions/85238?source=sessions).

Pour les projets open source, la prise en main de nos API Microsoft Search, ainsi que d’autres exemples de personnalisation et d’extensibilité, visitez [le site Microsoft Search sur GitHub](https://github.com/microsoft-search).
