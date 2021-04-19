---
title: Lettre de crédit d’exportation
description: Cette procédure décrit le processus associé à une lettre de crédit d’exportation.
author: kweekley
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: CustTable, CustBankAccounts, DefaultDashboard, SalesTableListPage, SalesCreateOrder, SalesTable, BankLCExport, SalesEditLines,  LedgerJournalTable, LedgerJournalTransCustPaym, CustOpenTrans
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 260ef2d05e1f21708817346af2db2841aa6acdd9
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5834786"
---
# <a name="export-letter-of-credit"></a><span data-ttu-id="1c8aa-103">Lettre de crédit d’exportation</span><span class="sxs-lookup"><span data-stu-id="1c8aa-103">Export letter of credit</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="1c8aa-104">Cette procédure décrit le processus associé à une lettre de crédit d’exportation.</span><span class="sxs-lookup"><span data-stu-id="1c8aa-104">This procedure walks through the process of the Export letter of credit.</span></span>

<span data-ttu-id="1c8aa-105">Une lettre de crédit est un accord émis par une banque, dans lequel la banque accepte de garantir le paiement au nom de l’acheteur, si les conditions de l’accord entre l’acheteur et le vendeur sont satisfaites.</span><span class="sxs-lookup"><span data-stu-id="1c8aa-105">A letter of credit is an agreement that is issued by a bank, in which the bank agrees to ensure payment on behalf of the buyer, if the terms of the agreement between the buyer and seller are met.</span></span>



<span data-ttu-id="1c8aa-106">Préalablement à cette procédure, exécutez la procédure « Paramétrage des établissements bancaires et profils de validation » et la procédure « Lettre de crédit_Création d’un accord d’établissement bancaire ».</span><span class="sxs-lookup"><span data-stu-id="1c8aa-106">Run the 'Set up bank facilities and posting profiles' procedure and the 'Letter of Credit_Create a bank facility agreement' procedure prior to this procedure.</span></span> <span data-ttu-id="1c8aa-107">Pour exécuter cette procédure correctement, vous devez sélectionner la société fictive USMF.</span><span class="sxs-lookup"><span data-stu-id="1c8aa-107">The USMF demo company must be selected in order to run this procedure successfully.</span></span>




## <a name="create-sales-order-for-export-letter-of-credit"></a><span data-ttu-id="1c8aa-108">Créer une commande client pour une lettre de crédit d’exportation</span><span class="sxs-lookup"><span data-stu-id="1c8aa-108">Create Sales Order for Export letter of credit</span></span>
1. <span data-ttu-id="1c8aa-109">Accédez à Comptabilité client > Commandes > Toutes les commandes client.</span><span class="sxs-lookup"><span data-stu-id="1c8aa-109">Go to Accounts receivable > Orders > All sales orders.</span></span>
2. <span data-ttu-id="1c8aa-110">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="1c8aa-110">Click New.</span></span>
3. <span data-ttu-id="1c8aa-111">Dans le champ Compte client, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="1c8aa-111">In the Customer account field, click the drop-down button to open the lookup.</span></span>
4. <span data-ttu-id="1c8aa-112">Dans la liste, recherchez et sélectionnez l’enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="1c8aa-112">In the list, find and select the desired record.</span></span>
5. <span data-ttu-id="1c8aa-113">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="1c8aa-113">In the list, click the link in the selected row.</span></span>
6. <span data-ttu-id="1c8aa-114">Développez ou réduisez la section Général.</span><span class="sxs-lookup"><span data-stu-id="1c8aa-114">Expand or collapse the General section.</span></span>
7. <span data-ttu-id="1c8aa-115">Dans le champ Site, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="1c8aa-115">In the Site field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="1c8aa-116">Sélectionner le site où l’article qui doit sortir est stocké.</span><span class="sxs-lookup"><span data-stu-id="1c8aa-116">Select the Site where the item to be issued is stocked.</span></span>  
8. <span data-ttu-id="1c8aa-117">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="1c8aa-117">In the list, click the link in the selected row.</span></span>
9. <span data-ttu-id="1c8aa-118">Dans le champ Entrepôt, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="1c8aa-118">In the Warehouse field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="1c8aa-119">Sélectionner l’entrepôt où l’article qui doit sortir est stocké.</span><span class="sxs-lookup"><span data-stu-id="1c8aa-119">Select the Warehouse where item to be issued is stocked.</span></span>  
10. <span data-ttu-id="1c8aa-120">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="1c8aa-120">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="1c8aa-121">Remarque : le champ « Type de document bancaire » doit être sélectionné et renseigné avec la valeur « Lettre de crédit ».</span><span class="sxs-lookup"><span data-stu-id="1c8aa-121">Note: The Bank document type field should be selected with the value 'Letter of credit'.</span></span>  
11. <span data-ttu-id="1c8aa-122">Dans le champ Type de document bancaire, sélectionnez « Lettre de crédit ».</span><span class="sxs-lookup"><span data-stu-id="1c8aa-122">In the Bank document type field, select 'Letter of credit'.</span></span>
12. <span data-ttu-id="1c8aa-123">Développez ou réduisez la section Livraison.</span><span class="sxs-lookup"><span data-stu-id="1c8aa-123">Expand or collapse the Delivery section.</span></span>
    * <span data-ttu-id="1c8aa-124">Sélectionnez Vérification de la date de livraison = Aucun(e).</span><span class="sxs-lookup"><span data-stu-id="1c8aa-124">Select Delivery date control = None.</span></span>  
13. <span data-ttu-id="1c8aa-125">Dans le champ Date de réception demandée, entrez une date.</span><span class="sxs-lookup"><span data-stu-id="1c8aa-125">In the Requested receipt date field, enter a date.</span></span>
14. <span data-ttu-id="1c8aa-126">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="1c8aa-126">Click OK.</span></span>
15. <span data-ttu-id="1c8aa-127">Dans le champ Numéro d’article, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="1c8aa-127">In the Item number field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="1c8aa-128">Sélectionnez l’article requis qui doit sortir/être vendu.</span><span class="sxs-lookup"><span data-stu-id="1c8aa-128">Select the required item to be Issued/Sold.</span></span>  
16. <span data-ttu-id="1c8aa-129">Dans la liste, recherchez et sélectionnez l’enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="1c8aa-129">In the list, find and select the desired record.</span></span>
17. <span data-ttu-id="1c8aa-130">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="1c8aa-130">In the list, click the link in the selected row.</span></span>
18. <span data-ttu-id="1c8aa-131">Entrez un nombre dans le champ Prix unitaire.</span><span class="sxs-lookup"><span data-stu-id="1c8aa-131">In the Unit price field, enter a number.</span></span>
19. <span data-ttu-id="1c8aa-132">Développez ou réduisez la section Détails de ligne.</span><span class="sxs-lookup"><span data-stu-id="1c8aa-132">Expand or collapse the Line details section.</span></span>
20. <span data-ttu-id="1c8aa-133">Cliquez sur l’onglet Livraison.</span><span class="sxs-lookup"><span data-stu-id="1c8aa-133">Click the Delivery tab.</span></span>
21. <span data-ttu-id="1c8aa-134">Dans le champ Date d’expédition demandée, entrez une date.</span><span class="sxs-lookup"><span data-stu-id="1c8aa-134">In the Requested ship date field, enter a date.</span></span>
22. <span data-ttu-id="1c8aa-135">Dans le champ Date d’expédition confirmée, entrez une date.</span><span class="sxs-lookup"><span data-stu-id="1c8aa-135">In the Confirmed ship date field, enter a date.</span></span>
23. <span data-ttu-id="1c8aa-136">Dans le volet Actions, cliquez sur Gérer.</span><span class="sxs-lookup"><span data-stu-id="1c8aa-136">On the Action Pane, click Manage.</span></span>
24. <span data-ttu-id="1c8aa-137">Cliquez sur Lettre de crédit.</span><span class="sxs-lookup"><span data-stu-id="1c8aa-137">Click Letter of credit.</span></span>
25. <span data-ttu-id="1c8aa-138">Dans le champ Numéro de document bancaire, tapez une valeur.</span><span class="sxs-lookup"><span data-stu-id="1c8aa-138">In the Bank document number field, type a value.</span></span>
26. <span data-ttu-id="1c8aa-139">Entrez une date et une heure dans le champ Date d’expiration.</span><span class="sxs-lookup"><span data-stu-id="1c8aa-139">In the Expiration date field, enter a date and time.</span></span>
27. <span data-ttu-id="1c8aa-140">Développez ou réduisez la section Détails bancaires.</span><span class="sxs-lookup"><span data-stu-id="1c8aa-140">Expand or collapse the Bank details section.</span></span>
28. <span data-ttu-id="1c8aa-141">Dans le champ Banque émettrice, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="1c8aa-141">In the Issuing bank field, click the drop-down button to open the lookup.</span></span>
29. <span data-ttu-id="1c8aa-142">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="1c8aa-142">In the list, click the link in the selected row.</span></span>
30. <span data-ttu-id="1c8aa-143">Dans le champ Banque conseillère, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="1c8aa-143">In the Advising bank field, click the drop-down button to open the lookup.</span></span>
31. <span data-ttu-id="1c8aa-144">Dans la liste, recherchez et sélectionnez l’enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="1c8aa-144">In the list, find and select the desired record.</span></span>
32. <span data-ttu-id="1c8aa-145">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="1c8aa-145">In the list, click the link in the selected row.</span></span>
33. <span data-ttu-id="1c8aa-146">Cliquez sur Extraire les expéditions de la commande client.</span><span class="sxs-lookup"><span data-stu-id="1c8aa-146">Click Fetch sales order shipments.</span></span>
34. <span data-ttu-id="1c8aa-147">Cliquez sur Émettre le document bancaire.</span><span class="sxs-lookup"><span data-stu-id="1c8aa-147">Click Issue bank document.</span></span>
35. <span data-ttu-id="1c8aa-148">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="1c8aa-148">Close the page.</span></span>

## <a name="post-packing-slip"></a><span data-ttu-id="1c8aa-149">Valider un bon de livraison</span><span class="sxs-lookup"><span data-stu-id="1c8aa-149">Post Packing slip</span></span>
1. <span data-ttu-id="1c8aa-150">Cliquez sur Prélever et emballer dans le volet Actions.</span><span class="sxs-lookup"><span data-stu-id="1c8aa-150">On the Action Pane, click Pick and pack.</span></span>
2. <span data-ttu-id="1c8aa-151">Cliquez sur Validation du bon de livraison.</span><span class="sxs-lookup"><span data-stu-id="1c8aa-151">Click Post packing slip.</span></span>
3. <span data-ttu-id="1c8aa-152">Développez ou réduisez la section Paramètres.</span><span class="sxs-lookup"><span data-stu-id="1c8aa-152">Expand or collapse the Parameters section.</span></span>
4. <span data-ttu-id="1c8aa-153">Sélectionnez Tout dans le champ Quantité.</span><span class="sxs-lookup"><span data-stu-id="1c8aa-153">In the Quantity field, select 'All'.</span></span>
5. <span data-ttu-id="1c8aa-154">Développez ou réduisez la section Paramétrage.</span><span class="sxs-lookup"><span data-stu-id="1c8aa-154">Expand or collapse the Setup section.</span></span>
6. <span data-ttu-id="1c8aa-155">Dans le champ Date de bon de livraison, entrez une date.</span><span class="sxs-lookup"><span data-stu-id="1c8aa-155">In the Packing slip date field, enter a date.</span></span>
7. <span data-ttu-id="1c8aa-156">Sélectionnez le numéro d’expédition.</span><span class="sxs-lookup"><span data-stu-id="1c8aa-156">Select the Shipment number.</span></span>
8. <span data-ttu-id="1c8aa-157">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="1c8aa-157">In the list, click the link in the selected row.</span></span>
9. <span data-ttu-id="1c8aa-158">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="1c8aa-158">Click OK.</span></span>
10. <span data-ttu-id="1c8aa-159">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="1c8aa-159">Click OK.</span></span>

## <a name="post-sales-invoice"></a><span data-ttu-id="1c8aa-160">Valider une facture client</span><span class="sxs-lookup"><span data-stu-id="1c8aa-160">Post sales invoice</span></span>
1. <span data-ttu-id="1c8aa-161">Dans le volet Actions, cliquez sur Facture.</span><span class="sxs-lookup"><span data-stu-id="1c8aa-161">On the Action Pane, click Invoice.</span></span>
2. <span data-ttu-id="1c8aa-162">Cliquez sur Facture.</span><span class="sxs-lookup"><span data-stu-id="1c8aa-162">Click Invoice.</span></span>
3. <span data-ttu-id="1c8aa-163">Développez ou réduisez la section Vue d’ensemble.</span><span class="sxs-lookup"><span data-stu-id="1c8aa-163">Expand or collapse the Overview section.</span></span>
4. <span data-ttu-id="1c8aa-164">Sélectionnez le numéro d’expédition.</span><span class="sxs-lookup"><span data-stu-id="1c8aa-164">Select the Shipment number.</span></span>
5. <span data-ttu-id="1c8aa-165">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="1c8aa-165">In the list, click the link in the selected row.</span></span>
6. <span data-ttu-id="1c8aa-166">Développez ou réduisez la section Paramétrage.</span><span class="sxs-lookup"><span data-stu-id="1c8aa-166">Expand or collapse the Setup section.</span></span>
7. <span data-ttu-id="1c8aa-167">Entrez une date dans le champ Date de facture.</span><span class="sxs-lookup"><span data-stu-id="1c8aa-167">In the Invoice date field, enter a date.</span></span>
8. <span data-ttu-id="1c8aa-168">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="1c8aa-168">Click OK.</span></span>
9. <span data-ttu-id="1c8aa-169">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="1c8aa-169">Click OK.</span></span>

## <a name="shipment-document-submitted-status"></a><span data-ttu-id="1c8aa-170">Statut du document d’expédition soumis</span><span class="sxs-lookup"><span data-stu-id="1c8aa-170">Shipment document submitted status</span></span>
1. <span data-ttu-id="1c8aa-171">Dans le volet Actions, cliquez sur Gérer.</span><span class="sxs-lookup"><span data-stu-id="1c8aa-171">On the Action Pane, click Manage.</span></span>
2. <span data-ttu-id="1c8aa-172">Cliquez sur Lettre de crédit.</span><span class="sxs-lookup"><span data-stu-id="1c8aa-172">Click Letter of credit.</span></span>
3. <span data-ttu-id="1c8aa-173">Développez ou réduisez la section Lignes.</span><span class="sxs-lookup"><span data-stu-id="1c8aa-173">Expand or collapse the Lines section.</span></span>
    * <span data-ttu-id="1c8aa-174">Remarque : le champ « Document soumis » doit être défini à « Oui ».</span><span class="sxs-lookup"><span data-stu-id="1c8aa-174">Note: The 'Document submitted' field should be set to 'Yes'.</span></span>  

## <a name="verify-export-letter-of-credit"></a><span data-ttu-id="1c8aa-175">Vérifier la lettre de crédit d’exportation</span><span class="sxs-lookup"><span data-stu-id="1c8aa-175">Verify Export letter of credit</span></span>
1. <span data-ttu-id="1c8aa-176">Accédez à Gestion de la trésorerie et de la banque > Lettres de crédit > Lettre de crédit d’exportation/relance d’importation.</span><span class="sxs-lookup"><span data-stu-id="1c8aa-176">Go to Cash and bank management > Letters of credit > Export letter of credit and import collection.</span></span>
2. <span data-ttu-id="1c8aa-177">Dans la liste, recherchez et sélectionnez l’enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="1c8aa-177">In the list, find and select the desired record.</span></span>
3. <span data-ttu-id="1c8aa-178">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="1c8aa-178">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="1c8aa-179">Vérifiez que la lettre de crédit d’exportation est dotée du statut d’expédition « Facturée ».</span><span class="sxs-lookup"><span data-stu-id="1c8aa-179">Verify that the Export letter of credit has a Shipment status of 'Invoiced'.</span></span>  

## <a name="customer-payment"></a><span data-ttu-id="1c8aa-180">Client – Paiements</span><span class="sxs-lookup"><span data-stu-id="1c8aa-180">Customer payment</span></span>
1. <span data-ttu-id="1c8aa-181">Accédez à Comptabilité client > Paiements > Journal des paiements.</span><span class="sxs-lookup"><span data-stu-id="1c8aa-181">Go to Accounts receivable > Payments > Payment journal.</span></span>
2. <span data-ttu-id="1c8aa-182">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="1c8aa-182">Click New.</span></span>
3. <span data-ttu-id="1c8aa-183">Dans la liste, marquez la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="1c8aa-183">In the list, mark the selected row.</span></span>
4. <span data-ttu-id="1c8aa-184">Dans le champ Nom, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="1c8aa-184">In the Name field, click the drop-down button to open the lookup.</span></span>
5. <span data-ttu-id="1c8aa-185">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="1c8aa-185">In the list, click the link in the selected row.</span></span>
6. <span data-ttu-id="1c8aa-186">Cliquez sur Lignes.</span><span class="sxs-lookup"><span data-stu-id="1c8aa-186">Click Lines.</span></span>
7. <span data-ttu-id="1c8aa-187">Entrez une date dans le champ Date.</span><span class="sxs-lookup"><span data-stu-id="1c8aa-187">In the Date field, enter a date.</span></span>
8. <span data-ttu-id="1c8aa-188">Dans le champ Compte, spécifiez les valeurs souhaitées.</span><span class="sxs-lookup"><span data-stu-id="1c8aa-188">In the Account field, specify the desired values.</span></span>
9. <span data-ttu-id="1c8aa-189">Cliquez sur Règlement.</span><span class="sxs-lookup"><span data-stu-id="1c8aa-189">Click Settlement.</span></span>
10. <span data-ttu-id="1c8aa-190">Cochez la case dans l’en-tête de Totaux.</span><span class="sxs-lookup"><span data-stu-id="1c8aa-190">Select the check box on the header of Totals.</span></span>
    * <span data-ttu-id="1c8aa-191">Remarque : définissez le champ Afficher à « Lettre de crédit ».</span><span class="sxs-lookup"><span data-stu-id="1c8aa-191">Note: Set the Show field to 'Letter of credit'.</span></span>  
11. <span data-ttu-id="1c8aa-192">Dans la liste, recherchez et sélectionnez l’enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="1c8aa-192">In the list, find and select the desired record.</span></span>
12. <span data-ttu-id="1c8aa-193">Activez ou désactivez la case à cocher Marquer.</span><span class="sxs-lookup"><span data-stu-id="1c8aa-193">Select or clear the Mark check box.</span></span>
13. <span data-ttu-id="1c8aa-194">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="1c8aa-194">Click OK.</span></span>
14. <span data-ttu-id="1c8aa-195">Cliquez sur l’onglet Paiement.</span><span class="sxs-lookup"><span data-stu-id="1c8aa-195">Click the Payment tab.</span></span>
    * <span data-ttu-id="1c8aa-196">Vérifier les détails de numéro de document bancaire et de numéro d’expédition</span><span class="sxs-lookup"><span data-stu-id="1c8aa-196">Verify Bank document number and Shipment number details</span></span>  
15. <span data-ttu-id="1c8aa-197">Cliquez sur Valider.</span><span class="sxs-lookup"><span data-stu-id="1c8aa-197">Click Post.</span></span>

## <a name="verify-export-letter-of-credit-after-payment"></a><span data-ttu-id="1c8aa-198">Vérifier la lettre de crédit d’exportation après paiement</span><span class="sxs-lookup"><span data-stu-id="1c8aa-198">Verify Export letter of credit after payment</span></span>
1. <span data-ttu-id="1c8aa-199">Accédez à Gestion de la trésorerie et de la banque > Lettres de crédit > Lettre de crédit d’exportation/relance d’importation.</span><span class="sxs-lookup"><span data-stu-id="1c8aa-199">Go to Cash and bank management > Letters of credit > Export letter of credit and import collection.</span></span>
2. <span data-ttu-id="1c8aa-200">Dans la liste, recherchez et sélectionnez l’enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="1c8aa-200">In the list, find and select the desired record.</span></span>
3. <span data-ttu-id="1c8aa-201">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="1c8aa-201">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="1c8aa-202">Vérifiez que Statut de l’expédition = Paiement reçu et que le montant du solde = 0,00.</span><span class="sxs-lookup"><span data-stu-id="1c8aa-202">Verify Shipment status = Payment received and balance amount = 0.00.</span></span>  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]