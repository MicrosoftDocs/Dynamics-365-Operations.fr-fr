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
ms.openlocfilehash: 45096a728ad6f9e331b53b4e12ca0ff9317a3939
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/15/2019
ms.locfileid: "1544723"
---
# <a name="er-use-financial-dimensions-as-a-data-source-part-3-design-the-report"></a><span data-ttu-id="cad96-103">ER Utiliser les dimensions financières comme source de données (Partie 3 : Créer l'état)</span><span class="sxs-lookup"><span data-stu-id="cad96-103">ER Use financial dimensions as a data source (Part 3: Design the report)</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="cad96-104">Les étapes suivantes expliquent comment un utilisateur affecté au rôle d'administrateur système ou de développeur d'états électroniques peut configurer un modèle de génération d'états électroniques (ER) pour utiliser les dimensions financières comme source de données pour les états ER.</span><span class="sxs-lookup"><span data-stu-id="cad96-104">The following steps explain how a user assigned to the system administrator or electronic reporting developer role can configure an Electronic reporting (ER) model to use financial dimensions as a data source for ER reports.</span></span> <span data-ttu-id="cad96-105">Ces étapes peuvent être effectuées dans n'importe quelle société.</span><span class="sxs-lookup"><span data-stu-id="cad96-105">These steps can be performed in any company.</span></span>

<span data-ttu-id="cad96-106">Pour effectuer ces étapes, vous devez d'abord effectuer les étapes de la procédure « ER Utiliser les dimensions financières comme source de données (Partie 2 : mise en correspondance des modèles) ».</span><span class="sxs-lookup"><span data-stu-id="cad96-106">To complete these steps, you must first complete the steps in the “ER Use financial dimensions as a data source (Part 2: Model mapping)” procedure.</span></span>


## <a name="design-a-report-to-present-financial-dimensions"></a><span data-ttu-id="cad96-107">Créer un état pour présenter des dimensions financières</span><span class="sxs-lookup"><span data-stu-id="cad96-107">Design a report to present financial dimensions</span></span>
1. <span data-ttu-id="cad96-108">Accédez à Administration d'organisation > États électroniques > Configurations.</span><span class="sxs-lookup"><span data-stu-id="cad96-108">Go to Organization administration > Electronic reporting > Configurations.</span></span>
2. <span data-ttu-id="cad96-109">Dans l'arborescence, sélectionnez « Exemple de modèle de dimensions financières ».</span><span class="sxs-lookup"><span data-stu-id="cad96-109">In the tree, select 'Financial dimensions sample model'.</span></span>
3. <span data-ttu-id="cad96-110">Cliquez sur Créer la configuration pour ouvrir la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="cad96-110">Click Create configuration to open the drop dialog.</span></span>
4. <span data-ttu-id="cad96-111">Dans le champ Nouveau, entrez « Format basé sur l'exemple de modèle de dimensions financières pour le modèle de données ».</span><span class="sxs-lookup"><span data-stu-id="cad96-111">In the New field, enter 'Format based on data model Financial dimensions sample model'.</span></span>
    * <span data-ttu-id="cad96-112">Utilisez le modèle créé à l'avance comme source de données de votre nouvel état.</span><span class="sxs-lookup"><span data-stu-id="cad96-112">Use the model that was created in advance as the data source for your new report.</span></span>  
5. <span data-ttu-id="cad96-113">Dans le champ Nom, tapez « État du journal comptable ».</span><span class="sxs-lookup"><span data-stu-id="cad96-113">In the Name field, type 'Ledger journal report'.</span></span>
6. <span data-ttu-id="cad96-114">Dans le champ Définition du modèle de données, sélectionnez Entrée.</span><span class="sxs-lookup"><span data-stu-id="cad96-114">In the Data model definition field, select Entry.</span></span>
7. <span data-ttu-id="cad96-115">Cliquez sur Créer une configuration.</span><span class="sxs-lookup"><span data-stu-id="cad96-115">Click Create configuration.</span></span>
8. <span data-ttu-id="cad96-116">Cliquez sur Concepteur.</span><span class="sxs-lookup"><span data-stu-id="cad96-116">Click Designer.</span></span>
9. <span data-ttu-id="cad96-117">Cliquez sur Ajouter racine pour ouvrir la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="cad96-117">Click Add root to open the drop dialog.</span></span>
10. <span data-ttu-id="cad96-118">Dans l'arborescence , sélectionnez « XML\Élément ».</span><span class="sxs-lookup"><span data-stu-id="cad96-118">In the tree, select 'XML\Element'.</span></span>
11. <span data-ttu-id="cad96-119">Dans le champ Nom, tapez « Racine ».</span><span class="sxs-lookup"><span data-stu-id="cad96-119">In the Name field, type 'Root'.</span></span>
12. <span data-ttu-id="cad96-120">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="cad96-120">Click OK.</span></span>
13. <span data-ttu-id="cad96-121">Cliquez sur Ajouter pour ouvrir la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="cad96-121">Click Add to open the drop dialog.</span></span>
14. <span data-ttu-id="cad96-122">Dans l'arborescence, sélectionnez « XML\Attribut ».</span><span class="sxs-lookup"><span data-stu-id="cad96-122">In the tree, select 'XML\Attribute'.</span></span>
15. <span data-ttu-id="cad96-123">Dans le champ Nom, tapez « Société ».</span><span class="sxs-lookup"><span data-stu-id="cad96-123">In the Name field, type 'Company'.</span></span>
16. <span data-ttu-id="cad96-124">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="cad96-124">Click OK.</span></span>
17. <span data-ttu-id="cad96-125">Cliquez sur Ajouter pour ouvrir la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="cad96-125">Click Add to open the drop dialog.</span></span>
18. <span data-ttu-id="cad96-126">Dans l'arborescence , sélectionnez « XML\Élément ».</span><span class="sxs-lookup"><span data-stu-id="cad96-126">In the tree, select 'XML\Element'.</span></span>
19. <span data-ttu-id="cad96-127">Dans le champ Nom, tapez « Journal ».</span><span class="sxs-lookup"><span data-stu-id="cad96-127">In the Name field, type 'Journal'.</span></span>
20. <span data-ttu-id="cad96-128">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="cad96-128">Click OK.</span></span>
21. <span data-ttu-id="cad96-129">Dans l'arborescence, sélectionnez « Racine : Élément XML\Journal : Élément XML ».</span><span class="sxs-lookup"><span data-stu-id="cad96-129">In the tree, select 'Root: XML Element\Journal: XML Element'.</span></span>
22. <span data-ttu-id="cad96-130">Cliquez sur Ajouter pour ouvrir la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="cad96-130">Click Add to open the drop dialog.</span></span>
23. <span data-ttu-id="cad96-131">Dans l'arborescence, sélectionnez « XML\Attribut ».</span><span class="sxs-lookup"><span data-stu-id="cad96-131">In the tree, select 'XML\Attribute'.</span></span>
24. <span data-ttu-id="cad96-132">Dans le champ Nom, tapez « Traitement par lots ».</span><span class="sxs-lookup"><span data-stu-id="cad96-132">In the Name field, type 'Batch'.</span></span>
25. <span data-ttu-id="cad96-133">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="cad96-133">Click OK.</span></span>
26. <span data-ttu-id="cad96-134">Cliquez sur Ajouter pour ouvrir la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="cad96-134">Click Add to open the drop dialog.</span></span>
27. <span data-ttu-id="cad96-135">Dans l'arborescence , sélectionnez « XML\Élément ».</span><span class="sxs-lookup"><span data-stu-id="cad96-135">In the tree, select 'XML\Element'.</span></span>
28. <span data-ttu-id="cad96-136">Dans le champ Nom, tapez « Transaction ».</span><span class="sxs-lookup"><span data-stu-id="cad96-136">In the Name field, type 'Transaction'.</span></span>
29. <span data-ttu-id="cad96-137">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="cad96-137">Click OK.</span></span>
30. <span data-ttu-id="cad96-138">Dans l'arborescence, sélectionnez « Racine : Élément XML\Journal : Élément XML\Transaction : Élément XML ».</span><span class="sxs-lookup"><span data-stu-id="cad96-138">In the tree, select 'Root: XML Element\Journal: XML Element\Transaction: XML Element'.</span></span>
31. <span data-ttu-id="cad96-139">Cliquez sur Ajouter pour ouvrir la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="cad96-139">Click Add to open the drop dialog.</span></span>
32. <span data-ttu-id="cad96-140">Dans l'arborescence, sélectionnez « XML\Attribut ».</span><span class="sxs-lookup"><span data-stu-id="cad96-140">In the tree, select 'XML\Attribute'.</span></span>
33. <span data-ttu-id="cad96-141">Dans le champ Nom, tapez « N° document ».</span><span class="sxs-lookup"><span data-stu-id="cad96-141">In the Name field, type 'Voucher'.</span></span>
34. <span data-ttu-id="cad96-142">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="cad96-142">Click OK.</span></span>
35. <span data-ttu-id="cad96-143">Cliquez sur Ajouter un attribut.</span><span class="sxs-lookup"><span data-stu-id="cad96-143">Click Add Attribute.</span></span>
36. <span data-ttu-id="cad96-144">Dans le champ Nom, tapez « Date ».</span><span class="sxs-lookup"><span data-stu-id="cad96-144">In the Name field, type 'Date'.</span></span>
37. <span data-ttu-id="cad96-145">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="cad96-145">Click OK.</span></span>
38. <span data-ttu-id="cad96-146">Cliquez sur Ajouter un attribut.</span><span class="sxs-lookup"><span data-stu-id="cad96-146">Click Add Attribute.</span></span>
39. <span data-ttu-id="cad96-147">Tapez « Devise » dans le champ Nom.</span><span class="sxs-lookup"><span data-stu-id="cad96-147">In the Name field, type 'Currency'.</span></span>
40. <span data-ttu-id="cad96-148">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="cad96-148">Click OK.</span></span>
41. <span data-ttu-id="cad96-149">Cliquez sur Ajouter un attribut.</span><span class="sxs-lookup"><span data-stu-id="cad96-149">Click Add Attribute.</span></span>
42. <span data-ttu-id="cad96-150">Dans le champ Nom, tapez « Dt ».</span><span class="sxs-lookup"><span data-stu-id="cad96-150">In the Name field, type 'Dt'.</span></span>
43. <span data-ttu-id="cad96-151">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="cad96-151">Click OK.</span></span>
44. <span data-ttu-id="cad96-152">Cliquez sur Ajouter un attribut.</span><span class="sxs-lookup"><span data-stu-id="cad96-152">Click Add Attribute.</span></span>
45. <span data-ttu-id="cad96-153">Dans le champ Nom, tapez « Ct ».</span><span class="sxs-lookup"><span data-stu-id="cad96-153">In the Name field, type 'Ct'.</span></span>
46. <span data-ttu-id="cad96-154">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="cad96-154">Click OK.</span></span>
47. <span data-ttu-id="cad96-155">Cliquez sur Ajouter pour ouvrir la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="cad96-155">Click Add to open the drop dialog.</span></span>
48. <span data-ttu-id="cad96-156">Dans l'arborescence , sélectionnez « XML\Élément ».</span><span class="sxs-lookup"><span data-stu-id="cad96-156">In the tree, select 'XML\Element'.</span></span>
49. <span data-ttu-id="cad96-157">Dans le champ Nom, tapez « Dimensions ».</span><span class="sxs-lookup"><span data-stu-id="cad96-157">In the Name field, type 'Dimensions'.</span></span>
50. <span data-ttu-id="cad96-158">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="cad96-158">Click OK.</span></span>
51. <span data-ttu-id="cad96-159">Dans l'arborescence, sélectionnez « Racine : Élément XML\Journal : Élément XML\Transaction : Élément XML\Dimensions : Élément XML ».</span><span class="sxs-lookup"><span data-stu-id="cad96-159">In the tree, select 'Root: XML Element\Journal: XML Element\Transaction: XML Element\Dimensions: XML Element'.</span></span>
52. <span data-ttu-id="cad96-160">Cliquez sur Ajouter pour ouvrir la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="cad96-160">Click Add to open the drop dialog.</span></span>
53. <span data-ttu-id="cad96-161">Dans l'arborescence, sélectionnez « XML\Attribut ».</span><span class="sxs-lookup"><span data-stu-id="cad96-161">In the tree, select 'XML\Attribute'.</span></span>
54. <span data-ttu-id="cad96-162">Dans le champ Nom, tapez « Code ».</span><span class="sxs-lookup"><span data-stu-id="cad96-162">In the Name field, type 'Code'.</span></span>
55. <span data-ttu-id="cad96-163">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="cad96-163">Click OK.</span></span>
56. <span data-ttu-id="cad96-164">Cliquez sur Ajouter un attribut.</span><span class="sxs-lookup"><span data-stu-id="cad96-164">Click Add Attribute.</span></span>
57. <span data-ttu-id="cad96-165">Dans le champ Nom, tapez « Valeur ».</span><span class="sxs-lookup"><span data-stu-id="cad96-165">In the Name field, type 'Value'.</span></span>
58. <span data-ttu-id="cad96-166">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="cad96-166">Click OK.</span></span>
59. <span data-ttu-id="cad96-167">Cliquez sur Ajouter un attribut.</span><span class="sxs-lookup"><span data-stu-id="cad96-167">Click Add Attribute.</span></span>
60. <span data-ttu-id="cad96-168">Dans le champ Nom, tapez « Desc ».</span><span class="sxs-lookup"><span data-stu-id="cad96-168">In the Name field, type 'Desc'.</span></span>
61. <span data-ttu-id="cad96-169">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="cad96-169">Click OK.</span></span>

## <a name="map-report-elements-to-data-sources"></a><span data-ttu-id="cad96-170">Mettre en correspondance les éléments d'état avec les sources de données</span><span class="sxs-lookup"><span data-stu-id="cad96-170">Map report elements to data sources</span></span>
1. <span data-ttu-id="cad96-171">Cliquez sur l'onglet Mise en relation.</span><span class="sxs-lookup"><span data-stu-id="cad96-171">Click the Mapping tab.</span></span>
2. <span data-ttu-id="cad96-172">Dans l'arborescence, développez « Modèle : Exemple de modèle de dimensions financières pour le modèle de données ».</span><span class="sxs-lookup"><span data-stu-id="cad96-172">In the tree, expand 'model: Data model Financial dimensions sample model'.</span></span>
3. <span data-ttu-id="cad96-173">Dans l'arborescence, développez « Modèle : Exemple de modèle de dimensions financières pour le modèle de données\Journal : Liste d'enregistrements ».</span><span class="sxs-lookup"><span data-stu-id="cad96-173">In the tree, expand 'model: Data model Financial dimensions sample model\Journal: Record list'.</span></span>
4. <span data-ttu-id="cad96-174">Dans l'arborescence, développez « Modèle : Exemple de modèle de dimensions financières pour le modèle de données\Journal : Liste d'enregistrements\Transaction : Liste d'enregistrements ».</span><span class="sxs-lookup"><span data-stu-id="cad96-174">In the tree, expand 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list'.</span></span>
5. <span data-ttu-id="cad96-175">Dans l'arborescence, développez « Modèle : Exemple de modèle de dimensions financières pour le modèle de données\Journal : Liste d'enregistrements\Transaction : Liste d'enregistrements\Données de dimensions : Liste d'enregistrements ».</span><span class="sxs-lookup"><span data-stu-id="cad96-175">In the tree, expand 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Dimensions data: Record list'.</span></span>
6. <span data-ttu-id="cad96-176">Dans l'arborescence, sélectionnez « Racine : Élément XML\Journal : Élément XML\Transaction : Élément XML\Dimensions : Élément XML\Desc : Attribut XML ».</span><span class="sxs-lookup"><span data-stu-id="cad96-176">In the tree, select 'Root: XML Element\Journal: XML Element\Transaction: XML Element\Dimensions: XML Element\Desc: XML Attribute'.</span></span>
7. <span data-ttu-id="cad96-177">Dans l'arborescence, sélectionnez « Modèle : Exemple de modèle de dimensions financières pour le modèle de données\Journal : Liste d'enregistrements\Transaction : Liste d'enregistrements\Données de dimensions : Liste d'enregistrements\Description : Chaîne ».</span><span class="sxs-lookup"><span data-stu-id="cad96-177">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Dimensions data: Record list\Description: String'.</span></span>
8. <span data-ttu-id="cad96-178">Cliquez sur Lier.</span><span class="sxs-lookup"><span data-stu-id="cad96-178">Click Bind.</span></span>
9. <span data-ttu-id="cad96-179">Dans l'arborescence, sélectionnez « Racine : Élément XML\Journal : Élément XML\Transaction : Élément XML\Dimensions : Élément XML\Valeur : Attribut XML ».</span><span class="sxs-lookup"><span data-stu-id="cad96-179">In the tree, select 'Root: XML Element\Journal: XML Element\Transaction: XML Element\Dimensions: XML Element\Value: XML Attribute'.</span></span>
10. <span data-ttu-id="cad96-180">Dans l'arborescence, sélectionnez « Modèle : Exemple de modèle de dimensions financières pour le modèle de données\Journal : Liste d'enregistrements\Transaction : Liste d'enregistrements\Données de dimensions : Liste d'enregistrements\Code : Chaîne ».</span><span class="sxs-lookup"><span data-stu-id="cad96-180">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Dimensions data: Record list\Code: String'.</span></span>
11. <span data-ttu-id="cad96-181">Cliquez sur Lier.</span><span class="sxs-lookup"><span data-stu-id="cad96-181">Click Bind.</span></span>
12. <span data-ttu-id="cad96-182">Dans l'arborescence, sélectionnez « Racine : Élément XML\Journal : Élément XML\Transaction : Élément XML\Dimensions : Élément XML\Code : Attribut XML ».</span><span class="sxs-lookup"><span data-stu-id="cad96-182">In the tree, select 'Root: XML Element\Journal: XML Element\Transaction: XML Element\Dimensions: XML Element\Code: XML Attribute'.</span></span>
13. <span data-ttu-id="cad96-183">Dans l'arborescence, sélectionnez « Modèle : Exemple de modèle de dimensions financières pour le modèle de données\Journal : Liste d'enregistrements\Transaction : Liste d'enregistrements\Données de dimensions : Liste d'enregistrements\Nom : Chaîne ».</span><span class="sxs-lookup"><span data-stu-id="cad96-183">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Dimensions data: Record list\Name: String'.</span></span>
14. <span data-ttu-id="cad96-184">Cliquez sur Lier.</span><span class="sxs-lookup"><span data-stu-id="cad96-184">Click Bind.</span></span>
15. <span data-ttu-id="cad96-185">Dans l'arborescence, sélectionnez « Modèle : Exemple de modèle de dimensions financières pour le modèle de données\Journal : Liste d'enregistrements\Transaction : Liste d'enregistrements\Données de dimensions : Liste d'enregistrements ».</span><span class="sxs-lookup"><span data-stu-id="cad96-185">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Dimensions data: Record list'.</span></span>
16. <span data-ttu-id="cad96-186">Dans l'arborescence, sélectionnez « Racine : Élément XML\Journal : Élément XML\Transaction : Élément XML\Dimensions : Élément XML ».</span><span class="sxs-lookup"><span data-stu-id="cad96-186">In the tree, select 'Root: XML Element\Journal: XML Element\Transaction: XML Element\Dimensions: XML Element'.</span></span>
17. <span data-ttu-id="cad96-187">Cliquez sur Lier.</span><span class="sxs-lookup"><span data-stu-id="cad96-187">Click Bind.</span></span>
18. <span data-ttu-id="cad96-188">Dans l'arborescence, sélectionnez « Racine : Élément XML\Journal : Élément XML\Transaction : Élément XML\Ct : Attribut XML ».</span><span class="sxs-lookup"><span data-stu-id="cad96-188">In the tree, select 'Root: XML Element\Journal: XML Element\Transaction: XML Element\Ct: XML Attribute'.</span></span>
19. <span data-ttu-id="cad96-189">Dans l'arborescence, sélectionnez « Modèle : Exemple de modèle de dimensions financières pour le modèle de données\Journal : Liste d'enregistrements\Transaction : Liste d'enregistrements\Crédit : Réel ».</span><span class="sxs-lookup"><span data-stu-id="cad96-189">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Credit: Real'.</span></span>
20. <span data-ttu-id="cad96-190">Cliquez sur Lier.</span><span class="sxs-lookup"><span data-stu-id="cad96-190">Click Bind.</span></span>
21. <span data-ttu-id="cad96-191">Dans l'arborescence, sélectionnez « Racine : Élément XML\Journal : Élément XML\Transaction : Élément XML\Dt : Attribut XML ».</span><span class="sxs-lookup"><span data-stu-id="cad96-191">In the tree, select 'Root: XML Element\Journal: XML Element\Transaction: XML Element\Dt: XML Attribute'.</span></span>
22. <span data-ttu-id="cad96-192">Dans l'arborescence, sélectionnez « Modèle : Exemple de modèle de dimensions financières pour le modèle de données\Journal : Liste d'enregistrements\Transaction : Liste d'enregistrements\Débit : Réel ».</span><span class="sxs-lookup"><span data-stu-id="cad96-192">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Debit: Real'.</span></span>
23. <span data-ttu-id="cad96-193">Cliquez sur Lier.</span><span class="sxs-lookup"><span data-stu-id="cad96-193">Click Bind.</span></span>
24. <span data-ttu-id="cad96-194">Dans l'arborescence, sélectionnez « Racine : Élément XML\Journal : Élément XML\Transaction : Élément XML\Devise : Attribut XML ».</span><span class="sxs-lookup"><span data-stu-id="cad96-194">In the tree, select 'Root: XML Element\Journal: XML Element\Transaction: XML Element\Currency: XML Attribute'.</span></span>
25. <span data-ttu-id="cad96-195">Dans l'arborescence, sélectionnez « Modèle : Exemple de modèle de dimensions financières pour le modèle de données\Journal : Liste d'enregistrements\Transaction : Liste d'enregistrements\Devise : Chaîne ».</span><span class="sxs-lookup"><span data-stu-id="cad96-195">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Currency: String'.</span></span>
26. <span data-ttu-id="cad96-196">Cliquez sur Lier.</span><span class="sxs-lookup"><span data-stu-id="cad96-196">Click Bind.</span></span>
27. <span data-ttu-id="cad96-197">Dans l'arborescence, sélectionnez « Racine : Élément XML\Journal : Élément XML\Transaction : Élément XML\Date : Attribut XML ».</span><span class="sxs-lookup"><span data-stu-id="cad96-197">In the tree, select 'Root: XML Element\Journal: XML Element\Transaction: XML Element\Date: XML Attribute'.</span></span>
28. <span data-ttu-id="cad96-198">Dans l'arborescence, sélectionnez « Modèle : Exemple de modèle de dimensions financières pour le modèle de données\Journal : Liste d'enregistrements\Transaction : Liste d'enregistrements\Date : Date ».</span><span class="sxs-lookup"><span data-stu-id="cad96-198">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Date: Date'.</span></span>
29. <span data-ttu-id="cad96-199">Cliquez sur Lier.</span><span class="sxs-lookup"><span data-stu-id="cad96-199">Click Bind.</span></span>
30. <span data-ttu-id="cad96-200">Dans l'arborescence, sélectionnez « Racine : Élément XML\Journal : Élément XML\Transaction : Élément XML\N° document : Attribut XML ».</span><span class="sxs-lookup"><span data-stu-id="cad96-200">In the tree, select 'Root: XML Element\Journal: XML Element\Transaction: XML Element\Voucher: XML Attribute'.</span></span>
31. <span data-ttu-id="cad96-201">Dans l'arborescence, sélectionnez « Modèle : Exemple de modèle de dimensions financières pour le modèle de données\Journal : Liste d'enregistrements\Transaction : Liste d'enregistrements\N° document : Chaîne ».</span><span class="sxs-lookup"><span data-stu-id="cad96-201">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Voucher: String'.</span></span>
32. <span data-ttu-id="cad96-202">Cliquez sur Lier.</span><span class="sxs-lookup"><span data-stu-id="cad96-202">Click Bind.</span></span>
33. <span data-ttu-id="cad96-203">Dans l'arborescence, sélectionnez « Racine : Élément XML\Journal : Élément XML\Transaction : Élément XML ».</span><span class="sxs-lookup"><span data-stu-id="cad96-203">In the tree, select 'Root: XML Element\Journal: XML Element\Transaction: XML Element'.</span></span>
34. <span data-ttu-id="cad96-204">Dans l'arborescence, sélectionnez « Modèle : Exemple de modèle de dimensions financières pour le modèle de données\Journal : Liste d'enregistrements\Transaction : Liste d'enregistrements ».</span><span class="sxs-lookup"><span data-stu-id="cad96-204">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list'.</span></span>
35. <span data-ttu-id="cad96-205">Cliquez sur Lier.</span><span class="sxs-lookup"><span data-stu-id="cad96-205">Click Bind.</span></span>
36. <span data-ttu-id="cad96-206">Dans l'arborescence, sélectionnez « Racine : Élément XML\Journal : Élément XML\Lot : Attribut XML ».</span><span class="sxs-lookup"><span data-stu-id="cad96-206">In the tree, select 'Root: XML Element\Journal: XML Element\Batch: XML Attribute'.</span></span>
37. <span data-ttu-id="cad96-207">Dans l'arborescence, sélectionnez « Modèle : Exemple de modèle de dimensions financières pour le modèle de données\Journal : Liste d'enregistrements\Lot : Chaîne ».</span><span class="sxs-lookup"><span data-stu-id="cad96-207">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list\Batch: String'.</span></span>
38. <span data-ttu-id="cad96-208">Cliquez sur Lier.</span><span class="sxs-lookup"><span data-stu-id="cad96-208">Click Bind.</span></span>
39. <span data-ttu-id="cad96-209">Dans l'arborescence, sélectionnez « Racine : Élément XML\Journal : Élément XML ».</span><span class="sxs-lookup"><span data-stu-id="cad96-209">In the tree, select 'Root: XML Element\Journal: XML Element'.</span></span>
40. <span data-ttu-id="cad96-210">Dans l'arborescence, sélectionnez « Modèle : Exemple de modèle de dimensions financières pour le modèle de données\Journal : Liste d'enregistrements ».</span><span class="sxs-lookup"><span data-stu-id="cad96-210">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list'.</span></span>
41. <span data-ttu-id="cad96-211">Cliquez sur Lier.</span><span class="sxs-lookup"><span data-stu-id="cad96-211">Click Bind.</span></span>
42. <span data-ttu-id="cad96-212">Dans l'arborescence, sélectionnez « Racine : Élément XML\Société : Attribut XML ».</span><span class="sxs-lookup"><span data-stu-id="cad96-212">In the tree, select 'Root: XML Element\Company: XML Attribute'.</span></span>
43. <span data-ttu-id="cad96-213">Dans l'arborescence, sélectionnez « Modèle : Exemple de modèle de dimensions financières pour le modèle de données\Société : Chaîne ».</span><span class="sxs-lookup"><span data-stu-id="cad96-213">In the tree, select 'model: Data model Financial dimensions sample model\Company: String'.</span></span>
44. <span data-ttu-id="cad96-214">Cliquez sur Lier.</span><span class="sxs-lookup"><span data-stu-id="cad96-214">Click Bind.</span></span>
45. <span data-ttu-id="cad96-215">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="cad96-215">Click Save.</span></span>
46. <span data-ttu-id="cad96-216">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="cad96-216">Close the page.</span></span>

