---
title: Personnaliser la disposition des résultats de la recherche
ms.author: anfowler
author: adefowler
manager: shohara
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: À l’aide de cartes adaptatives, créer une disposition pour afficher vos résultats de recherche personnalisés
ms.openlocfilehash: 6f406bb32a18678f1ca0546e37edb8013e2ba450
ms.sourcegitcommit: 68087149c769a7cdde80944dd9c9933d2bf4a23f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/18/2019
ms.locfileid: "38699565"
---
# <a name="create-a-layout-to-customize-search-results"></a>Créer une disposition pour personnaliser les résultats de la recherche

Vous pouvez concevoir la disposition des résultats pour un secteur vertical personnalisé à l’aide du concepteur de mise en page. Vous pouvez commencer à concevoir la disposition en choisissant des modèles proposés dans le concepteur de mise en page et en les utilisant si elles répondent à vos besoins. Ou vous pouvez choisir de modifier ces modèles de différentes manières pour répondre à vos besoins. Par exemple, ajouter/supprimer des images, ajouter/supprimer du texte et modifier du texte. Si aucun des modèles ne répond à vos besoins, vous pouvez choisir de commencer à concevoir votre disposition à l’aide d’un modèle vide.  

 

Une fois la mise en page prête, utilisez le [langage de modèle cartes adaptatives](https://docs.microsoft.com/adaptive-cards/templating/language) pour créer un JSON de mise en page de résultat utilisé pour définir un type de résultat. Vous mappez les propriétés de résultat à la mise en page à l’aide de l’étape de mappage du concepteur de mise en page.  

## <a name="create-a-layout-on-your-own"></a>Créer une mise en page
La création d’une mise en page personnelle nécessite de connaître les [cartes adaptatives](https://docs.microsoft.com/adaptive-cards/authoring-cards/getting-started) et leur [schéma](https://adaptivecards.io/explorer/). La disposition des résultats de la recherche utilise un sous-ensemble des éléments proposés par des cartes adaptatives, et vous pouvez utiliser le concepteur de mise en page pour en savoir plus sur l’ensemble d’éléments pris en charge.  

Lors de la création de votre propre disposition, créez la disposition de la carte adaptative à l’aide des données de votre connecteur, puis finalisez la mise en page.
La création de votre propre disposition comporte deux étapes principales :
- Concevez la disposition.
- Séparez les données du modèle.

#### <a name="design-the-layout"></a>Conception de la mise en page

Dans cet exemple, nous affichons une disposition avec un en-tête, un lien et un texte descriptif.

![Exemple de mise en page avec un en-tête, un lien et une description.](media/Verts-ExampleLayout.png)

Et voici le fichier JSON associé à la mise en page :


```json
{ 
    "type": "AdaptiveCard", 
    "version": "1.0", 
     "body": [ 
{ 

            "type": "ColumnSet", 
             "columns": [ 
                 { 
                     "type": "Column", 
                     "width": 8, 
                     "items": [ 
                         { 
                             "type": "TextBlock", 
                             "text": "Contoso Marketing Analysis - Q3 FY18", 
                             "color": "Accent", 
                             "size": "Medium", 
                             "spacing": "None", 
                             "$when": "{title != \"\"}", 
                             "weight": "Bolder" 
                        }, 
                        { 
                        "type": "TextBlock",  
                        "text": "https://contoso.com/hr/link", 
                        "spacing": "None",  
                        "color": "Dark", 
                        "weight": "Bolder" 

                        }, 

                        {  
                        "type": "TextBlock", 
                        "text": "Marketing team at Contoso.., and looking at the Contoso Marketing documents on the team site. This contains the data from FY20 and will taken over to FY21...Marketing Planning is ongoing for FY20..",  
                        "wrap": true, 
                        "maxLines": 2, 
                        "spacing": "Medium" 
                        } 
                        ], 

                    "horizontalAlignment": "Center", 
                    "spacing": "None" 

                } 

            ] 

        } 
        ], 

    "$schema": "http://adaptivecards.io/schemas/adaptive-card.json" 
}
```

#### <a name="separate-the-data-from-the-layout"></a>Séparer les données de la mise en page

Vous pouvez séparer les données de la mise en page et lier les données. 

Voici la disposition JSON après avoir lié les données :


```json
{ 

    "type": "AdaptiveCard", 
    "version": "1.0", 
    "body": [ 
    { 
    "type": "ColumnSet", 
"columns": [ 

                { 
                "type": "Column", 
                "width": 8, 
                "items": [ 
                { 
                "type": "TextBlock", 
                "text": "[{title}]({titleUrl})", 
                "color": "Accent", 
                "size": "Medium",
                "spacing": "None", 
                "weight": "Bolder" 

                 }, 
                 { 
                 "type": "TextBlock", 
                 "text": "{link}",
                 "spacing": "None", 
                 "color": "Dark",
                 "weight": "Bolder" 
                 }, 
                 { 
                 "type": "TextBlock",
                 "text": "{description}",
                 "wrap": true,
                 "maxLines": 2, 
                 "spacing": "Medium" 
                 } 
                 ], 
                 "horizontalAlignment": "Center", 
                 "spacing": "None" 
                 } 
                 ] 

        } 

    ], 

    "$schema": "http://adaptivecards.io/schemas/adaptive-card.json" 
}
```

Exemples de données : spécifiez des exemples de données dans l' **éditeur de données exemple** pour afficher la carte liée aux données en **mode aperçu**.

```json
{ 

    "title": "Contoso Marketing Analysis - Q3 FY18", 
    "titleUrl": "https://contoso.com/hr/link", 
    "link": "https://contoso.com/hr/link", 
    "description": "Marketing team, and looking at the Contoso Marketing documents on the team site. Yo can't see right...Marketing Planning presentation?" 

} 
```

## <a name="map-the-layout-to-the-result-properties"></a>Mapper la disposition aux propriétés de résultat

Vous devez mapper chaque champ de la mise en page à une propriété Result ou à une propriété Connector pour générer le JSON de la disposition du résultat.

![Capture d’écran d’un exemple de mise en page sur la page du concepteur de mise en page de recherche avec un champ sélectionné et le volet de propriétés ouvert.](media/Verts-SearchLayoutDesigner.png)

Sélectionnez un champ dans la mise en page pour mettre en surbrillance les variables devant être mappées. Vous pouvez utiliser plusieurs variables pour un seul champ et tous les champs doivent être mappés sur les propriétés de résultat.

## <a name="things-to-consider"></a>Éléments à prendre en compte...

Avant de commencer, vous devez effectuer quelques opérations et quelques éléments que vous devez éviter pour garantir la réussite de vos mises en page.

### <a name="do"></a>À faire

- Modifier un modèle pour indiquer le lien du logo dans la mise en page si vous utilisez des liens statiques pour les logos et non pour les propriétés de résultat.   
- Valider la disposition des résultats pour les scénarios où aucune donnée n’est renvoyée pour une propriété Result utilisée dans le JSON résultant. Utilisez la `$when` condition pour masquer un élément si la propriété ne contient pas de données.  
- Assurez-vous que les types `$when` de données de la condition et la propriété Result correspondent. Par exemple, ne pas `Number` Comparer `Text` avec dans `$when` la condition.  
- Considérez les conditions requises pour les thèmes lors de la conception d’une disposition de résultats.  
- Assurez-vous `Textblock`  que l’élément peut gérer le contenu dynamique. Vous pouvez utiliser les `wrap` propriétés `maxLines` et de l’élément à cet effet. 
- Format correct de la date lors `{DATE()}` de l’utilisation de la démarque.  

### <a name="dont"></a>À ne pas faire

- Ne définissez pas de types de données non valides lors de la liaison de valeurs. Pour plus d’informations sur les types de données, voir [Manage the Search Schema](https://docs.microsoft.com/sharepoint/search/manage-the-search-schema).
- Évitez de détourer le résultat sur la page de résultats en suivant la hauteur maximale du JSON de la disposition du résultat. Si vous dépassez la hauteur maximale de la disposition du résultat, le résultat sera rogné sur la page de résultats.
- N’utilisez `px` pas de valeurs dans les propriétés de l’élément.


## <a name="resources"></a>Ressources
[Personnaliser la page des résultats de recherche](customize-search-page.md)

[Cartes adaptatives](https://docs.microsoft.com/adaptive-cards/authoring-cards/getting-started)

[Langue du modèle cartes adaptatives](https://docs.microsoft.com/adaptive-cards/templating/language)

[Schéma de carte adaptative](https://adaptivecards.io/explorer/)
