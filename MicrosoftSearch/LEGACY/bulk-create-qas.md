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
ms.openlocfilehash: 660f5663ff6238f4ab59dab36d51f1311d5c7260
ms.sourcegitcommit: 6b531b2ce7253c16251c7089795dedf1d2f3fc33
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/13/2019
ms.locfileid: "38311539"
---
# <a name="bulk-create-qas"></a><span data-ttu-id="ab5b5-103">Créer en bloc des questions et réponses</span><span class="sxs-lookup"><span data-stu-id="ab5b5-103">Bulk create Q&As</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ab5b5-104">Cet article s’applique à la fonctionnalité Recherche Microsoft dans le portail d’administration Bing.</span><span class="sxs-lookup"><span data-stu-id="ab5b5-104">This article applies to the Microsoft Search in Bing admin portal.</span></span> <span data-ttu-id="ab5b5-105">Nous déplaçons le portail vers le centre d’administration Microsoft 365. Nous supprimerons ensuite la fonctionnalité Recherche Microsoft dans le portail Bing.</span><span class="sxs-lookup"><span data-stu-id="ab5b5-105">We’re moving the portal to the Microsoft 365 admin center, and then the Microsoft Search in Bing portal will be removed.</span></span> <span data-ttu-id="ab5b5-106">Pour commencer, nous vous suggérons d’utiliser le centre d’administration Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="ab5b5-106">We recommend that you use the Microsoft 365 admin center to get started.</span></span> <span data-ttu-id="ab5b5-107">[Vue d’ensemble de la fonctionnalité Recherche Microsoft](overview-microsoft-search.md).</span><span class="sxs-lookup"><span data-stu-id="ab5b5-107">[Overview of Microsoft Search](overview-microsoft-search.md).</span></span>
    
<span data-ttu-id="ab5b5-108">Téléchargez et utilisez le modèle .csv pour créer ou éditer en bloc des questions et réponses.</span><span class="sxs-lookup"><span data-stu-id="ab5b5-108">Download and use the .csv template to bulk create or bulk edit Q&As.</span></span> <span data-ttu-id="ab5b5-109">C’est également un moyen simple d’enregistrer en bloc les brouillons de FAQ qui ont besoin de plus de modifications ou mises à jour.</span><span class="sxs-lookup"><span data-stu-id="ab5b5-109">It's also a simple way to bulk save draft Q&As that need additional edits or updates.</span></span> <span data-ttu-id="ab5b5-110">Si vous avez besoin de modifier des Q&R existants en bloc, des les exporter à partir du portail d’administration, apportez les modifications nécessaires, puis importez-les.</span><span class="sxs-lookup"><span data-stu-id="ab5b5-110">If you need to bulk edit existing Q&As, export them from the Admin portal, make the necessary edits, and then import them.</span></span>
  
1. <span data-ttu-id="ab5b5-111">Dans le coin supérieur droit de l’écran Q&R, cliquez sur **Importer**.</span><span class="sxs-lookup"><span data-stu-id="ab5b5-111">In the upper-right corner of the Q&As section, click **Import**</span></span>
    
2. <span data-ttu-id="ab5b5-112">Cliquez sur **télécharger un modèle Q&R (.csv)**</span><span class="sxs-lookup"><span data-stu-id="ab5b5-112">Click **Download Q&A template (.csv)**</span></span>
    
3. <span data-ttu-id="ab5b5-113">Enregistrez et ouvrez le fichier .csv.</span><span class="sxs-lookup"><span data-stu-id="ab5b5-113">Save and open the .csv file</span></span>
    
4. <span data-ttu-id="ab5b5-114">Ajoutez le contenu et les paramètres des Q&R, puis enregistrez le fichier.</span><span class="sxs-lookup"><span data-stu-id="ab5b5-114">Add the Q&A content and settings and save the file</span></span>

    <span data-ttu-id="ab5b5-115">Le fichier. csv doit être enregistré au format CSV UTF-8, car d’autres types ou codages de fichiers peuvent occasionner des erreurs d’importation.</span><span class="sxs-lookup"><span data-stu-id="ab5b5-115">The .csv file should be saved as a CSV UTF-8 file, other file types and or encodings may cause import errors</span></span>
    
5. <span data-ttu-id="ab5b5-116">Dans l’angle supérieur droit de la section Q&R, cliquez sur **Importer**.</span><span class="sxs-lookup"><span data-stu-id="ab5b5-116">In the upper-right corner of the Q&As section, click **Import**</span></span>
    
6. <span data-ttu-id="ab5b5-117">Dans le volet Import Q&As (Importer des Q&R), cliquez sur **Parcourir**, puis accédez au fichier .csv à importer.</span><span class="sxs-lookup"><span data-stu-id="ab5b5-117">In the Import Q&As pane, click **Browse** and navigate to the .csv file you want to import</span></span> 
    
7. <span data-ttu-id="ab5b5-118">Cliquez sur **Importer**.</span><span class="sxs-lookup"><span data-stu-id="ab5b5-118">Click **Import**</span></span>

## <a name="prevent-import-errors"></a><span data-ttu-id="ab5b5-119">Éviter les erreurs d’importation</span><span class="sxs-lookup"><span data-stu-id="ab5b5-119">Prevent import errors</span></span>      
<span data-ttu-id="ab5b5-120">Si des données requises sont manquantes ou non valides, un message d’erreur s’affiche.</span><span class="sxs-lookup"><span data-stu-id="ab5b5-120">You'll get an error if any required data is missing or invalid.</span></span> <span data-ttu-id="ab5b5-121">Selon l’erreur, un fichier journal peut être généré afin de fournir des informations supplémentaires sur les lignes et les colonnes à corriger.</span><span class="sxs-lookup"><span data-stu-id="ab5b5-121">Depending on the error, a log file may be generated with more information about the rows and columns that need to be corrected.</span></span> <span data-ttu-id="ab5b5-122">Apportez les modifications nécessaires, puis réessayez d’importer le fichier.</span><span class="sxs-lookup"><span data-stu-id="ab5b5-122">Make any necessary edits, and try importing the file again.</span></span>

> [!NOTE]
> <span data-ttu-id="ab5b5-123">Vous ne pouvez pas créer ou modifier des Q&R tant que toutes les erreurs ne sont pas résolues.</span><span class="sxs-lookup"><span data-stu-id="ab5b5-123">Until all errors are resolved, you can't create or edit any Q&As.</span></span> 

<span data-ttu-id="ab5b5-124">Pour éviter les erreurs, assurez-vous que votre fichier d’importation est correctement mis en forme, à savoir :</span><span class="sxs-lookup"><span data-stu-id="ab5b5-124">To help prevent errors, make sure your import file is properly formatted:</span></span>
- <span data-ttu-id="ab5b5-125">Il inclut la ligne d’en-tête qui figurait dans le modèle d’importation.</span><span class="sxs-lookup"><span data-stu-id="ab5b5-125">Includes the header row that was in the import template</span></span>
- <span data-ttu-id="ab5b5-126">Il inclut toutes les colonnes qui figuraient dans le modèle d’importation.</span><span class="sxs-lookup"><span data-stu-id="ab5b5-126">Includes all columns that were in the import template</span></span>
- <span data-ttu-id="ab5b5-127">L’ordre des colonnes est le même que celui du modèle d’importation.</span><span class="sxs-lookup"><span data-stu-id="ab5b5-127">The column order is the same as the import template</span></span>
- <span data-ttu-id="ab5b5-128">Les colonnes suivantes peuvent être vides : ID, Dernière modification et Dernière modification par.</span><span class="sxs-lookup"><span data-stu-id="ab5b5-128">These columns can be empty: Id, Last Modified, and Last Modified By</span></span>
- <span data-ttu-id="ab5b5-129">La colonne État ne peut pas être vide. Cette information est obligatoire.</span><span class="sxs-lookup"><span data-stu-id="ab5b5-129">The State column can't be empty, this information is required</span></span>  
<span data-ttu-id="ab5b5-130">En fonction du contenu du champ Statut, les Q&R sont enregistrés en tant que Brouillon, Suggéré ou Planifié, ou sont automatiquement publiés.</span><span class="sxs-lookup"><span data-stu-id="ab5b5-130">Based on the State field, Q&As will be saved as draft, suggested, scheduled, or they will be published automatically.</span></span>

<span data-ttu-id="ab5b5-131">Par ailleurs, si vous incluez l’ID d’une Q&R existante, celle-ci est remplacée par les informations contenues dans le fichier d’importation.</span><span class="sxs-lookup"><span data-stu-id="ab5b5-131">Also, if you include the Id of an existing Q&A, it will be replaced with the information in the import file.</span></span>

<span data-ttu-id="ab5b5-132">Pour les partenaires qui gèrent plusieurs organisations, vous pouvez exporter votre&Q à partir d’une organisation et les importer dans un autre.</span><span class="sxs-lookup"><span data-stu-id="ab5b5-132">For partners who manage multiple organizations, you can export your Q&As from one org and import them into another.</span></span> <span data-ttu-id="ab5b5-133">Toutefois, avant l’importation, vous devez supprimer les données contenues dans la colonne ID.</span><span class="sxs-lookup"><span data-stu-id="ab5b5-133">But you must remove all of the data in the Id column before you import.</span></span>

<span data-ttu-id="ab5b5-134">Pour en savoir plus sur les champs obligatoires et recommandés, voir [Créer des Q&R](create-qas.md).</span><span class="sxs-lookup"><span data-stu-id="ab5b5-134">To find out more about required and recommended fields, see [Create Q&As](create-qas.md).</span></span>

  

