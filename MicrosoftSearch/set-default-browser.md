---
title: Configurer la configuration par défaut
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
ms.assetid: 53e2b71a-348b-4dfe-a504-6e97d573effe
ROBOTS: NOINDEX
description: Définissez votre navigateur par défaut sur Microsoft Edge ou Internet Explorer pour les utilisateurs de Recherche Microsoft.
ms.openlocfilehash: ed145a1811aba0b58158ed04dd3bf8dc089a0682
ms.sourcegitcommit: c2c9e66af1038efd2849d578f846680851f9e5d2
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/27/2019
ms.locfileid: "36639738"
---
# <a name="make-microsoft-edge-the-default-browser"></a><span data-ttu-id="d7f9e-103">Définir Microsoft Edge comme navigateur par défaut</span><span class="sxs-lookup"><span data-stu-id="d7f9e-103">Make Microsoft Edge the default browser</span></span>
  
<span data-ttu-id="d7f9e-104">Pour garantir à vos utilisateurs une expérience optimale avec Recherche Microsoft, vous pouvez définir Microsoft Edge comme navigateur par défaut.</span><span class="sxs-lookup"><span data-stu-id="d7f9e-104">To give your users the best experience with Microsoft Search, you can make Microsoft Edge the default browser.</span></span> <span data-ttu-id="d7f9e-105">De cette façon, Microsoft Edge ne deviendra le navigateur par défaut que pour les utilisateurs de votre organisation, les utilisateurs individuels pouvant toujours sélectionner un navigateur différent.</span><span class="sxs-lookup"><span data-stu-id="d7f9e-105">This will only set Microsoft Edge as the default browser for users in your org, individual users can still select a different browser.</span></span>
  
  
## <a name="windows-8-and-later"></a><span data-ttu-id="d7f9e-106">Windows 8 (et versions ultérieures)</span><span class="sxs-lookup"><span data-stu-id="d7f9e-106">Windows 8 and above</span></span>

<span data-ttu-id="d7f9e-107">Ces instructions vous montrent comment définir Microsoft Edge ou Internet Explorer comme navigateur par défaut pour les ordinateurs exécutant Windows 8 ou une version ultérieure.</span><span class="sxs-lookup"><span data-stu-id="d7f9e-107">These instructions show you how to make Microsoft Edge or Internet Explorer as the default browser for computers running Windows 8 or later.</span></span> <span data-ttu-id="d7f9e-108">Les utilisateurs pourront modifier le navigateur après avoir défini cette stratégie.</span><span class="sxs-lookup"><span data-stu-id="d7f9e-108">Users will be able to change the browser after this policy is set.</span></span>
  
### <a name="step-1-create-the-default-associations-file"></a><span data-ttu-id="d7f9e-109">ÉTAPE 1 : Créer le fichier d'associations par défaut</span><span class="sxs-lookup"><span data-stu-id="d7f9e-109">STEP 1: Create the default associations file</span></span>
<span data-ttu-id="d7f9e-110">Créez le fichier d’associations par défaut dans le dossier SYSVOL du contrôleur de domaine.</span><span class="sxs-lookup"><span data-stu-id="d7f9e-110">These steps try and create the default associations file in the SYSVOL folder of the domain controller.</span></span>

1. <span data-ttu-id="d7f9e-111">Ouvrez une console d’administration PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d7f9e-111">Open an administrative PowerShell console.</span></span>
1. `New-Item -Path "\\$env:USERDOMAIN\SYSVOL\$env:USERDNSDOMAIN" -Type Directory -Name "Settings"`
1. `$SettingsPath="\\$env:USERDOMAIN\SYSVOL\$env:USERDNSDOMAIN\Settings"`
1. `Start-Process Dism.exe -PassThru "/Online /Export-DefaultAppAssociations:$SettingsPath\AppAssoc.xml"`
    
  
### <a name="step-2-add-or-edit-the-default-associations-file"></a><span data-ttu-id="d7f9e-112">ÉTAPE 2.</span><span class="sxs-lookup"><span data-stu-id="d7f9e-112">Step 2</span></span> <span data-ttu-id="d7f9e-113">Ajoutez ou modifiez le fichier d’associations par défaut</span><span class="sxs-lookup"><span data-stu-id="d7f9e-113">Add or edit the default associations file</span></span>

1. `Notepad "$SettingsPath\AppAssoc.xml"`
1. <span data-ttu-id="d7f9e-114">Modifier les entrées suivantes (.htm, .html, http, https) et supprimez les autres entrées si elles ne sont pas utilisées.</span><span class="sxs-lookup"><span data-stu-id="d7f9e-114">Edit the following entries (.htm, .html, http, https), and remove other entries if they're not needed.</span></span>
  - <span data-ttu-id="d7f9e-115">**Microsoft Edge**</span><span class="sxs-lookup"><span data-stu-id="d7f9e-115">**Microsoft Edge**</span></span>
    - `<Association Identifier=".htm" ProgId="AppX4hxtad77fbk3jkkeerkrm0ze94wjf3s9" ApplicationName="Microsoft Edge" />`
              
    - `<Association Identifier=".html" ProgId="AppX4hxtad77fbk3jkkeerkrm0ze94wjf3s9" ApplicationName="Microsoft Edge" />`
    - `<Association Identifier="http" ProgId="AppXq0fevzme2pys62n3e0fbqa7peapykr8v" ApplicationName="Microsoft Edge" />`
    
  - <span data-ttu-id="d7f9e-116">**Internet Explorer**</span><span class="sxs-lookup"><span data-stu-id="d7f9e-116">**Internet Explorer**</span></span>
    
    - `<Association Identifier=".htm" ProgId="htmlfile" ApplicationName="Internet Explorer" />`        
    - `<Association Identifier=".html" ProgId="htmlfile" ApplicationName="Internet Explorer" />`
    - `<Association Identifier="http" ProgId="IE.HTTP" ApplicationName="Internet Explorer" />`
    - `<Association Identifier="https" ProgId="IE.HTTPS" ApplicationName="Internet Explorer" />`

### <a name="step-3-edit-the-group-policy"></a><span data-ttu-id="d7f9e-117">Étape 3.</span><span class="sxs-lookup"><span data-stu-id="d7f9e-117">Step 3.</span></span> <span data-ttu-id="d7f9e-118">Modifier la stratégie de groupe</span><span class="sxs-lookup"><span data-stu-id="d7f9e-118">Edit the Group Policy</span></span>

1. <span data-ttu-id="d7f9e-119">Ouvrez la **Console de gestion des stratégies de groupe** (gpmc.msc) et basculez vers modifier toute stratégie existante ou créer une nouvelle.</span><span class="sxs-lookup"><span data-stu-id="d7f9e-119">Open Group Policy Management Console (gpmc.msc) and switch to editing any existing policy or creating a new one.</span></span>
1. <span data-ttu-id="d7f9e-120">Accédez à**Configuration ordinateur\Modèles administratifs\Composants Windows\Explorateur de fichiers**.</span><span class="sxs-lookup"><span data-stu-id="d7f9e-120">Navigate to **Computer Configuration\Administrative Templates\Windows Components\File Explorer**</span></span>
1. <span data-ttu-id="d7f9e-121">Double-cliquez sur **Définir un fichier de configuration d’associations par défaut**, définissez-le sur **Activé**, puis entrez le chemin d’accès à AppAssoc.xml (par exemple %USERDOMAIN%\SYSVOL\%USERDNSDOMAIN%\Settings\ AppAssoc.xml) Appliquez l’objet de la stratégie de groupe GPO résultant en le liant au domaine approprié.</span><span class="sxs-lookup"><span data-stu-id="d7f9e-121">Double-click **Set a default associations configuration file**, set it to **Enabled**, and enter the path to AppAssoc.xml (for example %USERDOMAIN%\SYSVOL\%USERDNSDOMAIN%\Settings\AppAssoc.xml) Enforce the resultant GPO by linking it to the appropriate domain.</span></span>

  
## <a name="windows-7"></a><span data-ttu-id="d7f9e-122">Windows 7</span><span class="sxs-lookup"><span data-stu-id="d7f9e-122">Windows 7</span></span>

1. <span data-ttu-id="d7f9e-123">Configurez l’ordinateur local destiné à être utilisé pour définir la stratégie de groupe (GPO).</span><span class="sxs-lookup"><span data-stu-id="d7f9e-123">Configure the local machine that will be used to set the GPO.</span></span>
    
1. <span data-ttu-id="d7f9e-124">Ouvrez le**programmes par défaut de contrôle\Programmes\Programmes par défaut\Définir les programmes par défaut** et définir Internet Explorer par défaut.</span><span class="sxs-lookup"><span data-stu-id="d7f9e-124">Open **Control Panel\Programs\Default Programs\Set Default Programs** and set Internet Explorer as the default.</span></span> 
    
2. <span data-ttu-id="d7f9e-125">Ouvrez la Console de gestion des stratégies de groupe (gpmc.msc) et basculez vers modifier toute stratégie existante ou créer un nouveau.</span><span class="sxs-lookup"><span data-stu-id="d7f9e-125">Open Group Policy Management Console (gpmc.msc) and switch to editing any existing policy or creating a new one.</span></span>
    
1. <span data-ttu-id="d7f9e-126">Accédez à \*\* \<Ordinateur/Utilisateur\> Configuration\Stratégies\Préférences\Paramètres Windows\*\*.</span><span class="sxs-lookup"><span data-stu-id="d7f9e-126">Navigate to **\<Computer/User\> Configuration\Policies\Preferences\Windows Settings**.</span></span>
    
2. <span data-ttu-id="d7f9e-127">Avec le bouton droit cliquez sur **Registre\Nouveauté** et sélectionnez **Assistant Registre**.</span><span class="sxs-lookup"><span data-stu-id="d7f9e-127">Right-click on **Registry\New** and select **Registry Wizard**.</span></span>
    
3. <span data-ttu-id="d7f9e-128">Dans la fenêtre du navigateur de Registre, sélectionnez **Ordinateur Local** sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="d7f9e-128">From the Registry Browser window, select **Local Computer** and click **Next**.</span></span>
    
4. <span data-ttu-id="d7f9e-p105">Accédez à **HKEY_CURRENT_USER\Software\Microsoft\Windows\Shell\Associations\UrlAssociations\https** et sélectionnez la valeur ProgId. Vérifiez que la valeur semblable à celui ci-dessous :</span><span class="sxs-lookup"><span data-stu-id="d7f9e-p105">Navigate to **HKEY_CURRENT_USER\Software\Microsoft\Windows\Shell\Associations\UrlAssociations\https** and select the ProgId value. Make sure the value looks like the one below:</span></span> 
    
    ![Sélectionner une valeur dans la modification de la chaîne ProgID](media/f6173dcc-b898-4967-8c40-4b0fe411a92b.png)
  
5. <span data-ttu-id="d7f9e-p106">Accédez à **HKEY_CURRENT_USER\Software\Microsoft\Windows\Shell\Associations\UrlAssociations\https** et sélectionnez la valeur ProgId. Vérifiez que la valeur semblable à celui ci-dessous :</span><span class="sxs-lookup"><span data-stu-id="d7f9e-p106">Navigate to **HKEY_CURRENT_USER\Software\Microsoft\Windows\Shell\Associations\UrlAssociations\https** and select the ProgId value. Make sure that the value looks like the one below:</span></span> 
    
    ![Sélectionner une valeur dans la modification de la chaîne ProgID pour HTTPS](media/3519e13b-4fe7-4d15-946c-82fd50fc49bb.png)
  
3. <span data-ttu-id="d7f9e-135">Appliquez la stratégie de groupe résultante GPO en les reliant au domaine approprié.</span><span class="sxs-lookup"><span data-stu-id="d7f9e-135">Enforce the resultant GPO by linking it to the appropriate domain.</span></span>
    
