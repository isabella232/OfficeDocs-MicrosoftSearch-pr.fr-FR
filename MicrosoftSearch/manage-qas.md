---
title: Gérer les Q&R
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
ms.assetid: 7e3432e6-5317-4d63-90b0-52da6fddd343
description: Recherchez et actualisez des réponses individuelles, ou servez-vous des outils de Recherche Microsoft disponibles pour les modifier tous à la fois
ms.openlocfilehash: ee239aa73d4e650289f39d33c63c3e2df4f100cc
ms.sourcegitcommit: 3e91a6e70b48a0100adfed1b62ba79f2fd1735d2
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/13/2019
ms.locfileid: "33968466"
---
# <a name="manage-qas"></a>Gérer les Q&R

> [!IMPORTANT]
> Les paramètres de Recherche Microsoft dans Bing sont désormais accessibles dans le Centre d’administration Microsoft 365. Commencez par [assigner des administrateurs de recherche](https://docs.microsoft.com/fr-FR/microsoftsearch/setup-microsoft-search#step-2-assign-search-admin-and-search-editor) dans votre centre d’administration.
    
Au fil du temps, il se peut que vous deviez mettre à jour le statut et le contenu de certaines Q&R afin qu’elles restent pertinentes. 
  
## <a name="filter-qas"></a>Filtrer FAQs

Utiliser l’option de filtre dans le coin supérieur droit sur l’utilisation de FAQ pour rechercher des questions et réponses par date et qui les a modifiées. Par exemple, positionnez le curseur de date sur 30 jours, puis sélectionnez un administrateur ou un éditeur pour afficher la liste des Q&R qu’il a créées ou modifiées au cours de cette période.
  
## <a name="change-qa-content-or-settings"></a>Modifier le contenu ou les paramètres d’une Q&A

1. Accédez au Portail d’administration de Recherche Microsoft
    
2. Dans le volet de navigation, cliquez sur Courrier**Q&As**.
    
3. Pour trouver une FAQ, recherchez, filtrez ou cliquez sur une FAQ pour affiner vos résultats
    
4. Pour modifier ou mettre à jour une FAQ, cliquez sur le titre
    
5. Apportez des modifications ou mises à jour au contenu ou paramètres et voir comment elles s’affichent
    
6. Cliquez sur **Enregistrer**.
    
## <a name="bulk-export-and-edit-qas"></a>Exportation en bloc et modifier des FAQ

Ne jamais modifier les données dans ces champs :
  
- Id
    
- Dernière modification
    
- Dernière modification par
    
ID est un identificateur unique pour chaque Q&R, qui ne doit jamais être modifié. Les champs Dernière modification et Dernière modification par servent uniquement à trier et trouver des Q&R.
  
1. Si vous voulez exporter un sous-ensemble de vos Q&R, filtrez-les.
    
2. Dans le coin supérieur droit de l’écran FAQ, cliquez sur **Exporter**.
    
3. Ouvrir et enregistrer le fichier .csv
    
4. Modifiez les données dans ces champs :
    
   - Question
    
   - URL
      
   - Mots clés
    
   - État
    
   - Description de réponse
    
   - Mots clés réservés
    
   - Date de début
    
   - Date de fin
    
   - Pays/région
    
   - Groupes
    
   - Appareil et système d’exploitation
    
   - Variantes ciblées
    
5. Enregistrez le fichier csv.

    Le fichier. csv doit être enregistré au format CSV UTF-8, car d’autres types ou codages de fichiers peuvent occasionner des erreurs d’importation.
    
6. Dans l’angle supérieur droit de la page Q&R, cliquez sur **Importer**.
    
7. Dans le volet Import Q&R (Importer les Q&R), cliquez sur **Parcourir**, puis sélectionnez le fichier .csv modifié. 
    
8. Cliquez sur **Importer**.
    
Vous recevrez une erreur si les données requises sont manquantes ou non valides. Selon l’erreur, un fichier journal peut être généré afin de fournir des informations supplémentaires sur les lignes et les colonnes à corriger. Apportez les modifications nécessaires, puis réessayez d’importer le fichier.
  
> [!NOTE]
> Vous ne pouvez pas créer ou modifier des Q&R tant que toutes les erreurs ne sont pas résolues. 
  
Les champs obligatoires varient en fonction du statut du Q&R. En fonction du contenu du champ Statut, les Q&R sont enregistrées en tant que Brouillon, Suggéré ou Planifié, ou sont automatiquement publiées. Pour en savoir plus sur les champs obligatoires et recommandés, voir [Créer des Q&R](create-qas.md).

  

