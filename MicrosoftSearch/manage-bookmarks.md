---
title: Gérer des signets
ms.author: dawholl
author: dawholl
manager: kellis
ms.date: 09/08/2018
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
ms.assetid: c0c814d0-f7e4-444e-b18e-09beb45c9322
description: Rechercher les signets qui doivent être mis à jour et comment modifier en bloc les résultats de signet pour Microsoft Search
ms.openlocfilehash: f87176c645e127e20edd9e70a74efe05dd381236
ms.sourcegitcommit: c70dd5eae43abb775acc6fc4522c2e6be4f0bb67
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/17/2019
ms.locfileid: "31901799"
---
# <a name="manage-bookmarks"></a>Gérer des signets

Au fil du temps, vous devrez peut-être mettre à jour l'État et le contenu d'un signet pour le conserver en adéquation. 
  
## <a name="filter-bookmarks"></a>Filtrer les signets

Utilisez l'option de filtre dans le coin supérieur droit de la page de signets pour rechercher des signets par date et qui les a modifiés. Par exemple, définissez le curseur date sur 30 jours et sélectionnez un administrateur ou un éditeur pour afficher la liste des signets qu'il a créés ou modifiés dans ce délai.
  
## <a name="change-bookmark-content-or-settings"></a>Modifier le contenu ou les paramètres d'un signet

1. Accédez au Portail d’administration de Microsoft Search(recherche Microsoft)
    
2. Dans le volet de navigation, cliquez sur**Signets**
    
3. Pour rechercher un signet, Rechercher, filtrer ou cliquer sur l'état d'un signet pour affiner les résultats
    
4. Pour modifier ou mettre à jour un signet, cliquez sur le titre
    
5. Effectuer des modifications ou des mises à jour du contenu ou des paramètres et afficher un aperçu de leur apparence 
    
6. Cliquez sur **Enregistrer**
    
## <a name="bulk-export-and-edit-bookmarks"></a>Exportation et modification en bloc de signets

Ne modifiez jamais les données de ces champs:
  
- ID
    
- Dernière modification
    
- Dernière modification par
    
ID est un identificateur unique pour chaque signet et ne doit jamais être modifié. Les champs dernière modification et dernière modification par ne doivent être utilisés que pour trier et Rechercher des signets.
  
1. Si vous souhaitez exporter un sous-ensemble de vos signets, filtrez-les.
    
2. Dans le coin supérieur droit de la page signets, cliquez sur **Exporter**
    
3. Enregistrer ou ouvrir le fichier. csv
    
4. Modifiez les données dans l'un des champs suivants:
   - Titre
    
   - URL
    
   - Mots clés
    
   - État
    
   - Description
    
   - Mots clés réservés
    
   - Start Date
    
   - End Date
    
   - Pays/Région
    
   - Groupes
    
   - Système&amp;d'exploitation de l'appareil
    
   - Variantes ciblées
    
5. Enregistrer le fichier. csv

    Le fichier. csv doit être enregistré en tant que fichier CSV UTF-8, d'autres types de fichiers ou de codages peuvent entraîner des erreurs d'importation
    
6. Dans le coin supérieur droit de la page signets, cliquez sur **Importer** .
    
7. Dans le volet importer les signets, cliquez sur **Parcourir** et sélectionnez le fichier. csv modifié. 
    
8. Cliquez sur **Importer**