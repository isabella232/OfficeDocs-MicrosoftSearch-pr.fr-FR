---
title: Test de l’authentification unique
ms.author: dawholl
author: dawholl
manager: kellis
ms.date: 09/11/2018
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Priority
search.appverid:
- BFB160
- MET150
- MOE150
ms.assetid: a220c1bf-7cee-448a-90a3-310284d03e81
ROBOTS: NOINDEX
description: Réduisez le nombre d’invites de connexion à la recherche Microsoft ou à Office 365 pour les utilisateurs de Windows 10.
ms.openlocfilehash: c05a8ffcc973926add551bdbb20273b41ea23bc0
ms.sourcegitcommit: be2e837d9b087bffe6ce40d72d7ae58a8fcdf3fe
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/30/2019
ms.locfileid: "34591043"
---
# <a name="test-single-sign-on"></a><span data-ttu-id="70257-103">Tester l’authentification unique</span><span class="sxs-lookup"><span data-stu-id="70257-103">Test single sign-on</span></span>

> [!IMPORTANT]
> <span data-ttu-id="70257-104">Cet article s’applique à la fonctionnalité Recherche Microsoft dans le portail d’administration Bing.</span><span class="sxs-lookup"><span data-stu-id="70257-104">This article applies to the Microsoft Search in Bing admin portal.</span></span> <span data-ttu-id="70257-105">Nous déplaçons le portail vers le centre d’administration Microsoft 365. Ensuite, nous le supprimerons.</span><span class="sxs-lookup"><span data-stu-id="70257-105">We’re moving the portal to the Microsoft 365 admin center, and then it will be removed.</span></span> <span data-ttu-id="70257-106">Pour commencer, nous vous suggérons d’utiliser le centre d’administration Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="70257-106">We recommend that you use the Microsoft 365 admin center to get started.</span></span> <span data-ttu-id="70257-107">[Vue d’ensemble de la fonctionnalité Recherche Microsoft](overview-microsoft-search.md).</span><span class="sxs-lookup"><span data-stu-id="70257-107">[Overview of Microsoft Search](overview-microsoft-search.md)</span></span>
    
<span data-ttu-id="70257-p102">Grâce à l’authentification unique, vous pouvez réduire le nombre d’invites de connexion pour les utilisateurs. Vous pouvez tester cette fonctionnalité avec un petit groupe d’utilisateurs afin d’identifier les problèmes de configuration bloquants.</span><span class="sxs-lookup"><span data-stu-id="70257-p102">Single sign-on reduces the number of times users are prompted to sign in. Testing single sign-on with a small group of users will help identify any blocking configuration issues.</span></span> 
  
<span data-ttu-id="70257-110">Pour les utilisateurs de Chrome sur Windows 10, l’authentification unique fonctionnera uniquement si l’extension de connexion Windows 10 et AAD pour Chrome est installée.</span><span class="sxs-lookup"><span data-stu-id="70257-110">For Chrome users on Windows 10, single sign-on will only work if the Windows 10 and AAD sign-in extension for Chrome is installed.</span></span> 
  
## <a name="download-the-windows-10-and-aad-sign-in-extension-for-chrome"></a><span data-ttu-id="70257-111">Téléchargez l’extension de connexion Windows 10 et AAD pour Chrome.</span><span class="sxs-lookup"><span data-stu-id="70257-111">Download the Windows 10 and AAD sign-in extension for Chrome</span></span>

<span data-ttu-id="70257-112">Nous vous recommandons de créer une stratégie de groupe pour installer automatiquement cette extension.</span><span class="sxs-lookup"><span data-stu-id="70257-112">We recommend that you create a group policy to automatically install this extension.</span></span>
  
1. <span data-ttu-id="70257-113">Accédez au portail d’administration de la recherche Microsoft.</span><span class="sxs-lookup"><span data-stu-id="70257-113">Go to the Microsoft Search Admin portal</span></span>
    
2. <span data-ttu-id="70257-114">Dans le volet de navigation, cliquez sur **Outils**.</span><span class="sxs-lookup"><span data-stu-id="70257-114">In the navigation pane, click **Tools**</span></span>
    
3. <span data-ttu-id="70257-115">Dans la liste Outils, téléchargez l’**extension de connexion Windows 10 et AAD pour Chrome**.</span><span class="sxs-lookup"><span data-stu-id="70257-115">In the Tools list, download the **Windows 10 and AAD sign-in extension for Chrome**</span></span>
    
4. <span data-ttu-id="70257-116">Partagez l’extension avec les utilisateurs de Chrome sur Windows 10.</span><span class="sxs-lookup"><span data-stu-id="70257-116">Share the extension with Chrome users on Windows 10</span></span>

  

