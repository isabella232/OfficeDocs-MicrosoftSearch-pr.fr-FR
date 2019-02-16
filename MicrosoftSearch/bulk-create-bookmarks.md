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
description: Créer un grand nombre de signets à la fois avec les outils d'importation pour le portail d'administration de Microsoft Search
ms.openlocfilehash: 07694de1f546a1431f371fa24ffc5721ea66337c
ms.sourcegitcommit: 61b4b84e581d3df6045851fe6c9c1291853dea06
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/16/2019
ms.locfileid: "30068401"
---
# <a name="bulk-create-bookmarks"></a>Créer en bloc des signets

Téléchargez et utilisez le modèle. csv pour créer, modifier et enregistrer des signets en bloc. Pour modifier en bloc des signets existants, exportez-les à partir du portail d'administration, effectuez les modifications nécessaires, puis importez-les.
  
1. Dans le coin supérieur droit de la section signets, cliquez sur **Importer** .
    
2. Cliquez sur **Télécharger le modèle de signets (. csv)** .
    
3. Enregistrer et ouvrir le fichier. csv
    
4. Ajouter le contenu et les paramètres du signet et enregistrer le fichier
    
5. Dans le coin supérieur droit de la section signets, cliquez sur **Importer** .
    
6. Dans le volet importer les signets, cliquez sur **Parcourir** et naviguez jusqu'au fichier. csv que vous souhaitez importer. 
    
7. Cliquez sur **Importer**

# <a name="prevent-import-errors"></a>Empêcher les erreurs d'importation      
Vous obtiendrez une erreur si les données requises sont manquantes ou non valides. En fonction de l'erreur, un fichier journal peut être généré avec davantage d'informations sur les lignes et les colonnes qui doivent être corrigées. Effectuez les modifications nécessaires, puis réessayez d'importer le fichier.

> [!NOTE]
> Tant que toutes les erreurs ne sont pas résolues, vous ne pouvez pas créer ni modifier de signets. 

Pour éviter les erreurs, assurez-vous que votre fichier d'importation est correctement mis en forme:
- Inclut la ligne d'en-tête qui était dans le modèle d'importation.
- Inclut toutes les colonnes qui se trouvaient dans le modèle d'importation.
- L'ordre des colonnes est le même que celui du modèle d'importation.
- Ces colonnes peuvent être vides: ID, Last modified et Last modified by
- La colonne État ne peut pas être vide; cette information est requise  
En fonction du champ d'État, les signets seront enregistrés en tant que brouillon, suggéré, programmé ou ils seront publiés automatiquement.

En outre, si vous incluez l'ID d'un signet existant, il sera remplacé par les informations contenues dans le fichier d'importation.

Pour les organisations avec plusieurs locataires, vous pouvez exporter vos signets d'un client et l'importer dans un autre. Toutefois, vous devez supprimer toutes les données de la colonne ID avant d'importer.

Pour en savoir plus sur les champs requis et recommandés, consultez la rubrique [création](create-bookmarks.md)de signets.
