---
title: Définir le mode de recherche par défaut
ms.author: jeffkizn
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
ms.assetid: ee40010e-5d7f-4ba8-a3f8-d240dab3af6d
description: Découvrez comment définir Bing comme moteur de recherche par défaut de votre entreprise à l’aide de Microsoft Search (recherche Microsoft).
ms.openlocfilehash: 346bf3bf2da10178a8bd19390920db2d9de2629e
ms.sourcegitcommit: 5df252e6d0bd67bb1b4c59418aceca8369f5fe42
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51031754"
---
# <a name="make-bing-the-default-search-engine"></a><span data-ttu-id="2a8cd-103">Définir Bing en tant que moteur de recherche par défaut</span><span class="sxs-lookup"><span data-stu-id="2a8cd-103">Make Bing the default search engine</span></span>
  
<span data-ttu-id="2a8cd-104">Cet article vous explique comment configurer Bing en tant que moteur de recherche par défaut pour Microsoft Edge, Google Chrome et Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="2a8cd-104">This article explains how you can make Bing the default search engine for Microsoft Edge, Google Chrome, and Internet Explorer.</span></span> 
  
## <a name="microsoft-edge-on-windows-10-version-1703-or-later"></a><span data-ttu-id="2a8cd-105">Microsoft Edge sur Windows 10, version 1703 ou ultérieure</span><span class="sxs-lookup"><span data-stu-id="2a8cd-105">Microsoft Edge on Windows 10, Version 1703 or later</span></span>

<span data-ttu-id="2a8cd-106">Bien que vous puissiez définir Bing en tant que moteur de recherche par défaut, Microsoft Edge autorise les utilisateurs à modifier leurs paramètres de manière à utiliser un autre moteur de recherche.</span><span class="sxs-lookup"><span data-stu-id="2a8cd-106">Although you'll set Bing as the default search engine, Microsoft Edge allows users to change their settings to use a different search engine.</span></span>
  
<span data-ttu-id="2a8cd-107">Concernant les fichiers récents d’ADMX relatifs aux différentes versions de Windows, reportez-vous à l’article [Comment créer et gérer le magasin central des modèles d’administration de stratégie de groupe dans Windows](https://support.microsoft.com/help/3087759/how-to-create-and-manage-the-central-store-for-group-policy-administra).</span><span class="sxs-lookup"><span data-stu-id="2a8cd-107">For the latest ADMX files for various versions of Windows, see [How to create and manage the Central Store for Group Policy Administrative Templates in Windows](https://support.microsoft.com/help/3087759/how-to-create-and-manage-the-central-store-for-group-policy-administra).</span></span>
  
<span data-ttu-id="2a8cd-108">Si le paramètre décrit dans cette section est in trouver dans gpMC, téléchargez le ADMX approprié et copiez-le dans le magasin central.</span><span class="sxs-lookup"><span data-stu-id="2a8cd-108">If the setting described in this section cannot be found inside of GPMC, download the appropriate ADMX and copy them to the central store.</span></span> <span data-ttu-id="2a8cd-109">Pour plus d’informations, voir [Modification de Domain-Based de groupe à l’aide de fichiers ADMX.](/previous-versions/windows/it-pro/windows-vista/cc748955%28v%3dws.10%29)</span><span class="sxs-lookup"><span data-stu-id="2a8cd-109">For more information, see [Editing Domain-Based GPOs Using ADMX Files](/previous-versions/windows/it-pro/windows-vista/cc748955%28v%3dws.10%29).</span></span> <span data-ttu-id="2a8cd-110">Le magasin central sur le contrôleur est un dossier avec la convention d’attribution de noms suivante : **%systemroot%\sysvol \\<domain \> \policies\PolicyDefinitions**</span><span class="sxs-lookup"><span data-stu-id="2a8cd-110">Central store on the controller is a folder with the following naming convention: **%systemroot%\sysvol\\<domain\>\policies\PolicyDefinitions**</span></span>
  
<span data-ttu-id="2a8cd-p102">Chaque domaine que votre contrôleur gère doit avoir un dossier séparé. La commande suivante peut être utilisée pour copier le fichier ADMX à partir de la commande rapide:</span><span class="sxs-lookup"><span data-stu-id="2a8cd-p102">Each domain that your controller handles should get a separate folder. The following command can be used to copy the ADMX file from the command prompt:</span></span>
  
 `Copy <path_to_ADMX.ADMX> %systemroot%\sysvol\<domain>\policies\PolicyDefinitions`
  
1. <span data-ttu-id="2a8cd-113">Ouvrez la Console de Gestion des Stratégies de Groupe (gpmc.msc) et basculez vers modifier toute stratégie existante ou créer un nouveau.</span><span class="sxs-lookup"><span data-stu-id="2a8cd-113">Open the Group Policy Management Console (gpmc.msc) and switch to editing an existing policy or creating a new one.</span></span>
2. <span data-ttu-id="2a8cd-114">Accédez à **&lt;Ordinateur/ Configuration Utilisateur&gt;\ Modèles administratifs\Composants Windows\Microsoft Edge**.</span><span class="sxs-lookup"><span data-stu-id="2a8cd-114">Navigate to **&lt;Computer/User Configuration&gt;\Administrative Templates\Windows Components\Microsoft Edge**.</span></span>
3. <span data-ttu-id="2a8cd-115">Double-cliquez sur **Définir le moteur de recherche par défaut**, définir à **Activé**, puis entrer`https://www.bing.com/sa/osd/bfb.xml`</span><span class="sxs-lookup"><span data-stu-id="2a8cd-115">Double-click **Set default search engine**, set to **Enabled**, and enter `https://www.bing.com/sa/osd/bfb.xml`</span></span>
4. <span data-ttu-id="2a8cd-116">Appliquez la stratégie de groupe résultante GPO en les reliant au domaine approprié.</span><span class="sxs-lookup"><span data-stu-id="2a8cd-116">Enforce the resultant GPO by linking it to the appropriate domain.</span></span>


## <a name="google-chrome-on-windows-10-version-1507-or-later"></a><span data-ttu-id="2a8cd-117">Google Chrome sur Windows 10, version 1507 ou ultérieure</span><span class="sxs-lookup"><span data-stu-id="2a8cd-117">Google Chrome on Windows 10, Version 1507 or later</span></span>

<span data-ttu-id="2a8cd-118">Une fois cette stratégie définie, les utilisateurs ne pourront plus modifier le moteur de recherche par défaut.</span><span class="sxs-lookup"><span data-stu-id="2a8cd-118">Users won't be able to change the default search engine after this policy is set.</span></span>
  
<span data-ttu-id="2a8cd-119">Chrome est fourni avec son propre ensemble de paramètres de stratégie de groupe qui peuvent être téléchargés sous la forme d’un fichier ADMX à partir de l’aide de [Google Chrome Enterprise](https://support.google.com/chrome/a/answer/187202).</span><span class="sxs-lookup"><span data-stu-id="2a8cd-119">Chrome comes with its own set of group policy settings which can be downloaded in the form of an ADMX file from [Google Chrome Enterprise Help](https://support.google.com/chrome/a/answer/187202).</span></span>
  
<span data-ttu-id="2a8cd-120">Copiez le fichier modèle dans un magasin central pour les fichiers ADMX sur le contrôleur de domaine.</span><span class="sxs-lookup"><span data-stu-id="2a8cd-120">Copy the template file to a central store for ADMX files on the domain controller.</span></span> <span data-ttu-id="2a8cd-121">Pour plus d’informations, voir [Modification de Domain-Based de groupe à l’aide de fichiers ADMX.](/previous-versions/windows/it-pro/windows-vista/cc748955%28v%3dws.10%29)</span><span class="sxs-lookup"><span data-stu-id="2a8cd-121">For more information, see [Editing Domain-Based GPOs Using ADMX Files](/previous-versions/windows/it-pro/windows-vista/cc748955%28v%3dws.10%29).</span></span> <span data-ttu-id="2a8cd-122">Le magasin central sur le contrôleur est un dossier avec la convention d’attribution de noms suivante : **%systemroot%\sysvol \\<domain \> \policies\PolicyDefinitions**</span><span class="sxs-lookup"><span data-stu-id="2a8cd-122">Central store on the controller is a folder with the following naming convention: **%systemroot%\sysvol\\<domain\>\policies\PolicyDefinitions**</span></span>
  
<span data-ttu-id="2a8cd-p104">Chaque domaine que votre contrôleur gère doit avoir un dossier séparé. La commande suivante peut être utilisée pour copier le fichier ADMX à partir de la commande rapide:</span><span class="sxs-lookup"><span data-stu-id="2a8cd-p104">Each domain that your controller handles should get a separate folder. The following command can be used to copy the ADMX file from the command prompt:</span></span>
  
 `Copy <path_to_Chrome.ADMX> %systemroot%\sysvol\<domain>\policies\PolicyDefinitions`
  
1. <span data-ttu-id="2a8cd-125">Ouvrez la Console de gestion des stratégies de groupe (gpmc.msc) et basculez vers modifier toute stratégie existante ou créer un nouveau.</span><span class="sxs-lookup"><span data-stu-id="2a8cd-125">Open the Group Policy Management Console (gpmc.msc) and switch to editing any existing policy or creating a new one.</span></span>
2. <span data-ttu-id="2a8cd-126">Assurez-vous que les dossiers suivants apparaissent dans la section Modèles Administratifs à la fois pour l’Utilisateur/la Configuration Ordinateur: Google Chrome et Google Chrome- Paramètres par défaut.</span><span class="sxs-lookup"><span data-stu-id="2a8cd-126">Make sure the following folders appear in the Administrative Templates section of both User/Computer Configuration: Google Chrome and Google Chrome - Default Settings.</span></span>

    - <span data-ttu-id="2a8cd-127">Les paramètres de la première section sont fixes et l’administrateur local ne pourra pas les modifier.</span><span class="sxs-lookup"><span data-stu-id="2a8cd-127">The settings of the first section are fixed and local administrators won't be able to change them in the browser.</span></span>
    - <span data-ttu-id="2a8cd-128">Les paramètres de la dernière section de stratégies peuvent être modifiés par les utilisateurs dans les paramètres de navigateur.</span><span class="sxs-lookup"><span data-stu-id="2a8cd-128">The settings of the latter section of policies can be changed by users in the browser settings.</span></span>

3. <span data-ttu-id="2a8cd-129">Accédez à **\<Computer/User\> Configuration\Modèles d’administration\Google Chrome\Fournisseur de recherche par défaut**</span><span class="sxs-lookup"><span data-stu-id="2a8cd-129">Navigate to **\<Computer/User\> Configuration\Administrative Templates\Google Chrome\Default search provider**</span></span>
4. <span data-ttu-id="2a8cd-130">Double-cliquez sur **Activer le fournisseur de recherche par défaut** et définissez-le comme programme **Activé**.</span><span class="sxs-lookup"><span data-stu-id="2a8cd-130">Double-click **Enable the default search provider**, and set it to **Enabled**.</span></span>
5. <span data-ttu-id="2a8cd-131">Double-cliquez sur **icône fournisseur de recherche par défaut**, définissez-le comme programme **Activé**, puis entrez `https://www.bing.com/sa/simg/bb.ico`</span><span class="sxs-lookup"><span data-stu-id="2a8cd-131">Double-click **Default search provider icon**, set it to **Enabled**, and enter `https://www.bing.com/sa/simg/bb.ico`</span></span>
6. <span data-ttu-id="2a8cd-132">Double-cliquez sur **l’URL instantané de fournisseur de recherche par défaut** puis entrez`https://www.bing.com/business/search?q={searchTerms}&amp;form=BFBSPR`</span><span class="sxs-lookup"><span data-stu-id="2a8cd-132">Double-click **Default search provider instant URL**, and enter `https://www.bing.com/business/search?q={searchTerms}&amp;form=BFBSPR`</span></span>
7. <span data-ttu-id="2a8cd-133">Double-cliquez sur **nom du fournisseur de recherche par défaut**, définissez-le comme Activé, puis entrez «Microsoft Search (recherche Microsoft) dans Bing»</span><span class="sxs-lookup"><span data-stu-id="2a8cd-133">Double-click **Default search provider name**, set it to Enabled, and enter 'Microsoft Search in Bing'</span></span>
8. <span data-ttu-id="2a8cd-134">Double-cliquez sur **l’URL fournisseur de recherche par défaut**, définissez-le comme **Activé**, puis entrez `https://www.bing.com/business/search?q={searchTerms}&amp;form=BFBSPR`</span><span class="sxs-lookup"><span data-stu-id="2a8cd-134">Double-click **Default search provider search URL**, set it to **Enabled**, and enter `https://www.bing.com/business/search?q={searchTerms}&amp;form=BFBSPR`</span></span>
9. <span data-ttu-id="2a8cd-135">Appliquez la stratégie de groupe résultante GPO en les reliant au domaine approprié.</span><span class="sxs-lookup"><span data-stu-id="2a8cd-135">Enforce the resultant GPO by linking it to the appropriate domain.</span></span>

## <a name="internet-explorer-11-or-later"></a><span data-ttu-id="2a8cd-136">Internet Explorer 11 ou version ultérieure</span><span class="sxs-lookup"><span data-stu-id="2a8cd-136">Internet Explorer 11 or later</span></span>

<span data-ttu-id="2a8cd-137">Une fois cette stratégie définie, les utilisateurs pourront modifier le moteur de recherche.</span><span class="sxs-lookup"><span data-stu-id="2a8cd-137">Users will be able to change the search provider after this policy is set.</span></span>
  
### <a name="step-1-configure-the-local-machine-that-will-be-used-to-set-the-gpo"></a><span data-ttu-id="2a8cd-138">ÉTAPE 1.</span><span class="sxs-lookup"><span data-stu-id="2a8cd-138">STEP 1.</span></span> <span data-ttu-id="2a8cd-139">Configurer l’ordinateur local destiné à être utilisé pour définir la stratégie de groupe</span><span class="sxs-lookup"><span data-stu-id="2a8cd-139">Configure the local machine that will be used to set the GPO</span></span>

<span data-ttu-id="2a8cd-140">Collez le texte suivant dans un fichier Bloc-notes(\*.reg).</span><span class="sxs-lookup"><span data-stu-id="2a8cd-140">Paste the following text into a reg(\*.reg) file.</span></span>
  
<span data-ttu-id="2a8cd-141">Windows Registry Editor Version 5.00</span><span class="sxs-lookup"><span data-stu-id="2a8cd-141">Windows Registry Editor Version 5.00</span></span>
  
<pre>[HKEY_CURRENT_USER\Software\Microsoft\Internet Explorer\SearchScopes]
"DefaultScope"="{D54CD0C8-C007-4BC4-B2DD-1E4896B8406D}"
[HKEY_CURRENT_USER\Software\Microsoft\Internet Explorer\SearchScopes\{D54CD0C8-C007-4BC4-B2DD-1E4896B8406D}]
"Codepage"=dword:0000fde9
"DisplayName"="Microsoft Search in Bing"
"OSDFileURL"="https://www.bing.com/sa/osd/bfb.xml"
"FaviconURL"="https://www.bing.com/sa/simg/bb.ico"
"URL"="https://www.bing.com/business/search?q={searchTerms}&amp;form=BFBSPR"</pre>
  
<span data-ttu-id="2a8cd-p106">Double-cliquez sur le fichier créé et suivez les étapes pour importer le fichier. Une importation réussie doit avoir pour résultat la boîte de dialogue suivante :</span><span class="sxs-lookup"><span data-stu-id="2a8cd-p106">Double-click the file created and follow the steps to import the file. A successful import should result in the following dialog:</span></span>
  
![Message d’importation réussi Éditeur du Registre](media/ea3686b9-f6d7-481e-9a0d-2c96891bc501.png)
  
### <a name="step-2-open-the-group-policy-management-console-gpmcmsc-and-switch-to-editing-an-existing-policy-or-creating-a-new-one"></a><span data-ttu-id="2a8cd-145">ÉTAPE 2.</span><span class="sxs-lookup"><span data-stu-id="2a8cd-145">STEP 2.</span></span> <span data-ttu-id="2a8cd-146">Ouvrir la Console de gestion des stratégies de groupe (gpmc.msc) et basculer en mode modification d’une stratégie existante ou en créer une nouvelle.</span><span class="sxs-lookup"><span data-stu-id="2a8cd-146">Open the Group Policy Management Console (gpmc.msc) and switch to editing an existing policy or creating a new one</span></span>

1. <span data-ttu-id="2a8cd-147">Accédez à **Configuration Utilisateur\Stratégies\Préférences\Paramètres Windows**.</span><span class="sxs-lookup"><span data-stu-id="2a8cd-147">Navigate to **User Configuration\Policies\Preferences\Windows Settings**.</span></span>
2. <span data-ttu-id="2a8cd-p108">Avec le bouton droit sur **Registre\Nouveau** et sélectionnez **Assistant Registre**. Dans la fenêtre du navigateur de Registre, sélectionnez **ordinateur Local** sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="2a8cd-p108">Right-click on **Registry\New** and select **Registry Wizard**. From the Registry Browser window, select **Local Computer** and click **Next**.</span></span>
3. <span data-ttu-id="2a8cd-150">Accédez à **HKEY_CURRENT_USER\SOFTWARE\Microsoft\Internet Explorer\SearchScopes**.</span><span class="sxs-lookup"><span data-stu-id="2a8cd-150">Navigate to **HKEY_CURRENT_USER\SOFTWARE\Microsoft\Internet Explorer\SearchScopes**.</span></span>
4. <span data-ttu-id="2a8cd-151">À partir de cette clé, veillez à sélectionner DefaultScope.</span><span class="sxs-lookup"><span data-stu-id="2a8cd-151">From this key, make sure to select DefaultScope.</span></span>

    ![Navigateur de Registre avec DefaultScope sélectionné](media/ec5a450d-0cba-4e9c-acba-1a09e8e90bad.png)
5. <span data-ttu-id="2a8cd-p109">Consultez toutes les sous-clés contenant le GUIDE de Microsoft Search (recherche Microsoft) dans Bing et chaque valeur sous la clé à l’exception d’un chemin d’accès aux profils utilisateur. Faites défiler vers le bas pour sélectionner d’autres éléments.</span><span class="sxs-lookup"><span data-stu-id="2a8cd-p109">Check all sub keys containing the GUID for Microsoft Search in Bing and every value under the key except any path to user profiles. Scroll down to select other items.</span></span>
6. <span data-ttu-id="2a8cd-155">Cliquez sur Terminer afin de compléter cette configuration.</span><span class="sxs-lookup"><span data-stu-id="2a8cd-155">Click Finish to complete this configuration.</span></span>

### <a name="step-3-set-up-user-preferences-to-help-eliminate-a-warning-the-user-may-get-when-defaultscope-search-is-enforced"></a><span data-ttu-id="2a8cd-156">ÉTAPE 3.</span><span class="sxs-lookup"><span data-stu-id="2a8cd-156">STEP 3.</span></span> <span data-ttu-id="2a8cd-157">Configurer les préférences d’utilisateur pour éliminer un avertissement que l’utilisateur peut recevoir quand la recherche DefaultScope est appliquée</span><span class="sxs-lookup"><span data-stu-id="2a8cd-157">Set up User Preferences to help eliminate a warning the user may get when DefaultScope search is enforced</span></span>

<span data-ttu-id="2a8cd-158">Ce message d’avertissement est normal et les utilisateurs d’un programme tente de modifier leurs paramètres d’alertes.</span><span class="sxs-lookup"><span data-stu-id="2a8cd-158">This warning is by design and alerts users of a program trying to modify their settings.</span></span>
  
1. <span data-ttu-id="2a8cd-159">Dans le même GPO, cliquez sur le bouton droit **Registre\Nouveauté** et sélectionnez **Assistant Registre**.</span><span class="sxs-lookup"><span data-stu-id="2a8cd-159">Within the same GPO, right click on **Registry\New** and select **Registry Wizard**.</span></span>
2. <span data-ttu-id="2a8cd-160">Accédez à **HKEY_CURRENT_USER\SOFTWARE\Microsoft\Internet Explorer\Préférences Utilisateur**.</span><span class="sxs-lookup"><span data-stu-id="2a8cd-160">Navigate to **HKEY_CURRENT_USER\SOFTWARE\Microsoft\Internet Explorer\User Preferences**.</span></span>
3. <span data-ttu-id="2a8cd-161">Sélectionnez la clé **Préférence Utilisateur**.</span><span class="sxs-lookup"><span data-stu-id="2a8cd-161">Select the **User Preference** key.</span></span>
4. <span data-ttu-id="2a8cd-162">Cliquez sur **Terminer**.</span><span class="sxs-lookup"><span data-stu-id="2a8cd-162">Click **Finish**.</span></span>
5. <span data-ttu-id="2a8cd-p111">Cliquez sur l’objet nouvellement créé. Dans le volet de droite, double-cliquez sur l’objet de Préférences d’utilisateur, modifiez le **Action** à **Supprimer et Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="2a8cd-p111">Click on the newly created object. On the right-side pane double click on the User Preferences object, change the **Action** to **Delete and Save**.</span></span>
6. <span data-ttu-id="2a8cd-165">Appliquez la stratégie de groupe résultante GPO en les reliant au domaine approprié.</span><span class="sxs-lookup"><span data-stu-id="2a8cd-165">Enforce the resultant GPO by linking it to the appropriate domain.</span></span>