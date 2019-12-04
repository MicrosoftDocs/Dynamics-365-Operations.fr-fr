---
title: Annuler une tâche de planification
description: Cette rubrique explique comment annuler une tâche active de planification qui utilise la fonctionnalité Optimisation de la planification.
author: ChristianRytt
manager: AnnBe
ms.date: 10/26/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ReqCreatePlanWorkspace
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: AX 10.0.5
ms.openlocfilehash: a2d90f04985fdd66ca83582ee676100fffb26981
ms.sourcegitcommit: fbc106af09bdadb860677f590464fb93223cbf65
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/06/2019
ms.locfileid: "2773960"
---
[!include [banner](../../includes/banner.md)]
[!include [banner](../../includes/preview-banner.md)]

# <a name="cancel-a-planning-job"></a>Annuler une tâche de planification

Dans Microsoft Dynamics 365 Supply Chain Management, vous pouvez annuler une tâche active de planification qui utilise la fonctionnalité Optimisation de la planification.

Pour annuler une tâche active de planification, procédez comme suit.

> [!NOTE]
> Seules les tâches actives peuvent être annulées.

1. Accédez à **Planification \> Paramétrage \> Plans**.
2. Permet de sélectionner un plan approprié pour l'exécution de la planification.
3. Sélectionnez **Historique**.
4. Sélectionnez la tâche de planification à annuler.
5. Sélectionnez **Annuler**.

Le statut de tâche sera **Annulation en cours** jusqu'à ce que le service Optimisation de la planification confirme que la tâche a été annulée. Le statut est alors modifié et passe sur **Annulé**.

> [!NOTE]
> Pour voir les modifications du statut, vous devez actualiser la page en sélectionnant le bouton **Actualiser**.

## <a name="related-resources"></a>Ressources associées

[Vue d'ensemble de l'optimisation de la planification](planning-optimization-overview.md)

[Prise en main de l'Optimisation de la planification](get-started.md)

[Analyse de concordance d'optimisation de la planification](planning-optimization-fit-analysis.md)

[Afficher l'historique du plan et les journaux de planification](plan-history-logs.md)

[Appliquer les filtres à un plan](plan-filters.md)
