---
title: Connecteur MediaWiki Graph pour Microsoft Search (recherche Microsoft)
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
description: Configurer le connecteur MediaWiki Graph pour Microsoft Search (recherche Microsoft)
ms.openlocfilehash: 5922cf76aa112430f9f6e857066acd054182058c
ms.sourcegitcommit: 5df252e6d0bd67bb1b4c59418aceca8369f5fe42
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51031691"
---
<!---Previous ms.author: monaray --->

# <a name="mediawiki-graph-connector"></a><span data-ttu-id="3c898-103">Connecteur MediaWiki Graph</span><span class="sxs-lookup"><span data-stu-id="3c898-103">MediaWiki Graph connector</span></span>

<span data-ttu-id="3c898-104">Le connecteur MediaWiki Graph permet à votre organisation de découvrir et d’indexer des données à partir d’un wiki créé à l’aide du logiciel MediaWiki.</span><span class="sxs-lookup"><span data-stu-id="3c898-104">The MediaWiki Graph connector allows your organization to discover and index data from a wiki created by using MediaWiki software.</span></span> <span data-ttu-id="3c898-105">Ce connecteur indexe le contenu spécifié dans Microsoft Search (recherche Microsoft) et prend en charge les analyse périodiques pour maintenir l’index à jour.</span><span class="sxs-lookup"><span data-stu-id="3c898-105">This connector indexes specified content into Microsoft Search and supports periodic crawls to keep the index up to date.</span></span>

> [!NOTE]
> <span data-ttu-id="3c898-106">Lisez [**l’article Configuration de votre connecteur Graph**](configure-connector.md) pour comprendre les instructions générales d’installation des connecteurs Graph.</span><span class="sxs-lookup"><span data-stu-id="3c898-106">Read the [**Setup for your Graph connector**](configure-connector.md) article to understand the general Graph connectors setup instructions.</span></span>

<span data-ttu-id="3c898-107">Cet article est réservé à toute personne qui configure, exécute et surveille un connecteur MediaWiki Graph.</span><span class="sxs-lookup"><span data-stu-id="3c898-107">This article is for anyone who configures, runs, and monitors a MediaWiki Graph connector.</span></span> <span data-ttu-id="3c898-108">Il complète le processus de configuration général et affiche des instructions qui s’appliquent uniquement au connecteur MediaWiki Graph.</span><span class="sxs-lookup"><span data-stu-id="3c898-108">It supplements the general setup process, and shows instructions that apply only for the MediaWiki Graph connector.</span></span> <span data-ttu-id="3c898-109">Cet article inclut également des informations sur [les limitations.](#limitations)</span><span class="sxs-lookup"><span data-stu-id="3c898-109">This article also includes information about [Limitations](#limitations).</span></span>

<!---## Before you get started-->

<!---Insert "Before you get started" recommendations for this data source-->

## <a name="step-1-add-a-graph-connector-in-the-microsoft-365-admin-center"></a><span data-ttu-id="3c898-110">Étape 1 : Ajouter un connecteur Graph dans le Centre d’administration Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="3c898-110">Step 1: Add a Graph connector in the Microsoft 365 admin center</span></span>

<span data-ttu-id="3c898-111">Suivez les [instructions d’installation générales.](./configure-connector.md)</span><span class="sxs-lookup"><span data-stu-id="3c898-111">Follow the general [setup instructions](./configure-connector.md).</span></span>
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-2-name-the-connection"></a><span data-ttu-id="3c898-112">Étape 2 : Nommer la connexion</span><span class="sxs-lookup"><span data-stu-id="3c898-112">Step 2: Name the connection</span></span>

<span data-ttu-id="3c898-113">Suivez les [instructions d’installation générales.](./configure-connector.md)</span><span class="sxs-lookup"><span data-stu-id="3c898-113">Follow the general [setup instructions](./configure-connector.md).</span></span>
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-3-configure-the-connection-settings"></a><span data-ttu-id="3c898-114">Étape 3 : Configurer les paramètres de connexion</span><span class="sxs-lookup"><span data-stu-id="3c898-114">Step 3: Configure the connection settings</span></span>

<span data-ttu-id="3c898-115">Entrez votre **URL Wiki** et choisissez le **type d’authentification** dans le menu déroulant des options.</span><span class="sxs-lookup"><span data-stu-id="3c898-115">Enter your **Wiki URL** and choose the **Authentication type** from the drop-down menu of options.</span></span> <span data-ttu-id="3c898-116">Les options sont **None**, **Basic** et **OAuth 2.0 AAD**.</span><span class="sxs-lookup"><span data-stu-id="3c898-116">The options are **None**, **Basic**, and **OAuth 2.0 AAD**.</span></span>

<span data-ttu-id="3c898-117">Si vous choisissez **De base** comme type d’authentification, vous devez fournir le nom d’utilisateur et le mot de **passe** du wiki. </span><span class="sxs-lookup"><span data-stu-id="3c898-117">If you choose **Basic** as the Authentication type, you will need to provide the **Username** and **Password** for the wiki.</span></span>

<span data-ttu-id="3c898-118">Si vous choisissez **OAuth 2.0 AAD** comme type d’authentification, vous devez fournir l’ID de ressource de l’installation wiki. </span><span class="sxs-lookup"><span data-stu-id="3c898-118">If you choose **OAuth 2.0 AAD** as the Authentication type, you will need to provide the **Resource ID** of the wiki installation.</span></span> <span data-ttu-id="3c898-119">Vous devez également fournir **l’ID client** et la secret **client** générés sur la page d’inscription de l’application AAD.</span><span class="sxs-lookup"><span data-stu-id="3c898-119">You will also need to provide the **Client ID** and **Client secret** generated on the AAD Application registration page.</span></span>

## <a name="step-4-manage-search-permissions"></a><span data-ttu-id="3c898-120">Étape 4 : Gérer les autorisations de recherche</span><span class="sxs-lookup"><span data-stu-id="3c898-120">Step 4: Manage search permissions</span></span>

<span data-ttu-id="3c898-121">Le connecteur MediaWiki prend uniquement en charge les autorisations de recherche visibles par **Tout le monde.**</span><span class="sxs-lookup"><span data-stu-id="3c898-121">The MediaWiki connector only supports search permissions visible to **Everyone**.</span></span> <span data-ttu-id="3c898-122">Les données indexées apparaissent dans les résultats de la recherche et sont visibles par tous les utilisateurs de l’organisation.</span><span class="sxs-lookup"><span data-stu-id="3c898-122">Indexed data appears in the search results and is visible to all users in the organization.</span></span>

## <a name="step-5-assign-property-labels"></a><span data-ttu-id="3c898-123">Étape 5 : Attribuer des étiquettes de propriété</span><span class="sxs-lookup"><span data-stu-id="3c898-123">Step 5: Assign property labels</span></span>

<span data-ttu-id="3c898-124">Suivez les [instructions d’installation générales.](./configure-connector.md)</span><span class="sxs-lookup"><span data-stu-id="3c898-124">Follow the general [setup instructions](./configure-connector.md).</span></span>
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-6-manage-schema"></a><span data-ttu-id="3c898-125">Étape 6 : Gérer le schéma</span><span class="sxs-lookup"><span data-stu-id="3c898-125">Step 6: Manage schema</span></span>

<span data-ttu-id="3c898-126">Suivez les [instructions d’installation générales.](./configure-connector.md)</span><span class="sxs-lookup"><span data-stu-id="3c898-126">Follow the general [setup instructions](./configure-connector.md).</span></span>
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-7-choose-refresh-settings"></a><span data-ttu-id="3c898-127">Étape 7 : Choisir les paramètres d’actualisation</span><span class="sxs-lookup"><span data-stu-id="3c898-127">Step 7: Choose refresh settings</span></span>

<span data-ttu-id="3c898-128">Suivez les [instructions d’installation générales.](./configure-connector.md)</span><span class="sxs-lookup"><span data-stu-id="3c898-128">Follow the general [setup instructions](./configure-connector.md).</span></span>
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-8-review-connection"></a><span data-ttu-id="3c898-129">Étape 8 : Examiner la connexion</span><span class="sxs-lookup"><span data-stu-id="3c898-129">Step 8: Review connection</span></span>

<span data-ttu-id="3c898-130">Suivez les [instructions d’installation générales.](./configure-connector.md)</span><span class="sxs-lookup"><span data-stu-id="3c898-130">Follow the general [setup instructions](./configure-connector.md).</span></span>
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

<!---## Troubleshooting-->
<!---To be added-->

## <a name="limitations"></a><span data-ttu-id="3c898-131">Limites</span><span class="sxs-lookup"><span data-stu-id="3c898-131">Limitations</span></span>

<span data-ttu-id="3c898-132">Le connecteur MediaWiki présente les limitations ci-après dans la version préliminaire :</span><span class="sxs-lookup"><span data-stu-id="3c898-132">The MediaWiki connector has these limitations in the preview release:</span></span>

* <span data-ttu-id="3c898-133">Prend en charge uniquement les wikis basés sur le cloud.</span><span class="sxs-lookup"><span data-stu-id="3c898-133">Supports only cloud-based wikis.</span></span>
* <span data-ttu-id="3c898-134">Prend en charge uniquement Basic ou OAuth 2.0 avec l’authentification Azure Active Directory ou Azure.</span><span class="sxs-lookup"><span data-stu-id="3c898-134">Supports only Basic or OAuth 2.0 with Azure Active Directory or Azure authentication.</span></span>
* <span data-ttu-id="3c898-135">Ne prend pas en charge la sélection d’espace de noms pour l’indexation.</span><span class="sxs-lookup"><span data-stu-id="3c898-135">Doesn't support namespace selection for indexing.</span></span> <span data-ttu-id="3c898-136">Indexe uniquement les espaces de noms Principal, Catégorie et Fichier.</span><span class="sxs-lookup"><span data-stu-id="3c898-136">Indexes only Main, Category, and File namespaces.</span></span>
* <span data-ttu-id="3c898-137">Ne prend pas en charge les listes de contrôle d’accès.</span><span class="sxs-lookup"><span data-stu-id="3c898-137">Doesn't support Access Control Lists (ACLs).</span></span> <span data-ttu-id="3c898-138">Par conséquent, les pages indexées sont visibles par tous les utilisateurs de l’organisation.</span><span class="sxs-lookup"><span data-stu-id="3c898-138">Thus, indexed pages are visible to all users in the organization.</span></span>