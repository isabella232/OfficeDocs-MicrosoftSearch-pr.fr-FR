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
description: Agent sur place
ms.openlocfilehash: b6303b71910dc300ba5297fde155e538452ef99d
ms.sourcegitcommit: 8ac77db22002d47bb461222b81b7cfc1c15a72fb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/13/2021
ms.locfileid: "58340095"
---
# <a name="microsoft-graph-connector-agent"></a>Agent du connecteur Graph Microsoft

L’utilisation de connecteurs sur site nécessite l’installation du logiciel *d’agent Graph Microsoft.* Il permet un transfert de données sécurisé entre les données sur site et les API de connecteur. Cet article vous guide tout au long de l’installation et de la configuration de l’agent.

## <a name="installation"></a>Installation

Téléchargez la dernière version de l’agent Graph connecteur d’installation et installez le logiciel à l’aide de [https://aka.ms/GCAdownload](https://aka.ms/gcadownload) l’Assistant d’installation. À l’aide de la configuration recommandée de l’ordinateur décrite ci-dessous, le logiciel peut gérer jusqu’à trois connexions. Toutes les connexions au-delà peuvent dégrader les performances de toutes les connexions sur l’agent.

Configuration recommandée :

* Windows 10, Windows Server 2016 R2 et supérieures
* [.NET Core Desktop Runtime 3.1 (x64)](https://dotnet.microsoft.com/download/dotnet-core/3.1)
* 8 cœurs, 3 GHz
* 16 Go de RAM, 2 Go d’espace disque
* Accès réseau à la source de données et à Internet via 443

Après avoir installé l’agent, si les serveurs proxy ou les pare-feu de votre organisation bloquent la communication vers des domaines inconnus, ajoutez ceux ci-dessous à la liste d’accès.

1. *.servicebus.windows.net
2. *.events.data.microsoft.com
3. https://<span>login.microsoftonline.</span> com
4. https://<span>gcs.office.</span> com/
5. https://<span>graph.microsoft.</span> com/

>[!NOTE]
>L’authentification proxy n’est pas prise en charge. Si votre environnement dispose d’un proxy qui nécessite une authentification, notre recommandation consiste à autoriser l’agent du connecteur à contourner le proxy.

## <a name="create-and-configure-an-app-for-the-agent"></a>Créer et configurer une application pour l’agent  

Tout d’abord, connectez-vous et notez que le privilège minimal requis sur le compte est administrateur de recherche. L’agent vous demandera ensuite de fournir des détails d’authentification. Utilisez les étapes ci-dessous pour créer une application et générer les détails d’authentification requis.

### <a name="create-an-app"></a>Créer une application

1. Go to the [Azure portal](https://portal.azure.com) and sign in with admin credentials for the tenant.

2. Accédez à **Azure Active Directory** inscriptions d’applications à partir du volet  ->   de navigation et sélectionnez **Nouvelle inscription.**

3. Fournissez un nom pour l’application et sélectionnez **Enregistrer.**

4. Notez l’ID de l’application (client).

5. Ouvrez **les autorisations d’API** à partir du volet de navigation et **sélectionnez Ajouter une autorisation.**

6. Sélectionnez **Microsoft Graph,** puis les **autorisations d’application.**

7. Recherchez « ExternalItem.ReadWrite.All » et « Directory.Read.All » dans les autorisations, puis sélectionnez **Ajouter des autorisations.**

8. Sélectionnez **Accorder le consentement administrateur pour [TenantName]** et confirmer en sélectionnant **Oui**.

9. Vérifiez que les autorisations sont dans l’état « accordé ».

    :::image type="content" alt-text="Autorisations affichées en vert sur la colonne de droite." source="media/onprem-agent/granted-state.png" lightbox="media/onprem-agent/granted-state.png":::

### <a name="configure-authentication"></a>Configuration de l’authentification

Les détails de l’authentification peuvent être fournis à l’aide d’une secret client ou d’un certificat. Suivez les étapes de votre choix.

#### <a name="configuring-the-client-secret-for-authentication"></a>Configuration de la secret client pour l’authentification

1. Go to the [Azure portal](https://portal.azure.com) and sign in with admin credentials for the tenant.

2. Ouvrez **l’inscription** de l’application à partir du volet de navigation et allez à l’application appropriée. Sous **Gérer,** **sélectionnez Certificats et secrets.**

3. Sélectionnez **Nouvelle secret client** et sélectionnez une période d’expiration pour la secret. Copiez la secret généré et enregistrez-le, car il ne sera pas affiché à nouveau.

4. Utilisez cette question secrète client avec l’ID d’application pour configurer l’agent. Vous ne pouvez pas utiliser d’espaces vides dans **le champ Nom** de l’agent. Les caractères numériques alpha sont acceptés.

#### <a name="using-a-certificate-for-authentication"></a>Utilisation d’un certificat pour l’authentification

Il existe trois étapes simples pour l’utilisation de l’authentification basée sur les certificats :

1. Créer ou obtenir un certificat
2. Télécharger le certificat sur le portail Azure
3. Affecter le certificat à l’agent

##### <a name="step-1-get-a-certificate"></a>Étape 1 : Obtenir un certificat

Le script ci-dessous peut être utilisé pour générer un certificat auto-signé. Votre organisation peut ne pas autoriser les certificats auto-signés. Dans ce cas, utilisez ces informations pour comprendre les exigences et acquérir un certificat conformément aux stratégies de votre organisation.

```powershell
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

##### <a name="step-2-upload-the-certificate-in-the-azure-portal"></a>Étape 2 : Télécharger certificat dans le portail Azure

1. Ouvrez l’application et accédez à la section Certificats et secrets à partir du volet gauche.

2. Sélectionnez **Télécharger certificat et** téléchargez le fichier .cer.

3. Ouvrez **l’inscription de** **l’application et sélectionnez Certificats et secrets** dans le volet de navigation. Copiez l’empreinte numérique du certificat.

:::image type="content" alt-text="Liste des certificats miniatures lorsque certificats et secrets sont sélectionnés dans le volet gauche" source="media/onprem-agent/certificates.png" lightbox="media/onprem-agent/certificates.png":::

##### <a name="step-3-assign-the-certificate-to-the-agent"></a>Étape 3 : Attribuer le certificat à l’agent

Si vous avez utilisé l’exemple de script pour générer un certificat, le fichier PFX se trouve à l’emplacement identifié dans le script.

1. Téléchargez le fichier pfx de certificat sur l’ordinateur de l’agent.

2. Double-cliquez sur le fichier pfx pour lancer la boîte de dialogue d’installation du certificat.

3. Sélectionnez **Ordinateur local pour** l’emplacement du magasin lors de l’installation du certificat.

4. Après avoir installé le certificat, ouvrez **Gérer les certificats d’ordinateur menu Démarrer.**

5. Sélectionnez le certificat nouvellement installé sous  >  **Certificats personnels.**

6. Cliquez avec le bouton droit sur le cert et sélectionnez **l’option** Toutes les tâches  >  **gérer les clés privées.**

7. Dans la boîte de dialogue Autorisations, sélectionnez l’option Ajouter. Dans la boîte de dialogue de sélection de l’utilisateur, écrivez : **NT Service\GcaHostService** et cliquez sur **OK**. Ne cliquez pas sur le **bouton Vérifier les noms.**

8. Cliquez sur OK dans la boîte de dialogue Autorisations. L’ordinateur de l’agent est maintenant configuré pour que l’agent génère des jetons à l’aide du certificat.

## <a name="troubleshooting"></a>Résolution des problèmes

### <a name="installation-failure"></a>Échec de l’installation

Si l’installation échoue, vérifiez les journaux d’installation en exécutant : msiexec /i " <path to msi>\GcaInstaller.msi " /L*V " <destination path> \install.log ». Si les erreurs ne sont pas résolvantes, MicrosoftGraphConnectorsFeedback@service.microsoft.com prise en charge avec les journaux.

### <a name="registration-failure"></a>Échec de l’inscription

Si la signature de l’application de config échoue avec l’erreur « Échec de la signature. Cliquez sur le bouton De se connectez pour essayer à nouveau. » même après la réussite de l’authentification du navigateur, ouvrez services.msc et vérifiez si GcaHostService est en cours d’exécution. Si ce n’est pas le cas, démarrez-le manuellement.

Si le service ne parvient pas à démarrer avec l’erreur « Le service n’a pas commencé en raison d’un échec de connexion », vérifiez si le compte virtuel NT Service\GcaHostService est autorisé à se connecter en tant que service sur l’ordinateur. Consultez [ce lien](/windows/security/threat-protection/security-policy-settings/log-on-as-a-service) pour obtenir des instructions. Si l’option d’ajout d’un utilisateur ou d’un groupe est grisée dans les stratégies locales\Attribution des droits d’utilisateur, cela signifie que l’utilisateur qui essaie d’ajouter ce compte n’a pas de privilèges d’administrateur sur cet ordinateur ou qu’une stratégie de groupe le permet. La stratégie de groupe doit être mise à jour pour permettre au service hôte de se rendre en tant que service.

### <a name="connection-failure"></a>Échec de connexion

Si l’action « Tester la connexion » échoue lors de la création d’une connexion avec l’erreur « Veuillez vérifier le nom d’utilisateur/mot de passe et le chemin d’accès de la source de données » même lorsque le nom d’utilisateur et le mot de passe fournis sont corrects, assurez-vous que le compte d’utilisateur dispose de droits d’accès interactifs à l’ordinateur sur lequel l’agent de connecteur Graph est installé. Reportez-vous à la documentation sur la [gestion des stratégies](/windows/security/threat-protection/security-policy-settings/allow-log-on-locally#policy-management) d’logo pour vérifier les droits d’accès. Assurez-vous également que la source de données et l’ordinateur de l’agent sont sur le même réseau.

Si une connexion échoue avec l’erreur « 1011 : l’agent du connecteur Graph n’est pas accessible ou hors connexion . », connectez-vous à l’ordinateur où l’agent est installé et démarrez l’application agent si elle n’est pas déjà en cours d’exécution. Si la connexion continue d’échouer, vérifiez que le certificat ou la secret client fourni à l’agent lors de l’inscription n’a pas expiré et qu’il dispose des autorisations requises.
