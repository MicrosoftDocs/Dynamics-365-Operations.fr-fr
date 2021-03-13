---
title: Organiser les composants d’état dans le concepteur d’état
description: Cette rubrique explique comment organiser les états, les blocs élémentaires et les objets existants dans le générateur d’états.
author: ShylaThompson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: FinancialReports
audience: Application User
ms.reviewer: kfend
ms.custom: 59161
ms.assetid: 32e728c5-3b06-4049-8070-ade01e951d49
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 0b55dcee00f571228ec1e933306d77d9edc12866
ms.sourcegitcommit: 5192cfaedfd861faea63d8954d7bcc500608a225
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/30/2021
ms.locfileid: "5092421"
---
# <a name="organize-report-components-in-report-designer"></a><span data-ttu-id="74684-103">Organiser les composants d’état dans le concepteur d’état</span><span class="sxs-lookup"><span data-stu-id="74684-103">Organize report components in report designer</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="74684-104">Après la création des blocs élémentaires et des états générés, il est utile d’organiser ces objets afin qu’ils soient plus faciles à localiser.</span><span class="sxs-lookup"><span data-stu-id="74684-104">After you've designed building blocks and generated reports, it's helpful to organize these objects so that they are easier for users to locate.</span></span> <span data-ttu-id="74684-105">Cet article explique comment organiser les états, les blocs élémentaires et les objets existants dans le générateur d’états.</span><span class="sxs-lookup"><span data-stu-id="74684-105">This article explains how to organize existing reports, building blocks, and objects in report designer.</span></span>

<span data-ttu-id="74684-106">Vous pouvez renommer des dossiers, des états, des blocs élémentaires, ainsi que d’autres objets dans le concepteur d’état pour aider à organiser vos fichiers.</span><span class="sxs-lookup"><span data-stu-id="74684-106">You can rename folders, reports, building blocks, and other objects in report designer to help organize your files.</span></span> <span data-ttu-id="74684-107">Selon le type d’objet que vous renommez, vous devrez peut-être mettre à jour des associations avec cet objet.</span><span class="sxs-lookup"><span data-stu-id="74684-107">Depending on the type of object that you rename, you might have to update associations with that object.</span></span>

## <a name="rename-a-folder-or-building-block-in-report-designer"></a><span data-ttu-id="74684-108">Renommer un dossier ou un bloc élémentaire dans Report Designer</span><span class="sxs-lookup"><span data-stu-id="74684-108">Rename a folder or building block in Report Designer</span></span>
<span data-ttu-id="74684-109">Dans le Concepteur de rapports, vous pouvez renommer des dossiers, des définitions de rapport, des définitions de ligne, des définitions de colonne et des définitions d’organigramme d’entreprise.</span><span class="sxs-lookup"><span data-stu-id="74684-109">In Report Designer, you can rename folders, report definitions, row definitions, column definitions, and reporting tree definitions.</span></span>

### <a name="rename-a-folder-or-building-block-in-report-designer"></a><span data-ttu-id="74684-110">Attribution d’un nouveau nom à un dossier ou à un bloc élémentaire dans le Concepteur de rapports</span><span class="sxs-lookup"><span data-stu-id="74684-110">Rename a folder or building block in Report Designer</span></span>

1. <span data-ttu-id="74684-111">Dans le Concepteur de rapports, utilisez le volet de navigation pour localiser le dossier ou l’objet à renommer.</span><span class="sxs-lookup"><span data-stu-id="74684-111">In Report Designer, use the navigation pane to locate the folder or object to rename.</span></span>
2. <span data-ttu-id="74684-112">Cliquez avec le bouton droit sur le dossier ou l’objet, puis cliquez sur **Renommer**.</span><span class="sxs-lookup"><span data-stu-id="74684-112">Right-click the folder or object, and then click **Rename**.</span></span> <span data-ttu-id="74684-113">Le champ **Nom** dans le volet de navigation devient disponible.</span><span class="sxs-lookup"><span data-stu-id="74684-113">The **Name** field in the navigation pane becomes available.</span></span>
3. <span data-ttu-id="74684-114">Entrez un nouveau nom, puis appuyez sur Entrer.</span><span class="sxs-lookup"><span data-stu-id="74684-114">Type a new name, and then press Enter.</span></span>
4. <span data-ttu-id="74684-115">Si le bloc élémentaire est une définition de ligne, une définition de colonne, ou une définition d’arborescence de génération d’états, vous devez mettre à jour d’autres blocs élémentaires associés à lui.</span><span class="sxs-lookup"><span data-stu-id="74684-115">If the building block is a row definition, column definition, or reporting tree definition, you must update other building blocks that are associated with it.</span></span> <span data-ttu-id="74684-116">Cliquez avec le bouton droit sur le bloc élémentaire que vous avez renommé à l’étape 3, sélectionnez **Associations**, puis sélectionnez un article dans la liste pour le mettre à jour.</span><span class="sxs-lookup"><span data-stu-id="74684-116">Right-click the building block that you renamed in step 3, select **Associations**, and then select an item in the list to update it.</span></span>
5. <span data-ttu-id="74684-117">Répétez l’étape 4 jusqu’à ce que tous les articles associés soient mis à jour.</span><span class="sxs-lookup"><span data-stu-id="74684-117">Repeat step 4 until all associated items are updated.</span></span>

## <a name="create-and-manage-report-groups"></a><span data-ttu-id="74684-118">Créer et gérer des groupes d’états</span><span class="sxs-lookup"><span data-stu-id="74684-118">Create and manage report groups</span></span>
<span data-ttu-id="74684-119">Vous pouvez regrouper les définitions d’état pour générer plusieurs états simultanément.</span><span class="sxs-lookup"><span data-stu-id="74684-119">You can group report definitions to generate multiple reports at the same time.</span></span> <span data-ttu-id="74684-120">Pour créer, modifier, supprimer, puis générer des groupes d’états, vous devez avoir le rôle de concepteur ou d’administrateur.</span><span class="sxs-lookup"><span data-stu-id="74684-120">To create, modify, delete, and generate report groups, you must have the designer or administrator role.</span></span> <span data-ttu-id="74684-121">Les utilisateurs ayant le rôle de générateur peuvent générer des groupes d’états et peuvent également modifier le paramètre des définitions d’état utilisateur pour des groupes d’états.</span><span class="sxs-lookup"><span data-stu-id="74684-121">Users who have the generator role can generate report groups and can also modify the user report definitions setting for report groups.</span></span>

### <a name="create-a-report-group"></a><span data-ttu-id="74684-122">Créer un groupe d’états</span><span class="sxs-lookup"><span data-stu-id="74684-122">Create a report group</span></span>

1. <span data-ttu-id="74684-123">Dans le générateur d’états, dans le volet de navigation, cliquez sur **Groupes d’états** dans le volet de navigation.</span><span class="sxs-lookup"><span data-stu-id="74684-123">In Report Designer, in the navigation pane, click **Report Groups**.</span></span>
2. <span data-ttu-id="74684-124">Dans le menu **Fichier**, cliquez sur **Nouveau** &gt; **Définition de groupe d’état** pour ouvrir un nouveau groupe d’état dans la fenêtre du visualiseur.</span><span class="sxs-lookup"><span data-stu-id="74684-124">On the **File** menu, click **New** &gt; **Report Group Definition** to open a new report group in the viewer window.</span></span> <span data-ttu-id="74684-125">Sinon, cliquez sur le bouton **Groupe d’états** ![Groupe d’états](media/report-group.gif "Groupe de rapports") sur la barre d’outils.</span><span class="sxs-lookup"><span data-stu-id="74684-125">Alternatively, click the **Report Group** button ![Report Group](media/report-group.gif "Report Group") on the toolbar.</span></span>
3. <span data-ttu-id="74684-126">Cliquez sur l’onglet **Groupe de rapports**. Pour remplacer les informations sur les différentes définitions d’état pour la génération de cet état, activez la case à cocher **Remplacer les paramètres de la société, des détails et de date à partir des définitions d’état**.</span><span class="sxs-lookup"><span data-stu-id="74684-126">Click the **Report Group** tab. To override the information on the individual report definitions for the generation of this report, select the **Override company, detail, and date settings from individual report definitions** check box.</span></span> <span data-ttu-id="74684-127">Les informations sur le nom de la société, le niveau de détail, les paramètres provisionnels et la date sont fournis automatiquement mais vous pouvez toujours effectuer des mises à jour.</span><span class="sxs-lookup"><span data-stu-id="74684-127">The company name, detail level, provisional setting, and date information are entered automatically, but you can make updates.</span></span>
4. <span data-ttu-id="74684-128">Pour générer plusieurs états affichant les devises de déclaration, activez la case à cocher **Inclure toutes les devises de déclaration**.</span><span class="sxs-lookup"><span data-stu-id="74684-128">To generate multiple reports that show the reporting currencies, select the **Include all reporting currencies** check box.</span></span> <span data-ttu-id="74684-129">Vous pouvez ensuite accéder à plusieurs en cliquant sur le bouton **Devise** dans la visionneuse Web lorsque vous afficherez l’état.</span><span class="sxs-lookup"><span data-stu-id="74684-129">You can then access multiple views by clicking the **Currency** button in the Web Viewer when you view the report.</span></span>
5. <span data-ttu-id="74684-130">Dans le champ **États dans le groupe**, cliquez sur **Ajouter** pour sélectionner les états à inclure dans le groupe d’états.</span><span class="sxs-lookup"><span data-stu-id="74684-130">In the **Reports in group** field, click **Add** to select the reports to include in the report group.</span></span> <span data-ttu-id="74684-131">Pour sélectionner plusieurs états dans la boîte de dialogue **Ajouter**, maintenez la touche Ctrl enfoncée alors que vous sélectionnez des états.</span><span class="sxs-lookup"><span data-stu-id="74684-131">To select multiple reports in the **Add** dialog box, hold down the Ctrl key while you select reports.</span></span> <span data-ttu-id="74684-132">Lorsque vous avez terminé la sélection des états, cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="74684-132">When you've finished selecting reports, click **OK**.</span></span>
6. <span data-ttu-id="74684-133">Cliquez sur **Fichier** &gt; **Enregistrer** pour enregistrer le nouveau groupe d’états.</span><span class="sxs-lookup"><span data-stu-id="74684-133">Click **File** &gt; **Save** to save the new report group.</span></span>

### <a name="modify-a-report-group"></a><span data-ttu-id="74684-134">Modifier un groupe d’états</span><span class="sxs-lookup"><span data-stu-id="74684-134">Modify a report group</span></span>

1. <span data-ttu-id="74684-135">Dans le générateur d’états, dans le volet de navigation, cliquez sur **Groupes d’états** dans le volet de navigation.</span><span class="sxs-lookup"><span data-stu-id="74684-135">In Report Designer, in the navigation pane, click **Report Groups**.</span></span>
2. <span data-ttu-id="74684-136">Double-cliquez sur le groupe d’états à modifier.</span><span class="sxs-lookup"><span data-stu-id="74684-136">Double-click the report group to modify.</span></span>
3. <span data-ttu-id="74684-137">Sur l’onglet **Groupe d’états**, apportez les modifications que vous souhaitez.</span><span class="sxs-lookup"><span data-stu-id="74684-137">On the **Report Group** tab, make the changes that you want.</span></span>
4. <span data-ttu-id="74684-138">Dans le menu **Fichier**, cliquez sur **Enregistrer** pour enregistrer le groupe d’états modifié ou sur le bouton **Enregistrer** ![Enregistrer](media/save.gif "Enregistrer") dans la barre d’outils.</span><span class="sxs-lookup"><span data-stu-id="74684-138">On the **File** menu, click **Save** to save the modified report group, Alternatively, click the **Save** button ![Save](media/save.gif "Save") on the toolbar.</span></span>

> <span data-ttu-id="74684-139">[REMARQUE] Si vous avez planifié des états à générer à intervalles définis, vous pouvez remplacer ces paramètres et déclarer un état immédiatement.</span><span class="sxs-lookup"><span data-stu-id="74684-139">[NOTE] If you've scheduled reports so that they are generated at set intervals, you can override those settings and generate a report immediately.</span></span>

### <a name="generate-a-report-group-report"></a><span data-ttu-id="74684-140">Générer un état du groupe d’états</span><span class="sxs-lookup"><span data-stu-id="74684-140">Generate a report group report</span></span>

1. <span data-ttu-id="74684-141">Dans le générateur d’états, dans le volet de navigation, cliquez sur **Groupes d’états** dans le volet de navigation.</span><span class="sxs-lookup"><span data-stu-id="74684-141">In Report Designer, in the navigation pane, click **Report Groups**.</span></span>
2. <span data-ttu-id="74684-142">Ouvrez le groupe d’états à générer.</span><span class="sxs-lookup"><span data-stu-id="74684-142">Open the report group to generate.</span></span>
3. <span data-ttu-id="74684-143">Cliquez sur le bouton **Générer un état** ![Générer un état](media/generate-report.gif "Générer un état") pour générer des états.</span><span class="sxs-lookup"><span data-stu-id="74684-143">Click the **Generate Report** button ![Generate Report](media/generate-report.gif "Generate Report") to generate reports.</span></span>

### <a name="delete-a-report-group"></a><span data-ttu-id="74684-144">Supprimer un groupe d’états</span><span class="sxs-lookup"><span data-stu-id="74684-144">Delete a report group</span></span>

1. <span data-ttu-id="74684-145">Dans le générateur d’états, dans le volet de navigation, cliquez sur **Groupes d’états** dans le volet de navigation.</span><span class="sxs-lookup"><span data-stu-id="74684-145">In Report Designer, in the navigation pane, click **Report Groups**.</span></span>
2. <span data-ttu-id="74684-146">Cliquez avec le bouton droit sur le groupe d’états à supprimer, puis sélectionnez **Supprimer**.</span><span class="sxs-lookup"><span data-stu-id="74684-146">Right-click the report group to delete, and then select **Delete**.</span></span>
3. <span data-ttu-id="74684-147">Lorsqu’un message de confirmation apparaît, cliquez sur **Oui**.</span><span class="sxs-lookup"><span data-stu-id="74684-147">When a confirmation message appears, click **Yes**.</span></span>

## <a name="report-group-tab-controls"></a><span data-ttu-id="74684-148">Contrôles de l’onglet Groupe d’états</span><span class="sxs-lookup"><span data-stu-id="74684-148">Report Group tab controls</span></span>
<span data-ttu-id="74684-149">Le tableau suivant décrit les contrôles l’onglet **Groupe d’états**.</span><span class="sxs-lookup"><span data-stu-id="74684-149">The following table describes the controls on the **Report Group** tab.</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="74684-150">Contrôle</span><span class="sxs-lookup"><span data-stu-id="74684-150">Control</span></span></th>
<th><span data-ttu-id="74684-151">Description</span><span class="sxs-lookup"><span data-stu-id="74684-151">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="74684-152">Remplacer les paramètres de la société, des détails et de date à partir des définitions d’état</span><span class="sxs-lookup"><span data-stu-id="74684-152">Override company, detail, and date settings from individual report definitions</span></span></td>
<td><span data-ttu-id="74684-153">Activez cette case à cocher pour remplacer les définitions d’état individuelles des états dans ce groupe d’états pour la génération de ces états uniquement.</span><span class="sxs-lookup"><span data-stu-id="74684-153">Select this check box to override individual report definitions of the reports in this report group for the generation of these reports only.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="74684-154">Nom de la société</span><span class="sxs-lookup"><span data-stu-id="74684-154">Company name</span></span></td>
<td><span data-ttu-id="74684-155">Sélectionnez la société à utiliser pour les états.</span><span class="sxs-lookup"><span data-stu-id="74684-155">Select the company to use for the reports.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="74684-156">Niveau de détail</span><span class="sxs-lookup"><span data-stu-id="74684-156">Detail level</span></span></td>
<td><span data-ttu-id="74684-157">Permet de spécifier le niveau de détail souhaité dans l’état.</span><span class="sxs-lookup"><span data-stu-id="74684-157">Specify the level of detail that the reports include.</span></span>
<ul>
<li><span data-ttu-id="74684-158"><strong>Rapport financier</strong> − Rapport de synthèse de haut niveau.</span><span class="sxs-lookup"><span data-stu-id="74684-158"><strong>Financial</strong> − A high-level summary report.</span></span> <span data-ttu-id="74684-159">Vous ne pouvez pas effectuer de zoom avant dans les comptes et les dimensions, à l&#39;exception de ceux ajoutés via une arborescence de génération d’états.</span><span class="sxs-lookup"><span data-stu-id="74684-159">You can&#39;t drill down to accounts and dimensions, except for those accounts and dimensions that have been added through a reporting tree.</span></span></li>
<li><span data-ttu-id="74684-160"><strong>Financier &amp; Compte</strong> − État qui contient une synthèse de haut niveau et des détails du compte.</span><span class="sxs-lookup"><span data-stu-id="74684-160"><strong>Financial &amp; Account</strong> − A report that contains a high-level summary and account details.</span></span></li>
<li><span data-ttu-id="74684-161"><strong>Financier, Compte &amp; Transaction</strong> État qui contient une synthèse de haut niveau et des détails de la transaction.</span><span class="sxs-lookup"><span data-stu-id="74684-161"><strong>Financial, Account, &amp; Transaction</strong> − A report that contains a high-level summary and transaction details.</span></span></li>
</ul></td>
</tr>
<tr>
<td><span data-ttu-id="74684-162">Provisionnel</span><span class="sxs-lookup"><span data-stu-id="74684-162">Provisional</span></span></td>
<td><span data-ttu-id="74684-163">Permet de spécifier les types d’activités souhaités dans l’état.</span><span class="sxs-lookup"><span data-stu-id="74684-163">Specify the types of activity that the reports include.</span></span>
<ul>
<li><span data-ttu-id="74684-164"><strong>Activité validée uniquement</strong> − Inclut uniquement les transactions et les soldes validés dans vos données financières.</span><span class="sxs-lookup"><span data-stu-id="74684-164"><strong>Posted activity only</strong> − Include only the transactions and balances that are posted in your financial data.</span></span></li>
<li><span data-ttu-id="74684-165"><strong>Activité validée et non validée</strong> − Inclut tous les soldes et transactions entrés et validés dans vos données financières.</span><span class="sxs-lookup"><span data-stu-id="74684-165"><strong>Posted and unposted activity</strong> − Include all the transactions and balances that are entered and posted in your financial data.</span></span></li>
<li><span data-ttu-id="74684-166"><strong>Activité non validée uniquement</strong> − Inclut uniquement les transactions entrées mais pas encore validées dans vos données financières.</span><span class="sxs-lookup"><span data-stu-id="74684-166"><strong>Unposted activity only</strong> − Include only the transactions that are entered, but not yet posted, in your financial data.</span></span></li>
</ul></td>
</tr>
<tr>
<td><span data-ttu-id="74684-167">Inclure toutes les devises de déclaration</span><span class="sxs-lookup"><span data-stu-id="74684-167">Include all reporting currencies</span></span></td>
<td><span data-ttu-id="74684-168">Toutes les devises de déclaration supplémentaires configurées dans votre système Microsoft Dynamics ERP sont indiquées ici.</span><span class="sxs-lookup"><span data-stu-id="74684-168">Any additional reporting currencies that are configured in your Microsoft Dynamics ERP system are listed here.</span></span> <span data-ttu-id="74684-169">Activez cette case à cocher pour générer des états supplémentaires dans les devises indiquées.</span><span class="sxs-lookup"><span data-stu-id="74684-169">Select this check box to generate additional reports in the currencies that are indicated.</span></span> <span data-ttu-id="74684-170">Pour afficher ces rapports dans la visionneuse Web, cliquez sur le bouton <strong>Devise</strong> et sélectionnez une devise.</span><span class="sxs-lookup"><span data-stu-id="74684-170">To view these reports in the Web Viewer, click the <strong>Currency</strong> button, and then select a currency.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="74684-171">Informations de date non enregistrées avec la définition d’état</span><span class="sxs-lookup"><span data-stu-id="74684-171">Date information not saved with report definition</span></span></td>
<td><ul>
<li><span data-ttu-id="74684-172">Période de base</span><span class="sxs-lookup"><span data-stu-id="74684-172">Base period</span></span></li>
<li><span data-ttu-id="74684-173">Année de base</span><span class="sxs-lookup"><span data-stu-id="74684-173">Base year</span></span></li>
<li><span data-ttu-id="74684-174">Période couverte</span><span class="sxs-lookup"><span data-stu-id="74684-174">Period covered</span></span></li>
</ul>
<span data-ttu-id="74684-175">Seuls les paramètres de période de base par défaut sont enregistrés avec la définition d’état.</span><span class="sxs-lookup"><span data-stu-id="74684-175">Only default base period settings are saved with the report definition.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="74684-176">Informations de date enregistrées avec la définition d’état</span><span class="sxs-lookup"><span data-stu-id="74684-176">Date information saved with report definition</span></span></td>
<td><ul>
<li><span data-ttu-id="74684-177">Date de l’état</span><span class="sxs-lookup"><span data-stu-id="74684-177">Report date</span></span></li>
<li><span data-ttu-id="74684-178">Période de base par défaut</span><span class="sxs-lookup"><span data-stu-id="74684-178">Default base period</span></span></li>
</ul></td>
</tr>
<tr>
<td><span data-ttu-id="74684-179">États dans le groupe</span><span class="sxs-lookup"><span data-stu-id="74684-179">Reports in group</span></span></td>
<td><span data-ttu-id="74684-180">Permet d’ajouter, de supprimer, et de trier à nouveau les états dans le groupe d’états.</span><span class="sxs-lookup"><span data-stu-id="74684-180">Add, remove, and re-order reports in the report group.</span></span>
<ul>
<li><span data-ttu-id="74684-181">Pour ajouter des définitions de rapport au groupe de rapports, double-cliquez sur ce dernier pour l’ouvrir, puis cliquez sur <strong>Ajouter</strong>.</span><span class="sxs-lookup"><span data-stu-id="74684-181">To add report definitions to the report group, double-click the report group to open it, and then click <strong>Add</strong>.</span></span> <span data-ttu-id="74684-182">Sélectionnez les rapports à inclure dans le groupe de rapports, puis cliquez sur <strong>OK</strong>.</span><span class="sxs-lookup"><span data-stu-id="74684-182">Select the reports to include in the report group, and then click <strong>OK</strong>.</span></span></li>
<li><span data-ttu-id="74684-183">Pour supprimer un rapport du groupe de rapports, sélectionnez-le, puis cliquez sur <strong>Supprimer</strong>.</span><span class="sxs-lookup"><span data-stu-id="74684-183">To remove a report from the report group, select it, and then click <strong>Remove</strong>.</span></span></li>
<li><span data-ttu-id="74684-184">Pour modifier l’ordre dans lequel les états sont générés, sélectionnez un état dans la liste, puis cliquez sur <strong>Déplacer vers le haut</strong> ou <strong>Déplacer vers le bas</strong>.</span><span class="sxs-lookup"><span data-stu-id="74684-184">To modify the order that the reports are generated in, select a report in the list, and then click <strong>Move up</strong> or <strong>Move down</strong>.</span></span></li>
</ul></td>
</tr>
</tbody>
</table>

## <a name="additional-resources"></a><span data-ttu-id="74684-185">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="74684-185">Additional resources</span></span>

[<span data-ttu-id="74684-186">États financiers</span><span class="sxs-lookup"><span data-stu-id="74684-186">Financial reporting</span></span>](financial-reporting-intro.md)
