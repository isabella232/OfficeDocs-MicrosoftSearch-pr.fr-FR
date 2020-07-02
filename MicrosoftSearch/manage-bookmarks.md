---
title: Gérer des signets
ms.author: jeffkizn
author: jeffkizn
manager: parulm
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
ms.assetid: c0c814d0-f7e4-444e-b18e-09beb45c9322
description: Créer et mettre à jour des signets et des méthodes pour modifier en bloc les résultats de signet pour Microsoft Search
ms.openlocfilehash: 64e430309ef1969ab804e8d757b987332f0a6006
ms.sourcegitcommit: 9ba062f8b632a74e56ad7ec4dffaa1d8dab57614
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/01/2020
ms.locfileid: "44996102"
---
# <a name="manage-bookmarks"></a>Gérer des signets

Vous pouvez créer un signet en quelques étapes. Chaque signet comprend un titre, une URL et un ensemble de mots clés qui le déclenchent. Un signet peut comprendre plusieurs mots clés, et plusieurs signets peuvent partager le même mot clé, mais un mot clé réservé ne peut pas être partagé. Lorsqu’un signet est créé ou modifié, l’index de recherche est aussitôt actualisé et le signet est immédiatement accessible aux utilisateurs.

Si votre organisation a promu les résultats configurés dans SharePoint, vous pouvez importer les résultats promus dans **Microsoft Search** et mettre le contenu importé à la disposition de vos utilisateurs. Cette méthode simple permet de renseigner rapidement les résultats de recherche dès que vous avez configuré la fonctionnalité **Recherche Microsoft**, et d’améliorer son efficacité pour vos utilisateurs. Nous vous recommandons d’utiliser les résultats promus de SharePoint comme référence pour apprendre à nommer et créer des résultats de recherche pertinents.

## <a name="add-or-edit-a-single-bookmark"></a>Ajouter ou modifier un seul signet

1. Accédez au **Centre d’administration Microsoft 365**.
1. Dans le volet de navigation, accédez à **paramètres**  >  **Microsoft Search**  >  **Answers**  >  [**signets**](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/bookmarks)de réponses Microsoft Search.
1. Pour ajouter un signet, sélectionnez **Ajouter nouveau**.
Pour modifier un signet, sélectionnez-le dans la liste.
1. Lorsque vous ajoutez ou modifiez les informations, l’aperçu est automatiquement mis à jour.
1. Enregistrez vos modifications.

## <a name="add-or-edit-bookmark-using-browser-extensions"></a>Ajouter ou modifier un signet à l’aide d’extensions de navigateur

Les administrateurs de recherche peuvent facilement créer du contenu de recherche en utilisant des extensions de navigateur. Installez l’extension de navigateur, puis accédez au site que vous souhaitez ajouter en tant que signet et ajoutez-le.

Actuellement, des extensions de navigateur sont disponibles pour Edge et Chrome.

- Pour télécharger les extensions de serveur Edge, accédez à [Microsoft Store](https://www.microsoft.com/p/microsoft-search-content-creator/9nrqdbcbwq55?activetab=pivot:overviewtab) et téléchargez l’application.
- Pour télécharger les extensions chrome, accédez à la [boutique web chrome](https://chrome.google.com/webstore/detail/microsoft-search-content/nocnablpaoeecfmfnjoheefkogmleipm) et téléchargez l’application.

## <a name="bulk-add-or-edit-bookmarks"></a>Ajout ou modification en bloc de signets

L’administrateur de recherche peut utiliser les fonctions d’importation ou d’exportation pour créer ou modifier des signets en bloc. Il s’agit d’une fonctionnalité très utile lorsqu’un administrateur souhaite ajouter ou modifier un grand nombre de signets.

Utilisez la fonction d’importation/exportation pour les opérations suivantes :

- Ajout en bloc de signets - Ajoutez des détails dans le fichier modèle du signet, puis importez-le.
- Modification en bloc de signets - Exportez les signets dans un fichier .csv, modifiez les détails des signets dans le fichier .csv exporté, puis importez le fichier .csv mis à jour.
- Importer les sites promus depuis SharePoint.
- Sauvegarde de signets - Exportez les signets dans un fichier .csv.

Pour importer ou exporter des signets :

1. Dans le coin supérieur droit de l’onglet **Signets**, sélectionnez **Importer**.
Sélectionnez **Exporter** pour télécharger tous les signets existants dans un fichier .csv.
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
- Pour les partenaires qui gèrent plusieurs organisations, vous pouvez exporter vos signets d’une organisation et les importer dans un autre. Avant l’importation, vous devez toutefois supprimer les données de la colonne *ID*.

### <a name="prevent-import-errors"></a>Éviter les erreurs d’importation

Une erreur se produit lorsqu’il manque des données obligatoires ou que celles-ci ne sont pas valides. Un fichier journal signalant les lignes et colonnes à corriger est alors généré. Apportez les modifications nécessaires et essayez à nouveau d’importer le fichier. Il est impossible d’importer ou d’enregistrer les signets tant que toutes les erreurs n’ont pas été résolues.

Pour éviter les erreurs, assurez-vous que votre fichier d’importation est correctement mis en forme et :

- qu’il inclut la ligne d’en-tête ainsi que toutes les colonnes qui se trouvaient dans le modèle d’importation ;
- que l’ordre des colonnes est le même que celui du modèle d’importation.
- Toutes les colonnes comportent des valeurs, à l’exception des trois suivantes, qui peuvent être vides : *ID*, *Dernière modification* et *Dernière modification par*.
- La colonne *État* n’est pas vide, car il s’agit d’une information obligatoire

Pour éviter les erreurs de duplication de signet à signet, suivez les meilleures pratiques suivantes :

- N’utilisez pas d’URL en double pour différents signets. Si une URL est déjà affectée à un autre signet et que vous la rajoutez à partir d’un fichier d’importation, vous obtiendrez une erreur. Cela s’applique également aux URL en double pour d’autres types de réponses.
- Utilisez la colonne *ID de signet* lors de la mise à jour de signets existants. Vous pouvez mettre à jour toute autre propriété d’un signet existant, telle que mot clé ou description, mais vous devez vous assurer que l' *ID de signet* se trouve dans la colonne appropriée du fichier d’importation. Si l' *ID de signet* est présent, le service ne le considère pas comme étant une nouvelle addition et n’est pas traité comme une erreur.

## <a name="power-apps"></a>Power Apps

Aidez vos utilisateurs à accomplir certaines tâches, telles que la saisie de périodes de congés ou de frais, en ajoutant des applications PowerApp existantes à vos signets.

### <a name="power-apps-explained"></a>Description des applications puissantes

Les applications Power sont un service qui vous permet de créer des applications métier qui s’exécutent dans un navigateur ou sur un téléphone ou une tablette sans intervention de codage. Les applications PowerApps fonctionnent dans n’importe quel navigateur et sur n’importe quel appareil, et leur ajout prend moins d’une minute. Pour plus d’informations sur les applications PowerApps, consultez :

- [Formation guidée](https://docs.microsoft.com/learn/browse/?products=powerapps)
- [Documentation](https://docs.microsoft.com/powerapps/maker/canvas-apps/get-sessionid)
- [Accueil des applications puissantes](https://make.preview.powerapps.com/environments/839eace6-59ab-4243-97ec-a5b8fcc104e4/home)

### <a name="add-a-power-app-to-a-bookmark"></a>Ajouter une application d’alimentation à un signet

1. Recherchez l' [ID d’application de l’application d’alimentation](https://docs.microsoft.com/powerapps/maker/canvas-apps/get-sessionid#get-an-app-id) que vous souhaitez ajouter.
1. Connectez-vous au [**Centre d’administration Microsoft 365**](https://admin.microsoft.com).
1. Dans le volet de navigation, accédez à **paramètres**  >  **Microsoft Search**  >  **Answers**  >  [**signets**](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/bookmarks)de réponses Microsoft Search.
1. Ajoutez un nouveau signet ou accédez à un signet existant auquel vous souhaitez ajouter une application **PowerApp**.
1. Dans **Paramètres de signet**, sélectionnez **Application PowerApp**, puis **Ajouter une application PowerApp**.
1. Entrez ou collez l’**ID de l’application**.
    La hauteur et la largeur sont automatiquement ajustées. Les signets peuvent prendre en charge les orientations portrait et paysage, mais actuellement la taille ne peut pas être modifiée. L’aperçu du signet présente une application PowerApp entièrement opérationnelle pour faciliter les tests.
1. Sélectionnez **Publier** ou **Enregistrer en tant que brouillon**.
