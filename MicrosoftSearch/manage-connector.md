---
title: Gérer les connecteurs Microsoft Graph pour Microsoft Search (recherche Microsoft)
ms.author: monaray
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
ms.openlocfilehash: 1c152f23e9b9d9982b957830d5f4bef0eef41347
ms.sourcegitcommit: 2f770de12b27546b18b2e86517d2c25522eb9022
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50929583"
---
<!-- markdownlint-disable no-inline-html -->

# <a name="monitor-your-connections"></a><span data-ttu-id="1b084-103">Surveiller vos connexions</span><span class="sxs-lookup"><span data-stu-id="1b084-103">Monitor your connections</span></span>

<span data-ttu-id="1b084-104">Pour accéder à vos connecteurs et les gérer, vous devez être désigné en tant qu’administrateur de recherche pour votre client.</span><span class="sxs-lookup"><span data-stu-id="1b084-104">To access and manage your connectors, you must be designated as a search administrator for your tenant.</span></span> <span data-ttu-id="1b084-105">Contactez votre administrateur client pour vous fournir le rôle d’administrateur de recherche.</span><span class="sxs-lookup"><span data-stu-id="1b084-105">Contact your tenant administrator to provision you for the search administrator role.</span></span>

## <a name="connection-operations"></a><span data-ttu-id="1b084-106">Opérations de connexion</span><span class="sxs-lookup"><span data-stu-id="1b084-106">Connection Operations</span></span>

<span data-ttu-id="1b084-107">Accédez à [l’onglet Connecteurs](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/Connectors) dans le [Centre d’administration Microsoft 365.](https://admin.microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="1b084-107">Navigate to the [Connectors tab](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/Connectors) in the [Microsoft 365 admin center](https://admin.microsoft.com).</span></span>

<span data-ttu-id="1b084-108">Pour chaque type de connecteur, le Centre [d’administration Microsoft 365](https://admin.microsoft.com) prend en charge les opérations indiquées dans le tableau suivant :</span><span class="sxs-lookup"><span data-stu-id="1b084-108">For each connector type, the [Microsoft 365 admin center](https://admin.microsoft.com) supports the operations shown in the following table:</span></span>

<span data-ttu-id="1b084-109">Opération</span><span class="sxs-lookup"><span data-stu-id="1b084-109">Operation</span></span> | <span data-ttu-id="1b084-110">Connecteurs Graph par Microsoft</span><span class="sxs-lookup"><span data-stu-id="1b084-110">Graph connectors by Microsoft</span></span> | <span data-ttu-id="1b084-111">Connecteurs partenaires ou Graph</span><span class="sxs-lookup"><span data-stu-id="1b084-111">Partner or Graph connectors</span></span>
--- | --- | ---
<span data-ttu-id="1b084-112">Ajouter une connexion</span><span class="sxs-lookup"><span data-stu-id="1b084-112">Add a connection</span></span> | <span data-ttu-id="1b084-113">:heavy_check_mark : (voir [vue d’ensemble du programme d’installation)](configure-connector.md)</span><span class="sxs-lookup"><span data-stu-id="1b084-113">:heavy_check_mark: (See [Setup overview](configure-connector.md))</span></span> | <span data-ttu-id="1b084-114">:x : (faire référence à l’UX de votre partenaire ou de votre connecteur personnalisé)</span><span class="sxs-lookup"><span data-stu-id="1b084-114">:x: (Refer to your partner or custom-built connector admin UX)</span></span>
<span data-ttu-id="1b084-115">Supprimer une connexion</span><span class="sxs-lookup"><span data-stu-id="1b084-115">Delete a connection</span></span> | :heavy_check_mark: | :heavy_check_mark:
<span data-ttu-id="1b084-118">Modifier une connexion publiée</span><span class="sxs-lookup"><span data-stu-id="1b084-118">Edit a published connection</span></span> | <span data-ttu-id="1b084-119">:heavy_check_mark : nom et description</span><span class="sxs-lookup"><span data-stu-id="1b084-119">:heavy_check_mark: Name and Description</span></span><br></br> <span data-ttu-id="1b084-120">:heavy_check_mark : paramètres de connexion</span><span class="sxs-lookup"><span data-stu-id="1b084-120">:heavy_check_mark: Connection settings</span></span><br></br> <span data-ttu-id="1b084-121">:heavy_check_mark : étiquettes de propriété</span><span class="sxs-lookup"><span data-stu-id="1b084-121">:heavy_check_mark: Property labels</span></span><br></br> <span data-ttu-id="1b084-122">:heavy_check_mark : schéma</span><span class="sxs-lookup"><span data-stu-id="1b084-122">:heavy_check_mark: Schema</span></span><br></br> <span data-ttu-id="1b084-123">:heavy_check_mark : planification d’actualisation</span><span class="sxs-lookup"><span data-stu-id="1b084-123">:heavy_check_mark: Refresh schedule</span></span><br></br> | :heavy_check_mark: <span data-ttu-id="1b084-124">Nom</span><span class="sxs-lookup"><span data-stu-id="1b084-124">Name</span></span><br></br> <span data-ttu-id="1b084-125">:heavy_check_mark : Description</span><span class="sxs-lookup"><span data-stu-id="1b084-125">:heavy_check_mark: Description</span></span>
<span data-ttu-id="1b084-126">Modifier un brouillon de connexion</span><span class="sxs-lookup"><span data-stu-id="1b084-126">Edit a draft connection</span></span> | :heavy_check_mark: | :x:

## <a name="monitor-your-connection-state"></a><span data-ttu-id="1b084-129">Surveiller l’état de votre connexion</span><span class="sxs-lookup"><span data-stu-id="1b084-129">Monitor your connection state</span></span>

<span data-ttu-id="1b084-130">Après avoir créé une connexion, le nombre d’éléments **traitées** s’affiche sous l’onglet Connecteurs de la page **Recherche Microsoft.**</span><span class="sxs-lookup"><span data-stu-id="1b084-130">After you create a connection, the number of processed items shows on the **Connectors** tab on the **Microsoft Search** page.</span></span> <span data-ttu-id="1b084-131">Une fois l’analyse complète initiale terminée, la progression des analyses incrémentielles périodiques s’affiche.</span><span class="sxs-lookup"><span data-stu-id="1b084-131">After the initial full crawl completes successfully, the progress for periodic incremental crawls displays.</span></span> <span data-ttu-id="1b084-132">Cette page fournit des informations sur les opérations quotidiennes du connecteur et une vue d’ensemble des journaux et de l’historique des erreurs.</span><span class="sxs-lookup"><span data-stu-id="1b084-132">This page provides information about the connector's day-to-day operations and an overview of the logs and error history.</span></span>

<span data-ttu-id="1b084-133">Quatre états s’affiche dans la colonne **État** par rapport à chaque connexion :</span><span class="sxs-lookup"><span data-stu-id="1b084-133">Four states show up in the **State** column against each connection:</span></span>

* <span data-ttu-id="1b084-134">**Synchronisation.**</span><span class="sxs-lookup"><span data-stu-id="1b084-134">**Syncing**.</span></span> <span data-ttu-id="1b084-135">Le connecteur analyse les données de la source pour indexer les éléments existants et effectuer des mises à jour.</span><span class="sxs-lookup"><span data-stu-id="1b084-135">The connector is crawling the data from the source to index the existing items and make any updates.</span></span>

* <span data-ttu-id="1b084-136">**Prêt**: la connexion est prête et aucune analyse active n’est en cours d’exécution.</span><span class="sxs-lookup"><span data-stu-id="1b084-136">**Ready**: The connection is ready, and there's no active crawl running against it.</span></span> <span data-ttu-id="1b084-137">**L’heure de la** dernière synchronisation indique à quel moment la dernière analyse réussie s’est produite.</span><span class="sxs-lookup"><span data-stu-id="1b084-137">**Last sync time** indicates when the last successful crawl happened.</span></span> <span data-ttu-id="1b084-138">La connexion est aussi nouvelle que l’heure de la dernière synchronisation.</span><span class="sxs-lookup"><span data-stu-id="1b084-138">The connection is as fresh as the last sync time.</span></span>

* <span data-ttu-id="1b084-139">**Suspendu**.</span><span class="sxs-lookup"><span data-stu-id="1b084-139">**Paused**.</span></span> <span data-ttu-id="1b084-140">Les analyses sont suspendues par les administrateurs via l’option de pause.</span><span class="sxs-lookup"><span data-stu-id="1b084-140">The crawls are paused by the admins through the pause option.</span></span> <span data-ttu-id="1b084-141">L’analyse suivante s’exécute uniquement lorsqu’elle est reprise manuellement.</span><span class="sxs-lookup"><span data-stu-id="1b084-141">The next crawl runs only when it's manually resumed.</span></span> <span data-ttu-id="1b084-142">Toutefois, les données de cette connexion sont toujours utilisables dans une recherche.</span><span class="sxs-lookup"><span data-stu-id="1b084-142">However, the data from this connection continues to be searchable.</span></span>

* <span data-ttu-id="1b084-143">**Échec**.</span><span class="sxs-lookup"><span data-stu-id="1b084-143">**Failed**.</span></span> <span data-ttu-id="1b084-144">La connexion a connu une défaillance critique.</span><span class="sxs-lookup"><span data-stu-id="1b084-144">The connection had a critical failure.</span></span> <span data-ttu-id="1b084-145">Cette erreur nécessite une intervention manuelle.</span><span class="sxs-lookup"><span data-stu-id="1b084-145">This error requires manual intervention.</span></span> <span data-ttu-id="1b084-146">L’administrateur doit prendre les mesures appropriées en fonction du message d’erreur affiché.</span><span class="sxs-lookup"><span data-stu-id="1b084-146">The admin needs to take appropriate action based on the error message shown.</span></span> <span data-ttu-id="1b084-147">Les données qui ont été indexées jusqu’à ce que l’erreur se soit produite sont utilisables dans une recherche.</span><span class="sxs-lookup"><span data-stu-id="1b084-147">Data that was indexed until the error occurred is searchable.</span></span>

## <a name="monitor-your-index-quota-utilization"></a><span data-ttu-id="1b084-148">Surveiller l’utilisation de votre quota d’index</span><span class="sxs-lookup"><span data-stu-id="1b084-148">Monitor your index quota utilization</span></span>

<span data-ttu-id="1b084-149">Le quota d’index et la consommation disponibles sont affichés sur la page d’accueil des connecteurs.</span><span class="sxs-lookup"><span data-stu-id="1b084-149">The available index quota and consumption is displayed on the connectors landing page.</span></span>

![Barre d’utilisation du quota d’index](media/quota_utilization.png)
 
>[!NOTE]
><span data-ttu-id="1b084-151">Pendant la période d’aperçu, chaque organisation qui essaie des connecteurs Graph a été fournie avec un quota fixe gratuit de 2 millions d’éléments sur toutes les connexions.</span><span class="sxs-lookup"><span data-stu-id="1b084-151">During the preview period, every organization trying out Graph connectors was provided a free fixed quota of up to 2 million items across all connections.</span></span> <span data-ttu-id="1b084-152">Les connecteurs Graph étant généralement disponibles, le quota gratuit expirera le 1er avril 2021 pour les organisations qui ont utilisé des connecteurs Graph en prévisualisation.</span><span class="sxs-lookup"><span data-stu-id="1b084-152">With Graph connectors being generally available, the free quota will expire on April 1st, 2021 for those organizations who have been using Graph connectors in preview.</span></span>
><span data-ttu-id="1b084-153">Les connecteurs Graph créés par Microsoft et étiquetés comme « [Aperçu](connectors-preview.md) » ne seront pas inclus dans le quota d’index facturé total pour votre organisation.</span><span class="sxs-lookup"><span data-stu-id="1b084-153">Microsoft-built Graph connectors labeled as ["Preview"](connectors-preview.md) will not be included in the total charged index quota for your organization.</span></span> <span data-ttu-id="1b084-154">Toutefois, il est comptabilisé dans le nombre maximum de 10 connexions que vous pouvez configurer pour votre organisation et le nombre maximum de 7 millions d’éléments que votre organisation peut indexer entre les connexions ; Chaque connexion est limitée à 700 000 éléments.</span><span class="sxs-lookup"><span data-stu-id="1b084-154">However, it will count towards the max number of 10 connections you can configure for your organization and the max number of 7 million items your organization can index across connections; each connection is limited 700,000 items.</span></span> 

<span data-ttu-id="1b084-155">La barre d’utilisation des quotas indiquera différents états en fonction de la consommation de quota par votre organisation :</span><span class="sxs-lookup"><span data-stu-id="1b084-155">The quota utilization bar will indicate various states based on consumption of quota by your organization:</span></span>

<span data-ttu-id="1b084-156">État</span><span class="sxs-lookup"><span data-stu-id="1b084-156">State</span></span> | <span data-ttu-id="1b084-157">Niveaux d’utilisation des quotas</span><span class="sxs-lookup"><span data-stu-id="1b084-157">Quota utilization levels</span></span>
--- | --- 
<span data-ttu-id="1b084-158">Normal</span><span class="sxs-lookup"><span data-stu-id="1b084-158">Normal</span></span> | <span data-ttu-id="1b084-159">0-79%</span><span class="sxs-lookup"><span data-stu-id="1b084-159">0-79%</span></span>
<span data-ttu-id="1b084-160">Élevé</span><span class="sxs-lookup"><span data-stu-id="1b084-160">High</span></span> | <span data-ttu-id="1b084-161">80-89%</span><span class="sxs-lookup"><span data-stu-id="1b084-161">80-89%</span></span>
<span data-ttu-id="1b084-162">Critique</span><span class="sxs-lookup"><span data-stu-id="1b084-162">Critical</span></span> | <span data-ttu-id="1b084-163">90%-99%</span><span class="sxs-lookup"><span data-stu-id="1b084-163">90%-99%</span></span>
<span data-ttu-id="1b084-164">Complet</span><span class="sxs-lookup"><span data-stu-id="1b084-164">Full</span></span> | <span data-ttu-id="1b084-165">100 %</span><span class="sxs-lookup"><span data-stu-id="1b084-165">100%</span></span>

<!-- 
![Quota utilization levels](media/connectors-quota-utilization-levels.png)
-->

<span data-ttu-id="1b084-166">Le nombre d’éléments indexés s’affiche également avec chaque connexion.</span><span class="sxs-lookup"><span data-stu-id="1b084-166">The number of items indexed will also be displayed with each connection.</span></span> <span data-ttu-id="1b084-167">Le nombre d’éléments indexés par chaque connexion contribue au quota total disponible pour votre organisation.</span><span class="sxs-lookup"><span data-stu-id="1b084-167">The number of items indexed by each connection contributes to the total quota available for your organization.</span></span>

<span data-ttu-id="1b084-168">Lorsque le quota d’index est dépassé pour votre organisation, toutes les connexions actives sont touchées et ces connexions fonctionnent dans un état **dépassé** limite.</span><span class="sxs-lookup"><span data-stu-id="1b084-168">When index quota is exceeded for your organization, all active connections will be impacted, and those connections will operate in **limit exceeded** state.</span></span> <span data-ttu-id="1b084-169">Dans cet état, vos connexions actives</span><span class="sxs-lookup"><span data-stu-id="1b084-169">In this state, your active connections</span></span>  

* <span data-ttu-id="1b084-170">Ne sera pas en mesure d’ajouter de nouveaux éléments.</span><span class="sxs-lookup"><span data-stu-id="1b084-170">Will not be able to add new items.</span></span>

* <span data-ttu-id="1b084-171">Sera en mesure de mettre à jour ou de supprimer des éléments existants.</span><span class="sxs-lookup"><span data-stu-id="1b084-171">Will be able to update or delete existing items.</span></span>

<span data-ttu-id="1b084-172">Pour résoudre ce problème, vous pouvez :</span><span class="sxs-lookup"><span data-stu-id="1b084-172">To fix this, you can do any of the following:</span></span>

* <span data-ttu-id="1b084-173">Découvrez comment acheter un quota d’index pour votre organisation selon les exigences de licence [et la tarification.](licensing.md)</span><span class="sxs-lookup"><span data-stu-id="1b084-173">Learn how to purchase index quota for your organization at [Licensing requirements and pricing](licensing.md).</span></span>

* <span data-ttu-id="1b084-174">Identifiez les connexions qui ont trop de contenu en cours d’ingestion et mettez-les à jour pour indexer moins d’éléments afin de faire de la place pour le quota.</span><span class="sxs-lookup"><span data-stu-id="1b084-174">Identify connections which have too much content being ingested and update them to index fewer items to make room for quota.</span></span> <span data-ttu-id="1b084-175">Pour mettre à jour la connexion, vous devez supprimer et créer une connexion avec un nouveau filtre d’ingestion qui apporte moins d’éléments.</span><span class="sxs-lookup"><span data-stu-id="1b084-175">To update the connection, you must delete and create a new connection with a new ingestion filter which brings in fewer items.</span></span>

* <span data-ttu-id="1b084-176">Supprimer définitivement une ou plusieurs connexions</span><span class="sxs-lookup"><span data-stu-id="1b084-176">Permanently delete one or more connections</span></span>
