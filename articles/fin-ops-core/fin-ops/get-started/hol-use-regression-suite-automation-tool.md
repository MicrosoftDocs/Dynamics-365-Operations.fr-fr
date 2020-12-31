---
title: Utiliser le didacticiel Regression Suite Automation Tool
description: Cette rubrique explique comment utiliser l’outil RSAT (Regression Suite Automation Tool). Il en décrit les diverses fonctions et fournit des exemples qui utilisent l’écriture de script avancée.
author: robinarh
manager: AnnBe
ms.date: 06/09/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: rhaertle
ms.custom: 21761
ms.search.region: Global
ms.author: rhaertle
ms.search.validFrom: 2017-06-30
ms.dyn365.ops.version: AX 7.0.0, Operations
ms.openlocfilehash: 798717b276e68949a9425350720bf683a37d6fb5
ms.sourcegitcommit: f5e31c34640add6d40308ac1365cc0ee60e60e24
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/08/2020
ms.locfileid: "4692988"
---
# <a name="regression-suite-automation-tool-tutorial"></a><span data-ttu-id="982e2-104">Didacticiel Regression Suite Automation Tool</span><span class="sxs-lookup"><span data-stu-id="982e2-104">Regression suite automation tool tutorial</span></span>

[!include [banner](../includes/banner.md)]

> [!NOTE]
> <span data-ttu-id="982e2-105">Utilisez les outils du navigateur Internet pour télécharger et enregistrer cette page au format PDF.</span><span class="sxs-lookup"><span data-stu-id="982e2-105">Use your internet browser tools to download and save this page in pdf format.</span></span> 

<span data-ttu-id="982e2-106">Ce didacticiel vous explique quelques-unes des fonctions avancées de l’outil RSAT (Regression Suite Automation Tool), inclut une mission de démonstration et décrit des points stratégiques et d’apprentissage clés.</span><span class="sxs-lookup"><span data-stu-id="982e2-106">This tutorial walks through some of the advanced features of the Regression suite automation tool (RSAT), includes a demo assignment, and describes strategy and key learning points.</span></span> 

## <a name="notable-features-of-rsat-and-task-recorder"></a><span data-ttu-id="982e2-107">Caractéristiques notables de RSAT et de l’enregistreur de tâches</span><span class="sxs-lookup"><span data-stu-id="982e2-107">Notable Features of RSAT and Task recorder</span></span>

### <a name="validate-a-field-value"></a><span data-ttu-id="982e2-108">Valider une valeur du champ</span><span class="sxs-lookup"><span data-stu-id="982e2-108">Validate a field value</span></span>

<span data-ttu-id="982e2-109">RSAT vous permet d’inclure des étapes de validation dans votre scénario de test pour valider les valeurs attendues.</span><span class="sxs-lookup"><span data-stu-id="982e2-109">RSAT allows you to include validation steps within your test case to validate expected values.</span></span> <span data-ttu-id="982e2-110">Pour plus d’informations sur cette fonctionnalité, consultez l’article [Valider des valeurs prévues](../../dev-itpro/perf-test/rsat/rsat-validate-expected.md).</span><span class="sxs-lookup"><span data-stu-id="982e2-110">For information about this feature, see the article [Validate expected values](../../dev-itpro/perf-test/rsat/rsat-validate-expected.md).</span></span>

<span data-ttu-id="982e2-111">L’exemple suivant montre comment vous pouvez utiliser cette fonction pour vérifier si le stock disponible est supérieur à 0 (zéro).</span><span class="sxs-lookup"><span data-stu-id="982e2-111">The following example shows how you can use this feature to validate whether the on-hand inventory is more than 0 (zero).</span></span>

1. <span data-ttu-id="982e2-112">Dans les données de démonstration de la société **USMF**, créez un enregistrement de tâche ayant les étapes suivantes :</span><span class="sxs-lookup"><span data-stu-id="982e2-112">In the demo data in the **USMF** company, create a task recording that has the following steps:</span></span>

    1. <span data-ttu-id="982e2-113">Allez à **Gestion des informations sur les produits \> Produits \> Produits lancés**.</span><span class="sxs-lookup"><span data-stu-id="982e2-113">Go to **Product information management \> Products \> Released products**.</span></span>
    2. <span data-ttu-id="982e2-114">Utilisez le Filtre rapide pour rechercher les enregistrements.</span><span class="sxs-lookup"><span data-stu-id="982e2-114">Use the Quick Filter to find records.</span></span> <span data-ttu-id="982e2-115">Par exemple, filtrez une valeur **1000** pour le champ **Numéro d’article**.</span><span class="sxs-lookup"><span data-stu-id="982e2-115">For example, filter on a value of **1000** for the **Item number** field.</span></span>
    3. <span data-ttu-id="982e2-116">Sélectionnez **Stock disponible**.</span><span class="sxs-lookup"><span data-stu-id="982e2-116">Select **On-hand inventory**.</span></span>
    4. <span data-ttu-id="982e2-117">Utilisez le Filtre rapide pour rechercher les enregistrements.</span><span class="sxs-lookup"><span data-stu-id="982e2-117">Use the Quick Filter to find records.</span></span> <span data-ttu-id="982e2-118">Par exemple, filtrez une valeur **1** pour le champ **Site**.</span><span class="sxs-lookup"><span data-stu-id="982e2-118">For example, filter on a value of **1** for the **Site** field.</span></span>
    5. <span data-ttu-id="982e2-119">Dans la liste, marquer la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="982e2-119">In the list, mark the selected row.</span></span>
    6. <span data-ttu-id="982e2-120">Vérifiez que la valeur du champ **Total disponible** est **411,0000000000000000**.</span><span class="sxs-lookup"><span data-stu-id="982e2-120">Validate that the value of the **Total available** field is **411.0000000000000000**.</span></span>

2. <span data-ttu-id="982e2-121">Enregistrez l’enregistrement de tâche et joignez-le à votre scénario de test dans Azure Devops.</span><span class="sxs-lookup"><span data-stu-id="982e2-121">Save the task recording and attach it to your test case in Azure Devops.</span></span>
3. <span data-ttu-id="982e2-122">Ajoutez le scénario de test au plan de test, puis chargez le scénario de test dans RSAT.</span><span class="sxs-lookup"><span data-stu-id="982e2-122">Add the test case to the test plan, and load the test case into RSAT.</span></span>
4. <span data-ttu-id="982e2-123">Ouvrez le fichier de paramètres Excel.</span><span class="sxs-lookup"><span data-stu-id="982e2-123">Open the Excel parameter file.</span></span> <span data-ttu-id="982e2-124">Dans l’onglet **InventOnhandItem**, vous voyez une section **Valider InventOnhandItem** qui inclut un champ **Opérateur**.</span><span class="sxs-lookup"><span data-stu-id="982e2-124">On the **InventOnhandItem** tab, you will see a **Validate InventOnhandItem** section that includes an **Operator** field.</span></span>

    ![Champ Opérateur](./media/use_rsa_tool_08.png)

5. <span data-ttu-id="982e2-126">Pour vérifier si le stock disponible est toujours supérieur à 0, modifiez la valeur du champ **Valeur** de **411** à **0** et la valeur du champ **Opérateur** d’un signe égal (**=**) à un signe supérieur à (**\>**).</span><span class="sxs-lookup"><span data-stu-id="982e2-126">To validate whether the inventory on-hand will always be more than 0, change the value of the **Value** field from **411** to **0** and the value of the **Operator** field from an equal sign (**=**) to a greater than sign (**\>**).</span></span>

    ![Valeurs des champs Valeur et Opérateur modifiées](./media/use_rsa_tool_09.png)

6. <span data-ttu-id="982e2-128">Enregistrez et fermez le fichier de paramètres Excel.</span><span class="sxs-lookup"><span data-stu-id="982e2-128">Save and close the Excel parameter file.</span></span>
7. <span data-ttu-id="982e2-129">Sélectionnez **Upload** pour enregistrer les modifications apportées au fichier de paramètres Excel dans Azure DevOps.</span><span class="sxs-lookup"><span data-stu-id="982e2-129">Select **Upload** to save the changes that you made to the Excel parameter file to Azure DevOps.</span></span>

<span data-ttu-id="982e2-130">Désormais, si la valeur du champ **Total disponible** pour l’article spécifié en stock est supérieure à 0 (zéro), les tests réussiront, indépendamment de la valeur réelle du stock disponible.</span><span class="sxs-lookup"><span data-stu-id="982e2-130">Now, if the value of the **Total Available** field for the specified item in inventory is more than 0 (zero), tests will pass, regardless of the actual on-hand inventory value.</span></span>

### <a name="saved-variables-and-chaining-of-test-cases"></a><span data-ttu-id="982e2-131">Variables enregistrées et enchaînement des cas de test</span><span class="sxs-lookup"><span data-stu-id="982e2-131">Saved variables and chaining of test cases</span></span>

<span data-ttu-id="982e2-132">L’une des fonctionnalités principales de RSAT n’est autre que l’enchaînement de cas de test, autrement dit la possibilité pour un test de transmettre des variables à d’autres tests.</span><span class="sxs-lookup"><span data-stu-id="982e2-132">One of the key features of RSAT is the chaining of test cases, that is, the ability of a test to pass variables to other tests.</span></span> <span data-ttu-id="982e2-133">Pour plus d’informations, consultez l’article [Copier des variables pour enchaîner des cas de test](../../dev-itpro/perf-test/rsat/rsat-chain-test-cases.md).</span><span class="sxs-lookup"><span data-stu-id="982e2-133">For more information, see the article [Copy variables to chain test cases](../../dev-itpro/perf-test/rsat/rsat-chain-test-cases.md).</span></span>

### <a name="derived-test-case"></a><span data-ttu-id="982e2-134">Scénario de test dérivé</span><span class="sxs-lookup"><span data-stu-id="982e2-134">Derived test case</span></span>

<span data-ttu-id="982e2-135">RSAT vous permet d’utiliser le même enregistrement de tâche avec plusieurs cas de test, permettant à une tâche de s’exécuter avec différentes configurations de données.</span><span class="sxs-lookup"><span data-stu-id="982e2-135">RSAT lets you use the same task recording with multiple test cases, enabling a task to run with different data configurations.</span></span> <span data-ttu-id="982e2-136">Voir l’article [Cas de test dérivés](../../dev-itpro/perf-test/rsat/rsat-derived-test-cases.md) pour plus d’informations.</span><span class="sxs-lookup"><span data-stu-id="982e2-136">See the article [Derived test cases](../../dev-itpro/perf-test/rsat/rsat-derived-test-cases.md) for more information.</span></span>

### <a name="validate-notifications-and-messages"></a><span data-ttu-id="982e2-137">Valider les notifications et les messages</span><span class="sxs-lookup"><span data-stu-id="982e2-137">Validate notifications and messages</span></span>

<span data-ttu-id="982e2-138">Cette fonction peut être utilisée pour vérifier si une action s’est produite.</span><span class="sxs-lookup"><span data-stu-id="982e2-138">This feature can be used to validate whether an action occurred.</span></span> <span data-ttu-id="982e2-139">Par exemple, lorsqu’un ordre de fabrication est créé, estimé, puis démarré, l’application présente un message « Production – démarrer » pour vous informer que l’ordre de fabrication a commencé.</span><span class="sxs-lookup"><span data-stu-id="982e2-139">For example, when a production order is created, estimated, and then started, the app shows a "Production – Start" message to notify you that the production order has been started.</span></span>

![Notification Production – Démarrer](./media/use_rsa_tool_05.png)

<span data-ttu-id="982e2-141">Vous pouvez valider ce message dans RSAT en entrant le texte du message dans l’onglet **Validation du message** du fichier de paramètres Excel pour l’enregistrement approprié.</span><span class="sxs-lookup"><span data-stu-id="982e2-141">You can validate this message through RSAT by entering the message text on the **MessageValidation** tab of the Excel parameter file for the appropriate recording.</span></span>

![Onglet Validation du message](./media/use_rsa_tool_06.png)

<span data-ttu-id="982e2-143">Une fois le scénario de test exécuté, le message du fichier de paramètres Excel est comparé au message qui s’affiche.</span><span class="sxs-lookup"><span data-stu-id="982e2-143">After the test case is run, the message in the Excel parameter file is compared to the message that is shown.</span></span> <span data-ttu-id="982e2-144">Si les messages ne correspondent pas, le scénario de test échoue.</span><span class="sxs-lookup"><span data-stu-id="982e2-144">If the messages don't match, the test case will fail.</span></span>

> [!NOTE]
> <span data-ttu-id="982e2-145">Vous pouvez entrer plusieurs messages dans l’onglet **Validation du message** du fichier de paramètres Excel.</span><span class="sxs-lookup"><span data-stu-id="982e2-145">You can enter more than one message on the **MessageValidation** tab in the Excel parameter file.</span></span> <span data-ttu-id="982e2-146">Les messages peuvent également être des messages d’erreur ou d’avertissement au lieu de messages d’information.</span><span class="sxs-lookup"><span data-stu-id="982e2-146">The messages also can be error or warning messages instead of informational messages.</span></span>

### <a name="snapshot"></a><span data-ttu-id="982e2-147">Instantané</span><span class="sxs-lookup"><span data-stu-id="982e2-147">Snapshot</span></span>

<span data-ttu-id="982e2-148">Cette fonction prend des captures d’écran des étapes qui ont été effectuées au cours de l’enregistrement de tâche.</span><span class="sxs-lookup"><span data-stu-id="982e2-148">This feature takes screenshots of the steps that were performed during task recording.</span></span> <span data-ttu-id="982e2-149">Il est utile à des fins d’audit ou de débogage.</span><span class="sxs-lookup"><span data-stu-id="982e2-149">It is useful for auditing or debugging purposes.</span></span>

- <span data-ttu-id="982e2-150">Pour utiliser cette fonction, ouvrez le fichier **Microsoft.Dynamics.RegressionSuite.WindowsApp.exe.config** sous le dossier d’installation de RSAT (par exemple, **C:\\Program Files (x86)\\Regression Suite Automation Tool**), puis modifiez la valeur de l’élément suivant de **faux** à **vrai**.</span><span class="sxs-lookup"><span data-stu-id="982e2-150">To use this feature, open the **Microsoft.Dynamics.RegressionSuite.WindowsApp.exe.config** file under the RSAT installation folder (for example, **C:\\Program Files (x86)\\Regression Suite Automation Tool**), and change the value of the following element from **false** to **true**.</span></span>

    ```xml
    <add key="VerboseSnapshotsEnabled" value="false" />
    ```

<span data-ttu-id="982e2-151">Lorsque vous exécutez le scénario de test, RSAT génère des instantanés (images) des étapes dans le dossier de lecture des scénarios de test dans le répertoire de travail.</span><span class="sxs-lookup"><span data-stu-id="982e2-151">When your run the test case, RSAT will generate snapshots (images) of the steps in the playback folder of the test cases in the working diretory.</span></span> <span data-ttu-id="982e2-152">Si vous utilisez une version précédente de RSAT, les images sont sauvegardées vers **C:\\Utilisateurs\\\<Username\>\\AppData\\Roaming\\regressionTool\\playback**, un dossier distinct est créé pour chaque cas de test exécuté.</span><span class="sxs-lookup"><span data-stu-id="982e2-152">If you are using an older version of RSAT, the images are saved to **C:\\Users\\\<Username\>\\AppData\\Roaming\\regressionTool\\playback**, a separate folder is created for each test case that is run.</span></span>

## <a name="assignment"></a><span data-ttu-id="982e2-153">Affectation</span><span class="sxs-lookup"><span data-stu-id="982e2-153">Assignment</span></span>

### <a name="scenario"></a><span data-ttu-id="982e2-154">Scénario</span><span class="sxs-lookup"><span data-stu-id="982e2-154">Scenario</span></span>

1. <span data-ttu-id="982e2-155">Le concepteur de produit crée un nouveau produit lancé.</span><span class="sxs-lookup"><span data-stu-id="982e2-155">The product designer creates a new released product.</span></span>
2. <span data-ttu-id="982e2-156">Le gestionnaire de production lance un ordre de fabrication pour amener le niveau de stock à deux unités.</span><span class="sxs-lookup"><span data-stu-id="982e2-156">The production manager initiates a production order to bring the stock level to two pieces.</span></span>
3. <span data-ttu-id="982e2-157">La fabrication démarre et termine l’ordre de fabrication, et vérifie que la quantité disponible est de deux unités.</span><span class="sxs-lookup"><span data-stu-id="982e2-157">Manufacturing starts and ends the production order, and verifies that the on-hand quantity is two pieces.</span></span>
4. <span data-ttu-id="982e2-158">L’équipe commerciale reçoit une commande de quatre unités du nouveau produit.</span><span class="sxs-lookup"><span data-stu-id="982e2-158">The sales team receives an order for four pieces of the new product.</span></span> <span data-ttu-id="982e2-159">Par conséquent, l’équipe de vente présente les besoins nets via le plan dynamique.</span><span class="sxs-lookup"><span data-stu-id="982e2-159">Therefore, the sales team updates the net requirements via the dynamic plan.</span></span> <span data-ttu-id="982e2-160">Comme aucune capacité supplémentaire n’est disponible, la stratégie de commande par défaut est définie sur « acheter plutôt que fabriquer ».</span><span class="sxs-lookup"><span data-stu-id="982e2-160">Because no additional capacity is available, the default order policy is set to "buy instead of make."</span></span> <span data-ttu-id="982e2-161">Par conséquent, une commande fournisseur est créée.</span><span class="sxs-lookup"><span data-stu-id="982e2-161">Therefore, a planned purchase order is created.</span></span>
5. <span data-ttu-id="982e2-162">L’acheteur ajoute un fournisseur, confirme la commande fournisseur prévisionnelle, puis confirme la commande fournisseur.</span><span class="sxs-lookup"><span data-stu-id="982e2-162">The buyer adds a vendor, firms the planned purchase order, and then confirms the purchase order.</span></span>
6. <span data-ttu-id="982e2-163">Lorsque les marchandises achetées arrivent au magasin, le magasinier recherche la commande fournisseur associée et réceptionne les marchandises.</span><span class="sxs-lookup"><span data-stu-id="982e2-163">When the goods that were purchased arrive at the store, the store operator searches the related purchase order and receives the goods.</span></span> <span data-ttu-id="982e2-164">Comme la commande est maintenant terminée, les marchandises peuvent être prélevées et emballées conformément à la commande client.</span><span class="sxs-lookup"><span data-stu-id="982e2-164">Because the order is now completed, goods can be picked and packed against the sales order.</span></span>
7. <span data-ttu-id="982e2-165">Le service financier valide la facture fournisseur et la facture client.</span><span class="sxs-lookup"><span data-stu-id="982e2-165">Finance posts the purchase invoice and sales invoice.</span></span>

<span data-ttu-id="982e2-166">La figure suivante présente une capture d’écran du flux de ce scénario.</span><span class="sxs-lookup"><span data-stu-id="982e2-166">The following illustration shows the flow for this scenario.</span></span>

![Flux du scénario de démonstration](./media/use_rsa_tool_14.png)

<span data-ttu-id="982e2-168">L’illustration suivante montre la hiérarchie des processus métier pour ce scénario dans le Concepteur de processus d’entreprise LCS.</span><span class="sxs-lookup"><span data-stu-id="982e2-168">The following illustration shows the business processes hierarchy for this scenario in the LCS Business Process Modeler.</span></span>

![Processus métier pour le scénario de démonstration](./media/use_rsa_tool_15.png)

## <a name="strategy--key-learning"></a><span data-ttu-id="982e2-170">Stratégie – Points d’apprentissage clés</span><span class="sxs-lookup"><span data-stu-id="982e2-170">Strategy – Key learning</span></span>

### <a name="data"></a><span data-ttu-id="982e2-171">Données</span><span class="sxs-lookup"><span data-stu-id="982e2-171">Data</span></span>

- <span data-ttu-id="982e2-172">Assurez-vous d’avoir des volumes de données représentatifs (une copie des données de production/configuration Golden, plus des données migrées).</span><span class="sxs-lookup"><span data-stu-id="982e2-172">Make sure that you have representative data volumes (a copy of production/golden configuration data plus migrated data).</span></span>
- <span data-ttu-id="982e2-173">Lorsque vous générez de nouvelles données via l’enregistreur de tâches, créez des noms de test qui ne seront pas en conflit avec des noms existants (par exemple, utilisez un préfixe tel que **RSATxxx**).</span><span class="sxs-lookup"><span data-stu-id="982e2-173">When you generate new data via Task recorder, create test names that won't conflict with existing names (for example, use a prefix such as **RSATxxx**).</span></span>
- <span data-ttu-id="982e2-174">Utilisez la restauration ponctuelle Azure pour réexécuter les tests dans des environnements de niveau autre que 1.</span><span class="sxs-lookup"><span data-stu-id="982e2-174">Use Azure Point-In-Time restore to rerun tests in non-Tier 1 environments.</span></span>
- <span data-ttu-id="982e2-175">Bien que vous puissiez utiliser les fonctions Excel **RANDOM** et **NOW** pour générer une combinaison unique, la charge de travail est considérable.</span><span class="sxs-lookup"><span data-stu-id="982e2-175">Although you can use the **RANDOM** and **NOW** Excel functions to generate a unique combination, the effort is considerably high.</span></span> <span data-ttu-id="982e2-176">Voici un exemple :</span><span class="sxs-lookup"><span data-stu-id="982e2-176">Here is an example.</span></span>

    ```Excel
    product = "AT" &TEXT(NOW(),"yyymmddhhmm")
    ```

### <a name="task-recorder"></a><span data-ttu-id="982e2-177">Enregistreur de tâches</span><span class="sxs-lookup"><span data-stu-id="982e2-177">Task recorder</span></span>

- <span data-ttu-id="982e2-178">Définissez les scénarios avant de commencer l’enregistrement.</span><span class="sxs-lookup"><span data-stu-id="982e2-178">Define scenarios before you start recording.</span></span> <span data-ttu-id="982e2-179">Un projet bien géré a des scénarios de test prédéfinis.</span><span class="sxs-lookup"><span data-stu-id="982e2-179">A well-managed project has predefined test scenarios.</span></span> <span data-ttu-id="982e2-180">Pour établir un scénario de test, prenez en compte la prédictibilité des résultats de ces scénarios de test.</span><span class="sxs-lookup"><span data-stu-id="982e2-180">To build a test case, consider how predictable the outcome of those test scenarios is.</span></span>
- <span data-ttu-id="982e2-181">Fractionnez les enregistrements s’ils sont réalisés par des rôles différents, ou s’il existe un temps d’attente ou un événement externe avant l’étape suivante.</span><span class="sxs-lookup"><span data-stu-id="982e2-181">Split recordings if they are performed by different roles, or if there is waiting time or an external event before the next step.</span></span>
- <span data-ttu-id="982e2-182">Évitez de sélectionner des valeurs dans des listes.</span><span class="sxs-lookup"><span data-stu-id="982e2-182">Avoid selecting values in lists.</span></span> <span data-ttu-id="982e2-183">Au lieu de cela, utilisez des formats texte, tels que **FIFO**, **AudioRM** et **SiteWH**.</span><span class="sxs-lookup"><span data-stu-id="982e2-183">Instead, use text formats, such as **FIFO**, **AudioRM**, and **SiteWH**.</span></span> <span data-ttu-id="982e2-184">Si vous faites une sélection dans une liste, c’est la position de la valeur dans la liste qui est enregistrée, pas la valeur elle-même.</span><span class="sxs-lookup"><span data-stu-id="982e2-184">When you select in a list, the position of the value in the list is recorded, not the value itself.</span></span> <span data-ttu-id="982e2-185">Si des articles sont ajoutés à cette liste, la position de la valeur peut changer.</span><span class="sxs-lookup"><span data-stu-id="982e2-185">If items are added to that list, the position of the value can change.</span></span> <span data-ttu-id="982e2-186">Par conséquent, l’enregistrement utilisera un paramètre différent, et le reste du scénario peut en être affecté.</span><span class="sxs-lookup"><span data-stu-id="982e2-186">Therefore, your recording will use a different parameter, and the rest of the scenario might be affected.</span></span>
- <span data-ttu-id="982e2-187">Pensez au comportement multi-utilisateur.</span><span class="sxs-lookup"><span data-stu-id="982e2-187">Think about multi-user behavior.</span></span> <span data-ttu-id="982e2-188">Par exemple, ne supposez pas que votre commande client nouvellement créée sera toujours sélectionnée automatiquement.</span><span class="sxs-lookup"><span data-stu-id="982e2-188">For example, don't assume that your newly created sales order will always be automatically selected.</span></span> <span data-ttu-id="982e2-189">Au lieu de cela, utilisez toujours le filtre permettant de trouver la commande appropriée.</span><span class="sxs-lookup"><span data-stu-id="982e2-189">Instead, always use the filter to find the correct order.</span></span>
- <span data-ttu-id="982e2-190">Utilisez la fonction Copier dans l’enregistreur de tâches pour enregistrer le nom d’un produit nouvellement créé, de manière à l’utiliser dans des scénarios de test enchaînés.</span><span class="sxs-lookup"><span data-stu-id="982e2-190">Use the Copy function in Task recorder to save the name of a newly created product so it can be used in chained test cases.</span></span>
- <span data-ttu-id="982e2-191">Utilisez la fonction Valider de l’enregistreur de tâches pour définir des points de contrôle pour vérifier que les étapes ont été exécutées correctement.</span><span class="sxs-lookup"><span data-stu-id="982e2-191">Use the Validate function in Task recorder to set checkpoints that verify that steps have been run correctly.</span></span>

### <a name="rsat"></a><span data-ttu-id="982e2-192">RSAT</span><span class="sxs-lookup"><span data-stu-id="982e2-192">RSAT</span></span>

- <span data-ttu-id="982e2-193">Pour exécuter le test sur une autre société, vous pouvez modifier la société sur l’onglet **Général** du fichier de paramètres Excel.</span><span class="sxs-lookup"><span data-stu-id="982e2-193">To run the test in another company, you can change the company on the **General** tab of the Excel parameter file.</span></span> <span data-ttu-id="982e2-194">Vérifiez que les paramètres et les données sont disponibles dans la société récemment sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="982e2-194">Make sure that settings and data are available in the newly selected company.</span></span>
- <span data-ttu-id="982e2-195">Vous pouvez modifier l’utilisateur du test dans l’onglet **Général** du fichier de paramètres Excel.</span><span class="sxs-lookup"><span data-stu-id="982e2-195">You can change the test user on the **General** tab of the Excel parameter file.</span></span> <span data-ttu-id="982e2-196">Indiquez l’ID d’e-mail de l’utilisateur qui exécutera le scénario de test.</span><span class="sxs-lookup"><span data-stu-id="982e2-196">Specify the email ID of the user who will run the test case.</span></span> <span data-ttu-id="982e2-197">Ainsi, le scénario de test pourra être exécuté à l’aide des autorisations de sécurité de l’utilisateur spécifié.</span><span class="sxs-lookup"><span data-stu-id="982e2-197">In this way, the test case can be run by using the security permissions of the specified user.</span></span>
- <span data-ttu-id="982e2-198">Pour attendre le démarrage du test, vous pouvez définir une pause dans l’onglet **Général** du fichier de paramètres Excel.</span><span class="sxs-lookup"><span data-stu-id="982e2-198">To wait before the test is started, you can define a pause on the **General** tab of the Excel parameter file.</span></span> <span data-ttu-id="982e2-199">Cette pause peut être utilisée dans un traitement par lots (par exemple, si un workflow doit être exécuté avant que l’étape suivante ne puisse être réalisée.)</span><span class="sxs-lookup"><span data-stu-id="982e2-199">This pause can be used in a batch job (for example, if a workflow must be run before the next step can be performed.)</span></span>

## <a name="advanced-scripting"></a><span data-ttu-id="982e2-200">Écriture de script avancée</span><span class="sxs-lookup"><span data-stu-id="982e2-200">Advanced scripting</span></span>

### <a name="cli"></a><span data-ttu-id="982e2-201">CLI</span><span class="sxs-lookup"><span data-stu-id="982e2-201">CLI</span></span>

<span data-ttu-id="982e2-202">RSAT peut être appelé à partir d’une fenêtre **Invite de commandes** ou **PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="982e2-202">RSAT can be called from a **Command Prompt** or **PowerShell** window.</span></span>

> [!NOTE]
> <span data-ttu-id="982e2-203">Vérifiez que la variable d’environnement **TestRoot** est définie sur le chemin d’installation de RSAT.</span><span class="sxs-lookup"><span data-stu-id="982e2-203">Verify that the **TestRoot** environment variable is set to the RSAT installation path.</span></span> <span data-ttu-id="982e2-204">(Dans Microsoft Windows, ouvrez **Panneau de configuration**, sélectionnez **Système et sécurité \> Système \> Paramètres système avancés**, puis sélectionnez **Variables d’environnement**.)</span><span class="sxs-lookup"><span data-stu-id="982e2-204">(In Microsoft Windows, open **Control Panel**, select **System and Security \> System \> Advanced system settings**, and then select **Environment Variables**.)</span></span>

1. <span data-ttu-id="982e2-205">Ouvrez une fenêtre **Invite de commandes** ou **PowerShell** en tant qu’administrateur.</span><span class="sxs-lookup"><span data-stu-id="982e2-205">Open a **Command Prompt** or **PowerShell** window as an admin.</span></span>
2. <span data-ttu-id="982e2-206">Accédez au répertoire d’installation de RSAT.</span><span class="sxs-lookup"><span data-stu-id="982e2-206">Navigate to the RSAT installation directory.</span></span>

    ```Console
    cd "c:\Program Files (x86)\Regression Suite Automation Tool\"
    ```

3. <span data-ttu-id="982e2-207">Répertoriez toutes les commandes.</span><span class="sxs-lookup"><span data-stu-id="982e2-207">List all commands.</span></span>

    ```Console
    C:\Program Files (x86)\Regression Suite Automation Tool>Microsoft.Dynamics.RegressionSuite.ConsoleApp.exe help

    Usage:
        Microsoft.Dynamics.RegressionSuite.ConsoleApp.exe command
        or
        Microsoft.Dynamics.RegressionSuite.ConsoleApp.exe /settings "C:\Path to\file.settings" command

    Available commands:
        ?
        about
        cls
        download
        edit
        generate
        generatederived
        generatetestonly
        generatetestsuite
        help
        list
        listtestplans
        listtestsuite
        listtestsuitenames
        playback
        playbackbyid
        playbackmany
        playbacksuite
        quit
        upload
        uploadrecording
        usage
    ```

#### <a name=""></a><span data-ttu-id="982e2-208">?</span><span class="sxs-lookup"><span data-stu-id="982e2-208">?</span></span> 
<span data-ttu-id="982e2-209">Affiche l’aide sur toutes les commandes disponibles et leurs paramètres.</span><span class="sxs-lookup"><span data-stu-id="982e2-209">Shows help about all available commands and their parameters.</span></span>

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``?``**``[command]``

##### <a name="optional-parameters"></a><span data-ttu-id="982e2-210">Paramètres facultatifs</span><span class="sxs-lookup"><span data-stu-id="982e2-210">Optional parameters</span></span>

**``command``**


<span data-ttu-id="982e2-211">Où ``[command]`` est l’une des commandes spécifiées ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="982e2-211">Where ``[command]`` is one of the commands specified below.</span></span>


#### <a name="about"></a><span data-ttu-id="982e2-212">à propos de</span><span class="sxs-lookup"><span data-stu-id="982e2-212">about</span></span>
<span data-ttu-id="982e2-213">Affiche la version actuelle.</span><span class="sxs-lookup"><span data-stu-id="982e2-213">Displays the current version.</span></span>

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``about``**

#### <a name="cls"></a><span data-ttu-id="982e2-214">cls</span><span class="sxs-lookup"><span data-stu-id="982e2-214">cls</span></span>
<span data-ttu-id="982e2-215">Efface l’écran.</span><span class="sxs-lookup"><span data-stu-id="982e2-215">Clears the screen.</span></span>

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``cls``**


#### <a name="download"></a><span data-ttu-id="982e2-216">télécharger</span><span class="sxs-lookup"><span data-stu-id="982e2-216">download</span></span>
<span data-ttu-id="982e2-217">Télécharge les pièces jointes pour le scénario de test spécifié dans le répertoire de sortie.</span><span class="sxs-lookup"><span data-stu-id="982e2-217">Downloads attachments for the specified test case to the output directory.</span></span> <span data-ttu-id="982e2-218">Vous pouvez utiliser la commande ``list`` pour obtenir tous les scénarios de test disponibles.</span><span class="sxs-lookup"><span data-stu-id="982e2-218">You can use the ``list`` command to get all available test cases.</span></span> <span data-ttu-id="982e2-219">Utilisez n’importe quelle valeur de la première colonne comme paramètre **test_case_id**.</span><span class="sxs-lookup"><span data-stu-id="982e2-219">Use any value from the first column as a **test_case_id** parameter.</span></span>

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``download``**``[test_case_id] [output_dir]``

##### <a name="required-parameters"></a><span data-ttu-id="982e2-220">Paramètres obligatoires</span><span class="sxs-lookup"><span data-stu-id="982e2-220">Required parameters</span></span>
<span data-ttu-id="982e2-221">**``test_case_id``** Représente l’ID du scénario de test.</span><span class="sxs-lookup"><span data-stu-id="982e2-221">**``test_case_id``** Represents the test case ID.</span></span>  
<span data-ttu-id="982e2-222">**``output_dir``** Représente le répertoire de sortie.</span><span class="sxs-lookup"><span data-stu-id="982e2-222">**``output_dir``** Represents the output directory.</span></span> <span data-ttu-id="982e2-223">Le répertoire doit exister.</span><span class="sxs-lookup"><span data-stu-id="982e2-223">The directory must exist.</span></span>

##### <a name="examples"></a><span data-ttu-id="982e2-224">Exemples</span><span class="sxs-lookup"><span data-stu-id="982e2-224">Examples</span></span>

``download 123 c:\temp\rsat``   
``download 765 c:\rsat\last``


#### <a name="edit"></a><span data-ttu-id="982e2-225">modifier</span><span class="sxs-lookup"><span data-stu-id="982e2-225">edit</span></span>
<span data-ttu-id="982e2-226">Vous permet d’ouvrir le fichier de paramètres dans le programme Excel et de le modifier.</span><span class="sxs-lookup"><span data-stu-id="982e2-226">Allows you to open parameters file in Excel program and edit it.</span></span>

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``edit``**``[excel_file]``

##### <a name="required-parameters"></a><span data-ttu-id="982e2-227">Paramètres obligatoires</span><span class="sxs-lookup"><span data-stu-id="982e2-227">Required parameters</span></span>
<span data-ttu-id="982e2-228">**``excel_file``** Doit contenir un chemin d’accès complet à un fichier Excel existant.</span><span class="sxs-lookup"><span data-stu-id="982e2-228">**``excel_file``** Must contain a full path to an existing Excel file.</span></span>

##### <a name="examples"></a><span data-ttu-id="982e2-229">Exemples</span><span class="sxs-lookup"><span data-stu-id="982e2-229">Examples</span></span>
``edit c:\RSAT\TestCase_123_Base.xlsx``  
``edit e:\temp\TestCase_456_Base.xlsx``


#### <a name="generate"></a><span data-ttu-id="982e2-230">generate</span><span class="sxs-lookup"><span data-stu-id="982e2-230">generate</span></span>
<span data-ttu-id="982e2-231">Génère les fichiers d’exécution de tests et de paramètre pour le scénario de test spécifié dans le répertoire de sortie.</span><span class="sxs-lookup"><span data-stu-id="982e2-231">Generates test execution and parameter files for the specified test case in the output directory.</span></span>
<span data-ttu-id="982e2-232">Vous pouvez utiliser la commande ``list`` pour obtenir tous les scénarios de test disponibles.</span><span class="sxs-lookup"><span data-stu-id="982e2-232">You can use the ``list`` command to get all available test cases.</span></span> <span data-ttu-id="982e2-233">Utilisez n’importe quelle valeur de la première colonne comme paramètre **test_case_id**.</span><span class="sxs-lookup"><span data-stu-id="982e2-233">Use any value from the first column as a **test_case_id** parameter.</span></span>

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``generate``**``[test_case_id] [output_dir]``

##### <a name="required-parameters"></a><span data-ttu-id="982e2-234">Paramètres obligatoires</span><span class="sxs-lookup"><span data-stu-id="982e2-234">Required parameters</span></span>
<span data-ttu-id="982e2-235">**``test_case_id``** Représente l’ID du scénario de test.</span><span class="sxs-lookup"><span data-stu-id="982e2-235">**``test_case_id``** Represents the test case ID.</span></span>  
<span data-ttu-id="982e2-236">**``output_dir``** Représente le répertoire de sortie.</span><span class="sxs-lookup"><span data-stu-id="982e2-236">**``output_dir``** Represents the output directory.</span></span> <span data-ttu-id="982e2-237">Le répertoire doit exister.</span><span class="sxs-lookup"><span data-stu-id="982e2-237">The directory must exist.</span></span>

##### <a name="examples"></a><span data-ttu-id="982e2-238">Exemples</span><span class="sxs-lookup"><span data-stu-id="982e2-238">Examples</span></span>
``generate 123 c:\temp\rsat``  
``generate 765 c:\rsat\last``


#### <a name="generatederived"></a><span data-ttu-id="982e2-239">generatederived</span><span class="sxs-lookup"><span data-stu-id="982e2-239">generatederived</span></span>
<span data-ttu-id="982e2-240">Génère un nouveau scénario de test, dérivé du scénario de test fourni.</span><span class="sxs-lookup"><span data-stu-id="982e2-240">Generates a new test case, derived from the provided test case.</span></span> <span data-ttu-id="982e2-241">Vous pouvez utiliser la commande ``list`` pour obtenir tous les scénarios de test disponibles.</span><span class="sxs-lookup"><span data-stu-id="982e2-241">You can use the ``list`` command to get all available test cases.</span></span> <span data-ttu-id="982e2-242">Utilisez n’importe quelle valeur de la première colonne comme paramètre **test_case_id**.</span><span class="sxs-lookup"><span data-stu-id="982e2-242">Use any value from the first column as a **test_case_id** parameter.</span></span>

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``generatederived``**``[parent_test_case_id] [test_plan_id] [test_suite_id]``

##### <a name="required-parameters"></a><span data-ttu-id="982e2-243">Paramètres obligatoires</span><span class="sxs-lookup"><span data-stu-id="982e2-243">Required parameters</span></span>
<span data-ttu-id="982e2-244">**``parent_test_case_id``** Représente l’ID du scénario de test parent.</span><span class="sxs-lookup"><span data-stu-id="982e2-244">**``parent_test_case_id``** Represents the parent test case ID.</span></span>  
<span data-ttu-id="982e2-245">**``test_plan_id``** Représente l’ID du plan de test.</span><span class="sxs-lookup"><span data-stu-id="982e2-245">**``test_plan_id``** Represents the test plan ID.</span></span>  
<span data-ttu-id="982e2-246">**``test_suite_id``** Représente l’ID de la suite de tests.</span><span class="sxs-lookup"><span data-stu-id="982e2-246">**``test_suite_id``** Represents the test suite ID.</span></span>

##### <a name="examples"></a><span data-ttu-id="982e2-247">Exemples</span><span class="sxs-lookup"><span data-stu-id="982e2-247">Examples</span></span>
``generatederived 123 8901 678``


#### <a name="generatetestonly"></a><span data-ttu-id="982e2-248">generatetestonly</span><span class="sxs-lookup"><span data-stu-id="982e2-248">generatetestonly</span></span>
<span data-ttu-id="982e2-249">Génère uniquement le fichier d’exécution de tests pour le scénario de test spécifié dans le répertoire de sortie.</span><span class="sxs-lookup"><span data-stu-id="982e2-249">Generates only test execution file for the specified test case in the output directory.</span></span> <span data-ttu-id="982e2-250">Vous pouvez utiliser la commande ``list`` pour obtenir tous les scénarios de test disponibles.</span><span class="sxs-lookup"><span data-stu-id="982e2-250">You can use the ``list`` command to get all available test cases.</span></span> <span data-ttu-id="982e2-251">Utilisez n’importe quelle valeur de la première colonne comme paramètre **test_case_id**.</span><span class="sxs-lookup"><span data-stu-id="982e2-251">Use any value from the first column as a **test_case_id** parameter.</span></span>

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``generatetestonly``**``[test_case_id] [output_dir]``

##### <a name="required-parameters"></a><span data-ttu-id="982e2-252">Paramètres obligatoires</span><span class="sxs-lookup"><span data-stu-id="982e2-252">Required parameters</span></span>
<span data-ttu-id="982e2-253">**``test_case_id``** Représente l’ID du scénario de test.</span><span class="sxs-lookup"><span data-stu-id="982e2-253">**``test_case_id``** Represents the test case ID.</span></span>  
<span data-ttu-id="982e2-254">**``output_dir``** Représente le répertoire de sortie.</span><span class="sxs-lookup"><span data-stu-id="982e2-254">**``output_dir``** Represents the output directory.</span></span> <span data-ttu-id="982e2-255">Le répertoire doit exister.</span><span class="sxs-lookup"><span data-stu-id="982e2-255">The directory must exist.</span></span>

##### <a name="examples"></a><span data-ttu-id="982e2-256">Exemples</span><span class="sxs-lookup"><span data-stu-id="982e2-256">Examples</span></span>
``generatetestonly 123 c:\temp\rsat``  
``generatetestonly 765 c:\rsat\last``


#### <a name="generatetestsuite"></a><span data-ttu-id="982e2-257">generatetestsuite</span><span class="sxs-lookup"><span data-stu-id="982e2-257">generatetestsuite</span></span>
<span data-ttu-id="982e2-258">Génère tous les scénarios de test pour la suite spécifiée dans le répertoire de sortie.</span><span class="sxs-lookup"><span data-stu-id="982e2-258">Generates all test cases for the specified suite in the output directory.</span></span>
<span data-ttu-id="982e2-259">Vous pouvez utiliser la commande ``listtestsuitenames`` pour obtenir toutes les suites de test disponibles.</span><span class="sxs-lookup"><span data-stu-id="982e2-259">You can use ``listtestsuitenames`` command to get all available test suits.</span></span> <span data-ttu-id="982e2-260">Utilisez n’importe quelle valeur de la colonne comme paramètre **test_suite_name**.</span><span class="sxs-lookup"><span data-stu-id="982e2-260">Use any value from the column as a **test_suite_name** parameter.</span></span>

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``generatetestsuite``**``[test_suite_name] [output_dir]``

##### <a name="required-parameters"></a><span data-ttu-id="982e2-261">Paramètres obligatoires</span><span class="sxs-lookup"><span data-stu-id="982e2-261">Required parameters</span></span>
<span data-ttu-id="982e2-262">**``test_suite_name``** Représente le nom de la suite de tests.</span><span class="sxs-lookup"><span data-stu-id="982e2-262">**``test_suite_name``** Represents the test suite name.</span></span>  
<span data-ttu-id="982e2-263">**``output_dir``** Représente le répertoire de sortie.</span><span class="sxs-lookup"><span data-stu-id="982e2-263">**``output_dir``** Represents the output directory.</span></span> <span data-ttu-id="982e2-264">Le répertoire doit exister.</span><span class="sxs-lookup"><span data-stu-id="982e2-264">The directory must exist.</span></span>

##### <a name="examples"></a><span data-ttu-id="982e2-265">Exemples</span><span class="sxs-lookup"><span data-stu-id="982e2-265">Examples</span></span>
``generatetestsuite Tests c:\temp\rsat``   
``generatetestsuite Purchase c:\rsat\last``


#### <a name="help"></a><span data-ttu-id="982e2-266">help</span><span class="sxs-lookup"><span data-stu-id="982e2-266">help</span></span>
<span data-ttu-id="982e2-267">Identique à la commande [?](#section)</span><span class="sxs-lookup"><span data-stu-id="982e2-267">Identical to the [?](#section)</span></span> <span data-ttu-id="982e2-268">.</span><span class="sxs-lookup"><span data-stu-id="982e2-268">command</span></span>


#### <a name="list"></a><span data-ttu-id="982e2-269">liste</span><span class="sxs-lookup"><span data-stu-id="982e2-269">list</span></span>
<span data-ttu-id="982e2-270">Répertorie tous les scénarios de test disponibles.</span><span class="sxs-lookup"><span data-stu-id="982e2-270">Lists all available test cases.</span></span>

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``list``**


#### <a name="listtestplans"></a><span data-ttu-id="982e2-271">listtestplans</span><span class="sxs-lookup"><span data-stu-id="982e2-271">listtestplans</span></span>
<span data-ttu-id="982e2-272">Répertorie tous les plans de test disponibles.</span><span class="sxs-lookup"><span data-stu-id="982e2-272">Lists all available test plans.</span></span>

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``listtestplans``**


#### <a name="listtestsuite"></a><span data-ttu-id="982e2-273">listtestsuite</span><span class="sxs-lookup"><span data-stu-id="982e2-273">listtestsuite</span></span>
<span data-ttu-id="982e2-274">Répertorie les scénarios de test pour la suite de tests spécifiée.</span><span class="sxs-lookup"><span data-stu-id="982e2-274">Lists test cases for the specified test suite.</span></span> <span data-ttu-id="982e2-275">Vous pouvez utiliser la commande ``listtestsuitenames`` pour obtenir toutes les suites de test disponibles.</span><span class="sxs-lookup"><span data-stu-id="982e2-275">You can use ``listtestsuitenames`` command to get all available test suites.</span></span> <span data-ttu-id="982e2-276">Utilisez n’importe quelle valeur de la première colonne comme paramètre **suite_name**.</span><span class="sxs-lookup"><span data-stu-id="982e2-276">Use any value from first column as **suite_name** parameter.</span></span>

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``listtestsuite``**``[suite_name]``

##### <a name="required-parameters"></a><span data-ttu-id="982e2-277">Paramètres obligatoires</span><span class="sxs-lookup"><span data-stu-id="982e2-277">Required parameters</span></span>
<span data-ttu-id="982e2-278">**``suite_name``** Nom de la suite souhaitée.</span><span class="sxs-lookup"><span data-stu-id="982e2-278">**``suite_name``** Name of the desired suite.</span></span>

##### <a name="examples"></a><span data-ttu-id="982e2-279">Exemples</span><span class="sxs-lookup"><span data-stu-id="982e2-279">Examples</span></span>
``listtestsuite "sample suite name"``  
``listtestsuite NameOfTheSuite``


#### <a name="listtestsuitenames"></a><span data-ttu-id="982e2-280">listtestsuitenames</span><span class="sxs-lookup"><span data-stu-id="982e2-280">listtestsuitenames</span></span>
<span data-ttu-id="982e2-281">Répertorie toutes les suites de test disponibles.</span><span class="sxs-lookup"><span data-stu-id="982e2-281">Lists all available test suites.</span></span>

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``listtestsuitenames``**


#### <a name="playback"></a><span data-ttu-id="982e2-282">playback</span><span class="sxs-lookup"><span data-stu-id="982e2-282">playback</span></span>
<span data-ttu-id="982e2-283">Lit un scénario de test à l’aide d’un fichier Excel.</span><span class="sxs-lookup"><span data-stu-id="982e2-283">Plays back a test case using an Excel file.</span></span>

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``playback``**``[excel_file]``

##### <a name="required-parameters"></a><span data-ttu-id="982e2-284">Paramètres obligatoires</span><span class="sxs-lookup"><span data-stu-id="982e2-284">Required parameters</span></span>
<span data-ttu-id="982e2-285">**``excel_file``** Chemin d’accès complet au fichier Excel.</span><span class="sxs-lookup"><span data-stu-id="982e2-285">**``excel_file``** A full path to the Excel file.</span></span> <span data-ttu-id="982e2-286">Le fichier doit exister.</span><span class="sxs-lookup"><span data-stu-id="982e2-286">File must exist.</span></span> 

##### <a name="examples"></a><span data-ttu-id="982e2-287">Exemples</span><span class="sxs-lookup"><span data-stu-id="982e2-287">Examples</span></span>
``
playback c:\RSAT\TestCaseParameters\sample1.xlsx
playback e:\temp\test.xlsx
``


#### <a name="playbackbyid"></a><span data-ttu-id="982e2-288">playbackbyid</span><span class="sxs-lookup"><span data-stu-id="982e2-288">playbackbyid</span></span>
<span data-ttu-id="982e2-289">Lit plusieurs scénarios de test à la fois.</span><span class="sxs-lookup"><span data-stu-id="982e2-289">Plays back multiple test cases at once.</span></span>
<span data-ttu-id="982e2-290">Vous pouvez utiliser la commande ``list`` pour obtenir tous les scénarios de test disponibles.</span><span class="sxs-lookup"><span data-stu-id="982e2-290">You can use the ``list`` command to get all available test cases.</span></span> <span data-ttu-id="982e2-291">Utilisez n’importe quelle valeur de la première colonne comme paramètre **test_case_id**.</span><span class="sxs-lookup"><span data-stu-id="982e2-291">Use any value from the first column as a **test_case_id** parameter.</span></span>

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``playbackbyid``**``[test_case_id1] [test_case_id2] ... [test_case_idN]``

##### <a name="required-parameters"></a><span data-ttu-id="982e2-292">Paramètres obligatoires</span><span class="sxs-lookup"><span data-stu-id="982e2-292">Required parameters</span></span>
<span data-ttu-id="982e2-293">**``test_case_id1``** ID du scénario de test existant.</span><span class="sxs-lookup"><span data-stu-id="982e2-293">**``test_case_id1``** ID of exisiting test case.</span></span>  
<span data-ttu-id="982e2-294">**``test_case_id2``** ID du scénario de test existant.</span><span class="sxs-lookup"><span data-stu-id="982e2-294">**``test_case_id2``** ID of exisiting test case.</span></span>  
<span data-ttu-id="982e2-295">**``test_case_idN``** ID du scénario de test existant.</span><span class="sxs-lookup"><span data-stu-id="982e2-295">**``test_case_idN``** ID of exisiting test case.</span></span>  

##### <a name="examples"></a><span data-ttu-id="982e2-296">Exemples</span><span class="sxs-lookup"><span data-stu-id="982e2-296">Examples</span></span>
``playbackbyid 878``  
``playbackbyid 2345 667 135``


#### <a name="playbackmany"></a><span data-ttu-id="982e2-297">playbackmany</span><span class="sxs-lookup"><span data-stu-id="982e2-297">playbackmany</span></span>
<span data-ttu-id="982e2-298">Lit plusieurs scénarios de test à la fois, à l’aide de fichiers Excel.</span><span class="sxs-lookup"><span data-stu-id="982e2-298">Plays back many test cases at once, using Excel files.</span></span>

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``playbackmany``**``[excel_file1] [excel_file2] ... [excel_fileN]``

##### <a name="required-parameters"></a><span data-ttu-id="982e2-299">Paramètres obligatoires</span><span class="sxs-lookup"><span data-stu-id="982e2-299">Required parameters</span></span>
<span data-ttu-id="982e2-300">**``excel_file1``** Chemin d’accès complet au fichier Excel.</span><span class="sxs-lookup"><span data-stu-id="982e2-300">**``excel_file1``** Full path to the Excel file.</span></span> <span data-ttu-id="982e2-301">Le fichier doit exister.</span><span class="sxs-lookup"><span data-stu-id="982e2-301">File must exist.</span></span>  
<span data-ttu-id="982e2-302">**``excel_file2``** Chemin d’accès complet au fichier Excel.</span><span class="sxs-lookup"><span data-stu-id="982e2-302">**``excel_file2``** Full path to the Excel file.</span></span> <span data-ttu-id="982e2-303">Le fichier doit exister.</span><span class="sxs-lookup"><span data-stu-id="982e2-303">File must exist.</span></span>  
<span data-ttu-id="982e2-304">**``excel_fileN``** Chemin d’accès complet au fichier Excel.</span><span class="sxs-lookup"><span data-stu-id="982e2-304">**``excel_fileN``** Full path to the Excel file.</span></span> <span data-ttu-id="982e2-305">Le fichier doit exister.</span><span class="sxs-lookup"><span data-stu-id="982e2-305">File must exist.</span></span>  

##### <a name="examples"></a><span data-ttu-id="982e2-306">Exemples</span><span class="sxs-lookup"><span data-stu-id="982e2-306">Examples</span></span>
``playbackmany c:\RSAT\TestCaseParameters\param1.xlsx``  
``playbackmany e:\temp\test.xlsx f:\rsat\sample1.xlsx c:\RSAT\sample2.xlsx``


#### <a name="playbacksuite"></a><span data-ttu-id="982e2-307">playbacksuite</span><span class="sxs-lookup"><span data-stu-id="982e2-307">playbacksuite</span></span>
<span data-ttu-id="982e2-308">Lit tous les scénarios de test à partir de la suite de tests spécifiée.</span><span class="sxs-lookup"><span data-stu-id="982e2-308">Plays back all test cases from the specified test suite.</span></span> <span data-ttu-id="982e2-309">Vous pouvez utiliser la commande ``listtestsuitenames`` pour obtenir toutes les suites de test disponibles.</span><span class="sxs-lookup"><span data-stu-id="982e2-309">You can use ``listtestsuitenames`` command to get all available test suites.</span></span> <span data-ttu-id="982e2-310">Utilisez n’importe quelle valeur de la première colonne comme paramètre **suite_name**.</span><span class="sxs-lookup"><span data-stu-id="982e2-310">Use any value from first column as **suite_name** parameter.</span></span>

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``playbacksuite``**``[suite_name]``

##### <a name="required-parameters"></a><span data-ttu-id="982e2-311">Paramètres obligatoires</span><span class="sxs-lookup"><span data-stu-id="982e2-311">Required parameters</span></span>
<span data-ttu-id="982e2-312">**``suite_name``** Nom de la suite souhaitée.</span><span class="sxs-lookup"><span data-stu-id="982e2-312">**``suite_name``** Name of the desired suite.</span></span>

##### <a name="examples"></a><span data-ttu-id="982e2-313">Exemples</span><span class="sxs-lookup"><span data-stu-id="982e2-313">Examples</span></span>
``playbacksuite suiteName``  
``playbacksuite sample_suite``


#### <a name="quit"></a><span data-ttu-id="982e2-314">quit</span><span class="sxs-lookup"><span data-stu-id="982e2-314">quit</span></span>
<span data-ttu-id="982e2-315">Ferme l’application.</span><span class="sxs-lookup"><span data-stu-id="982e2-315">Closes the  application.</span></span>

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``quit``**


#### <a name="upload"></a><span data-ttu-id="982e2-316">upload</span><span class="sxs-lookup"><span data-stu-id="982e2-316">upload</span></span>
<span data-ttu-id="982e2-317">Charge tous les fichiers appartenant à la suite de tests ou aux scénarios de test spécifiés.</span><span class="sxs-lookup"><span data-stu-id="982e2-317">Uploads all files belonging to the specified test suite or test cases.</span></span>

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``upload``**``[suite_name] [testcase_id]``

#### <a name="required-parameters"></a><span data-ttu-id="982e2-318">Paramètres obligatoires</span><span class="sxs-lookup"><span data-stu-id="982e2-318">Required parameters</span></span>
<span data-ttu-id="982e2-319">**``suite_name``** Tous les fichiers appartenant à la suite de tests spécifiée seront chargés.</span><span class="sxs-lookup"><span data-stu-id="982e2-319">**``suite_name``** All files belonging to the specified test suite will be uploaded.</span></span>
<span data-ttu-id="982e2-320">**``testcase_id``** Tous les fichiers appartenant aux scénarios de test spécifiés seront chargés.</span><span class="sxs-lookup"><span data-stu-id="982e2-320">**``testcase_id``** All files beloning to the specified test case(s) will be uploaded.</span></span>

##### <a name="examples"></a><span data-ttu-id="982e2-321">Exemples</span><span class="sxs-lookup"><span data-stu-id="982e2-321">Examples</span></span>
``upload sample_suite``  
``upload 123``  
``upload 123 456``


#### <a name="uploadrecording"></a><span data-ttu-id="982e2-322">uploadrecording</span><span class="sxs-lookup"><span data-stu-id="982e2-322">uploadrecording</span></span>
<span data-ttu-id="982e2-323">Charge uniquement le fichier d’enregistrement appartenant aux scénarios de test spécifiés.</span><span class="sxs-lookup"><span data-stu-id="982e2-323">Uploads only recording file belonging to the specified test cases.</span></span>

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``uploadrecording``**``[testcase_id]``

##### <a name="required-parameters"></a><span data-ttu-id="982e2-324">Paramètres obligatoires</span><span class="sxs-lookup"><span data-stu-id="982e2-324">Required parameters</span></span>
<span data-ttu-id="982e2-325">**``testcase_id``** Le fichier d’enregistrement appartenant aux scénarios de test spécifiés sera chargé.</span><span class="sxs-lookup"><span data-stu-id="982e2-325">**``testcase_id``** Recording file belonging to the specified test cases will be uploaded.</span></span>

##### <a name="examples"></a><span data-ttu-id="982e2-326">Exemples</span><span class="sxs-lookup"><span data-stu-id="982e2-326">Examples</span></span>
``uploadrecording 123``  
``uploadrecording 123 456``


#### <a name="usage"></a><span data-ttu-id="982e2-327">usage</span><span class="sxs-lookup"><span data-stu-id="982e2-327">usage</span></span>
<span data-ttu-id="982e2-328">Affiche deux façons d’appeler cette application : l’une en utilisant un fichier de paramètre par défaut, l’autre en fournissant un fichier de paramètre.</span><span class="sxs-lookup"><span data-stu-id="982e2-328">Shows two ways to invoke this application: one using a default setting file, another one providing a setting file.</span></span>

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``usage``**


### <a name="windows-powershell-examples"></a><span data-ttu-id="982e2-329">Exemples Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="982e2-329">Windows PowerShell examples</span></span>

[!IMPORTANT] <span data-ttu-id="982e2-330">Les exemples de scripts ci-dessous sont fournis TELS QUELS à des fins d’illustration et ne sont pas pris en charge par Microsoft.</span><span class="sxs-lookup"><span data-stu-id="982e2-330">The example scripts below are provided AS IS for illustration purposes and are not supported by Microsoft.</span></span>

#### <a name="run-a-test-case-in-a-loop"></a><span data-ttu-id="982e2-331">Exécuter un scénario de test dans une boucle</span><span class="sxs-lookup"><span data-stu-id="982e2-331">Run a test case in a loop</span></span>

<span data-ttu-id="982e2-332">Vous avez un script de test qui crée un nouveau client.</span><span class="sxs-lookup"><span data-stu-id="982e2-332">You have a test script that creates a new customer.</span></span> <span data-ttu-id="982e2-333">Grâce à l’écriture de script, ce scénario de test peut être exécuté en boucle en rendant aléatoires les données suivantes avant chaque itération de l’exécution :</span><span class="sxs-lookup"><span data-stu-id="982e2-333">Via scripting, this test case can be run in a loop by randomizing the following data before each iteration is run:</span></span>

- <span data-ttu-id="982e2-334">ID client</span><span class="sxs-lookup"><span data-stu-id="982e2-334">Customer ID</span></span>
- <span data-ttu-id="982e2-335">Nom du client</span><span class="sxs-lookup"><span data-stu-id="982e2-335">Customer name</span></span>
- <span data-ttu-id="982e2-336">Adresse du client</span><span class="sxs-lookup"><span data-stu-id="982e2-336">Customer address</span></span>

<span data-ttu-id="982e2-337">L’ID client est au format *ATCUS\<number\>*, où \<number\> est une valeur comprise entre **000000001** et **999999999**.</span><span class="sxs-lookup"><span data-stu-id="982e2-337">The customer ID will be in the format *ATCUS\<number\>*, where \<number\> is a value between **000000001** and **999999999**.</span></span>

<span data-ttu-id="982e2-338">L’exemple suivant utilise un paramètre, **début**, pour définir le premier numéro utilisé.</span><span class="sxs-lookup"><span data-stu-id="982e2-338">The following example uses one parameter, **start**, to define the first number that is used.</span></span> <span data-ttu-id="982e2-339">Il utilise un deuxième paramètre, **nr**, pour définir le nombre de clients à créer.</span><span class="sxs-lookup"><span data-stu-id="982e2-339">Is uses a second parameter, **nr**, to define the number of customers that must be created.</span></span> <span data-ttu-id="982e2-340">Pour chaque itération, les paramètres du fichier de paramètres Excel sont modifiés à l’aide d’une fonction UpdateCustomer.</span><span class="sxs-lookup"><span data-stu-id="982e2-340">For each iteration, the parameters in the Excel parameter file are changed by using an UpdateCustomer function.</span></span> <span data-ttu-id="982e2-341">Ensuite, la ligne de commande RSAT est appelée dans une fonction RunTestCase.</span><span class="sxs-lookup"><span data-stu-id="982e2-341">Then the RSAT command line is called in a RunTestCase function.</span></span>

<span data-ttu-id="982e2-342">Ouvrez l’environnement ISE ( PowerShell Integrated Scripting) de Microsoft Windows en mode administrateur, et collez le code suivant dans la fenêtre qui s’appelle **Untitled1.ps1**.</span><span class="sxs-lookup"><span data-stu-id="982e2-342">Open Microsoft Windows PowerShell Integrated Scripting Environment (ISE) in admin mode, and paste the following code into the window that is named **Untitled1.ps1**.</span></span>

```powershell
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
$excelFilename = "full path to Excel parameter file"
l$sheetName = "DirPartyQuickCreateForm"
for ($i = $start; $i -lt $start + $nr; $i++ )
{
    $CustomerId = $i.ToString("000000000")
    Write-Host "customer : " $CustomerId
    UpdateCustomer $excelFilename $sheetName $CustomerId
    RunTestCase $excelFilename
```

#### <a name="run-a-script-that-depends-on-data-in-microsoft-dynamics-365"></a><span data-ttu-id="982e2-343">Exécuter un script qui dépend de données de Microsoft Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="982e2-343">Run a script that depends on data in Microsoft Dynamics 365</span></span>

<span data-ttu-id="982e2-344">L’exemple suivant utilise un appel OData (Open Data Protocol) pour rechercher le statut d’une commande fournisseur.</span><span class="sxs-lookup"><span data-stu-id="982e2-344">The following example uses an Open Data Protocol (OData) call to find the order status of a purchase order.</span></span> <span data-ttu-id="982e2-345">Si le statut n’est pas **facturé**, vous pouvez, par exemple, appeler un scénario de test RSAT qui valide la facture.</span><span class="sxs-lookup"><span data-stu-id="982e2-345">If the status isn't **invoiced**, you can, for example, call an RSAT test case that posts the invoice.</span></span>

```xpp
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
