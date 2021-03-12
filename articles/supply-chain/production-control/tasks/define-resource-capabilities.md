---
title: Définir des capacités de ressources
description: Les capacités de ressource décrivent ce que les ressources opérationnelles peuvent effectuer.
author: sorenva
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WrkCtrCapability
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: sorenand
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 93b30cbe660d224f0a92f4e412d2b1ba33af3f9b
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4977836"
---
# <a name="define-resource-capabilities"></a><span data-ttu-id="2eda7-103">Définir des capacités de ressources</span><span class="sxs-lookup"><span data-stu-id="2eda7-103">Define resource capabilities</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="2eda7-104">Les capacités de ressource décrivent ce que les ressources opérationnelles peuvent effectuer.</span><span class="sxs-lookup"><span data-stu-id="2eda7-104">Resource capabilities describe what operations resources can do.</span></span> <span data-ttu-id="2eda7-105">Lors de la planification, les exigences de chaque tâche et opération sont mises en correspondance avec les capacités des ressources disponibles.</span><span class="sxs-lookup"><span data-stu-id="2eda7-105">During scheduling, the requirements of each job and operation are matched against the capabilities of the available resources.</span></span> <span data-ttu-id="2eda7-106">Ce guide des tâches vous aidera à créer une capacité et à l'affecter à une ressource.</span><span class="sxs-lookup"><span data-stu-id="2eda7-106">This task guide will help you create a resource capability and assign it to a resource.</span></span> <span data-ttu-id="2eda7-107">Les données fictives utilisées pour créer cette tâche correspondent à la société USMF.</span><span class="sxs-lookup"><span data-stu-id="2eda7-107">The demo data company used to create this task is USMF.</span></span>


## <a name="create-a-resource-capability"></a><span data-ttu-id="2eda7-108">Créer une capacité de ressource</span><span class="sxs-lookup"><span data-stu-id="2eda7-108">Create a resource capability</span></span>
1. <span data-ttu-id="2eda7-109">Allez dans Capacités de ressources.</span><span class="sxs-lookup"><span data-stu-id="2eda7-109">Go to Resource capabilities.</span></span>
2. <span data-ttu-id="2eda7-110">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="2eda7-110">Click New.</span></span>
3. <span data-ttu-id="2eda7-111">Dans le champ Capacité, entrez l'ID de la capacité de la ressource.</span><span class="sxs-lookup"><span data-stu-id="2eda7-111">In the Capability field, type the ID of the resource capability.</span></span>
    * <span data-ttu-id="2eda7-112">Pour une opération donnée, vous devez utiliser l'ID de capacité pour spécifier que les ressources doivent avoir cette possibilité d'exécuter l'opération.</span><span class="sxs-lookup"><span data-stu-id="2eda7-112">For a given operation, you use the capability ID to specify that resources must have this capability to perform the operation.</span></span>  
4. <span data-ttu-id="2eda7-113">Dans le champ Description, entrez la description de la capacité.</span><span class="sxs-lookup"><span data-stu-id="2eda7-113">In the Description field, enter a description of the capability.</span></span>

## <a name="assign-capability-to-a-resource"></a><span data-ttu-id="2eda7-114">Affecter la capacité à une ressource</span><span class="sxs-lookup"><span data-stu-id="2eda7-114">Assign capability to a resource</span></span>
1. <span data-ttu-id="2eda7-115">Cliquez sur Ajouter.</span><span class="sxs-lookup"><span data-stu-id="2eda7-115">Click Add.</span></span>
2. <span data-ttu-id="2eda7-116">Dans le champ Ressource, entrez l'ID de la capacité de la ressource.</span><span class="sxs-lookup"><span data-stu-id="2eda7-116">In the Resource field, type the ID of the resource.</span></span>
    * <span data-ttu-id="2eda7-117">Une capacité de la ressource peut être affectée à une ou plusieurs ressources.</span><span class="sxs-lookup"><span data-stu-id="2eda7-117">A resource capability can be assigned to one or more resources.</span></span>  
3. <span data-ttu-id="2eda7-118">Dans le champ Expiration, entrer une date et une heure.</span><span class="sxs-lookup"><span data-stu-id="2eda7-118">In the Expiration field, enter a date.</span></span>
    * <span data-ttu-id="2eda7-119">Vous pouvez utiliser ce champ pour spécifier qu'une ressource a la capacité pour une durée limitée uniquement.</span><span class="sxs-lookup"><span data-stu-id="2eda7-119">You can use this field to specify that a resource has the capability for only a limited time.</span></span>  
4. <span data-ttu-id="2eda7-120">Dans le champ Priorité, entrer un numéro.</span><span class="sxs-lookup"><span data-stu-id="2eda7-120">In the Priority field, enter a number.</span></span>
    * <span data-ttu-id="2eda7-121">Lorsque vous planifiez des tâches et des opérations, vous pouvez spécifier si les ressources doivent être sélectionnées par priorité ou non.</span><span class="sxs-lookup"><span data-stu-id="2eda7-121">When you schedule jobs and operations, you can specify whether to select resources by priority.</span></span> <span data-ttu-id="2eda7-122">Si vous choisissez de le faire et que plusieurs ressources peuvent exécuter la tâche ou l'opération pour la date demandée, la ressource ayant la priorité la plus faible par rapport à la capacité nécessaire est sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="2eda7-122">If you choose to do this, and more than one resource can perform the job or operation by the requested date, the resource that has the lowest priority with respect to the required capability is selected.</span></span>  
5. <span data-ttu-id="2eda7-123">Dans le champ Niveau, entrez un nombre.</span><span class="sxs-lookup"><span data-stu-id="2eda7-123">In the Level field, enter a number.</span></span>
    * <span data-ttu-id="2eda7-124">Si vous spécifiez qu'une tâche ou une opération nécessite une capacité particulière, vous pouvez également spécifier le niveau minimal requis.</span><span class="sxs-lookup"><span data-stu-id="2eda7-124">When you specify that a job or operation requires a particular capability, you can also specify the minimum level that is required.</span></span> <span data-ttu-id="2eda7-125">Utilisez le niveau de la capacité pour différencier les ressources capables d'effectuer la même tâche, mais à des vitesses, des forces, des tailles, etc. différentes.</span><span class="sxs-lookup"><span data-stu-id="2eda7-125">Use the capability level to differentiate resources that can perform the same job, but at different speeds, strengths, sizes, and so on.</span></span>  

