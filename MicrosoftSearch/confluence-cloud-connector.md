---
title: Connecteur cloud Graph Cloud pour Recherche Microsoft
ms.author: kam1
author: TheKarthikeyan
manager: harshkum
audience: Admin
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: Configurer le connecteur cloud Graph Cloud pour Recherche Microsoft
ms.openlocfilehash: baf6139257c8bf8e40bc997e2a408efb4fc2549f
ms.sourcegitcommit: ca5ee826ba4f4bb9b9baabc9ae8a130011c2a3d0
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/15/2021
ms.locfileid: "59375990"
---
<!---Previous ms.author: kam1 --->

# <a name="confluence-cloud-graph-connector-preview"></a>Cloud Graph Connector (prévisualisation)

Le connecteur d Graph cloud cloud permet à votre organisation d’indexer le contenu De la cloud. Une fois que vous avez configuré le connecteur et les données d’index à partir du site Der, les utilisateurs finaux peuvent rechercher ces contenus dans Recherche Microsoft.

>[!NOTE]
>Cloud Graph Connector est en prévisualisation. Si vous souhaitez obtenir un accès en avant-première pour l’essayer, inscrivez-vous à l’aide [<b>de ce formulaire. </b>](https://forms.office.com/r/duLxv8Nf8U)  

Cet article s’Microsoft 365 administrateurs informatiques ou toute personne qui configure, exécute et surveille un connecteur Graph Cloud Cloud. Il complète les instructions générales fournies dans l’article Configurer [Graph connecteur.](configure-connector.md) Si vous ne l’avez pas déjà fait, lisez l’intégralité de l’article Configurer votre connecteur Graph pour comprendre le processus d’installation général.

Chaque étape du processus d’installation est répertoriée ci-dessous, ainsi qu’une note qui indique que vous devez suivre les [](#troubleshooting) instructions de configuration générales ou d’autres instructions qui s’appliquent uniquement au connecteur Cloud Graph Cloud, y compris des informations sur le dépannage et les [limitations.](#limitations)


## <a name="before-you-get-started"></a>Avant de commencer
Vous devez être l’administrateur du client M365 de votre organisation, ainsi que l’administrateur du site De l’organisation.

## <a name="step-1-add-a-graph-connector-in-the-microsoft-365-admin-center"></a>Étape 1 : Ajouter un connecteur Graph dans le Centre d'administration Microsoft 365
Suivez les [instructions d’installation générales.](./configure-connector.md)

## <a name="step-2-name-the-connection"></a>Étape 2 : Nommer la connexion
Suivez les [instructions d’installation générales.](./configure-connector.md)

## <a name="step-3-configure-the-connection-settings"></a>Étape 3 : Configurer les paramètres de connexion
Pour vous connecter à votre site Der, utilisez l’URL de votre site. Une URL de site cloud DeNte ressemble généralement *à https://<organization_name>.atlassian.net/*. Vous pouvez choisir soit l’authentification de base, soit OAuth 2.0 (recommandé) pour vous authentifier sur votre site de Contrôle.

### <a name="basic-auth"></a>Th de base
Entrez le nom d’utilisateur de votre compte (généralement l’ID de courrier électronique) et le jeton d’API pour vous authentifier à l’aide de l’authentification de base. Pour en savoir plus sur la génération d’un jeton d’API, reportez-vous à la documentation d’Atlassian sur la gestion des jetons d’API pour votre [compte Atlassian.](https://support.atlassian.com/atlassian-account/docs/manage-api-tokens-for-your-atlassian-account/)

### <a name="oauth-20"></a>OAuth 2.0
Inscrivez une application dans Cloud Cloud afin que l’Recherche Microsoft’application puisse accéder à l’instance. Pour plus d’informations, voir la documentation du support Atlassian sur la façon d’activer [OAuth 2.0.](https://developer.atlassian.com/cloud/confluence/oauth-2-3lo-apps/#enabling-oauth-2-0--3lo-)

Les étapes suivantes fournissent des instructions sur la façon d’inscrire l’application :

1. Connectez-vous [à la console Atlassian Developer avec](https://developer.atlassian.com/console/myapps/) votre compte d’administrateur Atlassian Admin.
2. Cliquez dessus `Create` et sélectionnez `OAuth 2.0 integration`
3. Fournissez un nom approprié pour l’application et créez-la.
4. Accédez `Permissions` au volet de navigation à gauche. Cliquez `Add` pour `Confluence API` . Une fois ajouté, cliquez sur `Configure` et ajoutez les étendues suivantes `Read Confluence space summary` : , , , , et `Read Confluence content properties` `Read Confluence detailed content` `Read Confluence content summary` `Read content permission in Confluence` `Read user` `Read user groups` `Search Confluence content and space summaries` .
5. Accédez `Authorization` au volet de navigation à gauche. Ajoutez l’URL de `https://gcs.office.com/v1.0/admin/oauth/callback` rappel et enregistrez les modifications.
6. Accédez `Settings` au volet de navigation à gauche. Vous recevez les `Client ID` et à partir de cette `Secret` page.

Lors de l’inscription de l’application avec les détails ci-dessus, vous obtenez **l’ID client** et la **secret**. Terminez l’étape des paramètres de connexion à l’aide de ces paramètres.

## <a name="step-4-select-properties-and-filter-data"></a>Étape 4 : sélectionner les propriétés et filtrer les données

Au cours de cette étape, vous pouvez ajouter ou supprimer des propriétés disponibles de votre source de données à Base de données. Microsoft 365 a déjà sélectionné quelques propriétés par défaut.

Avec une chaîne CQL (Query Language), vous pouvez spécifier des conditions pour la synchronisation des pages. Il s’agit **d’une** clause Where dans une **SQL Select.** Par exemple, vous pouvez choisir d’indexer uniquement les pages modifiées au cours des deux dernières années. Pour en savoir plus sur la création de votre propre chaîne de requête, voir [Recherche avancée à l’aide de CQL](https://developer.atlassian.com/server/confluence/advanced-searching-using-cql/). Par défaut, tous les blogs et pages sont indexés par le connecteur.

Utilisez le bouton d’aperçu des résultats pour vérifier les exemples de valeurs des propriétés sélectionnées et de la chaîne CQL.

## <a name="step-5-manage-search-permissions"></a>Étape 5 : Gérer les autorisations de recherche

Le connecteur cloud Graph cloud prend  **** en charge les autorisations de recherche visibles par tout le monde ou uniquement les personnes ayant **accès à cette source de données.** Si vous choisissez **Tout le** monde, les données indexées apparaissent dans les résultats de recherche pour tous les utilisateurs. Si vous choisissez **uniquement les personnes** ayant accès à cette source de données, les données indexées apparaissent dans les résultats de la recherche pour les utilisateurs qui y ont accès.

Dans Cloud Cloud, les autorisations de sécurité pour les utilisateurs et les groupes sont définies à l’aide d’autorisations d’espace et de restrictions de page. Cloud Graph Connector applique des autorisations d’espace en l’absence de restrictions de page. Les restrictions de niveau page, si elles sont présentes, prévalent sur les autorisations d’espace.

Si vous choisissez uniquement les personnes ayant accès à cette **source** de données, vous devez choisir si votre site de Azure Active Directory (AAD) dispose d’utilisateurs ou d’utilisateurs non AAD.

Pour identifier l’option qui convient à votre organisation :

1. Sélectionnez **l’option AAD** si l’ID de messagerie des utilisateurs Demms est identique à l’UPN (UserPrincipalName) des utilisateurs dans AAD. 
2. Sélectionnez **l’option Non-AAD** si l’ID de messagerie des utilisateurs Demms est **différent** de l’UPN (UserPrincipalName) des utilisateurs dans AAD. 

>[!NOTE]
> * Si vous choisissez AAD comme type de source d’identité, le connecteur masce les ID de messagerie des utilisateurs obtenus directement à partir d’AAD à la propriété UPN.
> * Si vous avez choisi « Non-AAD » pour le type d’identité, voir Mappage de vos [identités non-Azure AD](map-non-aad.md) pour obtenir des instructions sur le mappage des identités. Vous pouvez utiliser cette option pour fournir l’expression régulière de mappage de l’ID de messagerie vers l’UPN.

## <a name="step-6-assign-property-labels"></a>Étape 6 : Attribuer des étiquettes de propriété

Suivez les [instructions d’installation générales.](./configure-connector.md)

## <a name="step-7-manage-schema"></a>Étape 7 : Gérer le schéma

Suivez les [instructions d’installation générales.](./configure-connector.md)

## <a name="step-8-choose-refresh-settings"></a>Étape 8 : Choisir les paramètres d’actualisation

Suivez les [instructions d’installation générales.](./configure-connector.md)

>[!NOTE]
>Pour les mises à jour des autorisations d’accès, seule l’analyse complète programmée sera appliquée.

## <a name="step-9-review-connection"></a>Étape 9 : Examiner la connexion

Suivez les [instructions d’installation générales.](./configure-connector.md)

Après avoir publié la connexion, vous devez personnaliser la page des résultats de la recherche. Pour en savoir plus sur la personnalisation des résultats de recherche, voir [Personnaliser la page des résultats de la recherche.](/microsoftsearch/configure-connector#next-steps-customize-the-search-results-page)

## <a name="troubleshooting"></a>Résolution des problèmes
Sous-dessous se trouve une liste des erreurs courantes observées lors de la configuration du connecteur et leurs raisons possibles.

| Étape de configuration | Message d’erreur | Raisons possibles |
| ------------ | ------------ | ------------ |
| Paramètres de connexion | La demande est de format non valide ou incorrecte. | URL de site incorrecte |
| Paramètres de connexion | Impossible d’accéder au service cloud DeNte pour votre site DeNte. | URL de site incorrecte |
| Paramètres de connexion | Le client n’est pas autorisé à effectuer l’action. | Jeton API non valide fourni pour l’thent de base |
| Sélectionner des propriétés | Aucun message d’erreur et aucun résultat d’aperçu | Vérifiez si votre requête CQL est valide |

## <a name="limitations"></a>Limites
Le connecteur cloud Graph cloud présente les limitations connues suivantes dans sa dernière version :

- Cloud Connector n’indexe pas les fichiers de pièces jointes et les commentaires.
- Les déploiements du serveur d’indexation et du centre de données seront publiés en tant que connecteur séparé.