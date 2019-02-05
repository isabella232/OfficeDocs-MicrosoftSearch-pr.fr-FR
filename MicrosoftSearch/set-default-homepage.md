---
title: Page d’accueil par défaut
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
ms.assetid: c020bd72-9906-4dfd-bc77-57287f5927ce
description: Découvrez comment configurer un navigateur par défaut pour votre entreprise avec Microsoft Search (recherche Microsoft).
ms.openlocfilehash: db0611ebd7f4a8344664825bbb42025f3bb36486
ms.sourcegitcommit: 1c038d87efab4840d97b1f367b39e2b9ecdfee4a
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/29/2019
ms.locfileid: "29612488"
---
# <a name="set-default-homepage"></a>Page d’accueil par défaut

La configuration du navigateur par défaut, le moteur de recherche par défaut et la page d’accueil par défaut qui aideront vos utilisateurs à découvrir les fonctionnalités de Microsoft Search (recherche Microsoft), à plus encourager l’utilisation et offrir une expérience plus fluide.
  
Pour définir le navigateur par défaut pour votre organisation, suivez les étapes ci-dessous.
  
## <a name="internet-explorer"></a>Internet Explorer

### <a name="internet-explorer-50-or-later"></a>Internet Explorer 5.0 ou version ultérieure

1. Ouvrez la Console de gestion des stratégies de groupe (gpmc.msc) et basculez vers modifier toute stratégie existante ou créer un nouveau.
    
2. Accédez à **Configuration utilisateur\Préférences\Paramètres de Panneau de contrôle\Paramètres Internet**.
    
3. Avec le bouton droit, cliquez sur**Paramètres Internet** et sélectionnez **Internet Explorer 10**.
    
    > [!NOTE]
    > Vous devez sélectionner l’option d’Internet Explorer 10 pour appliquer les paramètres Internet Explorer 11 comme les mêmes paramètres s’appliquent à Internet Explorer 11. 
  
4. Les paramètres qui sont soulignés en rouge ne sont pas configurés sur la machine cible, tandis que les paramètres soulignés en vert sont configurés à l’ordinateur cible. Pour modifier le soulignement, utilisez les touches de fonction suivantes :
    
    F5-Activer tous les paramètres sous l’onglet actif
    
    F6-Activer les paramètres actuellement sélectionnés
    
    F7-Désactiver les paramètres actuellement sélectionnés
    
    F8-Désactiver tous les paramètres sous l’onglet actif
    
5. Appuyez sur**F8** pour désactiver tous les paramètres avant de configurer quoi que ce soit. L’écran doit ressembler à ceci : 
    
    ![Boîte de dialogue Propriétés Internet Explorer 10](media/2fd55755-5007-4e33-a795-c42ce2fcef4a.jpg)
  
6. Appuyez sur**F6** sur les paramètres de la page d’accueil et entrez `https://www.bing.com/business?form=BFBSPR`
    
7. Appliquez la stratégie de groupe résultante GPO en les reliant au domaine approprié.
    
> [!NOTE]
> Les utilisateurs peuvent toujours modifier la page d’accueil après avoir défini cette stratégie. 
  
## <a name="microsoft-edge"></a>Microsoft Edge

### <a name="windows-10-version-1511-or-later"></a>Windows 10, version 1511 ou supérieure.

1. Ouvrez la Console de gestion des stratégies de groupe (gpmc.msc) et basculez vers modifier toute stratégie existante ou créer un nouveau.
    
2. Accédez à **Modèles administratifs\Composants Windows\Microsoft Edge**
    
1. Double-cliquez sur **Configurer les pages de démarrage**, définissez-le comme programme **Activé**, puis entrez `https://www.bing.com/business`
    
3. Appliquez la stratégie de groupe résultante GPO en les reliant au domaine approprié.
    
> [!CAUTION]
> Les utilisateurs ne pourront pas modifier le navigateur après avoir défini cette stratégie. 
  
## <a name="google-chrome"></a>Google Chrome

### <a name="windows-xp-sp2-or-later"></a>Windows XP (SP2) ou version ultérieure

L’article du Support de Windows sur la gestion des fichiers ADMX et les derniers fichiers ADMX pour différentes versions de Windows est accessible [sur le Support Microsoft](https://support.microsoft.com/fr-FR/help/3087759/how-to-create-and-manage-the-central-store-for-group-policy-administra).

Vous devez également utiliser le fichier de stratégie Google le plus récent, que vous trouverez sur[Aide Google Chrome Enterprise](https://support.google.com/chrome/a/answer/187202).
  
Si les paramètres décrits dans cette section sont introuvables dans le GPMC, téléchargez l’ ADMX approprié et les copier dans le [magasin central](https://docs.microsoft.com/fr-FR/previous-versions/windows/it-pro/windows-vista/cc748955%28v%3dws.10%29). Le magasin central relatif au contrôleur est un dossier avec la convention de dénomination suivante :
  
 **%systemroot%\sysvol\\<domain\>\policies\PolicyDefinitions**
  
Chaque domaine que votre contrôleur gère doit avoir un dossier séparé. La commande suivante peut être utilisée pour copier le fichier ADMX à partir de la commande rapide:
  
 `Copy <path_to_ADMX.ADMX> %systemroot%\sysvol\<domain>\policies\PolicyDefinitions`
  
1. Ouvrez la Console de gestion des stratégies de groupe (gpmc.msc) et basculez vers modifier toute stratégie existante ou créer un nouveau.
    
2. Assurez-vous que les dossiers suivants apparaissent dans la section**Modèles Administratifs** des deux*Utilisateur/Configuration Ordinateur*:Google Chrome et Google Chrome- Paramètres par défaut (les utilisateurs peuvent y déroger).
    
   - Les paramètres de la première section sont fixes et l’administrateur local ne pourra pas les modifier.
    
   - Les paramètres de la dernière section de stratégies peuvent être modifiés par les utilisateurs dans leurs paramètres de navigateur. Vous devez décider si les utilisateurs peuvent remplacer votre paramètre par défaut. Dans les étapes suivantes, modifiez dans le paramètre dans le dossier qui correspond à la stratégie de l’organisation et aux besoins. Les étapes ci-dessous utilisent Google Chrome- les paramètres par défaut comme paramètre par défaut.
    
3. Accédez à**&lt;Ordinateur/Configuration utilisateur&gt;\Modèles Administratifs\Google Chrome- Paramétrage par défaut\Page d’Accueil**.
    
4. Double-cliquez sur la**Page du Nouvel Onglet utilisation en tant que Page d’Accueil**et définissez-le comme**Activé**.
    
5. Accédez à**&lt;Ordinateur/Configuration Utilisateur&gt;\Modèles Administratifs\Google Chrome-Paramétrage par défaut\Page du Nouvel Onglet**.
    
6. Double-cliquez sur **Configurer le Nouvel URL de la Pages d’Onglet**, définissez-la comme**Activé**, puis entrez `https://www.bing.com/business?form=BFBSPR`
    
7. Appliquez la stratégie de groupe résultante GPO en les reliant au domaine approprié.
    
Les utilisateurs pourront modifier le navigateur après avoir défini cette stratégie.