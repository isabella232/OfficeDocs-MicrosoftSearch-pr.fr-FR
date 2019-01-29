---
title: Navigateur par défaut
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
description: Découvrez comment configurer un navigateur par défaut pour l’entreprise avec Microsoft Search.
ms.openlocfilehash: 160dbbef9981127b74c51f54f86428667ecd4471
ms.sourcegitcommit: 1c038d87efab4840d97b1f367b39e2b9ecdfee4a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/29/2019
ms.locfileid: "29612472"
---
# <a name="set-default-browser"></a>Navigateur par défaut

Configurer le navigateur par défaut, le moteur de recherche par défaut et la page d’accueil par défaut vous aidera vos utilisateurs découvrir les fonctionnalités de Microsoft Search, encourager l’utilisation de plus et fournir une meilleure expérience.
  
Pour définir le navigateur par défaut pour votre organisation, procédez comme suit.
  
## <a name="windows-8-and-above"></a>Windows 8 et versions ultérieures

Pour configurer Internet Explorer ou Microsoft Edge comme navigateur par défaut, procédez comme suit :
  
### <a name="create-default-associations-file"></a>Créer le fichier d’associations par défaut

1. Ouvrez une console d’administration de PowerShell.
    
2.  `New-Item -Path "\\$env:USERDOMAIN\SYSVOL\$env:USERDNSDOMAIN" -Type Directory -Name "Settings"`
    
3.  `$SettingsPath="\\$env:USERDOMAIN\SYSVOL\$env:USERDNSDOMAIN\Settings"`
    
4.  `Start-Process Dism.exe -PassThru "/Online /Export-DefaultAppAssociations:$SettingsPath\AppAssoc.xml"`
    
Ces étapes essaient et créer le fichier d’associations par défaut dans le dossier SYSVOL du contrôleur de domaine.
  
### <a name="add-or-edit-the-default-associations-file"></a>Ajouter ou modifier le fichier d’associations par défaut

1. `Notepad "$SettingsPath\AppAssoc.xml"`
    
2. Modifier les entrées suivantes (.htm, .html, http, https) et supprimez les autres entrées s’ils ne sont pas nécessaires.
    
  - **Microsoft Edge**
    
     `<Association Identifier=".htm" ProgId="AppX4hxtad77fbk3jkkeerkrm0ze94wjf3s9" ApplicationName="Microsoft Edge" />`
  
     `<Association Identifier=".html" ProgId="AppX4hxtad77fbk3jkkeerkrm0ze94wjf3s9" ApplicationName="Microsoft Edge" />`
  
     `<Association Identifier="http" ProgId="AppXq0fevzme2pys62n3e0fbqa7peapykr8v" ApplicationName="Microsoft Edge" />`
    
  - **Internet Explorer**
    
     `<Association Identifier=".htm" ProgId="htmlfile" ApplicationName="Internet Explorer" />`
  
     `<Association Identifier=".html" ProgId="htmlfile" ApplicationName="Internet Explorer" />`
  
     `<Association Identifier="http" ProgId="IE.HTTP" ApplicationName="Internet Explorer" />`
  
     `<Association Identifier="https" ProgId="IE.HTTPS" ApplicationName="Internet Explorer" />`
    
3. Ouvrez la Console de gestion des stratégies de groupe (gpmc.msc) et passer à la modification d’une stratégie existante ou créer un nouveau.
    
1. Accédez à la **configuration d’ordinateur administration\Composants Components\File Explorer**
    
2. Double-cliquez sur **la valeur d’un fichier de configuration d’associations par défaut**, définissez-la sur **activé**, puis entrez le chemin d’accès AppAssoc.xml (par exemple %USERDOMAIN%\SYSVOL\%USERDNSDOMAIN%\Settings\AppAssoc.xml)
    
4. Appliquer la stratégie de groupe qui en découlent à lier au domaine approprié.
    
Les utilisateurs pourront modifier le navigateur une fois que cette stratégie est définie.
  
## <a name="windows-7"></a>Windows 7

1. Configurer l’ordinateur local qui sera utilisé pour définir la stratégie de groupe.
    
1. Ouvrez **Programmes de contrôle Panel\Programs\Default Programs\Set par défaut** et définir Internet Explorer par défaut. 
    
2. Ouvrez la Console de gestion des stratégies de groupe (gpmc.msc) et passer à la modification d’une stratégie existante ou créer un nouveau.
    
1. Accédez à ** \<utilisateur de l’ordinateur/\> Configuration\Policies\Preferences\Windows paramètres**.
    
2. Avec le bouton droit sur **Registry\New** et sélectionnez **l’Assistant de Registre**.
    
3. Dans la fenêtre de navigateur dans le Registre, sélectionnez **l’Ordinateur Local** , cliquez sur **suivant**.
    
4. Accédez à **HKEY_CURRENT_USER\Software\Microsoft\Windows\Shell\Associations\UrlAssociations\https** et sélectionnez la valeur ProgId. Assurez-vous que la valeur ressemble à celui ci-dessous : 
    
    ![Sélectionner une valeur ProgID de modification de la chaîne](media/f6173dcc-b898-4967-8c40-4b0fe411a92b.png)
  
5. Accédez à **HKEY_CURRENT_USER\Software\Microsoft\Windows\Shell\Associations\UrlAssociations\https** et sélectionnez la valeur ProgId. Assurez-vous que la valeur ressemble à celui ci-dessous : 
    
    ![Sélectionnez ProgId pour le protocole HTTPS dans la chaîne de modification](media/3519e13b-4fe7-4d15-946c-82fd50fc49bb.png)
  
3. Appliquer la stratégie de groupe qui en découlent à lier au domaine approprié.
    
Les utilisateurs pourront modifier le navigateur une fois que cette stratégie est définie.