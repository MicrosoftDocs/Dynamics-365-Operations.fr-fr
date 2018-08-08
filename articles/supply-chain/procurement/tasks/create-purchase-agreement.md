--- 
title: "Créer un contrat d'achat"
description: "Cette procédure vous guide via la création d'un contrat d'achat."
author: mkirknel
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: d9747ba144d56c9410846769e5465372c89ea111
ms.openlocfilehash: 46b8ff64fd950aae9178133b8aba7a9a2888b074
ms.contentlocale: fr-fr
ms.lasthandoff: 08/07/2018

---
# <a name="create-a-purchase-agreement"></a><span data-ttu-id="3be84-103">Créer un contrat d'achat</span><span class="sxs-lookup"><span data-stu-id="3be84-103">Create a purchase agreement</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="3be84-104">Cette procédure vous guide via la création d'un contrat d'achat.</span><span class="sxs-lookup"><span data-stu-id="3be84-104">This procedure guides you through the creation of a purchase agreement.</span></span> <span data-ttu-id="3be84-105">Cela est généralement effectué par un gestionnaire des achats.</span><span class="sxs-lookup"><span data-stu-id="3be84-105">This would typically be done by a purchasing manager.</span></span> <span data-ttu-id="3be84-106">Vous pouvez utiliser cette procédure dans la société fictive de démonstration USMF ou utiliser vos propres données.</span><span class="sxs-lookup"><span data-stu-id="3be84-106">You can use this procedure in demo data company USMF or on your own data.</span></span> <span data-ttu-id="3be84-107">Vous devez avoir configuré des classifications de contrat d'achat avant de commencer.</span><span class="sxs-lookup"><span data-stu-id="3be84-107">You need to have set up purchase agreement classifications before you start.</span></span> <span data-ttu-id="3be84-108">Une fois que vous avez créé un accord, vous pouvez l'utiliser lorsque vous créez une commande fournisseur. Cela copiera les conditions du contrat d'achat dans l'en-tête et sur toutes les lignes de la commande qui sont affectées par l'accord.</span><span class="sxs-lookup"><span data-stu-id="3be84-108">Once you've created an agreement you can use it when you create a PO, and this will copy the purchase agreement conditions to the header and to any lines in the order that are affected by the agreement.</span></span>


## <a name="create-a-new-purchase-agreement"></a><span data-ttu-id="3be84-109">Créer un contrat d'achat</span><span class="sxs-lookup"><span data-stu-id="3be84-109">Create a new purchase agreement</span></span>
1. <span data-ttu-id="3be84-110">Accédez à Approvisionnements > Contrats d'achat > Contrats d'achat.</span><span class="sxs-lookup"><span data-stu-id="3be84-110">Go to Procurement and sourcing > Purchase agreements > Purchase agreements.</span></span>
2. <span data-ttu-id="3be84-111">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="3be84-111">Click New.</span></span>
3. <span data-ttu-id="3be84-112">Dans le champ Compte fournisseur, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="3be84-112">In the Vendor account field, click the drop-down button to open the lookup.</span></span>
4. <span data-ttu-id="3be84-113">Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="3be84-113">In the list, find and select the desired record.</span></span>
5. <span data-ttu-id="3be84-114">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="3be84-114">In the list, click the link in the selected row.</span></span>
6. <span data-ttu-id="3be84-115">Dans le champ Classifications des contrats d'achat, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="3be84-115">In the Purchase agreement classification field, click the drop-down button to open the lookup.</span></span>
7. <span data-ttu-id="3be84-116">Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="3be84-116">In the list, find and select the desired record.</span></span>
8. <span data-ttu-id="3be84-117">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="3be84-117">In the list, click the link in the selected row.</span></span>
9. <span data-ttu-id="3be84-118">Développez la section Général.</span><span class="sxs-lookup"><span data-stu-id="3be84-118">Expand the General section.</span></span>
10. <span data-ttu-id="3be84-119">Dans le champ Date d'expiration, entrez une date.</span><span class="sxs-lookup"><span data-stu-id="3be84-119">In the Expiration date field, enter a date.</span></span>
    * <span data-ttu-id="3be84-120">Cette date d'expiration est la valeur par défaut pour toutes les lignes d'engagement et détermine la durée pendant laquelle chaque engagement spécifique est valide.</span><span class="sxs-lookup"><span data-stu-id="3be84-120">This expiration date will be the default for all commitment lines and will determine how long each specific commitment is valid.</span></span>  
11. <span data-ttu-id="3be84-121">Dans le champ Titre du document, entrez un nom pour votre contrat d'achat.</span><span class="sxs-lookup"><span data-stu-id="3be84-121">In the Document title field, type a name for your purchase agreement.</span></span>
    * <span data-ttu-id="3be84-122">Laissez le champ Engagement par défaut configuré sur Engagement à la quantité de produits (ou modifiez-le s'il n'est pas défini ainsi).</span><span class="sxs-lookup"><span data-stu-id="3be84-122">Leave the Default commitment field set to Product quantity commitment (or change it if it’s not set to this).</span></span>  
    * <span data-ttu-id="3be84-123">La valeur d'engagement par défaut détermine les options dans les lignes d'accord.</span><span class="sxs-lookup"><span data-stu-id="3be84-123">The default commitment value determines your options on the agreement lines.</span></span> <span data-ttu-id="3be84-124">Si vous avez besoin d'un type d'engagement lorsque vous créez des lignes d'accord, vous devez modifier l'engagement par défaut sous l'en-tête.</span><span class="sxs-lookup"><span data-stu-id="3be84-124">If you need a new commitment type when you’re creating the agreement lines, you need to change the default commitment on the header.</span></span>  <span data-ttu-id="3be84-125">Il y a 4 types d'engagements : Engagement de quantité de produits (pour une quantité spécifique d'un produit) ; Engagement de valeur de produit (pour un montant en devise spécifique d'un produit) ; Engagement de valeur de catégorie de produit (pour un montant en devise spécifique dans une catégorie d'approvisionnement, avec un montant qui peut être celui d'un article du catalogue ou celui d'un article ne faisant pas partie du catalogue) ; Engagement de valeur (pour un montant en devise spécifique qui peut être atteint par tout produit ou par n'importe quelle catégorie d'approvisionnement).</span><span class="sxs-lookup"><span data-stu-id="3be84-125">There are 4 types of commitments: Product quantity commitment - for a specific quantity of a product; Product value commitment - for a specific currency amount of a product; Product category value commitment - for a specific currency amount in a procurement category where the amount can be for a catalog item or a non-catalog item; Value commitment - for a specific currency amount which can be fulfilled by any product or by any procurement category.</span></span>  
12. <span data-ttu-id="3be84-126">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="3be84-126">Click OK.</span></span>

## <a name="add-a-commitment"></a><span data-ttu-id="3be84-127">Ajouter un engagement</span><span class="sxs-lookup"><span data-stu-id="3be84-127">Add a commitment</span></span>
1. <span data-ttu-id="3be84-128">Cliquez sur Ajouter une ligne.</span><span class="sxs-lookup"><span data-stu-id="3be84-128">Click Add line.</span></span>
2. <span data-ttu-id="3be84-129">Dans la liste, marquez la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="3be84-129">In the list, mark the selected row.</span></span>
3. <span data-ttu-id="3be84-130">Dans le champ Numéro d'article, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="3be84-130">In the Item number field, click the drop-down button to open the lookup.</span></span>
4. <span data-ttu-id="3be84-131">Sélectionnez le produit auquel vous souhaitez ajouter un engagement.</span><span class="sxs-lookup"><span data-stu-id="3be84-131">Select the product you want to add a commitment for.</span></span>
5. <span data-ttu-id="3be84-132">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="3be84-132">In the list, click the link in the selected row.</span></span>
6. <span data-ttu-id="3be84-133">Dans le champ Quantité, entrer un numéro.</span><span class="sxs-lookup"><span data-stu-id="3be84-133">In the Quantity field, enter a number.</span></span>
    * <span data-ttu-id="3be84-134">Il s'agit de la quantité totale que vous avez acceptée d'acheter auprès de votre fournisseur.</span><span class="sxs-lookup"><span data-stu-id="3be84-134">This is the total quantity that you have agreed to buy from your vendor.</span></span>  
7. <span data-ttu-id="3be84-135">Entrez un nombre dans le champ Prix unitaire.</span><span class="sxs-lookup"><span data-stu-id="3be84-135">In the Unit price field, enter a number.</span></span>
8. <span data-ttu-id="3be84-136">Développez la section Détails de ligne.</span><span class="sxs-lookup"><span data-stu-id="3be84-136">Expand the Line details section.</span></span>
9. <span data-ttu-id="3be84-137">Définissez l'option Le max. est appliqué sur Oui.</span><span class="sxs-lookup"><span data-stu-id="3be84-137">Set the Max is enforced option to Yes.</span></span>
    * <span data-ttu-id="3be84-138">L'option Le max. est appliqué limite l'utilisation de l'engagement.</span><span class="sxs-lookup"><span data-stu-id="3be84-138">The Max is enforced option limits the use of the commitment.</span></span> <span data-ttu-id="3be84-139">Vous pouvez acheter jusqu'à la quantité spécifiée dans le champ Quantité pour la ligne.</span><span class="sxs-lookup"><span data-stu-id="3be84-139">You can only purchase up to the quantity that's specified in the Quantity field for the line.</span></span>  
10. <span data-ttu-id="3be84-140">Réduisez la section Détails de ligne.</span><span class="sxs-lookup"><span data-stu-id="3be84-140">Collapse the Line details section.</span></span>

## <a name="add-header-conditions"></a><span data-ttu-id="3be84-141">Ajouter des conditions d'en-tête</span><span class="sxs-lookup"><span data-stu-id="3be84-141">Add header conditions</span></span>
1. <span data-ttu-id="3be84-142">Dans le volet Actions, cliquez sur Options.</span><span class="sxs-lookup"><span data-stu-id="3be84-142">On the Action Pane, click Options.</span></span>
2. <span data-ttu-id="3be84-143">Cliquez sur Changer de vue.</span><span class="sxs-lookup"><span data-stu-id="3be84-143">Click Change view.</span></span>
3. <span data-ttu-id="3be84-144">Cliquez sur Vue de l'en-tête.</span><span class="sxs-lookup"><span data-stu-id="3be84-144">Click Header view.</span></span>
4. <span data-ttu-id="3be84-145">Développez la section Conditions.</span><span class="sxs-lookup"><span data-stu-id="3be84-145">Expand the Terms section.</span></span>
5. <span data-ttu-id="3be84-146">Dans le champ Mode de paiement, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="3be84-146">In the Method of payment field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="3be84-147">Les conditions de paiement du compte fournisseur sont indiquées ici par défaut.</span><span class="sxs-lookup"><span data-stu-id="3be84-147">The payment terms from the vendor account are shown here by default.</span></span>       
6. <span data-ttu-id="3be84-148">Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="3be84-148">In the list, find and select the desired record.</span></span>
7. <span data-ttu-id="3be84-149">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="3be84-149">In the list, click the link in the selected row.</span></span>
8. <span data-ttu-id="3be84-150">Dans le champ Mode de livraison, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="3be84-150">In the Mode of delivery field, click the drop-down button to open the lookup.</span></span>
9. <span data-ttu-id="3be84-151">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="3be84-151">In the list, click the link in the selected row.</span></span>
10. <span data-ttu-id="3be84-152">Dans le champ Conditions de livraison, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="3be84-152">In the Delivery terms field, click the drop-down button to open the lookup.</span></span>
11. <span data-ttu-id="3be84-153">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="3be84-153">In the list, click the link in the selected row.</span></span>

## <a name="confirm-and-activate-the-agreement"></a><span data-ttu-id="3be84-154">Confirmer et activer le contrat de vente</span><span class="sxs-lookup"><span data-stu-id="3be84-154">Confirm and activate the agreement</span></span>
1. <span data-ttu-id="3be84-155">Dans le volet Action, cliquez sur Contrat d'achat.</span><span class="sxs-lookup"><span data-stu-id="3be84-155">On the Action Pane, click Purchase agreement.</span></span>
2. <span data-ttu-id="3be84-156">Cliquez sur Confirmation.</span><span class="sxs-lookup"><span data-stu-id="3be84-156">Click Confirmation.</span></span>
    * <span data-ttu-id="3be84-157">Définissez l'option Marquer l'accord comme effectif sur oui.</span><span class="sxs-lookup"><span data-stu-id="3be84-157">Set the Mark agreement as effective option to Yes.</span></span>  
3. <span data-ttu-id="3be84-158">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="3be84-158">Click OK.</span></span>
4. <span data-ttu-id="3be84-159">Dans le volet Action, cliquez sur Contrat d'achat.</span><span class="sxs-lookup"><span data-stu-id="3be84-159">On the Action Pane, click Purchase agreement.</span></span>
5. <span data-ttu-id="3be84-160">Cliquez sur Confirmations de contrat d'achat.</span><span class="sxs-lookup"><span data-stu-id="3be84-160">Click Purchase agreement confirmations.</span></span>
    * <span data-ttu-id="3be84-161">L'option Aperçu/Imprimer permet de générer un document pour le contrat d'achat que vous pouvez ensuite imprimer ou envoyer au fournisseur.</span><span class="sxs-lookup"><span data-stu-id="3be84-161">The Preview/Print option allows you to generate a document for the purchase agreement which you can then print or send to the vendor.</span></span> <span data-ttu-id="3be84-162">Si vous mettez à jour l'accord ultérieurement et le confirmez à nouveau, les deux versions sont indiquées ici.</span><span class="sxs-lookup"><span data-stu-id="3be84-162">If you update the agreement later on and re-confirm it, both versions will be shown here.</span></span>  
6. <span data-ttu-id="3be84-163">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="3be84-163">Close the page.</span></span>


