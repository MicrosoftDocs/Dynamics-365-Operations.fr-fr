---
title: Déplacer les tâches de kanban planifiées
description: Cette procédure se concentre sur le déplacement des tâches de kanban d'un processus planifié dans une autre période.
author: ChristianRytt
manager: tfehr
ms.date: 11/07/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: KanbanJobSchedulingListPage
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 2769a7d519e12613796025b658db0b08cdfc4fde
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4961638"
---
# <a name="move-scheduled-kanban-jobs"></a>Déplacer les tâches de kanban planifiées

[!include [banner](../../includes/banner.md)]

Cette procédure se concentre sur le déplacement des tâches de kanban d'un processus planifié dans une autre période. Les données fictives utilisées pour créer cette procédure correspondent à la société USMF. Cette procédure est destinée au superviseur d'atelier ou au responsable de production qui utilisent des kanbans.

## <a name="select-scheduled-kanban-jobs"></a>Sélectionner les tâches de kanban planifiées. 

1. Accédez à **Contrôle de la production > Kanban > Planification de tâches de kanban**. 

2. Dans le champ **Cellule de travail**, cliquez sur le bouton de liste déroulante pour ouvrir la recherche. 

3. Dans la liste, marquez la ligne sélectionnée. 
   - Sélectionnez la cellule de travail 1250. 
4. Cliquez sur **Sélectionner**. 

5. Sélectionnez **Planifié** dans le champ **Afficher le statut de la tâche**. Cette opération filtre la liste des tâches pour afficher uniquement les tâches de kanban planifiées. 

## <a name="move-kanban-jobs-to-a-different-period"></a>Déplacer les tâches de kanban vers une autre période de planification. 

1. Dans la liste, recherchez et sélectionnez l'enregistrement souhaité. Sélectionnez une tâche dont le statut est **Planifié**, par exemple, une tâche prévue le 20 décembre 2012 dans le champ **Période planifiée**. Déplacez ensuite la tâche vers la période précédente. 

2. Cliquez sur **Période précédente**. 

3. Cliquez sur **Fin** pour déplacer la tâche à la fin de la liste des tâches comme la dernière tâche de la période précédente. 

4. Dans la liste, recherchez et sélectionnez l'enregistrement souhaité. Sélectionnez une tâche dont le statut est **Planifié**, par exemple, une tâche prévue le 18 décembre 2012 dans le champ **Période planifiée**. Déplacez ensuite la tâche vers la période suivante. 

5. Cliquez sur **Période suivante**. 

6. Cliquez sur **Début** pour déplacer la tâche au début de la liste des tâches comme la première tâche de la période précédente. 

## <a name="move-a-job-within-a-period"></a>Déplacer une tâche dans une période. 

1. Dans la liste, recherchez et sélectionnez l'enregistrement souhaité. Sélectionnez une tâche dont le statut est planifié, par exemple, la deuxième tâche prévue le 19 décembre 2012 dans le champ **Période planifiée**. Déplacez ensuite la tâche dans la période planifiée. 

2. Cliquez sur **Suivant**. Notez que la tâche est déplacée une ligne vers le bas dans la liste. 

3. Cliquez sur **Précédent**. Notez que la tâche est déplacée une ligne vers le haut dans la liste.
