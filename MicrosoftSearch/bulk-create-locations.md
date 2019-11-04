---
title: Créer en bloc des emplacements
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
ROBOTS: NoIndex
description: Ajouter des emplacements à la fois à l’aide des outils d’importation pour le portail d’administration de Microsoft Search
ms.openlocfilehash: e01c3774439a931dc81f850d8cbee76cc6128a53
ms.sourcegitcommit: bfcab9d42e93addccd1e3875b41bc9cc1b6986cc
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/04/2019
ms.locfileid: "37948969"
---
# <a name="bulk-create-locations"></a>Créer en bloc des emplacements

> [!IMPORTANT]
> Cet article s’applique à la fonctionnalité Recherche Microsoft dans le portail d’administration Bing. Nous déplaçons le portail vers le centre d’administration Microsoft 365. Nous supprimerons ensuite la fonctionnalité Recherche Microsoft dans le portail Bing. Pour commencer, nous vous suggérons d’utiliser le centre d’administration Microsoft 365. [Vue d’ensemble de la fonctionnalité Recherche Microsoft](overview-microsoft-search.md).
    
Téléchargez et utilisez le modèle. csv pour créer, modifier et enregistrer en bloc des emplacements. 
  
1. Dans le coin supérieur droit de la section emplacements, cliquez sur **Importer** .
    
2. Cliquez sur **Télécharger les emplacements (. csv)** .
    
3. Enregistrez et ouvrez le fichier .csv.
    
4. Ajouter le contenu de l’emplacement et enregistrer le fichier

    Le fichier. csv doit être enregistré au format CSV UTF-8, car d’autres types ou codages de fichiers peuvent occasionner des erreurs d’importation.
    
5. Dans le coin supérieur droit de la section emplacements, cliquez sur **Importer** .
    
6. Dans le volet importer des emplacements, cliquez sur **Parcourir** et naviguez jusqu’au fichier. csv que vous souhaitez importer. 
    
7. Cliquez sur **Importer**.

Les champs des modèles d’emplacement d’importation et d’exportation sont les mêmes. Vous pouvez exporter, modifier en bloc et importer les modifications, ou commencer avec un modèle vide pour créer des emplacements en bloc. Pour modifier en bloc des emplacements existants, exportez-les à partir du portail d’administration, effectuez les modifications nécessaires, puis importez-les.

## <a name="prevent-import-errors"></a>Éviter les erreurs d’importation  
Si des données requises sont manquantes ou non valides, un message d’erreur s’affiche. Selon l’erreur, un fichier journal peut être généré afin de fournir des informations supplémentaires sur les lignes et les colonnes à corriger. Apportez les modifications nécessaires, puis réessayez d’importer le fichier.
  
> [!NOTE]
> Tant que toutes les erreurs ne sont pas résolues, vous ne pouvez pas créer ni modifier d’emplacements. 

Pour éviter les erreurs, assurez-vous que votre fichier d’importation est correctement mis en forme, à savoir :
- Il inclut la ligne d’en-tête qui figurait dans le modèle d’importation.
- Il inclut toutes les colonnes qui figuraient dans le modèle d’importation.
- L’ordre des colonnes est le même que celui du modèle d’importation.
- Ces colonnes peuvent être vides : ID, dernière modification, dernière modification par et lat/long.  
Nous allons essayer de déterminer la table des adresses locales/longue en fonction de l’adresse si ce champ est vide.
- La colonne État ne peut pas être vide. Cette information est obligatoire.  
En fonction du champ d’État, les emplacements seront enregistrés en tant que brouillon, suggéré, programmé, ou ils seront publiés automatiquement.

En outre, si vous incluez l’ID d’un emplacement existant, il sera remplacé par les informations contenues dans le fichier d’importation.

Pour les partenaires qui gèrent plusieurs organisations, vous pouvez exporter vos emplacements d’une organisation et les importer dans un autre. Toutefois, avant l’importation, vous devez supprimer les données contenues dans la colonne ID.
  
Pour en savoir plus sur les champs requis et recommandés, consultez [la rubrique ajouter un emplacement](add-a-location.md).

  

