---
title: Connecteur de sites Web d’entreprise pour Microsoft Search
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
description: Configurer le connecteur de sites Web d’entreprise pour Microsoft Search
ms.openlocfilehash: 443e903e0fa371d2a056fd4bf06310eb2627b11c
ms.sourcegitcommit: 031e7c595496d9faed9038725b04f3c8b5f9ccbd
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/09/2020
ms.locfileid: "49604772"
---
<!-- markdownlint-disable no-inline-html -->
# <a name="enterprise-websites-connector"></a>Connecteur de sites Web d’entreprise

Avec le connecteur de sites Web d’entreprise, votre organisation peut indexer des articles et du **contenu à partir de ses sites Web internes**. Une fois que vous avez configuré le connecteur et synchronisé le contenu à partir du site Web, les utilisateurs finaux peuvent rechercher ce contenu à partir de n’importe quel client Microsoft Search.

Cet article est destiné aux administrateurs [365 de Microsoft](https://www.microsoft.com/microsoft-365) ou toute personne qui configure, exécute et surveille un connecteur de sites Web d’entreprise. Elle explique comment configurer les fonctionnalités de connecteur et de connecteur, ainsi que les restrictions et les techniques de résolution des problèmes.  

## <a name="connection-settings"></a>Paramètres de connexion

Pour vous connecter à votre source de données, vous devez renseigner l’URL racine du site Web, sélectionner une source d’analyse et le type d’authentification que vous souhaitez utiliser : aucun, authentification de base ou OAuth 2,0 avec [Azure Active Directory (Azure AD)](https://docs.microsoft.com/azure/active-directory/). Une fois ces informations terminées, cliquez sur tester la connexion pour vérifier vos paramètres.

### <a name="url"></a>URL

Utilisez le champ URL pour spécifier la racine du site Web que vous souhaitez analyser. Le connecteur de sites Web d’entreprise utilisera cette URL comme point de départ et suivra tous les liens de cette URL pour son analyse.

### <a name="crawl-mode-cloud-or-on-premises-preview"></a>Mode d’analyse : Cloud ou local (aperçu)

Le mode d’analyse détermine le type de sites Web que vous souhaitez indexer, sur le Cloud ou sur site. Pour vos sites Web Cloud, sélectionnez **Cloud** comme mode d’analyse.

De plus, le connecteur prend désormais en charge l’analyse des sites Web locaux. Ce mode est en mode aperçu. Pour accéder à vos données locales, vous devez d’abord installer et configurer l’agent connecteur Graph. Pour en savoir plus, consultez la rubrique [Graph Connector agent](https://docs.microsoft.com/microsoftsearch/on-prem-agent).

Pour vos sites Web locaux, sélectionnez **agent** comme mode d’analyse et, dans le champ **agent local** , sélectionnez l’agent connecteur Graph que vous avez installé et configuré précédemment.  

![Capture d’écran du volet Paramètres de connexion pour Enterprise Web Connector](media/enterprise-web-connector/connectors-enterpriseweb-settings.png)

### <a name="authentication"></a>Authentification

L’authentification de base nécessite un nom d’utilisateur et un mot de passe. Créez ce compte bot à l’aide du [Centre d’administration Microsoft 365](https://admin.microsoft.com).

OAuth 2,0 avec [Azure ad](https://docs.microsoft.com/azure/active-directory/) requiert un ID de ressource, un ID client et une clé secrète client. OAuth 2,0 fonctionne uniquement avec le mode Cloud.

Pour plus d’informations, consultez la rubrique [autoriser l’accès aux applications Web Azure Active Directory à l’aide du flux d’octroi de code OAuth 2,0](https://docs.microsoft.com/azure/active-directory/develop/v1-protocols-oauth-code). Inscrivez-vous avec les valeurs suivantes :

**Nom :** Microsoft Search <br/>
**Redirect_URI :**`https://gcs.office.com/v1.0/admin/oauth/callback`

Pour obtenir les valeurs de la ressource, client_id et client_secret, accédez à **utiliser le code d’autorisation pour demander un jeton d’accès** sur la page Web URL de redirection.

Pour plus d’informations, consultez [la rubrique QuickStart : inscrire une application avec la plateforme d’identité Microsoft](https://docs.microsoft.com/azure/active-directory/develop/quickstart-register-app).

## <a name="support-for-robotstxt"></a>Prise en charge des robots.txt

Le connecteur vérifie s’il existe un fichier de robots.txt pour votre site racine et, s’il en existe un, il suit et respecte les instructions contenues dans ce fichier. Si vous ne souhaitez pas que le connecteur analyse certaines pages ou certains répertoires de votre site, vous pouvez appeler ces pages ou répertoires dans les déclarations « Disallow » figurant dans votre fichier robots.txt.

## <a name="add-urls-to-exclude"></a>Ajouter des URL à exclure

Vous pouvez éventuellement créer une **liste d’exclusion** pour exclure certaines URL de l’analyse si ce contenu est sensible ou inutile à l’analyse. Pour créer une liste d’exclusion, parcourez l’URL racine. Vous avez la possibilité d’ajouter les URL exclues à la liste lors du processus de configuration.

## <a name="manage-search-permissions"></a>Gérer les autorisations de recherche

Le connecteur de sites Web d’entreprise ne prend en charge que les autorisations de recherche visibles par **tous**. Les données indexées apparaissent dans les résultats de la recherche et sont visibles par tous les utilisateurs de l’organisation.

## <a name="assign-property-labels"></a>Affecter des étiquettes de propriété

Vous pouvez affecter une propriété source à chaque étiquette en choisissant dans un menu d’options. Si cette étape n’est pas obligatoire, le fait d’avoir des étiquettes de propriété améliore la pertinence de la recherche et garantit des résultats de recherche plus précis pour les utilisateurs finaux.

## <a name="manage-schema"></a>Gérer le schéma

Dans l' **écran gérer le schéma** , vous avez la possibilité de modifier les attributs de schéma (**Queryable**, pouvant faire l’objet d’une **recherche**, l' **extraction** et l' **refinable**) associés aux propriétés, d’ajouter des alias facultatifs et de choisir la propriété **content** .

## <a name="set-the-refresh-schedule"></a>Définir la planification d’actualisation

Le connecteur de sites Web d’entreprise ne prend en charge qu’une actualisation complète. Cela signifie que le connecteur analysera de tout le contenu du site Web pendant chaque actualisation. Pour vous assurer que le connecteur dispose de suffisamment de temps pour analyser le contenu, nous vous recommandons de définir un intervalle de planification d’actualisation important. Nous vous recommandons d’utiliser une actualisation planifiée entre une et deux semaines.

## <a name="troubleshooting"></a>Résolution des problèmes

Lors de la lecture du contenu du site Web, l’analyse peut rencontrer des erreurs source, qui sont représentées par les codes d’erreur détaillés ci-dessous. Pour plus d’informations sur les types d’erreurs, accédez à la page des détails de l' **erreur** après avoir sélectionné la connexion. Cliquez sur le **code d’erreur** pour afficher des erreurs plus détaillées. Pour en savoir plus, consultez [la rubrique gérer votre connecteur](https://docs.microsoft.com/microsoftsearch/manage-connector) .

 Code d’erreur détaillé | Message d’erreur
 --- | ---
 6001 | Le site qui est essayé d’indexer est inaccessible
 6005 | La page source qui est tentée d’indexer a été bloquée par la configuration par robots.txt.
 6008 | Impossible de résoudre le DNS
 6009 | Pour toutes les erreurs côté client (sauf HTTP 404, 408), consultez la rubrique Codes d’erreur HTTP 4xx pour plus d’informations.
 6013 | La page source en cours d’indexation est introuvable. (Erreur HTTP 404)
 6018 | La page source ne répond pas et la demande a expiré. (Erreur HTTP 408)
 6021 | La page source essayée d’index n’a pas de contenu textuel sur la page.
 6023 | La page source qui est tentée d’index n’est pas prise en charge (pas une page HTML)
 6024 | La page source qui est tentée d’indexer a un contenu non pris en charge.

* Les erreurs 6001-6013 se produisent lorsque la source de données n’est pas accessible à cause d’un problème réseau ou lorsque la source de données elle-même est supprimée, déplacée ou renommée. Vérifiez si les détails de la source de données fournis sont toujours valides.
* Les erreurs 6021-6024 se produisent lorsque la source de données contient du contenu non textuel sur la page ou lorsque la page n’est pas au format HTML. Vérifiez la source de données et ajoutez cette page dans la liste d’exclusions ou ignorez l’erreur.

## <a name="limitations"></a>Limites

Le connecteur de sites Web d’entreprise ne prend pas en charge la recherche de données sur des **pages Web dynamiques**. Exemples de ces pages Web dans des systèmes de gestion de contenu [tels que le](https://www.atlassian.com/software/confluence) [Unily](https://www.unily.com/) et les bases de données qui stockent le contenu du site Web.

## <a name="next-steps"></a>Étapes suivantes

Une fois la connexion publiée, vous devez personnaliser la page des résultats de la recherche. Pour en savoir plus sur la personnalisation des résultats de recherche, voir [personnaliser la page des résultats de la recherche](https://docs.microsoft.com/microsoftsearch/configure-connector#next-steps-customize-the-search-results-page).
