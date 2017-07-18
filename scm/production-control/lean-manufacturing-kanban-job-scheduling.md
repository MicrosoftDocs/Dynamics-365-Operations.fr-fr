---
title: "Planification des tâches de kanban pour lean manufacturing"
description: "Cet article fournit des informations sur le contrôle visuel de la planification des tâches de kanban et différentes manières de planifier des tâches de kanban."
author: YuyuScheller
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: KanbanBoardScheduleJobForward, KanbanBoardShowJobs, KanbanJobSchedulingListPage
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 52961
ms.assetid: fe3b4822-6140-4b02-bebb-1fc17be2bce8
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: conradv
ms.search.validFrom: 2016-02-28T00:00:00.000Z
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: 27db57170ccc23c2ea18a49c1a3e5950c870fa13
ms.contentlocale: fr-fr
ms.lasthandoff: 05/25/2017

---

# <a name="kanban-job-scheduling-for-lean-manufacturing"></a>Planification des tâches de kanban pour lean manufacturing

[!include[banner](../includes/banner.md)]


Cet article fournit des informations sur le contrôle visuel de la planification des tâches de kanban et différentes manières de planifier des tâches de kanban.  

La page **Planification de tâches de kanban** fournit un contrôle visuel des programmes des cellules de travail lean manufacturing. Elle donne une vue d'ensemble de toutes les tâches de kanban et fournit plusieurs capacités de filtrage. À partir de cette page, vous pouvez accéder à toutes les autres pages associées à la configuration et à l'exécution de kanban.

## <a name="automatic-scheduling-of-kanban-jobs"></a>Planification automatique des tâches de kanban
La planification peut être déclenchée automatiquement si vous définissez le paramètre **Quantité de planification automatique** sur la règle de kanban. Si vous définissez **Quantité de planification automatique** à **1**, chaque tâche de kanban est planifiée immédiatement lors de sa création. Le résultat est une série d'opérations « premier tiré, premier servi ». Si vous définissez le paramètre **Quantité de planification automatique** à une valeur supérieure à 1, les tâches de kanban sont regroupées avant d'être planifiées. 

Ce concept active la réduction des tailles de kanban à un seuil inférieur aux tailles économiques réelles de traitements par lots. Par exemple, la taille économique de traitement par lots pour un article spécifique (ou une famille d'articles) est 30. Au lieu de créer des kanbans qui utilisent la quantité de produit, 30, vous pouvez configurer la règle de kanban de sorte qu'elle ait une quantité de produits de 10 et une valeur de **Quantité de planification automatique** **3**. Bien que la planification automatique planifie les tâches de kanban pour la cellule de travail uniquement si trois tâches non prévues existent, il est totalement transparent pour le planificateur et le superviseur d'atelier que deux tâches non prévues sont peut-être en attente d'exécution. Le planificateur ou le responsable d'atelier peut ensuite faire passer ces deux tâches en production en les planifiant manuellement ou en créant des kanbans supplémentaires.

## <a name="manual-scheduling"></a>Planification manuelle
Pour la planification manuelle, Microsoft Dynamics AX 2012 a présenté le tableau de planification de kanban. La planification manuelle peut être combinée avec la planification automatique. Le tableau de planification de kanban vous permet de planifier et de déprogrammer des tâches, de les déplacer dans un ordre spécifique, ou de les faire passer d'une période à une autre. Les tâches basées sur une règle de kanban où la valeur **Planification automatique** est supérieure à **0** peuvent être manuellement déprogrammées. Toutefois, ces tâches sont planifiées de nouveau lorsque l'événement de planification automatique suivant se produit (c'est-à-dire, lorsqu'un kanban est créé). Les options suivantes sont disponibles pour la planification manuelle :

-   **Planifier** planifie les tâches sélectionnées en fonction de leur date d'échéance. (Cette option est semblable à la planification automatique.)
-   **Planifier en avant à partir de la date** tente de planifier les tâches sélectionnées en fonction de leur date d'échéance mais contraint le résultat en utilisant la première date de début spécifiée.
-   **En arrière** décale les tâches planifiées sélectionnées en arrière dans la séquence au sein de la période.
-   **En avant** décale les tâches planifiées sélectionnées en avant dans la séquence au sein de la période.
-   **Période précédente** déplace les tâches planifiées sélectionnées vers le début ou la fin de la période précédente.
-   **Période suivante** déplace les tâches planifiées sélectionnées vers le début ou la fin de la période suivante.
-   **Planifier** &gt; **Rétablir le statut de la tâche** permet de déprogrammer une tâche planifiée.

## <a name="lean-scheduling-groups"></a>Groupes de calendriers de production au plus juste
Chaque couleur représente un groupe de calendriers de production au plus juste. Les groupes de calendriers de production au plus juste peuvent être librement définis comme des groupes génériques ou des groupes appartenant à une cellule de travail unique. Les articles et les dimensions peuvent être affectées librement aux groupes de calendriers de production. Par exemple, dans une cellule Peinture, un groupe de calendriers peut représenter une couleur du produit. Dans un travail dépendant d'exigences spécifiques en matière d'outillage, les articles peuvent être regroupés par exigence d'outillage, et une cellule de travail d'emballage peut regrouper les articles par modèle d'emballage. L'utilisation de couleurs pour les groupes de calendriers de production au plus juste est facultative mais recommandée. Elle améliore la visibilité dans le statut du plan. Par exemple, il est très facile de voir quelles couleurs sont produites un jour donné, et vous pouvez voir d'un coup d'œil comment ce travail peut être optimisé.

## <a name="work-cell-capacity-and-period-capacity"></a>Capacité de la cellule de travail et capacité de la période
La capacité d'une cellule de travail lean manufacturing est toujours une capacité simultanée. En d'autres termes, plusieurs tâches peuvent être actives simultanément dans une cellule de travail. La capacité peut être suivie dans deux modes : débit et heures.

### <a name="throughput"></a>Débit

La capacité d'une cellule de travail est définie par la quantité moyenne de débit d'une période de référence (journée de travail, semaine ou mois standard). La capacité réelle par jour ou par semaine est ensuite calculée en fonction des temps de travail du calendrier affecté à la cellule de travail en question. La capacité qui est chargée par tâche correspond à la quantité de la tâche, ajustée par le taux de débit de l'article dans la cellule de travail.

### <a name="hours"></a>Heures

La capacité disponible par jour ou par semaine est définie par le calendrier affecté à la cellule de travail. La capacité qui est chargée par tâche correspond à la durée de cycle de l'activité, ajustée par la quantité (quantité de l'activité par défaut par rapport à la quantité réelle de la tâche) et le taux de débit de l'article dans la cellule de travail.

#### <a name="period-capacity-factbox"></a>Récapitulatif de la capacité de la période

La page de liste **Planification de tâches de kanban** contient un Récapitulatif qui affiche la capacité de période disponible et réservée pour la cellule de travail sélectionnée. En fonction des périodes de planification sélectionnées dans le modèle de flux de production, les périodes indiquent des jours ou des semaines.

<a name="see-also"></a>Voir également :
--------




