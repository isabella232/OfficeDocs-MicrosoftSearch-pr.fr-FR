---
title: Connecteur de partage de fichiers
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
description: Configurer le connecteur de partage de fichiers pour Microsoft Search
ms.openlocfilehash: bf9fb730abd4ca6e42b681893525bbe3dd8a1419
ms.sourcegitcommit: 249f41723dd6fda1e93ee1a8f3f7571ef066454b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/05/2021
ms.locfileid: "49750896"
---
# <a name="file-share-connector"></a><span data-ttu-id="1d9f8-103">Connecteur de partage de fichiers</span><span class="sxs-lookup"><span data-stu-id="1d9f8-103">File share connector</span></span>

<span data-ttu-id="1d9f8-104">Avec le connecteur Graph du partage de fichiers, les utilisateurs de votre organisation peuvent effectuer des recherches dans des partages de fichiers Windows locaux.</span><span class="sxs-lookup"><span data-stu-id="1d9f8-104">With the File share Graph connector, users in your organization can search on-premise Windows file shares.</span></span>

<span data-ttu-id="1d9f8-105">Cet article est destiné aux administrateurs 365 de Microsoft ou toute personne qui configure, exécute et surveille un connecteur de partage de fichiers.</span><span class="sxs-lookup"><span data-stu-id="1d9f8-105">This article is for Microsoft 365 administrators or anyone who configures, runs, and monitors a file share connector.</span></span> <span data-ttu-id="1d9f8-106">Elle explique comment configurer les fonctionnalités de connecteur et de connecteur, ainsi que les restrictions et les techniques de résolution des problèmes.</span><span class="sxs-lookup"><span data-stu-id="1d9f8-106">It explains how to configure your connector and connector capabilities, limitations, and troubleshooting techniques.</span></span>

## <a name="install-graph-connector-agent"></a><span data-ttu-id="1d9f8-107">Installer l’agent Graph Connector</span><span class="sxs-lookup"><span data-stu-id="1d9f8-107">Install Graph connector agent</span></span>

<span data-ttu-id="1d9f8-108">Pour indexer vos partages de fichiers Windows, vous devez installer et inscrire [Graph Connector agent](on-prem-agent.md) .</span><span class="sxs-lookup"><span data-stu-id="1d9f8-108">In order to index your Windows file shares, you must install and register [Graph connector agent](on-prem-agent.md) software.</span></span>

## <a name="content-requirements"></a><span data-ttu-id="1d9f8-109">Exigences en matière de contenu</span><span class="sxs-lookup"><span data-stu-id="1d9f8-109">Content requirements</span></span>

### <a name="file-types"></a><span data-ttu-id="1d9f8-110">Types de fichiers</span><span class="sxs-lookup"><span data-stu-id="1d9f8-110">File types</span></span>

<span data-ttu-id="1d9f8-111">Le contenu des formats suivants peut être indexé et recherché : DOC, DOCM, DOCX, DOT, DOTX, EML, GIF, HTML, JPEG, MHT, MHTML, MSG, NWS, OBD, OBT, ODP, ODS, ODT, ONE, PDF, POT, PPS, PPT, PPTM, PPTX, TXT, XLB, XLC, XLSB, XLS, XLSX, XLT, XLXM, XML, XPS et ZIP.</span><span class="sxs-lookup"><span data-stu-id="1d9f8-111">Content of the following formats can be indexed and searched: DOC, DOCM, DOCX, DOT, DOTX, EML, GIF, HTML, JPEG, MHT, MHTML, MSG, NWS, OBD, OBT, ODP, ODS, ODT, ONE, PDF, POT, PPS, PPT, PPTM, PPTX, TXT, XLB, XLC, XLSB, XLS, XLSX, XLT, XLXM, XML, XPS, and ZIP.</span></span> <span data-ttu-id="1d9f8-112">Seul le contenu textuel de ces formats est indexé.</span><span class="sxs-lookup"><span data-stu-id="1d9f8-112">Only the textual content of these formats is indexed.</span></span> <span data-ttu-id="1d9f8-113">Tout le contenu multimédia est ignoré.</span><span class="sxs-lookup"><span data-stu-id="1d9f8-113">All multimedia content is ignored.</span></span> <span data-ttu-id="1d9f8-114">Pour tout fichier qui n’appartient pas à ce format, les métadonnées seules sont indexées.</span><span class="sxs-lookup"><span data-stu-id="1d9f8-114">For any file that does not belong to this format, the metadata alone is indexed.</span></span>

### <a name="file-size-limits"></a><span data-ttu-id="1d9f8-115">Limites de taille de fichier</span><span class="sxs-lookup"><span data-stu-id="1d9f8-115">File size limits</span></span>

<span data-ttu-id="1d9f8-116">La taille maximale de fichier prise en charge est de 100 Mo.</span><span class="sxs-lookup"><span data-stu-id="1d9f8-116">The maximum supported file size is 100 MB.</span></span> <span data-ttu-id="1d9f8-117">Les fichiers qui dépassent 100 Mo ne sont pas indexés.</span><span class="sxs-lookup"><span data-stu-id="1d9f8-117">Files that exceed 100 MB are not indexed.</span></span> <span data-ttu-id="1d9f8-118">La limite de taille post-traitée maximale est de 4 Mo.</span><span class="sxs-lookup"><span data-stu-id="1d9f8-118">The maximum post-processed size limit is 4 MB.</span></span> <span data-ttu-id="1d9f8-119">Le traitement s’arrête lorsque la taille d’un fichier atteint 4 Mo.</span><span class="sxs-lookup"><span data-stu-id="1d9f8-119">Processing stops when a file's size reaches 4 MB.</span></span> <span data-ttu-id="1d9f8-120">Par conséquent, il se peut que certaines expressions présentes dans le fichier ne fonctionnent pas pour la recherche.</span><span class="sxs-lookup"><span data-stu-id="1d9f8-120">Therefore, some phrases present in the file might not work for search.</span></span>

## <a name="connect-to-a-data-source"></a><span data-ttu-id="1d9f8-121">Se connecter à une source de données</span><span class="sxs-lookup"><span data-stu-id="1d9f8-121">Connect to a data source</span></span>

<span data-ttu-id="1d9f8-122">Sur la page **se connecter à la source de données** , sélectionnez **partage de fichiers** et indiquez le nom, l’ID de connexion et la description.</span><span class="sxs-lookup"><span data-stu-id="1d9f8-122">On the **Connect to data source** page, select **File share** and provide the name, connection ID, and description.</span></span> <span data-ttu-id="1d9f8-123">Sur la page suivante, indiquez le chemin d’accès au partage de fichiers et sélectionnez l’agent de connecteur Graph précédemment installé.</span><span class="sxs-lookup"><span data-stu-id="1d9f8-123">On the next page, provide the path to the file share and select your previously installed Graph connector agent.</span></span> <span data-ttu-id="1d9f8-124">Entrez les informations d’identification pour un compte d’utilisateur [Microsoft Windows](https://microsoft.com/windows) avec un accès en lecture à tous les fichiers du partage de fichiers.</span><span class="sxs-lookup"><span data-stu-id="1d9f8-124">Enter the credentials for a [Microsoft Windows](https://microsoft.com/windows) user account with read access to all the files in the file share.</span></span>

## <a name="preserve-last-access-time"></a><span data-ttu-id="1d9f8-125">Conserver l’heure du dernier accès</span><span class="sxs-lookup"><span data-stu-id="1d9f8-125">Preserve last access time</span></span>

<span data-ttu-id="1d9f8-126">Lorsque le connecteur tente d’analyser un fichier, le champ « heure du dernier accès » dans ses métadonnées est mis à jour.</span><span class="sxs-lookup"><span data-stu-id="1d9f8-126">When the connector attempts to crawl a file, the "last access time" field in its metadata is updated.</span></span> <span data-ttu-id="1d9f8-127">Si vous utilisez ce champ pour une solution d’archivage et de sauvegarde et que vous ne souhaitez pas le mettre à jour lorsque le connecteur y accède, vous pouvez configurer cette option dans la page **Paramètres avancés** .</span><span class="sxs-lookup"><span data-stu-id="1d9f8-127">If you depend on that field for any archiving and backup solutions and do not want to update it when the connector accesses it, you can configure this option in the **Advanced settings** page.</span></span>

## <a name="manage-search-permissions"></a><span data-ttu-id="1d9f8-128">Gérer les autorisations de recherche</span><span class="sxs-lookup"><span data-stu-id="1d9f8-128">Manage search permissions</span></span>

<span data-ttu-id="1d9f8-129">Vous pouvez limiter l’autorisation de recherche de n’importe quel fichier basé sur des listes de contrôle d’accès de partage ou des listes de contrôle d’accès NTFS (New Technology File System).</span><span class="sxs-lookup"><span data-stu-id="1d9f8-129">You can restrict the permission to search for any file based on Share Access Control Lists or New Technology File System (NTFS) Access Control Lists.</span></span> <span data-ttu-id="1d9f8-130">Si vous souhaitez utiliser les listes de contrôle d’accès de partage, sélectionnez l’option appropriée sur la page **Paramètres avancés** .</span><span class="sxs-lookup"><span data-stu-id="1d9f8-130">If you want to use Share Access Control Lists, select the appropriate option on the **Advanced settings** page.</span></span> <span data-ttu-id="1d9f8-131">Si vous souhaitez utiliser des listes de contrôle d’accès NTFS, sélectionnez l’option appropriée dans la page **gérer les autorisations de recherche** .</span><span class="sxs-lookup"><span data-stu-id="1d9f8-131">If you want to use NTFS Access Control Lists, select the appropriate option on the **Manage search permissions** page.</span></span>

## <a name="assign-property-labels"></a><span data-ttu-id="1d9f8-132">Affecter des étiquettes de propriété</span><span class="sxs-lookup"><span data-stu-id="1d9f8-132">Assign property labels</span></span>

<span data-ttu-id="1d9f8-133">Vous pouvez affecter une propriété source à chaque étiquette en choisissant dans un menu d’options.</span><span class="sxs-lookup"><span data-stu-id="1d9f8-133">You can assign a source property to each label by choosing from a menu of options.</span></span> <span data-ttu-id="1d9f8-134">Si cette étape n’est pas obligatoire, le fait d’avoir des étiquettes de propriété améliore la pertinence de la recherche et garantit des résultats de recherche plus précis pour les utilisateurs finaux.</span><span class="sxs-lookup"><span data-stu-id="1d9f8-134">While this step is not mandatory, having some property labels will improve the search relevance and ensure more accurate search results for end users.</span></span>

## <a name="manage-schema"></a><span data-ttu-id="1d9f8-135">Gérer le schéma</span><span class="sxs-lookup"><span data-stu-id="1d9f8-135">Manage schema</span></span>

<span data-ttu-id="1d9f8-136">Dans l' **écran gérer le schéma** , vous avez la possibilité de modifier les attributs de schéma (**Queryable**, pouvant faire l’objet d’une **recherche**, l' **extraction** et l' **refinable**) associés aux propriétés, d’ajouter des alias facultatifs et de choisir la propriété **content** .</span><span class="sxs-lookup"><span data-stu-id="1d9f8-136">On the **Manage Schema** screen, you have the option to change the schema attributes (**queryable**, **searchable**, **retrievable**, and **refinable**) associated with the properties, add optional aliases, and choose the **Content** property.</span></span>

## <a name="set-the-refresh-schedule"></a><span data-ttu-id="1d9f8-137">Définir la planification d’actualisation</span><span class="sxs-lookup"><span data-stu-id="1d9f8-137">Set the refresh schedule</span></span>

<span data-ttu-id="1d9f8-138">L’intervalle de planification des actualisations par défaut recommandé est de 15 minutes, mais vous pouvez le modifier en fonction de vos préférences.</span><span class="sxs-lookup"><span data-stu-id="1d9f8-138">The recommended default refresh schedule interval is 15 minutes, but you can change it based on your preferences.</span></span>

## <a name="result-layout"></a><span data-ttu-id="1d9f8-139">Disposition des résultats</span><span class="sxs-lookup"><span data-stu-id="1d9f8-139">Result layout</span></span>

<span data-ttu-id="1d9f8-140">Nous vous recommandons d’utiliser la disposition des résultats par défaut pour afficher les résultats de votre connecteur de FileShare car elle comporte des icônes et des contrôles appropriés pour vous aider à accéder au chemin d’accès du fichier.</span><span class="sxs-lookup"><span data-stu-id="1d9f8-140">We recommend that you use the default result layout to display your Fileshare connector results because it has appropriate icons and controls that help you navigate to the file path.</span></span> <span data-ttu-id="1d9f8-141">Si vous créez une nouvelle disposition de résultats, elle remplace la valeur par défaut.</span><span class="sxs-lookup"><span data-stu-id="1d9f8-141">If you create a new result layout, it will override the default.</span></span>
