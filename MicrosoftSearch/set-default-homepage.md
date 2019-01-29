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
description: Découvrez comment configurer Bing en tant que la page d’accueil par défaut de votre société avec Microsoft Search.
ms.openlocfilehash: db0611ebd7f4a8344664825bbb42025f3bb36486
ms.sourcegitcommit: 1c038d87efab4840d97b1f367b39e2b9ecdfee4a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/29/2019
ms.locfileid: "29612488"
---
# <a name="set-default-homepage"></a><span data-ttu-id="3b323-103">Page d’accueil par défaut</span><span class="sxs-lookup"><span data-stu-id="3b323-103">Set default homepage</span></span>

<span data-ttu-id="3b323-104">Configurer le navigateur par défaut, le moteur de recherche par défaut et la page d’accueil par défaut vous aidera vos utilisateurs découvrir les fonctionnalités de Microsoft Search, encourager l’utilisation de plus et fournir une meilleure expérience.</span><span class="sxs-lookup"><span data-stu-id="3b323-104">Configuring the default browser, default search engine, and default homepage will help your users discover Microsoft Search  capabilities, encourage more usage, and provide a smoother experience.</span></span>
  
<span data-ttu-id="3b323-105">Pour définir la page d’accueil par défaut pour votre organisation, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="3b323-105">To set the default homepage for your organization, follow the steps below.</span></span>
  
## <a name="internet-explorer"></a><span data-ttu-id="3b323-106">Internet Explorer</span><span class="sxs-lookup"><span data-stu-id="3b323-106">Internet Explorer</span></span>

### <a name="internet-explorer-50-or-later"></a><span data-ttu-id="3b323-107">Internet Explorer 5.0 ou version ultérieure</span><span class="sxs-lookup"><span data-stu-id="3b323-107">Internet Explorer 5.0 or later</span></span>

1. <span data-ttu-id="3b323-108">Ouvrez la Console de gestion de stratégie de groupe (gpmc.msc) et passer à la modification d’une stratégie existante ou créer un nouveau.</span><span class="sxs-lookup"><span data-stu-id="3b323-108">Open the Group Policy Management Console (gpmc.msc) and switch to editing any existing policy or creating a new one.</span></span>
    
2. <span data-ttu-id="3b323-109">Accédez aux **paramètres de Windows\Maintenance Internet utilisateur Configuration\Preferences\Control du Panneau de configuration**.</span><span class="sxs-lookup"><span data-stu-id="3b323-109">Navigate to **User Configuration\Preferences\Control Panel Settings\Internet Settings**.</span></span>
    
3. <span data-ttu-id="3b323-110">Avec le bouton droit sur les **Paramètres Internet** et sélectionnez **Internet Explorer 10**.</span><span class="sxs-lookup"><span data-stu-id="3b323-110">Right-click on **Internet Settings** and select **Internet Explorer 10**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="3b323-111">Vous devez sélectionner l’option d’Internet Explorer 10 pour appliquer les paramètres d’Internet Explorer 11 les mêmes paramètres s’appliquent à Internet Explorer 11.</span><span class="sxs-lookup"><span data-stu-id="3b323-111">You need to select the option of Internet Explorer 10 to apply the settings for Internet Explorer 11 as the same settings apply to Internet Explorer 11.</span></span> 
  
4. <span data-ttu-id="3b323-p101">Les paramètres qui sont soulignés en rouge ne sont pas configurés au niveau de l’ordinateur cible, tandis que les paramètres soulignés en vert sont configurés au niveau de l’ordinateur cible. Pour modifier le soulignement, utilisez les touches de fonction suivantes :</span><span class="sxs-lookup"><span data-stu-id="3b323-p101">Settings which are underlined in red are not configured at the target machine, while settings underlined in green are configured at the target machine. To change the underlining, use the following function keys:</span></span>
    
    <span data-ttu-id="3b323-114">F5 - activer tous les paramètres sous l’onglet en cours</span><span class="sxs-lookup"><span data-stu-id="3b323-114">F5 - Enable all settings on the current tab</span></span>
    
    <span data-ttu-id="3b323-115">F6 - activer le paramètre actuellement sélectionné</span><span class="sxs-lookup"><span data-stu-id="3b323-115">F6 - Enable the currently selected setting</span></span>
    
    <span data-ttu-id="3b323-116">F7 - désactiver le paramètre actuellement sélectionné</span><span class="sxs-lookup"><span data-stu-id="3b323-116">F7 - Disable the currently selected setting</span></span>
    
    <span data-ttu-id="3b323-117">F8 - désactiver tous les paramètres sous l’onglet en cours</span><span class="sxs-lookup"><span data-stu-id="3b323-117">F8 - Disable all settings on the current tab</span></span>
    
5. <span data-ttu-id="3b323-p102">Appuyez sur la touche **F8** pour désactiver tous les paramètres avant de configurer rien. L’écran doit se présenter comme suit :</span><span class="sxs-lookup"><span data-stu-id="3b323-p102">Press **F8** to disable all settings before configuring anything. The screen should look like this:</span></span> 
    
    ![Boîte de dialogue Propriétés Internet Explorer 10](media/2fd55755-5007-4e33-a795-c42ce2fcef4a.jpg)
  
6. <span data-ttu-id="3b323-121">Appuyez sur **F6** dans la page d’accueil de paramètre et entrez`https://www.bing.com/business?form=BFBSPR`</span><span class="sxs-lookup"><span data-stu-id="3b323-121">Press **F6** on the Home page setting and enter `https://www.bing.com/business?form=BFBSPR`</span></span>
    
7. <span data-ttu-id="3b323-122">Appliquer la stratégie de groupe qui en découlent à lier au domaine approprié.</span><span class="sxs-lookup"><span data-stu-id="3b323-122">Enforce the resultant GPO by linking it to the appropriate domain.</span></span>
    
> [!NOTE]
> <span data-ttu-id="3b323-123">Les utilisateurs peuvent toujours modifier la page d’accueil une fois que cette stratégie est définie.</span><span class="sxs-lookup"><span data-stu-id="3b323-123">Users can still change the homepage after this policy is set.</span></span> 
  
## <a name="microsoft-edge"></a><span data-ttu-id="3b323-124">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="3b323-124">Microsoft Edge</span></span>

### <a name="windows-10-version-1511-or-later"></a><span data-ttu-id="3b323-125">Windows 10, 1511 ou Version ultérieure</span><span class="sxs-lookup"><span data-stu-id="3b323-125">Windows 10, Version 1511 or later</span></span>

1. <span data-ttu-id="3b323-126">Ouvrez la Console de gestion de stratégie de groupe (gpmc.msc) et passer à la modification d’une stratégie existante ou créer un nouveau.</span><span class="sxs-lookup"><span data-stu-id="3b323-126">Open the Group Policy Management Console (gpmc.msc) and switch to editing any existing policy or creating a new one.</span></span>
    
2. <span data-ttu-id="3b323-127">Accédez à **administration administration\Composants Components\Microsoft Edge**</span><span class="sxs-lookup"><span data-stu-id="3b323-127">Navigate to **Administrative Templates\Windows Components\Microsoft Edge**</span></span>
    
1. <span data-ttu-id="3b323-128">Double-cliquez sur **des pages de configuration de démarrage**, définissez-la sur **activé**, puis entrez`https://www.bing.com/business`</span><span class="sxs-lookup"><span data-stu-id="3b323-128">Double-click **Configure Start pages**, set it to **Enabled**, and enter `https://www.bing.com/business`</span></span>
    
3. <span data-ttu-id="3b323-129">Appliquer la stratégie de groupe qui en découlent à lier au domaine approprié.</span><span class="sxs-lookup"><span data-stu-id="3b323-129">Enforce the resultant GPO by linking it to the appropriate domain.</span></span>
    
> [!CAUTION]
> <span data-ttu-id="3b323-130">Les utilisateurs ne pourront pas modifier le fournisseur de recherche une fois que cette stratégie est définie.</span><span class="sxs-lookup"><span data-stu-id="3b323-130">Users won't be able to change the search provider after this policy is set.</span></span> 
  
## <a name="google-chrome"></a><span data-ttu-id="3b323-131">Google Chrome</span><span class="sxs-lookup"><span data-stu-id="3b323-131">Google Chrome</span></span>

### <a name="windows-xp-sp2-or-later"></a><span data-ttu-id="3b323-132">Windows XP SP2 ou version ultérieure</span><span class="sxs-lookup"><span data-stu-id="3b323-132">Windows XP SP2 or later</span></span>

<span data-ttu-id="3b323-133">L’article de la prise en charge de Windows sur la gestion des fichiers ADMX et les fichiers ADMX le plus récent pour les différentes versions de Windows se trouvent [sur le support technique Microsoft](https://support.microsoft.com/en-us/help/3087759/how-to-create-and-manage-the-central-store-for-group-policy-administra).</span><span class="sxs-lookup"><span data-stu-id="3b323-133">The Windows Support article on managing ADMX files and the latest ADMX files for different versions of Windows can be found [on Microsoft Support](https://support.microsoft.com/en-us/help/3087759/how-to-create-and-manage-the-central-store-for-group-policy-administra).</span></span>

<span data-ttu-id="3b323-134">Vous devez également le fichier de stratégie Google le plus récent, vous pouvez trouver dans [l’Aide de Google Chrome Enterprise](https://support.google.com/chrome/a/answer/187202).</span><span class="sxs-lookup"><span data-stu-id="3b323-134">You'll also need the latest Google policy file, which you can find on [Google Chrome Enterprise Help](https://support.google.com/chrome/a/answer/187202).</span></span>
  
<span data-ttu-id="3b323-p103">Si les paramètres décrits dans cette section est introuvable à l’intérieur de la console GPMC, téléchargez le ADMX approprié et les copier dans le [magasin central](https://docs.microsoft.com/en-us/previous-versions/windows/it-pro/windows-vista/cc748955%28v%3dws.10%29). Magasin central sur le contrôleur est un dossier avec la convention d’affectation de noms suivante :</span><span class="sxs-lookup"><span data-stu-id="3b323-p103">If the settings described in this section can't be found inside of GPMC, download the appropriate ADMX and copy them to the [central store](https://docs.microsoft.com/en-us/previous-versions/windows/it-pro/windows-vista/cc748955%28v%3dws.10%29). Central store on the controller is a folder with the following naming convention:</span></span>
  
 <span data-ttu-id="3b323-137">**%systemroot%\sysvol\\<domain\>\policies\PolicyDefinitions**</span><span class="sxs-lookup"><span data-stu-id="3b323-137">**%systemroot%\sysvol\\<domain\>\policies\PolicyDefinitions**</span></span>
  
<span data-ttu-id="3b323-p104">Chaque domaine les poignées de votre contrôleur doivent obtenir un dossier distinct. La commande suivante peut être utilisée pour copier le fichier ADMX à partir de l’invite de commandes :</span><span class="sxs-lookup"><span data-stu-id="3b323-p104">Each domain your controller handles should get a separate folder. The following command can be used to copy the ADMX file from the command prompt:</span></span>
  
 `Copy <path_to_ADMX.ADMX> %systemroot%\sysvol\<domain>\policies\PolicyDefinitions`
  
1. <span data-ttu-id="3b323-140">Ouvrez la Console de gestion de stratégie de groupe (gpmc.msc) et passer à la modification d’une stratégie existante ou créer un nouveau.</span><span class="sxs-lookup"><span data-stu-id="3b323-140">Open the Group Policy Management Console (gpmc.msc) and switch to editing any existing policy or creating a new one.</span></span>
    
2. <span data-ttu-id="3b323-141">Assurez-vous que les dossiers suivants apparaissent dans la section **Modèles d’administration** de deux *Configuration utilisateur/ordinateur*: Google Chrome et Google Chrome - paramètres par défaut (modifiable).</span><span class="sxs-lookup"><span data-stu-id="3b323-141">Make sure the following folders appear in the **Administrative Templates** section of both *User/Computer Configuration*: Google Chrome and Google Chrome - Default Settings (users can override).</span></span>
    
   - <span data-ttu-id="3b323-142">Les paramètres de la première section sont fixes et l’administrateur local ne sera pas en mesure de les modifier.</span><span class="sxs-lookup"><span data-stu-id="3b323-142">The settings of the first section are fixed and the local administrator won't be able to change them.</span></span>
    
   - <span data-ttu-id="3b323-p105">Les paramètres de la section de ce dernier de stratégies peuvent être modifiés par les utilisateurs dans leurs paramètres de navigateur. Vous devez décider si les utilisateurs peuvent remplacer le paramètre par défaut. Dans les étapes suivantes, modifier dans le paramètre dans le dossier qui correspond à vos besoins et la stratégie de l’organisation. Les étapes ci-dessous utilisent le Google Chrome - paramètres par défaut, la valeur par défaut.</span><span class="sxs-lookup"><span data-stu-id="3b323-p105">The settings of the latter section of policies can be changed by users in their browser settings. You should decide if users can override your default setting. In the following steps, change in the setting in the folder that corresponds to your organization policy and needs. The steps below use the Google Chrome - Default Settings as the default.</span></span>
    
3. <span data-ttu-id="3b323-147">Accédez à \*\* &lt;Configuration ordinateur/utilisateur&gt;\Administrative Templates\Google Chrome - par défaut Settings\Home Page\*\*.</span><span class="sxs-lookup"><span data-stu-id="3b323-147">Navigate to **&lt;Computer/User Configuration&gt;\Administrative Templates\Google Chrome - Default Settings\Home Page**.</span></span>
    
4. <span data-ttu-id="3b323-148">Double-cliquez sur la **Page du nouvel onglet utilisation en tant que page d’accueil**et définissez-la sur **activé**.</span><span class="sxs-lookup"><span data-stu-id="3b323-148">Double-click **Use New Tab Page as homepage**, and set it to **Enabled**.</span></span>
    
5. <span data-ttu-id="3b323-149">Accédez à \*\* &lt;Configuration ordinateur/utilisateur&gt;\Administrative Templates\Google Chrome - Page de l’onglet par défaut Settings\New\*\*.</span><span class="sxs-lookup"><span data-stu-id="3b323-149">Navigate to **&lt;Computer/User Configuration&gt;\Administrative Templates\Google Chrome - Default Settings\New Tab Page**.</span></span>
    
6. <span data-ttu-id="3b323-150">Double-cliquez sur **configuration de la nouvelle URL de Page d’onglet**, définissez-la sur **activé**, puis entrez`https://www.bing.com/business?form=BFBSPR`</span><span class="sxs-lookup"><span data-stu-id="3b323-150">Double-click **Configure the New Tab Page URL**, set it to **Enabled**, and enter `https://www.bing.com/business?form=BFBSPR`</span></span>
    
7. <span data-ttu-id="3b323-151">Appliquer la stratégie de groupe qui en découlent à lier au domaine approprié.</span><span class="sxs-lookup"><span data-stu-id="3b323-151">Enforce the resultant GPO by linking it to the appropriate domain.</span></span>
    
<span data-ttu-id="3b323-152">Les utilisateurs seront en mesure de modifier la page d’accueil une fois que cette stratégie est définie.</span><span class="sxs-lookup"><span data-stu-id="3b323-152">Users will be able to change the home page after this policy is set.</span></span>