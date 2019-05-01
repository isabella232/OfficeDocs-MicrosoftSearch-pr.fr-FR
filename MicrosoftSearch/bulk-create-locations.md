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
description: Ajouter des emplacements à la fois à l'aide des outils d'importation pour le portail d'administration de Microsoft Search
ms.openlocfilehash: 3c7e43b03b97b46769d5e73f20ddae47b3459b59
ms.sourcegitcommit: a5fd9d4f46bbb7c539630735ac16e0c786939e5d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/01/2019
ms.locfileid: "33508560"
---
# <a name="bulk-create-locations"></a><span data-ttu-id="b6abe-103">Créer en bloc des emplacements</span><span class="sxs-lookup"><span data-stu-id="b6abe-103">Bulk create locations</span></span>

<span data-ttu-id="b6abe-104">Téléchargez et utilisez le modèle. csv pour créer, modifier et enregistrer en bloc des emplacements.</span><span class="sxs-lookup"><span data-stu-id="b6abe-104">Download and use the .csv template to bulk create, edit, and save locations.</span></span> 
  
1. <span data-ttu-id="b6abe-105">Dans le coin supérieur droit de la section emplacements, cliquez sur **Importer** .</span><span class="sxs-lookup"><span data-stu-id="b6abe-105">In the upper-right corner of the Locations section, click **Import**</span></span>
    
2. <span data-ttu-id="b6abe-106">Cliquez sur **Télécharger les emplacements (. csv)** .</span><span class="sxs-lookup"><span data-stu-id="b6abe-106">Click **Download locations template (.csv)**</span></span>
    
3. <span data-ttu-id="b6abe-107">Enregistrer et ouvrir le fichier. csv</span><span class="sxs-lookup"><span data-stu-id="b6abe-107">Save and open the .csv file</span></span>
    
4. <span data-ttu-id="b6abe-108">Ajouter le contenu de l'emplacement et enregistrer le fichier</span><span class="sxs-lookup"><span data-stu-id="b6abe-108">Add the location content and save the file</span></span>

    <span data-ttu-id="b6abe-109">Le fichier. csv doit être enregistré en tant que fichier CSV UTF-8, d'autres types de fichiers ou de codages peuvent entraîner des erreurs d'importation</span><span class="sxs-lookup"><span data-stu-id="b6abe-109">The .csv file should be saved as a CSV UTF-8 file, other file types and or encodings may cause import errors</span></span>
    
5. <span data-ttu-id="b6abe-110">Dans le coin supérieur droit de la section emplacements, cliquez sur **Importer** .</span><span class="sxs-lookup"><span data-stu-id="b6abe-110">In the upper-right corner of the Locations section, click **Import**</span></span>
    
6. <span data-ttu-id="b6abe-111">Dans le volet importer des emplacements, cliquez sur **Parcourir** et naviguez jusqu'au fichier. csv que vous souhaitez importer.</span><span class="sxs-lookup"><span data-stu-id="b6abe-111">In the Import locations pane, click **Browse** and navigate to the .csv file you want to import</span></span> 
    
7. <span data-ttu-id="b6abe-112">Cliquez sur **Importer**</span><span class="sxs-lookup"><span data-stu-id="b6abe-112">Click **Import**</span></span>

<span data-ttu-id="b6abe-113">Les champs des modèles d'emplacement d'importation et d'exportation sont les mêmes.</span><span class="sxs-lookup"><span data-stu-id="b6abe-113">The fields in the import and export locations templates are the same.</span></span> <span data-ttu-id="b6abe-114">Vous pouvez exporter, modifier en bloc et importer les modifications, ou commencer avec un modèle vide pour créer des emplacements en bloc.</span><span class="sxs-lookup"><span data-stu-id="b6abe-114">You can export, bulk edit, and import the edits, or start with an empty template to bulk create new locations.</span></span> <span data-ttu-id="b6abe-115">Pour modifier en bloc des emplacements existants, exportez-les à partir du portail d'administration, effectuez les modifications nécessaires, puis importez-les.</span><span class="sxs-lookup"><span data-stu-id="b6abe-115">To bulk edit existing locations, export them from the Admin portal, make the necessary edits, and then import them.</span></span>

# <a name="prevent-import-errors"></a><span data-ttu-id="b6abe-116">Empêcher les erreurs d'importation</span><span class="sxs-lookup"><span data-stu-id="b6abe-116">Prevent import errors</span></span>  
<span data-ttu-id="b6abe-117">Vous obtiendrez une erreur si les données requises sont manquantes ou non valides.</span><span class="sxs-lookup"><span data-stu-id="b6abe-117">You'll get an error if any required data is missing or invalid.</span></span> <span data-ttu-id="b6abe-118">En fonction de l'erreur, un fichier journal peut être généré avec davantage d'informations sur les lignes et les colonnes qui doivent être corrigées.</span><span class="sxs-lookup"><span data-stu-id="b6abe-118">Depending on the error, a log file may be generated with more information about the rows and columns that need to be corrected.</span></span> <span data-ttu-id="b6abe-119">Effectuez les modifications nécessaires, puis réessayez d'importer le fichier.</span><span class="sxs-lookup"><span data-stu-id="b6abe-119">Make any necessary edits, and try importing the file again.</span></span>
  
> [!NOTE]
> <span data-ttu-id="b6abe-120">Tant que toutes les erreurs ne sont pas résolues, vous ne pouvez pas créer ni modifier d'emplacements.</span><span class="sxs-lookup"><span data-stu-id="b6abe-120">Until all errors are resolved, you can't create or edit any locations.</span></span> 

<span data-ttu-id="b6abe-121">Pour éviter les erreurs, assurez-vous que votre fichier d'importation est correctement mis en forme:</span><span class="sxs-lookup"><span data-stu-id="b6abe-121">To help prevent errors, make sure your import file is properly formatted:</span></span>
- <span data-ttu-id="b6abe-122">Inclut la ligne d'en-tête qui était dans le modèle d'importation.</span><span class="sxs-lookup"><span data-stu-id="b6abe-122">Includes the header row that was in the import template</span></span>
- <span data-ttu-id="b6abe-123">Inclut toutes les colonnes qui se trouvaient dans le modèle d'importation.</span><span class="sxs-lookup"><span data-stu-id="b6abe-123">Includes all columns that were in the import template</span></span>
- <span data-ttu-id="b6abe-124">L'ordre des colonnes est le même que celui du modèle d'importation.</span><span class="sxs-lookup"><span data-stu-id="b6abe-124">The column order is the same as the import template</span></span>
- <span data-ttu-id="b6abe-125">Ces colonnes peuvent être vides: ID, dernière modification, dernière modification par et lat/long.</span><span class="sxs-lookup"><span data-stu-id="b6abe-125">These columns can be empty: Id, Last Modified, Last Modified By, and Lat/Long</span></span>  
<span data-ttu-id="b6abe-126">Nous allons essayer de déterminer la table des adresses locales/longue en fonction de l'adresse si ce champ est vide.</span><span class="sxs-lookup"><span data-stu-id="b6abe-126">We'll try to determine lat/long based on the address if that field is empty</span></span>
- <span data-ttu-id="b6abe-127">La colonne État ne peut pas être vide; cette information est requise</span><span class="sxs-lookup"><span data-stu-id="b6abe-127">The State column can't be empty, this information is required</span></span>  
<span data-ttu-id="b6abe-128">En fonction du champ d'État, les emplacements seront enregistrés en tant que brouillon, suggéré, programmé, ou ils seront publiés automatiquement.</span><span class="sxs-lookup"><span data-stu-id="b6abe-128">Based on the State field, locations will be saved as draft, suggested, scheduled, or they will be published automatically.</span></span>

<span data-ttu-id="b6abe-129">En outre, si vous incluez l'ID d'un emplacement existant, il sera remplacé par les informations contenues dans le fichier d'importation.</span><span class="sxs-lookup"><span data-stu-id="b6abe-129">Also, if you include the Id of an existing location, it will be replaced with the information in the import file.</span></span>

<span data-ttu-id="b6abe-130">Pour les organisations avec plusieurs locataires, vous pouvez exporter vos emplacements d'un client et l'importer dans un autre.</span><span class="sxs-lookup"><span data-stu-id="b6abe-130">For organizations with mulitple tenants, you can export your locations from one tenant and import it into another.</span></span> <span data-ttu-id="b6abe-131">Toutefois, vous devez supprimer toutes les données de la colonne ID avant d'importer.</span><span class="sxs-lookup"><span data-stu-id="b6abe-131">But you must remove all of the data in the Id column before you import.</span></span>
  
<span data-ttu-id="b6abe-132">Pour en savoir plus sur les champs requis et recommandés, consultez [la rubrique ajouter un emplacement](add-a-location.md).</span><span class="sxs-lookup"><span data-stu-id="b6abe-132">To find out more about required and recommended fields, see [Add a location](add-a-location.md).</span></span>

  

