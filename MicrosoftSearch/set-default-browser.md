---
title: Navigateur par défaut de SET
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
ms.assetid: 53e2b71a-348b-4dfe-a504-6e97d573effe
description: Découvrez comment configurer un navigateur par défaut pour l’entreprise avec Microsoft Search.
ms.openlocfilehash: 13a0a878b3288abeb7b07defdab839a158adc2ac
ms.sourcegitcommit: bf52cc63b75f2e0324a716fe65da47702956b722
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/18/2019
ms.locfileid: "29378669"
---
# <a name="set-default-browser"></a><span data-ttu-id="3372e-103">Navigateur par défaut de SET</span><span class="sxs-lookup"><span data-stu-id="3372e-103">Set default browser</span></span>

<span data-ttu-id="3372e-104">Configurer le navigateur par défaut, le moteur de recherche par défaut et la page d’accueil par défaut vous aidera vos utilisateurs découvrir les fonctionnalités de Microsoft Search, encourager l’utilisation de plus et fournir une meilleure expérience.</span><span class="sxs-lookup"><span data-stu-id="3372e-104">Configuring the default browser, default search engine, and default homepage will help your users discover Microsoft Search capabilities, encourage more usage, and provide a smoother experience.</span></span>
  
<span data-ttu-id="3372e-105">Pour définir le navigateur par défaut pour votre organisation, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="3372e-105">To set the default browser for your organization, follow the steps below.</span></span>
  
## <a name="windows-8-and-above"></a><span data-ttu-id="3372e-106">Windows 8 et versions ultérieures</span><span class="sxs-lookup"><span data-stu-id="3372e-106">Windows 8 and above</span></span>

<span data-ttu-id="3372e-107">Pour configurer Internet Explorer ou Microsoft Edge comme navigateur par défaut, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="3372e-107">To set Internet Explorer or Microsoft Edge as the default browser, follow these steps:</span></span>
  
### <a name="create-default-associations-file"></a><span data-ttu-id="3372e-108">Créer le fichier d’associations par défaut</span><span class="sxs-lookup"><span data-stu-id="3372e-108">Create default associations file</span></span>

1. <span data-ttu-id="3372e-109">Ouvrez une console d’administration de PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3372e-109">Open an administrative PowerShell console.</span></span>
    
2.  `New-Item -Path "\\$env:USERDOMAIN\SYSVOL\$env:USERDNSDOMAIN" -Type Directory -Name "Settings"`
    
3.  `$SettingsPath="\\$env:USERDOMAIN\SYSVOL\$env:USERDNSDOMAIN\Settings"`
    
4.  `Start-Process Dism.exe -PassThru "/Online /Export-DefaultAppAssociations:$SettingsPath\AppAssoc.xml"`
    
<span data-ttu-id="3372e-110">Ces étapes essaient et créer le fichier d’associations par défaut dans le dossier SYSVOL du contrôleur de domaine.</span><span class="sxs-lookup"><span data-stu-id="3372e-110">These steps try and create the default associations file in the SYSVOL folder of the domain controller.</span></span>
  
### <a name="add-or-edit-the-default-associations-file"></a><span data-ttu-id="3372e-111">Ajouter ou modifier le fichier d’associations par défaut</span><span class="sxs-lookup"><span data-stu-id="3372e-111">Add or edit the default associations file</span></span>

1. `Notepad "$SettingsPath\AppAssoc.xml"`
    
2. <span data-ttu-id="3372e-112">Modifier les entrées suivantes (.htm, .html, http, https) et supprimez les autres entrées s’ils ne sont pas nécessaires.</span><span class="sxs-lookup"><span data-stu-id="3372e-112">Edit the following entries (.htm, .html, http, https), and remove other entries if they're not needed.</span></span>
    
  - <span data-ttu-id="3372e-113">**Microsoft Edge**</span><span class="sxs-lookup"><span data-stu-id="3372e-113">**Microsoft Edge**</span></span>
    
     `<Association Identifier=".htm" ProgId="AppX4hxtad77fbk3jkkeerkrm0ze94wjf3s9" ApplicationName="Microsoft Edge" />`
  
     `<Association Identifier=".html" ProgId="AppX4hxtad77fbk3jkkeerkrm0ze94wjf3s9" ApplicationName="Microsoft Edge" />`
  
     `<Association Identifier="http" ProgId="AppXq0fevzme2pys62n3e0fbqa7peapykr8v" ApplicationName="Microsoft Edge" />`
    
  - <span data-ttu-id="3372e-114">**Internet Explorer**</span><span class="sxs-lookup"><span data-stu-id="3372e-114">**Internet Explorer**</span></span>
    
     `<Association Identifier=".htm" ProgId="htmlfile" ApplicationName="Internet Explorer" />`
  
     `<Association Identifier=".html" ProgId="htmlfile" ApplicationName="Internet Explorer" />`
  
     `<Association Identifier="http" ProgId="IE.HTTP" ApplicationName="Internet Explorer" />`
  
     `<Association Identifier="https" ProgId="IE.HTTPS" ApplicationName="Internet Explorer" />`
    
3. <span data-ttu-id="3372e-115">Ouvrez la Console de gestion des stratégies de groupe (gpmc.msc) et passer à la modification d’une stratégie existante ou créer un nouveau.</span><span class="sxs-lookup"><span data-stu-id="3372e-115">Open Group Policy Management Console (gpmc.msc) and switch to editing any existing policy or creating a new one.</span></span>
    
1. <span data-ttu-id="3372e-116">Accédez à la **configuration d’ordinateur administration\Composants Components\File Explorer**</span><span class="sxs-lookup"><span data-stu-id="3372e-116">Navigate to **Computer Configuration\Administrative Templates\Windows Components\File Explorer**</span></span>
    
2. <span data-ttu-id="3372e-117">Double-cliquez sur **la valeur d’un fichier de configuration d’associations par défaut**, définissez-la sur **activé**, puis entrez le chemin d’accès AppAssoc.xml (par exemple %USERDOMAIN%\SYSVOL\%USERDNSDOMAIN%\Settings\AppAssoc.xml)</span><span class="sxs-lookup"><span data-stu-id="3372e-117">Double-click **Set a default associations configuration file**, set it to **Enabled**, and enter the path to AppAssoc.xml (for example %USERDOMAIN%\SYSVOL\%USERDNSDOMAIN%\Settings\AppAssoc.xml)</span></span>
    
4. <span data-ttu-id="3372e-118">Appliquer la stratégie de groupe qui en découlent à lier au domaine approprié.</span><span class="sxs-lookup"><span data-stu-id="3372e-118">Enforce the resultant GPO by linking it to the appropriate domain.</span></span>
    
<span data-ttu-id="3372e-119">Les utilisateurs pourront modifier le navigateur une fois que cette stratégie est définie.</span><span class="sxs-lookup"><span data-stu-id="3372e-119">Users will be able to change the browser after this policy is set.</span></span>
  
## <a name="windows-7"></a><span data-ttu-id="3372e-120">Windows 7</span><span class="sxs-lookup"><span data-stu-id="3372e-120">Windows 7</span></span>

1. <span data-ttu-id="3372e-121">Configurer l’ordinateur local qui sera utilisé pour définir la stratégie de groupe.</span><span class="sxs-lookup"><span data-stu-id="3372e-121">Configure the local machine that will be used to set the GPO.</span></span>
    
1. <span data-ttu-id="3372e-122">Ouvrez **Programmes de contrôle Panel\Programs\Default Programs\Set par défaut** et définir Internet Explorer par défaut.</span><span class="sxs-lookup"><span data-stu-id="3372e-122">Open **Control Panel\Programs\Default Programs\Set Default Programs** and set Internet Explorer as the default.</span></span> 
    
2. <span data-ttu-id="3372e-123">Ouvrez la Console de gestion des stratégies de groupe (gpmc.msc) et passer à la modification d’une stratégie existante ou créer un nouveau.</span><span class="sxs-lookup"><span data-stu-id="3372e-123">Open Group Policy Management Console (gpmc.msc) and switch to editing any existing policy or creating a new one.</span></span>
    
1. <span data-ttu-id="3372e-124">Accédez à \*\* \<utilisateur de l’ordinateur/\> Configuration\Policies\Preferences\Windows paramètres\*\*.</span><span class="sxs-lookup"><span data-stu-id="3372e-124">Navigate to **\<Computer/User\> Configuration\Policies\Preferences\Windows Settings**.</span></span>
    
2. <span data-ttu-id="3372e-125">Avec le bouton droit sur **Registry\New** et sélectionnez **l’Assistant de Registre**.</span><span class="sxs-lookup"><span data-stu-id="3372e-125">Right-click on **Registry\New** and select **Registry Wizard**.</span></span>
    
3. <span data-ttu-id="3372e-126">Dans la fenêtre de navigateur dans le Registre, sélectionnez **l’Ordinateur Local** , cliquez sur **suivant**.</span><span class="sxs-lookup"><span data-stu-id="3372e-126">From the Registry Browser window, select **Local Computer** and click **Next**.</span></span>
    
4. <span data-ttu-id="3372e-p101">Accédez à **HKEY_CURRENT_USER\Software\Microsoft\Windows\Shell\Associations\UrlAssociations\https** et sélectionnez la valeur ProgId. Assurez-vous que la valeur ressemble à celui ci-dessous :</span><span class="sxs-lookup"><span data-stu-id="3372e-p101">Navigate to **HKEY_CURRENT_USER\Software\Microsoft\Windows\Shell\Associations\UrlAssociations\https** and select the ProgId value. Make sure the value looks like the one below:</span></span> 
    
    ![Sélectionner une valeur ProgID de modification de la chaîne](media/f6173dcc-b898-4967-8c40-4b0fe411a92b.png)
  
5. <span data-ttu-id="3372e-p102">Accédez à **HKEY_CURRENT_USER\Software\Microsoft\Windows\Shell\Associations\UrlAssociations\https** et sélectionnez la valeur ProgId. Assurez-vous que la valeur ressemble à celui ci-dessous :</span><span class="sxs-lookup"><span data-stu-id="3372e-p102">Navigate to **HKEY_CURRENT_USER\Software\Microsoft\Windows\Shell\Associations\UrlAssociations\https** and select the ProgId value. Make sure that the value looks like the one below:</span></span> 
    
    ![Sélectionnez ProgId pour le protocole HTTPS dans la chaîne de modification](media/3519e13b-4fe7-4d15-946c-82fd50fc49bb.png)
  
3. <span data-ttu-id="3372e-133">Appliquer la stratégie de groupe qui en découlent à lier au domaine approprié.</span><span class="sxs-lookup"><span data-stu-id="3372e-133">Enforce the resultant GPO by linking it to the appropriate domain.</span></span>
    
<span data-ttu-id="3372e-134">Les utilisateurs pourront modifier le navigateur une fois que cette stratégie est définie.</span><span class="sxs-lookup"><span data-stu-id="3372e-134">Users will be able to change the browser after this policy is set.</span></span>