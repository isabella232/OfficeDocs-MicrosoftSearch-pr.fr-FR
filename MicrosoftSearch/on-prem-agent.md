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
# <a name="graph-connector-agent"></a>Agent de connecteur Graph

L’utilisation des connecteurs graphiques local nécessite l’installation du logiciel de *l’agent Graph Connector* . Elle permet un transfert de données sécurisé entre les données locales et les API de connecteur Graph. Cet article vous guide tout au long de l’installation et de la configuration de l’agent.

## <a name="installation"></a>Installation

Téléchargez la dernière version de l’agent de connecteur Graph et installez le logiciel à l' [aide de l'](https://aka.ms/gcadownload) Assistant d’installation. À l’aide de la configuration recommandée de l’ordinateur décrit ci-dessous, le logiciel peut gérer jusqu’à trois connexions. Toutes les connexions au-delà de cela risquent de dégrader les performances de toutes les connexions de l’agent.

Configuration recommandée :

* Windows 10, Windows Server 2016 R2 et versions ultérieures
* [.NET Core Desktop Runtime 3,1 (x64)](https://dotnet.microsoft.com/download/dotnet-core/3.1)
* 8 cœurs, 3 GHz
* 16 Go de RAM, 2 Go d’espace disque
* Accès réseau à la source de données et à Internet via 443

## <a name="create-and-configure-an-app-for-the-agent"></a>Créer et configurer une application pour l’agent  

Avant d’utiliser l’agent, vous devez créer une application et configurer les détails de l’authentification.

### <a name="create-an-app"></a>Créer une application

1. Accédez au [portail Azure](https://portal.azure.com) et connectez-vous avec les informations d’identification d’administrateur pour le client.
2. Accédez à **Azure Active Directory**  ->  ,**inscriptions des applications** dans le volet de navigation, puis sélectionnez **nouvelle inscription**.
3. Fournissez un nom pour l’application, puis sélectionnez **Enregistrer**.
4. Notez l’ID de l’application (client).
5. Ouvrez les autorisations de l' **API** à partir du volet de navigation et sélectionnez **Ajouter une autorisation**.
6. Sélectionnez **Microsoft Graph** , puis **autorisations d’application**.
7. Recherchez « ExternalItem. ReadWrite. All » et « Directory. Read. All » à partir des autorisations, puis sélectionnez **Ajouter des autorisations**.
8. Sélectionnez **accorder le consentement de l’administrateur pour [TenantName]** et confirmez-le en sélectionnant **Oui**.
9. Vérifiez que les autorisations sont dans l’État « accordé ».
     ![Autorisations indiquées comme étant accordées dans la colonne de droite vert sur la droite.](media/onprem-agent/granted-state.png)

### <a name="configure-authentication"></a>Configuration de l’authentification

Les détails d’authentification peuvent être fournis à l’aide d’une clé secrète client ou d’un certificat. Suivez les étapes de votre choix.

#### <a name="configuring-the-client-secret-for-authentication"></a>Configuration de la clé secrète client pour l’authentification

1. Accédez au [portail Azure](https://portal.azure.com) et connectez-vous avec les informations d’identification d’administrateur pour le client.
2. Ouvrez **inscription** de l’application dans le volet de navigation et accédez à l’application appropriée. Sous **gérer**, sélectionnez **certificats et secrets**.
3. Sélectionnez **nouvelle clé secrète client** et sélectionnez une période d’expiration pour la clé secrète. Copiez la clé secrète générée et enregistrez-la, car elle ne s’affichera plus.
4. Utilisez cette clé secrète client avec l’ID de l’application pour configurer l’agent. Vous ne pouvez pas utiliser d’espaces dans le champ **nom** de l’agent. Les caractères numériques alphanumériques sont acceptés.

#### <a name="using-a-certificate-for-authentication"></a>Utilisation d’un certificat pour l’authentification

Il existe trois étapes simples pour utiliser l’authentification basée sur des certificats :

1. Créer ou obtenir un certificat
1. Télécharger le certificat vers le portail Azure
1. Affecter le certificat à l’agent

##### <a name="step-1-get-a-certificate"></a>Étape 1 : obtenir un certificat

Le script ci-dessous peut être utilisé pour générer un certificat auto-signé. Votre organisation ne peut pas autoriser les certificats auto-signés. Dans ce cas, utilisez ces informations pour comprendre les exigences et acquérir un certificat conformément aux stratégies de votre organisation.

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

##### <a name="step-2-upload-the-certificate-in-the-azure-portal"></a>Étape 2 : Télécharger le certificat dans le portail Azure

1. Ouvrir l’application et accéder à la section certificats et secrets à partir du volet gauche
1. Sélectionnez « Télécharger le certificat » et téléchargez le fichier. cer.
1. Ouvrez **inscription** de l’application et sélectionnez **certificats et secrets** dans le volet de navigation. Copiez l’empreinte de certificat.

![Liste des certificats thumbrint lorsque l’option certificats et secrets est sélectionnée dans le volet de gauche](media/onprem-agent/certificates.png)

##### <a name="step-3-assign-the-certificate-to-the-agent"></a>Étape 3 : assigner le certificat à l’agent

Si vous avez utilisé l’exemple de script pour générer un certificat, le fichier PFX se trouve à l’emplacement identifié dans le script.

1. Téléchargez le fichier PFX de certificat sur l’ordinateur de l’agent.
1. Double-cliquez sur le fichier PFX pour lancer la boîte de dialogue d’installation du certificat.
1. Sélectionnez « ordinateur local » pour l’emplacement du magasin lors de l’installation du certificat.
1. Après avoir installé le certificat, ouvrez « gérer les certificats d’ordinateur » via le menu Démarrer.
1. Sélectionnez le certificat nouvellement installé sous « personnel »-> « certificats »
1. Cliquez avec le bouton droit sur le certificat, puis sélectionnez « toutes les tâches »-> « gérer les clés privées... » Option
1. Dans la boîte de dialogue autorisations, sélectionnez Ajouter une option. Dans la boîte de dialogue de sélection de l’utilisateur, écrivez : « NT Service\GcaHostService », puis cliquez sur « OK ». Ne cliquez pas sur le bouton « vérifier les noms ».
1. Cliquez sur OK dans la boîte de dialogue autorisations. L’ordinateur agent est maintenant configuré pour que l’agent génère des jetons à l’aide du certificat.
