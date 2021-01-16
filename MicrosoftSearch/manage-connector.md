---
title: Gérer les connecteurs Microsoft Graph pour Microsoft Search (recherche Microsoft)
ms.author: monaray
author: monaray97
manager: mnirkhe
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: Gérer les connecteurs Microsoft Graph pour Microsoft Search (recherche Microsoft).
ms.openlocfilehash: cf1231f8003d166977398ef4bdcc1ad12104dd05
ms.sourcegitcommit: d22fe2a34d7efe2dd5bbb456f0d00eb5f6c7608c
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/16/2021
ms.locfileid: "49880608"
---
<!-- markdownlint-disable no-inline-html -->

# <a name="manage-your-connections-for-microsoft-search"></a>Gérer vos connexions pour Microsoft Search (recherche Microsoft)

Pour accéder à vos connecteurs et les gérer, vous devez être désigné en tant qu’administrateur de recherche pour votre client. Contactez votre administrateur client pour vous fournir le rôle d’administrateur de recherche.

## <a name="get-started"></a>Prise en main

Accédez à [l’onglet Connecteurs](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/Connectors) dans le [Centre d’administration Microsoft 365.](https://admin.microsoft.com)

Pour chaque type de connecteur, le Centre [d’administration Microsoft 365](https://admin.microsoft.com) prend en charge les opérations indiquées dans le tableau suivant :

Opération | Connecteur créé par Microsoft | Connecteur partenaire ou personnalisé
--- | --- | ---
Ajouter une connexion | :heavy_check_mark : (voir [Configurer votre connecteur créé par Microsoft)](configure-connector.md) | :x : (faire référence à l’UX de votre partenaire ou de votre connecteur personnalisé)
Supprimer une connexion | :heavy_check_mark: | :heavy_check_mark:
Modifier une connexion publiée | :heavy_check_mark: Nom<br></br> :heavy_check_mark : Description<br></br> :heavy_check_mark : informations d’identification d’authentification pour votre source de données externe<br></br> :heavy_check_mark : informations d’identification de passerelle pour votre source de données sur site<br></br> :heavy_check_mark : planification d’actualisation<br></br> | :heavy_check_mark: Nom<br></br> :heavy_check_mark : Description
Modifier un brouillon de connexion | :heavy_check_mark: | :x:

## <a name="monitor-your-connection-status"></a>Surveiller l’état de votre connexion

Après avoir créé une connexion, le nombre d’éléments **traitées** s’affiche sous l’onglet Connecteurs de la page **Recherche Microsoft.** Une fois l’analyse complète initiale terminée, la progression des analyses incrémentielles périodiques s’affiche. Cette page fournit des informations sur les opérations quotidiennes du connecteur et une vue d’ensemble des journaux et de l’historique des erreurs.

Quatre états s’affiche dans la colonne **État** par rapport à chaque connexion :

* **Synchronisation.** Le connecteur analyse les données de la source pour indexer les éléments existants et effectuer des mises à jour.

* **Activé :** la connexion est activée et aucune analyse active n’est en cours d’exécution. **L’heure de la** dernière synchronisation indique à quel moment la dernière analyse réussie s’est produite. La connexion est aussi nouvelle que l’heure de la dernière synchronisation.

* **Suspendu**. Les analyses sont suspendues par les administrateurs via l’option de pause. L’analyse suivante s’exécute uniquement lorsqu’elle est reprise manuellement. Toutefois, les données de cette connexion sont toujours utilisables dans une recherche.

* **Échec**. La connexion a connu une défaillance critique. Cette erreur nécessite une intervention manuelle. L’administrateur doit prendre les mesures appropriées en fonction du message d’erreur affiché. Les données qui ont été indexées jusqu’à ce que l’erreur se soit produite sont utilisables dans une recherche.

### <a name="view-your-last-crawl-info"></a>Afficher vos dernières informations d’analyse

Une fois la première analyse incrémentielle ou complète terminée, les dernières valeurs de données d’analyse sont affichées sous le dernier en-tête d’analyse dans le volet de détails. S’il n’y a pas eu de dernière analyse en cours d’analyse, aucune information ne s’y trouvait sous le dernier en-tête d’analyse. Ces informations sur la dernière analyse vous aideront à obtenir des informations sur la façon dont l’analyse a été effectuée et à effectuer les étapes nécessaires, le cas échéant.

Les dernières valeurs d’analyse suivantes seront disponibles pour chaque connexion :

Valeur | Description
--- | ---
Terminé à l' | Date et heure de fin de la dernière analyse
Type | Analyse incrémentielle ou complète
Durée | combien de temps la dernière analyse a-t-elle pris pour se terminer
Réussites | Nombre d’éléments qui ont été correctement ingérés lors de la dernière analyse
Erreurs | Nombre d’éléments qui ont fait l’objet d’une erreur lors de la dernière analyse

### <a name="monitor-errors"></a>Surveiller les erreurs

Pour chaque **connecteur actif sous** l’onglet **Connecteurs,** toutes les erreurs d’analyse existantes s’affiche sous **l’onglet** Erreur. L’onglet répertorie les codes d’erreur, le nombre de chacun et les options de téléchargement du journal des erreurs. Voir l’exemple dans l’image suivante. Sélectionnez **un code d’erreur** pour afficher les détails de l’erreur.

![Liste des connecteurs avec un connecteur sélectionné et volet d’informations affichant 3 erreurs pour ce connecteur.](media/errormonitoring1.png)

Pour afficher les détails spécifiques d’une erreur, sélectionnez son code d’erreur. Un écran s’affiche avec les détails de l’erreur et un lien. Les erreurs les plus récentes apparaissent en haut. Voir l’exemple dans le tableau suivant.

![Liste des connecteurs avec un connecteur sélectionné et volet d’informations affichant la liste des erreurs pour le connecteur.](media/errormonitoring2.png)

Vous trouverez ci-dessous la liste des différentes erreurs qui peuvent apparaître sur n’importe quelle connexion.

Code d’erreur | Message d’erreur | Solution
--- | --- | ---
1000 | La source de données n’est pas disponible. Vérifiez votre connexion Internet ou assurez-vous que la source de données est toujours accessible par le connecteur. | Cette erreur se produit lorsque la source de données n’est pas accessible en raison d’un problème réseau ou lorsque la source de données elle-même est supprimée, déplacée ou renommée. Vérifiez si les détails de la source de données fournis sont toujours valides.
1001 | Ne peut pas mettre à jour les données, car la source de données limitation le connecteur. | Pour limiter la source de données, vérifiez si ses limites d’échelle peuvent être augmentées ou patientez jusqu’à une heure moins longue du trafic de la journée.
1002 | Ne peut pas s’authentifier auprès de la source de données. Vérifiez que les informations d’identification associées à cette source de données sont correctes. | Cliquez sur **Modifier** pour mettre à jour les informations d’authentification.
1003 | Le compte associé au connecteur n’est pas autorisé à accéder à l’élément. |  Assurez-vous que le compte approprié a accès à l’élément que vous souhaitez indexer.
1004 | Impossible d’atteindre la passerelle de données sur site. Assurez-vous que le service de passerelle est en cours d’exécution et que les détails de la passerelle sont mis à jour dans la configuration de connexion. | Vérifiez l’ordinateur avec la passerelle, ouvrez l’application Power BI Gateway et assurez-vous que la passerelle est en cours d’exécution. Vérifiez que la passerelle utilise le même compte d’administrateur que Microsoft Search (recherche Microsoft), puis assurez-vous que tous les détails de la passerelle sont tous mis à jour dans la configuration de connexion.
1005 | Les informations d’identification associées à cette source de données ont expiré. Renouvelez les informations d’identification et mettez à jour la connexion. | Cliquez sur **Modifier** pour mettre à jour les informations d’authentification.
1006 | La version de votre passerelle n’est plus à jour et ne prend plus en charge ce connecteur. Vous devrez mettre à jour la passerelle. | Visitez Installer [une passerelle](https://docs.microsoft.com/data-integration/gateway/service-gateway-install) de données sur site pour télécharger et installer la dernière version de la passerelle Power BI sur l’ordinateur contenant la passerelle.
1007 | Aucune licence Power BI valide n’est détectée. Vous avez besoin d’une licence Power BI valide pour effectuer cette analyse. | Vous avez besoin d’une licence Power BI valide pour effectuer cette analyse. Vérifiez que votre organisation dispose d’une licence valide. Si c’est le cas, essayez à nouveau. Si ce n’est pas le cas, obtenez une licence, puis essayez à nouveau.
1008 | L’utilisation totale du quota de votre client a atteint sa limite. Essayez de supprimer une connexion pour libérer une partie de votre quota ou ajustez vos filtres d’ingestion afin d’apporter moins de données. | Essayez de supprimer une connexion pour libérer une partie de votre quota ou ajustez vos filtres d’ingestion afin d’apporter moins de données. Si ceux-ci ne résolvent pas le problème, contactez le support Microsoft.
2001 | L’indexation est limitée en raison d’un grand nombre de mises à jour dans la file d’attente. En fonction de la file d’attente, la fin des mises à jour peut prendre un certain temps. | Veuillez patienter jusqu’à ce que la file d’attente soit effacée.
2002 | L’indexation a échoué en raison d’une mise en forme d’élément non pris en compte. | Pour plus d’informations, voir la documentation spécifique au connecteur.
2003 | L’indexation a échoué en raison d’un contenu d’élément non pris en compte. | Pour plus d’informations, voir la documentation spécifique au connecteur.
2010 | Cette connexion n’est plus valide en raison d’une mise à jour réalisée par Microsoft. Supprimez la connexion et créez-en une. | Supprimez la connexion et créez-en une.
5000 | Un problème s’est passé. Si cela se poursuit, contactez le support technique. |

## <a name="monitor-your-index-quota-utilization"></a>Surveiller l’utilisation de votre quota d’index

Le quota d’index et la consommation disponibles sont affichés sur la page d’accueil des connecteurs.

![Barre d’utilisation du quota d’index](media/quota_utilization.png)

>[!NOTE]
>Pendant la période d’aperçu, chaque organisation qui essaie des connecteurs Graph a été fournie avec un quota fixe gratuit de 2 millions d’éléments sur toutes les connexions. Les connecteurs Graph étant généralement disponibles, le quota gratuit expirera le 1er février 2021 pour les organisations qui ont utilisé des connecteurs Graph en prévisualisation.
>Les connecteurs Graph créés par Microsoft et étiquetés comme « [Aperçu](connectors-preview.md) » ne seront pas inclus dans le quota d’index facturé total pour votre organisation. Toutefois, il est comptabilisé dans le nombre maximum de 10 connexions que vous pouvez configurer pour votre organisation et le nombre maximum de 7 millions d’éléments que votre organisation peut indexer entre les connexions ; Chaque connexion est limitée à 700 000 éléments. 

La barre d’utilisation des quotas indiquera différents états en fonction de la consommation de quota par votre organisation :

État | Consommation de quota
--- | ---
Normal | 1-69%
Élevé | 70-89%
Critique | 90%-99%
Complet | 100 %

Le nombre d’éléments indexés s’affiche également avec chaque connexion. Le nombre d’éléments indexés par chaque connexion contribue au quota total disponible pour votre organisation.

Lorsque le quota d’index est dépassé pour votre organisation, toutes les connexions actives sont touchées et ces connexions fonctionnent dans un état **dépassé** limite. Dans cet état, vos connexions actives  

* Ne sera pas en mesure d’ajouter de nouveaux éléments.

* Sera en mesure de mettre à jour ou de supprimer des éléments existants.

Pour résoudre ce problème, vous pouvez :

* Découvrez comment acheter un quota d’index pour votre organisation en matière de [licences et de tarification.](licensing.md)

* Identifiez les connexions qui ont trop de contenu en cours d’ingestion et mettez-les à jour pour indexer moins d’éléments afin de faire de la place pour le quota. Pour mettre à jour la connexion, vous devez supprimer et créer une connexion avec un nouveau filtre d’ingestion qui apporte moins d’éléments.

* Supprimer définitivement une ou plusieurs connexions

## <a name="limitations"></a>Limites

* Lorsque vous **publiez** un connecteur microsoft, la création de la connexion peut prendre quelques minutes. Pendant ce temps, la connexion affiche son état en attente.

* Le [Centre d’administration Microsoft 365](https://admin.microsoft.com) ne prend pas en charge la modification du schéma de recherche après la publication d’une connexion.  Pour modifier le schéma de recherche, supprimez votre connexion, puis créez-en une nouvelle.

* Le débit d’ingestion est limitée à environ quatre éléments par seconde.

* Il n’existe aucune prise en charge des mises à jour de schéma. Après avoir créé une configuration de connexion, il n’existe aucun moyen de mettre à jour le schéma. Vous pouvez uniquement supprimer et re-créer la connexion.

* Il existe une limite de connexions. Chaque client peut créer jusqu’à 10 connexions.

* La prise en charge de la modification de la connexion n’est pas disponible. Une fois la connexion créée, vous ne pouvez pas la modifier. Si vous devez modifier des détails, vous devez supprimer et recréer la connexion.
