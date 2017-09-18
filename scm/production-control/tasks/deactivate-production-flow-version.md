--- 
title: "Désactiver la version d'un flux de production"
description: "Lorsqu'une version de flux de production active n'est plus nécessaire, elle peut être désactivée."
author: cvocph
manager: AnnBe
ms.date: 10/07/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: conradv
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 55b22d246d6bfa9e8159fb844da95f61fcf07c62
ms.openlocfilehash: 06daa5e7d2b8e88bca281dc9bcaa73927253553c
ms.contentlocale: fr-fr
ms.lasthandoff: 07/28/2017

---
# <a name="deactivate-a-production-flow-version"></a>Désactiver la version d'un flux de production

[!include[task guide banner](../../includes/task-guide-banner.md)]

Lorsqu'une version de flux de production active n'est plus nécessaire, elle peut être désactivée. Vous devez uniquement utiliser cette option si toutes les règles de kanban et activités sont terminées et ne sont pas réactivées. Notez que la date d'expiration de toutes les règles de kanban associées à cette version de flux de production est mise à jour sur la date et l'heure actuelles. 

Pour modifier une version de flux de production active, définissez une date d'expiration pour la version active et créez une nouvelle version. Cela vous permet de continuer vos opérations de production tout en préparant la nouvelle version et les règles de kanban associées. 

Pour faire expirer une version de flux de production active, vous devez définir une date d'expiration. Dans ce sens, la désactivation s'apparente à une exception plutôt qu'à une règle. 

Pour cette procédure, vous avez besoin d'un flux de production avec une version qui peut être désactivée. Ne tentez pas d'effectuer cette procédure dans un environnement de production à moins que vous soyez sûr à 100 % que la version est entièrement obsolète.


## <a name="deactivate-a-production-flow-version"></a>Désactiver la version d'un flux de production
1. Accédez à Contrôle de la production > Paramétrage > Flux de production lean > Flux de production.
2. Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.
3. Dans la liste, cliquer sur le lien dans la ligne sélectionnée.
4. Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.
5. Cliquez sur Désactiver.
    * Ne continuez pas si vous n'êtes pas sûr à 100 % que cette version de flux de production est obsolète. Lorsque vous cliquez sur OK, toutes les règles de kanban actives expirent et toutes les activités de production et de réapprovisionnement de cette version de flux de production sont immédiatement arrêtées.  
6. Cliquez sur OK.

