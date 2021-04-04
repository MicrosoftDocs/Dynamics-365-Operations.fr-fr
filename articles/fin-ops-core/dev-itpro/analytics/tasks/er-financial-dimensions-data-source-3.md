---
title: ER Utiliser les dimensions financières comme source de données (Partie 3 - Créer l’état)
description: Cette rubrique décrit comment configurer un modèle de gestion des états électroniques pour utiliser les dimensions financières comme source de données pour les rapports de gestion des états électroniques. (Partie 3)
author: NickSelin
manager: AnnBe
ms.date: 05/27/2020
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: ERSolutionTable, ERSolutionCreateDropDialog, EROperationDesigner, ERComponentTypeDropDialog
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: a9594a12c28109d80c6ee07a9ee38f4923963dca
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/09/2021
ms.locfileid: "5565236"
---
# <a name="er-use-financial-dimensions-as-a-data-source-part-3---design-the-report"></a><span data-ttu-id="3a3d3-104">ER Utiliser les dimensions financières comme source de données (Partie 3 - Créer l’état)</span><span class="sxs-lookup"><span data-stu-id="3a3d3-104">ER Use financial dimensions as a data source (Part 3 - Design the report)</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="3a3d3-105">Les étapes suivantes expliquent comment un utilisateur affecté au rôle d’administrateur système ou de développeur d’états électroniques peut configurer un modèle de génération d’états électroniques (ER) pour utiliser les dimensions financières comme source de données pour les états ER.</span><span class="sxs-lookup"><span data-stu-id="3a3d3-105">The following steps explain how a user assigned to the system administrator or electronic reporting developer role can configure an Electronic reporting (ER) model to use financial dimensions as a data source for ER reports.</span></span> <span data-ttu-id="3a3d3-106">Ces étapes peuvent être effectuées dans n’importe quelle société.</span><span class="sxs-lookup"><span data-stu-id="3a3d3-106">These steps can be performed in any company.</span></span>

<span data-ttu-id="3a3d3-107">Pour effectuer ces étapes, vous devez d’abord effectuer les étapes de la procédure « ER Utiliser les dimensions financières comme source de données (Partie 2 : mise en correspondance des modèles) ».</span><span class="sxs-lookup"><span data-stu-id="3a3d3-107">To complete these steps, you must first complete the steps in the "ER Use financial dimensions as a data source (Part 2: Model mapping)" procedure.</span></span>


## <a name="design-a-report-to-present-financial-dimensions"></a><span data-ttu-id="3a3d3-108">Créer un état pour présenter des dimensions financières</span><span class="sxs-lookup"><span data-stu-id="3a3d3-108">Design a report to present financial dimensions</span></span>
1. <span data-ttu-id="3a3d3-109">Accédez à Administration d’organisation > États électroniques > Configurations.</span><span class="sxs-lookup"><span data-stu-id="3a3d3-109">Go to Organization administration > Electronic reporting > Configurations.</span></span>
2. <span data-ttu-id="3a3d3-110">Dans l’arborescence, sélectionnez « Exemple de modèle de dimensions financières ».</span><span class="sxs-lookup"><span data-stu-id="3a3d3-110">In the tree, select 'Financial dimensions sample model'.</span></span>
3. <span data-ttu-id="3a3d3-111">Cliquez sur Créer la configuration pour ouvrir la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="3a3d3-111">Click Create configuration to open the drop dialog.</span></span>
4. <span data-ttu-id="3a3d3-112">Dans le champ Nouveau, entrez « Format basé sur l’exemple de modèle de dimensions financières pour le modèle de données ».</span><span class="sxs-lookup"><span data-stu-id="3a3d3-112">In the New field, enter 'Format based on data model Financial dimensions sample model'.</span></span>
    * <span data-ttu-id="3a3d3-113">Utilisez le modèle créé à l’avance comme source de données de votre nouvel état.</span><span class="sxs-lookup"><span data-stu-id="3a3d3-113">Use the model that was created in advance as the data source for your new report.</span></span>  
5. <span data-ttu-id="3a3d3-114">Dans le champ Nom, tapez « État du journal comptable ».</span><span class="sxs-lookup"><span data-stu-id="3a3d3-114">In the Name field, type 'Ledger journal report'.</span></span>
6. <span data-ttu-id="3a3d3-115">Dans le champ Définition du modèle de données, sélectionnez Entrée.</span><span class="sxs-lookup"><span data-stu-id="3a3d3-115">In the Data model definition field, select Entry.</span></span>
7. <span data-ttu-id="3a3d3-116">Cliquez sur Créer une configuration.</span><span class="sxs-lookup"><span data-stu-id="3a3d3-116">Click Create configuration.</span></span>
8. <span data-ttu-id="3a3d3-117">Cliquez sur Concepteur.</span><span class="sxs-lookup"><span data-stu-id="3a3d3-117">Click Designer.</span></span>
9. <span data-ttu-id="3a3d3-118">Cliquez sur Ajouter racine pour ouvrir la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="3a3d3-118">Click Add root to open the drop dialog.</span></span>
10. <span data-ttu-id="3a3d3-119">Dans l’arborescence , sélectionnez « XML\Élément ».</span><span class="sxs-lookup"><span data-stu-id="3a3d3-119">In the tree, select 'XML\Element'.</span></span>
11. <span data-ttu-id="3a3d3-120">Dans le champ Nom, tapez « Racine ».</span><span class="sxs-lookup"><span data-stu-id="3a3d3-120">In the Name field, type 'Root'.</span></span>
12. <span data-ttu-id="3a3d3-121">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="3a3d3-121">Click OK.</span></span>
13. <span data-ttu-id="3a3d3-122">Cliquez sur Ajouter pour ouvrir la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="3a3d3-122">Click Add to open the drop dialog.</span></span>
14. <span data-ttu-id="3a3d3-123">Dans l’arborescence, sélectionnez « XML\Attribut ».</span><span class="sxs-lookup"><span data-stu-id="3a3d3-123">In the tree, select 'XML\Attribute'.</span></span>
15. <span data-ttu-id="3a3d3-124">Dans le champ Nom, tapez « Société ».</span><span class="sxs-lookup"><span data-stu-id="3a3d3-124">In the Name field, type 'Company'.</span></span>
16. <span data-ttu-id="3a3d3-125">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="3a3d3-125">Click OK.</span></span>
17. <span data-ttu-id="3a3d3-126">Cliquez sur Ajouter pour ouvrir la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="3a3d3-126">Click Add to open the drop dialog.</span></span>
18. <span data-ttu-id="3a3d3-127">Dans l’arborescence , sélectionnez « XML\Élément ».</span><span class="sxs-lookup"><span data-stu-id="3a3d3-127">In the tree, select 'XML\Element'.</span></span>
19. <span data-ttu-id="3a3d3-128">Dans le champ Nom, tapez « Journal ».</span><span class="sxs-lookup"><span data-stu-id="3a3d3-128">In the Name field, type 'Journal'.</span></span>
20. <span data-ttu-id="3a3d3-129">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="3a3d3-129">Click OK.</span></span>
21. <span data-ttu-id="3a3d3-130">Dans l’arborescence, sélectionnez « Racine : Élément XML\Journal : Élément XML ».</span><span class="sxs-lookup"><span data-stu-id="3a3d3-130">In the tree, select 'Root: XML Element\Journal: XML Element'.</span></span>
22. <span data-ttu-id="3a3d3-131">Cliquez sur Ajouter pour ouvrir la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="3a3d3-131">Click Add to open the drop dialog.</span></span>
23. <span data-ttu-id="3a3d3-132">Dans l’arborescence, sélectionnez « XML\Attribut ».</span><span class="sxs-lookup"><span data-stu-id="3a3d3-132">In the tree, select 'XML\Attribute'.</span></span>
24. <span data-ttu-id="3a3d3-133">Dans le champ Nom, tapez « Traitement par lots ».</span><span class="sxs-lookup"><span data-stu-id="3a3d3-133">In the Name field, type 'Batch'.</span></span>
25. <span data-ttu-id="3a3d3-134">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="3a3d3-134">Click OK.</span></span>
26. <span data-ttu-id="3a3d3-135">Cliquez sur Ajouter pour ouvrir la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="3a3d3-135">Click Add to open the drop dialog.</span></span>
27. <span data-ttu-id="3a3d3-136">Dans l’arborescence , sélectionnez « XML\Élément ».</span><span class="sxs-lookup"><span data-stu-id="3a3d3-136">In the tree, select 'XML\Element'.</span></span>
28. <span data-ttu-id="3a3d3-137">Dans le champ Nom, tapez « Transaction ».</span><span class="sxs-lookup"><span data-stu-id="3a3d3-137">In the Name field, type 'Transaction'.</span></span>
29. <span data-ttu-id="3a3d3-138">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="3a3d3-138">Click OK.</span></span>
30. <span data-ttu-id="3a3d3-139">Dans l’arborescence, sélectionnez « Racine : Élément XML\Journal : Élément XML\Transaction : Élément XML ».</span><span class="sxs-lookup"><span data-stu-id="3a3d3-139">In the tree, select 'Root: XML Element\Journal: XML Element\Transaction: XML Element'.</span></span>
31. <span data-ttu-id="3a3d3-140">Cliquez sur Ajouter pour ouvrir la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="3a3d3-140">Click Add to open the drop dialog.</span></span>
32. <span data-ttu-id="3a3d3-141">Dans l’arborescence, sélectionnez « XML\Attribut ».</span><span class="sxs-lookup"><span data-stu-id="3a3d3-141">In the tree, select 'XML\Attribute'.</span></span>
33. <span data-ttu-id="3a3d3-142">Dans le champ Nom, tapez « N° document ».</span><span class="sxs-lookup"><span data-stu-id="3a3d3-142">In the Name field, type 'Voucher'.</span></span>
34. <span data-ttu-id="3a3d3-143">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="3a3d3-143">Click OK.</span></span>
35. <span data-ttu-id="3a3d3-144">Cliquez sur Ajouter un attribut.</span><span class="sxs-lookup"><span data-stu-id="3a3d3-144">Click Add Attribute.</span></span>
36. <span data-ttu-id="3a3d3-145">Dans le champ Nom, tapez « Date ».</span><span class="sxs-lookup"><span data-stu-id="3a3d3-145">In the Name field, type 'Date'.</span></span>
37. <span data-ttu-id="3a3d3-146">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="3a3d3-146">Click OK.</span></span>
38. <span data-ttu-id="3a3d3-147">Cliquez sur Ajouter un attribut.</span><span class="sxs-lookup"><span data-stu-id="3a3d3-147">Click Add Attribute.</span></span>
39. <span data-ttu-id="3a3d3-148">Tapez « Devise » dans le champ Nom.</span><span class="sxs-lookup"><span data-stu-id="3a3d3-148">In the Name field, type 'Currency'.</span></span>
40. <span data-ttu-id="3a3d3-149">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="3a3d3-149">Click OK.</span></span>
41. <span data-ttu-id="3a3d3-150">Cliquez sur Ajouter un attribut.</span><span class="sxs-lookup"><span data-stu-id="3a3d3-150">Click Add Attribute.</span></span>
42. <span data-ttu-id="3a3d3-151">Dans le champ Nom, tapez « Dt ».</span><span class="sxs-lookup"><span data-stu-id="3a3d3-151">In the Name field, type 'Dt'.</span></span>
43. <span data-ttu-id="3a3d3-152">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="3a3d3-152">Click OK.</span></span>
44. <span data-ttu-id="3a3d3-153">Cliquez sur Ajouter un attribut.</span><span class="sxs-lookup"><span data-stu-id="3a3d3-153">Click Add Attribute.</span></span>
45. <span data-ttu-id="3a3d3-154">Dans le champ Nom, tapez « Ct ».</span><span class="sxs-lookup"><span data-stu-id="3a3d3-154">In the Name field, type 'Ct'.</span></span>
46. <span data-ttu-id="3a3d3-155">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="3a3d3-155">Click OK.</span></span>
47. <span data-ttu-id="3a3d3-156">Cliquez sur Ajouter pour ouvrir la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="3a3d3-156">Click Add to open the drop dialog.</span></span>
48. <span data-ttu-id="3a3d3-157">Dans l’arborescence , sélectionnez « XML\Élément ».</span><span class="sxs-lookup"><span data-stu-id="3a3d3-157">In the tree, select 'XML\Element'.</span></span>
49. <span data-ttu-id="3a3d3-158">Dans le champ Nom, tapez « Dimensions ».</span><span class="sxs-lookup"><span data-stu-id="3a3d3-158">In the Name field, type 'Dimensions'.</span></span>
50. <span data-ttu-id="3a3d3-159">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="3a3d3-159">Click OK.</span></span>
51. <span data-ttu-id="3a3d3-160">Dans l’arborescence, sélectionnez « Racine : Élément XML\Journal : Élément XML\Transaction : Élément XML\Dimensions : Élément XML ».</span><span class="sxs-lookup"><span data-stu-id="3a3d3-160">In the tree, select 'Root: XML Element\Journal: XML Element\Transaction: XML Element\Dimensions: XML Element'.</span></span>
52. <span data-ttu-id="3a3d3-161">Cliquez sur Ajouter pour ouvrir la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="3a3d3-161">Click Add to open the drop dialog.</span></span>
53. <span data-ttu-id="3a3d3-162">Dans l’arborescence, sélectionnez « XML\Attribut ».</span><span class="sxs-lookup"><span data-stu-id="3a3d3-162">In the tree, select 'XML\Attribute'.</span></span>
54. <span data-ttu-id="3a3d3-163">Dans le champ Nom, tapez « Code ».</span><span class="sxs-lookup"><span data-stu-id="3a3d3-163">In the Name field, type 'Code'.</span></span>
55. <span data-ttu-id="3a3d3-164">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="3a3d3-164">Click OK.</span></span>
56. <span data-ttu-id="3a3d3-165">Cliquez sur Ajouter un attribut.</span><span class="sxs-lookup"><span data-stu-id="3a3d3-165">Click Add Attribute.</span></span>
57. <span data-ttu-id="3a3d3-166">Dans le champ Nom, tapez « Valeur ».</span><span class="sxs-lookup"><span data-stu-id="3a3d3-166">In the Name field, type 'Value'.</span></span>
58. <span data-ttu-id="3a3d3-167">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="3a3d3-167">Click OK.</span></span>
59. <span data-ttu-id="3a3d3-168">Cliquez sur Ajouter un attribut.</span><span class="sxs-lookup"><span data-stu-id="3a3d3-168">Click Add Attribute.</span></span>
60. <span data-ttu-id="3a3d3-169">Dans le champ Nom, tapez « Desc ».</span><span class="sxs-lookup"><span data-stu-id="3a3d3-169">In the Name field, type 'Desc'.</span></span>
61. <span data-ttu-id="3a3d3-170">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="3a3d3-170">Click OK.</span></span>
<span data-ttu-id="3a3d3-171">![Page Concepteur d’opérations de gestion des états électroniques](../media/er-financial-dimensions-guides-format1.png)</span><span class="sxs-lookup"><span data-stu-id="3a3d3-171">![ER Operations designer page](../media/er-financial-dimensions-guides-format1.png)</span></span>

## <a name="map-report-elements-to-data-sources"></a><span data-ttu-id="3a3d3-172">Mettre en correspondance les éléments d’état avec les sources de données</span><span class="sxs-lookup"><span data-stu-id="3a3d3-172">Map report elements to data sources</span></span>
1. <span data-ttu-id="3a3d3-173">Cliquez sur l’onglet Mise en relation.</span><span class="sxs-lookup"><span data-stu-id="3a3d3-173">Click the Mapping tab.</span></span>
2. <span data-ttu-id="3a3d3-174">Dans l’arborescence, développez « Modèle : Exemple de modèle de dimensions financières pour le modèle de données ».</span><span class="sxs-lookup"><span data-stu-id="3a3d3-174">In the tree, expand 'model: Data model Financial dimensions sample model'.</span></span>
3. <span data-ttu-id="3a3d3-175">Dans l’arborescence, développez « Modèle : Exemple de modèle de dimensions financières pour le modèle de données\Journal : Liste d’enregistrements ».</span><span class="sxs-lookup"><span data-stu-id="3a3d3-175">In the tree, expand 'model: Data model Financial dimensions sample model\Journal: Record list'.</span></span>
4. <span data-ttu-id="3a3d3-176">Dans l’arborescence, développez « Modèle : Exemple de modèle de dimensions financières pour le modèle de données\Journal : Liste d’enregistrements\Transaction : Liste d’enregistrements ».</span><span class="sxs-lookup"><span data-stu-id="3a3d3-176">In the tree, expand 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list'.</span></span>
5. <span data-ttu-id="3a3d3-177">Dans l’arborescence, développez « Modèle : Exemple de modèle de dimensions financières pour le modèle de données\Journal : Liste d’enregistrements\Transaction : Liste d’enregistrements\Données de dimensions : Liste d’enregistrements ».</span><span class="sxs-lookup"><span data-stu-id="3a3d3-177">In the tree, expand 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Dimensions data: Record list'.</span></span>
6. <span data-ttu-id="3a3d3-178">Dans l’arborescence, sélectionnez « Racine : Élément XML\Journal : Élément XML\Transaction : Élément XML\Dimensions : Élément XML\Desc : Attribut XML ».</span><span class="sxs-lookup"><span data-stu-id="3a3d3-178">In the tree, select 'Root: XML Element\Journal: XML Element\Transaction: XML Element\Dimensions: XML Element\Desc: XML Attribute'.</span></span>
7. <span data-ttu-id="3a3d3-179">Dans l’arborescence, sélectionnez « Modèle : Exemple de modèle de dimensions financières pour le modèle de données\Journal : Liste d’enregistrements\Transaction : Liste d’enregistrements\Données de dimensions : Liste d’enregistrements\Description : Chaîne ».</span><span class="sxs-lookup"><span data-stu-id="3a3d3-179">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Dimensions data: Record list\Description: String'.</span></span>
8. <span data-ttu-id="3a3d3-180">Cliquez sur Lier.</span><span class="sxs-lookup"><span data-stu-id="3a3d3-180">Click Bind.</span></span>
9. <span data-ttu-id="3a3d3-181">Dans l’arborescence, sélectionnez « Racine : Élément XML\Journal : Élément XML\Transaction : Élément XML\Dimensions : Élément XML\Valeur : Attribut XML ».</span><span class="sxs-lookup"><span data-stu-id="3a3d3-181">In the tree, select 'Root: XML Element\Journal: XML Element\Transaction: XML Element\Dimensions: XML Element\Value: XML Attribute'.</span></span>
10. <span data-ttu-id="3a3d3-182">Dans l’arborescence, sélectionnez « Modèle : Exemple de modèle de dimensions financières pour le modèle de données\Journal : Liste d’enregistrements\Transaction : Liste d’enregistrements\Données de dimensions : Liste d’enregistrements\Code : Chaîne ».</span><span class="sxs-lookup"><span data-stu-id="3a3d3-182">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Dimensions data: Record list\Code: String'.</span></span>
11. <span data-ttu-id="3a3d3-183">Cliquez sur Lier.</span><span class="sxs-lookup"><span data-stu-id="3a3d3-183">Click Bind.</span></span>
12. <span data-ttu-id="3a3d3-184">Dans l’arborescence, sélectionnez « Racine : Élément XML\Journal : Élément XML\Transaction : Élément XML\Dimensions : Élément XML\Code : Attribut XML ».</span><span class="sxs-lookup"><span data-stu-id="3a3d3-184">In the tree, select 'Root: XML Element\Journal: XML Element\Transaction: XML Element\Dimensions: XML Element\Code: XML Attribute'.</span></span>
13. <span data-ttu-id="3a3d3-185">Dans l’arborescence, sélectionnez « Modèle : Exemple de modèle de dimensions financières pour le modèle de données\Journal : Liste d’enregistrements\Transaction : Liste d’enregistrements\Données de dimensions : Liste d’enregistrements\Nom : Chaîne ».</span><span class="sxs-lookup"><span data-stu-id="3a3d3-185">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Dimensions data: Record list\Name: String'.</span></span>
14. <span data-ttu-id="3a3d3-186">Cliquez sur Lier.</span><span class="sxs-lookup"><span data-stu-id="3a3d3-186">Click Bind.</span></span>
15. <span data-ttu-id="3a3d3-187">Dans l’arborescence, sélectionnez « Modèle : Exemple de modèle de dimensions financières pour le modèle de données\Journal : Liste d’enregistrements\Transaction : Liste d’enregistrements\Données de dimensions : Liste d’enregistrements ».</span><span class="sxs-lookup"><span data-stu-id="3a3d3-187">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Dimensions data: Record list'.</span></span>
16. <span data-ttu-id="3a3d3-188">Dans l’arborescence, sélectionnez « Racine : Élément XML\Journal : Élément XML\Transaction : Élément XML\Dimensions : Élément XML ».</span><span class="sxs-lookup"><span data-stu-id="3a3d3-188">In the tree, select 'Root: XML Element\Journal: XML Element\Transaction: XML Element\Dimensions: XML Element'.</span></span>
17. <span data-ttu-id="3a3d3-189">Cliquez sur Lier.</span><span class="sxs-lookup"><span data-stu-id="3a3d3-189">Click Bind.</span></span>
18. <span data-ttu-id="3a3d3-190">Dans l’arborescence, sélectionnez « Racine : Élément XML\Journal : Élément XML\Transaction : Élément XML\Ct : Attribut XML ».</span><span class="sxs-lookup"><span data-stu-id="3a3d3-190">In the tree, select 'Root: XML Element\Journal: XML Element\Transaction: XML Element\Ct: XML Attribute'.</span></span>
19. <span data-ttu-id="3a3d3-191">Dans l’arborescence, sélectionnez « Modèle : Exemple de modèle de dimensions financières pour le modèle de données\Journal : Liste d’enregistrements\Transaction : Liste d’enregistrements\Crédit : Réel ».</span><span class="sxs-lookup"><span data-stu-id="3a3d3-191">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Credit: Real'.</span></span>
20. <span data-ttu-id="3a3d3-192">Cliquez sur Lier.</span><span class="sxs-lookup"><span data-stu-id="3a3d3-192">Click Bind.</span></span>
21. <span data-ttu-id="3a3d3-193">Dans l’arborescence, sélectionnez « Racine : Élément XML\Journal : Élément XML\Transaction : Élément XML\Dt : Attribut XML ».</span><span class="sxs-lookup"><span data-stu-id="3a3d3-193">In the tree, select 'Root: XML Element\Journal: XML Element\Transaction: XML Element\Dt: XML Attribute'.</span></span>
22. <span data-ttu-id="3a3d3-194">Dans l’arborescence, sélectionnez « Modèle : Exemple de modèle de dimensions financières pour le modèle de données\Journal : Liste d’enregistrements\Transaction : Liste d’enregistrements\Débit : Réel ».</span><span class="sxs-lookup"><span data-stu-id="3a3d3-194">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Debit: Real'.</span></span>
23. <span data-ttu-id="3a3d3-195">Cliquez sur Lier.</span><span class="sxs-lookup"><span data-stu-id="3a3d3-195">Click Bind.</span></span>
24. <span data-ttu-id="3a3d3-196">Dans l’arborescence, sélectionnez « Racine : Élément XML\Journal : Élément XML\Transaction : Élément XML\Devise : Attribut XML ».</span><span class="sxs-lookup"><span data-stu-id="3a3d3-196">In the tree, select 'Root: XML Element\Journal: XML Element\Transaction: XML Element\Currency: XML Attribute'.</span></span>
25. <span data-ttu-id="3a3d3-197">Dans l’arborescence, sélectionnez « Modèle : Exemple de modèle de dimensions financières pour le modèle de données\Journal : Liste d’enregistrements\Transaction : Liste d’enregistrements\Devise : Chaîne ».</span><span class="sxs-lookup"><span data-stu-id="3a3d3-197">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Currency: String'.</span></span>
26. <span data-ttu-id="3a3d3-198">Cliquez sur Lier.</span><span class="sxs-lookup"><span data-stu-id="3a3d3-198">Click Bind.</span></span>
27. <span data-ttu-id="3a3d3-199">Dans l’arborescence, sélectionnez « Racine : Élément XML\Journal : Élément XML\Transaction : Élément XML\Date : Attribut XML ».</span><span class="sxs-lookup"><span data-stu-id="3a3d3-199">In the tree, select 'Root: XML Element\Journal: XML Element\Transaction: XML Element\Date: XML Attribute'.</span></span>
28. <span data-ttu-id="3a3d3-200">Dans l’arborescence, sélectionnez « Modèle : Exemple de modèle de dimensions financières pour le modèle de données\Journal : Liste d’enregistrements\Transaction : Liste d’enregistrements\Date : Date ».</span><span class="sxs-lookup"><span data-stu-id="3a3d3-200">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Date: Date'.</span></span>
29. <span data-ttu-id="3a3d3-201">Cliquez sur Lier.</span><span class="sxs-lookup"><span data-stu-id="3a3d3-201">Click Bind.</span></span>
30. <span data-ttu-id="3a3d3-202">Dans l’arborescence, sélectionnez « Racine : Élément XML\Journal : Élément XML\Transaction : Élément XML\N° document : Attribut XML ».</span><span class="sxs-lookup"><span data-stu-id="3a3d3-202">In the tree, select 'Root: XML Element\Journal: XML Element\Transaction: XML Element\Voucher: XML Attribute'.</span></span>
31. <span data-ttu-id="3a3d3-203">Dans l’arborescence, sélectionnez « Modèle : Exemple de modèle de dimensions financières pour le modèle de données\Journal : Liste d’enregistrements\Transaction : Liste d’enregistrements\N° document : Chaîne ».</span><span class="sxs-lookup"><span data-stu-id="3a3d3-203">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Voucher: String'.</span></span>
32. <span data-ttu-id="3a3d3-204">Cliquez sur Lier.</span><span class="sxs-lookup"><span data-stu-id="3a3d3-204">Click Bind.</span></span>
33. <span data-ttu-id="3a3d3-205">Dans l’arborescence, sélectionnez « Racine : Élément XML\Journal : Élément XML\Transaction : Élément XML ».</span><span class="sxs-lookup"><span data-stu-id="3a3d3-205">In the tree, select 'Root: XML Element\Journal: XML Element\Transaction: XML Element'.</span></span>
34. <span data-ttu-id="3a3d3-206">Dans l’arborescence, sélectionnez « Modèle : Exemple de modèle de dimensions financières pour le modèle de données\Journal : Liste d’enregistrements\Transaction : Liste d’enregistrements ».</span><span class="sxs-lookup"><span data-stu-id="3a3d3-206">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list'.</span></span>
35. <span data-ttu-id="3a3d3-207">Cliquez sur Lier.</span><span class="sxs-lookup"><span data-stu-id="3a3d3-207">Click Bind.</span></span>
36. <span data-ttu-id="3a3d3-208">Dans l’arborescence, sélectionnez « Racine : Élément XML\Journal : Élément XML\Lot : Attribut XML ».</span><span class="sxs-lookup"><span data-stu-id="3a3d3-208">In the tree, select 'Root: XML Element\Journal: XML Element\Batch: XML Attribute'.</span></span>
37. <span data-ttu-id="3a3d3-209">Dans l’arborescence, sélectionnez « Modèle : Exemple de modèle de dimensions financières pour le modèle de données\Journal : Liste d’enregistrements\Lot : Chaîne ».</span><span class="sxs-lookup"><span data-stu-id="3a3d3-209">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list\Batch: String'.</span></span>
38. <span data-ttu-id="3a3d3-210">Cliquez sur Lier.</span><span class="sxs-lookup"><span data-stu-id="3a3d3-210">Click Bind.</span></span>
39. <span data-ttu-id="3a3d3-211">Dans l’arborescence, sélectionnez « Racine : Élément XML\Journal : Élément XML ».</span><span class="sxs-lookup"><span data-stu-id="3a3d3-211">In the tree, select 'Root: XML Element\Journal: XML Element'.</span></span>
40. <span data-ttu-id="3a3d3-212">Dans l’arborescence, sélectionnez « Modèle : Exemple de modèle de dimensions financières pour le modèle de données\Journal : Liste d’enregistrements ».</span><span class="sxs-lookup"><span data-stu-id="3a3d3-212">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list'.</span></span>
41. <span data-ttu-id="3a3d3-213">Cliquez sur Lier.</span><span class="sxs-lookup"><span data-stu-id="3a3d3-213">Click Bind.</span></span>
42. <span data-ttu-id="3a3d3-214">Dans l’arborescence, sélectionnez « Racine : Élément XML\Société : Attribut XML ».</span><span class="sxs-lookup"><span data-stu-id="3a3d3-214">In the tree, select 'Root: XML Element\Company: XML Attribute'.</span></span>
43. <span data-ttu-id="3a3d3-215">Dans l’arborescence, sélectionnez « Modèle : Exemple de modèle de dimensions financières pour le modèle de données\Société : Chaîne ».</span><span class="sxs-lookup"><span data-stu-id="3a3d3-215">In the tree, select 'model: Data model Financial dimensions sample model\Company: String'.</span></span>
44. <span data-ttu-id="3a3d3-216">Cliquez sur Lier.</span><span class="sxs-lookup"><span data-stu-id="3a3d3-216">Click Bind.</span></span>
45. <span data-ttu-id="3a3d3-217">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="3a3d3-217">Click Save.</span></span>
46. <span data-ttu-id="3a3d3-218">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="3a3d3-218">Close the page.</span></span>
<span data-ttu-id="3a3d3-219">![Page Concepteur d’opérations de gestion des états électroniques](../media/er-financial-dimensions-guides-format2.png)</span><span class="sxs-lookup"><span data-stu-id="3a3d3-219">![ER Operations designer page](../media/er-financial-dimensions-guides-format2.png)</span></span>



[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]