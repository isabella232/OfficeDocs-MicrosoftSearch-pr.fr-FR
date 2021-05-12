---
title: Gérer les connecteurs Microsoft Graph pour Microsoft Search (recherche Microsoft)
ms.author: mecampos
author: monaray97
manager: mnirkhe
audience: Admin
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: Gérer les connecteurs Microsoft Graph pour Microsoft Search (recherche Microsoft).
ms.openlocfilehash: 685b501f3afe25d75c13a1fe6cc2c1b5db8a3511
ms.sourcegitcommit: e5d695c40b68c2f1fa082fa9de20b9aa6d5b8050
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2021
ms.locfileid: "52325167"
---
<!-- markdownlint-disable no-inline-html -->

# <a name="monitor-your-connections"></a><span data-ttu-id="08d9b-103">Surveiller vos connexions</span><span class="sxs-lookup"><span data-stu-id="08d9b-103">Monitor your connections</span></span>

<span data-ttu-id="08d9b-104">Pour accéder à vos connecteurs et les gérer, vous devez être désigné comme administrateur de recherche pour votre client.</span><span class="sxs-lookup"><span data-stu-id="08d9b-104">To access and manage your connectors, you must be designated as a search administrator for your tenant.</span></span> <span data-ttu-id="08d9b-105">Contactez votre administrateur client pour vous fournir le rôle d’administrateur de recherche.</span><span class="sxs-lookup"><span data-stu-id="08d9b-105">Contact your tenant administrator to provision you for the search administrator role.</span></span>

## <a name="connection-operations"></a><span data-ttu-id="08d9b-106">Opérations de connexion</span><span class="sxs-lookup"><span data-stu-id="08d9b-106">Connection Operations</span></span>

<span data-ttu-id="08d9b-107">Accédez à [l’onglet Connecteurs](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/Connectors) dans le [Centre d’administration Microsoft 365.](https://admin.microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="08d9b-107">Navigate to the [Connectors tab](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/Connectors) in the [Microsoft 365 admin center](https://admin.microsoft.com).</span></span>

<span data-ttu-id="08d9b-108">Pour chaque type de connecteur, le Centre [d’administration Microsoft 365](https://admin.microsoft.com) prend en charge les opérations indiquées dans le tableau suivant :</span><span class="sxs-lookup"><span data-stu-id="08d9b-108">For each connector type, the [Microsoft 365 admin center](https://admin.microsoft.com) supports the operations shown in the following table:</span></span>

<span data-ttu-id="08d9b-109">Opération</span><span class="sxs-lookup"><span data-stu-id="08d9b-109">Operation</span></span> | <span data-ttu-id="08d9b-110">Connecteurs Graph par Microsoft</span><span class="sxs-lookup"><span data-stu-id="08d9b-110">Graph connectors by Microsoft</span></span> | <span data-ttu-id="08d9b-111">Connecteurs partenaires ou Graph</span><span class="sxs-lookup"><span data-stu-id="08d9b-111">Partner or Graph connectors</span></span>
--- | --- | ---
<span data-ttu-id="08d9b-112">Ajouter une connexion</span><span class="sxs-lookup"><span data-stu-id="08d9b-112">Add a connection</span></span> | <span data-ttu-id="08d9b-113">:heavy_check_mark : (voir [vue d’ensemble du programme d’installation)](configure-connector.md)</span><span class="sxs-lookup"><span data-stu-id="08d9b-113">:heavy_check_mark: (See [Setup overview](configure-connector.md))</span></span> | <span data-ttu-id="08d9b-114">:x : (faire référence à l’UX de votre partenaire ou de votre connecteur personnalisé)</span><span class="sxs-lookup"><span data-stu-id="08d9b-114">:x: (Refer to your partner or custom-built connector admin UX)</span></span>
<span data-ttu-id="08d9b-115">Supprimer une connexion</span><span class="sxs-lookup"><span data-stu-id="08d9b-115">Delete a connection</span></span> | :heavy_check_mark: | :heavy_check_mark:
<span data-ttu-id="08d9b-118">Modifier une connexion publiée</span><span class="sxs-lookup"><span data-stu-id="08d9b-118">Edit a published connection</span></span> | <span data-ttu-id="08d9b-119">:heavy_check_mark : nom et description</span><span class="sxs-lookup"><span data-stu-id="08d9b-119">:heavy_check_mark: Name and Description</span></span><br></br> <span data-ttu-id="08d9b-120">:heavy_check_mark : paramètres de connexion</span><span class="sxs-lookup"><span data-stu-id="08d9b-120">:heavy_check_mark: Connection settings</span></span><br></br> <span data-ttu-id="08d9b-121">:heavy_check_mark : étiquettes de propriété</span><span class="sxs-lookup"><span data-stu-id="08d9b-121">:heavy_check_mark: Property labels</span></span><br></br> <span data-ttu-id="08d9b-122">:heavy_check_mark : schéma</span><span class="sxs-lookup"><span data-stu-id="08d9b-122">:heavy_check_mark: Schema</span></span><br></br> <span data-ttu-id="08d9b-123">:heavy_check_mark : planification d’actualisation</span><span class="sxs-lookup"><span data-stu-id="08d9b-123">:heavy_check_mark: Refresh schedule</span></span><br></br> | :heavy_check_mark: <span data-ttu-id="08d9b-124">Nom</span><span class="sxs-lookup"><span data-stu-id="08d9b-124">Name</span></span><br></br> <span data-ttu-id="08d9b-125">:heavy_check_mark : Description</span><span class="sxs-lookup"><span data-stu-id="08d9b-125">:heavy_check_mark: Description</span></span>
<span data-ttu-id="08d9b-126">Modifier un brouillon de connexion</span><span class="sxs-lookup"><span data-stu-id="08d9b-126">Edit a draft connection</span></span> | :heavy_check_mark: | :x:

## <a name="monitor-your-connection-state"></a><span data-ttu-id="08d9b-129">Surveiller l’état de votre connexion</span><span class="sxs-lookup"><span data-stu-id="08d9b-129">Monitor your connection state</span></span>

<span data-ttu-id="08d9b-130">Après avoir créé une connexion, le nombre d’éléments **traitées** s’affiche sous l’onglet Connecteurs de la page **Recherche Microsoft.**</span><span class="sxs-lookup"><span data-stu-id="08d9b-130">After you create a connection, the number of processed items shows on the **Connectors** tab on the **Microsoft Search** page.</span></span> <span data-ttu-id="08d9b-131">Une fois l’analyse complète initiale terminée, la progression des analyses incrémentielles périodiques s’affiche.</span><span class="sxs-lookup"><span data-stu-id="08d9b-131">After the initial full crawl completes successfully, the progress for periodic incremental crawls displays.</span></span> <span data-ttu-id="08d9b-132">Cette page fournit des informations sur les opérations quotidiennes du connecteur et une vue d’ensemble des journaux et de l’historique des erreurs.</span><span class="sxs-lookup"><span data-stu-id="08d9b-132">This page provides information about the connector's day-to-day operations and an overview of the logs and error history.</span></span>

<span data-ttu-id="08d9b-133">Cinq états s’affiche dans la colonne **État** par rapport à chaque connexion :</span><span class="sxs-lookup"><span data-stu-id="08d9b-133">Five states show up in the **State** column against each connection:</span></span>

* <span data-ttu-id="08d9b-134">**Synchronisation.**</span><span class="sxs-lookup"><span data-stu-id="08d9b-134">**Syncing**.</span></span> <span data-ttu-id="08d9b-135">Le connecteur analyse les données de la source pour indexer les éléments existants et effectuer des mises à jour.</span><span class="sxs-lookup"><span data-stu-id="08d9b-135">The connector is crawling the data from the source to index the existing items and make any updates.</span></span>

* <span data-ttu-id="08d9b-136">**Prêt**: la connexion est prête et aucune analyse active n’est en cours d’exécution.</span><span class="sxs-lookup"><span data-stu-id="08d9b-136">**Ready**: The connection is ready, and there's no active crawl running against it.</span></span> <span data-ttu-id="08d9b-137">**L’heure de la** dernière synchronisation indique à quel moment la dernière analyse réussie s’est produite.</span><span class="sxs-lookup"><span data-stu-id="08d9b-137">**Last sync time** indicates when the last successful crawl happened.</span></span> <span data-ttu-id="08d9b-138">La connexion est aussi nouvelle que l’heure de la dernière synchronisation.</span><span class="sxs-lookup"><span data-stu-id="08d9b-138">The connection is as fresh as the last sync time.</span></span>

* <span data-ttu-id="08d9b-139">**Suspendu**.</span><span class="sxs-lookup"><span data-stu-id="08d9b-139">**Paused**.</span></span> <span data-ttu-id="08d9b-140">Les analyses sont suspendues par les administrateurs via l’option de pause.</span><span class="sxs-lookup"><span data-stu-id="08d9b-140">The crawls are paused by the admins through the pause option.</span></span> <span data-ttu-id="08d9b-141">L’analyse suivante s’exécute uniquement lorsqu’elle est reprise manuellement.</span><span class="sxs-lookup"><span data-stu-id="08d9b-141">The next crawl runs only when it's manually resumed.</span></span> <span data-ttu-id="08d9b-142">Toutefois, les données de cette connexion sont toujours utilisables dans une recherche.</span><span class="sxs-lookup"><span data-stu-id="08d9b-142">However, the data from this connection continues to be searchable.</span></span>

* <span data-ttu-id="08d9b-143">**Échec**.</span><span class="sxs-lookup"><span data-stu-id="08d9b-143">**Failed**.</span></span> <span data-ttu-id="08d9b-144">La connexion a connu une défaillance critique.</span><span class="sxs-lookup"><span data-stu-id="08d9b-144">The connection had a critical failure.</span></span> <span data-ttu-id="08d9b-145">Cette erreur nécessite une intervention manuelle.</span><span class="sxs-lookup"><span data-stu-id="08d9b-145">This error requires manual intervention.</span></span> <span data-ttu-id="08d9b-146">L’administrateur doit prendre les mesures appropriées en fonction du message d’erreur affiché.</span><span class="sxs-lookup"><span data-stu-id="08d9b-146">The admin needs to take appropriate action based on the error message shown.</span></span> <span data-ttu-id="08d9b-147">Les données qui ont été indexées jusqu’à ce que l’erreur se soit produite sont utilisables dans une recherche.</span><span class="sxs-lookup"><span data-stu-id="08d9b-147">Data that was indexed until the error occurred is searchable.</span></span>

* <span data-ttu-id="08d9b-148">**Suppression échouée.**</span><span class="sxs-lookup"><span data-stu-id="08d9b-148">**Delete Failed**.</span></span> <span data-ttu-id="08d9b-149">La suppression de la connexion a échoué.</span><span class="sxs-lookup"><span data-stu-id="08d9b-149">The deletion of connection failed.</span></span> <span data-ttu-id="08d9b-150">Selon la raison de l’échec, les données peuvent toujours être indexées, le quota d’élément peut toujours être consommé et les analyses peuvent encore s’exécuter pour la connexion.</span><span class="sxs-lookup"><span data-stu-id="08d9b-150">Depending upon the failure reason, the data might still be indexed, item quota may still be consumed and crawls might still run for the connection.</span></span> <span data-ttu-id="08d9b-151">Il est recommandé d’essayer de supprimer à nouveau la connexion dans cet état.</span><span class="sxs-lookup"><span data-stu-id="08d9b-151">It is recommended to try deleting the connection again in this state.</span></span>

## <a name="monitor-your-index-quota-utilization"></a><span data-ttu-id="08d9b-152">Surveiller l’utilisation de votre quota d’index</span><span class="sxs-lookup"><span data-stu-id="08d9b-152">Monitor your index quota utilization</span></span>

<span data-ttu-id="08d9b-153">Le quota d’index et la consommation disponibles sont affichés sur la page d’accueil des connecteurs.</span><span class="sxs-lookup"><span data-stu-id="08d9b-153">The available index quota and consumption is displayed on the connectors landing page.</span></span>

![Barre d’utilisation du quota d’index](media/quota_utilization.png)
 
>[!NOTE]
><span data-ttu-id="08d9b-155">Pendant la période d’aperçu, chaque organisation qui essaie des connecteurs Graph a été fournie avec un quota fixe gratuit de 2 millions d’éléments sur toutes les connexions.</span><span class="sxs-lookup"><span data-stu-id="08d9b-155">During the preview period, every organization trying out Graph connectors was provided a free fixed quota of up to 2 million items across all connections.</span></span> <span data-ttu-id="08d9b-156">Les connecteurs Graph étant généralement disponibles, le quota gratuit expirera le 1er avril 2021 pour les organisations qui ont utilisé des connecteurs Graph en prévisualisation.</span><span class="sxs-lookup"><span data-stu-id="08d9b-156">With Graph connectors being generally available, the free quota will expire on April 1st, 2021 for those organizations who have been using Graph connectors in preview.</span></span>
><span data-ttu-id="08d9b-157">Les connecteurs Graph créés par Microsoft et étiquetés comme « [Aperçu](./connectors-overview.md) » ne seront pas inclus dans le quota d’index facturé total pour votre organisation.</span><span class="sxs-lookup"><span data-stu-id="08d9b-157">Microsoft-built Graph connectors labeled as ["Preview"](./connectors-overview.md) will not be included in the total charged index quota for your organization.</span></span> <span data-ttu-id="08d9b-158">Toutefois, il est comptabilisé dans le nombre maximum de 10 connexions que vous pouvez configurer pour votre organisation et le nombre maximum de 7 millions d’éléments que votre organisation peut indexer entre les connexions ; Chaque connexion est limitée à 700 000 éléments.</span><span class="sxs-lookup"><span data-stu-id="08d9b-158">However, it will count towards the max number of 10 connections you can configure for your organization and the max number of 7 million items your organization can index across connections; each connection is limited 700,000 items.</span></span> 

<span data-ttu-id="08d9b-159">La barre d’utilisation des quotas indiquera différents états en fonction de la consommation de quota par votre organisation :</span><span class="sxs-lookup"><span data-stu-id="08d9b-159">The quota utilization bar will indicate various states based on consumption of quota by your organization:</span></span>

<span data-ttu-id="08d9b-160">État</span><span class="sxs-lookup"><span data-stu-id="08d9b-160">State</span></span> | <span data-ttu-id="08d9b-161">Niveaux d’utilisation des quotas</span><span class="sxs-lookup"><span data-stu-id="08d9b-161">Quota utilization levels</span></span>
--- | --- 
<span data-ttu-id="08d9b-162">Normal</span><span class="sxs-lookup"><span data-stu-id="08d9b-162">Normal</span></span> | <span data-ttu-id="08d9b-163">0-79%</span><span class="sxs-lookup"><span data-stu-id="08d9b-163">0-79%</span></span>
<span data-ttu-id="08d9b-164">Élevé</span><span class="sxs-lookup"><span data-stu-id="08d9b-164">High</span></span> | <span data-ttu-id="08d9b-165">80-89%</span><span class="sxs-lookup"><span data-stu-id="08d9b-165">80-89%</span></span>
<span data-ttu-id="08d9b-166">Critique</span><span class="sxs-lookup"><span data-stu-id="08d9b-166">Critical</span></span> | <span data-ttu-id="08d9b-167">90%-99%</span><span class="sxs-lookup"><span data-stu-id="08d9b-167">90%-99%</span></span>
<span data-ttu-id="08d9b-168">Complet</span><span class="sxs-lookup"><span data-stu-id="08d9b-168">Full</span></span> | <span data-ttu-id="08d9b-169">100 %</span><span class="sxs-lookup"><span data-stu-id="08d9b-169">100%</span></span>

<!-- 
![Quota utilization levels](media/connectors-quota-utilization-levels.png)
-->

<span data-ttu-id="08d9b-170">Le nombre d’éléments indexés s’affiche également avec chaque connexion.</span><span class="sxs-lookup"><span data-stu-id="08d9b-170">The number of items indexed will also be displayed with each connection.</span></span> <span data-ttu-id="08d9b-171">Le nombre d’éléments indexés par chaque connexion contribue au quota total disponible pour votre organisation.</span><span class="sxs-lookup"><span data-stu-id="08d9b-171">The number of items indexed by each connection contributes to the total quota available for your organization.</span></span>

<span data-ttu-id="08d9b-172">Lorsque le quota d’index est dépassé pour votre organisation, toutes les connexions actives sont touchées et ces connexions fonctionnent dans un état **dépassé** limite.</span><span class="sxs-lookup"><span data-stu-id="08d9b-172">When index quota is exceeded for your organization, all active connections will be impacted, and those connections will operate in **limit exceeded** state.</span></span> <span data-ttu-id="08d9b-173">Dans cet état, vos connexions actives</span><span class="sxs-lookup"><span data-stu-id="08d9b-173">In this state, your active connections</span></span>  

* <span data-ttu-id="08d9b-174">Ne sera pas en mesure d’ajouter de nouveaux éléments.</span><span class="sxs-lookup"><span data-stu-id="08d9b-174">Will not be able to add new items.</span></span>

* <span data-ttu-id="08d9b-175">Sera en mesure de mettre à jour ou de supprimer des éléments existants.</span><span class="sxs-lookup"><span data-stu-id="08d9b-175">Will be able to update or delete existing items.</span></span>

<span data-ttu-id="08d9b-176">Pour résoudre ce problème, vous pouvez :</span><span class="sxs-lookup"><span data-stu-id="08d9b-176">To fix this, you can do any of the following:</span></span>

* <span data-ttu-id="08d9b-177">Découvrez comment acheter un quota d’index pour votre organisation en matière de [licences et de tarification.](licensing.md)</span><span class="sxs-lookup"><span data-stu-id="08d9b-177">Learn how to purchase index quota for your organization at [Licensing requirements and pricing](licensing.md).</span></span>

* <span data-ttu-id="08d9b-178">Identifiez les connexions qui ont trop de contenu en cours d’ingestion et mettez-les à jour pour indexer moins d’éléments afin de faire de la place pour le quota.</span><span class="sxs-lookup"><span data-stu-id="08d9b-178">Identify connections which have too much content being ingested and update them to index fewer items to make room for quota.</span></span> <span data-ttu-id="08d9b-179">Pour mettre à jour la connexion, vous devez supprimer et créer une connexion avec un nouveau filtre d’ingestion qui apporte moins d’éléments.</span><span class="sxs-lookup"><span data-stu-id="08d9b-179">To update the connection, you must delete and create a new connection with a new ingestion filter which brings in fewer items.</span></span>

* <span data-ttu-id="08d9b-180">Supprimer définitivement une ou plusieurs connexions</span><span class="sxs-lookup"><span data-stu-id="08d9b-180">Permanently delete one or more connections</span></span>