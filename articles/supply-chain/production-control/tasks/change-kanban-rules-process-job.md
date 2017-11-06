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
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 7f8b2a67e03a64deae9d4bc9c7e3e714d134443c
ms.contentlocale: fr-fr
ms.lasthandoff: 11/06/2017

---
# <a name="change-kanban-rules-for-a-process-job"></a><span data-ttu-id="d80bf-103">Modifier les règles de kanban pour une tâche de traitement</span><span class="sxs-lookup"><span data-stu-id="d80bf-103">Change kanban rules for a process job</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="d80bf-104">Cette procédure traite de la modification de la règle de kanban utilisée pour un kanban donné.</span><span class="sxs-lookup"><span data-stu-id="d80bf-104">This procedure focuses on changing the used kanban rule for a given kanban.</span></span> <span data-ttu-id="d80bf-105">Cela est utile pour l'équilibrage de charge des ressources ou en cas de panne.</span><span class="sxs-lookup"><span data-stu-id="d80bf-105">This is useful to level load resources or in case of breakdown.</span></span> <span data-ttu-id="d80bf-106">Les données fictives utilisées pour créer cette procédure correspondent à la société USMF.</span><span class="sxs-lookup"><span data-stu-id="d80bf-106">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="d80bf-107">Cette procédure est destinée au planificateur, travaillant pour une société de lean manufacturing, responsable de la chaîne de valeur.</span><span class="sxs-lookup"><span data-stu-id="d80bf-107">This procedure is intended for the planner, working at a lean manufacturing company, responsible for the value stream.</span></span>


## <a name="copy-kanban-rule"></a><span data-ttu-id="d80bf-108">Copier une règle de kanban</span><span class="sxs-lookup"><span data-stu-id="d80bf-108">Copy kanban rule</span></span>
1. <span data-ttu-id="d80bf-109">Accédez aux règles de kanban.</span><span class="sxs-lookup"><span data-stu-id="d80bf-109">Go to Kanban rules.</span></span>
2. <span data-ttu-id="d80bf-110">Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="d80bf-110">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="d80bf-111">Sélectionnez la règle de kanban d'événement 000022 pour L0001.</span><span class="sxs-lookup"><span data-stu-id="d80bf-111">Select Event Kanban rule 000022 for L0001.</span></span>  
3. <span data-ttu-id="d80bf-112">Cliquez sur Dupliquer une règle de kanban.</span><span class="sxs-lookup"><span data-stu-id="d80bf-112">Click Duplicate kanban rule.</span></span>
4. <span data-ttu-id="d80bf-113">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="d80bf-113">Click OK.</span></span>

## <a name="change-kanban-rule"></a><span data-ttu-id="d80bf-114">Modifier une règle de kanban</span><span class="sxs-lookup"><span data-stu-id="d80bf-114">Change kanban rule</span></span>
1. <span data-ttu-id="d80bf-115">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="d80bf-115">Close the page.</span></span>
2. <span data-ttu-id="d80bf-116">Accédez à Planification de tâches de kanban.</span><span class="sxs-lookup"><span data-stu-id="d80bf-116">Go to Kanban job scheduling.</span></span>
3. <span data-ttu-id="d80bf-117">Dans la liste, marquez la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="d80bf-117">In the list, mark the selected row.</span></span>
    * <span data-ttu-id="d80bf-118">Sélectionnez la ligne avec le Kanban 000177.</span><span class="sxs-lookup"><span data-stu-id="d80bf-118">Select line with Kanban 000177.</span></span>  
4. <span data-ttu-id="d80bf-119">Cliquez sur Utiliser une autre règle de kanban.</span><span class="sxs-lookup"><span data-stu-id="d80bf-119">Click Use alternative kanban rule.</span></span>
5. <span data-ttu-id="d80bf-120">Cliquez sur Suivant.</span><span class="sxs-lookup"><span data-stu-id="d80bf-120">Click Next.</span></span>
6. <span data-ttu-id="d80bf-121">Dans le champ Règle de kanban, saisissez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="d80bf-121">In the Kanban rule field, enter or select a value.</span></span>
    * <span data-ttu-id="d80bf-122">Sélectionnez la règle de kanban créée précédemment.</span><span class="sxs-lookup"><span data-stu-id="d80bf-122">Select the kanban rule that was created earlier.</span></span> <span data-ttu-id="d80bf-123">Il s'agit de la règle de kanban avec le numéro le plus élevé.</span><span class="sxs-lookup"><span data-stu-id="d80bf-123">This is the kanban rule with the highest number.</span></span>  
7. <span data-ttu-id="d80bf-124">Cliquez sur Terminer.</span><span class="sxs-lookup"><span data-stu-id="d80bf-124">Click Finish.</span></span>
    * <span data-ttu-id="d80bf-125">Actuellement, la tâche de kanban utilise une autre règle de kanban.</span><span class="sxs-lookup"><span data-stu-id="d80bf-125">Now the kanban job is using an another kanban rule.</span></span> <span data-ttu-id="d80bf-126">Cela peut être utile pour l'équilibrage de charge des cellules de travail.</span><span class="sxs-lookup"><span data-stu-id="d80bf-126">This can be useful to level load work cells.</span></span>  


