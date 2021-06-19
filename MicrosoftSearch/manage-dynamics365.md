---
title: Recherche de fédération Dynamics 365 (prévisualisation)
ms.author: dawholl
author: dawholl
manager: kellis
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
description: Gérer l’apparition du contenu Dynamics 365 dans les résultats de recherche
ms.openlocfilehash: 8818d2e6a412feb167c67f465f485b23e868a12a
ms.sourcegitcommit: be989950a7b63281c2348cfd9e6cc13e79b7c067
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/19/2021
ms.locfileid: "53021839"
---
# <a name="dynamics-365-federation-search-preview"></a><span data-ttu-id="f5afe-103">Recherche de fédération Dynamics 365 (prévisualisation)</span><span class="sxs-lookup"><span data-stu-id="f5afe-103">Dynamics 365 federation search (preview)</span></span>

## <a name="microsoft-search-federation-and-connectors"></a><span data-ttu-id="f5afe-104">Recherche Microsoft Fédération et connecteurs</span><span class="sxs-lookup"><span data-stu-id="f5afe-104">Microsoft Search Federation and connectors</span></span>

<span data-ttu-id="f5afe-105">Pour vous aider à rendre Recherche Microsoft plus utile, nous présentons Recherche Microsoft fédération.</span><span class="sxs-lookup"><span data-stu-id="f5afe-105">To help make Microsoft Search more useful, we're introducing Microsoft Search Federation.</span></span> <span data-ttu-id="f5afe-106">Avec la recherche fédérée, les organisations peuvent rendre les données accessibles dans les scénarios suivants Recherche Microsoft :</span><span class="sxs-lookup"><span data-stu-id="f5afe-106">With federated search, organizations can make data in these scenarios accessible in Microsoft Search:</span></span>

* <span data-ttu-id="f5afe-107">Données dans les systèmes soumis à des exigences strictes de conformité</span><span class="sxs-lookup"><span data-stu-id="f5afe-107">Data in systems that are subject to strict compliance requirements</span></span>
* <span data-ttu-id="f5afe-108">Données qui ne peuvent pas quitter les limites du système</span><span class="sxs-lookup"><span data-stu-id="f5afe-108">Data that can't leave system boundaries</span></span>
* <span data-ttu-id="f5afe-109">Données sensibles stockées sur site que votre organisation ne souhaite pas indexer sur le cloud</span><span class="sxs-lookup"><span data-stu-id="f5afe-109">Sensitive data stored on-prem that your organization doesn’t want indexed on the cloud</span></span>

<span data-ttu-id="f5afe-110">Les données accessibles via une connexion de recherche fédérée ne sont pas indexées Recherche Microsoft.</span><span class="sxs-lookup"><span data-stu-id="f5afe-110">Data accessed through a federated search connection isn't indexed in Microsoft Search.</span></span> <span data-ttu-id="f5afe-111">En outre, à l’aide de connecteurs intégrés de Microsoft, il est facile de configurer des connexions de recherche fédérée.</span><span class="sxs-lookup"><span data-stu-id="f5afe-111">Also, using built-in connectors from Microsoft, it's easy to set up federated search connections.</span></span> <span data-ttu-id="f5afe-112">Notre connecteur Dynamics 365 est actuellement en prévisualisation.</span><span class="sxs-lookup"><span data-stu-id="f5afe-112">Our Dynamics 365 connector is currently in preview.</span></span> <span data-ttu-id="f5afe-113">Si vous souhaitez participer à la prévisualisation, faites-le nous savoir [aka.ms/D365FederationSearchPreview](https://aka.ms/D365FederationSearchPreview).</span><span class="sxs-lookup"><span data-stu-id="f5afe-113">If you're interested in joining the preview, let us know at [aka.ms/D365FederationSearchPreview](https://aka.ms/D365FederationSearchPreview).</span></span>

## <a name="dynamics-365-federation-connector"></a><span data-ttu-id="f5afe-114">Connecteur de fédération Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="f5afe-114">Dynamics 365 federation connector</span></span>

<span data-ttu-id="f5afe-115">Microsoft Dynamics 365 est une gamme d’applications métier intelligentes conçues pour la planification des ressources d’entreprise et la gestion de la relation client.</span><span class="sxs-lookup"><span data-stu-id="f5afe-115">Microsoft Dynamics 365 is a line of intelligent business applications designed for enterprise resource planning and customer relationship management.</span></span> <span data-ttu-id="f5afe-116">Avec la fédération Dynamics 365, Recherche Microsoft offre une expérience de recherche transparente, permettant aux utilisateurs de trouver facilement les données client et métier les plus pertinentes stockées dans Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="f5afe-116">With Dynamics 365 federation, Microsoft Search provides a seamless search experience, enabling users to easily find the most relevant customer and business data stored in Dynamics 365.</span></span> <span data-ttu-id="f5afe-117">Le connecteur de fédération Dynamics 365 offre certains avantages clés :</span><span class="sxs-lookup"><span data-stu-id="f5afe-117">The Dynamics 365 federation connector provides some key benefits:</span></span>

* <span data-ttu-id="f5afe-118">**Facile à administrer :** Processus simplifié pour configurer et maintenir la connexion de recherche à une instance Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="f5afe-118">**Easy to administer:** Streamlined process to configure and maintain the search connection to a Dynamics 365 instance.</span></span>
* <span data-ttu-id="f5afe-119">**Facile à utiliser :** Les utilisateurs peuvent facilement et rapidement trouver des informations clés stockées dans Dynamics 365, notamment des comptes, des contacts, des opportunités d’ouverture, etc.</span><span class="sxs-lookup"><span data-stu-id="f5afe-119">**Easy to use:** Users can easily and quickly find key information stored in Dynamics 365, including accounts, contacts, open opportunities, and more.</span></span>
* <span data-ttu-id="f5afe-120">**Contenu enrichi :** Pour rendre les résultats de recherche Dynamics 365 plus utiles, ils incluent des informations clés telles que des prospects, des contacts et des détails de compte.</span><span class="sxs-lookup"><span data-stu-id="f5afe-120">**Richer content:** To make Dynamics 365 search results more useful, they include key information like leads, contacts, and account details.</span></span>
* <span data-ttu-id="f5afe-121">**Protection des données intégrée :** Les résultats dynamics 365 s’affichent uniquement pour les utilisateurs qui ont accès à l’instance connectée.</span><span class="sxs-lookup"><span data-stu-id="f5afe-121">**Built-in data protection:** Dynamics 365 results will only appear for users that have access to the connected instance.</span></span>
* <span data-ttu-id="f5afe-122">**Expérience de recherche unifiée :** Pour conserver une expérience cohérente, les résultats Dynamics 365 sont cohérents sur tous les points d’entrée de recherche.</span><span class="sxs-lookup"><span data-stu-id="f5afe-122">**Unified search experience:** To maintain a cohesive experience, Dynamics 365 results are consistent across all search entry points.</span></span> <span data-ttu-id="f5afe-123">Où que vous recherchez, vous obtenez les mêmes résultats avec la même apparence.</span><span class="sxs-lookup"><span data-stu-id="f5afe-123">Wherever you search, you'll get the same results with the same look and feel.</span></span>

## <a name="what-users-experience"></a><span data-ttu-id="f5afe-124">Expérience des utilisateurs</span><span class="sxs-lookup"><span data-stu-id="f5afe-124">What users experience</span></span>

<span data-ttu-id="f5afe-125">Les réponses Dynamics 365 apparaissent dans les résultats de la recherche dans Recherche Microsoft canevas, y compris SharePoint Online, Bing et Office.</span><span class="sxs-lookup"><span data-stu-id="f5afe-125">Dynamics 365 answers appear in search results across all Microsoft Search canvases, including SharePoint Online, Bing, and Office.</span></span>

:::image type="content" alt-text="Capture d’écran des réponses Dynamics 365 SharePoint, Bing et Office" source="media/dynamics365/dynamics365-answer.png" lightbox="media/dynamics365/dynamics365-answer.png":::

<span data-ttu-id="f5afe-127">À partir de la réponse, il est facile de voir d’autres résultats de recherche Dynamics 365 à l’aide du lien De plus **de résultats Dynamics 365.**</span><span class="sxs-lookup"><span data-stu-id="f5afe-127">From the answer, it's easy to see more Dynamics 365 search results by using the **More Dynamics 365 results** link.</span></span> <span data-ttu-id="f5afe-128">Il permet aux utilisateurs d’obtenir une page de résultats Dynamics 365 dédiée avec d’autres résultats pertinents pour leur requête.</span><span class="sxs-lookup"><span data-stu-id="f5afe-128">It takes users to a dedicated Dynamics 365 results page with more results relevant to their query.</span></span>

:::image type="content" alt-text="Capture d’écran de Dynamics 365 vertical et résultats sur SharePoint, Bing et Office" source="media/dynamics365/dynamics365-vertical.png" lightbox="media/dynamics365/dynamics365-vertical.png":::

<span data-ttu-id="f5afe-130">Le fait de cliquer ou d’appuyer sur un résultat ouvre Dynamics 365 et affiche les informations détaillées.</span><span class="sxs-lookup"><span data-stu-id="f5afe-130">Clicking or tapping any result opens Dynamics 365 and shows the detailed information.</span></span>

:::image type="content" alt-text="Capture d’écran de la page de détails dans Dynamics 365" source="media/dynamics365/dynamics365-detail-page.png" lightbox="media/dynamics365/dynamics365-detail-page.png":::

<span data-ttu-id="f5afe-132">Quel que soit l’endroit où vos utilisateurs lancent leur recherche, leur expérience sera cohérente et leur permettra de trouver rapidement les résultats Dynamics 365 les plus pertinents.</span><span class="sxs-lookup"><span data-stu-id="f5afe-132">No matter where your users start their search their experience will be consistent and enable them to quickly find the most relevant Dynamics 365 results.</span></span> <span data-ttu-id="f5afe-133">Regardez notre [vidéo Microsoft Build 2021](https://youtu.be/TH9QUkQoEJM) pour une démonstration.</span><span class="sxs-lookup"><span data-stu-id="f5afe-133">Check out our [Microsoft Build 2021 video](https://youtu.be/TH9QUkQoEJM) for a demonstration.</span></span>

## <a name="supported-query-patterns"></a><span data-ttu-id="f5afe-134">Modèles de requête pris en charge</span><span class="sxs-lookup"><span data-stu-id="f5afe-134">Supported query patterns</span></span>

<span data-ttu-id="f5afe-135">Les requêtes de nom de produit et de langage naturel sont toutes deux pris en charge lorsque vous utilisez Recherche Microsoft recherche de résultats Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="f5afe-135">Both natural language and product name queries are supported when using Microsoft Search to find Dynamics 365 results.</span></span> <span data-ttu-id="f5afe-136">En outre, les requêtes Dynamics 365 ne sont pas sensibles à la cas.</span><span class="sxs-lookup"><span data-stu-id="f5afe-136">Also, Dynamics 365 queries aren't case sensitive.</span></span> <span data-ttu-id="f5afe-137">Utilisez des modèles de langage naturel pour rechercher des contacts, des comptes et des opportunités (par nom de client ou emplacement) et d’autres requêtes fréquemment utilisées.</span><span class="sxs-lookup"><span data-stu-id="f5afe-137">Use natural language patterns to find contact, account, and opportunities--by customer name or location--and other frequently used queries.</span></span> <span data-ttu-id="f5afe-138">Voici quelques exemples :</span><span class="sxs-lookup"><span data-stu-id="f5afe-138">Here are a few examples:</span></span>

* <span data-ttu-id="f5afe-139">Qui est le contact pour Contoso</span><span class="sxs-lookup"><span data-stu-id="f5afe-139">Who is the contact for Contoso</span></span>
* <span data-ttu-id="f5afe-140">Opportunités ouvertes pour Contoso</span><span class="sxs-lookup"><span data-stu-id="f5afe-140">Open opportunities for Contoso</span></span>
* <span data-ttu-id="f5afe-141">Quelles sont les opportunités ouvertes à Seattle ?</span><span class="sxs-lookup"><span data-stu-id="f5afe-141">What are open opportunities in Seattle</span></span>
* <span data-ttu-id="f5afe-142">Quels sont les comptes à Seattle ?</span><span class="sxs-lookup"><span data-stu-id="f5afe-142">What are the accounts in Seattle</span></span>
* <span data-ttu-id="f5afe-143">Quels sont les contacts à Seattle ?</span><span class="sxs-lookup"><span data-stu-id="f5afe-143">What are the contacts in Seattle</span></span>
* <span data-ttu-id="f5afe-144">Quels sont mes prospects fermant ce mois-ci</span><span class="sxs-lookup"><span data-stu-id="f5afe-144">What are my leads closing this month</span></span>
* <span data-ttu-id="f5afe-145">Appel téléphonique haute priorité</span><span class="sxs-lookup"><span data-stu-id="f5afe-145">High priority phone call</span></span>
* <span data-ttu-id="f5afe-146">Messages électroniques manquants du contact</span><span class="sxs-lookup"><span data-stu-id="f5afe-146">Contact missing emails</span></span>

<span data-ttu-id="f5afe-147">Les modèles de nom de produit 365 365 peuvent déclencher des résultats Dynamics 365, quel que soit l’endroit où ils apparaissent dans une requête :</span><span class="sxs-lookup"><span data-stu-id="f5afe-147">Product name patterns support a range of Dynamics 365 applications and will trigger Dynamics 365 results regardless of where they appear in a query:</span></span>

* <span data-ttu-id="f5afe-148">D365</span><span class="sxs-lookup"><span data-stu-id="f5afe-148">D365</span></span>
* <span data-ttu-id="f5afe-149">Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="f5afe-149">Dynamics 365</span></span>
* <span data-ttu-id="f5afe-150">Dynamics365</span><span class="sxs-lookup"><span data-stu-id="f5afe-150">Dynamics365</span></span>
* <span data-ttu-id="f5afe-151">Dynamics CRM</span><span class="sxs-lookup"><span data-stu-id="f5afe-151">Dynamics CRM</span></span>
* <span data-ttu-id="f5afe-152">Dynamics Sales</span><span class="sxs-lookup"><span data-stu-id="f5afe-152">Dynamics Sales</span></span>
* <span data-ttu-id="f5afe-153">Service clientèle Dynamics</span><span class="sxs-lookup"><span data-stu-id="f5afe-153">Dynamics Customer Service</span></span>
* <span data-ttu-id="f5afe-154">Dynamics Service</span><span class="sxs-lookup"><span data-stu-id="f5afe-154">Dynamics Service</span></span>
* <span data-ttu-id="f5afe-155">Dynamics Field Service</span><span class="sxs-lookup"><span data-stu-id="f5afe-155">Dynamics Field Service</span></span>

## <a name="configure-the-dynamics-365-connector"></a><span data-ttu-id="f5afe-156">Configurer le connecteur Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="f5afe-156">Configure the Dynamics 365 connector</span></span>

<span data-ttu-id="f5afe-157">Avec cette configuration simple, vous pouvez activer l’expérience de recherche de fédération Dynamics 365 pour les membres de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="f5afe-157">With this simple configuration, you can enable the Dynamics 365 federation search experience for people in your organization.</span></span>

1. <span data-ttu-id="f5afe-158">Dans la [Centre d’administration Microsoft 365](https://admin.microsoft.com), allez aux [sources de données.](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/connectors)</span><span class="sxs-lookup"><span data-stu-id="f5afe-158">In the [Microsoft 365 admin center](https://admin.microsoft.com), go to [Data sources](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/connectors).</span></span>

2. <span data-ttu-id="f5afe-159">Dans la section Applications et services Microsoft, sous Microsoft Dynamics 365, sélectionnez **Gérer** pour ouvrir le panneau Microsoft Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="f5afe-159">In the Microsoft apps and services section, under Microsoft Dynamics 365, select **Manage** to open the Microsoft Dynamics 365 panel.</span></span>

3. <span data-ttu-id="f5afe-160">Activez le connecteur pour votre organisation.</span><span class="sxs-lookup"><span data-stu-id="f5afe-160">Enable the connector for your organization.</span></span>

4. <span data-ttu-id="f5afe-161">Dans la **liste Points de terminaison,** sélectionnez votre environnement Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="f5afe-161">In the **Endpoints** list, select your Dynamics 365 environment.</span></span>

5. <span data-ttu-id="f5afe-162">Dans **l’ID de connexion,** entrez un ID unique pour cette connexion.</span><span class="sxs-lookup"><span data-stu-id="f5afe-162">In the **Connection ID**, enter a unique ID for this connection.</span></span>

6. <span data-ttu-id="f5afe-163">Vérifiez et cochez la case de consentement.</span><span class="sxs-lookup"><span data-stu-id="f5afe-163">Review and select the consent check box.</span></span>

7. <span data-ttu-id="f5afe-164">Sélectionnez **Enregistrer** pour terminer la configuration de la connexion.</span><span class="sxs-lookup"><span data-stu-id="f5afe-164">Select **Save** to finish the connection setup.</span></span>

:::image type="content" alt-text="Capture d’écran du panneau de configurer Dynamics 365 dans la Centre d’administration Microsoft 365" source="media/dynamics365/dynamic365-connection-setup.png" lightbox="media/dynamics365/dynamic365-connection-setup.png":::

<span data-ttu-id="f5afe-166">Une fois l’installation terminée, les réponses et le secteur vertical de Dynamics 365 apparaissent uniquement pour les utilisateurs titulaires d’une licence Dynamics 365 valide et d’un accès à l’environnement Dynamics 365 connecté.</span><span class="sxs-lookup"><span data-stu-id="f5afe-166">When the setup is complete, Dynamics 365 answers and vertical will only appear for users with a valid Dynamics 365 license and access to the connected Dynamics 365 environment.</span></span> <span data-ttu-id="f5afe-167">À tout moment, vous pouvez revenir à ces paramètres et modifier l’environnement de point de terminaison de connexion ou désactiver la connexion.</span><span class="sxs-lookup"><span data-stu-id="f5afe-167">At any time, you can return to these settings and change the connection endpoint environment or deactivate the connection.</span></span>
