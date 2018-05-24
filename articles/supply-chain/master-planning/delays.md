---
title: Retards
description: "Cet article fournit des informations sur les dates retardées de la planification. Une date retardée est une date d'échéance réaliste attribuée à une transaction si la date d'exécution la plus proche calculée par la planification est postérieure à la date demandée."
author: roxanadiaconu
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: ReqTransFuturesListPage
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 19311
ms.assetid: 5ffb1486-2e08-4cdc-bd34-b47ae795ef0f
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: roxanad
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: fed78a7eba16d286a81b1e9ad709142422298c91
ms.contentlocale: fr-fr
ms.lasthandoff: 05/08/2018

---

# <a name="delays"></a>Retards

[!include [banner](../includes/banner.md)]

Cet article fournit des informations sur les dates retardées de la planification. Une date retardée est une date d'échéance réaliste attribuée à une transaction si la date d'exécution la plus proche calculée par la planification est postérieure à la date demandée.

La planification peut calculer la date d'exécution la plus proche pour une transaction, en fonction des délais, de la disponibilité des matières, de la disponibilité de la capacité et de divers paramètres de planification. 

Si la planification calcule une date de commande qui précède la date du jour, la commande ne peut pas être exécutée à temps. Par conséquent, la commande est retardée. Dans ce cas, la planification jalonne la commande en aval à partir de la date actuelle et inclut des délais. Ces délais débutent avec chaque composant de niveau inférieur. La commande reçoit ensuite une date différée. Une date différée est une date d'échéance réaliste basée sur les données actuelles. La planification calcule également le nombre de jours de retard. 

Dans certains cas, vous pouvez choisir de ne pas calculer les retards, par exemple lorsque les utilisateurs savent qu'ils peuvent accélérer les délais en sélectionnant d'autres modes de livraison. 

Vous pouvez configurer la manière dont les retards sont calculés pour un groupe de couverture. Vous pouvez ensuite lier le groupe de couverture à un article ultérieurement. 

Dans la page **Paramètres de planification**, vous pouvez définir l'heure de début pour le calcul des retards. Si une commande est exécutée après cette heure, un retard d'une journée est ajouté à la date de retard de la commande. 

**Remarque :** Dans les versions précédentes, les retards calculés étaient appelés *messages de perspectives*, la date différée était appelée *date au plus tôt*, et une transaction différée était appelée *transaction définie dans le futur*.

<a name="additional-resources"></a>Ressources supplémentaires
--------

[Paramètres de couverture](coverage-settings.md)




