---
title: Moteur de recherche par défaut Set
ms.author: dawholl
author: dawholl
manager: kellis
ms.date: 12/20/2018
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
ms.assetid: ee40010e-5d7f-4ba8-a3f8-d240dab3af6d
description: Découvrez comment configurer Bing comme moteur de recherche par défaut de votre société à l’aide de Microsoft Search.
ms.openlocfilehash: 1102c4c58b1e46e450276430a1e79b34964b4ad4
ms.sourcegitcommit: bf52cc63b75f2e0324a716fe65da47702956b722
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/18/2019
ms.locfileid: "29378657"
---
# <a name="set-default-search-engine"></a><span data-ttu-id="ca482-103">Moteur de recherche par défaut Set</span><span class="sxs-lookup"><span data-stu-id="ca482-103">Set default search engine</span></span>

<span data-ttu-id="ca482-104">Configurer le navigateur par défaut, le moteur de recherche par défaut et la page d’accueil par défaut vous aidera vos utilisateurs découvrir les fonctionnalités de Microsoft Search, encourager l’utilisation de plus et fournir une meilleure expérience.</span><span class="sxs-lookup"><span data-stu-id="ca482-104">Configuring the default browser, default search engine, and default homepage will help your users discover Microsoft Search capabilities, encourage more usage, and provide a smoother experience.</span></span>
  
<span data-ttu-id="ca482-105">Pour définir le moteur de recherche par défaut pour votre organisation, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="ca482-105">To set the default search engine for your organization, follow the steps below.</span></span>
  
## <a name="internet-explorer"></a><span data-ttu-id="ca482-106">Internet Explorer</span><span class="sxs-lookup"><span data-stu-id="ca482-106">Internet Explorer</span></span>

### <a name="internet-explorer-11"></a><span data-ttu-id="ca482-107">Internet Explorer 11</span><span class="sxs-lookup"><span data-stu-id="ca482-107">Internet Explorer 11</span></span>

<span data-ttu-id="ca482-108">Les utilisateurs seront en mesure de modifier le fournisseur de recherche une fois que cette stratégie est définie.</span><span class="sxs-lookup"><span data-stu-id="ca482-108">Users will be able to change the search provider after this policy is set.</span></span>
  
#### <a name="1-configure-the-local-machine-that-will-be-used-to-set-the-gpo"></a><span data-ttu-id="ca482-109">1. Configuration de l’ordinateur local qui sera utilisé pour définir la stratégie de groupe</span><span class="sxs-lookup"><span data-stu-id="ca482-109">1. Configure the local machine that will be used to set the GPO</span></span>

<span data-ttu-id="ca482-110">Collez le texte suivant dans un Registre (\*.reg) fichier.</span><span class="sxs-lookup"><span data-stu-id="ca482-110">Paste the following text into a reg(\*.reg) file.</span></span>
  
<span data-ttu-id="ca482-111">Windows Registry Editor Version 5.00</span><span class="sxs-lookup"><span data-stu-id="ca482-111">Windows Registry Editor Version 5.00</span></span>
  
<pre>[HKEY_CURRENT_USER\Software\Microsoft\Internet Explorer\SearchScopes]
"DefaultScope"="{D54CD0C8-C007-4BC4-B2DD-1E4896B8406D}"
[HKEY_CURRENT_USER\Software\Microsoft\Internet Explorer\SearchScopes\{D54CD0C8-C007-4BC4-B2DD-1E4896B8406D}]
"Codepage"=dword:0000fde9
"DisplayName"="Microsoft Search in Bing"
"OSDFileURL"="https://www.bing.com/sa/osd/bfb.xml"
"FaviconURL"="https://www.bing.com/sa/simg/bb.ico"
"SuggestionsURL_JSON"="https://business.ing.com/api/v2/browser/suggest?q={searchTerms}&amp;form=BFBSPA"
"ShowSearchSuggestions"=dword:00000001
"URL"="https://www.bing.com/business/search?q={searchTerms}&amp;form=BFBSPR"</pre>
  
<span data-ttu-id="ca482-p101">Double-cliquez sur le fichier créé et suivez les étapes pour importer le fichier. Une importation réussie devrait se traduire par la boîte de dialogue suivante :</span><span class="sxs-lookup"><span data-stu-id="ca482-p101">Double-click the file created and follow the steps to import the file. A successful import should result in the following dialog:</span></span>
  
![Message d’importation réussie de l’Éditeur du Registre](media/ea3686b9-f6d7-481e-9a0d-2c96891bc501.png)
  
#### <a name="2-open-the-group-policy-management-console-gpmcmsc-and-switch-to-editing-an-existing-policy-or-creating-a-new-one"></a><span data-ttu-id="ca482-115">2. Ouvrez la Console de gestion de stratégie de groupe (gpmc.msc) et passer à la modification d’une stratégie existante ou créer un nouveau</span><span class="sxs-lookup"><span data-stu-id="ca482-115">2. Open the Group Policy Management Console (gpmc.msc) and switch to editing an existing policy or creating a new one</span></span>

1. <span data-ttu-id="ca482-116">Accédez à **paramètres Configuration\Policies\Preferences\Windows de l’utilisateur**.</span><span class="sxs-lookup"><span data-stu-id="ca482-116">Navigate to **User Configuration\Policies\Preferences\Windows Settings**.</span></span>
    
2. <span data-ttu-id="ca482-p102">Avec le bouton droit sur **Registry\New** et sélectionnez **l’Assistant de Registre**. Dans la fenêtre de navigateur dans le Registre, sélectionnez **l’Ordinateur Local** , cliquez sur **suivant**.</span><span class="sxs-lookup"><span data-stu-id="ca482-p102">Right-click on **Registry\New** and select **Registry Wizard**. From the Registry Browser window, select **Local Computer** and click **Next**.</span></span>
    
3. <span data-ttu-id="ca482-119">Accédez à **HKEY_CURRENT_USER\SOFTWARE\Microsoft\Internet Explorer\SearchScopes**.</span><span class="sxs-lookup"><span data-stu-id="ca482-119">Navigate to **HKEY_CURRENT_USER\SOFTWARE\Microsoft\Internet Explorer\SearchScopes**.</span></span>
    
4. <span data-ttu-id="ca482-120">À partir de cette clé, veillez à sélectionner DefaultScope.</span><span class="sxs-lookup"><span data-stu-id="ca482-120">From this key, make sure to select DefaultScope.</span></span>
    
    ![Navigateur dans le Registre avec DefaultScope sélectionné](media/ec5a450d-0cba-4e9c-acba-1a09e8e90bad.png)
  
5. <span data-ttu-id="ca482-p103">Vérifiez toutes les sous-clés qui contient le GUID pour Microsoft Search dans Bing et chaque valeur sous la clé, à l’exception de n’importe quel chemin d’accès à des profils utilisateur. Faites défiler vers le bas pour sélectionner d’autres éléments.</span><span class="sxs-lookup"><span data-stu-id="ca482-p103">Check all sub keys containing the GUID for Microsoft Search in Bing and every value under the key except any path to user profiles. Scroll down to select other items.</span></span>
    
    ![Navigateur dans le Registre avec les autres valeurs sélectionnées](media/7eef7690-8bc5-46cf-9cd8-bd134fc77a02.png)
  
6. <span data-ttu-id="ca482-125">Cliquez sur Terminer pour terminer cette configuration.</span><span class="sxs-lookup"><span data-stu-id="ca482-125">Click Finish to complete this configuration.</span></span>
    
#### <a name="3-set-up-user-preferences-to-help-eliminate-a-warning-the-user-may-get-when-defaultscope-search-is-enforced"></a><span data-ttu-id="ca482-126">3. configurer les préférences utilisateur afin d’éliminer un avertissement indiquant que l’utilisateur peut obtenir lors de l’application de recherche DefaultScope</span><span class="sxs-lookup"><span data-stu-id="ca482-126">3. Set up User Preferences to help eliminate a warning the user may get when DefaultScope search is enforced</span></span>

<span data-ttu-id="ca482-127">Cet avertissement est par défaut et avertit l’utilisateur d’un programme essaie de modifier leurs paramètres.</span><span class="sxs-lookup"><span data-stu-id="ca482-127">This warning is by design and alerts users of a program trying to modify their settings.</span></span>
  
1. <span data-ttu-id="ca482-128">Dans la même stratégie de groupe, cliquez avec le bouton droit sur **Registry\New** et sélectionnez **Assistant dans le Registre**.</span><span class="sxs-lookup"><span data-stu-id="ca482-128">Within the same GPO, right click on **Registry\New** and select **Registry Wizard**.</span></span>
    
2. <span data-ttu-id="ca482-129">Accédez à **HKEY_CURRENT_USER\SOFTWARE\Microsoft\Internet Explorer\User préférences**.</span><span class="sxs-lookup"><span data-stu-id="ca482-129">Navigate to **HKEY_CURRENT_USER\SOFTWARE\Microsoft\Internet Explorer\User Preferences**.</span></span>
    
3. <span data-ttu-id="ca482-130">Sélectionnez la clé de **Préférence de l’utilisateur** .</span><span class="sxs-lookup"><span data-stu-id="ca482-130">Select the **User Preference** key.</span></span>
    
4. <span data-ttu-id="ca482-131">Cliquez sur **Terminer**.</span><span class="sxs-lookup"><span data-stu-id="ca482-131">Click **Finish**.</span></span>
    
5. <span data-ttu-id="ca482-p104">Cliquez sur l’objet nouvellement créé. Dans le volet de droite, double-cliquez sur l’objet de préférences de l’utilisateur, modifier l' **Action** **Supprimer**et enregistrer.</span><span class="sxs-lookup"><span data-stu-id="ca482-p104">Click on the newly created object. On the right-side pane double click on the User Preferences object, change the **Action** to **Delete and Save**.</span></span>
    
<span data-ttu-id="ca482-134">Appliquer la stratégie de groupe qui en découlent à lier au domaine approprié.</span><span class="sxs-lookup"><span data-stu-id="ca482-134">Enforce the resultant GPO by linking it to the appropriate domain.</span></span>
  
## <a name="microsoft-edge"></a><span data-ttu-id="ca482-135">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="ca482-135">Microsoft Edge</span></span>

### <a name="windows-10-version-1703-or-later"></a><span data-ttu-id="ca482-136">Windows 10, 1703 ou Version ultérieure</span><span class="sxs-lookup"><span data-stu-id="ca482-136">Windows 10, Version 1703 or later</span></span>

<span data-ttu-id="ca482-137">Les utilisateurs seront en mesure de modifier le fournisseur de recherche une fois que cette stratégie est définie.</span><span class="sxs-lookup"><span data-stu-id="ca482-137">Users will be able to change the search provider after this policy is set.</span></span>
  
<span data-ttu-id="ca482-138">Pour les fichiers ADMX le plus récent pour les différentes versions de Windows, voir [comment créer et gérer le magasin Central de modèles d’administration de stratégie de groupe dans Windows](https://support.microsoft.com/en-us/help/3087759/how-to-create-and-manage-the-central-store-for-group-policy-administra).</span><span class="sxs-lookup"><span data-stu-id="ca482-138">For the latest ADMX files for various versions of Windows, see [How to create and manage the Central Store for Group Policy Administrative Templates in Windows](https://support.microsoft.com/en-us/help/3087759/how-to-create-and-manage-the-central-store-for-group-policy-administra).</span></span>
  
<span data-ttu-id="ca482-p105">Si le paramètre décrit dans cette section est introuvable à l’intérieur de la console GPMC, téléchargez le ADMX approprié et les copier dans le magasin central. Pour plus d’informations, voir [Stratégie de groupe de modification via des fichiers ADMX](https://docs.microsoft.com/en-us/previous-versions/windows/it-pro/windows-vista/cc748955%28v%3dws.10%29). Magasin central sur le contrôleur est un dossier avec la convention d’affectation de noms suivante :</span><span class="sxs-lookup"><span data-stu-id="ca482-p105">If the setting described in this section cannot be found inside of GPMC, download the appropriate ADMX and copy them to the central store. For more information, see [Editing Domain-Based GPOs Using ADMX Files](https://docs.microsoft.com/en-us/previous-versions/windows/it-pro/windows-vista/cc748955%28v%3dws.10%29). Central store on the controller is a folder with the following naming convention:</span></span>
  
 <span data-ttu-id="ca482-142">**%systemroot%\sysvol\\<domain\>\policies\PolicyDefinitions**</span><span class="sxs-lookup"><span data-stu-id="ca482-142">**%systemroot%\sysvol\\<domain\>\policies\PolicyDefinitions**</span></span>
  
<span data-ttu-id="ca482-p106">Chaque domaine qui gère votre contrôleur doit obtenir un dossier distinct. La commande suivante peut être utilisée pour copier le fichier ADMX à partir de l’invite de commandes :</span><span class="sxs-lookup"><span data-stu-id="ca482-p106">Each domain that your controller handles should get a separate folder. The following command can be used to copy the ADMX file from the command prompt:</span></span>
  
 `Copy <path_to_ADMX.ADMX> %systemroot%\sysvol\<domain>\policies\PolicyDefinitions`
  
1. <span data-ttu-id="ca482-145">Ouvrez la Console de gestion de stratégie de groupe (gpmc.msc) et passer à la modification d’une stratégie existante ou créer un nouveau.</span><span class="sxs-lookup"><span data-stu-id="ca482-145">Open the Group Policy Management Console (gpmc.msc) and switch to editing an existing policy or creating a new one.</span></span>
    
2. <span data-ttu-id="ca482-146">Accédez à \*\* &lt;Configuration ordinateur/utilisateur&gt;\Administrative Templates\Windows Components\Microsoft Edge\*\*.</span><span class="sxs-lookup"><span data-stu-id="ca482-146">Navigate to **&lt;Computer/User Configuration&gt;\Administrative Templates\Windows Components\Microsoft Edge**.</span></span>
    
1. <span data-ttu-id="ca482-147">Double-cliquez sur **l’ensemble de moteur de recherche par défaut**, défini sur **activé**, puis entrez`https://www.bing.com/sa/osd/bfb.xml`</span><span class="sxs-lookup"><span data-stu-id="ca482-147">Double-click **Set default search engine**, set to **Enabled**, and enter `https://www.bing.com/sa/osd/bfb.xml`</span></span>
    
3. <span data-ttu-id="ca482-148">Appliquer la stratégie de groupe qui en découlent à lier au domaine approprié.</span><span class="sxs-lookup"><span data-stu-id="ca482-148">Enforce the resultant GPO by linking it to the appropriate domain.</span></span>
    
## <a name="google-chrome"></a><span data-ttu-id="ca482-149">Google Chrome</span><span class="sxs-lookup"><span data-stu-id="ca482-149">Google Chrome</span></span>

### <a name="windows-xp-sp2-or-later"></a><span data-ttu-id="ca482-150">Windows XP SP2 ou version ultérieure</span><span class="sxs-lookup"><span data-stu-id="ca482-150">Windows XP SP2 or later</span></span>

<span data-ttu-id="ca482-151">Les utilisateurs ne pourront pas modifier le fournisseur de recherche une fois que cette stratégie est définie.</span><span class="sxs-lookup"><span data-stu-id="ca482-151">Users won't be able to change the search provider after this policy is set.</span></span>
  
<span data-ttu-id="ca482-p107">Chrome est fourni avec son propre ensemble de paramètres de stratégie de groupe qui peut être téléchargé sous la forme d’un fichier ADMX à partir de [Google Chrome entreprise aide](https://support.google.com/chrome/a/answer/187202). Si Windows Vista de systèmes d’exploitation/Server 2008 ou version ultérieure sont utilisés pour gérer les objets de stratégie de groupe pour le domaine, le fichier ADMX fourni dans ce package prend en charge les paramètres de Chrome sur Windows XP SP2 ou version ultérieure.</span><span class="sxs-lookup"><span data-stu-id="ca482-p107">Chrome comes with its own set of group policy settings which can be downloaded in the form of an ADMX file from [Google Chrome Enterprise Help](https://support.google.com/chrome/a/answer/187202). If operating systems Windows Vista/Server 2008 or later are used to manage GPO's for the domain, the ADMX file provided in this package takes care of Chrome settings on Windows XP SP2 or later.</span></span>
  
<span data-ttu-id="ca482-p108">Copiez le fichier de modèle pour un magasin central pour les fichiers ADMX sur le contrôleur de domaine. Pour plus d’informations, voir [Stratégie de groupe de modification via des fichiers ADMX](https://docs.microsoft.com/en-us/previous-versions/windows/it-pro/windows-vista/cc748955%28v%3dws.10%29). Magasin central sur le contrôleur est un dossier avec la convention d’affectation de noms suivante :</span><span class="sxs-lookup"><span data-stu-id="ca482-p108">Copy the template file to a central store for ADMX files on the domain controller. For more information, see [Editing Domain-Based GPOs Using ADMX Files](https://docs.microsoft.com/en-us/previous-versions/windows/it-pro/windows-vista/cc748955%28v%3dws.10%29). Central store on the controller is a folder with the following naming convention:</span></span>
  
 <span data-ttu-id="ca482-157">**%systemroot%\sysvol\\<domain\>\policies\PolicyDefinitions**</span><span class="sxs-lookup"><span data-stu-id="ca482-157">**%systemroot%\sysvol\\<domain\>\policies\PolicyDefinitions**</span></span>
  
<span data-ttu-id="ca482-p109">Chaque domaine qui gère votre contrôleur doit obtenir un dossier distinct. La commande suivante peut être utilisée pour copier le fichier ADMX à partir de l’invite de commandes :</span><span class="sxs-lookup"><span data-stu-id="ca482-p109">Each domain that your controller handles should get a separate folder. The following command can be used to copy the ADMX file from the command prompt:</span></span>
  
 `Copy <path_to_Chrome.ADMX> %systemroot%\sysvol\<domain>\policies\PolicyDefinitions`
  
1. <span data-ttu-id="ca482-160">Ouvrez la Console de gestion de stratégie de groupe (gpmc.msc) et passer à la modification d’une stratégie existante ou créer un nouveau.</span><span class="sxs-lookup"><span data-stu-id="ca482-160">Open the Group Policy Management Console (gpmc.msc) and switch to editing any existing policy or creating a new one.</span></span>
    
2. <span data-ttu-id="ca482-161">Assurez-vous que les dossiers suivants apparaissent dans la section modèles d’administration de deux Configuration ordinateur/utilisateur : Google Chrome et Google Chrome - paramètres par défaut.</span><span class="sxs-lookup"><span data-stu-id="ca482-161">Make sure the following folders appear in the Administrative Templates section of both User/Computer Configuration: Google Chrome and Google Chrome - Default Settings.</span></span>
    
  - <span data-ttu-id="ca482-162">Les paramètres de la première section sont fixes et les administrateurs locaux ne pourront pas les modifier dans le navigateur.</span><span class="sxs-lookup"><span data-stu-id="ca482-162">The settings of the first section are fixed and local administrators won't be able to change them in the browser.</span></span>
    
  - <span data-ttu-id="ca482-163">Les paramètres de la section de ce dernier de stratégies peuvent être modifiés par les utilisateurs dans les paramètres du navigateur.</span><span class="sxs-lookup"><span data-stu-id="ca482-163">The settings of the latter section of policies can be changed by users in the browser settings.</span></span>
    
3. <span data-ttu-id="ca482-164">Accédez à \*\* \<utilisateur de l’ordinateur/\> fournisseur de recherche Chrome\Default Templates\Google de configuration\*\*</span><span class="sxs-lookup"><span data-stu-id="ca482-164">Navigate to **\<Computer/User\> Configuration\Administrative Templates\Google Chrome\Default search provider**</span></span>
    
4. <span data-ttu-id="ca482-165">Double-cliquez sur **Activer le fournisseur de recherche par défaut**, puis définissez-la sur **activé**.</span><span class="sxs-lookup"><span data-stu-id="ca482-165">Double-click **Enable the default search provider**, and set it to **Enabled**.</span></span>
    
5. <span data-ttu-id="ca482-166">Double-cliquez sur **icône de fournisseur de recherche par défaut**, définissez-la sur **activé**, puis entrez`https://www.bing.com/sa/simg/bb.ico`</span><span class="sxs-lookup"><span data-stu-id="ca482-166">Double-click **Default search provider icon**, set it to **Enabled**, and enter `https://www.bing.com/sa/simg/bb.ico`</span></span>
    
6. <span data-ttu-id="ca482-167">Double-cliquez sur **URL instantanée fournisseur de recherche par défaut**, puis entrez`https://www.bing.com/business/search?q={searchTerms}&amp;form=BFBSPR`</span><span class="sxs-lookup"><span data-stu-id="ca482-167">Double-click **Default search provider instant URL**, and enter `https://www.bing.com/business/search?q={searchTerms}&amp;form=BFBSPR`</span></span>
    
7. <span data-ttu-id="ca482-168">Double-cliquez sur le **nom de fournisseur de recherche par défaut**, définissez-la sur activé et entrez « Microsoft Search dans Bing »</span><span class="sxs-lookup"><span data-stu-id="ca482-168">Double-click **Default search provider name**, set it to Enabled, and enter 'Microsoft Search in Bing'</span></span>
    
8. <span data-ttu-id="ca482-169">Double-cliquez sur **recherche URL du fournisseur de recherche par défaut**, définissez-la sur **activé**, puis entrez`https://www.bing.com/business/search?q={searchTerms}&amp;form=BFBSPR`</span><span class="sxs-lookup"><span data-stu-id="ca482-169">Double-click **Default search provider search URL**, set it to **Enabled**, and enter `https://www.bing.com/business/search?q={searchTerms}&amp;form=BFBSPR`</span></span>
    
9. <span data-ttu-id="ca482-170">Double-cliquez sur le **fournisseur de recherche par défaut suggérer URL**, définissez-la sur **activé**, puis entrez`https://business.bing.com/api/v2/browser/suggest?q={searchTerms}&amp;form=BFBSPA`</span><span class="sxs-lookup"><span data-stu-id="ca482-170">Double-click **Default search provider suggest URL**, set it to **Enabled**, and enter `https://business.bing.com/api/v2/browser/suggest?q={searchTerms}&amp;form=BFBSPA`</span></span>
    
10. <span data-ttu-id="ca482-171">Appliquer la stratégie de groupe qui en découlent à lier au domaine approprié.</span><span class="sxs-lookup"><span data-stu-id="ca482-171">Enforce the resultant GPO by linking it to the appropriate domain.</span></span>
    
<span data-ttu-id="ca482-p110">Le moteur de recherche par défaut ajoute la fonctionnalité de suggestions de recherche Microsoft Search dans la barre d’adresse de navigateur. Actuellement, il prend en charge les signets uniquement. Les utilisateurs voient les suggestions de deux signet principaux au-dessus de suggestions web publics en tapant dans la barre d’adresses.</span><span class="sxs-lookup"><span data-stu-id="ca482-p110">Setting the default search engine will add the Microsoft Search search suggestions feature in the browser address bar. Currently, this supports bookmarks only. Users will see the top two bookmark suggestions above public web suggestions as they type in the address bar.</span></span>