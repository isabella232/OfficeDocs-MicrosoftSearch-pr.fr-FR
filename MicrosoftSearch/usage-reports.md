---
title: Rapports d’utilisation de la recherche
ms.author: ankmis
author: jeffkizn
manager: parulm
ms.topic: article
ms.service: mssearch
audience: Admin
ms.audience: Admin
ms.date: 07/02/2021
ms.localizationpriority: medium
search.appverid:
- BFB160
- MET150
- MOE150
description: Examiner les rapports Recherche Microsoft’utilisation des applications
ms.openlocfilehash: 9de48331efbc956ee7d980b919d9bd2f025fc8aa
ms.sourcegitcommit: cc9d743bcf5e998720ce9cd6eefb4061d913dc65
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/30/2021
ms.locfileid: "58701452"
---
# <a name="microsoft-search-usage-reports"></a>Recherche Microsoft Rapports d’utilisation

Les rapports d’utilisation de la recherche vous permettent de mieux comprendre le fonctionnement de la recherche dans votre organisation. Les informations générées à partir [](./make-content-easy-to-find.md) de ces rapports vous aideront à faciliter la recherche de contenu et à prendre des mesures qui donnent à vos utilisateurs une expérience plus utile et agréable.

> [!IMPORTANT]
> Recherche Microsoft rapports d’utilisation sont actuellement en prévisualisation

Les rapports [d’utilisation](https://admin.microsoft.com/Adminportal/Home?#/MicrosoftSearch/insights) Recherche Microsoft incluent des graphiques et des tableaux générés à partir de recherches exécutées à partir de SharePoint Home, Office.com et Recherche Microsoft dans Bing de recherche. Vous pouvez voir les données des 31 derniers jours, par jour ou par mois de l’année précédente. Ces rapports sont simplement en cours de déploiement, de sorte que l’ensemble des données historiques prendra du temps.

Une version précédente de cette page incluait les données des recherches exécutées uniquement pour Recherche Microsoft dans Bing sur Bing.com. Ces données sont désormais intégrées dans ces rapports ; Vous pouvez toujours voir l’ancienne page en cliquant sur le lien en bas de la page pour afficher les requêtes Bing et la distribution des **impressions.** Ce lien et l’ancienne page seront bientôt supprimés.

> [!div class="mx-imgBorder"]
> ![Tableau de bord rapports d’utilisation de la recherche.](media/usage-reports/usage_reports_v2.png)

## <a name="overview-of-search-reports"></a>Vue d’ensemble des rapports de recherche

| Rapport | Description |
|:-----|:-----|
|Volume de requête|Ce rapport indique le nombre de requêtes de recherche effectuées. Utilisez ce rapport pour identifier les tendances des volumes de requêtes de recherche et pour déterminer les périodes d’activité de recherche élevée et faible.|
|Requêtes les plus courantes|Ce rapport indique les requêtes de recherche les plus populaires. Une requête est ajoutée à ce rapport lorsqu’elle est recherché au moins trois fois avec un clic sur un résultat. Utilisez ce rapport pour comprendre les types d’informations que vos utilisateurs recherchent.|
|Requêtes abandonnées|Ce rapport affiche les requêtes de recherche les plus populaires qui reçoivent un faible clic. Il permet d'identifier les requêtes de recherche pouvant provoquer l'insatisfaction des utilisateurs et d'améliorer la détectabilité du contenu. Vous pouvez ensuite déterminer si la création d’une réponse, telle qu’un signet, ou l’ing d’un nouveau contenu via un connecteur Graph est l’action la plus appropriées.|
|Requêtes sans résultats|Ce rapport indique les requêtes de recherche populaires qui n'ont retourné aucun résultat. Il permet d'identifier les requêtes de recherche pouvant provoquer l'insatisfaction des utilisateurs et d'améliorer la détectabilité du contenu. Vous pouvez ensuite déterminer si la création d’une réponse, telle qu’un signet, ou l’ing d’un nouveau contenu via un connecteur Graph est l’action la plus appropriées.|

>[!NOTE]
>Il existe actuellement un problème connu où les requêtes satisfaites par une réponse telle qu’un signet sont comptabilisées comme une requête abandonnée.

## <a name="viewing-reports"></a>Affichage des rapports

Lorsque vous accédez à la page Rapports d’utilisation, tous les rapports sont disponibles. Vous pouvez utiliser le filtre de date pour sélectionner un jour ou un mois spécifique à afficher.

Le téléchargement d’un rapport vous permettra de voir les rapports à partir d’un plus large éventail de temps. Cliquez sur la flèche de téléchargement et sélectionnez **les 31 derniers jours** ou **les 12 derniers mois.** Le rapport est téléchargé sous la Excel feuille de calcul. Si vous avez sélectionné au-delà de 31 jours, la feuille de calcul aura un onglet individuel pour chaque jour. Le téléchargement des 12 derniers mois aura un onglet pour chaque mois.

Pour afficher Bing les principales requêtes et les rapports de distribution des impressions, cliquez sur le lien de la page.

## <a name="frequently-asked-questions"></a>Foire aux questions

**Lorsque je sélectionne les 31 derniers jours ou les 12 derniers mois, pourquoi dois-je choisir un jour ou un mois spécifique ?**

L’affichage Calendrier, aujourd’hui, dans les rapports d’utilisation de la recherche Microsoft est un processus en deux étapes. Tout d’abord, sélectionnez la plage de dates dans la dropdown (31 derniers jours ou 12 derniers mois), puis sélectionnez le jour ou le mois de début.

Les tables de requête en haut, abandonnées et échouées indiquent les résultats du jour ou du mois que vous choisissez.

**Quand puis-je voir les données agrégées des 7 derniers jours, des 30 derniers jours, et ainsi de suite... comme Bing les principaux rapports de requêtes ?**

Nous envisageons ce type d’agrégation et simplifions le filtrage des plages de données pour les futures versions de ces rapports.

**Pourquoi ne puis-je pas voir une répartition des rapports d’utilisation par différentes applications (sources) ?**

Actuellement, le filtrage par source n’est pas disponible. Les rapports combinent les recherches à partir SharePoint Home et Office.com. Notre prochaine version inclut le filtrage source afin que vous pouvez voir des mesures spécifiques à chaque application.

**Quel autre filtrage des rapports d’utilisation sera-t-il à venir ?**

Nous travaillons sur des filtres supplémentaires qui vous aideront à donner un sens à l’utilisation de la recherche à un niveau plus granulaire de votre organisation. Par exemple, vous pourrez voir le volume de requête pour une zone géographique ou un service spécifique.
