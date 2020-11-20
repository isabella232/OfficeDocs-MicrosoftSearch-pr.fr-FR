---
title: Connecteur MediaWiki pour Microsoft Search
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
description: Configurer le connecteur MediaWiki pour Microsoft Search
ms.openlocfilehash: 7f6b34dcafc4b82ab3778ec1d7a4921383e44a44
ms.sourcegitcommit: 59cdd3f0f82b7918399bf44d27d9891076090f4f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/20/2020
ms.locfileid: "49367639"
---
# <a name="mediawiki-connector"></a><span data-ttu-id="056be-103">Connecteur MediaWiki</span><span class="sxs-lookup"><span data-stu-id="056be-103">MediaWiki connector</span></span>

<span data-ttu-id="056be-104">Avec le connecteur MediaWiki, votre organisation peut découvrir et indexer des données à partir d’un wiki créé à l’aide du logiciel MediaWiki.</span><span class="sxs-lookup"><span data-stu-id="056be-104">With the MediaWiki connector, your organization can discover and index data from a wiki created by using MediaWiki software.</span></span> <span data-ttu-id="056be-105">Ce connecteur indexe le contenu spécifié dans Microsoft Search et prend en charge les analyses périodiques pour maintenir l’index à jour.</span><span class="sxs-lookup"><span data-stu-id="056be-105">This connector indexes specified content into Microsoft Search and supports periodic crawls to keep the index up to date.</span></span>

<span data-ttu-id="056be-106">Cet article est destiné aux administrateurs 365 de Microsoft ou toute personne qui configure, exécute et surveille un connecteur MediaWiki.</span><span class="sxs-lookup"><span data-stu-id="056be-106">This article is for Microsoft 365 administrators or anyone who configures, runs, and monitors a MediaWiki connector.</span></span> <span data-ttu-id="056be-107">Elle explique comment configurer les fonctionnalités de connecteur et de connecteur, ainsi que les restrictions et les techniques de résolution des problèmes.</span><span class="sxs-lookup"><span data-stu-id="056be-107">It explains how to configure your connector and connector capabilities, limitations, and troubleshooting techniques.</span></span>

## <a name="connect-to-a-data-source"></a><span data-ttu-id="056be-108">Se connecter à une source de données</span><span class="sxs-lookup"><span data-stu-id="056be-108">Connect to a data source</span></span>

<span data-ttu-id="056be-109">Entrez l’URL et les informations d’identification de votre MediaWiki pour authentifier la connexion.</span><span class="sxs-lookup"><span data-stu-id="056be-109">Enter your MediaWiki URL and credentials for authenticating the connection.</span></span> <span data-ttu-id="056be-110">Vous aurez besoin des informations suivantes : **ID** de client, **ID de ressource**, **ID client** et **clé secrète client**.</span><span class="sxs-lookup"><span data-stu-id="056be-110">You'll need the following information: **Tenant ID**, **Resource ID**, **Client ID**, and the **Client Secret**.</span></span>

## <a name="manage-search-permissions"></a><span data-ttu-id="056be-111">Gérer les autorisations de recherche</span><span class="sxs-lookup"><span data-stu-id="056be-111">Manage search permissions</span></span>

<span data-ttu-id="056be-112">Le connecteur MediaWiki prend uniquement en charge les autorisations de recherche visibles par **tous les utilisateurs**.</span><span class="sxs-lookup"><span data-stu-id="056be-112">The MediaWiki connector only supports search permissions visible to **Everyone**.</span></span> <span data-ttu-id="056be-113">Les données indexées apparaissent dans les résultats de la recherche et sont visibles par tous les utilisateurs de l’organisation.</span><span class="sxs-lookup"><span data-stu-id="056be-113">Indexed data appears in the search results and is visible to all users in the organization.</span></span>

## <a name="assign-property-labels"></a><span data-ttu-id="056be-114">Affecter des étiquettes de propriété</span><span class="sxs-lookup"><span data-stu-id="056be-114">Assign property labels</span></span>

<span data-ttu-id="056be-115">Vous pouvez affecter une propriété source à chaque étiquette en choisissant dans un menu d’options.</span><span class="sxs-lookup"><span data-stu-id="056be-115">You can assign a source property to each label by choosing from a menu of options.</span></span> <span data-ttu-id="056be-116">Si cette étape n’est pas obligatoire, le fait d’avoir des étiquettes de propriété améliore la pertinence de la recherche et garantit des résultats de recherche plus précis pour les utilisateurs finaux.</span><span class="sxs-lookup"><span data-stu-id="056be-116">While this step is not mandatory, having some property labels will improve the search relevance and ensure more accurate search results for end users.</span></span>

## <a name="manage-schema"></a><span data-ttu-id="056be-117">Gérer le schéma</span><span class="sxs-lookup"><span data-stu-id="056be-117">Manage schema</span></span>

<span data-ttu-id="056be-118">Dans l' **écran gérer le schéma** , vous avez la possibilité de modifier les attributs de schéma (**Queryable**, pouvant faire l’objet d’une **recherche**, l' **extraction** et l' **refinable**) associés aux propriétés, d’ajouter des alias facultatifs et de choisir la propriété **content** .</span><span class="sxs-lookup"><span data-stu-id="056be-118">On the **Manage Schema** screen, you have the option to change the schema attributes (**queryable**, **searchable**, **retrievable**, and **refinable**) associated with the properties, add optional aliases, and choose the **Content** property.</span></span>

## <a name="set-the-refresh-schedule"></a><span data-ttu-id="056be-119">Définir la planification d’actualisation</span><span class="sxs-lookup"><span data-stu-id="056be-119">Set the refresh schedule</span></span>

<span data-ttu-id="056be-120">Cette planification actualise les données indexées, de sorte que les modifications apportées au wiki sont reflétées dans Microsoft Search.</span><span class="sxs-lookup"><span data-stu-id="056be-120">This schedule refreshes indexed data, so changes to the wiki are reflected in Microsoft Search.</span></span> <span data-ttu-id="056be-121">Toutes les nouvelles pages, pages supprimées, contenu de page ou modifications de métadonnées apparaissent dans les résultats de la recherche après l’intervalle d’actualisation spécifié.</span><span class="sxs-lookup"><span data-stu-id="056be-121">All new pages, deleted pages, page content, or metadata changes appear in search results after the specified refresh interval.</span></span> <span data-ttu-id="056be-122">La durée de l’analyse dépend de la taille du wiki.</span><span class="sxs-lookup"><span data-stu-id="056be-122">The crawl time is dependent on the size of the wiki.</span></span> <span data-ttu-id="056be-123">Actuellement, le connecteur analyse environ 50 pages par minute.</span><span class="sxs-lookup"><span data-stu-id="056be-123">Currently the connector crawls at around 50 pages per minute.</span></span>

## <a name="limitations"></a><span data-ttu-id="056be-124">Limites</span><span class="sxs-lookup"><span data-stu-id="056be-124">Limitations</span></span>

<span data-ttu-id="056be-125">Le connecteur MediaWiki présente ces limitations dans la version d’évaluation :</span><span class="sxs-lookup"><span data-stu-id="056be-125">The MediaWiki connector has these limitations in the preview release:</span></span>

* <span data-ttu-id="056be-126">Prend en charge uniquement les wikis sur le Cloud.</span><span class="sxs-lookup"><span data-stu-id="056be-126">Supports only cloud-based wikis.</span></span>
* <span data-ttu-id="056be-127">Prend en charge uniquement les 2,0 de base ou OAuth avec Azure Active Directory ou l’authentification Azure.</span><span class="sxs-lookup"><span data-stu-id="056be-127">Supports only Basic or OAuth 2.0 with Azure Active Directory or Azure authentication.</span></span>
* <span data-ttu-id="056be-128">Ne prend pas en charge la sélection d’espace de noms pour l’indexation.</span><span class="sxs-lookup"><span data-stu-id="056be-128">Doesn't support namespace selection for indexing.</span></span> <span data-ttu-id="056be-129">Indexe uniquement les espaces de noms **principal**, de **catégorie** et de **fichier** .</span><span class="sxs-lookup"><span data-stu-id="056be-129">Indexes only **Main**, **Category**, and **File** namespaces.</span></span>
* <span data-ttu-id="056be-130">Ne prend pas en charge les listes de contrôle d’accès (ACL).</span><span class="sxs-lookup"><span data-stu-id="056be-130">Doesn't support Access Control Lists (ACLs).</span></span> <span data-ttu-id="056be-131">Ainsi, les pages indexées sont visibles par tous les utilisateurs de l’organisation.</span><span class="sxs-lookup"><span data-stu-id="056be-131">Thus, indexed pages are visible to all users in the organization.</span></span>
