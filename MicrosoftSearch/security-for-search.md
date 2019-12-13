---
title: Sécurité et confidentialité pour Microsoft Search dans Bing
ms.author: anfowler
author: adefowler
manager: shohara
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: Protégez les données et les utilisateurs finaux de votre entreprise tout en fournissant des informations aux utilisateurs autorisés à l’aide de Microsoft Search dans Bing
ms.openlocfilehash: d3d8822b68fc730885e973c0c24c52070d50eba8
ms.sourcegitcommit: f4cb37fdf85b895337caee827fb72b5b7fcaa8ad
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/12/2019
ms.locfileid: "39995386"
---
# <a name="security-and-privacy-for-microsoft-search-in-bing"></a>Sécurité et confidentialité pour Microsoft Search dans Bing

Avec des mesures de confidentialité et de sécurité améliorées, Microsoft Search dans Bing contribue à protéger vos utilisateurs et vos données d’espace de travail.

## <a name="secure-by-default"></a>Sécurise par défaut.

Les requêtes Microsoft Search dans Bing sont effectuées via HTTPs. La connexion est chiffrée de bout en bout pour renforcer la sécurité.
  
## <a name="authentication-and-authorization-with-azure-active-directory"></a>Authentification et autorisation avec Azure Active Directory

L’authentification pour Microsoft Search dans Bing est liée à Azure Active Directory. Lorsque les utilisateurs de Microsoft Search accèdent à Bing, l’en-tête Bing affiche les options de connexion pour un compte Microsoft, ainsi qu’un compte professionnel ou scolaire. Si Bing ne peut pas déterminer si un utilisateur est un participant éligible, les utilisateurs peuvent accéder à la page [Explorer Microsoft Search](https://www.bing.com/business/explore) , où ils sont automatiquement redirigés vers la page de connexion de votre organisation.
 
Les utilisateurs peuvent accéder à Microsoft Search (recherche Microsoft) uniquement par le biais d’un compte professionnel ou scolaire. Ils doivent se connecter avec les mêmes informations d’identification qu’ils utilisent pour accéder aux services Office 365 tels que SharePoint ou Outlook. Un compte Microsoft personnel ne peut pas être utilisé pour se connecter à Microsoft Search (recherche Microsoft).
    
## <a name="single-sign-on"></a>Authentification unique

Si un utilisateur est déjà authentifié avec son compte professionnel ou scolaire dans un autre service, tel qu’Outlook ou SharePoint, il est automatiquement connecté au même compte professionnel ou scolaire lorsqu’il accède à Bing dans le même navigateur. De même, lorsque l’utilisateur se déconnecte de son compte professionnel ou scolaire, il se déconnecte automatiquement des autres services Microsoft Office dans le même navigateur.
  
## <a name="communicates-with-the-microsoft-cloud-from-the-browser"></a>Communique avec Microsoft Cloud à partir du navigateur

Lorsqu’un utilisateur se connecte avec son compte professionnel ou scolaire, Bing télécharge les bibliothèques client nécessaires dans le navigateur pour activer les résultats de la recherche Microsoft. Ensuite, lorsqu’ils recherchent, le code dans le navigateur appelle le nuage Office 365 pour obtenir des résultats. Pour ce faire, Microsoft Search utilise une API dédiée qui est conforme à la couche C (SOC2 type 1) conformément à Office 365 [Compliance Framework for Industry Standards and Regulations]https://download.microsoft.com/download/B/2/7/B27B3EF3-8849-4C18-8BA4-5AD755728620/Compliance%20Framework_customer%20guidance.pdf) (téléchargement PDF). Cela signifie que les résultats de travail et les données de travail ne transitent jamais via les systèmes Bing non conformes.
  
## <a name="permissions"></a>Autorisations

Les résultats travail récupérées à partir de charges de travail Office 365 telles que SharePoint et OneDrive entreprise sont coupés à la source par sécurité. Les utilisateurs ne peuvent pas voir les ressources telles que des documents Word ou présentations PowerPoint qu’ils ne peuvent pas voir et accéder via Office 365. Elles ne peuvent voir que leurs propres fichiers et les fichiers qui ont été partagés avec eux par l’auteur de manière explicite ou implicite (via un appartenance au groupe, par exemple) dans SharePoint.

## <a name="microsoft-search-in-bing-protects-workplace-searches"></a>Microsoft Search dans Bing protège les recherches sur un lieu de travail

Lorsqu’un utilisateur entre une requête de recherche dans Microsoft Search dans Bing, deux requêtes de recherche simultanées se produisent :

- Une recherche des ressources internes de votre organisation.
- Une recherche distincte des résultats publics à partir de Bing.com.

Étant donné que les recherches Workplace peuvent être sensibles, Microsoft Search a implémenté un ensemble de mesures d’approbation qui décrivent le mode de gestion de la recherche séparée des résultats publics d’Bing.com.

### <a name="logging"></a>Logging

<Need an intro paragraph here>

- Tous les journaux de recherche Bing.com relatifs à Microsoft Search dans le trafic Bing sont désassociés à l’identité de votre espace de travail.
- Si un ensemble de restrictions ou de seuils de fréquence est atteint, ce qui nous donne la certitude que la requête n’est pas propre à une organisation particulière, la requête est traitée comme décrit dans la section recherche et intelligence artificielle de la [déclaration de confidentialité](https://privacy.microsoft.com/privacystatement). Par exemple, ces requêtes seront utilisées pour modéliser et former des fonctionnalités publiques, telles que des suggestions automatiques ou des recherches associées.
- Les requêtes qui ne répondent pas à ces restrictions ou seuils de fréquence seront stockées séparément du trafic public, hors Recherche Microsoft.

### <a name="advertising"></a>Publicité

La publicité affichée sur Bing.com dans le cadre des recherches Workplace est uniquement liée au contenu des requêtes de recherche. Les publicités ne sont jamais ciblées pour les utilisateurs en fonction de leur identité professionnelle.
     
## <a name="gdpr"></a>RGPD

Le [21 mai, 2018,](https://blogs.microsoft.com/on-the-issues/2018/05/21/microsofts-commitment-to-gdpr-privacy-and-putting-customers-in-control-of-their-own-data/) billet de blog de Microsoft reflète notre engagement envers la conformité RGPD et la façon dont Microsoft aide les entreprises et les organisations à respecter leurs obligations de conformité RGPD. Vous trouverez des détails supplémentaires dans le [Forum aux questions du centre](https://www.microsoft.com/trustcenter/privacy/gdpr/gdpr-faqs)de gestion de la confidentialité Microsoft. 

Les requêtes Microsoft Search exécutées sur les ressources internes d’un client et les résultats renvoyés sont considérées comme des données client et, en tant que telles, satisfont également aux engagements de processeur décrits dans l’article 28, comme indiqué dans le [Forum aux questions du centre](https://www.microsoft.com/trustcenter/privacy/gdpr/gdpr-faqs)de gestion de la confidentialité. En ce qui concerne les requêtes de Microsoft Search qui accèdent à public Bing, Microsoft respecte ses obligations RGPD comme un contrôleur de données.

