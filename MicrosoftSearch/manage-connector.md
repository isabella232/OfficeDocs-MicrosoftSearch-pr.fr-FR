---
title: Gérer les connecteurs Microsoft Graph pour Microsoft Search (recherche Microsoft)
ms.author: monaray
author: monaray97
manager: mnirkhe
audience: Admin
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: Gérer les connecteurs Microsoft Graph pour Microsoft Search (recherche Microsoft).
ms.openlocfilehash: 1c152f23e9b9d9982b957830d5f4bef0eef41347
ms.sourcegitcommit: 2f770de12b27546b18b2e86517d2c25522eb9022
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50929583"
---
<!-- markdownlint-disable no-inline-html -->

# <a name="monitor-your-connections"></a>Surveiller vos connexions

Pour accéder à vos connecteurs et les gérer, vous devez être désigné en tant qu’administrateur de recherche pour votre client. Contactez votre administrateur client pour vous fournir le rôle d’administrateur de recherche.

## <a name="connection-operations"></a>Opérations de connexion

Accédez à [l’onglet Connecteurs](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/Connectors) dans le [Centre d’administration Microsoft 365.](https://admin.microsoft.com)

Pour chaque type de connecteur, le Centre [d’administration Microsoft 365](https://admin.microsoft.com) prend en charge les opérations indiquées dans le tableau suivant :

Opération | Connecteurs Graph par Microsoft | Connecteurs partenaires ou Graph
--- | --- | ---
Ajouter une connexion | :heavy_check_mark : (voir [vue d’ensemble du programme d’installation)](configure-connector.md) | :x : (faire référence à l’UX de votre partenaire ou de votre connecteur personnalisé)
Supprimer une connexion | :heavy_check_mark: | :heavy_check_mark:
Modifier une connexion publiée | :heavy_check_mark : nom et description<br></br> :heavy_check_mark : paramètres de connexion<br></br> :heavy_check_mark : étiquettes de propriété<br></br> :heavy_check_mark : schéma<br></br> :heavy_check_mark : planification d’actualisation<br></br> | :heavy_check_mark: Nom<br></br> :heavy_check_mark : Description
Modifier un brouillon de connexion | :heavy_check_mark: | :x:

## <a name="monitor-your-connection-state"></a>Surveiller l’état de votre connexion

Après avoir créé une connexion, le nombre d’éléments **traitées** s’affiche sous l’onglet Connecteurs de la page **Recherche Microsoft.** Une fois l’analyse complète initiale terminée, la progression des analyses incrémentielles périodiques s’affiche. Cette page fournit des informations sur les opérations quotidiennes du connecteur et une vue d’ensemble des journaux et de l’historique des erreurs.

Quatre états s’affiche dans la colonne **État** par rapport à chaque connexion :

* **Synchronisation.** Le connecteur analyse les données de la source pour indexer les éléments existants et effectuer des mises à jour.

* **Prêt**: la connexion est prête et aucune analyse active n’est en cours d’exécution. **L’heure de la** dernière synchronisation indique à quel moment la dernière analyse réussie s’est produite. La connexion est aussi nouvelle que l’heure de la dernière synchronisation.

* **Suspendu**. Les analyses sont suspendues par les administrateurs via l’option de pause. L’analyse suivante s’exécute uniquement lorsqu’elle est reprise manuellement. Toutefois, les données de cette connexion sont toujours utilisables dans une recherche.

* **Échec**. La connexion a connu une défaillance critique. Cette erreur nécessite une intervention manuelle. L’administrateur doit prendre les mesures appropriées en fonction du message d’erreur affiché. Les données qui ont été indexées jusqu’à ce que l’erreur se soit produite sont utilisables dans une recherche.

## <a name="monitor-your-index-quota-utilization"></a>Surveiller l’utilisation de votre quota d’index

Le quota d’index et la consommation disponibles sont affichés sur la page d’accueil des connecteurs.

![Barre d’utilisation du quota d’index](media/quota_utilization.png)
 
>[!NOTE]
>Pendant la période d’aperçu, chaque organisation qui essaie des connecteurs Graph a été fournie avec un quota fixe gratuit de 2 millions d’éléments sur toutes les connexions. Les connecteurs Graph étant généralement disponibles, le quota gratuit expirera le 1er avril 2021 pour les organisations qui ont utilisé des connecteurs Graph en prévisualisation.
>Les connecteurs Graph créés par Microsoft et étiquetés comme « [Aperçu](connectors-preview.md) » ne seront pas inclus dans le quota d’index facturé total pour votre organisation. Toutefois, il est comptabilisé dans le nombre maximum de 10 connexions que vous pouvez configurer pour votre organisation et le nombre maximum de 7 millions d’éléments que votre organisation peut indexer entre les connexions ; Chaque connexion est limitée à 700 000 éléments. 

La barre d’utilisation des quotas indiquera différents états en fonction de la consommation de quota par votre organisation :

État | Niveaux d’utilisation des quotas
--- | --- 
Normal | 0-79%
Élevé | 80-89%
Critique | 90%-99%
Complet | 100 %

<!-- 
![Quota utilization levels](media/connectors-quota-utilization-levels.png)
-->

Le nombre d’éléments indexés s’affiche également avec chaque connexion. Le nombre d’éléments indexés par chaque connexion contribue au quota total disponible pour votre organisation.

Lorsque le quota d’index est dépassé pour votre organisation, toutes les connexions actives sont touchées et ces connexions fonctionnent dans un état **dépassé** limite. Dans cet état, vos connexions actives  

* Ne sera pas en mesure d’ajouter de nouveaux éléments.

* Sera en mesure de mettre à jour ou de supprimer des éléments existants.

Pour résoudre ce problème, vous pouvez :

* Découvrez comment acheter un quota d’index pour votre organisation selon les exigences de licence [et la tarification.](licensing.md)

* Identifiez les connexions qui ont trop de contenu en cours d’ingestion et mettez-les à jour pour indexer moins d’éléments afin de faire de la place pour le quota. Pour mettre à jour la connexion, vous devez supprimer et créer une connexion avec un nouveau filtre d’ingestion qui apporte moins d’éléments.

* Supprimer définitivement une ou plusieurs connexions
