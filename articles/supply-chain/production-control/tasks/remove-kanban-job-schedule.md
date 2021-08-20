---
title: Supprimer une tâche de kanban du programme
description: Cette procédure consiste à supprimer une tâche de kanban d’un processus planifié du programme en basculant le statut de la tâche sur Non planifié.
author: ChristianRytt
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: KanbanJobSchedulingListPage, SysLookupMultiSelectGrid, KanbanJobStatusUpdate
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: eeedfad5f294f73097fc1b6a973d63125df72209227fc06470663665961af2d4
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6756917"
---
# <a name="remove-a-kanban-job-from-the-schedule"></a>Supprimer une tâche de kanban du programme

[!include [banner](../../includes/banner.md)]

Cette procédure consiste à supprimer une tâche de kanban d’un processus planifié du programme en basculant le statut de la tâche sur Non planifié. Les données fictives utilisées pour créer cette procédure correspondent à la société USMF. Cette procédure est destinée au superviseur d’atelier ou au responsable de production.


## <a name="find-a-planned-kanban-job"></a>Rechercher une tâche de kanban planifiée
1. Accédez à Contrôle de la production > Kanban > Planification de tâches de kanban.
2. Dans le champ Cellule de travail, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.
3. Dans la liste, cliquer sur le lien dans la ligne sélectionnée.
    * Sélectionnez la cellule de travail 1250.  
4. Cliquez sur Sélectionner.
5. Sélectionnez « Planifié » dans le champ Afficher le statut de la tâche.

## <a name="remove-the-planned-kanban-job-from-the-schedule"></a>Supprimer la tâche de kanban planifiée du programme
1. Dans la liste, recherchez et sélectionnez l’enregistrement souhaité.
    * Sélectionnez une tâche dont le statut est Planifié, par exemple, une tâche du 19 décembre 2012.  
2. Cliquez sur Planifier dans le volet Actions.
3. Cliquez sur Rétablir le statut de la tâche.
4. Cliquez sur OK.
    * Cela va basculer le statut de la tâche actuel de « Planifié » à « Non planifié » et l’enlèvera du tableau de traitement.   



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]