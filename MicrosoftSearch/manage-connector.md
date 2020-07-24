---
title: Gérer les connecteurs Microsoft Graph pour Microsoft Search
ms.author: mounika.narayanan
author: monaray
manager: mnirkhe
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: Gérer les connecteurs Microsoft Graph pour Microsoft Search.
ms.openlocfilehash: dfbc58d7e51fca0491dc7e4452ba4312ff3dfd69
ms.sourcegitcommit: f2323c43fc732890213223efac32006df5b92c28
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/23/2020
ms.locfileid: "45388002"
---
# <a name="manage-your-connector-for-microsoft-search"></a>Gérer votre connecteur pour Microsoft Search

Pour accéder à vos connecteurs et les gérer, vous devez être désigné en tant qu’administrateur de recherche pour votre client. Contactez votre administrateur client pour vous approvisionner pour le rôle d’administrateur de recherche.

## <a name="get-started"></a>Prise en main

Accédez à l' [onglet Connecteurs](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/Connectors) dans le [Centre d’administration Microsoft 365](https://admin.microsoft.com).

Pour chaque type de connecteur, le [Centre d’administration Microsoft 365](https://admin.microsoft.com) prend en charge les opérations indiquées dans le tableau suivant :

Opération | Connecteur créé par Microsoft | Connecteur partenaire ou personnalisé
--- | --- | ---
Ajouter une connexion | : heavy_check_mark : (voir [Configure Your Microsoft-Built Connector](configure-connector.md)) | : x : (reportez-vous à votre partenaire ou à l’expérience utilisateur d’administration des connecteurs personnalisés)
Supprimer une connexion | : heavy_check_mark : | : heavy_check_mark :
Modifier une connexion publiée | : heavy_check_mark : nom<br></br> : heavy_check_mark : description<br></br> : heavy_check_mark : informations d’identification d’authentification pour votre source de données externe<br></br> : heavy_check_mark : informations d’identification de la passerelle pour votre source de données locale<br></br> : heavy_check_mark : actualiser la planification<br></br> | : heavy_check_mark : nom<br></br> : heavy_check_mark : description
Modifier une connexion brouillon | : heavy_check_mark : | ActiveX

## <a name="monitor-your-connection-status"></a>Surveiller l’état de votre connexion

Une fois que vous avez créé une connexion, le nombre d’éléments traités est affiché sous l’onglet **connecteurs** de la page **Microsoft Search** . Une fois l’analyse complète initiale terminée, la progression des analyses incrémentielles périodiques s’affiche. Cette page fournit des informations sur les opérations quotidiennes du connecteur et une vue d’ensemble des journaux et de l’historique des erreurs.

Quatre États apparaissent dans la colonne d' **État** pour chaque connexion :

* **Synchronisation**. Le connecteur analyse les données à partir de la source pour indexer les éléments existants et effectuer toutes les mises à jour.

* **Activé**: la connexion est activée et il n’y a aucune analyse active en cours d’exécution sur celle-ci. **Heure de la dernière synchronisation** indique la date de la dernière analyse réussie. La connexion est aussi récente que la dernière heure de synchronisation.

* **Suspendu**. Les analyses sont suspendues par les administrateurs via l’option pause. L’analyse suivante n’est exécutée qu’en cas de reprise manuelle. Toutefois, les données de cette connexion continuent d’être recherchées.

* **Échec**. Échec critique de la connexion. Cette erreur nécessite une intervention manuelle. L’administrateur doit prendre les mesures appropriées en fonction du message d’erreur qui s’affiche. Les données qui ont été indexées jusqu’à ce que l’erreur se produise soient utilisables dans une requête.

### <a name="monitor-errors"></a>Surveiller les erreurs

Pour chaque **connecteur actif** sous l’onglet **connecteurs** , toutes les erreurs d’analyse existantes apparaissent sous l’onglet **erreur** . L’onglet répertorie les codes d’erreur, le décompte de chaque option de téléchargement et le journal des erreurs. Consultez l’exemple dans l’image suivante. Sélectionnez un **code d’erreur** pour afficher les détails de l’erreur.

![Liste des connecteurs avec un connecteur sélectionné et volet de détails affichant 3 erreurs pour ce connecteur.](media/errormonitoring1.png)

Pour afficher les détails spécifiques d’une erreur, sélectionnez son code d’erreur. Un écran s’affiche avec les détails de l’erreur et un lien. Les erreurs les plus récentes apparaissent en haut. Voir l’exemple dans le tableau suivant.

![Liste des connecteurs avec un connecteur sélectionné et volet de détails affichant la liste des erreurs pour le connecteur. ](media/errormonitoring2.png)

Voici la liste des différentes erreurs qui peuvent apparaître contre n’importe quelle connexion. Si ces solutions ne fonctionnent pas, contactez le support technique ou envoyez-nous [vos commentaires](connectors-feedback.md).

Code d’erreur | Message d’erreur | Solution
--- | --- | ---
1000 | La source de données n’est pas disponible. Vérifiez votre connexion Internet ou assurez-vous que la source de données est toujours accessible par le connecteur. | Cette erreur se produit lorsque la source de données n’est pas accessible à cause d’un problème réseau ou lorsque la source de données elle-même est supprimée, déplacée ou renommée. Vérifiez si les détails de la source de données fournis sont toujours valides.
1001 | Impossible de mettre à jour les données, car la source de données limite le connecteur. | Pour ne pas limiter la source de données, vérifiez si les limites de l’étendue peuvent être augmentées ou patienter jusqu’à ce qu’un temps de trafic élevé de la journée soit moindre.
1002 | Impossible de s’authentifier auprès de la source de données. Vérifiez que les informations d’identification associées à cette source de données sont correctes. | Cliquez sur **modifier** pour mettre à jour les informations d’identification d’authentification.
1003 | Le compte associé au connecteur n’est pas autorisé à accéder à l’élément. |  Assurez-vous que le compte approprié a accès à l’élément que vous souhaitez indexer.
1004 | Impossible d’atteindre la passerelle de données locale. Assurez-vous que le service de passerelle est en cours d’exécution et que les détails de la passerelle sont mis à jour dans la configuration de connexion. | Vérifiez l’ordinateur à l’aide de la passerelle, ouvrez l’application passerelle Power BI et assurez-vous que la passerelle est en cours d’exécution. Vérifiez que la passerelle utilise le même compte d’administrateur que Microsoft Search, puis assurez-vous que tous les détails de la passerelle sont tous mis à jour dans la configuration de la connexion.
1005 | Les informations d’identification associées à cette source de données ont expiré. Renouvelez les informations d’identification et mettez à jour la connexion. | Cliquez sur **modifier** pour mettre à jour les informations d’identification d’authentification.
1006 | La version de votre passerelle est obsolète et ne prend plus en charge ce connecteur. Vous devrez mettre à jour la passerelle. | Consultez la visite [installer une passerelle de données locale](https://docs.microsoft.com/data-integration/gateway/service-gateway-install) pour télécharger et installer la dernière version de la passerelle Power bi sur l’ordinateur contenant la passerelle.
1007 | Aucune licence Power BI valide détectée. Vous avez besoin d’une licence Power BI valide pour effectuer cette analyse. | Vous avez besoin d’une licence Power BI valide pour effectuer cette analyse. Vérifiez que votre organisation dispose d’une licence valide. Si c’est le cas, réessayez. Si ce n’est pas le cas, obtenez une licence, puis réessayez.
1008 | L’utilisation totale du quota de votre client a atteint sa limite. Essayez de supprimer une connexion pour libérer une partie de votre quota ou Ajustez vos filtres d’ingestion afin de réduire le nombre de données. | Essayez de supprimer une connexion pour libérer une partie de votre quota ou Ajustez vos filtres d’ingestion afin de réduire le nombre de données. Si cela ne résout pas le problème, contactez le support Microsoft.
2001 | L’indexation est limitée en raison d’un grand nombre de mises à jour dans la file d’attente. En fonction de la file d’attente, l’exécution des mises à jour peut prendre un certain temps. | Veuillez patienter jusqu’à ce que la file d’attente soit effacée.
2002 | Échec de l’indexation en raison d’une mise en forme d’élément non prise en charge. | Pour plus d’informations, reportez-vous à la documentation spécifique au connecteur.
2003 | Échec de l’indexation en raison d’un contenu d’élément non pris en charge. | Pour plus d’informations, reportez-vous à la documentation spécifique au connecteur.
5000 | Un problème est survenu. Si cela persiste, contactez le support technique. |

## <a name="preview-limitations"></a>Limitations de l’aperçu

* Lorsque vous **publiez** un connecteur créé par Microsoft, la création de la connexion peut prendre quelques minutes. Pendant ce temps, la connexion indique son état en attente. En outre, il n’existe pas d’actualisation automatique, vous devez donc procéder à une actualisation manuelle.

* Le [Centre d’administration Microsoft 365](https://admin.microsoft.com) ne prend pas en charge l’affichage et la modification du **schéma de recherche** après la publication d’une connexion. Pour modifier le schéma de recherche, supprimez votre connexion, puis créez-en une nouvelle.

* Lorsque vous gérez la planification d' **actualisation**de votre connexion, le nombre d’éléments synchronisés au cours de chaque session s’affiche. Toutefois, l’historique de synchronisation n’est pas disponible.
