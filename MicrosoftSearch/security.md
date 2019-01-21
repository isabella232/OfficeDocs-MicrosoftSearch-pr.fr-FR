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
# <a name="security-for-microsoft-search"></a>Sécurité pour la recherche de Microsoft

Sécurité de niveau entreprise, Microsoft Search conserve toujours vos utilisateurs et les données protégées.
  
## <a name="secure-by-default"></a>Sécurité par défaut

Microsoft Search garantit toujours les requêtes sont effectuées sur HTTPS. Cette précaution garantit que la connexion est chiffré à bout en bout pour renforcer la sécurité.
  
## <a name="authentication-and-authorization-with-azure-active-directory"></a>Authentification et autorisation avec Azure Active Directory

Authentification pour Microsoft Search est liée à Azure Active Directory. Lorsque les utilisateurs de Microsoft Search accédez à Bing, le Bing en-tête affiche les options de connexion pour un compte Microsoft en tant qu’ainsi que d’un travail ou l’école compte. Si Bing ne peut pas déterminer si un utilisateur est un participant éligible, les utilisateurs peuvent accéder à la page de [Recherche de Microsoft Explorer](https://www.bing.com/business/explore) , où ils sont automatiquement redirigés vers la page de connexion de votre organisation. 
  
Les utilisateurs peuvent accéder à Microsoft Search uniquement par le biais d’un compte professionnel ou de l’école. Ils doivent se connecter avec les mêmes informations d’identification d’accès aux services Office 365 tels que SharePoint ou Outlook. Un compte Microsoft personnel ne peut pas être utilisé pour se connecter à Microsoft Search.
  
Les utilisateurs ne peuvent pas être connectés à Bing avec un compte Microsoft et un compte professionnel ou de l’école en même temps.
  
## <a name="single-sign-on"></a>Authentification unique

Si un utilisateur est déjà authentifié avec son compte professionnel ou de l’école dans un autre service, tel que Outlook ou SharePoint, ils allez être automatiquement connectés à Microsoft Search lorsqu’ils accèdent à Bing dans le navigateur même. En outre, lorsque l’utilisateur se connecte en dehors de Microsoft Search, ils allez automatiquement déconnectés à partir d’autres services dans le navigateur même.
  
## <a name="communicates-with-the-trusted-cloud-from-the-browser"></a>Communique avec le nuage approuvé à partir du navigateur

Lorsqu’un utilisateur se connecte avec leur travail ou compte de l’école, Bing télécharge les bibliothèques clientes nécessaires pour le navigateur pour activer Microsoft Search results. Ensuite, lorsqu’ils recherchent, le code dans le navigateur appelle le nuage Office 365 pour obtenir des résultats de travail. Pour ce faire, Microsoft Search utilise une API dédiée couche C SOC2 Type 1 conforme au titre de l' Office 365 [Infrastructure pour des normes et réglementations de conformité](https://download.microsoft.com/download/B/2/7/B27B3EF3-8849-4C18-8BA4-5AD755728620/Compliance%20Framework_customer%20guidance.pdf) (téléchargement PDF). Cela signifie jamais flux de travail résultats et les données de travail par le biais de systèmes Bing non conformes. 
  
## <a name="permissions"></a>Autorisations

Résultats de travail récupérés à partir de charges de travail Office 365 tels que SharePoint et OneDrive entreprise de sécurité sont limités à la source. Les utilisateurs ne peuvent pas voir les ressources telles que des documents Word ou des présentations PowerPoint qu’ils ne peuvent pas voir et accéder à Office 365. Ils peuvent voir uniquement leurs propres fichiers et qui ont été partagés avec eux à l’auteur explicitement ou implicitement (via une appartenance au groupe, par exemple) dans SharePoint.
  
## <a name="protects-user-queries-from-the-public-portion-of-bing"></a>Protège contre les requêtes des utilisateurs à partir de la partie publique de Bing

Recherches liées au travail pouvant être sensibles, Microsoft Search a implémenté un ensemble de mesures de confiance pour comment celles-ci sont gérées par le composant de résultats web publics de Bing.
  
Quel que soit ou non une requête utilisateur contienne un ou plusieurs résultats de travail dans la réponse renvoyée, les mesures suivantes sont prises :
  
- Logging
    
  - Tous les journaux de recherche concernant le trafic Microsoft Search sont identifiés déduplication et stockés séparément du trafic non Microsoft Search public. Ils sont conservés pendant 18 mois, et l’accès est limité uniquement à des fins de débogage.
    
  - Les requêtes dans ces journaux ne sont pas utilisés au modèle ou train publiques comme suggestion ou les fonctionnalités associées de recherche pour le site web public.
    
  - Accès limité est géré par le biais de plusieurs mécanismes d’informations sécurisé, y compris les groupes de sécurité et autres calques dans le système d’ingénierie.
    
- Historique de la recherche
    
  - Lorsque connecté avec un compte professionnel ou de l’école, l’historique de recherche d’un utilisateur n’est pas disponible sur les autres ordinateurs ou périphériques.
    
- Ajout de publicités
    
  - Requêtes de recherche de contenu d’entreprise ne sont jamais partagés ou suggérés aux publicitaires.
    
  - Journaux d’annonces recherche se rapporte à Microsoft Search sont stockés séparément de trafic public.
    
  - Annonces ne sont jamais ciblés pour un utilisateur en fonction de leur identité professionnelle ou de l’organisation.
    
## <a name="gdpr"></a>RGPD

Le [billet de blog 21 mai 2018,](https://blogs.microsoft.com/on-the-issues/2018/05/21/microsofts-commitment-to-gdpr-privacy-and-putting-customers-in-control-of-their-own-data/) à partir de Microsoft reflète notre engagement à la conformité PIBR et comment Microsoft aide les entreprises et les organisations avec leurs propres obligations de conformité PIBR. Vous trouverez des détails supplémentaires dans le [Forum aux questions de centre de gestion de la confidentialité](https://www.microsoft.com/en-us/trustcenter/privacy/gdpr/gdpr-faqs)de Microsoft. Requêtes de Microsoft Search qui fonctionnent sur les des données clients d’organisation de client dans les Services en ligne seront également engagements le processeur décrites dans l’Article 28 telle qu’elle apparaît dans le [Forum aux questions de centre de gestion de la confidentialité](https://www.microsoft.com/en-us/trustcenter/privacy/gdpr/gdpr-faqs). En ce qui concerne les requêtes à partir de Microsoft Search atteindre Bing public, Microsoft est un contrôleur de données et a mis en œuvre des mesures pour identifier des requêtes comme indiqué sous PIBR.


