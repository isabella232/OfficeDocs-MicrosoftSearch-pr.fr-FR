---
title: Microsoft SQL Connector pour Microsoft Search
ms.author: v-pamcn
author: monaray
manager: mnirkhe
ms.date: 11/04/2019
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: Configurez Microsoft SQL Connector pour Microsoft Search.
ms.openlocfilehash: a5e0b26277345814ed095b54583ea635341295ad
ms.sourcegitcommit: bfcab9d42e93addccd1e3875b41bc9cc1b6986cc
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/04/2019
ms.locfileid: "37949715"
---
# <a name="microsoft-sql-server-connector"></a>Connecteur Microsoft SQL Server

Avec un connecteur Microsoft SQL Server, votre organisation peut découvrir et indexer des données à partir d’une base de données SQL Server locale. Le connecteur indexe le contenu spécifié dans Microsoft Search. Pour conserver l’index à jour avec les données source, il prend en charge les analyses incrémentielles et complètes périodiques. Avec le connecteur SQL Server, vous pouvez également limiter l’accès aux résultats de recherche pour certains utilisateurs.

Cet article est destiné aux administrateurs 365 de Microsoft ou toute personne qui configure, exécute et surveille un connecteur Microsoft SQL Server. Elle explique comment configurer les fonctionnalités de connecteur et de connecteur, ainsi que les restrictions et les techniques de résolution des problèmes.

## <a name="install-a-data-gateway"></a>Installer une passerelle de données
Pour accéder à vos données tierces, vous devez installer et configurer une passerelle Microsoft Power BI. Pour en savoir plus [, voir Install and on-](https://docs.microsoft.com/data-integration/gateway/service-gateway-install) premises Gateway.  

## <a name="connect-to-a-data-source"></a>Se connecter à une source de données
Pour connecter votre Connecteur Microsoft SQL Server à une source de données, vous devez configurer le serveur de base de données que vous souhaitez analyser et la passerelle locale. Vous pouvez ensuite vous connecter à la base de données à l’aide de la méthode d’authentification requise.

> [!NOTE]
> Votre base de données doit exécuter SQL Server version 2008 ou ultérieure.

Pour effectuer une recherche dans le contenu de votre base de données, vous devez spécifier des requêtes SQL lorsque vous configurez le connecteur. Ces requêtes SQL doivent nommer toutes les colonnes de base de données que vous souhaitez indexer (c.-à-d. les propriétés source), y compris toutes les jointures SQL qui doivent être effectuées pour obtenir toutes les colonnes. Pour restreindre l’accès aux résultats de la recherche, vous devez spécifier des listes de contrôle d’accès (ACL) avec des requêtes SQL lorsque vous configurez le connecteur Microsoft SQL Server.

## <a name="full-crawl-required"></a>Analyse complète (obligatoire)
Dans cette étape, vous configurez la requête SQL qui exécute une analyse complète de la base de données. L’analyse complète sélectionne toutes les colonnes ou les propriétés que vous souhaitez rendre utilisables ou **pouvant**faire l’objet **** d’une **requête**. Vous pouvez également spécifier des colonnes ACL pour limiter l’accès aux résultats de la recherche à des utilisateurs ou à des groupes spécifiques.

> [!Tip]
> Pour obtenir toutes les colonnes dont vous avez besoin, vous pouvez joindre plusieurs tables.

![Script illustrant les OrderTable et AclTable avec les propriétés de l’exemple](media/MSSQL-fullcrawl.png)

### <a name="select-data-columns-required-and-acl-columns-optional"></a>Sélectionner des colonnes de données (obligatoires) et des colonnes ACL (facultatif)
L’exemple illustre la sélection de cinq colonnes de données qui contiennent les données pour la recherche : OrderId, OrderTitle, OrderDesc, CreatedDateTime et IsDeleted. Pour définir des autorisations d’affichage pour chaque ligne de données, vous pouvez éventuellement sélectionner les colonnes suivantes : AllowedUsers, AllowedGroups, DeniedUsers et DeniedGroups. Toutes ces colonnes de données peuvent être rendues pouvant faire l’objet d’une **requête**, d’une **recherche**ou d’une **extraction**.

Sélectionnez des colonnes de données comme indiqué dans cet exemple de requête :`SELECT OrderId, OrderTitle, OrderDesc, AllowedUsers, AllowedGroups, DeniedUsers, DeniedGroups, CreatedDateTime, IsDeleted`

### <a name="watermark-required"></a>Filigrane (obligatoire)
Pour éviter de surcharger la base de données, le connecteur regroupe et reprend les requêtes d’analyse complète avec une colonne de filigrane complète. En utilisant la valeur de la colonne filigrane, chaque lot suivant est extrait et l’interrogation reprend à partir du dernier point de contrôle. Fondamentalement, il s’agit d’un mécanisme de contrôle de l’actualisation des données pour les analyses complètes.

Créez des extraits de code de requête pour les filigranes, comme indiqué dans les exemples suivants :
* `WHERE (CreatedDateTime > @watermark)`. Citez le nom de la colonne filigrane par le `@watermark`mot clé réservé. Si l’ordre de tri de la colonne de filigrane est croissant, `>`utilisez la commande ; dans le cas `<`contraire, utilisez.
* `ORDER BY CreatedDateTime ASC`. Trier sur la colonne filigrane dans l’ordre croissant ou décroissant.

Dans la configuration illustrée dans l’image suivante `CreatedDateTime` , est la colonne de filigrane sélectionnée. Pour extraire le premier lot de lignes, spécifiez le type de données de la colonne de filigrane. Dans ce cas, le type de données `DateTime`est.

![](media/MSSQL-watermark.png)

La première requête extrait les **N** premières lignes à l’aide de : « CreatedDateTime > janvier 1, 1753 00:00:00 » (valeur minimale de type de données DateTime). Une fois le premier lot extrait, la valeur la plus élevée `CreatedDateTime` renvoyée dans le lot est enregistrée en tant que point de contrôle si les lignes sont triées par ordre croissant. Par exemple, le 1er mars 2019 03:00:00. Le prochain lot de **N** lignes est extrait en utilisant « CreatedDateTime > mars 1, 2019 03:00:00 » dans la requête.

### <a name="skipping-soft-deleted-rows-optional"></a>Ignorer les lignes supprimées (récupérables) (facultatif)
Pour exclure les lignes supprimées (récupérables) de votre base de données de l’indexation, spécifiez le nom et la valeur de la colonne de suppression récupérable qui indique que la ligne est supprimée.

![Paramètres de suppression douce : « colonne de suppression récupérable » et « valeur de la colonne suppression récupérable qui indique une ligne supprimée »](media/MSSQL-softdelete.png)

## <a name="incremental-crawl-optional"></a>Analyse incrémentielle (facultative)
Dans cette étape facultative, fournissez une requête SQL pour exécuter une analyse incrémentielle de la base de données. Avec cette requête, le connecteur Microsoft SQL Server apporte des modifications aux données depuis la dernière analyse incrémentielle. Comme dans l’analyse complète, sélectionnez toutes les colonnes que vous souhaitez rendre utilisables dans une **requête**, pouvant faire l’objet d’une **recherche**ou pouvoir être **récupérées**. Spécifiez le même ensemble de colonnes de liste de contrôle d’accès que vous avez spécifié dans la requête d’analyse complète.

Les composants de l’image suivante ressemblent aux composants d’analyse complets avec une exception. Dans ce cas, « ModifiedDateTime » est la colonne de filigrane sélectionnée. Examinez les étapes de l' [analyse complète](#full-crawl-required) pour apprendre à écrire votre requête d’analyse incrémentielle et voir l’image suivante par exemple.

![Script d’analyse incrémentielle affichant OrderTable, AclTable et des exemples de propriétés qui peuvent être utilisés.](media/MSSQL-incrcrawl.png)

## <a name="limitations"></a>Limites
Le connecteur Microsoft SQL Server présente ces limitations dans la version d’évaluation :
* La base de données locale doit exécuter SQL Server version 2008 ou une version ultérieure.
* Les ACL sont uniquement prises en charge à l’aide d’un nom d’utilisateur principal (UPN), d’Azure Active Directory (Azure AD) ou de la sécurité Active Directory.
* L’indexation de contenu riche dans les colonnes de base de données n’est pas prise en charge. Des exemples de ce type de contenu sont les analyses HTML, JSON, XML, BLOB et de document qui existent sous forme de liens dans les colonnes de base de données.

