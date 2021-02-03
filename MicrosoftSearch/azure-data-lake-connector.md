---
title: Connecteur Azure Data Lake Graph pour Microsoft Search (recherche Microsoft)
ms.author: mecampos
author: mecampos
manager: umas
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: Configurer le connecteur Graph Azure Data Lake Storage Gen2 pour Microsoft Search (recherche Microsoft)
ms.openlocfilehash: da508694929d3c83a456c664aa4613b09a1b14a3
ms.sourcegitcommit: d39113376db26333872d3a2c7baddc3a3a7aea61
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/03/2021
ms.locfileid: "50084856"
---
<!---Previous ms.author: monaray --->

# <a name="azure-data-lake-storage-gen2-graph-connector"></a><span data-ttu-id="027b8-103">Connecteur Graph Azure Data Lake Storage Gen2</span><span class="sxs-lookup"><span data-stu-id="027b8-103">Azure Data Lake Storage Gen2 Graph connector</span></span>

<span data-ttu-id="027b8-104">Le connecteur Graph Azure Data Lake Storage Gen2 permet aux utilisateurs de votre organisation de rechercher des fichiers stockés dans des comptes de stockage [d’objets blob Azure](https://docs.microsoft.com/azure/storage/blobs/storage-blobs-introduction) et [Azure Data Lake Gen 2 Storage.](https://docs.microsoft.com/azure/storage/blobs/data-lake-storage-introduction)</span><span class="sxs-lookup"><span data-stu-id="027b8-104">The Azure Data Lake Storage Gen2 Graph connector allows users in your organization to search for files stored in [Azure Blob Storage](https://docs.microsoft.com/azure/storage/blobs/storage-blobs-introduction) and [Azure Data Lake Gen 2 Storage](https://docs.microsoft.com/azure/storage/blobs/data-lake-storage-introduction) accounts.</span></span>

> [!NOTE]
> <span data-ttu-id="027b8-105">Lisez [**l’article Configurer votre connecteur Graph**](configure-connector.md) pour comprendre le processus d’installation général des connecteurs Graph.</span><span class="sxs-lookup"><span data-stu-id="027b8-105">Read the [**Setup your Graph connector**](configure-connector.md) article to understand the general Graph connectors setup process.</span></span>

<span data-ttu-id="027b8-106">Cet article est réservé à toute personne qui configure, exécute et surveille un connecteur Azure Data Lake Storage Gen2.</span><span class="sxs-lookup"><span data-stu-id="027b8-106">This article is for anyone who configures, runs, and monitors an Azure Data Lake Storage Gen2 connector.</span></span> <span data-ttu-id="027b8-107">Il complète le processus de configuration général et affiche des instructions qui s’appliquent uniquement au connecteur Azure Data Lake Storage Gen2.</span><span class="sxs-lookup"><span data-stu-id="027b8-107">It supplements the general setup process, and shows instructions that apply only for the Azure Data Lake Storage Gen2 connector.</span></span> <span data-ttu-id="027b8-108">Cet article inclut également des informations sur [les limitations.](#limitations)</span><span class="sxs-lookup"><span data-stu-id="027b8-108">This article also includes information about [Limitations](#limitations).</span></span>

<span data-ttu-id="027b8-109">Dans l’article, nous utilisons Le stockage *Azure* comme terme générique pour le stockage [d’objets blob Azure](https://docs.microsoft.com/azure/storage/blobs/storage-blobs-introduction) et le stockage Azure Data Lake Gen [2.](https://docs.microsoft.com/azure/storage/blobs/data-lake-storage-introduction)</span><span class="sxs-lookup"><span data-stu-id="027b8-109">In the article, we use *Azure Storage* as a generic term for [Azure Blob Storage](https://docs.microsoft.com/azure/storage/blobs/storage-blobs-introduction) and [Azure Data Lake Gen 2 Storage](https://docs.microsoft.com/azure/storage/blobs/data-lake-storage-introduction).</span></span>

## <a name="step-1-add-a-graph-connector-in-the-microsoft-365-admin-center"></a><span data-ttu-id="027b8-110">Étape 1 : Ajouter un connecteur Graph dans le Centre d’administration Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="027b8-110">Step 1: Add a Graph connector in the Microsoft 365 admin center</span></span>

<span data-ttu-id="027b8-111">Suivez les [instructions d’installation générales.](https://docs.microsoft.com/microsoftsearch/configure-connector)</span><span class="sxs-lookup"><span data-stu-id="027b8-111">Follow the general [setup instructions](https://docs.microsoft.com/microsoftsearch/configure-connector).</span></span>
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-2-name-the-connection"></a><span data-ttu-id="027b8-112">Étape 2 : Nommer la connexion</span><span class="sxs-lookup"><span data-stu-id="027b8-112">Step 2: Name the connection</span></span>

<span data-ttu-id="027b8-113">Suivez les [instructions d’installation générales.](https://docs.microsoft.com/microsoftsearch/configure-connector)</span><span class="sxs-lookup"><span data-stu-id="027b8-113">Follow the general [setup instructions](https://docs.microsoft.com/microsoftsearch/configure-connector).</span></span>
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-3-configure-the-connection-settings"></a><span data-ttu-id="027b8-114">Étape 3 : Configurer les paramètres de connexion</span><span class="sxs-lookup"><span data-stu-id="027b8-114">Step 3: Configure the connection settings</span></span>

<span data-ttu-id="027b8-115">Entrez votre chaîne de connexion de stockage principale.</span><span class="sxs-lookup"><span data-stu-id="027b8-115">Enter your Primary storage connection String.</span></span> <span data-ttu-id="027b8-116">Cette chaîne est nécessaire pour autoriser l’accès à votre compte de stockage.</span><span class="sxs-lookup"><span data-stu-id="027b8-116">This string is required to allow access to your storage account.</span></span> <span data-ttu-id="027b8-117">Pour rechercher votre chaîne de connexion, accédez au portail [Azure](https://ms.portal.azure.com/#home) et accédez à la section **Clés** de votre compte de stockage Azure approprié.</span><span class="sxs-lookup"><span data-stu-id="027b8-117">To find your connection string, go to the [Azure portal](https://ms.portal.azure.com/#home) and navigate to the **Keys** section of your relevant Azure Storage account.</span></span>

<span data-ttu-id="027b8-118">Si vous préférez ne pas fournir **la clé AccountKey** (paramètre dans la chaîne de connexion de stockage principale), accordez l’accès à notre service Graph Connectors pour les rôles suivants :</span><span class="sxs-lookup"><span data-stu-id="027b8-118">If you prefer not to provide the **AccountKey** (a parameter in the primary storage connection string), grant access to our Graph Connectors Service for the following roles:</span></span>

* <span data-ttu-id="027b8-119">Lecteur de données blob de stockage</span><span class="sxs-lookup"><span data-stu-id="027b8-119">Storage Blob Data Reader</span></span>
* <span data-ttu-id="027b8-120">Collaborateur de données de file d’attente de stockage</span><span class="sxs-lookup"><span data-stu-id="027b8-120">Storage Queue Data Contributor</span></span>
* <span data-ttu-id="027b8-121">Délégant d’objets blob de stockage</span><span class="sxs-lookup"><span data-stu-id="027b8-121">Storage Blob Delegator</span></span>

<span data-ttu-id="027b8-122">Accédez à **l’onglet Contrôle** d’accès de votre compte de stockage Azure et suivez les instructions ci-après pour accorder l’accès à l’application suivante :</span><span class="sxs-lookup"><span data-stu-id="027b8-122">Navigate to the **Access Control** tab of your Azure Storage account, and follow the instructions there to grant access to the following app:</span></span>

* <span data-ttu-id="027b8-123">**ID** d’application first party : 56c1da01-2129-48f7-9355-af6d59d42766</span><span class="sxs-lookup"><span data-stu-id="027b8-123">**First Party App ID:** 56c1da01-2129-48f7-9355-af6d59d42766</span></span>
* <span data-ttu-id="027b8-124">**Nom de l’application de première partie :** Graph Connector Service</span><span class="sxs-lookup"><span data-stu-id="027b8-124">**First Party App Name:** Graph Connector Service</span></span>

### <a name="storage-account-and-queue-notifications-optional"></a><span data-ttu-id="027b8-125">Notifications de compte de stockage et de file d’attente (facultatif)</span><span class="sxs-lookup"><span data-stu-id="027b8-125">Storage account and queue notifications (Optional)</span></span>

<span data-ttu-id="027b8-126">La prise en charge du traitement des modifications en temps réel dans le service Graph Connectors peut être ajoutée à l’avenir.</span><span class="sxs-lookup"><span data-stu-id="027b8-126">Support to process changes in real time in the Graph Connectors Service might be added in the future.</span></span> <span data-ttu-id="027b8-127">Dans ce cas, nous allons surveiller les notifications de modification du stockage Azure stockées dans une file d’attente.</span><span class="sxs-lookup"><span data-stu-id="027b8-127">In that case, we'll monitor Azure Storage change notifications stored in a queue.</span></span> <span data-ttu-id="027b8-128">Vous devez créer une file d’attente dans le même compte que votre compte de stockage Azure.</span><span class="sxs-lookup"><span data-stu-id="027b8-128">You'll need to create a queue in the same account as your Azure Storage account.</span></span>

<span data-ttu-id="027b8-129">Après avoir créé une file d’attente, rendez-vous dans l’onglet **Événements** de la page de file d’attente pour configurer **l’abonnement aux événements.**</span><span class="sxs-lookup"><span data-stu-id="027b8-129">After you create a queue, go to the **Events** tab on the queue page to configure **Event Subscription**.</span></span> <span data-ttu-id="027b8-130">Choisissez tous les événements Blob que la file d’attente recevra et connectez-la au compte de stockage Azure.</span><span class="sxs-lookup"><span data-stu-id="027b8-130">Choose all the Blob events that the queue will receive, and connect the queue to the Azure Storage account.</span></span>

## <a name="step-4-assign-property-labels"></a><span data-ttu-id="027b8-131">Étape 4 : Attribuer des étiquettes de propriété</span><span class="sxs-lookup"><span data-stu-id="027b8-131">Step 4: Assign property labels</span></span>

<span data-ttu-id="027b8-132">Vous pouvez affecter une propriété source à chaque étiquette en choisissant dans un menu d’options.</span><span class="sxs-lookup"><span data-stu-id="027b8-132">You can assign a source property to each label by choosing from a menu of options.</span></span> <span data-ttu-id="027b8-133">Bien que cette étape ne soit pas obligatoire, le fait d’avoir des étiquettes de propriétés améliorera la pertinence de la recherche et garantira de meilleurs résultats de recherche pour les utilisateurs finaux.</span><span class="sxs-lookup"><span data-stu-id="027b8-133">While this step isn't mandatory, having some property labels will improve the search relevance and ensure better search results for end users.</span></span>

## <a name="step-5-manage-schema"></a><span data-ttu-id="027b8-134">Étape 5 : Gérer le schéma</span><span class="sxs-lookup"><span data-stu-id="027b8-134">Step 5: Manage schema</span></span>

<span data-ttu-id="027b8-135">Dans **l’écran** Gérer le schéma, vous pouvez modifier les attributs de schéma associés aux propriétés, les options sont **Requête,** **Rechercher,** Récupérer **et** **Affiner**.</span><span class="sxs-lookup"><span data-stu-id="027b8-135">On the **Manage Schema** screen, you can change the schema attributes associated with the properties, the options are **Query**, **Search**, **Retrieve**, and **Refine**.</span></span> <span data-ttu-id="027b8-136">Vous pouvez également ajouter des alias facultatifs et choisir la **propriété Content.**</span><span class="sxs-lookup"><span data-stu-id="027b8-136">You also can add optional aliases, and choose the **Content** property.</span></span>

## <a name="step-6-manage-search-permissions"></a><span data-ttu-id="027b8-137">Étape 6 : Gérer les autorisations de recherche</span><span class="sxs-lookup"><span data-stu-id="027b8-137">Step 6: Manage search permissions</span></span>

### <a name="azure-data-lake-gen-2"></a><span data-ttu-id="027b8-138">Azure Data Lake Gen 2</span><span class="sxs-lookup"><span data-stu-id="027b8-138">Azure Data Lake Gen 2</span></span>

<span data-ttu-id="027b8-139">Vous pouvez choisir d’ingèrer les listes de contrôle d’accès à partir de votre compte de stockage [Azure Data Lake Gen 2.](https://docs.microsoft.com/azure/storage/blobs/data-lake-storage-introduction)</span><span class="sxs-lookup"><span data-stu-id="027b8-139">You can choose to ingest the Access Control Lists (ACLs) from your [Azure Data Lake Gen 2 Storage](https://docs.microsoft.com/azure/storage/blobs/data-lake-storage-introduction) account.</span></span> <span data-ttu-id="027b8-140">Lorsque ces autorisations de recherche sont définies, le contenu de recherche est découpé en fonction des autorisations de l’utilisateur qui s’est inscrit [dans Azure Active Directory.](https://docs.microsoft.com/azure/active-directory/)</span><span class="sxs-lookup"><span data-stu-id="027b8-140">When these search permissions are set, search content is trimmed based on the permissions of the user signed in [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/).</span></span> <span data-ttu-id="027b8-141">Vous pouvez également choisir de rendre tout le contenu indexé à partir de votre compte de stockage visible par tous les membres de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="027b8-141">Alternatively, you can choose to make all the content indexed from your storage account visible to everyone in your organization.</span></span> <span data-ttu-id="027b8-142">Dans ce cas, tous les membres de votre organisation auront accès à toutes les données de votre compte de stockage.</span><span class="sxs-lookup"><span data-stu-id="027b8-142">In this case, everyone in your organization will have access to all the data in your storage account.</span></span>

<span data-ttu-id="027b8-143">Le connecteur Azure Data Lake Storage Gen2 Graph prend en charge les autorisations de recherche visibles par tout le monde **ou** uniquement les personnes ayant accès à cette source **de données.**</span><span class="sxs-lookup"><span data-stu-id="027b8-143">The Azure Data Lake Storage Gen2 Graph connector supports search permissions visible to **Everyone**, or **Only people with access to this data source**.</span></span> <span data-ttu-id="027b8-144">Les données indexées qui apparaissent dans les résultats de la recherche peuvent être visibles par les utilisateurs de l’organisation qui ont accès à chaque élément.</span><span class="sxs-lookup"><span data-stu-id="027b8-144">Indexed data that appears in the search results could be visible to users in the organization who have access to each item.</span></span>

### <a name="azure-blob-storage"></a><span data-ttu-id="027b8-145">Stockage Blob Azure</span><span class="sxs-lookup"><span data-stu-id="027b8-145">Azure Blob Storage</span></span>

<span data-ttu-id="027b8-146">Pour une connexion au [stockage Blob Azure,](https://docs.microsoft.com/azure/storage/blobs/storage-blobs-introduction)tout le contenu indexé à partir de la source configurée est visible par tous les membres de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="027b8-146">For a connection to [Azure Blob Storage](https://docs.microsoft.com/azure/storage/blobs/storage-blobs-introduction), all the content indexed from the configured source is visible to everyone in your organization.</span></span> <span data-ttu-id="027b8-147">Les listes de contrôle d’accès ne sont pas pris en charge au niveau blob dans le stockage d’objets blob Azure.</span><span class="sxs-lookup"><span data-stu-id="027b8-147">Access control lists aren't supported at Blob level in Azure Blob Storage.</span></span>

## <a name="step-7-set-the-refresh-schedule"></a><span data-ttu-id="027b8-148">Étape 7 : Définir la planification d’actualisation</span><span class="sxs-lookup"><span data-stu-id="027b8-148">Step 7: Set the refresh schedule</span></span>

<span data-ttu-id="027b8-149">Dans **l’écran Paramètres** d’actualisation, vous pouvez définir l’intervalle d’analyse incrémentielle et l’intervalle d’analyse complet.</span><span class="sxs-lookup"><span data-stu-id="027b8-149">On the **Refresh Settings** screen, you can set the incremental crawl interval and the full crawl interval.</span></span> <span data-ttu-id="027b8-150">Les intervalles par défaut pour le connecteur Azure Data Lake Storage Gen2 sont de 15 minutes pour une analyse incrémentielle et d’une semaine pour une analyse complète.</span><span class="sxs-lookup"><span data-stu-id="027b8-150">The default intervals for the Azure Data Lake Storage Gen2 connector are 15 minutes for an incremental crawl and one week for a full crawl.</span></span>

## <a name="step-8-review-connection"></a><span data-ttu-id="027b8-151">Étape 8 : Examiner la connexion</span><span class="sxs-lookup"><span data-stu-id="027b8-151">Step 8: Review connection</span></span>

<span data-ttu-id="027b8-152">Suivez les [instructions d’installation générales.](https://docs.microsoft.com/microsoftsearch/configure-connector)</span><span class="sxs-lookup"><span data-stu-id="027b8-152">Follow the general [setup instructions](https://docs.microsoft.com/microsoftsearch/configure-connector).</span></span>
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

<!---## Troubleshooting-->
<!---Insert troubleshooting recommendations for this data source-->

## <a name="limitations"></a><span data-ttu-id="027b8-153">Limites</span><span class="sxs-lookup"><span data-stu-id="027b8-153">Limitations</span></span>

<span data-ttu-id="027b8-154">Une connexion publiée pour le stockage d’objets blob Azure ne peut pas être reconfigurée pour la source Azure Data Lake Storage Gen2 et inversement.</span><span class="sxs-lookup"><span data-stu-id="027b8-154">A published connection for Azure Blob Storage cannot be reconfigured for Azure Data Lake Storage Gen2 source and the other way around.</span></span> <span data-ttu-id="027b8-155">Dans de tels scénarios, il est recommandé de configurer une nouvelle connexion.</span><span class="sxs-lookup"><span data-stu-id="027b8-155">In such scenarios, it's recommended to configure a new connection.</span></span>

<span data-ttu-id="027b8-156">En outre, la taille des fichiers doit être inférieure ou inférieure à 4 Mo pour qu’ils soient analyser.</span><span class="sxs-lookup"><span data-stu-id="027b8-156">Also, the size of the files needs to be 4 MB or less for it to be crawled.</span></span> <span data-ttu-id="027b8-157">Les types de fichiers actuellement pris en charge sont :</span><span class="sxs-lookup"><span data-stu-id="027b8-157">File types currently supported are:</span></span>

* <span data-ttu-id="027b8-158">Word (docx, .docm, .dotx, .dotm)</span><span class="sxs-lookup"><span data-stu-id="027b8-158">Word (docx, .docm, .dotx, .dotm)</span></span>
* <span data-ttu-id="027b8-159">PowerPoint (.pptm, .pptx, .potm, .potx, .ppam, .ppsm, .ppsx)</span><span class="sxs-lookup"><span data-stu-id="027b8-159">PowerPoint (.pptm, .pptx, .potm, .potx, .ppam, .ppsm, .ppsx)</span></span>
* <span data-ttu-id="027b8-160">Excel (.xlsx, .xlsm)</span><span class="sxs-lookup"><span data-stu-id="027b8-160">Excel (.xlsx, .xlsm)</span></span>
* <span data-ttu-id="027b8-161">Formats Office hérités (.doc, .dot, etc.)</span><span class="sxs-lookup"><span data-stu-id="027b8-161">Legacy Office formats (.doc, .dot, etc.)</span></span>
* <span data-ttu-id="027b8-162">Texte (.txt)</span><span class="sxs-lookup"><span data-stu-id="027b8-162">Text (.txt)</span></span>
* <span data-ttu-id="027b8-163">HTML</span><span class="sxs-lookup"><span data-stu-id="027b8-163">HTML</span></span>
* <span data-ttu-id="027b8-164">PDF</span><span class="sxs-lookup"><span data-stu-id="027b8-164">PDF</span></span>

<span data-ttu-id="027b8-165">Les fichiers binaires tels que les images (.jpg, .bmp, etc.) ne sont pas pris en charge.</span><span class="sxs-lookup"><span data-stu-id="027b8-165">Binary files like images (.jpg, .bmp, etc.) are not supported.</span></span> <span data-ttu-id="027b8-166">Par exemple, si un fichier .docx contient uniquement des images, il peut être ignoré car il n’a pas renvoyé de contenu.</span><span class="sxs-lookup"><span data-stu-id="027b8-166">For example, if a .docx file contains only images, it might be skipped because it didn't return any content.</span></span>
