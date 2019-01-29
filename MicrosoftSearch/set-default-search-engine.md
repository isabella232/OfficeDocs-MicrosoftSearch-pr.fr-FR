---
title: Modèle de recherche par défaut
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
ms.assetid: ee40010e-5d7f-4ba8-a3f8-d240dab3af6d
description: Découvrez comment configurer Bing comme moteur de recherche par défaut de votre société à l’aide de Microsoft Search.
ms.openlocfilehash: a0798da94f4433bb754c71b9e0d00e09ba5a543b
ms.sourcegitcommit: 1c038d87efab4840d97b1f367b39e2b9ecdfee4a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/29/2019
ms.locfileid: "29612528"
---
# <a name="set-default-search-engine"></a>Modèle de recherche par défaut

Configurer le navigateur par défaut, le moteur de recherche par défaut et la page d’accueil par défaut vous aidera vos utilisateurs découvrir les fonctionnalités de Microsoft Search, encourager l’utilisation de plus et fournir une meilleure expérience.
  
Pour définir le moteur de recherche par défaut pour votre organisation, procédez comme suit.
  
## <a name="internet-explorer"></a>Internet Explorer

### <a name="internet-explorer-11"></a>Internet Explorer 11

Les utilisateurs seront en mesure de modifier le fournisseur de recherche une fois que cette stratégie est définie.
  
#### <a name="1-configure-the-local-machine-that-will-be-used-to-set-the-gpo"></a>1. Configuration de l’ordinateur local qui sera utilisé pour définir la stratégie de groupe

Collez le texte suivant dans un Registre (\*.reg) fichier.
  
Windows Registry Editor Version 5.00
  
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
  
Double-cliquez sur le fichier créé et suivez les étapes pour importer le fichier. Une importation réussie devrait se traduire par la boîte de dialogue suivante :
  
![Message d’importation réussie de l’Éditeur du Registre](media/ea3686b9-f6d7-481e-9a0d-2c96891bc501.png)
  
#### <a name="2-open-the-group-policy-management-console-gpmcmsc-and-switch-to-editing-an-existing-policy-or-creating-a-new-one"></a>2. Ouvrez la Console de gestion de stratégie de groupe (gpmc.msc) et passer à la modification d’une stratégie existante ou créer un nouveau

1. Accédez à **paramètres Configuration\Policies\Preferences\Windows de l’utilisateur**.
    
2. Avec le bouton droit sur **Registry\New** et sélectionnez **l’Assistant de Registre**. Dans la fenêtre de navigateur dans le Registre, sélectionnez **l’Ordinateur Local** , cliquez sur **suivant**.
    
3. Accédez à **HKEY_CURRENT_USER\SOFTWARE\Microsoft\Internet Explorer\SearchScopes**.
    
4. À partir de cette clé, veillez à sélectionner DefaultScope.
    
    ![Navigateur dans le Registre avec DefaultScope sélectionné](media/ec5a450d-0cba-4e9c-acba-1a09e8e90bad.png)
  
5. Vérifiez toutes les sous-clés qui contient le GUID pour Microsoft Search dans Bing et chaque valeur sous la clé, à l’exception de n’importe quel chemin d’accès à des profils utilisateur. Faites défiler vers le bas pour sélectionner d’autres éléments.
    
    ![Navigateur dans le Registre avec les autres valeurs sélectionnées](media/7eef7690-8bc5-46cf-9cd8-bd134fc77a02.png)
  
6. Cliquez sur Terminer pour terminer cette configuration.
    
#### <a name="3-set-up-user-preferences-to-help-eliminate-a-warning-the-user-may-get-when-defaultscope-search-is-enforced"></a>3. configurer les préférences utilisateur afin d’éliminer un avertissement indiquant que l’utilisateur peut obtenir lors de l’application de recherche DefaultScope

Cet avertissement est par défaut et avertit l’utilisateur d’un programme essaie de modifier leurs paramètres.
  
1. Dans la même stratégie de groupe, cliquez avec le bouton droit sur **Registry\New** et sélectionnez **Assistant dans le Registre**.
    
2. Accédez à **HKEY_CURRENT_USER\SOFTWARE\Microsoft\Internet Explorer\User préférences**.
    
3. Sélectionnez la clé de **Préférence de l’utilisateur** .
    
4. Cliquez sur **Terminer**.
    
5. Cliquez sur l’objet nouvellement créé. Dans le volet de droite, double-cliquez sur l’objet de préférences de l’utilisateur, modifier l' **Action** **Supprimer**et enregistrer.
    
Appliquer la stratégie de groupe qui en découlent à lier au domaine approprié.
  
## <a name="microsoft-edge"></a>Microsoft Edge

### <a name="windows-10-version-1703-or-later"></a>Windows 10, 1703 ou Version ultérieure

Les utilisateurs seront en mesure de modifier le fournisseur de recherche une fois que cette stratégie est définie.
  
Pour les fichiers ADMX le plus récent pour les différentes versions de Windows, voir [comment créer et gérer le magasin Central de modèles d’administration de stratégie de groupe dans Windows](https://support.microsoft.com/en-us/help/3087759/how-to-create-and-manage-the-central-store-for-group-policy-administra).
  
Si le paramètre décrit dans cette section est introuvable à l’intérieur de la console GPMC, téléchargez le ADMX approprié et les copier dans le magasin central. Pour plus d’informations, voir [Stratégie de groupe de modification via des fichiers ADMX](https://docs.microsoft.com/en-us/previous-versions/windows/it-pro/windows-vista/cc748955%28v%3dws.10%29). Magasin central sur le contrôleur est un dossier avec la convention d’affectation de noms suivante :
  
 **%systemroot%\sysvol\\<domain\>\policies\PolicyDefinitions**
  
Chaque domaine qui gère votre contrôleur doit obtenir un dossier distinct. La commande suivante peut être utilisée pour copier le fichier ADMX à partir de l’invite de commandes :
  
 `Copy <path_to_ADMX.ADMX> %systemroot%\sysvol\<domain>\policies\PolicyDefinitions`
  
1. Ouvrez la Console de gestion de stratégie de groupe (gpmc.msc) et passer à la modification d’une stratégie existante ou créer un nouveau.
    
2. Accédez à ** &lt;Configuration ordinateur/utilisateur&gt;\Administrative Templates\Windows Components\Microsoft Edge**.
    
1. Double-cliquez sur **l’ensemble de moteur de recherche par défaut**, défini sur **activé**, puis entrez`https://www.bing.com/sa/osd/bfb.xml`
    
3. Appliquer la stratégie de groupe qui en découlent à lier au domaine approprié.
    
## <a name="google-chrome"></a>Google Chrome

### <a name="windows-xp-sp2-or-later"></a>Windows XP SP2 ou version ultérieure

Les utilisateurs ne pourront pas modifier le fournisseur de recherche une fois que cette stratégie est définie.
  
Chrome est fourni avec son propre ensemble de paramètres de stratégie de groupe qui peut être téléchargé sous la forme d’un fichier ADMX à partir de [Google Chrome entreprise aide](https://support.google.com/chrome/a/answer/187202). Si Windows Vista de systèmes d’exploitation/Server 2008 ou version ultérieure sont utilisés pour gérer les objets de stratégie de groupe pour le domaine, le fichier ADMX fourni dans ce package prend en charge les paramètres de Chrome sur Windows XP SP2 ou version ultérieure.
  
Copiez le fichier de modèle pour un magasin central pour les fichiers ADMX sur le contrôleur de domaine. Pour plus d’informations, voir [Stratégie de groupe de modification via des fichiers ADMX](https://docs.microsoft.com/en-us/previous-versions/windows/it-pro/windows-vista/cc748955%28v%3dws.10%29). Magasin central sur le contrôleur est un dossier avec la convention d’affectation de noms suivante :
  
 **%systemroot%\sysvol\\<domain\>\policies\PolicyDefinitions**
  
Chaque domaine qui gère votre contrôleur doit obtenir un dossier distinct. La commande suivante peut être utilisée pour copier le fichier ADMX à partir de l’invite de commandes :
  
 `Copy <path_to_Chrome.ADMX> %systemroot%\sysvol\<domain>\policies\PolicyDefinitions`
  
1. Ouvrez la Console de gestion de stratégie de groupe (gpmc.msc) et passer à la modification d’une stratégie existante ou créer un nouveau.
    
2. Assurez-vous que les dossiers suivants apparaissent dans la section modèles d’administration de deux Configuration ordinateur/utilisateur : Google Chrome et Google Chrome - paramètres par défaut.
    
  - Les paramètres de la première section sont fixes et les administrateurs locaux ne pourront pas les modifier dans le navigateur.
    
  - Les paramètres de la section de ce dernier de stratégies peuvent être modifiés par les utilisateurs dans les paramètres du navigateur.
    
3. Accédez à ** \<utilisateur de l’ordinateur/\> fournisseur de recherche Chrome\Default Templates\Google de configuration**
    
4. Double-cliquez sur **Activer le fournisseur de recherche par défaut**, puis définissez-la sur **activé**.
    
5. Double-cliquez sur **icône de fournisseur de recherche par défaut**, définissez-la sur **activé**, puis entrez`https://www.bing.com/sa/simg/bb.ico`
    
6. Double-cliquez sur **URL instantanée fournisseur de recherche par défaut**, puis entrez`https://www.bing.com/business/search?q={searchTerms}&amp;form=BFBSPR`
    
7. Double-cliquez sur le **nom de fournisseur de recherche par défaut**, définissez-la sur activé et entrez « Microsoft Search dans Bing »
    
8. Double-cliquez sur **recherche URL du fournisseur de recherche par défaut**, définissez-la sur **activé**, puis entrez`https://www.bing.com/business/search?q={searchTerms}&amp;form=BFBSPR`
    
9. Double-cliquez sur le **fournisseur de recherche par défaut suggérer URL**, définissez-la sur **activé**, puis entrez`https://business.bing.com/api/v2/browser/suggest?q={searchTerms}&amp;form=BFBSPA`
    
10. Appliquer la stratégie de groupe qui en découlent à lier au domaine approprié.
    
Le moteur de recherche par défaut ajoute la fonctionnalité de suggestions de recherche Microsoft Search dans la barre d’adresse de navigateur. Actuellement, il prend en charge les signets uniquement. Les utilisateurs voient les suggestions de deux signet principaux au-dessus de suggestions web publics en tapant dans la barre d’adresses.