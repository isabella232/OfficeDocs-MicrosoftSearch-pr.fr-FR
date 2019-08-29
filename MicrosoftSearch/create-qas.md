---
title: Créer des Questions-réponses
ms.author: dawholl
author: dawholl
manager: kellis
ms.date: 12/18/2018
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Priority
search.appverid:
- BFB160
- MET150
- MOE150
ms.assetid: d432b9d9-3792-47a0-9a13-30a1a83caabc
ROBOTS: NoIndex
description: Méthodes de création des réponses aux questions fréquemment posées pour vos résultats de travail relatifs à Microsoft Search (recherche Microsoft)
ms.openlocfilehash: 78bbd6aa64c9bc2e1890e33beee645b0a9c61ef3
ms.sourcegitcommit: c2c9e66af1038efd2849d578f846680851f9e5d2
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/27/2019
ms.locfileid: "36639783"
---
# <a name="create-qas"></a>Créer des Q&R

> [!IMPORTANT]
> Cet article s’applique à la fonctionnalité Recherche Microsoft dans le portail d’administration Bing. Nous déplaçons le portail vers le centre d’administration Microsoft 365. Nous supprimerons ensuite la fonctionnalité Recherche Microsoft dans le portail Bing. Pour commencer, nous vous suggérons d’utiliser le centre d’administration Microsoft 365. [Vue d’ensemble de la fonctionnalité Recherche Microsoft](overview-microsoft-search.md).

Les questions-réponses fournissent une réponse ou des informations aux utilisateurs ainsi qu’un lien facultatif. Dans l’idéal, une Question-Réponse inclut tous les détails que vos utilisateurs recherchent afin que personne n’ait besoin d’accéder à la source. Vous pouvez mettre en forme le contenu de vos Questions- Réponses et inclure des images, des listes et des tableaux.
  
## <a name="create-a-qa"></a>Créer un Question-Réponse

Pour plus d’informations sur la création efficaces, les titres, des descriptions, les mots clés et autres aspects, voir [Planification de votre contenu](plan-your-content.md).
  
1. Accédez au portail d’administration de Microsoft Search (recherche Microsoft).
    
2. Dans le volet de navigation, cliquez sur Courrier**Q&As**.
    
3. En haut de la page, cliquez sur **Ajouter Q&A**
    
    La page Modifier le signet s’affiche avec une version d’évaluation afin de montrer à quoi ressemblera le signet sur Bing. Lorsque vous ajoutez les informations requises, la version d’affichage se mettra à jour automatiquement.
    
4. Entrez un**Titre**
    
    Le titre est celui qui s’affiche dans le résultat. Il peut avoir jusqu'à 120 caractères et nous vous recommandons d’utiliser un format de question.
    
5. Entrez l’**URL** de la page, d’un site ou d’un emplacement d’un signet qui sera lié au 
    
    Cette permet aux utilisateurs qui ont besoin des informations supplémentaires facilement accéder à la source pour en savoir plus.
    
6. Entrez une **description de réponse**
    
    Cela doit répondre à la question invitée dans le titre. Vous pouvez copier le contenu HTML existant et collez-la à cet endroit. Les balises non prises en charge seront ignorées.
    
7. Utilisez les balises HTML et des options prédéfinies pour mettre en forme du texte, ajouter des images, listes, tableaux, etc.
    
    Utilisez l’aperçu dans la partie supérieure de la page pour voir comment votre balise et la mise en forme ne s’affichent sur Bing. Pour plus d’informations sur :
    
  - Les balises HTML, voir la liste des indicateurs pris en charge HTML ci-dessous
    
  - Options intégrées, cliquez sur ce**guide de démarque** (icône de point d’interrogation) 
    
8. Entrez les**mots clés** que vous souhaitez associer au déclenchement de cette Question-réponse 
    
    Par exemple, un signet, lorsqu’un utilisateur recherche tous les mots clés que vous avez inclus, cette Question-réponse sera incluse dans leurs résultats de travail. Essayez d’ajouter des variantes autant que possible, y compris le titre de la Question-réponse.
    
9. Sélectionnez**automatiquement les mots-clés similaires en correspondance** pour développer votre ensemble de mots clés 
    
    Cela permet une correspondance plus large de termes de recherche et vous permet de vérifier que ce signet est inclus dans les résultats de travail pertinents.
    
10. Entrez les**Mots clés réservés**
    
    Si un mot clé déclenche plusieurs questions et réponses comme, Microsoft Search (recherche Microsoft) placera le plus populaire en haut et affichera les autres liens connexes. Utilisez un ou plusieurs mot(s) clé(s) réservé(s) pour garantir qu’une Question- réponse s’affiche en permanence en tant que résultat supérieur. Les mots clés réservés ne peuvent pas être partagés au sein de Question-réponse. Par ailleurs, le partage de signets et des mots clés réservés dans Question-réponse n’est pas recommandé. Si un signet et une question-réponse partagent un mot clé ou un mot clé réservé, le signet sera toujours prioritaire et la question-réponse ne s’affichera pas.
    
## <a name="add-qa-settings"></a>Ajouter des paramètres Question-réponse

Les paramètres de question-réponse cèdent le contrôle supplémentaire lorsque un signet s’affiche et les personnes autorisées l’affichent.
  
- Dates
    
    Définir une date de début ainsi que d’une date de fin facultative pour contrôler quand un signet sera publié ou expirera.
    
- Pays/région
    
    Si vous sélectionnez les pays ou les régions, seuls les utilisateurs dans ces emplacements verront cette question-réponse.
    
- Groupes
    
    Utilisez les paramètres de groupes pour rendre un résultat de signet disponible uniquement aux membres d’un groupe sélectionné. Par exemple, si vous créez les signets qui concernent uniquement les employés au sein de service ressources humaines, vous pouvez cartographier ce paramètre au groupe de sécurité RH approprié.
    
- Système d’exploitation de l’appareil OS&amp;
    
    Si vous sélectionnez les types d’appareil ou des systèmes d’exploitation, seuls les utilisateurs effectuant une recherche sur ces appareils ou à l’aide de ces systèmes verront cette Question-réponse.
    
- Variantes ciblées
    
    Utilisez ce paramètre pour varier le contenu du signet en fonction de l’appareil et l’emplacement d’un utilisateur.
    
## <a name="use-a-browser-extension-to-create-content"></a>Utiliser une extension du navigateur pour créer du contenu

À la section Outils du portail d’Administration, téléchargez et installez l’extension de navigateur créateur de contenu pour Microsoft Edge ou Chrome. Pour utiliser l’extension, connectez-vous et accédez à un site ou la page que vous souhaitez ajouter en tant qu’un signet. Passez en revue et modifiez le contenu suggéré, y compris les mots clés, ajoutez le contenu supplémentaire et enregistrez la Question-réponse.
  
Si plusieurs questions et réponses sont trouvées, passez en revue chacune d’elles et déterminez si vous souhaitez publier, enregistrer un brouillon ou tout enregistrer comme brouillon.
  
## <a name="supported-html-tags"></a>Balises HTML pris en charge

Vous pouvez utiliser les contenus HTML ou ajouter des balises HTML à la description de votre réponse. Les balises non prises en charge sont ignorées.
  
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

  

