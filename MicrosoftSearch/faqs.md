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
ms.openlocfilehash: 84f53755625e65328f8ffe8aabf78f93a9a36a22
ms.sourcegitcommit: 5151bcd8fd929ef37239b7c229e2fa33b1e0e0b7
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/13/2021
ms.locfileid: "58235866"
---
<!-- markdownlint-disable no-trailing-punctuation -->
# <a name="frequently-asked-questions"></a>Questions fréquemment posées

Voici la liste des questions fréquemment posées.

> [!TIP]
> La réponse à votre question n’y figure pas ? Posez votre question dans les commentaires de cet article.

## <a name="is-advanced-query-understanding-supported"></a>La compréhension de recherche avancée est-elle prise en charge ?

Oui, Recherche Microsoft l’intention de la requête à partir d’expressions plus grandes. Cette fonctionnalité utilise l’IA pour découvrir les expressions superflues courantes que les utilisateurs ajoutent à leurs requêtes qui n’affectent pas leur objectif de recherche. Par exemple, lorsqu’un utilisateur recherche des informations sur la modification de mon mot de *passe,* nous extrayons les mots les moins importants de la requête et le déclencheur en fonction des mots pertinents tels que le mot de passe de *modification.*
  
Cette fonctionnalité ne remplace pas les mots clés définies dans le [Centre d’administration Microsoft 365](https://admin.microsoft.com).
  
## <a name="can-you-search-for-files-on-premises"></a>Pouvez-vous rechercher des fichiers en local ?

Oui. Vous pouvez rechercher des fichiers SharePoint [locaux](http://sharepoint.com/) si vous avez un déploiement hybride de SharePoint.
  
## <a name="how-do-i-make-bing-the-default-search-engine-for-people-in-my-org"></a>Comment configurer Bing en tant que moteur de recherche par défaut pour les personnes au sein de mon organisation ?

Voici les instructions pour définir le moteur de recherche par défaut, la page d’accueil par défaut et le navigateur par défaut pour offrir à vos utilisateurs la meilleure expérience avec les Recherche Microsoft dans [Bing](https://Bing.com):

- [Définir Microsoft Edge comme navigateur par défaut](/deployedge/edge-default-browser)
- [Définir Bing en tant que moteur de recherche par défaut](set-default-search-engine.md)
- [Définir Bing.com en tant que page d’accueil de votre entreprise](set-default-homepage.md)

## <a name="how-are-my-search-results-protected"></a>Quel est le niveau de protection de mes résultats de recherche ?

Nous [](/azure/active-directory/) avons besoin Azure Active Directory’authentification pour accéder aux résultats à partir du cloud approuvé. Seul est présenté le contenu auquel les utilisateurs authentifiés ont accès. Lorsque vous utilisez Recherche Microsoft dans Bing, les requêtes de recherche sont identifiées et les journaux sont séparés du trafic de recherche [Bing](https://Bing.com) public.

## <a name="can-i-search-across-federated-organizations"></a>Puis-je effectuer des recherches dans les organisations fédérées ?

Non.

## <a name="where-can-i-get-info-about-office-365-security-compliance-and-privacy"></a>Où puis-je obtenir des informations sur Office 365 sécurité, conformité et confidentialité ?

Pour plus d’informations, voir les pages du Centre de [Office 365.](https://www.microsoft.com/TrustCenter/CloudServices/office365/default.aspx)

## <a name="can-guest-users-access-microsoft-search-in-my-organization"></a>Les utilisateurs invités peuvent-ils Recherche Microsoft dans mon organisation ?

Microsoft 365 permet une collaboration enrichie avec des personnes extérieures à votre organisation via [l’accès invité.](/microsoft-365/solutions/collaborate-with-people-outside-your-organization) Ces utilisateurs peuvent rechercher des documents, des sites, des groupes, des listes et des bibliothèques. Toutefois, les utilisateurs invités n’obtiennent pas l’expérience Recherche Microsoft complète et personnalisée et peuvent avoir besoin d’utiliser la zone de recherche sur la page au lieu de la zone de Recherche Microsoft unifiée dans l’en-tête.

## <a name="how-do-i-turn-microsoft-search-in-bing-on-or-off"></a>Comment puis-je activer Recherche Microsoft l Bing de l’autre ?

Pour la plupart des organisations, y compris les entreprises et l’éducation, les Recherche Microsoft dans Bing sont en cours d’exploitation par défaut. Pour activer Recherche Microsoft dans Bing, allez à la page [Configurations](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/configurations) dans la Centre d’administration Microsoft 365. Sous Recherche Microsoft dans Bing paramètres, sélectionnez Modifier les **paramètres** et activer Autoriser votre organisation à utiliser Recherche Microsoft dans **Bing**. Cette modification prend jusqu’à 24 heures pour prendre effet.

Si ce paramètre est éteint, les utilisateurs n’obtiennent pas de résultats internes lorsqu’ils recherchent sur Bing, Windows recherche ou dans Microsoft Edge. La Recherche Microsoft’Bing n’arrête pas ou n’empêche pas l’ajout de contenu interne à votre index de recherche. Il désactive uniquement Bing points d’entrée de Recherche Microsoft. Pour trouver des réponses et des résultats internes, les utilisateurs doivent utiliser d’autres points d’entrée, par exemple SharePoint Online ou une Office 365 app.
