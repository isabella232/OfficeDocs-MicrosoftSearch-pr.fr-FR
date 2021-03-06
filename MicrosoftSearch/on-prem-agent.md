---
title: Agent local
ms.author: rusamai
author: rsamai
manager: jameslau
audience: Admin
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
ms.openlocfilehash: 5134c0c4459f9d38825451f274e67469956756d2
ms.sourcegitcommit: f76ade4c8fed0fee9c36d067b3ca8288c6c980aa
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/05/2021
ms.locfileid: "50508804"
---
# <a name="graph-connector-agent"></a><span data-ttu-id="3f160-103">Agent de connecteur Graph</span><span class="sxs-lookup"><span data-stu-id="3f160-103">Graph connector agent</span></span>

<span data-ttu-id="3f160-104">L’utilisation de connecteurs Graph sur site nécessite l’installation du logiciel *d’agent du connecteur Graph.*</span><span class="sxs-lookup"><span data-stu-id="3f160-104">Using on-prem Graph connectors require you to install *Graph connector agent* software.</span></span> <span data-ttu-id="3f160-105">Il permet un transfert de données sécurisé entre les données sur site et les API du connecteur Graph.</span><span class="sxs-lookup"><span data-stu-id="3f160-105">It allows for secure data transfer between on-premises data and the Graph connector APIs.</span></span> <span data-ttu-id="3f160-106">Cet article vous guide tout au long de l’installation et de la configuration de l’agent.</span><span class="sxs-lookup"><span data-stu-id="3f160-106">This article guides you through the installing and configuring the agent.</span></span>

## <a name="installation"></a><span data-ttu-id="3f160-107">Installation</span><span class="sxs-lookup"><span data-stu-id="3f160-107">Installation</span></span>

<span data-ttu-id="3f160-108">Téléchargez la dernière version de l’agent de connecteur Graph [ici](https://aka.ms/gcadownload) et installez le logiciel à l’aide de l’Assistant d’installation.</span><span class="sxs-lookup"><span data-stu-id="3f160-108">Download the latest version of Graph connector agent [here](https://aka.ms/gcadownload) and install the software using the installation wizard.</span></span> <span data-ttu-id="3f160-109">À l’aide de la configuration recommandée de l’ordinateur décrite ci-dessous, le logiciel peut gérer jusqu’à trois connexions.</span><span class="sxs-lookup"><span data-stu-id="3f160-109">Using the recommended configuration of the machine described below, the software can handle up to three connections.</span></span> <span data-ttu-id="3f160-110">Toutes les connexions au-delà peuvent dégrader les performances de toutes les connexions sur l’agent.</span><span class="sxs-lookup"><span data-stu-id="3f160-110">Any connections beyond that might degrade the performance of all connections on the agent.</span></span>

<span data-ttu-id="3f160-111">Configuration recommandée :</span><span class="sxs-lookup"><span data-stu-id="3f160-111">Recommended configuration:</span></span>

* <span data-ttu-id="3f160-112">Windows 10, Windows Server 2016 R2 et supérieur</span><span class="sxs-lookup"><span data-stu-id="3f160-112">Windows 10, Windows Server 2016 R2 and above</span></span>
* [<span data-ttu-id="3f160-113">.NET Core Desktop Runtime 3.1 (x64)</span><span class="sxs-lookup"><span data-stu-id="3f160-113">.NET Core Desktop Runtime 3.1 (x64)</span></span>](https://dotnet.microsoft.com/download/dotnet-core/3.1)
* <span data-ttu-id="3f160-114">8 cœurs, 3 GHz</span><span class="sxs-lookup"><span data-stu-id="3f160-114">8 cores, 3 GHz</span></span>
* <span data-ttu-id="3f160-115">16 Go de RAM, 2 Go d’espace disque</span><span class="sxs-lookup"><span data-stu-id="3f160-115">16 GB RAM, 2 GB Disk Space</span></span>
* <span data-ttu-id="3f160-116">Accès réseau à la source de données et à Internet via 443</span><span class="sxs-lookup"><span data-stu-id="3f160-116">Network access to data source and internet through 443</span></span>

<span data-ttu-id="3f160-117">Après avoir installé l’agent, si les serveurs proxy ou les pare-feu de votre organisation bloquent la communication vers des domaines inconnus, ajoutez-en ci-dessous à la liste d’accès.</span><span class="sxs-lookup"><span data-stu-id="3f160-117">After you install the agent, if your organization's proxy servers or firewalls block communication to unknown domains, please add below ones to the allow list.</span></span>

1. <span data-ttu-id="3f160-118">\*.servicebus.windows.net</span><span class="sxs-lookup"><span data-stu-id="3f160-118">\*.servicebus.windows.net</span></span>
2. <span data-ttu-id="3f160-119">\*.events.data.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="3f160-119">\*.events.data.microsoft.com</span></span>
3. <span data-ttu-id="3f160-120"> https://<span>login.microsoftonline.</span>com</span><span class="sxs-lookup"><span data-stu-id="3f160-120">https://<span>login.microsoftonline.</span>com</span></span>
4. <span data-ttu-id="3f160-121"> https://<span>gcs.office.</span> com/</span><span class="sxs-lookup"><span data-stu-id="3f160-121">https://<span>gcs.office.</span>com/</span></span>
5. <span data-ttu-id="3f160-122"> https://<span>graph.microsoft.</span> com/</span><span class="sxs-lookup"><span data-stu-id="3f160-122">https://<span>graph.microsoft.</span>com/</span></span>


## <a name="create-and-configure-an-app-for-the-agent"></a><span data-ttu-id="3f160-123">Créer et configurer une application pour l’agent</span><span class="sxs-lookup"><span data-stu-id="3f160-123">Create and configure an App for the agent</span></span>  

<span data-ttu-id="3f160-124">Tout d’abord, connectez-vous et notez que le privilège minimal requis sur le compte est administrateur de recherche.</span><span class="sxs-lookup"><span data-stu-id="3f160-124">First, sign in and note that the minimum required privilege on the account is search administrator.</span></span> <span data-ttu-id="3f160-125">L’agent vous demandera ensuite de fournir des détails d’authentification.</span><span class="sxs-lookup"><span data-stu-id="3f160-125">The agent will then ask you to provide authentication details.</span></span> <span data-ttu-id="3f160-126">Utilisez les étapes ci-dessous pour créer une application et générer les détails d’authentification requis.</span><span class="sxs-lookup"><span data-stu-id="3f160-126">Use the steps below to create an app and generate the required authentication details.</span></span>

### <a name="create-an-app"></a><span data-ttu-id="3f160-127">Créer une application</span><span class="sxs-lookup"><span data-stu-id="3f160-127">Create an app</span></span>

1. <span data-ttu-id="3f160-128">Go to the [Azure portal](https://portal.azure.com) and sign in with admin credentials for the tenant.</span><span class="sxs-lookup"><span data-stu-id="3f160-128">Go to the [Azure portal](https://portal.azure.com) and sign in with admin credentials for the tenant.</span></span>
2. <span data-ttu-id="3f160-129">Accédez **aux inscriptions d’applications Azure Active Directory** à partir du volet de navigation et  ->   sélectionnez **Nouvelle inscription.**</span><span class="sxs-lookup"><span data-stu-id="3f160-129">Navigate to **Azure Active Directory** -> **App registrations** from the navigation pane and select **New registration**.</span></span>
3. <span data-ttu-id="3f160-130">Fournissez un nom pour l’application et sélectionnez **Enregistrer.**</span><span class="sxs-lookup"><span data-stu-id="3f160-130">Provide a name for the app and select **Register**.</span></span>
4. <span data-ttu-id="3f160-131">Notez l’ID de l’application (client).</span><span class="sxs-lookup"><span data-stu-id="3f160-131">Make a note of the Application (client) ID.</span></span>
5. <span data-ttu-id="3f160-132">Ouvrez **les autorisations d’API** à partir du volet de navigation et **sélectionnez Ajouter une autorisation.**</span><span class="sxs-lookup"><span data-stu-id="3f160-132">Open **API permissions** from the navigation pane and select **Add a permission**.</span></span>
6. <span data-ttu-id="3f160-133">Sélectionnez **Microsoft Graph,** puis les **autorisations d’application.**</span><span class="sxs-lookup"><span data-stu-id="3f160-133">Select **Microsoft Graph** and then **Application permissions**.</span></span>
7. <span data-ttu-id="3f160-134">Recherchez « ExternalItem.ReadWrite.All » et « Directory.Read.All » dans les autorisations, puis sélectionnez **Ajouter des autorisations.**</span><span class="sxs-lookup"><span data-stu-id="3f160-134">Search for "ExternalItem.ReadWrite.All" and "Directory.Read.All" from the permissions and select **Add permissions**.</span></span>
8. <span data-ttu-id="3f160-135">Sélectionnez **Accorder le consentement de l’administrateur pour [TenantName]** et confirmez en sélectionnant **Oui**.</span><span class="sxs-lookup"><span data-stu-id="3f160-135">Select **Grant admin consent for [TenantName]** and confirm by selecting **Yes**.</span></span>
9. <span data-ttu-id="3f160-136">Vérifiez que les autorisations sont dans l’état « accordé ».</span><span class="sxs-lookup"><span data-stu-id="3f160-136">Check that the permissions are in the "granted" state.</span></span>
     <span data-ttu-id="3f160-137">![Autorisations affichées en vert sur la colonne de droite.](media/onprem-agent/granted-state.png)</span><span class="sxs-lookup"><span data-stu-id="3f160-137">![Permissions shown as granted in green on right hand column.](media/onprem-agent/granted-state.png)</span></span>

### <a name="configure-authentication"></a><span data-ttu-id="3f160-138">Configuration de l’authentification</span><span class="sxs-lookup"><span data-stu-id="3f160-138">Configure Authentication</span></span>

<span data-ttu-id="3f160-139">Les détails de l’authentification peuvent être fournis à l’aide d’une secret client ou d’un certificat.</span><span class="sxs-lookup"><span data-stu-id="3f160-139">Authentication details can be provided using a client secret or a certificate.</span></span> <span data-ttu-id="3f160-140">Suivez les étapes de votre choix.</span><span class="sxs-lookup"><span data-stu-id="3f160-140">Follow the steps of your choice.</span></span>

#### <a name="configuring-the-client-secret-for-authentication"></a><span data-ttu-id="3f160-141">Configuration de la secret client pour l’authentification</span><span class="sxs-lookup"><span data-stu-id="3f160-141">Configuring the client secret for authentication</span></span>

1. <span data-ttu-id="3f160-142">Go to the [Azure portal](https://portal.azure.com) and sign in with admin credentials for the tenant.</span><span class="sxs-lookup"><span data-stu-id="3f160-142">Go to the [Azure portal](https://portal.azure.com) and sign in with admin credentials for the tenant.</span></span>
2. <span data-ttu-id="3f160-143">Ouvrez **l’inscription** de l’application à partir du volet de navigation et allez à l’application appropriée.</span><span class="sxs-lookup"><span data-stu-id="3f160-143">Open **App Registration** from the navigation pane and go to the appropriate App.</span></span> <span data-ttu-id="3f160-144">Sous **Gérer,** **sélectionnez Certificats et secrets.**</span><span class="sxs-lookup"><span data-stu-id="3f160-144">Under **Manage**, select **Certificates and secrets**.</span></span>
3. <span data-ttu-id="3f160-145">Sélectionnez **Nouvelle secret client** et sélectionnez une période d’expiration pour la secret.</span><span class="sxs-lookup"><span data-stu-id="3f160-145">Select **New Client secret** and select an expiry period for the secret.</span></span> <span data-ttu-id="3f160-146">Copiez la secret généré et enregistrez-le, car il ne sera pas affiché à nouveau.</span><span class="sxs-lookup"><span data-stu-id="3f160-146">Copy the generated secret and save it because it won't be shown again.</span></span>
4. <span data-ttu-id="3f160-147">Utilisez cette question secrète client avec l’ID d’application pour configurer l’agent.</span><span class="sxs-lookup"><span data-stu-id="3f160-147">Use this Client secret along with the Application ID to configure the agent.</span></span> <span data-ttu-id="3f160-148">Vous ne pouvez pas utiliser d’espaces vides dans **le champ Nom** de l’agent.</span><span class="sxs-lookup"><span data-stu-id="3f160-148">You cannot use blank spaces in the **Name** field of the agent.</span></span> <span data-ttu-id="3f160-149">Les caractères numériques alpha sont acceptés.</span><span class="sxs-lookup"><span data-stu-id="3f160-149">Alpha numeric characters are accepted.</span></span>

#### <a name="using-a-certificate-for-authentication"></a><span data-ttu-id="3f160-150">Utilisation d’un certificat pour l’authentification</span><span class="sxs-lookup"><span data-stu-id="3f160-150">Using a certificate for authentication</span></span>

<span data-ttu-id="3f160-151">Il existe trois étapes simples pour l’utilisation de l’authentification basée sur les certificats :</span><span class="sxs-lookup"><span data-stu-id="3f160-151">There are three simple steps for using certificate-based authentication:</span></span>

1. <span data-ttu-id="3f160-152">Créer ou obtenir un certificat</span><span class="sxs-lookup"><span data-stu-id="3f160-152">Create or obtain a certificate</span></span>
1. <span data-ttu-id="3f160-153">Télécharger le certificat sur le portail Azure</span><span class="sxs-lookup"><span data-stu-id="3f160-153">Upload the certificate to the Azure portal</span></span>
1. <span data-ttu-id="3f160-154">Affecter le certificat à l’agent</span><span class="sxs-lookup"><span data-stu-id="3f160-154">Assign the certificate to the agent</span></span>

##### <a name="step-1-get-a-certificate"></a><span data-ttu-id="3f160-155">Étape 1 : Obtenir un certificat</span><span class="sxs-lookup"><span data-stu-id="3f160-155">Step 1: Get a certificate</span></span>

<span data-ttu-id="3f160-156">Le script ci-dessous peut être utilisé pour générer un certificat auto-signé.</span><span class="sxs-lookup"><span data-stu-id="3f160-156">The script below can be used to generate a self-signed certificate.</span></span> <span data-ttu-id="3f160-157">Votre organisation peut ne pas autoriser les certificats auto-signés.</span><span class="sxs-lookup"><span data-stu-id="3f160-157">Your organization may not allow self-signed certificates.</span></span> <span data-ttu-id="3f160-158">Dans ce cas, utilisez ces informations pour comprendre les exigences et acquérir un certificat conformément aux stratégies de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="3f160-158">In that case, use this information to understand the requirements and acquire a certificate in accordance to your organization's policies.</span></span>

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

##### <a name="step-2-upload-the-certificate-in-the-azure-portal"></a><span data-ttu-id="3f160-159">Étape 2 : Télécharger le certificat dans le portail Azure</span><span class="sxs-lookup"><span data-stu-id="3f160-159">Step 2: Upload the certificate in the Azure portal</span></span>

1. <span data-ttu-id="3f160-160">Ouvrez l’application et accédez à la section Certificats et secrets à partir du volet gauche</span><span class="sxs-lookup"><span data-stu-id="3f160-160">Open the application and navigate to certificates and secrets section from left pane</span></span>
1. <span data-ttu-id="3f160-161">Sélectionnez « Télécharger le certificat » et téléchargez le fichier .cer</span><span class="sxs-lookup"><span data-stu-id="3f160-161">Select 'Upload certificate' and upload the .cer file</span></span>
1. <span data-ttu-id="3f160-162">Ouvrez **l’inscription de** **l’application et sélectionnez Certificats et secrets** dans le volet de navigation.</span><span class="sxs-lookup"><span data-stu-id="3f160-162">Open **App registration** and select **Certificates and secrets** from the navigation pane.</span></span> <span data-ttu-id="3f160-163">Copiez l’empreinte numérique du certificat.</span><span class="sxs-lookup"><span data-stu-id="3f160-163">Copy the certificate thumbprint.</span></span>

![Liste des certificats miniatures lorsque certificats et secrets sont sélectionnés dans le volet gauche](media/onprem-agent/certificates.png)

##### <a name="step-3-assign-the-certificate-to-the-agent"></a><span data-ttu-id="3f160-165">Étape 3 : Attribuer le certificat à l’agent</span><span class="sxs-lookup"><span data-stu-id="3f160-165">Step 3: Assign the certificate to the agent</span></span>

<span data-ttu-id="3f160-166">Si vous avez utilisé l’exemple de script pour générer un certificat, le fichier PFX se trouve à l’emplacement identifié dans le script.</span><span class="sxs-lookup"><span data-stu-id="3f160-166">If you used the sample script to generate a certificate, the PFX file can be found in the location identified in the script.</span></span>

1. <span data-ttu-id="3f160-167">Téléchargez le fichier pfx de certificat sur l’ordinateur de l’agent.</span><span class="sxs-lookup"><span data-stu-id="3f160-167">Download the certificate pfx file onto the Agent machine.</span></span>
1. <span data-ttu-id="3f160-168">Double-cliquez sur le fichier pfx pour lancer la boîte de dialogue d’installation du certificat.</span><span class="sxs-lookup"><span data-stu-id="3f160-168">Double-click the pfx file to launch the certificate installation dialog.</span></span>
1. <span data-ttu-id="3f160-169">Sélectionnez « Ordinateur local » pour l’emplacement du magasin lors de l’installation du certificat.</span><span class="sxs-lookup"><span data-stu-id="3f160-169">Select 'Local Machine' for store location while installing the certificate.</span></span>
1. <span data-ttu-id="3f160-170">Après avoir installé le certificat, ouvrez « Gérer les certificats d’ordinateur » via le menu Démarrer</span><span class="sxs-lookup"><span data-stu-id="3f160-170">After installing the certificate, open 'Manage computer certificates' through Start menu</span></span>
1. <span data-ttu-id="3f160-171">Sélectionnez le certificat nouvellement installé sous « Personnel » > « Certificats »</span><span class="sxs-lookup"><span data-stu-id="3f160-171">Select the newly installed certificate under 'Personal' -> 'Certificates'</span></span>
1. <span data-ttu-id="3f160-172">Cliquez avec le bouton droit sur le cert, puis sélectionnez « Toutes les tâches > gérer les clés privées... »</span><span class="sxs-lookup"><span data-stu-id="3f160-172">Right click on the cert and select 'All Tasks' -> 'Manage Private Keys…'</span></span> <span data-ttu-id="3f160-173">Option</span><span class="sxs-lookup"><span data-stu-id="3f160-173">Option</span></span>
1. <span data-ttu-id="3f160-174">Dans la boîte de dialogue Autorisations, sélectionnez ajouter une option.</span><span class="sxs-lookup"><span data-stu-id="3f160-174">In the permissions dialog, select add option.</span></span> <span data-ttu-id="3f160-175">Dans la boîte de dialogue de sélection de l’utilisateur, écrivez : « NT Service\GcaHostService » et cliquez sur « OK ».</span><span class="sxs-lookup"><span data-stu-id="3f160-175">In the user selection dialog, write: 'NT Service\GcaHostService' and click 'OK'.</span></span> <span data-ttu-id="3f160-176">Ne cliquez pas sur le bouton « Vérifier les noms ».</span><span class="sxs-lookup"><span data-stu-id="3f160-176">Don't click the 'Check Names' button.</span></span>
1. <span data-ttu-id="3f160-177">Cliquez sur OK dans la boîte de dialogue Autorisations.</span><span class="sxs-lookup"><span data-stu-id="3f160-177">Click okay on the permissions dialog.</span></span> <span data-ttu-id="3f160-178">L’ordinateur de l’agent est maintenant configuré pour que l’agent génère des jetons à l’aide du certificat.</span><span class="sxs-lookup"><span data-stu-id="3f160-178">The agent machine is now configured for agent to generate tokens using the certificate.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="3f160-179">Résolution des problèmes</span><span class="sxs-lookup"><span data-stu-id="3f160-179">Troubleshooting</span></span>
1. <span data-ttu-id="3f160-180">Si une connexion échoue avec l’erreur « 1011 : l’agent du connecteur Graph n’est pas accessible ou hors connexion ». Connectez-vous à l’ordinateur où l’agent est installé et démarrez l’application de l’agent si elle n’est pas déjà en cours d’exécution.</span><span class="sxs-lookup"><span data-stu-id="3f160-180">If a connection fails with the error '1011: The Graph connector agent is not reachable or offline.', log in to the machine where agent is installed and start the agent application if it isn't running already.</span></span> <span data-ttu-id="3f160-181">Si la connexion continue d’échouer, vérifiez que le certificat ou la secret client fourni à l’agent lors de l’inscription n’a pas expiré et qu’il dispose des autorisations requises.</span><span class="sxs-lookup"><span data-stu-id="3f160-181">If the connection continues to fail, verify that the certificate or client secret provided to the agent during registration hasn't expired and has required permissions.</span></span>
