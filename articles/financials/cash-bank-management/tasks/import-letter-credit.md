---
title: Importer une lettre de crédit
description: Cette procédure décrit le processus d'importation d'une lettre de crédit.
author: kweekley
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: VendTable, VendBankAccounts, PurchTable, PurchCreateOrder, InventItemIdLookupPurchase, BankLCImport,  PurchEditLines, VendEditInvoice, SrsReportViewerForm, LedgerJournalTable, LedgerJournalTransVendPaym, VendOpenTrans, SysQueryForm, BankAccountTableLookUp
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: c1768494182a79d7a33044498c1e768e61d937d1
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/29/2019
ms.locfileid: "313564"
---
# <a name="import-letter-of-credit"></a><span data-ttu-id="24f7b-103">Importer une lettre de crédit</span><span class="sxs-lookup"><span data-stu-id="24f7b-103">Import letter of credit</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="24f7b-104">Cette procédure décrit le processus d'importation d'une lettre de crédit.</span><span class="sxs-lookup"><span data-stu-id="24f7b-104">This procedure walks through the process of importing a letter of credit.</span></span> <span data-ttu-id="24f7b-105">Vous devez configurer les éléments suivants avant de terminer cette procédure : les établissements bancaires, les profils de validation, un accord d'établissement bancaire et les coordonnées bancaires du fournisseur.</span><span class="sxs-lookup"><span data-stu-id="24f7b-105">The following must be set up before completing this procedure: bank facilities, posting profiles, a bank facility agreement and vendor bank details.</span></span>

<span data-ttu-id="24f7b-106">La société fictive USMF sert d'exemple dans cette procédure.</span><span class="sxs-lookup"><span data-stu-id="24f7b-106">This procedure uses the USMF demo company.</span></span>


## <a name="create-a-purchase-order-with-letter-of-credit"></a><span data-ttu-id="24f7b-107">Créer une commande fournisseur avec une lettre de crédit</span><span class="sxs-lookup"><span data-stu-id="24f7b-107">Create a Purchase order with Letter of credit</span></span>
1. <span data-ttu-id="24f7b-108">Accédez à Comptabilité fournisseur > Commandes fournisseur > Toutes les commandes fournisseur.</span><span class="sxs-lookup"><span data-stu-id="24f7b-108">Go to Accounts payable > Purchase orders > All purchase orders.</span></span>
2. <span data-ttu-id="24f7b-109">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="24f7b-109">Click New.</span></span>
3. <span data-ttu-id="24f7b-110">Dans le champ Compte fournisseur, saisissez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="24f7b-110">In the Vendor account field, enter or select a value.</span></span>
4. <span data-ttu-id="24f7b-111">Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="24f7b-111">In the list, find and select the desired record.</span></span>
5. <span data-ttu-id="24f7b-112">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="24f7b-112">In the list, click the link in the selected row.</span></span>
6. <span data-ttu-id="24f7b-113">Développez la section Général.</span><span class="sxs-lookup"><span data-stu-id="24f7b-113">Expand the General section.</span></span>
7. <span data-ttu-id="24f7b-114">Saisissez ou sélectionnez une valeur dans le champ Site.</span><span class="sxs-lookup"><span data-stu-id="24f7b-114">In the Site field, enter or select a value.</span></span>
8. <span data-ttu-id="24f7b-115">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="24f7b-115">In the list, click the link in the selected row.</span></span>
9. <span data-ttu-id="24f7b-116">Dans le champ Entrepôt, saisissez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="24f7b-116">In the Warehouse field, enter or select a value.</span></span>
10. <span data-ttu-id="24f7b-117">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="24f7b-117">In the list, click the link in the selected row.</span></span>
11. <span data-ttu-id="24f7b-118">Dans le champ Comptabilité, entrez une date.</span><span class="sxs-lookup"><span data-stu-id="24f7b-118">In the Accounting date field, enter a date.</span></span>
12. <span data-ttu-id="24f7b-119">Dans le champ Date de livraison, entrez une date.</span><span class="sxs-lookup"><span data-stu-id="24f7b-119">In the Delivery date field, enter a date.</span></span>
    * <span data-ttu-id="24f7b-120">Remarque : le champ « Type de document bancaire » doit être sélectionné et renseigné avec la valeur « Lettre de crédit ».</span><span class="sxs-lookup"><span data-stu-id="24f7b-120">Note: The 'Bank document type' field should be selected with the value  'Letter of credit'.</span></span>  
13. <span data-ttu-id="24f7b-121">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="24f7b-121">Click OK.</span></span>
14. <span data-ttu-id="24f7b-122">Entrez ou sélectionnez une valeur dans le champ Numéro d'article.</span><span class="sxs-lookup"><span data-stu-id="24f7b-122">In the Item number field, enter or select a value.</span></span>
15. <span data-ttu-id="24f7b-123">Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="24f7b-123">In the list, find and select the desired record.</span></span>
16. <span data-ttu-id="24f7b-124">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="24f7b-124">In the list, click the link in the selected row.</span></span>
17. <span data-ttu-id="24f7b-125">Développez la section Détails de ligne.</span><span class="sxs-lookup"><span data-stu-id="24f7b-125">Expand the Line details section.</span></span>
18. <span data-ttu-id="24f7b-126">Cliquez sur l'onglet Livraison.</span><span class="sxs-lookup"><span data-stu-id="24f7b-126">Click the Delivery tab.</span></span>
19. <span data-ttu-id="24f7b-127">Dans le champ Date de livraison, entrez une date.</span><span class="sxs-lookup"><span data-stu-id="24f7b-127">In the Delivery date field, enter a date.</span></span>
20. <span data-ttu-id="24f7b-128">Dans le champ Date de livraison confirmée, entrez une date.</span><span class="sxs-lookup"><span data-stu-id="24f7b-128">In the Confirmed delivery date field, enter a date.</span></span>
21. <span data-ttu-id="24f7b-129">Entrez un nombre dans le champ Prix unitaire.</span><span class="sxs-lookup"><span data-stu-id="24f7b-129">In the Unit price field, enter a number.</span></span>
    * <span data-ttu-id="24f7b-130">Définissez les détails de la lettre de crédit.</span><span class="sxs-lookup"><span data-stu-id="24f7b-130">Define the Letter of credit details.</span></span>  
22. <span data-ttu-id="24f7b-131">Dans le volet Actions, cliquez sur Gérer.</span><span class="sxs-lookup"><span data-stu-id="24f7b-131">On the Action Pane, click Manage.</span></span>
23. <span data-ttu-id="24f7b-132">Cliquez sur Lettre de crédit/relance d'importation.</span><span class="sxs-lookup"><span data-stu-id="24f7b-132">Click Letter of credit / import collection.</span></span>
24. <span data-ttu-id="24f7b-133">Dans le champ Date de demande, entrez une date et une heure.</span><span class="sxs-lookup"><span data-stu-id="24f7b-133">In the Application date field, enter a date and time.</span></span>
    * <span data-ttu-id="24f7b-134">Vérifiez que le champ « Compte bancaire » contient le compte bancaire actif par défaut, qui est basé sur la date de demande.</span><span class="sxs-lookup"><span data-stu-id="24f7b-134">Verify that the 'Bank account' field has the default active Bank account, which is based on the application date.</span></span>  
25. <span data-ttu-id="24f7b-135">Dans le champ Numéro de document bancaire, tapez une valeur.</span><span class="sxs-lookup"><span data-stu-id="24f7b-135">In the Bank document number field, type a value.</span></span>
26. <span data-ttu-id="24f7b-136">Dans le champ Date de réception, entrez une date et une heure.</span><span class="sxs-lookup"><span data-stu-id="24f7b-136">In the Date of receipt field, enter a date and time.</span></span>
27. <span data-ttu-id="24f7b-137">Développez la section Document bancaire.</span><span class="sxs-lookup"><span data-stu-id="24f7b-137">Expand the Bank document section.</span></span>
28. <span data-ttu-id="24f7b-138">Entrez une date et une heure dans le champ Date d'expiration.</span><span class="sxs-lookup"><span data-stu-id="24f7b-138">In the Expiration date field, enter a date and time.</span></span>
29. <span data-ttu-id="24f7b-139">Développez la section Détails bancaires.</span><span class="sxs-lookup"><span data-stu-id="24f7b-139">Expand the Bank details section.</span></span>
30. <span data-ttu-id="24f7b-140">Dans le champ Banque conseillère, saisissez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="24f7b-140">In the Advising bank field, enter or select a value.</span></span>
31. <span data-ttu-id="24f7b-141">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="24f7b-141">In the list, click the link in the selected row.</span></span>
32. <span data-ttu-id="24f7b-142">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="24f7b-142">Click Save.</span></span>
33. <span data-ttu-id="24f7b-143">Cliquez sur Extraire les expéditions de commandes fournisseur.</span><span class="sxs-lookup"><span data-stu-id="24f7b-143">Click Fetch purchase order shipments.</span></span>
34. <span data-ttu-id="24f7b-144">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="24f7b-144">Close the page.</span></span>
35. <span data-ttu-id="24f7b-145">Cliquez sur Achats dans le volet Actions.</span><span class="sxs-lookup"><span data-stu-id="24f7b-145">On the Action Pane, click Purchase.</span></span>
36. <span data-ttu-id="24f7b-146">Cliquez sur Confirmer.</span><span class="sxs-lookup"><span data-stu-id="24f7b-146">Click Confirm.</span></span>
37. <span data-ttu-id="24f7b-147">Dans le volet Actions, cliquez sur Gérer.</span><span class="sxs-lookup"><span data-stu-id="24f7b-147">On the Action Pane, click Manage.</span></span>
38. <span data-ttu-id="24f7b-148">Cliquez sur Lettre de crédit/relance d'importation.</span><span class="sxs-lookup"><span data-stu-id="24f7b-148">Click Letter of credit / import collection.</span></span>
39. <span data-ttu-id="24f7b-149">Cliquez sur Traiter.</span><span class="sxs-lookup"><span data-stu-id="24f7b-149">Click Process.</span></span>
40. <span data-ttu-id="24f7b-150">Cliquez sur Confirmer.</span><span class="sxs-lookup"><span data-stu-id="24f7b-150">Click Confirm.</span></span>
    * <span data-ttu-id="24f7b-151">Vérifiez que le solde de l'établissement réduit le montant de la commande fournisseur.</span><span class="sxs-lookup"><span data-stu-id="24f7b-151">Verify that the Facility balance reduces the purchase order amount.</span></span>  <span data-ttu-id="24f7b-152">Dans cet exemple, Montant des achats = 500,00, Limite des services = 10000,00, par conséquent, Solde de l'établissement = 9500,00.</span><span class="sxs-lookup"><span data-stu-id="24f7b-152">In this example, Purchase amount = 500.00,  Facility limit = 10000.00,  therefore, Facility balance = 9500.00.</span></span>  
41. <span data-ttu-id="24f7b-153">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="24f7b-153">Close the page.</span></span>
42. <span data-ttu-id="24f7b-154">Entrez un nombre dans le champ Prix unitaire.</span><span class="sxs-lookup"><span data-stu-id="24f7b-154">In the Unit price field, enter a number.</span></span>
43. <span data-ttu-id="24f7b-155">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="24f7b-155">Click Save.</span></span>
44. <span data-ttu-id="24f7b-156">Cliquez sur Achats dans le volet Actions.</span><span class="sxs-lookup"><span data-stu-id="24f7b-156">On the Action Pane, click Purchase.</span></span>
45. <span data-ttu-id="24f7b-157">Cliquez sur Confirmer.</span><span class="sxs-lookup"><span data-stu-id="24f7b-157">Click Confirm.</span></span>
    * <span data-ttu-id="24f7b-158">Modifiez la lettre de crédit, en fonction de la modification du prix unitaire.</span><span class="sxs-lookup"><span data-stu-id="24f7b-158">Amend the Letter of credit, due to the change in Unit price.</span></span>  
46. <span data-ttu-id="24f7b-159">Dans le volet Actions, cliquez sur Gérer.</span><span class="sxs-lookup"><span data-stu-id="24f7b-159">On the Action Pane, click Manage.</span></span>
47. <span data-ttu-id="24f7b-160">Cliquez sur Lettre de crédit/relance d'importation.</span><span class="sxs-lookup"><span data-stu-id="24f7b-160">Click Letter of credit / import collection.</span></span>
    * <span data-ttu-id="24f7b-161">Modifiez la lettre de crédit, en fonction de la modification du prix unitaire d'achat.</span><span class="sxs-lookup"><span data-stu-id="24f7b-161">Amend the letter of credit, due to the change in Purchase unit price.</span></span>  
48. <span data-ttu-id="24f7b-162">Cliquez sur Traiter.</span><span class="sxs-lookup"><span data-stu-id="24f7b-162">Click Process.</span></span>
49. <span data-ttu-id="24f7b-163">Cliquez sur Amender.</span><span class="sxs-lookup"><span data-stu-id="24f7b-163">Click Amend.</span></span>
50. <span data-ttu-id="24f7b-164">Cliquez sur Supprimer.</span><span class="sxs-lookup"><span data-stu-id="24f7b-164">Click Remove.</span></span>
51. <span data-ttu-id="24f7b-165">Cliquez sur Oui.</span><span class="sxs-lookup"><span data-stu-id="24f7b-165">Click Yes.</span></span>
52. <span data-ttu-id="24f7b-166">Cliquez sur Extraire les expéditions de commandes fournisseur.</span><span class="sxs-lookup"><span data-stu-id="24f7b-166">Click Fetch purchase order shipments.</span></span>
53. <span data-ttu-id="24f7b-167">Cliquez sur Traiter.</span><span class="sxs-lookup"><span data-stu-id="24f7b-167">Click Process.</span></span>
54. <span data-ttu-id="24f7b-168">Cliquez sur Confirmer.</span><span class="sxs-lookup"><span data-stu-id="24f7b-168">Click Confirm.</span></span>
    * <span data-ttu-id="24f7b-169">Vérifiez que le solde de l'établissement réduit le montant de la commande fournisseur.</span><span class="sxs-lookup"><span data-stu-id="24f7b-169">Verify that the Facility balance reduces the purchase order amount.</span></span>  <span data-ttu-id="24f7b-170">Dans cet exemple, Montant modifié des achats = 600,00, Limite des services = 10 000,00, par conséquent, Solde de l'établissement = 9 400,00.</span><span class="sxs-lookup"><span data-stu-id="24f7b-170">In this example, edited Purchase amount = 600.00,  Facility limit = 10000.00,  therefore, Facility balance = 9400.00.</span></span>  
55. <span data-ttu-id="24f7b-171">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="24f7b-171">Close the page.</span></span>

## <a name="post-packing-slip"></a><span data-ttu-id="24f7b-172">Valider un bon de livraison</span><span class="sxs-lookup"><span data-stu-id="24f7b-172">Post Packing slip</span></span>
1. <span data-ttu-id="24f7b-173">Dans le volet Actions, cliquez sur Recevoir.</span><span class="sxs-lookup"><span data-stu-id="24f7b-173">On the Action Pane, click Receive.</span></span>
2. <span data-ttu-id="24f7b-174">Cliquez sur Accusé de réception de marchandises.</span><span class="sxs-lookup"><span data-stu-id="24f7b-174">Click Product receipt.</span></span>
3. <span data-ttu-id="24f7b-175">Dans le champ PurchParmTable_Num, tapez une valeur.</span><span class="sxs-lookup"><span data-stu-id="24f7b-175">In the PurchParmTable_Num field, type a value.</span></span>
    * <span data-ttu-id="24f7b-176">Sélectionnez le numéro d'expédition créé en référence à la lettre de crédit.</span><span class="sxs-lookup"><span data-stu-id="24f7b-176">Select the Shipment number created with reference to the Letter of credit.</span></span>  
4. <span data-ttu-id="24f7b-177">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="24f7b-177">In the list, click the link in the selected row.</span></span>
5. <span data-ttu-id="24f7b-178">Dans le champ Date de l'accusé de réception de marchandises, entrez une date.</span><span class="sxs-lookup"><span data-stu-id="24f7b-178">In the Product receipt date field, enter a date.</span></span>
6. <span data-ttu-id="24f7b-179">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="24f7b-179">Click OK.</span></span>
7. <span data-ttu-id="24f7b-180">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="24f7b-180">Close the page.</span></span>
8. <span data-ttu-id="24f7b-181">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="24f7b-181">Close the page.</span></span>

## <a name="verify-import-letter-of-credit-status"></a><span data-ttu-id="24f7b-182">Vérifier le statut d'une lettre de crédit d'importation</span><span class="sxs-lookup"><span data-stu-id="24f7b-182">Verify Import letter of credit status</span></span>
1. <span data-ttu-id="24f7b-183">Accédez à Gestion de la trésorerie et de la banque > Lettres de crédit > Lettre de crédit d'importation/relance d'importation.</span><span class="sxs-lookup"><span data-stu-id="24f7b-183">Go to Cash and bank management > Letters of credit > Import letter of credit and import collection.</span></span>
2. <span data-ttu-id="24f7b-184">Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="24f7b-184">In the list, find and select the desired record.</span></span>
3. <span data-ttu-id="24f7b-185">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="24f7b-185">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="24f7b-186">Vérifiez le statut de la lettre de crédit d'importation.</span><span class="sxs-lookup"><span data-stu-id="24f7b-186">Verify the Import letter of credit status.</span></span>    
    *   
4. <span data-ttu-id="24f7b-187">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="24f7b-187">Close the page.</span></span>
5. <span data-ttu-id="24f7b-188">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="24f7b-188">Close the page.</span></span>

## <a name="post-purchase-invoice"></a><span data-ttu-id="24f7b-189">Valider une facture d'achat</span><span class="sxs-lookup"><span data-stu-id="24f7b-189">Post purchase invoice</span></span>
1. <span data-ttu-id="24f7b-190">Accédez à Comptabilité fournisseur > Commandes fournisseur > Toutes les commandes fournisseur.</span><span class="sxs-lookup"><span data-stu-id="24f7b-190">Go to Accounts payable > Purchase orders > All purchase orders.</span></span>
    * <span data-ttu-id="24f7b-191">Sélectionnez la commande fournisseur créée avec la lettre de crédit.</span><span class="sxs-lookup"><span data-stu-id="24f7b-191">Select the purchase order that was created with letter of credit.</span></span>  
2. <span data-ttu-id="24f7b-192">Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="24f7b-192">In the list, find and select the desired record.</span></span>
3. <span data-ttu-id="24f7b-193">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="24f7b-193">In the list, click the link in the selected row.</span></span>
4. <span data-ttu-id="24f7b-194">Dans le volet Actions, cliquez sur Facture.</span><span class="sxs-lookup"><span data-stu-id="24f7b-194">On the Action Pane, click Invoice.</span></span>
5. <span data-ttu-id="24f7b-195">Cliquez sur Facture.</span><span class="sxs-lookup"><span data-stu-id="24f7b-195">Click Invoice.</span></span>
6. <span data-ttu-id="24f7b-196">Tapez une valeur dans le champ Nombre.</span><span class="sxs-lookup"><span data-stu-id="24f7b-196">In the Number field, type a value.</span></span>
7. <span data-ttu-id="24f7b-197">Dans le champ Numéro d'expédition, entrez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="24f7b-197">In the Shipment number field, enter or select a value.</span></span>
8. <span data-ttu-id="24f7b-198">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="24f7b-198">In the list, click the link in the selected row.</span></span>
9. <span data-ttu-id="24f7b-199">Entrez une date dans le champ Date de facture.</span><span class="sxs-lookup"><span data-stu-id="24f7b-199">In the Invoice date field, enter a date.</span></span>
10. <span data-ttu-id="24f7b-200">Cliquez sur Mettre à jour le statut de rapprochement.</span><span class="sxs-lookup"><span data-stu-id="24f7b-200">Click Update match status.</span></span>
11. <span data-ttu-id="24f7b-201">Cliquez sur Valider.</span><span class="sxs-lookup"><span data-stu-id="24f7b-201">Click Post.</span></span>
12. <span data-ttu-id="24f7b-202">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="24f7b-202">Close the page.</span></span>
13. <span data-ttu-id="24f7b-203">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="24f7b-203">Close the page.</span></span>

## <a name="verify-import-letter-of-credit-status"></a><span data-ttu-id="24f7b-204">Vérifier le statut d'une lettre de crédit d'importation</span><span class="sxs-lookup"><span data-stu-id="24f7b-204">Verify Import letter of credit status</span></span>
1. <span data-ttu-id="24f7b-205">Accédez à Gestion de la trésorerie et de la banque > Lettres de crédit > Lettre de crédit d'importation/relance d'importation.</span><span class="sxs-lookup"><span data-stu-id="24f7b-205">Go to Cash and bank management > Letters of credit > Import letter of credit and import collection.</span></span>
2. <span data-ttu-id="24f7b-206">Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="24f7b-206">In the list, find and select the desired record.</span></span>
3. <span data-ttu-id="24f7b-207">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="24f7b-207">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="24f7b-208">Vérifiez la lettre de crédit d'importation 2.</span><span class="sxs-lookup"><span data-stu-id="24f7b-208">Verify the Import letter of credit2.</span></span>  
    * <span data-ttu-id="24f7b-209">Validez : Statut de l'expédition = détails de l'établissement bancaire facturé</span><span class="sxs-lookup"><span data-stu-id="24f7b-209">Validate :  Shipment status = Invoiced  Bank facility details</span></span>  
4. <span data-ttu-id="24f7b-210">Cliquez sur Afficher.</span><span class="sxs-lookup"><span data-stu-id="24f7b-210">Click View.</span></span>
5. <span data-ttu-id="24f7b-211">Cliquez sur Imprimer la demande.</span><span class="sxs-lookup"><span data-stu-id="24f7b-211">Click Print application.</span></span>
6. <span data-ttu-id="24f7b-212">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="24f7b-212">Click OK.</span></span>
    * <span data-ttu-id="24f7b-213">Vérifiez que la demande de lettre de crédit est imprimée.</span><span class="sxs-lookup"><span data-stu-id="24f7b-213">Verify that the Letter of credit application gets printed.</span></span>  
7. <span data-ttu-id="24f7b-214">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="24f7b-214">Close the page.</span></span>
8. <span data-ttu-id="24f7b-215">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="24f7b-215">Close the page.</span></span>
9. <span data-ttu-id="24f7b-216">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="24f7b-216">Close the page.</span></span>

## <a name="post-vendor-payment-journal-for-the-created-purchase-invoice-with-letter-of-credit"></a><span data-ttu-id="24f7b-217">Valider le journal des paiements fournisseur pour la facture d'achat créée avec une lettre de crédit</span><span class="sxs-lookup"><span data-stu-id="24f7b-217">Post Vendor payment journal for the created purchase invoice with letter of credit</span></span>
1. <span data-ttu-id="24f7b-218">Accédez à Comptabilité fournisseur > Paiements > Journal des paiements.</span><span class="sxs-lookup"><span data-stu-id="24f7b-218">Go to Accounts payable > Payments > Payment journal.</span></span>
2. <span data-ttu-id="24f7b-219">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="24f7b-219">Click New.</span></span>
3. <span data-ttu-id="24f7b-220">Saisissez ou sélectionnez une valeur dans le champ Nom.</span><span class="sxs-lookup"><span data-stu-id="24f7b-220">In the Name field, enter or select a value.</span></span>
4. <span data-ttu-id="24f7b-221">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="24f7b-221">In the list, click the link in the selected row.</span></span>
5. <span data-ttu-id="24f7b-222">Cliquez sur Lignes.</span><span class="sxs-lookup"><span data-stu-id="24f7b-222">Click Lines.</span></span>
6. <span data-ttu-id="24f7b-223">Entrez une date dans le champ Date.</span><span class="sxs-lookup"><span data-stu-id="24f7b-223">In the Date field, enter a date.</span></span>
7. <span data-ttu-id="24f7b-224">Dans le champ Compte, spécifiez les valeurs souhaitées.</span><span class="sxs-lookup"><span data-stu-id="24f7b-224">In the Account field, specify the desired values.</span></span>
8. <span data-ttu-id="24f7b-225">Cliquez sur Régler les transactions.</span><span class="sxs-lookup"><span data-stu-id="24f7b-225">Click Settle transactions.</span></span>
9. <span data-ttu-id="24f7b-226">Développez la section Totaux.</span><span class="sxs-lookup"><span data-stu-id="24f7b-226">Expand the Totals section.</span></span>
10. <span data-ttu-id="24f7b-227">Dans le champ Afficher, sélectionnez une option.</span><span class="sxs-lookup"><span data-stu-id="24f7b-227">In the Show field, select an option.</span></span>
    * <span data-ttu-id="24f7b-228">Vérifiez que les champs Numéro de document bancaire et Numéro d'expédition ont été mis à jour.</span><span class="sxs-lookup"><span data-stu-id="24f7b-228">Verify that the Bank document number and Shipment number fields have been updated.</span></span>  
11. <span data-ttu-id="24f7b-229">Cochez la case Marquer.</span><span class="sxs-lookup"><span data-stu-id="24f7b-229">Select the Mark check box.</span></span>
12. <span data-ttu-id="24f7b-230">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="24f7b-230">Click OK.</span></span>
13. <span data-ttu-id="24f7b-231">Cliquez sur l'onglet Paiement.</span><span class="sxs-lookup"><span data-stu-id="24f7b-231">Click the Payment tab.</span></span>
    * <span data-ttu-id="24f7b-232">Vérifiez que les champs Numéro de document bancaire et Numéro d'expédition ont été mis à jour.</span><span class="sxs-lookup"><span data-stu-id="24f7b-232">Verify that the Bank document number and Shipment number fields have been updated.</span></span>  
14. <span data-ttu-id="24f7b-233">Cliquez sur Valider.</span><span class="sxs-lookup"><span data-stu-id="24f7b-233">Click Post.</span></span>
15. <span data-ttu-id="24f7b-234">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="24f7b-234">Close the page.</span></span>
16. <span data-ttu-id="24f7b-235">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="24f7b-235">Close the page.</span></span>

## <a name="verify-import-letter-of-credit-status-after-invoice-paid"></a><span data-ttu-id="24f7b-236">Vérifier le statut de la lettre de crédit d'importation une fois la facture payée</span><span class="sxs-lookup"><span data-stu-id="24f7b-236">Verify Import letter of credit status after Invoice paid</span></span>
1. <span data-ttu-id="24f7b-237">Accédez à Gestion de la trésorerie et de la banque > Lettres de crédit > Lettre de crédit d'importation/relance d'importation.</span><span class="sxs-lookup"><span data-stu-id="24f7b-237">Go to Cash and bank management > Letters of credit > Import letter of credit and import collection.</span></span>
2. <span data-ttu-id="24f7b-238">Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="24f7b-238">In the list, find and select the desired record.</span></span>
3. <span data-ttu-id="24f7b-239">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="24f7b-239">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="24f7b-240">Vérifiez le statut de la lettre de crédit d'importation.</span><span class="sxs-lookup"><span data-stu-id="24f7b-240">Verify the Import letter of credit status.</span></span>   
4. <span data-ttu-id="24f7b-241">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="24f7b-241">Close the page.</span></span>

## <a name="verify-the-bank-facility-limit-and-utilization-report"></a><span data-ttu-id="24f7b-242">Vérifier l'état de la limite des services de l'établissement bancaire et l'utilisation</span><span class="sxs-lookup"><span data-stu-id="24f7b-242">Verify the Bank facility limit and utilization report</span></span>
1. <span data-ttu-id="24f7b-243">Accédez à Gestion de la trésorerie et de la banque > Recherches et états > Lettres de crédit ou garantie > État des moyens bancaires et utilisation.</span><span class="sxs-lookup"><span data-stu-id="24f7b-243">Go to Cash and bank management > Inquiries and reports > Letters of credit or guarantee > Bank facilities and utilization report.</span></span>
2. <span data-ttu-id="24f7b-244">Développez les enregistrements pour inclure la section.</span><span class="sxs-lookup"><span data-stu-id="24f7b-244">Expand the Records to include section.</span></span>
3. <span data-ttu-id="24f7b-245">Cliquez sur Filtre.</span><span class="sxs-lookup"><span data-stu-id="24f7b-245">Click Filter.</span></span>
    * <span data-ttu-id="24f7b-246">Définissez le champ Critères avec le compte bancaire requis.</span><span class="sxs-lookup"><span data-stu-id="24f7b-246">Define the Criteria field with the required bank account.</span></span>  
4. <span data-ttu-id="24f7b-247">Dans le champ Critères, saisissez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="24f7b-247">In the Criteria field, enter or select a value.</span></span>
5. <span data-ttu-id="24f7b-248">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="24f7b-248">In the list, click the link in the selected row.</span></span>
6. <span data-ttu-id="24f7b-249">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="24f7b-249">Click OK.</span></span>
7. <span data-ttu-id="24f7b-250">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="24f7b-250">Click OK.</span></span>
    * <span data-ttu-id="24f7b-251">Vérifiez l'état qui répertorie les transactions.</span><span class="sxs-lookup"><span data-stu-id="24f7b-251">Verify the report which lists the transactions.</span></span>  
    * <span data-ttu-id="24f7b-252">Vérifiez que l'état répertorie les transactions avec le numéro de document bancaire, la limite des services, le montant utilisé et le montant du solde d'établissement.</span><span class="sxs-lookup"><span data-stu-id="24f7b-252">Verify the report lists the transactions with Bank document number, Facility limit, utilized amount and the facility balance amount.</span></span>  
8. <span data-ttu-id="24f7b-253">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="24f7b-253">Close the page.</span></span>

