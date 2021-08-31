---
title: Connecteur d’Graph Azure Data Lake pour Recherche Microsoft
ms.author: mecampos
author: mecampos
manager: umas
audience: Admin
ms.audience: Admin
ms.topic: article
ms.service: mssearch
ms.localizationpriority: medium
search.appverid:
- BFB160
- MET150
- MOE150
description: Configurer le connecteur Azure Data Lake Stockage Gen2 Graph pour Recherche Microsoft
ms.openlocfilehash: f60de4252e514f84bc92daf4ea65c535cf40a13d
ms.sourcegitcommit: cc9d743bcf5e998720ce9cd6eefb4061d913dc65
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/30/2021
ms.locfileid: "58701398"
---
<!---Previous ms.author: monaray --->

# <a name="azure-data-lake-storage-gen2-graph-connector"></a>Connecteur d’Graph Azure Data Lake Stockage Gen2

Le connecteur Azure Data Lake Stockage Gen2 Graph permet aux utilisateurs de votre organisation de rechercher des fichiers stockés dans des comptes [Azure Blob Stockage](/azure/storage/blobs/storage-blobs-introduction) et [Azure Data Lake Gen 2 Stockage.](/azure/storage/blobs/data-lake-storage-introduction)

> [!NOTE]
> Lisez [**l’article Configurer votre connecteur Graph pour**](configure-connector.md) comprendre les instructions générales Graph d’installation des connecteurs.

Cet article est réservé à toute personne qui configure, exécute et surveille un connecteur Azure Data Lake Stockage Gen2. Il complète le processus de configuration générale et affiche des instructions qui s’appliquent uniquement au connecteur Azure Data Lake Stockage Gen2. Cet article inclut également des informations sur [les limitations.](#limitations)

Dans l’article, nous utilisons *stockage Azure* comme terme générique pour [Azure Blob Stockage](/azure/storage/blobs/storage-blobs-introduction) et Azure Data Lake Gen [2 Stockage](/azure/storage/blobs/data-lake-storage-introduction).

## <a name="step-1-add-a-graph-connector-in-the-microsoft-365-admin-center"></a>Étape 1 : Ajouter un connecteur Graph dans le Centre d’administration Microsoft 365

Suivez les [instructions d’installation générales.](./configure-connector.md)
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-2-name-the-connection"></a>Étape 2 : Nommer la connexion

Suivez les [instructions d’installation générales.](./configure-connector.md)
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-3-configure-the-connection-settings"></a>Étape 3 : Configurer les paramètres de connexion

Entrez votre chaîne de connexion de stockage principale. Cette chaîne est nécessaire pour autoriser l’accès à votre compte de stockage. Pour rechercher votre chaîne de connexion, accédez au portail [Azure](https://ms.portal.azure.com/#home) et accédez à la section **Clés** de votre compte stockage Azure approprié.

Si vous préférez ne pas fournir la clé **AccountKey** (paramètre dans la chaîne de connexion de stockage principale), accordez l’accès à notre service Graph Connectors pour les rôles suivants :

* Stockage Lecteur de données Blob
* Stockage Collaborateur de données de file d’attente
* Stockage Délégant blob

Accédez à **l’onglet Contrôle** d’accès de votre compte stockage Azure, puis suivez les instructions ci-après pour accorder l’accès à l’application suivante :

* **ID** d’application first party : 56c1da01-2129-48f7-9355-af6d59d42766
* **First Party App Name:** Graph Connector Service

### <a name="storage-account-and-queue-notifications-optional"></a>Stockage de compte et de file d’attente (facultatif)

Prise en charge du traitement des modifications en temps réel dans Graph service connecteurs peut être ajouté à l’avenir. Dans ce cas, nous allons surveiller les stockage Azure notifications de modification stockées dans une file d’attente. Vous devez créer une file d’attente dans le même compte que votre stockage Azure client.

Après avoir créé une file d’attente, rendez-vous dans l’onglet **Événements** de la page de file d’attente pour configurer **l’abonnement aux événements.** Choisissez tous les événements Blob que la file d’attente recevra et connectez-la au compte stockage Azure client.

## <a name="step-4-assign-property-labels"></a>Étape 4 : Attribuer des étiquettes de propriété

Vous pouvez affecter une propriété source à chaque étiquette en choisissant dans un menu d’options. Bien que cette étape ne soit pas obligatoire, le fait d’avoir des étiquettes de propriétés améliorera la pertinence de la recherche et garantira de meilleurs résultats de recherche pour les utilisateurs finaux.

## <a name="step-5-manage-schema"></a>Étape 5 : Gérer le schéma

Dans **l’écran** Gérer le schéma, vous pouvez modifier les attributs de schéma associés aux propriétés, les options sont **Requête,** **Rechercher,** Récupérer **et** **Affiner**. Vous pouvez également ajouter des alias facultatifs et choisir la **propriété Content.**

## <a name="step-6-manage-search-permissions"></a>Étape 6 : Gérer les autorisations de recherche

### <a name="azure-data-lake-gen-2"></a>Azure Data Lake Gen 2

Vous pouvez choisir d’ingèrer les listes de contrôle d’accès à partir de votre compte [Azure Data Lake Gen 2 Stockage.](/azure/storage/blobs/data-lake-storage-introduction) Lorsque ces autorisations de recherche sont définies, le contenu de recherche est découpé en fonction des autorisations de l’utilisateur Azure Active Directory [.](/azure/active-directory/) Vous pouvez également choisir de rendre tout le contenu indexé à partir de votre compte de stockage visible par tous les membres de votre organisation. Dans ce cas, tous les membres de votre organisation auront accès à toutes les données de votre compte de stockage.

Le connecteur azure Data Lake Stockage Gen2 Graph prend en charge les autorisations de recherche visibles par tout le monde **ou** uniquement les personnes ayant accès à cette source **de données.** Les données indexées qui apparaissent dans les résultats de la recherche peuvent être visibles par les utilisateurs de l’organisation qui ont accès à chaque élément.

### <a name="azure-blob-storage"></a>Stockage Blob Azure

Pour une connexion à [Azure Blob Stockage](/azure/storage/blobs/storage-blobs-introduction), tout le contenu indexé à partir de la source configurée est visible par tous les membres de votre organisation. Les listes de contrôle d’accès ne sont pas pris en charge au niveau blob dans Azure Blob Stockage.

## <a name="step-7-set-the-refresh-schedule"></a>Étape 7 : Définir la planification de l’actualisation

Dans **l’écran Actualiser Paramètres,** vous pouvez définir l’intervalle d’analyse incrémentielle et l’intervalle d’analyse complet. Les intervalles par défaut pour le connecteur Azure Data Lake Stockage Gen2 sont de 15 minutes pour une analyse incrémentielle et d’une semaine pour une analyse complète.

## <a name="step-8-review-connection"></a>Étape 8 : Examiner la connexion

Suivez les [instructions d’installation générales.](./configure-connector.md)
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

<!---## Troubleshooting-->
<!---Insert troubleshooting recommendations for this data source-->

## <a name="limitations"></a>Limites

Une connexion publiée pour Azure Blob Stockage ne peut pas être reconfigurée pour Azure Data Lake Stockage source Gen2 et inversement. Dans de tels scénarios, il est recommandé de configurer une nouvelle connexion.

En outre, la taille des fichiers doit être inférieure ou inférieure à 4 Mo pour qu’ils soient analyser. Les types de fichiers actuellement pris en charge sont :

* Word (docx, .docm, .dotx, .dotm)
* PowerPoint (.pptm, .pptx, .potm, .potx, .ppam, .ppsm, .ppsx)
* Excel (.xlsx, .xlsm)
* Formats Office hérités (.doc, .dot, etc.)
* Texte (.txt)
* HTML
* PDF

Les fichiers binaires tels que les images (.jpg, .bmp, etc.) ne sont pas pris en charge. Par exemple, si un fichier .docx contient uniquement des images, il peut être ignoré car il n’a pas renvoyé de contenu.