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
# <a name="classic-pages-and-microsoft-search"></a><span data-ttu-id="8e67e-103">Pages classiques et Recherche Microsoft</span><span class="sxs-lookup"><span data-stu-id="8e67e-103">Classic pages and Microsoft Search</span></span>

<span data-ttu-id="8e67e-104">Les sites SharePoint créés avant les sites modernes utilisent une zone de recherche classique et une expérience de résultats de recherche classique.</span><span class="sxs-lookup"><span data-stu-id="8e67e-104">SharePoint sites created prior to modern sites use a classic search box and classic search results experience.</span></span> <span data-ttu-id="8e67e-105">Nous allons déployer une fonctionnalité qui permettra aux pages classiques par défaut de commencer à utiliser l’expérience de recherche moderne qui utilise Microsoft Search (recherche Microsoft), qui fournit des résultats personnalisés avec une pertinence plus élevée.</span><span class="sxs-lookup"><span data-stu-id="8e67e-105">We will be rolling out a feature that will default classic pages to start using the modern search experience that uses Microsoft Search, which provides personalized results with higher relevance.</span></span>

<span data-ttu-id="8e67e-106">L’utilisation de Microsoft Search (recherche Microsoft) est recommandée pour tous les sites, y compris classique, mais si vos sites classiques utilisent des pages maîtres personnalisées et/ou si vous avez personnalisé votre expérience de résultats de recherche classique, nous allons détecter automatiquement ces personnalisations et ne pas basculer vers Microsoft Search (recherche Microsoft).</span><span class="sxs-lookup"><span data-stu-id="8e67e-106">Using Microsoft Search is recommended for all sites, including classic, but if your classic sites use custom master pages and/or you have customized your classic search results experience, we will auto-detect these customizations and not switch to Microsoft Search.</span></span>

## <a name="classic-sites-that-will-automatically-switch-to-microsoft-search"></a><span data-ttu-id="8e67e-107">Sites classiques qui basculeront automatiquement vers Microsoft Search (recherche Microsoft)</span><span class="sxs-lookup"><span data-stu-id="8e67e-107">Classic sites that will automatically switch to Microsoft Search</span></span>

<span data-ttu-id="8e67e-108">Les sites classiques commenceront à utiliser Microsoft Search (recherche Microsoft) si toutes les valeurs suivantes sont vraies :</span><span class="sxs-lookup"><span data-stu-id="8e67e-108">Classic sites will start using Microsoft Search if all of the following are true:</span></span>

* <span data-ttu-id="8e67e-109">Le site est basé sur le modèle de site d’équipe (tel que STS#0 et STS#1).</span><span class="sxs-lookup"><span data-stu-id="8e67e-109">The site is based on the team site template (like STS#0 and STS#1).</span></span>
* <span data-ttu-id="8e67e-110">La fonctionnalité de publication n’est pas désactivée sur le site.</span><span class="sxs-lookup"><span data-stu-id="8e67e-110">The site does not have the publishing feature turned on.</span></span>
* <span data-ttu-id="8e67e-111">Le site n’utilise pas de page maître personnalisée (une page maître différente d’oslo.master ou seattle.master).</span><span class="sxs-lookup"><span data-stu-id="8e67e-111">The site does not use a custom master page (a different master page than oslo.master or seattle.master).</span></span>
* <span data-ttu-id="8e67e-112">Il n’existe aucune règle de requête active autre que celles qui ajoutent des résultats promus pour le site, la collection de sites ou le client sur l’origine des résultats par défaut.</span><span class="sxs-lookup"><span data-stu-id="8e67e-112">There are no active query rules other than those adding promoted results for the site, site collection or tenant on the default result source.</span></span>
* <span data-ttu-id="8e67e-113">Il n’existe aucun type de résultat personnalisé pour le site ou la collection de sites sur l’origine des résultats par défaut.</span><span class="sxs-lookup"><span data-stu-id="8e67e-113">There are no custom result types for the site or the site collection on the default result source.</span></span>
* <span data-ttu-id="8e67e-114">Le site ou la collection de sites n’est pas désintés par le commutateur à l’aide du paramètre *SearchBoxInNavBar* décrit ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="8e67e-114">The site or the site collection is not opted out of the switch using the *SearchBoxInNavBar* setting described below.</span></span>

<span data-ttu-id="8e67e-115">Après le passage à Recherche Microsoft, les pages classiques du site commencent à afficher la zone de recherche dans la barre de navigation de la suite et suppriment la zone de recherche classique de la page.</span><span class="sxs-lookup"><span data-stu-id="8e67e-115">After the switch to Microsoft Search, classic pages in the site will start to show the search box in the suite navigation bar and remove the classic search box from the page.</span></span> <span data-ttu-id="8e67e-116">Ensuite, lorsqu’un utilisateur recherche un terme, les résultats s’affichent à l’aide de l’expérience de recherche moderne de Microsoft Search (recherche Microsoft).</span><span class="sxs-lookup"><span data-stu-id="8e67e-116">Then, when a user searches for a term, the results will be displayed using the modern search experience of Microsoft Search.</span></span>

## <a name="staying-with-the-classic-search-experience"></a><span data-ttu-id="8e67e-117">Rester dans l’expérience de recherche classique</span><span class="sxs-lookup"><span data-stu-id="8e67e-117">Staying with the classic search experience</span></span>

<span data-ttu-id="8e67e-118">Si votre site répond aux critères répertoriés ci-dessus, mais que vous ne souhaitez pas qu’il bascule vers l’expérience Recherche Microsoft, vous pouvez choisir d’utiliser les commandes suivantes, en tant que propriétaire du site ou de la collection de sites.</span><span class="sxs-lookup"><span data-stu-id="8e67e-118">If your site meets the criteria listed above, but you do not want it to switch to the Microsoft Search experience, you can opt out using the following commands, as the site or site collection owner.</span></span>

<span data-ttu-id="8e67e-119">Vous pouvez utiliser cette commande à tout moment, avant ou après le basculement. Il est donc facile de revenir à l’expérience de recherche que vous aviez précédemment.</span><span class="sxs-lookup"><span data-stu-id="8e67e-119">You can use this command at any time, before or after the switch happens, so it is easy to go back to the search experience you had previously.</span></span>

<span data-ttu-id="8e67e-120">Pour exécuter les commandes ci-dessous, vous allez utiliser PowerShell avec les extensions PowerShell PnP SharePoint.</span><span class="sxs-lookup"><span data-stu-id="8e67e-120">To run the commands below, you will use PowerShell with SharePoint PnP PowerShell extensions.</span></span> <span data-ttu-id="8e67e-121">Vous pouvez installer et en savoir plus sur la façon de commencer [ici.](https://docs.microsoft.com/powershell/sharepoint/sharepoint-pnp/sharepoint-pnp-cmdlets?view=sharepoint-ps)</span><span class="sxs-lookup"><span data-stu-id="8e67e-121">You can install and learn more about how to get started [here](https://docs.microsoft.com/powershell/sharepoint/sharepoint-pnp/sharepoint-pnp-cmdlets?view=sharepoint-ps).</span></span> <span data-ttu-id="8e67e-122">Vous vous connectez à votre site ou collection de sites à l’aide de cette commande :</span><span class="sxs-lookup"><span data-stu-id="8e67e-122">You will sign in to your site or site collection using this command:</span></span>

```powershell
Connect-PnPOnline -Url <yoursiteurl> -UseWebLogin
# this will prompt you to sign in to your site. Use the site owner credentials.
```

<span data-ttu-id="8e67e-123">Pour rester avec l’expérience de recherche classique pour un site, exécutez la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="8e67e-123">To stay with classic search experience for a site, run the following command:</span></span>

```powershell
Set-PnPSearchSettings -Scope Web -SearchBoxInNavBar ModernOnly
# ModernOnly | Inherit
```

<span data-ttu-id="8e67e-124">Sinon, si vous souhaitez la définir pour tous les sites d’une collection de sites, vous pouvez utiliser cette commande :</span><span class="sxs-lookup"><span data-stu-id="8e67e-124">Alternately, if you want to set it for all the sites in a site collection, you can use this command:</span></span>

```powershell
Set-PnPSearchSettings -Scope Site -SearchBoxInNavBar ModernOnly
# ModernOnly | Inherit
```

## <a name="opting-into-microsoft-search"></a><span data-ttu-id="8e67e-125">Opting into Microsoft Search</span><span class="sxs-lookup"><span data-stu-id="8e67e-125">Opting into Microsoft Search</span></span>

<span data-ttu-id="8e67e-126">Pour les sites qui ne répondent pas aux critères répertoriés ci-dessus ou pour des sites spécifiques d’une collection de sites qui ont choisi de rester en mode classique, vous pouvez activer manuellement l’expérience Recherche Microsoft.</span><span class="sxs-lookup"><span data-stu-id="8e67e-126">For those sites that do not meet the criteria listed above, or for specific sites in a site collection that opted to stay in classic, you can manually enable the Microsoft Search experience.</span></span>

<span data-ttu-id="8e67e-127">Pour modifier ce paramètre pour un site spécifique, vous pouvez utiliser cette commande :</span><span class="sxs-lookup"><span data-stu-id="8e67e-127">To change this setting for a specific site, you can use this command:</span></span>

```powershell
Set-PnPSearchSettings -Scope Web -SearchBoxInNavBar AllPages
# AllPages | Inherit
```

<span data-ttu-id="8e67e-128">Si vous souhaitez la définir pour tous les sites d’une collection de sites, vous pouvez utiliser cette commande :</span><span class="sxs-lookup"><span data-stu-id="8e67e-128">If you want to set it for all the sites in a site collection, you can use this command:</span></span>

```powershell
Set-PnPSearchSettings -Scope Site -SearchBoxInNavBar AllPages
# AllPages | Inherit
```

> [!NOTE]
> <span data-ttu-id="8e67e-129">Vous pouvez activer manuellement La recherche Microsoft uniquement pour un site d’équipe ou un site de publication (ID de modèle contenant « STS », « CMSPUBLISHING », « BLANKINTERNET » et « GROUP »).</span><span class="sxs-lookup"><span data-stu-id="8e67e-129">You can manually enable Microsoft Search only for a Team Site or Publishing Site (template ids that contain "STS", "CMSPUBLISHING", "BLANKINTERNET" and "GROUP").</span></span>
