---
title: Gestion de la zone de recherche dans SharePoint sites
ms.author: keremy
author: jeffkizn
manager: parulm
ms.audience: Admin
ms.topic: article
ms.service: mssearch
ms.localizationpriority: medium
search.appverid:
- BFB160
- MET150
- MOE150
description: Comment personnaliser l’expérience de zone de recherche sur SharePoint sites
ms.openlocfilehash: b5d58dd5a241ccf2ada556c44ec0ea5479ea2e2b
ms.sourcegitcommit: ca5ee826ba4f4bb9b9baabc9ae8a130011c2a3d0
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/15/2021
ms.locfileid: "59334479"
---
# <a name="search-box-settings-on-sharepoint-sites"></a>Paramètres de zone de recherche sur SharePoint sites

L’une des différentes façons de personnaliser Recherche Microsoft sites SharePoint consiste à personnaliser le fonctionnement de la zone de recherche dans la barre de navigation de suite dans les sites SharePoint pour répondre au mieux à vos besoins.

Pour d’autres options de personnalisation, voir Modification de la page de résultats Recherche Microsoft pour ajouter des secteurs verticaux [personnalisés, des types](customize-search-page.md)de résultats et des dispositions, et Création d’une page de résultats de recherche [personnalisée.](create-search-results-pages.md)

> [!NOTE]
> La zone de recherche de la barre de navigation de suite n’est pas disponible pour tous les clients pour le moment, mais ces options peuvent toujours être définies maintenant et elles prennent effet dès qu’elles sont disponibles.

Pour les tâches répertoriées ci-dessous, vous utiliserez PowerShell avec SharePoint extensions PowerShell PnP. Vous pouvez installer et en savoir plus sur la façon de commencer [ici.](/powershell/sharepoint/sharepoint-pnp/sharepoint-pnp-cmdlets?view=sharepoint-ps) Vous vous connectez à votre site ou collection de sites à l’aide de la commande ci-après :

```powershell
Connect-PnPOnline -Url <yoursiteurl> -UseWebLogin
# this will prompt you to sign into your site. Use the site owner credentials 
```

## <a name="changing-the-scope-of-search"></a>Modification de l’étendue de la recherche

Lorsque vous créez un site dans SharePoint Online aujourd’hui et que vous tapez dans la zone de recherche, vous êtes conduit à la page Recherche Microsoft résultats. Cette page affiche les résultats de votre site actuel par défaut et vous permet d’étendre l’étendue de votre recherche au hub associé au site actuel (s’il en existe un) ou à l’ensemble de l’organisation.

L’étendue que la zone de recherche utilise, par défaut, dépend du type de site.

* Recherche de sites régulières sur le site actuel.
* Les sites hub recherchent sur tous les sites du hub.
* Les sites d’accueil recherchent tout le contenu.

Dans certains cas, vous pouvez modifier ces valeurs par défaut pour toujours effectuer une recherche dans l’ensemble de l’organisation ou dans le hub à qui un site est associé, sans avoir besoin d’un clic supplémentaire.

En tant que propriétaire de site, vous pouvez modifier ces valeurs par défaut à l’aide de la commande suivante :

```powershell
Set-PnPSearchSettings -SearchScope Tenant
# DefaultScope | Hub | Site | Tenant
```

Après avoir exécute cette commande, le site qui montrant précédemment les résultats du site actuel par défaut commence à afficher les résultats de l’ensemble de l’organisation.

Pour revenir au paramètre par défaut, exécutez à nouveau la commande avec la valeur « DefaultScope ». Pour effectuer une recherche sur le Hub, utilisez « Hub » comme valeur SearchScope.

Ce paramètre s’applique au niveau du site individuel. Il n’existe aucun paramètre équivalent pour les collections de sites.

## <a name="show-or-hide-the-search-box"></a>Afficher ou masquer la zone de recherche

Vous pouvez choisir de masquer la zone de recherche de la barre de navigation de suite si vous souhaitez empêcher vos utilisateurs de rechercher ou d’utiliser une implémentation de zone de recherche personnalisée.

Pour modifier ce paramètre pour un site donné, utilisez la commande ci-après :

```powershell
Set-PnPSearchSettings -Scope Web -SearchBoxInNavBar Hidden
# Hidden | Inherit
```

Sinon, si vous souhaitez la définir pour tous les sites d’une collection de sites, vous pouvez utiliser cette commande :

```powershell
Set-PnPSearchSettings -Scope Site -SearchBoxInNavBar Hidden
# Hidden | Inherit
```

Une fois ces commandes en cours d’exécution, la zone de recherche n’est plus présente dans la barre de navigation au-dessus de votre page. Pour revenir à l’affichage de la zone de recherche, exécutez à nouveau les commandes avec la valeur fournie au paramètre « SearchBoxInNavBar » sur « Inherit ».

Plusieurs points sont à prendre en considération :

* Ce paramètre s’applique uniquement à la zone de recherche dans la barre de navigation de la suite. Elle ne s’applique pas aux zones de recherche qui se trouver dans la page ou aux zones de recherche sur les pages classiques.

* Une fois que vous avez désactivé la zone de recherche dans la barre de navigation, si vous souhaitez une fonctionnalité de recherche dans votre site, vous devez la fournir vous-même à l’aide d’un élément Web Part personnalisé ou d’une extension SharePoint Framework.

* Cette solution supprime également la zone de recherche des listes et des bibliothèques de votre site. Votre solution de recherche personnalisée doit prendre en compte les recherches contextuelles pour SharePoint listes et bibliothèques, en plus de la recherche à l’échelle du site.

* Si vous appliquez le paramètre au site racine de votre domaine, la page d SharePoint de démarrage cessera également d’afficher la zone de recherche.

## <a name="changing-the-hint-displayed-in-the-search-box"></a>Modification de l’indication affichée dans la zone de recherche

Vous pouvez modifier l’indication que la zone de recherche affiche pour un site ou une collection de sites donné. Il s’agit du texte qui apparaît dans la zone de recherche avant qu’ils ne commencent à taper dans celle-ci. Cela peut aider vos utilisateurs à savoir à quoi s’attendre de la recherche si vous avez configuré une page de résultats personnalisée ou modifié le comportement de la recherche d’autres manières.

> [!NOTE]
> Pour pouvoir effectuer cette modification, vous devez autoriser l’exécution de scripts personnalisés sur le site en question en tant qu’administrateur client, ce qui est non permis par défaut. Pour plus https://docs.microsoft.com/sharepoint/allow-or-prevent-custom-script d’informations, voir. Vous pouvez autoriser l’exécution de scripts personnalisés, apporter les changements, puis revenir à la désalloiement des scripts pour le site si nécessaire.

Pour modifier ce paramètre pour un site donné, exécutez la commande suivante :

```powershell
Set-PnPSearchSettings -Scope Web -SearchBoxPlaceholderText "my placeholder" 
```

Sinon, si vous souhaitez la définir pour tous les sites d’une collection de sites, vous pouvez utiliser cette commande :

```powershell
Set-PnPSearchSettings -Scope Site -SearchBoxPlaceholderText "my placeholder" 
```

Pour revenir au texte de l’espace réservé par défaut, définissez la valeur sur vide («  »).