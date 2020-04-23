---
title: Prix de vente des abonnements
description: Lors de la création d'un abonnement, le prix de vente est calculé à partir du paramétrage de prix de vente défini dans l'écran Prix de vente (abonnement).
author: ShylaThompson
manager: tfehr
ms.date: 05/01/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SMASalespriceSubscription
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: ShylaThompson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: d6c59c90d49a4dcf3df4672c5f40d52ed639760c
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/02/2020
ms.locfileid: "3206609"
---
# <a name="subscription-sales-prices"></a><span data-ttu-id="a07eb-103">Prix de vente des abonnements</span><span class="sxs-lookup"><span data-stu-id="a07eb-103">Subscription sales prices</span></span>   

[!include [banner](../includes/banner.md)]


<span data-ttu-id="a07eb-104">Lors de la création d'un abonnement, le prix de vente est calculé à partir du paramétrage de prix de vente défini dans l'écran **Prix de vente (abonnement)**.</span><span class="sxs-lookup"><span data-stu-id="a07eb-104">When you create a subscription, the sales price is derived from the sales price setup that was created in the **Sales price (subscription)** form.</span></span>

<span data-ttu-id="a07eb-105">L'écran **Prix de vente (abonnement)** permet de créer des prix de vente pour un abonnement spécifique ou pour un champ d'application plus vaste.</span><span class="sxs-lookup"><span data-stu-id="a07eb-105">In the **Sales price (subscription)** form, you can create sales prices for a specific subscription or you can create sales prices that apply more broadly.</span></span> <span data-ttu-id="a07eb-106">Pour un prix de vente s'appliquant à un abonnement, le code période et la devise de l'abonnement doivent être identiques à ceux du prix de vente.</span><span class="sxs-lookup"><span data-stu-id="a07eb-106">For a sales price to be applied to a subscription, the period code and the currency of the subscription must be identical to the period code and the currency of the sales price.</span></span>

<span data-ttu-id="a07eb-107">Si le code période et la devise de l'abonnement et du prix de vente sont identiques, les prix de vente d'abonnement sont sélectionnés en fonction des priorités indiquées dans le tableau suivant.</span><span class="sxs-lookup"><span data-stu-id="a07eb-107">If the period code and currency are identical for the subscription and the sales price, subscription sales prices are selected on the basis of the priorities listed in the following table.</span></span> <span data-ttu-id="a07eb-108">Une cellule vide dans le tableau indique un champ sans valeur et un X indique une valeur égale à celle de l'abonnement à partir duquel la transaction est générée.</span><span class="sxs-lookup"><span data-stu-id="a07eb-108">A blank cell in the table indicates an empty field and an X indicates a value that is equal to the value in the subscription from which the transaction is generated.</span></span>

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
<th><p><span data-ttu-id="a07eb-109">Priorité</span><span class="sxs-lookup"><span data-stu-id="a07eb-109">Priority</span></span></p></th>
<th><p><span data-ttu-id="a07eb-110"><strong>Catégorie</strong></span><span class="sxs-lookup"><span data-stu-id="a07eb-110"><strong>Category</strong></span></span></p></th>
<th><p><span data-ttu-id="a07eb-111"><strong>ID Projet</strong></span><span class="sxs-lookup"><span data-stu-id="a07eb-111"><strong>Project ID</strong></span></span></p></th>
<th><p><span data-ttu-id="a07eb-112"><strong>Abonnement</strong></span><span class="sxs-lookup"><span data-stu-id="a07eb-112"><strong>Subscription</strong></span></span></p></th>
<th><p><span data-ttu-id="a07eb-113"><strong>Devise de vente</strong></span><span class="sxs-lookup"><span data-stu-id="a07eb-113"><strong>Sales currency</strong></span></span></p></th>
<th><p><span data-ttu-id="a07eb-114"><strong>Code période</strong></span><span class="sxs-lookup"><span data-stu-id="a07eb-114"><strong>Period code</strong></span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a07eb-115">1</span><span class="sxs-lookup"><span data-stu-id="a07eb-115">1</span></span></p></td>
<td><p><span data-ttu-id="a07eb-116">O</span><span class="sxs-lookup"><span data-stu-id="a07eb-116">X</span></span></p></td>
<td><p><span data-ttu-id="a07eb-117">O</span><span class="sxs-lookup"><span data-stu-id="a07eb-117">X</span></span></p></td>
<td><p><span data-ttu-id="a07eb-118">O</span><span class="sxs-lookup"><span data-stu-id="a07eb-118">X</span></span></p></td>
<td><p><span data-ttu-id="a07eb-119">O</span><span class="sxs-lookup"><span data-stu-id="a07eb-119">X</span></span></p></td>
<td><p><span data-ttu-id="a07eb-120">O</span><span class="sxs-lookup"><span data-stu-id="a07eb-120">X</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a07eb-121">2</span><span class="sxs-lookup"><span data-stu-id="a07eb-121">2</span></span></p></td>
<td><p></p></td>
<td><p><span data-ttu-id="a07eb-122">O</span><span class="sxs-lookup"><span data-stu-id="a07eb-122">X</span></span></p></td>
<td><p><span data-ttu-id="a07eb-123">O</span><span class="sxs-lookup"><span data-stu-id="a07eb-123">X</span></span></p></td>
<td><p><span data-ttu-id="a07eb-124">O</span><span class="sxs-lookup"><span data-stu-id="a07eb-124">X</span></span></p></td>
<td><p><span data-ttu-id="a07eb-125">O</span><span class="sxs-lookup"><span data-stu-id="a07eb-125">X</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a07eb-126">3</span><span class="sxs-lookup"><span data-stu-id="a07eb-126">3</span></span></p></td>
<td><p><span data-ttu-id="a07eb-127">O</span><span class="sxs-lookup"><span data-stu-id="a07eb-127">X</span></span></p></td>
<td><p></p></td>
<td><p><span data-ttu-id="a07eb-128">O</span><span class="sxs-lookup"><span data-stu-id="a07eb-128">X</span></span></p></td>
<td><p><span data-ttu-id="a07eb-129">O</span><span class="sxs-lookup"><span data-stu-id="a07eb-129">X</span></span></p></td>
<td><p><span data-ttu-id="a07eb-130">O</span><span class="sxs-lookup"><span data-stu-id="a07eb-130">X</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a07eb-131">4</span><span class="sxs-lookup"><span data-stu-id="a07eb-131">4</span></span></p></td>
<td><p></p></td>
<td><p></p></td>
<td><p><span data-ttu-id="a07eb-132">O</span><span class="sxs-lookup"><span data-stu-id="a07eb-132">X</span></span></p></td>
<td><p><span data-ttu-id="a07eb-133">O</span><span class="sxs-lookup"><span data-stu-id="a07eb-133">X</span></span></p></td>
<td><p><span data-ttu-id="a07eb-134">O</span><span class="sxs-lookup"><span data-stu-id="a07eb-134">X</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a07eb-135">5</span><span class="sxs-lookup"><span data-stu-id="a07eb-135">5</span></span></p></td>
<td><p><span data-ttu-id="a07eb-136">O</span><span class="sxs-lookup"><span data-stu-id="a07eb-136">X</span></span></p></td>
<td><p><span data-ttu-id="a07eb-137">O</span><span class="sxs-lookup"><span data-stu-id="a07eb-137">X</span></span></p></td>
<td><p></p></td>
<td><p><span data-ttu-id="a07eb-138">O</span><span class="sxs-lookup"><span data-stu-id="a07eb-138">X</span></span></p></td>
<td><p><span data-ttu-id="a07eb-139">O</span><span class="sxs-lookup"><span data-stu-id="a07eb-139">X</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a07eb-140">6</span><span class="sxs-lookup"><span data-stu-id="a07eb-140">6</span></span></p></td>
<td><p></p></td>
<td><p><span data-ttu-id="a07eb-141">O</span><span class="sxs-lookup"><span data-stu-id="a07eb-141">X</span></span></p></td>
<td><p></p></td>
<td><p><span data-ttu-id="a07eb-142">O</span><span class="sxs-lookup"><span data-stu-id="a07eb-142">X</span></span></p></td>
<td><p><span data-ttu-id="a07eb-143">O</span><span class="sxs-lookup"><span data-stu-id="a07eb-143">X</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a07eb-144">7</span><span class="sxs-lookup"><span data-stu-id="a07eb-144">7</span></span></p></td>
<td><p><span data-ttu-id="a07eb-145">O</span><span class="sxs-lookup"><span data-stu-id="a07eb-145">X</span></span></p></td>
<td><p></p></td>
<td><p></p></td>
<td><p><span data-ttu-id="a07eb-146">O</span><span class="sxs-lookup"><span data-stu-id="a07eb-146">X</span></span></p></td>
<td><p><span data-ttu-id="a07eb-147">O</span><span class="sxs-lookup"><span data-stu-id="a07eb-147">X</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a07eb-148">8</span><span class="sxs-lookup"><span data-stu-id="a07eb-148">8</span></span></p></td>
<td><p></p></td>
<td><p></p></td>
<td><p></p></td>
<td><p><span data-ttu-id="a07eb-149">O</span><span class="sxs-lookup"><span data-stu-id="a07eb-149">X</span></span></p></td>
<td><p><span data-ttu-id="a07eb-150">O</span><span class="sxs-lookup"><span data-stu-id="a07eb-150">X</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="a07eb-151">Lors de la création de frais d'abonnement, le prix de vente le plus détaillé, voir le tableau ci-dessus, est sélectionné comme prix de vente de l'abonnement.</span><span class="sxs-lookup"><span data-stu-id="a07eb-151">When a subscription fee is created, the sales price with the greatest level of detail, as noted in the table above, is selected as the subscription sales price.</span></span>

## <a name="update-and-index-subscription-sales-prices"></a><span data-ttu-id="a07eb-152">Mise à jour et indexation des prix de vente des abonnements</span><span class="sxs-lookup"><span data-stu-id="a07eb-152">Update and index subscription sales prices</span></span>

<span data-ttu-id="a07eb-153">Vous pouvez mettre à jour le prix de vente des abonnements en mettant à jour le prix de base ou l'indice.</span><span class="sxs-lookup"><span data-stu-id="a07eb-153">You can update the subscription sales price by updating the base price or the index.</span></span> <span data-ttu-id="a07eb-154">Ceux-ci peuvent être mis à jour en entrant un pourcentage ou une nouvelle valeur.</span><span class="sxs-lookup"><span data-stu-id="a07eb-154">You can update by a percentage or to a new value.</span></span>

## <a name="subscription-fee-sales-prices"></a><span data-ttu-id="a07eb-155">Prix de vente des frais d'abonnement</span><span class="sxs-lookup"><span data-stu-id="a07eb-155">Subscription fee sales prices</span></span>

<span data-ttu-id="a07eb-156">Lors de la création de frais d'abonnement, le prix de vente est calculé à partir du paramétrage de prix de vente de l'abonnement.</span><span class="sxs-lookup"><span data-stu-id="a07eb-156">When you create a subscription fee, the sales price is based on the sales price setup of the subscription.</span></span> <span data-ttu-id="a07eb-157">Vous pouvez soit utiliser le prix de base indiqué dans le paramétrage de prix de l'abonnement, soit créer des prix de vente indexés.</span><span class="sxs-lookup"><span data-stu-id="a07eb-157">You can either use the base price from the subscription price setup or create indexed sales prices.</span></span>

## <a name="example"></a><span data-ttu-id="a07eb-158">Exemple</span><span class="sxs-lookup"><span data-stu-id="a07eb-158">Example</span></span>

<span data-ttu-id="a07eb-159">Vous souhaitez paramétrer des prix de vente de 500 EUR pour un nouveau projet 9030.</span><span class="sxs-lookup"><span data-stu-id="a07eb-159">You want to set up subscription sales prices of EUR 500 for a new project 9030.</span></span> <span data-ttu-id="a07eb-160">Dans l'écran **Prix de vente (abonnement)**, créez une ligne de prix de vente d'abonnement comme indiqué dans le tableau suivant :</span><span class="sxs-lookup"><span data-stu-id="a07eb-160">In the **Sales price (subscription)** form, you create a subscription sales price line as indicated in the following table.</span></span>

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
<th><p><span data-ttu-id="a07eb-161">Valide du</span><span class="sxs-lookup"><span data-stu-id="a07eb-161">Valid from</span></span></p></th>
<th><p><span data-ttu-id="a07eb-162">Catégorie</span><span class="sxs-lookup"><span data-stu-id="a07eb-162">Category</span></span></p></th>
<th><p><span data-ttu-id="a07eb-163">Projet</span><span class="sxs-lookup"><span data-stu-id="a07eb-163">Project</span></span></p></th>
<th><p><span data-ttu-id="a07eb-164">Abonnement</span><span class="sxs-lookup"><span data-stu-id="a07eb-164">Subscription</span></span></p></th>
<th><p><span data-ttu-id="a07eb-165">Code période</span><span class="sxs-lookup"><span data-stu-id="a07eb-165">Period code</span></span></p></th>
<th><p><span data-ttu-id="a07eb-166">Devise de vente</span><span class="sxs-lookup"><span data-stu-id="a07eb-166">Sales currency</span></span></p></th>
<th><p><span data-ttu-id="a07eb-167">Prix de vente</span><span class="sxs-lookup"><span data-stu-id="a07eb-167">Sales price</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a07eb-168">28-08-2006</span><span class="sxs-lookup"><span data-stu-id="a07eb-168">28-08-2006</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a07eb-169">9030</span><span class="sxs-lookup"><span data-stu-id="a07eb-169">9030</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a07eb-170">Mois</span><span class="sxs-lookup"><span data-stu-id="a07eb-170">Month</span></span></p></td>
<td><p><span data-ttu-id="a07eb-171">EUR</span><span class="sxs-lookup"><span data-stu-id="a07eb-171">EUR</span></span></p></td>
<td><p><span data-ttu-id="a07eb-172">500</span><span class="sxs-lookup"><span data-stu-id="a07eb-172">500</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="a07eb-173">Notez que les champs **Catégorie** et **Abonnement** sont vides.</span><span class="sxs-lookup"><span data-stu-id="a07eb-173">Note that the **Category** and **Subscription** fields are empty.</span></span>

<span data-ttu-id="a07eb-174">Vous pouvez ensuite créer les abonnements suivants.</span><span class="sxs-lookup"><span data-stu-id="a07eb-174">You then create the following subscriptions.</span></span>

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
<th><p><span data-ttu-id="a07eb-175">Service récurrent</span><span class="sxs-lookup"><span data-stu-id="a07eb-175">Service subscription</span></span></p></th>
<th><p><span data-ttu-id="a07eb-176">Projet</span><span class="sxs-lookup"><span data-stu-id="a07eb-176">Project</span></span></p></th>
<th><p><span data-ttu-id="a07eb-177">Groupe d'abonnements</span><span class="sxs-lookup"><span data-stu-id="a07eb-177">Subscription group</span></span></p></th>
<th><p><span data-ttu-id="a07eb-178">Catégorie</span><span class="sxs-lookup"><span data-stu-id="a07eb-178">Category</span></span></p></th>
<th><p><span data-ttu-id="a07eb-179">Devise</span><span class="sxs-lookup"><span data-stu-id="a07eb-179">Currency</span></span></p></th>
<th><p><span data-ttu-id="a07eb-180">Code période</span><span class="sxs-lookup"><span data-stu-id="a07eb-180">Period code</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a07eb-181">00020_135</span><span class="sxs-lookup"><span data-stu-id="a07eb-181">00020_135</span></span></p></td>
<td><p><span data-ttu-id="a07eb-182">9030</span><span class="sxs-lookup"><span data-stu-id="a07eb-182">9030</span></span></p></td>
<td><p><span data-ttu-id="a07eb-183">Sous1</span><span class="sxs-lookup"><span data-stu-id="a07eb-183">Sub1</span></span></p></td>
<td><p><span data-ttu-id="a07eb-184">SousCat1</span><span class="sxs-lookup"><span data-stu-id="a07eb-184">SubCat1</span></span></p></td>
<td><p><span data-ttu-id="a07eb-185">EUR</span><span class="sxs-lookup"><span data-stu-id="a07eb-185">EUR</span></span></p></td>
<td><p><span data-ttu-id="a07eb-186">Mensuel</span><span class="sxs-lookup"><span data-stu-id="a07eb-186">Monthly</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a07eb-187">00021_135</span><span class="sxs-lookup"><span data-stu-id="a07eb-187">00021_135</span></span></p></td>
<td><p><span data-ttu-id="a07eb-188">9030</span><span class="sxs-lookup"><span data-stu-id="a07eb-188">9030</span></span></p></td>
<td><p><span data-ttu-id="a07eb-189">Sous1</span><span class="sxs-lookup"><span data-stu-id="a07eb-189">Sub1</span></span></p></td>
<td><p><span data-ttu-id="a07eb-190">SousCat2</span><span class="sxs-lookup"><span data-stu-id="a07eb-190">SubCat2</span></span></p></td>
<td><p><span data-ttu-id="a07eb-191">EUR</span><span class="sxs-lookup"><span data-stu-id="a07eb-191">EUR</span></span></p></td>
<td><p><span data-ttu-id="a07eb-192">Mensuel</span><span class="sxs-lookup"><span data-stu-id="a07eb-192">Monthly</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="a07eb-193">Créez maintenant des frais d'abonnement pour les deux abonnements du groupe d'abonnements Sous1 :</span><span class="sxs-lookup"><span data-stu-id="a07eb-193">Now you create subscription fees for both subscriptions in the subscription group Sub1:</span></span>

1.  <span data-ttu-id="a07eb-194">Cliquez sur **Gestion des services** \> **Paramétrage** \> **Services récurrents** \> **Groupes d'abonnements**.</span><span class="sxs-lookup"><span data-stu-id="a07eb-194">Click **Service management** \> **Setup** \> **Service subscriptions** \> **Subscription groups**.</span></span>

2.  <span data-ttu-id="a07eb-195">Dans l'écran **Groupes d'abonnements**, cliquez sur **Fonction** \> **Créer des frais d'abonnement**.</span><span class="sxs-lookup"><span data-stu-id="a07eb-195">In the **Subscription groups** form, click **Function** \> **Create subscription fee**.</span></span>

3.  <span data-ttu-id="a07eb-196">Dans l'écran **Créer des frais d'abonnement**, entrez les informations appropriées.</span><span class="sxs-lookup"><span data-stu-id="a07eb-196">In the **Create subscription fee** form, enter the appropriate information.</span></span> <span data-ttu-id="a07eb-197">Pour plus d'informations, voir [Créer des transactions de redevance](create-subscription-fee-transactions.md).</span><span class="sxs-lookup"><span data-stu-id="a07eb-197">For more information, see [Create subscription fee transactions](create-subscription-fee-transactions.md).</span></span>

<span data-ttu-id="a07eb-198">Des frais d'abonnement avec un prix de vente de 500 EUR sont créés pour les deux abonnements, comme indiqué dans le tableau suivant.</span><span class="sxs-lookup"><span data-stu-id="a07eb-198">Subscription fees that have a sales price of EUR 500 are created for both subscriptions, as shown in the following table.</span></span>

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
<th><p><span data-ttu-id="a07eb-199">Date du projet</span><span class="sxs-lookup"><span data-stu-id="a07eb-199">Project date</span></span></p></th>
<th><p><span data-ttu-id="a07eb-200">Service récurrent</span><span class="sxs-lookup"><span data-stu-id="a07eb-200">Service subscription</span></span></p></th>
<th><p><span data-ttu-id="a07eb-201">Projet</span><span class="sxs-lookup"><span data-stu-id="a07eb-201">Project</span></span></p></th>
<th><p><span data-ttu-id="a07eb-202">Catégorie</span><span class="sxs-lookup"><span data-stu-id="a07eb-202">Category</span></span></p></th>
<th><p><span data-ttu-id="a07eb-203">Date de début</span><span class="sxs-lookup"><span data-stu-id="a07eb-203">Start date</span></span></p></th>
<th><p><span data-ttu-id="a07eb-204">Date de fin</span><span class="sxs-lookup"><span data-stu-id="a07eb-204">End date</span></span></p></th>
<th><p><span data-ttu-id="a07eb-205">Devise de vente</span><span class="sxs-lookup"><span data-stu-id="a07eb-205">Sales currency</span></span></p></th>
<th><p><span data-ttu-id="a07eb-206">Prix de vente</span><span class="sxs-lookup"><span data-stu-id="a07eb-206">Sales price</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a07eb-207">28-08-2006</span><span class="sxs-lookup"><span data-stu-id="a07eb-207">28-08-2006</span></span></p></td>
<td><p><span data-ttu-id="a07eb-208">00020_135</span><span class="sxs-lookup"><span data-stu-id="a07eb-208">00020_135</span></span></p></td>
<td><p><span data-ttu-id="a07eb-209">9030</span><span class="sxs-lookup"><span data-stu-id="a07eb-209">9030</span></span></p></td>
<td><p><span data-ttu-id="a07eb-210">SousCat1</span><span class="sxs-lookup"><span data-stu-id="a07eb-210">SubCat1</span></span></p></td>
<td><p><span data-ttu-id="a07eb-211">01-01-2007</span><span class="sxs-lookup"><span data-stu-id="a07eb-211">01-01-2007</span></span></p></td>
<td><p><span data-ttu-id="a07eb-212">31-03-2007</span><span class="sxs-lookup"><span data-stu-id="a07eb-212">31-03-2007</span></span></p></td>
<td><p><span data-ttu-id="a07eb-213">EUR</span><span class="sxs-lookup"><span data-stu-id="a07eb-213">EUR</span></span></p></td>
<td><p><span data-ttu-id="a07eb-214">500</span><span class="sxs-lookup"><span data-stu-id="a07eb-214">500</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a07eb-215">28-08-2006</span><span class="sxs-lookup"><span data-stu-id="a07eb-215">28-08-2006</span></span></p></td>
<td><p><span data-ttu-id="a07eb-216">00021_135</span><span class="sxs-lookup"><span data-stu-id="a07eb-216">00021_135</span></span></p></td>
<td><p><span data-ttu-id="a07eb-217">9030</span><span class="sxs-lookup"><span data-stu-id="a07eb-217">9030</span></span></p></td>
<td><p><span data-ttu-id="a07eb-218">SousCat2</span><span class="sxs-lookup"><span data-stu-id="a07eb-218">SubCat2</span></span></p></td>
<td><p><span data-ttu-id="a07eb-219">01-01-2007</span><span class="sxs-lookup"><span data-stu-id="a07eb-219">01-01-2007</span></span></p></td>
<td><p><span data-ttu-id="a07eb-220">31-03-2007</span><span class="sxs-lookup"><span data-stu-id="a07eb-220">31-03-2007</span></span></p></td>
<td><p><span data-ttu-id="a07eb-221">EUR</span><span class="sxs-lookup"><span data-stu-id="a07eb-221">EUR</span></span></p></td>
<td><p><span data-ttu-id="a07eb-222">500</span><span class="sxs-lookup"><span data-stu-id="a07eb-222">500</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="a07eb-223">Plus tard, vous souhaitez spécifier des prix de vente pour la catégorie SousCat1 du projet 9030.</span><span class="sxs-lookup"><span data-stu-id="a07eb-223">Later, you decide that you want to specify sales prices for the category SubCat1 for project 9030.</span></span> <span data-ttu-id="a07eb-224">Vous créez donc une ligne de prix de vente avec un prix de vente de 550 EUR pour la combinaison du projet 9030 et de la sous-catégorie SousCat1.</span><span class="sxs-lookup"><span data-stu-id="a07eb-224">Therefore, you create a new sales price line that has a sales price of EUR 550 for the combination of project 9030 and fee category SubCat1.</span></span> <span data-ttu-id="a07eb-225">Il existe désormais deux lignes de prix de vente d'abonnement pour le projet 9030, comme indiqué dans le tableau suivant.</span><span class="sxs-lookup"><span data-stu-id="a07eb-225">There are now two subscription sales price lines for project 9030, as shown in the following table.</span></span>

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
<th><p><span data-ttu-id="a07eb-226">Valide du</span><span class="sxs-lookup"><span data-stu-id="a07eb-226">Valid from</span></span></p></th>
<th><p><span data-ttu-id="a07eb-227">Catégorie</span><span class="sxs-lookup"><span data-stu-id="a07eb-227">Category</span></span></p></th>
<th><p><span data-ttu-id="a07eb-228">Projet</span><span class="sxs-lookup"><span data-stu-id="a07eb-228">Project</span></span></p></th>
<th><p><span data-ttu-id="a07eb-229">Abonnement</span><span class="sxs-lookup"><span data-stu-id="a07eb-229">Subscription</span></span></p></th>
<th><p><span data-ttu-id="a07eb-230">Code période</span><span class="sxs-lookup"><span data-stu-id="a07eb-230">Period code</span></span></p></th>
<th><p><span data-ttu-id="a07eb-231">Devise</span><span class="sxs-lookup"><span data-stu-id="a07eb-231">Currency</span></span></p></th>
<th><p><span data-ttu-id="a07eb-232">Prix de vente</span><span class="sxs-lookup"><span data-stu-id="a07eb-232">Sales price</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a07eb-233">28-08-2007</span><span class="sxs-lookup"><span data-stu-id="a07eb-233">28-08-2007</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a07eb-234">9030</span><span class="sxs-lookup"><span data-stu-id="a07eb-234">9030</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a07eb-235">Mois</span><span class="sxs-lookup"><span data-stu-id="a07eb-235">Month</span></span></p></td>
<td><p><span data-ttu-id="a07eb-236">EUR</span><span class="sxs-lookup"><span data-stu-id="a07eb-236">EUR</span></span></p></td>
<td><p><span data-ttu-id="a07eb-237">500</span><span class="sxs-lookup"><span data-stu-id="a07eb-237">500</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a07eb-238">28-08-2007</span><span class="sxs-lookup"><span data-stu-id="a07eb-238">28-08-2007</span></span></p></td>
<td><p><span data-ttu-id="a07eb-239">SousCat1</span><span class="sxs-lookup"><span data-stu-id="a07eb-239">SubCat1</span></span></p></td>
<td><p><span data-ttu-id="a07eb-240">9030</span><span class="sxs-lookup"><span data-stu-id="a07eb-240">9030</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a07eb-241">Mois</span><span class="sxs-lookup"><span data-stu-id="a07eb-241">Month</span></span></p></td>
<td><p><span data-ttu-id="a07eb-242">EUR</span><span class="sxs-lookup"><span data-stu-id="a07eb-242">EUR</span></span></p></td>
<td><p><span data-ttu-id="a07eb-243">550</span><span class="sxs-lookup"><span data-stu-id="a07eb-243">550</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="a07eb-244">Répétez la procédure ci-dessus pour créer des frais d'abonnement pour les deux abonnements du groupe d'abonnements Sous1.</span><span class="sxs-lookup"><span data-stu-id="a07eb-244">You repeat the procedure described above to create subscription fees for both subscriptions in the subscription group Sub1.</span></span> <span data-ttu-id="a07eb-245">Le tableau suivant indique les transactions qui sont créées pour chaque abonnement lié au groupe d'abonnements.</span><span class="sxs-lookup"><span data-stu-id="a07eb-245">The following table shows the transactions that are created for each subscription that is attached to the subscription group.</span></span>

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
<th><p><span data-ttu-id="a07eb-246">Date du projet</span><span class="sxs-lookup"><span data-stu-id="a07eb-246">Project date</span></span></p></th>
<th><p><span data-ttu-id="a07eb-247">Abonnement</span><span class="sxs-lookup"><span data-stu-id="a07eb-247">Subscription</span></span></p></th>
<th><p><span data-ttu-id="a07eb-248">Projet</span><span class="sxs-lookup"><span data-stu-id="a07eb-248">Project</span></span></p></th>
<th><p><span data-ttu-id="a07eb-249">Catégorie</span><span class="sxs-lookup"><span data-stu-id="a07eb-249">Category</span></span></p></th>
<th><p><span data-ttu-id="a07eb-250">Date de début</span><span class="sxs-lookup"><span data-stu-id="a07eb-250">Start date</span></span></p></th>
<th><p><span data-ttu-id="a07eb-251">Date de fin</span><span class="sxs-lookup"><span data-stu-id="a07eb-251">End date</span></span></p></th>
<th><p><span data-ttu-id="a07eb-252">Devise de vente</span><span class="sxs-lookup"><span data-stu-id="a07eb-252">Sales currency</span></span></p></th>
<th><p><span data-ttu-id="a07eb-253">Prix de vente</span><span class="sxs-lookup"><span data-stu-id="a07eb-253">Sales price</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a07eb-254">28-07-2007</span><span class="sxs-lookup"><span data-stu-id="a07eb-254">28-07-2007</span></span></p></td>
<td><p><span data-ttu-id="a07eb-255">00020_135</span><span class="sxs-lookup"><span data-stu-id="a07eb-255">00020_135</span></span></p></td>
<td><p><span data-ttu-id="a07eb-256">9030</span><span class="sxs-lookup"><span data-stu-id="a07eb-256">9030</span></span></p></td>
<td><p><span data-ttu-id="a07eb-257">SousCat1</span><span class="sxs-lookup"><span data-stu-id="a07eb-257">SubCat1</span></span></p></td>
<td><p><span data-ttu-id="a07eb-258">01-01-2008</span><span class="sxs-lookup"><span data-stu-id="a07eb-258">01-01-2008</span></span></p></td>
<td><p><span data-ttu-id="a07eb-259">31-03-2008</span><span class="sxs-lookup"><span data-stu-id="a07eb-259">31-03-2008</span></span></p></td>
<td><p><span data-ttu-id="a07eb-260">EUR</span><span class="sxs-lookup"><span data-stu-id="a07eb-260">EUR</span></span></p></td>
<td><p><span data-ttu-id="a07eb-261">550</span><span class="sxs-lookup"><span data-stu-id="a07eb-261">550</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a07eb-262">28-07-2008</span><span class="sxs-lookup"><span data-stu-id="a07eb-262">28-07-2008</span></span></p></td>
<td><p><span data-ttu-id="a07eb-263">00021_135</span><span class="sxs-lookup"><span data-stu-id="a07eb-263">00021_135</span></span></p></td>
<td><p><span data-ttu-id="a07eb-264">9030</span><span class="sxs-lookup"><span data-stu-id="a07eb-264">9030</span></span></p></td>
<td><p><span data-ttu-id="a07eb-265">SousCat2</span><span class="sxs-lookup"><span data-stu-id="a07eb-265">SubCat2</span></span></p></td>
<td><p><span data-ttu-id="a07eb-266">01-01-2008</span><span class="sxs-lookup"><span data-stu-id="a07eb-266">01-01-2008</span></span></p></td>
<td><p><span data-ttu-id="a07eb-267">31-03-2008</span><span class="sxs-lookup"><span data-stu-id="a07eb-267">31-03-2008</span></span></p></td>
<td><p><span data-ttu-id="a07eb-268">EUR</span><span class="sxs-lookup"><span data-stu-id="a07eb-268">EUR</span></span></p></td>
<td><p><span data-ttu-id="a07eb-269">500</span><span class="sxs-lookup"><span data-stu-id="a07eb-269">500</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="a07eb-270">Pour la première transaction d'abonnement 00020\_135, le prix de vente de 550 EUR est calculé à partir du paramétrage du prix de vente d'abonnement défini pour la combinaison du projet et de la catégorie spécifiques.</span><span class="sxs-lookup"><span data-stu-id="a07eb-270">In the first transaction for subscription 00020\_135, the sales price of EUR 550 derives from the subscription sales price that is set up for the combination of the specific project and category.</span></span> <span data-ttu-id="a07eb-271">Pour la deuxième transaction d'abonnement 00021\_135, le prix de vente de 500 EUR est utilisé comme prix de vente d'abonnement du projet car aucun prix n'est défini pour la combinaison du projet 9030 et de la catégorie SousCat2.</span><span class="sxs-lookup"><span data-stu-id="a07eb-271">In the second transaction for subscription 00021\_135, the sales price of EUR 500 is used as the project subscription sales price because there is no price set up for the combination of project 9030 and category SubCat2.</span></span>

## <a name="see-also"></a><span data-ttu-id="a07eb-272">Voir également :</span><span class="sxs-lookup"><span data-stu-id="a07eb-272">See also</span></span>

[<span data-ttu-id="a07eb-273">Mise à jour et indexation des prix de vente des abonnements</span><span class="sxs-lookup"><span data-stu-id="a07eb-273">Update and index subscription sales prices</span></span>](update-and-index-subscription-sales-prices.md)

  


