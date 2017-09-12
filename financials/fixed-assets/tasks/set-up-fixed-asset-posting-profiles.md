--- 
title: "Paramétrage de profils de validation d'immobilisation"
description: "Ce guide de tâche va paramétrer les profils de validation d'immobilisation."
author: saraschi2
manager: AnnBe
ms.date: 02/24/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Operations
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: b9766d96d16429d0ce0864695a3157f54cad4054
ms.contentlocale: fr-fr
ms.lasthandoff: 08/29/2017

---
# <a name="set-up-fixed-asset-posting-profiles"></a><span data-ttu-id="276a8-103">Paramétrage de profils de validation d'immobilisation</span><span class="sxs-lookup"><span data-stu-id="276a8-103">Set up fixed asset posting profiles</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="276a8-104">Ce guide de tâche va paramétrer les profils de validation d'immobilisation.</span><span class="sxs-lookup"><span data-stu-id="276a8-104">This task guide will set up Fixed asset posting profiles.</span></span>  <span data-ttu-id="276a8-105">Il utilise le rôle de comptable et les données de démonstration de l'entité juridique USMF.</span><span class="sxs-lookup"><span data-stu-id="276a8-105">It uses the Accountant role and demo data for the USMF legal entity.</span></span>  <span data-ttu-id="276a8-106">Les exemples donnés dans le guide de tâches concernent un profil de validation de base, même s'il faut créer des profils de validation pour les besoins spécifiques de vos plans de comptes et de vos états financiers.</span><span class="sxs-lookup"><span data-stu-id="276a8-106">Examples given in the task guide are for a basic posting profile, though posting profiles must be created for your specific chart of accounts and financial reporting requirements.</span></span>

1. <span data-ttu-id="276a8-107">Accédez à Immobilisations > Paramétrage > Profils de validation d'immobilisation.</span><span class="sxs-lookup"><span data-stu-id="276a8-107">Go to Fixed assets > Setup > Fixed asset posting profiles.</span></span>
2. <span data-ttu-id="276a8-108">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="276a8-108">Click New.</span></span>
3. <span data-ttu-id="276a8-109">Tapez une valeur dans le champ Profil de validation.</span><span class="sxs-lookup"><span data-stu-id="276a8-109">In the Posting profile field, type a value.</span></span>
4. <span data-ttu-id="276a8-110">Dans le champ Description, entrez une valeur.</span><span class="sxs-lookup"><span data-stu-id="276a8-110">In the Description field, type a value.</span></span>
    * <span data-ttu-id="276a8-111">Vous devrez créer un profil de validation pour chaque type de transaction d'immobilisation que vous utiliserez lors de l'utilisation des immobilisations.</span><span class="sxs-lookup"><span data-stu-id="276a8-111">You will need to create a posting profile for each fixed asset transaction type you will be using when working with fixed assets.</span></span>  <span data-ttu-id="276a8-112">Ce guide de tâche débute par le type de transaction d'acquisition.</span><span class="sxs-lookup"><span data-stu-id="276a8-112">This task guide will start with the Acquisition transaction type.</span></span>  
5. <span data-ttu-id="276a8-113">Cliquez sur Ajouter.</span><span class="sxs-lookup"><span data-stu-id="276a8-113">Click Add.</span></span>
6. <span data-ttu-id="276a8-114">Dans le champ Registre, entrez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="276a8-114">In the Book field, enter or select a value.</span></span>
    * <span data-ttu-id="276a8-115">Le champ Regroupements vous permet de définir le profil de validation dans Tableau (un compte défini pour chaque immobilisation) ou Groupe (un compte défini pour chaque groupe d'immobilisations).</span><span class="sxs-lookup"><span data-stu-id="276a8-115">The Groupings field allows you to define the posting profile down to the Table (one account set up for each fixed asset) or Group (one account set up for each fixed asset group).</span></span>  <span data-ttu-id="276a8-116">Pour ce Guide de tâche, je laisserai la valeur définie sur « Tout » pour appliquer le registre spécifié à toutes les immobilisations.</span><span class="sxs-lookup"><span data-stu-id="276a8-116">For this task guide I will leave the value set to “All” to apply to all fixed assets with the specified Book.</span></span>  
7. <span data-ttu-id="276a8-117">Dans le champ Compte principal, spécifiez les valeurs souhaitées.</span><span class="sxs-lookup"><span data-stu-id="276a8-117">In the Main account field, specify the desired values.</span></span>
    * <span data-ttu-id="276a8-118">Pour les acquisitions, vous pouvez entrer un compte de contrepartie ou le laisser vide et le renseigner pour la transaction spécifique.</span><span class="sxs-lookup"><span data-stu-id="276a8-118">For Acquisitions, you can enter an offset account or leave it blank to be filled in for the specific transaction.</span></span>    
8. <span data-ttu-id="276a8-119">Dans le champ Type de transaction, sélectionnez Ajustement d'acquisition.</span><span class="sxs-lookup"><span data-stu-id="276a8-119">In the Transaction type field, select 'Acquisition adjustment'.</span></span>
    * <span data-ttu-id="276a8-120">Pour les transactions d'ajustement d'acquisition, nous utiliserons les mêmes comptes que ceux utilisés pour les transactions d'acquisition.</span><span class="sxs-lookup"><span data-stu-id="276a8-120">For Acquisition adjustment transactions, we will use the same accounts as used for Acquisition transactions.</span></span>  
9. <span data-ttu-id="276a8-121">Cliquez sur Ajouter.</span><span class="sxs-lookup"><span data-stu-id="276a8-121">Click Add.</span></span>
10. <span data-ttu-id="276a8-122">Dans le champ Registre, entrez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="276a8-122">In the Book field, enter or select a value.</span></span>
11. <span data-ttu-id="276a8-123">Dans le champ Compte principal, spécifiez les valeurs souhaitées.</span><span class="sxs-lookup"><span data-stu-id="276a8-123">In the Main account field, specify the desired values.</span></span>
    * <span data-ttu-id="276a8-124">Pour les ajustements d'acquisition, vous pouvez entrer un compte de contrepartie ou le laisser vide et le renseigner pour la transaction spécifique.</span><span class="sxs-lookup"><span data-stu-id="276a8-124">For Acquisition adjustments, you can enter an offset account or leave it blank to be filled in for the specific transaction.</span></span>    
12. <span data-ttu-id="276a8-125">Sélectionnez « Amortissement » dans le champ Type de transaction.</span><span class="sxs-lookup"><span data-stu-id="276a8-125">In the Transaction type field, select 'Depreciation'.</span></span>
13. <span data-ttu-id="276a8-126">Cliquez sur Ajouter.</span><span class="sxs-lookup"><span data-stu-id="276a8-126">Click Add.</span></span>
14. <span data-ttu-id="276a8-127">Dans le champ Registre, entrez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="276a8-127">In the Book field, enter or select a value.</span></span>
15. <span data-ttu-id="276a8-128">Dans le champ Compte principal, spécifiez les valeurs souhaitées.</span><span class="sxs-lookup"><span data-stu-id="276a8-128">In the Main account field, specify the desired values.</span></span>
16. <span data-ttu-id="276a8-129">Spécifiez les valeurs souhaitées dans le champ Compte de contrepartie.</span><span class="sxs-lookup"><span data-stu-id="276a8-129">In the Offset account field, specify the desired values.</span></span>
17. <span data-ttu-id="276a8-130">Sélectionnez « Ajustement de l'amortissement » dans le champ Type de transaction.</span><span class="sxs-lookup"><span data-stu-id="276a8-130">In the Transaction type field, select 'Depreciation adjustment'.</span></span>
    * <span data-ttu-id="276a8-131">Pour les transactions d'ajustement d'amortissement, nous utiliserons les mêmes comptes que ceux utilisés pour les transactions d'amortissement.</span><span class="sxs-lookup"><span data-stu-id="276a8-131">For Depreciation adjustment transactions, we will use the same accounts as used for Depreciation transactions.</span></span>  
18. <span data-ttu-id="276a8-132">Cliquez sur Ajouter.</span><span class="sxs-lookup"><span data-stu-id="276a8-132">Click Add.</span></span>
19. <span data-ttu-id="276a8-133">Dans le champ Registre, entrez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="276a8-133">In the Book field, enter or select a value.</span></span>
20. <span data-ttu-id="276a8-134">Dans le champ Compte principal, spécifiez les valeurs souhaitées.</span><span class="sxs-lookup"><span data-stu-id="276a8-134">In the Main account field, specify the desired values.</span></span>
21. <span data-ttu-id="276a8-135">Spécifiez les valeurs souhaitées dans le champ Compte de contrepartie.</span><span class="sxs-lookup"><span data-stu-id="276a8-135">In the Offset account field, specify the desired values.</span></span>
22. <span data-ttu-id="276a8-136">Sélectionnez « Cession - Vente » dans le champ Type de transaction.</span><span class="sxs-lookup"><span data-stu-id="276a8-136">In the Transaction type field, select 'Disposal - sale'.</span></span>
23. <span data-ttu-id="276a8-137">Cliquez sur Ajouter.</span><span class="sxs-lookup"><span data-stu-id="276a8-137">Click Add.</span></span>
24. <span data-ttu-id="276a8-138">Dans le champ Registre, entrez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="276a8-138">In the Book field, enter or select a value.</span></span>
25. <span data-ttu-id="276a8-139">Dans le champ Compte principal, spécifiez les valeurs souhaitées.</span><span class="sxs-lookup"><span data-stu-id="276a8-139">In the Main account field, specify the desired values.</span></span>
    * <span data-ttu-id="276a8-140">Pour les cessions, vous pouvez entrer un compte de contrepartie ou le laisser vide et le renseigner pour la transaction spécifique.</span><span class="sxs-lookup"><span data-stu-id="276a8-140">For Disposals, you can enter an offset account or leave it blank to be filled in for the specific transaction.</span></span>  
26. <span data-ttu-id="276a8-141">Sélectionnez « Cession - Mise au rebut » dans le champ Type de transaction.</span><span class="sxs-lookup"><span data-stu-id="276a8-141">In the Transaction type field, select 'Disposal - scrap'.</span></span>
    * <span data-ttu-id="276a8-142">Nous utiliserons les mêmes comptes pour la vente de cession et la mise au rebut.</span><span class="sxs-lookup"><span data-stu-id="276a8-142">We will use the same accounts for Disposal sale and Disposal scrap.</span></span>  
27. <span data-ttu-id="276a8-143">Cliquez sur Ajouter.</span><span class="sxs-lookup"><span data-stu-id="276a8-143">Click Add.</span></span>
28. <span data-ttu-id="276a8-144">Dans le champ Registre, entrez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="276a8-144">In the Book field, enter or select a value.</span></span>
29. <span data-ttu-id="276a8-145">Dans le champ Compte principal, spécifiez les valeurs souhaitées.</span><span class="sxs-lookup"><span data-stu-id="276a8-145">In the Main account field, specify the desired values.</span></span>
    * <span data-ttu-id="276a8-146">Pour les cessions, vous pouvez entrer un compte de contrepartie ou le laisser vide et le renseigner pour la transaction spécifique.</span><span class="sxs-lookup"><span data-stu-id="276a8-146">For Disposals, you can enter an offset account or leave it blank to be filled in for the specific transaction.</span></span>  
30. <span data-ttu-id="276a8-147">Développer la section Cession.</span><span class="sxs-lookup"><span data-stu-id="276a8-147">Expand the Disposal section.</span></span>
    * <span data-ttu-id="276a8-148">Vous devez paramétrer des profils de validation de cession pour la vente et la mise au rebut.</span><span class="sxs-lookup"><span data-stu-id="276a8-148">You must set up disposal posting profiles for both sale and scrap.</span></span>  <span data-ttu-id="276a8-149">Nous commencerons par des transactions de cession.</span><span class="sxs-lookup"><span data-stu-id="276a8-149">We will start with disposal sale transactions.</span></span>  
31. <span data-ttu-id="276a8-150">Cliquez sur Ajouter.</span><span class="sxs-lookup"><span data-stu-id="276a8-150">Click Add.</span></span>
32. <span data-ttu-id="276a8-151">Dans le champ Registre, entrez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="276a8-151">In the Book field, enter or select a value.</span></span>
33. <span data-ttu-id="276a8-152">Sélectionnez « Valeur d'acquisition » dans le champ Valider la valeur.</span><span class="sxs-lookup"><span data-stu-id="276a8-152">In the Post value field, select 'Acquisition value'.</span></span>
    * <span data-ttu-id="276a8-153">La valeur d'acquisition prend en compte l'acquisition et les valeurs d'ajustement de l'acquisition pour toutes les années.</span><span class="sxs-lookup"><span data-stu-id="276a8-153">Acquisition value will address Acquisition and Acquisition adjustment values for all years.</span></span>  <span data-ttu-id="276a8-154">Vous pouvez également définir des comptes pour ces types de transactions séparément.</span><span class="sxs-lookup"><span data-stu-id="276a8-154">You can also define accounts for these transaction types separately.</span></span>  
    * <span data-ttu-id="276a8-155">Vous pouvez définir le processus de cession afin d'utiliser différents comptes, selon que la cession débouche sur un profit ou une perte.</span><span class="sxs-lookup"><span data-stu-id="276a8-155">You can set the disposal process to use different accounts depending upon if the disposal results in a gain or loss.</span></span>  <span data-ttu-id="276a8-156">Je définirai le type de prix de vente sur « Tout » pour utiliser les mêmes comptes pour tous les types de cessions.</span><span class="sxs-lookup"><span data-stu-id="276a8-156">I will set the Sales value type to “All” to use the same accounts for all types of disposals.</span></span>  
34. <span data-ttu-id="276a8-157">Dans le champ Compte principal, spécifiez les valeurs souhaitées.</span><span class="sxs-lookup"><span data-stu-id="276a8-157">In the Main account field, specify the desired values.</span></span>
35. <span data-ttu-id="276a8-158">Spécifiez les valeurs souhaitées dans le champ Compte de contrepartie.</span><span class="sxs-lookup"><span data-stu-id="276a8-158">In the Offset account field, specify the desired values.</span></span>
36. <span data-ttu-id="276a8-159">Cliquez sur Ajouter.</span><span class="sxs-lookup"><span data-stu-id="276a8-159">Click Add.</span></span>
37. <span data-ttu-id="276a8-160">Dans le champ Registre, entrez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="276a8-160">In the Book field, enter or select a value.</span></span>
    * <span data-ttu-id="276a8-161">Sélectionnez « Amortissement (exercices précédents) » dans le champ Valider la valeur.</span><span class="sxs-lookup"><span data-stu-id="276a8-161">In the Post value field, select 'Depreciation (prior years)'.</span></span>  
38. <span data-ttu-id="276a8-162">Dans le champ Compte principal, spécifiez les valeurs souhaitées.</span><span class="sxs-lookup"><span data-stu-id="276a8-162">In the Main account field, specify the desired values.</span></span>
39. <span data-ttu-id="276a8-163">Spécifiez les valeurs souhaitées dans le champ Compte de contrepartie.</span><span class="sxs-lookup"><span data-stu-id="276a8-163">In the Offset account field, specify the desired values.</span></span>
40. <span data-ttu-id="276a8-164">Cliquez sur Ajouter.</span><span class="sxs-lookup"><span data-stu-id="276a8-164">Click Add.</span></span>
41. <span data-ttu-id="276a8-165">Dans le champ Registre, entrez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="276a8-165">In the Book field, enter or select a value.</span></span>
42. <span data-ttu-id="276a8-166">Sélectionnez « Amortissement (cet exercice) » dans le champ Valider la valeur.</span><span class="sxs-lookup"><span data-stu-id="276a8-166">In the Post value field, select 'Depreciation (this year)'.</span></span>
43. <span data-ttu-id="276a8-167">Dans le champ Compte principal, spécifiez les valeurs souhaitées.</span><span class="sxs-lookup"><span data-stu-id="276a8-167">In the Main account field, specify the desired values.</span></span>
44. <span data-ttu-id="276a8-168">Spécifiez les valeurs souhaitées dans le champ Compte de contrepartie.</span><span class="sxs-lookup"><span data-stu-id="276a8-168">In the Offset account field, specify the desired values.</span></span>
45. <span data-ttu-id="276a8-169">Cliquez sur Ajouter.</span><span class="sxs-lookup"><span data-stu-id="276a8-169">Click Add.</span></span>
46. <span data-ttu-id="276a8-170">Dans le champ Registre, entrez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="276a8-170">In the Book field, enter or select a value.</span></span>
47. <span data-ttu-id="276a8-171">Sélectionnez « Ajustements de l'amortissement (exercices précédents) » dans le champ Valider la valeur.</span><span class="sxs-lookup"><span data-stu-id="276a8-171">In the Post value field, select 'Depreciation adjustments (prior years)'.</span></span>
48. <span data-ttu-id="276a8-172">Dans le champ Compte principal, spécifiez les valeurs souhaitées.</span><span class="sxs-lookup"><span data-stu-id="276a8-172">In the Main account field, specify the desired values.</span></span>
49. <span data-ttu-id="276a8-173">Spécifiez les valeurs souhaitées dans le champ Compte de contrepartie.</span><span class="sxs-lookup"><span data-stu-id="276a8-173">In the Offset account field, specify the desired values.</span></span>
50. <span data-ttu-id="276a8-174">Cliquez sur Ajouter.</span><span class="sxs-lookup"><span data-stu-id="276a8-174">Click Add.</span></span>
51. <span data-ttu-id="276a8-175">Dans le champ Registre, entrez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="276a8-175">In the Book field, enter or select a value.</span></span>
52. <span data-ttu-id="276a8-176">Sélectionnez « Ajustements de l'amortissement (cet exercice) » dans le champ Valider la valeur.</span><span class="sxs-lookup"><span data-stu-id="276a8-176">In the Post value field, select 'Depreciation adjustments (this year)'.</span></span>
53. <span data-ttu-id="276a8-177">Dans le champ Compte principal, spécifiez les valeurs souhaitées.</span><span class="sxs-lookup"><span data-stu-id="276a8-177">In the Main account field, specify the desired values.</span></span>
54. <span data-ttu-id="276a8-178">Spécifiez les valeurs souhaitées dans le champ Compte de contrepartie.</span><span class="sxs-lookup"><span data-stu-id="276a8-178">In the Offset account field, specify the desired values.</span></span>
55. <span data-ttu-id="276a8-179">Cliquez sur Ajouter.</span><span class="sxs-lookup"><span data-stu-id="276a8-179">Click Add.</span></span>
56. <span data-ttu-id="276a8-180">Dans le champ Registre, entrez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="276a8-180">In the Book field, enter or select a value.</span></span>
57. <span data-ttu-id="276a8-181">Sélectionnez « Valeur nette » dans le champ Valider la valeur.</span><span class="sxs-lookup"><span data-stu-id="276a8-181">In the Post value field, select 'Net book value'.</span></span>
58. <span data-ttu-id="276a8-182">Dans le champ Compte principal, spécifiez les valeurs souhaitées.</span><span class="sxs-lookup"><span data-stu-id="276a8-182">In the Main account field, specify the desired values.</span></span>
59. <span data-ttu-id="276a8-183">Spécifiez les valeurs souhaitées dans le champ Compte de contrepartie.</span><span class="sxs-lookup"><span data-stu-id="276a8-183">In the Offset account field, specify the desired values.</span></span>
60. <span data-ttu-id="276a8-184">Sélectionnez « Rebut » dans le champ Vente ou mise au rebut.</span><span class="sxs-lookup"><span data-stu-id="276a8-184">In the Sale or scrap field, select 'Scrap'.</span></span>
61. <span data-ttu-id="276a8-185">Cliquez sur Ajouter.</span><span class="sxs-lookup"><span data-stu-id="276a8-185">Click Add.</span></span>
62. <span data-ttu-id="276a8-186">Dans le champ Registre, entrez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="276a8-186">In the Book field, enter or select a value.</span></span>
63. <span data-ttu-id="276a8-187">Sélectionnez « Valeur d'acquisition » dans le champ Valider la valeur.</span><span class="sxs-lookup"><span data-stu-id="276a8-187">In the Post value field, select 'Acquisition value'.</span></span>
64. <span data-ttu-id="276a8-188">Dans le champ Compte principal, spécifiez les valeurs souhaitées.</span><span class="sxs-lookup"><span data-stu-id="276a8-188">In the Main account field, specify the desired values.</span></span>
65. <span data-ttu-id="276a8-189">Spécifiez les valeurs souhaitées dans le champ Compte de contrepartie.</span><span class="sxs-lookup"><span data-stu-id="276a8-189">In the Offset account field, specify the desired values.</span></span>
66. <span data-ttu-id="276a8-190">Cliquez sur Ajouter.</span><span class="sxs-lookup"><span data-stu-id="276a8-190">Click Add.</span></span>
67. <span data-ttu-id="276a8-191">Dans le champ Registre, entrez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="276a8-191">In the Book field, enter or select a value.</span></span>
    * <span data-ttu-id="276a8-192">Sélectionnez « Amortissement (exercices précédents) » dans le champ Valider la valeur.</span><span class="sxs-lookup"><span data-stu-id="276a8-192">In Post value field, select 'Depreciation (prior years)'.</span></span>  
68. <span data-ttu-id="276a8-193">Dans le champ Compte principal, spécifiez les valeurs souhaitées.</span><span class="sxs-lookup"><span data-stu-id="276a8-193">In the Main account field, specify the desired values.</span></span>
69. <span data-ttu-id="276a8-194">Spécifiez les valeurs souhaitées dans le champ Compte de contrepartie.</span><span class="sxs-lookup"><span data-stu-id="276a8-194">In the Offset account field, specify the desired values.</span></span>
70. <span data-ttu-id="276a8-195">Cliquez sur Ajouter.</span><span class="sxs-lookup"><span data-stu-id="276a8-195">Click Add.</span></span>
71. <span data-ttu-id="276a8-196">Dans le champ Registre, entrez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="276a8-196">In the Book field, enter or select a value.</span></span>
72. <span data-ttu-id="276a8-197">Sélectionnez « Amortissement (cet exercice) » dans le champ Valider la valeur.</span><span class="sxs-lookup"><span data-stu-id="276a8-197">In the Post value field, select 'Depreciation (this year)'.</span></span>
73. <span data-ttu-id="276a8-198">Dans le champ Compte principal, spécifiez les valeurs souhaitées.</span><span class="sxs-lookup"><span data-stu-id="276a8-198">In the Main account field, specify the desired values.</span></span>
74. <span data-ttu-id="276a8-199">Spécifiez les valeurs souhaitées dans le champ Compte de contrepartie.</span><span class="sxs-lookup"><span data-stu-id="276a8-199">In the Offset account field, specify the desired values.</span></span>
75. <span data-ttu-id="276a8-200">Cliquez sur Ajouter.</span><span class="sxs-lookup"><span data-stu-id="276a8-200">Click Add.</span></span>
76. <span data-ttu-id="276a8-201">Dans le champ Registre, entrez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="276a8-201">In the Book field, enter or select a value.</span></span>
77. <span data-ttu-id="276a8-202">Sélectionnez « Ajustements de l'amortissement (exercices précédents) » dans le champ Valider la valeur.</span><span class="sxs-lookup"><span data-stu-id="276a8-202">In the Post value field, select 'Depreciation adjustments (prior years)'.</span></span>
78. <span data-ttu-id="276a8-203">Dans le champ Compte principal, spécifiez les valeurs souhaitées.</span><span class="sxs-lookup"><span data-stu-id="276a8-203">In the Main account field, specify the desired values.</span></span>
79. <span data-ttu-id="276a8-204">Spécifiez les valeurs souhaitées dans le champ Compte de contrepartie.</span><span class="sxs-lookup"><span data-stu-id="276a8-204">In the Offset account field, specify the desired values.</span></span>
80. <span data-ttu-id="276a8-205">Cliquez sur Ajouter.</span><span class="sxs-lookup"><span data-stu-id="276a8-205">Click Add.</span></span>
81. <span data-ttu-id="276a8-206">Dans le champ Registre, entrez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="276a8-206">In the Book field, enter or select a value.</span></span>
82. <span data-ttu-id="276a8-207">Sélectionnez « Ajustements de l'amortissement (cet exercice) » dans le champ Valider la valeur.</span><span class="sxs-lookup"><span data-stu-id="276a8-207">In the Post value field, select 'Depreciation adjustments (this year)'.</span></span>
83. <span data-ttu-id="276a8-208">Dans le champ Compte principal, spécifiez les valeurs souhaitées.</span><span class="sxs-lookup"><span data-stu-id="276a8-208">In the Main account field, specify the desired values.</span></span>
84. <span data-ttu-id="276a8-209">Spécifiez les valeurs souhaitées dans le champ Compte de contrepartie.</span><span class="sxs-lookup"><span data-stu-id="276a8-209">In the Offset account field, specify the desired values.</span></span>
85. <span data-ttu-id="276a8-210">Cliquez sur Ajouter.</span><span class="sxs-lookup"><span data-stu-id="276a8-210">Click Add.</span></span>
86. <span data-ttu-id="276a8-211">Dans le champ Registre, entrez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="276a8-211">In the Book field, enter or select a value.</span></span>
87. <span data-ttu-id="276a8-212">Sélectionnez « Valeur nette » dans le champ Valider la valeur.</span><span class="sxs-lookup"><span data-stu-id="276a8-212">In the Post value field, select 'Net book value'.</span></span>
88. <span data-ttu-id="276a8-213">Dans le champ Compte principal, spécifiez les valeurs souhaitées.</span><span class="sxs-lookup"><span data-stu-id="276a8-213">In the Main account field, specify the desired values.</span></span>
89. <span data-ttu-id="276a8-214">Spécifiez les valeurs souhaitées dans le champ Compte de contrepartie.</span><span class="sxs-lookup"><span data-stu-id="276a8-214">In the Offset account field, specify the desired values.</span></span>


