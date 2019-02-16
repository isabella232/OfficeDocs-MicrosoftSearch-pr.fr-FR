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
description: Ajouter des emplacements à la fois à l'aide des outils d'importation pour le portail d'administration de Microsoft Search
ms.openlocfilehash: eb51b93ceaa560e5142ac46d316ba745c614fe34
ms.sourcegitcommit: 61b4b84e581d3df6045851fe6c9c1291853dea06
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/16/2019
ms.locfileid: "30068409"
---
# <a name="bulk-create-locations"></a>Créer en bloc des emplacements

Téléchargez et utilisez le modèle. csv pour créer, modifier et enregistrer en bloc des emplacements. 
  
1. Dans le coin supérieur droit de la section emplacements, cliquez sur **Importer** .
    
2. Cliquez sur **Télécharger les emplacements (. csv)** .
    
3. Enregistrer et ouvrir le fichier. csv
    
4. Ajouter le contenu de l'emplacement et enregistrer le fichier
    
5. Dans le coin supérieur droit de la section emplacements, cliquez sur **Importer** .
    
6. Dans le volet importer des emplacements, cliquez sur **Parcourir** et naviguez jusqu'au fichier. csv que vous souhaitez importer. 
    
7. Cliquez sur **Importer**

Les champs des modèles d'emplacement d'importation et d'exportation sont les mêmes. Vous pouvez exporter, modifier en bloc et importer les modifications, ou commencer avec un modèle vide pour créer des emplacements en bloc. Pour modifier en bloc des emplacements existants, exportez-les à partir du portail d'administration, effectuez les modifications nécessaires, puis importez-les.

# <a name="prevent-import-errors"></a>Empêcher les erreurs d'importation  
Vous obtiendrez une erreur si les données requises sont manquantes ou non valides. En fonction de l'erreur, un fichier journal peut être généré avec davantage d'informations sur les lignes et les colonnes qui doivent être corrigées. Effectuez les modifications nécessaires, puis réessayez d'importer le fichier.
  
> [!NOTE]
> Tant que toutes les erreurs ne sont pas résolues, vous ne pouvez pas créer ni modifier d'emplacements. 

Pour éviter les erreurs, assurez-vous que votre fichier d'importation est correctement mis en forme:
- Inclut la ligne d'en-tête qui était dans le modèle d'importation.
- Inclut toutes les colonnes qui se trouvaient dans le modèle d'importation.
- L'ordre des colonnes est le même que celui du modèle d'importation.
- Ces colonnes peuvent être vides: ID, dernière modification, dernière modification par et lat/long.  
Nous allons essayer de déterminer la table des adresses locales/longue en fonction de l'adresse si ce champ est vide.
- La colonne État ne peut pas être vide; cette information est requise  
En fonction du champ d'État, les emplacements seront enregistrés en tant que brouillon, suggéré, programmé, ou ils seront publiés automatiquement.

En outre, si vous incluez l'ID d'un emplacement existant, il sera remplacé par les informations contenues dans le fichier d'importation.

Pour les organisations avec plusieurs locataires, vous pouvez exporter vos emplacements d'un client et l'importer dans un autre. Toutefois, vous devez supprimer toutes les données de la colonne ID avant d'importer.
  
Pour en savoir plus sur les champs requis et recommandés, consultez [la rubrique ajouter un emplacement](add-a-location.md).

  

