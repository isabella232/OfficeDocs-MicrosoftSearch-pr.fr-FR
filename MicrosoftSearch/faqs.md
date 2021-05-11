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
ms.openlocfilehash: 614fa241f353533b1c1e181904eb961fd55d0dfa
ms.sourcegitcommit: ea784081bc9c3ae7981a87a493d3a74503859dda
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/10/2021
ms.locfileid: "52306069"
---
<!-- markdownlint-disable no-trailing-punctuation -->
# <a name="frequently-asked-questions"></a><span data-ttu-id="2b404-103">Questions fréquemment posées</span><span class="sxs-lookup"><span data-stu-id="2b404-103">Frequently asked questions</span></span>

<span data-ttu-id="2b404-104">Voici la liste des questions fréquemment posées.</span><span class="sxs-lookup"><span data-stu-id="2b404-104">Here's a list of the most common questions.</span></span>

> [!TIP]
> <span data-ttu-id="2b404-105">La réponse à votre question n’y figure pas ?</span><span class="sxs-lookup"><span data-stu-id="2b404-105">Don't see your question answered here?</span></span> <span data-ttu-id="2b404-106">Posez votre question dans les commentaires de cet article.</span><span class="sxs-lookup"><span data-stu-id="2b404-106">Ask your question in this article's feedback.</span></span>

## <a name="is-advanced-query-understanding-supported"></a><span data-ttu-id="2b404-107">La compréhension de recherche avancée est-elle prise en charge ?</span><span class="sxs-lookup"><span data-stu-id="2b404-107">Is advanced query understanding supported?</span></span>

<span data-ttu-id="2b404-108">Oui, Microsoft Search (recherche Microsoft) recherche l’intention de la requête à partir d’expressions plus grandes.</span><span class="sxs-lookup"><span data-stu-id="2b404-108">Yes, Microsoft Search parses query intent from larger phrases.</span></span> <span data-ttu-id="2b404-109">Cette fonctionnalité utilise l’IA pour découvrir les expressions superflues courantes que les utilisateurs ajoutent à leurs requêtes qui n’ont pas d’impact sur leur intention de recherche.</span><span class="sxs-lookup"><span data-stu-id="2b404-109">This feature uses AI to learn common superfluous phrases users add to their queries that don't impact their search intent.</span></span> <span data-ttu-id="2b404-110">Par exemple, lorsqu’un utilisateur recherche des informations sur la modification de mon mot de *passe,* nous extrayons les mots les moins importants de la requête et le déclencheur en fonction des mots pertinents tels que le mot de passe de *modification.*</span><span class="sxs-lookup"><span data-stu-id="2b404-110">For example, when a user searches for *tell me more about how to change my password*, we extract the less important words from the query and trigger based on the relevant ones like *change password*.</span></span>
  
<span data-ttu-id="2b404-111">Cette fonctionnalité ne remplacera pas les mots clés du centre d’administration [Microsoft 365.](https://admin.microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="2b404-111">This feature won't override keywords set in the [Microsoft 365 admin center](https://admin.microsoft.com).</span></span>
  
## <a name="can-you-search-for-files-on-premises"></a><span data-ttu-id="2b404-112">Pouvez-vous rechercher des fichiers en local ?</span><span class="sxs-lookup"><span data-stu-id="2b404-112">Can you search for files on-premises?</span></span>

<span data-ttu-id="2b404-113">Oui.</span><span class="sxs-lookup"><span data-stu-id="2b404-113">Yes.</span></span> <span data-ttu-id="2b404-114">Vous pouvez rechercher des fichiers SharePoint [locaux](http://sharepoint.com/) si vous avez un déploiement hybride de SharePoint.</span><span class="sxs-lookup"><span data-stu-id="2b404-114">You can search on-premises [SharePoint](http://sharepoint.com/) files if you have a hybrid deployment of SharePoint.</span></span>
  
## <a name="how-do-i-make-bing-the-default-search-engine-for-people-in-my-org"></a><span data-ttu-id="2b404-115">Comment configurer Bing en tant que moteur de recherche par défaut pour les personnes au sein de mon organisation ?</span><span class="sxs-lookup"><span data-stu-id="2b404-115">How do I make Bing the default search engine for people in my org?</span></span>

<span data-ttu-id="2b404-116">Voici les instructions pour définir le moteur de recherche par défaut, la page d’accueil par défaut et le navigateur par défaut pour offrir à vos utilisateurs la meilleure expérience avec La recherche Microsoft [dans Bing](https://Bing.com):</span><span class="sxs-lookup"><span data-stu-id="2b404-116">Here's the instructions for setting the default search engine, default homepage, and default browser to give your users the best experience with Microsoft Search in [Bing](https://Bing.com):</span></span>

- [<span data-ttu-id="2b404-117">Définir Microsoft Edge comme navigateur par défaut</span><span class="sxs-lookup"><span data-stu-id="2b404-117">Set Microsoft Edge as your default browser</span></span>](/deployedge/edge-default-browser)
- [<span data-ttu-id="2b404-118">Définir Bing en tant que moteur de recherche par défaut</span><span class="sxs-lookup"><span data-stu-id="2b404-118">Make Bing your default search engine</span></span>](set-default-search-engine.md)
- [<span data-ttu-id="2b404-119">Définir Bing.com en tant que page d’accueil de votre entreprise</span><span class="sxs-lookup"><span data-stu-id="2b404-119">Set Bing.com as your enterprise homepage</span></span>](set-default-homepage.md)

## <a name="how-are-my-search-results-protected"></a><span data-ttu-id="2b404-120">Quel est le niveau de protection de mes résultats de recherche ?</span><span class="sxs-lookup"><span data-stu-id="2b404-120">How are my search results protected?</span></span>

<span data-ttu-id="2b404-121">Nous [](/azure/active-directory/) avons besoin Azure Active Directory’authentification pour accéder aux résultats à partir du cloud approuvé.</span><span class="sxs-lookup"><span data-stu-id="2b404-121">We require [Azure Active Directory](/azure/active-directory/) authentication to access results from the Trusted Cloud.</span></span> <span data-ttu-id="2b404-122">Seul est présenté le contenu auquel les utilisateurs authentifiés ont accès.</span><span class="sxs-lookup"><span data-stu-id="2b404-122">Authenticated users only see content they have access to.</span></span> <span data-ttu-id="2b404-123">Les requêtes de recherche sont dé identifiées [](https://Bing.com) et les journaux sont séparés du trafic de recherche Bing public lorsque vous utilisez Recherche Microsoft dans Bing.</span><span class="sxs-lookup"><span data-stu-id="2b404-123">Search queries are de-identified, and logs are separated from public [Bing](https://Bing.com) search traffic when you use Microsoft Search in Bing.</span></span>

## <a name="can-i-search-across-federated-organizations"></a><span data-ttu-id="2b404-124">Puis-je effectuer des recherches dans les organisations fédérées ?</span><span class="sxs-lookup"><span data-stu-id="2b404-124">Can I search across federated organizations?</span></span>

<span data-ttu-id="2b404-125">Non.</span><span class="sxs-lookup"><span data-stu-id="2b404-125">No.</span></span>

## <a name="where-can-i-get-info-about-office-365-security-compliance-and-privacy"></a><span data-ttu-id="2b404-126">Où puis-je obtenir des informations sur Office 365 sécurité, conformité et confidentialité ?</span><span class="sxs-lookup"><span data-stu-id="2b404-126">Where can I get info about Office 365 security, compliance, and privacy?</span></span>

<span data-ttu-id="2b404-127">Pour plus d’informations, voir les pages du Centre de [Office 365.](https://www.microsoft.com/TrustCenter/CloudServices/office365/default.aspx)</span><span class="sxs-lookup"><span data-stu-id="2b404-127">Details can be found on the [Trust Center pages for Office 365](https://www.microsoft.com/TrustCenter/CloudServices/office365/default.aspx).</span></span>

## <a name="can-guest-users-leverage-microsoft-search-in-my-organization"></a><span data-ttu-id="2b404-128">Les utilisateurs invités peuvent-ils tirer parti de Microsoft Search (recherche Microsoft) dans mon organisation ?</span><span class="sxs-lookup"><span data-stu-id="2b404-128">Can guest users leverage Microsoft Search in my organization?</span></span>

<span data-ttu-id="2b404-129">Microsoft 365 permet une collaboration enrichie avec des personnes extérieures à votre organisation via [l’accès invité.](/microsoft-365/solutions/collaborate-with-people-outside-your-organization)</span><span class="sxs-lookup"><span data-stu-id="2b404-129">Microsoft 365 enables rich collaboration with people outside of your organization through [guest access.](/microsoft-365/solutions/collaborate-with-people-outside-your-organization)</span></span> <span data-ttu-id="2b404-130">Ces utilisateurs pourront effectuer des opérations de recherche sur des documents, des sites, des groupes, des listes et des bibliothèques.</span><span class="sxs-lookup"><span data-stu-id="2b404-130">These users will be able to perform search operations on documents, sites, groups, lists, and libraries.</span></span> <span data-ttu-id="2b404-131">Toutefois, les utilisateurs invités ne pourront pas profiter de l’expérience recherche Microsoft complète et personnalisée et devront peut-être utiliser la zone de recherche sur la page au lieu de la zone recherche Microsoft unifiée dans l’en-tête.</span><span class="sxs-lookup"><span data-stu-id="2b404-131">However, guest users will not get the full, personalized, Microsoft Search experience and may need to leverage the on-page search box instead of the unified Microsoft Search box in the header.</span></span>