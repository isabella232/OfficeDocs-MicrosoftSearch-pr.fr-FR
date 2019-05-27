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
# <a name="import-sharepoint-promoted-results-and-top-queries"></a>Importer les requêtes les plus fréquentes et les résultats promus par SharePoint

> [!IMPORTANT]
> Les paramètres de Recherche Microsoft dans Bing sont désormais accessibles dans le Centre d’administration Microsoft 365. Commencez par [assigner des administrateurs de recherche](https://docs.microsoft.com/fr-FR/microsoftsearch/setup-microsoft-search#step-2-assign-search-admin-and-search-editor) dans votre centre d’administration.
    
Pour vous aider à exploiter les requêtes des utilisateurs et les meilleurs résultats que vous avez créés dans SharePoint, la fonctionnalité Recherche Microsoft inclut deux outils permettant d’importer ces informations en tant que signets suggérés : 
  
## <a name="import-sharepoint-promoted-result-query-rules"></a>Importer des règles de requête de résultats promus par SharePoint

Importez ces règles, précédemment appelées Meilleurs résultats, en tant que signets suggérés. Pour les rendre disponibles à vos utilisateurs, publiez-les. Le durée de la publication varie en fonction du nombre de signets que vous sélectionnez.
  
## <a name="import-top-sharepoint-queries-using-powershell"></a>Importer des principales requêtes SharePoint en utilisant PowerShell

- Téléchargez les principales requêtes à partir de votre installation SharePoint. Le script PowerShell vous invitent à entrer des vos informations d’identification d’administrateur SharePoint.
    
- Effectuez une recherche dans SharePoint pour chacune des requêtes supérieures pour obtenir le résultat de recherche supérieure.
    
- Ajouter des signets suggérés pour le portail d’administration.
    
- Vos principales requêtes SharePoint sont d’excellents choix pour une utilisation de signets. Utilisez le script PowerShell pour les importer en tant que signets suggérés. Ce script pourra:
    
Télécharger le script et ouvrir le fichier LISEZMOI pour plus d’informations sur la configuration requise, les exemples et les paramètres disponibles. Après l’exécution du script PowerShell, un administrateur ou éditeur doit passer en revue les signets suggérés et rendre les modifications nécessaires avant qu’elles ne soient publiées.

  

