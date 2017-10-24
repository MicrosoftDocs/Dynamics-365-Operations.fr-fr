--- 
title: "Concevoir un état pour utiliser les dimensions financières comme source de données pour la gestion des états électroniques (ER)"
description: "Les étapes suivantes expliquent comment un utilisateur affecté au rôle d'administrateur système ou de développeur d'états électroniques peut configurer un modèle de génération d'états électroniques (ER) pour utiliser les dimensions financières comme source de données pour les états ER."
author: NickSelin
manager: AnnBe
ms.date: 10/18/2016
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
ms.openlocfilehash: c67bf235f3514a19893bcefcaae6e3bb11bbb151
ms.contentlocale: fr-fr
ms.lasthandoff: 09/29/2017

---
# <a name="design-a-report-to-use-financial-dimensions-as-a-data-source-for-electronic-reporting-er"></a><span data-ttu-id="ea273-103">Concevoir un état pour utiliser les dimensions financières comme source de données pour la gestion des états électroniques (ER)</span><span class="sxs-lookup"><span data-stu-id="ea273-103">Design a report to use financial dimensions as a data source for electronic reporting (ER)</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="ea273-104">Les étapes suivantes expliquent comment un utilisateur affecté au rôle d'administrateur système ou de développeur d'états électroniques peut configurer un modèle de génération d'états électroniques (ER) pour utiliser les dimensions financières comme source de données pour les états ER.</span><span class="sxs-lookup"><span data-stu-id="ea273-104">The following steps explain how a user assigned to the system administrator or electronic reporting developer role can configure an Electronic reporting (ER) model to use financial dimensions as a data source for ER reports.</span></span> <span data-ttu-id="ea273-105">Ces étapes peuvent être effectuées dans n'importe quelle société.</span><span class="sxs-lookup"><span data-stu-id="ea273-105">These steps can be performed in any company.</span></span>

<span data-ttu-id="ea273-106">Pour effectuer ces étapes, vous devez d'abord effectuer les étapes de la procédure « ER Utiliser les dimensions financières comme source de données (Partie 2 : mise en correspondance des modèles) ».</span><span class="sxs-lookup"><span data-stu-id="ea273-106">To complete these steps, you must first complete the steps in the “ER Use financial dimensions as a data source (Part 2: Model mapping)” procedure.</span></span>


## <a name="design-a-report-to-present-financial-dimensions"></a><span data-ttu-id="ea273-107">Créer un état pour présenter des dimensions financières</span><span class="sxs-lookup"><span data-stu-id="ea273-107">Design a report to present financial dimensions</span></span>
1. <span data-ttu-id="ea273-108">Accédez à Administration d'organisation > États électroniques > Configurations.</span><span class="sxs-lookup"><span data-stu-id="ea273-108">Go to Organization administration > Electronic reporting > Configurations.</span></span>
2. <span data-ttu-id="ea273-109">Dans l'arborescence, sélectionnez « Exemple de modèle de dimensions financières ».</span><span class="sxs-lookup"><span data-stu-id="ea273-109">In the tree, select 'Financial dimensions sample model'.</span></span>
3. <span data-ttu-id="ea273-110">Cliquez sur Créer la configuration pour ouvrir la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="ea273-110">Click Create configuration to open the drop dialog.</span></span>
4. <span data-ttu-id="ea273-111">Dans le champ Nouveau, entrez « Format basé sur l'exemple de modèle de dimensions financières pour le modèle de données ».</span><span class="sxs-lookup"><span data-stu-id="ea273-111">In the New field, enter 'Format based on data model Financial dimensions sample model'.</span></span>
    * <span data-ttu-id="ea273-112">Utilisez le modèle créé à l'avance comme source de données de votre nouvel état.</span><span class="sxs-lookup"><span data-stu-id="ea273-112">Use the model that was created in advance as the data source for your new report.</span></span>  
5. <span data-ttu-id="ea273-113">Dans le champ Nom, tapez « État du journal comptable ».</span><span class="sxs-lookup"><span data-stu-id="ea273-113">In the Name field, type 'Ledger journal report'.</span></span>
6. <span data-ttu-id="ea273-114">Dans le champ Définition du modèle de données, sélectionnez Entrée.</span><span class="sxs-lookup"><span data-stu-id="ea273-114">In the Data model definition field, select Entry.</span></span>
7. <span data-ttu-id="ea273-115">Cliquez sur Créer une configuration.</span><span class="sxs-lookup"><span data-stu-id="ea273-115">Click Create configuration.</span></span>
8. <span data-ttu-id="ea273-116">Cliquez sur Concepteur.</span><span class="sxs-lookup"><span data-stu-id="ea273-116">Click Designer.</span></span>
9. <span data-ttu-id="ea273-117">Cliquez sur Ajouter racine pour ouvrir la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="ea273-117">Click Add root to open the drop dialog.</span></span>
10. <span data-ttu-id="ea273-118">Dans l'arborescence , sélectionnez « XML\Élément ».</span><span class="sxs-lookup"><span data-stu-id="ea273-118">In the tree, select 'XML\Element'.</span></span>
11. <span data-ttu-id="ea273-119">Dans le champ Nom, tapez « Racine ».</span><span class="sxs-lookup"><span data-stu-id="ea273-119">In the Name field, type 'Root'.</span></span>
12. <span data-ttu-id="ea273-120">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="ea273-120">Click OK.</span></span>
13. <span data-ttu-id="ea273-121">Cliquez sur Ajouter pour ouvrir la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="ea273-121">Click Add to open the drop dialog.</span></span>
14. <span data-ttu-id="ea273-122">Dans l'arborescence, sélectionnez « XML\Attribut ».</span><span class="sxs-lookup"><span data-stu-id="ea273-122">In the tree, select 'XML\Attribute'.</span></span>
15. <span data-ttu-id="ea273-123">Dans le champ Nom, tapez « Société ».</span><span class="sxs-lookup"><span data-stu-id="ea273-123">In the Name field, type 'Company'.</span></span>
16. <span data-ttu-id="ea273-124">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="ea273-124">Click OK.</span></span>
17. <span data-ttu-id="ea273-125">Cliquez sur Ajouter pour ouvrir la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="ea273-125">Click Add to open the drop dialog.</span></span>
18. <span data-ttu-id="ea273-126">Dans l'arborescence , sélectionnez « XML\Élément ».</span><span class="sxs-lookup"><span data-stu-id="ea273-126">In the tree, select 'XML\Element'.</span></span>
19. <span data-ttu-id="ea273-127">Dans le champ Nom, tapez « Journal ».</span><span class="sxs-lookup"><span data-stu-id="ea273-127">In the Name field, type 'Journal'.</span></span>
20. <span data-ttu-id="ea273-128">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="ea273-128">Click OK.</span></span>
21. <span data-ttu-id="ea273-129">Dans l'arborescence, sélectionnez « Racine : Élément XML\Journal : Élément XML ».</span><span class="sxs-lookup"><span data-stu-id="ea273-129">In the tree, select 'Root: XML Element\Journal: XML Element'.</span></span>
22. <span data-ttu-id="ea273-130">Cliquez sur Ajouter pour ouvrir la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="ea273-130">Click Add to open the drop dialog.</span></span>
23. <span data-ttu-id="ea273-131">Dans l'arborescence, sélectionnez « XML\Attribut ».</span><span class="sxs-lookup"><span data-stu-id="ea273-131">In the tree, select 'XML\Attribute'.</span></span>
24. <span data-ttu-id="ea273-132">Dans le champ Nom, tapez « Traitement par lots ».</span><span class="sxs-lookup"><span data-stu-id="ea273-132">In the Name field, type 'Batch'.</span></span>
25. <span data-ttu-id="ea273-133">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="ea273-133">Click OK.</span></span>
26. <span data-ttu-id="ea273-134">Cliquez sur Ajouter pour ouvrir la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="ea273-134">Click Add to open the drop dialog.</span></span>
27. <span data-ttu-id="ea273-135">Dans l'arborescence , sélectionnez « XML\Élément ».</span><span class="sxs-lookup"><span data-stu-id="ea273-135">In the tree, select 'XML\Element'.</span></span>
28. <span data-ttu-id="ea273-136">Dans le champ Nom, tapez « Transaction ».</span><span class="sxs-lookup"><span data-stu-id="ea273-136">In the Name field, type 'Transaction'.</span></span>
29. <span data-ttu-id="ea273-137">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="ea273-137">Click OK.</span></span>
30. <span data-ttu-id="ea273-138">Dans l'arborescence, sélectionnez « Racine : Élément XML\Journal : Élément XML\Transaction : Élément XML ».</span><span class="sxs-lookup"><span data-stu-id="ea273-138">In the tree, select 'Root: XML Element\Journal: XML Element\Transaction: XML Element'.</span></span>
31. <span data-ttu-id="ea273-139">Cliquez sur Ajouter pour ouvrir la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="ea273-139">Click Add to open the drop dialog.</span></span>
32. <span data-ttu-id="ea273-140">Dans l'arborescence, sélectionnez « XML\Attribut ».</span><span class="sxs-lookup"><span data-stu-id="ea273-140">In the tree, select 'XML\Attribute'.</span></span>
33. <span data-ttu-id="ea273-141">Dans le champ Nom, tapez « N° document ».</span><span class="sxs-lookup"><span data-stu-id="ea273-141">In the Name field, type 'Voucher'.</span></span>
34. <span data-ttu-id="ea273-142">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="ea273-142">Click OK.</span></span>
35. <span data-ttu-id="ea273-143">Cliquez sur Ajouter un attribut.</span><span class="sxs-lookup"><span data-stu-id="ea273-143">Click Add Attribute.</span></span>
36. <span data-ttu-id="ea273-144">Dans le champ Nom, tapez « Date ».</span><span class="sxs-lookup"><span data-stu-id="ea273-144">In the Name field, type 'Date'.</span></span>
37. <span data-ttu-id="ea273-145">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="ea273-145">Click OK.</span></span>
38. <span data-ttu-id="ea273-146">Cliquez sur Ajouter un attribut.</span><span class="sxs-lookup"><span data-stu-id="ea273-146">Click Add Attribute.</span></span>
39. <span data-ttu-id="ea273-147">Tapez « Devise » dans le champ Nom.</span><span class="sxs-lookup"><span data-stu-id="ea273-147">In the Name field, type 'Currency'.</span></span>
40. <span data-ttu-id="ea273-148">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="ea273-148">Click OK.</span></span>
41. <span data-ttu-id="ea273-149">Cliquez sur Ajouter un attribut.</span><span class="sxs-lookup"><span data-stu-id="ea273-149">Click Add Attribute.</span></span>
42. <span data-ttu-id="ea273-150">Dans le champ Nom, tapez « Dt ».</span><span class="sxs-lookup"><span data-stu-id="ea273-150">In the Name field, type 'Dt'.</span></span>
43. <span data-ttu-id="ea273-151">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="ea273-151">Click OK.</span></span>
44. <span data-ttu-id="ea273-152">Cliquez sur Ajouter un attribut.</span><span class="sxs-lookup"><span data-stu-id="ea273-152">Click Add Attribute.</span></span>
45. <span data-ttu-id="ea273-153">Dans le champ Nom, tapez « Ct ».</span><span class="sxs-lookup"><span data-stu-id="ea273-153">In the Name field, type 'Ct'.</span></span>
46. <span data-ttu-id="ea273-154">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="ea273-154">Click OK.</span></span>
47. <span data-ttu-id="ea273-155">Cliquez sur Ajouter pour ouvrir la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="ea273-155">Click Add to open the drop dialog.</span></span>
48. <span data-ttu-id="ea273-156">Dans l'arborescence , sélectionnez « XML\Élément ».</span><span class="sxs-lookup"><span data-stu-id="ea273-156">In the tree, select 'XML\Element'.</span></span>
49. <span data-ttu-id="ea273-157">Dans le champ Nom, tapez « Dimensions ».</span><span class="sxs-lookup"><span data-stu-id="ea273-157">In the Name field, type 'Dimensions'.</span></span>
50. <span data-ttu-id="ea273-158">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="ea273-158">Click OK.</span></span>
51. <span data-ttu-id="ea273-159">Dans l'arborescence, sélectionnez « Racine : Élément XML\Journal : Élément XML\Transaction : Élément XML\Dimensions : Élément XML ».</span><span class="sxs-lookup"><span data-stu-id="ea273-159">In the tree, select 'Root: XML Element\Journal: XML Element\Transaction: XML Element\Dimensions: XML Element'.</span></span>
52. <span data-ttu-id="ea273-160">Cliquez sur Ajouter pour ouvrir la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="ea273-160">Click Add to open the drop dialog.</span></span>
53. <span data-ttu-id="ea273-161">Dans l'arborescence, sélectionnez « XML\Attribut ».</span><span class="sxs-lookup"><span data-stu-id="ea273-161">In the tree, select 'XML\Attribute'.</span></span>
54. <span data-ttu-id="ea273-162">Dans le champ Nom, tapez « Code ».</span><span class="sxs-lookup"><span data-stu-id="ea273-162">In the Name field, type 'Code'.</span></span>
55. <span data-ttu-id="ea273-163">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="ea273-163">Click OK.</span></span>
56. <span data-ttu-id="ea273-164">Cliquez sur Ajouter un attribut.</span><span class="sxs-lookup"><span data-stu-id="ea273-164">Click Add Attribute.</span></span>
57. <span data-ttu-id="ea273-165">Dans le champ Nom, tapez « Valeur ».</span><span class="sxs-lookup"><span data-stu-id="ea273-165">In the Name field, type 'Value'.</span></span>
58. <span data-ttu-id="ea273-166">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="ea273-166">Click OK.</span></span>
59. <span data-ttu-id="ea273-167">Cliquez sur Ajouter un attribut.</span><span class="sxs-lookup"><span data-stu-id="ea273-167">Click Add Attribute.</span></span>
60. <span data-ttu-id="ea273-168">Dans le champ Nom, tapez « Desc ».</span><span class="sxs-lookup"><span data-stu-id="ea273-168">In the Name field, type 'Desc'.</span></span>
61. <span data-ttu-id="ea273-169">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="ea273-169">Click OK.</span></span>

## <a name="map-report-elements-to-data-sources"></a><span data-ttu-id="ea273-170">Mettre en correspondance les éléments d'état avec les sources de données</span><span class="sxs-lookup"><span data-stu-id="ea273-170">Map report elements to data sources</span></span>
1. <span data-ttu-id="ea273-171">Cliquez sur l'onglet Mise en relation.</span><span class="sxs-lookup"><span data-stu-id="ea273-171">Click the Mapping tab.</span></span>
2. <span data-ttu-id="ea273-172">Dans l'arborescence, développez « Modèle : Exemple de modèle de dimensions financières pour le modèle de données ».</span><span class="sxs-lookup"><span data-stu-id="ea273-172">In the tree, expand 'model: Data model Financial dimensions sample model'.</span></span>
3. <span data-ttu-id="ea273-173">Dans l'arborescence, développez « Modèle : Exemple de modèle de dimensions financières pour le modèle de données\Journal : Liste d'enregistrements ».</span><span class="sxs-lookup"><span data-stu-id="ea273-173">In the tree, expand 'model: Data model Financial dimensions sample model\Journal: Record list'.</span></span>
4. <span data-ttu-id="ea273-174">Dans l'arborescence, développez « Modèle : Exemple de modèle de dimensions financières pour le modèle de données\Journal : Liste d'enregistrements\Transaction : Liste d'enregistrements ».</span><span class="sxs-lookup"><span data-stu-id="ea273-174">In the tree, expand 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list'.</span></span>
5. <span data-ttu-id="ea273-175">Dans l'arborescence, développez « Modèle : Exemple de modèle de dimensions financières pour le modèle de données\Journal : Liste d'enregistrements\Transaction : Liste d'enregistrements\Données de dimensions : Liste d'enregistrements ».</span><span class="sxs-lookup"><span data-stu-id="ea273-175">In the tree, expand 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Dimensions data: Record list'.</span></span>
6. <span data-ttu-id="ea273-176">Dans l'arborescence, sélectionnez « Racine : Élément XML\Journal : Élément XML\Transaction : Élément XML\Dimensions : Élément XML\Desc : Attribut XML ».</span><span class="sxs-lookup"><span data-stu-id="ea273-176">In the tree, select 'Root: XML Element\Journal: XML Element\Transaction: XML Element\Dimensions: XML Element\Desc: XML Attribute'.</span></span>
7. <span data-ttu-id="ea273-177">Dans l'arborescence, sélectionnez « Modèle : Exemple de modèle de dimensions financières pour le modèle de données\Journal : Liste d'enregistrements\Transaction : Liste d'enregistrements\Données de dimensions : Liste d'enregistrements\Description : Chaîne ».</span><span class="sxs-lookup"><span data-stu-id="ea273-177">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Dimensions data: Record list\Description: String'.</span></span>
8. <span data-ttu-id="ea273-178">Cliquez sur Lier.</span><span class="sxs-lookup"><span data-stu-id="ea273-178">Click Bind.</span></span>
9. <span data-ttu-id="ea273-179">Dans l'arborescence, sélectionnez « Racine : Élément XML\Journal : Élément XML\Transaction : Élément XML\Dimensions : Élément XML\Valeur : Attribut XML ».</span><span class="sxs-lookup"><span data-stu-id="ea273-179">In the tree, select 'Root: XML Element\Journal: XML Element\Transaction: XML Element\Dimensions: XML Element\Value: XML Attribute'.</span></span>
10. <span data-ttu-id="ea273-180">Dans l'arborescence, sélectionnez « Modèle : Exemple de modèle de dimensions financières pour le modèle de données\Journal : Liste d'enregistrements\Transaction : Liste d'enregistrements\Données de dimensions : Liste d'enregistrements\Code : Chaîne ».</span><span class="sxs-lookup"><span data-stu-id="ea273-180">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Dimensions data: Record list\Code: String'.</span></span>
11. <span data-ttu-id="ea273-181">Cliquez sur Lier.</span><span class="sxs-lookup"><span data-stu-id="ea273-181">Click Bind.</span></span>
12. <span data-ttu-id="ea273-182">Dans l'arborescence, sélectionnez « Racine : Élément XML\Journal : Élément XML\Transaction : Élément XML\Dimensions : Élément XML\Code : Attribut XML ».</span><span class="sxs-lookup"><span data-stu-id="ea273-182">In the tree, select 'Root: XML Element\Journal: XML Element\Transaction: XML Element\Dimensions: XML Element\Code: XML Attribute'.</span></span>
13. <span data-ttu-id="ea273-183">Dans l'arborescence, sélectionnez « Modèle : Exemple de modèle de dimensions financières pour le modèle de données\Journal : Liste d'enregistrements\Transaction : Liste d'enregistrements\Données de dimensions : Liste d'enregistrements\Nom : Chaîne ».</span><span class="sxs-lookup"><span data-stu-id="ea273-183">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Dimensions data: Record list\Name: String'.</span></span>
14. <span data-ttu-id="ea273-184">Cliquez sur Lier.</span><span class="sxs-lookup"><span data-stu-id="ea273-184">Click Bind.</span></span>
15. <span data-ttu-id="ea273-185">Dans l'arborescence, sélectionnez « Modèle : Exemple de modèle de dimensions financières pour le modèle de données\Journal : Liste d'enregistrements\Transaction : Liste d'enregistrements\Données de dimensions : Liste d'enregistrements ».</span><span class="sxs-lookup"><span data-stu-id="ea273-185">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Dimensions data: Record list'.</span></span>
16. <span data-ttu-id="ea273-186">Dans l'arborescence, sélectionnez « Racine : Élément XML\Journal : Élément XML\Transaction : Élément XML\Dimensions : Élément XML ».</span><span class="sxs-lookup"><span data-stu-id="ea273-186">In the tree, select 'Root: XML Element\Journal: XML Element\Transaction: XML Element\Dimensions: XML Element'.</span></span>
17. <span data-ttu-id="ea273-187">Cliquez sur Lier.</span><span class="sxs-lookup"><span data-stu-id="ea273-187">Click Bind.</span></span>
18. <span data-ttu-id="ea273-188">Dans l'arborescence, sélectionnez « Racine : Élément XML\Journal : Élément XML\Transaction : Élément XML\Ct : Attribut XML ».</span><span class="sxs-lookup"><span data-stu-id="ea273-188">In the tree, select 'Root: XML Element\Journal: XML Element\Transaction: XML Element\Ct: XML Attribute'.</span></span>
19. <span data-ttu-id="ea273-189">Dans l'arborescence, sélectionnez « Modèle : Exemple de modèle de dimensions financières pour le modèle de données\Journal : Liste d'enregistrements\Transaction : Liste d'enregistrements\Crédit : Réel ».</span><span class="sxs-lookup"><span data-stu-id="ea273-189">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Credit: Real'.</span></span>
20. <span data-ttu-id="ea273-190">Cliquez sur Lier.</span><span class="sxs-lookup"><span data-stu-id="ea273-190">Click Bind.</span></span>
21. <span data-ttu-id="ea273-191">Dans l'arborescence, sélectionnez « Racine : Élément XML\Journal : Élément XML\Transaction : Élément XML\Dt : Attribut XML ».</span><span class="sxs-lookup"><span data-stu-id="ea273-191">In the tree, select 'Root: XML Element\Journal: XML Element\Transaction: XML Element\Dt: XML Attribute'.</span></span>
22. <span data-ttu-id="ea273-192">Dans l'arborescence, sélectionnez « Modèle : Exemple de modèle de dimensions financières pour le modèle de données\Journal : Liste d'enregistrements\Transaction : Liste d'enregistrements\Débit : Réel ».</span><span class="sxs-lookup"><span data-stu-id="ea273-192">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Debit: Real'.</span></span>
23. <span data-ttu-id="ea273-193">Cliquez sur Lier.</span><span class="sxs-lookup"><span data-stu-id="ea273-193">Click Bind.</span></span>
24. <span data-ttu-id="ea273-194">Dans l'arborescence, sélectionnez « Racine : Élément XML\Journal : Élément XML\Transaction : Élément XML\Devise : Attribut XML ».</span><span class="sxs-lookup"><span data-stu-id="ea273-194">In the tree, select 'Root: XML Element\Journal: XML Element\Transaction: XML Element\Currency: XML Attribute'.</span></span>
25. <span data-ttu-id="ea273-195">Dans l'arborescence, sélectionnez « Modèle : Exemple de modèle de dimensions financières pour le modèle de données\Journal : Liste d'enregistrements\Transaction : Liste d'enregistrements\Devise : Chaîne ».</span><span class="sxs-lookup"><span data-stu-id="ea273-195">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Currency: String'.</span></span>
26. <span data-ttu-id="ea273-196">Cliquez sur Lier.</span><span class="sxs-lookup"><span data-stu-id="ea273-196">Click Bind.</span></span>
27. <span data-ttu-id="ea273-197">Dans l'arborescence, sélectionnez « Racine : Élément XML\Journal : Élément XML\Transaction : Élément XML\Date : Attribut XML ».</span><span class="sxs-lookup"><span data-stu-id="ea273-197">In the tree, select 'Root: XML Element\Journal: XML Element\Transaction: XML Element\Date: XML Attribute'.</span></span>
28. <span data-ttu-id="ea273-198">Dans l'arborescence, sélectionnez « Modèle : Exemple de modèle de dimensions financières pour le modèle de données\Journal : Liste d'enregistrements\Transaction : Liste d'enregistrements\Date : Date ».</span><span class="sxs-lookup"><span data-stu-id="ea273-198">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Date: Date'.</span></span>
29. <span data-ttu-id="ea273-199">Cliquez sur Lier.</span><span class="sxs-lookup"><span data-stu-id="ea273-199">Click Bind.</span></span>
30. <span data-ttu-id="ea273-200">Dans l'arborescence, sélectionnez « Racine : Élément XML\Journal : Élément XML\Transaction : Élément XML\N° document : Attribut XML ».</span><span class="sxs-lookup"><span data-stu-id="ea273-200">In the tree, select 'Root: XML Element\Journal: XML Element\Transaction: XML Element\Voucher: XML Attribute'.</span></span>
31. <span data-ttu-id="ea273-201">Dans l'arborescence, sélectionnez « Modèle : Exemple de modèle de dimensions financières pour le modèle de données\Journal : Liste d'enregistrements\Transaction : Liste d'enregistrements\N° document : Chaîne ».</span><span class="sxs-lookup"><span data-stu-id="ea273-201">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Voucher: String'.</span></span>
32. <span data-ttu-id="ea273-202">Cliquez sur Lier.</span><span class="sxs-lookup"><span data-stu-id="ea273-202">Click Bind.</span></span>
33. <span data-ttu-id="ea273-203">Dans l'arborescence, sélectionnez « Racine : Élément XML\Journal : Élément XML\Transaction : Élément XML ».</span><span class="sxs-lookup"><span data-stu-id="ea273-203">In the tree, select 'Root: XML Element\Journal: XML Element\Transaction: XML Element'.</span></span>
34. <span data-ttu-id="ea273-204">Dans l'arborescence, sélectionnez « Modèle : Exemple de modèle de dimensions financières pour le modèle de données\Journal : Liste d'enregistrements\Transaction : Liste d'enregistrements ».</span><span class="sxs-lookup"><span data-stu-id="ea273-204">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list'.</span></span>
35. <span data-ttu-id="ea273-205">Cliquez sur Lier.</span><span class="sxs-lookup"><span data-stu-id="ea273-205">Click Bind.</span></span>
36. <span data-ttu-id="ea273-206">Dans l'arborescence, sélectionnez « Racine : Élément XML\Journal : Élément XML\Lot : Attribut XML ».</span><span class="sxs-lookup"><span data-stu-id="ea273-206">In the tree, select 'Root: XML Element\Journal: XML Element\Batch: XML Attribute'.</span></span>
37. <span data-ttu-id="ea273-207">Dans l'arborescence, sélectionnez « Modèle : Exemple de modèle de dimensions financières pour le modèle de données\Journal : Liste d'enregistrements\Lot : Chaîne ».</span><span class="sxs-lookup"><span data-stu-id="ea273-207">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list\Batch: String'.</span></span>
38. <span data-ttu-id="ea273-208">Cliquez sur Lier.</span><span class="sxs-lookup"><span data-stu-id="ea273-208">Click Bind.</span></span>
39. <span data-ttu-id="ea273-209">Dans l'arborescence, sélectionnez « Racine : Élément XML\Journal : Élément XML ».</span><span class="sxs-lookup"><span data-stu-id="ea273-209">In the tree, select 'Root: XML Element\Journal: XML Element'.</span></span>
40. <span data-ttu-id="ea273-210">Dans l'arborescence, sélectionnez « Modèle : Exemple de modèle de dimensions financières pour le modèle de données\Journal : Liste d'enregistrements ».</span><span class="sxs-lookup"><span data-stu-id="ea273-210">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list'.</span></span>
41. <span data-ttu-id="ea273-211">Cliquez sur Lier.</span><span class="sxs-lookup"><span data-stu-id="ea273-211">Click Bind.</span></span>
42. <span data-ttu-id="ea273-212">Dans l'arborescence, sélectionnez « Racine : Élément XML\Société : Attribut XML ».</span><span class="sxs-lookup"><span data-stu-id="ea273-212">In the tree, select 'Root: XML Element\Company: XML Attribute'.</span></span>
43. <span data-ttu-id="ea273-213">Dans l'arborescence, sélectionnez « Modèle : Exemple de modèle de dimensions financières pour le modèle de données\Société : Chaîne ».</span><span class="sxs-lookup"><span data-stu-id="ea273-213">In the tree, select 'model: Data model Financial dimensions sample model\Company: String'.</span></span>
44. <span data-ttu-id="ea273-214">Cliquez sur Lier.</span><span class="sxs-lookup"><span data-stu-id="ea273-214">Click Bind.</span></span>
45. <span data-ttu-id="ea273-215">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="ea273-215">Click Save.</span></span>
46. <span data-ttu-id="ea273-216">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="ea273-216">Close the page.</span></span>


