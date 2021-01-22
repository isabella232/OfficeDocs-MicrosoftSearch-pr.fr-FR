---
title: Connecteur Azure Data Lake pour Microsoft Search (recherche Microsoft)
ms.author: monaray
author: monaray97
manager: shohara
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: Configurer le connecteur Azure Data Lake Storage Gen2 pour Microsoft Search (recherche Microsoft)
ms.openlocfilehash: 8891c9a1fdf5397c397a941b5131f014db9e7a54
ms.sourcegitcommit: 597c338bf9c1c425747ac74a9a1ae57c5e8957ce
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/21/2021
ms.locfileid: "49920721"
---
# <a name="azure-data-lake-storage-gen2-connector"></a>Connecteur Azure Data Lake Storage Gen2

Avec le connecteur Azure Data Lake Storage Gen2, les utilisateurs de votre organisation peuvent rechercher des fichiers stockés dans des comptes de stockage [Blob Azure](https://docs.microsoft.com/azure/storage/blobs/storage-blobs-introduction) et [Azure Data Lake Gen 2 Storage.](https://docs.microsoft.com/azure/storage/blobs/data-lake-storage-introduction)

Cet article est réservé aux administrateurs [Microsoft 365](https://www.microsoft.com/microsoft-365) ou à toute personne qui configure, exécute et surveille un connecteur Azure Data Lake Storage Gen2. Il donne une vue d’ensemble de la configuration, des fonctionnalités, des limitations et des techniques de dépannage du connecteur. Dans l’article, nous utilisons Le stockage *Azure* comme terme générique pour le stockage [d’objets blob Azure](https://docs.microsoft.com/azure/storage/blobs/storage-blobs-introduction) et le stockage Azure Data Lake Gen [2.](https://docs.microsoft.com/azure/storage/blobs/data-lake-storage-introduction)

## <a name="connect-to-a-data-source"></a>Connexion à une source de données

### <a name="primary-storage-connection-string"></a>Chaîne de connexion de stockage principale

Dans **l’écran Authentification et config,** fournissez la chaîne de connexion de stockage principale. Cette chaîne est nécessaire pour autoriser l’accès à votre compte de stockage. Pour rechercher votre chaîne de connexion, accédez au portail [Azure](https://ms.portal.azure.com/#home) et accédez à la section **Clés** de votre compte de stockage Azure approprié. Copiez et collez la chaîne de connexion dans le champ approprié à l’écran.

Si vous ne préférez pas fournir la clé **AccountKey** (un paramètre dans la chaîne de connexion de stockage principale), vous devez accorder l’accès à notre service Graph Connectors pour les rôles suivants. (Cette fonctionnalité est uniquement prise en charge pour le stockage hiérarchique. Le stockage blob traditionnel doit fournir AccountKey.)
* Lecteur de données blob de stockage
* Collaborateur de données de file d’attente de stockage
* Délégant blob de stockage

Accédez à **l’onglet Contrôle** d’accès de votre compte de stockage Azure et suivez les instructions ci-après pour accorder l’accès à l’application suivante :

* **ID d’application** first party : 56c1da01-2129-48f7-9355-af6d59d42766
* **Nom de l’application de première partie :** Graph Connector Service

### <a name="storage-account-and-queue-notifications-optional"></a>Notifications de compte de stockage et de file d’attente (facultatif)

La prise en charge du traitement des modifications en temps réel dans le service Graph Connectors peut être ajoutée à l’avenir. Dans ce cas, nous allons surveiller les notifications de modification du stockage Azure stockées dans une file d’attente. Vous devez créer une file d’attente dans le même compte que votre compte de stockage Azure.

Après avoir créé une file d’attente, rendez-vous dans l’onglet **Événements** de la page de file d’attente pour configurer **l’abonnement aux événements.** Choisissez tous les événements Blob que la file d’attente recevra et connectez-la au compte de stockage Azure.

## <a name="manage-search-permissions"></a>Gérer les autorisations de recherche

### <a name="azure-data-lake-gen-2"></a>Azure Data Lake Gen 2

Dans l’écran Gérer les **autorisations** de recherche, vous pouvez choisir d’ingèrer les listes de contrôle d’accès à partir de votre compte de stockage [Azure Data Lake Gen 2.](https://docs.microsoft.com/azure/storage/blobs/data-lake-storage-introduction) Lorsque ces autorisations de recherche sont définies, le contenu de recherche est découpé en fonction des autorisations attribuées à l’utilisateur [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/) qui recherche le contenu. Vous pouvez également choisir de rendre tout le contenu indexé à partir de votre compte de stockage visible par tous les membres de votre organisation. Dans ce cas, tous les membres de votre organisation auront accès à toutes les données de votre compte de stockage.

### <a name="azure-blob-storage"></a>Stockage Blob Azure

Pour une connexion au [stockage Blob Azure,](https://docs.microsoft.com/azure/storage/blobs/storage-blobs-introduction)tout le contenu indexé à partir de la source configurée est visible par tous les membres de votre organisation. Les listes de contrôle d’accès ne sont pas pris en charge au niveau blob dans le stockage d’objets blob Azure.

## <a name="search-permissions"></a>Autorisations de recherche

Le connecteur Azure Data Lake Storage Gen2  prend en charge les autorisations de recherche visibles par tout le monde ou uniquement par les personnes ayant **accès à cette source de données.** Les données indexées qui apparaissent dans les résultats de la recherche peuvent être visibles par tous les utilisateurs de l’organisation ou uniquement par les utilisateurs qui ont accès à chaque élément.

## <a name="assign-property-labels"></a>Attribuer des étiquettes de propriété

Vous pouvez affecter une propriété source à chaque étiquette en choisissant dans un menu d’options. Bien que cette étape ne soit pas obligatoire, le fait d’avoir des étiquettes de propriétés améliorera la pertinence de la recherche et garantira des résultats de recherche plus précis pour les utilisateurs finaux.

## <a name="manage-schema"></a>Gérer le schéma

Dans  l’écran Gérer le schéma, vous avez la possibilité de modifier les attributs de schéma **(utilisables** dans une **requête,** utilisables dans une requête, **récupérables** et utilisables dans une recherche dans une recherche) associés aux propriétés, d’ajouter des alias facultatifs et de choisir la propriété **Content.**

## <a name="set-the-refresh-schedule"></a>Définir la planification d’actualisation

Dans **l’écran Paramètres** d’actualisation, vous pouvez définir l’intervalle d’analyse incrémentielle et l’intervalle d’analyse complet. Les intervalles par défaut pour le connecteur Azure Data Lake Storage Gen2 sont de 15 minutes pour une analyse incrémentielle et d’une semaine pour une analyse complète.

## <a name="limitations"></a>Limites

Une connexion publiée pour le stockage d’objets blob Azure ne peut pas être reconfigurée pour la source Azure Data Lake Storage Gen2 et vice-versa. Dans de tels scénarios, il est recommandé de configurer une nouvelle connexion.
