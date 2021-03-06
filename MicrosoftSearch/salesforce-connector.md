---
title: Connecteur Salesforce Graph pour Microsoft Search (recherche Microsoft)
ms.author: mecampos
author: mecampos
manager: umas
audience: Admin
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: Configurer le connecteur Salesforce Graph pour Microsoft Search (recherche Microsoft)
ms.openlocfilehash: 86140a4650593e08188f171be54f1753b73ecf7a
ms.sourcegitcommit: f76ade4c8fed0fee9c36d067b3ca8288c6c980aa
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/05/2021
ms.locfileid: "50508822"
---
<!---Previous ms.author: rusamai --->

# <a name="salesforce-graph-connector-preview"></a>Connecteur Salesforce Graph (prévisualisation)

Le connecteur Salesforce Graph permet à votre organisation d’indexer les objets Contacts, Opportunités, Prospects et Comptes dans votre instance Salesforce. Après avoir configuré le connecteur et indexé le contenu à partir de Salesforce, les utilisateurs finaux peuvent rechercher ces éléments à partir de n’importe quel client Recherche Microsoft.

> [!NOTE]
> Lisez [**l’article Configuration de votre connecteur Graph**](configure-connector.md) pour comprendre les instructions générales d’installation des connecteurs Graph.

Cet article est réservé à toute personne qui configure, exécute et surveille un connecteur Salesforce Graph. Il complète le processus d’installation général et affiche des instructions qui s’appliquent uniquement au connecteur Salesforce Graph. Cet article inclut également des informations sur [les limitations.](#limitations)

>[!IMPORTANT]
>Le connecteur Salesforce Graph prend actuellement en charge Summer '19 ou une ultérieure.

## <a name="before-you-get-started"></a>Avant de commencer

Pour vous connecter à votre instance Salesforce, vous avez besoin de votre URL d’instance Salesforce, de l’ID client et de la secret client pour l’authentification OAuth. Les étapes suivantes expliquent comment vous ou votre administrateur Salesforce pouvez obtenir ces informations à partir de votre compte Salesforce :

- Connectez-vous à votre instance Salesforce et allez au programme d’installation

- Accédez à Apps -> App Manager.

- Sélectionnez **Nouvelle application connectée.**

- Remplissez la section API comme suit :

    - Activez la case à **cocher Activer les paramètres Oauth.**

    - Spécifiez l’URL de rappel comme : [https://gcs.office.com/v1.0/admin/oauth/callback](https://gcs.office.com/v1.0/admin/oauth/callback)

    - Sélectionnez les étendues OAuth requises.

        - Accéder à vos données (api) et les gérer

        - Effectuer des demandes en votre nom à tout moment (refresh_token, offline_access)

    - Cochez la case exiger **une secret pour le flux de serveur web.**

    - Enregistrez l’application.
    
      > [!div class="mx-imgBorder"]
      > ![Section API dans l’instance Salesforce une fois que l’administrateur a entré toutes les configurations requises répertoriées ci-dessus.](media/salesforce-connector/sf1.png)

- Copiez la clé grand public et la clé secrète consommateur. Ces informations sont utilisées comme ID client et secret client lorsque vous configurez les paramètres de connexion de votre connecteur Graph dans le portail d’administration Microsoft 365.

  > [!div class="mx-imgBorder"]
  > ![Résultats renvoyés par la section API dans l’instance Salesforce après que l’administrateur a soumis toutes les configurations requises. La clé consommateur se trouve en haut de la colonne gauche et la clé secrète consommateur en haut de la colonne de droite.](media/salesforce-connector/clientsecret.png)
  
- Avant de fermer votre instance Salesforce, suivez ces étapes pour vous assurer que les jetons d’actualisation n’expirent pas :
    - Go to Apps -> App Manager
    - Recherchez l’application que vous avez créée et sélectionnez la drop-down sur la droite. Sélectionnez **Gérer**
    - Sélectionner des **stratégies de modification**
    - Pour la stratégie de jeton d’actualisation, **sélectionnez Le jeton d’actualisation est valide jusqu’à ce qu’il soit révoqué**

  > [!div class="mx-imgBorder"]
  > ![Sélectionnez la stratégie de jeton d’actualisation nommée « Jeton d’actualisation est valide jusqu’à ce qu’elle soit révoquée »](media/salesforce-connector/oauthpolicies.png)

Vous pouvez désormais utiliser le [Centre d’administration M365](https://admin.microsoft.com/) pour terminer le reste du processus de configuration de votre connecteur Graph.

## <a name="step-1-add-a-graph-connector-in-the-microsoft-365-admin-center"></a>Étape 1 : Ajouter un connecteur Graph dans le Centre d’administration Microsoft 365

Suivez les [instructions d’installation générales.](https://docs.microsoft.com/microsoftsearch/configure-connector)
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-2-name-the-connection"></a>Étape 2 : Nommer la connexion

Suivez les [instructions d’installation générales.](https://docs.microsoft.com/microsoftsearch/configure-connector)
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-3-configure-the-connection-settings"></a>Étape 3 : Configurer les paramètres de connexion

Pour l’URL de l’instance, utilisez https://[domaine].my.salesforce.com où le domaine serait le domaine Salesforce de votre organisation.

Entrez l’ID client et la secret client que vous avez obtenus à partir de votre instance Salesforce, puis sélectionnez Se connectez.

La première fois que vous tentez de vous connecter à l’aide de ces paramètres, une fenêtre vous demande de vous connecter à Salesforce avec votre nom d’utilisateur et votre mot de passe d’administrateur. La capture d’écran ci-dessous montre la fenêtre pop-up. Entrez vos informations d’identification, puis sélectionnez « Se connecter ».

  ![Fenêtre de connexion pour demander le nom d’utilisateur et le mot de passe.](media/salesforce-connector/sf4.png)

  >[!NOTE]
  >Si la fenêtre pop-up n’apparaît pas, elle risque d’être bloquée dans votre navigateur. Vous devez donc autoriser les fenêtres pop-up et les redirections.

Vérifiez que la connexion a réussi en recherchant une bannière verte qui indique « Connexion réussie », comme indiqué dans la capture d’écran ci-dessous.

  > [!div class="mx-imgBorder"]
  > ![Capture d’écran de la connexion réussie. La bannière verte qui indique « Connexion réussie » se trouve sous le champ de votre URL d’instance Salesforce](media/salesforce-connector/sf5.png)

## <a name="step-4-manage-search-permissions"></a>Étape 4 : Gérer les autorisations de recherche

Vous devez choisir les utilisateurs qui voient les résultats de la recherche à partir de cette source de données. Si vous autorisez uniquement certains utilisateurs Azure Active Directory (Azure AD) ou non Azure AD à voir les résultats de la recherche, assurez-vous de ma cartographier les identités.

## <a name="step-4a-select-permissions"></a>Étape 4a : Sélectionner les autorisations

Vous pouvez choisir d’ingèrer des listes de contrôle d’accès à partir de votre instance Salesforce ou autoriser tous les membres de votre organisation à voir les résultats de recherche provenant de cette source de données. Les ALA peuvent inclure des identités Azure Active Directory (AAD) (utilisateurs fédérés d’Azure AD à Salesforce), des identités non Azure AD (utilisateurs Salesforce natifs ayant des identités correspondantes dans Azure AD) ou les deux.

>[!NOTE]
>Si vous utilisez un fournisseur d’identité tiers comme Ping ID ou secureAuth, vous devez sélectionner « non-AAD » comme type d’identité.

> [!div class="mx-imgBorder"]
> ![Écran Sélectionner les autorisations qui ont été effectuées par un administrateur. L’administrateur a sélectionné l’option « Uniquement les personnes ayant accès à cette source de données » et a également sélectionné « AAD » dans un menu déroulant de types d’identité.](media/salesforce-connector/sf6.png)

Si vous avez choisi d’ing d’une ACL à partir de votre instance Salesforce et que vous avez sélectionné « non-AAD » pour le type d’identité, voir Mappage de vos [identités non Azure AD](map-non-aad.md) pour obtenir des instructions sur le mappage des identités.

## <a name="step-4b-map-aad-identities"></a>Étape 4b : Maser les identités AAD

Si vous avez choisi d’ing d’une ACL à partir de votre instance Salesforce et que vous avez sélectionné « AAD » pour le type d’identité, voir Mappage de vos [identités Azure AD](map-aad.md) pour obtenir des instructions sur le mappage des identités. Pour savoir comment configurer Azure AD SSO pour Salesforce, consultez ce [didacticiel.](https://docs.microsoft.com/azure/active-directory/saas-apps/salesforce-tutorial)

## <a name="step-5-assign-property-labels"></a>Étape 5 : Attribuer des étiquettes de propriété

Vous pouvez affecter une propriété source à chaque étiquette en choisissant dans un menu d’options. Bien que cette étape ne soit pas obligatoire, le fait d’avoir certaines étiquettes de propriétés améliorera la pertinence de la recherche et garantira de meilleurs résultats de recherche pour les utilisateurs finaux. Par défaut, certaines étiquettes telles que « Titre », « URL », « CreatedBy » et « LastModifiedBy » se sont déjà vu attribuer des propriétés source.

## <a name="step-6-manage-schema"></a>Étape 6 : Gérer le schéma

Vous pouvez sélectionner les propriétés source qui doivent être indexées afin qu’elles s’afficheront dans les résultats de la recherche. L’Assistant Connexion sélectionne par défaut un schéma de recherche basé sur un ensemble de propriétés source. Vous pouvez le modifier en élecant les cases à cocher de chaque propriété et attribut de la page de schéma de recherche. Les attributs de schéma de recherche incluent recherche, requête, récupération et affiner.
L’affinement vous permet de définir les propriétés qui peuvent être utilisées ultérieurement en tant qu’affinements ou filtres personnalisés dans l’expérience de recherche.  

> [!div class="mx-imgBorder"]
> ![Sélectionnez le schéma pour chaque propriété source. Les options sont Requête, Recherche, Récupérer et Affiner](media/salesforce-connector/sf9.png)

## <a name="step-7-set-the-refresh-schedule"></a>Étape 7 : Définir la planification de l’actualisation

Le connecteur Salesforce prend uniquement en charge les planifications d’actualisation pour les analyse complètes actuellement.

>[!IMPORTANT]
>Une analyse complète recherche des objets et des utilisateurs supprimés qui ont été précédemment synchronisés avec l’index recherche Microsoft.

La planification recommandée est d’une semaine pour une analyse complète.

## <a name="step-8-review-connection"></a>Étape 8 : Examiner la connexion

Suivez les [instructions d’installation générales.](https://docs.microsoft.com/microsoftsearch/configure-connector)
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

<!---## Troubleshooting-->
<!---Insert troubleshooting recommendations for this data source-->

## <a name="limitations"></a>Limites

- Le connecteur Graph ne prend actuellement pas en charge le partage et le partage basés sur un territoire à l’aide de groupes personnels de Salesforce.
- Il existe un bogue connu dans l’API Salesforce que le connecteur Graph utilise, où les valeurs par défaut privées à l’échelle de l’organisation pour les prospects ne sont pas honorées actuellement.  
- Si un champ a la sécurité au niveau du champ (FLS) définie pour un profil, le connecteur Graph n’inserre pas ce champ pour les profils dans cette organisation Salesforce. Par conséquent, les utilisateurs ne pourront pas rechercher sur les valeurs de ces champs, ni s’afficher dans les résultats.  
- Dans l’écran Gérer le schéma, ces noms de propriétés standard communs sont répertoriés une seule fois, les options sont **Requête,** **Rechercher,** Récupérer **et** **Affiner,** et s’appliquent à tout ou aucun.
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
