---
title: ER Configurer le format pour effectuer le comptage et la synthèse (Partie 3 - Utiliser les calculs pour générer la sortie)
description: Cette rubrique décrit comment configurer un format de gestion des états électroniques pour effectuer le comptage et la somme en fonction des données de la sortie de texte déjà générée. (Partie 3)
author: NickSelin
manager: AnnBe
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
ms.openlocfilehash: af95399118b9059b9bead3a1b84203cf3b6e74c2
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/09/2021
ms.locfileid: "5567114"
---
# <a name="er-configure-format-to-do-counting-and-summing-part-3---use-computations-to-make-the-output"></a><span data-ttu-id="2f7d7-104">ER Configurer le format pour effectuer le comptage et la synthèse (Partie 3 - Utiliser les calculs pour générer la sortie)</span><span class="sxs-lookup"><span data-stu-id="2f7d7-104">ER Configure format to do counting and summing (Part 3 - Use computations to make the output)</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="2f7d7-105">Les étapes suivantes expliquent comment un utilisateur affecté au rôle d’administrateur système ou de développeur d’états électroniques peut configurer un format de génération d’états électroniques (ER) pour effectuer le comptage et la synthèse en fonction des données de la sortie de texte déjà générée.</span><span class="sxs-lookup"><span data-stu-id="2f7d7-105">The following steps explain how a user assigned to the system administrator or electronic reporting developer role can configure an Electronic reporting (ER) format to do counting and summing based on data of the already generated text output.</span></span> <span data-ttu-id="2f7d7-106">Ces étapes peuvent être effectuées dans n’importe quelle société.</span><span class="sxs-lookup"><span data-stu-id="2f7d7-106">These steps can be performed in any company.</span></span>

<span data-ttu-id="2f7d7-107">Pour effectuer ces étapes, vous devez d’abord effectuer les étapes de la procédure « ER Configurer le format pour effectuer le comptage et la synthèse (Partie 2 : Configurer des calculs) ».</span><span class="sxs-lookup"><span data-stu-id="2f7d7-107">To complete these steps, you must first complete the steps in the "ER Configure format to do counting and summing (Part 2: Configure computations)" procedure.</span></span>

<span data-ttu-id="2f7d7-108">Cette procédure s’applique à une fonction qui a été ajoutée dans la version 1611 de Dynamics 365 for Operations.</span><span class="sxs-lookup"><span data-stu-id="2f7d7-108">This procedure is for a feature that was added in Dynamics 365 for Operations version 1611.</span></span>


## <a name="configure-this-report-to-use-counting-and-summing-info"></a><span data-ttu-id="2f7d7-109">Configurer cet état pour utiliser les informations de comptage et de synthèse</span><span class="sxs-lookup"><span data-stu-id="2f7d7-109">Configure this report to use counting and summing info</span></span>
1. <span data-ttu-id="2f7d7-110">Accédez à Administration d’organisation > Espaces de travail > États électroniques.</span><span class="sxs-lookup"><span data-stu-id="2f7d7-110">Go to Organization administration > Workspaces > Electronic reporting.</span></span>
2. <span data-ttu-id="2f7d7-111">Cliquez sur Configurations des états.</span><span class="sxs-lookup"><span data-stu-id="2f7d7-111">Click Reporting configurations.</span></span>
3. <span data-ttu-id="2f7d7-112">Dans l’arborescence, développez « Modèle de déclaration d’échanges de biens ».</span><span class="sxs-lookup"><span data-stu-id="2f7d7-112">In the tree, expand 'Intrastat model'.</span></span>
4. <span data-ttu-id="2f7d7-113">Dans l’arborescence, développez « Modèle de déclaration d’échanges de biens\Déclaration d’échanges de biens (Allemagne) ».</span><span class="sxs-lookup"><span data-stu-id="2f7d7-113">In the tree, expand 'Intrastat model\Intrastat (DE)'.</span></span>
5. <span data-ttu-id="2f7d7-114">Dans l’arborescence, sélectionnez « Modèle de déclaration d’échanges de biens\Déclaration d’échanges de biens (Allemagne)\Déclaration d’échanges de biens (Allemagne) avec comptage et synthèse ».</span><span class="sxs-lookup"><span data-stu-id="2f7d7-114">In the tree, select 'Intrastat model\Intrastat (DE)\Intrastat (DE) with counting & summing'.</span></span>
6. <span data-ttu-id="2f7d7-115">Cliquez sur Concepteur.</span><span class="sxs-lookup"><span data-stu-id="2f7d7-115">Click Designer.</span></span>
7. <span data-ttu-id="2f7d7-116">Cliquez sur l’onglet Mise en relation.</span><span class="sxs-lookup"><span data-stu-id="2f7d7-116">Click the Mapping tab.</span></span>
8. <span data-ttu-id="2f7d7-117">Cliquez sur Ajouter racine pour ouvrir la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="2f7d7-117">Click Add root to open the drop dialog.</span></span>
    * <span data-ttu-id="2f7d7-118">Ajoutez une nouvelle source de données pour obtenir la liste des blocs mémorisés.</span><span class="sxs-lookup"><span data-stu-id="2f7d7-118">Add a new data source to get the list of memorized blocks.</span></span>  
9. <span data-ttu-id="2f7d7-119">Dans l’arborescence, sélectionnez « Fonctions\Champ calculé ».</span><span class="sxs-lookup"><span data-stu-id="2f7d7-119">In the tree, select 'Functions\Calculated field'.</span></span>
10. <span data-ttu-id="2f7d7-120">Dans le champ Nom, tapez « $BlocksList ».</span><span class="sxs-lookup"><span data-stu-id="2f7d7-120">In the Name field, type '$BlocksList'.</span></span>
    * <span data-ttu-id="2f7d7-121">$BlocksList</span><span class="sxs-lookup"><span data-stu-id="2f7d7-121">$BlocksList</span></span>  
11. <span data-ttu-id="2f7d7-122">Cliquez sur Modifier la formule.</span><span class="sxs-lookup"><span data-stu-id="2f7d7-122">Click Edit formula.</span></span>
12. <span data-ttu-id="2f7d7-123">Dans l’arborescence, sélectionnez « Fonctions de collecte des données\COLLECTEDLIST ».</span><span class="sxs-lookup"><span data-stu-id="2f7d7-123">In the tree, select 'Data collection functions\COLLECTEDLIST'.</span></span>
13. <span data-ttu-id="2f7d7-124">Cliquez sur Ajouter une fonction.</span><span class="sxs-lookup"><span data-stu-id="2f7d7-124">Click Add function.</span></span>
14. <span data-ttu-id="2f7d7-125">Cliquez sur Ajouter une source de données.</span><span class="sxs-lookup"><span data-stu-id="2f7d7-125">Click Add data source.</span></span>
15. <span data-ttu-id="2f7d7-126">Dans le champ Formule, entrez ’COLLECTEDLIST(’$BlockName’, ’.</span><span class="sxs-lookup"><span data-stu-id="2f7d7-126">In the Formula field, enter 'COLLECTEDLIST('$BlockName', '.</span></span>
    * <span data-ttu-id="2f7d7-127">COLLECTEDLIST(’$BlockName’,</span><span class="sxs-lookup"><span data-stu-id="2f7d7-127">COLLECTEDLIST('$BlockName',</span></span>  
16. <span data-ttu-id="2f7d7-128">Dans le champ Formule, entrez ’COLLECTEDLIST(’$BlockName’, "\*")’.</span><span class="sxs-lookup"><span data-stu-id="2f7d7-128">In the Formula field, enter 'COLLECTEDLIST('$BlockName', "\*")'.</span></span>
    * <span data-ttu-id="2f7d7-129">COLLECTEDLIST(’$BlockName’, "\*")</span><span class="sxs-lookup"><span data-stu-id="2f7d7-129">COLLECTEDLIST('$BlockName', "\*")</span></span>  
17. <span data-ttu-id="2f7d7-130">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="2f7d7-130">Click Save.</span></span>
    * <span data-ttu-id="2f7d7-131">Le modèle « \* » signifie que tous les blocs sont inclus dans la liste pour cet enregistrement.</span><span class="sxs-lookup"><span data-stu-id="2f7d7-131">The pattern "\*" means that all blocks will be included to the list for this record.</span></span>  
18. <span data-ttu-id="2f7d7-132">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="2f7d7-132">Close the page.</span></span>
19. <span data-ttu-id="2f7d7-133">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="2f7d7-133">Click OK.</span></span>
20. <span data-ttu-id="2f7d7-134">Cliquez sur l’onglet Format.</span><span class="sxs-lookup"><span data-stu-id="2f7d7-134">Click the Format tab.</span></span>
21. <span data-ttu-id="2f7d7-135">Dans l’arborescence, sélectionnez « Déclaration d’échanges de biens\Données ».</span><span class="sxs-lookup"><span data-stu-id="2f7d7-135">In the tree, select 'Intrastat\Data'.</span></span>
22. <span data-ttu-id="2f7d7-136">Cliquez sur Ajouter pour ouvrir la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="2f7d7-136">Click Add to open the drop dialog.</span></span>
23. <span data-ttu-id="2f7d7-137">Dans l’arborescence, sélectionnez « Texte\Souche ».</span><span class="sxs-lookup"><span data-stu-id="2f7d7-137">In the tree, select 'Text\Sequence'.</span></span>
24. <span data-ttu-id="2f7d7-138">Dans le champ Nom, tapez « Totaux par bloc ».</span><span class="sxs-lookup"><span data-stu-id="2f7d7-138">In the Name field, type 'Totals by blocks'.</span></span>
    * <span data-ttu-id="2f7d7-139">Totaux par bloc</span><span class="sxs-lookup"><span data-stu-id="2f7d7-139">Totals by blocks</span></span>  
25. <span data-ttu-id="2f7d7-140">Dans le champ Caractères spéciaux, sélectionnez « Nouvelle ligne - Windows (CR LF) ».</span><span class="sxs-lookup"><span data-stu-id="2f7d7-140">In the Special characters field, select 'New line - Windows (CR LF)'.</span></span>
26. <span data-ttu-id="2f7d7-141">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="2f7d7-141">Click OK.</span></span>
27. <span data-ttu-id="2f7d7-142">Dans l’arborescence, sélectionnez « Déclaration d’échanges de biens\Données\Totaux par bloc ».</span><span class="sxs-lookup"><span data-stu-id="2f7d7-142">In the tree, select 'Intrastat\Data\Totals by blocks'.</span></span>
28. <span data-ttu-id="2f7d7-143">Cliquez sur Ajouter pour ouvrir la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="2f7d7-143">Click Add to open the drop dialog.</span></span>
29. <span data-ttu-id="2f7d7-144">Dans l’arborescence, sélectionnez « Texte\Chaîne ».</span><span class="sxs-lookup"><span data-stu-id="2f7d7-144">In the tree, select 'Text\String'.</span></span>
30. <span data-ttu-id="2f7d7-145">Dans le champ Nom, tapez « Code du bloc ».</span><span class="sxs-lookup"><span data-stu-id="2f7d7-145">In the Name field, type 'Block code'.</span></span>
    * <span data-ttu-id="2f7d7-146">Code du bloc</span><span class="sxs-lookup"><span data-stu-id="2f7d7-146">Block code</span></span>  
31. <span data-ttu-id="2f7d7-147">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="2f7d7-147">Click OK.</span></span>
32. <span data-ttu-id="2f7d7-148">Cliquez sur Ajouter une chaîne.</span><span class="sxs-lookup"><span data-stu-id="2f7d7-148">Click Add String.</span></span>
33. <span data-ttu-id="2f7d7-149">Dans le champ Nom, tapez « Comptage des lignes ».</span><span class="sxs-lookup"><span data-stu-id="2f7d7-149">In the Name field, type 'Lines counting'.</span></span>
    * <span data-ttu-id="2f7d7-150">Comptage des lignes</span><span class="sxs-lookup"><span data-stu-id="2f7d7-150">Lines counting</span></span>  
34. <span data-ttu-id="2f7d7-151">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="2f7d7-151">Click OK.</span></span>
35. <span data-ttu-id="2f7d7-152">Cliquez sur Ajouter une chaîne.</span><span class="sxs-lookup"><span data-stu-id="2f7d7-152">Click Add String.</span></span>
36. <span data-ttu-id="2f7d7-153">Dans le champ Nom, tapez « Montant total ».</span><span class="sxs-lookup"><span data-stu-id="2f7d7-153">In the Name field, type 'Total amount'.</span></span>
    * <span data-ttu-id="2f7d7-154">Montant total</span><span class="sxs-lookup"><span data-stu-id="2f7d7-154">Total amount</span></span>  
37. <span data-ttu-id="2f7d7-155">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="2f7d7-155">Click OK.</span></span>
38. <span data-ttu-id="2f7d7-156">Cliquez sur l’onglet Mise en relation.</span><span class="sxs-lookup"><span data-stu-id="2f7d7-156">Click the Mapping tab.</span></span>
39. <span data-ttu-id="2f7d7-157">Dans l’arborescence, sélectionnez « $BlocksList ».</span><span class="sxs-lookup"><span data-stu-id="2f7d7-157">In the tree, select '$BlocksList'.</span></span>
40. <span data-ttu-id="2f7d7-158">Cliquez sur Lier.</span><span class="sxs-lookup"><span data-stu-id="2f7d7-158">Click Bind.</span></span>
    * <span data-ttu-id="2f7d7-159">Créez une ligne de synthèse pour chaque bloc mémorisé.</span><span class="sxs-lookup"><span data-stu-id="2f7d7-159">Create a summary line for each memorized block.</span></span>  
41. <span data-ttu-id="2f7d7-160">Cliquez sur l’onglet Format.</span><span class="sxs-lookup"><span data-stu-id="2f7d7-160">Click the Format tab.</span></span>
42. <span data-ttu-id="2f7d7-161">Dans l’arborescence, sélectionnez « Déclaration d’échanges de biens\Données\Totaux par bloc\Code du bloc ».</span><span class="sxs-lookup"><span data-stu-id="2f7d7-161">In the tree, select 'Intrastat\Data\Totals by blocks\Block code'.</span></span>
43. <span data-ttu-id="2f7d7-162">Cliquez sur l’onglet Mise en relation.</span><span class="sxs-lookup"><span data-stu-id="2f7d7-162">Click the Mapping tab.</span></span>
44. <span data-ttu-id="2f7d7-163">Cliquez sur Modifier la formule.</span><span class="sxs-lookup"><span data-stu-id="2f7d7-163">Click Edit formula.</span></span>
45. <span data-ttu-id="2f7d7-164">Dans le champ Formule, entrez ’"ID bloc : " & ’.</span><span class="sxs-lookup"><span data-stu-id="2f7d7-164">In the Formula field, enter '"Block id: " & '.</span></span>
    * <span data-ttu-id="2f7d7-165">"ID bloc : " &</span><span class="sxs-lookup"><span data-stu-id="2f7d7-165">"Block id: " &</span></span>  
46. <span data-ttu-id="2f7d7-166">Dans l’arborescence, développez « $BlocksList ».</span><span class="sxs-lookup"><span data-stu-id="2f7d7-166">In the tree, expand '$BlocksList'.</span></span>
47. <span data-ttu-id="2f7d7-167">Dans l’arborescence, sélectionnez « $BlocksList\Valeur ».</span><span class="sxs-lookup"><span data-stu-id="2f7d7-167">In the tree, select '$BlocksList\Value'.</span></span>
48. <span data-ttu-id="2f7d7-168">Cliquez sur Ajouter une source de données.</span><span class="sxs-lookup"><span data-stu-id="2f7d7-168">Click Add data source.</span></span>
49. <span data-ttu-id="2f7d7-169">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="2f7d7-169">Click Save.</span></span>
50. <span data-ttu-id="2f7d7-170">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="2f7d7-170">Close the page.</span></span>
51. <span data-ttu-id="2f7d7-171">Cliquez sur l’onglet Format.</span><span class="sxs-lookup"><span data-stu-id="2f7d7-171">Click the Format tab.</span></span>
52. <span data-ttu-id="2f7d7-172">Dans l’arborescence, sélectionnez « Déclaration d’échanges de biens\Données\Totaux par bloc\Comptage des lignes ».</span><span class="sxs-lookup"><span data-stu-id="2f7d7-172">In the tree, select 'Intrastat\Data\Totals by blocks\Lines counting'.</span></span>
53. <span data-ttu-id="2f7d7-173">Cliquez sur l’onglet Mise en relation.</span><span class="sxs-lookup"><span data-stu-id="2f7d7-173">Click the Mapping tab.</span></span>
54. <span data-ttu-id="2f7d7-174">Cliquez sur Modifier la formule.</span><span class="sxs-lookup"><span data-stu-id="2f7d7-174">Click Edit formula.</span></span>
    * <span data-ttu-id="2f7d7-175">Créez une sortie pour le nombre de lignes pour chaque bloc présenté dans cet état.</span><span class="sxs-lookup"><span data-stu-id="2f7d7-175">Create output for the number of lines for each block presented in this report.</span></span>  
55. <span data-ttu-id="2f7d7-176">Dans le champ Formule, entrez ’"Nombre de lignes dans ce bloc : " & ’.</span><span class="sxs-lookup"><span data-stu-id="2f7d7-176">In the Formula field, enter '"Number of lines in this block: " & '.</span></span>
    * <span data-ttu-id="2f7d7-177">"Nombre de lignes dans ce bloc : " &</span><span class="sxs-lookup"><span data-stu-id="2f7d7-177">"Number of lines in this block: " &</span></span>  
56. <span data-ttu-id="2f7d7-178">Dans le champ Formule, entrez ’"Nombre de lignes dans ce bloc : " & TEXT(’.</span><span class="sxs-lookup"><span data-stu-id="2f7d7-178">In the Formula field, enter '"Number of lines in this block: " & TEXT('.</span></span>
    * <span data-ttu-id="2f7d7-179">"Nombre de lignes dans ce bloc : " & TEXT(</span><span class="sxs-lookup"><span data-stu-id="2f7d7-179">"Number of lines in this block: " & TEXT(</span></span>  
57. <span data-ttu-id="2f7d7-180">Dans l’arborescence, sélectionnez « Fonctions de collecte des données\COUNTIFS ».</span><span class="sxs-lookup"><span data-stu-id="2f7d7-180">In the tree, select 'Data collection functions\COUNTIFS'.</span></span>
58. <span data-ttu-id="2f7d7-181">Cliquez sur Ajouter une fonction.</span><span class="sxs-lookup"><span data-stu-id="2f7d7-181">Click Add function.</span></span>
59. <span data-ttu-id="2f7d7-182">Cliquez sur Ajouter une source de données.</span><span class="sxs-lookup"><span data-stu-id="2f7d7-182">Click Add data source.</span></span>
60. <span data-ttu-id="2f7d7-183">Dans le champ Formule, entrez ’"Nombre de lignes dans ce bloc: " & TEXT(COUNTIFS(’$BlockName’, ’.</span><span class="sxs-lookup"><span data-stu-id="2f7d7-183">In the Formula field, enter '"Number of lines in this block: " & TEXT(COUNTIFS('$BlockName', '.</span></span>
    * <span data-ttu-id="2f7d7-184">"Nombre de lignes dans ce bloc: " & TEXT(COUNTIFS(’$BlockName’,</span><span class="sxs-lookup"><span data-stu-id="2f7d7-184">"Number of lines in this block: " & TEXT(COUNTIFS('$BlockName',</span></span>  
61. <span data-ttu-id="2f7d7-185">Dans l’arborescence, développez « $BlocksList ».</span><span class="sxs-lookup"><span data-stu-id="2f7d7-185">In the tree, expand '$BlocksList'.</span></span>
62. <span data-ttu-id="2f7d7-186">Dans l’arborescence, sélectionnez « $BlocksList\Valeur ».</span><span class="sxs-lookup"><span data-stu-id="2f7d7-186">In the tree, select '$BlocksList\Value'.</span></span>
63. <span data-ttu-id="2f7d7-187">Cliquez sur Ajouter une source de données.</span><span class="sxs-lookup"><span data-stu-id="2f7d7-187">Click Add data source.</span></span>
64. <span data-ttu-id="2f7d7-188">Dans le champ Formule, entrez ’"Nombre de lignes dans ce bloc: " & TEXT(COUNTIFS(’$BlockName’, ’$BlocksList’.Value, ’.</span><span class="sxs-lookup"><span data-stu-id="2f7d7-188">In the Formula field, enter '"Number of lines in this block: " & TEXT(COUNTIFS('$BlockName', '$BlocksList'.Value, '.</span></span>
    * <span data-ttu-id="2f7d7-189">"Nombre de lignes dans ce bloc: " & TEXT(COUNTIFS(’$BlockName’, ’$BlocksList’.Value,</span><span class="sxs-lookup"><span data-stu-id="2f7d7-189">"Number of lines in this block: " & TEXT(COUNTIFS('$BlockName', '$BlocksList'.Value,</span></span>  
65. <span data-ttu-id="2f7d7-190">Dans l’arborescence, sélectionnez « RecName ».</span><span class="sxs-lookup"><span data-stu-id="2f7d7-190">In the tree, select '$RecName'.</span></span>
66. <span data-ttu-id="2f7d7-191">Cliquez sur Ajouter une source de données.</span><span class="sxs-lookup"><span data-stu-id="2f7d7-191">Click Add data source.</span></span>
67. <span data-ttu-id="2f7d7-192">Dans le champ Formule, entrez ’"Nombre de lignes dans ce bloc: " & TEXT(COUNTIFS(’$BlockName’, ’$BlocksList’.Value, ’$RecName’, "\*"))’.</span><span class="sxs-lookup"><span data-stu-id="2f7d7-192">In the Formula field, enter '"Number of lines in this block: " & TEXT(COUNTIFS('$BlockName', '$BlocksList'.Value, '$RecName', "\*"))'.</span></span>
    * <span data-ttu-id="2f7d7-193">"Nombre de lignes dans ce bloc: " & TEXT(COUNTIFS(’$BlockName’, ’$BlocksList’.Value, ’$RecName’, "\*"))</span><span class="sxs-lookup"><span data-stu-id="2f7d7-193">"Number of lines in this block: " & TEXT(COUNTIFS('$BlockName', '$BlocksList'.Value, '$RecName', "\*"))</span></span>  
68. <span data-ttu-id="2f7d7-194">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="2f7d7-194">Click Save.</span></span>
69. <span data-ttu-id="2f7d7-195">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="2f7d7-195">Close the page.</span></span>
70. <span data-ttu-id="2f7d7-196">Cliquez sur l’onglet Format.</span><span class="sxs-lookup"><span data-stu-id="2f7d7-196">Click the Format tab.</span></span>
71. <span data-ttu-id="2f7d7-197">Dans l’arborescence, sélectionnez « Déclaration d’échanges de biens\Données\Totaux par bloc\Montant total ».</span><span class="sxs-lookup"><span data-stu-id="2f7d7-197">In the tree, select 'Intrastat\Data\Totals by blocks\Total amount'.</span></span>
72. <span data-ttu-id="2f7d7-198">Cliquez sur l’onglet Mise en relation.</span><span class="sxs-lookup"><span data-stu-id="2f7d7-198">Click the Mapping tab.</span></span>
73. <span data-ttu-id="2f7d7-199">Cliquez sur Modifier la formule.</span><span class="sxs-lookup"><span data-stu-id="2f7d7-199">Click Edit formula.</span></span>
    * <span data-ttu-id="2f7d7-200">Créez une sortie qui est égale au total du montant facturé pour chaque bloc présenté dans cet état.</span><span class="sxs-lookup"><span data-stu-id="2f7d7-200">Create output that will be the total of the invoiced amount for each block presented in this report.</span></span>  
74. <span data-ttu-id="2f7d7-201">Dans le champ Formule, entrez ’"Somme du montant facturé : " & TEXT(SUMIFS(’$InvName’, ’$BlockName’, ’$BlocksList’.Value, ’$RecName’, "\*"))’.</span><span class="sxs-lookup"><span data-stu-id="2f7d7-201">In the Formula field, enter '"Sum of invoiced amount: " & TEXT(SUMIFS('$InvName', '$BlockName', '$BlocksList'.Value, '$RecName', "\*"))'.</span></span>
    * <span data-ttu-id="2f7d7-202">"Somme du montant facturé : " & TEXT(SUMIFS(’$InvName’, ’$BlockName’, ’$BlocksList’.Value, ’$RecName’, "\*"))</span><span class="sxs-lookup"><span data-stu-id="2f7d7-202">"Sum of invoiced amount: " & TEXT(SUMIFS('$InvName', '$BlockName', '$BlocksList'.Value, '$RecName', "\*"))</span></span>  
75. <span data-ttu-id="2f7d7-203">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="2f7d7-203">Click Save.</span></span>
76. <span data-ttu-id="2f7d7-204">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="2f7d7-204">Close the page.</span></span>
77. <span data-ttu-id="2f7d7-205">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="2f7d7-205">Click Save.</span></span>
78. <span data-ttu-id="2f7d7-206">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="2f7d7-206">Close the page.</span></span>



[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]