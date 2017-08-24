--- 
title: "Modifier les règles de kanban pour une tâche de traitement"
description: "Cette procédure traite de la modification de la règle de kanban utilisée pour un kanban donné."
author: ChristianRytt
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
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f01d88149074b37517d00f03d8f55e1199a5198f
ms.openlocfilehash: e8355a94322e6489fe64f22a049a34b7ecfe65b9
ms.contentlocale: fr-fr
ms.lasthandoff: 07/27/2017

---
# <a name="change-kanban-rules-for-a-process-job"></a>Modifier les règles de kanban pour une tâche de traitement

[!include[task guide banner](../../includes/task-guide-banner.md)]

Cette procédure traite de la modification de la règle de kanban utilisée pour un kanban donné. Cela est utile pour l'équilibrage de charge des ressources ou en cas de panne. Les données fictives utilisées pour créer cette procédure correspondent à la société USMF. Cette procédure est destinée au planificateur, travaillant pour une société de lean manufacturing, responsable de la chaîne de valeur.


## <a name="copy-kanban-rule"></a>Copier une règle de kanban
1. Accédez aux règles de kanban.
2. Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.
    * Sélectionnez la règle de kanban d'événement 000022 pour L0001.  
3. Cliquez sur Dupliquer une règle de kanban.
4. Cliquez sur OK.

## <a name="change-kanban-rule"></a>Modifier une règle de kanban
1. Fermez la page.
2. Accédez à Planification de tâches de kanban.
3. Dans la liste, marquez la ligne sélectionnée.
    * Sélectionnez la ligne avec le Kanban 000177.  
4. Cliquez sur Utiliser une autre règle de kanban.
5. Cliquez sur Suivant.
6. Dans le champ Règle de kanban, saisissez ou sélectionnez une valeur.
    * Sélectionnez la règle de kanban créée précédemment. Il s'agit de la règle de kanban avec le numéro le plus élevé.  
7. Cliquez sur Terminer.
    * Actuellement, la tâche de kanban utilise une autre règle de kanban. Cela peut être utile pour l'équilibrage de charge des cellules de travail.  


