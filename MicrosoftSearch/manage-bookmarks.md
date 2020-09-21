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
ms.openlocfilehash: eb65121b53ab110b91880a65a5146d868f3a7405
ms.sourcegitcommit: d88226f9c3a99540a591dc0a26408bb9960cf39a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/19/2020
ms.locfileid: "48134166"
---
# <a name="manage-bookmarks"></a>Gérer des signets

Vous pouvez créer un signet en quelques étapes. Chaque signet comprend un titre, une URL et un ensemble de mots clés qui le déclenchent. Vous pouvez également ajouter des catégories à un signet qui peuvent être utilisées pour le tri et le filtrage dans le portail d’administration. Un signet peut avoir plusieurs mots-clés et les signets peuvent partager le même mot-clé, mais le mot clé réservé ne peut pas être partagé. Lors de la création ou de la modification d’un signet, l’index de recherche est immédiatement actualisé et le signet est immédiatement accessible aux utilisateurs.

Si votre organisation a défini des résultats promus dans SharePoint, vous pouvez importer les résultats promus dans **Microsoft Search** et mettre le contenu importé à la disposition de vos utilisateurs. Cette méthode simple permet de renseigner rapidement les résultats de recherche dès que vous avez configuré la fonctionnalité **Recherche Microsoft**, et d’améliorer son efficacité pour vos utilisateurs. Nous vous recommandons d’utiliser des résultats promus à partir de SharePoint comme référence pour comprendre comment nommer et créer des résultats de recherche pertinents.

## <a name="add-or-edit-a-single-bookmark"></a>Ajouter ou modifier un seul signet

1. Dans le [Centre d’administration Microsoft 365](https://admin.microsoft.com), accédez à [**signets**](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/bookmarks).
1. Pour ajouter un signet, sélectionnez **Ajouter**.
Pour modifier un signet, sélectionnez-le dans la liste.
1. Lorsque vous ajoutez ou modifiez les informations, l’aperçu est automatiquement mis à jour.
1. Enregistrez vos modifications.

## <a name="add-or-edit-bookmark-using-browser-extensions"></a>Ajouter ou modifier un signet à l’aide d’extensions de navigateur

Les administrateurs de recherche peuvent facilement créer du contenu de recherche en utilisant des extensions de navigateur. Installez l’extension du navigateur, accédez au site que vous souhaitez ajouter en tant que signet, puis ajoutez le signet.

Actuellement, des extensions de navigateur sont disponibles pour Edge et Chrome.

- Pour télécharger les extensions de serveur Edge, accédez à [Microsoft Store](https://www.microsoft.com/p/microsoft-search-content-creator/9nrqdbcbwq55?activetab=pivot:overviewtab) et téléchargez l’application.
- Pour télécharger les extensions chrome, accédez à la [boutique web chrome](https://chrome.google.com/webstore/detail/microsoft-search-content/nocnablpaoeecfmfnjoheefkogmleipm) et téléchargez l’application.

## <a name="bulk-add-or-edit-bookmarks"></a>Ajout ou modification en bloc de signets

Utilisez la fonctionnalité d’importation ou d’exportation pour créer ou modifier en bloc des signets. Cela accélère et facilite l’ajout ou la modification d’un grand nombre de signets. Utilisez-le pour :

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

Voici quelques points importants à propos du fichier de modèle :

- Ne jamais modifier les données de ces champs : *ID*, *Last modified*et *Last modified by*
- Si vous incluez l' *ID* d’un signet existant, il sera remplacé par les informations contenues dans le fichier d’importation.
- Pour le signet existant avec le même titre ou URL, le signet est mis à jour avec les informations contenues dans le fichier d’importation.
- Certains champs du fichier modèle ne sont pas obligatoires, et les champs obligatoires varient en fonction de l’état du signet.
- En fonction du champ d' *État* , les signets seront enregistrés en tant que brouillon, suggéré, programmé ou ils seront publiés automatiquement.
- Pour les partenaires qui gèrent plusieurs organisations, vous pouvez exporter vos signets d’une organisation et les importer dans un autre. Toutefois, vous devez supprimer les données de la colonne *ID* avant de procéder à l’importation.

### <a name="prevent-import-errors"></a>Éviter les erreurs d’importation

Une erreur se produit lorsqu’il manque des données obligatoires ou que celles-ci ne sont pas valides. Un fichier journal signalant les lignes et colonnes à corriger est alors généré. Apportez les modifications nécessaires et essayez à nouveau d’importer le fichier. Il est impossible d’importer ou d’enregistrer les signets tant que toutes les erreurs n’ont pas été résolues.

Pour éviter les erreurs, assurez-vous que votre fichier d’importation est correctement mis en forme et :

- qu’il inclut la ligne d’en-tête ainsi que toutes les colonnes qui se trouvaient dans le modèle d’importation ;
- que l’ordre des colonnes est le même que celui du modèle d’importation.
- Toutes les colonnes ont des valeurs, sauf les trois pouvant être vides : *ID*, *Last modified*et *Last modified by*
- La colonne *État* n’est pas vide, il s’agit des informations requises.

Pour éviter les erreurs de duplication de signet à signet :

- N’utilisez pas d’URL en double pour différents signets. Si une URL est affectée à un autre signet et que vous essayez de la rajouter à partir d’un fichier d’importation, vous obtiendrez une erreur. Cela s’applique également aux URL en double pour d’autres types de réponses.
- Lors de la mise à jour de signets existants, utilisez la colonne *ID de signet* . Vous pouvez mettre à jour toute autre propriété d’un signet existant, telle que mot clé ou description, mais vous devez vous assurer que l' *ID de signet* se trouve dans la colonne appropriée du fichier d’importation. Si l' *ID de signet* est présent, il ne sera pas traité comme une nouvelle addition et ne sera pas traité comme une erreur.

## <a name="power-apps"></a>Power Apps

Aidez vos utilisateurs à effectuer des tâches, telles que la saisie des heures de vacances ou de création de rapports, en ajoutant des applications d’alimentation existantes à vos signets.

### <a name="power-apps-explained"></a>Description des applications puissantes

Les applications Power sont un service qui vous permet de créer des applications métier qui s’exécutent dans un navigateur ou sur un téléphone ou une tablette sans intervention de codage. Les applications Power fonctionnent dans n’importe quel navigateur et sur n’importe quel appareil et prennent moins d’une minute à ajouter. Pour plus d’informations sur les applications d’alimentation, voir :

- [Formation guidée](https://docs.microsoft.com/learn/browse/?terms=power%20apps)
- [Documentation](https://docs.microsoft.com/powerapps/maker/canvas-apps/get-sessionid)
- [Accueil des applications puissantes](https://make.preview.powerapps.com/environments/839eace6-59ab-4243-97ec-a5b8fcc104e4/home)

### <a name="add-a-power-app-to-a-bookmark"></a>Ajouter une application d’alimentation à un signet

1. Recherchez l' [ID d’application de l’application d’alimentation](https://docs.microsoft.com/powerapps/maker/canvas-apps/get-sessionid#get-an-app-id) que vous souhaitez ajouter.
1. Dans le [Centre d’administration Microsoft 365](https://admin.microsoft.com), accédez à [**signets**](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/bookmarks).
1. Ajoutez un signet ou recherchez un signet existant auquel vous souhaitez ajouter une **application de gestion** de l’alimentation.
1. Dans **paramètres du signet**, sélectionnez **alimentation**, puis entrez ou collez l’ID de l' **application**.
    La hauteur et la largeur sont ajustées automatiquement en fonction de l’orientation sélectionnée lors de la création de l’application d’alimentation. Les signets prennent en charge les orientations portrait et paysage. L’aperçu du signet présente une application PowerApp entièrement opérationnelle pour faciliter les tests.
1. Sélectionnez **Publier** ou **Enregistrer en tant que brouillon**.
