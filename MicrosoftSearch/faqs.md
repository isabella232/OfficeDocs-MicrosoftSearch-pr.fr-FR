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
ms.openlocfilehash: 3ff2aabae4e09170b6b0380d520bfc620d5de5d8
ms.sourcegitcommit: 21361af7c244ffd6ff8689fd0ff0daa359bf4129
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/14/2019
ms.locfileid: "38626254"
---
# <a name="frequently-asked-questions"></a><span data-ttu-id="42472-103">Questions fréquemment posées</span><span class="sxs-lookup"><span data-stu-id="42472-103">Frequently asked questions</span></span>

<span data-ttu-id="42472-104">Voici la liste des questions fréquemment posées.</span><span class="sxs-lookup"><span data-stu-id="42472-104">Here's a list of the most common questions.</span></span>

> [!TIP]
> <span data-ttu-id="42472-105">La réponse à votre question n’y figure pas ?</span><span class="sxs-lookup"><span data-stu-id="42472-105">Don't see your question answered here?</span></span> <span data-ttu-id="42472-106">Posez votre question dans les commentaires de cet article.</span><span class="sxs-lookup"><span data-stu-id="42472-106">Ask your question in this article's feedback.</span></span>

## <a name="is-advanced-query-understanding-supported"></a><span data-ttu-id="42472-107">La compréhension de recherche avancée est-elle prise en charge ?</span><span class="sxs-lookup"><span data-stu-id="42472-107">Is advanced query understanding supported?</span></span>

<span data-ttu-id="42472-p102">Oui, Microsoft Search (recherche Microsoft) analyse objectif requête à partir de phrases plus grande. Cette fonctionnalité utilise AI pour en savoir plus sur les phrases courantes superflues que les utilisateurs ajoutent à leurs requêtes qui n’ont pas d’impact sur leur objectif de recherche. Par exemple, lorsqu’un utilisateur recherche « en savoir plus sur comment modifier mon mot de passe svp» nous extrayons les mots moins importants à partir de la requête, puis déclenchons ceux pertinents par exemple, « modifier votre mot de passe ».</span><span class="sxs-lookup"><span data-stu-id="42472-p102">Yes, Microsoft Search parses query intent from larger phrases. This feature uses AI to learn common superfluous phrases users add to their queries that don't impact their search intent. For example, when a user searches for 'tell me more about how to change my password please' we extract the less important words from the query and trigger based on the relevant ones like 'change password.'</span></span>
  
<span data-ttu-id="42472-111">Cette fonctionnalité ne remplace pas l’ensemble de mots clés dans le Centre d’administration.</span><span class="sxs-lookup"><span data-stu-id="42472-111">This feature will not override keywords set in the admin center.</span></span>
  
## <a name="can-you-search-for-files-on-premises"></a><span data-ttu-id="42472-112">Pouvez-vous rechercher des fichiers en local ?</span><span class="sxs-lookup"><span data-stu-id="42472-112">Can you search for files on-premises?</span></span>

<span data-ttu-id="42472-113">Oui.</span><span class="sxs-lookup"><span data-stu-id="42472-113">Yes.</span></span> <span data-ttu-id="42472-114">Vous pouvez rechercher des fichiers SharePoint locaux si vous disposez d’un déploiement SharePoint hybride.</span><span class="sxs-lookup"><span data-stu-id="42472-114">You can search on-premises SharePoint files if you have a hybrid deployment of SharePoint.</span></span>
  
## <a name="how-do-i-make-bing-the-default-search-engine-for-people-in-my-org"></a><span data-ttu-id="42472-115">Comment configurer Bing en tant que moteur de recherche par défaut pour les personnes au sein de mon organisation ?</span><span class="sxs-lookup"><span data-stu-id="42472-115">How do I make Bing the default search engine for people in my org?</span></span>

<span data-ttu-id="42472-116">Voici les instructions permettant de définir le moteur de recherche, la page d’accueil et le navigateur par défaut afin d’offrir à vos utilisateurs une expérience optimale avec la Recherche Microsoft dans Bing :</span><span class="sxs-lookup"><span data-stu-id="42472-116">Here's the instructions for setting the default search engine, default homepage, and default browser to give your users the best experience with Microsoft Search in Bing:</span></span>

- [<span data-ttu-id="42472-117">Définir Microsoft Edge en tant que navigateur par défaut</span><span class="sxs-lookup"><span data-stu-id="42472-117">Set Edge as your default browser</span></span>](set-default-browser.md)
- [<span data-ttu-id="42472-118">Définir Bing en tant que moteur de recherche par défaut</span><span class="sxs-lookup"><span data-stu-id="42472-118">Make Bing your default search engine</span></span>](set-default-search-engine.md)
- [<span data-ttu-id="42472-119">Définir Bing.com en tant que page d’accueil de votre entreprise</span><span class="sxs-lookup"><span data-stu-id="42472-119">Set Bing.com as your enterprise homepage</span></span>](set-default-homepage.md)

  
## <a name="how-are-my-search-results-protected"></a><span data-ttu-id="42472-120">Quel est le niveau de protection de mes résultats de recherche ?</span><span class="sxs-lookup"><span data-stu-id="42472-120">How are my search results protected?</span></span>

<span data-ttu-id="42472-121">Nous demandons l’authentification Azure Active Directory pour accéder aux résultats à partir de Trusted Cloud.</span><span class="sxs-lookup"><span data-stu-id="42472-121">We require Azure Active Directory (AAD) authentication to access results from the Trusted Cloud.</span></span> <span data-ttu-id="42472-122">Seul est présenté le contenu auquel les utilisateurs authentifiés ont accès.</span><span class="sxs-lookup"><span data-stu-id="42472-122">Authenticated users only see content they have access to.</span></span> <span data-ttu-id="42472-123">Les requêtes de recherche ne sont pas identifiées et les journaux sont séparés du trafic de recherche public Bing.</span><span class="sxs-lookup"><span data-stu-id="42472-123">Search queries are de-identified and logs are separated from public Bing search traffic.</span></span> <span data-ttu-id="42472-124">Ce niveau de protection est inédit dans le secteur.</span><span class="sxs-lookup"><span data-stu-id="42472-124">This level of protection is unavailable anywhere else in the industry.</span></span>

## <a name="can-i-search-across-federated-organizations"></a><span data-ttu-id="42472-125">Puis-je effectuer des recherches dans les organisations fédérées ?</span><span class="sxs-lookup"><span data-stu-id="42472-125">Can I search across federated organizations?</span></span>

<span data-ttu-id="42472-126">Non.</span><span class="sxs-lookup"><span data-stu-id="42472-126">No.</span></span>

## <a name="where-can-i-get-info-about-office-365-and-microsoft-365-compliance-tiers-and-categories"></a><span data-ttu-id="42472-127">Où puis-je obtenir des informations sur les différents niveaux et catégories de conformité d’Office 365 et de Microsoft 365 ?</span><span class="sxs-lookup"><span data-stu-id="42472-127">Where can I get info about Office 365 and Microsoft 365 compliance tiers and categories?</span></span>

<span data-ttu-id="42472-128">Les détails sont accessibles dans l’[infrastructure de conformité pour les normes et réglementations](https://download.microsoft.com/download/B/2/7/B27B3EF3-8849-4C18-8BA4-5AD755728620/Compliance%20Framework_customer%20guidance.pdf) (téléchargement PDF).</span><span class="sxs-lookup"><span data-stu-id="42472-128">Details can be found in the [Compliance Framework for Industry Standards and Regulations](https://download.microsoft.com/download/B/2/7/B27B3EF3-8849-4C18-8BA4-5AD755728620/Compliance%20Framework_customer%20guidance.pdf) (PDF download).</span></span>

## <a name="can-users-earn-microsoft-rewards-points-with-their-work-or-school-account"></a><span data-ttu-id="42472-129">Les utilisateurs peuvent-ils gagner des points Microsoft Rewards avec leur compte professionnel ou scolaire ?</span><span class="sxs-lookup"><span data-stu-id="42472-129">Can users earn Microsoft Rewards points with their work or school account?</span></span>

<span data-ttu-id="42472-130">La Recherche Microsoft nécessite que les utilisateurs de l’entreprise se connectent avec un compte professionnel ou scolaire,</span><span class="sxs-lookup"><span data-stu-id="42472-130">Microsoft Search requires that enterprise users sign in with a work or school account.</span></span> <span data-ttu-id="42472-131">mais les utilisateurs ne peuvent pas participer ou se connecter au programme Microsoft Rewards avec ces comptes.</span><span class="sxs-lookup"><span data-stu-id="42472-131">But users can’t join or sign in to the Microsoft Rewards program with those accounts.</span></span> <span data-ttu-id="42472-132">Toutefois, il existe une instance où un utilisateur de l’entreprise peut voir un gain de points Rewards.</span><span class="sxs-lookup"><span data-stu-id="42472-132">However, there is an instance when an enterprise user may see Rewards points accrue.</span></span> <span data-ttu-id="42472-133">Cela peut se produire lorsqu’un utilisateur de la Recherche Microsoft dispose d’un compte Rewards qui a été créé avec un <a href="https://www.microsoft.com/en-us/welcome?rtc=1">compte Microsoft</a>.</span><span class="sxs-lookup"><span data-stu-id="42472-133">This can happen when a Microsoft Search user has a Rewards account that was created with a <a href="https://www.microsoft.com/en-us/welcome?rtc=1">Microsoft account</a>.</span></span> <span data-ttu-id="42472-134">(L’adresse e-mail associée à un compte Microsoft peut être un compte Outlook.com, Hotmail.com, Gmail, Yahoo ou un compte provenant d’autres fournisseurs.) Si les utilisateurs se connectent avec leur compte professionnel et leur compte Microsoft dans la même session de navigateur, ils peuvent accumuler des points à leur compte Rewards.</span><span class="sxs-lookup"><span data-stu-id="42472-134">(The email address associated with a Microsoft account can be from Outlook.com, Hotmail.com, Gmail, Yahoo, or other providers.) If users sign in alternately with both their work account and Microsoft account in the same browser session, they might accrue points to their Rewards account.</span></span> <span data-ttu-id="42472-135">Les utilisateurs peuvent arrêter d’accumuler des points lorsqu’ils effectuent une recherche avec la Recherche Microsoft en effaçant leur cookies.</span><span class="sxs-lookup"><span data-stu-id="42472-135">Users can stop accruing points while searching with Microsoft Search by clearing their cookies.</span></span> 

