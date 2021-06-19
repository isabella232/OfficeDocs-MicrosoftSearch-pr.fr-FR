---
title: Recherche de fédération Dynamics 365 (prévisualisation)
ms.author: dawholl
author: dawholl
manager: kellis
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
description: Gérer l’apparition du contenu Dynamics 365 dans les résultats de recherche
ms.openlocfilehash: 8818d2e6a412feb167c67f465f485b23e868a12a
ms.sourcegitcommit: be989950a7b63281c2348cfd9e6cc13e79b7c067
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/19/2021
ms.locfileid: "53021839"
---
# <a name="dynamics-365-federation-search-preview"></a>Recherche de fédération Dynamics 365 (prévisualisation)

## <a name="microsoft-search-federation-and-connectors"></a>Recherche Microsoft Fédération et connecteurs

Pour vous aider à rendre Recherche Microsoft plus utile, nous présentons Recherche Microsoft fédération. Avec la recherche fédérée, les organisations peuvent rendre les données accessibles dans les scénarios suivants Recherche Microsoft :

* Données dans les systèmes soumis à des exigences strictes de conformité
* Données qui ne peuvent pas quitter les limites du système
* Données sensibles stockées sur site que votre organisation ne souhaite pas indexer sur le cloud

Les données accessibles via une connexion de recherche fédérée ne sont pas indexées Recherche Microsoft. En outre, à l’aide de connecteurs intégrés de Microsoft, il est facile de configurer des connexions de recherche fédérée. Notre connecteur Dynamics 365 est actuellement en prévisualisation. Si vous souhaitez participer à la prévisualisation, faites-le nous savoir [aka.ms/D365FederationSearchPreview](https://aka.ms/D365FederationSearchPreview).

## <a name="dynamics-365-federation-connector"></a>Connecteur de fédération Dynamics 365

Microsoft Dynamics 365 est une gamme d’applications métier intelligentes conçues pour la planification des ressources d’entreprise et la gestion de la relation client. Avec la fédération Dynamics 365, Recherche Microsoft offre une expérience de recherche transparente, permettant aux utilisateurs de trouver facilement les données client et métier les plus pertinentes stockées dans Dynamics 365. Le connecteur de fédération Dynamics 365 offre certains avantages clés :

* **Facile à administrer :** Processus simplifié pour configurer et maintenir la connexion de recherche à une instance Dynamics 365.
* **Facile à utiliser :** Les utilisateurs peuvent facilement et rapidement trouver des informations clés stockées dans Dynamics 365, notamment des comptes, des contacts, des opportunités d’ouverture, etc.
* **Contenu enrichi :** Pour rendre les résultats de recherche Dynamics 365 plus utiles, ils incluent des informations clés telles que des prospects, des contacts et des détails de compte.
* **Protection des données intégrée :** Les résultats dynamics 365 s’affichent uniquement pour les utilisateurs qui ont accès à l’instance connectée.
* **Expérience de recherche unifiée :** Pour conserver une expérience cohérente, les résultats Dynamics 365 sont cohérents sur tous les points d’entrée de recherche. Où que vous recherchez, vous obtenez les mêmes résultats avec la même apparence.

## <a name="what-users-experience"></a>Expérience des utilisateurs

Les réponses Dynamics 365 apparaissent dans les résultats de la recherche dans Recherche Microsoft canevas, y compris SharePoint Online, Bing et Office.

:::image type="content" alt-text="Capture d’écran des réponses Dynamics 365 SharePoint, Bing et Office" source="media/dynamics365/dynamics365-answer.png" lightbox="media/dynamics365/dynamics365-answer.png":::

À partir de la réponse, il est facile de voir d’autres résultats de recherche Dynamics 365 à l’aide du lien De plus **de résultats Dynamics 365.** Il permet aux utilisateurs d’obtenir une page de résultats Dynamics 365 dédiée avec d’autres résultats pertinents pour leur requête.

:::image type="content" alt-text="Capture d’écran de Dynamics 365 vertical et résultats sur SharePoint, Bing et Office" source="media/dynamics365/dynamics365-vertical.png" lightbox="media/dynamics365/dynamics365-vertical.png":::

Le fait de cliquer ou d’appuyer sur un résultat ouvre Dynamics 365 et affiche les informations détaillées.

:::image type="content" alt-text="Capture d’écran de la page de détails dans Dynamics 365" source="media/dynamics365/dynamics365-detail-page.png" lightbox="media/dynamics365/dynamics365-detail-page.png":::

Quel que soit l’endroit où vos utilisateurs lancent leur recherche, leur expérience sera cohérente et leur permettra de trouver rapidement les résultats Dynamics 365 les plus pertinents. Regardez notre [vidéo Microsoft Build 2021](https://youtu.be/TH9QUkQoEJM) pour une démonstration.

## <a name="supported-query-patterns"></a>Modèles de requête pris en charge

Les requêtes de nom de produit et de langage naturel sont toutes deux pris en charge lorsque vous utilisez Recherche Microsoft recherche de résultats Dynamics 365. En outre, les requêtes Dynamics 365 ne sont pas sensibles à la cas. Utilisez des modèles de langage naturel pour rechercher des contacts, des comptes et des opportunités (par nom de client ou emplacement) et d’autres requêtes fréquemment utilisées. Voici quelques exemples :

* Qui est le contact pour Contoso
* Opportunités ouvertes pour Contoso
* Quelles sont les opportunités ouvertes à Seattle ?
* Quels sont les comptes à Seattle ?
* Quels sont les contacts à Seattle ?
* Quels sont mes prospects fermant ce mois-ci
* Appel téléphonique haute priorité
* Messages électroniques manquants du contact

Les modèles de nom de produit 365 365 peuvent déclencher des résultats Dynamics 365, quel que soit l’endroit où ils apparaissent dans une requête :

* D365
* Dynamics 365
* Dynamics365
* Dynamics CRM
* Dynamics Sales
* Service clientèle Dynamics
* Dynamics Service
* Dynamics Field Service

## <a name="configure-the-dynamics-365-connector"></a>Configurer le connecteur Dynamics 365

Avec cette configuration simple, vous pouvez activer l’expérience de recherche de fédération Dynamics 365 pour les membres de votre organisation.

1. Dans la [Centre d’administration Microsoft 365](https://admin.microsoft.com), allez aux [sources de données.](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/connectors)

2. Dans la section Applications et services Microsoft, sous Microsoft Dynamics 365, sélectionnez **Gérer** pour ouvrir le panneau Microsoft Dynamics 365.

3. Activez le connecteur pour votre organisation.

4. Dans la **liste Points de terminaison,** sélectionnez votre environnement Dynamics 365.

5. Dans **l’ID de connexion,** entrez un ID unique pour cette connexion.

6. Vérifiez et cochez la case de consentement.

7. Sélectionnez **Enregistrer** pour terminer la configuration de la connexion.

:::image type="content" alt-text="Capture d’écran du panneau de configurer Dynamics 365 dans la Centre d’administration Microsoft 365" source="media/dynamics365/dynamic365-connection-setup.png" lightbox="media/dynamics365/dynamic365-connection-setup.png":::

Une fois l’installation terminée, les réponses et le secteur vertical de Dynamics 365 apparaissent uniquement pour les utilisateurs titulaires d’une licence Dynamics 365 valide et d’un accès à l’environnement Dynamics 365 connecté. À tout moment, vous pouvez revenir à ces paramètres et modifier l’environnement de point de terminaison de connexion ou désactiver la connexion.
