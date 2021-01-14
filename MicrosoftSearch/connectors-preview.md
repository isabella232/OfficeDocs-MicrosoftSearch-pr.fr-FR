---
title: Aperçu des connecteurs
ms.author: monaray
author: monaray97
manager: shohara
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: Découvrez la prévisualisation des connecteurs Microsoft Graph pour Microsoft Search (recherche Microsoft).
ms.openlocfilehash: 47f7e1e417222c948f2916c70626278f9fe5b44a
ms.sourcegitcommit: 469be70ad295a5837978d75babf5243115257f77
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/13/2021
ms.locfileid: "49847509"
---
# <a name="microsoft-graph-connectors-preview-release-and-features"></a><span data-ttu-id="e9c00-103">Fonctionnalités et version d’aperçu des connecteurs Microsoft Graph</span><span class="sxs-lookup"><span data-stu-id="e9c00-103">Microsoft Graph connectors preview release and features</span></span>

<span data-ttu-id="e9c00-104">Les connecteurs Microsoft Graph et les API de recherche Microsoft sont désormais généralement disponibles.</span><span class="sxs-lookup"><span data-stu-id="e9c00-104">Microsoft Graph connectors and Microsoft Search APIs are now generally available.</span></span> <span data-ttu-id="e9c00-105">Le déploiement initial sera destiné aux clients configurés pour la version ciblée.</span><span class="sxs-lookup"><span data-stu-id="e9c00-105">The initial rollout will be to customers configured for Targeted Release.</span></span> <span data-ttu-id="e9c00-106">Ce déploiement se déroule jusqu’à la fin du mois de février 2021.</span><span class="sxs-lookup"><span data-stu-id="e9c00-106">This rollout will go on until the end of February 2021.</span></span> <span data-ttu-id="e9c00-107">Une fois le déploiement terminé pour tous les clients, l’utilisation du quota d’index à partir du contenu des connecteurs est soumise à facturation.</span><span class="sxs-lookup"><span data-stu-id="e9c00-107">Upon rollout completion to all tenants, index quota utilization from connectors content will become subject to billing.</span></span> <span data-ttu-id="e9c00-108">Pour plus [d’informations, voir Exigences](licensing.md) et tarifs en matière de licences.</span><span class="sxs-lookup"><span data-stu-id="e9c00-108">See [Licensing requirements and pricing](licensing.md) for more information.</span></span>

## <a name="set-up-targeted-release"></a><span data-ttu-id="e9c00-109">Configurer la version ciblée</span><span class="sxs-lookup"><span data-stu-id="e9c00-109">Set up Targeted release</span></span>

<span data-ttu-id="e9c00-110">Si vous souhaitez utiliser des connecteurs Graph dans votre client lors du déploiement, vous **devez** opter pour la version ciblée.</span><span class="sxs-lookup"><span data-stu-id="e9c00-110">If you want to use Graph connectors in your tenant during rollout, you **must** opt into Targeted release.</span></span> <span data-ttu-id="e9c00-111">Pour en savoir plus sur l’option De publication ciblée et comment la définir, voir Configurer les options de publication standard ou ciblée [dans Office 365.](https://docs.microsoft.com/office365/admin/manage/release-options-in-office-365?view=o365-worldwide&preserve-view=true)</span><span class="sxs-lookup"><span data-stu-id="e9c00-111">To learn more about the Targeted release option and how to set it, see [Set up the Standard or Targeted release options in Office 365](https://docs.microsoft.com/office365/admin/manage/release-options-in-office-365?view=o365-worldwide&preserve-view=true).</span></span>

## <a name="preview-features"></a><span data-ttu-id="e9c00-112">Fonctionnalités en préversion</span><span class="sxs-lookup"><span data-stu-id="e9c00-112">Preview features</span></span>

<span data-ttu-id="e9c00-113">Bien que les connecteurs Microsoft Graph et les API de recherche Microsoft soient désormais généralement disponibles, plusieurs fonctionnalités resteront en prévisualisation.</span><span class="sxs-lookup"><span data-stu-id="e9c00-113">Although Microsoft Graph connectors and Microsoft Search APIs are now generally available, there are several features that will remain in preview.</span></span>

<span data-ttu-id="e9c00-114">L’ensemble des connecteurs et des fonctionnalités de la prévisualisation comprend les éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="e9c00-114">The set of connectors and features in preview include:</span></span>

* [<span data-ttu-id="e9c00-115">Connecteur Azure DevOps</span><span class="sxs-lookup"><span data-stu-id="e9c00-115">Azure DevOps connector</span></span>](azure-devops-connector.md)
* [<span data-ttu-id="e9c00-116">Connecteur Salesforce</span><span class="sxs-lookup"><span data-stu-id="e9c00-116">Salesforce connector</span></span>](salesforce-connector.md)
* <span data-ttu-id="e9c00-117">[Connecteur ServiceNow avec](servicenow-connector.md) autorisations de recherche qui utilisent des ACA sources</span><span class="sxs-lookup"><span data-stu-id="e9c00-117">[ServiceNow connector](servicenow-connector.md) with search permissions that use source ACLs</span></span>
* [<span data-ttu-id="e9c00-118">Gérer le cluster de résultat</span><span class="sxs-lookup"><span data-stu-id="e9c00-118">Manage result cluster</span></span>](result-cluster.md)