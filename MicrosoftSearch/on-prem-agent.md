---
title: Agent local
ms.author: rusamai
author: rsamai
manager: jameslau
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
ROBOTS: NoIndex
description: Agent sur place
ms.openlocfilehash: 31220196849fe90ab2611e9c2b83a1cec0a02b34
ms.sourcegitcommit: a04f1df14a3221776ccd141f6060328612d80e06
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/15/2021
ms.locfileid: "49876497"
---
# <a name="graph-connector-agent"></a><span data-ttu-id="9af99-103">Agent de connecteur Graph</span><span class="sxs-lookup"><span data-stu-id="9af99-103">Graph connector agent</span></span>

<span data-ttu-id="9af99-104">L’utilisation de connecteurs Graph sur site nécessite l’installation du logiciel *d’agent du connecteur Graph.*</span><span class="sxs-lookup"><span data-stu-id="9af99-104">Using on-prem Graph connectors require you to install *Graph connector agent* software.</span></span> <span data-ttu-id="9af99-105">Il permet un transfert de données sécurisé entre les données sur site et les API du connecteur Graph.</span><span class="sxs-lookup"><span data-stu-id="9af99-105">It allows for secure data transfer between on-premises data and the Graph connector APIs.</span></span> <span data-ttu-id="9af99-106">Cet article vous guide tout au long de l’installation et de la configuration de l’agent.</span><span class="sxs-lookup"><span data-stu-id="9af99-106">This article guides you through the installing and configuring the agent.</span></span>

## <a name="installation"></a><span data-ttu-id="9af99-107">Installation</span><span class="sxs-lookup"><span data-stu-id="9af99-107">Installation</span></span>

<span data-ttu-id="9af99-108">Téléchargez la dernière version de l’agent de connecteur Graph [ici](https://aka.ms/gcadownload) et installez le logiciel à l’aide de l’Assistant d’installation.</span><span class="sxs-lookup"><span data-stu-id="9af99-108">Download the latest version of Graph connector agent [here](https://aka.ms/gcadownload) and install the software using the installation wizard.</span></span> <span data-ttu-id="9af99-109">À l’aide de la configuration recommandée de l’ordinateur décrite ci-dessous, le logiciel peut gérer jusqu’à trois connexions.</span><span class="sxs-lookup"><span data-stu-id="9af99-109">Using the recommended configuration of the machine described below, the software can handle up to three connections.</span></span> <span data-ttu-id="9af99-110">Toutes les connexions au-delà peuvent dégrader les performances de toutes les connexions sur l’agent.</span><span class="sxs-lookup"><span data-stu-id="9af99-110">Any connections beyond that might degrade the performance of all connections on the agent.</span></span>

<span data-ttu-id="9af99-111">Configuration recommandée :</span><span class="sxs-lookup"><span data-stu-id="9af99-111">Recommended configuration:</span></span>

* <span data-ttu-id="9af99-112">Windows 10, Windows Server 2016 R2 et supérieur</span><span class="sxs-lookup"><span data-stu-id="9af99-112">Windows 10, Windows Server 2016 R2 and above</span></span>
* [<span data-ttu-id="9af99-113">.NET Core Desktop Runtime 3.1 (x64)</span><span class="sxs-lookup"><span data-stu-id="9af99-113">.NET Core Desktop Runtime 3.1 (x64)</span></span>](https://dotnet.microsoft.com/download/dotnet-core/3.1)
* <span data-ttu-id="9af99-114">8 cœurs, 3 GHz</span><span class="sxs-lookup"><span data-stu-id="9af99-114">8 cores, 3 GHz</span></span>
* <span data-ttu-id="9af99-115">16 Go de RAM, 2 Go d’espace disque</span><span class="sxs-lookup"><span data-stu-id="9af99-115">16 GB RAM, 2 GB Disk Space</span></span>
* <span data-ttu-id="9af99-116">Accès réseau à la source de données et à Internet via 443</span><span class="sxs-lookup"><span data-stu-id="9af99-116">Network access to data source and internet through 443</span></span>

## <a name="create-and-configure-an-app-for-the-agent"></a><span data-ttu-id="9af99-117">Créer et configurer une application pour l’agent</span><span class="sxs-lookup"><span data-stu-id="9af99-117">Create and configure an App for the agent</span></span>  

<span data-ttu-id="9af99-118">Tout d’abord, connectez-vous et notez que le privilège minimal requis sur le compte est administrateur de recherche.</span><span class="sxs-lookup"><span data-stu-id="9af99-118">First, sign in and note that the minimum required privilege on the account is search administrator.</span></span> <span data-ttu-id="9af99-119">L’agent vous demandera ensuite de fournir des détails d’authentification.</span><span class="sxs-lookup"><span data-stu-id="9af99-119">The agent will then ask you to provide authentication details.</span></span> <span data-ttu-id="9af99-120">Utilisez les étapes ci-dessous pour créer une application et générer les détails d’authentification requis.</span><span class="sxs-lookup"><span data-stu-id="9af99-120">Use the steps below to create an app and generate the required authentication details.</span></span>

### <a name="create-an-app"></a><span data-ttu-id="9af99-121">Créer une application</span><span class="sxs-lookup"><span data-stu-id="9af99-121">Create an app</span></span>

1. <span data-ttu-id="9af99-122">Go to the [Azure portal](https://portal.azure.com) and sign in with admin credentials for the tenant.</span><span class="sxs-lookup"><span data-stu-id="9af99-122">Go to the [Azure portal](https://portal.azure.com) and sign in with admin credentials for the tenant.</span></span>
2. <span data-ttu-id="9af99-123">Accédez **aux inscriptions d’applications Azure Active Directory** à partir du volet de navigation et  ->   sélectionnez **Nouvelle inscription.**</span><span class="sxs-lookup"><span data-stu-id="9af99-123">Navigate to **Azure Active Directory** -> **App registrations** from the navigation pane and select **New registration**.</span></span>
3. <span data-ttu-id="9af99-124">Fournissez un nom pour l’application et sélectionnez **Enregistrer.**</span><span class="sxs-lookup"><span data-stu-id="9af99-124">Provide a name for the app and select **Register**.</span></span>
4. <span data-ttu-id="9af99-125">Notez l’ID de l’application (client).</span><span class="sxs-lookup"><span data-stu-id="9af99-125">Make a note of the Application (client) ID.</span></span>
5. <span data-ttu-id="9af99-126">Ouvrez **les autorisations d’API** à partir du volet de navigation et **sélectionnez Ajouter une autorisation.**</span><span class="sxs-lookup"><span data-stu-id="9af99-126">Open **API permissions** from the navigation pane and select **Add a permission**.</span></span>
6. <span data-ttu-id="9af99-127">Sélectionnez **Microsoft Graph,** puis les **autorisations d’application.**</span><span class="sxs-lookup"><span data-stu-id="9af99-127">Select **Microsoft Graph** and then **Application permissions**.</span></span>
7. <span data-ttu-id="9af99-128">Recherchez « ExternalItem.ReadWrite.All » et « Directory.Read.All » dans les autorisations, puis sélectionnez **Ajouter des autorisations.**</span><span class="sxs-lookup"><span data-stu-id="9af99-128">Search for "ExternalItem.ReadWrite.All" and "Directory.Read.All" from the permissions and select **Add permissions**.</span></span>
8. <span data-ttu-id="9af99-129">Sélectionnez **Accorder le consentement administrateur pour [TenantName]** et confirmer en sélectionnant **Oui**.</span><span class="sxs-lookup"><span data-stu-id="9af99-129">Select **Grant admin consent for [TenantName]** and confirm by selecting **Yes**.</span></span>
9. <span data-ttu-id="9af99-130">Vérifiez que les autorisations sont dans l’état « accordé ».</span><span class="sxs-lookup"><span data-stu-id="9af99-130">Check that the permissions are in the "granted" state.</span></span>
     <span data-ttu-id="9af99-131">![Autorisations affichées en vert sur la colonne de droite.](media/onprem-agent/granted-state.png)</span><span class="sxs-lookup"><span data-stu-id="9af99-131">![Permissions shown as granted in green on right hand column.](media/onprem-agent/granted-state.png)</span></span>

### <a name="configure-authentication"></a><span data-ttu-id="9af99-132">Configuration de l’authentification</span><span class="sxs-lookup"><span data-stu-id="9af99-132">Configure Authentication</span></span>

<span data-ttu-id="9af99-133">Les détails de l’authentification peuvent être fournis à l’aide d’une secret client ou d’un certificat.</span><span class="sxs-lookup"><span data-stu-id="9af99-133">Authentication details can be provided using a client secret or a certificate.</span></span> <span data-ttu-id="9af99-134">Suivez les étapes de votre choix.</span><span class="sxs-lookup"><span data-stu-id="9af99-134">Follow the steps of your choice.</span></span>

#### <a name="configuring-the-client-secret-for-authentication"></a><span data-ttu-id="9af99-135">Configuration de la secret client pour l’authentification</span><span class="sxs-lookup"><span data-stu-id="9af99-135">Configuring the client secret for authentication</span></span>

1. <span data-ttu-id="9af99-136">Go to the [Azure portal](https://portal.azure.com) and sign in with admin credentials for the tenant.</span><span class="sxs-lookup"><span data-stu-id="9af99-136">Go to the [Azure portal](https://portal.azure.com) and sign in with admin credentials for the tenant.</span></span>
2. <span data-ttu-id="9af99-137">Ouvrez **l’inscription** de l’application à partir du volet de navigation et allez à l’application appropriée.</span><span class="sxs-lookup"><span data-stu-id="9af99-137">Open **App Registration** from the navigation pane and go to the appropriate App.</span></span> <span data-ttu-id="9af99-138">Sous **Gérer,** sélectionnez **Certificats et secrets.**</span><span class="sxs-lookup"><span data-stu-id="9af99-138">Under **Manage**, select **Certificates and secrets**.</span></span>
3. <span data-ttu-id="9af99-139">Sélectionnez **Nouvelle secret client** et sélectionnez une période d’expiration pour la secret.</span><span class="sxs-lookup"><span data-stu-id="9af99-139">Select **New Client secret** and select an expiry period for the secret.</span></span> <span data-ttu-id="9af99-140">Copiez la secret généré et enregistrez-le, car il ne sera pas affiché à nouveau.</span><span class="sxs-lookup"><span data-stu-id="9af99-140">Copy the generated secret and save it because it won't be shown again.</span></span>
4. <span data-ttu-id="9af99-141">Utilisez cette question secrète client avec l’ID d’application pour configurer l’agent.</span><span class="sxs-lookup"><span data-stu-id="9af99-141">Use this Client secret along with the Application ID to configure the agent.</span></span> <span data-ttu-id="9af99-142">Vous ne pouvez pas utiliser d’espaces vides dans **le champ Nom** de l’agent.</span><span class="sxs-lookup"><span data-stu-id="9af99-142">You cannot use blank spaces in the **Name** field of the agent.</span></span> <span data-ttu-id="9af99-143">Les caractères numériques alpha sont acceptés.</span><span class="sxs-lookup"><span data-stu-id="9af99-143">Alpha numeric characters are accepted.</span></span>

#### <a name="using-a-certificate-for-authentication"></a><span data-ttu-id="9af99-144">Utilisation d’un certificat pour l’authentification</span><span class="sxs-lookup"><span data-stu-id="9af99-144">Using a certificate for authentication</span></span>

<span data-ttu-id="9af99-145">Il existe trois étapes simples pour l’utilisation de l’authentification basée sur les certificats :</span><span class="sxs-lookup"><span data-stu-id="9af99-145">There are three simple steps for using certificate-based authentication:</span></span>

1. <span data-ttu-id="9af99-146">Créer ou obtenir un certificat</span><span class="sxs-lookup"><span data-stu-id="9af99-146">Create or obtain a certificate</span></span>
1. <span data-ttu-id="9af99-147">Télécharger le certificat sur le portail Azure</span><span class="sxs-lookup"><span data-stu-id="9af99-147">Upload the certificate to the Azure portal</span></span>
1. <span data-ttu-id="9af99-148">Affecter le certificat à l’agent</span><span class="sxs-lookup"><span data-stu-id="9af99-148">Assign the certificate to the agent</span></span>

##### <a name="step-1-get-a-certificate"></a><span data-ttu-id="9af99-149">Étape 1 : Obtenir un certificat</span><span class="sxs-lookup"><span data-stu-id="9af99-149">Step 1: Get a certificate</span></span>

<span data-ttu-id="9af99-150">Le script ci-dessous peut être utilisé pour générer un certificat auto-signé.</span><span class="sxs-lookup"><span data-stu-id="9af99-150">The script below can be used to generate a self-signed certificate.</span></span> <span data-ttu-id="9af99-151">Votre organisation peut ne pas autoriser les certificats auto-signés.</span><span class="sxs-lookup"><span data-stu-id="9af99-151">Your organization may not allow self-signed certificates.</span></span> <span data-ttu-id="9af99-152">Dans ce cas, utilisez ces informations pour comprendre les exigences et acquérir un certificat conformément aux stratégies de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="9af99-152">In that case, use this information to understand the requirements and acquire a certificate in accordance to your organization's policies.</span></span>

```Powershell
$dnsName = "<TenantDomain like agent.onmicrosoft.com>" # Your DNS name
$password = "<password>" # Certificate password
$folderPath = "D:\New folder\" # Where do you want the files to get saved to? The folder needs to exist.
$fileName = "agentcert" # What do you want to call the cert files? without the file extension
$yearsValid = 10 # Number of years until you need to renew the certificate
$certStoreLocation = "cert:\LocalMachine\My"
$expirationDate = (Get-Date).AddYears($yearsValid)
$certificate = New-SelfSignedCertificate -DnsName $dnsName -CertStoreLocation $certStoreLocation -NotAfter $expirationDate -KeyExportPolicy Exportable -KeySpec Signature
$certificatePath = $certStoreLocation + '\' + $certificate.Thumbprint
$filePath = $folderPath + '\' + $fileName
$securePassword = ConvertTo-SecureString -String $password -Force -AsPlainText
Export-Certificate -Cert $certificatePath -FilePath ($filePath + '.cer')
Export-PfxCertificate -Cert $certificatePath -FilePath ($filePath + '.pfx') -Password $securePassword
```

##### <a name="step-2-upload-the-certificate-in-the-azure-portal"></a><span data-ttu-id="9af99-153">Étape 2 : Télécharger le certificat dans le portail Azure</span><span class="sxs-lookup"><span data-stu-id="9af99-153">Step 2: Upload the certificate in the Azure portal</span></span>

1. <span data-ttu-id="9af99-154">Ouvrez l’application et accédez à la section Certificats et secrets à partir du volet gauche</span><span class="sxs-lookup"><span data-stu-id="9af99-154">Open the application and navigate to certificates and secrets section from left pane</span></span>
1. <span data-ttu-id="9af99-155">Sélectionnez « Télécharger le certificat » et téléchargez le fichier .cer</span><span class="sxs-lookup"><span data-stu-id="9af99-155">Select 'Upload certificate' and upload the .cer file</span></span>
1. <span data-ttu-id="9af99-156">Ouvrez **l’inscription** de **l’application et sélectionnez Certificats et secrets** dans le volet de navigation.</span><span class="sxs-lookup"><span data-stu-id="9af99-156">Open **App registration** and select **Certificates and secrets** from the navigation pane.</span></span> <span data-ttu-id="9af99-157">Copiez l’empreinte numérique du certificat.</span><span class="sxs-lookup"><span data-stu-id="9af99-157">Copy the certificate thumbprint.</span></span>

![Liste des certificats miniatures lorsque certificats et secrets sont sélectionnés dans le volet gauche](media/onprem-agent/certificates.png)

##### <a name="step-3-assign-the-certificate-to-the-agent"></a><span data-ttu-id="9af99-159">Étape 3 : Attribuer le certificat à l’agent</span><span class="sxs-lookup"><span data-stu-id="9af99-159">Step 3: Assign the certificate to the agent</span></span>

<span data-ttu-id="9af99-160">Si vous avez utilisé l’exemple de script pour générer un certificat, le fichier PFX se trouve à l’emplacement identifié dans le script.</span><span class="sxs-lookup"><span data-stu-id="9af99-160">If you used the sample script to generate a certificate, the PFX file can be found in the location identified in the script.</span></span>

1. <span data-ttu-id="9af99-161">Téléchargez le fichier pfx de certificat sur l’ordinateur de l’agent.</span><span class="sxs-lookup"><span data-stu-id="9af99-161">Download the certificate pfx file onto the Agent machine.</span></span>
1. <span data-ttu-id="9af99-162">Double-cliquez sur le fichier pfx pour lancer la boîte de dialogue d’installation du certificat.</span><span class="sxs-lookup"><span data-stu-id="9af99-162">Double-click the pfx file to launch the certificate installation dialog.</span></span>
1. <span data-ttu-id="9af99-163">Sélectionnez « Ordinateur local » pour l’emplacement du magasin lors de l’installation du certificat.</span><span class="sxs-lookup"><span data-stu-id="9af99-163">Select 'Local Machine' for store location while installing the certificate.</span></span>
1. <span data-ttu-id="9af99-164">Après avoir installé le certificat, ouvrez « Gérer les certificats d’ordinateur » via le menu Démarrer</span><span class="sxs-lookup"><span data-stu-id="9af99-164">After installing the certificate, open 'Manage computer certificates' through Start menu</span></span>
1. <span data-ttu-id="9af99-165">Sélectionnez le certificat nouvellement installé sous « Personnel » > « Certificats »</span><span class="sxs-lookup"><span data-stu-id="9af99-165">Select the newly installed certificate under 'Personal' -> 'Certificates'</span></span>
1. <span data-ttu-id="9af99-166">Cliquez avec le bouton droit sur le cert et sélectionnez « Toutes les tâches » > « Gérer les clés privées... »</span><span class="sxs-lookup"><span data-stu-id="9af99-166">Right click on the cert and select 'All Tasks' -> 'Manage Private Keys…'</span></span> <span data-ttu-id="9af99-167">Option</span><span class="sxs-lookup"><span data-stu-id="9af99-167">Option</span></span>
1. <span data-ttu-id="9af99-168">Dans la boîte de dialogue Autorisations, sélectionnez ajouter une option.</span><span class="sxs-lookup"><span data-stu-id="9af99-168">In the permissions dialog, select add option.</span></span> <span data-ttu-id="9af99-169">Dans la boîte de dialogue de sélection de l’utilisateur, écrivez : « NT Service\GcaHostService » et cliquez sur « OK ».</span><span class="sxs-lookup"><span data-stu-id="9af99-169">In the user selection dialog, write: 'NT Service\GcaHostService' and click 'OK'.</span></span> <span data-ttu-id="9af99-170">Ne cliquez pas sur le bouton « Vérifier les noms ».</span><span class="sxs-lookup"><span data-stu-id="9af99-170">Don't click the 'Check Names' button.</span></span>
1. <span data-ttu-id="9af99-171">Cliquez sur OK dans la boîte de dialogue Autorisations.</span><span class="sxs-lookup"><span data-stu-id="9af99-171">Click okay on the permissions dialog.</span></span> <span data-ttu-id="9af99-172">L’ordinateur de l’agent est maintenant configuré pour que l’agent génère des jetons à l’aide du certificat.</span><span class="sxs-lookup"><span data-stu-id="9af99-172">The agent machine is now configured for agent to generate tokens using the certificate.</span></span>
