--- 
title: "Préparer une tâche de kanban de processus lorsque les matières ne sont pas disponibles pour la cellule de travail"
description: "Cette procédure se concentre sur la préparation d'une tâche de kanban de processus lorsque certaines matières sont disponibles pour la cellule de travail par conséquent, il est nécessaire de prélever des matières de l'entrepôt."
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
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 5a47af6910a9686e74ab6d1069dd02079e60cb8a
ms.contentlocale: fr-fr
ms.lasthandoff: 09/29/2017

---
# <a name="prepare-a-process-kanban-job-when-materials-are-not-available-for-the-work-cell"></a>Préparer une tâche de kanban de processus lorsque les matières ne sont pas disponibles pour la cellule de travail

[!include[task guide banner](../../includes/task-guide-banner.md)]

Cette procédure se concentre sur la préparation d'une tâche de kanban de processus lorsque certaines matières sont disponibles pour la cellule de travail par conséquent, il est nécessaire de prélever des matières de l'entrepôt. La procédure « Préparer une tâche de kanban de processus lorsque les matières sont disponibles » est une étape préliminaire à la création de cette procédure. Cette procédure est destinée à l'opérateur. Les données fictives utilisées pour créer cette procédure correspondent à la société USMF.

1. Accédez à Contrôle de la production > Kanban > Tableau kanban pour les opérations de traitement.
2. Dans le champ Cellule de travail, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.
3. Dans la liste, cliquer sur le lien dans la ligne sélectionnée.
    * Sélectionnez la cellule de travail 1250.  
4. Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.
    * Sélectionnez Kanban 000356.  
5. Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.
    * Dans la liste, désélectionnez la ligne 4 ou sélectionnez-la si vous n'avez pas terminé la tâche « Préparer une tâche de kanban de processus lorsque les matières sont disponibles ».  
6. Activez ou désactivez l'extension de la section Prélèvements.
    * L'icône Aucune entrée dans le statut d'approvisionnement indique qu'il manque 48 ea dans l'article P0002 pour la cellule de travail.  

## <a name="transfer-materials-to-work-cell"></a>Transférer les matériaux à la cellule de travail
1. Activez ou désactivez l'extension de la section Tâches de transfert.
2. Utilisez le filtre rapide pour filtrer sur le champ Numéro d'article avec une valeur de « P0002 ».
3. Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.
4. Cliquez sur Démarrer.
    * Le transfert est en cours.  
5. Cliquez sur Terminé.
    * L'article P0002 est à présent disponible dans les prélèvements pour la tâche de kanban. Cela signifie que nous pouvons préparer le kanban avec toutes les matériaux nécessaires.  
6. Cliquez sur Préparer.
    * Notez qu'une icône dans le statut de la tâche indique que la tâche est désormais prête.  


