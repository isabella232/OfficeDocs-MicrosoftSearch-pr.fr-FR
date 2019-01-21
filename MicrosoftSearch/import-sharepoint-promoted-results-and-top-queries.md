---
title: Importation SharePoint promu résultats et des requêtes les plus fréquentes
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
ms.sourcegitcommit: bf52cc63b75f2e0324a716fe65da47702956b722
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/18/2019
ms.locfileid: "29378652"
---
# <a name="import-sharepoint-promoted-results-and-top-queries"></a><span data-ttu-id="c7bab-103">Importation SharePoint promu résultats et des requêtes les plus fréquentes</span><span class="sxs-lookup"><span data-stu-id="c7bab-103">Import SharePoint promoted results and top queries</span></span>

<span data-ttu-id="c7bab-104">Pour tirer parti des requêtes des utilisateurs et les meilleurs résultats que vous avez créé dans SharePoint, Microsoft Search inclut deux outils pour importer ces informations sous forme de signets suggérées :</span><span class="sxs-lookup"><span data-stu-id="c7bab-104">To leverage users' queries and Best Bets you've created in SharePoint, Microsoft Search includes two tools to import this information as suggested bookmarks:</span></span> 
  
## <a name="import-sharepoint-promoted-result-query-rules"></a><span data-ttu-id="c7bab-105">Importation SharePoint promu des règles de requête de résultats</span><span class="sxs-lookup"><span data-stu-id="c7bab-105">Import SharePoint promoted result query rules</span></span>

<span data-ttu-id="c7bab-p101">Importez ces règles, précédemment appelé les meilleurs résultats, sous forme de signets suggérées. Pour les rendre disponibles pour vos utilisateurs, les publier. Durée de la publication varie en fonction du nombre de signets que vous sélectionnez.</span><span class="sxs-lookup"><span data-stu-id="c7bab-p101">Import these rules, previously called Best Bets, as suggested bookmarks. To make them available to your users, publish them. Publishing time varies based on the number of bookmarks you select.</span></span>
  
## <a name="import-top-sharepoint-queries-using-powershell"></a><span data-ttu-id="c7bab-109">Importer des requêtes SharePoint principales à l’aide de PowerShell</span><span class="sxs-lookup"><span data-stu-id="c7bab-109">Import top SharePoint queries using PowerShell</span></span>

- <span data-ttu-id="c7bab-p102">Télécharger les requêtes les plus fréquentes à partir de SharePoint. Le script PowerShell vous demandera de vos informations d’identification d’administrateur SharePoint.</span><span class="sxs-lookup"><span data-stu-id="c7bab-p102">Download the top queries from your SharePoint. The PowerShell script will prompt you for your SharePoint administrator credentials.</span></span>
    
- <span data-ttu-id="c7bab-112">Exécuter une recherche de SharePoint pour chacune des requêtes supérieurs pour obtenir le résultat de recherche.</span><span class="sxs-lookup"><span data-stu-id="c7bab-112">Run a SharePoint search for each of the top queries to get the top search result.</span></span>
    
- <span data-ttu-id="c7bab-113">Ajouter des signets suggérés pour le portail d’administration.</span><span class="sxs-lookup"><span data-stu-id="c7bab-113">Add suggested bookmarks to the Admin portal.</span></span>
    
- <span data-ttu-id="c7bab-p103">Vos requêtes SharePoint les plus fréquentes sont une excellente candidats pour les signets. Utilisez le script PowerShell pour les importer sous forme de signets suggérées. Ce script est :</span><span class="sxs-lookup"><span data-stu-id="c7bab-p103">Your top SharePoint queries are excellent candidates for bookmarks. Use the PowerShell script to import them as suggested bookmarks. This script will:</span></span>
    
<span data-ttu-id="c7bab-p104">Pour plus d’informations sur la configuration requise, des exemples et paramètres disponibles, téléchargez le script et consultez le fichier Lisez-moi. Après le script PowerShell s’exécute, un administrateur ou un éditeur doit consulter les signets suggérées et apportez les modifications nécessaires avant leur publication.</span><span class="sxs-lookup"><span data-stu-id="c7bab-p104">For information about requirements, examples, and available parameters, download the script and review the README file. After the PowerShell script runs, an admin or editor should review the suggested bookmarks and make any necessary edits before they're published.</span></span>

  

