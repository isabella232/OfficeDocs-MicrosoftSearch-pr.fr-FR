---
title: Créer Q&As
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
description: Ajoutez rapidement des réponses aux questions fréquemment posées à l'aide des outils d'importation dans le portail d'administration de Microsoft Search.
ms.openlocfilehash: 53f1d167948f6b621ad139620553df51b0cb91c2
ms.sourcegitcommit: 61b4b84e581d3df6045851fe6c9c1291853dea06
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/16/2019
ms.locfileid: "30068393"
---
# <a name="bulk-create-qas"></a><span data-ttu-id="05267-103">Créer Q&As</span><span class="sxs-lookup"><span data-stu-id="05267-103">Bulk create Q&As</span></span>

<span data-ttu-id="05267-p101">Téléchargez et utilisez le modèle. csv pour créer ou modifier en bloc Q&As. Il s'agit également d'un moyen simple d'enregistrer des Q&As brouillons qui nécessitent des modifications ou des mises à jour supplémentaires. Si vous devez modifier en bloc des Q&As existants, exportez-les à partir du portail d'administration, effectuez les modifications nécessaires, puis importez-les.</span><span class="sxs-lookup"><span data-stu-id="05267-p101">Download and use the .csv template to bulk create or bulk edit Q&As. It's also a simple way to bulk save draft Q&As that need additional edits or updates. If you need to bulk edit existing Q&As, export them from the Admin portal, make the necessary edits, and then import them.</span></span>
  
1. <span data-ttu-id="05267-107">Dans le coin supérieur droit de la section Q&As, cliquez sur **Importer** .</span><span class="sxs-lookup"><span data-stu-id="05267-107">In the upper-right corner of the Q&As section, click **Import**</span></span>
    
2. <span data-ttu-id="05267-108">Cliquez sur **Télécharger le modèle Q&A (. csv)** .</span><span class="sxs-lookup"><span data-stu-id="05267-108">Click **Download Q&A template (.csv)**</span></span>
    
3. <span data-ttu-id="05267-109">Enregistrer et ouvrir le fichier. csv</span><span class="sxs-lookup"><span data-stu-id="05267-109">Save and open the .csv file</span></span>
    
4. <span data-ttu-id="05267-110">Ajouter le contenu et les paramètres Q&A et enregistrer le fichier</span><span class="sxs-lookup"><span data-stu-id="05267-110">Add the Q&A content and settings and save the file</span></span>
    
5. <span data-ttu-id="05267-111">Dans le coin supérieur droit de la section Q&As, cliquez sur **Importer** .</span><span class="sxs-lookup"><span data-stu-id="05267-111">In the upper-right corner of the Q&As section, click **Import**</span></span>
    
6. <span data-ttu-id="05267-112">Dans le volet importer Q&As, cliquez sur **Parcourir** et naviguez jusqu'au fichier. csv que vous souhaitez importer.</span><span class="sxs-lookup"><span data-stu-id="05267-112">In the Import Q&As pane, click **Browse** and navigate to the .csv file you want to import</span></span> 
    
7. <span data-ttu-id="05267-113">Cliquez sur **Importer**</span><span class="sxs-lookup"><span data-stu-id="05267-113">Click **Import**</span></span>

# <a name="prevent-import-errors"></a><span data-ttu-id="05267-114">Empêcher les erreurs d'importation</span><span class="sxs-lookup"><span data-stu-id="05267-114">Prevent import errors</span></span>      
<span data-ttu-id="05267-p102">Vous obtiendrez une erreur si les données requises sont manquantes ou non valides. En fonction de l'erreur, un fichier journal peut être généré avec davantage d'informations sur les lignes et les colonnes qui doivent être corrigées. Effectuez les modifications nécessaires, puis réessayez d'importer le fichier.</span><span class="sxs-lookup"><span data-stu-id="05267-p102">You'll get an error if any required data is missing or invalid. Depending on the error, a log file may be generated with more information about the rows and columns that need to be corrected. Make any necessary edits, and try importing the file again.</span></span>

> [!NOTE]
> <span data-ttu-id="05267-118">Tant que toutes les erreurs ne sont pas résolues, vous ne pouvez pas créer ni modifier de Q&As.</span><span class="sxs-lookup"><span data-stu-id="05267-118">Until all errors are resolved, you can't create or edit any Q&As.</span></span> 

<span data-ttu-id="05267-119">Pour éviter les erreurs, assurez-vous que votre fichier d'importation est correctement mis en forme:</span><span class="sxs-lookup"><span data-stu-id="05267-119">To help prevent errors, make sure your import file is properly formatted:</span></span>
- <span data-ttu-id="05267-120">Inclut la ligne d'en-tête qui était dans le modèle d'importation.</span><span class="sxs-lookup"><span data-stu-id="05267-120">Includes the header row that was in the import template</span></span>
- <span data-ttu-id="05267-121">Inclut toutes les colonnes qui se trouvaient dans le modèle d'importation.</span><span class="sxs-lookup"><span data-stu-id="05267-121">Includes all columns that were in the import template</span></span>
- <span data-ttu-id="05267-122">L'ordre des colonnes est le même que celui du modèle d'importation.</span><span class="sxs-lookup"><span data-stu-id="05267-122">The column order is the same as the import template</span></span>
- <span data-ttu-id="05267-123">Ces colonnes peuvent être vides: ID, Last modified et Last modified by</span><span class="sxs-lookup"><span data-stu-id="05267-123">These columns can be empty: Id, Last Modified, and Last Modified By</span></span>
- <span data-ttu-id="05267-124">La colonne État ne peut pas être vide; cette information est requise</span><span class="sxs-lookup"><span data-stu-id="05267-124">The State column can't be empty, this information is required</span></span>  
<span data-ttu-id="05267-125">En fonction du champ d'État, Q&As sera enregistré en tant que brouillon, suggéré, programmé, ou il sera automatiquement publié.</span><span class="sxs-lookup"><span data-stu-id="05267-125">Based on the State field, Q&As will be saved as draft, suggested, scheduled, or they will be published automatically.</span></span>

<span data-ttu-id="05267-126">En outre, si vous incluez l'ID d'un Q&A existant, il sera remplacé par les informations contenues dans le fichier d'importation.</span><span class="sxs-lookup"><span data-stu-id="05267-126">Also, if you include the Id of an existing Q&A, it will be replaced with the information in the import file.</span></span>

<span data-ttu-id="05267-p103">Pour les organisations avec plusieurs locataires, vous pouvez exporter votre Q&As d'un client et l'importer dans un autre. Toutefois, vous devez supprimer toutes les données de la colonne ID avant d'importer.</span><span class="sxs-lookup"><span data-stu-id="05267-p103">For organizations with mulitple tenants, you can export your Q&As from one tenant and import it into another. But you must remove all of the data in the Id column before you import.</span></span>

<span data-ttu-id="05267-129">Pour en savoir plus sur les champs requis et recommandés, voir [Create Q&As](create-qas.md).</span><span class="sxs-lookup"><span data-stu-id="05267-129">To find out more about required and recommended fields, see [Create Q&As](create-qas.md).</span></span>

  

