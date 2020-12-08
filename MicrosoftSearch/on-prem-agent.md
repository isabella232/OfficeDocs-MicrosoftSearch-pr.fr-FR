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
description: Agent local
ms.openlocfilehash: 5dbca392fefdcc11de253fd244cc98a6adcee68a
ms.sourcegitcommit: e8d770fa72ac83e074a5de57098cb55d06d8db07
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/08/2020
ms.locfileid: "49588366"
---
# <a name="graph-connector-agent"></a><span data-ttu-id="43961-103">Agent de connecteur Graph</span><span class="sxs-lookup"><span data-stu-id="43961-103">Graph connector agent</span></span>

<span data-ttu-id="43961-104">L’utilisation des connecteurs graphiques local nécessite l’installation du logiciel de *l’agent Graph Connector* .</span><span class="sxs-lookup"><span data-stu-id="43961-104">Using on-prem Graph connectors require you to install *Graph connector agent* software.</span></span> <span data-ttu-id="43961-105">Elle permet un transfert de données sécurisé entre les données locales et les API de connecteur Graph.</span><span class="sxs-lookup"><span data-stu-id="43961-105">It allows for secure data transfer between on-premises data and the Graph connector APIs.</span></span> <span data-ttu-id="43961-106">Cet article vous guide tout au long de l’installation et de la configuration de l’agent.</span><span class="sxs-lookup"><span data-stu-id="43961-106">This article guides you through the installing and configuring the agent.</span></span>

## <a name="installation"></a><span data-ttu-id="43961-107">Installation</span><span class="sxs-lookup"><span data-stu-id="43961-107">Installation</span></span>

<span data-ttu-id="43961-108">Téléchargez la dernière version de l’agent de connecteur Graph et installez le logiciel à l' [aide de l'](https://aka.ms/gcadownload) Assistant d’installation.</span><span class="sxs-lookup"><span data-stu-id="43961-108">Download the latest version of Graph connector agent [here](https://aka.ms/gcadownload) and install the software using the installation wizard.</span></span> <span data-ttu-id="43961-109">À l’aide de la configuration recommandée de l’ordinateur décrit ci-dessous, le logiciel peut gérer jusqu’à trois connexions.</span><span class="sxs-lookup"><span data-stu-id="43961-109">Using the recommended configuration of the machine described below, the software can handle up to three connections.</span></span> <span data-ttu-id="43961-110">Toutes les connexions au-delà de cela risquent de dégrader les performances de toutes les connexions de l’agent.</span><span class="sxs-lookup"><span data-stu-id="43961-110">Any connections beyond that might degrade the performance of all connections on the agent.</span></span>

<span data-ttu-id="43961-111">Configuration recommandée :</span><span class="sxs-lookup"><span data-stu-id="43961-111">Recommended configuration:</span></span>

* <span data-ttu-id="43961-112">Windows 10, Windows Server 2016 R2 et versions ultérieures</span><span class="sxs-lookup"><span data-stu-id="43961-112">Windows 10, Windows Server 2016 R2 and above</span></span>
* [<span data-ttu-id="43961-113">.NET Core Desktop Runtime 3,1 (x64)</span><span class="sxs-lookup"><span data-stu-id="43961-113">.NET Core Desktop Runtime 3.1 (x64)</span></span>](https://dotnet.microsoft.com/download/dotnet-core/3.1)
* <span data-ttu-id="43961-114">8 cœurs, 3 GHz</span><span class="sxs-lookup"><span data-stu-id="43961-114">8 cores, 3 GHz</span></span>
* <span data-ttu-id="43961-115">16 Go de RAM, 2 Go d’espace disque</span><span class="sxs-lookup"><span data-stu-id="43961-115">16 GB RAM, 2 GB Disk Space</span></span>
* <span data-ttu-id="43961-116">Accès réseau à la source de données et à Internet via 443</span><span class="sxs-lookup"><span data-stu-id="43961-116">Network access to data source and internet through 443</span></span>

## <a name="create-and-configure-an-app-for-the-agent"></a><span data-ttu-id="43961-117">Créer et configurer une application pour l’agent</span><span class="sxs-lookup"><span data-stu-id="43961-117">Create and configure an App for the agent</span></span>  

<span data-ttu-id="43961-118">Avant d’utiliser l’agent, vous devez créer une application et configurer les détails de l’authentification.</span><span class="sxs-lookup"><span data-stu-id="43961-118">Before using the agent, you must create an app and configure the authentication details.</span></span>

### <a name="create-an-app"></a><span data-ttu-id="43961-119">Créer une application</span><span class="sxs-lookup"><span data-stu-id="43961-119">Create an app</span></span>

1. <span data-ttu-id="43961-120">Accédez au [portail Azure](https://portal.azure.com) et connectez-vous avec les informations d’identification d’administrateur pour le client.</span><span class="sxs-lookup"><span data-stu-id="43961-120">Go to the [Azure portal](https://portal.azure.com) and sign in with admin credentials for the tenant.</span></span>
2. <span data-ttu-id="43961-121">Accédez à **Azure Active Directory**  ->  ,**inscriptions des applications** dans le volet de navigation, puis sélectionnez **nouvelle inscription**.</span><span class="sxs-lookup"><span data-stu-id="43961-121">Navigate to **Azure Active Directory** -> **App registrations** from the navigation pane and select **New registration**.</span></span>
3. <span data-ttu-id="43961-122">Fournissez un nom pour l’application, puis sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="43961-122">Provide a name for the app and select **Register**.</span></span>
4. <span data-ttu-id="43961-123">Notez l’ID de l’application (client).</span><span class="sxs-lookup"><span data-stu-id="43961-123">Make a note of the Application (client) ID.</span></span>
5. <span data-ttu-id="43961-124">Ouvrez les autorisations de l' **API** à partir du volet de navigation et sélectionnez **Ajouter une autorisation**.</span><span class="sxs-lookup"><span data-stu-id="43961-124">Open **API permissions** from the navigation pane and select **Add a permission**.</span></span>
6. <span data-ttu-id="43961-125">Sélectionnez **Microsoft Graph** , puis **autorisations d’application**.</span><span class="sxs-lookup"><span data-stu-id="43961-125">Select **Microsoft Graph** and then **Application permissions**.</span></span>
7. <span data-ttu-id="43961-126">Recherchez « ExternalItem. ReadWrite. All » et « Directory. Read. All » à partir des autorisations, puis sélectionnez **Ajouter des autorisations**.</span><span class="sxs-lookup"><span data-stu-id="43961-126">Search for "ExternalItem.ReadWrite.All" and "Directory.Read.All" from the permissions and select **Add permissions**.</span></span>
8. <span data-ttu-id="43961-127">Sélectionnez **accorder le consentement de l’administrateur pour [TenantName]** et confirmez-le en sélectionnant **Oui**.</span><span class="sxs-lookup"><span data-stu-id="43961-127">Select **Grant admin consent for [TenantName]** and confirm by selecting **Yes**.</span></span>
9. <span data-ttu-id="43961-128">Vérifiez que les autorisations sont dans l’État « accordé ».</span><span class="sxs-lookup"><span data-stu-id="43961-128">Check that the permissions are in the "granted" state.</span></span>
     <span data-ttu-id="43961-129">![Autorisations indiquées comme étant accordées dans la colonne de droite vert sur la droite.](media/onprem-agent/granted-state.png)</span><span class="sxs-lookup"><span data-stu-id="43961-129">![Permissions shown as granted in green on right hand column.](media/onprem-agent/granted-state.png)</span></span>

### <a name="configure-authentication"></a><span data-ttu-id="43961-130">Configuration de l’authentification</span><span class="sxs-lookup"><span data-stu-id="43961-130">Configure Authentication</span></span>

<span data-ttu-id="43961-131">Les détails d’authentification peuvent être fournis à l’aide d’une clé secrète client ou d’un certificat.</span><span class="sxs-lookup"><span data-stu-id="43961-131">Authentication details can be provided using a client secret or a certificate.</span></span> <span data-ttu-id="43961-132">Suivez les étapes de votre choix.</span><span class="sxs-lookup"><span data-stu-id="43961-132">Follow the steps for your choice.</span></span>

#### <a name="configuring-the-client-secret-for-authentication"></a><span data-ttu-id="43961-133">Configuration de la clé secrète client pour l’authentification</span><span class="sxs-lookup"><span data-stu-id="43961-133">Configuring the client secret for authentication</span></span>

1. <span data-ttu-id="43961-134">Accédez au [portail Azure](https://portal.azure.com) et connectez-vous avec les informations d’identification d’administrateur pour le client.</span><span class="sxs-lookup"><span data-stu-id="43961-134">Go to the [Azure portal](https://portal.azure.com) and sign in with admin credentials for the tenant.</span></span>
2. <span data-ttu-id="43961-135">Ouvrez **inscription** de l’application dans le volet de navigation et accédez à l’application appropriée.</span><span class="sxs-lookup"><span data-stu-id="43961-135">Open **App Registration** from the navigation pane and go to the appropriate App.</span></span> <span data-ttu-id="43961-136">Sous **gérer**, sélectionnez **certificats et secrets**.</span><span class="sxs-lookup"><span data-stu-id="43961-136">Under **Manage**, select **Certificates and secrets**.</span></span>
3. <span data-ttu-id="43961-137">Sélectionnez **nouvelle clé secrète client** et sélectionnez une période d’expiration pour la clé secrète.</span><span class="sxs-lookup"><span data-stu-id="43961-137">Select **New Client secret** and select an expiry period for the secret.</span></span> <span data-ttu-id="43961-138">Copiez la clé secrète générée et enregistrez-la, car elle ne s’affichera plus.</span><span class="sxs-lookup"><span data-stu-id="43961-138">Copy the generated secret and save it because it won't be shown again.</span></span>
4. <span data-ttu-id="43961-139">Utilisez cette clé secrète client avec l’ID de l’application pour configurer l’agent.</span><span class="sxs-lookup"><span data-stu-id="43961-139">Use this Client secret along with the Application ID to configure the agent.</span></span> <span data-ttu-id="43961-140">Vous ne pouvez pas utiliser d’espaces dans le champ **nom** de l’agent.</span><span class="sxs-lookup"><span data-stu-id="43961-140">You cannot use blank spaces in the **Name** field of the agent.</span></span> <span data-ttu-id="43961-141">Les caractères numériques alphanumériques sont acceptés.</span><span class="sxs-lookup"><span data-stu-id="43961-141">Alpha numeric characters are accepted.</span></span>

#### <a name="using-a-certificate-for-authentication"></a><span data-ttu-id="43961-142">Utilisation d’un certificat pour l’authentification</span><span class="sxs-lookup"><span data-stu-id="43961-142">Using a certificate for authentication</span></span>

<span data-ttu-id="43961-143">Il existe trois étapes simples pour utiliser l’authentification basée sur des certificats :</span><span class="sxs-lookup"><span data-stu-id="43961-143">There are three simple steps for using certificate-based authentication:</span></span>

1. <span data-ttu-id="43961-144">Créer ou obtenir un certificat</span><span class="sxs-lookup"><span data-stu-id="43961-144">Create or obtain a certificate</span></span>
1. <span data-ttu-id="43961-145">Télécharger le certificat vers le portail Azure</span><span class="sxs-lookup"><span data-stu-id="43961-145">Upload the certificate to the Azure portal</span></span>
1. <span data-ttu-id="43961-146">Affecter le certificat à l’agent</span><span class="sxs-lookup"><span data-stu-id="43961-146">Assign the certificate to the agent</span></span>

##### <a name="step-1-get-a-certificate"></a><span data-ttu-id="43961-147">Étape 1 : obtenir un certificat</span><span class="sxs-lookup"><span data-stu-id="43961-147">Step 1: Get a certificate</span></span>

<span data-ttu-id="43961-148">Le script ci-dessous peut être utilisé pour générer un certificat auto-signé.</span><span class="sxs-lookup"><span data-stu-id="43961-148">The script below can be used to generate a self-signed certificate.</span></span> <span data-ttu-id="43961-149">Votre organisation ne peut pas autoriser les certificats auto-signés.</span><span class="sxs-lookup"><span data-stu-id="43961-149">Your organization may not allow self-signed certificates.</span></span> <span data-ttu-id="43961-150">Dans ce cas, utilisez ces informations pour comprendre les exigences et acquérir un certificat conformément aux stratégies de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="43961-150">In that case, use this information to understand the requirements and acquire a certificate in accordance to your organization's policies.</span></span>

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

##### <a name="step-2-upload-the-certificate-in-the-azure-portal"></a><span data-ttu-id="43961-151">Étape 2 : Télécharger le certificat dans le portail Azure</span><span class="sxs-lookup"><span data-stu-id="43961-151">Step 2: Upload the certificate in the Azure portal</span></span>

1. <span data-ttu-id="43961-152">Ouvrir l’application et accéder à la section certificats et secrets à partir du volet gauche</span><span class="sxs-lookup"><span data-stu-id="43961-152">Open the application and navigate to certificates and secrets section from left pane</span></span>
1. <span data-ttu-id="43961-153">Sélectionnez « Télécharger le certificat » et téléchargez le fichier. cer.</span><span class="sxs-lookup"><span data-stu-id="43961-153">Select 'Upload certificate' and upload the .cer file</span></span>
1. <span data-ttu-id="43961-154">Ouvrez **inscription** de l’application et sélectionnez **certificats et secrets** dans le volet de navigation.</span><span class="sxs-lookup"><span data-stu-id="43961-154">Open **App registration** and select **Certificates and secrets** from the navigation pane.</span></span> <span data-ttu-id="43961-155">Copiez l’empreinte de certificat.</span><span class="sxs-lookup"><span data-stu-id="43961-155">Copy the certificate thumbprint.</span></span>

![Liste des certificats thumbrint lorsque l’option certificats et secrets est sélectionnée dans le volet de gauche](media/onprem-agent/certificates.png)

##### <a name="step-3-assign-the-certificate-to-the-agent"></a><span data-ttu-id="43961-157">Étape 3 : assigner le certificat à l’agent</span><span class="sxs-lookup"><span data-stu-id="43961-157">Step 3: Assign the certificate to the agent</span></span>

<span data-ttu-id="43961-158">Si vous avez utilisé l’exemple de script pour générer un certificat, le fichier PFX se trouve à l’emplacement identifié dans le script.</span><span class="sxs-lookup"><span data-stu-id="43961-158">If you used the sample script to generate a certificate, the PFX file can be found in the location identified in the script.</span></span>

1. <span data-ttu-id="43961-159">Téléchargez le fichier PFX de certificat sur l’ordinateur de l’agent.</span><span class="sxs-lookup"><span data-stu-id="43961-159">Download the certificate pfx file onto the Agent machine.</span></span>
1. <span data-ttu-id="43961-160">Double-cliquez sur le fichier PFX pour lancer la boîte de dialogue d’installation du certificat.</span><span class="sxs-lookup"><span data-stu-id="43961-160">Double-click the pfx file to launch the certificate installation dialog.</span></span>
1. <span data-ttu-id="43961-161">Sélectionnez « ordinateur local » pour l’emplacement du magasin lors de l’installation du certificat.</span><span class="sxs-lookup"><span data-stu-id="43961-161">Select 'Local Machine' for store location while installing the certificate.</span></span>
1. <span data-ttu-id="43961-162">Après avoir installé le certificat, ouvrez « gérer les certificats d’ordinateur » via le menu Démarrer.</span><span class="sxs-lookup"><span data-stu-id="43961-162">After installing the certificate, open 'Manage computer certificates' through Start menu</span></span>
1. <span data-ttu-id="43961-163">Sélectionnez le certificat nouvellement installé sous « personnel »-> « certificats »</span><span class="sxs-lookup"><span data-stu-id="43961-163">Select the newly installed certificate under 'Personal' -> 'Certificates'</span></span>
1. <span data-ttu-id="43961-164">Cliquez avec le bouton droit sur le certificat, puis sélectionnez « toutes les tâches »-> « gérer les clés privées... »</span><span class="sxs-lookup"><span data-stu-id="43961-164">Right click on the cert and select 'All Tasks' -> 'Manage Private Keys…'</span></span> <span data-ttu-id="43961-165">Option</span><span class="sxs-lookup"><span data-stu-id="43961-165">Option</span></span>
1. <span data-ttu-id="43961-166">Dans la boîte de dialogue autorisations, sélectionnez Ajouter une option.</span><span class="sxs-lookup"><span data-stu-id="43961-166">In the permissions dialog, select add option.</span></span> <span data-ttu-id="43961-167">Dans la boîte de dialogue de sélection de l’utilisateur, écrivez : « NT Service\GcaHostService », puis cliquez sur « OK ».</span><span class="sxs-lookup"><span data-stu-id="43961-167">In the user selection dialog, write: 'NT Service\GcaHostService' and click 'OK'.</span></span> <span data-ttu-id="43961-168">Ne cliquez pas sur le bouton « vérifier les noms ».</span><span class="sxs-lookup"><span data-stu-id="43961-168">Don't click the 'Check Names' button.</span></span>
1. <span data-ttu-id="43961-169">Cliquez sur OK dans la boîte de dialogue autorisations.</span><span class="sxs-lookup"><span data-stu-id="43961-169">Click okay on the permissions dialog.</span></span> <span data-ttu-id="43961-170">L’ordinateur agent est maintenant configuré pour que l’agent génère des jetons à l’aide du certificat.</span><span class="sxs-lookup"><span data-stu-id="43961-170">The agent machine is now configured for agent to generate tokens using the certificate.</span></span>
