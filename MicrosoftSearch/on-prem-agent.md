---
title: Sur l’agent local
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
ROBOTS: NoIndex
description: Agent local
ms.openlocfilehash: 487c5b179e09fd99fa26ae7a237e89ca38b7be4d
ms.sourcegitcommit: 69a1c544cc8db364991cb58d7818d7158ff108b8
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/25/2020
ms.locfileid: "49408941"
---
# <a name="on-prem-agent"></a><span data-ttu-id="684d8-103">Agent local</span><span class="sxs-lookup"><span data-stu-id="684d8-103">On-Prem Agent</span></span>

## <a name="graph-connector-agent"></a><span data-ttu-id="684d8-104">Agent de connecteur Graph</span><span class="sxs-lookup"><span data-stu-id="684d8-104">Graph connector agent</span></span>

<span data-ttu-id="684d8-105">Les connecteurs Graph local requièrent l’installation du logiciel de *l’agent Graph Connector* .</span><span class="sxs-lookup"><span data-stu-id="684d8-105">On-prem Graph connectors require you to install *Graph connector agent* software.</span></span> <span data-ttu-id="684d8-106">Elle permet de transférer rapidement et en toute sécurité des données entre des services de données et de Cloud Computing.</span><span class="sxs-lookup"><span data-stu-id="684d8-106">It allows quick and secure data transfer between on-premises data and cloud services.</span></span> <span data-ttu-id="684d8-107">Cet article vous guide tout au long des étapes d’installation et de configuration du logiciel.</span><span class="sxs-lookup"><span data-stu-id="684d8-107">This article guides you through the steps of installing and configuring the software.</span></span> <span data-ttu-id="684d8-108">Une fois configuré, il sera disponible pour la création de connexions à vos sources de données local à partir du [Centre d’administration Microsoft 365](https://admin.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="684d8-108">Once configured, it will be available for creating connections to your on-prem data sources from the [Microsoft 365 admin center](https://admin.microsoft.com).</span></span>

## <a name="installation"></a><span data-ttu-id="684d8-109">Installation</span><span class="sxs-lookup"><span data-stu-id="684d8-109">Installation</span></span>

<span data-ttu-id="684d8-110">Téléchargez la dernière version de l’agent connecteur Graph à l’aide de [ce lien](https://download.microsoft.com/download/d/d/e/dde18236-9c67-437d-a864-894a0a888ef2/AgentPackage.msi) et installez le logiciel à l’aide de l’Assistant d’installation.</span><span class="sxs-lookup"><span data-stu-id="684d8-110">Download the latest version of Graph connector agent using [this link](https://download.microsoft.com/download/d/d/e/dde18236-9c67-437d-a864-894a0a888ef2/AgentPackage.msi) and install the software using the installation wizard.</span></span> <span data-ttu-id="684d8-111">Avec la configuration recommandée de l’ordinateur décrit ci-dessous, le logiciel peut gérer de manière transparente jusqu’à trois connexions.</span><span class="sxs-lookup"><span data-stu-id="684d8-111">With the recommended configuration of the machine described below, the software can seamlessly handle up to three connections.</span></span> <span data-ttu-id="684d8-112">Toutes les connexions au-delà de cela risquent de dégrader les performances.</span><span class="sxs-lookup"><span data-stu-id="684d8-112">Any connections beyond that might degrade the performance.</span></span>

<span data-ttu-id="684d8-113">Configuration recommandée :</span><span class="sxs-lookup"><span data-stu-id="684d8-113">Recommended configuration:</span></span>

* <span data-ttu-id="684d8-114">Windows 10, Windows Server 2012 R2 et versions ultérieures</span><span class="sxs-lookup"><span data-stu-id="684d8-114">Windows 10, Windows Server 2012 R2 and above</span></span>
* <span data-ttu-id="684d8-115">8 cœurs, 3 GHz</span><span class="sxs-lookup"><span data-stu-id="684d8-115">8 cores, 3GHz</span></span>
* <span data-ttu-id="684d8-116">16 Go de RAM, 1 Go d’espace disque</span><span class="sxs-lookup"><span data-stu-id="684d8-116">16GB RAM, 1GB Disk Space</span></span>
* <span data-ttu-id="684d8-117">Accès réseau à la source de données et à Internet via 443</span><span class="sxs-lookup"><span data-stu-id="684d8-117">Network access to data source and internet through 443</span></span>

## <a name="creating-app-for-the-agent"></a><span data-ttu-id="684d8-118">Création de l’application pour l’agent</span><span class="sxs-lookup"><span data-stu-id="684d8-118">Creating App for the agent</span></span>  

<span data-ttu-id="684d8-119">L’instance de l’agent doit comporter peu de paramètres critiques avant de créer des connexions.</span><span class="sxs-lookup"><span data-stu-id="684d8-119">The agent instance needs to be fed few critical parameters before you create connections.</span></span> <span data-ttu-id="684d8-120">Ces paramètres incluent des détails d’authentification requis pour l’utilisation des API de réception Graph.</span><span class="sxs-lookup"><span data-stu-id="684d8-120">These parameters include authentication details required for using Graph ingestion APIs.</span></span>  

<span data-ttu-id="684d8-121">Étapes de création de l’application pour l’agent.</span><span class="sxs-lookup"><span data-stu-id="684d8-121">Steps for creating App for the agent.</span></span>

1. <span data-ttu-id="684d8-122">Accédez au [portail Azure](https://portal.azure.com) et connectez-vous avec les informations d’identification d’administrateur pour le client.</span><span class="sxs-lookup"><span data-stu-id="684d8-122">Go to the [Azure portal](https://portal.azure.com) and sign in with admin credentials for the tenant.</span></span>
2. <span data-ttu-id="684d8-123">Accédez à **Azure Active Directory**  ->  ,**inscriptions des applications** dans le volet de navigation, puis sélectionnez **nouvelle inscription**.</span><span class="sxs-lookup"><span data-stu-id="684d8-123">Navigate to **Azure Active Directory** -> **App registrations** from the navigation pane and select **New registration**.</span></span>
3. <span data-ttu-id="684d8-124">Fournissez un nom pour l’application, puis sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="684d8-124">Provide a name for the app and select **Register**.</span></span>
4. <span data-ttu-id="684d8-125">Notez l’ID de l’application (client).</span><span class="sxs-lookup"><span data-stu-id="684d8-125">Make a note of the Application (client) ID.</span></span>
5. <span data-ttu-id="684d8-126">Ouvrez les autorisations de l' **API** à partir du volet de navigation et sélectionnez **Ajouter une autorisation**.</span><span class="sxs-lookup"><span data-stu-id="684d8-126">Open **API permissions** from the navigation pane and select **Add a permission**.</span></span>
6. <span data-ttu-id="684d8-127">Sélectionnez **Microsoft Graph** , puis **autorisations d’application**.</span><span class="sxs-lookup"><span data-stu-id="684d8-127">Select **Microsoft Graph** and then **Application permissions**.</span></span>
7. <span data-ttu-id="684d8-128">Recherchez « ExternalItem. ReadWrite. All » et « Directory. Read. All » à partir des autorisations, puis sélectionnez **Ajouter des autorisations**.</span><span class="sxs-lookup"><span data-stu-id="684d8-128">Search for "ExternalItem.ReadWrite.All" and "Directory.Read.All" from the permissions and select **Add permissions**.</span></span>
8. <span data-ttu-id="684d8-129">Sélectionnez **accorder le consentement de l’administrateur pour [TenantName]** et confirmez-le en sélectionnant **Oui**.</span><span class="sxs-lookup"><span data-stu-id="684d8-129">Select **Grant admin consent for [TenantName]** and confirm by selecting **Yes**.</span></span>
9. <span data-ttu-id="684d8-130">Vérifiez que les autorisations sont dans l’État accordé.</span><span class="sxs-lookup"><span data-stu-id="684d8-130">Check that the permissions are in the granted state.</span></span>
     <span data-ttu-id="684d8-131">![Autorisations indiquées comme étant accordées dans la colonne de droite vert sur la droite.](media/onprem-agent/granted-state.png)</span><span class="sxs-lookup"><span data-stu-id="684d8-131">![Permissions shown as granted in green on right hand column.](media/onprem-agent/granted-state.png)</span></span>

## <a name="configuring-graph-connector-agent"></a><span data-ttu-id="684d8-132">Configuration de l’agent de connecteur Graph</span><span class="sxs-lookup"><span data-stu-id="684d8-132">Configuring Graph connector agent</span></span>

<span data-ttu-id="684d8-133">Une fois que vous avez créé l’application pour l’agent, vous devez configurer l’agent avec les détails d’authentification appropriés.</span><span class="sxs-lookup"><span data-stu-id="684d8-133">Once you have created the App for the agent, you must configure the agent with appropriate authentication details.</span></span>

<span data-ttu-id="684d8-134">Les détails de l’authentification peuvent être fournis dans l’un des formulaires suivants.</span><span class="sxs-lookup"><span data-stu-id="684d8-134">Authentication details can be provided in one of the following forms.</span></span>

### <a name="configuring-the-client-secret-for-authentication"></a><span data-ttu-id="684d8-135">Configuration de la clé secrète client pour l’authentification</span><span class="sxs-lookup"><span data-stu-id="684d8-135">Configuring the client secret for authentication</span></span>

1. <span data-ttu-id="684d8-136">Accédez au [portail Azure](https://portal.azure.com) et connectez-vous avec les informations d’identification d’administrateur pour le client.</span><span class="sxs-lookup"><span data-stu-id="684d8-136">Go to the [Azure portal](https://portal.azure.com) and sign in with admin credentials for the tenant.</span></span>
2. <span data-ttu-id="684d8-137">Ouvrez **inscription** de l’application dans le volet de navigation et accédez à l’application appropriée.</span><span class="sxs-lookup"><span data-stu-id="684d8-137">Open **App Registration** from the navigation pane and go to the appropriate App.</span></span> <span data-ttu-id="684d8-138">Sous **gérer**, sélectionnez **certificats et secrets**.</span><span class="sxs-lookup"><span data-stu-id="684d8-138">Under **Manage**, select **Certificates and secrets**.</span></span>
3. <span data-ttu-id="684d8-139">Sélectionnez **nouvelle clé secrète client** et sélectionnez une période d’expiration pour la clé secrète.</span><span class="sxs-lookup"><span data-stu-id="684d8-139">Select **New Client secret** and select an expiry period for the secret.</span></span> <span data-ttu-id="684d8-140">Copiez la clé secrète générée et enregistrez-la, car elle ne s’affichera plus.</span><span class="sxs-lookup"><span data-stu-id="684d8-140">Copy the generated secret and save it because it will not be shown again.</span></span>
4. <span data-ttu-id="684d8-141">Utilisez cette clé secrète client avec l’ID de l’application pour configurer l’agent.</span><span class="sxs-lookup"><span data-stu-id="684d8-141">Use this Client secret along with the Application ID to configure the agent.</span></span> <span data-ttu-id="684d8-142">N’utilisez pas d’espaces dans le champ **nom** de l’agent.</span><span class="sxs-lookup"><span data-stu-id="684d8-142">Do not use any blank spaces in the **Name** field of the agent.</span></span> <span data-ttu-id="684d8-143">Les caractères numériques alphanumériques sont acceptés.</span><span class="sxs-lookup"><span data-stu-id="684d8-143">Alpha numeric characters are accepted.</span></span>

## <a name="using-thumbprint-certificate-for-authentication"></a><span data-ttu-id="684d8-144">Utilisation d’un certificat d’empreinte numérique pour l’authentification</span><span class="sxs-lookup"><span data-stu-id="684d8-144">Using thumbprint certificate for authentication</span></span>

<span data-ttu-id="684d8-145">Si vous avez déjà configuré les détails d’authentification en suivant [la configuration de la clé secrète client pour l’authentification](#configuring-the-client-secret-for-authentication) , vous pouvez passer directement à la [rubrique Configuration Overview](configure-connector.md).</span><span class="sxs-lookup"><span data-stu-id="684d8-145">If you have already configured the authentication details by following [Configuring the client secret for authentication](#configuring-the-client-secret-for-authentication) , then you can jump directly to [Setup overview](configure-connector.md).</span></span>

1. <span data-ttu-id="684d8-146">Ouvrez **inscription** de l’application et sélectionnez **certificats et secrets** dans le volet de navigation.</span><span class="sxs-lookup"><span data-stu-id="684d8-146">Open **App registration** and select **Certificates and secrets** from the navigation pane.</span></span> <span data-ttu-id="684d8-147">Copiez l’empreinte de certificat.</span><span class="sxs-lookup"><span data-stu-id="684d8-147">Copy the certificate thumbprint.</span></span>
<span data-ttu-id="684d8-148">![Liste des certificats thumbrint lorsque l’option certificats et secrets est sélectionnée dans le volet de gauche](media/onprem-agent/certificates.png)</span><span class="sxs-lookup"><span data-stu-id="684d8-148">![List of thumbrint certificates when Certificates and secrets is selected in the left pane](media/onprem-agent/certificates.png)</span></span>
2. <span data-ttu-id="684d8-149">Utilisez la clé secrète client ou l’empreinte numérique pour enregistrer l’agent connecteur Graph.</span><span class="sxs-lookup"><span data-stu-id="684d8-149">Use either the client secret or thumbprint to register the Graph connector agent.</span></span>
<span data-ttu-id="684d8-150">![Formulaire d’inscription demandant le nom, l’ID de l’application, le type d’informations d’identification et le certificat](media/onprem-agent/register.png)</span><span class="sxs-lookup"><span data-stu-id="684d8-150">![Register form asking for name, app id, credential type, and certificate](media/onprem-agent/register.png)</span></span>
