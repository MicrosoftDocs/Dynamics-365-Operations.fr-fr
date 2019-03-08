---
title: Paramétrage de profils de validation d'immobilisation
description: Ce guide de tâche va paramétrer les profils de validation d'immobilisation.
author: saraschi2
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: AssetPosting
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 286c8732c1f2c92d0f16582b0b9de41990280e5a
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/29/2019
ms.locfileid: "351100"
---
# <a name="set-up-fixed-asset-posting-profiles"></a><span data-ttu-id="31b18-103">Paramétrage de profils de validation d'immobilisation</span><span class="sxs-lookup"><span data-stu-id="31b18-103">Set up fixed asset posting profiles</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="31b18-104">Ce guide de tâche va paramétrer les profils de validation d'immobilisation.</span><span class="sxs-lookup"><span data-stu-id="31b18-104">This task guide will set up Fixed asset posting profiles.</span></span>  <span data-ttu-id="31b18-105">Il utilise le rôle de comptable et les données de démonstration de l'entité juridique USMF.</span><span class="sxs-lookup"><span data-stu-id="31b18-105">It uses the Accountant role and demo data for the USMF legal entity.</span></span>  <span data-ttu-id="31b18-106">Les exemples donnés dans le guide de tâches concernent un profil de validation de base, même s'il faut créer des profils de validation pour les besoins spécifiques de vos plans de comptes et de vos états financiers.</span><span class="sxs-lookup"><span data-stu-id="31b18-106">Examples given in the task guide are for a basic posting profile, though posting profiles must be created for your specific chart of accounts and financial reporting requirements.</span></span>

1. <span data-ttu-id="31b18-107">Accédez à Immobilisations > Paramétrage > Profils de validation d'immobilisation.</span><span class="sxs-lookup"><span data-stu-id="31b18-107">Go to Fixed assets > Setup > Fixed asset posting profiles.</span></span>
2. <span data-ttu-id="31b18-108">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="31b18-108">Click New.</span></span>
3. <span data-ttu-id="31b18-109">Tapez une valeur dans le champ Profil de validation.</span><span class="sxs-lookup"><span data-stu-id="31b18-109">In the Posting profile field, type a value.</span></span>
4. <span data-ttu-id="31b18-110">Dans le champ Description, entrez une valeur.</span><span class="sxs-lookup"><span data-stu-id="31b18-110">In the Description field, type a value.</span></span>
    * <span data-ttu-id="31b18-111">Vous devrez créer un profil de validation pour chaque type de transaction d'immobilisation que vous utiliserez lors de l'utilisation des immobilisations.</span><span class="sxs-lookup"><span data-stu-id="31b18-111">You will need to create a posting profile for each fixed asset transaction type you will be using when working with fixed assets.</span></span>  <span data-ttu-id="31b18-112">Ce guide de tâche débute par le type de transaction d'acquisition.</span><span class="sxs-lookup"><span data-stu-id="31b18-112">This task guide will start with the Acquisition transaction type.</span></span>  
5. <span data-ttu-id="31b18-113">Cliquez sur Ajouter.</span><span class="sxs-lookup"><span data-stu-id="31b18-113">Click Add.</span></span>
6. <span data-ttu-id="31b18-114">Dans le champ Registre, entrez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="31b18-114">In the Book field, enter or select a value.</span></span>
    * <span data-ttu-id="31b18-115">Le champ Regroupements vous permet de définir le profil de validation dans Tableau (un compte défini pour chaque immobilisation) ou Groupe (un compte défini pour chaque groupe d'immobilisations).</span><span class="sxs-lookup"><span data-stu-id="31b18-115">The Groupings field allows you to define the posting profile down to the Table (one account set up for each fixed asset) or Group (one account set up for each fixed asset group).</span></span>  <span data-ttu-id="31b18-116">Pour ce Guide de tâche, je laisserai la valeur définie sur « Tout » pour appliquer le registre spécifié à toutes les immobilisations.</span><span class="sxs-lookup"><span data-stu-id="31b18-116">For this task guide I will leave the value set to “All” to apply to all fixed assets with the specified Book.</span></span>  
7. <span data-ttu-id="31b18-117">Dans le champ Compte principal, spécifiez les valeurs souhaitées.</span><span class="sxs-lookup"><span data-stu-id="31b18-117">In the Main account field, specify the desired values.</span></span>
    * <span data-ttu-id="31b18-118">Pour les acquisitions, vous pouvez entrer un compte de contrepartie ou le laisser vide et le renseigner pour la transaction spécifique.</span><span class="sxs-lookup"><span data-stu-id="31b18-118">For Acquisitions, you can enter an offset account or leave it blank to be filled in for the specific transaction.</span></span>    
8. <span data-ttu-id="31b18-119">Dans le champ Type de transaction, sélectionnez Ajustement d'acquisition.</span><span class="sxs-lookup"><span data-stu-id="31b18-119">In the Transaction type field, select 'Acquisition adjustment'.</span></span>
    * <span data-ttu-id="31b18-120">Pour les transactions d'ajustement d'acquisition, nous utiliserons les mêmes comptes que ceux utilisés pour les transactions d'acquisition.</span><span class="sxs-lookup"><span data-stu-id="31b18-120">For Acquisition adjustment transactions, we will use the same accounts as used for Acquisition transactions.</span></span>  
9. <span data-ttu-id="31b18-121">Cliquez sur Ajouter.</span><span class="sxs-lookup"><span data-stu-id="31b18-121">Click Add.</span></span>
10. <span data-ttu-id="31b18-122">Dans le champ Registre, entrez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="31b18-122">In the Book field, enter or select a value.</span></span>
11. <span data-ttu-id="31b18-123">Dans le champ Compte principal, spécifiez les valeurs souhaitées.</span><span class="sxs-lookup"><span data-stu-id="31b18-123">In the Main account field, specify the desired values.</span></span>
    * <span data-ttu-id="31b18-124">Pour les ajustements d'acquisition, vous pouvez entrer un compte de contrepartie ou le laisser vide et le renseigner pour la transaction spécifique.</span><span class="sxs-lookup"><span data-stu-id="31b18-124">For Acquisition adjustments, you can enter an offset account or leave it blank to be filled in for the specific transaction.</span></span>    
12. <span data-ttu-id="31b18-125">Sélectionnez « Amortissement » dans le champ Type de transaction.</span><span class="sxs-lookup"><span data-stu-id="31b18-125">In the Transaction type field, select 'Depreciation'.</span></span>
13. <span data-ttu-id="31b18-126">Cliquez sur Ajouter.</span><span class="sxs-lookup"><span data-stu-id="31b18-126">Click Add.</span></span>
14. <span data-ttu-id="31b18-127">Dans le champ Registre, entrez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="31b18-127">In the Book field, enter or select a value.</span></span>
15. <span data-ttu-id="31b18-128">Dans le champ Compte principal, spécifiez les valeurs souhaitées.</span><span class="sxs-lookup"><span data-stu-id="31b18-128">In the Main account field, specify the desired values.</span></span>
16. <span data-ttu-id="31b18-129">Spécifiez les valeurs souhaitées dans le champ Compte de contrepartie.</span><span class="sxs-lookup"><span data-stu-id="31b18-129">In the Offset account field, specify the desired values.</span></span>
17. <span data-ttu-id="31b18-130">Sélectionnez « Ajustement de l'amortissement » dans le champ Type de transaction.</span><span class="sxs-lookup"><span data-stu-id="31b18-130">In the Transaction type field, select 'Depreciation adjustment'.</span></span>
    * <span data-ttu-id="31b18-131">Pour les transactions d'ajustement d'amortissement, nous utiliserons les mêmes comptes que ceux utilisés pour les transactions d'amortissement.</span><span class="sxs-lookup"><span data-stu-id="31b18-131">For Depreciation adjustment transactions, we will use the same accounts as used for Depreciation transactions.</span></span>  
18. <span data-ttu-id="31b18-132">Cliquez sur Ajouter.</span><span class="sxs-lookup"><span data-stu-id="31b18-132">Click Add.</span></span>
19. <span data-ttu-id="31b18-133">Dans le champ Registre, entrez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="31b18-133">In the Book field, enter or select a value.</span></span>
20. <span data-ttu-id="31b18-134">Dans le champ Compte principal, spécifiez les valeurs souhaitées.</span><span class="sxs-lookup"><span data-stu-id="31b18-134">In the Main account field, specify the desired values.</span></span>
21. <span data-ttu-id="31b18-135">Spécifiez les valeurs souhaitées dans le champ Compte de contrepartie.</span><span class="sxs-lookup"><span data-stu-id="31b18-135">In the Offset account field, specify the desired values.</span></span>
22. <span data-ttu-id="31b18-136">Sélectionnez « Cession - Vente » dans le champ Type de transaction.</span><span class="sxs-lookup"><span data-stu-id="31b18-136">In the Transaction type field, select 'Disposal - sale'.</span></span>
23. <span data-ttu-id="31b18-137">Cliquez sur Ajouter.</span><span class="sxs-lookup"><span data-stu-id="31b18-137">Click Add.</span></span>
24. <span data-ttu-id="31b18-138">Dans le champ Registre, entrez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="31b18-138">In the Book field, enter or select a value.</span></span>
25. <span data-ttu-id="31b18-139">Dans le champ Compte principal, spécifiez les valeurs souhaitées.</span><span class="sxs-lookup"><span data-stu-id="31b18-139">In the Main account field, specify the desired values.</span></span>
    * <span data-ttu-id="31b18-140">Pour les cessions, vous pouvez entrer un compte de contrepartie ou le laisser vide et le renseigner pour la transaction spécifique.</span><span class="sxs-lookup"><span data-stu-id="31b18-140">For Disposals, you can enter an offset account or leave it blank to be filled in for the specific transaction.</span></span>  
26. <span data-ttu-id="31b18-141">Sélectionnez « Cession - Mise au rebut » dans le champ Type de transaction.</span><span class="sxs-lookup"><span data-stu-id="31b18-141">In the Transaction type field, select 'Disposal - scrap'.</span></span>
    * <span data-ttu-id="31b18-142">Nous utiliserons les mêmes comptes pour la vente de cession et la mise au rebut.</span><span class="sxs-lookup"><span data-stu-id="31b18-142">We will use the same accounts for Disposal sale and Disposal scrap.</span></span>  
27. <span data-ttu-id="31b18-143">Cliquez sur Ajouter.</span><span class="sxs-lookup"><span data-stu-id="31b18-143">Click Add.</span></span>
28. <span data-ttu-id="31b18-144">Dans le champ Registre, entrez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="31b18-144">In the Book field, enter or select a value.</span></span>
29. <span data-ttu-id="31b18-145">Dans le champ Compte principal, spécifiez les valeurs souhaitées.</span><span class="sxs-lookup"><span data-stu-id="31b18-145">In the Main account field, specify the desired values.</span></span>
    * <span data-ttu-id="31b18-146">Pour les cessions, vous pouvez entrer un compte de contrepartie ou le laisser vide et le renseigner pour la transaction spécifique.</span><span class="sxs-lookup"><span data-stu-id="31b18-146">For Disposals, you can enter an offset account or leave it blank to be filled in for the specific transaction.</span></span>  
30. <span data-ttu-id="31b18-147">Développer la section Cession.</span><span class="sxs-lookup"><span data-stu-id="31b18-147">Expand the Disposal section.</span></span>
    * <span data-ttu-id="31b18-148">Vous devez paramétrer des profils de validation de cession pour la vente et la mise au rebut.</span><span class="sxs-lookup"><span data-stu-id="31b18-148">You must set up disposal posting profiles for both sale and scrap.</span></span>  <span data-ttu-id="31b18-149">Nous commencerons par des transactions de cession.</span><span class="sxs-lookup"><span data-stu-id="31b18-149">We will start with disposal sale transactions.</span></span>  
31. <span data-ttu-id="31b18-150">Cliquez sur Ajouter.</span><span class="sxs-lookup"><span data-stu-id="31b18-150">Click Add.</span></span>
32. <span data-ttu-id="31b18-151">Dans le champ Registre, entrez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="31b18-151">In the Book field, enter or select a value.</span></span>
33. <span data-ttu-id="31b18-152">Sélectionnez « Valeur d'acquisition » dans le champ Valider la valeur.</span><span class="sxs-lookup"><span data-stu-id="31b18-152">In the Post value field, select 'Acquisition value'.</span></span>
    * <span data-ttu-id="31b18-153">La valeur d'acquisition prend en compte l'acquisition et les valeurs d'ajustement de l'acquisition pour toutes les années.</span><span class="sxs-lookup"><span data-stu-id="31b18-153">Acquisition value will address Acquisition and Acquisition adjustment values for all years.</span></span>  <span data-ttu-id="31b18-154">Vous pouvez également définir des comptes pour ces types de transactions séparément.</span><span class="sxs-lookup"><span data-stu-id="31b18-154">You can also define accounts for these transaction types separately.</span></span>  
    * <span data-ttu-id="31b18-155">Vous pouvez définir le processus de cession afin d'utiliser différents comptes, selon que la cession débouche sur un profit ou une perte.</span><span class="sxs-lookup"><span data-stu-id="31b18-155">You can set the disposal process to use different accounts depending upon if the disposal results in a gain or loss.</span></span>  <span data-ttu-id="31b18-156">Je définirai le type de prix de vente sur « Tout » pour utiliser les mêmes comptes pour tous les types de cessions.</span><span class="sxs-lookup"><span data-stu-id="31b18-156">I will set the Sales value type to “All” to use the same accounts for all types of disposals.</span></span>  
34. <span data-ttu-id="31b18-157">Dans le champ Compte principal, spécifiez les valeurs souhaitées.</span><span class="sxs-lookup"><span data-stu-id="31b18-157">In the Main account field, specify the desired values.</span></span>
35. <span data-ttu-id="31b18-158">Spécifiez les valeurs souhaitées dans le champ Compte de contrepartie.</span><span class="sxs-lookup"><span data-stu-id="31b18-158">In the Offset account field, specify the desired values.</span></span>
36. <span data-ttu-id="31b18-159">Cliquez sur Ajouter.</span><span class="sxs-lookup"><span data-stu-id="31b18-159">Click Add.</span></span>
37. <span data-ttu-id="31b18-160">Dans le champ Registre, entrez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="31b18-160">In the Book field, enter or select a value.</span></span>
    * <span data-ttu-id="31b18-161">Sélectionnez « Amortissement (exercices précédents) » dans le champ Valider la valeur.</span><span class="sxs-lookup"><span data-stu-id="31b18-161">In the Post value field, select 'Depreciation (prior years)'.</span></span>  
38. <span data-ttu-id="31b18-162">Dans le champ Compte principal, spécifiez les valeurs souhaitées.</span><span class="sxs-lookup"><span data-stu-id="31b18-162">In the Main account field, specify the desired values.</span></span>
39. <span data-ttu-id="31b18-163">Spécifiez les valeurs souhaitées dans le champ Compte de contrepartie.</span><span class="sxs-lookup"><span data-stu-id="31b18-163">In the Offset account field, specify the desired values.</span></span>
40. <span data-ttu-id="31b18-164">Cliquez sur Ajouter.</span><span class="sxs-lookup"><span data-stu-id="31b18-164">Click Add.</span></span>
41. <span data-ttu-id="31b18-165">Dans le champ Registre, entrez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="31b18-165">In the Book field, enter or select a value.</span></span>
42. <span data-ttu-id="31b18-166">Sélectionnez « Amortissement (cet exercice) » dans le champ Valider la valeur.</span><span class="sxs-lookup"><span data-stu-id="31b18-166">In the Post value field, select 'Depreciation (this year)'.</span></span>
43. <span data-ttu-id="31b18-167">Dans le champ Compte principal, spécifiez les valeurs souhaitées.</span><span class="sxs-lookup"><span data-stu-id="31b18-167">In the Main account field, specify the desired values.</span></span>
44. <span data-ttu-id="31b18-168">Spécifiez les valeurs souhaitées dans le champ Compte de contrepartie.</span><span class="sxs-lookup"><span data-stu-id="31b18-168">In the Offset account field, specify the desired values.</span></span>
45. <span data-ttu-id="31b18-169">Cliquez sur Ajouter.</span><span class="sxs-lookup"><span data-stu-id="31b18-169">Click Add.</span></span>
46. <span data-ttu-id="31b18-170">Dans le champ Registre, entrez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="31b18-170">In the Book field, enter or select a value.</span></span>
47. <span data-ttu-id="31b18-171">Sélectionnez « Ajustements de l'amortissement (exercices précédents) » dans le champ Valider la valeur.</span><span class="sxs-lookup"><span data-stu-id="31b18-171">In the Post value field, select 'Depreciation adjustments (prior years)'.</span></span>
48. <span data-ttu-id="31b18-172">Dans le champ Compte principal, spécifiez les valeurs souhaitées.</span><span class="sxs-lookup"><span data-stu-id="31b18-172">In the Main account field, specify the desired values.</span></span>
49. <span data-ttu-id="31b18-173">Spécifiez les valeurs souhaitées dans le champ Compte de contrepartie.</span><span class="sxs-lookup"><span data-stu-id="31b18-173">In the Offset account field, specify the desired values.</span></span>
50. <span data-ttu-id="31b18-174">Cliquez sur Ajouter.</span><span class="sxs-lookup"><span data-stu-id="31b18-174">Click Add.</span></span>
51. <span data-ttu-id="31b18-175">Dans le champ Registre, entrez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="31b18-175">In the Book field, enter or select a value.</span></span>
52. <span data-ttu-id="31b18-176">Sélectionnez « Ajustements de l'amortissement (cet exercice) » dans le champ Valider la valeur.</span><span class="sxs-lookup"><span data-stu-id="31b18-176">In the Post value field, select 'Depreciation adjustments (this year)'.</span></span>
53. <span data-ttu-id="31b18-177">Dans le champ Compte principal, spécifiez les valeurs souhaitées.</span><span class="sxs-lookup"><span data-stu-id="31b18-177">In the Main account field, specify the desired values.</span></span>
54. <span data-ttu-id="31b18-178">Spécifiez les valeurs souhaitées dans le champ Compte de contrepartie.</span><span class="sxs-lookup"><span data-stu-id="31b18-178">In the Offset account field, specify the desired values.</span></span>
55. <span data-ttu-id="31b18-179">Cliquez sur Ajouter.</span><span class="sxs-lookup"><span data-stu-id="31b18-179">Click Add.</span></span>
56. <span data-ttu-id="31b18-180">Dans le champ Registre, entrez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="31b18-180">In the Book field, enter or select a value.</span></span>
57. <span data-ttu-id="31b18-181">Sélectionnez « Valeur nette » dans le champ Valider la valeur.</span><span class="sxs-lookup"><span data-stu-id="31b18-181">In the Post value field, select 'Net book value'.</span></span>
58. <span data-ttu-id="31b18-182">Dans le champ Compte principal, spécifiez les valeurs souhaitées.</span><span class="sxs-lookup"><span data-stu-id="31b18-182">In the Main account field, specify the desired values.</span></span>
59. <span data-ttu-id="31b18-183">Spécifiez les valeurs souhaitées dans le champ Compte de contrepartie.</span><span class="sxs-lookup"><span data-stu-id="31b18-183">In the Offset account field, specify the desired values.</span></span>
60. <span data-ttu-id="31b18-184">Sélectionnez « Rebut » dans le champ Vente ou mise au rebut.</span><span class="sxs-lookup"><span data-stu-id="31b18-184">In the Sale or scrap field, select 'Scrap'.</span></span>
61. <span data-ttu-id="31b18-185">Cliquez sur Ajouter.</span><span class="sxs-lookup"><span data-stu-id="31b18-185">Click Add.</span></span>
62. <span data-ttu-id="31b18-186">Dans le champ Registre, entrez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="31b18-186">In the Book field, enter or select a value.</span></span>
63. <span data-ttu-id="31b18-187">Sélectionnez « Valeur d'acquisition » dans le champ Valider la valeur.</span><span class="sxs-lookup"><span data-stu-id="31b18-187">In the Post value field, select 'Acquisition value'.</span></span>
64. <span data-ttu-id="31b18-188">Dans le champ Compte principal, spécifiez les valeurs souhaitées.</span><span class="sxs-lookup"><span data-stu-id="31b18-188">In the Main account field, specify the desired values.</span></span>
65. <span data-ttu-id="31b18-189">Spécifiez les valeurs souhaitées dans le champ Compte de contrepartie.</span><span class="sxs-lookup"><span data-stu-id="31b18-189">In the Offset account field, specify the desired values.</span></span>
66. <span data-ttu-id="31b18-190">Cliquez sur Ajouter.</span><span class="sxs-lookup"><span data-stu-id="31b18-190">Click Add.</span></span>
67. <span data-ttu-id="31b18-191">Dans le champ Registre, entrez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="31b18-191">In the Book field, enter or select a value.</span></span>
    * <span data-ttu-id="31b18-192">Sélectionnez « Amortissement (exercices précédents) » dans le champ Valider la valeur.</span><span class="sxs-lookup"><span data-stu-id="31b18-192">In Post value field, select 'Depreciation (prior years)'.</span></span>  
68. <span data-ttu-id="31b18-193">Dans le champ Compte principal, spécifiez les valeurs souhaitées.</span><span class="sxs-lookup"><span data-stu-id="31b18-193">In the Main account field, specify the desired values.</span></span>
69. <span data-ttu-id="31b18-194">Spécifiez les valeurs souhaitées dans le champ Compte de contrepartie.</span><span class="sxs-lookup"><span data-stu-id="31b18-194">In the Offset account field, specify the desired values.</span></span>
70. <span data-ttu-id="31b18-195">Cliquez sur Ajouter.</span><span class="sxs-lookup"><span data-stu-id="31b18-195">Click Add.</span></span>
71. <span data-ttu-id="31b18-196">Dans le champ Registre, entrez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="31b18-196">In the Book field, enter or select a value.</span></span>
72. <span data-ttu-id="31b18-197">Sélectionnez « Amortissement (cet exercice) » dans le champ Valider la valeur.</span><span class="sxs-lookup"><span data-stu-id="31b18-197">In the Post value field, select 'Depreciation (this year)'.</span></span>
73. <span data-ttu-id="31b18-198">Dans le champ Compte principal, spécifiez les valeurs souhaitées.</span><span class="sxs-lookup"><span data-stu-id="31b18-198">In the Main account field, specify the desired values.</span></span>
74. <span data-ttu-id="31b18-199">Spécifiez les valeurs souhaitées dans le champ Compte de contrepartie.</span><span class="sxs-lookup"><span data-stu-id="31b18-199">In the Offset account field, specify the desired values.</span></span>
75. <span data-ttu-id="31b18-200">Cliquez sur Ajouter.</span><span class="sxs-lookup"><span data-stu-id="31b18-200">Click Add.</span></span>
76. <span data-ttu-id="31b18-201">Dans le champ Registre, entrez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="31b18-201">In the Book field, enter or select a value.</span></span>
77. <span data-ttu-id="31b18-202">Sélectionnez « Ajustements de l'amortissement (exercices précédents) » dans le champ Valider la valeur.</span><span class="sxs-lookup"><span data-stu-id="31b18-202">In the Post value field, select 'Depreciation adjustments (prior years)'.</span></span>
78. <span data-ttu-id="31b18-203">Dans le champ Compte principal, spécifiez les valeurs souhaitées.</span><span class="sxs-lookup"><span data-stu-id="31b18-203">In the Main account field, specify the desired values.</span></span>
79. <span data-ttu-id="31b18-204">Spécifiez les valeurs souhaitées dans le champ Compte de contrepartie.</span><span class="sxs-lookup"><span data-stu-id="31b18-204">In the Offset account field, specify the desired values.</span></span>
80. <span data-ttu-id="31b18-205">Cliquez sur Ajouter.</span><span class="sxs-lookup"><span data-stu-id="31b18-205">Click Add.</span></span>
81. <span data-ttu-id="31b18-206">Dans le champ Registre, entrez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="31b18-206">In the Book field, enter or select a value.</span></span>
82. <span data-ttu-id="31b18-207">Sélectionnez « Ajustements de l'amortissement (cet exercice) » dans le champ Valider la valeur.</span><span class="sxs-lookup"><span data-stu-id="31b18-207">In the Post value field, select 'Depreciation adjustments (this year)'.</span></span>
83. <span data-ttu-id="31b18-208">Dans le champ Compte principal, spécifiez les valeurs souhaitées.</span><span class="sxs-lookup"><span data-stu-id="31b18-208">In the Main account field, specify the desired values.</span></span>
84. <span data-ttu-id="31b18-209">Spécifiez les valeurs souhaitées dans le champ Compte de contrepartie.</span><span class="sxs-lookup"><span data-stu-id="31b18-209">In the Offset account field, specify the desired values.</span></span>
85. <span data-ttu-id="31b18-210">Cliquez sur Ajouter.</span><span class="sxs-lookup"><span data-stu-id="31b18-210">Click Add.</span></span>
86. <span data-ttu-id="31b18-211">Dans le champ Registre, entrez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="31b18-211">In the Book field, enter or select a value.</span></span>
87. <span data-ttu-id="31b18-212">Sélectionnez « Valeur nette » dans le champ Valider la valeur.</span><span class="sxs-lookup"><span data-stu-id="31b18-212">In the Post value field, select 'Net book value'.</span></span>
88. <span data-ttu-id="31b18-213">Dans le champ Compte principal, spécifiez les valeurs souhaitées.</span><span class="sxs-lookup"><span data-stu-id="31b18-213">In the Main account field, specify the desired values.</span></span>
89. <span data-ttu-id="31b18-214">Spécifiez les valeurs souhaitées dans le champ Compte de contrepartie.</span><span class="sxs-lookup"><span data-stu-id="31b18-214">In the Offset account field, specify the desired values.</span></span>

