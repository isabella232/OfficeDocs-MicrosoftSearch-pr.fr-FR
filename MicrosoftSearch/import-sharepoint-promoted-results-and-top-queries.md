---
title: Importer les requêtes les plus fréquentes et les résultats promus par SharePoint
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
description: Utilisez des requêtes de recherche de SharePoint afin de créer des résultats de travail pour la fonctionnalité Recherche Microsoft
ms.openlocfilehash: 6e55e2000792bdb576a18a0efeb353dc3ea13605
ms.sourcegitcommit: 3e91a6e70b48a0100adfed1b62ba79f2fd1735d2
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/13/2019
ms.locfileid: "33968450"
---
# <a name="import-sharepoint-promoted-results-and-top-queries"></a><span data-ttu-id="2f3ca-103">Importer les requêtes les plus fréquentes et les résultats promus par SharePoint</span><span class="sxs-lookup"><span data-stu-id="2f3ca-103">Import SharePoint promoted results and top queries</span></span>

> [!IMPORTANT]
> <span data-ttu-id="2f3ca-104">Les paramètres de Recherche Microsoft dans Bing sont désormais accessibles dans le Centre d’administration Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="2f3ca-104">Microsoft Search in Bing settings are now available in the Microsoft 365 admin center.</span></span> <span data-ttu-id="2f3ca-105">Commencez par [assigner des administrateurs de recherche](https://docs.microsoft.com/fr-FR/microsoftsearch/setup-microsoft-search#step-2-assign-search-admin-and-search-editor) dans votre centre d’administration.</span><span class="sxs-lookup"><span data-stu-id="2f3ca-105">Get started by [assigning search admins](https://docs.microsoft.com/en-us/microsoftsearch/setup-microsoft-search#step-2-assign-search-admin-and-search-editor) in your admin center.</span></span>
    
<span data-ttu-id="2f3ca-106">Pour vous aider à exploiter les requêtes des utilisateurs et les meilleurs résultats que vous avez créés dans SharePoint, la fonctionnalité Recherche Microsoft inclut deux outils permettant d’importer ces informations en tant que signets suggérés :</span><span class="sxs-lookup"><span data-stu-id="2f3ca-106">To leverage users' queries and Best Bets you've created in SharePoint, Microsoft Search includes two tools to import this information as suggested bookmarks:</span></span> 
  
## <a name="import-sharepoint-promoted-result-query-rules"></a><span data-ttu-id="2f3ca-107">Importer des règles de requête de résultats promus par SharePoint</span><span class="sxs-lookup"><span data-stu-id="2f3ca-107">Import SharePoint promoted result query rules</span></span>

<span data-ttu-id="2f3ca-108">Importez ces règles, précédemment appelées Meilleurs résultats, en tant que signets suggérés.</span><span class="sxs-lookup"><span data-stu-id="2f3ca-108">Import these rules, previously called Best Bets, as suggested bookmarks.</span></span> <span data-ttu-id="2f3ca-109">Pour les rendre disponibles à vos utilisateurs, publiez-les.</span><span class="sxs-lookup"><span data-stu-id="2f3ca-109">To make them available to your users, publish them.</span></span> <span data-ttu-id="2f3ca-110">Le durée de la publication varie en fonction du nombre de signets que vous sélectionnez.</span><span class="sxs-lookup"><span data-stu-id="2f3ca-110">Publishing time varies based on the number of bookmarks you select.</span></span>
  
## <a name="import-top-sharepoint-queries-using-powershell"></a><span data-ttu-id="2f3ca-111">Importer des principales requêtes SharePoint en utilisant PowerShell</span><span class="sxs-lookup"><span data-stu-id="2f3ca-111">Import top SharePoint queries using PowerShell</span></span>

- <span data-ttu-id="2f3ca-112">Téléchargez les principales requêtes à partir de votre installation SharePoint.</span><span class="sxs-lookup"><span data-stu-id="2f3ca-112">Download the top queries from your SharePoint.</span></span> <span data-ttu-id="2f3ca-113">Le script PowerShell vous invitent à entrer des vos informations d’identification d’administrateur SharePoint.</span><span class="sxs-lookup"><span data-stu-id="2f3ca-113">The PowerShell script will prompt you for your SharePoint administrator credentials.</span></span>
    
- <span data-ttu-id="2f3ca-114">Effectuez une recherche dans SharePoint pour chacune des requêtes supérieures pour obtenir le résultat de recherche supérieure.</span><span class="sxs-lookup"><span data-stu-id="2f3ca-114">Run a SharePoint search for each of the top queries to get the top search result.</span></span>
    
- <span data-ttu-id="2f3ca-115">Ajouter des signets suggérés pour le portail d’administration.</span><span class="sxs-lookup"><span data-stu-id="2f3ca-115">Add suggested bookmarks to the Admin portal.</span></span>
    
- <span data-ttu-id="2f3ca-116">Vos principales requêtes SharePoint sont d’excellents choix pour une utilisation de signets.</span><span class="sxs-lookup"><span data-stu-id="2f3ca-116">Your top SharePoint queries are excellent candidates for bookmarks.</span></span> <span data-ttu-id="2f3ca-117">Utilisez le script PowerShell pour les importer en tant que signets suggérés.</span><span class="sxs-lookup"><span data-stu-id="2f3ca-117">Use the PowerShell script to import them as suggested bookmarks.</span></span> <span data-ttu-id="2f3ca-118">Ce script pourra:</span><span class="sxs-lookup"><span data-stu-id="2f3ca-118">This script will:</span></span>
    
<span data-ttu-id="2f3ca-119">Télécharger le script et ouvrir le fichier LISEZMOI pour plus d’informations sur la configuration requise, les exemples et les paramètres disponibles.</span><span class="sxs-lookup"><span data-stu-id="2f3ca-119">For information about requirements, examples, and available parameters, download the script and review the README file.</span></span> <span data-ttu-id="2f3ca-120">Après l’exécution du script PowerShell, un administrateur ou éditeur doit passer en revue les signets suggérés et rendre les modifications nécessaires avant qu’elles ne soient publiées.</span><span class="sxs-lookup"><span data-stu-id="2f3ca-120">After the PowerShell script runs, an admin or editor should review the suggested bookmarks and make any necessary edits before they're published.</span></span>

  

