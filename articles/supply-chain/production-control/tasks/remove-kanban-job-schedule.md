--- 
title: "Supprimer une tâche de kanban du programme"
description: "Cette procédure consiste à supprimer une tâche de kanban d'un processus planifié du programme en basculant le statut de la tâche sur Non planifié."
author: ChristianRytt
manager: AnnBe
ms.date: 11/11/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations
ms.search.region: Global
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 9a0f246bfe42dde0befdf5c4f01d2ad1e1200b12
ms.contentlocale: fr-fr
ms.lasthandoff: 11/06/2017

---
# <a name="remove-a-kanban-job-from-the-schedule"></a>Supprimer une tâche de kanban du programme

[!include [task guide banner](../../includes/task-guide-banner.md)]

Cette procédure consiste à supprimer une tâche de kanban d'un processus planifié du programme en basculant le statut de la tâche sur Non planifié. Les données fictives utilisées pour créer cette procédure correspondent à la société USMF. Cette procédure est destinée au superviseur d'atelier ou au responsable de production.


## <a name="find-a-planned-kanban-job"></a>Rechercher une tâche de kanban planifiée
1. Accédez à Contrôle de la production > Kanban > Planification de tâches de kanban.
2. Dans le champ Cellule de travail, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.
3. Dans la liste, cliquer sur le lien dans la ligne sélectionnée.
    * Sélectionnez la cellule de travail 1250.  
4. Cliquez sur Sélectionner.
5. Sélectionnez « Planifié » dans le champ Afficher le statut de la tâche.

## <a name="remove-the-planned-kanban-job-from-the-schedule"></a>Supprimer la tâche de kanban planifiée du programme
1. Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.
    * Sélectionnez une tâche dont le statut est Planifié, par exemple, une tâche du 19 décembre 2012.  
2. Cliquez sur Planifier dans le volet Actions.
3. Cliquez sur Rétablir le statut de la tâche.
4. Cliquez sur OK.
    * Cela va basculer le statut de la tâche actuel de « Planifié » à « Non planifié » et l'enlèvera du tableau de traitement.   


