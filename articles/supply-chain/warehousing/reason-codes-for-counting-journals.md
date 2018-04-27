---
title: Codes motif d'inventaire de stock
description: "Cette rubrique décrit comment paramétrer et appliquer des codes motif pour les tâches d'inventaire."
author: Mirzaab
manager: AnnBe
ms.date: 03/15/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: InventCountingReasonCodePolicy
audience: Application User
ms.reviewer: bis
ms.search.scope: Core, Operations
ms.custom: 1705903
ms.assetid: 427e01b3-4968-4cff-9b85-1717530f72e4
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 8.0.0
ms.translationtype: HT
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: fe01425fa236655731e6e0723f3a1e57c05035cc
ms.contentlocale: fr-fr
ms.lasthandoff: 04/13/2018

---

# <a name="reason-codes-for-inventory-counting"></a><span data-ttu-id="56f5b-103">Codes motif d'inventaire de stock</span><span class="sxs-lookup"><span data-stu-id="56f5b-103">Reason codes for inventory counting</span></span>

[!INCLUDE [banner](../includes/banner.md)]

<span data-ttu-id="56f5b-104">Les codes motif permettent d'analyser les résultats d'un processus d'inventaire et les écarts qui surviennent lors de ce processus.</span><span class="sxs-lookup"><span data-stu-id="56f5b-104">Reason codes let you analyze the results of a counting process and any discrepancies that occur during that process.</span></span> <span data-ttu-id="56f5b-105">Vous pouvez indiquer le motif du comptage, tel qu'une palette brisée ou un ajustement du stock basé sur des exemples de stock.</span><span class="sxs-lookup"><span data-stu-id="56f5b-105">You can specify the reason for doing the count, such as a broken pallet or a stock adjustment that is based on inventory samples.</span></span>

## <a name="recommendation"></a><span data-ttu-id="56f5b-106">Recommandation</span><span class="sxs-lookup"><span data-stu-id="56f5b-106">Recommendation</span></span>

<span data-ttu-id="56f5b-107">Avant de paramétrer le système, nous vous recommandons de définir une stratégie pour l'utilisation des codes motif.</span><span class="sxs-lookup"><span data-stu-id="56f5b-107">Before you set up the system, we recommend that you define a strategy for working with reason codes.</span></span> <span data-ttu-id="56f5b-108">Par exemple, essayez de répondre aux questions suivantes :</span><span class="sxs-lookup"><span data-stu-id="56f5b-108">For example, try to answer the following questions:</span></span>

- <span data-ttu-id="56f5b-109">Les codes motif doivent-ils être obligatoires dans les entrepôts ?</span><span class="sxs-lookup"><span data-stu-id="56f5b-109">Should reason codes be mandatory on warehouses?</span></span>
- <span data-ttu-id="56f5b-110">Les codes motif doivent-ils être obligatoires ou facultatifs pour certains articles ?</span><span class="sxs-lookup"><span data-stu-id="56f5b-110">Should reason codes be mandatory or optional on some items?</span></span>
- <span data-ttu-id="56f5b-111">De combien de codes motif avez-vous besoin ?</span><span class="sxs-lookup"><span data-stu-id="56f5b-111">How many reason codes do you require?</span></span>
- <span data-ttu-id="56f5b-112">Comment les utilisateurs des scanneurs de code-barres doivent-ils utiliser les codes motif ?</span><span class="sxs-lookup"><span data-stu-id="56f5b-112">How should users of barcode scanners use reason codes?</span></span> <span data-ttu-id="56f5b-113">Les codes motif doivent-ils être présélectionnés, obligatoires, ou non modifiables ?</span><span class="sxs-lookup"><span data-stu-id="56f5b-113">Should the reason codes be preselected, mandatory, or not editable?</span></span>
- <span data-ttu-id="56f5b-114">Les magasiniers ont-ils besoin de différents comportements de code motif sur les scanneurs mobiles ?</span><span class="sxs-lookup"><span data-stu-id="56f5b-114">Do warehouse workers require different reason code behavior on mobile scanners?</span></span> <span data-ttu-id="56f5b-115">Si la réponse est oui, vous pouvez créer plusieurs éléments de menu et les affecter à différentes personnes.</span><span class="sxs-lookup"><span data-stu-id="56f5b-115">If the answer is yes, you can create more menu items and assign them to different people.</span></span>

## <a name="where-reason-codes-apply"></a><span data-ttu-id="56f5b-116">Lorsque des codes motif s'appliquent</span><span class="sxs-lookup"><span data-stu-id="56f5b-116">Where reason codes apply</span></span>

<span data-ttu-id="56f5b-117">Vous pouvez créer plusieurs stratégies de code motif, et chaque stratégie de code motif peut comporter deux stratégies de code motif d'inventaire.</span><span class="sxs-lookup"><span data-stu-id="56f5b-117">You can create multiple reason code policies, and each reason code policy can have two counting reason code policies.</span></span> <span data-ttu-id="56f5b-118">Les stratégies de code motif d'inventaire peuvent être utilisées au niveau de l'entrepôt ou au niveau de l'article.</span><span class="sxs-lookup"><span data-stu-id="56f5b-118">The counting reason code policies can be used at the warehouse level or the item level.</span></span>

## <a name="set-up-reason-code-policies"></a><span data-ttu-id="56f5b-119">Paramétrer des stratégies de codes motif</span><span class="sxs-lookup"><span data-stu-id="56f5b-119">Set up reason code policies</span></span>

1. <span data-ttu-id="56f5b-120">Sélectionnez **Gestion des stocks** \> **Paramétrage** \> **Stock** \> **Stratégies de code motif d'inventaire**, puis créez une stratégie de code motif.</span><span class="sxs-lookup"><span data-stu-id="56f5b-120">Select **Inventory management** \> **Setup** \> **Inventory** \> **Counting reason code policies**, and create a new reason code policy.</span></span>
2. <span data-ttu-id="56f5b-121">Dans le champ **Type de code motif d'inventaire**, sélectionnez **Obligatoire** ou **Facultatif** pour spécifier si la sélection d'un code motif doit être une action facultative ou obligatoire dans l'un des journaux d'inventaire suivants :</span><span class="sxs-lookup"><span data-stu-id="56f5b-121">In the **Counting reason code type** field, select either **Mandatory** or **Optional** to specify whether selection of a reason code should be an optional or mandatory action in one of the following counting journals:</span></span>

    - <span data-ttu-id="56f5b-122">Inventaire tournant (appareil mobile)</span><span class="sxs-lookup"><span data-stu-id="56f5b-122">Cycle Count (mobile device)</span></span>
    - <span data-ttu-id="56f5b-123">Inventaire ponctuel (appareil mobile)</span><span class="sxs-lookup"><span data-stu-id="56f5b-123">Spot Count (mobile device)</span></span>
    - <span data-ttu-id="56f5b-124">Inventaire de seuil (appareil mobile)</span><span class="sxs-lookup"><span data-stu-id="56f5b-124">Threshold Count (mobile device)</span></span>
    - <span data-ttu-id="56f5b-125">Ajustement en entrée (appareil mobile)</span><span class="sxs-lookup"><span data-stu-id="56f5b-125">Adjustment In (mobile device)</span></span>
    - <span data-ttu-id="56f5b-126">Ajustement en sortie (appareil mobile)</span><span class="sxs-lookup"><span data-stu-id="56f5b-126">Adjustment Out (mobile device)</span></span>
    - <span data-ttu-id="56f5b-127">Journal d'inventaire (Rich Client)</span><span class="sxs-lookup"><span data-stu-id="56f5b-127">Counting Journal (rich client)</span></span>

<span data-ttu-id="56f5b-128">Vous pouvez également paramétrer des codes motif pour des entrepôts et des produits individuels.</span><span class="sxs-lookup"><span data-stu-id="56f5b-128">You can also set up reason codes for individual warehouses and for products.</span></span> <span data-ttu-id="56f5b-129">Le paramétrage de codes motif pour les produits peut ignorer le paramétrage des entrepôts.</span><span class="sxs-lookup"><span data-stu-id="56f5b-129">The reason code setup for products can disregard the setup for warehouses.</span></span>

## <a name="mandatory-reason-codes"></a><span data-ttu-id="56f5b-130">Codes motif obligatoires</span><span class="sxs-lookup"><span data-stu-id="56f5b-130">Mandatory reason codes</span></span>

<span data-ttu-id="56f5b-131">Si le paramètre **Obligatoire** est défini dans la configuration des codes motif pour les entrepôts et les articles, le journal d'inventaire ne peut pas être rempli et clôturé tant qu'un code motif n'est pas fourni.</span><span class="sxs-lookup"><span data-stu-id="56f5b-131">If the **Mandatory** parameter is set in the configuration of reason codes for warehouses or items, the counting journal can't be completed and closed until a reason code is provided.</span></span>

### <a name="set-up-reason-codes-for-warehouses"></a><span data-ttu-id="56f5b-132">Définir les codes motif pour des entrepôts</span><span class="sxs-lookup"><span data-stu-id="56f5b-132">Set up reason codes for warehouses</span></span>

1. <span data-ttu-id="56f5b-133">Sélectionnez **Gestion des stocks** \> **Paramétrage** \> **Décomposition du stock** \> **Entrepôts**.</span><span class="sxs-lookup"><span data-stu-id="56f5b-133">Select **Inventory Management** \> **Setup** \> **Inventory breakdown** \> **Warehouses**.</span></span>
2. <span data-ttu-id="56f5b-134">Dans l'onglet **Entrepôt**, dans le champ **Stratégie de code motif d'inventaire**, sélectionnez l'une des options suivantes :</span><span class="sxs-lookup"><span data-stu-id="56f5b-134">On the **Warehouse** tab, in the **Counting reason code policy** field, select one of the following options:</span></span>

    - <span data-ttu-id="56f5b-135">**Vide** – Le paramètre défini pour l'article est utilisé pour déterminer si les journaux d'inventaire sont obligatoires pour le produit.</span><span class="sxs-lookup"><span data-stu-id="56f5b-135">**Blank** – The parameter that is set up for the item is used to determine whether counting journals are mandatory for the product.</span></span>
    - <span data-ttu-id="56f5b-136">**Obligatoire** – Un code motif est toujours requis dans les journaux d'inventaire pour l'entrepôt.</span><span class="sxs-lookup"><span data-stu-id="56f5b-136">**Mandatory** – A reason code is always required on counting journals for the warehouse.</span></span>
    - <span data-ttu-id="56f5b-137">**Facultatif** – Un code motif n'est pas requis dans les journaux d'inventaire pour l'entrepôt.</span><span class="sxs-lookup"><span data-stu-id="56f5b-137">**Optional** – A reason code isn't required on counting journals for the warehouse.</span></span>

### <a name="set-up-reason-codes-for-products"></a><span data-ttu-id="56f5b-138">Définir les codes motif pour des produits</span><span class="sxs-lookup"><span data-stu-id="56f5b-138">Set up reason codes for products</span></span>

1. <span data-ttu-id="56f5b-139">Sélectionnez **Gestion des informations sur les produits** \> **Produits** \> **Produits lancés**.</span><span class="sxs-lookup"><span data-stu-id="56f5b-139">Select **Product information management** \> **Products** \> **Released products**.</span></span>
2. <span data-ttu-id="56f5b-140">Dans l'onglet **Produit**, sélectionnez **Stratégie de code motif d'inventaire**, puis l'une des options suivantes :</span><span class="sxs-lookup"><span data-stu-id="56f5b-140">On the **Product** tab, select **Counting reason code policy**, and then select one of the following options:</span></span>

    - <span data-ttu-id="56f5b-141">**Vide** – Le paramètre défini pour l'entrepôt est utilisé pour déterminer si les journaux d'inventaire sont obligatoires pour le produit.</span><span class="sxs-lookup"><span data-stu-id="56f5b-141">**Blank** – The parameter that is set up for the warehouse is used to determine whether counting journals are mandatory for the product.</span></span>
    - <span data-ttu-id="56f5b-142">**Obligatoire** – Un code motif est toujours requis dans les journaux d'inventaire pour le produit.</span><span class="sxs-lookup"><span data-stu-id="56f5b-142">**Mandatory** – A reason code is always required on counting journals for the product.</span></span> <span data-ttu-id="56f5b-143">Ce paramètre remplace le paramètre de code motif au niveau de l'entrepôt.</span><span class="sxs-lookup"><span data-stu-id="56f5b-143">This setting overrides any reason code setting at the warehouse level.</span></span>
    - <span data-ttu-id="56f5b-144">**Facultatif** – Un code motif n'est pas requis dans les journaux d'inventaire pour le produit.</span><span class="sxs-lookup"><span data-stu-id="56f5b-144">**Optional** – A reason code isn't required on counting journals for the product.</span></span> <span data-ttu-id="56f5b-145">Ce paramètre remplace le paramètre de code motif au niveau de l'entrepôt.</span><span class="sxs-lookup"><span data-stu-id="56f5b-145">This setting overrides any reason code setting at the warehouse level.</span></span>

### <a name="use-reason-codes-in-counting-journals"></a><span data-ttu-id="56f5b-146">Utiliser des codes motif dans les journaux d'inventaire</span><span class="sxs-lookup"><span data-stu-id="56f5b-146">Use reason codes in counting journals</span></span>

<span data-ttu-id="56f5b-147">Dans un journal d'inventaire, vous pouvez ajouter des codes motif pour les types suivants :</span><span class="sxs-lookup"><span data-stu-id="56f5b-147">In a counting journal, you can add reason codes for counts of the following types:</span></span>

- <span data-ttu-id="56f5b-148">Inventaire tournant</span><span class="sxs-lookup"><span data-stu-id="56f5b-148">Cycle Count</span></span>
- <span data-ttu-id="56f5b-149">Inventaire ponctuel</span><span class="sxs-lookup"><span data-stu-id="56f5b-149">Spot Count</span></span>
- <span data-ttu-id="56f5b-150">Inventaire de seuil</span><span class="sxs-lookup"><span data-stu-id="56f5b-150">Threshold Count</span></span>
- <span data-ttu-id="56f5b-151">Ajustement en entrée</span><span class="sxs-lookup"><span data-stu-id="56f5b-151">Adjustment In</span></span>
- <span data-ttu-id="56f5b-152">Ajustement en sortie</span><span class="sxs-lookup"><span data-stu-id="56f5b-152">Adjustment Out</span></span>

<span data-ttu-id="56f5b-153">Les codes motif sont ajoutés aux lignes de journal dans les journaux d'inventaire de type **Journal d'inventaire**.</span><span class="sxs-lookup"><span data-stu-id="56f5b-153">Reason codes are added to the journal lines in counting journals of the **Counting journal** type.</span></span>

1. <span data-ttu-id="56f5b-154">Sélectionnez **Gestion des stocks** \> **Entrées de journal** \> **Inventaire des articles** \> **Inventaire**.</span><span class="sxs-lookup"><span data-stu-id="56f5b-154">Select **Inventory management** \> **Journal entries** \> **Item counting** \> **Counting**.</span></span>
2. <span data-ttu-id="56f5b-155">Dans les détails de ligne du journal d'inventaire, dans le champ **Code motif d'inventaire**, sélectionnez une option.</span><span class="sxs-lookup"><span data-stu-id="56f5b-155">In the line details of the counting journal, in the **Counting reason code** field, select an option.</span></span>

### <a name="view-the-counting-history-as-its-recorded-by-reason-codes"></a><span data-ttu-id="56f5b-156">Affichez l'historique d'inventaire tel qu'il est enregistré par codes motif</span><span class="sxs-lookup"><span data-stu-id="56f5b-156">View the counting history as it's recorded by reason codes</span></span>

- <span data-ttu-id="56f5b-157">Sélectionnez **Gestion des stocks** \> **Recherches et états** \> **Historique d'inventaire**, puis, dans le champ **Code motif d'inventaire**, affichez l'historique d'inventaire enregistré via un code motif.</span><span class="sxs-lookup"><span data-stu-id="56f5b-157">Select **Inventory management** \> **Inquiries and reports** \> **Counting history**, and then, in the **Counting reason code** field, view the counting history that has been recorded through a reason code.</span></span>

### <a name="use-a-reason-code-for-a-quantity-adjustment"></a><span data-ttu-id="56f5b-158">Utiliser un code motif pour un ajustement de quantité</span><span class="sxs-lookup"><span data-stu-id="56f5b-158">Use a reason code for a quantity adjustment</span></span>

1. <span data-ttu-id="56f5b-159">Dans la page **Stock disponible**, sélectionnez **Ajuster la quantité**.</span><span class="sxs-lookup"><span data-stu-id="56f5b-159">On the **On-hand inventory** page, select **Adjust quantity**.</span></span> <span data-ttu-id="56f5b-160">Vous pouvez ouvrir la page **Stock disponible** de plusieurs façons.</span><span class="sxs-lookup"><span data-stu-id="56f5b-160">You can open the **On-hand inventory** page in several ways.</span></span> <span data-ttu-id="56f5b-161">Par exemple, sélectionnez **Gestion des stocks** \> **Recherches et états** \> **Stock disponible**.</span><span class="sxs-lookup"><span data-stu-id="56f5b-161">For example, select **Inventory management** \> **Inquiries and reports** \> **On-hand inventory**.</span></span>
2. <span data-ttu-id="56f5b-162">Sélectionnez **Ajuster la quantité**, puis, dans le champ **Code motif d'inventaire**, sélectionnez un code motif.</span><span class="sxs-lookup"><span data-stu-id="56f5b-162">Select **Adjust quantity**, and then, in the **Counting reason code** field, select a reason code.</span></span>

### <a name="configure-reason-codes-for-mobile-device-menu-items"></a><span data-ttu-id="56f5b-163">Configurer des codes motif pour des éléments du menu d'appareil mobile</span><span class="sxs-lookup"><span data-stu-id="56f5b-163">Configure reason codes for mobile device menu items</span></span>

<span data-ttu-id="56f5b-164">Vous pouvez configurer des codes motif pour tous les types d'inventaire sur un élément du menu d'appareil mobile.</span><span class="sxs-lookup"><span data-stu-id="56f5b-164">You can configure reason codes for any type of count on a mobile device menu item.</span></span> <span data-ttu-id="56f5b-165">La configuration de l'élément de menu d'appareil mobile inclut les informations suivantes :</span><span class="sxs-lookup"><span data-stu-id="56f5b-165">The configuration of the mobile device menu item includes the following information:</span></span>

- <span data-ttu-id="56f5b-166">Si le code motif s'affiche pour l'utilisateur de l'appareil mobile pendant l'inventaire.</span><span class="sxs-lookup"><span data-stu-id="56f5b-166">Whether the reason code is shown to the mobile device worker during counting.</span></span>
- <span data-ttu-id="56f5b-167">Le code motif par défaut qui s'affiche sur un élément du menu d'appareil mobile.</span><span class="sxs-lookup"><span data-stu-id="56f5b-167">The default reason code that is shown on a mobile device menu item.</span></span>
- <span data-ttu-id="56f5b-168">Si l'utilisateur peut modifier le code motif.</span><span class="sxs-lookup"><span data-stu-id="56f5b-168">Whether the user can edit the reason code.</span></span>

### <a name="set-up-reason-codes-on-a-mobile-device"></a><span data-ttu-id="56f5b-169">Paramétrer des codes motif sur un appareil mobile</span><span class="sxs-lookup"><span data-stu-id="56f5b-169">Set up reason codes on a mobile device</span></span>

1. <span data-ttu-id="56f5b-170">Sélectionnez **Gestion des entrepôts** \> **Configuration** \> **Appareil mobile** \> **Options de menu d'appareil mobile**.</span><span class="sxs-lookup"><span data-stu-id="56f5b-170">Select **Warehouse management** \> **Setup** \> **Mobile device** \> **Mobile device menu items**.</span></span>
2. <span data-ttu-id="56f5b-171">Dans l'onglet **Inventaire tournant**, sélectionnez **Inventaire tournant**.</span><span class="sxs-lookup"><span data-stu-id="56f5b-171">On the **Cycle count** tab, select **Cycle counting**.</span></span>
3. <span data-ttu-id="56f5b-172">Dans le champ **Code motif d'inventaire par défaut**, définissez le code motif par défaut à enregistrer lorsque l'inventaire est effectué à l'aide de l'élément de menu de l'appareil mobile.</span><span class="sxs-lookup"><span data-stu-id="56f5b-172">In the **Default counting reason code** field, set the default reason code that should be recorded when counting is done by using the mobile device menu item.</span></span>
4. <span data-ttu-id="56f5b-173">Dans le champ **Afficher le code motif d'inventaire**, sélectionnez **Ligne** pour afficher le code motif après chaque écart enregistré.</span><span class="sxs-lookup"><span data-stu-id="56f5b-173">In the **Display counting reason code** field, select **Line** to show the reason code after each variance is recorded.</span></span> <span data-ttu-id="56f5b-174">Sinon, sélectionnez **Masquer** si le code motif ne doit pas être affiché.</span><span class="sxs-lookup"><span data-stu-id="56f5b-174">Alternatively, select **Hide** if the reason code shouldn't be shown.</span></span>
5. <span data-ttu-id="56f5b-175">Définissez l'option **Modifier le code motif d'inventaire** sur **Oui** ou **Non**.</span><span class="sxs-lookup"><span data-stu-id="56f5b-175">Set the **Edit counting reason code** option to either **Yes** or **No**.</span></span> <span data-ttu-id="56f5b-176">Si vous définissez cette option sur **Oui**, le collaborateur peut modifier le code motif lorsqu'il est affiché sur l'appareil mobile pendant l'inventaire.</span><span class="sxs-lookup"><span data-stu-id="56f5b-176">If you set this option to **Yes**, the worker can edit the reason code when it's shown on the mobile device during counting.</span></span>

> [!NOTE]
> <span data-ttu-id="56f5b-177">Le bouton **Inventaire tournant** peut être activé sur n'importe quel élément de menu d'appareil mobile sur lequel l'inventaire peut être effectué.</span><span class="sxs-lookup"><span data-stu-id="56f5b-177">The **Cycle counting** button can be enabled on any mobile device menu item where counting can be done.</span></span> <span data-ttu-id="56f5b-178">Les éléments de menu comprennent les inventaires ponctuels, le travail dirigé par l'utilisateur, et le travail dirigé par le système.</span><span class="sxs-lookup"><span data-stu-id="56f5b-178">Example include the menu items for spot counts, user-directed work, and system-directed work.</span></span>

## <a name="cycle-count-approvals"></a><span data-ttu-id="56f5b-179">Approbations d'inventaire tournant</span><span class="sxs-lookup"><span data-stu-id="56f5b-179">Cycle count approvals</span></span>

<span data-ttu-id="56f5b-180">Avant qu'un inventaire soit approuvé, l'utilisateur peut modifier le code motif associé à l'inventaire.</span><span class="sxs-lookup"><span data-stu-id="56f5b-180">Before a count is approved, the user can change the reason code that is associated with the count.</span></span> <span data-ttu-id="56f5b-181">Lorsque l'inventaire est approuvé, le code motif est entré sur les lignes du journal d'inventaire.</span><span class="sxs-lookup"><span data-stu-id="56f5b-181">When the count is approved, the reason code is entered on the counting journal lines.</span></span>

### <a name="modify-cycle-count-approvals"></a><span data-ttu-id="56f5b-182">Modifier les approbations d'inventaire tournant</span><span class="sxs-lookup"><span data-stu-id="56f5b-182">Modify cycle count approvals</span></span>

1. <span data-ttu-id="56f5b-183">Sélectionnez **Gestion des entrepôts** \> **Inventaire tournant** \> **Travail d'inventaire tournant en attente de révision**.</span><span class="sxs-lookup"><span data-stu-id="56f5b-183">Select **Warehouse management** \> **Cycle counting** \> **Cycle count work pending review**.</span></span>
2. <span data-ttu-id="56f5b-184">Sélectionnez **Inventaire tournant**, puis, dans le champ **Code motif**, sélectionnez un nouveau code motif.</span><span class="sxs-lookup"><span data-stu-id="56f5b-184">Select **Cycle counting**, and then, in the **Reason code** field, select a new reason code.</span></span>

### <a name="modify-the-mobile-device-menu-item-for-adjustment-in-and-adjustment-out"></a><span data-ttu-id="56f5b-185">Modifier l'élément de menu de l'appareil mobile pour l'Ajustement en entrée et l'Ajustement en sortie</span><span class="sxs-lookup"><span data-stu-id="56f5b-185">Modify the mobile device menu item for Adjustment in and Adjustment out</span></span>

1. <span data-ttu-id="56f5b-186">Sélectionnez **Gestion des entrepôts** \> **Paramétrage** \> **Appareil mobile** \> **Options de menu d'appareil mobile**, puis **Ajustement en entrée et Ajustement en sortie**.</span><span class="sxs-lookup"><span data-stu-id="56f5b-186">Select **Warehouse management** \> **Setup** \> **Mobile device** \> **Mobile device menu items**, and then select **Adjustment in and out**.</span></span>
2. <span data-ttu-id="56f5b-187">Définissez l'option **Utiliser un travail existant** sur **Non**.</span><span class="sxs-lookup"><span data-stu-id="56f5b-187">Set the **Use existing work** option to **No**.</span></span>
3. <span data-ttu-id="56f5b-188">Dans le champ **Processus de création du travail**, sélectionnez **Ajustement en entrée**.</span><span class="sxs-lookup"><span data-stu-id="56f5b-188">In the **Work creation process** field, select **Adjustment in**.</span></span>

<span data-ttu-id="56f5b-189">Les champs suivants sont ajoutés aux options du menu de l'appareil mobile si **Ajustement en entrée** ou **Ajustement en sortie** est sélectionné lors du processus de création du travail :</span><span class="sxs-lookup"><span data-stu-id="56f5b-189">The following fields will be added to the mobile device menu item when **Adjustment in** or **Adjustment out** is selected during the work creation process:</span></span>

- <span data-ttu-id="56f5b-190">Code motif d'inventaire par défaut</span><span class="sxs-lookup"><span data-stu-id="56f5b-190">Default counting reason code</span></span>
- <span data-ttu-id="56f5b-191">Afficher le code motif d'inventaire</span><span class="sxs-lookup"><span data-stu-id="56f5b-191">Display counting reason code</span></span>
- <span data-ttu-id="56f5b-192">Modifier le code motif d'inventaire</span><span class="sxs-lookup"><span data-stu-id="56f5b-192">Edit counting reason code</span></span>

