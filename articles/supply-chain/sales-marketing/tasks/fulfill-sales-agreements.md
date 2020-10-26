---
title: Fournir des contrats de vente
description: Cette procédure montre comment honorer un contrat de vente en y associant des commandes client.
author: omulvad
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SalesAgreementListPage, SalesAgreement, SalesAgreementGenerateReleaseOrder, SalesTableListPage, SalesTable, AgreementLine, SalesCreateOrder,  SalesEditLines, SalesAgreementHistory
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 7d3a35c7140b886f931df48e583b1582201b6547
ms.sourcegitcommit: 708ca25687a4e48271cdcd6d2d22d99fb94cf140
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/10/2020
ms.locfileid: "3982015"
---
# <a name="fulfill-sales-agreements"></a><span data-ttu-id="dd7a5-103">Fournir des contrats de vente</span><span class="sxs-lookup"><span data-stu-id="dd7a5-103">Fulfill sales agreements</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="dd7a5-104">Cette procédure montre comment honorer un contrat de vente en y associant des commandes client.</span><span class="sxs-lookup"><span data-stu-id="dd7a5-104">This procedure shows you how to fulfill a sales agreement by associating sales orders with it.</span></span> <span data-ttu-id="dd7a5-105">Vous pouvez exécuter cette procédure dans la société fictive de démonstration USMF ou utiliser vos propres données.</span><span class="sxs-lookup"><span data-stu-id="dd7a5-105">You can run this procedure in demo data company USMF or on your own data.</span></span> <span data-ttu-id="dd7a5-106">Avant de lancer ce guide, vérifiez que vous avez un contrat de vente en vigueur du type « Engagement à la valeur du produit ».</span><span class="sxs-lookup"><span data-stu-id="dd7a5-106">Before starting this guide, make sure you have an effective sales agreement of type "Product value commitment".</span></span> <span data-ttu-id="dd7a5-107">Dans le cas contraire, vous pouvez exécuter le guide de tâche appelé « Créer des contrats de vente ».</span><span class="sxs-lookup"><span data-stu-id="dd7a5-107">Alternatively, you can run the task guide called "Create sales agreements".</span></span>  




## <a name="release-a-sales-order-from-the-agreement"></a><span data-ttu-id="dd7a5-108">Lancer une commande client à partir du contrat</span><span class="sxs-lookup"><span data-stu-id="dd7a5-108">Release a sales order from the agreement</span></span>
1. <span data-ttu-id="dd7a5-109">Accédez à Ventes et marketing > Contrats de vente > Contrats de vente.</span><span class="sxs-lookup"><span data-stu-id="dd7a5-109">Go to Sales and marketing > Sales agreements > Sales agreements.</span></span>
2. <span data-ttu-id="dd7a5-110">Dans la liste, ouvrez l'accord avec lequel vous souhaitez lancer la commande.</span><span class="sxs-lookup"><span data-stu-id="dd7a5-110">In the list, open the agreement against which you want to release the order.</span></span>
3. <span data-ttu-id="dd7a5-111">Dans le volet Actions, cliquez sur Contrats de vente.</span><span class="sxs-lookup"><span data-stu-id="dd7a5-111">On the Action Pane, click Sales agreement.</span></span>
4. <span data-ttu-id="dd7a5-112">Cliquez sur Lancer la commande.</span><span class="sxs-lookup"><span data-stu-id="dd7a5-112">Click Release order.</span></span>
    * <span data-ttu-id="dd7a5-113">Comme l'indique le texte en haut de la page Créer un ordre de lancement, les détails requis pour les lignes de commande client seront différents selon que l'accord est fondé sur la quantité ou sur la valeur.</span><span class="sxs-lookup"><span data-stu-id="dd7a5-113">As the text on top of the  Create release order page points out, the details required for the sales order lines will differ depending on whether the agreement is quantity- or value-based.</span></span>  
    * <span data-ttu-id="dd7a5-114">Dans ce guide, l'accord est du type « Engagement à la valeur du produit ».</span><span class="sxs-lookup"><span data-stu-id="dd7a5-114">The agreement in this guide is of type "Product value commitment".</span></span> <span data-ttu-id="dd7a5-115">C'est pourquoi la section Lignes de cette page est vide.</span><span class="sxs-lookup"><span data-stu-id="dd7a5-115">This is why the Lines section of this page is blank.</span></span> <span data-ttu-id="dd7a5-116">Si l'engagement était fondé sur la quantité, les informations de ligne seraient copiées à partir de l'accord.</span><span class="sxs-lookup"><span data-stu-id="dd7a5-116">If the commitment was based on quantity, the line information would be copied from the agreement.</span></span>  
5. <span data-ttu-id="dd7a5-117">Cliquez sur Créer.</span><span class="sxs-lookup"><span data-stu-id="dd7a5-117">Click Create.</span></span>
    * <span data-ttu-id="dd7a5-118">Le message vous indique qu'une commande fournisseur a été créée.</span><span class="sxs-lookup"><span data-stu-id="dd7a5-118">The message informs you that a sales order has been created.</span></span> <span data-ttu-id="dd7a5-119">Étant donné que la commande ne contient aucune ligne, vous devez ajouter des détails de ligne de commande pour compléter le processus de lancement.</span><span class="sxs-lookup"><span data-stu-id="dd7a5-119">Since the order does not contain any lines, you must add order line details to complete the release process.</span></span>   
6. <span data-ttu-id="dd7a5-120">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="dd7a5-120">Close the page.</span></span>
7. <span data-ttu-id="dd7a5-121">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="dd7a5-121">Close the page.</span></span>
8. <span data-ttu-id="dd7a5-122">Allez dans Ventes et marketing > Commandes client > Toutes les commandes client.</span><span class="sxs-lookup"><span data-stu-id="dd7a5-122">Go to Sales and marketing > Sales orders > All sales orders.</span></span>
9. <span data-ttu-id="dd7a5-123">Dans la liste, cherchez et ouvrez la commande qui a été créée suite au lancement de commande de la tâche précédente.</span><span class="sxs-lookup"><span data-stu-id="dd7a5-123">In the list, find and open the order that was created as the result of the order release in the previous task.</span></span>
10. <span data-ttu-id="dd7a5-124">Cliquez sur Ajouter une ligne.</span><span class="sxs-lookup"><span data-stu-id="dd7a5-124">Click Add line.</span></span>
11. <span data-ttu-id="dd7a5-125">Dans le champ Numéro d'article, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="dd7a5-125">In the Item number field, click the drop-down button to open the lookup.</span></span>
12. <span data-ttu-id="dd7a5-126">Dans le champ Numéro d'article, tapez ou sélectionnez l'article spécifié dans le contrat de vente associé.</span><span class="sxs-lookup"><span data-stu-id="dd7a5-126">In the Item number field, type or select the item that is specified on the associated sales agreement.</span></span>
13. <span data-ttu-id="dd7a5-127">Dans le champ Quantité, entrer un numéro.</span><span class="sxs-lookup"><span data-stu-id="dd7a5-127">In the Quantity field, enter a number.</span></span>
    * <span data-ttu-id="dd7a5-128">Assurez-vous d'entrer une quantité qui porte le montant HT sous la valeur du contrat de vente associé.</span><span class="sxs-lookup"><span data-stu-id="dd7a5-128">Make sure that you enter a quantity that brings the Net amount under the value of the associated sales agreement.</span></span>  
    * <span data-ttu-id="dd7a5-129">Notez que, comme la commande client est liée à l'accord, le pourcentage de remise négocié est appliqué à la ligne de commande.</span><span class="sxs-lookup"><span data-stu-id="dd7a5-129">Notice that because the sales order is linked to the agreement, the negotiated discount percent is applied to the order line.</span></span>  
14. <span data-ttu-id="dd7a5-130">Cliquez sur Mettre à jour la ligne.</span><span class="sxs-lookup"><span data-stu-id="dd7a5-130">Click Update line.</span></span>
15. <span data-ttu-id="dd7a5-131">Cliquez sur Joint.</span><span class="sxs-lookup"><span data-stu-id="dd7a5-131">Click Attached.</span></span>
    * <span data-ttu-id="dd7a5-132">La page Accord joint affiche l'ID et les conditions de l'accord à partir duquel la ligne est lancée.</span><span class="sxs-lookup"><span data-stu-id="dd7a5-132">The Attached agreement page shows the ID and terms of the agreement from which the line is released.</span></span>  
16. <span data-ttu-id="dd7a5-133">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="dd7a5-133">Close the page.</span></span>
17. <span data-ttu-id="dd7a5-134">Cliquez sur Général dans le volet Actions.</span><span class="sxs-lookup"><span data-stu-id="dd7a5-134">On the Action Pane, click General.</span></span>
18. <span data-ttu-id="dd7a5-135">Cliquez sur Contrat de vente joint.</span><span class="sxs-lookup"><span data-stu-id="dd7a5-135">Click Attached sales agreement.</span></span>
19. <span data-ttu-id="dd7a5-136">Développez la section Détails de ligne.</span><span class="sxs-lookup"><span data-stu-id="dd7a5-136">Expand the Line details section.</span></span>
20. <span data-ttu-id="dd7a5-137">Cliquez sur l'onglet Exécution.</span><span class="sxs-lookup"><span data-stu-id="dd7a5-137">Click the Fulfillment tab.</span></span>
    * <span data-ttu-id="dd7a5-138">L'onglet Exécution indique un récapitulatif de toutes les lignes de commande client associées à cet engagement et leur état d'exécution, ainsi que le montant ou la quantité qui n'ont pas encore été lancés.</span><span class="sxs-lookup"><span data-stu-id="dd7a5-138">The Fulfillment tab shows a summary of all the sales order lines that are associated with this commitment, and their fulfillment state, as well as the amount or quantity that has not yet been released.</span></span>   
21. <span data-ttu-id="dd7a5-139">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="dd7a5-139">Close the page.</span></span>
22. <span data-ttu-id="dd7a5-140">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="dd7a5-140">Close the page.</span></span>
23. <span data-ttu-id="dd7a5-141">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="dd7a5-141">Close the page.</span></span>

## <a name="apply-sales-agreement-in-the-order-process"></a><span data-ttu-id="dd7a5-142">Appliquer un contrat de vente dans le processus de commande</span><span class="sxs-lookup"><span data-stu-id="dd7a5-142">Apply sales agreement in the order process</span></span>
1. <span data-ttu-id="dd7a5-143">Allez dans Ventes et marketing > Commandes client > Toutes les commandes client.</span><span class="sxs-lookup"><span data-stu-id="dd7a5-143">Go to Sales and marketing > Sales orders > All sales orders.</span></span>
2. <span data-ttu-id="dd7a5-144">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="dd7a5-144">Click New.</span></span>
3. <span data-ttu-id="dd7a5-145">Dans le champ Compte client, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="dd7a5-145">In the Customer account field, click the drop-down button to open the lookup.</span></span>
4. <span data-ttu-id="dd7a5-146">Dans la liste, cherchez et sélectionnez le client spécifié dans le contrat de vente.</span><span class="sxs-lookup"><span data-stu-id="dd7a5-146">In the list, find and select the customer specified on the sales agreement.</span></span>
5. <span data-ttu-id="dd7a5-147">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="dd7a5-147">In the list, click the link in the selected row.</span></span>
6. <span data-ttu-id="dd7a5-148">Développez la section Général.</span><span class="sxs-lookup"><span data-stu-id="dd7a5-148">Expand the General section.</span></span>
7. <span data-ttu-id="dd7a5-149">Dans le champ ID Contrat de vente, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="dd7a5-149">In the Sales agreement ID field, click the drop-down button to open the lookup.</span></span>
8. <span data-ttu-id="dd7a5-150">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="dd7a5-150">In the list, click the link in the selected row.</span></span>
9. <span data-ttu-id="dd7a5-151">Cliquez sur Oui.</span><span class="sxs-lookup"><span data-stu-id="dd7a5-151">Click Yes.</span></span>
10. <span data-ttu-id="dd7a5-152">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="dd7a5-152">Click OK.</span></span>
11. <span data-ttu-id="dd7a5-153">Dans la liste, marquez la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="dd7a5-153">In the list, mark the selected row.</span></span>
12. <span data-ttu-id="dd7a5-154">Dans le champ Numéro d'article, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="dd7a5-154">In the Item number field, click the drop-down button to open the lookup.</span></span>
13. <span data-ttu-id="dd7a5-155">Dans le champ Numéro d'article, tapez ou sélectionnez l'article spécifié dans le contrat de vente associé.</span><span class="sxs-lookup"><span data-stu-id="dd7a5-155">In the Item number field, type or select the item that is specified on the associated sales agreement.</span></span>
14. <span data-ttu-id="dd7a5-156">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="dd7a5-156">In the list, click the link in the selected row.</span></span>
15. <span data-ttu-id="dd7a5-157">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="dd7a5-157">Click Save.</span></span>
16. <span data-ttu-id="dd7a5-158">Cliquez sur Prélever et emballer dans le volet Actions.</span><span class="sxs-lookup"><span data-stu-id="dd7a5-158">On the Action Pane, click Pick and pack.</span></span>
17. <span data-ttu-id="dd7a5-159">Cliquez sur Validation du bon de livraison.</span><span class="sxs-lookup"><span data-stu-id="dd7a5-159">Click Post packing slip.</span></span>
18. <span data-ttu-id="dd7a5-160">Développez la section Paramètres.</span><span class="sxs-lookup"><span data-stu-id="dd7a5-160">Expand the Parameters section.</span></span>
19. <span data-ttu-id="dd7a5-161">Sélectionnez Oui dans le champ Validation.</span><span class="sxs-lookup"><span data-stu-id="dd7a5-161">Select Yes in the Posting field.</span></span>
20. <span data-ttu-id="dd7a5-162">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="dd7a5-162">Click OK.</span></span>
21. <span data-ttu-id="dd7a5-163">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="dd7a5-163">Click OK.</span></span>
22. <span data-ttu-id="dd7a5-164">Cliquez sur Général dans le volet Actions.</span><span class="sxs-lookup"><span data-stu-id="dd7a5-164">On the Action Pane, click General.</span></span>
23. <span data-ttu-id="dd7a5-165">Cliquez sur Contrat de vente joint.</span><span class="sxs-lookup"><span data-stu-id="dd7a5-165">Click Attached sales agreement.</span></span>
24. <span data-ttu-id="dd7a5-166">Cliquez sur l'onglet Exécution.</span><span class="sxs-lookup"><span data-stu-id="dd7a5-166">Click the Fulfillment tab.</span></span>

