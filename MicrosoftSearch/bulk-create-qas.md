---
title: Créer Q&As
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
description: Ajoutez rapidement des réponses aux questions fréquemment posées à l'aide des outils d'importation dans le portail d'administration de Microsoft Search.
ms.openlocfilehash: 53f1d167948f6b621ad139620553df51b0cb91c2
ms.sourcegitcommit: 61b4b84e581d3df6045851fe6c9c1291853dea06
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/16/2019
ms.locfileid: "30068393"
---
# <a name="bulk-create-qas"></a>Créer Q&As

Téléchargez et utilisez le modèle. csv pour créer ou modifier en bloc Q&As. Il s'agit également d'un moyen simple d'enregistrer des Q&As brouillons qui nécessitent des modifications ou des mises à jour supplémentaires. Si vous devez modifier en bloc des Q&As existants, exportez-les à partir du portail d'administration, effectuez les modifications nécessaires, puis importez-les.
  
1. Dans le coin supérieur droit de la section Q&As, cliquez sur **Importer** .
    
2. Cliquez sur **Télécharger le modèle Q&A (. csv)** .
    
3. Enregistrer et ouvrir le fichier. csv
    
4. Ajouter le contenu et les paramètres Q&A et enregistrer le fichier
    
5. Dans le coin supérieur droit de la section Q&As, cliquez sur **Importer** .
    
6. Dans le volet importer Q&As, cliquez sur **Parcourir** et naviguez jusqu'au fichier. csv que vous souhaitez importer. 
    
7. Cliquez sur **Importer**

# <a name="prevent-import-errors"></a>Empêcher les erreurs d'importation      
Vous obtiendrez une erreur si les données requises sont manquantes ou non valides. En fonction de l'erreur, un fichier journal peut être généré avec davantage d'informations sur les lignes et les colonnes qui doivent être corrigées. Effectuez les modifications nécessaires, puis réessayez d'importer le fichier.

> [!NOTE]
> Tant que toutes les erreurs ne sont pas résolues, vous ne pouvez pas créer ni modifier de Q&As. 

Pour éviter les erreurs, assurez-vous que votre fichier d'importation est correctement mis en forme:
- Inclut la ligne d'en-tête qui était dans le modèle d'importation.
- Inclut toutes les colonnes qui se trouvaient dans le modèle d'importation.
- L'ordre des colonnes est le même que celui du modèle d'importation.
- Ces colonnes peuvent être vides: ID, Last modified et Last modified by
- La colonne État ne peut pas être vide; cette information est requise  
En fonction du champ d'État, Q&As sera enregistré en tant que brouillon, suggéré, programmé, ou il sera automatiquement publié.

En outre, si vous incluez l'ID d'un Q&A existant, il sera remplacé par les informations contenues dans le fichier d'importation.

Pour les organisations avec plusieurs locataires, vous pouvez exporter votre Q&As d'un client et l'importer dans un autre. Toutefois, vous devez supprimer toutes les données de la colonne ID avant d'importer.

Pour en savoir plus sur les champs requis et recommandés, voir [Create Q&As](create-qas.md).

  

