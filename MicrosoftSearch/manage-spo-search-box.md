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
description: Comment personnaliser l’expérience de zone de recherche sur les sites SharePoint
ms.openlocfilehash: c58e7cf0a47d22fa9c6fd3abd93cc97087625690
ms.sourcegitcommit: 5df252e6d0bd67bb1b4c59418aceca8369f5fe42
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51031358"
---
# <a name="search-box-settings-on-sharepoint-sites"></a><span data-ttu-id="83375-103">Paramètres de zone de recherche sur les sites SharePoint</span><span class="sxs-lookup"><span data-stu-id="83375-103">Search box settings on SharePoint sites</span></span>

<span data-ttu-id="83375-104">L’une des différentes façons de personnaliser Recherche Microsoft sur les sites SharePoint consiste à personnaliser le fonctionnement de la zone de recherche dans la barre de navigation de suite dans les sites SharePoint pour mieux répondre à vos besoins.</span><span class="sxs-lookup"><span data-stu-id="83375-104">One of the several ways Microsoft Search can be customized on SharePoint sites is to tailor how the search box in the suite navigation bar works in SharePoint sites to best fit your needs.</span></span>

<span data-ttu-id="83375-105">Pour d’autres options de personnalisation, voir Modifier la page des résultats de recherche Microsoft pour ajouter des secteurs verticaux [personnalisés,](customize-search-page.md)des types de résultats et des dispositions, et Créer une page de résultats [de recherche personnalisée.](create-search-results-pages.md)</span><span class="sxs-lookup"><span data-stu-id="83375-105">For other customization options, see [Changing the Microsoft Search results page to add custom verticals, result types and layouts](customize-search-page.md), and [Creating a custom search results page](create-search-results-pages.md).</span></span>

> [!NOTE]
> <span data-ttu-id="83375-106">La zone de recherche de la barre de navigation de suite n’est pas disponible pour tous les clients pour le moment, mais ces options peuvent toujours être définies maintenant et elles prennent effet dès qu’elles sont disponibles.</span><span class="sxs-lookup"><span data-stu-id="83375-106">The suite navigation bar search box is not available for all customers at this time, but these options can still be set now and they will take effect when it becomes available.</span></span>

<span data-ttu-id="83375-107">Pour les tâches répertoriées ci-dessous, vous allez utiliser PowerShell avec les extensions PowerShell PnP SharePoint.</span><span class="sxs-lookup"><span data-stu-id="83375-107">For the tasks listed below, you will use PowerShell with SharePoint PnP PowerShell extensions.</span></span> <span data-ttu-id="83375-108">Vous pouvez installer et en savoir plus sur la façon de commencer [ici.](/powershell/sharepoint/sharepoint-pnp/sharepoint-pnp-cmdlets?view=sharepoint-ps)</span><span class="sxs-lookup"><span data-stu-id="83375-108">You can install and learn more about how to get started [here](/powershell/sharepoint/sharepoint-pnp/sharepoint-pnp-cmdlets?view=sharepoint-ps).</span></span> <span data-ttu-id="83375-109">Vous vous connectez à votre site ou collection de sites à l’aide de cette commande :</span><span class="sxs-lookup"><span data-stu-id="83375-109">You will sign into your site or site collection using this command:</span></span>

```powershell
Connect-PnPOnline -Url <yoursiteurl> -UseWebLogin
# this will prompt you to sign into your site. Use the site owner credentials 
```

## <a name="changing-the-scope-of-search"></a><span data-ttu-id="83375-110">Modification de l’étendue de la recherche</span><span class="sxs-lookup"><span data-stu-id="83375-110">Changing the scope of search</span></span>

<span data-ttu-id="83375-111">Lorsque vous créez un site dans SharePoint Online aujourd’hui et que vous tapez dans la zone de recherche, vous êtes conduit à la page des résultats de recherche Microsoft.</span><span class="sxs-lookup"><span data-stu-id="83375-111">When you create a new site in SharePoint Online today, and type into the search box, you are taken to the Microsoft Search results page.</span></span> <span data-ttu-id="83375-112">Cette page affiche les résultats de votre site actuel par défaut et vous permet d’étendre l’étendue de votre recherche au hub associé au site actuel (s’il en existe un) ou à l’ensemble de l’organisation.</span><span class="sxs-lookup"><span data-stu-id="83375-112">This page shows results from your current site by default and allows you to expand the scope of your search to the hub that the current site is associated with (if there is one), or to the whole organization.</span></span>

<span data-ttu-id="83375-113">L’étendue que la zone de recherche utilise, par défaut, dépend du type de site.</span><span class="sxs-lookup"><span data-stu-id="83375-113">The scope the search box uses, by default, depends on type of site.</span></span>

* <span data-ttu-id="83375-114">Recherche de sites régulières sur le site actuel.</span><span class="sxs-lookup"><span data-stu-id="83375-114">Regular sites search over the current site.</span></span>
* <span data-ttu-id="83375-115">Les sites hub recherchent sur tous les sites du hub.</span><span class="sxs-lookup"><span data-stu-id="83375-115">Hub sites search over all sites in the hub.</span></span>
* <span data-ttu-id="83375-116">Les sites d’accueil recherchent tout le contenu.</span><span class="sxs-lookup"><span data-stu-id="83375-116">Home sites search over all content.</span></span>

<span data-ttu-id="83375-117">Dans certains cas, vous pouvez modifier ces valeurs par défaut pour toujours effectuer une recherche dans l’ensemble de l’organisation ou dans le hub à qui un site est associé, sans avoir besoin d’un clic supplémentaire.</span><span class="sxs-lookup"><span data-stu-id="83375-117">In some cases, you may want to change these defaults to always search over the whole organization, or across the hub a site is associated with, without needing an additional click.</span></span>

<span data-ttu-id="83375-118">En tant que propriétaire de site, vous pouvez modifier ces valeurs par défaut à l’aide de la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="83375-118">As a site owner, you can change these defaults using the following command:</span></span>

```powershell
Set-PnPSearchSettings -SearchScope Tenant
# DefaultScope | Hub | Site | Tenant
```

<span data-ttu-id="83375-119">Après avoir exécute cette commande, le site qui montrant précédemment les résultats du site actuel par défaut commence à afficher les résultats de l’ensemble de l’organisation.</span><span class="sxs-lookup"><span data-stu-id="83375-119">After running this command, the site that was previously showing results from the current site by default will start to show results from the whole organization.</span></span>

<span data-ttu-id="83375-120">Pour revenir au paramètre par défaut, exécutez à nouveau la commande avec la valeur « DefaultScope ».</span><span class="sxs-lookup"><span data-stu-id="83375-120">To go back to the default setting, run the command again with the value “DefaultScope".</span></span> <span data-ttu-id="83375-121">Pour effectuer une recherche sur le Hub, utilisez « Hub » comme valeur SearchScope.</span><span class="sxs-lookup"><span data-stu-id="83375-121">To search across the Hub, use “Hub” as the SearchScope value.</span></span>

<span data-ttu-id="83375-122">Ce paramètre s’applique au niveau du site individuel.</span><span class="sxs-lookup"><span data-stu-id="83375-122">This setting applies at the individual site level.</span></span> <span data-ttu-id="83375-123">Il n’existe aucun paramètre équivalent pour les collections de sites.</span><span class="sxs-lookup"><span data-stu-id="83375-123">There is no equivalent setting for site collections.</span></span>

## <a name="show-or-hide-the-search-box"></a><span data-ttu-id="83375-124">Afficher ou masquer la zone de recherche</span><span class="sxs-lookup"><span data-stu-id="83375-124">Show or hide the search box</span></span>

<span data-ttu-id="83375-125">Vous pouvez choisir de masquer la zone de recherche de la barre de navigation de suite si vous souhaitez empêcher vos utilisateurs de rechercher ou d’utiliser une implémentation de zone de recherche personnalisée.</span><span class="sxs-lookup"><span data-stu-id="83375-125">You can choose to hide the suite navigation bar search box if you want to prevent your users from searching or to use a custom search box implementation.</span></span>

<span data-ttu-id="83375-126">Pour modifier ce paramètre pour un site donné, utilisez la commande ci-après :</span><span class="sxs-lookup"><span data-stu-id="83375-126">To change this setting for a given site use this command:</span></span>

```powershell
Set-PnPSearchSettings -Scope Web -SearchBoxInNavBar Hidden
# Hidden | Inherit
```

<span data-ttu-id="83375-127">Sinon, si vous souhaitez la définir pour tous les sites d’une collection de sites, vous pouvez utiliser cette commande :</span><span class="sxs-lookup"><span data-stu-id="83375-127">Alternately, if you want to set it for all the sites in a site collection, you can use this command:</span></span>

```powershell
Set-PnPSearchSettings -Scope Site -SearchBoxInNavBar Hidden
# Hidden | Inherit
```

<span data-ttu-id="83375-128">Une fois ces commandes en cours d’exécution, la zone de recherche n’est plus présente dans la barre de navigation au-dessus de votre page.</span><span class="sxs-lookup"><span data-stu-id="83375-128">After running these commands, the search box will no longer show up in the navigation bar on top of your page.</span></span> <span data-ttu-id="83375-129">Pour revenir à l’affichage de la zone de recherche, exécutez à nouveau les commandes avec la valeur fournie au paramètre « SearchBoxInNavBar » sur « Inherit ».</span><span class="sxs-lookup"><span data-stu-id="83375-129">To go back to showing the search box, run the commands again with the value provided to "SearchBoxInNavBar" parameter to “Inherit”.</span></span>

<span data-ttu-id="83375-130">Plusieurs points sont à prendre en considération :</span><span class="sxs-lookup"><span data-stu-id="83375-130">There are several points to consider:</span></span>

* <span data-ttu-id="83375-131">Ce paramètre s’applique uniquement à la zone de recherche dans la barre de navigation de la suite.</span><span class="sxs-lookup"><span data-stu-id="83375-131">This setting only applies to the search box in the suite navigation bar.</span></span> <span data-ttu-id="83375-132">Elle ne s’applique pas aux zones de recherche qui se trouver dans la page ou aux zones de recherche sur les pages classiques.</span><span class="sxs-lookup"><span data-stu-id="83375-132">It does not apply to search boxes that are in the page, or to search boxes on classic pages.</span></span>

* <span data-ttu-id="83375-133">Une fois que vous avez désactivé la zone de recherche dans la barre de navigation, si vous souhaitez une fonctionnalité de recherche dans votre site, vous devez la fournir vous-même à l’aide d’un élément Web Part personnalisé ou d’une extension SharePoint Framework.</span><span class="sxs-lookup"><span data-stu-id="83375-133">Once you’ve disabled the search box in the navigation bar, if you want search functionality in your site, you will have to provide it yourself using a custom web part or a SharePoint Framework extension.</span></span>

* <span data-ttu-id="83375-134">Cette solution supprime également la zone de recherche des listes et des bibliothèques de votre site.</span><span class="sxs-lookup"><span data-stu-id="83375-134">This solution will remove the search box from lists and libraries for your site as well.</span></span> <span data-ttu-id="83375-135">Votre solution de recherche personnalisée doit prendre en compte les recherches contextuelles pour les listes et les bibliothèques SharePoint, en plus de la recherche à l’échelle du site.</span><span class="sxs-lookup"><span data-stu-id="83375-135">Your custom search solution will need to consider contextual searches for SharePoint lists and libraries, in addition to site-wide search.</span></span>

* <span data-ttu-id="83375-136">Si vous appliquez le paramètre au site racine de votre domaine, la page d’accueil SharePoint cesse également d’afficher la zone de recherche.</span><span class="sxs-lookup"><span data-stu-id="83375-136">If you apply the setting to the root site of your domain, the SharePoint start page will also stop showing the search box.</span></span>

## <a name="changing-the-hint-displayed-in-the-search-box"></a><span data-ttu-id="83375-137">Modification de l’indication affichée dans la zone de recherche</span><span class="sxs-lookup"><span data-stu-id="83375-137">Changing the hint displayed in the search box</span></span>

<span data-ttu-id="83375-138">Vous pouvez modifier l’indication que la zone de recherche affiche pour un site ou une collection de sites donné.</span><span class="sxs-lookup"><span data-stu-id="83375-138">You can change the hint the search box shows for a given site or site collection.</span></span> <span data-ttu-id="83375-139">Il s’agit du texte qui apparaît dans la zone de recherche avant qu’ils ne commencent à taper dans celle-ci.</span><span class="sxs-lookup"><span data-stu-id="83375-139">This is the text that appears in the search box before they start typing into it.</span></span> <span data-ttu-id="83375-140">Cela peut aider vos utilisateurs à savoir à quoi s’attendre de la recherche si vous avez configuré une page de résultats personnalisée ou modifié le comportement de la recherche d’autres manières.</span><span class="sxs-lookup"><span data-stu-id="83375-140">This may help guide your users about what to expect from search if you’ve configured a custom results page or changed behavior of search in other ways.</span></span>

> [!NOTE]
> <span data-ttu-id="83375-141">Pour pouvoir effectuer cette modification, vous devez autoriser l’exécution de scripts personnalisés sur le site en question en tant qu’administrateur client, ce qui est non permis par défaut.</span><span class="sxs-lookup"><span data-stu-id="83375-141">To be able to make this change, you need to allow running custom scripts on the site in question as a tenant administrator, which is disallowed by default.</span></span> <span data-ttu-id="83375-142">Pour plus https://docs.microsoft.com/sharepoint/allow-or-prevent-custom-script d’informations, voir.</span><span class="sxs-lookup"><span data-stu-id="83375-142">Please see https://docs.microsoft.com/sharepoint/allow-or-prevent-custom-script for details.</span></span> <span data-ttu-id="83375-143">Vous pouvez autoriser l’exécution de scripts personnalisés, apporter les changements, puis revenir à la désalloiement des scripts pour le site si nécessaire.</span><span class="sxs-lookup"><span data-stu-id="83375-143">You can allow running custom scripts, make the change, and then revert to disallowing scripts for the site if necessary.</span></span>

<span data-ttu-id="83375-144">Pour modifier ce paramètre pour un site donné, exécutez la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="83375-144">To change this setting for a given site run the following command:</span></span>

```powershell
Set-PnPSearchSettings -Scope Web -SearchBoxPlaceholderText "my placeholder" 
```

<span data-ttu-id="83375-145">Sinon, si vous souhaitez la définir pour tous les sites d’une collection de sites, vous pouvez utiliser cette commande :</span><span class="sxs-lookup"><span data-stu-id="83375-145">Alternately, if you want to set it for all the sites in a site collection, you can use this command:</span></span>

```powershell
Set-PnPSearchSettings -Scope Site -SearchBoxPlaceholderText "my placeholder" 
```

<span data-ttu-id="83375-146">Pour revenir au texte de l’espace réservé par défaut, définissez la valeur sur vide («  »).</span><span class="sxs-lookup"><span data-stu-id="83375-146">To go back to the default placeholder text, set the value to be blank ("").</span></span>