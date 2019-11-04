---
title: Connecteur ServiceNow pour Microsoft Search
ms.author: v-pamcn
author: TrishaMc1
manager: mnirkhe
ms.date: 10/08/2019
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: Configurer le connecteur ServiceNow pour Microsoft Search
ms.openlocfilehash: b83bf04dc06ffab26a0067d15b36a99496c199a8
ms.sourcegitcommit: bfcab9d42e93addccd1e3875b41bc9cc1b6986cc
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/04/2019
ms.locfileid: "37949774"
---
# <a name="servicenow-connector"></a>Connecteur ServiceNow

Avec le connecteur ServiceNow, votre organisation peut indexer des Articles de la base de connaissances qui sont visibles par tous les utilisateurs au sein de votre organisation. Une fois que vous avez configuré le connecteur et le contenu d’index à partir de ServiceNow, les utilisateurs finals peuvent rechercher ces articles à partir de n’importe quel client Microsoft Search.  

Cet article est destiné aux administrateurs 365 de Microsoft ou toute personne qui configure, exécute et surveille un connecteur ServiceNow. Elle explique comment configurer les fonctionnalités de connecteur et de connecteur, ainsi que les restrictions et les techniques de résolution des problèmes.

## <a name="connect-to-a-data-source"></a>Se connecter à une source de données
Pour vous connecter à vos données ServiceNow, vous avez besoin de l’URL de l' **instance ServiceNow**de votre organisation, des informations d’identification de ce compte, ainsi que de l’ID client et de la clé secrète client pour l’authentification OAuth.  

L’URL de l' **instance ServiceNow** de votre organisation ressemble généralement **à https://&lt;>. service-Now.com**. En plus de cette URL, vous aurez besoin d’un compte pour la configuration de la connexion à ServiceNow, ainsi que pour permettre à Microsoft Search de mettre à jour régulièrement les articles à partir de ServiceNow en fonction de la planification de l’actualisation.

Pour authentifier et synchroniser le contenu à partir de ServiceNow, choisissez l’une des deux méthodes prises en charge : 
1. Authentification de base 
2. OAuth (recommandé)

> [!Note]
> Pour utiliser OAuth pour l’authentification, un administrateur ServiceNow doit mettre en service un point de terminaison dans votre instance ServiceNow, afin que l’application Microsoft Search puisse accéder à l’instance. Pour plus d’informations, reportez-vous à la rubrique [créer un point de terminaison pour les clients pour accéder à l’instance](https://docs.servicenow.com/bundle/newyork-platform-administration/page/administer/security/task/t_CreateEndpointforExternalClients.html) dans la documentation ServiceNow.

Le tableau suivant fournit des instructions sur la façon de remplir le formulaire de création du point de terminaison :

**Field** | **Description** | **Valeur recommandée**
--- | --- | ---
Nom | Cette valeur unique identifie l’application pour laquelle vous avez besoin d’un accès OAuth. | Recherche Microsoft
ID du client | IDENTIFICATEUR unique en lecture seule et généré automatiquement pour l’application. L’instance utilise l’ID client lorsqu’elle demande un jeton d’accès. | N/A
Clé secrète client | Avec cette chaîne secrète partagée, l’instance de ServiceNow et Microsoft Search autorisent les communications les uns avec les autres. | Suivez les meilleures pratiques en matière de sécurité en le traitant comme un mot de passe.
URL de redirection | URL de rappel obligatoire vers laquelle le serveur d’autorisation redirige. | Consultez la rubrique [rappel OAuth](https://gcs.office.com/v1.0/admin/oauth/callback).
URL du logo | URL qui contient l’image du logo de l’application. | N/A
Actif | Activez la case à cocher pour activer le registre d’application. | Défini sur actif
Durée de vie des jetons d’actualisation | Nombre de secondes pendant lesquelles un jeton d’actualisation est valide. Par défaut, les jetons d’actualisation expirent dans 100 jours (8640000 secondes). | 31 536 000 (1 an)
Durée de vie du jeton d’accès | Nombre de secondes pendant lesquelles un jeton d’accès est valide. | 43 200 (12 heures)

## <a name="set-a-sync-filter"></a>Définir un filtre de synchronisation 
Avec un filtre de synchronisation, vous pouvez spécifier des conditions pour la synchronisation des articles. Il s’agit d’une clause **Where** d’une instruction **SQL SELECT** . Par exemple, vous pouvez choisir d’indexer uniquement les articles publiés et actifs. La page de configuration de SyncNow décrit la capture et la définition d’un filtre de synchronisation.

## <a name="manage-the-search-schema"></a>Gérer le schéma de recherche
Une fois la connexion établie, configurez le mappage du schéma de recherche. Vous pouvez choisir les propriétés à utiliser pour les **requêtes**, les **recherches**et les **extractions**.

## <a name="manage-search-permissions"></a>Gérer les autorisations de recherche
Le connecteur ServiceNow prend uniquement en charge les autorisations de recherche visibles par **tous les utilisateurs**. Les données indexées apparaissent dans les résultats de la recherche et sont visibles par tous les utilisateurs de l’organisation.
 
## <a name="set-the-refresh-schedule"></a>Définir la planification d’actualisation 
Le connecteur ServiceNow prend en charge les planifications d’actualisation pour les analyses complètes et incrémentielles. Nous vous recommandons de définir les deux.

Une planification d’analyse complète recherche les articles supprimés qui ont été précédemment synchronisés avec l’index Microsoft Search et les articles qui se sont déplacés du filtre de synchronisation. Lorsque vous vous connectez pour la première fois à ServiceNow, une analyse complète est exécutée pour synchroniser tous les Articles de la base de connaissances. Pour synchroniser de nouveaux éléments et effectuer des mises à jour, vous devez planifier des analyses incrémentielles.

La valeur par défaut recommandée est d’un jour pour une analyse complète et de quatre heures pour une analyse incrémentielle.
