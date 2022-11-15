---
title: Annuler une tâche de planification
description: Cet article explique comment annuler une tâche active de planification qui utilise la fonctionnalité Optimisation de la planification.
author: t-benebo
ms.date: 02/18/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ReqCreatePlanWorkspace
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: benebotg
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: AX 10.0.5
ms.openlocfilehash: f5f1f2c8e3e43e36d837ebf989422b0dca7819d6
ms.sourcegitcommit: 491ab9ae2b6ed991b4eb0317e396fef542d3a21b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/03/2022
ms.locfileid: "9741174"
---
# <a name="cancel-a-planning-job"></a>Annuler une tâche de planification

[!include [banner](../../includes/banner.md)]

Dans Microsoft Dynamics 365 Supply Chain Management, vous pouvez annuler une tâche active de planification qui utilise la fonctionnalité Optimisation de la planification. Lorsque vous cliquez sur **Annuler** dans la boîte de dialogue lorsqu’une tâche d’optimisation de la planification est déclenchée directement à partir de l’interface utilisateur (pas en arrière-plan), cette dernière ne sera pas annulée. Même si vous recevez un avertissement tel que « Opération annulée », vous devez tout de même effectuer les étapes suivantes pour annuler une tâche de planification à l’aide de la fonctionnalité Optimisation de la planification.

Pour annuler une tâche active de planification, procédez comme suit.

> [!NOTE]
> Seules les tâches actives peuvent être annulées.

1. Accédez à **Planification \> Paramétrage \> Plans**.
2. Permet de sélectionner un plan approprié pour l’exécution de la planification.
3. Sélectionnez **Historique**.
4. Sélectionnez la tâche de planification à annuler.
5. Sélectionnez **Annuler**.

Le statut de tâche sera **Annulation en cours** jusqu’à ce que le service Optimisation de la planification confirme que la tâche a été annulée. Le statut est alors modifié et passe sur **Annulé**.

> [!NOTE]
> Pour voir les modifications du statut, vous devez actualiser la page en sélectionnant le bouton **Actualiser**.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]