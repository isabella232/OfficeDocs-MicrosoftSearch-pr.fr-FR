---
title: Azure DevOps Graph connecteur d’Recherche Microsoft
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
description: Configurer le connecteur Azure DevOps Graph pour Recherche Microsoft
ms.openlocfilehash: fcf381a92ef397f900b300ca667fa80067a6672a
ms.sourcegitcommit: cc9d743bcf5e998720ce9cd6eefb4061d913dc65
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/30/2021
ms.locfileid: "58701389"
---
<!---Previous ms.author: shgrover --->

# <a name="azure-devops-graph-connector-preview"></a>Azure DevOps Graph(prévisualisation)

Le connecteur Azure DevOps Graph permet à votre organisation d’indexer des éléments de travail dans son instance du service Azure DevOps de travail. Après avoir configuré le connecteur et indexé le contenu à partir Azure DevOps, les utilisateurs finaux peuvent rechercher ces éléments dans Recherche Microsoft.

> [!NOTE]
> Lisez [**l’article**](configure-connector.md) Installation de votre connecteur Graph pour comprendre les instructions générales Graph d’installation des connecteurs.

Cet article est réservé à toute personne qui configure, exécute et surveille un connecteur Azure DevOps Graph de connexion. Il complète le processus d’installation général et affiche des instructions qui s’appliquent uniquement au connecteur Azure DevOps Graph de connexion.

>[!IMPORTANT]
>Le connecteur Azure DevOps prend en charge uniquement le service Azure DevOps cloud. Azure DevOps Server 2019, TFS 2018, TFS 2017, TFS 2015 et TFS 2013 ne sont pas pris en charge par ce connecteur.

<!---## Before you get started-->

<!---Insert "Before you get started" recommendations for this data source-->

## <a name="step-1-add-a-graph-connector-in-the-microsoft-365-admin-center"></a>Étape 1 : Ajouter un connecteur Graph dans le Centre d’administration Microsoft 365

Suivez les [instructions d’installation générales.](./configure-connector.md)
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup 
instructions.-->

## <a name="step-2-name-the-connection"></a>Étape 2 : Nommer la connexion

Suivez les [instructions d’installation générales.](./configure-connector.md)
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup 
instructions.-->

## <a name="step-3-configure-the-connection-settings"></a>Étape 3 : Configurer les paramètres de connexion

Pour vous connecter à votre instance Azure DevOps, vous [](/azure/devops/organizations/accounts/create-organization) avez besoin du nom Azure DevOps organisation, de son ID d’application et de votre secret client pour l’authentification OAuth.

### <a name="register-an-app"></a>Inscrire une application

Inscrivez une application dans Azure DevOps pour que l’Recherche Microsoft puisse accéder à l’instance. Pour en savoir plus, consultez Azure DevOps documentation sur l’inscription [d’une application.](/azure/devops/integrate/get-started/authentication/oauth?preserve-view=true&view=azure-devops#register-your-app)

Le tableau suivant fournit des instructions sur la façon de remplir le formulaire d’inscription de l’application :

Champs obligatoires | Description | Valeur recommandée
--- | --- | ---
| Nom de la société         | Nom de votre société. | Utiliser une valeur appropriée   |
| Nom de l’application     | Valeur unique qui identifie l’application que vous autorisez.    | Recherche Microsoft     |
| Site web d’application  | URL de l’application qui demande l’accès à votre instance Azure DevOps lors de l’installation du connecteur. (Obligatoire).  | https://<span>gcs.office.</span> com/
| URL de rappel d’autorisation        | URL de rappel requise vers qui le serveur d’autorisation redirige. | https://<span>gcs.office.</span> com/v1.0/admin/oauth/callback|
| Étendues autorisées | Étendue de l’accès pour l’application | Sélectionnez les étendues suivantes : Identité (lecture), Éléments de travail (lecture), Groupes de variables (lecture), Project et équipe (lecture), Graph (lecture), Analyse (lecture)|

>[!IMPORTANT]
>Les étendues autorisées que vous sélectionnez pour l’application doivent correspondre exactement aux étendues répertoriées ci-dessus. Si vous omettez l’une des étendues autorisées dans la liste ou ajoutez une autre étendue, l’autorisation échoue.

Lors de l’inscription de l’application avec les détails ci-dessus, vous obtenez **l’ID** d’application et la secret **client** qui seront utilisés pour configurer le connecteur.

>[!NOTE]
>Pour révoquer l’accès à toute application inscrite dans Azure DevOps, accédez aux paramètres utilisateur en haut de votre instance Azure DevOps instance. Sélectionnez Profil, puis autorisations dans la section Sécurité du volet latéral. Pointez sur une application OAuth autorisée pour voir le bouton Révoquer dans le coin des détails de l’application.

### <a name="connection-settings"></a>Paramètres de connexion

Après avoir inscrit l Recherche Microsoft appapplation Azure DevOps, vous pouvez effectuer l’étape des paramètres de connexion. Entrez le nom de votre organisation, l’ID d’application et la secret client.

![Connexion application Paramètres.](media/ADO_Connection_settings_2.png)

### <a name="configure-data-select-projects-and-fields"></a>Configurer les données : sélectionner des projets et des champs

Vous pouvez choisir la connexion pour indexer l’ensemble de l’organisation ou des projets spécifiques.

Si vous choisissez d’indexer l’ensemble de l’organisation, les éléments de tous les projets de l’organisation seront indexés. Les nouveaux projets et éléments seront indexés lors de l’analyse suivante après leur création.

Si vous choisissez des projets individuels, seuls les éléments de travail de ces projets seront indexés.

![Configurez les données.](media/ADO_Configure_data.png)

Ensuite, sélectionnez les champs que vous souhaitez que la connexion indexe et affiche un aperçu des données dans ces champs avant de poursuivre.

![Choisissez les propriétés.](media/ADO_choose_properties.png)

## <a name="step-4-manage-search-permissions"></a>Étape 4 : Gérer les autorisations de recherche

Le connecteur Azure DevOps prend en charge les autorisations de recherche visibles uniquement pour les personnes ayant accès à  **cette source de données** ou Tout le **monde.** Si vous choisissez uniquement les personnes ayant accès à cette **source** de données, les données indexées apparaissent dans les résultats de recherche pour les utilisateurs qui y ont accès en fonction des autorisations accordées aux utilisateurs ou groupes au niveau organisation, Project ou chemin d’accès de la zone dans Azure DevOps. Si vous choisissez **Tout le** monde, les données indexées apparaissent dans les résultats de recherche pour tous les utilisateurs.

## <a name="step-5-assign-property-labels"></a>Étape 5 : Attribuer des étiquettes de propriété

Suivez les [instructions d’installation générales.](./configure-connector.md)

## <a name="step-6-manage-schema"></a>Étape 6 : Gérer le schéma

Suivez les [instructions d’installation générales.](./configure-connector.md)

## <a name="step-7-choose-refresh-settings"></a>Étape 7 : Choisir les paramètres d’actualisation

Le connecteur Azure DevOps prend en charge les planifications d’actualisation pour les analyses complètes et incrémentielles.
La planification recommandée est d’une heure pour une analyse incrémentielle et d’un jour pour une analyse complète.

## <a name="step-8-review-connection"></a>Étape 8 : Examiner la connexion

Suivez les [instructions d’installation générales.](./configure-connector.md)

>[!TIP]
>**Type de résultat par défaut**
>* Le connecteur Azure DevOps enregistre automatiquement un [type](./customize-search-page.md#step-2-create-result-types) de résultat une fois le connecteur publié. Le type de résultat utilise [](./customize-results-layout.md) une disposition des résultats générée dynamiquement en fonction des champs sélectionnés à l’étape 3. 
>* Vous pouvez gérer le type de résultat en naviguant vers les [**types de**](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/resulttypes) résultats dans [le Centre d’administration Microsoft 365](https://admin.microsoft.com). Le type de résultat par défaut sera nommé « `ConnectionId` Default ». Par exemple, si votre ID de connexion est , votre disposition des résultats sera nommée `AzureDevOps` : « AzureDevOpsDefault »
>* En outre, vous pouvez choisir de créer votre propre type de résultat si nécessaire.

<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup 
instructions.-->

## <a name="troubleshooting"></a>Résolution des problèmes
Voici une erreur courante observée lors de la configuration du connecteur et sa raison possible.

| Étape de configuration | Message d’erreur | Raisons possibles |
| ------------ | ------------ | ------------ |
|  | `The account associated with the connector doesn't have permission to access the item.` | L’application inscrite ne comprend aucune des étendues OAuth requises. (Remarque : une nouvelle exigence d’étendue OAuth « Analytics:read » a été introduite le 31/08/2021)  |

<!---## Limitations-->
<!---Insert limitations for this data source-->