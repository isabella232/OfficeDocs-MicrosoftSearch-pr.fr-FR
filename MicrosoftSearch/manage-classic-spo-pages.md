---
title: Pages classiques dans SharePoint Online et Recherche Microsoft
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
description: Utilisation de Microsoft Search (recherche Microsoft) sur les pages SharePoint classiques
ms.openlocfilehash: 9a5aeb2e683297faccfb55d3407653c1791b3961
ms.sourcegitcommit: 7133d46ca9c3a5216ee9159db781febd17e5a831
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/14/2021
ms.locfileid: "49863173"
---
# <a name="classic-pages-and-microsoft-search"></a>Pages classiques et Recherche Microsoft

Les sites SharePoint créés avant les sites modernes utilisent une zone de recherche classique et une expérience de résultats de recherche classique. Nous allons déployer une fonctionnalité qui permettra aux pages classiques par défaut de commencer à utiliser l’expérience de recherche moderne qui utilise Microsoft Search (recherche Microsoft), qui fournit des résultats personnalisés avec une pertinence plus élevée.

L’utilisation de Microsoft Search (recherche Microsoft) est recommandée pour tous les sites, y compris classique, mais si vos sites classiques utilisent des pages maîtres personnalisées et/ou si vous avez personnalisé votre expérience de résultats de recherche classique, nous allons détecter automatiquement ces personnalisations et ne pas basculer vers Microsoft Search (recherche Microsoft).

## <a name="classic-sites-that-will-automatically-switch-to-microsoft-search"></a>Sites classiques qui basculeront automatiquement vers Microsoft Search (recherche Microsoft)

Les sites classiques commenceront à utiliser Microsoft Search (recherche Microsoft) si toutes les valeurs suivantes sont vraies :

* Le site est basé sur le modèle de site d’équipe (tel que STS#0 et STS#1).
* La fonctionnalité de publication n’est pas désactivée sur le site.
* Le site n’utilise pas de page maître personnalisée (une page maître différente d’oslo.master ou seattle.master).
* Il n’existe aucune règle de requête active autre que celles qui ajoutent des résultats promus pour le site, la collection de sites ou le client sur l’origine des résultats par défaut.
* Il n’existe aucun type de résultat personnalisé pour le site ou la collection de sites sur l’origine des résultats par défaut.
* Le site ou la collection de sites n’est pas désintés par le commutateur à l’aide du paramètre *SearchBoxInNavBar* décrit ci-dessous.

Après le passage à Recherche Microsoft, les pages classiques du site commencent à afficher la zone de recherche dans la barre de navigation de la suite et suppriment la zone de recherche classique de la page. Ensuite, lorsqu’un utilisateur recherche un terme, les résultats s’affichent à l’aide de l’expérience de recherche moderne de Microsoft Search (recherche Microsoft).

## <a name="staying-with-the-classic-search-experience"></a>Rester dans l’expérience de recherche classique

Si votre site répond aux critères répertoriés ci-dessus, mais que vous ne souhaitez pas qu’il bascule vers l’expérience Recherche Microsoft, vous pouvez choisir d’utiliser les commandes suivantes, en tant que propriétaire du site ou de la collection de sites.

Vous pouvez utiliser cette commande à tout moment, avant ou après le basculement. Il est donc facile de revenir à l’expérience de recherche que vous aviez précédemment.

Pour exécuter les commandes ci-dessous, vous allez utiliser PowerShell avec les extensions PowerShell PnP SharePoint. Vous pouvez installer et en savoir plus sur la façon de commencer [ici.](https://docs.microsoft.com/powershell/sharepoint/sharepoint-pnp/sharepoint-pnp-cmdlets?view=sharepoint-ps) Vous vous connectez à votre site ou collection de sites à l’aide de cette commande :

```powershell
Connect-PnPOnline -Url <yoursiteurl> -UseWebLogin
# this will prompt you to sign in to your site. Use the site owner credentials.
```

Pour rester avec l’expérience de recherche classique pour un site, exécutez la commande suivante :

```powershell
Set-PnPSearchSettings -Scope Web -SearchBoxInNavBar ModernOnly
# ModernOnly | Inherit
```

Sinon, si vous souhaitez la définir pour tous les sites d’une collection de sites, vous pouvez utiliser cette commande :

```powershell
Set-PnPSearchSettings -Scope Site -SearchBoxInNavBar ModernOnly
# ModernOnly | Inherit
```

## <a name="opting-into-microsoft-search"></a>Opting into Microsoft Search

Pour les sites qui ne répondent pas aux critères répertoriés ci-dessus ou pour des sites spécifiques d’une collection de sites qui ont choisi de rester en mode classique, vous pouvez activer manuellement l’expérience Recherche Microsoft.

Pour modifier ce paramètre pour un site spécifique, vous pouvez utiliser cette commande :

```powershell
Set-PnPSearchSettings -Scope Web -SearchBoxInNavBar AllPages
# AllPages | Inherit
```

Si vous souhaitez la définir pour tous les sites d’une collection de sites, vous pouvez utiliser cette commande :

```powershell
Set-PnPSearchSettings -Scope Site -SearchBoxInNavBar AllPages
# AllPages | Inherit
```

> [!NOTE]
> Vous pouvez activer manuellement La recherche Microsoft uniquement pour un site d’équipe ou un site de publication (ID de modèle contenant « STS », « CMSPUBLISHING », « BLANKINTERNET » et « GROUP »).
