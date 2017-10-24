--- 
title: "Définir le mappage de modèles et sélectionner des sources de données pour la gestion des états électroniques (ER)"
description: "Les étapes suivantes expliquent comment un utilisateur doté du rôle Administrateur système ou Développeur d'états électroniques peut sélectionner des sources de données pour un modèle de données de génération d'états électroniques (ER)."
author: NickSelin
manager: AnnBe
ms.date: 01/16/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: kfend
ms.search.scope: Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 512e24b5d0e20f00890e2a9abfe45b660a913913
ms.contentlocale: fr-fr
ms.lasthandoff: 09/29/2017

---
# <a name="define-model-mapping-and-select-data-sources-for-electronic-reporting-er"></a><span data-ttu-id="51f16-103">Définir le mappage de modèles et sélectionner des sources de données pour la gestion des états électroniques (ER)</span><span class="sxs-lookup"><span data-stu-id="51f16-103">Define model mapping and select data sources for electronic reporting (ER)</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="51f16-104">Les étapes suivantes expliquent comment un utilisateur doté du rôle Administrateur système ou Développeur d'états électroniques peut sélectionner des sources de données pour un modèle de données de génération d'états électroniques (ER).</span><span class="sxs-lookup"><span data-stu-id="51f16-104">The following steps explain how a user in the System Administrator or Electronic Reporting Developer role can select data sources for an Electronic reporting (ER) data model.</span></span> <span data-ttu-id="51f16-105">Les sources de données seront liées aux composants du modèle de données sélectionné au moment de la création et des données commerciales seront renseignées dans ce modèle de données au moment de l'exécution.</span><span class="sxs-lookup"><span data-stu-id="51f16-105">The data sources will be bound to individual components of the selected data model at design time and populate business data to that data model at run-time.</span></span> <span data-ttu-id="51f16-106">Dans cet exemple, vous allez sélectionner des sources de données pour un modèle de données existant qui a été créé pour la société témoin, Litware, Inc. Pour effectuer ces étapes, vous devez d'abord accomplir celles de la procédure « Créer un modèle de données ».</span><span class="sxs-lookup"><span data-stu-id="51f16-106">In this example, you will select data sources for an existing data model that has been created for sample company, Litware, Inc. To complete these steps, you must first complete the steps in the “Create a new data model” procedure.</span></span>


## <a name="open-the-electronic-reporting-configurations-tree"></a><span data-ttu-id="51f16-107">Ouvrir l'arborescence des configurations d'états électroniques</span><span class="sxs-lookup"><span data-stu-id="51f16-107">Open the Electronic Reporting configurations tree</span></span>
1. <span data-ttu-id="51f16-108">Accédez à Administration d'organisation > Espaces de travail > États électroniques.</span><span class="sxs-lookup"><span data-stu-id="51f16-108">Go to Organization administration > Workspaces > Electronic reporting.</span></span>
2. <span data-ttu-id="51f16-109">Cliquez sur Configurations des états.</span><span class="sxs-lookup"><span data-stu-id="51f16-109">Click Reporting configurations.</span></span>

## <a name="insert-a-new-model-mapping"></a><span data-ttu-id="51f16-110">Insérer une nouvelle mise en correspondance de modèle</span><span class="sxs-lookup"><span data-stu-id="51f16-110">Insert a new model mapping</span></span>
1. <span data-ttu-id="51f16-111">Dans l'arborescence, sélectionnez « Paiements (modèle simplifié) ».</span><span class="sxs-lookup"><span data-stu-id="51f16-111">In the tree, select 'Payments (simplified model)'.</span></span>
2. <span data-ttu-id="51f16-112">Cliquez sur Concepteur.</span><span class="sxs-lookup"><span data-stu-id="51f16-112">Click Designer.</span></span>
3. <span data-ttu-id="51f16-113">Cliquez sur Mettre en correspondance le modèle à la source de données.</span><span class="sxs-lookup"><span data-stu-id="51f16-113">Click Map model to datasource.</span></span>
4. <span data-ttu-id="51f16-114">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="51f16-114">Click New.</span></span>
    * <span data-ttu-id="51f16-115">Cette opération crée un enregistrement qui mappera le modèle de données aux sources de données.</span><span class="sxs-lookup"><span data-stu-id="51f16-115">This will create a new record that will map the data model to data sources.</span></span> <span data-ttu-id="51f16-116">Dans cet exemple, vous mapperez le modèle de données aux sources de données pour le type désiré de paiement : virement.</span><span class="sxs-lookup"><span data-stu-id="51f16-116">In this example, you will map the data model to data sources for the desired payment type: credit transfer.</span></span>     <span data-ttu-id="51f16-117">Il est possible de concevoir plusieurs mises en correspondance pour un modèle de données spécifique.</span><span class="sxs-lookup"><span data-stu-id="51f16-117">It is possible to design more than one mapping for a particular data model.</span></span> <span data-ttu-id="51f16-118">Par exemple, vous pouvez créer une mise en correspondance pour les différents types de paiements, comme le débit direct ou les virements bancaires.</span><span class="sxs-lookup"><span data-stu-id="51f16-118">For example, you could create a mapping for the different types of payments, such as for direct debit or for credit transfers.</span></span> <span data-ttu-id="51f16-119">Dans cet exemple, vous créerez une mise en correspondance pour les virements.</span><span class="sxs-lookup"><span data-stu-id="51f16-119">In this example, you will create a mapping for credit transfers.</span></span>  
5. <span data-ttu-id="51f16-120">Dans le champ Nom, tapez « Mise en correspondance VMT ».</span><span class="sxs-lookup"><span data-stu-id="51f16-120">In the Name field, type 'CT mapping'.</span></span>
    * <span data-ttu-id="51f16-121">Mise en correspondance VMT</span><span class="sxs-lookup"><span data-stu-id="51f16-121">CT mapping</span></span>  
6. <span data-ttu-id="51f16-122">Dans le champ Description, entrez « Mise en correspondance de modèle de paiement VMT ».</span><span class="sxs-lookup"><span data-stu-id="51f16-122">In the Description field, type 'Payment model mapping CT'.</span></span>
    * <span data-ttu-id="51f16-123">Mise en correspondance de modèle de paiement VMT</span><span class="sxs-lookup"><span data-stu-id="51f16-123">Payment model mapping CT</span></span>  
7. <span data-ttu-id="51f16-124">Dans le champ Définition, tapez « CustomerCreditTransferInitiation ».</span><span class="sxs-lookup"><span data-stu-id="51f16-124">In the Definition field, type 'CustomerCreditTransferInitiation'.</span></span>
    * <span data-ttu-id="51f16-125">CustomerCreditTransferInitiation</span><span class="sxs-lookup"><span data-stu-id="51f16-125">CustomerCreditTransferInitiation</span></span>  
8. <span data-ttu-id="51f16-126">Résolvez les modifications de la définition.</span><span class="sxs-lookup"><span data-stu-id="51f16-126">ResolveChanges the Definition.</span></span>
9. <span data-ttu-id="51f16-127">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="51f16-127">Click Save.</span></span>

## <a name="define-required-data-sources-for-the-current-model-mapping"></a><span data-ttu-id="51f16-128">Définir des sources de données pour la mise en correspondance de modèle existante</span><span class="sxs-lookup"><span data-stu-id="51f16-128">Define required data sources for the current model mapping</span></span>
1. <span data-ttu-id="51f16-129">Cliquez sur Concepteur.</span><span class="sxs-lookup"><span data-stu-id="51f16-129">Click Designer.</span></span>
2. <span data-ttu-id="51f16-130">Dans l'arborescence, sélectionnez « Dynamics 365 for Operations\Enregistrements de tables ».</span><span class="sxs-lookup"><span data-stu-id="51f16-130">In the tree, select 'Dynamics 365 for Operations\Table records'.</span></span>
3. <span data-ttu-id="51f16-131">Cliquez sur Ajouter racine.</span><span class="sxs-lookup"><span data-stu-id="51f16-131">Click Add root.</span></span>
    * <span data-ttu-id="51f16-132">Entrez cette source de données pour accéder à des transactions de paiement.</span><span class="sxs-lookup"><span data-stu-id="51f16-132">Enter this data source to access payment transactions.</span></span>  
4. <span data-ttu-id="51f16-133">Dans le champ Nom, tapez « Transactions ».</span><span class="sxs-lookup"><span data-stu-id="51f16-133">In the Name field, type 'Transactions'.</span></span>
    * <span data-ttu-id="51f16-134">Transactions</span><span class="sxs-lookup"><span data-stu-id="51f16-134">Transactions</span></span>  
5. <span data-ttu-id="51f16-135">Dans le champ Étiquette, tapez « Transactions ».</span><span class="sxs-lookup"><span data-stu-id="51f16-135">In the Label field, enter 'Transactions'.</span></span>
    * <span data-ttu-id="51f16-136">Transactions</span><span class="sxs-lookup"><span data-stu-id="51f16-136">Transactions</span></span>  
6. <span data-ttu-id="51f16-137">Dans le champ Aide, entrez « Lignes de journal comptable ».</span><span class="sxs-lookup"><span data-stu-id="51f16-137">In the Help field, enter 'Ledger journal lines'.</span></span>
    * <span data-ttu-id="51f16-138">Lignes de journal comptable</span><span class="sxs-lookup"><span data-stu-id="51f16-138">Ledger journal lines</span></span>  
7. <span data-ttu-id="51f16-139">Sélectionnez Oui dans le champ Demander une requête.</span><span class="sxs-lookup"><span data-stu-id="51f16-139">Select Yes in the Ask for query field.</span></span>
    * <span data-ttu-id="51f16-140">Sélectionnez Oui.</span><span class="sxs-lookup"><span data-stu-id="51f16-140">Select Yes.</span></span>  
8. <span data-ttu-id="51f16-141">Dans le champ Table, tapez « LedgerJournalTrans ».</span><span class="sxs-lookup"><span data-stu-id="51f16-141">In the Table field, type 'LedgerJournalTrans'.</span></span>
    * <span data-ttu-id="51f16-142">LedgerJournalTrans</span><span class="sxs-lookup"><span data-stu-id="51f16-142">LedgerJournalTrans</span></span>  
9. <span data-ttu-id="51f16-143">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="51f16-143">Click OK.</span></span>
    * <span data-ttu-id="51f16-144">Sélectionnez la table LedgerJournalTrans comme source de données pour le modèle de données actuel.</span><span class="sxs-lookup"><span data-stu-id="51f16-144">Select the LedgerJournalTrans table as a data source for the current data model.</span></span>  
10. <span data-ttu-id="51f16-145">Dans l'arborescence, sélectionnez « Fonctions\Champ calculé ».</span><span class="sxs-lookup"><span data-stu-id="51f16-145">In the tree, select 'Functions\Calculated field'.</span></span>
11. <span data-ttu-id="51f16-146">Cliquez sur Ajouter.</span><span class="sxs-lookup"><span data-stu-id="51f16-146">Click Add.</span></span>
    * <span data-ttu-id="51f16-147">Cliquez sur Ajouter pour ajouter un champ calculé.</span><span class="sxs-lookup"><span data-stu-id="51f16-147">Click Add to add a new calculated field.</span></span>  
12. <span data-ttu-id="51f16-148">Dans le champ Nom, tapez « $EndToEndID ».</span><span class="sxs-lookup"><span data-stu-id="51f16-148">In the Name field, type '$EndToEndID'.</span></span>
    * <span data-ttu-id="51f16-149">$EndToEndID</span><span class="sxs-lookup"><span data-stu-id="51f16-149">$EndToEndID</span></span>  
13. <span data-ttu-id="51f16-150">Cliquez sur Modifier la formule.</span><span class="sxs-lookup"><span data-stu-id="51f16-150">Click Edit formula.</span></span>
14. <span data-ttu-id="51f16-151">Dans l'arborescence, sélectionner « String\CONCATENATE ».</span><span class="sxs-lookup"><span data-stu-id="51f16-151">In the tree, select 'String\CONCATENATE'.</span></span>
15. <span data-ttu-id="51f16-152">Cliquez sur Ajouter une fonction.</span><span class="sxs-lookup"><span data-stu-id="51f16-152">Click Add function.</span></span>
16. <span data-ttu-id="51f16-153">Dans l'arborescence , développer « Transactions ».</span><span class="sxs-lookup"><span data-stu-id="51f16-153">In the tree, expand 'Transactions'.</span></span>
17. <span data-ttu-id="51f16-154">Dans l'arborescence, sélectionnez « Transactions\Document ».</span><span class="sxs-lookup"><span data-stu-id="51f16-154">In the tree, select 'Transactions\Voucher'.</span></span>
18. <span data-ttu-id="51f16-155">Cliquez sur Ajouter une source de données.</span><span class="sxs-lookup"><span data-stu-id="51f16-155">Click Add data source.</span></span>
19. <span data-ttu-id="51f16-156">Dans le champ Formule, entrez « CONCATENATE(Transactions.Voucher, "-",  ».</span><span class="sxs-lookup"><span data-stu-id="51f16-156">In the Formula field, enter 'CONCATENATE(Transactions.Voucher, "-", '.</span></span>
    * <span data-ttu-id="51f16-157">Tapez [ , “-“, ] à la fin de la formule.</span><span class="sxs-lookup"><span data-stu-id="51f16-157">Type [ , “-“, ] at the end of the formula.</span></span>  
20. <span data-ttu-id="51f16-158">Dans l'arborescence , sélectionnez « Chaîne\TEXTE ».</span><span class="sxs-lookup"><span data-stu-id="51f16-158">In the tree, select 'String\TEXT'.</span></span>
21. <span data-ttu-id="51f16-159">Cliquez sur Ajouter une fonction.</span><span class="sxs-lookup"><span data-stu-id="51f16-159">Click Add function.</span></span>
22. <span data-ttu-id="51f16-160">Dans l'arborescence, sélectionnez « Transactions\ID enregistrement (RecId) ».</span><span class="sxs-lookup"><span data-stu-id="51f16-160">In the tree, select 'Transactions\Record-ID(RecId)'.</span></span>
23. <span data-ttu-id="51f16-161">Cliquez sur Ajouter une source de données.</span><span class="sxs-lookup"><span data-stu-id="51f16-161">Click Add data source.</span></span>
24. <span data-ttu-id="51f16-162">Dans le champ Formule, entrez « CONCATENATE(Transactions.Voucher, "-", TEXT(Transactions.RecId)) ».</span><span class="sxs-lookup"><span data-stu-id="51f16-162">In the Formula field, enter 'CONCATENATE(Transactions.Voucher, "-", TEXT(Transactions.RecId))'.</span></span>
    * <span data-ttu-id="51f16-163">Tapez [))] à la fin de la formule.</span><span class="sxs-lookup"><span data-stu-id="51f16-163">Type [))] at the end of the formula.</span></span>  
25. <span data-ttu-id="51f16-164">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="51f16-164">Click Save.</span></span>
    * <span data-ttu-id="51f16-165">Assurez-vous qu'aucune erreur n'a été découverte dans la formule créée.</span><span class="sxs-lookup"><span data-stu-id="51f16-165">Make sure that no errors have been discovered for the created formula.</span></span> <span data-ttu-id="51f16-166">Voir l'onglet ERREURS en dessous du contrôle d'éditeur de formule.</span><span class="sxs-lookup"><span data-stu-id="51f16-166">See the ERRORS tab below the formula editor control.</span></span>  
26. <span data-ttu-id="51f16-167">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="51f16-167">Close the page.</span></span>
27. <span data-ttu-id="51f16-168">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="51f16-168">Click OK.</span></span>
    * <span data-ttu-id="51f16-169">Ajoutez le champ calculé à cette source de données.</span><span class="sxs-lookup"><span data-stu-id="51f16-169">Add the calculated field to this data source.</span></span>  
28. <span data-ttu-id="51f16-170">Cliquez sur Ajouter.</span><span class="sxs-lookup"><span data-stu-id="51f16-170">Click Add.</span></span>
    * <span data-ttu-id="51f16-171">Cliquez sur Ajouter pour ajouter un champ calculé.</span><span class="sxs-lookup"><span data-stu-id="51f16-171">Click Add to add a new calculated field.</span></span>  
29. <span data-ttu-id="51f16-172">Dans le champ Nom, tapez « $Amount ».</span><span class="sxs-lookup"><span data-stu-id="51f16-172">In the Name field, type '$Amount'.</span></span>
    * <span data-ttu-id="51f16-173">$Montant</span><span class="sxs-lookup"><span data-stu-id="51f16-173">$Amount</span></span>  
30. <span data-ttu-id="51f16-174">Cliquez sur Modifier la formule.</span><span class="sxs-lookup"><span data-stu-id="51f16-174">Click Edit formula.</span></span>
31. <span data-ttu-id="51f16-175">Dans l'arborescence , développer « Transactions ».</span><span class="sxs-lookup"><span data-stu-id="51f16-175">In the tree, expand 'Transactions'.</span></span>
32. <span data-ttu-id="51f16-176">Dans l'arborescence, sélectionnez « Transactions\Debit(AmountCurDebit) ».</span><span class="sxs-lookup"><span data-stu-id="51f16-176">In the tree, select 'Transactions\Debit(AmountCurDebit)'.</span></span>
33. <span data-ttu-id="51f16-177">Cliquez sur Ajouter une source de données.</span><span class="sxs-lookup"><span data-stu-id="51f16-177">Click Add data source.</span></span>
34. <span data-ttu-id="51f16-178">Dans le champ Formule, entrez « Transactions.AmountCurDebit -  ».</span><span class="sxs-lookup"><span data-stu-id="51f16-178">In the Formula field, enter 'Transactions.AmountCurDebit - '.</span></span>
    * <span data-ttu-id="51f16-179">Tapez [ - ] à la fin de la formule.</span><span class="sxs-lookup"><span data-stu-id="51f16-179">Type [ - ] at the end of the formula.</span></span>  
35. <span data-ttu-id="51f16-180">Dans l'arborescence, sélectionnez « Transactions\Credit(AmountCurCredit) ».</span><span class="sxs-lookup"><span data-stu-id="51f16-180">In the tree, select 'Transactions\Credit(AmountCurCredit)'.</span></span>
36. <span data-ttu-id="51f16-181">Cliquez sur Ajouter une source de données.</span><span class="sxs-lookup"><span data-stu-id="51f16-181">Click Add data source.</span></span>
37. <span data-ttu-id="51f16-182">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="51f16-182">Click Save.</span></span>
38. <span data-ttu-id="51f16-183">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="51f16-183">Close the page.</span></span>
39. <span data-ttu-id="51f16-184">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="51f16-184">Click OK.</span></span>
    * <span data-ttu-id="51f16-185">Cela ajoutera le champ calculé de $Amount à la source de données sélectionnée pour le modèle de données actuel.</span><span class="sxs-lookup"><span data-stu-id="51f16-185">This will add the $Amount calculated field to the selected data source for the current data model.</span></span>  
40. <span data-ttu-id="51f16-186">Dans l'arborescence, sélectionnez « Transactions\$Amount ».</span><span class="sxs-lookup"><span data-stu-id="51f16-186">In the tree, select 'Transactions\$Amount'.</span></span>
41. <span data-ttu-id="51f16-187">Dans l'arborescence , développer « Transactions ».</span><span class="sxs-lookup"><span data-stu-id="51f16-187">In the tree, expand 'Transactions'.</span></span>
42. <span data-ttu-id="51f16-188">Dans l'arborescence, développez ou réduisez « Transactions\$Amount ».</span><span class="sxs-lookup"><span data-stu-id="51f16-188">In the tree, expand or collapse 'Transactions\$Amount'.</span></span>
43. <span data-ttu-id="51f16-189">Dans l'arborescence, développez ou réduisez « Transactions ».</span><span class="sxs-lookup"><span data-stu-id="51f16-189">In the tree, expand or collapse 'Transactions'.</span></span>
44. <span data-ttu-id="51f16-190">Dans l'arborescence, sélectionnez « Dynamics 365 for Operations\Enregistrements de tables ».</span><span class="sxs-lookup"><span data-stu-id="51f16-190">In the tree, select 'Dynamics 365 for Operations\Table records'.</span></span>
45. <span data-ttu-id="51f16-191">Cliquez sur Ajouter racine.</span><span class="sxs-lookup"><span data-stu-id="51f16-191">Click Add root.</span></span>
    * <span data-ttu-id="51f16-192">Entrez cette source de données pour accéder aux détails du compte bancaire de la société.</span><span class="sxs-lookup"><span data-stu-id="51f16-192">Enter this data source to access the company’s bank account details.</span></span>  
46. <span data-ttu-id="51f16-193">Dans le champ Nom, tapez « BankAccount ».</span><span class="sxs-lookup"><span data-stu-id="51f16-193">In the Name field, type 'BankAccount'.</span></span>
    * <span data-ttu-id="51f16-194">BankAccount</span><span class="sxs-lookup"><span data-stu-id="51f16-194">BankAccount</span></span>  
47. <span data-ttu-id="51f16-195">Dans le champ Étiquette, tapez « Compte bancaire ».</span><span class="sxs-lookup"><span data-stu-id="51f16-195">In the Label field, enter 'Bank Account'.</span></span>
    * <span data-ttu-id="51f16-196">Compte bancaire</span><span class="sxs-lookup"><span data-stu-id="51f16-196">Bank Account</span></span>  
48. <span data-ttu-id="51f16-197">Dans le champ Aide, tapez « Compte bancaire ».</span><span class="sxs-lookup"><span data-stu-id="51f16-197">In the Help field, enter 'Bank Account'.</span></span>
    * <span data-ttu-id="51f16-198">Compte bancaire</span><span class="sxs-lookup"><span data-stu-id="51f16-198">Bank Account</span></span>  
49. <span data-ttu-id="51f16-199">Sélectionnez Oui dans le champ Demander une requête.</span><span class="sxs-lookup"><span data-stu-id="51f16-199">Select Yes in the Ask for query field.</span></span>
    * <span data-ttu-id="51f16-200">Sélectionnez Oui.</span><span class="sxs-lookup"><span data-stu-id="51f16-200">Select Yes.</span></span>  
50. <span data-ttu-id="51f16-201">Dans le champ Table, tapez « BankAccountTable ».</span><span class="sxs-lookup"><span data-stu-id="51f16-201">In the Table field, type 'BankAccountTable'.</span></span>
    * <span data-ttu-id="51f16-202">BankAccountTable</span><span class="sxs-lookup"><span data-stu-id="51f16-202">BankAccountTable</span></span>  
51. <span data-ttu-id="51f16-203">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="51f16-203">Click OK.</span></span>
    * <span data-ttu-id="51f16-204">Sélectionnez la table BankAccountTable comme source de données pour le modèle de données actuel.</span><span class="sxs-lookup"><span data-stu-id="51f16-204">Select the BankAccountTable table as a data source for the current data model.</span></span>  
52. <span data-ttu-id="51f16-205">Cliquez sur Ajouter racine.</span><span class="sxs-lookup"><span data-stu-id="51f16-205">Click Add root.</span></span>
    * <span data-ttu-id="51f16-206">Entrez cette source de données pour accéder aux conditions de la société.</span><span class="sxs-lookup"><span data-stu-id="51f16-206">Enter this data source to access the company’s requisites.</span></span>  
53. <span data-ttu-id="51f16-207">Dans le champ Nom, tapez « Société ».</span><span class="sxs-lookup"><span data-stu-id="51f16-207">In the Name field, type 'Company'.</span></span>
    * <span data-ttu-id="51f16-208">Société</span><span class="sxs-lookup"><span data-stu-id="51f16-208">Company</span></span>  
54. <span data-ttu-id="51f16-209">Dans le champ Étiquette, tapez une valeur.</span><span class="sxs-lookup"><span data-stu-id="51f16-209">In the Label field, type a value.</span></span>
    * <span data-ttu-id="51f16-210">Informations sur la société</span><span class="sxs-lookup"><span data-stu-id="51f16-210">Company information</span></span>  
55. <span data-ttu-id="51f16-211">Dans le champ Aide, entrez « Informations sur la société ».</span><span class="sxs-lookup"><span data-stu-id="51f16-211">In the Help field, enter 'Company information'.</span></span>
    * <span data-ttu-id="51f16-212">Informations sur la société</span><span class="sxs-lookup"><span data-stu-id="51f16-212">Company information</span></span>  
56. <span data-ttu-id="51f16-213">Sélectionnez Oui dans le champ Demander une requête.</span><span class="sxs-lookup"><span data-stu-id="51f16-213">Select Yes in the Ask for query field.</span></span>
    * <span data-ttu-id="51f16-214">Sélectionnez Oui.</span><span class="sxs-lookup"><span data-stu-id="51f16-214">Select Yes.</span></span>  
57. <span data-ttu-id="51f16-215">Dans le champ Table, tapez « CompanyInfo ».</span><span class="sxs-lookup"><span data-stu-id="51f16-215">In the Table field, type 'CompanyInfo'.</span></span>
    * <span data-ttu-id="51f16-216">CompanyInfo</span><span class="sxs-lookup"><span data-stu-id="51f16-216">CompanyInfo</span></span>  
58. <span data-ttu-id="51f16-217">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="51f16-217">Click OK.</span></span>
    * <span data-ttu-id="51f16-218">Sélectionnez la table CompanyInfo comme source de données pour le modèle de données actuel.</span><span class="sxs-lookup"><span data-stu-id="51f16-218">Select the CompanyInfo table as a data source for the current data model.</span></span>  
59. <span data-ttu-id="51f16-219">Dans l'arborescence, sélectionnez « Fonctions\Champ calculé ».</span><span class="sxs-lookup"><span data-stu-id="51f16-219">In the tree, select 'Functions\Calculated field'.</span></span>
60. <span data-ttu-id="51f16-220">Cliquez sur Ajouter racine.</span><span class="sxs-lookup"><span data-stu-id="51f16-220">Click Add root.</span></span>
    * <span data-ttu-id="51f16-221">Insérez un champ calculé comme nouvelle source de données.</span><span class="sxs-lookup"><span data-stu-id="51f16-221">Insert a calculated field as a new data source.</span></span>  
61. <span data-ttu-id="51f16-222">Tapez « ProcessingDateTime » dans le champ Nom.</span><span class="sxs-lookup"><span data-stu-id="51f16-222">In the Name field, type 'ProcessingDateTime'.</span></span>
    * <span data-ttu-id="51f16-223">ProcessingDateTime</span><span class="sxs-lookup"><span data-stu-id="51f16-223">ProcessingDateTime</span></span>  
62. <span data-ttu-id="51f16-224">Dans le champ Étiquette, entrez « Date et heure de traitement ».</span><span class="sxs-lookup"><span data-stu-id="51f16-224">In the Label field, enter 'Processing date & time'.</span></span>
    * <span data-ttu-id="51f16-225">Date et heure de traitement</span><span class="sxs-lookup"><span data-stu-id="51f16-225">Processing date & time</span></span>  
63. <span data-ttu-id="51f16-226">Cliquez sur Modifier la formule.</span><span class="sxs-lookup"><span data-stu-id="51f16-226">Click Edit formula.</span></span>
64. <span data-ttu-id="51f16-227">Dans l'arborescence, sélectionnez « Date/time\SESSIONNOW ».</span><span class="sxs-lookup"><span data-stu-id="51f16-227">In the tree, select 'Date/time\SESSIONNOW'.</span></span>
65. <span data-ttu-id="51f16-228">Cliquez sur Ajouter une fonction.</span><span class="sxs-lookup"><span data-stu-id="51f16-228">Click Add function.</span></span>
66. <span data-ttu-id="51f16-229">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="51f16-229">Click Save.</span></span>
67. <span data-ttu-id="51f16-230">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="51f16-230">Close the page.</span></span>
68. <span data-ttu-id="51f16-231">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="51f16-231">Click OK.</span></span>
    * <span data-ttu-id="51f16-232">Ajoutez le champ calculé de ProcessingDateTime comme source de données pour le modèle de données actuel.</span><span class="sxs-lookup"><span data-stu-id="51f16-232">Add the ProcessingDateTime calculated field as a data source for the current data model.</span></span>  
69. <span data-ttu-id="51f16-233">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="51f16-233">Click Save.</span></span>
70. <span data-ttu-id="51f16-234">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="51f16-234">Close the page.</span></span>
71. <span data-ttu-id="51f16-235">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="51f16-235">Close the page.</span></span>
72. <span data-ttu-id="51f16-236">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="51f16-236">Close the page.</span></span>


