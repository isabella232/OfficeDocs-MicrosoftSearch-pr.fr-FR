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
ms.openlocfilehash: c4b799a3127a4a302e3f07953a59ea0319a09052
ms.sourcegitcommit: c186be143164f21a3fecdb3037acd90a26c0fcf3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/27/2020
ms.locfileid: "44374334"
---
# <a name="enterprise-websites-connector"></a>Connecteur de sites Web d’entreprise

Avec le connecteur de sites Web d’entreprise, votre organisation peut indexer des articles et du **contenu à partir de ses sites Web internes**. Une fois que vous avez configuré le connecteur et synchronisé le contenu à partir du site Web, les utilisateurs finaux peuvent rechercher ce contenu à partir de n’importe quel client Microsoft Search.

Cet article est destiné aux administrateurs [365 de Microsoft](https://www.microsoft.com/microsoft-365) ou toute personne qui configure, exécute et surveille un connecteur de sites Web d’entreprise. Elle explique comment configurer les fonctionnalités de connecteur et de connecteur, ainsi que les restrictions et les techniques de résolution des problèmes.  

## <a name="connect-to-a-data-source"></a>Se connecter à une source de données 
Pour vous connecter à votre source de données, vous avez besoin de votre URL racine et de votre authentification de base.

### <a name="root-url"></a>URL racine
L’URL racine est celle qui initie l’analyse et qui est utilisée pour l’authentification. Vous pouvez obtenir l’URL à partir de la page d’accueil du site Web que vous souhaitez analyser.

### <a name="authentication"></a>Authentification 
L’authentification de base nécessite un nom d’utilisateur et un mot de passe. Créez ce compte bot à l’aide du [Centre d’administration](https://admin.microsoft.com)Microsoft 365.

## <a name="select-the-source-properties"></a>Sélectionnez les propriétés source. 
Les propriétés sources sont définies en fonction du format de données du site Web d’entreprise. Toutefois, vous pouvez créer une **liste d’exclusion** pour exclure certaines URL de l’analyse si ce contenu est sensible ou inutile à l’analyse. Pour créer une liste d’exclusion, parcourez l’URL racine. Vous avez la possibilité d’ajouter les URL exclues à la liste lors du processus de configuration.

## <a name="manage-search-permissions"></a>Gérer les autorisations de recherche 
Il n’existe pas de prise en charge des listes de contrôle d’accès (ACL). Par conséquent, nous vous recommandons de connecter uniquement les sites Web visibles par tous les utilisateurs au sein de votre organisation.

## <a name="set-the-refresh-schedule"></a>Définir la planification d’actualisation
Le connecteur de sites Web d’entreprise ne prend en charge qu’une analyse complète. Cela signifie que le connecteur lit tout le contenu du site Web pendant chaque analyse. Pour vous assurer que le connecteur dispose de suffisamment de temps pour lire le contenu, nous vous recommandons de définir un intervalle de planification d’actualisation important. Nous vous recommandons une actualisation planifiée entre trois jours et deux semaines. 

## <a name="troubleshooting"></a>Résolution des problèmes
Lors de la lecture du contenu du site Web, l’analyse peut rencontrer des erreurs sources qui sont représentées par les codes d’erreur détaillés ci-dessous. Pour plus d’informations sur les types d’erreurs, accédez à la page des détails de l' **erreur** après avoir sélectionné la connexion. Cliquez sur le **code d’erreur** pour afficher des erreurs plus détaillées. Pour en savoir plus, consultez [la rubrique gérer votre connecteur](https://docs.microsoft.com/microsoftsearch/manage-connector) .

 **Code d’erreur détaillé** | **Message d’erreur**
 --- | --- 
 6001   | Le site qui est essayé d’indexer est inaccessible 
 6005 | La page source en cours d’indexation a été bloquée par en fonction de la configuration d’robots. txt.
 6008 | Impossible de résoudre le DNS
 6009 | Pour toutes les erreurs côté client (sauf HTTP 404, 408), reportez-vous à la rubrique Codes d’erreur HTTP 4xx pour plus de détails.
 6013 | La page source en cours d’indexation est introuvable. (Erreur HTTP 404)
 6018 | La page source ne répond pas et la demande a expiré. (Erreur HTTP 408)
 6021 | La page source essayée d’index n’a pas de contenu textuel sur la page.
 6023 | La page source qui est tentée d’index n’est pas prise en charge (pas une page HTML)
 6024 | La page source qui est tentée d’indexer a un contenu non pris en charge.

* Les erreurs 6001-6013 se produisent lorsque la source de données n’est pas accessible à cause d’un problème réseau ou lorsque la source de données elle-même est supprimée, déplacée ou renommée. Vérifiez si les détails de la source de données fournis sont toujours valides.
* Des erreurs 6021-6024 se produisent lorsque la source de données contient du contenu non textuel sur la page ou lorsque la page n’est pas au format HTML. Vérifiez la source de données et ajoutez cette page dans la liste d’exclusions ou ignorez l’erreur.

## <a name="limitations"></a>Limites
Le connecteur de sites Web d’entreprise ne prend pas en charge la recherche de données sur des **pages Web dynamiques**. Exemples de ces pages Web dans des systèmes de gestion de contenu [tels que le](https://www.atlassian.com/software/confluence) [Unily](https://www.unily.com/) et les bases de données qui stockent le contenu du site Web.
