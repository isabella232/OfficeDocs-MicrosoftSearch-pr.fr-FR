---
title: Créer en bloc des Q&R
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
ms.assetid: 7bada218-8908-4956-aae3-6ffaeef384ca
ROBOTS: NoIndex
description: Ajoutez rapidement des réponses aux questions fréquemment posées à l’aide des outils d’importation disponibles dans le portail d’administration de Recherche Microsoft
ms.openlocfilehash: 7368014f3bc2f21a788625f0bf826af963366e1b
ms.sourcegitcommit: be2e837d9b087bffe6ce40d72d7ae58a8fcdf3fe
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/30/2019
ms.locfileid: "34591367"
---
# <a name="bulk-create-qas"></a><span data-ttu-id="098d9-103">Créer en bloc des questions et réponses</span><span class="sxs-lookup"><span data-stu-id="098d9-103">Bulk create Q&As</span></span>

> [!IMPORTANT]
> <span data-ttu-id="098d9-104">Cet article s’applique à la fonctionnalité Recherche Microsoft dans le portail d’administration Bing.</span><span class="sxs-lookup"><span data-stu-id="098d9-104">This article applies to the Microsoft Search in Bing admin portal.</span></span> <span data-ttu-id="098d9-105">Nous déplaçons le portail vers le centre d’administration Microsoft 365. Ensuite, nous le supprimerons.</span><span class="sxs-lookup"><span data-stu-id="098d9-105">We’re moving the portal to the Microsoft 365 admin center, and then it will be removed.</span></span> <span data-ttu-id="098d9-106">Pour commencer, nous vous suggérons d’utiliser le centre d’administration Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="098d9-106">We recommend that you use the Microsoft 365 admin center to get started.</span></span> <span data-ttu-id="098d9-107">[Vue d’ensemble de la fonctionnalité Recherche Microsoft](overview-microsoft-search.md).</span><span class="sxs-lookup"><span data-stu-id="098d9-107">[Overview of Microsoft Search](overview-microsoft-search.md)</span></span>
    
<span data-ttu-id="098d9-108">Téléchargez et utilisez le modèle .csv pour créer ou éditer en bloc des questions et réponses.</span><span class="sxs-lookup"><span data-stu-id="098d9-108">Download and use the .csv template to bulk create or bulk edit Q&As.</span></span> <span data-ttu-id="098d9-109">C’est également un moyen simple d’enregistrer en bloc les brouillons de FAQ qui ont besoin de plus de modifications ou mises à jour.</span><span class="sxs-lookup"><span data-stu-id="098d9-109">It's also a simple way to bulk save draft Q&As that need additional edits or updates.</span></span> <span data-ttu-id="098d9-110">Si vous avez besoin de modifier des Q&R existants en bloc, des les exporter à partir du portail d’administration, apportez les modifications nécessaires, puis importez-les.</span><span class="sxs-lookup"><span data-stu-id="098d9-110">If you need to bulk edit existing Q&As, export them from the Admin portal, make the necessary edits, and then import them.</span></span>
  
1. <span data-ttu-id="098d9-111">Dans le coin supérieur droit de l’écran Q&R, cliquez sur **Importer**.</span><span class="sxs-lookup"><span data-stu-id="098d9-111">In the upper-right corner of the Q&As section, click **Import**</span></span>
    
2. <span data-ttu-id="098d9-112">Cliquez sur **télécharger un modèle Q&R (.csv)**</span><span class="sxs-lookup"><span data-stu-id="098d9-112">Click **Download Q&A template (.csv)**</span></span>
    
3. <span data-ttu-id="098d9-113">Enregistrez et ouvrez le fichier .csv.</span><span class="sxs-lookup"><span data-stu-id="098d9-113">Save and open the .csv file</span></span>
    
4. <span data-ttu-id="098d9-114">Ajoutez le contenu et les paramètres des Q&R, puis enregistrez le fichier.</span><span class="sxs-lookup"><span data-stu-id="098d9-114">Add the Q&A content and settings and save the file</span></span>

    <span data-ttu-id="098d9-115">Le fichier. csv doit être enregistré au format CSV UTF-8, car d’autres types ou codages de fichiers peuvent occasionner des erreurs d’importation.</span><span class="sxs-lookup"><span data-stu-id="098d9-115">The .csv file should be saved as a CSV UTF-8 file, other file types and or encodings may cause import errors</span></span>
    
5. <span data-ttu-id="098d9-116">Dans l’angle supérieur droit de la section Q&R, cliquez sur **Importer**.</span><span class="sxs-lookup"><span data-stu-id="098d9-116">In the upper-right corner of the Q&As section, click **Import**</span></span>
    
6. <span data-ttu-id="098d9-117">Dans le volet Import Q&As (Importer des Q&R), cliquez sur **Parcourir**, puis accédez au fichier .csv à importer.</span><span class="sxs-lookup"><span data-stu-id="098d9-117">In the Import locations pane, select **Browse**, and then the .csv file that you want to import.</span></span> 
    
7. <span data-ttu-id="098d9-118">Cliquez sur **Importer**.</span><span class="sxs-lookup"><span data-stu-id="098d9-118">Click **Import**.</span></span>

# <a name="prevent-import-errors"></a><span data-ttu-id="098d9-119">Éviter les erreurs d’importation</span><span class="sxs-lookup"><span data-stu-id="098d9-119">Prevent import errors</span></span>      
<span data-ttu-id="098d9-120">Si des données requises sont manquantes ou non valides, un message d’erreur s’affiche.</span><span class="sxs-lookup"><span data-stu-id="098d9-120">You'll get an error if any required data is missing or invalid.</span></span> <span data-ttu-id="098d9-121">Selon l’erreur, un fichier journal peut être généré afin de fournir des informations supplémentaires sur les lignes et les colonnes à corriger.</span><span class="sxs-lookup"><span data-stu-id="098d9-121">Depending on the error, a log file may be generated with more information about the rows and columns that need to be corrected.</span></span> <span data-ttu-id="098d9-122">Apportez les modifications nécessaires, puis réessayez d’importer le fichier.</span><span class="sxs-lookup"><span data-stu-id="098d9-122">Make necessary edits and try importing the file again.</span></span>

> [!NOTE]
> <span data-ttu-id="098d9-123">Vous ne pouvez pas créer ou modifier des Q&R tant que toutes les erreurs ne sont pas résolues.</span><span class="sxs-lookup"><span data-stu-id="098d9-123">Until all errors are resolved, you can't create or edit any Q&As.</span></span> 

<span data-ttu-id="098d9-124">Pour éviter les erreurs, assurez-vous que votre fichier d’importation est correctement mis en forme, à savoir :</span><span class="sxs-lookup"><span data-stu-id="098d9-124">To prevent errors, make sure your import file is properly formatted and:</span></span>
- <span data-ttu-id="098d9-125">Il inclut la ligne d’en-tête qui figurait dans le modèle d’importation.</span><span class="sxs-lookup"><span data-stu-id="098d9-125">Includes the header row and all the columns that were in the import template</span></span>
- <span data-ttu-id="098d9-126">Il inclut toutes les colonnes qui figuraient dans le modèle d’importation.</span><span class="sxs-lookup"><span data-stu-id="098d9-126">Includes the header row and all the columns that were in the import template</span></span>
- <span data-ttu-id="098d9-127">L’ordre des colonnes est le même que celui du modèle d’importation.</span><span class="sxs-lookup"><span data-stu-id="098d9-127">The column order is the same as the import template</span></span>
- <span data-ttu-id="098d9-128">Les colonnes suivantes peuvent être vides : ID, Dernière modification et Dernière modification par.</span><span class="sxs-lookup"><span data-stu-id="098d9-128">All columns have values, except the three that can be empty: Id, Last Modified, and Last Modified By</span></span>
- <span data-ttu-id="098d9-129">La colonne État ne peut pas être vide. Cette information est obligatoire.</span><span class="sxs-lookup"><span data-stu-id="098d9-129">The State column is not empty, as this information is required</span></span>  
<span data-ttu-id="098d9-130">En fonction du contenu du champ Statut, les Q&R sont enregistrés en tant que Brouillon, Suggéré ou Planifié, ou sont automatiquement publiés.</span><span class="sxs-lookup"><span data-stu-id="098d9-130">Based on the State field, bookmarks will be saved as draft, suggested, scheduled, or they will be published automatically.</span></span>

<span data-ttu-id="098d9-131">Par ailleurs, si vous incluez l’ID d’une Q&R existante, celle-ci est remplacée par les informations contenues dans le fichier d’importation.</span><span class="sxs-lookup"><span data-stu-id="098d9-131">If you include the Id of an existing bookmark, it will be replaced with the information in the import file.</span></span>

<span data-ttu-id="098d9-132">Si votre organisation compte plusieurs locataires, vous pouvez exporter vos Q&R à partir d’un locataire, puis les importer dans un autre.</span><span class="sxs-lookup"><span data-stu-id="098d9-132">For organizations with multiple tenants, you can export your bookmarks from one tenant and import it into another.</span></span> <span data-ttu-id="098d9-133">Toutefois, avant l’importation, vous devez supprimer les données contenues dans la colonne ID.</span><span class="sxs-lookup"><span data-stu-id="098d9-133">But you must remove the data in the Id column before you import.</span></span>

<span data-ttu-id="098d9-134">Pour en savoir plus sur les champs obligatoires et recommandés, voir [Créer des Q&R](create-qas.md).</span><span class="sxs-lookup"><span data-stu-id="098d9-134">To find out more about required and recommended fields, see [Create Q&As](create-qas.md).</span></span>

  

