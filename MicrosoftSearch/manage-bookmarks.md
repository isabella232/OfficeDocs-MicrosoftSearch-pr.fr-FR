---
title: Gérer les signets
ms.author: anfowler
author: adefowler
manager: mnirkhe
ms.date: 05/30/2019
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
ms.assetid: c0c814d0-f7e4-444e-b18e-09beb45c9322
description: Créez et mettez à jour des signets et des façons de modifier en bloc les résultats de signet pour la fonctionnalité Recherche Microsoft
ms.openlocfilehash: fb1be0bc137891a54e370fef1e4b5628963c5ad9
ms.sourcegitcommit: be2e837d9b087bffe6ce40d72d7ae58a8fcdf3fe
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/30/2019
ms.locfileid: "34591619"
---
# <a name="manage-bookmarks"></a>Gérer les signets

Vous pouvez créer un signet en quelques étapes. Chaque signet comprend un titre, une URL et un ensemble de mots clés qui le déclenchent. Un signet peut comprendre plusieurs mots clés, et plusieurs signets peuvent partager le même mot clé, mais un mot clé réservé ne peut pas être partagé. Lorsqu’un signet est créé ou modifié, l’index de recherche est aussitôt actualisé et le signet est immédiatement accessible aux utilisateurs.

Si votre organisation a configuré des résultats promus dans SharePoint, vous pouvez importer ceux-ci dans **Recherche Microsoft** et mettre le contenu importé à la disposition de vos utilisateurs. Cette méthode simple permet de renseigner rapidement les résultats de recherche dès que vous avez configuré la fonctionnalité **Recherche Microsoft**, et d’améliorer son efficacité pour vos utilisateurs. Nous vous recommandons d’utiliser les résultats promus de SharePoint comme référence pour apprendre à nommer et créer des résultats de recherche pertinents. 

## <a name="add-or-edit-a-single-bookmark"></a>Ajouter ou modifier un seul signet
1. Accédez au **Centre d’administration Microsoft 365**.
1. Dans le volet de navigation, accédez à **Paramètres**, puis sélectionnez ****Recherche Microsoft****.
Par défaut, l’onglet **Signets** est sélectionné.
1. Pour ajouter un signet, sélectionnez **Ajouter nouveau**. Pour modifier un signet, sélectionnez-le dans la liste. 
1. Lorsque vous ajoutez ou modifiez les informations, l’aperçu est automatiquement mis à jour.
1. Enregistrez vos modifications.

## <a name="add-or-edit-bookmark-using-browser-extensions"></a>Ajouter ou modifier un signet à l’aide d’extensions de navigateur
Les administrateurs de recherche peuvent facilement créer du contenu de recherche en utilisant des extensions de navigateur. Installez l’extension de navigateur, puis accédez au site que vous souhaitez ajouter en tant que signet et ajoutez-le.

Actuellement, des extensions de navigateur sont disponibles pour Edge et Chrome. 
- Pour télécharger l’extension Edge, accédez à [Microsoft Store](https://www.microsoft.com/en-us/p/microsoft-search-content-creator/9nrqdbcbwq55?activetab=pivot:overviewtab) et téléchargez l’application.
- Pour télécharger l’extension Chrome, accédez à [Chrome Web Store](https://chrome.google.com/webstore/detail/microsoft-search-content/nocnablpaoeecfmfnjoheefkogmleipm) et téléchargez l’application.

## <a name="bulk-add-or-edit-bookmarks"></a>Ajout ou modification en bloc de signets
L’administrateur de recherche peut utiliser les fonctions d’importation ou d’exportation pour créer ou modifier des signets en bloc. Il s’agit d’une fonctionnalité très utile lorsqu’un administrateur souhaite ajouter ou modifier un grand nombre de signets. 

Utilisez la fonction d’importation/exportation pour les opérations suivantes :
- Ajout en bloc de signets - Ajoutez des détails dans le fichier modèle du signet, puis importez-le.
- Modification en bloc de signets - Exportez les signets dans un fichier .csv, modifiez les détails des signets dans le fichier .csv exporté, puis importez le fichier .csv mis à jour.
- Importer les sites promus depuis SharePoint.
- Sauvegarde de signets - Exportez les signets dans un fichier .csv.

Pour importer ou exporter des signets :
1. Dans le coin supérieur droit de l’onglet **Signets**, sélectionnez **Importer**. Sélectionnez **Exporter** pour télécharger tous les signets existants dans un fichier .csv.
1. Dans le volet de droite, choisissez l’option d’importation : à l’aide d’un fichier .csv ou à partir de SharePoint.
Téléchargez le fichier modèle pour obtenir la liste des champs et détails requis. 
1. Ajoutez ou modifiez les détails des signets dans le fichier modèle, puis enregistrez-le sur votre ordinateur. 
1. Dans le volet **Importer des signets**, sélectionnez **Parcourir** et choisissez le fichier .csv à importer.
1. Sélectionnez **Importer**.

Remarques importantes concernant le fichier modèle :
- Ne modifiez jamais les données dans les champs suivants : *ID*, *Dernière modification* et *Dernière modification par*.
- Si vous incluez l’*ID* d’un signet existant, celui-ci sera remplacé par les informations contenues dans le fichier d’importation.
- Si un signet existant comporte déjà le même titre ou la même URL, il est mis à jour avec les informations contenues dans le fichier d’importation.
- Certains champs du fichier modèle ne sont pas obligatoires, et les champs obligatoires varient en fonction de l’état du signet.
- En fonction du champ *État*, les signets sont enregistrés en tant que signets brouillons, suggérés ou programmés, ou sont automatiquement publiés.
- Si votre organisation est dotée de plusieurs locataires, vous pouvez exporter vos signets à partir d’un locataire et les importer dans un autre. Avant l’importation, vous devez toutefois supprimer les données de la colonne *ID*.

### <a name="prevent-import-errors"></a>Éviter les erreurs d’importation
Une erreur se produit lorsqu’il manque des données obligatoires ou que celles-ci ne sont pas valides. Un fichier journal signalant les lignes et colonnes à corriger est alors généré. Apportez les modifications nécessaires et essayez à nouveau d’importer le fichier. Il est impossible d’importer ou d’enregistrer les signets tant que toutes les erreurs n’ont pas été résolues.

Pour éviter les erreurs, assurez-vous que votre fichier d’importation est correctement mis en forme et :
- qu’il inclut la ligne d’en-tête ainsi que toutes les colonnes qui se trouvaient dans le modèle d’importation ;
- que l’ordre des colonnes est le même que celui du modèle d’importation.
- Toutes les colonnes comportent des valeurs, à l’exception des trois suivantes, qui peuvent être vides : *ID*, *Dernière modification* et *Dernière modification par*. 
- La colonne *État* n’est pas vide, car il s’agit d’une information obligatoire

## <a name="powerapps"></a>PowerApps
Aidez vos utilisateurs à accomplir certaines tâches, telles que la saisie de périodes de congés ou de frais, en ajoutant des applications PowerApp existantes à vos signets. 

### <a name="what-are-powerapps"></a>Que sont les applications PowerApps ?
PowerApps est un service qui vous permet de créer des applications métier qui s’exécutent dans un navigateur, sur un téléphone ou sur une tablette, sans aucune expérience en matière de codage. Les applications PowerApps fonctionnent dans n’importe quel navigateur et sur n’importe quel appareil, et leur ajout prend moins d’une minute. Pour plus d’informations sur les applications PowerApps, consultez :
- 
  [Formation guidée](https://docs.microsoft.com/fr-FR/learn/browse/?products=powerapps)
- 
  [Documentation](https://docs.microsoft.com/fr-FR/powerapps/maker/canvas-apps/get-sessionid)
- [Accueil PowerApps](https://make.preview.powerapps.com/environments/839eace6-59ab-4243-97ec-a5b8fcc104e4/home)

### <a name="add-a-powerapp-to-a-bookmark"></a>Ajouter une application PowerApp à un signet
1. Recherchez l’[ID de l’application PowerApp](https://docs.microsoft.com/fr-FR/powerapps/maker/canvas-apps/get-sessionid#get-an-app-id) que vous souhaitez ajouter.
1. Connectez-vous et accédez au **Centre d’administration Microsoft 365**.
1. Dans le volet de navigation, accédez à **Paramètres**, puis sélectionnez **Recherche Microsoft**.
1. Ajoutez un nouveau signet ou accédez à un signet existant auquel vous souhaitez ajouter une application **PowerApp**.
1. Dans **Paramètres de signet**, sélectionnez **Application PowerApp**, puis **Ajouter une application PowerApp**.
1. Entrez ou collez l’**ID de l’application**.
    La hauteur et la largeur sont automatiquement ajustées. Les signets peuvent prendre en charge les orientations portrait et paysage, mais actuellement la taille ne peut pas être modifiée. L’aperçu du signet présente une application PowerApp entièrement opérationnelle pour faciliter les tests.
1. Sélectionnez **Publier** ou **Enregistrer en tant que brouillon**.