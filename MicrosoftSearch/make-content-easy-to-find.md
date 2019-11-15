---
title: Faciliter l’accès au contenu à l’aide de la fonctionnalité Recherche Microsoft
ms.author: anfowler
author: adefowler
manager: mnirkhe
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: Créez des signets, des emplacements et des Q&R pour accéder facilement au contenu de votre organisation.
ms.openlocfilehash: 605610264e2068deb6215c3157efc24cf0b0a2fd
ms.sourcegitcommit: 21361af7c244ffd6ff8689fd0ff0daa359bf4129
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/14/2019
ms.locfileid: "38626827"
---
# <a name="make-content-easy-to-find"></a>Faciliter l’accès au contenu

La fonctionnalité Recherche Microsoft aide les utilisateurs à accéder à du contenu pertinent. Il s’agit d’un moyen sécurisé pour effectuer des recherches dans votre contenu intranet et Web. Ce type d’intégration sur le Web et les organisations est uniquement disponible auprès de Microsoft. Avec Microsoft Search, les administrateurs peuvent utiliser leur connaissance d’une organisation pour permettre aux utilisateurs de trouver facilement du contenu pertinent. 

## <a name="components-that-find-content"></a>Composants de recherche de contenu
Dans Microsoft Search, les administrateurs créent des [signets](manage-bookmarks.md), des [powerapps](integrate-powerapps.md), des [Q&A](manage-qas.md)et des [emplacements](manage-locations.md) qui rendent le contenu plus facile à trouver. Chacun de ces composants de recherche comprend un titre, une URL et un ensemble de mots clés qui le déclenchent.

## <a name="bookmarks"></a>Signets
Vous pouvez créer des [signets](manage-bookmarks.md) en quelques étapes seulement. Chaque signet comprend un titre, une URL et un ensemble de mots clés qui le déclenchent. Un signet peut avoir plusieurs mots-clés, et plusieurs signets peuvent partager le même mot-clé. Mais les mots clés réservés ne peuvent pas être partagés. Lorsque vous créez ou modifiez un signet, l’index de recherche est actualisé et le signet est immédiatement accessible aux utilisateurs.

Si votre organisation a **promu les résultats** configurés dans [SharePoint](http://sharepoint.com/), vous pouvez importer ces résultats dans Microsoft Search. Avec les résultats promus, vous pouvez rapidement renseigner les résultats de recherche, mettre le contenu à la disposition des utilisateurs et améliorer l’efficacité de Microsoft Search dès que vous le configurez. Nous vous recommandons d’utiliser les résultats promus de SharePoint comme référence pour apprendre à nommer et créer des résultats de recherche pertinents. 

### <a name="add-or-edit-bookmarks-by-using-browser-extensions"></a>Ajouter ou modifier des signets à l’aide des extensions de navigateur
Les administrateurs de recherche peuvent facilement créer du contenu de recherche en utilisant des extensions de navigateur. Pour ajouter le site en tant que signet, installez l’extension du navigateur. Ensuite, accédez au site et ajoutez-le en tant que signet. Pour plus d’informations, consultez la rubrique [gestion des signets](manage-bookmarks.md).

Actuellement, les extensions de navigateur sont disponibles pour [Microsoft Edge](https://www.microsoft.com/windows/microsoft-edge) et [Google Chrome](https://www.google.com): 
- Pour télécharger l’extension Edge, accédez au [Microsoft Store](https://www.microsoft.com/p/microsoft-search-content-creator/9nrqdbcbwq55?activetab=pivot:overviewtab).
- Pour télécharger l’extension chrome, accédez au [magasin Web chrome](https://chrome.google.com/webstore/detail/microsoft-search-content/nocnablpaoeecfmfnjoheefkogmleipm).

## <a name="powerapps"></a>PowerApps

En ajoutant des [PowerApp](integrate-powerapps.md) à vos [signets](manage-bookmarks.md), les utilisateurs peuvent effectuer des tâches telles que la saisie des heures de vacances ou la création de rapports. 

Avec les [PowerApp](integrate-powerapps.md), vous pouvez créer des applications métiers qui s’exécutent dans un navigateur ou sur un téléphone ou une tablette. Aucune expérience de codage n’est requise. Les PowerApp fonctionnent dans n’importe quel navigateur et sur n’importe quel appareil. L’ajout s’effectue moins d’une minute. Pour en savoir plus sur les PowerApp, consultez les articles suivants :
- [Formation guidée](https://docs.microsoft.com/learn/browse/?products=powerapps)
- [Documentation PowerApp](https://docs.microsoft.com/powerapps/maker/canvas-apps/get-sessionid)
- [Famille des PowerApp](https://make.preview.powerapps.com/environments/839eace6-59ab-4243-97ec-a5b8fcc104e4/home)

### <a name="add-a-powerapp-to-a-bookmark"></a>Ajouter une application PowerApp à un signet

1. Recherchez l' [ID d’application](https://docs.microsoft.com/powerapps/maker/canvas-apps/get-sessionid#get-an-app-id) pour le PowerApp que vous souhaitez ajouter.
1. Dans le centre d' [administration](https://admin.microsoft.com)Microsoft 365, accédez à **paramètres** > **Microsoft Search**. 
1. Ajoutez un nouveau signet ou accédez à un signet existant auquel vous souhaitez ajouter une application PowerApp.
1. Dans **paramètres du signet**, sélectionnez **Power App**. Ensuite, sélectionnez **Ajouter une application d’alimentation**.
1. Entrez l' **ID**de l’application. La hauteur et la largeur s’ajustent automatiquement. Les [signets](manage-bookmarks.md) peuvent prendre en charge les orientations portrait et paysage, mais la taille ne peut pas être modifiée. Pour faciliter le test, l’aperçu de signet présente une fonctionnalité PowerApp entièrement fonctionnelle.
1. Sélectionnez **Publier** ou **Enregistrer en tant que brouillon**.

## <a name="qa"></a>Q&R

La création d’une [&Q](manage-qas.md) est semblable à la création de [signets](manage-bookmarks.md). Avec Q&A, vous pouvez fournir des réponses aux questions des utilisateurs au lieu d’un simple lien vers la page Web. Vous pouvez mettre en forme les réponses dans le texte enrichi en utilisant les outils disponibles. Si un signet et un Q&un partage du même mot-clé, le résultat du signet apparaît en premier. Comme les signets, le Q&un index est actualisé immédiatement après l’ajout ou la modification d’un Q&A. 

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

Les balises non prises en charge sont soit ignorées, soit affichées sous forme de texte. Veillez à avoir un aperçu de vos cartes.

> [!Note]
> Vous ne pouvez pas importer Q&des éléments si le fichier de modèle comporte des erreurs. Pour éviter les erreurs, assurez-vous que votre fichier d’importation est correctement mis en forme et qu’il inclut toutes les informations requises. Pour plus d’informations sur la façon d' [éviter les erreurs d’importation](#prevent-import-errors).

## <a name="locations"></a>Emplacements

Avec des [emplacements](manage-locations.md), vos utilisateurs peuvent trouver des adresses et localiser les bâtiments de votre organisation. La fonctionnalité **emplacements** fournit un emplacement précis pour les bureaux, les campuss et les bâtiments, ainsi que pour les directions et la navigation. Pour de meilleurs résultats, les administrateurs doivent ajouter tous les emplacements importants de leurs organisations à Microsoft Search. Contrairement aux [signets](manage-bookmarks.md) et [Q&A](manage-qas.md), l’index des emplacements n’est pas actualisé immédiatement. L’affichage des emplacements nouveaux ou modifiés dans les résultats de recherche peut prendre plusieurs heures.

## <a name="get-started"></a>Prise en main
Pour connaître les besoins de vos utilisateurs et rendre ces informations faciles à découvrir, essayez certaines des méthodes suivantes :

- Utilisez les journaux de recherche intranet pour identifier les sites et les pages qui génèrent le plus de trafic.
- Identifiez les applications, les sites et les outils utilisés sur une base quotidienne ou hebdomadaire.
- Trouvez des liens directs pour les avantages sociaux des employés.
- Identifiez les stratégies et processus que les utilisateurs doivent connaître.
- Déterminez les personnes qui contactent le support et la façon dont ils le font.
- Obtenir des informations qui sont nécessaires sur une base récurrente, de manière saisonnière ou basée sur des cycles d’entreprise. Par exemple, les utilisateurs recherchent des outils pour livrer des mises à jour financières ou trimestrielles.
- Collecter des stratégies pour les utilisateurs locaux ou mobiles. Les exemples sont des avantages qui varient en fonction de l’emplacement.
- Déterminer les sites internes et les informations pour les recherches fréquentes sur le Web. Il s’agit par exemple du trafic, des informations de transit public, de la météo locale, des remises disponibles auprès des partenaires d’entreprise et des programmes d’intégrité et de remise en état.
- Trouvez des informations sur les événements, conférences ou séminaires parrainés par l’entreprise.
- Effectuez des recherches sur des sujets courants liés à l’informatique, aux ressources humaines et au support technique ainsi que les questions fréquentes (FAQ) et leurs réponses.

## <a name="involve-smes-and-users"></a>Impliquer les PME et les utilisateurs
Au sein d’une organisation, les utilisateurs recherchent un large éventail de rubriques simples et complexes. Les exemples simples sont les adresses Office et les avantages des employés. Les exemples complexes sont les nouveaux processus de travail, les informations techniques et le contenu des procédures. Pour créer ou trouver un grand nombre de contenus, vous avez besoin d’une expertise dans différents domaines, sujets et technologies. 

La plupart des administrateurs de recherche n’ont pas de connaissances spécifiques sur chaque sujet. Pour redimensionner la quantité de contenu disponible sans l’aide de ressources externes, demandez de l’expérience et des connaissances auprès d’autres membres de votre organisation.

### <a name="get-content-from-smes"></a>Obtenir du contenu de PME
Tirez parti des experts techniques de votre organisation, y compris des experts des RH, du support, des ventes, de la technologie et d’autres domaines clés. Les PME peuvent contribuer directement au contenu si vous les ajoutez en tant qu’éditeurs de recherche Microsoft. 

### <a name="involve-your-users"></a>Impliquer les utilisateurs
Demandez aux utilisateurs de suggérer des ressources à ajouter comme signets. Demandez également aux utilisateurs de signaler les erreurs telles que les liens rompus ou non valides.

## <a name="set-up-components"></a>Configurer des composants
Pour ajouter ou modifier des [signets](manage-bookmarks.md)uniques ou en bloc, [Q&A](manage-qas.md)et des [emplacements](manage-locations.md), effectuez les étapes décrites dans les sections suivantes. 

### <a name="add-or-edit-a-single-bookmark-qa-or-location-component"></a>Ajouter ou modifier un seul signet, Q&un ou un composant d’emplacement
1. Dans le centre d' [administration](https://admin.microsoft.com)Microsoft 365, accédez à **paramètres** > **Microsoft Search**. Sélectionnez l’onglet nommé du composant. L’onglet **signets** est sélectionné par défaut.
1. Pour ajouter un composant, sélectionnez **Ajouter un nouveau**. 
1. Pour modifier un composant, sélectionnez-le dans la liste des composants pertinents. 
1. Lorsque vous ajoutez ou modifiez les informations, l’aperçu est automatiquement mis à jour.

### <a name="bulk-add-or-edit-components"></a>Ajouter ou modifier en bloc des composants
Avec les fonctionnalités d' **importation** et d' **exportation** , les administrateurs de la recherche peuvent créer ou modifier en bloc des [signets](manage-bookmarks.md), [Q&un](manage-qas.md)et des [emplacements](manage-locations.md). Cette fonctionnalité est utile lorsqu’un administrateur souhaite ajouter ou modifier un grand nombre de composants. 

Les fonctionnalités d’importation et d’exportation offrent les fonctions suivantes :
- **Ajout en bloc**. Ajoutez des détails dans le fichier de modèle du composant, puis importez-le.
- **Modification en bloc**. Exportez les composants dans un fichier CSV, puis modifiez les détails des signets dans le fichier CSV exporté, puis importez le fichier CSV mis à jour.
- **Importez les sites promus à partir de [SharePoint](http://sharepoint.com/)**. Cette fonctionnalité s’applique uniquement aux [signets](manage-bookmarks.md).
- **Sauvegarde**. Exportez les composants vers un fichier CSV.

Pour importer ou exporter des composants, procédez comme suit :
1. Dans le coin supérieur droit de l’onglet nommé du composant, sélectionnez **Importer**. 
1. Pour télécharger tous les composants existants dans un fichier CSV, sélectionnez **Exporter**.
1. Dans le volet droit, choisissez l’option d’importation à l’aide d’un fichier CSV ou de [SharePoint](http://sharepoint.com/).
1. Pour obtenir la liste des champs requis et des détails, téléchargez le fichier de modèle du composant. 
1. Ajouter ou modifier des détails de composants dans le fichier de modèle. Ensuite, enregistrez-le sur votre ordinateur. 
1. Dans le volet **Importer** du composant, sélectionnez **Parcourir**. Sélectionnez le fichier CSV de votre choix et sélectionnez **Importer**.

### <a name="template-guidelines"></a>Instructions de modèle
Gardez à l’esprit ces instructions et restrictions lorsque vous utilisez des fichiers de modèle :
- Ne modifiez jamais les données de ces champs : *ID*, *Last modified*et *Last modified by*.
- Si vous incluez l' *ID* d’un signet existant, il est remplacé par les informations contenues dans le fichier d’importation.
- S’il existe un signet avec le même titre ou URL dans le fichier existant, le signet est mis à jour avec les informations contenues dans le fichier d’importation.
- Les champs du fichier de modèle ne sont pas tous obligatoires et les champs obligatoires varient en fonction de l’état du signet.
- En fonction du champ *État* , les signets sont enregistrés en tant que **Brouillon**, **suggéré**ou **planifié**. Dans le cas contraire, elles sont publiées automatiquement.
- Si vous gérez plusieurs organisations, vous pouvez exporter vos signets d’une organisation et les importer dans un autre. Avant l’importation, vous devez toutefois supprimer les données de la colonne *ID*.

> [!Note]
> Vous ne pouvez pas importer des éléments de composant s’il existe des erreurs dans le fichier de modèle. Pour éviter les erreurs, assurez-vous que votre fichier d’importation est correctement mis en forme et qu’il inclut toutes les informations requises.

### <a name="prevent-import-errors"></a>Éviter les erreurs d’importation

Vous obtenez un message d’erreur si les données requises sont manquantes ou non valides. Un fichier journal génère des informations supplémentaires sur les lignes et les colonnes à corriger. Effectuez les modifications nécessaires, puis réessayez d’importer le fichier. Vous ne pouvez pas importer ou enregistrer de signets tant que toutes les erreurs ne sont pas résolues.

Pour éviter les erreurs, assurez-vous que votre fichier d’importation est correctement mis en forme et répond à la configuration requise suivante :
- La ligne d’en-tête et toutes les colonnes du modèle d’importation sont incluses.
- L’ordre des colonnes est le même que celui du modèle d’importation.
- Toutes les colonnes ont des valeurs, à l’exception des trois qui peuvent être vides : *ID*, *Last modified*et *Last modified by*. 
- La colonne *État* n’est pas vide.

### <a name="titles-and-descriptions"></a>Titres et descriptions
Les titres et les descriptions connectés aident les utilisateurs à déterminer si les résultats répondent à leur requête de recherche. Les titres et les descriptions appropriés reflètent l’objectif principal du résultat. Par exemple, le titre **avantages** du centre d’aide à la description *en savoir plus sur les avantages pour vous aider à payer les frais de garde*. Avec ces données connectées, les utilisateurs qui recherchent des **enfants** peuvent trouver des avantages de support monétaire et obtenir un lien pour en savoir plus.

### <a name="keywords"></a>Mots clés
Avec les mots clés, les utilisateurs de votre organisation peuvent rechercher et trouver du contenu pertinent. Vous devez associer les termes de mots clés à leurs résultats de recherche connexes. Microsoft Search suggère des mots clés en fonction du titre et de l’URL de votre contenu. Pour identifier d’autres mots clés, obtenez des réponses à ces questions :

1. **Quels termes de recherche peuvent trouver les informations que vous avez identifiées ?** Reportez-vous à toute terminologie existante dans votre organisation, ainsi qu’aux variantes, acronymes, sujets et rubriques associés.
1. **Quels sont les variantes ou les mots que les utilisateurs utilisent pour parler de ces informations ?** Demandez à votre équipe de support technique de fournir ces mots clés.

Par exemple, si vous créez un résultat qui renvoie à un outil pour soumettre des demandes de congés, les mots clés **vacances** et **soumettre la demande de congés** sont des options appropriées à inclure. Les utilisateurs de votre organisation peuvent également rechercher des informations relatives aux vacances avec **congés** **ou congés.** Pour permettre aux utilisateurs de trouver plus facilement du contenu pertinent, ajoutez ces mots-clés et d’autres personnes, comme **Envoyer une demande de congés** et des congés de la **demande**.

### <a name="reserved-keywords"></a>Mots clés réservés
 Un mot clé réservé est un terme ou une expression unique qui déclenche un résultat. Contrairement à d’autres mots clés, les mots clés réservés sont associés à un seul résultat. Utilisez les mots clés réservés avec parcimonie pour permettre à la fonctionnalité Recherche Microsoft d’apprendre en se basant sur l’utilisation.

Un signet pour un site est un exemple d’envoi de vos heures. Si l' **heure de journalisation** est un mot clé réservé, les utilisateurs de votre organisation qui recherchent le **temps de journalisation** voient ce site comme le seul signet dans la zone de recherche de Microsoft. 

### <a name="group-related-content-with-keywords"></a>Regrouper le contenu associé avec des mots clés
Si vous souhaitez que les utilisateurs puissent trouver des ensembles de contenu associé lorsqu’ils recherchent un terme spécifique, affectez le même mot-clé à tout le contenu associé. Voici un exemple de recherche de processus et d’outils relatifs aux modifications d’état de vie. Pour regrouper les réponses en fonction de la mise à jour des avantages, des informations fiscales et des modifications apportées au nom et à l’alias, incluez un mot-clé comme **mariage**

### <a name="search-settings"></a>Paramètres de recherche
Avec les paramètres de recherche, vous pouvez personnaliser votre contenu et cibler des groupes d’utilisateurs spécifiques. Ces paramètres de recherche Microsoft contrôlent quand un résultat de recherche s’affiche et qui peut le voir :

- **Date**. Pour contrôler quand le contenu est disponible ou indisponible, définissez une date de début et une date de fin. Par exemple, des éléments sensibles au temps apparaissent dans les résultats de recherche lorsqu’ils sont pertinents.
- **Pays ou région**. Vous pouvez sélectionner des pays ou régions, de sorte que seuls les utilisateurs situés à ces emplacements voient certains contenus. Par exemple, les informations propres à un pays apparaissent dans les résultats de recherche dans ces pays uniquement.
- Les paramètres de **groupe** rendent les résultats accessibles uniquement aux membres des groupes sélectionnés. Par exemple, si vous créez des sites qui se rapportent uniquement aux employés du service des ressources humaines, associez ce paramètre au groupe de sécurité RH approprié.
- **Périphérique ou système d’exploitation**. Sélectionnez types d’appareils ou systèmes d’exploitation, afin que seuls les utilisateurs qui recherchent sur ces appareils ou qui utilisent ces systèmes voient ce signet.
- **Variantes ciblées**. Ce paramètre fait varier le contenu d’un signet en fonction de l’appareil et de l’emplacement d’un utilisateur.

## <a name="test-your-content"></a>Tester votre contenu
Une fois que vous avez créé des [signets](manage-bookmarks.md) et [Q&A](manage-qas.md), vérifiez les résultats suivants :
- Le signet correct ou Q&A apparaît.
- Tout le contenu groupé avec des mots clés apparaît ensemble comme prévu.
- Aucune inattendue n’apparaît dans les réponses de recherche.
- Le signet ou Q&a dispose de suffisamment d’informations.

Les utilisateurs et les PME qui contribuent à la création de contenu peuvent vous aider à tester et valider les résultats de la recherche.

## <a name="review-and-update-periodically"></a>Vérification et mise à jour de manière périodique
Les informations faisant autorité telles que les [signets](manage-bookmarks.md) et [Q&un](manage-qas.md) doivent rester frais. Suivez ces étapes régulièrement :
- Corrigez ou supprimez les URL rompues ou non valides.
- Supprimez les signets ou les&Q qui ne sont plus pertinents.
- vérifier si des changements d’outil, de nom de site ou de nom d’équipe sont intervenus ;
- Déterminez si le signet ou Q&a fait suffisamment autorité ou a besoin d’une description plus claire.

## <a name="get-insights-about-bookmarks-qa-and-locations"></a>Obtenir des informations sur les signets, Q&un et des emplacements

Microsoft Search vous indique le nombre de [signets](manage-bookmarks.md), [Q&A](manage-qas.md)et les [emplacements](manage-locations.md) sont publiés, planifiés ou suggérés. Le [tableau de bord Insights](get-insights.md) affiche les totaux des signets, des Q&A et des emplacements par État :

- **Publiés :** nombre de résultats publiés accessibles aux utilisateurs.
- **Programmés :** nombre de résultats programmés dans le pipeline de publication.
- **Suggérés :** nombre de suggestions des utilisateurs.

Les [signets](manage-bookmarks.md)suggérés, [Q&a](manage-qas.md)et les [emplacements](manage-locations.md) sont un parfait indicateur des intervalles dans votre contenu. Elles vous aident à comprendre ce que vos utilisateurs cherchent, mais qui ne le trouvent pas. Ces données peuvent indiquer que vous devez créer d’autres signets, Q&un ou plusieurs emplacements. Ou vous devrez peut-être mettre à jour votre contenu existant à l’aide de meilleurs Mots clés, Mots clés réservés et chaînes de recherche pour améliorer la détectabilité de votre contenu.

### <a name="review-top-search-queries"></a>Examiner les principales requêtes de recherche.

Pour savoir quelles recherches ont généré le plus d’impressions au cours des 90 derniers jours, consultez les requêtes de recherche les plus fréquentes. *Impression* indique le nombre de fois qu’une page a été affichée dans les résultats de la recherche. La carte des **requêtes du haut** dans le [tableau de bord Insights](get-insights.md) affiche les 25 premières recherches utilisateur pour chaque type de résultat, le nombre total de recherches et le taux de clic. Ce rapport vous permet d’identifier le volume des requêtes de recherche et de déterminer les requêtes avec des activités de recherche élevée et faible.

Le nombre de recherches faibles peut indiquer une insatisfaction de l’utilisateur. Soit les utilisateurs ne cherchent pas ce contenu, soit ils utilisent des mots clés différents pour le trouver. Le taux de clic indique la fréquence à laquelle les utilisateurs sélectionnent les résultats promus ainsi que l’utilité des résultats et des règles de requête pour les utilisateurs. Un faible taux de clic indique que les utilisateurs trouvent le contenu, mais il ne répond pas à leurs besoins. Dans ce cas, passez en revue le contenu. Pour aligner le contenu sur les requêtes de recherche, assurez-vous qu’il correspond à la recherche et à la mise à jour des titres, des descriptions et des mots clés. 

### <a name="analyze-impressions-by-result-type"></a>Analyser les impressions par type de résultat

Des graphiques faciles à lire dans la carte de **distribution d’impression** du [tableau de bord Insights](get-insights.md) affichent des impressions sur différentes périodes. La chronologie indique le nombre d’impressions quotidien pour un type de résultat. Ces graphiques vous permettent de déterminer le type de résultat le plus souvent ou rarement utilisé. Une utilisation peu fréquente d’un type de résultat particulier ne signifie pas nécessairement que le type de résultat n’est pas correct. Elle montre simplement comment les utilisateurs utilisent les résultats de la recherche.

 Si les utilisateurs préfèrent un type de résultat particulier, vous pouvez créer d’autres résultats de recherche du même type. Pour vous assurer que les mots clés sont appropriés, examinez les mots clés des types de résultats avec une utilisation faible. Avec ce rapport, vous pouvez également afficher les modifications apportées au comportement de l’utilisateur dans le temps.
