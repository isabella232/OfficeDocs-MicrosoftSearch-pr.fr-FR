---
title: Connecteur d’Graph Salesforce pour Recherche Microsoft
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
description: Configurer le connecteur Graph Salesforce pour Recherche Microsoft
ms.openlocfilehash: 4bef771538934722deaa5deac3959f21246e4529
ms.sourcegitcommit: 93fc70f0073ab45b4dbd702441ac2fc07a7668bc
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/01/2021
ms.locfileid: "53230933"
---
<!---Previous ms.author: rusamai --->

# <a name="salesforce-graph-connector-preview"></a><span data-ttu-id="316bb-103">Connecteur Graph Salesforce (prévisualisation)</span><span class="sxs-lookup"><span data-stu-id="316bb-103">Salesforce Graph connector (preview)</span></span>

<span data-ttu-id="316bb-104">Le connecteur Graph Salesforce permet à votre organisation d’indexer les objets Contacts, Opportunités, Prospects et Comptes dans votre instance Salesforce.</span><span class="sxs-lookup"><span data-stu-id="316bb-104">The Salesforce Graph connector, allows your organization to index Contacts, Opportunities, Leads, and Accounts objects in your Salesforce instance.</span></span> <span data-ttu-id="316bb-105">Après avoir configuré le connecteur et indexé le contenu à partir de Salesforce, les utilisateurs finaux peuvent rechercher ces éléments à partir de n’importe quel client Recherche Microsoft client.</span><span class="sxs-lookup"><span data-stu-id="316bb-105">After you configure the connector and index content from Salesforce, end users can search for those items from any Microsoft Search client.</span></span>

> [!NOTE]
> <span data-ttu-id="316bb-106">Lisez [**l’article**](configure-connector.md) Installation de votre connecteur Graph pour comprendre les instructions générales Graph d’installation des connecteurs.</span><span class="sxs-lookup"><span data-stu-id="316bb-106">Read the [**Setup for your Graph connector**](configure-connector.md) article to understand the general Graph connectors setup instructions.</span></span>

<span data-ttu-id="316bb-107">Cet article est réservé à toute personne qui configure, exécute et surveille un connecteur Graph Salesforce.</span><span class="sxs-lookup"><span data-stu-id="316bb-107">This article is for anyone who configures, runs, and monitors a Salesforce Graph connector.</span></span> <span data-ttu-id="316bb-108">Il complète le processus d’installation général et affiche des instructions qui s’appliquent uniquement au connecteur Graph Salesforce.</span><span class="sxs-lookup"><span data-stu-id="316bb-108">It supplements the general setup process, and shows instructions that apply only for the Salesforce Graph connector.</span></span> <span data-ttu-id="316bb-109">Cet article inclut également des informations sur [les limitations.](#limitations)</span><span class="sxs-lookup"><span data-stu-id="316bb-109">This article also includes information about [Limitations](#limitations).</span></span>

>[!IMPORTANT]
><span data-ttu-id="316bb-110">Le connecteur Graph Salesforce prend actuellement en charge l’été 19 ou une ultérieure.</span><span class="sxs-lookup"><span data-stu-id="316bb-110">The Salesforce Graph connector currently supports Summer '19 or later.</span></span>

## <a name="before-you-get-started"></a><span data-ttu-id="316bb-111">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="316bb-111">Before you get started</span></span>

<span data-ttu-id="316bb-112">Pour vous connecter à votre instance Salesforce, vous avez besoin de votre URL d’instance Salesforce, de l’ID client et de la secret client pour l’authentification OAuth.</span><span class="sxs-lookup"><span data-stu-id="316bb-112">To connect to your Salesforce instance, you need your Salesforce instance URL, the Client ID, and Client Secret for OAuth authentication.</span></span> <span data-ttu-id="316bb-113">Les étapes suivantes expliquent comment vous ou votre administrateur Salesforce pouvez obtenir ces informations à partir de votre compte Salesforce :</span><span class="sxs-lookup"><span data-stu-id="316bb-113">The following steps explain how you or your Salesforce administrator can get this information from your Salesforce account:</span></span>

- <span data-ttu-id="316bb-114">Connectez-vous à votre instance Salesforce et allez au programme d’installation</span><span class="sxs-lookup"><span data-stu-id="316bb-114">Log in to your Salesforce instance and go to Setup</span></span>

- <span data-ttu-id="316bb-115">Accédez à Apps -> App Manager.</span><span class="sxs-lookup"><span data-stu-id="316bb-115">Navigate to Apps -> App Manager.</span></span>

- <span data-ttu-id="316bb-116">Sélectionnez **Nouvelle application connectée.**</span><span class="sxs-lookup"><span data-stu-id="316bb-116">Select **New connected app**.</span></span>

- <span data-ttu-id="316bb-117">Remplissez la section API comme suit :</span><span class="sxs-lookup"><span data-stu-id="316bb-117">Complete the API section as follows:</span></span>

    - <span data-ttu-id="316bb-118">Activez la case à cocher **pour activer Oauth Paramètres**.</span><span class="sxs-lookup"><span data-stu-id="316bb-118">Select the checkbox for **Enable Oauth Settings**.</span></span>

    - <span data-ttu-id="316bb-119">Spécifiez l’URL de rappel comme : [https://gcs.office.com/v1.0/admin/oauth/callback](https://gcs.office.com/v1.0/admin/oauth/callback)</span><span class="sxs-lookup"><span data-stu-id="316bb-119">Specify the Callback URL as: [https://gcs.office.com/v1.0/admin/oauth/callback](https://gcs.office.com/v1.0/admin/oauth/callback)</span></span>

    - <span data-ttu-id="316bb-120">Sélectionnez les étendues OAuth requises.</span><span class="sxs-lookup"><span data-stu-id="316bb-120">Select these required OAuth scopes.</span></span>

        - <span data-ttu-id="316bb-121">Accéder à vos données (api) et les gérer</span><span class="sxs-lookup"><span data-stu-id="316bb-121">Access and manage your data (api)</span></span>

        - <span data-ttu-id="316bb-122">Effectuer des demandes en votre nom à tout moment (refresh_token, offline_access)</span><span class="sxs-lookup"><span data-stu-id="316bb-122">Perform requests on your behalf at any time (refresh_token, offline_access)</span></span>

    - <span data-ttu-id="316bb-123">Cochez la case exiger **une secret pour le flux de serveur web.**</span><span class="sxs-lookup"><span data-stu-id="316bb-123">Select the checkbox for **Require secret for web server flow**.</span></span>

    - <span data-ttu-id="316bb-124">Enregistrez l’application.</span><span class="sxs-lookup"><span data-stu-id="316bb-124">Save the app.</span></span>
    
      > [!div class="mx-imgBorder"]
      > <span data-ttu-id="316bb-125">![Section API dans l’instance Salesforce une fois que l’administrateur a entré toutes les configurations requises répertoriées ci-dessus.](media/salesforce-connector/sf1.png)</span><span class="sxs-lookup"><span data-stu-id="316bb-125">![API section in Salesforce instance after admin has entered all required configurations listed above.](media/salesforce-connector/sf1.png)</span></span>

- <span data-ttu-id="316bb-126">Copiez la clé grand public et la clé secrète consommateur.</span><span class="sxs-lookup"><span data-stu-id="316bb-126">Copy the consumer key and the consumer secret.</span></span> <span data-ttu-id="316bb-127">Ces informations sont utilisées comme ID client et secret client lorsque vous configurez le Paramètres de connexion pour votre connecteur Graph dans le portail d’administration Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="316bb-127">This information will be used as the Client ID and the Client Secret when you configure the Connection Settings for your Graph Connector in the Microsoft 365 admin portal.</span></span>

  > [!div class="mx-imgBorder"]
  > <span data-ttu-id="316bb-128">![Résultats renvoyés par la section API dans l’instance Salesforce après que l’administrateur a soumis toutes les configurations requises.</span><span class="sxs-lookup"><span data-stu-id="316bb-128">![Results returned by API section in Salesforce instance after admin has submitted all required configurations.</span></span> <span data-ttu-id="316bb-129">La clé consommateur se trouve en haut de la colonne gauche et la clé secrète consommateur en haut de la colonne de droite.](media/salesforce-connector/clientsecret.png)</span><span class="sxs-lookup"><span data-stu-id="316bb-129">Consumer Key is at top of left column and Consumer Secret is at top of right column.](media/salesforce-connector/clientsecret.png)</span></span>
  
- <span data-ttu-id="316bb-130">Avant de fermer votre instance Salesforce, suivez ces étapes pour vous assurer que les jetons d’actualisation n’expirent pas :</span><span class="sxs-lookup"><span data-stu-id="316bb-130">Before closing your Salesforce instance, follow these steps to ensure that refresh tokens don't expire:</span></span>
    - <span data-ttu-id="316bb-131">Go to Apps -> App Manager</span><span class="sxs-lookup"><span data-stu-id="316bb-131">Go to Apps -> App Manager</span></span>
    - <span data-ttu-id="316bb-132">Recherchez l’application que vous avez créée et sélectionnez la drop-down sur la droite.</span><span class="sxs-lookup"><span data-stu-id="316bb-132">Find the app you created and select the drop-down on the right.</span></span> <span data-ttu-id="316bb-133">Sélectionnez **Gérer**</span><span class="sxs-lookup"><span data-stu-id="316bb-133">Select **Manage**</span></span>
    - <span data-ttu-id="316bb-134">Sélectionner des **stratégies de modification**</span><span class="sxs-lookup"><span data-stu-id="316bb-134">Select **edit policies**</span></span>
    - <span data-ttu-id="316bb-135">Pour la stratégie de jeton d’actualisation, **sélectionnez Le jeton d’actualisation est valide jusqu’à ce qu’il soit révoqué**</span><span class="sxs-lookup"><span data-stu-id="316bb-135">For refresh token policy, select **Refresh token is valid until revoked**</span></span>

  > [!div class="mx-imgBorder"]
  > <span data-ttu-id="316bb-136">![Sélectionnez la stratégie de jeton d’actualisation nommée « Jeton d’actualisation est valide jusqu’à ce qu’elle soit révoquée »](media/salesforce-connector/oauthpolicies.png)</span><span class="sxs-lookup"><span data-stu-id="316bb-136">![Select the Refresh Token Policy named "Refresh token is valid until revoked "](media/salesforce-connector/oauthpolicies.png)</span></span>

<span data-ttu-id="316bb-137">Vous pouvez désormais utiliser le [centre Administration Microsoft 365 pour](https://admin.microsoft.com/) terminer le reste du processus d’installation de votre connecteur Graph de connexion.</span><span class="sxs-lookup"><span data-stu-id="316bb-137">You can now use the [Microsoft 365 Admin Center](https://admin.microsoft.com/) to complete the rest of the setup process for your Graph connector.</span></span>

## <a name="step-1-add-a-graph-connector-in-the-microsoft-365-admin-center"></a><span data-ttu-id="316bb-138">Étape 1 : Ajouter un connecteur Graph dans le Centre d’administration Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="316bb-138">Step 1: Add a Graph connector in the Microsoft 365 admin center</span></span>

<span data-ttu-id="316bb-139">Suivez les [instructions d’installation générales.](./configure-connector.md)</span><span class="sxs-lookup"><span data-stu-id="316bb-139">Follow the general [setup instructions](./configure-connector.md).</span></span>
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-2-name-the-connection"></a><span data-ttu-id="316bb-140">Étape 2 : Nommer la connexion</span><span class="sxs-lookup"><span data-stu-id="316bb-140">Step 2: Name the connection</span></span>

<span data-ttu-id="316bb-141">Suivez les [instructions d’installation générales.](./configure-connector.md)</span><span class="sxs-lookup"><span data-stu-id="316bb-141">Follow the general [setup instructions](./configure-connector.md).</span></span>
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-3-configure-the-connection-settings"></a><span data-ttu-id="316bb-142">Étape 3 : Configurer les paramètres de connexion</span><span class="sxs-lookup"><span data-stu-id="316bb-142">Step 3: Configure the connection settings</span></span>

<span data-ttu-id="316bb-143">Pour l’URL d’instance, utilisez https://[domaine].my.salesforce.com où le domaine serait le domaine Salesforce de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="316bb-143">For the Instance URL, use https://[domain].my.salesforce.com where domain would be the Salesforce domain for your organization.</span></span>

<span data-ttu-id="316bb-144">Entrez l’ID client et la secret client que vous avez obtenus à partir de votre instance Salesforce, puis sélectionnez Se connectez.</span><span class="sxs-lookup"><span data-stu-id="316bb-144">Enter the Client ID and Client Secret you obtained from your Salesforce instance and select Sign in.</span></span>

<span data-ttu-id="316bb-145">La première fois que vous tentez de vous connecter à l’aide de ces paramètres, une fenêtre vous demande de vous connecter à Salesforce avec votre nom d’utilisateur et votre mot de passe d’administrateur.</span><span class="sxs-lookup"><span data-stu-id="316bb-145">The first time you've attempted to sign in with these settings, you'll get a pop-up asking you to log in to Salesforce with your admin username and password.</span></span> <span data-ttu-id="316bb-146">La capture d’écran ci-dessous montre la fenêtre pop-up.</span><span class="sxs-lookup"><span data-stu-id="316bb-146">The screenshot below shows the popup.</span></span> <span data-ttu-id="316bb-147">Entrez vos informations d’identification, puis sélectionnez « Se connecter ».</span><span class="sxs-lookup"><span data-stu-id="316bb-147">Enter your credentials and select "Log In".</span></span>

  ![Fenêtre de connexion pour demander le nom d’utilisateur et le mot de passe.](media/salesforce-connector/sf4.png)

  >[!NOTE]
  ><span data-ttu-id="316bb-149">Si la fenêtre pop-up n’apparaît pas, elle risque d’être bloquée dans votre navigateur. Vous devez donc autoriser les fenêtres pop-up et les redirections.</span><span class="sxs-lookup"><span data-stu-id="316bb-149">If the pop up does not appear, it might be getting blocked in your browser, so you must allow pop-ups and redirects.</span></span>

<span data-ttu-id="316bb-150">Vérifiez que la connexion a réussi en recherchant une bannière verte qui indique « Connexion réussie », comme indiqué dans la capture d’écran ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="316bb-150">Check that the connection was successful by searching for a green banner that says "Connection successful" as show in the screenshot below.</span></span>

  > [!div class="mx-imgBorder"]
  > <span data-ttu-id="316bb-151">![Capture d’écran de la connexion réussie.</span><span class="sxs-lookup"><span data-stu-id="316bb-151">![Screenshot of successful login.</span></span> <span data-ttu-id="316bb-152">La bannière verte qui indique « Connexion réussie » se trouve sous le champ de votre URL d’instance Salesforce](media/salesforce-connector/sf5.png)</span><span class="sxs-lookup"><span data-stu-id="316bb-152">The green banner that says "Connection successful" is located under the field for your Salesforce Instance URL](media/salesforce-connector/sf5.png)</span></span>

## <a name="step-4-manage-search-permissions"></a><span data-ttu-id="316bb-153">Étape 4 : Gérer les autorisations de recherche</span><span class="sxs-lookup"><span data-stu-id="316bb-153">Step 4: Manage search permissions</span></span>

<span data-ttu-id="316bb-154">Vous devez choisir les utilisateurs qui voient les résultats de la recherche à partir de cette source de données.</span><span class="sxs-lookup"><span data-stu-id="316bb-154">You'll need to choose which users will see search results from this data source.</span></span> <span data-ttu-id="316bb-155">Si vous autorisez uniquement certains utilisateurs Azure Active Directory (Azure AD) ou non-Azure AD à voir les résultats de la recherche, assurez-vous de ma cartographier les identités.</span><span class="sxs-lookup"><span data-stu-id="316bb-155">If you allow only certain Azure Active Directory (Azure AD) or Non-Azure AD users to see the search results, make sure you map the identities.</span></span>

### <a name="step-4a-select-permissions"></a><span data-ttu-id="316bb-156">Étape 4.a : Sélectionner les autorisations</span><span class="sxs-lookup"><span data-stu-id="316bb-156">Step 4.a: Select permissions</span></span>

<span data-ttu-id="316bb-157">Vous pouvez choisir d’ingèrer des listes de contrôle d’accès à partir de votre instance Salesforce ou autoriser tous les membres de votre organisation à voir les résultats de recherche provenant de cette source de données.</span><span class="sxs-lookup"><span data-stu-id="316bb-157">You can choose to ingest Access Control Lists (ACLs) from your Salesforce instance, or allow everyone in your organization to see search results from this data source.</span></span> <span data-ttu-id="316bb-158">Les ALA peuvent inclure des identités Azure Active Directory (AAD) (utilisateurs fédérés d’Azure AD à Salesforce), des identités non Azure AD (utilisateurs Salesforce natifs ayant des identités correspondantes dans Azure AD) ou les deux.</span><span class="sxs-lookup"><span data-stu-id="316bb-158">ACLs can include Azure Active Directory (AAD) identities (users who are federated from Azure AD to Salesforce), non-Azure AD identities (native Salesforce users who have corresponding identities in Azure AD), or both.</span></span>

>[!NOTE]
><span data-ttu-id="316bb-159">Si vous utilisez un fournisseur d’identité tiers comme Ping ID ou secureAuth, vous devez sélectionner « non-AAD » comme type d’identité.</span><span class="sxs-lookup"><span data-stu-id="316bb-159">If you use a third-party Identity Provider like Ping ID or secureAuth, you should select "non-AAD" as the identity type.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="316bb-160">![Écran Sélectionner les autorisations qui ont été effectuées par un administrateur. L’administrateur a sélectionné l’option « Uniquement les personnes ayant accès à cette source de données » et a également sélectionné « AAD » dans un menu déroulant de types d’identité.](media/salesforce-connector/sf6.png)</span><span class="sxs-lookup"><span data-stu-id="316bb-160">![Select permissions screen that has been completed by an admin. The admin has selected the "Only people with access to this data source" option and has also selected "AAD" from a drop down menu of identity types.](media/salesforce-connector/sf6.png)</span></span>

<span data-ttu-id="316bb-161">Si vous avez choisi d’ing d’une ACL à partir de votre instance Salesforce et que vous avez sélectionné « non-AAD » pour le type d’identité, voir Mappage de vos [identités non Azure AD](map-non-aad.md) pour obtenir des instructions sur le mappage des identités.</span><span class="sxs-lookup"><span data-stu-id="316bb-161">If you chose to ingest an ACL from your Salesforce instance and selected "non-AAD" for the identity type, see [Map your non-Azure AD Identities](map-non-aad.md) for instructions on mapping the identities.</span></span>

### <a name="step-4b-map-aad-identities"></a><span data-ttu-id="316bb-162">Étape 4.b : Maser les identités AAD</span><span class="sxs-lookup"><span data-stu-id="316bb-162">Step 4.b: Map AAD identities</span></span>

<span data-ttu-id="316bb-163">Si vous avez choisi d’ing d’une ACL à partir de votre instance Salesforce et que vous avez sélectionné « AAD » pour le type d’identité, voir Mappage de vos [identités Azure AD](map-aad.md) pour obtenir des instructions sur le mappage des identités.</span><span class="sxs-lookup"><span data-stu-id="316bb-163">If you chose to ingest an ACL from your Salesforce instance and selected "AAD" for the identity type, see [Map your Azure AD Identities](map-aad.md) for instructions on mapping the identities.</span></span> <span data-ttu-id="316bb-164">Pour savoir comment configurer Azure AD SSO pour Salesforce, consultez ce [didacticiel.](/azure/active-directory/saas-apps/salesforce-tutorial)</span><span class="sxs-lookup"><span data-stu-id="316bb-164">To learn how to set up Azure AD SSO for Salesforce, see this [tutorial](/azure/active-directory/saas-apps/salesforce-tutorial).</span></span>

### <a name="apply-user-mapping-to-sync-your-salesforce-identities-to-azure-ad-identities"></a><span data-ttu-id="316bb-165">Appliquer le mappage d’utilisateurs pour synchroniser vos identités Salesforce avec les identités Azure AD</span><span class="sxs-lookup"><span data-stu-id="316bb-165">Apply user mapping to sync your Salesforce identities to Azure AD identities</span></span>

<span data-ttu-id="316bb-166">Dans cette vidéo, vous pouvez voir le processus d’authentification à votre instance Salesforce, synchroniser vos identités non-Azure Active Directory avec vos identités Azure Active Directory et appliquer les trimmings de sécurité appropriés à vos éléments Salesforce.</span><span class="sxs-lookup"><span data-stu-id="316bb-166">In this video you can see the process to authenticate to your Salesforce instance, sync your non-Azure Active Directory identities to your Azure Active Directory identities, and apply the proper security trimmings to your Salesforce items.</span></span>

> [!VIDEO https://www.youtube-nocookie.com/embed/SZYiFxZMKcM]

## <a name="step-5-assign-property-labels"></a><span data-ttu-id="316bb-167">Étape 5 : Attribuer des étiquettes de propriété</span><span class="sxs-lookup"><span data-stu-id="316bb-167">Step 5: Assign property labels</span></span>

<span data-ttu-id="316bb-168">Vous pouvez affecter une propriété source à chaque étiquette en choisissant dans un menu d’options.</span><span class="sxs-lookup"><span data-stu-id="316bb-168">You can assign a source property to each label by choosing from a menu of options.</span></span> <span data-ttu-id="316bb-169">Bien que cette étape ne soit pas obligatoire, le fait d’avoir certaines étiquettes de propriétés améliorera la pertinence de la recherche et garantira de meilleurs résultats de recherche pour les utilisateurs finaux.</span><span class="sxs-lookup"><span data-stu-id="316bb-169">While this step is not mandatory, having some property labels will improve the search relevance and ensure better search results for end users.</span></span> <span data-ttu-id="316bb-170">Par défaut, certaines étiquettes telles que « Titre », « URL », « CreatedBy » et « LastModifiedBy » se sont déjà vu attribuer des propriétés source.</span><span class="sxs-lookup"><span data-stu-id="316bb-170">By default, some of the Labels like "Title," "URL," "CreatedBy," and  "LastModifiedBy" have already been assigned source properties.</span></span>

## <a name="step-6-manage-schema"></a><span data-ttu-id="316bb-171">Étape 6 : Gérer le schéma</span><span class="sxs-lookup"><span data-stu-id="316bb-171">Step 6: Manage schema</span></span>

<span data-ttu-id="316bb-172">Vous pouvez sélectionner les propriétés source qui doivent être indexées afin qu’elles s’afficheront dans les résultats de la recherche.</span><span class="sxs-lookup"><span data-stu-id="316bb-172">You can select what source properties should be indexed so that they show up in search results.</span></span> <span data-ttu-id="316bb-173">L’Assistant Connexion sélectionne par défaut un schéma de recherche basé sur un ensemble de propriétés source.</span><span class="sxs-lookup"><span data-stu-id="316bb-173">The connection wizard by default selects a search schema based on a set of source properties.</span></span> <span data-ttu-id="316bb-174">Vous pouvez le modifier en élecntant les cases à cocher de chaque propriété et attribut de la page de schéma de recherche.</span><span class="sxs-lookup"><span data-stu-id="316bb-174">You can modify it by selecting the check boxes for each property and attribute in the search schema page.</span></span> <span data-ttu-id="316bb-175">Les attributs de schéma de recherche incluent recherche, requête, récupération et affiner.</span><span class="sxs-lookup"><span data-stu-id="316bb-175">Search schema attributes include Search, Query, Retrieve, and Refine.</span></span>
<span data-ttu-id="316bb-176">L’affinement vous permet de définir les propriétés qui peuvent être utilisées ultérieurement en tant qu’affinements ou filtres personnalisés dans l’expérience de recherche.</span><span class="sxs-lookup"><span data-stu-id="316bb-176">Refine allows you to define the properties that can be later used as custom refiners or filters in the search experience.</span></span>  

> [!div class="mx-imgBorder"]
> <span data-ttu-id="316bb-177">![Sélectionnez le schéma pour chaque propriété source.</span><span class="sxs-lookup"><span data-stu-id="316bb-177">![Select the schema for each source property.</span></span> <span data-ttu-id="316bb-178">Les options sont Requête, Recherche, Récupérer et Affiner](media/salesforce-connector/sf9.png)</span><span class="sxs-lookup"><span data-stu-id="316bb-178">The options are Query, Search, Retrieve, and Refine](media/salesforce-connector/sf9.png)</span></span>

## <a name="step-7-set-the-refresh-schedule"></a><span data-ttu-id="316bb-179">Étape 7 : Définir la planification de l’actualisation</span><span class="sxs-lookup"><span data-stu-id="316bb-179">Step 7: Set the refresh schedule</span></span>

<span data-ttu-id="316bb-180">Le connecteur Salesforce prend uniquement en charge les planifications d’actualisation pour les analyse complètes actuellement.</span><span class="sxs-lookup"><span data-stu-id="316bb-180">The Salesforce connector only supports refresh schedules for full crawls currently.</span></span>

>[!IMPORTANT]
><span data-ttu-id="316bb-181">Une analyse complète recherche les objets et les utilisateurs supprimés qui ont été précédemment synchronisés avec l Recherche Microsoft index.</span><span class="sxs-lookup"><span data-stu-id="316bb-181">A full crawl finds deleted objects and users that were previously synced to the Microsoft Search index.</span></span>

<span data-ttu-id="316bb-182">La planification recommandée est d’une semaine pour une analyse complète.</span><span class="sxs-lookup"><span data-stu-id="316bb-182">The recommended schedule is one week for a full crawl.</span></span>

## <a name="step-8-review-connection"></a><span data-ttu-id="316bb-183">Étape 8 : Examiner la connexion</span><span class="sxs-lookup"><span data-stu-id="316bb-183">Step 8: Review connection</span></span>

<span data-ttu-id="316bb-184">Suivez les [instructions d’installation générales.](./configure-connector.md)</span><span class="sxs-lookup"><span data-stu-id="316bb-184">Follow the general [setup instructions](./configure-connector.md).</span></span>
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

<!---## Troubleshooting-->
<!---Insert troubleshooting recommendations for this data source-->

## <a name="limitations"></a><span data-ttu-id="316bb-185">Limites</span><span class="sxs-lookup"><span data-stu-id="316bb-185">Limitations</span></span>

- <span data-ttu-id="316bb-186">Le connecteur Graph ne prend actuellement pas en charge le partage basé sur apex basé sur un territoire et le partage à l’aide de groupes personnels de Salesforce.</span><span class="sxs-lookup"><span data-stu-id="316bb-186">The Graph connector doesn't currently support Apex based, territory-based sharing and sharing using personal groups from Salesforce.</span></span>
- <span data-ttu-id="316bb-187">Il existe un bogue connu dans l’API Salesforce que le connecteur Graph utilise, où les valeurs par défaut à l’échelle de l’organisation privée pour les prospects ne sont pas honorées actuellement.</span><span class="sxs-lookup"><span data-stu-id="316bb-187">There's a known bug in the Salesforce API the Graph connector uses, where the private org-wide defaults for leads aren't honored currently.</span></span>  
- <span data-ttu-id="316bb-188">Si un champ a la sécurité au niveau du champ (FLS) définie pour un profil, le connecteur Graph n’ing aura pas ce champ pour les profils dans cette organisation Salesforce. Par conséquent, les utilisateurs ne pourront pas rechercher sur les valeurs de ces champs, ni s’afficher dans les résultats.</span><span class="sxs-lookup"><span data-stu-id="316bb-188">If a field has field level security (FLS) set for a profile, the Graph connector won't ingest that field for any profiles in that Salesforce org. As a result, users won't be able to search on values for those fields, nor will it show up in the results.</span></span>  
- <span data-ttu-id="316bb-189">Dans l’écran Gérer le schéma, ces noms de propriété standard communs sont répertoriés une seule fois, les options sont **Requête,** **Rechercher,** Récupérer **et** **Affiner,** et s’appliquent à tout ou aucun.</span><span class="sxs-lookup"><span data-stu-id="316bb-189">In the Manage Schema screen these common standard property names are listed once, the options are **Query**, **Search**, **Retrieve**, and **Refine**, and apply to all or none.</span></span>
    - <span data-ttu-id="316bb-190">Nom</span><span class="sxs-lookup"><span data-stu-id="316bb-190">Name</span></span>
    - <span data-ttu-id="316bb-191">Url</span><span class="sxs-lookup"><span data-stu-id="316bb-191">Url</span></span>
    - <span data-ttu-id="316bb-192">Description</span><span class="sxs-lookup"><span data-stu-id="316bb-192">Description</span></span>
    - <span data-ttu-id="316bb-193">Fax</span><span class="sxs-lookup"><span data-stu-id="316bb-193">Fax</span></span>
    - <span data-ttu-id="316bb-194">Téléphone</span><span class="sxs-lookup"><span data-stu-id="316bb-194">Phone</span></span>
    - <span data-ttu-id="316bb-195">MobilePhone</span><span class="sxs-lookup"><span data-stu-id="316bb-195">MobilePhone</span></span>
    - <span data-ttu-id="316bb-196">E-mail</span><span class="sxs-lookup"><span data-stu-id="316bb-196">Email</span></span>
    - <span data-ttu-id="316bb-197">Type</span><span class="sxs-lookup"><span data-stu-id="316bb-197">Type</span></span>
    - <span data-ttu-id="316bb-198">Titre</span><span class="sxs-lookup"><span data-stu-id="316bb-198">Title</span></span>
    - <span data-ttu-id="316bb-199">AccountId</span><span class="sxs-lookup"><span data-stu-id="316bb-199">AccountId</span></span>
    - <span data-ttu-id="316bb-200">AccountName</span><span class="sxs-lookup"><span data-stu-id="316bb-200">AccountName</span></span>
    - <span data-ttu-id="316bb-201">AccountUrl</span><span class="sxs-lookup"><span data-stu-id="316bb-201">AccountUrl</span></span>
    - <span data-ttu-id="316bb-202">AccountOwner</span><span class="sxs-lookup"><span data-stu-id="316bb-202">AccountOwner</span></span>
    - <span data-ttu-id="316bb-203">AccountOwnerUrl</span><span class="sxs-lookup"><span data-stu-id="316bb-203">AccountOwnerUrl</span></span>
    - <span data-ttu-id="316bb-204">Propriétaire</span><span class="sxs-lookup"><span data-stu-id="316bb-204">Owner</span></span>
    - <span data-ttu-id="316bb-205">OwnerUrl</span><span class="sxs-lookup"><span data-stu-id="316bb-205">OwnerUrl</span></span>
    - <span data-ttu-id="316bb-206">CreatedBy</span><span class="sxs-lookup"><span data-stu-id="316bb-206">CreatedBy</span></span>
    - <span data-ttu-id="316bb-207">CreatedByUrl</span><span class="sxs-lookup"><span data-stu-id="316bb-207">CreatedByUrl</span></span>
    - <span data-ttu-id="316bb-208">LastModifiedBy</span><span class="sxs-lookup"><span data-stu-id="316bb-208">LastModifiedBy</span></span>
    - <span data-ttu-id="316bb-209">LastModifiedByUrl</span><span class="sxs-lookup"><span data-stu-id="316bb-209">LastModifiedByUrl</span></span>
    - <span data-ttu-id="316bb-210">LastModifiedDate</span><span class="sxs-lookup"><span data-stu-id="316bb-210">LastModifiedDate</span></span>
    - <span data-ttu-id="316bb-211">ObjectName</span><span class="sxs-lookup"><span data-stu-id="316bb-211">ObjectName</span></span>
