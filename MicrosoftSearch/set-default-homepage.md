---
title: Page d’accueil par défaut
ms.author: anfowler
author: adefowler
manager: shohara
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
ms.openlocfilehash: c3302863fab8888b8304b909c2c74ce71b391ade
ms.sourcegitcommit: 3da22a2e09830672ebf199e05a32fa89b75c083b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/27/2019
ms.locfileid: "37289008"
---
# <a name="make-bingcom-the-default-home-page"></a><span data-ttu-id="a1d08-103">Configurer Bing.com en tant que page d’accueil par défaut</span><span class="sxs-lookup"><span data-stu-id="a1d08-103">Make Bing.com the default home page</span></span>

<span data-ttu-id="a1d08-104">Cet article vous explique comment configurer Bing.com en tant que page d’accueil par défaut pour Microsoft Edge, Google Chrome et Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="a1d08-104">This article explains how to set Bing.com as the default home page for Microsoft Edge, Google Chrome, and Internet Explorer browsers.</span></span> 
  
 
## <a name="microsoft-edge-on-windows-10-version-1511-or-later"></a><span data-ttu-id="a1d08-105">Microsoft Edge sur Windows 10, version 1511 ou ultérieure</span><span class="sxs-lookup"><span data-stu-id="a1d08-105">Microsoft Edge on Windows 10, Version 1511 or later</span></span>

<span data-ttu-id="a1d08-106">Les utilisateurs ne pourront plus modifier ce paramètre après avoir défini cette stratégie.</span><span class="sxs-lookup"><span data-stu-id="a1d08-106">Users won't be able to change the search provider after this policy is set.</span></span> 

1. <span data-ttu-id="a1d08-107">Ouvrez la Console de gestion des stratégies de groupe (gpmc.msc) et basculez vers le mode de modification d’une stratégie existante ou de création d’une nouvelle.</span><span class="sxs-lookup"><span data-stu-id="a1d08-107">Open the Group Policy Management Console (gpmc.msc) and switch to editing any existing policy or creating a new one.</span></span> 
1. <span data-ttu-id="a1d08-108">Accédez à **Modèles administratifs\Composants Windows\Microsoft Edge**.</span><span class="sxs-lookup"><span data-stu-id="a1d08-108">Navigate to **Administrative Templates\Windows Components\Microsoft Edge**</span></span>    
1. <span data-ttu-id="a1d08-109">Double-cliquez sur **Configurer les pages de démarrage**, définissez-le comme programme **Activé**, puis entrez `https://www.bing.com/business`</span><span class="sxs-lookup"><span data-stu-id="a1d08-109">Double-click **Configure Start pages**, set it to **Enabled**, and enter `https://www.bing.com/business`</span></span>
1.  <span data-ttu-id="a1d08-110">Appliquez la stratégie de groupe résultante GPO en les reliant au domaine approprié.</span><span class="sxs-lookup"><span data-stu-id="a1d08-110">Enforce the resultant GPO by linking it to the appropriate domain.</span></span>

  
## <a name="google-chrome-on-windows-xp-sp2-or-later"></a><span data-ttu-id="a1d08-111">Google Chrome sur Windows XP SP2 ou version ultérieure</span><span class="sxs-lookup"><span data-stu-id="a1d08-111">Google Chrome on Windows XP SP2 or later</span></span>


<span data-ttu-id="a1d08-112">L’article du Support de Windows sur la gestion des fichiers ADMX et les derniers fichiers ADMX pour différentes versions de Windows est accessible [sur le Support Microsoft](https://support.microsoft.com/help/3087759/how-to-create-and-manage-the-central-store-for-group-policy-administra).</span><span class="sxs-lookup"><span data-stu-id="a1d08-112">The Windows Support article on managing ADMX files and the latest ADMX files for different versions of Windows can be found [on Microsoft Support](https://support.microsoft.com/help/3087759/how-to-create-and-manage-the-central-store-for-group-policy-administra).</span></span>

<span data-ttu-id="a1d08-113">Vous devez également utiliser le fichier de stratégie Google le plus récent, que vous trouverez sur[Aide Google Chrome Enterprise](https://support.google.com/chrome/a/answer/187202).</span><span class="sxs-lookup"><span data-stu-id="a1d08-113">You'll also need the latest Google policy file, which you can find on [Google Chrome Enterprise Help](https://support.google.com/chrome/a/answer/187202).</span></span>
  
<span data-ttu-id="a1d08-p101">Si les paramètres décrits dans cette section sont introuvables dans le GPMC, téléchargez l’ ADMX approprié et les copier dans le [magasin central](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-vista/cc748955%28v%3dws.10%29). Le magasin central relatif au contrôleur est un dossier avec la convention de dénomination suivante :</span><span class="sxs-lookup"><span data-stu-id="a1d08-p101">If the settings described in this section can't be found inside of GPMC, download the appropriate ADMX and copy them to the [central store](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-vista/cc748955%28v%3dws.10%29). Central store on the controller is a folder with the following naming convention:</span></span>
  
 <span data-ttu-id="a1d08-116">**%systemroot%\sysvol\\<domain\>\policies\PolicyDefinitions**</span><span class="sxs-lookup"><span data-stu-id="a1d08-116">**%systemroot%\sysvol\\<domain\>\policies\PolicyDefinitions**</span></span>
  
<span data-ttu-id="a1d08-p102">Chaque domaine que votre contrôleur gère doit avoir un dossier séparé. La commande suivante peut être utilisée pour copier le fichier ADMX à partir de la commande rapide:</span><span class="sxs-lookup"><span data-stu-id="a1d08-p102">Each domain your controller handles should get a separate folder. The following command can be used to copy the ADMX file from the command prompt:</span></span>
  
 `Copy <path_to_ADMX.ADMX> %systemroot%\sysvol\<domain>\policies\PolicyDefinitions`
  
1. <span data-ttu-id="a1d08-119">Ouvrez la Console de gestion des stratégies de groupe (gpmc.msc) et basculez vers modifier toute stratégie existante ou créer un nouveau.</span><span class="sxs-lookup"><span data-stu-id="a1d08-119">Open the Group Policy Management Console (gpmc.msc) and switch to editing any existing policy or creating a new one.</span></span>
1. <span data-ttu-id="a1d08-120">Assurez-vous que les dossiers suivants apparaissent dans la section**Modèles Administratifs** des deux*Utilisateur/Configuration Ordinateur*:Google Chrome et Google Chrome- Paramètres par défaut (les utilisateurs peuvent y déroger).</span><span class="sxs-lookup"><span data-stu-id="a1d08-120">Make sure the following folders appear in the **Administrative Templates** section of both *User/Computer Configuration*: Google Chrome and Google Chrome - Default Settings (users can override).</span></span>
   - <span data-ttu-id="a1d08-121">Les paramètres de la première section sont fixes et l’administrateur local ne pourra pas les modifier.</span><span class="sxs-lookup"><span data-stu-id="a1d08-121">The settings of the first section are fixed and the local administrator won't be able to change them.</span></span>
   - <span data-ttu-id="a1d08-p103">Les paramètres de la dernière section de stratégies peuvent être modifiés par les utilisateurs dans leurs paramètres de navigateur. Vous devez décider si les utilisateurs peuvent remplacer votre paramètre par défaut. Dans les étapes suivantes, modifiez dans le paramètre dans le dossier qui correspond à la stratégie de l’organisation et aux besoins. Les étapes ci-dessous utilisent Google Chrome- les paramètres par défaut comme paramètre par défaut.</span><span class="sxs-lookup"><span data-stu-id="a1d08-p103">The settings of the latter section of policies can be changed by users in their browser settings. You should decide if users can override your default setting. In the following steps, change in the setting in the folder that corresponds to your organization policy and needs. The steps below use the Google Chrome - Default Settings as the default.</span></span>

1. <span data-ttu-id="a1d08-126">Accédez à**&lt;Ordinateur/Configuration utilisateur&gt;\Modèles Administratifs\Google Chrome- Paramétrage par défaut\Page d’Accueil**.</span><span class="sxs-lookup"><span data-stu-id="a1d08-126">Navigate to **&lt;Computer/User Configuration&gt;\Administrative Templates\Google Chrome - Default Settings\Home Page**.</span></span> 
1. <span data-ttu-id="a1d08-127">Double-cliquez sur la**Page du Nouvel Onglet utilisation en tant que Page d’Accueil**et définissez-le comme**Activé**.</span><span class="sxs-lookup"><span data-stu-id="a1d08-127">Double-click **Use New Tab Page as homepage**, and set it to **Enabled**.</span></span> 
1. <span data-ttu-id="a1d08-128">Accédez à**&lt;Ordinateur/Configuration Utilisateur&gt;\Modèles Administratifs\Google Chrome-Paramétrage par défaut\Page du Nouvel Onglet**.</span><span class="sxs-lookup"><span data-stu-id="a1d08-128">Navigate to **&lt;Computer/User Configuration&gt;\Administrative Templates\Google Chrome - Default Settings\New Tab Page**.</span></span> 
1. <span data-ttu-id="a1d08-129">Double-cliquez sur **Configurer le Nouvel URL de la Pages d’Onglet**, définissez-la comme**Activé**, puis entrez `https://www.bing.com/business?form=BFBSPR`</span><span class="sxs-lookup"><span data-stu-id="a1d08-129">Double-click **Configure the New Tab Page URL**, set it to **Enabled**, and enter `https://www.bing.com/business?form=BFBSPR`</span></span> 
1. <span data-ttu-id="a1d08-130">Appliquez la stratégie de groupe résultante GPO en les reliant au domaine approprié.</span><span class="sxs-lookup"><span data-stu-id="a1d08-130">Enforce the resultant GPO by linking it to the appropriate domain.</span></span>

## <a name="internet-explorer-50-or-later"></a><span data-ttu-id="a1d08-131">Internet Explorer 5.0 ou version ultérieure</span><span class="sxs-lookup"><span data-stu-id="a1d08-131">Internet Explorer 5.0 or later</span></span>
<span data-ttu-id="a1d08-132">Les utilisateurs peuvent encore modifier la page d’accueil une fois cette stratégie définie.</span><span class="sxs-lookup"><span data-stu-id="a1d08-132">Users can still change the homepage after this policy is set.</span></span> 

1. <span data-ttu-id="a1d08-133">Ouvrez la Console de gestion des stratégies de groupe (gpmc.msc) et basculez vers modifier toute stratégie existante ou créer un nouveau.</span><span class="sxs-lookup"><span data-stu-id="a1d08-133">Open the Group Policy Management Console (gpmc.msc) and switch to editing any existing policy or creating a new one.</span></span>
    
2. <span data-ttu-id="a1d08-134">Accédez à **Configuration utilisateur\Préférences\Paramètres de Panneau de contrôle\Paramètres Internet**.</span><span class="sxs-lookup"><span data-stu-id="a1d08-134">Navigate to **User Configuration\Preferences\Control Panel Settings\Internet Settings**.</span></span>
    
3. <span data-ttu-id="a1d08-135">Avec le bouton droit, cliquez sur**Paramètres Internet** et sélectionnez **Internet Explorer 10**.</span><span class="sxs-lookup"><span data-stu-id="a1d08-135">Right-click on **Internet Settings** and select **Internet Explorer 10**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="a1d08-136">Vous devez sélectionner l’option d’Internet Explorer 10 pour appliquer les paramètres Internet Explorer 11 comme les mêmes paramètres s’appliquent à Internet Explorer 11.</span><span class="sxs-lookup"><span data-stu-id="a1d08-136">You need to select the option of Internet Explorer 10 to apply the settings for Internet Explorer 11 as the same settings apply to Internet Explorer 11.</span></span> 
  
4. <span data-ttu-id="a1d08-p104">Les paramètres qui sont soulignés en rouge ne sont pas configurés sur la machine cible, tandis que les paramètres soulignés en vert sont configurés à l’ordinateur cible. Pour modifier le soulignement, utilisez les touches de fonction suivantes :</span><span class="sxs-lookup"><span data-stu-id="a1d08-p104">Settings which are underlined in red are not configured at the target machine, while settings underlined in green are configured at the target machine. To change the underlining, use the following function keys:</span></span>
    
    <span data-ttu-id="a1d08-139">F5-Activer tous les paramètres sous l’onglet actif</span><span class="sxs-lookup"><span data-stu-id="a1d08-139">F5 - Enable all settings on the current tab</span></span>
    
    <span data-ttu-id="a1d08-140">F6-Activer les paramètres actuellement sélectionnés</span><span class="sxs-lookup"><span data-stu-id="a1d08-140">F6 - Enable the currently selected setting</span></span>
    
    <span data-ttu-id="a1d08-141">F7-Désactiver les paramètres actuellement sélectionnés</span><span class="sxs-lookup"><span data-stu-id="a1d08-141">F7 - Disable the currently selected setting</span></span>
    
    <span data-ttu-id="a1d08-142">F8-Désactiver tous les paramètres sous l’onglet actif</span><span class="sxs-lookup"><span data-stu-id="a1d08-142">F8 - Disable all settings on the current tab</span></span>
    
5. <span data-ttu-id="a1d08-p105">Appuyez sur**F8** pour désactiver tous les paramètres avant de configurer quoi que ce soit. L’écran doit ressembler à ceci :</span><span class="sxs-lookup"><span data-stu-id="a1d08-p105">Press **F8** to disable all settings before configuring anything. The screen should look like this:</span></span> 
    
    ![Boîte de dialogue Propriétés Internet Explorer 10](media/2fd55755-5007-4e33-a795-c42ce2fcef4a.jpg)
  
6. <span data-ttu-id="a1d08-146">Appuyez sur**F6** sur les paramètres de la page d’accueil et entrez `https://www.bing.com/business?form=BFBSPR`</span><span class="sxs-lookup"><span data-stu-id="a1d08-146">Press **F6** on the Home page setting and enter `https://www.bing.com/business?form=BFBSPR`</span></span>
    
7. <span data-ttu-id="a1d08-147">Appliquez la stratégie de groupe résultante GPO en la reliant au domaine approprié.</span><span class="sxs-lookup"><span data-stu-id="a1d08-147">Enforce the resultant GPO by linking it to the appropriate domain.</span></span>