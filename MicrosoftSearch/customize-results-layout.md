---
title: Gérer les dispositions des résultats de la recherche
ms.author: jypal
author: jypal6
manager: jeffkizn
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: À l’aide de cartes adaptatives, créez une disposition pour afficher vos résultats de recherche personnalisés
ms.openlocfilehash: d29b1a45f11079f4b71f71a387cf43cbf2f48e7d
ms.sourcegitcommit: 5df252e6d0bd67bb1b4c59418aceca8369f5fe42
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51031736"
---
<!-- markdownlint-disable no-hard-tabs -->
# <a name="create-a-layout-to-customize-search-results"></a><span data-ttu-id="bd4b9-103">Créer une disposition pour personnaliser les résultats de recherche</span><span class="sxs-lookup"><span data-stu-id="bd4b9-103">Create a layout to customize search results</span></span>

<span data-ttu-id="bd4b9-104">Vous pouvez concevoir la disposition des résultats pour un secteur vertical personnalisé à l’aide du concepteur de disposition de recherche.</span><span class="sxs-lookup"><span data-stu-id="bd4b9-104">You can design the result layout for a custom vertical using the search layout designer.</span></span> <span data-ttu-id="bd4b9-105">Vous pouvez commencer à concevoir la disposition en choisissant les modèles proposés dans le concepteur de disposition et en les utilisant s’ils correspondent à vos besoins.</span><span class="sxs-lookup"><span data-stu-id="bd4b9-105">You can start designing the layout by choosing templates offered in the layout designer and using them if they fit your requirements.</span></span> <span data-ttu-id="bd4b9-106">Vous pouvez également choisir de modifier ces modèles de différentes manières pour vous adapter à vos besoins.</span><span class="sxs-lookup"><span data-stu-id="bd4b9-106">Or you can choose to edit these templates in various ways to fit your requirements.</span></span> <span data-ttu-id="bd4b9-107">Par exemple, ajoutez/supprimez des images, ajoutez/supprimez du texte et modifiez du texte.</span><span class="sxs-lookup"><span data-stu-id="bd4b9-107">For example, add/remove images, add/remove text, and modify text.</span></span> <span data-ttu-id="bd4b9-108">Si aucun des modèles ne répond à vos besoins, vous pouvez choisir de commencer à concevoir votre disposition à l’aide d’un modèle vide.</span><span class="sxs-lookup"><span data-stu-id="bd4b9-108">If none of the templates meet your requirements, you can choose to start designing your layout using a blank template.</span></span>  

<span data-ttu-id="bd4b9-109">Une fois la disposition prête, utilisez le langage [de](/adaptive-cards/templating/language) modèle de cartes adaptatives pour créer un JSON de disposition de résultat qui est utilisé pour définir un type de résultat.</span><span class="sxs-lookup"><span data-stu-id="bd4b9-109">After the layout is ready, use the [Adaptive Cards Template language](/adaptive-cards/templating/language) to create a result layout JSON that's used to define a result type.</span></span> <span data-ttu-id="bd4b9-110">Vous mappagez les propriétés de résultat à la disposition à l’aide de l’étape Mappage dans le concepteur de disposition.</span><span class="sxs-lookup"><span data-stu-id="bd4b9-110">You map the result properties to the layout using the Mapping step in the layout designer.</span></span>  

## <a name="create-a-layout-on-your-own"></a><span data-ttu-id="bd4b9-111">Créer une disposition par vous-même</span><span class="sxs-lookup"><span data-stu-id="bd4b9-111">Create a layout on your own</span></span>

<span data-ttu-id="bd4b9-112">La création d’une disposition par vous-même nécessite une connaissance des [cartes adaptatives](/adaptive-cards/authoring-cards/getting-started) et de [leur schéma.](https://adaptivecards.io/explorer/)</span><span class="sxs-lookup"><span data-stu-id="bd4b9-112">Creating a layout on your own requires knowledge of [adaptive cards](/adaptive-cards/authoring-cards/getting-started) and their [schema](https://adaptivecards.io/explorer/).</span></span> <span data-ttu-id="bd4b9-113">La disposition des résultats de recherche utilise un sous-ensemble des éléments offerts par les cartes adaptatives, et vous pouvez utiliser le concepteur de disposition pour en savoir plus sur l’ensemble d’éléments pris en charge.</span><span class="sxs-lookup"><span data-stu-id="bd4b9-113">Search result layout uses a subset of the elements offered by adaptive cards, and you can use the layout designer to learn about the supported set of elements.</span></span>  

<span data-ttu-id="bd4b9-114">Lors de la création de votre propre disposition, créez la disposition de carte adaptative à l’aide des données de votre connecteur, puis finalisez la disposition.</span><span class="sxs-lookup"><span data-stu-id="bd4b9-114">While creating your own layout, create the adaptive card layout using data from your connector, and then finalize the layout.</span></span>
<span data-ttu-id="bd4b9-115">Il existe deux étapes principales pour créer votre propre disposition :</span><span class="sxs-lookup"><span data-stu-id="bd4b9-115">There are two main steps in creating your own layout:</span></span>

- <span data-ttu-id="bd4b9-116">Concevez la disposition.</span><span class="sxs-lookup"><span data-stu-id="bd4b9-116">Design the layout.</span></span>
- <span data-ttu-id="bd4b9-117">Séparez les données du modèle.</span><span class="sxs-lookup"><span data-stu-id="bd4b9-117">Separate the data from the template.</span></span>

### <a name="design-the-layout"></a><span data-ttu-id="bd4b9-118">Conception de la mise en page</span><span class="sxs-lookup"><span data-stu-id="bd4b9-118">Design the layout</span></span>

<span data-ttu-id="bd4b9-119">Dans cet exemple, nous montrons une disposition avec un en-tête, un lien et un texte descriptif.</span><span class="sxs-lookup"><span data-stu-id="bd4b9-119">In this example, we show a layout with a header, link, and descriptive text.</span></span>

![Exemple de disposition avec un en-tête, un lien et une description.](media/Verts-ExampleLayout.png)

<span data-ttu-id="bd4b9-121">Et voici le fichier JSON associé à la disposition :</span><span class="sxs-lookup"><span data-stu-id="bd4b9-121">And here's the layout's associated JSON file:</span></span>

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

### <a name="separate-the-data-from-the-layout"></a><span data-ttu-id="bd4b9-122">Séparer les données de la disposition</span><span class="sxs-lookup"><span data-stu-id="bd4b9-122">Separate the data from the layout</span></span>

<span data-ttu-id="bd4b9-123">Vous pouvez séparer les données de la disposition et les lier.</span><span class="sxs-lookup"><span data-stu-id="bd4b9-123">You can separate the data from the layout and bind the data.</span></span>

<span data-ttu-id="bd4b9-124">Voici la disposition JSON après la liaison des données :</span><span class="sxs-lookup"><span data-stu-id="bd4b9-124">Here's Layout JSON after binding the data:</span></span>

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

<span data-ttu-id="bd4b9-125">Exemple de données :  spécifiez des exemples de données dans l’exemple d’éditeur de données pour afficher la carte liée aux données en **mode Aperçu.**</span><span class="sxs-lookup"><span data-stu-id="bd4b9-125">Sample data: Specify sample data in the **Sample Data Editor** to view the data-bound card when in **Preview Mode**.</span></span>

```json
{

    "title": "Contoso Marketing Analysis - Q3 FY18",
    "titleUrl": "https://contoso.com/hr/link",
    "link": "https://contoso.com/hr/link",
    "description": "Marketing team, and looking at the Contoso Marketing documents on the team site. Yo can't see right...Marketing Planning presentation?"

}
```

## <a name="map-the-layout-to-the-result-properties"></a><span data-ttu-id="bd4b9-126">Ma cartographier la disposition sur les propriétés des résultats</span><span class="sxs-lookup"><span data-stu-id="bd4b9-126">Map the layout to the result properties</span></span>

<span data-ttu-id="bd4b9-127">Vous devez maque chaque champ de la disposition sur une propriété de résultat ou une propriété de connecteur pour générer la disposition des résultats JSON.</span><span class="sxs-lookup"><span data-stu-id="bd4b9-127">You must map each field of the layout to a result property or a connector property to generate the result layout JSON.</span></span>

![Capture d’écran d’un exemple de mise en page sur la page Concepteur de disposition de recherche avec un champ sélectionné et le volet de propriétés ouvert.](media/Verts-SearchLayoutDesigner.png)

<span data-ttu-id="bd4b9-129">Sélectionnez un champ dans la disposition pour mettre en évidence les variables qui doivent être mappées.</span><span class="sxs-lookup"><span data-stu-id="bd4b9-129">Select a field in the layout to highlight the variables that need to be mapped.</span></span> <span data-ttu-id="bd4b9-130">Vous pouvez utiliser plusieurs variables pour un seul champ, et tous les champs doivent être mappés aux propriétés de résultat.</span><span class="sxs-lookup"><span data-stu-id="bd4b9-130">You can use multiple variables for a single field, and all fields must be mapped to the result properties.</span></span>

### <a name="show-snippet-on-search-result"></a><span data-ttu-id="bd4b9-131">Afficher l’extrait de code sur le résultat de la recherche</span><span class="sxs-lookup"><span data-stu-id="bd4b9-131">Show snippet on search result</span></span>  

<span data-ttu-id="bd4b9-132">Les extraits de code dynamiques générés sur **la** propriété de contenu du résultat du connecteur peuvent être affichés sur le résultat de recherche.</span><span class="sxs-lookup"><span data-stu-id="bd4b9-132">Dynamic snippets generated on the **content** property of the connector result can be shown on the search result.</span></span> <span data-ttu-id="bd4b9-133">**ResultSnippet est** la propriété système qui agit comme une propriété d’espace réservé pour les extraits de code générés pour chaque résultat de connecteur.</span><span class="sxs-lookup"><span data-stu-id="bd4b9-133">**ResultSnippet** is the system property that acts as a placeholder property for the snippets generated for each Connector result.</span></span> <span data-ttu-id="bd4b9-134">Pour afficher les extraits de code sur la disposition des résultats, la propriété système **ResultSnippet** doit être mappée sur un champ approprié, par exemple Description, dans la disposition des résultats de la recherche.</span><span class="sxs-lookup"><span data-stu-id="bd4b9-134">To show the snippets on the result layout, the **ResultSnippet** system property must be mapped to an appropriate field, for example Description, in the search result layout.</span></span> <span data-ttu-id="bd4b9-135">Les extraits de code générés sur chaque résultat mettent également en évidence les correspondances dans l’extrait de code avec le terme de requête entré par l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="bd4b9-135">Snippets generated on each result also highlight the matches in the Snippet with the query term entered by the user.</span></span>

## <a name="things-to-consider"></a><span data-ttu-id="bd4b9-136">Informations importantes</span><span class="sxs-lookup"><span data-stu-id="bd4b9-136">Things to consider</span></span>

<span data-ttu-id="bd4b9-137">Avant de commencer, vous devez faire quelques opérations et éviter d’avoir à faire en sorte que vos dispositions soient réussies.</span><span class="sxs-lookup"><span data-stu-id="bd4b9-137">Before you get started, there are a few things that you should do and a few things you should avoid to ensure that your layouts will be successful.</span></span>

### <a name="do"></a><span data-ttu-id="bd4b9-138">À faire</span><span class="sxs-lookup"><span data-stu-id="bd4b9-138">Do</span></span>

- <span data-ttu-id="bd4b9-139">Modifiez un modèle pour fournir le lien de logo dans la disposition si vous utilisez des liens statiques pour les logos et non pour les propriétés de résultat.</span><span class="sxs-lookup"><span data-stu-id="bd4b9-139">Edit a template to provide the logo link in the layout if you're using static links for logos and not result properties.</span></span>
- <span data-ttu-id="bd4b9-140">Validez la disposition des résultats pour les scénarios dans lequel aucune donnée n’est renvoyée pour une propriété de résultat utilisée dans le résultat JSON.</span><span class="sxs-lookup"><span data-stu-id="bd4b9-140">Validate the result layout for scenarios where no data is returned for a result property used in the result JSON.</span></span> <span data-ttu-id="bd4b9-141">Utilisez la `$when` condition pour masquer un élément si la propriété ne contient pas de données.</span><span class="sxs-lookup"><span data-stu-id="bd4b9-141">Use the `$when` condition to hide an element if the property doesn't contain data.</span></span>  
- <span data-ttu-id="bd4b9-142">Assurez-vous que les types de données de `$when` la condition et de la propriété de résultat correspondent.</span><span class="sxs-lookup"><span data-stu-id="bd4b9-142">Make sure that data types of the `$when` condition and the result property match.</span></span> <span data-ttu-id="bd4b9-143">Par exemple, ne comparez pas `Number` avec `Text` dans la `$when` condition.</span><span class="sxs-lookup"><span data-stu-id="bd4b9-143">For example, don't compare `Number` with `Text` in the `$when` condition.</span></span>  
- <span data-ttu-id="bd4b9-144">Pensez aux exigences de thème lors de la conception d’une disposition des résultats.</span><span class="sxs-lookup"><span data-stu-id="bd4b9-144">Think of theme requirements when designing a result layout.</span></span>  
- <span data-ttu-id="bd4b9-145">Assurez-vous que `Textblock`   l’élément peut gérer le contenu dynamique.</span><span class="sxs-lookup"><span data-stu-id="bd4b9-145">Make sure that the `Textblock` element can handle dynamic content.</span></span> <span data-ttu-id="bd4b9-146">Vous pouvez utiliser les `wrap` propriétés et `maxLines` les propriétés d’élément à cet effet.</span><span class="sxs-lookup"><span data-stu-id="bd4b9-146">You can use the `wrap` and `maxLines` element properties for this purpose.</span></span>
- <span data-ttu-id="bd4b9-147">Formatez correctement la date lors de `{DATE()}` l’utilisation dans Markdown.</span><span class="sxs-lookup"><span data-stu-id="bd4b9-147">Properly format the date when using `{DATE()}` in Markdown.</span></span>  

### <a name="dont"></a><span data-ttu-id="bd4b9-148">À ne pas faire</span><span class="sxs-lookup"><span data-stu-id="bd4b9-148">Don't</span></span>

- <span data-ttu-id="bd4b9-149">Ne définissez pas de types de données non valides lors de la liaison de valeurs.</span><span class="sxs-lookup"><span data-stu-id="bd4b9-149">Don't define invalid data types when binding values.</span></span> <span data-ttu-id="bd4b9-150">Pour plus d’informations sur les types de données, voir [Gérer le schéma de recherche.](/sharepoint/search/manage-the-search-schema)</span><span class="sxs-lookup"><span data-stu-id="bd4b9-150">For more information about data types, see [Manage the Search schema](/sharepoint/search/manage-the-search-schema).</span></span>
- <span data-ttu-id="bd4b9-151">Évitez de rogler le résultat sur la page de résultats en suivant la hauteur maximale de la disposition des résultats JSON.</span><span class="sxs-lookup"><span data-stu-id="bd4b9-151">Avoid cropping the result on the result page by following the maximum height of the result layout JSON.</span></span> <span data-ttu-id="bd4b9-152">Si vous dépassez la hauteur maximale de la mise en page des résultats, le résultat est rogé sur la page de résultats.</span><span class="sxs-lookup"><span data-stu-id="bd4b9-152">If you exceed the maximum height of the result layout, the result will be cropped on the result page.</span></span>
- <span data-ttu-id="bd4b9-153">N’utilisez pas de `px` valeurs dans les propriétés de l’élément.</span><span class="sxs-lookup"><span data-stu-id="bd4b9-153">Don't use `px` values in element properties.</span></span>
- <span data-ttu-id="bd4b9-154">N’utilisez pas markdown avec la **propriété ResultSnippet** dans la disposition des résultats pour mettre en évidence la correspondance de requête dans le résultat de recherche.</span><span class="sxs-lookup"><span data-stu-id="bd4b9-154">Don't use markdown with the **ResultSnippet** property in the result layout to highlight query match in the search result.</span></span>

## <a name="resources"></a><span data-ttu-id="bd4b9-155">Ressources</span><span class="sxs-lookup"><span data-stu-id="bd4b9-155">Resources</span></span>

[<span data-ttu-id="bd4b9-156">Personnaliser la page des résultats de la recherche</span><span class="sxs-lookup"><span data-stu-id="bd4b9-156">Customize search result page</span></span>](customize-search-page.md)

[<span data-ttu-id="bd4b9-157">Cartes adaptatives</span><span class="sxs-lookup"><span data-stu-id="bd4b9-157">Adaptive cards</span></span>](/adaptive-cards/authoring-cards/getting-started)

[<span data-ttu-id="bd4b9-158">Langage du modèle de cartes adaptatives</span><span class="sxs-lookup"><span data-stu-id="bd4b9-158">Adaptive Cards Template language</span></span>](/adaptive-cards/templating/language)

[<span data-ttu-id="bd4b9-159">Schéma de carte adaptative</span><span class="sxs-lookup"><span data-stu-id="bd4b9-159">Adaptive card schema</span></span>](https://adaptivecards.io/explorer/)