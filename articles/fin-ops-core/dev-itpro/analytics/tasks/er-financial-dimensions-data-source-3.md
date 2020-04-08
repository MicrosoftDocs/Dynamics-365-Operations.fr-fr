---
title: ER Utiliser les dimensions financières comme source de données (Partie 3 - Créer l'état)
description: Les étapes suivantes expliquent comment un utilisateur affecté au rôle d'administrateur système ou de développeur d'états électroniques peut configurer un modèle de génération d'états électroniques (ER) pour utiliser les dimensions financières comme source de données pour les états ER.
author: NickSelin
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ERSolutionTable, ERSolutionCreateDropDialog, EROperationDesigner, ERComponentTypeDropDialog
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 7bbbc81eaf8c13e8d13e30a0276e38453e07ead9
ms.sourcegitcommit: 57e1dafa186fec77ddd8ba9425d238e36e0f0998
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/18/2020
ms.locfileid: "3142522"
---
# <a name="er-use-financial-dimensions-as-a-data-source-part-3---design-the-report"></a><span data-ttu-id="fb750-103">ER Utiliser les dimensions financières comme source de données (Partie 3 - Créer l'état)</span><span class="sxs-lookup"><span data-stu-id="fb750-103">ER Use financial dimensions as a data source (Part 3 - Design the report)</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="fb750-104">Les étapes suivantes expliquent comment un utilisateur affecté au rôle d'administrateur système ou de développeur d'états électroniques peut configurer un modèle de génération d'états électroniques (ER) pour utiliser les dimensions financières comme source de données pour les états ER.</span><span class="sxs-lookup"><span data-stu-id="fb750-104">The following steps explain how a user assigned to the system administrator or electronic reporting developer role can configure an Electronic reporting (ER) model to use financial dimensions as a data source for ER reports.</span></span> <span data-ttu-id="fb750-105">Ces étapes peuvent être effectuées dans n'importe quelle société.</span><span class="sxs-lookup"><span data-stu-id="fb750-105">These steps can be performed in any company.</span></span>

<span data-ttu-id="fb750-106">Pour effectuer ces étapes, vous devez d'abord effectuer les étapes de la procédure « ER Utiliser les dimensions financières comme source de données (Partie 2 : mise en correspondance des modèles) ».</span><span class="sxs-lookup"><span data-stu-id="fb750-106">To complete these steps, you must first complete the steps in the "ER Use financial dimensions as a data source (Part 2: Model mapping)" procedure.</span></span>


## <a name="design-a-report-to-present-financial-dimensions"></a><span data-ttu-id="fb750-107">Créer un état pour présenter des dimensions financières</span><span class="sxs-lookup"><span data-stu-id="fb750-107">Design a report to present financial dimensions</span></span>
1. <span data-ttu-id="fb750-108">Accédez à Administration d'organisation > États électroniques > Configurations.</span><span class="sxs-lookup"><span data-stu-id="fb750-108">Go to Organization administration > Electronic reporting > Configurations.</span></span>
2. <span data-ttu-id="fb750-109">Dans l'arborescence, sélectionnez « Exemple de modèle de dimensions financières ».</span><span class="sxs-lookup"><span data-stu-id="fb750-109">In the tree, select 'Financial dimensions sample model'.</span></span>
3. <span data-ttu-id="fb750-110">Cliquez sur Créer la configuration pour ouvrir la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="fb750-110">Click Create configuration to open the drop dialog.</span></span>
4. <span data-ttu-id="fb750-111">Dans le champ Nouveau, entrez « Format basé sur l'exemple de modèle de dimensions financières pour le modèle de données ».</span><span class="sxs-lookup"><span data-stu-id="fb750-111">In the New field, enter 'Format based on data model Financial dimensions sample model'.</span></span>
    * <span data-ttu-id="fb750-112">Utilisez le modèle créé à l'avance comme source de données de votre nouvel état.</span><span class="sxs-lookup"><span data-stu-id="fb750-112">Use the model that was created in advance as the data source for your new report.</span></span>  
5. <span data-ttu-id="fb750-113">Dans le champ Nom, tapez « État du journal comptable ».</span><span class="sxs-lookup"><span data-stu-id="fb750-113">In the Name field, type 'Ledger journal report'.</span></span>
6. <span data-ttu-id="fb750-114">Dans le champ Définition du modèle de données, sélectionnez Entrée.</span><span class="sxs-lookup"><span data-stu-id="fb750-114">In the Data model definition field, select Entry.</span></span>
7. <span data-ttu-id="fb750-115">Cliquez sur Créer une configuration.</span><span class="sxs-lookup"><span data-stu-id="fb750-115">Click Create configuration.</span></span>
8. <span data-ttu-id="fb750-116">Cliquez sur Concepteur.</span><span class="sxs-lookup"><span data-stu-id="fb750-116">Click Designer.</span></span>
9. <span data-ttu-id="fb750-117">Cliquez sur Ajouter racine pour ouvrir la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="fb750-117">Click Add root to open the drop dialog.</span></span>
10. <span data-ttu-id="fb750-118">Dans l'arborescence , sélectionnez « XML\Élément ».</span><span class="sxs-lookup"><span data-stu-id="fb750-118">In the tree, select 'XML\Element'.</span></span>
11. <span data-ttu-id="fb750-119">Dans le champ Nom, tapez « Racine ».</span><span class="sxs-lookup"><span data-stu-id="fb750-119">In the Name field, type 'Root'.</span></span>
12. <span data-ttu-id="fb750-120">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="fb750-120">Click OK.</span></span>
13. <span data-ttu-id="fb750-121">Cliquez sur Ajouter pour ouvrir la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="fb750-121">Click Add to open the drop dialog.</span></span>
14. <span data-ttu-id="fb750-122">Dans l'arborescence, sélectionnez « XML\Attribut ».</span><span class="sxs-lookup"><span data-stu-id="fb750-122">In the tree, select 'XML\Attribute'.</span></span>
15. <span data-ttu-id="fb750-123">Dans le champ Nom, tapez « Société ».</span><span class="sxs-lookup"><span data-stu-id="fb750-123">In the Name field, type 'Company'.</span></span>
16. <span data-ttu-id="fb750-124">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="fb750-124">Click OK.</span></span>
17. <span data-ttu-id="fb750-125">Cliquez sur Ajouter pour ouvrir la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="fb750-125">Click Add to open the drop dialog.</span></span>
18. <span data-ttu-id="fb750-126">Dans l'arborescence , sélectionnez « XML\Élément ».</span><span class="sxs-lookup"><span data-stu-id="fb750-126">In the tree, select 'XML\Element'.</span></span>
19. <span data-ttu-id="fb750-127">Dans le champ Nom, tapez « Journal ».</span><span class="sxs-lookup"><span data-stu-id="fb750-127">In the Name field, type 'Journal'.</span></span>
20. <span data-ttu-id="fb750-128">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="fb750-128">Click OK.</span></span>
21. <span data-ttu-id="fb750-129">Dans l'arborescence, sélectionnez « Racine : Élément XML\Journal : Élément XML ».</span><span class="sxs-lookup"><span data-stu-id="fb750-129">In the tree, select 'Root: XML Element\Journal: XML Element'.</span></span>
22. <span data-ttu-id="fb750-130">Cliquez sur Ajouter pour ouvrir la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="fb750-130">Click Add to open the drop dialog.</span></span>
23. <span data-ttu-id="fb750-131">Dans l'arborescence, sélectionnez « XML\Attribut ».</span><span class="sxs-lookup"><span data-stu-id="fb750-131">In the tree, select 'XML\Attribute'.</span></span>
24. <span data-ttu-id="fb750-132">Dans le champ Nom, tapez « Traitement par lots ».</span><span class="sxs-lookup"><span data-stu-id="fb750-132">In the Name field, type 'Batch'.</span></span>
25. <span data-ttu-id="fb750-133">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="fb750-133">Click OK.</span></span>
26. <span data-ttu-id="fb750-134">Cliquez sur Ajouter pour ouvrir la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="fb750-134">Click Add to open the drop dialog.</span></span>
27. <span data-ttu-id="fb750-135">Dans l'arborescence , sélectionnez « XML\Élément ».</span><span class="sxs-lookup"><span data-stu-id="fb750-135">In the tree, select 'XML\Element'.</span></span>
28. <span data-ttu-id="fb750-136">Dans le champ Nom, tapez « Transaction ».</span><span class="sxs-lookup"><span data-stu-id="fb750-136">In the Name field, type 'Transaction'.</span></span>
29. <span data-ttu-id="fb750-137">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="fb750-137">Click OK.</span></span>
30. <span data-ttu-id="fb750-138">Dans l'arborescence, sélectionnez « Racine : Élément XML\Journal : Élément XML\Transaction : Élément XML ».</span><span class="sxs-lookup"><span data-stu-id="fb750-138">In the tree, select 'Root: XML Element\Journal: XML Element\Transaction: XML Element'.</span></span>
31. <span data-ttu-id="fb750-139">Cliquez sur Ajouter pour ouvrir la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="fb750-139">Click Add to open the drop dialog.</span></span>
32. <span data-ttu-id="fb750-140">Dans l'arborescence, sélectionnez « XML\Attribut ».</span><span class="sxs-lookup"><span data-stu-id="fb750-140">In the tree, select 'XML\Attribute'.</span></span>
33. <span data-ttu-id="fb750-141">Dans le champ Nom, tapez « N° document ».</span><span class="sxs-lookup"><span data-stu-id="fb750-141">In the Name field, type 'Voucher'.</span></span>
34. <span data-ttu-id="fb750-142">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="fb750-142">Click OK.</span></span>
35. <span data-ttu-id="fb750-143">Cliquez sur Ajouter un attribut.</span><span class="sxs-lookup"><span data-stu-id="fb750-143">Click Add Attribute.</span></span>
36. <span data-ttu-id="fb750-144">Dans le champ Nom, tapez « Date ».</span><span class="sxs-lookup"><span data-stu-id="fb750-144">In the Name field, type 'Date'.</span></span>
37. <span data-ttu-id="fb750-145">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="fb750-145">Click OK.</span></span>
38. <span data-ttu-id="fb750-146">Cliquez sur Ajouter un attribut.</span><span class="sxs-lookup"><span data-stu-id="fb750-146">Click Add Attribute.</span></span>
39. <span data-ttu-id="fb750-147">Tapez « Devise » dans le champ Nom.</span><span class="sxs-lookup"><span data-stu-id="fb750-147">In the Name field, type 'Currency'.</span></span>
40. <span data-ttu-id="fb750-148">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="fb750-148">Click OK.</span></span>
41. <span data-ttu-id="fb750-149">Cliquez sur Ajouter un attribut.</span><span class="sxs-lookup"><span data-stu-id="fb750-149">Click Add Attribute.</span></span>
42. <span data-ttu-id="fb750-150">Dans le champ Nom, tapez « Dt ».</span><span class="sxs-lookup"><span data-stu-id="fb750-150">In the Name field, type 'Dt'.</span></span>
43. <span data-ttu-id="fb750-151">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="fb750-151">Click OK.</span></span>
44. <span data-ttu-id="fb750-152">Cliquez sur Ajouter un attribut.</span><span class="sxs-lookup"><span data-stu-id="fb750-152">Click Add Attribute.</span></span>
45. <span data-ttu-id="fb750-153">Dans le champ Nom, tapez « Ct ».</span><span class="sxs-lookup"><span data-stu-id="fb750-153">In the Name field, type 'Ct'.</span></span>
46. <span data-ttu-id="fb750-154">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="fb750-154">Click OK.</span></span>
47. <span data-ttu-id="fb750-155">Cliquez sur Ajouter pour ouvrir la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="fb750-155">Click Add to open the drop dialog.</span></span>
48. <span data-ttu-id="fb750-156">Dans l'arborescence , sélectionnez « XML\Élément ».</span><span class="sxs-lookup"><span data-stu-id="fb750-156">In the tree, select 'XML\Element'.</span></span>
49. <span data-ttu-id="fb750-157">Dans le champ Nom, tapez « Dimensions ».</span><span class="sxs-lookup"><span data-stu-id="fb750-157">In the Name field, type 'Dimensions'.</span></span>
50. <span data-ttu-id="fb750-158">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="fb750-158">Click OK.</span></span>
51. <span data-ttu-id="fb750-159">Dans l'arborescence, sélectionnez « Racine : Élément XML\Journal : Élément XML\Transaction : Élément XML\Dimensions : Élément XML ».</span><span class="sxs-lookup"><span data-stu-id="fb750-159">In the tree, select 'Root: XML Element\Journal: XML Element\Transaction: XML Element\Dimensions: XML Element'.</span></span>
52. <span data-ttu-id="fb750-160">Cliquez sur Ajouter pour ouvrir la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="fb750-160">Click Add to open the drop dialog.</span></span>
53. <span data-ttu-id="fb750-161">Dans l'arborescence, sélectionnez « XML\Attribut ».</span><span class="sxs-lookup"><span data-stu-id="fb750-161">In the tree, select 'XML\Attribute'.</span></span>
54. <span data-ttu-id="fb750-162">Dans le champ Nom, tapez « Code ».</span><span class="sxs-lookup"><span data-stu-id="fb750-162">In the Name field, type 'Code'.</span></span>
55. <span data-ttu-id="fb750-163">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="fb750-163">Click OK.</span></span>
56. <span data-ttu-id="fb750-164">Cliquez sur Ajouter un attribut.</span><span class="sxs-lookup"><span data-stu-id="fb750-164">Click Add Attribute.</span></span>
57. <span data-ttu-id="fb750-165">Dans le champ Nom, tapez « Valeur ».</span><span class="sxs-lookup"><span data-stu-id="fb750-165">In the Name field, type 'Value'.</span></span>
58. <span data-ttu-id="fb750-166">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="fb750-166">Click OK.</span></span>
59. <span data-ttu-id="fb750-167">Cliquez sur Ajouter un attribut.</span><span class="sxs-lookup"><span data-stu-id="fb750-167">Click Add Attribute.</span></span>
60. <span data-ttu-id="fb750-168">Dans le champ Nom, tapez « Desc ».</span><span class="sxs-lookup"><span data-stu-id="fb750-168">In the Name field, type 'Desc'.</span></span>
61. <span data-ttu-id="fb750-169">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="fb750-169">Click OK.</span></span>

## <a name="map-report-elements-to-data-sources"></a><span data-ttu-id="fb750-170">Mettre en correspondance les éléments d'état avec les sources de données</span><span class="sxs-lookup"><span data-stu-id="fb750-170">Map report elements to data sources</span></span>
1. <span data-ttu-id="fb750-171">Cliquez sur l'onglet Mise en relation.</span><span class="sxs-lookup"><span data-stu-id="fb750-171">Click the Mapping tab.</span></span>
2. <span data-ttu-id="fb750-172">Dans l'arborescence, développez « Modèle : Exemple de modèle de dimensions financières pour le modèle de données ».</span><span class="sxs-lookup"><span data-stu-id="fb750-172">In the tree, expand 'model: Data model Financial dimensions sample model'.</span></span>
3. <span data-ttu-id="fb750-173">Dans l'arborescence, développez « Modèle : Exemple de modèle de dimensions financières pour le modèle de données\Journal : Liste d'enregistrements ».</span><span class="sxs-lookup"><span data-stu-id="fb750-173">In the tree, expand 'model: Data model Financial dimensions sample model\Journal: Record list'.</span></span>
4. <span data-ttu-id="fb750-174">Dans l'arborescence, développez « Modèle : Exemple de modèle de dimensions financières pour le modèle de données\Journal : Liste d'enregistrements\Transaction : Liste d'enregistrements ».</span><span class="sxs-lookup"><span data-stu-id="fb750-174">In the tree, expand 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list'.</span></span>
5. <span data-ttu-id="fb750-175">Dans l'arborescence, développez « Modèle : Exemple de modèle de dimensions financières pour le modèle de données\Journal : Liste d'enregistrements\Transaction : Liste d'enregistrements\Données de dimensions : Liste d'enregistrements ».</span><span class="sxs-lookup"><span data-stu-id="fb750-175">In the tree, expand 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Dimensions data: Record list'.</span></span>
6. <span data-ttu-id="fb750-176">Dans l'arborescence, sélectionnez « Racine : Élément XML\Journal : Élément XML\Transaction : Élément XML\Dimensions : Élément XML\Desc : Attribut XML ».</span><span class="sxs-lookup"><span data-stu-id="fb750-176">In the tree, select 'Root: XML Element\Journal: XML Element\Transaction: XML Element\Dimensions: XML Element\Desc: XML Attribute'.</span></span>
7. <span data-ttu-id="fb750-177">Dans l'arborescence, sélectionnez « Modèle : Exemple de modèle de dimensions financières pour le modèle de données\Journal : Liste d'enregistrements\Transaction : Liste d'enregistrements\Données de dimensions : Liste d'enregistrements\Description : Chaîne ».</span><span class="sxs-lookup"><span data-stu-id="fb750-177">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Dimensions data: Record list\Description: String'.</span></span>
8. <span data-ttu-id="fb750-178">Cliquez sur Lier.</span><span class="sxs-lookup"><span data-stu-id="fb750-178">Click Bind.</span></span>
9. <span data-ttu-id="fb750-179">Dans l'arborescence, sélectionnez « Racine : Élément XML\Journal : Élément XML\Transaction : Élément XML\Dimensions : Élément XML\Valeur : Attribut XML ».</span><span class="sxs-lookup"><span data-stu-id="fb750-179">In the tree, select 'Root: XML Element\Journal: XML Element\Transaction: XML Element\Dimensions: XML Element\Value: XML Attribute'.</span></span>
10. <span data-ttu-id="fb750-180">Dans l'arborescence, sélectionnez « Modèle : Exemple de modèle de dimensions financières pour le modèle de données\Journal : Liste d'enregistrements\Transaction : Liste d'enregistrements\Données de dimensions : Liste d'enregistrements\Code : Chaîne ».</span><span class="sxs-lookup"><span data-stu-id="fb750-180">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Dimensions data: Record list\Code: String'.</span></span>
11. <span data-ttu-id="fb750-181">Cliquez sur Lier.</span><span class="sxs-lookup"><span data-stu-id="fb750-181">Click Bind.</span></span>
12. <span data-ttu-id="fb750-182">Dans l'arborescence, sélectionnez « Racine : Élément XML\Journal : Élément XML\Transaction : Élément XML\Dimensions : Élément XML\Code : Attribut XML ».</span><span class="sxs-lookup"><span data-stu-id="fb750-182">In the tree, select 'Root: XML Element\Journal: XML Element\Transaction: XML Element\Dimensions: XML Element\Code: XML Attribute'.</span></span>
13. <span data-ttu-id="fb750-183">Dans l'arborescence, sélectionnez « Modèle : Exemple de modèle de dimensions financières pour le modèle de données\Journal : Liste d'enregistrements\Transaction : Liste d'enregistrements\Données de dimensions : Liste d'enregistrements\Nom : Chaîne ».</span><span class="sxs-lookup"><span data-stu-id="fb750-183">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Dimensions data: Record list\Name: String'.</span></span>
14. <span data-ttu-id="fb750-184">Cliquez sur Lier.</span><span class="sxs-lookup"><span data-stu-id="fb750-184">Click Bind.</span></span>
15. <span data-ttu-id="fb750-185">Dans l'arborescence, sélectionnez « Modèle : Exemple de modèle de dimensions financières pour le modèle de données\Journal : Liste d'enregistrements\Transaction : Liste d'enregistrements\Données de dimensions : Liste d'enregistrements ».</span><span class="sxs-lookup"><span data-stu-id="fb750-185">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Dimensions data: Record list'.</span></span>
16. <span data-ttu-id="fb750-186">Dans l'arborescence, sélectionnez « Racine : Élément XML\Journal : Élément XML\Transaction : Élément XML\Dimensions : Élément XML ».</span><span class="sxs-lookup"><span data-stu-id="fb750-186">In the tree, select 'Root: XML Element\Journal: XML Element\Transaction: XML Element\Dimensions: XML Element'.</span></span>
17. <span data-ttu-id="fb750-187">Cliquez sur Lier.</span><span class="sxs-lookup"><span data-stu-id="fb750-187">Click Bind.</span></span>
18. <span data-ttu-id="fb750-188">Dans l'arborescence, sélectionnez « Racine : Élément XML\Journal : Élément XML\Transaction : Élément XML\Ct : Attribut XML ».</span><span class="sxs-lookup"><span data-stu-id="fb750-188">In the tree, select 'Root: XML Element\Journal: XML Element\Transaction: XML Element\Ct: XML Attribute'.</span></span>
19. <span data-ttu-id="fb750-189">Dans l'arborescence, sélectionnez « Modèle : Exemple de modèle de dimensions financières pour le modèle de données\Journal : Liste d'enregistrements\Transaction : Liste d'enregistrements\Crédit : Réel ».</span><span class="sxs-lookup"><span data-stu-id="fb750-189">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Credit: Real'.</span></span>
20. <span data-ttu-id="fb750-190">Cliquez sur Lier.</span><span class="sxs-lookup"><span data-stu-id="fb750-190">Click Bind.</span></span>
21. <span data-ttu-id="fb750-191">Dans l'arborescence, sélectionnez « Racine : Élément XML\Journal : Élément XML\Transaction : Élément XML\Dt : Attribut XML ».</span><span class="sxs-lookup"><span data-stu-id="fb750-191">In the tree, select 'Root: XML Element\Journal: XML Element\Transaction: XML Element\Dt: XML Attribute'.</span></span>
22. <span data-ttu-id="fb750-192">Dans l'arborescence, sélectionnez « Modèle : Exemple de modèle de dimensions financières pour le modèle de données\Journal : Liste d'enregistrements\Transaction : Liste d'enregistrements\Débit : Réel ».</span><span class="sxs-lookup"><span data-stu-id="fb750-192">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Debit: Real'.</span></span>
23. <span data-ttu-id="fb750-193">Cliquez sur Lier.</span><span class="sxs-lookup"><span data-stu-id="fb750-193">Click Bind.</span></span>
24. <span data-ttu-id="fb750-194">Dans l'arborescence, sélectionnez « Racine : Élément XML\Journal : Élément XML\Transaction : Élément XML\Devise : Attribut XML ».</span><span class="sxs-lookup"><span data-stu-id="fb750-194">In the tree, select 'Root: XML Element\Journal: XML Element\Transaction: XML Element\Currency: XML Attribute'.</span></span>
25. <span data-ttu-id="fb750-195">Dans l'arborescence, sélectionnez « Modèle : Exemple de modèle de dimensions financières pour le modèle de données\Journal : Liste d'enregistrements\Transaction : Liste d'enregistrements\Devise : Chaîne ».</span><span class="sxs-lookup"><span data-stu-id="fb750-195">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Currency: String'.</span></span>
26. <span data-ttu-id="fb750-196">Cliquez sur Lier.</span><span class="sxs-lookup"><span data-stu-id="fb750-196">Click Bind.</span></span>
27. <span data-ttu-id="fb750-197">Dans l'arborescence, sélectionnez « Racine : Élément XML\Journal : Élément XML\Transaction : Élément XML\Date : Attribut XML ».</span><span class="sxs-lookup"><span data-stu-id="fb750-197">In the tree, select 'Root: XML Element\Journal: XML Element\Transaction: XML Element\Date: XML Attribute'.</span></span>
28. <span data-ttu-id="fb750-198">Dans l'arborescence, sélectionnez « Modèle : Exemple de modèle de dimensions financières pour le modèle de données\Journal : Liste d'enregistrements\Transaction : Liste d'enregistrements\Date : Date ».</span><span class="sxs-lookup"><span data-stu-id="fb750-198">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Date: Date'.</span></span>
29. <span data-ttu-id="fb750-199">Cliquez sur Lier.</span><span class="sxs-lookup"><span data-stu-id="fb750-199">Click Bind.</span></span>
30. <span data-ttu-id="fb750-200">Dans l'arborescence, sélectionnez « Racine : Élément XML\Journal : Élément XML\Transaction : Élément XML\N° document : Attribut XML ».</span><span class="sxs-lookup"><span data-stu-id="fb750-200">In the tree, select 'Root: XML Element\Journal: XML Element\Transaction: XML Element\Voucher: XML Attribute'.</span></span>
31. <span data-ttu-id="fb750-201">Dans l'arborescence, sélectionnez « Modèle : Exemple de modèle de dimensions financières pour le modèle de données\Journal : Liste d'enregistrements\Transaction : Liste d'enregistrements\N° document : Chaîne ».</span><span class="sxs-lookup"><span data-stu-id="fb750-201">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Voucher: String'.</span></span>
32. <span data-ttu-id="fb750-202">Cliquez sur Lier.</span><span class="sxs-lookup"><span data-stu-id="fb750-202">Click Bind.</span></span>
33. <span data-ttu-id="fb750-203">Dans l'arborescence, sélectionnez « Racine : Élément XML\Journal : Élément XML\Transaction : Élément XML ».</span><span class="sxs-lookup"><span data-stu-id="fb750-203">In the tree, select 'Root: XML Element\Journal: XML Element\Transaction: XML Element'.</span></span>
34. <span data-ttu-id="fb750-204">Dans l'arborescence, sélectionnez « Modèle : Exemple de modèle de dimensions financières pour le modèle de données\Journal : Liste d'enregistrements\Transaction : Liste d'enregistrements ».</span><span class="sxs-lookup"><span data-stu-id="fb750-204">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list'.</span></span>
35. <span data-ttu-id="fb750-205">Cliquez sur Lier.</span><span class="sxs-lookup"><span data-stu-id="fb750-205">Click Bind.</span></span>
36. <span data-ttu-id="fb750-206">Dans l'arborescence, sélectionnez « Racine : Élément XML\Journal : Élément XML\Lot : Attribut XML ».</span><span class="sxs-lookup"><span data-stu-id="fb750-206">In the tree, select 'Root: XML Element\Journal: XML Element\Batch: XML Attribute'.</span></span>
37. <span data-ttu-id="fb750-207">Dans l'arborescence, sélectionnez « Modèle : Exemple de modèle de dimensions financières pour le modèle de données\Journal : Liste d'enregistrements\Lot : Chaîne ».</span><span class="sxs-lookup"><span data-stu-id="fb750-207">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list\Batch: String'.</span></span>
38. <span data-ttu-id="fb750-208">Cliquez sur Lier.</span><span class="sxs-lookup"><span data-stu-id="fb750-208">Click Bind.</span></span>
39. <span data-ttu-id="fb750-209">Dans l'arborescence, sélectionnez « Racine : Élément XML\Journal : Élément XML ».</span><span class="sxs-lookup"><span data-stu-id="fb750-209">In the tree, select 'Root: XML Element\Journal: XML Element'.</span></span>
40. <span data-ttu-id="fb750-210">Dans l'arborescence, sélectionnez « Modèle : Exemple de modèle de dimensions financières pour le modèle de données\Journal : Liste d'enregistrements ».</span><span class="sxs-lookup"><span data-stu-id="fb750-210">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list'.</span></span>
41. <span data-ttu-id="fb750-211">Cliquez sur Lier.</span><span class="sxs-lookup"><span data-stu-id="fb750-211">Click Bind.</span></span>
42. <span data-ttu-id="fb750-212">Dans l'arborescence, sélectionnez « Racine : Élément XML\Société : Attribut XML ».</span><span class="sxs-lookup"><span data-stu-id="fb750-212">In the tree, select 'Root: XML Element\Company: XML Attribute'.</span></span>
43. <span data-ttu-id="fb750-213">Dans l'arborescence, sélectionnez « Modèle : Exemple de modèle de dimensions financières pour le modèle de données\Société : Chaîne ».</span><span class="sxs-lookup"><span data-stu-id="fb750-213">In the tree, select 'model: Data model Financial dimensions sample model\Company: String'.</span></span>
44. <span data-ttu-id="fb750-214">Cliquez sur Lier.</span><span class="sxs-lookup"><span data-stu-id="fb750-214">Click Bind.</span></span>
45. <span data-ttu-id="fb750-215">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="fb750-215">Click Save.</span></span>
46. <span data-ttu-id="fb750-216">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="fb750-216">Close the page.</span></span>

