---
title: Gérer les Q&R
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
ms.assetid: 7e3432e6-5317-4d63-90b0-52da6fddd343
description: Recherchez et mettez à jour les réponses individuellement ou utilisez les outils de recherche Microsoft disponibles pour modifier les&Q en une seule fois.
ms.openlocfilehash: 2a8b0727ef3540a35d617cf6c8bae7b0d99767a8
ms.sourcegitcommit: 988c37610e71f9784b486660400aecaa7bed40b0
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/09/2020
ms.locfileid: "47422999"
---
# <a name="manage-qas"></a>Gérer les Q&R

La création de Q&R s’apparente à celle de signets. Q&en tant que vous permettent de répondre aux questions de l’utilisateur au lieu de simplement fournir un lien vers une page Web. Vous pouvez également mettre en forme la réponse en texte enrichi. Si un signet et un Q&un partage du même mot-clé, le résultat du signet est affiché en premier. Comme les signets, le Q&un index est actualisé immédiatement après qu’un Q&a est ajouté ou modifié.

## <a name="add-or-edit-a-single-qa"></a>Ajouter ou modifier un seul élément Q&R

1. Dans le [Centre d’administration 365 de Microsoft](https://admin.microsoft.com), accédez à [**Q&**](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/qnas)
1. Pour ajouter un Q&A, sélectionnez **Ajouter**.
Pour modifier un élément Q&R, sélectionnez-le dans la liste. Lorsque vous ajoutez ou modifiez les informations, l’aperçu est automatiquement mis à jour.
1. Enregistrez vos modifications.

### <a name="supported-html-tags"></a>Balises HTML prises en charge

Vous pouvez utiliser le contenu HTML existant ou ajouter des balises HTML à votre réponse (description). Les balises non prises en charge sont ignorées.

Les balises HTML suivantes sont prises en charge :

- blockquote
- div
- em
- H1, h2, h3 et h4
- ol, ul et li
- p
- Pre
- span
- Fort
- table, thead, tbody, tr, th et td
- u
- a
- code
- br
- hr
- img

## <a name="add-or-edit-qas-using-browser-extensions"></a>Ajouter ou modifier des&Q à l’aide des extensions de navigateur

Les administrateurs de recherche peuvent facilement créer du contenu de recherche en utilisant des extensions de navigateur. Installez l’extension du navigateur, puis accédez au site à partir duquel vous souhaitez générer un Q&A. Vous pouvez ensuite créer le Q&A et inclure un lien vers le site source.

Actuellement, les extensions de navigateur sont disponibles pour Microsoft Edge et chrome.

- Pour télécharger les extensions pour Edge (hérité), accédez à [Microsoft Store](https://www.microsoft.com/p/microsoft-search-content-creator/9nrqdbcbwq55?activetab=pivot:overviewtab).
- Pour télécharger les extensions chrome ou Edge (chrome), accédez au [magasin Web chrome](https://chrome.google.com/webstore/detail/microsoft-search-content/nocnablpaoeecfmfnjoheefkogmleipm).

## <a name="bulk-add-or-edit-qas"></a>Ajouter ou modifier en bloc des questions et réponses

Les administrateurs peuvent utiliser les fonctionnalités d’importation et d’exportation pour créer ou modifier en bloc des&Q en tant que.

Utilisez la fonctionnalité importation/exportation pour :

- Ajouter des Q&en bloc en tant que-ajoutez des détails dans le dossier Q&un fichier de modèle, puis importez-le.
- Modifier en bloc Q&sous-exporter Q&en tant que fichier. csv, modifiez le Q&les détails du fichier exporté, puis importez le fichier.
- Sauvegardez Q&sous-exporter Q&en tant que fichier. csv.

Pour importer ou exporter des&Q, procédez comme suit :

1. Dans le coin supérieur droit de l’onglet Q&R, sélectionnez **Importer**.
Sélectionnez **Exporter** pour télécharger tous les&Q existants sous la forme d’un fichier. csv.
1. Dans le volet droit, sélectionnez l’option d’importation à l’aide d’un fichier. csv. Téléchargez le fichier de modèle pour obtenir la liste des champs et détails requis.
1. Ajouter ou modifier Q&les détails dans le fichier de modèle et l’enregistrer sur votre ordinateur.
1. Dans le **&d’importation un** volet, sélectionnez **Parcourir**, puis sélectionnez le fichier. csv que vous souhaitez importer.
1. Sélectionnez **Importer**.

Conseils importants pour les modèles de fichiers :

- Ne modifiez jamais les données dans les champs suivants : **ID**, **Dernière modification** et **Dernière modification par**.
- Si vous incluez l’**ID** d’un signet existant, celui-ci sera remplacé par les informations contenues dans le fichier d’importation.
- S’il existe un signet existant qui a le même titre ou URL, le signet est mis à jour avec les informations contenues dans le fichier d’importation.
- Les champs du fichier de modèle ne sont pas tous obligatoires et les champs obligatoires varient en fonction de l’état du signet.
- En fonction du champ **État** , les signets sont enregistrés en tant que *Brouillon*, *suggéré*ou *planifié*, ou ils sont publiés automatiquement.
- Pour les partenaires qui gèrent plusieurs organisations : vous pouvez exporter vos signets d’une organisation et les importer dans un autre. Avant l’importation, vous devez toutefois supprimer les données de la colonne **ID**.

> [!NOTE]
> Vous ne pouvez pas importer les&Q comme s’il existe des erreurs dans le fichier de modèle. Pour éviter les erreurs, assurez-vous que votre fichier d’importation est correctement mis en forme et incluez toutes les informations requises.

Pour plus d’informations sur la façon d’éviter les erreurs, voir [empêcher les erreurs d’importation](manage-bookmarks.md#prevent-import-errors).
