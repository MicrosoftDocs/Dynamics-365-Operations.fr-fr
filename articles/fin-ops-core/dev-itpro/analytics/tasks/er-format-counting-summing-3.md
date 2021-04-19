---
title: ER Configurer le format pour effectuer le comptage et la synthèse (Partie 3 – Utiliser les calculs pour générer la sortie)
description: Cette rubrique décrit comment configurer un format de gestion des états électroniques pour effectuer le comptage et la somme en fonction des données de la sortie de texte déjà générée. (Partie 3)
author: NickSelin
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: ERWorkspace, ERSolutionTable, EROperationDesigner, ERDataSourceAddDropDialog, ERExpressionDesignerFormula, ERComponentTypeDropDialog
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 7073539ed4c1d9d5acbb0ca84b43538d87fc8b4b
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5748995"
---
# <a name="er-configure-format-to-do-counting-and-summing-part-3---use-computations-to-make-the-output"></a><span data-ttu-id="d9277-104">ER Configurer le format pour effectuer le comptage et la synthèse (Partie 3 – Utiliser les calculs pour générer la sortie)</span><span class="sxs-lookup"><span data-stu-id="d9277-104">ER Configure format to do counting and summing (Part 3 - Use computations to make the output)</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="d9277-105">Les étapes suivantes expliquent comment un utilisateur affecté au rôle d’administrateur système ou de développeur d’états électroniques peut configurer un format de génération d’états électroniques (ER) pour effectuer le comptage et la synthèse en fonction des données de la sortie de texte déjà générée.</span><span class="sxs-lookup"><span data-stu-id="d9277-105">The following steps explain how a user assigned to the system administrator or electronic reporting developer role can configure an Electronic reporting (ER) format to do counting and summing based on data of the already generated text output.</span></span> <span data-ttu-id="d9277-106">Ces étapes peuvent être effectuées dans n’importe quelle société.</span><span class="sxs-lookup"><span data-stu-id="d9277-106">These steps can be performed in any company.</span></span>

<span data-ttu-id="d9277-107">Pour effectuer ces étapes, vous devez d’abord effectuer les étapes de la procédure « ER Configurer le format pour effectuer le comptage et la synthèse (Partie 2 : Configurer des calculs) ».</span><span class="sxs-lookup"><span data-stu-id="d9277-107">To complete these steps, you must first complete the steps in the "ER Configure format to do counting and summing (Part 2: Configure computations)" procedure.</span></span>

<span data-ttu-id="d9277-108">Cette procédure s’applique à une fonction qui a été ajoutée dans la version 1611 de Dynamics 365 for Operations.</span><span class="sxs-lookup"><span data-stu-id="d9277-108">This procedure is for a feature that was added in Dynamics 365 for Operations version 1611.</span></span>


## <a name="configure-this-report-to-use-counting-and-summing-info"></a><span data-ttu-id="d9277-109">Configurer cet état pour utiliser les informations de comptage et de synthèse</span><span class="sxs-lookup"><span data-stu-id="d9277-109">Configure this report to use counting and summing info</span></span>
1. <span data-ttu-id="d9277-110">Accédez à Administration d’organisation > Espaces de travail > États électroniques.</span><span class="sxs-lookup"><span data-stu-id="d9277-110">Go to Organization administration > Workspaces > Electronic reporting.</span></span>
2. <span data-ttu-id="d9277-111">Cliquez sur Configurations des états.</span><span class="sxs-lookup"><span data-stu-id="d9277-111">Click Reporting configurations.</span></span>
3. <span data-ttu-id="d9277-112">Dans l’arborescence, développez « Modèle de déclaration d’échanges de biens ».</span><span class="sxs-lookup"><span data-stu-id="d9277-112">In the tree, expand 'Intrastat model'.</span></span>
4. <span data-ttu-id="d9277-113">Dans l’arborescence, développez « Modèle de déclaration d’échanges de biens\Déclaration d’échanges de biens (Allemagne) ».</span><span class="sxs-lookup"><span data-stu-id="d9277-113">In the tree, expand 'Intrastat model\Intrastat (DE)'.</span></span>
5. <span data-ttu-id="d9277-114">Dans l’arborescence, sélectionnez « Modèle de déclaration d’échanges de biens\Déclaration d’échanges de biens (Allemagne)\Déclaration d’échanges de biens (Allemagne) avec comptage et synthèse ».</span><span class="sxs-lookup"><span data-stu-id="d9277-114">In the tree, select 'Intrastat model\Intrastat (DE)\Intrastat (DE) with counting & summing'.</span></span>
6. <span data-ttu-id="d9277-115">Cliquez sur Concepteur.</span><span class="sxs-lookup"><span data-stu-id="d9277-115">Click Designer.</span></span>
7. <span data-ttu-id="d9277-116">Cliquez sur l’onglet Mise en relation.</span><span class="sxs-lookup"><span data-stu-id="d9277-116">Click the Mapping tab.</span></span>
8. <span data-ttu-id="d9277-117">Cliquez sur Ajouter racine pour ouvrir la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="d9277-117">Click Add root to open the drop dialog.</span></span>
    * <span data-ttu-id="d9277-118">Ajoutez une nouvelle source de données pour obtenir la liste des blocs mémorisés.</span><span class="sxs-lookup"><span data-stu-id="d9277-118">Add a new data source to get the list of memorized blocks.</span></span>  
9. <span data-ttu-id="d9277-119">Dans l’arborescence, sélectionnez « Fonctions\Champ calculé ».</span><span class="sxs-lookup"><span data-stu-id="d9277-119">In the tree, select 'Functions\Calculated field'.</span></span>
10. <span data-ttu-id="d9277-120">Dans le champ Nom, tapez « $BlocksList ».</span><span class="sxs-lookup"><span data-stu-id="d9277-120">In the Name field, type '$BlocksList'.</span></span>
    * <span data-ttu-id="d9277-121">$BlocksList</span><span class="sxs-lookup"><span data-stu-id="d9277-121">$BlocksList</span></span>  
11. <span data-ttu-id="d9277-122">Cliquez sur Modifier la formule.</span><span class="sxs-lookup"><span data-stu-id="d9277-122">Click Edit formula.</span></span>
12. <span data-ttu-id="d9277-123">Dans l’arborescence, sélectionnez « Fonctions de collecte des données\COLLECTEDLIST ».</span><span class="sxs-lookup"><span data-stu-id="d9277-123">In the tree, select 'Data collection functions\COLLECTEDLIST'.</span></span>
13. <span data-ttu-id="d9277-124">Cliquez sur Ajouter une fonction.</span><span class="sxs-lookup"><span data-stu-id="d9277-124">Click Add function.</span></span>
14. <span data-ttu-id="d9277-125">Cliquez sur Ajouter une source de données.</span><span class="sxs-lookup"><span data-stu-id="d9277-125">Click Add data source.</span></span>
15. <span data-ttu-id="d9277-126">Dans le champ Formule, entrez ’COLLECTEDLIST(’$BlockName’, ’.</span><span class="sxs-lookup"><span data-stu-id="d9277-126">In the Formula field, enter 'COLLECTEDLIST('$BlockName', '.</span></span>
    * <span data-ttu-id="d9277-127">COLLECTEDLIST(’$BlockName’,</span><span class="sxs-lookup"><span data-stu-id="d9277-127">COLLECTEDLIST('$BlockName',</span></span>  
16. <span data-ttu-id="d9277-128">Dans le champ Formule, entrez ’COLLECTEDLIST(’$BlockName’, "\*")’.</span><span class="sxs-lookup"><span data-stu-id="d9277-128">In the Formula field, enter 'COLLECTEDLIST('$BlockName', "\*")'.</span></span>
    * <span data-ttu-id="d9277-129">COLLECTEDLIST(’$BlockName’, "\*")</span><span class="sxs-lookup"><span data-stu-id="d9277-129">COLLECTEDLIST('$BlockName', "\*")</span></span>  
17. <span data-ttu-id="d9277-130">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="d9277-130">Click Save.</span></span>
    * <span data-ttu-id="d9277-131">Le modèle « \* » signifie que tous les blocs sont inclus dans la liste pour cet enregistrement.</span><span class="sxs-lookup"><span data-stu-id="d9277-131">The pattern "\*" means that all blocks will be included to the list for this record.</span></span>  
18. <span data-ttu-id="d9277-132">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="d9277-132">Close the page.</span></span>
19. <span data-ttu-id="d9277-133">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="d9277-133">Click OK.</span></span>
20. <span data-ttu-id="d9277-134">Cliquez sur l’onglet Format.</span><span class="sxs-lookup"><span data-stu-id="d9277-134">Click the Format tab.</span></span>
21. <span data-ttu-id="d9277-135">Dans l’arborescence, sélectionnez « Déclaration d’échanges de biens\Données ».</span><span class="sxs-lookup"><span data-stu-id="d9277-135">In the tree, select 'Intrastat\Data'.</span></span>
22. <span data-ttu-id="d9277-136">Cliquez sur Ajouter pour ouvrir la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="d9277-136">Click Add to open the drop dialog.</span></span>
23. <span data-ttu-id="d9277-137">Dans l’arborescence, sélectionnez « Texte\Souche ».</span><span class="sxs-lookup"><span data-stu-id="d9277-137">In the tree, select 'Text\Sequence'.</span></span>
24. <span data-ttu-id="d9277-138">Dans le champ Nom, tapez « Totaux par bloc ».</span><span class="sxs-lookup"><span data-stu-id="d9277-138">In the Name field, type 'Totals by blocks'.</span></span>
    * <span data-ttu-id="d9277-139">Totaux par bloc</span><span class="sxs-lookup"><span data-stu-id="d9277-139">Totals by blocks</span></span>  
25. <span data-ttu-id="d9277-140">Dans le champ Caractères spéciaux, sélectionnez « Nouvelle ligne – Windows (CR LF) ».</span><span class="sxs-lookup"><span data-stu-id="d9277-140">In the Special characters field, select 'New line - Windows (CR LF)'.</span></span>
26. <span data-ttu-id="d9277-141">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="d9277-141">Click OK.</span></span>
27. <span data-ttu-id="d9277-142">Dans l’arborescence, sélectionnez « Déclaration d’échanges de biens\Données\Totaux par bloc ».</span><span class="sxs-lookup"><span data-stu-id="d9277-142">In the tree, select 'Intrastat\Data\Totals by blocks'.</span></span>
28. <span data-ttu-id="d9277-143">Cliquez sur Ajouter pour ouvrir la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="d9277-143">Click Add to open the drop dialog.</span></span>
29. <span data-ttu-id="d9277-144">Dans l’arborescence, sélectionnez « Texte\Chaîne ».</span><span class="sxs-lookup"><span data-stu-id="d9277-144">In the tree, select 'Text\String'.</span></span>
30. <span data-ttu-id="d9277-145">Dans le champ Nom, tapez « Code du bloc ».</span><span class="sxs-lookup"><span data-stu-id="d9277-145">In the Name field, type 'Block code'.</span></span>
    * <span data-ttu-id="d9277-146">Code du bloc</span><span class="sxs-lookup"><span data-stu-id="d9277-146">Block code</span></span>  
31. <span data-ttu-id="d9277-147">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="d9277-147">Click OK.</span></span>
32. <span data-ttu-id="d9277-148">Cliquez sur Ajouter une chaîne.</span><span class="sxs-lookup"><span data-stu-id="d9277-148">Click Add String.</span></span>
33. <span data-ttu-id="d9277-149">Dans le champ Nom, tapez « Comptage des lignes ».</span><span class="sxs-lookup"><span data-stu-id="d9277-149">In the Name field, type 'Lines counting'.</span></span>
    * <span data-ttu-id="d9277-150">Comptage des lignes</span><span class="sxs-lookup"><span data-stu-id="d9277-150">Lines counting</span></span>  
34. <span data-ttu-id="d9277-151">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="d9277-151">Click OK.</span></span>
35. <span data-ttu-id="d9277-152">Cliquez sur Ajouter une chaîne.</span><span class="sxs-lookup"><span data-stu-id="d9277-152">Click Add String.</span></span>
36. <span data-ttu-id="d9277-153">Dans le champ Nom, tapez « Montant total ».</span><span class="sxs-lookup"><span data-stu-id="d9277-153">In the Name field, type 'Total amount'.</span></span>
    * <span data-ttu-id="d9277-154">Montant total</span><span class="sxs-lookup"><span data-stu-id="d9277-154">Total amount</span></span>  
37. <span data-ttu-id="d9277-155">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="d9277-155">Click OK.</span></span>
38. <span data-ttu-id="d9277-156">Cliquez sur l’onglet Mise en relation.</span><span class="sxs-lookup"><span data-stu-id="d9277-156">Click the Mapping tab.</span></span>
39. <span data-ttu-id="d9277-157">Dans l’arborescence, sélectionnez « $BlocksList ».</span><span class="sxs-lookup"><span data-stu-id="d9277-157">In the tree, select '$BlocksList'.</span></span>
40. <span data-ttu-id="d9277-158">Cliquez sur Lier.</span><span class="sxs-lookup"><span data-stu-id="d9277-158">Click Bind.</span></span>
    * <span data-ttu-id="d9277-159">Créez une ligne de synthèse pour chaque bloc mémorisé.</span><span class="sxs-lookup"><span data-stu-id="d9277-159">Create a summary line for each memorized block.</span></span>  
41. <span data-ttu-id="d9277-160">Cliquez sur l’onglet Format.</span><span class="sxs-lookup"><span data-stu-id="d9277-160">Click the Format tab.</span></span>
42. <span data-ttu-id="d9277-161">Dans l’arborescence, sélectionnez « Déclaration d’échanges de biens\Données\Totaux par bloc\Code du bloc ».</span><span class="sxs-lookup"><span data-stu-id="d9277-161">In the tree, select 'Intrastat\Data\Totals by blocks\Block code'.</span></span>
43. <span data-ttu-id="d9277-162">Cliquez sur l’onglet Mise en relation.</span><span class="sxs-lookup"><span data-stu-id="d9277-162">Click the Mapping tab.</span></span>
44. <span data-ttu-id="d9277-163">Cliquez sur Modifier la formule.</span><span class="sxs-lookup"><span data-stu-id="d9277-163">Click Edit formula.</span></span>
45. <span data-ttu-id="d9277-164">Dans le champ Formule, entrez ’"ID bloc : " & ’.</span><span class="sxs-lookup"><span data-stu-id="d9277-164">In the Formula field, enter '"Block id: " & '.</span></span>
    * <span data-ttu-id="d9277-165">"ID bloc : " &</span><span class="sxs-lookup"><span data-stu-id="d9277-165">"Block id: " &</span></span>  
46. <span data-ttu-id="d9277-166">Dans l’arborescence, développez « $BlocksList ».</span><span class="sxs-lookup"><span data-stu-id="d9277-166">In the tree, expand '$BlocksList'.</span></span>
47. <span data-ttu-id="d9277-167">Dans l’arborescence, sélectionnez « $BlocksList\Valeur ».</span><span class="sxs-lookup"><span data-stu-id="d9277-167">In the tree, select '$BlocksList\Value'.</span></span>
48. <span data-ttu-id="d9277-168">Cliquez sur Ajouter une source de données.</span><span class="sxs-lookup"><span data-stu-id="d9277-168">Click Add data source.</span></span>
49. <span data-ttu-id="d9277-169">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="d9277-169">Click Save.</span></span>
50. <span data-ttu-id="d9277-170">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="d9277-170">Close the page.</span></span>
51. <span data-ttu-id="d9277-171">Cliquez sur l’onglet Format.</span><span class="sxs-lookup"><span data-stu-id="d9277-171">Click the Format tab.</span></span>
52. <span data-ttu-id="d9277-172">Dans l’arborescence, sélectionnez « Déclaration d’échanges de biens\Données\Totaux par bloc\Comptage des lignes ».</span><span class="sxs-lookup"><span data-stu-id="d9277-172">In the tree, select 'Intrastat\Data\Totals by blocks\Lines counting'.</span></span>
53. <span data-ttu-id="d9277-173">Cliquez sur l’onglet Mise en relation.</span><span class="sxs-lookup"><span data-stu-id="d9277-173">Click the Mapping tab.</span></span>
54. <span data-ttu-id="d9277-174">Cliquez sur Modifier la formule.</span><span class="sxs-lookup"><span data-stu-id="d9277-174">Click Edit formula.</span></span>
    * <span data-ttu-id="d9277-175">Créez une sortie pour le nombre de lignes pour chaque bloc présenté dans cet état.</span><span class="sxs-lookup"><span data-stu-id="d9277-175">Create output for the number of lines for each block presented in this report.</span></span>  
55. <span data-ttu-id="d9277-176">Dans le champ Formule, entrez ’"Nombre de lignes dans ce bloc : " & ’.</span><span class="sxs-lookup"><span data-stu-id="d9277-176">In the Formula field, enter '"Number of lines in this block: " & '.</span></span>
    * <span data-ttu-id="d9277-177">"Nombre de lignes dans ce bloc : " &</span><span class="sxs-lookup"><span data-stu-id="d9277-177">"Number of lines in this block: " &</span></span>  
56. <span data-ttu-id="d9277-178">Dans le champ Formule, entrez ’"Nombre de lignes dans ce bloc : " & TEXT(’.</span><span class="sxs-lookup"><span data-stu-id="d9277-178">In the Formula field, enter '"Number of lines in this block: " & TEXT('.</span></span>
    * <span data-ttu-id="d9277-179">"Nombre de lignes dans ce bloc : " & TEXT(</span><span class="sxs-lookup"><span data-stu-id="d9277-179">"Number of lines in this block: " & TEXT(</span></span>  
57. <span data-ttu-id="d9277-180">Dans l’arborescence, sélectionnez « Fonctions de collecte des données\COUNTIFS ».</span><span class="sxs-lookup"><span data-stu-id="d9277-180">In the tree, select 'Data collection functions\COUNTIFS'.</span></span>
58. <span data-ttu-id="d9277-181">Cliquez sur Ajouter une fonction.</span><span class="sxs-lookup"><span data-stu-id="d9277-181">Click Add function.</span></span>
59. <span data-ttu-id="d9277-182">Cliquez sur Ajouter une source de données.</span><span class="sxs-lookup"><span data-stu-id="d9277-182">Click Add data source.</span></span>
60. <span data-ttu-id="d9277-183">Dans le champ Formule, entrez ’"Nombre de lignes dans ce bloc: " & TEXT(COUNTIFS(’$BlockName’, ’.</span><span class="sxs-lookup"><span data-stu-id="d9277-183">In the Formula field, enter '"Number of lines in this block: " & TEXT(COUNTIFS('$BlockName', '.</span></span>
    * <span data-ttu-id="d9277-184">"Nombre de lignes dans ce bloc: " & TEXT(COUNTIFS(’$BlockName’,</span><span class="sxs-lookup"><span data-stu-id="d9277-184">"Number of lines in this block: " & TEXT(COUNTIFS('$BlockName',</span></span>  
61. <span data-ttu-id="d9277-185">Dans l’arborescence, développez « $BlocksList ».</span><span class="sxs-lookup"><span data-stu-id="d9277-185">In the tree, expand '$BlocksList'.</span></span>
62. <span data-ttu-id="d9277-186">Dans l’arborescence, sélectionnez « $BlocksList\Valeur ».</span><span class="sxs-lookup"><span data-stu-id="d9277-186">In the tree, select '$BlocksList\Value'.</span></span>
63. <span data-ttu-id="d9277-187">Cliquez sur Ajouter une source de données.</span><span class="sxs-lookup"><span data-stu-id="d9277-187">Click Add data source.</span></span>
64. <span data-ttu-id="d9277-188">Dans le champ Formule, entrez ’"Nombre de lignes dans ce bloc: " & TEXT(COUNTIFS(’$BlockName’, ’$BlocksList’.Value, ’.</span><span class="sxs-lookup"><span data-stu-id="d9277-188">In the Formula field, enter '"Number of lines in this block: " & TEXT(COUNTIFS('$BlockName', '$BlocksList'.Value, '.</span></span>
    * <span data-ttu-id="d9277-189">"Nombre de lignes dans ce bloc: " & TEXT(COUNTIFS(’$BlockName’, ’$BlocksList’.Value,</span><span class="sxs-lookup"><span data-stu-id="d9277-189">"Number of lines in this block: " & TEXT(COUNTIFS('$BlockName', '$BlocksList'.Value,</span></span>  
65. <span data-ttu-id="d9277-190">Dans l’arborescence, sélectionnez « RecName ».</span><span class="sxs-lookup"><span data-stu-id="d9277-190">In the tree, select '$RecName'.</span></span>
66. <span data-ttu-id="d9277-191">Cliquez sur Ajouter une source de données.</span><span class="sxs-lookup"><span data-stu-id="d9277-191">Click Add data source.</span></span>
67. <span data-ttu-id="d9277-192">Dans le champ Formule, entrez ’"Nombre de lignes dans ce bloc: " & TEXT(COUNTIFS(’$BlockName’, ’$BlocksList’.Value, ’$RecName’, "\*"))’.</span><span class="sxs-lookup"><span data-stu-id="d9277-192">In the Formula field, enter '"Number of lines in this block: " & TEXT(COUNTIFS('$BlockName', '$BlocksList'.Value, '$RecName', "\*"))'.</span></span>
    * <span data-ttu-id="d9277-193">"Nombre de lignes dans ce bloc: " & TEXT(COUNTIFS(’$BlockName’, ’$BlocksList’.Value, ’$RecName’, "\*"))</span><span class="sxs-lookup"><span data-stu-id="d9277-193">"Number of lines in this block: " & TEXT(COUNTIFS('$BlockName', '$BlocksList'.Value, '$RecName', "\*"))</span></span>  
68. <span data-ttu-id="d9277-194">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="d9277-194">Click Save.</span></span>
69. <span data-ttu-id="d9277-195">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="d9277-195">Close the page.</span></span>
70. <span data-ttu-id="d9277-196">Cliquez sur l’onglet Format.</span><span class="sxs-lookup"><span data-stu-id="d9277-196">Click the Format tab.</span></span>
71. <span data-ttu-id="d9277-197">Dans l’arborescence, sélectionnez « Déclaration d’échanges de biens\Données\Totaux par bloc\Montant total ».</span><span class="sxs-lookup"><span data-stu-id="d9277-197">In the tree, select 'Intrastat\Data\Totals by blocks\Total amount'.</span></span>
72. <span data-ttu-id="d9277-198">Cliquez sur l’onglet Mise en relation.</span><span class="sxs-lookup"><span data-stu-id="d9277-198">Click the Mapping tab.</span></span>
73. <span data-ttu-id="d9277-199">Cliquez sur Modifier la formule.</span><span class="sxs-lookup"><span data-stu-id="d9277-199">Click Edit formula.</span></span>
    * <span data-ttu-id="d9277-200">Créez une sortie qui est égale au total du montant facturé pour chaque bloc présenté dans cet état.</span><span class="sxs-lookup"><span data-stu-id="d9277-200">Create output that will be the total of the invoiced amount for each block presented in this report.</span></span>  
74. <span data-ttu-id="d9277-201">Dans le champ Formule, entrez ’"Somme du montant facturé : " & TEXT(SUMIFS(’$InvName’, ’$BlockName’, ’$BlocksList’.Value, ’$RecName’, "\*"))’.</span><span class="sxs-lookup"><span data-stu-id="d9277-201">In the Formula field, enter '"Sum of invoiced amount: " & TEXT(SUMIFS('$InvName', '$BlockName', '$BlocksList'.Value, '$RecName', "\*"))'.</span></span>
    * <span data-ttu-id="d9277-202">"Somme du montant facturé : " & TEXT(SUMIFS(’$InvName’, ’$BlockName’, ’$BlocksList’.Value, ’$RecName’, "\*"))</span><span class="sxs-lookup"><span data-stu-id="d9277-202">"Sum of invoiced amount: " & TEXT(SUMIFS('$InvName', '$BlockName', '$BlocksList'.Value, '$RecName', "\*"))</span></span>  
75. <span data-ttu-id="d9277-203">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="d9277-203">Click Save.</span></span>
76. <span data-ttu-id="d9277-204">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="d9277-204">Close the page.</span></span>
77. <span data-ttu-id="d9277-205">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="d9277-205">Click Save.</span></span>
78. <span data-ttu-id="d9277-206">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="d9277-206">Close the page.</span></span>



[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]