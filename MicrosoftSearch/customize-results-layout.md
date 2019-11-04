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
ms.openlocfilehash: 2ca53f2e2dc207acdf48542f39ee4f448bdeb90e
ms.sourcegitcommit: bfcab9d42e93addccd1e3875b41bc9cc1b6986cc
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/04/2019
ms.locfileid: "37949725"
---
# <a name="create-a-layout-to-customize-search-results"></a><span data-ttu-id="7e14c-103">Créer une disposition pour personnaliser les résultats de la recherche</span><span class="sxs-lookup"><span data-stu-id="7e14c-103">Create a layout to customize search results</span></span>

<span data-ttu-id="7e14c-104">Vous pouvez concevoir la disposition des résultats pour un secteur vertical personnalisé à l’aide du concepteur de mise en page.</span><span class="sxs-lookup"><span data-stu-id="7e14c-104">You can design the result layout for a custom vertical using the search layout designer.</span></span> <span data-ttu-id="7e14c-105">Vous pouvez commencer à concevoir la disposition en choisissant des modèles proposés dans le concepteur de mise en page et en les utilisant si elles répondent à vos besoins.</span><span class="sxs-lookup"><span data-stu-id="7e14c-105">You can start designing the layout by choosing templates offered in the layout designer and using them if they fit your requirements.</span></span> <span data-ttu-id="7e14c-106">Ou vous pouvez choisir de modifier ces modèles de différentes manières pour répondre à vos besoins.</span><span class="sxs-lookup"><span data-stu-id="7e14c-106">Or you can choose to edit these templates in various ways to fit your requirements.</span></span> <span data-ttu-id="7e14c-107">Par exemple, ajouter/supprimer des images, ajouter/supprimer du texte, modifier du texte.</span><span class="sxs-lookup"><span data-stu-id="7e14c-107">For example, add/remove images, add/remove text, modify text.</span></span> <span data-ttu-id="7e14c-108">Si aucun des modèles ne répond à vos besoins, vous pouvez choisir de commencer à concevoir votre disposition à l’aide d’un modèle vide.</span><span class="sxs-lookup"><span data-stu-id="7e14c-108">If none of the templates meet your requirement, you can choose to start designing your layout using a blank template.</span></span>  

 

<span data-ttu-id="7e14c-109">Une fois que la mise en page est prête, vous utilisez le [langage de modèle cartes adaptatives](https://docs.microsoft.com/adaptive-cards/templating/language) pour créer un type de résultat thead.</span><span class="sxs-lookup"><span data-stu-id="7e14c-109">Once the layout is ready, you use the [Adaptive Cards Template language](https://docs.microsoft.com/adaptive-cards/templating/language)  to create thea result layout JSON which is used to define a result type.</span></span> <span data-ttu-id="7e14c-110">Vous mappez les propriétés de résultat à la mise en page à l’aide de l’étape de mappage du concepteur de mise en page.</span><span class="sxs-lookup"><span data-stu-id="7e14c-110">You map the result properties to the layout using the Mapping step in the layout designer.</span></span>  

## <a name="create-a-layout-on-your-own"></a><span data-ttu-id="7e14c-111">Créer une mise en page</span><span class="sxs-lookup"><span data-stu-id="7e14c-111">Create a layout on your own</span></span>
<span data-ttu-id="7e14c-112">La création d’une mise en page personnelle nécessite de connaître les [cartes adaptatives](https://docs.microsoft.com/adaptive-cards/authoring-cards/getting-started) et leur [schéma](https://adaptivecards.io/explorer/).</span><span class="sxs-lookup"><span data-stu-id="7e14c-112">Creating a layout on your own requires knowledge of [adaptive cards](https://docs.microsoft.com/adaptive-cards/authoring-cards/getting-started) and their [schema](https://adaptivecards.io/explorer/).</span></span> <span data-ttu-id="7e14c-113">La disposition des résultats de la recherche utilise un sous-ensemble des éléments proposés par des cartes adaptatives et vous pouvez utiliser le concepteur de mise en page pour en savoir plus sur l’ensemble d’éléments pris en charge.</span><span class="sxs-lookup"><span data-stu-id="7e14c-113">Search result layout uses a subset of the elements offered by adaptive cards and you can use the layout designer to learn about the supported set of elements.</span></span>  

<span data-ttu-id="7e14c-114">Lors de la création de votre propre disposition, créez la disposition de la carte adaptative à l’aide des données de votre, puis finalisez la mise en page.</span><span class="sxs-lookup"><span data-stu-id="7e14c-114">While creating your own layout, create the adaptive card layout using data from your , and then finalize the layout.</span></span>
<span data-ttu-id="7e14c-115">La création de votre propre disposition comporte deux étapes principales.</span><span class="sxs-lookup"><span data-stu-id="7e14c-115">There are two main steps in creating your own layout</span></span>
- <span data-ttu-id="7e14c-116">Conception de la disposition</span><span class="sxs-lookup"><span data-stu-id="7e14c-116">Designing the layout</span></span>
- <span data-ttu-id="7e14c-117">Séparation des données du modèle</span><span class="sxs-lookup"><span data-stu-id="7e14c-117">Separating the data from the template</span></span>

#### <a name="designing-the-layout"></a><span data-ttu-id="7e14c-118">Conception de la disposition</span><span class="sxs-lookup"><span data-stu-id="7e14c-118">Designing the layout</span></span>

<span data-ttu-id="7e14c-119">Dans cet exemple, nous affichons une disposition avec un en-tête, un lien et un texte descriptif.</span><span class="sxs-lookup"><span data-stu-id="7e14c-119">In this example, we're showing a layout with a header, link, and descriptive text.</span></span>

![Exemple de mise en page avec un en-tête, un lien et une description.](media/Verts-ExampleLayout.png)

<span data-ttu-id="7e14c-121">Et voici le fichier JSON associé à la mise en page :</span><span class="sxs-lookup"><span data-stu-id="7e14c-121">And here's the layout's associated JSON file:</span></span>


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

#### <a name="separating-the-data-from-the-layout"></a><span data-ttu-id="7e14c-122">Séparation des données de la mise en page</span><span class="sxs-lookup"><span data-stu-id="7e14c-122">Separating the data from the layout</span></span>

<span data-ttu-id="7e14c-123">Vous pouvez séparer les données de la mise en page et lier les données.</span><span class="sxs-lookup"><span data-stu-id="7e14c-123">You can separate the data from the layout and bind the data.</span></span> 

<span data-ttu-id="7e14c-124">Voici la disposition JSON après avoir lié les données :</span><span class="sxs-lookup"><span data-stu-id="7e14c-124">Here's Layout JSON after binding the data:</span></span>


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

<span data-ttu-id="7e14c-125">Exemples de données : spécifiez des exemples de données dans l' **éditeur de données exemple** pour afficher la carte liée aux données en mode aperçu.</span><span class="sxs-lookup"><span data-stu-id="7e14c-125">Sample data: Specify sample data in the **Sample Data Editor** to view the data-bound card when in "Preview Mode".</span></span>

```json
{ 

    "title": "Contoso Marketing Analysis - Q3 FY18", 
    "titleUrl": "https://contoso.com/hr/link", 
    "link": "https://contoso.com/hr/link", 
    "description": "Marketing team, and looking at the Contoso Marketing documents on the team site. Yo can't see right...Marketing Planning presentation?" 

} 
```

## <a name="map-the-layout-to-the-result-properties"></a><span data-ttu-id="7e14c-126">Mapper la disposition aux propriétés de résultat</span><span class="sxs-lookup"><span data-stu-id="7e14c-126">Map the layout to the result properties</span></span>

<span data-ttu-id="7e14c-127">Vous devez mapper chaque champ de la mise en page à une propriété Result ou à une propriété Connector pour générer le JSON de la disposition du résultat.</span><span class="sxs-lookup"><span data-stu-id="7e14c-127">You must map each field of the layout to a result property or a connector property to generate the result layout JSON.</span></span>

![Verts-SearchLayoutDesigner. png](media/Verts-SearchLayoutDesigner.png)

<span data-ttu-id="7e14c-129">Sélectionnez un champ dans la mise en page pour mettre en surbrillance les variables devant être mappées.</span><span class="sxs-lookup"><span data-stu-id="7e14c-129">Select a field in the layout to highlight the variables that need to be mapped.</span></span> <span data-ttu-id="7e14c-130">Vous pouvez utiliser plusieurs variables pour un seul champ et tous les champs doivent être mappés aux propriétés de résultat.</span><span class="sxs-lookup"><span data-stu-id="7e14c-130">You can use multiple variables for a single field and all fields must be mapped to the result properties.</span></span>

## <a name="things-to-consider"></a><span data-ttu-id="7e14c-131">Éléments à prendre en compte...</span><span class="sxs-lookup"><span data-stu-id="7e14c-131">Things to consider...</span></span>

<span data-ttu-id="7e14c-132">Avant de commencer, vous devez effectuer quelques opérations et quelques éléments que vous devez éviter pour garantir la réussite de vos mises en page.</span><span class="sxs-lookup"><span data-stu-id="7e14c-132">Before you get started, there are a few things that you should do and a few things you should avoid to ensure that your layouts will be successful.</span></span>

### <a name="do"></a><span data-ttu-id="7e14c-133">À faire</span><span class="sxs-lookup"><span data-stu-id="7e14c-133">Do</span></span>

- <span data-ttu-id="7e14c-134">Modifier un modèle pour indiquer le lien du logo dans la mise en page si vous utilisez des liens statiques pour les logos et non pour les propriétés de résultat.</span><span class="sxs-lookup"><span data-stu-id="7e14c-134">Edit a template to provide the logo link in the layout if you are using static links for logos and not result properties.</span></span>   
- <span data-ttu-id="7e14c-135">Valider la disposition des résultats pour les scénarios où aucune donnée n’est renvoyée pour une propriété Result utilisée dans le JSON résultant.</span><span class="sxs-lookup"><span data-stu-id="7e14c-135">Validate the result layout for scenarios where no data is returned for a result property used in the result JSON.</span></span> <span data-ttu-id="7e14c-136">Utilisez `$when` condition pour masquer un élément si la propriété ne contient pas de données.</span><span class="sxs-lookup"><span data-stu-id="7e14c-136">Use `$when` condition to hide an element if the property doesn't contain data.</span></span>  
- <span data-ttu-id="7e14c-137">Assurez-vous que les types `$when` de données de la condition et la propriété Result correspondent.</span><span class="sxs-lookup"><span data-stu-id="7e14c-137">Make sure that data types of the `$when` condition and the result property match.</span></span> <span data-ttu-id="7e14c-138">Par exemple, ne pas `Number` Comparer `Text` avec `$when` l’état de condition.</span><span class="sxs-lookup"><span data-stu-id="7e14c-138">For example, don't compare `Number` with `Text` in `$when` condition.</span></span>  
- <span data-ttu-id="7e14c-139">Considérez les conditions requises pour les thèmes lors de la conception d’une disposition de résultats.</span><span class="sxs-lookup"><span data-stu-id="7e14c-139">Think of theme requirements when designing a result layout.</span></span>  
- <span data-ttu-id="7e14c-140">Assurez- `Textblock`  vous que l’élément peut gérer le contenu dynamique.</span><span class="sxs-lookup"><span data-stu-id="7e14c-140">Make sure that `Textblock` element can handle dynamic content.</span></span> <span data-ttu-id="7e14c-141">Vous pouvez utiliser les `wrap` propriétés `maxLines` et de l’élément à cet effet.</span><span class="sxs-lookup"><span data-stu-id="7e14c-141">You can use the `wrap` and `maxLines` element properties for this purpose.</span></span> 
- <span data-ttu-id="7e14c-142">Format correct de la date lors `{DATE()}` de l’utilisation de la démarque.</span><span class="sxs-lookup"><span data-stu-id="7e14c-142">Properly format the date when using `{DATE()}` in markdown.</span></span>  

### <a name="dont"></a><span data-ttu-id="7e14c-143">À ne pas faire</span><span class="sxs-lookup"><span data-stu-id="7e14c-143">Don't</span></span>

- <span data-ttu-id="7e14c-144">Ne définissez pas de types de données non valides lors de la liaison de valeurs.</span><span class="sxs-lookup"><span data-stu-id="7e14c-144">Don't define invalid data types when binding values.</span></span> <span data-ttu-id="7e14c-145">Pour plus d’informations sur les types de données, voir [Manage the Search Schema](https://docs.microsoft.com/sharepoint/search/manage-the-search-schema ).</span><span class="sxs-lookup"><span data-stu-id="7e14c-145">For more information about the data types, see [Manage the Search schema](https://docs.microsoft.com/sharepoint/search/manage-the-search-schema ).</span></span>
- <span data-ttu-id="7e14c-146">Évitez de détourer le résultat sur la page de résultats en suivant la hauteur maximale du JSON de la disposition du résultat.</span><span class="sxs-lookup"><span data-stu-id="7e14c-146">Avoid cropping the result on the result page by following the maximum height of the result layout JSON.</span></span> <span data-ttu-id="7e14c-147">Si vous dépassez la hauteur maximale de la disposition du résultat, le résultat sera rogné sur la page de résultats.</span><span class="sxs-lookup"><span data-stu-id="7e14c-147">If you exceed the maximum height of the result layout the result will be cropped on the result page.</span></span>
- <span data-ttu-id="7e14c-148">N’utilisez `px` pas de valeurs dans les propriétés de l’élément.</span><span class="sxs-lookup"><span data-stu-id="7e14c-148">Don't use `px` values in properties of element.</span></span>


## <a name="resources"></a><span data-ttu-id="7e14c-149">Ressources</span><span class="sxs-lookup"><span data-stu-id="7e14c-149">Resources</span></span>
[<span data-ttu-id="7e14c-150">Personnaliser la page des résultats de recherche</span><span class="sxs-lookup"><span data-stu-id="7e14c-150">Customize search result page</span></span>](customize-search-page.md)

[<span data-ttu-id="7e14c-151">Cartes adaptatives</span><span class="sxs-lookup"><span data-stu-id="7e14c-151">Adaptive cards</span></span>](https://docs.microsoft.com/adaptive-cards/authoring-cards/getting-started)

[<span data-ttu-id="7e14c-152">Langue du modèle cartes adaptatives</span><span class="sxs-lookup"><span data-stu-id="7e14c-152">Adaptive Cards Template language</span></span>](https://docs.microsoft.com/adaptive-cards/templating/language)

[<span data-ttu-id="7e14c-153">Schéma de carte adaptative</span><span class="sxs-lookup"><span data-stu-id="7e14c-153">Adaptive card schema</span></span>](https://adaptivecards.io/explorer/)
