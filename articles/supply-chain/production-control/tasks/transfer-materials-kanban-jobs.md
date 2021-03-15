---
title: Transférer des matériaux avec des tâches de kanban
description: Cette procédure traite de l'exécution d'une tâche de kanban de prélèvement pour transférer des matériaux.
author: ChristianRytt
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: KanbanBoardTransferJob
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 4e8808b168d2b3845b315e6bbcfb376e37f31fe4
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4981029"
---
# <a name="transfer-materials-with-kanban-jobs"></a>Transférer des matériaux avec des tâches de kanban

[!include [banner](../../includes/banner.md)]

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



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]