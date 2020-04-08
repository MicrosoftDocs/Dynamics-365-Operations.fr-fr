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
# <a name="prepare-a-process-kanban-job-when-materials-are-available-for-the-work-cell"></a><span data-ttu-id="b9886-103">Préparer une tâche de kanban de processus lorsque les matières sont disponibles pour la cellule de travail</span><span class="sxs-lookup"><span data-stu-id="b9886-103">Prepare a process kanban job when materials are available for the work cell</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="b9886-104">Cette tâche se concentre sur la préparation d'une tâche de kanban de processus lorsque toutes les matières ne sont pas disponibles pour la cellule de travail.</span><span class="sxs-lookup"><span data-stu-id="b9886-104">This task focuses on preparing a process kanban job when all materials are available for the work cell.</span></span> <span data-ttu-id="b9886-105">Les données fictives utilisées pour créer cette tâche correspondent à la société USMF.</span><span class="sxs-lookup"><span data-stu-id="b9886-105">The demo data company used to create this task is USMF.</span></span> <span data-ttu-id="b9886-106">Cette tâche est destinée à l'opérateur.</span><span class="sxs-lookup"><span data-stu-id="b9886-106">This task is intended for the machine operator.</span></span>

1. <span data-ttu-id="b9886-107">Allez dans le tableau kanban pour les opérations de traitement.</span><span class="sxs-lookup"><span data-stu-id="b9886-107">Go to Kanban board for process jobs.</span></span>
2. <span data-ttu-id="b9886-108">Dans le champ Cellule de travail, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="b9886-108">In the Work cell field, click the drop-down button to open the lookup.</span></span>
3. <span data-ttu-id="b9886-109">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="b9886-109">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="b9886-110">Sélectionnez la cellule de travail 1250 et cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="b9886-110">Select work cell 1250 and click OK.</span></span>  
4. <span data-ttu-id="b9886-111">Sélectionnez la ligne 4 dans la liste.</span><span class="sxs-lookup"><span data-stu-id="b9886-111">In the list, select row 4.</span></span>
    * <span data-ttu-id="b9886-112">Dans la société fictive de démonstration, le kanban 000329 de la ligne 4 est la première tâche qui n'est pas encore terminée.</span><span class="sxs-lookup"><span data-stu-id="b9886-112">In the clean demo company, Kanban 000329 in row 4 is the first job that is not completed yet.</span></span>  
5. <span data-ttu-id="b9886-113">Activez ou désactivez l'extension de la section Prélèvements.</span><span class="sxs-lookup"><span data-stu-id="b9886-113">Toggle the expansion of the Picking list section.</span></span>
    * <span data-ttu-id="b9886-114">Vérifiez que le statut d'approvisionnement est disponible pour tous les articles des prélèvements.</span><span class="sxs-lookup"><span data-stu-id="b9886-114">Verify that the supply status is available for all items in the picking list.</span></span>  
    * <span data-ttu-id="b9886-115">Si plusieurs tâches sont activées, les prélèvements indique la somme de tous les articles nécessaires pour les tâches sélectionnées.</span><span class="sxs-lookup"><span data-stu-id="b9886-115">If multiple jobs are selected, the picking list will show the sum of all items needed for the selected jobs.</span></span>  
6. <span data-ttu-id="b9886-116">Cliquez sur Préparer.</span><span class="sxs-lookup"><span data-stu-id="b9886-116">Click Prepare.</span></span>
    * <span data-ttu-id="b9886-117">Le processus de préparation est désormais terminé.</span><span class="sxs-lookup"><span data-stu-id="b9886-117">The preparation process is now completed.</span></span> <span data-ttu-id="b9886-118">La case à cocher activée pour toutes les lignes des prélèvements indique que le statut d'approvisionnement est prélevé.</span><span class="sxs-lookup"><span data-stu-id="b9886-118">The selected check box for all rows in the picking list indicates that the supply status is picked.</span></span>  

