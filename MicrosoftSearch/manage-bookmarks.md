---
title: Gérer des signets
ms.author: jeffkizn
author: jeffkizn
manager: parulm
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
ms.assetid: c0c814d0-f7e4-444e-b18e-09beb45c9322
description: Créer et mettre à jour des signets et des méthodes pour modifier en bloc les résultats de signet pour Microsoft Search
ms.openlocfilehash: 6a678464ec23c2d4c90190b6a02c0a73839b50ee
ms.sourcegitcommit: 41d28060238091455c7b8b011c67ae60c8a41f1f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/10/2020
ms.locfileid: "49619575"
---
# <a name="manage-bookmarks"></a>Gérer des signets

Les signets aident les utilisateurs à trouver rapidement des sites et des outils importants avec une recherche. Chaque signet inclut un titre, une URL, un ensemble de mots clés conviviaux pour déclencher le signet et une catégorie.

## <a name="what-makes-a-great-bookmark"></a>Qu’est-ce qu’un excellent signet

Un signet très important comporte quatre éléments clés :

1. **Titre** fort et instructif. But ne dépassant pas 8 mots ou environ 60 caractères maximum. Vous souhaitez que vos utilisateurs cliquent sur le titre et affichent le contenu, mais évitent les clickbait évidentes :
    - Bonnes : essayez les favoris de cette semaine Tasty dans le menu cafétéria. Le titre est clair, concis et intéressant, mais peut être surprometteur.
    - Mieux : le menu cafétéria de la semaine. Ne surpromet pas ou ne ressemble pas à une publicité.
    - Éviter : vous ne vous croirez pas dans le menu de la cafétéria cette semaine. Utilise clickbait clichés comme une publicité.
2. **Description** succincte, à savoir 300 caractères, qui résume l’objectif ou la fonctionnalité de la ressource liée.
3. Collection de **Mots clés** qui permettra aux utilisateurs de trouver le signet lors de la recherche. Nous vous suggérons au minimum cinq mots-clés. Incluez également les variantes que les utilisateurs de votre organisation peuvent utiliser, par exemple, le menu du restaurant, les menus du déjeuner et le menu café peuvent tous être des variantes pour le menu cafétéria.
4. Ensemble utile de **catégories** qui facilitent le tri et le filtrage des signets dans le centre d’administration. Vos utilisateurs ne voient jamais les catégories affectées.

## <a name="create-bookmark-answers"></a>Créer des réponses de signet

Dans le [Centre d’administration Microsoft 365](https://admin.microsoft.com/), accédez à [signets](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/bookmarks) et choisissez comment vous souhaitez créer de nouveaux signets :

- Ajouter des signets
- Importer des résultats SharePoint
- Ajout de signets et de signets suggérés par défaut
- Importer des signets
- Publier ou passer en revue les signets recommandés

### <a name="add-bookmarks"></a>Ajouter des signets

Les administrateurs et les administrateurs de recherche peuvent ajouter des signets dans le centre d’administration Microsoft 365. Les signets peuvent être publiés ou enregistrés en brouillon. La publication d’un signet actualise immédiatement l’index de recherche afin que les utilisateurs puissent commencer à le découvrir et à l’utiliser immédiatement. Vous pouvez également planifier un signet en spécifiant la date et l’heure à laquelle il sera publié.

- **Publié**: les signets sont disponibles pour les utilisateurs de l’organisation via Microsoft Search.
- **Brouillon**: les signets enregistrés en tant que brouillons ne sont pas disponibles pour vos utilisateurs. Utilisez cet État si vous ou d’autres parties prenantes souhaitez vérifier ou mettre à jour les signets avant de les publier.
- **Planifié**: signets qui seront publiés à la date et à l’heure spécifiées.

Vous pouvez utiliser l’extension de navigateur créateur de contenu Microsoft Search pour ajouter facilement des signets. Pour installer l’extension du navigateur, accédez au site que vous souhaitez ajouter en tant que signet, puis cliquez sur Ajouter dans l’extension.
Installez l’extension pour le serveur Edge et le chrome :

- Pour le chrome ou le chrome : accédez au [magasin Web chrome](https://chrome.google.com/webstore/detail/microsoft-search-content/nocnablpaoeecfmfnjoheefkogmleipm) et ajoutez l’extension.
- Pour le serveur Edge hérité : accédez au [Microsoft Store](https://www.microsoft.com/p/microsoft-search-content-creator/9nrqdbcbwq55?activetab=pivot:overviewtab) et ajoutez l’extension.

### <a name="import-sharepoint-results"></a>Importer des résultats SharePoint

Si votre organisation a configuré les résultats promus dans SharePoint, vous pouvez importer les titres, les URL et les descriptions des résultats promus pour votre client dans Microsoft Search et mettre le contenu importé à la disposition de vos utilisateurs. Dans la plupart des cas, l’importation des résultats SharePoint prend seulement quelques minutes. Si vous importez un grand nombre de résultats, cela peut prendre jusqu’à 48 heures. Il s’agit d’un moyen facile de remplir rapidement des résultats de recherche et de les mettre en service pour vos utilisateurs. Nous vous recommandons d’utiliser des résultats promus à partir de SharePoint comme référence pour comprendre comment nommer et créer des résultats de recherche pertinents.

### <a name="add-default-and-suggested-bookmarks"></a>Ajouter les signets suggérés et par défaut

Nous avons inclus des signets suggérés par défaut que vos utilisateurs peuvent trouver utiles, notamment des signets pour les RH, les avantages, le support informatique, la gestion des mots de passe et bien plus encore. Passez en revue, mettez à jour et publiez ces signets suggérés pour fournir des résultats de haute qualité à vos utilisateurs immédiatement.

Vos utilisateurs peuvent également suggérer des signets qui souhaiteraient ajouter à l’aide de liens de commentaire dans Microsoft Search. Leurs recommandations apparaîtront sous forme de signets suggérés.

### <a name="import-bookmarks"></a>Importer des signets

Utilisez la fonctionnalité d’importation pour accélérer et faciliter l’ajout ou la modification d’un grand nombre de signets. Utilisez-le pour :

- Ajouter des signets en bloc : ajoutez des détails dans le fichier de modèle de signets, puis importez-le.
- Modifier en bloc les signets : exporter des signets vers un fichier. csv, modifier les détails des signets dans le fichier exporté, puis importer le fichier modifié.

Voici quelques points importants relatifs au fichier de modèle :

- Ne jamais modifier les données de ces champs : *ID*, *Last modified* et *Last modified by*
- Si vous incluez l' *ID* d’un signet existant, il sera remplacé par les informations contenues dans le fichier d’importation.
- Pour les signets existants portant le même titre ou URL, le signet est mis à jour avec les informations contenues dans le fichier d’importation.
- Certains champs du fichier modèle ne sont pas obligatoires, et les champs obligatoires varient en fonction de l’état du signet.
- En fonction du champ d' *État* , les signets seront enregistrés en tant que brouillon, suggéré, programmé, exclu ou ils seront publiés automatiquement.
- Pour les partenaires qui gèrent plusieurs organisations, vous pouvez exporter vos signets d’une organisation et les importer dans un autre. Toutefois, vous devez supprimer les données de la colonne *ID* avant de procéder à l’importation.

### <a name="prevent-import-errors"></a>Éviter les erreurs d’importation

Une erreur se produit lorsqu’il manque des données obligatoires ou que celles-ci ne sont pas valides. Un fichier journal signalant les lignes et colonnes à corriger est alors généré. Apportez les modifications nécessaires et essayez à nouveau d’importer le fichier. Il est impossible d’importer ou d’enregistrer les signets tant que toutes les erreurs n’ont pas été résolues.

Pour éviter les erreurs, assurez-vous que votre fichier d’importation est correctement mis en forme et :

- qu’il inclut la ligne d’en-tête ainsi que toutes les colonnes qui se trouvaient dans le modèle d’importation ;
- que l’ordre des colonnes est le même que celui du modèle d’importation.
- Toutes les colonnes ont des valeurs, sauf les trois pouvant être vides : *ID*, *Last modified* et *Last modified by*
- La colonne *État* n’est pas vide, il s’agit des informations requises.
- Lors de l’importation de signets publiés, suggérés, planifiés ou brouillons, les colonnes *titre*, *URL* et *Mots clés* sont requises
- Lors de l’importation de signets exclus, la colonne *URL* est requise

Pour éviter les erreurs de duplication de signet à signet :

- N’utilisez pas d’URL en double pour différents signets. Si une URL est affectée à un autre signet et que vous essayez de la rajouter à partir d’un fichier d’importation, vous obtiendrez une erreur. Cela s’applique également aux URL en double pour d’autres types de réponses.
- Lors de la mise à jour de signets existants, utilisez la colonne *ID de signet* . Vous pouvez mettre à jour toute autre propriété d’un signet existant, telle que mot clé ou description, mais vous devez vous assurer que l' *ID de signet* se trouve dans la colonne appropriée du fichier d’importation. Si l' *ID de signet* est présent, il ne sera pas traité comme une nouvelle addition et ne sera pas traité comme une erreur.

### <a name="publish-or-review-recommended-bookmarks"></a>Publier ou passer en revue les signets recommandés

Pour réduire les tâches manuelles nécessaires à l’ajout de signets, Microsoft Search peut évaluer les liens SharePoint dans votre organisation et recommander des signets, et vous pouvez les consulter avant de les publier ou les configurer pour les publier automatiquement. Aucune configuration n’est nécessaire pour les signets recommandés, ils sont activés et configurés pour la publication automatique par défaut. Pour modifier ces paramètres à tout moment, sélectionnez **gérer les signets** pour ouvrir le panneau Paramètres du signet.

![Capture d’écran des paramètres de signet recommandés dans le portail d’administration Microsoft 365](media/bookmarks-recommendedsettings.png)

Si les signets recommandés sont activés, le moteur de recommandations évalue les sites SharePoint de votre organisation afin d’identifier les liens de trafic élevé. Après une période d’évaluation initiale, les signets recommandés seront publiés automatiquement ou ajoutés à la liste des signets suggérés. Le cycle suivant (période d’évaluation de 30 jours suivie par la publication automatique ou l’ajout de signets suggérés) commencera.

Nous suggérons aux administrateurs ou aux administrateurs de la recherche de consulter régulièrement ces signets suggérés ou publiés automatiquement. En outre, les signets recommandés n’incluent jamais les URL trouvées dans les signets publiés, suggérés, planifiés ou exclus existants.

Pour s’assurer que seuls les utilisateurs disposant d’un accès verront un signet recommandé dans leurs résultats de travail, une fonctionnalité de vérification d’accès est incluse pour tous les signets recommandés. Les utilisateurs qui ne sont pas autorisés à accéder à un site SharePoint ne verront jamais le signet recommandé pour ce site. Cette vérification d’accès est contrôlée par l’option **uniquement les personnes ayant accès à ce lien** dans le paramètre groupes pour chaque signet recommandé.

La vérification d’accès s’arrêtera si l’URL dans le signet recommandé ou le paramètre groupes est modifié.

Pour empêcher le moteur de recommandations de publier ou de suggérer un signet à un site particulier, vous pouvez ajouter l’URL à une liste exclue. Le moteur de recommandations ne publiera pas ou ne suggérera jamais un signet pour un site exclu ou une page dans un site exclu.

## <a name="about-keywords-and-reserved-keywords"></a>À propos des mots clés et des mots clés réservés

Un signet peut avoir plusieurs mots-clés et les signets peuvent partager le même mot-clé, mais le mot clé réservé ne peut pas être partagé. Un mot clé réservé est un terme unique ou une expression qui déclenche un signet spécifique. Un mot clé réservé ne peut être associé qu’à une seule réponse. Utilisez des mots clés réservés avec parcimonie.

## <a name="frequently-asked-questions"></a>Questions fréquemment posées

**Q : combien de temps faut-il pour qu’un signet soit visible dans Microsoft Search après sa publication ?**

**A :**  Un signet est disponible dans Microsoft Search immédiatement après la publication.

**Q : combien de temps faut-il pour qu’un signet recommandé apparaisse ?**

**A :**  Les signets recommandés ne s’affichent dans Microsoft Search que si les signets recommandés et la publication automatique sont activés. Pendant la période d’évaluation initiale, le moteur de recommandations évalue le trafic SharePoint pour identifier les signets appropriés, puis les publie automatiquement. Une fois publiés, ils deviennent disponibles immédiatement dans Microsoft Search.

**Q : Microsoft Search doit-il recommander des signets provenant de sites dans toutes les langues ?**

**A**: Oui, Microsoft Search peut recommander des signets à partir de n’importe quel site SharePoint interne, quelle que soit la langue.

**Q : puis-je arrêter l’affichage des signets recommandés dans les résultats de la recherche ?**

**A :** Pour arrêter l’affichage des signets recommandés, désactivez le paramètre publication automatique dans votre centre d’administration. Les signets recommandés sont ajoutés à la liste des signets suggérés.

**Q : Comment puis-je identifier un signet recommandé dans les résultats de recherche ou dans le centre d’administration ?**

**A :** Dans les résultats de la recherche, les signets recommandés incluent l’expression « recommandé pour vous » avant l’URL. Dans le centre d’administration, les signets de type extrait auront la valeur « SYSTEM ».

**Q : comment l’accès à un signet recommandé est-il géré ?**

**A**: un moteur d’accès développé par Microsoft détermine si l’URL de signet est accessible à un utilisateur particulier et affiche uniquement le signet recommandé à l’audience appropriée. Toutefois, si l’URL est modifiée ou si le paramètre groups est modifié, le moteur d’accès développé est désactivé.

**Q : que se passe-t-il si aucune action n’est effectuée sur les signets recommandés ajoutés à la liste proposée ?**

**A**: pour éviter un volume important de signets dans la liste proposée, un signet recommandé (propriétaire = système) sera vidé après 180 jours.

**Q : où puis-je trouver l’ID de l’application pour une application d’alimentation ?**

**A**: accédez au site applications puissantes et affichez le volet d’informations de l’application. En savoir plus sur [l’obtention d’un ID d’application](https://docs.microsoft.com/powerapps/maker/canvas-apps/get-sessionid#get-an-app-id).
