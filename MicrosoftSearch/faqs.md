---
title: FAQ
ms.author: anfowler
author: adefowler
manager: shohara
ms.audience: Admin
ms.topic: reference
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: Trouvez les réponses à certaines des questions les plus fréquentes concernant Microsoft Search (recherche Microsoft)
ms.openlocfilehash: edfb8346263d60184d8655afa24118ed4b3e3bca
ms.sourcegitcommit: 68087149c769a7cdde80944dd9c9933d2bf4a23f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/18/2019
ms.locfileid: "38699792"
---
# <a name="frequently-asked-questions"></a>Questions fréquemment posées

Voici la liste des questions fréquemment posées.

> [!TIP]
> La réponse à votre question n’y figure pas ? Posez votre question dans les commentaires de cet article.

## <a name="is-advanced-query-understanding-supported"></a>La compréhension de recherche avancée est-elle prise en charge ?

Oui, Microsoft Search analyse l’intention des requêtes à partir d’expressions plus volumineuses. Cette fonctionnalité utilise l’AI pour découvrir les expressions superflues courantes que les utilisateurs ajoutent à leurs requêtes qui n’ont pas d’impact sur leur intention de recherche. Par exemple, lorsqu’un utilisateur recherche de *plus amples informations sur la modification de mon mot de passe*, Nous extrayons les mots moins importants de la requête et du déclencheur en fonction de ceux-ci, comme *modifier le mot de passe*.
  
Cette fonctionnalité ne remplace pas les mots clés définis dans le [Centre d’administration](https://admin.microsoft.com)365 de Microsoft.
  
## <a name="can-you-search-for-files-on-premises"></a>Pouvez-vous rechercher des fichiers en local ?

Oui. Vous pouvez effectuer des recherches dans des fichiers [SharePoint](http://sharepoint.com/) locaux si vous disposez d’un déploiement hybride de SharePoint.
  
## <a name="how-do-i-make-bing-the-default-search-engine-for-people-in-my-org"></a>Comment configurer Bing en tant que moteur de recherche par défaut pour les personnes au sein de mon organisation ?

Voici les instructions permettant de définir le moteur de recherche par défaut, la page d’accueil par défaut et le navigateur par défaut pour permettre à vos utilisateurs de tirer le meilleur parti de Microsoft Search dans [Bing](https://Bing.com):

- [Définir Microsoft Edge comme navigateur par défaut](set-default-browser.md)
- [Définir Bing en tant que moteur de recherche par défaut](set-default-search-engine.md)
- [Définir Bing.com en tant que page d’accueil de votre entreprise](set-default-homepage.md)

  
## <a name="how-are-my-search-results-protected"></a>Quel est le niveau de protection de mes résultats de recherche ?

Nous avons besoin de l’authentification [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/) pour accéder aux résultats à partir du Cloud approuvé. Seul est présenté le contenu auquel les utilisateurs authentifiés ont accès. Les requêtes de recherche sont déidentifiées et les journaux sont séparés du trafic de recherche [Bing](https://Bing.com) public. Ce niveau de protection est inédit dans le secteur.

## <a name="can-i-search-across-federated-organizations"></a>Puis-je effectuer des recherches dans les organisations fédérées ?

Non.

## <a name="where-can-i-get-info-about-office-365-and-microsoft-365-compliance-tiers-and-categories"></a>Où puis-je obtenir des informations sur les différents niveaux et catégories de conformité d’Office 365 et de Microsoft 365 ?

Les détails sont accessibles dans l’[infrastructure de conformité pour les normes et réglementations](https://download.microsoft.com/download/B/2/7/B27B3EF3-8849-4C18-8BA4-5AD755728620/Compliance%20Framework_customer%20guidance.pdf) (téléchargement PDF).

## <a name="can-users-earn-microsoft-rewards-points-with-their-work-or-school-account"></a>Les utilisateurs peuvent-ils gagner des points Microsoft Rewards avec leur compte professionnel ou scolaire ?

La Recherche Microsoft nécessite que les utilisateurs de l’entreprise se connectent avec un compte professionnel ou scolaire, mais les utilisateurs ne peuvent pas participer ou se connecter au programme Microsoft Rewards avec ces comptes. Toutefois, il existe une instance où un utilisateur de l’entreprise peut voir un gain de points Rewards. Cela peut se produire lorsqu’un utilisateur de la Recherche Microsoft dispose d’un compte Rewards qui a été créé avec un <a href="https://www.microsoft.com/welcome?rtc=1">compte Microsoft</a>. (L’adresse e-mail associée à un compte Microsoft peut être un compte Outlook.com, Hotmail.com, Gmail, Yahoo ou un compte provenant d’autres fournisseurs.) Si les utilisateurs se connectent avec leur compte professionnel et leur compte Microsoft dans la même session de navigateur, ils peuvent accumuler des points à leur compte Rewards. Les utilisateurs peuvent arrêter d’accumuler des points lorsqu’ils effectuent une recherche avec la Recherche Microsoft en effaçant leur cookies. 

