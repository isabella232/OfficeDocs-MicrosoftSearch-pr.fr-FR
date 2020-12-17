---
title: Pages classiques dans SharePoint Online et Microsoft Search
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
description: Utilisation de Microsoft Search sur des pages SharePoint classiques
ms.openlocfilehash: 605e63a30ad166c63320c7e89e1b2745e628e15d
ms.sourcegitcommit: c5fe4e01403379b3ee7ea4dbded8b31696311d79
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/17/2020
ms.locfileid: "49700972"
---
# <a name="classic-pages-and-microsoft-search"></a>Pages classiques et Microsoft Search

Les sites SharePoint créés avant les sites modernes utilisent une zone de recherche classique et une expérience de résultats de recherche classique. Nous allons déployer une fonctionnalité qui va commencer par défaut aux pages classiques à utiliser l’expérience de recherche moderne qui utilise Microsoft Search, qui fournit des résultats personnalisés avec une pertinence supérieure.

L’utilisation de Microsoft Search est recommandée pour tous les sites, y compris les sites classiques, mais si vos sites classiques utilisent des pages maîtres personnalisées et/ou que vous avez personnalisé votre expérience de résultats de recherche classique, nous allons détecter automatiquement ces personnalisations et ne pas basculer vers Microsoft Search.

## <a name="classic-sites-that-will-automatically-switch-to-microsoft-search"></a>Sites classiques qui basculeront automatiquement vers Microsoft Search

Les sites classiques commenceront à utiliser Microsoft Search si toutes les conditions suivantes sont vraies.

* Le site est basé sur le modèle de site d’équipe (par exemple, STS # 0 et STS # 1).
* La fonctionnalité de publication n’est pas activée sur le site.
* Le site n’utilise pas de page maître personnalisée (autre page maître que Oslo. Master ou Seattle. Master).
* Il n’existe pas de règles de requête actives autres que celles qui ajoutent des résultats promus pour le site, la collection de sites ou le client sur l’origine des résultats par défaut.
* Il n’existe aucun type de résultat personnalisé pour le site ou la collection de sites sur l’origine des résultats par défaut.
* Le site ou la collection de sites dont il fait partie n’a pas été désactivé en utilisant le paramètre SearchBoxInNavBar décrit ci-dessous.

Une fois que vous avez basculé vers Microsoft Search, les pages classiques du site commencent à afficher la zone de recherche dans la barre de navigation suite et suppriment la zone de recherche classique de la page. Ensuite, lorsqu’un utilisateur recherche un terme, les résultats s’affichent à l’aide de l’expérience de recherche moderne de Microsoft Search.

## <a name="staying-with-the-classic-search-experience"></a>Garder l’expérience de recherche classique

Si votre site remplit les critères mentionnés ci-dessus, mais que vous ne souhaitez pas basculer vers l’expérience de recherche de Microsoft, vous pouvez choisir d’utiliser les commandes suivantes, comme propriétaire de site ou de collection de sites.

Vous pouvez utiliser cette commande à tout moment, avant ou après le basculement, afin qu’il soit facile de revenir à l’expérience de recherche que vous aviez précédemment.

Pour exécuter les commandes ci-dessous, vous allez utiliser PowerShell avec les extensions PowerShell PnP SharePoint. Vous pouvez installer et en savoir plus sur la prise en main [ici](https://docs.microsoft.com/powershell/sharepoint/sharepoint-pnp/sharepoint-pnp-cmdlets?view=sharepoint-ps). Vous vous connectez à votre site ou à votre collection de sites à l’aide de la commande suivante :

```powershell
Connect-PnPOnline -Url <yoursiteurl> -UseWebLogin
# this will prompt you to sign into your site. Use the site owner credentials
```

Pour rester au fait de l’expérience de recherche classique pour un site, exécutez la commande suivante :

```powershell
Set-PnPSearchSettings -Scope Web -SearchBoxInNavBar ModernOnly
# ModernOnly | Inherit
```

Sinon, si vous voulez le définir pour tous les sites d’une collection de sites, vous pouvez utiliser la commande suivante :

```powershell
Set-PnPSearchSettings -Scope Site -SearchBoxInNavBar ModernOnly
# ModernOnly | Inherit
```

## <a name="opting-into-microsoft-search"></a>Opt-moi de Microsoft Search

Pour les sites qui ne répondent pas aux critères mentionnés ci-dessus, ou pour des sites spécifiques d’une collection de sites qui ont choisi de rester en mode classique, vous pouvez activer manuellement l’expérience de recherche de Microsoft.

Pour modifier ce paramètre pour un site spécifique, vous pouvez utiliser la commande suivante :

```powershell
Set-PnPSearchSettings -Scope Web -SearchBoxInNavBar AllPages
# AllPages | Inherit
```

Si vous souhaitez le définir pour tous les sites d’une collection de sites, vous pouvez utiliser la commande suivante :

```powershell
Set-PnPSearchSettings -Scope Site -SearchBoxInNavBar AllPages
# AllPages | Inherit
```

> [!NOTE]
> Vous pouvez activer manuellement Microsoft Search uniquement pour un site d’équipe ou un site de publication (ID de modèle qui contiennent « STS », « CMSPUBLISHING », « BLANKINTERNET » et « GROUP »).
