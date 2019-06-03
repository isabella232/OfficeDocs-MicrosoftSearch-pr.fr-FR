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
description: Ajoutez un grand nombre d’emplacements à la fois grâce aux outils d’importation pour le portail d’administration de la fonctionnalité Recherche Microsoft
ms.openlocfilehash: 186f6973de1ff87b62b5f07a47eb41acdd842010
ms.sourcegitcommit: be2e837d9b087bffe6ce40d72d7ae58a8fcdf3fe
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/30/2019
ms.locfileid: "34591394"
---
# <a name="bulk-create-locations"></a><span data-ttu-id="3f4a7-103">Créer en bloc des emplacements</span><span class="sxs-lookup"><span data-stu-id="3f4a7-103">Bulk create locations</span></span>

> [!IMPORTANT]
> <span data-ttu-id="3f4a7-104">Cet article s’applique à la fonctionnalité Recherche Microsoft dans le portail d’administration Bing.</span><span class="sxs-lookup"><span data-stu-id="3f4a7-104">This article applies to the Microsoft Search in Bing admin portal.</span></span> <span data-ttu-id="3f4a7-105">Nous déplaçons le portail vers le centre d’administration Microsoft 365. Ensuite, nous le supprimerons.</span><span class="sxs-lookup"><span data-stu-id="3f4a7-105">We’re moving the portal to the Microsoft 365 admin center, and then it will be removed.</span></span> <span data-ttu-id="3f4a7-106">Pour commencer, nous vous suggérons d’utiliser le centre d’administration Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="3f4a7-106">We recommend that you use the Microsoft 365 admin center to get started.</span></span> <span data-ttu-id="3f4a7-107">[Vue d’ensemble de la fonctionnalité Recherche Microsoft](overview-microsoft-search.md).</span><span class="sxs-lookup"><span data-stu-id="3f4a7-107">[Overview of Microsoft Search](overview-microsoft-search.md)</span></span>
    
<span data-ttu-id="3f4a7-108">Téléchargez et utilisez le modèle .csv pour créer, éditer et enregistrer en bloc des emplacements.</span><span class="sxs-lookup"><span data-stu-id="3f4a7-108">Download and use the .csv template to bulk create, edit, and save locations.</span></span> 
  
1. <span data-ttu-id="3f4a7-109">Dans l’angle supérieur droit de la section Emplacements, cliquez sur **Importer**.</span><span class="sxs-lookup"><span data-stu-id="3f4a7-109">In the upper-right corner of the Locations tab, select **Import**.</span></span>
    
2. <span data-ttu-id="3f4a7-110">Cliquez sur **Download locations template (.csv)** (modèle Télécharger des emplacements (.csv)).</span><span class="sxs-lookup"><span data-stu-id="3f4a7-110">Click **Download locations template (.csv)**</span></span>
    
3. <span data-ttu-id="3f4a7-111">Enregistrez et ouvrez le fichier .csv.</span><span class="sxs-lookup"><span data-stu-id="3f4a7-111">Save and open the .csv file</span></span>
    
4. <span data-ttu-id="3f4a7-112">Ajoutez le contenu d’emplacements, puis enregistrez le fichier.</span><span class="sxs-lookup"><span data-stu-id="3f4a7-112">Add the location content and save the file</span></span>

    <span data-ttu-id="3f4a7-113">Le fichier. csv doit être enregistré au format CSV UTF-8, car d’autres types ou codages de fichiers peuvent occasionner des erreurs d’importation.</span><span class="sxs-lookup"><span data-stu-id="3f4a7-113">The .csv file should be saved as a CSV UTF-8 file, other file types and or encodings may cause import errors</span></span>
    
5. <span data-ttu-id="3f4a7-114">Dans l’angle supérieur droit de la section Emplacements, cliquez sur **Importer**.</span><span class="sxs-lookup"><span data-stu-id="3f4a7-114">In the upper-right corner of the Locations tab, select **Import**.</span></span>
    
6. <span data-ttu-id="3f4a7-115">Dans le volet Import locations (Importer des emplacements), cliquez sur **Parcourir** pour accéder au fichier .csv à importer.</span><span class="sxs-lookup"><span data-stu-id="3f4a7-115">In the Import locations pane, select **Browse**, and then the .csv file that you want to import.</span></span> 
    
7. <span data-ttu-id="3f4a7-116">Cliquez sur **Importer**.</span><span class="sxs-lookup"><span data-stu-id="3f4a7-116">Click **Import**.</span></span>

<span data-ttu-id="3f4a7-117">Les champs sont identiques dans les modèles d’importation et d’exportation d’emplacements.</span><span class="sxs-lookup"><span data-stu-id="3f4a7-117">The fields in the import and export locations templates are the same.</span></span> <span data-ttu-id="3f4a7-118">Vous pouvez exporter, modifier en bloc et importer les modifications, ou utiliser un modèle vierge pour créer en bloc de nouveaux emplacements.</span><span class="sxs-lookup"><span data-stu-id="3f4a7-118">You can export, bulk edit, and import the edits, or start with an empty template to bulk create new locations.</span></span> <span data-ttu-id="3f4a7-119">Pour modifier en bloc des emplacements, exportez-les à partir du portail d’administration, apportez les modifications nécessaires, puis importez-les.</span><span class="sxs-lookup"><span data-stu-id="3f4a7-119">To bulk edit existing locations, export them from the Admin portal, make the necessary edits, and then import them.</span></span>

# <a name="prevent-import-errors"></a><span data-ttu-id="3f4a7-120">Éviter les erreurs d’importation</span><span class="sxs-lookup"><span data-stu-id="3f4a7-120">Prevent import errors</span></span>  
<span data-ttu-id="3f4a7-121">Si des données requises sont manquantes ou non valides, un message d’erreur s’affiche.</span><span class="sxs-lookup"><span data-stu-id="3f4a7-121">You'll get an error if any required data is missing or invalid.</span></span> <span data-ttu-id="3f4a7-122">Selon l’erreur, un fichier journal peut être généré afin de fournir des informations supplémentaires sur les lignes et les colonnes à corriger.</span><span class="sxs-lookup"><span data-stu-id="3f4a7-122">Depending on the error, a log file may be generated with more information about the rows and columns that need to be corrected.</span></span> <span data-ttu-id="3f4a7-123">Apportez les modifications nécessaires, puis réessayez d’importer le fichier.</span><span class="sxs-lookup"><span data-stu-id="3f4a7-123">Make necessary edits and try importing the file again.</span></span>
  
> [!NOTE]
> <span data-ttu-id="3f4a7-124">Vous ne pouvez pas créer ou modifier des emplacements tant que toutes les erreurs ne sont pas résolues.</span><span class="sxs-lookup"><span data-stu-id="3f4a7-124">Until all errors are resolved, you can't create or edit any locations.</span></span> 

<span data-ttu-id="3f4a7-125">Pour éviter les erreurs, assurez-vous que votre fichier d’importation est correctement mis en forme, à savoir :</span><span class="sxs-lookup"><span data-stu-id="3f4a7-125">To prevent errors, make sure your import file is properly formatted and:</span></span>
- <span data-ttu-id="3f4a7-126">Il inclut la ligne d’en-tête qui figurait dans le modèle d’importation.</span><span class="sxs-lookup"><span data-stu-id="3f4a7-126">Includes the header row and all the columns that were in the import template</span></span>
- <span data-ttu-id="3f4a7-127">Il inclut toutes les colonnes qui figuraient dans le modèle d’importation.</span><span class="sxs-lookup"><span data-stu-id="3f4a7-127">Includes the header row and all the columns that were in the import template</span></span>
- <span data-ttu-id="3f4a7-128">L’ordre des colonnes est le même que celui du modèle d’importation.</span><span class="sxs-lookup"><span data-stu-id="3f4a7-128">The column order is the same as the import template</span></span>
- <span data-ttu-id="3f4a7-129">Les colonnes suivantes peuvent être vides : ID, Dernière modification, Dernière modification par et Latitude/Longitude.</span><span class="sxs-lookup"><span data-stu-id="3f4a7-129">These columns can be empty: Id, Last Modified, Last Modified By, and Lat/Long</span></span>  
<span data-ttu-id="3f4a7-130">Si les champs Latitude/Longitude sont vides, nous essaierons de déterminer leurs valeurs sur la base de l’adresse.</span><span class="sxs-lookup"><span data-stu-id="3f4a7-130">We'll try to determine lat/long based on the address if that field is empty</span></span>
- <span data-ttu-id="3f4a7-131">La colonne État ne peut pas être vide. Cette information est obligatoire.</span><span class="sxs-lookup"><span data-stu-id="3f4a7-131">The State column is not empty, as this information is required</span></span>  
<span data-ttu-id="3f4a7-132">En fonction du contenu du champ Statut, les emplacements sont enregistrés en tant que Brouillon, Suggéré ou Planifié, ou sont automatiquement publiés.</span><span class="sxs-lookup"><span data-stu-id="3f4a7-132">Based on the State field, bookmarks will be saved as draft, suggested, scheduled, or they will be published automatically.</span></span>

<span data-ttu-id="3f4a7-133">Par ailleurs, si vous incluez l’ID d’un emplacement existant, celui-ci est remplacé par les informations contenues dans le fichier d’importation.</span><span class="sxs-lookup"><span data-stu-id="3f4a7-133">If you include the Id of an existing bookmark, it will be replaced with the information in the import file.</span></span>

<span data-ttu-id="3f4a7-134">Si votre organisation compte plusieurs locataires, vous pouvez exporter vos emplacements à partir d’un locataire, puis les importer dans un autre.</span><span class="sxs-lookup"><span data-stu-id="3f4a7-134">For organizations with multiple tenants, you can export your bookmarks from one tenant and import it into another.</span></span> <span data-ttu-id="3f4a7-135">Toutefois, avant l’importation, vous devez supprimer les données contenues dans la colonne ID.</span><span class="sxs-lookup"><span data-stu-id="3f4a7-135">But you must remove the data in the Id column before you import.</span></span>
  
<span data-ttu-id="3f4a7-136">Pour en savoir plus sur les champs obligatoires et recommandés, voir la section [Ajouter un emplacement](add-a-location.md).</span><span class="sxs-lookup"><span data-stu-id="3f4a7-136">To find out more about required and recommended fields, see [Add a location](add-a-location.md).</span></span>

  

