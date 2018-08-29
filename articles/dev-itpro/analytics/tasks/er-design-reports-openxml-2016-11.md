--- 
title: "Créer des configurations de gestion d'états électroniques pour générer des états au format OpenXML"
description: "Les étapes suivantes expliquent comment un utilisateur dont le rôle est Administrateur système ou Développeur d'états électroniques peut créer une configuration de format pour la génération d'états électronique (ER) qui contient un modèle pour générer des documents électroniques au format OPENXML."
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
ms.sourcegitcommit: e782d33f3748524491dace28008cd9148ae70529
ms.openlocfilehash: b42cfe36c57a9526e585bbad0fcd31ff60b90397
ms.contentlocale: fr-fr
ms.lasthandoff: 08/08/2018

---
# <a name="design-er-configurations-to-generate-reports-in-openxml-format"></a><span data-ttu-id="57289-103">Créer des configurations de gestion d'états électroniques pour générer des états au format OpenXML</span><span class="sxs-lookup"><span data-stu-id="57289-103">Design ER configurations to generate reports in OpenXML format</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="57289-104">Les étapes suivantes expliquent comment un utilisateur dont le rôle est Administrateur système ou Développeur d'états électroniques peut créer une configuration de format pour la génération d'états électronique (ER) qui contient un modèle pour générer des documents électroniques au format OPENXML.</span><span class="sxs-lookup"><span data-stu-id="57289-104">The following steps explain how a user in the System Administrator or Electronic Reporting Developer role can create a new Electronic reporting (ER) configuration that contains a template for generating electronic documents in OPENXML format.</span></span> <span data-ttu-id="57289-105">Cette configuration sera utilisée pour traiter les paiements fournisseur.</span><span class="sxs-lookup"><span data-stu-id="57289-105">This configuration will be used for processing vendor payments.</span></span>



<span data-ttu-id="57289-106">Dans cet exemple, vous allez créer une configuration pour la société témoin, Litware, Inc. Ces étapes peuvent être effectuées dans la société GBSI.</span><span class="sxs-lookup"><span data-stu-id="57289-106">In this example, you will create a configuration for sample company, Litware, Inc. These steps can be performed in GBSI company.</span></span>



<span data-ttu-id="57289-107">Pour effectuer ces étapes, vous devez commencer par effectuer les étapes de la procédure « Créer un fournisseur de configuration et le marquer comme actif ».</span><span class="sxs-lookup"><span data-stu-id="57289-107">To complete these steps, you must first complete the steps in the “Create a configuration provider and mark it as active” procedure.</span></span> <span data-ttu-id="57289-108">Vous devez également télécharger et enregistrer le fichier Microsoft Excel [Modèle d'état de paiement](https://go.microsoft.com/fwlink/?linkid=862266).</span><span class="sxs-lookup"><span data-stu-id="57289-108">You must also download and save the Microsoft Excel file, [Template of Payment Report](https://go.microsoft.com/fwlink/?linkid=862266).</span></span> 

## <a name="upload-the-payments-data-model-configuration"></a><span data-ttu-id="57289-109">Téléchargez la configuration du modèle de données des paiements</span><span class="sxs-lookup"><span data-stu-id="57289-109">Upload the Payments data model configuration</span></span>
1. <span data-ttu-id="57289-110">Accédez à Administration d'organisation > Espaces de travail > États électroniques.</span><span class="sxs-lookup"><span data-stu-id="57289-110">Go to Organization administration > Workspaces > Electronic reporting.</span></span>
2. <span data-ttu-id="57289-111">Dans la liste, marquez la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="57289-111">In the list, mark the selected row.</span></span>
    * <span data-ttu-id="57289-112">Sélectionnez le fournisseur de configuration pour la société fictive Litware, Inc. Si vous ne voyez pas ce fournisseur de configuration, vous devez d'abord effectuer les étapes de la procédure « Créer un fournisseur de configuration et le marquer comme actif ».</span><span class="sxs-lookup"><span data-stu-id="57289-112">Select the configuration provider for sample company, Litware, Inc. If you don’t see this configuration provider, you must first complete the steps in the “Create a configuration provider and mark it as active” procedure.</span></span>  
3. <span data-ttu-id="57289-113">Cliquez sur Activer.</span><span class="sxs-lookup"><span data-stu-id="57289-113">Click Set active.</span></span>
4. <span data-ttu-id="57289-114">Cliquez sur Référentiels.</span><span class="sxs-lookup"><span data-stu-id="57289-114">Click Repositories.</span></span>
    * <span data-ttu-id="57289-115">Sélectionnez un référentiel pour le type de ressources opérationnelles, si disponible.</span><span class="sxs-lookup"><span data-stu-id="57289-115">Select a repository for the Operations Resources type, if available.</span></span> <span data-ttu-id="57289-116">S'il n'est pas disponible, ignorez les étapes suivantes sur la création d'un référentiel.</span><span class="sxs-lookup"><span data-stu-id="57289-116">If its available, skip the following steps about creating a new repository.</span></span>  
5. <span data-ttu-id="57289-117">Cliquez sur Ajouter pour ouvrir la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="57289-117">Click Add to open the drop dialog.</span></span>
6. <span data-ttu-id="57289-118">Dans le champ Type du référentiel de configuration, entrez « Ressources opérationnelles ».</span><span class="sxs-lookup"><span data-stu-id="57289-118">In the Configuration repository type field, enter 'Operations resources'.</span></span>
7. <span data-ttu-id="57289-119">Cliquez sur Créer un référentiel.</span><span class="sxs-lookup"><span data-stu-id="57289-119">Click Create repository.</span></span>
8. <span data-ttu-id="57289-120">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="57289-120">Click OK.</span></span>
9. <span data-ttu-id="57289-121">Cliquez sur Ouvrir.</span><span class="sxs-lookup"><span data-stu-id="57289-121">Click Open.</span></span>
10. <span data-ttu-id="57289-122">Dans l'arborescence, sélectionnez « Modèle de paiement ».</span><span class="sxs-lookup"><span data-stu-id="57289-122">In the tree, select 'Payment model'.</span></span>
11. <span data-ttu-id="57289-123">Cliquez sur Importer.</span><span class="sxs-lookup"><span data-stu-id="57289-123">Click Import.</span></span>
    * <span data-ttu-id="57289-124">Importez ce modèle de données.</span><span class="sxs-lookup"><span data-stu-id="57289-124">Import this data model.</span></span> <span data-ttu-id="57289-125">Il est utilisé comme source de données dans une nouvelle configuration de format.</span><span class="sxs-lookup"><span data-stu-id="57289-125">It will be used as a data source in a new format configuration.</span></span> <span data-ttu-id="57289-126">Ignorez cette étape si cette configuration a déjà été importée.</span><span class="sxs-lookup"><span data-stu-id="57289-126">Skip this step if this configuration has been already imported.</span></span>  
12. <span data-ttu-id="57289-127">Cliquez sur Oui.</span><span class="sxs-lookup"><span data-stu-id="57289-127">Click Yes.</span></span>
13. <span data-ttu-id="57289-128">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="57289-128">Close the page.</span></span>
14. <span data-ttu-id="57289-129">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="57289-129">Close the page.</span></span>

## <a name="create-a-new-format-configuration"></a><span data-ttu-id="57289-130">Créer une configuration de format</span><span class="sxs-lookup"><span data-stu-id="57289-130">Create a new format configuration</span></span>
1. <span data-ttu-id="57289-131">Cliquez sur Configurations des états.</span><span class="sxs-lookup"><span data-stu-id="57289-131">Click Reporting configurations.</span></span>
2. <span data-ttu-id="57289-132">Dans l'arborescence, sélectionnez « Modèle de paiement ».</span><span class="sxs-lookup"><span data-stu-id="57289-132">In the tree, select 'Payment model'.</span></span>
3. <span data-ttu-id="57289-133">Cliquez sur Créer la configuration pour ouvrir la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="57289-133">Click Create configuration to open the drop dialog.</span></span>
4. <span data-ttu-id="57289-134">Dans le champ Nouveau, entrez « Format basé sur le PaymentModel du modèle du paiement ».</span><span class="sxs-lookup"><span data-stu-id="57289-134">In the New field, enter 'Format based on data model PaymentModel'.</span></span>
    * <span data-ttu-id="57289-135">Créez un format basé sur le modèle de données PaymentModel.</span><span class="sxs-lookup"><span data-stu-id="57289-135">Create a format that is based on the PaymentModel data model.</span></span>  
5. <span data-ttu-id="57289-136">Tapez Exemple d'état sur les feuilles de calcul dans le champ Nom.</span><span class="sxs-lookup"><span data-stu-id="57289-136">In the Name field, type 'Sample worksheet report'.</span></span>
    * <span data-ttu-id="57289-137">Exemple d'état sur les feuilles de calcul</span><span class="sxs-lookup"><span data-stu-id="57289-137">Sample worksheet report</span></span>  
6. <span data-ttu-id="57289-138">Entrez « Exemple d'état sur les feuilles de calcul pour les paiements fournisseurs » dans le champ Description.</span><span class="sxs-lookup"><span data-stu-id="57289-138">In the Description field, type 'Sample worksheet report for vendors’ payments'.</span></span>
    * <span data-ttu-id="57289-139">Exemple d'état sur les feuilles de calcul pour les paiements fournisseurs.</span><span class="sxs-lookup"><span data-stu-id="57289-139">Sample worksheet report for vendors’ payments.</span></span>  
7. <span data-ttu-id="57289-140">Dans le champ Définition du modèle de données, entrez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="57289-140">In the Data model definition field, enter or select a value.</span></span>
    * <span data-ttu-id="57289-141">Sélectionnez la définition « CustomerCreditTransferInitiation ».</span><span class="sxs-lookup"><span data-stu-id="57289-141">Select the 'CustomerCreditTransferInitiation' definition.</span></span>  
8. <span data-ttu-id="57289-142">Cliquez sur Créer une configuration.</span><span class="sxs-lookup"><span data-stu-id="57289-142">Click Create configuration.</span></span>

## <a name="design-a-new-document-in-openxml-worksheet-format"></a><span data-ttu-id="57289-143">Créez un document dans le format de la feuille de calcul OPENXML</span><span class="sxs-lookup"><span data-stu-id="57289-143">Design a new document in OPENXML worksheet format</span></span>
1. <span data-ttu-id="57289-144">Sélectionnez Modèle de paiement\Exemple d'état sur les feuilles de calcul dans l'arborescence.</span><span class="sxs-lookup"><span data-stu-id="57289-144">In the tree, select 'Payment model\Sample worksheet report'.</span></span>
2. <span data-ttu-id="57289-145">Cliquez sur Concepteur.</span><span class="sxs-lookup"><span data-stu-id="57289-145">Click Designer.</span></span>
3. <span data-ttu-id="57289-146">Cliquez sur Importer dans le volet Actions.</span><span class="sxs-lookup"><span data-stu-id="57289-146">On the Action Pane, click Import.</span></span>
4. <span data-ttu-id="57289-147">Cliquez sur Importer depuis Excel.</span><span class="sxs-lookup"><span data-stu-id="57289-147">Click Import from Excel.</span></span>
5. <span data-ttu-id="57289-148">Cliquez sur Documents joints.</span><span class="sxs-lookup"><span data-stu-id="57289-148">Click Attachments.</span></span>
    * <span data-ttu-id="57289-149">Joignez le document Excel existant comme modèle.</span><span class="sxs-lookup"><span data-stu-id="57289-149">Attach the existing Excel document as a template.</span></span>  
6. <span data-ttu-id="57289-150">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="57289-150">Click New.</span></span>
7. <span data-ttu-id="57289-151">Cliquez sur Fichier.</span><span class="sxs-lookup"><span data-stu-id="57289-151">Click File.</span></span>
    * <span data-ttu-id="57289-152">Pointez vers le fichier Excel existant.</span><span class="sxs-lookup"><span data-stu-id="57289-152">Point to the existing Excel file.</span></span>  
8. <span data-ttu-id="57289-153">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="57289-153">Close the page.</span></span>
9. <span data-ttu-id="57289-154">Dans le champ Modèle, entrez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="57289-154">In the Template field, enter or select a value.</span></span>
    * <span data-ttu-id="57289-155">Sélectionnez le fichier Excel à utiliser comme modèle.</span><span class="sxs-lookup"><span data-stu-id="57289-155">Select the attached Excel file to be used as a template.</span></span>  
10. <span data-ttu-id="57289-156">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="57289-156">Click OK.</span></span>
    * <span data-ttu-id="57289-157">Notez que les composants de format ER ont été créés dans le format de conception basé sur la structure du document MS Excel de référence (plages nommées).</span><span class="sxs-lookup"><span data-stu-id="57289-157">Note that ER format components have been created in the designing format based on the structure of the referring MS Excel document (named ranges).</span></span>  

## <a name="create-a-new-data-source-to-calculate-totals-by-currency-codes"></a><span data-ttu-id="57289-158">Créer une nouvelle source de données pour calculer les totaux par codes devise</span><span class="sxs-lookup"><span data-stu-id="57289-158">Create a new data source to calculate totals by currency codes</span></span>
1. <span data-ttu-id="57289-159">Cliquez sur l'onglet Mise en relation.</span><span class="sxs-lookup"><span data-stu-id="57289-159">Click the Mapping tab.</span></span>
2. <span data-ttu-id="57289-160">Cliquez sur Ajouter racine pour ouvrir la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="57289-160">Click Add root to open the drop dialog.</span></span>
3. <span data-ttu-id="57289-161">Dans l'arborescence, sélectionnez Fonctions\Grouper par.</span><span class="sxs-lookup"><span data-stu-id="57289-161">In the tree, select 'Functions\Group by'.</span></span>
4. <span data-ttu-id="57289-162">Entrez PaymentByCurrency dans le champ Nom.</span><span class="sxs-lookup"><span data-stu-id="57289-162">In the Name field, type 'PaymentByCurrency'.</span></span>
    * <span data-ttu-id="57289-163">PaymentByCurrency</span><span class="sxs-lookup"><span data-stu-id="57289-163">PaymentByCurrency</span></span>  
5. <span data-ttu-id="57289-164">Cliquez sur Modifier le groupe par.</span><span class="sxs-lookup"><span data-stu-id="57289-164">Click Edit group by.</span></span>
6. <span data-ttu-id="57289-165">Dans l'arborescence , développez « model ».</span><span class="sxs-lookup"><span data-stu-id="57289-165">In the tree, expand 'model'.</span></span>
7. <span data-ttu-id="57289-166">Dans l'arborescence, sélectionnez model\Payments.</span><span class="sxs-lookup"><span data-stu-id="57289-166">In the tree, select 'model\Payments'.</span></span>
8. <span data-ttu-id="57289-167">Cliquez sur Ajouter le champ à.</span><span class="sxs-lookup"><span data-stu-id="57289-167">Click Add field to.</span></span>
9. <span data-ttu-id="57289-168">Cliquez sur Éléments à grouper.</span><span class="sxs-lookup"><span data-stu-id="57289-168">Click What to group.</span></span>
10. <span data-ttu-id="57289-169">Dans l'arborescence, développez model\Payments.</span><span class="sxs-lookup"><span data-stu-id="57289-169">In the tree, expand 'model\Payments'.</span></span>
11. <span data-ttu-id="57289-170">Dans l'arborescence, sélectionnez modèle\Paiements\Devise.</span><span class="sxs-lookup"><span data-stu-id="57289-170">In the tree, select 'model\Payments\Currency'.</span></span>
12. <span data-ttu-id="57289-171">Cliquez sur Ajouter le champ à.</span><span class="sxs-lookup"><span data-stu-id="57289-171">Click Add field to.</span></span>
13. <span data-ttu-id="57289-172">Cliquez sur Champs groupés.</span><span class="sxs-lookup"><span data-stu-id="57289-172">Click Grouped fields.</span></span>
14. <span data-ttu-id="57289-173">Dans l'arborescence, sélectionnez modèle\Paiements\Montant ordonné.</span><span class="sxs-lookup"><span data-stu-id="57289-173">In the tree, select 'model\Payments\Instructed Amount(InstructedAmount)'.</span></span>
15. <span data-ttu-id="57289-174">Cliquez sur Ajouter le champ à.</span><span class="sxs-lookup"><span data-stu-id="57289-174">Click Add field to.</span></span>
16. <span data-ttu-id="57289-175">Cliquez sur Champs d'agrégation.</span><span class="sxs-lookup"><span data-stu-id="57289-175">Click Aggregation fields.</span></span>
17. <span data-ttu-id="57289-176">Sélectionnez une option dans le champ Méthode.</span><span class="sxs-lookup"><span data-stu-id="57289-176">In the Method field, select an option.</span></span>
    * <span data-ttu-id="57289-177">Sélectionnez la fonction d'agrégation SOMME.</span><span class="sxs-lookup"><span data-stu-id="57289-177">Select the SUM aggregation function.</span></span>  
18. <span data-ttu-id="57289-178">Dans le champ Nom, tapez TotalInstructuredAmount.</span><span class="sxs-lookup"><span data-stu-id="57289-178">In the Name field, type 'TotalInstructuredAmount'.</span></span>
    * <span data-ttu-id="57289-179">TotalInstructuredAmount</span><span class="sxs-lookup"><span data-stu-id="57289-179">TotalInstructuredAmount</span></span>  
19. <span data-ttu-id="57289-180">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="57289-180">Click Save.</span></span>
20. <span data-ttu-id="57289-181">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="57289-181">Close the page.</span></span>
21. <span data-ttu-id="57289-182">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="57289-182">Click OK.</span></span>

## <a name="map-format-components-to-data-sources"></a><span data-ttu-id="57289-183">Mettre en correspondance des composants de format vers des sources de données</span><span class="sxs-lookup"><span data-stu-id="57289-183">Map format components to data sources</span></span>
1. <span data-ttu-id="57289-184">Dans l'arborescence , développez « model ».</span><span class="sxs-lookup"><span data-stu-id="57289-184">In the tree, expand 'model'.</span></span>
2. <span data-ttu-id="57289-185">Dans l'arborescence, développez model\Payments.</span><span class="sxs-lookup"><span data-stu-id="57289-185">In the tree, expand 'model\Payments'.</span></span>
3. <span data-ttu-id="57289-186">Dans l'arborescence, développez modèle\Paiements\Partie qui prend l'initiative.</span><span class="sxs-lookup"><span data-stu-id="57289-186">In the tree, expand 'model\Payments\Initiating Party(InitiatingParty)'.</span></span>
4. <span data-ttu-id="57289-187">Dans l'arborescence, sélectionnez modèle\Paiements\Partie qui prend l'initiative\Nom.</span><span class="sxs-lookup"><span data-stu-id="57289-187">In the tree, select 'model\Payments\Initiating Party(InitiatingParty)\Name'.</span></span>
5. <span data-ttu-id="57289-188">Dans l'arborescence, développez ou réduisez « Excel\ReportHeader ».</span><span class="sxs-lookup"><span data-stu-id="57289-188">In the tree, expand 'Excel\ReportHeader'.</span></span>
6. <span data-ttu-id="57289-189">Dans l'arborescence, sélectionnez « Excel\ReportHeader\CompanyName ».</span><span class="sxs-lookup"><span data-stu-id="57289-189">In the tree, select 'Excel\ReportHeader\CompanyName'.</span></span>
7. <span data-ttu-id="57289-190">Cliquez sur Lier.</span><span class="sxs-lookup"><span data-stu-id="57289-190">Click Bind.</span></span>
8. <span data-ttu-id="57289-191">Dans l'arborescence , développez « modèle\Paiements\Créditeur ».</span><span class="sxs-lookup"><span data-stu-id="57289-191">In the tree, expand 'model\Payments\Creditor'.</span></span>
9. <span data-ttu-id="57289-192">Dans l'arborescence , développez modèle\Paiements\Créancier\Identification.</span><span class="sxs-lookup"><span data-stu-id="57289-192">In the tree, expand 'model\Payments\Creditor\Identification'.</span></span>
10. <span data-ttu-id="57289-193">Dans l'arborescence, sélectionnez modèle\Paiements\Créancier\Identification\Source ID(SourceID).</span><span class="sxs-lookup"><span data-stu-id="57289-193">In the tree, select 'model\Payments\Creditor\Identification\Source ID(SourceID)'.</span></span>
11. <span data-ttu-id="57289-194">Dans l'arborescence, développez « Excel\PaymLines ».</span><span class="sxs-lookup"><span data-stu-id="57289-194">In the tree, expand 'Excel\PaymLines'.</span></span>
12. <span data-ttu-id="57289-195">Dans l'arborescence, sélectionnez « Excel\PaymLines\VendAccountName ».</span><span class="sxs-lookup"><span data-stu-id="57289-195">In the tree, select 'Excel\PaymLines\VendAccountName'.</span></span>
13. <span data-ttu-id="57289-196">Cliquez sur Lier.</span><span class="sxs-lookup"><span data-stu-id="57289-196">Click Bind.</span></span>
14. <span data-ttu-id="57289-197">Dans l'arborescence, sélectionnez « modèle\Paiements\Créditeur\Nom ».</span><span class="sxs-lookup"><span data-stu-id="57289-197">In the tree, select 'model\Payments\Creditor\Name'.</span></span>
15. <span data-ttu-id="57289-198">Dans l'arborescence, sélectionnez « Excel\PaymLines\VendName ».</span><span class="sxs-lookup"><span data-stu-id="57289-198">In the tree, select 'Excel\PaymLines\VendName'.</span></span>
16. <span data-ttu-id="57289-199">Cliquez sur Lier.</span><span class="sxs-lookup"><span data-stu-id="57289-199">Click Bind.</span></span>
17. <span data-ttu-id="57289-200">Dans l'arborescence , développez modèle\Paiements\Créancier.</span><span class="sxs-lookup"><span data-stu-id="57289-200">In the tree, expand 'model\Payments\Creditor Agent(CreditorAgent)'.</span></span>
18. <span data-ttu-id="57289-201">Dans l'arborescence, sélectionnez modèle\Paiements\Créancier\Nom.</span><span class="sxs-lookup"><span data-stu-id="57289-201">In the tree, select 'model\Payments\Creditor Agent(CreditorAgent)\Name'.</span></span>
19. <span data-ttu-id="57289-202">Dans l'arborescence, sélectionnez « Excel\PaymLines\Banque ».</span><span class="sxs-lookup"><span data-stu-id="57289-202">In the tree, select 'Excel\PaymLines\Bank'.</span></span>
20. <span data-ttu-id="57289-203">Cliquez sur Lier.</span><span class="sxs-lookup"><span data-stu-id="57289-203">Click Bind.</span></span>
21. <span data-ttu-id="57289-204">Dans l'arborescence, sélectionnez modèle\Paiements\Créancier\Numéro d'acheminement.</span><span class="sxs-lookup"><span data-stu-id="57289-204">In the tree, select 'model\Payments\Creditor Agent(CreditorAgent)\Routing Number(RoutingNumber)'.</span></span>
22. <span data-ttu-id="57289-205">Dans l'arborescence, sélectionnez « Excel\PaymLines\RoutingNumber ».</span><span class="sxs-lookup"><span data-stu-id="57289-205">In the tree, select 'Excel\PaymLines\RoutingNumber'.</span></span>
23. <span data-ttu-id="57289-206">Cliquez sur Lier.</span><span class="sxs-lookup"><span data-stu-id="57289-206">Click Bind.</span></span>
24. <span data-ttu-id="57289-207">Dans l'arborescence , développez « model\Payments\Creditor Account(CreditorAccount) ».</span><span class="sxs-lookup"><span data-stu-id="57289-207">In the tree, expand 'model\Payments\Creditor Account(CreditorAccount)'.</span></span>
25. <span data-ttu-id="57289-208">Dans l'arborescence , développez « model\Payments\Creditor Account(CreditorAccount)\Identification ».</span><span class="sxs-lookup"><span data-stu-id="57289-208">In the tree, expand 'model\Payments\Creditor Account(CreditorAccount)\Identification'.</span></span>
26. <span data-ttu-id="57289-209">Dans l'arborescence, sélectionnez modèle\Paiements\Créancier\Identification\Numéro.</span><span class="sxs-lookup"><span data-stu-id="57289-209">In the tree, select 'model\Payments\Creditor Account(CreditorAccount)\Identification\Number'.</span></span>
27. <span data-ttu-id="57289-210">Dans l'arborescence, sélectionnez « Excel\PaymLines\AccountNumber ».</span><span class="sxs-lookup"><span data-stu-id="57289-210">In the tree, select 'Excel\PaymLines\AccountNumber'.</span></span>
28. <span data-ttu-id="57289-211">Cliquez sur Lier.</span><span class="sxs-lookup"><span data-stu-id="57289-211">Click Bind.</span></span>
29. <span data-ttu-id="57289-212">Dans l'arborescence, sélectionnez modèle\Paiements\Montant ordonné.</span><span class="sxs-lookup"><span data-stu-id="57289-212">In the tree, select 'model\Payments\Instructed Amount(InstructedAmount)'.</span></span>
30. <span data-ttu-id="57289-213">Dans l'arborescence, sélectionnez « Excel\PaymLines\Débit ».</span><span class="sxs-lookup"><span data-stu-id="57289-213">In the tree, select 'Excel\PaymLines\Debit'.</span></span>
31. <span data-ttu-id="57289-214">Cliquez sur Lier.</span><span class="sxs-lookup"><span data-stu-id="57289-214">Click Bind.</span></span>
32. <span data-ttu-id="57289-215">Dans l'arborescence , développez « modèle\Paiements\Créditeur ».</span><span class="sxs-lookup"><span data-stu-id="57289-215">In the tree, expand 'model\Payments\Creditor'.</span></span>
33. <span data-ttu-id="57289-216">Dans l'arborescence , développez « model\Payments\Creditor Account(CreditorAccount) ».</span><span class="sxs-lookup"><span data-stu-id="57289-216">In the tree, expand 'model\Payments\Creditor Account(CreditorAccount)'.</span></span>
34. <span data-ttu-id="57289-217">Dans l'arborescence , développez modèle\Paiements\Créancier.</span><span class="sxs-lookup"><span data-stu-id="57289-217">In the tree, expand 'model\Payments\Creditor Agent(CreditorAgent)'.</span></span>
35. <span data-ttu-id="57289-218">Dans l'arborescence, sélectionnez modèle\Paiements\Devise.</span><span class="sxs-lookup"><span data-stu-id="57289-218">In the tree, select 'model\Payments\Currency'.</span></span>
36. <span data-ttu-id="57289-219">Dans l'arborescence, sélectionnez « Excel\PaymLines\Devise ».</span><span class="sxs-lookup"><span data-stu-id="57289-219">In the tree, select 'Excel\PaymLines\Currency'.</span></span>
37. <span data-ttu-id="57289-220">Cliquez sur Lier.</span><span class="sxs-lookup"><span data-stu-id="57289-220">Click Bind.</span></span>
38. <span data-ttu-id="57289-221">Dans l'arborescence, développez PaymentByCurrency.</span><span class="sxs-lookup"><span data-stu-id="57289-221">In the tree, expand 'PaymentByCurrency'.</span></span>
39. <span data-ttu-id="57289-222">Dans l'arborescence, développez PaymentByCurrency\groupé.</span><span class="sxs-lookup"><span data-stu-id="57289-222">In the tree, expand 'PaymentByCurrency\grouped'.</span></span>
40. <span data-ttu-id="57289-223">Dans l'arborescence, sélectionnez PaymentByCurrency\groupé\Devise.</span><span class="sxs-lookup"><span data-stu-id="57289-223">In the tree, select 'PaymentByCurrency\grouped\Currency'.</span></span>
41. <span data-ttu-id="57289-224">Dans l'arborescence, développez « Excel\SummaryLines ».</span><span class="sxs-lookup"><span data-stu-id="57289-224">In the tree, expand 'Excel\SummaryLines'.</span></span>
42. <span data-ttu-id="57289-225">Dans l'arborescence, sélectionnez « Excel\SummaryLines\SummaryCurrency ».</span><span class="sxs-lookup"><span data-stu-id="57289-225">In the tree, select 'Excel\SummaryLines\SummaryCurrency'.</span></span>
43. <span data-ttu-id="57289-226">Cliquez sur Lier.</span><span class="sxs-lookup"><span data-stu-id="57289-226">Click Bind.</span></span>
44. <span data-ttu-id="57289-227">Dans l'arborescence, développez PaymentByCurrency\agrégé.</span><span class="sxs-lookup"><span data-stu-id="57289-227">In the tree, expand 'PaymentByCurrency\aggregated'.</span></span>
45. <span data-ttu-id="57289-228">Dans l'arborescence, sélectionnez PaymentByCurrency\agrégé\TotalInstructuredAmount.</span><span class="sxs-lookup"><span data-stu-id="57289-228">In the tree, select 'PaymentByCurrency\aggregated\TotalInstructuredAmount'.</span></span>
46. <span data-ttu-id="57289-229">Dans l'arborescence, sélectionnez « Excel\SummaryLines\SummaryAmount ».</span><span class="sxs-lookup"><span data-stu-id="57289-229">In the tree, select 'Excel\SummaryLines\SummaryAmount'.</span></span>
47. <span data-ttu-id="57289-230">Cliquez sur Lier.</span><span class="sxs-lookup"><span data-stu-id="57289-230">Click Bind.</span></span>
48. <span data-ttu-id="57289-231">Sélectionnez PaymentByCurrency.</span><span class="sxs-lookup"><span data-stu-id="57289-231">In the tree, select 'PaymentByCurrency'.</span></span>
49. <span data-ttu-id="57289-232">Dans l'arborescence, sélectionnez « Excel\SummaryLines ».</span><span class="sxs-lookup"><span data-stu-id="57289-232">In the tree, select 'Excel\SummaryLines'.</span></span>
50. <span data-ttu-id="57289-233">Cliquez sur Lier.</span><span class="sxs-lookup"><span data-stu-id="57289-233">Click Bind.</span></span>
51. <span data-ttu-id="57289-234">Dans l'arborescence, sélectionnez model\Payments.</span><span class="sxs-lookup"><span data-stu-id="57289-234">In the tree, select 'model\Payments'.</span></span>
52. <span data-ttu-id="57289-235">Dans l'arborescence, sélectionnez « Excel\PaymLines ».</span><span class="sxs-lookup"><span data-stu-id="57289-235">In the tree, select 'Excel\PaymLines'.</span></span>
53. <span data-ttu-id="57289-236">Cliquez sur Lier.</span><span class="sxs-lookup"><span data-stu-id="57289-236">Click Bind.</span></span>
54. <span data-ttu-id="57289-237">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="57289-237">Click Save.</span></span>
55. <span data-ttu-id="57289-238">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="57289-238">Close the page.</span></span>

## <a name="use-the-created-configuration-for-payments-processing"></a><span data-ttu-id="57289-239">Utiliser la configuration créée pour le traitement des paiements</span><span class="sxs-lookup"><span data-stu-id="57289-239">Use the created configuration for payments processing</span></span>
1. <span data-ttu-id="57289-240">Cliquez sur Modifier le statut.</span><span class="sxs-lookup"><span data-stu-id="57289-240">Click Change status.</span></span>
2. <span data-ttu-id="57289-241">Cliquez sur Terminé.</span><span class="sxs-lookup"><span data-stu-id="57289-241">Click Complete.</span></span>
3. <span data-ttu-id="57289-242">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="57289-242">Click OK.</span></span>
4. <span data-ttu-id="57289-243">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="57289-243">Close the page.</span></span>
5. <span data-ttu-id="57289-244">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="57289-244">Close the page.</span></span>
6. <span data-ttu-id="57289-245">Accédez à Comptabilité fournisseur > Paramétrage des paiements > Modes de paiement.</span><span class="sxs-lookup"><span data-stu-id="57289-245">Go to Accounts payable > Payment setup > Methods of payment.</span></span>
7. <span data-ttu-id="57289-246">Utilisez le filtre rapide pour filtrer selon le champ Mode de paiement avec une valeur de « Électronique ».</span><span class="sxs-lookup"><span data-stu-id="57289-246">Use the Quick Filter to filter on the Method of payment field with a value of 'Electronic'.</span></span>
    * <span data-ttu-id="57289-247">électronique</span><span class="sxs-lookup"><span data-stu-id="57289-247">Electronic</span></span>  
8. <span data-ttu-id="57289-248">Cliquez sur Modifier.</span><span class="sxs-lookup"><span data-stu-id="57289-248">Click Edit.</span></span>
9. <span data-ttu-id="57289-249">Développez la section Formats de fichier.</span><span class="sxs-lookup"><span data-stu-id="57289-249">Expand the File formats section.</span></span>
10. <span data-ttu-id="57289-250">Sélectionnez Oui dans le champ États électroniques génériques.</span><span class="sxs-lookup"><span data-stu-id="57289-250">Select Yes in the Generic electronic reporting field.</span></span>
11. <span data-ttu-id="57289-251">Entrez ou sélectionnez une valeur dans le champ Exporter la configuration du format.</span><span class="sxs-lookup"><span data-stu-id="57289-251">In the Export format configuration field, enter or select a value.</span></span>
    * <span data-ttu-id="57289-252">Sélectionnez la configuration « Exemple d'état sur les feuilles de calcul ».</span><span class="sxs-lookup"><span data-stu-id="57289-252">Select the ‘Sample worksheet report’ configuration.</span></span>  
12. <span data-ttu-id="57289-253">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="57289-253">Click Save.</span></span>
13. <span data-ttu-id="57289-254">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="57289-254">Close the page.</span></span>

## <a name="use-the-created-configuration-for-testing-of-payment-journals-processing"></a><span data-ttu-id="57289-255">Utiliser la configuration créée pour tester le traitement de journaux des paiements</span><span class="sxs-lookup"><span data-stu-id="57289-255">Use the created configuration for testing of payment journals processing</span></span>
1. <span data-ttu-id="57289-256">Accédez à Comptabilité fournisseur > Paiements > Journal des paiements.</span><span class="sxs-lookup"><span data-stu-id="57289-256">Go to Accounts payable > Payments > Payment journal.</span></span>
2. <span data-ttu-id="57289-257">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="57289-257">Click New.</span></span>
    * <span data-ttu-id="57289-258">Créez un journal des paiements.</span><span class="sxs-lookup"><span data-stu-id="57289-258">Create a new payment journal.</span></span>  
3. <span data-ttu-id="57289-259">Dans le champ Nom, tapez « VendPay ».</span><span class="sxs-lookup"><span data-stu-id="57289-259">In the Name field, type 'VendPay'.</span></span>
    * <span data-ttu-id="57289-260">VendPay</span><span class="sxs-lookup"><span data-stu-id="57289-260">VendPay</span></span>  
4. <span data-ttu-id="57289-261">Cliquez sur Lignes.</span><span class="sxs-lookup"><span data-stu-id="57289-261">Click Lines.</span></span>
5. <span data-ttu-id="57289-262">Dans le champ Compte, spécifiez les valeurs GB_SI_000001.</span><span class="sxs-lookup"><span data-stu-id="57289-262">In the Account field, specify the values 'GB_SI_000001'.</span></span>
    * <span data-ttu-id="57289-263">GB_SI_000001</span><span class="sxs-lookup"><span data-stu-id="57289-263">GB_SI_000001</span></span>  
6. <span data-ttu-id="57289-264">Définissez Débit sur 1000.</span><span class="sxs-lookup"><span data-stu-id="57289-264">Set Debit to '1000'.</span></span>
7. <span data-ttu-id="57289-265">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="57289-265">Click New.</span></span>
8. <span data-ttu-id="57289-266">Dans le champ Compte, spécifiez les valeurs GB_SI_000005.</span><span class="sxs-lookup"><span data-stu-id="57289-266">In the Account field, specify the values 'GB_SI_000005'.</span></span>
    * <span data-ttu-id="57289-267">GB_SI_000005</span><span class="sxs-lookup"><span data-stu-id="57289-267">GB_SI_000005</span></span>  
9. <span data-ttu-id="57289-268">Définissez Débit sur 2000.</span><span class="sxs-lookup"><span data-stu-id="57289-268">Set Debit to '2000'.</span></span>
10. <span data-ttu-id="57289-269">Dans le champ Devise, tapez EUR.</span><span class="sxs-lookup"><span data-stu-id="57289-269">In the Currency field, type 'EUR'.</span></span>
    * <span data-ttu-id="57289-270">EUR</span><span class="sxs-lookup"><span data-stu-id="57289-270">EUR</span></span>  
11. <span data-ttu-id="57289-271">Spécifiez les valeurs GBSI OPER dans le champ Compte de contrepartie.</span><span class="sxs-lookup"><span data-stu-id="57289-271">In the Offset account field, specify the values 'GBSI OPER'.</span></span>
    * <span data-ttu-id="57289-272">GBSI OPER</span><span class="sxs-lookup"><span data-stu-id="57289-272">GBSI OPER</span></span>  
12. <span data-ttu-id="57289-273">Tapez Électronique dans le champ Mode de paiement.</span><span class="sxs-lookup"><span data-stu-id="57289-273">In the Method of payment field, type 'Electronic'.</span></span>
    * <span data-ttu-id="57289-274">électronique</span><span class="sxs-lookup"><span data-stu-id="57289-274">Electronic</span></span>  
13. <span data-ttu-id="57289-275">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="57289-275">Click Save.</span></span>
14. <span data-ttu-id="57289-276">Cliquez sur Générer les paiements.</span><span class="sxs-lookup"><span data-stu-id="57289-276">Click Generate payments.</span></span>
15. <span data-ttu-id="57289-277">Tapez Électronique dans le champ Mode de paiement.</span><span class="sxs-lookup"><span data-stu-id="57289-277">In the Method of payment field, type 'Electronic'.</span></span>
    * <span data-ttu-id="57289-278">électronique</span><span class="sxs-lookup"><span data-stu-id="57289-278">Electronic</span></span>  
16. <span data-ttu-id="57289-279">Dans le champ Nom de fichier, tapez « Paiements ».</span><span class="sxs-lookup"><span data-stu-id="57289-279">In the File name field, type 'Payments'.</span></span>
    * <span data-ttu-id="57289-280">Par exemple, tapez Paiements.</span><span class="sxs-lookup"><span data-stu-id="57289-280">For example, type Payments.</span></span>  
17. <span data-ttu-id="57289-281">Tapez GBSI OPER dans le champ Compte bancaire.</span><span class="sxs-lookup"><span data-stu-id="57289-281">In the Bank account field, type 'GBSI OPER'.</span></span>
    * <span data-ttu-id="57289-282">GBSI OPER</span><span class="sxs-lookup"><span data-stu-id="57289-282">GBSI OPER</span></span>  
18. <span data-ttu-id="57289-283">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="57289-283">Click OK.</span></span>
19. <span data-ttu-id="57289-284">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="57289-284">Click OK.</span></span>
    * <span data-ttu-id="57289-285">Examinez la feuille de calcul créée, notamment les détails des lignes de paiement ainsi que les totaux pour chaque code devise utilisé dans ce message de paiement.</span><span class="sxs-lookup"><span data-stu-id="57289-285">Review the created worksheet, including details of payment lines as well as totals for each currency code used in this payment message.</span></span>  


