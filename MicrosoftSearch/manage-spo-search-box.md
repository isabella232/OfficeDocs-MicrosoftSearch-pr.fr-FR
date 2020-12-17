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
# <a name="search-box-settings-on-sharepoint-sites"></a><span data-ttu-id="6ac15-103">Paramètres de la zone de recherche sur les sites SharePoint</span><span class="sxs-lookup"><span data-stu-id="6ac15-103">Search box settings on SharePoint sites</span></span>

<span data-ttu-id="6ac15-104">L’une des différentes façons de personnaliser Microsoft Search sur les sites SharePoint est de personnaliser l’apparence de la zone de recherche dans la barre de navigation suite dans les sites SharePoint pour répondre au mieux à vos besoins.</span><span class="sxs-lookup"><span data-stu-id="6ac15-104">One of the several ways Microsoft Search can be customized on SharePoint sites is to tailor how the search box in the suite navigation bar works in SharePoint sites to best fit your needs.</span></span>

<span data-ttu-id="6ac15-105">Pour d’autres options de personnalisation, consultez [la rubrique modification de la page de résultats de recherche Microsoft pour ajouter des secteurs verticaux, des types de résultats et des dispositions](customize-search-page.md)personnalisés, ainsi que [la création d’une page de résultats de recherche personnalisée](create-search-results-pages.md).</span><span class="sxs-lookup"><span data-stu-id="6ac15-105">For other customization options, see [Changing the Microsoft Search results page to add custom verticals, result types and layouts](customize-search-page.md), and [Creating a custom search results page](create-search-results-pages.md).</span></span>

> [!NOTE]
> <span data-ttu-id="6ac15-106">La zone de recherche de la barre de navigation suite n’est pas disponible pour tous les clients pour le moment, mais ces options peuvent encore être définies et elles prendront effet dès qu’elle sera disponible.</span><span class="sxs-lookup"><span data-stu-id="6ac15-106">The suite navigation bar search box is not available for all customers at this time, but these options can still be set now and they will take effect when it becomes available.</span></span>

<span data-ttu-id="6ac15-107">Pour les tâches indiquées ci-dessous, vous allez utiliser PowerShell avec les extensions PowerShell PnP SharePoint.</span><span class="sxs-lookup"><span data-stu-id="6ac15-107">For the tasks listed below, you will use PowerShell with SharePoint PnP PowerShell extensions.</span></span> <span data-ttu-id="6ac15-108">Vous pouvez installer et en savoir plus sur la prise en main [ici](https://docs.microsoft.com/powershell/sharepoint/sharepoint-pnp/sharepoint-pnp-cmdlets?view=sharepoint-ps).</span><span class="sxs-lookup"><span data-stu-id="6ac15-108">You can install and learn more about how to get started [here](https://docs.microsoft.com/powershell/sharepoint/sharepoint-pnp/sharepoint-pnp-cmdlets?view=sharepoint-ps).</span></span> <span data-ttu-id="6ac15-109">Vous vous connectez à votre site ou à votre collection de sites à l’aide de la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="6ac15-109">You will sign into your site or site collection using this command:</span></span>

```powershell
Connect-PnPOnline -Url <yoursiteurl> -UseWebLogin
# this will prompt you to sign into your site. Use the site owner credentials 
```

## <a name="changing-the-scope-of-search"></a><span data-ttu-id="6ac15-110">Modification de l’étendue de la recherche</span><span class="sxs-lookup"><span data-stu-id="6ac15-110">Changing the scope of search</span></span>

<span data-ttu-id="6ac15-111">Lorsque vous créez un site dans SharePoint Online aujourd’hui et que vous tapez dans la zone de recherche, vous êtes redirigé vers la page des résultats de la recherche Microsoft.</span><span class="sxs-lookup"><span data-stu-id="6ac15-111">When you create a new site in SharePoint Online today, and type into the search box, you are taken to the Microsoft Search results page.</span></span> <span data-ttu-id="6ac15-112">Cette page affiche les résultats de votre site actuel par défaut et vous permet d’étendre l’étendue de votre recherche au hub auquel le site actuel est associé (le cas échéant) ou à l’ensemble de l’organisation.</span><span class="sxs-lookup"><span data-stu-id="6ac15-112">This page shows results from your current site by default and allows you to expand the scope of your search to the hub that the current site is associated with (if there is one), or to the whole organization.</span></span>

<span data-ttu-id="6ac15-113">L’étendue que la zone de recherche utilise, par défaut, dépend du type de site.</span><span class="sxs-lookup"><span data-stu-id="6ac15-113">The scope the search box uses, by default, depends on type of site.</span></span>

* <span data-ttu-id="6ac15-114">Recherche de sites réguliers sur le site actuel.</span><span class="sxs-lookup"><span data-stu-id="6ac15-114">Regular sites search over the current site.</span></span>
* <span data-ttu-id="6ac15-115">Les sites hub recherchent tous les sites dans le Hub.</span><span class="sxs-lookup"><span data-stu-id="6ac15-115">Hub sites search over all sites in the hub.</span></span>
* <span data-ttu-id="6ac15-116">Les sites d’accueil recherchent tout le contenu.</span><span class="sxs-lookup"><span data-stu-id="6ac15-116">Home sites search over all content.</span></span>

<span data-ttu-id="6ac15-117">Dans certains cas, vous souhaiterez peut-être modifier ces valeurs par défaut de façon à toujours effectuer une recherche sur l’ensemble de l’organisation ou sur le concentrateur auquel un site est associé, sans avoir besoin d’un clic supplémentaire.</span><span class="sxs-lookup"><span data-stu-id="6ac15-117">In some cases, you may want to change these defaults to always search over the whole organization, or across the hub a site is associated with, without needing an additional click.</span></span>

<span data-ttu-id="6ac15-118">En tant que propriétaire de site, vous pouvez modifier ces valeurs par défaut à l’aide de la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="6ac15-118">As a site owner, you can change these defaults using the following command:</span></span>

```powershell
Set-PnPSearchSettings -SearchScope Tenant
# DefaultScope | Hub | Site | Tenant
```

<span data-ttu-id="6ac15-119">Après avoir exécuté cette commande, le site qui affichait précédemment les résultats à partir du site actuel commence à afficher les résultats de l’ensemble de l’organisation.</span><span class="sxs-lookup"><span data-stu-id="6ac15-119">After running this command, the site that was previously showing results from the current site by default will start to show results from the whole organization.</span></span>

<span data-ttu-id="6ac15-120">Pour revenir au paramètre par défaut, exécutez à nouveau la commande avec la valeur « DefaultScope ».</span><span class="sxs-lookup"><span data-stu-id="6ac15-120">To go back to the default setting, run the command again with the value “DefaultScope".</span></span> <span data-ttu-id="6ac15-121">Pour effectuer une recherche sur le Hub, utilisez « Hub » comme valeur SearchScope.</span><span class="sxs-lookup"><span data-stu-id="6ac15-121">To search across the Hub, use “Hub” as the SearchScope value.</span></span>

<span data-ttu-id="6ac15-122">Ce paramètre s’applique au niveau du site individuel.</span><span class="sxs-lookup"><span data-stu-id="6ac15-122">This setting applies at the individual site level.</span></span> <span data-ttu-id="6ac15-123">Il n’existe aucun paramètre équivalent pour les collections de sites.</span><span class="sxs-lookup"><span data-stu-id="6ac15-123">There is no equivalent setting for site collections.</span></span>

## <a name="show-or-hide-the-search-box"></a><span data-ttu-id="6ac15-124">Afficher ou masquer la zone de recherche</span><span class="sxs-lookup"><span data-stu-id="6ac15-124">Show or hide the search box</span></span>

<span data-ttu-id="6ac15-125">Vous pouvez choisir de masquer la zone de recherche de la barre de navigation suite si vous souhaitez empêcher les utilisateurs de rechercher ou utiliser une implémentation de zone de recherche personnalisée.</span><span class="sxs-lookup"><span data-stu-id="6ac15-125">You can choose to hide the suite navigation bar search box if you want to prevent your users from searching or to use a custom search box implementation.</span></span>

<span data-ttu-id="6ac15-126">Pour modifier ce paramètre pour un site donné, utilisez la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="6ac15-126">To change this setting for a given site use this command:</span></span>

```powershell
Set-PnPSearchSettings -Scope Web -SearchBoxInNavBar Hidden
# Hidden | Inherit
```

<span data-ttu-id="6ac15-127">Sinon, si vous voulez le définir pour tous les sites d’une collection de sites, vous pouvez utiliser la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="6ac15-127">Alternately, if you want to set it for all the sites in a site collection, you can use this command:</span></span>

```powershell
Set-PnPSearchSettings -Scope Site -SearchBoxInNavBar Hidden
# Hidden | Inherit
```

<span data-ttu-id="6ac15-128">Après avoir exécuté ces commandes, la zone de recherche ne s’affiche plus dans la barre de navigation en haut de votre page.</span><span class="sxs-lookup"><span data-stu-id="6ac15-128">After running these commands, the search box will no longer show up in the navigation bar on top of your page.</span></span> <span data-ttu-id="6ac15-129">Pour revenir à l’affichage de la zone de recherche, exécutez à nouveau les commandes avec la valeur fournie au paramètre « SearchBoxInNavBar » pour « hériter ».</span><span class="sxs-lookup"><span data-stu-id="6ac15-129">To go back to showing the search box, run the commands again with the value provided to "SearchBoxInNavBar" parameter to “Inherit”.</span></span>

<span data-ttu-id="6ac15-130">Il existe plusieurs points à prendre en compte :</span><span class="sxs-lookup"><span data-stu-id="6ac15-130">There are several points to consider:</span></span>

* <span data-ttu-id="6ac15-131">Ce paramètre s’applique uniquement à la zone de recherche dans la barre de navigation suite.</span><span class="sxs-lookup"><span data-stu-id="6ac15-131">This setting only applies to the search box in the suite navigation bar.</span></span> <span data-ttu-id="6ac15-132">Elle ne s’applique pas aux zones de recherche qui se trouvent dans la page ou aux zones de recherche dans les pages classiques.</span><span class="sxs-lookup"><span data-stu-id="6ac15-132">It does not apply to search boxes that are in the page, or to search boxes on classic pages.</span></span>

* <span data-ttu-id="6ac15-133">Une fois que vous avez désactivé la zone de recherche dans la barre de navigation, si vous souhaitez une fonctionnalité de recherche dans votre site, vous devez lui fournir vous-même un composant WebPart personnalisé ou une extension SharePoint Framework.</span><span class="sxs-lookup"><span data-stu-id="6ac15-133">Once you’ve disabled the search box in the navigation bar, if you want search functionality in your site, you will have to provide it yourself using a custom web part or a SharePoint Framework extension.</span></span>

* <span data-ttu-id="6ac15-134">Cette solution permet également de supprimer de la zone de recherche les listes et les bibliothèques de votre site.</span><span class="sxs-lookup"><span data-stu-id="6ac15-134">This solution will remove the search box from lists and libraries for your site as well.</span></span> <span data-ttu-id="6ac15-135">Votre solution de recherche personnalisée doit prendre en compte les recherches contextuelles pour les listes et les bibliothèques SharePoint, en plus de la recherche au niveau du site.</span><span class="sxs-lookup"><span data-stu-id="6ac15-135">Your custom search solution will need to consider contextual searches for SharePoint lists and libraries, in addition to site-wide search.</span></span>

* <span data-ttu-id="6ac15-136">Si vous appliquez le paramètre au site racine de votre domaine, la page de démarrage de SharePoint s’arrêtera également d’afficher la zone de recherche.</span><span class="sxs-lookup"><span data-stu-id="6ac15-136">If you apply the setting to the root site of your domain, the SharePoint start page will also stop showing the search box.</span></span>

## <a name="changing-the-hint-displayed-in-the-search-box"></a><span data-ttu-id="6ac15-137">Modification de l’indicateur affiché dans la zone de recherche</span><span class="sxs-lookup"><span data-stu-id="6ac15-137">Changing the hint displayed in the search box</span></span>

<span data-ttu-id="6ac15-138">Vous pouvez modifier l’indicateur affiché par la zone de recherche pour un site ou une collection de sites donné.</span><span class="sxs-lookup"><span data-stu-id="6ac15-138">You can change the hint the search box shows for a given site or site collection.</span></span> <span data-ttu-id="6ac15-139">Il s’agit du texte qui apparaît dans la zone de recherche avant qu’il commence à taper dans celui-ci.</span><span class="sxs-lookup"><span data-stu-id="6ac15-139">This is the text that appears in the search box before they start typing into it.</span></span> <span data-ttu-id="6ac15-140">Cela peut aider vos utilisateurs à déterminer ce qu’ils doivent attendre de la recherche si vous avez configuré une page de résultats personnalisée ou modifié le comportement de la recherche d’autres façons.</span><span class="sxs-lookup"><span data-stu-id="6ac15-140">This may help guide your users about what to expect from search if you’ve configured a custom results page or changed behavior of search in other ways.</span></span>

> [!NOTE]
> <span data-ttu-id="6ac15-141">Pour pouvoir effectuer cette modification, vous devez autoriser l’exécution des scripts personnalisés sur le site en question en tant qu’administrateur client, ce qui n’est pas autorisé par défaut.</span><span class="sxs-lookup"><span data-stu-id="6ac15-141">To be able to make this change, you need to allow running custom scripts on the site in question as a tenant administrator, which is disallowed by default.</span></span> <span data-ttu-id="6ac15-142">Pour plus d’informations, reportez-vous https://docs.microsoft.com/sharepoint/allow-or-prevent-custom-script à.</span><span class="sxs-lookup"><span data-stu-id="6ac15-142">Please see https://docs.microsoft.com/sharepoint/allow-or-prevent-custom-script for details.</span></span> <span data-ttu-id="6ac15-143">Vous pouvez autoriser l’exécution de scripts personnalisés, effectuer les modifications, puis annuler l’autorisation des scripts pour le site, le cas échéant.</span><span class="sxs-lookup"><span data-stu-id="6ac15-143">You can allow running custom scripts, make the change, and then revert to disallowing scripts for the site if necessary.</span></span>

<span data-ttu-id="6ac15-144">Pour modifier ce paramètre pour un site donné, exécutez la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="6ac15-144">To change this setting for a given site run the following command:</span></span>

```powershell
Set-PnPSearchSettings -Scope Web -SearchBoxPlaceholderText "my placeholder" 
```

<span data-ttu-id="6ac15-145">Sinon, si vous voulez le définir pour tous les sites d’une collection de sites, vous pouvez utiliser la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="6ac15-145">Alternately, if you want to set it for all the sites in a site collection, you can use this command:</span></span>

```powershell
Set-PnPSearchSettings -Scope Site -SearchBoxPlaceholderText "my placeholder" 
```

<span data-ttu-id="6ac15-146">Pour revenir au texte d’espace réservé par défaut, définissez la valeur sur vide ("").</span><span class="sxs-lookup"><span data-stu-id="6ac15-146">To go back to the default placeholder text, set the value to be blank ("").</span></span>
