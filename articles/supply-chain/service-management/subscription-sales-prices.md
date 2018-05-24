---
title: Prix de vente des abonnements
description: "Lors de la création d'un abonnement, le prix de vente est calculé à partir du paramétrage de prix de vente défini dans l'écran Prix de vente (abonnement)."
author: YuyuScheller
manager: AnnBe
ms.date: 05/01/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: SMASalespriceSubscription
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 
ms.assetid: 
ms.search.region: Global
ms.author: YuyuScheller
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: d9d462121915ce3f800581a9540dc1ef8f6e785f
ms.contentlocale: fr-fr
ms.lasthandoff: 05/08/2018

---

# <a name="subscription-sales-prices"></a><span data-ttu-id="4fa69-103">Prix de vente des abonnements</span><span class="sxs-lookup"><span data-stu-id="4fa69-103">Subscription sales prices</span></span>   

[!include [banner](../includes/banner.md)]


<span data-ttu-id="4fa69-104">Lors de la création d'un abonnement, le prix de vente est calculé à partir du paramétrage de prix de vente défini dans l'écran **Prix de vente (abonnement)**.</span><span class="sxs-lookup"><span data-stu-id="4fa69-104">When you create a subscription, the sales price is derived from the sales price setup that was created in the **Sales price (subscription)** form.</span></span>

<span data-ttu-id="4fa69-105">L'écran **Prix de vente (abonnement)** permet de créer des prix de vente pour un abonnement spécifique ou pour un champ d'application plus vaste.</span><span class="sxs-lookup"><span data-stu-id="4fa69-105">In the **Sales price (subscription)** form, you can create sales prices for a specific subscription or you can create sales prices that apply more broadly.</span></span> <span data-ttu-id="4fa69-106">Pour un prix de vente s'appliquant à un abonnement, le code période et la devise de l'abonnement doivent être identiques à ceux du prix de vente.</span><span class="sxs-lookup"><span data-stu-id="4fa69-106">For a sales price to be applied to a subscription, the period code and the currency of the subscription must be identical to the period code and the currency of the sales price.</span></span>

<span data-ttu-id="4fa69-107">Si le code période et la devise de l'abonnement et du prix de vente sont identiques, les prix de vente d'abonnement sont sélectionnés en fonction des priorités indiquées dans le tableau suivant.</span><span class="sxs-lookup"><span data-stu-id="4fa69-107">If the period code and currency are identical for the subscription and the sales price, subscription sales prices are selected on the basis of the priorities listed in the following table.</span></span> <span data-ttu-id="4fa69-108">Une cellule vide dans le tableau indique un champ sans valeur et un X indique une valeur égale à celle de l'abonnement à partir duquel la transaction est générée.</span><span class="sxs-lookup"><span data-stu-id="4fa69-108">A blank cell in the table indicates an empty field and an X indicates a value that is equal to the value in the subscription from which the transaction is generated.</span></span>

<table style="width:100%;">
<colgroup>
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="4fa69-109">Priorité</span><span class="sxs-lookup"><span data-stu-id="4fa69-109">Priority</span></span></p></th>
<th><p><span data-ttu-id="4fa69-110"><strong>Catégorie</strong></span><span class="sxs-lookup"><span data-stu-id="4fa69-110"><strong>Category</strong></span></span></p></th>
<th><p><span data-ttu-id="4fa69-111"><strong>ID Projet</strong></span><span class="sxs-lookup"><span data-stu-id="4fa69-111"><strong>Project ID</strong></span></span></p></th>
<th><p><span data-ttu-id="4fa69-112"><strong>Abonnement</strong></span><span class="sxs-lookup"><span data-stu-id="4fa69-112"><strong>Subscription</strong></span></span></p></th>
<th><p><span data-ttu-id="4fa69-113"><strong>Devise de vente</strong></span><span class="sxs-lookup"><span data-stu-id="4fa69-113"><strong>Sales currency</strong></span></span></p></th>
<th><p><span data-ttu-id="4fa69-114"><strong>Code période</strong></span><span class="sxs-lookup"><span data-stu-id="4fa69-114"><strong>Period code</strong></span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4fa69-115">1</span><span class="sxs-lookup"><span data-stu-id="4fa69-115">1</span></span></p></td>
<td><p><span data-ttu-id="4fa69-116">O</span><span class="sxs-lookup"><span data-stu-id="4fa69-116">X</span></span></p></td>
<td><p><span data-ttu-id="4fa69-117">O</span><span class="sxs-lookup"><span data-stu-id="4fa69-117">X</span></span></p></td>
<td><p><span data-ttu-id="4fa69-118">O</span><span class="sxs-lookup"><span data-stu-id="4fa69-118">X</span></span></p></td>
<td><p><span data-ttu-id="4fa69-119">O</span><span class="sxs-lookup"><span data-stu-id="4fa69-119">X</span></span></p></td>
<td><p><span data-ttu-id="4fa69-120">O</span><span class="sxs-lookup"><span data-stu-id="4fa69-120">X</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4fa69-121">2</span><span class="sxs-lookup"><span data-stu-id="4fa69-121">2</span></span></p></td>
<td><p></p></td>
<td><p><span data-ttu-id="4fa69-122">O</span><span class="sxs-lookup"><span data-stu-id="4fa69-122">X</span></span></p></td>
<td><p><span data-ttu-id="4fa69-123">O</span><span class="sxs-lookup"><span data-stu-id="4fa69-123">X</span></span></p></td>
<td><p><span data-ttu-id="4fa69-124">O</span><span class="sxs-lookup"><span data-stu-id="4fa69-124">X</span></span></p></td>
<td><p><span data-ttu-id="4fa69-125">O</span><span class="sxs-lookup"><span data-stu-id="4fa69-125">X</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4fa69-126">3</span><span class="sxs-lookup"><span data-stu-id="4fa69-126">3</span></span></p></td>
<td><p><span data-ttu-id="4fa69-127">O</span><span class="sxs-lookup"><span data-stu-id="4fa69-127">X</span></span></p></td>
<td><p></p></td>
<td><p><span data-ttu-id="4fa69-128">O</span><span class="sxs-lookup"><span data-stu-id="4fa69-128">X</span></span></p></td>
<td><p><span data-ttu-id="4fa69-129">O</span><span class="sxs-lookup"><span data-stu-id="4fa69-129">X</span></span></p></td>
<td><p><span data-ttu-id="4fa69-130">O</span><span class="sxs-lookup"><span data-stu-id="4fa69-130">X</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4fa69-131">4</span><span class="sxs-lookup"><span data-stu-id="4fa69-131">4</span></span></p></td>
<td><p></p></td>
<td><p></p></td>
<td><p><span data-ttu-id="4fa69-132">O</span><span class="sxs-lookup"><span data-stu-id="4fa69-132">X</span></span></p></td>
<td><p><span data-ttu-id="4fa69-133">O</span><span class="sxs-lookup"><span data-stu-id="4fa69-133">X</span></span></p></td>
<td><p><span data-ttu-id="4fa69-134">O</span><span class="sxs-lookup"><span data-stu-id="4fa69-134">X</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4fa69-135">5</span><span class="sxs-lookup"><span data-stu-id="4fa69-135">5</span></span></p></td>
<td><p><span data-ttu-id="4fa69-136">O</span><span class="sxs-lookup"><span data-stu-id="4fa69-136">X</span></span></p></td>
<td><p><span data-ttu-id="4fa69-137">O</span><span class="sxs-lookup"><span data-stu-id="4fa69-137">X</span></span></p></td>
<td><p></p></td>
<td><p><span data-ttu-id="4fa69-138">O</span><span class="sxs-lookup"><span data-stu-id="4fa69-138">X</span></span></p></td>
<td><p><span data-ttu-id="4fa69-139">O</span><span class="sxs-lookup"><span data-stu-id="4fa69-139">X</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4fa69-140">6</span><span class="sxs-lookup"><span data-stu-id="4fa69-140">6</span></span></p></td>
<td><p></p></td>
<td><p><span data-ttu-id="4fa69-141">O</span><span class="sxs-lookup"><span data-stu-id="4fa69-141">X</span></span></p></td>
<td><p></p></td>
<td><p><span data-ttu-id="4fa69-142">O</span><span class="sxs-lookup"><span data-stu-id="4fa69-142">X</span></span></p></td>
<td><p><span data-ttu-id="4fa69-143">O</span><span class="sxs-lookup"><span data-stu-id="4fa69-143">X</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4fa69-144">7</span><span class="sxs-lookup"><span data-stu-id="4fa69-144">7</span></span></p></td>
<td><p><span data-ttu-id="4fa69-145">O</span><span class="sxs-lookup"><span data-stu-id="4fa69-145">X</span></span></p></td>
<td><p></p></td>
<td><p></p></td>
<td><p><span data-ttu-id="4fa69-146">O</span><span class="sxs-lookup"><span data-stu-id="4fa69-146">X</span></span></p></td>
<td><p><span data-ttu-id="4fa69-147">O</span><span class="sxs-lookup"><span data-stu-id="4fa69-147">X</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4fa69-148">8</span><span class="sxs-lookup"><span data-stu-id="4fa69-148">8</span></span></p></td>
<td><p></p></td>
<td><p></p></td>
<td><p></p></td>
<td><p><span data-ttu-id="4fa69-149">O</span><span class="sxs-lookup"><span data-stu-id="4fa69-149">X</span></span></p></td>
<td><p><span data-ttu-id="4fa69-150">O</span><span class="sxs-lookup"><span data-stu-id="4fa69-150">X</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="4fa69-151">Lors de la création de frais d'abonnement, le prix de vente le plus détaillé, voir le tableau ci-dessus, est sélectionné comme prix de vente de l'abonnement.</span><span class="sxs-lookup"><span data-stu-id="4fa69-151">When a subscription fee is created, the sales price with the greatest level of detail, as noted in the table above, is selected as the subscription sales price.</span></span>

## <a name="update-and-index-subscription-sales-prices"></a><span data-ttu-id="4fa69-152">Mise à jour et indexation des prix de vente des abonnements</span><span class="sxs-lookup"><span data-stu-id="4fa69-152">Update and index subscription sales prices</span></span>

<span data-ttu-id="4fa69-153">Vous pouvez mettre à jour le prix de vente des abonnements en mettant à jour le prix de base ou l'indice.</span><span class="sxs-lookup"><span data-stu-id="4fa69-153">You can update the subscription sales price by updating the base price or the index.</span></span> <span data-ttu-id="4fa69-154">Ceux-ci peuvent être mis à jour en entrant un pourcentage ou une nouvelle valeur.</span><span class="sxs-lookup"><span data-stu-id="4fa69-154">You can update by a percentage or to a new value.</span></span>

## <a name="subscription-fee-sales-prices"></a><span data-ttu-id="4fa69-155">Prix de vente des frais d'abonnement</span><span class="sxs-lookup"><span data-stu-id="4fa69-155">Subscription fee sales prices</span></span>

<span data-ttu-id="4fa69-156">Lors de la création de frais d'abonnement, le prix de vente est calculé à partir du paramétrage de prix de vente de l'abonnement.</span><span class="sxs-lookup"><span data-stu-id="4fa69-156">When you create a subscription fee, the sales price is based on the sales price setup of the subscription.</span></span> <span data-ttu-id="4fa69-157">Vous pouvez soit utiliser le prix de base indiqué dans le paramétrage de prix de l'abonnement, soit créer des prix de vente indexés.</span><span class="sxs-lookup"><span data-stu-id="4fa69-157">You can either use the base price from the subscription price setup or create indexed sales prices.</span></span>

## <a name="example"></a><span data-ttu-id="4fa69-158">Exemple</span><span class="sxs-lookup"><span data-stu-id="4fa69-158">Example</span></span>

<span data-ttu-id="4fa69-159">Vous souhaitez paramétrer des prix de vente de 500 EUR pour un nouveau projet 9030.</span><span class="sxs-lookup"><span data-stu-id="4fa69-159">You want to set up subscription sales prices of EUR 500 for a new project 9030.</span></span> <span data-ttu-id="4fa69-160">Dans l'écran **Prix de vente (abonnement)**, créez une ligne de prix de vente d'abonnement comme indiqué dans le tableau suivant :</span><span class="sxs-lookup"><span data-stu-id="4fa69-160">In the **Sales price (subscription)** form, you create a subscription sales price line as indicated in the following table.</span></span>

<table style="width:100%;">
<colgroup>
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="4fa69-161">Valide du</span><span class="sxs-lookup"><span data-stu-id="4fa69-161">Valid from</span></span></p></th>
<th><p><span data-ttu-id="4fa69-162">Catégorie</span><span class="sxs-lookup"><span data-stu-id="4fa69-162">Category</span></span></p></th>
<th><p><span data-ttu-id="4fa69-163">Projet</span><span class="sxs-lookup"><span data-stu-id="4fa69-163">Project</span></span></p></th>
<th><p><span data-ttu-id="4fa69-164">Abonnement</span><span class="sxs-lookup"><span data-stu-id="4fa69-164">Subscription</span></span></p></th>
<th><p><span data-ttu-id="4fa69-165">Code période</span><span class="sxs-lookup"><span data-stu-id="4fa69-165">Period code</span></span></p></th>
<th><p><span data-ttu-id="4fa69-166">Devise de vente</span><span class="sxs-lookup"><span data-stu-id="4fa69-166">Sales currency</span></span></p></th>
<th><p><span data-ttu-id="4fa69-167">Prix de vente</span><span class="sxs-lookup"><span data-stu-id="4fa69-167">Sales price</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4fa69-168">28-08-2006</span><span class="sxs-lookup"><span data-stu-id="4fa69-168">28-08-2006</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="4fa69-169">9030</span><span class="sxs-lookup"><span data-stu-id="4fa69-169">9030</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="4fa69-170">Mois</span><span class="sxs-lookup"><span data-stu-id="4fa69-170">Month</span></span></p></td>
<td><p><span data-ttu-id="4fa69-171">EUR</span><span class="sxs-lookup"><span data-stu-id="4fa69-171">EUR</span></span></p></td>
<td><p><span data-ttu-id="4fa69-172">500</span><span class="sxs-lookup"><span data-stu-id="4fa69-172">500</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="4fa69-173">Notez que les champs **Catégorie** et **Abonnement** sont vides.</span><span class="sxs-lookup"><span data-stu-id="4fa69-173">Note that the **Category** and **Subscription** fields are empty.</span></span>

<span data-ttu-id="4fa69-174">Vous pouvez ensuite créer les abonnements suivants.</span><span class="sxs-lookup"><span data-stu-id="4fa69-174">You then create the following subscriptions.</span></span>

<table style="width:100%;">
<colgroup>
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="4fa69-175">Service récurrent</span><span class="sxs-lookup"><span data-stu-id="4fa69-175">Service subscription</span></span></p></th>
<th><p><span data-ttu-id="4fa69-176">Projet</span><span class="sxs-lookup"><span data-stu-id="4fa69-176">Project</span></span></p></th>
<th><p><span data-ttu-id="4fa69-177">Groupe d'abonnements</span><span class="sxs-lookup"><span data-stu-id="4fa69-177">Subscription group</span></span></p></th>
<th><p><span data-ttu-id="4fa69-178">Catégorie</span><span class="sxs-lookup"><span data-stu-id="4fa69-178">Category</span></span></p></th>
<th><p><span data-ttu-id="4fa69-179">Devise</span><span class="sxs-lookup"><span data-stu-id="4fa69-179">Currency</span></span></p></th>
<th><p><span data-ttu-id="4fa69-180">Code période</span><span class="sxs-lookup"><span data-stu-id="4fa69-180">Period code</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4fa69-181">00020_135</span><span class="sxs-lookup"><span data-stu-id="4fa69-181">00020_135</span></span></p></td>
<td><p><span data-ttu-id="4fa69-182">9030</span><span class="sxs-lookup"><span data-stu-id="4fa69-182">9030</span></span></p></td>
<td><p><span data-ttu-id="4fa69-183">Sous1</span><span class="sxs-lookup"><span data-stu-id="4fa69-183">Sub1</span></span></p></td>
<td><p><span data-ttu-id="4fa69-184">SousCat1</span><span class="sxs-lookup"><span data-stu-id="4fa69-184">SubCat1</span></span></p></td>
<td><p><span data-ttu-id="4fa69-185">EUR</span><span class="sxs-lookup"><span data-stu-id="4fa69-185">EUR</span></span></p></td>
<td><p><span data-ttu-id="4fa69-186">Mensuel</span><span class="sxs-lookup"><span data-stu-id="4fa69-186">Monthly</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4fa69-187">00021_135</span><span class="sxs-lookup"><span data-stu-id="4fa69-187">00021_135</span></span></p></td>
<td><p><span data-ttu-id="4fa69-188">9030</span><span class="sxs-lookup"><span data-stu-id="4fa69-188">9030</span></span></p></td>
<td><p><span data-ttu-id="4fa69-189">Sous1</span><span class="sxs-lookup"><span data-stu-id="4fa69-189">Sub1</span></span></p></td>
<td><p><span data-ttu-id="4fa69-190">SousCat2</span><span class="sxs-lookup"><span data-stu-id="4fa69-190">SubCat2</span></span></p></td>
<td><p><span data-ttu-id="4fa69-191">EUR</span><span class="sxs-lookup"><span data-stu-id="4fa69-191">EUR</span></span></p></td>
<td><p><span data-ttu-id="4fa69-192">Mensuel</span><span class="sxs-lookup"><span data-stu-id="4fa69-192">Monthly</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="4fa69-193">Créez maintenant des frais d'abonnement pour les deux abonnements du groupe d'abonnements Sous1 :</span><span class="sxs-lookup"><span data-stu-id="4fa69-193">Now you create subscription fees for both subscriptions in the subscription group Sub1:</span></span>

1.  <span data-ttu-id="4fa69-194">Cliquez sur **Gestion des services** \> **Paramétrage** \> **Services récurrents** \> **Groupes d'abonnements**.</span><span class="sxs-lookup"><span data-stu-id="4fa69-194">Click **Service management** \> **Setup** \> **Service subscriptions** \> **Subscription groups**.</span></span>

2.  <span data-ttu-id="4fa69-195">Dans l'écran **Groupes d'abonnements**, cliquez sur **Fonction** \> **Créer des frais d'abonnement**.</span><span class="sxs-lookup"><span data-stu-id="4fa69-195">In the **Subscription groups** form, click **Function** \> **Create subscription fee**.</span></span>

3.  <span data-ttu-id="4fa69-196">Dans l'écran **Créer des frais d'abonnement**, entrez les informations appropriées.</span><span class="sxs-lookup"><span data-stu-id="4fa69-196">In the **Create subscription fee** form, enter the appropriate information.</span></span> <span data-ttu-id="4fa69-197">Pour plus d'informations, voir [Créer des transactions de redevance](create-subscription-fee-transactions.md).</span><span class="sxs-lookup"><span data-stu-id="4fa69-197">For more information, see [Create subscription fee transactions](create-subscription-fee-transactions.md).</span></span>

<span data-ttu-id="4fa69-198">Des frais d'abonnement avec un prix de vente de 500 EUR sont créés pour les deux abonnements, comme indiqué dans le tableau suivant.</span><span class="sxs-lookup"><span data-stu-id="4fa69-198">Subscription fees that have a sales price of EUR 500 are created for both subscriptions, as shown in the following table.</span></span>

<table>
<colgroup>
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="4fa69-199">Date du projet</span><span class="sxs-lookup"><span data-stu-id="4fa69-199">Project date</span></span></p></th>
<th><p><span data-ttu-id="4fa69-200">Service récurrent</span><span class="sxs-lookup"><span data-stu-id="4fa69-200">Service subscription</span></span></p></th>
<th><p><span data-ttu-id="4fa69-201">Projet</span><span class="sxs-lookup"><span data-stu-id="4fa69-201">Project</span></span></p></th>
<th><p><span data-ttu-id="4fa69-202">Catégorie</span><span class="sxs-lookup"><span data-stu-id="4fa69-202">Category</span></span></p></th>
<th><p><span data-ttu-id="4fa69-203">Date de début</span><span class="sxs-lookup"><span data-stu-id="4fa69-203">Start date</span></span></p></th>
<th><p><span data-ttu-id="4fa69-204">Date de fin</span><span class="sxs-lookup"><span data-stu-id="4fa69-204">End date</span></span></p></th>
<th><p><span data-ttu-id="4fa69-205">Devise de vente</span><span class="sxs-lookup"><span data-stu-id="4fa69-205">Sales currency</span></span></p></th>
<th><p><span data-ttu-id="4fa69-206">Prix de vente</span><span class="sxs-lookup"><span data-stu-id="4fa69-206">Sales price</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4fa69-207">28-08-2006</span><span class="sxs-lookup"><span data-stu-id="4fa69-207">28-08-2006</span></span></p></td>
<td><p><span data-ttu-id="4fa69-208">00020_135</span><span class="sxs-lookup"><span data-stu-id="4fa69-208">00020_135</span></span></p></td>
<td><p><span data-ttu-id="4fa69-209">9030</span><span class="sxs-lookup"><span data-stu-id="4fa69-209">9030</span></span></p></td>
<td><p><span data-ttu-id="4fa69-210">SousCat1</span><span class="sxs-lookup"><span data-stu-id="4fa69-210">SubCat1</span></span></p></td>
<td><p><span data-ttu-id="4fa69-211">01-01-2007</span><span class="sxs-lookup"><span data-stu-id="4fa69-211">01-01-2007</span></span></p></td>
<td><p><span data-ttu-id="4fa69-212">31-03-2007</span><span class="sxs-lookup"><span data-stu-id="4fa69-212">31-03-2007</span></span></p></td>
<td><p><span data-ttu-id="4fa69-213">EUR</span><span class="sxs-lookup"><span data-stu-id="4fa69-213">EUR</span></span></p></td>
<td><p><span data-ttu-id="4fa69-214">500</span><span class="sxs-lookup"><span data-stu-id="4fa69-214">500</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4fa69-215">28-08-2006</span><span class="sxs-lookup"><span data-stu-id="4fa69-215">28-08-2006</span></span></p></td>
<td><p><span data-ttu-id="4fa69-216">00021_135</span><span class="sxs-lookup"><span data-stu-id="4fa69-216">00021_135</span></span></p></td>
<td><p><span data-ttu-id="4fa69-217">9030</span><span class="sxs-lookup"><span data-stu-id="4fa69-217">9030</span></span></p></td>
<td><p><span data-ttu-id="4fa69-218">SousCat2</span><span class="sxs-lookup"><span data-stu-id="4fa69-218">SubCat2</span></span></p></td>
<td><p><span data-ttu-id="4fa69-219">01-01-2007</span><span class="sxs-lookup"><span data-stu-id="4fa69-219">01-01-2007</span></span></p></td>
<td><p><span data-ttu-id="4fa69-220">31-03-2007</span><span class="sxs-lookup"><span data-stu-id="4fa69-220">31-03-2007</span></span></p></td>
<td><p><span data-ttu-id="4fa69-221">EUR</span><span class="sxs-lookup"><span data-stu-id="4fa69-221">EUR</span></span></p></td>
<td><p><span data-ttu-id="4fa69-222">500</span><span class="sxs-lookup"><span data-stu-id="4fa69-222">500</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="4fa69-223">Plus tard, vous souhaitez spécifier des prix de vente pour la catégorie SousCat1 du projet 9030.</span><span class="sxs-lookup"><span data-stu-id="4fa69-223">Later, you decide that you want to specify sales prices for the category SubCat1 for project 9030.</span></span> <span data-ttu-id="4fa69-224">Vous créez donc une ligne de prix de vente avec un prix de vente de 550 EUR pour la combinaison du projet 9030 et de la sous-catégorie SousCat1.</span><span class="sxs-lookup"><span data-stu-id="4fa69-224">Therefore, you create a new sales price line that has a sales price of EUR 550 for the combination of project 9030 and fee category SubCat1.</span></span> <span data-ttu-id="4fa69-225">Il existe désormais deux lignes de prix de vente d'abonnement pour le projet 9030, comme indiqué dans le tableau suivant.</span><span class="sxs-lookup"><span data-stu-id="4fa69-225">There are now two subscription sales price lines for project 9030, as shown in the following table.</span></span>

<table style="width:100%;">
<colgroup>
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="4fa69-226">Valide du</span><span class="sxs-lookup"><span data-stu-id="4fa69-226">Valid from</span></span></p></th>
<th><p><span data-ttu-id="4fa69-227">Catégorie</span><span class="sxs-lookup"><span data-stu-id="4fa69-227">Category</span></span></p></th>
<th><p><span data-ttu-id="4fa69-228">Projet</span><span class="sxs-lookup"><span data-stu-id="4fa69-228">Project</span></span></p></th>
<th><p><span data-ttu-id="4fa69-229">Abonnement</span><span class="sxs-lookup"><span data-stu-id="4fa69-229">Subscription</span></span></p></th>
<th><p><span data-ttu-id="4fa69-230">Code période</span><span class="sxs-lookup"><span data-stu-id="4fa69-230">Period code</span></span></p></th>
<th><p><span data-ttu-id="4fa69-231">Devise</span><span class="sxs-lookup"><span data-stu-id="4fa69-231">Currency</span></span></p></th>
<th><p><span data-ttu-id="4fa69-232">Prix de vente</span><span class="sxs-lookup"><span data-stu-id="4fa69-232">Sales price</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4fa69-233">28-08-2007</span><span class="sxs-lookup"><span data-stu-id="4fa69-233">28-08-2007</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="4fa69-234">9030</span><span class="sxs-lookup"><span data-stu-id="4fa69-234">9030</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="4fa69-235">Mois</span><span class="sxs-lookup"><span data-stu-id="4fa69-235">Month</span></span></p></td>
<td><p><span data-ttu-id="4fa69-236">EUR</span><span class="sxs-lookup"><span data-stu-id="4fa69-236">EUR</span></span></p></td>
<td><p><span data-ttu-id="4fa69-237">500</span><span class="sxs-lookup"><span data-stu-id="4fa69-237">500</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4fa69-238">28-08-2007</span><span class="sxs-lookup"><span data-stu-id="4fa69-238">28-08-2007</span></span></p></td>
<td><p><span data-ttu-id="4fa69-239">SousCat1</span><span class="sxs-lookup"><span data-stu-id="4fa69-239">SubCat1</span></span></p></td>
<td><p><span data-ttu-id="4fa69-240">9030</span><span class="sxs-lookup"><span data-stu-id="4fa69-240">9030</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="4fa69-241">Mois</span><span class="sxs-lookup"><span data-stu-id="4fa69-241">Month</span></span></p></td>
<td><p><span data-ttu-id="4fa69-242">EUR</span><span class="sxs-lookup"><span data-stu-id="4fa69-242">EUR</span></span></p></td>
<td><p><span data-ttu-id="4fa69-243">550</span><span class="sxs-lookup"><span data-stu-id="4fa69-243">550</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="4fa69-244">Répétez la procédure ci-dessus pour créer des frais d'abonnement pour les deux abonnements du groupe d'abonnements Sous1.</span><span class="sxs-lookup"><span data-stu-id="4fa69-244">You repeat the procedure described above to create subscription fees for both subscriptions in the subscription group Sub1.</span></span> <span data-ttu-id="4fa69-245">Le tableau suivant indique les transactions qui sont créées pour chaque abonnement lié au groupe d'abonnements.</span><span class="sxs-lookup"><span data-stu-id="4fa69-245">The following table shows the transactions that are created for each subscription that is attached to the subscription group.</span></span>

<table>
<colgroup>
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="4fa69-246">Date du projet</span><span class="sxs-lookup"><span data-stu-id="4fa69-246">Project date</span></span></p></th>
<th><p><span data-ttu-id="4fa69-247">Abonnement</span><span class="sxs-lookup"><span data-stu-id="4fa69-247">Subscription</span></span></p></th>
<th><p><span data-ttu-id="4fa69-248">Projet</span><span class="sxs-lookup"><span data-stu-id="4fa69-248">Project</span></span></p></th>
<th><p><span data-ttu-id="4fa69-249">Catégorie</span><span class="sxs-lookup"><span data-stu-id="4fa69-249">Category</span></span></p></th>
<th><p><span data-ttu-id="4fa69-250">Date de début</span><span class="sxs-lookup"><span data-stu-id="4fa69-250">Start date</span></span></p></th>
<th><p><span data-ttu-id="4fa69-251">Date de fin</span><span class="sxs-lookup"><span data-stu-id="4fa69-251">End date</span></span></p></th>
<th><p><span data-ttu-id="4fa69-252">Devise de vente</span><span class="sxs-lookup"><span data-stu-id="4fa69-252">Sales currency</span></span></p></th>
<th><p><span data-ttu-id="4fa69-253">Prix de vente</span><span class="sxs-lookup"><span data-stu-id="4fa69-253">Sales price</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4fa69-254">28-07-2007</span><span class="sxs-lookup"><span data-stu-id="4fa69-254">28-07-2007</span></span></p></td>
<td><p><span data-ttu-id="4fa69-255">00020_135</span><span class="sxs-lookup"><span data-stu-id="4fa69-255">00020_135</span></span></p></td>
<td><p><span data-ttu-id="4fa69-256">9030</span><span class="sxs-lookup"><span data-stu-id="4fa69-256">9030</span></span></p></td>
<td><p><span data-ttu-id="4fa69-257">SousCat1</span><span class="sxs-lookup"><span data-stu-id="4fa69-257">SubCat1</span></span></p></td>
<td><p><span data-ttu-id="4fa69-258">01-01-2008</span><span class="sxs-lookup"><span data-stu-id="4fa69-258">01-01-2008</span></span></p></td>
<td><p><span data-ttu-id="4fa69-259">31-03-2008</span><span class="sxs-lookup"><span data-stu-id="4fa69-259">31-03-2008</span></span></p></td>
<td><p><span data-ttu-id="4fa69-260">EUR</span><span class="sxs-lookup"><span data-stu-id="4fa69-260">EUR</span></span></p></td>
<td><p><span data-ttu-id="4fa69-261">550</span><span class="sxs-lookup"><span data-stu-id="4fa69-261">550</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4fa69-262">28-07-2008</span><span class="sxs-lookup"><span data-stu-id="4fa69-262">28-07-2008</span></span></p></td>
<td><p><span data-ttu-id="4fa69-263">00021_135</span><span class="sxs-lookup"><span data-stu-id="4fa69-263">00021_135</span></span></p></td>
<td><p><span data-ttu-id="4fa69-264">9030</span><span class="sxs-lookup"><span data-stu-id="4fa69-264">9030</span></span></p></td>
<td><p><span data-ttu-id="4fa69-265">SousCat2</span><span class="sxs-lookup"><span data-stu-id="4fa69-265">SubCat2</span></span></p></td>
<td><p><span data-ttu-id="4fa69-266">01-01-2008</span><span class="sxs-lookup"><span data-stu-id="4fa69-266">01-01-2008</span></span></p></td>
<td><p><span data-ttu-id="4fa69-267">31-03-2008</span><span class="sxs-lookup"><span data-stu-id="4fa69-267">31-03-2008</span></span></p></td>
<td><p><span data-ttu-id="4fa69-268">EUR</span><span class="sxs-lookup"><span data-stu-id="4fa69-268">EUR</span></span></p></td>
<td><p><span data-ttu-id="4fa69-269">500</span><span class="sxs-lookup"><span data-stu-id="4fa69-269">500</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="4fa69-270">Pour la première transaction d'abonnement 00020\_135, le prix de vente de 550 EUR est calculé à partir du paramétrage du prix de vente d'abonnement défini pour la combinaison du projet et de la catégorie spécifiques.</span><span class="sxs-lookup"><span data-stu-id="4fa69-270">In the first transaction for subscription 00020\_135, the sales price of EUR 550 derives from the subscription sales price that is set up for the combination of the specific project and category.</span></span> <span data-ttu-id="4fa69-271">Pour la deuxième transaction d'abonnement 00021\_135, le prix de vente de 500 EUR est utilisé comme prix de vente d'abonnement du projet car aucun prix n'est défini pour la combinaison du projet 9030 et de la catégorie SousCat2.</span><span class="sxs-lookup"><span data-stu-id="4fa69-271">In the second transaction for subscription 00021\_135, the sales price of EUR 500 is used as the project subscription sales price because there is no price set up for the combination of project 9030 and category SubCat2.</span></span>

## <a name="see-also"></a><span data-ttu-id="4fa69-272">Voir également :</span><span class="sxs-lookup"><span data-stu-id="4fa69-272">See also</span></span>

[<span data-ttu-id="4fa69-273">Mise à jour et indexation des prix de vente des abonnements</span><span class="sxs-lookup"><span data-stu-id="4fa69-273">Update and index subscription sales prices</span></span>](update-and-index-subscription-sales-prices.md)

  



