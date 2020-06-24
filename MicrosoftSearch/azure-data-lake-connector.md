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
ms.openlocfilehash: f8cb94e806e619d6dae7258b6c2d708d93afb9a8
ms.sourcegitcommit: 7eda9b621def0659d7e7bc8b989f8adc929cce93
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/24/2020
ms.locfileid: "44861075"
---
# <a name="azure-data-lake-storage-gen2-connector"></a>Connecteur Azure Data Lake Storage Gen2

Avec le connecteur [Azure Data Lake Storage Gen2](https://docs.microsoft.com/azure/storage/blobs/data-lake-storage-introduction) , les utilisateurs de votre organisation peuvent rechercher des fichiers et leur contenu. Ce connecteur accède aux données stockées dans les conteneurs d’objets BLOB Azure et les dossiers activés dans la hiérarchie dans un compte Azure Data Lake Storage Gen 2.

Cet article est destiné aux administrateurs [365 de Microsoft](https://www.microsoft.com/microsoft-365) ou toute personne qui configure, exécute et surveille un connecteur Azure Data Lake Storage Gen2. Elle explique comment configurer les fonctionnalités de connecteur et de connecteur, ainsi que les restrictions et les techniques de résolution des problèmes.

## <a name="connect-to-a-data-source"></a>Se connecter à une source de données

### <a name="primary-storage-connection-string"></a>Chaîne de connexion de stockage principal 
Sur l’écran **authentification et configuration** , fournissez la chaîne de connexion de stockage principal. Cette chaîne est requise pour autoriser l’accès à votre compte de stockage. Pour rechercher votre chaîne de connexion, accédez au [portail Azure](https://ms.portal.azure.com/#home) et accédez à la section **clés** du compte [Azure Data Lake Storage Gen2](https://docs.microsoft.com/azure/storage/blobs/data-lake-storage-introduction) . Copiez et collez la chaîne de connexion dans le champ approprié à l’écran.

Si vous ne souhaitez pas fournir le **AccountKey** (un paramètre dans la chaîne de connexion de stockage principal), vous devez accorder un accès en lecture à notre service de connecteurs Graph. Dans l’onglet **contrôle d’accès** de votre compte Azure Data Lake Storage Gen2, suivez les instructions de cette page pour accorder l’accès à l’application suivante :
* **ID de l’application du premier groupe :** 56c1da01-2129-48f7-9355-af6d59d42766
* **Nom de l’application de premier tiers :** Service connecteur Graph

### <a name="storage-account-and-queue-notifications-optional"></a>Compte de stockage et notifications de file d’attente (facultatif)
Le support pour traiter les modifications en temps réel dans le service de connecteurs Graph peut être ajouté à l’avenir. Dans ce cas, nous allons analyser les notifications de modification de l' [enregistrement des données de stockage Azure Data Lake](https://docs.microsoft.com/azure/storage/blobs/data-lake-storage-introduction) stockées dans une file d’attente. Vous devez créer une file d’attente dans le même compte que celui de votre compte Azure Data Lake Storage Gen2 ou dans un autre compte de stockage.

Après avoir créé une file d’attente, accédez à l’onglet **événements** sur la page de la file d’attente pour configurer l' **abonnement aux événements**. Choisissez tous les événements BLOB que la file d’attente recevra et connectez la file d’attente au compte Azure Data Lake Storage Gen2.

## <a name="manage-the-search-schema"></a>Gérer le schéma de recherche
Dans l’écran **gérer le schéma** , vous avez la possibilité de modifier les attributs de schéma (pouvant faire l’objet d’une**requête**, d’une **recherche**et de l' **extraction**) associés aux propriétés gérées. Ces attributs de propriétés gérées sont des données indexées à partir de votre compte [Azure Data Lake Storage Gen2](https://docs.microsoft.com/azure/storage/blobs/data-lake-storage-introduction) .

## <a name="manage-search-permissions"></a>Gérer les autorisations de recherche
Dans l’écran gérer les autorisations de recherche, vous pouvez choisir d' **administrer** les listes de contrôle d’accès (ACL) de votre compte de stockage. Lorsque ces autorisations de recherche sont définies, le contenu de recherche est tronqué en fonction des autorisations attribuées à l’utilisateur [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/) connecté à rechercher dans le contenu. Vous pouvez également choisir de faire en sorte que tout le contenu indexé à partir de votre compte de stockage soit visible par tous les membres de votre organisation. Dans ce cas, tous les membres de votre organisation auront accès à toutes les données de votre compte de stockage.
 
## <a name="set-the-refresh-schedule"></a>Définir la planification d’actualisation
Dans l’écran **paramètres d’actualisation** , vous pouvez définir l’intervalle d’analyse incrémentielle et l’intervalle d’analyse complète. Les intervalles par défaut du connecteur [Azure Data Lake Storage Gen2](https://docs.microsoft.com/azure/storage/blobs/data-lake-storage-introduction) sont 15 minutes pour une analyse incrémentielle et une semaine pour une analyse complète.
 
## <a name="limitations"></a>Limites
Actuellement, l’accès multiprotocole du fournisseur de [stockage Azure Data Lake](https://docs.microsoft.com/azure/storage/blobs/data-lake-storage-introduction) n’est disponible que pour les États-Unis, les États-Unis, le Canada central, l’est-u, l’Asie de l’est, l’Europe du Nord, l’US2, le sud-est de l’Ouest, l’Europe de l’Ouest, l’Australie, le Japon ou le sud-est.

Pour plus d’informations sur les mises à jour et plus d’informations, voir [Multi-Protocol Access on Azure Data Lake Storage (Preview)](https://docs.microsoft.com/azure/storage/blobs/data-lake-storage-multi-protocol-access).


