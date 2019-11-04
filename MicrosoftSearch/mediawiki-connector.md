---
title: Connecteur MediaWiki pour Microsoft Search
ms.author: v-pamcn
author: monaray
manager: mnirkhe
ms.date: 11/04/2019
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: Configurer le connecteur MediaWiki pour Microsoft Search
ms.openlocfilehash: 281d270a47051e20cb1cfd44540bd51371557c13
ms.sourcegitcommit: bfcab9d42e93addccd1e3875b41bc9cc1b6986cc
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/04/2019
ms.locfileid: "37949765"
---
# <a name="mediawiki-connector"></a>Connecteur MediaWiki

Avec le connecteur MediaWiki, votre organisation peut découvrir et indexer des données à partir d’un wiki créé à l’aide du logiciel MediaWiki. Ce connecteur indexe le contenu spécifié dans Microsoft Search et prend en charge les analyses périodiques pour maintenir l’index à jour.

Cet article est destiné aux administrateurs 365 de Microsoft ou toute personne qui configure, exécute et surveille un connecteur MediaWiki. Elle explique comment configurer les fonctionnalités de connecteur et de connecteur, ainsi que les restrictions et les techniques de résolution des problèmes.

## <a name="connect-to-a-data-source"></a>Se connecter à une source de données
Entrez l’URL et les informations d’identification de votre MediaWiki pour authentifier la connexion. Vous aurez besoin des informations suivantes : **ID**de client, **ID de ressource**, **ID client**et **clé secrète client**.

## <a name="manage-the-search-schema"></a>Gérer le schéma de recherche
Une fois la connexion établie, configurez le mappage du schéma de recherche. Vous pouvez choisir les propriétés à utiliser pour les **requêtes**, les **recherches**et les **extractions**.

## <a name="manage-search-permissions"></a>Gérer les autorisations de recherche
Le connecteur MediaWiki prend uniquement en charge les autorisations de recherche visibles par **tous les utilisateurs**. Les données indexées apparaissent dans les résultats de la recherche et sont visibles par tous les utilisateurs de l’organisation.

## <a name="set-the-refresh-schedule"></a>Définir la planification d’actualisation 
Cette planification actualise les données indexées, de sorte que les modifications apportées au wiki sont reflétées dans Microsoft Search. Toutes les nouvelles pages, pages supprimées, contenu de page ou modifications de métadonnées apparaissent dans les résultats de la recherche après l’intervalle d’actualisation spécifié. La durée de l’analyse dépend de la taille du wiki. Actuellement, le connecteur analyse environ 50 pages par minute.

## <a name="limitations"></a>Limites 
Le connecteur MediaWiki présente ces limitations dans la version d’évaluation :
* Prend en charge uniquement les wikis sur le Cloud.
* Prend en charge uniquement les 2,0 de base ou OAuth avec Azure Active Directory ou l’authentification Azure.
* Ne prend pas en charge la sélection d’espace de noms pour l’indexation. Indexe uniquement les espaces de noms **principal**, de **catégorie**et de **fichier** .
* Ne prend pas en charge les listes de contrôle d’accès (ACL). Ainsi, les pages indexées sont visibles par tous les utilisateurs de l’organisation.
