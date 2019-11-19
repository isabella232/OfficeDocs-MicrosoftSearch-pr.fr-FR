---
title: Connecteur de sites Web d’entreprise pour Microsoft Search
ms.author: mounika.narayanan
author: monaray
manager: mnirkhe
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: Configurer le connecteur de sites Web d’entreprise pour Microsoft Search
ms.openlocfilehash: 14eef035f4cc054ab87582b573cb6b7e3c12d0c7
ms.sourcegitcommit: 68087149c769a7cdde80944dd9c9933d2bf4a23f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/18/2019
ms.locfileid: "38699520"
---
# <a name="enterprise-websites-connector"></a>Connecteur de sites Web d’entreprise

Avec le connecteur de sites Web d’entreprise, votre organisation peut indexer des articles et du **contenu à partir de ses sites Web internes**. Une fois que vous avez configuré le connecteur et synchronisé le contenu à partir du site Web, les utilisateurs finaux peuvent rechercher ce contenu à partir de n’importe quel client Microsoft Search.

Cet article est destiné aux administrateurs [365 de Microsoft](https://www.microsoft.com/microsoft-365) ou toute personne qui configure, exécute et surveille un connecteur de sites Web d’entreprise. Elle explique comment configurer les fonctionnalités de connecteur et de connecteur, ainsi que les restrictions et les techniques de résolution des problèmes.  

## <a name="connect-to-a-data-source"></a>Se connecter à une source de données 
Pour vous connecter à votre source de données, vous avez besoin de votre URL racine et d’une forme d’authentification : authentification de base ou OAuth 2,0 avec [Azure Active Directory (Azure AD)](https://docs.microsoft.com/azure/active-directory/).

### <a name="root-url"></a>URL racine
L’URL racine est celle qui initie l’analyse et qui est utilisée pour l’authentification. Vous pouvez obtenir l’URL à partir de la page d’accueil du site Web que vous souhaitez analyser.

### <a name="authentication"></a>Authentification 
L’authentification de base nécessite un nom d’utilisateur et un mot de passe. Créez ce compte bot à l’aide du [Centre d’administration](https://admin.microsoft.com)Microsoft 365.

OAuth 2,0 avec [Azure ad](https://docs.microsoft.com/azure/active-directory/) requiert un ID de client, un ID de ressource, un ID client et une clé secrète client.
Pour plus d’informations, consultez la rubrique [autoriser l’accès aux applications Web Azure Active Directory à l’aide du flux d’octroi de code OAuth 2,0](https://docs.microsoft.com/azure/active-directory/develop/v1-protocols-oauth-code). Inscrivez-vous avec les valeurs suivantes :
* **Nom :** Microsoft Search
* **Redirect_URI :**`https://gcs.office.com/v1.0/admin/oauth/callback`

Pour obtenir les valeurs de client nommé, de ressource, de client_id et de client_secret, accédez à **utiliser le code d’autorisation pour demander un jeton d’accès** sur la page Web URL de redirection.

Pour plus d’informations, consultez [la rubrique QuickStart : inscrire une application avec la plateforme d’identité Microsoft](https://docs.microsoft.com/azure/active-directory/develop/quickstart-register-app).

### <a name="reverse-proxy-url"></a>URL du proxy inverse 
Le connecteur de sites Web d’entreprise est basé sur le Cloud et n’a donc pas accès au contenu local. Pour fournir cet accès, installez un proxy inverse. Un proxy inverse offre un accès sécurisé et fiable aux sites Web locaux. Nous recommandons le [proxy d’application Azure](https://docs.microsoft.com/azure/active-directory/manage-apps/application-proxy).

La configuration requise pour le proxy inverse pour l’URL racine et l’authentification est la même que pour le contenu basé sur le Cloud, sauf que l’URL racine et l’authentification sont fournies par le serveur proxy inverse.

Consultez la section [considérations relatives à la sécurité pour accéder aux applications à distance avec le proxy d’application Azure ad](https://docs.microsoft.com/azure/active-directory/manage-apps/application-proxy-security).

## <a name="select-the-source-properties"></a>Sélectionnez les propriétés source. 
Les propriétés sources sont définies en fonction du format de données du site Web d’entreprise. Toutefois, vous pouvez créer une **liste d’exclusion** pour exclure certaines URL de l’analyse si ce contenu est sensible ou inutile à l’analyse. Pour créer une liste d’exclusion, parcourez l’URL racine. Vous avez la possibilité d’ajouter les URL exclues à la liste lors du processus de configuration.

## <a name="manage-search-permissions"></a>Gérer les autorisations de recherche 
Il n’existe pas de prise en charge des listes de contrôle d’accès (ACL). Par conséquent, nous vous recommandons de connecter uniquement les sites Web visibles par tous les utilisateurs au sein de votre organisation.

## <a name="set-the-refresh-schedule"></a>Définir la planification d’actualisation
Le connecteur de sites Web d’entreprise ne prend en charge qu’une analyse complète. Cela signifie que le connecteur lit tout le contenu du site Web pendant chaque analyse. Pour vous assurer que le connecteur dispose de suffisamment de temps pour lire le contenu, nous vous recommandons de définir un intervalle de planification d’actualisation important. Nous vous recommandons une actualisation planifiée entre trois jours et deux semaines.

## <a name="limitations"></a>Limites 
Le connecteur de sites Web d’entreprise ne prend pas en charge la recherche de données sur des pages Web dynamiques. Exemples de ces pages Web dans des systèmes de gestion de contenu [tels que le](https://www.atlassian.com/software/confluence) [Unily](https://www.unily.com/) et les bases de données qui stockent le contenu du site Web.