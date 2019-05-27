---
title: Gérer les emplacements
ms.author: dawholl
author: dawholl
manager: kellis
ms.date: 11/08/2018
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
ms.assetid: 8ab9aa00-cd74-405f-8410-9a1c3cfacdb9
description: Au fil du temps, il se peut que vous deviez mettre à jour le statut et le contenu de certains emplacements afin qu’ils restent pertinents. 
ms.openlocfilehash: 0e23cf3d3d3d05fe86cdc3e09ce808e54242d670
ms.sourcegitcommit: 3e91a6e70b48a0100adfed1b62ba79f2fd1735d2
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/13/2019
ms.locfileid: "33968426"
---
# <a name="manage-locations"></a>Gérer les emplacements

> [!IMPORTANT]
> Les paramètres de Recherche Microsoft dans Bing sont désormais accessibles dans le Centre d’administration Microsoft 365. Commencez par [assigner des administrateurs de recherche](https://docs.microsoft.com/fr-FR/microsoftsearch/setup-microsoft-search#step-2-assign-search-admin-and-search-editor) dans votre centre d’administration.
    
Au fil du temps, il se peut que vous deviez mettre à jour le statut et le contenu de certains emplacements afin qu’ils restent pertinents.  
  
## <a name="filter-locations"></a>Filtrer les emplacements

L’option Filtrer dans l’angle supérieur droit de la page Emplacements permet de rechercher des emplacements sur la base de leur date afin de voir qui les a modifiés. Par exemple, positionnez le curseur de date sur 30 jours, puis sélectionnez un administrateur ou un éditeur pour afficher la liste des emplacements qu’il a créés ou modifiés au cours de cette période.
  
## <a name="change-location-content"></a>Modifier le contenu d’un emplacement

1. Accédez au portail d’administration de Recherche Microsoft.
    
2. Dans le volet de navigation, cliquez sur **Emplacements**.
    
3. Pour trouver un emplacement, effectuez une recherche, filtrez ou cliquez sur un statut d’emplacement pour limiter les résultats.
    
4. Pour modifier ou mettre à jour un emplacement, cliquez sur son nom.
    
5. Apportez des modifications ou mises à jour au contenu afin de voir comment elles s’affichent. 
    
6. Cliquez sur **Enregistrer**.
    
## <a name="bulk-export-and-edit-locations"></a>Exporter et modifier en bloc des emplacements

Ne modifiez jamais les données contenues dans les champs suivants :
  
- Id
    
- Dernière modification
    
- Dernière modification par
    
ID est un identificateur unique pour chaque emplacement, qui ne doit jamais être modifié. Les champs Dernière modification et Dernière modification par servent uniquement à trier et trouver des signets.
  
1. Si vous voulez exporter un sous-ensemble de vos emplacements, filtrez-les.
    
2. Dans l’angle supérieur droit de la page Emplacements, cliquez sur **Exporter**.
    
3. Enregistrez ou ouvrez le fichier .csv.
    
4. Si nécessaire, modifiez les données des champs suivants :
    
   - Nom
    
   - Ligne d’adresse 1
    
   - Ligne d’adresse 2
    
   - Ville
    
   - État de l’adresse
    
   - Code postal
    
   - Pays
    
   - Adresse complète
    
   - Latitude
    
   - Longitude
    
   - Mots clés
    
   - Mots clés réservés
    
   - État
    
5. Enregistrez le fichier csv.

    Le fichier. csv doit être enregistré au format CSV UTF-8, car d’autres types ou codages de fichiers peuvent occasionner des erreurs d’importation.
    
6. Dans l’angle supérieur droit de la page Emplacements, cliquez sur **Importer**.
    
7. Dans le volet Import locations (Importer les emplacements), cliquez sur **Parcourir**, puis sélectionnez le fichier .csv modifié. 
    
8. Cliquez sur **Importer**.

  

