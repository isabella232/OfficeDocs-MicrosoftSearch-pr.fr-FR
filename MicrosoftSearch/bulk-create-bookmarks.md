---
title: Créer en bloc des signets
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
description: Créez un grand nombre de signets à la fois grâce aux outils d’importation pour le portail d’administration de la fonctionnalité Recherche Microsoft
ms.openlocfilehash: 1b3922215534391c65547a4ece22310261626036
ms.sourcegitcommit: be2e837d9b087bffe6ce40d72d7ae58a8fcdf3fe
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/30/2019
ms.locfileid: "34591421"
---
# <a name="bulk-create-bookmarks"></a><span data-ttu-id="7e7f7-103">Créer en bloc des signets</span><span class="sxs-lookup"><span data-stu-id="7e7f7-103">Bulk create bookmarks</span></span>

> [!IMPORTANT]
> <span data-ttu-id="7e7f7-104">Cet article s’applique à la fonctionnalité Recherche Microsoft dans le portail d’administration Bing.</span><span class="sxs-lookup"><span data-stu-id="7e7f7-104">This article applies to the Microsoft Search in Bing admin portal.</span></span> <span data-ttu-id="7e7f7-105">Nous déplaçons le portail vers le centre d’administration Microsoft 365. Ensuite, nous le supprimerons.</span><span class="sxs-lookup"><span data-stu-id="7e7f7-105">We’re moving the portal to the Microsoft 365 admin center, and then it will be removed.</span></span> <span data-ttu-id="7e7f7-106">Pour commencer, nous vous suggérons d’utiliser le centre d’administration Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="7e7f7-106">We recommend that you use the Microsoft 365 admin center to get started.</span></span> <span data-ttu-id="7e7f7-107">[Vue d’ensemble de la fonctionnalité Recherche Microsoft](overview-microsoft-search.md).</span><span class="sxs-lookup"><span data-stu-id="7e7f7-107">[Overview of Microsoft Search](overview-microsoft-search.md)</span></span>
    
<span data-ttu-id="7e7f7-108">Téléchargez et utilisez le modèle .csv pour créer, éditer et enregistrer en bloc des signets.</span><span class="sxs-lookup"><span data-stu-id="7e7f7-108">Download and use the .csv template to bulk create, edit, and save bookmarks.</span></span> <span data-ttu-id="7e7f7-109">Pour modifier des signets en bloc, exportez-les à partir du portail d’administration, apportez les modifications nécessaires, puis importez-les.</span><span class="sxs-lookup"><span data-stu-id="7e7f7-109">To bulk edit existing bookmarks, export them from the Admin portal, make the necessary edits, and then import them.</span></span>
  
1. <span data-ttu-id="7e7f7-110">Dans le coin supérieur droit de la section Signets, cliquez sur **Importer**.</span><span class="sxs-lookup"><span data-stu-id="7e7f7-110">In the upper-right corner of the Bookmarks section, click **Import**</span></span>
    
2. <span data-ttu-id="7e7f7-111">Cliquez sur **Télécharger un modèle de signet (.csv)**.</span><span class="sxs-lookup"><span data-stu-id="7e7f7-111">Click **Download bookmarks template (.csv)**</span></span>
    
3. <span data-ttu-id="7e7f7-112">Enregistrez et ouvrez le fichier .csv.</span><span class="sxs-lookup"><span data-stu-id="7e7f7-112">Save and open the .csv file</span></span>
    
4. <span data-ttu-id="7e7f7-113">Ajoutez le contenu et les paramètres du signet, puis enregistrez le fichier.</span><span class="sxs-lookup"><span data-stu-id="7e7f7-113">Add the bookmark content and settings and save the file</span></span>

    <span data-ttu-id="7e7f7-114">Le fichier. csv doit être enregistré au format CSV UTF-8, car d’autres types ou codages de fichiers peuvent occasionner des erreurs d’importation.</span><span class="sxs-lookup"><span data-stu-id="7e7f7-114">The .csv file should be saved as a CSV UTF-8 file, other file types and or encodings may cause import errors</span></span>
    
5. <span data-ttu-id="7e7f7-115">Dans l’angle supérieur droit de la section Signets, cliquez sur **Importer**.</span><span class="sxs-lookup"><span data-stu-id="7e7f7-115">In the upper-right corner of the Bookmarks section, click **Import**</span></span>
    
6. <span data-ttu-id="7e7f7-116">Dans le volet Import bookmarks (Importer des signets), cliquez sur **Parcourir** et accédez au fichier .csv à importer.</span><span class="sxs-lookup"><span data-stu-id="7e7f7-116">In the Import bookmarks pane, select **Browse** and then the .csv file that you want to import.</span></span> 
    
7. <span data-ttu-id="7e7f7-117">Cliquez sur **Importer**.</span><span class="sxs-lookup"><span data-stu-id="7e7f7-117">Click **Import**.</span></span>

# <a name="prevent-import-errors"></a><span data-ttu-id="7e7f7-118">Éviter les erreurs d’importation</span><span class="sxs-lookup"><span data-stu-id="7e7f7-118">Prevent import errors</span></span>      
<span data-ttu-id="7e7f7-119">Si des données requises sont manquantes ou non valides, un message d’erreur s’affiche.</span><span class="sxs-lookup"><span data-stu-id="7e7f7-119">You'll get an error if any required data is missing or invalid.</span></span> <span data-ttu-id="7e7f7-120">Selon l’erreur, un fichier journal peut être généré afin de fournir des informations supplémentaires sur les lignes et les colonnes à corriger.</span><span class="sxs-lookup"><span data-stu-id="7e7f7-120">Depending on the error, a log file may be generated with more information about the rows and columns that need to be corrected.</span></span> <span data-ttu-id="7e7f7-121">Apportez les modifications nécessaires, puis réessayez d’importer le fichier.</span><span class="sxs-lookup"><span data-stu-id="7e7f7-121">Make necessary edits and try importing the file again.</span></span>

> [!NOTE]
> <span data-ttu-id="7e7f7-122">Vous ne pouvez pas créer ou modifier des signets tant que toutes les erreurs ne sont pas résolues.</span><span class="sxs-lookup"><span data-stu-id="7e7f7-122">Until all errors are resolved, you can't create or edit any bookmarks.</span></span> 

<span data-ttu-id="7e7f7-123">Pour éviter les erreurs, assurez-vous que votre fichier d’importation est correctement mis en forme, à savoir :</span><span class="sxs-lookup"><span data-stu-id="7e7f7-123">To prevent errors, make sure your import file is properly formatted and:</span></span>
- <span data-ttu-id="7e7f7-124">Il inclut la ligne d’en-tête qui figurait dans le modèle d’importation.</span><span class="sxs-lookup"><span data-stu-id="7e7f7-124">Includes the header row and all the columns that were in the import template</span></span>
- <span data-ttu-id="7e7f7-125">Il inclut toutes les colonnes qui figuraient dans le modèle d’importation.</span><span class="sxs-lookup"><span data-stu-id="7e7f7-125">Includes the header row and all the columns that were in the import template</span></span>
- <span data-ttu-id="7e7f7-126">L’ordre des colonnes est le même que celui du modèle d’importation.</span><span class="sxs-lookup"><span data-stu-id="7e7f7-126">The column order is the same as the import template</span></span>
- <span data-ttu-id="7e7f7-127">Les colonnes suivantes peuvent être vides : ID, Dernière modification et Dernière modification par.</span><span class="sxs-lookup"><span data-stu-id="7e7f7-127">All columns have values, except the three that can be empty: Id, Last Modified, and Last Modified By</span></span>
- <span data-ttu-id="7e7f7-128">La colonne État ne peut pas être vide. Cette information est obligatoire.</span><span class="sxs-lookup"><span data-stu-id="7e7f7-128">The State column is not empty, as this information is required</span></span>  
<span data-ttu-id="7e7f7-129">En fonction du contenu du champ Statut, les signets sont enregistrés en tant que Brouillon, Suggéré ou Planifié, ou sont automatiquement publiés.</span><span class="sxs-lookup"><span data-stu-id="7e7f7-129">Based on the State field, bookmarks will be saved as draft, suggested, scheduled, or they will be published automatically.</span></span>

<span data-ttu-id="7e7f7-130">Par ailleurs, si vous incluez l’ID d’un signet existant, celui-ci est remplacé par les informations contenues dans le fichier d’importation.</span><span class="sxs-lookup"><span data-stu-id="7e7f7-130">If you include the Id of an existing bookmark, it will be replaced with the information in the import file.</span></span>

<span data-ttu-id="7e7f7-131">Si votre organisation compte plusieurs locataires, vous pouvez exporter vos signets à partir d’un locataire, puis les importer dans un autre.</span><span class="sxs-lookup"><span data-stu-id="7e7f7-131">For organizations with multiple tenants, you can export your bookmarks from one tenant and import it into another.</span></span> <span data-ttu-id="7e7f7-132">Toutefois, avant l’importation, vous devez supprimer les données contenues dans la colonne ID.</span><span class="sxs-lookup"><span data-stu-id="7e7f7-132">But you must remove the data in the Id column before you import.</span></span>

<span data-ttu-id="7e7f7-133">Pour en savoir plus sur les champs obligatoires et recommandés, voir [Créer des signets](create-bookmarks.md).</span><span class="sxs-lookup"><span data-stu-id="7e7f7-133">To find out more about required and recommended fields, see [Create bookmarks](create-bookmarks.md).</span></span>
