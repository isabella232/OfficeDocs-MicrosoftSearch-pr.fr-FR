---
title: Connecteur ServiceNow pour Microsoft Search
ms.author: kam1
author: TheKarthikeyan
manager: harshkum
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: Configurer le connecteur ServiceNow pour Microsoft Search
ms.openlocfilehash: 5bcc0870df7c2ad418bb2ae29e9d4d999dcbdf3f
ms.sourcegitcommit: 59cdd3f0f82b7918399bf44d27d9891076090f4f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/20/2020
ms.locfileid: "49367594"
---
# <a name="servicenow-connector"></a>Connecteur ServiceNow

Avec le connecteur ServiceNow, votre organisation peut indexer des Articles de la base de connaissances visibles par tous les utilisateurs ou des autorisations restreintes avec des critères utilisateur au sein de votre organisation. Une fois que vous avez configuré le connecteur et le contenu d’index à partir de ServiceNow, les utilisateurs finals peuvent rechercher ces articles à partir de n’importe quel client Microsoft Search.  

Cet article est destiné aux administrateurs 365 de Microsoft ou toute personne qui configure, exécute et surveille un connecteur ServiceNow. Elle explique comment configurer les fonctionnalités de connecteur et de connecteur, ainsi que les restrictions et les techniques de résolution des problèmes.

Découvrez comment accéder aux connecteurs Microsoft générés à partir de [la configuration de votre connecteur intégré Microsoft pour Microsoft Search](https://docs.microsoft.com/microsoftsearch/configure-connector). La configuration spécifique d’un connecteur ServiceNow est expliquée dans l’article ci-dessous.

## <a name="connection-settings"></a>Paramètres de connexion
Pour vous connecter à vos données ServiceNow, vous avez besoin de l’URL de l' **instance ServiceNow** de votre organisation, des informations d’identification de ce compte, ainsi que de l’ID client et de la clé secrète client pour l’authentification OAuth.  

L’URL de l' **instance ServiceNow** de votre organisation ressemble généralement **&lt; à https://>. service-Now.com**. En plus de cette URL, vous aurez besoin d’un compte pour la configuration de la connexion à ServiceNow, ainsi que pour permettre à Microsoft Search de mettre à jour régulièrement les articles à partir de ServiceNow en fonction de la planification de l’actualisation. Le compte doit au moins avoir le rôle de <em>connaissances</em> . [Découvrez comment attribuer des rôles pour les comptes ServiceNow](https://docs.servicenow.com/bundle/paris-platform-administration/page/administer/users-and-groups/task/t_AssignARoleToAUser.html).

>[!NOTE]
>Si vous souhaitez analyser les identités d’utilisateurs et de groupes afin de respecter les autorisations d’accès des Articles de la Knowledge dans les résultats de la recherche Microsoft, le compte doit avoir accès pour lire les enregistrements de tableau suivants dans ServiceNow :
>* kb_uc_can_contribute_mtom
>* kb_uc_can_read_mtom
>* kb_uc_cannot_read_mtom
>* kb_uc_cannot_contribute_mtom
>* sys_user
>* sys_user_has_role
>* sys_user_grmember
>* user_criteria
>* kb_knowledge_base  
> Vous pouvez créer et attribuer un rôle pour le compte que vous utilisez pour vous connecter à Microsoft Search. L’accès en lecture aux tables peut être affecté à ce rôle. Pour en savoir plus sur la définition de l’accès en lecture aux enregistrements de table, consultez la rubrique [sécurisation des enregistrements de tableau](https://developer.servicenow.com/dev.do#!/learn/learning-plans/orlando/new_to_servicenow/app_store_learnv2_securingapps_orlando_creating_and_editing_access_controls).

Pour authentifier et synchroniser le contenu à partir de ServiceNow, choisissez **l’une des trois** méthodes prises en charge : 
1. Authentification de base 
2. ServiceNow OAuth (recommandé)
3. Azure AD OpenID Connect

#### <a name="basic-authentication"></a>Authentification de base

Entrez le nom d’utilisateur et le mot de passe du compte ServiceNow avec le rôle **connaissances** pour s’authentifier auprès de votre instance.

#### <a name="servicenow-oauth"></a>ServiceNow OAuth

Pour utiliser ServiceNow OAuth pour l’authentification, un administrateur ServiceNow doit mettre en service un point de terminaison dans votre instance de ServiceNow, afin que l’application Microsoft Search puisse accéder à l’instance. Pour plus d’informations, reportez-vous à la rubrique [créer un point de terminaison pour les clients pour accéder à l’instance](https://docs.servicenow.com/bundle/newyork-platform-administration/page/administer/security/task/t_CreateEndpointforExternalClients.html) dans la documentation ServiceNow.

Le tableau suivant fournit des instructions sur la façon de remplir le formulaire de création du point de terminaison :

**Field** | **Description** | **Valeur recommandée**
--- | --- | ---
Nom | Cette valeur unique identifie l’application pour laquelle vous avez besoin d’un accès OAuth. | Recherche Microsoft
ID du client | IDENTIFICATEUR unique en lecture seule et généré automatiquement pour l’application. L’instance utilise l’ID client lorsqu’elle demande un jeton d’accès. | N/A
Clé secrète client | Avec cette chaîne secrète partagée, l’instance de ServiceNow et Microsoft Search autorisent les communications les uns avec les autres. | Suivez les meilleures pratiques en matière de sécurité en le traitant comme un mot de passe.
URL de redirection | URL de rappel obligatoire vers laquelle le serveur d’autorisation redirige. | https://gcs.office.com/v1.0/admin/oauth/callback
URL du logo | URL qui contient l’image du logo de l’application. | N/A
Actif | Activez la case à cocher pour activer le registre d’application. | Défini sur actif
Durée de vie des jetons d’actualisation | Nombre de secondes pendant lesquelles un jeton d’actualisation est valide. Par défaut, les jetons d’actualisation expirent dans 100 jours (8640000 secondes). | 31 536 000 (1 an)
Durée de vie du jeton d’accès | Nombre de secondes pendant lesquelles un jeton d’accès est valide. | 43 200 (12 heures)

Entrez l’ID client et la clé secrète client pour vous connecter à votre instance. Une fois connecté, utilisez les informations d’identification d’un compte ServiceNow pour authentifier l’autorisation d’analyse. Le compte doit au moins avoir le rôle de **connaissances** .

#### <a name="azure-ad-openid-connect"></a>Azure AD OpenID Connect

Pour utiliser Azure AD OpenID Connect pour l’authentification, suivez les étapes ci-dessous.

###### <a name="step-1-register-a-new-application-in-azure-active-directory"></a>Étape 1 : enregistrer une nouvelle application dans Azure Active Directory

Pour en savoir plus sur l’enregistrement d’une nouvelle application dans Azure Active Directory, consultez la rubrique [enregistrer une application](https://docs.microsoft.com/azure/active-directory/develop/quickstart-register-app#register-an-application). Sélectionnez annuaire d’organisation client unique. L’URI de redirection n’est pas nécessaire. Après l’enregistrement, notez l’ID d’application (client) et l’ID de répertoire (client).

###### <a name="step-2-create-a-client-secret"></a>Étape 2 : créer une clé secrète client

Pour en savoir plus sur la création d’une clé secrète client, consultez [la rubrique Création d’une clé secrète client](https://docs.microsoft.com/azure/active-directory/develop/quickstart-register-app#add-a-client-secret). Prenez note de la clé secrète client.

###### <a name="step-3-retrieve-service-principal-object-identifier"></a>Étape 3 : récupérer l’identificateur d’objet principal du service

Suivez la procédure pour récupérer l’identificateur d’objet principal du service.

1. Exécuter PowerShell
2. Installez Azure PowerShell à l’aide de la commande suivante :
```<language>
   Install-Module -Name Az -AllowClobber -Scope CurrentUser
```
3. Se connecter à Azure
```<language>
    Connect-AzAccount
```
4. Obtenir l’identificateur de l’objet principal du service
```<language>
   Get-AzADServicePrincipal -ApplicationId "Application-ID"
```
Remplacez « application-ID » par ID d’application (client) (sans guillemets) de l’application que vous avez inscrite à l’étape 1. Notez la valeur de l’objet ID de la sortie PowerShell. Il s’agit de l’ID du principal du service.

Vous disposez maintenant de toutes les informations requises à partir du portail Azure. Un résumé rapide des informations est indiqué dans le tableau ci-dessous.

**Propriété** | **Description**
--- | ---
ID d’annuaire (ID de client) | Il s’agit d’un ID unique qui fait référence au client Azure Active Directory (à partir de l’étape 1).
ID de l’application (ID client) | Il s’agit d’un ID unique qui fait référence à l’application inscrite à l’étape 1.
Clé secrète client | Il s’agit de la clé secrète de l’application (à partir de l’étape 2). Le traiter comme un mot de passe.
ID du principal du service | Identité de l’application en cours d’exécution en tant que service. (de l’étape 3)

###### <a name="step-4-register-servicenow-application"></a>Étape 4 : inscrire l’application ServiceNow

La configuration suivante doit être exécutée dans l’instance ServiceNow.

1. Enregistrer une nouvelle entité OIDC OAuth. Pour en savoir plus, consultez la rubrique [Create an OAUTH OIDC Provider](https://docs.servicenow.com/bundle/orlando-platform-administration/page/administer/security/task/add-OIDC-entity.html).
2. Le tableau suivant fournit des instructions sur la façon de remplir le formulaire d’inscription du fournisseur OIDC

**Field** | **Description** | **Valeur recommandée**
--- | --- | ---
Nom | Nom unique qui identifie l’entité OIDC OAuth. | Azure AD
ID du client | ID client de l’application inscrite dans le serveur OIDC OAuth tiers. L’instance utilise l’ID client lors de la demande d’un jeton d’accès. | ID d’application (client) de l’étape 1
Clé secrète client | Clé secrète client de l’application inscrite dans le serveur OIDC OAuth tiers. | Clé secrète client à partir de l’étape 2

Toutes les autres valeurs peuvent être par défaut.

3. Dans le formulaire d’inscription du fournisseur OIDC, vous devez ajouter une nouvelle configuration de fournisseur OIDC. Cliquez sur l’icône de recherche sur le champ de *configuration du fournisseur OIDC OAuth* pour ouvrir les enregistrements des configurations de OIDC. Cliquez sur Nouveau.
4. Le tableau suivant fournit des instructions sur la façon de remplir le formulaire de configuration du fournisseur OIDC

**Champ** | **Valeur recommandée**
--- | ---
Fournisseur OIDC |  Azure AD
URL de métadonnées OIDC | Il doit être au format https \: //login.microsoftonline.com/« tenandId »/.well-known/OpenID-configuration <br/>Remplacez « tenantID » par l’ID d’annuaire (locataire) de l’étape 1 (sans les guillemets).
Durée de vie du cache de configuration OIDC |  120
Application | Global
Revendication utilisateur | sub
Champ utilisateur | ID utilisateur
Activer la vérification de revendication JTI | Désactivé

5. Cliquez sur envoyer et mettez à jour le formulaire d’entité OIDC OAuth.

###### <a name="step-5-create-a-servicenow-account"></a>Étape 5 : créer un compte ServiceNow

Consultez les instructions pour créer un compte ServiceNow, [créez un utilisateur dans ServiceNow](https://docs.servicenow.com/bundle/paris-platform-administration/page/administer/users-and-groups/task/t_CreateAUser.html).

Le tableau suivant fournit des instructions sur la façon de renseigner l’enregistrement de compte d’utilisateur ServiceNow

**Champ** | **Valeur recommandée**
--- | ---
ID utilisateur | ID de principal de service de l’étape 3
Accès au service Web uniquement | Checked

Toutes les autres valeurs peuvent être conservées par défaut.

###### <a name="step-6-enable-knowledge-role-for-the-servicenow-account"></a>Étape 6 : activer le rôle de connaissances pour le compte ServiceNow

Accédez au compte ServiceNow que vous avez créé avec l’ID de principal ServiceNow en tant qu’ID d’utilisateur et attribuez le rôle de connaissances. Vous trouverez des instructions sur l’affectation d’un rôle à un compte ServiceNow ici, ainsi [qu’un rôle à un utilisateur](https://docs.servicenow.com/bundle/paris-platform-administration/page/administer/users-and-groups/task/t_AssignARoleToAUser.html).

Utilisez ID de l’application comme ID client (de l’étape 1) et clé secrète client (à partir de l’étape 2) de l’Assistant de configuration du centre d’administration pour s’authentifier auprès de votre instance ServiceNow à l’aide d’Azure AD OpenID Connect.

## <a name="filter-data"></a>Filtrer les données

Avec une chaîne de requête ServiceNow, vous pouvez spécifier des conditions pour la synchronisation des articles. Il s’agit d’une clause **Where** d’une instruction **SQL SELECT** . Par exemple, vous pouvez choisir d’indexer uniquement les articles publiés et actifs. Pour en savoir plus sur la création de votre propre chaîne de requête, voir [générer une chaîne de requête codée à l’aide d’un filtre](https://docs.servicenow.com/bundle/paris-platform-user-interface/page/use/using-lists/task/t_GenEncodQueryStringFilter.html).

## <a name="manage-search-permissions"></a>Gérer les autorisations de recherche

Le connecteur ServiceNow prend en charge les autorisations de recherche visibles pour **tous** **les utilisateurs ou uniquement les personnes ayant accès à cette source de données**. Les données indexées apparaissent dans les résultats de la recherche et sont visibles par tous les utilisateurs de l’organisation ou des utilisateurs qui y ont accès respectivement. Le connecteur ServiceNow prend en charge les autorisations par défaut des critères utilisateur sans les scripts avancés. Lorsque le connecteur rencontre un critère utilisateur avec un script avancé, toutes les données utilisant ce critère utilisateur ne sont pas affichées dans les résultats de la recherche.

Si vous choisissez **uniquement des personnes ayant accès à cette source de données**, vous devez préciser si votre instance ServiceNow dispose d’utilisateurs disposant d’Azure Active Directory (AAD) ou d’utilisateurs non AAD.

>[!NOTE]
>Si vous choisissez AAD comme type de source d’identité, vérifiez que vous affectez la propriété source UPN à la propriété e-mail ciblé dans ServiceNow. Pour vérifier ou modifier vos mappages, reportez-vous à la rubrique [Customizing User Provisioning attribute-Mappings for Saas applications in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/app-provisioning/customize-application-attributes).

Si vous avez choisi d’une liste de contrôle d’accès à partir de votre instance ServiceNow et que vous avez sélectionné « non-AAD » pour le type d’identité, voir [mapper vos identités non Azure ad](map-non-aad.md) pour obtenir des instructions sur le mappage des identités.

## <a name="assign-property-labels"></a>Affecter des étiquettes de propriété

Vous pouvez affecter une propriété source à chaque étiquette en choisissant dans un menu d’options. Si cette étape n’est pas obligatoire, le fait d’avoir des étiquettes de propriété améliore la pertinence de la recherche et garantit des résultats de recherche plus précis pour les utilisateurs finaux.

## <a name="manage-schema"></a>Gérer le schéma

Dans l' **écran gérer le schéma** , vous avez la possibilité de modifier les attributs de schéma (**Queryable**, pouvant faire l’objet d’une **recherche**, l' **extraction** et l' **refinable**) associés aux propriétés, d’ajouter des alias facultatifs et de choisir la propriété **content** .

## <a name="set-the-refresh-schedule"></a>Définir la planification d’actualisation

Le connecteur ServiceNow prend en charge les planifications d’actualisation pour les analyses complètes et incrémentielles. Nous vous recommandons de définir les deux.

Une planification d’analyse complète recherche les articles supprimés qui ont été précédemment synchronisés avec l’index Microsoft Search et les articles qui se sont déplacés du filtre de synchronisation. Lorsque vous vous connectez pour la première fois à ServiceNow, une analyse complète est exécutée pour synchroniser tous les Articles de la base de connaissances. Pour synchroniser de nouveaux éléments et effectuer des mises à jour, vous devez planifier des analyses incrémentielles.

La valeur par défaut recommandée est d’un jour pour une analyse complète et de quatre heures pour une analyse incrémentielle.
>[!NOTE]
>Pour les identités, seule l’analyse complète planifiée est appliquée.

## <a name="review-and-publish"></a>Révision et publication

Après avoir configuré votre connecteur, vous pouvez passer en revue et publier la connexion.

## <a name="next-steps"></a>Étapes suivantes

Une fois la connexion publiée, vous devez personnaliser la page des résultats de la recherche. Pour en savoir plus sur la personnalisation des résultats de recherche, voir [personnaliser la page des résultats de la recherche](https://docs.microsoft.com/microsoftsearch/configure-connector#next-steps-customize-the-search-results-page).