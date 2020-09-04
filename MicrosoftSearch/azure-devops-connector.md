---
title: Connecteur Azure DevOps pour Microsoft Search
ms.author: shgrover
author: shakungrover05
manager: jeffkizn
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: Configurer Azure DevOps Connector pour Microsoft Search
ms.openlocfilehash: 1030dd2b508e5364f53f92e7c8ce8c12c040ce70
ms.sourcegitcommit: 85d40512e8616c851da1a38c137ca0e4e8625813
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/03/2020
ms.locfileid: "47359720"
---
# <a name="azure-devops-connector"></a>Connecteur DevOps Azure

Avec le connecteur Azure DevOps, votre organisation peut indexer les éléments de travail dans son instance du service Azure DevOps. Une fois que vous avez configuré le connecteur et le contenu d’index à partir d’Azure DevOps, les utilisateurs finals peuvent rechercher ces éléments dans Microsoft Search.

Cet article est destiné aux administrateurs 365 de Microsoft ou toute personne qui configure, exécute et surveille un connecteur DevOps Azure. Elle explique comment configurer les fonctionnalités de connecteur et de connecteur, ainsi que les restrictions et les techniques de résolution des problèmes.

>[!IMPORTANT]
>Le connecteur Azure DevOps prend en charge uniquement le service de Cloud Azure DevOps. Azure DevOps Server 2019, TFS 2018, TFS 2017, TFS 2015 et TFS 2013 ne sont pas pris en charge par ce connecteur.

## <a name="connect-to-a-data-source"></a>Se connecter à une source de données

Pour vous connecter à votre instance Azure DevOps, vous avez besoin de votre nom d' [organisation](https://docs.microsoft.com/azure/devops/organizations/accounts/create-organization) Azure DevOps, de son ID d’application et de la clé secrète client pour l’authentification OAuth.

### <a name="register-an-app"></a>Inscrire une application

Vous devez inscrire une application dans Azure DevOps afin que l’application Microsoft Search puisse accéder à l’instance. Pour plus d’informations, reportez-vous à la documentation Azure DevOps sur l' [enregistrement d’une application](https://docs.microsoft.com/azure/devops/integrate/get-started/authentication/oauth?view=azure-devops#register-your-app).

Le tableau suivant fournit des instructions sur la façon de remplir le formulaire d’inscription de l’application :

 **Champs obligatoires** | **Description**      | **Valeur recommandée**
--- | --- | ---
| Nom de la société         | Il s’agit du nom de votre société. | Utiliser une valeur appropriée   |
| Nom de l’application     | Cette valeur unique identifie l’application que vous autorisez.    | Recherche Microsoft     |
| Site Web d’application  | Ce champ obligatoire est l’URL de l’application qui demandera l’accès à votre instance Azure DevOps lors de la configuration du connecteur.  | <https://gcs.office.com/>                |
| URL de rappel d’autorisation        | URL de rappel obligatoire vers laquelle le serveur d’autorisation redirige. | <https://gcs.office.com/v1.0/admin/oauth/callback>|
| Étendues autorisées | Il s’agit de la portée de l’accès à l’application | Sélectionnez les étendues suivantes : identité (lecture), éléments de travail (lecture), groupes de variables (lecture), projet et équipe (lecture), graphique (lecture)|

Lors de l’inscription de l’application avec les détails ci-dessus, vous obtiendrez l’ID de l' **application** et la **clé secrète client** qui seront utilisés pour configurer le connecteur.

>[!NOTE]
>Pour révoquer l’accès à une application inscrite dans Azure DevOps, accédez à paramètres utilisateur en haut à droite de votre instance de DevOps Azure. Cliquez sur profil, puis sur autorisations dans la section sécurité du volet latéral. Placez le pointeur de la souris sur une application OAuth autorisée pour afficher le bouton révoquer dans le coin des détails de l’application.

### <a name="connection-settings"></a>Paramètres de connexion

Après avoir inscrit l’application Microsoft Search auprès d’Azure DevOps, vous pouvez effectuer l’étape des paramètres de connexion. Entrez le nom de votre organisation, l’ID de l’application et la clé secrète client.

![Paramètres de l’application de connexion](media/ADO_Connection_settings_2.png)

## <a name="select-projects-and-fields"></a>Sélectionner des projets et des champs

Vous pouvez choisir pour la connexion d’indexer l’ensemble de l’organisation ou des projets spécifiques.

Si vous choisissez d’indexer toute l’organisation, les éléments de tous les projets de l’Organisation seront indexés. Les nouveaux projets et éléments seront indexés lors de la prochaine analyse après leur création. Si vous choisissez des projets individuels, seuls les éléments de travail de ces projets seront indexés.

![Configurer les données](media/ADO_Configure_data.png)

Ensuite, sélectionnez les champs pour lesquels vous souhaitez que la connexion indexe et prévisualiser les données dans ces champs avant de poursuivre.

![Choisir les propriétés](media/ADO_choose_properties.png)

## <a name="manage-the-search-schema"></a>Gérer le schéma de recherche

Configurez le mappage du schéma de recherche. Vous pouvez choisir les propriétés à utiliser pour les **requêtes**, les **recherches** et les **extractions**.

## <a name="manage-search-permissions"></a>Gérer les autorisations de recherche

Actuellement, le connecteur Azure DevOps prend uniquement en charge les autorisations **de recherche visibles par tous les utilisateurs**. Les données indexées apparaîtront dans les résultats de recherche pour tous les utilisateurs.

## <a name="set-the-refresh-schedule"></a>Définir la planification d’actualisation

Le connecteur Azure DevOps prend en charge les planifications d’actualisation pour les analyses complètes et incrémentielles. Une analyse complète recherche les éléments de travail supprimés qui ont été précédemment synchronisés avec l’index de recherche Microsoft. Une analyse complète est exécutée pour synchroniser tous les éléments de travail. Pour synchroniser les nouveaux éléments de travail et les mises à jour d’éléments de travail existants, vous devez planifier des analyses incrémentielles.

La planification recommandée est d’une heure pour une analyse incrémentielle et d’un jour pour une analyse complète.
