---
title: Connecteur Salesforce pour Microsoft Search
ms.author: rusamai
author: rsamai
manager: jameslau
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: Configurer le connecteur Salesforce pour Microsoft Search
ms.openlocfilehash: 149d1d9a297e09e9b895aeb0947c7ff4a3cbdf84
ms.sourcegitcommit: 59cdd3f0f82b7918399bf44d27d9891076090f4f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/20/2020
ms.locfileid: "49367648"
---
# <a name="salesforce-connector-preview"></a><span data-ttu-id="3f902-103">Connecteur Salesforce (aperçu)</span><span class="sxs-lookup"><span data-stu-id="3f902-103">Salesforce connector (preview)</span></span>

<span data-ttu-id="3f902-104">Avec le connecteur de graphique Salesforce, votre organisation peut indexer des contacts, des opportunités, des prospects et des objets de comptes dans votre instance Salesforce.</span><span class="sxs-lookup"><span data-stu-id="3f902-104">With the Salesforce Graph connector, your organization can index Contacts, Opportunities, Leads and Accounts objects in your Salesforce instance.</span></span> <span data-ttu-id="3f902-105">Une fois que vous avez configuré le connecteur et le contenu d’index à partir de Salesforce, les utilisateurs finaux peuvent rechercher ces éléments à partir de n’importe quel client Microsoft Search.</span><span class="sxs-lookup"><span data-stu-id="3f902-105">After you configure the connector and index content from Salesforce, end users can search for those items from any Microsoft Search client.</span></span>

<span data-ttu-id="3f902-106">Cet article est destiné aux administrateurs [365 de Microsoft](https://www.microsoft.com/microsoft-365) ou toute personne qui configure, exécute et surveille un connecteur Salesforce.</span><span class="sxs-lookup"><span data-stu-id="3f902-106">This article is for [Microsoft 365](https://www.microsoft.com/microsoft-365) administrators or anyone who configures, runs, and monitors a Salesforce connector.</span></span> <span data-ttu-id="3f902-107">Elle explique comment configurer les fonctionnalités de connecteur et de connecteur, ainsi que les restrictions et les techniques de résolution des problèmes.</span><span class="sxs-lookup"><span data-stu-id="3f902-107">It explains how to configure your connector and connector capabilities, limitations, and troubleshooting techniques.</span></span>

>[!IMPORTANT]
><span data-ttu-id="3f902-108">Le connecteur de graphique Salesforce prend actuellement en charge l’été le 19 ou une version ultérieure.</span><span class="sxs-lookup"><span data-stu-id="3f902-108">The Salesforce Graph connector currently supports Summer '19 or later.</span></span>

## <a name="connection-settings"></a><span data-ttu-id="3f902-109">Paramètres de connexion</span><span class="sxs-lookup"><span data-stu-id="3f902-109">Connection settings</span></span>

<span data-ttu-id="3f902-110">Pour vous connecter à votre instance Salesforce, vous avez besoin de l’URL de votre instance de Salesforce, de l’ID client et de la clé secrète client pour l’authentification OAuth.</span><span class="sxs-lookup"><span data-stu-id="3f902-110">To connect to your Salesforce instance, you need your Salesforce instance URL, the Client ID, and Client Secret for OAuth authentication.</span></span> <span data-ttu-id="3f902-111">Les étapes suivantes expliquent comment vous ou votre administrateur Salesforce pouvez obtenir ces informations à partir de votre compte Salesforce :</span><span class="sxs-lookup"><span data-stu-id="3f902-111">The following steps explain how you or your Salesforce administrator can get this information from your Salesforce account:</span></span>

- <span data-ttu-id="3f902-112">Connectez-vous à votre instance Salesforce et accédez à la configuration.</span><span class="sxs-lookup"><span data-stu-id="3f902-112">Log in to your Salesforce instance and go to Setup</span></span>

- <span data-ttu-id="3f902-113">Accédez à applications-> gestionnaire d’applications.</span><span class="sxs-lookup"><span data-stu-id="3f902-113">Navigate to Apps -> App Manager.</span></span>

- <span data-ttu-id="3f902-114">Sélectionnez **nouvelle application connectée**.</span><span class="sxs-lookup"><span data-stu-id="3f902-114">Select **New connected app**.</span></span>

- <span data-ttu-id="3f902-115">Complétez la section API comme suit :</span><span class="sxs-lookup"><span data-stu-id="3f902-115">Complete the API section as follows:</span></span>

    - <span data-ttu-id="3f902-116">Activez la case à cocher **activer les paramètres OAuth**.</span><span class="sxs-lookup"><span data-stu-id="3f902-116">Select the checkbox for **Enable Oauth Settings**.</span></span>

    - <span data-ttu-id="3f902-117">Spécifiez l’URL de rappel comme suit : [https://gcs.office.com/v1.0/admin/oauth/callback](https://gcs.office.com/v1.0/admin/oauth/callback)</span><span class="sxs-lookup"><span data-stu-id="3f902-117">Specify the Callback URL as: [https://gcs.office.com/v1.0/admin/oauth/callback](https://gcs.office.com/v1.0/admin/oauth/callback)</span></span>

    - <span data-ttu-id="3f902-118">Sélectionnez ces étendues OAuth requises.</span><span class="sxs-lookup"><span data-stu-id="3f902-118">Select these required OAuth scopes.</span></span> 

        - <span data-ttu-id="3f902-119">Accéder aux données et les gérer (API)</span><span class="sxs-lookup"><span data-stu-id="3f902-119">Access and manage your data (api)</span></span> 

        - <span data-ttu-id="3f902-120">Effectuer des demandes en votre nom à tout moment (refresh_token, offline_access)</span><span class="sxs-lookup"><span data-stu-id="3f902-120">Perform requests on your behalf at any time (refresh_token, offline_access)</span></span> 

    - <span data-ttu-id="3f902-121">Activez la case à cocher **exiger une clé secrète pour le flux de serveur Web**.</span><span class="sxs-lookup"><span data-stu-id="3f902-121">Select the checkbox for **Require secret for web server flow**.</span></span>

    - <span data-ttu-id="3f902-122">Enregistrez l’application.</span><span class="sxs-lookup"><span data-stu-id="3f902-122">Save the app.</span></span>
    
      ![Section API dans l’instance Salesforce une fois que l’administrateur a entré toutes les configurations requises mentionnées ci-dessus.](media/salesforce-connector/sf1.png)

- <span data-ttu-id="3f902-124">Copiez la clé de consommateur et la clé secrète consommateur.</span><span class="sxs-lookup"><span data-stu-id="3f902-124">Copy the consumer key and the consumer secret.</span></span> <span data-ttu-id="3f902-125">Ceux-ci seront utilisés comme ID client et clé secrète client lorsque vous configurez les paramètres de connexion de votre connecteur Graph dans le portail d’administration Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="3f902-125">These will be used as the Client ID and the Client Secret when you configure the Connection Settings for your Graph Connector in the Microsoft 365 admin portal.</span></span>

  ![Résultats retournés par la section API dans l’instance Salesforce une fois que l’administrateur a soumis toutes les configurations requises.](media/salesforce-connector/clientsecret.png)
- <span data-ttu-id="3f902-128">Avant de fermer votre instance de Salesforce, effectuez les étapes suivantes pour vous assurer que les jetons d’actualisation n’expirent pas :</span><span class="sxs-lookup"><span data-stu-id="3f902-128">Before closing your Salesforce instance, perform the following steps to ensure that refresh tokens do not expire:</span></span>
    - <span data-ttu-id="3f902-129">Accédez à applications-> App Manager</span><span class="sxs-lookup"><span data-stu-id="3f902-129">Go to Apps -> App Manager</span></span>
    - <span data-ttu-id="3f902-130">Recherchez l’application que vous venez de créer et sélectionnez la liste déroulante sur la droite.</span><span class="sxs-lookup"><span data-stu-id="3f902-130">Find the app you just created and select the drop down on the right.</span></span> <span data-ttu-id="3f902-131">Sélectionnez **gérer**</span><span class="sxs-lookup"><span data-stu-id="3f902-131">Select **Manage**</span></span>
    - <span data-ttu-id="3f902-132">Sélectionnez **modifier les stratégies**</span><span class="sxs-lookup"><span data-stu-id="3f902-132">Select **edit policies**</span></span>
    - <span data-ttu-id="3f902-133">Pour la stratégie de jeton d’actualisation, sélectionnez le **jeton d’actualisation est valide jusqu’à révoqué** .</span><span class="sxs-lookup"><span data-stu-id="3f902-133">For refresh token policy, select **Refresh token is valid until revoked**</span></span>

  ![Sélectionnez la stratégie d’actualisation des jetons nommée « actualisation du jeton est valide jusqu’à révoqué »](media/salesforce-connector/oauthpolicies.png)

<span data-ttu-id="3f902-135">Vous pouvez désormais utiliser le [Centre d’administration M365](https://admin.microsoft.com/) pour terminer le reste du processus de configuration de votre connecteur Graph.</span><span class="sxs-lookup"><span data-stu-id="3f902-135">You can now use the [M365 Admin Center](https://admin.microsoft.com/) to complete the rest of the setup process for your Graph connector.</span></span>  

<span data-ttu-id="3f902-136">Configurez les paramètres de connexion de votre connecteur Graph comme suit :</span><span class="sxs-lookup"><span data-stu-id="3f902-136">Configure the Connection settings for your Graph connector as follows:</span></span>

- <span data-ttu-id="3f902-137">Pour l’URL d’instance, utilisez https://[domaine]. My. salesforce. com où Domain serait le domaine Salesforce de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="3f902-137">For the Instance URL, use https://[domain].my.salesforce.com where domain would be the Salesforce domain for your organization.</span></span> 
- <span data-ttu-id="3f902-138">Entrez l’ID client et la clé secrète client que vous avez obtenus à partir de votre instance Salesforce et sélectionnez connexion.</span><span class="sxs-lookup"><span data-stu-id="3f902-138">Enter the Client ID and Client Secret you obtained from your Salesforce instance and select Sign in.</span></span>
- <span data-ttu-id="3f902-139">S’il s’agit de la première fois que vous tentez de vous connecter avec ces paramètres, une fenêtre contextuelle s’affiche pour vous demander de vous connecter à la force de connexion avec votre nom d’utilisateur et votre mot de passe d’administrateur.</span><span class="sxs-lookup"><span data-stu-id="3f902-139">If this is the first time you have attempted to Sign in with these settings, you will get a pop up asking you to login to Salesforce with your admin username and password.</span></span> <span data-ttu-id="3f902-140">La capture d’écran ci-dessous montre le menu contextuel.</span><span class="sxs-lookup"><span data-stu-id="3f902-140">The screenshot below shows the popup.</span></span> <span data-ttu-id="3f902-141">Entrez vos informations d’identification et sélectionnez connexion.</span><span class="sxs-lookup"><span data-stu-id="3f902-141">Enter your credentials and select Log in.</span></span>

  ![Ouverture de session contextuelle demandant le nom d’utilisateur et le mot de passe.](media/salesforce-connector/sf4.png)

  >[!NOTE]
  ><span data-ttu-id="3f902-143">Si la fenêtre contextuelle ne s’affiche pas, elle peut être bloquée dans votre navigateur, vous devez donc autoriser les fenêtres publicitaires intempestives et les redirections.</span><span class="sxs-lookup"><span data-stu-id="3f902-143">If the pop up does not appear, it might be getting blocked in your browser, so you must allow pop-ups and redirects.</span></span>

  >[!NOTE]
  ><span data-ttu-id="3f902-144">Si votre organisation utilise l’authentification unique (SSO), vous pouvez sélectionner **utiliser un domaine personnalisé** dans le coin inférieur droit de l’interface de connexion.</span><span class="sxs-lookup"><span data-stu-id="3f902-144">If your organization uses single sign-on (SSO), you can select **Use Custom Domain** in the bottom, right-hand corner of the login interface.</span></span> <span data-ttu-id="3f902-145">Entrez le domaine, puis cliquez sur **Continuer**.</span><span class="sxs-lookup"><span data-stu-id="3f902-145">Enter the domain and then select **Continue**.</span></span> <span data-ttu-id="3f902-146">Il accède à la page de connexion spécifique de votre organisation où vous pouvez vous connecter à l’aide de l’authentification unique.</span><span class="sxs-lookup"><span data-stu-id="3f902-146">It will go to your organization specific login page where you will have an option to login with SSO.</span></span>

- <span data-ttu-id="3f902-147">Vérifiez que la connexion a réussi en recherchant une bannière verte indiquant « connexion réussie » comme illustré dans la capture d’écran ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="3f902-147">Check that the connection was successful by searching for a green banner that says "Connection successful" as show in the screenshot below.</span></span>

  ![Capture d’écran de la connexion réussie.](media/salesforce-connector/sf5.png)

## <a name="manage-search-permissions"></a><span data-ttu-id="3f902-150">Gérer les autorisations de recherche</span><span class="sxs-lookup"><span data-stu-id="3f902-150">Manage search permissions</span></span>
<span data-ttu-id="3f902-151">Vous devrez choisir les utilisateurs qui verront les résultats de la recherche à partir de cette source de données.</span><span class="sxs-lookup"><span data-stu-id="3f902-151">You will need to choose which users will see search results from this data source.</span></span> <span data-ttu-id="3f902-152">Si vous autorisez uniquement certains utilisateurs Azure Active Directory (Azure AD) ou non Azure AD à voir les résultats de la recherche, vous devrez mapper les identités.</span><span class="sxs-lookup"><span data-stu-id="3f902-152">If you allow only certain Azure Active Directory (Azure AD) or Non-Azure AD users to see the search results, you will then need to map the identities.</span></span>

### <a name="select-permissions"></a><span data-ttu-id="3f902-153">Sélectionner des autorisations</span><span class="sxs-lookup"><span data-stu-id="3f902-153">Select Permissions</span></span>
<span data-ttu-id="3f902-154">Vous pouvez choisir d’ingérer les listes de contrôle d’accès (ACL) à partir de votre instance Salesforce ou vous pouvez autoriser tous les membres de votre organisation à consulter les résultats de la recherche à partir de cette source de données.</span><span class="sxs-lookup"><span data-stu-id="3f902-154">You can choose to ingest Access Control Lists (ACLs) from your Salesforce instance, or you can allow everyone in your organization to see search results from this data source.</span></span> <span data-ttu-id="3f902-155">Les listes de Contrã’le d’accès peuvent inclure des identités AAD (Azure Active Directory) (utilisateurs fédérés d’Azure AD à la force de la force), des identités non Azure AD (utilisateurs de la force de la force de l’offre correspondante dans Azure AD) ou les deux.</span><span class="sxs-lookup"><span data-stu-id="3f902-155">ACLs can include Azure Active Directory (AAD) identities (users who are federated from Azure AD to Salesforce), non-Azure AD identities (native Salesforce users who have corresponding identities in Azure AD), or both.</span></span>

![Sélectionnez l’écran autorisations qui a été complété par un administrateur. L’administrateur a sélectionné l’option « uniquement les personnes ayant accès à cette source de données » et a également sélectionné « AAD » dans un menu déroulant des types d’identité.](media/salesforce-connector/sf6.png)

### <a name="map-non-aad-identities"></a><span data-ttu-id="3f902-157">Mapper des identités non AAD</span><span class="sxs-lookup"><span data-stu-id="3f902-157">Map non-AAD identities</span></span> 
<span data-ttu-id="3f902-158">Si vous avez choisi d’une liste de contrôle d’accès à partir de votre instance Salesforce et que vous avez sélectionné « non AAD » pour le type d’identité, voir [mapper vos identités non Azure ad](map-non-aad.md) pour obtenir des instructions sur le mappage des identités.</span><span class="sxs-lookup"><span data-stu-id="3f902-158">If you chose to ingest an ACL from your Salesforce instance and selected "non-AAD" for the identity type see [Map your non-Azure AD Identities](map-non-aad.md) for instructions on mapping the identities.</span></span>

### <a name="map-aad-identities"></a><span data-ttu-id="3f902-159">Mapper des identités AAD</span><span class="sxs-lookup"><span data-stu-id="3f902-159">Map AAD identities</span></span>
<span data-ttu-id="3f902-160">Si vous avez choisi d’une liste de contrôle d’accès à partir de votre instance Salesforce et que vous avez sélectionné « AAD » pour le type d’identité, voir [mapper vos identités Azure ad](map-aad.md) pour obtenir des instructions sur le mappage des identités.</span><span class="sxs-lookup"><span data-stu-id="3f902-160">If you chose to ingest an ACL from your Salesforce instance and selected "AAD" for the identity type see [Map your Azure AD Identities](map-aad.md) for instructions on mapping the identities.</span></span> <span data-ttu-id="3f902-161">Pour en savoir plus sur la configuration de l’authentification unique Azure AD pour Salesforce, reportez-vous à ce [didacticiel](https://docs.microsoft.com/en-us/azure/active-directory/saas-apps/salesforce-tutorial).</span><span class="sxs-lookup"><span data-stu-id="3f902-161">To learn how to set up Azure AD SSO for Salesforce, see this [tutorial](https://docs.microsoft.com/en-us/azure/active-directory/saas-apps/salesforce-tutorial).</span></span>

## <a name="assign-property-labels"></a><span data-ttu-id="3f902-162">Affecter des étiquettes de propriété</span><span class="sxs-lookup"><span data-stu-id="3f902-162">Assign property labels</span></span> 
<span data-ttu-id="3f902-163">Vous pouvez affecter une propriété source à chaque étiquette en choisissant dans un menu d’options.</span><span class="sxs-lookup"><span data-stu-id="3f902-163">You can assign a source property to each label by choosing from a menu of options.</span></span> <span data-ttu-id="3f902-164">Si cette étape n’est pas obligatoire, le fait d’avoir des étiquettes de propriété améliore la pertinence de la recherche et garantit des résultats de recherche plus précis pour les utilisateurs finaux.</span><span class="sxs-lookup"><span data-stu-id="3f902-164">While this step is not mandatory, having some property labels will improve the search relevance and ensure more accurate search results for end users.</span></span> <span data-ttu-id="3f902-165">Par défaut, certaines étiquettes comme « titre », « URL », « CreatedBy » et « LastModifiedBy » ont déjà reçu des propriétés source.</span><span class="sxs-lookup"><span data-stu-id="3f902-165">By default, some of the Labels like "Title," "URL," "CreatedBy," and  "LastModifiedBy" have already been assigned source properties.</span></span>

![Écran affecter des étiquettes de propriétés affichant les propriétés de la source par défaut.](media/salesforce-connector/sf8.png)

## <a name="manage-schema"></a><span data-ttu-id="3f902-167">Gérer le schéma</span><span class="sxs-lookup"><span data-stu-id="3f902-167">Manage Schema</span></span>
<span data-ttu-id="3f902-168">Vous pouvez sélectionner les propriétés sources à indexer pour qu’elles puissent apparaître dans les résultats de la recherche.</span><span class="sxs-lookup"><span data-stu-id="3f902-168">You can select what source properties should be indexed so that they can show up in search results.</span></span> <span data-ttu-id="3f902-169">Par défaut, l’Assistant Connexion sélectionne un schéma de recherche en fonction d’un ensemble de propriétés source.</span><span class="sxs-lookup"><span data-stu-id="3f902-169">The connection wizard by default selects a search schema based on a set of source properties.</span></span> <span data-ttu-id="3f902-170">Vous pouvez le modifier en activant les cases à cocher de chaque propriété et attribut dans la page schéma de recherche.</span><span class="sxs-lookup"><span data-stu-id="3f902-170">You can modify it by selecting the check boxes for each property and attribute in the search schema page.</span></span> <span data-ttu-id="3f902-171">Les attributs de schéma de recherche incluent la recherche, la requête, l’extraction et l’affinement.</span><span class="sxs-lookup"><span data-stu-id="3f902-171">Search schema attributes include Search, Query, Retrieve and Refine.</span></span> <span data-ttu-id="3f902-172">Affiner vous permet de définir les propriétés qui peuvent être utilisées ultérieurement en tant qu’affinements personnalisés ou filtres dans l’expérience de recherche.</span><span class="sxs-lookup"><span data-stu-id="3f902-172">Refine allows you to define the properties which can be later used as custom refiners or filters in the search experience.</span></span>  

![Sélectionnez le schéma pour chaque propriété source.](media/salesforce-connector/sf9.png)

## <a name="set-the-refresh-schedule"></a><span data-ttu-id="3f902-175">Définir la planification d’actualisation</span><span class="sxs-lookup"><span data-stu-id="3f902-175">Set the refresh schedule</span></span>

<span data-ttu-id="3f902-176">Le connecteur Salesforce prend uniquement en charge l’actualisation des planifications pour les analyses complètes actuellement.</span><span class="sxs-lookup"><span data-stu-id="3f902-176">The Salesforce connector only supports refresh schedules for full crawls currently.</span></span>

>[!IMPORTANT]
><span data-ttu-id="3f902-177">Une analyse complète recherche les objets et les utilisateurs supprimés qui ont été précédemment synchronisés avec l’index de recherche Microsoft.</span><span class="sxs-lookup"><span data-stu-id="3f902-177">A full crawl finds deleted objects and users that were previously synced to the Microsoft Search index.</span></span>

<span data-ttu-id="3f902-178">La planification recommandée est d’une semaine pour une analyse complète.</span><span class="sxs-lookup"><span data-stu-id="3f902-178">The recommended schedule is one week for a full crawl.</span></span>

## <a name="limitations"></a><span data-ttu-id="3f902-179">Limites</span><span class="sxs-lookup"><span data-stu-id="3f902-179">Limitations</span></span>

- <span data-ttu-id="3f902-180">Le connecteur Graph ne prend actuellement pas en charge le partage et le partage basés sur un apex basé sur les territoires à l’aide de groupes personnels de salesforce.</span><span class="sxs-lookup"><span data-stu-id="3f902-180">The Graph connector does not currently support Apex based , territory-based sharing and sharing using personal groups from Salesforce.</span></span>
- <span data-ttu-id="3f902-181">Il existe un bogue connu dans l’API Salesforce que le connecteur Graph utilise lorsque les valeurs par défaut à l’échelle de l’organisation privée pour les prospects ne sont pas honorées actuellement.</span><span class="sxs-lookup"><span data-stu-id="3f902-181">There is a known bug in the Salesforce API that the Graph connector uses where the private org wide defaults for leads is not honored currently.</span></span>  
- <span data-ttu-id="3f902-182">Si un champ a une sécurité au niveau champ (FLS) définie pour un profil, le connecteur Graph n’admettra pas ce champ aux profils de cette organisation Salesforce. Par conséquent, les utilisateurs ne pourront pas Rechercher des valeurs de ces champs, ni s’afficher dans les résultats.</span><span class="sxs-lookup"><span data-stu-id="3f902-182">If a field has field level security (FLS) set for a profile, the Graph connector will not ingest that field for any profiles in that Salesforce org. Users will thus not be able to search on values for those fields, nor will it  show up in the results.</span></span>  
- <span data-ttu-id="3f902-183">Dans l’écran gérer le schéma, ces noms de propriétés standard courants sont répertoriés une fois et la sélection est effectuée pour les rendre interutilisables, pouvant faire l’objet d’une recherche et d’une extraction s’appliquent à tout ou aucun.</span><span class="sxs-lookup"><span data-stu-id="3f902-183">In the Manage Schema screen these common standard property names are listed once and the selection done to make them queryable, searchable and retrievable apply to all or none.</span></span>
    - <span data-ttu-id="3f902-184">Nom</span><span class="sxs-lookup"><span data-stu-id="3f902-184">Name</span></span>
    - <span data-ttu-id="3f902-185">Url</span><span class="sxs-lookup"><span data-stu-id="3f902-185">Url</span></span> 
    - <span data-ttu-id="3f902-186">Description</span><span class="sxs-lookup"><span data-stu-id="3f902-186">Description</span></span>
    - <span data-ttu-id="3f902-187">Fax</span><span class="sxs-lookup"><span data-stu-id="3f902-187">Fax</span></span>
    - <span data-ttu-id="3f902-188">Téléphone</span><span class="sxs-lookup"><span data-stu-id="3f902-188">Phone</span></span>
    - <span data-ttu-id="3f902-189">MobilePhone</span><span class="sxs-lookup"><span data-stu-id="3f902-189">MobilePhone</span></span>
    - <span data-ttu-id="3f902-190">E-mail</span><span class="sxs-lookup"><span data-stu-id="3f902-190">Email</span></span>
    - <span data-ttu-id="3f902-191">Tapez</span><span class="sxs-lookup"><span data-stu-id="3f902-191">Type</span></span>
    - <span data-ttu-id="3f902-192">Titre</span><span class="sxs-lookup"><span data-stu-id="3f902-192">Title</span></span>
    - <span data-ttu-id="3f902-193">AccountId</span><span class="sxs-lookup"><span data-stu-id="3f902-193">AccountId</span></span>
    - <span data-ttu-id="3f902-194">AccountName</span><span class="sxs-lookup"><span data-stu-id="3f902-194">AccountName</span></span>
    - <span data-ttu-id="3f902-195">AccountUrl</span><span class="sxs-lookup"><span data-stu-id="3f902-195">AccountUrl</span></span>
    - <span data-ttu-id="3f902-196">AccountOwner</span><span class="sxs-lookup"><span data-stu-id="3f902-196">AccountOwner</span></span>
    - <span data-ttu-id="3f902-197">AccountOwnerUrl</span><span class="sxs-lookup"><span data-stu-id="3f902-197">AccountOwnerUrl</span></span>
    - <span data-ttu-id="3f902-198">Propriétaire</span><span class="sxs-lookup"><span data-stu-id="3f902-198">Owner</span></span>
    - <span data-ttu-id="3f902-199">OwnerUrl</span><span class="sxs-lookup"><span data-stu-id="3f902-199">OwnerUrl</span></span>
    - <span data-ttu-id="3f902-200">CreatedBy</span><span class="sxs-lookup"><span data-stu-id="3f902-200">CreatedBy</span></span> 
    - <span data-ttu-id="3f902-201">CreatedByUrl</span><span class="sxs-lookup"><span data-stu-id="3f902-201">CreatedByUrl</span></span> 
    - <span data-ttu-id="3f902-202">LastModifiedBy</span><span class="sxs-lookup"><span data-stu-id="3f902-202">LastModifiedBy</span></span> 
    - <span data-ttu-id="3f902-203">LastModifiedByUrl</span><span class="sxs-lookup"><span data-stu-id="3f902-203">LastModifiedByUrl</span></span> 
    - <span data-ttu-id="3f902-204">LastModifiedDate</span><span class="sxs-lookup"><span data-stu-id="3f902-204">LastModifiedDate</span></span>
    - <span data-ttu-id="3f902-205">ObjectName</span><span class="sxs-lookup"><span data-stu-id="3f902-205">ObjectName</span></span> 
