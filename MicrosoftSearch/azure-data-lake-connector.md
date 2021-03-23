---
title: Connecteur Azure Data Lake Graph pour Microsoft Search (recherche Microsoft)
ms.author: mecampos
author: mecampos
manager: umas
audience: Admin
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: Configurer le connecteur Graph Azure Data Lake Storage Gen2 pour Microsoft Search (recherche Microsoft)
ms.openlocfilehash: 37a035b3de9dc217f885f193992d1e74a675fb35
ms.sourcegitcommit: 5df252e6d0bd67bb1b4c59418aceca8369f5fe42
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51031322"
---
<!---Previous ms.author: monaray --->

# <a name="azure-data-lake-storage-gen2-graph-connector"></a>Connecteur Graph Azure Data Lake Storage Gen2

Le connecteur Graph Azure Data Lake Storage Gen2 permet aux utilisateurs de votre organisation de rechercher des fichiers stockés dans des comptes de stockage [d’objets blob Azure](/azure/storage/blobs/storage-blobs-introduction) et [Azure Data Lake Gen 2 Storage.](/azure/storage/blobs/data-lake-storage-introduction)

> [!NOTE]
> Lisez [**l’article Configurer votre connecteur Graph**](configure-connector.md) pour comprendre les instructions générales d’installation des connecteurs Graph.

Cet article est réservé à toute personne qui configure, exécute et surveille un connecteur Azure Data Lake Storage Gen2. Il complète le processus de configuration général et affiche des instructions qui s’appliquent uniquement au connecteur Azure Data Lake Storage Gen2. Cet article inclut également des informations sur [les limitations.](#limitations)

Dans l’article, nous utilisons Le stockage *Azure* comme terme générique pour le stockage [d’objets blob Azure](/azure/storage/blobs/storage-blobs-introduction) et le stockage Azure Data Lake Gen [2.](/azure/storage/blobs/data-lake-storage-introduction)

## <a name="step-1-add-a-graph-connector-in-the-microsoft-365-admin-center"></a>Étape 1 : Ajouter un connecteur Graph dans le Centre d’administration Microsoft 365

Suivez les [instructions d’installation générales.](./configure-connector.md)
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-2-name-the-connection"></a>Étape 2 : Nommer la connexion

Suivez les [instructions d’installation générales.](./configure-connector.md)
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-3-configure-the-connection-settings"></a>Étape 3 : Configurer les paramètres de connexion

Entrez votre chaîne de connexion de stockage principale. Cette chaîne est nécessaire pour autoriser l’accès à votre compte de stockage. Pour rechercher votre chaîne de connexion, accédez au portail [Azure](https://ms.portal.azure.com/#home) et accédez à la section **Clés** de votre compte de stockage Azure approprié.

Si vous préférez ne pas fournir **accountKey** (paramètre dans la chaîne de connexion de stockage principale), accordez l’accès à notre service Graph Connectors pour les rôles suivants :

* Lecteur de données blob de stockage
* Collaborateur de données de file d’attente de stockage
* Délégant d’objets blob de stockage

Accédez à **l’onglet Contrôle** d’accès de votre compte de stockage Azure et suivez les instructions ci-après pour accorder l’accès à l’application suivante :

* **ID** d’application first party : 56c1da01-2129-48f7-9355-af6d59d42766
* **Nom de l’application de première partie :** Graph Connector Service

### <a name="storage-account-and-queue-notifications-optional"></a>Notifications de compte de stockage et de file d’attente (facultatif)

La prise en charge du traitement des modifications en temps réel dans le service Graph Connectors peut être ajoutée à l’avenir. Dans ce cas, nous allons surveiller les notifications de modification du stockage Azure stockées dans une file d’attente. Vous devez créer une file d’attente dans le même compte que votre compte de stockage Azure.

Après avoir créé une file d’attente, rendez-vous dans l’onglet **Événements** de la page de file d’attente pour configurer **l’abonnement aux événements.** Choisissez tous les événements Blob que la file d’attente recevra et connectez-la au compte de stockage Azure.

## <a name="step-4-assign-property-labels"></a>Étape 4 : Attribuer des étiquettes de propriété

Vous pouvez affecter une propriété source à chaque étiquette en choisissant dans un menu d’options. Bien que cette étape ne soit pas obligatoire, le fait d’avoir des étiquettes de propriétés améliorera la pertinence de la recherche et garantira de meilleurs résultats de recherche pour les utilisateurs finaux.

## <a name="step-5-manage-schema"></a>Étape 5 : Gérer le schéma

Dans **l’écran** Gérer le schéma, vous pouvez modifier les attributs de schéma associés aux propriétés, les options sont **Requête,** **Rechercher,** Récupérer **et** **Affiner**. Vous pouvez également ajouter des alias facultatifs et choisir la **propriété Content.**

## <a name="step-6-manage-search-permissions"></a>Étape 6 : Gérer les autorisations de recherche

### <a name="azure-data-lake-gen-2"></a>Azure Data Lake Gen 2

Vous pouvez choisir d’ingèrer les listes de contrôle d’accès à partir de votre compte de stockage [Azure Data Lake Gen 2.](/azure/storage/blobs/data-lake-storage-introduction) Lorsque ces autorisations de recherche sont définies, le contenu de recherche est découpé en fonction des autorisations de l’utilisateur qui s’est inscrit [dans Azure Active Directory](/azure/active-directory/). Vous pouvez également choisir de rendre tout le contenu indexé à partir de votre compte de stockage visible par tous les membres de votre organisation. Dans ce cas, tous les membres de votre organisation auront accès à toutes les données de votre compte de stockage.

Le connecteur Azure Data Lake Storage Gen2 Graph prend en charge les autorisations de recherche visibles par tout le monde **ou** uniquement les personnes ayant accès à cette source **de données.** Les données indexées qui apparaissent dans les résultats de la recherche peuvent être visibles par les utilisateurs de l’organisation qui ont accès à chaque élément.

### <a name="azure-blob-storage"></a>Stockage Blob Azure

Pour une connexion au [stockage Blob Azure,](/azure/storage/blobs/storage-blobs-introduction)tout le contenu indexé à partir de la source configurée est visible par tous les membres de votre organisation. Les listes de contrôle d’accès ne sont pas pris en charge au niveau blob dans le stockage d’objets blob Azure.

## <a name="step-7-set-the-refresh-schedule"></a>Étape 7 : Définir la planification de l’actualisation

Dans **l’écran Paramètres** d’actualisation, vous pouvez définir l’intervalle d’analyse incrémentielle et l’intervalle d’analyse complet. Les intervalles par défaut pour le connecteur Azure Data Lake Storage Gen2 sont de 15 minutes pour une analyse incrémentielle et d’une semaine pour une analyse complète.

## <a name="step-8-review-connection"></a>Étape 8 : Examiner la connexion

Suivez les [instructions d’installation générales.](./configure-connector.md)
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

<!---## Troubleshooting-->
<!---Insert troubleshooting recommendations for this data source-->

## <a name="limitations"></a>Limites

Une connexion publiée pour le stockage d’objets blob Azure ne peut pas être reconfigurée pour la source Azure Data Lake Storage Gen2 et inversement. Dans de tels scénarios, il est recommandé de configurer une nouvelle connexion.

En outre, la taille des fichiers doit être inférieure ou inférieure à 4 Mo pour qu’ils soient analyser. Les types de fichiers actuellement pris en charge sont :

* Word (docx, .docm, .dotx, .dotm)
* PowerPoint (.pptm, .pptx, .potm, .potx, .ppam, .ppsm, .ppsx)
* Excel (.xlsx, .xlsm)
* Formats Office hérités (.doc, .dot, etc.)
* Texte (.txt)
* HTML
* PDF

Les fichiers binaires tels que les images (.jpg, .bmp, etc.) ne sont pas pris en charge. Par exemple, si un fichier .docx contient uniquement des images, il peut être ignoré car il n’a pas renvoyé de contenu.