---
title: ER Mapper le modèle de données aux sources de données sélectionnées
description: Cette rubrique décrit comment mapper un modèle de données pour la gestion des états électroniques à une sélection de sources de données Microsoft Dynamics 365 Finance.
author: NickSelin
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: ERWorkspace, ERSolutionTable, ERDataModelDesigner, ERModelMappingTable, ERModelMappingDesigner
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 8b6f5e3b64e7d000feb7fa1ff84edd2e20891bb7
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/09/2021
ms.locfileid: "5570660"
---
# <a name="er-map-data-model-to-selected-data-sources"></a><span data-ttu-id="1e4b7-103">ER Mapper le modèle de données aux sources de données sélectionnées</span><span class="sxs-lookup"><span data-stu-id="1e4b7-103">ER Map data model to selected data sources</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="1e4b7-104">Les étapes suivantes expliquent comment un utilisateur bénéficiant du rôle Administrateur système ou Développeur d’états électroniques peut mapper un modèle de données de génération d’états électronique (ER) vers des sources de données sélectionnées.</span><span class="sxs-lookup"><span data-stu-id="1e4b7-104">The following steps explain how a user in the System Administrator or Electronic Reporting Developer role can map an Electronic reporting (ER) data model to selected data sources.</span></span> <span data-ttu-id="1e4b7-105">Cette mise en correspondance de modèles sera utilisée ultérieurement comme source de données dans la configuration du format à utiliser pour gérer des documents de paiement électronique.</span><span class="sxs-lookup"><span data-stu-id="1e4b7-105">This model mapping will later be used as a data source in a format configuration that will be used to manage electronic payment documents.</span></span> <span data-ttu-id="1e4b7-106">Dans cet exemple, vous mettez en correspondance un modèle de données pour la société témoin, Litware, Inc. avec des sources de données.</span><span class="sxs-lookup"><span data-stu-id="1e4b7-106">In this example, you map a data model for sample company, Litware, Inc. to data sources.</span></span> <span data-ttu-id="1e4b7-107">Pour effectuer ces étapes, vous devez tout d’abord appliquer la procédure « Sélectionner des sources de données pour la mise en correspondance de modèles ».</span><span class="sxs-lookup"><span data-stu-id="1e4b7-107">To complete these steps, you must first complete the steps in the "Select data sources for model mapping" procedure.</span></span>


## <a name="open-er-configurations-tree"></a><span data-ttu-id="1e4b7-108">Ouvrir l’arborescence de configurations d’ER</span><span class="sxs-lookup"><span data-stu-id="1e4b7-108">Open ER configurations tree</span></span>
1. <span data-ttu-id="1e4b7-109">Accédez à Administration d’organisation > Espaces de travail > États électroniques.</span><span class="sxs-lookup"><span data-stu-id="1e4b7-109">Go to Organization administration > Workspaces > Electronic reporting.</span></span>
2. <span data-ttu-id="1e4b7-110">Cliquez sur Configurations.</span><span class="sxs-lookup"><span data-stu-id="1e4b7-110">Click Configurations.</span></span>

## <a name="select-created-model-mapping"></a><span data-ttu-id="1e4b7-111">Sélectionner une mise en correspondance de modèles créée</span><span class="sxs-lookup"><span data-stu-id="1e4b7-111">Select created model mapping</span></span>
1. <span data-ttu-id="1e4b7-112">Dans l’arborescence, sélectionnez « Paiements (modèle simplifié) ».</span><span class="sxs-lookup"><span data-stu-id="1e4b7-112">In the tree, select 'Payments (simplified model)'.</span></span>
    * <span data-ttu-id="1e4b7-113">Vérifiez que la configuration du modèle « Paiements (modèle simplifié) » a été créée à l’avance.</span><span class="sxs-lookup"><span data-stu-id="1e4b7-113">Make sure that the model configuration "Payments (simplified model)" has been created in advance.</span></span> <span data-ttu-id="1e4b7-114">Dans le cas contraire, arrêtez dès à présent et revenez après avoir effectué la section « Créer une configuration avec le modèle de données du domaine sélectionné » du Guide de tâche.</span><span class="sxs-lookup"><span data-stu-id="1e4b7-114">Otherwise, stop now and return after completion of the task guide 'Create a new configuration with data model of the selected domain'.</span></span>  
2. <span data-ttu-id="1e4b7-115">Cliquez sur Concepteur de modèles.</span><span class="sxs-lookup"><span data-stu-id="1e4b7-115">Click Model designer.</span></span>
3. <span data-ttu-id="1e4b7-116">Cliquez sur Mettre en correspondance le modèle à la source de données.</span><span class="sxs-lookup"><span data-stu-id="1e4b7-116">Click Map model to datasource.</span></span>
4. <span data-ttu-id="1e4b7-117">Sélectionnez l’enregistrement « Mise en correspondance de CT ».</span><span class="sxs-lookup"><span data-stu-id="1e4b7-117">Select the 'CT mapping' record.</span></span>
    * <span data-ttu-id="1e4b7-118">Mise en correspondance VMT</span><span class="sxs-lookup"><span data-stu-id="1e4b7-118">CT mapping</span></span>  

## <a name="bind-created-data-sources-to-data-model-elements"></a><span data-ttu-id="1e4b7-119">Lier des sources de données créées à des éléments de modèles de données</span><span class="sxs-lookup"><span data-stu-id="1e4b7-119">Bind created data sources to data model elements</span></span>
1. <span data-ttu-id="1e4b7-120">Cliquez sur Concepteur.</span><span class="sxs-lookup"><span data-stu-id="1e4b7-120">Click Designer.</span></span>
2. <span data-ttu-id="1e4b7-121">Dans l’arborescence, sélectionnez « Date et heure de traitement(ProcessingDateTime) ».</span><span class="sxs-lookup"><span data-stu-id="1e4b7-121">In the tree, select 'Processing date & time(ProcessingDateTime)'.</span></span>
3. <span data-ttu-id="1e4b7-122">Dans l’arborescence, sélectionnez « Date de traitement(ProcessingDateTime) ».</span><span class="sxs-lookup"><span data-stu-id="1e4b7-122">In the tree, select 'Processing date(ProcessingDateTime)'.</span></span>
4. <span data-ttu-id="1e4b7-123">Cliquez sur Lier.</span><span class="sxs-lookup"><span data-stu-id="1e4b7-123">Click Bind.</span></span>
5. <span data-ttu-id="1e4b7-124">Dans l’arborescence, sélectionnez « Identification de message de paiement (MessageIdentification) ».</span><span class="sxs-lookup"><span data-stu-id="1e4b7-124">In the tree, select 'Payment message identification(MessageIdentification)'.</span></span>
6. <span data-ttu-id="1e4b7-125">Dans l’arborescence , développer « Transactions ».</span><span class="sxs-lookup"><span data-stu-id="1e4b7-125">In the tree, expand 'Transactions'.</span></span>
7. <span data-ttu-id="1e4b7-126">Dans l’arborescence, sélectionnez « Transactions\Numéro de lot du journal(JournalNum) ».</span><span class="sxs-lookup"><span data-stu-id="1e4b7-126">In the tree, select 'Transactions\Journal batch number(JournalNum)'.</span></span>
8. <span data-ttu-id="1e4b7-127">Cliquez sur Lier.</span><span class="sxs-lookup"><span data-stu-id="1e4b7-127">Click Bind.</span></span>
9. <span data-ttu-id="1e4b7-128">Dans l’arborescence, sélectionnez « Paiements ».</span><span class="sxs-lookup"><span data-stu-id="1e4b7-128">In the tree, select 'Payments'.</span></span>
10. <span data-ttu-id="1e4b7-129">Dans l’arborescence, sélectionnez « Transactions ».</span><span class="sxs-lookup"><span data-stu-id="1e4b7-129">In the tree, select 'Transactions'.</span></span>
11. <span data-ttu-id="1e4b7-130">Cliquez sur Lier.</span><span class="sxs-lookup"><span data-stu-id="1e4b7-130">Click Bind.</span></span>
12. <span data-ttu-id="1e4b7-131">Dans l’arborescence , développez « Paiements=Transactions ».</span><span class="sxs-lookup"><span data-stu-id="1e4b7-131">In the tree, expand 'Payments= Transactions'.</span></span>
13. <span data-ttu-id="1e4b7-132">Dans l’arborescence , développez « Paiements=Transactions\Créditeur ».</span><span class="sxs-lookup"><span data-stu-id="1e4b7-132">In the tree, expand 'Payments= Transactions\Creditor'.</span></span>
14. <span data-ttu-id="1e4b7-133">Dans l’arborescence , développez « Paiements=Transactions\Créditeur\Compte ».</span><span class="sxs-lookup"><span data-stu-id="1e4b7-133">In the tree, expand 'Payments= Transactions\Creditor\Account'.</span></span>
15. <span data-ttu-id="1e4b7-134">Dans l’arborescence, sélectionnez « Paiements=Transactions\Créditeur\Compte\Code devise(Currency) ».</span><span class="sxs-lookup"><span data-stu-id="1e4b7-134">In the tree, select 'Payments= Transactions\Creditor\Account\Currency code(Currency)'.</span></span>
16. <span data-ttu-id="1e4b7-135">Dans l’arborescence , développez « Transactions\vendBankAccountInTransactionCompany() ».</span><span class="sxs-lookup"><span data-stu-id="1e4b7-135">In the tree, expand 'Transactions\vendBankAccountInTransactionCompany()'.</span></span>
17. <span data-ttu-id="1e4b7-136">Dans l’arborescence, sélectionnez « Transactions\vendBankAccountInTransactionCompany()\Currency(CurrencyCode) ».</span><span class="sxs-lookup"><span data-stu-id="1e4b7-136">In the tree, select 'Transactions\vendBankAccountInTransactionCompany()\Currency(CurrencyCode)'.</span></span>
18. <span data-ttu-id="1e4b7-137">Cliquez sur Lier.</span><span class="sxs-lookup"><span data-stu-id="1e4b7-137">Click Bind.</span></span>
19. <span data-ttu-id="1e4b7-138">Dans l’arborescence, sélectionnez « Paiements=Transactions\Créditeur\Compte\Code IBAN(IBAN) ».</span><span class="sxs-lookup"><span data-stu-id="1e4b7-138">In the tree, select 'Payments= Transactions\Creditor\Account\IBAN code(IBAN)'.</span></span>
20. <span data-ttu-id="1e4b7-139">Dans l’arborescence , sélectionnez « Transactions\vendBankAccountInTransactionCompany()\IBAN(BankIBAN) ».</span><span class="sxs-lookup"><span data-stu-id="1e4b7-139">In the tree, select 'Transactions\vendBankAccountInTransactionCompany()\IBAN(BankIBAN)'.</span></span>
21. <span data-ttu-id="1e4b7-140">Cliquez sur Lier.</span><span class="sxs-lookup"><span data-stu-id="1e4b7-140">Click Bind.</span></span>
22. <span data-ttu-id="1e4b7-141">Dans l’arborescence, sélectionnez « Paiements=Transactions\Créditeur\Compte\Numéro ».</span><span class="sxs-lookup"><span data-stu-id="1e4b7-141">In the tree, select 'Payments= Transactions\Creditor\Account\Number'.</span></span>
23. <span data-ttu-id="1e4b7-142">Dans l’arborescence , sélectionnez « Transactions\vendBankAccountInTransactionCompany()\Numéro de compte bancaire(AccountNum) ».</span><span class="sxs-lookup"><span data-stu-id="1e4b7-142">In the tree, select 'Transactions\vendBankAccountInTransactionCompany()\Bank account number(AccountNum)'.</span></span>
24. <span data-ttu-id="1e4b7-143">Cliquez sur Lier.</span><span class="sxs-lookup"><span data-stu-id="1e4b7-143">Click Bind.</span></span>
25. <span data-ttu-id="1e4b7-144">Dans l’arborescence , développez « Paiements=Transactions\Créditeur\Agent ».</span><span class="sxs-lookup"><span data-stu-id="1e4b7-144">In the tree, expand 'Payments= Transactions\Creditor\Agent'.</span></span>
26. <span data-ttu-id="1e4b7-145">Dans l’arborescence, sélectionnez « Paiements=Transactions\Créditeur\Agent\Nom ».</span><span class="sxs-lookup"><span data-stu-id="1e4b7-145">In the tree, select 'Payments= Transactions\Creditor\Agent\Name'.</span></span>
27. <span data-ttu-id="1e4b7-146">Dans l’arborescence , sélectionnez « Transactions\vendBankAccountInTransactionCompany()\Nom ».</span><span class="sxs-lookup"><span data-stu-id="1e4b7-146">In the tree, select 'Transactions\vendBankAccountInTransactionCompany()\Name'.</span></span>
28. <span data-ttu-id="1e4b7-147">Cliquez sur Lier.</span><span class="sxs-lookup"><span data-stu-id="1e4b7-147">Click Bind.</span></span>
29. <span data-ttu-id="1e4b7-148">Dans l’arborescence, sélectionnez « Paiements=Transactions\Créditeur\Agent\Numéro de routage(RoutingNumber) ».</span><span class="sxs-lookup"><span data-stu-id="1e4b7-148">In the tree, select 'Payments= Transactions\Creditor\Agent\Routing number(RoutingNumber)'.</span></span>
30. <span data-ttu-id="1e4b7-149">Dans l’arborescence , sélectionnez « Transactions\vendBankAccountInTransactionCompany()\Numéro de routage(RegistrationNum) ».</span><span class="sxs-lookup"><span data-stu-id="1e4b7-149">In the tree, select 'Transactions\vendBankAccountInTransactionCompany()\Routing number(RegistrationNum)'.</span></span>
31. <span data-ttu-id="1e4b7-150">Cliquez sur Lier.</span><span class="sxs-lookup"><span data-stu-id="1e4b7-150">Click Bind.</span></span>
32. <span data-ttu-id="1e4b7-151">Dans l’arborescence, sélectionnez « Paiements=Transactions\Créditeur\Agent\Code SWIFT(SWIFT) ».</span><span class="sxs-lookup"><span data-stu-id="1e4b7-151">In the tree, select 'Payments= Transactions\Creditor\Agent\SWIFT code(SWIFT)'.</span></span>
33. <span data-ttu-id="1e4b7-152">Dans l’arborescence, sélectionnez « Transactions\vendBankAccountInTransactionCompany()\Code SWIFT(SWIFTNo) ».</span><span class="sxs-lookup"><span data-stu-id="1e4b7-152">In the tree, select 'Transactions\vendBankAccountInTransactionCompany()\SWIFT code(SWIFTNo)'.</span></span>
34. <span data-ttu-id="1e4b7-153">Cliquez sur Lier.</span><span class="sxs-lookup"><span data-stu-id="1e4b7-153">Click Bind.</span></span>
35. <span data-ttu-id="1e4b7-154">Dans l’arborescence, sélectionnez « Paiements=Transactions\Créditeur\Nom ».</span><span class="sxs-lookup"><span data-stu-id="1e4b7-154">In the tree, select 'Payments= Transactions\Creditor\Name'.</span></span>
36. <span data-ttu-id="1e4b7-155">Dans l’arborescence , développez « Transactions\findVendTable() ».</span><span class="sxs-lookup"><span data-stu-id="1e4b7-155">In the tree, expand 'Transactions\findVendTable()'.</span></span>
37. <span data-ttu-id="1e4b7-156">Dans l’arborescence , sélectionnez « Transactions\findVendTable()name() ».</span><span class="sxs-lookup"><span data-stu-id="1e4b7-156">In the tree, select 'Transactions\findVendTable()\name()'.</span></span>
38. <span data-ttu-id="1e4b7-157">Cliquez sur Lier.</span><span class="sxs-lookup"><span data-stu-id="1e4b7-157">Click Bind.</span></span>
39. <span data-ttu-id="1e4b7-158">Dans l’arborescence, sélectionnez « Paiements=Transactions\Code devise(Currency) ».</span><span class="sxs-lookup"><span data-stu-id="1e4b7-158">In the tree, select 'Payments= Transactions\Currency code(Currency)'.</span></span>
40. <span data-ttu-id="1e4b7-159">Dans l’arborescence, développez « Transactions\>Relations ».</span><span class="sxs-lookup"><span data-stu-id="1e4b7-159">In the tree, expand 'Transactions\>Relations'.</span></span>
41. <span data-ttu-id="1e4b7-160">Dans l’arborescence, développez « Transactions\>Relations\Table des devises(Currency) ».</span><span class="sxs-lookup"><span data-stu-id="1e4b7-160">In the tree, expand 'Transactions\>Relations\Currency table(Currency)'.</span></span>
42. <span data-ttu-id="1e4b7-161">Dans l’arborescence, sélectionnez « Transactions\>Relations\Table des devises(Currency)\Code devis (CurrencyCodeISO) ».</span><span class="sxs-lookup"><span data-stu-id="1e4b7-161">In the tree, select 'Transactions\>Relations\Currency table(Currency)\Currency code(CurrencyCodeISO)'.</span></span>
43. <span data-ttu-id="1e4b7-162">Cliquez sur Lier.</span><span class="sxs-lookup"><span data-stu-id="1e4b7-162">Click Bind.</span></span>
44. <span data-ttu-id="1e4b7-163">Dans l’arborescence , développez « Paiements=Transactions\Débiteur ».</span><span class="sxs-lookup"><span data-stu-id="1e4b7-163">In the tree, expand 'Payments= Transactions\Debtor'.</span></span>
45. <span data-ttu-id="1e4b7-164">Dans l’arborescence , développez « Paiements=Transactions\Débiteur\Compte ».</span><span class="sxs-lookup"><span data-stu-id="1e4b7-164">In the tree, expand 'Payments= Transactions\Debtor\Account'.</span></span>
46. <span data-ttu-id="1e4b7-165">Dans l’arborescence, sélectionnez « Paiements=Transactions\Débiteur\Compte\Code devise(Currency) ».</span><span class="sxs-lookup"><span data-stu-id="1e4b7-165">In the tree, select 'Payments= Transactions\Debtor\Account\Currency code(Currency)'.</span></span>
47. <span data-ttu-id="1e4b7-166">Dans l’arborescence, sélectionnez « Compte bancaire(BankAccount) ».</span><span class="sxs-lookup"><span data-stu-id="1e4b7-166">In the tree, select 'Bank Account(BankAccount)'.</span></span>
48. <span data-ttu-id="1e4b7-167">Dans l’arborescence, développez « Compte bancaire(BankAccount) ».</span><span class="sxs-lookup"><span data-stu-id="1e4b7-167">In the tree, expand 'Bank Account(BankAccount)'.</span></span>
49. <span data-ttu-id="1e4b7-168">Dans l’arborescence, sélectionnez « Compte bancaire(BankAccount)\Devise(CurrencyCode) ».</span><span class="sxs-lookup"><span data-stu-id="1e4b7-168">In the tree, select 'Bank Account(BankAccount)\Currency(CurrencyCode)'.</span></span>
50. <span data-ttu-id="1e4b7-169">Cliquez sur Lier.</span><span class="sxs-lookup"><span data-stu-id="1e4b7-169">Click Bind.</span></span>
51. <span data-ttu-id="1e4b7-170">Dans l’arborescence, sélectionnez « Compte bancaire(BankAccount)\IBAN ».</span><span class="sxs-lookup"><span data-stu-id="1e4b7-170">In the tree, select 'Bank Account(BankAccount)\IBAN'.</span></span>
52. <span data-ttu-id="1e4b7-171">Dans l’arborescence, sélectionnez « Paiements=Transactions\Débiteur\Compte\Code IBAN(IBAN) ».</span><span class="sxs-lookup"><span data-stu-id="1e4b7-171">In the tree, select 'Payments= Transactions\Debtor\Account\IBAN code(IBAN)'.</span></span>
53. <span data-ttu-id="1e4b7-172">Cliquez sur Lier.</span><span class="sxs-lookup"><span data-stu-id="1e4b7-172">Click Bind.</span></span>
54. <span data-ttu-id="1e4b7-173">Dans l’arborescence, sélectionnez « Paiements=Transactions\Débiteur\Compte\Numéro ».</span><span class="sxs-lookup"><span data-stu-id="1e4b7-173">In the tree, select 'Payments= Transactions\Debtor\Account\Number'.</span></span>
55. <span data-ttu-id="1e4b7-174">Dans l’arborescence, sélectionnez « Compte bancaire(BankAccount)\Numéro de compte bancaire(AccountNum) ».</span><span class="sxs-lookup"><span data-stu-id="1e4b7-174">In the tree, select 'Bank Account(BankAccount)\Bank account number(AccountNum)'.</span></span>
56. <span data-ttu-id="1e4b7-175">Cliquez sur Lier.</span><span class="sxs-lookup"><span data-stu-id="1e4b7-175">Click Bind.</span></span>
57. <span data-ttu-id="1e4b7-176">Dans l’arborescence , développez « Paiements=Transactions\Débiteur\Agent ».</span><span class="sxs-lookup"><span data-stu-id="1e4b7-176">In the tree, expand 'Payments= Transactions\Debtor\Agent'.</span></span>
58. <span data-ttu-id="1e4b7-177">Dans l’arborescence, sélectionnez « Paiements=Transactions\Débiteur\Agent\Nom ».</span><span class="sxs-lookup"><span data-stu-id="1e4b7-177">In the tree, select 'Payments= Transactions\Debtor\Agent\Name'.</span></span>
59. <span data-ttu-id="1e4b7-178">Dans l’arborescence, sélectionnez « Compte bancaire(BankAccount)\Nom ».</span><span class="sxs-lookup"><span data-stu-id="1e4b7-178">In the tree, select 'Bank Account(BankAccount)\Name'.</span></span>
60. <span data-ttu-id="1e4b7-179">Cliquez sur Lier.</span><span class="sxs-lookup"><span data-stu-id="1e4b7-179">Click Bind.</span></span>
61. <span data-ttu-id="1e4b7-180">Dans l’arborescence, sélectionnez « Paiements=Transactions\Débiteur\Agent\Numéro de routage(RoutingNumber) ».</span><span class="sxs-lookup"><span data-stu-id="1e4b7-180">In the tree, select 'Payments= Transactions\Debtor\Agent\Routing number(RoutingNumber)'.</span></span>
62. <span data-ttu-id="1e4b7-181">Dans l’arborescence, sélectionnez « Compte bancaire(BankAccount)\Numéro de routage(RegistrationNum) ».</span><span class="sxs-lookup"><span data-stu-id="1e4b7-181">In the tree, select 'Bank Account(BankAccount)\Routing number(RegistrationNum)'.</span></span>
63. <span data-ttu-id="1e4b7-182">Cliquez sur Lier.</span><span class="sxs-lookup"><span data-stu-id="1e4b7-182">Click Bind.</span></span>
64. <span data-ttu-id="1e4b7-183">Dans l’arborescence, sélectionnez « Paiements=Transactions\Débiteur\Agent\Code SWIFT(SWIFT) ».</span><span class="sxs-lookup"><span data-stu-id="1e4b7-183">In the tree, select 'Payments= Transactions\Debtor\Agent\SWIFT code(SWIFT)'.</span></span>
65. <span data-ttu-id="1e4b7-184">Dans l’arborescence, sélectionnez « Compte bancaire(BankAccount)\Code SWIFT(SWIFTNo) ».</span><span class="sxs-lookup"><span data-stu-id="1e4b7-184">In the tree, select 'Bank Account(BankAccount)\SWIFT code(SWIFTNo)'.</span></span>
66. <span data-ttu-id="1e4b7-185">Cliquez sur Lier.</span><span class="sxs-lookup"><span data-stu-id="1e4b7-185">Click Bind.</span></span>
67. <span data-ttu-id="1e4b7-186">Dans l’arborescence, sélectionnez « Paiements=Transactions\Débiteur\Nom ».</span><span class="sxs-lookup"><span data-stu-id="1e4b7-186">In the tree, select 'Payments= Transactions\Debtor\Name'.</span></span>
68. <span data-ttu-id="1e4b7-187">Dans l’arborescence, sélectionnez « Informations sur la société(Company) ».</span><span class="sxs-lookup"><span data-stu-id="1e4b7-187">In the tree, select 'Company information(Company)'.</span></span>
69. <span data-ttu-id="1e4b7-188">Dans l’arborescence, développez « Informations sur la société(Company) ».</span><span class="sxs-lookup"><span data-stu-id="1e4b7-188">In the tree, expand 'Company information(Company)'.</span></span>
70. <span data-ttu-id="1e4b7-189">Dans l’arborescence, sélectionnez « Informations sur la société(Company)\Nom ».</span><span class="sxs-lookup"><span data-stu-id="1e4b7-189">In the tree, select 'Company information(Company)\Name'.</span></span>
71. <span data-ttu-id="1e4b7-190">Cliquez sur Lier.</span><span class="sxs-lookup"><span data-stu-id="1e4b7-190">Click Bind.</span></span>
72. <span data-ttu-id="1e4b7-191">Dans l’arborescence, sélectionnez « Paiements=Transactions\Description ».</span><span class="sxs-lookup"><span data-stu-id="1e4b7-191">In the tree, select 'Payments= Transactions\Description'.</span></span>
73. <span data-ttu-id="1e4b7-192">Dans l’arborescence, sélectionnez « Transactions\Description(Txt) ».</span><span class="sxs-lookup"><span data-stu-id="1e4b7-192">In the tree, select 'Transactions\Description(Txt)'.</span></span>
74. <span data-ttu-id="1e4b7-193">Cliquez sur Lier.</span><span class="sxs-lookup"><span data-stu-id="1e4b7-193">Click Bind.</span></span>
75. <span data-ttu-id="1e4b7-194">Dans l’arborescence, sélectionnez « Transactions \Code d’identification de bout en bout(End2EndID) ».</span><span class="sxs-lookup"><span data-stu-id="1e4b7-194">In the tree, select 'Payments= Transactions\End to end identification code(End2EndID)'.</span></span>
76. <span data-ttu-id="1e4b7-195">Dans l’arborescence, sélectionnez « Transactions\$EndToEndID ».</span><span class="sxs-lookup"><span data-stu-id="1e4b7-195">In the tree, select 'Transactions\$EndToEndID'.</span></span>
77. <span data-ttu-id="1e4b7-196">Cliquez sur Lier.</span><span class="sxs-lookup"><span data-stu-id="1e4b7-196">Click Bind.</span></span>
78. <span data-ttu-id="1e4b7-197">Dans l’arborescence, sélectionnez « Transactions\Montant instruit(InstructedAmount) ».</span><span class="sxs-lookup"><span data-stu-id="1e4b7-197">In the tree, select 'Payments= Transactions\Instructed amount(InstructedAmount)'.</span></span>
79. <span data-ttu-id="1e4b7-198">Dans l’arborescence, sélectionnez « Transactions\$Amount ».</span><span class="sxs-lookup"><span data-stu-id="1e4b7-198">In the tree, select 'Transactions\$Amount'.</span></span>
80. <span data-ttu-id="1e4b7-199">Cliquez sur Lier.</span><span class="sxs-lookup"><span data-stu-id="1e4b7-199">Click Bind.</span></span>
81. <span data-ttu-id="1e4b7-200">Dans l’arborescence, sélectionnez « Transactions\Date de transaction(TransactionDate) ».</span><span class="sxs-lookup"><span data-stu-id="1e4b7-200">In the tree, select 'Payments= Transactions\Transaction date(TransactionDate)'.</span></span>
82. <span data-ttu-id="1e4b7-201">Dans l’arborescence, sélectionnez « Transactions\Date(TransDate) ».</span><span class="sxs-lookup"><span data-stu-id="1e4b7-201">In the tree, select 'Transactions\Date(TransDate)'.</span></span>
83. <span data-ttu-id="1e4b7-202">Cliquez sur Lier.</span><span class="sxs-lookup"><span data-stu-id="1e4b7-202">Click Bind.</span></span>

## <a name="validate-created-mapping"></a><span data-ttu-id="1e4b7-203">Valider une mise en correspondance créée</span><span class="sxs-lookup"><span data-stu-id="1e4b7-203">Validate created mapping</span></span>
1. <span data-ttu-id="1e4b7-204">Cliquez sur Valider.</span><span class="sxs-lookup"><span data-stu-id="1e4b7-204">Click Validate.</span></span>
    * <span data-ttu-id="1e4b7-205">Validez la nouvelle mise en correspondance pour vous assurer que toutes les liaisons sont correctes.</span><span class="sxs-lookup"><span data-stu-id="1e4b7-205">Validate the new mapping to ensure that all bindings are okay.</span></span>  
2. <span data-ttu-id="1e4b7-206">Cliquez sur la flèche pour développer ou réduire la section Liste des erreurs.</span><span class="sxs-lookup"><span data-stu-id="1e4b7-206">Click the arrow to expand or collapse the Error List section.</span></span>
3. <span data-ttu-id="1e4b7-207">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="1e4b7-207">Click Save.</span></span>
4. <span data-ttu-id="1e4b7-208">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="1e4b7-208">Close the page.</span></span>
5. <span data-ttu-id="1e4b7-209">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="1e4b7-209">Close the page.</span></span>
6. <span data-ttu-id="1e4b7-210">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="1e4b7-210">Close the page.</span></span>

## <a name="change-the-status-of-the-current-version-of-model-configuration"></a><span data-ttu-id="1e4b7-211">Modifier le statut de la version actuelle de la configuration du modèle</span><span class="sxs-lookup"><span data-stu-id="1e4b7-211">Change the status of the current version of model configuration</span></span>
1. <span data-ttu-id="1e4b7-212">Cliquez sur Modifier le statut.</span><span class="sxs-lookup"><span data-stu-id="1e4b7-212">Click Change status.</span></span>
    * <span data-ttu-id="1e4b7-213">Modifiez le statut de la configuration du modèle conçue : remplacez Brouillon par Terminé pour le rendre disponible pour la conception de format de paiement.</span><span class="sxs-lookup"><span data-stu-id="1e4b7-213">Change the status of designed model configuration – from Draft to Completed to make it available for payment format design.</span></span>  
2. <span data-ttu-id="1e4b7-214">Cliquez sur Terminé.</span><span class="sxs-lookup"><span data-stu-id="1e4b7-214">Click Complete.</span></span>
    * <span data-ttu-id="1e4b7-215">Sélectionnez Terminer.</span><span class="sxs-lookup"><span data-stu-id="1e4b7-215">Select Complete.</span></span>  
3. <span data-ttu-id="1e4b7-216">Dans le champ Description, entrez une valeur.</span><span class="sxs-lookup"><span data-stu-id="1e4b7-216">In the Description field, type a value.</span></span>
    * <span data-ttu-id="1e4b7-217">Par exemple, « version 1 ».</span><span class="sxs-lookup"><span data-stu-id="1e4b7-217">For example, 'version 1'.</span></span>  
4. <span data-ttu-id="1e4b7-218">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="1e4b7-218">Click OK.</span></span>
5. <span data-ttu-id="1e4b7-219">Sélectionnez la version terminée de la configuration actuelle.</span><span class="sxs-lookup"><span data-stu-id="1e4b7-219">Select the completed version of the current configuration.</span></span>
    * <span data-ttu-id="1e4b7-220">Notez que la configuration créée est enregistrée comme version 1 terminée.</span><span class="sxs-lookup"><span data-stu-id="1e4b7-220">Note that the created configuration is saved as completed version 1.</span></span>  



[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]