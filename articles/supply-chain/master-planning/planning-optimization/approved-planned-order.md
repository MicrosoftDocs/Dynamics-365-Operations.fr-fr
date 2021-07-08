---
title: Afficher, gérer et approuver les ordres prévisionnels
description: Cette rubrique fournit des informations sur l’affichage, la gestion et l’approbation des ordres prévisionnels dans l’Optimisation de la planification.
author: ChristianRytt
ms.date: 04/07/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ReqCreatePlanWorkspace
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2020-08-21
ms.dyn365.ops.version: 10.0.13
ms.openlocfilehash: 71ec26bea2063bcf8b6d302a7ece804b3ac934b3
ms.sourcegitcommit: 3673eeca1ada0f3e4ec277176515a946706f8a41
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/24/2021
ms.locfileid: "6304365"
---
# <a name="view-manage-and-approve-planned-orders"></a><span data-ttu-id="b8950-103">Afficher, gérer et approuver les ordres prévisionnels</span><span class="sxs-lookup"><span data-stu-id="b8950-103">View, manage, and approve planned orders</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="b8950-104">Cette rubrique fournit des informations sur l’affichage, la gestion et l’approbation des ordres prévisionnels dans l’Optimisation de la planification.</span><span class="sxs-lookup"><span data-stu-id="b8950-104">This topic provides information about how to view, manage, and approve planned orders in Planning Optimization.</span></span>

## <a name="view-and-manage-planned-orders"></a><a name="view-planned-orders"></a><span data-ttu-id="b8950-105">Afficher et gérer les ordres prévisionnels</span><span class="sxs-lookup"><span data-stu-id="b8950-105">View and manage planned orders</span></span>

<span data-ttu-id="b8950-106">Vous pouvez afficher et gérer les ordres prévisionnels sur n’importe quelle page de liste d’ordres prévisionnels.</span><span class="sxs-lookup"><span data-stu-id="b8950-106">You can view and manage planned orders on any planned orders list page.</span></span> <span data-ttu-id="b8950-107">Accédez à l’un des emplacements suivants, en fonction du type d’ordres prévisionnels avec lesquels vous souhaitez travailler :</span><span class="sxs-lookup"><span data-stu-id="b8950-107">Go to one of the following places, depending on the type of planned orders that you want to work with:</span></span>

- <span data-ttu-id="b8950-108">Planification \> Espaces de travail \> Planification</span><span class="sxs-lookup"><span data-stu-id="b8950-108">Master planning \> Workspaces \> Master planning</span></span>
- <span data-ttu-id="b8950-109">Planification \> Planification \> Ordres prévisionnels</span><span class="sxs-lookup"><span data-stu-id="b8950-109">Master planning \> Master planning \> Planned orders</span></span>
- <span data-ttu-id="b8950-110">Contrôle de la production \> Ordres de fabrication \> Ordres de fabrication prévisionnels</span><span class="sxs-lookup"><span data-stu-id="b8950-110">Production control \> Production orders \> Planned production orders</span></span>
- <span data-ttu-id="b8950-111">Approvisionnements \> Commandes fournisseur \> Commandes fournisseurs prévisionnelles</span><span class="sxs-lookup"><span data-stu-id="b8950-111">Procurement and sourcing \> Purchase orders \> Planned purchase orders</span></span>
- <span data-ttu-id="b8950-112">Gestion des stocks \> Commandes entrantes \> Ordres de transfert prévisionnels</span><span class="sxs-lookup"><span data-stu-id="b8950-112">Inventory management \> Inbound orders \> Planned transfers</span></span>
- <span data-ttu-id="b8950-113">Gestion des stocks \> Commandes sortantes \> Ordres de transfert prévisionnels</span><span class="sxs-lookup"><span data-stu-id="b8950-113">Inventory management \> Outbound orders \> Planned transfers</span></span>

## <a name="view-and-edit-the-status-of-planned-orders"></a><span data-ttu-id="b8950-114">Afficher et modifier le statut des ordres prévisionnels</span><span class="sxs-lookup"><span data-stu-id="b8950-114">View and edit the status of planned orders</span></span>

<span data-ttu-id="b8950-115">Vous pouvez utiliser le **Statut** de chaque ordre prévisionnel pour suivre votre progression ou modifier le traitement d’un ordre prévisionnel.</span><span class="sxs-lookup"><span data-stu-id="b8950-115">You can use the **Status** field of each planned order to help track your progress or change how a planned order will be processed.</span></span> <span data-ttu-id="b8950-116">Les valeurs de **Statut** suivantes sont disponibles :</span><span class="sxs-lookup"><span data-stu-id="b8950-116">The following **Status** values are available:</span></span>

- <span data-ttu-id="b8950-117">**Non traité** – Lorsque la planification génère des ordres prévisionnels, ils reçoivent ce statut.</span><span class="sxs-lookup"><span data-stu-id="b8950-117">**Unprocessed** – When master planning generates planned orders, they are given this status.</span></span> <span data-ttu-id="b8950-118">Les ordres prévisionnels qui ont ce statut seront supprimés lors du prochain cycle de planification.</span><span class="sxs-lookup"><span data-stu-id="b8950-118">Planned orders that have this status will be deleted during the next planning run.</span></span>
- <span data-ttu-id="b8950-119">**Terminé** – Ce statut indique que l’ordre prévisionnel est terminé.</span><span class="sxs-lookup"><span data-stu-id="b8950-119">**Completed** – This status indicates that the planned order has been completed.</span></span> <span data-ttu-id="b8950-120">Si vous décidez de ne pas confirmer un ordre prévisionnel, vous pouvez modifier manuellement son statut sur *Terminé*.</span><span class="sxs-lookup"><span data-stu-id="b8950-120">If you decide not to firm a planned order, you can manually change its status to *Completed*.</span></span> <span data-ttu-id="b8950-121">Notez traite les statuts *Non traité* et *Terminé* de la même manière.</span><span class="sxs-lookup"><span data-stu-id="b8950-121">Note that the system treats the *Unprocessed* and *Completed* statuses in the same way.</span></span>
- <span data-ttu-id="b8950-122">**Approuvé** – Ce statut indique que l’ordre prévisionnel est approuvé pour confirmation.</span><span class="sxs-lookup"><span data-stu-id="b8950-122">**Approved** – This status indicates that the planned order is approved for firming.</span></span> <span data-ttu-id="b8950-123">Si vous souhaitez confirmer un ordre prévisionnel, vous pouvez modifier son statut sur *Approuvé*.</span><span class="sxs-lookup"><span data-stu-id="b8950-123">If you want to firm a planned order, you can change its status to *Approved*.</span></span> <span data-ttu-id="b8950-124">Si vous souhaitez conserver les modifications apportées à un ordre prévisionnel ou si vous prévoyez de confirmer un ordre prévisionnel, changez son statut en *Approuvé*.</span><span class="sxs-lookup"><span data-stu-id="b8950-124">If you want to keep the edits that have been made to a planned order, or if you're planning to firm a planned order, change its status to *Approved*.</span></span> <span data-ttu-id="b8950-125">Les ordres prévisionnels dont le statut est *Approuvé* sont considérés comme des approvisionnements fixes et attendus par la planification.</span><span class="sxs-lookup"><span data-stu-id="b8950-125">Planned orders that have a status of *Approved* are considered fixed and expected supply by master planning.</span></span> <span data-ttu-id="b8950-126">Par conséquent, ils ne sont ni modifiés ni supprimés lors des exécutions ultérieures de la planification.</span><span class="sxs-lookup"><span data-stu-id="b8950-126">Therefore, they aren't modified or deleted during later master planning runs.</span></span> <span data-ttu-id="b8950-127">Pour ce faire, la logique de planification copie les ordres prévisionnels qui ont un statut *Approuvé* de l’ancienne version du plan vers la nouvelle version du plan lors de la planification.</span><span class="sxs-lookup"><span data-stu-id="b8950-127">To achieve this behavior, the planning logic copies planned orders that have a status of *Approved* from the old plan version to the new plan version during master planning.</span></span> <span data-ttu-id="b8950-128">Notez que les ordres prévisionnels qui ont le statut *Approuvé* ne sont considérés comme des approvisionnements que dans le cadre du plan directeur spécifique.</span><span class="sxs-lookup"><span data-stu-id="b8950-128">Note that planned orders that have a status of *Approved* are considered supply only within the specific master plan.</span></span>

<span data-ttu-id="b8950-129">Pour modifier le statut d’un seul ordre prévisionnel, [ouvrez une page de liste d’ordres prévisionnels](#view-planned-orders), ouvrez l’ordre, puis effectuez l’une de ces étapes :</span><span class="sxs-lookup"><span data-stu-id="b8950-129">To change the status of a single planned order, [open any planned orders list page](#view-planned-orders), open the order, and then follow one of these steps:</span></span>

- <span data-ttu-id="b8950-130">Sur le raccourci **Général**, modifiez la valeur du champ **Statut**.</span><span class="sxs-lookup"><span data-stu-id="b8950-130">On the **General** FastTab, change the value of the **Status** field.</span></span>
- <span data-ttu-id="b8950-131">Dans le volet Actions, sous l’onglet **Ordre prévisionnel**, dans le groupe **Processus**, sélectionnez **Modifier le statut**.</span><span class="sxs-lookup"><span data-stu-id="b8950-131">On the Action Pane, on the **Planned order** tab, in the **Process** group, select **Change status**.</span></span>
- <span data-ttu-id="b8950-132">Pour marquer l’ordre comme approuvé, dans le volet Actions, sélectionnez **Approuver**.</span><span class="sxs-lookup"><span data-stu-id="b8950-132">On the Action Pane, select **Approve** to mark the order as approved.</span></span>

<span data-ttu-id="b8950-133">Pour modifier le statut de plusieurs ordres prévisionnels en même temps, [ouvrez une page de liste d’ordres prévisionnels](#view-planned-orders), activez la case à cocher pour chaque ordre que vous souhaitez modifier, puis effectuez l’une des étapes suivantes :</span><span class="sxs-lookup"><span data-stu-id="b8950-133">To change the status of several planned orders at the same time, [open any planned orders list page](#view-planned-orders), select the check box for each order that you want to change, and then follow one of these steps:</span></span>

- <span data-ttu-id="b8950-134">Dans le volet Actions, sous l’onglet **Ordre prévisionnel**, dans le groupe **Processus**, sélectionnez **Modifier le statut**.</span><span class="sxs-lookup"><span data-stu-id="b8950-134">On the Action Pane, on the **Planned order** tab, in the **Process** group, select **Change status**.</span></span>
- <span data-ttu-id="b8950-135">Pour marquer les ordres comme approuvés, dans le volet Actions, sélectionnez **Approuver**.</span><span class="sxs-lookup"><span data-stu-id="b8950-135">On the Action Pane, select **Approve** to mark the orders as approved.</span></span>

## <a name="approve-planned-orders"></a><span data-ttu-id="b8950-136">Approuver les ordres prévisionnels</span><span class="sxs-lookup"><span data-stu-id="b8950-136">Approve planned orders</span></span>

<span data-ttu-id="b8950-137">L’approbation des ordres prévisionnels est une étape facultative dans le processus de création d’un ordre confirmé à partir d’un ordre prévisionnel.</span><span class="sxs-lookup"><span data-stu-id="b8950-137">Approval of planned orders is an optional step in the process of creating a firmed order from a planned order.</span></span>

<span data-ttu-id="b8950-138">L’illustration suivante montre comment utiliser la valeur **Statut** affectée à chaque ordre prévisionnel pour implémenter un workflow d’approbation.</span><span class="sxs-lookup"><span data-stu-id="b8950-138">The following illustration shows how you can use the **Status** value that is assigned to each planned order to implement an approval workflow.</span></span> <span data-ttu-id="b8950-139">Pour mettre en œuvre un processus d’approbation, ajustez manuellement la valeur **Statut** pour chaque ordre prévisionnel comme décrit dans la section précédente.</span><span class="sxs-lookup"><span data-stu-id="b8950-139">To implement an approval process, manually adjust the **Status** value for each planned order as described in the previous section.</span></span>

![Flux d’ordre prévisionnel](media/approved-planned-orders-1.png)

> [!TIP]
> <span data-ttu-id="b8950-141">Nous vous recommandons d’approuver tous les ordres prévisionnels modifiés.</span><span class="sxs-lookup"><span data-stu-id="b8950-141">We recommend that you approve any modified planned orders.</span></span> <span data-ttu-id="b8950-142">Sinon, les modifications seront ignorées et écrasées lors du prochain cycle de planification.</span><span class="sxs-lookup"><span data-stu-id="b8950-142">Otherwise, the edits will be ignored and overwritten by the next planning run.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="b8950-143">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="b8950-143">Additional resources</span></span>

- [<span data-ttu-id="b8950-144">Ordres prévisionnels confirmés</span><span class="sxs-lookup"><span data-stu-id="b8950-144">Firm planned orders</span></span>](planned-order-firming.md)

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
