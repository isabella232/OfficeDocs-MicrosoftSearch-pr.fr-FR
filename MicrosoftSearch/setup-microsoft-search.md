---
title: Configurer la fonctionnalité Recherche Microsoft
ms.author: anfowler
author: adefowler
manager: mnirkhe
ms.date: 08/06/2019
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Priority
search.appverid:
- BFB160
- MET150
- MOE150
description: Configurer la fonctionnalité Recherche Microsoft pour la première fois.
ms.openlocfilehash: 7c80701e83fea7b9b93e4e01f98fd1eeedbfa749
ms.sourcegitcommit: c2c9e66af1038efd2849d578f846680851f9e5d2
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/27/2019
ms.locfileid: "36639498"
---
# <a name="set-up-microsoft-search"></a>Configurer la fonctionnalité Recherche Microsoft

La fonctionnalité Recherche Microsoft offre une interface conviviale qui permet aux utilisateurs de trouver des informations (telles que des fichiers et des documents, des sites internes et des outils professionnels, des utilisateurs et des groupes, des emplacements et des itinéraires, ou des conversations et des réponses) en accédant en toute sécurité à l’ensemble des sources de données, y compris les e-mails, les fichiers, les fichiers SharePoint, le contenu OneDrive et les autres ressources partagées, ainsi qu’à l’Internet de l’organisation de l’utilisateur.

Pour en savoir plus sur la fonctionnalité Recherche Microsoft, consultez [Vue d’ensemble de Recherche Microsoft](overview-microsoft-search.md).

## <a name="get-started"></a>Prise en main

La fonctionnalité Recherche Microsoft est activée par défaut pour toutes les applications Microsoft qui la prennent en charge, dans le cadre de Microsoft 365. Il suffit à l’utilisateur de se connecter avec un compte professionnel ou scolaire et d’utiliser un navigateur sur lequel Bing est défini comme fournisseur de recherche par défaut.

Vous gérez Recherche Microsoft à partir du Centre d’administration Microsoft 365.

1. Dans le Centre d’administration Microsoft 365, accédez à **Paramètres** > **Microsoft**.

**Remarque:** si vous NE voyez PAS Recherche Microsoft sous **Paramètres**, activez le commutateur **Essayer la préversion** en haut à droite d’une page du centre d’administration.

En tant qu’administrateur, vous devez tenir compte de certains éléments pour rendre l’expérience Recherche Microsoft efficace et conviviale au sein de votre organisation.

## <a name="step-1-check-access-level-of-your-users"></a>Étape 1 : Vérifier le niveau d’accès de vos utilisateurs

La fonctionnalité Recherche Microsoft respecte les paramètres de sécurité de la source du contenu. Ce que les utilisateurs voient dans les résultats de leur recherche dépend de leurs autorisations et de leurs niveaux d’accès. Vérifiez le niveau d’accès des utilisateurs de votre organisation pour veiller à ce qu’ils aient uniquement accès à du contenu autorisé.

| Service         | Description                                                                                                                                                                                                                                         |
| --------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Groupes          | [Ajouter ou supprimer des membres de groupes](https://docs.microsoft.com/office365/admin/create-groups/add-or-remove-members-from-groups)                                                                                                                     |
| Personnes          | Vous pouvez masquer certains utilisateurs d’une recherche dans votre liste d'adresses en définissant le paramètre `HiddenFromAddressListEnabled` sur `true` en utilisant l’applet de commande [Set-User](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/set-user). |
| Microsoft Teams | [Gérer l’accès des utilisateurs à Microsoft Teams](https://docs.microsoft.com/microsoftteams/user-access)                                                                                                                                                      |
| OneDrive        | [Gérer le partage](https://docs.microsoft.com/OneDrive/manage-sharing)                                                                                                                                                                                |
| SharePoint      | [Planification des autorisations](https://docs.microsoft.com/fr-FR/sharepoint/plan-your-permissions-strategy)<br> [Création des niveaux d’autorisations](https://docs.microsoft.com/fr-FR/sharepoint/how-to-create-and-edit-permission-levels)                          |
| OneNote         | Vous ne pouvez pas effectuer de recherche dans les fichiers incorporés dans OneNote. [Changer les autorisations pour un bloc-notes sur OneDrive](https://support.office.com/article/B9600CCF-045A-40E6-9913-4A7EB02869A5)                                                                    |
| Yammer          | [Paramètres de sécurité Yammer](https://docs.microsoft.com/Yammer/manage-security-and-compliance/yammer-security-settings)                                                                                                                               |

## <a name="step-2-assign-search-admin-and-search-editor"></a>Étape 2 : attribuer un administrateur et un éditeur de recherche

La fonctionnalité Recherche Microsoft vous permet de gérer le contenu et les paramètres de recherche de votre organisation en affectant ces rôles aux utilisateurs :

1. **Administrateur de recherche :** ce rôle permet de créer et de gérer le contenu des résultats de recherche et de définir les paramètres de requête pour améliorer les résultats des recherches effectuées au sein de l’organisation. L’administrateur de recherche gère la configuration de la fonctionnalité Recherche Microsoft et peut effectuer les mêmes tâches de gestion de contenu qu’un éditeur de recherche.
2. **Éditeur de recherche :** ce rôle permet de créer, de gérer et de supprimer du contenu pour la fonctionnalité Recherche Microsoft dans le Centre d’administration Microsoft 365. Un éditeur peut créer et gérer du contenu éditorial tel que des questions fréquentes et leurs réponses, des emplacements importants, ainsi que des sites et des applications fréquemment recherchés et utilisés.

Pour l’instant, les rôles d’administrateur et d’éditeur de recherche doivent être attribués par un administrateur général. Pour plus d’informations, voir [Attribuer des rôles d’administrateur](https://docs.microsoft.com/fr-FR/office365/admin/add-users/assign-admin-roles?view=o365-worldwide).

Les administrateurs de recherche ont une influence directe sur l’expérience de recherche des utilisateurs finaux, notamment sur le choix des types de résultats présentés à ceux-ci. Il peut être difficile pour une seule et même personne de choisir et de créer du contenu capable de faire autorité dans les nombreux domaines sur lesquels les utilisateurs effectuent des recherches au sein d’une organisation. Nous vous recommandons donc de tirer parti de l’expertise et des connaissances d’experts techniques et d’autres utilisateurs en les ajoutant en tant qu’éditeurs de recherche.

## <a name="step-3-make-content-easy-to-find"></a>Étape 3 : faciliter l’accès au contenu

La fonctionnalité Recherche Microsoft fournit aux administrateurs des outils qui leur permettent de créer une expérience de recherche robuste pour leurs utilisateurs. Dans la fonctionnalité Recherche Microsoft, les administrateurs peuvent créer trois types de contenus de recherche différents afin d’améliorer l’expérience de recherche et l’accessibilité du contenu :

- **Signets :** les signets sont semblables aux résultats promus de SharePoint. Ils vous permettent de placer les meilleurs résultats possibles pour les requêtes de vos utilisateurs en tête des résultats de recherche et de faciliter l’accès aux sites internes importants.
- **Questions et réponses :** les Q&R sont semblables aux questions fréquentes. Elles sont généralement présentées sous un format question/réponse. Les Q&R fournissent les réponses les plus pertinentes aux questions à visée professionnelle de vos utilisateurs.
- **Emplacements :** les emplacements sont des adresses permettant aux utilisateurs de localiser les bâtiments, les bureaux et les campus de votre organisation.

Plus vous publiez de signets, de Q&R et d’emplacements, plus vos utilisateurs en tirent parti. Cependant, s’ils sont trop nombreux, ceux-ci peuvent générer des frais de gestion importants, car ils doivent être régulièrement examinés et actualisés pour que les résultats restent pertinents et à jour.

Voici quelques exemples de contenu que vous pouvez transformer en signets pour vos utilisateurs :

- Informations relatives à l’organisation ou aux produits et services.
- Contenu informatif accessible à tous ; par exemple, informations sur l’entreprise, aide pour les applications Windows et Office, etc.
- Contenu que les membres de l’organisation ont l’habitude de rechercher dans le cadre de leurs activités professionnelles quotidiennes. Dans ce domaine, les recherches les plus courantes concernent les avantages sociaux des employés, les fiches de présence et les notes de frais, l’envoi de bons de commande et l’obtention d’aide auprès des services informatiques.

Pour créer et gérer du contenu de recherche, consultez la page [Faciliter l’accès au contenu](make-content-easy-to-find.md).

## <a name="step-4-training-and-communication"></a>Étape 4 : formation et communication

Établissez des ressources en libre-service auxquelles les employés peuvent facilement accéder par eux-mêmes. Cela allégera le fardeau qui pèse constamment sur vous et votre équipe en termes de publication de communications et de formation/auto-formation des employés. Fournissez à vos utilisateurs des communications, des FAQ, des vidéos et des webinaires ou formations enregistrées. Voici quelques liens utiles pour commencer :

- [Trouvez ce dont vous avez besoin avec la fonctionnalité Recherche Microsoft d’Office](https://support.office.com/article/find-what-you-need-with-microsoft-search-in-office-2457d4d8-48a8-4ad4-ab89-5a0657aa8446?ui=en-US&rs=en-US&ad=US)
- [Centre de formation Office 365](https://support.office.com/office-training-center)
- [Centre de recherche Microsoft](https://support.office.com/fr-FR/article/-working-title-microsoft-search-center-b8bf5a2c-7515-40a9-9a6a-b8ed382c86bc?ui=en-US&rs=en-US&ad=US)