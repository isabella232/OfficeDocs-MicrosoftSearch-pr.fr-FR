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
ROBOTS: NOINDEX
description: Utilisez des requêtes de recherche de SharePoint afin de créer des résultats de travail pour la fonctionnalité Recherche Microsoft
ms.openlocfilehash: 1538c57a7b4138b36fe62e3076feb58d746b2b3e
ms.sourcegitcommit: be2e837d9b087bffe6ce40d72d7ae58a8fcdf3fe
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/30/2019
ms.locfileid: "34591601"
---
# <a name="import-sharepoint-promoted-results-and-top-queries"></a><span data-ttu-id="dd2e2-103">Importer les requêtes les plus fréquentes et les résultats promus par SharePoint</span><span class="sxs-lookup"><span data-stu-id="dd2e2-103">Import SharePoint promoted results and top queries</span></span>

> [!IMPORTANT]
> <span data-ttu-id="dd2e2-104">Cet article s’applique à la fonctionnalité Recherche Microsoft dans le portail d’administration Bing.</span><span class="sxs-lookup"><span data-stu-id="dd2e2-104">This article applies to the Microsoft Search in Bing admin portal.</span></span> <span data-ttu-id="dd2e2-105">Nous déplaçons le portail vers le centre d’administration Microsoft 365. Ensuite, nous le supprimerons.</span><span class="sxs-lookup"><span data-stu-id="dd2e2-105">We’re moving the portal to the Microsoft 365 admin center, and then it will be removed.</span></span> <span data-ttu-id="dd2e2-106">Pour commencer, nous vous suggérons d’utiliser le centre d’administration Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="dd2e2-106">We recommend that you use the Microsoft 365 admin center to get started.</span></span> <span data-ttu-id="dd2e2-107">[Vue d’ensemble de la fonctionnalité Recherche Microsoft](overview-microsoft-search.md).</span><span class="sxs-lookup"><span data-stu-id="dd2e2-107">[Overview of Microsoft Search](overview-microsoft-search.md)</span></span>
    
<span data-ttu-id="dd2e2-108">Pour vous aider à exploiter les requêtes des utilisateurs et les meilleurs résultats que vous avez créés dans SharePoint, la fonctionnalité Recherche Microsoft inclut deux outils permettant d’importer ces informations en tant que signets suggérés :</span><span class="sxs-lookup"><span data-stu-id="dd2e2-108">To leverage users' queries and Best Bets you've created in SharePoint, Microsoft Search includes two tools to import this information as suggested bookmarks:</span></span> 
  
## <a name="import-sharepoint-promoted-result-query-rules"></a><span data-ttu-id="dd2e2-109">Importer des règles de requête de résultats promus par SharePoint</span><span class="sxs-lookup"><span data-stu-id="dd2e2-109">Import SharePoint promoted result query rules</span></span>

<span data-ttu-id="dd2e2-110">Importez ces règles, précédemment appelées Meilleurs résultats, en tant que signets suggérés.</span><span class="sxs-lookup"><span data-stu-id="dd2e2-110">Import these rules, previously called Best Bets, as suggested bookmarks.</span></span> <span data-ttu-id="dd2e2-111">Pour les rendre disponibles à vos utilisateurs, publiez-les.</span><span class="sxs-lookup"><span data-stu-id="dd2e2-111">To make them available to your users, publish them.</span></span> <span data-ttu-id="dd2e2-112">Le durée de la publication varie en fonction du nombre de signets que vous sélectionnez.</span><span class="sxs-lookup"><span data-stu-id="dd2e2-112">Publishing time varies based on the number of bookmarks you select.</span></span>
  
## <a name="import-top-sharepoint-queries-using-powershell"></a><span data-ttu-id="dd2e2-113">Importer des principales requêtes SharePoint en utilisant PowerShell</span><span class="sxs-lookup"><span data-stu-id="dd2e2-113">Import top SharePoint queries using PowerShell</span></span>

- <span data-ttu-id="dd2e2-114">Téléchargez les principales requêtes à partir de votre installation SharePoint.</span><span class="sxs-lookup"><span data-stu-id="dd2e2-114">Download the top queries from your SharePoint.</span></span> <span data-ttu-id="dd2e2-115">Le script PowerShell vous invitent à entrer des vos informations d’identification d’administrateur SharePoint.</span><span class="sxs-lookup"><span data-stu-id="dd2e2-115">The PowerShell script will prompt you for your SharePoint administrator credentials.</span></span>
    
- <span data-ttu-id="dd2e2-116">Effectuez une recherche dans SharePoint pour chacune des requêtes supérieures pour obtenir le résultat de recherche supérieure.</span><span class="sxs-lookup"><span data-stu-id="dd2e2-116">Run a SharePoint search for each of the top queries to get the top search result.</span></span>
    
- <span data-ttu-id="dd2e2-117">Ajouter des signets suggérés pour le portail d’administration.</span><span class="sxs-lookup"><span data-stu-id="dd2e2-117">Add suggested bookmarks to the Admin portal.</span></span>
    
- <span data-ttu-id="dd2e2-118">Vos principales requêtes SharePoint sont d’excellents choix pour une utilisation de signets.</span><span class="sxs-lookup"><span data-stu-id="dd2e2-118">Your top SharePoint queries are excellent candidates for bookmarks.</span></span> <span data-ttu-id="dd2e2-119">Utilisez le script PowerShell pour les importer en tant que signets suggérés.</span><span class="sxs-lookup"><span data-stu-id="dd2e2-119">Use the PowerShell script to import them as suggested bookmarks.</span></span> <span data-ttu-id="dd2e2-120">Ce script pourra:</span><span class="sxs-lookup"><span data-stu-id="dd2e2-120">This script will:</span></span>
    
<span data-ttu-id="dd2e2-121">Télécharger le script et ouvrir le fichier LISEZMOI pour plus d’informations sur la configuration requise, les exemples et les paramètres disponibles.</span><span class="sxs-lookup"><span data-stu-id="dd2e2-121">For information about requirements, examples, and available parameters, download the script and review the README file.</span></span> <span data-ttu-id="dd2e2-122">Après l’exécution du script PowerShell, un administrateur ou éditeur doit passer en revue les signets suggérés et rendre les modifications nécessaires avant qu’elles ne soient publiées.</span><span class="sxs-lookup"><span data-stu-id="dd2e2-122">After the PowerShell script runs, an admin or editor should review the suggested bookmarks and make any necessary edits before they're published.</span></span>

  

