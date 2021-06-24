---
title: La quantité ne peut pas être réduite lorsqu’une commande client est annulée
description: La quantité ne peut pas être réduite lorsqu’une commande client est annulée.
author: hja-ms
ms.date: 5/17/2021
ms.topic: troubleshooting
ms.search.form: SalesTable_SalesCancelOrder, SalesTableListPage_SalesCancelOrder
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: hja
ms.search.validFrom: 2021-05-17
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 1a2cc9c9fd3d085508fc652bc9ee0a352d869dee
ms.sourcegitcommit: a02d3d64c899f8554b74342d5a1856d824bf1abe
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/11/2021
ms.locfileid: "6230834"
---
# <a name="the-quantity-cant-be-reduced-when-a-sales-order-is-canceled"></a><span data-ttu-id="90a1b-103">La quantité ne peut pas être réduite lorsqu’une commande client est annulée</span><span class="sxs-lookup"><span data-stu-id="90a1b-103">The quantity can't be reduced when a sales order is canceled</span></span>

<span data-ttu-id="90a1b-104">Code d’erreur : SYS138831</span><span class="sxs-lookup"><span data-stu-id="90a1b-104">Error code: SYS138831</span></span>

## <a name="symptoms"></a><span data-ttu-id="90a1b-105">Symptômes</span><span class="sxs-lookup"><span data-stu-id="90a1b-105">Symptoms</span></span>

<span data-ttu-id="90a1b-106">Le système affiche le message d’erreur suivant :</span><span class="sxs-lookup"><span data-stu-id="90a1b-106">The system shows the following error message:</span></span>

> <span data-ttu-id="90a1b-107">La quantité ne peut pas être réduite.</span><span class="sxs-lookup"><span data-stu-id="90a1b-107">The quantity cannot be reduced.</span></span> <span data-ttu-id="90a1b-108">Le nombre de mouvements de stock sur la commande est trop faible car la quantité ou une partie de celle-ci est référencée par un ordre de sortie ou un ordre de fabrication ou est marquée par rapport à d’autres transactions.</span><span class="sxs-lookup"><span data-stu-id="90a1b-108">The number of inventory transactions on order is too low because the quantity or part of it is referenced by an output order or a production order or is marked against other transactions.</span></span>

## <a name="cause"></a><span data-ttu-id="90a1b-109">Cause</span><span class="sxs-lookup"><span data-stu-id="90a1b-109">Cause</span></span>

<span data-ttu-id="90a1b-110">Si le travail est associé à une commande client, vous ne pouvez pas annuler la commande client tant que le travail n’est pas annulé et contrepassé.</span><span class="sxs-lookup"><span data-stu-id="90a1b-110">If work is associated with a sales order, you can't cancel the sales order until the work is canceled and reversed.</span></span> <span data-ttu-id="90a1b-111">Cette exigence s’applique même si le travail associé à la commande client est clôturé.</span><span class="sxs-lookup"><span data-stu-id="90a1b-111">This requirement applies even if the work that is associated with the sales order is closed.</span></span>

## <a name="resolution"></a><span data-ttu-id="90a1b-112">Résolution</span><span class="sxs-lookup"><span data-stu-id="90a1b-112">Resolution</span></span>

<span data-ttu-id="90a1b-113">Pour résoudre ce problème, effectuez les tâches suivantes :</span><span class="sxs-lookup"><span data-stu-id="90a1b-113">To fix this issue, complete the following tasks:</span></span>

1. <span data-ttu-id="90a1b-114">Annulez le travail ouvert.</span><span class="sxs-lookup"><span data-stu-id="90a1b-114">Cancel open work.</span></span>
1. <span data-ttu-id="90a1b-115">Supprimez le chargement.</span><span class="sxs-lookup"><span data-stu-id="90a1b-115">Delete the load.</span></span>
1. <span data-ttu-id="90a1b-116">Réduisez la quantité prélevée.</span><span class="sxs-lookup"><span data-stu-id="90a1b-116">Reduce the picked quantity.</span></span>

### <a name="cancel-open-work"></a><span data-ttu-id="90a1b-117">Annuler le travail ouvert</span><span class="sxs-lookup"><span data-stu-id="90a1b-117">Cancel open work</span></span>

<span data-ttu-id="90a1b-118">Pour annuler le travail ouvert, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="90a1b-118">To cancel open work, follow these steps.</span></span>

1. <span data-ttu-id="90a1b-119">Allez dans **Gestion des entrepôts \> Tâches périodiques \> Nettoyer \> Annuler le travail**.</span><span class="sxs-lookup"><span data-stu-id="90a1b-119">Go to **Warehouse management \> Periodic tasks \> Clean up \> Cancel work**.</span></span>
1. <span data-ttu-id="90a1b-120">Dans le champ **ID de travail**, spécifiez l’ID de travail que vous souhaitez annuler et dont le **Statut de travail** est actuellement *Ouvert*, *En cours*, *Annulé*, *Combiné* ou *Fermé*.</span><span class="sxs-lookup"><span data-stu-id="90a1b-120">In the **Work ID** field, specify the ID of the work that you want to cancel, and that currently has a **Work status** value of *Open*, *In progress*, *Canceled*, *Combined*, or *Closed*.</span></span>
1. <span data-ttu-id="90a1b-121">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="90a1b-121">Select **OK**.</span></span>
1. <span data-ttu-id="90a1b-122">Sélectionnez **Oui** pour confirmer que vous souhaitez annuler le travail.</span><span class="sxs-lookup"><span data-stu-id="90a1b-122">Select **Yes** to confirm that you want to cancel the work.</span></span>

### <a name="delete-the-load"></a><span data-ttu-id="90a1b-123">Supprimer le chargement</span><span class="sxs-lookup"><span data-stu-id="90a1b-123">Delete the load</span></span>

<span data-ttu-id="90a1b-124">Pour supprimer un chargement, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="90a1b-124">To delete a load, follow these steps.</span></span>

1. <span data-ttu-id="90a1b-125">Accédez à **Ventes et marketing \> Commandes client \> Toutes les commandes client**.</span><span class="sxs-lookup"><span data-stu-id="90a1b-125">Go to **Sales and marketing \> Sales orders \> All sales orders**.</span></span>
1. <span data-ttu-id="90a1b-126">Ouvrez les commandes clients concernées.</span><span class="sxs-lookup"><span data-stu-id="90a1b-126">Open the relevant sales order.</span></span>
1. <span data-ttu-id="90a1b-127">Dans le raccourci **Lignes de commande client**, sélectionnez **Entrepôt \> Détails du travail**.</span><span class="sxs-lookup"><span data-stu-id="90a1b-127">On the **Sales order lines** FastTab, select **Warehouse \> Work details**.</span></span>
1. <span data-ttu-id="90a1b-128">Sur la page **Travail**, dans le volet Actions, sur l’onglet **Travail**, dans le groupe **Travail**, sélectionnez **Annuler le travail**.</span><span class="sxs-lookup"><span data-stu-id="90a1b-128">On the **Work** page, on the Action Pane, on the **Work** tab, in the **Work** group, select **Cancel work**.</span></span>
1. <span data-ttu-id="90a1b-129">Confirmez que le champ **Statut du travail** est défini sur *Annulé*.</span><span class="sxs-lookup"><span data-stu-id="90a1b-129">Confirm that the **Work status** field is set to *Canceled*.</span></span>
1. <span data-ttu-id="90a1b-130">Fermez la page **Travail**.</span><span class="sxs-lookup"><span data-stu-id="90a1b-130">Close the **Work** page.</span></span>
1. <span data-ttu-id="90a1b-131">Sur la page des détails de la commande client, dans le raccourci **Lignes de commande client**, sélectionnez **Entrepôt \> Détails du chargement**.</span><span class="sxs-lookup"><span data-stu-id="90a1b-131">On the sales order details page, on the **Sales order lines** FastTab, select **Warehouse \> Load details**.</span></span>
1. <span data-ttu-id="90a1b-132">Dans le volet Actions, sélectionnez **Supprimer**.</span><span class="sxs-lookup"><span data-stu-id="90a1b-132">On the Action Pane, select **Delete**.</span></span>
1. <span data-ttu-id="90a1b-133">Sélectionnez **Oui** pour confirmer que vous souhaitez supprimer le chargement.</span><span class="sxs-lookup"><span data-stu-id="90a1b-133">Select **Yes** to confirm that you want to delete the load.</span></span>
1. <span data-ttu-id="90a1b-134">Fermez la page **Chargement**.</span><span class="sxs-lookup"><span data-stu-id="90a1b-134">Close the **Load** page.</span></span>

### <a name="reduce-the-picked-quantity"></a><span data-ttu-id="90a1b-135">Réduire la quantité prélevée</span><span class="sxs-lookup"><span data-stu-id="90a1b-135">Reduce the picked quantity</span></span>

<span data-ttu-id="90a1b-136">Une fois tous les travaux annulés, suivez ces étapes pour réduire la quantité prélevée.</span><span class="sxs-lookup"><span data-stu-id="90a1b-136">After all work has been canceled, follow these steps to reduce the picked quantity.</span></span>

1. <span data-ttu-id="90a1b-137">Accédez à **Ventes et marketing \> Commandes client \> Toutes les commandes client**.</span><span class="sxs-lookup"><span data-stu-id="90a1b-137">Go to **Sales and marketing \> Sales orders \> All sales orders**.</span></span>
1. <span data-ttu-id="90a1b-138">Ouvrez les commandes clients concernées.</span><span class="sxs-lookup"><span data-stu-id="90a1b-138">Open the relevant sales order.</span></span>
1. <span data-ttu-id="90a1b-139">Dans le raccourci **Lignes de commande client**, sélectionnez **Mettre à jour la ligne \> Prélever** dans la barre d’outils.</span><span class="sxs-lookup"><span data-stu-id="90a1b-139">On the **Sales order lines** FastTab, select **Update line \> Pick** from the toolbar.</span></span>
1. <span data-ttu-id="90a1b-140">Sur la page **Prélever**, dans la section **Transactions**, sélectionnez la ligne où le champ **Statut de sortie** est défini sur *Prélevé*.</span><span class="sxs-lookup"><span data-stu-id="90a1b-140">On the **Pick** page, in the **Transactions** section, select the line where the **Issue status** field is set to *Picked*.</span></span>
1. <span data-ttu-id="90a1b-141">Dans la section **Transactions**, sélectionnez **Ajouter une ligne de prélèvement** dans la barre d’outils.</span><span class="sxs-lookup"><span data-stu-id="90a1b-141">In the **Transactions** section, select **Add picking line** from the toolbar.</span></span>
1. <span data-ttu-id="90a1b-142">Dans la section **Lignes de prélèvement**, sélectionnez **Confirmer Prélever tout** dans la barre d’outils.</span><span class="sxs-lookup"><span data-stu-id="90a1b-142">In the **Picking lines** section, select **Confirm pick all** from the toolbar.</span></span>
1. <span data-ttu-id="90a1b-143">Fermez la page **Prélèvement**.</span><span class="sxs-lookup"><span data-stu-id="90a1b-143">Close the **Pick** page.</span></span>
1. <span data-ttu-id="90a1b-144">Dans la page des détails de la commande, dans le volet Actions, sous l’onglet **Commande client**, dans le groupe **Tenir à jour**, sélectionnez **Annuler**.</span><span class="sxs-lookup"><span data-stu-id="90a1b-144">On the sales order details page, on the Action Pane, on the **Sales order** tab, in the **Maintain** group, select **Cancel**.</span></span>
1. <span data-ttu-id="90a1b-145">Sélectionnez **Oui** pour confirmer que vous souhaitez annuler la commande client.</span><span class="sxs-lookup"><span data-stu-id="90a1b-145">Select **Yes** to confirm that you want to cancel the sales order.</span></span>
