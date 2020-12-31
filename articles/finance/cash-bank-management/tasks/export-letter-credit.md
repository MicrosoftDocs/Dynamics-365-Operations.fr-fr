---
title: Lettre de crédit d’exportation
description: Cette procédure décrit le processus associé à une lettre de crédit d’exportation.
author: kweekley
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CustTable, CustBankAccounts, DefaultDashboard, SalesTableListPage, SalesCreateOrder, SalesTable, BankLCExport, SalesEditLines,  LedgerJournalTable, LedgerJournalTransCustPaym, CustOpenTrans
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 3cd18320ca8505b1357ce505dfb4c94e81aaae91
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4443133"
---
# <a name="export-letter-of-credit"></a><span data-ttu-id="2ee9f-103">Lettre de crédit d’exportation</span><span class="sxs-lookup"><span data-stu-id="2ee9f-103">Export letter of credit</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="2ee9f-104">Cette procédure décrit le processus associé à une lettre de crédit d’exportation.</span><span class="sxs-lookup"><span data-stu-id="2ee9f-104">This procedure walks through the process of the Export letter of credit.</span></span>

<span data-ttu-id="2ee9f-105">Une lettre de crédit est un accord émis par une banque, dans lequel la banque accepte de garantir le paiement au nom de l’acheteur, si les conditions de l’accord entre l’acheteur et le vendeur sont satisfaites.</span><span class="sxs-lookup"><span data-stu-id="2ee9f-105">A letter of credit is an agreement that is issued by a bank, in which the bank agrees to ensure payment on behalf of the buyer, if the terms of the agreement between the buyer and seller are met.</span></span>



<span data-ttu-id="2ee9f-106">Préalablement à cette procédure, exécutez la procédure « Paramétrage des établissements bancaires et profils de validation » et la procédure « Lettre de crédit_Création d’un accord d’établissement bancaire ».</span><span class="sxs-lookup"><span data-stu-id="2ee9f-106">Run the 'Set up bank facilities and posting profiles' procedure and the 'Letter of Credit_Create a bank facility agreement' procedure prior to this procedure.</span></span> <span data-ttu-id="2ee9f-107">Pour exécuter cette procédure correctement, vous devez sélectionner la société fictive USMF.</span><span class="sxs-lookup"><span data-stu-id="2ee9f-107">The USMF demo company must be selected in order to run this procedure successfully.</span></span>




## <a name="create-sales-order-for-export-letter-of-credit"></a><span data-ttu-id="2ee9f-108">Créer une commande client pour une lettre de crédit d’exportation</span><span class="sxs-lookup"><span data-stu-id="2ee9f-108">Create Sales Order for Export letter of credit</span></span>
1. <span data-ttu-id="2ee9f-109">Accédez à Comptabilité client > Commandes > Toutes les commandes client.</span><span class="sxs-lookup"><span data-stu-id="2ee9f-109">Go to Accounts receivable > Orders > All sales orders.</span></span>
2. <span data-ttu-id="2ee9f-110">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="2ee9f-110">Click New.</span></span>
3. <span data-ttu-id="2ee9f-111">Dans le champ Compte client, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="2ee9f-111">In the Customer account field, click the drop-down button to open the lookup.</span></span>
4. <span data-ttu-id="2ee9f-112">Dans la liste, recherchez et sélectionnez l’enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="2ee9f-112">In the list, find and select the desired record.</span></span>
5. <span data-ttu-id="2ee9f-113">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="2ee9f-113">In the list, click the link in the selected row.</span></span>
6. <span data-ttu-id="2ee9f-114">Développez ou réduisez la section Général.</span><span class="sxs-lookup"><span data-stu-id="2ee9f-114">Expand or collapse the General section.</span></span>
7. <span data-ttu-id="2ee9f-115">Dans le champ Site, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="2ee9f-115">In the Site field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="2ee9f-116">Sélectionner le site où l’article qui doit sortir est stocké.</span><span class="sxs-lookup"><span data-stu-id="2ee9f-116">Select the Site where the item to be issued is stocked.</span></span>  
8. <span data-ttu-id="2ee9f-117">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="2ee9f-117">In the list, click the link in the selected row.</span></span>
9. <span data-ttu-id="2ee9f-118">Dans le champ Entrepôt, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="2ee9f-118">In the Warehouse field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="2ee9f-119">Sélectionner l’entrepôt où l’article qui doit sortir est stocké.</span><span class="sxs-lookup"><span data-stu-id="2ee9f-119">Select the Warehouse where item to be issued is stocked.</span></span>  
10. <span data-ttu-id="2ee9f-120">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="2ee9f-120">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="2ee9f-121">Remarque : le champ « Type de document bancaire » doit être sélectionné et renseigné avec la valeur « Lettre de crédit ».</span><span class="sxs-lookup"><span data-stu-id="2ee9f-121">Note: The Bank document type field should be selected with the value 'Letter of credit'.</span></span>  
11. <span data-ttu-id="2ee9f-122">Dans le champ Type de document bancaire, sélectionnez « Lettre de crédit ».</span><span class="sxs-lookup"><span data-stu-id="2ee9f-122">In the Bank document type field, select 'Letter of credit'.</span></span>
12. <span data-ttu-id="2ee9f-123">Développez ou réduisez la section Livraison.</span><span class="sxs-lookup"><span data-stu-id="2ee9f-123">Expand or collapse the Delivery section.</span></span>
    * <span data-ttu-id="2ee9f-124">Sélectionnez Vérification de la date de livraison = Aucun(e).</span><span class="sxs-lookup"><span data-stu-id="2ee9f-124">Select Delivery date control = None.</span></span>  
13. <span data-ttu-id="2ee9f-125">Dans le champ Date de réception demandée, entrez une date.</span><span class="sxs-lookup"><span data-stu-id="2ee9f-125">In the Requested receipt date field, enter a date.</span></span>
14. <span data-ttu-id="2ee9f-126">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="2ee9f-126">Click OK.</span></span>
15. <span data-ttu-id="2ee9f-127">Dans le champ Numéro d’article, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="2ee9f-127">In the Item number field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="2ee9f-128">Sélectionnez l’article requis qui doit sortir/être vendu.</span><span class="sxs-lookup"><span data-stu-id="2ee9f-128">Select the required item to be Issued/Sold.</span></span>  
16. <span data-ttu-id="2ee9f-129">Dans la liste, recherchez et sélectionnez l’enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="2ee9f-129">In the list, find and select the desired record.</span></span>
17. <span data-ttu-id="2ee9f-130">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="2ee9f-130">In the list, click the link in the selected row.</span></span>
18. <span data-ttu-id="2ee9f-131">Entrez un nombre dans le champ Prix unitaire.</span><span class="sxs-lookup"><span data-stu-id="2ee9f-131">In the Unit price field, enter a number.</span></span>
19. <span data-ttu-id="2ee9f-132">Développez ou réduisez la section Détails de ligne.</span><span class="sxs-lookup"><span data-stu-id="2ee9f-132">Expand or collapse the Line details section.</span></span>
20. <span data-ttu-id="2ee9f-133">Cliquez sur l’onglet Livraison.</span><span class="sxs-lookup"><span data-stu-id="2ee9f-133">Click the Delivery tab.</span></span>
21. <span data-ttu-id="2ee9f-134">Dans le champ Date d’expédition demandée, entrez une date.</span><span class="sxs-lookup"><span data-stu-id="2ee9f-134">In the Requested ship date field, enter a date.</span></span>
22. <span data-ttu-id="2ee9f-135">Dans le champ Date d’expédition confirmée, entrez une date.</span><span class="sxs-lookup"><span data-stu-id="2ee9f-135">In the Confirmed ship date field, enter a date.</span></span>
23. <span data-ttu-id="2ee9f-136">Dans le volet Actions, cliquez sur Gérer.</span><span class="sxs-lookup"><span data-stu-id="2ee9f-136">On the Action Pane, click Manage.</span></span>
24. <span data-ttu-id="2ee9f-137">Cliquez sur Lettre de crédit.</span><span class="sxs-lookup"><span data-stu-id="2ee9f-137">Click Letter of credit.</span></span>
25. <span data-ttu-id="2ee9f-138">Dans le champ Numéro de document bancaire, tapez une valeur.</span><span class="sxs-lookup"><span data-stu-id="2ee9f-138">In the Bank document number field, type a value.</span></span>
26. <span data-ttu-id="2ee9f-139">Entrez une date et une heure dans le champ Date d’expiration.</span><span class="sxs-lookup"><span data-stu-id="2ee9f-139">In the Expiration date field, enter a date and time.</span></span>
27. <span data-ttu-id="2ee9f-140">Développez ou réduisez la section Détails bancaires.</span><span class="sxs-lookup"><span data-stu-id="2ee9f-140">Expand or collapse the Bank details section.</span></span>
28. <span data-ttu-id="2ee9f-141">Dans le champ Banque émettrice, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="2ee9f-141">In the Issuing bank field, click the drop-down button to open the lookup.</span></span>
29. <span data-ttu-id="2ee9f-142">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="2ee9f-142">In the list, click the link in the selected row.</span></span>
30. <span data-ttu-id="2ee9f-143">Dans le champ Banque conseillère, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="2ee9f-143">In the Advising bank field, click the drop-down button to open the lookup.</span></span>
31. <span data-ttu-id="2ee9f-144">Dans la liste, recherchez et sélectionnez l’enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="2ee9f-144">In the list, find and select the desired record.</span></span>
32. <span data-ttu-id="2ee9f-145">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="2ee9f-145">In the list, click the link in the selected row.</span></span>
33. <span data-ttu-id="2ee9f-146">Cliquez sur Extraire les expéditions de la commande client.</span><span class="sxs-lookup"><span data-stu-id="2ee9f-146">Click Fetch sales order shipments.</span></span>
34. <span data-ttu-id="2ee9f-147">Cliquez sur Émettre le document bancaire.</span><span class="sxs-lookup"><span data-stu-id="2ee9f-147">Click Issue bank document.</span></span>
35. <span data-ttu-id="2ee9f-148">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="2ee9f-148">Close the page.</span></span>

## <a name="post-packing-slip"></a><span data-ttu-id="2ee9f-149">Valider un bon de livraison</span><span class="sxs-lookup"><span data-stu-id="2ee9f-149">Post Packing slip</span></span>
1. <span data-ttu-id="2ee9f-150">Cliquez sur Prélever et emballer dans le volet Actions.</span><span class="sxs-lookup"><span data-stu-id="2ee9f-150">On the Action Pane, click Pick and pack.</span></span>
2. <span data-ttu-id="2ee9f-151">Cliquez sur Validation du bon de livraison.</span><span class="sxs-lookup"><span data-stu-id="2ee9f-151">Click Post packing slip.</span></span>
3. <span data-ttu-id="2ee9f-152">Développez ou réduisez la section Paramètres.</span><span class="sxs-lookup"><span data-stu-id="2ee9f-152">Expand or collapse the Parameters section.</span></span>
4. <span data-ttu-id="2ee9f-153">Sélectionnez Tout dans le champ Quantité.</span><span class="sxs-lookup"><span data-stu-id="2ee9f-153">In the Quantity field, select 'All'.</span></span>
5. <span data-ttu-id="2ee9f-154">Développez ou réduisez la section Paramétrage.</span><span class="sxs-lookup"><span data-stu-id="2ee9f-154">Expand or collapse the Setup section.</span></span>
6. <span data-ttu-id="2ee9f-155">Dans le champ Date de bon de livraison, entrez une date.</span><span class="sxs-lookup"><span data-stu-id="2ee9f-155">In the Packing slip date field, enter a date.</span></span>
7. <span data-ttu-id="2ee9f-156">Sélectionnez le numéro d’expédition.</span><span class="sxs-lookup"><span data-stu-id="2ee9f-156">Select the Shipment number.</span></span>
8. <span data-ttu-id="2ee9f-157">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="2ee9f-157">In the list, click the link in the selected row.</span></span>
9. <span data-ttu-id="2ee9f-158">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="2ee9f-158">Click OK.</span></span>
10. <span data-ttu-id="2ee9f-159">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="2ee9f-159">Click OK.</span></span>

## <a name="post-sales-invoice"></a><span data-ttu-id="2ee9f-160">Valider une facture client</span><span class="sxs-lookup"><span data-stu-id="2ee9f-160">Post sales invoice</span></span>
1. <span data-ttu-id="2ee9f-161">Dans le volet Actions, cliquez sur Facture.</span><span class="sxs-lookup"><span data-stu-id="2ee9f-161">On the Action Pane, click Invoice.</span></span>
2. <span data-ttu-id="2ee9f-162">Cliquez sur Facture.</span><span class="sxs-lookup"><span data-stu-id="2ee9f-162">Click Invoice.</span></span>
3. <span data-ttu-id="2ee9f-163">Développez ou réduisez la section Vue d’ensemble.</span><span class="sxs-lookup"><span data-stu-id="2ee9f-163">Expand or collapse the Overview section.</span></span>
4. <span data-ttu-id="2ee9f-164">Sélectionnez le numéro d’expédition.</span><span class="sxs-lookup"><span data-stu-id="2ee9f-164">Select the Shipment number.</span></span>
5. <span data-ttu-id="2ee9f-165">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="2ee9f-165">In the list, click the link in the selected row.</span></span>
6. <span data-ttu-id="2ee9f-166">Développez ou réduisez la section Paramétrage.</span><span class="sxs-lookup"><span data-stu-id="2ee9f-166">Expand or collapse the Setup section.</span></span>
7. <span data-ttu-id="2ee9f-167">Entrez une date dans le champ Date de facture.</span><span class="sxs-lookup"><span data-stu-id="2ee9f-167">In the Invoice date field, enter a date.</span></span>
8. <span data-ttu-id="2ee9f-168">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="2ee9f-168">Click OK.</span></span>
9. <span data-ttu-id="2ee9f-169">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="2ee9f-169">Click OK.</span></span>

## <a name="shipment-document-submitted-status"></a><span data-ttu-id="2ee9f-170">Statut du document d’expédition soumis</span><span class="sxs-lookup"><span data-stu-id="2ee9f-170">Shipment document submitted status</span></span>
1. <span data-ttu-id="2ee9f-171">Dans le volet Actions, cliquez sur Gérer.</span><span class="sxs-lookup"><span data-stu-id="2ee9f-171">On the Action Pane, click Manage.</span></span>
2. <span data-ttu-id="2ee9f-172">Cliquez sur Lettre de crédit.</span><span class="sxs-lookup"><span data-stu-id="2ee9f-172">Click Letter of credit.</span></span>
3. <span data-ttu-id="2ee9f-173">Développez ou réduisez la section Lignes.</span><span class="sxs-lookup"><span data-stu-id="2ee9f-173">Expand or collapse the Lines section.</span></span>
    * <span data-ttu-id="2ee9f-174">Remarque : le champ « Document soumis » doit être défini à « Oui ».</span><span class="sxs-lookup"><span data-stu-id="2ee9f-174">Note: The 'Document submitted' field should be set to 'Yes'.</span></span>  

## <a name="verify-export-letter-of-credit"></a><span data-ttu-id="2ee9f-175">Vérifier la lettre de crédit d’exportation</span><span class="sxs-lookup"><span data-stu-id="2ee9f-175">Verify Export letter of credit</span></span>
1. <span data-ttu-id="2ee9f-176">Accédez à Gestion de la trésorerie et de la banque > Lettres de crédit > Lettre de crédit d’exportation/relance d’importation.</span><span class="sxs-lookup"><span data-stu-id="2ee9f-176">Go to Cash and bank management > Letters of credit > Export letter of credit and import collection.</span></span>
2. <span data-ttu-id="2ee9f-177">Dans la liste, recherchez et sélectionnez l’enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="2ee9f-177">In the list, find and select the desired record.</span></span>
3. <span data-ttu-id="2ee9f-178">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="2ee9f-178">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="2ee9f-179">Vérifiez que la lettre de crédit d’exportation est dotée du statut d’expédition « Facturée ».</span><span class="sxs-lookup"><span data-stu-id="2ee9f-179">Verify that the Export letter of credit has a Shipment status of 'Invoiced'.</span></span>  

## <a name="customer-payment"></a><span data-ttu-id="2ee9f-180">Client - Paiements</span><span class="sxs-lookup"><span data-stu-id="2ee9f-180">Customer payment</span></span>
1. <span data-ttu-id="2ee9f-181">Accédez à Comptabilité client > Paiements > Journal des paiements.</span><span class="sxs-lookup"><span data-stu-id="2ee9f-181">Go to Accounts receivable > Payments > Payment journal.</span></span>
2. <span data-ttu-id="2ee9f-182">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="2ee9f-182">Click New.</span></span>
3. <span data-ttu-id="2ee9f-183">Dans la liste, marquez la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="2ee9f-183">In the list, mark the selected row.</span></span>
4. <span data-ttu-id="2ee9f-184">Dans le champ Nom, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="2ee9f-184">In the Name field, click the drop-down button to open the lookup.</span></span>
5. <span data-ttu-id="2ee9f-185">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="2ee9f-185">In the list, click the link in the selected row.</span></span>
6. <span data-ttu-id="2ee9f-186">Cliquez sur Lignes.</span><span class="sxs-lookup"><span data-stu-id="2ee9f-186">Click Lines.</span></span>
7. <span data-ttu-id="2ee9f-187">Entrez une date dans le champ Date.</span><span class="sxs-lookup"><span data-stu-id="2ee9f-187">In the Date field, enter a date.</span></span>
8. <span data-ttu-id="2ee9f-188">Dans le champ Compte, spécifiez les valeurs souhaitées.</span><span class="sxs-lookup"><span data-stu-id="2ee9f-188">In the Account field, specify the desired values.</span></span>
9. <span data-ttu-id="2ee9f-189">Cliquez sur Règlement.</span><span class="sxs-lookup"><span data-stu-id="2ee9f-189">Click Settlement.</span></span>
10. <span data-ttu-id="2ee9f-190">Cochez la case dans l’en-tête de Totaux.</span><span class="sxs-lookup"><span data-stu-id="2ee9f-190">Select the check box on the header of Totals.</span></span>
    * <span data-ttu-id="2ee9f-191">Remarque : définissez le champ Afficher à « Lettre de crédit ».</span><span class="sxs-lookup"><span data-stu-id="2ee9f-191">Note: Set the Show field to 'Letter of credit'.</span></span>  
11. <span data-ttu-id="2ee9f-192">Dans la liste, recherchez et sélectionnez l’enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="2ee9f-192">In the list, find and select the desired record.</span></span>
12. <span data-ttu-id="2ee9f-193">Activez ou désactivez la case à cocher Marquer.</span><span class="sxs-lookup"><span data-stu-id="2ee9f-193">Select or clear the Mark check box.</span></span>
13. <span data-ttu-id="2ee9f-194">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="2ee9f-194">Click OK.</span></span>
14. <span data-ttu-id="2ee9f-195">Cliquez sur l’onglet Paiement.</span><span class="sxs-lookup"><span data-stu-id="2ee9f-195">Click the Payment tab.</span></span>
    * <span data-ttu-id="2ee9f-196">Vérifier les détails de numéro de document bancaire et de numéro d’expédition</span><span class="sxs-lookup"><span data-stu-id="2ee9f-196">Verify Bank document number and Shipment number details</span></span>  
15. <span data-ttu-id="2ee9f-197">Cliquez sur Valider.</span><span class="sxs-lookup"><span data-stu-id="2ee9f-197">Click Post.</span></span>

## <a name="verify-export-letter-of-credit-after-payment"></a><span data-ttu-id="2ee9f-198">Vérifier la lettre de crédit d’exportation après paiement</span><span class="sxs-lookup"><span data-stu-id="2ee9f-198">Verify Export letter of credit after payment</span></span>
1. <span data-ttu-id="2ee9f-199">Accédez à Gestion de la trésorerie et de la banque > Lettres de crédit > Lettre de crédit d’exportation/relance d’importation.</span><span class="sxs-lookup"><span data-stu-id="2ee9f-199">Go to Cash and bank management > Letters of credit > Export letter of credit and import collection.</span></span>
2. <span data-ttu-id="2ee9f-200">Dans la liste, recherchez et sélectionnez l’enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="2ee9f-200">In the list, find and select the desired record.</span></span>
3. <span data-ttu-id="2ee9f-201">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="2ee9f-201">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="2ee9f-202">Vérifiez que Statut de l’expédition = Paiement reçu et que le montant du solde = 0,00.</span><span class="sxs-lookup"><span data-stu-id="2ee9f-202">Verify Shipment status = Payment received and balance amount = 0.00.</span></span>  

