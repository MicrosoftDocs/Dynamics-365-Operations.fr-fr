---
title: Transaction de lettre de garantie
description: Cette procédure décrit le processus associé à une lettre de garantie.
author: kweekley
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: Reasons, SalesTableListPage, SalesCreateOrder, SalesTable, BankLGRequestForm, BankLGRequestFormRequest, BankLGGuarantee, BankLGFormSubmitToBank, BankDocumentAgreementLineLookup, BankLGFormReceiveFromBank, LedgerJournalTable, LedgerJournalTransDaily, BankLGRequestFormGiveToBeneficiary, BankLGFormGiveToBeneficiary, BankLGRequestFormIncreaseValue, BankLGFormIncreaseValue, BankLGRequestFormLiquidate, BankLGFormLiquidate
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 05abad6898c2b97cf66abdff21b30407dacd6488
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4443266"
---
# <a name="letter-of-guarantee-transaction"></a><span data-ttu-id="763c7-103">Transaction de lettre de garantie</span><span class="sxs-lookup"><span data-stu-id="763c7-103">Letter of guarantee transaction</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="763c7-104">Cette procédure décrit le processus associé à une lettre de garantie.</span><span class="sxs-lookup"><span data-stu-id="763c7-104">This procedure walks through the Letter of guarantee process.</span></span>



<span data-ttu-id="763c7-105">Les tâches suivantes doivent être terminées avant d’effectuer cette procédure :</span><span class="sxs-lookup"><span data-stu-id="763c7-105">The following tasks must be complete before completing this procedure:</span></span>

- <span data-ttu-id="763c7-106">Paramétrer les établissements et les profils de validation pour une lettre de garantie.</span><span class="sxs-lookup"><span data-stu-id="763c7-106">Set up bank facilities and posting profiles for a letter of guarantee.</span></span>

- <span data-ttu-id="763c7-107">Créer un accord d’établissement bancaire pour une lettre de garantie.</span><span class="sxs-lookup"><span data-stu-id="763c7-107">Create a bank facility agreement for a letter of guarantee.</span></span>



<span data-ttu-id="763c7-108">La société fictive USMF sert d’exemple dans cette procédure.</span><span class="sxs-lookup"><span data-stu-id="763c7-108">This procedure uses the USMF demo company.</span></span>


## <a name="create-sales-order-with-letter-of-guarantee"></a><span data-ttu-id="763c7-109">Créer une commande client avec une lettre de garantie</span><span class="sxs-lookup"><span data-stu-id="763c7-109">Create Sales Order with Letter of Guarantee</span></span>
1. <span data-ttu-id="763c7-110">Accédez à Comptabilité client > Commandes > Toutes les commandes client.</span><span class="sxs-lookup"><span data-stu-id="763c7-110">Go to Accounts receivable > Orders > All sales orders.</span></span>
2. <span data-ttu-id="763c7-111">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="763c7-111">Click New.</span></span>
3. <span data-ttu-id="763c7-112">Entrez ou sélectionnez une valeur dans le champ Compte client.</span><span class="sxs-lookup"><span data-stu-id="763c7-112">In the Customer account field, enter or select a value.</span></span>
4. <span data-ttu-id="763c7-113">Développez la section Général.</span><span class="sxs-lookup"><span data-stu-id="763c7-113">Expand the General section.</span></span>
5. <span data-ttu-id="763c7-114">Saisissez ou sélectionnez une valeur dans le champ Site.</span><span class="sxs-lookup"><span data-stu-id="763c7-114">In the Site field, enter or select a value.</span></span>
6. <span data-ttu-id="763c7-115">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="763c7-115">In the list, click the link in the selected row.</span></span>
7. <span data-ttu-id="763c7-116">Dans le champ Entrepôt, saisissez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="763c7-116">In the Warehouse field, enter or select a value.</span></span>
8. <span data-ttu-id="763c7-117">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="763c7-117">In the list, click the link in the selected row.</span></span>
9. <span data-ttu-id="763c7-118">Dans le champ Type de document bancaire, sélectionnez « Lettre de garantie ».</span><span class="sxs-lookup"><span data-stu-id="763c7-118">In the Bank document type field, select 'Letter of guarantee'.</span></span>
10. <span data-ttu-id="763c7-119">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="763c7-119">Click OK.</span></span>
11. <span data-ttu-id="763c7-120">Entrez ou sélectionnez une valeur dans le champ Numéro d’article.</span><span class="sxs-lookup"><span data-stu-id="763c7-120">In the Item number field, enter or select a value.</span></span>
12. <span data-ttu-id="763c7-121">Entrez un nombre dans le champ Prix unitaire.</span><span class="sxs-lookup"><span data-stu-id="763c7-121">In the Unit price field, enter a number.</span></span>
13. <span data-ttu-id="763c7-122">Développez la section Détails de ligne.</span><span class="sxs-lookup"><span data-stu-id="763c7-122">Expand the Line details section.</span></span>
14. <span data-ttu-id="763c7-123">Cliquez sur l’onglet Livraison.</span><span class="sxs-lookup"><span data-stu-id="763c7-123">Click the Delivery tab.</span></span>
    * <span data-ttu-id="763c7-124">Remarque : Sélectionnez Vérification de la date de livraison = Aucun(e).</span><span class="sxs-lookup"><span data-stu-id="763c7-124">Note: Select Delivery date control = None</span></span>  
15. <span data-ttu-id="763c7-125">Dans le champ Date d’expédition demandée, entrez une date.</span><span class="sxs-lookup"><span data-stu-id="763c7-125">In the Requested ship date field, enter a date.</span></span>
16. <span data-ttu-id="763c7-126">Dans le champ Date d’expédition confirmée, entrez une date.</span><span class="sxs-lookup"><span data-stu-id="763c7-126">In the Confirmed ship date field, enter a date.</span></span>

## <a name="process-letter-of-guarantee_request"></a><span data-ttu-id="763c7-127">Traiter une demande de lettre de garantie</span><span class="sxs-lookup"><span data-stu-id="763c7-127">Process letter of guarantee_Request</span></span>
1. <span data-ttu-id="763c7-128">Dans le volet Actions, cliquez sur Gérer.</span><span class="sxs-lookup"><span data-stu-id="763c7-128">On the Action Pane, click Manage.</span></span>
2. <span data-ttu-id="763c7-129">Cliquez sur Lettre de garantie.</span><span class="sxs-lookup"><span data-stu-id="763c7-129">Click Letter of guarantee.</span></span>
3. <span data-ttu-id="763c7-130">Dans le Volet Actions, cliquez sur Lettre de garantie.</span><span class="sxs-lookup"><span data-stu-id="763c7-130">On the Action Pane, click Letter of guarantee.</span></span>
4. <span data-ttu-id="763c7-131">Cliquer sur Demande pour ouvrir la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="763c7-131">Click Request to open the drop dialog.</span></span>
5. <span data-ttu-id="763c7-132">Dans le champ Type, saisissez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="763c7-132">In the Type field, enter or select a value.</span></span>
6. <span data-ttu-id="763c7-133">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="763c7-133">In the list, click the link in the selected row.</span></span>
7. <span data-ttu-id="763c7-134">Entrez un nombre dans le champ Valeur.</span><span class="sxs-lookup"><span data-stu-id="763c7-134">In the Value field, enter a number.</span></span>
8. <span data-ttu-id="763c7-135">Entrez une date et une heure dans le champ Date d’expiration.</span><span class="sxs-lookup"><span data-stu-id="763c7-135">In the Expiration date field, enter a date and time.</span></span>
9. <span data-ttu-id="763c7-136">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="763c7-136">Click OK.</span></span>
10. <span data-ttu-id="763c7-137">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="763c7-137">Close the page.</span></span>

## <a name="process-letter-of-guarantee_submit-to-bank"></a><span data-ttu-id="763c7-138">Traiter la lettre de garantie_Remettre à la banque</span><span class="sxs-lookup"><span data-stu-id="763c7-138">Process letter of guarantee_Submit to bank</span></span>
1. <span data-ttu-id="763c7-139">Accédez à Gestion de la trésorerie et de la banque > Lettres de garantie > Lettres de garantie.</span><span class="sxs-lookup"><span data-stu-id="763c7-139">Go to Cash and bank management > Letters of guarantee > Letters of guarantee.</span></span>
2. <span data-ttu-id="763c7-140">Dans la liste, recherchez et sélectionnez l’enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="763c7-140">In the list, find and select the desired record.</span></span>
3. <span data-ttu-id="763c7-141">Cliquez sur Remettre à la banque pour ouvrir la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="763c7-141">Click Submit to bank to open the drop dialog.</span></span>
4. <span data-ttu-id="763c7-142">Dans le champ Compte en banque, saisissez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="763c7-142">In the Bank account field, enter or select a value.</span></span>
5. <span data-ttu-id="763c7-143">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="763c7-143">In the list, click the link in the selected row.</span></span>
6. <span data-ttu-id="763c7-144">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="763c7-144">Click OK.</span></span>

## <a name="process-letter-of-guarantee_receive-from-bank"></a><span data-ttu-id="763c7-145">Traiter la lettre de garantie_Recevoir de la banque</span><span class="sxs-lookup"><span data-stu-id="763c7-145">Process letter of guarantee_Receive from bank</span></span>
1. <span data-ttu-id="763c7-146">Cliquez sur Recevoir de la banque pour ouvrir la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="763c7-146">Click Receive from bank to open the drop dialog.</span></span>
2. <span data-ttu-id="763c7-147">Dans le champ Numéro de banque, tapez une valeur.</span><span class="sxs-lookup"><span data-stu-id="763c7-147">In the Bank number field, type a value.</span></span>
    * <span data-ttu-id="763c7-148">Vérifiez les valeurs dans les champs calculés Marge et Dépense.</span><span class="sxs-lookup"><span data-stu-id="763c7-148">Verify the values in the calculated Margin and Expense fields.</span></span>  
3. <span data-ttu-id="763c7-149">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="763c7-149">Click OK.</span></span>
4. <span data-ttu-id="763c7-150">Développez la section Actions.</span><span class="sxs-lookup"><span data-stu-id="763c7-150">Expand the Actions section.</span></span>
    * <span data-ttu-id="763c7-151">Vérifiez l’enregistrement « Recevoir de la banque ».</span><span class="sxs-lookup"><span data-stu-id="763c7-151">Verify the 'Receive from bank' record.</span></span>  
5. <span data-ttu-id="763c7-152">Cliquez pour suivre le lien dans le champ Numéro de lot du journal.</span><span class="sxs-lookup"><span data-stu-id="763c7-152">Click to follow the link in the Journal batch number field.</span></span>
6. <span data-ttu-id="763c7-153">Cliquez sur Lignes.</span><span class="sxs-lookup"><span data-stu-id="763c7-153">Click Lines.</span></span>
    * <span data-ttu-id="763c7-154">Vérifiez la validation des écritures de journal.</span><span class="sxs-lookup"><span data-stu-id="763c7-154">Verify the posting of journal entries.</span></span>  
7. <span data-ttu-id="763c7-155">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="763c7-155">Close the page.</span></span>

## <a name="process-letter-of-guarantee_give-to-beneficiary"></a><span data-ttu-id="763c7-156">Traiter la lettre de garantie_Remettre au bénéficiaire</span><span class="sxs-lookup"><span data-stu-id="763c7-156">Process letter of guarantee_Give to beneficiary</span></span>
1. <span data-ttu-id="763c7-157">Accédez à Comptabilité client > Commandes > Toutes les commandes client.</span><span class="sxs-lookup"><span data-stu-id="763c7-157">Go to Accounts receivable > Orders > All sales orders.</span></span>
2. <span data-ttu-id="763c7-158">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="763c7-158">In the list, click the link in the selected row.</span></span>
3. <span data-ttu-id="763c7-159">Dans le volet Actions, cliquez sur Gérer.</span><span class="sxs-lookup"><span data-stu-id="763c7-159">On the Action Pane, click Manage.</span></span>
4. <span data-ttu-id="763c7-160">Cliquez sur Lettre de garantie.</span><span class="sxs-lookup"><span data-stu-id="763c7-160">Click Letter of guarantee.</span></span>
5. <span data-ttu-id="763c7-161">Dans le Volet Actions, cliquez sur Lettre de garantie.</span><span class="sxs-lookup"><span data-stu-id="763c7-161">On the Action Pane, click Letter of guarantee.</span></span>
6. <span data-ttu-id="763c7-162">Cliquez sur Remettre au bénéficiaire pour ouvrir la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="763c7-162">Click Give to beneficiary to open the drop dialog.</span></span>
7. <span data-ttu-id="763c7-163">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="763c7-163">Click OK.</span></span>
8. <span data-ttu-id="763c7-164">Accédez à Gestion de la trésorerie et de la banque > Lettres de garantie > Lettres de garantie.</span><span class="sxs-lookup"><span data-stu-id="763c7-164">Go to Cash and bank management > Letters of guarantee > Letters of guarantee.</span></span>
9. <span data-ttu-id="763c7-165">Dans la liste, recherchez et sélectionnez l’enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="763c7-165">In the list, find and select the desired record.</span></span>
10. <span data-ttu-id="763c7-166">Cliquez sur Remettre au bénéficiaire pour ouvrir la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="763c7-166">Click Give to beneficiary to open the drop dialog.</span></span>
11. <span data-ttu-id="763c7-167">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="763c7-167">Click OK.</span></span>
12. <span data-ttu-id="763c7-168">Développez la section Actions.</span><span class="sxs-lookup"><span data-stu-id="763c7-168">Expand the Actions section.</span></span>
    * <span data-ttu-id="763c7-169">Validez l’enregistrement « Remettre au bénéficiaire ».</span><span class="sxs-lookup"><span data-stu-id="763c7-169">Validate the 'Give to beneficiary' record.</span></span>  

## <a name="process-letter-of-guarantee_increase-value"></a><span data-ttu-id="763c7-170">Traiter la lettre de garantie_Augmenter la valeur</span><span class="sxs-lookup"><span data-stu-id="763c7-170">Process letter of guarantee_Increase value</span></span>
1. <span data-ttu-id="763c7-171">Accédez à Comptabilité client > Commandes > Toutes les commandes client.</span><span class="sxs-lookup"><span data-stu-id="763c7-171">Go to Accounts receivable > Orders > All sales orders.</span></span>
2. <span data-ttu-id="763c7-172">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="763c7-172">In the list, click the link in the selected row.</span></span>
3. <span data-ttu-id="763c7-173">Dans le volet Actions, cliquez sur Gérer.</span><span class="sxs-lookup"><span data-stu-id="763c7-173">On the Action Pane, click Manage.</span></span>
4. <span data-ttu-id="763c7-174">Cliquez sur Lettre de garantie.</span><span class="sxs-lookup"><span data-stu-id="763c7-174">Click Letter of guarantee.</span></span>
5. <span data-ttu-id="763c7-175">Dans le Volet Actions, cliquez sur Lettre de garantie.</span><span class="sxs-lookup"><span data-stu-id="763c7-175">On the Action Pane, click Letter of guarantee.</span></span>
6. <span data-ttu-id="763c7-176">Cliquer sur Augmenter la valeur pour ouvrir la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="763c7-176">Click Increase value to open the drop dialog.</span></span>
7. <span data-ttu-id="763c7-177">Dans le champ Valeur à ajouter, entrez un numéro.</span><span class="sxs-lookup"><span data-stu-id="763c7-177">In the Value to add field, enter a number.</span></span>
8. <span data-ttu-id="763c7-178">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="763c7-178">Click OK.</span></span>
9. <span data-ttu-id="763c7-179">Accédez à Gestion de la trésorerie et de la banque > Lettres de garantie > Lettres de garantie.</span><span class="sxs-lookup"><span data-stu-id="763c7-179">Go to Cash and bank management > Letters of guarantee > Letters of guarantee.</span></span>
10. <span data-ttu-id="763c7-180">Dans la liste, recherchez et sélectionnez l’enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="763c7-180">In the list, find and select the desired record.</span></span>
11. <span data-ttu-id="763c7-181">Cliquer sur Augmenter la valeur pour ouvrir la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="763c7-181">Click Increase value to open the drop dialog.</span></span>
12. <span data-ttu-id="763c7-182">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="763c7-182">Click OK.</span></span>
13. <span data-ttu-id="763c7-183">Développez la section Actions.</span><span class="sxs-lookup"><span data-stu-id="763c7-183">Expand the Actions section.</span></span>
    * <span data-ttu-id="763c7-184">Vérifiez l’enregistrement « Augmenter la valeur ».</span><span class="sxs-lookup"><span data-stu-id="763c7-184">Verify the 'Increase value' record.</span></span>  
14. <span data-ttu-id="763c7-185">Dans la liste, recherchez et sélectionnez l’enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="763c7-185">In the list, find and select the desired record.</span></span>
15. <span data-ttu-id="763c7-186">Cliquez pour suivre le lien dans le champ Numéro de lot du journal.</span><span class="sxs-lookup"><span data-stu-id="763c7-186">Click to follow the link in the Journal batch number field.</span></span>
16. <span data-ttu-id="763c7-187">Cliquez sur Lignes.</span><span class="sxs-lookup"><span data-stu-id="763c7-187">Click Lines.</span></span>
    * <span data-ttu-id="763c7-188">Vérifiez les écritures de journal validées.</span><span class="sxs-lookup"><span data-stu-id="763c7-188">Verify the posted journal entries.</span></span>  

## <a name="process-letter-of-guarantee_liquidate"></a><span data-ttu-id="763c7-189">Traiter la lettre de garantie_Liquider</span><span class="sxs-lookup"><span data-stu-id="763c7-189">Process letter of guarantee_Liquidate</span></span>
1. <span data-ttu-id="763c7-190">Accédez à Comptabilité client > Commandes > Toutes les commandes client.</span><span class="sxs-lookup"><span data-stu-id="763c7-190">Go to Accounts receivable > Orders > All sales orders.</span></span>
2. <span data-ttu-id="763c7-191">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="763c7-191">In the list, click the link in the selected row.</span></span>
3. <span data-ttu-id="763c7-192">Dans le volet Actions, cliquez sur Gérer.</span><span class="sxs-lookup"><span data-stu-id="763c7-192">On the Action Pane, click Manage.</span></span>
4. <span data-ttu-id="763c7-193">Cliquez sur Lettre de garantie.</span><span class="sxs-lookup"><span data-stu-id="763c7-193">Click Letter of guarantee.</span></span>
5. <span data-ttu-id="763c7-194">Dans le Volet Actions, cliquez sur Lettre de garantie.</span><span class="sxs-lookup"><span data-stu-id="763c7-194">On the Action Pane, click Letter of guarantee.</span></span>
6. <span data-ttu-id="763c7-195">Cliquer sur Liquider pour ouvrir la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="763c7-195">Click Liquidate to open the drop dialog.</span></span>
7. <span data-ttu-id="763c7-196">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="763c7-196">Click OK.</span></span>
8. <span data-ttu-id="763c7-197">Accédez à Gestion de la trésorerie et de la banque > Lettres de garantie > Lettres de garantie.</span><span class="sxs-lookup"><span data-stu-id="763c7-197">Go to Cash and bank management > Letters of guarantee > Letters of guarantee.</span></span>
9. <span data-ttu-id="763c7-198">Dans la liste, recherchez et sélectionnez l’enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="763c7-198">In the list, find and select the desired record.</span></span>
10. <span data-ttu-id="763c7-199">Cliquer sur Liquider pour ouvrir la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="763c7-199">Click Liquidate to open the drop dialog.</span></span>
11. <span data-ttu-id="763c7-200">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="763c7-200">Click OK.</span></span>
12. <span data-ttu-id="763c7-201">Développez la section Actions.</span><span class="sxs-lookup"><span data-stu-id="763c7-201">Expand the Actions section.</span></span>
    * <span data-ttu-id="763c7-202">Vérifiez l’enregistrement « Liquider ».</span><span class="sxs-lookup"><span data-stu-id="763c7-202">Verify the 'Liquidate' record.</span></span>  
13. <span data-ttu-id="763c7-203">Dans la liste, recherchez et sélectionnez l’enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="763c7-203">In the list, find and select the desired record.</span></span>
14. <span data-ttu-id="763c7-204">Cliquez pour suivre le lien dans le champ Numéro de lot du journal.</span><span class="sxs-lookup"><span data-stu-id="763c7-204">Click to follow the link in the Journal batch number field.</span></span>
15. <span data-ttu-id="763c7-205">Cliquez sur Lignes.</span><span class="sxs-lookup"><span data-stu-id="763c7-205">Click Lines.</span></span>
    * <span data-ttu-id="763c7-206">Vérifiez les écritures de journal validées.</span><span class="sxs-lookup"><span data-stu-id="763c7-206">Verify the posted journal entries.</span></span>  
16. <span data-ttu-id="763c7-207">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="763c7-207">Close the page.</span></span>

