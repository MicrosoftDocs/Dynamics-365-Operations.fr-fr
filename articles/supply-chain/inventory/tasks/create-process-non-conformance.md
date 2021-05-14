---
title: Créer et traiter les non-conformités
description: Cette rubrique explique comment effectuer la gestion de non-conformité, en fonction d’un ordre de qualité existant.
author: perlynne
ms.date: 03/23/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 06a56a694f7a80d65cb46d08744e78d8361cee3b
ms.sourcegitcommit: 8362f3bd32ce8b9a5af93c8e57daef732a93b19e
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/28/2021
ms.locfileid: "5956204"
---
# <a name="create-and-process-nonconformances"></a><span data-ttu-id="ddca1-103">Créer et traiter les non-conformités</span><span class="sxs-lookup"><span data-stu-id="ddca1-103">Create and process nonconformances</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="ddca1-104">Cette rubrique explique comment effectuer la gestion de non-conformité, en fonction d’un ordre de qualité existant.</span><span class="sxs-lookup"><span data-stu-id="ddca1-104">This topic describes how to perform nonconformance management based on an existing quality order.</span></span> <span data-ttu-id="ddca1-105">En règle générale, la gestion des non-conformités est effectuée par un commis au contrôle de la qualité.</span><span class="sxs-lookup"><span data-stu-id="ddca1-105">Typically, nonconformance management is done by a quality clerk.</span></span> <span data-ttu-id="ddca1-106">Au préalable, vous devez disposer d'un ordre de qualité.</span><span class="sxs-lookup"><span data-stu-id="ddca1-106">As a prerequisite, you must have a quality order available.</span></span> <span data-ttu-id="ddca1-107">(Pour plus d'informations sur la création d'un ordre de qualité, voir [Inspecter la qualité des marchandises](inspect-quality-goods.md) .)</span><span class="sxs-lookup"><span data-stu-id="ddca1-107">(For information about how to create a quality order, see [Inspect the quality of goods](inspect-quality-goods.md).)</span></span>

<span data-ttu-id="ddca1-108">Avant qu'un utilisateur puisse traiter l'approbation d'une non-conformité, un collaborateur doit lui être affecté dans le champ **Personne** sur la page **Utilisateurs**.</span><span class="sxs-lookup"><span data-stu-id="ddca1-108">Before a user can process the approval of a nonconformance, a worker must be assigned to them in the **Person** field on the **Users** page.</span></span> <span data-ttu-id="ddca1-109">De plus, avant que l'utilisateur puisse utiliser les notes du document, l'option **Activer la gestion des documents** doit être définie sur *Oui* dans leurs options de l'utilisateur.</span><span class="sxs-lookup"><span data-stu-id="ddca1-109">Additionally, before the user can use the document notes, the **Enable document handling** option must be set to *Yes* in their user options.</span></span>

## <a name="create-a-nonconformance"></a><span data-ttu-id="ddca1-110">Créer une non-conformité</span><span class="sxs-lookup"><span data-stu-id="ddca1-110">Create a nonconformance</span></span>

<span data-ttu-id="ddca1-111">Pour créer une non-conformité, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="ddca1-111">To create a nonconformance, follow these steps.</span></span>

1. <span data-ttu-id="ddca1-112">Allez dans **Gestion des stocks \> Tâches périodiques \> Gestion de la qualité \> Non-conformités**.</span><span class="sxs-lookup"><span data-stu-id="ddca1-112">Go to **Inventory management \> Periodic tasks \> Quality management \> Non conformances**.</span></span>
1. <span data-ttu-id="ddca1-113">Dans le volet Actions, sélectionnez **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="ddca1-113">On the Action pane, select **New**.</span></span>
1. <span data-ttu-id="ddca1-114">Dans la boîte de dialogue **Créer une non-conformité**, dans le champ **Type de problème**, sélectionnez le type de problème détecté lors du processus d'inspection.</span><span class="sxs-lookup"><span data-stu-id="ddca1-114">In the **Create non conformance** dialog box, in **Problem type** field, select the type of problem that was found during the inspection process.</span></span>
1. <span data-ttu-id="ddca1-115">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="ddca1-115">Select **OK**.</span></span>

## <a name="approve-or-reject-a-nonconformance"></a><span data-ttu-id="ddca1-116">Approuver ou rejeter une non-conformité</span><span class="sxs-lookup"><span data-stu-id="ddca1-116">Approve or reject a nonconformance</span></span>

<span data-ttu-id="ddca1-117">Pour approuver ou rejeter une non-conformité, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="ddca1-117">To approve or reject a nonconformance, follow these steps.</span></span>

1. <span data-ttu-id="ddca1-118">Allez dans **Gestion des stocks \> Tâches périodiques \> Gestion de la qualité \> Non-conformités**.</span><span class="sxs-lookup"><span data-stu-id="ddca1-118">Go to **Inventory management \> Periodic tasks \> Quality management \> Non conformances**.</span></span>
1. <span data-ttu-id="ddca1-119">Dans la liste, localisez et sélectionnez la non-conformité que vous voulez mettre à jour.</span><span class="sxs-lookup"><span data-stu-id="ddca1-119">In the list, select the nonconformance that you want to update.</span></span>

    > [!NOTE]
    > <span data-ttu-id="ddca1-120">Vous ne pouvez ajouter une correction qu'aux non-conformités approuvées.</span><span class="sxs-lookup"><span data-stu-id="ddca1-120">You can add a correction only to nonconformances that are approved.</span></span>

1. <span data-ttu-id="ddca1-121">Dans le volet Actions, sélectionnez **Fonctions \> Approuver la non-conformité** pour approuver la non-conformité ou **Fonctions \> Refuser la non-conformité** pour la rejeter.</span><span class="sxs-lookup"><span data-stu-id="ddca1-121">On the Action Pane, select **Functions \> Approve non conformance** to approve the nonconformance or **Functions \> Refuse non conformance** to reject it.</span></span> <span data-ttu-id="ddca1-122">Vous pouvez associer des non-conformités approuvées aux [opérations connexes](../quality-operations.md).</span><span class="sxs-lookup"><span data-stu-id="ddca1-122">You can associate approved nonconformances with [related operations](../quality-operations.md).</span></span> <span data-ttu-id="ddca1-123">De cette manière, vous pouvez enregistrer le travail effectué dans le cadre de la gestion des non-conformités et du traitement de la gestion des corrections.</span><span class="sxs-lookup"><span data-stu-id="ddca1-123">In this way, you can record work that is done as part of the nonconformance handling and the processing of correction handling.</span></span>
1. <span data-ttu-id="ddca1-124">Vous êtes invité à confirmer la sélection.</span><span class="sxs-lookup"><span data-stu-id="ddca1-124">You're prompted to confirm your selection.</span></span> <span data-ttu-id="ddca1-125">Sélectionnez **Oui** pour continuer.</span><span class="sxs-lookup"><span data-stu-id="ddca1-125">Select **Yes** to continue.</span></span>

## <a name="add-operations-and-other-details-to-nonconformances"></a><span data-ttu-id="ddca1-126">Ajouter des opérations et d'autres détails aux non-conformités</span><span class="sxs-lookup"><span data-stu-id="ddca1-126">Add operations and other details to nonconformances</span></span>

<span data-ttu-id="ddca1-127">Après avoir créé une non-conformité, vous pouvez commencer à ajouter des opérations associées et spécifier des informations supplémentaires sur ces opérations.</span><span class="sxs-lookup"><span data-stu-id="ddca1-127">After you've created a nonconformance, you can start to add related operations and specify additional information about those operations.</span></span> <span data-ttu-id="ddca1-128">Vous ne pouvez ajouter des opérations connexes qu'aux non-conformités approuvées.</span><span class="sxs-lookup"><span data-stu-id="ddca1-128">You can add related operations only to nonconformances that are approved.</span></span>

<span data-ttu-id="ddca1-129">Outre les informations de base, vous pouvez ajouter les détails suivants à une opération :</span><span class="sxs-lookup"><span data-stu-id="ddca1-129">Besides the basic information, you can add the following details to an operation:</span></span>

- <span data-ttu-id="ddca1-130">**Articles** - Vous pouvez créer une liste d'articles consommés pour effectuer la correction.</span><span class="sxs-lookup"><span data-stu-id="ddca1-130">**Items** – You can create a list of items that are consumed to perform the correction.</span></span> <span data-ttu-id="ddca1-131">Par exemple, les articles peuvent être des produits nécessaires à la réparation de l'équipement ou des substances nécessaires pour retravailler un produit fini.</span><span class="sxs-lookup"><span data-stu-id="ddca1-131">For example, the items might be products that are required to repair equipment or ingredients that are required to rework a finished product.</span></span>
- <span data-ttu-id="ddca1-132">**Frais de qualité** - Vous pouvez créer une liste des frais encourus ou facturés à des sources externes.</span><span class="sxs-lookup"><span data-stu-id="ddca1-132">**Quality charges** – You can create a list of charges that are incurred or billed out to external sources.</span></span>
- <span data-ttu-id="ddca1-133">**Emploi du temps** - Vous pouvez créer un journal du temps que chaque collaborateur passe sur l'opération.</span><span class="sxs-lookup"><span data-stu-id="ddca1-133">**Timesheet** – You can create a log of the time that each worker spends on the operation.</span></span>

<span data-ttu-id="ddca1-134">Les paramètres restantes sont facultatifs.</span><span class="sxs-lookup"><span data-stu-id="ddca1-134">The remaining settings are optional.</span></span> <span data-ttu-id="ddca1-135">Le coût de chaque article, les frais de qualité et la feuille de temps sont additionnés et indiqués sur l'opération.</span><span class="sxs-lookup"><span data-stu-id="ddca1-135">The cost for each item, quality charges, and the timesheet are summed and shown on the operation.</span></span> <span data-ttu-id="ddca1-136">Vous ne pouvez pas modifier directement le champ **Coût** sur l'opération.</span><span class="sxs-lookup"><span data-stu-id="ddca1-136">You can't directly edit the **Cost** field on the operation.</span></span>

### <a name="create-an-operation-for-a-nonconformance"></a><span data-ttu-id="ddca1-137">Créer une opération pour une non-conformité</span><span class="sxs-lookup"><span data-stu-id="ddca1-137">Create an operation for a nonconformance</span></span>

<span data-ttu-id="ddca1-138">Pour créer une opération pour une non-conformité, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="ddca1-138">To create an operation for a nonconformance, follow these steps.</span></span>

1. <span data-ttu-id="ddca1-139">Allez dans **Gestion des stocks \> Tâches périodiques \> Gestion de la qualité \> Non-conformités**.</span><span class="sxs-lookup"><span data-stu-id="ddca1-139">Go to **Inventory management \> Periodic tasks \> Quality management \> Non conformances**.</span></span>
1. <span data-ttu-id="ddca1-140">Dans la liste, localisez et sélectionnez la non-conformité que vous voulez mettre à jour.</span><span class="sxs-lookup"><span data-stu-id="ddca1-140">In the list, select the nonconformance that you want to update.</span></span>

    > [!NOTE]
    > <span data-ttu-id="ddca1-141">Vous pouvez ajouter et mettre à jour des opérations connexes uniquement pour des non-conformités approuvées.</span><span class="sxs-lookup"><span data-stu-id="ddca1-141">You can add or update operations only for nonconformances that are approved.</span></span>

1. <span data-ttu-id="ddca1-142">Dans le volet Actions, sélectionnez **Opérations connexes**.</span><span class="sxs-lookup"><span data-stu-id="ddca1-142">On the Action Pane, select **Related operations**.</span></span>
1. <span data-ttu-id="ddca1-143">Sur la page **Opérations connexes**, dans le volet Actions, sélectionnez **Nouveau** pour ajouter une ligne à la grille.</span><span class="sxs-lookup"><span data-stu-id="ddca1-143">On the **Related operations** page, on the Action pane, select **New** to add a row to the grid.</span></span> <span data-ttu-id="ddca1-144">Définissez ensuite les champs suivants pour la nouvelle ligne :</span><span class="sxs-lookup"><span data-stu-id="ddca1-144">Then set the following fields for the new row:</span></span>

    - <span data-ttu-id="ddca1-145">**Opération** - Sélectionnez le code de l'opération qui sera effectuée pour la non-conformité.</span><span class="sxs-lookup"><span data-stu-id="ddca1-145">**Operation** – Select the code of the operation that will be performed for the nonconformance.</span></span>
    - <span data-ttu-id="ddca1-146">**Raison** - Entrez une description détaillée expliquant pourquoi l'opération est requise.</span><span class="sxs-lookup"><span data-stu-id="ddca1-146">**Reason** – Enter a detailed description that explains why the operation is required.</span></span>
    - <span data-ttu-id="ddca1-147">**Commande client** - Si le code d'opération sélectionné est lié au type de commande client, sélectionnez la commande client à laquelle vous liez l'opération.</span><span class="sxs-lookup"><span data-stu-id="ddca1-147">**Sales order** – If the selected operation code is related to the sales order type, select the sales order that you're linking the operation to.</span></span>
    - <span data-ttu-id="ddca1-148">**Commande fournisseur** - Si le code d'opération sélectionné est lié au type de commande fournisseur, sélectionnez la commande fournisseur à laquelle vous liez l'opération.</span><span class="sxs-lookup"><span data-stu-id="ddca1-148">**Purchase order** – If the selected operation code is related to the purchase order type, select the purchase order that you're linking the operation to.</span></span>

1. <span data-ttu-id="ddca1-149">Fermez les pages.</span><span class="sxs-lookup"><span data-stu-id="ddca1-149">Close the pages.</span></span>

### <a name="add-items-to-an-operation"></a><span data-ttu-id="ddca1-150">Ajouter des articles à une opération</span><span class="sxs-lookup"><span data-stu-id="ddca1-150">Add items to an operation</span></span>

<span data-ttu-id="ddca1-151">Pour ajouter des articles à une opération, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="ddca1-151">To add items to an operation, follow these steps.</span></span>

1. <span data-ttu-id="ddca1-152">Allez dans **Gestion des stocks \> Tâches périodiques \> Gestion de la qualité \> Non-conformités**.</span><span class="sxs-lookup"><span data-stu-id="ddca1-152">Go to **Inventory management \> Periodic tasks \> Quality management \> Non conformances**.</span></span>
1. <span data-ttu-id="ddca1-153">Dans la liste, localisez et sélectionnez la non-conformité que vous voulez mettre à jour.</span><span class="sxs-lookup"><span data-stu-id="ddca1-153">In the list, select the nonconformance that you want to update.</span></span>

    > [!NOTE]
    > <span data-ttu-id="ddca1-154">Vous pouvez ajouter et mettre à jour des opérations connexes uniquement pour des non-conformités approuvées.</span><span class="sxs-lookup"><span data-stu-id="ddca1-154">You can add or update operations only for nonconformances that are approved.</span></span>

1. <span data-ttu-id="ddca1-155">Dans le volet Actions, sélectionnez **Opérations connexes**.</span><span class="sxs-lookup"><span data-stu-id="ddca1-155">On the Action Pane, select **Related operations**.</span></span>
1. <span data-ttu-id="ddca1-156">Dans la page **Opérations connexes**, sélectionnez l'opération à laquelle vous souhaitez ajouter des articles.</span><span class="sxs-lookup"><span data-stu-id="ddca1-156">On the **Related operations** page, select the operation that you want to add items to.</span></span>
1. <span data-ttu-id="ddca1-157">Dans le volet Actions, sélectionnez **Articles**.</span><span class="sxs-lookup"><span data-stu-id="ddca1-157">On the Action Pane, select **Items**.</span></span>
1. <span data-ttu-id="ddca1-158">Sur la page **Opérations connexes**, dans le volet Actions, sélectionnez **Nouveau** pour ajouter une ligne à la grille.</span><span class="sxs-lookup"><span data-stu-id="ddca1-158">On the **Related operations** page, on the Action pane, select **New** to add a row to the grid.</span></span> <span data-ttu-id="ddca1-159">Définissez ensuite les champs suivants pour la nouvelle ligne :</span><span class="sxs-lookup"><span data-stu-id="ddca1-159">Then set the following fields for new row:</span></span>

    - <span data-ttu-id="ddca1-160">**Numéro d'article** - Sélectionnez le produit qui sera consommé dans le cadre de l'opération sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="ddca1-160">**Item number** – Select the product that will be consumed as part of the selected operation.</span></span>
    - <span data-ttu-id="ddca1-161">**Quantité** - Entrez le nombre d'articles qui seront consommés.</span><span class="sxs-lookup"><span data-stu-id="ddca1-161">**Quantity** – Enter the number of items that will be consumed.</span></span>

    > [!NOTE]
    > <span data-ttu-id="ddca1-162">Vous pouvez afficher le coût de l'article dans le champ **Coût** sur l'onglet **Général**. Le coût qui y est indiqué provient du coût défini sur la page **Produit lancé**.</span><span class="sxs-lookup"><span data-stu-id="ddca1-162">You can view the cost for the item in the **Cost** field on the **General** tab. The cost that is shown there comes from the cost that is set up on the **Released product** page.</span></span> <span data-ttu-id="ddca1-163">Le coût ne peut pas être mis à jour directement sur la page **Article d'opération connexe**.</span><span class="sxs-lookup"><span data-stu-id="ddca1-163">The cost can't be updated directly on the **Related operation item** page.</span></span> <span data-ttu-id="ddca1-164">Le coût de tous les articles ajoutés sur la page **Articles d'opération connexe** est automatiquement ajouté au champ **Coût** sur la page **Opérations connexes**.</span><span class="sxs-lookup"><span data-stu-id="ddca1-164">The cost of all items that are added on the **Related operation items** page is automatically added to the **Cost** field on the **Related operations** page.</span></span>

1. <span data-ttu-id="ddca1-165">Répétez l'étape précédente pour chaque article supplémentaire que vous devez ajouter.</span><span class="sxs-lookup"><span data-stu-id="ddca1-165">Repeat the previous step for each additional item that you must add.</span></span>
1. <span data-ttu-id="ddca1-166">Fermez les pages.</span><span class="sxs-lookup"><span data-stu-id="ddca1-166">Close the pages.</span></span>

### <a name="add-quality-charges-to-an-operation"></a><span data-ttu-id="ddca1-167">Ajouter des frais de qualité à une opération</span><span class="sxs-lookup"><span data-stu-id="ddca1-167">Add quality charges to an operation</span></span>

<span data-ttu-id="ddca1-168">Pour ajouter des frais de qualité à une opération, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="ddca1-168">To add quality charges to an operation, follow these steps.</span></span>

1. <span data-ttu-id="ddca1-169">Allez dans **Gestion des stocks \> Tâches périodiques \> Gestion de la qualité \> Non-conformités**.</span><span class="sxs-lookup"><span data-stu-id="ddca1-169">Go to **Inventory management \> Periodic tasks \> Quality management \> Non conformances**.</span></span>
1. <span data-ttu-id="ddca1-170">Dans la liste, localisez et sélectionnez la non-conformité que vous voulez mettre à jour.</span><span class="sxs-lookup"><span data-stu-id="ddca1-170">In the list, select the nonconformance that you want to update.</span></span>

    > [!NOTE]
    > <span data-ttu-id="ddca1-171">Vous pouvez ajouter et mettre à jour des opérations connexes uniquement pour des non-conformités approuvées.</span><span class="sxs-lookup"><span data-stu-id="ddca1-171">You can add or update operations only for nonconformances that are approved.</span></span>

1. <span data-ttu-id="ddca1-172">Dans le volet Actions, sélectionnez **Opérations connexes**.</span><span class="sxs-lookup"><span data-stu-id="ddca1-172">On the Action Pane, select **Related operations**.</span></span>
1. <span data-ttu-id="ddca1-173">Dans la page **Opérations connexes**, sélectionnez l'opération à laquelle vous souhaitez ajouter des frais de qualité.</span><span class="sxs-lookup"><span data-stu-id="ddca1-173">On the **Related operations** page, select the operation that you want to add quality charges to.</span></span>
1. <span data-ttu-id="ddca1-174">Dans le volet Actions, cliquez sur **Frais de qualité**.</span><span class="sxs-lookup"><span data-stu-id="ddca1-174">On the Action Pane, select **Quality charges**.</span></span>
1. <span data-ttu-id="ddca1-175">Sur la page **Frais d'opération connexe**, dans le volet Actions, sélectionnez **Nouveau** pour ajouter une ligne à la grille.</span><span class="sxs-lookup"><span data-stu-id="ddca1-175">On the **Related operation charges** page, on the Action pane, select **New** to add a row to the grid.</span></span> <span data-ttu-id="ddca1-176">Définissez ensuite les champs suivants pour la nouvelle ligne :</span><span class="sxs-lookup"><span data-stu-id="ddca1-176">Then set the following fields for the new row:</span></span>

    - <span data-ttu-id="ddca1-177">**Code de frais** - Sélectionnez les frais de qualité que vous souhaitez ajouter.</span><span class="sxs-lookup"><span data-stu-id="ddca1-177">**Charges code** – Select the quality charge that you want to add.</span></span>
    - <span data-ttu-id="ddca1-178">**Description** - Entrez une description détaillée des frais.</span><span class="sxs-lookup"><span data-stu-id="ddca1-178">**Description** – Enter a detailed description of the charge.</span></span>
    - <span data-ttu-id="ddca1-179">**Valeur des frais** – Entrez le montant des frais.</span><span class="sxs-lookup"><span data-stu-id="ddca1-179">**Charges value** – Enter the amount of the charge.</span></span>

1. <span data-ttu-id="ddca1-180">Répétez l'étape précédente pour les frais supplémentaires individuels que vous devez ajouter.</span><span class="sxs-lookup"><span data-stu-id="ddca1-180">Repeat the previous step for each additional charge that you must add.</span></span>
1. <span data-ttu-id="ddca1-181">Fermez les pages.</span><span class="sxs-lookup"><span data-stu-id="ddca1-181">Close the pages.</span></span>

> [!NOTE]
> <span data-ttu-id="ddca1-182">Le montant dans le champ **Valeur des frais** est automatiquement additionné pour tous les frais de qualité et ajouté à tout autre montant dans le champ **Coût** sur la page **Opérations connexes**.</span><span class="sxs-lookup"><span data-stu-id="ddca1-182">The amount in the **Charges value** field is automatically summed for all quality charges and added to any other amounts in the **Cost** field on the **Related operations** page.</span></span>

### <a name="create-a-timesheet-on-an-operation"></a><span data-ttu-id="ddca1-183">Créer une feuille de temps sur une opération</span><span class="sxs-lookup"><span data-stu-id="ddca1-183">Create a timesheet on an operation</span></span>

<span data-ttu-id="ddca1-184">Pour ajouter une feuille de temps à une opération, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="ddca1-184">To add a timesheet to an operation, follow these steps.</span></span>

1. <span data-ttu-id="ddca1-185">Allez dans **Gestion des stocks \> Tâches périodiques \> Gestion de la qualité \> Non-conformités**.</span><span class="sxs-lookup"><span data-stu-id="ddca1-185">Go to **Inventory management \> Periodic tasks \> Quality management \> Non conformances**.</span></span>
1. <span data-ttu-id="ddca1-186">Dans la liste, localisez et sélectionnez la non-conformité que vous voulez mettre à jour.</span><span class="sxs-lookup"><span data-stu-id="ddca1-186">In the list, select the nonconformance that you want to update.</span></span>

    > [!NOTE]
    > <span data-ttu-id="ddca1-187">Vous pouvez ajouter et mettre à jour des opérations connexes uniquement pour des non-conformités approuvées.</span><span class="sxs-lookup"><span data-stu-id="ddca1-187">You can add or update operations only for nonconformances that are approved.</span></span>

1. <span data-ttu-id="ddca1-188">Dans le volet Actions, sélectionnez **Opérations connexes**.</span><span class="sxs-lookup"><span data-stu-id="ddca1-188">On the Action Pane, select **Related operations**.</span></span>
1. <span data-ttu-id="ddca1-189">Dans la page **Opérations connexes**, sélectionnez l'opération à laquelle vous souhaitez ajouter une feuille de temps.</span><span class="sxs-lookup"><span data-stu-id="ddca1-189">On the **Related operations** page, select the operation that you want to add a timesheet to.</span></span>
1. <span data-ttu-id="ddca1-190">Dans le volet Actions, sélectionnez **Feuille de temps**.</span><span class="sxs-lookup"><span data-stu-id="ddca1-190">On the Action Pane, select **Timesheet**.</span></span>
1. <span data-ttu-id="ddca1-191">Sur la page **Feuille de temps d'opération connexe**, dans le volet Actions, sélectionnez **Nouveau** pour ajouter une ligne à la grille.</span><span class="sxs-lookup"><span data-stu-id="ddca1-191">On the **Related operation time sheets** page, on the Action pane, select **New** to add a row to the grid.</span></span> <span data-ttu-id="ddca1-192">Définissez ensuite les champs suivants pour la nouvelle ligne :</span><span class="sxs-lookup"><span data-stu-id="ddca1-192">Then set the following fields for the new row:</span></span>

    - <span data-ttu-id="ddca1-193">**Date** - Précisez la date à laquelle le travail a été effectué.</span><span class="sxs-lookup"><span data-stu-id="ddca1-193">**Date** – Specify the date when work was done.</span></span> <span data-ttu-id="ddca1-194">Par défaut, ce champ est défini sur la date actuelle.</span><span class="sxs-lookup"><span data-stu-id="ddca1-194">By default, this field is set to the current date.</span></span>
    - <span data-ttu-id="ddca1-195">**Collaborateur** – Permet de sélectionner le collaborateur qui a effectué le travail.</span><span class="sxs-lookup"><span data-stu-id="ddca1-195">**Worker** – Select the worker who did the work.</span></span> <span data-ttu-id="ddca1-196">Par défaut, ce champ est défini sur le collaborateur affecté à l'utilisateur actuel.</span><span class="sxs-lookup"><span data-stu-id="ddca1-196">By default, this field is set to the worker that is assigned to the current user.</span></span>
    - <span data-ttu-id="ddca1-197">**Heures de l'opération** - Saisissez le nombre d'heures travaillées sur l'opération sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="ddca1-197">**Operation hours** – Enter the number of hours that were worked on the selected operation.</span></span>
    - <span data-ttu-id="ddca1-198">**Facturé** - Cochez cette case si le temps a été facturé à un client ou fournisseur au moyen d'une facture.</span><span class="sxs-lookup"><span data-stu-id="ddca1-198">**Invoiced** – Select this check box if the time has been charged to a customer or vendor on an invoice.</span></span>

    > [!NOTE]
    > <span data-ttu-id="ddca1-199">Vous pouvez consulter le coût dans le champ **Coût** sur l'onglet **Général**. Le coût est calculé en utilisant le taux que vous définissez sur la page **Paramètres de gestion des stocks**.</span><span class="sxs-lookup"><span data-stu-id="ddca1-199">You can view the cost in the **Cost** field on the **General** tab. The cost is calculated by using the rate that you define on the **Inventory management parameters** page.</span></span>

1. <span data-ttu-id="ddca1-200">Répétez l'étape précédente pour chaque feuille de temps que vous devez ajouter.</span><span class="sxs-lookup"><span data-stu-id="ddca1-200">Repeat the previous step for each additional timesheet line that you must add.</span></span>
1. <span data-ttu-id="ddca1-201">Fermez les pages.</span><span class="sxs-lookup"><span data-stu-id="ddca1-201">Close the pages.</span></span>

> [!NOTE]
> <span data-ttu-id="ddca1-202">Le montant dans le champ **Coût** est automatiquement additionné pour toutes les feuilles de temps et ajouté à tout autre montant dans le champ **Coût** sur la page **Opérations connexes**.</span><span class="sxs-lookup"><span data-stu-id="ddca1-202">The amount in the **Cost** field is summed for all timesheet lines and added to any other amounts in the **Cost** field on the **Related operations** page.</span></span>

## <a name="add-a-correction-to-a-nonconformance"></a><span data-ttu-id="ddca1-203">Ajouter une correction à une non-conformité</span><span class="sxs-lookup"><span data-stu-id="ddca1-203">Add a correction to a nonconformance</span></span>

<span data-ttu-id="ddca1-204">Pour ajouter une correction à une non-conformité, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="ddca1-204">To add a correction to a nonconformance, follow these steps.</span></span>

1. <span data-ttu-id="ddca1-205">Allez dans **Gestion des stocks \> Tâches périodiques \> Gestion de la qualité \> Non-conformités**.</span><span class="sxs-lookup"><span data-stu-id="ddca1-205">Go to **Inventory management \> Periodic tasks \> Quality management \> Non conformances**.</span></span>
1. <span data-ttu-id="ddca1-206">Dans la liste, localisez et sélectionnez la non-conformité que vous voulez mettre à jour.</span><span class="sxs-lookup"><span data-stu-id="ddca1-206">In the list, select the nonconformance that you want to update.</span></span>

    > [!NOTE]
    > <span data-ttu-id="ddca1-207">Vous ne pouvez ajouter une correction qu'aux non-conformités approuvées.</span><span class="sxs-lookup"><span data-stu-id="ddca1-207">You can add a correction only to nonconformances that are approved.</span></span>

1. <span data-ttu-id="ddca1-208">Sur le volet Actions, sélectionnez **Correction**.</span><span class="sxs-lookup"><span data-stu-id="ddca1-208">On the Action Pane, select **Corrections**.</span></span>
1. <span data-ttu-id="ddca1-209">Dans la page **Corrections**, sur le volet Actions, sélectionnez **Nouveau** pour ajouter une ligne à la grille.</span><span class="sxs-lookup"><span data-stu-id="ddca1-209">On the **Corrections** page, on the Action Pane, select **New** to add a row to the grid.</span></span> <span data-ttu-id="ddca1-210">Définissez ensuite les champs suivants pour la nouvelle ligne :</span><span class="sxs-lookup"><span data-stu-id="ddca1-210">Then set the following fields for the new row:</span></span>

    - <span data-ttu-id="ddca1-211">**Diagnostique** - Sélectionnez le type de diagnostic qui identifie le type de correction que vous créez.</span><span class="sxs-lookup"><span data-stu-id="ddca1-211">**Diagnostic** – Select the diagnostic type that identifies the type of correction that you're creating.</span></span>
    - <span data-ttu-id="ddca1-212">**Collaborateur** – Sélectionnez la personne responsable de la correction.</span><span class="sxs-lookup"><span data-stu-id="ddca1-212">**Worker** – Select the person who is responsible for the correction.</span></span>
    - <span data-ttu-id="ddca1-213">**Priorité de correction** - Sélectionnez une option pour indiquer comment la correction doit être priorisée (priorité *Faible*,*Normale*, ou alors *Haute*).</span><span class="sxs-lookup"><span data-stu-id="ddca1-213">**Correction priority** – Select an option to indicate how the correction should be prioritized (*Low*, *Normal*, or *High*).</span></span>
    - <span data-ttu-id="ddca1-214">**Date demandée** - Saisissez la date à laquelle l'action corrective a été demandée.</span><span class="sxs-lookup"><span data-stu-id="ddca1-214">**Requested date** – Enter the date when the corrective action was requested.</span></span>
    - <span data-ttu-id="ddca1-215">**Date prévue** - Entrez la date à laquelle la correction devrait être terminée.</span><span class="sxs-lookup"><span data-stu-id="ddca1-215">**Planned date** – Enter the date when the correction is expected to be completed.</span></span>
    - <span data-ttu-id="ddca1-216">**Solution a court terme** - Cochez cette case si l'action corrective ne corrige la non-conformité que pendant une courte période.</span><span class="sxs-lookup"><span data-stu-id="ddca1-216">**Short term solution** – Select this check box if the corrective action corrects the nonconformance only for a short time.</span></span>

1. <span data-ttu-id="ddca1-217">Fermez les pages.</span><span class="sxs-lookup"><span data-stu-id="ddca1-217">Close the pages.</span></span>

## <a name="mark-a-correction-as-completed"></a><span data-ttu-id="ddca1-218">Marquer une correction comme terminée</span><span class="sxs-lookup"><span data-stu-id="ddca1-218">Mark a correction as completed</span></span>

<span data-ttu-id="ddca1-219">Pour marquer une correction de non-conformité comme terminée, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="ddca1-219">To mark a nonconformance correction as completed, follow these steps.</span></span>

1. <span data-ttu-id="ddca1-220">Allez dans **Gestion des stocks \> Tâches périodiques \> Gestion de la qualité \> Non-conformités**.</span><span class="sxs-lookup"><span data-stu-id="ddca1-220">Go to **Inventory management \> Periodic tasks \> Quality management \> Non conformances**.</span></span>
1. <span data-ttu-id="ddca1-221">Dans la liste, localisez et sélectionnez la non-conformité que vous voulez mettre à jour.</span><span class="sxs-lookup"><span data-stu-id="ddca1-221">In the list, select the nonconformance that you want to update.</span></span>

    > [!NOTE]
    > <span data-ttu-id="ddca1-222">Vous ne pouvez ajouter une correction qu'aux non-conformités approuvées.</span><span class="sxs-lookup"><span data-stu-id="ddca1-222">You can add a correction only to nonconformances that are approved.</span></span>

1. <span data-ttu-id="ddca1-223">Sur le volet Actions, sélectionnez **Correction**.</span><span class="sxs-lookup"><span data-stu-id="ddca1-223">On the Action Pane, select **Corrections**.</span></span>
1. <span data-ttu-id="ddca1-224">Sur la page **Corrections**, dans la grille, sélectionnez la correction que vous souhaitez marquer comme terminée.</span><span class="sxs-lookup"><span data-stu-id="ddca1-224">On the **Corrections** page, in the grid, select the correction that you want to mark as completed.</span></span>
1. <span data-ttu-id="ddca1-225">Dans le volet Actions, sélectionnez **Marquer comme terminé**.</span><span class="sxs-lookup"><span data-stu-id="ddca1-225">On the Action Pane, select **Mark complete**.</span></span>
1. <span data-ttu-id="ddca1-226">Vous êtes invité à confirmer la sélection.</span><span class="sxs-lookup"><span data-stu-id="ddca1-226">You're prompted to confirm your selection.</span></span> <span data-ttu-id="ddca1-227">Cliquez sur **OK** pour continuer.</span><span class="sxs-lookup"><span data-stu-id="ddca1-227">Select **OK** to continue.</span></span> <span data-ttu-id="ddca1-228">Le champ **Date et heure de fin** est défini sur la date et l'heure actuelles, et la case à cocher **Terminé** est cochée.</span><span class="sxs-lookup"><span data-stu-id="ddca1-228">The **Completion date and time** field is set to the current date and time, and the **Completed** check box is selected.</span></span>
1. <span data-ttu-id="ddca1-229">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="ddca1-229">Close the page.</span></span>

## <a name="reopen-a-completed-correction"></a><span data-ttu-id="ddca1-230">Rouvrir une correction terminée</span><span class="sxs-lookup"><span data-stu-id="ddca1-230">Reopen a completed correction</span></span>

<span data-ttu-id="ddca1-231">Pour rouvrir une correction terminée, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="ddca1-231">To reopen a completed correction, follow these steps.</span></span>

1. <span data-ttu-id="ddca1-232">Allez dans **Gestion des stocks \> Tâches périodiques \> Gestion de la qualité \> Non-conformités**.</span><span class="sxs-lookup"><span data-stu-id="ddca1-232">Go to **Inventory management \> Periodic tasks \> Quality management \> Non conformances**.</span></span>
1. <span data-ttu-id="ddca1-233">Dans la liste, localisez et sélectionnez la non-conformité que vous voulez mettre à jour.</span><span class="sxs-lookup"><span data-stu-id="ddca1-233">In the list, select the nonconformance that you want to update.</span></span>
1. <span data-ttu-id="ddca1-234">Sur le volet Actions, sélectionnez **Correction**.</span><span class="sxs-lookup"><span data-stu-id="ddca1-234">On the Action pane, select **Corrections**.</span></span>
1. <span data-ttu-id="ddca1-235">Sur la page **Corrections**, dans la grille, sélectionnez la correction que vous souhaitez rouvrir.</span><span class="sxs-lookup"><span data-stu-id="ddca1-235">On the **Corrections** page, in the grid, select the correction that you want to reopen.</span></span>
1. <span data-ttu-id="ddca1-236">Dans le volet Actions, sélectionnez **Rouvrir**.</span><span class="sxs-lookup"><span data-stu-id="ddca1-236">On the Action Pane, select **Reopen**.</span></span>
1. <span data-ttu-id="ddca1-237">Vous êtes invité à confirmer la sélection.</span><span class="sxs-lookup"><span data-stu-id="ddca1-237">You're prompted to confirm your selection.</span></span> <span data-ttu-id="ddca1-238">Cliquez sur **OK** pour continuer.</span><span class="sxs-lookup"><span data-stu-id="ddca1-238">Select **OK** to continue.</span></span> <span data-ttu-id="ddca1-239">La valeur est effacée du champ **Date et heure de fin**, et la case à cocher **Terminé** est désactivée.</span><span class="sxs-lookup"><span data-stu-id="ddca1-239">The value is cleared from the **Completion date and time** field, and the **Completed** check box is cleared.</span></span>
1. <span data-ttu-id="ddca1-240">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="ddca1-240">Close the page.</span></span>

<span data-ttu-id="ddca1-241">Vous pouvez désormais apporter des modifications ou des mises à jour supplémentaires à la correction.</span><span class="sxs-lookup"><span data-stu-id="ddca1-241">You can now make additional edits or updates to the correction.</span></span> <span data-ttu-id="ddca1-242">Lorsque vous avez terminé, vous pouvez marquer à nouveau la correction comme terminée.</span><span class="sxs-lookup"><span data-stu-id="ddca1-242">When you've finished, you can mark the correction as completed again.</span></span>

## <a name="close-a-nonconformance"></a><span data-ttu-id="ddca1-243">Clôturer une non-conformité</span><span class="sxs-lookup"><span data-stu-id="ddca1-243">Close a nonconformance</span></span>

<span data-ttu-id="ddca1-244">Pour fermer une non-conformité, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="ddca1-244">To close a nonconformance, follow these steps.</span></span>

1. <span data-ttu-id="ddca1-245">Allez dans **Gestion des stocks \> Tâches périodiques \> Gestion de la qualité \> Ordres de qualité**.</span><span class="sxs-lookup"><span data-stu-id="ddca1-245">Go to **Inventory management \> Periodic tasks \> Quality management \> Quality orders**.</span></span>
1. <span data-ttu-id="ddca1-246">Sélectionnez un ordre de qualité dans la grille.</span><span class="sxs-lookup"><span data-stu-id="ddca1-246">Select a quality order in the grid.</span></span>
1. <span data-ttu-id="ddca1-247">Dans le volet Actions, sélectionnez **Recherches \> Non-conformités**.</span><span class="sxs-lookup"><span data-stu-id="ddca1-247">On the Action Pane, select **Inquiries \> Non conformances**.</span></span>
1. <span data-ttu-id="ddca1-248">Sur la page **Non-conformités**, sélectionnez la non-conformité cible dans la grille.</span><span class="sxs-lookup"><span data-stu-id="ddca1-248">On the **Non conformances** page, select the target nonconformance in the grid.</span></span>
1. <span data-ttu-id="ddca1-249">Dans le volet Actions, sélectionnez **Fonctions \> Clôturer la non-conformité**.</span><span class="sxs-lookup"><span data-stu-id="ddca1-249">On the Action Pane, select **Functions \> Close non conformance**.</span></span>
1. <span data-ttu-id="ddca1-250">Vous êtes invité à confirmer la sélection.</span><span class="sxs-lookup"><span data-stu-id="ddca1-250">You're prompted to confirm your selection.</span></span> <span data-ttu-id="ddca1-251">Sélectionnez **Oui** pour continuer.</span><span class="sxs-lookup"><span data-stu-id="ddca1-251">Select **Yes** to continue.</span></span>
1. <span data-ttu-id="ddca1-252">Fermez les pages.</span><span class="sxs-lookup"><span data-stu-id="ddca1-252">Close the pages.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="ddca1-253">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="ddca1-253">Additional resources</span></span>

- [<span data-ttu-id="ddca1-254">Vue d’ensemble de la gestion de la qualité</span><span class="sxs-lookup"><span data-stu-id="ddca1-254">Quality management overview</span></span>](../quality-management-processes.md)
- [<span data-ttu-id="ddca1-255">Activer la gestion de la qualité et de la non-conformité</span><span class="sxs-lookup"><span data-stu-id="ddca1-255">Enable quality and nonconformance management</span></span>](../enable-quality-management.md)
- [<span data-ttu-id="ddca1-256">Collaborateurs chargés d'approuver les non-conformités</span><span class="sxs-lookup"><span data-stu-id="ddca1-256">Workers responsible for approving nonconformances</span></span>](../quality-responsible-workers.md)
- [<span data-ttu-id="ddca1-257">Zones de quarantaine pour les non-conformités</span><span class="sxs-lookup"><span data-stu-id="ddca1-257">Quarantine zones for nonconformances</span></span>](../quality-quarantine-zones.md)
- [<span data-ttu-id="ddca1-258">Types de diagnostic pour les non-conformités</span><span class="sxs-lookup"><span data-stu-id="ddca1-258">Diagnostic types for nonconformances</span></span>](../quality-diagnostic-types.md)
- [<span data-ttu-id="ddca1-259">Frais de qualité pour les non-conformités</span><span class="sxs-lookup"><span data-stu-id="ddca1-259">Quality charges for nonconformances</span></span>](../quality-charges.md)
- [<span data-ttu-id="ddca1-260">Opérations pour les non-conformités</span><span class="sxs-lookup"><span data-stu-id="ddca1-260">Operations for nonconformances</span></span>](../quality-operations.md)
- [<span data-ttu-id="ddca1-261">Gestion de la qualité pour les processus d'entrepôt</span><span class="sxs-lookup"><span data-stu-id="ddca1-261">Quality management for warehouse processes</span></span>](../quality-management-for-warehouses-processes.md)

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
