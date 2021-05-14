---
title: Vous ne pouvez pas confirmer une expédition car un élément est manquant ou incomplet
description: Vous ne pouvez pas confirmer une expédition car un élément est manquant ou incomplet
author: perlynne
ms.date: 04/21/2021
ms.topic: troubleshooting
ms.search.form: WHSLoadTable_WHSShipConfirm,WHSLoadPlanningListPage_WHSShipConfirm,WHSLoadPlanningWorkbench_WHSShipConfirm,WHSTransportLoad_WHSShipConfirm,WHSShipPlanningListPage_WHSShipConfirm,WHSShipmentDetails_WHSShipConfirm,WHSWorkTable_WHSShipConfirm,WHSWorkTableListPage_WHSShipConfirm,Dialog_WHSOutboundShipConfirmController_WHSOutboundShipConfirm
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: lbc
ms.search.validFrom: 2021-04-21
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: da6388d433d6021a99840ae9781c717db1b540a9
ms.sourcegitcommit: cd9016e9787169cb800889d335b9c5919ddbe4af
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2021
ms.locfileid: "5938470"
---
# <a name="you-cant-confirm-a-shipment-because-of-incomplete-or-missing-work"></a><span data-ttu-id="3ceef-103">Vous ne pouvez pas confirmer une expédition car un élément est manquant ou incomplet</span><span class="sxs-lookup"><span data-stu-id="3ceef-103">You can't confirm a shipment because of incomplete or missing work</span></span>

<span data-ttu-id="3ceef-104">Code d’erreur : WAX515</span><span class="sxs-lookup"><span data-stu-id="3ceef-104">Error code: WAX515</span></span>

## <a name="symptoms"></a><span data-ttu-id="3ceef-105">Symptômes</span><span class="sxs-lookup"><span data-stu-id="3ceef-105">Symptoms</span></span>

<span data-ttu-id="3ceef-106">Lorsque vous essayez de confirmer une expédition, le système affiche le message d'erreur suivant :</span><span class="sxs-lookup"><span data-stu-id="3ceef-106">When you try to confirm a shipment, the system shows the following error message:</span></span>

> <span data-ttu-id="3ceef-107">Impossible de confirmer l'expédition pour le chargement %1, car l'ensemble du travail pour le chargement doit être terminé.</span><span class="sxs-lookup"><span data-stu-id="3ceef-107">The shipment for load %1 could not be confirmed because all work for the load must be complete.</span></span>

<span data-ttu-id="3ceef-108">Par conséquent, vous ne pouvez pas confirmer l'expédition pour le chargement.</span><span class="sxs-lookup"><span data-stu-id="3ceef-108">Therefore, you can't confirm the shipment for the load.</span></span>

## <a name="cause"></a><span data-ttu-id="3ceef-109">Cause</span><span class="sxs-lookup"><span data-stu-id="3ceef-109">Cause</span></span>

<span data-ttu-id="3ceef-110">Le chargement ou l'expédition est actuellement dans un état d'échec.</span><span class="sxs-lookup"><span data-stu-id="3ceef-110">The load or shipment is currently in a state where shipment confirmation fails.</span></span> <span data-ttu-id="3ceef-111">Avant de pouvoir confirmer l'expédition, il doit au moins exister certains travaux pour le chargement, et ils doivent tous avoir le statut *Clôturé* ou *Annulé*.</span><span class="sxs-lookup"><span data-stu-id="3ceef-111">Before you can confirm the shipment, at least some work must exist for the load, and all that work must have a status of *Closed* or *Canceled*.</span></span>

## <a name="resolution"></a><span data-ttu-id="3ceef-112">Résolution</span><span class="sxs-lookup"><span data-stu-id="3ceef-112">Resolution</span></span>

<span data-ttu-id="3ceef-113">Vérifiez les commandes client ou les ordres de transfert associés pour le chargement ou l'expédition, et assurez-vous que tous les travaux connexes ont été terminés ou annulés.</span><span class="sxs-lookup"><span data-stu-id="3ceef-113">Check the related sales orders or transfer orders for the load or shipment, and make sure that all the related work has been completed or canceled.</span></span>

<span data-ttu-id="3ceef-114">Vous pouvez travailler avec des expéditions et des chargements sur plusieurs pages.</span><span class="sxs-lookup"><span data-stu-id="3ceef-114">You can work with shipments and loads on several pages.</span></span> <span data-ttu-id="3ceef-115">Les sous-sections suivantes fournissent quelques exemples.</span><span class="sxs-lookup"><span data-stu-id="3ceef-115">The following subsections provide a few examples.</span></span>

### <a name="all-loads-page"></a><span data-ttu-id="3ceef-116">Page Tous les chargements</span><span class="sxs-lookup"><span data-stu-id="3ceef-116">All loads page</span></span>

1. <span data-ttu-id="3ceef-117">Accédez à **Gestion des entrepôts \> Chargements \> Tous les chargements**.</span><span class="sxs-lookup"><span data-stu-id="3ceef-117">Go to **Warehouse management \> Loads \> All loads**.</span></span>
1. <span data-ttu-id="3ceef-118">Sélectionnez le chargement pour lequel l'expédition ne peut pas être confirmée.</span><span class="sxs-lookup"><span data-stu-id="3ceef-118">Select the load that the shipment can't be confirmed for.</span></span>
1. <span data-ttu-id="3ceef-119">Dans le volet Actions, sous l’onglet **Chargements**, dans le groupe **Informations associées**, cliquez sur **Travail**.</span><span class="sxs-lookup"><span data-stu-id="3ceef-119">On the Action Pane, on the **Loads** tab, in the **Related information** group, select **Work**.</span></span>
1. <span data-ttu-id="3ceef-120">Inspectez le statut de chaque ID de travail.</span><span class="sxs-lookup"><span data-stu-id="3ceef-120">Inspect the status of each work ID.</span></span> <span data-ttu-id="3ceef-121">Faites le suivi de chaque ID de travail qui n'a pas le statut *Clôturé* ou *Annulé*.</span><span class="sxs-lookup"><span data-stu-id="3ceef-121">Follow up on each work ID that doesn't have a status of *Closed* or *Canceled*.</span></span>
1. <span data-ttu-id="3ceef-122">Lorsque chaque ID de travail a un statut *Clôturé* ou *Annulé*, réessayez pour confirmer l'expédition.</span><span class="sxs-lookup"><span data-stu-id="3ceef-122">When every work ID has a status of *Closed* or *Canceled*, try again to confirm the shipment.</span></span>

### <a name="all-shipments-page"></a><span data-ttu-id="3ceef-123">Page Toutes les expéditions</span><span class="sxs-lookup"><span data-stu-id="3ceef-123">All shipments page</span></span>

1. <span data-ttu-id="3ceef-124">Allez dans **Gestion des entrepôts \> Expéditions \> Toutes les expéditions**.</span><span class="sxs-lookup"><span data-stu-id="3ceef-124">Go to **Warehouse management \> Shipments\> All shipments**.</span></span>
1. <span data-ttu-id="3ceef-125">Sélectionnez l'expédition qui ne peut pas être confirmée.</span><span class="sxs-lookup"><span data-stu-id="3ceef-125">Select the shipment that can't be confirmed.</span></span>
1. <span data-ttu-id="3ceef-126">Dans le volet Actions, sous l’onglet **Expéditions**, dans le groupe **Travail**, cliquez sur **Détails du travail**.</span><span class="sxs-lookup"><span data-stu-id="3ceef-126">On the Action Pane, on the **Shipments** tab, in the **Work** group, select **Work details**.</span></span>
1. <span data-ttu-id="3ceef-127">Inspectez le statut de chaque ID de travail.</span><span class="sxs-lookup"><span data-stu-id="3ceef-127">Inspect the status of each work ID.</span></span> <span data-ttu-id="3ceef-128">Faites le suivi de chaque ID de travail qui n'a pas le statut *Clôturé* ou *Annulé*.</span><span class="sxs-lookup"><span data-stu-id="3ceef-128">Follow up on each work ID that doesn't have a status of *Closed* or *Canceled*.</span></span>
1. <span data-ttu-id="3ceef-129">Lorsque chaque ID de travail a un statut *Clôturé* ou *Annulé*, réessayez pour confirmer l'expédition.</span><span class="sxs-lookup"><span data-stu-id="3ceef-129">When every work ID has a status of *Closed* or *Canceled*, try again to confirm the shipment.</span></span>

### <a name="all-work-page"></a><span data-ttu-id="3ceef-130">Page Tout le travail</span><span class="sxs-lookup"><span data-stu-id="3ceef-130">All work page</span></span>

1. <span data-ttu-id="3ceef-131">Accédez à **Gestion des entrepôts \> Travail\> Tout le travail**.</span><span class="sxs-lookup"><span data-stu-id="3ceef-131">Go to **Warehouse management \> Work\> All work**.</span></span>
1. <span data-ttu-id="3ceef-132">Sélectionnez le travail correspondant au numéro de commande pour lequel l'expédition ne peut pas être confirmée.</span><span class="sxs-lookup"><span data-stu-id="3ceef-132">Select the work for the order number that the shipment can't be confirmed for.</span></span>
1. <span data-ttu-id="3ceef-133">Dans le volet Actions, sous l’onglet **Expédition**, dans le groupe **Expédition**, sélectionnez **Confirmer l’expédition**.</span><span class="sxs-lookup"><span data-stu-id="3ceef-133">On the Action Pane, on the **Shipment** tab, in the **Shipment** group, select **Confirm shipment**.</span></span>
1. <span data-ttu-id="3ceef-134">Inspectez le statut de chaque ID de travail.</span><span class="sxs-lookup"><span data-stu-id="3ceef-134">Inspect the status of each work ID.</span></span> <span data-ttu-id="3ceef-135">Faites le suivi de chaque ID de travail qui n'a pas le statut *Clôturé* ou *Annulé*.</span><span class="sxs-lookup"><span data-stu-id="3ceef-135">Follow up on each work ID that doesn't have a status of *Closed* or *Canceled*.</span></span>
1. <span data-ttu-id="3ceef-136">Lorsque chaque ID de travail a un statut *Clôturé* ou *Annulé*, réessayez pour confirmer l'expédition.</span><span class="sxs-lookup"><span data-stu-id="3ceef-136">When every work ID has a status of *Closed* or *Canceled*, try again to confirm the shipment.</span></span>
