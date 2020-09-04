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
# <a name="azure-devops-connector"></a><span data-ttu-id="21543-103">Connecteur DevOps Azure</span><span class="sxs-lookup"><span data-stu-id="21543-103">Azure DevOps connector</span></span>

<span data-ttu-id="21543-104">Avec le connecteur Azure DevOps, votre organisation peut indexer les éléments de travail dans son instance du service Azure DevOps.</span><span class="sxs-lookup"><span data-stu-id="21543-104">With the Azure DevOps connector, your organization can index work items in its instance of the Azure DevOps service.</span></span> <span data-ttu-id="21543-105">Une fois que vous avez configuré le connecteur et le contenu d’index à partir d’Azure DevOps, les utilisateurs finals peuvent rechercher ces éléments dans Microsoft Search.</span><span class="sxs-lookup"><span data-stu-id="21543-105">After you configure the connector and index content from Azure DevOps, end users can search for those items in Microsoft Search.</span></span>

<span data-ttu-id="21543-106">Cet article est destiné aux administrateurs 365 de Microsoft ou toute personne qui configure, exécute et surveille un connecteur DevOps Azure.</span><span class="sxs-lookup"><span data-stu-id="21543-106">This article is for Microsoft 365 administrators or anyone who configures, runs, and monitors an Azure DevOps connector.</span></span> <span data-ttu-id="21543-107">Elle explique comment configurer les fonctionnalités de connecteur et de connecteur, ainsi que les restrictions et les techniques de résolution des problèmes.</span><span class="sxs-lookup"><span data-stu-id="21543-107">It explains how to configure your connector and connector capabilities, limitations, and troubleshooting techniques.</span></span>

>[!IMPORTANT]
><span data-ttu-id="21543-108">Le connecteur Azure DevOps prend en charge uniquement le service de Cloud Azure DevOps.</span><span class="sxs-lookup"><span data-stu-id="21543-108">The Azure DevOps connector supports only the Azure DevOps cloud service.</span></span> <span data-ttu-id="21543-109">Azure DevOps Server 2019, TFS 2018, TFS 2017, TFS 2015 et TFS 2013 ne sont pas pris en charge par ce connecteur.</span><span class="sxs-lookup"><span data-stu-id="21543-109">Azure DevOps Server 2019, TFS 2018, TFS 2017, TFS 2015, and TFS 2013 are not supported by this connector.</span></span>

## <a name="connect-to-a-data-source"></a><span data-ttu-id="21543-110">Se connecter à une source de données</span><span class="sxs-lookup"><span data-stu-id="21543-110">Connect to a data source</span></span>

<span data-ttu-id="21543-111">Pour vous connecter à votre instance Azure DevOps, vous avez besoin de votre nom d' [organisation](https://docs.microsoft.com/azure/devops/organizations/accounts/create-organization) Azure DevOps, de son ID d’application et de la clé secrète client pour l’authentification OAuth.</span><span class="sxs-lookup"><span data-stu-id="21543-111">To connect to your Azure DevOps instance, you need your Azure DevOps [organization](https://docs.microsoft.com/azure/devops/organizations/accounts/create-organization) name, its App ID, and client secret for OAuth authentication.</span></span>

### <a name="register-an-app"></a><span data-ttu-id="21543-112">Inscrire une application</span><span class="sxs-lookup"><span data-stu-id="21543-112">Register an app</span></span>

<span data-ttu-id="21543-113">Vous devez inscrire une application dans Azure DevOps afin que l’application Microsoft Search puisse accéder à l’instance.</span><span class="sxs-lookup"><span data-stu-id="21543-113">You must register an app in Azure DevOps so that the Microsoft Search app can access the instance.</span></span> <span data-ttu-id="21543-114">Pour plus d’informations, reportez-vous à la documentation Azure DevOps sur l' [enregistrement d’une application](https://docs.microsoft.com/azure/devops/integrate/get-started/authentication/oauth?view=azure-devops#register-your-app).</span><span class="sxs-lookup"><span data-stu-id="21543-114">To learn more, see Azure DevOps documentation on how to [register an app](https://docs.microsoft.com/azure/devops/integrate/get-started/authentication/oauth?view=azure-devops#register-your-app).</span></span>

<span data-ttu-id="21543-115">Le tableau suivant fournit des instructions sur la façon de remplir le formulaire d’inscription de l’application :</span><span class="sxs-lookup"><span data-stu-id="21543-115">The following table provides guidance on how to fill out the app registration form:</span></span>

 <span data-ttu-id="21543-116">**Champs obligatoires**</span><span class="sxs-lookup"><span data-stu-id="21543-116">**Mandatory Fields**</span></span> | <span data-ttu-id="21543-117">**Description**</span><span class="sxs-lookup"><span data-stu-id="21543-117">**Description**</span></span>      | <span data-ttu-id="21543-118">**Valeur recommandée**</span><span class="sxs-lookup"><span data-stu-id="21543-118">**Recommended Value**</span></span>
--- | --- | ---
| <span data-ttu-id="21543-119">Nom de la société</span><span class="sxs-lookup"><span data-stu-id="21543-119">Company Name</span></span>         | <span data-ttu-id="21543-120">Il s’agit du nom de votre société.</span><span class="sxs-lookup"><span data-stu-id="21543-120">This is the name of your company.</span></span> | <span data-ttu-id="21543-121">Utiliser une valeur appropriée</span><span class="sxs-lookup"><span data-stu-id="21543-121">Use an appropriate value</span></span>   |
| <span data-ttu-id="21543-122">Nom de l’application</span><span class="sxs-lookup"><span data-stu-id="21543-122">Application name</span></span>     | <span data-ttu-id="21543-123">Cette valeur unique identifie l’application que vous autorisez.</span><span class="sxs-lookup"><span data-stu-id="21543-123">This unique value identifies the application that you're authorizing.</span></span>    | <span data-ttu-id="21543-124">Recherche Microsoft</span><span class="sxs-lookup"><span data-stu-id="21543-124">Microsoft Search</span></span>     |
| <span data-ttu-id="21543-125">Site Web d’application</span><span class="sxs-lookup"><span data-stu-id="21543-125">Application website</span></span>  | <span data-ttu-id="21543-126">Ce champ obligatoire est l’URL de l’application qui demandera l’accès à votre instance Azure DevOps lors de la configuration du connecteur.</span><span class="sxs-lookup"><span data-stu-id="21543-126">This required field is the URL of the application that will request access to your Azure DevOps instance during connector setup.</span></span>  | <https://gcs.office.com/>                |
| <span data-ttu-id="21543-127">URL de rappel d’autorisation</span><span class="sxs-lookup"><span data-stu-id="21543-127">Authorization callback URL</span></span>        | <span data-ttu-id="21543-128">URL de rappel obligatoire vers laquelle le serveur d’autorisation redirige.</span><span class="sxs-lookup"><span data-stu-id="21543-128">A required callback URL that the authorization server redirects to.</span></span> | <https://gcs.office.com/v1.0/admin/oauth/callback>|
| <span data-ttu-id="21543-129">Étendues autorisées</span><span class="sxs-lookup"><span data-stu-id="21543-129">Authorized scopes</span></span> | <span data-ttu-id="21543-130">Il s’agit de la portée de l’accès à l’application</span><span class="sxs-lookup"><span data-stu-id="21543-130">This is the scope of access for the application</span></span> | <span data-ttu-id="21543-131">Sélectionnez les étendues suivantes : identité (lecture), éléments de travail (lecture), groupes de variables (lecture), projet et équipe (lecture), graphique (lecture)</span><span class="sxs-lookup"><span data-stu-id="21543-131">Select the following scopes: Identity (read), Work Items (read), Variable Groups (read), Project and team (read), Graph (read)</span></span>|

<span data-ttu-id="21543-132">Lors de l’inscription de l’application avec les détails ci-dessus, vous obtiendrez l’ID de l' **application** et la **clé secrète client** qui seront utilisés pour configurer le connecteur.</span><span class="sxs-lookup"><span data-stu-id="21543-132">On registering the app with the details above, you will get the **App ID** and **Client Secret** that will be used to configure the connector.</span></span>

>[!NOTE]
><span data-ttu-id="21543-133">Pour révoquer l’accès à une application inscrite dans Azure DevOps, accédez à paramètres utilisateur en haut à droite de votre instance de DevOps Azure.</span><span class="sxs-lookup"><span data-stu-id="21543-133">To revoke access to any app registered in Azure DevOps, go to User settings at the right top of your Azure DevOps instance.</span></span> <span data-ttu-id="21543-134">Cliquez sur profil, puis sur autorisations dans la section sécurité du volet latéral.</span><span class="sxs-lookup"><span data-stu-id="21543-134">Click on Profile and then click on Authorizations in the Security section of the side pane.</span></span> <span data-ttu-id="21543-135">Placez le pointeur de la souris sur une application OAuth autorisée pour afficher le bouton révoquer dans le coin des détails de l’application.</span><span class="sxs-lookup"><span data-stu-id="21543-135">Hover over an authorized OAuth app to see the Revoke button at the corner of the app details.</span></span>

### <a name="connection-settings"></a><span data-ttu-id="21543-136">Paramètres de connexion</span><span class="sxs-lookup"><span data-stu-id="21543-136">Connection settings</span></span>

<span data-ttu-id="21543-137">Après avoir inscrit l’application Microsoft Search auprès d’Azure DevOps, vous pouvez effectuer l’étape des paramètres de connexion.</span><span class="sxs-lookup"><span data-stu-id="21543-137">After registering the Microsoft Search app with Azure DevOps, you can complete the connection settings step.</span></span> <span data-ttu-id="21543-138">Entrez le nom de votre organisation, l’ID de l’application et la clé secrète client.</span><span class="sxs-lookup"><span data-stu-id="21543-138">Enter your organization name, App ID, and Client secret.</span></span>

![Paramètres de l’application de connexion](media/ADO_Connection_settings_2.png)

## <a name="select-projects-and-fields"></a><span data-ttu-id="21543-140">Sélectionner des projets et des champs</span><span class="sxs-lookup"><span data-stu-id="21543-140">Select projects and fields</span></span>

<span data-ttu-id="21543-141">Vous pouvez choisir pour la connexion d’indexer l’ensemble de l’organisation ou des projets spécifiques.</span><span class="sxs-lookup"><span data-stu-id="21543-141">You can choose for the connection to index either the entire organization or specific projects.</span></span>

<span data-ttu-id="21543-142">Si vous choisissez d’indexer toute l’organisation, les éléments de tous les projets de l’Organisation seront indexés.</span><span class="sxs-lookup"><span data-stu-id="21543-142">If you choose to index the entire organization, items in all projects in the organization will get indexed.</span></span> <span data-ttu-id="21543-143">Les nouveaux projets et éléments seront indexés lors de la prochaine analyse après leur création.</span><span class="sxs-lookup"><span data-stu-id="21543-143">New projects and items will be indexed during the next crawl after they are created.</span></span> <span data-ttu-id="21543-144">Si vous choisissez des projets individuels, seuls les éléments de travail de ces projets seront indexés.</span><span class="sxs-lookup"><span data-stu-id="21543-144">If you choose individual projects, only work items in those projects will be indexed.</span></span>

![Configurer les données](media/ADO_Configure_data.png)

<span data-ttu-id="21543-146">Ensuite, sélectionnez les champs pour lesquels vous souhaitez que la connexion indexe et prévisualiser les données dans ces champs avant de poursuivre.</span><span class="sxs-lookup"><span data-stu-id="21543-146">Next, select which fields you want the connection to index and preview data in these fields before proceeding.</span></span>

![Choisir les propriétés](media/ADO_choose_properties.png)

## <a name="manage-the-search-schema"></a><span data-ttu-id="21543-148">Gérer le schéma de recherche</span><span class="sxs-lookup"><span data-stu-id="21543-148">Manage the search schema</span></span>

<span data-ttu-id="21543-149">Configurez le mappage du schéma de recherche.</span><span class="sxs-lookup"><span data-stu-id="21543-149">Configure the search schema mapping.</span></span> <span data-ttu-id="21543-150">Vous pouvez choisir les propriétés à utiliser pour les **requêtes**, les **recherches** et les **extractions**.</span><span class="sxs-lookup"><span data-stu-id="21543-150">You can choose which properties to make **queryable**, **searchable** and **retrievable**.</span></span>

## <a name="manage-search-permissions"></a><span data-ttu-id="21543-151">Gérer les autorisations de recherche</span><span class="sxs-lookup"><span data-stu-id="21543-151">Manage search permissions</span></span>

<span data-ttu-id="21543-152">Actuellement, le connecteur Azure DevOps prend uniquement en charge les autorisations **de recherche visibles par tous les utilisateurs**.</span><span class="sxs-lookup"><span data-stu-id="21543-152">The Azure DevOps connector currently only supports search permissions **Visible to Everyone**.</span></span> <span data-ttu-id="21543-153">Les données indexées apparaîtront dans les résultats de recherche pour tous les utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="21543-153">Indexed data will appear in the search results for all users.</span></span>

## <a name="set-the-refresh-schedule"></a><span data-ttu-id="21543-154">Définir la planification d’actualisation</span><span class="sxs-lookup"><span data-stu-id="21543-154">Set the refresh schedule</span></span>

<span data-ttu-id="21543-155">Le connecteur Azure DevOps prend en charge les planifications d’actualisation pour les analyses complètes et incrémentielles.</span><span class="sxs-lookup"><span data-stu-id="21543-155">The Azure DevOps connector supports refresh schedules for both full and incremental crawls.</span></span> <span data-ttu-id="21543-156">Une analyse complète recherche les éléments de travail supprimés qui ont été précédemment synchronisés avec l’index de recherche Microsoft.</span><span class="sxs-lookup"><span data-stu-id="21543-156">A full crawl finds deleted work items that were previously synced to the Microsoft Search index.</span></span> <span data-ttu-id="21543-157">Une analyse complète est exécutée pour synchroniser tous les éléments de travail.</span><span class="sxs-lookup"><span data-stu-id="21543-157">A full crawl runs to sync all the work items.</span></span> <span data-ttu-id="21543-158">Pour synchroniser les nouveaux éléments de travail et les mises à jour d’éléments de travail existants, vous devez planifier des analyses incrémentielles.</span><span class="sxs-lookup"><span data-stu-id="21543-158">To sync new work items and updates to existing work items, you need to schedule incremental crawls.</span></span>

<span data-ttu-id="21543-159">La planification recommandée est d’une heure pour une analyse incrémentielle et d’un jour pour une analyse complète.</span><span class="sxs-lookup"><span data-stu-id="21543-159">The recommended schedule is one hour for an incremental crawl and one day for a full crawl.</span></span>
