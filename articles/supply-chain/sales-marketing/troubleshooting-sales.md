---
title: Résoudre les problèmes liés aux commandes client
description: Cette rubrique décrit comment résoudre les problèmes que vous pourriez rencontrer lors de l’utilisation des commandes client.
author: SmithaNataraj
ms.date: 09/16/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SalesTable, SalesTableListPage, SalesTableListPage_SalesCancelOrder
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: smnatara
ms.search.validFrom: 2020-9-16
ms.dyn365.ops.version: Release 10.0.14
ms.openlocfilehash: b5389b0d5a8ff68a3c16dedd2d8bb62f6e99af4f
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5824724"
---
# <a name="troubleshoot-sales-orders"></a><span data-ttu-id="a97a4-103">Résoudre les problèmes liés aux commandes client</span><span class="sxs-lookup"><span data-stu-id="a97a4-103">Troubleshoot sales orders</span></span>

<span data-ttu-id="a97a4-104">Cette rubrique décrit comment résoudre les problèmes que vous pourriez rencontrer lors de l’utilisation des commandes client.</span><span class="sxs-lookup"><span data-stu-id="a97a4-104">This topic describes how to fix issues that you might encounter while you work with sales orders.</span></span>

## <a name="the-tax-information-isnt-updated-if-i-change-the-location-on-a-sales-order-header"></a><span data-ttu-id="a97a4-105">Les informations fiscales ne sont pas mises à jour si je modifie l’emplacement sur un en-tête de commande client.</span><span class="sxs-lookup"><span data-stu-id="a97a4-105">The tax information isn't updated if I change the location on a sales order header.</span></span>

### <a name="issue-description"></a><span data-ttu-id="a97a4-106">Description du problème</span><span class="sxs-lookup"><span data-stu-id="a97a4-106">Issue description</span></span>

<span data-ttu-id="a97a4-107">Si le site, l’entrepôt ou l’adresse de livraison est modifiée sur un en-tête de commande client ou au niveau de la ligne, les informations fiscales concernées ne sont pas automatiquement mises à jour pour les lignes.</span><span class="sxs-lookup"><span data-stu-id="a97a4-107">If the site, warehouse, or delivery address is changed either on a sales order header or at the line level, the case tax information isn't automatically updated for the lines.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="a97a4-108">Résolution du problème</span><span class="sxs-lookup"><span data-stu-id="a97a4-108">Issue resolution</span></span>

<span data-ttu-id="a97a4-109">Ce comportement est fait exprès.</span><span class="sxs-lookup"><span data-stu-id="a97a4-109">This behavior is by design.</span></span> <span data-ttu-id="a97a4-110">Le problème se produit car l’adresse de livraison, le site et l’entrepôt ne sont pas non plus automatiquement modifiés au niveau de la ligne.</span><span class="sxs-lookup"><span data-stu-id="a97a4-110">The issue occurs because the delivery address, site, and warehouse aren't automatically changed at the line level either.</span></span> <span data-ttu-id="a97a4-111">Vous devez les mettre à jour manuellement.</span><span class="sxs-lookup"><span data-stu-id="a97a4-111">You must update them manually.</span></span>

## <a name="if-there-are-two-trade-agreements-for-the-same-period-or-overlapping-periods-the-same-agreement-line-is-always-selected"></a><span data-ttu-id="a97a4-112">S’il existe deux accords commerciaux pour la même période ou des périodes qui se chevauchent, la même ligne d’accord est toujours sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="a97a4-112">If there are two trade agreements for the same period or overlapping periods, the same agreement line is always selected.</span></span>

### <a name="issue-description"></a><span data-ttu-id="a97a4-113">Description du problème</span><span class="sxs-lookup"><span data-stu-id="a97a4-113">Issue description</span></span>

<span data-ttu-id="a97a4-114">Si deux accords commerciaux sont définis pour la même période ou des périodes qui se chevauchent, le même accord commercial semble être sélectionné à chaque fois que vous créez des lignes de commande client contenant ces articles.</span><span class="sxs-lookup"><span data-stu-id="a97a4-114">If two trade agreements are defined for the same period or overlapping periods, the same trade agreement seems to be selected every time when you create sales order lines that contain those items.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="a97a4-115">Résolution du problème</span><span class="sxs-lookup"><span data-stu-id="a97a4-115">Issue resolution</span></span>

<span data-ttu-id="a97a4-116">S’il y a plus d’un accord commercial pour une date donnée, l’accord commercial qui a le prix le plus bas est toujours sélectionné.</span><span class="sxs-lookup"><span data-stu-id="a97a4-116">If there is more than one trade agreement for a given date, the trade agreement that has the lowest price is always selected.</span></span> <span data-ttu-id="a97a4-117">Pour plus d’informations, téléchargez le livre blanc suivant : [Accords commerciaux dans Microsoft Dynamics AX 2012](https://www.axug.com/HigherLogic/System/DownloadDocumentFile.ashx?DocumentFileKey=3396a3a8-1f48-4d85-8cd6-5fa982f62e90).</span><span class="sxs-lookup"><span data-stu-id="a97a4-117">For more information, download the following white paper: [Trade agreements in Microsoft Dynamics AX 2012](https://www.axug.com/HigherLogic/System/DownloadDocumentFile.ashx?DocumentFileKey=3396a3a8-1f48-4d85-8cd6-5fa982f62e90).</span></span>

## <a name="can-i-link-a-purchase-order-to-a-sales-order-to-fulfill-demand"></a><span data-ttu-id="a97a4-118">Puis-je lier une commande fournisseur à une commande client pour répondre à la demande ?</span><span class="sxs-lookup"><span data-stu-id="a97a4-118">Can I link a purchase order to a sales order to fulfill demand?</span></span>

<span data-ttu-id="a97a4-119">Vous pouvez créer une commande fournisseur à partir d’une commande client.</span><span class="sxs-lookup"><span data-stu-id="a97a4-119">You can create a purchase order from a sales order.</span></span> <span data-ttu-id="a97a4-120">Pour plus d’informations, voir [Créer une commande fournisseur à partir d’une commande client](tasks/create-purchase-order-sales-order.md).</span><span class="sxs-lookup"><span data-stu-id="a97a4-120">For more information, see [Create a purchase order from a sales order](tasks/create-purchase-order-sales-order.md).</span></span>

## <a name="i-cant-cancel-or-delete-a-return-order-or-a-sales-order"></a><span data-ttu-id="a97a4-121">Je ne peux pas annuler ou supprimer un ordre de retour ou une commande client.</span><span class="sxs-lookup"><span data-stu-id="a97a4-121">I can't cancel or delete a return order or a sales order.</span></span>

<span data-ttu-id="a97a4-122">Vous ne pouvez annuler que les commandes client et les ordres de retour qui se trouvent dans l’état *Créé*.</span><span class="sxs-lookup"><span data-stu-id="a97a4-122">You can cancel only sales orders and return orders that are in a *Created* state.</span></span> <span data-ttu-id="a97a4-123">Pour plus d’informations, voir [Annuler un ordre de retour](../service-management/cancel-return-order.md).</span><span class="sxs-lookup"><span data-stu-id="a97a4-123">For more information, see [Cancel a return order](../service-management/cancel-return-order.md).</span></span>

## <a name="when-i-try-to-cancel-a-sales-order-i-receive-a-reservations-cannot-be-removed-because-there-is-work-created-which-relies-on-the-reservations-error"></a><span data-ttu-id="a97a4-124">Lorsque j’essaie d’annuler une commande client, je reçois le message d’erreur "Impossible de supprimer les réservations, car un travail qui a été créé repose sur ces réservations".</span><span class="sxs-lookup"><span data-stu-id="a97a4-124">When I try to cancel a sales order, I receive a "Reservations cannot be removed because there is work created which relies on the reservations" error.</span></span>

<span data-ttu-id="a97a4-125">Code d’erreur : WAX4661</span><span class="sxs-lookup"><span data-stu-id="a97a4-125">Error code: WAX4661</span></span>

<span data-ttu-id="a97a4-126">Si le travail est associé à une commande client, vous ne pouvez pas annuler la commande client tant que le travail n’est pas annulé et contrepassé.</span><span class="sxs-lookup"><span data-stu-id="a97a4-126">If work is associated with a sales order, you can't cancel the sales order until the work is canceled and reversed.</span></span> <span data-ttu-id="a97a4-127">Cette exigence s’applique même si le travail associé à la commande client est clôturé.</span><span class="sxs-lookup"><span data-stu-id="a97a4-127">This requirement applies even if the work that is associated with the sales order is closed.</span></span>

<span data-ttu-id="a97a4-128">Pour régler ce problème, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="a97a4-128">To fix this issue, follow these steps.</span></span>

1. <span data-ttu-id="a97a4-129">Annulez le travail et remettez le stock à l’emplacement souhaité.</span><span class="sxs-lookup"><span data-stu-id="a97a4-129">Cancel the work, and put inventory back into the desired location.</span></span> <span data-ttu-id="a97a4-130">Accédez au chargement approprié de la commande client et sélectionnez soit **Réduisez la quantité prélevée** sur la ligne de chargement ou **Contrepasser le travail** sur le volet Actions.</span><span class="sxs-lookup"><span data-stu-id="a97a4-130">Go to the relevant load of the sales order, and select either **Reduce picked quantity** on the load line or **Reverse work** on the Action Pane.</span></span>

    <span data-ttu-id="a97a4-131">Le travail a maintenant un statut *Annulé*, et un nouveau travail de mouvement de stock est automatiquement créé et traité pour remettre le stock à l’emplacement qui a été décrit au moment de l’annulation.</span><span class="sxs-lookup"><span data-stu-id="a97a4-131">The work now has a status of *Canceled*, and new inventory movement work is automatically created and processed to put inventory back into the location that was described at the time of reversal.</span></span>

2. <span data-ttu-id="a97a4-132">Supprimez le chargement.</span><span class="sxs-lookup"><span data-stu-id="a97a4-132">Delete the load.</span></span> <span data-ttu-id="a97a4-133">L’expédition est également supprimée.</span><span class="sxs-lookup"><span data-stu-id="a97a4-133">The shipment is also deleted.</span></span>
3. <span data-ttu-id="a97a4-134">Vous devriez maintenant pouvoir accéder à la commande client et l’annuler.</span><span class="sxs-lookup"><span data-stu-id="a97a4-134">You should now be able to go to the sales order and cancel it.</span></span>

## <a name="i-cant-cancel-an-intercompany-purchase-order-that-is-linked-to-a-sales-order"></a><span data-ttu-id="a97a4-135">Je ne peux pas annuler une commande fournisseur intersociétés liée à une commande client.</span><span class="sxs-lookup"><span data-stu-id="a97a4-135">I can't cancel an intercompany purchase order that is linked to a sales order.</span></span>

### <a name="issue-description"></a><span data-ttu-id="a97a4-136">Description du problème</span><span class="sxs-lookup"><span data-stu-id="a97a4-136">Issue description</span></span>

<span data-ttu-id="a97a4-137">Si vous essayez d’annuler une commande fournisseur intersociétés liée à une commande client, le message d’erreur suivant peut s’afficher : "Impossible de réduire la quantité en raison du changement de signe de la quantité de mise à jour restante".</span><span class="sxs-lookup"><span data-stu-id="a97a4-137">If you try to cancel an intercompany purchase order that is linked to a sales order, you might receive the following error message: "Quantity cannot be reduced because the remaining update quantity changes sign."</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="a97a4-138">Résolution du problème</span><span class="sxs-lookup"><span data-stu-id="a97a4-138">Issue resolution</span></span>

<span data-ttu-id="a97a4-139">Ce problème a été résolu dans Microsoft Dynamics 365 Supply Chain Management version 10.0.13.</span><span class="sxs-lookup"><span data-stu-id="a97a4-139">This issue was fixed in Microsoft Dynamics 365 Supply Chain Management version 10.0.13.</span></span> <span data-ttu-id="a97a4-140">Dans cette version et les versions ultérieures, vous pouvez désormais annuler une commande fournisseur intersociétés liée à une commande client.</span><span class="sxs-lookup"><span data-stu-id="a97a4-140">In that version and later versions, you can now cancel an intercompany purchase order that is linked to a sales order.</span></span>

## <a name="can-i-restore-an-invoiced-sales-order-that-was-deleted"></a><span data-ttu-id="a97a4-141">Puis-je restaurer une commande client facturée qui a été supprimée ?</span><span class="sxs-lookup"><span data-stu-id="a97a4-141">Can I restore an invoiced sales order that was deleted?</span></span>

### <a name="issue-description"></a><span data-ttu-id="a97a4-142">Description du problème</span><span class="sxs-lookup"><span data-stu-id="a97a4-142">Issue description</span></span>

<span data-ttu-id="a97a4-143">Une commande client facturée a été supprimée par erreur et vous souhaitez la restaurer ou en afficher les détails.</span><span class="sxs-lookup"><span data-stu-id="a97a4-143">An invoiced sales order was deleted by mistake, and you want to restore it or view its details.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="a97a4-144">Résolution du problème</span><span class="sxs-lookup"><span data-stu-id="a97a4-144">Issue resolution</span></span>

<span data-ttu-id="a97a4-145">Si la commande client supprimée a déjà été facturée, accédez à **Compte client \> Transactions \> Document original \> Voir les détails**.</span><span class="sxs-lookup"><span data-stu-id="a97a4-145">If the deleted sales order has already been invoiced, go to **Customer account \> Transactions \> Original document \> View details**.</span></span> <span data-ttu-id="a97a4-146">Recherchez la facture que vous recherchez et sélectionnez-la pour afficher ses détails.</span><span class="sxs-lookup"><span data-stu-id="a97a4-146">Find the invoice that you're looking for, and select it to view its details.</span></span> <span data-ttu-id="a97a4-147">Ces détails incluent la référence de la commande client.</span><span class="sxs-lookup"><span data-stu-id="a97a4-147">These details include the sales order reference.</span></span> <span data-ttu-id="a97a4-148">Vous devriez également pouvoir accéder aux détails de la commande client à partir de cette page.</span><span class="sxs-lookup"><span data-stu-id="a97a4-148">You should also be able to access the sales order details from that page.</span></span>

## <a name="the-deadline-of-a-sales-order-header-cant-be-found-in-the-salesorderheaderv2entity-data-entity"></a><span data-ttu-id="a97a4-149">La date limite d’un en-tête de commande client est introuvable dans l’entité de données SalesOrderHeaderV2Entity.</span><span class="sxs-lookup"><span data-stu-id="a97a4-149">The deadline of a sales order header can't be found in the SalesOrderHeaderV2Entity data entity.</span></span>

<span data-ttu-id="a97a4-150">Le champ Date limite n’existe pas sur l’entité *SalesOrderHeaderV2Entity*.</span><span class="sxs-lookup"><span data-stu-id="a97a4-150">The deadline field doesn't exist on the *SalesOrderHeaderV2Entity* entity.</span></span>

## <a name="i-must-delete-orphaned-sales-order-records"></a><span data-ttu-id="a97a4-151">Je dois supprimer les enregistrements de commande client orphelins.</span><span class="sxs-lookup"><span data-stu-id="a97a4-151">I must delete orphaned sales order records.</span></span>

<span data-ttu-id="a97a4-152">Pour nettoyer les enregistrements de commande client orphelins, exécutez la tâche périodique *Suppression de commandes client* en accédant à l’un des emplacements suivants :</span><span class="sxs-lookup"><span data-stu-id="a97a4-152">To clean up orphaned sales order records, run the *Sales order deletion* periodic job by going to either of the following places:</span></span>

- <span data-ttu-id="a97a4-153">Ventes et marketing \> Tâches périodiques \> Nettoyage \> Supprimer des commandes clients</span><span class="sxs-lookup"><span data-stu-id="a97a4-153">Sales and marketing \> Periodic tasks \> Clean up \> Delete sales orders</span></span>
- <span data-ttu-id="a97a4-154">Retail et Commerce \> IT Retail et Commerce \> Nettoyage \> Supprimer des commandes client</span><span class="sxs-lookup"><span data-stu-id="a97a4-154">Retail and commerce \> Retail and commerce IT \> Clean up \> Delete sales orders</span></span>

## <a name="is-there-a-way-to-calculate-commissions-on-invoices-that-have-already-been-posted"></a><span data-ttu-id="a97a4-155">Existe-t-il un moyen de calculer les commissions sur les factures déjà validées ?</span><span class="sxs-lookup"><span data-stu-id="a97a4-155">Is there a way to calculate commissions on invoices that have already been posted?</span></span>

<span data-ttu-id="a97a4-156">Supply Chain Management ne prend actuellement pas en charge le calcul des commissions pour les factures validées.</span><span class="sxs-lookup"><span data-stu-id="a97a4-156">Supply Chain Management doesn't currently support the calculation of commissions for posted invoices.</span></span>

## <a name="a-bundle-item-isnt-supported-in-an-intercompany-process"></a><span data-ttu-id="a97a4-157">Un élément d’offre groupée n’est pas pris en charge dans un processus intersociétés.</span><span class="sxs-lookup"><span data-stu-id="a97a4-157">A bundle item isn't supported in an intercompany process.</span></span>

<span data-ttu-id="a97a4-158">L’élément d’offre groupée n’est pas disponible pour la commande fournisseur car, si vous examinez les lignes de commande client pour l’élément d’offre groupée, vous remarquerez que la quantité est *0* (zéro) et l’état est *Annulé*.</span><span class="sxs-lookup"><span data-stu-id="a97a4-158">The bundle item isn't available for the purchase order because, if you examine the sales order lines for the bundle item, you will notice that the quantity is *0* (zero) and the status is *Canceled*.</span></span> <span data-ttu-id="a97a4-159">Ce comportement est fait exprès.</span><span class="sxs-lookup"><span data-stu-id="a97a4-159">This behavior is by design.</span></span> <span data-ttu-id="a97a4-160">La commande client n’achète que les composants de l’élément d’offre groupée.</span><span class="sxs-lookup"><span data-stu-id="a97a4-160">The sales order buys only the components of the bundle item.</span></span> <span data-ttu-id="a97a4-161">Elle n’achète pas l’élément d’offre groupée lui-même.</span><span class="sxs-lookup"><span data-stu-id="a97a4-161">It doesn't buy the bundle item itself.</span></span>

<span data-ttu-id="a97a4-162">Si vous devez acheter une offre groupée, déterminez si vous devez la marquer comme élément d’offre groupée, car cette fonctionnalité est conçue pour les scénarios de constatation du produit.</span><span class="sxs-lookup"><span data-stu-id="a97a4-162">If you must buy a bundle, consider whether you have to mark it as bundle item, because this functionality is designed for revenue recognition scenarios.</span></span> <span data-ttu-id="a97a4-163">Pour plus d’informations sur les éléments d’offre groupée, voir [Offres groupées](../../finance/accounts-receivable/revenue-recognition-setup.md#bundles).</span><span class="sxs-lookup"><span data-stu-id="a97a4-163">For more information about bundle items, see [Bundles](../../finance/accounts-receivable/revenue-recognition-setup.md#bundles).</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]