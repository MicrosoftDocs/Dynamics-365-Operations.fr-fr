--- 
title: "Déplacer les tâches de kanban planifiées"
description: "Cette procédure se concentre sur le déplacement des tâches de kanban d'un processus planifié dans une autre période."
author: ChristianRytt
manager: AnnBe
ms.date: 11/11/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Operations
ms.search.region: Global
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 2a12a6859a3a436706822873bc6fdd781e0ef032
ms.contentlocale: fr-fr
ms.lasthandoff: 09/29/2017

---
# <a name="move-scheduled-kanban-jobs"></a>Déplacer les tâches de kanban planifiées

[!include[task guide banner](../../includes/task-guide-banner.md)]

Cette procédure se concentre sur le déplacement des tâches de kanban d'un processus planifié dans une autre période. Les données fictives utilisées pour créer cette procédure correspondent à la société USMF. Cette procédure est destinée au superviseur d'atelier ou au responsable de production qui utilisent des kanbans.


## <a name="select-scheduled-kanban-jobs"></a>Sélectionner les tâches de kanban planifiées
1. Gå til Produktionsstyring > Kanban > Tidsplanlægning af kanban-job.
2. Dans le champ Cellule de travail, cliquez sur le bouton de liste déroulante pour ouvrir la recherche. áçêìõý !
3. Markér den valgte række på listen.
    * Sélectionnez la cellule de travail 1250.  
4. Klik på Select.
5. Vælg 'Planlagt' i feltet Display job status.
    * Cette opération filtre la liste des tâches pour afficher uniquement les tâches de kanban planifiées.  

## <a name="move-kanban-jobs-to-a-different-period"></a>Déplacer les tâches de kanban vers une autre période de planification.
1. Find og vælg den ønskede post på listen.
    * Sélectionnez une tâche dont le statut est planifié, par exemple, une tâche prévue le 20 décembre 2012 dans le champ Période planifiée. Déplacez ensuite la tâche vers la période précédente.  
2. Klik på Previous period.
3. Klik på End.
    * Cela déplacera la tâche à la fin de la liste des tâches comme la dernière tâche de la période précédente.  
4. Find og vælg den ønskede post på listen.
    * Sélectionnez une tâche dont le statut est planifié, par exemple, une tâche prévue le 18 décembre 2012 dans le champ Période planifiée. Déplacez ensuite la tâche vers la période suivante.  
5. Klik på Next period.
6. Klik på Start.
    * Cela déplacera la tâche au début de la liste des tâches comme la première tâche de la période précédente.  

## <a name="task-move-a-job-within-a-period"></a>Tâche : Déplacer une tâche dans une période.
1. Find og vælg den ønskede post på listen.
    * Sélectionnez une tâche dont le statut est planifié, par exemple, la deuxième tâche prévue le 19 décembre 2012 dans le champ Période planifiée. Déplacez ensuite la tâche dans la période planifiée.  
2. Klik på Forward.
    * Notez que la tâche est déplacée une ligne vers le bas dans la liste.  
3. Klik på Backward.
    * Notez que la tâche est déplacée une ligne vers le haut dans la liste.  


