---
title: Configurer la fonctionnalité **Recherche Microsoft**
ms.author: anfowler
author: adefowler
manager: mnirkhe
ms.date: 05/30/2019
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Priority
search.appverid:
- BFB160
- MET150
- MOE150
description: Configurer la fonctionnalité Recherche Microsoft pour la première fois.
ms.openlocfilehash: c95cc0d11d60e3d4d9a509dc691c01858ede7262
ms.sourcegitcommit: 9df9b1a5f83c9fbe62900df183bee239a8ea6d91
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/14/2019
ms.locfileid: "34947742"
---
# <a name="set-up-microsoft-search"></a>Configurer la fonctionnalité Recherche Microsoft

La fonctionnalité **Recherche Microsoft** offre une interface conviviale qui permet aux utilisateurs de trouver des informations (telles que des fichiers et des documents, des sites internes et des outils professionnels, des utilisateurs et des groupes, des emplacements et des itinéraires, ou des conversations et des réponses) en accédant en toute sécurité à l’ensemble des sources de données, y compris les e-mails, les fichiers, les fichiers SharePoint, le contenu OneDrive et les autres ressources partagées, ainsi qu’à l’Internet de l’organisation de l’utilisateur.

Pour en savoir plus sur la fonctionnalité **Recherche Microsoft**, consultez [Vue d’ensemble de Recherche Microsoft](overview-microsoft-search.md).

## <a name="get-started"></a>Prise en main

La fonctionnalité **Recherche Microsoft** est activée par défaut pour toutes les applications Microsoft qui la prennent en charge, dans le cadre de Microsoft 365. Il suffit à l’utilisateur de se connecter avec un compte professionnel ou scolaire et d’utiliser un navigateur sur lequel Bing est défini comme fournisseur de recherche par défaut.

Vous administrez **Recherche Microsoft** à partir du **Centre d’administration Microsoft 365**. Connectez-vous en utilisant votre ID de connexion avec les informations d’identification d’administrateur, puis, dans la liste des applications Office 365, sélectionnez la vignette **Administrateur** (cliquez sur l’icône du **lanceur d’applications** dans l’angle supérieur gauche de la liste des applications). Dans le **Centre d’administration Microsoft 365**, sélectionnez **Recherche Microsoft** sous **Paramètres** dans le volet de navigation de gauche. 

**Remarque:** si vous NE voyez PAS **Recherche Microsoft** sous **Paramètres** dans le **Centre d’administration Microsoft 365**, activez le commutateur **Essayer la préversion** en haut à droite dans le centre d’administration. 

En tant qu’administrateur, vous devez tenir compte de certains éléments pour rendre l’expérience **Recherche Microsoft** efficace et conviviale au sein de votre organisation.

## <a name="step-1-check-access-level-of-your-users"></a>Étape 1 : Vérifier le niveau d’accès de vos utilisateurs

La fonctionnalité **Recherche Microsoft** respecte les paramètres de sécurité de la source du contenu. Ce que les utilisateurs voient dans les résultats de leur recherche dépend de leurs autorisations et de leurs niveaux d’accès. Vérifiez le niveau d’accès des utilisateurs de votre organisation pour veiller à ce qu’ils aient uniquement accès à du contenu autorisé.

Découvrez-en plus sur la [planification des autorisations](https://docs.microsoft.com/fr-FR/sharepoint/plan-your-permissions-strategy) et la [création de niveaux d’autorisation](https://docs.microsoft.com/fr-FR/sharepoint/how-to-create-and-edit-permission-levels).

## <a name="step-2-assign-search-admin-and-search-editor"></a>Étape 2 : Attribuer un administrateur et un éditeur de recherche

Deux nouveaux rôles ont été ajoutés au **Centre d’administration Microsoft** : administrateur de recherche et éditeur de recherche.  L’administrateur général, qui bénéficie de tous les privilèges, affecte des rôles d’administrateur aux utilisateurs, notamment le rôle d’administrateur de recherche. Les administrateurs de recherche peuvent déléguer les rôles Administrateur de recherche ou Éditeur de recherche à d’autres utilisateurs. Pour plus d’informations sur les différents rôles d’administrateur, consultez l’article [À propos des rôles d’administrateur Office 365](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles?view=o365-worldwide).

**Remarque :** ces deux nouveaux rôles (administrateur de recherche et éditeur de recherche) ne sont disponibles que dans le **Centre d’administration Microsoft 365**, pas dans le portail d’administration hérité. 

Les administrateurs de recherche ont une influence directe sur l’expérience de recherche des utilisateurs finaux, notamment sur le choix des types de résultats présentés à ceux-ci. Il peut être difficile pour une seule et même personne de choisir et de créer du contenu capable de faire autorité dans les nombreux domaines sur lesquels les utilisateurs effectuent des recherches au sein d’une organisation. Nous vous recommandons donc de tirer parti de l’expertise et des connaissances d’experts techniques et d’autres utilisateurs en les ajoutant en tant qu’éditeurs. 

La fonctionnalité **Recherche Microsoft** vous permet de gérer le contenu et les paramètres de recherche de votre organisation à l’aide de deux nouveaux rôles :
1. **Administrateur de recherche :** ce rôle permet de créer et de gérer le contenu des résultats de recherche et de définir les paramètres de requête pour améliorer les résultats des recherches effectuées au sein de l’organisation. L’administrateur de recherche gère la configuration de la fonctionnalité **Recherche Microsoft** et désigne les éditeurs de recherche pour créer le contenu.
2. **Éditeur de recherche :** ce rôle permet de créer, de gérer et de supprimer du contenu pour la fonctionnalité **Recherche Microsoft** dans le Centre d’administration Microsoft 365. Un éditeur peut créer et gérer du contenu éditorial tel que des questions fréquentes et leurs réponses, des emplacements importants, des sites et des applications fréquemment recherchés et utilisés, etc. Il n’a toutefois pas accès à la gestion des paramètres de recherche.

Pour attribuer des rôles d’administrateur, consultez [Attribuer des rôles d’administrateur dans Office 365 pour les entreprises](https://docs.microsoft.com/fr-FR/office365/admin/add-users/assign-admin-roles?view=o365-worldwide).

## <a name="step-3-make-content-easy-to-find"></a>Étape 3 : Faciliter l’accès au contenu 

La fonctionnalité **Recherche Microsoft** fournit aux administrateurs des outils qui leur permettent de créer une expérience de recherche robuste pour leurs utilisateurs. Dans la fonctionnalité **Recherche Microsoft**, les administrateurs peuvent créer trois types de contenus de recherche différents afin d’améliorer l’expérience de recherche et l’accessibilité du contenu :
- **Signet :** les signets sont semblables aux résultats promus de SharePoint. Ils vous permettent de placer les meilleurs résultats possibles pour les requêtes de vos utilisateurs en tête des résultats de recherche et de faciliter l’accès aux sites internes importants. 
- **Questions et réponses :** les Q&R sont semblables aux questions fréquentes. Elles sont généralement présentées sous un format question/réponse. Les Q&R fournissent les réponses les plus pertinentes aux questions à visée professionnelle de vos utilisateurs.
- **Emplacement :** les emplacements sont des adresses permettant aux utilisateurs de localiser les bâtiments, les bureaux et les campus de votre organisation. 

Plus vous publiez de signets, de Q&R et d’emplacements, plus vos utilisateurs en tirent parti. Cependant, s’ils sont trop nombreux, ceux-ci peuvent générer des frais de gestion importants, car ils doivent être régulièrement examinés et actualisés pour que les résultats restent pertinents et à jour.

Voici quelques exemples de contenu que vous pouvez transformer en signets pour vos utilisateurs :
- Informations relatives à l’organisation ou aux produits et services.
- Contenu informatif accessible à tous ; par exemple, informations sur l’entreprise, aide pour les applications Windows et Office, etc. 
- Contenu que les membres de l’organisation ont l’habitude de rechercher dans le cadre de leurs activités professionnelles quotidiennes. Dans ce domaine, les recherches les plus courantes concernent les avantages sociaux des employés, les fiches de présence et les notes de frais, l’envoi de bons de commande et l’obtention d’aide auprès des services informatiques. 

Pour créer et gérer du contenu de recherche, consultez [Faciliter l’accès au contenu](make-content-easy-to-find.md).

## <a name="step-4-test-single-sign-on"></a>Étape 4 : Tester l’authentification unique
La fonctionnalité **Recherche Microsoft** utilise Azure Active Directory (AAD) pour authentifier et autoriser l’accès aux données de votre organisation.  Cela signifie que vos utilisateurs sont automatiquement connectés à votre compte professionnel ou scolaire lorsque vous êtes connecté à une application Office 365 ou Windows 10.

Nous recommandons aux utilisateurs de la fonctionnalité **Recherche Microsoft** d’avoir recours à l’authentification unique car celle-ci réduit le nombre d’invitations à se connecter. Il est conseillé aux administrateurs de tester l’authentification unique sur un petit groupe d’utilisateurs afin d’identifier les éventuels problèmes de blocage de la configuration. 

Pour les utilisateurs de Chrome sous Windows 10, l’authentification unique ne fonctionne que lorsque l’extension de connexion Windows 10 et AAD pour Chrome est installée. Une fois l’extension Chrome installée, vous pouvez l’utiliser pour vous authentifier facilement auprès d’AAD lors de la connexion à des sites pris en charge, comme Office 365 et Bing. Cette fonctionnalité est réservée aux utilisateurs autorisés. 

Pour télécharger et installer l’extension de connexion Windows 10 et AAD pour Chrome, accédez à [Chrome Web Store](https://go.microsoft.com/fwlink/?linkid=2090961).

## <a name="step-5-training-and-communication"></a>Étape 5 : Formation et communication
Établissez des ressources en libre-service auxquelles les employés peuvent facilement accéder par eux-mêmes. Cela allégera le fardeau qui pèse constamment sur vous et votre équipe en termes de publication de communications et de formation/auto-formation des employés. Fournissez à vos utilisateurs des communications, des FAQ, des vidéos et des webinaires ou formations enregistrées. Voici quelques liens utiles pour commencer :
- [Trouvez ce dont vous avez besoin avec la fonctionnalité Recherche Microsoft d’Office](https://support.office.com/article/find-what-you-need-with-microsoft-search-in-office-2457d4d8-48a8-4ad4-ab89-5a0657aa8446?ui=en-US&rs=en-US&ad=US)
- [Centre de formation Office 365](https://support.office.com/office-training-center)
- 
  [Centre de recherche Microsoft](https://support.office.com/fr-FR/article/-working-title-microsoft-search-center-b8bf5a2c-7515-40a9-9a6a-b8ed382c86bc?ui=en-US&rs=en-US&ad=US)

## <a name="trying-out-microsoft-search-in-bing"></a>Essayer la fonctionnalité **Recherche Microsoft** dans Bing 
L’administrateur de la fonctionnalité **Recherche Microsoft** peut désactiver celle-ci dans Bing. Lorsqu’elle est désactivée, les utilisateurs n’ont pas accès au contenu de l’organisation dans le cadre de la recherche Bing. Par défaut, la fonctionnalité **Recherche Microsoft** est activée dans Bing. Pour une meilleure expérience utilisateur, nous vous recommandons de ne pas désactiver la fonctionnalité **Recherche Microsoft** dans Bing. 

Si vous souhaitez essayer la fonctionnalité **Recherche Microsoft** sur un locataire test ou tester l’expérience de recherche avant de la mettre à la disposition de tous les utilisateurs, vous pouvez la désactiver.
Pour activer/désactiver la fonctionnalité **Recherche Microsoft** dans Bing, accédez à **Services et compléments** dans le **Centre d’administration Microsoft 365** et activez/désactivez **Recherche Microsoft dans Bing**.
