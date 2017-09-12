--- 
title: "Créer une configuration de format pour la gestion des états électroniques (ER)"
description: "es étapes suivantes expliquent comment un utilisateur dans l'administrateur système ou le rôle Développeur d'états électroniques peut créer une configuration de format pour la génération d'états électronique (ER)."
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
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: 04817d1f1851e43679995641e8b0ff99edaa83ad
ms.contentlocale: fr-fr
ms.lasthandoff: 08/29/2017

---
# <a name="create-a-format-configuration-for-electronic-reporting-er"></a><span data-ttu-id="f330c-103">Créer une configuration de format pour la gestion des états électroniques (ER)</span><span class="sxs-lookup"><span data-stu-id="f330c-103">Create a format configuration for electronic reporting (ER)</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="f330c-104">es étapes suivantes expliquent comment un utilisateur dans l'administrateur système ou le rôle Développeur d'états électroniques peut créer une configuration de format pour la génération d'états électronique (ER).</span><span class="sxs-lookup"><span data-stu-id="f330c-104">The following steps explain how a user in the System Administrator or Electronic Reporting Developer role can create a format configuration for Electronic reporting (ER).</span></span> <span data-ttu-id="f330c-105">Cette configuration de formats définira le format des documents électroniques utilisés pour traiter les paiements.</span><span class="sxs-lookup"><span data-stu-id="f330c-105">This format configuration will define the format of electronic documents that are used for processing payments.</span></span> <span data-ttu-id="f330c-106">Dans cet exemple, vous allez créer une configuration de format pour la société témoin, Litware, Inc. Pour effectuer ces étapes, vous devez d'abord accomplir celles de la procédure « Mettre en relation le modèle aux sources de données sélectionnées ».</span><span class="sxs-lookup"><span data-stu-id="f330c-106">In this example, you will create a format configuration for sample company, Litware, Inc. To complete these steps, you must first complete the steps in the “Map model to selected datasources” procedure.</span></span>


## <a name="create-a-new-format-configuration"></a><span data-ttu-id="f330c-107">Créer une configuration de format</span><span class="sxs-lookup"><span data-stu-id="f330c-107">Create a new format configuration</span></span>
1. <span data-ttu-id="f330c-108">Accédez à Administration d'organisation > Espaces de travail > États électroniques.</span><span class="sxs-lookup"><span data-stu-id="f330c-108">Go to Organization administration > Workspaces > Electronic reporting.</span></span>
2. <span data-ttu-id="f330c-109">Cliquez sur Configurations des états.</span><span class="sxs-lookup"><span data-stu-id="f330c-109">Click Reporting configurations.</span></span>
3. <span data-ttu-id="f330c-110">Dans l'arborescence, sélectionnez « Paiements (modèle simplifié) ».</span><span class="sxs-lookup"><span data-stu-id="f330c-110">In the tree, select 'Payments (simplified model)'.</span></span>
4. <span data-ttu-id="f330c-111">Cliquez sur Créer la configuration pour ouvrir la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="f330c-111">Click Create configuration to open the drop dialog.</span></span>
5. <span data-ttu-id="f330c-112">Dans le champ Nouveau, entrez « Format basé sur le PaymentModel du modèle du paiement ».</span><span class="sxs-lookup"><span data-stu-id="f330c-112">In the New field, enter 'Format based on data model PaymentModel'.</span></span>
6. <span data-ttu-id="f330c-113">Dans le champ Nom, tapez « LE SYSTÈME BACS (R-U factice) ».</span><span class="sxs-lookup"><span data-stu-id="f330c-113">In the Name field, type 'BACS (UK fictitious)'.</span></span>
    * <span data-ttu-id="f330c-114">LE SYSTÈME BACS (R-U factice)</span><span class="sxs-lookup"><span data-stu-id="f330c-114">BACS (UK fictitious)</span></span>  
7. <span data-ttu-id="f330c-115">Dans le champ Description, entrez « Format de paiement fournisseur du SYSTÈME BACS (R-U factice) ».</span><span class="sxs-lookup"><span data-stu-id="f330c-115">In the Description field, type 'BACS vendor payment format (UK fictitious)'.</span></span>
    * <span data-ttu-id="f330c-116">Format de paiement fournisseur du SYSTÈME BACS (R-U factice)</span><span class="sxs-lookup"><span data-stu-id="f330c-116">BACS vendor payment format (UK fictitious)</span></span>  
    * <span data-ttu-id="f330c-117">Le fournisseur de configuration actif est automatiquement entré ici.</span><span class="sxs-lookup"><span data-stu-id="f330c-117">The active configuration provider is automatically entered here.</span></span> <span data-ttu-id="f330c-118">Ce fournisseur pourra mettre à jour cette configuration.</span><span class="sxs-lookup"><span data-stu-id="f330c-118">This provider will be able to maintain this configuration.</span></span> <span data-ttu-id="f330c-119">D'autres fournisseurs peuvent utiliser cette configuration, mais ne peuvent pas la mettre à jour.</span><span class="sxs-lookup"><span data-stu-id="f330c-119">Other providers can use this configuration, but will not be able to maintain it.</span></span>  
    * <span data-ttu-id="f330c-120">Un format spécifique de document électronique peut être défini.</span><span class="sxs-lookup"><span data-stu-id="f330c-120">A particular format of electronic document can be defined.</span></span> <span data-ttu-id="f330c-121">Laissez ce champ vide si vous souhaitez sélectionner un format au moment de l'exécution.</span><span class="sxs-lookup"><span data-stu-id="f330c-121">Leave this field blank if you want to select a format at run-time.</span></span>  
8. <span data-ttu-id="f330c-122">Dans le champ Définition du modèle de données, entrez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="f330c-122">In the Data model definition field, enter or select a value.</span></span>
9. <span data-ttu-id="f330c-123">Cliquez sur Créer une configuration.</span><span class="sxs-lookup"><span data-stu-id="f330c-123">Click Create configuration.</span></span>
    * <span data-ttu-id="f330c-124">Une nouvelle configuration client a été créée.</span><span class="sxs-lookup"><span data-stu-id="f330c-124">A new configuration has been created.</span></span> <span data-ttu-id="f330c-125">La version temporaire peut servir à enregistrer le format de conception pour gérer des documents électroniques.</span><span class="sxs-lookup"><span data-stu-id="f330c-125">The draft version can be used to store the design format for managing electronic documents.</span></span>  

## <a name="design-format-of-electronic-document"></a><span data-ttu-id="f330c-126">Créer le format du document électronique</span><span class="sxs-lookup"><span data-stu-id="f330c-126">Design format of electronic document</span></span>
1. <span data-ttu-id="f330c-127">Cliquez sur Concepteur.</span><span class="sxs-lookup"><span data-stu-id="f330c-127">Click Designer.</span></span>
2. <span data-ttu-id="f330c-128">Cliquez sur Ajouter racine pour ouvrir la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="f330c-128">Click Add root to open the drop dialog.</span></span>
3. <span data-ttu-id="f330c-129">Dans l'arborescence, sélectionnez « Common\File ».</span><span class="sxs-lookup"><span data-stu-id="f330c-129">In the tree, select 'Common\File'.</span></span>
4. <span data-ttu-id="f330c-130">Dans le champ Nom, tapez « Xml ».</span><span class="sxs-lookup"><span data-stu-id="f330c-130">In the Name field, type 'Xml'.</span></span>
    * <span data-ttu-id="f330c-131">XML</span><span class="sxs-lookup"><span data-stu-id="f330c-131">Xml</span></span>  
5. <span data-ttu-id="f330c-132">Dans le champ Encodage, tapez « UTF-8 ».</span><span class="sxs-lookup"><span data-stu-id="f330c-132">In the Encoding field, type 'UTF-8'.</span></span>
    * <span data-ttu-id="f330c-133">UTF-8</span><span class="sxs-lookup"><span data-stu-id="f330c-133">UTF-8</span></span>  
6. <span data-ttu-id="f330c-134">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="f330c-134">Click OK.</span></span>
7. <span data-ttu-id="f330c-135">Cliquez sur Ajouter pour ouvrir la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="f330c-135">Click Add to open the drop dialog.</span></span>
8. <span data-ttu-id="f330c-136">Dans l'arborescence , sélectionnez « XML\Élément ».</span><span class="sxs-lookup"><span data-stu-id="f330c-136">In the tree, select 'XML\Element'.</span></span>
9. <span data-ttu-id="f330c-137">Dans le champ Nom, tapez « Message ».</span><span class="sxs-lookup"><span data-stu-id="f330c-137">In the Name field, type 'Message'.</span></span>
    * <span data-ttu-id="f330c-138">Message</span><span class="sxs-lookup"><span data-stu-id="f330c-138">Message</span></span>  
10. <span data-ttu-id="f330c-139">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="f330c-139">Click OK.</span></span>
11. <span data-ttu-id="f330c-140">Dans l'arborescence, sélectionnez « Xml\Message ».</span><span class="sxs-lookup"><span data-stu-id="f330c-140">In the tree, select 'Xml\Message'.</span></span>
12. <span data-ttu-id="f330c-141">Cliquez sur Ajouter un élément.</span><span class="sxs-lookup"><span data-stu-id="f330c-141">Click Add Element.</span></span>
13. <span data-ttu-id="f330c-142">Dans le champ Nom, tapez « ProcessingDate ».</span><span class="sxs-lookup"><span data-stu-id="f330c-142">In the Name field, type 'ProcessingDate'.</span></span>
    * <span data-ttu-id="f330c-143">ProcessingDate</span><span class="sxs-lookup"><span data-stu-id="f330c-143">ProcessingDate</span></span>  
14. <span data-ttu-id="f330c-144">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="f330c-144">Click OK.</span></span>
15. <span data-ttu-id="f330c-145">Cliquez sur Ajouter un élément.</span><span class="sxs-lookup"><span data-stu-id="f330c-145">Click Add Element.</span></span>
16. <span data-ttu-id="f330c-146">Dans le champ Nom, tapez « MessageId ».</span><span class="sxs-lookup"><span data-stu-id="f330c-146">In the Name field, type 'MessageId'.</span></span>
    * <span data-ttu-id="f330c-147">MessageId</span><span class="sxs-lookup"><span data-stu-id="f330c-147">MessageId</span></span>  
17. <span data-ttu-id="f330c-148">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="f330c-148">Click OK.</span></span>
18. <span data-ttu-id="f330c-149">Cliquez sur Ajouter un élément.</span><span class="sxs-lookup"><span data-stu-id="f330c-149">Click Add Element.</span></span>
19. <span data-ttu-id="f330c-150">Tapez « Paiements » dans le champ Nom.</span><span class="sxs-lookup"><span data-stu-id="f330c-150">In the Name field, type 'Payments'.</span></span>
    * <span data-ttu-id="f330c-151">Paiements</span><span class="sxs-lookup"><span data-stu-id="f330c-151">Payments</span></span>  
20. <span data-ttu-id="f330c-152">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="f330c-152">Click OK.</span></span>
21. <span data-ttu-id="f330c-153">Dans l'arborescence, sélectionnez « Xml\Message\Paiements ».</span><span class="sxs-lookup"><span data-stu-id="f330c-153">In the tree, select 'Xml\Message\Payments'.</span></span>
22. <span data-ttu-id="f330c-154">Cliquez sur Ajouter un élément.</span><span class="sxs-lookup"><span data-stu-id="f330c-154">Click Add Element.</span></span>
23. <span data-ttu-id="f330c-155">Dans le champ Nom, tapez « Article ».</span><span class="sxs-lookup"><span data-stu-id="f330c-155">In the Name field, type 'Item'.</span></span>
    * <span data-ttu-id="f330c-156">Article</span><span class="sxs-lookup"><span data-stu-id="f330c-156">Item</span></span>  
24. <span data-ttu-id="f330c-157">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="f330c-157">Click OK.</span></span>
25. <span data-ttu-id="f330c-158">Dans l'arborescence, sélectionnez « Xml\Message\Paiements\Article ».</span><span class="sxs-lookup"><span data-stu-id="f330c-158">In the tree, select 'Xml\Message\Payments\Item'.</span></span>
26. <span data-ttu-id="f330c-159">Cliquez sur Ajouter pour ouvrir la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="f330c-159">Click Add to open the drop dialog.</span></span>
27. <span data-ttu-id="f330c-160">Dans l'arborescence, sélectionnez « XML\Attribut ».</span><span class="sxs-lookup"><span data-stu-id="f330c-160">In the tree, select 'XML\Attribute'.</span></span>
28. <span data-ttu-id="f330c-161">Dans le champ Nom, tapez « Id ».</span><span class="sxs-lookup"><span data-stu-id="f330c-161">In the Name field, type 'Id'.</span></span>
    * <span data-ttu-id="f330c-162">ID</span><span class="sxs-lookup"><span data-stu-id="f330c-162">Id</span></span>  
29. <span data-ttu-id="f330c-163">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="f330c-163">Click OK.</span></span>
30. <span data-ttu-id="f330c-164">Cliquez sur Ajouter pour ouvrir la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="f330c-164">Click Add to open the drop dialog.</span></span>
31. <span data-ttu-id="f330c-165">Dans l'arborescence , sélectionnez « XML\Élément ».</span><span class="sxs-lookup"><span data-stu-id="f330c-165">In the tree, select 'XML\Element'.</span></span>
32. <span data-ttu-id="f330c-166">Dans le champ Nom, tapez « Fournisseur ».</span><span class="sxs-lookup"><span data-stu-id="f330c-166">In the Name field, type 'Vendor'.</span></span>
    * <span data-ttu-id="f330c-167">Fournisseur</span><span class="sxs-lookup"><span data-stu-id="f330c-167">Vendor</span></span>  
33. <span data-ttu-id="f330c-168">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="f330c-168">Click OK.</span></span>
34. <span data-ttu-id="f330c-169">Dans l'arborescence, sélectionnez « Xml\Message\Paiements\Article\Fournisseur ».</span><span class="sxs-lookup"><span data-stu-id="f330c-169">In the tree, select 'Xml\Message\Payments\Item\Vendor'.</span></span>
35. <span data-ttu-id="f330c-170">Cliquez sur Ajouter un élément.</span><span class="sxs-lookup"><span data-stu-id="f330c-170">Click Add Element.</span></span>
36. <span data-ttu-id="f330c-171">Tapez « Nom » dans le champ Nom.</span><span class="sxs-lookup"><span data-stu-id="f330c-171">In the Name field, type 'Name'.</span></span>
    * <span data-ttu-id="f330c-172">Nom</span><span class="sxs-lookup"><span data-stu-id="f330c-172">Name</span></span>  
37. <span data-ttu-id="f330c-173">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="f330c-173">Click OK.</span></span>
38. <span data-ttu-id="f330c-174">Cliquez sur Ajouter un élément.</span><span class="sxs-lookup"><span data-stu-id="f330c-174">Click Add Element.</span></span>
39. <span data-ttu-id="f330c-175">Dans le champ Nom, tapez « Banque ».</span><span class="sxs-lookup"><span data-stu-id="f330c-175">In the Name field, type 'Bank'.</span></span>
    * <span data-ttu-id="f330c-176">Banque</span><span class="sxs-lookup"><span data-stu-id="f330c-176">Bank</span></span>  
40. <span data-ttu-id="f330c-177">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="f330c-177">Click OK.</span></span>
41. <span data-ttu-id="f330c-178">Dans l'arborescence, sélectionnez « Xml\Message\Paiements\Article\Fournisseur\Banque ».</span><span class="sxs-lookup"><span data-stu-id="f330c-178">In the tree, select 'Xml\Message\Payments\Item\Vendor\Bank'.</span></span>
42. <span data-ttu-id="f330c-179">Cliquez sur Ajouter un élément.</span><span class="sxs-lookup"><span data-stu-id="f330c-179">Click Add Element.</span></span>
43. <span data-ttu-id="f330c-180">Tapez « RoutingNumber » dans le champ Nom.</span><span class="sxs-lookup"><span data-stu-id="f330c-180">In the Name field, type 'RoutingNumber'.</span></span>
    * <span data-ttu-id="f330c-181">RoutingNumber</span><span class="sxs-lookup"><span data-stu-id="f330c-181">RoutingNumber</span></span>  
44. <span data-ttu-id="f330c-182">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="f330c-182">Click OK.</span></span>
45. <span data-ttu-id="f330c-183">Cliquez sur Ajouter un élément.</span><span class="sxs-lookup"><span data-stu-id="f330c-183">Click Add Element.</span></span>
46. <span data-ttu-id="f330c-184">Dans le champ Nom, tapez « AccountNumber ».</span><span class="sxs-lookup"><span data-stu-id="f330c-184">In the Name field, type 'AccountNumber'.</span></span>
    * <span data-ttu-id="f330c-185">Numéro de compte,</span><span class="sxs-lookup"><span data-stu-id="f330c-185">AccountNumber</span></span>  
47. <span data-ttu-id="f330c-186">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="f330c-186">Click OK.</span></span>
48. <span data-ttu-id="f330c-187">Dans l'arborescence, sélectionnez « Xml\Message\Paiements\Article\Fournisseur ».</span><span class="sxs-lookup"><span data-stu-id="f330c-187">In the tree, select 'Xml\Message\Payments\Item\Vendor'.</span></span>
49. <span data-ttu-id="f330c-188">Cliquez sur Copier.</span><span class="sxs-lookup"><span data-stu-id="f330c-188">Click Copy.</span></span>
50. <span data-ttu-id="f330c-189">Dans l'arborescence, sélectionnez « Xml\Message\Paiements\Article ».</span><span class="sxs-lookup"><span data-stu-id="f330c-189">In the tree, select 'Xml\Message\Payments\Item'.</span></span>
51. <span data-ttu-id="f330c-190">Cliquez sur Coller.</span><span class="sxs-lookup"><span data-stu-id="f330c-190">Click Paste.</span></span>
52. <span data-ttu-id="f330c-191">Dans le champ Nom, tapez « Payeur ».</span><span class="sxs-lookup"><span data-stu-id="f330c-191">In the Name field, type 'Payer'.</span></span>
    * <span data-ttu-id="f330c-192">Payeur</span><span class="sxs-lookup"><span data-stu-id="f330c-192">Payer</span></span>  
53. <span data-ttu-id="f330c-193">Dans l'arborescence, sélectionnez « Xml\Message\Paiements\Article ».</span><span class="sxs-lookup"><span data-stu-id="f330c-193">In the tree, select 'Xml\Message\Payments\Item'.</span></span>
54. <span data-ttu-id="f330c-194">Cliquez sur Ajouter un élément.</span><span class="sxs-lookup"><span data-stu-id="f330c-194">Click Add Element.</span></span>
55. <span data-ttu-id="f330c-195">Tapez « Devise » dans le champ Nom.</span><span class="sxs-lookup"><span data-stu-id="f330c-195">In the Name field, type 'Currency'.</span></span>
    * <span data-ttu-id="f330c-196">Devise</span><span class="sxs-lookup"><span data-stu-id="f330c-196">Currency</span></span>  
56. <span data-ttu-id="f330c-197">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="f330c-197">Click OK.</span></span>
57. <span data-ttu-id="f330c-198">Cliquez sur Ajouter un élément.</span><span class="sxs-lookup"><span data-stu-id="f330c-198">Click Add Element.</span></span>
58. <span data-ttu-id="f330c-199">Tapez « Description » dans le champ Nom.</span><span class="sxs-lookup"><span data-stu-id="f330c-199">In the Name field, type 'Description'.</span></span>
    * <span data-ttu-id="f330c-200">Description</span><span class="sxs-lookup"><span data-stu-id="f330c-200">Description</span></span>  
59. <span data-ttu-id="f330c-201">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="f330c-201">Click OK.</span></span>
60. <span data-ttu-id="f330c-202">Cliquez sur Ajouter un élément.</span><span class="sxs-lookup"><span data-stu-id="f330c-202">Click Add Element.</span></span>
61. <span data-ttu-id="f330c-203">Dans le champ Nom, tapez « TransDate ».</span><span class="sxs-lookup"><span data-stu-id="f330c-203">In the Name field, type 'TransDate'.</span></span>
    * <span data-ttu-id="f330c-204">Date de transaction</span><span class="sxs-lookup"><span data-stu-id="f330c-204">TransDate</span></span>  
62. <span data-ttu-id="f330c-205">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="f330c-205">Click OK.</span></span>
63. <span data-ttu-id="f330c-206">Cliquez sur Ajouter un élément.</span><span class="sxs-lookup"><span data-stu-id="f330c-206">Click Add Element.</span></span>
64. <span data-ttu-id="f330c-207">Dans le champ Nom, tapez « Montant ».</span><span class="sxs-lookup"><span data-stu-id="f330c-207">In the Name field, type 'Amount'.</span></span>
    * <span data-ttu-id="f330c-208">Montant</span><span class="sxs-lookup"><span data-stu-id="f330c-208">Amount</span></span>  
65. <span data-ttu-id="f330c-209">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="f330c-209">Click OK.</span></span>

## <a name="prepare-format-components-for-mapping-to-data-model-elements"></a><span data-ttu-id="f330c-210">Préparer des composants de format pour la mise en correspondance aux éléments de modèle de données</span><span class="sxs-lookup"><span data-stu-id="f330c-210">Prepare format components for mapping to data model elements</span></span>
1. <span data-ttu-id="f330c-211">Dans l'arborescence, sélectionnez « Xml\Message\ProcessingDate ».</span><span class="sxs-lookup"><span data-stu-id="f330c-211">In the tree, select 'Xml\Message\ProcessingDate'.</span></span>
2. <span data-ttu-id="f330c-212">Cliquez sur Ajouter pour ouvrir la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="f330c-212">Click Add to open the drop dialog.</span></span>
3. <span data-ttu-id="f330c-213">Dans l'arborescence, sélectionnez « Texte\DateTime ».</span><span class="sxs-lookup"><span data-stu-id="f330c-213">In the tree, select 'Text\DateTime'.</span></span>
4. <span data-ttu-id="f330c-214">Dans le champ Format, tapez « jj-mm-aaaa ».</span><span class="sxs-lookup"><span data-stu-id="f330c-214">In the Format field, type 'yyyy-MM-dd'.</span></span>
    * <span data-ttu-id="f330c-215">aaaa/MM/jj</span><span class="sxs-lookup"><span data-stu-id="f330c-215">yyyy-MM-dd</span></span>  
5. <span data-ttu-id="f330c-216">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="f330c-216">Click OK.</span></span>
6. <span data-ttu-id="f330c-217">Dans l'arborescence, sélectionnez « Xml\Message\Paiements\Article\TransDate ».</span><span class="sxs-lookup"><span data-stu-id="f330c-217">In the tree, select 'Xml\Message\Payments\Item\TransDate'.</span></span>
7. <span data-ttu-id="f330c-218">Cliquez sur Ajouter DateTime.</span><span class="sxs-lookup"><span data-stu-id="f330c-218">Click Add DateTime.</span></span>
8. <span data-ttu-id="f330c-219">Dans le champ Format, tapez « jj-mm-aaaa ».</span><span class="sxs-lookup"><span data-stu-id="f330c-219">In the Format field, type 'yyyy-MM-dd'.</span></span>
    * <span data-ttu-id="f330c-220">aaaa/MM/jj</span><span class="sxs-lookup"><span data-stu-id="f330c-220">yyyy-MM-dd</span></span>  
9. <span data-ttu-id="f330c-221">Dans le champ de type DateTime, sélectionnez « Date »</span><span class="sxs-lookup"><span data-stu-id="f330c-221">In the DateTime type field, select 'Date'.</span></span>
10. <span data-ttu-id="f330c-222">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="f330c-222">Click OK.</span></span>
11. <span data-ttu-id="f330c-223">Dans l'arborescence, sélectionnez « Xml\Message\MessageId ».</span><span class="sxs-lookup"><span data-stu-id="f330c-223">In the tree, select 'Xml\Message\MessageId'.</span></span>
12. <span data-ttu-id="f330c-224">Cliquez sur Ajouter pour ouvrir la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="f330c-224">Click Add to open the drop dialog.</span></span>
13. <span data-ttu-id="f330c-225">Dans l'arborescence, sélectionnez « Texte\Chaîne ».</span><span class="sxs-lookup"><span data-stu-id="f330c-225">In the tree, select 'Text\String'.</span></span>
14. <span data-ttu-id="f330c-226">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="f330c-226">Click OK.</span></span>
15. <span data-ttu-id="f330c-227">Dans l'arborescence, sélectionnez « Xml\Message\Paiements\Article\Fournisseur\Nom ».</span><span class="sxs-lookup"><span data-stu-id="f330c-227">In the tree, select 'Xml\Message\Payments\Item\Vendor\Name'.</span></span>
16. <span data-ttu-id="f330c-228">Cliquez sur Ajouter une chaîne.</span><span class="sxs-lookup"><span data-stu-id="f330c-228">Click Add String.</span></span>
17. <span data-ttu-id="f330c-229">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="f330c-229">Click OK.</span></span>
18. <span data-ttu-id="f330c-230">Dans l'arborescence, sélectionnez « Xml\Message\Paiements\Article\Fournisseur\Banque\RoutingNumber ».</span><span class="sxs-lookup"><span data-stu-id="f330c-230">In the tree, select 'Xml\Message\Payments\Item\Vendor\Bank\RoutingNumber'.</span></span>
19. <span data-ttu-id="f330c-231">Cliquez sur Ajouter une chaîne.</span><span class="sxs-lookup"><span data-stu-id="f330c-231">Click Add String.</span></span>
20. <span data-ttu-id="f330c-232">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="f330c-232">Click OK.</span></span>
21. <span data-ttu-id="f330c-233">Dans l'arborescence, sélectionnez « Xml\Message\Paiements\Article\Fournisseur\Banque\AccountNumber ».</span><span class="sxs-lookup"><span data-stu-id="f330c-233">In the tree, select 'Xml\Message\Payments\Item\Vendor\Bank\AccountNumber'.</span></span>
22. <span data-ttu-id="f330c-234">Cliquez sur Ajouter une chaîne.</span><span class="sxs-lookup"><span data-stu-id="f330c-234">Click Add String.</span></span>
23. <span data-ttu-id="f330c-235">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="f330c-235">Click OK.</span></span>
24. <span data-ttu-id="f330c-236">Dans l'arborescence, sélectionnez « Xml\Message\Paiements\Article\Payeur\Nom ».</span><span class="sxs-lookup"><span data-stu-id="f330c-236">In the tree, select 'Xml\Message\Payments\Item\Payer\Name'.</span></span>
25. <span data-ttu-id="f330c-237">Cliquez sur Ajouter une chaîne.</span><span class="sxs-lookup"><span data-stu-id="f330c-237">Click Add String.</span></span>
26. <span data-ttu-id="f330c-238">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="f330c-238">Click OK.</span></span>
27. <span data-ttu-id="f330c-239">Dans l'arborescence, sélectionnez « Xml\Message\Paiements\Article\Payeur\Banque\RoutingNumber ».</span><span class="sxs-lookup"><span data-stu-id="f330c-239">In the tree, select 'Xml\Message\Payments\Item\Payer\Bank\RoutingNumber'.</span></span>
28. <span data-ttu-id="f330c-240">Cliquez sur Ajouter une chaîne.</span><span class="sxs-lookup"><span data-stu-id="f330c-240">Click Add String.</span></span>
29. <span data-ttu-id="f330c-241">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="f330c-241">Click OK.</span></span>
30. <span data-ttu-id="f330c-242">Dans l'arborescence, sélectionnez « Xml\Message\Paiements\Article\Payeur\Banque\AccountNumber ».</span><span class="sxs-lookup"><span data-stu-id="f330c-242">In the tree, select 'Xml\Message\Payments\Item\Payer\Bank\AccountNumber'.</span></span>
31. <span data-ttu-id="f330c-243">Cliquez sur Ajouter une chaîne.</span><span class="sxs-lookup"><span data-stu-id="f330c-243">Click Add String.</span></span>
32. <span data-ttu-id="f330c-244">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="f330c-244">Click OK.</span></span>
33. <span data-ttu-id="f330c-245">Dans l'arborescence, sélectionnez « Xml\Message\Paiements\Article\Devise ».</span><span class="sxs-lookup"><span data-stu-id="f330c-245">In the tree, select 'Xml\Message\Payments\Item\Currency'.</span></span>
34. <span data-ttu-id="f330c-246">Cliquez sur Ajouter une chaîne.</span><span class="sxs-lookup"><span data-stu-id="f330c-246">Click Add String.</span></span>
35. <span data-ttu-id="f330c-247">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="f330c-247">Click OK.</span></span>
36. <span data-ttu-id="f330c-248">Dans l'arborescence, sélectionnez « Xml\Message\Paiements\Article\Description ».</span><span class="sxs-lookup"><span data-stu-id="f330c-248">In the tree, select 'Xml\Message\Payments\Item\Description'.</span></span>
37. <span data-ttu-id="f330c-249">Cliquez sur Ajouter une chaîne.</span><span class="sxs-lookup"><span data-stu-id="f330c-249">Click Add String.</span></span>
38. <span data-ttu-id="f330c-250">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="f330c-250">Click OK.</span></span>
39. <span data-ttu-id="f330c-251">Dans l'arborescence, sélectionnez « Xml\Message\Paiements\Article\Montant ».</span><span class="sxs-lookup"><span data-stu-id="f330c-251">In the tree, select 'Xml\Message\Payments\Item\Amount'.</span></span>
40. <span data-ttu-id="f330c-252">Cliquez sur Ajouter une chaîne.</span><span class="sxs-lookup"><span data-stu-id="f330c-252">Click Add String.</span></span>
41. <span data-ttu-id="f330c-253">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="f330c-253">Click OK.</span></span>
42. <span data-ttu-id="f330c-254">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="f330c-254">Click Save.</span></span>
43. <span data-ttu-id="f330c-255">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="f330c-255">Close the page.</span></span>


