---
title: Sécurité pour la recherche de Microsoft
ms.author: dawholl
author: dawholl
manager: kellis
ms.date: 9/12/2018
ms.audience: Admin
ms.topic: reference
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
ms.assetid: 50461cb9-8707-46c1-935a-1b9608a98800
description: Protéger vos données d’entreprise et les utilisateurs tout en fournissant des informations aux utilisateurs autorisés à Microsoft Search
ms.openlocfilehash: 65cf1d49e32edbb8061a06f8da7ba644c2145e24
ms.sourcegitcommit: bf52cc63b75f2e0324a716fe65da47702956b722
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/18/2019
ms.locfileid: "29378666"
---
# <a name="security-for-microsoft-search"></a><span data-ttu-id="99786-103">Sécurité pour la recherche de Microsoft</span><span class="sxs-lookup"><span data-stu-id="99786-103">Security for Microsoft Search</span></span>

<span data-ttu-id="99786-104">Sécurité de niveau entreprise, Microsoft Search conserve toujours vos utilisateurs et les données protégées.</span><span class="sxs-lookup"><span data-stu-id="99786-104">With enterprise-grade security, Microsoft Search always keeps your users and data protected.</span></span>
  
## <a name="secure-by-default"></a><span data-ttu-id="99786-105">Sécurité par défaut</span><span class="sxs-lookup"><span data-stu-id="99786-105">Secure by default</span></span>

<span data-ttu-id="99786-p101">Microsoft Search garantit toujours les requêtes sont effectuées sur HTTPS. Cette précaution garantit que la connexion est chiffré à bout en bout pour renforcer la sécurité.</span><span class="sxs-lookup"><span data-stu-id="99786-p101">Microsoft Search always ensures requests are made over HTTPS. This safeguard ensures the connection is encrypted end-to-end for enhanced security.</span></span>
  
## <a name="authentication-and-authorization-with-azure-active-directory"></a><span data-ttu-id="99786-108">Authentification et autorisation avec Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="99786-108">Authentication and authorization with Azure Active Directory</span></span>

<span data-ttu-id="99786-p102">Authentification pour Microsoft Search est liée à Azure Active Directory. Lorsque les utilisateurs de Microsoft Search accédez à Bing, le Bing en-tête affiche les options de connexion pour un compte Microsoft en tant qu’ainsi que d’un travail ou l’école compte. Si Bing ne peut pas déterminer si un utilisateur est un participant éligible, les utilisateurs peuvent accéder à la page de [Recherche de Microsoft Explorer](https://www.bing.com/business/explore) , où ils sont automatiquement redirigés vers la page de connexion de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="99786-p102">Authentication for Microsoft Search is tied to Azure Active Directory. When Microsoft Search users go to Bing, the Bing header will show sign-in options for a Microsoft account as well as a work or school account. If Bing can't determine whether a user is an eligible participant, users can go to the [Explore Microsoft Search](https://www.bing.com/business/explore) page, where they'll be automatically redirected to your organization's sign-in page.</span></span> 
  
<span data-ttu-id="99786-p103">Les utilisateurs peuvent accéder à Microsoft Search uniquement par le biais d’un compte professionnel ou de l’école. Ils doivent se connecter avec les mêmes informations d’identification d’accès aux services Office 365 tels que SharePoint ou Outlook. Un compte Microsoft personnel ne peut pas être utilisé pour se connecter à Microsoft Search.</span><span class="sxs-lookup"><span data-stu-id="99786-p103">Users can access Microsoft Search only through a work or school account. They need to sign in with the same credentials they use to access Office 365 services such as SharePoint or Outlook. A personal Microsoft account can't be used to sign in to Microsoft Search.</span></span>
  
<span data-ttu-id="99786-115">Les utilisateurs ne peuvent pas être connectés à Bing avec un compte Microsoft et un compte professionnel ou de l’école en même temps.</span><span class="sxs-lookup"><span data-stu-id="99786-115">Users can't be signed in to Bing with both a Microsoft account and a work or school account at the same time.</span></span>
  
## <a name="single-sign-on"></a><span data-ttu-id="99786-116">Authentification unique</span><span class="sxs-lookup"><span data-stu-id="99786-116">Single sign-on</span></span>

<span data-ttu-id="99786-p104">Si un utilisateur est déjà authentifié avec son compte professionnel ou de l’école dans un autre service, tel que Outlook ou SharePoint, ils allez être automatiquement connectés à Microsoft Search lorsqu’ils accèdent à Bing dans le navigateur même. En outre, lorsque l’utilisateur se connecte en dehors de Microsoft Search, ils allez automatiquement déconnectés à partir d’autres services dans le navigateur même.</span><span class="sxs-lookup"><span data-stu-id="99786-p104">If a user is already authenticated with their work or school account in another service, such as Outlook or SharePoint, they'll be automatically signed in to Microsoft Search when they go to Bing in the same browser. Also, when the user signs out of Microsoft Search, they'll be automatically signed out from other services in the same browser.</span></span>
  
## <a name="communicates-with-the-trusted-cloud-from-the-browser"></a><span data-ttu-id="99786-119">Communique avec le nuage approuvé à partir du navigateur</span><span class="sxs-lookup"><span data-stu-id="99786-119">Communicates with the Trusted Cloud from the browser</span></span>

<span data-ttu-id="99786-p105">Lorsqu’un utilisateur se connecte avec leur travail ou compte de l’école, Bing télécharge les bibliothèques clientes nécessaires pour le navigateur pour activer Microsoft Search results. Ensuite, lorsqu’ils recherchent, le code dans le navigateur appelle le nuage Office 365 pour obtenir des résultats de travail. Pour ce faire, Microsoft Search utilise une API dédiée couche C SOC2 Type 1 conforme au titre de l' Office 365 [Infrastructure pour des normes et réglementations de conformité](https://download.microsoft.com/download/B/2/7/B27B3EF3-8849-4C18-8BA4-5AD755728620/Compliance%20Framework_customer%20guidance.pdf) (téléchargement PDF). Cela signifie jamais flux de travail résultats et les données de travail par le biais de systèmes Bing non conformes.</span><span class="sxs-lookup"><span data-stu-id="99786-p105">When a user signs in with their work or school account, Bing will download the necessary client libraries to the browser to enable Microsoft Search results. Then, when they search, the in-browser code calls the Office 365 cloud to get work results. To do this, Microsoft Search uses a dedicated API that is Tier C (SOC2 Type 1) compliant pursuant to the Office 365 [Compliance Framework for Industry Standards and Regulations](https://download.microsoft.com/download/B/2/7/B27B3EF3-8849-4C18-8BA4-5AD755728620/Compliance%20Framework_customer%20guidance.pdf) (PDF download). This means work results and work data never flow through non-compliant Bing systems.</span></span> 
  
## <a name="permissions"></a><span data-ttu-id="99786-124">Autorisations</span><span class="sxs-lookup"><span data-stu-id="99786-124">Permissions</span></span>

<span data-ttu-id="99786-p106">Résultats de travail récupérés à partir de charges de travail Office 365 tels que SharePoint et OneDrive entreprise de sécurité sont limités à la source. Les utilisateurs ne peuvent pas voir les ressources telles que des documents Word ou des présentations PowerPoint qu’ils ne peuvent pas voir et accéder à Office 365. Ils peuvent voir uniquement leurs propres fichiers et qui ont été partagés avec eux à l’auteur explicitement ou implicitement (via une appartenance au groupe, par exemple) dans SharePoint.</span><span class="sxs-lookup"><span data-stu-id="99786-p106">Work results retrieved from Office 365 workloads such as SharePoint and OneDrive for Business are security trimmed at the source. Users can't see resources such as Word documents or PowerPoint presentations they can't see and access through Office 365. They can only see their own files and files that have been shared with them by the author explicitly or implicitly (through a group membership, for example) in SharePoint.</span></span>
  
## <a name="protects-user-queries-from-the-public-portion-of-bing"></a><span data-ttu-id="99786-128">Protège contre les requêtes des utilisateurs à partir de la partie publique de Bing</span><span class="sxs-lookup"><span data-stu-id="99786-128">Protects user queries from the public portion of Bing</span></span>

<span data-ttu-id="99786-129">Recherches liées au travail pouvant être sensibles, Microsoft Search a implémenté un ensemble de mesures de confiance pour comment celles-ci sont gérées par le composant de résultats web publics de Bing.</span><span class="sxs-lookup"><span data-stu-id="99786-129">Because work-related searches may be sensitive, Microsoft Search has implemented a set of trust measures for how these are handled by the public web results part of Bing.</span></span>
  
<span data-ttu-id="99786-130">Quel que soit ou non une requête utilisateur contienne un ou plusieurs résultats de travail dans la réponse renvoyée, les mesures suivantes sont prises :</span><span class="sxs-lookup"><span data-stu-id="99786-130">Regardless of whether a user query contains one or more work results in the returned response, the following measures are taken:</span></span>
  
- <span data-ttu-id="99786-131">Logging</span><span class="sxs-lookup"><span data-stu-id="99786-131">Logging</span></span>
    
  - <span data-ttu-id="99786-p107">Tous les journaux de recherche concernant le trafic Microsoft Search sont identifiés déduplication et stockés séparément du trafic non Microsoft Search public. Ils sont conservés pendant 18 mois, et l’accès est limité uniquement à des fins de débogage.</span><span class="sxs-lookup"><span data-stu-id="99786-p107">All search logs pertaining to Microsoft Search traffic are de-identified and stored separately from public, non-Microsoft Search traffic. They're retained for 18 months, and access is restricted for debugging purposes only.</span></span>
    
  - <span data-ttu-id="99786-134">Les requêtes dans ces journaux ne sont pas utilisés au modèle ou train publiques comme suggestion ou les fonctionnalités associées de recherche pour le site web public.</span><span class="sxs-lookup"><span data-stu-id="99786-134">The queries in these logs are not used to model or train public features such as autosuggest or related searches for the public web.</span></span>
    
  - <span data-ttu-id="99786-135">Accès limité est géré par le biais de plusieurs mécanismes d’informations sécurisé, y compris les groupes de sécurité et autres calques dans le système d’ingénierie.</span><span class="sxs-lookup"><span data-stu-id="99786-135">Restricted access is managed via various secure mechanisms, including security groups and other layers within the engineering system.</span></span>
    
- <span data-ttu-id="99786-136">Historique de la recherche</span><span class="sxs-lookup"><span data-stu-id="99786-136">Search history</span></span>
    
  - <span data-ttu-id="99786-137">Lorsque connecté avec un compte professionnel ou de l’école, l’historique de recherche d’un utilisateur n’est pas disponible sur les autres ordinateurs ou périphériques.</span><span class="sxs-lookup"><span data-stu-id="99786-137">When signed in with a work or school account, a user's search history won't be available on other computers or devices.</span></span>
    
- <span data-ttu-id="99786-138">Ajout de publicités</span><span class="sxs-lookup"><span data-stu-id="99786-138">Advertising</span></span>
    
  - <span data-ttu-id="99786-139">Requêtes de recherche de contenu d’entreprise ne sont jamais partagés ou suggérés aux publicitaires.</span><span class="sxs-lookup"><span data-stu-id="99786-139">Enterprise search queries are never shared with or suggested to advertisers.</span></span>
    
  - <span data-ttu-id="99786-140">Journaux d’annonces recherche se rapporte à Microsoft Search sont stockés séparément de trafic public.</span><span class="sxs-lookup"><span data-stu-id="99786-140">Search Ads logs pertaining to Microsoft Search are stored separately from public traffic.</span></span>
    
  - <span data-ttu-id="99786-141">Annonces ne sont jamais ciblés pour un utilisateur en fonction de leur identité professionnelle ou de l’organisation.</span><span class="sxs-lookup"><span data-stu-id="99786-141">Ads are never targeted to a user based on their work identity or organization.</span></span>
    
## <a name="gdpr"></a><span data-ttu-id="99786-142">RGPD</span><span class="sxs-lookup"><span data-stu-id="99786-142">GDPR</span></span>

<span data-ttu-id="99786-p108">Le [billet de blog 21 mai 2018,](https://blogs.microsoft.com/on-the-issues/2018/05/21/microsofts-commitment-to-gdpr-privacy-and-putting-customers-in-control-of-their-own-data/) à partir de Microsoft reflète notre engagement à la conformité PIBR et comment Microsoft aide les entreprises et les organisations avec leurs propres obligations de conformité PIBR. Vous trouverez des détails supplémentaires dans le [Forum aux questions de centre de gestion de la confidentialité](https://www.microsoft.com/en-us/trustcenter/privacy/gdpr/gdpr-faqs)de Microsoft. Requêtes de Microsoft Search qui fonctionnent sur les des données clients d’organisation de client dans les Services en ligne seront également engagements le processeur décrites dans l’Article 28 telle qu’elle apparaît dans le [Forum aux questions de centre de gestion de la confidentialité](https://www.microsoft.com/en-us/trustcenter/privacy/gdpr/gdpr-faqs). En ce qui concerne les requêtes à partir de Microsoft Search atteindre Bing public, Microsoft est un contrôleur de données et a mis en œuvre des mesures pour identifier des requêtes comme indiqué sous PIBR.</span><span class="sxs-lookup"><span data-stu-id="99786-p108">The [May 21, 2018, blog post](https://blogs.microsoft.com/on-the-issues/2018/05/21/microsofts-commitment-to-gdpr-privacy-and-putting-customers-in-control-of-their-own-data/) from Microsoft reflects our commitment to GDPR compliance and how Microsoft helps businesses and organizations with their own GDPR compliance obligations. You can find additional detail in the Microsoft [Trust Center FAQ](https://www.microsoft.com/en-us/trustcenter/privacy/gdpr/gdpr-faqs). Microsoft Search queries that operate against organizational customers' Customer Data within the Online Services will also meet the processor commitments outlined in Article 28 as reflected in the [Trust Center FAQ](https://www.microsoft.com/en-us/trustcenter/privacy/gdpr/gdpr-faqs). With respect to queries from Microsoft Search that go to public Bing, Microsoft is a data controller and has implemented measures to de-identify the queries as outlined under GDPR.</span></span>


