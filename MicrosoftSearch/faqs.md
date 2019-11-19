---
title: FAQ
ms.author: anfowler
author: adefowler
manager: shohara
ms.audience: Admin
ms.topic: reference
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: Trouvez les réponses à certaines des questions les plus fréquentes concernant Microsoft Search (recherche Microsoft)
ms.openlocfilehash: edfb8346263d60184d8655afa24118ed4b3e3bca
ms.sourcegitcommit: 68087149c769a7cdde80944dd9c9933d2bf4a23f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/18/2019
ms.locfileid: "38699792"
---
# <a name="frequently-asked-questions"></a><span data-ttu-id="6e13b-103">Questions fréquemment posées</span><span class="sxs-lookup"><span data-stu-id="6e13b-103">Frequently asked questions</span></span>

<span data-ttu-id="6e13b-104">Voici la liste des questions fréquemment posées.</span><span class="sxs-lookup"><span data-stu-id="6e13b-104">Here's a list of the most common questions.</span></span>

> [!TIP]
> <span data-ttu-id="6e13b-105">La réponse à votre question n’y figure pas ?</span><span class="sxs-lookup"><span data-stu-id="6e13b-105">Don't see your question answered here?</span></span> <span data-ttu-id="6e13b-106">Posez votre question dans les commentaires de cet article.</span><span class="sxs-lookup"><span data-stu-id="6e13b-106">Ask your question in this article's feedback.</span></span>

## <a name="is-advanced-query-understanding-supported"></a><span data-ttu-id="6e13b-107">La compréhension de recherche avancée est-elle prise en charge ?</span><span class="sxs-lookup"><span data-stu-id="6e13b-107">Is advanced query understanding supported?</span></span>

<span data-ttu-id="6e13b-p102">Oui, Microsoft Search analyse l’intention des requêtes à partir d’expressions plus volumineuses. Cette fonctionnalité utilise l’AI pour découvrir les expressions superflues courantes que les utilisateurs ajoutent à leurs requêtes qui n’ont pas d’impact sur leur intention de recherche. Par exemple, lorsqu’un utilisateur recherche de *plus amples informations sur la modification de mon mot de passe*, Nous extrayons les mots moins importants de la requête et du déclencheur en fonction de ceux-ci, comme *modifier le mot de passe*.</span><span class="sxs-lookup"><span data-stu-id="6e13b-p102">Yes, Microsoft Search parses query intent from larger phrases. This feature uses AI to learn common superfluous phrases users add to their queries that don't impact their search intent. For example, when a user searches for *tell me more about how to change my password please*, we extract the less important words from the query and trigger based on the relevant ones like *change password*.</span></span>
  
<span data-ttu-id="6e13b-111">Cette fonctionnalité ne remplace pas les mots clés définis dans le [Centre d’administration](https://admin.microsoft.com)365 de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="6e13b-111">This feature won't override keywords set in the Microsoft 365 [admin center](https://admin.microsoft.com).</span></span>
  
## <a name="can-you-search-for-files-on-premises"></a><span data-ttu-id="6e13b-112">Pouvez-vous rechercher des fichiers en local ?</span><span class="sxs-lookup"><span data-stu-id="6e13b-112">Can you search for files on-premises?</span></span>

<span data-ttu-id="6e13b-113">Oui.</span><span class="sxs-lookup"><span data-stu-id="6e13b-113">Yes.</span></span> <span data-ttu-id="6e13b-114">Vous pouvez effectuer des recherches dans des fichiers [SharePoint](http://sharepoint.com/) locaux si vous disposez d’un déploiement hybride de SharePoint.</span><span class="sxs-lookup"><span data-stu-id="6e13b-114">You can search on-premises [SharePoint](http://sharepoint.com/) files if you have a hybrid deployment of SharePoint.</span></span>
  
## <a name="how-do-i-make-bing-the-default-search-engine-for-people-in-my-org"></a><span data-ttu-id="6e13b-115">Comment configurer Bing en tant que moteur de recherche par défaut pour les personnes au sein de mon organisation ?</span><span class="sxs-lookup"><span data-stu-id="6e13b-115">How do I make Bing the default search engine for people in my org?</span></span>

<span data-ttu-id="6e13b-116">Voici les instructions permettant de définir le moteur de recherche par défaut, la page d’accueil par défaut et le navigateur par défaut pour permettre à vos utilisateurs de tirer le meilleur parti de Microsoft Search dans [Bing](https://Bing.com):</span><span class="sxs-lookup"><span data-stu-id="6e13b-116">Here's the instructions for setting the default search engine, default homepage, and default browser to give your users the best experience with Microsoft Search in [Bing](https://Bing.com):</span></span>

- [<span data-ttu-id="6e13b-117">Définir Microsoft Edge comme navigateur par défaut</span><span class="sxs-lookup"><span data-stu-id="6e13b-117">Set Microsoft Edge as your default browser</span></span>](set-default-browser.md)
- [<span data-ttu-id="6e13b-118">Définir Bing en tant que moteur de recherche par défaut</span><span class="sxs-lookup"><span data-stu-id="6e13b-118">Make Bing your default search engine</span></span>](set-default-search-engine.md)
- [<span data-ttu-id="6e13b-119">Définir Bing.com en tant que page d’accueil de votre entreprise</span><span class="sxs-lookup"><span data-stu-id="6e13b-119">Set Bing.com as your enterprise homepage</span></span>](set-default-homepage.md)

  
## <a name="how-are-my-search-results-protected"></a><span data-ttu-id="6e13b-120">Quel est le niveau de protection de mes résultats de recherche ?</span><span class="sxs-lookup"><span data-stu-id="6e13b-120">How are my search results protected?</span></span>

<span data-ttu-id="6e13b-121">Nous avons besoin de l’authentification [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/) pour accéder aux résultats à partir du Cloud approuvé.</span><span class="sxs-lookup"><span data-stu-id="6e13b-121">We require [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/) authentication to access results from the Trusted Cloud.</span></span> <span data-ttu-id="6e13b-122">Seul est présenté le contenu auquel les utilisateurs authentifiés ont accès.</span><span class="sxs-lookup"><span data-stu-id="6e13b-122">Authenticated users only see content they have access to.</span></span> <span data-ttu-id="6e13b-123">Les requêtes de recherche sont déidentifiées et les journaux sont séparés du trafic de recherche [Bing](https://Bing.com) public.</span><span class="sxs-lookup"><span data-stu-id="6e13b-123">Search queries are de-identified, and logs are separated from public [Bing](https://Bing.com) search traffic.</span></span> <span data-ttu-id="6e13b-124">Ce niveau de protection est inédit dans le secteur.</span><span class="sxs-lookup"><span data-stu-id="6e13b-124">This level of protection is unavailable anywhere else in the industry.</span></span>

## <a name="can-i-search-across-federated-organizations"></a><span data-ttu-id="6e13b-125">Puis-je effectuer des recherches dans les organisations fédérées ?</span><span class="sxs-lookup"><span data-stu-id="6e13b-125">Can I search across federated organizations?</span></span>

<span data-ttu-id="6e13b-126">Non.</span><span class="sxs-lookup"><span data-stu-id="6e13b-126">No.</span></span>

## <a name="where-can-i-get-info-about-office-365-and-microsoft-365-compliance-tiers-and-categories"></a><span data-ttu-id="6e13b-127">Où puis-je obtenir des informations sur les différents niveaux et catégories de conformité d’Office 365 et de Microsoft 365 ?</span><span class="sxs-lookup"><span data-stu-id="6e13b-127">Where can I get info about Office 365 and Microsoft 365 compliance tiers and categories?</span></span>

<span data-ttu-id="6e13b-128">Les détails sont accessibles dans l’[infrastructure de conformité pour les normes et réglementations](https://download.microsoft.com/download/B/2/7/B27B3EF3-8849-4C18-8BA4-5AD755728620/Compliance%20Framework_customer%20guidance.pdf) (téléchargement PDF).</span><span class="sxs-lookup"><span data-stu-id="6e13b-128">Details can be found in the [Compliance Framework for Industry Standards and Regulations](https://download.microsoft.com/download/B/2/7/B27B3EF3-8849-4C18-8BA4-5AD755728620/Compliance%20Framework_customer%20guidance.pdf) (PDF download).</span></span>

## <a name="can-users-earn-microsoft-rewards-points-with-their-work-or-school-account"></a><span data-ttu-id="6e13b-129">Les utilisateurs peuvent-ils gagner des points Microsoft Rewards avec leur compte professionnel ou scolaire ?</span><span class="sxs-lookup"><span data-stu-id="6e13b-129">Can users earn Microsoft Rewards points with their work or school account?</span></span>

<span data-ttu-id="6e13b-130">La Recherche Microsoft nécessite que les utilisateurs de l’entreprise se connectent avec un compte professionnel ou scolaire,</span><span class="sxs-lookup"><span data-stu-id="6e13b-130">Microsoft Search requires that enterprise users sign in with a work or school account.</span></span> <span data-ttu-id="6e13b-131">mais les utilisateurs ne peuvent pas participer ou se connecter au programme Microsoft Rewards avec ces comptes.</span><span class="sxs-lookup"><span data-stu-id="6e13b-131">But users can’t join or sign in to the Microsoft Rewards program with those accounts.</span></span> <span data-ttu-id="6e13b-132">Toutefois, il existe une instance où un utilisateur de l’entreprise peut voir un gain de points Rewards.</span><span class="sxs-lookup"><span data-stu-id="6e13b-132">However, there is an instance when an enterprise user may see Rewards points accrue.</span></span> <span data-ttu-id="6e13b-133">Cela peut se produire lorsqu’un utilisateur de la Recherche Microsoft dispose d’un compte Rewards qui a été créé avec un <a href="https://www.microsoft.com/welcome?rtc=1">compte Microsoft</a>.</span><span class="sxs-lookup"><span data-stu-id="6e13b-133">This can happen when a Microsoft Search user has a Rewards account that was created with a <a href="https://www.microsoft.com/welcome?rtc=1">Microsoft account</a>.</span></span> <span data-ttu-id="6e13b-134">(L’adresse e-mail associée à un compte Microsoft peut être un compte Outlook.com, Hotmail.com, Gmail, Yahoo ou un compte provenant d’autres fournisseurs.) Si les utilisateurs se connectent avec leur compte professionnel et leur compte Microsoft dans la même session de navigateur, ils peuvent accumuler des points à leur compte Rewards.</span><span class="sxs-lookup"><span data-stu-id="6e13b-134">(The email address associated with a Microsoft account can be from Outlook.com, Hotmail.com, Gmail, Yahoo, or other providers.) If users sign in alternately with both their work account and Microsoft account in the same browser session, they might accrue points to their Rewards account.</span></span> <span data-ttu-id="6e13b-135">Les utilisateurs peuvent arrêter d’accumuler des points lorsqu’ils effectuent une recherche avec la Recherche Microsoft en effaçant leur cookies.</span><span class="sxs-lookup"><span data-stu-id="6e13b-135">Users can stop accruing points while searching with Microsoft Search by clearing their cookies.</span></span> 

