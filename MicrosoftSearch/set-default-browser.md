---
title: Configurer la configuration par défaut
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
ms.assetid: 53e2b71a-348b-4dfe-a504-6e97d573effe
description: Découvrez comment configurer un navigateur par défaut pour votre entreprise avec Microsoft Search (recherche Microsoft).
ms.openlocfilehash: 160dbbef9981127b74c51f54f86428667ecd4471
ms.sourcegitcommit: 1c038d87efab4840d97b1f367b39e2b9ecdfee4a
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/29/2019
ms.locfileid: "29612472"
---
# <a name="set-default-browser"></a><span data-ttu-id="3f3c1-103">Configurer la configuration par défaut</span><span class="sxs-lookup"><span data-stu-id="3f3c1-103">Set default browser</span></span>

<span data-ttu-id="3f3c1-104">La configuration du navigateur par défaut, le moteur de recherche par défaut et la page d’accueil par défaut aideront vos utilisateurs à découvrir les fonctionnalités de Microsoft Search (recherche Microsoft), à plus encourager l’utilisation et offrir une expérience plus fluide.</span><span class="sxs-lookup"><span data-stu-id="3f3c1-104">Configuring the default browser, default search engine, and default homepage will help your users discover Microsoft Search capabilities, encourage more usage, and provide a smoother experience.</span></span>
  
<span data-ttu-id="3f3c1-105">Pour définir le navigateur par défaut pour votre organisation, suivez les étapes ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="3f3c1-105">To set the default browser for your organization, follow the steps below.</span></span>
  
## <a name="windows-8-and-above"></a><span data-ttu-id="3f3c1-106">Windows 8 ou version ultérieure</span><span class="sxs-lookup"><span data-stu-id="3f3c1-106">Windows 8 and above</span></span>

<span data-ttu-id="3f3c1-107">Pour définir Internet Explorer ou Microsoft Edge comme navigateur par défaut, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="3f3c1-107">To set Internet Explorer or Microsoft Edge as the default browser, follow these steps:</span></span>
  
### <a name="create-default-associations-file"></a><span data-ttu-id="3f3c1-108">Créez le fichier d’associations par défaut</span><span class="sxs-lookup"><span data-stu-id="3f3c1-108">Create default associations file</span></span>

1. <span data-ttu-id="3f3c1-109">Ouvrez une console d’administration PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3f3c1-109">Open an administrative PowerShell console.</span></span>
    
2.  `New-Item -Path "\\$env:USERDOMAIN\SYSVOL\$env:USERDNSDOMAIN" -Type Directory -Name "Settings"`
    
3.  `$SettingsPath="\\$env:USERDOMAIN\SYSVOL\$env:USERDNSDOMAIN\Settings"`
    
4.  `Start-Process Dism.exe -PassThru "/Online /Export-DefaultAppAssociations:$SettingsPath\AppAssoc.xml"`
    
<span data-ttu-id="3f3c1-110">Ces étapes essaient et créent le fichier d’associations par défaut dans le dossier SYSVOL du contrôleur de domaine.</span><span class="sxs-lookup"><span data-stu-id="3f3c1-110">These steps try and create the default associations file in the SYSVOL folder of the domain controller.</span></span>
  
### <a name="add-or-edit-the-default-associations-file"></a><span data-ttu-id="3f3c1-111">Ajoutez ou modifiez le fichier d’associations par défaut</span><span class="sxs-lookup"><span data-stu-id="3f3c1-111">Add or edit the default associations file</span></span>

1. `Notepad "$SettingsPath\AppAssoc.xml"`
    
2. <span data-ttu-id="3f3c1-112">Modifier les entrées suivantes (.htm, .html, http, https) et supprimez les autres entrées si elles ne sont pas utilisées.</span><span class="sxs-lookup"><span data-stu-id="3f3c1-112">Edit the following entries (.htm, .html, http, https), and remove other entries if they're not needed.</span></span>
    
  - <span data-ttu-id="3f3c1-113">**Microsoft Edge**</span><span class="sxs-lookup"><span data-stu-id="3f3c1-113">**Microsoft Edge**</span></span>
    
     `<Association Identifier=".htm" ProgId="AppX4hxtad77fbk3jkkeerkrm0ze94wjf3s9" ApplicationName="Microsoft Edge" />`
  
     `<Association Identifier=".html" ProgId="AppX4hxtad77fbk3jkkeerkrm0ze94wjf3s9" ApplicationName="Microsoft Edge" />`
  
     `<Association Identifier="http" ProgId="AppXq0fevzme2pys62n3e0fbqa7peapykr8v" ApplicationName="Microsoft Edge" />`
    
  - <span data-ttu-id="3f3c1-114">**Internet Explorer**</span><span class="sxs-lookup"><span data-stu-id="3f3c1-114">**Internet Explorer**</span></span>
    
     `<Association Identifier=".htm" ProgId="htmlfile" ApplicationName="Internet Explorer" />`
  
     `<Association Identifier=".html" ProgId="htmlfile" ApplicationName="Internet Explorer" />`
  
     `<Association Identifier="http" ProgId="IE.HTTP" ApplicationName="Internet Explorer" />`
  
     `<Association Identifier="https" ProgId="IE.HTTPS" ApplicationName="Internet Explorer" />`
    
3. <span data-ttu-id="3f3c1-115">Ouvrez la Console de gestion des stratégies de groupe (gpmc.msc) et basculez vers modifier toute stratégie existante ou créer un nouveau.</span><span class="sxs-lookup"><span data-stu-id="3f3c1-115">Open Group Policy Management Console (gpmc.msc) and switch to editing any existing policy or creating a new one.</span></span>
    
1. <span data-ttu-id="3f3c1-116">Accédez à**Configuration ordinateur\Administration administrative\Composants Windows\Dossier Explorer**</span><span class="sxs-lookup"><span data-stu-id="3f3c1-116">Navigate to **Computer Configuration\Administrative Templates\Windows Components\File Explorer**</span></span>
    
2. <span data-ttu-id="3f3c1-117">Double-cliquez sur **définir un fichier de configuration d’associations par défaut**, définissez-le comme programme **Activé**, puis entrez le chemin d’accès à AppAssoc.xml (par exemple %USERDOMAIN%\SYSVOL\%USERDNSDOMAIN%\Settings\ AppAssoc.xml)</span><span class="sxs-lookup"><span data-stu-id="3f3c1-117">Double-click **Set a default associations configuration file**, set it to **Enabled**, and enter the path to AppAssoc.xml (for example %USERDOMAIN%\SYSVOL\%USERDNSDOMAIN%\Settings\AppAssoc.xml)</span></span>
    
4. <span data-ttu-id="3f3c1-118">Appliquez la stratégie de groupe résultante GPO en les reliant au domaine approprié.</span><span class="sxs-lookup"><span data-stu-id="3f3c1-118">Enforce the resultant GPO by linking it to the appropriate domain.</span></span>
    
<span data-ttu-id="3f3c1-119">Les utilisateurs pourront modifier le navigateur après avoir défini cette stratégie.</span><span class="sxs-lookup"><span data-stu-id="3f3c1-119">Users will be able to change the browser after this policy is set.</span></span>
  
## <a name="windows-7"></a><span data-ttu-id="3f3c1-120">Windows 7</span><span class="sxs-lookup"><span data-stu-id="3f3c1-120">Windows 7</span></span>

1. <span data-ttu-id="3f3c1-121">Configurez l’ordinateur local destiné à être utilisé pour définir la stratégie de groupe (GPO).</span><span class="sxs-lookup"><span data-stu-id="3f3c1-121">Configure the local machine that will be used to set the GPO.</span></span>
    
1. <span data-ttu-id="3f3c1-122">Ouvrez le**programmes par défaut de contrôle\Programmes\Programmes par défaut\Définir les programmes par défaut** et définir Internet Explorer par défaut.</span><span class="sxs-lookup"><span data-stu-id="3f3c1-122">Open **Control Panel\Programs\Default Programs\Set Default Programs** and set Internet Explorer as the default.</span></span> 
    
2. <span data-ttu-id="3f3c1-123">Ouvrez la Console de gestion des stratégies de groupe (gpmc.msc) et basculez vers modifier toute stratégie existante ou créer un nouveau.</span><span class="sxs-lookup"><span data-stu-id="3f3c1-123">Open Group Policy Management Console (gpmc.msc) and switch to editing any existing policy or creating a new one.</span></span>
    
1. <span data-ttu-id="3f3c1-124">Accédez à \*\* \<Ordinateur/Utilisateur\> Configuration\Stratégies\Préférences\Paramètres Windows\*\*.</span><span class="sxs-lookup"><span data-stu-id="3f3c1-124">Navigate to **\<Computer/User\> Configuration\Policies\Preferences\Windows Settings**.</span></span>
    
2. <span data-ttu-id="3f3c1-125">Avec le bouton droit cliquez sur **Registre\Nouveauté** et sélectionnez **Assistant Registre**.</span><span class="sxs-lookup"><span data-stu-id="3f3c1-125">Right-click on **Registry\New** and select **Registry Wizard**.</span></span>
    
3. <span data-ttu-id="3f3c1-126">Dans la fenêtre du navigateur de Registre, sélectionnez **Ordinateur Local** sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="3f3c1-126">From the Registry Browser window, select **Local Computer** and click **Next**.</span></span>
    
4. <span data-ttu-id="3f3c1-p101">Accédez à **HKEY_CURRENT_USER\Software\Microsoft\Windows\Shell\Associations\UrlAssociations\https** et sélectionnez la valeur ProgId. Vérifiez que la valeur semblable à celui ci-dessous :</span><span class="sxs-lookup"><span data-stu-id="3f3c1-p101">Navigate to **HKEY_CURRENT_USER\Software\Microsoft\Windows\Shell\Associations\UrlAssociations\https** and select the ProgId value. Make sure the value looks like the one below:</span></span> 
    
    ![Sélectionner une valeur dans la modification de la chaîne ProgID](media/f6173dcc-b898-4967-8c40-4b0fe411a92b.png)
  
5. <span data-ttu-id="3f3c1-p102">Accédez à **HKEY_CURRENT_USER\Software\Microsoft\Windows\Shell\Associations\UrlAssociations\https** et sélectionnez la valeur ProgId. Vérifiez que la valeur semblable à celui ci-dessous :</span><span class="sxs-lookup"><span data-stu-id="3f3c1-p102">Navigate to **HKEY_CURRENT_USER\Software\Microsoft\Windows\Shell\Associations\UrlAssociations\https** and select the ProgId value. Make sure that the value looks like the one below:</span></span> 
    
    ![Sélectionner une valeur dans la modification de la chaîne ProgID pour HTTPS](media/3519e13b-4fe7-4d15-946c-82fd50fc49bb.png)
  
3. <span data-ttu-id="3f3c1-133">Appliquez la stratégie de groupe résultante GPO en les reliant au domaine approprié.</span><span class="sxs-lookup"><span data-stu-id="3f3c1-133">Enforce the resultant GPO by linking it to the appropriate domain.</span></span>
    
<span data-ttu-id="3f3c1-134">Les utilisateurs pourront modifier le navigateur après avoir défini cette stratégie.</span><span class="sxs-lookup"><span data-stu-id="3f3c1-134">Users will be able to change the browser after this policy is set.</span></span>