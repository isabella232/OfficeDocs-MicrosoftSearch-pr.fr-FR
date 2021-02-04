---
title: Connecteur Graph Azure DevOps pour Microsoft Search (recherche Microsoft)
ms.author: mecampos
author: mecampos
manager: umas
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: Configurer le connecteur Azure DevOps Graph pour Microsoft Search (recherche Microsoft)
ms.openlocfilehash: 8fe783c847c672223e051f4433af3e41678fe367
ms.sourcegitcommit: d53b91f8f52a4a96281b66831c2449bbffe2177c
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/03/2021
ms.locfileid: "50097402"
---
<!---Previous ms.author: shgrover --->

# <a name="azure-devops-graph-connector-preview"></a>Connecteur Graph Azure DevOps (prévisualisation)

Le connecteur Graph Azure DevOps permet à votre organisation d’indexer des éléments de travail dans son instance du service Azure DevOps. Après avoir configuré le connecteur et indexé le contenu à partir d’Azure DevOps, les utilisateurs finaux peuvent rechercher ces éléments dans Microsoft Search (recherche Microsoft).

> [!NOTE]
> Lisez [**l’article Installation de votre connecteur Graph**](configure-connector.md) pour comprendre le processus d’installation général des connecteurs Graph.

Cet article est réservé à toute personne qui configure, exécute et surveille un connecteur Graph Azure DevOps. Il complète le processus de configuration général et affiche des instructions qui s’appliquent uniquement au connecteur Graph Azure DevOps.

>[!IMPORTANT]
>Le connecteur Azure DevOps prend uniquement en charge le service cloud Azure DevOps. Azure DevOps Server 2019, TFS 2018, TFS 2017, TFS 2015 et TFS 2013 ne sont pas pris en charge par ce connecteur.

<!---## Before you get started-->

<!---Insert "Before you get started" recommendations for this data source-->

## <a name="step-1-add-a-graph-connector-in-the-microsoft-365-admin-center"></a>Étape 1 : Ajouter un connecteur Graph dans le Centre d’administration Microsoft 365

Suivez les [instructions d’installation générales.](https://docs.microsoft.com/microsoftsearch/configure-connector)
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup 
instructions.-->

## <a name="step-2-name-the-connection"></a>Étape 2 : Nommer la connexion

Suivez les [instructions d’installation générales.](https://docs.microsoft.com/microsoftsearch/configure-connector)
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup 
instructions.-->

## <a name="step-3-configure-the-connection-settings"></a>Étape 3 : Configurer les paramètres de connexion

Pour vous connecter à votre instance Azure DevOps, [](https://docs.microsoft.com/azure/devops/organizations/accounts/create-organization) vous avez besoin du nom de votre organisation Azure DevOps, de son ID d’application et de votre secret client pour l’authentification OAuth.

### <a name="register-an-app"></a>Inscrire une application

Inscrivez une application dans Azure DevOps afin que l’application Recherche Microsoft puisse accéder à l’instance. Pour en savoir plus, consultez la documentation Azure DevOps sur l’inscription [d’une application.](https://docs.microsoft.com/azure/devops/integrate/get-started/authentication/oauth?view=azure-devops#register-your-app&preserve-view=true)

Le tableau suivant fournit des instructions sur la façon de remplir le formulaire d’inscription de l’application :

Champs obligatoires | Description | Valeur recommandée
--- | --- | ---
| Nom de la société         | Nom de votre société. | Utiliser une valeur appropriée   |
| Nom de l’application     | Valeur unique qui identifie l’application que vous autorisez.    | Recherche Microsoft     |
| Site web d’application  | URL de l’application qui demande l’accès à votre instance Azure DevOps lors de l’installation du connecteur. (Obligatoire).  | https://<span>gcs.office.</span> com/
| URL de rappel d’autorisation        | URL de rappel requise vers qui le serveur d’autorisation redirige. | https://<span>gcs.office.</span> com/v1.0/admin/oauth/callback|
| Étendues autorisées | Étendue de l’accès pour l’application | Sélectionnez les étendues suivantes : Identité (lecture), Éléments de travail (lecture), Groupes de variables (lecture), Projet et équipe (lecture), Graph (lecture)|

Lors de l’inscription de l’application avec les détails ci-dessus, vous obtenez **l’ID** d’application et la secret **client** qui seront utilisés pour configurer le connecteur.

>[!NOTE]
>Pour révoquer l’accès à toute application inscrite dans Azure DevOps, accédez aux paramètres utilisateur en haut de votre instance Azure DevOps. Sélectionnez Profil, puis autorisations dans la section Sécurité du volet latéral. Pointez sur une application OAuth autorisée pour voir le bouton Révoquer dans le coin des détails de l’application.

### <a name="connection-settings"></a>Paramètres de connexion

Après avoir inscrit l’application Recherche Microsoft auprès d’Azure DevOps, vous pouvez effectuer l’étape des paramètres de connexion. Entrez le nom de votre organisation, l’ID d’application et la secret client.

![Paramètres de l’application de connexion](media/ADO_Connection_settings_2.png)

### <a name="configure-data-select-projects-and-fields"></a>Configurer des données : sélectionner des projets et des champs

Vous pouvez choisir la connexion pour indexer l’ensemble de l’organisation ou des projets spécifiques.

Si vous choisissez d’indexer l’ensemble de l’organisation, les éléments de tous les projets de l’organisation seront indexés. Les nouveaux projets et éléments seront indexés lors de l’analyse suivante après leur création.

Si vous choisissez des projets individuels, seuls les éléments de travail de ces projets seront indexés.

![Configurer des données](media/ADO_Configure_data.png)

Ensuite, sélectionnez les champs que vous souhaitez que la connexion indexe et affiche un aperçu des données dans ces champs avant de poursuivre.

![Choisir les propriétés](media/ADO_choose_properties.png)

## <a name="step-4-manage-search-permissions"></a>Étape 4 : Gérer les autorisations de recherche

Le connecteur Azure DevOps prend en charge les autorisations de recherche visibles uniquement pour les personnes ayant accès à  **cette source** de données ou Tout le **monde.** Si vous choisissez uniquement les personnes ayant accès à cette **source** de données, les données indexées apparaissent dans les résultats de recherche pour les utilisateurs qui y ont accès en fonction des autorisations accordées aux utilisateurs ou groupes au niveau du chemin d’accès Organisation, Projet ou Zone dans Azure DevOps. Si vous choisissez **Tout le** monde, les données indexées apparaissent dans les résultats de recherche pour tous les utilisateurs.

## <a name="step-5-assign-property-labels"></a>Étape 5 : Attribuer des étiquettes de propriété

Suivez les [instructions d’installation générales.](https://docs.microsoft.com/microsoftsearch/configure-connector)

## <a name="step-6-manage-schema"></a>Étape 6 : Gérer le schéma

Suivez les [instructions d’installation générales.](https://docs.microsoft.com/microsoftsearch/configure-connector)

## <a name="step-7-choose-refresh-settings"></a>Étape 7 : Choisir les paramètres d’actualisation

Le connecteur Azure DevOps prend en charge les planifications d’actualisation pour les analyse complètes et incrémentielles.
La planification recommandée est une heure pour une analyse incrémentielle et un jour pour une analyse complète.

## <a name="step-8-review-connection"></a>Étape 8 : Examiner la connexion

Suivez les [instructions d’installation générales.](https://docs.microsoft.com/microsoftsearch/configure-connector)
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup 
instructions.-->

<!---## Troubleshooting-->
<!---Insert troubleshooting recommendations for this data source-->

<!---## Limitations-->
<!---Insert limitations for this data source-->
