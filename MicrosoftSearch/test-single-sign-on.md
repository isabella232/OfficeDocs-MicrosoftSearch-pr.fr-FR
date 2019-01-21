---
title: Test de l’authentification unique
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
ms.assetid: a220c1bf-7cee-448a-90a3-310284d03e81
description: Réduire le nombre de fois où que les utilisateurs Windows 10 sont invités à se connecter à Microsoft Search et Office 365
ms.openlocfilehash: 4157707d58ead304449805c8fd16578690ac01a6
ms.sourcegitcommit: bf52cc63b75f2e0324a716fe65da47702956b722
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/18/2019
ms.locfileid: "29378728"
---
# <a name="test-single-sign-on"></a><span data-ttu-id="4ad6d-103">Test de l’authentification unique</span><span class="sxs-lookup"><span data-stu-id="4ad6d-103">Test single sign-on</span></span>

<span data-ttu-id="4ad6d-p101">Authentification unique réduit le nombre de fois que les utilisateurs sont invités à se connecter. Test de l’authentification unique avec un petit groupe d’utilisateurs permet d’identifier les problèmes de configuration bloquante.</span><span class="sxs-lookup"><span data-stu-id="4ad6d-p101">Single sign-on reduces the number of times users are prompted to sign in. Testing single sign-on with a small group of users will help identify any blocking configuration issues.</span></span> 
  
<span data-ttu-id="4ad6d-106">Pour les utilisateurs de Chrome sur Windows 10, authentification unique fonctionne uniquement si le Windows 10 et DAS connexion l’extension de Chrome est installé.</span><span class="sxs-lookup"><span data-stu-id="4ad6d-106">For Chrome users on Windows 10, single sign-on will only work if the Windows 10 and AAD sign-in extension for Chrome is installed.</span></span> 
  
## <a name="download-the-windows-10-and-aad-sign-in-extension-for-chrome"></a><span data-ttu-id="4ad6d-107">Téléchargez l’extension connexion Windows 10 et DAS pour Chrome</span><span class="sxs-lookup"><span data-stu-id="4ad6d-107">Download the Windows 10 and AAD sign-in extension for Chrome</span></span>

<span data-ttu-id="4ad6d-108">Nous vous conseillons de créer une stratégie de groupe pour installer automatiquement cette extension.</span><span class="sxs-lookup"><span data-stu-id="4ad6d-108">We recommend that you create a group policy to automatically install this extension.</span></span>
  
1. <span data-ttu-id="4ad6d-109">Accédez au portail d’administration de recherche Microsoft</span><span class="sxs-lookup"><span data-stu-id="4ad6d-109">Go to the Microsoft Search Admin portal</span></span>
    
2. <span data-ttu-id="4ad6d-110">Dans le volet de navigation, cliquez sur **Outils**</span><span class="sxs-lookup"><span data-stu-id="4ad6d-110">In the navigation pane, click **Tools**</span></span>
    
3. <span data-ttu-id="4ad6d-111">Dans la liste des outils, téléchargez **Windows 10 et DAS connexion extension de Chrome**</span><span class="sxs-lookup"><span data-stu-id="4ad6d-111">In the Tools list, download the **Windows 10 and AAD sign-in extension for Chrome**</span></span>
    
4. <span data-ttu-id="4ad6d-112">Partager l’extension avec des utilisateurs de Chrome sur Windows 10</span><span class="sxs-lookup"><span data-stu-id="4ad6d-112">Share the extension with Chrome users on Windows 10</span></span>

  

