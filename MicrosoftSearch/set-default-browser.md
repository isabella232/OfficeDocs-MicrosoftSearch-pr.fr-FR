---
title: Configurer la configuration par défaut
ms.author: anfowler
author: adefowler
manager: shohara
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
ms.assetid: 53e2b71a-348b-4dfe-a504-6e97d573effe
description: Définissez votre navigateur par défaut sur Microsoft Edge ou Internet Explorer pour les utilisateurs de Recherche Microsoft.
ms.openlocfilehash: b99127411d070b37fe34a4f8468449f2354cb6be
ms.sourcegitcommit: 21361af7c244ffd6ff8689fd0ff0daa359bf4129
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/14/2019
ms.locfileid: "38626935"
---
# <a name="make-microsoft-edge-the-default-browser"></a>Définir Microsoft Edge comme navigateur par défaut
  
Pour garantir à vos utilisateurs une expérience optimale avec Recherche Microsoft, vous pouvez définir Microsoft Edge comme navigateur par défaut. De cette façon, Microsoft Edge ne deviendra le navigateur par défaut que pour les utilisateurs de votre organisation, les utilisateurs individuels pouvant toujours sélectionner un navigateur différent.
  
  
## <a name="windows-8-and-later"></a>Windows 8 (et versions ultérieures)

Ces instructions vous montrent comment définir Microsoft Edge ou Internet Explorer comme navigateur par défaut pour les ordinateurs exécutant Windows 8 ou une version ultérieure. Les utilisateurs pourront modifier le navigateur après avoir défini cette stratégie.
  
### <a name="step-1-create-the-default-associations-file"></a>ÉTAPE 1 : Créer le fichier d'associations par défaut
Créez le fichier d’associations par défaut dans le dossier SYSVOL du contrôleur de domaine.

1. Ouvrez une console d’administration PowerShell.
1. `New-Item -Path "\\$env:USERDOMAIN\SYSVOL\$env:USERDNSDOMAIN" -Type Directory -Name "Settings"`
1. `$SettingsPath="\\$env:USERDOMAIN\SYSVOL\$env:USERDNSDOMAIN\Settings"`
1. `Start-Process Dism.exe -PassThru "/Online /Export-DefaultAppAssociations:$SettingsPath\AppAssoc.xml"`
    
  
### <a name="step-2-add-or-edit-the-default-associations-file"></a>ÉTAPE 2. Ajoutez ou modifiez le fichier d’associations par défaut

1. `Notepad "$SettingsPath\AppAssoc.xml"`
1. Modifier les entrées suivantes (.htm, .html, http, https) et supprimez les autres entrées si elles ne sont pas utilisées.
  - **Microsoft Edge**
    - `<Association Identifier=".htm" ProgId="AppX4hxtad77fbk3jkkeerkrm0ze94wjf3s9" ApplicationName="Microsoft Edge" />`
              
    - `<Association Identifier=".html" ProgId="AppX4hxtad77fbk3jkkeerkrm0ze94wjf3s9" ApplicationName="Microsoft Edge" />`
    - `<Association Identifier="http" ProgId="AppXq0fevzme2pys62n3e0fbqa7peapykr8v" ApplicationName="Microsoft Edge" />`
    
  - **Internet Explorer**
    
    - `<Association Identifier=".htm" ProgId="htmlfile" ApplicationName="Internet Explorer" />`        
    - `<Association Identifier=".html" ProgId="htmlfile" ApplicationName="Internet Explorer" />`
    - `<Association Identifier="http" ProgId="IE.HTTP" ApplicationName="Internet Explorer" />`
    - `<Association Identifier="https" ProgId="IE.HTTPS" ApplicationName="Internet Explorer" />`

### <a name="step-3-edit-the-group-policy"></a>Étape 3. Modifier la stratégie de groupe

1. Ouvrez la **Console de gestion des stratégies de groupe** (gpmc.msc) et basculez vers modifier toute stratégie existante ou créer une nouvelle.
1. Accédez à**Configuration ordinateur\Modèles administratifs\Composants Windows\Explorateur de fichiers**.
1. Double-cliquez sur **Définir un fichier de configuration d’associations par défaut**, définissez-le sur **Activé**, puis entrez le chemin d’accès à AppAssoc.xml (par exemple %USERDOMAIN%\SYSVOL\%USERDNSDOMAIN%\Settings\ AppAssoc.xml) Appliquez l’objet de la stratégie de groupe GPO résultant en le liant au domaine approprié.

  
## <a name="windows-7"></a>Windows 7

1. Configurez l’ordinateur local destiné à être utilisé pour définir la stratégie de groupe (GPO).
    
1. Ouvrez le**programmes par défaut de contrôle\Programmes\Programmes par défaut\Définir les programmes par défaut** et définir Internet Explorer par défaut. 
    
2. Ouvrez la Console de gestion des stratégies de groupe (gpmc.msc) et basculez vers modifier toute stratégie existante ou créer un nouveau.
    
1. Accédez à ** \<Ordinateur/Utilisateur\> Configuration\Stratégies\Préférences\Paramètres Windows**.
    
2. Avec le bouton droit cliquez sur **Registre\Nouveauté** et sélectionnez **Assistant Registre**.
    
3. Dans la fenêtre du navigateur de Registre, sélectionnez **Ordinateur Local** sur **Suivant**.
    
4. Accédez à **HKEY_CURRENT_USER\Software\Microsoft\Windows\Shell\Associations\UrlAssociations\https** et sélectionnez la valeur ProgId. Vérifiez que la valeur semblable à celui ci-dessous : 
    
    ![Sélectionner une valeur dans la modification de la chaîne ProgID](media/f6173dcc-b898-4967-8c40-4b0fe411a92b.png)
  
5. Accédez à **HKEY_CURRENT_USER\Software\Microsoft\Windows\Shell\Associations\UrlAssociations\https** et sélectionnez la valeur ProgId. Vérifiez que la valeur semblable à celui ci-dessous : 
    
    ![Sélectionner une valeur dans la modification de la chaîne ProgID pour HTTPS](media/3519e13b-4fe7-4d15-946c-82fd50fc49bb.png)
  
3. Appliquez la stratégie de groupe résultante GPO en les reliant au domaine approprié.
    
