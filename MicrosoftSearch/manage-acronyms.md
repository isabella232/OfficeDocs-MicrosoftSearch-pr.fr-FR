---
title: Gérer les réponses des acronymes dans Microsoft Search
ms.author: v-pamcna
author: TrishaMc1
manager: mnirkhe
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: Créer et mettre à jour des réponses d’acronymes dans Microsoft Search
ms.openlocfilehash: 4f47d5b743709657459ccbc6b03897c29a51e109
ms.sourcegitcommit: 21361af7c244ffd6ff8689fd0ff0daa359bf4129
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/14/2019
ms.locfileid: "38626818"
---
# <a name="manage-acronyms-answers-in-microsoft-search"></a>Gérer les acronymes Answers in Microsoft Search

Les employés utilisent souvent des acronymes et des abréviations inconnus utilisés par leur organisation ou leur équipe. Les termes propres aux organisations ou aux équipes peuvent être nouveaux pour les personnes qui passent d’une équipe à une autre, qui travaillent avec des équipes partenaires internes ou de nouveaux employés.

Les organisations ne disposent pas toujours d’une référence unique pour leur terminologie standard. L’absence de référence unique rend difficile de trouver des définitions ou des expansions pour ces acronymes. Microsoft Search résout ce problème avec des acronymes.

## <a name="what-users-experience"></a>Expérience des utilisateurs
Les utilisateurs de Microsoft Search peuvent obtenir des définitions avec des acronymes dans [Bing](https://Bing.com), [Microsoft Office 365](https://Office.com)et [Microsoft SharePoint Online](https://products.office.com/sharepoint/collaboration). Dans les zones de **recherche** des barres d’en-tête, les utilisateurs entrent des requêtes comme les exemples suivants :

- *Qu’est-ce que* DNN
- *Définir* DNN
- *Définition* DNN
- *Développez* DNN
- *Expansion* DNN
- *Signification de* DNN
- DNN *signifie*

Les résultats suggérés incluent toutes les significations des DNN présentes dans l’organisation de l’utilisateur.

> [!NOTE]
> Les utilisateurs doivent entrer une requête qui inclut les *Mots clés* spécifiés de l’acronyme pour déclencher les réponses correspondantes.  

## <a name="set-up-acronyms-answers"></a>Configurer des acronymes pour les réponses
Dans le centre d' [administration](https://admin.microsoft.com)Microsoft 365, accédez à **paramètres** > **acronymes****Microsoft Search** >, puis sélectionnez **Ajouter des acronymes**. 

Microsoft Search interroge deux sources de données pour fournir des informations d’acronymes aux recherches des utilisateurs :

1.  **Acronymes éditorial**. Fourni par les administrateurs informatiques dans le [Centre d’administration](https://admin.microsoft.com).
2.  **Acronymes**de extrait. Extrait par Microsoft Search de la messagerie et des documents personnels de l’utilisateur et des données accessibles au public au sein de l’organisation.

### <a name="set-up-editorial-acronyms"></a>Configurer des acronymes éditoriaux
Les administrateurs informatiques peuvent configurer des acronymes éditoriaux sous l' [onglet acronymes](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch) dans le [centre d’administration 365 de Microsoft]( https://admin.microsoft.com). Vous pouvez ajouter des acronymes à partir de n’importe quel site ou référentiel interne vers le centre d’administration. Les acronymes éditoriaux peuvent être ajoutés à l’état **publié** ou **Brouillon** :

**État publié**. Les acronymes sont disponibles pour les employés de l’organisation via Microsoft Search.

> [!NOTE]
> Il peut falloir jusqu’à trois jours pour que les acronymes ajoutés à l’État publié soient disponibles dans Microsoft Search.

**État Brouillon**. Si les administrateurs souhaitent examiner les réponses des acronymes avant de les rendre disponibles dans Microsoft Search, ils peuvent ajouter les acronymes à l’état Brouillon. Les acronymes ajoutés à l’état Brouillon ne sont pas disponibles dans Microsoft Search. Les administrateurs doivent ajouter les acronymes à l’État publié pour les rendre disponibles.

Les administrateurs peuvent ajouter des acronymes individuellement ou les importer par bloc dans un fichier CSV. Téléchargez un fichier CSV avec les champs indiqués dans le tableau suivant :

| Acronyme (obligatoire) | Expansion (obligatoire) | Description  | Source | État (obligatoire) |
| --------- | --------- | ---------- | --------- |--------- |
| *439* | *Abréviation orthographiée* |  | *URL* | *Publié ou brouillon* |

### <a name="csv-fields"></a>Champs CSV
**Acronyme**. Contient la forme courte ou l’acronyme réel. Par exemple, *DNN*.

**Expansion**. Contient l’expansion de l’acronyme. Il s’agit par exemple d’un *réseau neuronal profond*.

**Description**. Brève description de l’acronyme qui donne aux utilisateurs un aperçu rapide de ce que signifient l’acronyme et son expansion. Par exemple, *un réseau neuronal profond est un réseau neuronal avec un certain niveau de complexité, un réseau neuronal avec plus de deux couches*.

**Source**. URL de la page ou du site Web où vous souhaitez que les utilisateurs accèdent à des informations supplémentaires sur l’acronyme.

**État**. Ce champ peut prendre deux valeurs :

- **Brouillon**. Ajoute l’acronyme à l’état Brouillon.
- **Publié**. Ajoute l’acronyme à l’État publié et le rend disponible dans Microsoft Search.

### <a name="mined-acronyms"></a>Acronymes de extrait
Il peut être difficile pour les administrateurs d’ajouter tous les acronymes utilisés dans une organisation aux réponses. Cette fonctionnalité peut trouver des acronymes que les administrateurs de recherche ne tiennent pas compte de. Pour ce faire, Microsoft Search explore également des acronymes de ces sources :

- Les e-mails des utilisateurs.
- Documents dans [SharePoint](https://products.office.com/sharepoint/collaboration), [Microsoft OneDrive]( https://onedrive.live.com/about/) et [Microsoft OneNote](http://www.onenote.com/).
- Documents publics au sein de l’organisation auxquels les utilisateurs ont accès dans SharePoint, OneDrive ou OneNote.

Microsoft Search garantit que seuls les utilisateurs disposant d’autorisations et d’accès à un document peuvent voir les acronymes qu’il contient. Les acronymes sont extraits de la boîte de réception d’un utilisateur et stockés dans l’utilisateur Shard. Seul l’utilisateur peut accéder aux acronymes extraits de la boîte de réception de l’utilisateur.

> [!NOTE]
> Aucune installation de l’administrateur informatique n’est nécessaire pour les acronymes de l’extrait.

## <a name="frequently-asked-questions"></a>Questions fréquemment posées
**Q : comment les données éditoriales et extraites sont-elles classées ?**

**A :** La fonctionnalité classe actuellement les acronymes éditoriaux par-dessus les acronymes.

**Q : combien de temps faut-il pour que les acronymes soient visibles dans Microsoft Search après leur publication ?**

**A :**  Trois jours sont nécessaires pour que les acronymes ajoutés à l’État publié soient disponibles dans Microsoft Search. 

**Q : comment les utilisateurs déclenchent-ils les réponses ?**

**R**: pour obtenir les réponses des acronymes, les utilisateurs doivent entrer des modèles de requête spécifiques dans une zone de **recherche** [Bing](https://bing.com), [Office 365](https://Office.com)ou [SharePoint](https://products.office.com/sharepoint/collaboration) . Voici des exemples de requêtes qui recherchent des réponses pour le terme *DNN* :

- *Qu’est-ce que* DNN
- *Définir* DNN
- *Définition* DNN
- *Développez* DNN
- *Expansion* DNN
- *Signification de* DNN
- DNN *signifie*

**Q : combien de temps faut-il pour que les acronymes s’affichent lorsque vous recevez ou envoyez un nouveau message ou un nouveau document ?**

**A :** Les acronymes extraites d’un nouveau message électronique ou d’un nouveau document prennent jusqu’à sept jours pour apparaître dans les résultats de Microsoft Search.

**Q : est-ce que les documents doivent être dans un format spécifique pour que l’exploration les récupère ?**

**A :** Nbre. Nous prenons en charge tous les types de fichiers, à l’exception des fichiers d’image, de dossiers et zip.

**Q : les acronymes de Microsoft mien seront-ils issus de documents dans toutes les langues ?**

**A**: Microsoft prend uniquement en charge l’exploration des documents en anglais. La prise en charge d’autres langues sera ajoutée en plusieurs phases.

**Q : que se passe-t-il si mon organisation ne souhaite pas afficher d’acronymes extrait ? Puis-je arrêter l’affichage des acronymes d’extrait dans les résultats de recherche ?**

**A**: pour désactiver l’affichage des acronymes d’extrait dans les résultats de la recherche, créez un ticket de support client en suivant les instructions indiquées sur [contacter le support technique pour les produits métiers](https://docs.microsoft.com/office365/admin/contact-support-for-business-products?redirectSourcePath=%252fen-us%252farticle%252fContact-Office-365-for-business-support-32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b&view=o365-worldwide&tabs=online#BKMK_call_support).
Une fois que vous avez créé un ticket de support, il prend jusqu’à 48 heures pour que les acronymes d’extrait s’affichent dans les résultats de la recherche. 

**Q : Quand recevrai-je des réponses d’acronymes dans [Office 365](https://Office.com) et [SharePoint Online](https://products.office.com/sharepoint/collaboration)?**

**R**: Acronymes les réponses sont actuellement disponibles uniquement dans Microsoft Search dans [Bing](https://bing.com). Elles seront déployées dans Office 365 et SharePoint Online dans 2020.
