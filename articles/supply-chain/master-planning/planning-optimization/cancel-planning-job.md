---
title: Annuler une tâche de planification
description: Cette rubrique explique comment annuler une tâche active de planification qui utilise la fonctionnalité Optimisation de la planification.
author: ChristianRytt
manager: tfehr
ms.date: 02/18/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ReqCreatePlanWorkspace
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: AX 10.0.5
ms.openlocfilehash: 4b65d344cd764740cc1485969c2fc4c2052e55e2
ms.sourcegitcommit: 68092ed283bfbb7b6f611cce1b62c791f9b6a208
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/30/2020
ms.locfileid: "3323460"
---
# <a name="cancel-a-planning-job"></a>Annuler une tâche de planification

[!include [banner](../../includes/banner.md)]

Dans Microsoft Dynamics 365 Supply Chain Management, vous pouvez annuler une tâche active de planification qui utilise la fonctionnalité Optimisation de la planification. Lorsque vous cliquez sur **Annuler** dans la boîte de dialogue lorsqu'une tâche d'optimisation de la planification est déclenchée directement à partir de l'interface utilisateur (pas en arrière-plan), cette dernière ne sera pas annulée. Même si vous recevez un avertissement tel que « Opération annulée », vous devez tout de même effectuer les étapes suivantes pour annuler une tâche de planification à l'aide de la fonctionnalité Optimisation de la planification.


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

## <a name="additional-resources"></a>Ressources supplémentaires

[Vue d'ensemble de l'optimisation de la planification](planning-optimization-overview.md)

[Mise en route de l'optimisation de la planification](get-started.md)

[Analyse de concordance d'optimisation de la planification](planning-optimization-fit-analysis.md)

[Afficher l'historique du plan et les journaux de planification](plan-history-logs.md)

[Appliquer les filtres à un plan](plan-filters.md)
