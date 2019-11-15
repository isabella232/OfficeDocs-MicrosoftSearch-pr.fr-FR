---
title: Connecteur MediaWiki pour Microsoft Search
ms.author: v-pamcn
author: monaray
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
ms.openlocfilehash: 2aa0ef494aa42b1a7364ec68f6532dec737b9c25
ms.sourcegitcommit: 21361af7c244ffd6ff8689fd0ff0daa359bf4129
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/14/2019
ms.locfileid: "38626962"
---
# <a name="mediawiki-connector"></a><span data-ttu-id="88095-103">Connecteur MediaWiki</span><span class="sxs-lookup"><span data-stu-id="88095-103">MediaWiki connector</span></span>

<span data-ttu-id="88095-104">Avec le connecteur MediaWiki, votre organisation peut découvrir et indexer des données à partir d’un wiki créé à l’aide du logiciel MediaWiki.</span><span class="sxs-lookup"><span data-stu-id="88095-104">With the MediaWiki connector, your organization can discover and index data from a wiki created by using MediaWiki software.</span></span> <span data-ttu-id="88095-105">Ce connecteur indexe le contenu spécifié dans Microsoft Search et prend en charge les analyses périodiques pour maintenir l’index à jour.</span><span class="sxs-lookup"><span data-stu-id="88095-105">This connector indexes specified content into Microsoft Search and supports periodic crawls to keep the index up to date.</span></span>

<span data-ttu-id="88095-106">Cet article est destiné aux administrateurs 365 de Microsoft ou toute personne qui configure, exécute et surveille un connecteur MediaWiki.</span><span class="sxs-lookup"><span data-stu-id="88095-106">This article is for Microsoft 365 administrators or anyone who configures, runs, and monitors a MediaWiki connector.</span></span> <span data-ttu-id="88095-107">Elle explique comment configurer les fonctionnalités de connecteur et de connecteur, ainsi que les restrictions et les techniques de résolution des problèmes.</span><span class="sxs-lookup"><span data-stu-id="88095-107">It explains how to configure your connector and connector capabilities, limitations, and troubleshooting techniques.</span></span>

## <a name="connect-to-a-data-source"></a><span data-ttu-id="88095-108">Se connecter à une source de données</span><span class="sxs-lookup"><span data-stu-id="88095-108">Connect to a data source</span></span>
<span data-ttu-id="88095-109">Entrez l’URL et les informations d’identification de votre MediaWiki pour authentifier la connexion.</span><span class="sxs-lookup"><span data-stu-id="88095-109">Enter your MediaWiki URL and credentials for authenticating the connection.</span></span> <span data-ttu-id="88095-110">Vous aurez besoin des informations suivantes : **ID**de client, **ID de ressource**, **ID client**et **clé secrète client**.</span><span class="sxs-lookup"><span data-stu-id="88095-110">You'll need the following information: **Tenant ID**, **Resource ID**, **Client ID**, and the **Client Secret**.</span></span>

## <a name="manage-the-search-schema"></a><span data-ttu-id="88095-111">Gérer le schéma de recherche</span><span class="sxs-lookup"><span data-stu-id="88095-111">Manage the search schema</span></span>
<span data-ttu-id="88095-112">Une fois la connexion établie, configurez le mappage du schéma de recherche.</span><span class="sxs-lookup"><span data-stu-id="88095-112">After successful connection, configure the search schema mapping.</span></span> <span data-ttu-id="88095-113">Vous pouvez choisir les propriétés à utiliser pour les **requêtes**, les **recherches**et les **extractions**.</span><span class="sxs-lookup"><span data-stu-id="88095-113">You can choose which properties to make **queryable**, **searchable**, and **retrievable**.</span></span>

## <a name="manage-search-permissions"></a><span data-ttu-id="88095-114">Gérer les autorisations de recherche</span><span class="sxs-lookup"><span data-stu-id="88095-114">Manage search permissions</span></span>
<span data-ttu-id="88095-115">Le connecteur MediaWiki prend uniquement en charge les autorisations de recherche visibles par **tous les utilisateurs**.</span><span class="sxs-lookup"><span data-stu-id="88095-115">The MediaWiki connector only supports search permissions visible to **Everyone**.</span></span> <span data-ttu-id="88095-116">Les données indexées apparaissent dans les résultats de la recherche et sont visibles par tous les utilisateurs de l’organisation.</span><span class="sxs-lookup"><span data-stu-id="88095-116">Indexed data appears in the search results and is visible to all users in the organization.</span></span>

## <a name="set-the-refresh-schedule"></a><span data-ttu-id="88095-117">Définir la planification d’actualisation</span><span class="sxs-lookup"><span data-stu-id="88095-117">Set the refresh schedule</span></span> 
<span data-ttu-id="88095-118">Cette planification actualise les données indexées, de sorte que les modifications apportées au wiki sont reflétées dans Microsoft Search.</span><span class="sxs-lookup"><span data-stu-id="88095-118">This schedule refreshes indexed data, so changes to the wiki are reflected in Microsoft Search.</span></span> <span data-ttu-id="88095-119">Toutes les nouvelles pages, pages supprimées, contenu de page ou modifications de métadonnées apparaissent dans les résultats de la recherche après l’intervalle d’actualisation spécifié.</span><span class="sxs-lookup"><span data-stu-id="88095-119">All new pages, deleted pages, page content, or metadata changes appear in search results after the specified refresh interval.</span></span> <span data-ttu-id="88095-120">La durée de l’analyse dépend de la taille du wiki.</span><span class="sxs-lookup"><span data-stu-id="88095-120">The crawl time is dependent on the size of the wiki.</span></span> <span data-ttu-id="88095-121">Actuellement, le connecteur analyse environ 50 pages par minute.</span><span class="sxs-lookup"><span data-stu-id="88095-121">Currently the connector crawls at around 50 pages per minute.</span></span>

## <a name="limitations"></a><span data-ttu-id="88095-122">Limites</span><span class="sxs-lookup"><span data-stu-id="88095-122">Limitations</span></span> 
<span data-ttu-id="88095-123">Le connecteur MediaWiki présente ces limitations dans la version d’évaluation :</span><span class="sxs-lookup"><span data-stu-id="88095-123">The MediaWiki connector has these limitations in the preview release:</span></span>
* <span data-ttu-id="88095-124">Prend en charge uniquement les wikis sur le Cloud.</span><span class="sxs-lookup"><span data-stu-id="88095-124">Supports only cloud-based wikis.</span></span>
* <span data-ttu-id="88095-125">Prend en charge uniquement les 2,0 de base ou OAuth avec Azure Active Directory ou l’authentification Azure.</span><span class="sxs-lookup"><span data-stu-id="88095-125">Supports only Basic or OAuth 2.0 with Azure Active Directory or Azure authentication.</span></span>
* <span data-ttu-id="88095-126">Ne prend pas en charge la sélection d’espace de noms pour l’indexation.</span><span class="sxs-lookup"><span data-stu-id="88095-126">Doesn't support namespace selection for indexing.</span></span> <span data-ttu-id="88095-127">Indexe uniquement les espaces de noms **principal**, de **catégorie**et de **fichier** .</span><span class="sxs-lookup"><span data-stu-id="88095-127">Indexes only **Main**, **Category**, and **File** namespaces.</span></span>
* <span data-ttu-id="88095-128">Ne prend pas en charge les listes de contrôle d’accès (ACL).</span><span class="sxs-lookup"><span data-stu-id="88095-128">Doesn't support Access Control Lists (ACLs).</span></span> <span data-ttu-id="88095-129">Ainsi, les pages indexées sont visibles par tous les utilisateurs de l’organisation.</span><span class="sxs-lookup"><span data-stu-id="88095-129">Thus, indexed pages are visible to all users in the organization.</span></span>
