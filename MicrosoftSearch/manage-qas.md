---
title: Gérer les Q&R
ms.author: jeffkizn
author: jeffkizn
manager: parulm
ms.audience: Admin
ms.topic: article
ms.service: mssearch
ms.localizationpriority: medium
search.appverid:
- BFB160
- MET150
- MOE150
ms.assetid: 7e3432e6-5317-4d63-90b0-52da6fddd343
description: Recherchez et mettez à jour les réponses individuellement ou utilisez les outils Recherche Microsoft disponibles pour modifier les&en même temps.
ms.openlocfilehash: 2ee42e3feaf5c14b2af820360f753ecc2e116f9b
ms.sourcegitcommit: ca5ee826ba4f4bb9b9baabc9ae8a130011c2a3d0
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/15/2021
ms.locfileid: "59334487"
---
# <a name="manage-qas"></a>Gérer les Q&R

La création de Q&R s’apparente à celle de signets. Q&vous permettre de répondre aux questions de l’utilisateur au lieu de simplement fournir un lien vers une page web. Vous pouvez également formater la réponse en texte enrichi. Si un signet et un signet&A partagent le même mot clé, le résultat du signet s’affiche en premier. Comme les signets, la&un index est actualisé immédiatement après l’ajout ou la&A.

## <a name="add-or-edit-a-single-qa"></a>Ajouter ou modifier un seul élément Q&R

1. Dans la [Centre d'administration Microsoft 365,](https://admin.microsoft.com)allez à [**Q&A**](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/qnas)
1. Pour ajouter une question&R, sélectionnez **Ajouter.**
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

## <a name="add-or-edit-qas-using-browser-extensions"></a>Ajouter ou modifier des Q&à l’aide des extensions de navigateur

Les administrateurs de recherche peuvent facilement créer du contenu de recherche en utilisant des extensions de navigateur. Installez l’extension de navigateur, puis allez sur le site à partir duquel vous souhaitez générer une&R. Vous pouvez ensuite créer la&A et inclure un lien vers le site source.

Actuellement, les extensions de navigateur sont disponibles pour Microsoft Edge et Chrome.

- Pour télécharger des extensions pour Edge (hérité), Microsoft Store [.](https://www.microsoft.com/p/microsoft-search-content-creator/9nrqdbcbwq55?activetab=pivot:overviewtab)
- Pour télécharger les extensions Chrome ou Edge (Chromium), go to the [Chrome web store](https://chrome.google.com/webstore/detail/microsoft-search-content/nocnablpaoeecfmfnjoheefkogmleipm).

## <a name="bulk-add-or-edit-qas"></a>Ajouter ou modifier en bloc des questions et réponses

Les administrateurs peuvent utiliser les fonctionnalités d’importation et d’exportation pour créer ou modifier en bloc des&as.

Utilisez la Import/Export pour :

- Ajoutez en bloc des&- Ajoutez des détails dans le fichier de modèle&A, puis importez-le.
- Modification en bloc de Q&- Exporter les Q&Comme à un fichier .csv, modifiez les détails de la&Q dans le fichier exporté, puis importez le fichier.
- Back up&Q As - Export Q&As to a .csv file.

Pour importer ou exporter des Q&comme :

1. Dans le coin supérieur droit de l’onglet Q&R, sélectionnez **Importer**.
Sélectionnez **Exporter** pour télécharger toutes les données Q&comme dans un .csv existant.
1. Dans le volet droit, sélectionnez l’option à importer à l’aide d'.csv fichier. Téléchargez le fichier modèle pour obtenir la liste des champs et détails requis.
1. Ajoutez ou modifiez Q&détails dans le fichier de modèle et enregistrez-le sur votre ordinateur.
1. Dans le **volet Importer&A,** sélectionnez **Parcourir,** puis sélectionnez .csv fichier à importer.
1. Sélectionnez **Importer**.

Conseils importants sur les fichiers de modèles :

- Ne modifiez jamais les données dans les champs suivants : **ID**, **Dernière modification** et **Dernière modification par**.
- Si vous incluez l’**ID** d’un signet existant, celui-ci sera remplacé par les informations contenues dans le fichier d’importation.
- S’il existe un signet ayant le même titre ou la même URL, le signet est mis à jour avec les informations dans le fichier d’importation.
- Tous les champs du fichier de modèle ne sont pas obligatoires et les champs requis varient en fonction de l’état du signet.
- En fonction du **champ État,** les signets sont enregistrés en tant que brouillons, suggérés ou programmés, ou ils sont publiés automatiquement.   
- Pour les partenaires qui gèrent plusieurs organisations : vous pouvez exporter vos signets d’une organisation et les importer dans une autre. Avant l’importation, vous devez toutefois supprimer les données de la colonne **ID**.

> [!NOTE]
> Vous ne pouvez pas importer Q&comme s’il y avait des erreurs dans le fichier modèle. Pour éviter les erreurs, assurez-vous que votre fichier d’importation est correctement formaté et incluez toutes les informations requises.

Pour plus d’informations sur la prévention des erreurs, voir [Empêcher les erreurs d’importation.](manage-bookmarks.md#prevent-import-errors)
