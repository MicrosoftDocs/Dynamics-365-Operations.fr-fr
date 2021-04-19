---
title: Préparer une tâche de kanban de processus lorsque les matières sont disponibles pour la cellule de travail
description: Cette tâche se concentre sur la préparation d’une tâche de kanban de processus lorsque toutes les matières ne sont pas disponibles pour la cellule de travail.
author: johanhoffmann
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: KanbanBoardWorkCell
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 460d55a8c4b8a8401db7abc43721cf0d114c27c5
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5807822"
---
# <a name="prepare-a-process-kanban-job-when-materials-are-available-for-the-work-cell"></a><span data-ttu-id="a416c-103">Préparer une tâche de kanban de processus lorsque les matières sont disponibles pour la cellule de travail</span><span class="sxs-lookup"><span data-stu-id="a416c-103">Prepare a process kanban job when materials are available for the work cell</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="a416c-104">Cette tâche se concentre sur la préparation d’une tâche de kanban de processus lorsque toutes les matières ne sont pas disponibles pour la cellule de travail.</span><span class="sxs-lookup"><span data-stu-id="a416c-104">This task focuses on preparing a process kanban job when all materials are available for the work cell.</span></span> <span data-ttu-id="a416c-105">Les données fictives utilisées pour créer cette tâche correspondent à la société USMF.</span><span class="sxs-lookup"><span data-stu-id="a416c-105">The demo data company used to create this task is USMF.</span></span> <span data-ttu-id="a416c-106">Cette tâche est destinée à l’opérateur.</span><span class="sxs-lookup"><span data-stu-id="a416c-106">This task is intended for the machine operator.</span></span>

1. <span data-ttu-id="a416c-107">Allez dans le tableau kanban pour les opérations de traitement.</span><span class="sxs-lookup"><span data-stu-id="a416c-107">Go to Kanban board for process jobs.</span></span>
2. <span data-ttu-id="a416c-108">Dans le champ Cellule de travail, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="a416c-108">In the Work cell field, click the drop-down button to open the lookup.</span></span>
3. <span data-ttu-id="a416c-109">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="a416c-109">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="a416c-110">Sélectionnez la cellule de travail 1250 et cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="a416c-110">Select work cell 1250 and click OK.</span></span>  
4. <span data-ttu-id="a416c-111">Sélectionnez la ligne 4 dans la liste.</span><span class="sxs-lookup"><span data-stu-id="a416c-111">In the list, select row 4.</span></span>
    * <span data-ttu-id="a416c-112">Dans la société fictive de démonstration, le kanban 000329 de la ligne 4 est la première tâche qui n’est pas encore terminée.</span><span class="sxs-lookup"><span data-stu-id="a416c-112">In the clean demo company, Kanban 000329 in row 4 is the first job that is not completed yet.</span></span>  
5. <span data-ttu-id="a416c-113">Activez ou désactivez l’extension de la section Prélèvements.</span><span class="sxs-lookup"><span data-stu-id="a416c-113">Toggle the expansion of the Picking list section.</span></span>
    * <span data-ttu-id="a416c-114">Vérifiez que le statut d’approvisionnement est disponible pour tous les articles des prélèvements.</span><span class="sxs-lookup"><span data-stu-id="a416c-114">Verify that the supply status is available for all items in the picking list.</span></span>  
    * <span data-ttu-id="a416c-115">Si plusieurs tâches sont activées, les prélèvements indique la somme de tous les articles nécessaires pour les tâches sélectionnées.</span><span class="sxs-lookup"><span data-stu-id="a416c-115">If multiple jobs are selected, the picking list will show the sum of all items needed for the selected jobs.</span></span>  
6. <span data-ttu-id="a416c-116">Cliquez sur Préparer.</span><span class="sxs-lookup"><span data-stu-id="a416c-116">Click Prepare.</span></span>
    * <span data-ttu-id="a416c-117">Le processus de préparation est désormais terminé.</span><span class="sxs-lookup"><span data-stu-id="a416c-117">The preparation process is now completed.</span></span> <span data-ttu-id="a416c-118">La case à cocher activée pour toutes les lignes des prélèvements indique que le statut d’approvisionnement est prélevé.</span><span class="sxs-lookup"><span data-stu-id="a416c-118">The selected check box for all rows in the picking list indicates that the supply status is picked.</span></span>  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]