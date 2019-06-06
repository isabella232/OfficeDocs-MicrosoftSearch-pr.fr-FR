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
ROBOTS: NOINDEX
description: Découvrez comment configurer un navigateur par défaut pour votre entreprise avec Microsoft Search (recherche Microsoft).
ms.openlocfilehash: 08c61bf6dd68f8044f3f79a0b22829a8f7f6b8ef
ms.sourcegitcommit: fe7f3dae4edba97071a4d127e8a27bdf4fa00d81
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/05/2019
ms.locfileid: "34727842"
---
# <a name="set-default-browser"></a>Configurer la configuration par défaut

  
La configuration du navigateur par défaut, le moteur de recherche par défaut et la page d’accueil par défaut aideront vos utilisateurs à découvrir les fonctionnalités de Microsoft Search (recherche Microsoft), à plus encourager l’utilisation et offrir une expérience plus fluide.
  
Pour définir le navigateur par défaut pour votre organisation, suivez les étapes ci-dessous.
  
## <a name="windows-8-and-above"></a>Windows 8 ou version ultérieure

Pour définir Internet Explorer ou Microsoft Edge comme navigateur par défaut, procédez comme suit :
  
### <a name="create-default-associations-file"></a>Créez le fichier d’associations par défaut

1. Ouvrez une console d’administration PowerShell.
    
2.  `New-Item -Path "\\$env:USERDOMAIN\SYSVOL\$env:USERDNSDOMAIN" -Type Directory -Name "Settings"`
    
3.  `$SettingsPath="\\$env:USERDOMAIN\SYSVOL\$env:USERDNSDOMAIN\Settings"`
    
4.  `Start-Process Dism.exe -PassThru "/Online /Export-DefaultAppAssociations:$SettingsPath\AppAssoc.xml"`
    
Ces étapes essaient et créent le fichier d’associations par défaut dans le dossier SYSVOL du contrôleur de domaine.
  
### <a name="add-or-edit-the-default-associations-file"></a>Ajoutez ou modifiez le fichier d’associations par défaut

1. `Notepad "$SettingsPath\AppAssoc.xml"`
    
2. Modifier les entrées suivantes (.htm, .html, http, https) et supprimez les autres entrées si elles ne sont pas utilisées.
    
  - **Microsoft Edge**
    
     `<Association Identifier=".htm" ProgId="AppX4hxtad77fbk3jkkeerkrm0ze94wjf3s9" ApplicationName="Microsoft Edge" />`
  
     `<Association Identifier=".html" ProgId="AppX4hxtad77fbk3jkkeerkrm0ze94wjf3s9" ApplicationName="Microsoft Edge" />`
  
     `<Association Identifier="http" ProgId="AppXq0fevzme2pys62n3e0fbqa7peapykr8v" ApplicationName="Microsoft Edge" />`
    
  - **Internet Explorer**
    
     `<Association Identifier=".htm" ProgId="htmlfile" ApplicationName="Internet Explorer" />`
  
     `<Association Identifier=".html" ProgId="htmlfile" ApplicationName="Internet Explorer" />`
  
     `<Association Identifier="http" ProgId="IE.HTTP" ApplicationName="Internet Explorer" />`
  
     `<Association Identifier="https" ProgId="IE.HTTPS" ApplicationName="Internet Explorer" />`
    
3. Ouvrez la Console de gestion des stratégies de groupe (gpmc.msc) et basculez vers modifier toute stratégie existante ou créer un nouveau.
    
1. Accédez à**Configuration ordinateur\Administration administrative\Composants Windows\Dossier Explorer**
    
2. Double-cliquez sur **définir un fichier de configuration d’associations par défaut**, définissez-le comme programme **Activé**, puis entrez le chemin d’accès à AppAssoc.xml (par exemple %USERDOMAIN%\SYSVOL\%USERDNSDOMAIN%\Settings\ AppAssoc.xml)
    
4. Appliquez la stratégie de groupe résultante GPO en les reliant au domaine approprié.
    
Les utilisateurs pourront modifier le navigateur après avoir défini cette stratégie.
  
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
    
Les utilisateurs pourront modifier le navigateur après avoir défini cette stratégie.