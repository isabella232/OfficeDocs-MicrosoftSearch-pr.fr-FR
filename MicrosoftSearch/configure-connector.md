---
title: Configurer votre connecteur créé par Microsoft pour Microsoft Search
ms.author: monaray
author: monaray97
manager: jameslau
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: Configurer votre connecteur créé par Microsoft pour Microsoft Search
ms.openlocfilehash: ce2515b3eaa859a8fbb00d83c4727865ab55e174
ms.sourcegitcommit: 6aea7102c94855e9f80711c0f3d7bf5833ce8fb5
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/14/2020
ms.locfileid: "48464475"
---
<!-- markdownlint-disable no-trailing-punctuation -->

# <a name="set-up-your-microsoft-built-connector-for-microsoft-search"></a>Configurer votre connecteur créé par Microsoft pour Microsoft Search

Cet article vous guide tout au long de la procédure de configuration d’un connecteur créé par Microsoft. Il décrit le flux de configuration d’une connexion dans le [Centre d’administration](https://admin.microsoft.com)365 de Microsoft. Pour plus d’informations sur la configuration de connecteurs créés par Microsoft, consultez les articles suivants :

* [Azure Data Lake Storage Gen2](azure-data-lake-connector.md)
* [Azure DevOps](azure-devops-connector.md)
* [Azure SQL](MSSQL-connector.md)
* [Sites web d’entreprise](enterprise-web-connector.md)
* [MediaWiki](mediawiki-connector.md)
* [Microsoft SQL Server](MSSQL-connector.md)
* [ServiceNow](servicenow-connector.md)

## <a name="set-up"></a>Configurer

Procédez comme suit pour configurer les connecteurs créés par Microsoft.

1. Accédez à l' [onglet Connecteurs](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/Connectors) dans le [Centre d’administration Microsoft 365](https://admin.microsoft.com).
2. Connectez-vous à votre compte avec les informations d’identification de votre client [Microsoft 365](https://www.microsoft.com/microsoft-365) .
3. Sélectionnez **Ajouter un connecteur**.
4. Dans la liste des connecteurs disponibles, sélectionnez le connecteur de votre choix.

![Les sources de données disponibles sont les suivantes : Azure DevOps Connector, ServiceNow, ADLS Gen2, Enterprise Web, MediaWiki, Microsoft SQL Server et Azure SQL.](media/add_connector.png)

### <a name="name-the-connector"></a>Nommer le connecteur

Pour créer une connexion, spécifiez d’abord les attributs suivants :

1. Nom de la connexion
2. ID de connexion
3. Description (facultatif)

L’ID de connexion crée des propriétés implicites pour votre connecteur. Il doit contenir uniquement des caractères alphanumériques et comporter jusqu’à 32 caractères.

### <a name="connect-to-a-data-source"></a>Se connecter à une source de données

Le processus de connexion de données varie en fonction du type de connecteur. Pour en savoir plus sur la connexion à votre source de données locale, consultez la rubrique [installer une passerelle de données locale](https://aka.ms/configuregateway).

### <a name="select-source-properties"></a>Sélectionner les propriétés de la source

Les champs de données définis par votre source de données tierce en tant que propriétés source sont indexés dans Microsoft Search. Pour modifier ces propriétés, sélectionnez **modifier les propriétés** dans la barre latérale à droite de la page **connecteurs** . Vous pouvez sélectionner **jusqu’à 64 propriétés source**.

### <a name="manage-the-search-schema"></a>Gérer le schéma de recherche

#### <a name="content-property"></a>Content, propriété

Vous pouvez sélectionner la propriété source correspondant à la propriété **content** (index de texte intégral de l’élément) en sélectionnant une propriété de chaîne dans la liste déroulante de la propriété **content** . Vous pouvez également conserver la propriété sélectionnée par défaut si celle-ci est présente.

Il est particulièrement important que la propriété correcte soit sélectionnée depuis que cette propriété est utilisée pour l’indexation de texte intégral de contenu, la génération d’extraits de page de résultats de recherche, la détection de langue, le support HTML/texte, le classement et la pertinence, et la formulation de requête.

Si vous sélectionnez une propriété pour le **contenu**, vous aurez la possibilité d’utiliser la propriété générée par le système **ResultSnippet** lorsque vous [Créez votre type de résultat](customize-results-layout.md). Cette propriété sert d’espace réservé pour les extraits de code dynamiques générés à partir de la propriété **content** au moment de la requête. Si vous utilisez cette propriété dans votre type de résultat, des extraits de code sont générés dans les résultats de la recherche.

#### <a name="search-schema-attributes"></a>Attributs du schéma de recherche

Vous pouvez définir les attributs du schéma de recherche pour contrôler la fonctionnalité de recherche de chaque propriété source. Un schéma de recherche permet de déterminer les résultats affichés sur la page des résultats de la recherche et les informations que les utilisateurs finaux peuvent afficher et auxquels ils peuvent accéder.

Les attributs de schéma de recherche incluent des **recherches pouvant**faire l’objet d’une recherche, d’une **requête**ou d’une **récupération**. Le tableau suivant répertorie chacun des attributs pris en charge par les connecteurs Microsoft Graph et explique leurs fonctions.

Attribut de schéma de recherche | Fonction | Exemple
--- | --- | ---
FAIRE l’objet | Rend le texte d’une propriété pouvant faire l’objet d’une recherche. Le contenu de la propriété est inclus dans l’index de texte intégral. | Si la propriété est **title**, une requête pour **Enterprise** renvoie des réponses qui contiennent le mot **entreprise** dans n’importe quel texte ou titre.
QUERYABLE | Recherche par requête une correspondance pour une propriété particulière. Le nom de la propriété peut ensuite être spécifié dans la requête, soit par programme, soit par mot Verbatim. |  Si la propriété **title** peut être Requery, le titre de la requête **: Enterprise** est pris en charge.
AFFICHABLE dans | Seules les propriétés récupérables peuvent être utilisées dans le type de résultat et s’afficher dans le résultat de la recherche. |

Pour tous les connecteurs, les types personnalisés doivent être définis manuellement. Pour activer les fonctionnalités de recherche pour chaque champ, vous avez besoin d’un schéma de recherche mappé à une liste de propriétés. L’Assistant de connexion sélectionne automatiquement un schéma de recherche en fonction de l’ensemble des propriétés sources que vous choisissez. Vous pouvez modifier ce schéma en activant les cases à cocher pour chaque propriété et attribut dans la page schéma de recherche.

![Le schéma d’un connecteur peut être personnalisé en ajoutant ou en supprimant des fonctions de requête, de recherche et de récupération.](media/manageschema.png)

#### <a name="restrictions-and-recommendations-for-search-schema-settings"></a>Restrictions et recommandations pour les paramètres de schéma de recherche

* La propriété **content** peut faire l’objet d’une recherche uniquement. Une fois que vous avez sélectionné dans la liste déroulante, cette **queryable**propriété ne peut pas **être sélectionnée.** Des problèmes de performances significatifs se produisent lorsque les résultats de la recherche sont affichés avec la propriété **content** . Le champ de contenu de **texte** d’un article de la base de connaissances [ServiceNow](https://www.servicenow.com) en est un exemple.

* Seules les propriétés marquées comme rendu récupérables dans les résultats de la recherche et peuvent être utilisées pour créer des types de résultats modernes (MRTs).

* Seules les propriétés de chaîne peuvent être marquées comme pouvant faire l’objet d’une recherche.


> [!Note]
> Après avoir créé une connexion, vous **ne pouvez** plus modifier le schéma. Pour ce faire, vous devez supprimer votre connexion et en créer une nouvelle.

### <a name="manage-search-permissions"></a>Gérer les autorisations de recherche

Les listes de contrôle d’accès déterminent les utilisateurs de votre organisation qui peuvent accéder à chaque élément de données. Tous les connecteurs prennent en charge les autorisations de recherche visibles par tous les utilisateurs.

### <a name="set-the-refresh-schedule"></a>Définir la planification d’actualisation

La planification de l’actualisation détermine la fréquence à laquelle vos données sont synchronisées avec l’index dans Microsoft Graph et Microsoft Search. Vous pouvez planifier l’actualisation de deux manières : analyse complète ou analyse incrémentielle.

Avec une **analyse complète**, le moteur de recherche traite et indexe chaque élément dans la source de contenu, quelles que soient les analyses précédentes. L’analyse complète fonctionne de manière optimale dans les situations suivantes :

* Détection des suppressions de données.
* L’analyse incrémentielle n’a pas pu analyser le contenu pour les erreurs.
* Les ACL ont été modifiées.
* Les règles d’analyse ont été modifiées.
* Une mise à jour logicielle pour Microsoft Search est requise. Les mises à jour modifient le schéma de recherche.

Avec une **analyse incrémentielle**, le moteur de recherche peut traiter et indexer uniquement les éléments qui ont été créés ou modifiés depuis la dernière analyse réussie. Par conséquent, toutes les données de la source de contenu ne sont pas réindexées. Les analyses incrémentielles fonctionnent mieux pour détecter le contenu, les métadonnées, les autorisations et les autres mises à jour.

Les analyses incrémentielles sont beaucoup plus rapides que les analyses complètes, car les éléments inchangés ne sont pas traités. Pour maintenir une synchronisation des données précise entre la source de contenu et l’index de recherche, vous devez exécuter régulièrement les deux analyses.

Chaque connecteur dispose d’un ensemble optimal de planifications d’actualisation en fonction de la fréquence à laquelle les données sont modifiées et du type de modifications.

![Paramètres d’analyse incrémentielle et d’intervalle de l’analyse complète, avec incrémentielle à 15 minutes et analyse complète sur 1 semaine.](media/refreshschedule.png)

### <a name="review-connector-settings"></a>Vérifier les paramètres du connecteur

Une fois que vous avez configuré votre connecteur, le [Centre d’administration](https://admin.microsoft.com) vous amène sur une page où vous pouvez vérifier vos paramètres. Vous pouvez revenir au processus de configuration pour modifier un paramètre avant de confirmer la connexion. Pour plus d’informations, consultez [la rubrique Manage Your Connector](manage-connector.md).

## <a name="next-steps-customize-the-search-results-page"></a>Étapes suivantes : personnaliser la page de résultats de recherche

Avec l’interface utilisateur de Microsoft Search (IU), vos utilisateurs finals peuvent rechercher du contenu à partir de vos applications de productivité [microsoft 365](https://www.microsoft.com/microsoft-365) et de l’écosystème Microsoft plus large. Un secteur vertical de recherche fait référence aux onglets qui apparaissent lorsqu’un utilisateur affiche ses résultats de recherche dans [SharePoint](https://sharepoint.com/), [Microsoft Office](https://Office.com)et Microsoft Search dans [Bing](https://Bing.com). Vous pouvez personnaliser les secteurs verticaux de recherche pour affiner les résultats, de sorte que seul un certain type de résultats de recherche s’affiche. Ces secteurs verticaux apparaissent sous forme d’onglet dans la partie supérieure de la page des résultats de la recherche. Un type de résultat moderne (MRT) est l’interface utilisateur qui désigne le mode de présentation des résultats.

Créez vos propres types de résultat et de vertical, de sorte que les utilisateurs finaux puissent afficher les résultats de la recherche à partir de nouvelles connexions. Sans cette étape, les données de votre connexion ne s’afficheront pas sur la page des résultats de la recherche.

Pour en savoir plus sur la création de vos secteurs verticaux et MRTs, voir Personnalisation de la [page de résultats de recherche](customize-search-page.md).

## <a name="how-do-i-know-the-connection-setup-worked"></a>Comment puis-je savoir si l’installation de la connexion a fonctionné ?

Accédez à la liste de vos connexions publiées sous l’onglet **connecteurs** dans le [Centre d’administration](https://admin.microsoft.com). Pour savoir comment effectuer des mises à jour et des suppressions, consultez [la rubrique Manage Your Connector](manage-connector.md).
