---
title: Gestion de la zone de recherche dans les sites SharePoint
ms.author: keremy
author: jeffkizn
manager: parulm
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: Procédure de personnalisation de l’expérience de zone de recherche sur les sites SharePoint
ms.openlocfilehash: 6ebd084aadb38acb5475b7e43d7c4092ffc09eb8
ms.sourcegitcommit: c5fe4e01403379b3ee7ea4dbded8b31696311d79
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/17/2020
ms.locfileid: "49700963"
---
# <a name="search-box-settings-on-sharepoint-sites"></a>Paramètres de la zone de recherche sur les sites SharePoint

L’une des différentes façons de personnaliser Microsoft Search sur les sites SharePoint est de personnaliser l’apparence de la zone de recherche dans la barre de navigation suite dans les sites SharePoint pour répondre au mieux à vos besoins.

Pour d’autres options de personnalisation, consultez [la rubrique modification de la page de résultats de recherche Microsoft pour ajouter des secteurs verticaux, des types de résultats et des dispositions](customize-search-page.md)personnalisés, ainsi que [la création d’une page de résultats de recherche personnalisée](create-search-results-pages.md).

> [!NOTE]
> La zone de recherche de la barre de navigation suite n’est pas disponible pour tous les clients pour le moment, mais ces options peuvent encore être définies et elles prendront effet dès qu’elle sera disponible.

Pour les tâches indiquées ci-dessous, vous allez utiliser PowerShell avec les extensions PowerShell PnP SharePoint. Vous pouvez installer et en savoir plus sur la prise en main [ici](https://docs.microsoft.com/powershell/sharepoint/sharepoint-pnp/sharepoint-pnp-cmdlets?view=sharepoint-ps). Vous vous connectez à votre site ou à votre collection de sites à l’aide de la commande suivante :

```powershell
Connect-PnPOnline -Url <yoursiteurl> -UseWebLogin
# this will prompt you to sign into your site. Use the site owner credentials 
```

## <a name="changing-the-scope-of-search"></a>Modification de l’étendue de la recherche

Lorsque vous créez un site dans SharePoint Online aujourd’hui et que vous tapez dans la zone de recherche, vous êtes redirigé vers la page des résultats de la recherche Microsoft. Cette page affiche les résultats de votre site actuel par défaut et vous permet d’étendre l’étendue de votre recherche au hub auquel le site actuel est associé (le cas échéant) ou à l’ensemble de l’organisation.

L’étendue que la zone de recherche utilise, par défaut, dépend du type de site.

* Recherche de sites réguliers sur le site actuel.
* Les sites hub recherchent tous les sites dans le Hub.
* Les sites d’accueil recherchent tout le contenu.

Dans certains cas, vous souhaiterez peut-être modifier ces valeurs par défaut de façon à toujours effectuer une recherche sur l’ensemble de l’organisation ou sur le concentrateur auquel un site est associé, sans avoir besoin d’un clic supplémentaire.

En tant que propriétaire de site, vous pouvez modifier ces valeurs par défaut à l’aide de la commande suivante :

```powershell
Set-PnPSearchSettings -SearchScope Tenant
# DefaultScope | Hub | Site | Tenant
```

Après avoir exécuté cette commande, le site qui affichait précédemment les résultats à partir du site actuel commence à afficher les résultats de l’ensemble de l’organisation.

Pour revenir au paramètre par défaut, exécutez à nouveau la commande avec la valeur « DefaultScope ». Pour effectuer une recherche sur le Hub, utilisez « Hub » comme valeur SearchScope.

Ce paramètre s’applique au niveau du site individuel. Il n’existe aucun paramètre équivalent pour les collections de sites.

## <a name="show-or-hide-the-search-box"></a>Afficher ou masquer la zone de recherche

Vous pouvez choisir de masquer la zone de recherche de la barre de navigation suite si vous souhaitez empêcher les utilisateurs de rechercher ou utiliser une implémentation de zone de recherche personnalisée.

Pour modifier ce paramètre pour un site donné, utilisez la commande suivante :

```powershell
Set-PnPSearchSettings -Scope Web -SearchBoxInNavBar Hidden
# Hidden | Inherit
```

Sinon, si vous voulez le définir pour tous les sites d’une collection de sites, vous pouvez utiliser la commande suivante :

```powershell
Set-PnPSearchSettings -Scope Site -SearchBoxInNavBar Hidden
# Hidden | Inherit
```

Après avoir exécuté ces commandes, la zone de recherche ne s’affiche plus dans la barre de navigation en haut de votre page. Pour revenir à l’affichage de la zone de recherche, exécutez à nouveau les commandes avec la valeur fournie au paramètre « SearchBoxInNavBar » pour « hériter ».

Il existe plusieurs points à prendre en compte :

* Ce paramètre s’applique uniquement à la zone de recherche dans la barre de navigation suite. Elle ne s’applique pas aux zones de recherche qui se trouvent dans la page ou aux zones de recherche dans les pages classiques.

* Une fois que vous avez désactivé la zone de recherche dans la barre de navigation, si vous souhaitez une fonctionnalité de recherche dans votre site, vous devez lui fournir vous-même un composant WebPart personnalisé ou une extension SharePoint Framework.

* Cette solution permet également de supprimer de la zone de recherche les listes et les bibliothèques de votre site. Votre solution de recherche personnalisée doit prendre en compte les recherches contextuelles pour les listes et les bibliothèques SharePoint, en plus de la recherche au niveau du site.

* Si vous appliquez le paramètre au site racine de votre domaine, la page de démarrage de SharePoint s’arrêtera également d’afficher la zone de recherche.

## <a name="changing-the-hint-displayed-in-the-search-box"></a>Modification de l’indicateur affiché dans la zone de recherche

Vous pouvez modifier l’indicateur affiché par la zone de recherche pour un site ou une collection de sites donné. Il s’agit du texte qui apparaît dans la zone de recherche avant qu’il commence à taper dans celui-ci. Cela peut aider vos utilisateurs à déterminer ce qu’ils doivent attendre de la recherche si vous avez configuré une page de résultats personnalisée ou modifié le comportement de la recherche d’autres façons.

> [!NOTE]
> Pour pouvoir effectuer cette modification, vous devez autoriser l’exécution des scripts personnalisés sur le site en question en tant qu’administrateur client, ce qui n’est pas autorisé par défaut. Pour plus d’informations, reportez-vous https://docs.microsoft.com/sharepoint/allow-or-prevent-custom-script à. Vous pouvez autoriser l’exécution de scripts personnalisés, effectuer les modifications, puis annuler l’autorisation des scripts pour le site, le cas échéant.

Pour modifier ce paramètre pour un site donné, exécutez la commande suivante :

```powershell
Set-PnPSearchSettings -Scope Web -SearchBoxPlaceholderText "my placeholder" 
```

Sinon, si vous voulez le définir pour tous les sites d’une collection de sites, vous pouvez utiliser la commande suivante :

```powershell
Set-PnPSearchSettings -Scope Site -SearchBoxPlaceholderText "my placeholder" 
```

Pour revenir au texte d’espace réservé par défaut, définissez la valeur sur vide ("").
