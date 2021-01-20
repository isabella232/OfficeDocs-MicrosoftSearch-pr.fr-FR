---
title: Connecteur MediaWiki pour Microsoft Search (recherche Microsoft)
ms.author: monaray
author: monaray97
manager: mnirkhe
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: Configurer le connecteur MediaWiki pour Microsoft Search (recherche Microsoft)
ms.openlocfilehash: 7a22fcc84f6f435bf438aa027c42c76eb8be1eaf
ms.sourcegitcommit: 39bf9f0db7f9bff2ab82c99a059b0ddcf1c98f5f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/19/2021
ms.locfileid: "49905950"
---
# <a name="mediawiki-connector"></a><span data-ttu-id="63ca2-103">Connecteur MediaWiki</span><span class="sxs-lookup"><span data-stu-id="63ca2-103">MediaWiki connector</span></span>

<span data-ttu-id="63ca2-104">Avec le connecteur MediaWiki, votre organisation peut découvrir et indexer des données à partir d’un wiki créé à l’aide du logiciel MediaWiki.</span><span class="sxs-lookup"><span data-stu-id="63ca2-104">With the MediaWiki connector, your organization can discover and index data from a wiki created by using MediaWiki software.</span></span> <span data-ttu-id="63ca2-105">Ce connecteur indexe le contenu spécifié dans Microsoft Search (recherche Microsoft) et prend en charge les analyse périodiques pour maintenir l’index à jour.</span><span class="sxs-lookup"><span data-stu-id="63ca2-105">This connector indexes specified content into Microsoft Search and supports periodic crawls to keep the index up to date.</span></span>

<span data-ttu-id="63ca2-106">Cet article est réservé aux administrateurs Microsoft 365 ou à toute personne qui configure, exécute et surveille un connecteur MediaWiki Graph.</span><span class="sxs-lookup"><span data-stu-id="63ca2-106">This article is for Microsoft 365 administrators or anyone who configures, runs, and monitors a MediaWiki Graph connector.</span></span> <span data-ttu-id="63ca2-107">Il complète les instructions générales fournies dans l’article [Configurer votre connecteur Graph.](configure-connector.md)</span><span class="sxs-lookup"><span data-stu-id="63ca2-107">It supplements the general instructions provided in the [Set up your Graph connector](configure-connector.md) article.</span></span> <span data-ttu-id="63ca2-108">Si vous ne l’avez pas déjà fait, lisez l’intégralité de l’article Configurer votre connecteur Graph pour comprendre le processus d’installation général.</span><span class="sxs-lookup"><span data-stu-id="63ca2-108">If you have not already done so, read the entire Set up your Graph connector article to understand the general setup process.</span></span>

<span data-ttu-id="63ca2-109">Chaque étape du processus d’installation est répertoriée ci-dessous avec une note qui indique que vous devez suivre les instructions d’installation générales ou d’autres instructions qui s’appliquent uniquement aux connecteurs MediaWiki Graph.</span><span class="sxs-lookup"><span data-stu-id="63ca2-109">Each step in the setup process is listed below along with either a note that indicates you should follow the general setup instructions OR other instructions that apply to only MediaWiki Graph connectors.</span></span> <span data-ttu-id="63ca2-110">Cet article inclut également des informations [sur les limitations](#limitations) des connecteurs MediaWiki Graph.</span><span class="sxs-lookup"><span data-stu-id="63ca2-110">This article also includes information about [Limitations](#limitations) for MediaWiki Graph connectors.</span></span> 

## <a name="step-1-add-a-graph-connector-in-the-microsoft-365-admin-center"></a><span data-ttu-id="63ca2-111">Étape 1 : Ajoutez un connecteur Graph dans le Centre d’administration Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="63ca2-111">Step 1: Add a Graph connector in the Microsoft 365 admin center.</span></span>
<span data-ttu-id="63ca2-112">Suivez les instructions d’installation générales.</span><span class="sxs-lookup"><span data-stu-id="63ca2-112">Follow the general setup instructions.</span></span>

## <a name="step-2-name-the-connection"></a><span data-ttu-id="63ca2-113">Étape 2 : Nommez la connexion.</span><span class="sxs-lookup"><span data-stu-id="63ca2-113">Step 2: Name the connection.</span></span>
<span data-ttu-id="63ca2-114">Suivez les instructions d’installation générales.</span><span class="sxs-lookup"><span data-stu-id="63ca2-114">Follow the general setup instructions.</span></span>
 
## <a name="step-3-configure-the-connection-settings"></a><span data-ttu-id="63ca2-115">Étape 3 : Configurer les paramètres de connexion.</span><span class="sxs-lookup"><span data-stu-id="63ca2-115">Step 3: Configure the connection settings.</span></span>
<span data-ttu-id="63ca2-116">Entrez votre **URL Wiki** et choisissez le **type d’authentification** dans le menu déroulant des options.</span><span class="sxs-lookup"><span data-stu-id="63ca2-116">Enter your **Wiki URL** and choose the **Authentication type** from the drop-down menu of options.</span></span> <span data-ttu-id="63ca2-117">Les options sont **None**, **Basic** et **OAuth 2.0 AAD**.</span><span class="sxs-lookup"><span data-stu-id="63ca2-117">The options are **None**, **Basic**, and **OAuth 2.0 AAD**.</span></span>

<span data-ttu-id="63ca2-118">Si vous choisissez **De base** comme type d’authentification, vous devez fournir le nom d’utilisateur et le mot de **passe** du wiki. </span><span class="sxs-lookup"><span data-stu-id="63ca2-118">If you choose **Basic** as the Authentication type, you will need to provide the **Username** and **Password** for the wiki.</span></span>

<span data-ttu-id="63ca2-119">Si vous choisissez **OAuth 2.0 AAD** comme type d’authentification, vous devez fournir l’ID de ressource de l’installation wiki. </span><span class="sxs-lookup"><span data-stu-id="63ca2-119">If you choose **OAuth 2.0 AAD** as the Authentication type, you will need to provide the **Resource ID** of the wiki installation.</span></span> <span data-ttu-id="63ca2-120">Vous devez également fournir **l’ID client** et la secret **client** générés sur la page d’inscription de l’application AAD.</span><span class="sxs-lookup"><span data-stu-id="63ca2-120">You will also need to provide the **Client ID** and **Client secret** generated on the AAD Application registration page.</span></span> 

## <a name="step-4-manage-search-permissions"></a><span data-ttu-id="63ca2-121">Étape 4 : Gérer les autorisations de recherche</span><span class="sxs-lookup"><span data-stu-id="63ca2-121">Step 4: Manage search permissions</span></span>
<span data-ttu-id="63ca2-122">Le connecteur MediaWiki prend uniquement en charge les autorisations de recherche visibles par **Tout le monde.**</span><span class="sxs-lookup"><span data-stu-id="63ca2-122">The MediaWiki connector only supports search permissions visible to **Everyone**.</span></span> <span data-ttu-id="63ca2-123">Les données indexées apparaissent dans les résultats de la recherche et sont visibles par tous les utilisateurs de l’organisation.</span><span class="sxs-lookup"><span data-stu-id="63ca2-123">Indexed data appears in the search results and is visible to all users in the organization.</span></span>

## <a name="step-5-assign-property-labels"></a><span data-ttu-id="63ca2-124">Étape 5 : Attribuer des étiquettes de propriété</span><span class="sxs-lookup"><span data-stu-id="63ca2-124">Step 5: Assign property labels</span></span>
<span data-ttu-id="63ca2-125">Suivez les instructions d’installation générales.</span><span class="sxs-lookup"><span data-stu-id="63ca2-125">Follow the general setup instructions.</span></span>

## <a name="step-6-manage-schema"></a><span data-ttu-id="63ca2-126">Étape 6 : Gérer le schéma</span><span class="sxs-lookup"><span data-stu-id="63ca2-126">Step 6: Manage schema</span></span>
<span data-ttu-id="63ca2-127">Suivez les instructions d’installation générales.</span><span class="sxs-lookup"><span data-stu-id="63ca2-127">Follow the general setup instructions.</span></span>

## <a name="step-7-choose-refresh-settings"></a><span data-ttu-id="63ca2-128">Étape 7 : Choisir les paramètres d’actualisation</span><span class="sxs-lookup"><span data-stu-id="63ca2-128">Step 7: Choose refresh settings</span></span>
<span data-ttu-id="63ca2-129">Suivez les instructions d’installation générales.</span><span class="sxs-lookup"><span data-stu-id="63ca2-129">Follow the general setup instructions.</span></span>

## <a name="step-8-review-connection"></a><span data-ttu-id="63ca2-130">Étape 8 : Examiner la connexion</span><span class="sxs-lookup"><span data-stu-id="63ca2-130">Step 8: Review connection</span></span>
<span data-ttu-id="63ca2-131">Suivez les instructions d’installation générales.</span><span class="sxs-lookup"><span data-stu-id="63ca2-131">Follow the general setup instructions.</span></span>

<!---## Troubleshooting-->
<!---To be added-->

## <a name="limitations"></a><span data-ttu-id="63ca2-132">Limites</span><span class="sxs-lookup"><span data-stu-id="63ca2-132">Limitations</span></span>
<span data-ttu-id="63ca2-133">Le connecteur MediaWiki présente les limitations ci-après dans la version préliminaire :</span><span class="sxs-lookup"><span data-stu-id="63ca2-133">The MediaWiki connector has these limitations in the preview release:</span></span>

* <span data-ttu-id="63ca2-134">Prend en charge uniquement les wikis basés sur le cloud.</span><span class="sxs-lookup"><span data-stu-id="63ca2-134">Supports only cloud-based wikis.</span></span>
* <span data-ttu-id="63ca2-135">Prend en charge uniquement Basic ou OAuth 2.0 avec l’authentification Azure Active Directory ou Azure.</span><span class="sxs-lookup"><span data-stu-id="63ca2-135">Supports only Basic or OAuth 2.0 with Azure Active Directory or Azure authentication.</span></span>
* <span data-ttu-id="63ca2-136">Ne prend pas en charge la sélection d’espace de noms pour l’indexation.</span><span class="sxs-lookup"><span data-stu-id="63ca2-136">Doesn't support namespace selection for indexing.</span></span> <span data-ttu-id="63ca2-137">Indexe uniquement les espaces de noms Principal, Catégorie et Fichier.</span><span class="sxs-lookup"><span data-stu-id="63ca2-137">Indexes only Main, Category, and File namespaces.</span></span>
* <span data-ttu-id="63ca2-138">Ne prend pas en charge les listes de contrôle d’accès.</span><span class="sxs-lookup"><span data-stu-id="63ca2-138">Doesn't support Access Control Lists (ACLs).</span></span> <span data-ttu-id="63ca2-139">Par conséquent, les pages indexées sont visibles par tous les utilisateurs de l’organisation.</span><span class="sxs-lookup"><span data-stu-id="63ca2-139">Thus, indexed pages are visible to all users in the organization.</span></span>
