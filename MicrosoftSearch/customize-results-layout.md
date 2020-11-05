---
title: Personnaliser la disposition des résultats de la recherche
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
description: À l’aide de cartes adaptatives, créer une disposition pour afficher vos résultats de recherche personnalisés
ms.openlocfilehash: 5bd42eded291781f5122cfede3759327b5222108
ms.sourcegitcommit: 995ce23d4e47a3456a02dba0ba7c9cd0de64528a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/05/2020
ms.locfileid: "48919509"
---
<!-- markdownlint-disable no-hard-tabs -->
# <a name="create-a-layout-to-customize-search-results"></a><span data-ttu-id="be7b7-103">Créer une disposition pour personnaliser les résultats de la recherche</span><span class="sxs-lookup"><span data-stu-id="be7b7-103">Create a layout to customize search results</span></span>

<span data-ttu-id="be7b7-104">Vous pouvez concevoir la disposition des résultats pour un secteur vertical personnalisé à l’aide du concepteur de mise en page.</span><span class="sxs-lookup"><span data-stu-id="be7b7-104">You can design the result layout for a custom vertical using the search layout designer.</span></span> <span data-ttu-id="be7b7-105">Vous pouvez commencer à concevoir la disposition en choisissant des modèles proposés dans le concepteur de mise en page et en les utilisant si elles répondent à vos besoins.</span><span class="sxs-lookup"><span data-stu-id="be7b7-105">You can start designing the layout by choosing templates offered in the layout designer and using them if they fit your requirements.</span></span> <span data-ttu-id="be7b7-106">Ou vous pouvez choisir de modifier ces modèles de différentes manières pour répondre à vos besoins.</span><span class="sxs-lookup"><span data-stu-id="be7b7-106">Or you can choose to edit these templates in various ways to fit your requirements.</span></span> <span data-ttu-id="be7b7-107">Par exemple, ajouter/supprimer des images, ajouter/supprimer du texte et modifier du texte.</span><span class="sxs-lookup"><span data-stu-id="be7b7-107">For example, add/remove images, add/remove text, and modify text.</span></span> <span data-ttu-id="be7b7-108">Si aucun des modèles ne répond à vos besoins, vous pouvez choisir de commencer à concevoir votre disposition à l’aide d’un modèle vide.</span><span class="sxs-lookup"><span data-stu-id="be7b7-108">If none of the templates meet your requirements, you can choose to start designing your layout using a blank template.</span></span>  

<span data-ttu-id="be7b7-109">Une fois la mise en page prête, utilisez le [langage de modèle cartes adaptatives](https://docs.microsoft.com/adaptive-cards/templating/language) pour créer un JSON de mise en page de résultat utilisé pour définir un type de résultat.</span><span class="sxs-lookup"><span data-stu-id="be7b7-109">After the layout is ready, use the [Adaptive Cards Template language](https://docs.microsoft.com/adaptive-cards/templating/language) to create a result layout JSON that's used to define a result type.</span></span> <span data-ttu-id="be7b7-110">Vous mappez les propriétés de résultat à la mise en page à l’aide de l’étape de mappage du concepteur de mise en page.</span><span class="sxs-lookup"><span data-stu-id="be7b7-110">You map the result properties to the layout using the Mapping step in the layout designer.</span></span>  

## <a name="create-a-layout-on-your-own"></a><span data-ttu-id="be7b7-111">Créer une mise en page</span><span class="sxs-lookup"><span data-stu-id="be7b7-111">Create a layout on your own</span></span>

<span data-ttu-id="be7b7-112">La création d’une mise en page personnelle nécessite de connaître les [cartes adaptatives](https://docs.microsoft.com/adaptive-cards/authoring-cards/getting-started) et leur [schéma](https://adaptivecards.io/explorer/).</span><span class="sxs-lookup"><span data-stu-id="be7b7-112">Creating a layout on your own requires knowledge of [adaptive cards](https://docs.microsoft.com/adaptive-cards/authoring-cards/getting-started) and their [schema](https://adaptivecards.io/explorer/).</span></span> <span data-ttu-id="be7b7-113">La disposition des résultats de la recherche utilise un sous-ensemble des éléments proposés par des cartes adaptatives, et vous pouvez utiliser le concepteur de mise en page pour en savoir plus sur l’ensemble d’éléments pris en charge.</span><span class="sxs-lookup"><span data-stu-id="be7b7-113">Search result layout uses a subset of the elements offered by adaptive cards, and you can use the layout designer to learn about the supported set of elements.</span></span>  

<span data-ttu-id="be7b7-114">Lors de la création de votre propre disposition, créez la disposition de la carte adaptative à l’aide des données de votre connecteur, puis finalisez la mise en page.</span><span class="sxs-lookup"><span data-stu-id="be7b7-114">While creating your own layout, create the adaptive card layout using data from your connector, and then finalize the layout.</span></span>
<span data-ttu-id="be7b7-115">La création de votre propre disposition comporte deux étapes principales :</span><span class="sxs-lookup"><span data-stu-id="be7b7-115">There are two main steps in creating your own layout:</span></span>

- <span data-ttu-id="be7b7-116">Concevez la disposition.</span><span class="sxs-lookup"><span data-stu-id="be7b7-116">Design the layout.</span></span>
- <span data-ttu-id="be7b7-117">Séparez les données du modèle.</span><span class="sxs-lookup"><span data-stu-id="be7b7-117">Separate the data from the template.</span></span>

### <a name="design-the-layout"></a><span data-ttu-id="be7b7-118">Conception de la mise en page</span><span class="sxs-lookup"><span data-stu-id="be7b7-118">Design the layout</span></span>

<span data-ttu-id="be7b7-119">Dans cet exemple, nous affichons une disposition avec un en-tête, un lien et un texte descriptif.</span><span class="sxs-lookup"><span data-stu-id="be7b7-119">In this example, we show a layout with a header, link, and descriptive text.</span></span>

![Exemple de mise en page avec un en-tête, un lien et une description.](media/Verts-ExampleLayout.png)

<span data-ttu-id="be7b7-121">Et voici le fichier JSON associé à la mise en page :</span><span class="sxs-lookup"><span data-stu-id="be7b7-121">And here's the layout's associated JSON file:</span></span>

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

### <a name="separate-the-data-from-the-layout"></a><span data-ttu-id="be7b7-122">Séparer les données de la mise en page</span><span class="sxs-lookup"><span data-stu-id="be7b7-122">Separate the data from the layout</span></span>

<span data-ttu-id="be7b7-123">Vous pouvez séparer les données de la mise en page et lier les données.</span><span class="sxs-lookup"><span data-stu-id="be7b7-123">You can separate the data from the layout and bind the data.</span></span>

<span data-ttu-id="be7b7-124">Voici la disposition JSON après avoir lié les données :</span><span class="sxs-lookup"><span data-stu-id="be7b7-124">Here's Layout JSON after binding the data:</span></span>

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

<span data-ttu-id="be7b7-125">Exemples de données : spécifiez des exemples de données dans l' **éditeur de données exemple** pour afficher la carte liée aux données en **mode aperçu**.</span><span class="sxs-lookup"><span data-stu-id="be7b7-125">Sample data: Specify sample data in the **Sample Data Editor** to view the data-bound card when in **Preview Mode**.</span></span>

```json
{

    "title": "Contoso Marketing Analysis - Q3 FY18",
    "titleUrl": "https://contoso.com/hr/link",
    "link": "https://contoso.com/hr/link",
    "description": "Marketing team, and looking at the Contoso Marketing documents on the team site. Yo can't see right...Marketing Planning presentation?"

}
```

## <a name="map-the-layout-to-the-result-properties"></a><span data-ttu-id="be7b7-126">Mapper la disposition aux propriétés de résultat</span><span class="sxs-lookup"><span data-stu-id="be7b7-126">Map the layout to the result properties</span></span>

<span data-ttu-id="be7b7-127">Vous devez mapper chaque champ de la mise en page à une propriété Result ou à une propriété Connector pour générer le JSON de la disposition du résultat.</span><span class="sxs-lookup"><span data-stu-id="be7b7-127">You must map each field of the layout to a result property or a connector property to generate the result layout JSON.</span></span>

![Capture d’écran d’un exemple de mise en page sur la page du concepteur de mise en page de recherche avec un champ sélectionné et le volet de propriétés ouvert.](media/Verts-SearchLayoutDesigner.png)

<span data-ttu-id="be7b7-129">Sélectionnez un champ dans la mise en page pour mettre en surbrillance les variables devant être mappées.</span><span class="sxs-lookup"><span data-stu-id="be7b7-129">Select a field in the layout to highlight the variables that need to be mapped.</span></span> <span data-ttu-id="be7b7-130">Vous pouvez utiliser plusieurs variables pour un seul champ et tous les champs doivent être mappés sur les propriétés de résultat.</span><span class="sxs-lookup"><span data-stu-id="be7b7-130">You can use multiple variables for a single field, and all fields must be mapped to the result properties.</span></span>

### <a name="show-snippet-on-search-result"></a><span data-ttu-id="be7b7-131">Afficher l’extrait de résultats de la recherche</span><span class="sxs-lookup"><span data-stu-id="be7b7-131">Show snippet on search result</span></span>  

<span data-ttu-id="be7b7-132">Les extraits de code dynamiques générés sur la propriété de **contenu** du résultat du connecteur peuvent être affichés sur le résultat de la recherche.</span><span class="sxs-lookup"><span data-stu-id="be7b7-132">Dynamic snippets generated on the **content** property of the connector result can be shown on the search result.</span></span> <span data-ttu-id="be7b7-133">**ResultSnippet** est la propriété système qui agit comme une propriété d’espace réservé pour les extraits de code générés pour chaque résultat de connecteur.</span><span class="sxs-lookup"><span data-stu-id="be7b7-133">**ResultSnippet** is the system property that acts as a placeholder property for the snippets generated for each Connector result.</span></span> <span data-ttu-id="be7b7-134">Pour afficher les extraits de code sur la disposition des résultats, la propriété système **ResultSnippet** doit être mappée sur un champ approprié, par exemple Description, dans la disposition des résultats de la recherche.</span><span class="sxs-lookup"><span data-stu-id="be7b7-134">To show the snippets on the result layout, the **ResultSnippet** system property must be mapped to an appropriate field, for example Description, in the search result layout.</span></span> <span data-ttu-id="be7b7-135">Les extraits de code générés sur chaque résultat surlignent également les correspondances dans l’extrait de code avec le terme de requête entré par l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="be7b7-135">Snippets generated on each result also highlight the matches in the Snippet with the query term entered by the user.</span></span>

## <a name="things-to-consider"></a><span data-ttu-id="be7b7-136">Informations importantes</span><span class="sxs-lookup"><span data-stu-id="be7b7-136">Things to consider</span></span>

<span data-ttu-id="be7b7-137">Avant de commencer, vous devez effectuer quelques opérations et quelques éléments que vous devez éviter pour garantir la réussite de vos mises en page.</span><span class="sxs-lookup"><span data-stu-id="be7b7-137">Before you get started, there are a few things that you should do and a few things you should avoid to ensure that your layouts will be successful.</span></span>

### <a name="do"></a><span data-ttu-id="be7b7-138">À faire</span><span class="sxs-lookup"><span data-stu-id="be7b7-138">Do</span></span>

- <span data-ttu-id="be7b7-139">Modifier un modèle pour indiquer le lien du logo dans la mise en page si vous utilisez des liens statiques pour les logos et non pour les propriétés de résultat.</span><span class="sxs-lookup"><span data-stu-id="be7b7-139">Edit a template to provide the logo link in the layout if you're using static links for logos and not result properties.</span></span>
- <span data-ttu-id="be7b7-140">Valider la disposition des résultats pour les scénarios où aucune donnée n’est renvoyée pour une propriété Result utilisée dans le JSON résultant.</span><span class="sxs-lookup"><span data-stu-id="be7b7-140">Validate the result layout for scenarios where no data is returned for a result property used in the result JSON.</span></span> <span data-ttu-id="be7b7-141">Utilisez la `$when` condition pour masquer un élément si la propriété ne contient pas de données.</span><span class="sxs-lookup"><span data-stu-id="be7b7-141">Use the `$when` condition to hide an element if the property doesn't contain data.</span></span>  
- <span data-ttu-id="be7b7-142">Assurez-vous que les types de données de la `$when` condition et la propriété Result correspondent.</span><span class="sxs-lookup"><span data-stu-id="be7b7-142">Make sure that data types of the `$when` condition and the result property match.</span></span> <span data-ttu-id="be7b7-143">Par exemple, ne pas comparer `Number` avec `Text` dans la `$when` condition.</span><span class="sxs-lookup"><span data-stu-id="be7b7-143">For example, don't compare `Number` with `Text` in the `$when` condition.</span></span>  
- <span data-ttu-id="be7b7-144">Considérez les conditions requises pour les thèmes lors de la conception d’une disposition de résultats.</span><span class="sxs-lookup"><span data-stu-id="be7b7-144">Think of theme requirements when designing a result layout.</span></span>  
- <span data-ttu-id="be7b7-145">Assurez-vous que l' `Textblock`   élément peut gérer le contenu dynamique.</span><span class="sxs-lookup"><span data-stu-id="be7b7-145">Make sure that the `Textblock` element can handle dynamic content.</span></span> <span data-ttu-id="be7b7-146">Vous pouvez utiliser les `wrap` `maxLines` Propriétés et de l’élément à cet effet.</span><span class="sxs-lookup"><span data-stu-id="be7b7-146">You can use the `wrap` and `maxLines` element properties for this purpose.</span></span>
- <span data-ttu-id="be7b7-147">Format correct de la date lors `{DATE()}` de l’utilisation de la démarque.</span><span class="sxs-lookup"><span data-stu-id="be7b7-147">Properly format the date when using `{DATE()}` in Markdown.</span></span>  

### <a name="dont"></a><span data-ttu-id="be7b7-148">À ne pas faire</span><span class="sxs-lookup"><span data-stu-id="be7b7-148">Don't</span></span>

- <span data-ttu-id="be7b7-149">Ne définissez pas de types de données non valides lors de la liaison de valeurs.</span><span class="sxs-lookup"><span data-stu-id="be7b7-149">Don't define invalid data types when binding values.</span></span> <span data-ttu-id="be7b7-150">Pour plus d’informations sur les types de données, voir [Manage the Search Schema](https://docs.microsoft.com/sharepoint/search/manage-the-search-schema).</span><span class="sxs-lookup"><span data-stu-id="be7b7-150">For more information about data types, see [Manage the Search schema](https://docs.microsoft.com/sharepoint/search/manage-the-search-schema).</span></span>
- <span data-ttu-id="be7b7-151">Évitez de détourer le résultat sur la page de résultats en suivant la hauteur maximale du JSON de la disposition du résultat.</span><span class="sxs-lookup"><span data-stu-id="be7b7-151">Avoid cropping the result on the result page by following the maximum height of the result layout JSON.</span></span> <span data-ttu-id="be7b7-152">Si vous dépassez la hauteur maximale de la disposition du résultat, le résultat sera rogné sur la page de résultats.</span><span class="sxs-lookup"><span data-stu-id="be7b7-152">If you exceed the maximum height of the result layout, the result will be cropped on the result page.</span></span>
- <span data-ttu-id="be7b7-153">N’utilisez pas `px` de valeurs dans les propriétés de l’élément.</span><span class="sxs-lookup"><span data-stu-id="be7b7-153">Don't use `px` values in element properties.</span></span>
- <span data-ttu-id="be7b7-154">N’utilisez pas la démarque avec la propriété **ResultSnippet** dans la mise en page des résultats pour mettre en surbrillance la requête dans le résultat de la recherche.</span><span class="sxs-lookup"><span data-stu-id="be7b7-154">Don't use markdown when with the **ResultSnippet** property in the result layout to highlight query match in the search result.</span></span>

## <a name="resources"></a><span data-ttu-id="be7b7-155">Ressources</span><span class="sxs-lookup"><span data-stu-id="be7b7-155">Resources</span></span>

[<span data-ttu-id="be7b7-156">Personnaliser la page des résultats de recherche</span><span class="sxs-lookup"><span data-stu-id="be7b7-156">Customize search result page</span></span>](customize-search-page.md)

[<span data-ttu-id="be7b7-157">Cartes adaptatives</span><span class="sxs-lookup"><span data-stu-id="be7b7-157">Adaptive cards</span></span>](https://docs.microsoft.com/adaptive-cards/authoring-cards/getting-started)

[<span data-ttu-id="be7b7-158">Langue du modèle cartes adaptatives</span><span class="sxs-lookup"><span data-stu-id="be7b7-158">Adaptive Cards Template language</span></span>](https://docs.microsoft.com/adaptive-cards/templating/language)

[<span data-ttu-id="be7b7-159">Schéma de carte adaptative</span><span class="sxs-lookup"><span data-stu-id="be7b7-159">Adaptive card schema</span></span>](https://adaptivecards.io/explorer/)