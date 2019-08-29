---
title: Créer en bloc des Q&R
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
ms.assetid: 7bada218-8908-4956-aae3-6ffaeef384ca
ROBOTS: NoIndex
description: Ajoutez rapidement des réponses aux questions fréquemment posées à l’aide des outils d’importation disponibles dans le portail d’administration de Recherche Microsoft
ms.openlocfilehash: c0ec4aaa0ee93e94c8569dc383456018ccc6679d
ms.sourcegitcommit: c2c9e66af1038efd2849d578f846680851f9e5d2
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/27/2019
ms.locfileid: "36639774"
---
# <a name="bulk-create-qas"></a>Créer en bloc des questions et réponses

> [!IMPORTANT]
> Cet article s’applique à la fonctionnalité Recherche Microsoft dans le portail d’administration Bing. Nous déplaçons le portail vers le centre d’administration Microsoft 365. Nous supprimerons ensuite la fonctionnalité Recherche Microsoft dans le portail Bing. Pour commencer, nous vous suggérons d’utiliser le centre d’administration Microsoft 365. [Vue d’ensemble de la fonctionnalité Recherche Microsoft](overview-microsoft-search.md).
    
Téléchargez et utilisez le modèle .csv pour créer ou éditer en bloc des questions et réponses. C’est également un moyen simple d’enregistrer en bloc les brouillons de FAQ qui ont besoin de plus de modifications ou mises à jour. Si vous avez besoin de modifier des Q&R existants en bloc, des les exporter à partir du portail d’administration, apportez les modifications nécessaires, puis importez-les.
  
1. Dans le coin supérieur droit de l’écran Q&R, cliquez sur **Importer**.
    
2. Cliquez sur **télécharger un modèle Q&R (.csv)**
    
3. Enregistrez et ouvrez le fichier .csv.
    
4. Ajoutez le contenu et les paramètres des Q&R, puis enregistrez le fichier.

    Le fichier. csv doit être enregistré au format CSV UTF-8, car d’autres types ou codages de fichiers peuvent occasionner des erreurs d’importation.
    
5. Dans l’angle supérieur droit de la section Q&R, cliquez sur **Importer**.
    
6. Dans le volet Import Q&As (Importer des Q&R), cliquez sur **Parcourir**, puis accédez au fichier .csv à importer. 
    
7. Cliquez sur **Importer**.

# <a name="prevent-import-errors"></a>Éviter les erreurs d’importation      
Si des données requises sont manquantes ou non valides, un message d’erreur s’affiche. Selon l’erreur, un fichier journal peut être généré afin de fournir des informations supplémentaires sur les lignes et les colonnes à corriger. Apportez les modifications nécessaires, puis réessayez d’importer le fichier.

> [!NOTE]
> Vous ne pouvez pas créer ou modifier des Q&R tant que toutes les erreurs ne sont pas résolues. 

Pour éviter les erreurs, assurez-vous que votre fichier d’importation est correctement mis en forme, à savoir :
- Il inclut la ligne d’en-tête qui figurait dans le modèle d’importation.
- Il inclut toutes les colonnes qui figuraient dans le modèle d’importation.
- L’ordre des colonnes est le même que celui du modèle d’importation.
- Les colonnes suivantes peuvent être vides : ID, Dernière modification et Dernière modification par.
- La colonne État ne peut pas être vide. Cette information est obligatoire.  
En fonction du contenu du champ Statut, les Q&R sont enregistrés en tant que Brouillon, Suggéré ou Planifié, ou sont automatiquement publiés.

Par ailleurs, si vous incluez l’ID d’une Q&R existante, celle-ci est remplacée par les informations contenues dans le fichier d’importation.

Si votre organisation compte plusieurs locataires, vous pouvez exporter vos Q&R à partir d’un locataire, puis les importer dans un autre. Toutefois, avant l’importation, vous devez supprimer les données contenues dans la colonne ID.

Pour en savoir plus sur les champs obligatoires et recommandés, voir [Créer des Q&R](create-qas.md).

  

