---
title: Workflows d’approbation du journal de stock
description: Cette rubrique décrit comment paramétrer et utiliser des workflows d’approbation du journal de stock pour différents types de transactions de stock physique. Les workflows du journal de stock aident à garantir que seuls les journaux de stock approuvés peuvent être validés sur les transactions.
author: sherry-zheng
manager: tfehr
ms.date: 07/21/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2020-07-21
ms.dyn365.ops.version: Release 10.0.13
ms.openlocfilehash: 1feef1beb1fb3091b84f1601a65c3018063ddd5f
ms.sourcegitcommit: bd89ac6d0b214ce8d7b1314f27111e96713dbd7f
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/28/2020
ms.locfileid: "3628371"
---
# <a name="inventory-journal-approval-workflows"></a><span data-ttu-id="63d3d-104">Workflows d’approbation du journal de stock</span><span class="sxs-lookup"><span data-stu-id="63d3d-104">Inventory journal approval workflows</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="63d3d-105">Cette rubrique décrit comment paramétrer et utiliser des workflows d’approbation du journal de stock pour différents types de transactions de stock physique, tels que les sorties et les réceptions, les mouvements de stock, les nomenclatures et le rapprochement du stock physique.</span><span class="sxs-lookup"><span data-stu-id="63d3d-105">This topic describes how to set up and use inventory journal approval workflows for various types of physical inventory transactions, such as issues and receipts, inventory movements, bills of materials (BOMs), and the reconciliation of physical inventory.</span></span> <span data-ttu-id="63d3d-106">Les workflows du journal de stock aident à garantir que seuls les journaux de stock approuvés peuvent être validés sur les transactions.</span><span class="sxs-lookup"><span data-stu-id="63d3d-106">Inventory journal workflows help ensure that only approved inventory journals can be posted to transactions.</span></span>

> [!NOTE]
> <span data-ttu-id="63d3d-107">Les workflows d’approbation du journal de stock s’appliquent uniquement aux transactions enregistrées à l’aide du module Gestion des stocks.</span><span class="sxs-lookup"><span data-stu-id="63d3d-107">Inventory journal approval workflows apply only to transactions recorded using the Inventory Management module.</span></span> <span data-ttu-id="63d3d-108">Ils ne fonctionnent pas avec les journaux de stock déclenchés à partir du module Gestion des entrepôts.</span><span class="sxs-lookup"><span data-stu-id="63d3d-108">They don't work with inventory journals triggered from the Warehouse Management module.</span></span>

## <a name="create-your-inventory-journal-approval-workflows"></a><span data-ttu-id="63d3d-109">Créer vos workflows d’approbation du journal de stock</span><span class="sxs-lookup"><span data-stu-id="63d3d-109">Create your inventory journal approval workflows</span></span>

<span data-ttu-id="63d3d-110">Pour paramétrer cette fonctionnalité, vous devez créer un workflow pour chacun des types de journaux de stock que vous souhaitez contrôler.</span><span class="sxs-lookup"><span data-stu-id="63d3d-110">To set up this feature, you must create a workflow for each of the inventory journal types you want to control.</span></span> <span data-ttu-id="63d3d-111">Comme différents types de journaux de stock peuvent avoir des hiérarchies d’approbation et des étapes de workflow différentes, vous pouvez configurer des workflows individuels pour chaque type de journal de stock.</span><span class="sxs-lookup"><span data-stu-id="63d3d-111">Because different inventory journal types can have different approval hierarchies and workflow steps, you can configure individual workflows for each inventory journal type.</span></span>

<span data-ttu-id="63d3d-112">Les workflows prennent en charge le contrôle de version et chacun a un ID de workflow et une version active.</span><span class="sxs-lookup"><span data-stu-id="63d3d-112">Workflows support version control, and each has a workflow ID and an active version.</span></span> <span data-ttu-id="63d3d-113">Vous pouvez choisir d’activer chaque nouvelle version de workflow dès sa création ou de la conserver inactive.</span><span class="sxs-lookup"><span data-stu-id="63d3d-113">You can choose to activate each new workflow version immediately upon creation or keep it inactive.</span></span> <span data-ttu-id="63d3d-114">Si différents workflows sont nécessaires pour le même type de journal, créez plusieurs workflows pour ce type de journal, puis affectez chacun d’eux à un nom de journal différent qui utilise ce type.</span><span class="sxs-lookup"><span data-stu-id="63d3d-114">If you need different workflows for the same journal type, then create multiple workflows for that journal type, and then assign each of these to a different journal name that uses that type.</span></span>

<span data-ttu-id="63d3d-115">Pour créer vos workflows d’approbation du journal de stock :</span><span class="sxs-lookup"><span data-stu-id="63d3d-115">To create your inventory journal approval workflows:</span></span>

1. <span data-ttu-id="63d3d-116">Allez dans **Gestion des stocks \> Paramétrage \> Workflows de gestion des stocks**.</span><span class="sxs-lookup"><span data-stu-id="63d3d-116">Go to **Inventory Management \> Setup\> Inventory management workflows**.</span></span>
1. <span data-ttu-id="63d3d-117">Sélectionnez **Nouveau** dans le volet Actions.</span><span class="sxs-lookup"><span data-stu-id="63d3d-117">Select **New** on the Action Pane.</span></span>
1. <span data-ttu-id="63d3d-118">Choisissez le type de journal de stock pour lequel vous souhaitez paramétrer un workflow :</span><span class="sxs-lookup"><span data-stu-id="63d3d-118">Choose the inventory journal type for which you want to set up a workflow:</span></span>
    - <span data-ttu-id="63d3d-119">**Journal d’inventaire de balise de stock**</span><span class="sxs-lookup"><span data-stu-id="63d3d-119">**Inventory tag counting journal**</span></span>
    - <span data-ttu-id="63d3d-120">**Journal des modifications de propriété du stock**</span><span class="sxs-lookup"><span data-stu-id="63d3d-120">**Inventory ownership change journal**</span></span>
    - <span data-ttu-id="63d3d-121">**Journal des mouvements de stock**</span><span class="sxs-lookup"><span data-stu-id="63d3d-121">**Inventory movement journal**</span></span>
    - <span data-ttu-id="63d3d-122">**Journal de transfert de stock**</span><span class="sxs-lookup"><span data-stu-id="63d3d-122">**Inventory transfer journal**</span></span>
    - <span data-ttu-id="63d3d-123">**Journal d’inventaire de stock**</span><span class="sxs-lookup"><span data-stu-id="63d3d-123">**Inventory counting journal**</span></span>
    - <span data-ttu-id="63d3d-124">**Journal de nomenclature de stock**</span><span class="sxs-lookup"><span data-stu-id="63d3d-124">**Inventory BOM journal**</span></span>
    - <span data-ttu-id="63d3d-125">**Journal d’ajustement du stock**</span><span class="sxs-lookup"><span data-stu-id="63d3d-125">**Inventory adjustment journal**</span></span>

    <span data-ttu-id="63d3d-126">![Boîte de dialogue Créer un workflow](media/journal-workflow-create-workflow.png "Boîte de dialogue Créer un workflow")</span><span class="sxs-lookup"><span data-stu-id="63d3d-126">![The Create workflow dialog box](media/journal-workflow-create-workflow.png "The Create workflow dialog box")</span></span>

1. <span data-ttu-id="63d3d-127">L’application Éditeur de workflow se lance sur votre ordinateur.</span><span class="sxs-lookup"><span data-stu-id="63d3d-127">The workflow editor app launches on your machine.</span></span> <span data-ttu-id="63d3d-128">(Vous pouvez être invité à approuver cette action.) Utilisez-la pour concevoir votre workflow selon vos besoins.</span><span class="sxs-lookup"><span data-stu-id="63d3d-128">(You may be asked to approve this action.) Use it to design your workflow as needed.</span></span> <span data-ttu-id="63d3d-129">Pour plus d’informations sur l’utilisation de l’éditeur de workflow, voir [Vue d’ensemble du système de workflow](../../fin-ops-core/fin-ops/organization-administration/overview-workflow-system.md).</span><span class="sxs-lookup"><span data-stu-id="63d3d-129">For details about how to use the workflow editor, see [Workflow system overview](../../fin-ops-core/fin-ops/organization-administration/overview-workflow-system.md).</span></span>
1. <span data-ttu-id="63d3d-130">Après avoir enregistré et fermé l’application Éditeur de workflow, vous devez choisir d’activer cette version de workflow ou de la conserver comme inactive.</span><span class="sxs-lookup"><span data-stu-id="63d3d-130">After saving and closing the workflow editor app, you must choose whether to activate this workflow version or keep it as inactivate.</span></span>

> [!NOTE]
> <span data-ttu-id="63d3d-131">Les workflows fournissent le contrôle de version, ce qui signifie que vous pouvez afficher une liste des versions que vous avez créées et choisir celle active.</span><span class="sxs-lookup"><span data-stu-id="63d3d-131">Workflows provide version control, which means that you can view a list of versions you have created and choose which one is active.</span></span> <span data-ttu-id="63d3d-132">Pour afficher la liste des versions disponibles et choisir celle à activer, sélectionnez un workflow répertorié dans la page **Workflows de gestion des stocks**.</span><span class="sxs-lookup"><span data-stu-id="63d3d-132">To view the list of available versions and choose which to activate, select a workflow listed on the **Inventory management workflows** page.</span></span> <span data-ttu-id="63d3d-133">Dans le volet Actions, ouvrez l’onglet **Workflow** et sélectionnez **Versions**.</span><span class="sxs-lookup"><span data-stu-id="63d3d-133">On the Action Pane, open the **Workflow** tab, and select **Versions**.</span></span> <span data-ttu-id="63d3d-134">Une seule version peut être active à la fois pour chaque ID de workflow.</span><span class="sxs-lookup"><span data-stu-id="63d3d-134">Only one version can be active at a time for each workflow ID.</span></span>

## <a name="assign-approval-workflows-to-inventory-journal-names"></a><span data-ttu-id="63d3d-135">Affecter des workflows d’approbation à des noms de journal de stock</span><span class="sxs-lookup"><span data-stu-id="63d3d-135">Assign approval workflows to inventory journal names</span></span>

<span data-ttu-id="63d3d-136">L’étape suivante consiste à affecter un workflow du journal de stock à chaque nom de journal de stock.</span><span class="sxs-lookup"><span data-stu-id="63d3d-136">The next step is to assign a inventory journal workflow to each inventory journal name.</span></span> <span data-ttu-id="63d3d-137">Pour chaque type de journal de stock, vous pouvez configurer plusieurs noms de journal de stock.</span><span class="sxs-lookup"><span data-stu-id="63d3d-137">For each inventory journal type, you can set up multiple inventory journal names.</span></span>

<span data-ttu-id="63d3d-138">Pour associer un workflow du journal de stock à un nom de journal de stock :</span><span class="sxs-lookup"><span data-stu-id="63d3d-138">To associate an inventory journal workflow with an inventory journal name:</span></span>

1. <span data-ttu-id="63d3d-139">Allez dans **Gestion des stocks \> Paramétrage \> Noms de journal \> Stock**.</span><span class="sxs-lookup"><span data-stu-id="63d3d-139">Go to **Inventory management \> Setup \> Journal names \> Inventory**.</span></span>
1. <span data-ttu-id="63d3d-140">Sélectionnez un nom de journal dans la colonne de liste pour ouvrir sa page de paramètres.</span><span class="sxs-lookup"><span data-stu-id="63d3d-140">Select a journal name from the list column to open its settings page.</span></span>
1. <span data-ttu-id="63d3d-141">Dans l’organisateur **Général**, définissez l’option **Workflow d’approbation** sur **Oui**.</span><span class="sxs-lookup"><span data-stu-id="63d3d-141">On the **General** FastTab, set **Approval workflow** to **Yes**.</span></span> <span data-ttu-id="63d3d-142">Si vous êtes invité à approuver l’action, cliquez sur **Oui**.</span><span class="sxs-lookup"><span data-stu-id="63d3d-142">If you are prompted to approve the action, select **Yes**.</span></span>

    <span data-ttu-id="63d3d-143">![Affecter un workflow à un nom de journal](media/journal-workflow-journal-name.png "Affecter un workflow à un nom de journal")</span><span class="sxs-lookup"><span data-stu-id="63d3d-143">![Assign a workflow to a journal name](media/journal-workflow-journal-name.png "Assign a workflow to a journal name")</span></span>

1. <span data-ttu-id="63d3d-144">Ouvrez la liste déroulante **Workflow** et sélectionnez le workflow approprié.</span><span class="sxs-lookup"><span data-stu-id="63d3d-144">Open the **Workflow** drop-down list and select the appropriate workflow.</span></span> <span data-ttu-id="63d3d-145">La liste affiche chaque workflow actif que vous avez créé à l’aide de l’application Éditeur de workflow.</span><span class="sxs-lookup"><span data-stu-id="63d3d-145">The list shows each active workflow that you have created using the workflow editor app.</span></span>

## <a name="create-an-inventory-journal-and-send-it-for-approval"></a><span data-ttu-id="63d3d-146">Créer un journal de stock et l’envoyer pour approbation</span><span class="sxs-lookup"><span data-stu-id="63d3d-146">Create an inventory journal and send it for approval</span></span>

<span data-ttu-id="63d3d-147">Après avoir associé un nom de journal de stock à son workflow d’approbation du journal de stock correspondant, vous pourrez créer des journaux de stock qui utilisent ce nom, puis envoyer ces journaux pour approbation à l’aide de ce workflow.</span><span class="sxs-lookup"><span data-stu-id="63d3d-147">After you associate an inventory journal name with its matching inventory journal approval workflow, you'll be able to create new inventory journals that use that name and then send these journals for approval using that workflow.</span></span> <span data-ttu-id="63d3d-148">Vous ne pourrez pas valider le journal de stock tant qu’il n’aura pas été approuvé par les approbateurs configurés dans le workflow.</span><span class="sxs-lookup"><span data-stu-id="63d3d-148">You won't be able post the inventory journal until it has been approved by the approvers configured in the workflow.</span></span>

1. <span data-ttu-id="63d3d-149">Dans le volet de navigation, développez **Gestion des stocks \> Entrées de journal \> Articles**, puis sélectionnez un type de journal de stock.</span><span class="sxs-lookup"><span data-stu-id="63d3d-149">On the navigation pane, expand **Inventory management \> Journal entries \> Items** and then select an inventory journal type.</span></span>
1. <span data-ttu-id="63d3d-150">Sélectionnez **Nouveau** pour créer un journal du type sélectionné.</span><span class="sxs-lookup"><span data-stu-id="63d3d-150">Select **New** to create a new journal of your selected type.</span></span>
1. <span data-ttu-id="63d3d-151">La boîte de dialogue **Créer un journal de stock** s’ouvre.</span><span class="sxs-lookup"><span data-stu-id="63d3d-151">The **Create inventory journal** dialog box opens.</span></span> <span data-ttu-id="63d3d-152">Complétez le formulaire selon les besoins, puis cliquez sur **OK** pour enregistrer le journal.</span><span class="sxs-lookup"><span data-stu-id="63d3d-152">Fill out the form as needed and then select **OK** to save the journal.</span></span>
1. <span data-ttu-id="63d3d-153">Complétez le journal selon les besoins.</span><span class="sxs-lookup"><span data-stu-id="63d3d-153">Complete the journal as required.</span></span>
1. <span data-ttu-id="63d3d-154">Lorsque vous créez ou ouvrez un journal de stock auquel est associé un workflow d’approbation, le bouton **Workflow** est actif dans le volet Actions.</span><span class="sxs-lookup"><span data-stu-id="63d3d-154">When you create or open an inventory journal with an approval workflow associated with it, the **Workflow** button will be active in the Action Pane.</span></span> <span data-ttu-id="63d3d-155">Lorsque vous êtes prêt à soumettre le journal pour approbation, cliquez sur le bouton **Workflow** pour ouvrir une boîte de dialogue déroulante, puis sélectionnez **Soumettre**.</span><span class="sxs-lookup"><span data-stu-id="63d3d-155">When you are ready to submit the journal for approval, select the **Workflow** button to open a drop-down dialog box and then select **Submit**.</span></span> <span data-ttu-id="63d3d-156">La demande d’approbation est ensuite envoyée à l’approbateur approprié, qui en est informé à l’aide de la méthode de notification configurée pour le workflow.</span><span class="sxs-lookup"><span data-stu-id="63d3d-156">The approval request will then route to the relevant approver, who will be alerted using the notification method configured for the workflow.</span></span>

    <span data-ttu-id="63d3d-157">![Soumettre un journal pour approbation](media/journal-workflow-inventory-journal.png "Soumettre un journal pour approbation")</span><span class="sxs-lookup"><span data-stu-id="63d3d-157">![Submit a journal for approval](media/journal-workflow-inventory-journal.png "Submit a journal for approval")</span></span>

<span data-ttu-id="63d3d-158">Pour rappeler une demande d’approbation, ouvrez le journal approprié, cliquez sur le bouton **Workflow**, puis sélectionnez **Rappeler**.</span><span class="sxs-lookup"><span data-stu-id="63d3d-158">To recall an approval request, open the relevant journal, select the **Workflow** button and then select **Recall**.</span></span> <span data-ttu-id="63d3d-159">Le workflow est alors réinitialisé.</span><span class="sxs-lookup"><span data-stu-id="63d3d-159">This will reset the workflow.</span></span>

<span data-ttu-id="63d3d-160">Une fois que votre journal aura été approuvé, vous pourrez le valider.</span><span class="sxs-lookup"><span data-stu-id="63d3d-160">When your journal has been approved, you'll be able to post it.</span></span> <span data-ttu-id="63d3d-161">Pour valider le journal, sélectionnez **Valider** dans le volet Actions.</span><span class="sxs-lookup"><span data-stu-id="63d3d-161">To post the journal, select **Post** from the Action Pane.</span></span> <span data-ttu-id="63d3d-162">Si le bouton **Valider** n’est pas actif, le journal n’a pas encore été approuvé.</span><span class="sxs-lookup"><span data-stu-id="63d3d-162">If the **Post** button isn't active the journal hasn't been approved yet.</span></span>

## <a name="respond-to-an-inventory-journal-approval-request"></a><span data-ttu-id="63d3d-163">Répondre à une demande d’approbation du journal de stock</span><span class="sxs-lookup"><span data-stu-id="63d3d-163">Respond to an inventory journal approval request</span></span>

<span data-ttu-id="63d3d-164">Si vous êtes un approbateur, vous devez recevoir un message chaque fois que votre approbation est nécessaire (comme configuré dans le workflow approprié).</span><span class="sxs-lookup"><span data-stu-id="63d3d-164">If you are an approver, you should receive a message each time your approval is needed (as configured in the relevant workflow).</span></span> <span data-ttu-id="63d3d-165">Vous pouvez ensuite approuver ou rejeter une demande d’approbation de journal en procédant comme suit :</span><span class="sxs-lookup"><span data-stu-id="63d3d-165">Then you can approve or reject a journal approval request by doing the following:</span></span>

1. <span data-ttu-id="63d3d-166">Dans le volet de navigation, développez **Gestion des stocks \> Entrées de journal \> Articles**, puis sélectionnez un type de journal de stock.</span><span class="sxs-lookup"><span data-stu-id="63d3d-166">On the navigation pane, expand **Inventory management \> Journal entries \> Items** and then select an inventory journal type.</span></span>
1. <span data-ttu-id="63d3d-167">Ouvrez le journal approprié et passez-le en revue.</span><span class="sxs-lookup"><span data-stu-id="63d3d-167">Open the relevant journal and review it.</span></span>
1. <span data-ttu-id="63d3d-168">Cliquez sur le bouton **Workflow** dans le volet Actions pour ouvrir une boîte de dialogue déroulante.</span><span class="sxs-lookup"><span data-stu-id="63d3d-168">Select the **Workflow** button on the Action Pane to open a drop-down dialog box.</span></span> <span data-ttu-id="63d3d-169">Sélectionnez l’une des options suivantes :</span><span class="sxs-lookup"><span data-stu-id="63d3d-169">Select one of the following:</span></span>
    - <span data-ttu-id="63d3d-170">**Approuver** : pour approuver la demande.</span><span class="sxs-lookup"><span data-stu-id="63d3d-170">**Approve** - To approve the request.</span></span>
    - <span data-ttu-id="63d3d-171">**Rejeter** : pour rejeter la demande.</span><span class="sxs-lookup"><span data-stu-id="63d3d-171">**Reject** - To reject the reject the request.</span></span>
    - <span data-ttu-id="63d3d-172">**Autre \> Demander une modification** : pour envoyer un message au demandeur lui demandant de modifier quelque chose de spécifique, puis soumettre la demande à nouveau.</span><span class="sxs-lookup"><span data-stu-id="63d3d-172">**More \> Request change** - To send a message to the requester asking them to change something specific and then resubmit.</span></span>
    - <span data-ttu-id="63d3d-173">**Autre \> Déléguer** : pour déléguer l’approbation à un autre utilisateur.</span><span class="sxs-lookup"><span data-stu-id="63d3d-173">**More \> Delegate** - To delegate the approval to another user.</span></span>
    - <span data-ttu-id="63d3d-174">**Autre \> Rappeler** : pour rappeler la demande d’approbation (réinitialise le workflow).</span><span class="sxs-lookup"><span data-stu-id="63d3d-174">**More \> Recall** - To recall the approval request (resets the workflow).</span></span>
    - <span data-ttu-id="63d3d-175">**Autre \> Historique du workflow** : pour afficher l’historique de ce workflow d’approbation jusqu’à présent.</span><span class="sxs-lookup"><span data-stu-id="63d3d-175">**More \> Workflow history** - To view the history of this approval workflow so far.</span></span>

## <a name="review-the-approval-history"></a><span data-ttu-id="63d3d-176">Consulter l’historique d’approbation</span><span class="sxs-lookup"><span data-stu-id="63d3d-176">Review the approval history</span></span>

<span data-ttu-id="63d3d-177">Comme pour les autres types de workflows, vous pouvez utiliser la page **Historique du workflow** pour afficher l’historique du workflow d’approbation de n’importe quel journal.</span><span class="sxs-lookup"><span data-stu-id="63d3d-177">As with other types of workflows, you can use the **Workflow history** page to view the approval workflow history for any journal.</span></span>

<span data-ttu-id="63d3d-178">Pour consulter l’historique du workflow d’un journal :</span><span class="sxs-lookup"><span data-stu-id="63d3d-178">To review the workflow history for a journal:</span></span>

1. <span data-ttu-id="63d3d-179">Dans le volet de navigation, développez **Gestion des stocks \> Entrées de journal \> Articles**, puis sélectionnez un type de journal de stock.</span><span class="sxs-lookup"><span data-stu-id="63d3d-179">On the navigation pane, expand **Inventory management \> Journal entries \> Items** and then select an inventory journal type.</span></span>
1. <span data-ttu-id="63d3d-180">Ouvrez le journal approprié.</span><span class="sxs-lookup"><span data-stu-id="63d3d-180">Open the relevant journal.</span></span>
1. <span data-ttu-id="63d3d-181">Cliquez sur le bouton **Workflow** dans le volet Actions pour ouvrir une boîte de dialogue déroulante.</span><span class="sxs-lookup"><span data-stu-id="63d3d-181">Select the **Workflow** button on the Action Pane to open a drop-down dialog box.</span></span> <span data-ttu-id="63d3d-182">Sélectionnez **Historique du workflow**.</span><span class="sxs-lookup"><span data-stu-id="63d3d-182">Select **Workflow history**.</span></span> <span data-ttu-id="63d3d-183">Pour plus d’informations, voir [Afficher l’historique du worklow](../../fin-ops-core/fin-ops/organization-administration/tasks/view-workflow-history.md).</span><span class="sxs-lookup"><span data-stu-id="63d3d-183">For more information, see [View workflow history](../../fin-ops-core/fin-ops/organization-administration/tasks/view-workflow-history.md).</span></span>