---
title: Gérer les réponses acronymes dans Microsoft Search (recherche Microsoft)
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
description: Créer et mettre à jour les réponses acronymes dans Microsoft Search (recherche Microsoft)
ms.openlocfilehash: 5677ff6915c9e43e2559964c40086cb360a05db7
ms.sourcegitcommit: 5df252e6d0bd67bb1b4c59418aceca8369f5fe42
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51031367"
---
# <a name="manage-acronyms-answers-in-microsoft-search"></a>Gérer les réponses acronymes dans Microsoft Search (recherche Microsoft)

Les utilisateurs utilisent souvent des acronymes et des abréviations peu familiers utilisés par leur organisation ou leur équipe. Les conditions propres aux organisations ou aux équipes peuvent être nouvelles pour les personnes qui passe d’une équipe à une autre, qui travaillent avec des équipes partenaires internes ou qui sont nouvelles dans l’organisation.

Les organisations n’ont pas toujours une seule référence pour leur terminologie standard. L’absence d’une référence unique rend difficile la recherche de définitions ou d’extensions pour ces acronymes. Microsoft Search (recherche Microsoft) résout ce problème avec acronymes.

## <a name="what-users-experience"></a>Expérience des utilisateurs

Les utilisateurs de Recherche Microsoft peuvent obtenir des définitions avec des acronymes dans [Bing,](https://Bing.com) [SharePoint](https://products.office.com/sharepoint/collaboration)et [Office 365](https://Office.com). Dans la zone **de** recherche, les utilisateurs entrent des requêtes telles que les exemples suivants :

- *Qu’est-ce que* DNN
- *Définir* DNN
- Définition *DNN*
- *Expand* DNN
- Développement *DNN*
- *Signification de* DNN
- DNN *signifie*

Le résultat inclut toutes les significations de DNN présentes au sein de l’organisation de l’utilisateur.

> [!NOTE]
> Les utilisateurs doivent entrer une requête qui inclut les mots clés *spécifiés* de l’acronyme pour déclencher ses réponses correspondantes. Les requêtes Acronym ne sont pas sensibles à la cas.

## <a name="set-up-acronyms-answers"></a>Configurer les réponses acronymes

Dans le [Centre d’administration Microsoft 365,](https://admin.microsoft.com)sélectionnez [**Acronymes,**](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/acronyms)puis **sélectionnez Ajouter un acronyme.**

Recherche Microsoft interroge deux sources de données pour fournir des réponses acronymes aux recherches des utilisateurs :

1. **Organisé par l’administrateur.** Fourni par les administrateurs informatiques dans le [Centre d’administration.](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/acronyms)
2. **Organisé par le système**. Découvert par Microsoft Search (recherche Microsoft) à partir du courrier électronique et des documents des utilisateurs et des données publiquement disponibles au sein de l’organisation.

### <a name="set-up-admin-curated-acronyms"></a>Configurer des acronymes organisés par l’administrateur

Les administrateurs de recherche peuvent ajouter des acronymes sous [l’onglet Acronymes](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/acronyms) dans le Centre [d’administration Recherche Microsoft.](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch) Vous pouvez ajouter des acronymes de n’importe quel site ou référentiel interne au Centre d’administration. Ces acronymes peuvent être ajoutés à l’état **Publié** **ou** Brouillon :

**État publié**. Les acronymes sont disponibles pour les utilisateurs de l’organisation via Microsoft Search (recherche Microsoft).

> [!NOTE]
> La publication des acronymes ajoutés à l’état publié dans Microsoft Search (recherche Microsoft) peut prendre jusqu’à trois jours.

**État brouillon**. Si vous souhaitez passer en revue un acronyme avant de le rendre disponible dans Microsoft Search (recherche Microsoft), vous pouvez ajouter l’acronyme dans un état Brouillon. Les acronymes dans l’état Brouillon n’apparaissent pas dans les résultats de la recherche. Vous devez déplacer l’acronyme vers l’état Publié pour qu’il apparaisse dans les résultats de la recherche.

Vous pouvez ajouter des acronymes individuellement ou en bloc pour les importer dans un fichier CSV. Téléchargez un fichier CSV avec les champs indiqués dans le tableau suivant :

| Acronyme (obligatoire) | Expansion (obligatoire) | Url | Description  | État (obligatoire) | Dernière modification | Dernière modification par | ID |
| --------- | --------- | --------- | ---------- | --------- |--------- |--------- |--------- |
| *XXX* | *Abréviation orthographie* | *Source* |  | *Publié ou brouillon* |  |  |  |

### <a name="csv-fields"></a>Champs CSV

**Acronyme**. Contient le formulaire court ou l’acronyme réel. Par exemple, *DNN*.

**Expansion**. Contient l’extension de l’acronyme. Par exemple, *le réseau neuronal profond*.

**Description**. Brève description de l’acronyme qui donne aux utilisateurs plus d’informations sur l’acronyme et son développement. Par exemple, un réseau neuronal profond est un réseau neuronal avec un certain niveau de complexité, un réseau neuronal avec plus *de deux couches*.

**Source**. URL de la page ou du site web où vous souhaitez que les utilisateurs recherchent plus d’informations sur l’acronyme.

**État**. Ce champ peut prendre deux valeurs :

- **Brouillon**. Ajoute l’acronyme à l’état Brouillon.
- **Publié**. Ajoute l’acronyme à l’état Publié et le rend disponible dans Microsoft Search (recherche Microsoft).

### <a name="system-curated-acronyms"></a>Acronymes organisés par le système

Il peut être difficile pour les administrateurs d’ajouter tous les acronymes utilisés au sein d’une organisation aux réponses. Cette fonctionnalité peut trouver des acronymes que les administrateurs de recherche ne connaissent même pas. Pour ce faire, Microsoft Search (recherche Microsoft) découvre et organise les acronymes à partir de ces sources :

- Courriers électroniques des utilisateurs
- Documents dans [SharePoint,](https://products.office.com/sharepoint/collaboration) [Microsoft OneDrive]( https://onedrive.live.com/about/)et [Microsoft OneNote](https://www.onenote.com/)
- Documents publics au sein de l’organisation à qui les utilisateurs ont accès dans SharePoint, OneDrive ou OneNote

Microsoft Search (recherche Microsoft) permet de s’assurer que seuls les utilisateurs autorisées à accéder à un document peuvent voir les acronymes qui sont découverts à partir de celui-ci. Lorsqu’un acronyme est trouvé dans la boîte aux lettres d’un utilisateur, seul cet utilisateur peut voir cet acronyme.

> [!NOTE]
> Aucune configuration n’est nécessaire pour les acronymes organisés par l’administrateur.

## <a name="frequently-asked-questions"></a>Foire aux questions

**Q : Comment les données organisées par l’administrateur et le système sont-elles classées ?**

**R :** Le classement des résultats peut varier d’une personne à l’autre, car les résultats sont personnalisés pour chaque utilisateur. Aucune de ces catégories ne sera toujours prioritaire sur l’autre.

**Q : Combien de temps faut-il pour que les acronymes organisés par l’administrateur soient visibles dans Recherche Microsoft après leur publication ?**

**R :**  La publication des acronymes ajoutés à l’état publié dans Microsoft Search (recherche Microsoft) prend jusqu’à trois jours.

**Q : Comment les utilisateurs déclenchent-ils des réponses aux acronymes ?**

**R**: Pour obtenir des réponses aux acronymes, les utilisateurs doivent entrer des modèles de requête spécifiques dans une zone de recherche [Bing,](https://bing.com) [SharePoint](https://products.office.com/sharepoint/collaboration)ou [Office 365.](https://Office.com) 

**Q : Combien de temps faut-il pour que les acronymes organisés par le système apparaissent après la réception ou l’envoi d’un nouveau message électronique ou document ?**

**R :** Les acronymes trouvés dans un nouveau message électronique ou document prennent jusqu’à sept jours pour apparaître dans les résultats de recherche Microsoft.

**Q : Les documents doivent-ils être dans un format spécifique pour l’exploration pour les récupérer ?**

**R :** Non. Nous prise en charge tous les types de fichiers à l’exception des fichiers image, dossiers et zip.

**Q : Microsoft découvrira-t-il les acronymes des documents dans toutes les langues ?**

**R**: Microsoft prend uniquement en charge l’exploration à partir de documents en anglais. La prise en charge d’autres langues sera ajoutée par phases.

**Q : Que se passe-t-il si mon organisation ne souhaite pas afficher les acronymes organisés par le système ? Puis-je arrêter d’afficher ce type d’acronyme dans mes résultats de recherche ?**

**R**: pour désactiver l’affichage des acronymes organisés par le système dans les résultats de la recherche, créez un ticket de support client en suivant les instructions du support technique pour les [produits d’entreprise.](/microsoft-365/admin/contact-support-for-business-products)
Après avoir créé un ticket de support, l’apparition des acronymes organisés par le système dans les résultats de la recherche prend jusqu’à 48 heures.