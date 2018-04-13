--- 
title: "Transférer des matières avec des tâches de kanban (février 2016 uniquement)"
description: "Cette procédure traite de l'exécution d'une tâche de kanban de prélèvement pour transférer des matériaux."
author: ChristianRytt
manager: AnnBe
ms.date: 02/07/2017
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
ms.openlocfilehash: c79480d844627a7eed8129515924f1f70ad04f95
ms.contentlocale: fr-fr
ms.lasthandoff: 11/06/2017

---
# <a name="transfer-materials-with-kanban-jobs-february-2016-only"></a>Transférer des matières avec des tâches de kanban (février 2016 uniquement)

[!INCLUDE [task guide banner](../../includes/task-guide-banner.md)]

Cette procédure traite de l'exécution d'une tâche de kanban de prélèvement pour transférer des matériaux. Les données fictives utilisées pour créer cette procédure correspondent à la société USMF. Cette procédure est destinée au magasinier.


## <a name="display-transfer-jobs"></a>Afficher les opérations de transfert
1. Allez dans Contrôle de la production > Kanban > Tableau kanban pour les opérations de transfert.
2. Développez ou réduisez la section Filtres.
    * Dans la section Filtres, vous pouvez spécifier les tâches que vous souhaitez afficher en filtrant sur Flux de production, Nom de l'activité, Entrepôt d'origine et Emplacement, et Entrepôt de destination et emplacement.  
3. Tapez « 11 » dans le champ Entrepôt d'origine.
4. Tapez « 12 » dans le champ Lieu de destination.

## <a name="start-a-transfer-job"></a>Commencer une tâche de transfert
1. Dans la liste, désélectionnez la ligne sélectionnée, le cas échéant.
2. Sélectionnez la ligne 4 dans la liste.
    * Sélectionnez la première tâche ayant le statut Non planifié. Assurez-vous que c'est la seule tâche sélectionnée.  
3. Cliquez sur Démarrer.
    * Notez qu'une icône indique que la tâche a commencé.  

## <a name="select-a-second-transfer-job-and-change-quantity"></a>Sélectionner une deuxième opération de transfert et modifier la quantité
1. Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.
    * Vous pouvez avoir plusieurs tâches sélectionnées, mais pour l'instant, sélectionnez la ligne 5.  
2. Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.
    * Vérifiez que la tâche de l'étape précédente est la seule sélectionnée. Désélectionnez toutes les autres tâches.  
3. Notez la valeur du champ Quantité de tâches pour la consulter plus tard
4. Définissez la quantité de tâches sur 30.
    * Notez l'avertissement ! Vous n'êtes pas autorisé à transférer 30. En fonction du paramétrage de la règle de kanban, vous pouvez uniquement transférer la quantité originale.  
5. Utiliser la valeur notée précédemment dans le champ Quantité de tâches
    * Définissez la quantité de tâches sur la valeur précédente.  

## <a name="start-the-second-transfer-job"></a>Démarrer la deuxième opération de transfert
1. Cliquez sur Démarrer.
    * Cela débute le transfert de la tâche dans la ligne 5.  

## <a name="complete-both-transfer-jobs"></a>Terminer les deux tâches de transfert
1. Sélectionnez la ligne 4 dans la liste.
    * Désormais deux tâches de transfert sont sélectionnées sur la ligne 4 et la ligne 5.  
2. Cliquez sur Terminé.
    * Le transfert des deux tâches est alors terminé.  


