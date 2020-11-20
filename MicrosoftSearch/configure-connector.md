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
ms.openlocfilehash: 86ddf0387e3d00a005f25207a322c8470799b76b
ms.sourcegitcommit: 59cdd3f0f82b7918399bf44d27d9891076090f4f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/20/2020
ms.locfileid: "49367606"
---
<!-- markdownlint-disable no-trailing-punctuation -->

# <a name="setup-overview-for-graph-connectors-by-microsoft"></a>Vue d’ensemble de la configuration des connecteurs Graph par Microsoft 

Cet article résume le processus de base requis pour utiliser le [Centre d’administration microsoft 365](https://admin.microsoft.com) afin de configurer les connecteurs Graph de Microsoft. Le processus de base inclut les étapes suivantes :  
<!---Add links to each section in the doc--->

1. Ajoutez un connecteur Graph dans le centre d’administration Microsoft 365.
2. Nommez la connexion.
3. Configurez les paramètres de connexion.
4. Gérer les autorisations de recherche.
5. Affectez des étiquettes de propriété.
6. Gérer le schéma.
7. Choisissez actualiser les paramètres.
8. Passez en revue la connexion.

Il est important de noter que le processus de configuration est très similaire pour tous les connecteurs Graph de Microsoft, mais n’est pas exactement le même. **En plus de lire cet article, veillez à lire le lien propre au connecteur pour votre source de données.**  

## <a name="step-1-add-a-graph-connector-in-the-microsoft-365-admin-center"></a>Étape 1 : ajouter un connecteur Graph dans le centre d’administration Microsoft 365

Procédez comme suit pour configurer les connecteurs créés par Microsoft.

1. Connectez-vous à votre compte d’administrateur dans le [Centre d’administration Microsoft 365](https://admin.microsoft.com)
2. Dans le volet de navigation, sélectionnez **paramètres**, puis sélectionnez **recherche & intelligence**. Sélectionnez l' [onglet Connecteurs](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/Connectors).
3.  Sélectionnez **+ Ajouter**, puis sélectionnez la source de données de votre choix dans le menu des options disponibles.

![Les sources de données disponibles sont les suivantes : ADLS Gen2, Enterprise Web, Microsoft SQL Server, Azure SQL, Oracle SQL Database, ServiceNow, partage de fichiers, Azure DevOps et MediaWiki.](media/add-connector.png)

>[! Remarque :] vous pouvez ajouter un maximum de dix connexions graphiques à chaque client.

## <a name="step-2-name-the-connection"></a>Étape 2 : nommer la connexion
Vous devrez spécifier ces attributs : 

* Nom  
* ID de connexion 
* Description (facultatif) 

L’ID de connexion crée des propriétés implicites pour votre connecteur. Il doit contenir uniquement des caractères alphanumériques et comporter jusqu’à 32 caractères. 

## <a name="step-3-configure-the-connection-settings"></a>Étape 3 : configurer les paramètres de connexion

Le processus de configuration des paramètres de connexion varie en fonction du type de source de données. Consultez les informations spécifiques au connecteur pour le type de source de données que vous souhaitez ajouter à votre client pour effectuer cette étape dans le processus de configuration.  

Pour en savoir plus sur la connexion à une source de données locale, consultez la rubrique [installer une passerelle de données locale](https://aka.ms/configuregateway).

## <a name="step-4-manage-search-permissions"></a>Étape 4 : gérer les autorisations de recherche

Les listes de contrôle d’accès déterminent les utilisateurs de votre organisation qui peuvent accéder à chaque élément de données.  

Certains connecteurs, comme [Microsoft SQL](MSSQL-connector.md) et [Azure Data Lake Storage Gen2](azure-data-lake-connector.md) , prennent en charge en mode natif les listes de Contrã’le d’accès [Azure Active Directory (Azure AD)](https://docs.microsoft.com/azure/active-directory/) .

D’autres connecteurs comme [ServiceNow](servicenow-connector.md), [Azure DevOps](azure-devops-connector.md)et [Salesforce](salesforce-connector.md) prennent en charge la synchronisation des utilisateurs et des groupes ad non-Azure ad.  

## <a name="step-5-assign-property-labels"></a>Étape 5 : assigner des étiquettes de propriété
Vous pouvez attribuer des étiquettes sémantiques à vos propriétés sources dans la page « affecter des étiquettes de propriété ». Les étiquettes sont des balises connues de Microsoft qui fournissent une signification sémantique. Elles permettent à Microsoft d’intégrer les données de votre connecteur dans des expériences Microsoft 365 telles que la recherche améliorée, les cartes de visite, la découverte intelligente, etc.  

Le tableau suivant répertorie les étiquettes actuellement prises en charge et leurs descriptions.  

Étiquette | Description
--- | ---  
**title** | Titre de l’élément que vous souhaitez afficher dans la recherche et dans d’autres expériences 
**url** | URL cible de l’élément dans le système source 
**createdBy** | Nom de la personne qui a créé l’élément 
**lastModifiedBy** | Nom de la personne qui a modifié l’élément le plus récemment 
**authors** | Nom des personnes qui ont participé/collaboré à la collaboration sur l’élément 
**createdDateTime** | Quand l’élément est-il créé ? 
**lastModifiedDateTime** | Date de la dernière modification de l’élément 
**fileName** | Nom de l’élément de fichier 
**fileExtension** | Type d’élément de fichier tel que. pdf ou. Word 

Les propriétés de cette page sont pré-sélectionnées en fonction de votre source de données, mais vous pouvez modifier cette sélection s’il existe une propriété différente qui est mieux adaptée à une étiquette particulière.  

Le **titre** de l’étiquette est l’étiquette la plus importante. Il est **vivement recommandé** d’attribuer une propriété à cette étiquette afin que votre connexion participe à l' [expérience de cluster de résultats](result-cluster.md).

Une mise en correspondance incorrecte des étiquettes entraînera une détérioration de la recherche. Il est possible que des étiquettes ne soient pas affectées à une propriété.  

## <a name="step-6-manage-schema"></a>Étape 6 : gérer le schéma

### <a name="content-property"></a>Content, propriété

Il est vivement recommandé de sélectionner une propriété de contenu * * dans le menu déroulant des options ou de conserver la valeur par défaut si celle-ci est présente. Cette propriété est utilisée pour l’indexation de texte intégral de contenu, la génération d’extraits de page de résultats de recherche, la participation de [clusters de résultats](result-cluster.md) , la détection de langue, la prise en charge HTML/texte, le classement et la pertinence, ainsi que la formulation de requête.

Si vous sélectionnez une propriété de contenu, vous pouvez utiliser la propriété générée par le système **ResultSnippet** lorsque vous [Créez votre type de résultat](customize-results-layout.md). Cette propriété sert d’espace réservé pour les extraits de code dynamiques générés à partir de la propriété Content au moment de la requête. Si vous utilisez cette propriété dans votre type de résultat, des extraits de code sont générés dans les résultats de la recherche.

### <a name="creating-aliases-for-source-properties"></a>Création d’alias pour les propriétés sources

Vous pouvez ajouter des alias à vos propriétés sous la colonne « alias » de la page « gérer le schéma ». Les alias sont des noms conviviaux pour vos propriétés. Elles sont utilisées dans les requêtes et dans la création de filtres. Ils sont également utilisés pour normaliser les propriétés sources de plusieurs connexions, de sorte qu’elles aient le même nom. De cette façon, vous pouvez créer un filtre unique pour un secteur vertical avec plusieurs connexions. Pour plus d’informations, voir [personnaliser la page des résultats de la recherche](customize-search-page.md) .  

### <a name="search-schema-attributes"></a>Attributs du schéma de recherche

Vous pouvez définir les attributs du schéma de recherche pour contrôler la fonctionnalité de recherche de chaque propriété source. Un schéma de recherche permet de déterminer les résultats affichés sur la page des résultats de la recherche et les informations que les utilisateurs finaux peuvent afficher et auxquels ils peuvent accéder.

Les attributs de schéma de recherche incluent les requêtes pouvant faire l’objet d’une **recherche**, l' **interrogation**, l' **extraction** et la **refinable**. Le tableau suivant répertorie chacun des attributs pris en charge par les connecteurs Microsoft Graph et explique leurs fonctions.

Attribut de schéma de recherche | Fonction | Exemple
--- | --- | ---
FAIRE l’objet | Rend le texte d’une propriété pouvant faire l’objet d’une recherche. Le contenu de la propriété est inclus dans l’index de texte intégral. | Si la propriété est **title**, une requête pour **Enterprise** renvoie des réponses qui contiennent le mot **entreprise** dans n’importe quel texte ou titre.
QUERYABLE | Recherche par requête une correspondance pour une propriété particulière. Le nom de la propriété peut ensuite être spécifié dans la requête, soit par programme, soit par mot Verbatim. |  Si la propriété **title** peut être Requery, le titre de la requête **: Enterprise** est pris en charge. 
AFFICHABLE dans | Seules les propriétés récupérables peuvent être utilisées dans le type de résultat et s’afficher dans le résultat de la recherche. |
REFINABLE | Les propriétés Refinable peuvent être utilisées comme dans la page des résultats de la recherche Microsoft. | Les utilisateurs de votre organisation peuvent [Filtrer](custom-filters.md) par **lastModifiedDateTime** dans la page des résultats de la recherche si la propriété est marquée refinable lors de la configuration de la connexion.

Pour tous les connecteurs à l’exception du connecteur de partage de fichiers, les types personnalisés doivent être définis manuellement. Pour activer les fonctionnalités de recherche pour chaque champ, vous avez besoin d’un schéma de recherche mappé à une liste de propriétés. L’Assistant de connexion sélectionne automatiquement un schéma de recherche en fonction de l’ensemble des propriétés sources que vous choisissez. Vous pouvez modifier ce schéma en activant les cases à cocher pour chaque propriété et attribut dans la page schéma de recherche.

![Le schéma d’un connecteur peut être personnalisé en ajoutant ou en supprimant des fonctions de requête, de recherche et de récupération.](media/manageschema.png)
 
### <a name="restrictions-and-recommendations-for-search-schema-settings"></a>Restrictions et recommandations pour les paramètres de schéma de recherche

* La propriété **content** peut faire l’objet d’une recherche uniquement. Une fois que vous avez sélectionné dans la liste déroulante, cette **queryable** propriété ne peut pas **être sélectionnée.**

* Des problèmes de performances significatifs se produisent lorsque les résultats de la recherche sont affichés avec la propriété **content** . Le champ de contenu de **texte** d’un article de la base de connaissances [ServiceNow](https://www.servicenow.com) en est un exemple.

* Seules les propriétés marquées comme rendu récupérables dans les résultats de la recherche et peuvent être utilisées pour créer des types de résultats modernes (MRTs).

* Seules les propriétés de chaîne peuvent être marquées comme pouvant faire l’objet d’une recherche.

> [!NOTE]
> Après avoir créé une connexion, vous **ne pouvez** plus modifier le schéma. Pour ce faire, vous devez supprimer votre connexion et en créer une nouvelle.

## <a name="step-7-refresh-settings"></a>Étape 7 : actualiser les paramètres

L’intervalle d’actualisation détermine la fréquence de synchronisation de vos données entre la source de données et Microsoft Search. Chaque type de source de données dispose d’un ensemble différent de planifications d’actualisation optimales en fonction de la fréquence à laquelle les données sont modifiées et du type de modifications.

Il existe deux types d’intervalles d’actualisation, qui sont l’actualisation **complète** et l' **actualisation incrémentielle**, mais les actualisations incrémentielles ne sont pas disponibles pour certaines sources de données.

Avec une actualisation complète, le moteur de recherche traite et indexe chaque élément dans la source de contenu, quelles que soient les analyses précédentes. Une actualisation complète fonctionne de manière optimale dans les situations suivantes :

* Détection des suppressions de données.
* L’actualisation incrémentielle n’a pas pu mettre à jour le contenu en raison d’erreurs.
* Les ACL ont été modifiées.
* Les règles d’analyse ont été modifiées.
* Lorsque le schéma de la connexion a été mis à jour (les mises à jour du schéma ne sont pas encore prises en charge)

Avec une **actualisation incrémentielle**, le moteur de recherche peut traiter et indexer uniquement les éléments qui ont été créés ou modifiés depuis la dernière analyse réussie. Par conséquent, toutes les données de la source de contenu ne sont pas réindexées. Les actualisations incrémentielles fonctionnent mieux pour détecter le contenu, les métadonnées, les autorisations et les autres mises à jour.

Les actualisations incrémentielles sont beaucoup plus rapides que les actualisations complètes car les éléments inchangés ne sont pas traités. Toutefois, si vous choisissez d’exécuter des actualisations incrémentielles, vous devrez toujours exécuter des actualisations complètes régulièrement afin de maintenir une synchronisation des données précise entre la source de contenu et l’index de recherche.

![Paramètres d’analyse incrémentielle et d’intervalle de l’analyse complète, avec incrémentielle à 15 minutes et analyse complète sur 1 semaine.](media/refreshschedule.png)

<!---Change screenshot for one that shows both options in new UI (try ServiceNow)--->

## <a name="step-8-review-connection"></a>Étape 8 : vérifier la connexion

Vous pouvez vérifier l’ensemble de votre configuration et modifier les paramètres en fonction de vos besoins avant de terminer la connexion. **Veillez à lire les informations spécifiques au connecteur pour votre source de données si vous ne l’avez pas déjà fait.** Sélectionnez **terminer la mise à jour** lorsque vous êtes prêt à terminer la connexion.

## <a name="how-do-i-know-the-connection-setup-worked"></a>Comment puis-je savoir si l’installation de la connexion a fonctionné ?

Accédez à la liste de vos connexions publiées sous l’onglet **connecteurs** dans le [Centre d’administration](https://admin.microsoft.com). Pour savoir comment effectuer des mises à jour et des suppressions, consultez [la rubrique Manage Your Connector](manage-connector.md).
