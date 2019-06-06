---
title: Configuration DNS avancée
ms.author: dawholl
author: dawholl
manager: kellis
ms.date: 12/19/2018
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Priority
search.appverid:
- BFB160
- MOE150
- MED150
ms.assetid: 47eedbb9-6da9-47e0-aac5-078d34a7fd8f
ROBOTS: NoIndex
description: Garantissez une expérience transparente à vos utilisateurs pour se connecter en configurant votre serveur DNS à l’aide d’un enregistrement CNAME
ms.openlocfilehash: 05562bd9379af395ee305ffebdddbf7bfcd1e835
ms.sourcegitcommit: fe7f3dae4edba97071a4d127e8a27bdf4fa00d81
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/05/2019
ms.locfileid: "34727896"
---
# <a name="advanced-dns-configuration"></a>Configuration DNS avancée


Pour vous assurer que Bing peut toujours identifier les utilisateurs au sein de votre organisation et qui les connectent correctement à leur compte professionnel ou scolaire, configurer votre serveur DNS interne ou serveur proxy pour les résoudre à partir de`www.bing.com` à `ms.bing.com`. Pour ce faire, créez une entrée DNS pour`www.bing.com` être CNAME pour`ms.bing.com`.
  
****

|**Nom**|**Type**|**Valeur**|
|:-----|:-----|:-----|
|`www.bing.com`  <br/> |CNAME  <br/> |`ms.bing.com`  <br/> |
   
Utiliser un enregistrement CNAME plutôt que l’adresse IP est conseillé, car un enregistrement CNAME continuera à fonctionner si l’adresse IP change. Après avoir apporté cette modification DNS, les résultats continueront à apparaître à vos utilisateurs comme s’ils venaient d’apparaître`www.bing.com`. 
  
Cela ne nécessite aucune configuration supplémentaire sur les ordinateurs client et offre une expérience transparente pour vos utilisateurs. Lorsqu’ils accèdent à `bing.com`, ils sont automatiquement connectés de manière plus consistante et s’ils ne peuvent pas être connectés automatiquement, ils seront invités à le faire.
