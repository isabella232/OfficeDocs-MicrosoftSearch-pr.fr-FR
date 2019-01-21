---
title: Gérer les Q&As
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
description: Rechercher et mettre à jour les réponses individuellement ou utiliser les outils Microsoft Search disponibles pour les modifier en une seule fois
ms.openlocfilehash: c0f6b42aa1e0ad8c4736d37ec4dcc8cff6025dbc
ms.sourcegitcommit: bf52cc63b75f2e0324a716fe65da47702956b722
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/18/2019
ms.locfileid: "29378659"
---
# <a name="manage-qas"></a>Gérer les Q&As

Au fil du temps, vous devrez peut-être mettre à jour le statut d’un Q&A et le contenu de conserver pertinents.
  
## <a name="filter-qas"></a>Filtre Q&As

Utilisez l’option de filtrage dans le coin supérieur droit de la page Q&As pour trouver des Q&As par date et qui les a modifiés. Par exemple, réglez la date de 30 jours et sélectionnez un administrateur ou un éditeur pour afficher la liste de Q&As ils ont créés ou modifiés en ce moment.
  
## <a name="change-qa-content-or-settings"></a>Modifier les paramètres ou Q&A contenu

1. Accédez au portail d’administration de recherche Microsoft
    
2. Dans le volet de navigation, cliquez sur **Q&As**
    
3. Pour rechercher un Q&A, la recherche, le filtre ou cliquez sur un statut Q&A pour limiter les résultats
    
4. Pour modifier ou mettre à jour un Q&A, cliquez sur le titre
    
5. Apportez les modifications ou les mises à jour au contenu ou les paramètres et aperçu comment ils apparaissent
    
6. Cliquez sur **Enregistrer**.
    
## <a name="bulk-export-and-edit-qas"></a>Exportation en bloc et modifier Q&As

Ne jamais modifier les données dans ces champs :
  
- Id
    
- Dernière modification
    
- Dernière modifiée par
    
ID est un identificateur unique pour chaque Q&A et ne doit jamais être modifié. Les champs de dernière modification et modifié par doivent uniquement être utilisés pour trier et rechercher Q&As.
  
1. Si vous souhaitez exporter un sous-ensemble de vos Q&As, filtrer
    
2. Dans le coin supérieur droit de la page Q&As, cliquez sur **Exporter**
    
3. Enregistrer ou ouvrir le fichier .csv
    
4. Modifier les données dans une de ces champs :
    
   - Question
    
   - URL
      
   - Mots-clés
    
   - State
    
   - Description de la réponse
    
   - Mots clés réservés
    
   - Date de début
    
   - Date de fin
    
   - Pays/Région
    
   - Groupes
    
   - APPAREIL&amp;système d’exploitation
    
   - Variantes ciblés
    
5. Enregistrez le fichier .csv
    
6. Dans le coin supérieur droit de la page Q&As, cliquez sur **Importer**
    
7. Dans le volet Q&As d’importation, cliquez sur **Parcourir** et sélectionnez le fichier .csv modifié 
    
8. Cliquez sur **Importer**
    
Vous obtiendrez une erreur si toutes les données requises sont manquant ou non valide. En fonction de l’erreur, un fichier journal peut être généré avec plus d’informations sur les lignes et colonnes qui doivent être corrigées. Apportez les modifications nécessaires et relancez l’importation du fichier.
  
> [!NOTE]
> Jusqu'à ce que toutes les erreurs sont résolus, vous ne pouvez pas créer ou modifier n’importe quel Q&As. 
  
Pas tous les champs obligatoires et les champs requis varient en fonction de l’état Q&A. Selon le champ d’état, Q&As sera enregistré comme brouillon, suggéré, planifiées, ou ils sont automatiquement publiées. Pour en savoir plus sur les champs obligatoires et recommandées dans [créer Q&As](create-qas.md).

  

