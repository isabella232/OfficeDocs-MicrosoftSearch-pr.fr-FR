---
title: Gérer les secteurs verticaux de recherche
ms.author: jypal
author: jypal6
manager: jeffkizn
ms.audience: Admin
ms.topic: article
ms.service: mssearch
ms.localizationpriority: medium
search.appverid:
- BFB160
- MET150
- MOE150
description: Gérer les secteurs verticaux de recherche sur la page des résultats
ms.openlocfilehash: 0396c1f67b22a77a39f78aa1f058ee4b2019a39c
ms.sourcegitcommit: 02d4f91210d992da080fd39d5b60f8cf30d8f0b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/08/2021
ms.locfileid: "60238402"
---
# <a name="manage-search-verticals"></a>Gérer les secteurs verticaux de recherche

Les secteurs verticaux de recherche sont des onglets de la page des résultats de recherche qui indiquent les résultats d’un type spécifique ou de sources sélectionnées. Par exemple, le secteur vertical Fichiers affiche les résultats classés en tant que fichiers et facilite la recherche de documents pour les utilisateurs. Vous pouvez personnaliser les secteurs verticaux Recherche Microsoft pour répondre aux besoins de votre organisation ou services individuels.

Vous pouvez gérer les secteurs verticaux à deux niveaux :

- **Niveau** de l’organisation : un secteur vertical au niveau de l’organisation [](https://office.com)apparaît sur la page des résultats de la recherche lorsque les utilisateurs recherchent à partir de leur page d’accueil [SharePoint,](https://sharepoint.com/) Microsoft Office et Recherche Microsoft dans [Bing](https://bing.com)
- **Niveau du site** : un secteur vertical au niveau du site apparaît sur la page des résultats de la recherche lorsque les utilisateurs recherchent sur SharePoint site. Par exemple, vous souhaitez peut-être permettre aux employés de votre service clientèle de rechercher des incidents de gravité 1 directement à partir du site SharePoint de leur service.

## <a name="understanding-search-verticals"></a>Comprendre les secteurs verticaux de recherche

Recherche Microsoft possède deux types de secteurs verticaux, les secteurs verticaux intégrés et les secteurs verticaux personnalisés. Les secteurs verticaux à l’emploi tels que Tous, Fichiers et Personnes créent un accès facile aux résultats de recherche les plus couramment utilisés.

Des options de configuration supplémentaires sont proposées sur des secteurs verticaux personnalisés et peuvent être utilisées pour créer la meilleure expérience pour vos utilisateurs.

Vous pouvez ajouter des secteurs verticaux de recherche pertinents pour votre organisation. Par exemple, vous pouvez créer un secteur vertical pour le contenu marketing et un autre pour les ventes, en fonction du type d’informations dont chaque service a besoin. Des secteurs verticaux peuvent être ajoutés pour afficher les résultats du contenu indexé par [des connecteurs Graph,](connectors-overview.md)mais vous ne pouvez pas créer de secteur vertical pour le contenu qui réside dans SharePoint.

## <a name="create-search-verticals"></a>Créer des secteurs verticaux de recherche

L’expérience de gestion verticale est pilotée par l’Assistant. Vous êtes guidé à travers les étapes pour définir le nom du secteur vertical, la source de contenu et l’étendue du contenu à rechercher. Vous pouvez utiliser un ensemble limité de langage de requête de mot clé [(KQL)](#keyword-query-language-kql) pour définir l’étendue de la recherche verticale pour une source de contenu donnée.

Voici les étapes à suivre pour créer les secteurs verticaux personnalisés sur Recherche Microsoft dans SharePoint [accueil,](https://sharepoint.com/)Office [ou](https://office.com/) [Bing](https://bing.com/).  

### <a name="manage-organization-level-verticals"></a>Gérer les secteurs verticaux au niveau de l’organisation

1. Dans la [Centre d'administration Microsoft 365,](https://admin.microsoft.com)allez à la page [**Verticals**](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/verticals) dans la section **Personnalisation.**
1. Cliquez **sur Ajouter** pour créer un secteur vertical.
1. Après avoir passé en revue les étapes de configuration, vous pouvez examiner et enregistrer le secteur vertical.  

### <a name="manage-site-level-verticals"></a>Gérer les secteurs verticaux au niveau du site

1. Dans le SharePoint où vous souhaitez gérer les secteurs verticaux, ouvrez le panneau de paramètres en cliquant sur l’engrenage.
1. Sélectionnez **Informations sur le** site, puis afficher tous les **paramètres du site.**  
1. Recherchez la section Recherche Microsoft, puis sélectionnez **Configurer les paramètres de recherche.**
1. Dans le volet de navigation, sélectionnez Expérience personnalisée, puis **sélectionnez Verticals**.
1. Cliquez **sur Ajouter** pour créer un secteur vertical.
1. Après avoir paramètre votre configuration, vous pouvez examiner et enregistrer le secteur vertical.  

## <a name="view-the-vertical-in-search-results"></a>Afficher le secteur vertical dans les résultats de recherche

Une [disposition des résultats de recherche](manage-result-types.md) est nécessaire pour Graph de connecteur de recherche à restituer sur la page de secteur vertical de recherche. Pour vous assurer que la disposition des résultats appropriée est présente, vous pouvez activer le secteur vertical de recherche. Après avoir activé un secteur vertical, il y a un délai de quelques heures avant de pouvoir l’afficher. Vous pouvez append cacheClear=true à l’URL SharePoint et Office pour afficher immédiatement le secteur vertical. Dans Bing, &features=uncachedVerticals à l’URL de secteur vertical de travail pour afficher immédiatement le secteur vertical.

> [!NOTE]
> Les secteurs verticaux ajoutés ne sont pas visibles [SharePoint](https://sharepoint.com/) et [Office](https://office.com) lorsqu’ils sont visibles à partir de navigateurs web mobiles.

## <a name="advanced-configuration-options"></a>Options de configuration avancées

### <a name="multiple-connections-in-a-vertical"></a>Connexions multiples dans un secteur vertical

Un secteur vertical de recherche peut faire surface des résultats provenant de plusieurs sources de connecteur. Cette option offre de la flexibilité dans la conception de votre page de résultats de recherche. Le processus de configuration verticale permet aux administrateurs de sélectionner plusieurs connexions à l’étape « Source de contenu ».

Si vous nommez avec précision autant d’étiquettes *sémantiques* que possible, cette expérience est améliorée. Vous ajoutez des étiquettes sémantiques au point de définition de schéma et d’ingestion. [En savoir plus sur la création et la gestion d’étiquettes sémantiques.](configure-connector.md#step-6-assign-property-labels)
[Voici](configure-connector.md#step-6-assign-property-labels) des informations supplémentaires sur la création et la gestion d’étiquettes sémantiques.

> [!NOTE]
> - Les connexions multiples dans une fonctionnalité verticale sont actuellement en prévisualisation. Pour plus d’informations, voir [les fonctionnalités d’aperçu des connecteurs.](connectors-overview.md#what-are-the-preview-features)
> - Une connexion peut être ajoutée en tant que source de contenu sous un seul secteur vertical. Vous ne pouvez pas utiliser les connexions sous plusieurs secteurs verticaux.

Pour configurer une requête pour un secteur vertical de recherche où plusieurs sources de connexion ont été ajoutées, utilisez les propriétés sources communes pour créer la requête.

### <a name="keyword-query-language-kql"></a>KQL (Keyword Query Language)

Une requête peut être ajoutée à un secteur vertical pour affiner les résultats affichés sur le secteur vertical de recherche à l’aide du langage [KQL (Keyword Query Language) (prise](/sharepoint/dev/general-development/keyword-query-language-kql-syntax-reference) en charge limitée). Cette page répertorie les propriétés disponibles. Nous vous recommandons d’utiliser des mots clés de texte libre et des restrictions de propriété avec des opérateurs booléens pour créer le KQL. Les opérateurs de classement dynamique tels que XRANK, les opérateurs de proximité et les mots ne sont pas pris en charge.

Voici quelques exemples de requêtes.

|Scénario         | Requête   |  
| --------- | ------ |
|Exclusion des résultats des sites d’archivage           |NOT (path:http//contoso.sharepoint.com/archive OR path:http//contoso.sharepoint.com/CompanyArchive)|
| Exclusion des résultats en fonction de la propriété du type de fichier | NOT(FileType:htm)|  

#### <a name="profile-query-variables"></a>Variables de requête de profil

Utilisez des variables dans la section de requête KQL d’un secteur vertical pour fournir des données dynamiques en tant qu’entrée à la requête d’un secteur vertical. Vous pouvez utiliser des variables de requête de profil pour rendre les résultats de la recherche contextuels pour l’utilisateur. Les variables de requête de profil récupèrent des valeurs à partir du profil de [l’utilisateur.](/graph/api/resources/profile)

Par exemple, pour créer un secteur vertical « Tickets » pour que l’utilisateur trouve les tickets de support qui lui sont affectés, vous pouvez spécifier la requête suivante dans la section « Requête » lors de la création verticale dans la page d’administration :  

`AssignedTo:{Profile.accounts.userPrincipalName}`

Cette langue affinera les résultats de la recherche pour afficher uniquement les éléments pour lesquels la personne assignée est l’utilisateur qui exécute la recherche.

[La ressource de profil](/graph/api/resources/profile) expose les propriétés en tant que collections. Par exemple, les informations relatives aux adresses de messagerie sont exposées via la collecte de courriers électroniques, les postes de travail en tant que collection de positions, etc. Toutes les propriétés disponibles dans le profil utilisateur, qui ont AAD comme type source, sont exposées en tant que variables de requête.

Considérons un utilisateur qui dispose de trois adresses de messagerie disponibles dans la collection de courriers électroniques, comme illustré ici :

```json
"emails": [{ 

        "address": "Megan.Bowen@contoso.com",
        "id": "xyz", 
        "source": { 
            "CreatedBy": "xyz", 
            "CreatedOn": "2222", 
            "Type": "official" 
        },
        "type": "main" 
    }, { 
        "address": "meganb@hotmail.com",
        "id": "abc", 
        "source": { 
            "CreatedBy": "abc",
            "CreatedOn": "3333", 
            "Type": "non-official",
        },
        "type": "work"
    }, { 
        "address": "meganb@outlook.com",
        "id": "pqr", 
        "source": { 
            "CreatedBy": "pqr", 
            "CreatedOn": "4444", 
            "Type": "personal" 
        },
        "type": "personal" 
    } 
] 
```

- La requête `MyProperty: {Profile.emails.address}` est résolue en *MyProperty : « Megan.Bowen@contoso.com*».  

- Pour résoudre toutes les valeurs de l’attribut d’adresse, utilisez la syntaxe d’extension à valeurs multiples. La requête sera résolue en `{|MyProperty:{Profile.emails.address}}` *((MyProperty:"Megan.Bowen@contoso \. com »)* ou *(MyProperty: « meganb@hotmail \. com »)* ou *(MyProperty:"meganb@outlook \. com »)).*

Utilisez l’opérateur « | » pour résoudre les variables à valeurs multiples. Pour plus d’exemples d’extension de profil, voir le tableau suivant.

| #         | Syntaxe |  Valeur renvoyée  |
| --------- | ------ | --- |
| 1    | MyProperty:{Profile.emails.address}  |   « Megan \. Bowen@contoso.com »  |
| 2 | MyProperty:{Profile.emails}   |    {Profile.emails} This won’t resolve because *emails* is an object.|
| 3    | {? MyProperty:{Profile.emails}}  |  Cela ne sera pas résolu car *les e-mails sont* un objet. Le « ? » ignore les variables de requête qui ne sont pas résolues. Cette variable est supprimée lorsqu’elle est passée plus bas dans la pile de requêtes.   |
| 4  | {&#124;MyProperty : {Profile.emails.source.Type}}    |  ((MyProperty:"official ») ou (MyProperty:"non-official ») ou (MyProperty:"personal »))    |

> [!NOTE]
>
> - Les variables de requête de profil sont uniquement pris en charge pour les secteurs verticaux personnalisés qui utilisent [un connecteur](connectors-overview.md) comme source de contenu.
> - La fonctionnalité des variables de requête de profil est actuellement en prévisualisation. Pour plus d’informations sur la prévisualisation, voir [les fonctionnalités d’aperçu des connecteurs.](connectors-overview.md#what-are-the-preview-features)

## <a name="troubleshooting"></a>Résolution des problèmes

Voici une liste des problèmes courants que vous pouvez rencontrer et des actions à prendre pour les résoudre.

|Problème  |Action  |
|---------|---------|
| Je vois un message d’erreur « Un problème s’est passé » sur le secteur vertical. | Les types de résultat et vertical sont nécessaires pour terminer l’installation. Assurez-vous que les deux sont définies pour la source de contenu. |
| Je ne vois aucune source de contenu sur la page verticale. | Assurez-vous que vous avez configuré des connecteurs et des données indexées.   |
