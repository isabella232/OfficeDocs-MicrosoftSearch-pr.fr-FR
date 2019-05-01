---
title: Importer les résultats et principales requêtes mis en avant par SharePoint
ms.author: dawholl
author: dawholl
manager: kellis
ms.date: 9/8/2018
ms.audience: Admin
ms.topic: reference
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
ms.assetid: 3d2a1498-174e-4214-9cf1-8b58cce5a872
description: Utiliser des requêtes de recherche à partir de SharePoint pour créer des résultats de travail pour Microsoft Search
ms.openlocfilehash: f4fa4354fed667800c1cdcf63c86f59d736c342a
ms.sourcegitcommit: a5fd9d4f46bbb7c539630735ac16e0c786939e5d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/01/2019
ms.locfileid: "33508752"
---
# <a name="import-sharepoint-promoted-results-and-top-queries"></a><span data-ttu-id="036fd-103">Importer les résultats et principales requêtes mis en avant par SharePoint</span><span class="sxs-lookup"><span data-stu-id="036fd-103">Import SharePoint promoted results and top queries</span></span>

<span data-ttu-id="036fd-104">Pour tirer parti des requêtes et des meilleurs résultats que vous avez créés dans SharePoint, Microsoft Search inclut deux outils pour importer ces informations en tant que signets suggérés:</span><span class="sxs-lookup"><span data-stu-id="036fd-104">To leverage users' queries and Best Bets you've created in SharePoint, Microsoft Search includes two tools to import this information as suggested bookmarks:</span></span> 
  
## <a name="import-sharepoint-promoted-result-query-rules"></a><span data-ttu-id="036fd-105">Importer des règles de requête de résultats promus SharePoint</span><span class="sxs-lookup"><span data-stu-id="036fd-105">Import SharePoint promoted result query rules</span></span>

<span data-ttu-id="036fd-106">ImPortez ces règles, précédemment appelées meilleurs résultats, sous la forme de signets suggérés.</span><span class="sxs-lookup"><span data-stu-id="036fd-106">Import these rules, previously called Best Bets, as suggested bookmarks.</span></span> <span data-ttu-id="036fd-107">Pour les rendre accessibles à vos utilisateurs, publiez-les.</span><span class="sxs-lookup"><span data-stu-id="036fd-107">To make them available to your users, publish them.</span></span> <span data-ttu-id="036fd-108">Le temps de publication varie en fonction du nombre de signets que vous sélectionnez.</span><span class="sxs-lookup"><span data-stu-id="036fd-108">Publishing time varies based on the number of bookmarks you select.</span></span>
  
## <a name="import-top-sharepoint-queries-using-powershell"></a><span data-ttu-id="036fd-109">Importer les requêtes SharePoint les plus courantes à l'aide de PowerShell</span><span class="sxs-lookup"><span data-stu-id="036fd-109">Import top SharePoint queries using PowerShell</span></span>

- <span data-ttu-id="036fd-110">Téléchargez les requêtes les plus populaires à partir de votre SharePoint.</span><span class="sxs-lookup"><span data-stu-id="036fd-110">Download the top queries from your SharePoint.</span></span> <span data-ttu-id="036fd-111">Le script PowerShell vous invite à entrer vos informations d'identification d'administrateur SharePoint.</span><span class="sxs-lookup"><span data-stu-id="036fd-111">The PowerShell script will prompt you for your SharePoint administrator credentials.</span></span>
    
- <span data-ttu-id="036fd-112">Exécutez une recherche SharePoint pour chacune des requêtes les plus fréquentes afin d'obtenir le résultat de recherche le plus élevé.</span><span class="sxs-lookup"><span data-stu-id="036fd-112">Run a SharePoint search for each of the top queries to get the top search result.</span></span>
    
- <span data-ttu-id="036fd-113">Ajouter des signets suggérés au portail d'administration.</span><span class="sxs-lookup"><span data-stu-id="036fd-113">Add suggested bookmarks to the Admin portal.</span></span>
    
- <span data-ttu-id="036fd-114">Vos requêtes SharePoint les plus fréquentes sont des candidats excellents pour les signets.</span><span class="sxs-lookup"><span data-stu-id="036fd-114">Your top SharePoint queries are excellent candidates for bookmarks.</span></span> <span data-ttu-id="036fd-115">Utilisez le script PowerShell pour les importer sous forme de signets suggérés.</span><span class="sxs-lookup"><span data-stu-id="036fd-115">Use the PowerShell script to import them as suggested bookmarks.</span></span> <span data-ttu-id="036fd-116">Ce script:</span><span class="sxs-lookup"><span data-stu-id="036fd-116">This script will:</span></span>
    
<span data-ttu-id="036fd-117">Pour plus d'informations sur les conditions requises, les exemples et les paramètres disponibles, téléchargez le script et passez en revue le fichier Lisez-moi.</span><span class="sxs-lookup"><span data-stu-id="036fd-117">For information about requirements, examples, and available parameters, download the script and review the README file.</span></span> <span data-ttu-id="036fd-118">Une fois le script PowerShell exécuté, un administrateur ou un éditeur doit passer en revue les signets suggérés et apporter les modifications nécessaires avant qu'il ne soit publié.</span><span class="sxs-lookup"><span data-stu-id="036fd-118">After the PowerShell script runs, an admin or editor should review the suggested bookmarks and make any necessary edits before they're published.</span></span>

  

