---
title: Connecteur Salesforce pour Microsoft Search
ms.author: rusamai
author: rsamai
manager: jameslao
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
ROBOTS: NOINDEX, NOFOLLOW
description: Configurer le connecteur Salesforce pour Microsoft Search
ms.openlocfilehash: 8de7784cae7d430bc385889bd836360c69492591
ms.sourcegitcommit: 77ec27736f3c8434b2ac47e10897ac2606ee8a03
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/11/2020
ms.locfileid: "48992867"
---
# <a name="salesforce-connector"></a>Connecteur Salesforce

Avec le connecteur de graphique Salesforce, votre organisation peut indexer des contacts, des opportunités, des prospects et des objets de comptes dans votre instance Salesforce. Après avoir configuré le connecteur et le contenu d’index à partir de Salesforce, les utilisateurs finals peuvent rechercher ces éléments à partir d’un client Microsoft Search.

Cet article est destiné aux administrateurs [365 de Microsoft](https://www.microsoft.com/microsoft-365) ou toute personne qui configure, exécute et surveille un connecteur Salesforce. Elle explique comment configurer les fonctionnalités de connecteur et de connecteur, ainsi que les restrictions et les techniques de résolution des problèmes.

>[!IMPORTANT]
>Le connecteur de graphique Salesforce prend actuellement en charge les versions estivales : 20, printemps, 20, hiver 20 et été 19.

## <a name="connection-settings"></a>Paramètres de connexion

Pour vous connecter à votre instance Salesforce, vous avez besoin de l’URL de votre instance de Salesforce, de l’ID client et de la clé secrète client pour l’authentification OAuth. Les étapes suivantes expliquent comment vous ou votre administrateur Salesforce pouvez obtenir ces informations à partir de votre compte Salesforce :

- Connectez-vous à votre instance Salesforce et accédez à la configuration.

- Accédez à applications-> gestionnaire d’applications.

- Sélectionnez **nouvelle application connectée**.

- Complétez la section API comme suit :

    - Activez la case à cocher **activer les paramètres OAuth**.

    - Spécifiez l’URL de rappel comme suit : [https://gcs.office.com/v1.0/admin/oauth/callback](https://gcs.office.com/v1.0/admin/oauth/callback)

    - Sélectionnez ces étendues OAuth requises. 

        - Accéder aux données et les gérer (API) 

        - Effectuer des demandes en votre nom à tout moment (refresh_token, offline_access) 

    - Activez la case à cocher **exiger une clé secrète pour le flux de serveur Web**.

    - Enregistrez l’application.
    
      ![Section API dans l’instance Salesforce une fois que l’administrateur a entré toutes les configurations requises mentionnées ci-dessus.](media/salesforce-connector/sf1.png)

- Copiez la clé de consommateur et la clé secrète consommateur. Ceux-ci seront utilisés comme ID client et clé secrète client lorsque vous configurez les paramètres de connexion de votre connecteur Graph dans le portail d’administration Microsoft 365.

  ![Résultats retournés par la section API dans l’instance Salesforce une fois que l’administrateur a soumis toutes les configurations requises. La clé de client est située en haut de la colonne de gauche et la clé secrète du consommateur est située en haut de la colonne de droite.](media/salesforce-connector/clientsecret.png)
- Avant de fermer votre instance de Salesforce, effectuez les étapes suivantes pour vous assurer que les jetons d’actualisation n’expirent pas : 
    - Accédez à applications-> App Manager
    - Recherchez l’application que vous venez de créer et sélectionnez la liste déroulante sur la droite. Sélectionnez **gérer**
    - Sélectionnez **modifier les stratégies**
    - Pour la stratégie de jeton d’actualisation, sélectionnez le **jeton d’actualisation est valide jusqu’à révoqué** .

  ![Sélectionnez la stratégie d’actualisation des jetons nommée « actualisation du jeton est valide jusqu’à révoqué »](media/salesforce-connector/oauthpolicies.png)

Vous pouvez désormais utiliser le [Centre d’administration M365](https://admin.microsoft.com/) pour terminer le reste du processus de configuration de votre connecteur Graph.  

Configurez les paramètres de connexion de votre connecteur Graph comme suit :

- Pour l’URL d’instance, utilisez https://[domaine]. My. salesforce. com où Domain serait le domaine Salesforce de votre organisation. 
- Entrez l’ID client et la clé secrète client que vous avez obtenus à partir de votre instance Salesforce et sélectionnez connexion.
- S’il s’agit de la première fois que vous tentez de vous connecter avec ces paramètres, une fenêtre contextuelle s’affiche pour vous demander de vous connecter à la force de connexion avec votre nom d’utilisateur et votre mot de passe d’administrateur. La capture d’écran ci-dessous montre le menu contextuel. Entrez vos informations d’identification et sélectionnez connexion.

  ![Ouverture de session contextuelle demandant le nom d’utilisateur et le mot de passe.](media/salesforce-connector/sf4.png)

  >[!NOTE]
  >Si la fenêtre contextuelle ne s’affiche pas, elle peut être bloquée dans votre navigateur, vous devez donc autoriser les fenêtres publicitaires intempestives et les redirections.

  >[!NOTE]
  >Si votre organisation utilise l’authentification unique (SSO), vous pouvez sélectionner **utiliser un domaine personnalisé** dans le coin inférieur droit de l’interface de connexion. Entrez le domaine, puis cliquez sur **Continuer**. Il accède à la page de connexion spécifique de votre organisation où vous pouvez vous connecter à l’aide de l’authentification unique.

- Vérifiez que la connexion a réussi en recherchant une bannière verte indiquant « connexion réussie » comme illustré dans la capture d’écran ci-dessous.

  ![Capture d’écran de la connexion réussie. La bannière verte indiquant « connexion réussie » se trouve sous le champ de l’URL de votre instance de salesforce.](media/salesforce-connector/sf5.png)

## <a name="manage-search-permissions"></a>Gérer les autorisations de recherche
Vous devrez choisir les utilisateurs qui verront les résultats de la recherche à partir de cette source de données. Si vous autorisez uniquement certains utilisateurs Azure Active Directory (AAD) ou non AAD à afficher les résultats de la recherche, vous devrez mapper les identités.

### <a name="select-permissions"></a>Sélectionner des autorisations
Vous pouvez choisir d’ingérer les listes de contrôle d’accès (ACL) à partir de votre instance Salesforce ou vous pouvez autoriser tous les membres de votre organisation à consulter les résultats de la recherche à partir de cette source de données. Les listes de Contrã’le d’accès peuvent inclure des identités AAD (Azure Active Directory), des identités non AAD, ou les deux.

![Sélectionnez l’écran autorisations qui a été complété par un administrateur. L’administrateur a sélectionné l’option « uniquement les personnes ayant accès à cette source de données » et a également sélectionné « AAD » dans un menu déroulant des types d’identité.](media/salesforce-connector/sf6.png)

### <a name="map-non-aad-identities"></a>Mapper des identités non AAD 
Si vous avez choisi d’une liste de contrôle d’accès à partir de votre instance Salesforce et que vous avez sélectionné « non AAD » pour le type d’identité, voir [mapper vos identités non Azure ad ](map-non-aad.md) pour obtenir des instructions sur le mappage des identités.

### <a name="map-aad-identities"></a>Mapper des identités AAD
Si vous avez choisi d’une liste de contrôle d’accès à partir de votre instance Salesforce et que vous avez sélectionné « AAD » pour le type d’identité, voir [mapper vos identités Azure ad](map-aad.md) pour obtenir des instructions sur le mappage des identités.

## <a name="assign-property-labels"></a>Affecter des étiquettes de propriété 
Vous pouvez affecter une propriété source à chaque étiquette en choisissant dans un menu d’options. Si cette étape n’est pas obligatoire, le fait d’avoir des étiquettes de propriété améliore la pertinence de la recherche et garantit des résultats de recherche plus précis pour les utilisateurs finaux. Par défaut, certaines étiquettes telles que « titre », « URL » et « LastModifiedBy » ont déjà reçu des propriétés source.

![Écran affecter des étiquettes de propriétés affichant les propriétés de la source par défaut.](media/salesforce-connector/sf8.png)

## <a name="manage-schema"></a>Gérer le schéma
Vous pouvez sélectionner les propriétés sources à indexer pour qu’elles puissent apparaître dans les résultats de la recherche. Par défaut, l’Assistant Connexion sélectionne un schéma de recherche en fonction d’un ensemble de propriétés source. Vous pouvez le modifier en activant les cases à cocher de chaque propriété et attribut dans la page schéma de recherche. Les attributs de schéma de recherche incluent la recherche, la requête, l’extraction et l’affinement. Affiner vous permet de définir les propriétés qui peuvent être utilisées ultérieurement en tant qu’affinements personnalisés ou filtres dans l’expérience de recherche.  

![Sélectionnez le schéma pour chaque propriété source. Les options sont Query, Search, Retrieve et refinent](media/salesforce-connector/sf9.png)

## <a name="set-the-refresh-schedule"></a>Définir la planification d’actualisation

Le connecteur Salesforce prend uniquement en charge l’actualisation des planifications pour les analyses complètes actuellement.

>[!IMPORTANT]
>Une analyse complète recherche les objets et les utilisateurs supprimés qui ont été précédemment synchronisés avec l’index de recherche Microsoft.

La planification recommandée est d’une semaine pour une analyse complète.

## <a name="limitations"></a>Limites

- Le connecteur Graph ne prend actuellement pas en charge le partage et le partage basés sur un apex basé sur les territoires à l’aide de groupes personnels de salesforce.
- Il existe un bogue connu dans l’API Salesforce que le connecteur Graph utilise lorsque les valeurs par défaut à l’échelle de l’organisation privée pour les prospects ne sont pas honorées actuellement.  
- Si un champ a une sécurité au niveau champ (FLS) définie pour un profil, le connecteur Graph n’admettra pas ce champ aux profils de cette organisation Salesforce. Par conséquent, les utilisateurs ne pourront pas Rechercher des valeurs de ces champs, ni s’afficher dans les résultats.  
- Toutes les FLS configurées seront honorées pendant les synchronisations complètes du connecteur.
- Dans l’écran gérer le schéma, ces noms de propriétés standard courants sont répertoriés une fois et la sélection est effectuée pour les rendre interutilisables, pouvant faire l’objet d’une recherche et d’une extraction s’appliquent à tout ou aucun.
    - Nom
    - Url 
    - Description
    - Fax
    - Téléphone
    - MobilePhone
    - E-mail
    - Type
    - Titre
    - AccountId
    - AccountName
    - AccountUrl
    - AccountOwner
    - AccountOwnerUrl
    - Propriétaire
    - OwnerUrl
    - CreatedBy 
    - CreatedByUrl 
    - LastModifiedBy 
    - LastModifiedByUrl 
    - LastModifiedDate
    - ObjectName 
