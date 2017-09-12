---
title: "Organiser les composants d'état dans le concepteur d'état"
description: "Après la création des blocs élémentaires et des états générés, il est utile d’organiser ces objets afin qu’ils soient plus faciles à localiser. Cet article explique comment organiser les états, les blocs élémentaires et les objets existants dans le générateur d'états."
author: ShylaThompson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
ms.search.form: FinancialReports
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Management Reporter, UnifiedOperations, Core
ms.custom: 59161
ms.assetid: 32e728c5-3b06-4049-8070-ade01e951d49
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: Human Translation
ms.sourcegitcommit: 08c38aada355583c5a6872f75b57db95d9b81786
ms.openlocfilehash: fade9e2acdb94daa6a908d949c578fd7ed439882
ms.contentlocale: fr-fr
ms.lasthandoff: 07/18/2017

---

# <a name="organize-report-components-in-report-designer"></a><span data-ttu-id="2d602-104">Organiser les composants d'état dans le concepteur d'état</span><span class="sxs-lookup"><span data-stu-id="2d602-104">Organize report components in report designer</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="2d602-105">Après la création des blocs élémentaires et des états générés, il est utile d’organiser ces objets afin qu’ils soient plus faciles à localiser.</span><span class="sxs-lookup"><span data-stu-id="2d602-105">After you've designed building blocks and generated reports, it's helpful to organize these objects so that they are easier for users to locate.</span></span> <span data-ttu-id="2d602-106">Cet article explique comment organiser les états, les blocs élémentaires et les objets existants dans le générateur d'états.</span><span class="sxs-lookup"><span data-stu-id="2d602-106">This article explains how to organize existing reports, building blocks, and objects in report designer.</span></span>

<span data-ttu-id="2d602-107">Vous pouvez renommer des dossiers, des états, des blocs élémentaires, ainsi que d'autres objets dans le concepteur d'état pour aider à organiser vos fichiers.</span><span class="sxs-lookup"><span data-stu-id="2d602-107">You can rename folders, reports, building blocks, and other objects in report designer to help organize your files.</span></span> <span data-ttu-id="2d602-108">Selon le type d'objet que vous renommez, vous devrez peut-être mettre à jour des associations avec cet objet.</span><span class="sxs-lookup"><span data-stu-id="2d602-108">Depending on the type of object that you rename, you might have to update associations with that object.</span></span>

## <a name="rename-a-folder-or-building-block-in-report-designer"></a><span data-ttu-id="2d602-109">Renommer un dossier ou un bloc élémentaire dans Report Designer</span><span class="sxs-lookup"><span data-stu-id="2d602-109">Rename a folder or building block in Report Designer</span></span>
<span data-ttu-id="2d602-110">Dans Report Designer, vous pouvez renommer des fichiers, des définitions d'état, des définitions de ligne, des définitions de colonne et des définitions d'arborescence de génération d'états.</span><span class="sxs-lookup"><span data-stu-id="2d602-110">In Report Designer, you can rename folders, report definitions, row definitions, column definitions, and reporting tree definitions.</span></span> <span data-ttu-id="2d602-111">**Remarque :** lorsque vous renommez un bloc élémentaire, vous devez mettre à jour toutes les définitions d'état qui utilisent le bloc élémentaire.</span><span class="sxs-lookup"><span data-stu-id="2d602-111">**Note:** When you rename a building block, you must update any reporting definitions that use the building block.</span></span> <span data-ttu-id="2d602-112">Sinon, aucun nouvel état ne peut être généré.</span><span class="sxs-lookup"><span data-stu-id="2d602-112">Otherwise, a new report can't be generated.</span></span>

### <a name="rename-a-folder-or-building-block-in-report-designer"></a><span data-ttu-id="2d602-113">Renommer un dossier ou un bloc élémentaire dans Report Designer</span><span class="sxs-lookup"><span data-stu-id="2d602-113">Rename a folder or building block in Report Designer</span></span>

1.  <span data-ttu-id="2d602-114">Dans Report Designer, utilisez le volet de navigation pour rechercher le dossier ou l'objet à renommer.</span><span class="sxs-lookup"><span data-stu-id="2d602-114">In Report Designer, use the navigation pane to locate the folder or object to rename.</span></span>
2.  <span data-ttu-id="2d602-115">Cliquez avec le bouton droit sur le dossier ou l'objet, puis cliquez sur **Renommer**.</span><span class="sxs-lookup"><span data-stu-id="2d602-115">Right-click the folder or object, and then click **Rename**.</span></span> <span data-ttu-id="2d602-116">Le champ **Nom** dans le volet de navigation devient disponible.</span><span class="sxs-lookup"><span data-stu-id="2d602-116">The **Name** field in the navigation pane becomes available.</span></span>
3.  <span data-ttu-id="2d602-117">Entrez un nouveau nom, puis appuyez sur Entrer.</span><span class="sxs-lookup"><span data-stu-id="2d602-117">Type a new name, and then press Enter.</span></span>
4.  <span data-ttu-id="2d602-118">Si le bloc élémentaire est une définition de ligne, une définition de colonne, ou une définition d'arborescence de génération d'états, vous devez mettre à jour d'autres blocs élémentaires associés à lui.</span><span class="sxs-lookup"><span data-stu-id="2d602-118">If the building block is a row definition, column definition, or reporting tree definition, you must update other building blocks that are associated with it.</span></span> <span data-ttu-id="2d602-119">Cliquez avec le bouton droit sur le bloc élémentaire que vous avez renommé à l'étape 3, sélectionnez **Associations**, puis sélectionnez un article dans la liste pour le mettre à jour.</span><span class="sxs-lookup"><span data-stu-id="2d602-119">Right-click the building block that you renamed in step 3, select **Associations**, and then select an item in the list to update it.</span></span>
5.  <span data-ttu-id="2d602-120">Répétez l'étape 4 jusqu'à ce que tous les articles associés soient mis à jour.</span><span class="sxs-lookup"><span data-stu-id="2d602-120">Repeat step 4 until all associated items are updated.</span></span>

## <a name="create-and-manage-report-groups"></a><span data-ttu-id="2d602-121">Créer et gérer des groupes d'états</span><span class="sxs-lookup"><span data-stu-id="2d602-121">Create and manage report groups</span></span>
<span data-ttu-id="2d602-122">Vous pouvez regrouper les définitions d'état pour générer plusieurs états simultanément.</span><span class="sxs-lookup"><span data-stu-id="2d602-122">You can group report definitions to generate multiple reports at the same time.</span></span> <span data-ttu-id="2d602-123">Pour créer, modifier, supprimer, puis générer des groupes d'états, vous devez avoir le rôle de concepteur ou d'administrateur.</span><span class="sxs-lookup"><span data-stu-id="2d602-123">To create, modify, delete, and generate report groups, you must have the designer or administrator role.</span></span> <span data-ttu-id="2d602-124">Les utilisateurs ayant le rôle de générateur peuvent générer des groupes d'états et peuvent également modifier le paramètre des définitions d'état utilisateur pour des groupes d'états.</span><span class="sxs-lookup"><span data-stu-id="2d602-124">Users who have the generator role can generate report groups and can also modify the user report definitions setting for report groups.</span></span>

### <a name="create-a-report-group"></a><span data-ttu-id="2d602-125">Créer un groupe d'états</span><span class="sxs-lookup"><span data-stu-id="2d602-125">Create a report group</span></span>

1.  <span data-ttu-id="2d602-126">Dans le générateur d'états, dans le volet de navigation, cliquez sur **Groupes d'états** dans le volet de navigation.</span><span class="sxs-lookup"><span data-stu-id="2d602-126">In Report Designer, in the navigation pane, click **Report Groups**.</span></span>
2.  <span data-ttu-id="2d602-127">Dans le menu **Fichier**, cliquez sur **Nouveau** &gt; **Définition de groupe d'état** pour ouvrir un nouveau groupe d'état dans la fenêtre du visualiseur.</span><span class="sxs-lookup"><span data-stu-id="2d602-127">On the **File** menu, click **New** &gt; **Report Group Definition** to open a new report group in the viewer window.</span></span> <span data-ttu-id="2d602-128">Sinon, cliquez sur le bouton **Groupe d'états** ![Groupe d'états](https://i-technet.sec.s-msft.com/dynimg/IC679515.gif "Groupe d'états") sur la barre d’outils.</span><span class="sxs-lookup"><span data-stu-id="2d602-128">Alternatively, click the **Report Group** button ![Report Group](https://i-technet.sec.s-msft.com/dynimg/IC679515.gif "Report Group") on the toolbar.</span></span>
3.  <span data-ttu-id="2d602-129">Cliquez sur l'onglet **Groupe d'états**.</span><span class="sxs-lookup"><span data-stu-id="2d602-129">Click the **Report Group** tab.</span></span> <span data-ttu-id="2d602-130">Pour remplacer les informations sur les différentes définitions d'état pour la génération de cet état, activez la case à cocher **Remplacer les paramètres de la société, des détails et de date à partir des définitions d'état**.</span><span class="sxs-lookup"><span data-stu-id="2d602-130">To override the information on the individual report definitions for the generation of this report, select the **Override company, detail, and date settings from individual report definitions** check box.</span></span> <span data-ttu-id="2d602-131">Les informations sur le nom de la société, le niveau de détail, les paramètres provisionnels et la date sont fournis automatiquement mais vous pouvez toujours effectuer des mises à jour.</span><span class="sxs-lookup"><span data-stu-id="2d602-131">The company name, detail level, provisional setting, and date information are entered automatically, but you can make updates.</span></span>
4.  <span data-ttu-id="2d602-132">Pour générer plusieurs états affichant les devises de déclaration, activez la case à cocher **Inclure toutes les devises de déclaration**.</span><span class="sxs-lookup"><span data-stu-id="2d602-132">To generate multiple reports that show the reporting currencies, select the **Include all reporting currencies** check box.</span></span> <span data-ttu-id="2d602-133">Vous pouvez ensuite accéder à plusieurs en cliquant sur le bouton **Devise** dans la visionneuse Web lorsque vous afficherez l'état.</span><span class="sxs-lookup"><span data-stu-id="2d602-133">You can then access multiple views by clicking the **Currency** button in the Web Viewer when you view the report.</span></span>
5.  <span data-ttu-id="2d602-134">Dans le champ **États dans le groupe**, cliquez sur **Ajouter** pour sélectionner les états à inclure dans le groupe d'états.</span><span class="sxs-lookup"><span data-stu-id="2d602-134">In the **Reports in group** field, click **Add** to select the reports to include in the report group.</span></span> <span data-ttu-id="2d602-135">Pour sélectionner plusieurs états dans la boîte de dialogue **Ajouter**, maintenez la touche Ctrl enfoncée alors que vous sélectionnez des états.</span><span class="sxs-lookup"><span data-stu-id="2d602-135">To select multiple reports in the **Add** dialog box, hold down the Ctrl key while you select reports.</span></span> <span data-ttu-id="2d602-136">Lorsque vous avez terminé la sélection des états, cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="2d602-136">When you've finished selecting reports, click **OK**.</span></span>
6.  <span data-ttu-id="2d602-137">Cliquez sur **Fichier** &gt; **Enregistrer** pour enregistrer le nouveau groupe d'états.</span><span class="sxs-lookup"><span data-stu-id="2d602-137">Click **File** &gt; **Save** to save the new report group.</span></span>

### <a name="modify-a-report-group"></a><span data-ttu-id="2d602-138">Modifier un groupe d'états</span><span class="sxs-lookup"><span data-stu-id="2d602-138">Modify a report group</span></span>

1.  <span data-ttu-id="2d602-139">Dans le générateur d'états, dans le volet de navigation, cliquez sur **Groupes d'états** dans le volet de navigation.</span><span class="sxs-lookup"><span data-stu-id="2d602-139">In Report Designer, in the navigation pane, click **Report Groups**.</span></span>
2.  <span data-ttu-id="2d602-140">Double-cliquez sur le groupe d'états à modifier.</span><span class="sxs-lookup"><span data-stu-id="2d602-140">Double-click the report group to modify.</span></span>
3.  <span data-ttu-id="2d602-141">Sur l'onglet **Groupe d'états**, apportez les modifications que vous souhaitez.</span><span class="sxs-lookup"><span data-stu-id="2d602-141">On the **Report Group** tab, make the changes that you want.</span></span>
4.  <span data-ttu-id="2d602-142">Dans le menu **Fichier**, cliquez sur **Enregistrer** pour enregistrer le groupe d'états modifié ou sur le bouton **Enregistrer** ![Enregistrer](https://i-technet.sec.s-msft.com/dynimg/IC679516.gif "Enregistrer") dans la barre d'outils.</span><span class="sxs-lookup"><span data-stu-id="2d602-142">On the **File** menu, click **Save** to save the modified report group, Alternatively, click the **Save** button ![Save](https://i-technet.sec.s-msft.com/dynimg/IC679516.gif "Save") on the toolbar.</span></span>

<span data-ttu-id="2d602-143">**Remarque :** si vous avez planifié des états à générer à intervalles définis, vous pouvez remplacer ces paramètres et déclarer un état immédiatement.</span><span class="sxs-lookup"><span data-stu-id="2d602-143">**Note:** If you've scheduled reports so that they are generated at set intervals, you can override those settings and generate a report immediately.</span></span>

### <a name="generate-a-report-group-report"></a><span data-ttu-id="2d602-144">Générer un état du groupe d'états</span><span class="sxs-lookup"><span data-stu-id="2d602-144">Generate a report group report</span></span>

1.  <span data-ttu-id="2d602-145">Dans le générateur d'états, dans le volet de navigation, cliquez sur **Groupes d'états** dans le volet de navigation.</span><span class="sxs-lookup"><span data-stu-id="2d602-145">In Report Designer, in the navigation pane, click **Report Groups**.</span></span>
2.  <span data-ttu-id="2d602-146">Ouvrez le groupe d'états à générer.</span><span class="sxs-lookup"><span data-stu-id="2d602-146">Open the report group to generate.</span></span>
3.  <span data-ttu-id="2d602-147">Cliquez sur le bouton **Générer un état** ![Générer un état](https://i-technet.sec.s-msft.com/dynimg/IC679517.gif "Générer un état") pour générer des états.</span><span class="sxs-lookup"><span data-stu-id="2d602-147">Click the **Generate Report** button ![Generate Report](https://i-technet.sec.s-msft.com/dynimg/IC679517.gif "Generate Report") to generate reports.</span></span>

### <a name="delete-a-report-group"></a><span data-ttu-id="2d602-148">Supprimer un groupe d'états</span><span class="sxs-lookup"><span data-stu-id="2d602-148">Delete a report group</span></span>

1.  <span data-ttu-id="2d602-149">Dans le générateur d'états, dans le volet de navigation, cliquez sur **Groupes d'états** dans le volet de navigation.</span><span class="sxs-lookup"><span data-stu-id="2d602-149">In Report Designer, in the navigation pane, click **Report Groups**.</span></span>
2.  <span data-ttu-id="2d602-150">Cliquez avec le bouton droit sur le groupe d'états à supprimer, puis sélectionnez **Supprimer**.</span><span class="sxs-lookup"><span data-stu-id="2d602-150">Right-click the report group to delete, and then select **Delete**.</span></span>
3.  <span data-ttu-id="2d602-151">Lorsqu’un message de confirmation apparaît, cliquez sur **Oui**.</span><span class="sxs-lookup"><span data-stu-id="2d602-151">When a confirmation message appears, click **Yes**.</span></span>

## <a name="report-group-tab-controls"></a><span data-ttu-id="2d602-152">Contrôles de l'onglet Groupe d'états</span><span class="sxs-lookup"><span data-stu-id="2d602-152">Report Group tab controls</span></span>
<span data-ttu-id="2d602-153">Le tableau suivant décrit les contrôles l'onglet **Groupe d'états**.</span><span class="sxs-lookup"><span data-stu-id="2d602-153">The following table describes the controls on the **Report Group** tab.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="2d602-154">Contrôle</span><span class="sxs-lookup"><span data-stu-id="2d602-154">Control</span></span></th>
<th><span data-ttu-id="2d602-155">Description</span><span class="sxs-lookup"><span data-stu-id="2d602-155">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="2d602-156">Remplacer les paramètres de la société, des détails et de date à partir des définitions d'état</span><span class="sxs-lookup"><span data-stu-id="2d602-156">Override company, detail, and date settings from individual report definitions</span></span></td>
<td><span data-ttu-id="2d602-157">Activez cette case à cocher pour remplacer les définitions d'état individuelles des états dans ce groupe d'états pour la génération de ces états uniquement.</span><span class="sxs-lookup"><span data-stu-id="2d602-157">Select this check box to override individual report definitions of the reports in this report group for the generation of these reports only.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="2d602-158">Nom de la société</span><span class="sxs-lookup"><span data-stu-id="2d602-158">Company name</span></span></td>
<td><span data-ttu-id="2d602-159">Sélectionnez la société à utiliser pour les états.</span><span class="sxs-lookup"><span data-stu-id="2d602-159">Select the company to use for the reports.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="2d602-160">Niveau de détail</span><span class="sxs-lookup"><span data-stu-id="2d602-160">Detail level</span></span></td>
<td><span data-ttu-id="2d602-161">Permet de spécifier le niveau de détail souhaité dans l'état.</span><span class="sxs-lookup"><span data-stu-id="2d602-161">Specify the level of detail that the reports include.</span></span>
<ul>
<li><span data-ttu-id="2d602-162"><strong>Financier</strong> : Rapport de synthèse de haut niveau.</span><span class="sxs-lookup"><span data-stu-id="2d602-162"><strong>Financial</strong> − A high-level summary report.</span></span> <span data-ttu-id="2d602-163">Vous ne pouvez pas effectuer de zoom avant dans les comptes et les dimensions, à l'exception de ceux ajoutés via une arborescence de génération d'états.</span><span class="sxs-lookup"><span data-stu-id="2d602-163">You can't drill down to accounts and dimensions, except for those accounts and dimensions that have been added through a reporting tree.</span></span></li>
<li><span data-ttu-id="2d602-164"><strong>Financier &amp; Compte</strong> − État qui contient une synthèse de haut niveau et des détails du compte.</span><span class="sxs-lookup"><span data-stu-id="2d602-164"><strong>Financial &amp; Account</strong> − A report that contains a high-level summary and account details.</span></span></li>
<li><span data-ttu-id="2d602-165"><strong>Financier, Compte &amp; Transaction</strong> État qui contient une synthèse de haut niveau et des détails de la transaction.</span><span class="sxs-lookup"><span data-stu-id="2d602-165"><strong>Financial, Account, &amp; Transaction</strong> − A report that contains a high-level summary and transaction details.</span></span></li>
</ul></td>
</tr>
<tr class="even">
<td><span data-ttu-id="2d602-166">Provisionnel</span><span class="sxs-lookup"><span data-stu-id="2d602-166">Provisional</span></span></td>
<td><span data-ttu-id="2d602-167">Permet de spécifier les types d'activités souhaités dans l'état.</span><span class="sxs-lookup"><span data-stu-id="2d602-167">Specify the types of activity that the reports include.</span></span>
<ul>
<li><span data-ttu-id="2d602-168"><strong>Activités validées uniquement</strong> : Inclut uniquement les transactions et les soldes validés dans vos données financières.</span><span class="sxs-lookup"><span data-stu-id="2d602-168"><strong>Posted activity only</strong> − Include only the transactions and balances that are posted in your financial data.</span></span></li>
<li><span data-ttu-id="2d602-169"><strong>Activités validées et non validées</strong> : Inclut toutes les transactions et tous les soldes entrés et validés dans vos données financières.</span><span class="sxs-lookup"><span data-stu-id="2d602-169"><strong>Posted and unposted activity</strong> − Include all the transactions and balances that are entered and posted in your financial data.</span></span></li>
<li><span data-ttu-id="2d602-170"><strong>Activités non validées uniquement</strong> : Inclut uniquement les transactions entrées mais pas encore validées dans vos données financières.</span><span class="sxs-lookup"><span data-stu-id="2d602-170"><strong>Unposted activity only</strong> − Include only the transactions that are entered, but not yet posted, in your financial data.</span></span></li>
</ul></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="2d602-171">Inclure toutes les devises de déclaration</span><span class="sxs-lookup"><span data-stu-id="2d602-171">Include all reporting currencies</span></span></td>
<td><span data-ttu-id="2d602-172">Toutes les devises de déclaration supplémentaires configurées dans votre système Microsoft Dynamics ERP sont indiquées ici.</span><span class="sxs-lookup"><span data-stu-id="2d602-172">Any additional reporting currencies that are configured in your Microsoft Dynamics ERP system are listed here.</span></span> <span data-ttu-id="2d602-173">Activez cette case à cocher pour générer des états supplémentaires dans les devises indiquées.</span><span class="sxs-lookup"><span data-stu-id="2d602-173">Select this check box to generate additional reports in the currencies that are indicated.</span></span> <span data-ttu-id="2d602-174">Pour afficher ces états dans la visionneuse Web, cliquez sur le bouton <strong>Devise</strong>, puis sélectionnez une devise.</span><span class="sxs-lookup"><span data-stu-id="2d602-174">To view these reports in the Web Viewer, click the <strong>Currency</strong> button, and then select a currency.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="2d602-175">Informations de date non enregistrées avec la définition d'état</span><span class="sxs-lookup"><span data-stu-id="2d602-175">Date information not saved with report definition</span></span></td>
<td><ul>
<li><span data-ttu-id="2d602-176">Période de base</span><span class="sxs-lookup"><span data-stu-id="2d602-176">Base period</span></span></li>
<li><span data-ttu-id="2d602-177">Année de base</span><span class="sxs-lookup"><span data-stu-id="2d602-177">Base year</span></span></li>
<li><span data-ttu-id="2d602-178">Période couverte</span><span class="sxs-lookup"><span data-stu-id="2d602-178">Period covered</span></span></li>
</ul>
<span data-ttu-id="2d602-179">Seuls les paramètres de période de base par défaut sont enregistrés avec la définition d'état.</span><span class="sxs-lookup"><span data-stu-id="2d602-179">Only default base period settings are saved with the report definition.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="2d602-180">Informations de date enregistrées avec la définition d'état</span><span class="sxs-lookup"><span data-stu-id="2d602-180">Date information saved with report definition</span></span></td>
<td><ul>
<li><span data-ttu-id="2d602-181">Date de l'état</span><span class="sxs-lookup"><span data-stu-id="2d602-181">Report date</span></span></li>
<li><span data-ttu-id="2d602-182">Période de base par défaut</span><span class="sxs-lookup"><span data-stu-id="2d602-182">Default base period</span></span></li>
</ul></td>
</tr>
<tr class="even">
<td><span data-ttu-id="2d602-183">États dans le groupe</span><span class="sxs-lookup"><span data-stu-id="2d602-183">Reports in group</span></span></td>
<td><span data-ttu-id="2d602-184">Permet d'ajouter, de supprimer, et de trier à nouveau les états dans le groupe d'états.</span><span class="sxs-lookup"><span data-stu-id="2d602-184">Add, remove, and re-order reports in the report group.</span></span>
<ul>
<li><span data-ttu-id="2d602-185">Pour ajouter des définitions d'état au groupe d'état, double-cliquez sur le groupe d'état pour l'ouvrir, puis cliquez sur <strong>Ajouter</strong>.</span><span class="sxs-lookup"><span data-stu-id="2d602-185">To add report definitions to the report group, double-click the report group to open it, and then click <strong>Add</strong>.</span></span> <span data-ttu-id="2d602-186">Sélectionnez les rapports à inclure dans le groupe d'états, puis cliquez sur <strong>OK</strong>.</span><span class="sxs-lookup"><span data-stu-id="2d602-186">Select the reports to include in the report group, and then click <strong>OK</strong>.</span></span></li>
<li><span data-ttu-id="2d602-187">Pour supprimer un état du groupe d'états, sélectionnez-le et cliquez sur <strong>Supprimer</strong>.</span><span class="sxs-lookup"><span data-stu-id="2d602-187">To remove a report from the report group, select it, and then click <strong>Remove</strong>.</span></span></li>
<li><span data-ttu-id="2d602-188">Pour modifier l'ordre dans lequel les états sont générés, sélectionnez un état dans la liste, puis cliquez sur <strong>Déplacer vers le haut</strong> ou <strong>Déplacer vers le bas</strong>.</span><span class="sxs-lookup"><span data-stu-id="2d602-188">To modify the order that the reports are generated in, select a report in the list, and then click <strong>Move up</strong> or <strong>Move down</strong>.</span></span></li>
</ul></td>
</tr>
</tbody>
</table>



<a name="see-also"></a><span data-ttu-id="2d602-189">Voir également :</span><span class="sxs-lookup"><span data-stu-id="2d602-189">See also</span></span>
--------

[<span data-ttu-id="2d602-190">États financiers</span><span class="sxs-lookup"><span data-stu-id="2d602-190">Financial reporting</span></span>](financial-reporting-intro.md)




