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
ms.openlocfilehash: 763904f8dd96c5db8b0633e36795443502afe7d0
ms.sourcegitcommit: 0ed8ec8b3c4e0f5f669005081fd8b2219f07b4f0
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/25/2020
ms.locfileid: "49420832"
---
# <a name="graph-connector-agent"></a><span data-ttu-id="f7d93-103">Agent de connecteur Graph</span><span class="sxs-lookup"><span data-stu-id="f7d93-103">Graph connector agent</span></span>

<span data-ttu-id="f7d93-104">L’utilisation des connecteurs graphiques local nécessite l’installation du logiciel de *l’agent Graph Connector* .</span><span class="sxs-lookup"><span data-stu-id="f7d93-104">Using on-prem Graph connectors require you to install *Graph connector agent* software.</span></span> <span data-ttu-id="f7d93-105">Elle permet un transfert de données sécurisé entre les données locales et les API de connecteur Graph.</span><span class="sxs-lookup"><span data-stu-id="f7d93-105">It allows for secure data transfer between on-premises data and the Graph connector APIs.</span></span> <span data-ttu-id="f7d93-106">Cet article vous guide tout au long de l’installation et de la configuration de l’agent.</span><span class="sxs-lookup"><span data-stu-id="f7d93-106">This article guides you through the installing and configuring the agent.</span></span>

## <a name="installation"></a><span data-ttu-id="f7d93-107">Installation</span><span class="sxs-lookup"><span data-stu-id="f7d93-107">Installation</span></span>

<span data-ttu-id="f7d93-108">Téléchargez la dernière version de l’agent de connecteur Graph et installez le logiciel à l' [aide de l'](https://aka.ms/gcadownload) Assistant d’installation.</span><span class="sxs-lookup"><span data-stu-id="f7d93-108">Download the latest version of Graph connector agent [here](https://aka.ms/gcadownload) and install the software using the installation wizard.</span></span> <span data-ttu-id="f7d93-109">À l’aide de la configuration recommandée de l’ordinateur décrit ci-dessous, le logiciel peut gérer jusqu’à trois connexions.</span><span class="sxs-lookup"><span data-stu-id="f7d93-109">Using the recommended configuration of the machine described below, the software can handle up to three connections.</span></span> <span data-ttu-id="f7d93-110">Toutes les connexions au-delà de cela risquent de dégrader les performances de toutes les connexions de l’agent.</span><span class="sxs-lookup"><span data-stu-id="f7d93-110">Any connections beyond that might degrade the performance of all connections on the agent.</span></span>

<span data-ttu-id="f7d93-111">Configuration recommandée :</span><span class="sxs-lookup"><span data-stu-id="f7d93-111">Recommended configuration:</span></span>

* <span data-ttu-id="f7d93-112">Windows 10, Windows Server 2016 R2 et versions ultérieures</span><span class="sxs-lookup"><span data-stu-id="f7d93-112">Windows 10, Windows Server 2016 R2 and above</span></span>
* <span data-ttu-id="f7d93-113">8 cœurs, 3 GHz</span><span class="sxs-lookup"><span data-stu-id="f7d93-113">8 cores, 3 GHz</span></span>
* <span data-ttu-id="f7d93-114">16 Go de RAM, 2 Go d’espace disque</span><span class="sxs-lookup"><span data-stu-id="f7d93-114">16 GB RAM, 2 GB Disk Space</span></span>
* <span data-ttu-id="f7d93-115">Accès réseau à la source de données et à Internet via 443</span><span class="sxs-lookup"><span data-stu-id="f7d93-115">Network access to data source and internet through 443</span></span>

## <a name="create-and-configure-an-app-for-the-agent"></a><span data-ttu-id="f7d93-116">Créer et configurer une application pour l’agent</span><span class="sxs-lookup"><span data-stu-id="f7d93-116">Create and configure an App for the agent</span></span>  

<span data-ttu-id="f7d93-117">Avant d’utiliser l’agent, vous devez créer une application et configurer les détails de l’authentification.</span><span class="sxs-lookup"><span data-stu-id="f7d93-117">Before using the agent, you must create an app and configure the authentication details.</span></span>

### <a name="create-an-app"></a><span data-ttu-id="f7d93-118">Créer une application</span><span class="sxs-lookup"><span data-stu-id="f7d93-118">Create an app</span></span>

1. <span data-ttu-id="f7d93-119">Accédez au [portail Azure](https://portal.azure.com) et connectez-vous avec les informations d’identification d’administrateur pour le client.</span><span class="sxs-lookup"><span data-stu-id="f7d93-119">Go to the [Azure portal](https://portal.azure.com) and sign in with admin credentials for the tenant.</span></span>
2. <span data-ttu-id="f7d93-120">Accédez à **Azure Active Directory**  ->  ,**inscriptions des applications** dans le volet de navigation, puis sélectionnez **nouvelle inscription**.</span><span class="sxs-lookup"><span data-stu-id="f7d93-120">Navigate to **Azure Active Directory** -> **App registrations** from the navigation pane and select **New registration**.</span></span>
3. <span data-ttu-id="f7d93-121">Fournissez un nom pour l’application, puis sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="f7d93-121">Provide a name for the app and select **Register**.</span></span>
4. <span data-ttu-id="f7d93-122">Notez l’ID de l’application (client).</span><span class="sxs-lookup"><span data-stu-id="f7d93-122">Make a note of the Application (client) ID.</span></span>
5. <span data-ttu-id="f7d93-123">Ouvrez les autorisations de l' **API** à partir du volet de navigation et sélectionnez **Ajouter une autorisation**.</span><span class="sxs-lookup"><span data-stu-id="f7d93-123">Open **API permissions** from the navigation pane and select **Add a permission**.</span></span>
6. <span data-ttu-id="f7d93-124">Sélectionnez **Microsoft Graph** , puis **autorisations d’application**.</span><span class="sxs-lookup"><span data-stu-id="f7d93-124">Select **Microsoft Graph** and then **Application permissions**.</span></span>
7. <span data-ttu-id="f7d93-125">Recherchez « ExternalItem. ReadWrite. All » et « Directory. Read. All » à partir des autorisations, puis sélectionnez **Ajouter des autorisations**.</span><span class="sxs-lookup"><span data-stu-id="f7d93-125">Search for "ExternalItem.ReadWrite.All" and "Directory.Read.All" from the permissions and select **Add permissions**.</span></span>
8. <span data-ttu-id="f7d93-126">Sélectionnez **accorder le consentement de l’administrateur pour [TenantName]** et confirmez-le en sélectionnant **Oui**.</span><span class="sxs-lookup"><span data-stu-id="f7d93-126">Select **Grant admin consent for [TenantName]** and confirm by selecting **Yes**.</span></span>
9. <span data-ttu-id="f7d93-127">Vérifiez que les autorisations sont dans l’État « accordé ».</span><span class="sxs-lookup"><span data-stu-id="f7d93-127">Check that the permissions are in the "granted" state.</span></span>
     <span data-ttu-id="f7d93-128">![Autorisations indiquées comme étant accordées dans la colonne de droite vert sur la droite.](media/onprem-agent/granted-state.png)</span><span class="sxs-lookup"><span data-stu-id="f7d93-128">![Permissions shown as granted in green on right hand column.](media/onprem-agent/granted-state.png)</span></span>

### <a name="configure-authentication"></a><span data-ttu-id="f7d93-129">Configuration de l’authentification</span><span class="sxs-lookup"><span data-stu-id="f7d93-129">Configure Authentication</span></span>

<span data-ttu-id="f7d93-130">Les détails d’authentification peuvent être fournis à l’aide d’une clé secrète client ou d’un certificat.</span><span class="sxs-lookup"><span data-stu-id="f7d93-130">Authentication details can be provided using a client secret or a certificate.</span></span> <span data-ttu-id="f7d93-131">Suivez les étapes de votre choix.</span><span class="sxs-lookup"><span data-stu-id="f7d93-131">Follow the steps for your choice.</span></span>

#### <a name="configuring-the-client-secret-for-authentication"></a><span data-ttu-id="f7d93-132">Configuration de la clé secrète client pour l’authentification</span><span class="sxs-lookup"><span data-stu-id="f7d93-132">Configuring the client secret for authentication</span></span>

1. <span data-ttu-id="f7d93-133">Accédez au [portail Azure](https://portal.azure.com) et connectez-vous avec les informations d’identification d’administrateur pour le client.</span><span class="sxs-lookup"><span data-stu-id="f7d93-133">Go to the [Azure portal](https://portal.azure.com) and sign in with admin credentials for the tenant.</span></span>
2. <span data-ttu-id="f7d93-134">Ouvrez **inscription** de l’application dans le volet de navigation et accédez à l’application appropriée.</span><span class="sxs-lookup"><span data-stu-id="f7d93-134">Open **App Registration** from the navigation pane and go to the appropriate App.</span></span> <span data-ttu-id="f7d93-135">Sous **gérer**, sélectionnez **certificats et secrets**.</span><span class="sxs-lookup"><span data-stu-id="f7d93-135">Under **Manage**, select **Certificates and secrets**.</span></span>
3. <span data-ttu-id="f7d93-136">Sélectionnez **nouvelle clé secrète client** et sélectionnez une période d’expiration pour la clé secrète.</span><span class="sxs-lookup"><span data-stu-id="f7d93-136">Select **New Client secret** and select an expiry period for the secret.</span></span> <span data-ttu-id="f7d93-137">Copiez la clé secrète générée et enregistrez-la, car elle ne s’affichera plus.</span><span class="sxs-lookup"><span data-stu-id="f7d93-137">Copy the generated secret and save it because it won't be shown again.</span></span>
4. <span data-ttu-id="f7d93-138">Utilisez cette clé secrète client avec l’ID de l’application pour configurer l’agent.</span><span class="sxs-lookup"><span data-stu-id="f7d93-138">Use this Client secret along with the Application ID to configure the agent.</span></span> <span data-ttu-id="f7d93-139">Vous ne pouvez pas utiliser d’espaces dans le champ **nom** de l’agent.</span><span class="sxs-lookup"><span data-stu-id="f7d93-139">You cannot use blank spaces in the **Name** field of the agent.</span></span> <span data-ttu-id="f7d93-140">Les caractères numériques alphanumériques sont acceptés.</span><span class="sxs-lookup"><span data-stu-id="f7d93-140">Alpha numeric characters are accepted.</span></span>

#### <a name="using-a-certificate-for-authentication"></a><span data-ttu-id="f7d93-141">Utilisation d’un certificat pour l’authentification</span><span class="sxs-lookup"><span data-stu-id="f7d93-141">Using a certificate for authentication</span></span>

<span data-ttu-id="f7d93-142">Il existe trois étapes simples pour utiliser l’authentification basée sur des certificats :</span><span class="sxs-lookup"><span data-stu-id="f7d93-142">There are three simple steps for using certificate-based authentication:</span></span>

1. <span data-ttu-id="f7d93-143">Créer ou obtenir un certificat</span><span class="sxs-lookup"><span data-stu-id="f7d93-143">Create or obtain a certificate</span></span>
1. <span data-ttu-id="f7d93-144">Télécharger le certificat vers le portail Azure</span><span class="sxs-lookup"><span data-stu-id="f7d93-144">Upload the certificate to the Azure portal</span></span>
1. <span data-ttu-id="f7d93-145">Affecter le certificat à l’agent</span><span class="sxs-lookup"><span data-stu-id="f7d93-145">Assign the certificate to the agent</span></span>

##### <a name="step-1-get-a-certificate"></a><span data-ttu-id="f7d93-146">Étape 1 : obtenir un certificat</span><span class="sxs-lookup"><span data-stu-id="f7d93-146">Step 1: Get a certificate</span></span>

<span data-ttu-id="f7d93-147">Le script ci-dessous peut être utilisé pour générer un certificat auto-signé.</span><span class="sxs-lookup"><span data-stu-id="f7d93-147">The script below can be used to generate a self-signed certificate.</span></span> <span data-ttu-id="f7d93-148">Votre organisation ne peut pas autoriser les certificats auto-signés.</span><span class="sxs-lookup"><span data-stu-id="f7d93-148">Your organization may not allow self-signed certificates.</span></span> <span data-ttu-id="f7d93-149">Dans ce cas, utilisez ces informations pour comprendre les exigences et acquérir un certificat conformément aux stratégies de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="f7d93-149">In that case, use this information to understand the requirements and acquire a certificate in accordance to your organization's policies.</span></span>

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

##### <a name="step-2-upload-the-certificate-in-the-azure-portal"></a><span data-ttu-id="f7d93-150">Étape 2 : Télécharger le certificat dans le portail Azure</span><span class="sxs-lookup"><span data-stu-id="f7d93-150">Step 2: Upload the certificate in the Azure portal</span></span>

1. <span data-ttu-id="f7d93-151">Ouvrir l’application et accéder à la section certificats et secrets à partir du volet gauche</span><span class="sxs-lookup"><span data-stu-id="f7d93-151">Open the application and navigate to certificates and secrets section from left pane</span></span>
1. <span data-ttu-id="f7d93-152">Sélectionnez « Télécharger le certificat » et téléchargez le fichier. cer.</span><span class="sxs-lookup"><span data-stu-id="f7d93-152">Select 'Upload certificate' and upload the .cer file</span></span>
1. <span data-ttu-id="f7d93-153">Ouvrez **inscription** de l’application et sélectionnez **certificats et secrets** dans le volet de navigation.</span><span class="sxs-lookup"><span data-stu-id="f7d93-153">Open **App registration** and select **Certificates and secrets** from the navigation pane.</span></span> <span data-ttu-id="f7d93-154">Copiez l’empreinte de certificat.</span><span class="sxs-lookup"><span data-stu-id="f7d93-154">Copy the certificate thumbprint.</span></span>

![Liste des certificats thumbrint lorsque l’option certificats et secrets est sélectionnée dans le volet de gauche](media/onprem-agent/certificates.png)

##### <a name="step-3-assign-the-certificate-to-the-agent"></a><span data-ttu-id="f7d93-156">Étape 3 : assigner le certificat à l’agent</span><span class="sxs-lookup"><span data-stu-id="f7d93-156">Step 3: Assign the certificate to the agent</span></span>

<span data-ttu-id="f7d93-157">Si vous avez utilisé l’exemple de script pour générer un certificat, le fichier PFX se trouve à l’emplacement identifié dans le script.</span><span class="sxs-lookup"><span data-stu-id="f7d93-157">If you used the sample script to generate a certificate, the PFX file can be found in the location identified in the script.</span></span>

1. <span data-ttu-id="f7d93-158">Téléchargez le fichier PFX de certificat sur l’ordinateur de l’agent.</span><span class="sxs-lookup"><span data-stu-id="f7d93-158">Download the certificate pfx file onto the Agent machine.</span></span>
1. <span data-ttu-id="f7d93-159">Double-cliquez sur le fichier PFX pour lancer la boîte de dialogue d’installation du certificat.</span><span class="sxs-lookup"><span data-stu-id="f7d93-159">Double-click the pfx file to launch the certificate installation dialog.</span></span>
1. <span data-ttu-id="f7d93-160">Sélectionnez « ordinateur local » pour l’emplacement du magasin lors de l’installation du certificat.</span><span class="sxs-lookup"><span data-stu-id="f7d93-160">Select 'Local Machine' for store location while installing the certificate.</span></span>
1. <span data-ttu-id="f7d93-161">Après avoir installé le certificat, ouvrez « gérer les certificats d’ordinateur » via le menu Démarrer.</span><span class="sxs-lookup"><span data-stu-id="f7d93-161">After installing the certificate, open 'Manage computer certificates' through Start menu</span></span>
1. <span data-ttu-id="f7d93-162">Sélectionnez le certificat nouvellement installé sous « personnel »-> « certificats »</span><span class="sxs-lookup"><span data-stu-id="f7d93-162">Select the newly installed certificate under 'Personal' -> 'Certificates'</span></span>
1. <span data-ttu-id="f7d93-163">Cliquez avec le bouton droit sur le certificat, puis sélectionnez « toutes les tâches »-> « gérer les clés privées... »</span><span class="sxs-lookup"><span data-stu-id="f7d93-163">Right click on the cert and select 'All Tasks' -> 'Manage Private Keys…'</span></span> <span data-ttu-id="f7d93-164">Option</span><span class="sxs-lookup"><span data-stu-id="f7d93-164">Option</span></span>
1. <span data-ttu-id="f7d93-165">Dans la boîte de dialogue autorisations, sélectionnez Ajouter une option.</span><span class="sxs-lookup"><span data-stu-id="f7d93-165">In the permissions dialog, select add option.</span></span> <span data-ttu-id="f7d93-166">Dans la boîte de dialogue de sélection de l’utilisateur, écrivez : « NT Service\GcaHostService », puis cliquez sur « OK ».</span><span class="sxs-lookup"><span data-stu-id="f7d93-166">In the user selection dialog, write: 'NT Service\GcaHostService' and click 'OK'.</span></span> <span data-ttu-id="f7d93-167">Ne cliquez pas sur le bouton « vérifier les noms ».</span><span class="sxs-lookup"><span data-stu-id="f7d93-167">Don't click the 'Check Names' button.</span></span>
1. <span data-ttu-id="f7d93-168">Cliquez sur OK dans la boîte de dialogue autorisations.</span><span class="sxs-lookup"><span data-stu-id="f7d93-168">Click okay on the permissions dialog.</span></span> <span data-ttu-id="f7d93-169">L’ordinateur agent est maintenant configuré pour que l’agent génère des jetons à l’aide du certificat.</span><span class="sxs-lookup"><span data-stu-id="f7d93-169">The agent machine is now configured for agent to generate tokens using the certificate.</span></span>
