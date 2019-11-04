---
title: Créer des signets en bloc
ms.author: dawholl
author: dawholl
manager: kellis
ms.date: 09/11/2018
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
ms.assetid: def300e7-103c-4e92-a062-28ffa27561d7
ROBOTS: NoIndex
description: Créer un grand nombre de signets à la fois avec les outils d’importation pour le portail d’administration de Microsoft Search
ms.openlocfilehash: 2983a47a8761a2463b25497911024f9bfd069369
ms.sourcegitcommit: bfcab9d42e93addccd1e3875b41bc9cc1b6986cc
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/04/2019
ms.locfileid: "37948923"
---
# <a name="bulk-create-bookmarks"></a><span data-ttu-id="214cb-103">Créer des signets en bloc</span><span class="sxs-lookup"><span data-stu-id="214cb-103">Bulk create bookmarks</span></span>

> [!IMPORTANT]
> <span data-ttu-id="214cb-104">Cet article s’applique à la fonctionnalité Recherche Microsoft dans le portail d’administration Bing.</span><span class="sxs-lookup"><span data-stu-id="214cb-104">This article applies to the Microsoft Search in Bing admin portal.</span></span> <span data-ttu-id="214cb-105">Nous déplaçons le portail vers le centre d’administration Microsoft 365. Nous supprimerons ensuite la fonctionnalité Recherche Microsoft dans le portail Bing.</span><span class="sxs-lookup"><span data-stu-id="214cb-105">We’re moving the portal to the Microsoft 365 admin center, and then the Microsoft Search in Bing portal will be removed.</span></span> <span data-ttu-id="214cb-106">Pour commencer, nous vous suggérons d’utiliser le centre d’administration Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="214cb-106">We recommend that you use the Microsoft 365 admin center to get started.</span></span> <span data-ttu-id="214cb-107">[Vue d’ensemble de la fonctionnalité Recherche Microsoft](overview-microsoft-search.md).</span><span class="sxs-lookup"><span data-stu-id="214cb-107">[Overview of Microsoft Search](overview-microsoft-search.md).</span></span>
    
<span data-ttu-id="214cb-108">Téléchargez et utilisez le modèle. csv pour créer, modifier et enregistrer des signets en bloc.</span><span class="sxs-lookup"><span data-stu-id="214cb-108">Download and use the .csv template to bulk create, edit, and save bookmarks.</span></span> <span data-ttu-id="214cb-109">Pour modifier en bloc des signets existants, exportez-les à partir du portail d’administration, effectuez les modifications nécessaires, puis importez-les.</span><span class="sxs-lookup"><span data-stu-id="214cb-109">To bulk edit existing bookmarks, export them from the Admin portal, make the necessary edits, and then import them.</span></span>
  
1. <span data-ttu-id="214cb-110">Dans le coin supérieur droit de la section signets, cliquez sur **Importer** .</span><span class="sxs-lookup"><span data-stu-id="214cb-110">In the upper-right corner of the Bookmarks section, click **Import**</span></span>
    
2. <span data-ttu-id="214cb-111">Cliquez sur **Télécharger le modèle de signets (. csv)** .</span><span class="sxs-lookup"><span data-stu-id="214cb-111">Click **Download bookmarks template (.csv)**</span></span>
    
3. <span data-ttu-id="214cb-112">Enregistrez et ouvrez le fichier .csv.</span><span class="sxs-lookup"><span data-stu-id="214cb-112">Save and open the .csv file</span></span>
    
4. <span data-ttu-id="214cb-113">Ajouter le contenu et les paramètres du signet et enregistrer le fichier</span><span class="sxs-lookup"><span data-stu-id="214cb-113">Add the bookmark content and settings and save the file</span></span>

    <span data-ttu-id="214cb-114">Le fichier. csv doit être enregistré au format CSV UTF-8, car d’autres types ou codages de fichiers peuvent occasionner des erreurs d’importation.</span><span class="sxs-lookup"><span data-stu-id="214cb-114">The .csv file should be saved as a CSV UTF-8 file, other file types and or encodings may cause import errors</span></span>
    
5. <span data-ttu-id="214cb-115">Dans le coin supérieur droit de la section signets, cliquez sur **Importer** .</span><span class="sxs-lookup"><span data-stu-id="214cb-115">In the upper-right corner of the Bookmarks section, click **Import**</span></span>
    
6. <span data-ttu-id="214cb-116">Dans le volet importer les signets, cliquez sur **Parcourir** et naviguez jusqu’au fichier. csv que vous souhaitez importer.</span><span class="sxs-lookup"><span data-stu-id="214cb-116">In the Import bookmarks pane, click **Browse** and navigate to the .csv file you want to import</span></span> 
    
7. <span data-ttu-id="214cb-117">Cliquez sur **Importer**.</span><span class="sxs-lookup"><span data-stu-id="214cb-117">Click **Import**</span></span>

## <a name="prevent-import-errors"></a><span data-ttu-id="214cb-118">Éviter les erreurs d’importation</span><span class="sxs-lookup"><span data-stu-id="214cb-118">Prevent import errors</span></span>      
<span data-ttu-id="214cb-119">Si des données requises sont manquantes ou non valides, un message d’erreur s’affiche.</span><span class="sxs-lookup"><span data-stu-id="214cb-119">You'll get an error if any required data is missing or invalid.</span></span> <span data-ttu-id="214cb-120">Selon l’erreur, un fichier journal peut être généré afin de fournir des informations supplémentaires sur les lignes et les colonnes à corriger.</span><span class="sxs-lookup"><span data-stu-id="214cb-120">Depending on the error, a log file may be generated with more information about the rows and columns that need to be corrected.</span></span> <span data-ttu-id="214cb-121">Apportez les modifications nécessaires, puis réessayez d’importer le fichier.</span><span class="sxs-lookup"><span data-stu-id="214cb-121">Make any necessary edits, and try importing the file again.</span></span>

> [!NOTE]
> <span data-ttu-id="214cb-122">Tant que toutes les erreurs ne sont pas résolues, vous ne pouvez pas créer ni modifier de signets.</span><span class="sxs-lookup"><span data-stu-id="214cb-122">Until all errors are resolved, you can't create or edit any bookmarks.</span></span> 

<span data-ttu-id="214cb-123">Pour éviter les erreurs, assurez-vous que votre fichier d’importation est correctement mis en forme, à savoir :</span><span class="sxs-lookup"><span data-stu-id="214cb-123">To help prevent errors, make sure your import file is properly formatted:</span></span>
- <span data-ttu-id="214cb-124">Il inclut la ligne d’en-tête qui figurait dans le modèle d’importation.</span><span class="sxs-lookup"><span data-stu-id="214cb-124">Includes the header row that was in the import template</span></span>
- <span data-ttu-id="214cb-125">Il inclut toutes les colonnes qui figuraient dans le modèle d’importation.</span><span class="sxs-lookup"><span data-stu-id="214cb-125">Includes all columns that were in the import template</span></span>
- <span data-ttu-id="214cb-126">L’ordre des colonnes est le même que celui du modèle d’importation.</span><span class="sxs-lookup"><span data-stu-id="214cb-126">The column order is the same as the import template</span></span>
- <span data-ttu-id="214cb-127">Les colonnes suivantes peuvent être vides : ID, Dernière modification et Dernière modification par.</span><span class="sxs-lookup"><span data-stu-id="214cb-127">These columns can be empty: Id, Last Modified, and Last Modified By</span></span>
- <span data-ttu-id="214cb-128">La colonne État ne peut pas être vide. Cette information est obligatoire.</span><span class="sxs-lookup"><span data-stu-id="214cb-128">The State column can't be empty, this information is required</span></span>  
<span data-ttu-id="214cb-129">En fonction du champ État, les signets sont enregistrés en tant que signets brouillons, suggérés ou programmés, ou sont automatiquement publiés.</span><span class="sxs-lookup"><span data-stu-id="214cb-129">Based on the State field, bookmarks will be saved as draft, suggested, scheduled, or they will be published automatically.</span></span>

<span data-ttu-id="214cb-130">En outre, si vous incluez l’ID d’un signet existant, il sera remplacé par les informations contenues dans le fichier d’importation.</span><span class="sxs-lookup"><span data-stu-id="214cb-130">Also, if you include the Id of an existing bookmark, it will be replaced with the information in the import file.</span></span>

<span data-ttu-id="214cb-131">Pour les partenaires qui gèrent plusieurs organisations, vous pouvez exporter vos signets d’une organisation et les importer dans un autre.</span><span class="sxs-lookup"><span data-stu-id="214cb-131">For partners who manage multiple organizations, you can export your bookmarks from one org and import them into another.</span></span> <span data-ttu-id="214cb-132">Toutefois, avant l’importation, vous devez supprimer les données contenues dans la colonne ID.</span><span class="sxs-lookup"><span data-stu-id="214cb-132">But you must remove all of the data in the Id column before you import.</span></span>

<span data-ttu-id="214cb-133">Pour en savoir plus sur les champs requis et recommandés, consultez la rubrique [création de signets](create-bookmarks.md).</span><span class="sxs-lookup"><span data-stu-id="214cb-133">To find out more about required and recommended fields, see [Create bookmarks](create-bookmarks.md).</span></span>
