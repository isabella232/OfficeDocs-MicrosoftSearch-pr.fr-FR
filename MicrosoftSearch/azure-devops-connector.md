---
title: Azure DevOps Graph pour Microsoft Search (recherche Microsoft)
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
description: Configurer le connecteur Azure DevOps Graph pour Microsoft Search (recherche Microsoft)
ms.openlocfilehash: bfe04a022360a968424b673ad03ba05f27c8c333
ms.sourcegitcommit: 1b154441f3a3abba0f2719e66a767432bc9506ca
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/02/2021
ms.locfileid: "52720951"
---
<!---Previous ms.author: shgrover --->

# <a name="azure-devops-graph-connector-preview"></a><span data-ttu-id="95f3b-103">Azure DevOps Graph connecteur de connexion (prévisualisation)</span><span class="sxs-lookup"><span data-stu-id="95f3b-103">Azure DevOps Graph connector (preview)</span></span>

<span data-ttu-id="95f3b-104">Le connecteur Azure DevOps Graph permet à votre organisation d’indexer des éléments de travail dans son instance du service Azure DevOps de travail.</span><span class="sxs-lookup"><span data-stu-id="95f3b-104">The Azure DevOps Graph connector allows your organization to index work items in its instance of the Azure DevOps service.</span></span> <span data-ttu-id="95f3b-105">Après avoir configuré le connecteur et indexé le contenu à partir Azure DevOps, les utilisateurs finaux peuvent rechercher ces éléments dans Microsoft Search (recherche Microsoft).</span><span class="sxs-lookup"><span data-stu-id="95f3b-105">After you configure the connector and index content from Azure DevOps, end users can search for those items in Microsoft Search.</span></span>

> [!NOTE]
> <span data-ttu-id="95f3b-106">Lisez [**l’article**](configure-connector.md) Installation de votre connecteur Graph pour comprendre les instructions générales Graph d’installation des connecteurs.</span><span class="sxs-lookup"><span data-stu-id="95f3b-106">Read the [**Setup for your Graph connector**](configure-connector.md) article to understand the general Graph connectors setup instructions.</span></span>

<span data-ttu-id="95f3b-107">Cet article est réservé à toute personne qui configure, exécute et surveille un connecteur Azure DevOps Graph de connexion.</span><span class="sxs-lookup"><span data-stu-id="95f3b-107">This article is for anyone who configures, runs, and monitors an Azure DevOps Graph connector.</span></span> <span data-ttu-id="95f3b-108">Il complète le processus d’installation général et affiche des instructions qui s’appliquent uniquement au connecteur Azure DevOps Graph de connexion.</span><span class="sxs-lookup"><span data-stu-id="95f3b-108">It supplements the general setup process, and shows instructions that apply only for the Azure DevOps Graph connector.</span></span>

>[!IMPORTANT]
><span data-ttu-id="95f3b-109">Le connecteur Azure DevOps prend en charge uniquement le service Azure DevOps cloud.</span><span class="sxs-lookup"><span data-stu-id="95f3b-109">The Azure DevOps connector supports only the Azure DevOps cloud service.</span></span> <span data-ttu-id="95f3b-110">Azure DevOps Server 2019, TFS 2018, TFS 2017, TFS 2015 et TFS 2013 ne sont pas pris en charge par ce connecteur.</span><span class="sxs-lookup"><span data-stu-id="95f3b-110">Azure DevOps Server 2019, TFS 2018, TFS 2017, TFS 2015, and TFS 2013 are not supported by this connector.</span></span>

<!---## Before you get started-->

<!---Insert "Before you get started" recommendations for this data source-->

## <a name="step-1-add-a-graph-connector-in-the-microsoft-365-admin-center"></a><span data-ttu-id="95f3b-111">Étape 1 : Ajouter un connecteur Graph dans le centre d Microsoft 365'administration</span><span class="sxs-lookup"><span data-stu-id="95f3b-111">Step 1: Add a Graph connector in the Microsoft 365 admin center</span></span>

<span data-ttu-id="95f3b-112">Suivez les [instructions d’installation générales.](./configure-connector.md)</span><span class="sxs-lookup"><span data-stu-id="95f3b-112">Follow the general [setup instructions](./configure-connector.md).</span></span>
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup 
instructions.-->

## <a name="step-2-name-the-connection"></a><span data-ttu-id="95f3b-113">Étape 2 : Nommer la connexion</span><span class="sxs-lookup"><span data-stu-id="95f3b-113">Step 2: Name the connection</span></span>

<span data-ttu-id="95f3b-114">Suivez les [instructions d’installation générales.](./configure-connector.md)</span><span class="sxs-lookup"><span data-stu-id="95f3b-114">Follow the general [setup instructions](./configure-connector.md).</span></span>
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup 
instructions.-->

## <a name="step-3-configure-the-connection-settings"></a><span data-ttu-id="95f3b-115">Étape 3 : Configurer les paramètres de connexion</span><span class="sxs-lookup"><span data-stu-id="95f3b-115">Step 3: Configure the connection settings</span></span>

<span data-ttu-id="95f3b-116">Pour vous connecter à votre instance Azure DevOps, vous [](/azure/devops/organizations/accounts/create-organization) avez besoin du nom Azure DevOps organisation, de son ID d’application et de votre secret client pour l’authentification OAuth.</span><span class="sxs-lookup"><span data-stu-id="95f3b-116">To connect to your Azure DevOps instance, you need your Azure DevOps [organization](/azure/devops/organizations/accounts/create-organization) name, its App ID, and client secret for OAuth authentication.</span></span>

### <a name="register-an-app"></a><span data-ttu-id="95f3b-117">Inscrire une application</span><span class="sxs-lookup"><span data-stu-id="95f3b-117">Register an app</span></span>

<span data-ttu-id="95f3b-118">Inscrivez une application dans Azure DevOps pour que l’application Recherche Microsoft puisse accéder à l’instance.</span><span class="sxs-lookup"><span data-stu-id="95f3b-118">Register an app in Azure DevOps so that the Microsoft Search app can access the instance.</span></span> <span data-ttu-id="95f3b-119">Pour en savoir plus, consultez Azure DevOps documentation sur l’inscription [d’une application.](/azure/devops/integrate/get-started/authentication/oauth?preserve-view=true&view=azure-devops#register-your-app)</span><span class="sxs-lookup"><span data-stu-id="95f3b-119">To learn more, see Azure DevOps documentation on how to [register an app](/azure/devops/integrate/get-started/authentication/oauth?preserve-view=true&view=azure-devops#register-your-app).</span></span>

<span data-ttu-id="95f3b-120">Le tableau suivant fournit des instructions sur la façon de remplir le formulaire d’inscription de l’application :</span><span class="sxs-lookup"><span data-stu-id="95f3b-120">The following table provides guidance on how to fill out the app registration form:</span></span>

<span data-ttu-id="95f3b-121">Champs obligatoires</span><span class="sxs-lookup"><span data-stu-id="95f3b-121">Mandatory Fields</span></span> | <span data-ttu-id="95f3b-122">Description</span><span class="sxs-lookup"><span data-stu-id="95f3b-122">Description</span></span> | <span data-ttu-id="95f3b-123">Valeur recommandée</span><span class="sxs-lookup"><span data-stu-id="95f3b-123">Recommended Value</span></span>
--- | --- | ---
| <span data-ttu-id="95f3b-124">Nom de la société</span><span class="sxs-lookup"><span data-stu-id="95f3b-124">Company Name</span></span>         | <span data-ttu-id="95f3b-125">Nom de votre société.</span><span class="sxs-lookup"><span data-stu-id="95f3b-125">The name of your company.</span></span> | <span data-ttu-id="95f3b-126">Utiliser une valeur appropriée</span><span class="sxs-lookup"><span data-stu-id="95f3b-126">Use an appropriate value</span></span>   |
| <span data-ttu-id="95f3b-127">Nom de l’application</span><span class="sxs-lookup"><span data-stu-id="95f3b-127">Application name</span></span>     | <span data-ttu-id="95f3b-128">Valeur unique qui identifie l’application que vous autorisez.</span><span class="sxs-lookup"><span data-stu-id="95f3b-128">A unique value that identifies the application that you're authorizing.</span></span>    | <span data-ttu-id="95f3b-129">Recherche Microsoft</span><span class="sxs-lookup"><span data-stu-id="95f3b-129">Microsoft Search</span></span>     |
| <span data-ttu-id="95f3b-130">Site web d’application</span><span class="sxs-lookup"><span data-stu-id="95f3b-130">Application website</span></span>  | <span data-ttu-id="95f3b-131">URL de l’application qui demande l’accès à votre instance Azure DevOps lors de l’installation du connecteur.</span><span class="sxs-lookup"><span data-stu-id="95f3b-131">The URL of the application that will request access to your Azure DevOps instance during connector setup.</span></span> <span data-ttu-id="95f3b-132">(Obligatoire).</span><span class="sxs-lookup"><span data-stu-id="95f3b-132">(Required).</span></span>  | <span data-ttu-id="95f3b-133"> https://<span>gcs.office.</span> com/</span><span class="sxs-lookup"><span data-stu-id="95f3b-133">https://<span>gcs.office.</span>com/</span></span>
| <span data-ttu-id="95f3b-134">URL de rappel d’autorisation</span><span class="sxs-lookup"><span data-stu-id="95f3b-134">Authorization callback URL</span></span>        | <span data-ttu-id="95f3b-135">URL de rappel requise vers qui le serveur d’autorisation redirige.</span><span class="sxs-lookup"><span data-stu-id="95f3b-135">A required callback URL that the authorization server redirects to.</span></span> | <span data-ttu-id="95f3b-136"> https://<span>gcs.office.</span> com/v1.0/admin/oauth/callback</span><span class="sxs-lookup"><span data-stu-id="95f3b-136">https://<span>gcs.office.</span>com/v1.0/admin/oauth/callback</span></span>|
| <span data-ttu-id="95f3b-137">Étendues autorisées</span><span class="sxs-lookup"><span data-stu-id="95f3b-137">Authorized scopes</span></span> | <span data-ttu-id="95f3b-138">Étendue de l’accès pour l’application</span><span class="sxs-lookup"><span data-stu-id="95f3b-138">The scope of access for the application</span></span> | <span data-ttu-id="95f3b-139">Sélectionnez les étendues suivantes : Identité (lecture), Éléments de travail (lecture), Groupes de variables (lecture), Project et équipe (lecture), Graph (lecture)</span><span class="sxs-lookup"><span data-stu-id="95f3b-139">Select the following scopes: Identity (read), Work Items (read), Variable Groups (read), Project and team (read), Graph (read)</span></span>|

>[!IMPORTANT]
><span data-ttu-id="95f3b-140">Les étendues autorisées que vous sélectionnez pour l’application doivent correspondre exactement aux étendues répertoriées ci-dessus.</span><span class="sxs-lookup"><span data-stu-id="95f3b-140">The authorized scopes that you select for the app should match the scopes exactly as listed above.</span></span> <span data-ttu-id="95f3b-141">Si vous omettez l’une des étendues autorisées dans la liste ou ajoutez une autre étendue, l’autorisation échoue.</span><span class="sxs-lookup"><span data-stu-id="95f3b-141">If you omit one of the authorized scopes in the list, or add another scope, the authorization will fail.</span></span>

<span data-ttu-id="95f3b-142">Lors de l’inscription de l’application avec les détails ci-dessus, vous obtenez **l’ID** d’application et la secret **client** qui seront utilisés pour configurer le connecteur.</span><span class="sxs-lookup"><span data-stu-id="95f3b-142">On registering the app with the details above, you'll get the **App ID** and **Client Secret** that will be used to configure the connector.</span></span>

>[!NOTE]
><span data-ttu-id="95f3b-143">Pour révoquer l’accès à toute application inscrite dans Azure DevOps, accédez aux paramètres utilisateur en haut de votre instance Azure DevOps instance.</span><span class="sxs-lookup"><span data-stu-id="95f3b-143">To revoke access to any app registered in Azure DevOps, go to User settings at the right top of your Azure DevOps instance.</span></span> <span data-ttu-id="95f3b-144">Sélectionnez Profil, puis autorisations dans la section Sécurité du volet latéral.</span><span class="sxs-lookup"><span data-stu-id="95f3b-144">Select Profile and then select Authorizations in the Security section of the side pane.</span></span> <span data-ttu-id="95f3b-145">Pointez sur une application OAuth autorisée pour voir le bouton Révoquer dans le coin des détails de l’application.</span><span class="sxs-lookup"><span data-stu-id="95f3b-145">Hover over an authorized OAuth app to see the Revoke button at the corner of the app details.</span></span>

### <a name="connection-settings"></a><span data-ttu-id="95f3b-146">Paramètres de connexion</span><span class="sxs-lookup"><span data-stu-id="95f3b-146">Connection settings</span></span>

<span data-ttu-id="95f3b-147">Après avoir inscrit l’application Recherche Microsoft Azure DevOps, vous pouvez effectuer l’étape des paramètres de connexion.</span><span class="sxs-lookup"><span data-stu-id="95f3b-147">After registering the Microsoft Search app with Azure DevOps, you can complete the connection settings step.</span></span> <span data-ttu-id="95f3b-148">Entrez le nom de votre organisation, l’ID d’application et la secret client.</span><span class="sxs-lookup"><span data-stu-id="95f3b-148">Enter your organization name, App ID, and Client secret.</span></span>

![Connection Application Paramètres](media/ADO_Connection_settings_2.png)

### <a name="configure-data-select-projects-and-fields"></a><span data-ttu-id="95f3b-150">Configurer des données : sélectionner des projets et des champs</span><span class="sxs-lookup"><span data-stu-id="95f3b-150">Configure data: select projects and fields</span></span>

<span data-ttu-id="95f3b-151">Vous pouvez choisir la connexion pour indexer l’ensemble de l’organisation ou des projets spécifiques.</span><span class="sxs-lookup"><span data-stu-id="95f3b-151">You can choose for the connection to index either the entire organization or specific projects.</span></span>

<span data-ttu-id="95f3b-152">Si vous choisissez d’indexer l’ensemble de l’organisation, les éléments de tous les projets de l’organisation seront indexés.</span><span class="sxs-lookup"><span data-stu-id="95f3b-152">If you choose to index the entire organization, items in all projects in the organization will get indexed.</span></span> <span data-ttu-id="95f3b-153">Les nouveaux projets et éléments seront indexés lors de l’analyse suivante après leur création.</span><span class="sxs-lookup"><span data-stu-id="95f3b-153">New projects and items will be indexed during the next crawl after they're created.</span></span>

<span data-ttu-id="95f3b-154">Si vous choisissez des projets individuels, seuls les éléments de travail de ces projets seront indexés.</span><span class="sxs-lookup"><span data-stu-id="95f3b-154">If you choose individual projects, only work items in those projects will be indexed.</span></span>

![Configurer des données](media/ADO_Configure_data.png)

<span data-ttu-id="95f3b-156">Ensuite, sélectionnez les champs que vous souhaitez que la connexion indexe et affiche un aperçu des données dans ces champs avant de poursuivre.</span><span class="sxs-lookup"><span data-stu-id="95f3b-156">Next, select which fields you want the connection to index and preview data in these fields before proceeding.</span></span>

![Choisir les propriétés](media/ADO_choose_properties.png)

## <a name="step-4-manage-search-permissions"></a><span data-ttu-id="95f3b-158">Étape 4 : Gérer les autorisations de recherche</span><span class="sxs-lookup"><span data-stu-id="95f3b-158">Step 4: Manage search permissions</span></span>

<span data-ttu-id="95f3b-159">Le connecteur Azure DevOps prend en charge les autorisations de recherche visibles uniquement pour les personnes ayant accès à  **cette source de données** ou Tout le **monde.**</span><span class="sxs-lookup"><span data-stu-id="95f3b-159">The Azure DevOps connector supports search permissions visible to  **Only people with access to this data source** or **Everyone**.</span></span> <span data-ttu-id="95f3b-160">Si vous choisissez uniquement les personnes ayant accès à cette **source** de données, les données indexées apparaissent dans les résultats de la recherche pour les utilisateurs qui y ont accès en fonction des autorisations accordées aux utilisateurs ou aux groupes au niveau de l’organisation, du Project ou du chemin d’accès de la zone dans Azure DevOps.</span><span class="sxs-lookup"><span data-stu-id="95f3b-160">If you choose **Only people with access to this data source**, indexed data will appear in the search results for users who have access to them based on permissions to users or groups at the Organization, Project or Area path level in Azure DevOps.</span></span> <span data-ttu-id="95f3b-161">Si vous choisissez **Tout le** monde, les données indexées apparaissent dans les résultats de recherche pour tous les utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="95f3b-161">If you choose **Everyone**, indexed data will appear in the search results for all users.</span></span>

## <a name="step-5-assign-property-labels"></a><span data-ttu-id="95f3b-162">Étape 5 : Attribuer des étiquettes de propriété</span><span class="sxs-lookup"><span data-stu-id="95f3b-162">Step 5: Assign property labels</span></span>

<span data-ttu-id="95f3b-163">Suivez les [instructions d’installation générales.](./configure-connector.md)</span><span class="sxs-lookup"><span data-stu-id="95f3b-163">Follow the general [setup instructions](./configure-connector.md).</span></span>

## <a name="step-6-manage-schema"></a><span data-ttu-id="95f3b-164">Étape 6 : Gérer le schéma</span><span class="sxs-lookup"><span data-stu-id="95f3b-164">Step 6: Manage schema</span></span>

<span data-ttu-id="95f3b-165">Suivez les [instructions d’installation générales.](./configure-connector.md)</span><span class="sxs-lookup"><span data-stu-id="95f3b-165">Follow the general [setup instructions](./configure-connector.md).</span></span>

## <a name="step-7-choose-refresh-settings"></a><span data-ttu-id="95f3b-166">Étape 7 : Choisir les paramètres d’actualisation</span><span class="sxs-lookup"><span data-stu-id="95f3b-166">Step 7: Choose refresh settings</span></span>

<span data-ttu-id="95f3b-167">Le connecteur Azure DevOps prend en charge les planifications d’actualisation pour les analyses complètes et incrémentielles.</span><span class="sxs-lookup"><span data-stu-id="95f3b-167">The Azure DevOps connector supports refresh schedules for both full and incremental crawls.</span></span>
<span data-ttu-id="95f3b-168">La planification recommandée est une heure pour une analyse incrémentielle et un jour pour une analyse complète.</span><span class="sxs-lookup"><span data-stu-id="95f3b-168">The recommended schedule is one hour for an incremental crawl and one day for a full crawl.</span></span>

## <a name="step-8-review-connection"></a><span data-ttu-id="95f3b-169">Étape 8 : Examiner la connexion</span><span class="sxs-lookup"><span data-stu-id="95f3b-169">Step 8: Review connection</span></span>

<span data-ttu-id="95f3b-170">Suivez les [instructions d’installation générales.](./configure-connector.md)</span><span class="sxs-lookup"><span data-stu-id="95f3b-170">Follow the general [setup instructions](./configure-connector.md).</span></span>

>[!TIP]
><span data-ttu-id="95f3b-171">**Type de résultat par défaut**</span><span class="sxs-lookup"><span data-stu-id="95f3b-171">**Default Result type**</span></span>
>* <span data-ttu-id="95f3b-172">Le connecteur Azure DevOps enregistre automatiquement un [type](./customize-search-page.md#step-2-create-the-result-types) de résultat une fois le connecteur publié.</span><span class="sxs-lookup"><span data-stu-id="95f3b-172">The Azure DevOps connector automatically registers a [result type](./customize-search-page.md#step-2-create-the-result-types) once the connector is published.</span></span> <span data-ttu-id="95f3b-173">Le type de résultat utilise [](./customize-results-layout.md) une disposition des résultats générée dynamiquement en fonction des champs sélectionnés à l’étape 3.</span><span class="sxs-lookup"><span data-stu-id="95f3b-173">The result type uses a dynamically generated [result layout](./customize-results-layout.md) based on the fields selected in step 3.</span></span> 
>* <span data-ttu-id="95f3b-174">Vous pouvez gérer le type de résultat en naviguant vers [**les types**](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/resulttypes) de résultats dans le [centre Microsoft 365'administration.](https://admin.microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="95f3b-174">You can manage the result type by navigating to [**Result types**](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/resulttypes) in the [Microsoft 365 admin center](https://admin.microsoft.com).</span></span> <span data-ttu-id="95f3b-175">Le type de résultat par défaut sera nommé « `ConnectionId` Default ».</span><span class="sxs-lookup"><span data-stu-id="95f3b-175">The default result type will be named as "`ConnectionId`Default".</span></span> <span data-ttu-id="95f3b-176">Par exemple, si votre ID de connexion est , votre disposition des résultats sera nommée `AzureDevOps` : « AzureDevOpsDefault »</span><span class="sxs-lookup"><span data-stu-id="95f3b-176">For example, if your connection id is `AzureDevOps`, your result layout will be named: "AzureDevOpsDefault"</span></span>
>* <span data-ttu-id="95f3b-177">En outre, vous pouvez choisir de créer votre propre type de résultat si nécessaire.</span><span class="sxs-lookup"><span data-stu-id="95f3b-177">Also, you can choose to create your own result type if needed.</span></span>

<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup 
instructions.-->

<!---## Troubleshooting-->
<!---Insert troubleshooting recommendations for this data source-->

<!---## Limitations-->
<!---Insert limitations for this data source-->