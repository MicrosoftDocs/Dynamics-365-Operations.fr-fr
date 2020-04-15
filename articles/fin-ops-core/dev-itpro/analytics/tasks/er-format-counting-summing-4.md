---
title: ER Configurer le format pour effectuer le comptage et la synthèse (Partie 4 - Exécuter le format)
description: Les étapes suivantes expliquent comment un utilisateur affecté au rôle d'administrateur système ou de développeur d'états électroniques peut configurer un format de génération d'états électroniques (ER) pour effectuer le comptage et la synthèse en fonction des données de la sortie de texte déjà générée.
author: NickSelin
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ERWorkspace, ERSolutionTable, IntrastatParameters, Intrastat, InventItemIdLookupSimple, IntrastatCommodityLookup, ERFormatMappingRunLogTable, DocuView
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: b89d08d8f6a4223eb592ffa2b918504839e5287b
ms.sourcegitcommit: 57e1dafa186fec77ddd8ba9425d238e36e0f0998
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/18/2020
ms.locfileid: "3142407"
---
# <a name="er-configure-format-to-do-counting-and-summing-part-4---run-format"></a><span data-ttu-id="1386e-103">ER Configurer le format pour effectuer le comptage et la synthèse (Partie 4 - Exécuter le format)</span><span class="sxs-lookup"><span data-stu-id="1386e-103">ER Configure format to do counting and summing (Part 4 - Run format)</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="1386e-104">Les étapes suivantes expliquent comment un utilisateur affecté au rôle d'administrateur système ou de développeur d'états électroniques peut configurer un format de génération d'états électroniques (ER) pour effectuer le comptage et la synthèse en fonction des données de la sortie de texte déjà générée.</span><span class="sxs-lookup"><span data-stu-id="1386e-104">The following steps explain how a user assigned to the system administrator or electronic reporting developer role can configure an Electronic reporting (ER) format to do counting and summing based on data of the already generated text output.</span></span> <span data-ttu-id="1386e-105">Ces étapes peuvent être effectuées dans la société DEMF.</span><span class="sxs-lookup"><span data-stu-id="1386e-105">These steps can be performed in the DEMF company.</span></span>

<span data-ttu-id="1386e-106">Pour effectuer ces étapes, vous devez d'abord effectuer les étapes de la procédure « ER Configurer le format pour effectuer le comptage et la synthèse (Partie 3 : Utiliser les calculs pour générer la sortie) ».</span><span class="sxs-lookup"><span data-stu-id="1386e-106">To complete these steps, you must first complete the steps in the "ER Configure format to do counting and summing (Part 3: Use computations to make the output)" procedure.</span></span>

<span data-ttu-id="1386e-107">Cette procédure s'applique à une fonction qui a été ajoutée dans la version 1611 de Dynamics 365 for Operations.</span><span class="sxs-lookup"><span data-stu-id="1386e-107">This procedure is for a feature that was added in Dynamics 365 for Operations version 1611.</span></span>


## <a name="test-this-configuration-for-generation-of-the-intrastat-reports"></a><span data-ttu-id="1386e-108">Tester cette configuration pour la génération des états de déclaration d'échanges de biens</span><span class="sxs-lookup"><span data-stu-id="1386e-108">Test this configuration for generation of the Intrastat reports</span></span>
1. <span data-ttu-id="1386e-109">Accédez à Administration d'organisation > Espaces de travail > États électroniques.</span><span class="sxs-lookup"><span data-stu-id="1386e-109">Go to Organization administration > Workspaces > Electronic reporting.</span></span>
2. <span data-ttu-id="1386e-110">Cliquez sur Configurations des états.</span><span class="sxs-lookup"><span data-stu-id="1386e-110">Click Reporting configurations.</span></span>
3. <span data-ttu-id="1386e-111">Dans l'arborescence, développez « Modèle de déclaration d'échanges de biens ».</span><span class="sxs-lookup"><span data-stu-id="1386e-111">In the tree, expand 'Intrastat model'.</span></span>
4. <span data-ttu-id="1386e-112">Dans l'arborescence, développez « Modèle de déclaration d'échanges de biens\Déclaration d'échanges de biens (Allemagne) ».</span><span class="sxs-lookup"><span data-stu-id="1386e-112">In the tree, expand 'Intrastat model\Intrastat (DE)'.</span></span>
5. <span data-ttu-id="1386e-113">Dans l'arborescence, sélectionnez « Modèle de déclaration d'échanges de biens\Déclaration d'échanges de biens (Allemagne)\Déclaration d'échanges de biens (Allemagne) avec comptage et synthèse ».</span><span class="sxs-lookup"><span data-stu-id="1386e-113">In the tree, select 'Intrastat model\Intrastat (DE)\Intrastat (DE) with counting & summing'.</span></span>
6. <span data-ttu-id="1386e-114">Dans le volet Actions, cliquez sur Configurations.</span><span class="sxs-lookup"><span data-stu-id="1386e-114">On the Action Pane, click Configurations.</span></span>
7. <span data-ttu-id="1386e-115">Cliquez sur Paramètres utilisateur.</span><span class="sxs-lookup"><span data-stu-id="1386e-115">Click User parameters.</span></span>
8. <span data-ttu-id="1386e-116">Sélectionnez Oui dans le champ Paramètres d'exécution.</span><span class="sxs-lookup"><span data-stu-id="1386e-116">Select Yes in the Run settings field.</span></span>
9. <span data-ttu-id="1386e-117">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="1386e-117">Click OK.</span></span>
10. <span data-ttu-id="1386e-118">Cliquez sur Modifier.</span><span class="sxs-lookup"><span data-stu-id="1386e-118">Click Edit.</span></span>
11. <span data-ttu-id="1386e-119">Sélectionnez Oui dans le champ Exécuter le brouillon.</span><span class="sxs-lookup"><span data-stu-id="1386e-119">Select Yes in the Run Draft field.</span></span>
12. <span data-ttu-id="1386e-120">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="1386e-120">Click Save.</span></span>
13. <span data-ttu-id="1386e-121">Accédez à Taxe > Paramétrage > Commerce extérieur > Paramètres de commerce extérieur.</span><span class="sxs-lookup"><span data-stu-id="1386e-121">Go to Tax > Setup > Foreign trade > Foreign trade parameters.</span></span>
14. <span data-ttu-id="1386e-122">Développez la section Génération d'états électroniques.</span><span class="sxs-lookup"><span data-stu-id="1386e-122">Expand the Electronic reporting section.</span></span>
15. <span data-ttu-id="1386e-123">Sélectionnez la configuration « Déclaration d'échanges de biens (Allemagne) avec comptage et synthèse ».</span><span class="sxs-lookup"><span data-stu-id="1386e-123">Select the "Intrastat (DE) with counting & summing" configuration.</span></span>
16. <span data-ttu-id="1386e-124">Sélectionnez la configuration « Déclaration d'échanges de biens (Allemagne) avec comptage et synthèse ».</span><span class="sxs-lookup"><span data-stu-id="1386e-124">Select the "Intrastat (DE) with counting & summing" configuration.</span></span>
17. <span data-ttu-id="1386e-125">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="1386e-125">Click Save.</span></span>
18. <span data-ttu-id="1386e-126">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="1386e-126">Close the page.</span></span>
19. <span data-ttu-id="1386e-127">Accédez à Taxe > Déclarations > Commerce extérieur > Déclaration d'échanges de biens.</span><span class="sxs-lookup"><span data-stu-id="1386e-127">Go to Tax > Declarations > Foreign trade > Intrastat.</span></span>
20. <span data-ttu-id="1386e-128">Cliquez sur Résultat.</span><span class="sxs-lookup"><span data-stu-id="1386e-128">Click Output.</span></span>
21. <span data-ttu-id="1386e-129">Cliquez sur État.</span><span class="sxs-lookup"><span data-stu-id="1386e-129">Click Report.</span></span>
    * <span data-ttu-id="1386e-130">Exécutez le processus de génération d'états de déclaration d'échanges de biens.</span><span class="sxs-lookup"><span data-stu-id="1386e-130">Run the Intrastat report generation process.</span></span>  
22. <span data-ttu-id="1386e-131">Dans le champ Date de début, définissez la date sur « 01-01-2000 ».</span><span class="sxs-lookup"><span data-stu-id="1386e-131">In the From date field, set the date to '2000-01-01'.</span></span>
    * <span data-ttu-id="1386e-132">Définissez les dates de début et de fin de la période de déclaration qui incluent celles existantes dans les transactions du formulaire.</span><span class="sxs-lookup"><span data-stu-id="1386e-132">Define start and end dates for the reporting period that include the existing on the form transactions.</span></span>  
23. <span data-ttu-id="1386e-133">Dans le champ Date de fin, définissez la date sur « 31-12-2022 ».</span><span class="sxs-lookup"><span data-stu-id="1386e-133">In the To date field, set the date to '2022-12-31'.</span></span>
    * <span data-ttu-id="1386e-134">Définissez les dates de début et de fin de la période de déclaration qui incluent celles existantes dans les transactions du formulaire.</span><span class="sxs-lookup"><span data-stu-id="1386e-134">Define start and end dates for the reporting period that include the existing on the form transactions.</span></span>  
24. <span data-ttu-id="1386e-135">Dans le champ Direction, sélectionnez « Arrivées ».</span><span class="sxs-lookup"><span data-stu-id="1386e-135">In the Direction field, select 'Arrivals'.</span></span>
25. <span data-ttu-id="1386e-136">Sélectionnez Oui dans le champ Générer un fichier.</span><span class="sxs-lookup"><span data-stu-id="1386e-136">Select Yes in the Generate file field.</span></span>
26. <span data-ttu-id="1386e-137">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="1386e-137">Click OK.</span></span>
    * <span data-ttu-id="1386e-138">Examinez la sortie créée avec les lignes de synthèse à la fin.</span><span class="sxs-lookup"><span data-stu-id="1386e-138">Review the created output with the summary lines in the end.</span></span>  
27. <span data-ttu-id="1386e-139">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="1386e-139">Click New.</span></span>
28. <span data-ttu-id="1386e-140">Dans la liste, marquez la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="1386e-140">In the list, mark the selected row.</span></span>
29. <span data-ttu-id="1386e-141">Dans le champ Direction, sélectionnez « Répartitions ».</span><span class="sxs-lookup"><span data-stu-id="1386e-141">In the Direction field, select 'Dispatches'.</span></span>
30. <span data-ttu-id="1386e-142">Entrez ou sélectionnez une valeur dans le champ Numéro d'article.</span><span class="sxs-lookup"><span data-stu-id="1386e-142">In the Item number field, enter or select a value.</span></span>
31. <span data-ttu-id="1386e-143">Saisissez ou sélectionnez une valeur dans le champ Marchandise.</span><span class="sxs-lookup"><span data-stu-id="1386e-143">In the Commodity field, enter or select a value.</span></span>
32. <span data-ttu-id="1386e-144">Définissez le poids sur « 10 ».</span><span class="sxs-lookup"><span data-stu-id="1386e-144">Set Weight to '10'.</span></span>
33. <span data-ttu-id="1386e-145">Définissez le montant de la facture sur « 10000 »</span><span class="sxs-lookup"><span data-stu-id="1386e-145">Set Invoice amount to '10000'.</span></span>
34. <span data-ttu-id="1386e-146">Définissez le montant statistique sur « 10000 »</span><span class="sxs-lookup"><span data-stu-id="1386e-146">Set Statistical amount to '10000'.</span></span>
35. <span data-ttu-id="1386e-147">Cliquez sur Résultat.</span><span class="sxs-lookup"><span data-stu-id="1386e-147">Click Output.</span></span>
36. <span data-ttu-id="1386e-148">Cliquez sur État.</span><span class="sxs-lookup"><span data-stu-id="1386e-148">Click Report.</span></span>
37. <span data-ttu-id="1386e-149">Dans le champ Direction, sélectionnez « Répartitions ».</span><span class="sxs-lookup"><span data-stu-id="1386e-149">In the Direction field, select 'Dispatches'.</span></span>
38. <span data-ttu-id="1386e-150">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="1386e-150">Click OK.</span></span>
    * <span data-ttu-id="1386e-151">Examinez la sortie créée avec les lignes de synthèse à la fin.</span><span class="sxs-lookup"><span data-stu-id="1386e-151">Review the created output with the summary lines in the end.</span></span> <span data-ttu-id="1386e-152">Notez qu'elle a été modifiée par rapport à la première exécution.</span><span class="sxs-lookup"><span data-stu-id="1386e-152">Note that it has been changed in comparison to the first run.</span></span>  

## <a name="run-this-configuration-in-debug-mode-to-review-the-collected-counting--summing-data"></a><span data-ttu-id="1386e-153">Exécuter cette configuration en mode débogage pour examiner les données de comptage et de synthèse collectées</span><span class="sxs-lookup"><span data-stu-id="1386e-153">Run this configuration in debug mode to review the collected counting & summing data</span></span>
1. <span data-ttu-id="1386e-154">Accédez à Administration d'organisation > États électroniques > Configurations.</span><span class="sxs-lookup"><span data-stu-id="1386e-154">Go to Organization administration > Electronic reporting > Configurations.</span></span>
2. <span data-ttu-id="1386e-155">Dans l'arborescence, développez « Modèle de déclaration d'échanges de biens ».</span><span class="sxs-lookup"><span data-stu-id="1386e-155">In the tree, expand 'Intrastat model'.</span></span>
3. <span data-ttu-id="1386e-156">Dans l'arborescence, développez « Modèle de déclaration d'échanges de biens\Déclaration d'échanges de biens (Allemagne) ».</span><span class="sxs-lookup"><span data-stu-id="1386e-156">In the tree, expand 'Intrastat model\Intrastat (DE)'.</span></span>
4. <span data-ttu-id="1386e-157">Dans l'arborescence, sélectionnez « Modèle de déclaration d'échanges de biens\Déclaration d'échanges de biens (Allemagne)\Déclaration d'échanges de biens (Allemagne) avec comptage et synthèse ».</span><span class="sxs-lookup"><span data-stu-id="1386e-157">In the tree, select 'Intrastat model\Intrastat (DE)\Intrastat (DE) with counting & summing'.</span></span>
5. <span data-ttu-id="1386e-158">Dans le volet Actions, cliquez sur Configurations.</span><span class="sxs-lookup"><span data-stu-id="1386e-158">On the Action Pane, click Configurations.</span></span>
6. <span data-ttu-id="1386e-159">Cliquez sur Paramètres utilisateur.</span><span class="sxs-lookup"><span data-stu-id="1386e-159">Click User parameters.</span></span>
7. <span data-ttu-id="1386e-160">Sélectionnez Oui dans le champ Exécuter en mode débogage.</span><span class="sxs-lookup"><span data-stu-id="1386e-160">Select Yes in the Run in debug mode field.</span></span>
8. <span data-ttu-id="1386e-161">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="1386e-161">Click OK.</span></span>
9. <span data-ttu-id="1386e-162">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="1386e-162">Close the page.</span></span>
10. <span data-ttu-id="1386e-163">Accédez à Taxe > Déclarations > Commerce extérieur > Déclaration d'échanges de biens.</span><span class="sxs-lookup"><span data-stu-id="1386e-163">Go to Tax > Declarations > Foreign trade > Intrastat.</span></span>
11. <span data-ttu-id="1386e-164">Cliquez sur Résultat.</span><span class="sxs-lookup"><span data-stu-id="1386e-164">Click Output.</span></span>
12. <span data-ttu-id="1386e-165">Cliquez sur État.</span><span class="sxs-lookup"><span data-stu-id="1386e-165">Click Report.</span></span>
13. <span data-ttu-id="1386e-166">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="1386e-166">Click OK.</span></span>
14. <span data-ttu-id="1386e-167">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="1386e-167">Close the page.</span></span>
15. <span data-ttu-id="1386e-168">Accédez à Administration d'organisation > États électroniques > Configurations.</span><span class="sxs-lookup"><span data-stu-id="1386e-168">Go to Organization administration > Electronic reporting > Configurations.</span></span>
16. <span data-ttu-id="1386e-169">Dans l'arborescence, développez « Modèle de déclaration d'échanges de biens ».</span><span class="sxs-lookup"><span data-stu-id="1386e-169">In the tree, expand 'Intrastat model'.</span></span>
17. <span data-ttu-id="1386e-170">Dans l'arborescence, développez « Modèle de déclaration d'échanges de biens\Déclaration d'échanges de biens (Allemagne) ».</span><span class="sxs-lookup"><span data-stu-id="1386e-170">In the tree, expand 'Intrastat model\Intrastat (DE)'.</span></span>
18. <span data-ttu-id="1386e-171">Dans l'arborescence, sélectionnez « Modèle de déclaration d'échanges de biens\Déclaration d'échanges de biens (Allemagne)\Déclaration d'échanges de biens (Allemagne) avec comptage et synthèse ».</span><span class="sxs-lookup"><span data-stu-id="1386e-171">In the tree, select 'Intrastat model\Intrastat (DE)\Intrastat (DE) with counting & summing'.</span></span>
19. <span data-ttu-id="1386e-172">Cliquez sur Journaux de débogage.</span><span class="sxs-lookup"><span data-stu-id="1386e-172">Click Debug logs.</span></span>
    * <span data-ttu-id="1386e-173">Notez qu'un enregistrement du journal de débogage a été créé pour le processus d'exécution de la configuration sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="1386e-173">Note that a debug log record has been created for the execution process of the selected configuration.</span></span>  
20. <span data-ttu-id="1386e-174">Cliquez Joindre.</span><span class="sxs-lookup"><span data-stu-id="1386e-174">Click Attach.</span></span>
21. <span data-ttu-id="1386e-175">Cliquez sur Ouvrir.</span><span class="sxs-lookup"><span data-stu-id="1386e-175">Click Open.</span></span>
    * <span data-ttu-id="1386e-176">Examinez le fichier XML créé qui contient les détails de comptage et de synthèse qui ont été collectés lors de l'exécution de la configuration sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="1386e-176">Review the created XML file that contains counting and summing details that were collected during the execution of the selected configuration.</span></span>  

