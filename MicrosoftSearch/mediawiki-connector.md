---
title: Connecteur d’Graph MediaWiki pour Recherche Microsoft
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
description: Configurer le connecteur d’Graph MediaWiki pour Recherche Microsoft
ms.openlocfilehash: 7e1c308eb1785dd7fec23fac7e9002957a0d50ca
ms.sourcegitcommit: bb99601a7bd0f16dde7b271de516465d134e5bac
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/08/2021
ms.locfileid: "58973494"
---
<!---Previous ms.author: monaray --->

# <a name="mediawiki-graph-connector"></a>Connecteur d’Graph MediaWiki

Le connecteur Graph MediaWiki permet à votre organisation de découvrir et d’indexer des données à partir d’un wiki créé à l’aide du logiciel MediaWiki. Ce connecteur indexe le contenu spécifié dans Recherche Microsoft et prend en charge les analyse périodiques pour maintenir l’index à jour.

> [!NOTE]
> Lisez [**l’article**](configure-connector.md) Installation de votre connecteur Graph pour comprendre les instructions générales Graph d’installation des connecteurs.

Cet article est réservé à toute personne qui configure, exécute et surveille un connecteur Graph MediaWiki. Il complète le processus de configuration général et affiche des instructions qui s’appliquent uniquement au connecteur Graph MediaWiki. Cet article inclut également des informations sur [les limitations.](#limitations)

<!---## Before you get started-->

<!---Insert "Before you get started" recommendations for this data source-->

## <a name="step-1-add-a-graph-connector-in-the-microsoft-365-admin-center"></a>Étape 1 : Ajouter un connecteur Graph dans le Centre d'administration Microsoft 365

Suivez les [instructions d’installation générales.](./configure-connector.md)
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-2-name-the-connection"></a>Étape 2 : Nommer la connexion

Suivez les [instructions d’installation générales.](./configure-connector.md)
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-3-configure-the-connection-settings"></a>Étape 3 : Configurer les paramètres de connexion

Entrez votre **URL Wiki** et choisissez le **type d’authentification** dans le menu déroulant des options. Les options sont **None**, **Basic** et **OAuth 2.0 AAD**.

Si vous choisissez **De base** comme type d’authentification, vous devez fournir le nom d’utilisateur et le mot de **passe** du wiki. 

Si vous choisissez **OAuth 2.0 AAD** comme type d’authentification, vous devez fournir l’ID de ressource de l’installation wiki.  Vous devez également fournir **l’ID client** et la secret **client** générés sur la page d’inscription de l’application AAD.

## <a name="step-4-manage-search-permissions"></a>Étape 4 : Gérer les autorisations de recherche

Le connecteur MediaWiki prend uniquement en charge les autorisations de recherche visibles par **Tout le monde.** Les données indexées apparaissent dans les résultats de la recherche et sont visibles par tous les utilisateurs de l’organisation.

## <a name="step-5-assign-property-labels"></a>Étape 5 : Attribuer des étiquettes de propriété

Suivez les [instructions d’installation générales.](./configure-connector.md)
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-6-manage-schema"></a>Étape 6 : Gérer le schéma

Suivez les [instructions d’installation générales.](./configure-connector.md)
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-7-choose-refresh-settings"></a>Étape 7 : Choisir les paramètres d’actualisation

Suivez les [instructions d’installation générales.](./configure-connector.md)
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-8-review-connection"></a>Étape 8 : Examiner la connexion

Suivez les [instructions d’installation générales.](./configure-connector.md)
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

<!---## Troubleshooting-->
<!---To be added-->

## <a name="limitations"></a>Limites

Le connecteur MediaWiki présente les limitations ci-après dans la version préliminaire :

* Prend en charge uniquement les wikis basés sur le cloud.
* Prend en charge uniquement Basic ou OAuth 2.0 avec l’authentification Azure Active Directory ou Azure.
* Ne prend pas en charge la sélection d’espace de noms pour l’indexation. Indexe uniquement les espaces de noms Principal, Catégorie et Fichier.
* Ne prend pas en charge les listes de contrôle d’accès. Par conséquent, les pages indexées sont visibles par tous les utilisateurs de l’organisation.