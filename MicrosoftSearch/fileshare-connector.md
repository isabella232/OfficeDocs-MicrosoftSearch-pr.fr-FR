---
title: Connecteur Graph de partage de fichiers pour Microsoft Search (recherche Microsoft)
ms.author: mecampos
author: mecampos
manager: umas
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
ROBOTS: NoIndex
description: Configurer le connecteur Graph de partage de fichiers pour Microsoft Search (recherche Microsoft)
ms.openlocfilehash: e8a68a1c6b9c2c8a8592fb915fe9bf846a758e77
ms.sourcegitcommit: d53b91f8f52a4a96281b66831c2449bbffe2177c
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/03/2021
ms.locfileid: "50097420"
---
<!---Previous ms.author: rusamai --->

# <a name="file-share-graph-connector"></a><span data-ttu-id="8f160-103">Connecteur Graph de partage de fichiers</span><span class="sxs-lookup"><span data-stu-id="8f160-103">File share Graph connector</span></span>

<span data-ttu-id="8f160-104">Le connecteur Graph de partage de fichiers permet aux utilisateurs de votre organisation de rechercher des partages de fichiers Windows locaux.</span><span class="sxs-lookup"><span data-stu-id="8f160-104">The File share Graph connector allows users in your organization to search on-premise Windows file shares.</span></span>

> [!NOTE]
> <span data-ttu-id="8f160-105">Lisez [**l’article Installation de votre connecteur Graph**](configure-connector.md) pour comprendre le processus d’installation général des connecteurs Graph.</span><span class="sxs-lookup"><span data-stu-id="8f160-105">Read the [**Setup for your Graph connector**](configure-connector.md) article to understand the general Graph connectors setup process.</span></span>

## <a name="before-you-get-started"></a><span data-ttu-id="8f160-106">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="8f160-106">Before you get started</span></span>

### <a name="install-the-graph-connector-agent"></a><span data-ttu-id="8f160-107">Installer l’agent de connecteur Graph</span><span class="sxs-lookup"><span data-stu-id="8f160-107">Install the Graph connector agent</span></span>

<span data-ttu-id="8f160-108">Pour indexer vos partages de fichiers Windows, vous devez installer et inscrire l’agent de connecteur Graph.</span><span class="sxs-lookup"><span data-stu-id="8f160-108">To index your Windows file shares, you must install and register the Graph connector agent.</span></span> <span data-ttu-id="8f160-109">Pour plus [d’informations, voir Installer l’agent de](on-prem-agent.md) connecteur Graph.</span><span class="sxs-lookup"><span data-stu-id="8f160-109">See [Install the Graph connector agent](on-prem-agent.md) to learn more.</span></span>  

### <a name="content-requirements"></a><span data-ttu-id="8f160-110">Exigences en matière de contenu</span><span class="sxs-lookup"><span data-stu-id="8f160-110">Content requirements</span></span>

### <a name="file-types"></a><span data-ttu-id="8f160-111">Types de fichiers</span><span class="sxs-lookup"><span data-stu-id="8f160-111">File types</span></span>

<span data-ttu-id="8f160-112">Le contenu des formats suivants peut être indexé et recherché : DOC, DOCM, DOCX, DOTX, EML, GIF, HTML, JPEG, MHT, MHTML, MSG, NWS, OBD, OBT, ODP, ODS, ODT, ONE, PDF, POT, PPS, PPT, PPTM, PPTX, TXT, XLB, XLC, XLSB, XLSX, XLSX, XLT, XLXM, XML, XPS et ZIP.</span><span class="sxs-lookup"><span data-stu-id="8f160-112">Content of the following formats can be indexed and searched: DOC, DOCM, DOCX, DOT, DOTX, EML, GIF, HTML, JPEG, MHT, MHTML, MSG, NWS, OBD, OBT, ODP, ODS, ODT, ONE, PDF, POT, PPS, PPT, PPTM, PPTX, TXT, XLB, XLC, XLSB, XLS, XLSX, XLT, XLXM, XML, XPS, and ZIP.</span></span> <span data-ttu-id="8f160-113">Seul le contenu textuel de ces formats est indexé.</span><span class="sxs-lookup"><span data-stu-id="8f160-113">Only the textual content of these formats is indexed.</span></span> <span data-ttu-id="8f160-114">Tout le contenu multimédia est ignoré.</span><span class="sxs-lookup"><span data-stu-id="8f160-114">All multimedia content is ignored.</span></span> <span data-ttu-id="8f160-115">Pour tout fichier qui n’appartient pas à ce format, les métadonnées seules sont indexées.</span><span class="sxs-lookup"><span data-stu-id="8f160-115">For any file that doesn't belong to this format, the metadata alone is indexed.</span></span>

### <a name="file-size-limits"></a><span data-ttu-id="8f160-116">Limites de taille de fichier</span><span class="sxs-lookup"><span data-stu-id="8f160-116">File size limits</span></span>

<span data-ttu-id="8f160-117">La taille maximale de fichier prise en charge est de 100 Mo.</span><span class="sxs-lookup"><span data-stu-id="8f160-117">The maximum supported file size is 100 MB.</span></span> <span data-ttu-id="8f160-118">Les fichiers dont la valeur est supérieure à 100 Mo ne sont pas indexés.</span><span class="sxs-lookup"><span data-stu-id="8f160-118">Files that exceed 100 MB aren't indexed.</span></span> <span data-ttu-id="8f160-119">La taille limite post-traitée maximale est de 4 Mo.</span><span class="sxs-lookup"><span data-stu-id="8f160-119">The maximum post-processed size limit is 4 MB.</span></span> <span data-ttu-id="8f160-120">Le traitement s’arrête lorsque la taille d’un fichier atteint 4 Mo.</span><span class="sxs-lookup"><span data-stu-id="8f160-120">Processing stops when a file's size reaches 4 MB.</span></span> <span data-ttu-id="8f160-121">Par conséquent, certaines expressions présentes dans le fichier peuvent ne pas fonctionner pour la recherche.</span><span class="sxs-lookup"><span data-stu-id="8f160-121">Therefore, some phrases present in the file might not work for search.</span></span>

## <a name="step-1-add-a-graph-connector-in-the-microsoft-365-admin-center"></a><span data-ttu-id="8f160-122">Étape 1 : Ajouter un connecteur Graph dans le Centre d’administration Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="8f160-122">Step 1: Add a Graph connector in the Microsoft 365 admin center</span></span>

<span data-ttu-id="8f160-123">Suivez les [instructions d’installation générales.](https://docs.microsoft.com/microsoftsearch/configure-connector)</span><span class="sxs-lookup"><span data-stu-id="8f160-123">Follow the general [setup instructions](https://docs.microsoft.com/microsoftsearch/configure-connector).</span></span>
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-2-name-the-connection"></a><span data-ttu-id="8f160-124">Étape 2 : Nommer la connexion</span><span class="sxs-lookup"><span data-stu-id="8f160-124">Step 2: Name the connection</span></span>

<span data-ttu-id="8f160-125">Suivez les [instructions d’installation générales.](https://docs.microsoft.com/microsoftsearch/configure-connector)</span><span class="sxs-lookup"><span data-stu-id="8f160-125">Follow the general [setup instructions](https://docs.microsoft.com/microsoftsearch/configure-connector).</span></span>
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-3-configure-the-connection-settings"></a><span data-ttu-id="8f160-126">Étape 3 : Configurer les paramètres de connexion</span><span class="sxs-lookup"><span data-stu-id="8f160-126">Step 3: Configure the connection settings</span></span>

<span data-ttu-id="8f160-127">Dans la page **Se connecter à la source de données,** sélectionnez **Partage** de fichiers et indiquez le nom, l’ID de connexion et la description.</span><span class="sxs-lookup"><span data-stu-id="8f160-127">On the **Connect to data source** page, select **File share** and provide the name, connection ID, and description.</span></span> <span data-ttu-id="8f160-128">Sur la page suivante, indiquez le chemin d’accès au partage de fichiers et sélectionnez votre agent de connecteur Graph précédemment installé.</span><span class="sxs-lookup"><span data-stu-id="8f160-128">On the next page, provide the path to the file share and select your previously installed Graph connector agent.</span></span> <span data-ttu-id="8f160-129">Entrez les informations d’identification d’un [compte d’utilisateur Microsoft Windows](https://microsoft.com/windows) avec un accès en lecture à tous les fichiers du partage de fichiers.</span><span class="sxs-lookup"><span data-stu-id="8f160-129">Enter the credentials for a [Microsoft Windows](https://microsoft.com/windows) user account with read access to all the files in the file share.</span></span>

### <a name="preserve-last-access-time"></a><span data-ttu-id="8f160-130">Conserver l’heure du dernier accès</span><span class="sxs-lookup"><span data-stu-id="8f160-130">Preserve last access time</span></span>

<span data-ttu-id="8f160-131">Lorsque le connecteur tente d’analyser un fichier, le champ « Heure du dernier accès » dans ses métadonnées est mis à jour.</span><span class="sxs-lookup"><span data-stu-id="8f160-131">When the connector attempts to crawl a file, the "last access time" field in its metadata is updated.</span></span> <span data-ttu-id="8f160-132">Si vous dépendez de ce champ pour les solutions d’archivage et de sauvegarde et que vous ne souhaitez pas le mettre à jour lorsque le connecteur y accède, vous pouvez configurer cette option dans la page **Paramètres** avancés.</span><span class="sxs-lookup"><span data-stu-id="8f160-132">If you depend on that field for any archiving and backup solutions and doesn't want to update it when the connector accesses it, you can configure this option in the **Advanced settings** page.</span></span>

## <a name="step-4-manage-search-permissions"></a><span data-ttu-id="8f160-133">Étape 4 : Gérer les autorisations de recherche</span><span class="sxs-lookup"><span data-stu-id="8f160-133">Step 4: Manage search permissions</span></span>

<span data-ttu-id="8f160-134">Vous pouvez restreindre l’autorisation de rechercher n’importe quel fichier en fonction des listes de contrôle d’accès de partage ou des listes de contrôle d’accès NTFS (New Technology File System).</span><span class="sxs-lookup"><span data-stu-id="8f160-134">You can restrict the permission to search for any file based on Share Access Control Lists or New Technology File System (NTFS) Access Control Lists.</span></span> <span data-ttu-id="8f160-135">Si vous souhaitez utiliser les listes de contrôle d’accès de partage, sélectionnez l’option appropriée dans la page **Paramètres avancés.**</span><span class="sxs-lookup"><span data-stu-id="8f160-135">If you want to use Share Access Control Lists, select the appropriate option on the **Advanced settings** page.</span></span> <span data-ttu-id="8f160-136">Si vous souhaitez utiliser des listes de contrôle d’accès NTFS, sélectionnez l’option appropriée dans la page Gérer les **autorisations de recherche.**</span><span class="sxs-lookup"><span data-stu-id="8f160-136">If you want to use NTFS Access Control Lists, select the appropriate option on the **Manage search permissions** page.</span></span>

## <a name="step-5-assign-property-labels"></a><span data-ttu-id="8f160-137">Étape 5 : Attribuer des étiquettes de propriété</span><span class="sxs-lookup"><span data-stu-id="8f160-137">Step 5: Assign property labels</span></span>

<span data-ttu-id="8f160-138">Suivez les [instructions d’installation générales.](https://docs.microsoft.com/microsoftsearch/configure-connector)</span><span class="sxs-lookup"><span data-stu-id="8f160-138">Follow the general [setup instructions](https://docs.microsoft.com/microsoftsearch/configure-connector).</span></span>
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-6-manage-schema"></a><span data-ttu-id="8f160-139">Étape 6 : Gérer le schéma</span><span class="sxs-lookup"><span data-stu-id="8f160-139">Step 6: Manage schema</span></span>

<span data-ttu-id="8f160-140">Suivez les [instructions d’installation générales.](https://docs.microsoft.com/microsoftsearch/configure-connector)</span><span class="sxs-lookup"><span data-stu-id="8f160-140">Follow the general [setup instructions](https://docs.microsoft.com/microsoftsearch/configure-connector).</span></span>
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-7-choose-refresh-settings"></a><span data-ttu-id="8f160-141">Étape 7 : Choisir les paramètres d’actualisation</span><span class="sxs-lookup"><span data-stu-id="8f160-141">Step 7: Choose refresh settings</span></span>

<span data-ttu-id="8f160-142">Suivez les [instructions d’installation générales.](https://docs.microsoft.com/microsoftsearch/configure-connector)</span><span class="sxs-lookup"><span data-stu-id="8f160-142">Follow the general [setup instructions](https://docs.microsoft.com/microsoftsearch/configure-connector).</span></span>
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-8-review-connection"></a><span data-ttu-id="8f160-143">Étape 8 : Examiner la connexion</span><span class="sxs-lookup"><span data-stu-id="8f160-143">Step 8: Review connection</span></span>

<span data-ttu-id="8f160-144">Suivez les [instructions d’installation générales.](https://docs.microsoft.com/microsoftsearch/configure-connector)</span><span class="sxs-lookup"><span data-stu-id="8f160-144">Follow the general [setup instructions](https://docs.microsoft.com/microsoftsearch/configure-connector).</span></span>
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup 
instructions.-->

<!---## Troubleshooting-->
<!---Insert troubleshooting recommendations for this data source-->

<!---## Limitations-->
<!---Insert limitations for this data source-->
