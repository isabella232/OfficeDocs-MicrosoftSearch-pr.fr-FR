---
title: Définir le mode de recherche par défaut
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
ROBOTS: NOINDEX
description: Découvrez comment définir Bing comme moteur de recherche par défaut de votre entreprise à l’aide de Microsoft Search (recherche Microsoft).
ms.openlocfilehash: 77a8ea884f4df26fc8f7661fb9a9b8791b2f0f18
ms.sourcegitcommit: be2e837d9b087bffe6ce40d72d7ae58a8fcdf3fe
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/30/2019
ms.locfileid: "34591115"
---
# <a name="set-default-search-engine"></a>Définir le moteur de recherche par défaut

> [!IMPORTANT]
> Cet article s’applique à la fonctionnalité Recherche Microsoft dans le portail d’administration Bing. Nous déplaçons le portail vers le centre d’administration Microsoft 365. Ensuite, nous le supprimerons. Pour commencer, nous vous suggérons d’utiliser le centre d’administration Microsoft 365. [Vue d’ensemble de la fonctionnalité Recherche Microsoft](overview-microsoft-search.md).
    
La configuration du navigateur par défaut, le moteur de recherche par défaut et la page d’accueil par défaut aideront vos utilisateurs à découvrir les fonctionnalités de Microsoft Search (recherche Microsoft), à plus encourager l’utilisation et offrir une expérience plus fluide.
  
Pour définir le navigateur par défaut pour votre organisation, suivez les étapes ci-dessous.
  
## <a name="internet-explorer"></a>Internet Explorer

### <a name="internet-explorer-11"></a>Internet Explorer 11

Les utilisateurs ne pourront pas modifier le navigateur après avoir défini cette stratégie.
  
#### <a name="1-configure-the-local-machine-that-will-be-used-to-set-the-gpo"></a>1.Configurez l’ordinateur local destiné à être utilisé pour définir la stratégie de groupe (GPO)

Collez le texte suivant dans un fichier Bloc-notes(\*.reg).
  
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
  
Double-cliquez sur le fichier créé et suivez les étapes pour importer le fichier. Une importation réussie doit avoir pour résultat la boîte de dialogue suivante :
  
![Message d’importation réussi Éditeur du Registre](media/ea3686b9-f6d7-481e-9a0d-2c96891bc501.png)
  
#### <a name="2-open-the-group-policy-management-console-gpmcmsc-and-switch-to-editing-an-existing-policy-or-creating-a-new-one"></a>2. Ouvrez la Console de gestion des stratégies de groupe (gpmc.msc) et basculez vers modifier toute stratégie existante ou créer un nouveau.

1. Accédez à **Configuration Utilisateur\Stratégies\Préférences\Paramètres Windows**.
    
2. Avec le bouton droit sur **Registre\Nouveau** et sélectionnez **Assistant Registre**. Dans la fenêtre du navigateur de Registre, sélectionnez **ordinateur Local** sur **Suivant**.
    
3. Accédez à **HKEY_CURRENT_USER\SOFTWARE\Microsoft\Internet Explorer\SearchScopes**.
    
4. À partir de cette clé, veillez à sélectionner DefaultScope.
    
    ![Navigateur de Registre avec DefaultScope sélectionné](media/ec5a450d-0cba-4e9c-acba-1a09e8e90bad.png)
  
5. Consultez toutes les sous-clés contenant le GUIDE de Microsoft Search (recherche Microsoft) dans Bing et chaque valeur sous la clé à l’exception d’un chemin d’accès aux profils utilisateur. Faites défiler vers le bas pour sélectionner d’autres éléments.
    
    ![Navigateur de Registre avec des valeurs supplémentaires sélectionnées](media/7eef7690-8bc5-46cf-9cd8-bd134fc77a02.png)
  
6. Cliquez sur Terminer afin de compléter cette configuration.
    
#### <a name="3-set-up-user-preferences-to-help-eliminate-a-warning-the-user-may-get-when-defaultscope-search-is-enforced"></a>3. configurer les Préférences d’utilisateur pour éliminer un avertissement que l’utilisateur peut apparaître quand la recherche DefaultScope est appliquée

Ce message d’avertissement est normal et les utilisateurs d’un programme tente de modifier leurs paramètres d’alertes.
  
1. Dans le même GPO, cliquez sur le bouton droit**Registre\Nouveauté** et sélectionnez**Assistant Registre**.
    
2. Accédez à **HKEY_CURRENT_USER\SOFTWARE\Microsoft\Internet Explorer\Préférences Utilisateur**.
    
3. Sélectionnez la clé**Préférence Utilisateur**.
    
4. Cliquez sur**Terminer**.
    
5. Cliquez sur l’objet nouvellement créé. Dans le volet de droite, double-cliquez sur l’objet de Préférences d’utilisateur, modifiez le **Action** à **Supprimer et Enregistrer**.
    
Appliquez la stratégie de groupe résultante GPO en les reliant au domaine approprié.
  
## <a name="microsoft-edge"></a>Microsoft Edge

### <a name="windows-10-version-1703-or-later"></a>Windows 10, version 1703 ou supérieure.

Les utilisateurs ne pourront pas modifier le navigateur après avoir défini cette stratégie.
  
Concernant les fichiers récents d’ADMX relatifs aux différentes versions de Windows, reportez-vous à l’article [Comment créer et gérer le magasin central des modèles d’administration de stratégie de groupe dans Windows](https://support.microsoft.com/fr-FR/help/3087759/how-to-create-and-manage-the-central-store-for-group-policy-administra).
  
Si les paramètres décrits dans cette section sont introuvables dans le GPMC, téléchargez l’ ADMX approprié et copiez-les dans le magasin central. Pour plus d’informations, voir[Modifier les groupes de stratégie GPOs basés sur le domaine à l’aide des fichiers ADMX](https://docs.microsoft.com/fr-FR/previous-versions/windows/it-pro/windows-vista/cc748955%28v%3dws.10%29). Le magasin central relatif au contrôleur est un dossier avec la convention de dénomination suivante:
  
 **%systemroot%\sysvol\\<domain\>\policies\PolicyDefinitions**
  
Chaque domaine que votre contrôleur gère doit avoir un dossier séparé. La commande suivante peut être utilisée pour copier le fichier ADMX à partir de la commande rapide:
  
 `Copy <path_to_ADMX.ADMX> %systemroot%\sysvol\<domain>\policies\PolicyDefinitions`
  
1. Ouvrez la Console de Gestion des Stratégies de Groupe (gpmc.msc) et basculez vers modifier toute stratégie existante ou créer un nouveau.
    
2. Accédez à**&lt;Ordinateur/ Configuration Utilisateur&gt;\ Modèles administratifs\Composants Windows\Microsoft Edge**.
    
1. Double-cliquez sur **Définir le moteur de recherche par défaut**, définir à**Activé**, puis entrer`https://www.bing.com/sa/osd/bfb.xml`
    
3. Appliquez la stratégie de groupe résultante GPO en les reliant au domaine approprié.
    
## <a name="google-chrome"></a>Google Chrome

### <a name="windows-xp-sp2-or-later"></a>Windows XP SP2 ou version ultérieure

Les utilisateurs ne pourront pas modifier le fournisseur de recherche après avoir défini cette stratégie.
  
Chrome fournit avec son propre ensemble de paramètres de stratégie de groupe qui peut être téléchargé sous la forme d’un fichier ADMX à partir[Aide Google Chrome Enterprise](https://support.google.com/chrome/a/answer/187202). Si les systèmes d’exploitation Windows Vista/Server 2008 ou version ultérieure servent à gérer l’objet de stratégie de groupe pour le domaine, le fichier ADMX fourni dans ce package assure la gestion des paramètres de Chrome sous Windows XP SP2 ou version ultérieure.
  
Copiez le fichier de modèle dans un magasin central de fichiers ADMX sur le contrôleur de domaine. Pour plus d’informations, voir [Modifier les stratégies de groupe GPOs basés sur le domaine à l’aide des fichiers ADMX](https://docs.microsoft.com/fr-FR/previous-versions/windows/it-pro/windows-vista/cc748955%28v%3dws.10%29). Le magasin central sur le contrôleur est un dossier avec la convention de dénomination suivante:
  
 **%systemroot%\sysvol\\<domain\>\policies\PolicyDefinitions**
  
Chaque domaine que votre contrôleur gère doit avoir un dossier séparé. La commande suivante peut être utilisée pour copier le fichier ADMX à partir de la commande rapide:
  
 `Copy <path_to_Chrome.ADMX> %systemroot%\sysvol\<domain>\policies\PolicyDefinitions`
  
1. Ouvrez la Console de gestion des stratégies de groupe (gpmc.msc) et basculez vers modifier toute stratégie existante ou créer un nouveau.
    
2. Assurez-vous que les dossiers suivants apparaissent dans la section Modèles Administratifs à la fois pour l’Utilisateur/la Configuration Ordinateur: Google Chrome et Google Chrome- Paramètres par défaut.
    
  - Les paramètres de la première section sont fixes et l’administrateur local ne pourra pas les modifier.
    
  - Les paramètres de la dernière section de stratégies peuvent être modifiés par les utilisateurs dans les paramètres de navigateur.
    
3. Accédez à**\<Ordinateur/Configuration utilisateur\>\Modèles Administratifs\Google Chrome- Paramétrage fournisseur par défaut**.
    
4. Double-cliquez sur **Activer le fournisseur de recherche par défaut**et définissez-le comme programme **Activé**.
    
5. Double-cliquez sur **icône fournisseur de recherche par défaut**, définissez-le comme programme **Activé**, puis entrez `https://www.bing.com/sa/simg/bb.ico`
    
6. Double-cliquez sur **l’URL instantané de fournisseur de recherche par défaut** puis entrez`https://www.bing.com/business/search?q={searchTerms}&amp;form=BFBSPR`
    
7. Double-cliquez sur **nom du fournisseur de recherche par défaut**, définissez-le comme Activé, puis entrez «Microsoft Search (recherche Microsoft) dans Bing»
    
8. Double-cliquez sur **l’URL fournisseur de recherche par défaut**, définissez-le comme**Activé**, puis entrez `https://www.bing.com/business/search?q={searchTerms}&amp;form=BFBSPR`
    
9. Double-cliquez sur **l’URL fournisseur de recherche par défaut suggéré**, définissez-le comme**Activé**, puis entrez `https://business.bing.com/api/v2/browser/suggest?q={searchTerms}&amp;form=BFBSPA`
    
10. Appliquez la stratégie de groupe résultante GPO en les reliant au domaine approprié.
    
Le paramétrage du moteur de recherche par défaut ajoute la fonctionnalité de suggestions de recherche Microsoft Search (recherche Microsoft) dans la barre d’adresses navigateur. Pour l’instant, il prend en charge uniquement des signets. Les utilisateurs verront les deux premières suggestions des signets au-dessus des suggestions web public en temps réel dans la barre d’adresses.