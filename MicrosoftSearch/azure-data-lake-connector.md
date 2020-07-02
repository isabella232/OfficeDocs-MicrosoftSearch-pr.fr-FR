---
title: Connecteur Azure Data Lake pour Microsoft Search
ms.author: mounika.narayanan
author: monaray
manager: shohara
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: Configurer le connecteur Azure Data Lake Storage Gen2 pour Microsoft Search
ms.openlocfilehash: d6adabc6ea40b4385059f80375f49fb73e63e65b
ms.sourcegitcommit: 9ba062f8b632a74e56ad7ec4dffaa1d8dab57614
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/01/2020
ms.locfileid: "44996093"
---
# <a name="azure-data-lake-storage-gen2-connector"></a>Connecteur Azure Data Lake Storage Gen2

Avec le connecteur Azure Data Lake Storage Gen2, les utilisateurs de votre organisation peuvent rechercher des fichiers stockés dans les comptes de stockage [BLOB Azure](https://docs.microsoft.com/azure/storage/blobs/storage-blobs-introduction) et [Azure Data Lake Gen 2](https://docs.microsoft.com/azure/storage/blobs/data-lake-storage-introduction) .

Cet article est destiné aux administrateurs [365 de Microsoft](https://www.microsoft.com/microsoft-365) ou toute personne qui configure, exécute et surveille un connecteur Azure Data Lake Storage Gen2. Elle offre une vue d’ensemble de la configuration, des fonctionnalités, des limites et des techniques de résolution des problèmes des connecteurs. Dans cet article, nous utilisons *Azure Storage* comme terme générique pour le stockage d' [objets BLOB Azure](https://docs.microsoft.com/azure/storage/blobs/storage-blobs-introduction) et le [stockage Azure Data Lake Gen 2](https://docs.microsoft.com/azure/storage/blobs/data-lake-storage-introduction).

## <a name="connect-to-a-data-source"></a>Se connecter à une source de données
### <a name="primary-storage-connection-string"></a>Chaîne de connexion de stockage principal 
Sur l’écran **authentification et configuration** , fournissez la chaîne de connexion de stockage principal. Cette chaîne est requise pour autoriser l’accès à votre compte de stockage. Pour rechercher votre chaîne de connexion, accédez au [portail Azure](https://ms.portal.azure.com/#home) et accédez à la section **clés** de votre compte de stockage Azure approprié. Copiez et collez la chaîne de connexion dans le champ approprié à l’écran.

Si vous ne souhaitez pas fournir le **AccountKey** (un paramètre dans la chaîne de connexion de stockage principal), vous devrez accorder un accès en lecture à notre service de connecteurs Graph. Accédez à l’onglet **contrôle d’accès** de votre compte de stockage Azure et suivez les instructions pour accorder l’accès à l’application suivante :
* **ID de l’application du premier groupe :** 56c1da01-2129-48f7-9355-af6d59d42766
* **Nom de l’application de premier tiers :** Service connecteur Graph

### <a name="storage-account-and-queue-notifications-optional"></a>Compte de stockage et notifications de file d’attente (facultatif)
Le support pour traiter les modifications en temps réel dans le service de connecteurs Graph peut être ajouté à l’avenir. Dans ce cas, nous allons analyser les notifications de modification de stockage Azure stockées dans une file d’attente. Vous devez créer une file d’attente dans le même compte que votre compte de stockage Azure.

Après avoir créé une file d’attente, accédez à l’onglet **événements** sur la page de la file d’attente pour configurer l' **abonnement aux événements**. Choisissez tous les événements BLOB que la file d’attente recevra et connectez la file d’attente au compte de stockage Azure.

## <a name="manage-the-search-schema"></a>Gérer le schéma de recherche
Dans l’écran **gérer le schéma** , vous avez la possibilité de modifier les attributs de schéma (pouvant faire l’objet d’une**requête**, d’une **recherche**et de l' **extraction**) associés aux propriétés gérées. Ces attributs de propriétés gérées sont des données indexées à partir de votre compte de stockage de données Azure.

## <a name="manage-search-permissions"></a>Gérer les autorisations de recherche
### <a name="azure-data-lake-gen-2"></a>Azure Data Lake Gen 2
Dans l’écran gérer les autorisations de recherche, vous pouvez choisir d' **administrer** les listes de contrôle d’accès (ACL) de votre compte de [stockage Azure Data Lake Gen 2](https://docs.microsoft.com/azure/storage/blobs/data-lake-storage-introduction) . Lorsque ces autorisations de recherche sont définies, le contenu de recherche est tronqué en fonction des autorisations attribuées à l’utilisateur [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/) connecté à rechercher dans le contenu. Vous pouvez également choisir de faire en sorte que tout le contenu indexé à partir de votre compte de stockage soit visible par tous les membres de votre organisation. Dans ce cas, tous les membres de votre organisation auront accès à toutes les données de votre compte de stockage.

### <a name="azure-blob-storage"></a>Stockage Blob Azure
Pour une connexion au [stockage BLOB Azure](https://docs.microsoft.com/azure/storage/blobs/storage-blobs-introduction), tout le contenu indexé à partir de la source configurée est visible par tous les utilisateurs de votre organisation. Les listes de contrôle d’accès ne sont pas prises en charge au niveau BLOB dans le stockage BLOB Azure.

## <a name="set-the-refresh-schedule"></a>Définir la planification d’actualisation
Dans l’écran **paramètres d’actualisation** , vous pouvez définir l’intervalle d’analyse incrémentielle et l’intervalle d’analyse complète. Les intervalles par défaut du connecteur Azure Data Lake Storage Gen2 sont 15 minutes pour une analyse incrémentielle et une semaine pour une analyse complète.

## <a name="limitations"></a>Limites
Une connexion publiée pour Azure BLOB Storage ne peut pas être reconfigurée pour Azure Data Lake Storage Gen2 source et inversement. Dans ce cas, il est recommandé de configurer une nouvelle connexion.