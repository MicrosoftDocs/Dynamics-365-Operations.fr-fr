---
title: Préparer une tâche de kanban de processus lorsque les matières sont disponibles pour la cellule de travail
description: Cette tâche se concentre sur la préparation d'une tâche de kanban de processus lorsque toutes les matières ne sont pas disponibles pour la cellule de travail.
author: johanhoffmann
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: KanbanBoardWorkCell
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: cf163968474e91da7e3d47fd638a857a76179645
ms.sourcegitcommit: fcb27d6a46cd544feef34f6ec7607bdd46b0c12b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/18/2020
ms.locfileid: "3148969"
---
# <a name="prepare-a-process-kanban-job-when-materials-are-available-for-the-work-cell"></a>Préparer une tâche de kanban de processus lorsque les matières sont disponibles pour la cellule de travail

[!include [banner](../../includes/banner.md)]

Cette tâche se concentre sur la préparation d'une tâche de kanban de processus lorsque toutes les matières ne sont pas disponibles pour la cellule de travail. Les données fictives utilisées pour créer cette tâche correspondent à la société USMF. Cette tâche est destinée à l'opérateur.

1. Allez dans le tableau kanban pour les opérations de traitement.
2. Dans le champ Cellule de travail, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.
3. Dans la liste, cliquer sur le lien dans la ligne sélectionnée.
    * Sélectionnez la cellule de travail 1250 et cliquez sur OK.  
4. Sélectionnez la ligne 4 dans la liste.
    * Dans la société fictive de démonstration, le kanban 000329 de la ligne 4 est la première tâche qui n'est pas encore terminée.  
5. Activez ou désactivez l'extension de la section Prélèvements.
    * Vérifiez que le statut d'approvisionnement est disponible pour tous les articles des prélèvements.  
    * Si plusieurs tâches sont activées, les prélèvements indique la somme de tous les articles nécessaires pour les tâches sélectionnées.  
6. Cliquez sur Préparer.
    * Le processus de préparation est désormais terminé. La case à cocher activée pour toutes les lignes des prélèvements indique que le statut d'approvisionnement est prélevé.  

