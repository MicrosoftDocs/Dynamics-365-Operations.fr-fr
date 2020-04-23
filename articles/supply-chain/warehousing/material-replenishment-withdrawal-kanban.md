---
title: Réapprovisionnement avec des kanbans de prélèvement
description: Cette rubrique décrit comment le kanban de prélèvement est utilisé pour le réapprovisionnement des matières dans le cadre des activités de fabrication.
author: johanhoffmann
manager: tfehr
ms.date: 06/16/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: KanbanBoardTransferJob, KanbanFlow, KanbanRules
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: d712cc3ebdc959d1fee4a2a79e3283b84f0b901a
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/02/2020
ms.locfileid: "3205550"
---
# <a name="replenishment-with-withdrawal-kanbans"></a>Réapprovisionnement avec des kanbans de prélèvement

[!include [banner](../includes/banner.md)]

Cette rubrique décrit comment le kanban de prélèvement est utilisé pour le réapprovisionnement des matières dans le cadre des activités de fabrication.

## <a name="workflow-for-material-replenishment-that-uses-the-withdrawal-kanban"></a>Workflow pour le réapprovisionnement des matières qui utilise le kanban de prélèvement
-------------------------------------------------------------------

Le kanban de prélèvement permet de déplacer un kanban d'un seul article entre les entrepôts et les emplacements de production où les matières sont consommées. Le kanban de prélèvement prend en charge une solution basée sur le type pull pour le réapprovisionnement des matières, où un signal de type pull est requis pour déclencher l'approvisionnement suite à une demande spécifique. 

Le scénario suivant montre un système de réapprovisionnement basé sur le type pull dans lequel un signal de type pull déclenche la création d'un kanban pour réapprovisionner en matières un processus de production. 

[![Signal de type pull déclenchant la création d'un kanban pour réapprovisionner en matières un processus de production](./media/material-replenishment-with-withdrawal-kanban.png)](./media/material-replenishment-with-withdrawal-kanban.png)

1.  Kanban de prélèvement
2.  Emplacement d'origine et emplacement de rangement du kanban pour le travail d'entrepôt
3.  Emplacement de destination et emplacement d'entrée en production du kanban
4.  Processus de fabrication
5.  Travail d'entrepôt pour le prélèvement de kanban
6.  Emplacements de l'entrepôt pour les matières premières
7.  Entrepôt des matières
8.  Entrepôt de fabrication

Dans ce scénario, un processus de fabrication (4) consomme les matières d'un emplacement d'entrée en production (3) dans l'entrepôt de fabrication (8). Lorsqu'une unité de manutention des matières (kanban) est consommée, elle est enregistrée comme vide. Un signal de réapprovisionnement est créé pour l'origine de l'article, et un nouveau kanban (1) est créé. Dans ce cas, l'origine de l'article est constitué des emplacements dans l'entrepôt des matières (7). Les matières pour le kanban sont prélevées et mises à un emplacement (2) dans le même entrepôt. Lorsque la matière est prélevée, elle est prête à être transférée depuis l'emplacement 2 vers l'emplacement d'entrée en production (3) dans l'entrepôt de fabrication (8).

## <a name="configure-warehouse-work-for-kanban-picking-for-the-withdrawal-kanban"></a>Configurer le travail d'entrepôt pour le prélèvement de kanban dans le cadre du kanban de prélèvement

Pour activer le prélèvement des matières premières pour le kanban de prélèvement, configurez les modèles de vague, les modèles de travail et les instructions d'emplacement pour le type d'ordre d'exécution **Prélèvement de kanban**. Ce type d'ordre d'exécution ne prend pas en charge que le processus de prélèvement pour le kanban de prélèvement. Il prend également en charge le processus de prélèvement pour le kanban de fabrication. Toutefois, vous pouvez configurer un processus de prélèvement distinct pour chaque type de kanban en séparant les modèles de vague, les modèles de travail, ainsi que les instructions d'emplacement. Pour séparer les modèles de vague, les modèles de travail et les instructions d'emplacement, définissez des critères sous le type d'activité (**Traiter** ou **Transférer**) dans les requêtes pour ces entités.

## <a name="configure-the-withdrawal-kanban"></a>Configurer le kanban de prélèvement

L'activité de transfert utilisée pour le kanban de prélèvement est configurée comme faisant partie d'un programme d'activités dans un flux de production au plus juste. Lors de la configuration de l'activité de transfert, spécifiez les emplacements d'origine et de destination du transfert. Après avoir configuré l'activité de transfert, vous pouvez l'affecter à une règle de kanban du type **Prélèvement**. La règle de kanban définit les stratégies et les configurations pour le kanban de prélèvement. La quantité du kanban définit le nombre d'unités de l'unité de manutention que le kanban véhicule lors du processus de transfert. La quantité de kanban fixe est utilisée lorsque la stratégie de réapprovisionnement Fixe est sélectionnée. Cette quantité définit le nombre de kanbans nécessaires afin d'empêcher une rupture du stock à la source de la demande. La quantité fixe peut être basée sur la demande réelle calculée, la demande historique et les niveaux de service. Les deux scénarios suivants décrivent comment gérer le réapprovisionnement des matières qui utilise le kanban de prélèvement.

## <a name="scenario-1-replenish-a-production-input-location-by-using-a-fixed-withdrawal-kanban"></a>Scénario 1 : Réapprovisionner un emplacement d'entrée en production à l'aide d'un kanban de prélèvement fixe

Un processus de fabrication consomme les matières premières achetées d'un emplacement d'entrée en production qui se trouve dans l'entrepôt de fabrication. Lorsque les matières premières sont reçues du fournisseur, elles sont stockées dans l'entrepôt des matières. Comme la demande de matières est considérée stable au cours d'une période, elle est paramétrée pour assurer la production dans un flux de kanban de quantité fixe. Lorsqu'un kanban est consommé à l'emplacement d'entrée en production, un signal vide est enregistré, et un nouveau kanban du même type est ajouté au flux. 

Le signal vide peut être configuré pour être généré automatiquement lorsqu'un kanban est terminé. Sinon, le signal vide peut être défini comme une interaction manuelle, qui est émis par le tableau de transfert kanban ou un menu sur l'appareil portable. Le tableau de transfert kanban est l'espace de travail où toutes les activités du cycle de vie d'un kanban sont traitées. 

Lorsque le kanban est créé, une ligne de vague des matières premières est ajoutée à une vague de kanban pour l'entrepôt des matières. Dans la section de prélèvement du tableau de transfert kanban, le statut de la matière et les processus d'entrepôt associés peuvent être surveillés depuis la création de la vague et la création du travail, jusqu'à ce que la matière soit disponible à l'emplacement « transfert à partir de » et est prête à être transférée vers les emplacements d'entrée en production. Le kanban peut être exécuté depuis le tableau de transfert kanban ou depuis un menu sur l'appareil portable. 

Dans ce cas, les travaux de prélèvement dans l'entrepôt des matières sont traités comme une activité. L'activité de transfert entre l'entrepôt des matières et l'entrepôt de production est considérée comme une activité distincte. Cette approche peut être utile si, par exemple, il existe une grande distance physique entre les deux entrepôts. Dans ce cas, l'activité de transfert de kanban peut représenter un chargement de camion. 

Si la distance entre les emplacements d'entrepôt et l'emplacement d'entrée en production est courte, il peut être plus efficace d'inclure l'activité de transfert dans le processus de prélèvement. Ensuite, une fois la matière prélevée, celle-ci peut être placée directement à l'emplacement d'entrée en production. Pour prendre en charge ce processus, configurez l'activité de transfert afin qu'elle soit automatiquement exécutée lorsque le travail de prélèvement dans le cadre du kanban de prélèvement est traité.

## <a name="scenario-2-automatically-complete-the-transfer-activity-when-kanban-picking-work-is-processed"></a>Scénario 2 : Exécuter automatiquement l'activité de transfert lorsque le travail de prélèvement de kanban est traité

Dans le scénario suivant, l'activité de transfert du kanban de prélèvement est configurée pour un transfert entre deux emplacements au sein du même entrepôt. L'activité de transfert du kanban de prélèvement est paramétrée pour une exécution automatique. 

[![L'activité de transfert est exécutée automatiquement lorsque le travail de prélèvement de kanban est traité](./media/transfer-activities-when-processing-kanban-picking.png)](./media/transfer-activities-when-processing-kanban-picking.png)

1.  Entrepôt partagé pour les matières premières et la production
2.  Emplacements de l'entrepôt pour les matières premières
3.  Emplacement d'origine et emplacement de rangement du kanban pour le travail d'entrepôt
4.  Kanban de prélèvement
5.  Emplacement de l'entrée en production
6.  Processus de fabrication

Dès qu'un kanban est consommé à l'emplacement d'entrée en production, celui-ci est indiqué comme étant vide et un nouveau kanban est ajouté au flux. Lorsque le kanban est créé, une ligne de vague est ajoutée à une vague de kanban. Lorsque la vague de kanban est traitée, le travail d'entrepôt pour le prélèvement de kanban est créé. Le collaborateur de l'entrepôt traite le travail de prélèvement de kanban et reçoit l'ordre de prélever les matières pour le kanban dans un entrepôt. Une fois que le collaborateur d'entrepôt confirme le prélèvement, le kanban est automatiquement exécuté, puis le collaborateur d'entrepôt reçoit l'instruction de disposer les matières à l'emplacement d'entrée en production.

