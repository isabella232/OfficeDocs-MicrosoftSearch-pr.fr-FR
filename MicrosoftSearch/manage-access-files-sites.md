---
title: Gérer l’accès aux fichiers et aux sites
ms.author: dawholl
author: dawholl
manager: kellis
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: Vue d’ensemble de la façon dont les administrateurs peuvent s’assurer que l’accès aux sites et aux fichiers est correctement restreint au sein de leur organisation.
ms.openlocfilehash: c19442e1d89ddfe65a772213a8b0225ca680d699
ms.sourcegitcommit: ca5ee826ba4f4bb9b9baabc9ae8a130011c2a3d0
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/15/2021
ms.locfileid: "59375715"
---
# <a name="manage-access-to-files-and-sites"></a>Gérer l’accès aux fichiers et aux sites

Tous les fichiers ou sites ne doivent pas être disponibles pour tous les membres de votre organisation. Les administrateurs et les utilisateurs peuvent gérer l’accès aux informations sensibles ou confidentielles à l’aide de solutions qui permettent de résoudre au mieux leurs problèmes spécifiques. Si les contrôles d’accès adéquats ne sont pas appliqués de manière cohérente, cela peut entraîner un « partage de partage ». En rendant plus facile la recherche d’informations partagées au sein de votre organisation, les fichiers et les sites avec des restrictions incorrectes sont accessibles par inadvertance à l’aide de Recherche Microsoft.

Les administrateurs de recherche ne peuvent pas résoudre ces problèmes de partage. Les fichiers et les sites sans accès restreint seront découverts dans les résultats de recherche internes et via d’autres moyens de découverte. Toutefois, lorsque des contrôles pour empêcher le partage sont en place, toutes les voies, y compris la recherche, sont fermées.

## <a name="solutions-to-prevent-oversharing"></a>Solutions pour empêcher le partage

Utilisez les outils, stratégies et techniques ci-dessous pour restreindre ou obscurcir l’accès aux informations afin d’empêcher le partage. L’implémentation de ces solutions nécessitera probablement un accès administrateur global, de conformité ou de sécurité. Nous recommandons également une campagne interne pour informer vos utilisateurs sur la façon de sécuriser, d’étiqueter et d’autoriser correctement leurs sites et fichiers.

### <a name="public-sites-or-sites-with-public-groups-as-owners"></a>Sites publics ou sites avec des groupes publics en tant que propriétaires

Les fichiers peuvent être partagés avec tout le monde via des sites publics ou des sites avec des groupes publics en tant que propriétaires. Les étiquettes de sensibilité peuvent empêcher les utilisateurs de créer des groupes ou des sites publics. Pour plus d’informations sur la configuration de toutes les étiquettes pour créer des groupes/sites privés et l’établissement d’une étiquette pour les groupes/sites, voir Utiliser des étiquettes de niveau de sensibilité pour protéger le contenu dans [les sites Microsoft Teams, Microsoft 365 Groups](/microsoft-365/compliance/sensitivity-labels-teams-groups-sites)et SharePoint.

Une autre option consiste à contrôler qui peut créer des groupes Microsoft 365 de votre organisation. Pour plus d’informations, voir Créer un groupe pour les utilisateurs qui doivent [créer Microsoft 365 groupes.](/microsoft-365/solutions/manage-creation-of-groups#step-1-create-a-group-for-users-who-need-to-create-microsoft-365-groups)

Lorsque vous implémentez l’une de ces solutions, nous vous suggérons également de configurer un processus pour que les utilisateurs demandent la création de groupes publics et informent vos utilisateurs de la modification.

Si la restriction de la possibilité de créer des groupes n’est pas possible pour votre organisation, vous pouvez surveiller les activités, y compris la création de groupes, par le biais de l’audit. Pour plus d’informations sur l’audit de base et avancé, voir [solutions d’audit dans Microsoft 365](/microsoft-365/compliance/auditing-solutions-overview).

### <a name="shared-files"></a>Fichiers partagés

Pour restreindre l’accès à tous les fichiers classés comme sensibles à l’entreprise, vous pouvez définir et appliquer des classifications de données pour votre organisation. Des exemples de données doivent être collectés pour vous aider à former les nouveaux classifieurs. Pour plus d’informations sur les conditions préalables et les autorisations, voir [En savoir plus sur la classification des données.](/microsoft-365/compliance/data-classification-overview)

Pour restreindre l’accès aux fichiers aux membres d’un groupe spécifique, comme les cadres, vous pouvez créer des étiquettes personnalisées limitées à un groupe de sécurité. Ensuite, lorsqu’un membre du groupe de sécurité applique l’étiquette, il restreint automatiquement l’accès au groupe. Pour en savoir plus [](/microsoft-365/compliance/create-sensitivity-labels) sur les étiquettes personnalisées, voir Créer et configurer des étiquettes de confidentialité et leurs stratégies et restreindre l’accès au contenu à l’aide d’étiquettes de confidentialité pour appliquer le [chiffrement.](/microsoft-365/compliance/encryption-sensitivity-labels)

Pour s’assurer que les documents et les e-mails sont correctement étiquetés, les administrateurs peuvent également définir une stratégie d’étiquette par défaut et obliger les utilisateurs à les étiqueter. Pour plus d’informations, consultez [Demander aux utilisateurs d'appliquer une étiquette à leurs e-mails et documents](/microsoft-365/compliance/sensitivity-labels-office-apps#require-users-to-apply-a-label-to-their-email-and-documents).

Vous pouvez également réduire le partage de fichiers en empêchant l’apparition de fichiers récents lors de la recherche. Cette fonction peut être effectuée au niveau d’un groupe ou pour tous les membres de votre organisation. Pour empêcher l’apparition de fichiers récents pour un groupe, voir [Personnalisation de](/graph/insights-customize-item-insights-privacy)la confidentialité des informations sur les éléments dans Microsoft Graph . Un membre du groupe peut voir ses propres fichiers récents, mais d’autres personnes obtiennent un message qui indique qu’aucun résultat n’est trouvé. Pour désactiver les fichiers récents pour tous les membres de votre organisation, vous devez désactiver la Delve. Pour plus d’informations, voir [Contrôler l’accès Delve](/sharepoint/delve-for-office-365-admins#control-access-to-delve).

> [!Note]
> Les utilisateurs pourront toujours trouver des fichiers partagés avec eux dans Recherche Microsoft résultats. La personnalisation des informations sur les éléments ou la Delve empêche uniquement les fichiers d’apparaître dans la liste des fichiers récents d’un utilisateur.

### <a name="sites-and-files-between-groups"></a>Sites et fichiers entre groupes

Pour restreindre le partage de fichiers et de sites entre les groupes, par exemple, une équipe financière qui gère des projets confidentiels avec une équipe marketing, vous pouvez définir et implémenter des stratégies d’obstacle à l’information. Ces obstacles empêchent également d’autres aspects de la communication et de la collaboration dans Microsoft Teams, SharePoint et OneDrive. Pour plus d’informations, voir [En savoir plus sur les obstacles aux](/microsoft-365/compliance/information-barriers)informations Microsoft 365 .

## <a name="get-access-insights"></a>Obtenir des informations sur l’accès

La gouvernance d’accès fournit des informations sur les sites avec les documents les plus sensibles et les sites sur-partagés dans votre organisation. Pour une vue [d’ensemble,](https://techcommunity.microsoft.com/t5/microsoft-sharepoint-blog/what-s-new-in-security-and-compliance-in-sharepoint-and-onedrive/ba-p/1696705)voir Nouveautés de la sécurité et de la conformité dans SharePoint et OneDrive . Vous devez désigner [votre organisation pour](https://forms.microsoft.com/Pages/ResponsePage.aspx?id=v4j5cvGGr0GRqy180BHbR3-O9WDTKhhDtgWfphwS9YhUM0hJNklNRkZKMlhLNDRZNzlEQlVDSjdZVi4u) cette prévisualisation.
