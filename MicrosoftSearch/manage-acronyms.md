---
title: Gérer les réponses des acronymes dans Microsoft Search
ms.author: rakkum
author: rakeshMSFT
manager: jeffkizn
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: Créer et mettre à jour des réponses d’acronymes dans Microsoft Search
ms.openlocfilehash: ff79e3d741e10d401873c29d86739e61c9f53329
ms.sourcegitcommit: e6ceb07cae208648dadd5452a077414ab5a4513f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/22/2020
ms.locfileid: "49728005"
---
# <a name="manage-acronyms-answers-in-microsoft-search"></a>Gérer les acronymes Answers in Microsoft Search

Les utilisateurs ont souvent des acronymes et des abréviations inconnus utilisés par leur organisation ou leur équipe. Les termes propres aux organisations ou aux équipes peuvent être nouveaux pour les personnes qui passent d’une équipe à une autre, qui travaillent avec des équipes partenaires internes ou qui sont nouveaux dans l’organisation.

Les organisations ne disposent pas toujours d’une référence unique pour leur terminologie standard. L’absence de référence unique rend difficile de trouver des définitions ou des expansions pour ces acronymes. Microsoft Search résout ce problème avec des acronymes.

## <a name="what-users-experience"></a>Expérience des utilisateurs

Les utilisateurs de Microsoft Search peuvent obtenir des définitions avec des acronymes dans [Bing](https://Bing.com), [SharePoint](https://products.office.com/sharepoint/collaboration)et [Office 365](https://Office.com). Dans la zone de **recherche** , les utilisateurs entrent des requêtes comme les exemples suivants :

- *Qu’est-ce que* DNN
- *Définir* DNN
- *Définition* DNN
- *Développez* DNN
- *Expansion* DNN
- *Signification de* DNN
- DNN *signifie*

Le résultat inclut toutes les significations de DNN présentes dans l’organisation de l’utilisateur.

> [!NOTE]
> Les utilisateurs doivent entrer une requête qui inclut les *Mots clés* spécifiés de l’acronyme pour déclencher les réponses correspondantes. Les requêtes d’acronyme ne sont pas sensibles à la casse.

## <a name="set-up-acronyms-answers"></a>Configurer des acronymes pour les réponses

Dans le [Centre d’administration 365 de Microsoft](https://admin.microsoft.com), accédez à [**acronymes**](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/acronyms), puis sélectionnez **Ajouter un acronyme**.

Microsoft Search interroge deux sources de données pour fournir des informations d’acronymes aux recherches des utilisateurs :

1. **Administrateurs-organisée**. Fourni par les administrateurs informatiques dans le [Centre d’administration](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/acronyms).
2. **Système-organisée**. Découvertes par Microsoft Search à partir des courriers électroniques et des documents des utilisateurs et des données accessibles au public au sein de l’organisation.

### <a name="set-up-admin-curated-acronyms"></a>Configurer des acronymes organisée par l’administrateur

Les administrateurs de recherche peuvent ajouter des acronymes dans l' [onglet acronymes](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/acronyms) du  [Centre d’administration de Microsoft Search](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch). Vous pouvez ajouter des acronymes à partir de n’importe quel site ou référentiel interne vers le centre d’administration. Ces acronymes peuvent être ajoutés à l’état **publié** ou **Brouillon** :

**État publié**. Les acronymes sont disponibles pour les utilisateurs de l’organisation via Microsoft Search.

> [!NOTE]
> Il peut falloir jusqu’à trois jours pour que les acronymes ajoutés à l’État publié soient disponibles dans Microsoft Search.

**État Brouillon**. Si vous souhaitez examiner un acronyme avant de le rendre disponible dans Microsoft Search, vous pouvez l’ajouter à l’état Brouillon. Les acronymes de l’état Brouillon n’apparaîtront pas dans les résultats de la recherche. Vous devrez déplacer l’acronyme vers l’État publié pour qu’il apparaisse dans les résultats de la recherche.

Vous pouvez ajouter des acronymes individuellement ou les importer par bloc dans un fichier CSV. Téléchargez un fichier CSV avec les champs indiqués dans le tableau suivant :

| Acronyme (obligatoire) | Expansion (obligatoire) | Description  | Source | État (obligatoire) |
| --------- | --------- | ---------- | --------- |--------- |
| *439* | *Abréviation orthographiée* |  | *URL* | *Publié ou brouillon* |

### <a name="csv-fields"></a>Champs CSV

**Acronyme**. Contient la forme courte ou l’acronyme réel. Par exemple, *DNN*.

**Expansion**. Contient l’expansion de l’acronyme. Il s’agit par exemple d’un *réseau neuronal profond*.

**Description**. Brève description de l’acronyme qui donne aux utilisateurs plus d’informations sur l’acronyme et son expansion. Par exemple, *un réseau neuronal profond est un réseau neuronal avec un certain niveau de complexité, un réseau neuronal avec plus de deux couches*.

**Source**. URL de la page ou du site Web où vous souhaitez que les utilisateurs accèdent à des informations supplémentaires sur l’acronyme.

**État**. Ce champ peut prendre deux valeurs :

- **Brouillon**. Ajoute l’acronyme à l’état Brouillon.
- **Publié**. Ajoute l’acronyme à l’État publié et le rend disponible dans Microsoft Search.

### <a name="system-curated-acronyms"></a>Acronymes organisée par le système

Il peut être difficile pour les administrateurs d’ajouter tous les acronymes utilisés dans une organisation aux réponses. Cette fonctionnalité peut trouver des acronymes que les administrateurs de recherche ne tiennent pas compte de. Pour ce faire, Microsoft Search identifie et organise les acronymes de ces sources :

- Courriels des utilisateurs
- Documents dans [SharePoint](https://products.office.com/sharepoint/collaboration), [Microsoft OneDrive]( https://onedrive.live.com/about/)et [Microsoft OneNote](https://www.onenote.com/)
- Documents publics au sein de l’organisation auxquels les utilisateurs ont accès dans SharePoint, OneDrive ou OneNote

Microsoft Search garantit que seuls les utilisateurs disposant d’autorisations d’accès à un document peuvent voir les acronymes qui sont découverts à partir de celui-ci. Lorsqu’un acronyme est trouvé dans la boîte aux lettres d’un utilisateur, seul cet utilisateur peut voir cet acronyme.

> [!NOTE]
> Aucune configuration n’est nécessaire pour les acronymes organisée par l’administrateur.

## <a name="frequently-asked-questions"></a>Questions fréquemment posées

**Q : comment les données ordonnées par l’administrateur et celles du système sont-elles classées ?**

**A :** Le classement des résultats peut varier d’une personne à l’autre lorsque les résultats sont personnalisés pour chaque utilisateur. Aucune de ces catégories n’aura toujours priorité sur l’autre.

**Q : combien de temps faut-il pour que les acronymes administratifs soient visibles dans Microsoft Search après leur publication ?**

**A :**  Trois jours sont nécessaires pour que les acronymes ajoutés à l’État publié soient disponibles dans Microsoft Search.

**Q : comment les utilisateurs déclenchent-ils les réponses ?**

**R**: pour obtenir les réponses des acronymes, les utilisateurs doivent entrer des modèles de requête spécifiques dans une zone de **recherche** [Bing](https://bing.com), [SharePoint](https://products.office.com/sharepoint/collaboration)ou [Office 365](https://Office.com) .

**Q : combien de temps faut-il pour que les acronymes système s’affichent lorsque vous recevez ou envoyez un nouveau message électronique ou un nouveau document ?**

**A :** Les acronymes figurant dans un nouveau message électronique ou dans un nouveau document prennent jusqu’à sept jours pour apparaître dans les résultats de Microsoft Search.

**Q : est-ce que les documents doivent être dans un format spécifique pour que l’exploration les récupère ?**

**A :** Nbre. Nous prenons en charge tous les types de fichiers, à l’exception des fichiers d’image, de dossiers et zip.

**Q : Microsoft va-t-il découvrir des acronymes de documents dans toutes les langues ?**

**A**: Microsoft prend uniquement en charge l’exploration des documents en anglais. La prise en charge d’autres langues sera ajoutée en plusieurs phases.

**Q : que se passe-t-il si mon organisation ne souhaite pas afficher d’acronymes système ? Puis-je arrêter l’affichage de ce type d’acronyme dans mes résultats de recherche ?**

**A**: pour désactiver l’affichage des acronymes par le système dans les résultats de la recherche, créez un ticket de support client en suivant les instructions indiquées sur [contacter le support technique pour les produits métiers](https://docs.microsoft.com/office365/admin/contact-support-for-business-products?redirectSourcePath=%252f%252farticle%252fContact-Office-365-for-business-support-32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b&view=o365-worldwide&tabs=online#BKMK_call_support).
Une fois que vous avez créé un ticket de support, il prend jusqu’à 48 heures pour que les acronymes du système cessent de s’afficher dans les résultats de la recherche.
