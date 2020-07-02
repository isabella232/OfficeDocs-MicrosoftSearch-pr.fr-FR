---
title: Gérer les réponses des acronymes dans Microsoft Search
ms.author: jeffkizn
author: jeffkizn
manager: parulm
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: Créer et mettre à jour des réponses d’acronymes dans Microsoft Search
ms.openlocfilehash: 9d58306751f735cef77eba4404597c73c0528c11
ms.sourcegitcommit: 9ba062f8b632a74e56ad7ec4dffaa1d8dab57614
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/01/2020
ms.locfileid: "44996075"
---
# <a name="manage-acronyms-answers-in-microsoft-search"></a><span data-ttu-id="bbd53-103">Gérer les acronymes Answers in Microsoft Search</span><span class="sxs-lookup"><span data-stu-id="bbd53-103">Manage Acronyms answers in Microsoft Search</span></span>

<span data-ttu-id="bbd53-104">Les utilisateurs ont souvent des acronymes et des abréviations inconnus utilisés par leur organisation ou leur équipe.</span><span class="sxs-lookup"><span data-stu-id="bbd53-104">Users often run into unfamiliar acronyms and abbreviations used by their organization or team.</span></span> <span data-ttu-id="bbd53-105">Les termes propres aux organisations ou aux équipes peuvent être nouveaux pour les personnes qui passent d’une équipe à une autre, qui travaillent avec des équipes partenaires internes ou qui sont nouveaux dans l’organisation.</span><span class="sxs-lookup"><span data-stu-id="bbd53-105">Terms that are specific to organizations or teams might be new to people who move from one team to another, those who work with internal partner teams, or are new to the organization.</span></span>

<span data-ttu-id="bbd53-106">Les organisations ne disposent pas toujours d’une référence unique pour leur terminologie standard.</span><span class="sxs-lookup"><span data-stu-id="bbd53-106">Organizations don't always have a single reference for their standard terminology.</span></span> <span data-ttu-id="bbd53-107">L’absence de référence unique rend difficile de trouver des définitions ou des expansions pour ces acronymes.</span><span class="sxs-lookup"><span data-stu-id="bbd53-107">Lack of a single reference makes it hard to find definitions or expansions for these acronyms.</span></span> <span data-ttu-id="bbd53-108">Microsoft Search résout ce problème avec des acronymes.</span><span class="sxs-lookup"><span data-stu-id="bbd53-108">Microsoft Search solves that problem with Acronyms.</span></span>

## <a name="what-users-experience"></a><span data-ttu-id="bbd53-109">Expérience des utilisateurs</span><span class="sxs-lookup"><span data-stu-id="bbd53-109">What users experience</span></span>

<span data-ttu-id="bbd53-110">Les utilisateurs de Microsoft Search peuvent obtenir des définitions avec des acronymes dans [Bing](https://Bing.com).</span><span class="sxs-lookup"><span data-stu-id="bbd53-110">Microsoft Search users can get definitions with Acronyms in [Bing](https://Bing.com).</span></span> <span data-ttu-id="bbd53-111">Dans la zone de **recherche** , les utilisateurs entrent des requêtes comme les exemples suivants :</span><span class="sxs-lookup"><span data-stu-id="bbd53-111">In the **Search** box, users enter queries like these examples:</span></span>

- <span data-ttu-id="bbd53-112">*Qu’est-ce que* DNN</span><span class="sxs-lookup"><span data-stu-id="bbd53-112">*What is* DNN</span></span>
- <span data-ttu-id="bbd53-113">*Définir* DNN</span><span class="sxs-lookup"><span data-stu-id="bbd53-113">*Define* DNN</span></span>
- <span data-ttu-id="bbd53-114">*Définition* DNN</span><span class="sxs-lookup"><span data-stu-id="bbd53-114">DNN *definition*</span></span>
- <span data-ttu-id="bbd53-115">*Développez* DNN</span><span class="sxs-lookup"><span data-stu-id="bbd53-115">*Expand* DNN</span></span>
- <span data-ttu-id="bbd53-116">*Expansion* DNN</span><span class="sxs-lookup"><span data-stu-id="bbd53-116">DNN *expansion*</span></span>
- <span data-ttu-id="bbd53-117">*Signification de* DNN</span><span class="sxs-lookup"><span data-stu-id="bbd53-117">*Meaning of* DNN</span></span>
- <span data-ttu-id="bbd53-118">DNN *signifie*</span><span class="sxs-lookup"><span data-stu-id="bbd53-118">DNN *means*</span></span>

<span data-ttu-id="bbd53-119">Le résultat inclut toutes les significations de DNN présentes dans l’organisation de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="bbd53-119">The result includes all the meanings of DNN that are present within the user’s organization.</span></span>

> [!NOTE]
> <span data-ttu-id="bbd53-120">Les utilisateurs doivent entrer une requête qui inclut les *Mots clés* spécifiés de l’acronyme pour déclencher les réponses correspondantes.</span><span class="sxs-lookup"><span data-stu-id="bbd53-120">Users must enter a query that includes the acronym’s specified *keywords* to trigger its corresponding answers.</span></span> <span data-ttu-id="bbd53-121">Les requêtes d’acronyme ne sont pas sensibles à la casse.</span><span class="sxs-lookup"><span data-stu-id="bbd53-121">Acronym queries are not case sensitive.</span></span>

## <a name="set-up-acronyms-answers"></a><span data-ttu-id="bbd53-122">Configurer des acronymes pour les réponses</span><span class="sxs-lookup"><span data-stu-id="bbd53-122">Set up Acronyms answers</span></span>

<span data-ttu-id="bbd53-123">Dans le centre d' [administration](https://admin.microsoft.com)Microsoft 365, accédez aux **paramètres**  >  acronymes de**Microsoft Search**  >  **Answers**  >  [**Acronyms**](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/acronyms), puis sélectionnez **Ajouter des acronymes**.</span><span class="sxs-lookup"><span data-stu-id="bbd53-123">In the Microsoft 365 [admin center](https://admin.microsoft.com), go to **Settings** > **Microsoft Search** > **Answers** > [**Acronyms**](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/acronyms), and then select **Add acronyms**.</span></span>

<span data-ttu-id="bbd53-124">Microsoft Search interroge deux sources de données pour fournir des informations d’acronymes aux recherches des utilisateurs :</span><span class="sxs-lookup"><span data-stu-id="bbd53-124">Microsoft Search queries two data sources to provide Acronyms answers to users’ searches:</span></span>

1. <span data-ttu-id="bbd53-125">**Acronymes éditorial**.</span><span class="sxs-lookup"><span data-stu-id="bbd53-125">**Editorial acronyms**.</span></span> <span data-ttu-id="bbd53-126">Fourni par les administrateurs informatiques dans le [Centre d’administration](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/acronyms).</span><span class="sxs-lookup"><span data-stu-id="bbd53-126">Provided by IT administrators in the [admin center](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/acronyms).</span></span>
2. <span data-ttu-id="bbd53-127">**Acronymes**de extrait.</span><span class="sxs-lookup"><span data-stu-id="bbd53-127">**Mined acronyms**.</span></span> <span data-ttu-id="bbd53-128">Extrait par Microsoft Search de la messagerie et des documents personnels de l’utilisateur et des données accessibles au public au sein de l’organisation.</span><span class="sxs-lookup"><span data-stu-id="bbd53-128">Mined by Microsoft Search from the user’s personal email and documents and publicly available data within the organization.</span></span>

### <a name="set-up-editorial-acronyms"></a><span data-ttu-id="bbd53-129">Configurer des acronymes éditoriaux</span><span class="sxs-lookup"><span data-stu-id="bbd53-129">Set up editorial acronyms</span></span>

<span data-ttu-id="bbd53-130">Les administrateurs de recherche peuvent configurer des acronymes éditoriaux sous l' [onglet acronymes](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/acronyms) dans le [Centre d’administration de Microsoft Search](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch).</span><span class="sxs-lookup"><span data-stu-id="bbd53-130">Search administrators can set up editorial acronyms on the [Acronyms tab](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/acronyms) in the  [Microsoft Search admin center](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch).</span></span> <span data-ttu-id="bbd53-131">Vous pouvez ajouter des acronymes à partir de n’importe quel site ou référentiel interne vers le centre d’administration.</span><span class="sxs-lookup"><span data-stu-id="bbd53-131">You can add acronyms from any internal site or repository to the admin center.</span></span> <span data-ttu-id="bbd53-132">Les acronymes éditoriaux peuvent être ajoutés à l’état **publié** ou **Brouillon** :</span><span class="sxs-lookup"><span data-stu-id="bbd53-132">Editorial acronyms can be added to **Published** or **Draft** state:</span></span>

<span data-ttu-id="bbd53-133">**État publié**.</span><span class="sxs-lookup"><span data-stu-id="bbd53-133">**Published state**.</span></span> <span data-ttu-id="bbd53-134">Les acronymes sont disponibles pour les employés de l’organisation via Microsoft Search.</span><span class="sxs-lookup"><span data-stu-id="bbd53-134">Acronyms are available to the organization’s employees through Microsoft Search.</span></span>

> [!NOTE]
> <span data-ttu-id="bbd53-135">Il peut falloir jusqu’à trois jours pour que les acronymes ajoutés à l’État publié soient disponibles dans Microsoft Search.</span><span class="sxs-lookup"><span data-stu-id="bbd53-135">It might take up to three days for acronyms added to Published state to become available in Microsoft Search.</span></span>

<span data-ttu-id="bbd53-136">**État Brouillon**.</span><span class="sxs-lookup"><span data-stu-id="bbd53-136">**Draft state**.</span></span> <span data-ttu-id="bbd53-137">Si les administrateurs souhaitent examiner les réponses des acronymes avant de les rendre disponibles dans Microsoft Search, ils peuvent ajouter les acronymes à l’état Brouillon.</span><span class="sxs-lookup"><span data-stu-id="bbd53-137">If admins want to review Acronyms answers before making them available in Microsoft Search, they can add the acronyms to Draft state.</span></span> <span data-ttu-id="bbd53-138">Les acronymes ajoutés à l’état Brouillon ne sont pas disponibles dans Microsoft Search.</span><span class="sxs-lookup"><span data-stu-id="bbd53-138">Acronyms added to Draft state aren’t available in Microsoft Search.</span></span> <span data-ttu-id="bbd53-139">Les administrateurs doivent ajouter les acronymes à l’État publié pour les rendre disponibles.</span><span class="sxs-lookup"><span data-stu-id="bbd53-139">Admins need to add the acronyms to Published state to make them available.</span></span>

<span data-ttu-id="bbd53-140">Les administrateurs peuvent ajouter des acronymes individuellement ou les importer par bloc dans un fichier CSV.</span><span class="sxs-lookup"><span data-stu-id="bbd53-140">Admins can add acronyms individually or bulk import them in a CSV file.</span></span> <span data-ttu-id="bbd53-141">Téléchargez un fichier CSV avec les champs indiqués dans le tableau suivant :</span><span class="sxs-lookup"><span data-stu-id="bbd53-141">Upload a CSV file with the fields shown in the following table:</span></span>

| <span data-ttu-id="bbd53-142">Acronyme (obligatoire)</span><span class="sxs-lookup"><span data-stu-id="bbd53-142">Acronym (mandatory)</span></span> | <span data-ttu-id="bbd53-143">Expansion (obligatoire)</span><span class="sxs-lookup"><span data-stu-id="bbd53-143">Expansion (mandatory)</span></span> | <span data-ttu-id="bbd53-144">Description</span><span class="sxs-lookup"><span data-stu-id="bbd53-144">Description</span></span>  | <span data-ttu-id="bbd53-145">Source</span><span class="sxs-lookup"><span data-stu-id="bbd53-145">Source</span></span> | <span data-ttu-id="bbd53-146">État (obligatoire)</span><span class="sxs-lookup"><span data-stu-id="bbd53-146">State (mandatory)</span></span> |
| --------- | --------- | ---------- | --------- |--------- |
| <span data-ttu-id="bbd53-147">*439*</span><span class="sxs-lookup"><span data-stu-id="bbd53-147">*XXX*</span></span> | <span data-ttu-id="bbd53-148">*Abréviation orthographiée*</span><span class="sxs-lookup"><span data-stu-id="bbd53-148">*Spelled out abbreviation*</span></span> |  | <span data-ttu-id="bbd53-149">*URL*</span><span class="sxs-lookup"><span data-stu-id="bbd53-149">*URL*</span></span> | <span data-ttu-id="bbd53-150">*Publié ou brouillon*</span><span class="sxs-lookup"><span data-stu-id="bbd53-150">*Published or Draft*</span></span> |

### <a name="csv-fields"></a><span data-ttu-id="bbd53-151">Champs CSV</span><span class="sxs-lookup"><span data-stu-id="bbd53-151">CSV fields</span></span>

<span data-ttu-id="bbd53-152">**Acronyme**.</span><span class="sxs-lookup"><span data-stu-id="bbd53-152">**Acronym**.</span></span> <span data-ttu-id="bbd53-153">Contient la forme courte ou l’acronyme réel.</span><span class="sxs-lookup"><span data-stu-id="bbd53-153">Contains the actual short form or acronym.</span></span> <span data-ttu-id="bbd53-154">Par exemple, *DNN*.</span><span class="sxs-lookup"><span data-stu-id="bbd53-154">An example is *DNN*.</span></span>

<span data-ttu-id="bbd53-155">**Expansion**.</span><span class="sxs-lookup"><span data-stu-id="bbd53-155">**Expansion**.</span></span> <span data-ttu-id="bbd53-156">Contient l’expansion de l’acronyme.</span><span class="sxs-lookup"><span data-stu-id="bbd53-156">Contains the expansion of the acronym.</span></span> <span data-ttu-id="bbd53-157">Il s’agit par exemple d’un *réseau neuronal profond*.</span><span class="sxs-lookup"><span data-stu-id="bbd53-157">An example is *Deep Neural Network*.</span></span>

<span data-ttu-id="bbd53-158">**Description**.</span><span class="sxs-lookup"><span data-stu-id="bbd53-158">**Description**.</span></span> <span data-ttu-id="bbd53-159">Brève description de l’acronyme qui donne aux utilisateurs un aperçu rapide de ce que signifient l’acronyme et son expansion.</span><span class="sxs-lookup"><span data-stu-id="bbd53-159">A brief description of the acronym that gives users quick insight into what the acronym and its expansion mean.</span></span> <span data-ttu-id="bbd53-160">Par exemple, *un réseau neuronal profond est un réseau neuronal avec un certain niveau de complexité, un réseau neuronal avec plus de deux couches*.</span><span class="sxs-lookup"><span data-stu-id="bbd53-160">For example, *A deep neural network is a neural network with a certain level of complexity, a neural network with more than two layers*.</span></span>

<span data-ttu-id="bbd53-161">**Source**.</span><span class="sxs-lookup"><span data-stu-id="bbd53-161">**Source**.</span></span> <span data-ttu-id="bbd53-162">URL de la page ou du site Web où vous souhaitez que les utilisateurs accèdent à des informations supplémentaires sur l’acronyme.</span><span class="sxs-lookup"><span data-stu-id="bbd53-162">The URL of the page or website where you want users to go for more information about the acronym.</span></span>

<span data-ttu-id="bbd53-163">**État**.</span><span class="sxs-lookup"><span data-stu-id="bbd53-163">**State**.</span></span> <span data-ttu-id="bbd53-164">Ce champ peut prendre deux valeurs :</span><span class="sxs-lookup"><span data-stu-id="bbd53-164">This field can take two values:</span></span>

- <span data-ttu-id="bbd53-165">**Brouillon**.</span><span class="sxs-lookup"><span data-stu-id="bbd53-165">**Draft**.</span></span> <span data-ttu-id="bbd53-166">Ajoute l’acronyme à l’état Brouillon.</span><span class="sxs-lookup"><span data-stu-id="bbd53-166">Adds  the acronym to the Draft state.</span></span>
- <span data-ttu-id="bbd53-167">**Publié**.</span><span class="sxs-lookup"><span data-stu-id="bbd53-167">**Published**.</span></span> <span data-ttu-id="bbd53-168">Ajoute l’acronyme à l’État publié et le rend disponible dans Microsoft Search.</span><span class="sxs-lookup"><span data-stu-id="bbd53-168">Adds the acronym to the Published state and makes it available in Microsoft Search.</span></span>

### <a name="mined-acronyms"></a><span data-ttu-id="bbd53-169">Acronymes de extrait</span><span class="sxs-lookup"><span data-stu-id="bbd53-169">Mined acronyms</span></span>

<span data-ttu-id="bbd53-170">Il peut être difficile pour les administrateurs d’ajouter tous les acronymes utilisés dans une organisation aux réponses.</span><span class="sxs-lookup"><span data-stu-id="bbd53-170">It might be a challenge for admins to add all the acronyms used within an organization to Answers.</span></span> <span data-ttu-id="bbd53-171">Cette fonctionnalité peut trouver des acronymes que les administrateurs de recherche ne tiennent pas compte de.</span><span class="sxs-lookup"><span data-stu-id="bbd53-171">This feature can find acronyms that search administrators aren’t even aware of.</span></span> <span data-ttu-id="bbd53-172">Pour ce faire, Microsoft Search explore également des acronymes de ces sources :</span><span class="sxs-lookup"><span data-stu-id="bbd53-172">To do that work, Microsoft Search also mines acronyms from these sources:</span></span>

- <span data-ttu-id="bbd53-173">Les e-mails des utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="bbd53-173">Users’ emails.</span></span>
- <span data-ttu-id="bbd53-174">Documents dans [SharePoint](https://products.office.com/sharepoint/collaboration), [Microsoft OneDrive]( https://onedrive.live.com/about/) et [Microsoft OneNote](http://www.onenote.com/).</span><span class="sxs-lookup"><span data-stu-id="bbd53-174">Documents in [SharePoint](https://products.office.com/sharepoint/collaboration), [Microsoft OneDrive]( https://onedrive.live.com/about/) and [Microsoft OneNote](http://www.onenote.com/).</span></span>
- <span data-ttu-id="bbd53-175">Documents publics au sein de l’organisation auxquels les utilisateurs ont accès dans SharePoint, OneDrive ou OneNote.</span><span class="sxs-lookup"><span data-stu-id="bbd53-175">Public documents within the organization that users have access to in SharePoint, OneDrive, or OneNote.</span></span>

<span data-ttu-id="bbd53-176">Microsoft Search garantit que seuls les utilisateurs disposant d’autorisations et d’accès à un document peuvent voir les acronymes qu’il contient.</span><span class="sxs-lookup"><span data-stu-id="bbd53-176">Microsoft Search makes sure that only users with access and permissions to a document can see the acronyms that are mined from it.</span></span> <span data-ttu-id="bbd53-177">Lorsqu’un acronyme provient de la boîte aux lettres d’un utilisateur, seul cet utilisateur peut voir cet acronyme.</span><span class="sxs-lookup"><span data-stu-id="bbd53-177">When an acronym is mined from a user's mailbox, only that user can see that acronym.</span></span>

> [!NOTE]
> <span data-ttu-id="bbd53-178">Aucune configuration n’est nécessaire pour les acronymes de l’extrait.</span><span class="sxs-lookup"><span data-stu-id="bbd53-178">No setup is needed for mined acronyms.</span></span>

## <a name="frequently-asked-questions"></a><span data-ttu-id="bbd53-179">Foire aux questions</span><span class="sxs-lookup"><span data-stu-id="bbd53-179">Frequently asked questions</span></span>

<span data-ttu-id="bbd53-180">**Q : comment les données éditoriales et extraites sont-elles classées ?**</span><span class="sxs-lookup"><span data-stu-id="bbd53-180">**Q: How is editorial and mined data ranked?**</span></span>

<span data-ttu-id="bbd53-181">**A :** La fonctionnalité classe actuellement les acronymes éditoriaux par-dessus les acronymes.</span><span class="sxs-lookup"><span data-stu-id="bbd53-181">**A:** The feature currently ranks editorial acronyms above mined acronyms.</span></span>

<span data-ttu-id="bbd53-182">**Q : combien de temps faut-il pour que les acronymes soient visibles dans Microsoft Search après leur publication ?**</span><span class="sxs-lookup"><span data-stu-id="bbd53-182">**Q: How long does it take for editorial acronyms to be visible in Microsoft Search after they’re published?**</span></span>

<span data-ttu-id="bbd53-183">**A :**  Trois jours sont nécessaires pour que les acronymes ajoutés à l’État publié soient disponibles dans Microsoft Search.</span><span class="sxs-lookup"><span data-stu-id="bbd53-183">**A:**  It takes up to three days for acronyms added to Published state to become available in Microsoft Search.</span></span>

<span data-ttu-id="bbd53-184">**Q : comment les utilisateurs déclenchent-ils les réponses ?**</span><span class="sxs-lookup"><span data-stu-id="bbd53-184">**Q: How do users trigger Acronyms answers?**</span></span>

<span data-ttu-id="bbd53-185">**R**: pour obtenir les réponses des acronymes, les utilisateurs doivent entrer des modèles de requête spécifiques dans une zone de **recherche** [Bing](https://bing.com) .</span><span class="sxs-lookup"><span data-stu-id="bbd53-185">**A**: To get Acronyms answers, users must enter specific query patterns in a [Bing](https://bing.com) **Search** box.</span></span> <span data-ttu-id="bbd53-186">Actuellement, les réponses d’acronyme ne sont pas disponibles dans [Office 365](https://Office.com) ou [SharePoint](https://products.office.com/sharepoint/collaboration).</span><span class="sxs-lookup"><span data-stu-id="bbd53-186">Currently, Acronym answers aren't available in [Office 365](https://Office.com) or [SharePoint](https://products.office.com/sharepoint/collaboration).</span></span>

<span data-ttu-id="bbd53-187">**Q : combien de temps faut-il pour que les acronymes s’affichent lorsque vous recevez ou envoyez un nouveau message ou un nouveau document ?**</span><span class="sxs-lookup"><span data-stu-id="bbd53-187">**Q: How long does it take for mined acronyms to appear after you receive or send a new email or document?**</span></span>

<span data-ttu-id="bbd53-188">**A :** Les acronymes extraites d’un nouveau message électronique ou d’un nouveau document prennent jusqu’à sept jours pour apparaître dans les résultats de Microsoft Search.</span><span class="sxs-lookup"><span data-stu-id="bbd53-188">**A:** Mined acronyms from a new email or document take up to seven days to appear in Microsoft Search results.</span></span>

<span data-ttu-id="bbd53-189">**Q : est-ce que les documents doivent être dans un format spécifique pour que l’exploration les récupère ?**</span><span class="sxs-lookup"><span data-stu-id="bbd53-189">**Q: Do documents need to be in a specific format for mining to pick them up?**</span></span>

<span data-ttu-id="bbd53-190">**A :** Nbre.</span><span class="sxs-lookup"><span data-stu-id="bbd53-190">**A:** No.</span></span> <span data-ttu-id="bbd53-191">Nous prenons en charge tous les types de fichiers, à l’exception des fichiers d’image, de dossiers et zip.</span><span class="sxs-lookup"><span data-stu-id="bbd53-191">We support all file types except image, folders, and zip files.</span></span>

<span data-ttu-id="bbd53-192">**Q : les acronymes de Microsoft mien seront-ils issus de documents dans toutes les langues ?**</span><span class="sxs-lookup"><span data-stu-id="bbd53-192">**Q: Will Microsoft mine acronyms from documents in all languages?**</span></span>

<span data-ttu-id="bbd53-193">**A**: Microsoft prend uniquement en charge l’exploration des documents en anglais.</span><span class="sxs-lookup"><span data-stu-id="bbd53-193">**A**: Microsoft only supports mining from documents in English.</span></span> <span data-ttu-id="bbd53-194">La prise en charge d’autres langues sera ajoutée en plusieurs phases.</span><span class="sxs-lookup"><span data-stu-id="bbd53-194">Support for other languages will be added in phases.</span></span>

<span data-ttu-id="bbd53-195">**Q : que se passe-t-il si mon organisation ne souhaite pas afficher d’acronymes extrait ? Puis-je arrêter l’affichage des acronymes d’extrait dans les résultats de recherche ?**</span><span class="sxs-lookup"><span data-stu-id="bbd53-195">**Q: What if my organization doesn’t want to show mined acronyms? Can I stop showing mined acronyms in search results?**</span></span>

<span data-ttu-id="bbd53-196">**A**: pour désactiver l’affichage des acronymes d’extrait dans les résultats de la recherche, créez un ticket de support client en suivant les instructions indiquées sur [contacter le support technique pour les produits métiers](https://docs.microsoft.com/office365/admin/contact-support-for-business-products?redirectSourcePath=%252f%252farticle%252fContact-Office-365-for-business-support-32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b&view=o365-worldwide&tabs=online#BKMK_call_support).</span><span class="sxs-lookup"><span data-stu-id="bbd53-196">**A**: To turn off showing mined acronyms in search results, create a customer support ticket by following the instructions at [Contact support for business products](https://docs.microsoft.com/office365/admin/contact-support-for-business-products?redirectSourcePath=%252f%252farticle%252fContact-Office-365-for-business-support-32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b&view=o365-worldwide&tabs=online#BKMK_call_support).</span></span>
<span data-ttu-id="bbd53-197">Une fois que vous avez créé un ticket de support, il prend jusqu’à 48 heures pour que les acronymes d’extrait s’affichent dans les résultats de la recherche.</span><span class="sxs-lookup"><span data-stu-id="bbd53-197">After you create a support ticket, it takes up to 48 hours for mined acronyms to stop appearing in search results.</span></span>

<span data-ttu-id="bbd53-198">**Q : Quand recevrai-je des réponses d’acronymes dans [Office 365](https://Office.com) et [SharePoint Online](https://products.office.com/sharepoint/collaboration)?**</span><span class="sxs-lookup"><span data-stu-id="bbd53-198">**Q: When will I see Acronyms answers in [Office 365](https://Office.com) and [SharePoint Online](https://products.office.com/sharepoint/collaboration)?**</span></span>

<span data-ttu-id="bbd53-199">**R**: acronymes Answers in Office 365 et SharePoint Online font partie de notre feuille de route de produits, mais nous ne sommes actuellement pas en mesure de fournir une date ou un calendrier.</span><span class="sxs-lookup"><span data-stu-id="bbd53-199">**A**: Acronyms answers in Office 365 and SharePoint Online are part of our product roadmap, but we're currently unable to provide a date or timeframe.</span></span>
