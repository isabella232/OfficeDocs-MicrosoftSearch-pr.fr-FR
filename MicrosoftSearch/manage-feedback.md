---
title: Gestion des commentaires des utilisateurs
ms.author: lebhansa
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
ROBOTS: NoIndex
description: Passer en revue et agir sur les commentaires des utilisateurs dans Microsoft Search
ms.openlocfilehash: fd47403fd86be2e2fb1ba7baee7473958a8e5572
ms.sourcegitcommit: 4b2cc0a4cd3d7cdcd8eb23a8baa9703173889a73
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/10/2020
ms.locfileid: "48986956"
---
# <a name="managing-user-feedback"></a>Gestion des commentaires des utilisateurs

La création d’une expérience de recherche idéale pour vos utilisateurs est un partenariat entre Microsoft et l’administrateur de recherche. Les commentaires de vos utilisateurs nous permettent d’évaluer en permanence le produit et de le régler pour une expérience optimale. Toutefois, il est préférable de procéder à des commentaires.

Nous proposons désormais des outils qui vous permettront de vérifier et de gérer les commentaires que vos utilisateurs fournissent sur l’expérience de recherche.

## <a name="how-users-submit-feedback"></a>Comment les utilisateurs envoient des commentaires

À mesure que les membres de votre organisation utilisent Microsoft Search, ils peuvent avoir des commentaires sur l’expérience. Lorsqu’ils cliquent sur un lien de commentaires sur la page des résultats, ils peuvent classer leurs commentaires et inclure des commentaires supplémentaires.

![Formulaire de commentaires global](media/feedback/feedback-global-dialog.png)

Les utilisateurs ont également la possibilité d’envoyer leur requête et d’autres informations de diagnostic, ainsi que la catégorie et les commentaires, à Microsoft. Les informations de diagnostic incluent des données personnelles telles qu’un identificateur d’utilisateur. [En savoir plus](https://privacy.microsoft.com/en-US/privacystatement) sur la confidentialité et sur la protection de ces données. Les données de diagnostic contiennent les informations les plus importantes dont Microsoft a besoin pour utiliser l’élément de commentaires pour l’amélioration du produit.

La plupart des commentaires de commentaires apparaissent dans la section [Commentaires](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/feedback) du centre d’administration de Microsoft Search. Les commentaires envoyés avec la catégorie **je souhaite suggérer une catégorie interne** apparaissent en tant que signet suggéré dans la section [signets](https://admin-ignite.microsoft.com/Adminportal/Home#/MicrosoftSearch/bookmarks) et peuvent être vus en filtrant sur l’état **proposé** .

## <a name="review-feedback"></a>Consulter les commentaires

Sur la page [Commentaires](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/feedback) , vous pouvez passer en revue et exporter les commentaires que les personnes de votre organisation ont envoyées au cours des 30 derniers jours. Une fois qu’un utilisateur envoie des commentaires, il apparaît dans cette liste dans les 20 minutes. Vous pouvez utiliser le bouton Actualiser pour vous assurer que vous examinez les données les plus récentes.

À l’aide d’un filtre, vous pouvez voir des commentaires sur des types de réponses spécifiques. Vous pouvez également filtrer par source et par plage de dates.

Vous pouvez utiliser la zone de recherche au-dessus de la liste de commentaires pour rechercher des commentaires sur une requête spécifique.

Dans la liste de commentaires, la colonne Verbatim indique les commentaires de l’utilisateur qui incluent également un commentaire ou une suggestion. Pour le lire, cliquez sur la requête pour ouvrir le panneau de **Détails** .

## <a name="update-feedback-state"></a>Mettre à jour l’état des commentaires

Lorsque le feedback se présente, il sera dans un *nouvel* État et il y restera jusqu’à ce que *Resolved* vous le transformez en *double*.

Pour modifier cet État :

1. En regard de la requête, sélectionnez **plus d’options** (trois points verticaux).
1. Dans le menu, sélectionnez **marquer comme résolu** ou **marquer comme doublon.**
1. La liste est actualisée et affiche l’État mis à jour.

Vous pouvez également mettre à jour l’état de plusieurs éléments, les sélectionner, puis sélectionner d’autres options en regard de ces éléments.

## <a name="export-feedback"></a>Exporter les commentaires

Si vous souhaitez partager des commentaires de recherche avec d’autres personnes ou les conserver pendant plus de 30 jours, cliquez sur **Exporter.** Un fichier. csv nommé feedbacks avec la date, comme « Feedbacks_10_31_2020.csv », sera automatiquement téléchargé.

## <a name="send-user-feedback-to-microsoft"></a>Envoyer les commentaires de l’utilisateur à Microsoft

Par défaut, tous les commentaires des utilisateurs sont envoyés à Microsoft et viennent s’ajouter à vous. Pour cesser d’envoyer des commentaires à Microsoft, cliquez sur **gérer les paramètres** et désactivez la case à cocher Envoyer les **commentaires des utilisateurs à Microsoft automatiquement** . Cette modification peut prendre jusqu’à 24 heures.

Si vous avez décidé de ne pas envoyer de commentaires à Microsoft automatiquement, vous pouvez toujours envoyer des Commentaires individuels à Microsoft.

1. Sélectionnez le commentaire que vous souhaitez partager.
1. Dans la barre d’action, sélectionnez autres (trois points), puis cliquez sur **Envoyer des commentaires à Microsoft**.

1. L’État dans la colonne envoyé à Microsoft passe à en attente. Lorsque le commentaire est envoyé, il passe à Oui.

Si vous partagez des commentaires automatiquement ou manuellement, il n’inclut jamais les requêtes ni les autres informations de diagnostic pour les utilisateurs qui ont choisi de ne pas inclure ces informations.

## <a name="suggestions-on-how-to-use-feedback"></a>Suggestions sur l’utilisation des commentaires

En tant qu’administrateur de recherche, vous devez comprendre les principaux personnages de votre organisation et les types de contenu que ces personnes utilisent généralement et recherche. Avec cette compréhension, vous pouvez utiliser les commentaires pour apporter des améliorations ciblées à l’expérience de recherche de vos utilisateurs.

1. « Je n’ai pas trouvé ce que je recherchais » et des commentaires similaires peuvent être utilisés pour identifier le contenu souhaité par les utilisateurs, mais il n’est pas inclus dans l’index de recherche. La détermination de cette opération nécessite souvent une enquête et une inférence en fonction de la compréhension de vos utilisateurs. Une fois trouvé, déterminez les méthodes d’inclusion de ce contenu les plus appropriées :
    1. Les signets sont utiles pour les sources de contenu disposant d’une page d’accueil de haute qualité et d’un nombre limité de termes de recherche, afin que la communauté d’utilisateurs puisse obtenir un résultat de haute qualité à partir du signet et puisse trouver efficacement ce qu’elles cherchent.
    1. Q&A sont utiles pour les réponses individuelles qui sont assez fréquentes, mais qui ne changent pas.
    1. Les connecteurs sont utiles pour les sources de contenu avec un large éventail de contenus et de nombreux termes de recherche.
1. « Les résultats ont duré trop longtemps pour charger «& «j’ai trouvé un problème » peuvent être des indicateurs d’un problème plus large. Rechercher cette évaluation quotidienne peut vous aider et, si plusieurs cas apparaissent, vous pouvez vérifier l’expérience de recherche pour vous-même et ouvrir un cas de support technique auprès de Microsoft si nécessaire. Ce type de commentaires est également important pour Microsoft et constitue une excellente raison de nous faire part de vos commentaires.
1. « Je veux suggérer un lien interne » peut être évalué pour être ajouté en tant que signet ou contenu connecté. Votre première pensée doit être un signet ; Si l’utilisation du signet est élevée, vous pouvez envisager d’insérer du contenu via un connecteur pour activer une expérience de recherche encore plus riche.
