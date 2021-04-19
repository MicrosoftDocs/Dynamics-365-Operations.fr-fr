---
title: Archiver les mouvements de stock
description: Cette rubrique décrit comment archiver les données de transaction d’inventaire pour améliorer les performances du système.
author: sherry-zheng
ms.date: 03/01/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventTransArchiveProcessForm
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2021-03-01
ms.dyn365.ops.version: Release 10.0.18
ms.openlocfilehash: bacc27c1a9066892c51110d28ba9a2ad26bebe77
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5839293"
---
# <a name="archive-inventory-transactions"></a><span data-ttu-id="f8ddd-103">Archiver les mouvements de stock</span><span class="sxs-lookup"><span data-stu-id="f8ddd-103">Archive inventory transactions</span></span>

[!include [banner](../../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

<span data-ttu-id="f8ddd-104">Au fil du temps, le tableau des transactions d’inventaire (`InventTrans`) continuera de croître et de consommer plus d’espace de base de données.</span><span class="sxs-lookup"><span data-stu-id="f8ddd-104">Over time, the inventory transactions table (`InventTrans`) will continue to grow and consume more database space.</span></span> <span data-ttu-id="f8ddd-105">Par conséquent, les requêtes effectuées sur la table deviendront progressivement plus lentes.</span><span class="sxs-lookup"><span data-stu-id="f8ddd-105">Therefore, queries that are made against the table will gradually become slower.</span></span> <span data-ttu-id="f8ddd-106">Cette rubrique décrit comment utiliser la fonctionnalité *Archivage des transactions d’inventaire* pour archiver les données sur les transactions d’inventaire afin d’améliorer les performances du système.</span><span class="sxs-lookup"><span data-stu-id="f8ddd-106">This topic describes how you can use the *Inventory transactions archive* feature to archive data about inventory transactions to help improve system performance.</span></span>

> [!NOTE]
> <span data-ttu-id="f8ddd-107">Seules les transactions de stock mises à jour financièrement peuvent être archivées dans une période comptable fermée sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="f8ddd-107">Only financially updated inventory transactions can be archived in a selected closed ledger period.</span></span> <span data-ttu-id="f8ddd-108">Pour être archivées, les mouvements de stock sortants mis à jour financièrement doivent avoir un statut de sortie de *Vendu*, et les transactions d’inventaire entrantes doivent avoir un statut de réception de *Acheté*.</span><span class="sxs-lookup"><span data-stu-id="f8ddd-108">To be archived, financially updated outbound inventory transactions must have an issue status of *Sold*, and inbound inventory transactions must have a receipt status of *Purchased*.</span></span>

<span data-ttu-id="f8ddd-109">Lorsque vous archivez des transactions d’inventaire, toutes les transactions associées sont déplacées vers la table `InventTransArchive`.</span><span class="sxs-lookup"><span data-stu-id="f8ddd-109">When you archive inventory transactions, all related transactions are moved to the `InventTransArchive` table.</span></span> <span data-ttu-id="f8ddd-110">Les transactions de sortie de stock et les transactions de réception de stock sont archivées séparément, en fonction de la combinaison de l’ID article (`itemId`) et l’ID de la dimension d’inventaire (`inventDimId`), et ils sont placés dans le numéro récapitulé et dans les transactions de réception récapitulées.</span><span class="sxs-lookup"><span data-stu-id="f8ddd-110">Inventory issue transactions and inventory receipt transactions are archived separately, based on the combination of the item ID (`itemId`) and inventory dimension ID (`inventDimId`), and they are put into the summarized issue and summarized receipt transactions.</span></span>

<span data-ttu-id="f8ddd-111">Si une combinaison de `itemId` et de `inventDimId` ne contient qu’une seule transaction de réception ou de sortie, la transaction ne sera pas archivée.</span><span class="sxs-lookup"><span data-stu-id="f8ddd-111">If an `itemId` and `inventDimId` combination contains only one receipt or issue transaction, the transaction won't be archived.</span></span>

## <a name="turn-on-the-feature-in-your-system"></a><span data-ttu-id="f8ddd-112">Activez la fonctionnalité dans votre système</span><span class="sxs-lookup"><span data-stu-id="f8ddd-112">Turn on the feature in your system</span></span>

<span data-ttu-id="f8ddd-113">Si votre système n’inclut pas déjà les fonctionnalités décrites dans cette rubrique, accédez à [Gestion des fonctionnalités](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) et activez la fonctionnalité *Archivage des transactions d’inventaire*.</span><span class="sxs-lookup"><span data-stu-id="f8ddd-113">If your system doesn't already include the features that is described in this topic, go to [Feature management](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md), and turn on the *Inventory transactions archive* feature.</span></span>

## <a name="things-to-consider-before-you-archive-inventory-transactions"></a><span data-ttu-id="f8ddd-114">Éléments à prendre en compte avant d’archiver les transactions d’inventaire</span><span class="sxs-lookup"><span data-stu-id="f8ddd-114">Things to consider before you archive inventory transactions</span></span>

<span data-ttu-id="f8ddd-115">Avant d’archiver les transactions d’inventaire, vous devez envisager les scénarios commerciaux suivants, car ils seront affectés par l’opération :</span><span class="sxs-lookup"><span data-stu-id="f8ddd-115">Before you archive inventory transactions, you should consider the following business scenarios, because they will be affected by the operation:</span></span>

- <span data-ttu-id="f8ddd-116">Lorsque vous auditez des transactions d’inventaire à partir de documents associés, tels que des lignes de commande fournisseur, elles sont affichées comme archivées.</span><span class="sxs-lookup"><span data-stu-id="f8ddd-116">When you audit inventory transactions from related documents, such as purchase order lines, they will be shown as archived.</span></span> <span data-ttu-id="f8ddd-117">Pour consulter les transactions archivées, vous devez aller à **Gestion de l’inventaire \> Tâches périodiques \> Nettoyer \> Archive des transactions d’inventaire**.</span><span class="sxs-lookup"><span data-stu-id="f8ddd-117">To review the archived transactions, you must go to **Inventory management \> Periodic tasks \> Clean up \> Inventory transactions archive**.</span></span>
- <span data-ttu-id="f8ddd-118">La clôture de l’inventaire ne peut pas être annulée pour les périodes archivées.</span><span class="sxs-lookup"><span data-stu-id="f8ddd-118">Inventory closing can't be canceled for archived periods.</span></span> <span data-ttu-id="f8ddd-119">Avant de pouvoir annuler une clôture de stock, vous devez contrepasser l’archive des mouvements de stock pour la période concernée.</span><span class="sxs-lookup"><span data-stu-id="f8ddd-119">Before you can cancel an inventory closing, you must reverse the inventory transaction archive for the relevant period.</span></span>
- <span data-ttu-id="f8ddd-120">La conversion des coûts standard ne peut pas être effectuée pour les périodes archivées.</span><span class="sxs-lookup"><span data-stu-id="f8ddd-120">Standard cost conversion can't be done for archived periods.</span></span> <span data-ttu-id="f8ddd-121">Avant de pouvoir effectuer une conversion de coût standard, vous devez contrepasser l’archive des mouvements de stock pour la période concernée.</span><span class="sxs-lookup"><span data-stu-id="f8ddd-121">Before you can do standard cost conversion, you must reverse the inventory transaction archive for the relevant period.</span></span>
- <span data-ttu-id="f8ddd-122">Les rapports d’inventaire issus des transactions d’inventaire seront affectés lorsque vous archiverez les transactions d’inventaire.</span><span class="sxs-lookup"><span data-stu-id="f8ddd-122">Inventory reports that are sourced from inventory transactions will be affected when you archive inventory transactions.</span></span> <span data-ttu-id="f8ddd-123">Ces rapports comprennent le rapport sur le vieillissement des stocks et les rapports sur la valeur des stocks.</span><span class="sxs-lookup"><span data-stu-id="f8ddd-123">These reports include the inventory aging report and inventory value reports.</span></span>
- <span data-ttu-id="f8ddd-124">Les prévisions d’inventaire peuvent être affectées si elles sont exécutées pendant l’horizon temporel des périodes archivées.</span><span class="sxs-lookup"><span data-stu-id="f8ddd-124">Inventory forecasts might be affected if they are run during the time horizon of archived periods.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="f8ddd-125">Conditions préalables</span><span class="sxs-lookup"><span data-stu-id="f8ddd-125">Prerequisites</span></span>

<span data-ttu-id="f8ddd-126">Les transactions de stock ne peuvent être archivées que pendant les périodes où les conditions suivantes sont remplies :</span><span class="sxs-lookup"><span data-stu-id="f8ddd-126">Inventory transactions can be archived only during periods where the following conditions are met:</span></span>

- <span data-ttu-id="f8ddd-127">La période comptable doit être clôturée.</span><span class="sxs-lookup"><span data-stu-id="f8ddd-127">The ledger period must be closed.</span></span>
- <span data-ttu-id="f8ddd-128">La clôture de l’inventaire doit être exécutée à la date de fin de période de l’archive ou après cette date.</span><span class="sxs-lookup"><span data-stu-id="f8ddd-128">Inventory closing must be run on or after the to-period date of the archive.</span></span>
- <span data-ttu-id="f8ddd-129">La période doit être au moins un an avant la date de la période de début de l’archive.</span><span class="sxs-lookup"><span data-stu-id="f8ddd-129">The period must be at least one year before the from-period date of the archive.</span></span>
- <span data-ttu-id="f8ddd-130">Il ne doit y avoir aucun recalcul d’inventaire existant.</span><span class="sxs-lookup"><span data-stu-id="f8ddd-130">There must not be any existing inventory recalculations.</span></span>

## <a name="archive-inventory-transactions"></a><span data-ttu-id="f8ddd-131">Archiver les mouvements de stock</span><span class="sxs-lookup"><span data-stu-id="f8ddd-131">Archive inventory transactions</span></span>

<span data-ttu-id="f8ddd-132">Pour archiver les transactions de stock, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="f8ddd-132">To archive inventory transactions, follow these steps.</span></span>

1. <span data-ttu-id="f8ddd-133">Aller à **Gestion des stocks** \> **Tâches périodiques** \> **Nettoyer** \> **Archive des transactions d’inventaire**.</span><span class="sxs-lookup"><span data-stu-id="f8ddd-133">Go to **Inventory management** \> **Periodic tasks** \> **Clean up** \> **Inventory transaction archive**.</span></span>

    <span data-ttu-id="f8ddd-134">La page **Archive des transactions d’inventaire** apparaît et affiche une liste des enregistrements de processus archivés.</span><span class="sxs-lookup"><span data-stu-id="f8ddd-134">The **Inventory transactions archive** page appears and shows a list of archived process records.</span></span>

    <span data-ttu-id="f8ddd-135">![Page Archive des transactions de stock](media/archive-inventory-empty.png "Page Archive des transactions de stock")</span><span class="sxs-lookup"><span data-stu-id="f8ddd-135">![Inventory transactions archive page](media/archive-inventory-empty.png "Inventory transactions archive page")</span></span>

1. <span data-ttu-id="f8ddd-136">Dans le volet Actions, sélectionnez **Archive des transactions d’inventaire** pour créer une archive de transactions d’inventaire.</span><span class="sxs-lookup"><span data-stu-id="f8ddd-136">On the Action Pane, select **Inventory transactions archive** to create an inventory transaction archive.</span></span>
1. <span data-ttu-id="f8ddd-137">Dans la boîte de dialogue **Archive des transactions d’inventaire**, sur le raccourci **Paramètres**, définissez les champs suivants :</span><span class="sxs-lookup"><span data-stu-id="f8ddd-137">In the **Inventory transactions archive** dialog box, on the **Parameters** FastTab, set the following fields:</span></span>

    - <span data-ttu-id="f8ddd-138">**De la date dans la période comptable fermée** – Sélectionnez la date de transaction la plus récente à inclure dans l’archive.</span><span class="sxs-lookup"><span data-stu-id="f8ddd-138">**From date in closed ledger period** – Select the earliest transaction date to include in the archive.</span></span>
    - <span data-ttu-id="f8ddd-139">**À la date dans la période comptable fermée** – Sélectionnez la date de transaction la plus ancienne à inclure dans l’archive.</span><span class="sxs-lookup"><span data-stu-id="f8ddd-139">**To date in closed ledger period** – Select the latest transaction date to include in the archive.</span></span>

    <span data-ttu-id="f8ddd-140">![Boîte de dialogue Archive des transactions de stock](media/archive-inventory-dates.png "Boîte de dialogue Archive des transactions de stock")</span><span class="sxs-lookup"><span data-stu-id="f8ddd-140">![Inventory transactions archive dialog box](media/archive-inventory-dates.png "Inventory transactions archive dialog box")</span></span>

    > [!NOTE]
    > <span data-ttu-id="f8ddd-141">Seules les périodes qui respectent les [conditions préalables](#prerequisites) sera disponible pour la sélection.</span><span class="sxs-lookup"><span data-stu-id="f8ddd-141">Only periods that meet the [prerequisites](#prerequisites) will be available for selection.</span></span>

1. <span data-ttu-id="f8ddd-142">Sur le raccourci **Exécuter en arrière-plan**, configurez les détails du traitement par lots selon vos besoins.</span><span class="sxs-lookup"><span data-stu-id="f8ddd-142">On the **Run in the background** FastTab, set up batch processing details as you require.</span></span> <span data-ttu-id="f8ddd-143">Suivez les étapes habituelles pour les travaux par lots dans Microsoft Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="f8ddd-143">Follow the usual steps for batch jobs in Microsoft Dynamics 365 Supply Chain Management.</span></span>
1. <span data-ttu-id="f8ddd-144">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="f8ddd-144">Select **OK**.</span></span>
1. <span data-ttu-id="f8ddd-145">Vous recevez un message qui vous invite à confirmer que vous souhaitez continuer.</span><span class="sxs-lookup"><span data-stu-id="f8ddd-145">You receive a message that prompts you to confirm that you want to continue.</span></span> <span data-ttu-id="f8ddd-146">Lisez attentivement le message, puis sélectionnez **Oui** pour continuer.</span><span class="sxs-lookup"><span data-stu-id="f8ddd-146">Read the message carefully, and then select **Yes** if you want to continue.</span></span>

    <span data-ttu-id="f8ddd-147">Vous recevez un message indiquant que votre travail d’archivage des transactions d’inventaire a été ajouté à la file d’attente par lots.</span><span class="sxs-lookup"><span data-stu-id="f8ddd-147">You receive a message that states that your inventory transactions archive job has been added to the batch queue.</span></span> <span data-ttu-id="f8ddd-148">Le travail commencera maintenant à archiver les transactions d’inventaire de la période sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="f8ddd-148">The job will now start to archive inventory transactions from the selected period.</span></span>

## <a name="view-archived-inventory-transactions"></a><span data-ttu-id="f8ddd-149">Afficher les transactions de stock archivées</span><span class="sxs-lookup"><span data-stu-id="f8ddd-149">View archived inventory transactions</span></span>

<span data-ttu-id="f8ddd-150">La page **Archive des transactions d’inventaire** affiche votre historique d’archivage complet.</span><span class="sxs-lookup"><span data-stu-id="f8ddd-150">The **Inventory transactions archive** page shows your full archiving history.</span></span> <span data-ttu-id="f8ddd-151">Chaque ligne de la grille affiche des informations telles que la date de création de l’archive, l’utilisateur qui l’a créée et son statut.</span><span class="sxs-lookup"><span data-stu-id="f8ddd-151">Each row in the grid shows information such as the date when the archive was created, the user who created it, and its status.</span></span>

<span data-ttu-id="f8ddd-152">![Page Historique de l’archivage des transactions d’inventaire](media/archive-inventory-full.png "Page Historique de l’archivage des transactions d’inventaire")</span><span class="sxs-lookup"><span data-stu-id="f8ddd-152">![Archiving history on the Inventory transactions archive page](media/archive-inventory-full.png "Archiving history on the Inventory transactions archive page")</span></span>

<span data-ttu-id="f8ddd-153">Dans la liste déroulante en haut de la page, sélectionnez l’une des valeurs suivantes pour filtrer les archives affichées dans la grille :</span><span class="sxs-lookup"><span data-stu-id="f8ddd-153">In the drop-down list at the top of the page select one of the following values to filter the archives that are shown in the grid:</span></span>

- <span data-ttu-id="f8ddd-154">**Actif** – Afficher uniquement les archives actives, pas les archives inversées.</span><span class="sxs-lookup"><span data-stu-id="f8ddd-154">**Active** – Show only active archives, not reversed archives.</span></span>
- <span data-ttu-id="f8ddd-155">**Tout** – Afficher toutes les archives, actives et inversées.</span><span class="sxs-lookup"><span data-stu-id="f8ddd-155">**All** – Show all archives, both active and reversed.</span></span>

<span data-ttu-id="f8ddd-156">Pour chaque archive de la grille, les informations suivantes sont fournies :</span><span class="sxs-lookup"><span data-stu-id="f8ddd-156">For each archive in the grid, the following information is provided:</span></span>

- <span data-ttu-id="f8ddd-157">**Actif** – Une coche indique que l’archive est active.</span><span class="sxs-lookup"><span data-stu-id="f8ddd-157">**Active** – A check mark indicates that the archive is active.</span></span>
- <span data-ttu-id="f8ddd-158">**Date de début** – La date de la transaction la plus ancienne pouvant être incluse dans l’archive.</span><span class="sxs-lookup"><span data-stu-id="f8ddd-158">**From date** – The date of the oldest transaction that can be included in the archive.</span></span>
- <span data-ttu-id="f8ddd-159">**Date de fin** – La date de la transaction la plus récente pouvant être incluse dans l’archive.</span><span class="sxs-lookup"><span data-stu-id="f8ddd-159">**To date** – The date of the latest transaction that can be included in the archive.</span></span>
- <span data-ttu-id="f8ddd-160">**Programmé par** – Le compte utilisateur qui a créé l’archive.</span><span class="sxs-lookup"><span data-stu-id="f8ddd-160">**Scheduled by** – The user account that created the archive.</span></span>
- <span data-ttu-id="f8ddd-161">**Exécuté** – Date de création de l’archive.</span><span class="sxs-lookup"><span data-stu-id="f8ddd-161">**Executed** – The date when the archive was created.</span></span>
- <span data-ttu-id="f8ddd-162">**Annuler** – Une coche indique que l’archive a été annulée.</span><span class="sxs-lookup"><span data-stu-id="f8ddd-162">**Reverse** – A check mark indicates that the archive has been reversed.</span></span>
- <span data-ttu-id="f8ddd-163">**Arrêter la mise à jour actuelle** – Une coche indique que l’archive est en cours, mais qu’elle a été suspendue.</span><span class="sxs-lookup"><span data-stu-id="f8ddd-163">**Stop current update** – A check mark indicates that the archive is in progress, but it has been paused.</span></span>
- <span data-ttu-id="f8ddd-164">**État** – Le statut de traitement de l’archive.</span><span class="sxs-lookup"><span data-stu-id="f8ddd-164">**State** – The processing status of the archive.</span></span> <span data-ttu-id="f8ddd-165">Les valeurs possibles sont *Attente*, *En cours*, et *Terminé*.</span><span class="sxs-lookup"><span data-stu-id="f8ddd-165">The possible values are *Waiting*, *In progress*, and *Finished*.</span></span>

<span data-ttu-id="f8ddd-166">La barre d’outils au-dessus de la grille fournit les boutons suivants que vous pouvez utiliser pour travailler avec une archive sélectionnée :</span><span class="sxs-lookup"><span data-stu-id="f8ddd-166">The toolbar above the grid provides the following buttons that you can use to work with a selected archive:</span></span>

- <span data-ttu-id="f8ddd-167">**Transactions archivées** – Afficher les détails complets de l’archive sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="f8ddd-167">**Archived transactions** – View the full details of the selected archive.</span></span> <span data-ttu-id="f8ddd-168">La page **Transactions archivées** qui apparaît montre toutes les transactions dans l’archive.</span><span class="sxs-lookup"><span data-stu-id="f8ddd-168">The **Archived transactions** page that appears shows all the transactions in the archive.</span></span>

    <span data-ttu-id="f8ddd-169">![Page des transactions archivées](media/archive-inventory-transactions.png "Page des transactions archivées")</span><span class="sxs-lookup"><span data-stu-id="f8ddd-169">![Archived transactions page](media/archive-inventory-transactions.png "Archived transactions page")</span></span>

    <span data-ttu-id="f8ddd-170">Pour afficher plus d’informations sur une transaction spécifique sur la page **Transactions archivées**, sélectionnez-le dans la grille, puis, dans le volet Actions, sélectionnez **Détails de la transaction archivée**.</span><span class="sxs-lookup"><span data-stu-id="f8ddd-170">To view more information about a specific transaction on the **Archived transactions** page, select it in the grid, and then, on the Action Pane, select **Archived transaction details**.</span></span> <span data-ttu-id="f8ddd-171">La page **Détails de la transaction archivés** qui apparaît affiche des informations telles que l’écriture comptable, les références de comptabilité auxiliaire associées et les dimensions financières.</span><span class="sxs-lookup"><span data-stu-id="f8ddd-171">The **Archived transaction details** page that appears shows information such as the ledger posting, related subledger references, and financial dimensions.</span></span>

- <span data-ttu-id="f8ddd-172">**Suspendre l’archivage** – Suspend une archive sélectionnée en cours de traitement.</span><span class="sxs-lookup"><span data-stu-id="f8ddd-172">**Pause archiving** – Pause a selected archive that is currently being processed.</span></span> <span data-ttu-id="f8ddd-173">La pause prend effet uniquement après la génération de la tâche d’archivage.</span><span class="sxs-lookup"><span data-stu-id="f8ddd-173">The pause takes effect only after the archiving task has been generated.</span></span> <span data-ttu-id="f8ddd-174">Par conséquent, il peut y avoir un court délai avant que la pause ne prenne effet.</span><span class="sxs-lookup"><span data-stu-id="f8ddd-174">Therefore, there might be a short delay before the pause takes effect.</span></span> <span data-ttu-id="f8ddd-175">Si une archive a été mise en pause, une coche apparaît dans son champ **Arrêter la mise à jour actuelle**.</span><span class="sxs-lookup"><span data-stu-id="f8ddd-175">If an archive has been paused, a check mark appears in its **Stop current update** field.</span></span>
- <span data-ttu-id="f8ddd-176">**Reprendre l’archivage** – Reprendre le traitement d’une archive sélectionnée en cours de suspension.</span><span class="sxs-lookup"><span data-stu-id="f8ddd-176">**Resume archiving** – Resume processing for a selected archive that is currently paused.</span></span>
- <span data-ttu-id="f8ddd-177">**Annuler** – Annulez l’archive sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="f8ddd-177">**Reverse** – Reverse the selected archive.</span></span> <span data-ttu-id="f8ddd-178">Vous ne pouvez annuler une archive que si son champ **État** est défini sur *Terminé*.</span><span class="sxs-lookup"><span data-stu-id="f8ddd-178">You can reverse an archive only if its **State** field is set to *Finished*.</span></span> <span data-ttu-id="f8ddd-179">Si une archive a été annulée, une coche apparaît dans son champ **Annuler**.</span><span class="sxs-lookup"><span data-stu-id="f8ddd-179">If an archive has been reversed, a check mark appears in its **Reverse** field.</span></span>