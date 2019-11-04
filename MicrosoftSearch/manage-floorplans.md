---
title: Gérer les plans d’étage
ms.author: rasrivas
author: rasrivas
manager: tonytha
ms.date: 11/01/2019
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: La fonctionnalité plans d’étage de Microsoft Search aide les utilisateurs à trouver des personnes, des bureaux et d’autres équipements dans un immeuble.
ms.openlocfilehash: 68912a8f440443c14cbc27019c7b30dc2d7a34c6
ms.sourcegitcommit: bfcab9d42e93addccd1e3875b41bc9cc1b6986cc
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/04/2019
ms.locfileid: "37949742"
---
# <a name="manage-floor-plans"></a>Gérer les plans d’étage

Les plans d’étage de Microsoft Search aident les utilisateurs à trouver des personnes et des salles de réunion au sein d’un bâtiment. Les plans d’étage répondent à ces questions :
- Où se trouve Allan Young Office ?
- Où se trouve la salle C1 ?

![Plan d’étage : identification de l’emplacement du Bureau de l’utilisateur dans le bâtiment.](media/floorplans-officelocation.png)

Pour faciliter la recherche de réponses à des questions comme celles-ci, les informations sur les bâtiments, les bureaux et les installations d’une organisation doivent être disponibles et pouvoir faire l’objet de recherches. Les grandes organisations ont généralement des installations ou des équipes de gestion de l’espace, et peuvent avoir déjà ces informations disponibles. Dans une organisation plus petite, il se peut que l’administrateur de recherche ait à créer et à l’ajouter.

## <a name="48-hours-before-you-begin"></a>48 heures avant de commencer
Avant de commencer à télécharger des plans d’étage, vous devez indexer les emplacements de bureau des utilisateurs. En fonction de la taille de votre organisation, l’opération peut prendre jusqu’à 48 heures. Si vous ignorez cette étape, vous recevez des erreurs lors de l’exécution de la procédure.

![Capture d’écran de la page des plans d’étage dont la mention « Microsoft doit recueillir et organiser les emplacements de bureau avant de télécharger les plans d’étage » s’affiche.](media/floorplans_hydrationstep.png)

Dans le centre d' [administration](https://admin.microsoft.com)Microsoft 365, accédez **à paramètres** > **Microsoft Search** > **Floor plans**, puis sélectionnez **prise en main**.

Si vous ne voyez pas cette notification, c’est que vous ou une personne de votre organisation avez déjà initié cette étape.

## <a name="things-to-consider"></a>Informations importantes
Pour aider les utilisateurs à trouver des informations sur les bureaux et les installations de création, vous devez ajouter les éléments suivants :

|Mûre     |Pourquoi est-ce si important ?  |
|---------|---------|
|Emplacement de création    |    Vous devrez ajouter chaque bâtiment aux emplacements de recherche Microsoft. Vous devez utiliser un format de dénomination standard pour chaque bâtiment. Vous pouvez ajouter le bâtiment à l’aide d’une adresse postale ou de coordonnées de mappage.     |
|Propriété **Office** sur tous les comptes d’utilisateur     |    Chaque compte d’utilisateur doit disposer de la propriété **Office** avec son emplacement Office. Et les emplacements de bureau doivent respecter un format standard et inclure des informations sur la construction, le plancher et la salle.   <br> Dans Azure AD, cette propriété est appelée **PhysicalDeliveryOfficeName**.    |
|Fichier plan d’étage au format DWG     |   Vous avez besoin d’un plan d’étage distinct pour chaque étage ou aile de votre bâtiment et incluez les informations Office dans le même format que celui que vous avez utilisé dans la propriété Office de l’utilisateur. Le fichier doit être au format DWG Drawing AutoCAD. |

Pour plus d’informations, consultez la rubrique [Best Practices for Microsoft Search Floor plans](floorplans-bestpractices.md).

## <a name="building-location"></a>Emplacement de création

Identifiez les bâtiments qui doivent être ajoutés en tant qu’emplacements. L’adresse d’emplacement et les coordonnées de mappage d’un bâtiment sont le premier point d’identification. Si le bâtiment n’est pas encore ajouté en tant qu’emplacement, l’administrateur doit l’ajouter. Pour plus d’informations, voir [Manage locations](manage-locations.md) .

## <a name="floor-plans-files"></a>Fichiers de plans d’étage

Une fois le bâtiment identifié, vous pouvez ajouter ses plans d’étage. Tous les fichiers du plan d’étage doivent être au format DWG. Si votre organisation ne les a pas encore, vous devez créer les plans d’étage dans une application compatible DWG. Les plans d’étage doivent correspondre correctement toutes les salles, y compris les salles de conférence, les salles de réunion, les toilettes, les cuisines, les salles de messagerie et d’autres installations sur chaque étage du bâtiment pour permettre la recherche.

### <a name="office-locations"></a>Emplacements Office

Pour être mis en correspondance avec les plans d’étage, tous les emplacements Office et les données Office des employés doivent se trouver dans le compte de l’utilisateur. Dans le plan d’étage, les emplacements de bureau doivent être uniques et ne peuvent pas être répétés. Par exemple, si deux personnes partagent Office 2/1173, **2/1173** ne peuvent avoir qu’une seule instance unique dans vos plans d’étage, mais les comptes d’utilisateur dans Azure ad auront le même emplacement de bureau.

![floorplans-peoplecard. png](media/floorplans-peoplecard.png)

 > [!Note] 
 > Lorsqu’un utilisateur recherche une salle ou un bureau d’un collègue, les numéros des plans d’étage sont mis en correspondance avec les emplacements de bureau dans Azure AD. Si une correspondance est trouvée, le mappage est affiché.

## <a name="add-floor-plan"></a>Ajouter un plan d’étage

 La première fois que vous accédez à plans d’étage, vous pouvez voir une note en haut de la page indiquant que *Microsoft a besoin de collecter et d’organiser les emplacements de bureau avant de télécharger les plans d’étage*. Sélectionnez **prise en main** pour indexer vos emplacements Azure ad. 

1. Dans le [Centre d’administration](https://admin.microsoft.com), accédez **à paramètres** > **plans d’étage****Microsoft Search** >, puis sélectionnez **Ajouter des plans d’étage**.
4. Sélectionnez le bâtiment dans la liste déroulante et cliquez sur **suivant**. Si le bâtiment n’est pas présent, vous devez l’ajouter à l’emplacement. Pour plus d’informations, consultez la rubrique [Manage locations](manage-locations.md) .
6. Sélectionnez **Télécharger les fichiers**, puis sélectionnez le plan d’étage que vous souhaitez télécharger. 
1. Une fois que le fichier a été téléchargé correctement, vous devez identifier la façon dont le numéro d’étage ou aile est représenté. 
7. Entrez le code qui identifie le bâtiment. Le code de bâtiment se trouve sur le compte de l’utilisateur dans la propriété emplacement de l' **Office** . Par exemple, si l’emplacement du Bureau de l’utilisateur est **2/1173**, le code de génération est **2**. 
9. Examinez et identifiez les modèles d’emplacement pour tous les plans d’étage téléchargés, puis sélectionnez **suivant**.
10. Lorsque vous êtes prêt, sélectionnez **publier** pour faire en sorte que le plan d’étage peut faire l’objet d’une recherche.

> [!Note] 
> Lorsqu’un plan d’étage est à l’état Brouillon, il est incomplet. Un brouillon permet aux parties prenantes de coordonner le chargement et la création de plans d’étage. Il vous permet également de déployer des plans d’étage en plusieurs étapes.

## <a name="edit-floor-plans"></a>Modifier les plans d’étage

1. Dans le [Centre d’administration](https://admin.microsoft.com), accédez **à paramètres** > **Microsoft Search** > **Floor plans**. 
1. Sélectionnez **publié** ou **Brouillon**, sélectionnez le plan d’étage que vous souhaitez modifier, puis sélectionnez **modifier**.
5. Effectuez vos modifications, puis sélectionnez **Enregistrer**.

## <a name="troubleshoot-errors"></a>Résoudre les erreurs

Vous ne pouvez pas passer à l’étape suivante de définition du plancher, de l’aile et des informations de salle jusqu’à ce que toutes les erreurs soient résolues. Le tableau suivant présente les messages d’erreur de chargement de fichier et les actions permettant de résoudre les problèmes.

| Message d’erreur   | Type    | Action       |
|:----------------| :--------- | :-------------- |
| Impossible de lire CC_1. dwg. Rechargez ou supprimez le plan d’étage. | Error |  Essayez de recharger le fichier. Si cela ne fonctionne pas, supprimez le fichier, puis réessayez. |
| Il existe deux fichiers nommés CC_1. dwg. Supprimez l’un d’entre eux ou rechargez-le à l’aide d’un autre nom.| Error | Si le nom de fichier est incorrect, rendez le nom de fichier unique en ajoutant des informations d’étage ou d’aile, puis téléchargez de nouveau le fichier. <br><br>Si vous avez accidentellement ajouté le même fichier deux fois, supprimez-le. |
| Aucune donnée n’a été trouvée. | Error | Vérifiez que votre fichier est correct, puis téléchargez-le à nouveau, ou supprimez-le. |
| Des références externes sont manquantes dans ce fichier. Téléchargez le fichier « CC_1_furniture. DWG » ou supprimez-le. | Avertissement | Télécharger des fichiers de référence externes ou supprimer.|
| Impossible de lire les numéros de pièces ou les balises dans le fichier DWG. Veuillez supprimer ce fichier. | Avertissement | Vérifiez que les données sont incluses dans votre fichier DWG, puis supprimez le fichier et réessayez. |
