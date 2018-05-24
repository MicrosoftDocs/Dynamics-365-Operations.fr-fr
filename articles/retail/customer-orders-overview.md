---
title: Vue d'ensemble des commandes client
description: "Cette rubrique fournit des informations sur les commandes client dans Retail Modern POS (MPOS). Les commandes client sont également appelées commandes spéciales. La rubrique inclut une discussion sur les paramètres associés et les flux de transaction."
author: josaw1
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
ms.search.form: RetailFunctionalityProfile
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 260594
ms.assetid: 6fc835ef-d62e-4f23-9d49-50299be642ca
ms.search.region: global
ms.search.industry: Retail
ms.author: anpurush
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: f46cf7d4df4a8cb0ad1846882292965aa492239b
ms.contentlocale: fr-fr
ms.lasthandoff: 05/08/2018

---

# <a name="customer-orders-overview"></a><span data-ttu-id="966f7-105">Vue d'ensemble des commandes client</span><span class="sxs-lookup"><span data-stu-id="966f7-105">Customer orders overview</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="966f7-106">Cette rubrique fournit des informations sur les commandes client dans Retail Modern POS (MPOS).</span><span class="sxs-lookup"><span data-stu-id="966f7-106">This topic provides information about customer orders in Retail Modern POS (MPOS).</span></span> <span data-ttu-id="966f7-107">Les commandes client sont également appelées commandes spéciales.</span><span class="sxs-lookup"><span data-stu-id="966f7-107">Customer orders are also known as special orders.</span></span> <span data-ttu-id="966f7-108">La rubrique inclut une discussion sur les paramètres associés et les flux de transaction.</span><span class="sxs-lookup"><span data-stu-id="966f7-108">The topic includes a discussion of related parameters and transaction flows.</span></span>

<span data-ttu-id="966f7-109">Dans le monde de la vente au détail dans plusieurs canaux, de nombreux détaillants offrent la possibilité que les commandes client ou les commandes spéciales répondent à diverses exigences de produit et de traitement.</span><span class="sxs-lookup"><span data-stu-id="966f7-109">In an omni-channel retail world, many retailers provide the option of customer orders, or special orders, to meet various product and fulfillment requirements.</span></span> <span data-ttu-id="966f7-110">Voici quelques scénarios classiques :</span><span class="sxs-lookup"><span data-stu-id="966f7-110">Here are some typical scenarios:</span></span>

-   <span data-ttu-id="966f7-111">Un client souhaite que les produits soient livrés à une adresse spécifique à une date spécifique.</span><span class="sxs-lookup"><span data-stu-id="966f7-111">A customer wants products to be delivered to a specific address on a specific date.</span></span>
-   <span data-ttu-id="966f7-112">Un client souhaite prélever les produits dans un magasin ou un emplacement qui diffère du magasin ou de l'emplacement où il a acheté ces produits.</span><span class="sxs-lookup"><span data-stu-id="966f7-112">A customer wants to pick up products from a store or location that differs from the store or location where the customer purchased those products.</span></span>
-   <span data-ttu-id="966f7-113">Un client souhaite qu'une autre personne prélève les produits qu'il a achetés.</span><span class="sxs-lookup"><span data-stu-id="966f7-113">A customer wants someone else to pick up products that the customer purchased.</span></span>

<span data-ttu-id="966f7-114">Les détaillants utilisent également les commandes client pour réduire les ventes perdues que les pénuries de stock peuvent causer, car les marchandises peuvent être livrées ou prélevées à un autre moment ou emplacement.</span><span class="sxs-lookup"><span data-stu-id="966f7-114">Retailers also use customer orders to minimize lost sales that stock outages might otherwise cause, because the merchandise can be delivered or picked up at a different time or place.</span></span>

## <a name="set-up-customer-orders"></a><span data-ttu-id="966f7-115">Paramétrer les commandes client</span><span class="sxs-lookup"><span data-stu-id="966f7-115">Set up customer orders</span></span>
<span data-ttu-id="966f7-116">Voici quelques paramètres qui peuvent être définis dans la page **Paramètres des ventes au détail** pour définir la façon dont les commandes client sont honorées :</span><span class="sxs-lookup"><span data-stu-id="966f7-116">Here are some of the parameters that can be set on the **Retail parameters** page to define how customer orders are fulfilled:</span></span>

-   <span data-ttu-id="966f7-117">**Pourcentage de dépôt par défaut** – Spécifiez le montant que le client doit payer comme dépôt avant qu'un ordre puisse être confirmé.</span><span class="sxs-lookup"><span data-stu-id="966f7-117">**Default deposit percentage** – Specify the amount that the customer must pay as a deposit before an order can be confirmed.</span></span> <span data-ttu-id="966f7-118">Le montant de dépôt par défaut est calculé sous forme de pourcentage de la valeur de la commande.</span><span class="sxs-lookup"><span data-stu-id="966f7-118">The default deposit amount is calculated as a percentage of the order value.</span></span> <span data-ttu-id="966f7-119">Selon les privilèges, un associé du magasin peut remplacer le montant à l'aide de l'option **Remplacement de dépôt**.</span><span class="sxs-lookup"><span data-stu-id="966f7-119">Depending on privileges, a store associate might be able to override the amount by using **Deposit override**.</span></span>
-   <span data-ttu-id="966f7-120">**Pourcentage de frais d'annulation** – Si des frais sont appliqués lorsqu'une commande client est annulée, spécifiez le montant de ces frais.</span><span class="sxs-lookup"><span data-stu-id="966f7-120">**Cancellation charge percentage** – If a charge will be applied when a customer order is canceled, specify the amount of that charge.</span></span>
-   <span data-ttu-id="966f7-121">**Code frais d'annulation** – Si des frais sont appliqués lorsqu'une commande client est annulée, ces frais sont indiqués dans un code frais sur la commande client.</span><span class="sxs-lookup"><span data-stu-id="966f7-121">**Cancellation charge code** – If a charge will be applied when a customer order is canceled, that charge will be reflected under a charge code on the sales order.</span></span> <span data-ttu-id="966f7-122">Utilisez ce paramètre pour définir un code frais d'annulation.</span><span class="sxs-lookup"><span data-stu-id="966f7-122">Use this parameter to define the cancellation charge code.</span></span>
-   <span data-ttu-id="966f7-123">**Code frais d'expédition** – Les détaillants peuvent facturer des frais supplémentaires pour expédier les marchandises à un client.</span><span class="sxs-lookup"><span data-stu-id="966f7-123">**Shipping charge code** – Retailers can charge an extra fee for shipping merchandise to a customer.</span></span> <span data-ttu-id="966f7-124">Le montant de ces frais d'expédition sera indiqué dans un code frais sur la commande client.</span><span class="sxs-lookup"><span data-stu-id="966f7-124">The amount of that shipping charge will be reflected under a charge code on the sales order.</span></span> <span data-ttu-id="966f7-125">Utilisez ce paramètre pour mettre en correspondance le code frais d'expédition avec les frais d'expédition de la commande client.</span><span class="sxs-lookup"><span data-stu-id="966f7-125">Use this parameter to map the shipping charge code to shipping charges on the customer order.</span></span>
-   <span data-ttu-id="966f7-126">**Rembourser les frais d'expédition** – Spécifiez si les frais d'expédition associés à une commande client sont remboursables.</span><span class="sxs-lookup"><span data-stu-id="966f7-126">**Refund shipping charges** – Specify whether shipping charges that are associated with a customer order are refundable.</span></span>
-   <span data-ttu-id="966f7-127">**Montant maximal sans approbation** – Si les frais d'expédition sont remboursables, spécifiez le montant maximal du remboursement des frais d'expédition pour plusieurs ordres de retour.</span><span class="sxs-lookup"><span data-stu-id="966f7-127">**Maximum amount without approval** – If shipping charges are refundable, specify the maximum amount of shipping charge refunds across return orders.</span></span> <span data-ttu-id="966f7-128">Si ce montant est dépassé, le remplacement par le responsable est nécessaire pour procéder au remboursement.</span><span class="sxs-lookup"><span data-stu-id="966f7-128">If this amount is exceeded, manager override is required in order to continue with the refund.</span></span> <span data-ttu-id="966f7-129">Pour prendre en charge les scénarios suivants, le remboursement des frais d'expédition peut dépasser le montant initialement payé :</span><span class="sxs-lookup"><span data-stu-id="966f7-129">To accommodate the following scenarios, a refund of shipping charges can exceed the amount that was originally paid:</span></span>
    -   <span data-ttu-id="966f7-130">Les frais sont appliqués au niveau de l'en-tête de commande client et, lorsqu'une certaine quantité d'une ligne de produit est renvoyée, le remboursement maximal des frais d'expédition qui est autorisé pour les produits et la quantité ne peut pas être déterminé de manière appropriée pour tous les clients de vente au détail.</span><span class="sxs-lookup"><span data-stu-id="966f7-130">Charges are applied at the level of the sales order header, and when some quantity of a product line is returned, the maximum refund of shipping charges that is allowed for the products and the quantity can't be determined in way that works for all retail customers.</span></span>
    -   <span data-ttu-id="966f7-131">Des frais d'expédition sont générés pour chaque instance d'expédition.</span><span class="sxs-lookup"><span data-stu-id="966f7-131">Shipping charges are incurred for every instance of shipping.</span></span> <span data-ttu-id="966f7-132">Si un client retourne des produits à plusieurs reprises, et la stratégie du détaillant spécifie que le coût des frais d'expédition de retour sera à la charge du détaillant, les frais d'expédition de retour seront supérieurs aux frais d'expédition réels.</span><span class="sxs-lookup"><span data-stu-id="966f7-132">If a customer returns products multiple times, and the retailer’s policy specifies that the retailer will bear the cost of return shipping charges, the return shipping charges will be more than the actual shipping charges.</span></span>

## <a name="transaction-flow-for-customer-orders"></a><span data-ttu-id="966f7-133">Flux de transaction pour les commandes client</span><span class="sxs-lookup"><span data-stu-id="966f7-133">Transaction flow for customer orders</span></span>
### <a name="create-a-customer-order-in-retail-modern-pos"></a><span data-ttu-id="966f7-134">Créer une commande client dans Retail Modern POS</span><span class="sxs-lookup"><span data-stu-id="966f7-134">Create a customer order in Retail Modern POS</span></span>

1.  <span data-ttu-id="966f7-135">Ajoutez un client à la transaction.</span><span class="sxs-lookup"><span data-stu-id="966f7-135">Add a customer to the transaction.</span></span>
2.  <span data-ttu-id="966f7-136">Ajoutez des produits dans le chariot.</span><span class="sxs-lookup"><span data-stu-id="966f7-136">Add products to the cart.</span></span>
3.  <span data-ttu-id="966f7-137">Cliquez sur **Créer une commande client**, puis sélectionnez le type de commande.</span><span class="sxs-lookup"><span data-stu-id="966f7-137">Click **Create customer order**, and then select the order type.</span></span> <span data-ttu-id="966f7-138">Le type de commande peut être **Commande client** ou **Devis**.</span><span class="sxs-lookup"><span data-stu-id="966f7-138">The order type can be either **Customer order** or **Quote**.</span></span>
4.  <span data-ttu-id="966f7-139">Cliquez sur **Expédition sélectionnée** ou sur **Expédier tout** pour expédier les produits à une adresse indiquée sur le compte client, spécifier la date d'expédition demandée et spécifier les frais d'expédition.</span><span class="sxs-lookup"><span data-stu-id="966f7-139">Click **Ship selected** or **Ship all** to ship the products to an address on the customer account, specify the requested shipping date, and specify shipping charges.</span></span>
5.  <span data-ttu-id="966f7-140">Cliquez sur **Prélèvement sélectionné** ou sur **Prélever tout** pour sélectionner les produits qui seront prélevés du magasin actuel ou d'un autre magasin à une date spécifique.</span><span class="sxs-lookup"><span data-stu-id="966f7-140">Click **Pick up selected** or **Pick-up all** to select products that will be picked up from the current store or a different store on a specific date.</span></span>
6.  <span data-ttu-id="966f7-141">Prélevez le montant de dépôt, si un dépôt est requis.</span><span class="sxs-lookup"><span data-stu-id="966f7-141">Collect the deposit amount, if a deposit is required.</span></span>

### <a name="edit-an-existing-customer-order"></a><span data-ttu-id="966f7-142">Modifier une commande client existante</span><span class="sxs-lookup"><span data-stu-id="966f7-142">Edit an existing customer order</span></span>

1.  <span data-ttu-id="966f7-143">Sur la page d'accueil, cliquez sur **Rechercher une commande**.</span><span class="sxs-lookup"><span data-stu-id="966f7-143">On the home page, click **Find an order**.</span></span>
2.  <span data-ttu-id="966f7-144">Recherchez et sélectionnez la commande à modifier.</span><span class="sxs-lookup"><span data-stu-id="966f7-144">Find and select the order to edit.</span></span> <span data-ttu-id="966f7-145">En bas de la page, cliquez sur **Modifier**.</span><span class="sxs-lookup"><span data-stu-id="966f7-145">At the bottom of the page, click the **Edit**.</span></span>

### <a name="pick-up-an-order"></a><span data-ttu-id="966f7-146">Prélever une commande</span><span class="sxs-lookup"><span data-stu-id="966f7-146">Pick up an order</span></span>

1.  <span data-ttu-id="966f7-147">Sur la page d'accueil, cliquez sur **Rechercher une commande**.</span><span class="sxs-lookup"><span data-stu-id="966f7-147">On the home page, click **Find an order**.</span></span>
2.  <span data-ttu-id="966f7-148">Sélectionnez la commande à prélever.</span><span class="sxs-lookup"><span data-stu-id="966f7-148">Select the order to pick up.</span></span> <span data-ttu-id="966f7-149">En bas de la page, cliquez sur **Prélèvement et conditionnement**.</span><span class="sxs-lookup"><span data-stu-id="966f7-149">At the bottom of the page, click **Picking and packing**.</span></span>
3.  <span data-ttu-id="966f7-150">Cliquez sur **Prélever**.</span><span class="sxs-lookup"><span data-stu-id="966f7-150">Click **Pick up**.</span></span>

### <a name="cancel-an-order"></a><span data-ttu-id="966f7-151">Annuler une commande</span><span class="sxs-lookup"><span data-stu-id="966f7-151">Cancel an order</span></span>

1.  <span data-ttu-id="966f7-152">Sur la page d'accueil, cliquez sur **Rechercher une commande**.</span><span class="sxs-lookup"><span data-stu-id="966f7-152">On the home page, click **Find an order**.</span></span>
2.  <span data-ttu-id="966f7-153">Sélectionnez la commande à annuler.</span><span class="sxs-lookup"><span data-stu-id="966f7-153">Select the order to cancel.</span></span> <span data-ttu-id="966f7-154">En bas de la page, cliquez sur **Annuler**.</span><span class="sxs-lookup"><span data-stu-id="966f7-154">At the bottom of the page, click **Cancel**.</span></span>

#### <a name="create-a-return-order"></a><span data-ttu-id="966f7-155">Créer un ordre de retour</span><span class="sxs-lookup"><span data-stu-id="966f7-155">Create a return order</span></span>

1.  <span data-ttu-id="966f7-156">Sur la page d'accueil, cliquez sur **Rechercher une commande**.</span><span class="sxs-lookup"><span data-stu-id="966f7-156">On the home page, click **Find an order**.</span></span>
2.  <span data-ttu-id="966f7-157">Sélectionnez la commande à retourner, sélectionnez la facture pour la commande, puis sélectionnez la ligne de produit pour les marchandises à retourner.</span><span class="sxs-lookup"><span data-stu-id="966f7-157">Select the order to return, select the invoice for the order, and then select the product line for the merchandise to return.</span></span>
3.  <span data-ttu-id="966f7-158">En bas de la page, cliquez sur **Ordre de retour**.</span><span class="sxs-lookup"><span data-stu-id="966f7-158">At the bottom of the page, click the **Return order**.</span></span>

## <a name="asynchronous-transaction-flow-for-customer-orders"></a><span data-ttu-id="966f7-159">Flux de transaction asynchrone pour les commandes client</span><span class="sxs-lookup"><span data-stu-id="966f7-159">Asynchronous transaction flow for customer orders</span></span>
<span data-ttu-id="966f7-160">Les commandes client peuvent être créées à partir du client de point de vente (PDV) en mode synchrone ou asynchrone.</span><span class="sxs-lookup"><span data-stu-id="966f7-160">Customer orders can be created from the point of sale (POS) client in either synchronous mode or asynchronous mode.</span></span>

### <a name="enable-customer-orders-to-be-created-in-asynchronous-mode"></a><span data-ttu-id="966f7-161">Activer les commandes client à créer en mode asynchrone</span><span class="sxs-lookup"><span data-stu-id="966f7-161">Enable customer orders to be created in asynchronous mode</span></span>

1.  <span data-ttu-id="966f7-162">Cliquez sur **Vente au détail** &gt; **Paramétrage du canal** &gt; **Paramétrage POS** &gt; **Profil POS** &gt; **Profils de fonctionnalité**.</span><span class="sxs-lookup"><span data-stu-id="966f7-162">Click **Retail** &gt; **Channel setup** &gt; **POS setup** &gt; **POS profile** &gt; **Functionality profiles**.</span></span>
2.  <span data-ttu-id="966f7-163">Dans l'organisateur **Général**, définissez l'option **Créer une commande client en mode asynchrone** sur **Oui**.</span><span class="sxs-lookup"><span data-stu-id="966f7-163">On the **General** FastTab, set the **Create customer order in async mode** option to **Yes**.</span></span>

<span data-ttu-id="966f7-164">Lorsque l'option **Créer une commande client en mode asynchrone** est définie sur **Oui**, les commandes client sont toujours créées en mode asynchrone, même si Retail Transaction Service (RTS) est disponible.</span><span class="sxs-lookup"><span data-stu-id="966f7-164">When the **Create customer order in async mode** option is set to **Yes**, customer orders are always created in asynchronous mode, even if Retail Transaction Service (RTS) is available.</span></span> <span data-ttu-id="966f7-165">Si vous définissez cette option sur **Non**, les commandes client sont toujours créées en mode synchrone à l'aide de RTS.</span><span class="sxs-lookup"><span data-stu-id="966f7-165">If you set this option to **No**, customer orders are always created in synchronous mode by using RTS.</span></span> <span data-ttu-id="966f7-166">Lorsque les commandes client sont créées en mode asynchrone, elles sont extraites et insérées dans Dynamics AX par les tâches de traction Retail (P).</span><span class="sxs-lookup"><span data-stu-id="966f7-166">When customer orders are created in asynchronous mode, they are pulled and inserted into Retail by Pull (P) jobs.</span></span> <span data-ttu-id="966f7-167">Les commandes client correspondantes sont créées dans Retail lorsque l'option **Synchroniser les commandes** est exécutée manuellement ou via un processus de traitement par lots.</span><span class="sxs-lookup"><span data-stu-id="966f7-167">The corresponding sales orders are created in Retail when **Synchronize orders** is run either manually or through a batch process.</span></span>

<a name="additional-resources"></a><span data-ttu-id="966f7-168">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="966f7-168">Additional resources</span></span>
--------

[<span data-ttu-id="966f7-169">Commandes client hybrides</span><span class="sxs-lookup"><span data-stu-id="966f7-169">Hybrid customer orders</span></span>](hybrid-customer-orders.md)




