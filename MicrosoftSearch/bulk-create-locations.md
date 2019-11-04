---
title: Créer en bloc des emplacements
ms.author: dawholl
author: dawholl
manager: kellis
ms.date: 12/18/2018
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
ms.assetid: 15c9fada-f7a6-4210-aa6b-028b32217830
ROBOTS: NoIndex
description: Ajouter des emplacements à la fois à l’aide des outils d’importation pour le portail d’administration de Microsoft Search
ms.openlocfilehash: e01c3774439a931dc81f850d8cbee76cc6128a53
ms.sourcegitcommit: bfcab9d42e93addccd1e3875b41bc9cc1b6986cc
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/04/2019
ms.locfileid: "37948969"
---
# <a name="bulk-create-locations"></a><span data-ttu-id="e3c39-103">Créer en bloc des emplacements</span><span class="sxs-lookup"><span data-stu-id="e3c39-103">Bulk create locations</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e3c39-104">Cet article s’applique à la fonctionnalité Recherche Microsoft dans le portail d’administration Bing.</span><span class="sxs-lookup"><span data-stu-id="e3c39-104">This article applies to the Microsoft Search in Bing admin portal.</span></span> <span data-ttu-id="e3c39-105">Nous déplaçons le portail vers le centre d’administration Microsoft 365. Nous supprimerons ensuite la fonctionnalité Recherche Microsoft dans le portail Bing.</span><span class="sxs-lookup"><span data-stu-id="e3c39-105">We’re moving the portal to the Microsoft 365 admin center, and then the Microsoft Search in Bing portal will be removed.</span></span> <span data-ttu-id="e3c39-106">Pour commencer, nous vous suggérons d’utiliser le centre d’administration Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="e3c39-106">We recommend that you use the Microsoft 365 admin center to get started.</span></span> <span data-ttu-id="e3c39-107">[Vue d’ensemble de la fonctionnalité Recherche Microsoft](overview-microsoft-search.md).</span><span class="sxs-lookup"><span data-stu-id="e3c39-107">[Overview of Microsoft Search](overview-microsoft-search.md).</span></span>
    
<span data-ttu-id="e3c39-108">Téléchargez et utilisez le modèle. csv pour créer, modifier et enregistrer en bloc des emplacements.</span><span class="sxs-lookup"><span data-stu-id="e3c39-108">Download and use the .csv template to bulk create, edit, and save locations.</span></span> 
  
1. <span data-ttu-id="e3c39-109">Dans le coin supérieur droit de la section emplacements, cliquez sur **Importer** .</span><span class="sxs-lookup"><span data-stu-id="e3c39-109">In the upper-right corner of the Locations section, click **Import**</span></span>
    
2. <span data-ttu-id="e3c39-110">Cliquez sur **Télécharger les emplacements (. csv)** .</span><span class="sxs-lookup"><span data-stu-id="e3c39-110">Click **Download locations template (.csv)**</span></span>
    
3. <span data-ttu-id="e3c39-111">Enregistrez et ouvrez le fichier .csv.</span><span class="sxs-lookup"><span data-stu-id="e3c39-111">Save and open the .csv file</span></span>
    
4. <span data-ttu-id="e3c39-112">Ajouter le contenu de l’emplacement et enregistrer le fichier</span><span class="sxs-lookup"><span data-stu-id="e3c39-112">Add the location content and save the file</span></span>

    <span data-ttu-id="e3c39-113">Le fichier. csv doit être enregistré au format CSV UTF-8, car d’autres types ou codages de fichiers peuvent occasionner des erreurs d’importation.</span><span class="sxs-lookup"><span data-stu-id="e3c39-113">The .csv file should be saved as a CSV UTF-8 file, other file types and or encodings may cause import errors</span></span>
    
5. <span data-ttu-id="e3c39-114">Dans le coin supérieur droit de la section emplacements, cliquez sur **Importer** .</span><span class="sxs-lookup"><span data-stu-id="e3c39-114">In the upper-right corner of the Locations section, click **Import**</span></span>
    
6. <span data-ttu-id="e3c39-115">Dans le volet importer des emplacements, cliquez sur **Parcourir** et naviguez jusqu’au fichier. csv que vous souhaitez importer.</span><span class="sxs-lookup"><span data-stu-id="e3c39-115">In the Import locations pane, click **Browse** and navigate to the .csv file you want to import</span></span> 
    
7. <span data-ttu-id="e3c39-116">Cliquez sur **Importer**.</span><span class="sxs-lookup"><span data-stu-id="e3c39-116">Click **Import**</span></span>

<span data-ttu-id="e3c39-117">Les champs des modèles d’emplacement d’importation et d’exportation sont les mêmes.</span><span class="sxs-lookup"><span data-stu-id="e3c39-117">The fields in the import and export locations templates are the same.</span></span> <span data-ttu-id="e3c39-118">Vous pouvez exporter, modifier en bloc et importer les modifications, ou commencer avec un modèle vide pour créer des emplacements en bloc.</span><span class="sxs-lookup"><span data-stu-id="e3c39-118">You can export, bulk edit, and import the edits, or start with an empty template to bulk create new locations.</span></span> <span data-ttu-id="e3c39-119">Pour modifier en bloc des emplacements existants, exportez-les à partir du portail d’administration, effectuez les modifications nécessaires, puis importez-les.</span><span class="sxs-lookup"><span data-stu-id="e3c39-119">To bulk edit existing locations, export them from the Admin portal, make the necessary edits, and then import them.</span></span>

## <a name="prevent-import-errors"></a><span data-ttu-id="e3c39-120">Éviter les erreurs d’importation</span><span class="sxs-lookup"><span data-stu-id="e3c39-120">Prevent import errors</span></span>  
<span data-ttu-id="e3c39-121">Si des données requises sont manquantes ou non valides, un message d’erreur s’affiche.</span><span class="sxs-lookup"><span data-stu-id="e3c39-121">You'll get an error if any required data is missing or invalid.</span></span> <span data-ttu-id="e3c39-122">Selon l’erreur, un fichier journal peut être généré afin de fournir des informations supplémentaires sur les lignes et les colonnes à corriger.</span><span class="sxs-lookup"><span data-stu-id="e3c39-122">Depending on the error, a log file may be generated with more information about the rows and columns that need to be corrected.</span></span> <span data-ttu-id="e3c39-123">Apportez les modifications nécessaires, puis réessayez d’importer le fichier.</span><span class="sxs-lookup"><span data-stu-id="e3c39-123">Make any necessary edits, and try importing the file again.</span></span>
  
> [!NOTE]
> <span data-ttu-id="e3c39-124">Tant que toutes les erreurs ne sont pas résolues, vous ne pouvez pas créer ni modifier d’emplacements.</span><span class="sxs-lookup"><span data-stu-id="e3c39-124">Until all errors are resolved, you can't create or edit any locations.</span></span> 

<span data-ttu-id="e3c39-125">Pour éviter les erreurs, assurez-vous que votre fichier d’importation est correctement mis en forme, à savoir :</span><span class="sxs-lookup"><span data-stu-id="e3c39-125">To help prevent errors, make sure your import file is properly formatted:</span></span>
- <span data-ttu-id="e3c39-126">Il inclut la ligne d’en-tête qui figurait dans le modèle d’importation.</span><span class="sxs-lookup"><span data-stu-id="e3c39-126">Includes the header row that was in the import template</span></span>
- <span data-ttu-id="e3c39-127">Il inclut toutes les colonnes qui figuraient dans le modèle d’importation.</span><span class="sxs-lookup"><span data-stu-id="e3c39-127">Includes all columns that were in the import template</span></span>
- <span data-ttu-id="e3c39-128">L’ordre des colonnes est le même que celui du modèle d’importation.</span><span class="sxs-lookup"><span data-stu-id="e3c39-128">The column order is the same as the import template</span></span>
- <span data-ttu-id="e3c39-129">Ces colonnes peuvent être vides : ID, dernière modification, dernière modification par et lat/long.</span><span class="sxs-lookup"><span data-stu-id="e3c39-129">These columns can be empty: Id, Last Modified, Last Modified By, and Lat/Long</span></span>  
<span data-ttu-id="e3c39-130">Nous allons essayer de déterminer la table des adresses locales/longue en fonction de l’adresse si ce champ est vide.</span><span class="sxs-lookup"><span data-stu-id="e3c39-130">We'll try to determine lat/long based on the address if that field is empty</span></span>
- <span data-ttu-id="e3c39-131">La colonne État ne peut pas être vide. Cette information est obligatoire.</span><span class="sxs-lookup"><span data-stu-id="e3c39-131">The State column can't be empty, this information is required</span></span>  
<span data-ttu-id="e3c39-132">En fonction du champ d’État, les emplacements seront enregistrés en tant que brouillon, suggéré, programmé, ou ils seront publiés automatiquement.</span><span class="sxs-lookup"><span data-stu-id="e3c39-132">Based on the State field, locations will be saved as draft, suggested, scheduled, or they will be published automatically.</span></span>

<span data-ttu-id="e3c39-133">En outre, si vous incluez l’ID d’un emplacement existant, il sera remplacé par les informations contenues dans le fichier d’importation.</span><span class="sxs-lookup"><span data-stu-id="e3c39-133">Also, if you include the Id of an existing location, it will be replaced with the information in the import file.</span></span>

<span data-ttu-id="e3c39-134">Pour les partenaires qui gèrent plusieurs organisations, vous pouvez exporter vos emplacements d’une organisation et les importer dans un autre.</span><span class="sxs-lookup"><span data-stu-id="e3c39-134">For partners who manage multiple organizations, you can export your locations from one org and import them into another.</span></span> <span data-ttu-id="e3c39-135">Toutefois, avant l’importation, vous devez supprimer les données contenues dans la colonne ID.</span><span class="sxs-lookup"><span data-stu-id="e3c39-135">But you must remove all of the data in the Id column before you import.</span></span>
  
<span data-ttu-id="e3c39-136">Pour en savoir plus sur les champs requis et recommandés, consultez [la rubrique ajouter un emplacement](add-a-location.md).</span><span class="sxs-lookup"><span data-stu-id="e3c39-136">To find out more about required and recommended fields, see [Add a location](add-a-location.md).</span></span>

  

