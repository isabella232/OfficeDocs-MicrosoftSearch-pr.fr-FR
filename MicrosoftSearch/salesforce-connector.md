---
title: Connecteur Salesforce Graph pour Microsoft Search (recherche Microsoft)
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
description: Configurer le connecteur Salesforce Graph pour Microsoft Search (recherche Microsoft)
ms.openlocfilehash: 86140a4650593e08188f171be54f1753b73ecf7a
ms.sourcegitcommit: f76ade4c8fed0fee9c36d067b3ca8288c6c980aa
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/05/2021
ms.locfileid: "50508822"
---
<!---Previous ms.author: rusamai --->

# <a name="salesforce-graph-connector-preview"></a><span data-ttu-id="71da0-103">Connecteur Salesforce Graph (prévisualisation)</span><span class="sxs-lookup"><span data-stu-id="71da0-103">Salesforce Graph connector (preview)</span></span>

<span data-ttu-id="71da0-104">Le connecteur Salesforce Graph permet à votre organisation d’indexer les objets Contacts, Opportunités, Prospects et Comptes dans votre instance Salesforce.</span><span class="sxs-lookup"><span data-stu-id="71da0-104">The Salesforce Graph connector, allows your organization to index Contacts, Opportunities, Leads, and Accounts objects in your Salesforce instance.</span></span> <span data-ttu-id="71da0-105">Après avoir configuré le connecteur et indexé le contenu à partir de Salesforce, les utilisateurs finaux peuvent rechercher ces éléments à partir de n’importe quel client Recherche Microsoft.</span><span class="sxs-lookup"><span data-stu-id="71da0-105">After you configure the connector and index content from Salesforce, end users can search for those items from any Microsoft Search client.</span></span>

> [!NOTE]
> <span data-ttu-id="71da0-106">Lisez [**l’article Configuration de votre connecteur Graph**](configure-connector.md) pour comprendre les instructions générales d’installation des connecteurs Graph.</span><span class="sxs-lookup"><span data-stu-id="71da0-106">Read the [**Setup for your Graph connector**](configure-connector.md) article to understand the general Graph connectors setup instructions.</span></span>

<span data-ttu-id="71da0-107">Cet article est réservé à toute personne qui configure, exécute et surveille un connecteur Salesforce Graph.</span><span class="sxs-lookup"><span data-stu-id="71da0-107">This article is for anyone who configures, runs, and monitors a Salesforce Graph connector.</span></span> <span data-ttu-id="71da0-108">Il complète le processus d’installation général et affiche des instructions qui s’appliquent uniquement au connecteur Salesforce Graph.</span><span class="sxs-lookup"><span data-stu-id="71da0-108">It supplements the general setup process, and shows instructions that apply only for the Salesforce Graph connector.</span></span> <span data-ttu-id="71da0-109">Cet article inclut également des informations sur [les limitations.](#limitations)</span><span class="sxs-lookup"><span data-stu-id="71da0-109">This article also includes information about [Limitations](#limitations).</span></span>

>[!IMPORTANT]
><span data-ttu-id="71da0-110">Le connecteur Salesforce Graph prend actuellement en charge Summer '19 ou une ultérieure.</span><span class="sxs-lookup"><span data-stu-id="71da0-110">The Salesforce Graph connector currently supports Summer '19 or later.</span></span>

## <a name="before-you-get-started"></a><span data-ttu-id="71da0-111">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="71da0-111">Before you get started</span></span>

<span data-ttu-id="71da0-112">Pour vous connecter à votre instance Salesforce, vous avez besoin de votre URL d’instance Salesforce, de l’ID client et de la secret client pour l’authentification OAuth.</span><span class="sxs-lookup"><span data-stu-id="71da0-112">To connect to your Salesforce instance, you need your Salesforce instance URL, the Client ID, and Client Secret for OAuth authentication.</span></span> <span data-ttu-id="71da0-113">Les étapes suivantes expliquent comment vous ou votre administrateur Salesforce pouvez obtenir ces informations à partir de votre compte Salesforce :</span><span class="sxs-lookup"><span data-stu-id="71da0-113">The following steps explain how you or your Salesforce administrator can get this information from your Salesforce account:</span></span>

- <span data-ttu-id="71da0-114">Connectez-vous à votre instance Salesforce et allez au programme d’installation</span><span class="sxs-lookup"><span data-stu-id="71da0-114">Log in to your Salesforce instance and go to Setup</span></span>

- <span data-ttu-id="71da0-115">Accédez à Apps -> App Manager.</span><span class="sxs-lookup"><span data-stu-id="71da0-115">Navigate to Apps -> App Manager.</span></span>

- <span data-ttu-id="71da0-116">Sélectionnez **Nouvelle application connectée.**</span><span class="sxs-lookup"><span data-stu-id="71da0-116">Select **New connected app**.</span></span>

- <span data-ttu-id="71da0-117">Remplissez la section API comme suit :</span><span class="sxs-lookup"><span data-stu-id="71da0-117">Complete the API section as follows:</span></span>

    - <span data-ttu-id="71da0-118">Activez la case à **cocher Activer les paramètres Oauth.**</span><span class="sxs-lookup"><span data-stu-id="71da0-118">Select the checkbox for **Enable Oauth Settings**.</span></span>

    - <span data-ttu-id="71da0-119">Spécifiez l’URL de rappel comme : [https://gcs.office.com/v1.0/admin/oauth/callback](https://gcs.office.com/v1.0/admin/oauth/callback)</span><span class="sxs-lookup"><span data-stu-id="71da0-119">Specify the Callback URL as: [https://gcs.office.com/v1.0/admin/oauth/callback](https://gcs.office.com/v1.0/admin/oauth/callback)</span></span>

    - <span data-ttu-id="71da0-120">Sélectionnez les étendues OAuth requises.</span><span class="sxs-lookup"><span data-stu-id="71da0-120">Select these required OAuth scopes.</span></span>

        - <span data-ttu-id="71da0-121">Accéder à vos données (api) et les gérer</span><span class="sxs-lookup"><span data-stu-id="71da0-121">Access and manage your data (api)</span></span>

        - <span data-ttu-id="71da0-122">Effectuer des demandes en votre nom à tout moment (refresh_token, offline_access)</span><span class="sxs-lookup"><span data-stu-id="71da0-122">Perform requests on your behalf at any time (refresh_token, offline_access)</span></span>

    - <span data-ttu-id="71da0-123">Cochez la case exiger **une secret pour le flux de serveur web.**</span><span class="sxs-lookup"><span data-stu-id="71da0-123">Select the checkbox for **Require secret for web server flow**.</span></span>

    - <span data-ttu-id="71da0-124">Enregistrez l’application.</span><span class="sxs-lookup"><span data-stu-id="71da0-124">Save the app.</span></span>
    
      > [!div class="mx-imgBorder"]
      > <span data-ttu-id="71da0-125">![Section API dans l’instance Salesforce une fois que l’administrateur a entré toutes les configurations requises répertoriées ci-dessus.](media/salesforce-connector/sf1.png)</span><span class="sxs-lookup"><span data-stu-id="71da0-125">![API section in Salesforce instance after admin has entered all required configurations listed above.](media/salesforce-connector/sf1.png)</span></span>

- <span data-ttu-id="71da0-126">Copiez la clé grand public et la clé secrète consommateur.</span><span class="sxs-lookup"><span data-stu-id="71da0-126">Copy the consumer key and the consumer secret.</span></span> <span data-ttu-id="71da0-127">Ces informations sont utilisées comme ID client et secret client lorsque vous configurez les paramètres de connexion de votre connecteur Graph dans le portail d’administration Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="71da0-127">This information will be used as the Client ID and the Client Secret when you configure the Connection Settings for your Graph Connector in the Microsoft 365 admin portal.</span></span>

  > [!div class="mx-imgBorder"]
  > <span data-ttu-id="71da0-128">![Résultats renvoyés par la section API dans l’instance Salesforce après que l’administrateur a soumis toutes les configurations requises.</span><span class="sxs-lookup"><span data-stu-id="71da0-128">![Results returned by API section in Salesforce instance after admin has submitted all required configurations.</span></span> <span data-ttu-id="71da0-129">La clé consommateur se trouve en haut de la colonne gauche et la clé secrète consommateur en haut de la colonne de droite.](media/salesforce-connector/clientsecret.png)</span><span class="sxs-lookup"><span data-stu-id="71da0-129">Consumer Key is at top of left column and Consumer Secret is at top of right column.](media/salesforce-connector/clientsecret.png)</span></span>
  
- <span data-ttu-id="71da0-130">Avant de fermer votre instance Salesforce, suivez ces étapes pour vous assurer que les jetons d’actualisation n’expirent pas :</span><span class="sxs-lookup"><span data-stu-id="71da0-130">Before closing your Salesforce instance, follow these steps to ensure that refresh tokens don't expire:</span></span>
    - <span data-ttu-id="71da0-131">Go to Apps -> App Manager</span><span class="sxs-lookup"><span data-stu-id="71da0-131">Go to Apps -> App Manager</span></span>
    - <span data-ttu-id="71da0-132">Recherchez l’application que vous avez créée et sélectionnez la drop-down sur la droite.</span><span class="sxs-lookup"><span data-stu-id="71da0-132">Find the app you created and select the drop-down on the right.</span></span> <span data-ttu-id="71da0-133">Sélectionnez **Gérer**</span><span class="sxs-lookup"><span data-stu-id="71da0-133">Select **Manage**</span></span>
    - <span data-ttu-id="71da0-134">Sélectionner des **stratégies de modification**</span><span class="sxs-lookup"><span data-stu-id="71da0-134">Select **edit policies**</span></span>
    - <span data-ttu-id="71da0-135">Pour la stratégie de jeton d’actualisation, **sélectionnez Le jeton d’actualisation est valide jusqu’à ce qu’il soit révoqué**</span><span class="sxs-lookup"><span data-stu-id="71da0-135">For refresh token policy, select **Refresh token is valid until revoked**</span></span>

  > [!div class="mx-imgBorder"]
  > <span data-ttu-id="71da0-136">![Sélectionnez la stratégie de jeton d’actualisation nommée « Jeton d’actualisation est valide jusqu’à ce qu’elle soit révoquée »](media/salesforce-connector/oauthpolicies.png)</span><span class="sxs-lookup"><span data-stu-id="71da0-136">![Select the Refresh Token Policy named "Refresh token is valid until revoked "](media/salesforce-connector/oauthpolicies.png)</span></span>

<span data-ttu-id="71da0-137">Vous pouvez désormais utiliser le [Centre d’administration M365](https://admin.microsoft.com/) pour terminer le reste du processus de configuration de votre connecteur Graph.</span><span class="sxs-lookup"><span data-stu-id="71da0-137">You can now use the [M365 Admin Center](https://admin.microsoft.com/) to complete the rest of the setup process for your Graph connector.</span></span>

## <a name="step-1-add-a-graph-connector-in-the-microsoft-365-admin-center"></a><span data-ttu-id="71da0-138">Étape 1 : Ajouter un connecteur Graph dans le Centre d’administration Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="71da0-138">Step 1: Add a Graph connector in the Microsoft 365 admin center</span></span>

<span data-ttu-id="71da0-139">Suivez les [instructions d’installation générales.](https://docs.microsoft.com/microsoftsearch/configure-connector)</span><span class="sxs-lookup"><span data-stu-id="71da0-139">Follow the general [setup instructions](https://docs.microsoft.com/microsoftsearch/configure-connector).</span></span>
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-2-name-the-connection"></a><span data-ttu-id="71da0-140">Étape 2 : Nommer la connexion</span><span class="sxs-lookup"><span data-stu-id="71da0-140">Step 2: Name the connection</span></span>

<span data-ttu-id="71da0-141">Suivez les [instructions d’installation générales.](https://docs.microsoft.com/microsoftsearch/configure-connector)</span><span class="sxs-lookup"><span data-stu-id="71da0-141">Follow the general [setup instructions](https://docs.microsoft.com/microsoftsearch/configure-connector).</span></span>
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-3-configure-the-connection-settings"></a><span data-ttu-id="71da0-142">Étape 3 : Configurer les paramètres de connexion</span><span class="sxs-lookup"><span data-stu-id="71da0-142">Step 3: Configure the connection settings</span></span>

<span data-ttu-id="71da0-143">Pour l’URL de l’instance, utilisez https://[domaine].my.salesforce.com où le domaine serait le domaine Salesforce de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="71da0-143">For the Instance URL, use https://[domain].my.salesforce.com where domain would be the Salesforce domain for your organization.</span></span>

<span data-ttu-id="71da0-144">Entrez l’ID client et la secret client que vous avez obtenus à partir de votre instance Salesforce, puis sélectionnez Se connectez.</span><span class="sxs-lookup"><span data-stu-id="71da0-144">Enter the Client ID and Client Secret you obtained from your Salesforce instance and select Sign in.</span></span>

<span data-ttu-id="71da0-145">La première fois que vous tentez de vous connecter à l’aide de ces paramètres, une fenêtre vous demande de vous connecter à Salesforce avec votre nom d’utilisateur et votre mot de passe d’administrateur.</span><span class="sxs-lookup"><span data-stu-id="71da0-145">The first time you've attempted to sign in with these settings, you'll get a pop-up asking you to log in to Salesforce with your admin username and password.</span></span> <span data-ttu-id="71da0-146">La capture d’écran ci-dessous montre la fenêtre pop-up.</span><span class="sxs-lookup"><span data-stu-id="71da0-146">The screenshot below shows the popup.</span></span> <span data-ttu-id="71da0-147">Entrez vos informations d’identification, puis sélectionnez « Se connecter ».</span><span class="sxs-lookup"><span data-stu-id="71da0-147">Enter your credentials and select "Log In".</span></span>

  ![Fenêtre de connexion pour demander le nom d’utilisateur et le mot de passe.](media/salesforce-connector/sf4.png)

  >[!NOTE]
  ><span data-ttu-id="71da0-149">Si la fenêtre pop-up n’apparaît pas, elle risque d’être bloquée dans votre navigateur. Vous devez donc autoriser les fenêtres pop-up et les redirections.</span><span class="sxs-lookup"><span data-stu-id="71da0-149">If the pop up does not appear, it might be getting blocked in your browser, so you must allow pop-ups and redirects.</span></span>

<span data-ttu-id="71da0-150">Vérifiez que la connexion a réussi en recherchant une bannière verte qui indique « Connexion réussie », comme indiqué dans la capture d’écran ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="71da0-150">Check that the connection was successful by searching for a green banner that says "Connection successful" as show in the screenshot below.</span></span>

  > [!div class="mx-imgBorder"]
  > <span data-ttu-id="71da0-151">![Capture d’écran de la connexion réussie.</span><span class="sxs-lookup"><span data-stu-id="71da0-151">![Screenshot of successful login.</span></span> <span data-ttu-id="71da0-152">La bannière verte qui indique « Connexion réussie » se trouve sous le champ de votre URL d’instance Salesforce](media/salesforce-connector/sf5.png)</span><span class="sxs-lookup"><span data-stu-id="71da0-152">The green banner that says "Connection successful" is located under the field for your Salesforce Instance URL](media/salesforce-connector/sf5.png)</span></span>

## <a name="step-4-manage-search-permissions"></a><span data-ttu-id="71da0-153">Étape 4 : Gérer les autorisations de recherche</span><span class="sxs-lookup"><span data-stu-id="71da0-153">Step 4: Manage search permissions</span></span>

<span data-ttu-id="71da0-154">Vous devez choisir les utilisateurs qui voient les résultats de la recherche à partir de cette source de données.</span><span class="sxs-lookup"><span data-stu-id="71da0-154">You'll need to choose which users will see search results from this data source.</span></span> <span data-ttu-id="71da0-155">Si vous autorisez uniquement certains utilisateurs Azure Active Directory (Azure AD) ou non Azure AD à voir les résultats de la recherche, assurez-vous de ma cartographier les identités.</span><span class="sxs-lookup"><span data-stu-id="71da0-155">If you allow only certain Azure Active Directory (Azure AD) or Non-Azure AD users to see the search results, make sure you map the identities.</span></span>

## <a name="step-4a-select-permissions"></a><span data-ttu-id="71da0-156">Étape 4a : Sélectionner les autorisations</span><span class="sxs-lookup"><span data-stu-id="71da0-156">Step 4a: Select permissions</span></span>

<span data-ttu-id="71da0-157">Vous pouvez choisir d’ingèrer des listes de contrôle d’accès à partir de votre instance Salesforce ou autoriser tous les membres de votre organisation à voir les résultats de recherche provenant de cette source de données.</span><span class="sxs-lookup"><span data-stu-id="71da0-157">You can choose to ingest Access Control Lists (ACLs) from your Salesforce instance, or allow everyone in your organization to see search results from this data source.</span></span> <span data-ttu-id="71da0-158">Les ALA peuvent inclure des identités Azure Active Directory (AAD) (utilisateurs fédérés d’Azure AD à Salesforce), des identités non Azure AD (utilisateurs Salesforce natifs ayant des identités correspondantes dans Azure AD) ou les deux.</span><span class="sxs-lookup"><span data-stu-id="71da0-158">ACLs can include Azure Active Directory (AAD) identities (users who are federated from Azure AD to Salesforce), non-Azure AD identities (native Salesforce users who have corresponding identities in Azure AD), or both.</span></span>

>[!NOTE]
><span data-ttu-id="71da0-159">Si vous utilisez un fournisseur d’identité tiers comme Ping ID ou secureAuth, vous devez sélectionner « non-AAD » comme type d’identité.</span><span class="sxs-lookup"><span data-stu-id="71da0-159">If you use a third-party Identity Provider like Ping ID or secureAuth, you should select "non-AAD" as the identity type.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="71da0-160">![Écran Sélectionner les autorisations qui ont été effectuées par un administrateur. L’administrateur a sélectionné l’option « Uniquement les personnes ayant accès à cette source de données » et a également sélectionné « AAD » dans un menu déroulant de types d’identité.](media/salesforce-connector/sf6.png)</span><span class="sxs-lookup"><span data-stu-id="71da0-160">![Select permissions screen that has been completed by an admin. The admin has selected the "Only people with access to this data source" option and has also selected "AAD" from a drop down menu of identity types.](media/salesforce-connector/sf6.png)</span></span>

<span data-ttu-id="71da0-161">Si vous avez choisi d’ing d’une ACL à partir de votre instance Salesforce et que vous avez sélectionné « non-AAD » pour le type d’identité, voir Mappage de vos [identités non Azure AD](map-non-aad.md) pour obtenir des instructions sur le mappage des identités.</span><span class="sxs-lookup"><span data-stu-id="71da0-161">If you chose to ingest an ACL from your Salesforce instance and selected "non-AAD" for the identity type, see [Map your non-Azure AD Identities](map-non-aad.md) for instructions on mapping the identities.</span></span>

## <a name="step-4b-map-aad-identities"></a><span data-ttu-id="71da0-162">Étape 4b : Maser les identités AAD</span><span class="sxs-lookup"><span data-stu-id="71da0-162">Step 4b: Map AAD identities</span></span>

<span data-ttu-id="71da0-163">Si vous avez choisi d’ing d’une ACL à partir de votre instance Salesforce et que vous avez sélectionné « AAD » pour le type d’identité, voir Mappage de vos [identités Azure AD](map-aad.md) pour obtenir des instructions sur le mappage des identités.</span><span class="sxs-lookup"><span data-stu-id="71da0-163">If you chose to ingest an ACL from your Salesforce instance and selected "AAD" for the identity type, see [Map your Azure AD Identities](map-aad.md) for instructions on mapping the identities.</span></span> <span data-ttu-id="71da0-164">Pour savoir comment configurer Azure AD SSO pour Salesforce, consultez ce [didacticiel.](https://docs.microsoft.com/azure/active-directory/saas-apps/salesforce-tutorial)</span><span class="sxs-lookup"><span data-stu-id="71da0-164">To learn how to set up Azure AD SSO for Salesforce, see this [tutorial](https://docs.microsoft.com/azure/active-directory/saas-apps/salesforce-tutorial).</span></span>

## <a name="step-5-assign-property-labels"></a><span data-ttu-id="71da0-165">Étape 5 : Attribuer des étiquettes de propriété</span><span class="sxs-lookup"><span data-stu-id="71da0-165">Step 5: Assign property labels</span></span>

<span data-ttu-id="71da0-166">Vous pouvez affecter une propriété source à chaque étiquette en choisissant dans un menu d’options.</span><span class="sxs-lookup"><span data-stu-id="71da0-166">You can assign a source property to each label by choosing from a menu of options.</span></span> <span data-ttu-id="71da0-167">Bien que cette étape ne soit pas obligatoire, le fait d’avoir certaines étiquettes de propriétés améliorera la pertinence de la recherche et garantira de meilleurs résultats de recherche pour les utilisateurs finaux.</span><span class="sxs-lookup"><span data-stu-id="71da0-167">While this step is not mandatory, having some property labels will improve the search relevance and ensure better search results for end users.</span></span> <span data-ttu-id="71da0-168">Par défaut, certaines étiquettes telles que « Titre », « URL », « CreatedBy » et « LastModifiedBy » se sont déjà vu attribuer des propriétés source.</span><span class="sxs-lookup"><span data-stu-id="71da0-168">By default, some of the Labels like "Title," "URL," "CreatedBy," and  "LastModifiedBy" have already been assigned source properties.</span></span>

## <a name="step-6-manage-schema"></a><span data-ttu-id="71da0-169">Étape 6 : Gérer le schéma</span><span class="sxs-lookup"><span data-stu-id="71da0-169">Step 6: Manage schema</span></span>

<span data-ttu-id="71da0-170">Vous pouvez sélectionner les propriétés source qui doivent être indexées afin qu’elles s’afficheront dans les résultats de la recherche.</span><span class="sxs-lookup"><span data-stu-id="71da0-170">You can select what source properties should be indexed so that they show up in search results.</span></span> <span data-ttu-id="71da0-171">L’Assistant Connexion sélectionne par défaut un schéma de recherche basé sur un ensemble de propriétés source.</span><span class="sxs-lookup"><span data-stu-id="71da0-171">The connection wizard by default selects a search schema based on a set of source properties.</span></span> <span data-ttu-id="71da0-172">Vous pouvez le modifier en élecant les cases à cocher de chaque propriété et attribut de la page de schéma de recherche.</span><span class="sxs-lookup"><span data-stu-id="71da0-172">You can modify it by selecting the check boxes for each property and attribute in the search schema page.</span></span> <span data-ttu-id="71da0-173">Les attributs de schéma de recherche incluent recherche, requête, récupération et affiner.</span><span class="sxs-lookup"><span data-stu-id="71da0-173">Search schema attributes include Search, Query, Retrieve, and Refine.</span></span>
<span data-ttu-id="71da0-174">L’affinement vous permet de définir les propriétés qui peuvent être utilisées ultérieurement en tant qu’affinements ou filtres personnalisés dans l’expérience de recherche.</span><span class="sxs-lookup"><span data-stu-id="71da0-174">Refine allows you to define the properties that can be later used as custom refiners or filters in the search experience.</span></span>  

> [!div class="mx-imgBorder"]
> <span data-ttu-id="71da0-175">![Sélectionnez le schéma pour chaque propriété source.</span><span class="sxs-lookup"><span data-stu-id="71da0-175">![Select the schema for each source property.</span></span> <span data-ttu-id="71da0-176">Les options sont Requête, Recherche, Récupérer et Affiner](media/salesforce-connector/sf9.png)</span><span class="sxs-lookup"><span data-stu-id="71da0-176">The options are Query, Search, Retrieve, and Refine](media/salesforce-connector/sf9.png)</span></span>

## <a name="step-7-set-the-refresh-schedule"></a><span data-ttu-id="71da0-177">Étape 7 : Définir la planification de l’actualisation</span><span class="sxs-lookup"><span data-stu-id="71da0-177">Step 7: Set the refresh schedule</span></span>

<span data-ttu-id="71da0-178">Le connecteur Salesforce prend uniquement en charge les planifications d’actualisation pour les analyse complètes actuellement.</span><span class="sxs-lookup"><span data-stu-id="71da0-178">The Salesforce connector only supports refresh schedules for full crawls currently.</span></span>

>[!IMPORTANT]
><span data-ttu-id="71da0-179">Une analyse complète recherche des objets et des utilisateurs supprimés qui ont été précédemment synchronisés avec l’index recherche Microsoft.</span><span class="sxs-lookup"><span data-stu-id="71da0-179">A full crawl finds deleted objects and users that were previously synced to the Microsoft Search index.</span></span>

<span data-ttu-id="71da0-180">La planification recommandée est d’une semaine pour une analyse complète.</span><span class="sxs-lookup"><span data-stu-id="71da0-180">The recommended schedule is one week for a full crawl.</span></span>

## <a name="step-8-review-connection"></a><span data-ttu-id="71da0-181">Étape 8 : Examiner la connexion</span><span class="sxs-lookup"><span data-stu-id="71da0-181">Step 8: Review connection</span></span>

<span data-ttu-id="71da0-182">Suivez les [instructions d’installation générales.](https://docs.microsoft.com/microsoftsearch/configure-connector)</span><span class="sxs-lookup"><span data-stu-id="71da0-182">Follow the general [setup instructions](https://docs.microsoft.com/microsoftsearch/configure-connector).</span></span>
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

<!---## Troubleshooting-->
<!---Insert troubleshooting recommendations for this data source-->

## <a name="limitations"></a><span data-ttu-id="71da0-183">Limites</span><span class="sxs-lookup"><span data-stu-id="71da0-183">Limitations</span></span>

- <span data-ttu-id="71da0-184">Le connecteur Graph ne prend actuellement pas en charge le partage et le partage basés sur un territoire à l’aide de groupes personnels de Salesforce.</span><span class="sxs-lookup"><span data-stu-id="71da0-184">The Graph connector doesn't currently support Apex based, territory-based sharing and sharing using personal groups from Salesforce.</span></span>
- <span data-ttu-id="71da0-185">Il existe un bogue connu dans l’API Salesforce que le connecteur Graph utilise, où les valeurs par défaut privées à l’échelle de l’organisation pour les prospects ne sont pas honorées actuellement.</span><span class="sxs-lookup"><span data-stu-id="71da0-185">There's a known bug in the Salesforce API the Graph connector uses, where the private org-wide defaults for leads aren't honored currently.</span></span>  
- <span data-ttu-id="71da0-186">Si un champ a la sécurité au niveau du champ (FLS) définie pour un profil, le connecteur Graph n’inserre pas ce champ pour les profils dans cette organisation Salesforce. Par conséquent, les utilisateurs ne pourront pas rechercher sur les valeurs de ces champs, ni s’afficher dans les résultats.</span><span class="sxs-lookup"><span data-stu-id="71da0-186">If a field has field level security (FLS) set for a profile, the Graph connector won't ingest that field for any profiles in that Salesforce org. As a result, users won't be able to search on values for those fields, nor will it show up in the results.</span></span>  
- <span data-ttu-id="71da0-187">Dans l’écran Gérer le schéma, ces noms de propriétés standard communs sont répertoriés une seule fois, les options sont **Requête,** **Rechercher,** Récupérer **et** **Affiner,** et s’appliquent à tout ou aucun.</span><span class="sxs-lookup"><span data-stu-id="71da0-187">In the Manage Schema screen these common standard property names are listed once, the options are **Query**, **Search**, **Retrieve**, and **Refine**, and apply to all or none.</span></span>
    - <span data-ttu-id="71da0-188">Nom</span><span class="sxs-lookup"><span data-stu-id="71da0-188">Name</span></span>
    - <span data-ttu-id="71da0-189">Url</span><span class="sxs-lookup"><span data-stu-id="71da0-189">Url</span></span>
    - <span data-ttu-id="71da0-190">Description</span><span class="sxs-lookup"><span data-stu-id="71da0-190">Description</span></span>
    - <span data-ttu-id="71da0-191">Fax</span><span class="sxs-lookup"><span data-stu-id="71da0-191">Fax</span></span>
    - <span data-ttu-id="71da0-192">Téléphone</span><span class="sxs-lookup"><span data-stu-id="71da0-192">Phone</span></span>
    - <span data-ttu-id="71da0-193">MobilePhone</span><span class="sxs-lookup"><span data-stu-id="71da0-193">MobilePhone</span></span>
    - <span data-ttu-id="71da0-194">E-mail</span><span class="sxs-lookup"><span data-stu-id="71da0-194">Email</span></span>
    - <span data-ttu-id="71da0-195">Type</span><span class="sxs-lookup"><span data-stu-id="71da0-195">Type</span></span>
    - <span data-ttu-id="71da0-196">Titre</span><span class="sxs-lookup"><span data-stu-id="71da0-196">Title</span></span>
    - <span data-ttu-id="71da0-197">AccountId</span><span class="sxs-lookup"><span data-stu-id="71da0-197">AccountId</span></span>
    - <span data-ttu-id="71da0-198">AccountName</span><span class="sxs-lookup"><span data-stu-id="71da0-198">AccountName</span></span>
    - <span data-ttu-id="71da0-199">AccountUrl</span><span class="sxs-lookup"><span data-stu-id="71da0-199">AccountUrl</span></span>
    - <span data-ttu-id="71da0-200">AccountOwner</span><span class="sxs-lookup"><span data-stu-id="71da0-200">AccountOwner</span></span>
    - <span data-ttu-id="71da0-201">AccountOwnerUrl</span><span class="sxs-lookup"><span data-stu-id="71da0-201">AccountOwnerUrl</span></span>
    - <span data-ttu-id="71da0-202">Propriétaire</span><span class="sxs-lookup"><span data-stu-id="71da0-202">Owner</span></span>
    - <span data-ttu-id="71da0-203">OwnerUrl</span><span class="sxs-lookup"><span data-stu-id="71da0-203">OwnerUrl</span></span>
    - <span data-ttu-id="71da0-204">CreatedBy</span><span class="sxs-lookup"><span data-stu-id="71da0-204">CreatedBy</span></span>
    - <span data-ttu-id="71da0-205">CreatedByUrl</span><span class="sxs-lookup"><span data-stu-id="71da0-205">CreatedByUrl</span></span>
    - <span data-ttu-id="71da0-206">LastModifiedBy</span><span class="sxs-lookup"><span data-stu-id="71da0-206">LastModifiedBy</span></span>
    - <span data-ttu-id="71da0-207">LastModifiedByUrl</span><span class="sxs-lookup"><span data-stu-id="71da0-207">LastModifiedByUrl</span></span>
    - <span data-ttu-id="71da0-208">LastModifiedDate</span><span class="sxs-lookup"><span data-stu-id="71da0-208">LastModifiedDate</span></span>
    - <span data-ttu-id="71da0-209">ObjectName</span><span class="sxs-lookup"><span data-stu-id="71da0-209">ObjectName</span></span>
