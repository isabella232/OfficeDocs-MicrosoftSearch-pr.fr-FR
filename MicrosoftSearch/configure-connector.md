---
title: Configurer votre connecteur microsoft pour Microsoft Search (recherche Microsoft)
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
description: Configurer votre connecteur microsoft pour Microsoft Search (recherche Microsoft)
ms.openlocfilehash: 61a7d444ddc4c290b5098c327faa8e70f0ef1049
ms.sourcegitcommit: 469be70ad295a5837978d75babf5243115257f77
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/13/2021
ms.locfileid: "49847545"
---
<!-- markdownlint-disable no-trailing-punctuation -->

# <a name="setup-overview-for-graph-connectors-by-microsoft"></a>Vue d’ensemble du programme d’installation des connecteurs Graph par Microsoft 

Cet article récapitule le processus de base requis pour utiliser le Centre d’administration [Microsoft 365](https://admin.microsoft.com) pour configurer l’un des connecteurs Graph par Microsoft. Le processus de base comprend les étapes suivantes :  
<!---Add links to each section in the doc--->

1. Ajoutez un connecteur Graph dans le Centre d’administration Microsoft 365.
2. Nommez la connexion.
3. Configurez les paramètres de connexion.
4. Gérer les autorisations de recherche.
5. Attribuez des étiquettes de propriété.
6. Gérer le schéma.
7. Choisissez les paramètres d’actualisation.
8. Examinez la connexion.

Il est important de noter que le processus d’installation est très similaire pour tous les connecteurs Graph par Microsoft, mais n’est pas exactement le même. **En plus de lire cet article, n’oubliez pas de lire les informations spécifiques au connecteur pour votre source de données.**  

## <a name="step-1-add-a-graph-connector-in-the-microsoft-365-admin-center"></a>Étape 1 : Ajouter un connecteur Graph dans le Centre d’administration Microsoft 365

Pour configurer l’un des connecteurs créés par Microsoft, complétez les étapes suivantes.

1. Connectez-vous à votre compte d’administrateur dans le [Centre d’administration Microsoft 365](https://admin.microsoft.com)
2. Dans le volet de navigation, sélectionnez **Paramètres,** puis **recherchez & intelligence.** Sélectionnez [l’onglet Connecteurs.](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/Connectors)
3. Sélectionnez **+Ajouter,** puis sélectionnez la source de données de votre choix dans le menu des options disponibles.

![Les sources de données disponibles sont les suivantes : ADLS Gen2, les sites web d’entreprise, le serveur Microsoft SQL, Azure SQL, la base de données Oracle SQL, ServiceNow, le partage de fichiers, Azure DevOps et MediaWiki.](media/add-connector.png)

>[! Remarque :] Vous pouvez ajouter un maximum de dix connexions Graph à chaque client.

## <a name="step-2-name-the-connection"></a>Étape 2 : Nommer la connexion
Vous devez spécifier les attributs ci-après : 

* Nom  
* ID de connexion 
* Description (facultatif) 

L’ID de connexion crée des propriétés implicites pour votre connecteur. Il ne doit contenir que des caractères alphanumériques et un maximum de 32 caractères. 

## <a name="step-3-configure-the-connection-settings"></a>Étape 3 : Configurer les paramètres de connexion

Le processus de configuration des paramètres de connexion varie en fonction du type de source de données. Consultez les informations spécifiques au connecteur pour le type de source de données que vous souhaitez ajouter à votre client pour effectuer cette étape du processus d’installation.  

Pour en savoir plus sur la connexion à une source de données sur site, voir Installer une passerelle [de données sur site.](https://aka.ms/configuregateway)

## <a name="step-4-manage-search-permissions"></a>Étape 4 : Gérer les autorisations de recherche

Les listes de contrôle d’accès déterminent les utilisateurs de votre organisation qui peuvent accéder à chaque élément de données.  

Certains connecteurs tels que [Microsoft SQL](MSSQL-connector.md) azure Data Lake [Storage Gen2](azure-data-lake-connector.md) supportent en natif les AD Azure [Active Directory (Azure AD).](https://docs.microsoft.com/azure/active-directory/)

D’autres connecteurs tels [que ServiceNow,](servicenow-connector.md) [Azure DevOps](azure-devops-connector.md)et [Salesforce](salesforce-connector.md) prise en charge la synchronisation des utilisateurs et groupes non Azure AD.  

## <a name="step-5-assign-property-labels"></a>Étape 5 : Attribuer des étiquettes de propriété
Vous pouvez affecter des étiquettes sémantiques à vos propriétés source sur la page « Attribuer des étiquettes de propriétés ». Les étiquettes sont des balises bien connues fournies par Microsoft qui fournissent une signification sémantique. Ils permettent à Microsoft d’intégrer vos données de connecteur dans des expériences Microsoft 365 telles que la recherche améliorée, les cartes de personnes, la découverte intelligente, etc.  

Le tableau suivant répertorie les étiquettes actuellement pris en charge et leurs descriptions.  

Étiquette | Description
--- | ---  
**title** | Titre de l’élément que vous souhaitez voir dans la recherche et d’autres expériences 
**url** | URL cible de l’élément dans le système source 
**createdBy** | Nom de la personne qui a créé l’élément 
**lastModifiedBy** | Nom de la personne qui a modifié l’élément le plus récemment 
**authors** | Nom des personnes qui ont participé/ont participé à l’élément 
**createdDateTime** | Quand l’élément a-t-il été créé ? 
**lastModifiedDateTime** | Quand l’élément a-t-il été modifié le plus récemment 
**fileName** | Nom de l’élément de fichier 
**fileExtension** | Type d’élément de fichier tel que .pdf ou .word 

Les propriétés de cette page sont pré-sélectionnées en fonction de votre source de données, mais vous pouvez modifier cette sélection s’il existe une autre propriété mieux adaptée à une étiquette particulière.  

Le titre **de l’étiquette** est l’étiquette la plus importante. Il est **vivement recommandé d’avoir** une propriété affectée à cette étiquette afin que votre connexion participe à l’expérience [de cluster de résultats.](result-cluster.md)

Un mappage incorrect des étiquettes entraîne une expérience de recherche insérante. Certaines étiquettes ne peuvent pas se voir attribuer de propriété.  

## <a name="step-6-manage-schema"></a>Étape 6 : Gérer le schéma

### <a name="content-property"></a>Propriété de contenu

Il est vivement recommandé de sélectionner une **propriété de contenu » dans le menu déroulant des options, ou de conserver la valeur par défaut si elle est présente. Cette propriété est utilisée pour l’indexation de texte intégral du contenu, la génération d’extraits de page de résultats de recherche, la participation au [cluster](result-cluster.md) de résultats, la détection de langue, la prise en charge HTML/texte, le classement et la pertinence, ainsi que la formulation des requêtes.

Si vous sélectionnez une propriété de contenu, vous avez la possibilité d’utiliser la propriété générée par le système **ResultSnippet** lorsque vous créez [votre type de résultat.](customize-results-layout.md) Cette propriété sert d’espace réservé pour les extraits de code dynamiques générés à partir de la propriété de contenu au moment de la requête. Si vous utilisez cette propriété dans votre type de résultat, des extraits de code sont générés dans vos résultats de recherche.

### <a name="creating-aliases-for-source-properties"></a>Création d’alias pour les propriétés source

Vous pouvez ajouter des alias à vos propriétés sous la colonne « Alias » dans la page Gérer le schéma. Les alias sont des noms convivial pour vos propriétés. Ils sont utilisés dans les requêtes et dans la création de filtres. Ils sont également utilisés pour normaliser les propriétés source à partir de plusieurs connexions de telle façon qu’elles ont le même nom. Ainsi, vous pouvez créer un filtre unique pour un secteur vertical avec plusieurs connexions. Pour plus [d’informations, voir](customize-search-page.md) Personnaliser la page des résultats de la recherche.  

### <a name="search-schema-attributes"></a>Attributs de schéma de recherche

Vous pouvez définir les attributs de schéma de recherche pour contrôler les fonctionnalités de recherche de chaque propriété source. Un schéma de recherche permet de déterminer les résultats affichés sur la page des résultats de la recherche et les informations que les utilisateurs finaux peuvent afficher et consulter.

Les attributs de schéma de recherche incluent **les** attributs utilisables dans une **recherche,** utilisables dans une requête, **récupérables** et **utilisables dans une recherche.** Le tableau suivant répertorie chacun des attributs que les connecteurs Microsoft Graph supportent et explique leurs fonctions.

Attribut de schéma de recherche | Fonction | Exemple
--- | --- | ---
UTILISABLE DANS UNE RECHERCHE | Rend le contenu de texte d’une propriété utilisable dans une recherche. Le contenu de la propriété est inclus dans l’index de texte intégral. | Si la propriété est un  **titre,** une requête entreprise renvoie des réponses qui contiennent le mot **Entreprise** dans un texte ou un titre.
QUERYABLE | Recherche par requête une correspondance pour une propriété particulière. Le nom de la propriété peut ensuite être spécifié dans la requête par programme ou en verbatim. |  Si la **propriété Title** est utilisable dans une requête, la requête **Title: Enterprise** est prise en charge. 
RÉCUPÉRABLE | Seules les propriétés récupérables peuvent être utilisées dans le type de résultat et s’afficher dans le résultat de recherche. |
UTILISABLE DANS UNE REFINABLE | Les propriétés utilisables dans une recherche refinable peuvent être utilisées comme dans la page des résultats de recherche Microsoft. | Les utilisateurs de votre [organisation](custom-filters.md) peuvent filtrer **par lastModifiedDateTime** dans la page des résultats de la recherche si la propriété est marquée comme utilisable dans une recherche dans une recherche dans le cadre de la configuration de la connexion.

Pour tous les connecteurs à l’exception du connecteur de partage de fichiers, les types personnalisés doivent être définies manuellement. Pour activer les fonctionnalités de recherche pour chaque champ, vous avez besoin d’un schéma de recherche mappé à une liste de propriétés. L’Assistant Connexion sélectionne automatiquement un schéma de recherche basé sur l’ensemble des propriétés source que vous choisissez. Vous pouvez modifier ce schéma en sélectionnant les cases à cocher pour chaque propriété et attribut dans la page de schéma de recherche.

![Le schéma d’un connecteur peut être personnalisé en ajoutant ou en supprimant des fonctions Requête, Recherche et Récupération.](media/manageschema.png)
 
### <a name="restrictions-and-recommendations-for-search-schema-settings"></a>Restrictions et recommandations pour les paramètres de schéma de recherche

* La **propriété de** contenu est uniquement utilisable dans une recherche. Une fois sélectionnée dans la dropdown, cette propriété ne peut pas être marquée **comme récupérable** ou **utilisable dans une requête.**

* Des problèmes de performances importants se produisent lorsque les résultats de la recherche s’restituer avec la **propriété de** contenu. Par exemple, le **champ de** contenu Texte d’un article de la base de connaissances [ServiceNow.](https://www.servicenow.com)

* Seules les propriétés marquées comme récupérables sont restituer dans les résultats de la recherche et peuvent être utilisées pour créer des types de résultats modernes (MRT).

* Seules les propriétés de chaîne peuvent être marquées comme utilisables dans une recherche.

> [!NOTE]
> Après avoir créé une connexion, vous **ne pouvez pas** modifier le schéma. Pour ce faire, vous devez supprimer votre connexion et en créer une nouvelle.

## <a name="step-7-refresh-settings"></a>Étape 7 : Actualiser les paramètres

L’intervalle d’actualisation détermine la fréquence de synchronisation de vos données entre la source de données et Microsoft Search (recherche Microsoft). Chaque type de source de données possède un ensemble différent de planifications d’actualisation optimales en fonction de la fréquence de modification des données et du type de modifications.

Il existe deux types d’intervalles d’actualisation: l’actualisation complète et l’actualisation incrémentielle, mais les actualisations incrémentielles ne sont pas disponibles pour certaines sources de données.  

Avec une actualisation complète, le moteur de recherche traite et indexe chaque élément de la source de contenu, quelles que soient les analyses précédentes. Une actualisation complète est la meilleure pour les situations ci-après :

* Détection de suppressions de données.
* L’actualisation incrémentielle n’a pas réussi à mettre à jour le contenu en raison d’erreurs.
* Les ACA ont été modifiées.
* Les règles d’analyse ont été modifiées.
* Lorsque le schéma de la connexion a été mis à jour (les mises à jour de schéma ne sont pas encore pris en charge)

Avec une actualisation **incrémentielle,** le moteur de recherche peut traiter et indexer uniquement les éléments qui ont été créés ou modifiés depuis la dernière analyse réussie. Par conséquent, toutes les données de la source de contenu ne sont pas ré-indexées. Les actualisations incrémentielles fonctionnent mieux pour détecter le contenu, les métadonnées, les autorisations et d’autres mises à jour.

Les actualisations incrémentielles sont beaucoup plus rapides que les actualisations complètes, car les éléments inchangés ne sont pas traitées. Toutefois, si vous choisissez d’exécuter des actualisations incrémentielles, vous devrez toujours exécuter régulièrement des actualisations complètes pour maintenir une synchronisation précise des données entre la source de contenu et l’index de recherche.

![Paramètres d’analyse incrémentielle et d’intervalle d’analyse complète indiquant Incrémentielle à 15 minutes et analyse complète à 1 semaine.](media/refreshschedule.png)

<!---Change screenshot for one that shows both options in new UI (try ServiceNow)--->

## <a name="step-8-review-connection"></a>Étape 8 : Examiner la connexion

Vous pouvez passer en revue l’intégralité de votre configuration et modifier les paramètres selon vos besoins avant d’achever la connexion. **N’oubliez pas de lire les informations spécifiques au connecteur pour votre source de données si vous ne l’avez pas déjà fait.** Sélectionnez **Terminer la mise** à jour lorsque vous êtes prêt à terminer la connexion.

## <a name="how-do-i-know-the-connection-setup-worked"></a>Comment savoir si la configuration de la connexion a fonctionné ?

Go to the list of your published connections under the **Connectors** tab in the [admin center](https://admin.microsoft.com). Pour découvrir comment effectuer des mises à jour et des suppressions, voir [Gérer votre connecteur.](manage-connector.md)
