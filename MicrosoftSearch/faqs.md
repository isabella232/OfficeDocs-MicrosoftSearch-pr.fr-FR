---
title: FAQ
ms.author: jeffkizn
author: jeffkizn
manager: parulm
ms.audience: Admin
ms.topic: reference
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: Trouvez les réponses à certaines des questions les plus fréquentes concernant Microsoft Search (recherche Microsoft)
ms.openlocfilehash: 5a134116c98b4feea0c04909349ce4b972c59ffe
ms.sourcegitcommit: 0b8c3c57384cecaa93c5cbaf3b3b30f8e20d1a69
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/09/2020
ms.locfileid: "48408437"
---
<!-- markdownlint-disable no-trailing-punctuation -->
# <a name="frequently-asked-questions"></a><span data-ttu-id="4d7c0-103">Questions fréquemment posées</span><span class="sxs-lookup"><span data-stu-id="4d7c0-103">Frequently asked questions</span></span>

<span data-ttu-id="4d7c0-104">Voici la liste des questions fréquemment posées.</span><span class="sxs-lookup"><span data-stu-id="4d7c0-104">Here's a list of the most common questions.</span></span>

> [!TIP]
> <span data-ttu-id="4d7c0-105">La réponse à votre question n’y figure pas ?</span><span class="sxs-lookup"><span data-stu-id="4d7c0-105">Don't see your question answered here?</span></span> <span data-ttu-id="4d7c0-106">Posez votre question dans les commentaires de cet article.</span><span class="sxs-lookup"><span data-stu-id="4d7c0-106">Ask your question in this article's feedback.</span></span>

## <a name="is-advanced-query-understanding-supported"></a><span data-ttu-id="4d7c0-107">La compréhension de recherche avancée est-elle prise en charge ?</span><span class="sxs-lookup"><span data-stu-id="4d7c0-107">Is advanced query understanding supported?</span></span>

<span data-ttu-id="4d7c0-p102">Oui, Microsoft Search analyse l’intention des requêtes à partir d’expressions plus volumineuses. Cette fonctionnalité utilise l’AI pour découvrir les expressions superflues courantes que les utilisateurs ajoutent à leurs requêtes qui n’ont pas d’impact sur leur intention de recherche. Par exemple, lorsqu’un utilisateur recherche de *plus amples informations sur la modification de mon mot de passe*, Nous extrayons les mots moins importants de la requête et du déclencheur en fonction de ceux-ci, comme *modifier le mot de passe*.</span><span class="sxs-lookup"><span data-stu-id="4d7c0-p102">Yes, Microsoft Search parses query intent from larger phrases. This feature uses AI to learn common superfluous phrases users add to their queries that don't impact their search intent. For example, when a user searches for *tell me more about how to change my password please*, we extract the less important words from the query and trigger based on the relevant ones like *change password*.</span></span>
  
<span data-ttu-id="4d7c0-111">Cette fonctionnalité ne remplace pas les mots clés définis dans le [Centre d’administration 365 de Microsoft](https://admin.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="4d7c0-111">This feature won't override keywords set in the [Microsoft 365 admin center](https://admin.microsoft.com).</span></span>
  
## <a name="can-you-search-for-files-on-premises"></a><span data-ttu-id="4d7c0-112">Pouvez-vous rechercher des fichiers en local ?</span><span class="sxs-lookup"><span data-stu-id="4d7c0-112">Can you search for files on-premises?</span></span>

<span data-ttu-id="4d7c0-113">Oui.</span><span class="sxs-lookup"><span data-stu-id="4d7c0-113">Yes.</span></span> <span data-ttu-id="4d7c0-114">Vous pouvez effectuer des recherches dans des fichiers [SharePoint](http://sharepoint.com/) locaux si vous disposez d’un déploiement hybride de SharePoint.</span><span class="sxs-lookup"><span data-stu-id="4d7c0-114">You can search on-premises [SharePoint](http://sharepoint.com/) files if you have a hybrid deployment of SharePoint.</span></span>
  
## <a name="how-do-i-make-bing-the-default-search-engine-for-people-in-my-org"></a><span data-ttu-id="4d7c0-115">Comment configurer Bing en tant que moteur de recherche par défaut pour les personnes au sein de mon organisation ?</span><span class="sxs-lookup"><span data-stu-id="4d7c0-115">How do I make Bing the default search engine for people in my org?</span></span>

<span data-ttu-id="4d7c0-116">Voici les instructions permettant de définir le moteur de recherche par défaut, la page d’accueil par défaut et le navigateur par défaut pour permettre à vos utilisateurs de tirer le meilleur parti de Microsoft Search dans [Bing](https://Bing.com):</span><span class="sxs-lookup"><span data-stu-id="4d7c0-116">Here's the instructions for setting the default search engine, default homepage, and default browser to give your users the best experience with Microsoft Search in [Bing](https://Bing.com):</span></span>

- [<span data-ttu-id="4d7c0-117">Définir Microsoft Edge comme navigateur par défaut</span><span class="sxs-lookup"><span data-stu-id="4d7c0-117">Set Microsoft Edge as your default browser</span></span>](set-default-browser.md)
- [<span data-ttu-id="4d7c0-118">Définir Bing en tant que moteur de recherche par défaut</span><span class="sxs-lookup"><span data-stu-id="4d7c0-118">Make Bing your default search engine</span></span>](set-default-search-engine.md)
- [<span data-ttu-id="4d7c0-119">Définir Bing.com en tant que page d’accueil de votre entreprise</span><span class="sxs-lookup"><span data-stu-id="4d7c0-119">Set Bing.com as your enterprise homepage</span></span>](set-default-homepage.md)

## <a name="how-are-my-search-results-protected"></a><span data-ttu-id="4d7c0-120">Quel est le niveau de protection de mes résultats de recherche ?</span><span class="sxs-lookup"><span data-stu-id="4d7c0-120">How are my search results protected?</span></span>

<span data-ttu-id="4d7c0-121">Nous avons besoin de l’authentification [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/) pour accéder aux résultats à partir du Cloud approuvé.</span><span class="sxs-lookup"><span data-stu-id="4d7c0-121">We require [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/) authentication to access results from the Trusted Cloud.</span></span> <span data-ttu-id="4d7c0-122">Seul est présenté le contenu auquel les utilisateurs authentifiés ont accès.</span><span class="sxs-lookup"><span data-stu-id="4d7c0-122">Authenticated users only see content they have access to.</span></span> <span data-ttu-id="4d7c0-123">Les requêtes de recherche sont déidentifiées et les journaux sont séparés du trafic de recherche [Bing](https://Bing.com) public.</span><span class="sxs-lookup"><span data-stu-id="4d7c0-123">Search queries are de-identified, and logs are separated from public [Bing](https://Bing.com) search traffic.</span></span> <span data-ttu-id="4d7c0-124">Ce niveau de protection est inédit dans le secteur.</span><span class="sxs-lookup"><span data-stu-id="4d7c0-124">This level of protection is unavailable anywhere else in the industry.</span></span>

## <a name="can-i-search-across-federated-organizations"></a><span data-ttu-id="4d7c0-125">Puis-je effectuer des recherches dans les organisations fédérées ?</span><span class="sxs-lookup"><span data-stu-id="4d7c0-125">Can I search across federated organizations?</span></span>

<span data-ttu-id="4d7c0-126">Non.</span><span class="sxs-lookup"><span data-stu-id="4d7c0-126">No.</span></span>

## <a name="where-can-i-get-info-about-office-365-security-compliance-and-privacy"></a><span data-ttu-id="4d7c0-127">Où puis-je obtenir des informations sur la sécurité, la conformité et la confidentialité d’Office 365 ?</span><span class="sxs-lookup"><span data-stu-id="4d7c0-127">Where can I get info about Office 365 security, compliance, and privacy?</span></span>

<span data-ttu-id="4d7c0-128">Vous trouverez des détails dans les [pages du centre de gestion de la confidentialité pour Office 365](https://www.microsoft.com/TrustCenter/CloudServices/office365/default.aspx).</span><span class="sxs-lookup"><span data-stu-id="4d7c0-128">Details can be found on the [Trust Center pages for Office 365](https://www.microsoft.com/TrustCenter/CloudServices/office365/default.aspx).</span></span>

## <a name="can-users-earn-microsoft-rewards-points-with-their-work-or-school-account"></a><span data-ttu-id="4d7c0-129">Les utilisateurs peuvent-ils gagner des points Microsoft Rewards avec leur compte professionnel ou scolaire ?</span><span class="sxs-lookup"><span data-stu-id="4d7c0-129">Can users earn Microsoft Rewards points with their work or school account?</span></span>

<span data-ttu-id="4d7c0-130">La Recherche Microsoft nécessite que les utilisateurs de l’entreprise se connectent avec un compte professionnel ou scolaire,</span><span class="sxs-lookup"><span data-stu-id="4d7c0-130">Microsoft Search requires that enterprise users sign in with a work or school account.</span></span> <span data-ttu-id="4d7c0-131">mais les utilisateurs ne peuvent pas participer ou se connecter au programme Microsoft Rewards avec ces comptes.</span><span class="sxs-lookup"><span data-stu-id="4d7c0-131">But users can’t join or sign in to the Microsoft Rewards program with those accounts.</span></span> <span data-ttu-id="4d7c0-132">Toutefois, il existe une instance où un utilisateur de l’entreprise peut voir un gain de points Rewards.</span><span class="sxs-lookup"><span data-stu-id="4d7c0-132">However, there is an instance when an enterprise user may see Rewards points accrue.</span></span> <span data-ttu-id="4d7c0-133">Cela peut se produire lorsqu’un utilisateur de la Recherche Microsoft dispose d’un compte Rewards qui a été créé avec un [compte Microsoft](https://www.microsoft.com/welcome?rtc=1).</span><span class="sxs-lookup"><span data-stu-id="4d7c0-133">This can happen when a Microsoft Search user has a Rewards account that was created with a [Microsoft account](https://www.microsoft.com/welcome?rtc=1).</span></span> <span data-ttu-id="4d7c0-134">(L’adresse e-mail associée à un compte Microsoft peut être un compte Outlook.com, Hotmail.com, Gmail, Yahoo ou un compte provenant d’autres fournisseurs.) Si les utilisateurs se connectent avec leur compte professionnel et leur compte Microsoft dans la même session de navigateur, ils peuvent accumuler des points à leur compte Rewards.</span><span class="sxs-lookup"><span data-stu-id="4d7c0-134">(The email address associated with a Microsoft account can be from Outlook.com, Hotmail.com, Gmail, Yahoo, or other providers.) If users sign in alternately with both their work account and Microsoft account in the same browser session, they might accrue points to their Rewards account.</span></span> <span data-ttu-id="4d7c0-135">Les utilisateurs peuvent arrêter d’accumuler des points lorsqu’ils effectuent une recherche avec la Recherche Microsoft en effaçant leur cookies.</span><span class="sxs-lookup"><span data-stu-id="4d7c0-135">Users can stop accruing points while searching with Microsoft Search by clearing their cookies.</span></span>

## <a name="can-guest-users-leverage-microsoft-search-in-my-organization"></a><span data-ttu-id="4d7c0-136">Les utilisateurs invités peuvent-ils utiliser Microsoft Search dans mon organisation ?</span><span class="sxs-lookup"><span data-stu-id="4d7c0-136">Can guest users leverage Microsoft Search in my organization?</span></span>

<span data-ttu-id="4d7c0-137">Microsoft 365 permet une collaboration enrichie avec des personnes extérieures à votre organisation via [l’accès invité.](https://docs.microsoft.com/microsoft-365/solutions/collaborate-with-people-outside-your-organization)</span><span class="sxs-lookup"><span data-stu-id="4d7c0-137">Microsoft 365 enables rich collaboration with people outside of your organization through [guest access.](https://docs.microsoft.com/microsoft-365/solutions/collaborate-with-people-outside-your-organization)</span></span> <span data-ttu-id="4d7c0-138">Ces utilisateurs peuvent effectuer des opérations de recherche sur des documents, des sites, des groupes, des listes et des bibliothèques.</span><span class="sxs-lookup"><span data-stu-id="4d7c0-138">These users will be able to perform search operations on documents, sites, groups, lists, and libraries.</span></span> <span data-ttu-id="4d7c0-139">Toutefois, les utilisateurs invités n’obtiendront pas l’expérience complète et personnalisée de recherche Microsoft et devront peut-être utiliser la zone de recherche sur site à la place de la zone de recherche unifiée de Microsoft dans l’en-tête.</span><span class="sxs-lookup"><span data-stu-id="4d7c0-139">However, guest users will not get the full, personalized, Microsoft Search experience and may need to leverage the on-page search box instead of the unified Microsoft Search box in the header.</span></span>
