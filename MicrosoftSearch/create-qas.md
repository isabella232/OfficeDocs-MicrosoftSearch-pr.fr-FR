---
title: Créer Q&As
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
description: Moyens de créer des réponses aux questions fréquemment posées pour votre Microsoft Search fonctionnent résultats
ms.openlocfilehash: 9713608450688a0841aa64d1f3198183b10e05ee
ms.sourcegitcommit: 1c038d87efab4840d97b1f367b39e2b9ecdfee4a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/29/2019
ms.locfileid: "29612496"
---
# <a name="create-qas"></a>Créer Q&As

Q&As fournir une réponse ou les informations aux utilisateurs, y compris un lien facultatif. Dans l’idéal, un Q&A inclut tous les détails que cherchent vos utilisateurs afin qu’ils n’avez pas besoin accéder à la source. Vous pouvez mettre en forme votre contenu Q&A et inclure des images, des listes et des tableaux.
  
## <a name="create-a-qa"></a>Créer un Q&A

Pour plus d’informations sur la création efficaces titres, descriptions, mots clés et plus d’informations, consultez [planifier votre contenu.](plan-your-content.md)
  
1. Accédez au portail d’administration de recherche Microsoft
    
2. Dans le volet de navigation, cliquez sur **Q&As**
    
3. En haut de la page, cliquez sur **Ajouter un Q&A**
    
    La page Modifier la Q&A s’affiche, avec un aperçu de l’apparence de la Q&A sur Bing. Lorsque vous ajoutez les informations requises, l’aperçu met à jour automatiquement.
    
4. Entrez un **titre**
    
    Le titre est le titre qui apparaît dans le résultat. Il peut contenir jusqu'à 120 caractères et nous recommandons d’utiliser un format de question.
    
5. Si nécessaire, entrez l' **URL** de la page, un site ou un emplacement que établit un lien vers le signet 
    
    Cette permet aux utilisateurs ayant besoin d’informations supplémentaires facilement accéder à la source pour en savoir plus.
    
6. Entrez une **description de la réponse**
    
    Il doit répondre à la question est posée dans le titre. Vous pouvez copier le contenu HTML existant et coller ici. Toutes les balises non prises en charge seront ignorées.
    
7. Utiliser des balises HTML et les options intégrées au format texte, ajoutez des images, des listes, des tableaux et plus
    
    Utiliser l’aperçu en haut de la page pour voir comment vos balises et la mise en forme s’ils apparaissent sur Bing. Pour plus d’informations sur :
    
  - Balises HTML, voir la liste de balises HTML prises en charge ci-dessous
    
  - Options intégrées, cliquez sur **guide de promotions** (point d’interrogation) 
    
8. Entrez des **mots clés** que vous souhaitez déclencher cette Q&A 
    
    Comme un signet, lorsqu’un utilisateur recherche les mots clés que vous avez inclus, cette Q&A seront inclus dans les résultats de leur travail. Essayez d’ajouter des variantes autant que possible, y compris le titre de la Q&A.
    
9. Sélectionnez **automatiquement correspondent à des mots clés similaires** pour développer votre ensemble de mots clés 
    
    Cela permet une correspondance plus large de termes de recherche et contribue à garantie que cette Q&A est inclus dans les résultats de travail pertinent.
    
10. Entrez des **mots clés réservés**
    
    Si un mot clé déclenche plusieurs Q&As, Microsoft Search alors placer les plus populaires en haut et affiche les autres sous forme de liens. Utilisez un ou plusieurs mots-clés réservés pour garantir qu'une Q&A apparaît toujours comme le meilleur résultat. Mots clés réservés ne peuvent pas être partagés entre Q&As. En outre, le partage des mots clés réservés entre Q&As et les signets n’est pas recommandé. Si un signet et un Q&A partagent un mot clé ou un mot clé réservé, le signet système toujours prioritaires et le Q&A n’apparaît pas.
    
## <a name="add-qa-settings"></a>Ajouter des paramètres Q&A

Paramètres Q&A permettent de contrôler quand un Q&A s’affiche et qui il voit.
  
- Dates
    
    Définir une date de début ainsi que d’une date de fin facultative pour contrôler quand un Q&A sera publié ou expire.
    
- Pays/région
    
    Si vous sélectionnez le pays ou régions, uniquement dans ces emplacements s’affiche que Q&A.
    
- Groupes
    
    Utilisez les groupes pour qu’un résultat Q&A disponibles uniquement aux membres d’un groupe sélectionné. Par exemple, si vous créez Q&As qui s’appliquent uniquement aux employés du service des ressources humaines, vous pouvez mapper ce paramètre au groupe de sécurité des ressources humaines approprié.
    
- APPAREIL &amp; système d’exploitation
    
    Si vous sélectionnez types de périphériques ou systèmes d’exploitation, uniquement une recherche sur ces périphériques ou à l’aide de ces systèmes s’affiche que Q&A.
    
- Variantes ciblés
    
    Utilisez ce paramètre pour faire varier le contenu de la Q&A basé sur l’appareil et l’emplacement d’un utilisateur.
    
## <a name="use-a-browser-extension-to-create-content"></a>Utiliser une extension de navigateur pour créer du contenu

Dans la section Outils du portail d’administration, téléchargez et installez l’extension de navigateur créateur de contenu pour le serveur Edge ou Chrome. Pour utiliser l’extension, se connecter et accéder à un site ou une page que vous souhaitez ajouter en tant que révision Q&A. et modifier les suggestions de contenu, y compris les mots clés, ajouter du contenu supplémentaire, puis enregistrez le Q&A.
  
Si plusieurs Q&As sont détectés, passez en revue chaque et déterminez si vous souhaitez publier, enregistrer un brouillon ou enregistrer tout brouillon.
  
## <a name="supported-html-tags"></a>Balises HTML prises en charge

Vous pouvez utiliser le contenu HTML existant ou ajouter des balises HTML pour la description de votre réponse. Balises non prises en charge sont ignorées.
  
- BLOCKQUOTE
    
- div
    
- cadratin
    
- H1, h2, h3 et h4
    
- ol, ul et li
    
- p
    
- versions antérieures
    
- étendue
    
- fort
    
- table, thead, tbody, tr, th et td
    
- u
    
- a
    
- code
    
- br
    
- hr
    
- IMG

  

