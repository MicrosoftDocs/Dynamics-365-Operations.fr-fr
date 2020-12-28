---
title: Créer un programme pour un site
description: Cette procédure décrit comment planifier les ordres de fabrication qui n'ont pas encore commencé pour un site.
author: ShylaThompson
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ProdTableListPage, ProdSchedule, ProdRouteJob
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: d9059080fcd77a5317ce4226de6aad38b0066500
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4427907"
---
# <a name="create-a-schedule-for-a-site"></a><span data-ttu-id="c8e92-103">Créer un programme pour un site</span><span class="sxs-lookup"><span data-stu-id="c8e92-103">Create a schedule for a site</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="c8e92-104">Cette procédure décrit comment planifier les ordres de fabrication qui n'ont pas encore commencé pour un site.</span><span class="sxs-lookup"><span data-stu-id="c8e92-104">This procedure shows how to schedule production orders that are not yet started for a site.</span></span>  <span data-ttu-id="c8e92-105">Les données fictives de la société USMF sont utilisées pour réaliser cette procédure.</span><span class="sxs-lookup"><span data-stu-id="c8e92-105">The demo data company USMF is used to complete this procedure.</span></span>


## <a name="identify-production-orders-that-are-not-started"></a><span data-ttu-id="c8e92-106">Identifier les ordres de fabrication qui n'ont pas encore commencé</span><span class="sxs-lookup"><span data-stu-id="c8e92-106">Identify production orders that are not started</span></span>
1. <span data-ttu-id="c8e92-107">Accédez à Contrôle de la production > Ordres de fabrication > Tous les ordres de fabrication.</span><span class="sxs-lookup"><span data-stu-id="c8e92-107">Go to Production control > Production orders > All production orders.</span></span>
2. <span data-ttu-id="c8e92-108">Utilisez le Filtre rapide pour rechercher les enregistrements.</span><span class="sxs-lookup"><span data-stu-id="c8e92-108">Use the Quick Filter to find records.</span></span> <span data-ttu-id="c8e92-109">Par exemple, filtrez sur le champ Site avec une valeur de « 1 ».</span><span class="sxs-lookup"><span data-stu-id="c8e92-109">For example, filter on the Site field with a value of '1'.</span></span>
    * <span data-ttu-id="c8e92-110">1 représente un site dans USMF.</span><span class="sxs-lookup"><span data-stu-id="c8e92-110">1 represents a site in USMF.</span></span> <span data-ttu-id="c8e92-111">Si vous n'utilisez pas USMF, sélectionnez un site à partir de votre propre société.</span><span class="sxs-lookup"><span data-stu-id="c8e92-111">If you are not using USMF, select a site from your own company.</span></span>  
3. <span data-ttu-id="c8e92-112">Ouvrez le filtre de colonne Statut.</span><span class="sxs-lookup"><span data-stu-id="c8e92-112">Open the Status column filter.</span></span>
4. <span data-ttu-id="c8e92-113">Appliquez un filtre sur le champ « Statut » avec une valeur « Planifié », à l'aide de l'opérateur de filtre « est exactement ».</span><span class="sxs-lookup"><span data-stu-id="c8e92-113">Apply a filter on the "Status" field, with a value of "Scheduled", using the "is exactly" filter operator.</span></span>

## <a name="create-a-schedule"></a><span data-ttu-id="c8e92-114">Créer un programme</span><span class="sxs-lookup"><span data-stu-id="c8e92-114">Create a schedule</span></span>
1. <span data-ttu-id="c8e92-115">Dans la liste, cochez ou décochez toutes les lignes.</span><span class="sxs-lookup"><span data-stu-id="c8e92-115">In the list, mark or unmark all rows.</span></span>
2. <span data-ttu-id="c8e92-116">Dans le volet Actions, cliquez sur Planification.</span><span class="sxs-lookup"><span data-stu-id="c8e92-116">On the Action Pane, click Schedule.</span></span>
3. <span data-ttu-id="c8e92-117">Cliquez sur Planifier les tâches.</span><span class="sxs-lookup"><span data-stu-id="c8e92-117">Click Schedule jobs.</span></span>
4. <span data-ttu-id="c8e92-118">Dans le champ Direction de la planification, sélectionnez « En arrière à partir de la date de livraison ».</span><span class="sxs-lookup"><span data-stu-id="c8e92-118">In the Scheduling direction field, select 'Backward from delivery date'.</span></span>
5. <span data-ttu-id="c8e92-119">Dans le champ Capacité finie, sélectionnez Non.</span><span class="sxs-lookup"><span data-stu-id="c8e92-119">Select No in the Finite capacity field.</span></span>
6. <span data-ttu-id="c8e92-120">Dans le champ Matières limitées, sélectionnez Non.</span><span class="sxs-lookup"><span data-stu-id="c8e92-120">Select No in the Finite material field.</span></span>
7. <span data-ttu-id="c8e92-121">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="c8e92-121">Click OK.</span></span>
    * <span data-ttu-id="c8e92-122">Cette opération peut prendre du temps.</span><span class="sxs-lookup"><span data-stu-id="c8e92-122">This may take a while.</span></span>  

## <a name="view-the-result-of-scheduled-production-orders"></a><span data-ttu-id="c8e92-123">Afficher le résultat des ordres de fabrication planifiés</span><span class="sxs-lookup"><span data-stu-id="c8e92-123">View the result of scheduled production orders</span></span>
1. <span data-ttu-id="c8e92-124">Dans la liste, marquez la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="c8e92-124">In the list, mark the selected row.</span></span>
    * <span data-ttu-id="c8e92-125">Vous pouvez marquer n'importe quelle ligne.</span><span class="sxs-lookup"><span data-stu-id="c8e92-125">You can mark any row.</span></span>  
2. <span data-ttu-id="c8e92-126">Cliquez sur Ordre de fabrication dans le volet Actions.</span><span class="sxs-lookup"><span data-stu-id="c8e92-126">On the Action Pane, click Production order.</span></span>
3. <span data-ttu-id="c8e92-127">Cliquez sur Toutes les tâches.</span><span class="sxs-lookup"><span data-stu-id="c8e92-127">Click All jobs.</span></span>
    * <span data-ttu-id="c8e92-128">Dans cette page, vous pouvez afficher la liste de tâches.</span><span class="sxs-lookup"><span data-stu-id="c8e92-128">On this page, you can see the list of jobs.</span></span> <span data-ttu-id="c8e92-129">Sous l'onglet Planification, vous pouvez afficher la date de début et de fin d'une tâche.</span><span class="sxs-lookup"><span data-stu-id="c8e92-129">On the Scheduling tab, you can see the Start date and End date for a job.</span></span>  
4. <span data-ttu-id="c8e92-130">Cliquez sur Matériaux.</span><span class="sxs-lookup"><span data-stu-id="c8e92-130">Click Materials.</span></span>
    * <span data-ttu-id="c8e92-131">Dans cette page, vous pouvez voir la consommation de matériaux estimée pour les opérations sur l'ordre de fabrication et le stock disponible actuel.</span><span class="sxs-lookup"><span data-stu-id="c8e92-131">On this page, you can see the estimated material consumption for the operations on the production order and the current available inventory.</span></span>  

