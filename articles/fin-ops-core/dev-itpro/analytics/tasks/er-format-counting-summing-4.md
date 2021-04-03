---
title: ER Configurer le format pour effectuer le comptage et la synthèse (Partie 4 - Exécuter le format)
description: Cette rubrique décrit comment configurer un format de gestion des états électroniques pour effectuer le comptage et la somme en fonction des données de la sortie de texte déjà générée. (Partie 4)
author: NickSelin
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: ERWorkspace, ERSolutionTable, IntrastatParameters, Intrastat, InventItemIdLookupSimple, IntrastatCommodityLookup, ERFormatMappingRunLogTable, DocuView
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 2ca8449581edc06016b6e387880aad91087b67f1
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/09/2021
ms.locfileid: "5565415"
---
# <a name="er-configure-format-to-do-counting-and-summing-part-4---run-format"></a><span data-ttu-id="f7296-104">ER Configurer le format pour effectuer le comptage et la synthèse (Partie 4 - Exécuter le format)</span><span class="sxs-lookup"><span data-stu-id="f7296-104">ER Configure format to do counting and summing (Part 4 - Run format)</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="f7296-105">Les étapes suivantes expliquent comment un utilisateur affecté au rôle d’administrateur système ou de développeur d’états électroniques peut configurer un format de génération d’états électroniques (ER) pour effectuer le comptage et la synthèse en fonction des données de la sortie de texte déjà générée.</span><span class="sxs-lookup"><span data-stu-id="f7296-105">The following steps explain how a user assigned to the system administrator or electronic reporting developer role can configure an Electronic reporting (ER) format to do counting and summing based on data of the already generated text output.</span></span> <span data-ttu-id="f7296-106">Ces étapes peuvent être effectuées dans la société DEMF.</span><span class="sxs-lookup"><span data-stu-id="f7296-106">These steps can be performed in the DEMF company.</span></span>

<span data-ttu-id="f7296-107">Pour effectuer ces étapes, vous devez d’abord effectuer les étapes de la procédure « ER Configurer le format pour effectuer le comptage et la synthèse (Partie 3 : Utiliser les calculs pour générer la sortie) ».</span><span class="sxs-lookup"><span data-stu-id="f7296-107">To complete these steps, you must first complete the steps in the "ER Configure format to do counting and summing (Part 3: Use computations to make the output)" procedure.</span></span>

<span data-ttu-id="f7296-108">Cette procédure s’applique à une fonction qui a été ajoutée dans la version 1611 de Dynamics 365 for Operations.</span><span class="sxs-lookup"><span data-stu-id="f7296-108">This procedure is for a feature that was added in Dynamics 365 for Operations version 1611.</span></span>


## <a name="test-this-configuration-for-generation-of-the-intrastat-reports"></a><span data-ttu-id="f7296-109">Tester cette configuration pour la génération des états de déclaration d’échanges de biens</span><span class="sxs-lookup"><span data-stu-id="f7296-109">Test this configuration for generation of the Intrastat reports</span></span>
1. <span data-ttu-id="f7296-110">Accédez à Administration d’organisation > Espaces de travail > États électroniques.</span><span class="sxs-lookup"><span data-stu-id="f7296-110">Go to Organization administration > Workspaces > Electronic reporting.</span></span>
2. <span data-ttu-id="f7296-111">Cliquez sur Configurations des états.</span><span class="sxs-lookup"><span data-stu-id="f7296-111">Click Reporting configurations.</span></span>
3. <span data-ttu-id="f7296-112">Dans l’arborescence, développez « Modèle de déclaration d’échanges de biens ».</span><span class="sxs-lookup"><span data-stu-id="f7296-112">In the tree, expand 'Intrastat model'.</span></span>
4. <span data-ttu-id="f7296-113">Dans l’arborescence, développez « Modèle de déclaration d’échanges de biens\Déclaration d’échanges de biens (Allemagne) ».</span><span class="sxs-lookup"><span data-stu-id="f7296-113">In the tree, expand 'Intrastat model\Intrastat (DE)'.</span></span>
5. <span data-ttu-id="f7296-114">Dans l’arborescence, sélectionnez « Modèle de déclaration d’échanges de biens\Déclaration d’échanges de biens (Allemagne)\Déclaration d’échanges de biens (Allemagne) avec comptage et synthèse ».</span><span class="sxs-lookup"><span data-stu-id="f7296-114">In the tree, select 'Intrastat model\Intrastat (DE)\Intrastat (DE) with counting & summing'.</span></span>
6. <span data-ttu-id="f7296-115">Dans le volet Actions, cliquez sur Configurations.</span><span class="sxs-lookup"><span data-stu-id="f7296-115">On the Action Pane, click Configurations.</span></span>
7. <span data-ttu-id="f7296-116">Cliquez sur Paramètres utilisateur.</span><span class="sxs-lookup"><span data-stu-id="f7296-116">Click User parameters.</span></span>
8. <span data-ttu-id="f7296-117">Sélectionnez Oui dans le champ Paramètres d’exécution.</span><span class="sxs-lookup"><span data-stu-id="f7296-117">Select Yes in the Run settings field.</span></span>
9. <span data-ttu-id="f7296-118">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="f7296-118">Click OK.</span></span>
10. <span data-ttu-id="f7296-119">Cliquez sur Modifier.</span><span class="sxs-lookup"><span data-stu-id="f7296-119">Click Edit.</span></span>
11. <span data-ttu-id="f7296-120">Sélectionnez Oui dans le champ Exécuter le brouillon.</span><span class="sxs-lookup"><span data-stu-id="f7296-120">Select Yes in the Run Draft field.</span></span>
12. <span data-ttu-id="f7296-121">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="f7296-121">Click Save.</span></span>
13. <span data-ttu-id="f7296-122">Accédez à Taxe > Paramétrage > Commerce extérieur > Paramètres de commerce extérieur.</span><span class="sxs-lookup"><span data-stu-id="f7296-122">Go to Tax > Setup > Foreign trade > Foreign trade parameters.</span></span>
14. <span data-ttu-id="f7296-123">Développez la section Génération d’états électroniques.</span><span class="sxs-lookup"><span data-stu-id="f7296-123">Expand the Electronic reporting section.</span></span>
15. <span data-ttu-id="f7296-124">Sélectionnez la configuration « Déclaration d’échanges de biens (Allemagne) avec comptage et synthèse ».</span><span class="sxs-lookup"><span data-stu-id="f7296-124">Select the "Intrastat (DE) with counting & summing" configuration.</span></span>
16. <span data-ttu-id="f7296-125">Sélectionnez la configuration « Déclaration d’échanges de biens (Allemagne) avec comptage et synthèse ».</span><span class="sxs-lookup"><span data-stu-id="f7296-125">Select the "Intrastat (DE) with counting & summing" configuration.</span></span>
17. <span data-ttu-id="f7296-126">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="f7296-126">Click Save.</span></span>
18. <span data-ttu-id="f7296-127">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="f7296-127">Close the page.</span></span>
19. <span data-ttu-id="f7296-128">Accédez à Taxe > Déclarations > Commerce extérieur > Déclaration d’échanges de biens.</span><span class="sxs-lookup"><span data-stu-id="f7296-128">Go to Tax > Declarations > Foreign trade > Intrastat.</span></span>
20. <span data-ttu-id="f7296-129">Cliquez sur Résultat.</span><span class="sxs-lookup"><span data-stu-id="f7296-129">Click Output.</span></span>
21. <span data-ttu-id="f7296-130">Cliquez sur État.</span><span class="sxs-lookup"><span data-stu-id="f7296-130">Click Report.</span></span>
    * <span data-ttu-id="f7296-131">Exécutez le processus de génération d’états de déclaration d’échanges de biens.</span><span class="sxs-lookup"><span data-stu-id="f7296-131">Run the Intrastat report generation process.</span></span>  
22. <span data-ttu-id="f7296-132">Dans le champ Date de début, définissez la date sur « 01-01-2000 ».</span><span class="sxs-lookup"><span data-stu-id="f7296-132">In the From date field, set the date to '2000-01-01'.</span></span>
    * <span data-ttu-id="f7296-133">Définissez les dates de début et de fin de la période de déclaration qui incluent celles existantes dans les transactions du formulaire.</span><span class="sxs-lookup"><span data-stu-id="f7296-133">Define start and end dates for the reporting period that include the existing on the form transactions.</span></span>  
23. <span data-ttu-id="f7296-134">Dans le champ Date de fin, définissez la date sur « 31-12-2022 ».</span><span class="sxs-lookup"><span data-stu-id="f7296-134">In the To date field, set the date to '2022-12-31'.</span></span>
    * <span data-ttu-id="f7296-135">Définissez les dates de début et de fin de la période de déclaration qui incluent celles existantes dans les transactions du formulaire.</span><span class="sxs-lookup"><span data-stu-id="f7296-135">Define start and end dates for the reporting period that include the existing on the form transactions.</span></span>  
24. <span data-ttu-id="f7296-136">Dans le champ Direction, sélectionnez « Arrivées ».</span><span class="sxs-lookup"><span data-stu-id="f7296-136">In the Direction field, select 'Arrivals'.</span></span>
25. <span data-ttu-id="f7296-137">Sélectionnez Oui dans le champ Générer un fichier.</span><span class="sxs-lookup"><span data-stu-id="f7296-137">Select Yes in the Generate file field.</span></span>
26. <span data-ttu-id="f7296-138">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="f7296-138">Click OK.</span></span>
    * <span data-ttu-id="f7296-139">Examinez la sortie créée avec les lignes de synthèse à la fin.</span><span class="sxs-lookup"><span data-stu-id="f7296-139">Review the created output with the summary lines in the end.</span></span>  
27. <span data-ttu-id="f7296-140">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="f7296-140">Click New.</span></span>
28. <span data-ttu-id="f7296-141">Dans la liste, marquez la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="f7296-141">In the list, mark the selected row.</span></span>
29. <span data-ttu-id="f7296-142">Dans le champ Direction, sélectionnez « Répartitions ».</span><span class="sxs-lookup"><span data-stu-id="f7296-142">In the Direction field, select 'Dispatches'.</span></span>
30. <span data-ttu-id="f7296-143">Entrez ou sélectionnez une valeur dans le champ Numéro d’article.</span><span class="sxs-lookup"><span data-stu-id="f7296-143">In the Item number field, enter or select a value.</span></span>
31. <span data-ttu-id="f7296-144">Saisissez ou sélectionnez une valeur dans le champ Marchandise.</span><span class="sxs-lookup"><span data-stu-id="f7296-144">In the Commodity field, enter or select a value.</span></span>
32. <span data-ttu-id="f7296-145">Définissez le poids sur « 10 ».</span><span class="sxs-lookup"><span data-stu-id="f7296-145">Set Weight to '10'.</span></span>
33. <span data-ttu-id="f7296-146">Définissez le montant de la facture sur « 10000 »</span><span class="sxs-lookup"><span data-stu-id="f7296-146">Set Invoice amount to '10000'.</span></span>
34. <span data-ttu-id="f7296-147">Définissez le montant statistique sur « 10000 »</span><span class="sxs-lookup"><span data-stu-id="f7296-147">Set Statistical amount to '10000'.</span></span>
35. <span data-ttu-id="f7296-148">Cliquez sur Résultat.</span><span class="sxs-lookup"><span data-stu-id="f7296-148">Click Output.</span></span>
36. <span data-ttu-id="f7296-149">Cliquez sur État.</span><span class="sxs-lookup"><span data-stu-id="f7296-149">Click Report.</span></span>
37. <span data-ttu-id="f7296-150">Dans le champ Direction, sélectionnez « Répartitions ».</span><span class="sxs-lookup"><span data-stu-id="f7296-150">In the Direction field, select 'Dispatches'.</span></span>
38. <span data-ttu-id="f7296-151">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="f7296-151">Click OK.</span></span>
    * <span data-ttu-id="f7296-152">Examinez la sortie créée avec les lignes de synthèse à la fin.</span><span class="sxs-lookup"><span data-stu-id="f7296-152">Review the created output with the summary lines in the end.</span></span> <span data-ttu-id="f7296-153">Notez qu’elle a été modifiée par rapport à la première exécution.</span><span class="sxs-lookup"><span data-stu-id="f7296-153">Note that it has been changed in comparison to the first run.</span></span>  

## <a name="run-this-configuration-in-debug-mode-to-review-the-collected-counting--summing-data"></a><span data-ttu-id="f7296-154">Exécuter cette configuration en mode débogage pour examiner les données de comptage et de synthèse collectées</span><span class="sxs-lookup"><span data-stu-id="f7296-154">Run this configuration in debug mode to review the collected counting & summing data</span></span>
1. <span data-ttu-id="f7296-155">Accédez à Administration d’organisation > États électroniques > Configurations.</span><span class="sxs-lookup"><span data-stu-id="f7296-155">Go to Organization administration > Electronic reporting > Configurations.</span></span>
2. <span data-ttu-id="f7296-156">Dans l’arborescence, développez « Modèle de déclaration d’échanges de biens ».</span><span class="sxs-lookup"><span data-stu-id="f7296-156">In the tree, expand 'Intrastat model'.</span></span>
3. <span data-ttu-id="f7296-157">Dans l’arborescence, développez « Modèle de déclaration d’échanges de biens\Déclaration d’échanges de biens (Allemagne) ».</span><span class="sxs-lookup"><span data-stu-id="f7296-157">In the tree, expand 'Intrastat model\Intrastat (DE)'.</span></span>
4. <span data-ttu-id="f7296-158">Dans l’arborescence, sélectionnez « Modèle de déclaration d’échanges de biens\Déclaration d’échanges de biens (Allemagne)\Déclaration d’échanges de biens (Allemagne) avec comptage et synthèse ».</span><span class="sxs-lookup"><span data-stu-id="f7296-158">In the tree, select 'Intrastat model\Intrastat (DE)\Intrastat (DE) with counting & summing'.</span></span>
5. <span data-ttu-id="f7296-159">Dans le volet Actions, cliquez sur Configurations.</span><span class="sxs-lookup"><span data-stu-id="f7296-159">On the Action Pane, click Configurations.</span></span>
6. <span data-ttu-id="f7296-160">Cliquez sur Paramètres utilisateur.</span><span class="sxs-lookup"><span data-stu-id="f7296-160">Click User parameters.</span></span>
7. <span data-ttu-id="f7296-161">Sélectionnez Oui dans le champ Exécuter en mode débogage.</span><span class="sxs-lookup"><span data-stu-id="f7296-161">Select Yes in the Run in debug mode field.</span></span>
8. <span data-ttu-id="f7296-162">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="f7296-162">Click OK.</span></span>
9. <span data-ttu-id="f7296-163">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="f7296-163">Close the page.</span></span>
10. <span data-ttu-id="f7296-164">Accédez à Taxe > Déclarations > Commerce extérieur > Déclaration d’échanges de biens.</span><span class="sxs-lookup"><span data-stu-id="f7296-164">Go to Tax > Declarations > Foreign trade > Intrastat.</span></span>
11. <span data-ttu-id="f7296-165">Cliquez sur Résultat.</span><span class="sxs-lookup"><span data-stu-id="f7296-165">Click Output.</span></span>
12. <span data-ttu-id="f7296-166">Cliquez sur État.</span><span class="sxs-lookup"><span data-stu-id="f7296-166">Click Report.</span></span>
13. <span data-ttu-id="f7296-167">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="f7296-167">Click OK.</span></span>
14. <span data-ttu-id="f7296-168">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="f7296-168">Close the page.</span></span>
15. <span data-ttu-id="f7296-169">Accédez à Administration d’organisation > États électroniques > Configurations.</span><span class="sxs-lookup"><span data-stu-id="f7296-169">Go to Organization administration > Electronic reporting > Configurations.</span></span>
16. <span data-ttu-id="f7296-170">Dans l’arborescence, développez « Modèle de déclaration d’échanges de biens ».</span><span class="sxs-lookup"><span data-stu-id="f7296-170">In the tree, expand 'Intrastat model'.</span></span>
17. <span data-ttu-id="f7296-171">Dans l’arborescence, développez « Modèle de déclaration d’échanges de biens\Déclaration d’échanges de biens (Allemagne) ».</span><span class="sxs-lookup"><span data-stu-id="f7296-171">In the tree, expand 'Intrastat model\Intrastat (DE)'.</span></span>
18. <span data-ttu-id="f7296-172">Dans l’arborescence, sélectionnez « Modèle de déclaration d’échanges de biens\Déclaration d’échanges de biens (Allemagne)\Déclaration d’échanges de biens (Allemagne) avec comptage et synthèse ».</span><span class="sxs-lookup"><span data-stu-id="f7296-172">In the tree, select 'Intrastat model\Intrastat (DE)\Intrastat (DE) with counting & summing'.</span></span>
19. <span data-ttu-id="f7296-173">Cliquez sur Journaux de débogage.</span><span class="sxs-lookup"><span data-stu-id="f7296-173">Click Debug logs.</span></span>
    * <span data-ttu-id="f7296-174">Notez qu’un enregistrement du journal de débogage a été créé pour le processus d’exécution de la configuration sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="f7296-174">Note that a debug log record has been created for the execution process of the selected configuration.</span></span>  
20. <span data-ttu-id="f7296-175">Cliquez Joindre.</span><span class="sxs-lookup"><span data-stu-id="f7296-175">Click Attach.</span></span>
21. <span data-ttu-id="f7296-176">Cliquez sur Ouvrir.</span><span class="sxs-lookup"><span data-stu-id="f7296-176">Click Open.</span></span>
    * <span data-ttu-id="f7296-177">Examinez le fichier XML créé qui contient les détails de comptage et de synthèse qui ont été collectés lors de l’exécution de la configuration sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="f7296-177">Review the created XML file that contains counting and summing details that were collected during the execution of the selected configuration.</span></span>  



[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]