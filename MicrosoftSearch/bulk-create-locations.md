---
title: Créer des emplacements en bloc
ms.author: dawholl
author: dawholl
manager: kellis
ms.date: 12/18/2018
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
ms.assetid: 15c9fada-f7a6-4210-aa6b-028b32217830
description: Ajouter de nombreux emplacements à la fois avec les outils pour le portail d’administration de recherche Microsoft d’importation
ms.openlocfilehash: af91dbc4a0efdaabb2bf91672c0e665683d2a6ab
ms.sourcegitcommit: bf52cc63b75f2e0324a716fe65da47702956b722
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/18/2019
ms.locfileid: "29378661"
---
# <a name="bulk-create-locations"></a>Créer des emplacements en bloc

Télécharger et utiliser le modèle .csv en bloc créer, modifier et enregistrer des emplacements. Pour en bloc modifier les emplacements existants, les exporter à partir du portail d’administration, apportez les modifications nécessaires, puis importez-les.
  
1. Dans le coin supérieur droit de la section emplacements, cliquez sur **Importer**
    
2. Cliquez sur **Télécharger le modèle d’emplacements (.csv)**
    
3. Enregistrez et ouvrez le fichier .csv
    
4. Ajouter du contenu de l’emplacement et enregistrez le fichier
    
5. Dans le coin supérieur droit de la section emplacements, cliquez sur **Importer**
    
6. Dans le volet d’emplacements importation, cliquez sur **Parcourir** et accédez au fichier .csv à importer 
    
7. Cliquez sur **Importer**
    
Vous obtiendrez une erreur si toutes les données requises sont manquant ou non valide. En fonction de l’erreur, un fichier journal peut être généré avec plus d’informations sur les lignes et colonnes qui doivent être corrigées. Apportez les modifications nécessaires et relancez l’importation du fichier.
  
> [!NOTE]
> Jusqu'à ce que toutes les erreurs sont résolus, vous ne pouvez pas créer ou modifier tous les emplacements. 
  
Les champs dans les modèles d’importation et d’exportation emplacements sont les mêmes. Vous pouvez exporter, modifier et importer les modifications, ou démarrer avec un modèle vide en bloc créer de nouveaux emplacements.
  
Pas tous les champs obligatoires et les champs requis varient en fonction de l’état de l’emplacement. Basé sur le champ d’état, les emplacements seront enregistrées comme brouillon, suggéré, planifiées, ou ils sont automatiquement publiées. Pour en savoir plus sur les champs obligatoires et recommandées, voir [Gérer les emplacements](manage-locations.md).

  

