---
title: Entrer et comparer des appels d'offre et octroyer des contrats
description: Cette procédure décrit comment entrer des réponses à un appel d'offre, marquer et comparer les offres, puis attribuer le contrat à l'un des fournisseurs.
author: mkirknel
manager: AnnBe
ms.date: 02/26/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: PurchRFQCaseTableListPage, PurchRFQCaseTable, PurchRFQReplyTable, PurchRFQCompare, PurchRFQEditLines, PurchRFQEditLinesParameters, PurchTable
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 45ddab03810b331bcd8965f6a2ba699ffb138910
ms.sourcegitcommit: 2b890cd7a801055ab0ca24398efc8e4e777d4d8c
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/07/2019
ms.locfileid: "1533350"
---
# <a name="enter-and-compare-rfq-bids-and-award-contracts"></a><span data-ttu-id="7c2fa-103">Entrer et comparer des appels d'offre et octroyer des contrats</span><span class="sxs-lookup"><span data-stu-id="7c2fa-103">Enter and compare RFQ bids, and award contracts</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="7c2fa-104">Cette procédure décrit comment entrer des réponses à un appel d'offre, marquer et comparer les offres que vous recevez, puis attribuer le contrat à l'un des fournisseurs ayant fait une offre.</span><span class="sxs-lookup"><span data-stu-id="7c2fa-104">This procedure shows how to enter replies to a request for quotation (RFQ), score and compare bids that you receive, and then award the contract to one of the vendors who submitted bids.</span></span> <span data-ttu-id="7c2fa-105">Vous pouvez utiliser cette procédure dans les données fictives de la société **USMF**.</span><span class="sxs-lookup"><span data-stu-id="7c2fa-105">You can use this procedure in the **USMF** demo data company.</span></span>

<span data-ttu-id="7c2fa-106">Avant de commencer cette procédure, vous devez avoir un appel d'offre avec deux lignes et qui a été envoyé au moins à deux fournisseurs.</span><span class="sxs-lookup"><span data-stu-id="7c2fa-106">Before you start this procedure, you must have an RFQ that has two lines, and that has been sent to at least two vendors.</span></span> <span data-ttu-id="7c2fa-107">Pour créer cet appel d'offre, suivez la procédure [Créer un appel d'offre](create-request-quotation.md).</span><span class="sxs-lookup"><span data-stu-id="7c2fa-107">To create this RFQ, complete the [Create a request for quotation](create-request-quotation.md) procedure.</span></span> <span data-ttu-id="7c2fa-108">Des critères d'attribution de score doivent également avoir été paramétrés pour pouvoir exécuter cette procédure.</span><span class="sxs-lookup"><span data-stu-id="7c2fa-108">Scoring criteria must also be set up before you can complete this procedure.</span></span>

<span data-ttu-id="7c2fa-109">Vous pouvez entrer l'offre comme fournisseur ou professionnel des approvisionnements.</span><span class="sxs-lookup"><span data-stu-id="7c2fa-109">You can enter the bid as either a vendor or a procurement professional.</span></span> <span data-ttu-id="7c2fa-110">Pour plus d'informations, voir [Paramétrer et mettre à jour la collaboration fournisseur](../set-up-maintain-vendor-collaboration.md).</span><span class="sxs-lookup"><span data-stu-id="7c2fa-110">For more information, see [Set up and maintain vendor collaboration](../set-up-maintain-vendor-collaboration.md).</span></span>

## <a name="enter-a-reply-as-a-vendor"></a><span data-ttu-id="7c2fa-111">Entrer la réponse en tant que fournisseur</span><span class="sxs-lookup"><span data-stu-id="7c2fa-111">Enter a reply as a vendor</span></span>

1. <span data-ttu-id="7c2fa-112">Sur le tableau de bord, sélectionnez **Offre du fournisseur**.</span><span class="sxs-lookup"><span data-stu-id="7c2fa-112">On the dashboard, select **Vendor bidding**.</span></span>
2. <span data-ttu-id="7c2fa-113">Dans la liste **Nouvelles invitations à une offre**, recherchez un appel d'offre qui vient juste d'être envoyé.</span><span class="sxs-lookup"><span data-stu-id="7c2fa-113">In the **New bid invitations** list, find an RFQ that was just sent.</span></span> <span data-ttu-id="7c2fa-114">Sélectionnez l'appel d'offre pour examiner ce qui a été demandé.</span><span class="sxs-lookup"><span data-stu-id="7c2fa-114">Select the RFQ to review what was requested.</span></span>
3. <span data-ttu-id="7c2fa-115">Sélectionnez **Pièces jointes à l'appel d'offre** pour examiner les pièces jointes ayant été ajoutées.</span><span class="sxs-lookup"><span data-stu-id="7c2fa-115">Select **RFQ attachments** to review any attachments that have been added.</span></span>
4. <span data-ttu-id="7c2fa-116">Sélectionnez **Offre** pour rendre les champs modifiables.</span><span class="sxs-lookup"><span data-stu-id="7c2fa-116">Select **Bid** to make the fields editable.</span></span> <span data-ttu-id="7c2fa-117">Notez que le champ **Progression de l'offre** est défini sur **Le fournisseur effectue une mise à jour**.</span><span class="sxs-lookup"><span data-stu-id="7c2fa-117">Notice that the **Bid progress** field is set to **Vendor is updating**.</span></span>
5. <span data-ttu-id="7c2fa-118">Sur l'en-tête et les lignes, entrez les valeurs de la réponse à l'offre.</span><span class="sxs-lookup"><span data-stu-id="7c2fa-118">On the header and lines, enter the values from the bid reply.</span></span>
6. <span data-ttu-id="7c2fa-119">Si des pièces jointes doivent être ajoutées à l'offre, sélectionnez **Pièces jointes à l'offre**.</span><span class="sxs-lookup"><span data-stu-id="7c2fa-119">If any attachments should be added to the bid, select **Bid attachments**.</span></span>
7. <span data-ttu-id="7c2fa-120">Sélectionnez l'organisateur **Instructions de soumission** pour afficher si des documents sont requis.</span><span class="sxs-lookup"><span data-stu-id="7c2fa-120">Select the **Bidding guiding items** FastTab to view whether any documents are required.</span></span>
8. <span data-ttu-id="7c2fa-121">Sélectionnez l'organisateur **Avenants** pour afficher si l'appel d'offre a été modifié.</span><span class="sxs-lookup"><span data-stu-id="7c2fa-121">Select the **Amendments** FastTab to view whether the RFQ has been amended.</span></span>
9. <span data-ttu-id="7c2fa-122">Sélectionnez l'organisateur **Questionnaire**.</span><span class="sxs-lookup"><span data-stu-id="7c2fa-122">Select the **Questionnaire** FastTab.</span></span> <span data-ttu-id="7c2fa-123">Tous les questionnaires qui apparaissent ici doivent être remplis.</span><span class="sxs-lookup"><span data-stu-id="7c2fa-123">Any questionnaires that appear here must be answered.</span></span>
10. <span data-ttu-id="7c2fa-124">Sélectionnez l'organisateur **Détails de la ligne** pour afficher des informations supplémentaires sur la ligne.</span><span class="sxs-lookup"><span data-stu-id="7c2fa-124">Select the **Line details** FastTab to view extended information about the line.</span></span>
11. <span data-ttu-id="7c2fa-125">Sélectionnez **Réinitialiser à partir de l'appel d'offre** uniquement si vous devez réinitialisé les valeurs entrées dans les valeurs d'appel d'offre d'origine.</span><span class="sxs-lookup"><span data-stu-id="7c2fa-125">Select **Reset from RFQ** only if you must reset the values that have been entered to the original RFQ values.</span></span>
12. <span data-ttu-id="7c2fa-126">Vous pouvez enregistrer l'offre à tout moment et effectuer un traitement supplémentaire ultérieurement, avant que la date et l'heure d'expiration se soient écoulées.</span><span class="sxs-lookup"><span data-stu-id="7c2fa-126">You can save the bid at any time and do additional processing later, provided that the expiration date and time haven't passed.</span></span> <span data-ttu-id="7c2fa-127">Dans ce cas, vous pouvez trouver l'offre dans la liste **Offres en cours** dans l'espace de travail **Offre du fournisseur**.</span><span class="sxs-lookup"><span data-stu-id="7c2fa-127">In this case, you can find the bid in the **Bids in progress** list in the **Vendor bidding** workspace.</span></span>
13. <span data-ttu-id="7c2fa-128">Lorsque l'offre est prête à être soumise, sélectionnez **Soumettre**.</span><span class="sxs-lookup"><span data-stu-id="7c2fa-128">When the bid is ready to be sent, select **Submit**.</span></span> <span data-ttu-id="7c2fa-129">Si vous ne souhaitez pas faire d'offre, sélectionnez **Refuser**.</span><span class="sxs-lookup"><span data-stu-id="7c2fa-129">If you don't want to bid, select **Decline**.</span></span>

    <span data-ttu-id="7c2fa-130">Les offres envoyées sont disponibles dans la liste **Offres envoyées** de l'espace de travail **Offre du fournisseur**.</span><span class="sxs-lookup"><span data-stu-id="7c2fa-130">Submitted bids are available in the **Submitted bids** list in the **Vendor bidding** workspace.</span></span>

14. <span data-ttu-id="7c2fa-131">Une fois l'offre soumise, vous pouvez la rappeler à tout moment avant la date et l'heure d'expiration.</span><span class="sxs-lookup"><span data-stu-id="7c2fa-131">After the bid is submitted, you can recall it at any time before the expiration date and time.</span></span> <span data-ttu-id="7c2fa-132">Notez que lorsqu'une offre est rappelée, elle n'est pas traitée comme soumise.</span><span class="sxs-lookup"><span data-stu-id="7c2fa-132">Note that when a bid is recalled, it isn't treated as submitted.</span></span>

    <span data-ttu-id="7c2fa-133">Lorsque l'offre est acceptée ou refusée par département d'approvisionnement, elle apparaît dans **Offres attribuées** ou **Offres perdues** dans l'espace de travail **Offre du fournisseur**.</span><span class="sxs-lookup"><span data-stu-id="7c2fa-133">When the bid is accepted or rejected by the procurement department, it appears in either the **Awarded bids** or **Lost bids** list in the **Vendor bidding** workspace.</span></span>

## <a name="enter-a-reply-from-a-vendor-as-a-procurement-professional"></a><span data-ttu-id="7c2fa-134">Entrer une réponse d'un fournisseur en tant professionnel de l'approvisionnement</span><span class="sxs-lookup"><span data-stu-id="7c2fa-134">Enter a reply from a vendor as a procurement professional</span></span>

1. <span data-ttu-id="7c2fa-135">Assurez-vous que l'autorisation de modifier les offres du fournisseur est paramétrée.</span><span class="sxs-lookup"><span data-stu-id="7c2fa-135">Make sure that the permission to edit vendor bids is set up.</span></span> <span data-ttu-id="7c2fa-136">Accédez à **Approvisionnements \> Paramétrage \> Paramètres d'approvisionnements**.</span><span class="sxs-lookup"><span data-stu-id="7c2fa-136">Go to **Procurement and sourcing \> Setup \> Procurement and sourcing parameters**.</span></span> <span data-ttu-id="7c2fa-137">Dans l'onglet **Appels d'offre**, définissez l'option **L'acheteur peut modifier l'offre des fournisseurs** sur **Oui**.</span><span class="sxs-lookup"><span data-stu-id="7c2fa-137">On the **Request for quotations** tab, set the **Purchaser can edit vendors bid** option to **Yes**.</span></span>
2. <span data-ttu-id="7c2fa-138">Accédez à **Approvisionnements \> Appels d'offre \> Toutes les demandes de devis**.</span><span class="sxs-lookup"><span data-stu-id="7c2fa-138">Go to **Procurement and sourcing \> Requests for quotations \> All requests for quotations**.</span></span>
3. <span data-ttu-id="7c2fa-139">Sélectionnez un appel d'offre ayant le statut **Envoyé**, puis sélectionnez le lien dans le champ **Dossier d'appel d'offre**.</span><span class="sxs-lookup"><span data-stu-id="7c2fa-139">Select an RFQ that has a status of **Sent**, and then select the link in the **Request for quotation case** field.</span></span>
4. <span data-ttu-id="7c2fa-140">Sélectionnez **Gérer les réponses**.</span><span class="sxs-lookup"><span data-stu-id="7c2fa-140">Select **Manage replies**.</span></span> <span data-ttu-id="7c2fa-141">La page qui apparaît présente un appel d'offre pour chaque fournisseur invité à faire une offre.</span><span class="sxs-lookup"><span data-stu-id="7c2fa-141">The page that appears shows an RFQ for each vendor that was invited to bid.</span></span>
5. <span data-ttu-id="7c2fa-142">Sélectionnez un appel d'offre qui n'a pas reçu de réponse.</span><span class="sxs-lookup"><span data-stu-id="7c2fa-142">Select an RFQ that hasn't been replied to.</span></span> <span data-ttu-id="7c2fa-143">(Le champ **Progression de la réponse** devrait être défini sur **Non commencé**.)</span><span class="sxs-lookup"><span data-stu-id="7c2fa-143">(The **Reply progress** field should be set to **Not started**.)</span></span>
6. <span data-ttu-id="7c2fa-144">Sélectionnez **Modifier \> Modifier la réponse à l'appel d'offre**.</span><span class="sxs-lookup"><span data-stu-id="7c2fa-144">Select **Edit \> Edit RFQ reply**.</span></span>

    <span data-ttu-id="7c2fa-145">La page **Modifier la réponse** s'affiche.</span><span class="sxs-lookup"><span data-stu-id="7c2fa-145">The **RFQ reply** page appears.</span></span> <span data-ttu-id="7c2fa-146">En tant que professionnel des approvisionnements, vous pouvez désormais entrer la réponse au nom du fournisseur.</span><span class="sxs-lookup"><span data-stu-id="7c2fa-146">As a procurement professional, you can now enter the reply on behalf of the vendor.</span></span> <span data-ttu-id="7c2fa-147">Notez que le champ **Progression de l'offre** est défini sur **L'acheteur effectue une mise à jour**.</span><span class="sxs-lookup"><span data-stu-id="7c2fa-147">Notice that the **Bid progress** field is set to **Purchaser is updating**.</span></span>

7. <span data-ttu-id="7c2fa-148">Entrez les données de l'offre.</span><span class="sxs-lookup"><span data-stu-id="7c2fa-148">Enter the bid data.</span></span> <span data-ttu-id="7c2fa-149">Lorsque vous avez terminé, sélectionnez **Soumettre**.</span><span class="sxs-lookup"><span data-stu-id="7c2fa-149">When you've finished, select **Submit**.</span></span>

## <a name="score-the-bids"></a><span data-ttu-id="7c2fa-150">Attribuer un score aux offres</span><span class="sxs-lookup"><span data-stu-id="7c2fa-150">Score the bids</span></span>

1. <span data-ttu-id="7c2fa-151">Dans la page **Toutes les demandes de devis**, sélectionnez le dossier d'appel d'offre auquel vous souhaitez attribuer des points pour les réponses.</span><span class="sxs-lookup"><span data-stu-id="7c2fa-151">On the **All requests for quotations** page, select the RFQ case that you want to score replies for.</span></span>
2. <span data-ttu-id="7c2fa-152">Sélectionnez **Gérer les réponses**.</span><span class="sxs-lookup"><span data-stu-id="7c2fa-152">Select **Manage replies**.</span></span>
3. <span data-ttu-id="7c2fa-153">Sélectionnez la réponse à laquelle attribuer des points.</span><span class="sxs-lookup"><span data-stu-id="7c2fa-153">Select the reply to score.</span></span>
4. <span data-ttu-id="7c2fa-154">Sélectionnez **En-tête** afin de pouvoir afficher les points obtenus par l'offre.</span><span class="sxs-lookup"><span data-stu-id="7c2fa-154">Select **Header** so that you can view the scoring for the bid.</span></span>
5. <span data-ttu-id="7c2fa-155">Sur l'organisateur **Attribution de score de l'offre**, entrez un nombre dans le champ **Score** pour l'un des critères d'attribution de score.</span><span class="sxs-lookup"><span data-stu-id="7c2fa-155">On the **Bid scoring** FastTab, enter a number in the **Score** field for one of the scoring criteria.</span></span>

    <span data-ttu-id="7c2fa-156">Si vous passez la souris sur l'un des critères d'attribution de score, une info-bulle indique la plage dans laquelle doit se trouver le score.</span><span class="sxs-lookup"><span data-stu-id="7c2fa-156">If you hover over a scoring criterion, a tooltip shows the range that the score must be within.</span></span> <span data-ttu-id="7c2fa-157">Dans cette démonstration, vous pouvez entrer un nombre compris entre 1 et 5 à n'importe lequel des critères d'attribution de score.</span><span class="sxs-lookup"><span data-stu-id="7c2fa-157">In this demo, you can enter a number between 1 and 5 for any of the scoring criteria.</span></span>

6. <span data-ttu-id="7c2fa-158">Répétez l'étape 5 pour un autre critère d'attribution de score.</span><span class="sxs-lookup"><span data-stu-id="7c2fa-158">Repeat step 5 for another scoring criterion.</span></span>
7. <span data-ttu-id="7c2fa-159">Si le dossier d'appel d'offre a un questionnaire qui a été soumis aux fournisseurs, vous pouvez entrer leurs réponses sur l'organisateur **Questionnaires**.</span><span class="sxs-lookup"><span data-stu-id="7c2fa-159">If the RFQ case has a questionnaire that was sent to the vendors, you can enter the vendor responses on the **Questionnaires** FastTab.</span></span>
8. <span data-ttu-id="7c2fa-160">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="7c2fa-160">Close the page.</span></span>
9. <span data-ttu-id="7c2fa-161">Répétez les étapes 1 à 8 pour toutes les autres offres.</span><span class="sxs-lookup"><span data-stu-id="7c2fa-161">Repeat steps 1 through 8 for all the other bids.</span></span>

## <a name="compare-the-replies"></a><span data-ttu-id="7c2fa-162">Comparer les réponses</span><span class="sxs-lookup"><span data-stu-id="7c2fa-162">Compare the replies</span></span>

1. <span data-ttu-id="7c2fa-163">Dans le volet Actions, sous l'onglet **Général**, sélectionnez **Comparer les réponses**.</span><span class="sxs-lookup"><span data-stu-id="7c2fa-163">On the Action Pane, on the **General** tab, select **Compare replies**.</span></span>
2. <span data-ttu-id="7c2fa-164">Dans le champ **Rang**, entrez un nombre.</span><span class="sxs-lookup"><span data-stu-id="7c2fa-164">In the **Rank** field, enter a number.</span></span>

    <span data-ttu-id="7c2fa-165">Cette page affiche les offres avec les informations d'en-tête et de ligne, ainsi que le score total au niveau de l'en-tête.</span><span class="sxs-lookup"><span data-stu-id="7c2fa-165">This page shows the bids, together with the header and line information, and also the total score at the header level.</span></span> <span data-ttu-id="7c2fa-166">Vous pouvez comparer les lignes en effectuant un tri dans la grille afin que les lignes comparables soient les unes à côté des autres.</span><span class="sxs-lookup"><span data-stu-id="7c2fa-166">You can compare the lines by sorting the grid so that comparable lines are next to each other.</span></span> <span data-ttu-id="7c2fa-167">Les informations suivantes sont également incluses :</span><span class="sxs-lookup"><span data-stu-id="7c2fa-167">The following information is also included:</span></span>

    - <span data-ttu-id="7c2fa-168">**Quantité** – Quantité ayant fait l'objet du devis du fournisseur.</span><span class="sxs-lookup"><span data-stu-id="7c2fa-168">**Quantity** – The quantity that the vendor quoted.</span></span> <span data-ttu-id="7c2fa-169">Cette quantité peut ne pas être égale à la quantité indiquée dans l'appel d'offre.</span><span class="sxs-lookup"><span data-stu-id="7c2fa-169">This quantity might not equal the quantity that is specified in the RFQ.</span></span>
    - <span data-ttu-id="7c2fa-170">**Montant net** – Prix du devis du fournisseur pour les articles de la ligne, après soustraction de toutes les remises.</span><span class="sxs-lookup"><span data-stu-id="7c2fa-170">**Net amount** – The price that the vendor quoted for the items on the line, minus any discounts.</span></span>
    - <span data-ttu-id="7c2fa-171">**Écart** – Nombre de jours d'écart entre la date de livraison de l'en-tête ou la ligne de l'offre et la date de livraison de l'en-tête ou la ligne de l'appel d'offre.</span><span class="sxs-lookup"><span data-stu-id="7c2fa-171">**Deviation** – The number of days by which the delivery date on the bid header or line differs from the requested delivery date on the RFQ header or line.</span></span> <span data-ttu-id="7c2fa-172">Vous pouvez entrer un classement pour chaque offre.</span><span class="sxs-lookup"><span data-stu-id="7c2fa-172">You can enter a rank for each bid.</span></span>

3. <span data-ttu-id="7c2fa-173">Sélectionnez la ligne d'en-tête de l'autre offre que vous souhaitez classer.</span><span class="sxs-lookup"><span data-stu-id="7c2fa-173">Select the header line for the other bid that you want to rank.</span></span>
4. <span data-ttu-id="7c2fa-174">Dans le champ **Rang**, entrez un nombre.</span><span class="sxs-lookup"><span data-stu-id="7c2fa-174">In the **Rank** field, enter a number.</span></span>
5. <span data-ttu-id="7c2fa-175">Sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="7c2fa-175">Select **Save**.</span></span>

## <a name="reject-a-bid"></a><span data-ttu-id="7c2fa-176">Rejeter une offre</span><span class="sxs-lookup"><span data-stu-id="7c2fa-176">Reject a bid</span></span>

1. <span data-ttu-id="7c2fa-177">Sélectionnez la ligne d'en-tête de l'autre offre que vous souhaitez rejeter.</span><span class="sxs-lookup"><span data-stu-id="7c2fa-177">Select the header line for the bid that you want to reject.</span></span>

    <span data-ttu-id="7c2fa-178">Vous pouvez accepter, rejeter ou retourner uniquement une offre ou les lignes d'une offre à la fois.</span><span class="sxs-lookup"><span data-stu-id="7c2fa-178">You can accept, reject, or return only one bid or the lines on only one bid at a time.</span></span>

2. <span data-ttu-id="7c2fa-179">Activez la case à cocher **Marquer**.</span><span class="sxs-lookup"><span data-stu-id="7c2fa-179">Select the **Mark** check box.</span></span>

    <span data-ttu-id="7c2fa-180">Si vous activez la case à cocher **Marquer** dans l'en-tête de l'offre, toutes les lignes sont également marquées.</span><span class="sxs-lookup"><span data-stu-id="7c2fa-180">If you select the **Mark** check box on the header of the bid, all the lines are also marked.</span></span> <span data-ttu-id="7c2fa-181">Pour rejeter ou accepter uniquement certaines lignes sous l'offre, vous pouvez marquer juste ces lignes.</span><span class="sxs-lookup"><span data-stu-id="7c2fa-181">To reject or accept only some of the lines on the bid, you can mark just those lines.</span></span> <span data-ttu-id="7c2fa-182">De plus, vous pouvez accepter l'offre d'un fournisseur pour certaines lignes d'un appel d'offre, puis attribuer d'autres lignes d'appel d'offre à un autre fournisseur.</span><span class="sxs-lookup"><span data-stu-id="7c2fa-182">Additionally, you can accept one vendor's bid for some lines of an RFQ and then award other RFQ lines to a different vendor.</span></span> <span data-ttu-id="7c2fa-183">Toutefois, vous devez effectuer une offre à la fois.</span><span class="sxs-lookup"><span data-stu-id="7c2fa-183">However, you must do one bid at a time.</span></span>

    <span data-ttu-id="7c2fa-184">Si d'autres lignes sont présentes, vous pouvez accepter la ligne d'offre d'origine ou sa remplaçante, mais pas les deux.</span><span class="sxs-lookup"><span data-stu-id="7c2fa-184">If alternate lines are present, you can accept either the original bid line or its alternate, but not both.</span></span>

3. <span data-ttu-id="7c2fa-185">Sélectionnez **Refuser**.</span><span class="sxs-lookup"><span data-stu-id="7c2fa-185">Select **Reject**.</span></span>
4. <span data-ttu-id="7c2fa-186">Sélectionnez **Paramètres**, puis, dans le champ **Motif du refus**, entrez ou sélectionnez le motif du refus de l'offre.</span><span class="sxs-lookup"><span data-stu-id="7c2fa-186">Select **Parameters**, and then, in the **Reason reject** field, enter or select your reason for rejecting the bid.</span></span>

    <span data-ttu-id="7c2fa-187">Le motif est enregistré dans la réponse.</span><span class="sxs-lookup"><span data-stu-id="7c2fa-187">The reason is stored in the reply.</span></span>

5. <span data-ttu-id="7c2fa-188">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="7c2fa-188">Select **OK**.</span></span>
6. <span data-ttu-id="7c2fa-189">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="7c2fa-189">Select **OK**.</span></span>

## <a name="accept-a-bid"></a><span data-ttu-id="7c2fa-190">Accepter une offre</span><span class="sxs-lookup"><span data-stu-id="7c2fa-190">Accept a bid</span></span>

1. <span data-ttu-id="7c2fa-191">Sélectionnez l'offre à accepter, puis le lien dans le champ **Appel d'offre**.</span><span class="sxs-lookup"><span data-stu-id="7c2fa-191">Select the bid to accept, and then select the link in the **Request for quotation** field.</span></span>

    <span data-ttu-id="7c2fa-192">Si vous êtes sur la page **Comparer les réponses aux appels d'offre**, l'offre en surbrillance est l'offre que le système prendra en compte pendant l'action Accepter.</span><span class="sxs-lookup"><span data-stu-id="7c2fa-192">If you're on the **Compare request for quotation replies** page, the highlighted bid that has focus is the bid that the system will consider during the Accept action.</span></span> <span data-ttu-id="7c2fa-193">Vous pouvez accepter les lignes d'une seule offre à la fois.</span><span class="sxs-lookup"><span data-stu-id="7c2fa-193">You can accept lines from only one bid at a time.</span></span>

2. <span data-ttu-id="7c2fa-194">Dans le volet Actions, sélectionnez **Répondre**.</span><span class="sxs-lookup"><span data-stu-id="7c2fa-194">On the Action Pane, select **Reply**.</span></span>
3. <span data-ttu-id="7c2fa-195">Sélectionner **Accepter**.</span><span class="sxs-lookup"><span data-stu-id="7c2fa-195">Select **Accept**.</span></span>

    <span data-ttu-id="7c2fa-196">Si vous avez marqué uniquement des lignes spécifiques, l'action Accepter inclut uniquement ces lignes.</span><span class="sxs-lookup"><span data-stu-id="7c2fa-196">If you marked only specific lines, the Accept action will include only those lines.</span></span> <span data-ttu-id="7c2fa-197">Si vous souhaitez accepter toutes les lignes de l'offre, vous n'avez pas besoin de marquer les lignes.</span><span class="sxs-lookup"><span data-stu-id="7c2fa-197">If you want to accept all the lines on the bid, you don't have to mark the lines.</span></span>

4. <span data-ttu-id="7c2fa-198">Sélectionnez **Paramètres**, puis, dans le champ **Motif d'acceptation**, entrez ou sélectionnez le motif de l'acceptation de l'offre.</span><span class="sxs-lookup"><span data-stu-id="7c2fa-198">Select **Parameters**, and then, in the **Reason accept** field, enter or select your reason for accepting the bid.</span></span>

    <span data-ttu-id="7c2fa-199">Le motif est enregistré dans l'offre.</span><span class="sxs-lookup"><span data-stu-id="7c2fa-199">The reason is stored in the bid.</span></span>

5. <span data-ttu-id="7c2fa-200">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="7c2fa-200">Select **OK**.</span></span>
6. <span data-ttu-id="7c2fa-201">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="7c2fa-201">Select **OK**.</span></span>

    <span data-ttu-id="7c2fa-202">Lorsque vous sélectionnez **OK**, une commande fournisseur est générée sur la base sur les lignes incluses dans l'acceptation d'appel d'offre.</span><span class="sxs-lookup"><span data-stu-id="7c2fa-202">When you select **OK**, a purchase order is generated based on the lines that are included in the RFQ acceptance.</span></span> <span data-ttu-id="7c2fa-203">S'il existe d'autres offres qui n'ont pas été traitées (acceptées, rejetées ou retournées), le système vous invite à les rejeter.</span><span class="sxs-lookup"><span data-stu-id="7c2fa-203">If there are other bids that haven't been processed (accepted, rejected, or returned), the system prompts you to reject them.</span></span>

## <a name="view-the-purchase-order-that-is-generated"></a><span data-ttu-id="7c2fa-204">Afficher la commande fournisseur générée</span><span class="sxs-lookup"><span data-stu-id="7c2fa-204">View the purchase order that is generated</span></span>

- <span data-ttu-id="7c2fa-205">Dans le volet Actions, sous l'onglet **Général**, sélectionnez **Commande fournisseur**.</span><span class="sxs-lookup"><span data-stu-id="7c2fa-205">On the Action Pane, on the **General** tab, select **Purchase order**.</span></span>

    <span data-ttu-id="7c2fa-206">La page qui s'affiche indique la commande fournisseur générée lorsque vous avez accepté l'offre.</span><span class="sxs-lookup"><span data-stu-id="7c2fa-206">The page that appears shows the purchase order that was generated when you accepted the bid.</span></span>
