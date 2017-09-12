--- 
title: "Créer un programme pour un site"
description: "Cette procédure décrit comment planifier les ordres de fabrication qui n'ont pas encore commencé pour un site."
author: YuyuScheller
manager: AnnBe
ms.date: 06/10/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Operations
ms.search.region: Global
ms.author: yuyus
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: 775428bf84a752c03c492e764fa9ed576ab64fb8
ms.contentlocale: fr-fr
ms.lasthandoff: 08/29/2017

---
# <a name="create-a-schedule-for-a-site"></a><span data-ttu-id="ef540-103">Créer un programme pour un site</span><span class="sxs-lookup"><span data-stu-id="ef540-103">Create a schedule for a site</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="ef540-104">Cette procédure décrit comment planifier les ordres de fabrication qui n'ont pas encore commencé pour un site.</span><span class="sxs-lookup"><span data-stu-id="ef540-104">This procedure shows how to schedule production orders that are not yet started for a site.</span></span>  <span data-ttu-id="ef540-105">Les données fictives de la société USMF sont utilisées pour réaliser cette procédure.</span><span class="sxs-lookup"><span data-stu-id="ef540-105">The demo data company USMF is used to complete this procedure.</span></span>


## <a name="identify-production-orders-that-are-not-started"></a><span data-ttu-id="ef540-106">Identifier les ordres de fabrication qui n'ont pas encore commencé</span><span class="sxs-lookup"><span data-stu-id="ef540-106">Identify production orders that are not started</span></span>
1. <span data-ttu-id="ef540-107">Accédez à Contrôle de la production > Ordres de fabrication > Tous les ordres de fabrication.</span><span class="sxs-lookup"><span data-stu-id="ef540-107">Go to Production control > Production orders > All production orders.</span></span>
2. <span data-ttu-id="ef540-108">Utilisez le Filtre rapide pour rechercher les enregistrements.</span><span class="sxs-lookup"><span data-stu-id="ef540-108">Use the Quick Filter to find records.</span></span> <span data-ttu-id="ef540-109">Par exemple, filtrez sur le champ Site avec une valeur de « 1 ».</span><span class="sxs-lookup"><span data-stu-id="ef540-109">For example, filter on the Site field with a value of '1'.</span></span>
    * <span data-ttu-id="ef540-110">1 représente un site dans USMF.</span><span class="sxs-lookup"><span data-stu-id="ef540-110">1 represents a site in USMF.</span></span> <span data-ttu-id="ef540-111">Si vous n'utilisez pas USMF, sélectionnez un site à partir de votre propre société.</span><span class="sxs-lookup"><span data-stu-id="ef540-111">If you are not using USMF, select a site from your own company.</span></span>  
3. <span data-ttu-id="ef540-112">Ouvrez le filtre de colonne Statut.</span><span class="sxs-lookup"><span data-stu-id="ef540-112">Open the Status column filter.</span></span>
4. <span data-ttu-id="ef540-113">Appliquez un filtre sur le champ « Statut » avec une valeur « Planifié », à l'aide de l'opérateur de filtre « est exactement ».</span><span class="sxs-lookup"><span data-stu-id="ef540-113">Apply a filter on the "Status" field, with a value of "Scheduled", using the "is exactly" filter operator.</span></span>

## <a name="create-a-schedule"></a><span data-ttu-id="ef540-114">Créer un programme</span><span class="sxs-lookup"><span data-stu-id="ef540-114">Create a schedule</span></span>
1. <span data-ttu-id="ef540-115">Dans la liste, cochez ou décochez toutes les lignes.</span><span class="sxs-lookup"><span data-stu-id="ef540-115">In the list, mark or unmark all rows.</span></span>
2. <span data-ttu-id="ef540-116">Dans le volet Actions, cliquez sur Planification.</span><span class="sxs-lookup"><span data-stu-id="ef540-116">On the Action Pane, click Schedule.</span></span>
3. <span data-ttu-id="ef540-117">Cliquez sur Planifier les tâches.</span><span class="sxs-lookup"><span data-stu-id="ef540-117">Click Schedule jobs.</span></span>
4. <span data-ttu-id="ef540-118">Dans le champ Direction de la planification, sélectionnez « En arrière à partir de la date de livraison ».</span><span class="sxs-lookup"><span data-stu-id="ef540-118">In the Scheduling direction field, select 'Backward from delivery date'.</span></span>
5. <span data-ttu-id="ef540-119">Dans le champ Capacité finie, sélectionnez Non.</span><span class="sxs-lookup"><span data-stu-id="ef540-119">Select No in the Finite capacity field.</span></span>
6. <span data-ttu-id="ef540-120">Dans le champ Matières limitées, sélectionnez Non.</span><span class="sxs-lookup"><span data-stu-id="ef540-120">Select No in the Finite material field.</span></span>
7. <span data-ttu-id="ef540-121">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="ef540-121">Click OK.</span></span>
    * <span data-ttu-id="ef540-122">Cette opération peut prendre du temps.</span><span class="sxs-lookup"><span data-stu-id="ef540-122">This may take a while.</span></span>  

## <a name="view-the-result-of-scheduled-production-orders"></a><span data-ttu-id="ef540-123">Afficher le résultat des ordres de fabrication planifiés</span><span class="sxs-lookup"><span data-stu-id="ef540-123">View the result of scheduled production orders</span></span>
1. <span data-ttu-id="ef540-124">Dans la liste, marquez la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="ef540-124">In the list, mark the selected row.</span></span>
    * <span data-ttu-id="ef540-125">Vous pouvez marquer n'importe quelle ligne.</span><span class="sxs-lookup"><span data-stu-id="ef540-125">You can mark any row.</span></span>  
2. <span data-ttu-id="ef540-126">Cliquez sur Ordre de fabrication dans le volet Actions.</span><span class="sxs-lookup"><span data-stu-id="ef540-126">On the Action Pane, click Production order.</span></span>
3. <span data-ttu-id="ef540-127">Cliquez sur Toutes les tâches.</span><span class="sxs-lookup"><span data-stu-id="ef540-127">Click All jobs.</span></span>
    * <span data-ttu-id="ef540-128">Dans cette page, vous pouvez afficher la liste de tâches.</span><span class="sxs-lookup"><span data-stu-id="ef540-128">On this page, you can see the list of jobs.</span></span> <span data-ttu-id="ef540-129">Sous l'onglet Planification, vous pouvez afficher la date de début et de fin d'une tâche.</span><span class="sxs-lookup"><span data-stu-id="ef540-129">On the Scheduling tab, you can see the Start date and End date for a job.</span></span>  
4. <span data-ttu-id="ef540-130">Cliquez sur Matériaux.</span><span class="sxs-lookup"><span data-stu-id="ef540-130">Click Materials.</span></span>
    * <span data-ttu-id="ef540-131">Dans cette page, vous pouvez voir la consommation de matériaux estimée pour les opérations sur l'ordre de fabrication et le stock disponible actuel.</span><span class="sxs-lookup"><span data-stu-id="ef540-131">On this page, you can see the estimated material consumption for the operations on the production order and the current available inventory.</span></span>  


