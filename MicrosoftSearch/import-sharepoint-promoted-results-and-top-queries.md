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
ROBOTS: NOINDEX
description: Utiliser des requêtes de recherche à partir de SharePoint pour créer des résultats de travail pour Microsoft Search
ms.openlocfilehash: 59d133aceb15c8f1fa75ecc3f35522def4201d0a
ms.sourcegitcommit: 9a9d24b4b7a6f3e80b89086d29fd369ebded0619
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/10/2019
ms.locfileid: "34810645"
---
# <a name="import-sharepoint-promoted-results-and-top-queries"></a>Importer les résultats et principales requêtes mis en avant par SharePoint

> [!IMPORTANT]
> Cet article s’applique au portail d’administration de Microsoft Search dans Bing. Nous allons déplacer le portail vers le centre d’administration Microsoft 365, puis il sera supprimé. Nous vous recommandons d’utiliser le centre d’administration Microsoft 365 pour commencer. [Vue d’ensemble de Microsoft Search](overview-microsoft-search.md).
    
Pour tirer parti des requêtes et des meilleurs résultats que vous avez créés dans SharePoint, Microsoft Search inclut deux outils pour importer ces informations en tant que signets suggérés: 
  
## <a name="import-sharepoint-promoted-result-query-rules"></a>Importer des règles de requête de résultats promus SharePoint

Importez ces règles, précédemment appelées meilleurs résultats, sous la forme de signets suggérés. Pour les rendre accessibles à vos utilisateurs, publiez-les. Le temps de publication varie en fonction du nombre de signets que vous sélectionnez.
  
## <a name="import-top-sharepoint-queries-using-powershell"></a>Importer les requêtes SharePoint les plus courantes à l’aide de PowerShell

- Téléchargez les requêtes les plus populaires à partir de votre SharePoint. Le script PowerShell vous invite à entrer vos informations d’identification d’administrateur SharePoint.
    
- Exécutez une recherche SharePoint pour chacune des requêtes les plus fréquentes afin d’obtenir le résultat de recherche le plus élevé.
    
- Ajouter des signets suggérés au portail d’administration.
    
- Vos requêtes SharePoint les plus fréquentes sont des candidats excellents pour les signets. Utilisez le script PowerShell pour les importer sous forme de signets suggérés. Ce script effectue les tâches suivantes:
    - Ajoute des signets suggérés basés sur les requêtes principales de SharePoint pour améliorer la couverture des signets Microsoft Search. Ce script télécharge les requêtes principales accessibles à partir du portail d’administration SharePoint, puis les télécharge sous forme de signets suggérés pour un administrateur afin qu’il les examine dans le portail d’administration de Microsoft Search.
    - Par défaut, le script ajoute des signets suggérés au client donné pour tous les mois disponibles. Il obtient les requêtes les plus populaires à partir d’un site Web d’administration SharePoint donné et les ajoute à Microsoft Search en tant que signets suggérés. Les signets suggérés ont besoin d’un administrateur/éditeur pour les approuver dans le portail d’administration avant d’être publiés. Lorsque vous exécutez ce script, vous êtes invité à entrer les informations d’identification pour accéder au portail d’administration de Microsoft Search.
    - Le script permet de spécifier des paramètres supplémentaires. Vous pouvez, par exemple, ajouter des signets suggérés au client donné pour les requêtes Top N dans chaque mois disponible.
    - Si vous le souhaitez, vous pouvez ajouter des signets suggérés au client donné pendant les mois de l’année donnée. Cette commande obtient les requêtes les plus fréquentes pour la période donnée à partir du site Web d’administration SharePoint et les ajoute à Microsoft Search en tant que signets suggérés.
    - Il existe également de nombreuses autres options et modes de commande: Télécharger les requêtes les plus fréquentes à partir de SharePoint vers un dossier spécifique, exécuter le script en mode sans échec, exécuter le script en mode détaillé et un mode de débogage.
    - Téléchargez le script [ici](https://www.bingforbusiness.com/distribution/SharepointTopQueryBookmarks.zip). 

Pour plus d’informations sur les conditions requises, les exemples et les paramètres disponibles, téléchargez le script et passez en revue le fichier Lisez-moi. Une fois le script PowerShell exécuté, un administrateur ou un éditeur doit passer en revue les signets suggérés et apporter les modifications nécessaires avant qu’il ne soit publié.