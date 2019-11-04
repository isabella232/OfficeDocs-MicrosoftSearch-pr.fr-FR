---
title: Créer des signets en bloc
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
description: Créer un grand nombre de signets à la fois avec les outils d’importation pour le portail d’administration de Microsoft Search
ms.openlocfilehash: 2983a47a8761a2463b25497911024f9bfd069369
ms.sourcegitcommit: bfcab9d42e93addccd1e3875b41bc9cc1b6986cc
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/04/2019
ms.locfileid: "37948923"
---
# <a name="bulk-create-bookmarks"></a>Créer des signets en bloc

> [!IMPORTANT]
> Cet article s’applique à la fonctionnalité Recherche Microsoft dans le portail d’administration Bing. Nous déplaçons le portail vers le centre d’administration Microsoft 365. Nous supprimerons ensuite la fonctionnalité Recherche Microsoft dans le portail Bing. Pour commencer, nous vous suggérons d’utiliser le centre d’administration Microsoft 365. [Vue d’ensemble de la fonctionnalité Recherche Microsoft](overview-microsoft-search.md).
    
Téléchargez et utilisez le modèle. csv pour créer, modifier et enregistrer des signets en bloc. Pour modifier en bloc des signets existants, exportez-les à partir du portail d’administration, effectuez les modifications nécessaires, puis importez-les.
  
1. Dans le coin supérieur droit de la section signets, cliquez sur **Importer** .
    
2. Cliquez sur **Télécharger le modèle de signets (. csv)** .
    
3. Enregistrez et ouvrez le fichier .csv.
    
4. Ajouter le contenu et les paramètres du signet et enregistrer le fichier

    Le fichier. csv doit être enregistré au format CSV UTF-8, car d’autres types ou codages de fichiers peuvent occasionner des erreurs d’importation.
    
5. Dans le coin supérieur droit de la section signets, cliquez sur **Importer** .
    
6. Dans le volet importer les signets, cliquez sur **Parcourir** et naviguez jusqu’au fichier. csv que vous souhaitez importer. 
    
7. Cliquez sur **Importer**.

## <a name="prevent-import-errors"></a>Éviter les erreurs d’importation      
Si des données requises sont manquantes ou non valides, un message d’erreur s’affiche. Selon l’erreur, un fichier journal peut être généré afin de fournir des informations supplémentaires sur les lignes et les colonnes à corriger. Apportez les modifications nécessaires, puis réessayez d’importer le fichier.

> [!NOTE]
> Tant que toutes les erreurs ne sont pas résolues, vous ne pouvez pas créer ni modifier de signets. 

Pour éviter les erreurs, assurez-vous que votre fichier d’importation est correctement mis en forme, à savoir :
- Il inclut la ligne d’en-tête qui figurait dans le modèle d’importation.
- Il inclut toutes les colonnes qui figuraient dans le modèle d’importation.
- L’ordre des colonnes est le même que celui du modèle d’importation.
- Les colonnes suivantes peuvent être vides : ID, Dernière modification et Dernière modification par.
- La colonne État ne peut pas être vide. Cette information est obligatoire.  
En fonction du champ État, les signets sont enregistrés en tant que signets brouillons, suggérés ou programmés, ou sont automatiquement publiés.

En outre, si vous incluez l’ID d’un signet existant, il sera remplacé par les informations contenues dans le fichier d’importation.

Pour les partenaires qui gèrent plusieurs organisations, vous pouvez exporter vos signets d’une organisation et les importer dans un autre. Toutefois, avant l’importation, vous devez supprimer les données contenues dans la colonne ID.

Pour en savoir plus sur les champs requis et recommandés, consultez la rubrique [création de signets](create-bookmarks.md).
