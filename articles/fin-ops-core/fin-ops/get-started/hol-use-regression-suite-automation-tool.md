---
title: Utiliser le didacticiel Regression Suite Automation Tool
description: Cette rubrique explique comment utiliser l'outil RSAT (Regression Suite Automation Tool). Il en décrit les diverses fonctions et fournit des exemples qui utilisent l'écriture de script avancée.
author: kfend
manager: AnnBe
ms.date: 06/09/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.custom: 21761
ms.search.region: Global
ms.author: kfend
ms.search.validFrom: 2017-06-30
ms.dyn365.ops.version: AX 7.0.0, Operations
ms.openlocfilehash: cf3ca501efb4e540994b01e651eee5b8aab4ddbc
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/27/2019
ms.locfileid: "2191084"
---
# <a name="use-the-regression-suite-automation-tool-tutorial"></a><span data-ttu-id="421db-104">Utiliser le didacticiel Regression Suite Automation Tool</span><span class="sxs-lookup"><span data-stu-id="421db-104">Use the Regression suite automation tool tutorial</span></span>

[!include [banner](../includes/banner.md)]

> [!NOTE]
> <span data-ttu-id="421db-105">Utilisez les outils du navigateur Internet pour télécharger et enregistrer cette page au format PDF.</span><span class="sxs-lookup"><span data-stu-id="421db-105">Use your internet browser tools to download and save this page in pdf format.</span></span> 

<span data-ttu-id="421db-106">Ce didacticiel vous explique quelques-unes des fonctions avancées de l'outil RSAT (Regression Suite Automation Tool), inclut une mission de démonstration et décrit des points stratégiques et d'apprentissage clés.</span><span class="sxs-lookup"><span data-stu-id="421db-106">This tutorial walks through some of the advanced features of the Regression suite automation tool (RSAT), includes a demo assignment, and describes strategy and key learning points.</span></span>

## <a name="features-of-rsattask-recorder"></a><span data-ttu-id="421db-107">Fonctions de RSAT/Enregistreur de tâches</span><span class="sxs-lookup"><span data-stu-id="421db-107">Features of RSAT/Task recorder</span></span>

### <a name="validate-a-field-value"></a><span data-ttu-id="421db-108">Valider une valeur du champ</span><span class="sxs-lookup"><span data-stu-id="421db-108">Validate a field value</span></span>

<span data-ttu-id="421db-109">Pour plus d'informations sur cette fonction, voir [Créer un nouvel enregistrement de tâche possédant une fonction de validation](./hol-set-up-regression-suite-automation-tool.md#create-a-new-task-recording-that-has-a-validate-function).</span><span class="sxs-lookup"><span data-stu-id="421db-109">For information about this feature, see the [Create a new task recording that has a Validate function](./hol-set-up-regression-suite-automation-tool.md#create-a-new-task-recording-that-has-a-validate-function).</span></span>

### <a name="saved-variable"></a><span data-ttu-id="421db-110">Variable enregistrée</span><span class="sxs-lookup"><span data-stu-id="421db-110">Saved variable</span></span>

<span data-ttu-id="421db-111">Pour plus d'informations sur cette fonction, voir [Modifier un enregistrement de tâche existant pour créer une variable enregistrée](./hol-set-up-regression-suite-automation-tool.md#modify-an-existing-task-recording-to-create-a-saved-variable).</span><span class="sxs-lookup"><span data-stu-id="421db-111">For information about this feature, see the [Modify an existing task recording to create a saved variable](./hol-set-up-regression-suite-automation-tool.md#modify-an-existing-task-recording-to-create-a-saved-variable).</span></span>

### <a name="derived-test-case"></a><span data-ttu-id="421db-112">Scénario de test dérivé</span><span class="sxs-lookup"><span data-stu-id="421db-112">Derived test case</span></span>

1. <span data-ttu-id="421db-113">Ouvrez l'outil RSAT (Regression Suite Automation Tool), puis sélectionnez les deux scénarios de test que vous avez créés dans [Configurer et installer l'outil Regression Suite Automation Tool](./hol-set-up-regression-suite-automation-tool.md).</span><span class="sxs-lookup"><span data-stu-id="421db-113">Open Regression suite automation tool (RSAT), and select both the test cases that you created in [Set up and install Regression suite automation tool](./hol-set-up-regression-suite-automation-tool.md).</span></span>
2. <span data-ttu-id="421db-114">Sélectionnez **Nouveau \> Créer un scénario de test dérivé**.</span><span class="sxs-lookup"><span data-stu-id="421db-114">Select **New \> Create derived test case**.</span></span>

    ![Commande Créer un scénario de test dérivé dans le menu Nouveau](./media/use_rsa_tool_01.png)

3. <span data-ttu-id="421db-116">Vous recevez un message indiquant qu'un scénario de test dérivé sera créé pour chaque scénario de test sélectionné dans la suite de tests actuelle, et que chaque scénario de test dérivé aura sa propre copie du fichier de paramètres Excel.</span><span class="sxs-lookup"><span data-stu-id="421db-116">You receive a message that states that a derived test case will be created for each selected test case in the current test suite, and that each derived test case will have its own copy of the Excel parameter file.</span></span> <span data-ttu-id="421db-117">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="421db-117">Select **OK**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="421db-118">Lorsque vous exécutez un scénario de test dérivé, il utilise l'enregistrement de tâche de son scénario de test parent et sa propre copie du fichier de paramètres Excel.</span><span class="sxs-lookup"><span data-stu-id="421db-118">When you run a derived test case, it uses the task recording of its parent test case and its own copy of the Excel parameter file.</span></span> <span data-ttu-id="421db-119">De cette manière, vous pouvez exécuter le même test avec différents paramètres, sans devoir mettre à jour plusieurs enregistrement de tâches.</span><span class="sxs-lookup"><span data-stu-id="421db-119">In this way, you can run the same test with different parameters, without having to maintain more than one task recording.</span></span> <span data-ttu-id="421db-120">Un scénario de test dérivé n'est pas obligé de faire partie de la même suite de tests que son scénario de test parent.</span><span class="sxs-lookup"><span data-stu-id="421db-120">A derived test case doesn't have to be part of the same test suite as its parent test case.</span></span>

    ![Zone de message](./media/use_rsa_tool_02.png)

    <span data-ttu-id="421db-122">Deux scénarios de test dérivés supplémentaires sont créés, et la case à cocher **Dérivé ?** est sélectionnée pour eux.</span><span class="sxs-lookup"><span data-stu-id="421db-122">Two additional derived test cases are created, and the **Derived?** check box is selected for them.</span></span>

    ![Scénarios de test dérivés créés](./media/use_rsa_tool_03.png)

    <span data-ttu-id="421db-124">Un scénario de test dérivé est automatiquement créé dans Azure DevOps.</span><span class="sxs-lookup"><span data-stu-id="421db-124">A derived test case is automatically created in Azure DevOps.</span></span> <span data-ttu-id="421db-125">Il s'agit d'un élément enfant du scénario de test **Créer un nouveau produit** et il est étiqueté avec un mot clé spécial : **RSAT: DerivedTestSteps**.</span><span class="sxs-lookup"><span data-stu-id="421db-125">It's a child item of the **Create a new product** test case and is tagged with a special keyword: **RSAT:DerivedTestSteps**.</span></span> <span data-ttu-id="421db-126">Ces scénarios de test sont automatiquement ajoutés au plan de test dans Azure DevOps.</span><span class="sxs-lookup"><span data-stu-id="421db-126">These test cases are also automatically added to the test plan in Azure DevOps.</span></span>

    ![Mot clé RSAT:DerivedTestSteps](./media/use_rsa_tool_04.png)

    > [!NOTE]
    > <span data-ttu-id="421db-128">Si, pour une raison quelconque, les scénarios de test dérivés qui sont créés ne sont pas dans l'ordre correct, accédez à Azure DevOps et réorganisez les scénarios de test dans la suite de tests, de sorte que RSAT puisse les exécuter dans l'ordre correct.</span><span class="sxs-lookup"><span data-stu-id="421db-128">If, for any reason, the derived test cases that are created aren't in the correct order, go to Azure DevOps, and reorder the test cases in the test suite, so that RSAT can run them in the correct order.</span></span>

4. <span data-ttu-id="421db-129">Sélectionnez les scénarios de test dérivés, puis sélectionnez **Modifier** pour ouvrir les fichiers de paramètres Excel correspondants.</span><span class="sxs-lookup"><span data-stu-id="421db-129">Select the derived test cases, and then select **Edit** to open the corresponding Excel parameter files.</span></span>
5. <span data-ttu-id="421db-130">Modifiez les fichiers de paramètres Excel de la même manière que vous avez modifié les fichiers parents.</span><span class="sxs-lookup"><span data-stu-id="421db-130">Edit these Excel parameter files in the same way that you edited the parent files.</span></span> <span data-ttu-id="421db-131">En d'autres termes, vérifiez que l'ID produit est défini afin d'être généré automatiquement.</span><span class="sxs-lookup"><span data-stu-id="421db-131">In other words, make sure that the product ID is set so that it's automatically generated.</span></span> <span data-ttu-id="421db-132">Assurez-vous également que la variable enregistrée est copiée dans les champs appropriés.</span><span class="sxs-lookup"><span data-stu-id="421db-132">Also make sure that the saved variable is copied to the relevant fields.</span></span>
6. <span data-ttu-id="421db-133">Dans l'onglet **Général** des deux fichiers de paramètres Excel, mettez à jour la valeur du champ **Société** sur **USSI**, afin que les scénarios de test dérivés soient exécutés avec une autre entité juridique que le scénario de test parent.</span><span class="sxs-lookup"><span data-stu-id="421db-133">On the **General** tab of both Excel parameter files, update the value of the **Company** field to **USSI**, so that the derived test cases will be run against a different legal entity than the parent test case.</span></span> <span data-ttu-id="421db-134">Pour exécuter les scénarios de test pour un utilisateur spécifique (ou le rôle qui est associé à un utilisateur spécifique), vous pouvez mettre à jour la valeur du champ **Utilisateur du test**.</span><span class="sxs-lookup"><span data-stu-id="421db-134">To run the test cases against a specific user (or the role that is associated with a specific user), you can update the value of the **Test User** field.</span></span>
7. <span data-ttu-id="421db-135">Sélectionnez **Exécuter**, puis vérifiez le produit est créé dans l'entité juridique USMF et l'entité juridique USSI.</span><span class="sxs-lookup"><span data-stu-id="421db-135">Select **Run**, and validate that the product is created in both the USMF legal entity and the USSI legal entity.</span></span>

### <a name="validate-notifications"></a><span data-ttu-id="421db-136">Valider les notifications</span><span class="sxs-lookup"><span data-stu-id="421db-136">Validate notifications</span></span>

<span data-ttu-id="421db-137">Cette fonction peut être utilisée pour vérifier si une action s'est produite.</span><span class="sxs-lookup"><span data-stu-id="421db-137">This feature can be used to validate whether an action occurred.</span></span> <span data-ttu-id="421db-138">Par exemple, lorsqu'un ordre de fabrication est créé, estimé, puis démarré, l'application présente un message « Production – démarrer » pour vous informer que l'ordre de fabrication a commencé.</span><span class="sxs-lookup"><span data-stu-id="421db-138">For example, when a production order is created, estimated, and then started, the app shows a "Production – Start" message to notify you that the production order has been started.</span></span>

![Notification Production – Démarrer](./media/use_rsa_tool_05.png)

<span data-ttu-id="421db-140">Vous pouvez valider ce message dans RSAT en entrant le texte du message dans l'onglet **Validation du message** du fichier de paramètres Excel pour l'enregistrement approprié.</span><span class="sxs-lookup"><span data-stu-id="421db-140">You can validate this message through RSAT by entering the message text on the **MessageValidation** tab of the Excel parameter file for the appropriate recording.</span></span>

![Onglet Validation du message](./media/use_rsa_tool_06.png)

<span data-ttu-id="421db-142">Une fois le scénario de test exécuté, le message du fichier de paramètres Excel est comparé au message qui s'affiche.</span><span class="sxs-lookup"><span data-stu-id="421db-142">After the test case is run, the message in the Excel parameter file is compared to the message that is shown.</span></span> <span data-ttu-id="421db-143">Si les messages ne correspondent pas, le scénario de test échoue.</span><span class="sxs-lookup"><span data-stu-id="421db-143">If the messages don't match, the test case will fail.</span></span>

> [!NOTE]
> <span data-ttu-id="421db-144">Vous pouvez entrer plusieurs messages dans l'onglet **Validation du message** du fichier de paramètres Excel.</span><span class="sxs-lookup"><span data-stu-id="421db-144">You can enter more than one message on the **MessageValidation** tab in the Excel parameter file.</span></span> <span data-ttu-id="421db-145">Les messages peuvent également être des messages d'erreur ou d'avertissement au lieu de messages d'information.</span><span class="sxs-lookup"><span data-stu-id="421db-145">The messages also can be error or warning messages instead of informational messages.</span></span>

### <a name="validate-values-by-using-operators"></a><span data-ttu-id="421db-146">Valider les valeurs à l'aide d'opérateurs</span><span class="sxs-lookup"><span data-stu-id="421db-146">Validate values by using operators</span></span>

<span data-ttu-id="421db-147">Dans les versions précédentes de RSAT, vous ne pouviez valider les valeurs que si une valeur de contrôle était égale à une valeur attendue.</span><span class="sxs-lookup"><span data-stu-id="421db-147">In previous versions of RSAT, you could validate values only if a control value equaled an expected value.</span></span> <span data-ttu-id="421db-148">La nouvelle fonction permet de valider qu'une variable n'est pas égale à, est inférieure à, ou est supérieure à une valeur spécifiée.</span><span class="sxs-lookup"><span data-stu-id="421db-148">The new feature lets you validate that a variable isn't equal to, is less than, or is more than a specified value.</span></span>

- <span data-ttu-id="421db-149">Pour utiliser cette fonction, ouvrez le fichier **Microsoft.Dynamics.RegressionSuite.WindowsApp.exe.config** sous le dossier d'installation de RSAT (par exemple, **C:\\Program Files (x86)\\Regression Suite Automation Tool**), puis modifiez la valeur de l'élément suivant de **faux** à **vrai**.</span><span class="sxs-lookup"><span data-stu-id="421db-149">To use this feature, open the **Microsoft.Dynamics.RegressionSuite.WindowsApp.exe.config** file under the RSAT installation folder (for example, **C:\\Program Files (x86)\\Regression Suite Automation Tool**), and change the value in the following element from **false** to **true**.</span></span>

    ```
    <add key="AddOperatorFieldsToExcelValidation" value="false" />
    ```

    <span data-ttu-id="421db-150">Dans le fichier de paramètres Excel, un nouveau champ **Opérateur** apparaît.</span><span class="sxs-lookup"><span data-stu-id="421db-150">In the Excel parameter file, a new **Operator** field appears.</span></span>

    > [!NOTE]
    > <span data-ttu-id="421db-151">Si vous utilisiez une version plus ancienne de RSAT, vous devez générer de nouveaux fichiers de paramètres Excel.</span><span class="sxs-lookup"><span data-stu-id="421db-151">If you've been using an older version of RSAT, you must generate new Excel parameter files.</span></span>

    ![Champ Opérateur](./media/use_rsa_tool_07.png)

<span data-ttu-id="421db-153">L'exemple suivant montre comment vous pouvez utiliser cette fonction pour vérifier si le stock disponible est supérieur à 0 (zéro).</span><span class="sxs-lookup"><span data-stu-id="421db-153">The following example shows how you can use this feature to validate whether the on-hand inventory is more than 0 (zero).</span></span>

1. <span data-ttu-id="421db-154">Dans les données de démonstration de la société **USMF**, créez un enregistrement de tâche ayant les étapes suivantes :</span><span class="sxs-lookup"><span data-stu-id="421db-154">In the demo data in the **USMF** company, create a task recording that has the following steps:</span></span>

    1. <span data-ttu-id="421db-155">Allez à **Gestion des informations sur les produits \> Produits \> Produits lancés**.</span><span class="sxs-lookup"><span data-stu-id="421db-155">Go to **Product information management \> Products \> Released products**.</span></span>
    2. <span data-ttu-id="421db-156">Utilisez le Filtre rapide pour rechercher les enregistrements.</span><span class="sxs-lookup"><span data-stu-id="421db-156">Use the Quick Filter to find records.</span></span> <span data-ttu-id="421db-157">Par exemple, filtrez une valeur **1000** pour le champ **Numéro d'article**.</span><span class="sxs-lookup"><span data-stu-id="421db-157">For example, filter on a value of **1000** for the **Item number** field.</span></span>
    3. <span data-ttu-id="421db-158">Sélectionnez **Stock disponible**.</span><span class="sxs-lookup"><span data-stu-id="421db-158">Select **On-hand inventory**.</span></span>
    4. <span data-ttu-id="421db-159">Utilisez le Filtre rapide pour rechercher les enregistrements.</span><span class="sxs-lookup"><span data-stu-id="421db-159">Use the Quick Filter to find records.</span></span> <span data-ttu-id="421db-160">Par exemple, filtrez une valeur **1** pour le champ **Site**.</span><span class="sxs-lookup"><span data-stu-id="421db-160">For example, filter on a value of **1** for the **Site** field.</span></span>
    5. <span data-ttu-id="421db-161">Dans la liste, marquer la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="421db-161">In the list, mark the selected row.</span></span>
    6. <span data-ttu-id="421db-162">Vérifiez que la valeur du champ **Total disponible** est **411,0000000000000000**.</span><span class="sxs-lookup"><span data-stu-id="421db-162">Validate that the value of the **Total available** field is **411.0000000000000000**.</span></span>

2. <span data-ttu-id="421db-163">Enregistrez l'enregistrement de tâche dans la bibliothèque BPM de LCS et synchronisez-la avec Azure DevOps.</span><span class="sxs-lookup"><span data-stu-id="421db-163">Save the task recording to the BPM library in LCS, and sync it to Azure DevOps.</span></span>
3. <span data-ttu-id="421db-164">Ajoutez le scénario de test au plan de test, puis chargez le scénario de test dans RSAT.</span><span class="sxs-lookup"><span data-stu-id="421db-164">Add the test case to the test plan, and load the test case into RSAT.</span></span>
4. <span data-ttu-id="421db-165">Ouvrez le fichier de paramètres Excel.</span><span class="sxs-lookup"><span data-stu-id="421db-165">Open the Excel parameter file.</span></span> <span data-ttu-id="421db-166">Dans l'onglet **InventOnhandItem**, vous voyez une section **Valider InventOnhandItem** qui inclut un champ **Opérateur**.</span><span class="sxs-lookup"><span data-stu-id="421db-166">On the **InventOnhandItem** tab, you will see a **Validate InventOnhandItem** section that includes an **Operator** field.</span></span>

    ![Champ Opérateur](./media/use_rsa_tool_08.png)

5. <span data-ttu-id="421db-168">Pour vérifier si le stock disponible est toujours supérieur à 0, modifiez la valeur du champ **Valeur** de **411** à **0** et la valeur du champ **Opérateur** d'un signe égal (**=**) à un signe supérieur à (**\>**).</span><span class="sxs-lookup"><span data-stu-id="421db-168">To validate whether the inventory on-hand will always be more than 0, change the value of the **Value** field from **411** to **0** and the value of the **Operator** field from an equal sign (**=**) to a greater than sign (**\>**).</span></span>

    ![Valeurs des champs Valeur et Opérateur modifiées](./media/use_rsa_tool_09.png)

6. <span data-ttu-id="421db-170">Enregistrez et fermez le fichier de paramètres Excel.</span><span class="sxs-lookup"><span data-stu-id="421db-170">Save and close the Excel parameter file.</span></span>
7. <span data-ttu-id="421db-171">Sélectionnez **Upload** pour enregistrer les modifications apportées au fichier de paramètres Excel dans Azure DevOps.</span><span class="sxs-lookup"><span data-stu-id="421db-171">Select **Upload** to save the changes that you made to the Excel parameter file to Azure DevOps.</span></span>

<span data-ttu-id="421db-172">Désormais, si la valeur du champ **Total disponible** pour l'article spécifié en stock est supérieure à 0 (zéro), les tests réussiront, indépendamment de la valeur réelle du stock disponible.</span><span class="sxs-lookup"><span data-stu-id="421db-172">Now, if the value of the **Total Available** field for the specified item in inventory is more than 0 (zero), tests will pass, regardless of the actual on-hand inventory value.</span></span>

### <a name="generator-logs"></a><span data-ttu-id="421db-173">Journaux Générateur</span><span class="sxs-lookup"><span data-stu-id="421db-173">Generator logs</span></span>

<span data-ttu-id="421db-174">Cette fonction permet de créer un dossier contenant les journaux des scénarios de test qui ont été exécutés.</span><span class="sxs-lookup"><span data-stu-id="421db-174">This feature creates a folder that contains the logs of the test cases that have been run.</span></span>

- <span data-ttu-id="421db-175">Pour utiliser cette fonction, ouvrez le fichier **Microsoft.Dynamics.RegressionSuite.WindowsApp.exe.config** sous le dossier d'installation de RSAT (par exemple, **C:\\Program Files (x86)\\Regression Suite Automation Tool**), puis modifiez la valeur de l'élément suivant de **faux** à **vrai**.</span><span class="sxs-lookup"><span data-stu-id="421db-175">To use this feature, open the **Microsoft.Dynamics.RegressionSuite.WindowsApp.exe.config** file under the RSAT installation folder (for example, **C:\\Program Files (x86)\\Regression Suite Automation Tool**), and change the value in the following element from **false** to **true**.</span></span>

    ```
    <add key="LogGeneration" value="false" />
    ```

<span data-ttu-id="421db-176">Une fois les scénarios de test exécutés, vous pouvez trouver les fichiers journaux sous **C:\\Utilisateurs\\\<Nom d'utilisateur\>\\AppData\\Roaming\\regressionTool\\generatorLogs**.</span><span class="sxs-lookup"><span data-stu-id="421db-176">After the test cases are run, you can find the log files under **C:\\Users\\\<Username\>\\AppData\\Roaming\\regressionTool\\generatorLogs**.</span></span>

![Dossier GeneratorLogs](./media/use_rsa_tool_10.png)

> [!NOTE]
> <span data-ttu-id="421db-178">S'il y a des scénarios de test existants avant de modifier la valeur du fichier .config, les journaux ne seront pas générés pour ces scénarios de test jusqu'à ce que vous ayez généré de nouveaux fichiers d'exécution de test.</span><span class="sxs-lookup"><span data-stu-id="421db-178">If there were existing test cases before you changed the value in the .config file, logs won't be generated for those test cases until you generate new test execution files.</span></span>
> 
> ![Commande Générer des fichiers d'exécution de test uniquement dans le menu Nouveau](./media/use_rsa_tool_11.png)

### <a name="snapshot"></a><span data-ttu-id="421db-180">Instantané</span><span class="sxs-lookup"><span data-stu-id="421db-180">Snapshot</span></span>

<span data-ttu-id="421db-181">Cette fonction prend des captures d'écran des étapes qui ont été effectuées au cours de l'enregistrement de tâche.</span><span class="sxs-lookup"><span data-stu-id="421db-181">This feature takes screenshots of the steps that were performed during task recording.</span></span>

- <span data-ttu-id="421db-182">Pour utiliser cette fonction, ouvrez le fichier **Microsoft.Dynamics.RegressionSuite.WindowsApp.exe.config** sous le dossier d'installation de RSAT (par exemple, **C:\\Program Files (x86)\\Regression Suite Automation Tool**), puis modifiez la valeur de l'élément suivant de **faux** à **vrai**.</span><span class="sxs-lookup"><span data-stu-id="421db-182">To use this feature, open the **Microsoft.Dynamics.RegressionSuite.WindowsApp.exe.config** file under the RSAT installation folder (for example, **C:\\Program Files (x86)\\Regression Suite Automation Tool**), and change the value of the following element from **false** to **true**.</span></span>

    ```
    <add key="VerboseSnapshotsEnabled" value="false" />
    ```

<span data-ttu-id="421db-183">Sous **C:\\Utilisateurs\\\<Nom d'utilisateur\>\\AppData\\Roaming\\regressionTool\\playback**, un dossier distinct est créé pour chaque scénario de test qui est exécuté.</span><span class="sxs-lookup"><span data-stu-id="421db-183">Under **C:\\Users\\\<Username\>\\AppData\\Roaming\\regressionTool\\playback**, a separate folder is created for each test case that is run.</span></span>

![Dossier Instantané pour un scénario de test](./media/use_rsa_tool_12.png)

<span data-ttu-id="421db-185">Dans chacune de ces dossiers, vous pouvez trouver des instantanés des étapes qui ont été effectuées lorsque les scénarios de test ont été effectués.</span><span class="sxs-lookup"><span data-stu-id="421db-185">In each of these folders, you can find snapshots of the steps that were performed while the test cases were run.</span></span>

![Fichiers d'instantané](./media/use_rsa_tool_13.png)

## <a name="assignment"></a><span data-ttu-id="421db-187">Affectation</span><span class="sxs-lookup"><span data-stu-id="421db-187">Assignment</span></span>

### <a name="scenario"></a><span data-ttu-id="421db-188">Scénario</span><span class="sxs-lookup"><span data-stu-id="421db-188">Scenario</span></span>

1. <span data-ttu-id="421db-189">Le concepteur de produit crée un nouveau produit lancé.</span><span class="sxs-lookup"><span data-stu-id="421db-189">The product designer creates a new released product.</span></span>
2. <span data-ttu-id="421db-190">Le gestionnaire de production lance un ordre de fabrication pour amener le niveau de stock à deux unités.</span><span class="sxs-lookup"><span data-stu-id="421db-190">The production manager initiates a production order to bring the stock level to two pieces.</span></span>
3. <span data-ttu-id="421db-191">La fabrication démarre et termine l'ordre de fabrication, et vérifie que la quantité disponible est de deux unités.</span><span class="sxs-lookup"><span data-stu-id="421db-191">Manufacturing starts and ends the production order, and verifies that the on-hand quantity is two pieces.</span></span>
4. <span data-ttu-id="421db-192">L'équipe commerciale reçoit une commande de quatre unités du nouveau produit.</span><span class="sxs-lookup"><span data-stu-id="421db-192">The sales team receives an order for four pieces of the new product.</span></span> <span data-ttu-id="421db-193">Par conséquent, l'équipe de vente présente les besoins nets via le plan dynamique.</span><span class="sxs-lookup"><span data-stu-id="421db-193">Therefore, the sales team updates the net requirements via the dynamic plan.</span></span> <span data-ttu-id="421db-194">Comme aucune capacité supplémentaire n'est disponible, la stratégie de commande par défaut est définie sur « acheter plutôt que fabriquer ».</span><span class="sxs-lookup"><span data-stu-id="421db-194">Because no additional capacity is available, the default order policy is set to "buy instead of make."</span></span> <span data-ttu-id="421db-195">Par conséquent, une commande fournisseur est créée.</span><span class="sxs-lookup"><span data-stu-id="421db-195">Therefore, a planned purchase order is created.</span></span>
5. <span data-ttu-id="421db-196">L'acheteur ajoute un fournisseur, confirme la commande fournisseur prévisionnelle, puis confirme la commande fournisseur.</span><span class="sxs-lookup"><span data-stu-id="421db-196">The buyer adds a vendor, firms the planned purchase order, and then confirms the purchase order.</span></span>
6. <span data-ttu-id="421db-197">Lorsque les marchandises achetées arrivent au magasin, le magasinier recherche la commande fournisseur associée et réceptionne les marchandises.</span><span class="sxs-lookup"><span data-stu-id="421db-197">When the goods that were purchased arrive at the store, the store operator searches the related purchase order and receives the goods.</span></span> <span data-ttu-id="421db-198">Comme la commande est maintenant terminée, les marchandises peuvent être prélevées et emballées conformément à la commande client.</span><span class="sxs-lookup"><span data-stu-id="421db-198">Because the order is now completed, goods can be picked and packed against the sales order.</span></span>
7. <span data-ttu-id="421db-199">Le service financier valide la facture fournisseur et la facture client.</span><span class="sxs-lookup"><span data-stu-id="421db-199">Finance posts the purchase invoice and sales invoice.</span></span>

<span data-ttu-id="421db-200">La figure suivante présente une capture d'écran du flux de ce scénario.</span><span class="sxs-lookup"><span data-stu-id="421db-200">The following illustration shows the flow for this scenario.</span></span>

![Flux du scénario de démonstration](./media/use_rsa_tool_14.png)

<span data-ttu-id="421db-202">La figure suivante présente les processus métier de ce scénario dans RSAT.</span><span class="sxs-lookup"><span data-stu-id="421db-202">The following illustration shows the business processes for this scenario in RSAT.</span></span>

![Processus métier pour le scénario de démonstration](./media/use_rsa_tool_15.png)

## <a name="strategy--key-learning"></a><span data-ttu-id="421db-204">Stratégie – Points d'apprentissage clés</span><span class="sxs-lookup"><span data-stu-id="421db-204">Strategy – Key learning</span></span>

### <a name="data"></a><span data-ttu-id="421db-205">Données</span><span class="sxs-lookup"><span data-stu-id="421db-205">Data</span></span>

- <span data-ttu-id="421db-206">Assurez-vous d'avoir des volumes de données représentatifs (une copie des données de production/configuration Golden, plus des données migrées).</span><span class="sxs-lookup"><span data-stu-id="421db-206">Make sure that you have representative data volumes (a copy of production/golden configuration data plus migrated data).</span></span>
- <span data-ttu-id="421db-207">Lorsque vous générez de nouvelles données via l'enregistreur de tâches, créez des noms de test qui ne seront pas en conflit avec des noms existants (par exemple, utilisez un préfixe tel que **RSATxxx**).</span><span class="sxs-lookup"><span data-stu-id="421db-207">When you generate new data via Task recorder, create test names that won't conflict with existing names (for example, use a prefix such as **RSATxxx**).</span></span>
- <span data-ttu-id="421db-208">Utilisez la restauration ponctuelle Azure pour réexécuter les tests dans des environnements de niveau autre que 1.</span><span class="sxs-lookup"><span data-stu-id="421db-208">Use Azure Point-In-Time restore to rerun tests in non-Tier 1 environments.</span></span>
- <span data-ttu-id="421db-209">Bien que vous puissiez utiliser les fonctions Excel **RANDOM** et **NOW** pour générer une combinaison unique, la charge de travail est considérable.</span><span class="sxs-lookup"><span data-stu-id="421db-209">Although you can use the **RANDOM** and **NOW** Excel functions to generate a unique combination, the effort is considerably high.</span></span> <span data-ttu-id="421db-210">Voici un exemple :</span><span class="sxs-lookup"><span data-stu-id="421db-210">Here is an example.</span></span>

    ```
    product = "AT" &TEXT(NOW(),"yyymmddhhmm")
    ```

### <a name="task-recorder"></a><span data-ttu-id="421db-211">Enregistreur de tâches</span><span class="sxs-lookup"><span data-stu-id="421db-211">Task recorder</span></span>

- <span data-ttu-id="421db-212">Définissez les scénarios avant de commencer l'enregistrement.</span><span class="sxs-lookup"><span data-stu-id="421db-212">Define scenarios before you start recording.</span></span> <span data-ttu-id="421db-213">Un projet bien géré a des scénarios de test prédéfinis.</span><span class="sxs-lookup"><span data-stu-id="421db-213">A well-managed project has predefined test scenarios.</span></span> <span data-ttu-id="421db-214">Pour établir un scénario de test, prenez en compte la prédictibilité des résultats de ces scénarios de test.</span><span class="sxs-lookup"><span data-stu-id="421db-214">To build a test case, consider how predictable the outcome of those test scenarios is.</span></span>
- <span data-ttu-id="421db-215">Fractionnez les enregistrements s'ils sont réalisés par des rôles différents, ou s'il existe un temps d'attente ou un événement externe avant l'étape suivante.</span><span class="sxs-lookup"><span data-stu-id="421db-215">Split recordings if they are performed by different roles, or if there is waiting time or an external event before the next step.</span></span>
- <span data-ttu-id="421db-216">Évitez de sélectionner des valeurs dans des listes.</span><span class="sxs-lookup"><span data-stu-id="421db-216">Avoid selecting values in lists.</span></span> <span data-ttu-id="421db-217">Au lieu de cela, utilisez des formats texte, tels que **FIFO**, **AudioRM** et **SiteWH**.</span><span class="sxs-lookup"><span data-stu-id="421db-217">Instead, use text formats, such as **FIFO**, **AudioRM**, and **SiteWH**.</span></span> <span data-ttu-id="421db-218">Si vous faites une sélection dans une liste, c'est la position de la valeur dans la liste qui est enregistrée, pas la valeur elle-même.</span><span class="sxs-lookup"><span data-stu-id="421db-218">When you select in a list, the position of the value in the list is recorded, not the value itself.</span></span> <span data-ttu-id="421db-219">Si des articles sont ajoutés à cette liste, la position de la valeur peut changer.</span><span class="sxs-lookup"><span data-stu-id="421db-219">If items are added to that list, the position of the value can change.</span></span> <span data-ttu-id="421db-220">Par conséquent, l'enregistrement utilisera un paramètre différent, et le reste du scénario peut en être affecté.</span><span class="sxs-lookup"><span data-stu-id="421db-220">Therefore, your recording will use a different parameter, and the rest of the scenario might be affected.</span></span>
- <span data-ttu-id="421db-221">Pensez au comportement multi-utilisateur.</span><span class="sxs-lookup"><span data-stu-id="421db-221">Think about multi-user behavior.</span></span> <span data-ttu-id="421db-222">Par exemple, ne supposez pas que votre commande client nouvellement créée sera toujours sélectionnée automatiquement.</span><span class="sxs-lookup"><span data-stu-id="421db-222">For example, don't assume that your newly created sales order will always be automatically selected.</span></span> <span data-ttu-id="421db-223">Au lieu de cela, utilisez toujours le filtre permettant de trouver la commande appropriée.</span><span class="sxs-lookup"><span data-stu-id="421db-223">Instead, always use the filter to find the correct order.</span></span>
- <span data-ttu-id="421db-224">Utilisez la fonction Copier dans l'enregistreur de tâches pour enregistrer le nom d'un produit nouvellement créé, de manière à l'utiliser dans des scénarios de test enchaînés.</span><span class="sxs-lookup"><span data-stu-id="421db-224">Use the Copy function in Task recorder to save the name of a newly created product so it can be used in chained test cases.</span></span>
- <span data-ttu-id="421db-225">Utilisez la fonction Valider de l'enregistreur de tâches pour définir des points de contrôle pour vérifier que les étapes ont été exécutées correctement.</span><span class="sxs-lookup"><span data-stu-id="421db-225">Use the Validate function in Task recorder to set checkpoints that verify that steps have been run correctly.</span></span>

### <a name="rsat"></a><span data-ttu-id="421db-226">RSAT</span><span class="sxs-lookup"><span data-stu-id="421db-226">RSAT</span></span>

- <span data-ttu-id="421db-227">Pour exécuter le test sur une autre société, vous pouvez modifier la société sur l'onglet **Général** du fichier de paramètres Excel.</span><span class="sxs-lookup"><span data-stu-id="421db-227">To run the test in another company, you can change the company on the **General** tab of the Excel parameter file.</span></span> <span data-ttu-id="421db-228">Vérifiez que les paramètres et les données sont disponibles dans la société récemment sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="421db-228">Make sure that settings and data are available in the newly selected company.</span></span>
- <span data-ttu-id="421db-229">Vous pouvez modifier l'utilisateur du test dans l'onglet **Général** du fichier de paramètres Excel.</span><span class="sxs-lookup"><span data-stu-id="421db-229">You can change the test user on the **General** tab of the Excel parameter file.</span></span> <span data-ttu-id="421db-230">Indiquez l'ID d'e-mail de l'utilisateur qui exécutera le scénario de test.</span><span class="sxs-lookup"><span data-stu-id="421db-230">Specify the email ID of the user who will run the test case.</span></span> <span data-ttu-id="421db-231">Ainsi, le scénario de test pourra être exécuté à l'aide des autorisations de sécurité de l'utilisateur spécifié.</span><span class="sxs-lookup"><span data-stu-id="421db-231">In this way, the test case can be run by using the security permissions of the specified user.</span></span>
- <span data-ttu-id="421db-232">Pour attendre le démarrage du test, vous pouvez définir une pause dans l'onglet **Général** du fichier de paramètres Excel.</span><span class="sxs-lookup"><span data-stu-id="421db-232">To wait before the test is started, you can define a pause on the **General** tab of the Excel parameter file.</span></span> <span data-ttu-id="421db-233">Cette pause peut être utilisée dans un traitement par lots (par exemple, si un workflow doit être exécuté avant que l'étape suivante ne puisse être réalisée.)</span><span class="sxs-lookup"><span data-stu-id="421db-233">This pause can be used in a batch job (for example, if a workflow must be run before the next step can be performed.)</span></span>

## <a name="advanced-scripting"></a><span data-ttu-id="421db-234">Écriture de script avancée</span><span class="sxs-lookup"><span data-stu-id="421db-234">Advanced scripting</span></span>

### <a name="command-line"></a><span data-ttu-id="421db-235">Ligne de commande</span><span class="sxs-lookup"><span data-stu-id="421db-235">Command line</span></span>

<span data-ttu-id="421db-236">RSAT peut être appelé à partir d'une fenêtre **Invite de commandes**.</span><span class="sxs-lookup"><span data-stu-id="421db-236">RSAT can be called from a **Command Prompt** window.</span></span>

> [!NOTE]
> <span data-ttu-id="421db-237">Vérifiez que la variable d'environnement **TestRoot** est définie sur le chemin d'installation de RSAT.</span><span class="sxs-lookup"><span data-stu-id="421db-237">Verify that the **TestRoot** environment variable is set to the RSAT installation path.</span></span> <span data-ttu-id="421db-238">(Dans Microsoft Windows, ouvrez **Panneau de configuration**, sélectionnez **Système et sécurité \> Système \> Paramètres système avancés**, puis sélectionnez **Variables d'environnement**.)</span><span class="sxs-lookup"><span data-stu-id="421db-238">(In Microsoft Windows, open **Control Panel**, select **System and Security \> System \> Advanced system settings**, and then select **Environment Variables**.)</span></span>

1. <span data-ttu-id="421db-239">Ouvrez une fenêtre d'**invite de commande** en tant qu'administrateur.</span><span class="sxs-lookup"><span data-stu-id="421db-239">Open a **Command Prompt** window as an admin.</span></span>
2. <span data-ttu-id="421db-240">Exécutez l'outil à partir du répertoire d'installation.</span><span class="sxs-lookup"><span data-stu-id="421db-240">Run the tool from the installation directory.</span></span>

    ```
    cd "c:\Program Files (x86)\Regression Suite Automation Tool\"
    ```

3. <span data-ttu-id="421db-241">Répertoriez toutes les commandes.</span><span class="sxs-lookup"><span data-stu-id="421db-241">List all commands.</span></span>

    ```
    C:\Program Files (x86)\Regression Suite Automation Tool>Microsoft.Dynamics.RegressionSuite.ConsoleApp.exe help

    Usage:
        Microsoft.Dynamics.RegressionSuite.ConsoleApp.exe command
        or
        Microsoft.Dynamics.RegressionSuite.ConsoleApp.exe /settings "C:\Path to\file.settings" command

    Available commands:
        list
        listtestsuite suite_name
        download test_case_id output_dir
        generate test_case_id output_dir
        generatederived parent_test_case_id test_plan_id test_suite_id
        generatetestonly test_case_id output_dir
        edit excel_file
        playback excel_file
        playbackmany excel_file1 [excel_file2 [.. excel_fileN]]
        playbackbyid test_case_id1 [test_case_id2 [.. test_case_idN]]
        playbacksuite suite_name
        clear
        help
        about
        quit
    ```

### <a name="windows-powershell-examples"></a><span data-ttu-id="421db-242">Exemples Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="421db-242">Windows PowerShell examples</span></span>

#### <a name="run-a-test-case-in-a-loop"></a><span data-ttu-id="421db-243">Exécuter un scénario de test dans une boucle</span><span class="sxs-lookup"><span data-stu-id="421db-243">Run a test case in a loop</span></span>

<span data-ttu-id="421db-244">Vous avez un script de test qui crée un nouveau client.</span><span class="sxs-lookup"><span data-stu-id="421db-244">You have a test script that creates a new customer.</span></span> <span data-ttu-id="421db-245">Grâce à l'écriture de script, ce scénario de test peut être exécuté en boucle en rendant aléatoires les données suivantes avant chaque itération de l'exécution :</span><span class="sxs-lookup"><span data-stu-id="421db-245">Via scripting, this test case can be run in a loop by randomizing the following data before each iteration is run:</span></span>

- <span data-ttu-id="421db-246">ID client</span><span class="sxs-lookup"><span data-stu-id="421db-246">Customer ID</span></span>
- <span data-ttu-id="421db-247">Nom du client</span><span class="sxs-lookup"><span data-stu-id="421db-247">Customer name</span></span>
- <span data-ttu-id="421db-248">Adresse du client</span><span class="sxs-lookup"><span data-stu-id="421db-248">Customer address</span></span>

<span data-ttu-id="421db-249">L'ID client est au format *ATCUS\<numéro\>*, où \<numéro\> est une valeur comprise entre **000000001** et **999999999**.</span><span class="sxs-lookup"><span data-stu-id="421db-249">The customer ID will be in the format *ATCUS\<number\>*, where \<number\> is a value between **000000001** and **999999999**.</span></span>

<span data-ttu-id="421db-250">L'exemple suivant utilise un paramètre, **début**, pour définir le premier numéro utilisé.</span><span class="sxs-lookup"><span data-stu-id="421db-250">The following example uses one parameter, **start**, to define the first number that is used.</span></span> <span data-ttu-id="421db-251">Il utilise un deuxième paramètre, **nr**, pour définir le nombre de clients à créer.</span><span class="sxs-lookup"><span data-stu-id="421db-251">Is uses a second parameter, **nr**, to define the number of customers that must be created.</span></span> <span data-ttu-id="421db-252">Pour chaque itération, les paramètres du fichier de paramètres Excel sont modifiés à l'aide d'une fonction UpdateCustomer.</span><span class="sxs-lookup"><span data-stu-id="421db-252">For each iteration, the parameters in the Excel parameter file are changed by using an UpdateCustomer function.</span></span> <span data-ttu-id="421db-253">Ensuite, la ligne de commande RSAT est appelée dans une fonction RunTestCase.</span><span class="sxs-lookup"><span data-stu-id="421db-253">Then the RSAT command line is called in a RunTestCase function.</span></span>

<span data-ttu-id="421db-254">Ouvrez l'environnement ISE ( PowerShell Integrated Scripting) de Microsoft Windows en mode administrateur, et collez le code suivant dans la fenêtre qui s'appelle **Untitled1.ps1**.</span><span class="sxs-lookup"><span data-stu-id="421db-254">Open Microsoft Windows PowerShell Integrated Scripting Environment (ISE) in admin mode, and paste the following code into the window that is named **Untitled1.ps1**.</span></span>

```
param ( [int]$start = 1, [int]$nr = 1 )
function UpdateCustomer
{
    param ([string]$paramFilename, [string]$sheetName, [string]$CustId)
    $xl = New-Object -COM "Excel.Application"
    $xl.Visible = $false
    $wb = $xl.Workbooks.Open($paramFilename)
    $ws = $wb.Sheets.Item($sheetName)
    $ws.Cells.Item(3, 2).Value = "ATCUS" + $CustId
    $ws.Cells.Item(4, 2).Value = "Automated Test Customer " + $CustId
    $ws.Cells.Item(8, 2).Value = "Automated Test Street " + $CustId
    $wb.Save()
    $wb.Close()
    $xl.Quit()
    [System.Runtime.Interopservices.Marshal]::ReleaseComObject($xl)
}
function RunTestCase
{
    param ( [string]$filename )
    $cmd = "cd c:\Program Files (x86)\Regression Suite Automation Tool\ &&  "
    $cmd = $cmd + "Microsoft.Dynamics.RegressionSuite.ConsoleApp.exe playback "
    $cmd = $cmd + $filename
    cmd /c $cmd
}
$excelFilename = "full path to excel file parameter file"
l$sheetName = "DirPartyQuickCreateForm"
for ($i = $start; $i -lt $start + $nr; $i++ )
{
    $CustomerId = $i.ToString("000000000")
    Write-Host "customer : " $CustomerId
    UpdateCustomer $excelFilename $sheetName $CustomerId
    RunTestCase $excelFilename
```

#### <a name="run-a-script-that-depends-on-data-in-microsoft-dynamics-365"></a><span data-ttu-id="421db-255">Exécuter un script qui dépend de données de Microsoft Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="421db-255">Run a script that depends on data in Microsoft Dynamics 365</span></span>

<span data-ttu-id="421db-256">L'exemple suivant utilise un appel OData (Open Data Protocol) pour rechercher le statut d'une commande fournisseur.</span><span class="sxs-lookup"><span data-stu-id="421db-256">The following example uses an Open Data Protocol (OData) call to find the order status of a purchase order.</span></span> <span data-ttu-id="421db-257">Si le statut n'est pas **facturé**, vous pouvez, par exemple, appeler un scénario de test RSAT qui valide la facture.</span><span class="sxs-lookup"><span data-stu-id="421db-257">If the status isn't **invoiced**, you can, for example, call an RSAT test case that posts the invoice.</span></span>

```
function Odata_Get
{
    Param ( [string] $environment, [string] $cmd )
    [Net.ServicePointManager]::SecurityProtocol = [Net.SecurityProtocolType]::Tls12
    $tenant = "your tenant"
    $creds = @{
        grant_type = "client_credentials"
        client_id = "your client application Id"
        client_secret = "your client secret"
        resource = $environment
    }
    $headers = $null
    $bearer = Invoke-RestMethod https://login.microsoftonline.com/$tenant/oauth2/token -Method Post -Body $creds -Headers $headers;
    $headers = @{
        Authorization = "Bearer " + $bearer.access_token
    }
    $Odata_cmd = $environment + '/data/' + $cmd
    return (Invoke-RestMethod -Uri $Odata_cmd -Method Get -Headers $headers -ContentType application/json )
}
function PurchaseOrderStatus
{
    Param ( [string] $environment, [string] $purchaseOrderNumber )
    $cmd = 'PurchaseOrderHeaders?$filter=PurchaseOrderNumber eq '
    $cmd = $cmd + "'" + $purchaseOrderNumber + "'"
    $response = Odata_Get -environment $environment -cmd $cmd
    return $response.value.PurchaseOrderStatus
}
$environment = "https://your environment"
$orderStatus = PurchaseOrderStatus -environment $environment -purchaseOrderNumber '000003'
if ($orderStatus -eq $null) {   write-host 'doesn''t exist'}
elseif ($orderStatus -ne 'invoiced') { RunTestCase "PostInvoice" }
```
