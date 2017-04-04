---
title: "Éclatement d&quot;une version de nomenclature"
description: "Cet article décrit un scénario de planification qui implique l&quot;éclatement d&quot;une version de (BOM) de nomenclature."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: ReqTransExplosion
audience: Application User
ms.reviewer: YuyuScheller
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 19211
ms.assetid: fe08c2e6-9cc5-4e34-bbb2-cd07843403b5
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: roxanad
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 9ccbe5815ebb54e00265e130be9c82491aebabce
ms.openlocfilehash: 6461a07f8c8f02f584e5ef70b21ebaf04f29b57b
ms.lasthandoff: 03/31/2017


---

# <a name="explosion-of-a-bom-version"></a>Éclatement d'une version de nomenclature

Cet article décrit un scénario de planification qui implique l'éclatement d'une version de (BOM) de nomenclature.

Un éclatement de la demande d'une version de nomenclature crée une demande pour chaque ligne de nomenclature au niveau d'un site spécifique, et éventuellement d'un entrepôt spécifique. Dans une nomenclature spécifique à un site, un entrepôt spécifique peut être défini pour chaque ligne de nomenclature. En outre, pour chaque ligne de nomenclature, les paramètres de dimension de l'article déterminent si un entrepôt est requis ou non. La demande qui en résulte pour chaque ligne de nomenclature devient le point de départ d'un autre éclatement de la demande. Ce scénario de planification implique les conditions suivantes :

-   La dimension de site est obligatoire et doit être entrée dans la transaction de demande.
-   La dimension de site est cohérente. Le site pour la demande de niveau inférieur est donc identique au site de la transaction de demande initiale.

L'illustration suivante présente le processus d'éclatement de la demande de planification. ![Éclatement de la demande à l'aide d'une version de nomenclature](./media/multisitedemandexplosionscenariousingbomversion.gif)

<a name="see-also"></a>Voir également :
--------

[Planification - comment la version de nomenclature est déterminée] (master-plan-bom-version-determined.md)

[Master planning and multisite functionality](master-plan-multisite-functionality.md)


