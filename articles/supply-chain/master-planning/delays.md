---
title: Retards
description: Cette rubrique fournit des informations sur les dates retardées de la planification. Une date retardée est une date d'échéance réaliste attribuée à une transaction si la date d'exécution la plus proche calculée par la planification est postérieure à la date demandée.
author: roxanadiaconu
manager: tfehr
ms.date: 03/31/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ReqTransFuturesListPage
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: 19311
ms.assetid: 5ffb1486-2e08-4cdc-bd34-b47ae795ef0f
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: roxanad
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 34252e5cd9ee5151b1cba47975fc0cc612521a17
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/02/2020
ms.locfileid: "3203846"
---
# <a name="delays"></a>Retards

[!include [banner](../includes/banner.md)]

Cette rubrique fournit des informations sur les dates retardées de la planification. Une date retardée est une date d'échéance réaliste attribuée à une transaction si la date d'exécution la plus proche calculée par la planification est postérieure à la date demandée.

La planification peut calculer la date d'exécution la plus proche pour une transaction, en fonction des délais, de la disponibilité des matières, de la disponibilité de la capacité et de divers paramètres de planification. 

Si la planification calcule une date de commande qui précède la date du jour, la commande ne peut pas être exécutée à temps. Par conséquent, la commande est retardée. Dans ce cas, la planification jalonne la commande en aval à partir de la date actuelle et inclut des délais. Ces délais débutent avec chaque composant de niveau inférieur. La commande reçoit ensuite une date différée. Une date différée est une date d'échéance réaliste basée sur les données actuelles. La planification calcule également le nombre de jours de retard. 

Dans certains cas, vous pouvez choisir de ne pas calculer les retards, par exemple lorsque les utilisateurs savent qu'ils peuvent accélérer les délais en sélectionnant d'autres modes de livraison. 

Vous pouvez configurer la manière dont les retards sont calculés pour un groupe de couverture. Vous pouvez ensuite lier le groupe de couverture à un article ultérieurement. 

Dans la page **Paramètres de planification**, vous pouvez définir l'heure de début pour le calcul des retards. Si une commande est exécutée après cette heure, un retard d'une journée est ajouté à la date de retard de la commande. 

> [!NOTE]
> Dans les versions précédentes, les retards calculés étaient appelés *messages de perspectives*, la date différée était appelée *date au plus tôt*, et une transaction différée était appelée *transaction définie dans le futur*.

## <a name="limited-delays-in-production-setup-with-multiple-bom-levels"></a>Retards limités à la configuration de la production avec plusieurs niveaux de nomenclature
Lorsque vous travaillez avec des retards dans une configuration de production avec plusieurs niveaux de nomenclature, il est important de noter que seuls les articles directement au-dessus de l'article (dans la structure de nomenclature) provoquant le retard, seront mis à jour avec un retard dans le cadre de l'exécution de la planification principale. Le retard ne sera pas appliqué aux autres articles de la structure de la nomenclature tant que la première exécution de la planification principale n'est pas terminée, une fois l'ordre planifié pour le niveau supérieur approuvé ou confirmé. 

Pour contourner cette limitation connue, les ordres de fabrication en haut de la structure de la nomenclature avec des retards peuvent être approuvés (ou confirmés) avant la prochaine exécution de la planification principale. De cette façon, le retard par rapport à l'ordre de fabrication prévisionnel approuvé retardé sera conservé et tous les composants sous-jacents seront mis à jour en conséquence.
Les messages d'action peuvent être également utilisés pour identifier les ordres planifiés qui peuvent être déplacés à une date ultérieure, en raison d'autres retards dans la structure de la nomenclature.

## <a name="desired-date"></a>Date souhaitée

Dans la page **Ordre prévisionnel**, sous l'onglet **Retards**, se trouve la **Date souhaitée** pour l'ordre prévisionnel. La date souhaitée d'un ordre prévisionnel est la date de référence pour les retards, qui est une date calculée équivalente à la **Date demandée** calculée à partir des **Besoins nets**. Si l'ordre prévisionnel est une ligne de nomenclature, une ligne de production ou une ligne de kanban, la date souhaitée est basée sur la **Date de besoin** et la date souhaitée ne s'affiche pas dans la page **Ordre prévisionnel**.

<a name="additional-resources"></a>Ressources supplémentaires
--------

[Paramètres de couverture](coverage-settings.md)
