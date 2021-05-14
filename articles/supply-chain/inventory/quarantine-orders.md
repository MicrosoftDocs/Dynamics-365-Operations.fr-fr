---
title: Ordres de contrôle
description: Cette rubrique décrit comment utiliser les ordres de contrôle pour bloquer le stock.
author: perlynne
ms.date: 03/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: InventLocation, InventModelGroup, InventQuarantineOrder, InventQuarantineParmEnd, InventQuarantineParmReportFinished, InventQuarantineParmStartUp, InventTrans
audience: Application User
ms.reviewer: kamaybac
ms.custom: 30021
ms.assetid: d5047727-653c-49da-b489-6fd3fe50445e
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 5e1eed14b7d38cf569af7192dec9580e771f06df
ms.sourcegitcommit: 8362f3bd32ce8b9a5af93c8e57daef732a93b19e
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/28/2021
ms.locfileid: "5956180"
---
# <a name="quarantine-orders"></a><span data-ttu-id="2e99a-103">Ordres de contrôle</span><span class="sxs-lookup"><span data-stu-id="2e99a-103">Quarantine orders</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="2e99a-104">Cette rubrique décrit comment utiliser les ordres de contrôle pour bloquer le stock.</span><span class="sxs-lookup"><span data-stu-id="2e99a-104">This topic describes how to use quarantine orders to block inventory.</span></span>

<span data-ttu-id="2e99a-105">Les ordres de contrôle vous permettent de bloquer le stock.</span><span class="sxs-lookup"><span data-stu-id="2e99a-105">Quarantine orders let you block inventory.</span></span> <span data-ttu-id="2e99a-106">Par exemple, vous pouvez contrôler des articles à des fins de contrôle de la qualité.</span><span class="sxs-lookup"><span data-stu-id="2e99a-106">For example, you might want to quarantine items for quality control reasons.</span></span> <span data-ttu-id="2e99a-107">Le stock qui a été mis en contrôle est transféré vers un entrepôt de contrôle.</span><span class="sxs-lookup"><span data-stu-id="2e99a-107">Inventory that has been quarantined is transferred to a quarantine warehouse.</span></span>

> [!NOTE]
> <span data-ttu-id="2e99a-108">Si vous utilisez des processus de gestion avancée des entrepôts (dans le module Gestion des entrepôts), le traitement d’ordre de contrôle n’est utilisé que pour les commandes client retournées.</span><span class="sxs-lookup"><span data-stu-id="2e99a-108">If you're using advanced warehouse management processes (in Warehouse management), quarantine order processing is used only for return sales orders.</span></span>

## <a name="quarantine-on-hand-inventory-items"></a><span data-ttu-id="2e99a-109">Contrôler des articles disponibles dans le stock</span><span class="sxs-lookup"><span data-stu-id="2e99a-109">Quarantine on-hand inventory items</span></span>

<span data-ttu-id="2e99a-110">Lorsque vous contrôlez des articles, vous pouvez soit créer des ordres de contrôle manuellement ou paramétrer le système pour le faire automatiquement lors du traitement entrant.</span><span class="sxs-lookup"><span data-stu-id="2e99a-110">When you quarantine items, you can either manually create the quarantine orders or set up the system to automatically create them during inbound processing.</span></span>

<span data-ttu-id="2e99a-111">Pour configurer le système afin de générer automatiquement des ordres de contrôle, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="2e99a-111">To set up the system to automatically generate quarantine orders, follow these steps.</span></span>

1. <span data-ttu-id="2e99a-112">Allez dans **Gestion des stocks \> Paramétrage \> Stock \> Groupes de modèles d'article**.</span><span class="sxs-lookup"><span data-stu-id="2e99a-112">Go to **Inventory management \> Setup \> Inventory \> Item model groups**.</span></span>
1. <span data-ttu-id="2e99a-113">Sélectionnez un groupe de modèles approprié dans le volet de liste ou créez un groupe de modèles.</span><span class="sxs-lookup"><span data-stu-id="2e99a-113">Select a relevant model group in the list pane, or create a new model group.</span></span>
1. <span data-ttu-id="2e99a-114">Dans le raccourci **Stratégies de stock**, cochez la case **Gestion des contrôles**.</span><span class="sxs-lookup"><span data-stu-id="2e99a-114">On the **Inventory policies** FastTab, select the **Quarantine management** check box.</span></span>
1. <span data-ttu-id="2e99a-115">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="2e99a-115">Close the page.</span></span>
1. <span data-ttu-id="2e99a-116">Spécifiez un entrepôt de contrôle par défaut dans le champ **Entrepôts de contrôle** pour les entrepôts de réception.</span><span class="sxs-lookup"><span data-stu-id="2e99a-116">In the **Quarantine warehouse** field for the receiving warehouses, specify a default quarantine warehouse.</span></span>

<span data-ttu-id="2e99a-117">Lorsqu'un article enregistré comme reçu à l'entrepôt appartient à un groupe de modèles dans lequel la case **Gestion des contrôles** est cochée, le système génère un ordre de contrôle pour celui-ci.</span><span class="sxs-lookup"><span data-stu-id="2e99a-117">When an item that is registered as received at the warehouse belongs to a model group where the **Quarantine management** check box is selected, the system generates a quarantine order for it.</span></span> <span data-ttu-id="2e99a-118">L'ordre de contrôle demande aux travailleurs de déplacer l'article vers l'entrepôt de contrôle.</span><span class="sxs-lookup"><span data-stu-id="2e99a-118">The quarantine order instructs workers to move the item to the quarantine warehouse.</span></span>

<span data-ttu-id="2e99a-119">Lorsque vous créez des ordres de contrôle manuellement sur la page **Ordres de contrôle**, il n’est pas nécessaire que l’article actuel soit paramétré pour la gestion des contrôles dans le groupe de modèles d’article associé.</span><span class="sxs-lookup"><span data-stu-id="2e99a-119">When you manually create quarantine orders on the **Quarantine orders** page, the item doesn't have to be set up for quarantine management in the associated item model group.</span></span> <span data-ttu-id="2e99a-120">Pour ce processus, vous devez spécifier le stock disponible qui doit être mis sous contrôle et l’entrepôt de contrôle qui doit être utilisé.</span><span class="sxs-lookup"><span data-stu-id="2e99a-120">For this process, you must specify the on-hand inventory that should be quarantined and the quarantine warehouse that should be used.</span></span> <span data-ttu-id="2e99a-121">Utilisez les statuts d’ordre de contrôle pour aider à planifier le processus.</span><span class="sxs-lookup"><span data-stu-id="2e99a-121">You can use the quarantine order statuses to help plan the process.</span></span>

## <a name="quarantine-order-statuses"></a><span data-ttu-id="2e99a-122">Statuts de l’ordre de contrôle</span><span class="sxs-lookup"><span data-stu-id="2e99a-122">Quarantine order statuses</span></span>

<span data-ttu-id="2e99a-123">Les ordres de contrôle peuvent avoir les statuts suivants :</span><span class="sxs-lookup"><span data-stu-id="2e99a-123">Quarantine orders can have the following statuses:</span></span>

- <span data-ttu-id="2e99a-124">Créé</span><span class="sxs-lookup"><span data-stu-id="2e99a-124">Created</span></span>
- <span data-ttu-id="2e99a-125">Commencé</span><span class="sxs-lookup"><span data-stu-id="2e99a-125">Started</span></span>
- <span data-ttu-id="2e99a-126">Déclaré terminé</span><span class="sxs-lookup"><span data-stu-id="2e99a-126">Reported as finished</span></span>
- <span data-ttu-id="2e99a-127">Terminé</span><span class="sxs-lookup"><span data-stu-id="2e99a-127">Ended</span></span>

### <a name="created"></a><span data-ttu-id="2e99a-128">Créé</span><span class="sxs-lookup"><span data-stu-id="2e99a-128">Created</span></span>

<span data-ttu-id="2e99a-129">Lorsqu’un ordre de contrôle a été créé manuellement, mais que l’article n’est pas encore placé dans l’entrepôt de contrôle, l’ordre de contrôle a le statut **Créé**.</span><span class="sxs-lookup"><span data-stu-id="2e99a-129">When a quarantine order has been created manually, but the item isn't yet in the quarantine warehouse, the quarantine order has a status of **Created**.</span></span> <span data-ttu-id="2e99a-130">Deux mouvements de stock sont générés.</span><span class="sxs-lookup"><span data-stu-id="2e99a-130">Two inventory transactions are generated.</span></span> <span data-ttu-id="2e99a-131">La première transaction est une transaction de sortie qui peut être dotée du statut **En commande**, **Physique réservé** ou **Prélevé**.</span><span class="sxs-lookup"><span data-stu-id="2e99a-131">One transaction is an issue transaction that can have a status of **On order**, **Reserved physical**, or **Picked**.</span></span> <span data-ttu-id="2e99a-132">Le deuxième est une transaction de réception qui peut avoir les statuts **Commandé** ou **Enregistré** à l’entrepôt de contrôle.</span><span class="sxs-lookup"><span data-stu-id="2e99a-132">The other transaction is a receipt transaction that can have a status of **Ordered** or **Registered** at the quarantine warehouse.</span></span> <span data-ttu-id="2e99a-133">Vous pouvez réserver, prélever et enregistrer les mises à jour du stock à l’aide des processus habituels.</span><span class="sxs-lookup"><span data-stu-id="2e99a-133">You can reserve, pick, and register updates to the inventory by using the usual processes.</span></span>

### <a name="started"></a><span data-ttu-id="2e99a-134">Commencé</span><span class="sxs-lookup"><span data-stu-id="2e99a-134">Started</span></span>

<span data-ttu-id="2e99a-135">Quand un ordre de contrôle a le statut **Commencé**, le stock est transféré de l’entrepôt ordinaire vers l’entrepôt de contrôle et deux mouvements de stock sont générés.</span><span class="sxs-lookup"><span data-stu-id="2e99a-135">When a quarantine order has a status of **Started**, the inventory is transferred from the regular warehouse to the quarantine warehouse, and two inventory transactions are generated.</span></span> <span data-ttu-id="2e99a-136">Une transaction a le statut **Déduit** et l’autre a le statut **Reçu**.</span><span class="sxs-lookup"><span data-stu-id="2e99a-136">One transaction has a status of **Deducted**, and the other transaction has a status of **Received**.</span></span> <span data-ttu-id="2e99a-137">En même temps, deux mouvements de stock sont créés pour gérer le transfert en retour.</span><span class="sxs-lookup"><span data-stu-id="2e99a-137">At the same time, two inventory transactions are created to handle the return transfer.</span></span> <span data-ttu-id="2e99a-138">Ces transactions ne sont pas datées.</span><span class="sxs-lookup"><span data-stu-id="2e99a-138">These transactions aren't dated.</span></span> <span data-ttu-id="2e99a-139">Une transaction a le statut **Physique réservé** et l’autre a le statut **Commandé**.</span><span class="sxs-lookup"><span data-stu-id="2e99a-139">One transaction has a status of **Reserved physical**, and the other transaction has a status of **Ordered**.</span></span>

### <a name="reported-as-finished"></a><span data-ttu-id="2e99a-140">Déclaré terminé</span><span class="sxs-lookup"><span data-stu-id="2e99a-140">Reported as finished</span></span>

<span data-ttu-id="2e99a-141">Pour signaler un ordre de contrôle commencé comme terminé, ouvrez la commande et sélectionnez **Signaler comme terminé** dans le volet Actions.</span><span class="sxs-lookup"><span data-stu-id="2e99a-141">To report a started quarantine order as finished, open the order, and select **Report as finished** on the Action Pane.</span></span> <span data-ttu-id="2e99a-142">L’article n’est plus sous contrôle, mais il n’est pas encore replacé dans l’entrepôt ordinaire.</span><span class="sxs-lookup"><span data-stu-id="2e99a-142">The item is released from quarantine, but it isn't yet moved back to the regular warehouse.</span></span> <span data-ttu-id="2e99a-143">Le mouvement vers l’entrepôt ordinaire peut être traité via un journal des arrivées d’articles pouvant être initialisé lors de l’état dans le cadre du processus de déclaration de fin.</span><span class="sxs-lookup"><span data-stu-id="2e99a-143">The movement back to the regular warehouse can be processed via an item arrival journal that can be initialized during the report as finished process.</span></span>

### <a name="ended"></a><span data-ttu-id="2e99a-144">Terminé</span><span class="sxs-lookup"><span data-stu-id="2e99a-144">Ended</span></span>

<span data-ttu-id="2e99a-145">Lorsqu’un ordre de contrôle prend fin, l’article est déplacé de l’entrepôt de contrôle vers l’entrepôt ordinaire.</span><span class="sxs-lookup"><span data-stu-id="2e99a-145">When a quarantine order is ended, the item is moved from the quarantine warehouse back to the regular warehouse.</span></span> <span data-ttu-id="2e99a-146">Le statut de la transaction d’article est défini sur *Vendu* au niveau de l’entrepôt de contrôle et sur *Acheté* au niveau de l’entrepôt ordinaire.</span><span class="sxs-lookup"><span data-stu-id="2e99a-146">The status of the item transaction is set to *Sold* at the quarantine warehouse and *Purchased* at the regular warehouse.</span></span>

## <a name="quarantine-order-scrap"></a><span data-ttu-id="2e99a-147">Rebut d’ordre de contrôle</span><span class="sxs-lookup"><span data-stu-id="2e99a-147">Quarantine order scrap</span></span>

<span data-ttu-id="2e99a-148">Dans le cadre du processus d’ordre de contrôle, vous pouvez mettre le stock au rebut.</span><span class="sxs-lookup"><span data-stu-id="2e99a-148">As part of the quarantine order process, you can scrap inventory.</span></span> <span data-ttu-id="2e99a-149">Lors du traitement d’une mise au rebut, le statut du stock est défini sur *Vendu* par une transaction de sortie de l’entrepôt de contrôle.</span><span class="sxs-lookup"><span data-stu-id="2e99a-149">When you process scrap, the status of the inventory is set to *Sold* by an issue transaction from the quarantine warehouse.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="2e99a-150">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="2e99a-150">Additional resources</span></span>

- [<span data-ttu-id="2e99a-151">Blocage du stock</span><span class="sxs-lookup"><span data-stu-id="2e99a-151">Inventory blocking</span></span>](inventory-blocking.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
