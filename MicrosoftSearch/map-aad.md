---
title: Mappage des identités AAD
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
description: Procédure de mappage des identités AAD
ms.openlocfilehash: db0378e596c560edebd2ceb942e6327b47a5286b
ms.sourcegitcommit: 59cdd3f0f82b7918399bf44d27d9891076090f4f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/20/2020
ms.locfileid: "49367702"
---
# <a name="map-your-azure-ad-identities"></a><span data-ttu-id="78642-103">Mapper vos identités Azure AD</span><span class="sxs-lookup"><span data-stu-id="78642-103">Map your Azure AD Identities</span></span>  

<span data-ttu-id="78642-104">Cet article vous guide tout au long des étapes de mappage de vos identités Azure AD à un identificateur unique pour votre source de données (identité non Azure AD) afin que les utilisateurs de votre liste de contrôle d’accès avec des identités autres que Azure AD puissent voir les résultats de la recherche de connecteur étendues à ceux-ci.</span><span class="sxs-lookup"><span data-stu-id="78642-104">This article walks you through the steps of mapping your Azure AD identities to a unique identifier for your data source (non-Azure AD identity) so that people in your Access Control List (ACL) with non-Azure AD identities can see connector search results scoped to them.</span></span>

<span data-ttu-id="78642-105">Ces étapes s’appliquent uniquement aux administrateurs de recherche qui configurent un connecteur [Salesforce](salesforce-connector.md) par Microsoft avec des autorisations de recherche pour « uniquement les personnes ayant accès à cette source de données » et le type d’identité « AAD ».</span><span class="sxs-lookup"><span data-stu-id="78642-105">These steps are only relevant to search administrators who are setting up a [Salesforce](salesforce-connector.md) connector by Microsoft with search permissions for "Only people with access to this data source" and identity type "AAD."</span></span> <span data-ttu-id="78642-106">Les étapes suivantes vous expliquent comment mapper les propriétés de votre utilisateur Azure AD aux ID de **Fédération** de vos utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="78642-106">The following steps walk you through how to map your Azure AD user properties to your users' **Federation IDs**.</span></span>

>[!NOTE]
><span data-ttu-id="78642-107">Si vous configurez un [connecteur Salesforce](salesforce-connector.md) et que vous sélectionnez **uniquement les personnes ayant accès à cette source de données** et le type d’identité **non-AAD** sur l’écran des autorisations de recherche, reportez-vous à la rubrique [mapper votre article d’identités non Azure ad](map-non-aad.md) pour obtenir des informations sur la façon de mapper des identités non Azure ad.</span><span class="sxs-lookup"><span data-stu-id="78642-107">If you are setting up a [Salesforce connector](salesforce-connector.md) and select **Only people with access to this data source** and identity type **non-AAD** on the search permissions screen, refer to the [Map your non-Azure AD Identities](map-non-aad.md) article for steps on how to map non-Azure AD identities.</span></span>  

## <a name="steps-for-mapping-your-azure-ad-properties"></a><span data-ttu-id="78642-108">Étapes de mappage de vos propriétés Azure AD</span><span class="sxs-lookup"><span data-stu-id="78642-108">Steps for mapping your Azure AD properties</span></span>

### <a name="1-select-azure-ad-user-properties-to-map"></a><span data-ttu-id="78642-109">1. Sélectionnez les propriétés de l’utilisateur Azure AD à mapper</span><span class="sxs-lookup"><span data-stu-id="78642-109">1. Select Azure AD user properties to map</span></span>

<span data-ttu-id="78642-110">Vous pouvez sélectionner les propriétés Azure AD que vous devez mapper à l’ID de Fédération.</span><span class="sxs-lookup"><span data-stu-id="78642-110">You can select the Azure AD properties you need to map to the Federation ID.</span></span>

<span data-ttu-id="78642-111">Vous pouvez sélectionner une propriété utilisateur Azure AD dans la liste déroulante.</span><span class="sxs-lookup"><span data-stu-id="78642-111">You can select an Azure AD user property from the dropdown.</span></span> <span data-ttu-id="78642-112">Vous pouvez également ajouter autant de propriétés d’utilisateur Azure AD que vous le souhaitez si ces propriétés sont nécessaires pour créer le mappage d’ID de Fédération pour votre organisation.</span><span class="sxs-lookup"><span data-stu-id="78642-112">You can also add as many Azure AD user properties as you would like if these properties are necessary to create the Federation ID mapping for your organization.</span></span>

### <a name="2-create-formula-to-complete-mapping"></a><span data-ttu-id="78642-113">2. créer une formule pour terminer le mappage</span><span class="sxs-lookup"><span data-stu-id="78642-113">2. Create formula to complete mapping</span></span>

<span data-ttu-id="78642-114">Vous pouvez combiner les valeurs des propriétés de l’utilisateur Azure AD pour former l’ID de Fédération unique.</span><span class="sxs-lookup"><span data-stu-id="78642-114">You can combine the values of the Azure AD user properties to form the unique Federation ID.</span></span>

<span data-ttu-id="78642-115">Dans la zone formule, « {0} » correspond à la *première* propriété Azure ad que vous avez sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="78642-115">In the formula box, "{0}" corresponds to the *first* Azure AD property you selected.</span></span> <span data-ttu-id="78642-116">« {1} » correspond à la *deuxième* propriété Azure ad que vous avez sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="78642-116">"{1}" corresponds to the *second* Azure AD property you selected.</span></span> <span data-ttu-id="78642-117">« {2} » correspond à la *troisième* propriété Azure ad, et ainsi de suite.</span><span class="sxs-lookup"><span data-stu-id="78642-117">"{2}" corresponds to the *third* Azure AD property, and so on.</span></span>  

<span data-ttu-id="78642-118">Voici quelques exemples de formules avec des résultats d’expressions régulières et des sorties de formule :</span><span class="sxs-lookup"><span data-stu-id="78642-118">Below are some examples of formulas with sample regular expression outputs and formula outputs:</span></span>

| <span data-ttu-id="78642-119">Exemple de formule</span><span class="sxs-lookup"><span data-stu-id="78642-119">Sample formula</span></span>                  | <span data-ttu-id="78642-120">Valeur de {0} la propriété pour un exemple d’utilisateur</span><span class="sxs-lookup"><span data-stu-id="78642-120">Value of property {0} for a sample user</span></span>                 | <span data-ttu-id="78642-121">Valeur de {1} la propriété pour un exemple d’utilisateur</span><span class="sxs-lookup"><span data-stu-id="78642-121">Value of property {1} for a sample user</span></span>           | <span data-ttu-id="78642-122">Sortie de la formule</span><span class="sxs-lookup"><span data-stu-id="78642-122">Output of formula</span></span>                  |
| :------------------- | :------------------- |:---------------|:---------------|
| <span data-ttu-id="78642-123">{0}.{1} @contoso. com</span><span class="sxs-lookup"><span data-stu-id="78642-123">{0}.{1}@contoso.com</span></span>  | <span data-ttu-id="78642-124">FirstName</span><span class="sxs-lookup"><span data-stu-id="78642-124">firstname</span></span> | <span data-ttu-id="78642-125">prénom</span><span class="sxs-lookup"><span data-stu-id="78642-125">lastname</span></span> |<span data-ttu-id="78642-126">firstname.lastname@contoso.com</span><span class="sxs-lookup"><span data-stu-id="78642-126">firstname.lastname@contoso.com</span></span>
| <span data-ttu-id="78642-127">{0}@domain. com</span><span class="sxs-lookup"><span data-stu-id="78642-127">{0}@domain.com</span></span>                 | <span data-ttu-id="78642-128">identifi</span><span class="sxs-lookup"><span data-stu-id="78642-128">userid</span></span>                 |             |<span data-ttu-id="78642-129">userid@domain.com</span><span class="sxs-lookup"><span data-stu-id="78642-129">userid@domain.com</span></span>

<span data-ttu-id="78642-130">Une fois que vous avez fourni votre formule, vous pouvez éventuellement cliquer sur **Aperçu** pour afficher un aperçu de 5 utilisateurs aléatoires de votre source de données avec leurs mappages utilisateur respectifs appliqués.</span><span class="sxs-lookup"><span data-stu-id="78642-130">After you provide your formula, you can optionally click **Preview** to see a preview of 5 random users from your data source with their respective user mappings applied.</span></span> <span data-ttu-id="78642-131">La sortie de l’aperçu inclut la valeur des propriétés de l’utilisateur Azure AD sélectionnées à l’étape 1 pour ces utilisateurs et le résultat de la formule finale fournie à l’étape 2 pour cet utilisateur.</span><span class="sxs-lookup"><span data-stu-id="78642-131">The output of the preview includes the value of the Azure AD user properties selected in step 1 for those users and the output of the final formula provided in step 2 for that user.</span></span> <span data-ttu-id="78642-132">Il indique également si la sortie de la formule peut être résolue en utilisateur Azure AD dans votre client via une icône « réussite » ou « échec ».</span><span class="sxs-lookup"><span data-stu-id="78642-132">It also indicates whether the output of the formula could be resolved to an Azure AD user in your tenant via a "Success" or "Failed" icon.</span></span>  

>[!NOTE]
><span data-ttu-id="78642-133">Vous pouvez continuer à créer votre connexion si un ou plusieurs mappages utilisateur ont un État « échec » une fois que vous avez cliqué sur **Aperçu**.</span><span class="sxs-lookup"><span data-stu-id="78642-133">You can still proceed with creating your connection if one or more user mappings have a "Failed" status after you click **Preview**.</span></span> <span data-ttu-id="78642-134">L’aperçu montre 5 utilisateurs aléatoires et leurs mappages à partir de votre source de données.</span><span class="sxs-lookup"><span data-stu-id="78642-134">The preview shows 5 random users and their mappings from your data source.</span></span> <span data-ttu-id="78642-135">Si le mappage que vous fournissez ne mappe pas tous les utilisateurs, vous pouvez observer ce cas.</span><span class="sxs-lookup"><span data-stu-id="78642-135">If the mapping you provide does not map all users, you may experience this case.</span></span>

## <a name="sample-azure-ad-mapping"></a><span data-ttu-id="78642-136">Exemple de mappage Azure AD</span><span class="sxs-lookup"><span data-stu-id="78642-136">Sample Azure AD mapping</span></span>

<span data-ttu-id="78642-137">Consultez la capture instantanée ci-dessous pour obtenir un exemple de mappage Azure AD.</span><span class="sxs-lookup"><span data-stu-id="78642-137">See the snapshot below for a sample Azure AD mapping.</span></span>

![Exemple de capture instantanée sur la façon de remplir la page de mappage Azure AD](media/aad-mapping.png)

## <a name="limitations"></a><span data-ttu-id="78642-139">Limites</span><span class="sxs-lookup"><span data-stu-id="78642-139">Limitations</span></span>  

- <span data-ttu-id="78642-140">Un seul mappage est pris en charge pour tous les utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="78642-140">Only one mapping is supported for all users.</span></span> <span data-ttu-id="78642-141">Les mappages conditionnels ne sont pas pris en charge.</span><span class="sxs-lookup"><span data-stu-id="78642-141">Conditional mappings are not supported.</span></span>  

- <span data-ttu-id="78642-142">Vous ne pouvez pas modifier votre mappage une fois la connexion publiée.</span><span class="sxs-lookup"><span data-stu-id="78642-142">You cannot change your mapping once the connection is published.</span></span>  

- <span data-ttu-id="78642-143">Les expressions Regex sur les propriétés de l’utilisateur Azure AD ne sont pas prises en charge pour la transformation d’ID de Fédération Azure AD.</span><span class="sxs-lookup"><span data-stu-id="78642-143">Regex-based expressions against the Azure AD user properties are not supported for the Azure AD to Federation ID transformation.</span></span>