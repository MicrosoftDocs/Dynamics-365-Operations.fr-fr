---
title: "Réinitialiser le mini-data warehouse d'états financiers"
description: "Cette rubrique décrit la procédure de réinitialisation du mini-data warehouse d'états financiers."
author: aolson
manager: AnnBe
ms.date: 12/01/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
audience: Application User, IT Pro
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 261824
ms.search.region: Global
ms.author: aloson
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: HT
ms.sourcegitcommit: 0786d3377b914791106ef30455d676e5ab2ae03d
ms.openlocfilehash: c708fa18b8676d8ff57c26b3176a36d86df29387
ms.contentlocale: fr-fr
ms.lasthandoff: 12/07/2017

---

# <a name="reset-the-financial-reporting-data-mart"></a><span data-ttu-id="97c62-103">Réinitialiser le mini-data warehouse d'états financiers</span><span class="sxs-lookup"><span data-stu-id="97c62-103">Reset the Financial reporting data mart</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="97c62-104">Cette rubrique explique la procédure de réinitialisation du mini-data warehouse d'états financiers pour les versions suivantes :</span><span class="sxs-lookup"><span data-stu-id="97c62-104">This topic explains how to reset the Financial reporting data mart for the following versions:</span></span>

- <span data-ttu-id="97c62-105">Version 7.2.6.0 et ultérieure de Microsoft Dynamics 365 for Finance and Operations Financial Reporting</span><span class="sxs-lookup"><span data-stu-id="97c62-105">Microsoft Dynamics 365 for Finance and Operations Financial reporting release 7.2.6.0 and later</span></span>
- <span data-ttu-id="97c62-106">Version 7.0.10000.4 et ultérieure de Microsoft Dynamics 365 for Finance and Operations Financial Reporting</span><span class="sxs-lookup"><span data-stu-id="97c62-106">Microsoft Dynamics 365 for Finance and Operations Financial reporting release 7.0.10000.4 and later</span></span>
- <span data-ttu-id="97c62-107">Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition (local)</span><span class="sxs-lookup"><span data-stu-id="97c62-107">Microsoft Dynamics 365 for Finance and Operations, Enterprise edition (on-premises)</span></span>

<span data-ttu-id="97c62-108">Pour obtenir la version 7.2.6.0 de Finance and Operations Financial Reporting, vous pouvez télécharger l'article KB 4052514 à l'adresse <https://support.microsoft.com/en-us/help/4052514>.</span><span class="sxs-lookup"><span data-stu-id="97c62-108">To get Finance and Operations Financial reporting release 7.2.6.0, you can download KB 4052514 from <https://support.microsoft.com/en-us/help/4052514>.</span></span>

## <a name="reset-the-financial-reporting-data-mart-for-finance-and-operations-financial-reporting-release-7260-and-later"></a><span data-ttu-id="97c62-109">Réinitialiser le mini-data warehouse d'états financiers pour la version 7.2.6.0 et ultérieure de Finance and Operations Financial Reporting</span><span class="sxs-lookup"><span data-stu-id="97c62-109">Reset the Financial reporting data mart for Finance and Operations Financial reporting release 7.2.6.0 and later</span></span>

### <a name="reset-the-financial-reporting-data-mart-from-report-designer"></a><span data-ttu-id="97c62-110">Réinitialiser le mini-data warehouse d'états financiers à partir du concepteur d'états</span><span class="sxs-lookup"><span data-stu-id="97c62-110">Reset the Financial reporting data mart from Report designer</span></span>

> [!NOTE]
> <span data-ttu-id="97c62-111">Les étapes décrites dans ce processus sont prises en charge par la version 7.2.6.0 et ultérieure de Finance and Operations Financial Reporting.</span><span class="sxs-lookup"><span data-stu-id="97c62-111">The steps in this process are supported for Finance and Operations Financial reporting release 7.2.6.0 and later.</span></span> <span data-ttu-id="97c62-112">Si vous disposez d'une version antérieure, contactez l'équipe de support pour obtenir de l'aide.</span><span class="sxs-lookup"><span data-stu-id="97c62-112">If you have an earlier release, contact the Support team for assistance.</span></span>

<span data-ttu-id="97c62-113">Dans les scénarios spécifiques, vous devrez peut-être réinitialiser le mini-data warehouse pour les états financiers.</span><span class="sxs-lookup"><span data-stu-id="97c62-113">In specific scenarios, you might have to reset the data mart for Financial reporting.</span></span> <span data-ttu-id="97c62-114">Vous pouvez effectuer cette tâche dans le client Concepteur d'états.</span><span class="sxs-lookup"><span data-stu-id="97c62-114">You can complete this task in the Report designer client.</span></span> <span data-ttu-id="97c62-115">Voici quelques scénarios où vous devrez peut-être réinitialiser le mini-data warehouse :</span><span class="sxs-lookup"><span data-stu-id="97c62-115">Here are some scenarios where you might have to reset the data mart:</span></span>

- <span data-ttu-id="97c62-116">La base de données Finance and Operations a été restaurée, mais pas celle du mini-data warehouse.</span><span class="sxs-lookup"><span data-stu-id="97c62-116">The Finance and Operations database was restored, but the data mart database wasn't restored.</span></span>
- <span data-ttu-id="97c62-117">Des données incorrectes s'affichent pour une période.</span><span class="sxs-lookup"><span data-stu-id="97c62-117">You see incorrect data for a period.</span></span>
- <span data-ttu-id="97c62-118">Le support technique vous demande de réinitialiser le mini-data warehouse dans le cadre d'une étape de dépannage.</span><span class="sxs-lookup"><span data-stu-id="97c62-118">Support instructs you to reset the data mart as part of a troubleshooting step.</span></span>

<span data-ttu-id="97c62-119">La réinitialisation du mini-data warehouse doit être effectuée uniquement à des périodes où peu de traitements sont exécutés sur la base de données.</span><span class="sxs-lookup"><span data-stu-id="97c62-119">The data mart reset should be done only during times when the amount of processing on the database is small.</span></span> <span data-ttu-id="97c62-120">Les états financiers seront indisponibles pendant le processus de réinitialisation.</span><span class="sxs-lookup"><span data-stu-id="97c62-120">Financial reporting will be unavailable during the reset process.</span></span>

#### <a name="reset-the-data-mart"></a><span data-ttu-id="97c62-121">Réinitialiser le mini-data warehouse</span><span class="sxs-lookup"><span data-stu-id="97c62-121">Reset the data mart</span></span>

<span data-ttu-id="97c62-122">Pour réinitialiser le mini-data warehouse, dans le concepteur d'états, dans le menu **Outils**, sélectionnez **Réinitialiser le mini-data warehouse**.</span><span class="sxs-lookup"><span data-stu-id="97c62-122">To reset the data mart, in Report designer, on the **Tools** menu, select **Reset Data Mart**.</span></span> <span data-ttu-id="97c62-123">La boîte de dialogue qui s'affiche comporte deux sections : **Statistiques** et **Réinitialiser**.</span><span class="sxs-lookup"><span data-stu-id="97c62-123">The dialog box that appears has two sections: **Statistics** and **Reset**.</span></span>

<span data-ttu-id="97c62-124">[![Boîte de dialogue Réinitialiser le mini-data warehouse](./media/Statistics.png)](./media/Statistics.png)</span><span class="sxs-lookup"><span data-stu-id="97c62-124">[![Reset Data Mart dialog box](./media/Statistics.png)](./media/Statistics.png)</span></span>

##### <a name="integration-attempts"></a><span data-ttu-id="97c62-125">Tentatives d'intégration</span><span class="sxs-lookup"><span data-stu-id="97c62-125">Integration attempts</span></span>

<span data-ttu-id="97c62-126">La grille **Tentatives d'intégration** affiche le nombre de tentatives d'intégration de transactions par le système.</span><span class="sxs-lookup"><span data-stu-id="97c62-126">The **Integration attempts** grid shows how many times the system has tried to integrate transactions.</span></span> <span data-ttu-id="97c62-127">Le système continue d'essayer d'intégrer les données au fil des jours si les premières tentatives sont infructueuses.</span><span class="sxs-lookup"><span data-stu-id="97c62-127">The system continues to try to integrate data over a period of days if the first few attempts aren't successful.</span></span> <span data-ttu-id="97c62-128">Vous saurez que le mini-data warehouse doit être réinitialisé si le nombre de tentatives est égal à 8 ou plus, et s'il existe plusieurs enregistrements de combinaison de dimensions ou de transaction.</span><span class="sxs-lookup"><span data-stu-id="97c62-128">You will know that the data mart must be reset is if the number of attempts is 8 or more, and if there are many Dimension combination or Transaction records.</span></span> <span data-ttu-id="97c62-129">Dans ce cas, un état des données ne sera pas généré.</span><span class="sxs-lookup"><span data-stu-id="97c62-129">In this situation, the data won't be reported on.</span></span>

##### <a name="data-status"></a><span data-ttu-id="97c62-130">Statut des données</span><span class="sxs-lookup"><span data-stu-id="97c62-130">Data status</span></span>

<span data-ttu-id="97c62-131">La grille **Statut des données** fournit un instantané des transactions, des taux de change et des valeurs de dimension dans le mini-data warehouse.</span><span class="sxs-lookup"><span data-stu-id="97c62-131">The **Data status** grid provides a snapshot of the transactions, exchange rates, and dimension values in the data mart.</span></span> <span data-ttu-id="97c62-132">Un grand nombre d'enregistrements périmés indique que plusieurs mises à jour des enregistrements ont été effectuées.</span><span class="sxs-lookup"><span data-stu-id="97c62-132">A large number of stale records indicates that numerous updates to the records have occurred.</span></span> <span data-ttu-id="97c62-133">Cette situation peut ralentir les délais de génération d'états.</span><span class="sxs-lookup"><span data-stu-id="97c62-133">This situation might cause slower report generation times.</span></span>

##### <a name="misaligned-main-account-categories"></a><span data-ttu-id="97c62-134">Catégories de compte principal non alignées</span><span class="sxs-lookup"><span data-stu-id="97c62-134">Misaligned main account categories</span></span>

<span data-ttu-id="97c62-135">Si vous utilisez une version antérieure à la version 7.2.1 de Microsoft Dynamics 365 for Finance and Operations Financial Reporting, vous devrez peut-être réinitialiser le mini-data warehouse si vous renommez des comptes et déplacez des comptes entre des catégories de compte.</span><span class="sxs-lookup"><span data-stu-id="97c62-135">If you're using a release that is earlier than Microsoft Dynamics 365 for Finance and Operations Financial reporting release 7.2.1, you might have to reset the data mart if you rename accounts and move accounts between account categories.</span></span> <span data-ttu-id="97c62-136">Ces actions peuvent entraîner un alignement incorrect des catégories de compte principal.</span><span class="sxs-lookup"><span data-stu-id="97c62-136">These actions can cause main account categories to become misaligned.</span></span> <span data-ttu-id="97c62-137">Le champ **Catégories de compte principal non alignées** s'affiche si vous rencontrez ce problème.</span><span class="sxs-lookup"><span data-stu-id="97c62-137">The **Misaligned main account categories** field shows whether you're experiencing that issue.</span></span>

### <a name="reset-the-data-mart-in-finance-and-operations-financial-reporting-release-7260"></a><span data-ttu-id="97c62-138">Réinitialiser le mini-data warehouse dans la version 7.2.6.0 de Finance and Operations Financial Reporting</span><span class="sxs-lookup"><span data-stu-id="97c62-138">Reset the data mart in Finance and Operations Financial reporting release 7.2.6.0</span></span>

<span data-ttu-id="97c62-139">Pour réinitialiser le mini-data warehouse dans la version 7.2.6.0 et antérieure de Finance and Operations Financial Reporting, dans la boîte de dialogue **Réinitialiser le mini-data warehouse**, activez la case à cocher **Réinitialiser le mini-data warehouse**, puis sélectionnez **OK**.</span><span class="sxs-lookup"><span data-stu-id="97c62-139">To reset the data mart in Finance and Operations Financial reporting release 7.2.6.0 and earlier, in the **Reset Data Mart** dialog box, select the **Reset data mart** check box, and then select **OK**.</span></span> <span data-ttu-id="97c62-140">Vous devez réinitialiser le mini-data warehouse uniquement pendant les interruptions planifiées.</span><span class="sxs-lookup"><span data-stu-id="97c62-140">You should reset the data mart only during scheduled downtime.</span></span>

<span data-ttu-id="97c62-141">[![Case à cocher Réinitialiser le mini-data warehouse](./media/Reset-72.jpg)](./media/Reset-72.jpg)</span><span class="sxs-lookup"><span data-stu-id="97c62-141">[![Reset data mart check box](./media/Reset-72.jpg)](./media/Reset-72.jpg)</span></span>

### <a name="reset-the-data-mart-and-select-a-reason-in-microsoft-dynamics-365-for-finance-and-operations-financial-reporting-release-730"></a><span data-ttu-id="97c62-142">Réinitialiser le mini-data warehouse et sélectionner un motif dans la version 7.3.0 de Microsoft Dynamics 365 for Finance and Operations Financial Reporting</span><span class="sxs-lookup"><span data-stu-id="97c62-142">Reset the data mart and select a reason in Microsoft Dynamics 365 for Finance and Operations Financial reporting release 7.3.0</span></span>

<span data-ttu-id="97c62-143">Si vous déterminez qu'une réinitialisation du mini-data warehouse est nécessaire, activez la case à cocher **Réinitialiser le mini-data warehouse**, puis sélectionnez un motif dans le champ **Motif**.</span><span class="sxs-lookup"><span data-stu-id="97c62-143">If you determine that a data mart reset is required, select the **Reset data mart** check box, and then select a reason in the **Reason** field.</span></span> <span data-ttu-id="97c62-144">Les options suivantes sont disponibles :</span><span class="sxs-lookup"><span data-stu-id="97c62-144">The following options are available:</span></span>

- <span data-ttu-id="97c62-145">**Données manquantes ou incorrectes** – Sur la base des statistiques, vous avez déterminé que des données sont peut-être manquantes.</span><span class="sxs-lookup"><span data-stu-id="97c62-145">**Missing or incorrect data** – Based on the statistics, you've determined that data might be missing.</span></span> <span data-ttu-id="97c62-146">Avant de continuer, nous vous recommandons de contacter le support technique pour déterminer la cause principale.</span><span class="sxs-lookup"><span data-stu-id="97c62-146">Before you continue, we recommend that you work with Support to determine the root cause.</span></span>
- <span data-ttu-id="97c62-147">**Restaurer la base de données** – La base de données Finance and Operations a été restaurée, mais pas celle du mini-data warehouse d'états financiers.</span><span class="sxs-lookup"><span data-stu-id="97c62-147">**Restore database** – The Finance and Operations database was restored, but the database for the Financial reporting data mart wasn't restored.</span></span>
- <span data-ttu-id="97c62-148">**Autre** – Vous réinitialisez le mini-data warehouse pour un autre motif.</span><span class="sxs-lookup"><span data-stu-id="97c62-148">**Other** – You're resetting the data mart for another reason.</span></span> <span data-ttu-id="97c62-149">Si vous êtes préoccupé par un problème, contactez le support technique pour l'identifier.</span><span class="sxs-lookup"><span data-stu-id="97c62-149">If you're concerned that there is an issue, contact Support to identify it.</span></span>

> [!NOTE]
> <span data-ttu-id="97c62-150">Vérifiez que l'intégration de toutes les tâches existantes est terminée avant d'effectuer les étapes.</span><span class="sxs-lookup"><span data-stu-id="97c62-150">Verify that all existing tasks have finished integrating before you complete the steps.</span></span> <span data-ttu-id="97c62-151">Vous pouvez afficher le statut de l'intégration en sélectionnant **Outils** &gt; **Statut de l'intégration**.</span><span class="sxs-lookup"><span data-stu-id="97c62-151">You can view the status of the integration by selecting **Tools** &gt; **Integration status**.</span></span>

#### <a name="clear-users-and-companies"></a><span data-ttu-id="97c62-152">Effacer les utilisateurs et les sociétés</span><span class="sxs-lookup"><span data-stu-id="97c62-152">Clear users and companies</span></span>

<span data-ttu-id="97c62-153">Activez la case à cocher **Effacer les utilisateurs et les sociétés** si vous avez restauré votre base de données, mais vous avez ensuite apporté des modifications aux utilisateurs ou sociétés.</span><span class="sxs-lookup"><span data-stu-id="97c62-153">Select the **Clear users and companies** check box if you restored your database, but you then made changes to users or companies.</span></span> <span data-ttu-id="97c62-154">Vous devez rarement activer cette case à cocher.</span><span class="sxs-lookup"><span data-stu-id="97c62-154">You should rarely have to select this check box.</span></span>

<span data-ttu-id="97c62-155">Lorsque vous êtes prêt à démarrer le processus de réinitialisation, sélectionnez **OK**.</span><span class="sxs-lookup"><span data-stu-id="97c62-155">When you're ready to start the reset process, select **OK**.</span></span> <span data-ttu-id="97c62-156">Vous êtes invité à confirmer que vous êtes prêt à démarrer le processus.</span><span class="sxs-lookup"><span data-stu-id="97c62-156">You're prompted to confirm that you're ready to start the process.</span></span> <span data-ttu-id="97c62-157">Notez que les états financiers ne seront pas disponibles lors de la réinitialisation et de l'intégration des données d'origine qui a lieu par la suite.</span><span class="sxs-lookup"><span data-stu-id="97c62-157">Note that Financial reporting won't be available during the reset and the initial data integration that occurs afterward.</span></span>

<span data-ttu-id="97c62-158">Si vous souhaitez examiner le statut de l'intégration, sélectionnez &gt; **Outils** **Statut de l'intégration** pour afficher la dernière date d'exécution de l'intégration et le statut.</span><span class="sxs-lookup"><span data-stu-id="97c62-158">If you want to review the status of the integration, select **Tools** &gt; **Integration status** to see the last time that the integration was run and the status.</span></span>

<span data-ttu-id="97c62-159">[![Afficher le statut de l'intégration](./media/Integration.png)](./media/Integration.png)</span><span class="sxs-lookup"><span data-stu-id="97c62-159">[![View the status of the integration](./media/Integration.png)](./media/Integration.png)</span></span>

## <a name="reset-the-financial-reporting-data-mart-for-finance-and-operations-financial-reporting-release-70100004-and-later"></a><span data-ttu-id="97c62-160">Réinitialiser le mini-data warehouse d'états financiers pour la version 7.0.10000.4 et ultérieure de Finance and Operations Financial Reporting</span><span class="sxs-lookup"><span data-stu-id="97c62-160">Reset the Financial reporting data mart for Finance and Operations Financial reporting release 7.0.10000.4 and later</span></span>

<span data-ttu-id="97c62-161">Si vous restaurez votre base de données Finance and Operations à partir d'une sauvegarde ou copiez la base de données à partir d'un autre environnement, vous devez suivre les étapes de cette section pour garantir que le mini-data warehouse d'états financiers utilise correctement la base de données Finance and Operations restaurée.</span><span class="sxs-lookup"><span data-stu-id="97c62-161">If you ever restore your Finance and Operations database from a backup or copy the database from another environment, you must follow the steps in this section to help guarantee that the Financial reporting data mart correctly uses the restored Finance and Operations database.</span></span>

> [!NOTE]
> <span data-ttu-id="97c62-162">Les étapes de ce processus sont prises en charge pour la version 7.0.1 de l'application Microsoft Dynamics AX (mai 2016) (version d'application 7.0.1265.23014 et version 7.0.10000.4 de Financial Reporting) et ultérieure.</span><span class="sxs-lookup"><span data-stu-id="97c62-162">The steps in this process are supported for Microsoft Dynamics AX application version 7.0.1 (May 2016) (application build 7.0.1265.23014 and Financial reporting build 7.0.10000.4) and later.</span></span> <span data-ttu-id="97c62-163">Si vous disposez d'une version antérieure de Finance and Operations, contactez le support technique pour obtenir de l'aide.</span><span class="sxs-lookup"><span data-stu-id="97c62-163">If you have an earlier version of Finance and Operations, contact Support for assistance.</span></span>

### <a name="export-report-definitions"></a><span data-ttu-id="97c62-164">Exporter des définitions d'état</span><span class="sxs-lookup"><span data-stu-id="97c62-164">Export report definitions</span></span>

<span data-ttu-id="97c62-165">Effectuez d'abord les étapes ci-après pour exporter les conceptions d'état à partir du concepteur d'états.</span><span class="sxs-lookup"><span data-stu-id="97c62-165">First, follow these steps to export the report designs from Report designer.</span></span>

1. <span data-ttu-id="97c62-166">Dans le concepteur d'états, sélectionnez **Société** &gt; **Groupes de blocs élémentaires**.</span><span class="sxs-lookup"><span data-stu-id="97c62-166">In Report designer, select **Company** &gt; **Building Block Groups**.</span></span>
2. <span data-ttu-id="97c62-167">Sélectionnez le groupe de blocs élémentaires à exporter, puis sélectionnez **Exporter**.</span><span class="sxs-lookup"><span data-stu-id="97c62-167">Select the building block group to export, and then select **Export**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="97c62-168">Pour Finance and Operations, un seul groupe de blocs élémentaires est pris en charge, **Valeur par défaut**.</span><span class="sxs-lookup"><span data-stu-id="97c62-168">For Finance and Operations, only one building block group is supported, **Default**.</span></span>

3. <span data-ttu-id="97c62-169">Sélectionnez des définitions de rapport à exporter :</span><span class="sxs-lookup"><span data-stu-id="97c62-169">Select the report definitions to export:</span></span>

    - <span data-ttu-id="97c62-170">Pour exporter toutes les définitions d'état et les blocs élémentaires associés, sélectionnez **Sélectionner tout**.</span><span class="sxs-lookup"><span data-stu-id="97c62-170">To export all your report definitions and the associated building blocks, select **Select All**.</span></span>
    - <span data-ttu-id="97c62-171">Pour exporter des états, lignes, colonnes, organigrammes ou ensembles de dimensions spécifiques, sélectionnez l'onglet approprié, puis les éléments à exporter.</span><span class="sxs-lookup"><span data-stu-id="97c62-171">To export specific reports, rows, columns, trees, or dimension sets, select the appropriate tab, and then select the items to export.</span></span> <span data-ttu-id="97c62-172">Maintenez la touche Ctrl enfoncée pour sélectionner plusieurs articles dans un onglet. Lorsque vous sélectionnez des états à exporter, les lignes, colonnes, arborescences et ensembles de dimensions associés sont sélectionnés.</span><span class="sxs-lookup"><span data-stu-id="97c62-172">Press and hold the Ctrl key to select multiple items on a tab. When you select reports to export, the associated rows, columns, trees, and dimension sets are selected.</span></span>

4. <span data-ttu-id="97c62-173">Sélectionnez **Exporter**.</span><span class="sxs-lookup"><span data-stu-id="97c62-173">Select **Export**.</span></span>
5. <span data-ttu-id="97c62-174">Entrez un nom et sélectionnez un emplacement sûr où vous souhaitez enregistrer les définitions d'état exportées.</span><span class="sxs-lookup"><span data-stu-id="97c62-174">Enter a file name, and select a secure location where you want to save the exported report definitions.</span></span>
6. <span data-ttu-id="97c62-175">Sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="97c62-175">Select **Save**.</span></span>

<span data-ttu-id="97c62-176">Vous pouvez copier ou télécharger le fichier dans un emplacement sûr.</span><span class="sxs-lookup"><span data-stu-id="97c62-176">You can copy or upload the file to a secure location.</span></span> <span data-ttu-id="97c62-177">Ainsi, le fichier pourra être importé dans un autre environnement ultérieurement.</span><span class="sxs-lookup"><span data-stu-id="97c62-177">In this way, the file can be imported into a different environment later.</span></span> <span data-ttu-id="97c62-178">Pour plus d'informations sur l'utilisation d'un compte de stockage Microsoft Azure, voir [Transférer les données avec l'utilitaire de ligne de commande AzCopy](/azure/storage/storage-use-azcopy).</span><span class="sxs-lookup"><span data-stu-id="97c62-178">For information about how to use a Microsoft Azure storage account, see [Transfer data with the AzCopy Command-Line Utility](/azure/storage/storage-use-azcopy).</span></span>

> [!NOTE]
> <span data-ttu-id="97c62-179">Microsoft ne fournit pas un compte de stockage dans le cadre de l'accord Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="97c62-179">Microsoft doesn't provide a storage account as part of your Finance and Operations agreement.</span></span> <span data-ttu-id="97c62-180">Vous devez acheter un compte de stockage ou utiliser le compte de stockage d'un abonnement Azure distinct.</span><span class="sxs-lookup"><span data-stu-id="97c62-180">You must either purchase a storage account or use a storage account from a separate Azure subscription.</span></span>

> [!WARNING]
> <span data-ttu-id="97c62-181">Tenez compte du comportement du lecteur D sur les machines virtuelles Azure.</span><span class="sxs-lookup"><span data-stu-id="97c62-181">Be aware of the behavior of drive D on Azure virtual machines (VMs).</span></span> <span data-ttu-id="97c62-182">Ne stockez pas définitivement vos groupes de blocs élémentaires exportés sur le lecteur D. Pour plus d'informations sur les lecteurs temporaires, voir [Présentation du lecteur temporaire sur les machines virtuelles Windows Azure](https://blogs.msdn.microsoft.com/mast/2013/12/06/understanding-the-temporary-drive-on-windows-azure-virtual-machines/).</span><span class="sxs-lookup"><span data-stu-id="97c62-182">Don't permanently store your exported building block groups on drive D. For more information about temporary drives, see [Understanding the temporary drive on Windows Azure Virtual Machines](https://blogs.msdn.microsoft.com/mast/2013/12/06/understanding-the-temporary-drive-on-windows-azure-virtual-machines/).</span></span>

### <a name="stop-services"></a><span data-ttu-id="97c62-183">Arrêter les services</span><span class="sxs-lookup"><span data-stu-id="97c62-183">Stop services</span></span>

<span data-ttu-id="97c62-184">Les services Microsoft Windows suivants maintiendront les connexions ouvertes dans la base de données Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="97c62-184">The following Microsoft Windows services will have open connections to the Finance and Operations database.</span></span> <span data-ttu-id="97c62-185">Par conséquent, vous devez utiliser le Bureau à distance Microsoft pour vous connecter à tous les ordinateurs de l'environnement, puis utiliser services.msc pour arrêter ces services.</span><span class="sxs-lookup"><span data-stu-id="97c62-185">Therefore, you must use Microsoft Remote Desktop to connect to all the computers in the environment and then use services.msc to stop these services.</span></span>

- <span data-ttu-id="97c62-186">Service de publication World Wide Web (sur tous les ordinateurs Application Object Servers [AOS])</span><span class="sxs-lookup"><span data-stu-id="97c62-186">World wide web publishing service (on all Application Object Servers [AOS] computers)</span></span>
- <span data-ttu-id="97c62-187">Service de gestion des traitements par lots Microsoft Dynamics 365 for Finance and Operations (sur les ordinateurs AOS non privés uniquement)</span><span class="sxs-lookup"><span data-stu-id="97c62-187">Microsoft Dynamics 365 for Finance and Operations Batch Management Service (on non-private AOS computers only)</span></span>
- <span data-ttu-id="97c62-188">Service de traitement Management Reporter 2012 (sur les ordinateurs Business Intelligence [BI] uniquement)</span><span class="sxs-lookup"><span data-stu-id="97c62-188">Management Reporter 2012 Process Service (on Business intelligence [BI] computers only)</span></span>

### <a name="reset"></a><span data-ttu-id="97c62-189">Rétablir</span><span class="sxs-lookup"><span data-stu-id="97c62-189">Reset</span></span>

#### <a name="download-the-latest-minorversiondataupgradezip-package"></a><span data-ttu-id="97c62-190">Télécharger le package MinorVersionDataUpgrade.zip le plus récent</span><span class="sxs-lookup"><span data-stu-id="97c62-190">Download the latest MinorVersionDataUpgrade.zip package</span></span>

<span data-ttu-id="97c62-191">Téléchargez le package MinorVersionDataUpgrade.zip le plus récent.</span><span class="sxs-lookup"><span data-stu-id="97c62-191">Download the latest MinorVersionDataUpgrade.zip package.</span></span> <span data-ttu-id="97c62-192">Pour obtenir des instructions sur la recherche et le téléchargement de la version correcte du package de mise à niveau des données, voir [Télécharger le dernier package déployable de mise à niveau des données](..\migration-upgrade\upgrade-data-to-latest-update.md#download-the-latest-data-upgrade-deployable-packages).</span><span class="sxs-lookup"><span data-stu-id="97c62-192">For instructions about how to find and download the correct version of the data upgrade package, see the[Download the latest data upgrade deployable package](..\migration-upgrade\upgrade-data-to-latest-update.md#download-the-latest-data-upgrade-deployable-packages).</span></span> <span data-ttu-id="97c62-193">Une mise à niveau n'est pas nécessaire pour télécharger le package MinorVersionDataUpgrade.zip.</span><span class="sxs-lookup"><span data-stu-id="97c62-193">An upgrade isn't required in order to download the MinorVersionDataUpgrade.zip package.</span></span> <span data-ttu-id="97c62-194">Par conséquent, vous devez simplement suivre les étapes décrites dans la section « Télécharger le dernier package déployable de mise à niveau des données » de cette rubrique.</span><span class="sxs-lookup"><span data-stu-id="97c62-194">Therefore, you just have follow the steps in the "Download the latest data upgrade deployable package" section of that topic.</span></span> <span data-ttu-id="97c62-195">Vous pouvez ignorer toutes les autres étapes de la rubrique.</span><span class="sxs-lookup"><span data-stu-id="97c62-195">You can skip all the other steps in the topic.</span></span>

#### <a name="run-scripts-against-the-finance-and-operations-database"></a><span data-ttu-id="97c62-196">Exécuter les scripts sur la base de données Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="97c62-196">Run scripts against the Finance and Operations database</span></span>

<span data-ttu-id="97c62-197">Exécutez les scripts suivants sur la base de données Finance and Operations (et non sur la base de données d'états financiers) :</span><span class="sxs-lookup"><span data-stu-id="97c62-197">Run the following scripts against the Finance and Operations database (not against the Financial reporting database):</span></span>

- <span data-ttu-id="97c62-198">DataUpgrade.zip\\AosService\\Scripts\\ConfigureAxReportingIntegration.sql</span><span class="sxs-lookup"><span data-stu-id="97c62-198">DataUpgrade.zip\\AosService\\Scripts\\ConfigureAxReportingIntegration.sql</span></span>
- <span data-ttu-id="97c62-199">DataUpgrade.zip\\AosService\\Scripts\\GrantAzViewChangeTracking.sql</span><span class="sxs-lookup"><span data-stu-id="97c62-199">DataUpgrade.zip\\AosService\\Scripts\\GrantAzViewChangeTracking.sql</span></span>

<span data-ttu-id="97c62-200">Ces scripts garantissent que les utilisateurs, les rôles et les paramètres de suivi de modifications sont corrects.</span><span class="sxs-lookup"><span data-stu-id="97c62-200">These scripts help guarantee that the users, roles, and change tracking settings are correct.</span></span>

#### <a name="run-a-windows-powershell-command-to-reset-the-database"></a><span data-ttu-id="97c62-201">Exécuter une commande Windows PowerShell pour réinitialiser la base de données</span><span class="sxs-lookup"><span data-stu-id="97c62-201">Run a Windows PowerShell command to reset the database</span></span>

<span data-ttu-id="97c62-202">Sur l'ordinateur AOS, démarrez Microsoft Windows PowerShell en tant qu'administrateur et exécutez les commandes suivantes pour réinitialiser l'intégration entre Finance and Operations et les états financiers.</span><span class="sxs-lookup"><span data-stu-id="97c62-202">On the AOS computer, start Microsoft Windows PowerShell as an administrator, and run the following commands to reset the integration between Finance and Operations and Financial reporting.</span></span>

```
F:
cd F:\MRApplicationService\MRInstallDirectory
Import-Module .\Server\MRDeploy\MRDeploy.psd1
Reset-DatamartIntegration -Reason OTHER -ReasonDetail "<reason for resetting>"
```

<span data-ttu-id="97c62-203">Voici une explication des paramètres dans la commande **Reset-DatamartIntegration** :</span><span class="sxs-lookup"><span data-stu-id="97c62-203">Here is an explanation of the parameters in the **Reset-DatamartIntegration** command:</span></span>

- <span data-ttu-id="97c62-204">Les valeurs valides pour **-Reason** sont **SERVICING**, **BADDATA** et **OTHER**.</span><span class="sxs-lookup"><span data-stu-id="97c62-204">The valid values for **-Reason** are **SERVICING**, **BADDATA**, and **OTHER**.</span></span>
- <span data-ttu-id="97c62-205">Le paramètre **-ReasonDetail** est texte libre.</span><span class="sxs-lookup"><span data-stu-id="97c62-205">The **-ReasonDetail** parameter is free text.</span></span>
- <span data-ttu-id="97c62-206">Les paramètres reason et reason detail sont stockés dans le contrôle de télémétrie/d'environnement.</span><span class="sxs-lookup"><span data-stu-id="97c62-206">The reason and reason detail will be recorded in telemetry/environment monitoring.</span></span>

> [!NOTE]
> <span data-ttu-id="97c62-207">Après avoir exécuté les commandes, vous êtes invité à entrer **O** pour confirmer la réinitialisation de la base de données.</span><span class="sxs-lookup"><span data-stu-id="97c62-207">After you run the commands, you will be asked to enter **Y** to confirm that you want to reset the database.</span></span>

#### <a name="restart-services"></a><span data-ttu-id="97c62-208">Redémarrer les services</span><span class="sxs-lookup"><span data-stu-id="97c62-208">Restart services</span></span>

<span data-ttu-id="97c62-209">Utilisez services.msc pour redémarrer les services que vous avez arrêtés précédemment :</span><span class="sxs-lookup"><span data-stu-id="97c62-209">Use services.msc to restart the services that you stopped earlier:</span></span>

- <span data-ttu-id="97c62-210">Le service de publication World Wide Web (sur tous les ordinateurs AOS)</span><span class="sxs-lookup"><span data-stu-id="97c62-210">World wide web publishing service (on all AOS computers)</span></span>
- <span data-ttu-id="97c62-211">Service de gestion des traitements par lots Microsoft Dynamics 365 for Finance and Operations (sur les ordinateurs AOS non privés uniquement)</span><span class="sxs-lookup"><span data-stu-id="97c62-211">Microsoft Dynamics 365 for Finance and Operations Batch Management Service (on non-private AOS computers only)</span></span>
- <span data-ttu-id="97c62-212">Service de traitement Management Reporter 2012 (sur les ordinateurs BI uniquement)</span><span class="sxs-lookup"><span data-stu-id="97c62-212">Management Reporter 2012 Process Service (on BI computers only)</span></span>

#### <a name="import-report-definitions"></a><span data-ttu-id="97c62-213">Importer des définitions d'état</span><span class="sxs-lookup"><span data-stu-id="97c62-213">Import report definitions</span></span>

<span data-ttu-id="97c62-214">Importez vos conceptions d'états à partir du concepteur d'état à l'aide du fichier créé lors de l'exportation.</span><span class="sxs-lookup"><span data-stu-id="97c62-214">Import your report designs from Report designer by using the file that was created during the export.</span></span>

1. <span data-ttu-id="97c62-215">Dans le concepteur d'états, sélectionnez **Société** &gt; **Groupes de blocs élémentaires**.</span><span class="sxs-lookup"><span data-stu-id="97c62-215">In Report designer, select **Company** &gt; **Building Block Groups**.</span></span>
2. <span data-ttu-id="97c62-216">Sélectionnez le groupe de blocs élémentaires à exporter, puis sélectionnez **Exporter**.</span><span class="sxs-lookup"><span data-stu-id="97c62-216">Select the building block group to export, and then select **Export**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="97c62-217">Pour Finance and Operations, un seul groupe de blocs élémentaires est pris en charge, **Valeur par défaut**.</span><span class="sxs-lookup"><span data-stu-id="97c62-217">For Finance and Operations, only one building block group is supported, **Default**.</span></span>

3. <span data-ttu-id="97c62-218">Sélectionnez le bloc élémentaire **Valeur par défaut**, puis sélectionnez **Importer**.</span><span class="sxs-lookup"><span data-stu-id="97c62-218">Select the **Default** building block, and then select **Import**.</span></span>
4. <span data-ttu-id="97c62-219">Sélectionnez le fichier contenant les définitions d'état exportées, puis sélectionnez **Ouvrir**.</span><span class="sxs-lookup"><span data-stu-id="97c62-219">Select the file that contains the exported report definitions, and then select **Open**.</span></span>
5. <span data-ttu-id="97c62-220">Dans la boîte de dialogue **Importer**, sélectionnez les définitions de rapport à importer :</span><span class="sxs-lookup"><span data-stu-id="97c62-220">In the **Import** dialog box, select the report definitions to import:</span></span>

    - <span data-ttu-id="97c62-221">Pour importer toutes les définitions d'état et les blocs élémentaires associés, sélectionnez **Sélectionner tout**.</span><span class="sxs-lookup"><span data-stu-id="97c62-221">To import all the report definitions and the associated building blocks, select **Select All**.</span></span>
    - <span data-ttu-id="97c62-222">Pour importer uniquement certains rapports, certaines lignes, colonnes, arborescences ou certains ensembles de dimensions, sélectionnez les rapports, les lignes, les colonnes, les arborescences ou les ensembles de dimensions à importer.</span><span class="sxs-lookup"><span data-stu-id="97c62-222">To import specific reports, rows, columns, trees, or dimension sets, select the reports, rows, columns, trees, or dimension sets to import.</span></span>

6. <span data-ttu-id="97c62-223">Sélectionnez **Importer**.</span><span class="sxs-lookup"><span data-stu-id="97c62-223">Select **Import**.</span></span>

## <a name="reset-the-financial-reporting-data-mart-for-finance-and-operations-on-premises"></a><span data-ttu-id="97c62-224">Réinitialiser le mini-data warehouse d'états financiers pour Finance and Operations (local)</span><span class="sxs-lookup"><span data-stu-id="97c62-224">Reset the Financial reporting data mart for Finance and Operations (on-premises)</span></span>

1. <span data-ttu-id="97c62-225">Demandez à tous les utilisateurs de quitter le concepteur d'états et la zone États financiers de Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="97c62-225">Instruct all users to exit Report designer and the Financial reporting area of Finance and Operations.</span></span>
2. <span data-ttu-id="97c62-226">Exécutez le script suivant sur la base de données d'états financiers (MRDB).</span><span class="sxs-lookup"><span data-stu-id="97c62-226">Run the following script against the Financial reporting database (MRDB).</span></span>

    ```
    DECLARE @triggerIds table(id uniqueidentifier, taskTypeId uniqueidentifier)
    INSERT INTO @triggerIds SELECT tr.[Id], tt.[Id]
    FROM [Scheduling].[Task] t with(nolock)
    JOIN [Scheduling].[Trigger] tr ON t.[TriggerId] = tr.[Id]
    JOIN [Scheduling].[TaskState] ts ON ts.[TaskId] = t.[Id]
    LEFT JOIN [Scheduling].[TaskCategory] tc ON tc.[Id] = t.[CategoryId]
    JOIN [Scheduling].[TaskType] tt ON t.[TypeId] = tt.[Id]
    WHERE tt.[Id] IN ('D81C1197-D486-4FB7-AF8C-078C110893A0', '55D3F71A-2618-4EAE-9AA6-D48767B974D8') -- 'Maintenance Task', 'Map Task'
    PRINT 'Disable integration tasks'
    UPDATE [Scheduling].[Trigger] SET IsEnabled = 0 WHERE [Id] in (SELECT id FROM @triggerIds)
    ```

3. <span data-ttu-id="97c62-227">Tronquez ou supprimez tous les enregistrements de la table FINANCIALREPORTS dans la base de données Finance and Operations (AXDB).</span><span class="sxs-lookup"><span data-stu-id="97c62-227">Truncate or delete all records from the FINANCIALREPORTS table in the Finance and Operations database (AXDB).</span></span>
4. <span data-ttu-id="97c62-228">Tronquez ou supprimez tous les enregistrements de la table FINANCIALREPORTVERSION, si cette table existe dans la base de données Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="97c62-228">Truncate or delete all records from the FINANCIALREPORTVERSION table, if this table exists in the Finance and Operations database.</span></span> <span data-ttu-id="97c62-229">Si la table n'existe pas dans la base de données Finance and Operations, ignorez cette étape.</span><span class="sxs-lookup"><span data-stu-id="97c62-229">If the table doesn't exist in the Finance and Operations database, skip this step.</span></span>
5. <span data-ttu-id="97c62-230">Exécutez le script **ResetDatamart.sql** sur la base de données d'états financiers.</span><span class="sxs-lookup"><span data-stu-id="97c62-230">Run the **ResetDatamart.sql** script against the Financial reporting database.</span></span> <span data-ttu-id="97c62-231">Ce script désactive l'intégration du mini-data warehouse, supprime toutes les données du mini-data warehouse, puis réactive l'intégration du mini-data warehouse.</span><span class="sxs-lookup"><span data-stu-id="97c62-231">This script disables the data mart integration, deletes all the data mart data, and then reenables the data mart integration.</span></span>

    ```
    DECLARE @triggerIds table(id uniqueidentifier, taskTypeId uniqueidentifier)
    INSERT INTO @triggerIds SELECT tr.[Id], tt.[Id]
    FROM [Scheduling].[Task] t with(nolock)
    JOIN [Scheduling].[Trigger] tr ON t.[TriggerId] = tr.[Id]
    JOIN [Scheduling].[TaskState] ts ON ts.[TaskId] = t.[Id]
    LEFT JOIN [Scheduling].[TaskCategory] tc ON tc.[Id] = t.[CategoryId]
    JOIN [Scheduling].[TaskType] tt ON t.[TypeId] = tt.[Id]
    WHERE tt.[Id] IN ('D81C1197-D486-4FB7-AF8C-078C110893A0', '55D3F71A-2618-4EAE-9AA6-D48767B974D8') -- 'Maintenance Task', 'Map Task'
    PRINT 'Disable integration tasks'
    UPDATE [Scheduling].[Trigger] SET IsEnabled = 0 WHERE [Id] in (SELECT id FROM @triggerIds)
    ------------------------------
    PRINT 'Drop archive tables'
    ------------------------------
    DECLARE @tableId nvarchar(max)
    DECLARE dropCursor CURSOR LOCAL FAST_FORWARD FOR
    SELECT Id FROM [Datamart].Archive
    OPEN dropCursor
    FETCH NEXT FROM dropCursor INTO @tableId
    WHILE @@FETCH_STATUS = 0
    BEGIN
        IF EXISTS (SELECT 1 FROM INFORMATION_SCHEMA.TABLES t WHERE t.TABLE_NAME = 'FactStaging' + @tableId and t.TABLE_SCHEMA = 'Datamart')
        EXEC('DROP TABLE [Datamart].FactStaging' + @tableId)
        IF EXISTS (SELECT 1 FROM INFORMATION_SCHEMA.TABLES t WHERE t.TABLE_NAME = 'DimensionCombinationStaging' + @tableId and t.TABLE_SCHEMA = 'Datamart')
        EXEC('DROP TABLE [Datamart].DimensionCombinationStaging' + @tableId)
        FETCH NEXT FROM dropCursor INTO @tableId
    END
    CLOSE dropCursor
    DEALLOCATE dropCursor
    IF EXISTS (SELECT 1 FROM INFORMATION_SCHEMA.TABLES t WHERE t.TABLE_NAME = 'DimensionCombinationProcessing' and t.TABLE_SCHEMA = 'Datamart')
        EXEC('DROP TABLE [Datamart].DimensionCombinationProcessing')
    ------------------------------
    PRINT 'Begin Truncating tables'
    ------------------------------
    DECLARE @tablename nvarchar(200)
    DECLARE @schemaname nvarchar(200)
    DECLARE clear_tables CURSOR
        FOR SELECT TABLE_NAME, TABLE_SCHEMA FROM INFORMATION_SCHEMA.TABLES WHERE TABLE_SCHEMA = 'Datamart' AND TABLE_TYPE='BASE TABLE'
    PRINT 'remove check constraints'
    OPEN clear_tables
    FETCH NEXT FROM clear_tables INTO @tablename, @schemaname
    WHILE @@FETCH_STATUS = 0
    BEGIN
        IF @tablename <> 'VersionHistory'
        BEGIN
        EXEC('ALTER TABLE [' + @schemaname + '].[' + @tablename + '] NOCHECK CONSTRAINT ALL')
        END
        FETCH NEXT FROM clear_tables INTO @tablename, @schemaname
    END
    CLOSE clear_tables
    ------------------------------
    PRINT 'delete data from tables and rebuild indexes'
    ------------------------------
    OPEN clear_tables
    FETCH NEXT FROM clear_tables INTO @tablename, @schemaname
    WHILE @@FETCH_STATUS = 0
    BEGIN
        IF @tablename <> 'VersionHistory'
        BEGIN
            IF(EXISTS (select TOP 1 1 from sys.foreign_keys where referenced_object_id = OBJECT_ID(@schemaname + '.' + @tablename)) OR
            EXISTS(SELECT TOP 1 1 FROM sys.sql_expression_dependencies sed
            INNER JOIN sys.objects o ON sed.referencing_id = o.[object_id]
            WHERE o.[type] = 'V' 
            AND referenced_schema_name = @schemaname
            AND referenced_entity_name = @tablename))
            BEGIN
            PRINT 'deleting from ' + @tablename
            EXEC('DELETE FROM [' + @schemaname + '].[' + @tablename + ']')
            END
            ELSE
            BEGIN
            PRINT 'truncating from ' + @tablename
            EXEC('TRUNCATE TABLE [' + @schemaname + '].[' + @tablename + ']')
            END
        END
        EXEC('ALTER INDEX ALL ON [' + @schemaname + '].[' + @tablename + '] REBUILD')
        FETCH NEXT FROM clear_tables INTO @tablename, @schemaname
    END
    CLOSE clear_tables
    ------------------------------
    PRINT 'reenable check constraints'
    ------------------------------
    OPEN clear_tables
    FETCH NEXT FROM clear_tables INTO @tablename, @schemaname
    WHILE @@FETCH_STATUS = 0
    BEGIN
        IF @tablename <> 'VersionHistory'
        BEGIN
        EXEC('ALTER TABLE [' + @schemaname + '].[' + @tablename +'] WITH CHECK CHECK CONSTRAINT ALL')
        END
        FETCH NEXT FROM clear_tables INTO @tablename, @schemaname
    END
    CLOSE clear_tables
    DEALLOCATE clear_tables
    ------------------------------
    PRINT 'Complete Truncating tables'
    ------------------------------
    ------------------------------
    PRINT 'Remove indexes from DimensionCombination'
    ------------------------------
    DECLARE @indexname nvarchar(200)
    DECLARE drop_indexes CURSOR
    FOR SELECT Name FROM sys.indexes WHERE object_id = OBJECT_ID('[Datamart].[DimensionCombination]') AND is_primary_key = 0
    OPEN drop_indexes
    FETCH NEXT FROM drop_indexes INTO @indexname
    WHILE @@FETCH_STATUS = 0
    BEGIN
        EXEC('DROP INDEX [' + @indexname + '] on [Datamart].[DimensionCombination]')
        FETCH NEXT FROM drop_indexes INTO @indexname
    END
    CLOSE drop_indexes
    DEALLOCATE drop_indexes
    ------------------------------
    PRINT 'Drop Columns on DimensionCombination'
    ------------------------------
    DECLARE @objectname nvarchar(200)
    DECLARE drop_objects CURSOR
    FOR SELECT Name FROM sys.columns WHERE object_id = OBJECT_ID('[Datamart].[DimensionCombination]')
    OPEN drop_objects
    FETCH NEXT FROM drop_objects INTO @objectname
    WHILE @@FETCH_STATUS = 0
    BEGIN
        IF @objectname NOT IN ('Id', 'Description', 'SourceKey', 'OrganizationId', 'InactiveDimensions')
        BEGIN
        EXEC('ALTER TABLE [Datamart].[DimensionCombination] DROP COLUMN ' + @objectname)
        END
        FETCH NEXT FROM drop_objects INTO @objectname
    END
    CLOSE drop_objects
    DEALLOCATE drop_objects
    ------------------------------
    PRINT 'Drop Columns on DimensionCombinationResolving'
    ------------------------------
    DECLARE drop_objects CURSOR
    FOR SELECT Name FROM sys.columns WHERE object_id = OBJECT_ID('[Datamart].[DimensionCombinationResolving]')
    OPEN drop_objects
    FETCH NEXT FROM drop_objects INTO @objectname
    WHILE @@FETCH_STATUS = 0
    BEGIN
        IF @objectname NOT IN ('Id', 'Description', 'SourceKey', 'OrganizationId')
        BEGIN
        EXEC('ALTER TABLE [Datamart].[DimensionCombinationResolving] DROP COLUMN ' + @objectname)
        END
        FETCH NEXT FROM drop_objects INTO @objectname
    END
    CLOSE drop_objects
    DEALLOCATE drop_objects
    ------------------------------
    PRINT 'Drop Columns on DimensionCombinationStaging'
    ------------------------------
    DECLARE drop_objects CURSOR
    FOR SELECT Name FROM sys.columns WHERE object_id = OBJECT_ID('[Datamart].[DimensionCombinationStaging]')
    OPEN drop_objects
    FETCH NEXT FROM drop_objects INTO @objectname
    WHILE @@FETCH_STATUS = 0
    BEGIN
        IF @objectname NOT IN ('Id', 'OrganizationId', 'Description', 'SourceKey', 'OrganizationKey', 'FreshnessDate')
        BEGIN
        EXEC('ALTER TABLE [Datamart].[DimensionCombinationStaging] DROP COLUMN ' + @objectname)
        END
        FETCH NEXT FROM drop_objects INTO @objectname
    END
    CLOSE drop_objects
    DEALLOCATE drop_objects
    ------------------------------
    PRINT 'Drop Columns on DimensionCombinationUnreferenced'
    ------------------------------
    DECLARE drop_objects CURSOR
    FOR SELECT Name FROM sys.columns WHERE object_id = OBJECT_ID('[Datamart].[DimensionCombinationUnreferenced]')
    OPEN drop_objects
    FETCH NEXT FROM drop_objects INTO @objectname
    WHILE @@FETCH_STATUS = 0
    BEGIN
        IF @objectname NOT IN ('Id', 'Description', 'SourceKey', 'OrganizationId')
        BEGIN
        EXEC('ALTER TABLE [Datamart].[DimensionCombinationUnreferenced] DROP COLUMN ' + @objectname)
        END
        FETCH NEXT FROM drop_objects INTO @objectname
    END
    CLOSE drop_objects
    DEALLOCATE drop_objects
    ------------------------------
    PRINT 'Drop Columns on DimensionValueAttributeValue'
    ------------------------------
    DECLARE drop_objects CURSOR
    FOR SELECT Name FROM sys.columns WHERE object_id = OBJECT_ID('[Datamart].[DimensionValueAttributeValue]')
    OPEN drop_objects
    FETCH NEXT FROM drop_objects INTO @objectname
    WHILE @@FETCH_STATUS = 0
    BEGIN
        IF @objectname NOT IN ('DimensionValueId')
        BEGIN
        EXEC('ALTER TABLE [Datamart].[DimensionValueAttributeValue] DROP COLUMN ' + @objectname)
        END
        FETCH NEXT FROM drop_objects INTO @objectname
    END
    CLOSE drop_objects
    DEALLOCATE drop_objects
    ------------------------------
    PRINT 'Drop Columns on FactAttributeValue'
    ------------------------------
    DECLARE drop_objects CURSOR
    FOR SELECT Name FROM sys.columns WHERE object_id = OBJECT_ID('[Datamart].[FactAttributeValue]')
    OPEN drop_objects
    FETCH NEXT FROM drop_objects INTO @objectname
    WHILE @@FETCH_STATUS = 0
    BEGIN
        IF @objectname NOT IN ('FactId')
        BEGIN
        EXEC('ALTER TABLE [Datamart].[FactAttributeValue] DROP COLUMN ' + @objectname)
        END
        FETCH NEXT FROM drop_objects INTO @objectname
    END
    CLOSE drop_objects
    DEALLOCATE drop_objects
    ------------------------------
    PRINT 'Remove constraints from TranslatedPeriodBalance'
    ------------------------------
    DECLARE @name nvarchar(200)
    DECLARE drop_constraints CURSOR
    FOR SELECT Name FROM sys.default_constraints WHERE parent_object_id = OBJECT_ID('[Datamart].[TranslatedPeriodBalance]')
    OPEN drop_constraints
    FETCH NEXT FROM drop_constraints INTO @name
    WHILE @@FETCH_STATUS = 0
    BEGIN
        EXEC('ALTER TABLE [Datamart].[TranslatedPeriodBalance] DROP CONSTRAINT [' + @name + ']')
        FETCH NEXT FROM drop_constraints INTO @name
    END
    CLOSE drop_constraints
    DEALLOCATE drop_constraints
    ------------------------------
    PRINT 'Drop Columns on TranslatedPeriodBalance'
    ------------------------------
    DECLARE drop_objects CURSOR
    FOR SELECT Name FROM sys.columns WHERE object_id = OBJECT_ID('[Datamart].[TranslatedPeriodBalance]')
    OPEN drop_objects
    FETCH NEXT FROM drop_objects INTO @objectname
    WHILE @@FETCH_STATUS = 0
    BEGIN
        IF @objectname NOT IN ('PeriodId', 'DimensionsId', 'ScenarioId', 'FactType', 'PostingLayerId')
        BEGIN
        EXEC('ALTER TABLE [Datamart].[TranslatedPeriodBalance] DROP COLUMN ' + @objectname)
        END
        FETCH NEXT FROM drop_objects INTO @objectname
    END
    CLOSE drop_objects
    DEALLOCATE drop_objects
    ------------------------------
    PRINT 'Remove constraints from TranslatedPeriodBalanceChanges'
    ------------------------------
    DECLARE drop_constraints CURSOR
    FOR SELECT Name FROM sys.default_constraints WHERE parent_object_id = OBJECT_ID('[Datamart].[TranslatedPeriodBalanceChanges]')
    OPEN drop_constraints
    FETCH NEXT FROM drop_constraints INTO @name
    WHILE @@FETCH_STATUS = 0
    BEGIN
        EXEC('ALTER TABLE [Datamart].[TranslatedPeriodBalanceChanges] DROP CONSTRAINT [' + @name + ']')
        FETCH NEXT FROM drop_constraints INTO @name
    END
    CLOSE drop_constraints
    DEALLOCATE drop_constraints
    ------------------------------
    PRINT 'Drop Columns on TranslatedPeriodBalanceChanges'
    ------------------------------
    DECLARE drop_objects CURSOR
    FOR SELECT Name FROM sys.columns WHERE object_id = OBJECT_ID('[Datamart].[TranslatedPeriodBalanceChanges]')
    OPEN drop_objects
    FETCH NEXT FROM drop_objects INTO @objectname
    WHILE @@FETCH_STATUS = 0
    BEGIN
        IF @objectname NOT IN ('PeriodId', 'DimensionsId', 'ScenarioId', 'FactType', 'PostingLayerId')
        BEGIN
        EXEC('ALTER TABLE [Datamart].[TranslatedPeriodBalanceChanges] DROP COLUMN ' + @objectname)
        END
        FETCH NEXT FROM drop_objects INTO @objectname
    END
    CLOSE drop_objects
    DEALLOCATE drop_objects
    -- Rebuild dropped indexes that are dynamic
    EXEC [Datamart].ConfigureIndexesAndConstraints
    ------------------------------------------
    ------------------------------------------
    PRINT 'Reset the map tokens'
    UPDATE [Connector].[Map] SET InitalLoad = 0, ReaderToken=NULL, LastQuerySuccess='1900-01-01' WHERE MapId IN (SELECT t.[Id]
    FROM [Scheduling].[Task] t with(nolock)
    JOIN [Scheduling].[Trigger] tr ON t.[TriggerId] = tr.[Id]
    JOIN [Scheduling].[TaskState] ts ON ts.[TaskId] = t.[Id]
    LEFT JOIN [Scheduling].[TaskCategory] tc ON tc.[Id] = t.[CategoryId]
    JOIN [Scheduling].[TaskType] tt ON t.[TypeId] = tt.[Id]
    WHERE tt.[Id] = '55D3F71A-2618-4EAE-9AA6-D48767B974D8')
    PRINT 'Reset the tasks'
    UPDATE [Scheduling].[TaskState] SET StateType = 0, Progress = 0.0, LastRunTime = NULL, NextRunTime = NULL WHERE TaskId IN (SELECT ts.[TaskId]
    FROM [Scheduling].[Task] t with(nolock)
    JOIN [Scheduling].[Trigger] tr ON t.[TriggerId] = tr.[Id]
    JOIN [Scheduling].[TaskState] ts ON ts.[TaskId] = t.[Id]
    LEFT JOIN [Scheduling].[TaskCategory] tc ON tc.[Id] = t.[CategoryId]
    JOIN [Scheduling].[TaskType] tt ON t.[TypeId] = tt.[Id]
    WHERE tt.[Id] IN ('D81C1197-D486-4FB7-AF8C-078C110893A0', '55D3F71A-2618-4EAE-9AA6-D48767B974D8'))
    PRINT 'Enable integration tasks, RunImmediately'
    UPDATE [Scheduling].[Trigger] SET IsEnabled = 1, RunImmediately = 1, StartBoundary = '1900-01-01' 
    WHERE Id in (SELECT [id] from @triggerIds WHERE taskTypeId = '55D3F71A-2618-4EAE-9AA6-D48767B974D8')
    PRINT 'Enable the Maintenance Task'
    UPDATE [Scheduling].[Trigger] SET IsEnabled = 1, RunImmediately = 0, StartBoundary = GETDATE() WHERE Id in
    (SELECT [id] from @triggerIds WHERE taskTypeId = 'D81C1197-D486-4FB7-AF8C-078C110893A0')
    ------------------------------------------
    ------------------------------------------
    ```

6. <span data-ttu-id="97c62-232">Après la réinitialisation, vous pouvez vérifier manuellement le rechargement des données en exécutant la requête suivante sur la base de données d'états financiers.</span><span class="sxs-lookup"><span data-stu-id="97c62-232">After the reset, you can manually verify the data reload by running the following query against the Financial reporting database.</span></span>

    ```
    select ReaderObjectName, WriterObjectName, LastRunTime, StateType from Connector.MapsWithDetail with (nolock)
    ```

    <span data-ttu-id="97c62-233">Confirmez que toutes les lignes ont une valeur **LastRunTime** et que **StateType** est défini sur **5**.</span><span class="sxs-lookup"><span data-stu-id="97c62-233">Confirm that all rows have a **LastRunTime** value, and that **StateType** is set to **5**.</span></span> <span data-ttu-id="97c62-234">La valeur **StateType** **5** indique que les données ont bien été rechargées.</span><span class="sxs-lookup"><span data-stu-id="97c62-234">A **StateType** value of **5** indicates that the data was successfully reloaded.</span></span> <span data-ttu-id="97c62-235">La valeur **7** indique un état d'erreur.</span><span class="sxs-lookup"><span data-stu-id="97c62-235">A value of **7** indicates a faulted state.</span></span> <span data-ttu-id="97c62-236">Parfois, la carte Hiérarchie d'organisation présente cet état lorsqu'elle s'exécute pour la première fois.</span><span class="sxs-lookup"><span data-stu-id="97c62-236">Sometimes, the Organization Hierarchy map has this state the first time that it runs.</span></span> <span data-ttu-id="97c62-237">Toutefois, l'état d'erreur doit être automatiquement résolu.</span><span class="sxs-lookup"><span data-stu-id="97c62-237">However, the faulted state but should be automatically resolved.</span></span>

