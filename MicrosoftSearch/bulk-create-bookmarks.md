---
title: Créer en bloc des signets
ms.author: dawholl
author: dawholl
manager: kellis
ms.date: 09/11/2018
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
ms.assetid: def300e7-103c-4e92-a062-28ffa27561d7
ROBOTS: NoIndex
description: Créez un grand nombre de signets à la fois grâce aux outils d’importation pour le portail d’administration de la fonctionnalité Recherche Microsoft
ms.openlocfilehash: 1b3922215534391c65547a4ece22310261626036
ms.sourcegitcommit: be2e837d9b087bffe6ce40d72d7ae58a8fcdf3fe
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/30/2019
ms.locfileid: "34591421"
---
# <a name="bulk-create-bookmarks"></a>Créer en bloc des signets

> [!IMPORTANT]
> Cet article s’applique à la fonctionnalité Recherche Microsoft dans le portail d’administration Bing. Nous déplaçons le portail vers le centre d’administration Microsoft 365. Ensuite, nous le supprimerons. Pour commencer, nous vous suggérons d’utiliser le centre d’administration Microsoft 365. [Vue d’ensemble de la fonctionnalité Recherche Microsoft](overview-microsoft-search.md).
    
Téléchargez et utilisez le modèle .csv pour créer, éditer et enregistrer en bloc des signets. Pour modifier des signets en bloc, exportez-les à partir du portail d’administration, apportez les modifications nécessaires, puis importez-les.
  
1. Dans le coin supérieur droit de la section Signets, cliquez sur **Importer**.
    
2. Cliquez sur **Télécharger un modèle de signet (.csv)**.
    
3. Enregistrez et ouvrez le fichier .csv.
    
4. Ajoutez le contenu et les paramètres du signet, puis enregistrez le fichier.

    Le fichier. csv doit être enregistré au format CSV UTF-8, car d’autres types ou codages de fichiers peuvent occasionner des erreurs d’importation.
    
5. Dans l’angle supérieur droit de la section Signets, cliquez sur **Importer**.
    
6. Dans le volet Import bookmarks (Importer des signets), cliquez sur **Parcourir** et accédez au fichier .csv à importer. 
    
7. Cliquez sur **Importer**.

# <a name="prevent-import-errors"></a>Éviter les erreurs d’importation      
Si des données requises sont manquantes ou non valides, un message d’erreur s’affiche. Selon l’erreur, un fichier journal peut être généré afin de fournir des informations supplémentaires sur les lignes et les colonnes à corriger. Apportez les modifications nécessaires, puis réessayez d’importer le fichier.

> [!NOTE]
> Vous ne pouvez pas créer ou modifier des signets tant que toutes les erreurs ne sont pas résolues. 

Pour éviter les erreurs, assurez-vous que votre fichier d’importation est correctement mis en forme, à savoir :
- Il inclut la ligne d’en-tête qui figurait dans le modèle d’importation.
- Il inclut toutes les colonnes qui figuraient dans le modèle d’importation.
- L’ordre des colonnes est le même que celui du modèle d’importation.
- Les colonnes suivantes peuvent être vides : ID, Dernière modification et Dernière modification par.
- La colonne État ne peut pas être vide. Cette information est obligatoire.  
En fonction du contenu du champ Statut, les signets sont enregistrés en tant que Brouillon, Suggéré ou Planifié, ou sont automatiquement publiés.

Par ailleurs, si vous incluez l’ID d’un signet existant, celui-ci est remplacé par les informations contenues dans le fichier d’importation.

Si votre organisation compte plusieurs locataires, vous pouvez exporter vos signets à partir d’un locataire, puis les importer dans un autre. Toutefois, avant l’importation, vous devez supprimer les données contenues dans la colonne ID.

Pour en savoir plus sur les champs obligatoires et recommandés, voir [Créer des signets](create-bookmarks.md).
