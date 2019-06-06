---
title: Sécurité relative à Microsoft Search (recherche Microsoft)
ms.author: dawholl
author: dawholl
manager: kellis
ms.date: 9/12/2018
ms.audience: Admin
ms.topic: reference
ms.service: mssearch
localization_priority: Priority
search.appverid:
- BFB160
- MET150
- MOE150
ms.assetid: 50461cb9-8707-46c1-935a-1b9608a98800
ROBOTS: NOINDEX
description: Protégez vos données d’entreprise et utilisateurs tout en fournissant des informations pour les utilisateurs ayant une autorisation pour Microsoft Search (recherche Microsoft)
ms.openlocfilehash: 4e5e23e5e1389c95d28ede66e06707f9856a3770
ms.sourcegitcommit: fe7f3dae4edba97071a4d127e8a27bdf4fa00d81
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/05/2019
ms.locfileid: "34727939"
---
# <a name="security-for-microsoft-search"></a>Sécurité relative à Microsoft Search (recherche Microsoft)

Avec la sécurité de qualité professionnelle, Microsoft Search (recherche Microsoft) conserve toujours vos utilisateurs et données protégées.


## <a name="secure-by-default"></a>Sécurise par défaut.

Microsoft Search (recherche Microsoft) garantit toujours que les requêtes soient effectuées via HTTPS. Que cette protection ait garanti que la connexion soit chiffrée de bout en bout pour une sécurité renforcée.
  
## <a name="authentication-and-authorization-with-azure-active-directory"></a>Authentification et autorisation avec Azure Active Directory

L’authentification pour Microsoft Search (recherche Microsoft) est liée à Azure Active Directory. Lorsque les utilisateurs de Microsoft Search (recherche Microsoft) passent à Bing, l’en-tête de Bing affiche également les options de connexion pour un compte Microsoft comme un professionnel ou scolaire. Si Bing ne peut pas déterminer si un utilisateur est un participant éligible, les utilisateurs peuvent accéder à la page[Explorer Microsoft Search (recherche Microsoft)](https://www.bing.com/business/explore), où ils seront redirigés automatiquement vers la page de connexion de votre organisation. 
  
Les utilisateurs peuvent accéder à Microsoft Search (recherche Microsoft) uniquement par le biais d’un compte professionnel ou scolaire. Ils doivent se connecter avec les mêmes informations d’identification qu’ils utilisent pour accéder aux services Office 365 tels que SharePoint ou Outlook. Un compte Microsoft personnel ne peut pas être utilisé pour se connecter à Microsoft Search (recherche Microsoft).
  
Les utilisateurs ne peuvent pas se connecter à Bing avec un compte Microsoft et un compte professionnel ou scolaire en même temps.
  
## <a name="single-sign-on"></a>Authentification unique

Si un utilisateur est déjà authentifié avec leur compte professionnel ou scolaire dans un autre service tel que Outlook ou SharePoint, ils êtes automatiquement connectés à Microsoft Search (recherche Microsoft) lorsqu’elles accèdent à Bing dans le même navigateur. Par ailleurs, lorsque l’utilisateur se connecte parti de Microsoft Search (recherche Microsoft), ils se déconnectent automatiquement à partir d’autres services dans le même navigateur.
  
## <a name="communicates-with-the-trusted-cloud-from-the-browser"></a>Communique avec le Cloud approuvés à partir du navigateur

Lorsqu’un utilisateur se connecte avec son travail ou compte scolaire, Bing télécharge les bibliothèques du client nécessaires sur le navigateur pour activer les résultats Microsoft Search (recherche Microsoft). Puis, quand ils recherchent le code dans le navigateur appelle le cloud Office 365 pour obtenir des résultats de travail. Pour ce faire, Microsoft Search (recherche Microsoft) utilise une API dédiée qui est niveau C (Type 1 SOC2) compatible en application Office 365 [infrastructure de conformité pour les normes et réglementations](https://download.microsoft.com/download/B/2/7/B27B3EF3-8849-4C18-8BA4-5AD755728620/Compliance%20Framework_customer%20guidance.pdf) (téléchargement PDF). Cela signifie que jamais les résultats de flux de travail et les données de travail via les systèmes de Bing non conformes. 
  
## <a name="permissions"></a>Autorisations

Les résultats travail récupérées à partir de charges de travail Office 365 telles que SharePoint et OneDrive entreprise sont coupés à la source par sécurité. Les utilisateurs ne peuvent pas voir les ressources telles que des documents Word ou présentations PowerPoint qu’ils ne peuvent pas voir et accéder via Office 365. Elles ne peuvent voir que leurs propres fichiers et les fichiers qui ont été partagés avec eux par l’auteur de manière explicite ou implicite (via un appartenance au groupe, par exemple) dans SharePoint.
  
## <a name="protects-user-queries-from-the-public-portion-of-bing"></a>Protège les requêtes de l’utilisateur à partir de la partie publique de Bing

Étant donné que les recherches Professionnel peuvent être sensibles, Microsoft Search (recherche Microsoft) a implémenté un ensemble de mesures de gestion de la confidentialité pour la gestion par la partie de résultats web public de Bing.
  
Quelle que soit la requête utilisateur contienne un ou plusieurs résultat(s) de travail dans la réponse renvoyée, les mesures suivantes sont prises:
  
- Journalisation
    
  - Tous les journaux de recherche se rapportant au trafic Microsoft Search (recherche Microsoft) sont anonymisés et stockés séparément du trafic public, non Microsoft Search (recherche Microsoft). Elles sont conservées pendant 18 mois et l’accès est restreint uniquement aux fins de débogage.
    
  - Les requêtes dans les journaux créés ne sont pas utilisées pour modèle ou en train fonctionnalités publiques comme suggestions automatiques ou recherches pour le site web public associées.
    
  - L’accès restreint est géré via divers mécanismes sécurisés, y compris les groupes de sécurité et autres couches au sein du système d’ingénierie.
    
- Historique de recherche
    
  - Une fois connecté avec un compte professionnel ou scolaire, l’historique de recherche d’un utilisateur n’est pas disponible sur d’autres ordinateurs ou appareils.
    
- Publicité
    
  - Les requêtes de recherche d’entreprise sont jamais partagées avec ou suggérées aux publicitaires.
    
  - Les journaux de publicités de recherche appartenant à Microsoft Search (recherche Microsoft) sont stockés séparément du trafic public.
    
  - Les publicités ne sont jamais des canaux ciblés à un utilisateur en fonction de leur travail d’identité ou d’organisation.
    
## <a name="gdpr"></a>RGPD

Le [billet de blog 21 mai 2018](https://blogs.microsoft.com/on-the-issues/2018/05/21/microsofts-commitment-to-gdpr-privacy-and-putting-customers-in-control-of-their-own-data/) auprès de Microsoft reflète notre engagement de mise en conformité et comment Microsoft aide les entreprises et les organisations avec leurs propres obligations de conformité RGPD. Vous pouvez trouver des détails supplémentaires dans le Microsoft [Forum aux questions du centre de gestion de la Confidentialité](https://www.microsoft.com/en-us/trustcenter/privacy/gdpr/gdpr-faqs). Les requêtes Microsoft Search (recherche Microsoft) fonctionnent sur les données organisationnelles clients client au sein de Services en ligne seront également respecter les engagements de processeur décrites dans l’Article 28 comme reflétées dans le [Forum aux questions du centre de gestion de la confidentialité](https://www.microsoft.com/en-us/trustcenter/privacy/gdpr/gdpr-faqs). Pour des requêtes à partir de Microsoft Search atteindre Bing public, Microsoft est un contrôleur des données et a implémenté mesures pour l’identifier les requêtes comme indiqué sous RGPD.


