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
description: Recherchez et actualisez des réponses individuelles, ou servez-vous des outils de Recherche Microsoft disponibles pour les modifier tous à la fois
ms.openlocfilehash: af5f12e759179d7a00d682575a51286e607149b2
ms.sourcegitcommit: 5946fe6aad2331c023bedda8faf826c0248651f8
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41711756"
---
# <a name="manage-qas"></a>Gérer les Q&R

La création de Q&R s’apparente à celle de signets. Les Q&R vous permettent de répondre aux questions des utilisateurs au lieu de vous contenter de leur fournir un lien vers une page web. Les réponses peuvent être mises en forme en texte enrichi à l’aide des outils disponibles. Si un signet et un élément Q&R partagent le même mot clé, le résultat du signet est affiché en premier. Comme pour les signets, l’index des Q&R est actualisé immédiatement après l’ajout ou la modification d’un élément Q&R.

## <a name="add-or-edit-a-single-qa"></a>Ajouter ou modifier un seul élément Q&R

1. Accédez au **Centre d’administration Microsoft 365**.
1. Dans le volet de navigation, accédez à **Paramètres** et sélectionnez **Recherche Microsoft**.
1. Sélectionnez l’onglet **Q&R**. Par défaut, le premier onglet (**Signets**) est sélectionné.
1. Pour ajouter un élément Q&R, sélectionnez **Ajouter nouveau**.
Pour modifier un élément Q&R, sélectionnez-le dans la liste.
1. Lorsque vous ajoutez ou modifiez les informations, l’aperçu est automatiquement mis à jour.
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

Actuellement, des extensions de navigateur sont disponibles pour Edge et Chrome.

- Pour télécharger l’extension Edge, accédez à [Microsoft Store](https://www.microsoft.com/p/microsoft-search-content-creator/9nrqdbcbwq55?activetab=pivot:overviewtab) et téléchargez l’application.
- Pour télécharger l’extension Chrome, accédez à [Chrome Web Store](https://chrome.google.com/webstore/detail/microsoft-search-content/nocnablpaoeecfmfnjoheefkogmleipm) et téléchargez l’application.

## <a name="bulk-add-or-edit-qas"></a>Ajouter ou modifier en bloc des questions et réponses

Les administrateurs peuvent utiliser les fonctions d’importation ou d’exportation pour créer ou modifier des Q&R en bloc. Il s’agit d’une fonctionnalité très utile lorsque les administrateurs ont besoin d’ajouter ou de modifier un grand nombre de Q&R.

Utilisez la fonction d’importation/exportation pour les opérations suivantes :

1. Ajout en bloc de Q&R - Ajoutez des détails dans le fichier modèle de l’élément Q&R, puis importez-le.
1. Modification en bloc de Q&R - Exportez les Q&R dans un fichier .csv, modifiez les détails des Q&R dans le fichier .csv exporté, puis importez le fichier .csv.
1. Sauvegarde de Q&R - Exportez les Q&R dans un fichier .csv.

Pour importer ou exporter des Q&R :

1. Dans le coin supérieur droit de l’onglet Q&R, sélectionnez **Importer**.
Sélectionnez **Exporter** pour télécharger tous les Q&R existants dans un fichier .csv.
1. Dans le volet de droite, choisissez de procéder à l’importation à l’aide d’un fichier .csv.
Téléchargez le fichier modèle pour obtenir la liste des champs et détails requis.
1. Ajoutez ou modifiez les détails des Q&R dans le fichier modèle et enregistrez-le sur votre ordinateur.
1. Dans le volet **Importer des Q&R**, sélectionnez **Parcourir** et choisissez le fichier .csv à importer.
1. Sélectionnez **Importer**.

Remarques importantes concernant le fichier modèle :

- Ne modifiez jamais les données dans les champs suivants : *ID*, *Dernière modification* et *Dernière modification par*.
- Si vous incluez l’*ID* d’un signet existant, celui-ci sera remplacé par les informations contenues dans le fichier d’importation.
- Si un signet existant comporte déjà le même titre ou la même URL, il est mis à jour avec les informations contenues dans le fichier d’importation.
- Certains champs du fichier modèle ne sont pas obligatoires, et les champs obligatoires varient en fonction de l’état du signet.
- En fonction du champ État, les signets sont enregistrés en tant que signets brouillons, suggérés ou programmés, ou sont automatiquement publiés.
- Pour les partenaires qui gèrent plusieurs organisations, vous pouvez exporter vos signets d’une organisation et les importer dans un autre. Avant l’importation, vous devez toutefois supprimer les données de la colonne *ID*.

**Remarque :** vous ne pouvez pas importer de Q&R si le fichier modèle comporte des erreurs. Pour éviter les erreurs, assurez-vous que votre fichier d’importation est correctement mis en forme et qu’il contient toutes les informations requises.

Pour plus d’informations sur la prévention des erreurs, consultez [Éviter les erreurs d’importation](manage-bookmarks.md#prevent-import-errors).
