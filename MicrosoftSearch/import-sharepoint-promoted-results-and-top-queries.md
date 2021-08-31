---
title: Importer les résultats et principales requêtes mis en avant par SharePoint
ms.author: dawholl
author: dawholl
manager: kellis
ms.audience: Admin
ms.topic: reference
ms.service: mssearch
ms.localizationpriority: medium
search.appverid:
- BFB160
- MET150
- MOE150
ms.assetid: 3d2a1498-174e-4214-9cf1-8b58cce5a872
ROBOTS: NOINDEX
description: Utiliser des requêtes de recherche à partir SharePoint pour créer des résultats de travail pour Recherche Microsoft
ms.openlocfilehash: 13ea273ce20f6aae3376468a638c27dedddf8cdc
ms.sourcegitcommit: cc9d743bcf5e998720ce9cd6eefb4061d913dc65
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/30/2021
ms.locfileid: "58702110"
---
# <a name="import-sharepoint-promoted-results-and-top-queries"></a>Importer les résultats et principales requêtes mis en avant par SharePoint

> [!IMPORTANT]
> Cet article s’applique aux Recherche Microsoft dans le portail Bing’administration. Nous déplaçons le portail vers le Centre d’administration Microsoft 365. Nous supprimerons ensuite la fonctionnalité Recherche Microsoft du portail Bing. Pour commencer, nous vous suggérons d’utiliser le Centre d’administration Microsoft 365. [Vue d’ensemble de la fonctionnalité Recherche Microsoft](overview-microsoft-search.md).
    
Pour tirer parti des requêtes des utilisateurs et des meilleurs meilleurs résultat que vous avez créés dans SharePoint, Recherche Microsoft inclut deux outils pour importer ces informations en tant que signets suggérés : 
  
## <a name="import-sharepoint-promoted-result-query-rules"></a>Importer SharePoint règles de requête de résultats promues

Importez ces règles, précédemment appelées Meilleurs résultats, comme les signets suggérés. Pour les rendre accessibles à vos utilisateurs, publiez-les. Le temps de publication varie en fonction du nombre de signets que vous sélectionnez.
  
## <a name="import-top-sharepoint-queries-using-powershell"></a>Importer les requêtes SharePoint à l’aide de PowerShell

- Téléchargez les principales requêtes à partir de votre SharePoint. Le script PowerShell vous invite à obtenir vos informations d’identification SharePoint administrateur.
    
- Exécutez une SharePoint recherche pour chacune des requêtes les plus hautes afin d’obtenir le meilleur résultat de recherche.
    
- Ajoutez des signets suggérés au portail d’administration.
    
- Vos requêtes SharePoint sont d’excellents candidats pour les signets. Utilisez le script PowerShell pour les importer en tant que signets suggérés. Ce script fonctionne comme suit :
    - Ajoute des signets suggérés en fonction SharePoint requêtes principales pour améliorer Recherche Microsoft couverture des signets. Ce script télécharge les principales requêtes accessibles à partir du portail d’administration SharePoint, puis les télécharge en tant que signets suggérés pour qu’un administrateur les examine dans le portail d’administration Recherche Microsoft.
    - Par défaut, le script ajoute des signets suggérés au client donné pour tous les mois disponibles. Il obtient les principales requêtes d’un site web SharePoint’administration et les ajoute Recherche Microsoft sous la Recherche Microsoft signets suggérés. Les signets suggérés ont besoin d’un administrateur/éditeur pour les approuver dans le portail d’administration avant d’être publiés. Lorsque vous exécutez ce script, vous êtes invité à obtenir des informations d’identification pour accéder Recherche Microsoft portail d’administration.
    - Le script permet de spécifier des paramètres supplémentaires. Vous pouvez, par exemple, ajouter des signets suggérés à un client donné pour les requêtes N principales dans chacun des mois disponibles.
    - Si vous le souhaitez, vous pouvez ajouter des signets suggérés à un client donné pour les mois de l’année donnée. Cette commande obtient les principales requêtes pour la période donnée à partir SharePoint site web de l’administrateur et les ajoute Recherche Microsoft sous la Recherche Microsoft signets suggérés.
    - En outre, il existe de nombreuses autres options et modes de commande : télécharger les requêtes principales à partir de SharePoint dans un dossier spécifié, exécuter le script en mode Coffre, exécuter le script en mode détaillée et un mode débogage.
    - Téléchargez le script [ici.](https://www.bingforbusiness.com/distribution/SharepointTopQueryBookmarks.zip) 

Pour plus d’informations sur les conditions requises, les exemples et les paramètres disponibles, téléchargez le script et examinez le fichier README. Une fois le script PowerShell s’exécute, un administrateur ou un éditeur doit examiner les signets suggérés et apporter les modifications nécessaires avant leur publication.