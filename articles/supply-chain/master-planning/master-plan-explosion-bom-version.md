---
title: Éclatement d'une version de nomenclature
description: Cet article décrit un scénario de planification qui implique l'éclatement d'une version de nomenclature.
author: roxanadiaconu
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ReqTransExplosion
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 19211
ms.assetid: fe08c2e6-9cc5-4e34-bbb2-cd07843403b5
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: roxanad
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 4f3c800d96805df38a2e31018f2d6c305e3ed7da
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/15/2019
ms.locfileid: "1564575"
---
# <a name="explosion-of-a-bom-version"></a>Éclatement d'une version de nomenclature

[!include [banner](../includes/banner.md)]

Cet article décrit un scénario de planification qui implique l'éclatement d'une version de nomenclature.

Un éclatement de la demande d'une version de nomenclature crée une demande pour chaque ligne de nomenclature au niveau d'un site spécifique, et éventuellement d'un entrepôt spécifique. Dans une nomenclature spécifique à un site, un entrepôt spécifique peut être défini pour chaque ligne de nomenclature. En outre, pour chaque ligne de nomenclature, les paramètres de dimension de l'article déterminent si un entrepôt est requis ou non. La demande qui en résulte pour chaque ligne de nomenclature devient le point de départ d'un autre éclatement de la demande. Ce scénario de planification implique les conditions suivantes :

-   La dimension de site est obligatoire et doit être entrée dans la transaction de demande.
-   La dimension de site est cohérente. Le site pour la demande de niveau inférieur est donc identique au site de la transaction de demande initiale.

L'illustration suivante présente le processus d'éclatement de la demande de planification. ![Éclatement de la demande à l'aide d'une version de nomenclature](./media/multisitedemandexplosionscenariousingbomversion.gif)

<a name="additional-resources"></a>Ressources supplémentaires
--------

[Planification - Méthode de détermination de la version de nomenclature](master-plan-bom-version-determined.md)

[Planification et fonctionnalité multisite](master-plan-multisite-functionality.md)



