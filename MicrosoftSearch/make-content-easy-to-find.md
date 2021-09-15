---
title: Faciliter l’accès au contenu à l’aide de la fonctionnalité Recherche Microsoft
ms.author: anfowler
author: adefowler
manager: mnirkhe
ms.audience: Admin
ms.topic: article
ms.service: mssearch
ms.localizationpriority: medium
search.appverid:
- BFB160
- MET150
- MOE150
description: Créez des signets, des emplacements et des Q&R pour accéder facilement au contenu de votre organisation.
ms.openlocfilehash: 77b6507c7643e6cf2176f37a9a2cf0def1c640ba
ms.sourcegitcommit: ca5ee826ba4f4bb9b9baabc9ae8a130011c2a3d0
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/15/2021
ms.locfileid: "59375856"
---
# <a name="make-content-easy-to-find"></a>Faciliter l’accès au contenu

La fonctionnalité Recherche Microsoft aide les utilisateurs à accéder à du contenu pertinent. Façon sécuritaire d’effectuer des recherches sur votre intranet autant que du contenu web. Ce type d’intégration web et sur les organisations est uniquement disponible auprès de Microsoft. Avec la recherche Microsoft, les administrateurs utilisent leur connaissance de l’organisation pour permettre à ses utilisateurs d’accéder facilement à du contenu pertinent. 

## <a name="components-that-find-content"></a>Composants qui trouvent du contenu
Dans Recherche Microsoft, les administrateurs créent des signets, [](manage-bookmarks.md) [PowerApps,](integrate-powerapps.md) [](manage-locations.md) [Q&A](manage-qas.md)et des emplacements qui facilitent la recherche de contenu. Chacun de ces composants de recherche comprend un titre, une URL et un ensemble de mots clés qui le déclenchent.

## <a name="bookmarks"></a>Signets
Vous pouvez créer [des signets](manage-bookmarks.md) en quelques étapes seulement. Chaque signet comprend un titre, une URL et un ensemble de mots clés qui le déclenchent. Un signet peut avoir plusieurs mots clés et plusieurs signets peuvent partager le même mot clé. Toutefois, les mots clés réservés ne peuvent pas être partagés. Lorsque vous créez ou modifiez un signet, l’index de recherche est actualisé et le signet est immédiatement disponible pour les utilisateurs.

Si votre organisation a **mis en** place des résultats promus dans [SharePoint,](http://sharepoint.com/)vous pouvez importer ces résultats dans Recherche Microsoft. Avec les résultats promus, vous pouvez rapidement remplir les résultats de la recherche, mettre le contenu à la disposition des utilisateurs et rendre Recherche Microsoft plus efficace dès que vous le définissez. Nous vous recommandons d’utiliser les résultats promus de SharePoint comme référence pour apprendre à nommer et créer des résultats de recherche pertinents. 

### <a name="add-or-edit-bookmarks-by-using-browser-extensions"></a>Ajouter ou modifier des signets à l’aide d’extensions de navigateur
Les administrateurs de recherche peuvent facilement créer du contenu de recherche en utilisant des extensions de navigateur. Pour ajouter le site en tant que signet, installez l’extension de navigateur. Ensuite, allez sur le site et ajoutez-le en tant que signet. Pour plus d’informations, [voir Gérer les signets.](manage-bookmarks.md)

Actuellement, les extensions de navigateur sont disponibles [pour Microsoft Edge](https://www.microsoft.com/windows/microsoft-edge) et [Google Chrome](https://www.google.com): 
- Pour télécharger l’extension Edge, go to the [Microsoft Store](https://www.microsoft.com/p/microsoft-search-content-creator/9nrqdbcbwq55?activetab=pivot:overviewtab).
- Pour télécharger l’extension Chrome, allez dans le [magasin web Chrome.](https://chrome.google.com/webstore/detail/microsoft-search-content/nocnablpaoeecfmfnjoheefkogmleipm)

## <a name="powerapps"></a>PowerApps

En ajoutant des [PowerApps existantes](integrate-powerapps.md) à vos signets, les utilisateurs peuvent effectuer des tâches [telles](manage-bookmarks.md)que la saisie de congés ou la déclaration de dépenses. 

Avec [PowerApps,](integrate-powerapps.md)vous pouvez créer des applications professionnelles qui s’exécutent dans un navigateur, sur un téléphone ou une tablette. Aucune expérience de codage n’est requise. PowerApps fonctionne dans n’importe quel navigateur et sur n’importe quel appareil. L’ajout prend moins d’une minute. Pour en savoir plus sur PowerApps, consultez les articles suivants :
- [Formation guidée](/learn/browse/?products=powerapps)
- [Documentation PowerApps](/powerapps/maker/canvas-apps/get-sessionid)
- [Accueil PowerApps](https://make.preview.powerapps.com/environments/839eace6-59ab-4243-97ec-a5b8fcc104e4/home)

### <a name="add-a-powerapp-to-a-bookmark"></a>Ajouter une application PowerApp à un signet

1. Recherchez [l’ID d’application](/powerapps/maker/canvas-apps/get-sessionid#get-an-app-id) pour l’application PowerApp que vous souhaitez ajouter.
1. Dans le Microsoft 365 [d’administration,](https://admin.microsoft.com) Paramètres  >  **Recherche Microsoft**. 
1. Ajoutez un nouveau signet ou accédez à un signet existant auquel vous souhaitez ajouter une application PowerApp.
1. Dans **les paramètres de signet,** **sélectionnez Power App.** Ensuite, **sélectionnez Ajouter une application Power.**
1. Entrez **l’ID de l’application.** La hauteur et la largeur s’ajustent automatiquement. [Les signets](manage-bookmarks.md) peuvent prendre en charge les orientations portrait et paysage, mais actuellement la taille ne peut pas être modifiée. Pour faciliter le test, l’aperçu de signet affiche un PowerApp entièrement fonctionnel.
1. Sélectionnez **Publier** ou **Enregistrer en tant que brouillon**.

## <a name="qa"></a>Q&R

La création [d’une&A est](manage-qas.md) comme la création [de signets.](manage-bookmarks.md) Avec Q&R, vous pouvez fournir des réponses aux questions des utilisateurs au lieu d’un simple lien vers la page web. Vous pouvez formater les réponses en texte enrichi à l’aide des outils disponibles. Si un signet et un signet&un partage du même mot clé, le résultat du signet s’affiche en premier. Comme les signets, l’index de&A est actualisé immédiatement après l’ajout ou la modification d’une&A. 

### <a name="supported-html-tags"></a>Balises HTML pris en charge

Vous pouvez utiliser du contenu HTML ou ajouter des balises HTML à votre réponse ou description. Ces balises HTML sont prises en charge :
 
- blockquote
- div
- em
- H1, h2, h3 et h4
- ol, ul et li
- p
- Pre
- span
- Fort
- table, thead, tbody, tr, th et td
- u
- a
- code
- br
- hr
- img

Les balises non pris en compte sont ignorées ou affichées en tant que texte. Veillez à avoir un aperçu de vos cartes.

> [!Note]
> Vous ne pouvez pas importer des éléments Q&A s’il existe des erreurs dans le fichier de modèle. Pour éviter les erreurs, assurez-vous que votre fichier d’importation est correctement formaté et qu’il inclut toutes les informations requises. Voir plus d’informations sur la façon [d’éviter les erreurs d’importation.](#prevent-import-errors)

## <a name="locations"></a>Emplacements

Avec [Locations,](manage-locations.md)vos utilisateurs peuvent trouver des adresses et localiser les bâtiments de votre organisation. La **fonctionnalité Emplacements** fournit un emplacement précis pour les bureaux, les campus et les bâtiments, ainsi que des instructions et la navigation. Pour obtenir de meilleurs résultats, les administrateurs doivent ajouter tous les emplacements importants de leur organisation Recherche Microsoft. Contrairement [aux signets](manage-bookmarks.md) [et aux signets&A,](manage-qas.md)l’index des emplacements n’est pas actualisé immédiatement. L’apparition d’emplacements nouveaux ou modifiés dans les résultats de la recherche peut prendre plusieurs heures.

## <a name="get-started"></a>Prise en main
Pour savoir ce dont vos utilisateurs ont besoin et faciliter la découverte de ces informations, essayez certaines de ces méthodes :

- Utilisez les journaux de recherche intranet pour identifier les sites et les pages qui génèrent le plus de trafic.
- Identifiez les applications, les sites et les outils utilisés sur une base quotidienne ou hebdomadaire.
- Trouvez des liens directs pour les avantages sociaux des employés.
- Identifiez les stratégies et processus que les utilisateurs doivent connaître.
- Déterminez qui les utilisateurs contactent pour obtenir de l’aide et comment ils le font.
- Obtenez des informations qui sont nécessaires de manière récurrente, soit de manière annuelle, soit en fonction des cycles d’entreprise. Par exemple, les personnes qui recherchent des outils pour réserver des congés ou des mises à jour financières trimestrielles.
- Collecter des stratégies pour les utilisateurs régionaux ou mobiles. Par exemple, les avantages varient en fonction de l’emplacement.
- Déterminer les sites internes et les informations pour les recherches web courantes. Par exemple, le trafic, les informations de transport public, la météo locale, les remises disponibles auprès des partenaires de l’entreprise et les programmes de santé et de santé.
- Trouvez des informations sur les événements, conférences ou séminaires parrainés par l’entreprise.
- Effectuez des recherches sur des sujets courants liés à l’informatique, aux ressources humaines et au support technique ainsi que les questions fréquentes (FAQ) et leurs réponses.

## <a name="involve-smes-and-users"></a>Impliquer des PME et des utilisateurs
Dans une organisation, les utilisateurs recherchent une gamme de sujets simples à complexes. Les adresses de bureau et les avantages des employés sont des exemples simples. Les exemples complexes sont de nouveaux processus de travail, des informations techniques et du contenu de procédure. Pour créer ou trouver une telle variété de contenu, vous avez besoin d’une expertise dans différents champs, sujets et technologies. 

La plupart des administrateurs de recherche n’ont pas de connaissances spécifiques sur chaque sujet. Pour mettre à l’échelle la quantité de contenu disponible sans l’aide de ressources externes, recherchez des connaissances et des connaissances d’autres membres de votre organisation.

### <a name="get-content-from-smes"></a>Obtenir du contenu à partir de PME
Tirez parti des experts techniques de votre organisation, notamment des experts en ressources humaines, en support technique, en ventes, en technologie et dans d’autres domaines clés. Les PME peuvent contribuer directement au contenu si vous les ajoutez en tant qu Recherche Microsoft éditeurs. 

### <a name="involve-your-users"></a>Impliquer les utilisateurs
Demandez aux utilisateurs de suggérer des ressources à ajouter comme signets. Demandez également aux utilisateurs de signaler des erreurs telles que des liens rompus ou non valides.

## <a name="set-up-components"></a>Configurer des composants
Pour ajouter ou modifier des [signets](manage-bookmarks.md)simples ou en bloc, [Q&A](manage-qas.md)et [Emplacements,](manage-locations.md)prenez les étapes des sections suivantes. 

### <a name="add-or-edit-a-single-bookmark-qa-or-location-component"></a>Ajouter ou modifier un seul signet, Q&A ou un composant d’emplacement
1. Dans le Microsoft 365 [d’administration,](https://admin.microsoft.com) Paramètres  >  **Recherche Microsoft**. Sélectionnez l’onglet nommé du composant. **L’onglet Signets** est sélectionné par défaut.
1. Pour ajouter un composant, sélectionnez **Ajouter nouveau**. 
1. Pour modifier un composant, sélectionnez le signet dans la liste des composants concernée. 
1. Lorsque vous ajoutez ou modifiez les informations, l’aperçu est automatiquement mis à jour.

### <a name="bulk-add-or-edit-components"></a>Ajout ou modification en bloc de composants
Avec les  **fonctionnalités d’importation** et d’exportation, les administrateurs de recherche peuvent créer ou modifier en bloc des signets, [des&A](manage-qas.md)et des [emplacements.](manage-bookmarks.md) [](manage-locations.md) Cette fonctionnalité est utile lorsqu’un administrateur souhaite ajouter ou modifier de nombreux composants. 

Les fonctionnalités d’importation et d’exportation fournissent les fonctions ci-après :
- **Ajout en bloc**. Ajoutez des détails dans le fichier de modèle du composant, puis importez-le.
- **Modification en bloc**. Exportez les composants vers un fichier CSV, modifiez les détails du signet dans le fichier CSV exporté, puis importez le fichier CSV mis à jour.
- **Importer des sites promus à [partir SharePoint](http://sharepoint.com/)**. Cette fonctionnalité s’applique uniquement [aux signets.](manage-bookmarks.md)
- **Sauvegarde**. Exporter des composants vers un fichier CSV.

Pour importer ou exporter des composants, prenez les mesures suivantes :
1. Dans le coin supérieur droit de l’onglet nommé du composant, sélectionnez **Importer.** 
1. Pour télécharger tous les composants existants dans un fichier CSV, sélectionnez **Exporter.**
1. Dans le volet droit, choisissez l’option à importer à l’aide d’un fichier CSV ou [à partir de SharePoint](http://sharepoint.com/).
1. Pour obtenir la liste des champs et détails requis, téléchargez le fichier de modèle du composant. 
1. Ajoutez ou modifiez les détails du composant dans le fichier de modèle. Enregistrez-le sur votre ordinateur. 
1. Dans le volet Importation **du** composant, sélectionnez **Parcourir.** Sélectionnez ensuite le fichier CSV de votre choix, puis sélectionnez **Importer.**

### <a name="template-guidelines"></a>Recommandations en matière de modèles
Ez compte des recommandations et restrictions suivantes lorsque vous travaillez avec des fichiers de modèles :
- Ne modifiez jamais les données dans ces champs *: ID,* *Dernière modification* et Dernière *modification par*.
- Si vous incluez *l’ID* d’un signet existant, il est remplacé par les informations du fichier d’importation.
- S’il existe un signet avec le même titre ou url dans le fichier existant, le signet est mis à jour avec les informations dans le fichier d’importation.
- Tous les champs du fichier de modèle ne sont pas obligatoires et les champs requis varient en fonction de l’état du signet.
- En fonction du *champ État,* les signets sont enregistrés en tant que brouillons, **suggérés** ou  **programmés.** Dans le cas contraire, ils sont publiés automatiquement.
- Si vous gérez plusieurs organisations, vous pouvez exporter vos signets à partir d’une organisation et les importer dans une autre. Avant l’importation, vous devez toutefois supprimer les données de la colonne *ID*.

> [!Note]
> Vous ne pouvez pas importer d’éléments de composant en cas d’erreurs dans le fichier modèle. Pour éviter les erreurs, assurez-vous que votre fichier d’importation est correctement formaté et qu’il inclut toutes les informations requises.

### <a name="prevent-import-errors"></a>Éviter les erreurs d’importation

Vous obtenez un message d’erreur si des données requises sont manquantes ou non valides. Un fichier journal génère des informations supplémentaires sur les lignes et les colonnes à corriger. A effectuer les modifications nécessaires et essayez à nouveau d’importer le fichier. Vous ne pouvez pas importer ou enregistrer de signet tant que toutes les erreurs n’ont pas été résolues.

Pour éviter les erreurs, assurez-vous que votre fichier d’importation est correctement formaté et répond aux exigences ci-après :
- La ligne d’en-tête et toutes les colonnes du modèle d’importation sont incluses.
- L’ordre des colonnes est identique au modèle d’importation.
- Toutes les colonnes ont des valeurs, à l’exception des trois qui peuvent être vides : *ID,* Dernière modification *et* *Dernière modification par*. 
- La *colonne État* n’est pas vide.

### <a name="titles-and-descriptions"></a>Titres et descriptions
Les titres et descriptions connectés aident les utilisateurs à déterminer si les résultats répondent à leur requête de recherche. De bons titres et descriptions reflètent l’objectif principal du résultat. Par exemple, le titre Avantages de la garde **d’enfants** avec la description *Découvrez les avantages pour vous aider à payer les coûts liés à la garde d’enfants.* Grâce à ces données connectées, les utilisateurs qui recherchent une garde d’enfants peuvent trouver des avantages monétaires et obtenir un lien pour en savoir plus. 

### <a name="keywords"></a>Mots clés
Avec des mots clés, les utilisateurs de votre organisation peuvent rechercher et trouver du contenu pertinent. Vous devez associer des termes de mot clé à leurs résultats de recherche associés. Recherche Microsoft des mots clés en fonction du titre et de l’URL de votre contenu. Pour identifier d’autres mots clés, obtenez des réponses à ces questions :

1. **Quels termes de recherche peuvent trouver les informations que vous avez identifiées ?** Reportez-vous à toute terminologie existante dans votre organisation, ainsi qu’aux variantes, acronymes, sujets et rubriques connexes.
1. **Quelles variantes ou mots les personnes utilisent-ils pour parler de ces informations ?** Demandez à votre équipe de support de fournir ces mots clés.

Par exemple, si vous créez un résultat qui crée des  liens  vers un outil permettant d’envoyer des demandes de vacances, les mots clés vacances et envoyer une demande de vacances sont de bonnes options à inclure. Les utilisateurs de votre organisation peuvent également rechercher des informations relatives aux vacances avec **des congés** **ou des congés.** Pour faciliter la recherche de contenu pertinent pour les  utilisateurs, ajoutez ces mots clés et d’autres comme envoyer une demande de congé et demander des **congés.**

### <a name="reserved-keywords"></a>Mots clés réservés
 Un mot clé réservé est un terme ou une expression unique qui déclenche un résultat. Contrairement aux autres mots clés, les mots clés réservés sont associés à un seul résultat. Utilisez les mots clés réservés avec parcimonie pour permettre à la fonctionnalité Recherche Microsoft d’apprendre en se basant sur l’utilisation.

Par exemple, un signet pour un site pour l’envoi de vos heures. Si **l’heure du** journal est un mot  clé réservé, les utilisateurs de votre organisation qui recherchent l’heure du journal voient ce site comme le seul signet dans la Recherche Microsoft. 

### <a name="group-related-content-with-keywords"></a>Grouper le contenu associé à l’aide de mots clés
Si vous souhaitez que les utilisateurs trouvent des ensembles de contenu associé lorsqu’ils recherchent un terme spécifique, affectez le même mot clé à tout le contenu connexe. Par exemple, une recherche de processus et d’outils autour des changements d’état de vie. Pour grouper des réponses sur la mise à jour des avantages, des informations fiscales et des changements de nom et d’alias, incluez un mot clé comme **le mariage.**

### <a name="search-settings"></a>Paramètres de recherche
Grâce aux paramètres de recherche, vous pouvez personnaliser votre contenu et cibler des groupes d’utilisateurs spécifiques. Ces Recherche Microsoft contrôlent quand un résultat de recherche s’affiche et qui peut le voir :

- **Date**. Pour contrôler la disponibilité ou l’indisponibilité du contenu, définissez une date de début et une date de fin. Par exemple, les documents sensibles au temps apparaissent dans les résultats de la recherche lorsqu’ils sont pertinents.
- **Pays ou région**. Vous pouvez sélectionner des pays ou des régions, afin que seuls les utilisateurs de ces emplacements voient certains contenus. Par exemple, les informations spécifiques au pays apparaissent uniquement dans les résultats de la recherche dans ces pays.
- **Les paramètres** de groupe rendent les résultats disponibles uniquement pour les membres des groupes sélectionnés. Par exemple, si vous créez des sites qui concernent uniquement les employés du service RESSOURCES HUMAINES, map faites le map m me ce paramètre au groupe de sécurité RH approprié.
- **Appareil ou système d’exploitation**. Sélectionnez les types d’appareils ou les systèmes d’exploitation, de sorte que seuls les utilisateurs qui recherchent sur ces appareils ou utilisent ces systèmes voient ce signet.
- **Variantes ciblées.** Ce paramètre varie le contenu d’un signet en fonction de l’appareil et de l’emplacement d’un utilisateur.

## <a name="test-your-content"></a>Tester votre contenu
Après avoir créé [des signets](manage-bookmarks.md) et [des&R,](manage-qas.md)vérifiez les résultats ci-après :
- Le signet ou le signet Q&A correct s’affiche.
- Tout le contenu regroupé avec des mots clés apparaît ensemble comme prévu.
- Rien d’inattendu n’apparaît dans les réponses de recherche.
- Le signet ou le signet&A a suffisamment d’informations.

Les utilisateurs et les PME qui contribuent à la création de contenu peuvent aider à tester et valider les résultats de la recherche.

## <a name="review-and-update-periodically"></a>Vérification et mise à jour de manière périodique
Les informations faisant autorité [telles](manage-bookmarks.md) que les signets [et les&A doivent](manage-qas.md) rester à jour. Prenez les mesures suivantes régulièrement :
- Corrigez ou supprimez les URL incorrectes et non valides.
- Supprimez les signets ou les&A qui ne sont plus pertinents.
- vérifier si des changements d’outil, de nom de site ou de nom d’équipe sont intervenus ;
- Envisagez si le signet ou le signet&A fait suffisamment autorité ou nécessite une description plus claire.

## <a name="get-insights-about-bookmarks-qa-and-locations"></a>Obtenir des informations sur les signets, les&A et les emplacements

Recherche Microsoft indique le nombre de signets, de Q [](manage-locations.md) [&A](manage-qas.md)et d’emplacements publiés, programmés ou suggérés. [](manage-bookmarks.md) Le [tableau Informations de bord](./usage-reports.md) affiche les signets, les&A et les totaux d’emplacement par état :

- **Publiés :** nombre de résultats publiés accessibles aux utilisateurs.
- **Programmés :** nombre de résultats programmés dans le pipeline de publication.
- **Suggérés :** nombre de suggestions des utilisateurs.

Les [signets suggérés,](manage-bookmarks.md) [les&](manage-qas.md) [](manage-locations.md) A et les emplacements sont un bon indicateur des lacunes dans votre contenu. Ils vous aident à comprendre ce que vos utilisateurs recherchent, mais ne trouvent pas. Ces données peuvent indiquer que vous devez créer d’autres signets, Q&A ou Emplacements. Vous devrez peut-être mettre à jour votre contenu existant à l’aide de meilleurs mots clés, mots clés réservés et chaînes de recherche pour rendre votre contenu plus découvrable.

### <a name="review-top-search-queries"></a>Examiner les principales requêtes de recherche.

Pour connaître les recherches qui ont généré le plus d’impressions au cours des 90 derniers jours, examinez vos requêtes de recherche les plus importantes. *Impression* signifie le nombre de fois qu’une page a été vue dans les résultats de la recherche. La **carte** Requêtes principales du tableau de bord [Informations](./usage-reports.md) affiche les 25 premières recherches d’utilisateurs pour chaque type de résultat, le nombre total de recherches et le taux de clic(CTR). Avec ce rapport, vous pouvez identifier le volume de requête de recherche et déterminer les requêtes avec une activité de recherche élevée et faible.

Un faible nombre de recherches peut indiquer une insatisfaction de l’utilisateur. Les utilisateurs ne recherchent pas ce contenu ou utilisent des mots clés différents pour le trouver. Le taux de clic indique la fréquence à laquelle les utilisateurs sélectionnent les résultats promus ainsi que l’utilité des résultats et des règles de requête pour les utilisateurs. Un taux de temps de travail faible indique que les utilisateurs trouvent le contenu, mais qu’il ne répond pas à leurs besoins. Dans ce cas, examinez le contenu. Pour aligner le contenu sur les requêtes de recherche, assurez-vous qu’il correspond aux titres, descriptions et mots clés de recherche et de mise à jour des utilisateurs. 

### <a name="analyze-impressions-by-result-type"></a>Analyser les impressions par type de résultat

Les graphiques faciles à lire de la carte de **distribution Impression** du tableau [Informations tableau](./usage-reports.md) de bord montrent des impressions sur différentes périodes. La chronologie indique le nombre d’impressions quotidien pour un type de résultat. Avec ces graphiques, vous pouvez déterminer le type de résultat le plus fréquemment ou rarement utilisé. L’utilisation rare d’un type de résultat particulier ne signifie pas nécessairement que le type de résultat n’est pas bon. Elle montre simplement comment les utilisateurs utilisent les résultats de la recherche.

 Si un type de résultat particulier est préféré par les utilisateurs, vous pouvez créer d’autres résultats de recherche du même type. Pour vous assurer que les mots clés sont appropriés, examinez les mots clés des types de résultats avec une faible utilisation. Avec ce rapport, vous pouvez également voir les modifications apportées au comportement des utilisateurs au fil du temps.