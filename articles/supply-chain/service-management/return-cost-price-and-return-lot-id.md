---
title: Prix de vente de retour et n° de lot de retour
description: Vous pouvez vous arranger pour que le coût des produits retournés soit égal au coût des produits au moment où vous les avez vendus au client. Pour ce faire, utilisez le champ **N° de traitement de retours**.
author: ShylaThompson
manager: tfehr
ms.date: 04/30/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ReturnTableListPage, ReturnInventTransIdLookup, ReturnItemNumLookup
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: b420c0716823f587ea3f349a5d654ace23d84f41
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5219267"
---
# <a name="return-cost-price-and-return-lot-id"></a><span data-ttu-id="e251a-104">Prix de vente de retour et n° de lot de retour</span><span class="sxs-lookup"><span data-stu-id="e251a-104">Return cost price and return lot ID</span></span>        

[!include [banner](../includes/banner.md)]



<span data-ttu-id="e251a-105">Le coût des produits renvoyés en stock est calculé à l’aide du coût actuel des produits.</span><span class="sxs-lookup"><span data-stu-id="e251a-105">The cost of products that are returned to inventory is calculated by using the current cost of the products.</span></span> <span data-ttu-id="e251a-106">Toutefois, vous pouvez vous arranger pour que le coût des produits retournés soit égal au coût des produits au moment où vous les avez vendus au client.</span><span class="sxs-lookup"><span data-stu-id="e251a-106">However, you might want the cost of the returned products to equal the cost of the products at the time when you sold the products to the customer.</span></span> <span data-ttu-id="e251a-107">Pour ce faire, utilisez le champ **N° de traitement de retours** de l’organisateur **Détails de ligne** dans l’écran **Commande client**.</span><span class="sxs-lookup"><span data-stu-id="e251a-107">You can do this by using the **Return lot ID** field on the **Line details** FastTab in the **Sales order** form.</span></span>

<span data-ttu-id="e251a-108">Prenons comme exemple le scénario suivant :</span><span class="sxs-lookup"><span data-stu-id="e251a-108">For example, consider the following scenario.</span></span> <span data-ttu-id="e251a-109">Vous facturez un client.</span><span class="sxs-lookup"><span data-stu-id="e251a-109">You invoice a customer.</span></span> <span data-ttu-id="e251a-110">Ensuite, le client vous renvoie les produits livrés.</span><span class="sxs-lookup"><span data-stu-id="e251a-110">Then, the customer returns the delivered products to you.</span></span> <span data-ttu-id="e251a-111">Vous renvoyez les produits en stock.</span><span class="sxs-lookup"><span data-stu-id="e251a-111">You return the products to stock.</span></span> <span data-ttu-id="e251a-112">Dans ce cas, lorsque vous créditez le client pour les produits retournés, le coût de ces produits est calculé à l’aide du coût actuel des produits.</span><span class="sxs-lookup"><span data-stu-id="e251a-112">In this case, when you credit the customer for the returned products, the cost of those products is calculated by using the current cost of the products.</span></span> <span data-ttu-id="e251a-113">Toutefois, si vous utilisez le champ **N° de traitement de retours**, le coût des produits retournés est calculé à l’aide du coût figurant sur la facture de la vente d’origine au client.</span><span class="sxs-lookup"><span data-stu-id="e251a-113">However, if you use the **Return lot ID** field, the cost of the returned products is calculated by using the cost on the invoice of the original sale to the customer.</span></span>

<span data-ttu-id="e251a-114">Pour utiliser un coût autre que le coût actuel pour les retours provenant d’un client, utilisez l’une des méthodes suivantes.</span><span class="sxs-lookup"><span data-stu-id="e251a-114">To use a cost other than the current cost for returns from a customer, use one of the following methods.</span></span>

## <a name="method-1-manually-enter-the-return-cost-price"></a><span data-ttu-id="e251a-115">Méthode 1 : entrez manuellement le prix de revient de retour</span><span class="sxs-lookup"><span data-stu-id="e251a-115">Method 1: Manually enter the return cost price</span></span>

<span data-ttu-id="e251a-116">Par défaut, lorsque vous ajoutez des articles à un ordre de retour, ceux-ci sont renvoyés en stock au prix de revient actuel.</span><span class="sxs-lookup"><span data-stu-id="e251a-116">By default, when you add items to a return order, the items are returned to inventory at the current cost price.</span></span> <span data-ttu-id="e251a-117">Pour spécifier un prix de revient de retour différent, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="e251a-117">To specify a different return cost price, follow these steps.</span></span>

1.  <span data-ttu-id="e251a-118">Cliquez sur **Ventes et marketing** \> **Commun** \> **Ordres de retour** \> **Tous les ordres de retour**.</span><span class="sxs-lookup"><span data-stu-id="e251a-118">Click **Sales and marketing** \> **Common** \> **Return orders** \> **All return orders**.</span></span>

2.  <span data-ttu-id="e251a-119">Dans le volet **Actions**, dans le groupe **Nouveau**, cliquez sur **Ordre de retour**.</span><span class="sxs-lookup"><span data-stu-id="e251a-119">On the **Action Pane**, in the **New** group, click **Return order**.</span></span>

3.  <span data-ttu-id="e251a-120">Dans l’écran **Créer un ordre de retour**, sélectionnez un compte client, puis cliquez sur **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="e251a-120">In the **Create return order** form, select a customer account, and then click **OK**.</span></span>

4.  <span data-ttu-id="e251a-121">Dans l’écran **Ordre de retour - Numéro de retour marchandises : %1, %2**, sélectionnez un article, puis entrez une quantité négative dans le champ **Quantité**.</span><span class="sxs-lookup"><span data-stu-id="e251a-121">In the **Return order - RMA number: %1, %2** form, select an item, and then enter a negative quantity in the **Quantity** field.</span></span>

5.  <span data-ttu-id="e251a-122">Cliquez sur l’organisateur **Détails de ligne**.</span><span class="sxs-lookup"><span data-stu-id="e251a-122">Click the **Line details** FastTab.</span></span>

6.  <span data-ttu-id="e251a-123">Sous l’onglet **Général**, entrez une valeur dans le champ **Prix de vente de retour**.</span><span class="sxs-lookup"><span data-stu-id="e251a-123">On the **General** tab, enter a value in the **Return cost price** field.</span></span> <span data-ttu-id="e251a-124">Cette valeur est utilisée lorsque les marchandises sont renvoyées en stock.</span><span class="sxs-lookup"><span data-stu-id="e251a-124">This value is used when the goods are returned to inventory.</span></span> <span data-ttu-id="e251a-125">Si vous n’entrez pas de valeur, le prix de revient actuel est utilisé lorsque les marchandises sont renvoyées en stock.</span><span class="sxs-lookup"><span data-stu-id="e251a-125">If you do not enter a value, the current cost price is used when the goods are returned to inventory.</span></span>

## <a name="method-2-automatically-generate-the-cost-price-based-on-the-customer-invoice-line"></a><span data-ttu-id="e251a-126">Méthode 2 : générez automatiquement le prix de revient en fonction de la ligne de facture client</span><span class="sxs-lookup"><span data-stu-id="e251a-126">Method 2: Automatically generate the cost price based on the customer invoice line</span></span>

<span data-ttu-id="e251a-127">Il s’agit de la méthode recommandée à utiliser pour créer des lignes de retour.</span><span class="sxs-lookup"><span data-stu-id="e251a-127">This is the preferred method to use to create return lines.</span></span> <span data-ttu-id="e251a-128">Pour utiliser le coût auquel les produits ont été vendus au client, créez un ordre de retour et spécifiez une ligne de vente à retourner.</span><span class="sxs-lookup"><span data-stu-id="e251a-128">To use the cost of the products at the time when you sold the products to the customer, create a return order and specify a sales line to return.</span></span>

1.  <span data-ttu-id="e251a-129">Cliquez sur **Ventes et marketing** \> **Commun** \> **Ordres de retour** \> **Tous les ordres de retour**.</span><span class="sxs-lookup"><span data-stu-id="e251a-129">Click **Sales and marketing** \> **Common** \> **Return orders** \> **All return orders**.</span></span>

2.  <span data-ttu-id="e251a-130">Dans le volet **Actions**, dans le groupe **Nouveau**, cliquez sur **Ordre de retour**.</span><span class="sxs-lookup"><span data-stu-id="e251a-130">On the **Action Pane**, in the **New** group, click **Return order**.</span></span>

3.  <span data-ttu-id="e251a-131">Dans l’écran **Créer un ordre de retour**, sélectionnez un compte client, puis cliquez sur **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="e251a-131">In the **Create return order** form, select a customer account, and then click **OK**.</span></span>

4.  <span data-ttu-id="e251a-132">Dans l’écran **Ordre de retour - Numéro de retour marchandises : %1, %2**, dans le **volet Actions**, cliquez sur **Rechercher une commande client**.</span><span class="sxs-lookup"><span data-stu-id="e251a-132">In the **Return order - RMA number: %1, %2** form, on the **Action Pane**, click **Find sales order**.</span></span>

5.  <span data-ttu-id="e251a-133">Dans l’écran **Rechercher une commande client**, sélectionnez la ligne de facture à retourner, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="e251a-133">In the **Find sales order** form, select the invoice line to return, and then click **OK**.</span></span>
    
    <span data-ttu-id="e251a-134">Dans l’organisateur **Détails de ligne**, sous l’onglet **Général**, le champ **N° de traitement de retours** affiche la valeur de la ligne de vente d’origine.</span><span class="sxs-lookup"><span data-stu-id="e251a-134">On the **Line details** FastTab, on the **General** tab, the **Return lot ID** field displays the value from the original sales line.</span></span> <span data-ttu-id="e251a-135">En outre, le champ **Prix de vente de retour** affiche la valeur de coût de la ligne de vente d’origine.</span><span class="sxs-lookup"><span data-stu-id="e251a-135">Additionally, the **Return cost price** field displays the cost value from the original sales line.</span></span>

## <a name="cost-calculation-example"></a><span data-ttu-id="e251a-136">Exemple de calcul de coût</span><span class="sxs-lookup"><span data-stu-id="e251a-136">Cost calculation example</span></span>

<span data-ttu-id="e251a-137">Lorsque vous utilisez le champ **N° de traitement de retours** d’une ligne d’ordre de retour pour spécifier le prix de vente de retour, le coût de la ligne d’ordre de retour est utilisé.</span><span class="sxs-lookup"><span data-stu-id="e251a-137">When you use the **Return lot ID** field on a return order line to specify the return cost price, the cost on the return order line is used.</span></span> <span data-ttu-id="e251a-138">Si vous exécutez la fonctionnalité de nouveau calcul ou de clôture du stock, le coût est ajusté sur la ligne de vente d’origine.</span><span class="sxs-lookup"><span data-stu-id="e251a-138">If you run the inventory close or recalculation functionality, the cost is adjusted on the original sales line.</span></span> <span data-ttu-id="e251a-139">Le coût de la ligne d’ordre de retour est automatiquement ajusté pour refléter le même coût par pièce.</span><span class="sxs-lookup"><span data-stu-id="e251a-139">The cost on the return order line is automatically adjusted to reflect the same cost per piece.</span></span>

1.  <span data-ttu-id="e251a-140">Créez et lancez un produit nommé Test.</span><span class="sxs-lookup"><span data-stu-id="e251a-140">Create and release a product that is named Test.</span></span> <span data-ttu-id="e251a-141">Dans l’écran **Détails des produits lancés**, spécifiez les informations suivantes :</span><span class="sxs-lookup"><span data-stu-id="e251a-141">In the **Released product details** form, specify the following information:</span></span>
    
    1.  <span data-ttu-id="e251a-142">Dans l’organisateur **Gérer les coûts**, dans le champ **Groupe d’articles**, sélectionnez le groupe **Parties**.</span><span class="sxs-lookup"><span data-stu-id="e251a-142">On the **Manage costs** FastTab, in the **Item group** field, select the **Parts** group.</span></span>
    
    2.  <span data-ttu-id="e251a-143">Dans l’organisateur **Général**, dans le champ **Groupe de modèles d’article**, sélectionnez **DEF**.</span><span class="sxs-lookup"><span data-stu-id="e251a-143">On the **General** FastTab, in the **Item model group** field, select **DEF**.</span></span>
    
    3.  <span data-ttu-id="e251a-144">Dans l’organisateur **Achats**, dans le champ **Prix**, tapez 10,00 comme prix de revient de l’article.</span><span class="sxs-lookup"><span data-stu-id="e251a-144">On the **Purchase** FastTab, in the **Price** field, type 10.00 as the cost price of the item.</span></span>
    
    4.  <span data-ttu-id="e251a-145">Dans le volet **Actions**, cliquez sur **Groupes de dimensions**.</span><span class="sxs-lookup"><span data-stu-id="e251a-145">On the **Action Pane**, click **Dimension groups**.</span></span> <span data-ttu-id="e251a-146">Dans le champ **Groupe de dimensions de stockage**, sélectionnez **Site et entrepôt uniquement**.</span><span class="sxs-lookup"><span data-stu-id="e251a-146">In the **Storage dimension group** field, select **Site and Warehouse only**.</span></span> <span data-ttu-id="e251a-147">Dans le champ **Groupe de dimensions de suivi**, sélectionnez **Aucune dimension de suivi active**.</span><span class="sxs-lookup"><span data-stu-id="e251a-147">In the **Tracking dimension group** field, select **No active tracking dimensions**.</span></span>

2.  <span data-ttu-id="e251a-148">Créez une commande fournisseur pour 10 pièces de l’article Test à 6,00 par pièce, puis validez une facture pour la commande fournisseur.</span><span class="sxs-lookup"><span data-stu-id="e251a-148">Create a purchase order for 10 pieces of the Test item at 6.00 per piece, and then post an invoice for the purchase order.</span></span>
    
    <span data-ttu-id="e251a-149">Créez une deuxième commande fournisseur pour 10 pièces de l’article Test à 8,00 par pièce, puis validez une facture pour la commande fournisseur.</span><span class="sxs-lookup"><span data-stu-id="e251a-149">Create a second purchase order for 10 pieces of the Test item at 8.00 per piece, and then post an invoice for the purchase order.</span></span>

3.  <span data-ttu-id="e251a-150">Validez une facture pour une commande client afin de vendre cinq pièces de l’article Test.</span><span class="sxs-lookup"><span data-stu-id="e251a-150">Post an invoice for a sales order to sell five pieces of the Test item.</span></span>
    
    <span data-ttu-id="e251a-151">Dans ce cas, la ligne de commande client est évaluée à 35,00 (5 pièces \* 7,00 (coût moyen par pièce)).</span><span class="sxs-lookup"><span data-stu-id="e251a-151">In this case, the sales order line is costed at 35.00 (5 pieces \* 7.00 average cost per piece).</span></span>

4.  <span data-ttu-id="e251a-152">Créez un ordre de retour pour le client.</span><span class="sxs-lookup"><span data-stu-id="e251a-152">Create a return order for the customer.</span></span> <span data-ttu-id="e251a-153">Dans l’écran **Rechercher une commande client**, sélectionnez la ligne de facture, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="e251a-153">In the **Find sales order** form, select the invoice line, and then click **OK**.</span></span>

5.  <span data-ttu-id="e251a-154">Dans l’écran **Ordre de retour - Numéro de retour marchandises : %1, %2**, vérifiez qu’un ordre de retour est généré de manière à retourner l’article Test.</span><span class="sxs-lookup"><span data-stu-id="e251a-154">In the **Return order - RMA number: %1, %2** form, verify that a return order is generated to return the Test item.</span></span> <span data-ttu-id="e251a-155">La quantité de l’ordre de retour est définie sur -5,00.</span><span class="sxs-lookup"><span data-stu-id="e251a-155">The quantity of the return order is set to -5.00.</span></span>
    
    <span data-ttu-id="e251a-156">Le champ **N° de traitement de retours** affiche un n° de traitement.</span><span class="sxs-lookup"><span data-stu-id="e251a-156">The **Return lot ID** field displays a lot ID.</span></span> <span data-ttu-id="e251a-157">Cet ID lot est extrait de la commande client d’origine de l’article vendu au client.</span><span class="sxs-lookup"><span data-stu-id="e251a-157">This lot ID is taken from the original sales order of the item that was sold to the customer.</span></span> <span data-ttu-id="e251a-158">Le champ **Prix de vente de retour** affiche le prix de revient de la ligne de vente d’origine.</span><span class="sxs-lookup"><span data-stu-id="e251a-158">The **Return cost price** field displays the cost price from the original sales line.</span></span>

6.  <span data-ttu-id="e251a-159">Enregistrez la réception des articles retournés.</span><span class="sxs-lookup"><span data-stu-id="e251a-159">Register the receipt of the returned items.</span></span>

7.  <span data-ttu-id="e251a-160">Validez un bon de livraison pour les articles retournés.</span><span class="sxs-lookup"><span data-stu-id="e251a-160">Post a packing slip for the returned items.</span></span>

8.  <span data-ttu-id="e251a-161">Validez une facture pour l’ordre de retour.</span><span class="sxs-lookup"><span data-stu-id="e251a-161">Post an invoice for the return order.</span></span> <span data-ttu-id="e251a-162">Dans la page de liste **Toutes les commandes client**, sélectionnez une commande client avec le type de commande **Commande retournée**.</span><span class="sxs-lookup"><span data-stu-id="e251a-162">On the **All sales orders** list page, select a sales order for which **Returned order** is the order type.</span></span>

9.  <span data-ttu-id="e251a-163">Ouvrez l’écran **Mouvements de stock**.</span><span class="sxs-lookup"><span data-stu-id="e251a-163">Open the **Inventory transactions** form.</span></span> <span data-ttu-id="e251a-164">Vérifiez que le retour est évalué à 7,00 par pièce à l’aide de la valeur du champ **Prix de vente de retour**, pour un total de 35,00 dans le champ **Coût**.</span><span class="sxs-lookup"><span data-stu-id="e251a-164">Verify that the return is costed at 7.00 per piece by using the value in the **Return cost price** field, for a total of 35.00 in the **Cost amount** field.</span></span> <span data-ttu-id="e251a-165">Vous pouvez ouvrir l’écran **Mouvements de stock** de l’écran **Ordre de retour - Numéro de retour marchandises : %1, %2**.</span><span class="sxs-lookup"><span data-stu-id="e251a-165">You can open the **Inventory transactions** form from the **Return order - RMA number: %1, %2** form.</span></span> <span data-ttu-id="e251a-166">Dans la grille **Lignes**, cliquez sur **Stock** \> **Transactions**.</span><span class="sxs-lookup"><span data-stu-id="e251a-166">In the **Lines** grid, click **Inventory** \> **Transactions**.</span></span>

10. <span data-ttu-id="e251a-167">Dans le module Gestion des stocks et des entrepôts, utilisez l’écran **Clôture et ajustement** pour exécuter la procédure **3. Clôturer**.</span><span class="sxs-lookup"><span data-stu-id="e251a-167">In Inventory and warehouse management, use the **Closing and adjustment** form to run the **3. Close** procedure.</span></span>
    
    <span data-ttu-id="e251a-168">Cette action règle le coût de la ligne de vente d’origine qui a été évaluée à -35,00 (5 pièces \* 7,00) sur -30,00 (5 pièces \* 6,00).</span><span class="sxs-lookup"><span data-stu-id="e251a-168">This action adjusts the cost on the original sales line that was costed at -35.00 (5 pieces \* 7.00) to -30.00 (5 pieces \* 6.00).</span></span> <span data-ttu-id="e251a-169">Cela est dû au fait que le groupe de modèles de stock utilise le modèle Premier entré, premier sorti (First In, First Out, ou FIFO) et que 6,00 est le coût FIFO de la première commande fournisseur.</span><span class="sxs-lookup"><span data-stu-id="e251a-169">This is because the inventory model group uses First in, First out (FIFO), and 6.00 per piece is the FIFO cost from the first purchase order.</span></span> <span data-ttu-id="e251a-170">En outre, l’action règle le coût de la ligne de vente de retour de manière à correspondre au coût par pièce de la ligne de vente d’origine.</span><span class="sxs-lookup"><span data-stu-id="e251a-170">Additionally, the action adjusts the cost on the return sales line to match the cost per piece on the original sales line.</span></span> <span data-ttu-id="e251a-171">Ainsi, le coût de la ligne de retour est ajusté de 35,00 à 30,00.</span><span class="sxs-lookup"><span data-stu-id="e251a-171">Therefore, the cost of the return line is adjusted from 35.00 to 30.00.</span></span>






[!INCLUDE[footer-include](../../includes/footer-banner.md)]