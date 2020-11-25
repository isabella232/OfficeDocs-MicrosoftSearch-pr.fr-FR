---
title: Sur l’agent local
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
ms.openlocfilehash: 487c5b179e09fd99fa26ae7a237e89ca38b7be4d
ms.sourcegitcommit: 69a1c544cc8db364991cb58d7818d7158ff108b8
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/25/2020
ms.locfileid: "49408941"
---
# <a name="on-prem-agent"></a>Agent local

## <a name="graph-connector-agent"></a>Agent de connecteur Graph

Les connecteurs Graph local requièrent l’installation du logiciel de *l’agent Graph Connector* . Elle permet de transférer rapidement et en toute sécurité des données entre des services de données et de Cloud Computing. Cet article vous guide tout au long des étapes d’installation et de configuration du logiciel. Une fois configuré, il sera disponible pour la création de connexions à vos sources de données local à partir du [Centre d’administration Microsoft 365](https://admin.microsoft.com).

## <a name="installation"></a>Installation

Téléchargez la dernière version de l’agent connecteur Graph à l’aide de [ce lien](https://download.microsoft.com/download/d/d/e/dde18236-9c67-437d-a864-894a0a888ef2/AgentPackage.msi) et installez le logiciel à l’aide de l’Assistant d’installation. Avec la configuration recommandée de l’ordinateur décrit ci-dessous, le logiciel peut gérer de manière transparente jusqu’à trois connexions. Toutes les connexions au-delà de cela risquent de dégrader les performances.

Configuration recommandée :

* Windows 10, Windows Server 2012 R2 et versions ultérieures
* 8 cœurs, 3 GHz
* 16 Go de RAM, 1 Go d’espace disque
* Accès réseau à la source de données et à Internet via 443

## <a name="creating-app-for-the-agent"></a>Création de l’application pour l’agent  

L’instance de l’agent doit comporter peu de paramètres critiques avant de créer des connexions. Ces paramètres incluent des détails d’authentification requis pour l’utilisation des API de réception Graph.  

Étapes de création de l’application pour l’agent.

1. Accédez au [portail Azure](https://portal.azure.com) et connectez-vous avec les informations d’identification d’administrateur pour le client.
2. Accédez à **Azure Active Directory**  ->  ,**inscriptions des applications** dans le volet de navigation, puis sélectionnez **nouvelle inscription**.
3. Fournissez un nom pour l’application, puis sélectionnez **Enregistrer**.
4. Notez l’ID de l’application (client).
5. Ouvrez les autorisations de l' **API** à partir du volet de navigation et sélectionnez **Ajouter une autorisation**.
6. Sélectionnez **Microsoft Graph** , puis **autorisations d’application**.
7. Recherchez « ExternalItem. ReadWrite. All » et « Directory. Read. All » à partir des autorisations, puis sélectionnez **Ajouter des autorisations**.
8. Sélectionnez **accorder le consentement de l’administrateur pour [TenantName]** et confirmez-le en sélectionnant **Oui**.
9. Vérifiez que les autorisations sont dans l’État accordé.
     ![Autorisations indiquées comme étant accordées dans la colonne de droite vert sur la droite.](media/onprem-agent/granted-state.png)

## <a name="configuring-graph-connector-agent"></a>Configuration de l’agent de connecteur Graph

Une fois que vous avez créé l’application pour l’agent, vous devez configurer l’agent avec les détails d’authentification appropriés.

Les détails de l’authentification peuvent être fournis dans l’un des formulaires suivants.

### <a name="configuring-the-client-secret-for-authentication"></a>Configuration de la clé secrète client pour l’authentification

1. Accédez au [portail Azure](https://portal.azure.com) et connectez-vous avec les informations d’identification d’administrateur pour le client.
2. Ouvrez **inscription** de l’application dans le volet de navigation et accédez à l’application appropriée. Sous **gérer**, sélectionnez **certificats et secrets**.
3. Sélectionnez **nouvelle clé secrète client** et sélectionnez une période d’expiration pour la clé secrète. Copiez la clé secrète générée et enregistrez-la, car elle ne s’affichera plus.
4. Utilisez cette clé secrète client avec l’ID de l’application pour configurer l’agent. N’utilisez pas d’espaces dans le champ **nom** de l’agent. Les caractères numériques alphanumériques sont acceptés.

## <a name="using-thumbprint-certificate-for-authentication"></a>Utilisation d’un certificat d’empreinte numérique pour l’authentification

Si vous avez déjà configuré les détails d’authentification en suivant [la configuration de la clé secrète client pour l’authentification](#configuring-the-client-secret-for-authentication) , vous pouvez passer directement à la [rubrique Configuration Overview](configure-connector.md).

1. Ouvrez **inscription** de l’application et sélectionnez **certificats et secrets** dans le volet de navigation. Copiez l’empreinte de certificat.
![Liste des certificats thumbrint lorsque l’option certificats et secrets est sélectionnée dans le volet de gauche](media/onprem-agent/certificates.png)
2. Utilisez la clé secrète client ou l’empreinte numérique pour enregistrer l’agent connecteur Graph.
![Formulaire d’inscription demandant le nom, l’ID de l’application, le type d’informations d’identification et le certificat](media/onprem-agent/register.png)
