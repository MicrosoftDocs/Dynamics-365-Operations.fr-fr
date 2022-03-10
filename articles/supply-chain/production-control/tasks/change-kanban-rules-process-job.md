---
title: Modifier les règles de kanban pour une tâche de traitement
description: Cette procédure traite de la modification de la règle de kanban utilisée pour un kanban donné.
author: johanhoffmann
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: KanbanRules, KanbanRuleDuplicate, KanbanJobSchedulingListPage, LeanRuleReassignmentWizard, KanbanReassignRuleLookup
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 13798e3521efacda896ca88a39faf36ac979d42c
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/29/2021
ms.locfileid: "7574495"
---
# <a name="change-kanban-rules-for-a-process-job"></a>Modifier les règles de kanban pour une tâche de traitement

[!include [banner](../../includes/banner.md)]

Cette procédure traite de la modification de la règle de kanban utilisée pour un kanban donné. Cela est utile pour l’équilibrage de charge des ressources ou en cas de panne. Les données fictives utilisées pour créer cette procédure correspondent à la société USMF. Cette procédure est destinée au planificateur, travaillant pour une société de lean manufacturing, responsable de la chaîne de valeur.


## <a name="copy-kanban-rule"></a>Copier une règle de kanban
1. Accédez aux règles de kanban.
2. Dans la liste, recherchez et sélectionnez l’enregistrement souhaité.
    * Sélectionnez la règle de kanban d’événement 000022 pour L0001.  
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
    * Sélectionnez la règle de kanban créée précédemment. Il s’agit de la règle de kanban avec le numéro le plus élevé.  
7. Cliquez sur Terminer.
    * Actuellement, la tâche de kanban utilise une autre règle de kanban. Cela peut être utile pour l’équilibrage de charge des cellules de travail.  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]