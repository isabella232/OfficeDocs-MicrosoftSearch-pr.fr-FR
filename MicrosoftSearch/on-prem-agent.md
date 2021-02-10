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
ms.openlocfilehash: 7aef2ea57c92929d4d4f45e1a738c84e6a3f4bba
ms.sourcegitcommit: ab4f81ded967168689e6e81c90e115b94719335c
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/10/2021
ms.locfileid: "50173061"
---
# <a name="graph-connector-agent"></a><span data-ttu-id="c770d-103">Agent de connecteur Graph</span><span class="sxs-lookup"><span data-stu-id="c770d-103">Graph connector agent</span></span>

<span data-ttu-id="c770d-104">L’utilisation de connecteurs Graph sur site nécessite l’installation du logiciel *d’agent du connecteur Graph.*</span><span class="sxs-lookup"><span data-stu-id="c770d-104">Using on-prem Graph connectors require you to install *Graph connector agent* software.</span></span> <span data-ttu-id="c770d-105">Il permet un transfert de données sécurisé entre les données sur site et les API du connecteur Graph.</span><span class="sxs-lookup"><span data-stu-id="c770d-105">It allows for secure data transfer between on-premises data and the Graph connector APIs.</span></span> <span data-ttu-id="c770d-106">Cet article vous guide tout au long de l’installation et de la configuration de l’agent.</span><span class="sxs-lookup"><span data-stu-id="c770d-106">This article guides you through the installing and configuring the agent.</span></span>

## <a name="installation"></a><span data-ttu-id="c770d-107">Installation</span><span class="sxs-lookup"><span data-stu-id="c770d-107">Installation</span></span>

<span data-ttu-id="c770d-108">Téléchargez la dernière version de l’agent de connecteur Graph [ici](https://aka.ms/gcadownload) et installez le logiciel à l’aide de l’Assistant d’installation.</span><span class="sxs-lookup"><span data-stu-id="c770d-108">Download the latest version of Graph connector agent [here](https://aka.ms/gcadownload) and install the software using the installation wizard.</span></span> <span data-ttu-id="c770d-109">À l’aide de la configuration recommandée de l’ordinateur décrite ci-dessous, le logiciel peut gérer jusqu’à trois connexions.</span><span class="sxs-lookup"><span data-stu-id="c770d-109">Using the recommended configuration of the machine described below, the software can handle up to three connections.</span></span> <span data-ttu-id="c770d-110">Toutes les connexions au-delà peuvent dégrader les performances de toutes les connexions sur l’agent.</span><span class="sxs-lookup"><span data-stu-id="c770d-110">Any connections beyond that might degrade the performance of all connections on the agent.</span></span>

<span data-ttu-id="c770d-111">Configuration recommandée :</span><span class="sxs-lookup"><span data-stu-id="c770d-111">Recommended configuration:</span></span>

* <span data-ttu-id="c770d-112">Windows 10, Windows Server 2016 R2 et supérieur</span><span class="sxs-lookup"><span data-stu-id="c770d-112">Windows 10, Windows Server 2016 R2 and above</span></span>
* [<span data-ttu-id="c770d-113">.NET Core Desktop Runtime 3.1 (x64)</span><span class="sxs-lookup"><span data-stu-id="c770d-113">.NET Core Desktop Runtime 3.1 (x64)</span></span>](https://dotnet.microsoft.com/download/dotnet-core/3.1)
* <span data-ttu-id="c770d-114">8 cœurs, 3 GHz</span><span class="sxs-lookup"><span data-stu-id="c770d-114">8 cores, 3 GHz</span></span>
* <span data-ttu-id="c770d-115">16 Go de RAM, 2 Go d’espace disque</span><span class="sxs-lookup"><span data-stu-id="c770d-115">16 GB RAM, 2 GB Disk Space</span></span>
* <span data-ttu-id="c770d-116">Accès réseau à la source de données et à Internet via 443</span><span class="sxs-lookup"><span data-stu-id="c770d-116">Network access to data source and internet through 443</span></span>

<span data-ttu-id="c770d-117">Après avoir installé l’agent, si les serveurs proxy ou les pare-feu de votre organisation bloquent la communication vers des domaines inconnus, ajoutez ceux ci-dessous à la liste d’accès.</span><span class="sxs-lookup"><span data-stu-id="c770d-117">After you install the agent, if your organization's proxy servers or firewalls block communication to unknown domains, please add below ones to the allow list.</span></span>

1. <span data-ttu-id="c770d-118">\*.servicebus.windows.net</span><span class="sxs-lookup"><span data-stu-id="c770d-118">\*.servicebus.windows.net</span></span>
2. <span data-ttu-id="c770d-119">\*.events.data.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="c770d-119">\*.events.data.microsoft.com</span></span>
3. https://login.microsoftonline.com
4. https://gcs.office.com
5. https://graph.microsoft.com/


## <a name="create-and-configure-an-app-for-the-agent"></a><span data-ttu-id="c770d-120">Créer et configurer une application pour l’agent</span><span class="sxs-lookup"><span data-stu-id="c770d-120">Create and configure an App for the agent</span></span>  

<span data-ttu-id="c770d-121">Tout d’abord, connectez-vous et notez que le privilège minimal requis sur le compte est administrateur de recherche.</span><span class="sxs-lookup"><span data-stu-id="c770d-121">First, sign in and note that the minimum required privilege on the account is search administrator.</span></span> <span data-ttu-id="c770d-122">L’agent vous demandera ensuite de fournir des détails d’authentification.</span><span class="sxs-lookup"><span data-stu-id="c770d-122">The agent will then ask you to provide authentication details.</span></span> <span data-ttu-id="c770d-123">Utilisez les étapes ci-dessous pour créer une application et générer les détails d’authentification requis.</span><span class="sxs-lookup"><span data-stu-id="c770d-123">Use the steps below to create an app and generate the required authentication details.</span></span>

### <a name="create-an-app"></a><span data-ttu-id="c770d-124">Créer une application</span><span class="sxs-lookup"><span data-stu-id="c770d-124">Create an app</span></span>

1. <span data-ttu-id="c770d-125">Go to the [Azure portal](https://portal.azure.com) and sign in with admin credentials for the tenant.</span><span class="sxs-lookup"><span data-stu-id="c770d-125">Go to the [Azure portal](https://portal.azure.com) and sign in with admin credentials for the tenant.</span></span>
2. <span data-ttu-id="c770d-126">Accédez **aux inscriptions d’applications Azure Active Directory** à partir du volet de navigation et  ->   sélectionnez **Nouvelle inscription.**</span><span class="sxs-lookup"><span data-stu-id="c770d-126">Navigate to **Azure Active Directory** -> **App registrations** from the navigation pane and select **New registration**.</span></span>
3. <span data-ttu-id="c770d-127">Fournissez un nom pour l’application et sélectionnez **Enregistrer.**</span><span class="sxs-lookup"><span data-stu-id="c770d-127">Provide a name for the app and select **Register**.</span></span>
4. <span data-ttu-id="c770d-128">Notez l’ID de l’application (client).</span><span class="sxs-lookup"><span data-stu-id="c770d-128">Make a note of the Application (client) ID.</span></span>
5. <span data-ttu-id="c770d-129">Ouvrez **les autorisations d’API** à partir du volet de navigation et **sélectionnez Ajouter une autorisation.**</span><span class="sxs-lookup"><span data-stu-id="c770d-129">Open **API permissions** from the navigation pane and select **Add a permission**.</span></span>
6. <span data-ttu-id="c770d-130">Sélectionnez **Microsoft Graph,** puis les **autorisations d’application.**</span><span class="sxs-lookup"><span data-stu-id="c770d-130">Select **Microsoft Graph** and then **Application permissions**.</span></span>
7. <span data-ttu-id="c770d-131">Recherchez « ExternalItem.ReadWrite.All » et « Directory.Read.All » dans les autorisations, puis sélectionnez **Ajouter des autorisations.**</span><span class="sxs-lookup"><span data-stu-id="c770d-131">Search for "ExternalItem.ReadWrite.All" and "Directory.Read.All" from the permissions and select **Add permissions**.</span></span>
8. <span data-ttu-id="c770d-132">Sélectionnez **Accorder le consentement de l’administrateur pour [TenantName]** et confirmez en sélectionnant **Oui**.</span><span class="sxs-lookup"><span data-stu-id="c770d-132">Select **Grant admin consent for [TenantName]** and confirm by selecting **Yes**.</span></span>
9. <span data-ttu-id="c770d-133">Vérifiez que les autorisations sont dans l’état « accordé ».</span><span class="sxs-lookup"><span data-stu-id="c770d-133">Check that the permissions are in the "granted" state.</span></span>
     <span data-ttu-id="c770d-134">![Autorisations affichées en vert sur la colonne de droite.](media/onprem-agent/granted-state.png)</span><span class="sxs-lookup"><span data-stu-id="c770d-134">![Permissions shown as granted in green on right hand column.](media/onprem-agent/granted-state.png)</span></span>

### <a name="configure-authentication"></a><span data-ttu-id="c770d-135">Configuration de l’authentification</span><span class="sxs-lookup"><span data-stu-id="c770d-135">Configure Authentication</span></span>

<span data-ttu-id="c770d-136">Les détails de l’authentification peuvent être fournis à l’aide d’une secret client ou d’un certificat.</span><span class="sxs-lookup"><span data-stu-id="c770d-136">Authentication details can be provided using a client secret or a certificate.</span></span> <span data-ttu-id="c770d-137">Suivez les étapes de votre choix.</span><span class="sxs-lookup"><span data-stu-id="c770d-137">Follow the steps of your choice.</span></span>

#### <a name="configuring-the-client-secret-for-authentication"></a><span data-ttu-id="c770d-138">Configuration de la secret client pour l’authentification</span><span class="sxs-lookup"><span data-stu-id="c770d-138">Configuring the client secret for authentication</span></span>

1. <span data-ttu-id="c770d-139">Go to the [Azure portal](https://portal.azure.com) and sign in with admin credentials for the tenant.</span><span class="sxs-lookup"><span data-stu-id="c770d-139">Go to the [Azure portal](https://portal.azure.com) and sign in with admin credentials for the tenant.</span></span>
2. <span data-ttu-id="c770d-140">Ouvrez **l’inscription** de l’application à partir du volet de navigation et allez à l’application appropriée.</span><span class="sxs-lookup"><span data-stu-id="c770d-140">Open **App Registration** from the navigation pane and go to the appropriate App.</span></span> <span data-ttu-id="c770d-141">Sous **Gérer,** sélectionnez **Certificats et secrets.**</span><span class="sxs-lookup"><span data-stu-id="c770d-141">Under **Manage**, select **Certificates and secrets**.</span></span>
3. <span data-ttu-id="c770d-142">Sélectionnez **Nouvelle secret client** et sélectionnez une période d’expiration pour la secret.</span><span class="sxs-lookup"><span data-stu-id="c770d-142">Select **New Client secret** and select an expiry period for the secret.</span></span> <span data-ttu-id="c770d-143">Copiez la secret généré et enregistrez-le, car il ne sera pas affiché à nouveau.</span><span class="sxs-lookup"><span data-stu-id="c770d-143">Copy the generated secret and save it because it won't be shown again.</span></span>
4. <span data-ttu-id="c770d-144">Utilisez cette question secrète client avec l’ID d’application pour configurer l’agent.</span><span class="sxs-lookup"><span data-stu-id="c770d-144">Use this Client secret along with the Application ID to configure the agent.</span></span> <span data-ttu-id="c770d-145">Vous ne pouvez pas utiliser d’espaces vides dans **le champ Nom** de l’agent.</span><span class="sxs-lookup"><span data-stu-id="c770d-145">You cannot use blank spaces in the **Name** field of the agent.</span></span> <span data-ttu-id="c770d-146">Les caractères numériques alpha sont acceptés.</span><span class="sxs-lookup"><span data-stu-id="c770d-146">Alpha numeric characters are accepted.</span></span>

#### <a name="using-a-certificate-for-authentication"></a><span data-ttu-id="c770d-147">Utilisation d’un certificat pour l’authentification</span><span class="sxs-lookup"><span data-stu-id="c770d-147">Using a certificate for authentication</span></span>

<span data-ttu-id="c770d-148">Il existe trois étapes simples pour l’utilisation de l’authentification basée sur les certificats :</span><span class="sxs-lookup"><span data-stu-id="c770d-148">There are three simple steps for using certificate-based authentication:</span></span>

1. <span data-ttu-id="c770d-149">Créer ou obtenir un certificat</span><span class="sxs-lookup"><span data-stu-id="c770d-149">Create or obtain a certificate</span></span>
1. <span data-ttu-id="c770d-150">Télécharger le certificat sur le portail Azure</span><span class="sxs-lookup"><span data-stu-id="c770d-150">Upload the certificate to the Azure portal</span></span>
1. <span data-ttu-id="c770d-151">Affecter le certificat à l’agent</span><span class="sxs-lookup"><span data-stu-id="c770d-151">Assign the certificate to the agent</span></span>

##### <a name="step-1-get-a-certificate"></a><span data-ttu-id="c770d-152">Étape 1 : Obtenir un certificat</span><span class="sxs-lookup"><span data-stu-id="c770d-152">Step 1: Get a certificate</span></span>

<span data-ttu-id="c770d-153">Le script ci-dessous peut être utilisé pour générer un certificat auto-signé.</span><span class="sxs-lookup"><span data-stu-id="c770d-153">The script below can be used to generate a self-signed certificate.</span></span> <span data-ttu-id="c770d-154">Votre organisation peut ne pas autoriser les certificats auto-signés.</span><span class="sxs-lookup"><span data-stu-id="c770d-154">Your organization may not allow self-signed certificates.</span></span> <span data-ttu-id="c770d-155">Dans ce cas, utilisez ces informations pour comprendre les exigences et acquérir un certificat conformément aux stratégies de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="c770d-155">In that case, use this information to understand the requirements and acquire a certificate in accordance to your organization's policies.</span></span>

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

##### <a name="step-2-upload-the-certificate-in-the-azure-portal"></a><span data-ttu-id="c770d-156">Étape 2 : Télécharger le certificat dans le portail Azure</span><span class="sxs-lookup"><span data-stu-id="c770d-156">Step 2: Upload the certificate in the Azure portal</span></span>

1. <span data-ttu-id="c770d-157">Ouvrez l’application et accédez à la section Certificats et secrets à partir du volet gauche</span><span class="sxs-lookup"><span data-stu-id="c770d-157">Open the application and navigate to certificates and secrets section from left pane</span></span>
1. <span data-ttu-id="c770d-158">Sélectionnez « Télécharger le certificat » et téléchargez le fichier .cer</span><span class="sxs-lookup"><span data-stu-id="c770d-158">Select 'Upload certificate' and upload the .cer file</span></span>
1. <span data-ttu-id="c770d-159">Ouvrez **l’inscription de** **l’application et sélectionnez Certificats et secrets** dans le volet de navigation.</span><span class="sxs-lookup"><span data-stu-id="c770d-159">Open **App registration** and select **Certificates and secrets** from the navigation pane.</span></span> <span data-ttu-id="c770d-160">Copiez l’empreinte numérique du certificat.</span><span class="sxs-lookup"><span data-stu-id="c770d-160">Copy the certificate thumbprint.</span></span>

![Liste des certificats miniatures lorsque certificats et secrets sont sélectionnés dans le volet gauche](media/onprem-agent/certificates.png)

##### <a name="step-3-assign-the-certificate-to-the-agent"></a><span data-ttu-id="c770d-162">Étape 3 : Attribuer le certificat à l’agent</span><span class="sxs-lookup"><span data-stu-id="c770d-162">Step 3: Assign the certificate to the agent</span></span>

<span data-ttu-id="c770d-163">Si vous avez utilisé l’exemple de script pour générer un certificat, le fichier PFX se trouve à l’emplacement identifié dans le script.</span><span class="sxs-lookup"><span data-stu-id="c770d-163">If you used the sample script to generate a certificate, the PFX file can be found in the location identified in the script.</span></span>

1. <span data-ttu-id="c770d-164">Téléchargez le fichier pfx de certificat sur l’ordinateur de l’agent.</span><span class="sxs-lookup"><span data-stu-id="c770d-164">Download the certificate pfx file onto the Agent machine.</span></span>
1. <span data-ttu-id="c770d-165">Double-cliquez sur le fichier pfx pour lancer la boîte de dialogue d’installation du certificat.</span><span class="sxs-lookup"><span data-stu-id="c770d-165">Double-click the pfx file to launch the certificate installation dialog.</span></span>
1. <span data-ttu-id="c770d-166">Sélectionnez « Ordinateur local » pour l’emplacement du magasin lors de l’installation du certificat.</span><span class="sxs-lookup"><span data-stu-id="c770d-166">Select 'Local Machine' for store location while installing the certificate.</span></span>
1. <span data-ttu-id="c770d-167">Après avoir installé le certificat, ouvrez « Gérer les certificats d’ordinateur » via le menu Démarrer</span><span class="sxs-lookup"><span data-stu-id="c770d-167">After installing the certificate, open 'Manage computer certificates' through Start menu</span></span>
1. <span data-ttu-id="c770d-168">Sélectionnez le certificat nouvellement installé sous « Personnel » > « Certificats »</span><span class="sxs-lookup"><span data-stu-id="c770d-168">Select the newly installed certificate under 'Personal' -> 'Certificates'</span></span>
1. <span data-ttu-id="c770d-169">Cliquez avec le bouton droit sur le cert, puis sélectionnez « Toutes les tâches > gérer les clés privées... »</span><span class="sxs-lookup"><span data-stu-id="c770d-169">Right click on the cert and select 'All Tasks' -> 'Manage Private Keys…'</span></span> <span data-ttu-id="c770d-170">Option</span><span class="sxs-lookup"><span data-stu-id="c770d-170">Option</span></span>
1. <span data-ttu-id="c770d-171">Dans la boîte de dialogue Autorisations, sélectionnez ajouter une option.</span><span class="sxs-lookup"><span data-stu-id="c770d-171">In the permissions dialog, select add option.</span></span> <span data-ttu-id="c770d-172">Dans la boîte de dialogue de sélection de l’utilisateur, écrivez : « NT Service\GcaHostService » et cliquez sur « OK ».</span><span class="sxs-lookup"><span data-stu-id="c770d-172">In the user selection dialog, write: 'NT Service\GcaHostService' and click 'OK'.</span></span> <span data-ttu-id="c770d-173">Ne cliquez pas sur le bouton « Vérifier les noms ».</span><span class="sxs-lookup"><span data-stu-id="c770d-173">Don't click the 'Check Names' button.</span></span>
1. <span data-ttu-id="c770d-174">Cliquez sur OK dans la boîte de dialogue Autorisations.</span><span class="sxs-lookup"><span data-stu-id="c770d-174">Click okay on the permissions dialog.</span></span> <span data-ttu-id="c770d-175">L’ordinateur de l’agent est maintenant configuré pour que l’agent génère des jetons à l’aide du certificat.</span><span class="sxs-lookup"><span data-stu-id="c770d-175">The agent machine is now configured for agent to generate tokens using the certificate.</span></span>
