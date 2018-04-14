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
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: ef33fec0162e3b379bc8fe563d37a88fa35dfc85
ms.contentlocale: fr-fr
ms.lasthandoff: 04/13/2018

---
# <a name="create-a-format-configuration-for-electronic-reporting-er"></a><span data-ttu-id="df43d-103">Créer une configuration de format pour la gestion des états électroniques (ER)</span><span class="sxs-lookup"><span data-stu-id="df43d-103">Create a format configuration for electronic reporting (ER)</span></span>

[!INCLUDE [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="df43d-104">es étapes suivantes expliquent comment un utilisateur dans l'administrateur système ou le rôle Développeur d'états électroniques peut créer une configuration de format pour la génération d'états électronique (ER).</span><span class="sxs-lookup"><span data-stu-id="df43d-104">The following steps explain how a user in the System Administrator or Electronic Reporting Developer role can create a format configuration for Electronic reporting (ER).</span></span> <span data-ttu-id="df43d-105">Cette configuration de formats définira le format des documents électroniques utilisés pour traiter les paiements.</span><span class="sxs-lookup"><span data-stu-id="df43d-105">This format configuration will define the format of electronic documents that are used for processing payments.</span></span> <span data-ttu-id="df43d-106">Dans cet exemple, vous allez créer une configuration de format pour la société témoin, Litware, Inc. Pour effectuer ces étapes, vous devez d'abord accomplir celles de la procédure « Mettre en relation le modèle aux sources de données sélectionnées ».</span><span class="sxs-lookup"><span data-stu-id="df43d-106">In this example, you will create a format configuration for sample company, Litware, Inc. To complete these steps, you must first complete the steps in the “Map model to selected datasources” procedure.</span></span>


## <a name="create-a-new-format-configuration"></a><span data-ttu-id="df43d-107">Créer une configuration de format</span><span class="sxs-lookup"><span data-stu-id="df43d-107">Create a new format configuration</span></span>
1. <span data-ttu-id="df43d-108">Accédez à Administration d'organisation > Espaces de travail > États électroniques.</span><span class="sxs-lookup"><span data-stu-id="df43d-108">Go to Organization administration > Workspaces > Electronic reporting.</span></span>
2. <span data-ttu-id="df43d-109">Cliquez sur Configurations des états.</span><span class="sxs-lookup"><span data-stu-id="df43d-109">Click Reporting configurations.</span></span>
3. <span data-ttu-id="df43d-110">Dans l'arborescence, sélectionnez « Paiements (modèle simplifié) ».</span><span class="sxs-lookup"><span data-stu-id="df43d-110">In the tree, select 'Payments (simplified model)'.</span></span>
4. <span data-ttu-id="df43d-111">Cliquez sur Créer la configuration pour ouvrir la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="df43d-111">Click Create configuration to open the drop dialog.</span></span>
5. <span data-ttu-id="df43d-112">Dans le champ Nouveau, entrez « Format basé sur le PaymentModel du modèle du paiement ».</span><span class="sxs-lookup"><span data-stu-id="df43d-112">In the New field, enter 'Format based on data model PaymentModel'.</span></span>
6. <span data-ttu-id="df43d-113">Dans le champ Nom, tapez « LE SYSTÈME BACS (R-U factice) ».</span><span class="sxs-lookup"><span data-stu-id="df43d-113">In the Name field, type 'BACS (UK fictitious)'.</span></span>
    * <span data-ttu-id="df43d-114">LE SYSTÈME BACS (R-U factice)</span><span class="sxs-lookup"><span data-stu-id="df43d-114">BACS (UK fictitious)</span></span>  
7. <span data-ttu-id="df43d-115">Dans le champ Description, entrez « Format de paiement fournisseur du SYSTÈME BACS (R-U factice) ».</span><span class="sxs-lookup"><span data-stu-id="df43d-115">In the Description field, type 'BACS vendor payment format (UK fictitious)'.</span></span>
    * <span data-ttu-id="df43d-116">Format de paiement fournisseur du SYSTÈME BACS (R-U factice)</span><span class="sxs-lookup"><span data-stu-id="df43d-116">BACS vendor payment format (UK fictitious)</span></span>  
    * <span data-ttu-id="df43d-117">Le fournisseur de configuration actif est automatiquement entré ici.</span><span class="sxs-lookup"><span data-stu-id="df43d-117">The active configuration provider is automatically entered here.</span></span> <span data-ttu-id="df43d-118">Ce fournisseur pourra mettre à jour cette configuration.</span><span class="sxs-lookup"><span data-stu-id="df43d-118">This provider will be able to maintain this configuration.</span></span> <span data-ttu-id="df43d-119">D'autres fournisseurs peuvent utiliser cette configuration, mais ne peuvent pas la mettre à jour.</span><span class="sxs-lookup"><span data-stu-id="df43d-119">Other providers can use this configuration, but will not be able to maintain it.</span></span>  
    * <span data-ttu-id="df43d-120">Un format spécifique de document électronique peut être défini.</span><span class="sxs-lookup"><span data-stu-id="df43d-120">A particular format of electronic document can be defined.</span></span> <span data-ttu-id="df43d-121">Laissez ce champ vide si vous souhaitez sélectionner un format au moment de l'exécution.</span><span class="sxs-lookup"><span data-stu-id="df43d-121">Leave this field blank if you want to select a format at run-time.</span></span>  
8. <span data-ttu-id="df43d-122">Dans le champ Définition du modèle de données, entrez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="df43d-122">In the Data model definition field, enter or select a value.</span></span>
9. <span data-ttu-id="df43d-123">Cliquez sur Créer une configuration.</span><span class="sxs-lookup"><span data-stu-id="df43d-123">Click Create configuration.</span></span>
    * <span data-ttu-id="df43d-124">Une nouvelle configuration client a été créée.</span><span class="sxs-lookup"><span data-stu-id="df43d-124">A new configuration has been created.</span></span> <span data-ttu-id="df43d-125">La version temporaire peut servir à enregistrer le format de conception pour gérer des documents électroniques.</span><span class="sxs-lookup"><span data-stu-id="df43d-125">The draft version can be used to store the design format for managing electronic documents.</span></span>  

## <a name="design-format-of-electronic-document"></a><span data-ttu-id="df43d-126">Créer le format du document électronique</span><span class="sxs-lookup"><span data-stu-id="df43d-126">Design format of electronic document</span></span>
1. <span data-ttu-id="df43d-127">Cliquez sur Concepteur.</span><span class="sxs-lookup"><span data-stu-id="df43d-127">Click Designer.</span></span>
2. <span data-ttu-id="df43d-128">Cliquez sur Ajouter racine pour ouvrir la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="df43d-128">Click Add root to open the drop dialog.</span></span>
3. <span data-ttu-id="df43d-129">Dans l'arborescence, sélectionnez « Common\File ».</span><span class="sxs-lookup"><span data-stu-id="df43d-129">In the tree, select 'Common\File'.</span></span>
4. <span data-ttu-id="df43d-130">Dans le champ Nom, tapez « Xml ».</span><span class="sxs-lookup"><span data-stu-id="df43d-130">In the Name field, type 'Xml'.</span></span>
    * <span data-ttu-id="df43d-131">XML</span><span class="sxs-lookup"><span data-stu-id="df43d-131">Xml</span></span>  
5. <span data-ttu-id="df43d-132">Dans le champ Encodage, tapez « UTF-8 ».</span><span class="sxs-lookup"><span data-stu-id="df43d-132">In the Encoding field, type 'UTF-8'.</span></span>
    * <span data-ttu-id="df43d-133">UTF-8</span><span class="sxs-lookup"><span data-stu-id="df43d-133">UTF-8</span></span>  
6. <span data-ttu-id="df43d-134">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="df43d-134">Click OK.</span></span>
7. <span data-ttu-id="df43d-135">Cliquez sur Ajouter pour ouvrir la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="df43d-135">Click Add to open the drop dialog.</span></span>
8. <span data-ttu-id="df43d-136">Dans l'arborescence , sélectionnez « XML\Élément ».</span><span class="sxs-lookup"><span data-stu-id="df43d-136">In the tree, select 'XML\Element'.</span></span>
9. <span data-ttu-id="df43d-137">Dans le champ Nom, tapez « Message ».</span><span class="sxs-lookup"><span data-stu-id="df43d-137">In the Name field, type 'Message'.</span></span>
    * <span data-ttu-id="df43d-138">Message</span><span class="sxs-lookup"><span data-stu-id="df43d-138">Message</span></span>  
10. <span data-ttu-id="df43d-139">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="df43d-139">Click OK.</span></span>
11. <span data-ttu-id="df43d-140">Dans l'arborescence, sélectionnez « Xml\Message ».</span><span class="sxs-lookup"><span data-stu-id="df43d-140">In the tree, select 'Xml\Message'.</span></span>
12. <span data-ttu-id="df43d-141">Cliquez sur Ajouter un élément.</span><span class="sxs-lookup"><span data-stu-id="df43d-141">Click Add Element.</span></span>
13. <span data-ttu-id="df43d-142">Dans le champ Nom, tapez « ProcessingDate ».</span><span class="sxs-lookup"><span data-stu-id="df43d-142">In the Name field, type 'ProcessingDate'.</span></span>
    * <span data-ttu-id="df43d-143">ProcessingDate</span><span class="sxs-lookup"><span data-stu-id="df43d-143">ProcessingDate</span></span>  
14. <span data-ttu-id="df43d-144">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="df43d-144">Click OK.</span></span>
15. <span data-ttu-id="df43d-145">Cliquez sur Ajouter un élément.</span><span class="sxs-lookup"><span data-stu-id="df43d-145">Click Add Element.</span></span>
16. <span data-ttu-id="df43d-146">Dans le champ Nom, tapez « MessageId ».</span><span class="sxs-lookup"><span data-stu-id="df43d-146">In the Name field, type 'MessageId'.</span></span>
    * <span data-ttu-id="df43d-147">MessageId</span><span class="sxs-lookup"><span data-stu-id="df43d-147">MessageId</span></span>  
17. <span data-ttu-id="df43d-148">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="df43d-148">Click OK.</span></span>
18. <span data-ttu-id="df43d-149">Cliquez sur Ajouter un élément.</span><span class="sxs-lookup"><span data-stu-id="df43d-149">Click Add Element.</span></span>
19. <span data-ttu-id="df43d-150">Tapez « Paiements » dans le champ Nom.</span><span class="sxs-lookup"><span data-stu-id="df43d-150">In the Name field, type 'Payments'.</span></span>
    * <span data-ttu-id="df43d-151">Paiements</span><span class="sxs-lookup"><span data-stu-id="df43d-151">Payments</span></span>  
20. <span data-ttu-id="df43d-152">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="df43d-152">Click OK.</span></span>
21. <span data-ttu-id="df43d-153">Dans l'arborescence, sélectionnez « Xml\Message\Paiements ».</span><span class="sxs-lookup"><span data-stu-id="df43d-153">In the tree, select 'Xml\Message\Payments'.</span></span>
22. <span data-ttu-id="df43d-154">Cliquez sur Ajouter un élément.</span><span class="sxs-lookup"><span data-stu-id="df43d-154">Click Add Element.</span></span>
23. <span data-ttu-id="df43d-155">Dans le champ Nom, tapez « Article ».</span><span class="sxs-lookup"><span data-stu-id="df43d-155">In the Name field, type 'Item'.</span></span>
    * <span data-ttu-id="df43d-156">Article</span><span class="sxs-lookup"><span data-stu-id="df43d-156">Item</span></span>  
24. <span data-ttu-id="df43d-157">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="df43d-157">Click OK.</span></span>
25. <span data-ttu-id="df43d-158">Dans l'arborescence, sélectionnez « Xml\Message\Paiements\Article ».</span><span class="sxs-lookup"><span data-stu-id="df43d-158">In the tree, select 'Xml\Message\Payments\Item'.</span></span>
26. <span data-ttu-id="df43d-159">Cliquez sur Ajouter pour ouvrir la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="df43d-159">Click Add to open the drop dialog.</span></span>
27. <span data-ttu-id="df43d-160">Dans l'arborescence, sélectionnez « XML\Attribut ».</span><span class="sxs-lookup"><span data-stu-id="df43d-160">In the tree, select 'XML\Attribute'.</span></span>
28. <span data-ttu-id="df43d-161">Dans le champ Nom, tapez « Id ».</span><span class="sxs-lookup"><span data-stu-id="df43d-161">In the Name field, type 'Id'.</span></span>
    * <span data-ttu-id="df43d-162">ID</span><span class="sxs-lookup"><span data-stu-id="df43d-162">Id</span></span>  
29. <span data-ttu-id="df43d-163">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="df43d-163">Click OK.</span></span>
30. <span data-ttu-id="df43d-164">Cliquez sur Ajouter pour ouvrir la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="df43d-164">Click Add to open the drop dialog.</span></span>
31. <span data-ttu-id="df43d-165">Dans l'arborescence , sélectionnez « XML\Élément ».</span><span class="sxs-lookup"><span data-stu-id="df43d-165">In the tree, select 'XML\Element'.</span></span>
32. <span data-ttu-id="df43d-166">Dans le champ Nom, tapez « Fournisseur ».</span><span class="sxs-lookup"><span data-stu-id="df43d-166">In the Name field, type 'Vendor'.</span></span>
    * <span data-ttu-id="df43d-167">Fournisseur</span><span class="sxs-lookup"><span data-stu-id="df43d-167">Vendor</span></span>  
33. <span data-ttu-id="df43d-168">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="df43d-168">Click OK.</span></span>
34. <span data-ttu-id="df43d-169">Dans l'arborescence, sélectionnez « Xml\Message\Paiements\Article\Fournisseur ».</span><span class="sxs-lookup"><span data-stu-id="df43d-169">In the tree, select 'Xml\Message\Payments\Item\Vendor'.</span></span>
35. <span data-ttu-id="df43d-170">Cliquez sur Ajouter un élément.</span><span class="sxs-lookup"><span data-stu-id="df43d-170">Click Add Element.</span></span>
36. <span data-ttu-id="df43d-171">Tapez « Nom » dans le champ Nom.</span><span class="sxs-lookup"><span data-stu-id="df43d-171">In the Name field, type 'Name'.</span></span>
    * <span data-ttu-id="df43d-172">Nom</span><span class="sxs-lookup"><span data-stu-id="df43d-172">Name</span></span>  
37. <span data-ttu-id="df43d-173">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="df43d-173">Click OK.</span></span>
38. <span data-ttu-id="df43d-174">Cliquez sur Ajouter un élément.</span><span class="sxs-lookup"><span data-stu-id="df43d-174">Click Add Element.</span></span>
39. <span data-ttu-id="df43d-175">Dans le champ Nom, tapez « Banque ».</span><span class="sxs-lookup"><span data-stu-id="df43d-175">In the Name field, type 'Bank'.</span></span>
    * <span data-ttu-id="df43d-176">Banque</span><span class="sxs-lookup"><span data-stu-id="df43d-176">Bank</span></span>  
40. <span data-ttu-id="df43d-177">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="df43d-177">Click OK.</span></span>
41. <span data-ttu-id="df43d-178">Dans l'arborescence, sélectionnez « Xml\Message\Paiements\Article\Fournisseur\Banque ».</span><span class="sxs-lookup"><span data-stu-id="df43d-178">In the tree, select 'Xml\Message\Payments\Item\Vendor\Bank'.</span></span>
42. <span data-ttu-id="df43d-179">Cliquez sur Ajouter un élément.</span><span class="sxs-lookup"><span data-stu-id="df43d-179">Click Add Element.</span></span>
43. <span data-ttu-id="df43d-180">Tapez « RoutingNumber » dans le champ Nom.</span><span class="sxs-lookup"><span data-stu-id="df43d-180">In the Name field, type 'RoutingNumber'.</span></span>
    * <span data-ttu-id="df43d-181">RoutingNumber</span><span class="sxs-lookup"><span data-stu-id="df43d-181">RoutingNumber</span></span>  
44. <span data-ttu-id="df43d-182">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="df43d-182">Click OK.</span></span>
45. <span data-ttu-id="df43d-183">Cliquez sur Ajouter un élément.</span><span class="sxs-lookup"><span data-stu-id="df43d-183">Click Add Element.</span></span>
46. <span data-ttu-id="df43d-184">Dans le champ Nom, tapez « AccountNumber ».</span><span class="sxs-lookup"><span data-stu-id="df43d-184">In the Name field, type 'AccountNumber'.</span></span>
    * <span data-ttu-id="df43d-185">Numéro de compte,</span><span class="sxs-lookup"><span data-stu-id="df43d-185">AccountNumber</span></span>  
47. <span data-ttu-id="df43d-186">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="df43d-186">Click OK.</span></span>
48. <span data-ttu-id="df43d-187">Dans l'arborescence, sélectionnez « Xml\Message\Paiements\Article\Fournisseur ».</span><span class="sxs-lookup"><span data-stu-id="df43d-187">In the tree, select 'Xml\Message\Payments\Item\Vendor'.</span></span>
49. <span data-ttu-id="df43d-188">Cliquez sur Copier.</span><span class="sxs-lookup"><span data-stu-id="df43d-188">Click Copy.</span></span>
50. <span data-ttu-id="df43d-189">Dans l'arborescence, sélectionnez « Xml\Message\Paiements\Article ».</span><span class="sxs-lookup"><span data-stu-id="df43d-189">In the tree, select 'Xml\Message\Payments\Item'.</span></span>
51. <span data-ttu-id="df43d-190">Cliquez sur Coller.</span><span class="sxs-lookup"><span data-stu-id="df43d-190">Click Paste.</span></span>
52. <span data-ttu-id="df43d-191">Dans le champ Nom, tapez « Payeur ».</span><span class="sxs-lookup"><span data-stu-id="df43d-191">In the Name field, type 'Payer'.</span></span>
    * <span data-ttu-id="df43d-192">Payeur</span><span class="sxs-lookup"><span data-stu-id="df43d-192">Payer</span></span>  
53. <span data-ttu-id="df43d-193">Dans l'arborescence, sélectionnez « Xml\Message\Paiements\Article ».</span><span class="sxs-lookup"><span data-stu-id="df43d-193">In the tree, select 'Xml\Message\Payments\Item'.</span></span>
54. <span data-ttu-id="df43d-194">Cliquez sur Ajouter un élément.</span><span class="sxs-lookup"><span data-stu-id="df43d-194">Click Add Element.</span></span>
55. <span data-ttu-id="df43d-195">Tapez « Devise » dans le champ Nom.</span><span class="sxs-lookup"><span data-stu-id="df43d-195">In the Name field, type 'Currency'.</span></span>
    * <span data-ttu-id="df43d-196">Devise</span><span class="sxs-lookup"><span data-stu-id="df43d-196">Currency</span></span>  
56. <span data-ttu-id="df43d-197">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="df43d-197">Click OK.</span></span>
57. <span data-ttu-id="df43d-198">Cliquez sur Ajouter un élément.</span><span class="sxs-lookup"><span data-stu-id="df43d-198">Click Add Element.</span></span>
58. <span data-ttu-id="df43d-199">Tapez « Description » dans le champ Nom.</span><span class="sxs-lookup"><span data-stu-id="df43d-199">In the Name field, type 'Description'.</span></span>
    * <span data-ttu-id="df43d-200">Description</span><span class="sxs-lookup"><span data-stu-id="df43d-200">Description</span></span>  
59. <span data-ttu-id="df43d-201">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="df43d-201">Click OK.</span></span>
60. <span data-ttu-id="df43d-202">Cliquez sur Ajouter un élément.</span><span class="sxs-lookup"><span data-stu-id="df43d-202">Click Add Element.</span></span>
61. <span data-ttu-id="df43d-203">Dans le champ Nom, tapez « TransDate ».</span><span class="sxs-lookup"><span data-stu-id="df43d-203">In the Name field, type 'TransDate'.</span></span>
    * <span data-ttu-id="df43d-204">Date de transaction</span><span class="sxs-lookup"><span data-stu-id="df43d-204">TransDate</span></span>  
62. <span data-ttu-id="df43d-205">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="df43d-205">Click OK.</span></span>
63. <span data-ttu-id="df43d-206">Cliquez sur Ajouter un élément.</span><span class="sxs-lookup"><span data-stu-id="df43d-206">Click Add Element.</span></span>
64. <span data-ttu-id="df43d-207">Dans le champ Nom, tapez « Montant ».</span><span class="sxs-lookup"><span data-stu-id="df43d-207">In the Name field, type 'Amount'.</span></span>
    * <span data-ttu-id="df43d-208">Montant</span><span class="sxs-lookup"><span data-stu-id="df43d-208">Amount</span></span>  
65. <span data-ttu-id="df43d-209">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="df43d-209">Click OK.</span></span>

## <a name="prepare-format-components-for-mapping-to-data-model-elements"></a><span data-ttu-id="df43d-210">Préparer des composants de format pour la mise en correspondance aux éléments de modèle de données</span><span class="sxs-lookup"><span data-stu-id="df43d-210">Prepare format components for mapping to data model elements</span></span>
1. <span data-ttu-id="df43d-211">Dans l'arborescence, sélectionnez « Xml\Message\ProcessingDate ».</span><span class="sxs-lookup"><span data-stu-id="df43d-211">In the tree, select 'Xml\Message\ProcessingDate'.</span></span>
2. <span data-ttu-id="df43d-212">Cliquez sur Ajouter pour ouvrir la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="df43d-212">Click Add to open the drop dialog.</span></span>
3. <span data-ttu-id="df43d-213">Dans l'arborescence, sélectionnez « Texte\DateTime ».</span><span class="sxs-lookup"><span data-stu-id="df43d-213">In the tree, select 'Text\DateTime'.</span></span>
4. <span data-ttu-id="df43d-214">Dans le champ Format, tapez « jj-mm-aaaa ».</span><span class="sxs-lookup"><span data-stu-id="df43d-214">In the Format field, type 'yyyy-MM-dd'.</span></span>
    * <span data-ttu-id="df43d-215">aaaa/MM/jj</span><span class="sxs-lookup"><span data-stu-id="df43d-215">yyyy-MM-dd</span></span>  
5. <span data-ttu-id="df43d-216">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="df43d-216">Click OK.</span></span>
6. <span data-ttu-id="df43d-217">Dans l'arborescence, sélectionnez « Xml\Message\Paiements\Article\TransDate ».</span><span class="sxs-lookup"><span data-stu-id="df43d-217">In the tree, select 'Xml\Message\Payments\Item\TransDate'.</span></span>
7. <span data-ttu-id="df43d-218">Cliquez sur Ajouter DateTime.</span><span class="sxs-lookup"><span data-stu-id="df43d-218">Click Add DateTime.</span></span>
8. <span data-ttu-id="df43d-219">Dans le champ Format, tapez « jj-mm-aaaa ».</span><span class="sxs-lookup"><span data-stu-id="df43d-219">In the Format field, type 'yyyy-MM-dd'.</span></span>
    * <span data-ttu-id="df43d-220">aaaa/MM/jj</span><span class="sxs-lookup"><span data-stu-id="df43d-220">yyyy-MM-dd</span></span>  
9. <span data-ttu-id="df43d-221">Dans le champ de type DateTime, sélectionnez « Date »</span><span class="sxs-lookup"><span data-stu-id="df43d-221">In the DateTime type field, select 'Date'.</span></span>
10. <span data-ttu-id="df43d-222">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="df43d-222">Click OK.</span></span>
11. <span data-ttu-id="df43d-223">Dans l'arborescence, sélectionnez « Xml\Message\MessageId ».</span><span class="sxs-lookup"><span data-stu-id="df43d-223">In the tree, select 'Xml\Message\MessageId'.</span></span>
12. <span data-ttu-id="df43d-224">Cliquez sur Ajouter pour ouvrir la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="df43d-224">Click Add to open the drop dialog.</span></span>
13. <span data-ttu-id="df43d-225">Dans l'arborescence, sélectionnez « Texte\Chaîne ».</span><span class="sxs-lookup"><span data-stu-id="df43d-225">In the tree, select 'Text\String'.</span></span>
14. <span data-ttu-id="df43d-226">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="df43d-226">Click OK.</span></span>
15. <span data-ttu-id="df43d-227">Dans l'arborescence, sélectionnez « Xml\Message\Paiements\Article\Fournisseur\Nom ».</span><span class="sxs-lookup"><span data-stu-id="df43d-227">In the tree, select 'Xml\Message\Payments\Item\Vendor\Name'.</span></span>
16. <span data-ttu-id="df43d-228">Cliquez sur Ajouter une chaîne.</span><span class="sxs-lookup"><span data-stu-id="df43d-228">Click Add String.</span></span>
17. <span data-ttu-id="df43d-229">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="df43d-229">Click OK.</span></span>
18. <span data-ttu-id="df43d-230">Dans l'arborescence, sélectionnez « Xml\Message\Paiements\Article\Fournisseur\Banque\RoutingNumber ».</span><span class="sxs-lookup"><span data-stu-id="df43d-230">In the tree, select 'Xml\Message\Payments\Item\Vendor\Bank\RoutingNumber'.</span></span>
19. <span data-ttu-id="df43d-231">Cliquez sur Ajouter une chaîne.</span><span class="sxs-lookup"><span data-stu-id="df43d-231">Click Add String.</span></span>
20. <span data-ttu-id="df43d-232">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="df43d-232">Click OK.</span></span>
21. <span data-ttu-id="df43d-233">Dans l'arborescence, sélectionnez « Xml\Message\Paiements\Article\Fournisseur\Banque\AccountNumber ».</span><span class="sxs-lookup"><span data-stu-id="df43d-233">In the tree, select 'Xml\Message\Payments\Item\Vendor\Bank\AccountNumber'.</span></span>
22. <span data-ttu-id="df43d-234">Cliquez sur Ajouter une chaîne.</span><span class="sxs-lookup"><span data-stu-id="df43d-234">Click Add String.</span></span>
23. <span data-ttu-id="df43d-235">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="df43d-235">Click OK.</span></span>
24. <span data-ttu-id="df43d-236">Dans l'arborescence, sélectionnez « Xml\Message\Paiements\Article\Payeur\Nom ».</span><span class="sxs-lookup"><span data-stu-id="df43d-236">In the tree, select 'Xml\Message\Payments\Item\Payer\Name'.</span></span>
25. <span data-ttu-id="df43d-237">Cliquez sur Ajouter une chaîne.</span><span class="sxs-lookup"><span data-stu-id="df43d-237">Click Add String.</span></span>
26. <span data-ttu-id="df43d-238">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="df43d-238">Click OK.</span></span>
27. <span data-ttu-id="df43d-239">Dans l'arborescence, sélectionnez « Xml\Message\Paiements\Article\Payeur\Banque\RoutingNumber ».</span><span class="sxs-lookup"><span data-stu-id="df43d-239">In the tree, select 'Xml\Message\Payments\Item\Payer\Bank\RoutingNumber'.</span></span>
28. <span data-ttu-id="df43d-240">Cliquez sur Ajouter une chaîne.</span><span class="sxs-lookup"><span data-stu-id="df43d-240">Click Add String.</span></span>
29. <span data-ttu-id="df43d-241">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="df43d-241">Click OK.</span></span>
30. <span data-ttu-id="df43d-242">Dans l'arborescence, sélectionnez « Xml\Message\Paiements\Article\Payeur\Banque\AccountNumber ».</span><span class="sxs-lookup"><span data-stu-id="df43d-242">In the tree, select 'Xml\Message\Payments\Item\Payer\Bank\AccountNumber'.</span></span>
31. <span data-ttu-id="df43d-243">Cliquez sur Ajouter une chaîne.</span><span class="sxs-lookup"><span data-stu-id="df43d-243">Click Add String.</span></span>
32. <span data-ttu-id="df43d-244">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="df43d-244">Click OK.</span></span>
33. <span data-ttu-id="df43d-245">Dans l'arborescence, sélectionnez « Xml\Message\Paiements\Article\Devise ».</span><span class="sxs-lookup"><span data-stu-id="df43d-245">In the tree, select 'Xml\Message\Payments\Item\Currency'.</span></span>
34. <span data-ttu-id="df43d-246">Cliquez sur Ajouter une chaîne.</span><span class="sxs-lookup"><span data-stu-id="df43d-246">Click Add String.</span></span>
35. <span data-ttu-id="df43d-247">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="df43d-247">Click OK.</span></span>
36. <span data-ttu-id="df43d-248">Dans l'arborescence, sélectionnez « Xml\Message\Paiements\Article\Description ».</span><span class="sxs-lookup"><span data-stu-id="df43d-248">In the tree, select 'Xml\Message\Payments\Item\Description'.</span></span>
37. <span data-ttu-id="df43d-249">Cliquez sur Ajouter une chaîne.</span><span class="sxs-lookup"><span data-stu-id="df43d-249">Click Add String.</span></span>
38. <span data-ttu-id="df43d-250">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="df43d-250">Click OK.</span></span>
39. <span data-ttu-id="df43d-251">Dans l'arborescence, sélectionnez « Xml\Message\Paiements\Article\Montant ».</span><span class="sxs-lookup"><span data-stu-id="df43d-251">In the tree, select 'Xml\Message\Payments\Item\Amount'.</span></span>
40. <span data-ttu-id="df43d-252">Cliquez sur Ajouter une chaîne.</span><span class="sxs-lookup"><span data-stu-id="df43d-252">Click Add String.</span></span>
41. <span data-ttu-id="df43d-253">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="df43d-253">Click OK.</span></span>
42. <span data-ttu-id="df43d-254">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="df43d-254">Click Save.</span></span>
43. <span data-ttu-id="df43d-255">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="df43d-255">Close the page.</span></span>


