---
title: Connecteur MediaWiki pour Microsoft Search (recherche Microsoft)
ms.author: monaray
author: monaray97
manager: mnirkhe
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: Configurer le connecteur MediaWiki pour Microsoft Search (recherche Microsoft)
ms.openlocfilehash: 7a22fcc84f6f435bf438aa027c42c76eb8be1eaf
ms.sourcegitcommit: 39bf9f0db7f9bff2ab82c99a059b0ddcf1c98f5f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/19/2021
ms.locfileid: "49905950"
---
# <a name="mediawiki-connector"></a>Connecteur MediaWiki

Avec le connecteur MediaWiki, votre organisation peut découvrir et indexer des données à partir d’un wiki créé à l’aide du logiciel MediaWiki. Ce connecteur indexe le contenu spécifié dans Microsoft Search (recherche Microsoft) et prend en charge les analyse périodiques pour maintenir l’index à jour.

Cet article est réservé aux administrateurs Microsoft 365 ou à toute personne qui configure, exécute et surveille un connecteur MediaWiki Graph. Il complète les instructions générales fournies dans l’article [Configurer votre connecteur Graph.](configure-connector.md) Si vous ne l’avez pas déjà fait, lisez l’intégralité de l’article Configurer votre connecteur Graph pour comprendre le processus d’installation général.

Chaque étape du processus d’installation est répertoriée ci-dessous avec une note qui indique que vous devez suivre les instructions d’installation générales ou d’autres instructions qui s’appliquent uniquement aux connecteurs MediaWiki Graph. Cet article inclut également des informations [sur les limitations](#limitations) des connecteurs MediaWiki Graph. 

## <a name="step-1-add-a-graph-connector-in-the-microsoft-365-admin-center"></a>Étape 1 : Ajoutez un connecteur Graph dans le Centre d’administration Microsoft 365.
Suivez les instructions d’installation générales.

## <a name="step-2-name-the-connection"></a>Étape 2 : Nommez la connexion.
Suivez les instructions d’installation générales.
 
## <a name="step-3-configure-the-connection-settings"></a>Étape 3 : Configurer les paramètres de connexion.
Entrez votre **URL Wiki** et choisissez le **type d’authentification** dans le menu déroulant des options. Les options sont **None**, **Basic** et **OAuth 2.0 AAD**.

Si vous choisissez **De base** comme type d’authentification, vous devez fournir le nom d’utilisateur et le mot de **passe** du wiki. 

Si vous choisissez **OAuth 2.0 AAD** comme type d’authentification, vous devez fournir l’ID de ressource de l’installation wiki.  Vous devez également fournir **l’ID client** et la secret **client** générés sur la page d’inscription de l’application AAD. 

## <a name="step-4-manage-search-permissions"></a>Étape 4 : Gérer les autorisations de recherche
Le connecteur MediaWiki prend uniquement en charge les autorisations de recherche visibles par **Tout le monde.** Les données indexées apparaissent dans les résultats de la recherche et sont visibles par tous les utilisateurs de l’organisation.

## <a name="step-5-assign-property-labels"></a>Étape 5 : Attribuer des étiquettes de propriété
Suivez les instructions d’installation générales.

## <a name="step-6-manage-schema"></a>Étape 6 : Gérer le schéma
Suivez les instructions d’installation générales.

## <a name="step-7-choose-refresh-settings"></a>Étape 7 : Choisir les paramètres d’actualisation
Suivez les instructions d’installation générales.

## <a name="step-8-review-connection"></a>Étape 8 : Examiner la connexion
Suivez les instructions d’installation générales.

<!---## Troubleshooting-->
<!---To be added-->

## <a name="limitations"></a>Limites
Le connecteur MediaWiki présente les limitations ci-après dans la version préliminaire :

* Prend en charge uniquement les wikis basés sur le cloud.
* Prend en charge uniquement Basic ou OAuth 2.0 avec l’authentification Azure Active Directory ou Azure.
* Ne prend pas en charge la sélection d’espace de noms pour l’indexation. Indexe uniquement les espaces de noms Principal, Catégorie et Fichier.
* Ne prend pas en charge les listes de contrôle d’accès. Par conséquent, les pages indexées sont visibles par tous les utilisateurs de l’organisation.
