---
title: Analyser les résultats des questionnaires
description: Les statistiques de questionnaire permettent de calculer les moyennes, les totaux et les pourcentages selon un ensemble d'informations démographiques.
author: andreabichsel
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: KMQuestionnaireStatistics, KMQuestionnaireStatisticsLine
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 9d3b13ef7eda9943af35bbb37e3059dd81aa6365
ms.sourcegitcommit: 40163705a134c9874fd33be80c7ae59ccce22c21
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/03/2020
ms.locfileid: "3009060"
---
# <a name="analyzing-questionnaire-results"></a><span data-ttu-id="ad173-103">Analyser les résultats des questionnaires</span><span class="sxs-lookup"><span data-stu-id="ad173-103">Analyzing questionnaire results</span></span>



<span data-ttu-id="ad173-104">Les statistiques de questionnaire permettent de calculer les moyennes, les totaux et les pourcentages selon un ensemble d'informations démographiques.</span><span class="sxs-lookup"><span data-stu-id="ad173-104">Questionnaire statistics can be used to calculate averages, totals, and percentages based on a set of demographic data.</span></span> <span data-ttu-id="ad173-105">Pour démarrer cette procédure, accédez à Questionnaire > Afficher et analyser les résultats > Statistiques de questionnaire.</span><span class="sxs-lookup"><span data-stu-id="ad173-105">To begin this procedure, go to Questionnaire > View and analyze results > Questionnaire statistics.</span></span> <span data-ttu-id="ad173-106">Les données fictives utilisées pour créer cette procédure correspondent à la société USMF.</span><span class="sxs-lookup"><span data-stu-id="ad173-106">The demo data company used to create this procedure is USMF.</span></span>


## <a name="create-a-questionnaire-statistics-record"></a><span data-ttu-id="ad173-107">Créer des résultats des statistiques de questionnaire</span><span class="sxs-lookup"><span data-stu-id="ad173-107">Create a Questionnaire statistics record</span></span>
1. <span data-ttu-id="ad173-108">Allez dans Statistiques de questionnaire.</span><span class="sxs-lookup"><span data-stu-id="ad173-108">Go to Questionnaire statistics.</span></span>
2. <span data-ttu-id="ad173-109">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="ad173-109">Click New.</span></span>
3. <span data-ttu-id="ad173-110">Dans la liste, marquez la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="ad173-110">In the list, mark the selected row.</span></span>
4. <span data-ttu-id="ad173-111">Tapez une valeur dans le champ Statistiques.</span><span class="sxs-lookup"><span data-stu-id="ad173-111">In the Statistics field, type a value.</span></span>
5. <span data-ttu-id="ad173-112">Tapez une valeur dans le champ Description.</span><span class="sxs-lookup"><span data-stu-id="ad173-112">In the Description field, type a value.</span></span>
6. <span data-ttu-id="ad173-113">Dans le champ Questionnaire, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="ad173-113">In the Questionnaire field, click the drop-down button to open the lookup.</span></span>
7. <span data-ttu-id="ad173-114">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="ad173-114">In the list, click the link in the selected row.</span></span>
8. <span data-ttu-id="ad173-115">Cliquez sur l'onglet Général.</span><span class="sxs-lookup"><span data-stu-id="ad173-115">Click the General tab.</span></span>
    * <span data-ttu-id="ad173-116">Indiquez si vous voulez inclure des résultats anonymes ou des résultats provenant des collaborateurs, des contacts et des candidats.</span><span class="sxs-lookup"><span data-stu-id="ad173-116">Select if you want to include anonymous results or results from workers, contacts, and applicants.</span></span>  
9. <span data-ttu-id="ad173-117">Activez ou désactivez la case à cocher Collaborateur.</span><span class="sxs-lookup"><span data-stu-id="ad173-117">Select or clear the Worker check box.</span></span>
    * <span data-ttu-id="ad173-118">Si vous affichez les résultats par ancienneté ou par âge, spécifiez les intervalles que vous voulez utiliser pour regrouper les résultats.</span><span class="sxs-lookup"><span data-stu-id="ad173-118">If you will be viewing the results by seniority or age, specify the intervals that you would like to use for grouping the results.</span></span>  
    * <span data-ttu-id="ad173-119">Si vous entrez 5 comme intervalle d'âges, les résultats seront regroupés par intervalles de cinq ans.</span><span class="sxs-lookup"><span data-stu-id="ad173-119">Entering a 5 for the age interval will group the results based on five-year age intervals.</span></span>  
10. <span data-ttu-id="ad173-120">Entrez un numéro dans le champ Âge.</span><span class="sxs-lookup"><span data-stu-id="ad173-120">In the Age field, enter a number.</span></span>
    * <span data-ttu-id="ad173-121">Indiquez si vous souhaitez effectuer le calcul avec le questionnaire entier, pour chaque groupe de résultats, pour chaque question, ou pour chaque ligne de question.</span><span class="sxs-lookup"><span data-stu-id="ad173-121">Select if you want to run the calculation against the entire questionnaire, for each result group, for each question, or for each question row.</span></span>  
    * <span data-ttu-id="ad173-122">Sélectionnez la manière dont vous souhaitez regrouper les résultats.</span><span class="sxs-lookup"><span data-stu-id="ad173-122">Select how you would like to group the results.</span></span>  
    * <span data-ttu-id="ad173-123">Par exemple, si vous calculez les points moyens par question, vous pouvez souhaiter afficher les questions regroupées par groupe de résultats.</span><span class="sxs-lookup"><span data-stu-id="ad173-123">For example, if you calculate the average points per question, you may want to see the questions grouped by Result group.</span></span>  
    * <span data-ttu-id="ad173-124">Sélectionnez les données sur lesquelles baser le calcul.</span><span class="sxs-lookup"><span data-stu-id="ad173-124">Select the data to base the calculation on.</span></span>  
    * <span data-ttu-id="ad173-125">Par exemple, si vous souhaitez afficher le pourcentage moyen reçu dans le questionnaire entre les collaborateurs par rapport au nombre moyen de points obtenus entre vos collaborateurs.</span><span class="sxs-lookup"><span data-stu-id="ad173-125">For example, if you want to see the average percent received on the questionnaire across your workers versus the average number of points achieved across your workers.</span></span>  
11. <span data-ttu-id="ad173-126">Cliquez sur l'onglet Plage.</span><span class="sxs-lookup"><span data-stu-id="ad173-126">Click the Range tab.</span></span>
    * <span data-ttu-id="ad173-127">Utilisez les plages pour limiter les résultats uniquement à ceux qui répondent à la plage de critères.</span><span class="sxs-lookup"><span data-stu-id="ad173-127">Use ranges to limit your result set to only those meeting the Range criteria.</span></span>  
12. <span data-ttu-id="ad173-128">Cliquez sur l'onglet Regroupement par.</span><span class="sxs-lookup"><span data-stu-id="ad173-128">Click the Grouping by tab.</span></span>
    * <span data-ttu-id="ad173-129">Utilisez les regroupements pour déterminer la manière dont les résultats doivent être affichés.</span><span class="sxs-lookup"><span data-stu-id="ad173-129">Use Groupings to determine how the results should be displayed.</span></span>  
    * <span data-ttu-id="ad173-130">Regroupez par exemple les résultats d'abord par genre, puis par âge.</span><span class="sxs-lookup"><span data-stu-id="ad173-130">For example, group the results first by gender, then by age.</span></span>  
13. <span data-ttu-id="ad173-131">Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="ad173-131">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="ad173-132">Déplacez les regroupements dans le côté sélectionné et les placez-les dans l'ordre souhaité.</span><span class="sxs-lookup"><span data-stu-id="ad173-132">Move the groupings into the Selected side and place them in the desired order.</span></span>  

## <a name="execute-the-statistics-calculation"></a><span data-ttu-id="ad173-133">Exécuter le calcul de statistiques</span><span class="sxs-lookup"><span data-stu-id="ad173-133">Execute the statistics calculation</span></span>
1. <span data-ttu-id="ad173-134">Cliquez sur Exécuter.</span><span class="sxs-lookup"><span data-stu-id="ad173-134">Click Execute.</span></span>
    * <span data-ttu-id="ad173-135">Sélectionnez la fonction de calcul à appliquer sur les résultats.</span><span class="sxs-lookup"><span data-stu-id="ad173-135">Select which calculation function you would like to perform on the results.</span></span>  
    * <span data-ttu-id="ad173-136">Par exemple, calculez les pourcentages moyens entre le questionnaire pour les regroupements sélectionnés ou additionnez les points entre les groupes de résultats pour les regroupements sélectionnés.</span><span class="sxs-lookup"><span data-stu-id="ad173-136">For example, calculate the average percentages across the questionnaire for the selected groupings or total the points across the result groups for the selected groupings.</span></span>  
2. <span data-ttu-id="ad173-137">Activez ou désactivez la case à cocher Supprimer les recherches précédentes.</span><span class="sxs-lookup"><span data-stu-id="ad173-137">Select or clear the Delete previous searches check box.</span></span>
3. <span data-ttu-id="ad173-138">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="ad173-138">Click OK.</span></span>

## <a name="view-the-results-of-the-questionnaire-statistics-run"></a><span data-ttu-id="ad173-139">Afficher les résultats de l'exécution des statistiques de questionnaires.</span><span class="sxs-lookup"><span data-stu-id="ad173-139">View the results of the questionnaire statistics run.</span></span>
1. <span data-ttu-id="ad173-140">Cliquez sur Résultat.</span><span class="sxs-lookup"><span data-stu-id="ad173-140">Click Result.</span></span>
2. <span data-ttu-id="ad173-141">Cliquez sur Résultat.</span><span class="sxs-lookup"><span data-stu-id="ad173-141">Click Result.</span></span>
3. <span data-ttu-id="ad173-142">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="ad173-142">Close the page.</span></span>

