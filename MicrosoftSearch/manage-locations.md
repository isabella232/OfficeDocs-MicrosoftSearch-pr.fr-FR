---
title: Gérer les emplacements
ms.author: dawholl
author: dawholl
manager: kellis
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
ms.assetid: 8ab9aa00-cd74-405f-8410-9a1c3cfacdb9
description: Au fil du temps, il se peut que vous deviez mettre à jour le statut et le contenu de certains emplacements afin qu’ils restent pertinents. 
ms.openlocfilehash: 25fa6fdb8f95c04332e8df16c7589286ecaefdb0
ms.sourcegitcommit: 21361af7c244ffd6ff8689fd0ff0daa359bf4129
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/14/2019
ms.locfileid: "38626782"
---
# <a name="manage-locations"></a>Gérer les emplacements

## <a name="location"></a>Lieu
Les emplacements permettent à vos utilisateurs de trouver des adresses et de localiser les bâtiments de votre organisation en fournissant la localisation précise des bureaux, campus et bâtiments, ainsi que des instructions de navigation. Les administrateurs doivent ajouter tous les emplacements importants de votre organisation. Contrairement aux signets et aux Q&R, l’index n’est pas actualisé immédiatement, et il peut s’écouler plusieurs heures avant que de nouveaux emplacements ou des emplacements modifiés apparaissent dans les résultats de la recherche.

### <a name="add-or-edit-a-single-location"></a>Ajouter ou modifier un seul emplacement
1. Accédez au **Centre d’administration Microsoft 365**.
1. Dans le volet de navigation, accédez à **Paramètres** et sélectionnez **Recherche Microsoft**.
1. Sélectionnez l’onglet **Emplacements**. Par défaut, l’onglet **Signets** est sélectionné sur la page **Recherche Microsoft**.
1. Pour ajouter un nouvel emplacement, sélectionnez **Ajouter nouveau**.
1. Pour modifier un emplacement, sélectionnez-le dans la liste.
1. Lorsque vous ajoutez ou modifiez les informations, l’aperçu est automatiquement mis à jour.
1. Enregistrez vos modifications.

### <a name="bulk-add-or-edit-locations"></a>Ajout ou modification en bloc d’emplacements
Les administrateurs peuvent utiliser les fonctions d’importation ou d’exportation pour ajouter ou modifier des emplacements en bloc. 

Utilisez la fonction d’importation/exportation pour les opérations suivantes :
1. Ajout en bloc d’emplacements - Ajoutez des détails dans le fichier modèle de l’emplacement, puis importez-le. 
1. Modification en bloc d’emplacements - Exportez les emplacements dans un fichier .csv, modifiez les détails des emplacements dans le fichier .csv exporté, puis importez le fichier .csv mis à jour.
1. Sauvegarde d’emplacements - Exportez les emplacements existants dans un fichier .csv.

Pour exporter ou importer des emplacements :
1. Dans le coin supérieur droit de l’onglet **Emplacements**, sélectionnez **Importer**.
Sélectionnez **Exporter** pour télécharger les emplacements existants dans un fichier .csv.
1. Dans le volet de droite, choisissez de procéder à l’importation à l’aide d’un fichier .csv. Téléchargez le fichier modèle pour obtenir la liste des champs et détails obligatoires.
1. Ajoutez ou modifiez les détails de l’emplacement dans le fichier modèle, puis enregistrez-le sur votre ordinateur. 
1. Dans le volet **Importer des emplacements**, sélectionnez **Parcourir** et choisissez le fichier .csv à importer.
1. Sélectionnez **Importer**.

Remarques importantes concernant le fichier modèle :
- Ne modifiez jamais les données dans les champs suivants : *ID*, *Dernière modification* et *Dernière modification par*.
- Si vous incluez l’*ID* d’un signet existant, celui-ci sera remplacé par les informations contenues dans le fichier d’importation.
- Si un signet existant comporte déjà le même titre ou la même URL, il est mis à jour avec les informations contenues dans le fichier d’importation.
- Certains champs du fichier modèle ne sont pas obligatoires, et les champs obligatoires varient en fonction de l’état du signet.
- En fonction du champ *État*, les signets sont enregistrés en tant que signets brouillons, suggérés ou programmés, ou sont automatiquement publiés.
- Pour les partenaires qui gèrent plusieurs organisations, vous pouvez exporter vos signets d’une organisation et les importer dans un autre. Avant l’importation, vous devez toutefois supprimer les données de la colonne *ID*.

**Remarque :** il est impossible d’importer des emplacements si le fichier modèle comporte des erreurs. Pour éviter les erreurs, assurez-vous que votre fichier d’importation est correctement mis en forme et qu’il contient toutes les informations requises. 

Pour plus d’informations sur la prévention des erreurs, consultez [Éviter les erreurs d’importation](manage-bookmarks.md#prevent-import-errors).
