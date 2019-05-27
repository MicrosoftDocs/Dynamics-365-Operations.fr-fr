---
title: Ordres de contrôle
description: Cette rubrique décrit la manière dont les ordres de contrôle sont utilisés pour bloquer le stock.
author: perlynne
manager: AnnBe
ms.date: 11/02/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventLocation, InventModelGroup, InventQuarantineOrder, InventQuarantineParmEnd, InventQuarantineParmReportFinished, InventQuarantineParmStartUp, InventTrans
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 30021
ms.assetid: d5047727-653c-49da-b489-6fd3fe50445e
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 523e51c705d76b6e8624887292395f8f239bcb65
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/15/2019
ms.locfileid: "1570463"
---
# <a name="quarantine-orders"></a><span data-ttu-id="aa226-103">Ordres de contrôle</span><span class="sxs-lookup"><span data-stu-id="aa226-103">Quarantine orders</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="aa226-104">Cette rubrique décrit la manière dont les ordres de contrôle sont utilisés pour bloquer le stock.</span><span class="sxs-lookup"><span data-stu-id="aa226-104">This topic describes how quarantine orders are used to block inventory.</span></span>

<span data-ttu-id="aa226-105">Les ordres de contrôle peuvent être utilisés pour bloquer le stock.</span><span class="sxs-lookup"><span data-stu-id="aa226-105">Quarantine orders can be used to block inventory.</span></span> <span data-ttu-id="aa226-106">Par exemple, vous pouvez contrôler des articles à des fins de contrôle de la qualité.</span><span class="sxs-lookup"><span data-stu-id="aa226-106">For example, you might want to quarantine items for quality control reasons.</span></span> <span data-ttu-id="aa226-107">Le stock qui a été mis en contrôle est transféré vers un entrepôt de contrôle.</span><span class="sxs-lookup"><span data-stu-id="aa226-107">Inventory that has been quarantined is transferred to a quarantine warehouse.</span></span> <span data-ttu-id="aa226-108">**Remarque :** Si vous utilisez des processus de gestion avancée des entrepôts (dans le module gestion des entrepôts), le traitement d'ordre de contrôle n'est utilisé que pour les commandes client retournées.</span><span class="sxs-lookup"><span data-stu-id="aa226-108">**Note:** If you're using advanced warehouse management processes (in Warehouse management), quarantine order processing is used only for return sales orders.</span></span>

## <a name="quarantine-on-hand-inventory-items"></a><span data-ttu-id="aa226-109">Contrôler des articles disponibles dans le stock</span><span class="sxs-lookup"><span data-stu-id="aa226-109">Quarantine on-hand inventory items</span></span>
<span data-ttu-id="aa226-110">Lorsque vous contrôlez des articles, vous pouvez créer des ordres de contrôle manuellement ou paramétrer le système pour que celui-ci crée des ordres de contrôle automatiquement lors du traitement entrant.</span><span class="sxs-lookup"><span data-stu-id="aa226-110">When you quarantine items, you can either create the quarantine orders manually or set up the system to create the quarantine orders automatically during inbound processing.</span></span> <span data-ttu-id="aa226-111">Pour créer des ordres de contrôle automatiquement, sélectionnez l'option **Gestion des contrôles** dans l'onglet **Stratégies de stock** dans la page **Groupes de modèles d'article**.</span><span class="sxs-lookup"><span data-stu-id="aa226-111">To create quarantine orders automatically, select the **Quarantine management** option on the **Inventory policies** tab on the **Item model groups** page.</span></span> <span data-ttu-id="aa226-112">Vous devez également spécifier un entrepôt de contrôle par défaut dans le champ **Entrepôts de contrôle** pour les entrepôts de réception.</span><span class="sxs-lookup"><span data-stu-id="aa226-112">You must also specify a default quarantine warehouse in the **Quarantine warehouse** field for the receiving warehouses.</span></span> <span data-ttu-id="aa226-113">Lorsque le stock physique disponible est enregistré dans une commande fournisseur ou un ordre de fabrication, les articles mis sous contrôle sont déplacés automatiquement dans des entrepôts de contrôle dans Microsoft Dynamics 365 for Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="aa226-113">When the physically on-hand inventory is recorded in a purchase order or production order, quarantined items are automatically moved to a quarantine warehouse in Microsoft Dynamics 365 for Finance and Operations.</span></span> <span data-ttu-id="aa226-114">Ce mouvement se produit car le statut de l'ordre de contrôle est changé en **Commencé**.</span><span class="sxs-lookup"><span data-stu-id="aa226-114">This movement occurs because the status of the quarantine order is changed to **Started**.</span></span> <span data-ttu-id="aa226-115">Lorsque vous créez des ordres de contrôle manuellement, il n'est pas nécessaire que l'article actuel soit paramétré pour la gestion des contrôles dans le groupe de modèles d'article associé.</span><span class="sxs-lookup"><span data-stu-id="aa226-115">When you create quarantine orders manually, the item doesn't have to be set up for quarantine management in the associated item model group.</span></span> <span data-ttu-id="aa226-116">Pour ce processus, vous devez spécifier le stock disponible qui doit être mis sous contrôle et l'entrepôt de contrôle qui doit être utilisé.</span><span class="sxs-lookup"><span data-stu-id="aa226-116">For this process, you must specify the on-hand inventory that should be quarantined and the quarantine warehouse that should be used.</span></span> <span data-ttu-id="aa226-117">Utilisez les statuts d'ordre de contrôle pour aider à planifier le processus.</span><span class="sxs-lookup"><span data-stu-id="aa226-117">You can use the quarantine order statuses to help plan the process.</span></span>

## <a name="quarantine-order-statuses"></a><span data-ttu-id="aa226-118">Statuts de l'ordre de contrôle</span><span class="sxs-lookup"><span data-stu-id="aa226-118">Quarantine order statuses</span></span>
<span data-ttu-id="aa226-119">Les ordres de contrôle peuvent avoir les statuts suivants :</span><span class="sxs-lookup"><span data-stu-id="aa226-119">Quarantine orders can have the following statuses:</span></span>

-   <span data-ttu-id="aa226-120">Créé</span><span class="sxs-lookup"><span data-stu-id="aa226-120">Created</span></span>
-   <span data-ttu-id="aa226-121">Commencé</span><span class="sxs-lookup"><span data-stu-id="aa226-121">Started</span></span>
-   <span data-ttu-id="aa226-122">Déclaré terminé</span><span class="sxs-lookup"><span data-stu-id="aa226-122">Reported as finished</span></span>
-   <span data-ttu-id="aa226-123">Terminé</span><span class="sxs-lookup"><span data-stu-id="aa226-123">Ended</span></span>

### <a name="created"></a><span data-ttu-id="aa226-124">Créé</span><span class="sxs-lookup"><span data-stu-id="aa226-124">Created</span></span>

<span data-ttu-id="aa226-125">Lorsqu'un ordre de contrôle a été créé manuellement, mais que l'article n'est pas encore placé dans l'entrepôt de contrôle, l'ordre de contrôle a le statut **Créé**.</span><span class="sxs-lookup"><span data-stu-id="aa226-125">When a quarantine order has been created manually, but the item isn't yet in the quarantine warehouse, the quarantine order has a status of **Created**.</span></span> <span data-ttu-id="aa226-126">Deux mouvements de stock sont générés.</span><span class="sxs-lookup"><span data-stu-id="aa226-126">Two inventory transactions are generated.</span></span> <span data-ttu-id="aa226-127">La première transaction est une transaction de sortie qui peut être dotée du statut **En commande**, **Physique réservé** ou **Prélevé**.</span><span class="sxs-lookup"><span data-stu-id="aa226-127">One transaction is an issue transaction that can have a status of **On order**, **Reserved physical**, or **Picked**.</span></span> <span data-ttu-id="aa226-128">Le deuxième est une transaction de réception qui peut avoir les statuts **Commandé** ou **Enregistré** à l'entrepôt de contrôle.</span><span class="sxs-lookup"><span data-stu-id="aa226-128">The other transaction is a receipt transaction that can have a status of **Ordered** or **Registered** at the quarantine warehouse.</span></span> <span data-ttu-id="aa226-129">Vous pouvez réserver, prélever et enregistrer les mises à jour du stock à l'aide des processus habituels.</span><span class="sxs-lookup"><span data-stu-id="aa226-129">You can reserve, pick, and register updates to the inventory by using the usual processes.</span></span>

### <a name="started"></a><span data-ttu-id="aa226-130">Commencé</span><span class="sxs-lookup"><span data-stu-id="aa226-130">Started</span></span>

<span data-ttu-id="aa226-131">Quand un ordre de contrôle a le statut **Commencé**, le stock est transféré de l'entrepôt ordinaire vers l'entrepôt de contrôle et deux mouvements de stock sont générés.</span><span class="sxs-lookup"><span data-stu-id="aa226-131">When a quarantine order has a status of **Started**, the inventory is transferred from the regular warehouse to the quarantine warehouse, and two inventory transactions are generated.</span></span> <span data-ttu-id="aa226-132">Une transaction a le statut **Déduit** et l'autre a le statut **Reçu**.</span><span class="sxs-lookup"><span data-stu-id="aa226-132">One transaction has a status of **Deducted**, and the other transaction has a status of **Received**.</span></span> <span data-ttu-id="aa226-133">En même temps, deux mouvements de stock sont créés pour gérer le transfert en retour.</span><span class="sxs-lookup"><span data-stu-id="aa226-133">At the same time, two inventory transactions are created to handle the return transfer.</span></span> <span data-ttu-id="aa226-134">Ces transactions ne sont pas datées.</span><span class="sxs-lookup"><span data-stu-id="aa226-134">These transactions aren't dated.</span></span> <span data-ttu-id="aa226-135">Une transaction a le statut **Physique réservé** et l'autre a le statut **Commandé**.</span><span class="sxs-lookup"><span data-stu-id="aa226-135">One transaction has a status of **Reserved physical**, and the other transaction has a status of **Ordered**.</span></span>

### <a name="reported-as-finished"></a><span data-ttu-id="aa226-136">Déclaré terminé</span><span class="sxs-lookup"><span data-stu-id="aa226-136">Reported as finished</span></span>

<span data-ttu-id="aa226-137">Pour déclarer un ordre de contrôle commencé comme terminé, cliquez sur **Déclaration de fin**.</span><span class="sxs-lookup"><span data-stu-id="aa226-137">By clicking **Report as finished**, you can report a started quarantine order as finished.</span></span> <span data-ttu-id="aa226-138">L'article n'est plus sous contrôle mais il n'est pas encore replacé dans l'entrepôt ordinaire.</span><span class="sxs-lookup"><span data-stu-id="aa226-138">The item is released from quarantine but isn't yet moved back to the regular warehouse.</span></span> <span data-ttu-id="aa226-139">Le mouvement vers l'entrepôt ordinaire peut être traité via un Journal des arrivées d'articles pouvant être initialisé lors de l'État dans le cadre du processus de déclaration de fin.</span><span class="sxs-lookup"><span data-stu-id="aa226-139">The movement back to the regular warehouse can be processed via an Item arrival journal that can be initialized during the Report as finished process.</span></span>

### <a name="ended"></a><span data-ttu-id="aa226-140">Terminé</span><span class="sxs-lookup"><span data-stu-id="aa226-140">Ended</span></span>

<span data-ttu-id="aa226-141">Lorsqu'un ordre de contrôle prend fin, l'article est déplacé de l'entrepôt de contrôle vers l'entrepôt ordinaire.</span><span class="sxs-lookup"><span data-stu-id="aa226-141">When a quarantine order is ended, the item is moved from the quarantine warehouse back to the regular warehouse.</span></span> <span data-ttu-id="aa226-142">Le statut de la transaction d'article est défini sur **Vendu** au niveau de l'entrepôt de contrôle et sur **Acheté** au niveau de l'entrepôt ordinaire.</span><span class="sxs-lookup"><span data-stu-id="aa226-142">The status of the item transaction is set to **Sold** at the quarantine warehouse and **Purchased** at the regular warehouse.</span></span>

## <a name="quarantine-order-scrap"></a><span data-ttu-id="aa226-143">Rebut d'ordre de contrôle</span><span class="sxs-lookup"><span data-stu-id="aa226-143">Quarantine order scrap</span></span>
<span data-ttu-id="aa226-144">Dans le cadre du processus d'ordre de contrôle, vous pouvez mettre le stock au rebut.</span><span class="sxs-lookup"><span data-stu-id="aa226-144">As part of the quarantine order process, you can scrap inventory.</span></span> <span data-ttu-id="aa226-145">Lors du traitement d'une mise au rebut, le statut du stock sera défini sur **Vendu** par une transaction de sortie de l'entrepôt de contrôle.</span><span class="sxs-lookup"><span data-stu-id="aa226-145">When you process scrap, the status of the inventory will be set to **Sold** by an issue transaction from the quarantine warehouse.</span></span>

<a name="additional-resources"></a><span data-ttu-id="aa226-146">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="aa226-146">Additional resources</span></span>
--------

[<span data-ttu-id="aa226-147">Blocage du stock</span><span class="sxs-lookup"><span data-stu-id="aa226-147">Inventory blocking</span></span>](inventory-blocking.md)
