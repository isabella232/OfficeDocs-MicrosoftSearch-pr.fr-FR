---
title: Connecteur ServiceNow Graph pour Microsoft Search (recherche Microsoft)
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
description: Configurer le connecteur ServiceNow Graph pour Microsoft Search (recherche Microsoft)
ms.openlocfilehash: 692170ef6f8332418efc7d56a56c6fa1b1cce76c
ms.sourcegitcommit: 5df252e6d0bd67bb1b4c59418aceca8369f5fe42
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51031763"
---
<!---Previous ms.author: kam1 --->

# <a name="servicenow-graph-connector"></a>ServiceNow Graph Connector

Le connecteur ServiceNow Graph permet à votre organisation d’indexer les articles basés sur les connaissances visibles par les utilisateurs en fonction des autorisations des critères utilisateur au sein de votre organisation. Après avoir configuré le connecteur et indexé le contenu à partir de ServiceNow, les utilisateurs peuvent rechercher les articles à partir de n’importe quel client Recherche Microsoft.

> [!NOTE]
> Lisez [**l’article Configuration de votre connecteur Graph**](configure-connector.md) pour comprendre les instructions générales d’installation des connecteurs Graph.

Cet article est réservé à toute personne qui configure, exécute et surveille un connecteur ServiceNow Graph. Il complète le processus de configuration général et affiche des instructions qui s’appliquent uniquement au connecteur ServiceNow Graph. Cet article inclut également des informations [sur la résolution des problèmes](#troubleshooting) et les [limitations.](#limitations)
  
## <a name="step-1-add-a-graph-connector-in-the-microsoft-365-admin-center"></a>Étape 1 : Ajouter un connecteur Graph dans le Centre d’administration Microsoft 365

Suivez les [instructions d’installation générales.](./configure-connector.md)
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-2-name-the-connection"></a>Étape 2 : Nommer la connexion

Suivez les [instructions d’installation générales.](./configure-connector.md)
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-3-connection-settings"></a>Étape 3 : Paramètres de connexion

Pour vous connecter à vos données ServiceNow, utilisez les informations d’identification de **l’URL d’instance ServiceNow** de votre organisation pour ce compte, l’ID client et la question secrète client pour l’authentification OAuth.  

L’URL de **l’instance ServiceNow** de votre organisation ressemble généralement **https:// &lt;>.service-now.com**. Avec cette URL, vous avez besoin d’un compte pour la configuration de la connexion à ServiceNow et pour permettre à Microsoft Search (recherche Microsoft) de mettre à jour les articles à partir de ServiceNow en fonction de la planification d’actualisation. Le compte doit au moins avoir un <em>rôle de</em> connaissance. [Découvrez comment attribuer un rôle pour les comptes ServiceNow.](https://docs.servicenow.com/bundle/paris-platform-administration/page/administer/users-and-groups/task/t_AssignARoleToAUser.html)

>[!NOTE]
>Si vous souhaitez analyser les identités des utilisateurs et des groupes afin d’honorer les autorisations d’accès des articles de la base de connaissances dans les résultats de recherche Microsoft, le compte doit avoir accès pour lire les enregistrements de tableau suivants dans ServiceNow :
>* kb_uc_can_contribute_mtom
>* kb_uc_can_read_mtom
>* kb_uc_cannot_read_mtom
>* kb_uc_cannot_contribute_mtom
>* sys_user
>* sys_user_has_role
>* sys_user_grmember
>* user_criteria
>* kb_knowledge_base  
> Vous pouvez créer et attribuer un rôle pour le compte que vous utilisez pour vous connecter à Microsoft Search (recherche Microsoft). L’accès en lecture aux tables peut être affecté à ce rôle. Pour en savoir plus sur la définition de l’accès en lecture aux enregistrements de table, voir [Sécurisation des enregistrements de table.](https://developer.servicenow.com/dev.do#!/learn/learning-plans/orlando/new_to_servicenow/app_store_learnv2_securingapps_orlando_creating_and_editing_access_controls)

Pour authentifier et synchroniser le contenu à partir de ServiceNow, choisissez **l’une des trois méthodes** prise en charge :

1. Authentification de base
1. ServiceNow OAuth (recommandé)
1. Azure AD OpenID Connect

### <a name="basic-authentication"></a>Authentification de base

Entrez le nom d’utilisateur et le mot de passe du compte ServiceNow avec le rôle **de** connaissance pour vous authentifier auprès de votre instance.

### <a name="servicenow-oauth"></a>ServiceNow OAuth

Pour utiliser ServiceNow OAuth pour l’authentification, provisionnez un point de terminaison dans votre instance ServiceNow. L’application Recherche Microsoft l’utilisera pour accéder à l’instance. Pour plus d’informations, voir [Créer un point de terminaison pour que les clients accèdent](https://docs.servicenow.com/bundle/newyork-platform-administration/page/administer/security/task/t_CreateEndpointforExternalClients.html) à l’instance dans la documentation ServiceNow.

Le tableau suivant fournit des instructions sur la façon de remplir le formulaire de création de point de terminaison :

Champ | Description | Valeur recommandée 
--- | --- | ---
Nom | Valeur unique qui identifie l’application pour qui vous avez besoin d’un accès OAuth. | Recherche Microsoft
ID du client | ID unique généré automatiquement en lecture seule pour l’application. L’instance utilise l’ID client lorsqu’elle demande un jeton d’accès. | N/A
Secret client | Avec cette chaîne secrète partagée, l’instance ServiceNow et Microsoft Search (recherche Microsoft) autorisent les communications entre eux. | Suivez les meilleures pratiques en matière de sécurité en traitant le secret comme un mot de passe.
URL de redirection | URL de rappel requise vers qui le serveur d’autorisation redirige. | https://gcs.office.com/v1.0/admin/oauth/callback
Logo URL | URL qui contient l’image du logo de l’application. | N/A
Actif | Activez la case à cocher pour rendre le Registre d’application actif. | Définir sur actif
Durée de vie du jeton d’actualisation | Nombre de secondes de validité d’un jeton d’actualisation. Par défaut, les jetons d’actualisation expirent dans les 100 jours (8 640 000 secondes). | 31 536 000 (1 an)
Durée de vie du jeton d’accès | Nombre de secondes de validité d’un jeton d’accès. | 43 200 (12 heures)

Entrez l’ID client et la secret client pour vous connecter à votre instance. Une fois connecté, utilisez les informations d’identification d’un compte ServiceNow pour authentifier l’autorisation d’analyse. Le compte doit au moins avoir un **rôle de** connaissance.

### <a name="azure-ad-openid-connect"></a>Azure AD OpenID Connect

Pour utiliser Azure AD OpenID Connect pour l’authentification, suivez les étapes ci-dessous.

## <a name="step-3a-register-a-new-application-in-azure-active-directory"></a>Étape 3.a : Inscrire une nouvelle application dans Azure Active Directory

Pour en savoir plus sur l’inscription d’une nouvelle application dans Azure Active Directory, voir [Inscrire une application.](/azure/active-directory/develop/quickstart-register-app#register-an-application) Sélectionnez l’annuaire d’organisation client unique. L’URI de redirection n’est pas nécessaire. Après l’inscription, notez l’ID de l’application (client) et l’ID d’annuaire (client).

## <a name="step-3b-create-a-client-secret"></a>Étape 3.b : Créer une secret client

Pour en savoir plus sur la création d’une secret client, voir [Création d’une question secrète client.](/azure/active-directory/develop/quickstart-register-app#add-a-client-secret) Prenez note de la secret client.

## <a name="step-3c-retrieve-service-principal-object-identifier"></a>Étape 3.c : Récupérer l’identificateur d’objet principal du service

Suivez les étapes pour récupérer l’identificateur d’objet principal du service

1. Exécutez PowerShell.

2. Installez Azure PowerShell à l’aide de la commande suivante.

   ```powershell
   Install-Module -Name Az -AllowClobber -Scope CurrentUser
   ```

3. Connectez-vous à Azure.

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

## <a name="step-3d-register-servicenow-application"></a>Étape 3.d : inscrire l’application ServiceNow

L’instance ServiceNow a besoin de la configuration suivante :

1. Inscrivez une nouvelle entité OAuth OIDC. Pour en savoir plus, [voir Créer un fournisseur OAuth OIDC.](https://docs.servicenow.com/bundle/orlando-platform-administration/page/administer/security/task/add-OIDC-entity.html)

2. Le tableau suivant fournit des instructions sur la façon de remplir le formulaire d’inscription du fournisseur OIDC

   Champ | Description | Valeur recommandée
   --- | --- | ---
   Nom | Nom unique qui identifie l’entité OIDC OAuth. | Azure AD
   ID du client | ID client de l’application inscrite sur le serveur OAuth OIDC tiers. L’instance utilise l’ID client lors de la demande d’un jeton d’accès. | ID d’application (client) de l’étape 3.a
   Clé secrète client | La secret client de l’application inscrite sur le serveur OAuth OIDC tiers. | Secret client de l’étape 3.b

   Toutes les autres valeurs peuvent être par défaut.

3. Dans le formulaire d’inscription du fournisseur OIDC, vous devez ajouter une nouvelle configuration de fournisseur OIDC. Sélectionnez l’icône de recherche par rapport au champ Configuration du fournisseur *OAuth OIDC* pour ouvrir les enregistrements des configurations OIDC. Sélectionnez Nouveau.

4. Le tableau suivant fournit des instructions sur la façon de remplir le formulaire de configuration du fournisseur OIDC

   Champ | Valeur recommandée
   --- | ---
   Fournisseur OIDC |  Azure AD
   URL des métadonnées OIDC | L’URL doit être au formulaire https \: //login.microsoftonline.com/<tenandId">/.well-known/openid-configuration <br/>Remplacez « tenantID » par l’ID d’annuaire (client) de l’étape 3.a.
   Durée de vie du cache de configuration OIDC |  120
   Application | Global
   Revendication de l’utilisateur | sub
   Champ Utilisateur | ID utilisateur
   Activer la vérification des revendications JTI | Désactivé

5. Sélectionnez Envoyer et mettre à jour le formulaire d’entité OAuth OIDC.

## <a name="step-3e-create-a-servicenow-account"></a>Étape 3.e : Créer un compte ServiceNow

Reportez-vous aux instructions pour créer un compte ServiceNow, [créer un utilisateur dans ServiceNow](https://docs.servicenow.com/bundle/paris-platform-administration/page/administer/users-and-groups/task/t_CreateAUser.html).

Le tableau suivant fournit des instructions sur la façon de remplir l’inscription du compte d’utilisateur ServiceNow

Champ | Valeur recommandée
--- | ---
ID utilisateur | ID principal de service de l’étape 3.c
Accès au service Web uniquement | Checked

Toutes les autres valeurs peuvent être laissées à la valeur par défaut.

## <a name="step-3f-enable-knowledge-role-for-the-servicenow-account"></a>Étape 3.f : Activer le rôle De connaissances pour le compte ServiceNow

Accédez au compte ServiceNow que vous avez créé avec l’ID principal ServiceNow en tant qu’ID d’utilisateur et attribuez le rôle de connaissance. Vous pouvez trouver des instructions sur l’attribution d’un rôle à un compte ServiceNow ici : attribuez un rôle [à un utilisateur.](https://docs.servicenow.com/bundle/paris-platform-administration/page/administer/users-and-groups/task/t_AssignARoleToAUser.html)

Utilisez l’ID d’application comme ID client de l’étape 3.a et la secret client de l’étape 3.b pour vous authentifier auprès de votre instance ServiceNow à l’aide d’Azure AD OpenID Connect.

## <a name="step-4-select-properties-and-filter-data"></a>Étape 4 : sélectionner les propriétés et filtrer les données

Dans cette étape, vous pouvez ajouter ou supprimer des propriétés disponibles de votre source de données ServiceNow. Microsoft 365 a déjà sélectionné quelques propriétés par défaut.

Avec une chaîne de requête ServiceNow, vous pouvez spécifier des conditions pour la synchronisation des articles. Il s’agit **d’une** clause Where dans une **SQL Select.** Par exemple, vous pouvez choisir d’indexer uniquement les articles publiés et actifs. Pour en savoir plus sur la création de votre propre chaîne de requête, voir Générer une chaîne de requête [codée à l’aide d’un filtre.](https://docs.servicenow.com/bundle/paris-platform-user-interface/page/use/using-lists/task/t_GenEncodQueryStringFilter.html)

Utilisez le bouton aperçu des résultats pour vérifier les exemples de valeurs des propriétés et du filtre de requête sélectionnés.

## <a name="step-5-manage-search-permissions"></a>Étape 5 : Gérer les autorisations de recherche

Le connecteur ServiceNow prend en  charge les autorisations de recherche visibles par tout le monde ou uniquement par les personnes ayant **accès à cette source de données.** Les données indexées apparaissent dans les résultats de la recherche et sont visibles par les utilisateurs de l’organisation qui y ont accès respectivement. ServiceNow Connector prend en charge les autorisations de critères utilisateur par défaut sans scripts avancés. Lorsque le connecteur trouve un critère utilisateur avec un script avancé, toutes les données utilisant ces critères utilisateur ne sont pas affichées dans les résultats de la recherche.

Si vous sélectionnez uniquement les personnes ayant accès à cette **source** de données, vous devez choisir si votre instance ServiceNow dispose d’utilisateurs azure Active Directory (AAD) ou d’utilisateurs non-AAD.

>[!NOTE]
>Le connecteur ServiceNow est en **prévisualisation** si vous choisissez uniquement les personnes ayant **accès à cette source de données.**

>[!NOTE]
>Si vous choisissez AAD comme type de source d’identité, assurez-vous que vous affectez la propriété source UPN à la propriété ciblée de messagerie dans ServiceNow. Pour vérifier ou modifier vos mappages, voir Personnalisation des mappages d’attributs de mise en service des utilisateurs pour les [applications SaaS dans Azure Active Directory.](/azure/active-directory/app-provisioning/customize-application-attributes)

Si vous avez choisi d’ing d’une ACL à partir de votre instance ServiceNow et que vous avez sélectionné « non-AAD » pour le type d’identité, voir Mappage de vos [identités non Azure AD](map-non-aad.md) pour obtenir des instructions sur le mappage des identités.

## <a name="step-6-assign-property-labels"></a>Étape 6 : Attribuer des étiquettes de propriété

Suivez les [instructions d’installation générales.](./configure-connector.md)
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-7-manage-schema"></a>Étape 7 : Gérer le schéma

Suivez les [instructions d’installation générales.](./configure-connector.md)
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-8-choose-refresh-settings"></a>Étape 8 : Choisir les paramètres d’actualisation

Suivez les [instructions d’installation générales.](./configure-connector.md)
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

>[!NOTE]
>Pour les identités, seule l’analyse complète programmée sera appliquée.

## <a name="step-9-review-connection"></a>Étape 9 : Examiner la connexion

Suivez les [instructions d’installation générales.](./configure-connector.md)
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="troubleshooting"></a>Résolution des problèmes

Après avoir publié votre connexion, personnalisé la page des résultats, vous pouvez passer en revue l’état sous l’onglet **Connecteurs** dans le [Centre d’administration.](https://admin.microsoft.com) Pour découvrir comment effectuer des mises à jour et des suppressions, voir [Gérer votre connecteur.](manage-connector.md)

## <a name="limitations"></a>Limites

Le connecteur ServiceNow Graph présente les limitations suivantes dans sa dernière version :

- L’indexation des articles de la base de connaissances accessibles à tous les membres d’une organisation est une fonctionnalité généralement disponible.
- *Seules les personnes ayant accès à cette fonctionnalité de source* de données dans l’étape Gérer les autorisations de recherche sont en prévisualisation et traitent uniquement les autorisations des [critères](https://hi.service-now.com/kb_view.do?sysparm_article=KB0550924) utilisateur. Tout autre type d’autorisation d’accès ne sera pas appliqué dans les résultats de la recherche.
- Les critères utilisateur avec des scripts avancés ne sont pas pris en charge dans la version d’évaluation actuelle. Les articles de la base de connaissances avec une restriction d’accès seront indexés avec refuser l’accès à tout le monde et n’apparaîtront dans les résultats de la recherche pour aucun utilisateur tant que nous ne les avons pas supportés.