---
title: Résoudre les problèmes des opérations d’inventaire
description: Cette rubrique décrit comment résoudre les problèmes que vous pourriez rencontrer lors de l’utilisation des opérations d’inventaire.
author: sherry-zheng
manager: tfehr
ms.date: 12/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2020-12-03
ms.dyn365.ops.version: Release 10.0.16
ms.openlocfilehash: 3a22229106753d265a90f0ef05f5ac82dc745bbd
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4967153"
---
# <a name="troubleshoot-inventory-operations"></a><span data-ttu-id="20efd-103">Résoudre les problèmes des opérations d’inventaire</span><span class="sxs-lookup"><span data-stu-id="20efd-103">Troubleshoot inventory operations</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="20efd-104">Cette rubrique décrit comment résoudre les problèmes que vous pourriez rencontrer lors de l’utilisation des opérations d’inventaire.</span><span class="sxs-lookup"><span data-stu-id="20efd-104">This topic describes how to fix issues that you might encounter while you work with inventory operations.</span></span>

## <a name="i-cant-find-the-workflow-drop-down-dialog-box-for-inventory-journals"></a><span data-ttu-id="20efd-105">Je ne trouve pas la boîte de dialogue déroulante « Workflow » pour les journaux d’inventaire.</span><span class="sxs-lookup"><span data-stu-id="20efd-105">I can't find the "Workflow" drop-down dialog box for inventory journals.</span></span>

### <a name="issue-description"></a><span data-ttu-id="20efd-106">Description du problème</span><span class="sxs-lookup"><span data-stu-id="20efd-106">Issue description</span></span>

<span data-ttu-id="20efd-107">Vous ne trouvez pas la boîte de dialogue déroulante **Workflow** sur la page du journal, ou les opérations de workflow associées ne sont pas disponibles.</span><span class="sxs-lookup"><span data-stu-id="20efd-107">You can't find the **Workflow** drop-down dialog box on the journal page, or related workflow operations aren't available.</span></span>

<span data-ttu-id="20efd-108">Ce problème peut se produire pour trois raisons, comme décrit dans les sous-sections suivantes.</span><span class="sxs-lookup"><span data-stu-id="20efd-108">This issue can occur for three reasons, as described in the following subsections.</span></span>

### <a name="issue-resolution-1"></a><span data-ttu-id="20efd-109">Résolution du problème 1</span><span class="sxs-lookup"><span data-stu-id="20efd-109">Issue resolution 1</span></span>

<span data-ttu-id="20efd-110">Si le problème s’applique à tous les utilisateurs, il peut se produire car le workflow d’approbation n’a pas été attribué au nom du journal.</span><span class="sxs-lookup"><span data-stu-id="20efd-110">If the issue applies to all users, it might be occurring because the approval workflow hasn't been assigned to the journal name.</span></span> <span data-ttu-id="20efd-111">Pour régler le problème, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="20efd-111">To fix the issue, follow these steps.</span></span>

1. <span data-ttu-id="20efd-112">Allez dans **Gestion des stocks &gt; Paramétrage &gt; Noms de journal &gt; Inventaire**.</span><span class="sxs-lookup"><span data-stu-id="20efd-112">Go to **Inventory Management &gt; Setup &gt; Journal names &gt; Inventory**.</span></span>
1. <span data-ttu-id="20efd-113">Dans le volet de liste, sélectionnez un nom de journal pour ouvrir ses paramètres.</span><span class="sxs-lookup"><span data-stu-id="20efd-113">In the list pane, select a journal name to open its settings.</span></span>
1. <span data-ttu-id="20efd-114">Dans le raccourci **Général**, définissez l’option **Workflow d’approbation** sur *Oui*.</span><span class="sxs-lookup"><span data-stu-id="20efd-114">On the **General** FastTab, set the **Approval workflow** option to *Yes*.</span></span> <span data-ttu-id="20efd-115">Si vous êtes invité à confirmer la modification, sélectionnez **Oui**.</span><span class="sxs-lookup"><span data-stu-id="20efd-115">If you're prompted to confirm the change, select **Yes**.</span></span>
1. <span data-ttu-id="20efd-116">Dans le champ **Workflow**, sélectionnez le workflow que vous souhaitez utiliser pour le nom de journal sélectionné.</span><span class="sxs-lookup"><span data-stu-id="20efd-116">In the **Workflow** field, select the workflow that you want to use for the selected journal name.</span></span>

### <a name="issue-resolution-2"></a><span data-ttu-id="20efd-117">Résolution du problème 2</span><span class="sxs-lookup"><span data-stu-id="20efd-117">Issue resolution 2</span></span>

<span data-ttu-id="20efd-118">Si votre workflow utilise un code personnalisé, des problèmes peuvent se produire après la mise à niveau du système.</span><span class="sxs-lookup"><span data-stu-id="20efd-118">If your workflow uses customized code, issues might occur after you upgrade the system.</span></span> <span data-ttu-id="20efd-119">Par exemple, dans le workflow du journal, le bouton **Envoyer** peut être grisé, vous ne pouvez donc pas le sélectionner pour approuver un envoi.</span><span class="sxs-lookup"><span data-stu-id="20efd-119">For example, in the journal workflow, the **Submit** button might be grayed out so you can't select it to approve a submission.</span></span>

<span data-ttu-id="20efd-120">Si le bouton **Envoyer** est grisé, votre workflow a peut-être été personnalisé, ce qui signifie que la méthode du workflow, `canSubmitToWorkflow()` dans `FormDataUtil`, a été étendue.</span><span class="sxs-lookup"><span data-stu-id="20efd-120">If the **Submit** button is grayed out, your workflow might have been customized, which means the method of the workflow, `canSubmitToWorkflow()` in `FormDataUtil`, has been extended.</span></span> <span data-ttu-id="20efd-121">Pour résoudre ce problème, modifiez la façon dont vous étendez la méthode de `canSubmitToWorkflow()` pour utiliser la structure dans l’exemple suivant.</span><span class="sxs-lookup"><span data-stu-id="20efd-121">To fix this issue, change the way that you extend the method of the `canSubmitToWorkflow()` to use the structure in the following example.</span></span>

```xpp
[ExtensionOf(formStr(InventJournalMovement))]
public final class InventJournalMovement_extension
{
    public boolean canSubmitToWorkflow()
    {
        boolean ret = YourLogicOfCanSubmitToWorkflow();

        return ret;
    }
}
```

### <a name="issue-resolution-3"></a><span data-ttu-id="20efd-122">Résolution du problème 3</span><span class="sxs-lookup"><span data-stu-id="20efd-122">Issue resolution 3</span></span>

<span data-ttu-id="20efd-123">Si le problème ne s’applique qu'à quelques utilisateurs spécifiques, ces utilisateurs peuvent ne pas disposer des privilèges de sécurité nécessaires pour exécuter des opérations de workflow sur les journaux d’inventaire.</span><span class="sxs-lookup"><span data-stu-id="20efd-123">If the issue applies only to a few specific users, those users might not have the security privileges that are required to run workflow operations on inventory journals.</span></span> <span data-ttu-id="20efd-124">Vérifiez que chaque utilisateur affecté dispose du privilège de sécurité *Tenir à jour le workflow du journal d’inventaire*.</span><span class="sxs-lookup"><span data-stu-id="20efd-124">Verify that each affected user has the *Maintain inventory journal workflow* security privilege.</span></span> <span data-ttu-id="20efd-125">Par défaut, ce privilège est attribué à un droit qui porte le même nom, et ce droit est appliqué aux rôles *Magasinier* et *Gestionnaire de l’entrepôt*.</span><span class="sxs-lookup"><span data-stu-id="20efd-125">By default, this privilege is assigned to a duty that has same name, and that duty is applied to the *Warehouse worker* and *Warehouse manager* roles.</span></span>

## <a name="my-inventory-journal-remains-in-system-locked-status-and-the-workflow-batch-job-doesnt-work"></a><span data-ttu-id="20efd-126">Mon journal d’inventaire reste à l’état verrouillé par le système, et la tâche de traitement par lots du workflow ne fonctionne pas.</span><span class="sxs-lookup"><span data-stu-id="20efd-126">My inventory journal remains in system-locked status, and the workflow batch job doesn't work.</span></span>

### <a name="issue-description"></a><span data-ttu-id="20efd-127">Description du problème</span><span class="sxs-lookup"><span data-stu-id="20efd-127">Issue description</span></span>

<span data-ttu-id="20efd-128">L’un de vos journaux d’inventaire est verrouillé par une opération et n’est pas lancé.</span><span class="sxs-lookup"><span data-stu-id="20efd-128">One of your inventory journals is locked by some operation and isn't being released.</span></span> <span data-ttu-id="20efd-129">Par exemple, si une erreur inconnue se produit lors de la validation (qui est une opération de verrouillage du système), le journal peut rester à l’état verrouillé par le système.</span><span class="sxs-lookup"><span data-stu-id="20efd-129">For example, if an unknown error occurs during posting (which is a system lock operation), the journal might remain in system-locked status.</span></span> <span data-ttu-id="20efd-130">Dans ce cas, le gestionnaire des éléments de travail du workflow générera une erreur lors de la validation du verrouillage.</span><span class="sxs-lookup"><span data-stu-id="20efd-130">In this case, the workflow work item handler will throw an error while it does lock validation.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="20efd-131">Résolution du problème</span><span class="sxs-lookup"><span data-stu-id="20efd-131">Issue resolution</span></span>

<span data-ttu-id="20efd-132">Connectez-vous à l’instance de SQL Server pour Supply Chain Management et vérifiez si **InventJournalTable.SystemBlocked** est défini sur *1*.</span><span class="sxs-lookup"><span data-stu-id="20efd-132">Sign in to the SQL Server instance for Supply Chain Management, and check whether **InventJournalTable.SystemBlocked** is set to *1*.</span></span> <span data-ttu-id="20efd-133">Si tel est le cas, assurez-vous que le journal n’est pas à l’état verrouillé, puis redéfinissez **InventJournalTable.SystemBlocked** sur *0*.</span><span class="sxs-lookup"><span data-stu-id="20efd-133">If it is, make sure that the journal should not be in locked status, and then reset **InventJournalTable.SystemBlocked** to *0*.</span></span>

## <a name="my-inventory-journal-workflow-is-never-completed-and-the-journal-cant-be-edited-or-posted"></a><span data-ttu-id="20efd-134">Le workflow de mon journal d’inventaire ne se termine jamais et le journal ne peut pas être modifié ou publié.</span><span class="sxs-lookup"><span data-stu-id="20efd-134">My inventory journal workflow is never completed, and the journal can't be edited or posted.</span></span>

### <a name="issue-description"></a><span data-ttu-id="20efd-135">Description du problème</span><span class="sxs-lookup"><span data-stu-id="20efd-135">Issue description</span></span>

<span data-ttu-id="20efd-136">Une fois que vous avez envoyé un workflow d’approbation de journal, le traitement du workflow cesse de répondre et vous ne pouvez pas modifier ou traiter vos journaux.</span><span class="sxs-lookup"><span data-stu-id="20efd-136">After you submit a journal approval workflow, workflow processing stops responding, and you can't edit or process your journals.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="20efd-137">Résolution du problème</span><span class="sxs-lookup"><span data-stu-id="20efd-137">Issue resolution</span></span>

<span data-ttu-id="20efd-138">Le traitement du workflow peut ne pas se terminer pour plusieurs raisons.</span><span class="sxs-lookup"><span data-stu-id="20efd-138">There are several reasons why workflow processing might not be completed.</span></span> <span data-ttu-id="20efd-139">Recherchez les problèmes suivants :</span><span class="sxs-lookup"><span data-stu-id="20efd-139">Check for the following issues:</span></span>

- <span data-ttu-id="20efd-140">Accédez à **Gestion des stocks &gt; Paramétrage &gt; Workflow de gestion des stocks** et examinez la configuration du workflow affecté.</span><span class="sxs-lookup"><span data-stu-id="20efd-140">Go to **Inventory management &gt; Setup &gt; Inventory management workflows**, and review the configuration of the affected workflow.</span></span> <span data-ttu-id="20efd-141">Pour plus d’informations, voir [Workflow d’approbation du journal d’inventaire](inventory-journal-workflow.md).</span><span class="sxs-lookup"><span data-stu-id="20efd-141">For more information, see [Inventory journal approval workflows](inventory-journal-workflow.md).</span></span>
- <span data-ttu-id="20efd-142">Le workflow peut rencontrer une exception ou une erreur.</span><span class="sxs-lookup"><span data-stu-id="20efd-142">The workflow might be encountering an exception or error.</span></span> <span data-ttu-id="20efd-143">Révisez l’historique des éléments de travail du workflow affecté pour voir s’il inclut une erreur d’application qui termine le workflow.</span><span class="sxs-lookup"><span data-stu-id="20efd-143">Review the work item history of the affected workflow to see whether it includes an application error that terminates the workflow.</span></span>
- <span data-ttu-id="20efd-144">Le journal d’inventaire ne peut être mis à jour ou modifié que s’il est approuvé.</span><span class="sxs-lookup"><span data-stu-id="20efd-144">The inventory journal can be updated or edited only if it's approved.</span></span> <span data-ttu-id="20efd-145">Si le rappel est actif, vous pouvez essayer de rappeler le journal.</span><span class="sxs-lookup"><span data-stu-id="20efd-145">If recall is active, you can try to recall the journal.</span></span> <span data-ttu-id="20efd-146">L’exécution de la tâche de traitement par lots du workflow peut être suspendue pour plusieurs raisons.</span><span class="sxs-lookup"><span data-stu-id="20efd-146">Execution of the workflow batch job might be suspended for multiple reasons.</span></span> <span data-ttu-id="20efd-147">Certaines de ces raisons peuvent être causées par le problème de structure du workflow.</span><span class="sxs-lookup"><span data-stu-id="20efd-147">Some of these reasons might be caused by the workflow framework issue.</span></span>

## <a name="inventory-journal-workflow-conditions-apply-only-at-the-journal-level-not-at-the-line-level"></a><span data-ttu-id="20efd-148">Les conditions du workflow du journal d’inventaire ne s’appliquent qu’au niveau du journal, et non au niveau de la ligne</span><span class="sxs-lookup"><span data-stu-id="20efd-148">Inventory journal workflow conditions apply only at the journal level, not at the line level</span></span>

### <a name="issue-description"></a><span data-ttu-id="20efd-149">Description du problème</span><span class="sxs-lookup"><span data-stu-id="20efd-149">Issue description</span></span>

<span data-ttu-id="20efd-150">Vous pouvez rencontrer ce problème si, par exemple, vous essayez de configurer une condition du workflow du journal d’inventaire sur le montant du coût.</span><span class="sxs-lookup"><span data-stu-id="20efd-150">You might experience this issue if, for example, you try to set up an inventory journal workflow condition on the cost amount.</span></span> <span data-ttu-id="20efd-151">Vous configurez la condition pour que l’étape 1 ne soit exécutée que lorsque le montant du coût est inférieur à 100.</span><span class="sxs-lookup"><span data-stu-id="20efd-151">You set up the condition so that step 1 is run only when the cost amount is less than 100.</span></span> <span data-ttu-id="20efd-152">Vous configurez ensuite une autre condition pour que l’étape 2 ne soit exécutée que lorsque le montant du coût est supérieur ou égal à 100.</span><span class="sxs-lookup"><span data-stu-id="20efd-152">You then set up another condition so that step 2 is run only when the cost amount is more than or equal to 100.</span></span> <span data-ttu-id="20efd-153">Ensuite, lorsque le workflow est exécuté, l’historique du workflow n’affiche qu’une seule ligne et la première condition est toujours évaluée comme *vrai*, quelle que soit la valeur envoyée.</span><span class="sxs-lookup"><span data-stu-id="20efd-153">Then, when the workflow is run, the workflow history shows only one line, and the first condition is always evaluated as *true*, regardless of the value that is submitted.</span></span>

### <a name="issue-workaround"></a><span data-ttu-id="20efd-154">Solution de contournement du problème</span><span class="sxs-lookup"><span data-stu-id="20efd-154">Issue workaround</span></span>

<span data-ttu-id="20efd-155">Dans la version actuelle, les conditions du workflow du journal ne s’appliquent qu’au niveau du journal, et non au niveau de la ligne.</span><span class="sxs-lookup"><span data-stu-id="20efd-155">In the current release, inventory workflow conditions apply only at the journal level, not at the line level.</span></span> <span data-ttu-id="20efd-156">Ce comportement est fait exprès.</span><span class="sxs-lookup"><span data-stu-id="20efd-156">This behavior is by design.</span></span> <span data-ttu-id="20efd-157">Nous vous recommandons de définir vos critères de condition uniquement sur les attributs au niveau du journal.</span><span class="sxs-lookup"><span data-stu-id="20efd-157">We recommend that you set your condition criteria only on journal-level attributes.</span></span>

## <a name="the-filter-pane-on-the-on-hand-list-page-doesnt-filter-results-as-i-expect"></a><span data-ttu-id="20efd-158">Le volet de filtre de la page Liste disponible ne filtre pas les résultats comme prévu.</span><span class="sxs-lookup"><span data-stu-id="20efd-158">The filter pane on the On-hand list page doesn't filter results as I expect.</span></span>

### <a name="issue-description"></a><span data-ttu-id="20efd-159">Description du problème</span><span class="sxs-lookup"><span data-stu-id="20efd-159">Issue description</span></span>

<span data-ttu-id="20efd-160">Les filtres du volet de filtre de la page **Liste disponible**  ne filtrent pas les résultats comme prévu.</span><span class="sxs-lookup"><span data-stu-id="20efd-160">The filters in the filter pane on the **On-hand list** page don't filter results as you expect.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="20efd-161">Résolution du problème</span><span class="sxs-lookup"><span data-stu-id="20efd-161">Issue resolution</span></span>

<span data-ttu-id="20efd-162">Ce comportement est fait exprès.</span><span class="sxs-lookup"><span data-stu-id="20efd-162">This behavior is by design.</span></span>

<span data-ttu-id="20efd-163">La page  **Liste disponible**  est assemblée à partir d’une table de stock disponible détaillée qui comprend toutes les dimensions disponibles.</span><span class="sxs-lookup"><span data-stu-id="20efd-163">The **On-hand list** page is assembled from a detailed on-hand inventory table that includes all available dimensions.</span></span> <span data-ttu-id="20efd-164">Cependant, la liste sur cette page est un résumé.</span><span class="sxs-lookup"><span data-stu-id="20efd-164">However, the list on this page is a summary.</span></span> <span data-ttu-id="20efd-165">Par conséquent, elle peut combiner des lignes de la table source en regroupant les valeurs en fonction des dimensions affichées.</span><span class="sxs-lookup"><span data-stu-id="20efd-165">Therefore, it might combine rows from the source table by aggregating values according to the dimensions that are shown.</span></span>

<span data-ttu-id="20efd-166">Les filtres configurés dans le volet de filtre s’appliquent à la table source, et non à la liste regroupée.</span><span class="sxs-lookup"><span data-stu-id="20efd-166">Filters that are set up in the filter pane apply to the source table, not to the aggregated list.</span></span> <span data-ttu-id="20efd-167">Ce comportement peut parfois produire des résultats inattendus, comme indiqué dans [ces exemples](inventory-on-hand-list.md#examples).</span><span class="sxs-lookup"><span data-stu-id="20efd-167">This behavior can sometimes produce unexpected results, as shown in [these examples](inventory-on-hand-list.md#examples).</span></span>

<span data-ttu-id="20efd-168">Cependant, les [filtres disponibles dans la grille](inventory-on-hand-list.md#grid-filters) *s’appliquent* à la liste regroupée.</span><span class="sxs-lookup"><span data-stu-id="20efd-168">However, the [filters that are provided in the grid](inventory-on-hand-list.md#grid-filters) *do* apply to the aggregated list.</span></span> <span data-ttu-id="20efd-169">Ces filtres comprennent à la fois le filtre rapide en haut de la grille et le filtre pour chaque en-tête de colonne.</span><span class="sxs-lookup"><span data-stu-id="20efd-169">These filters include both the QuickFilter at the top of the grid and the filter for each column heading.</span></span>

## <a name="the-unit-and-unit-quantity-arent-working-correctly-in-the-inventory-journal"></a><span data-ttu-id="20efd-170">L’unité et la quantité unitaire ne fonctionnent pas correctement dans le journal d’inventaire.</span><span class="sxs-lookup"><span data-stu-id="20efd-170">The unit and unit quantity aren't working correctly in the inventory journal.</span></span>

### <a name="issue-description"></a><span data-ttu-id="20efd-171">Description du problème</span><span class="sxs-lookup"><span data-stu-id="20efd-171">Issue description</span></span>

<span data-ttu-id="20efd-172">Vous pouvez rencontrer l’un ou les deux problèmes suivants lorsque vous utilisez des unités et des quantités dans un journal d’inventaire :</span><span class="sxs-lookup"><span data-stu-id="20efd-172">You might encounter one or both of the following issues when you work with units and quantities in an inventory journal:</span></span>

- <span data-ttu-id="20efd-173">Vous ne voyez pas les unités ou les quantités unitaires dans le journal d’inventaire lorsqu’une unité de conversion est configurée pour le produit lancé, et vous ne pouvez pas modifier l’unité dans le journal d’inventaire.</span><span class="sxs-lookup"><span data-stu-id="20efd-173">You don't see units or unit quantities in the inventory journal while a unit of conversion is set up for the released product, and you can't change the unit in the inventory journal.</span></span>
- <span data-ttu-id="20efd-174">Vous voyez les champs **Quantité** et **Unité** dans le journal d’inventaire, mais vous ne voyez pas le champ **Quantité unitaire**.</span><span class="sxs-lookup"><span data-stu-id="20efd-174">You see the **Quantity** and **Unit** fields in the inventory journal, but you don't see the **Unit quantity** field.</span></span> <span data-ttu-id="20efd-175">Si vous modifiez l’unité, entrez une quantité et validez le journal, le journal affiche toujours l’unité de mesure d’origine pour cette quantité.</span><span class="sxs-lookup"><span data-stu-id="20efd-175">If you change the unit, enter a quantity, and post the journal, the journal still shows the original unit of measurement for that quantity.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="20efd-176">Résolution du problème</span><span class="sxs-lookup"><span data-stu-id="20efd-176">Issue resolution</span></span>

<span data-ttu-id="20efd-177">Pour régler ce problème, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="20efd-177">To fix this issue, follow these steps.</span></span>

1. <span data-ttu-id="20efd-178">Dans l’espace de travail **Gestion des fonctionnalités**, assurez-vous que la fonctionnalité *Utilisation de l’unité de mesure et de la quantité unitaire dans les journaux d’inventaire* est activée.</span><span class="sxs-lookup"><span data-stu-id="20efd-178">In the **Feature management** workspace, make sure that the *Using unit of measure and unit quantity in inventory journals* feature is turned on.</span></span> <span data-ttu-id="20efd-179">Cette fonctionnalité ajoute les champs **Unité** et **Quantité Unitaire** au journal.</span><span class="sxs-lookup"><span data-stu-id="20efd-179">This feature adds the **Unit** and **Unit quantity** fields to the journal.</span></span>
1. <span data-ttu-id="20efd-180">Une fois la fonctionnalité activée, utilisez les champs **Quantité**, **Quantité Unitaire** et **Unité** de la manière suivante :</span><span class="sxs-lookup"><span data-stu-id="20efd-180">After the feature is turned on, use the **Quantity**, **Unit quantity**, and **Unit** fields in the following way:</span></span>

    - <span data-ttu-id="20efd-181">**Quantité** : indiquez la quantité en utilisant l’unité par défaut définie pour le produit lancé.</span><span class="sxs-lookup"><span data-stu-id="20efd-181">**Quantity** – Specify the quantity by using the default unit that is defined for the released product.</span></span> <span data-ttu-id="20efd-182">Cependant, l’unité par défaut proprement dite n’est pas affichée ici.</span><span class="sxs-lookup"><span data-stu-id="20efd-182">However, the default unit itself isn't shown here.</span></span> <span data-ttu-id="20efd-183">Si une conversion est configurée entre l’unité par défaut et l’unité sélectionnée dans le champ **Unité**, le champ **Quantité** est automatiquement mis à jour, en fonction des sélections dans les champs **Quantité unitaire** et **Unité**.</span><span class="sxs-lookup"><span data-stu-id="20efd-183">If a conversion is set up between the default unit and the unit that is selected in the **Unit** field, the **Quantity** field is automatically updated, based on the selections in the **Unit quantity** and **Unit** fields.</span></span>
    - <span data-ttu-id="20efd-184">**Quantité unitaire** : spécifiez la quantité en utilisant l’unité sélectionnée dans le champ **Unité**.</span><span class="sxs-lookup"><span data-stu-id="20efd-184">**Unit quantity** – Specify the quantity by using the unit that is selected in the **Unit** field.</span></span>
    - <span data-ttu-id="20efd-185">**Unité** : sélectionnez l’unité à appliquer à la valeur dans le champ **Quantité Unitaire**.</span><span class="sxs-lookup"><span data-stu-id="20efd-185">**Unit** – Select the unit to apply to the value in the **Unit quantity** field.</span></span>

## <a name="i-receive-the-following-error-message-maximum-number-of-decimals-for-the-stock-keeping-unit-is-0"></a><span data-ttu-id="20efd-186">Je reçois le message d’erreur suivant : « Le nombre maximum de décimales pour l’unité de gestion des stocks est 0 ».</span><span class="sxs-lookup"><span data-stu-id="20efd-186">I receive the following error message: "Maximum number of decimals for the stock keeping unit is 0."</span></span>

### <a name="issue-description"></a><span data-ttu-id="20efd-187">Description du problème</span><span class="sxs-lookup"><span data-stu-id="20efd-187">Issue description</span></span>

<span data-ttu-id="20efd-188">Lorsque vous essayez de valider une transaction de stock ou une réservation de stock, vous recevez le message d’erreur suivant : « Le nombre maximal de décimales pour l’unité de gestion des stocks est 0 ».</span><span class="sxs-lookup"><span data-stu-id="20efd-188">When you try to post an inventory transaction or an inventory reservation, you receive the following error message: "Maximum number of decimals for the stock keeping unit is 0."</span></span>

<span data-ttu-id="20efd-189">Ce problème se produit lorsque la quantité de transactions de stock est spécifiée sous la forme d’une valeur décimale inférieure au niveau de précision pris en charge par le champ.</span><span class="sxs-lookup"><span data-stu-id="20efd-189">This issue occurs when the inventory transaction quantity is specified as a decimal value that is below the level of precision that the field supports.</span></span> <span data-ttu-id="20efd-190">Par exemple, une quantité de *0,5* a été spécifiée pour une transaction de stock, mais seules les quantités entières sont prises en charge.</span><span class="sxs-lookup"><span data-stu-id="20efd-190">For example, a quantity of *0.5* has been specified for an inventory transaction, but only integer quantities are supported.</span></span> <span data-ttu-id="20efd-191">Par conséquent, la valeur doit être *1* au lieu de *0,5*.</span><span class="sxs-lookup"><span data-stu-id="20efd-191">Therefore, the value should be *1* instead of *0.5*.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="20efd-192">Résolution du problème</span><span class="sxs-lookup"><span data-stu-id="20efd-192">Issue resolution</span></span>

1. <span data-ttu-id="20efd-193">Exécutez le script suivant sur votre instance de SQL Server pour arrondir les quantités dans les transactions de stock.</span><span class="sxs-lookup"><span data-stu-id="20efd-193">Run the following script on your SQL Server instance to round quantities in the inventory transactions.</span></span> <span data-ttu-id="20efd-194">Ce script corrigera les valeurs dans la table **inventTrans**.</span><span class="sxs-lookup"><span data-stu-id="20efd-194">This script will correct values in the **inventTrans** table.</span></span>

    ```sql
    update it set it.QTY = round(it.qty, decimalPrecisionValue) from inventtrans it where it.DATAAREAID='XXXX' and it.PARTITION=XXXXXX and it.qty <> round(it.qty, decimalPrecisionValue) and exists (select 'x' from INVENTTABLEMODULE a, unitofmeasure b where  a.unitid =b.SYMBOL and a.partition=it.partition and a.PARTITION=b.PARTITION and  MODULETYPE =0 and  b.DECIMALPRECISION=decimalPrecisionValue and a.DATAAREAID='XXXX' and a.ITEMID =it.ITEMID and it.DATAAREAID=a.DATAAREAID)
    ```

1. <span data-ttu-id="20efd-195">Exécutez un contrôle de cohérence disponible où l’option **corriger l’erreur** est activée.</span><span class="sxs-lookup"><span data-stu-id="20efd-195">Run an on-hand consistency check where the **fix error** option is turned on.</span></span> <span data-ttu-id="20efd-196">Ce contrôle corrigera les valeurs dans la table **inventSum**.</span><span class="sxs-lookup"><span data-stu-id="20efd-196">This check will correct values in the **inventSum** table.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="20efd-197">Il est vivement recommandé de modifier attentivement le script selon les besoins de votre environnement, de le tester dans un environnement de test, puis de vérifier les données résultantes avant d’exécuter le script dans un environnement de production.</span><span class="sxs-lookup"><span data-stu-id="20efd-197">We strongly recommend that you carefully edit the script as required for your environment, test it in a test environment, and then check the resulting data before you run the script in a production environment.</span></span>
