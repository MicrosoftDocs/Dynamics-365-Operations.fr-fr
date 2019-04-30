---
title: Retards
description: Cette rubrique fournit des informations sur les dates retardées de la planification. Une date retardée est une date d'échéance réaliste attribuée à une transaction si la date d'exécution la plus proche calculée par la planification est postérieure à la date demandée.
author: roxanadiaconu
manager: AnnBe
ms.date: 03/15/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ReqTransFuturesListPage
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 19311
ms.assetid: 5ffb1486-2e08-4cdc-bd34-b47ae795ef0f
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: roxanad
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 7c26fedf15118a304469604527c33a25871356be
ms.sourcegitcommit: 8eac5eee94bb32143df44c82a2dfdbe903967af8
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/20/2019
ms.locfileid: "878308"
---
# <a name="delays"></a>Retards

[!include [banner](../includes/banner.md)]

Cette rubrique fournit des informations sur les dates retardées de la planification. Une date retardée est une date d'échéance réaliste attribuée à une transaction si la date d'exécution la plus proche calculée par la planification est postérieure à la date demandée.

La planification peut calculer la date d'exécution la plus proche pour une transaction, en fonction des délais, de la disponibilité des matières, de la disponibilité de la capacité et de divers paramètres de planification. 

Si la planification calcule une date de commande qui précède la date du jour, la commande ne peut pas être exécutée à temps. Par conséquent, la commande est retardée. Dans ce cas, la planification jalonne la commande en aval à partir de la date actuelle et inclut des délais. Ces délais débutent avec chaque composant de niveau inférieur. La commande reçoit ensuite une date différée. Une date différée est une date d'échéance réaliste basée sur les données actuelles. La planification calcule également le nombre de jours de retard. 

Dans certains cas, vous pouvez choisir de ne pas calculer les retards, par exemple lorsque les utilisateurs savent qu'ils peuvent accélérer les délais en sélectionnant d'autres modes de livraison. 

Vous pouvez configurer la manière dont les retards sont calculés pour un groupe de couverture. Vous pouvez ensuite lier le groupe de couverture à un article ultérieurement. 

Dans la page **Paramètres de planification**, vous pouvez définir l'heure de début pour le calcul des retards. Si une commande est exécutée après cette heure, un retard d'une journée est ajouté à la date de retard de la commande. 

> [!REMARQUE} : dans les versions précédentes, les retards calculés étaient appelés *messages de perspectives*, la date différée était appelée *date au plus tôt*, et une transaction différée était appelée *transaction définie dans le futur*.

## <a name="desired-date"></a>Date souhaitée

Dans la page **Ordre prévisionnel**, sous l'onglet **Retards**, se trouve la **Date souhaitée** pour l'ordre prévisionnel. La date souhaitée d'un ordre prévisionnel est la date de référence pour les retards, qui est une date calculée équivalente à la **Date demandée** calculée à partir des **Besoins nets**. Si l'ordre prévisionnel est une ligne de nomenclature, une ligne de production ou une ligne de kanban, la date souhaitée est basée sur la **Date de besoin** et la date souhaitée ne s'affiche pas dans la page **Ordre prévisionnel**.

<a name="additional-resources"></a>Ressources supplémentaires
--------

[Paramètres de couverture](coverage-settings.md)
