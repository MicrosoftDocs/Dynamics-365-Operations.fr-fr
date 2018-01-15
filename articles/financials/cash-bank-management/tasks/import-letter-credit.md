--- 
title: "Importer une lettre de crédit"
description: "Cette procédure décrit le processus d'importation d'une lettre de crédit."
author: kweekley
manager: AnnBe
ms.date: 02/26/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Operations
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f827b4787506cfdec8b9a91c4a68f3293190158a
ms.openlocfilehash: 02be2627186a149a05eaccfa3e5906a9fe1d74dd
ms.contentlocale: fr-fr
ms.lasthandoff: 11/06/2017

---
# <a name="import-a-letter-of-credit"></a><span data-ttu-id="c9211-103">Importer une lettre de crédit</span><span class="sxs-lookup"><span data-stu-id="c9211-103">Import a letter of credit</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="c9211-104">Cette procédure décrit le processus d'importation d'une lettre de crédit.</span><span class="sxs-lookup"><span data-stu-id="c9211-104">This procedure walks through the process of importing a letter of credit.</span></span> <span data-ttu-id="c9211-105">Vous devez configurer les éléments suivants avant de terminer cette procédure : les établissements bancaires, les profils de validation, un accord d'établissement bancaire et les coordonnées bancaires du fournisseur.</span><span class="sxs-lookup"><span data-stu-id="c9211-105">The following must be set up before completing this procedure: bank facilities, posting profiles, a bank facility agreement and vendor bank details.</span></span>

<span data-ttu-id="c9211-106">La société fictive USMF sert d'exemple dans cette procédure.</span><span class="sxs-lookup"><span data-stu-id="c9211-106">This procedure uses the USMF demo company.</span></span>


## <a name="create-a-purchase-order-with-letter-of-credit"></a><span data-ttu-id="c9211-107">Créer une commande fournisseur avec une lettre de crédit</span><span class="sxs-lookup"><span data-stu-id="c9211-107">Create a Purchase order with Letter of credit</span></span>
1. <span data-ttu-id="c9211-108">Accédez à Comptabilité fournisseur > Commandes fournisseur > Toutes les commandes fournisseur.</span><span class="sxs-lookup"><span data-stu-id="c9211-108">Go to Accounts payable > Purchase orders > All purchase orders.</span></span>
2. <span data-ttu-id="c9211-109">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="c9211-109">Click New.</span></span>
3. <span data-ttu-id="c9211-110">Dans le champ Compte fournisseur, saisissez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="c9211-110">In the Vendor account field, enter or select a value.</span></span>
4. <span data-ttu-id="c9211-111">Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="c9211-111">In the list, find and select the desired record.</span></span>
5. <span data-ttu-id="c9211-112">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="c9211-112">In the list, click the link in the selected row.</span></span>
6. <span data-ttu-id="c9211-113">Développez la section Général.</span><span class="sxs-lookup"><span data-stu-id="c9211-113">Expand the General section.</span></span>
7. <span data-ttu-id="c9211-114">Saisissez ou sélectionnez une valeur dans le champ Site.</span><span class="sxs-lookup"><span data-stu-id="c9211-114">In the Site field, enter or select a value.</span></span>
8. <span data-ttu-id="c9211-115">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="c9211-115">In the list, click the link in the selected row.</span></span>
9. <span data-ttu-id="c9211-116">Dans le champ Entrepôt, saisissez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="c9211-116">In the Warehouse field, enter or select a value.</span></span>
10. <span data-ttu-id="c9211-117">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="c9211-117">In the list, click the link in the selected row.</span></span>
11. <span data-ttu-id="c9211-118">Dans le champ Comptabilité, entrez une date.</span><span class="sxs-lookup"><span data-stu-id="c9211-118">In the Accounting date field, enter a date.</span></span>
12. <span data-ttu-id="c9211-119">Dans le champ Date de livraison, entrez une date.</span><span class="sxs-lookup"><span data-stu-id="c9211-119">In the Delivery date field, enter a date.</span></span>
    * <span data-ttu-id="c9211-120">Remarque : le champ « Type de document bancaire » doit être sélectionné et renseigné avec la valeur « Lettre de crédit ».</span><span class="sxs-lookup"><span data-stu-id="c9211-120">Note: The 'Bank document type' field should be selected with the value  'Letter of credit'.</span></span>  
13. <span data-ttu-id="c9211-121">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="c9211-121">Click OK.</span></span>
14. <span data-ttu-id="c9211-122">Entrez ou sélectionnez une valeur dans le champ Numéro d'article.</span><span class="sxs-lookup"><span data-stu-id="c9211-122">In the Item number field, enter or select a value.</span></span>
15. <span data-ttu-id="c9211-123">Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="c9211-123">In the list, find and select the desired record.</span></span>
16. <span data-ttu-id="c9211-124">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="c9211-124">In the list, click the link in the selected row.</span></span>
17. <span data-ttu-id="c9211-125">Développez la section Détails de ligne.</span><span class="sxs-lookup"><span data-stu-id="c9211-125">Expand the Line details section.</span></span>
18. <span data-ttu-id="c9211-126">Cliquez sur l'onglet Livraison.</span><span class="sxs-lookup"><span data-stu-id="c9211-126">Click the Delivery tab.</span></span>
19. <span data-ttu-id="c9211-127">Dans le champ Date de livraison, entrez une date.</span><span class="sxs-lookup"><span data-stu-id="c9211-127">In the Delivery date field, enter a date.</span></span>
20. <span data-ttu-id="c9211-128">Dans le champ Date de livraison confirmée, entrez une date.</span><span class="sxs-lookup"><span data-stu-id="c9211-128">In the Confirmed delivery date field, enter a date.</span></span>
21. <span data-ttu-id="c9211-129">Entrez un nombre dans le champ Prix unitaire.</span><span class="sxs-lookup"><span data-stu-id="c9211-129">In the Unit price field, enter a number.</span></span>
    * <span data-ttu-id="c9211-130">Définissez les détails de la lettre de crédit.</span><span class="sxs-lookup"><span data-stu-id="c9211-130">Define the Letter of credit details.</span></span>  
22. <span data-ttu-id="c9211-131">Dans le volet Actions, cliquez sur Gérer.</span><span class="sxs-lookup"><span data-stu-id="c9211-131">On the Action Pane, click Manage.</span></span>
23. <span data-ttu-id="c9211-132">Cliquez sur Lettre de crédit/relance d'importation.</span><span class="sxs-lookup"><span data-stu-id="c9211-132">Click Letter of credit / import collection.</span></span>
24. <span data-ttu-id="c9211-133">Dans le champ Date de demande, entrez une date et une heure.</span><span class="sxs-lookup"><span data-stu-id="c9211-133">In the Application date field, enter a date and time.</span></span>
    * <span data-ttu-id="c9211-134">Vérifiez que le champ « Compte bancaire » contient le compte bancaire actif par défaut, qui est basé sur la date de demande.</span><span class="sxs-lookup"><span data-stu-id="c9211-134">Verify that the 'Bank account' field has the default active Bank account, which is based on the application date.</span></span>  
25. <span data-ttu-id="c9211-135">Dans le champ Numéro de document bancaire, tapez une valeur.</span><span class="sxs-lookup"><span data-stu-id="c9211-135">In the Bank document number field, type a value.</span></span>
26. <span data-ttu-id="c9211-136">Dans le champ Date de réception, entrez une date et une heure.</span><span class="sxs-lookup"><span data-stu-id="c9211-136">In the Date of receipt field, enter a date and time.</span></span>
27. <span data-ttu-id="c9211-137">Développez la section Document bancaire.</span><span class="sxs-lookup"><span data-stu-id="c9211-137">Expand the Bank document section.</span></span>
28. <span data-ttu-id="c9211-138">Entrez une date et une heure dans le champ Date d'expiration.</span><span class="sxs-lookup"><span data-stu-id="c9211-138">In the Expiration date field, enter a date and time.</span></span>
29. <span data-ttu-id="c9211-139">Développez la section Détails bancaires.</span><span class="sxs-lookup"><span data-stu-id="c9211-139">Expand the Bank details section.</span></span>
30. <span data-ttu-id="c9211-140">Dans le champ Banque conseillère, saisissez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="c9211-140">In the Advising bank field, enter or select a value.</span></span>
31. <span data-ttu-id="c9211-141">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="c9211-141">In the list, click the link in the selected row.</span></span>
32. <span data-ttu-id="c9211-142">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="c9211-142">Click Save.</span></span>
33. <span data-ttu-id="c9211-143">Cliquez sur Extraire les expéditions de commandes fournisseur.</span><span class="sxs-lookup"><span data-stu-id="c9211-143">Click Fetch purchase order shipments.</span></span>
34. <span data-ttu-id="c9211-144">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="c9211-144">Close the page.</span></span>
35. <span data-ttu-id="c9211-145">Cliquez sur Achats dans le volet Actions.</span><span class="sxs-lookup"><span data-stu-id="c9211-145">On the Action Pane, click Purchase.</span></span>
36. <span data-ttu-id="c9211-146">Cliquez sur Confirmer.</span><span class="sxs-lookup"><span data-stu-id="c9211-146">Click Confirm.</span></span>
37. <span data-ttu-id="c9211-147">Dans le volet Actions, cliquez sur Gérer.</span><span class="sxs-lookup"><span data-stu-id="c9211-147">On the Action Pane, click Manage.</span></span>
38. <span data-ttu-id="c9211-148">Cliquez sur Lettre de crédit/relance d'importation.</span><span class="sxs-lookup"><span data-stu-id="c9211-148">Click Letter of credit / import collection.</span></span>
39. <span data-ttu-id="c9211-149">Cliquez sur Traiter.</span><span class="sxs-lookup"><span data-stu-id="c9211-149">Click Process.</span></span>
40. <span data-ttu-id="c9211-150">Cliquez sur Confirmer.</span><span class="sxs-lookup"><span data-stu-id="c9211-150">Click Confirm.</span></span>
    * <span data-ttu-id="c9211-151">Vérifiez que le solde de l'établissement réduit le montant de la commande fournisseur.</span><span class="sxs-lookup"><span data-stu-id="c9211-151">Verify that the Facility balance reduces the purchase order amount.</span></span>  <span data-ttu-id="c9211-152">Dans cet exemple, Montant des achats = 500,00, Limite des services = 10000,00, par conséquent, Solde de l'établissement = 9500,00.</span><span class="sxs-lookup"><span data-stu-id="c9211-152">In this example, Purchase amount = 500.00,  Facility limit = 10000.00,  therefore, Facility balance = 9500.00.</span></span>  
41. <span data-ttu-id="c9211-153">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="c9211-153">Close the page.</span></span>
42. <span data-ttu-id="c9211-154">Entrez un nombre dans le champ Prix unitaire.</span><span class="sxs-lookup"><span data-stu-id="c9211-154">In the Unit price field, enter a number.</span></span>
43. <span data-ttu-id="c9211-155">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="c9211-155">Click Save.</span></span>
44. <span data-ttu-id="c9211-156">Cliquez sur Achats dans le volet Actions.</span><span class="sxs-lookup"><span data-stu-id="c9211-156">On the Action Pane, click Purchase.</span></span>
45. <span data-ttu-id="c9211-157">Cliquez sur Confirmer.</span><span class="sxs-lookup"><span data-stu-id="c9211-157">Click Confirm.</span></span>
    * <span data-ttu-id="c9211-158">Modifiez la lettre de crédit, en fonction de la modification du prix unitaire.</span><span class="sxs-lookup"><span data-stu-id="c9211-158">Amend the Letter of credit, due to the change in Unit price.</span></span>  
46. <span data-ttu-id="c9211-159">Dans le volet Actions, cliquez sur Gérer.</span><span class="sxs-lookup"><span data-stu-id="c9211-159">On the Action Pane, click Manage.</span></span>
47. <span data-ttu-id="c9211-160">Cliquez sur Lettre de crédit/relance d'importation.</span><span class="sxs-lookup"><span data-stu-id="c9211-160">Click Letter of credit / import collection.</span></span>
    * <span data-ttu-id="c9211-161">Modifiez la lettre de crédit, en fonction de la modification du prix unitaire d'achat.</span><span class="sxs-lookup"><span data-stu-id="c9211-161">Amend the letter of credit, due to the change in Purchase unit price.</span></span>  
48. <span data-ttu-id="c9211-162">Cliquez sur Traiter.</span><span class="sxs-lookup"><span data-stu-id="c9211-162">Click Process.</span></span>
49. <span data-ttu-id="c9211-163">Cliquez sur Amender.</span><span class="sxs-lookup"><span data-stu-id="c9211-163">Click Amend.</span></span>
50. <span data-ttu-id="c9211-164">Cliquez sur Supprimer.</span><span class="sxs-lookup"><span data-stu-id="c9211-164">Click Remove.</span></span>
51. <span data-ttu-id="c9211-165">Cliquez sur Oui.</span><span class="sxs-lookup"><span data-stu-id="c9211-165">Click Yes.</span></span>
52. <span data-ttu-id="c9211-166">Cliquez sur Extraire les expéditions de commandes fournisseur.</span><span class="sxs-lookup"><span data-stu-id="c9211-166">Click Fetch purchase order shipments.</span></span>
53. <span data-ttu-id="c9211-167">Cliquez sur Traiter.</span><span class="sxs-lookup"><span data-stu-id="c9211-167">Click Process.</span></span>
54. <span data-ttu-id="c9211-168">Cliquez sur Confirmer.</span><span class="sxs-lookup"><span data-stu-id="c9211-168">Click Confirm.</span></span>
    * <span data-ttu-id="c9211-169">Vérifiez que le solde de l'établissement réduit le montant de la commande fournisseur.</span><span class="sxs-lookup"><span data-stu-id="c9211-169">Verify that the Facility balance reduces the purchase order amount.</span></span>  <span data-ttu-id="c9211-170">Dans cet exemple, Montant modifié des achats = 600,00, Limite des services = 10 000,00, par conséquent, Solde de l'établissement = 9 400,00.</span><span class="sxs-lookup"><span data-stu-id="c9211-170">In this example, edited Purchase amount = 600.00,  Facility limit = 10000.00,  therefore, Facility balance = 9400.00.</span></span>  
55. <span data-ttu-id="c9211-171">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="c9211-171">Close the page.</span></span>

## <a name="post-packing-slip"></a><span data-ttu-id="c9211-172">Valider un bon de livraison</span><span class="sxs-lookup"><span data-stu-id="c9211-172">Post Packing slip</span></span>
1. <span data-ttu-id="c9211-173">Dans le volet Actions, cliquez sur Recevoir.</span><span class="sxs-lookup"><span data-stu-id="c9211-173">On the Action Pane, click Receive.</span></span>
2. <span data-ttu-id="c9211-174">Cliquez sur Accusé de réception de marchandises.</span><span class="sxs-lookup"><span data-stu-id="c9211-174">Click Product receipt.</span></span>
3. <span data-ttu-id="c9211-175">Dans le champ PurchParmTable_Num, tapez une valeur.</span><span class="sxs-lookup"><span data-stu-id="c9211-175">In the PurchParmTable_Num field, type a value.</span></span>
    * <span data-ttu-id="c9211-176">Sélectionnez le numéro d'expédition créé en référence à la lettre de crédit.</span><span class="sxs-lookup"><span data-stu-id="c9211-176">Select the Shipment number created with reference to the Letter of credit.</span></span>  
4. <span data-ttu-id="c9211-177">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="c9211-177">In the list, click the link in the selected row.</span></span>
5. <span data-ttu-id="c9211-178">Dans le champ Date de l'accusé de réception de marchandises, entrez une date.</span><span class="sxs-lookup"><span data-stu-id="c9211-178">In the Product receipt date field, enter a date.</span></span>
6. <span data-ttu-id="c9211-179">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="c9211-179">Click OK.</span></span>
7. <span data-ttu-id="c9211-180">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="c9211-180">Close the page.</span></span>
8. <span data-ttu-id="c9211-181">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="c9211-181">Close the page.</span></span>

## <a name="verify-import-letter-of-credit-status"></a><span data-ttu-id="c9211-182">Vérifier le statut d'une lettre de crédit d'importation</span><span class="sxs-lookup"><span data-stu-id="c9211-182">Verify Import letter of credit status</span></span>
1. <span data-ttu-id="c9211-183">Accédez à Gestion de la trésorerie et de la banque > Lettres de crédit > Lettre de crédit d'importation/relance d'importation.</span><span class="sxs-lookup"><span data-stu-id="c9211-183">Go to Cash and bank management > Letters of credit > Import letter of credit and import collection.</span></span>
2. <span data-ttu-id="c9211-184">Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="c9211-184">In the list, find and select the desired record.</span></span>
3. <span data-ttu-id="c9211-185">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="c9211-185">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="c9211-186">Vérifiez le statut de la lettre de crédit d'importation.</span><span class="sxs-lookup"><span data-stu-id="c9211-186">Verify the Import letter of credit status.</span></span>  
4. <span data-ttu-id="c9211-187">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="c9211-187">Close the page.</span></span>
5. <span data-ttu-id="c9211-188">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="c9211-188">Close the page.</span></span>

## <a name="post-purchase-invoice"></a><span data-ttu-id="c9211-189">Valider une facture d'achat</span><span class="sxs-lookup"><span data-stu-id="c9211-189">Post purchase invoice</span></span>
1. <span data-ttu-id="c9211-190">Accédez à Comptabilité fournisseur > Commandes fournisseur > Toutes les commandes fournisseur.</span><span class="sxs-lookup"><span data-stu-id="c9211-190">Go to Accounts payable > Purchase orders > All purchase orders.</span></span>
    * <span data-ttu-id="c9211-191">Sélectionnez la commande fournisseur créée avec la lettre de crédit.</span><span class="sxs-lookup"><span data-stu-id="c9211-191">Select the purchase order that was created with letter of credit.</span></span>  
2. <span data-ttu-id="c9211-192">Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="c9211-192">In the list, find and select the desired record.</span></span>
3. <span data-ttu-id="c9211-193">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="c9211-193">In the list, click the link in the selected row.</span></span>
4. <span data-ttu-id="c9211-194">Dans le volet Actions, cliquez sur Facture.</span><span class="sxs-lookup"><span data-stu-id="c9211-194">On the Action Pane, click Invoice.</span></span>
5. <span data-ttu-id="c9211-195">Cliquez sur Facture.</span><span class="sxs-lookup"><span data-stu-id="c9211-195">Click Invoice.</span></span>
6. <span data-ttu-id="c9211-196">Tapez une valeur dans le champ Nombre.</span><span class="sxs-lookup"><span data-stu-id="c9211-196">In the Number field, type a value.</span></span>
7. <span data-ttu-id="c9211-197">Dans le champ Numéro d'expédition, entrez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="c9211-197">In the Shipment number field, enter or select a value.</span></span>
8. <span data-ttu-id="c9211-198">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="c9211-198">In the list, click the link in the selected row.</span></span>
9. <span data-ttu-id="c9211-199">Entrez une date dans le champ Date de facture.</span><span class="sxs-lookup"><span data-stu-id="c9211-199">In the Invoice date field, enter a date.</span></span>
10. <span data-ttu-id="c9211-200">Cliquez sur Mettre à jour le statut de rapprochement.</span><span class="sxs-lookup"><span data-stu-id="c9211-200">Click Update match status.</span></span>
11. <span data-ttu-id="c9211-201">Cliquez sur Valider.</span><span class="sxs-lookup"><span data-stu-id="c9211-201">Click Post.</span></span>
12. <span data-ttu-id="c9211-202">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="c9211-202">Close the page.</span></span>
13. <span data-ttu-id="c9211-203">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="c9211-203">Close the page.</span></span>

## <a name="verify-import-letter-of-credit-status"></a><span data-ttu-id="c9211-204">Vérifier le statut d'une lettre de crédit d'importation</span><span class="sxs-lookup"><span data-stu-id="c9211-204">Verify Import letter of credit status</span></span>
1. <span data-ttu-id="c9211-205">Accédez à Gestion de la trésorerie et de la banque > Lettres de crédit > Lettre de crédit d'importation/relance d'importation.</span><span class="sxs-lookup"><span data-stu-id="c9211-205">Go to Cash and bank management > Letters of credit > Import letter of credit and import collection.</span></span>
2. <span data-ttu-id="c9211-206">Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="c9211-206">In the list, find and select the desired record.</span></span>
3. <span data-ttu-id="c9211-207">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="c9211-207">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="c9211-208">Vérifiez la lettre de crédit d'importation 2.</span><span class="sxs-lookup"><span data-stu-id="c9211-208">Verify the Import letter of credit2.</span></span>  
    * <span data-ttu-id="c9211-209">Validez : Statut de l'expédition = détails de l'établissement bancaire facturé</span><span class="sxs-lookup"><span data-stu-id="c9211-209">Validate :  Shipment status = Invoiced  Bank facility details</span></span>  
4. <span data-ttu-id="c9211-210">Cliquez sur Afficher.</span><span class="sxs-lookup"><span data-stu-id="c9211-210">Click View.</span></span>
5. <span data-ttu-id="c9211-211">Cliquez sur Imprimer la demande.</span><span class="sxs-lookup"><span data-stu-id="c9211-211">Click Print application.</span></span>
6. <span data-ttu-id="c9211-212">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="c9211-212">Click OK.</span></span>
    * <span data-ttu-id="c9211-213">Vérifiez que la demande de lettre de crédit est imprimée.</span><span class="sxs-lookup"><span data-stu-id="c9211-213">Verify that the Letter of credit application gets printed.</span></span>  
7. <span data-ttu-id="c9211-214">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="c9211-214">Close the page.</span></span>
8. <span data-ttu-id="c9211-215">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="c9211-215">Close the page.</span></span>
9. <span data-ttu-id="c9211-216">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="c9211-216">Close the page.</span></span>

## <a name="post-vendor-payment-journal-for-the-created-purchase-invoice-with-letter-of-credit"></a><span data-ttu-id="c9211-217">Valider le journal des paiements fournisseur pour la facture d'achat créée avec une lettre de crédit</span><span class="sxs-lookup"><span data-stu-id="c9211-217">Post Vendor payment journal for the created purchase invoice with letter of credit</span></span>
1. <span data-ttu-id="c9211-218">Accédez à Comptabilité fournisseur > Paiements > Journal des paiements.</span><span class="sxs-lookup"><span data-stu-id="c9211-218">Go to Accounts payable > Payments > Payment journal.</span></span>
2. <span data-ttu-id="c9211-219">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="c9211-219">Click New.</span></span>
3. <span data-ttu-id="c9211-220">Saisissez ou sélectionnez une valeur dans le champ Nom.</span><span class="sxs-lookup"><span data-stu-id="c9211-220">In the Name field, enter or select a value.</span></span>
4. <span data-ttu-id="c9211-221">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="c9211-221">In the list, click the link in the selected row.</span></span>
5. <span data-ttu-id="c9211-222">Cliquez sur Lignes.</span><span class="sxs-lookup"><span data-stu-id="c9211-222">Click Lines.</span></span>
6. <span data-ttu-id="c9211-223">Entrez une date dans le champ Date.</span><span class="sxs-lookup"><span data-stu-id="c9211-223">In the Date field, enter a date.</span></span>
7. <span data-ttu-id="c9211-224">Dans le champ Compte, spécifiez les valeurs souhaitées.</span><span class="sxs-lookup"><span data-stu-id="c9211-224">In the Account field, specify the desired values.</span></span>
8. <span data-ttu-id="c9211-225">Cliquez sur Régler les transactions.</span><span class="sxs-lookup"><span data-stu-id="c9211-225">Click Settle transactions.</span></span>
9. <span data-ttu-id="c9211-226">Développez la section Totaux.</span><span class="sxs-lookup"><span data-stu-id="c9211-226">Expand the Totals section.</span></span>
10. <span data-ttu-id="c9211-227">Dans le champ Afficher, sélectionnez une option.</span><span class="sxs-lookup"><span data-stu-id="c9211-227">In the Show field, select an option.</span></span>
    * <span data-ttu-id="c9211-228">Vérifiez que les champs Numéro de document bancaire et Numéro d'expédition ont été mis à jour.</span><span class="sxs-lookup"><span data-stu-id="c9211-228">Verify that the Bank document number and Shipment number fields have been updated.</span></span>  
11. <span data-ttu-id="c9211-229">Cochez la case Marquer.</span><span class="sxs-lookup"><span data-stu-id="c9211-229">Select the Mark check box.</span></span>
12. <span data-ttu-id="c9211-230">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="c9211-230">Click OK.</span></span>
13. <span data-ttu-id="c9211-231">Cliquez sur l'onglet Paiement.</span><span class="sxs-lookup"><span data-stu-id="c9211-231">Click the Payment tab.</span></span>
    * <span data-ttu-id="c9211-232">Vérifiez que les champs Numéro de document bancaire et Numéro d'expédition ont été mis à jour.</span><span class="sxs-lookup"><span data-stu-id="c9211-232">Verify that the Bank document number and Shipment number fields have been updated.</span></span>  
14. <span data-ttu-id="c9211-233">Cliquez sur Valider.</span><span class="sxs-lookup"><span data-stu-id="c9211-233">Click Post.</span></span>
15. <span data-ttu-id="c9211-234">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="c9211-234">Close the page.</span></span>
16. <span data-ttu-id="c9211-235">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="c9211-235">Close the page.</span></span>

## <a name="verify-import-letter-of-credit-status-after-invoice-paid"></a><span data-ttu-id="c9211-236">Vérifier le statut de la lettre de crédit d'importation une fois la facture payée</span><span class="sxs-lookup"><span data-stu-id="c9211-236">Verify Import letter of credit status after Invoice paid</span></span>
1. <span data-ttu-id="c9211-237">Accédez à Gestion de la trésorerie et de la banque > Lettres de crédit > Lettre de crédit d'importation/relance d'importation.</span><span class="sxs-lookup"><span data-stu-id="c9211-237">Go to Cash and bank management > Letters of credit > Import letter of credit and import collection.</span></span>
2. <span data-ttu-id="c9211-238">Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="c9211-238">In the list, find and select the desired record.</span></span>
3. <span data-ttu-id="c9211-239">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="c9211-239">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="c9211-240">Vérifiez le statut de la lettre de crédit d'importation.</span><span class="sxs-lookup"><span data-stu-id="c9211-240">Verify the Import letter of credit status.</span></span>   
4. <span data-ttu-id="c9211-241">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="c9211-241">Close the page.</span></span>

## <a name="verify-the-bank-facility-limit-and-utilization-report"></a><span data-ttu-id="c9211-242">Vérifier l'état de la limite des services de l'établissement bancaire et l'utilisation</span><span class="sxs-lookup"><span data-stu-id="c9211-242">Verify the Bank facility limit and utilization report</span></span>
1. <span data-ttu-id="c9211-243">Accédez à Gestion de la trésorerie et de la banque > Recherches et états > Lettres de crédit ou garantie > État des moyens bancaires et utilisation.</span><span class="sxs-lookup"><span data-stu-id="c9211-243">Go to Cash and bank management > Inquiries and reports > Letters of credit or guarantee > Bank facilities and utilization report.</span></span>
2. <span data-ttu-id="c9211-244">Développez les enregistrements pour inclure la section.</span><span class="sxs-lookup"><span data-stu-id="c9211-244">Expand the Records to include section.</span></span>
3. <span data-ttu-id="c9211-245">Cliquez sur Filtre.</span><span class="sxs-lookup"><span data-stu-id="c9211-245">Click Filter.</span></span>
    * <span data-ttu-id="c9211-246">Définissez le champ Critères avec le compte bancaire requis.</span><span class="sxs-lookup"><span data-stu-id="c9211-246">Define the Criteria field with the required bank account.</span></span>  
4. <span data-ttu-id="c9211-247">Dans le champ Critères, saisissez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="c9211-247">In the Criteria field, enter or select a value.</span></span>
5. <span data-ttu-id="c9211-248">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="c9211-248">In the list, click the link in the selected row.</span></span>
6. <span data-ttu-id="c9211-249">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="c9211-249">Click OK.</span></span>
7. <span data-ttu-id="c9211-250">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="c9211-250">Click OK.</span></span>
    * <span data-ttu-id="c9211-251">Vérifiez l'état qui répertorie les transactions.</span><span class="sxs-lookup"><span data-stu-id="c9211-251">Verify the report which lists the transactions.</span></span>  
    * <span data-ttu-id="c9211-252">Vérifiez que l'état répertorie les transactions avec le numéro de document bancaire, la limite des services, le montant utilisé et le montant du solde d'établissement.</span><span class="sxs-lookup"><span data-stu-id="c9211-252">Verify the report lists the transactions with Bank document number, Facility limit, utilized amount and the facility balance amount.</span></span>  
8. <span data-ttu-id="c9211-253">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="c9211-253">Close the page.</span></span>

