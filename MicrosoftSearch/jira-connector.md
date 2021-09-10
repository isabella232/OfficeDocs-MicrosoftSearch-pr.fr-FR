---
title: Connecteur d’Graph Atlassian Jira pour Recherche Microsoft
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
description: Configurer le connecteur Graph Atlassian Jira pour Recherche Microsoft
ms.openlocfilehash: 0b4b1dc0ed1f9e9d3ca57f98dc3878f63e68d510
ms.sourcegitcommit: bb99601a7bd0f16dde7b271de516465d134e5bac
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/08/2021
ms.locfileid: "58973777"
---
# <a name="atlassian-jira-graph-connector-preview"></a>Connecteur d’Graph Atlassian Jira (prévisualisation)

Le connecteur de Graph atlassien permet à votre organisation d’indexer les problèmes de Jira. Après avoir configuré le connecteur et indexé le contenu à partir du site Jira, les utilisateurs finaux peuvent rechercher ces éléments dans Recherche Microsoft.

> [!NOTE]
> Lisez [**l’article**](configure-connector.md) Installation de votre connecteur Graph pour comprendre les instructions générales Graph d’installation des connecteurs.

Cet article est réservé à toute personne qui configure, exécute et surveille un connecteur d’Graph Atlassian. Il complète le processus d’installation général et affiche des instructions qui s’appliquent uniquement au connecteur Graph Atlassian.

>[!IMPORTANT]
>Le connecteur d’Graph atlassian Jira prend en charge uniquement les instances hébergées dans le cloud Jira. Les versions de Jira Server et du centre de données Jira ne sont pas pris en charge par ce connecteur.

## <a name="before-you-get-started"></a>Avant de commencer
Vous devez être l’administrateur du client M365 de votre organisation, ainsi que l’administrateur du site Jira de votre organisation.

## <a name="step-1-add-a-graph-connector-in-the-microsoft-365-admin-center"></a>Étape 1 : Ajouter un connecteur Graph dans le Centre d'administration Microsoft 365
Suivez les [instructions d’installation générales.](./configure-connector.md)

## <a name="step-2-name-the-connection"></a>Étape 2 : Nommer la connexion
Suivez les [instructions d’installation générales.](./configure-connector.md)

## <a name="step-3-configure-the-connection-settings"></a>Étape 3 : Configurer les paramètres de connexion
Pour vous connecter à votre site Jira, utilisez l’URL de votre site Jira. Une URL de site cloud Jira ressemble généralement *à https://<organization_name>.atlassian.net/*. Vous pouvez choisir l’authentification de base ou OAuth 2.0 (recommandé) pour vous authentifier sur votre site Jira.

### <a name="basic-auth"></a>Th de base
Entrez le nom d’utilisateur de votre compte (généralement l’ID de courrier électronique) et le jeton d’API pour vous authentifier à l’aide de l’authentification de base. Pour en savoir plus sur la génération d’un jeton d’API, reportez-vous à la documentation d’Atlassian sur la gestion des jetons d’API pour votre [compte Atlassian.](https://support.atlassian.com/atlassian-account/docs/manage-api-tokens-for-your-atlassian-account/)

### <a name="oauth-20"></a>OAuth 2.0
Inscrivez une application dans atlassian Jira afin que l’Recherche Microsoft’application puisse accéder à l’instance. Pour plus d’informations, voir la documentation du support Atlassian sur la façon d’activer [OAuth 2.0.](https://developer.atlassian.com/cloud/jira/platform/oauth-2-3lo-apps/#enabling-oauth-2-0--3lo-)

Les étapes suivantes fournissent des instructions sur la façon d’inscrire l’application :

1. Connectez-vous [à la console Atlassian Developer avec](https://developer.atlassian.com/console/myapps/) votre compte d’administrateur Atlassian Jira.
2. Cliquez dessus `Create` et sélectionnez `OAuth 2.0 integration`
3. Fournissez un nom approprié pour l’application et créez-la.
4. Accédez `Permissions` au volet de navigation à gauche. Cliquez `Add` pour `Jira platform REST API` . Une fois ajouté, cliquez sur `Configure` et ajoutez les étendues suivantes `View Jira issue data` : et `Manage Jira global settings` `View user profiles` .
5. Accédez `Authorization` au volet de navigation à gauche. Ajoutez l’URL de `https://gcs.office.com/v1.0/admin/oauth/callback` rappel et enregistrez les modifications.
6. Accédez `Settings` au volet de navigation à gauche. Vous recevez les `Client ID` et à partir de cette `Secret` page.

Lors de l’inscription de l’application avec les détails ci-dessus, vous obtenez **l’ID client** et la **secret**. Terminez l’étape des paramètres de connexion à l’aide de ces paramètres.

### <a name="step-3a-configure-data-select-projects"></a>Étape 3a : Configurer les données : sélectionner des projets

Vous pouvez choisir la connexion pour indexer l’intégralité du site Jira ou des projets spécifiques uniquement.

* Si vous choisissez d’indexer l’intégralité du site Jira, les problèmes de Jira dans tous les projets du site seront indexés. Les nouveaux projets et problèmes seront indexés lors de l’analyse suivante après leur création.
* Si vous choisissez des projets individuels, seuls les problèmes de Jira dans ces projets seront indexés.

Vous pouvez également choisir de filtrer les problèmes de Jira qui seront indexés de 2 façons.
* Spécifiez la **période de modification du problème.** Cela indexe uniquement les problèmes Jira qui sont créés ou  modifiés dans la période sélectionnée sur une base continue en fonction de l’analyse actuelle.
* Spécifiez **le JQL**. Cela indexe uniquement les problèmes Jira qui sont renvoyés après le filtrage en fonction du langage Jira Query Language (JQL) fourni. Pour en savoir plus sur l’utilisation de JQL, voir la documentation du support Atlassian sur l’utilisation de la recherche avancée avec [le langage de requête Jira](https://support.atlassian.com/jira-service-management-cloud/docs/use-advanced-search-with-jira-query-language-jql/)

> [!TIP]
> Vous pouvez utiliser le filtre JQL pour indexer uniquement des types de problèmes Jira spécifiques à l’aide de «*issueType in (Bug,Improvement)*»

### <a name="step-3b-configure-data-select-properties"></a>Étape 3b : Configurer les données : sélectionner les propriétés

Sélectionnez les champs que vous souhaitez que la connexion indexe et prévisualiser les données de ces champs avant de poursuivre. Certains champs sont déjà sélectionnés par défaut et ne peuvent pas être supprimés.

Le connecteur d’Graph Atlassian Jira peut indexer à la fois les champs de problème par défaut ainsi que les champs de problèmes créés personnalisés.

> [!NOTE]
> Si un champ créé personnalisé sélectionné n’est pas présent dans certains types de problème Jira, le champ est ingéré sous la forme *NULL* (vide).

## <a name="step-4-manage-search-permissions"></a>Étape 4 : Gérer les autorisations de recherche

Le connecteur d’Graph atlassien prend en charge  **** les autorisations de recherche visibles par tout le monde ou uniquement par les personnes ayant accès à **cette source de données.** Si vous choisissez **Tout le** monde, les données indexées apparaissent dans les résultats de recherche pour tous les utilisateurs. Si vous choisissez **uniquement les personnes** ayant accès à cette source de données, les données indexées apparaissent dans les résultats de la recherche pour les utilisateurs qui y ont accès. Dans la Jira atlassienne, les autorisations de sécurité sont définies à l’aide de schémas d’autorisations de projet contenant des groupes au niveau du site et des rôles de projet. La sécurité au niveau du problème peut également être définie à l’aide de schémas d’autorisation au niveau du problème.

Si vous choisissez uniquement les personnes ayant accès à cette **source** de données, vous devez choisir si votre site Jira dispose d’utilisateurs Azure Active Directory (AAD) ou d’utilisateurs non AAD.

Pour identifier l’option qui convient à votre organisation :

1. Choisissez **l’option AAD** si l’ID  de messagerie des utilisateurs Jira est identique à l’UPN (UserPrincipalName) des utilisateurs dans AAD.
2. Choisissez **l’option Non-AAD** si l’ID de messagerie des utilisateurs Jira est **différent** de l’UPN (UserPrincipalName) des utilisateurs dans AAD. 

>[!NOTE]
> * Si vous choisissez AAD comme type de source d’identité, le connecteur masce les ID de messagerie des utilisateurs obtenus à partir de Jira directement à la propriété UPN à partir d’AAD.
> * Si vous avez choisi « Non-AAD » pour le type d’identité, voir Mappage de vos [identités non-Azure AD](map-non-aad.md) pour obtenir des instructions sur le mappage des identités. Vous pouvez utiliser cette option pour fournir l’expression régulière de mappage de l’ID de messagerie vers l’UPN.

## <a name="step-5-assign-property-labels"></a>Étape 5 : Attribuer des étiquettes de propriété

Suivez les [instructions d’installation générales.](./configure-connector.md)

## <a name="step-6-manage-schema"></a>Étape 6 : Gérer le schéma

Suivez les [instructions d’installation générales.](./configure-connector.md)

## <a name="step-7-choose-refresh-settings"></a>Étape 7 : Choisir les paramètres d’actualisation

Le connecteur d’Graph Atlassian prend en charge les planifications d’actualisation pour les analyses complètes et incrémentielles.
La planification recommandée est d’une heure pour une analyse incrémentielle et d’un jour pour une analyse complète.

## <a name="step-8-review-connection"></a>Étape 8 : Examiner la connexion

Suivez les [instructions d’installation générales.](./configure-connector.md)

## <a name="troubleshooting"></a>Résolution des problèmes
Sous-dessous se trouve une liste des erreurs courantes observées lors de la configuration du connecteur et leurs raisons possibles.

| Étape de configuration | Message d’erreur | Raisons possibles |
| ------------ | ------------ | ------------ |
| Paramètres de connexion | La demande est de format non valide ou incorrecte. | URL de site Jira incorrecte |
| Paramètres de connexion | Impossible d’accéder au service cloud Jira pour votre site Jira. | URL de site Jira incorrecte |
| Paramètres de connexion | Le client n’est pas autorisé à effectuer l’action. | Jeton API non valide fourni pour l’thent de base |


## <a name="limitations"></a>Limites
Les limitations connues du connecteur d’Graph atlassien sont les suivantes :
* Les versions de Jira Server et du centre de données ne sont pas pris en charge.