---
title: Configuration DNS avancés
ms.author: dawholl
author: dawholl
manager: kellis
ms.date: 12/19/2018
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MOE150
- MED150
ms.assetid: 47eedbb9-6da9-47e0-aac5-078d34a7fd8f
description: Garantir une expérience de connexion transparente pour vos utilisateurs à configurer votre serveur DNS à l’aide d’un enregistrement CNAME
ms.openlocfilehash: f08fc4c29c4c4356a1616faab67fdebdd6c85839
ms.sourcegitcommit: bf52cc63b75f2e0324a716fe65da47702956b722
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/18/2019
ms.locfileid: "29378656"
---
# <a name="advanced-dns-configuration"></a>Configuration DNS avancés

Pour garantir Bing peut toujours identifier les utilisateurs au sein de votre organisation et les connecter correctement à leur compte professionnel ou de l’école, configurez votre serveur DNS interne ou un serveur proxy pour résoudre à partir de `www.bing.com` à `ms.bing.com`. Pour ce faire, créez une entrée DNS pour `www.bing.com` à un enregistrement CNAME pour `ms.bing.com`.
  
****

|**Nom**|**Type**|**Valeur**|
|:-----|:-----|:-----|
|`www.bing.com`  <br/> |CNAME  <br/> |`ms.bing.com`  <br/> |
   
Il est préférable d’utiliser un enregistrement CNAME plutôt que l’adresse IP dans la mesure où un enregistrement CNAME continueront de fonctionner si l’adresse IP change. Après avoir apporté cette modification DNS, les résultats continuera d’apparaître à vos utilisateurs comme si elles proviennent `www.bing.com`. 
  
Cela ne requiert aucune configuration supplémentaire sur les ordinateurs clients et offre une expérience transparente pour vos utilisateurs. Lorsqu’ils accèdent à `bing.com`, ils serez automatiquement connectés plus cohérente et si elles ne peuvent pas être connectés automatiquement, ils serez invités à le faire.
