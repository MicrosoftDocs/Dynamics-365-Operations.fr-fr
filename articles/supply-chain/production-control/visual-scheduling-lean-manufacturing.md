---
title: Planification visuelle pour Lean manufacturing
description: Cette rubrique fournit des informations relatives à la carte de programme du kanban, que le gestionnaire de production peut utiliser pour contrôler et optimiser le plan de production pour les tâches de kanban.
author: johanhoffmann
ms.date: 06/16/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: KanbanBoard, KanbanJobSchedulingListPage, LeanProductionFlowVisualization, KanbanBoardUnplannedJobs
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: c94834a491877a69a206f827ad60f12455456e3f
ms.sourcegitcommit: ff09736563d3cd2bc74c7664edd1767b218401cb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/04/2021
ms.locfileid: "6188845"
---
# <a name="visual-scheduling-for-lean-manufacturing"></a>Planification visuelle pour Lean manufacturing

[!include [banner](../includes/banner.md)]

Cette rubrique fournit des informations relatives à la carte de programme du kanban, que le gestionnaire de production peut utiliser pour contrôler et optimiser le plan de production pour les tâches de kanban.

Cette rubrique fournit des informations relatives à la carte de programme du kanban, que le gestionnaire de production peut utiliser pour contrôler et optimiser le plan de production pour les tâches de kanban.

La carte de programme du kanban permet au gestionnaire de production de contrôler et d’optimiser le plan de production pour les tâches de kanban. Il assure la transparence du flux des tâches de kanban et fournit au gestionnaire de production un outil qui optimise et ajuste le plan de production pour la cellule de travail du lean manufacturing.

## <a name="visual-scheduling-of-kanban-jobs"></a>Planification visuelle des tâches de kanban
Une tâche de kanban peut comporter une ou plusieurs tâches de kanban. Il existe deux types de tâches de kanban :

-   Processus
-   Transfert

Vous pouvez planifier uniquement les tâches de type **Traiter**. La tâche de kanban et ses propriétés, telles que la durée d’activité, sont définies dans le flux kanban de production. Dans le flux kanban de production, la tâche de kanban est également affectée à une cellule de travail. La capacité quotidienne de la cellule de travail est calculée en fonction de la capacité de la cellule de travail qui est définie dans le groupe de ressources. Elle est ajustée en fonction du temps de travail quotidien dans le calendrier associé. Lorsqu’une tâche de kanban est planifiée, la tâche charge la capacité de la cellule de travail. La carte de programme du kanban fournit les principales fonctionnalités suivantes :

-   Une vue d’ensemble graphique du plan de production dans une cellule de travail au plus juste. Cette vue d’ensemble affiche les tâches de traitement planifiées du kanban dans les périodes définies.
-   Un outil qui vous permet de planifier les tâches de kanban non planifiées et de replanifier les tâches déjà planifiées.

## <a name="kanban-schedule-board"></a>Carte de programme du kanban
La page **Carte de programme du kanban** contient sept éléments principaux, comme indiqué dans l’illustration suivante. 

![Carte de programme du kanban](./media/kanban-schedule-board-1024x554.png)
1.  Volet Actions
2.  Champs Filtrer
3.  Bouton pour les tâches non planifiées
4.  Nœud de période
5.  Opération kanban
6.  Barre de capacité
7.  Échelle de temps

### <a name="view-the-time-scale"></a>Afficher l’échelle de temps

La carte est divisée en périodes, chacune étant représentée par un nœud (4). Les nœuds de période sont répertoriés sur l’axe vertical, et l’axe horizontal représente un échelle de temps (7) qui indique la durée de la période. Une période a une durée d’un jour ou d’une semaine. La durée de la période est déterminée par la configuration de la cellule de travail sélectionnée pour la carte de programme du kanban (2). Pour chaque nœud de période, la carte de programme du kanban indique le nombre de tâches de kanban planifiées qui sont chargées pour la période. Le débit maximal pour la période est également indiqué. Si le débit planifié dépasse le débit maximal, la période est considérée comme surchargée, et un symbole d’avertissement rouge s’affiche. Une tâche de kanban planifiée apparaît dans une période qui a des heures de début et de fin planifiées (5). La durée de la tâche est égale à la durée d’activité. Des tâches de kanban se chevauchent dans une période si leurs durées d’activité dépassent la durée de tâche de la cellule de travail.

### <a name="view-job-status"></a>Afficher le statut des tâches

Des informations supplémentaires sur une tâche de kanban sont disponibles dans l’info-bulle qui s’affiche lorsque vous positionnez le pointeur sur la tâche. Un symbole fournit des informations sur le statut de la tâche. Par exemple, un symbole d’horloge indique que la tâche de kanban est en retard.

### <a name="use-colors-to-view-the-kanban-schedule-board"></a>Utiliser des couleurs pour afficher la carte de programme du kanban

Pour améliorer la vue d’ensemble fournie par la carte de programme du kanban, vous pouvez utiliser des couleurs pour distinguer les tâches de kanban. La couleur d’une tâche de kanban est configurée dans le groupe de calendriers de production au plus juste, dans lequel vous pouvez regrouper les produits qui doivent être fabriqués dans le même ordre. Le bouton **Utiliser les couleurs de thèmes** dans l’onglet **Tableau** du volet Actions permet de basculer entre les couleurs de thème de l’application et les couleurs configurées dans le groupe de calendriers de production au plus juste. Pour chaque période, une barre de capacité (6) indique le nombre d’heures disponibles pour la période qui ont été chargées avec les tâches de kanban. Si la période est surchargée, la barre de capacité apparaît plus épaisse et en rouge. Toutes ces fonctions sont disponibles sous l’onglet **Tableau** du volet Actions (1) en haut de la page **Carte de programme du kanban**.

## <a name="plan-unplanned-jobs"></a>Planifier des tâches non planifiées
Vous pouvez planifier des tâches de kanban non planifiées dans la boîte de dialogue **Planifier des tâches non planifiées**. Pour ouvrir cette boîte de dialogue, cliquez sur le bouton **Tâches non planifiées** qui affiche le nombre actuel de tâches non planifiées. Sinon, cliquez sur **Planifier des tâches non planifiées** sous l’onglet **Tableau** du volet Actions. La boîte de dialogue affiche la liste des tâches de kanban non planifiées pour la cellule de travail. Vous pouvez utiliser le champ **Filtrer** pour filtrer tous les champs de la grille. Par exemple, vous pouvez filtrer les tâches de kanban pour un produit spécifique. Après avoir filtré la liste des tâches que vous souhaitez planifier, sélectionnez-les dans la liste, puis cliquez sur **OK**. Pour utiliser la planification automatique pour planifier les tâches, définissez l’option **Planification automatique** sur **Oui**. Dans ce cas, les tâches sont planifiées dans une période en fonction de leur date d’échéance. Vous pouvez aussi planifier les tâches par période. Sélectionnez simplement une période dans le champ **Période**. L’illustration suivante présente un exemple de la boîte de dialogue **Planifier des tâches non planifiées**. 

![Boîte de dialogue Planifier des tâches non planifiées](./media/plan-unplanned-jobs-1024x564.png)

## <a name="sequence-kanban-jobs-within-the-same-period"></a>Définir l’ordre des tâches de kanban dans la même période
Vous pouvez modifier l’ordre d’une ou de plusieurs tâches sélectionnées dans une période. Cette fonction peut être utile si vous souhaitez définir la priorité des tâches dans la période. Vous pouvez également définir l’ordre des tâches qui ont les mêmes attributs de produit, pour optimiser l’exécution des tâches. Vous pouvez modifier l’ordre par le biais d’une opération de glisser-déplacer, ou à l’aide des options de menu **En arrière** et **En avant** dans l’onglet **Tableau** du volet Actions.

## <a name="reassign-kanban-jobs-across-periods"></a>Réaffecter des tâches de kanban sur différentes périodes
Les tâches peuvent être réaffectées d’une période à une autre. Cette fonction peut être utile si une période est surchargée et vous souhaitez équilibrer la charge sur les périodes qui ont de la capacité disponible. Vous pouvez réaffecter des tâches par le biais d’une opération de glisser-déplacer, ou à l’aide des options de menu **Période précédente** et **Période suivante** dans l’onglet **Tableau** du volet Actions.

## <a name="open-the-kanban-schedule-board"></a>Ouvrir la carte de programme du kanban
Vous pouvez ouvrir la carte de programme du kanban à l’aide de l’option de menu disponible sur les pages suivantes :

-   Page **Zone de production**
-   Page **Planification des tâches de kanban**
-   Page **Visualisation du flux de production**


## <a name="additional-resources"></a>Ressources supplémentaires

[Planification des tâches de kanban pour Lean manufacturing](lean-manufacturing-kanban-job-scheduling.md)



[!INCLUDE[footer-include](../../includes/footer-banner.md)]