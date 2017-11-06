--- 
title: "Définir des capacités de ressources"
description: "Les capacités de ressource décrivent ce que les ressources opérationnelles peuvent effectuer."
author: sorenva
manager: AnnBe
ms.date: 10/27/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: sorenand
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 99c230c0e6a580f77d863b6f0be298615966c479
ms.contentlocale: fr-fr
ms.lasthandoff: 11/06/2017

---
# <a name="define-resource-capabilities"></a><span data-ttu-id="0ec98-103">Définir des capacités de ressources</span><span class="sxs-lookup"><span data-stu-id="0ec98-103">Define resource capabilities</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="0ec98-104">Les capacités de ressource décrivent ce que les ressources opérationnelles peuvent effectuer.</span><span class="sxs-lookup"><span data-stu-id="0ec98-104">Resource capabilities describe what operations resources can do.</span></span> <span data-ttu-id="0ec98-105">Lors de la planification, les exigences de chaque tâche et opération sont mises en correspondance avec les capacités des ressources disponibles.</span><span class="sxs-lookup"><span data-stu-id="0ec98-105">During scheduling, the requirements of each job and operation are matched against the capabilities of the available resources.</span></span> <span data-ttu-id="0ec98-106">Ce guide des tâches vous aidera à créer une capacité et à l'affecter à une ressource.</span><span class="sxs-lookup"><span data-stu-id="0ec98-106">This task guide will help you create a resource capability and assign it to a resource.</span></span> <span data-ttu-id="0ec98-107">Les données fictives utilisées pour créer cette tâche correspondent à la société USMF.</span><span class="sxs-lookup"><span data-stu-id="0ec98-107">The demo data company used to create this task is USMF.</span></span>


## <a name="create-a-resource-capability"></a><span data-ttu-id="0ec98-108">Créer une capacité de ressource</span><span class="sxs-lookup"><span data-stu-id="0ec98-108">Create a resource capability</span></span>
1. <span data-ttu-id="0ec98-109">Allez dans Capacités de ressources.</span><span class="sxs-lookup"><span data-stu-id="0ec98-109">Go to Resource capabilities.</span></span>
2. <span data-ttu-id="0ec98-110">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="0ec98-110">Click New.</span></span>
3. <span data-ttu-id="0ec98-111">Dans le champ Capacité, entrez l'ID de la capacité de la ressource.</span><span class="sxs-lookup"><span data-stu-id="0ec98-111">In the Capability field, type the ID of the resource capability.</span></span>
    * <span data-ttu-id="0ec98-112">Pour une opération donnée, vous devez utiliser l'ID de capacité pour spécifier que les ressources doivent avoir cette possibilité d'exécuter l'opération.</span><span class="sxs-lookup"><span data-stu-id="0ec98-112">For a given operation, you use the capability ID to specify that resources must have this capability to perform the operation.</span></span>  
4. <span data-ttu-id="0ec98-113">Dans le champ Description, entrez la description de la capacité.</span><span class="sxs-lookup"><span data-stu-id="0ec98-113">In the Description field, enter a description of the capability.</span></span>

## <a name="assign-capability-to-a-resource"></a><span data-ttu-id="0ec98-114">Affecter la capacité à une ressource</span><span class="sxs-lookup"><span data-stu-id="0ec98-114">Assign capability to a resource</span></span>
1. <span data-ttu-id="0ec98-115">Cliquez sur Ajouter.</span><span class="sxs-lookup"><span data-stu-id="0ec98-115">Click Add.</span></span>
2. <span data-ttu-id="0ec98-116">Dans le champ Ressource, entrez l'ID de la capacité de la ressource.</span><span class="sxs-lookup"><span data-stu-id="0ec98-116">In the Resource field, type the ID of the resource.</span></span>
    * <span data-ttu-id="0ec98-117">Une capacité de la ressource peut être affectée à une ou plusieurs ressources.</span><span class="sxs-lookup"><span data-stu-id="0ec98-117">A resource capability can be assigned to one or more resources.</span></span>  
3. <span data-ttu-id="0ec98-118">Dans le champ Expiration, entrer une date et une heure.</span><span class="sxs-lookup"><span data-stu-id="0ec98-118">In the Expiration field, enter a date.</span></span>
    * <span data-ttu-id="0ec98-119">Vous pouvez utiliser ce champ pour spécifier qu'une ressource a la capacité pour une durée limitée uniquement.</span><span class="sxs-lookup"><span data-stu-id="0ec98-119">You can use this field to specify that a resource has the capability for only a limited time.</span></span>  
4. <span data-ttu-id="0ec98-120">Dans le champ Priorité, entrer un numéro.</span><span class="sxs-lookup"><span data-stu-id="0ec98-120">In the Priority field, enter a number.</span></span>
    * <span data-ttu-id="0ec98-121">Lorsque vous planifiez des tâches et des opérations, vous pouvez spécifier si les ressources doivent être sélectionnées par priorité ou non.</span><span class="sxs-lookup"><span data-stu-id="0ec98-121">When you schedule jobs and operations, you can specify whether to select resources by priority.</span></span> <span data-ttu-id="0ec98-122">Si vous choisissez de le faire et que plusieurs ressources peuvent exécuter la tâche ou l'opération pour la date demandée, la ressource ayant la priorité la plus faible par rapport à la capacité nécessaire est sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="0ec98-122">If you choose to do this, and more than one resource can perform the job or operation by the requested date, the resource that has the lowest priority with respect to the required capability is selected.</span></span>  
5. <span data-ttu-id="0ec98-123">Dans le champ Niveau, entrez un nombre.</span><span class="sxs-lookup"><span data-stu-id="0ec98-123">In the Level field, enter a number.</span></span>
    * <span data-ttu-id="0ec98-124">Si vous spécifiez qu'une tâche ou une opération nécessite une capacité particulière, vous pouvez également spécifier le niveau minimal requis.</span><span class="sxs-lookup"><span data-stu-id="0ec98-124">When you specify that a job or operation requires a particular capability, you can also specify the minimum level that is required.</span></span> <span data-ttu-id="0ec98-125">Utilisez le niveau de la capacité pour différencier les ressources capables d'effectuer la même tâche, mais à des vitesses, des forces, des tailles, etc. différentes.</span><span class="sxs-lookup"><span data-stu-id="0ec98-125">Use the capability level to differentiate resources that can perform the same job, but at different speeds, strengths, sizes, and so on.</span></span>  


