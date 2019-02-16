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
ms.openlocfilehash: eb51b93ceaa560e5142ac46d316ba745c614fe34
ms.sourcegitcommit: 61b4b84e581d3df6045851fe6c9c1291853dea06
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/16/2019
ms.locfileid: "30068409"
---
# <a name="bulk-create-locations"></a><span data-ttu-id="7508d-103">Créer en bloc des emplacements</span><span class="sxs-lookup"><span data-stu-id="7508d-103">Bulk create locations</span></span>

<span data-ttu-id="7508d-104">Téléchargez et utilisez le modèle. csv pour créer, modifier et enregistrer en bloc des emplacements.</span><span class="sxs-lookup"><span data-stu-id="7508d-104">Download and use the .csv template to bulk create, edit, and save locations.</span></span> 
  
1. <span data-ttu-id="7508d-105">Dans le coin supérieur droit de la section emplacements, cliquez sur **Importer** .</span><span class="sxs-lookup"><span data-stu-id="7508d-105">In the upper-right corner of the Locations section, click **Import**</span></span>
    
2. <span data-ttu-id="7508d-106">Cliquez sur **Télécharger les emplacements (. csv)** .</span><span class="sxs-lookup"><span data-stu-id="7508d-106">Click **Download locations template (.csv)**</span></span>
    
3. <span data-ttu-id="7508d-107">Enregistrer et ouvrir le fichier. csv</span><span class="sxs-lookup"><span data-stu-id="7508d-107">Save and open the .csv file</span></span>
    
4. <span data-ttu-id="7508d-108">Ajouter le contenu de l'emplacement et enregistrer le fichier</span><span class="sxs-lookup"><span data-stu-id="7508d-108">Add the location content and save the file</span></span>
    
5. <span data-ttu-id="7508d-109">Dans le coin supérieur droit de la section emplacements, cliquez sur **Importer** .</span><span class="sxs-lookup"><span data-stu-id="7508d-109">In the upper-right corner of the Locations section, click **Import**</span></span>
    
6. <span data-ttu-id="7508d-110">Dans le volet importer des emplacements, cliquez sur **Parcourir** et naviguez jusqu'au fichier. csv que vous souhaitez importer.</span><span class="sxs-lookup"><span data-stu-id="7508d-110">In the Import locations pane, click **Browse** and navigate to the .csv file you want to import</span></span> 
    
7. <span data-ttu-id="7508d-111">Cliquez sur **Importer**</span><span class="sxs-lookup"><span data-stu-id="7508d-111">Click **Import**</span></span>

<span data-ttu-id="7508d-p101">Les champs des modèles d'emplacement d'importation et d'exportation sont les mêmes. Vous pouvez exporter, modifier en bloc et importer les modifications, ou commencer avec un modèle vide pour créer des emplacements en bloc. Pour modifier en bloc des emplacements existants, exportez-les à partir du portail d'administration, effectuez les modifications nécessaires, puis importez-les.</span><span class="sxs-lookup"><span data-stu-id="7508d-p101">The fields in the import and export locations templates are the same. You can export, bulk edit, and import the edits, or start with an empty template to bulk create new locations. To bulk edit existing locations, export them from the Admin portal, make the necessary edits, and then import them.</span></span>

# <a name="prevent-import-errors"></a><span data-ttu-id="7508d-115">Empêcher les erreurs d'importation</span><span class="sxs-lookup"><span data-stu-id="7508d-115">Prevent import errors</span></span>  
<span data-ttu-id="7508d-p102">Vous obtiendrez une erreur si les données requises sont manquantes ou non valides. En fonction de l'erreur, un fichier journal peut être généré avec davantage d'informations sur les lignes et les colonnes qui doivent être corrigées. Effectuez les modifications nécessaires, puis réessayez d'importer le fichier.</span><span class="sxs-lookup"><span data-stu-id="7508d-p102">You'll get an error if any required data is missing or invalid. Depending on the error, a log file may be generated with more information about the rows and columns that need to be corrected. Make any necessary edits, and try importing the file again.</span></span>
  
> [!NOTE]
> <span data-ttu-id="7508d-119">Tant que toutes les erreurs ne sont pas résolues, vous ne pouvez pas créer ni modifier d'emplacements.</span><span class="sxs-lookup"><span data-stu-id="7508d-119">Until all errors are resolved, you can't create or edit any locations.</span></span> 

<span data-ttu-id="7508d-120">Pour éviter les erreurs, assurez-vous que votre fichier d'importation est correctement mis en forme:</span><span class="sxs-lookup"><span data-stu-id="7508d-120">To help prevent errors, make sure your import file is properly formatted:</span></span>
- <span data-ttu-id="7508d-121">Inclut la ligne d'en-tête qui était dans le modèle d'importation.</span><span class="sxs-lookup"><span data-stu-id="7508d-121">Includes the header row that was in the import template</span></span>
- <span data-ttu-id="7508d-122">Inclut toutes les colonnes qui se trouvaient dans le modèle d'importation.</span><span class="sxs-lookup"><span data-stu-id="7508d-122">Includes all columns that were in the import template</span></span>
- <span data-ttu-id="7508d-123">L'ordre des colonnes est le même que celui du modèle d'importation.</span><span class="sxs-lookup"><span data-stu-id="7508d-123">The column order is the same as the import template</span></span>
- <span data-ttu-id="7508d-124">Ces colonnes peuvent être vides: ID, dernière modification, dernière modification par et lat/long.</span><span class="sxs-lookup"><span data-stu-id="7508d-124">These columns can be empty: Id, Last Modified, Last Modified By, and Lat/Long</span></span>  
<span data-ttu-id="7508d-125">Nous allons essayer de déterminer la table des adresses locales/longue en fonction de l'adresse si ce champ est vide.</span><span class="sxs-lookup"><span data-stu-id="7508d-125">We'll try to determine lat/long based on the address if that field is empty</span></span>
- <span data-ttu-id="7508d-126">La colonne État ne peut pas être vide; cette information est requise</span><span class="sxs-lookup"><span data-stu-id="7508d-126">The State column can't be empty, this information is required</span></span>  
<span data-ttu-id="7508d-127">En fonction du champ d'État, les emplacements seront enregistrés en tant que brouillon, suggéré, programmé, ou ils seront publiés automatiquement.</span><span class="sxs-lookup"><span data-stu-id="7508d-127">Based on the State field, locations will be saved as draft, suggested, scheduled, or they will be published automatically.</span></span>

<span data-ttu-id="7508d-128">En outre, si vous incluez l'ID d'un emplacement existant, il sera remplacé par les informations contenues dans le fichier d'importation.</span><span class="sxs-lookup"><span data-stu-id="7508d-128">Also, if you include the Id of an existing location, it will be replaced with the information in the import file.</span></span>

<span data-ttu-id="7508d-p103">Pour les organisations avec plusieurs locataires, vous pouvez exporter vos emplacements d'un client et l'importer dans un autre. Toutefois, vous devez supprimer toutes les données de la colonne ID avant d'importer.</span><span class="sxs-lookup"><span data-stu-id="7508d-p103">For organizations with mulitple tenants, you can export your locations from one tenant and import it into another. But you must remove all of the data in the Id column before you import.</span></span>
  
<span data-ttu-id="7508d-131">Pour en savoir plus sur les champs requis et recommandés, consultez [la rubrique ajouter un emplacement](add-a-location.md).</span><span class="sxs-lookup"><span data-stu-id="7508d-131">To find out more about required and recommended fields, see [Add a location](add-a-location.md).</span></span>

  

