---
title: Configuration DNS avancée
ms.author: dawholl
author: dawholl
manager: kellis
ms.date: 12/19/2018
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Priority
search.appverid:
- BFB160
- MOE150
- MED150
ms.assetid: 47eedbb9-6da9-47e0-aac5-078d34a7fd8f
ROBOTS: NoIndex
description: Garantissez une expérience transparente à vos utilisateurs pour se connecter en configurant votre serveur DNS à l’aide d’un enregistrement CNAME
ms.openlocfilehash: 6a291165df33f8acc99d247104e8e88cd35c3a0e
ms.sourcegitcommit: be2e837d9b087bffe6ce40d72d7ae58a8fcdf3fe
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/30/2019
ms.locfileid: "34591358"
---
# <a name="advanced-dns-configuration"></a><span data-ttu-id="e6e70-103">Configuration DNS avancée</span><span class="sxs-lookup"><span data-stu-id="e6e70-103">Advanced DNS configuration</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e6e70-104">Cet article s’applique à la fonctionnalité Recherche Microsoft dans le portail d’administration Bing.</span><span class="sxs-lookup"><span data-stu-id="e6e70-104">This article applies to the Microsoft Search in Bing admin portal.</span></span> <span data-ttu-id="e6e70-105">Nous déplaçons le portail vers le centre d’administration Microsoft 365. Ensuite, nous le supprimerons.</span><span class="sxs-lookup"><span data-stu-id="e6e70-105">We’re moving the portal to the Microsoft 365 admin center, and then it will be removed.</span></span> <span data-ttu-id="e6e70-106">Pour commencer, nous vous suggérons d’utiliser le centre d’administration Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="e6e70-106">We recommend that you use the Microsoft 365 admin center to get started.</span></span> <span data-ttu-id="e6e70-107">[Vue d’ensemble de la fonctionnalité Recherche Microsoft](overview-microsoft-search.md).</span><span class="sxs-lookup"><span data-stu-id="e6e70-107">[Overview of Microsoft Search](overview-microsoft-search.md)</span></span>
    
<span data-ttu-id="e6e70-p102">Pour vous assurer que Bing peut toujours identifier les utilisateurs au sein de votre organisation et qui les connectent correctement à leur compte professionnel ou scolaire, configurer votre serveur DNS interne ou serveur proxy pour les résoudre à partir de`www.bing.com` à `ms.bing.com`. Pour ce faire, créez une entrée DNS pour`www.bing.com` être CNAME pour`ms.bing.com`.</span><span class="sxs-lookup"><span data-stu-id="e6e70-p102">To ensure Bing can always identify users within your organization and successfully sign them in to their work or school account, configure your internal DNS server or proxy server to resolve from `www.bing.com` to `ms.bing.com`. To do this, create a DNS entry for `www.bing.com` to be a CNAME for `ms.bing.com`.</span></span>
  
****

|<span data-ttu-id="e6e70-110">**Nom**</span><span class="sxs-lookup"><span data-stu-id="e6e70-110">**Name**</span></span>|<span data-ttu-id="e6e70-111">**Type**</span><span class="sxs-lookup"><span data-stu-id="e6e70-111">**Type**</span></span>|<span data-ttu-id="e6e70-112">**Valeur**</span><span class="sxs-lookup"><span data-stu-id="e6e70-112">**Value**</span></span>|
|:-----|:-----|:-----|
|`www.bing.com`  <br/> |<span data-ttu-id="e6e70-113">CNAME</span><span class="sxs-lookup"><span data-stu-id="e6e70-113">CNAME</span></span>  <br/> |`ms.bing.com`  <br/> |
   
<span data-ttu-id="e6e70-p103">Utiliser un enregistrement CNAME plutôt que l’adresse IP est conseillé, car un enregistrement CNAME continuera à fonctionner si l’adresse IP change. Après avoir apporté cette modification DNS, les résultats continueront à apparaître à vos utilisateurs comme s’ils venaient d’apparaître`www.bing.com`.</span><span class="sxs-lookup"><span data-stu-id="e6e70-p103">Using a CNAME rather than the IP address is preferred since a CNAME will continue to work if the IP address changes. After you make this DNS change, results will continue to appear to your users as if they are coming from `www.bing.com`.</span></span> 
  
<span data-ttu-id="e6e70-p104">Cela ne nécessite aucune configuration supplémentaire sur les ordinateurs client et offre une expérience transparente pour vos utilisateurs. Lorsqu’ils accèdent à `bing.com`, ils sont automatiquement connectés de manière plus consistante et s’ils ne peuvent pas être connectés automatiquement, ils seront invités à le faire.</span><span class="sxs-lookup"><span data-stu-id="e6e70-p104">This requires no additional configuration on client machines and provides a seamless experience for your users. When they go to `bing.com`, they'll be automatically signed in more consistently, and if they can't be signed in automatically, they'll be prompted to do so.</span></span>
