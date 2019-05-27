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
description: Ajoutez un grand nombre d’emplacements à la fois grâce aux outils d’importation pour le portail d’administration de la fonctionnalité Recherche Microsoft
ms.openlocfilehash: 1d360fda2851083def0bcbd8fcffd77cfa15240e
ms.sourcegitcommit: 3e91a6e70b48a0100adfed1b62ba79f2fd1735d2
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/13/2019
ms.locfileid: "33968290"
---
# <a name="bulk-create-locations"></a><span data-ttu-id="96249-103">Créer en bloc des emplacements</span><span class="sxs-lookup"><span data-stu-id="96249-103">Bulk create locations</span></span>

> [!IMPORTANT]
> <span data-ttu-id="96249-104">Les paramètres de Recherche Microsoft dans Bing sont désormais accessibles dans le Centre d’administration Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="96249-104">Microsoft Search in Bing settings are now available in the Microsoft 365 admin center.</span></span> <span data-ttu-id="96249-105">Commencez par [assigner des administrateurs de recherche](https://docs.microsoft.com/fr-FR/microsoftsearch/setup-microsoft-search#step-2-assign-search-admin-and-search-editor) dans votre centre d’administration.</span><span class="sxs-lookup"><span data-stu-id="96249-105">Get started by [assigning search admins](https://docs.microsoft.com/en-us/microsoftsearch/setup-microsoft-search#step-2-assign-search-admin-and-search-editor) in your admin center.</span></span>
    
<span data-ttu-id="96249-106">Téléchargez et utilisez le modèle .csv pour créer, éditer et enregistrer en bloc des emplacements.</span><span class="sxs-lookup"><span data-stu-id="96249-106">Download and use the .csv template to bulk create, edit, and save locations.</span></span> 
  
1. <span data-ttu-id="96249-107">Dans l’angle supérieur droit de la section Emplacements, cliquez sur **Importer**.</span><span class="sxs-lookup"><span data-stu-id="96249-107">In the upper-right corner of the Locations tab, select **Import**.</span></span>
    
2. <span data-ttu-id="96249-108">Cliquez sur **Download locations template (.csv)** (modèle Télécharger des emplacements (.csv)).</span><span class="sxs-lookup"><span data-stu-id="96249-108">Click **Download locations template (.csv)**</span></span>
    
3. <span data-ttu-id="96249-109">Enregistrez et ouvrez le fichier .csv.</span><span class="sxs-lookup"><span data-stu-id="96249-109">Save and open the .csv file</span></span>
    
4. <span data-ttu-id="96249-110">Ajoutez le contenu d’emplacements, puis enregistrez le fichier.</span><span class="sxs-lookup"><span data-stu-id="96249-110">Add the location content and save the file</span></span>

    <span data-ttu-id="96249-111">Le fichier. csv doit être enregistré au format CSV UTF-8, car d’autres types ou codages de fichiers peuvent occasionner des erreurs d’importation.</span><span class="sxs-lookup"><span data-stu-id="96249-111">The .csv file should be saved as a CSV UTF-8 file, other file types and or encodings may cause import errors</span></span>
    
5. <span data-ttu-id="96249-112">Dans l’angle supérieur droit de la section Emplacements, cliquez sur **Importer**.</span><span class="sxs-lookup"><span data-stu-id="96249-112">In the upper-right corner of the Locations tab, select **Import**.</span></span>
    
6. <span data-ttu-id="96249-113">Dans le volet Import locations (Importer des emplacements), cliquez sur **Parcourir** pour accéder au fichier .csv à importer.</span><span class="sxs-lookup"><span data-stu-id="96249-113">In the Import locations pane, select **Browse**, and then the .csv file that you want to import.</span></span> 
    
7. <span data-ttu-id="96249-114">Cliquez sur **Importer**.</span><span class="sxs-lookup"><span data-stu-id="96249-114">Click **Import**.</span></span>

<span data-ttu-id="96249-115">Les champs sont identiques dans les modèles d’importation et d’exportation d’emplacements.</span><span class="sxs-lookup"><span data-stu-id="96249-115">The fields in the import and export locations templates are the same.</span></span> <span data-ttu-id="96249-116">Vous pouvez exporter, modifier en bloc et importer les modifications, ou utiliser un modèle vierge pour créer en bloc de nouveaux emplacements.</span><span class="sxs-lookup"><span data-stu-id="96249-116">You can export, bulk edit, and import the edits, or start with an empty template to bulk create new locations.</span></span> <span data-ttu-id="96249-117">Pour modifier en bloc des emplacements, exportez-les à partir du portail d’administration, apportez les modifications nécessaires, puis importez-les.</span><span class="sxs-lookup"><span data-stu-id="96249-117">To bulk edit existing locations, export them from the Admin portal, make the necessary edits, and then import them.</span></span>

# <a name="prevent-import-errors"></a><span data-ttu-id="96249-118">Éviter les erreurs d’importation</span><span class="sxs-lookup"><span data-stu-id="96249-118">Prevent import errors</span></span>  
<span data-ttu-id="96249-119">Si des données requises sont manquantes ou non valides, un message d’erreur s’affiche.</span><span class="sxs-lookup"><span data-stu-id="96249-119">You'll get an error if any required data is missing or invalid.</span></span> <span data-ttu-id="96249-120">Selon l’erreur, un fichier journal peut être généré afin de fournir des informations supplémentaires sur les lignes et les colonnes à corriger.</span><span class="sxs-lookup"><span data-stu-id="96249-120">Depending on the error, a log file may be generated with more information about the rows and columns that need to be corrected.</span></span> <span data-ttu-id="96249-121">Apportez les modifications nécessaires, puis réessayez d’importer le fichier.</span><span class="sxs-lookup"><span data-stu-id="96249-121">Make necessary edits and try importing the file again.</span></span>
  
> [!NOTE]
> <span data-ttu-id="96249-122">Vous ne pouvez pas créer ou modifier des emplacements tant que toutes les erreurs ne sont pas résolues.</span><span class="sxs-lookup"><span data-stu-id="96249-122">Until all errors are resolved, you can't create or edit any locations.</span></span> 

<span data-ttu-id="96249-123">Pour éviter les erreurs, assurez-vous que votre fichier d’importation est correctement mis en forme, à savoir :</span><span class="sxs-lookup"><span data-stu-id="96249-123">To prevent errors, make sure your import file is properly formatted and:</span></span>
- <span data-ttu-id="96249-124">Il inclut la ligne d’en-tête qui figurait dans le modèle d’importation.</span><span class="sxs-lookup"><span data-stu-id="96249-124">Includes the header row and all the columns that were in the import template</span></span>
- <span data-ttu-id="96249-125">Il inclut toutes les colonnes qui figuraient dans le modèle d’importation.</span><span class="sxs-lookup"><span data-stu-id="96249-125">Includes the header row and all the columns that were in the import template</span></span>
- <span data-ttu-id="96249-126">L’ordre des colonnes est le même que celui du modèle d’importation.</span><span class="sxs-lookup"><span data-stu-id="96249-126">The column order is the same as the import template</span></span>
- <span data-ttu-id="96249-127">Les colonnes suivantes peuvent être vides : ID, Dernière modification, Dernière modification par et Latitude/Longitude.</span><span class="sxs-lookup"><span data-stu-id="96249-127">These columns can be empty: Id, Last Modified, Last Modified By, and Lat/Long</span></span>  
<span data-ttu-id="96249-128">Si les champs Latitude/Longitude sont vides, nous essaierons de déterminer leurs valeurs sur la base de l’adresse.</span><span class="sxs-lookup"><span data-stu-id="96249-128">We'll try to determine lat/long based on the address if that field is empty</span></span>
- <span data-ttu-id="96249-129">La colonne État ne peut pas être vide. Cette information est obligatoire.</span><span class="sxs-lookup"><span data-stu-id="96249-129">The State column is not empty, as this information is required</span></span>  
<span data-ttu-id="96249-130">En fonction du contenu du champ Statut, les emplacements sont enregistrés en tant que Brouillon, Suggéré ou Planifié, ou sont automatiquement publiés.</span><span class="sxs-lookup"><span data-stu-id="96249-130">Based on the State field, bookmarks will be saved as draft, suggested, scheduled, or they will be published automatically.</span></span>

<span data-ttu-id="96249-131">Par ailleurs, si vous incluez l’ID d’un emplacement existant, celui-ci est remplacé par les informations contenues dans le fichier d’importation.</span><span class="sxs-lookup"><span data-stu-id="96249-131">If you include the Id of an existing bookmark, it will be replaced with the information in the import file.</span></span>

<span data-ttu-id="96249-132">Si votre organisation compte plusieurs locataires, vous pouvez exporter vos emplacements à partir d’un locataire, puis les importer dans un autre.</span><span class="sxs-lookup"><span data-stu-id="96249-132">For organizations with multiple tenants, you can export your bookmarks from one tenant and import it into another.</span></span> <span data-ttu-id="96249-133">Toutefois, avant l’importation, vous devez supprimer les données contenues dans la colonne ID.</span><span class="sxs-lookup"><span data-stu-id="96249-133">But you must remove the data in the Id column before you import.</span></span>
  
<span data-ttu-id="96249-134">Pour en savoir plus sur les champs obligatoires et recommandés, voir la section [Ajouter un emplacement](add-a-location.md).</span><span class="sxs-lookup"><span data-stu-id="96249-134">To find out more about required and recommended fields, see [Add a location](add-a-location.md).</span></span>

  

