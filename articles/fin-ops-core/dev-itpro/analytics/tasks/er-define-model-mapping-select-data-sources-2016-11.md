---
title: Définir les mises en correspondance de modèles de gestion d’états électroniques et sélectionner des sources de données pour eux
description: Cette rubrique décrit comment un utilisateur doté du rôle Administrateur système ou Développeur d’états électroniques peut sélectionner des sources de données pour un modèle de données de génération d’états électroniques.
author: NickSelin
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ERWorkspace, ERSolutionTable, ERDataModelDesigner, ERModelMappingTable, ERModelMappingDesigner, ERExpressionDesignerFormula
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 7fccdda3ac441630836a0d33f78eb04e9cd26d4a
ms.sourcegitcommit: 5192cfaedfd861faea63d8954d7bcc500608a225
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/30/2021
ms.locfileid: "5092108"
---
# <a name="define-er-model-mappings-and-select-data-sources-for-them"></a><span data-ttu-id="0b61d-103">Définir les mises en correspondance de modèles de gestion d’états électroniques et sélectionner des sources de données pour eux</span><span class="sxs-lookup"><span data-stu-id="0b61d-103">Define ER model mappings and select data sources for them</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="0b61d-104">Les étapes suivantes expliquent comment un utilisateur doté du rôle Administrateur système ou Développeur d’états électroniques peut sélectionner des sources de données pour un modèle de données de génération d’états électroniques (ER).</span><span class="sxs-lookup"><span data-stu-id="0b61d-104">The following steps explain how a user in the System Administrator or Electronic Reporting Developer role can select data sources for an Electronic reporting (ER) data model.</span></span> <span data-ttu-id="0b61d-105">Les sources de données seront liées aux composants du modèle de données sélectionné au moment de la création et des données commerciales seront renseignées dans ce modèle de données au moment de l’exécution.</span><span class="sxs-lookup"><span data-stu-id="0b61d-105">The data sources will be bound to individual components of the selected data model at design time and populate business data to that data model at run-time.</span></span> <span data-ttu-id="0b61d-106">Dans cet exemple, vous allez sélectionner des sources de données pour un modèle de données existant qui a été créé pour la société témoin, Litware, Inc. Pour effectuer ces étapes, vous devez d’abord accomplir celles de la procédure « Créer un modèle de données ».</span><span class="sxs-lookup"><span data-stu-id="0b61d-106">In this example, you will select data sources for an existing data model that has been created for sample company, Litware, Inc. To complete these steps, you must first complete the steps in the "Create a new data model" procedure.</span></span>


## <a name="open-the-electronic-reporting-configurations-tree"></a><span data-ttu-id="0b61d-107">Ouvrir l’arborescence des configurations d’états électroniques</span><span class="sxs-lookup"><span data-stu-id="0b61d-107">Open the Electronic Reporting configurations tree</span></span>
1. <span data-ttu-id="0b61d-108">Accédez à Administration d’organisation > Espaces de travail > États électroniques.</span><span class="sxs-lookup"><span data-stu-id="0b61d-108">Go to Organization administration > Workspaces > Electronic reporting.</span></span>
2. <span data-ttu-id="0b61d-109">Cliquez sur Configurations des états.</span><span class="sxs-lookup"><span data-stu-id="0b61d-109">Click Reporting configurations.</span></span>

## <a name="insert-a-new-model-mapping"></a><span data-ttu-id="0b61d-110">Insérer une nouvelle mise en correspondance de modèle</span><span class="sxs-lookup"><span data-stu-id="0b61d-110">Insert a new model mapping</span></span>
1. <span data-ttu-id="0b61d-111">Dans l’arborescence, sélectionnez « Paiements (modèle simplifié) ».</span><span class="sxs-lookup"><span data-stu-id="0b61d-111">In the tree, select 'Payments (simplified model)'.</span></span>
2. <span data-ttu-id="0b61d-112">Cliquez sur Concepteur.</span><span class="sxs-lookup"><span data-stu-id="0b61d-112">Click Designer.</span></span>
3. <span data-ttu-id="0b61d-113">Cliquez sur Mettre en correspondance le modèle à la source de données.</span><span class="sxs-lookup"><span data-stu-id="0b61d-113">Click Map model to datasource.</span></span>
4. <span data-ttu-id="0b61d-114">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="0b61d-114">Click New.</span></span>
    * <span data-ttu-id="0b61d-115">Cette opération crée un enregistrement qui mappera le modèle de données aux sources de données.</span><span class="sxs-lookup"><span data-stu-id="0b61d-115">This will create a new record that will map the data model to data sources.</span></span> <span data-ttu-id="0b61d-116">Dans cet exemple, vous mapperez le modèle de données aux sources de données pour le type désiré de paiement : virement.</span><span class="sxs-lookup"><span data-stu-id="0b61d-116">In this example, you will map the data model to data sources for the desired payment type: credit transfer.</span></span>     <span data-ttu-id="0b61d-117">Il est possible de concevoir plusieurs mises en correspondance pour un modèle de données spécifique.</span><span class="sxs-lookup"><span data-stu-id="0b61d-117">It is possible to design more than one mapping for a particular data model.</span></span> <span data-ttu-id="0b61d-118">Par exemple, vous pouvez créer une mise en correspondance pour les différents types de paiements, comme le débit direct ou les virements bancaires.</span><span class="sxs-lookup"><span data-stu-id="0b61d-118">For example, you could create a mapping for the different types of payments, such as for direct debit or for credit transfers.</span></span> <span data-ttu-id="0b61d-119">Dans cet exemple, vous créerez une mise en correspondance pour les virements.</span><span class="sxs-lookup"><span data-stu-id="0b61d-119">In this example, you will create a mapping for credit transfers.</span></span>  
5. <span data-ttu-id="0b61d-120">Dans le champ Nom, tapez « Mise en correspondance VMT ».</span><span class="sxs-lookup"><span data-stu-id="0b61d-120">In the Name field, type 'CT mapping'.</span></span>
    * <span data-ttu-id="0b61d-121">Mise en correspondance VMT</span><span class="sxs-lookup"><span data-stu-id="0b61d-121">CT mapping</span></span>  
6. <span data-ttu-id="0b61d-122">Dans le champ Description, entrez « Mise en correspondance de modèle de paiement VMT ».</span><span class="sxs-lookup"><span data-stu-id="0b61d-122">In the Description field, type 'Payment model mapping CT'.</span></span>
    * <span data-ttu-id="0b61d-123">Mise en correspondance de modèle de paiement VMT</span><span class="sxs-lookup"><span data-stu-id="0b61d-123">Payment model mapping CT</span></span>  
7. <span data-ttu-id="0b61d-124">Dans le champ Définition, tapez « CustomerCreditTransferInitiation ».</span><span class="sxs-lookup"><span data-stu-id="0b61d-124">In the Definition field, type 'CustomerCreditTransferInitiation'.</span></span>
    * <span data-ttu-id="0b61d-125">CustomerCreditTransferInitiation</span><span class="sxs-lookup"><span data-stu-id="0b61d-125">CustomerCreditTransferInitiation</span></span>  
8. <span data-ttu-id="0b61d-126">Résolvez les modifications de la définition.</span><span class="sxs-lookup"><span data-stu-id="0b61d-126">ResolveChanges the Definition.</span></span>
9. <span data-ttu-id="0b61d-127">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="0b61d-127">Click Save.</span></span>

## <a name="define-required-data-sources-for-the-current-model-mapping"></a><span data-ttu-id="0b61d-128">Définir des sources de données pour la mise en correspondance de modèle existante</span><span class="sxs-lookup"><span data-stu-id="0b61d-128">Define required data sources for the current model mapping</span></span>
1. <span data-ttu-id="0b61d-129">Cliquez sur Concepteur.</span><span class="sxs-lookup"><span data-stu-id="0b61d-129">Click Designer.</span></span>
2. <span data-ttu-id="0b61d-130">Dans l’arborescence, sélectionnez « Dynamics 365 for Operations\Enregistrements de la table ».</span><span class="sxs-lookup"><span data-stu-id="0b61d-130">In the tree, select 'Dynamics 365 for Operations\Table records'.</span></span>
3. <span data-ttu-id="0b61d-131">Cliquez sur Ajouter racine.</span><span class="sxs-lookup"><span data-stu-id="0b61d-131">Click Add root.</span></span>
    * <span data-ttu-id="0b61d-132">Entrez cette source de données pour accéder à des transactions de paiement.</span><span class="sxs-lookup"><span data-stu-id="0b61d-132">Enter this data source to access payment transactions.</span></span>  
4. <span data-ttu-id="0b61d-133">Dans le champ Nom, tapez « Transactions ».</span><span class="sxs-lookup"><span data-stu-id="0b61d-133">In the Name field, type 'Transactions'.</span></span>
    * <span data-ttu-id="0b61d-134">Transactions</span><span class="sxs-lookup"><span data-stu-id="0b61d-134">Transactions</span></span>  
5. <span data-ttu-id="0b61d-135">Dans le champ Étiquette, tapez « Transactions ».</span><span class="sxs-lookup"><span data-stu-id="0b61d-135">In the Label field, enter 'Transactions'.</span></span>
    * <span data-ttu-id="0b61d-136">Transactions</span><span class="sxs-lookup"><span data-stu-id="0b61d-136">Transactions</span></span>  
6. <span data-ttu-id="0b61d-137">Dans le champ Aide, entrez « Lignes de journal comptable ».</span><span class="sxs-lookup"><span data-stu-id="0b61d-137">In the Help field, enter 'Ledger journal lines'.</span></span>
    * <span data-ttu-id="0b61d-138">Lignes de journal comptable</span><span class="sxs-lookup"><span data-stu-id="0b61d-138">Ledger journal lines</span></span>  
7. <span data-ttu-id="0b61d-139">Sélectionnez Oui dans le champ Demander une requête.</span><span class="sxs-lookup"><span data-stu-id="0b61d-139">Select Yes in the Ask for query field.</span></span>
    * <span data-ttu-id="0b61d-140">Sélectionnez Oui.</span><span class="sxs-lookup"><span data-stu-id="0b61d-140">Select Yes.</span></span>  
8. <span data-ttu-id="0b61d-141">Dans le champ Table, tapez « LedgerJournalTrans ».</span><span class="sxs-lookup"><span data-stu-id="0b61d-141">In the Table field, type 'LedgerJournalTrans'.</span></span>
    * <span data-ttu-id="0b61d-142">LedgerJournalTrans</span><span class="sxs-lookup"><span data-stu-id="0b61d-142">LedgerJournalTrans</span></span>  
9. <span data-ttu-id="0b61d-143">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="0b61d-143">Click OK.</span></span>
    * <span data-ttu-id="0b61d-144">Sélectionnez la table LedgerJournalTrans comme source de données pour le modèle de données actuel.</span><span class="sxs-lookup"><span data-stu-id="0b61d-144">Select the LedgerJournalTrans table as a data source for the current data model.</span></span>  
10. <span data-ttu-id="0b61d-145">Dans l’arborescence, sélectionnez « Fonctions\Champ calculé ».</span><span class="sxs-lookup"><span data-stu-id="0b61d-145">In the tree, select 'Functions\Calculated field'.</span></span>
11. <span data-ttu-id="0b61d-146">Cliquez sur Ajouter.</span><span class="sxs-lookup"><span data-stu-id="0b61d-146">Click Add.</span></span>
    * <span data-ttu-id="0b61d-147">Cliquez sur Ajouter pour ajouter un champ calculé.</span><span class="sxs-lookup"><span data-stu-id="0b61d-147">Click Add to add a new calculated field.</span></span>  
12. <span data-ttu-id="0b61d-148">Dans le champ Nom, tapez « $EndToEndID ».</span><span class="sxs-lookup"><span data-stu-id="0b61d-148">In the Name field, type '$EndToEndID'.</span></span>
    * <span data-ttu-id="0b61d-149">$EndToEndID</span><span class="sxs-lookup"><span data-stu-id="0b61d-149">$EndToEndID</span></span>  
13. <span data-ttu-id="0b61d-150">Cliquez sur Modifier la formule.</span><span class="sxs-lookup"><span data-stu-id="0b61d-150">Click Edit formula.</span></span>
14. <span data-ttu-id="0b61d-151">Dans l’arborescence, sélectionner « String\CONCATENATE ».</span><span class="sxs-lookup"><span data-stu-id="0b61d-151">In the tree, select 'String\CONCATENATE'.</span></span>
15. <span data-ttu-id="0b61d-152">Cliquez sur Ajouter une fonction.</span><span class="sxs-lookup"><span data-stu-id="0b61d-152">Click Add function.</span></span>
16. <span data-ttu-id="0b61d-153">Dans l’arborescence , développer « Transactions ».</span><span class="sxs-lookup"><span data-stu-id="0b61d-153">In the tree, expand 'Transactions'.</span></span>
17. <span data-ttu-id="0b61d-154">Dans l’arborescence, sélectionnez « Transactions\Document ».</span><span class="sxs-lookup"><span data-stu-id="0b61d-154">In the tree, select 'Transactions\Voucher'.</span></span>
18. <span data-ttu-id="0b61d-155">Cliquez sur Ajouter une source de données.</span><span class="sxs-lookup"><span data-stu-id="0b61d-155">Click Add data source.</span></span>
19. <span data-ttu-id="0b61d-156">Dans le champ Formule, entrez « CONCATENATE(Transactions.Voucher, "-", ».</span><span class="sxs-lookup"><span data-stu-id="0b61d-156">In the Formula field, enter 'CONCATENATE(Transactions.Voucher, "-", '.</span></span>
    * <span data-ttu-id="0b61d-157">Tapez [ , "-", ] à la fin de la formule.</span><span class="sxs-lookup"><span data-stu-id="0b61d-157">Type [ , "-", ] at the end of the formula.</span></span>  
20. <span data-ttu-id="0b61d-158">Dans l’arborescence , sélectionnez « Chaîne\TEXTE ».</span><span class="sxs-lookup"><span data-stu-id="0b61d-158">In the tree, select 'String\TEXT'.</span></span>
21. <span data-ttu-id="0b61d-159">Cliquez sur Ajouter une fonction.</span><span class="sxs-lookup"><span data-stu-id="0b61d-159">Click Add function.</span></span>
22. <span data-ttu-id="0b61d-160">Dans l’arborescence, sélectionnez « Transactions\ID enregistrement (RecId) ».</span><span class="sxs-lookup"><span data-stu-id="0b61d-160">In the tree, select 'Transactions\Record-ID(RecId)'.</span></span>
23. <span data-ttu-id="0b61d-161">Cliquez sur Ajouter une source de données.</span><span class="sxs-lookup"><span data-stu-id="0b61d-161">Click Add data source.</span></span>
24. <span data-ttu-id="0b61d-162">Dans le champ Formule, entrez « CONCATENATE(Transactions.Voucher, "-", TEXT(Transactions.RecId)) ».</span><span class="sxs-lookup"><span data-stu-id="0b61d-162">In the Formula field, enter 'CONCATENATE(Transactions.Voucher, "-", TEXT(Transactions.RecId))'.</span></span>
    * <span data-ttu-id="0b61d-163">Tapez [))] à la fin de la formule.</span><span class="sxs-lookup"><span data-stu-id="0b61d-163">Type [))] at the end of the formula.</span></span>  
25. <span data-ttu-id="0b61d-164">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="0b61d-164">Click Save.</span></span>
    * <span data-ttu-id="0b61d-165">Assurez-vous qu’aucune erreur n’a été découverte dans la formule créée.</span><span class="sxs-lookup"><span data-stu-id="0b61d-165">Make sure that no errors have been discovered for the created formula.</span></span> <span data-ttu-id="0b61d-166">Voir l’onglet ERREURS en dessous du contrôle d’éditeur de formule.</span><span class="sxs-lookup"><span data-stu-id="0b61d-166">See the ERRORS tab below the formula editor control.</span></span>  
26. <span data-ttu-id="0b61d-167">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="0b61d-167">Close the page.</span></span>
27. <span data-ttu-id="0b61d-168">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="0b61d-168">Click OK.</span></span>
    * <span data-ttu-id="0b61d-169">Ajoutez le champ calculé à cette source de données.</span><span class="sxs-lookup"><span data-stu-id="0b61d-169">Add the calculated field to this data source.</span></span>  
28. <span data-ttu-id="0b61d-170">Cliquez sur Ajouter.</span><span class="sxs-lookup"><span data-stu-id="0b61d-170">Click Add.</span></span>
    * <span data-ttu-id="0b61d-171">Cliquez sur Ajouter pour ajouter un champ calculé.</span><span class="sxs-lookup"><span data-stu-id="0b61d-171">Click Add to add a new calculated field.</span></span>  
29. <span data-ttu-id="0b61d-172">Dans le champ Nom, tapez « $Amount ».</span><span class="sxs-lookup"><span data-stu-id="0b61d-172">In the Name field, type '$Amount'.</span></span>
    * <span data-ttu-id="0b61d-173">$Montant</span><span class="sxs-lookup"><span data-stu-id="0b61d-173">$Amount</span></span>  
30. <span data-ttu-id="0b61d-174">Cliquez sur Modifier la formule.</span><span class="sxs-lookup"><span data-stu-id="0b61d-174">Click Edit formula.</span></span>
31. <span data-ttu-id="0b61d-175">Dans l’arborescence , développer « Transactions ».</span><span class="sxs-lookup"><span data-stu-id="0b61d-175">In the tree, expand 'Transactions'.</span></span>
32. <span data-ttu-id="0b61d-176">Dans l’arborescence, sélectionnez « Transactions\Debit(AmountCurDebit) ».</span><span class="sxs-lookup"><span data-stu-id="0b61d-176">In the tree, select 'Transactions\Debit(AmountCurDebit)'.</span></span>
33. <span data-ttu-id="0b61d-177">Cliquez sur Ajouter une source de données.</span><span class="sxs-lookup"><span data-stu-id="0b61d-177">Click Add data source.</span></span>
34. <span data-ttu-id="0b61d-178">Dans le champ Formule, entrez « Transactions.AmountCurDebit -  ».</span><span class="sxs-lookup"><span data-stu-id="0b61d-178">In the Formula field, enter 'Transactions.AmountCurDebit - '.</span></span>
    * <span data-ttu-id="0b61d-179">Tapez [ - ] à la fin de la formule.</span><span class="sxs-lookup"><span data-stu-id="0b61d-179">Type [ - ] at the end of the formula.</span></span>  
35. <span data-ttu-id="0b61d-180">Dans l’arborescence, sélectionnez « Transactions\Credit(AmountCurCredit) ».</span><span class="sxs-lookup"><span data-stu-id="0b61d-180">In the tree, select 'Transactions\Credit(AmountCurCredit)'.</span></span>
36. <span data-ttu-id="0b61d-181">Cliquez sur Ajouter une source de données.</span><span class="sxs-lookup"><span data-stu-id="0b61d-181">Click Add data source.</span></span>
37. <span data-ttu-id="0b61d-182">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="0b61d-182">Click Save.</span></span>
38. <span data-ttu-id="0b61d-183">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="0b61d-183">Close the page.</span></span>
39. <span data-ttu-id="0b61d-184">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="0b61d-184">Click OK.</span></span>
    * <span data-ttu-id="0b61d-185">Cela ajoutera le champ calculé de $Amount à la source de données sélectionnée pour le modèle de données actuel.</span><span class="sxs-lookup"><span data-stu-id="0b61d-185">This will add the $Amount calculated field to the selected data source for the current data model.</span></span>  
40. <span data-ttu-id="0b61d-186">Dans l’arborescence, sélectionnez « Transactions\$Amount ».</span><span class="sxs-lookup"><span data-stu-id="0b61d-186">In the tree, select 'Transactions\$Amount'.</span></span>
41. <span data-ttu-id="0b61d-187">Dans l’arborescence , développer « Transactions ».</span><span class="sxs-lookup"><span data-stu-id="0b61d-187">In the tree, expand 'Transactions'.</span></span>
42. <span data-ttu-id="0b61d-188">Dans l’arborescence, développez ou réduisez « Transactions\$Amount ».</span><span class="sxs-lookup"><span data-stu-id="0b61d-188">In the tree, expand or collapse 'Transactions\$Amount'.</span></span>
43. <span data-ttu-id="0b61d-189">Dans l’arborescence, développez ou réduisez « Transactions ».</span><span class="sxs-lookup"><span data-stu-id="0b61d-189">In the tree, expand or collapse 'Transactions'.</span></span>
44. <span data-ttu-id="0b61d-190">Dans l’arborescence, sélectionnez « Dynamics 365 for Operations\Enregistrements de la table ».</span><span class="sxs-lookup"><span data-stu-id="0b61d-190">In the tree, select 'Dynamics 365 for Operations\Table records'.</span></span>
45. <span data-ttu-id="0b61d-191">Cliquez sur Ajouter racine.</span><span class="sxs-lookup"><span data-stu-id="0b61d-191">Click Add root.</span></span>
    * <span data-ttu-id="0b61d-192">Entrez cette source de données pour accéder aux détails du compte bancaire de la société.</span><span class="sxs-lookup"><span data-stu-id="0b61d-192">Enter this data source to access the company's bank account details.</span></span>  
46. <span data-ttu-id="0b61d-193">Dans le champ Nom, tapez « BankAccount ».</span><span class="sxs-lookup"><span data-stu-id="0b61d-193">In the Name field, type 'BankAccount'.</span></span>
    * <span data-ttu-id="0b61d-194">BankAccount</span><span class="sxs-lookup"><span data-stu-id="0b61d-194">BankAccount</span></span>  
47. <span data-ttu-id="0b61d-195">Dans le champ Étiquette, tapez « Compte bancaire ».</span><span class="sxs-lookup"><span data-stu-id="0b61d-195">In the Label field, enter 'Bank Account'.</span></span>
    * <span data-ttu-id="0b61d-196">Compte bancaire</span><span class="sxs-lookup"><span data-stu-id="0b61d-196">Bank Account</span></span>  
48. <span data-ttu-id="0b61d-197">Dans le champ Aide, tapez « Compte bancaire ».</span><span class="sxs-lookup"><span data-stu-id="0b61d-197">In the Help field, enter 'Bank Account'.</span></span>
    * <span data-ttu-id="0b61d-198">Compte bancaire</span><span class="sxs-lookup"><span data-stu-id="0b61d-198">Bank Account</span></span>  
49. <span data-ttu-id="0b61d-199">Sélectionnez Oui dans le champ Demander une requête.</span><span class="sxs-lookup"><span data-stu-id="0b61d-199">Select Yes in the Ask for query field.</span></span>
    * <span data-ttu-id="0b61d-200">Sélectionnez Oui.</span><span class="sxs-lookup"><span data-stu-id="0b61d-200">Select Yes.</span></span>  
50. <span data-ttu-id="0b61d-201">Dans le champ Table, tapez « BankAccountTable ».</span><span class="sxs-lookup"><span data-stu-id="0b61d-201">In the Table field, type 'BankAccountTable'.</span></span>
    * <span data-ttu-id="0b61d-202">BankAccountTable</span><span class="sxs-lookup"><span data-stu-id="0b61d-202">BankAccountTable</span></span>  
51. <span data-ttu-id="0b61d-203">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="0b61d-203">Click OK.</span></span>
    * <span data-ttu-id="0b61d-204">Sélectionnez la table BankAccountTable comme source de données pour le modèle de données actuel.</span><span class="sxs-lookup"><span data-stu-id="0b61d-204">Select the BankAccountTable table as a data source for the current data model.</span></span>  
52. <span data-ttu-id="0b61d-205">Cliquez sur Ajouter racine.</span><span class="sxs-lookup"><span data-stu-id="0b61d-205">Click Add root.</span></span>
    * <span data-ttu-id="0b61d-206">Entrez cette source de données pour accéder aux conditions de la société.</span><span class="sxs-lookup"><span data-stu-id="0b61d-206">Enter this data source to access the company's requisites.</span></span>  
53. <span data-ttu-id="0b61d-207">Dans le champ Nom, tapez « Société ».</span><span class="sxs-lookup"><span data-stu-id="0b61d-207">In the Name field, type 'Company'.</span></span>
    * <span data-ttu-id="0b61d-208">Société</span><span class="sxs-lookup"><span data-stu-id="0b61d-208">Company</span></span>  
54. <span data-ttu-id="0b61d-209">Dans le champ Étiquette, tapez une valeur.</span><span class="sxs-lookup"><span data-stu-id="0b61d-209">In the Label field, type a value.</span></span>
    * <span data-ttu-id="0b61d-210">Informations sur la société</span><span class="sxs-lookup"><span data-stu-id="0b61d-210">Company information</span></span>  
55. <span data-ttu-id="0b61d-211">Dans le champ Aide, entrez « Informations sur la société ».</span><span class="sxs-lookup"><span data-stu-id="0b61d-211">In the Help field, enter 'Company information'.</span></span>
    * <span data-ttu-id="0b61d-212">Informations sur la société</span><span class="sxs-lookup"><span data-stu-id="0b61d-212">Company information</span></span>  
56. <span data-ttu-id="0b61d-213">Sélectionnez Oui dans le champ Demander une requête.</span><span class="sxs-lookup"><span data-stu-id="0b61d-213">Select Yes in the Ask for query field.</span></span>
    * <span data-ttu-id="0b61d-214">Sélectionnez Oui.</span><span class="sxs-lookup"><span data-stu-id="0b61d-214">Select Yes.</span></span>  
57. <span data-ttu-id="0b61d-215">Dans le champ Table, tapez « CompanyInfo ».</span><span class="sxs-lookup"><span data-stu-id="0b61d-215">In the Table field, type 'CompanyInfo'.</span></span>
    * <span data-ttu-id="0b61d-216">CompanyInfo</span><span class="sxs-lookup"><span data-stu-id="0b61d-216">CompanyInfo</span></span>  
58. <span data-ttu-id="0b61d-217">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="0b61d-217">Click OK.</span></span>
    * <span data-ttu-id="0b61d-218">Sélectionnez la table CompanyInfo comme source de données pour le modèle de données actuel.</span><span class="sxs-lookup"><span data-stu-id="0b61d-218">Select the CompanyInfo table as a data source for the current data model.</span></span>  
59. <span data-ttu-id="0b61d-219">Dans l’arborescence, sélectionnez « Fonctions\Champ calculé ».</span><span class="sxs-lookup"><span data-stu-id="0b61d-219">In the tree, select 'Functions\Calculated field'.</span></span>
60. <span data-ttu-id="0b61d-220">Cliquez sur Ajouter racine.</span><span class="sxs-lookup"><span data-stu-id="0b61d-220">Click Add root.</span></span>
    * <span data-ttu-id="0b61d-221">Insérez un champ calculé comme nouvelle source de données.</span><span class="sxs-lookup"><span data-stu-id="0b61d-221">Insert a calculated field as a new data source.</span></span>  
61. <span data-ttu-id="0b61d-222">Tapez « ProcessingDateTime » dans le champ Nom.</span><span class="sxs-lookup"><span data-stu-id="0b61d-222">In the Name field, type 'ProcessingDateTime'.</span></span>
    * <span data-ttu-id="0b61d-223">ProcessingDateTime</span><span class="sxs-lookup"><span data-stu-id="0b61d-223">ProcessingDateTime</span></span>  
62. <span data-ttu-id="0b61d-224">Dans le champ Étiquette, entrez « Date et heure de traitement ».</span><span class="sxs-lookup"><span data-stu-id="0b61d-224">In the Label field, enter 'Processing date & time'.</span></span>
    * <span data-ttu-id="0b61d-225">Date et heure de traitement</span><span class="sxs-lookup"><span data-stu-id="0b61d-225">Processing date & time</span></span>  
63. <span data-ttu-id="0b61d-226">Cliquez sur Modifier la formule.</span><span class="sxs-lookup"><span data-stu-id="0b61d-226">Click Edit formula.</span></span>
64. <span data-ttu-id="0b61d-227">Dans l’arborescence, sélectionnez « Date/time\SESSIONNOW ».</span><span class="sxs-lookup"><span data-stu-id="0b61d-227">In the tree, select 'Date/time\SESSIONNOW'.</span></span>
65. <span data-ttu-id="0b61d-228">Cliquez sur Ajouter une fonction.</span><span class="sxs-lookup"><span data-stu-id="0b61d-228">Click Add function.</span></span>
66. <span data-ttu-id="0b61d-229">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="0b61d-229">Click Save.</span></span>
67. <span data-ttu-id="0b61d-230">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="0b61d-230">Close the page.</span></span>
68. <span data-ttu-id="0b61d-231">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="0b61d-231">Click OK.</span></span>
    * <span data-ttu-id="0b61d-232">Ajoutez le champ calculé de ProcessingDateTime comme source de données pour le modèle de données actuel.</span><span class="sxs-lookup"><span data-stu-id="0b61d-232">Add the ProcessingDateTime calculated field as a data source for the current data model.</span></span>  
69. <span data-ttu-id="0b61d-233">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="0b61d-233">Click Save.</span></span>
70. <span data-ttu-id="0b61d-234">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="0b61d-234">Close the page.</span></span>
71. <span data-ttu-id="0b61d-235">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="0b61d-235">Close the page.</span></span>
72. <span data-ttu-id="0b61d-236">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="0b61d-236">Close the page.</span></span>

