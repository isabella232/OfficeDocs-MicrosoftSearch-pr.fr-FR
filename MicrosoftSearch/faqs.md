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
ms.openlocfilehash: abaa1a232b08ba586dd6cd777f7e54c323159dee
ms.sourcegitcommit: aa7774d2bdff2bd9e1b7f51fcda90fa6b0c3a5ca
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/14/2021
ms.locfileid: "49867377"
---
<!-- markdownlint-disable no-trailing-punctuation -->
# <a name="frequently-asked-questions"></a>Questions fréquemment posées

Voici la liste des questions fréquemment posées.

> [!TIP]
> La réponse à votre question n’y figure pas ? Posez votre question dans les commentaires de cet article.

## <a name="is-advanced-query-understanding-supported"></a>La compréhension de recherche avancée est-elle prise en charge ?

Oui, Microsoft Search (recherche Microsoft) recherche l’intention de la requête à partir d’expressions plus grandes. Cette fonctionnalité utilise l’IA pour découvrir les expressions superflues courantes que les utilisateurs ajoutent à leurs requêtes qui n’ont pas d’impact sur leur objectif de recherche. Par exemple, lorsqu’un utilisateur recherche des informations sur la modification de mon mot de *passe,* nous extrayons les mots les moins importants de la requête et le déclencheur en fonction des mots pertinents tels que le mot de passe de *modification.*
  
Cette fonctionnalité ne remplacera pas les mots clés définies dans le Centre d’administration [Microsoft 365.](https://admin.microsoft.com)
  
## <a name="can-you-search-for-files-on-premises"></a>Pouvez-vous rechercher des fichiers en local ?

Oui. Vous pouvez rechercher des fichiers [SharePoint](http://sharepoint.com/) locaux si vous avez un déploiement hybride de SharePoint.
  
## <a name="how-do-i-make-bing-the-default-search-engine-for-people-in-my-org"></a>Comment configurer Bing en tant que moteur de recherche par défaut pour les personnes au sein de mon organisation ?

Voici les instructions pour définir le moteur de recherche par défaut, la page d’accueil par défaut et le navigateur par défaut pour offrir à vos utilisateurs la meilleure expérience avec Microsoft Search (recherche Microsoft) dans [Bing](https://Bing.com):

- [Définir Microsoft Edge comme navigateur par défaut](/deployedge/edge-default-browser)
- [Définir Bing en tant que moteur de recherche par défaut](set-default-search-engine.md)
- [Définir Bing.com en tant que page d’accueil de votre entreprise](set-default-homepage.md)

## <a name="how-are-my-search-results-protected"></a>Quel est le niveau de protection de mes résultats de recherche ?

Nous avons [besoin de l’authentification Azure Active Directory](https://docs.microsoft.com/azure/active-directory/) pour accéder aux résultats à partir du cloud approuvé. Seul est présenté le contenu auquel les utilisateurs authentifiés ont accès. Les requêtes de recherche sont dé identifiées et les journaux sont séparés du trafic de recherche [Bing](https://Bing.com) public lorsque vous utilisez Microsoft Search (recherche Microsoft) dans Bing.

## <a name="can-i-search-across-federated-organizations"></a>Puis-je effectuer des recherches dans les organisations fédérées ?

Non.

## <a name="where-can-i-get-info-about-office-365-security-compliance-and-privacy"></a>Où puis-je obtenir des informations sur la sécurité, la conformité et la confidentialité d’Office 365 ?

Pour plus d’informations, voir les pages du Centre de [confiance pour Office 365.](https://www.microsoft.com/TrustCenter/CloudServices/office365/default.aspx)

## <a name="can-users-earn-microsoft-rewards-points-with-their-work-or-school-account"></a>Les utilisateurs peuvent-ils gagner des points Microsoft Rewards avec leur compte professionnel ou scolaire ?

La Recherche Microsoft nécessite que les utilisateurs de l’entreprise se connectent avec un compte professionnel ou scolaire, mais les utilisateurs ne peuvent pas participer ou se connecter au programme Microsoft Rewards avec ces comptes. Toutefois, il existe une instance où un utilisateur de l’entreprise peut voir un gain de points Rewards. Cela peut se produire lorsqu’un utilisateur de la Recherche Microsoft dispose d’un compte Rewards qui a été créé avec un [compte Microsoft](https://www.microsoft.com/welcome?rtc=1). (L’adresse e-mail associée à un compte Microsoft peut être un compte Outlook.com, Hotmail.com, Gmail, Yahoo ou un compte provenant d’autres fournisseurs.) Si les utilisateurs se connectent avec leur compte professionnel et leur compte Microsoft dans la même session de navigateur, ils peuvent accumuler des points à leur compte Rewards. Les utilisateurs peuvent arrêter d’accumuler des points lorsqu’ils effectuent une recherche avec la Recherche Microsoft en effaçant leur cookies.

## <a name="can-guest-users-leverage-microsoft-search-in-my-organization"></a>Les utilisateurs invités peuvent-ils tirer parti de Microsoft Search (recherche Microsoft) dans mon organisation ?

Microsoft 365 permet une collaboration enrichie avec des personnes extérieures à votre organisation via [l’accès invité.](https://docs.microsoft.com/microsoft-365/solutions/collaborate-with-people-outside-your-organization) Ces utilisateurs pourront effectuer des opérations de recherche sur des documents, des sites, des groupes, des listes et des bibliothèques. Toutefois, les utilisateurs invités ne pourront pas profiter de l’expérience recherche Microsoft complète et personnalisée et devront peut-être utiliser la zone de recherche sur la page au lieu de la zone recherche Microsoft unifiée dans l’en-tête.
