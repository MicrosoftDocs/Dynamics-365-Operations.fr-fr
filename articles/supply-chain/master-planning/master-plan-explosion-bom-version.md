---
title: Éclatement d’une version de nomenclature
description: Cet article décrit un scénario de planification qui implique l’éclatement d’une version de nomenclature.
author: t-benebo
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ReqTransExplosion
audience: Application User
ms.reviewer: kamaybac
ms.custom: 19211
ms.assetid: fe08c2e6-9cc5-4e34-bbb2-cd07843403b5
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: benebotg
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 1ef8a04ce4ab2180f39a6d2bcdab976eb146d610
ms.sourcegitcommit: 491ab9ae2b6ed991b4eb0317e396fef542d3a21b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/03/2022
ms.locfileid: "9741228"
---
# <a name="explosion-of-a-bom-version"></a>Éclatement d’une version de nomenclature

[!include [banner](../includes/banner.md)]

Cet article décrit un scénario de planification qui implique l’éclatement d’une version de nomenclature.

Un éclatement de la demande d’une version de nomenclature crée une demande pour chaque ligne de nomenclature au niveau d’un site spécifique, et éventuellement d’un entrepôt spécifique. Dans une nomenclature spécifique à un site, un entrepôt spécifique peut être défini pour chaque ligne de nomenclature. En outre, pour chaque ligne de nomenclature, les paramètres de dimension de l’article déterminent si un entrepôt est requis ou non. La demande qui en résulte pour chaque ligne de nomenclature devient le point de départ d’un autre éclatement de la demande. Ce scénario de planification implique les conditions suivantes :

-   La dimension de site est obligatoire et doit être entrée dans la transaction de demande.
-   La dimension de site est cohérente. Le site pour la demande de niveau inférieur est donc identique au site de la transaction de demande initiale.

L’illustration suivante présente le processus d’éclatement de la demande de planification. ![Éclatement de la demande à l’aide d’une version de nomenclature.](./media/multisitedemandexplosionscenariousingbomversion.gif)

## <a name="additional-resources"></a>Ressources supplémentaires

- [Déterminer la version de nomenclature](master-plan-bom-version-determined.md)
- [Vue d’ensemble de planification générale et fonctionnalité multisite](master-plan-multisite-functionality.md)





[!INCLUDE[footer-include](../../includes/footer-banner.md)]