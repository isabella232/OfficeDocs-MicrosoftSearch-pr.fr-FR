---
title: Connecteur de Graph ServiceNow pour Recherche Microsoft
ms.author: mecampos
author: mecampos
manager: umas
audience: Admin
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: Configurer le connecteur ServiceNow Graph pour Recherche Microsoft
ms.openlocfilehash: 11abe956e624fa23cd19e2dfc2ae9a4af31a0f81407f6e2c5672723c5fdfc8b5
ms.sourcegitcommit: 71ac2a38971ca4452d1bddfc773ff8f45e1ffd77
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/06/2021
ms.locfileid: "54534130"
---
<!---Previous ms.author: kam1 --->


# <a name="servicenow-graph-connector"></a>ServiceNow Graph Connector

Avec microsoft Graph Connector for ServiceNow, votre organisation peut indexer des articles de la base de connaissances qui sont visibles par tous les utilisateurs ou restreints avec des autorisations de critères utilisateur au sein de votre organisation. Après avoir configuré le connecteur et indexé le contenu à partir de ServiceNow, les utilisateurs finaux peuvent rechercher ces articles à partir de n’importe Recherche Microsoft client.  

Cet article s’Microsoft 365 administrateurs ou toute personne qui configure, exécute et surveille un connecteur Graph ServiceNow. Il complète les instructions générales fournies dans l’article Configurer [Graph connecteur.](configure-connector.md) Si vous ne l’avez pas déjà fait, lisez l’intégralité de l’article Configurer votre connecteur Graph pour comprendre le processus d’installation général.

Chaque étape du processus d’installation est répertoriée ci-dessous, ainsi qu’une note qui indique que vous devez suivre les [](#troubleshooting) instructions d’installation générales ou d’autres instructions qui s’appliquent uniquement au connecteur ServiceNow Graph, y compris des informations sur le dépannage et les [limitations.](#limitations)  

## <a name="step-1-add-a-graph-connector-in-the-microsoft-365-admin-center"></a>Étape 1 : Ajoutez un connecteur Graph dans le Centre d’administration Microsoft 365.
Suivez les instructions d’installation générales.

## <a name="step-2-name-the-connection"></a>Étape 2 : Nommez la connexion.
Suivez les instructions d’installation générales.


## <a name="step-3-connection-settings"></a>Étape 3 : Connexion Paramètres
Pour vous connecter à vos données ServiceNow, vous avez besoin de **l’URL d’instance ServiceNow** de votre organisation. L’URL de l’instance ServiceNow de votre organisation ressemble généralement **https:// &lt;>.service-now.com**. 

En plus de cette URL, vous aurez besoin d’un compte de **service** pour la configuration de la connexion à ServiceNow et pour permettre à Recherche Microsoft de mettre à jour périodiquement les articles de la base de connaissances en fonction de la planification de l’actualisation. Le compte de service aura besoin d’un accès en lecture aux enregistrements de **table ServiceNow** suivants pour analyser correctement différentes entités.

**Fonctionnalité** | **Accéder en lecture aux tableaux requis** | **Description**
--- | --- | ---
Articles de la base de connaissances d’index disponibles pour <em>tout le monde</em> | kb_knowledge | Pour l’analyse des articles de la base de connaissances
Indexer et soutenir les autorisations des critères utilisateur | kb_uc_can_read_mtom | Qui lire cette base de connaissances
| | kb_uc_can_contribute_mtom | Qui peuvent contribuer à cette base de connaissances
| | kb_uc_cannot_read_mtom | Qui ne peut pas lire cette base de connaissances
| | kb_uc_cannot_contribute_mtom | Qui ne peut pas contribuer à cette base de connaissances
| | sys_user | Lire le tableau de l’utilisateur
| | sys_user_has_role | Lire les informations de rôle des utilisateurs
| | sys_user_grmember | Lire l’appartenance aux groupes d’utilisateurs
| | user_criteria | Autorisations de lecture des critères utilisateur
| | kb_knowledge_base | Lire les informations de la base de connaissances

Vous pouvez **créer et attribuer un rôle** pour le compte de service que vous utilisez pour vous connecter à Recherche Microsoft. [Découvrez comment attribuer un rôle pour les comptes ServiceNow.](https://docs.servicenow.com/bundle/paris-platform-administration/page/administer/users-and-groups/task/t_AssignARoleToAUser.html) L’accès en lecture aux tables peut être affecté au rôle créé. Pour en savoir plus sur la définition de l’accès en lecture aux enregistrements de table, voir [Sécurisation des enregistrements de table.](https://developer.servicenow.com/dev.do#!/learn/learning-plans/orlando/new_to_servicenow/app_store_learnv2_securingapps_orlando_creating_and_editing_access_controls) 


>[!NOTE]
> ServiceNow Graph Connector peut indexer les articles de connaissances et les autorisations des critères utilisateur sans scripts avancés. Si un critère utilisateur contient un script avancé, tous les articles de la base de connaissances associés seront masqués dans les résultats de recherche.

Pour authentifier et synchroniser le contenu à partir de ServiceNow, choisissez **l’une des trois méthodes** prise en charge : 
 
- Authentification de base 
- ServiceNow OAuth (recommandé)
- Azure AD OpenID Connecter

## <a name="step-31-basic-authentication"></a>Étape 3.1 : Authentification de base

Entrez le nom d’utilisateur et le mot de passe du compte ServiceNow avec le rôle **de** connaissance pour vous authentifier auprès de votre instance.

## <a name="step-32-servicenow-oauth"></a>Étape 3.2 : ServiceNow OAuth

Pour utiliser ServiceNow OAuth pour l’authentification, un administrateur ServiceNow doit mettre en service un point de terminaison dans votre instance ServiceNow, afin que l’application Recherche Microsoft puisse y accéder. Pour plus d’informations, voir [Créer un point de terminaison](https://docs.servicenow.com/bundle/newyork-platform-administration/page/administer/security/task/t_CreateEndpointforExternalClients.html) pour que les clients accèdent à l’instance dans la documentation ServiceNow.

Le tableau suivant fournit des instructions sur la façon de remplir le formulaire de création de point de terminaison :

Champ | Description | Valeur recommandée 
--- | --- | ---
Nom | Valeur unique qui identifie l’application pour qui vous avez besoin d’un accès OAuth. | Recherche Microsoft
ID du client | ID unique généré automatiquement en lecture seule pour l’application. L’instance utilise l’ID client lorsqu’elle demande un jeton d’accès. | N/A
Secret client | Avec cette chaîne secrète partagée, l’instance ServiceNow et Recherche Microsoft autoriser les communications entre eux. | Suivez les meilleures pratiques en matière de sécurité en traitant le secret comme un mot de passe.
URL de redirection | URL de rappel requise vers qui le serveur d’autorisation redirige. | https://gcs.office.com/v1.0/admin/oauth/callback
Logo URL | URL qui contient l’image du logo de l’application. | N/A
Actif | Activez la case à cocher pour que le Registre de l’application soit actif. | Définir sur actif
Durée de vie du jeton d’actualisation | Nombre de secondes de validité d’un jeton d’actualisation. Par défaut, les jetons d’actualisation expirent dans 100 jours (8 640 000 secondes). | 31 536 000 (1 an)
Durée de vie du jeton d’accès | Nombre de secondes de validité d’un jeton d’accès. | 43 200 (12 heures)

Entrez l’ID client et la secret client pour vous connecter à votre instance. Une fois connecté, utilisez les informations d’identification d’un compte ServiceNow pour authentifier l’autorisation d’analyse. Le compte doit au moins avoir un **rôle de** connaissance. Reportez-vous au tableau au début de l’étape 3 : [paramètres](#step-3-connection-settings) de connexion pour fournir un accès en lecture à d’autres enregistrements de table ServiceNow et indexer les autorisations des critères utilisateur.

## <a name="step-33-azure-ad-openid-connect"></a>Étape 3.3 : Azure AD OpenID Connecter

Pour utiliser Azure AD OpenID Connecter pour l’authentification, suivez les étapes ci-dessous.

### <a name="step-331-register-a-new-application-in-azure-active-directory"></a>Étape 3.3.1 : inscrire une nouvelle application dans Azure Active Directory

Pour en savoir plus sur l’inscription d’une nouvelle application dans Azure Active Directory, voir [Inscrire une application.](/azure/active-directory/develop/quickstart-register-app#register-an-application) Sélectionnez l’annuaire d’organisation client unique. L’URI de redirection n’est pas nécessaire. Après l’inscription, notez l’ID de l’application (client) et l’ID d’annuaire (client).

### <a name="step-332-create-a-client-secret"></a>Étape 3.3.2 : Créer une secret client

Pour en savoir plus sur la création d’une secret client, voir [Création d’une question secrète client.](/azure/active-directory/develop/quickstart-register-app#add-a-client-secret) Prenez note de la secret client.

### <a name="step-333-retrieve-service-principal-object-identifier"></a>Étape 3.3.3 : Récupérer l’identificateur d’objet principal du service

Suivez les étapes pour récupérer l’identificateur d’objet principal du service

1. Exécutez PowerShell.

2. Installez Azure PowerShell à l’aide de la commande suivante.

   ```powershell
   Install-Module -Name Az -AllowClobber -Scope CurrentUser
   ```

3. Connecter azure.

   ```powershell
   Connect-AzAccount
   ```

4. Obtenir l’identificateur d’objet principal du service.

   ```powershell
   Get-AzADServicePrincipal -ApplicationId "Application-ID"
   ```
   Remplacez « Application-ID » par l’ID d’application (client) (sans guillemets) de l’application que vous avez inscrite à l’étape 3.a. Notez la valeur de l’objet ID à partir de la sortie PowerShell. Il s’agit de l’ID principal de service.

Vous avez maintenant toutes les informations requises à partir du portail Azure. Un résumé rapide des informations est présenté dans le tableau ci-dessous.

Propriété | Description 
--- | ---
ID d’annuaire (ID de client) | ID unique du client Azure Active Directory, à l’étape 3.a.
ID d’application (ID client) | ID unique de l’application inscrite à l’étape 3.a.
Clé secrète client | Clé secrète de l’application (à partir de l’étape 3.b). Traitez-le comme un mot de passe.
Service Principal ID | Identité de l’application en cours d’exécution en tant que service. (à partir de l’étape 3.c)

### <a name="step-334-register-servicenow-application"></a>Étape 3.3.4 : inscrire l’application ServiceNow

L’instance ServiceNow a besoin de la configuration suivante :

1. Inscrivez une nouvelle entité OAuth OIDC. Pour en savoir plus, [voir Créer un fournisseur OAuth OIDC.](https://docs.servicenow.com/bundle/orlando-platform-administration/page/administer/security/task/add-OIDC-entity.html)

2. Le tableau suivant fournit des instructions sur la façon de remplir le formulaire d’inscription du fournisseur OIDC

   Champ | Description | Valeur recommandée
   --- | --- | ---
   Nom | Nom unique qui identifie l’entité OIDC OAuth. | Azure Active Directory
   ID du client | ID client de l’application inscrite sur le serveur OAuth OIDC tiers. L’instance utilise l’ID client lors de la demande d’un jeton d’accès. | ID d’application (client) de l’étape 3.a
   Clé secrète client | La secret client de l’application inscrite sur le serveur OAuth OIDC tiers. | Secret client de l’étape 3.b

   Toutes les autres valeurs peuvent être par défaut.

3. Dans le formulaire d’inscription du fournisseur OIDC, vous devez ajouter une nouvelle configuration de fournisseur OIDC. Sélectionnez l’icône de recherche par rapport au champ Configuration du fournisseur *OAuth OIDC* pour ouvrir les enregistrements des configurations OIDC. Sélectionnez Nouveau.

4. Le tableau suivant fournit des instructions sur la façon de remplir le formulaire de configuration du fournisseur OIDC

   Champ | Valeur recommandée
   --- | ---
   Fournisseur OIDC |  Azure Active Directory
   URL de métadonnées OIDC | L’URL doit prendre la forme https \: //login.microsoftonline.com/<tenandId">/.well-known/openid-configuration <br/>Remplacez « tenantID » par l’ID d’annuaire (client) de l’étape 3.a.
   Durée de vie du cache de configuration OIDC |  120
   Application | Global
   Revendication utilisateur | sub
   Champ Utilisateur | ID utilisateur
   Activer la vérification des revendications JTI | Désactivé

5. Sélectionnez Envoyer et mettre à jour le formulaire d’entité OAuth OIDC.

### <a name="step-335-create-a-servicenow-account"></a>Étape 3.3.5 : Créer un compte ServiceNow

Reportez-vous aux instructions pour créer un compte ServiceNow, [créer un utilisateur dans ServiceNow](https://docs.servicenow.com/bundle/paris-platform-administration/page/administer/users-and-groups/task/t_CreateAUser.html).

Le tableau suivant fournit des instructions sur la façon de remplir l’inscription du compte d’utilisateur ServiceNow

Champ | Valeur recommandée
--- | ---
ID utilisateur | ID principal de service de l’étape 3.c
Accès au service Web uniquement | Checked

Toutes les autres valeurs peuvent être laissées à la valeur par défaut.

### <a name="step-336-enable-knowledge-role-for-the-servicenow-account"></a>Étape 3.3.6 : activer le rôle De connaissances pour le compte ServiceNow

Accédez au compte ServiceNow que vous avez créé avec l’ID principal ServiceNow en tant qu’ID d’utilisateur et attribuez le rôle de connaissance. Vous pouvez trouver ici des instructions sur l’attribution d’un rôle à un compte ServiceNow, en [attribuant](https://docs.servicenow.com/bundle/paris-platform-administration/page/administer/users-and-groups/task/t_AssignARoleToAUser.html)un rôle à un utilisateur. Reportez-vous au tableau au début de l’étape 3 : [paramètres](#step-3-connection-settings) de connexion pour fournir un accès en lecture à d’autres enregistrements de table ServiceNow et indexer les autorisations des critères utilisateur.

Utilisez l’ID d’application comme ID client (à partir de l’étape 3.a) et la secret client (à partir de l’étape 3.b) dans l’Assistant configuration du centre d’administration pour vous authentifier auprès de votre instance ServiceNow à l’aide d’Azure AD OpenID Connecter.

## <a name="step-4-select-properties-and-filter-data"></a>Étape 4 : sélectionner les propriétés et filtrer les données

Dans cette étape, vous pouvez ajouter ou supprimer des propriétés disponibles de votre source de données ServiceNow. Microsoft 365 a déjà sélectionné quelques propriétés par défaut.

Avec une chaîne de requête ServiceNow, vous pouvez spécifier des conditions pour la synchronisation des articles. Il s’agit **d’une** clause Where dans une **SQL Select.** Par exemple, vous pouvez choisir d’indexer uniquement les articles publiés et actifs. Pour en savoir plus sur la création de votre propre chaîne de requête, voir Générer une chaîne de requête [codée à l’aide d’un filtre.](https://docs.servicenow.com/bundle/paris-platform-user-interface/page/use/using-lists/task/t_GenEncodQueryStringFilter.html)

Utilisez le bouton aperçu des résultats pour vérifier les exemples de valeurs des propriétés et du filtre de requête sélectionnés.

## <a name="step-5-manage-search-permissions"></a>Étape 5 : Gérer les autorisations de recherche

Le connecteur ServiceNow prend en  charge les autorisations de recherche visibles par tout le monde ou uniquement par les personnes ayant **accès à cette source de données.** Les données indexées apparaissent dans les résultats de la recherche et sont visibles par tous les utilisateurs de l’organisation ou les utilisateurs qui y ont accès via l’autorisation des critères utilisateur, respectivement. Si un article de base de connaissances n’est pas activé avec des critères utilisateur, il apparaît dans les résultats de recherche de tous les membres de l’organisation.

ServiceNow Graph Connector prend en charge les autorisations de critères utilisateur par défaut sans scripts avancés. Lorsque le connecteur rencontre des critères utilisateur avec un script avancé, toutes les données utilisant ces critères utilisateur n’apparaissent pas dans les résultats de la recherche.

>[!NOTE]
>Pour choisir uniquement **les personnes ayant accès à cette source de** données, activez les mises à jour de publication ciblées sur votre client. Pour en savoir plus sur la configuration de la version ciblée, consultez [les options de publication ciblée du programme d’installation.](/microsoft-365/admin/manage/release-options-in-office-365?preserve-view=true&view=o365-worldwide)

Si vous choisissez uniquement les personnes ayant accès à cette **source** de données, vous devez choisir si votre instance ServiceNow dispose d’utilisateurs Azure Active Directory (AAD) ou d’utilisateurs non AAD.

>[!NOTE]
>Si vous choisissez AAD comme type de source d’identité, assurez-vous que vous affectez la propriété source UserPrincipalName (UPN) à la propriété ciblée de messagerie dans ServiceNow. Pour vérifier ou modifier vos mappages, voir Personnalisation des mappages d’attributs de mise en service utilisateur pour les [applications SaaS dans Azure Active Directory](/azure/active-directory/app-provisioning/customize-application-attributes).

Si vous avez choisi « non-AAD » pour le type d’identité, voir Mappage de vos [identités non-Azure AD](map-non-aad.md) pour obtenir des instructions sur le mappage des identités. 

Vous pouvez également consulter la vidéo suivante pour en savoir plus sur la gestion des autorisations de recherche.

[![Gestion des autorisations de recherche dans Microsoft Graph Connector for ServiceNow](https://img.youtube.com/vi/TVSkJpk1RiE/hqdefault.jpg)](https://www.youtube.com/watch?v=TVSkJpk1RiE)

## <a name="step-6-assign-property-labels"></a>Étape 6 : Attribuer des étiquettes de propriété

Suivez les instructions d’installation générales.

## <a name="step-7-manage-schema"></a>Étape 7 : Gérer le schéma

Suivez les instructions d’installation générales.

## <a name="step-8-choose-refresh-settings"></a>Étape 8 : Choisir les paramètres d’actualisation

Suivez les instructions d’installation générales.

>[!NOTE]
>Pour les identités, seule l’analyse complète programmée sera appliquée.

## <a name="step-9-review-connection"></a>Étape 9 : Examiner la connexion

Suivez les [instructions d’installation générales.](./configure-connector.md)

Le connecteur Graph ServiceNow présente les limitations suivantes dans sa dernière version :

Après avoir publié la connexion, vous devez personnaliser la page des résultats de la recherche. Pour en savoir plus sur la personnalisation des résultats de recherche, voir [Personnaliser la page des résultats de la recherche.](/microsoftsearch/configure-connector#next-steps-customize-the-search-results-page)

## <a name="limitations"></a>Limites
Le connecteur Graph ServiceNow présente les limitations suivantes dans sa dernière version :
- L’indexation des articles de la base de connaissances accessibles à tous les membres d’une organisation est une fonctionnalité généralement disponible.
- *Seules les personnes ayant accès* à cette fonctionnalité de source de données dans l’étape Gérer les autorisations de recherche sont dans le canal de publication ciblé et traitent uniquement les autorisations des [critères](https://hi.service-now.com/kb_view.do?sysparm_article=KB0550924) utilisateur. Tout autre type d’autorisation d’accès ne sera pas appliqué dans les résultats de la recherche.
- Les critères utilisateur avec des scripts avancés ne sont pas pris en charge dans la version actuelle. Tous les articles de la base de connaissances avec une telle restriction d’accès seront indexés avec refuser l’accès à tout le monde, c’est-à-dire qu’ils n’apparaîtront pas dans les résultats de la recherche pour les utilisateurs tant que nous ne les auront pas supportés.

## <a name="troubleshooting"></a>Résolution des problèmes
Après avoir publié votre connexion, personnalisé la page des résultats, vous pouvez passer en revue l’état sous l’onglet **Sources** de données dans le [Centre d’administration.](https://admin.microsoft.com) Pour découvrir comment effectuer des mises à jour et des suppressions, voir [Gérer votre connecteur.](manage-connector.md)
Vous trouverez ci-dessous les étapes de résolution des problèmes couramment observés.
### <a name="1-unable-to-login-due-to-single-sign-on-enabled-servicenow-instance"></a>1. Impossible de se connecter en raison de l'Sign-On service ServiceNow activée

Si votre organisation a activé l'Sign-On (SSO) sur ServiceNow, vous risquez de ne pas pouvoir vous connecter avec le compte de service. Vous pouvez afficher la connexion basée <em> `login.do` </em> sur le nom d’utilisateur et le mot de passe en ajoutant l’URL de l’instance ServiceNow. Exemple. `https://<your-organization-domain>.service-now.com./login.do` 

### <a name="2-unauthorized-or-forbidden-response-to-api-request"></a>2. Réponse non autorisée ou interdite à la demande d’API

#### <a name="21-check-table-access-permissions"></a>2.1. Vérifier les autorisations d’accès aux tables
Si vous voyez une réponse interdite ou non autorisée dans l’état de connexion, vérifiez si le compte de service a requis l’accès aux tables mentionnées à l’étape [3 : paramètres de connexion.](#step-3-connection-settings) Vérifiez si toutes les colonnes des tableaux ont un accès en lecture.

#### <a name="22-check-if-servicenow-instance-behind-firewall"></a>2.2. Vérifier si l’instance ServiceNow est derrière le pare-feu
Graph Le connecteur peut ne pas être en mesure d’atteindre votre instance ServiceNow si elle se trouve derrière un pare-feu réseau. Vous devez autoriser explicitement l’accès Graph service Connecteur. Vous trouverez la plage d’adresses IP publiques Graph Service Connecteur dans le tableau ci-dessous. En fonction de votre région de client, ajoutez-la à votre liste blanche réseau d’instances ServiceNow.

**Environnement** | **Région** | **Range**
--- | --- | ---
PROD | Amérique du Nord | 52.250.92.252/30, 52.224.250.216/30
PROD | Europe | 20.54.41.208/30, 51.105.159.88/30 
PROD | Asie-Pacifique | 52.139.188.212/30, 20.43.146.44/30 


Si vous avez d’autres problèmes ou souhaitez nous faire part de vos commentaires, écrivez-nous [aka.ms/TalkToGraphConnectors](https://aka.ms/TalkToGraphConnectors)
