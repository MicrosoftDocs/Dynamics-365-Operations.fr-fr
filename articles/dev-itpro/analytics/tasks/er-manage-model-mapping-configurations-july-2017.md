--- 
title: "Gérer des configurations de mappage de modèle pour la gestion des états électroniques (ER)"
description: "Les étapes suivantes expliquent comment un utilisateur affecté au rôle d'administrateur système ou de développeur d'états électroniques peut gérer des mises en correspondance de modèle d'états électroniques dans des configurations ER distinctes."
author: NickSelin
manager: AnnBe
ms.date: 06/19/2017
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
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: 5c6804291752b6a187b2855c2a8feb92181dca24
ms.contentlocale: fr-fr
ms.lasthandoff: 04/13/2018

---
# <a name="manage-model-mapping-configurations-for-electronic-reporting-er"></a><span data-ttu-id="9cf68-103">Gérer des configurations de mappage de modèle pour la gestion des états électroniques (ER)</span><span class="sxs-lookup"><span data-stu-id="9cf68-103">Manage model mapping configurations for electronic reporting (ER)</span></span>

[!INCLUDE [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="9cf68-104">Les étapes suivantes expliquent comment un utilisateur affecté au rôle d'administrateur système ou de développeur d'états électroniques peut gérer des mises en correspondance de modèle d'états électroniques dans des configurations ER distinctes.</span><span class="sxs-lookup"><span data-stu-id="9cf68-104">The following steps explain how a user assigned to the System administrator or Electronic reporting developer role can manage Electronic reporting (ER) model mappings in separate ER configurations.</span></span> <span data-ttu-id="9cf68-105">Dans ce guide de tâche, vous allez créer les configurations ER requises pour l'exemple de société, Litware, Inc. Pour réaliser les étapes de ce guide de tâche, vous devez d'abord effectuer les étapes du guide de tâche, « ER Créer un fournisseur de configuration et le marquer comme actif ».</span><span class="sxs-lookup"><span data-stu-id="9cf68-105">In this task guide, you will create required ER configurations for the sample company, Litware, Inc. To complete this task guide, you must first complete the steps in the task guide, “ER Create a configuration provider” and mark it as active.</span></span> 

<span data-ttu-id="9cf68-106">Comme les configurations ER sont partagées entre les sociétés, vous pouvez réaliser les étapes de ce guide de tâche en utilisant l'ensemble de données de société de votre choix.</span><span class="sxs-lookup"><span data-stu-id="9cf68-106">Because ER configurations are shared among companies, you can complete this task guide using the company data set of your choice.</span></span> <span data-ttu-id="9cf68-107">La fonctionnalité pour ce guide de tâche est disponible que si vous avez installé l'un des correctifs suivants : https://fix.lcs.dynamics.com/Issue/Resolved?kb=4012872 pour la version 7.0 de Dynamics AX ou https://fix.lcs.dynamics.com/Issue/Resolved?kb=4012871 pour la version Dynamics 365 for Operations.</span><span class="sxs-lookup"><span data-stu-id="9cf68-107">The functionality for this task guide is available if you have installed one of the following hotfixes: https://fix.lcs.dynamics.com/Issue/Resolved?kb=4012872 for the Dynamics AX 7.0 version or https://fix.lcs.dynamics.com/Issue/Resolved?kb=4012871 for the Dynamics 365 for Operations version.</span></span>

1. <span data-ttu-id="9cf68-108">Accédez à Administration d'organisation > Espaces de travail > États électroniques.</span><span class="sxs-lookup"><span data-stu-id="9cf68-108">Go to Organization administration > Workspaces > Electronic reporting.</span></span>
    * <span data-ttu-id="9cf68-109">Vérifiez que le fournisseur de la configuration pour la société fictive Litware, Inc. est disponible et marqué comme actif.</span><span class="sxs-lookup"><span data-stu-id="9cf68-109">Verify that the configuration provider for the sample company Litware, Inc. is available and marked as active.</span></span> <span data-ttu-id="9cf68-110">Si ce fournisseur de configuration ne s'affiche pas, vous devez d'abord effectuer les étapes du guide de tâche, Créer un fournisseur de configuration et le marquer comme actif.</span><span class="sxs-lookup"><span data-stu-id="9cf68-110">If you don’t see this configuration provider, you must first complete the steps in the task guide, Create a configuration provider and mark it as active.</span></span>   

## <a name="add-a-new-er-model-configuration"></a><span data-ttu-id="9cf68-111">Ajouter une nouvelle configuration du modèle ER</span><span class="sxs-lookup"><span data-stu-id="9cf68-111">Add a new ER model configuration</span></span>
1. <span data-ttu-id="9cf68-112">Cliquez sur Configurations des états.</span><span class="sxs-lookup"><span data-stu-id="9cf68-112">Click Reporting configurations.</span></span>
    * <span data-ttu-id="9cf68-113">Ajoutez une nouvelle configuration du modèle.</span><span class="sxs-lookup"><span data-stu-id="9cf68-113">Add a new model configuration.</span></span> <span data-ttu-id="9cf68-114">Le nom doit être unique dans l'arborescence de configurations.</span><span class="sxs-lookup"><span data-stu-id="9cf68-114">The name must be unique in the configurations tree.</span></span>  
2. <span data-ttu-id="9cf68-115">Cliquez sur Créer la configuration pour ouvrir la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="9cf68-115">Click Create configuration to open the drop dialog.</span></span>
3. <span data-ttu-id="9cf68-116">Dans le champ Nom, tapez « Exemple de modèle de données ».</span><span class="sxs-lookup"><span data-stu-id="9cf68-116">In the Name field, type 'Sample data model'.</span></span>
    * <span data-ttu-id="9cf68-117">Exemple de modèle de données</span><span class="sxs-lookup"><span data-stu-id="9cf68-117">Sample data model</span></span>  
4. <span data-ttu-id="9cf68-118">Cliquez sur Créer une configuration.</span><span class="sxs-lookup"><span data-stu-id="9cf68-118">Click Create configuration.</span></span>
5. <span data-ttu-id="9cf68-119">Cliquez sur Concepteur.</span><span class="sxs-lookup"><span data-stu-id="9cf68-119">Click Designer.</span></span>
6. <span data-ttu-id="9cf68-120">Cliquez sur Nouveau pour ouvrir la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="9cf68-120">Click New to open the drop dialog.</span></span>
7. <span data-ttu-id="9cf68-121">Dans le champ Nom, tapez « Racine ».</span><span class="sxs-lookup"><span data-stu-id="9cf68-121">In the Name field, type 'Root'.</span></span>
    * <span data-ttu-id="9cf68-122">Racine</span><span class="sxs-lookup"><span data-stu-id="9cf68-122">Root</span></span>  
8. <span data-ttu-id="9cf68-123">Cliquez sur Ajouter.</span><span class="sxs-lookup"><span data-stu-id="9cf68-123">Click Add.</span></span>
9. <span data-ttu-id="9cf68-124">Cliquez sur Nouveau pour ouvrir la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="9cf68-124">Click New to open the drop dialog.</span></span>
10. <span data-ttu-id="9cf68-125">Dans le champ Nom, tapez « Société ».</span><span class="sxs-lookup"><span data-stu-id="9cf68-125">In the Name field, type 'Company'.</span></span>
    * <span data-ttu-id="9cf68-126">Société</span><span class="sxs-lookup"><span data-stu-id="9cf68-126">Company</span></span>  
11. <span data-ttu-id="9cf68-127">Cliquez sur Ajouter.</span><span class="sxs-lookup"><span data-stu-id="9cf68-127">Click Add.</span></span>
12. <span data-ttu-id="9cf68-128">Dans le champ Description, entrez le texte, Description de l'entité juridique ou de la société à laquelle un utilisateur est connecté au moment de l'exécution.</span><span class="sxs-lookup"><span data-stu-id="9cf68-128">In the Description field, enter the text, Description of the legal entity or company in which a user logged at run-time.</span></span> 
    * <span data-ttu-id="9cf68-129">Description de l'entité juridique ou de la société à laquelle un utilisateur est connecté au moment de l'exécution.</span><span class="sxs-lookup"><span data-stu-id="9cf68-129">Description of the legal entity or company in which a user logged at run-time.</span></span>  
13. <span data-ttu-id="9cf68-130">Cliquez sur Référence racine.</span><span class="sxs-lookup"><span data-stu-id="9cf68-130">Click Root reference.</span></span>
14. <span data-ttu-id="9cf68-131">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="9cf68-131">Click OK.</span></span>
15. <span data-ttu-id="9cf68-132">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="9cf68-132">Click Save.</span></span>
16. <span data-ttu-id="9cf68-133">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="9cf68-133">Close the page.</span></span>
17. <span data-ttu-id="9cf68-134">Cliquez sur Modifier le statut.</span><span class="sxs-lookup"><span data-stu-id="9cf68-134">Click Change status.</span></span>
18. <span data-ttu-id="9cf68-135">Cliquez sur Terminé.</span><span class="sxs-lookup"><span data-stu-id="9cf68-135">Click Complete.</span></span>
19. <span data-ttu-id="9cf68-136">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="9cf68-136">Click OK.</span></span>

## <a name="add-a-new-er-model-mapping-configuration"></a><span data-ttu-id="9cf68-137">Ajouter une nouvelle configuration de mise en correspondance du modèle de données ER</span><span class="sxs-lookup"><span data-stu-id="9cf68-137">Add a new ER model mapping configuration</span></span>
1. <span data-ttu-id="9cf68-138">Cliquez sur Créer la configuration pour ouvrir la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="9cf68-138">Click Create configuration to open the drop dialog.</span></span>
2. <span data-ttu-id="9cf68-139">Dans le champ Nouveau, entrez « Mise en correspondance de modèle basée sur le modèle de données Exemple de modèle de données ».</span><span class="sxs-lookup"><span data-stu-id="9cf68-139">In the New field, enter 'Model Mapping based on data model Sample data model'.</span></span>
3. <span data-ttu-id="9cf68-140">Dans le champ Nom, tapez « Exemple de mise en correspondance ».</span><span class="sxs-lookup"><span data-stu-id="9cf68-140">In the Name field, type 'Sample mapping'.</span></span>
    * <span data-ttu-id="9cf68-141">Exemple de mise en correspondance</span><span class="sxs-lookup"><span data-stu-id="9cf68-141">Sample mapping</span></span>  
4. <span data-ttu-id="9cf68-142">Cliquez sur Créer une configuration.</span><span class="sxs-lookup"><span data-stu-id="9cf68-142">Click Create configuration.</span></span>
5. <span data-ttu-id="9cf68-143">Développez la section Conditions préalables.</span><span class="sxs-lookup"><span data-stu-id="9cf68-143">Expand the Prerequisites section.</span></span>
    * <span data-ttu-id="9cf68-144">Notez que le groupe de composants prérequis Implémentations a été ajouté automatiquement.</span><span class="sxs-lookup"><span data-stu-id="9cf68-144">Note that the Implementations prerequisites group has been added automatically.</span></span> <span data-ttu-id="9cf68-145">Le groupe contient le composant prérequis qui fait référence à la configuration de modèle de données parent et est marqué comme implémentation.</span><span class="sxs-lookup"><span data-stu-id="9cf68-145">The group contains the prerequisite component that refers to the parent data model configuration and is marked as Implementation.</span></span> <span data-ttu-id="9cf68-146">Cela signifie que cette configuration de mise en correspondance de modèle Exemple de mise en correspondance est considérée comme l'implémentation du modèle de données, Exemple de modèle de données.</span><span class="sxs-lookup"><span data-stu-id="9cf68-146">This means that this Sample mapping model mapping configuration is considered the implementation of the data model, Sample data model.</span></span> <span data-ttu-id="9cf68-147">Par conséquent, ce composant forcera ER à télécharger la configuration de mise en correspondance de modèle, Exemple de mise en correspondance, à partir d'un référentiel ER lorsque la configuration de modèle, Exemple de modèle de données, est téléchargée.</span><span class="sxs-lookup"><span data-stu-id="9cf68-147">Therefore, this component will force ER to download the model mapping configuration, Sample mapping from an ER repository when the model configuration, Sample data model, is downloaded.</span></span>   
6. <span data-ttu-id="9cf68-148">Cliquez sur Concepteur.</span><span class="sxs-lookup"><span data-stu-id="9cf68-148">Click Designer.</span></span>
    * <span data-ttu-id="9cf68-149">Notez que la configuration de mise en correspondance de modèle créée contient une nouvelle mise en correspondance vide portant le même nom que la configuration créée.</span><span class="sxs-lookup"><span data-stu-id="9cf68-149">Note that the created model mapping configuration contains a new blank mapping with the same name as the created configuration.</span></span> <span data-ttu-id="9cf68-150">Notez que lorsqu'une configuration de modèle parent sélectionnée contient des mises en correspondance de modèle, celles-ci sont copiées dans une nouvelle configuration de mise en correspondance de modèle.</span><span class="sxs-lookup"><span data-stu-id="9cf68-150">Be aware that when a selected parent model configuration contains model mappings, they will be copied to a new model mapping configuration.</span></span>   
7. <span data-ttu-id="9cf68-151">Cliquez sur Concepteur.</span><span class="sxs-lookup"><span data-stu-id="9cf68-151">Click Designer.</span></span>
8. <span data-ttu-id="9cf68-152">Dans l'arborescence, sélectionnez « Dynamics 365 for Operations\Table ».</span><span class="sxs-lookup"><span data-stu-id="9cf68-152">In the tree, select 'Dynamics 365 for Operations\Table'.</span></span>
9. <span data-ttu-id="9cf68-153">Cliquez sur Ajouter racine.</span><span class="sxs-lookup"><span data-stu-id="9cf68-153">Click Add root.</span></span>
10. <span data-ttu-id="9cf68-154">Dans le champ Nom, tapez « Société ».</span><span class="sxs-lookup"><span data-stu-id="9cf68-154">In the Name field, type 'Company'.</span></span>
    * <span data-ttu-id="9cf68-155">Société</span><span class="sxs-lookup"><span data-stu-id="9cf68-155">Company</span></span>  
11. <span data-ttu-id="9cf68-156">Dans le champ Table, tapez « CompanyInfo ».</span><span class="sxs-lookup"><span data-stu-id="9cf68-156">In the Table field, type 'CompanyInfo'.</span></span>
    * <span data-ttu-id="9cf68-157">CompanyInfo</span><span class="sxs-lookup"><span data-stu-id="9cf68-157">CompanyInfo</span></span>  
12. <span data-ttu-id="9cf68-158">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="9cf68-158">Click OK.</span></span>
13. <span data-ttu-id="9cf68-159">Dans l'arborescence, développez « Société ».</span><span class="sxs-lookup"><span data-stu-id="9cf68-159">In the tree, expand 'Company'.</span></span>
14. <span data-ttu-id="9cf68-160">Dans l'arborescence, développez « Company\find() ».</span><span class="sxs-lookup"><span data-stu-id="9cf68-160">In the tree, expand 'Company\find()'.</span></span>
15. <span data-ttu-id="9cf68-161">Dans l'arborescence, sélectionnez « Company\find()\Name ».</span><span class="sxs-lookup"><span data-stu-id="9cf68-161">In the tree, select 'Company\find()\Name'.</span></span>
16. <span data-ttu-id="9cf68-162">Cliquez sur Lier.</span><span class="sxs-lookup"><span data-stu-id="9cf68-162">Click Bind.</span></span>
17. <span data-ttu-id="9cf68-163">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="9cf68-163">Click Save.</span></span>
18. <span data-ttu-id="9cf68-164">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="9cf68-164">Close the page.</span></span>
19. <span data-ttu-id="9cf68-165">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="9cf68-165">Close the page.</span></span>
20. <span data-ttu-id="9cf68-166">Dans le volet Actions, cliquez sur Configurations.</span><span class="sxs-lookup"><span data-stu-id="9cf68-166">On the Action Pane, click Configurations.</span></span>
21. <span data-ttu-id="9cf68-167">Cliquez sur Paramètres utilisateur.</span><span class="sxs-lookup"><span data-stu-id="9cf68-167">Click User parameters.</span></span>
22. <span data-ttu-id="9cf68-168">Sélectionnez Oui dans le champ Paramètres d'exécution.</span><span class="sxs-lookup"><span data-stu-id="9cf68-168">Select Yes in the Run settings field.</span></span>
23. <span data-ttu-id="9cf68-169">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="9cf68-169">Click OK.</span></span>
24. <span data-ttu-id="9cf68-170">Cliquez sur Modifier.</span><span class="sxs-lookup"><span data-stu-id="9cf68-170">Click Edit.</span></span>
25. <span data-ttu-id="9cf68-171">Sélectionnez Oui dans le champ Exécuter le brouillon.</span><span class="sxs-lookup"><span data-stu-id="9cf68-171">Select Yes in the Run Draft field.</span></span>

## <a name="add-a-new-er-format-configuration"></a><span data-ttu-id="9cf68-172">Ajouter une nouvelle configuration du format ER</span><span class="sxs-lookup"><span data-stu-id="9cf68-172">Add a new ER format configuration</span></span>
1. <span data-ttu-id="9cf68-173">Dans l'arborescence, sélectionnez « Exemple de modèle de données ».</span><span class="sxs-lookup"><span data-stu-id="9cf68-173">In the tree, select 'Sample data model'.</span></span>
2. <span data-ttu-id="9cf68-174">Cliquez sur Créer la configuration pour ouvrir la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="9cf68-174">Click Create configuration to open the drop dialog.</span></span>
3. <span data-ttu-id="9cf68-175">Dans le champ Nouveau, entrez « Format basé sur le modèle de données Exemple de modèle de données ».</span><span class="sxs-lookup"><span data-stu-id="9cf68-175">In the New field, enter 'Format based on data model Sample data model'.</span></span>
4. <span data-ttu-id="9cf68-176">Dans le champ Nom, tapez « Exemple de format ».</span><span class="sxs-lookup"><span data-stu-id="9cf68-176">In the Name field, type 'Sample format'.</span></span>
    * <span data-ttu-id="9cf68-177">Exemple de format</span><span class="sxs-lookup"><span data-stu-id="9cf68-177">Sample format</span></span>  
5. <span data-ttu-id="9cf68-178">Cliquez sur Créer une configuration.</span><span class="sxs-lookup"><span data-stu-id="9cf68-178">Click Create configuration.</span></span>
6. <span data-ttu-id="9cf68-179">Cliquez sur Concepteur.</span><span class="sxs-lookup"><span data-stu-id="9cf68-179">Click Designer.</span></span>
7. <span data-ttu-id="9cf68-180">Cliquez sur Ajouter racine pour ouvrir la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="9cf68-180">Click Add root to open the drop dialog.</span></span>
8. <span data-ttu-id="9cf68-181">Dans l'arborescence, sélectionnez « Texte\Chaîne ».</span><span class="sxs-lookup"><span data-stu-id="9cf68-181">In the tree, select 'Text\String'.</span></span>
9. <span data-ttu-id="9cf68-182">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="9cf68-182">Click OK.</span></span>
10. <span data-ttu-id="9cf68-183">Cliquez sur l'onglet Mise en relation.</span><span class="sxs-lookup"><span data-stu-id="9cf68-183">Click the Mapping tab.</span></span>
11. <span data-ttu-id="9cf68-184">Dans l'arborescence , développez « model ».</span><span class="sxs-lookup"><span data-stu-id="9cf68-184">In the tree, expand 'model'.</span></span>
12. <span data-ttu-id="9cf68-185">Dans l'arborescence, sélectionnez « model\Company ».</span><span class="sxs-lookup"><span data-stu-id="9cf68-185">In the tree, select 'model\Company'.</span></span>
13. <span data-ttu-id="9cf68-186">Cliquez sur Lier.</span><span class="sxs-lookup"><span data-stu-id="9cf68-186">Click Bind.</span></span>
14. <span data-ttu-id="9cf68-187">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="9cf68-187">Click Save.</span></span>
15. <span data-ttu-id="9cf68-188">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="9cf68-188">Close the page.</span></span>
    * <span data-ttu-id="9cf68-189">Exécutez la version brouillon du format créé à des fins de test.</span><span class="sxs-lookup"><span data-stu-id="9cf68-189">Run the draft version of the created format for testing purposes.</span></span>  
16. <span data-ttu-id="9cf68-190">Cliquez sur Exécuter.</span><span class="sxs-lookup"><span data-stu-id="9cf68-190">Click Run.</span></span>
    * <span data-ttu-id="9cf68-191">Dans l'organisateur Versions, cliquez sur Exécuter.</span><span class="sxs-lookup"><span data-stu-id="9cf68-191">On the Versions FastTab, click Run.</span></span>  
17. <span data-ttu-id="9cf68-192">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="9cf68-192">Click OK.</span></span>
    * <span data-ttu-id="9cf68-193">Examinez la sortie qui contient le nom de la société dans laquelle l'utilisateur exécutant cette configuration de format est connecté.</span><span class="sxs-lookup"><span data-stu-id="9cf68-193">Review the output that contains the name of the company in which the user who is running this format configuration is logged into.</span></span> <span data-ttu-id="9cf68-194">Notez que la configuration de mise en correspondance de modèle créée est utilisée par cette configuration de format, car une seule configuration disponible contient les mises en correspondance de modèle requises.</span><span class="sxs-lookup"><span data-stu-id="9cf68-194">Note that the created model mapping configuration is used by this format configuration because there is only one configuration available that contains required model mappings.</span></span>   

## <a name="add-alternative-er-model-mapping-configuration"></a><span data-ttu-id="9cf68-195">Ajouter une autre configuration de mise en correspondance de modèle ER</span><span class="sxs-lookup"><span data-stu-id="9cf68-195">Add alternative ER model mapping configuration</span></span>
1. <span data-ttu-id="9cf68-196">Dans l'arborescence, sélectionnez « Exemple de modèle de données ».</span><span class="sxs-lookup"><span data-stu-id="9cf68-196">In the tree, select 'Sample data model'.</span></span>
2. <span data-ttu-id="9cf68-197">Cliquez sur Créer la configuration pour ouvrir la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="9cf68-197">Click Create configuration to open the drop dialog.</span></span>
3. <span data-ttu-id="9cf68-198">Dans le champ Nouveau, entrez « Mise en correspondance de modèle basée sur le modèle de données Exemple de modèle de données ».</span><span class="sxs-lookup"><span data-stu-id="9cf68-198">In the New field, enter 'Model Mapping based on data model Sample data model'.</span></span>
4. <span data-ttu-id="9cf68-199">Dans le champ Nom, tapez « Exemple de mise en correspondance (autre) ».</span><span class="sxs-lookup"><span data-stu-id="9cf68-199">In the Name field, type 'Sample mapping (alternative)'.</span></span>
    * <span data-ttu-id="9cf68-200">Exemple de mise en correspondance (autre)</span><span class="sxs-lookup"><span data-stu-id="9cf68-200">Sample mapping (alternative)</span></span>  
5. <span data-ttu-id="9cf68-201">Cliquez sur Créer une configuration.</span><span class="sxs-lookup"><span data-stu-id="9cf68-201">Click Create configuration.</span></span>
6. <span data-ttu-id="9cf68-202">Cliquez sur Concepteur.</span><span class="sxs-lookup"><span data-stu-id="9cf68-202">Click Designer.</span></span>
7. <span data-ttu-id="9cf68-203">Cliquez sur Concepteur.</span><span class="sxs-lookup"><span data-stu-id="9cf68-203">Click Designer.</span></span>
8. <span data-ttu-id="9cf68-204">Dans l'arborescence, sélectionnez « Dynamics 365 for Operations\Table ».</span><span class="sxs-lookup"><span data-stu-id="9cf68-204">In the tree, select 'Dynamics 365 for Operations\Table'.</span></span>
9. <span data-ttu-id="9cf68-205">Cliquez sur Ajouter racine.</span><span class="sxs-lookup"><span data-stu-id="9cf68-205">Click Add root.</span></span>
10. <span data-ttu-id="9cf68-206">Dans le champ Nom, tapez « Société ».</span><span class="sxs-lookup"><span data-stu-id="9cf68-206">In the Name field, type 'Company'.</span></span>
    * <span data-ttu-id="9cf68-207">Société</span><span class="sxs-lookup"><span data-stu-id="9cf68-207">Company</span></span>  
11. <span data-ttu-id="9cf68-208">Dans le champ Table, tapez « CompanyInfo ».</span><span class="sxs-lookup"><span data-stu-id="9cf68-208">In the Table field, type 'CompanyInfo'.</span></span>
    * <span data-ttu-id="9cf68-209">CompanyInfo</span><span class="sxs-lookup"><span data-stu-id="9cf68-209">CompanyInfo</span></span>  
12. <span data-ttu-id="9cf68-210">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="9cf68-210">Click OK.</span></span>
13. <span data-ttu-id="9cf68-211">Cliquez sur Modifier.</span><span class="sxs-lookup"><span data-stu-id="9cf68-211">Click Edit.</span></span>
14. <span data-ttu-id="9cf68-212">Dans l'arborescence, sélectionner « String\CONCATENATE ».</span><span class="sxs-lookup"><span data-stu-id="9cf68-212">In the tree, select 'String\CONCATENATE'.</span></span>
15. <span data-ttu-id="9cf68-213">Cliquez sur Ajouter une fonction.</span><span class="sxs-lookup"><span data-stu-id="9cf68-213">Click Add function.</span></span>
16. <span data-ttu-id="9cf68-214">Dans l'arborescence, développez « Société ».</span><span class="sxs-lookup"><span data-stu-id="9cf68-214">In the tree, expand 'Company'.</span></span>
17. <span data-ttu-id="9cf68-215">Dans l'arborescence, développez « Company\find() ».</span><span class="sxs-lookup"><span data-stu-id="9cf68-215">In the tree, expand 'Company\find()'.</span></span>
18. <span data-ttu-id="9cf68-216">Dans l'arborescence, sélectionnez « Company\find()\Name ».</span><span class="sxs-lookup"><span data-stu-id="9cf68-216">In the tree, select 'Company\find()\Name'.</span></span>
19. <span data-ttu-id="9cf68-217">Cliquez sur Ajouter une source de données.</span><span class="sxs-lookup"><span data-stu-id="9cf68-217">Click Add data source.</span></span>
20. <span data-ttu-id="9cf68-218">Dans le champ Formule, tapez une valeur.</span><span class="sxs-lookup"><span data-stu-id="9cf68-218">In the Formula field, type a value.</span></span>
    * <span data-ttu-id="9cf68-219">CONCATENATE(Company.'find()'.Name, ";",</span><span class="sxs-lookup"><span data-stu-id="9cf68-219">CONCATENATE(Company.'find()'.Name, ";",</span></span>  
21. <span data-ttu-id="9cf68-220">Dans l'arborescence, sélectionnez « Company\find()\Company(DataArea) ».</span><span class="sxs-lookup"><span data-stu-id="9cf68-220">In the tree, select 'Company\find()\Company(DataArea)'.</span></span>
22. <span data-ttu-id="9cf68-221">Cliquez sur Ajouter une source de données.</span><span class="sxs-lookup"><span data-stu-id="9cf68-221">Click Add data source.</span></span>
23. <span data-ttu-id="9cf68-222">Dans le champ Formule, tapez une valeur.</span><span class="sxs-lookup"><span data-stu-id="9cf68-222">In the Formula field, type a value.</span></span>
    * <span data-ttu-id="9cf68-223">CONCATENATE(Company.'find()'.Name, ";", Company.'find()'.DataArea)</span><span class="sxs-lookup"><span data-stu-id="9cf68-223">CONCATENATE(Company.'find()'.Name, ";", Company.'find()'.DataArea)</span></span>  
24. <span data-ttu-id="9cf68-224">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="9cf68-224">Click Save.</span></span>
25. <span data-ttu-id="9cf68-225">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="9cf68-225">Close the page.</span></span>
26. <span data-ttu-id="9cf68-226">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="9cf68-226">Click Save.</span></span>
27. <span data-ttu-id="9cf68-227">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="9cf68-227">Close the page.</span></span>
28. <span data-ttu-id="9cf68-228">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="9cf68-228">Close the page.</span></span>
29. <span data-ttu-id="9cf68-229">Sélectionnez Oui dans le champ Exécuter le brouillon.</span><span class="sxs-lookup"><span data-stu-id="9cf68-229">Select Yes in the Run Draft field.</span></span>

## <a name="use-an-existing-er-model-mapping-configuration"></a><span data-ttu-id="9cf68-230">Utiliser une configuration de mise en correspondance de modèle ER existante</span><span class="sxs-lookup"><span data-stu-id="9cf68-230">Use an existing ER model mapping configuration</span></span>
1. <span data-ttu-id="9cf68-231">Dans l'arborescence, sélectionnez « Exemple de modèle de données\Exemple de format ».</span><span class="sxs-lookup"><span data-stu-id="9cf68-231">In the tree, select 'Sample data model\Sample format'.</span></span>
2. <span data-ttu-id="9cf68-232">Cliquez sur Exécuter.</span><span class="sxs-lookup"><span data-stu-id="9cf68-232">Click Run.</span></span>
    * <span data-ttu-id="9cf68-233">Notez que la version brouillon sélectionnée de la configuration du format ER ne peut pas être exécutée, car plusieurs configurations de mise en correspondance de modèle sont disponibles pour le modèle de données non défini qui a été sélectionné comme source de données du format ER en cours d'exécution.</span><span class="sxs-lookup"><span data-stu-id="9cf68-233">Note that the selected draft version of the ER format configuration can’t be executed because there is more than one model mapping configuration available for the undefined data model that has been selected as the data source of the running ER format.</span></span>   
    * <span data-ttu-id="9cf68-234">Ensuite, vous définirez l'autre configuration de mise en correspondance de modèle comme celle à partir de laquelle les mises en correspondance de modèle seront utilisées comme sources de données du format ER en cours d'exécution.</span><span class="sxs-lookup"><span data-stu-id="9cf68-234">Next, you will define the alternative model mapping configuration as the one from which model mappings will be used as data sources for running ER format.</span></span>   
3. <span data-ttu-id="9cf68-235">Dans l'arborescence, sélectionnez « Exemple de modèle de données\Exemple de mise en correspondance (autre) ».</span><span class="sxs-lookup"><span data-stu-id="9cf68-235">In the tree, select 'Sample data model\Sample mapping (alternative)'.</span></span>
4. <span data-ttu-id="9cf68-236">Sélectionnez Oui dans le champ Valeur par défaut de la mise en correspondance des modèles.</span><span class="sxs-lookup"><span data-stu-id="9cf68-236">Select Yes in the Default for model mapping field.</span></span>
5. <span data-ttu-id="9cf68-237">Dans l'arborescence, sélectionnez « Exemple de modèle de données\Exemple de format ».</span><span class="sxs-lookup"><span data-stu-id="9cf68-237">In the tree, select 'Sample data model\Sample format'.</span></span>
6. <span data-ttu-id="9cf68-238">Cliquez sur Exécuter.</span><span class="sxs-lookup"><span data-stu-id="9cf68-238">Click Run.</span></span>
7. <span data-ttu-id="9cf68-239">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="9cf68-239">Click OK.</span></span>
    * <span data-ttu-id="9cf68-240">Notez que la configuration de mise en correspondance de modèle par défaut est utilisée par cette configuration de format pour générer le document électronique (la sortie créée contient le code de la société).</span><span class="sxs-lookup"><span data-stu-id="9cf68-240">Note that the default model mapping configuration is used by this format configuration for generating the electronic document (the created output contains the company code).</span></span>  


