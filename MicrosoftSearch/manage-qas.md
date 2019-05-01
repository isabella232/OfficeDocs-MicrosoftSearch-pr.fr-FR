---
title: Gérer des Q&R
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
description: Rechercher et mettre à jour les réponses individuellement ou utiliser les outils de recherche Microsoft disponibles pour les modifier en une seule fois
ms.openlocfilehash: 47882deeb95133cfc19f4eec6417fc20fb7203de
ms.sourcegitcommit: a5fd9d4f46bbb7c539630735ac16e0c786939e5d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/01/2019
ms.locfileid: "33508816"
---
# <a name="manage-qas"></a>Gérer des Q&R

Au fil du temps, vous devrez peut-être mettre à jour l'État et le contenu d'un Q&A's pour le conserver en adéquation.
  
## <a name="filter-qas"></a>Filtre Q&As

Utilisez l'option de filtrage dans le coin supérieur droit de la page Q&As pour rechercher Q&As par date et qui les a modifiés. Par exemple, définissez le curseur date sur 30 jours et sélectionnez un administrateur ou un éditeur pour afficher la liste des Q&As qu'ils ont créés ou modifiés à ce moment-là.
  
## <a name="change-qa-content-or-settings"></a>Modifier le contenu ou les paramètres Q&A

1. Accédez au portail d’administration de Microsoft Search (recherche Microsoft).
    
2. Dans le volet de navigation, cliquez sur Courrier**Q&As**.
    
3. Pour rechercher un Q&A, recherchez, filtrez ou cliquez sur un État Q&A pour affiner vos résultats
    
4. Pour modifier ou mettre à jour un Q&A, cliquez sur le titre.
    
5. Effectuer des modifications ou des mises à jour du contenu ou des paramètres et afficher un aperçu de leur apparence
    
6. Cliquez sur **Enregistrer**
    
## <a name="bulk-export-and-edit-qas"></a>Exportation et modification en bloc Q&As

Ne modifiez jamais les données de ces champs:
  
- ID
    
- Dernière modification
    
- Dernière modification par
    
ID est un identificateur unique pour chaque Q&A et ne doit jamais être modifié. Les champs Last modified et Last modified by ne doivent être utilisés que pour trier et trouver Q&As.
  
1. Si vous souhaitez exporter un sous-ensemble de votre Q&As, filtrez-les.
    
2. Dans le coin supérieur droit de la page Q&As, cliquez sur **Exporter** .
    
3. Enregistrer ou ouvrir le fichier. csv
    
4. Modifiez les données dans l'un des champs suivants:
    
   - Question
    
   - URL
      
   - Mots clés
    
   - État
    
   - Description de la réponse
    
   - Mots clés réservés
    
   - Start Date
    
   - End Date
    
   - Pays/Région
    
   - Groupes
    
   - Système&amp;d'exploitation de l'appareil
    
   - Variantes ciblées
    
5. Enregistrer le fichier. csv

    Le fichier. csv doit être enregistré en tant que fichier CSV UTF-8, d'autres types de fichiers ou de codages peuvent entraîner des erreurs d'importation
    
6. Dans le coin supérieur droit de la page Q&As, cliquez sur **Importer** .
    
7. Dans le volet importer Q&As, cliquez sur **Parcourir** et sélectionnez le fichier. csv modifié. 
    
8. Cliquez sur **Importer**
    
Vous obtiendrez une erreur si les données requises sont manquantes ou non valides. En fonction de l'erreur, un fichier journal peut être généré avec davantage d'informations sur les lignes et les colonnes qui doivent être corrigées. Effectuez les modifications nécessaires, puis réessayez d'importer le fichier.
  
> [!NOTE]
> Tant que toutes les erreurs ne sont pas résolues, vous ne pouvez pas créer ni modifier de Q&As. 
  
Tous les champs ne sont pas obligatoires et les champs obligatoires varient en fonction de l'État Q&A. En fonction du champ d'État, Q&As sera enregistré en tant que brouillon, suggéré, programmé, ou il sera automatiquement publié. Pour en savoir plus sur les champs requis et recommandés, consultez la rubrique [Create Q&As](create-qas.md).

  

