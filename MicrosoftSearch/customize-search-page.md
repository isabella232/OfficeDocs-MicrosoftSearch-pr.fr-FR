---
title: Personnaliser la page Recherche Microsoft page
ms.author: jeffkizn
author: jypal
manager: jeffkizn
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: Ajouter des secteurs verticaux de recherche et personnaliser les résultats de recherche
ms.openlocfilehash: 701604798115091c7c7a286d3b6e97dea08e9453
ms.sourcegitcommit: be5dcc7005447d6139e39d86211c7ec4cd5dd907
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/27/2021
ms.locfileid: "58639587"
---
# <a name="customize-the-search-results-page"></a>Personnaliser la page des résultats de la recherche

Vous pouvez créer des *secteurs verticaux* de recherche et des *types* de résultats pour personnaliser les résultats de recherche que les utilisateurs voient lorsqu’ils recherchent dans Microsoft [SharePoint,](https://sharepoint.com/) [Microsoft Office](https://office.com)et Recherche Microsoft dans [Bing](https://bing.com). Les secteurs verticaux facilitent la recherche des informations qu’ils sont autorisés à voir.

Par exemple, vous pouvez créer un secteur vertical de recherche pour les données d’analyse marketing à partir de logiciels tiers pour vos utilisateurs au service marketing. Vous pouvez également définir des types de résultats et personnaliser la disposition de ces données.

## <a name="about-search-verticals"></a>À propos des secteurs verticaux de recherche

Une ligne d’onglets se place en haut de la page Recherche Microsoft résultats. Il s’existe des secteurs verticaux de recherche. Un secteur vertical de recherche affiche uniquement les résultats d’un certain type ou d’un certain ensemble de contenu. Fichiers **ou** Actualités en sont des **exemples.** Par défaut, Recherche Microsoft affiche les secteurs verticaux **Tous,** **Personnes,** **Fichiers,** **Sites** et **Actualités.**  

Vous pouvez ajouter des secteurs verticaux de recherche pertinents pour votre organisation. Ceux-ci apparaissent sur la page Recherche Microsoft résultats dans SharePoint, Office et Bing. Par exemple, vous pouvez créer un secteur vertical pour le contenu marketing et un autre pour les ventes, en fonction du type d’informations dont chaque service a besoin. Vous pouvez ajouter des secteurs verticaux pour afficher les résultats uniquement à partir du contenu indexé via des connecteurs.

Vous pouvez créer des secteurs verticaux et des types de résultats à deux niveaux :

-  Niveau de l’organisation : un secteur vertical que vous créez au niveau de l’organisation apparaît sur la page des résultats de la recherche lorsque les utilisateurs recherchent à partir de leur page d’accueil [SharePoint,](https://sharepoint.com/) sur [Office](https://office.com)ou [sur Bing](https://bing.com).
- **Niveau du** site : par exemple, vous souhaitez peut-être permettre aux employés de votre service clientèle de rechercher des incidents de gravité *1* directement à partir du site SharePoint de leur service.

### <a name="multiple-connections-in-a-vertical"></a>Plusieurs connexions dans un secteur vertical

Un secteur vertical de recherche peut faire surface des résultats provenant de plusieurs sources de connecteur. Cette option offre de la flexibilité dans la conception de votre page de résultats de recherche. Le processus de configuration verticale permet aux administrateurs de sélectionner plusieurs connexions à l’étape « Source de contenu ».

Si vous nommez avec précision autant d’étiquettes *sémantiques* que possible, cette expérience est améliorée. Vous ajoutez des étiquettes sémantiques au point de définition de schéma et d’ingestion. [En savoir plus sur la création et la gestion d’étiquettes sémantiques.](configure-connector.md#step-6-assign-property-labels)
[Voici](configure-connector.md#step-6-assign-property-labels) des informations supplémentaires sur la création et la gestion d’étiquettes sémantiques.

> [!NOTE]
> Les connexions multiples dans une fonctionnalité verticale sont actuellement en prévisualisation. Pour plus d’informations, voir [les fonctionnalités d’aperçu des connecteurs.](connectors-overview.md#what-are-the-preview-features)

Une connexion peut être ajoutée en tant que source de contenu sous un seul secteur vertical. Vous ne pouvez pas utiliser les connexions sous plusieurs secteurs verticaux.

Pour configurer une requête pour un secteur vertical de recherche où plusieurs sources de connexion ont été ajoutées, utilisez les propriétés sources communes pour créer la requête.

### <a name="before-you-create-verticals-and-result-types"></a>Avant de créer des secteurs verticaux et des types de résultats

Tenez compte de ces facteurs :

- Assurez-vous que le connecteur a été indexé. Cela peut prendre jusqu’à 48 heures, en fonction de la taille du fichier.

- Vous ne pouvez pas créer de secteur vertical pour le contenu qui réside dans SharePoint.

Voici les étapes à suivre pour implémenter un secteur vertical :

1. Créez le secteur vertical. Dans cette étape, vous définissez le nom, la source de contenu et l’étendue du contenu à rechercher.
2. Définissez à quoi ressembleront les résultats de ce secteur vertical.  
3. Activez le secteur vertical (à afficher) à partir de la page de liste verticale.

## <a name="step-1-create-the-search-vertical"></a>Étape 1 : Créer le secteur vertical de recherche

Après avoir commencé l’Assistant, vous êtes guidé à travers les étapes pour définir le nom du secteur vertical, la source de contenu et l’étendue du contenu à rechercher.

>[!Note]
>Les secteurs verticaux sont créés dans un état désactivé. Vous les activez pour les rendre consultables.

Vous pouvez utiliser un ensemble limité de langage de requête de mot [clé (KQL)](/sharepoint/dev/general-development/keyword-query-language-kql-syntax-reference) pour limiter l’étendue. (Les propriétés que vous pouvez utiliser sont décrites plus loin dans cet article.) Nous vous recommandons d’utiliser des mots clés de texte libre et des restrictions de propriété avec des opérateurs booléens. KQL prend également en [charge les variables de requête de profil](#profile-query-variables) pour affiner les résultats sous le secteur vertical.

### <a name="create-a-vertical-at-the-organization-level"></a>Créer un secteur vertical au niveau de l’organisation

Pour créer un secteur vertical Recherche Microsoft dans SharePoint d’accueil, Office ou Bing, suivez les étapes suivantes :

1. Dans la [Centre d’administration Microsoft 365](https://admin.microsoft.com), allez à [**Verticals**](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/verticals).
2. Sélectionnez **Ajouter** pour commencer.  

### <a name="create-a-vertical-at-the-site-level"></a>Créer un secteur vertical au niveau du site

1. Sur le [SharePoint](https://sharepoint.com/) où vous souhaitez le secteur vertical, Paramètres **.**
2. Sélectionnez **Informations sur le** site, puis afficher tous les **paramètres du site.**
3. Recherchez **la** Recherche Microsoft section, puis **sélectionnez Configurer Recherche Microsoft pour cette collection de sites.**
4. Dans le volet de navigation, sélectionnez **Expérience personnalisée,** puis sélectionnez **l’onglet Verticals.**
5. Pour ajouter un secteur vertical, sélectionnez **Ajouter.** Ou pour modifier un secteur vertical, sélectionnez-le dans la liste.

## <a name="step-2-create-result-types"></a>Étape 2 : Créer des types de résultats

Vous pouvez utiliser *des types de résultats* pour définir la façon dont les résultats sont affichés dans le secteur vertical. La disposition des résultats vous permet d’afficher des informations importantes directement dans les résultats de la recherche, afin que les utilisateurs n’ont pas à sélectionner chaque résultat pour voir s’ils ont trouvé ce qu’ils recherchent.

### <a name="default-search-result-layout"></a>Disposition des résultats de recherche par défaut

Une disposition des résultats de recherche par  défaut  s’affiche pour le contenu du connecteur si les étiquettes et les propriétés de contenu ont été correctement mappées aux propriétés source lors de la configuration du connecteur. *L’étiquette de* titre est l’étiquette la plus importante. Nous *vous recommandons vivement* d’attribuer une propriété à cette étiquette pour utiliser la disposition des résultats de recherche par défaut.

### <a name="create-your-own-result-type"></a>Créer votre propre type de résultat

Pour créer votre propre disposition des résultats de recherche et remplacer la disposition des résultats de recherche par défaut, vous créez un *type de résultat.* Un type de résultat de recherche est une règle qui entraîne l'affichage, sous diverses formes, de différents types de résultats de recherche. En voici les composants :

- **Une ou plusieurs conditions à** comparer à chaque résultat de recherche, telles que la source de contenu du résultat de la recherche.  
- Disposition **des résultats à** utiliser pour les résultats de recherche qui répondent aux conditions. La disposition qui en résulte contrôle l’apparition et le comportement des résultats qui répondent aux conditions sur une page de résultats de recherche.

*Si vous ne faites pas le mappage approprié pour afficher la disposition des résultats de recherche par défaut, vous devez créer au moins un type de résultat pour que les résultats s’affichent sur le secteur vertical.* 

Vous pouvez créer plusieurs types de résultats pour chaque secteur vertical, ce qui vous permet d’utiliser différentes dispositions pour différents types de résultats. Par exemple, vous pouvez personnaliser les incidents de gravité *1* pour qu’ils ont des couleurs plus visibles et une police plus grande que les incidents de gravité *3.*

Après avoir démarrer l’Assistant, vous êtes guidé dans les étapes pour définir le nom, la source de contenu et les conditions du type de résultat. Vous pouvez définir la priorité du type de résultat à partir de l’affichage Liste.
  
### <a name="create-a-result-type-at-the-organization-level"></a>Créer un type de résultat au niveau de l’organisation

1. Dans la [Centre d’administration Microsoft 365](https://admin.microsoft.com), allez à [**Types de résultats.**](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/resulttypes)
2. Pour ajouter un type de résultat, sélectionnez **Ajouter.** Pour modifier un type de résultat, sélectionnez-le dans la liste concernée.

### <a name="create-a-result-type-at-the-site-level"></a>Créer un type de résultat au niveau du site

1. Sur le [SharePoint](https://sharepoint.com/) site où vous souhaitez le type de résultat, Paramètres **.**
2. Sélectionnez **Informations sur le** site, puis afficher tous les **paramètres du site.**
3. Recherchez la section **Recherche Microsoft,** puis **sélectionnez Configurer Recherche Microsoft pour cette collection de sites.**
4. Dans le volet de navigation, sélectionnez **Expérience personnalisée** et sélectionnez **l’onglet Type de** résultat.
5. Pour ajouter un type de résultat, sélectionnez **Ajouter.**  Ou, pour modifier un type de résultat, sélectionnez le type de résultat dans la liste.

## <a name="step-3-view-the-vertical-after-its-enabled"></a>Étape 3 : Afficher le secteur vertical une fois activé

Après avoir activé le secteur vertical, il y a un délai de quelques heures avant de pouvoir l’afficher. Toutefois, vous pouvez l’SharePoint et Office pour afficher immédiatement `cacheClear=true` le secteur vertical. Pour Bing, vous devisez `&features=uncachedVerticals` à `Work vertical URL` l’affichage vertical immédiatement.

> [!NOTE]
> Les secteurs verticaux ajoutés ne sont pas visibles sur SharePoint]( et Office lorsqu’ils sont visibles à partir de https://sharepoint.com/) navigateurs web [](https://office.com) mobiles.

## <a name="profile-query-variables"></a>Variables de requête de profil

Utilisez des variables dans la section requête KQL d’un secteur vertical pour fournir des données dynamiques en tant qu’entrée à la requête d’un secteur vertical. Vous pouvez utiliser des variables de requête de profil pour rendre les résultats de la recherche contextuels pour l’utilisateur. Les variables de requête de profil récupèrent des valeurs à partir du profil de [l’utilisateur.](/graph/api/resources/profile)

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
> - Les variables de requête de profil sont définies dans la section « Requête » du processus [de configuration verticale.](customize-search-page.md#step-1-create-the-search-vertical)
> - La fonctionnalité des variables de requête de profil est actuellement en prévisualisation. Pour plus d’informations sur la prévisualisation, voir [Les fonctionnalités d’aperçu des connecteurs.](connectors-overview.md#what-are-the-preview-features)

## <a name="troubleshooting"></a>Résolution des problèmes

Voici une liste des problèmes courants que vous pouvez rencontrer et des actions à prendre pour les résoudre.

|Problème  |Action  |
|---------|---------|
| Je vois un message d’erreur « Un problème s’est passé » sur le secteur vertical. | Les types de résultat et vertical sont nécessaires pour terminer l’installation. Assurez-vous que vous avez créé les deux pour la même source de contenu. |
| Je ne vois pas ma disposition des résultats, même si j’en ai créé une. | Il peut y avoir un délai de quelques minutes car ces paramètres sont mis en cache. Patientez quelques minutes et essayez à nouveau.        |
| Je ne vois aucune source de contenu dans la page de type vertical ou de résultat. | Assurez-vous que vous avez configuré des connecteurs et des données indexées.   |

## <a name="next-steps"></a>Étapes suivantes

[Personnaliser la disposition des résultats](customize-results-layout.md)
