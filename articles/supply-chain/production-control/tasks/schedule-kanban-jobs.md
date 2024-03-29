---
title: Planification des tâches de kanban
description: Cette procédure se concentre sur des tâches de kanban du processus de planification pour une cellule de travail spécifique.
author: johanhoffmann
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: KanbanJobSchedulingListPage, KanbanPeriodCapacityPart, SysLookupMultiSelectGrid, KanbanBoardScheduleJobForward
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 2cab3af0802ae6fa942460cfdd9c0819e1d31d4b
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/29/2021
ms.locfileid: "7579086"
---
# <a name="schedule-kanban-jobs"></a>Planification des tâches de kanban

[!include [banner](../../includes/banner.md)]

Cette procédure se concentre sur des tâches de kanban du processus de planification pour une cellule de travail spécifique. La procédure « Préparer une tâche de kanban de processus lorsque les matières ne sont pas disponibles » est une étape préliminaire à la création de cette procédure. Les données fictives utilisées pour créer cette procédure correspondent à la société USMF. Cette tâche est destinée au superviseur d’atelier et au responsable de production qui utilisent des kanbans.


## <a name="select-kanban-jobs-for-a-work-cell"></a>Sélectionner les tâches de kanban pour une cellule de travail
1. Accédez à Contrôle de la production > Kanban > Planification de tâches de kanban.
2. Développez le récapitulatif Capacité de la période.
    * Développez le récapitulatif Kanban.  
3. Dans le champ Cellule de travail, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.
4. Dans la liste, marquez la ligne sélectionnée.
    * Sélectionnez la cellule de travail 1250. Cela filtrera l’affichage pour afficher uniquement les tâches de la cellule de travail 1250.  
5. Dans la liste, cliquer sur le lien dans la ligne sélectionnée.
6. Cliquez sur Sélectionner.

## <a name="schedule-a-kanban-job-in-the-first-available-period"></a>Planifier une tâche de kanban dans la première période disponible
1. Dans la liste, marquez la ligne sélectionnée.
    * Sélectionnez la première ligne de la liste ayant le statut Non prévu. L’icône en pointillés du champ Statut de tâche signifie Non prévu.  
2. Cliquez sur Programme.
    * Cela planifie la tâche de kanban de la première période disponible.  
    * Notez que la tâche de kanban est déplacée à la fin de la liste car elle a été ajoutée à la période le jour-même.  
    * Si la période commençant le jour-même est entièrement réservée, la tâche sera déplacée vers la première période disponible.  

## <a name="schedule-two-kanban-jobs-for-a-specific-day"></a>Planifier deux tâches de kanban pour un jour spécifique
1. Sélectionnez la ligne 1 dans la liste.
    * Vous devez voir que la première ligne a le statut Non prévu dans le champ Statut de tâche.  
2. Sélectionnez la ligne 2 dans la liste.
    * Vous devez voir que la deuxième ligne a le statut Non prévu dans le champ Statut de tâche. Les deux premières tâches sont désormais sélectionnées.  
3. Cliquez sur Planifier à partir de la date pour ouvrir la boîte de dialogue.
4. Activez ou désactivez la case à cocher Remplacer la réaction de pénurie de capacité.
    * Cette option permet d’ignorer la réaction de pénurie de capacité par défaut.  
5. Dans le champ Réaction de pénurie de capacité, sélectionnez « Ajouter à la période demandée ».
    * Cette option garantit que la tâche est ajoutée à la période requise, sans tenir compte de la surcharge éventuelle de la cellule de travail.  
6. Cliquez sur Programme.
    * Notez que les deux tâches sont ajoutées à la période souhaitée.  
    * Dans la section Capacité de la période, vous pouvez afficher la charge pour chaque période. Le champ Consommation affiche la consommation prévue pendant cette période. Si la consommation prévue est supérieure à la capacité disponible pendant cette période, la consommation surchargée sera sélectionnée.  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]