---
title: Page d’accueil par défaut
ms.author: dawholl
author: dawholl
manager: kellis
ms.date: 12/20/2018
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Priority
search.appverid:
- BFB160
- MET150
- MOE150
ms.assetid: c020bd72-9906-4dfd-bc77-57287f5927ce
ROBOTS: NOINDEX
description: Découvrez comment configurer un navigateur par défaut pour votre entreprise avec Microsoft Search (recherche Microsoft).
ms.openlocfilehash: 0fc16bc7389b8cfffc2ad528b3b10c7ae1d498c3
ms.sourcegitcommit: be2e837d9b087bffe6ce40d72d7ae58a8fcdf3fe
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/30/2019
ms.locfileid: "34591178"
---
# <a name="set-default-homepage"></a><span data-ttu-id="c25a8-103">Page d’accueil par défaut</span><span class="sxs-lookup"><span data-stu-id="c25a8-103">Set default homepage</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c25a8-104">Cet article s’applique à la fonctionnalité Recherche Microsoft dans le portail d’administration Bing.</span><span class="sxs-lookup"><span data-stu-id="c25a8-104">This article applies to the Microsoft Search in Bing admin portal.</span></span> <span data-ttu-id="c25a8-105">Nous déplaçons le portail vers le centre d’administration Microsoft 365. Ensuite, nous le supprimerons.</span><span class="sxs-lookup"><span data-stu-id="c25a8-105">We’re moving the portal to the Microsoft 365 admin center, and then it will be removed.</span></span> <span data-ttu-id="c25a8-106">Pour commencer, nous vous suggérons d’utiliser le centre d’administration Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="c25a8-106">We recommend that you use the Microsoft 365 admin center to get started.</span></span> <span data-ttu-id="c25a8-107">[Vue d’ensemble de la fonctionnalité Recherche Microsoft](overview-microsoft-search.md).</span><span class="sxs-lookup"><span data-stu-id="c25a8-107">[Overview of Microsoft Search](overview-microsoft-search.md)</span></span>

<span data-ttu-id="c25a8-108">La configuration du navigateur par défaut, le moteur de recherche par défaut et la page d’accueil par défaut qui aideront vos utilisateurs à découvrir les fonctionnalités de Microsoft Search (recherche Microsoft), à plus encourager l’utilisation et offrir une expérience plus fluide.</span><span class="sxs-lookup"><span data-stu-id="c25a8-108">Configuring the default browser, default search engine, and default homepage will help your users discover Microsoft Search  capabilities, encourage more usage, and provide a smoother experience.</span></span>
  
<span data-ttu-id="c25a8-109">Pour définir le navigateur par défaut pour votre organisation, suivez les étapes ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="c25a8-109">To set the default homepage for your organization, follow the steps below.</span></span>
  
## <a name="internet-explorer"></a><span data-ttu-id="c25a8-110">Internet Explorer</span><span class="sxs-lookup"><span data-stu-id="c25a8-110">Internet Explorer</span></span>

### <a name="internet-explorer-50-or-later"></a><span data-ttu-id="c25a8-111">Internet Explorer 5.0 ou version ultérieure</span><span class="sxs-lookup"><span data-stu-id="c25a8-111">Internet Explorer 5.0 or later</span></span>

1. <span data-ttu-id="c25a8-112">Ouvrez la Console de gestion des stratégies de groupe (gpmc.msc) et basculez vers modifier toute stratégie existante ou créer un nouveau.</span><span class="sxs-lookup"><span data-stu-id="c25a8-112">Open the Group Policy Management Console (gpmc.msc) and switch to editing any existing policy or creating a new one.</span></span>
    
2. <span data-ttu-id="c25a8-113">Accédez à **Configuration utilisateur\Préférences\Paramètres de Panneau de contrôle\Paramètres Internet**.</span><span class="sxs-lookup"><span data-stu-id="c25a8-113">Navigate to **User Configuration\Preferences\Control Panel Settings\Internet Settings**.</span></span>
    
3. <span data-ttu-id="c25a8-114">Avec le bouton droit, cliquez sur**Paramètres Internet** et sélectionnez **Internet Explorer 10**.</span><span class="sxs-lookup"><span data-stu-id="c25a8-114">Right-click on **Internet Settings** and select **Internet Explorer 10**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="c25a8-115">Vous devez sélectionner l’option d’Internet Explorer 10 pour appliquer les paramètres Internet Explorer 11 comme les mêmes paramètres s’appliquent à Internet Explorer 11.</span><span class="sxs-lookup"><span data-stu-id="c25a8-115">You need to select the option of Internet Explorer 10 to apply the settings for Internet Explorer 11 as the same settings apply to Internet Explorer 11.</span></span> 
  
4. <span data-ttu-id="c25a8-p102">Les paramètres qui sont soulignés en rouge ne sont pas configurés sur la machine cible, tandis que les paramètres soulignés en vert sont configurés à l’ordinateur cible. Pour modifier le soulignement, utilisez les touches de fonction suivantes :</span><span class="sxs-lookup"><span data-stu-id="c25a8-p102">Settings which are underlined in red are not configured at the target machine, while settings underlined in green are configured at the target machine. To change the underlining, use the following function keys:</span></span>
    
    <span data-ttu-id="c25a8-118">F5-Activer tous les paramètres sous l’onglet actif</span><span class="sxs-lookup"><span data-stu-id="c25a8-118">F5 - Enable all settings on the current tab</span></span>
    
    <span data-ttu-id="c25a8-119">F6-Activer les paramètres actuellement sélectionnés</span><span class="sxs-lookup"><span data-stu-id="c25a8-119">F6 - Enable the currently selected setting</span></span>
    
    <span data-ttu-id="c25a8-120">F7-Désactiver les paramètres actuellement sélectionnés</span><span class="sxs-lookup"><span data-stu-id="c25a8-120">F7 - Disable the currently selected setting</span></span>
    
    <span data-ttu-id="c25a8-121">F8-Désactiver tous les paramètres sous l’onglet actif</span><span class="sxs-lookup"><span data-stu-id="c25a8-121">F8 - Disable all settings on the current tab</span></span>
    
5. <span data-ttu-id="c25a8-p103">Appuyez sur**F8** pour désactiver tous les paramètres avant de configurer quoi que ce soit. L’écran doit ressembler à ceci :</span><span class="sxs-lookup"><span data-stu-id="c25a8-p103">Press **F8** to disable all settings before configuring anything. The screen should look like this:</span></span> 
    
    ![Boîte de dialogue Propriétés Internet Explorer 10](media/2fd55755-5007-4e33-a795-c42ce2fcef4a.jpg)
  
6. <span data-ttu-id="c25a8-125">Appuyez sur**F6** sur les paramètres de la page d’accueil et entrez `https://www.bing.com/business?form=BFBSPR`</span><span class="sxs-lookup"><span data-stu-id="c25a8-125">Press **F6** on the Home page setting and enter `https://www.bing.com/business?form=BFBSPR`</span></span>
    
7. <span data-ttu-id="c25a8-126">Appliquez la stratégie de groupe résultante GPO en les reliant au domaine approprié.</span><span class="sxs-lookup"><span data-stu-id="c25a8-126">Enforce the resultant GPO by linking it to the appropriate domain.</span></span>
    
> [!NOTE]
> <span data-ttu-id="c25a8-127">Les utilisateurs peuvent toujours modifier la page d’accueil après avoir défini cette stratégie.</span><span class="sxs-lookup"><span data-stu-id="c25a8-127">Users can still change the homepage after this policy is set.</span></span> 
  
## <a name="microsoft-edge"></a><span data-ttu-id="c25a8-128">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="c25a8-128">Microsoft Edge</span></span>

### <a name="windows-10-version-1511-or-later"></a><span data-ttu-id="c25a8-129">Windows 10, version 1511 ou supérieure.</span><span class="sxs-lookup"><span data-stu-id="c25a8-129">Windows 10, Version 1511 or later</span></span>

1. <span data-ttu-id="c25a8-130">Ouvrez la Console de gestion des stratégies de groupe (gpmc.msc) et basculez vers modifier toute stratégie existante ou créer un nouveau.</span><span class="sxs-lookup"><span data-stu-id="c25a8-130">Open the Group Policy Management Console (gpmc.msc) and switch to editing any existing policy or creating a new one.</span></span>
    
2. <span data-ttu-id="c25a8-131">Accédez à **Modèles administratifs\Composants Windows\Microsoft Edge**</span><span class="sxs-lookup"><span data-stu-id="c25a8-131">Navigate to **Administrative Templates\Windows Components\Microsoft Edge**</span></span>
    
1. <span data-ttu-id="c25a8-132">Double-cliquez sur **Configurer les pages de démarrage**, définissez-le comme programme **Activé**, puis entrez `https://www.bing.com/business`</span><span class="sxs-lookup"><span data-stu-id="c25a8-132">Double-click **Configure Start pages**, set it to **Enabled**, and enter `https://www.bing.com/business`</span></span>
    
3. <span data-ttu-id="c25a8-133">Appliquez la stratégie de groupe résultante GPO en les reliant au domaine approprié.</span><span class="sxs-lookup"><span data-stu-id="c25a8-133">Enforce the resultant GPO by linking it to the appropriate domain.</span></span>
    
> [!CAUTION]
> <span data-ttu-id="c25a8-134">Les utilisateurs ne pourront pas modifier le navigateur après avoir défini cette stratégie.</span><span class="sxs-lookup"><span data-stu-id="c25a8-134">Users won't be able to change the search provider after this policy is set.</span></span> 
  
## <a name="google-chrome"></a><span data-ttu-id="c25a8-135">Google Chrome</span><span class="sxs-lookup"><span data-stu-id="c25a8-135">Google Chrome</span></span>

### <a name="windows-xp-sp2-or-later"></a><span data-ttu-id="c25a8-136">Windows XP (SP2) ou version ultérieure</span><span class="sxs-lookup"><span data-stu-id="c25a8-136">Windows XP SP2 or later</span></span>

<span data-ttu-id="c25a8-137">L’article du Support de Windows sur la gestion des fichiers ADMX et les derniers fichiers ADMX pour différentes versions de Windows est accessible [sur le Support Microsoft](https://support.microsoft.com/fr-FR/help/3087759/how-to-create-and-manage-the-central-store-for-group-policy-administra).</span><span class="sxs-lookup"><span data-stu-id="c25a8-137">The Windows Support article on managing ADMX files and the latest ADMX files for different versions of Windows can be found [on Microsoft Support](https://support.microsoft.com/en-us/help/3087759/how-to-create-and-manage-the-central-store-for-group-policy-administra).</span></span>

<span data-ttu-id="c25a8-138">Vous devez également utiliser le fichier de stratégie Google le plus récent, que vous trouverez sur[Aide Google Chrome Enterprise](https://support.google.com/chrome/a/answer/187202).</span><span class="sxs-lookup"><span data-stu-id="c25a8-138">You'll also need the latest Google policy file, which you can find on [Google Chrome Enterprise Help](https://support.google.com/chrome/a/answer/187202).</span></span>
  
<span data-ttu-id="c25a8-p104">Si les paramètres décrits dans cette section sont introuvables dans le GPMC, téléchargez l’ ADMX approprié et les copier dans le [magasin central](https://docs.microsoft.com/fr-FR/previous-versions/windows/it-pro/windows-vista/cc748955%28v%3dws.10%29). Le magasin central relatif au contrôleur est un dossier avec la convention de dénomination suivante :</span><span class="sxs-lookup"><span data-stu-id="c25a8-p104">If the settings described in this section can't be found inside of GPMC, download the appropriate ADMX and copy them to the [central store](https://docs.microsoft.com/en-us/previous-versions/windows/it-pro/windows-vista/cc748955%28v%3dws.10%29). Central store on the controller is a folder with the following naming convention:</span></span>
  
 <span data-ttu-id="c25a8-141">**%systemroot%\sysvol\\<domain\>\policies\PolicyDefinitions**</span><span class="sxs-lookup"><span data-stu-id="c25a8-141">**%systemroot%\sysvol\\<domain\>\policies\PolicyDefinitions**</span></span>
  
<span data-ttu-id="c25a8-p105">Chaque domaine que votre contrôleur gère doit avoir un dossier séparé. La commande suivante peut être utilisée pour copier le fichier ADMX à partir de la commande rapide:</span><span class="sxs-lookup"><span data-stu-id="c25a8-p105">Each domain your controller handles should get a separate folder. The following command can be used to copy the ADMX file from the command prompt:</span></span>
  
 `Copy <path_to_ADMX.ADMX> %systemroot%\sysvol\<domain>\policies\PolicyDefinitions`
  
1. <span data-ttu-id="c25a8-144">Ouvrez la Console de gestion des stratégies de groupe (gpmc.msc) et basculez vers modifier toute stratégie existante ou créer un nouveau.</span><span class="sxs-lookup"><span data-stu-id="c25a8-144">Open the Group Policy Management Console (gpmc.msc) and switch to editing any existing policy or creating a new one.</span></span>
    
2. <span data-ttu-id="c25a8-145">Assurez-vous que les dossiers suivants apparaissent dans la section**Modèles Administratifs** des deux*Utilisateur/Configuration Ordinateur*:Google Chrome et Google Chrome- Paramètres par défaut (les utilisateurs peuvent y déroger).</span><span class="sxs-lookup"><span data-stu-id="c25a8-145">Make sure the following folders appear in the **Administrative Templates** section of both *User/Computer Configuration*: Google Chrome and Google Chrome - Default Settings (users can override).</span></span>
    
   - <span data-ttu-id="c25a8-146">Les paramètres de la première section sont fixes et l’administrateur local ne pourra pas les modifier.</span><span class="sxs-lookup"><span data-stu-id="c25a8-146">The settings of the first section are fixed and the local administrator won't be able to change them.</span></span>
    
   - <span data-ttu-id="c25a8-p106">Les paramètres de la dernière section de stratégies peuvent être modifiés par les utilisateurs dans leurs paramètres de navigateur. Vous devez décider si les utilisateurs peuvent remplacer votre paramètre par défaut. Dans les étapes suivantes, modifiez dans le paramètre dans le dossier qui correspond à la stratégie de l’organisation et aux besoins. Les étapes ci-dessous utilisent Google Chrome- les paramètres par défaut comme paramètre par défaut.</span><span class="sxs-lookup"><span data-stu-id="c25a8-p106">The settings of the latter section of policies can be changed by users in their browser settings. You should decide if users can override your default setting. In the following steps, change in the setting in the folder that corresponds to your organization policy and needs. The steps below use the Google Chrome - Default Settings as the default.</span></span>
    
3. <span data-ttu-id="c25a8-151">Accédez à**&lt;Ordinateur/Configuration utilisateur&gt;\Modèles Administratifs\Google Chrome- Paramétrage par défaut\Page d’Accueil**.</span><span class="sxs-lookup"><span data-stu-id="c25a8-151">Navigate to **&lt;Computer/User Configuration&gt;\Administrative Templates\Google Chrome - Default Settings\Home Page**.</span></span>
    
4. <span data-ttu-id="c25a8-152">Double-cliquez sur la**Page du Nouvel Onglet utilisation en tant que Page d’Accueil**et définissez-le comme**Activé**.</span><span class="sxs-lookup"><span data-stu-id="c25a8-152">Double-click **Use New Tab Page as homepage**, and set it to **Enabled**.</span></span>
    
5. <span data-ttu-id="c25a8-153">Accédez à**&lt;Ordinateur/Configuration Utilisateur&gt;\Modèles Administratifs\Google Chrome-Paramétrage par défaut\Page du Nouvel Onglet**.</span><span class="sxs-lookup"><span data-stu-id="c25a8-153">Navigate to **&lt;Computer/User Configuration&gt;\Administrative Templates\Google Chrome - Default Settings\New Tab Page**.</span></span>
    
6. <span data-ttu-id="c25a8-154">Double-cliquez sur **Configurer le Nouvel URL de la Pages d’Onglet**, définissez-la comme**Activé**, puis entrez `https://www.bing.com/business?form=BFBSPR`</span><span class="sxs-lookup"><span data-stu-id="c25a8-154">Double-click **Configure the New Tab Page URL**, set it to **Enabled**, and enter `https://www.bing.com/business?form=BFBSPR`</span></span>
    
7. <span data-ttu-id="c25a8-155">Appliquez la stratégie de groupe résultante GPO en les reliant au domaine approprié.</span><span class="sxs-lookup"><span data-stu-id="c25a8-155">Enforce the resultant GPO by linking it to the appropriate domain.</span></span>
    
<span data-ttu-id="c25a8-156">Les utilisateurs pourront modifier le navigateur après avoir défini cette stratégie.</span><span class="sxs-lookup"><span data-stu-id="c25a8-156">Users will be able to change the home page after this policy is set.</span></span>