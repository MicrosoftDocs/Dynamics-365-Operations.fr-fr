---
title: Afficher l’historique du plan et les journaux de planification
description: Cette rubrique explique comment afficher l’historique des tâches de planification déclenchées par la fonctionnalité d’Optimisation de la planification.
author: ChristianRytt
ms.date: 10/30/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: MPSPlanRegenerationJobList, MPSPlanRegenerationJobLogs
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: AX 10.0.5
ms.openlocfilehash: d7bba084b03f8698c8bf31d171d5e4e486ed06ad
ms.sourcegitcommit: a7649b361ec54b49c0e9ee1c1c63a8815f320225
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/04/2021
ms.locfileid: "6187245"
---
# <a name="view-plan-history-and-planning-logs"></a>Afficher l’historique du plan et les journaux de planification

[!include [banner](../../includes/banner.md)]

Cette rubrique explique comment afficher l’historique des tâches de planification déclenchées par la fonctionnalité d’Optimisation de la planification dans Microsoft Dynamics 365 Supply Chain Management.

Pour afficher l’historique d’un plan, ouvrez le plan en accédant à **Planification** \> **Paramétrage** \> **Plans** \> **Plans généraux** et en sélectionnant **Historique**. L’historique répertorie toutes les tâches du plan sélectionné. La liste inclut les tâches terminées et actives.

L’historique des exécutions de la planification générale de l’optimisation de la planification ne conserve que 60 enregistrements maximum par plan général. Chaque fois que vous exécutez un nouveau calcul de planification générale, le premier enregistrement de l’historique de ce plan est supprimé.

Outre le fait de voir l’heure de début et le statut des tâches, vous pouvez afficher le journal pour une tâche spécifique. Le journal inclut des informations supplémentaires et des avertissements. Toutes les tâches n’ont pas un journal. Pour afficher le journal pour une tâche, sélectionnez **Journal**. Les entrées de journal ne sont stockées que pendant 30 jours après la date de fin de la tâche, après quoi elles sont automatiquement supprimées.

## <a name="related-resources"></a>Ressources associées

- [Vue d’ensemble de l’optimisation de la planification](planning-optimization-overview.md)
- [Mise en route de l’optimisation de la planification](get-started.md)
- [Analyse de concordance d’optimisation de la planification](planning-optimization-fit-analysis.md)
- [Appliquer les filtres à un plan](plan-filters.md)
- [Annuler une tâche de planification](cancel-planning-job.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]