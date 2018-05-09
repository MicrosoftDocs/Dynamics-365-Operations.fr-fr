--- 
title: "Définir une configuration pour générer des états au format OpenXML pour la gestion des états électroniques (ER)"
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
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: d410e49e2248e503c5935a0d7e95b63a8381a6a8
ms.contentlocale: fr-fr
ms.lasthandoff: 05/08/2018

---
# <a name="design-a-configuration-for-generating-reports-in-openxml-format-for-electronic-reporting-er"></a><span data-ttu-id="b2356-103">Définir une configuration pour générer des états au format OpenXML pour la gestion des états électroniques (ER)</span><span class="sxs-lookup"><span data-stu-id="b2356-103">Design a configuration for generating reports in OpenXML format for electronic reporting (ER)</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="b2356-104">Les étapes suivantes expliquent comment un utilisateur dont le rôle est Administrateur système ou Développeur d'états électroniques peut créer une configuration de format pour la génération d'états électronique (ER) qui contient un modèle pour générer des documents électroniques au format OPENXML.</span><span class="sxs-lookup"><span data-stu-id="b2356-104">The following steps explain how a user in the System Administrator or Electronic Reporting Developer role can create a new Electronic reporting (ER) configuration that contains a template for generating electronic documents in OPENXML format.</span></span> <span data-ttu-id="b2356-105">Cette configuration sera utilisée pour traiter les paiements fournisseur.</span><span class="sxs-lookup"><span data-stu-id="b2356-105">This configuration will be used for processing vendor payments.</span></span>



<span data-ttu-id="b2356-106">Dans cet exemple, vous allez créer une configuration pour la société témoin, Litware, Inc. Ces étapes peuvent être effectuées dans la société GBSI.</span><span class="sxs-lookup"><span data-stu-id="b2356-106">In this example, you will create a configuration for sample company, Litware, Inc. These steps can be performed in GBSI company.</span></span>



<span data-ttu-id="b2356-107">Pour effectuer ces étapes, vous devez commencer par effectuer les étapes de la procédure « Créer un fournisseur de configuration et le marquer comme actif ».</span><span class="sxs-lookup"><span data-stu-id="b2356-107">To complete these steps, you must first complete the steps in the “Create a configuration provider and mark it as active” procedure.</span></span> <span data-ttu-id="b2356-108">Vous devez également télécharger et enregistrer le fichier Microsoft Excel [Modèle d'état de paiement](https://go.microsoft.com/fwlink/?linkid=862266).</span><span class="sxs-lookup"><span data-stu-id="b2356-108">You must also download and save the Microsoft Excel file, [Template of Payment Report](https://go.microsoft.com/fwlink/?linkid=862266).</span></span> 

## <a name="upload-the-payments-data-model-configuration"></a><span data-ttu-id="b2356-109">Téléchargez la configuration du modèle de données des paiements</span><span class="sxs-lookup"><span data-stu-id="b2356-109">Upload the Payments data model configuration</span></span>
1. <span data-ttu-id="b2356-110">Accédez à Administration d'organisation > Espaces de travail > États électroniques.</span><span class="sxs-lookup"><span data-stu-id="b2356-110">Go to Organization administration > Workspaces > Electronic reporting.</span></span>
2. <span data-ttu-id="b2356-111">Dans la liste, marquez la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="b2356-111">In the list, mark the selected row.</span></span>
    * <span data-ttu-id="b2356-112">Sélectionnez le fournisseur de configuration pour la société fictive Litware, Inc. Si vous ne voyez pas ce fournisseur de configuration, vous devez d'abord effectuer les étapes de la procédure « Créer un fournisseur de configuration et le marquer comme actif ».</span><span class="sxs-lookup"><span data-stu-id="b2356-112">Select the configuration provider for sample company, Litware, Inc. If you don’t see this configuration provider, you must first complete the steps in the “Create a configuration provider and mark it as active” procedure.</span></span>  
3. <span data-ttu-id="b2356-113">Cliquez sur Activer.</span><span class="sxs-lookup"><span data-stu-id="b2356-113">Click Set active.</span></span>
4. <span data-ttu-id="b2356-114">Cliquez sur Référentiels.</span><span class="sxs-lookup"><span data-stu-id="b2356-114">Click Repositories.</span></span>
    * <span data-ttu-id="b2356-115">Sélectionnez un référentiel pour le type de ressources opérationnelles, si disponible.</span><span class="sxs-lookup"><span data-stu-id="b2356-115">Select a repository for the Operations Resources type, if available.</span></span> <span data-ttu-id="b2356-116">S'il n'est pas disponible, ignorez les étapes suivantes sur la création d'un référentiel.</span><span class="sxs-lookup"><span data-stu-id="b2356-116">If its available, skip the following steps about creating a new repository.</span></span>  
5. <span data-ttu-id="b2356-117">Cliquez sur Ajouter pour ouvrir la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="b2356-117">Click Add to open the drop dialog.</span></span>
6. <span data-ttu-id="b2356-118">Dans le champ Type du référentiel de configuration, entrez « Ressources opérationnelles ».</span><span class="sxs-lookup"><span data-stu-id="b2356-118">In the Configuration repository type field, enter 'Operations resources'.</span></span>
7. <span data-ttu-id="b2356-119">Cliquez sur Créer un référentiel.</span><span class="sxs-lookup"><span data-stu-id="b2356-119">Click Create repository.</span></span>
8. <span data-ttu-id="b2356-120">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="b2356-120">Click OK.</span></span>
9. <span data-ttu-id="b2356-121">Cliquez sur Ouvrir.</span><span class="sxs-lookup"><span data-stu-id="b2356-121">Click Open.</span></span>
10. <span data-ttu-id="b2356-122">Dans l'arborescence, sélectionnez « Modèle de paiement ».</span><span class="sxs-lookup"><span data-stu-id="b2356-122">In the tree, select 'Payment model'.</span></span>
11. <span data-ttu-id="b2356-123">Cliquez sur Importer.</span><span class="sxs-lookup"><span data-stu-id="b2356-123">Click Import.</span></span>
    * <span data-ttu-id="b2356-124">Importez ce modèle de données.</span><span class="sxs-lookup"><span data-stu-id="b2356-124">Import this data model.</span></span> <span data-ttu-id="b2356-125">Il est utilisé comme source de données dans une nouvelle configuration de format.</span><span class="sxs-lookup"><span data-stu-id="b2356-125">It will be used as a data source in a new format configuration.</span></span> <span data-ttu-id="b2356-126">Ignorez cette étape si cette configuration a déjà été importée.</span><span class="sxs-lookup"><span data-stu-id="b2356-126">Skip this step if this configuration has been already imported.</span></span>  
12. <span data-ttu-id="b2356-127">Cliquez sur Oui.</span><span class="sxs-lookup"><span data-stu-id="b2356-127">Click Yes.</span></span>
13. <span data-ttu-id="b2356-128">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="b2356-128">Close the page.</span></span>
14. <span data-ttu-id="b2356-129">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="b2356-129">Close the page.</span></span>

## <a name="create-a-new-format-configuration"></a><span data-ttu-id="b2356-130">Créer une configuration de format</span><span class="sxs-lookup"><span data-stu-id="b2356-130">Create a new format configuration</span></span>
1. <span data-ttu-id="b2356-131">Cliquez sur Configurations des états.</span><span class="sxs-lookup"><span data-stu-id="b2356-131">Click Reporting configurations.</span></span>
2. <span data-ttu-id="b2356-132">Dans l'arborescence, sélectionnez « Modèle de paiement ».</span><span class="sxs-lookup"><span data-stu-id="b2356-132">In the tree, select 'Payment model'.</span></span>
3. <span data-ttu-id="b2356-133">Cliquez sur Créer la configuration pour ouvrir la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="b2356-133">Click Create configuration to open the drop dialog.</span></span>
4. <span data-ttu-id="b2356-134">Dans le champ Nouveau, entrez « Format basé sur le PaymentModel du modèle du paiement ».</span><span class="sxs-lookup"><span data-stu-id="b2356-134">In the New field, enter 'Format based on data model PaymentModel'.</span></span>
    * <span data-ttu-id="b2356-135">Créez un format basé sur le modèle de données PaymentModel.</span><span class="sxs-lookup"><span data-stu-id="b2356-135">Create a format that is based on the PaymentModel data model.</span></span>  
5. <span data-ttu-id="b2356-136">Tapez Exemple d'état sur les feuilles de calcul dans le champ Nom.</span><span class="sxs-lookup"><span data-stu-id="b2356-136">In the Name field, type 'Sample worksheet report'.</span></span>
    * <span data-ttu-id="b2356-137">Exemple d'état sur les feuilles de calcul</span><span class="sxs-lookup"><span data-stu-id="b2356-137">Sample worksheet report</span></span>  
6. <span data-ttu-id="b2356-138">Entrez « Exemple d'état sur les feuilles de calcul pour les paiements fournisseurs » dans le champ Description.</span><span class="sxs-lookup"><span data-stu-id="b2356-138">In the Description field, type 'Sample worksheet report for vendors’ payments'.</span></span>
    * <span data-ttu-id="b2356-139">Exemple d'état sur les feuilles de calcul pour les paiements fournisseurs.</span><span class="sxs-lookup"><span data-stu-id="b2356-139">Sample worksheet report for vendors’ payments.</span></span>  
7. <span data-ttu-id="b2356-140">Dans le champ Définition du modèle de données, entrez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="b2356-140">In the Data model definition field, enter or select a value.</span></span>
    * <span data-ttu-id="b2356-141">Sélectionnez la définition « CustomerCreditTransferInitiation ».</span><span class="sxs-lookup"><span data-stu-id="b2356-141">Select the 'CustomerCreditTransferInitiation' definition.</span></span>  
8. <span data-ttu-id="b2356-142">Cliquez sur Créer une configuration.</span><span class="sxs-lookup"><span data-stu-id="b2356-142">Click Create configuration.</span></span>

## <a name="design-a-new-document-in-openxml-worksheet-format"></a><span data-ttu-id="b2356-143">Créez un document dans le format de la feuille de calcul OPENXML</span><span class="sxs-lookup"><span data-stu-id="b2356-143">Design a new document in OPENXML worksheet format</span></span>
1. <span data-ttu-id="b2356-144">Sélectionnez Modèle de paiement\Exemple d'état sur les feuilles de calcul dans l'arborescence.</span><span class="sxs-lookup"><span data-stu-id="b2356-144">In the tree, select 'Payment model\Sample worksheet report'.</span></span>
2. <span data-ttu-id="b2356-145">Cliquez sur Concepteur.</span><span class="sxs-lookup"><span data-stu-id="b2356-145">Click Designer.</span></span>
3. <span data-ttu-id="b2356-146">Cliquez sur Importer dans le volet Actions.</span><span class="sxs-lookup"><span data-stu-id="b2356-146">On the Action Pane, click Import.</span></span>
4. <span data-ttu-id="b2356-147">Cliquez sur Importer depuis Excel.</span><span class="sxs-lookup"><span data-stu-id="b2356-147">Click Import from Excel.</span></span>
5. <span data-ttu-id="b2356-148">Cliquez sur Documents joints.</span><span class="sxs-lookup"><span data-stu-id="b2356-148">Click Attachments.</span></span>
    * <span data-ttu-id="b2356-149">Joignez le document Excel existant comme modèle.</span><span class="sxs-lookup"><span data-stu-id="b2356-149">Attach the existing Excel document as a template.</span></span>  
6. <span data-ttu-id="b2356-150">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="b2356-150">Click New.</span></span>
7. <span data-ttu-id="b2356-151">Cliquez sur Fichier.</span><span class="sxs-lookup"><span data-stu-id="b2356-151">Click File.</span></span>
    * <span data-ttu-id="b2356-152">Pointez vers le fichier Excel existant.</span><span class="sxs-lookup"><span data-stu-id="b2356-152">Point to the existing Excel file.</span></span>  
8. <span data-ttu-id="b2356-153">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="b2356-153">Close the page.</span></span>
9. <span data-ttu-id="b2356-154">Dans le champ Modèle, entrez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="b2356-154">In the Template field, enter or select a value.</span></span>
    * <span data-ttu-id="b2356-155">Sélectionnez le fichier Excel à utiliser comme modèle.</span><span class="sxs-lookup"><span data-stu-id="b2356-155">Select the attached Excel file to be used as a template.</span></span>  
10. <span data-ttu-id="b2356-156">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="b2356-156">Click OK.</span></span>
    * <span data-ttu-id="b2356-157">Notez que les composants de format ER ont été créés dans le format de conception basé sur la structure du document MS Excel de référence (plages nommées).</span><span class="sxs-lookup"><span data-stu-id="b2356-157">Note that ER format components have been created in the designing format based on the structure of the referring MS Excel document (named ranges).</span></span>  

## <a name="create-a-new-data-source-to-calculate-totals-by-currency-codes"></a><span data-ttu-id="b2356-158">Créer une nouvelle source de données pour calculer les totaux par codes devise</span><span class="sxs-lookup"><span data-stu-id="b2356-158">Create a new data source to calculate totals by currency codes</span></span>
1. <span data-ttu-id="b2356-159">Cliquez sur l'onglet Mise en relation.</span><span class="sxs-lookup"><span data-stu-id="b2356-159">Click the Mapping tab.</span></span>
2. <span data-ttu-id="b2356-160">Cliquez sur Ajouter racine pour ouvrir la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="b2356-160">Click Add root to open the drop dialog.</span></span>
3. <span data-ttu-id="b2356-161">Dans l'arborescence, sélectionnez Fonctions\Grouper par.</span><span class="sxs-lookup"><span data-stu-id="b2356-161">In the tree, select 'Functions\Group by'.</span></span>
4. <span data-ttu-id="b2356-162">Entrez PaymentByCurrency dans le champ Nom.</span><span class="sxs-lookup"><span data-stu-id="b2356-162">In the Name field, type 'PaymentByCurrency'.</span></span>
    * <span data-ttu-id="b2356-163">PaymentByCurrency</span><span class="sxs-lookup"><span data-stu-id="b2356-163">PaymentByCurrency</span></span>  
5. <span data-ttu-id="b2356-164">Cliquez sur Modifier le groupe par.</span><span class="sxs-lookup"><span data-stu-id="b2356-164">Click Edit group by.</span></span>
6. <span data-ttu-id="b2356-165">Dans l'arborescence , développez « model ».</span><span class="sxs-lookup"><span data-stu-id="b2356-165">In the tree, expand 'model'.</span></span>
7. <span data-ttu-id="b2356-166">Dans l'arborescence, sélectionnez model\Payments.</span><span class="sxs-lookup"><span data-stu-id="b2356-166">In the tree, select 'model\Payments'.</span></span>
8. <span data-ttu-id="b2356-167">Cliquez sur Ajouter le champ à.</span><span class="sxs-lookup"><span data-stu-id="b2356-167">Click Add field to.</span></span>
9. <span data-ttu-id="b2356-168">Cliquez sur Éléments à grouper.</span><span class="sxs-lookup"><span data-stu-id="b2356-168">Click What to group.</span></span>
10. <span data-ttu-id="b2356-169">Dans l'arborescence, développez model\Payments.</span><span class="sxs-lookup"><span data-stu-id="b2356-169">In the tree, expand 'model\Payments'.</span></span>
11. <span data-ttu-id="b2356-170">Dans l'arborescence, sélectionnez modèle\Paiements\Devise.</span><span class="sxs-lookup"><span data-stu-id="b2356-170">In the tree, select 'model\Payments\Currency'.</span></span>
12. <span data-ttu-id="b2356-171">Cliquez sur Ajouter le champ à.</span><span class="sxs-lookup"><span data-stu-id="b2356-171">Click Add field to.</span></span>
13. <span data-ttu-id="b2356-172">Cliquez sur Champs groupés.</span><span class="sxs-lookup"><span data-stu-id="b2356-172">Click Grouped fields.</span></span>
14. <span data-ttu-id="b2356-173">Dans l'arborescence, sélectionnez modèle\Paiements\Montant ordonné.</span><span class="sxs-lookup"><span data-stu-id="b2356-173">In the tree, select 'model\Payments\Instructed Amount(InstructedAmount)'.</span></span>
15. <span data-ttu-id="b2356-174">Cliquez sur Ajouter le champ à.</span><span class="sxs-lookup"><span data-stu-id="b2356-174">Click Add field to.</span></span>
16. <span data-ttu-id="b2356-175">Cliquez sur Champs d'agrégation.</span><span class="sxs-lookup"><span data-stu-id="b2356-175">Click Aggregation fields.</span></span>
17. <span data-ttu-id="b2356-176">Sélectionnez une option dans le champ Méthode.</span><span class="sxs-lookup"><span data-stu-id="b2356-176">In the Method field, select an option.</span></span>
    * <span data-ttu-id="b2356-177">Sélectionnez la fonction d'agrégation SOMME.</span><span class="sxs-lookup"><span data-stu-id="b2356-177">Select the SUM aggregation function.</span></span>  
18. <span data-ttu-id="b2356-178">Dans le champ Nom, tapez TotalInstructuredAmount.</span><span class="sxs-lookup"><span data-stu-id="b2356-178">In the Name field, type 'TotalInstructuredAmount'.</span></span>
    * <span data-ttu-id="b2356-179">TotalInstructuredAmount</span><span class="sxs-lookup"><span data-stu-id="b2356-179">TotalInstructuredAmount</span></span>  
19. <span data-ttu-id="b2356-180">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="b2356-180">Click Save.</span></span>
20. <span data-ttu-id="b2356-181">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="b2356-181">Close the page.</span></span>
21. <span data-ttu-id="b2356-182">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="b2356-182">Click OK.</span></span>

## <a name="map-format-components-to-data-sources"></a><span data-ttu-id="b2356-183">Mettre en correspondance des composants de format vers des sources de données</span><span class="sxs-lookup"><span data-stu-id="b2356-183">Map format components to data sources</span></span>
1. <span data-ttu-id="b2356-184">Dans l'arborescence , développez « model ».</span><span class="sxs-lookup"><span data-stu-id="b2356-184">In the tree, expand 'model'.</span></span>
2. <span data-ttu-id="b2356-185">Dans l'arborescence, développez model\Payments.</span><span class="sxs-lookup"><span data-stu-id="b2356-185">In the tree, expand 'model\Payments'.</span></span>
3. <span data-ttu-id="b2356-186">Dans l'arborescence, développez modèle\Paiements\Partie qui prend l'initiative.</span><span class="sxs-lookup"><span data-stu-id="b2356-186">In the tree, expand 'model\Payments\Initiating Party(InitiatingParty)'.</span></span>
4. <span data-ttu-id="b2356-187">Dans l'arborescence, sélectionnez modèle\Paiements\Partie qui prend l'initiative\Nom.</span><span class="sxs-lookup"><span data-stu-id="b2356-187">In the tree, select 'model\Payments\Initiating Party(InitiatingParty)\Name'.</span></span>
5. <span data-ttu-id="b2356-188">Dans l'arborescence, développez ou réduisez « Excel\ReportHeader ».</span><span class="sxs-lookup"><span data-stu-id="b2356-188">In the tree, expand 'Excel\ReportHeader'.</span></span>
6. <span data-ttu-id="b2356-189">Dans l'arborescence, sélectionnez « Excel\ReportHeader\CompanyName ».</span><span class="sxs-lookup"><span data-stu-id="b2356-189">In the tree, select 'Excel\ReportHeader\CompanyName'.</span></span>
7. <span data-ttu-id="b2356-190">Cliquez sur Lier.</span><span class="sxs-lookup"><span data-stu-id="b2356-190">Click Bind.</span></span>
8. <span data-ttu-id="b2356-191">Dans l'arborescence , développez « modèle\Paiements\Créditeur ».</span><span class="sxs-lookup"><span data-stu-id="b2356-191">In the tree, expand 'model\Payments\Creditor'.</span></span>
9. <span data-ttu-id="b2356-192">Dans l'arborescence , développez modèle\Paiements\Créancier\Identification.</span><span class="sxs-lookup"><span data-stu-id="b2356-192">In the tree, expand 'model\Payments\Creditor\Identification'.</span></span>
10. <span data-ttu-id="b2356-193">Dans l'arborescence, sélectionnez modèle\Paiements\Créancier\Identification\Source ID(SourceID).</span><span class="sxs-lookup"><span data-stu-id="b2356-193">In the tree, select 'model\Payments\Creditor\Identification\Source ID(SourceID)'.</span></span>
11. <span data-ttu-id="b2356-194">Dans l'arborescence, développez « Excel\PaymLines ».</span><span class="sxs-lookup"><span data-stu-id="b2356-194">In the tree, expand 'Excel\PaymLines'.</span></span>
12. <span data-ttu-id="b2356-195">Dans l'arborescence, sélectionnez « Excel\PaymLines\VendAccountName ».</span><span class="sxs-lookup"><span data-stu-id="b2356-195">In the tree, select 'Excel\PaymLines\VendAccountName'.</span></span>
13. <span data-ttu-id="b2356-196">Cliquez sur Lier.</span><span class="sxs-lookup"><span data-stu-id="b2356-196">Click Bind.</span></span>
14. <span data-ttu-id="b2356-197">Dans l'arborescence, sélectionnez « modèle\Paiements\Créditeur\Nom ».</span><span class="sxs-lookup"><span data-stu-id="b2356-197">In the tree, select 'model\Payments\Creditor\Name'.</span></span>
15. <span data-ttu-id="b2356-198">Dans l'arborescence, sélectionnez « Excel\PaymLines\VendName ».</span><span class="sxs-lookup"><span data-stu-id="b2356-198">In the tree, select 'Excel\PaymLines\VendName'.</span></span>
16. <span data-ttu-id="b2356-199">Cliquez sur Lier.</span><span class="sxs-lookup"><span data-stu-id="b2356-199">Click Bind.</span></span>
17. <span data-ttu-id="b2356-200">Dans l'arborescence , développez modèle\Paiements\Créancier.</span><span class="sxs-lookup"><span data-stu-id="b2356-200">In the tree, expand 'model\Payments\Creditor Agent(CreditorAgent)'.</span></span>
18. <span data-ttu-id="b2356-201">Dans l'arborescence, sélectionnez modèle\Paiements\Créancier\Nom.</span><span class="sxs-lookup"><span data-stu-id="b2356-201">In the tree, select 'model\Payments\Creditor Agent(CreditorAgent)\Name'.</span></span>
19. <span data-ttu-id="b2356-202">Dans l'arborescence, sélectionnez « Excel\PaymLines\Banque ».</span><span class="sxs-lookup"><span data-stu-id="b2356-202">In the tree, select 'Excel\PaymLines\Bank'.</span></span>
20. <span data-ttu-id="b2356-203">Cliquez sur Lier.</span><span class="sxs-lookup"><span data-stu-id="b2356-203">Click Bind.</span></span>
21. <span data-ttu-id="b2356-204">Dans l'arborescence, sélectionnez modèle\Paiements\Créancier\Numéro d'acheminement.</span><span class="sxs-lookup"><span data-stu-id="b2356-204">In the tree, select 'model\Payments\Creditor Agent(CreditorAgent)\Routing Number(RoutingNumber)'.</span></span>
22. <span data-ttu-id="b2356-205">Dans l'arborescence, sélectionnez « Excel\PaymLines\RoutingNumber ».</span><span class="sxs-lookup"><span data-stu-id="b2356-205">In the tree, select 'Excel\PaymLines\RoutingNumber'.</span></span>
23. <span data-ttu-id="b2356-206">Cliquez sur Lier.</span><span class="sxs-lookup"><span data-stu-id="b2356-206">Click Bind.</span></span>
24. <span data-ttu-id="b2356-207">Dans l'arborescence , développez « model\Payments\Creditor Account(CreditorAccount) ».</span><span class="sxs-lookup"><span data-stu-id="b2356-207">In the tree, expand 'model\Payments\Creditor Account(CreditorAccount)'.</span></span>
25. <span data-ttu-id="b2356-208">Dans l'arborescence , développez « model\Payments\Creditor Account(CreditorAccount)\Identification ».</span><span class="sxs-lookup"><span data-stu-id="b2356-208">In the tree, expand 'model\Payments\Creditor Account(CreditorAccount)\Identification'.</span></span>
26. <span data-ttu-id="b2356-209">Dans l'arborescence, sélectionnez modèle\Paiements\Créancier\Identification\Numéro.</span><span class="sxs-lookup"><span data-stu-id="b2356-209">In the tree, select 'model\Payments\Creditor Account(CreditorAccount)\Identification\Number'.</span></span>
27. <span data-ttu-id="b2356-210">Dans l'arborescence, sélectionnez « Excel\PaymLines\AccountNumber ».</span><span class="sxs-lookup"><span data-stu-id="b2356-210">In the tree, select 'Excel\PaymLines\AccountNumber'.</span></span>
28. <span data-ttu-id="b2356-211">Cliquez sur Lier.</span><span class="sxs-lookup"><span data-stu-id="b2356-211">Click Bind.</span></span>
29. <span data-ttu-id="b2356-212">Dans l'arborescence, sélectionnez modèle\Paiements\Montant ordonné.</span><span class="sxs-lookup"><span data-stu-id="b2356-212">In the tree, select 'model\Payments\Instructed Amount(InstructedAmount)'.</span></span>
30. <span data-ttu-id="b2356-213">Dans l'arborescence, sélectionnez « Excel\PaymLines\Débit ».</span><span class="sxs-lookup"><span data-stu-id="b2356-213">In the tree, select 'Excel\PaymLines\Debit'.</span></span>
31. <span data-ttu-id="b2356-214">Cliquez sur Lier.</span><span class="sxs-lookup"><span data-stu-id="b2356-214">Click Bind.</span></span>
32. <span data-ttu-id="b2356-215">Dans l'arborescence , développez « modèle\Paiements\Créditeur ».</span><span class="sxs-lookup"><span data-stu-id="b2356-215">In the tree, expand 'model\Payments\Creditor'.</span></span>
33. <span data-ttu-id="b2356-216">Dans l'arborescence , développez « model\Payments\Creditor Account(CreditorAccount) ».</span><span class="sxs-lookup"><span data-stu-id="b2356-216">In the tree, expand 'model\Payments\Creditor Account(CreditorAccount)'.</span></span>
34. <span data-ttu-id="b2356-217">Dans l'arborescence , développez modèle\Paiements\Créancier.</span><span class="sxs-lookup"><span data-stu-id="b2356-217">In the tree, expand 'model\Payments\Creditor Agent(CreditorAgent)'.</span></span>
35. <span data-ttu-id="b2356-218">Dans l'arborescence, sélectionnez modèle\Paiements\Devise.</span><span class="sxs-lookup"><span data-stu-id="b2356-218">In the tree, select 'model\Payments\Currency'.</span></span>
36. <span data-ttu-id="b2356-219">Dans l'arborescence, sélectionnez « Excel\PaymLines\Devise ».</span><span class="sxs-lookup"><span data-stu-id="b2356-219">In the tree, select 'Excel\PaymLines\Currency'.</span></span>
37. <span data-ttu-id="b2356-220">Cliquez sur Lier.</span><span class="sxs-lookup"><span data-stu-id="b2356-220">Click Bind.</span></span>
38. <span data-ttu-id="b2356-221">Dans l'arborescence, développez PaymentByCurrency.</span><span class="sxs-lookup"><span data-stu-id="b2356-221">In the tree, expand 'PaymentByCurrency'.</span></span>
39. <span data-ttu-id="b2356-222">Dans l'arborescence, développez PaymentByCurrency\groupé.</span><span class="sxs-lookup"><span data-stu-id="b2356-222">In the tree, expand 'PaymentByCurrency\grouped'.</span></span>
40. <span data-ttu-id="b2356-223">Dans l'arborescence, sélectionnez PaymentByCurrency\groupé\Devise.</span><span class="sxs-lookup"><span data-stu-id="b2356-223">In the tree, select 'PaymentByCurrency\grouped\Currency'.</span></span>
41. <span data-ttu-id="b2356-224">Dans l'arborescence, développez « Excel\SummaryLines ».</span><span class="sxs-lookup"><span data-stu-id="b2356-224">In the tree, expand 'Excel\SummaryLines'.</span></span>
42. <span data-ttu-id="b2356-225">Dans l'arborescence, sélectionnez « Excel\SummaryLines\SummaryCurrency ».</span><span class="sxs-lookup"><span data-stu-id="b2356-225">In the tree, select 'Excel\SummaryLines\SummaryCurrency'.</span></span>
43. <span data-ttu-id="b2356-226">Cliquez sur Lier.</span><span class="sxs-lookup"><span data-stu-id="b2356-226">Click Bind.</span></span>
44. <span data-ttu-id="b2356-227">Dans l'arborescence, développez PaymentByCurrency\agrégé.</span><span class="sxs-lookup"><span data-stu-id="b2356-227">In the tree, expand 'PaymentByCurrency\aggregated'.</span></span>
45. <span data-ttu-id="b2356-228">Dans l'arborescence, sélectionnez PaymentByCurrency\agrégé\TotalInstructuredAmount.</span><span class="sxs-lookup"><span data-stu-id="b2356-228">In the tree, select 'PaymentByCurrency\aggregated\TotalInstructuredAmount'.</span></span>
46. <span data-ttu-id="b2356-229">Dans l'arborescence, sélectionnez « Excel\SummaryLines\SummaryAmount ».</span><span class="sxs-lookup"><span data-stu-id="b2356-229">In the tree, select 'Excel\SummaryLines\SummaryAmount'.</span></span>
47. <span data-ttu-id="b2356-230">Cliquez sur Lier.</span><span class="sxs-lookup"><span data-stu-id="b2356-230">Click Bind.</span></span>
48. <span data-ttu-id="b2356-231">Sélectionnez PaymentByCurrency.</span><span class="sxs-lookup"><span data-stu-id="b2356-231">In the tree, select 'PaymentByCurrency'.</span></span>
49. <span data-ttu-id="b2356-232">Dans l'arborescence, sélectionnez « Excel\SummaryLines ».</span><span class="sxs-lookup"><span data-stu-id="b2356-232">In the tree, select 'Excel\SummaryLines'.</span></span>
50. <span data-ttu-id="b2356-233">Cliquez sur Lier.</span><span class="sxs-lookup"><span data-stu-id="b2356-233">Click Bind.</span></span>
51. <span data-ttu-id="b2356-234">Dans l'arborescence, sélectionnez model\Payments.</span><span class="sxs-lookup"><span data-stu-id="b2356-234">In the tree, select 'model\Payments'.</span></span>
52. <span data-ttu-id="b2356-235">Dans l'arborescence, sélectionnez « Excel\PaymLines ».</span><span class="sxs-lookup"><span data-stu-id="b2356-235">In the tree, select 'Excel\PaymLines'.</span></span>
53. <span data-ttu-id="b2356-236">Cliquez sur Lier.</span><span class="sxs-lookup"><span data-stu-id="b2356-236">Click Bind.</span></span>
54. <span data-ttu-id="b2356-237">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="b2356-237">Click Save.</span></span>
55. <span data-ttu-id="b2356-238">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="b2356-238">Close the page.</span></span>

## <a name="use-the-created-configuration-for-payments-processing"></a><span data-ttu-id="b2356-239">Utiliser la configuration créée pour le traitement des paiements</span><span class="sxs-lookup"><span data-stu-id="b2356-239">Use the created configuration for payments processing</span></span>
1. <span data-ttu-id="b2356-240">Cliquez sur Modifier le statut.</span><span class="sxs-lookup"><span data-stu-id="b2356-240">Click Change status.</span></span>
2. <span data-ttu-id="b2356-241">Cliquez sur Terminé.</span><span class="sxs-lookup"><span data-stu-id="b2356-241">Click Complete.</span></span>
3. <span data-ttu-id="b2356-242">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="b2356-242">Click OK.</span></span>
4. <span data-ttu-id="b2356-243">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="b2356-243">Close the page.</span></span>
5. <span data-ttu-id="b2356-244">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="b2356-244">Close the page.</span></span>
6. <span data-ttu-id="b2356-245">Accédez à Comptabilité fournisseur > Paramétrage des paiements > Modes de paiement.</span><span class="sxs-lookup"><span data-stu-id="b2356-245">Go to Accounts payable > Payment setup > Methods of payment.</span></span>
7. <span data-ttu-id="b2356-246">Utilisez le filtre rapide pour filtrer selon le champ Mode de paiement avec une valeur de « Électronique ».</span><span class="sxs-lookup"><span data-stu-id="b2356-246">Use the Quick Filter to filter on the Method of payment field with a value of 'Electronic'.</span></span>
    * <span data-ttu-id="b2356-247">électronique</span><span class="sxs-lookup"><span data-stu-id="b2356-247">Electronic</span></span>  
8. <span data-ttu-id="b2356-248">Cliquez sur Modifier.</span><span class="sxs-lookup"><span data-stu-id="b2356-248">Click Edit.</span></span>
9. <span data-ttu-id="b2356-249">Développez la section Formats de fichier.</span><span class="sxs-lookup"><span data-stu-id="b2356-249">Expand the File formats section.</span></span>
10. <span data-ttu-id="b2356-250">Sélectionnez Oui dans le champ États électroniques génériques.</span><span class="sxs-lookup"><span data-stu-id="b2356-250">Select Yes in the Generic electronic reporting field.</span></span>
11. <span data-ttu-id="b2356-251">Entrez ou sélectionnez une valeur dans le champ Exporter la configuration du format.</span><span class="sxs-lookup"><span data-stu-id="b2356-251">In the Export format configuration field, enter or select a value.</span></span>
    * <span data-ttu-id="b2356-252">Sélectionnez la configuration « Exemple d'état sur les feuilles de calcul ».</span><span class="sxs-lookup"><span data-stu-id="b2356-252">Select the ‘Sample worksheet report’ configuration.</span></span>  
12. <span data-ttu-id="b2356-253">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="b2356-253">Click Save.</span></span>
13. <span data-ttu-id="b2356-254">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="b2356-254">Close the page.</span></span>

## <a name="use-the-created-configuration-for-testing-of-payment-journals-processing"></a><span data-ttu-id="b2356-255">Utiliser la configuration créée pour tester le traitement de journaux des paiements</span><span class="sxs-lookup"><span data-stu-id="b2356-255">Use the created configuration for testing of payment journals processing</span></span>
1. <span data-ttu-id="b2356-256">Accédez à Comptabilité fournisseur > Paiements > Journal des paiements.</span><span class="sxs-lookup"><span data-stu-id="b2356-256">Go to Accounts payable > Payments > Payment journal.</span></span>
2. <span data-ttu-id="b2356-257">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="b2356-257">Click New.</span></span>
    * <span data-ttu-id="b2356-258">Créez un journal des paiements.</span><span class="sxs-lookup"><span data-stu-id="b2356-258">Create a new payment journal.</span></span>  
3. <span data-ttu-id="b2356-259">Dans le champ Nom, tapez « VendPay ».</span><span class="sxs-lookup"><span data-stu-id="b2356-259">In the Name field, type 'VendPay'.</span></span>
    * <span data-ttu-id="b2356-260">VendPay</span><span class="sxs-lookup"><span data-stu-id="b2356-260">VendPay</span></span>  
4. <span data-ttu-id="b2356-261">Cliquez sur Lignes.</span><span class="sxs-lookup"><span data-stu-id="b2356-261">Click Lines.</span></span>
5. <span data-ttu-id="b2356-262">Dans le champ Compte, spécifiez les valeurs GB_SI_000001.</span><span class="sxs-lookup"><span data-stu-id="b2356-262">In the Account field, specify the values 'GB_SI_000001'.</span></span>
    * <span data-ttu-id="b2356-263">GB_SI_000001</span><span class="sxs-lookup"><span data-stu-id="b2356-263">GB_SI_000001</span></span>  
6. <span data-ttu-id="b2356-264">Définissez Débit sur 1000.</span><span class="sxs-lookup"><span data-stu-id="b2356-264">Set Debit to '1000'.</span></span>
7. <span data-ttu-id="b2356-265">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="b2356-265">Click New.</span></span>
8. <span data-ttu-id="b2356-266">Dans le champ Compte, spécifiez les valeurs GB_SI_000005.</span><span class="sxs-lookup"><span data-stu-id="b2356-266">In the Account field, specify the values 'GB_SI_000005'.</span></span>
    * <span data-ttu-id="b2356-267">GB_SI_000005</span><span class="sxs-lookup"><span data-stu-id="b2356-267">GB_SI_000005</span></span>  
9. <span data-ttu-id="b2356-268">Définissez Débit sur 2000.</span><span class="sxs-lookup"><span data-stu-id="b2356-268">Set Debit to '2000'.</span></span>
10. <span data-ttu-id="b2356-269">Dans le champ Devise, tapez EUR.</span><span class="sxs-lookup"><span data-stu-id="b2356-269">In the Currency field, type 'EUR'.</span></span>
    * <span data-ttu-id="b2356-270">EUR</span><span class="sxs-lookup"><span data-stu-id="b2356-270">EUR</span></span>  
11. <span data-ttu-id="b2356-271">Spécifiez les valeurs GBSI OPER dans le champ Compte de contrepartie.</span><span class="sxs-lookup"><span data-stu-id="b2356-271">In the Offset account field, specify the values 'GBSI OPER'.</span></span>
    * <span data-ttu-id="b2356-272">GBSI OPER</span><span class="sxs-lookup"><span data-stu-id="b2356-272">GBSI OPER</span></span>  
12. <span data-ttu-id="b2356-273">Tapez Électronique dans le champ Mode de paiement.</span><span class="sxs-lookup"><span data-stu-id="b2356-273">In the Method of payment field, type 'Electronic'.</span></span>
    * <span data-ttu-id="b2356-274">électronique</span><span class="sxs-lookup"><span data-stu-id="b2356-274">Electronic</span></span>  
13. <span data-ttu-id="b2356-275">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="b2356-275">Click Save.</span></span>
14. <span data-ttu-id="b2356-276">Cliquez sur Générer les paiements.</span><span class="sxs-lookup"><span data-stu-id="b2356-276">Click Generate payments.</span></span>
15. <span data-ttu-id="b2356-277">Tapez Électronique dans le champ Mode de paiement.</span><span class="sxs-lookup"><span data-stu-id="b2356-277">In the Method of payment field, type 'Electronic'.</span></span>
    * <span data-ttu-id="b2356-278">électronique</span><span class="sxs-lookup"><span data-stu-id="b2356-278">Electronic</span></span>  
16. <span data-ttu-id="b2356-279">Dans le champ Nom de fichier, tapez « Paiements ».</span><span class="sxs-lookup"><span data-stu-id="b2356-279">In the File name field, type 'Payments'.</span></span>
    * <span data-ttu-id="b2356-280">Par exemple, tapez Paiements.</span><span class="sxs-lookup"><span data-stu-id="b2356-280">For example, type Payments.</span></span>  
17. <span data-ttu-id="b2356-281">Tapez GBSI OPER dans le champ Compte bancaire.</span><span class="sxs-lookup"><span data-stu-id="b2356-281">In the Bank account field, type 'GBSI OPER'.</span></span>
    * <span data-ttu-id="b2356-282">GBSI OPER</span><span class="sxs-lookup"><span data-stu-id="b2356-282">GBSI OPER</span></span>  
18. <span data-ttu-id="b2356-283">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="b2356-283">Click OK.</span></span>
19. <span data-ttu-id="b2356-284">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="b2356-284">Click OK.</span></span>
    * <span data-ttu-id="b2356-285">Examinez la feuille de calcul créée, notamment les détails des lignes de paiement ainsi que les totaux pour chaque code devise utilisé dans ce message de paiement.</span><span class="sxs-lookup"><span data-stu-id="b2356-285">Review the created worksheet, including details of payment lines as well as totals for each currency code used in this payment message.</span></span>  


