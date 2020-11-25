---
title: Connecteur de partage de fichiers
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
description: Configurer le connecteur de partage de fichiers pour Microsoft Search
ms.openlocfilehash: a95cfe90ca35a385bb9ce3a4c565c18c5a42ec80
ms.sourcegitcommit: 69a1c544cc8db364991cb58d7818d7158ff108b8
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/25/2020
ms.locfileid: "49408932"
---
# <a name="file-share-connector"></a>Connecteur de partage de fichiers

Avec le connecteur Graph du partage de fichiers, les utilisateurs de votre organisation peuvent effectuer des recherches dans des partages de fichiers Windows locaux.

Cet article est destiné aux administrateurs 365 de Microsoft ou toute personne qui configure, exécute et surveille un connecteur de partage de fichiers. Elle explique comment configurer les fonctionnalités de connecteur et de connecteur, ainsi que les restrictions et les techniques de résolution des problèmes.

## <a name="install-graph-connector-agent"></a>Installer l’agent Graph Connector

Pour indexer vos partages de fichiers Windows, vous devez installer et inscrire [Graph Connector agent](on-prem-agent.md) .

## <a name="content-requirements"></a>Exigences en matière de contenu

### <a name="file-types"></a>Types de fichiers

Le contenu des formats suivants peut être indexé et recherché : DOC, DOCM, DOCX, DOT, DOTX, EML, GIF, HTML, JPEG, MHT, MHTML, MSG, NWS, OBD, OBT, ODP, ODS, ODT, ONE, PDF, POT, PPS, PPT, PPTM, PPTX, TXT, XLB, XLC, XLSB, XLS, XLSX, XLT, XLXM, XML, XPS et ZIP. Seul le contenu textuel de ces formats est indexé. Tout le contenu multimédia est ignoré. Pour tout fichier qui n’appartient pas à ce format, les métadonnées seules sont indexées.

### <a name="file-size-limits"></a>Limites de taille de fichier

La taille maximale de fichier prise en charge est de 100 Mo. Les fichiers qui dépassent 100 Mo ne sont pas indexés. La limite de taille post-traitée maximale est de 4 Mo. Le traitement s’arrête lorsque la taille d’un fichier atteint 4 Mo. Par conséquent, il se peut que certaines expressions présentes dans le fichier ne fonctionnent pas pour la recherche.

## <a name="connect-to-a-data-source"></a>Se connecter à une source de données

Sur la page **se connecter à la source de données** , sélectionnez **partage de fichiers** et indiquez le nom, l’ID de connexion et la description. Sur la page suivante, indiquez le chemin d’accès au partage de fichiers et sélectionnez l’agent de connecteur Graph précédemment installé. Entrez les informations d’identification pour un compte d’utilisateur [Microsoft Windows](https://microsoft.com/windows) avec un accès en lecture à tous les fichiers du partage de fichiers.

## <a name="preserve-last-access-time"></a>Conserver l’heure du dernier accès

Lorsque le connecteur tente d’analyser un fichier, le champ « heure du dernier accès » dans ses métadonnées est mis à jour. Si vous utilisez ce champ pour une solution d’archivage et de sauvegarde et que vous ne souhaitez pas le mettre à jour lorsque le connecteur y accède, vous pouvez configurer cette option dans la page **Paramètres avancés** .

## <a name="manage-search-permissions"></a>Gérer les autorisations de recherche

Vous pouvez limiter l’autorisation de recherche de n’importe quel fichier basé sur des listes de contrôle d’accès de partage ou des listes de contrôle d’accès NTFS (New Technology File System). Si vous souhaitez utiliser les listes de contrôle d’accès de partage, sélectionnez l’option appropriée sur la page **Paramètres avancés** . Si vous souhaitez utiliser des listes de contrôle d’accès NTFS, sélectionnez l’option appropriée dans la page **gérer les autorisations de recherche** .

## <a name="assign-property-labels"></a>Affecter des étiquettes de propriété

Vous pouvez affecter une propriété source à chaque étiquette en choisissant dans un menu d’options. Si cette étape n’est pas obligatoire, le fait d’avoir des étiquettes de propriété améliore la pertinence de la recherche et garantit des résultats de recherche plus précis pour les utilisateurs finaux.

## <a name="manage-schema"></a>Gérer le schéma

Dans l' **écran gérer le schéma** , vous avez la possibilité de modifier les attributs de schéma (**Queryable**, pouvant faire l’objet d’une **recherche**, l' **extraction** et l' **refinable**) associés aux propriétés, d’ajouter des alias facultatifs et de choisir la propriété **content** .

## <a name="set-the-refresh-schedule"></a>Définir la planification d’actualisation

L’intervalle de planification des actualisations par défaut recommandé est de 15 minutes, mais vous pouvez le modifier en fonction de vos préférences.
