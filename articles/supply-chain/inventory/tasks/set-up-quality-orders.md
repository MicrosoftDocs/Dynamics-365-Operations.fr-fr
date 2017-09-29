---
title: "Paramétrer les ordres de qualité"
description: "Cette procédure décrit comment activer un processus de gestion de la qualité dans lequel le stock entrant doit être inspecté immédiatement après l'enregistrement des arrivées."
author: perlynne
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: YuyuScheller
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 0e7f66cccd76e5326fce75d1a13aff294c16fb9b
ms.openlocfilehash: 73981313fc662094ee4f8bb15a88271e16d41193
ms.contentlocale: fr-fr
ms.lasthandoff: 09/12/2017

---
# <a name="set-up-quality-orders"></a><span data-ttu-id="8c67b-103">Paramétrer les ordres de qualité</span><span class="sxs-lookup"><span data-stu-id="8c67b-103">Set up quality orders</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="8c67b-104">Cette procédure décrit comment activer un processus de gestion de la qualité dans lequel le stock entrant doit être inspecté immédiatement après l'enregistrement des arrivées.</span><span class="sxs-lookup"><span data-stu-id="8c67b-104">This procedure shows you how to enable a quality management process where incoming inventory must be inspected immediately after arrival registration.</span></span> <span data-ttu-id="8c67b-105">La procédure est généralement effectuée par un responsable de la qualité.</span><span class="sxs-lookup"><span data-stu-id="8c67b-105">The procedure will typically be carried out by a quality manager.</span></span> <span data-ttu-id="8c67b-106">Le processus inclut la création d'un groupe de qualité, pour définir les articles qui vont être échantillonnés, et un groupe de test pour regrouper les tests à exécuter sur des articles dans le groupe de qualité.</span><span class="sxs-lookup"><span data-stu-id="8c67b-106">The process includes the creation of a quality group, to define the items that are going to be sampled, and a test group to group the tests that are to be performed on items in the quality group.</span></span> <span data-ttu-id="8c67b-107">Vous pouvez exécuter ce guide dans les données de démonstration de la société fictive USMF.</span><span class="sxs-lookup"><span data-stu-id="8c67b-107">You can run this guide in the USMF demo data company.</span></span>


## <a name="enable-quality-management"></a><span data-ttu-id="8c67b-108">Activer la gestion de la qualité</span><span class="sxs-lookup"><span data-stu-id="8c67b-108">Enable quality management</span></span>
1. <span data-ttu-id="8c67b-109">Accédez à Gestion des stocks > Paramétrage > Paramètres de gestion des stocks et des entrepôts.</span><span class="sxs-lookup"><span data-stu-id="8c67b-109">Go to Inventory management > Setup > Inventory and warehouse management parameters.</span></span>
2. <span data-ttu-id="8c67b-110">Cliquez sur l'onglet Gestion de la qualité.</span><span class="sxs-lookup"><span data-stu-id="8c67b-110">Click the Quality management tab.</span></span>
3. <span data-ttu-id="8c67b-111">Définissez l'option Utiliser la gestion de la qualité sur Oui.</span><span class="sxs-lookup"><span data-stu-id="8c67b-111">Set the Use quality management option to Yes.</span></span>
4. <span data-ttu-id="8c67b-112">Cliquez sur Paramétrage d'état.</span><span class="sxs-lookup"><span data-stu-id="8c67b-112">Click Report setup.</span></span>
    * <span data-ttu-id="8c67b-113">Dans USMF, le paramétrage d'état pour la gestion de la qualité est déjà défini.</span><span class="sxs-lookup"><span data-stu-id="8c67b-113">In USMF, the report setup for quality management is already defined.</span></span> <span data-ttu-id="8c67b-114">Si ce n'est pas le cas, vous devez ajouter de nouvelles lignes ici pour les différents types d'état, et sélectionner le type de document à utiliser pour chaque état.</span><span class="sxs-lookup"><span data-stu-id="8c67b-114">If this wasn’t done, you’d add new lines here for the different report types, and select the type of document to be used for each report.</span></span>  
5. <span data-ttu-id="8c67b-115">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="8c67b-115">Close the page.</span></span>
6. <span data-ttu-id="8c67b-116">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="8c67b-116">Close the page.</span></span>

## <a name="create-a-test"></a><span data-ttu-id="8c67b-117">Créer un test</span><span class="sxs-lookup"><span data-stu-id="8c67b-117">Create a test</span></span>
1. <span data-ttu-id="8c67b-118">Allez dans Gestion des stocks > Configuration > Contrôle de la qualité > Tests.</span><span class="sxs-lookup"><span data-stu-id="8c67b-118">Go to Inventory management > Setup > Quality control > Tests.</span></span>
2. <span data-ttu-id="8c67b-119">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="8c67b-119">Click New.</span></span>
3. <span data-ttu-id="8c67b-120">Dans le champ Test, tapez une valeur.</span><span class="sxs-lookup"><span data-stu-id="8c67b-120">In the Test field, type a value.</span></span>
4. <span data-ttu-id="8c67b-121">Dans le champ Description, entrez une valeur.</span><span class="sxs-lookup"><span data-stu-id="8c67b-121">In the Description field, type a value.</span></span>
5. <span data-ttu-id="8c67b-122">Sélectionnez « Option » dans le champ Type.</span><span class="sxs-lookup"><span data-stu-id="8c67b-122">In the Type field, select 'Option'.</span></span>
    * <span data-ttu-id="8c67b-123">Dans cet exemple, nous allons sélectionner « Option » afin d'affecter les résultats du test selon les valeurs prédéfinies.</span><span class="sxs-lookup"><span data-stu-id="8c67b-123">In this example, we'll select "Option" which will make it possible to assign the test results based on pre-defined values.</span></span>  
6. <span data-ttu-id="8c67b-124">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="8c67b-124">Click Save.</span></span>
7. <span data-ttu-id="8c67b-125">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="8c67b-125">Close the page.</span></span>

## <a name="create-test-variables-to-define-the-way-test-results-are-recorded"></a><span data-ttu-id="8c67b-126">Créer des variables de test pour définir la manière dont les résultats de test sont enregistrés</span><span class="sxs-lookup"><span data-stu-id="8c67b-126">Create Test variables to define the way test results are recorded</span></span>
1. <span data-ttu-id="8c67b-127">Allez dans Gestion des stocks > Configuration > Contrôle de la qualité > Variables de test.</span><span class="sxs-lookup"><span data-stu-id="8c67b-127">Go to Inventory management > Setup > Quality control > Test variables.</span></span>
2. <span data-ttu-id="8c67b-128">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="8c67b-128">Click New.</span></span>
3. <span data-ttu-id="8c67b-129">Tapez une valeur dans le champ Variable.</span><span class="sxs-lookup"><span data-stu-id="8c67b-129">In the Variable field, type a value.</span></span>
4. <span data-ttu-id="8c67b-130">Dans le champ Description, entrez une valeur.</span><span class="sxs-lookup"><span data-stu-id="8c67b-130">In the Description field, type a value.</span></span>
5. <span data-ttu-id="8c67b-131">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="8c67b-131">Click Save.</span></span>
6. <span data-ttu-id="8c67b-132">Cliquez sur Résultats.</span><span class="sxs-lookup"><span data-stu-id="8c67b-132">Click Outcomes.</span></span>
7. <span data-ttu-id="8c67b-133">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="8c67b-133">Click New.</span></span>
8. <span data-ttu-id="8c67b-134">Tapez une valeur dans le champ Résultat.</span><span class="sxs-lookup"><span data-stu-id="8c67b-134">In the Outcome field, type a value.</span></span>
9. <span data-ttu-id="8c67b-135">Dans le champ Description, entrez une valeur.</span><span class="sxs-lookup"><span data-stu-id="8c67b-135">In the Description field, type a value.</span></span>
10. <span data-ttu-id="8c67b-136">Sélectionnez « Réussite » dans le champ Statut du résultat.</span><span class="sxs-lookup"><span data-stu-id="8c67b-136">In the Outcome status field, select 'Pass'.</span></span>
11. <span data-ttu-id="8c67b-137">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="8c67b-137">Click Save.</span></span>
12. <span data-ttu-id="8c67b-138">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="8c67b-138">Click New.</span></span>
13. <span data-ttu-id="8c67b-139">Tapez une valeur dans le champ Résultat.</span><span class="sxs-lookup"><span data-stu-id="8c67b-139">In the Outcome field, type a value.</span></span>
14. <span data-ttu-id="8c67b-140">Dans le champ Description, entrez une valeur.</span><span class="sxs-lookup"><span data-stu-id="8c67b-140">In the Description field, type a value.</span></span>
15. <span data-ttu-id="8c67b-141">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="8c67b-141">Click Save.</span></span>
16. <span data-ttu-id="8c67b-142">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="8c67b-142">Close the page.</span></span>
17. <span data-ttu-id="8c67b-143">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="8c67b-143">Close the page.</span></span>

## <a name="set-up-item-sampling"></a><span data-ttu-id="8c67b-144">Paramétrer l'échantillonnage d'article</span><span class="sxs-lookup"><span data-stu-id="8c67b-144">Set up item sampling</span></span>
1. <span data-ttu-id="8c67b-145">Allez dans Gestion des stocks > Configuration > Contrôle de la qualité > Échantillonnage d'article.</span><span class="sxs-lookup"><span data-stu-id="8c67b-145">Go to Inventory management > Setup > Quality control > Item sampling.</span></span>
2. <span data-ttu-id="8c67b-146">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="8c67b-146">Click New.</span></span>
3. <span data-ttu-id="8c67b-147">Tapez une valeur dans le champ Échantillonnage d'article.</span><span class="sxs-lookup"><span data-stu-id="8c67b-147">In the Item sampling field, type a value.</span></span>
4. <span data-ttu-id="8c67b-148">Dans le champ Description, entrez une valeur.</span><span class="sxs-lookup"><span data-stu-id="8c67b-148">In the Description field, type a value.</span></span>
5. <span data-ttu-id="8c67b-149">Entrez un nombre dans le champ Valeur.</span><span class="sxs-lookup"><span data-stu-id="8c67b-149">In the Value field, enter a number.</span></span>
    * <span data-ttu-id="8c67b-150">Cette valeur fait référence à la spécification de quantité sélectionnée dans le champ adjacent.</span><span class="sxs-lookup"><span data-stu-id="8c67b-150">This value relates to the Quantity specification that’s selected in the adjacent field.</span></span>  
6. <span data-ttu-id="8c67b-151">Développez ou réduisez la section Processus.</span><span class="sxs-lookup"><span data-stu-id="8c67b-151">Expand or collapse the Process section.</span></span>
7. <span data-ttu-id="8c67b-152">Activez ou désactivez la case à cocher Blocage total.</span><span class="sxs-lookup"><span data-stu-id="8c67b-152">Select or clear the Full blocking check box.</span></span>
    * <span data-ttu-id="8c67b-153">Si vous sélectionnez cette option, le lot entier ou la quantité de la ligne de commande est bloqué si un test échoue.</span><span class="sxs-lookup"><span data-stu-id="8c67b-153">If you select this option, the whole lot or order line quantity is blocked if a test is failed.</span></span> <span data-ttu-id="8c67b-154">Si vous ne la sélectionnez pas, seuls les articles de l'ordre de qualité sont bloqués.</span><span class="sxs-lookup"><span data-stu-id="8c67b-154">If you don't select it, only the items in the quality order are blocked.</span></span>  
8. <span data-ttu-id="8c67b-155">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="8c67b-155">Click Save.</span></span>
9. <span data-ttu-id="8c67b-156">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="8c67b-156">Close the page.</span></span>

## <a name="create-a-quality-group"></a><span data-ttu-id="8c67b-157">Créer un groupe de qualité</span><span class="sxs-lookup"><span data-stu-id="8c67b-157">Create a quality group</span></span>
1. <span data-ttu-id="8c67b-158">Allez dans Gestion des stocks > Configuration > Contrôle de la qualité > Groupes de qualité.</span><span class="sxs-lookup"><span data-stu-id="8c67b-158">Go to Inventory management > Setup > Quality control > Quality groups.</span></span>
2. <span data-ttu-id="8c67b-159">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="8c67b-159">Click New.</span></span>
3. <span data-ttu-id="8c67b-160">Tapez une valeur dans le champ Groupe de qualité.</span><span class="sxs-lookup"><span data-stu-id="8c67b-160">In the Quality group field, type a value.</span></span>
    * <span data-ttu-id="8c67b-161">Utilisez un nom descriptif pour vous aider à identifier les types d'articles contenus dans le groupe (vos critères d'échantillonnage).</span><span class="sxs-lookup"><span data-stu-id="8c67b-161">Use a descriptive name to help you identify which kind of items the group will contain (your sampling criteria).</span></span>  
4. <span data-ttu-id="8c67b-162">Dans le champ Description, entrez une valeur.</span><span class="sxs-lookup"><span data-stu-id="8c67b-162">In the Description field, type a value.</span></span>
5. <span data-ttu-id="8c67b-163">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="8c67b-163">Click Save.</span></span>
6. <span data-ttu-id="8c67b-164">Cliquez sur Ajout d'articles.</span><span class="sxs-lookup"><span data-stu-id="8c67b-164">Click Add items.</span></span>
7. <span data-ttu-id="8c67b-165">Sélectionnez la ligne Numéro d'article.</span><span class="sxs-lookup"><span data-stu-id="8c67b-165">Select the Item number row</span></span>
    * <span data-ttu-id="8c67b-166">Dans cet exemple le filtrage sera exécuté selon le numéro d'article.</span><span class="sxs-lookup"><span data-stu-id="8c67b-166">In this example the filtering will be run based on  the item number.</span></span>  
8. <span data-ttu-id="8c67b-167">Tapez une valeur dans le champ Critères.</span><span class="sxs-lookup"><span data-stu-id="8c67b-167">In the Criteria field, type a value.</span></span>
    * <span data-ttu-id="8c67b-168">Par exemple, tapez T* pour filtrer les numéros d'article commençant par un T.</span><span class="sxs-lookup"><span data-stu-id="8c67b-168">For example, type T* to filter on the item numbers that start with T.</span></span>  
9. <span data-ttu-id="8c67b-169">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="8c67b-169">Click OK.</span></span>
10. <span data-ttu-id="8c67b-170">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="8c67b-170">Click OK.</span></span>
11. <span data-ttu-id="8c67b-171">Cliquez sur Groupes de qualité d'article.</span><span class="sxs-lookup"><span data-stu-id="8c67b-171">Click Item quality groups.</span></span>
12. <span data-ttu-id="8c67b-172">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="8c67b-172">Close the page.</span></span>
13. <span data-ttu-id="8c67b-173">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="8c67b-173">Close the page.</span></span>

## <a name="create-a-test-group"></a><span data-ttu-id="8c67b-174">Création d'un groupe de test</span><span class="sxs-lookup"><span data-stu-id="8c67b-174">Create a test group</span></span>
1. <span data-ttu-id="8c67b-175">Allez dans Gestion des stocks > Configuration > Contrôle de la qualité > Groupes de test.</span><span class="sxs-lookup"><span data-stu-id="8c67b-175">Go to Inventory management > Setup > Quality control > Test groups.</span></span>
2. <span data-ttu-id="8c67b-176">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="8c67b-176">Click New.</span></span>
3. <span data-ttu-id="8c67b-177">Tapez une valeur dans le champ Groupe de test.</span><span class="sxs-lookup"><span data-stu-id="8c67b-177">In the Test group field, type a value.</span></span>
    * <span data-ttu-id="8c67b-178">Donnez au groupe de tests un nom qui vous aidera à vous souvenir des types de tests qui sont exécutés, et à quel groupe de qualité ils doivent être associés.</span><span class="sxs-lookup"><span data-stu-id="8c67b-178">Give the Test group a name that will help you remember what kind of tests are being run, and which quality group it should be associated with.</span></span> <span data-ttu-id="8c67b-179">Par exemple, s'il doit être utilisé avec un groupe de qualité qui sélectionne des articles en commençant par « T », vous pourriez l'appeler « Tests article-T ».</span><span class="sxs-lookup"><span data-stu-id="8c67b-179">For example, it it’s to be used with a quality group that selects items starting with “T”, you could call it “T-item tests”.</span></span>  
4. <span data-ttu-id="8c67b-180">Dans le champ Description, entrez une valeur.</span><span class="sxs-lookup"><span data-stu-id="8c67b-180">In the Description field, type a value.</span></span>
5. <span data-ttu-id="8c67b-181">Dans le champ Échantillonnage d'article, sélectionnez la ligne d'échantillonnage d'article que vous avez créée avant.</span><span class="sxs-lookup"><span data-stu-id="8c67b-181">In the Item sampling field, select the item sampling line that you created before.</span></span>
6. <span data-ttu-id="8c67b-182">Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="8c67b-182">In the list, find and select the desired record.</span></span>
7. <span data-ttu-id="8c67b-183">Cliquez sur Ajouter.</span><span class="sxs-lookup"><span data-stu-id="8c67b-183">Click Add.</span></span>
8. <span data-ttu-id="8c67b-184">Entrez un nombre dans le champ Numéro de souche.</span><span class="sxs-lookup"><span data-stu-id="8c67b-184">In the Sequence number field, enter a number.</span></span>
9. <span data-ttu-id="8c67b-185">Dans le champ Test, sélectionnez le test créé précédemment.</span><span class="sxs-lookup"><span data-stu-id="8c67b-185">In the Test field, select the test that you created earlier.</span></span>
10. <span data-ttu-id="8c67b-186">Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="8c67b-186">In the list, find and select the desired record.</span></span>
11. <span data-ttu-id="8c67b-187">Cliquez sur l'onglet Test.</span><span class="sxs-lookup"><span data-stu-id="8c67b-187">Click the Test tab.</span></span>
12. <span data-ttu-id="8c67b-188">Dans le champ Variable, sélectionnez la variable de test créée précédemment.</span><span class="sxs-lookup"><span data-stu-id="8c67b-188">In the Variable field, select the test variable that you created before</span></span>
13. <span data-ttu-id="8c67b-189">Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="8c67b-189">In the list, find and select the desired record.</span></span>
14. <span data-ttu-id="8c67b-190">Dans le champ Résultat par défaut, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="8c67b-190">In the Default outcome field, click the drop-down button to open the lookup.</span></span>
15. <span data-ttu-id="8c67b-191">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="8c67b-191">In the list, click the link in the selected row.</span></span>
16. <span data-ttu-id="8c67b-192">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="8c67b-192">Click Save.</span></span>
17. <span data-ttu-id="8c67b-193">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="8c67b-193">Close the page.</span></span>

## <a name="define-when-quality-orders-will-be-created"></a><span data-ttu-id="8c67b-194">Définir à quel moment les ordres de qualité seront créés</span><span class="sxs-lookup"><span data-stu-id="8c67b-194">Define when quality orders will be created</span></span>
1. <span data-ttu-id="8c67b-195">Allez dans Gestion des stocks > Configuration > Contrôle de la qualité > Associations de qualité.</span><span class="sxs-lookup"><span data-stu-id="8c67b-195">Go to Inventory management > Setup > Quality control > Quality associations.</span></span>
2. <span data-ttu-id="8c67b-196">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="8c67b-196">Click New.</span></span>
3. <span data-ttu-id="8c67b-197">Sélectionnez une option dans le champ Type de référence.</span><span class="sxs-lookup"><span data-stu-id="8c67b-197">In the Reference type field, select an option.</span></span>
4. <span data-ttu-id="8c67b-198">Sélectionnez Groupe dans le champ Article - valide pour.</span><span class="sxs-lookup"><span data-stu-id="8c67b-198">In the Item code field, select 'Group'.</span></span>
    * <span data-ttu-id="8c67b-199">Dans cet exemple, nous allons sélectionner « Groupe » et utiliser le groupe de qualité déjà créé avant.</span><span class="sxs-lookup"><span data-stu-id="8c67b-199">In this example, we’ll select "Group" and use the quality group we created before.</span></span> <span data-ttu-id="8c67b-200">Vous pouvez également le définir sur « Tableau » pour spécifier les articles manuellement, ou sélectionner « Tous » pour ajouter tous les articles à l'ordre de qualité.</span><span class="sxs-lookup"><span data-stu-id="8c67b-200">You could also set this to "Table" to specify the items manually, or select "All" to add all items to the quality order.</span></span>  
5. <span data-ttu-id="8c67b-201">Dans le champ Article, sélectionnez le groupe de qualité créé précédemment.</span><span class="sxs-lookup"><span data-stu-id="8c67b-201">In the Item field, select the quality group that you created before.</span></span>
    * <span data-ttu-id="8c67b-202">Les options disponibles dans le champ Article dépendent de ce qui vous définissez dans le champ Article - valide pour.</span><span class="sxs-lookup"><span data-stu-id="8c67b-202">The options available in the Item field depend on what you set in the Item code field.</span></span>  
6. <span data-ttu-id="8c67b-203">Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="8c67b-203">In the list, find and select the desired record.</span></span>
7. <span data-ttu-id="8c67b-204">Développez ou réduisez la section Processus.</span><span class="sxs-lookup"><span data-stu-id="8c67b-204">Expand or collapse the Process section.</span></span>
8. <span data-ttu-id="8c67b-205">Sélectionnez une option dans le champ Type d'événement.</span><span class="sxs-lookup"><span data-stu-id="8c67b-205">In the Event type field, select an option.</span></span>
    * <span data-ttu-id="8c67b-206">Il s'agit de l'événement qui déclenche le test.</span><span class="sxs-lookup"><span data-stu-id="8c67b-206">This is the event that triggers the test.</span></span> <span data-ttu-id="8c67b-207">Les options disponibles ici dépendent du processus que vous avez sélectionné dans le champ Type de référence.</span><span class="sxs-lookup"><span data-stu-id="8c67b-207">The options available here depend on which process you selected in the Reference type field.</span></span>  
9. <span data-ttu-id="8c67b-208">Sélectionnez une option dans le champ Exécution.</span><span class="sxs-lookup"><span data-stu-id="8c67b-208">In the Execution field, select an option.</span></span>
10. <span data-ttu-id="8c67b-209">Développez ou réduisez la section Processus d'ordre de qualité.</span><span class="sxs-lookup"><span data-stu-id="8c67b-209">Expand or collapse the Quality order process section.</span></span>
11. <span data-ttu-id="8c67b-210">Dans le champ Blocage d'événement, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="8c67b-210">In the Event blocking field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="8c67b-211">Ce champ affiche la liste des processus qu'il est possible de bloquer si l'ordre de qualité est toujours en cours.</span><span class="sxs-lookup"><span data-stu-id="8c67b-211">This field shows the list of processes that it’s possible to block if the quality order is still open.</span></span> <span data-ttu-id="8c67b-212">Les options dépendent de ce que vous avez sélectionné dans le champ Type d'événement.</span><span class="sxs-lookup"><span data-stu-id="8c67b-212">The options depend on what you selected in the Event type field.</span></span>  
12. <span data-ttu-id="8c67b-213">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="8c67b-213">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="8c67b-214">Tout dépend des valeurs sélectionnées précédemment.</span><span class="sxs-lookup"><span data-stu-id="8c67b-214">This will be depending on the previous selected values.</span></span> <span data-ttu-id="8c67b-215">Sélectionnez cette option si les processus suivants doivent être bloqués tandis que des ordres de qualité en cours sont liés à une ligne de document source.</span><span class="sxs-lookup"><span data-stu-id="8c67b-215">Select if the following processes must be blocked while having open quality orders linked to a source document line.</span></span>  
13. <span data-ttu-id="8c67b-216">Développez ou réduisez la section Spécifications.</span><span class="sxs-lookup"><span data-stu-id="8c67b-216">Expand or collapse the Specifications section.</span></span>
14. <span data-ttu-id="8c67b-217">Dans le champ Groupe de test, sélectionnez le groupe de test créé précédemment.</span><span class="sxs-lookup"><span data-stu-id="8c67b-217">In the Test group field, select the test group that you created before.</span></span>
15. <span data-ttu-id="8c67b-218">Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="8c67b-218">In the list, find and select the desired record.</span></span>
16. <span data-ttu-id="8c67b-219">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="8c67b-219">Click Save.</span></span>
17. <span data-ttu-id="8c67b-220">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="8c67b-220">Close the page.</span></span>

