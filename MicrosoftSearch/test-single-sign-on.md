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
description: Réduisez le nombre d’invites de connexion à la recherche Microsoft ou à Office 365 pour les utilisateurs de Windows 10.
ms.openlocfilehash: 55d359edac36020ec8cf2aad6b64ca9737ee1066
ms.sourcegitcommit: 1c038d87efab4840d97b1f367b39e2b9ecdfee4a
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/29/2019
ms.locfileid: "29612350"
---
# <a name="test-single-sign-on"></a><span data-ttu-id="ed1dd-103">Test de l’authentification unique</span><span class="sxs-lookup"><span data-stu-id="ed1dd-103">Test single sign-on</span></span>

<span data-ttu-id="ed1dd-p101">Grâce à l’authentification unique, vous pouvez réduire le nombre d’invites de connexion pour les utilisateurs. Vous pouvez tester cette fonctionnalité avec un petit groupe d’utilisateurs afin d’identifier les problèmes de configuration bloquants.</span><span class="sxs-lookup"><span data-stu-id="ed1dd-p101">Single sign-on reduces the number of times users are prompted to sign in. Testing single sign-on with a small group of users will help identify any blocking configuration issues.</span></span> 
  
<span data-ttu-id="ed1dd-106">Pour les utilisateurs de Chrome sur Windows 10, l’authentification unique fonctionnera uniquement si l’extension de connexion Windows 10 et AAD pour Chrome est installée.</span><span class="sxs-lookup"><span data-stu-id="ed1dd-106">For Chrome users on Windows 10, single sign-on will only work if the Windows 10 and AAD sign-in extension for Chrome is installed.</span></span> 
  
## <a name="download-the-windows-10-and-aad-sign-in-extension-for-chrome"></a><span data-ttu-id="ed1dd-107">Téléchargez l’extension de connexion Windows 10 et AAD pour Chrome.</span><span class="sxs-lookup"><span data-stu-id="ed1dd-107">Download the Windows 10 and AAD sign-in extension for Chrome</span></span>

<span data-ttu-id="ed1dd-108">Nous vous recommandons de créer une stratégie de groupe pour installer automatiquement cette extension.</span><span class="sxs-lookup"><span data-stu-id="ed1dd-108">We recommend that you create a group policy to automatically install this extension.</span></span>
  
1. <span data-ttu-id="ed1dd-109">Accédez au portail d’administration de la recherche Microsoft.</span><span class="sxs-lookup"><span data-stu-id="ed1dd-109">Go to the Microsoft Search Admin portal</span></span>
    
2. <span data-ttu-id="ed1dd-110">Dans le volet de navigation, cliquez sur **Outils**.</span><span class="sxs-lookup"><span data-stu-id="ed1dd-110">In the navigation pane, click **ADSI Edit**.</span></span>
    
3. <span data-ttu-id="ed1dd-111">Dans la liste Outils, téléchargez l’**extension de connexion Windows 10 et AAD pour Chrome**.</span><span class="sxs-lookup"><span data-stu-id="ed1dd-111">In the Tools list, download the **Windows 10 and AAD sign-in extension for Chrome**</span></span>
    
4. <span data-ttu-id="ed1dd-112">Partagez l’extension avec les utilisateurs de Chrome sur Windows 10.</span><span class="sxs-lookup"><span data-stu-id="ed1dd-112">Share the extension with Chrome users on Windows 10</span></span>

  

