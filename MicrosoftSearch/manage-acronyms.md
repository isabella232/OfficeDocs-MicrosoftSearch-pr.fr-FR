---
title: Gérer les réponses acronymes dans Recherche Microsoft
ms.author: rakkum
author: rakeshMSFT
manager: jeffkizn
ms.audience: Admin
ms.topic: article
ms.service: mssearch
ms.localizationpriority: medium
search.appverid:
- BFB160
- MET150
- MOE150
description: Créer et mettre à jour des réponses acronymes dans Recherche Microsoft
ms.openlocfilehash: b7b3272ba98bbce7d43562811389df0a35e9f7a2
ms.sourcegitcommit: bb99601a7bd0f16dde7b271de516465d134e5bac
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/08/2021
ms.locfileid: "58973660"
---
# <a name="manage-acronyms-answers-in-microsoft-search"></a>Gérer les réponses acronymes dans Recherche Microsoft

Les utilisateurs utilisent souvent des acronymes et des abréviations peu familiers utilisés par leur organisation ou leur équipe. Les conditions propres aux organisations ou aux équipes peuvent être nouvelles pour les personnes qui passe d’une équipe à une autre, qui travaillent avec des équipes partenaires internes ou qui sont nouvelles dans l’organisation.

Les organisations n’ont pas toujours une seule référence pour leur terminologie standard. L’absence d’une référence unique rend difficile la recherche de définitions pour ces acronymes. Recherche Microsoft résoudre ce problème avec les acronymes.

## <a name="what-users-experience"></a>Expérience des utilisateurs

Recherche Microsoft utilisateurs peuvent obtenir des définitions avec des acronymes dans [Bing,](https://Bing.com) [SharePoint,](https://products.office.com/sharepoint/collaboration) [Office 365,](https://Office.com)Outlook sur le web, Outlook Mobile (Android) et Teams Mobile (iOS et Android). Dans la zone **de** recherche, les utilisateurs entrent des requêtes telles que les exemples suivants :

- *Qu’est-ce que* DNN
- *Définir* DNN
- Définition *DNN*
- *Expand* DNN
- Développement *DNN*
- *Signification de* DNN
- DNN *signifie*
- DNN *signifie «* DNN

Le résultat inclut toutes les significations de DNN présentes au sein de l’organisation de l’utilisateur.

> [!NOTE]
> Les utilisateurs doivent entrer une requête qui inclut les mots clés *spécifiés* de l’acronyme pour déclencher ses réponses correspondantes. Les requêtes Acronym ne sont pas sensibles à la cas.

## <a name="set-up-acronyms-answers"></a>Configurer les réponses acronymes

Dans la [Centre d'administration Microsoft 365](https://admin.microsoft.com), sélectionnez [**Acronymes,**](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/acronyms)puis **sélectionnez Ajouter un acronyme**.

Recherche Microsoft deux sources de données pour fournir des réponses acronymes aux recherches des utilisateurs :

1. **Organisé par l’administrateur.** Fourni par les administrateurs informatiques dans le [Centre d’administration.](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/acronyms)
2. **Organisé par le système**. Découverte par les Recherche Microsoft des e-mails et des documents des utilisateurs, ainsi que des données publiquement disponibles au sein de l’organisation.

### <a name="set-up-admin-curated-acronyms"></a>Configurer les acronymes organisés par l’administrateur

Les administrateurs de recherche peuvent ajouter des acronymes sous l’onglet [Acronymes](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/acronyms) [dans Recherche Microsoft centre d’administration.](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch) Vous pouvez ajouter des acronymes de n’importe quel site ou référentiel interne au Centre d’administration. Ces acronymes peuvent être ajoutés à l’état **Publié** **ou** Brouillon :

**État publié**. Les acronymes sont disponibles pour les utilisateurs de l’organisation via Recherche Microsoft.

> [!NOTE]
> Il faut jusqu’à un jour pour que les acronymes ajoutés à l’état publié deviennent disponibles dans Recherche Microsoft.

**État brouillon**. Si vous souhaitez passer en revue un acronyme avant de le rendre disponible dans Recherche Microsoft, vous pouvez ajouter l’acronyme dans un état Brouillon. Les acronymes dans l’état Brouillon n’apparaissent pas dans les résultats de la recherche. Vous devrez déplacer l’acronyme vers l’état Publié pour qu’il apparaisse dans les résultats de la recherche.

**État exclu**. Si vous souhaitez empêcher l’apparition d’un acronyme dans Recherche Microsoft, utilisez **l’acronyme** Exclure pour l’ajouter. Pour empêcher l’exclusion d’un acronyme, vous devez supprimer l’acronyme exclu et l’ajouter ou vérifier qu’il figure dans votre liste publiée.

Vous pouvez ajouter des acronymes individuellement ou en bloc pour les importer dans un fichier CSV. Télécharger fichier CSV avec les champs indiqués dans le tableau suivant :

| Acronyme (obligatoire) | Signifie (obligatoire) | Url | Description  | État (obligatoire) | Dernière modification | Dernière modification par | ID |
| --------- | --------- | --------- | ---------- | --------- |--------- |--------- |--------- |
| *XXX* | *Abréviation orthographie* | *Source* |  | *Publié, Brouillon ou Exclu* |  |  |  |

### <a name="csv-fields"></a>Champs CSV

**Acronyme**. Contient la forme courte ou l’acronyme réel. Par exemple, *DNN*.

**Signifie**. Contient la définition de l’acronyme. Par exemple, *le réseau neuronal profond*.

**Description**. Brève description de l’acronyme qui donne aux utilisateurs plus d’informations sur l’acronyme et sa définition. Par exemple, un réseau neuronal profond est un réseau neuronal avec un certain niveau de complexité, un réseau neuronal de plus *de deux couches.*

**Source**. URL de la page ou du site web où vous souhaitez que les utilisateurs recherchent plus d’informations sur l’acronyme.

**État**. Ce champ peut prendre deux valeurs :

- **Brouillon**. Ajoute l’acronyme à l’état Brouillon.
- **Publié**. Ajoute l’acronyme à l’état Publié et le rend disponible Recherche Microsoft.
- **Exclu**. Ajoute l’acronyme à l’état Exclu et l’empêche d’apparaître dans Recherche Microsoft.

### <a name="system-curated-acronyms"></a>Acronymes organisés par le système

Il peut être difficile pour les administrateurs d’ajouter tous les acronymes utilisés au sein d’une organisation aux réponses. Cette fonctionnalité peut trouver des acronymes que les administrateurs de recherche ne connaissent même pas. Pour ce faire, Recherche Microsoft découvrir et organiser les acronymes à partir de ces sources :

- Courriers électroniques des utilisateurs
- Documents dans [SharePoint,](https://products.office.com/sharepoint/collaboration) [Microsoft OneDrive]( https://onedrive.live.com/about/)et [Microsoft OneNote](https://www.onenote.com/)
- Documents publics au sein de l’organisation à qui les utilisateurs ont accès SharePoint, OneDrive ou OneNote

Recherche Microsoft s’assure que seuls les utilisateurs ayant accès et des autorisations à un document peuvent voir les acronymes qui y sont découverts. Lorsqu’un acronyme est trouvé dans la boîte aux lettres d’un utilisateur, seul cet utilisateur peut voir cet acronyme.

> [!NOTE]
> Aucune configuration n’est nécessaire pour les acronymes organisés par le système.

## <a name="frequently-asked-questions"></a>Foire aux questions

**Q : Comment les données organisées par l’administrateur et le système sont-elles classées ?**

**R :** Le classement des résultats peut varier d’une personne à l’autre, car les résultats sont personnalisés pour chaque utilisateur. Aucune de ces catégories ne sera toujours prioritaire sur l’autre.

**Q : Comment les utilisateurs déclenchent-ils des réponses aux acronymes ?**

**R :** Pour obtenir des réponses aux acronymes, les utilisateurs doivent entrer des modèles de requête spécifiques dans une zone de recherche [Bing,](https://bing.com) [SharePoint,](https://products.office.com/sharepoint/collaboration) [Office 365,](https://Office.com)Outlook sur le web, Outlook Mobile (Android)  ou Teams Mobile (iOS et Android).

**Q : Les utilisateurs peuvent-ils entrer uniquement l’acronyme lors de la recherche ?**

**R :** Sur Bing, les utilisateurs peuvent désormais trouver des réponses acronymes en recherchant simplement un acronyme, un mot clé n’est plus nécessaire. Cette même expérience sera activée pour d’autres points d’Recherche Microsoft par phases.

**Q : Combien de temps faut-il pour que les acronymes organisés par l’administrateur soient visibles dans Recherche Microsoft après leur publication ?**

**R :** Il faut jusqu’à un jour pour que les acronymes ajoutés à l’état publié deviennent disponibles dans Recherche Microsoft.

**Q : Combien de temps faut-il pour que les acronymes organisés par le système apparaissent après la réception ou l’envoi d’un nouveau message électronique ou document ?**

**R :** Les acronymes trouvés dans un nouveau message électronique ou document prennent jusqu’à sept jours pour apparaître dans Recherche Microsoft résultats.

**Q : Que se passe-t-il lorsqu’un acronyme est à la fois exclu et publié ?**

**R :** L’acronyme exclu est prioritaire et empêche l’acronyme publié d’apparaître dans les résultats de la recherche. Il ne supprime pas ou ne supprime pas l’acronyme publié.

**Q : Combien de temps faut-il pour qu’un acronyme soit exclu des Recherche Microsoft résultats ?**

**R :** L’apparition d’un acronyme exclu dans les résultats de la recherche prend jusqu’à un jour.

**Q : Pour les acronymes organisés par le système, les documents doivent-ils être dans un format spécifique ?**

**R :** Non. Nous prise en charge tous les types de fichiers à l’exception des fichiers image, dossier et zip.

**Q : Microsoft découvrira-t-il les acronymes des documents dans toutes les langues ?**

**R :** Microsoft prend uniquement en charge les acronymes organisés par le système à partir de documents en anglais, en espagnol, en français, en italien, en allemand et en portugais. La prise en charge d’autres langues sera ajoutée par phases.

**Q : Que se passe-t-il si mon organisation ne souhaite pas afficher les acronymes organisés par le système ? Puis-je arrêter d’afficher ce type d’acronyme dans mes résultats de recherche ?**

**R :** Pour désactiver l’affichage des acronymes organisés par le système dans les résultats de la recherche, créez un ticket de support client en suivant les instructions du support technique pour les [produits d’entreprise.](/microsoft-365/admin/contact-support-for-business-products)
Après avoir créé un ticket de support, l’apparition des acronymes organisés par le système dans les résultats de la recherche prend jusqu’à 48 heures.
