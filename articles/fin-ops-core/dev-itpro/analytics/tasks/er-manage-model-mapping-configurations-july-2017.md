---
title: Gérer la mise en correspondance de modèle de gestion des états électroniques dans des configurations ER distinctes
description: Cette rubrique décrit comment gérer la mise en correspondance des modèles de gestion des états électroniques dans des configurations de gestion des états électroniques distinctes.
author: NickSelin
manager: AnnBe
ms.date: 06/19/2017
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 2f1013cfc9f421525fb0661cd5ace5eeaa157f9a
ms.sourcegitcommit: 5192cfaedfd861faea63d8954d7bcc500608a225
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/30/2021
ms.locfileid: "5093796"
---
# <a name="manage-er-model-mapping-in-separate-er-configurations"></a><span data-ttu-id="bec25-103">Gérer la mise en correspondance de modèle de gestion d’états électroniques dans des configurations de gestion d’états électroniques distinctes</span><span class="sxs-lookup"><span data-stu-id="bec25-103">Manage ER model mapping in separate ER configurations</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="bec25-104">Les étapes suivantes expliquent comment un utilisateur affecté au rôle d’administrateur système ou de développeur d’états électroniques peut gérer des mises en correspondance de modèle d’états électroniques dans des configurations ER distinctes.</span><span class="sxs-lookup"><span data-stu-id="bec25-104">The following steps explain how a user assigned to the System administrator or Electronic reporting developer role can manage Electronic reporting (ER) model mappings in separate ER configurations.</span></span> <span data-ttu-id="bec25-105">Dans ce guide de tâche, vous allez créer les configurations ER requises pour l’exemple de société, Litware, Inc. Pour réaliser les étapes de ce guide de tâche, vous devez d’abord effectuer les étapes du guide de tâche, « ER Créer un fournisseur de configuration et le marquer comme actif ».</span><span class="sxs-lookup"><span data-stu-id="bec25-105">In this task guide, you will create required ER configurations for the sample company, Litware, Inc. To complete this task guide, you must first complete the steps in the task guide, "ER Create a configuration provider" and mark it as active.</span></span> 

<span data-ttu-id="bec25-106">Comme les configurations ER sont partagées entre les sociétés, vous pouvez réaliser les étapes de ce guide de tâche en utilisant l’ensemble de données de société de votre choix.</span><span class="sxs-lookup"><span data-stu-id="bec25-106">Because ER configurations are shared among companies, you can complete this task guide using the company data set of your choice.</span></span> <span data-ttu-id="bec25-107">La fonctionnalité de ce guide de tâche est disponible si vous avez installé l’un des correctifs suivants : https://fix.lcs.dynamics.com/Issue/Resolved?kb=4012872 pour la version 7.0 de Dynamics AX ou https://fix.lcs.dynamics.com/Issue/Resolved?kb=4012871 pour la version Dynamics 365 for Operations.</span><span class="sxs-lookup"><span data-stu-id="bec25-107">The functionality for this task guide is available if you have installed one of the following hotfixes: https://fix.lcs.dynamics.com/Issue/Resolved?kb=4012872 for the Dynamics AX 7.0 version or https://fix.lcs.dynamics.com/Issue/Resolved?kb=4012871 for the Dynamics 365 for Operations version.</span></span>

1. <span data-ttu-id="bec25-108">Accédez à Administration d’organisation > Espaces de travail > États électroniques.</span><span class="sxs-lookup"><span data-stu-id="bec25-108">Go to Organization administration > Workspaces > Electronic reporting.</span></span>
    * <span data-ttu-id="bec25-109">Vérifiez que le fournisseur de la configuration pour la société fictive Litware, Inc. est disponible et marqué comme actif.</span><span class="sxs-lookup"><span data-stu-id="bec25-109">Verify that the configuration provider for the sample company Litware, Inc. is available and marked as active.</span></span> <span data-ttu-id="bec25-110">Si ce fournisseur de configuration ne s’affiche pas, vous devez d’abord effectuer les étapes du guide de tâche, Créer un fournisseur de configuration et le marquer comme actif.</span><span class="sxs-lookup"><span data-stu-id="bec25-110">If you don't see this configuration provider, you must first complete the steps in the task guide, Create a configuration provider, and mark it as active.</span></span>   

## <a name="add-a-new-er-model-configuration"></a><span data-ttu-id="bec25-111">Ajouter une nouvelle configuration du modèle ER</span><span class="sxs-lookup"><span data-stu-id="bec25-111">Add a new ER model configuration</span></span>
1. <span data-ttu-id="bec25-112">Cliquez sur Configurations des états.</span><span class="sxs-lookup"><span data-stu-id="bec25-112">Click Reporting configurations.</span></span>
    * <span data-ttu-id="bec25-113">Ajoutez une nouvelle configuration du modèle.</span><span class="sxs-lookup"><span data-stu-id="bec25-113">Add a new model configuration.</span></span> <span data-ttu-id="bec25-114">Le nom doit être unique dans l’arborescence de configurations.</span><span class="sxs-lookup"><span data-stu-id="bec25-114">The name must be unique in the configurations tree.</span></span>  
2. <span data-ttu-id="bec25-115">Cliquez sur Créer la configuration pour ouvrir la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="bec25-115">Click Create configuration to open the drop dialog.</span></span>
3. <span data-ttu-id="bec25-116">Dans le champ Nom, tapez « Exemple de modèle de données ».</span><span class="sxs-lookup"><span data-stu-id="bec25-116">In the Name field, type 'Sample data model'.</span></span>
    * <span data-ttu-id="bec25-117">Exemple de modèle de données</span><span class="sxs-lookup"><span data-stu-id="bec25-117">Sample data model</span></span>  
4. <span data-ttu-id="bec25-118">Cliquez sur Créer une configuration.</span><span class="sxs-lookup"><span data-stu-id="bec25-118">Click Create configuration.</span></span>
5. <span data-ttu-id="bec25-119">Cliquez sur Concepteur.</span><span class="sxs-lookup"><span data-stu-id="bec25-119">Click Designer.</span></span>
6. <span data-ttu-id="bec25-120">Cliquez sur Nouveau pour ouvrir la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="bec25-120">Click New to open the drop dialog.</span></span>
7. <span data-ttu-id="bec25-121">Dans le champ Nom, tapez « Racine ».</span><span class="sxs-lookup"><span data-stu-id="bec25-121">In the Name field, type 'Root'.</span></span>
    * <span data-ttu-id="bec25-122">Racine</span><span class="sxs-lookup"><span data-stu-id="bec25-122">Root</span></span>  
8. <span data-ttu-id="bec25-123">Cliquez sur Ajouter.</span><span class="sxs-lookup"><span data-stu-id="bec25-123">Click Add.</span></span>
9. <span data-ttu-id="bec25-124">Cliquez sur Nouveau pour ouvrir la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="bec25-124">Click New to open the drop dialog.</span></span>
10. <span data-ttu-id="bec25-125">Dans le champ Nom, tapez « Société ».</span><span class="sxs-lookup"><span data-stu-id="bec25-125">In the Name field, type 'Company'.</span></span>
    * <span data-ttu-id="bec25-126">Société</span><span class="sxs-lookup"><span data-stu-id="bec25-126">Company</span></span>  
11. <span data-ttu-id="bec25-127">Cliquez sur Ajouter.</span><span class="sxs-lookup"><span data-stu-id="bec25-127">Click Add.</span></span>
12. <span data-ttu-id="bec25-128">Dans le champ Description, entrez le texte, Description de l’entité juridique ou de la société à laquelle un utilisateur est connecté au moment de l’exécution.</span><span class="sxs-lookup"><span data-stu-id="bec25-128">In the Description field, enter the text, Description of the legal entity or company in which a user logged at run-time.</span></span> 
    * <span data-ttu-id="bec25-129">Description de l’entité juridique ou de la société à laquelle un utilisateur est connecté au moment de l’exécution.</span><span class="sxs-lookup"><span data-stu-id="bec25-129">Description of the legal entity or company in which a user logged at run-time.</span></span>  
13. <span data-ttu-id="bec25-130">Cliquez sur Référence racine.</span><span class="sxs-lookup"><span data-stu-id="bec25-130">Click Root reference.</span></span>
14. <span data-ttu-id="bec25-131">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="bec25-131">Click OK.</span></span>
15. <span data-ttu-id="bec25-132">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="bec25-132">Click Save.</span></span>
16. <span data-ttu-id="bec25-133">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="bec25-133">Close the page.</span></span>
17. <span data-ttu-id="bec25-134">Cliquez sur Modifier le statut.</span><span class="sxs-lookup"><span data-stu-id="bec25-134">Click Change status.</span></span>
18. <span data-ttu-id="bec25-135">Cliquez sur Terminé.</span><span class="sxs-lookup"><span data-stu-id="bec25-135">Click Complete.</span></span>
19. <span data-ttu-id="bec25-136">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="bec25-136">Click OK.</span></span>

## <a name="add-a-new-er-model-mapping-configuration"></a><span data-ttu-id="bec25-137">Ajouter une nouvelle configuration de mise en correspondance du modèle de données ER</span><span class="sxs-lookup"><span data-stu-id="bec25-137">Add a new ER model-mapping configuration</span></span>
1. <span data-ttu-id="bec25-138">Cliquez sur Créer la configuration pour ouvrir la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="bec25-138">Click Create configuration to open the drop dialog.</span></span>
2. <span data-ttu-id="bec25-139">Dans le champ Nouveau, entrez « Mise en correspondance de modèle basée sur le modèle de données Exemple de modèle de données ».</span><span class="sxs-lookup"><span data-stu-id="bec25-139">In the New field, enter 'Model Mapping based on data model Sample data model'.</span></span>
3. <span data-ttu-id="bec25-140">Dans le champ Nom, tapez « Exemple de mise en correspondance ».</span><span class="sxs-lookup"><span data-stu-id="bec25-140">In the Name field, type 'Sample mapping'.</span></span>
    * <span data-ttu-id="bec25-141">Exemple de mise en correspondance</span><span class="sxs-lookup"><span data-stu-id="bec25-141">Sample mapping</span></span>  
4. <span data-ttu-id="bec25-142">Cliquez sur Créer une configuration.</span><span class="sxs-lookup"><span data-stu-id="bec25-142">Click Create configuration.</span></span>
5. <span data-ttu-id="bec25-143">Développez la section Conditions préalables.</span><span class="sxs-lookup"><span data-stu-id="bec25-143">Expand the Prerequisites section.</span></span>
    * <span data-ttu-id="bec25-144">Le groupe de composants prérequis Implémentations a été ajouté automatiquement.</span><span class="sxs-lookup"><span data-stu-id="bec25-144">The Implementations prerequisites group has been added automatically.</span></span> <span data-ttu-id="bec25-145">Le groupe contient le composant prérequis qui fait référence à la configuration de modèle de données parent et est marqué comme implémentation.</span><span class="sxs-lookup"><span data-stu-id="bec25-145">The group contains the prerequisite component that refers to the parent data model configuration and is marked as Implementation.</span></span> <span data-ttu-id="bec25-146">Cela signifie que cette configuration de mise en correspondance de modèle Exemple de mise en correspondance est considérée comme l’implémentation du modèle de données, Exemple de modèle de données.</span><span class="sxs-lookup"><span data-stu-id="bec25-146">This means that this Sample-mapping model-mapping configuration is considered the implementation of the data model, Sample data model.</span></span> <span data-ttu-id="bec25-147">Par conséquent, ce composant forcera ER à télécharger la configuration de mise en correspondance de modèle, Exemple de mise en correspondance, à partir d’un référentiel ER lorsque la configuration de modèle, Exemple de modèle de données, est téléchargée.</span><span class="sxs-lookup"><span data-stu-id="bec25-147">Therefore, this component will force ER to download the model-mapping configuration, Sample mapping from an ER repository when the model configuration, Sample data model, is downloaded.</span></span>   
6. <span data-ttu-id="bec25-148">Cliquez sur Concepteur.</span><span class="sxs-lookup"><span data-stu-id="bec25-148">Click Designer.</span></span>
    * <span data-ttu-id="bec25-149">La configuration de mise en correspondance de modèle créée contient une nouvelle mise en correspondance vide portant le même nom que la configuration créée.</span><span class="sxs-lookup"><span data-stu-id="bec25-149">The created model-mapping configuration contains a new blank mapping with the same name as the created configuration.</span></span> <span data-ttu-id="bec25-150">Lorsqu’une configuration de modèle parent sélectionnée contient des mises en correspondance de modèle, celles-ci sont copiées dans une nouvelle configuration de mise en correspondance de modèle.</span><span class="sxs-lookup"><span data-stu-id="bec25-150">When a selected parent model configuration contains model mappings, they will be copied to a new model-mapping configuration.</span></span>   
7. <span data-ttu-id="bec25-151">Cliquez sur Concepteur.</span><span class="sxs-lookup"><span data-stu-id="bec25-151">Click Designer.</span></span>
8. <span data-ttu-id="bec25-152">Dans l’arborescence, sélectionnez « Dynamics 365 for Operations\Table ».</span><span class="sxs-lookup"><span data-stu-id="bec25-152">In the tree, select 'Dynamics 365 for Operations\Table'.</span></span>
9. <span data-ttu-id="bec25-153">Cliquez sur Ajouter racine.</span><span class="sxs-lookup"><span data-stu-id="bec25-153">Click Add root.</span></span>
10. <span data-ttu-id="bec25-154">Dans le champ Nom, tapez « Société ».</span><span class="sxs-lookup"><span data-stu-id="bec25-154">In the Name field, type 'Company'.</span></span>
    * <span data-ttu-id="bec25-155">Société</span><span class="sxs-lookup"><span data-stu-id="bec25-155">Company</span></span>  
11. <span data-ttu-id="bec25-156">Dans le champ Table, tapez « CompanyInfo ».</span><span class="sxs-lookup"><span data-stu-id="bec25-156">In the Table field, type 'CompanyInfo'.</span></span>
    * <span data-ttu-id="bec25-157">CompanyInfo</span><span class="sxs-lookup"><span data-stu-id="bec25-157">CompanyInfo</span></span>  
12. <span data-ttu-id="bec25-158">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="bec25-158">Click OK.</span></span>
13. <span data-ttu-id="bec25-159">Dans l’arborescence, développez « Société ».</span><span class="sxs-lookup"><span data-stu-id="bec25-159">In the tree, expand 'Company'.</span></span>
14. <span data-ttu-id="bec25-160">Dans l’arborescence, développez « Company\find() ».</span><span class="sxs-lookup"><span data-stu-id="bec25-160">In the tree, expand 'Company\find()'.</span></span>
15. <span data-ttu-id="bec25-161">Dans l’arborescence, sélectionnez « Company\find()\Name ».</span><span class="sxs-lookup"><span data-stu-id="bec25-161">In the tree, select 'Company\find()\Name'.</span></span>
16. <span data-ttu-id="bec25-162">Cliquez sur Lier.</span><span class="sxs-lookup"><span data-stu-id="bec25-162">Click Bind.</span></span>
17. <span data-ttu-id="bec25-163">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="bec25-163">Click Save.</span></span>
18. <span data-ttu-id="bec25-164">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="bec25-164">Close the page.</span></span>
19. <span data-ttu-id="bec25-165">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="bec25-165">Close the page.</span></span>
20. <span data-ttu-id="bec25-166">Dans le volet Actions, cliquez sur Configurations.</span><span class="sxs-lookup"><span data-stu-id="bec25-166">On the Action Pane, click Configurations.</span></span>
21. <span data-ttu-id="bec25-167">Cliquez sur Paramètres utilisateur.</span><span class="sxs-lookup"><span data-stu-id="bec25-167">Click User parameters.</span></span>
22. <span data-ttu-id="bec25-168">Sélectionnez Oui dans le champ Paramètres d’exécution.</span><span class="sxs-lookup"><span data-stu-id="bec25-168">Select Yes in the Run settings field.</span></span>
23. <span data-ttu-id="bec25-169">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="bec25-169">Click OK.</span></span>
24. <span data-ttu-id="bec25-170">Cliquez sur Modifier.</span><span class="sxs-lookup"><span data-stu-id="bec25-170">Click Edit.</span></span>
25. <span data-ttu-id="bec25-171">Sélectionnez Oui dans le champ Exécuter le brouillon.</span><span class="sxs-lookup"><span data-stu-id="bec25-171">Select Yes in the Run Draft field.</span></span>

## <a name="add-a-new-er-format-configuration"></a><span data-ttu-id="bec25-172">Ajouter une nouvelle configuration du format ER</span><span class="sxs-lookup"><span data-stu-id="bec25-172">Add a new ER format configuration</span></span>
1. <span data-ttu-id="bec25-173">Dans l’arborescence, sélectionnez « Exemple de modèle de données ».</span><span class="sxs-lookup"><span data-stu-id="bec25-173">In the tree, select 'Sample data model'.</span></span>
2. <span data-ttu-id="bec25-174">Cliquez sur Créer la configuration pour ouvrir la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="bec25-174">Click Create configuration to open the drop dialog.</span></span>
3. <span data-ttu-id="bec25-175">Dans le champ Nouveau, entrez « Format basé sur le modèle de données Exemple de modèle de données ».</span><span class="sxs-lookup"><span data-stu-id="bec25-175">In the New field, enter 'Format based on data model Sample data model'.</span></span>
4. <span data-ttu-id="bec25-176">Dans le champ Nom, tapez « Exemple de format ».</span><span class="sxs-lookup"><span data-stu-id="bec25-176">In the Name field, type 'Sample format'.</span></span>
    * <span data-ttu-id="bec25-177">Exemple de format</span><span class="sxs-lookup"><span data-stu-id="bec25-177">Sample format</span></span>  
5. <span data-ttu-id="bec25-178">Cliquez sur Créer une configuration.</span><span class="sxs-lookup"><span data-stu-id="bec25-178">Click Create configuration.</span></span>
6. <span data-ttu-id="bec25-179">Cliquez sur Concepteur.</span><span class="sxs-lookup"><span data-stu-id="bec25-179">Click Designer.</span></span>
7. <span data-ttu-id="bec25-180">Cliquez sur Ajouter racine pour ouvrir la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="bec25-180">Click Add root to open the drop dialog.</span></span>
8. <span data-ttu-id="bec25-181">Dans l’arborescence, sélectionnez « Texte\Chaîne ».</span><span class="sxs-lookup"><span data-stu-id="bec25-181">In the tree, select 'Text\String'.</span></span>
9. <span data-ttu-id="bec25-182">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="bec25-182">Click OK.</span></span>
10. <span data-ttu-id="bec25-183">Cliquez sur l’onglet Mise en relation.</span><span class="sxs-lookup"><span data-stu-id="bec25-183">Click the Mapping tab.</span></span>
11. <span data-ttu-id="bec25-184">Dans l’arborescence , développez « model ».</span><span class="sxs-lookup"><span data-stu-id="bec25-184">In the tree, expand 'model'.</span></span>
12. <span data-ttu-id="bec25-185">Dans l’arborescence, sélectionnez « model\Company ».</span><span class="sxs-lookup"><span data-stu-id="bec25-185">In the tree, select 'model\Company'.</span></span>
13. <span data-ttu-id="bec25-186">Cliquez sur Lier.</span><span class="sxs-lookup"><span data-stu-id="bec25-186">Click Bind.</span></span>
14. <span data-ttu-id="bec25-187">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="bec25-187">Click Save.</span></span>
15. <span data-ttu-id="bec25-188">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="bec25-188">Close the page.</span></span>
    * <span data-ttu-id="bec25-189">Exécutez la version brouillon du format créé à des fins de test.</span><span class="sxs-lookup"><span data-stu-id="bec25-189">Run the draft version of the created format for testing purposes.</span></span>  
16. <span data-ttu-id="bec25-190">Cliquez sur Exécuter.</span><span class="sxs-lookup"><span data-stu-id="bec25-190">Click Run.</span></span>
    * <span data-ttu-id="bec25-191">Dans l’organisateur Versions, cliquez sur Exécuter.</span><span class="sxs-lookup"><span data-stu-id="bec25-191">On the Versions FastTab, click Run.</span></span>  
17. <span data-ttu-id="bec25-192">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="bec25-192">Click OK.</span></span>
    * <span data-ttu-id="bec25-193">Examinez la sortie qui contient le nom de la société dans laquelle l’utilisateur exécutant cette configuration de format est connecté.</span><span class="sxs-lookup"><span data-stu-id="bec25-193">Review the output that contains the name of the company in which the user who is running this format configuration is logged into.</span></span> <span data-ttu-id="bec25-194">La configuration de mise en correspondance de modèle créée est utilisée par cette configuration de format, car une seule configuration disponible contient les mises en correspondance de modèle requises.</span><span class="sxs-lookup"><span data-stu-id="bec25-194">The created model-mapping configuration is used by this format configuration because there is only one configuration available that contains required model mappings.</span></span>   

## <a name="add-alternative-er-model-mapping-configuration"></a><span data-ttu-id="bec25-195">Ajouter une autre configuration de mise en correspondance de modèle ER</span><span class="sxs-lookup"><span data-stu-id="bec25-195">Add alternative ER model-mapping configuration</span></span>
1. <span data-ttu-id="bec25-196">Dans l’arborescence, sélectionnez « Exemple de modèle de données ».</span><span class="sxs-lookup"><span data-stu-id="bec25-196">In the tree, select 'Sample data model'.</span></span>
2. <span data-ttu-id="bec25-197">Cliquez sur Créer la configuration pour ouvrir la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="bec25-197">Click Create configuration to open the drop dialog.</span></span>
3. <span data-ttu-id="bec25-198">Dans le champ Nouveau, entrez « Mise en correspondance de modèle basée sur le modèle de données Exemple de modèle de données ».</span><span class="sxs-lookup"><span data-stu-id="bec25-198">In the New field, enter 'Model Mapping based on data model Sample data model'.</span></span>
4. <span data-ttu-id="bec25-199">Dans le champ Nom, tapez « Exemple de mise en correspondance (autre) ».</span><span class="sxs-lookup"><span data-stu-id="bec25-199">In the Name field, type 'Sample mapping (alternative)'.</span></span>
    * <span data-ttu-id="bec25-200">Exemple de mise en correspondance (autre)</span><span class="sxs-lookup"><span data-stu-id="bec25-200">Sample mapping (alternative)</span></span>  
5. <span data-ttu-id="bec25-201">Cliquez sur Créer une configuration.</span><span class="sxs-lookup"><span data-stu-id="bec25-201">Click Create configuration.</span></span>
6. <span data-ttu-id="bec25-202">Cliquez sur Concepteur.</span><span class="sxs-lookup"><span data-stu-id="bec25-202">Click Designer.</span></span>
7. <span data-ttu-id="bec25-203">Cliquez sur Concepteur.</span><span class="sxs-lookup"><span data-stu-id="bec25-203">Click Designer.</span></span>
8. <span data-ttu-id="bec25-204">Dans l’arborescence, sélectionnez « Dynamics 365 for Operations\Table ».</span><span class="sxs-lookup"><span data-stu-id="bec25-204">In the tree, select 'Dynamics 365 for Operations\Table'.</span></span>
9. <span data-ttu-id="bec25-205">Cliquez sur Ajouter racine.</span><span class="sxs-lookup"><span data-stu-id="bec25-205">Click Add root.</span></span>
10. <span data-ttu-id="bec25-206">Dans le champ Nom, tapez « Société ».</span><span class="sxs-lookup"><span data-stu-id="bec25-206">In the Name field, type 'Company'.</span></span>
    * <span data-ttu-id="bec25-207">Société</span><span class="sxs-lookup"><span data-stu-id="bec25-207">Company</span></span>  
11. <span data-ttu-id="bec25-208">Dans le champ Table, tapez « CompanyInfo ».</span><span class="sxs-lookup"><span data-stu-id="bec25-208">In the Table field, type 'CompanyInfo'.</span></span>
    * <span data-ttu-id="bec25-209">CompanyInfo</span><span class="sxs-lookup"><span data-stu-id="bec25-209">CompanyInfo</span></span>  
12. <span data-ttu-id="bec25-210">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="bec25-210">Click OK.</span></span>
13. <span data-ttu-id="bec25-211">Cliquez sur Modifier.</span><span class="sxs-lookup"><span data-stu-id="bec25-211">Click Edit.</span></span>
14. <span data-ttu-id="bec25-212">Dans l’arborescence, sélectionner « String\CONCATENATE ».</span><span class="sxs-lookup"><span data-stu-id="bec25-212">In the tree, select 'String\CONCATENATE'.</span></span>
15. <span data-ttu-id="bec25-213">Cliquez sur Ajouter une fonction.</span><span class="sxs-lookup"><span data-stu-id="bec25-213">Click Add function.</span></span>
16. <span data-ttu-id="bec25-214">Dans l’arborescence, développez « Société ».</span><span class="sxs-lookup"><span data-stu-id="bec25-214">In the tree, expand 'Company'.</span></span>
17. <span data-ttu-id="bec25-215">Dans l’arborescence, développez « Company\find() ».</span><span class="sxs-lookup"><span data-stu-id="bec25-215">In the tree, expand 'Company\find()'.</span></span>
18. <span data-ttu-id="bec25-216">Dans l’arborescence, sélectionnez « Company\find()\Name ».</span><span class="sxs-lookup"><span data-stu-id="bec25-216">In the tree, select 'Company\find()\Name'.</span></span>
19. <span data-ttu-id="bec25-217">Cliquez sur Ajouter une source de données.</span><span class="sxs-lookup"><span data-stu-id="bec25-217">Click Add data source.</span></span>
20. <span data-ttu-id="bec25-218">Dans le champ Formule, tapez une valeur.</span><span class="sxs-lookup"><span data-stu-id="bec25-218">In the Formula field, type a value.</span></span>
    * <span data-ttu-id="bec25-219">CONCATENATE(Company.’find()’.Name, ";",</span><span class="sxs-lookup"><span data-stu-id="bec25-219">CONCATENATE(Company.'find()'.Name, ";",</span></span>  
21. <span data-ttu-id="bec25-220">Dans l’arborescence, sélectionnez « Company\find()\Company(DataArea) ».</span><span class="sxs-lookup"><span data-stu-id="bec25-220">In the tree, select 'Company\find()\Company(DataArea)'.</span></span>
22. <span data-ttu-id="bec25-221">Cliquez sur Ajouter une source de données.</span><span class="sxs-lookup"><span data-stu-id="bec25-221">Click Add data source.</span></span>
23. <span data-ttu-id="bec25-222">Dans le champ Formule, tapez une valeur.</span><span class="sxs-lookup"><span data-stu-id="bec25-222">In the Formula field, type a value.</span></span>
    * <span data-ttu-id="bec25-223">CONCATENATE(Company.’find()’.Name, ";", Company.’find()’.DataArea)</span><span class="sxs-lookup"><span data-stu-id="bec25-223">CONCATENATE(Company.'find()'.Name, ";", Company.'find()'.DataArea)</span></span>  
24. <span data-ttu-id="bec25-224">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="bec25-224">Click Save.</span></span>
25. <span data-ttu-id="bec25-225">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="bec25-225">Close the page.</span></span>
26. <span data-ttu-id="bec25-226">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="bec25-226">Click Save.</span></span>
27. <span data-ttu-id="bec25-227">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="bec25-227">Close the page.</span></span>
28. <span data-ttu-id="bec25-228">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="bec25-228">Close the page.</span></span>
29. <span data-ttu-id="bec25-229">Sélectionnez Oui dans le champ Exécuter le brouillon.</span><span class="sxs-lookup"><span data-stu-id="bec25-229">Select Yes in the Run Draft field.</span></span>

## <a name="use-an-existing-er-model-mapping-configuration"></a><span data-ttu-id="bec25-230">Utiliser une configuration de mise en correspondance de modèle ER existante</span><span class="sxs-lookup"><span data-stu-id="bec25-230">Use an existing ER model-mapping configuration</span></span>
1. <span data-ttu-id="bec25-231">Dans l’arborescence, sélectionnez « Exemple de modèle de données\Exemple de format ».</span><span class="sxs-lookup"><span data-stu-id="bec25-231">In the tree, select 'Sample data model\Sample format'.</span></span>
2. <span data-ttu-id="bec25-232">Cliquez sur Exécuter.</span><span class="sxs-lookup"><span data-stu-id="bec25-232">Click Run.</span></span>
    * <span data-ttu-id="bec25-233">La version brouillon sélectionnée de la configuration du format ER ne peut pas être exécutée, car plusieurs configurations de mise en correspondance de modèle sont disponibles pour le modèle de données non défini qui a été sélectionné comme source de données du format ER en cours d’exécution.</span><span class="sxs-lookup"><span data-stu-id="bec25-233">The selected draft version of the ER format configuration can't be executed because there is more than one model-mapping configuration available for the undefined data model that has been selected as the data source of the running ER format.</span></span>   
    * <span data-ttu-id="bec25-234">Ensuite, vous définirez l’autre configuration de mise en correspondance de modèle comme celle à partir de laquelle les mises en correspondance de modèle seront utilisées comme sources de données du format ER en cours d’exécution.</span><span class="sxs-lookup"><span data-stu-id="bec25-234">Next, you will define the alternative model-mapping configuration as the one from which model mappings will be used as data sources for running ER format.</span></span>   
3. <span data-ttu-id="bec25-235">Dans l’arborescence, sélectionnez « Exemple de modèle de données\Exemple de mise en correspondance (autre) ».</span><span class="sxs-lookup"><span data-stu-id="bec25-235">In the tree, select 'Sample data model\Sample mapping (alternative)'.</span></span>
4. <span data-ttu-id="bec25-236">Sélectionnez Oui dans le champ Valeur par défaut de la mise en correspondance des modèles.</span><span class="sxs-lookup"><span data-stu-id="bec25-236">Select Yes in the Default for model-mapping field.</span></span>
5. <span data-ttu-id="bec25-237">Dans l’arborescence, sélectionnez « Exemple de modèle de données\Exemple de format ».</span><span class="sxs-lookup"><span data-stu-id="bec25-237">In the tree, select 'Sample data model\Sample format'.</span></span>
6. <span data-ttu-id="bec25-238">Cliquez sur Exécuter.</span><span class="sxs-lookup"><span data-stu-id="bec25-238">Click Run.</span></span>
7. <span data-ttu-id="bec25-239">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="bec25-239">Click OK.</span></span>
    * <span data-ttu-id="bec25-240">La configuration de mise en correspondance de modèle par défaut est utilisée par cette configuration de format pour générer le document électronique (la sortie créée contient le code de la société).</span><span class="sxs-lookup"><span data-stu-id="bec25-240">The default model-mapping configuration is used by this format configuration for generating the electronic document (the created output contains the company code).</span></span>  

