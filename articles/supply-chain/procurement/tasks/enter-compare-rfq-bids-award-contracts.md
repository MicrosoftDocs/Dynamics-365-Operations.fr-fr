--- 
title: Entrer et comparer des appels d'offre et octroyer des contrats
description: "Cette procédure décrit comment entrer des réponses à un appel d'offre, marquer et comparer les offres, puis attribuer une offre à l'un des fournisseurs."
author: mkirknel
manager: AnnBe
ms.date: 06/07/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bis
ms.search.scope: Operations
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 5dea9d7bfb1bf7b11f6c49cccaab1b73d4e58d16
ms.contentlocale: fr-fr
ms.lasthandoff: 09/29/2017

---
# <a name="enter-and-compare-rfq-bids-and-award-contracts"></a><span data-ttu-id="773ca-103">Entrer et comparer des appels d'offre et octroyer des contrats</span><span class="sxs-lookup"><span data-stu-id="773ca-103">Enter and compare RFQ bids and award contracts</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="773ca-104">Cette procédure décrit comment entrer des réponses à un appel d'offre, marquer et comparer les offres, puis attribuer une offre à l'un des fournisseurs.</span><span class="sxs-lookup"><span data-stu-id="773ca-104">This procedure shows you how to enter replies to an RFQ, score and compare bids, and then award the bid to one of the vendors.</span></span> <span data-ttu-id="773ca-105">Vous pouvez utiliser cette procédure dans les données fictives de la société USMF.</span><span class="sxs-lookup"><span data-stu-id="773ca-105">You can use this procedure in demo data company USMF.</span></span> <span data-ttu-id="773ca-106">Avant de commencer, vous devez avoir un appel d'offre avec deux lignes qui a été envoyé au moins à deux fournisseurs.</span><span class="sxs-lookup"><span data-stu-id="773ca-106">Before you start, you must have an RFQ with two lines that has been sent to at least two vendors.</span></span> <span data-ttu-id="773ca-107">Vous pouvez exécuter la procédure « Création d'une demande de devis » comme étape préliminaire pour créer cela.</span><span class="sxs-lookup"><span data-stu-id="773ca-107">You can run the "Create a request for quotation" procedure as a prerequisite to create this.</span></span> <span data-ttu-id="773ca-108">Vous devez avoir paramétré les critères d'attribution de score pour pouvoir exécuter cette procédure.</span><span class="sxs-lookup"><span data-stu-id="773ca-108">You need to have set up scoring criteria before you can run this procedure.</span></span>


## <a name="enter-a-reply-from-a-vendor"></a><span data-ttu-id="773ca-109">Entrer la réponse d'un fournisseur</span><span class="sxs-lookup"><span data-stu-id="773ca-109">Enter a reply from a vendor</span></span>
1. <span data-ttu-id="773ca-110">Accédez à Approvisionnements > Demandes de devis > Toutes les demandes de devis</span><span class="sxs-lookup"><span data-stu-id="773ca-110">Go to Procurement and sourcing > Requests for quotations > All requests for quotations.</span></span>
2. <span data-ttu-id="773ca-111">Sélectionnez un appel d'offre ayant le statut Envoyé, puis cliquez sur le lien sur le numéro de dossier de l'appel d'offre.</span><span class="sxs-lookup"><span data-stu-id="773ca-111">Select an RFQ that has a status of Sent and click the link on the Request for quotation case number.</span></span>
    * <span data-ttu-id="773ca-112">L'appel d'offre aurait dû être envoyé à au moins à 2 fournisseurs.</span><span class="sxs-lookup"><span data-stu-id="773ca-112">The RFQ should have been sent to at least 2 vendors.</span></span>  
3. <span data-ttu-id="773ca-113">Cliquez sur l'en-tête pour accéder à la liste des fournisseurs.</span><span class="sxs-lookup"><span data-stu-id="773ca-113">Click Header to go to the list of vendors.</span></span>
4. <span data-ttu-id="773ca-114">Sélectionnez le fournisseur pour lequel vous souhaitez entrer une réponse dans l'appel d'offre.</span><span class="sxs-lookup"><span data-stu-id="773ca-114">Select the vendor for whom you want to enter a response on the RFQ.</span></span>
5. <span data-ttu-id="773ca-115">Cliquez sur Entrer une réponse.</span><span class="sxs-lookup"><span data-stu-id="773ca-115">Click Enter reply.</span></span>
6. <span data-ttu-id="773ca-116">Cliquez sur Répondre dans le volet Actions.</span><span class="sxs-lookup"><span data-stu-id="773ca-116">On the Action Pane, click Reply.</span></span>
7. <span data-ttu-id="773ca-117">Cliquez sur Copier des données dans la réponse.</span><span class="sxs-lookup"><span data-stu-id="773ca-117">Click Copy data to reply.</span></span>
    * <span data-ttu-id="773ca-118">Cette action copiera les données sélectionnées, par exemple, la quantité du dossier d'appel d'offre est copiée dans la réponse d'appel d'offre.</span><span class="sxs-lookup"><span data-stu-id="773ca-118">This action will copy selected data, for example, the quantity from the RFQ case to the RFQ reply.</span></span> <span data-ttu-id="773ca-119">Vous pouvez également ignorer cette action et remplir tous les champs manuellement lorsque vous modifiez la réponse.</span><span class="sxs-lookup"><span data-stu-id="773ca-119">Alternatively you can skip this action and fill in all the response fields manually when you edit the reply.</span></span>  
8. <span data-ttu-id="773ca-120">Cliquez sur Modifier.</span><span class="sxs-lookup"><span data-stu-id="773ca-120">Click Edit.</span></span>
9. <span data-ttu-id="773ca-121">Entrez un nombre dans le champ Prix unitaire.</span><span class="sxs-lookup"><span data-stu-id="773ca-121">In the Unit price field, enter a number.</span></span>
10. <span data-ttu-id="773ca-122">Choisissez l'autre ligne de devis.</span><span class="sxs-lookup"><span data-stu-id="773ca-122">Choose the other quotation line.</span></span>
11. <span data-ttu-id="773ca-123">Entrez un nombre dans le champ Prix unitaire.</span><span class="sxs-lookup"><span data-stu-id="773ca-123">In the Unit price field, enter a number.</span></span>

## <a name="score-the-bid"></a><span data-ttu-id="773ca-124">Attribuer un score à l'offre</span><span class="sxs-lookup"><span data-stu-id="773ca-124">Score the bid</span></span>
1. <span data-ttu-id="773ca-125">Cliquez sur l'en-tête pour accéder à l'attribution de score de l'offre.</span><span class="sxs-lookup"><span data-stu-id="773ca-125">Click Header to go to the scoring of the bid.</span></span>
2. <span data-ttu-id="773ca-126">Développez la section Attribution de score de l'offre.</span><span class="sxs-lookup"><span data-stu-id="773ca-126">Expand the Bid scoring section.</span></span>
3. <span data-ttu-id="773ca-127">Entrez un nombre pour l'un des critères d'attribution de score dans le champ Score.</span><span class="sxs-lookup"><span data-stu-id="773ca-127">In the Score field, enter a number for one of the scoring criteria.</span></span>
    * <span data-ttu-id="773ca-128">Si vous passez la souris sur l'un des critères d'attribution de score, une info-bulle indique la plage dans laquelle vous devez marquer les points.</span><span class="sxs-lookup"><span data-stu-id="773ca-128">If you hover over one of the scoring criteria a tooltip shows the range that you have to score within.</span></span> <span data-ttu-id="773ca-129">Dans cette démonstration vous pouvez ajouter un nombre compris entre 1 et 5 à n'importe lequel des critères.</span><span class="sxs-lookup"><span data-stu-id="773ca-129">In this demo you can add a number between 1 and 5 to any of the criteria.</span></span>  
4. <span data-ttu-id="773ca-130">Sélectionnez un autre critère d'attribution de score.</span><span class="sxs-lookup"><span data-stu-id="773ca-130">Select another scoring criterion.</span></span>
5. <span data-ttu-id="773ca-131">Entrez un nombre dans le champ Score.</span><span class="sxs-lookup"><span data-stu-id="773ca-131">In the Score field, enter a number.</span></span>
6. <span data-ttu-id="773ca-132">Développez la section Questionnaires.</span><span class="sxs-lookup"><span data-stu-id="773ca-132">Expand the Questionnaires section.</span></span>
    * <span data-ttu-id="773ca-133">Si l'appel d'offre a un questionnaire qui a été soumis aux fournisseurs, vous pouvez entrer leurs réponses dans la section questionnaire.</span><span class="sxs-lookup"><span data-stu-id="773ca-133">If the RFQ case has a questionnaire that was sent to the vendors, you can enter their responses in the questionnaire section.</span></span>  
7. <span data-ttu-id="773ca-134">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="773ca-134">Close the page.</span></span>

## <a name="enter-a-reply-for-another-vendor"></a><span data-ttu-id="773ca-135">Entrer une réponse pour un autre fournisseur</span><span class="sxs-lookup"><span data-stu-id="773ca-135">Enter a reply for another vendor</span></span>
1. <span data-ttu-id="773ca-136">Sélectionnez le fournisseur suivant en désactivant le fournisseur pour lequel vous venez d'entrer la réponse, puis en sélectionnant la ligne du fournisseur suivant.</span><span class="sxs-lookup"><span data-stu-id="773ca-136">Select the next vendor by clearing the vendor you have just entered the reply for and then selecting the row for the next vendor.</span></span>
2. <span data-ttu-id="773ca-137">Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="773ca-137">In the list, find and select the desired record.</span></span>
3. <span data-ttu-id="773ca-138">Cliquez sur Entrer une réponse.</span><span class="sxs-lookup"><span data-stu-id="773ca-138">Click Enter reply.</span></span>
4. <span data-ttu-id="773ca-139">Cliquez sur Copier des données dans la réponse.</span><span class="sxs-lookup"><span data-stu-id="773ca-139">Click Copy data to reply.</span></span>
5. <span data-ttu-id="773ca-140">Cliquez sur Modifier.</span><span class="sxs-lookup"><span data-stu-id="773ca-140">Click Edit.</span></span>
6. <span data-ttu-id="773ca-141">Entrez un nombre dans le champ Prix unitaire.</span><span class="sxs-lookup"><span data-stu-id="773ca-141">In the Unit price field, enter a number.</span></span>
7. <span data-ttu-id="773ca-142">Choisissez l'autre ligne de devis.</span><span class="sxs-lookup"><span data-stu-id="773ca-142">Choose the other quotation line.</span></span>
8. <span data-ttu-id="773ca-143">Entrez un nombre dans le champ Prix unitaire.</span><span class="sxs-lookup"><span data-stu-id="773ca-143">In the Unit price field, enter a number.</span></span>

## <a name="score-the-second-bid"></a><span data-ttu-id="773ca-144">Attribuer un score à la deuxième offre</span><span class="sxs-lookup"><span data-stu-id="773ca-144">Score the second bid</span></span>
1. <span data-ttu-id="773ca-145">Cliquez sur l'en-tête pour accéder à l'attribution de score de l'offre.</span><span class="sxs-lookup"><span data-stu-id="773ca-145">Click Header to go to scoring of the bid.</span></span>
2. <span data-ttu-id="773ca-146">Entrez un nombre dans le champ Score.</span><span class="sxs-lookup"><span data-stu-id="773ca-146">In the Score field, enter a number.</span></span>
3. <span data-ttu-id="773ca-147">Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="773ca-147">In the list, find and select the desired record.</span></span>
4. <span data-ttu-id="773ca-148">Entrez un nombre dans le champ Score.</span><span class="sxs-lookup"><span data-stu-id="773ca-148">In the Score field, enter a number.</span></span>

## <a name="compare-the-replies"></a><span data-ttu-id="773ca-149">Comparer les réponses</span><span class="sxs-lookup"><span data-stu-id="773ca-149">Compare the replies</span></span>
1. <span data-ttu-id="773ca-150">Cliquez sur Général dans le volet Actions.</span><span class="sxs-lookup"><span data-stu-id="773ca-150">On the Action Pane, click General.</span></span>
2. <span data-ttu-id="773ca-151">Cliquez sur Comparer les réponses.</span><span class="sxs-lookup"><span data-stu-id="773ca-151">Click Compare replies.</span></span>
3. <span data-ttu-id="773ca-152">Entrez un nombre dans le champ Rang.</span><span class="sxs-lookup"><span data-stu-id="773ca-152">In the Rank field, enter a number.</span></span>
    * <span data-ttu-id="773ca-153">Cette page affiche les offres avec l'en-tête et les lignes, et le score total au niveau de l'en-tête.</span><span class="sxs-lookup"><span data-stu-id="773ca-153">This page shows the bids with the header and lines, and the total score on the header level.</span></span> <span data-ttu-id="773ca-154">Vous pouvez comparer les lignes en effectuant un tri dans la grille afin que les lignes comparables soient les unes à côté des autres.</span><span class="sxs-lookup"><span data-stu-id="773ca-154">You can compare the lines by sorting in the grid so that comparable lines are next to each other.</span></span> <span data-ttu-id="773ca-155">Les informations incluent également : Quantité : Quantité faisant l'objet d'un devis d'un fournisseur.</span><span class="sxs-lookup"><span data-stu-id="773ca-155">The information also includes:   Quantity: The quantity quoted by the vendor.</span></span> <span data-ttu-id="773ca-156">Celle-ci peut ne pas être égale à la quantité indiquée dans l'appel d'offre.</span><span class="sxs-lookup"><span data-stu-id="773ca-156">This might not equal the quantity specified in the RFQ.</span></span>   <span data-ttu-id="773ca-157">Montant HT : Prix du devis d'un fournisseur, après soustraction de toutes les remises pour les articles de la ligne.</span><span class="sxs-lookup"><span data-stu-id="773ca-157">Net amount: The price quoted by a vendor, after subtracting any discounts, for the items on the line.</span></span>   <span data-ttu-id="773ca-158">Écart : Nombre de jours d'écart entre la date de livraison de l'en-tête ou la ligne de l'offre et la date de livraison de l'en-tête ou la ligne de l'appel d'offre.</span><span class="sxs-lookup"><span data-stu-id="773ca-158">Deviation: The number of days that the delivery date in the bid header or line deviates from the requested delivery date in the RFQ header or RFQ line.</span></span>   <span data-ttu-id="773ca-159">Vous pouvez entrer un classement pour chaque offre.</span><span class="sxs-lookup"><span data-stu-id="773ca-159">You can enter a rank for each bid.</span></span>  
4. <span data-ttu-id="773ca-160">Sélectionnez la ligne d'en-tête de l'autre offre que vous souhaitez classer.</span><span class="sxs-lookup"><span data-stu-id="773ca-160">Select the header line for the other bid that you want to rank.</span></span>
5. <span data-ttu-id="773ca-161">Entrez un nombre dans le champ Rang.</span><span class="sxs-lookup"><span data-stu-id="773ca-161">In the Rank field, enter a number.</span></span>
6. <span data-ttu-id="773ca-162">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="773ca-162">Click Save.</span></span>

## <a name="reject-a-bid"></a><span data-ttu-id="773ca-163">Rejeter une offre</span><span class="sxs-lookup"><span data-stu-id="773ca-163">Reject a bid</span></span>
1. <span data-ttu-id="773ca-164">Sélectionnez la ligne d'en-tête de l'autre offre que vous souhaitez rejeter.</span><span class="sxs-lookup"><span data-stu-id="773ca-164">Select the header line for the bid that you want to reject.</span></span>
    * <span data-ttu-id="773ca-165">Vous pouvez uniquement accepter, rejeter ou retourner une offre ou des lignes d'une offre à la fois.</span><span class="sxs-lookup"><span data-stu-id="773ca-165">You can only accept, reject, or return one bid or lines within one bid at a time.</span></span>  
2. <span data-ttu-id="773ca-166">Cochez la case Marquer.</span><span class="sxs-lookup"><span data-stu-id="773ca-166">Select the Mark check box.</span></span>
    * <span data-ttu-id="773ca-167">Si vous activez la case à cocher Marquer dans l'en-tête de l'offre, toutes les lignes sont également marquées.</span><span class="sxs-lookup"><span data-stu-id="773ca-167">If you select the Mark check box on the Header of the bid then all the lines will be marked as well.</span></span> <span data-ttu-id="773ca-168">Vous pouvez également choisir de marquer un sous-ensemble des lignes dans l'offre pour les refuser ou les recevoir.</span><span class="sxs-lookup"><span data-stu-id="773ca-168">You could also choose to mark a subset of the lines within the bid to reject or accept those.</span></span> <span data-ttu-id="773ca-169">Il est possible d'accepter l'offre d'un fournisseur pour certaines lignes d'un appel d'offre, puis d'attribuer d'autres lignes d'appel d'offre à un autre fournisseur, toutefois, vous devez procéder en 2 étapes, une offre à la fois.</span><span class="sxs-lookup"><span data-stu-id="773ca-169">It’s possible to accept one vendor’s bid for some lines of an RFQ, and then award other RFQ lines to a different vendor, however you need to do this in 2 steps, one bid at a time.</span></span> <span data-ttu-id="773ca-170">Si d'autres lignes sont présentes, vous pouvez uniquement accepter la ligne d'offre d'origine ou sa remplaçante, mais pas les deux.</span><span class="sxs-lookup"><span data-stu-id="773ca-170">If alternate lines are present, you can only accept either the original bid line or its alternate, but not both.</span></span>  
3. <span data-ttu-id="773ca-171">Cliquez sur Rejeter.</span><span class="sxs-lookup"><span data-stu-id="773ca-171">Click Reject.</span></span>
4. <span data-ttu-id="773ca-172">Cliquez sur Paramètres pour ouvrir la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="773ca-172">Click Parameters to open the drop dialog.</span></span>
5. <span data-ttu-id="773ca-173">Saisissez ou sélectionnez une valeur dans le champ Motif du refus.</span><span class="sxs-lookup"><span data-stu-id="773ca-173">In the Reason reject field, enter or select a value.</span></span>
    * <span data-ttu-id="773ca-174">Le motif du rejet sera stocké dans la réponse.</span><span class="sxs-lookup"><span data-stu-id="773ca-174">The reason for rejection will be stored on the reply.</span></span>  
6. <span data-ttu-id="773ca-175">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="773ca-175">Click OK.</span></span>
7. <span data-ttu-id="773ca-176">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="773ca-176">Click OK.</span></span>
8. <span data-ttu-id="773ca-177">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="773ca-177">Close the page.</span></span>
9. <span data-ttu-id="773ca-178">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="773ca-178">Close the page.</span></span>
10. <span data-ttu-id="773ca-179">Actualisez la page.</span><span class="sxs-lookup"><span data-stu-id="773ca-179">Refresh the page.</span></span>

## <a name="accept-a-bid"></a><span data-ttu-id="773ca-180">Accepter une offre</span><span class="sxs-lookup"><span data-stu-id="773ca-180">Accept a bid</span></span>
1. <span data-ttu-id="773ca-181">Sélectionnez l'offre à accepter, puis cliquez sur le lien dans le champ Appel d'offre.</span><span class="sxs-lookup"><span data-stu-id="773ca-181">Select the bid that you want to accept and then click the link in the Request for quotation field.</span></span>
2. <span data-ttu-id="773ca-182">Cliquez sur Répondre dans le volet Actions.</span><span class="sxs-lookup"><span data-stu-id="773ca-182">On the Action Pane, click Reply.</span></span>
3. <span data-ttu-id="773ca-183">Cliquez sur Accepter.</span><span class="sxs-lookup"><span data-stu-id="773ca-183">Click Accept.</span></span>
    * <span data-ttu-id="773ca-184">Si vous avez marqué des lignes spécifiques et pas d'autres, l'action d'acceptation va inclure seulement les lignes marquées.</span><span class="sxs-lookup"><span data-stu-id="773ca-184">If you have marked specific lines and not others then the accept action will only include the marked lines.</span></span> <span data-ttu-id="773ca-185">Si vous souhaitez accepter toutes les lignes de l'offre, vous ne devez pas marquer de lignes.</span><span class="sxs-lookup"><span data-stu-id="773ca-185">If you want to accept all lines on the bid then you do not have to mark the lines.</span></span>  
4. <span data-ttu-id="773ca-186">Cliquez sur Paramètres pour ouvrir la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="773ca-186">Click Parameters to open the drop dialog.</span></span>
    * <span data-ttu-id="773ca-187">Cela vous permet d'enregistrer un motif d'acceptation de l'offre.</span><span class="sxs-lookup"><span data-stu-id="773ca-187">This allows you to record a reason for accepting the bid.</span></span> <span data-ttu-id="773ca-188">Le motif sera stocké dans l'offre.</span><span class="sxs-lookup"><span data-stu-id="773ca-188">The reason will be stored on the bid.</span></span>  
5. <span data-ttu-id="773ca-189">Saisissez ou sélectionnez une valeur dans le champ Motif d'acceptation.</span><span class="sxs-lookup"><span data-stu-id="773ca-189">In the Reason accept field, enter or select a value.</span></span>
6. <span data-ttu-id="773ca-190">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="773ca-190">Click OK.</span></span>
7. <span data-ttu-id="773ca-191">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="773ca-191">Click OK.</span></span>
    * <span data-ttu-id="773ca-192">Lorsque vous cliquez sur OK, cela génère une commande fournisseur basée sur les lignes incluses dans l'acceptation d'appel d'offre.</span><span class="sxs-lookup"><span data-stu-id="773ca-192">When you click OK this generates a purchase order based on the lines that are included in the RFQ acceptance.</span></span> <span data-ttu-id="773ca-193">S'il existe d'autres offres qui n'ont pas été traitées (acceptées, rejetées ou retournées), alors le système vous invite à rejeter les offres restantes.</span><span class="sxs-lookup"><span data-stu-id="773ca-193">If there are other bids that have not been processed (accepted, rejected, or returned) then the system will prompt you to reject the remaining bids.</span></span>  

## <a name="view-the-purchase-order-thats-been-generated"></a><span data-ttu-id="773ca-194">Afficher la commande fournisseur générée</span><span class="sxs-lookup"><span data-stu-id="773ca-194">View the purchase order that's been generated</span></span>
1. <span data-ttu-id="773ca-195">Cliquez sur Général dans le volet Actions.</span><span class="sxs-lookup"><span data-stu-id="773ca-195">On the Action Pane, click General.</span></span>
2. <span data-ttu-id="773ca-196">Cliquez sur Commande fournisseur.</span><span class="sxs-lookup"><span data-stu-id="773ca-196">Click Purchase order.</span></span>
    * <span data-ttu-id="773ca-197">Ici vous pouvez voir la commande fournisseur générée lorsque vous avez accepté l'offre.</span><span class="sxs-lookup"><span data-stu-id="773ca-197">Here you can see the purchase order that was generated when you accepted the bid.</span></span>  
3. <span data-ttu-id="773ca-198">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="773ca-198">Close the page.</span></span>
4. <span data-ttu-id="773ca-199">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="773ca-199">Close the page.</span></span>
5. <span data-ttu-id="773ca-200">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="773ca-200">Close the page.</span></span>
6. <span data-ttu-id="773ca-201">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="773ca-201">Close the page.</span></span>


