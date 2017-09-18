--- 
title: "Rétablir le statut de l'opération kanban"
description: "Cette procédure traite du rétablissement d'un statut de tâche de kanban incorrect."
author: YuyuScheller
manager: AnnBe
ms.date: 03/02/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: yuyus
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 9b947a02be981155053e33a4ef20e19bf2a194a5
ms.openlocfilehash: 00b6ae872e60a322c994420ab69236abef7fb312
ms.contentlocale: fr-fr
ms.lasthandoff: 07/27/2017

---
# <a name="revert-kanban-job-status"></a>Rétablir le statut de l'opération kanban

[!include[task guide banner](../../includes/task-guide-banner.md)]

Cette procédure traite du rétablissement d'un statut de tâche de kanban incorrect. Cela est utile au cas où l'opérateur mettrait à jour la tâche incorrecte, ou définirait le statut incorrect par erreur. Dans cette procédure, une tâche de kanban est enregistrée comme préparée par erreur, et le statut est rétabli. Les données fictives utilisées pour créer cette procédure correspondent à la société USMF. Cette procédure est destinée au responsable de magasin ou à l'opérateur travaillant pour une société de lean manufacturing.


## <a name="open-process-board-for-the-work-cell"></a>Ouvrir le tableau de traitement pour la cellule de travail
1. Allez dans le tableau kanban pour les opérations de traitement.
2. Dans le champ Cellule de travail, saisissez ou sélectionnez une valeur.
    * Sélectionnez la cellule de travail 1260.  

## <a name="prepare-kanban-job"></a>Préparer une tâche de kanban
1. Cliquez sur Préparer.
    * Si vous ne pouvez pas cliquer sur Préparer car l'option est grisée, assurez-vous que la tâche de kanban sélectionnée a le statut Planifiée, qui est indiqué par l'icône de kanban vide. Si la préparation échoue, vérifiez que toutes les matières des prélèvements sont disponibles.  
2. Dans la liste, sélectionnez la tâche préparée.
    * Sélectionnez la première tâche que vous venez de préparer.  
    * Remarquez que le statut des tâches est Préparée, ce qui est signalé par un triangle à l'intérieur de l'icône de kanban.  

## <a name="revert-the-status-of-the-prepared-kanban-job"></a>Rétablir le statut de la tâche de kanban préparée
1. Dans la liste, marquez la ligne sélectionnée.
    * Sélectionnez la première tâche ayant été préparée.  
2. Dans le volet Actions, cliquez sur Fabrication.
3. Cliquez sur Rétablir le statut.
    * Vous pouvez utiliser une autre règle de kanban lorsque les conditions suivantes sont remplies : - La stratégie de réapprovisionnement est la même pour les deux règles.  - La version du flux de production est la même pour les deux règles.  - Le produit qui est fourni est identique pour les deux règles.  - Toutes les activités en aval qui sont configurées pour la dernière activité des règles de kanban doivent être identiques pour les deux règles.  - Les mêmes dimensions de stock fournies doivent être configurées pour les deux règles.  - Le statut de l'unité de manutention doit être Non affecté.  - Les configurations des kanbans d'événement doivent être identique.  
    * Vérifiez que le nouveau statut est Planifié.  
4. Cliquez sur OK.
5. Dans la liste, désactiver la ligne sélectionnée.
    * Sélectionnez la même tâche.  
    * Remarquez que le statut de la tâche de kanban est revenu à Planifiée, ce qui est signalé par une icône de kanban vide.  

