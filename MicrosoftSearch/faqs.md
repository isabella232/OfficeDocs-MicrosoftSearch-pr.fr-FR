---
title: FAQ
ms.author: anfowler
author: adefowler
manager: shohara
ms.date: 10/19/2018
ms.audience: Admin
ms.topic: reference
ms.service: mssearch
localization_priority: Priority
search.appverid:
- BFB160
- MET150
- MOE150
ms.assetid: cd3ee09d-58ab-4b8a-8822-fa11a1399672
ROBOTS: NoIndex
description: Trouvez les réponses à certaines des questions les plus fréquentes concernant Microsoft Search (recherche Microsoft)
ms.openlocfilehash: 3b30980c76915405767381fb3b6397468bdd1b68
ms.sourcegitcommit: c2c9e66af1038efd2849d578f846680851f9e5d2
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/27/2019
ms.locfileid: "36639499"
---
# <a name="frequently-asked-questions"></a><span data-ttu-id="53fd9-103">Questions fréquemment posées</span><span class="sxs-lookup"><span data-stu-id="53fd9-103">Frequently asked questions</span></span>

<span data-ttu-id="53fd9-104">Voici la liste des questions fréquemment posées.</span><span class="sxs-lookup"><span data-stu-id="53fd9-104">Here's a list of the most common questions.</span></span>

> [!TIP]
> <span data-ttu-id="53fd9-105">La réponse à votre question n’y figure pas ?</span><span class="sxs-lookup"><span data-stu-id="53fd9-105">Don't see your question answered here?</span></span> <span data-ttu-id="53fd9-106">Posez votre question dans les commentaires de cet article.</span><span class="sxs-lookup"><span data-stu-id="53fd9-106">Ask your question in this article's feedback.</span></span>

## <a name="is-advanced-query-understanding-supported"></a><span data-ttu-id="53fd9-107">La compréhension de recherche avancée est-elle prise en charge ?</span><span class="sxs-lookup"><span data-stu-id="53fd9-107">Is advanced query understanding supported?</span></span>

<span data-ttu-id="53fd9-p102">Oui, Microsoft Search (recherche Microsoft) analyse objectif requête à partir de phrases plus grande. Cette fonctionnalité utilise AI pour en savoir plus sur les phrases courantes superflues que les utilisateurs ajoutent à leurs requêtes qui n’ont pas d’impact sur leur objectif de recherche. Par exemple, lorsqu’un utilisateur recherche « en savoir plus sur comment modifier mon mot de passe svp» nous extrayons les mots moins importants à partir de la requête, puis déclenchons ceux pertinents par exemple, « modifier votre mot de passe ».</span><span class="sxs-lookup"><span data-stu-id="53fd9-p102">Yes, Microsoft Search parses query intent from larger phrases. This feature uses AI to learn common superfluous phrases users add to their queries that don't impact their search intent. For example, when a user searches for 'tell me more about how to change my password please' we extract the less important words from the query and trigger based on the relevant ones like 'change password.'</span></span>
  
<span data-ttu-id="53fd9-111">Cette fonctionnalité ne remplace pas l’ensemble de mots clés dans le Centre d’administration.</span><span class="sxs-lookup"><span data-stu-id="53fd9-111">This feature will not override keywords set in the Admin portal.</span></span>
  
## <a name="can-you-search-for-files-on-premises"></a><span data-ttu-id="53fd9-112">Pouvez-vous rechercher des fichiers en local ?</span><span class="sxs-lookup"><span data-stu-id="53fd9-112">Can you search for files on-premises?</span></span>

<span data-ttu-id="53fd9-113">Oui.</span><span class="sxs-lookup"><span data-stu-id="53fd9-113">Yes.</span></span> <span data-ttu-id="53fd9-114">Vous pouvez rechercher des fichiers SharePoint locaux si vous disposez d’un déploiement SharePoint hybride.</span><span class="sxs-lookup"><span data-stu-id="53fd9-114">You can search on-premises SharePoint files if you have a hybrid deployment of SharePoint.</span></span>
  
## <a name="how-do-i-make-bing-the-default-search-engine-for-people-in-my-org"></a><span data-ttu-id="53fd9-115">Comment configurer Bing en tant que moteur de recherche par défaut pour les personnes au sein de mon organisation ?</span><span class="sxs-lookup"><span data-stu-id="53fd9-115">How do I make Bing the default search engine for people in my org?</span></span>

<span data-ttu-id="53fd9-116">Voici les instructions permettant de définir le moteur de recherche, la page d’accueil et le navigateur par défaut afin d’offrir à vos utilisateurs une expérience optimale avec la Recherche Microsoft dans Bing :</span><span class="sxs-lookup"><span data-stu-id="53fd9-116">Here's the instructions for setting the default search engine, default homepage, and default browser to give your users the best experience with Microsoft Search in Bing:</span></span>

- [<span data-ttu-id="53fd9-117">Définir Microsoft Edge en tant que navigateur par défaut</span><span class="sxs-lookup"><span data-stu-id="53fd9-117">Set Edge as your default browser</span></span>](set-default-browser.md)
- [<span data-ttu-id="53fd9-118">Définir Bing en tant que moteur de recherche par défaut</span><span class="sxs-lookup"><span data-stu-id="53fd9-118">Make Bing your default search engine</span></span>](set-default-search-engine.md)
- [<span data-ttu-id="53fd9-119">Définir Bing.com en tant que page d’accueil de votre entreprise</span><span class="sxs-lookup"><span data-stu-id="53fd9-119">Set Bing.com as your enterprise homepage</span></span>](set-default-homepage.md)

  
## <a name="how-are-my-search-results-protected"></a><span data-ttu-id="53fd9-120">Quel est le niveau de protection de mes résultats de recherche ?</span><span class="sxs-lookup"><span data-stu-id="53fd9-120">How are my search results protected?</span></span>

<span data-ttu-id="53fd9-121">Nous demandons l’authentification Azure Active Directory pour accéder aux résultats à partir de Trusted Cloud.</span><span class="sxs-lookup"><span data-stu-id="53fd9-121">We require Azure Active Directory (AAD) authentication to access results from the Trusted Cloud.</span></span> <span data-ttu-id="53fd9-122">Seul est présenté le contenu auquel les utilisateurs authentifiés ont accès.</span><span class="sxs-lookup"><span data-stu-id="53fd9-122">Authenticated users only see content they have access to.</span></span> <span data-ttu-id="53fd9-123">Les requêtes de recherche ne sont pas identifiées et les journaux sont séparés du trafic de recherche public Bing.</span><span class="sxs-lookup"><span data-stu-id="53fd9-123">Search queries are de-identified and logs are separated from public Bing search traffic.</span></span> <span data-ttu-id="53fd9-124">Ce niveau de protection est inédit dans le secteur.</span><span class="sxs-lookup"><span data-stu-id="53fd9-124">This level of protection is unavailable anywhere else in the industry.</span></span>

## <a name="can-i-search-across-federated-organizations"></a><span data-ttu-id="53fd9-125">Puis-je effectuer des recherches dans les organisations fédérées ?</span><span class="sxs-lookup"><span data-stu-id="53fd9-125">Can I search across federated organizations?</span></span>

<span data-ttu-id="53fd9-126">Non.</span><span class="sxs-lookup"><span data-stu-id="53fd9-126">No.</span></span>

## <a name="where-can-i-get-info-about-office-365-and-microsoft-365-compliance-tiers-and-categories"></a><span data-ttu-id="53fd9-127">Où puis-je obtenir des informations sur les différents niveaux et catégories de conformité d’Office 365 et de Microsoft 365 ?</span><span class="sxs-lookup"><span data-stu-id="53fd9-127">Where can I get info about Office 365 and Microsoft 365 compliance tiers and categories?</span></span>

<span data-ttu-id="53fd9-128">Les détails sont accessibles dans l’[infrastructure de conformité pour les normes et réglementations](https://download.microsoft.com/download/B/2/7/B27B3EF3-8849-4C18-8BA4-5AD755728620/Compliance%20Framework_customer%20guidance.pdf) (téléchargement PDF).</span><span class="sxs-lookup"><span data-stu-id="53fd9-128">Details can be found in the [Compliance Framework for Industry Standards and Regulations](https://download.microsoft.com/download/B/2/7/B27B3EF3-8849-4C18-8BA4-5AD755728620/Compliance%20Framework_customer%20guidance.pdf) (PDF download).</span></span>