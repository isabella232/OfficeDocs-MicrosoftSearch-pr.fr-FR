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
description: Créer un grand nombre de signets à la fois avec les outils d'importation pour le portail d'administration de Microsoft Search
ms.openlocfilehash: 07694de1f546a1431f371fa24ffc5721ea66337c
ms.sourcegitcommit: 61b4b84e581d3df6045851fe6c9c1291853dea06
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/16/2019
ms.locfileid: "30068401"
---
# <a name="bulk-create-bookmarks"></a><span data-ttu-id="6a337-103">Créer en bloc des signets</span><span class="sxs-lookup"><span data-stu-id="6a337-103">Bulk create bookmarks</span></span>

<span data-ttu-id="6a337-p101">Téléchargez et utilisez le modèle. csv pour créer, modifier et enregistrer des signets en bloc. Pour modifier en bloc des signets existants, exportez-les à partir du portail d'administration, effectuez les modifications nécessaires, puis importez-les.</span><span class="sxs-lookup"><span data-stu-id="6a337-p101">Download and use the .csv template to bulk create, edit, and save bookmarks. To bulk edit existing bookmarks, export them from the Admin portal, make the necessary edits, and then import them.</span></span>
  
1. <span data-ttu-id="6a337-106">Dans le coin supérieur droit de la section signets, cliquez sur **Importer** .</span><span class="sxs-lookup"><span data-stu-id="6a337-106">In the upper-right corner of the Bookmarks section, click **Import**</span></span>
    
2. <span data-ttu-id="6a337-107">Cliquez sur **Télécharger le modèle de signets (. csv)** .</span><span class="sxs-lookup"><span data-stu-id="6a337-107">Click **Download bookmarks template (.csv)**</span></span>
    
3. <span data-ttu-id="6a337-108">Enregistrer et ouvrir le fichier. csv</span><span class="sxs-lookup"><span data-stu-id="6a337-108">Save and open the .csv file</span></span>
    
4. <span data-ttu-id="6a337-109">Ajouter le contenu et les paramètres du signet et enregistrer le fichier</span><span class="sxs-lookup"><span data-stu-id="6a337-109">Add the bookmark content and settings and save the file</span></span>
    
5. <span data-ttu-id="6a337-110">Dans le coin supérieur droit de la section signets, cliquez sur **Importer** .</span><span class="sxs-lookup"><span data-stu-id="6a337-110">In the upper-right corner of the Bookmarks section, click **Import**</span></span>
    
6. <span data-ttu-id="6a337-111">Dans le volet importer les signets, cliquez sur **Parcourir** et naviguez jusqu'au fichier. csv que vous souhaitez importer.</span><span class="sxs-lookup"><span data-stu-id="6a337-111">In the Import bookmarks pane, click **Browse** and navigate to the .csv file you want to import</span></span> 
    
7. <span data-ttu-id="6a337-112">Cliquez sur **Importer**</span><span class="sxs-lookup"><span data-stu-id="6a337-112">Click **Import**</span></span>

# <a name="prevent-import-errors"></a><span data-ttu-id="6a337-113">Empêcher les erreurs d'importation</span><span class="sxs-lookup"><span data-stu-id="6a337-113">Prevent import errors</span></span>      
<span data-ttu-id="6a337-p102">Vous obtiendrez une erreur si les données requises sont manquantes ou non valides. En fonction de l'erreur, un fichier journal peut être généré avec davantage d'informations sur les lignes et les colonnes qui doivent être corrigées. Effectuez les modifications nécessaires, puis réessayez d'importer le fichier.</span><span class="sxs-lookup"><span data-stu-id="6a337-p102">You'll get an error if any required data is missing or invalid. Depending on the error, a log file may be generated with more information about the rows and columns that need to be corrected. Make any necessary edits, and try importing the file again.</span></span>

> [!NOTE]
> <span data-ttu-id="6a337-117">Tant que toutes les erreurs ne sont pas résolues, vous ne pouvez pas créer ni modifier de signets.</span><span class="sxs-lookup"><span data-stu-id="6a337-117">Until all errors are resolved, you can't create or edit any bookmarks.</span></span> 

<span data-ttu-id="6a337-118">Pour éviter les erreurs, assurez-vous que votre fichier d'importation est correctement mis en forme:</span><span class="sxs-lookup"><span data-stu-id="6a337-118">To help prevent errors, make sure your import file is properly formatted:</span></span>
- <span data-ttu-id="6a337-119">Inclut la ligne d'en-tête qui était dans le modèle d'importation.</span><span class="sxs-lookup"><span data-stu-id="6a337-119">Includes the header row that was in the import template</span></span>
- <span data-ttu-id="6a337-120">Inclut toutes les colonnes qui se trouvaient dans le modèle d'importation.</span><span class="sxs-lookup"><span data-stu-id="6a337-120">Includes all columns that were in the import template</span></span>
- <span data-ttu-id="6a337-121">L'ordre des colonnes est le même que celui du modèle d'importation.</span><span class="sxs-lookup"><span data-stu-id="6a337-121">The column order is the same as the import template</span></span>
- <span data-ttu-id="6a337-122">Ces colonnes peuvent être vides: ID, Last modified et Last modified by</span><span class="sxs-lookup"><span data-stu-id="6a337-122">These columns can be empty: Id, Last Modified, and Last Modified By</span></span>
- <span data-ttu-id="6a337-123">La colonne État ne peut pas être vide; cette information est requise</span><span class="sxs-lookup"><span data-stu-id="6a337-123">The State column can't be empty, this information is required</span></span>  
<span data-ttu-id="6a337-124">En fonction du champ d'État, les signets seront enregistrés en tant que brouillon, suggéré, programmé ou ils seront publiés automatiquement.</span><span class="sxs-lookup"><span data-stu-id="6a337-124">Based on the State field, bookmarks will be saved as draft, suggested, scheduled, or they will be published automatically.</span></span>

<span data-ttu-id="6a337-125">En outre, si vous incluez l'ID d'un signet existant, il sera remplacé par les informations contenues dans le fichier d'importation.</span><span class="sxs-lookup"><span data-stu-id="6a337-125">Also, if you include the Id of an existing bookmark, it will be replaced with the information in the import file.</span></span>

<span data-ttu-id="6a337-p103">Pour les organisations avec plusieurs locataires, vous pouvez exporter vos signets d'un client et l'importer dans un autre. Toutefois, vous devez supprimer toutes les données de la colonne ID avant d'importer.</span><span class="sxs-lookup"><span data-stu-id="6a337-p103">For organizations with mulitple tenants, you can export your bookmarks from one tenant and import it into another. But you must remove all of the data in the Id column before you import.</span></span>

<span data-ttu-id="6a337-128">Pour en savoir plus sur les champs requis et recommandés, consultez la rubrique [création](create-bookmarks.md)de signets.</span><span class="sxs-lookup"><span data-stu-id="6a337-128">To find out more about required and recommended fields, see [Create bookmarks](create-bookmarks.md).</span></span>
