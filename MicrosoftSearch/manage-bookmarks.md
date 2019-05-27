---
title: Gérer les signets
ms.author: dawholl
author: dawholl
manager: kellis
ms.date: 09/08/2018
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
ms.assetid: c0c814d0-f7e4-444e-b18e-09beb45c9322
description: Recherchez les signets qui nécessitent une mise à jour et des façons de modifier en bloc les résultats de signet pour la fonctionnalité Recherche Microsoft
ms.openlocfilehash: d5cebbfd5779bc8a6aa25cdbcdedb6e9b18f242e
ms.sourcegitcommit: 3e91a6e70b48a0100adfed1b62ba79f2fd1735d2
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/13/2019
ms.locfileid: "33968482"
---
# <a name="manage-bookmarks"></a>Gérer les signets

> [!IMPORTANT]
> Les paramètres de Recherche Microsoft dans Bing sont désormais accessibles dans le Centre d’administration Microsoft 365. Commencez par [assigner des administrateurs de recherche](https://docs.microsoft.com/fr-FR/microsoftsearch/setup-microsoft-search#step-2-assign-search-admin-and-search-editor) dans votre centre d’administration.
    
Au fil du temps, il se peut que vous deviez mettre à jour le statut et le contenu de certains signets afin qu’ils restent pertinents.  
  
## <a name="filter-bookmarks"></a>Filtrer les signets

Utiliser l’option de filtre dans le coin supérieur droit sur l’utilisation des signets pour rechercher des signets par date et qui les a modifiés. Par exemple, positionnez le curseur de date sur 30 jours, puis sélectionnez un administrateur ou un éditeur pour afficher la liste des signets qu’il a créés ou modifiés au cours de cette période.
  
## <a name="change-bookmark-content-or-settings"></a>Modifier le contenu ou les paramètres d’un signet

1. Accédez au Portail d’administration de Recherche Microsoft
    
2. Dans le volet de navigation, cliquez sur**Signets**
    
3. Pour trouver un signet, effectuez une recherche, filtrez ou cliquez sur un statut de signet pour limiter les résultats.
    
4. Pour modifier ou mettre à jour un signet, cliquez sur son titre.
    
5. Apportez des modifications ou mises à jour au contenu ou paramètres et voir comment ils s’affichent 
    
6. Cliquez sur **Enregistrer**.
    
## <a name="bulk-export-and-edit-bookmarks"></a>Exporter en bloc et modifier des signets

Ne jamais modifier les données dans ces champs :
  
- Id
    
- Dernière modification
    
- Dernière modification par
    
ID est un identificateur unique pour chaque signet et ne doit jamais être modifié. Utilisez les options dernière modification et dernier modification par uniquement pour trier et trouver des signets.
  
1. Si vous voulez exporter un sous-ensemble de vos signets, filtrez-les
    
2. Dans le coin supérieur droit de l’écran signets, cliquez sur **Exporter**.
    
3. Ouvrir et enregistrer le fichier .csv
    
4. Modifiez les données dans ces champs :
   - Titre
    
   - URL
    
   - Mots clés
    
   - État
    
   - Description
    
   - Mots clés réservés
    
   - Date de début
    
   - Date de fin
    
   - Pays/région
    
   - Groupes
    
   - Appareil et système d’exploitation
    
   - Variantes ciblées
    
5. Enregistrez le fichier csv.

    Le fichier. csv doit être enregistré au format CSV UTF-8, car d’autres types ou codages de fichiers peuvent occasionner des erreurs d’importation.
    
6. Dans l’angle supérieur droit de la page Signets, cliquez sur **Importer**.
    
7. Dans le volet Import bookmarks (Importer les signets), cliquez sur **Parcourir**, puis sélectionnez le fichier .csv modifié. 
    
8. Cliquez sur **Importer**.