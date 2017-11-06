--- 
title: "Utiliser les calculs pour générer la sortie pour effectuer le comptage et la synthèse pour la gestion des états électroniques (ER)"
description: "Les étapes suivantes expliquent comment un utilisateur affecté au rôle d'administrateur système ou de développeur d'états électroniques peut configurer un format de génération d'états électroniques (ER) pour effectuer le comptage et la synthèse en fonction des données de la sortie de texte déjà générée."
author: NickSelin
manager: AnnBe
ms.date: 10/28/2016
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
ms.openlocfilehash: 143856f65eaf1d6d667f4f7dfb229807da6f4ad8
ms.contentlocale: fr-fr
ms.lasthandoff: 11/06/2017

---
# <a name="use-computations-to-make-the-output-for-counting-and-summing-for-electronic-reporting-er"></a><span data-ttu-id="bc714-103">Utiliser les calculs pour générer la sortie pour effectuer le comptage et la synthèse pour la gestion des états électroniques (ER)</span><span class="sxs-lookup"><span data-stu-id="bc714-103">Use computations to make the output for counting and summing for electronic reporting (ER)</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="bc714-104">Les étapes suivantes expliquent comment un utilisateur affecté au rôle d'administrateur système ou de développeur d'états électroniques peut configurer un format de génération d'états électroniques (ER) pour effectuer le comptage et la synthèse en fonction des données de la sortie de texte déjà générée.</span><span class="sxs-lookup"><span data-stu-id="bc714-104">The following steps explain how a user assigned to the system administrator or electronic reporting developer role can configure an Electronic reporting (ER) format to do counting and summing based on data of the already generated text output.</span></span> <span data-ttu-id="bc714-105">Ces étapes peuvent être effectuées dans n'importe quelle société.</span><span class="sxs-lookup"><span data-stu-id="bc714-105">These steps can be performed in any company.</span></span>

<span data-ttu-id="bc714-106">Pour effectuer ces étapes, vous devez d'abord effectuer les étapes de la procédure « ER Configurer le format pour effectuer le comptage et la synthèse (Partie 2 : Configurer des calculs) ».</span><span class="sxs-lookup"><span data-stu-id="bc714-106">To complete these steps, you must first complete the steps in the “ER Configure format to do counting and summing (Part 2: Configure computations)” procedure.</span></span>

<span data-ttu-id="bc714-107">Cette procédure s'applique à une fonction qui a été ajoutée dans la version 1611 de Dynamics 365 for Operations.</span><span class="sxs-lookup"><span data-stu-id="bc714-107">This procedure is for a feature that was added in Dynamics 365 for Operations version 1611.</span></span>


## <a name="configure-this-report-to-use-counting-and-summing-info"></a><span data-ttu-id="bc714-108">Configurer cet état pour utiliser les informations de comptage et de synthèse</span><span class="sxs-lookup"><span data-stu-id="bc714-108">Configure this report to use counting and summing info</span></span>
1. <span data-ttu-id="bc714-109">Accédez à Administration d'organisation > Espaces de travail > États électroniques.</span><span class="sxs-lookup"><span data-stu-id="bc714-109">Go to Organization administration > Workspaces > Electronic reporting.</span></span>
2. <span data-ttu-id="bc714-110">Cliquez sur Configurations des états.</span><span class="sxs-lookup"><span data-stu-id="bc714-110">Click Reporting configurations.</span></span>
3. <span data-ttu-id="bc714-111">Dans l'arborescence, développez « Modèle de déclaration d'échanges de biens ».</span><span class="sxs-lookup"><span data-stu-id="bc714-111">In the tree, expand 'Intrastat model'.</span></span>
4. <span data-ttu-id="bc714-112">Dans l'arborescence, développez « Modèle de déclaration d'échanges de biens\Déclaration d'échanges de biens (Allemagne) ».</span><span class="sxs-lookup"><span data-stu-id="bc714-112">In the tree, expand 'Intrastat model\Intrastat (DE)'.</span></span>
5. <span data-ttu-id="bc714-113">Dans l'arborescence, sélectionnez « Modèle de déclaration d'échanges de biens\Déclaration d'échanges de biens (Allemagne)\Déclaration d'échanges de biens (Allemagne) avec comptage et synthèse ».</span><span class="sxs-lookup"><span data-stu-id="bc714-113">In the tree, select 'Intrastat model\Intrastat (DE)\Intrastat (DE) with counting & summing'.</span></span>
6. <span data-ttu-id="bc714-114">Cliquez sur Concepteur.</span><span class="sxs-lookup"><span data-stu-id="bc714-114">Click Designer.</span></span>
7. <span data-ttu-id="bc714-115">Cliquez sur l'onglet Mise en relation.</span><span class="sxs-lookup"><span data-stu-id="bc714-115">Click the Mapping tab.</span></span>
8. <span data-ttu-id="bc714-116">Cliquez sur Ajouter racine pour ouvrir la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="bc714-116">Click Add root to open the drop dialog.</span></span>
    * <span data-ttu-id="bc714-117">Ajoutez une nouvelle source de données pour obtenir la liste des blocs mémorisés.</span><span class="sxs-lookup"><span data-stu-id="bc714-117">Add a new data source to get the list of memorized blocks.</span></span>  
9. <span data-ttu-id="bc714-118">Dans l'arborescence, sélectionnez « Fonctions\Champ calculé ».</span><span class="sxs-lookup"><span data-stu-id="bc714-118">In the tree, select 'Functions\Calculated field'.</span></span>
10. <span data-ttu-id="bc714-119">Dans le champ Nom, tapez « $BlocksList ».</span><span class="sxs-lookup"><span data-stu-id="bc714-119">In the Name field, type '$BlocksList'.</span></span>
    * <span data-ttu-id="bc714-120">$BlocksList</span><span class="sxs-lookup"><span data-stu-id="bc714-120">$BlocksList</span></span>  
11. <span data-ttu-id="bc714-121">Cliquez sur Modifier la formule.</span><span class="sxs-lookup"><span data-stu-id="bc714-121">Click Edit formula.</span></span>
12. <span data-ttu-id="bc714-122">Dans l'arborescence, sélectionnez « Fonctions de collecte des données\COLLECTEDLIST ».</span><span class="sxs-lookup"><span data-stu-id="bc714-122">In the tree, select 'Data collection functions\COLLECTEDLIST'.</span></span>
13. <span data-ttu-id="bc714-123">Cliquez sur Ajouter une fonction.</span><span class="sxs-lookup"><span data-stu-id="bc714-123">Click Add function.</span></span>
14. <span data-ttu-id="bc714-124">Cliquez sur Ajouter une source de données.</span><span class="sxs-lookup"><span data-stu-id="bc714-124">Click Add data source.</span></span>
15. <span data-ttu-id="bc714-125">Dans le champ Formule, entrez 'COLLECTEDLIST('$BlockName', '.</span><span class="sxs-lookup"><span data-stu-id="bc714-125">In the Formula field, enter 'COLLECTEDLIST('$BlockName', '.</span></span>
    * <span data-ttu-id="bc714-126">COLLECTEDLIST('$BlockName',</span><span class="sxs-lookup"><span data-stu-id="bc714-126">COLLECTEDLIST('$BlockName',</span></span>  
16. <span data-ttu-id="bc714-127">Dans le champ Formule, entrez 'COLLECTEDLIST('$BlockName', "*")'.</span><span class="sxs-lookup"><span data-stu-id="bc714-127">In the Formula field, enter 'COLLECTEDLIST('$BlockName', "*")'.</span></span>
    * <span data-ttu-id="bc714-128">COLLECTEDLIST('$BlockName', "*")</span><span class="sxs-lookup"><span data-stu-id="bc714-128">COLLECTEDLIST('$BlockName', "*")</span></span>  
17. <span data-ttu-id="bc714-129">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="bc714-129">Click Save.</span></span>
    * <span data-ttu-id="bc714-130">Le modèle « * » signifie que tous les blocs sont inclus dans la liste pour cet enregistrement.</span><span class="sxs-lookup"><span data-stu-id="bc714-130">The pattern “*” means that all blocks will be included to the list for this record.</span></span>  
18. <span data-ttu-id="bc714-131">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="bc714-131">Close the page.</span></span>
19. <span data-ttu-id="bc714-132">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="bc714-132">Click OK.</span></span>
20. <span data-ttu-id="bc714-133">Cliquez sur l'onglet Format.</span><span class="sxs-lookup"><span data-stu-id="bc714-133">Click the Format tab.</span></span>
21. <span data-ttu-id="bc714-134">Dans l'arborescence, sélectionnez « Déclaration d'échanges de biens\Données ».</span><span class="sxs-lookup"><span data-stu-id="bc714-134">In the tree, select 'Intrastat\Data'.</span></span>
22. <span data-ttu-id="bc714-135">Cliquez sur Ajouter pour ouvrir la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="bc714-135">Click Add to open the drop dialog.</span></span>
23. <span data-ttu-id="bc714-136">Dans l'arborescence, sélectionnez « Texte\Souche ».</span><span class="sxs-lookup"><span data-stu-id="bc714-136">In the tree, select 'Text\Sequence'.</span></span>
24. <span data-ttu-id="bc714-137">Dans le champ Nom, tapez « Totaux par bloc ».</span><span class="sxs-lookup"><span data-stu-id="bc714-137">In the Name field, type 'Totals by blocks'.</span></span>
    * <span data-ttu-id="bc714-138">Totaux par bloc</span><span class="sxs-lookup"><span data-stu-id="bc714-138">Totals by blocks</span></span>  
25. <span data-ttu-id="bc714-139">Dans le champ Caractères spéciaux, sélectionnez « Nouvelle ligne - Windows (CR LF) ».</span><span class="sxs-lookup"><span data-stu-id="bc714-139">In the Special characters field, select 'New line - Windows (CR LF)'.</span></span>
26. <span data-ttu-id="bc714-140">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="bc714-140">Click OK.</span></span>
27. <span data-ttu-id="bc714-141">Dans l'arborescence, sélectionnez « Déclaration d'échanges de biens\Données\Totaux par bloc ».</span><span class="sxs-lookup"><span data-stu-id="bc714-141">In the tree, select 'Intrastat\Data\Totals by blocks'.</span></span>
28. <span data-ttu-id="bc714-142">Cliquez sur Ajouter pour ouvrir la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="bc714-142">Click Add to open the drop dialog.</span></span>
29. <span data-ttu-id="bc714-143">Dans l'arborescence, sélectionnez « Texte\Chaîne ».</span><span class="sxs-lookup"><span data-stu-id="bc714-143">In the tree, select 'Text\String'.</span></span>
30. <span data-ttu-id="bc714-144">Dans le champ Nom, tapez « Code du bloc ».</span><span class="sxs-lookup"><span data-stu-id="bc714-144">In the Name field, type 'Block code'.</span></span>
    * <span data-ttu-id="bc714-145">Code du bloc</span><span class="sxs-lookup"><span data-stu-id="bc714-145">Block code</span></span>  
31. <span data-ttu-id="bc714-146">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="bc714-146">Click OK.</span></span>
32. <span data-ttu-id="bc714-147">Cliquez sur Ajouter une chaîne.</span><span class="sxs-lookup"><span data-stu-id="bc714-147">Click Add String.</span></span>
33. <span data-ttu-id="bc714-148">Dans le champ Nom, tapez « Comptage des lignes ».</span><span class="sxs-lookup"><span data-stu-id="bc714-148">In the Name field, type 'Lines counting'.</span></span>
    * <span data-ttu-id="bc714-149">Comptage des lignes</span><span class="sxs-lookup"><span data-stu-id="bc714-149">Lines counting</span></span>  
34. <span data-ttu-id="bc714-150">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="bc714-150">Click OK.</span></span>
35. <span data-ttu-id="bc714-151">Cliquez sur Ajouter une chaîne.</span><span class="sxs-lookup"><span data-stu-id="bc714-151">Click Add String.</span></span>
36. <span data-ttu-id="bc714-152">Dans le champ Nom, tapez « Montant total ».</span><span class="sxs-lookup"><span data-stu-id="bc714-152">In the Name field, type 'Total amount'.</span></span>
    * <span data-ttu-id="bc714-153">Montant total</span><span class="sxs-lookup"><span data-stu-id="bc714-153">Total amount</span></span>  
37. <span data-ttu-id="bc714-154">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="bc714-154">Click OK.</span></span>
38. <span data-ttu-id="bc714-155">Cliquez sur l'onglet Mise en relation.</span><span class="sxs-lookup"><span data-stu-id="bc714-155">Click the Mapping tab.</span></span>
39. <span data-ttu-id="bc714-156">Dans l'arborescence, sélectionnez « $BlocksList ».</span><span class="sxs-lookup"><span data-stu-id="bc714-156">In the tree, select '$BlocksList'.</span></span>
40. <span data-ttu-id="bc714-157">Cliquez sur Lier.</span><span class="sxs-lookup"><span data-stu-id="bc714-157">Click Bind.</span></span>
    * <span data-ttu-id="bc714-158">Créez une ligne de synthèse pour chaque bloc mémorisé.</span><span class="sxs-lookup"><span data-stu-id="bc714-158">Create a summary line for each memorized block.</span></span>  
41. <span data-ttu-id="bc714-159">Cliquez sur l'onglet Format.</span><span class="sxs-lookup"><span data-stu-id="bc714-159">Click the Format tab.</span></span>
42. <span data-ttu-id="bc714-160">Dans l'arborescence, sélectionnez « Déclaration d'échanges de biens\Données\Totaux par bloc\Code du bloc ».</span><span class="sxs-lookup"><span data-stu-id="bc714-160">In the tree, select 'Intrastat\Data\Totals by blocks\Block code'.</span></span>
43. <span data-ttu-id="bc714-161">Cliquez sur l'onglet Mise en relation.</span><span class="sxs-lookup"><span data-stu-id="bc714-161">Click the Mapping tab.</span></span>
44. <span data-ttu-id="bc714-162">Cliquez sur Modifier la formule.</span><span class="sxs-lookup"><span data-stu-id="bc714-162">Click Edit formula.</span></span>
45. <span data-ttu-id="bc714-163">Dans le champ Formule, entrez '"ID bloc : " & '.</span><span class="sxs-lookup"><span data-stu-id="bc714-163">In the Formula field, enter '"Block id: " & '.</span></span>
    * <span data-ttu-id="bc714-164">"ID bloc : " &</span><span class="sxs-lookup"><span data-stu-id="bc714-164">"Block id: " &</span></span>  
46. <span data-ttu-id="bc714-165">Dans l'arborescence, développez « $BlocksList ».</span><span class="sxs-lookup"><span data-stu-id="bc714-165">In the tree, expand '$BlocksList'.</span></span>
47. <span data-ttu-id="bc714-166">Dans l'arborescence, sélectionnez « $BlocksList\Valeur ».</span><span class="sxs-lookup"><span data-stu-id="bc714-166">In the tree, select '$BlocksList\Value'.</span></span>
48. <span data-ttu-id="bc714-167">Cliquez sur Ajouter une source de données.</span><span class="sxs-lookup"><span data-stu-id="bc714-167">Click Add data source.</span></span>
49. <span data-ttu-id="bc714-168">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="bc714-168">Click Save.</span></span>
50. <span data-ttu-id="bc714-169">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="bc714-169">Close the page.</span></span>
51. <span data-ttu-id="bc714-170">Cliquez sur l'onglet Format.</span><span class="sxs-lookup"><span data-stu-id="bc714-170">Click the Format tab.</span></span>
52. <span data-ttu-id="bc714-171">Dans l'arborescence, sélectionnez « Déclaration d'échanges de biens\Données\Totaux par bloc\Comptage des lignes ».</span><span class="sxs-lookup"><span data-stu-id="bc714-171">In the tree, select 'Intrastat\Data\Totals by blocks\Lines counting'.</span></span>
53. <span data-ttu-id="bc714-172">Cliquez sur l'onglet Mise en relation.</span><span class="sxs-lookup"><span data-stu-id="bc714-172">Click the Mapping tab.</span></span>
54. <span data-ttu-id="bc714-173">Cliquez sur Modifier la formule.</span><span class="sxs-lookup"><span data-stu-id="bc714-173">Click Edit formula.</span></span>
    * <span data-ttu-id="bc714-174">Créez une sortie pour le nombre de lignes pour chaque bloc présenté dans cet état.</span><span class="sxs-lookup"><span data-stu-id="bc714-174">Create output for the number of lines for each block presented in this report.</span></span>  
55. <span data-ttu-id="bc714-175">Dans le champ Formule, entrez '"Nombre de lignes dans ce bloc : " & '.</span><span class="sxs-lookup"><span data-stu-id="bc714-175">In the Formula field, enter '"Number of lines in this block: " & '.</span></span>
    * <span data-ttu-id="bc714-176">"Nombre de lignes dans ce bloc : " &</span><span class="sxs-lookup"><span data-stu-id="bc714-176">"Number of lines in this block: " &</span></span>  
56. <span data-ttu-id="bc714-177">Dans le champ Formule, entrez '"Nombre de lignes dans ce bloc : " & TEXT('.</span><span class="sxs-lookup"><span data-stu-id="bc714-177">In the Formula field, enter '"Number of lines in this block: " & TEXT('.</span></span>
    * <span data-ttu-id="bc714-178">"Nombre de lignes dans ce bloc : " & TEXT(</span><span class="sxs-lookup"><span data-stu-id="bc714-178">"Number of lines in this block: " & TEXT(</span></span>  
57. <span data-ttu-id="bc714-179">Dans l'arborescence, sélectionnez « Fonctions de collecte des données\COUNTIFS ».</span><span class="sxs-lookup"><span data-stu-id="bc714-179">In the tree, select 'Data collection functions\COUNTIFS'.</span></span>
58. <span data-ttu-id="bc714-180">Cliquez sur Ajouter une fonction.</span><span class="sxs-lookup"><span data-stu-id="bc714-180">Click Add function.</span></span>
59. <span data-ttu-id="bc714-181">Cliquez sur Ajouter une source de données.</span><span class="sxs-lookup"><span data-stu-id="bc714-181">Click Add data source.</span></span>
60. <span data-ttu-id="bc714-182">Dans le champ Formule, entrez '"Nombre de lignes dans ce bloc: " & TEXT(COUNTIFS('$BlockName', '.</span><span class="sxs-lookup"><span data-stu-id="bc714-182">In the Formula field, enter '"Number of lines in this block: " & TEXT(COUNTIFS('$BlockName', '.</span></span>
    * <span data-ttu-id="bc714-183">"Nombre de lignes dans ce bloc: " & TEXT(COUNTIFS('$BlockName',</span><span class="sxs-lookup"><span data-stu-id="bc714-183">"Number of lines in this block: " & TEXT(COUNTIFS('$BlockName',</span></span>  
61. <span data-ttu-id="bc714-184">Dans l'arborescence, développez « $BlocksList ».</span><span class="sxs-lookup"><span data-stu-id="bc714-184">In the tree, expand '$BlocksList'.</span></span>
62. <span data-ttu-id="bc714-185">Dans l'arborescence, sélectionnez « $BlocksList\Valeur ».</span><span class="sxs-lookup"><span data-stu-id="bc714-185">In the tree, select '$BlocksList\Value'.</span></span>
63. <span data-ttu-id="bc714-186">Cliquez sur Ajouter une source de données.</span><span class="sxs-lookup"><span data-stu-id="bc714-186">Click Add data source.</span></span>
64. <span data-ttu-id="bc714-187">Dans le champ Formule, entrez '"Nombre de lignes dans ce bloc: " & TEXT(COUNTIFS('$BlockName', '$BlocksList'.Value, '.</span><span class="sxs-lookup"><span data-stu-id="bc714-187">In the Formula field, enter '"Number of lines in this block: " & TEXT(COUNTIFS('$BlockName', '$BlocksList'.Value, '.</span></span>
    * <span data-ttu-id="bc714-188">"Nombre de lignes dans ce bloc: " & TEXT(COUNTIFS('$BlockName', '$BlocksList'.Value,</span><span class="sxs-lookup"><span data-stu-id="bc714-188">"Number of lines in this block: " & TEXT(COUNTIFS('$BlockName', '$BlocksList'.Value,</span></span>  
65. <span data-ttu-id="bc714-189">Dans l'arborescence, sélectionnez « RecName ».</span><span class="sxs-lookup"><span data-stu-id="bc714-189">In the tree, select '$RecName'.</span></span>
66. <span data-ttu-id="bc714-190">Cliquez sur Ajouter une source de données.</span><span class="sxs-lookup"><span data-stu-id="bc714-190">Click Add data source.</span></span>
67. <span data-ttu-id="bc714-191">Dans le champ Formule, entrez '"Nombre de lignes dans ce bloc: " & TEXT(COUNTIFS('$BlockName', '$BlocksList'.Value, '$RecName', "*"))'.</span><span class="sxs-lookup"><span data-stu-id="bc714-191">In the Formula field, enter '"Number of lines in this block: " & TEXT(COUNTIFS('$BlockName', '$BlocksList'.Value, '$RecName', "*"))'.</span></span>
    * <span data-ttu-id="bc714-192">"Nombre de lignes dans ce bloc: " & TEXT(COUNTIFS('$BlockName', '$BlocksList'.Value, '$RecName', "*"))</span><span class="sxs-lookup"><span data-stu-id="bc714-192">"Number of lines in this block: " & TEXT(COUNTIFS('$BlockName', '$BlocksList'.Value, '$RecName', "*"))</span></span>  
68. <span data-ttu-id="bc714-193">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="bc714-193">Click Save.</span></span>
69. <span data-ttu-id="bc714-194">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="bc714-194">Close the page.</span></span>
70. <span data-ttu-id="bc714-195">Cliquez sur l'onglet Format.</span><span class="sxs-lookup"><span data-stu-id="bc714-195">Click the Format tab.</span></span>
71. <span data-ttu-id="bc714-196">Dans l'arborescence, sélectionnez « Déclaration d'échanges de biens\Données\Totaux par bloc\Montant total ».</span><span class="sxs-lookup"><span data-stu-id="bc714-196">In the tree, select 'Intrastat\Data\Totals by blocks\Total amount'.</span></span>
72. <span data-ttu-id="bc714-197">Cliquez sur l'onglet Mise en relation.</span><span class="sxs-lookup"><span data-stu-id="bc714-197">Click the Mapping tab.</span></span>
73. <span data-ttu-id="bc714-198">Cliquez sur Modifier la formule.</span><span class="sxs-lookup"><span data-stu-id="bc714-198">Click Edit formula.</span></span>
    * <span data-ttu-id="bc714-199">Créez une sortie qui est égale au total du montant facturé pour chaque bloc présenté dans cet état.</span><span class="sxs-lookup"><span data-stu-id="bc714-199">Create output that will be the total of the invoiced amount for each block presented in this report.</span></span>  
74. <span data-ttu-id="bc714-200">Dans le champ Formule, entrez '"Somme du montant facturé : " & TEXT(SUMIFS('$InvName', '$BlockName', '$BlocksList'.Value, '$RecName', "*"))'.</span><span class="sxs-lookup"><span data-stu-id="bc714-200">In the Formula field, enter '"Sum of invoiced amount: " & TEXT(SUMIFS('$InvName', '$BlockName', '$BlocksList'.Value, '$RecName', "*"))'.</span></span>
    * <span data-ttu-id="bc714-201">"Somme du montant facturé : " & TEXT(SUMIFS('$InvName', '$BlockName', '$BlocksList'.Value, '$RecName', "*"))</span><span class="sxs-lookup"><span data-stu-id="bc714-201">"Sum of invoiced amount: " & TEXT(SUMIFS('$InvName', '$BlockName', '$BlocksList'.Value, '$RecName', "*"))</span></span>  
75. <span data-ttu-id="bc714-202">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="bc714-202">Click Save.</span></span>
76. <span data-ttu-id="bc714-203">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="bc714-203">Close the page.</span></span>
77. <span data-ttu-id="bc714-204">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="bc714-204">Click Save.</span></span>
78. <span data-ttu-id="bc714-205">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="bc714-205">Close the page.</span></span>


