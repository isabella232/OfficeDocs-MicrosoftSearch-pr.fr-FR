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
ms.openlocfilehash: ed1c148a018ba9492a8a93685327bf43153d65d3
ms.sourcegitcommit: 6a7522d9aeaedeedaac096c485d3f343ce98d3d2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/04/2021
ms.locfileid: "50421074"
---
<!---Previous ms.author: rusamai --->

# <a name="file-share-graph-connector"></a><span data-ttu-id="1e071-103">Connecteur Graph de partage de fichiers</span><span class="sxs-lookup"><span data-stu-id="1e071-103">File share Graph connector</span></span>

<span data-ttu-id="1e071-104">Le connecteur Graph de partage de fichiers permet aux utilisateurs de votre organisation de rechercher des partages de fichiers Windows locaux.</span><span class="sxs-lookup"><span data-stu-id="1e071-104">The File share Graph connector allows users in your organization to search on-premise Windows file shares.</span></span>

> [!NOTE]
> <span data-ttu-id="1e071-105">Lisez [**l’article Installation de votre connecteur Graph**](configure-connector.md) pour comprendre le processus d’installation général des connecteurs Graph.</span><span class="sxs-lookup"><span data-stu-id="1e071-105">Read the [**Setup for your Graph connector**](configure-connector.md) article to understand the general Graph connectors setup process.</span></span>

## <a name="before-you-get-started"></a><span data-ttu-id="1e071-106">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="1e071-106">Before you get started</span></span>

### <a name="install-the-graph-connector-agent"></a><span data-ttu-id="1e071-107">Installer l’agent de connecteur Graph</span><span class="sxs-lookup"><span data-stu-id="1e071-107">Install the Graph connector agent</span></span>

<span data-ttu-id="1e071-108">Pour indexer vos partages de fichiers Windows, vous devez installer et inscrire l’agent de connecteur Graph.</span><span class="sxs-lookup"><span data-stu-id="1e071-108">To index your Windows file shares, you must install and register the Graph connector agent.</span></span> <span data-ttu-id="1e071-109">Pour plus [d’informations, voir Installer l’agent de](on-prem-agent.md) connecteur Graph.</span><span class="sxs-lookup"><span data-stu-id="1e071-109">See [Install the Graph connector agent](on-prem-agent.md) to learn more.</span></span>  

### <a name="content-requirements"></a><span data-ttu-id="1e071-110">Exigences en matière de contenu</span><span class="sxs-lookup"><span data-stu-id="1e071-110">Content requirements</span></span>

### <a name="file-types"></a><span data-ttu-id="1e071-111">Types de fichiers</span><span class="sxs-lookup"><span data-stu-id="1e071-111">File types</span></span>

<span data-ttu-id="1e071-112">Le contenu des formats suivants peut être indexé et recherché : DOC, DOCM, DOCX, DOTX, EML, GIF, HTML, JPEG, MHT, MHTML, MSG, NWS, OBD, OBT, ODP, ODS, ODT, ONE, PDF, POT, PPS, PPT, PPTM, PPTX, TXT, XLB, XLC, XLSB, XLSX, XLSX, XLT, XLXM, XML, XPS et ZIP.</span><span class="sxs-lookup"><span data-stu-id="1e071-112">Content of the following formats can be indexed and searched: DOC, DOCM, DOCX, DOT, DOTX, EML, GIF, HTML, JPEG, MHT, MHTML, MSG, NWS, OBD, OBT, ODP, ODS, ODT, ONE, PDF, POT, PPS, PPT, PPTM, PPTX, TXT, XLB, XLC, XLSB, XLS, XLSX, XLT, XLXM, XML, XPS, and ZIP.</span></span> <span data-ttu-id="1e071-113">Seul le contenu textuel de ces formats est indexé.</span><span class="sxs-lookup"><span data-stu-id="1e071-113">Only the textual content of these formats is indexed.</span></span> <span data-ttu-id="1e071-114">Tout le contenu multimédia est ignoré.</span><span class="sxs-lookup"><span data-stu-id="1e071-114">All multimedia content is ignored.</span></span> <span data-ttu-id="1e071-115">Pour tout fichier qui n’appartient pas à ce format, les métadonnées seules sont indexées.</span><span class="sxs-lookup"><span data-stu-id="1e071-115">For any file that doesn't belong to this format, the metadata alone is indexed.</span></span>

### <a name="file-size-limits"></a><span data-ttu-id="1e071-116">Limites de taille de fichier</span><span class="sxs-lookup"><span data-stu-id="1e071-116">File size limits</span></span>

<span data-ttu-id="1e071-117">La taille maximale de fichier prise en charge est de 100 Mo.</span><span class="sxs-lookup"><span data-stu-id="1e071-117">The maximum supported file size is 100 MB.</span></span> <span data-ttu-id="1e071-118">Les fichiers dont la valeur est supérieure à 100 Mo ne sont pas indexés.</span><span class="sxs-lookup"><span data-stu-id="1e071-118">Files that exceed 100 MB aren't indexed.</span></span> <span data-ttu-id="1e071-119">La taille limite post-traitée maximale est de 4 Mo.</span><span class="sxs-lookup"><span data-stu-id="1e071-119">The maximum post-processed size limit is 4 MB.</span></span> <span data-ttu-id="1e071-120">Le traitement s’arrête lorsque la taille d’un fichier atteint 4 Mo.</span><span class="sxs-lookup"><span data-stu-id="1e071-120">Processing stops when a file's size reaches 4 MB.</span></span> <span data-ttu-id="1e071-121">Par conséquent, certaines expressions présentes dans le fichier peuvent ne pas fonctionner pour la recherche.</span><span class="sxs-lookup"><span data-stu-id="1e071-121">Therefore, some phrases present in the file might not work for search.</span></span>

## <a name="step-1-add-a-graph-connector-in-the-microsoft-365-admin-center"></a><span data-ttu-id="1e071-122">Étape 1 : Ajouter un connecteur Graph dans le Centre d’administration Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="1e071-122">Step 1: Add a Graph connector in the Microsoft 365 admin center</span></span>

<span data-ttu-id="1e071-123">Suivez les [instructions d’installation générales.](https://docs.microsoft.com/microsoftsearch/configure-connector)</span><span class="sxs-lookup"><span data-stu-id="1e071-123">Follow the general [setup instructions](https://docs.microsoft.com/microsoftsearch/configure-connector).</span></span>
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-2-name-the-connection"></a><span data-ttu-id="1e071-124">Étape 2 : Nommer la connexion</span><span class="sxs-lookup"><span data-stu-id="1e071-124">Step 2: Name the connection</span></span>

<span data-ttu-id="1e071-125">Suivez les [instructions d’installation générales.](https://docs.microsoft.com/microsoftsearch/configure-connector)</span><span class="sxs-lookup"><span data-stu-id="1e071-125">Follow the general [setup instructions](https://docs.microsoft.com/microsoftsearch/configure-connector).</span></span>
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-3-configure-the-connection-settings"></a><span data-ttu-id="1e071-126">Étape 3 : Configurer les paramètres de connexion</span><span class="sxs-lookup"><span data-stu-id="1e071-126">Step 3: Configure the connection settings</span></span>

<span data-ttu-id="1e071-127">Dans la page **Se connecter à la source de données,** sélectionnez **Partage** de fichiers et indiquez le nom, l’ID de connexion et la description.</span><span class="sxs-lookup"><span data-stu-id="1e071-127">On the **Connect to data source** page, select **File share** and provide the name, connection ID, and description.</span></span> <span data-ttu-id="1e071-128">Sur la page suivante, indiquez le chemin d’accès au partage de fichiers et sélectionnez votre agent de connecteur Graph précédemment installé.</span><span class="sxs-lookup"><span data-stu-id="1e071-128">On the next page, provide the path to the file share and select your previously installed Graph connector agent.</span></span> <span data-ttu-id="1e071-129">Entrez les informations d’identification d’un [compte d’utilisateur Microsoft Windows](https://microsoft.com/windows) avec un accès en lecture à tous les fichiers du partage de fichiers.</span><span class="sxs-lookup"><span data-stu-id="1e071-129">Enter the credentials for a [Microsoft Windows](https://microsoft.com/windows) user account with read access to all the files in the file share.</span></span>

### <a name="preserve-last-access-time"></a><span data-ttu-id="1e071-130">Conserver l’heure du dernier accès</span><span class="sxs-lookup"><span data-stu-id="1e071-130">Preserve last access time</span></span>

<span data-ttu-id="1e071-131">Lorsque le connecteur tente d’analyser un fichier, le champ « Heure du dernier accès » dans ses métadonnées est mis à jour.</span><span class="sxs-lookup"><span data-stu-id="1e071-131">When the connector attempts to crawl a file, the "last access time" field in its metadata is updated.</span></span> <span data-ttu-id="1e071-132">Si vous dépendez de ce champ pour les solutions d’archivage et de sauvegarde et que vous ne souhaitez pas le mettre à jour lorsque le connecteur y accède, vous pouvez configurer cette option dans la page **Paramètres** avancés.</span><span class="sxs-lookup"><span data-stu-id="1e071-132">If you depend on that field for any archiving and backup solutions and doesn't want to update it when the connector accesses it, you can configure this option in the **Advanced settings** page.</span></span>

## <a name="step-4-manage-search-permissions"></a><span data-ttu-id="1e071-133">Étape 4 : Gérer les autorisations de recherche</span><span class="sxs-lookup"><span data-stu-id="1e071-133">Step 4: Manage search permissions</span></span>

<span data-ttu-id="1e071-134">Vous pouvez restreindre l’autorisation de rechercher n’importe quel fichier basé sur les listes de contrôle d’accès de partage ou les listes de contrôle d’accès NTFS (New Technology File System), en sélectionnant l’option souhaitée dans la page Gérer les **autorisations** de recherche.</span><span class="sxs-lookup"><span data-stu-id="1e071-134">You can restrict the permission to search for any file based on Share Access Control Lists or New Technology File System (NTFS) Access Control Lists, by selecting the desired option in **Manage search permissions** page.</span></span> <span data-ttu-id="1e071-135">Les comptes et groupes d’utilisateurs fournis dans ces listes de contrôle d’accès doivent être gérés par Active Directory (AD).</span><span class="sxs-lookup"><span data-stu-id="1e071-135">The user accounts and groups provided in these Access Control Lists must be managed by Active Directory (AD).</span></span> <span data-ttu-id="1e071-136">Si vous utilisez un autre système pour la gestion des comptes d’utilisateurs, vous pouvez sélectionner l’option « tout le monde » qui permet aux utilisateurs de rechercher tous les fichiers sans restrictions d’accès.</span><span class="sxs-lookup"><span data-stu-id="1e071-136">If you are using any other system for user accounts management, you can select 'everyone' option, which lets users search for all the files without any access restrictions.</span></span> <span data-ttu-id="1e071-137">Toutefois, lorsque les utilisateurs tentent d’ouvrir le fichier, les contrôles d’accès définies au niveau de la source s’appliquent.</span><span class="sxs-lookup"><span data-stu-id="1e071-137">However, when users try to open the file, access controls set at the source apply.</span></span>

<span data-ttu-id="1e071-138">Notez que windows fournit par défaut l’autorisation « Lecture » à « Tout le monde » dans les AAL de partage lorsqu’un dossier est partagé sur le réseau.</span><span class="sxs-lookup"><span data-stu-id="1e071-138">Note that windows by default provides 'Read' permission to 'Everyone' in Share ACLs when a folder is shared on network.</span></span> <span data-ttu-id="1e071-139">Par extension, si vous choisissez partager des ACA dans Gérer les autorisations de recherche, les **utilisateurs** pourront rechercher tous les fichiers.</span><span class="sxs-lookup"><span data-stu-id="1e071-139">By extension, if you are choosing Share ACLs in **Manage search permissions**, users will be able to search for all the files.</span></span> <span data-ttu-id="1e071-140">Si vous souhaitez restreindre l’accès, supprimez l’accès « Lecture » pour « Tout le monde » dans les partages de fichiers et fournissez l’accès uniquement aux utilisateurs et groupes souhaités.</span><span class="sxs-lookup"><span data-stu-id="1e071-140">If you want to restrict access, remove 'Read' access for 'Everyone' in file shares and provide access only to the desired users and groups.</span></span> <span data-ttu-id="1e071-141">Le connecteur lit ensuite ces restrictions d’accès et les applique à la recherche.</span><span class="sxs-lookup"><span data-stu-id="1e071-141">The connector then reads these access restrictions and applies them to search.</span></span>

<span data-ttu-id="1e071-142">Vous pouvez choisir les AAL de partage uniquement si le chemin d’accès de partage que vous avez fourni suit le format de chemin d’accès UNC.</span><span class="sxs-lookup"><span data-stu-id="1e071-142">You can choose Share ACLs only if the share path you provided follows UNC path format.</span></span> <span data-ttu-id="1e071-143">Vous pouvez créer un chemin d’accès au format UNC en allant à « Partage avancé » sous l’option « Partage ».</span><span class="sxs-lookup"><span data-stu-id="1e071-143">You can create a path in UNC format by going to 'Advanced Sharing' under 'Sharing' option.</span></span>

![Advanced_sharing](media/file-connector/file-advanced-sharing.png)

## <a name="step-5-assign-property-labels"></a><span data-ttu-id="1e071-145">Étape 5 : Attribuer des étiquettes de propriété</span><span class="sxs-lookup"><span data-stu-id="1e071-145">Step 5: Assign property labels</span></span>

<span data-ttu-id="1e071-146">Suivez les [instructions d’installation générales.](https://docs.microsoft.com/microsoftsearch/configure-connector)</span><span class="sxs-lookup"><span data-stu-id="1e071-146">Follow the general [setup instructions](https://docs.microsoft.com/microsoftsearch/configure-connector).</span></span>
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-6-manage-schema"></a><span data-ttu-id="1e071-147">Étape 6 : Gérer le schéma</span><span class="sxs-lookup"><span data-stu-id="1e071-147">Step 6: Manage schema</span></span>

<span data-ttu-id="1e071-148">Suivez les [instructions d’installation générales.](https://docs.microsoft.com/microsoftsearch/configure-connector)</span><span class="sxs-lookup"><span data-stu-id="1e071-148">Follow the general [setup instructions](https://docs.microsoft.com/microsoftsearch/configure-connector).</span></span>
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-7-choose-refresh-settings"></a><span data-ttu-id="1e071-149">Étape 7 : Choisir les paramètres d’actualisation</span><span class="sxs-lookup"><span data-stu-id="1e071-149">Step 7: Choose refresh settings</span></span>

<span data-ttu-id="1e071-150">Suivez les [instructions d’installation générales.](https://docs.microsoft.com/microsoftsearch/configure-connector)</span><span class="sxs-lookup"><span data-stu-id="1e071-150">Follow the general [setup instructions](https://docs.microsoft.com/microsoftsearch/configure-connector).</span></span>
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-8-review-connection"></a><span data-ttu-id="1e071-151">Étape 8 : Examiner la connexion</span><span class="sxs-lookup"><span data-stu-id="1e071-151">Step 8: Review connection</span></span>

<span data-ttu-id="1e071-152">Suivez les [instructions d’installation générales.](https://docs.microsoft.com/microsoftsearch/configure-connector)</span><span class="sxs-lookup"><span data-stu-id="1e071-152">Follow the general [setup instructions](https://docs.microsoft.com/microsoftsearch/configure-connector).</span></span>
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup 
instructions.-->

<!---## Troubleshooting-->
<!---Insert troubleshooting recommendations for this data source-->

<!---## Limitations-->
<!---Insert limitations for this data source-->
