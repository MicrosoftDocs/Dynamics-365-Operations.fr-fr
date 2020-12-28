---
title: Exécuter les opérations de traitement du kanban
description: Cette procédure se concentre sur l'exécution des tâches de traitement de kanban.
author: ChristianRytt
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: KanbanBoardWorkCell, KanbanJobStatusUpdate
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: a1c32b577007c400f3528a110436eb97aaabefe2
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4427935"
---
# <a name="execute-kanban-process-jobs"></a>Exécuter les opérations de traitement du kanban

[!include [banner](../../includes/banner.md)]

Cette procédure se concentre sur l'exécution des tâches de traitement de kanban. La première tâche est terminée avec la quantité prévue et il n'y a pas d'erreurs. La deuxième tâche est exécutée avec des erreurs. Les données fictives utilisées pour créer cette procédure correspondent à la société USMF. Cette procédure est destinée à l'opérateur.


## <a name="select-a-kanban-job"></a>Sélectionnez une tâche de kanban.
1. Accédez à Contrôle de la production > Kanban > Tableau kanban pour les opérations de traitement.
2. Dans le champ Cellule de travail, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.
3. Cliquez sur la ligne dont le groupe de ressources est 1250. Cela filtre la liste des tâches pour afficher uniquement les tâches de la cellule de travail 1250.
    * Marquez la ligne dont le statut est Planifié.  

## <a name="complete-a-job-with-expected-quantity"></a>Effectuer une tâche avec la quantité prévue
1. Développez ou réduisez la section Détails.
    * Cette section affiche des informations importantes sur le numéro de carte, le numéro d'article, la quantité commandée et le nom de l'activité.  
2. Développez ou réduisez la section Instructions de production.
    * Cette section affiche les instructions de production pour l'activité. Il peut s'agir d'un texte, d'images, de dessins et d'autres documents.  
3. Cliquez sur Démarrer.
    * Sélectionnez une tâche qui n'est pas terminée. Utilisez les icônes de statut dans le champ Statut de tâche pour afficher le statut de la tâche.      
4. Cliquez sur Terminé.
    * La tâche est exécutée avec la qualité prévue.  

## <a name="complete-a-job-with-errors"></a>Effectuer une tâche avec des erreurs
1. Cliquez sur Démarrer.
    * Lorsqu'une tâche est terminée, la tâche suivante dans la liste est activée automatiquement. C'est pourquoi vous n'avez pas à sélectionner une tâche avant de cliquer sur Démarrer.  
2. Dans le volet Actions, cliquez sur Fabrication.
3. Cliquez sur Terminer (détails).
4. Dans la liste, marquer la ligne sélectionnée.
5. Entrez un nombre dans le champ Quantité erronée.
6. Entrez un nombre dans le champ Quantité correcte.
7. Cliquez sur OK.

