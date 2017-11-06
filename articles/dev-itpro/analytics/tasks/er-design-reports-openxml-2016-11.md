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
ms.sourcegitcommit: f827b4787506cfdec8b9a91c4a68f3293190158a
ms.openlocfilehash: 04def14ddf9b079005bf11acbcaf64b21aa80fdb
ms.contentlocale: fr-fr
ms.lasthandoff: 11/06/2017

---
# <a name="design-a-configuration-for-generating-reports-in-openxml-format-for-electronic-reporting-er"></a><span data-ttu-id="9a50e-103">Définir une configuration pour générer des états au format OpenXML pour la gestion des états électroniques (ER)</span><span class="sxs-lookup"><span data-stu-id="9a50e-103">Design a configuration for generating reports in OpenXML format for electronic reporting (ER)</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="9a50e-104">Les étapes suivantes expliquent comment un utilisateur dont le rôle est Administrateur système ou Développeur d'états électroniques peut créer une configuration de format pour la génération d'états électronique (ER) qui contient un modèle pour générer des documents électroniques au format OPENXML.</span><span class="sxs-lookup"><span data-stu-id="9a50e-104">The following steps explain how a user in the System Administrator or Electronic Reporting Developer role can create a new Electronic reporting (ER) configuration that contains a template for generating electronic documents in OPENXML format.</span></span> <span data-ttu-id="9a50e-105">Cette configuration sera utilisée pour traiter les paiements fournisseur.</span><span class="sxs-lookup"><span data-stu-id="9a50e-105">This configuration will be used for processing vendor payments.</span></span>



<span data-ttu-id="9a50e-106">Dans cet exemple, vous allez créer une configuration pour la société témoin, Litware, Inc. Ces étapes peuvent être effectuées dans la société GBSI.</span><span class="sxs-lookup"><span data-stu-id="9a50e-106">In this example, you will create a configuration for sample company, Litware, Inc. These steps can be performed in GBSI company.</span></span>



<span data-ttu-id="9a50e-107">Pour effectuer ces étapes, vous devez commencer par effectuer les étapes de la procédure « Créer un fournisseur de configuration et le marquer comme actif ».</span><span class="sxs-lookup"><span data-stu-id="9a50e-107">To complete these steps, you must first complete the steps in the “Create a configuration provider and mark it as active” procedure.</span></span> <span data-ttu-id="9a50e-108">Vous devez également avoir un fichier Excel qui sera importé lorsque vous créez le modèle.</span><span class="sxs-lookup"><span data-stu-id="9a50e-108">You must also have an Excel file which will be imported when creating the template.</span></span> <span data-ttu-id="9a50e-109">Ce fichier peut être consulté à partir de : https://msdynamics.blob.core.windows.net/media/2016/04/SampleVendPaymWsReport.xlsx</span><span class="sxs-lookup"><span data-stu-id="9a50e-109">This file can be accessed from:  https://msdynamics.blob.core.windows.net/media/2016/04/SampleVendPaymWsReport.xlsx</span></span>


## <a name="upload-the-payments-data-model-configuration"></a><span data-ttu-id="9a50e-110">Téléchargez la configuration du modèle de données des paiements</span><span class="sxs-lookup"><span data-stu-id="9a50e-110">Upload the Payments data model configuration</span></span>
1. <span data-ttu-id="9a50e-111">Accédez à Administration d'organisation > Espaces de travail > États électroniques.</span><span class="sxs-lookup"><span data-stu-id="9a50e-111">Go to Organization administration > Workspaces > Electronic reporting.</span></span>
2. <span data-ttu-id="9a50e-112">Dans la liste, marquez la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="9a50e-112">In the list, mark the selected row.</span></span>
    * <span data-ttu-id="9a50e-113">Sélectionnez le fournisseur de configuration pour la société fictive Litware, Inc. Si vous ne voyez pas ce fournisseur de configuration, vous devez d'abord effectuer les étapes de la procédure « Créer un fournisseur de configuration et le marquer comme actif ».</span><span class="sxs-lookup"><span data-stu-id="9a50e-113">Select the configuration provider for sample company, Litware, Inc. If you don’t see this configuration provider, you must first complete the steps in the “Create a configuration provider and mark it as active” procedure.</span></span>  
3. <span data-ttu-id="9a50e-114">Cliquez sur Activer.</span><span class="sxs-lookup"><span data-stu-id="9a50e-114">Click Set active.</span></span>
4. <span data-ttu-id="9a50e-115">Cliquez sur Référentiels.</span><span class="sxs-lookup"><span data-stu-id="9a50e-115">Click Repositories.</span></span>
    * <span data-ttu-id="9a50e-116">Sélectionnez un référentiel pour le type de ressources opérationnelles, si disponible.</span><span class="sxs-lookup"><span data-stu-id="9a50e-116">Select a repository for the Operations Resources type, if available.</span></span> <span data-ttu-id="9a50e-117">S'il n'est pas disponible, ignorez les étapes suivantes sur la création d'un référentiel.</span><span class="sxs-lookup"><span data-stu-id="9a50e-117">If its available, skip the following steps about creating a new repository.</span></span>  
5. <span data-ttu-id="9a50e-118">Cliquez sur Ajouter pour ouvrir la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="9a50e-118">Click Add to open the drop dialog.</span></span>
6. <span data-ttu-id="9a50e-119">Dans le champ Type du référentiel de configuration, entrez « Ressources opérationnelles ».</span><span class="sxs-lookup"><span data-stu-id="9a50e-119">In the Configuration repository type field, enter 'Operations resources'.</span></span>
7. <span data-ttu-id="9a50e-120">Cliquez sur Créer un référentiel.</span><span class="sxs-lookup"><span data-stu-id="9a50e-120">Click Create repository.</span></span>
8. <span data-ttu-id="9a50e-121">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="9a50e-121">Click OK.</span></span>
9. <span data-ttu-id="9a50e-122">Cliquez sur Ouvrir.</span><span class="sxs-lookup"><span data-stu-id="9a50e-122">Click Open.</span></span>
10. <span data-ttu-id="9a50e-123">Dans l'arborescence, sélectionnez « Modèle de paiement ».</span><span class="sxs-lookup"><span data-stu-id="9a50e-123">In the tree, select 'Payment model'.</span></span>
11. <span data-ttu-id="9a50e-124">Cliquez sur Importer.</span><span class="sxs-lookup"><span data-stu-id="9a50e-124">Click Import.</span></span>
    * <span data-ttu-id="9a50e-125">Importez ce modèle de données.</span><span class="sxs-lookup"><span data-stu-id="9a50e-125">Import this data model.</span></span> <span data-ttu-id="9a50e-126">Il est utilisé comme source de données dans une nouvelle configuration de format.</span><span class="sxs-lookup"><span data-stu-id="9a50e-126">It will be used as a data source in a new format configuration.</span></span> <span data-ttu-id="9a50e-127">Ignorez cette étape si cette configuration a déjà été importée.</span><span class="sxs-lookup"><span data-stu-id="9a50e-127">Skip this step if this configuration has been already imported.</span></span>  
12. <span data-ttu-id="9a50e-128">Cliquez sur Oui.</span><span class="sxs-lookup"><span data-stu-id="9a50e-128">Click Yes.</span></span>
13. <span data-ttu-id="9a50e-129">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="9a50e-129">Close the page.</span></span>
14. <span data-ttu-id="9a50e-130">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="9a50e-130">Close the page.</span></span>

## <a name="create-a-new-format-configuration"></a><span data-ttu-id="9a50e-131">Créer une configuration de format</span><span class="sxs-lookup"><span data-stu-id="9a50e-131">Create a new format configuration</span></span>
1. <span data-ttu-id="9a50e-132">Cliquez sur Configurations des états.</span><span class="sxs-lookup"><span data-stu-id="9a50e-132">Click Reporting configurations.</span></span>
2. <span data-ttu-id="9a50e-133">Dans l'arborescence, sélectionnez « Modèle de paiement ».</span><span class="sxs-lookup"><span data-stu-id="9a50e-133">In the tree, select 'Payment model'.</span></span>
3. <span data-ttu-id="9a50e-134">Cliquez sur Créer la configuration pour ouvrir la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="9a50e-134">Click Create configuration to open the drop dialog.</span></span>
4. <span data-ttu-id="9a50e-135">Dans le champ Nouveau, entrez « Format basé sur le PaymentModel du modèle du paiement ».</span><span class="sxs-lookup"><span data-stu-id="9a50e-135">In the New field, enter 'Format based on data model PaymentModel'.</span></span>
    * <span data-ttu-id="9a50e-136">Créez un format basé sur le modèle de données PaymentModel.</span><span class="sxs-lookup"><span data-stu-id="9a50e-136">Create a format that is based on the PaymentModel data model.</span></span>  
5. <span data-ttu-id="9a50e-137">Tapez Exemple d'état sur les feuilles de calcul dans le champ Nom.</span><span class="sxs-lookup"><span data-stu-id="9a50e-137">In the Name field, type 'Sample worksheet report'.</span></span>
    * <span data-ttu-id="9a50e-138">Exemple d'état sur les feuilles de calcul</span><span class="sxs-lookup"><span data-stu-id="9a50e-138">Sample worksheet report</span></span>  
6. <span data-ttu-id="9a50e-139">Entrez « Exemple d'état sur les feuilles de calcul pour les paiements fournisseurs » dans le champ Description.</span><span class="sxs-lookup"><span data-stu-id="9a50e-139">In the Description field, type 'Sample worksheet report for vendors’ payments'.</span></span>
    * <span data-ttu-id="9a50e-140">Exemple d'état sur les feuilles de calcul pour les paiements fournisseurs.</span><span class="sxs-lookup"><span data-stu-id="9a50e-140">Sample worksheet report for vendors’ payments.</span></span>  
7. <span data-ttu-id="9a50e-141">Dans le champ Définition du modèle de données, entrez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="9a50e-141">In the Data model definition field, enter or select a value.</span></span>
    * <span data-ttu-id="9a50e-142">Sélectionnez la définition « CustomerCreditTransferInitiation ».</span><span class="sxs-lookup"><span data-stu-id="9a50e-142">Select the 'CustomerCreditTransferInitiation' definition.</span></span>  
8. <span data-ttu-id="9a50e-143">Cliquez sur Créer une configuration.</span><span class="sxs-lookup"><span data-stu-id="9a50e-143">Click Create configuration.</span></span>

## <a name="design-a-new-document-in-openxml-worksheet-format"></a><span data-ttu-id="9a50e-144">Créez un document dans le format de la feuille de calcul OPENXML</span><span class="sxs-lookup"><span data-stu-id="9a50e-144">Design a new document in OPENXML worksheet format</span></span>
1. <span data-ttu-id="9a50e-145">Sélectionnez Modèle de paiement\Exemple d'état sur les feuilles de calcul dans l'arborescence.</span><span class="sxs-lookup"><span data-stu-id="9a50e-145">In the tree, select 'Payment model\Sample worksheet report'.</span></span>
2. <span data-ttu-id="9a50e-146">Cliquez sur Concepteur.</span><span class="sxs-lookup"><span data-stu-id="9a50e-146">Click Designer.</span></span>
3. <span data-ttu-id="9a50e-147">Cliquez sur Importer dans le volet Actions.</span><span class="sxs-lookup"><span data-stu-id="9a50e-147">On the Action Pane, click Import.</span></span>
4. <span data-ttu-id="9a50e-148">Cliquez sur Importer depuis Excel.</span><span class="sxs-lookup"><span data-stu-id="9a50e-148">Click Import from Excel.</span></span>
5. <span data-ttu-id="9a50e-149">Cliquez sur Documents joints.</span><span class="sxs-lookup"><span data-stu-id="9a50e-149">Click Attachments.</span></span>
    * <span data-ttu-id="9a50e-150">Joignez le document Excel existant comme modèle.</span><span class="sxs-lookup"><span data-stu-id="9a50e-150">Attach the existing Excel document as a template.</span></span>  
6. <span data-ttu-id="9a50e-151">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="9a50e-151">Click New.</span></span>
7. <span data-ttu-id="9a50e-152">Cliquez sur Fichier.</span><span class="sxs-lookup"><span data-stu-id="9a50e-152">Click File.</span></span>
    * <span data-ttu-id="9a50e-153">Pointez vers le fichier Excel existant.</span><span class="sxs-lookup"><span data-stu-id="9a50e-153">Point to the existing Excel file.</span></span>  
8. <span data-ttu-id="9a50e-154">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="9a50e-154">Close the page.</span></span>
9. <span data-ttu-id="9a50e-155">Dans le champ Modèle, entrez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="9a50e-155">In the Template field, enter or select a value.</span></span>
    * <span data-ttu-id="9a50e-156">Sélectionnez le fichier Excel à utiliser comme modèle.</span><span class="sxs-lookup"><span data-stu-id="9a50e-156">Select the attached Excel file to be used as a template.</span></span>  
10. <span data-ttu-id="9a50e-157">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="9a50e-157">Click OK.</span></span>
    * <span data-ttu-id="9a50e-158">Notez que les composants de format ER ont été créés dans le format de conception basé sur la structure du document MS Excel de référence (plages nommées).</span><span class="sxs-lookup"><span data-stu-id="9a50e-158">Note that ER format components have been created in the designing format based on the structure of the referring MS Excel document (named ranges).</span></span>  

## <a name="create-a-new-data-source-to-calculate-totals-by-currency-codes"></a><span data-ttu-id="9a50e-159">Créer une nouvelle source de données pour calculer les totaux par codes devise</span><span class="sxs-lookup"><span data-stu-id="9a50e-159">Create a new data source to calculate totals by currency codes</span></span>
1. <span data-ttu-id="9a50e-160">Cliquez sur l'onglet Mise en relation.</span><span class="sxs-lookup"><span data-stu-id="9a50e-160">Click the Mapping tab.</span></span>
2. <span data-ttu-id="9a50e-161">Cliquez sur Ajouter racine pour ouvrir la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="9a50e-161">Click Add root to open the drop dialog.</span></span>
3. <span data-ttu-id="9a50e-162">Dans l'arborescence, sélectionnez Fonctions\Grouper par.</span><span class="sxs-lookup"><span data-stu-id="9a50e-162">In the tree, select 'Functions\Group by'.</span></span>
4. <span data-ttu-id="9a50e-163">Entrez PaymentByCurrency dans le champ Nom.</span><span class="sxs-lookup"><span data-stu-id="9a50e-163">In the Name field, type 'PaymentByCurrency'.</span></span>
    * <span data-ttu-id="9a50e-164">PaymentByCurrency</span><span class="sxs-lookup"><span data-stu-id="9a50e-164">PaymentByCurrency</span></span>  
5. <span data-ttu-id="9a50e-165">Cliquez sur Modifier le groupe par.</span><span class="sxs-lookup"><span data-stu-id="9a50e-165">Click Edit group by.</span></span>
6. <span data-ttu-id="9a50e-166">Dans l'arborescence , développez « model ».</span><span class="sxs-lookup"><span data-stu-id="9a50e-166">In the tree, expand 'model'.</span></span>
7. <span data-ttu-id="9a50e-167">Dans l'arborescence, sélectionnez model\Payments.</span><span class="sxs-lookup"><span data-stu-id="9a50e-167">In the tree, select 'model\Payments'.</span></span>
8. <span data-ttu-id="9a50e-168">Cliquez sur Ajouter le champ à.</span><span class="sxs-lookup"><span data-stu-id="9a50e-168">Click Add field to.</span></span>
9. <span data-ttu-id="9a50e-169">Cliquez sur Éléments à grouper.</span><span class="sxs-lookup"><span data-stu-id="9a50e-169">Click What to group.</span></span>
10. <span data-ttu-id="9a50e-170">Dans l'arborescence, développez model\Payments.</span><span class="sxs-lookup"><span data-stu-id="9a50e-170">In the tree, expand 'model\Payments'.</span></span>
11. <span data-ttu-id="9a50e-171">Dans l'arborescence, sélectionnez modèle\Paiements\Devise.</span><span class="sxs-lookup"><span data-stu-id="9a50e-171">In the tree, select 'model\Payments\Currency'.</span></span>
12. <span data-ttu-id="9a50e-172">Cliquez sur Ajouter le champ à.</span><span class="sxs-lookup"><span data-stu-id="9a50e-172">Click Add field to.</span></span>
13. <span data-ttu-id="9a50e-173">Cliquez sur Champs groupés.</span><span class="sxs-lookup"><span data-stu-id="9a50e-173">Click Grouped fields.</span></span>
14. <span data-ttu-id="9a50e-174">Dans l'arborescence, sélectionnez modèle\Paiements\Montant ordonné.</span><span class="sxs-lookup"><span data-stu-id="9a50e-174">In the tree, select 'model\Payments\Instructed Amount(InstructedAmount)'.</span></span>
15. <span data-ttu-id="9a50e-175">Cliquez sur Ajouter le champ à.</span><span class="sxs-lookup"><span data-stu-id="9a50e-175">Click Add field to.</span></span>
16. <span data-ttu-id="9a50e-176">Cliquez sur Champs d'agrégation.</span><span class="sxs-lookup"><span data-stu-id="9a50e-176">Click Aggregation fields.</span></span>
17. <span data-ttu-id="9a50e-177">Sélectionnez une option dans le champ Méthode.</span><span class="sxs-lookup"><span data-stu-id="9a50e-177">In the Method field, select an option.</span></span>
    * <span data-ttu-id="9a50e-178">Sélectionnez la fonction d'agrégation SOMME.</span><span class="sxs-lookup"><span data-stu-id="9a50e-178">Select the SUM aggregation function.</span></span>  
18. <span data-ttu-id="9a50e-179">Dans le champ Nom, tapez TotalInstructuredAmount.</span><span class="sxs-lookup"><span data-stu-id="9a50e-179">In the Name field, type 'TotalInstructuredAmount'.</span></span>
    * <span data-ttu-id="9a50e-180">TotalInstructuredAmount</span><span class="sxs-lookup"><span data-stu-id="9a50e-180">TotalInstructuredAmount</span></span>  
19. <span data-ttu-id="9a50e-181">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="9a50e-181">Click Save.</span></span>
20. <span data-ttu-id="9a50e-182">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="9a50e-182">Close the page.</span></span>
21. <span data-ttu-id="9a50e-183">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="9a50e-183">Click OK.</span></span>

## <a name="map-format-components-to-data-sources"></a><span data-ttu-id="9a50e-184">Mettre en correspondance des composants de format vers des sources de données</span><span class="sxs-lookup"><span data-stu-id="9a50e-184">Map format components to data sources</span></span>
1. <span data-ttu-id="9a50e-185">Dans l'arborescence , développez « model ».</span><span class="sxs-lookup"><span data-stu-id="9a50e-185">In the tree, expand 'model'.</span></span>
2. <span data-ttu-id="9a50e-186">Dans l'arborescence, développez model\Payments.</span><span class="sxs-lookup"><span data-stu-id="9a50e-186">In the tree, expand 'model\Payments'.</span></span>
3. <span data-ttu-id="9a50e-187">Dans l'arborescence, développez modèle\Paiements\Partie qui prend l'initiative.</span><span class="sxs-lookup"><span data-stu-id="9a50e-187">In the tree, expand 'model\Payments\Initiating Party(InitiatingParty)'.</span></span>
4. <span data-ttu-id="9a50e-188">Dans l'arborescence, sélectionnez modèle\Paiements\Partie qui prend l'initiative\Nom.</span><span class="sxs-lookup"><span data-stu-id="9a50e-188">In the tree, select 'model\Payments\Initiating Party(InitiatingParty)\Name'.</span></span>
5. <span data-ttu-id="9a50e-189">Dans l'arborescence, développez ou réduisez « Excel\ReportHeader ».</span><span class="sxs-lookup"><span data-stu-id="9a50e-189">In the tree, expand 'Excel\ReportHeader'.</span></span>
6. <span data-ttu-id="9a50e-190">Dans l'arborescence, sélectionnez « Excel\ReportHeader\CompanyName ».</span><span class="sxs-lookup"><span data-stu-id="9a50e-190">In the tree, select 'Excel\ReportHeader\CompanyName'.</span></span>
7. <span data-ttu-id="9a50e-191">Cliquez sur Lier.</span><span class="sxs-lookup"><span data-stu-id="9a50e-191">Click Bind.</span></span>
8. <span data-ttu-id="9a50e-192">Dans l'arborescence , développez « modèle\Paiements\Créditeur ».</span><span class="sxs-lookup"><span data-stu-id="9a50e-192">In the tree, expand 'model\Payments\Creditor'.</span></span>
9. <span data-ttu-id="9a50e-193">Dans l'arborescence , développez modèle\Paiements\Créancier\Identification.</span><span class="sxs-lookup"><span data-stu-id="9a50e-193">In the tree, expand 'model\Payments\Creditor\Identification'.</span></span>
10. <span data-ttu-id="9a50e-194">Dans l'arborescence, sélectionnez modèle\Paiements\Créancier\Identification\Source ID(SourceID).</span><span class="sxs-lookup"><span data-stu-id="9a50e-194">In the tree, select 'model\Payments\Creditor\Identification\Source ID(SourceID)'.</span></span>
11. <span data-ttu-id="9a50e-195">Dans l'arborescence, développez « Excel\PaymLines ».</span><span class="sxs-lookup"><span data-stu-id="9a50e-195">In the tree, expand 'Excel\PaymLines'.</span></span>
12. <span data-ttu-id="9a50e-196">Dans l'arborescence, sélectionnez « Excel\PaymLines\VendAccountName ».</span><span class="sxs-lookup"><span data-stu-id="9a50e-196">In the tree, select 'Excel\PaymLines\VendAccountName'.</span></span>
13. <span data-ttu-id="9a50e-197">Cliquez sur Lier.</span><span class="sxs-lookup"><span data-stu-id="9a50e-197">Click Bind.</span></span>
14. <span data-ttu-id="9a50e-198">Dans l'arborescence, sélectionnez « modèle\Paiements\Créditeur\Nom ».</span><span class="sxs-lookup"><span data-stu-id="9a50e-198">In the tree, select 'model\Payments\Creditor\Name'.</span></span>
15. <span data-ttu-id="9a50e-199">Dans l'arborescence, sélectionnez « Excel\PaymLines\VendName ».</span><span class="sxs-lookup"><span data-stu-id="9a50e-199">In the tree, select 'Excel\PaymLines\VendName'.</span></span>
16. <span data-ttu-id="9a50e-200">Cliquez sur Lier.</span><span class="sxs-lookup"><span data-stu-id="9a50e-200">Click Bind.</span></span>
17. <span data-ttu-id="9a50e-201">Dans l'arborescence , développez modèle\Paiements\Créancier.</span><span class="sxs-lookup"><span data-stu-id="9a50e-201">In the tree, expand 'model\Payments\Creditor Agent(CreditorAgent)'.</span></span>
18. <span data-ttu-id="9a50e-202">Dans l'arborescence, sélectionnez modèle\Paiements\Créancier\Nom.</span><span class="sxs-lookup"><span data-stu-id="9a50e-202">In the tree, select 'model\Payments\Creditor Agent(CreditorAgent)\Name'.</span></span>
19. <span data-ttu-id="9a50e-203">Dans l'arborescence, sélectionnez « Excel\PaymLines\Banque ».</span><span class="sxs-lookup"><span data-stu-id="9a50e-203">In the tree, select 'Excel\PaymLines\Bank'.</span></span>
20. <span data-ttu-id="9a50e-204">Cliquez sur Lier.</span><span class="sxs-lookup"><span data-stu-id="9a50e-204">Click Bind.</span></span>
21. <span data-ttu-id="9a50e-205">Dans l'arborescence, sélectionnez modèle\Paiements\Créancier\Numéro d'acheminement.</span><span class="sxs-lookup"><span data-stu-id="9a50e-205">In the tree, select 'model\Payments\Creditor Agent(CreditorAgent)\Routing Number(RoutingNumber)'.</span></span>
22. <span data-ttu-id="9a50e-206">Dans l'arborescence, sélectionnez « Excel\PaymLines\RoutingNumber ».</span><span class="sxs-lookup"><span data-stu-id="9a50e-206">In the tree, select 'Excel\PaymLines\RoutingNumber'.</span></span>
23. <span data-ttu-id="9a50e-207">Cliquez sur Lier.</span><span class="sxs-lookup"><span data-stu-id="9a50e-207">Click Bind.</span></span>
24. <span data-ttu-id="9a50e-208">Dans l'arborescence , développez « model\Payments\Creditor Account(CreditorAccount) ».</span><span class="sxs-lookup"><span data-stu-id="9a50e-208">In the tree, expand 'model\Payments\Creditor Account(CreditorAccount)'.</span></span>
25. <span data-ttu-id="9a50e-209">Dans l'arborescence , développez « model\Payments\Creditor Account(CreditorAccount)\Identification ».</span><span class="sxs-lookup"><span data-stu-id="9a50e-209">In the tree, expand 'model\Payments\Creditor Account(CreditorAccount)\Identification'.</span></span>
26. <span data-ttu-id="9a50e-210">Dans l'arborescence, sélectionnez modèle\Paiements\Créancier\Identification\Numéro.</span><span class="sxs-lookup"><span data-stu-id="9a50e-210">In the tree, select 'model\Payments\Creditor Account(CreditorAccount)\Identification\Number'.</span></span>
27. <span data-ttu-id="9a50e-211">Dans l'arborescence, sélectionnez « Excel\PaymLines\AccountNumber ».</span><span class="sxs-lookup"><span data-stu-id="9a50e-211">In the tree, select 'Excel\PaymLines\AccountNumber'.</span></span>
28. <span data-ttu-id="9a50e-212">Cliquez sur Lier.</span><span class="sxs-lookup"><span data-stu-id="9a50e-212">Click Bind.</span></span>
29. <span data-ttu-id="9a50e-213">Dans l'arborescence, sélectionnez modèle\Paiements\Montant ordonné.</span><span class="sxs-lookup"><span data-stu-id="9a50e-213">In the tree, select 'model\Payments\Instructed Amount(InstructedAmount)'.</span></span>
30. <span data-ttu-id="9a50e-214">Dans l'arborescence, sélectionnez « Excel\PaymLines\Débit ».</span><span class="sxs-lookup"><span data-stu-id="9a50e-214">In the tree, select 'Excel\PaymLines\Debit'.</span></span>
31. <span data-ttu-id="9a50e-215">Cliquez sur Lier.</span><span class="sxs-lookup"><span data-stu-id="9a50e-215">Click Bind.</span></span>
32. <span data-ttu-id="9a50e-216">Dans l'arborescence , développez « modèle\Paiements\Créditeur ».</span><span class="sxs-lookup"><span data-stu-id="9a50e-216">In the tree, expand 'model\Payments\Creditor'.</span></span>
33. <span data-ttu-id="9a50e-217">Dans l'arborescence , développez « model\Payments\Creditor Account(CreditorAccount) ».</span><span class="sxs-lookup"><span data-stu-id="9a50e-217">In the tree, expand 'model\Payments\Creditor Account(CreditorAccount)'.</span></span>
34. <span data-ttu-id="9a50e-218">Dans l'arborescence , développez modèle\Paiements\Créancier.</span><span class="sxs-lookup"><span data-stu-id="9a50e-218">In the tree, expand 'model\Payments\Creditor Agent(CreditorAgent)'.</span></span>
35. <span data-ttu-id="9a50e-219">Dans l'arborescence, sélectionnez modèle\Paiements\Devise.</span><span class="sxs-lookup"><span data-stu-id="9a50e-219">In the tree, select 'model\Payments\Currency'.</span></span>
36. <span data-ttu-id="9a50e-220">Dans l'arborescence, sélectionnez « Excel\PaymLines\Devise ».</span><span class="sxs-lookup"><span data-stu-id="9a50e-220">In the tree, select 'Excel\PaymLines\Currency'.</span></span>
37. <span data-ttu-id="9a50e-221">Cliquez sur Lier.</span><span class="sxs-lookup"><span data-stu-id="9a50e-221">Click Bind.</span></span>
38. <span data-ttu-id="9a50e-222">Dans l'arborescence, développez PaymentByCurrency.</span><span class="sxs-lookup"><span data-stu-id="9a50e-222">In the tree, expand 'PaymentByCurrency'.</span></span>
39. <span data-ttu-id="9a50e-223">Dans l'arborescence, développez PaymentByCurrency\groupé.</span><span class="sxs-lookup"><span data-stu-id="9a50e-223">In the tree, expand 'PaymentByCurrency\grouped'.</span></span>
40. <span data-ttu-id="9a50e-224">Dans l'arborescence, sélectionnez PaymentByCurrency\groupé\Devise.</span><span class="sxs-lookup"><span data-stu-id="9a50e-224">In the tree, select 'PaymentByCurrency\grouped\Currency'.</span></span>
41. <span data-ttu-id="9a50e-225">Dans l'arborescence, développez « Excel\SummaryLines ».</span><span class="sxs-lookup"><span data-stu-id="9a50e-225">In the tree, expand 'Excel\SummaryLines'.</span></span>
42. <span data-ttu-id="9a50e-226">Dans l'arborescence, sélectionnez « Excel\SummaryLines\SummaryCurrency ».</span><span class="sxs-lookup"><span data-stu-id="9a50e-226">In the tree, select 'Excel\SummaryLines\SummaryCurrency'.</span></span>
43. <span data-ttu-id="9a50e-227">Cliquez sur Lier.</span><span class="sxs-lookup"><span data-stu-id="9a50e-227">Click Bind.</span></span>
44. <span data-ttu-id="9a50e-228">Dans l'arborescence, développez PaymentByCurrency\agrégé.</span><span class="sxs-lookup"><span data-stu-id="9a50e-228">In the tree, expand 'PaymentByCurrency\aggregated'.</span></span>
45. <span data-ttu-id="9a50e-229">Dans l'arborescence, sélectionnez PaymentByCurrency\agrégé\TotalInstructuredAmount.</span><span class="sxs-lookup"><span data-stu-id="9a50e-229">In the tree, select 'PaymentByCurrency\aggregated\TotalInstructuredAmount'.</span></span>
46. <span data-ttu-id="9a50e-230">Dans l'arborescence, sélectionnez « Excel\SummaryLines\SummaryAmount ».</span><span class="sxs-lookup"><span data-stu-id="9a50e-230">In the tree, select 'Excel\SummaryLines\SummaryAmount'.</span></span>
47. <span data-ttu-id="9a50e-231">Cliquez sur Lier.</span><span class="sxs-lookup"><span data-stu-id="9a50e-231">Click Bind.</span></span>
48. <span data-ttu-id="9a50e-232">Sélectionnez PaymentByCurrency.</span><span class="sxs-lookup"><span data-stu-id="9a50e-232">In the tree, select 'PaymentByCurrency'.</span></span>
49. <span data-ttu-id="9a50e-233">Dans l'arborescence, sélectionnez « Excel\SummaryLines ».</span><span class="sxs-lookup"><span data-stu-id="9a50e-233">In the tree, select 'Excel\SummaryLines'.</span></span>
50. <span data-ttu-id="9a50e-234">Cliquez sur Lier.</span><span class="sxs-lookup"><span data-stu-id="9a50e-234">Click Bind.</span></span>
51. <span data-ttu-id="9a50e-235">Dans l'arborescence, sélectionnez model\Payments.</span><span class="sxs-lookup"><span data-stu-id="9a50e-235">In the tree, select 'model\Payments'.</span></span>
52. <span data-ttu-id="9a50e-236">Dans l'arborescence, sélectionnez « Excel\PaymLines ».</span><span class="sxs-lookup"><span data-stu-id="9a50e-236">In the tree, select 'Excel\PaymLines'.</span></span>
53. <span data-ttu-id="9a50e-237">Cliquez sur Lier.</span><span class="sxs-lookup"><span data-stu-id="9a50e-237">Click Bind.</span></span>
54. <span data-ttu-id="9a50e-238">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="9a50e-238">Click Save.</span></span>
55. <span data-ttu-id="9a50e-239">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="9a50e-239">Close the page.</span></span>

## <a name="use-the-created-configuration-for-payments-processing"></a><span data-ttu-id="9a50e-240">Utiliser la configuration créée pour le traitement des paiements</span><span class="sxs-lookup"><span data-stu-id="9a50e-240">Use the created configuration for payments processing</span></span>
1. <span data-ttu-id="9a50e-241">Cliquez sur Modifier le statut.</span><span class="sxs-lookup"><span data-stu-id="9a50e-241">Click Change status.</span></span>
2. <span data-ttu-id="9a50e-242">Cliquez sur Terminé.</span><span class="sxs-lookup"><span data-stu-id="9a50e-242">Click Complete.</span></span>
3. <span data-ttu-id="9a50e-243">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="9a50e-243">Click OK.</span></span>
4. <span data-ttu-id="9a50e-244">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="9a50e-244">Close the page.</span></span>
5. <span data-ttu-id="9a50e-245">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="9a50e-245">Close the page.</span></span>
6. <span data-ttu-id="9a50e-246">Accédez à Comptabilité fournisseur > Paramétrage des paiements > Modes de paiement.</span><span class="sxs-lookup"><span data-stu-id="9a50e-246">Go to Accounts payable > Payment setup > Methods of payment.</span></span>
7. <span data-ttu-id="9a50e-247">Utilisez le filtre rapide pour filtrer selon le champ Mode de paiement avec une valeur de « Électronique ».</span><span class="sxs-lookup"><span data-stu-id="9a50e-247">Use the Quick Filter to filter on the Method of payment field with a value of 'Electronic'.</span></span>
    * <span data-ttu-id="9a50e-248">électronique</span><span class="sxs-lookup"><span data-stu-id="9a50e-248">Electronic</span></span>  
8. <span data-ttu-id="9a50e-249">Cliquez sur Modifier.</span><span class="sxs-lookup"><span data-stu-id="9a50e-249">Click Edit.</span></span>
9. <span data-ttu-id="9a50e-250">Développez la section Formats de fichier.</span><span class="sxs-lookup"><span data-stu-id="9a50e-250">Expand the File formats section.</span></span>
10. <span data-ttu-id="9a50e-251">Sélectionnez Oui dans le champ États électroniques génériques.</span><span class="sxs-lookup"><span data-stu-id="9a50e-251">Select Yes in the Generic electronic reporting field.</span></span>
11. <span data-ttu-id="9a50e-252">Entrez ou sélectionnez une valeur dans le champ Exporter la configuration du format.</span><span class="sxs-lookup"><span data-stu-id="9a50e-252">In the Export format configuration field, enter or select a value.</span></span>
    * <span data-ttu-id="9a50e-253">Sélectionnez la configuration « Exemple d'état sur les feuilles de calcul ».</span><span class="sxs-lookup"><span data-stu-id="9a50e-253">Select the ‘Sample worksheet report’ configuration.</span></span>  
12. <span data-ttu-id="9a50e-254">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="9a50e-254">Click Save.</span></span>
13. <span data-ttu-id="9a50e-255">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="9a50e-255">Close the page.</span></span>

## <a name="use-the-created-configuration-for-testing-of-payment-journals-processing"></a><span data-ttu-id="9a50e-256">Utiliser la configuration créée pour tester le traitement de journaux des paiements</span><span class="sxs-lookup"><span data-stu-id="9a50e-256">Use the created configuration for testing of payment journals processing</span></span>
1. <span data-ttu-id="9a50e-257">Accédez à Comptabilité fournisseur > Paiements > Journal des paiements.</span><span class="sxs-lookup"><span data-stu-id="9a50e-257">Go to Accounts payable > Payments > Payment journal.</span></span>
2. <span data-ttu-id="9a50e-258">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="9a50e-258">Click New.</span></span>
    * <span data-ttu-id="9a50e-259">Créez un journal des paiements.</span><span class="sxs-lookup"><span data-stu-id="9a50e-259">Create a new payment journal.</span></span>  
3. <span data-ttu-id="9a50e-260">Dans le champ Nom, tapez « VendPay ».</span><span class="sxs-lookup"><span data-stu-id="9a50e-260">In the Name field, type 'VendPay'.</span></span>
    * <span data-ttu-id="9a50e-261">VendPay</span><span class="sxs-lookup"><span data-stu-id="9a50e-261">VendPay</span></span>  
4. <span data-ttu-id="9a50e-262">Cliquez sur Lignes.</span><span class="sxs-lookup"><span data-stu-id="9a50e-262">Click Lines.</span></span>
5. <span data-ttu-id="9a50e-263">Dans le champ Compte, spécifiez les valeurs GB_SI_000001.</span><span class="sxs-lookup"><span data-stu-id="9a50e-263">In the Account field, specify the values 'GB_SI_000001'.</span></span>
    * <span data-ttu-id="9a50e-264">GB_SI_000001</span><span class="sxs-lookup"><span data-stu-id="9a50e-264">GB_SI_000001</span></span>  
6. <span data-ttu-id="9a50e-265">Définissez Débit sur 1000.</span><span class="sxs-lookup"><span data-stu-id="9a50e-265">Set Debit to '1000'.</span></span>
7. <span data-ttu-id="9a50e-266">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="9a50e-266">Click New.</span></span>
8. <span data-ttu-id="9a50e-267">Dans le champ Compte, spécifiez les valeurs GB_SI_000005.</span><span class="sxs-lookup"><span data-stu-id="9a50e-267">In the Account field, specify the values 'GB_SI_000005'.</span></span>
    * <span data-ttu-id="9a50e-268">GB_SI_000005</span><span class="sxs-lookup"><span data-stu-id="9a50e-268">GB_SI_000005</span></span>  
9. <span data-ttu-id="9a50e-269">Définissez Débit sur 2000.</span><span class="sxs-lookup"><span data-stu-id="9a50e-269">Set Debit to '2000'.</span></span>
10. <span data-ttu-id="9a50e-270">Dans le champ Devise, tapez EUR.</span><span class="sxs-lookup"><span data-stu-id="9a50e-270">In the Currency field, type 'EUR'.</span></span>
    * <span data-ttu-id="9a50e-271">EUR</span><span class="sxs-lookup"><span data-stu-id="9a50e-271">EUR</span></span>  
11. <span data-ttu-id="9a50e-272">Spécifiez les valeurs GBSI OPER dans le champ Compte de contrepartie.</span><span class="sxs-lookup"><span data-stu-id="9a50e-272">In the Offset account field, specify the values 'GBSI OPER'.</span></span>
    * <span data-ttu-id="9a50e-273">GBSI OPER</span><span class="sxs-lookup"><span data-stu-id="9a50e-273">GBSI OPER</span></span>  
12. <span data-ttu-id="9a50e-274">Tapez Électronique dans le champ Mode de paiement.</span><span class="sxs-lookup"><span data-stu-id="9a50e-274">In the Method of payment field, type 'Electronic'.</span></span>
    * <span data-ttu-id="9a50e-275">électronique</span><span class="sxs-lookup"><span data-stu-id="9a50e-275">Electronic</span></span>  
13. <span data-ttu-id="9a50e-276">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="9a50e-276">Click Save.</span></span>
14. <span data-ttu-id="9a50e-277">Cliquez sur Générer les paiements.</span><span class="sxs-lookup"><span data-stu-id="9a50e-277">Click Generate payments.</span></span>
15. <span data-ttu-id="9a50e-278">Tapez Électronique dans le champ Mode de paiement.</span><span class="sxs-lookup"><span data-stu-id="9a50e-278">In the Method of payment field, type 'Electronic'.</span></span>
    * <span data-ttu-id="9a50e-279">électronique</span><span class="sxs-lookup"><span data-stu-id="9a50e-279">Electronic</span></span>  
16. <span data-ttu-id="9a50e-280">Dans le champ Nom de fichier, tapez « Paiements ».</span><span class="sxs-lookup"><span data-stu-id="9a50e-280">In the File name field, type 'Payments'.</span></span>
    * <span data-ttu-id="9a50e-281">Par exemple, tapez Paiements.</span><span class="sxs-lookup"><span data-stu-id="9a50e-281">For example, type Payments.</span></span>  
17. <span data-ttu-id="9a50e-282">Tapez GBSI OPER dans le champ Compte bancaire.</span><span class="sxs-lookup"><span data-stu-id="9a50e-282">In the Bank account field, type 'GBSI OPER'.</span></span>
    * <span data-ttu-id="9a50e-283">GBSI OPER</span><span class="sxs-lookup"><span data-stu-id="9a50e-283">GBSI OPER</span></span>  
18. <span data-ttu-id="9a50e-284">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="9a50e-284">Click OK.</span></span>
19. <span data-ttu-id="9a50e-285">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="9a50e-285">Click OK.</span></span>
    * <span data-ttu-id="9a50e-286">Examinez la feuille de calcul créée, notamment les détails des lignes de paiement ainsi que les totaux pour chaque code devise utilisé dans ce message de paiement.</span><span class="sxs-lookup"><span data-stu-id="9a50e-286">Review the created worksheet, including details of payment lines as well as totals for each currency code used in this payment message.</span></span>  


