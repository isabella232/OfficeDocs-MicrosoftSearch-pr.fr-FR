---
title: Sécurité et confidentialité pour les Recherche Microsoft dans Bing
ms.author: jeffkizn
author: jeffkizn
manager: parulm
ms.audience: Admin
ms.topic: article
ms.service: mssearch
ms.localizationpriority: medium
search.appverid:
- BFB160
- MET150
- MOE150
description: Protéger les données de votre entreprise et les utilisateurs finaux tout en fournissant des informations aux utilisateurs autorisés Recherche Microsoft dans Bing
ms.openlocfilehash: bf3629b2508c705d19e3b7b772c6f3672063a6f1
ms.sourcegitcommit: cc9d743bcf5e998720ce9cd6eefb4061d913dc65
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/30/2021
ms.locfileid: "58701857"
---
# <a name="security-and-privacy-for-microsoft-search-in-bing"></a>Sécurité et confidentialité pour les Recherche Microsoft dans Bing

Grâce à des mesures de confidentialité et de sécurité améliorées, Recherche Microsoft en Bing vous aide à protéger vos utilisateurs et vos données de l’espace de travail.

## <a name="secure-by-default"></a>Sécurisé par défaut.

Recherche Microsoft dans Bing requêtes sont réalisées sur HTTPS. La connexion est chiffrée de bout en bout pour une sécurité renforcée.
  
## <a name="authentication-and-authorization-with-azure-active-directory"></a>Authentification et autorisation avec Azure Active Directory

L’authentification Recherche Microsoft dans Bing est liée à Azure Active Directory. Lorsque Recherche Microsoft les utilisateurs peuvent Bing, l’en-tête Bing affiche les options de Bing pour un compte Microsoft, ainsi qu’un compte scolaire ou scolaire. Si Bing ne peut pas déterminer si un utilisateur est un participant éligible, les utilisateurs peuvent se rendre sur la page Explorer [Recherche Microsoft,](https://www.bing.com/business/explore) où ils seront automatiquement redirigés vers la page de signature de votre organisation.

Les utilisateurs peuvent accéder à Microsoft Search (recherche Microsoft) uniquement par le biais d’un compte professionnel ou scolaire. Ils doivent se connecter avec les mêmes informations d’identification qu’ils utilisent pour accéder aux services Office 365 tels que SharePoint ou Outlook. Un compte Microsoft personnel ne peut pas être utilisé pour se connecter à Microsoft Search (recherche Microsoft).

## <a name="single-sign-on"></a>Authentification unique

Si un utilisateur est déjà authentifié avec son compte scolaire ou de travail dans un autre service, tel que Outlook ou SharePoint, il est automatiquement inscrit au même compte scolaire ou scolaire lorsqu’il passe à Bing dans le même navigateur. En outre, lorsque l’utilisateur se résigne à son compte scolaire ou scolaire, il est automatiquement signé à partir d’autres services Microsoft Office dans le même navigateur.
  
## <a name="communicates-with-the-microsoft-cloud-from-the-browser"></a>Communique avec le cloud Microsoft à partir du navigateur

Lorsqu’un utilisateur se signe avec son compte professionnel ou scolaire, Bing télécharge les bibliothèques clientes nécessaires dans le navigateur pour activer Recherche Microsoft résultats. Ensuite, lorsqu’ils recherchent, le code dans le navigateur appelle le cloud Office 365 pour obtenir des résultats de travail. Pour ce faire, Recherche Microsoft utilise une API dédiée qui est gérée conformément aux objectifs de contrôle de SSAE 18 SOC2 Type 1. Cela signifie que les résultats du travail et les données de travail ne circulent pas dans les systèmes Bing soumis à des objectifs de contrôle de traitement des données moins stricts que les résultats de travail eux-mêmes qui sont soumis lors du traitement dans Office 365 Core Online Services.
  
## <a name="permissions"></a>Autorisations

Les résultats travail récupérées à partir de charges de travail Office 365 telles que SharePoint et OneDrive entreprise sont coupés à la source par sécurité. Les utilisateurs ne peuvent pas voir les ressources telles que des documents Word ou présentations PowerPoint qu’ils ne peuvent pas voir et accéder via Office 365. Elles ne peuvent voir que leurs propres fichiers et les fichiers qui ont été partagés avec eux par l’auteur de manière explicite ou implicite (via un appartenance au groupe, par exemple) dans SharePoint.

## <a name="microsoft-search-in-bing-protects-workplace-searches"></a>Recherche Microsoft dans Bing les recherches de l’espace de travail

Lorsqu’un utilisateur entre une requête de recherche dans Recherche Microsoft dans Bing, deux demandes de recherche simultanées se produisent :

- Recherche des ressources internes de votre organisation.
- Recherche distincte des résultats publics à partir de Bing.com.

Étant donné que les recherches sur le lieu de travail peuvent être sensibles, Recherche Microsoft a implémenté un ensemble de mesures d’confiance qui décrivent comment la recherche distincte de résultats publics à partir de Bing.com est gérée.

### <a name="logging"></a>Logging

- Tous Bing de recherche .com qui se rapportent à Recherche Microsoft dans Bing trafic sont dissociés de votre identité de lieu de travail.
- Si un ensemble de restrictions ou de seuils de fréquence est atteint, ce qui nous donne la certitude que la requête n’est pas spécifique à une organisation particulière, la requête sera traitée comme décrit dans la section Recherche et intelligence artificielle de la déclaration de [confidentialité.](https://privacy.microsoft.com/privacystatement) Par exemple, ces requêtes seront utilisées pour modéliser et former des fonctionnalités publiques, telles que les opérations de débrancher automatiquement ou les recherches associées.
- Les requêtes qui ne répondent pas à ces restrictions ou seuils de fréquence seront stockées séparément du trafic public, hors Recherche Microsoft.

### <a name="advertising"></a>Publicité

Les publicités affichées Bing.com dans le cadre des recherches sur l’espace de travail sont uniquement liées au contenu des requêtes de recherche. Les publicités ne sont jamais ciblées pour les utilisateurs en fonction de leur identité professionnelle.

## <a name="gdpr"></a>RGPD

Le billet de blog du [21 mai 2018](https://blogs.microsoft.com/on-the-issues/2018/05/21/microsofts-commitment-to-gdpr-privacy-and-putting-customers-in-control-of-their-own-data/) de Microsoft reflète notre engagement en matière de conformité au R GDPR et la façon dont Microsoft aide les entreprises et les organisations avec leurs propres obligations de conformité au R GDPR. Vous trouverez des détails supplémentaires dans le FAQ du Centre [de confidentialité](https://www.microsoft.com/trustcenter/privacy/gdpr/gdpr-faqs)Microsoft.

Recherche Microsoft requêtes exécutées sur les ressources internes et les résultats renvoyés d’un client sont considérées comme des données client et, en tant que telles, respectent également les engagements du sous-processeur décrits à l’article 28, comme indiqué dans la [FAQ](https://www.microsoft.com/trustcenter/privacy/gdpr/gdpr-faqs)du Centre de gestion de la confidentialité. En ce qui concerne les requêtes provenant de Recherche Microsoft qui sont Bing publiques, Microsoft respecte ses obligations en tant que contrôleur de données.
