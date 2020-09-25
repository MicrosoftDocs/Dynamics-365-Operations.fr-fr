---
title: Exemples et logique du rapport de vieillissement des stocks
description: Cette rubrique présente quelques exemples qui montrent comment interpréter les résultats d’un rapport de vieillissement des stocks.
author: RichardLuan
manager: tfehr
ms.date: 5/29/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventAgingStorage, InventAgingStorageChart, InventAgingStorageDetails
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: riluan
ms.search.validFrom: 2020-5-29
ms.dyn365.ops.version: ''
ms.openlocfilehash: a6e708e4dc818f20fc8d835053da75c2fe9c98f6
ms.sourcegitcommit: cd339f48066b1d0fc740b513cb72ea19015acd16
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/02/2020
ms.locfileid: "3759542"
---
# <a name="inventory-aging-report-examples-and-logic"></a><span data-ttu-id="a616e-103">Exemples et logique du rapport de vieillissement des stocks</span><span class="sxs-lookup"><span data-stu-id="a616e-103">Inventory aging report examples and logic</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="a616e-104">Cette rubrique présente quelques exemples qui montrent comment interpréter les résultats d’un rapport sur le **vieillissement des stocks**.</span><span class="sxs-lookup"><span data-stu-id="a616e-104">This topic presents some examples that show how to interpret the results of an **Inventory aging** report.</span></span> <span data-ttu-id="a616e-105">Ce rapport classe les quantités en stock et les valeurs de stock pour un article ou un groupe d’articles sélectionné dans plusieurs plages de périodes.</span><span class="sxs-lookup"><span data-stu-id="a616e-105">This report categorizes on-hand quantity and inventory values for a selected item or item group into several period buckets.</span></span> <span data-ttu-id="a616e-106">Cette rubrique montre également la logique interne du rapport.</span><span class="sxs-lookup"><span data-stu-id="a616e-106">This topic also shows the internal logic of the report.</span></span>

<span data-ttu-id="a616e-107">Les exemples de cette rubrique montrent les résultats présentés dans un rapport **Vieillissement des stocks** standard.</span><span class="sxs-lookup"><span data-stu-id="a616e-107">The examples in this topic show results that are presented on a standard **Inventory aging** report.</span></span> <span data-ttu-id="a616e-108">Cependant, en général, nous vous recommandons d’utiliser la version de ce rapport [Stockage des rapports de vieillissement des stocks](inventory-aging-report-storage.md), en particulier lorsque de nombreux articles et entrepôts doivent être traités.</span><span class="sxs-lookup"><span data-stu-id="a616e-108">However, in general, we recommend that you use the [Inventory aging report storage](inventory-aging-report-storage.md) version of this report, especially when you have many items and warehouses that must be processed.</span></span> <span data-ttu-id="a616e-109">Le stockage des rapports de vieillissement des stocks enregistre chaque rapport que vous générez, affiche les résultats sous forme de page interactive et de graphique et vous permet d’exporter n’importe quel rapport enregistré.</span><span class="sxs-lookup"><span data-stu-id="a616e-109">Inventory aging report storage saves each report that you generate, shows the results as an interactive page and a chart, and lets you export any saved report.</span></span>

## <a name="sample-data-that-is-used-in-these-examples"></a><span data-ttu-id="a616e-110">Exemples de données utilisées</span><span class="sxs-lookup"><span data-stu-id="a616e-110">Sample data that is used in these examples</span></span>

<span data-ttu-id="a616e-111">Les exemples de cette rubrique sont basés sur les exemples de données de transaction de stock décrits dans cette section.</span><span class="sxs-lookup"><span data-stu-id="a616e-111">The examples in this topic are based on the sample inventory transaction data that is described in this section.</span></span>

### <a name="storage-dimension-setup"></a><span data-ttu-id="a616e-112">Configuration de la dimension de stockage</span><span class="sxs-lookup"><span data-stu-id="a616e-112">Storage dimension setup</span></span>

<span data-ttu-id="a616e-113">L’exemple de système contient la configuration suivante des dimensions de stockage.</span><span class="sxs-lookup"><span data-stu-id="a616e-113">The example system contains the following setup of storage dimensions.</span></span>

| <span data-ttu-id="a616e-114">Nom</span><span class="sxs-lookup"><span data-stu-id="a616e-114">Name</span></span>      | <span data-ttu-id="a616e-115">Actifs</span><span class="sxs-lookup"><span data-stu-id="a616e-115">Active</span></span> | <span data-ttu-id="a616e-116">Stock physique</span><span class="sxs-lookup"><span data-stu-id="a616e-116">Physical inventory</span></span> | <span data-ttu-id="a616e-117">Stock financier</span><span class="sxs-lookup"><span data-stu-id="a616e-117">Financial inventory</span></span> |
|-----------|--------|--------------------|---------------------|
| <span data-ttu-id="a616e-118">Site</span><span class="sxs-lookup"><span data-stu-id="a616e-118">Site</span></span>      | <span data-ttu-id="a616e-119">Oui</span><span class="sxs-lookup"><span data-stu-id="a616e-119">Yes</span></span>    | <span data-ttu-id="a616e-120">Oui</span><span class="sxs-lookup"><span data-stu-id="a616e-120">Yes</span></span>                | <span data-ttu-id="a616e-121">Oui</span><span class="sxs-lookup"><span data-stu-id="a616e-121">Yes</span></span>                 |
| <span data-ttu-id="a616e-122">Entrepôt</span><span class="sxs-lookup"><span data-stu-id="a616e-122">Warehouse</span></span> | <span data-ttu-id="a616e-123">Oui</span><span class="sxs-lookup"><span data-stu-id="a616e-123">Yes</span></span>    | <span data-ttu-id="a616e-124">Oui</span><span class="sxs-lookup"><span data-stu-id="a616e-124">Yes</span></span>                | <span data-ttu-id="a616e-125">N°</span><span class="sxs-lookup"><span data-stu-id="a616e-125">No</span></span>                  |

### <a name="inventory-model"></a><span data-ttu-id="a616e-126">Modèle de stock</span><span class="sxs-lookup"><span data-stu-id="a616e-126">Inventory model</span></span>

<span data-ttu-id="a616e-127">Pour l’exemple de système, le modèle de stock pour les produits lancés est *FIFO*, et le paramètre **Prix de revient** du modèle de stock est *Inclure une valeur physique*.</span><span class="sxs-lookup"><span data-stu-id="a616e-127">For the example system, the inventory model for the released products is *FIFO*, and the **Cost price** setting for the inventory model is *Include physical value*.</span></span>

### <a name="inventory-transactions"></a><span data-ttu-id="a616e-128">Mouvements de stock</span><span class="sxs-lookup"><span data-stu-id="a616e-128">Inventory transactions</span></span>

<span data-ttu-id="a616e-129">L’exemple de système contient les transactions de stock suivantes pour un produit lancé portant le numéro d’article *1000*.</span><span class="sxs-lookup"><span data-stu-id="a616e-129">The example system contains the following inventory transactions for a released product that has the item number *1000*.</span></span>

| <span data-ttu-id="a616e-130">Référence</span><span class="sxs-lookup"><span data-stu-id="a616e-130">Reference</span></span>      | <span data-ttu-id="a616e-131">Site</span><span class="sxs-lookup"><span data-stu-id="a616e-131">Site</span></span> | <span data-ttu-id="a616e-132">Entrepôt</span><span class="sxs-lookup"><span data-stu-id="a616e-132">Warehouse</span></span> | <span data-ttu-id="a616e-133">Reçu</span><span class="sxs-lookup"><span data-stu-id="a616e-133">Receipt</span></span>   | <span data-ttu-id="a616e-134">Sortie</span><span class="sxs-lookup"><span data-stu-id="a616e-134">Issue</span></span> | <span data-ttu-id="a616e-135">Date physique</span><span class="sxs-lookup"><span data-stu-id="a616e-135">Physical date</span></span> | <span data-ttu-id="a616e-136">Date financière</span><span class="sxs-lookup"><span data-stu-id="a616e-136">Financial date</span></span> | <span data-ttu-id="a616e-137">Quantité</span><span class="sxs-lookup"><span data-stu-id="a616e-137">Quantity</span></span> | <span data-ttu-id="a616e-138">Coût</span><span class="sxs-lookup"><span data-stu-id="a616e-138">Cost amount</span></span> | <span data-ttu-id="a616e-139">Montant du coût physique</span><span class="sxs-lookup"><span data-stu-id="a616e-139">Physical cost amount</span></span> |
|----------------|------|-----------|-----------|-------|---------------|----------------|----------|-------------|----------------------|
| <span data-ttu-id="a616e-140">Commande fournisseur</span><span class="sxs-lookup"><span data-stu-id="a616e-140">Purchase order</span></span> | <span data-ttu-id="a616e-141">1</span><span class="sxs-lookup"><span data-stu-id="a616e-141">1</span></span>    | <span data-ttu-id="a616e-142">11</span><span class="sxs-lookup"><span data-stu-id="a616e-142">11</span></span>        | <span data-ttu-id="a616e-143">Acheté</span><span class="sxs-lookup"><span data-stu-id="a616e-143">Purchased</span></span> |       | <span data-ttu-id="a616e-144">15 mars</span><span class="sxs-lookup"><span data-stu-id="a616e-144">March 15</span></span>      | <span data-ttu-id="a616e-145">15 mars</span><span class="sxs-lookup"><span data-stu-id="a616e-145">March 15</span></span>       | <span data-ttu-id="a616e-146">10</span><span class="sxs-lookup"><span data-stu-id="a616e-146">10</span></span>       | <span data-ttu-id="a616e-147">1 000</span><span class="sxs-lookup"><span data-stu-id="a616e-147">1,000</span></span>       | <span data-ttu-id="a616e-148">1 000</span><span class="sxs-lookup"><span data-stu-id="a616e-148">1,000</span></span>                |
| <span data-ttu-id="a616e-149">Commande fournisseur</span><span class="sxs-lookup"><span data-stu-id="a616e-149">Purchase order</span></span> | <span data-ttu-id="a616e-150">2</span><span class="sxs-lookup"><span data-stu-id="a616e-150">2</span></span>    | <span data-ttu-id="a616e-151">21</span><span class="sxs-lookup"><span data-stu-id="a616e-151">21</span></span>        | <span data-ttu-id="a616e-152">Acheté</span><span class="sxs-lookup"><span data-stu-id="a616e-152">Purchased</span></span> |       | <span data-ttu-id="a616e-153">15 mars</span><span class="sxs-lookup"><span data-stu-id="a616e-153">March 15</span></span>      | <span data-ttu-id="a616e-154">15 mars</span><span class="sxs-lookup"><span data-stu-id="a616e-154">March 15</span></span>       | <span data-ttu-id="a616e-155">10</span><span class="sxs-lookup"><span data-stu-id="a616e-155">10</span></span>       | <span data-ttu-id="a616e-156">2,000</span><span class="sxs-lookup"><span data-stu-id="a616e-156">2,000</span></span>       | <span data-ttu-id="a616e-157">2,000</span><span class="sxs-lookup"><span data-stu-id="a616e-157">2,000</span></span>                |
| <span data-ttu-id="a616e-158">Commande fournisseur</span><span class="sxs-lookup"><span data-stu-id="a616e-158">Purchase order</span></span> | <span data-ttu-id="a616e-159">1</span><span class="sxs-lookup"><span data-stu-id="a616e-159">1</span></span>    | <span data-ttu-id="a616e-160">11</span><span class="sxs-lookup"><span data-stu-id="a616e-160">11</span></span>        | <span data-ttu-id="a616e-161">Reçu(e)</span><span class="sxs-lookup"><span data-stu-id="a616e-161">Received</span></span>  |       | <span data-ttu-id="a616e-162">15 avril</span><span class="sxs-lookup"><span data-stu-id="a616e-162">April 15</span></span>      |                | <span data-ttu-id="a616e-163">5</span><span class="sxs-lookup"><span data-stu-id="a616e-163">5</span></span>        |             | <span data-ttu-id="a616e-164">375</span><span class="sxs-lookup"><span data-stu-id="a616e-164">375</span></span>                  |
| <span data-ttu-id="a616e-165">Ordre de transfert</span><span class="sxs-lookup"><span data-stu-id="a616e-165">Transfer order</span></span> | <span data-ttu-id="a616e-166">1</span><span class="sxs-lookup"><span data-stu-id="a616e-166">1</span></span>    | <span data-ttu-id="a616e-167">11</span><span class="sxs-lookup"><span data-stu-id="a616e-167">11</span></span>        |           | <span data-ttu-id="a616e-168">Vendu</span><span class="sxs-lookup"><span data-stu-id="a616e-168">Sold</span></span>  | <span data-ttu-id="a616e-169">mai 2</span><span class="sxs-lookup"><span data-stu-id="a616e-169">May 2</span></span>         | <span data-ttu-id="a616e-170">mai 2</span><span class="sxs-lookup"><span data-stu-id="a616e-170">May 2</span></span>          | <span data-ttu-id="a616e-171">-5</span><span class="sxs-lookup"><span data-stu-id="a616e-171">-5</span></span>       | <span data-ttu-id="a616e-172">-458,33</span><span class="sxs-lookup"><span data-stu-id="a616e-172">-458.33</span></span>     | <span data-ttu-id="a616e-173">-458,33</span><span class="sxs-lookup"><span data-stu-id="a616e-173">-458.33</span></span>              |
| <span data-ttu-id="a616e-174">Ordre de transfert</span><span class="sxs-lookup"><span data-stu-id="a616e-174">Transfer order</span></span> | <span data-ttu-id="a616e-175">1</span><span class="sxs-lookup"><span data-stu-id="a616e-175">1</span></span>    | <span data-ttu-id="a616e-176">12</span><span class="sxs-lookup"><span data-stu-id="a616e-176">12</span></span>        | <span data-ttu-id="a616e-177">Acheté</span><span class="sxs-lookup"><span data-stu-id="a616e-177">Purchased</span></span> |       | <span data-ttu-id="a616e-178">mai 2</span><span class="sxs-lookup"><span data-stu-id="a616e-178">May 2</span></span>         | <span data-ttu-id="a616e-179">mai 2</span><span class="sxs-lookup"><span data-stu-id="a616e-179">May 2</span></span>          | <span data-ttu-id="a616e-180">5</span><span class="sxs-lookup"><span data-stu-id="a616e-180">5</span></span>        | <span data-ttu-id="a616e-181">458.33</span><span class="sxs-lookup"><span data-stu-id="a616e-181">458.33</span></span>      | <span data-ttu-id="a616e-182">458.33</span><span class="sxs-lookup"><span data-stu-id="a616e-182">458.33</span></span>               |
| <span data-ttu-id="a616e-183">Commandes client</span><span class="sxs-lookup"><span data-stu-id="a616e-183">Sales order</span></span>    | <span data-ttu-id="a616e-184">1</span><span class="sxs-lookup"><span data-stu-id="a616e-184">1</span></span>    | <span data-ttu-id="a616e-185">12</span><span class="sxs-lookup"><span data-stu-id="a616e-185">12</span></span>        |           | <span data-ttu-id="a616e-186">Vendu</span><span class="sxs-lookup"><span data-stu-id="a616e-186">Sold</span></span>  | <span data-ttu-id="a616e-187">mai 3</span><span class="sxs-lookup"><span data-stu-id="a616e-187">May 3</span></span>         | <span data-ttu-id="a616e-188">mai 3</span><span class="sxs-lookup"><span data-stu-id="a616e-188">May 3</span></span>          | <span data-ttu-id="a616e-189">-1</span><span class="sxs-lookup"><span data-stu-id="a616e-189">-1</span></span>       | <span data-ttu-id="a616e-190">-91,67</span><span class="sxs-lookup"><span data-stu-id="a616e-190">-91.67</span></span>      | <span data-ttu-id="a616e-191">-91,67</span><span class="sxs-lookup"><span data-stu-id="a616e-191">-91.67</span></span>               |

## <a name="how-quantities-and-amounts-in-each-period-bucket-are-calculated"></a><span data-ttu-id="a616e-192">Comment les quantités et les montants de chaque période sont calculés</span><span class="sxs-lookup"><span data-stu-id="a616e-192">How quantities and amounts in each period bucket are calculated</span></span>

<span data-ttu-id="a616e-193">En utilisant les exemples de données décrits dans les sections précédentes, vous pouvez exécuter un rapport **Vieillissement des stocks** contenant les paramètres suivants :</span><span class="sxs-lookup"><span data-stu-id="a616e-193">By using the sample data that is described in the previous sections, you can run an **Inventory aging** report that has the following settings:</span></span>

- <span data-ttu-id="a616e-194">**À ce jour :** *9 mai 2020*</span><span class="sxs-lookup"><span data-stu-id="a616e-194">**As of date:** *May 9, 2020*</span></span>
- <span data-ttu-id="a616e-195">**Site :** *Vue*</span><span class="sxs-lookup"><span data-stu-id="a616e-195">**Site:** *View*</span></span>
- <span data-ttu-id="a616e-196">**Entrepôt :** *Non*</span><span class="sxs-lookup"><span data-stu-id="a616e-196">**Warehouse:** *No*</span></span>
- <span data-ttu-id="a616e-197">**Numéro d’article :** *Total*</span><span class="sxs-lookup"><span data-stu-id="a616e-197">**Item number:** *Total*</span></span>
- <span data-ttu-id="a616e-198">**Période de vieillissement :** Définissez ce champ pour générer des compartiments mensuels.</span><span class="sxs-lookup"><span data-stu-id="a616e-198">**Aging period:** Set this field to generate monthly buckets.</span></span>

<span data-ttu-id="a616e-199">Dans ce cas, le contenu du rapport généré ressemblera à l’exemple suivant.</span><span class="sxs-lookup"><span data-stu-id="a616e-199">In this case, the content of the report that is generated will resemble the following example.</span></span>

<table>
<thead>
<tr>
    <th rowspan="2"><span data-ttu-id="a616e-200">numéro d’article</span><span class="sxs-lookup"><span data-stu-id="a616e-200">Item number</span></span></th>
    <th rowspan="2"><span data-ttu-id="a616e-201">Site</span><span class="sxs-lookup"><span data-stu-id="a616e-201">Site</span></span></th>
    <th rowspan="2"><span data-ttu-id="a616e-202">Quantité disponible</span><span class="sxs-lookup"><span data-stu-id="a616e-202">On-hand quantity</span></span></th>
    <th rowspan="2"><span data-ttu-id="a616e-203">Valeur disponible</span><span class="sxs-lookup"><span data-stu-id="a616e-203">On-hand value</span></span></th>
    <th rowspan="2"><span data-ttu-id="a616e-204">Quantité de valeur en stock</span><span class="sxs-lookup"><span data-stu-id="a616e-204">Inventory value quantity</span></span></th>
    <th rowspan="2"><span data-ttu-id="a616e-205">Valeur en stock</span><span class="sxs-lookup"><span data-stu-id="a616e-205">Inventory value</span></span></th>
    <th rowspan="2"><span data-ttu-id="a616e-206">Coût unitaire moyen</span><span class="sxs-lookup"><span data-stu-id="a616e-206">Average unit cost</span></span></th>
    <th colspan="2"><span data-ttu-id="a616e-207">08/05/2020 - 01/05/2020</span><span class="sxs-lookup"><span data-stu-id="a616e-207">5/8/2020 - 5/1/2020</span></span></th>
    <th colspan="2"><span data-ttu-id="a616e-208">30/04/2020 - 01/04/2020</span><span class="sxs-lookup"><span data-stu-id="a616e-208">4/30/2020 - 4/1/2020</span></span></th>
    <th colspan="2"><span data-ttu-id="a616e-209">31/03/2020 - 01/03/2020</span><span class="sxs-lookup"><span data-stu-id="a616e-209">3/31/2020 - 3/1/2020</span></span></th>
</tr>
<tr>
    <th><span data-ttu-id="a616e-210">P1:Quantité</span><span class="sxs-lookup"><span data-stu-id="a616e-210">P1:Quantity</span></span></th>
    <th><span data-ttu-id="a616e-211">P1:Montant</span><span class="sxs-lookup"><span data-stu-id="a616e-211">P1:Amount</span></span></th>
    <th><span data-ttu-id="a616e-212">P2:Quantité</span><span class="sxs-lookup"><span data-stu-id="a616e-212">P2:Quantity</span></span></th>
    <th><span data-ttu-id="a616e-213">P2:Montant</span><span class="sxs-lookup"><span data-stu-id="a616e-213">P2:Amount</span></span></th>
    <th><span data-ttu-id="a616e-214">P3:Quantité</span><span class="sxs-lookup"><span data-stu-id="a616e-214">P3:Quantity</span></span></th>
    <th><span data-ttu-id="a616e-215">P3:Montant</span><span class="sxs-lookup"><span data-stu-id="a616e-215">P3:Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
    <td><span data-ttu-id="a616e-216">1000</span><span class="sxs-lookup"><span data-stu-id="a616e-216">1000</span></span></td>
    <td><span data-ttu-id="a616e-217">1</span><span class="sxs-lookup"><span data-stu-id="a616e-217">1</span></span></td>
    <td><span data-ttu-id="a616e-218">14</span><span class="sxs-lookup"><span data-stu-id="a616e-218">14</span></span></td>
    <td><span data-ttu-id="a616e-219">1,283.33</span><span class="sxs-lookup"><span data-stu-id="a616e-219">1,283.33</span></span></td>
    <td><span data-ttu-id="a616e-220">14</span><span class="sxs-lookup"><span data-stu-id="a616e-220">14</span></span></td>
    <td><span data-ttu-id="a616e-221">1,283.33</span><span class="sxs-lookup"><span data-stu-id="a616e-221">1,283.33</span></span></td>
    <td><span data-ttu-id="a616e-222">91.67</span><span class="sxs-lookup"><span data-stu-id="a616e-222">91.67</span></span></td>
    <td></td>
    <td></td>
    <td><span data-ttu-id="a616e-223">5.00</span><span class="sxs-lookup"><span data-stu-id="a616e-223">5.00</span></span></td>
    <td><span data-ttu-id="a616e-224">458.33</span><span class="sxs-lookup"><span data-stu-id="a616e-224">458.33</span></span></td>
    <td><span data-ttu-id="a616e-225">9.00</span><span class="sxs-lookup"><span data-stu-id="a616e-225">9.00</span></span></td>
    <td><span data-ttu-id="a616e-226">825.00</span><span class="sxs-lookup"><span data-stu-id="a616e-226">825.00</span></span></td>
</tr>
<tr>
    <td><span data-ttu-id="a616e-227">1000</span><span class="sxs-lookup"><span data-stu-id="a616e-227">1000</span></span></td>
    <td><span data-ttu-id="a616e-228">2</span><span class="sxs-lookup"><span data-stu-id="a616e-228">2</span></span></td>
    <td><span data-ttu-id="a616e-229">10</span><span class="sxs-lookup"><span data-stu-id="a616e-229">10</span></span></td>
    <td><span data-ttu-id="a616e-230">2,000.00</span><span class="sxs-lookup"><span data-stu-id="a616e-230">2,000.00</span></span></td>
    <td><span data-ttu-id="a616e-231">10</span><span class="sxs-lookup"><span data-stu-id="a616e-231">10</span></span></td>
    <td><span data-ttu-id="a616e-232">2,000.00</span><span class="sxs-lookup"><span data-stu-id="a616e-232">2,000.00</span></span></td>
    <td><span data-ttu-id="a616e-233">200.00</span><span class="sxs-lookup"><span data-stu-id="a616e-233">200.00</span></span></td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
    <td><span data-ttu-id="a616e-234">10.00</span><span class="sxs-lookup"><span data-stu-id="a616e-234">10.00</span></span></td>
    <td><span data-ttu-id="a616e-235">2,000.00</span><span class="sxs-lookup"><span data-stu-id="a616e-235">2,000.00</span></span></td>
</tr>
</tbody>
<tfoot>
<tr>
    <td><span data-ttu-id="a616e-236"><strong>Nombre total : 1000</strong></span><span class="sxs-lookup"><span data-stu-id="a616e-236"><strong>1000 Totals</strong></span></span></td>
    <td></td>
    <td><span data-ttu-id="a616e-237"><strong>24.00</strong></span><span class="sxs-lookup"><span data-stu-id="a616e-237"><strong>24.00</strong></span></span></td>
    <td><span data-ttu-id="a616e-238"><strong>3,283.33</strong></span><span class="sxs-lookup"><span data-stu-id="a616e-238"><strong>3,283.33</strong></span></span></td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
    <td><span data-ttu-id="a616e-239"><strong>5.00</strong></span><span class="sxs-lookup"><span data-stu-id="a616e-239"><strong>5.00</strong></span></span></td>
    <td><span data-ttu-id="a616e-240"><strong>458.33</strong></span><span class="sxs-lookup"><span data-stu-id="a616e-240"><strong>458.33</strong></span></span></td>
    <td><span data-ttu-id="a616e-241"><strong>19</strong></span><span class="sxs-lookup"><span data-stu-id="a616e-241"><strong>19</strong></span></span></td>
    <td><span data-ttu-id="a616e-242"><strong>2,825.00</strong></span><span class="sxs-lookup"><span data-stu-id="a616e-242"><strong>2,825.00</strong></span></span></td>
</tr>
</tfoot>
</table>

<span data-ttu-id="a616e-243">Notez les détails suivants dans cet exemple de rapport :</span><span class="sxs-lookup"><span data-stu-id="a616e-243">Note the following details in this example report:</span></span>

- <span data-ttu-id="a616e-244">Les valeurs **Quantité de valeur du stock**, **Valeur du stock** et **Coût unitaire moyen** indiquées dans le rapport sont des valeurs pour la dimension de stock financier (**Site**, dans ce cas).</span><span class="sxs-lookup"><span data-stu-id="a616e-244">The **Inventory value quantity**, **Inventory value**, and **Average unit cost** values that are shown on the report are values for the financial inventory dimension (**Site**, in this case).</span></span>

    <span data-ttu-id="a616e-245">Par exemple, pour le site 1, le rapport affiche les informations suivantes :</span><span class="sxs-lookup"><span data-stu-id="a616e-245">For example, for site 1, the report shows the following information:</span></span>

    - <span data-ttu-id="a616e-246">La valeur **Quantité de valeur du stock** est *14* (= 10 + 5 – 5 + 5 – 1).</span><span class="sxs-lookup"><span data-stu-id="a616e-246">The **Inventory value quantity** value is *14* (= 10 + 5 – 5 + 5 – 1).</span></span>
    - <span data-ttu-id="a616e-247">La valeur **Quantité du stock** est *1 283,33* (= 1 000 + 375 – 458,33 + 458,33 – 91,67).</span><span class="sxs-lookup"><span data-stu-id="a616e-247">The **Inventory value** value is *1,283.33* (= 1,000 + 375 – 458.33 + 458.33 – 91.67).</span></span>
    - <span data-ttu-id="a616e-248">La valeur du **Coût unitaire moyen** est *91,67*.</span><span class="sxs-lookup"><span data-stu-id="a616e-248">The **Average unit cost** value is *91.67*.</span></span>
    - <span data-ttu-id="a616e-249">Les valeurs **Valeur disponible** et **Montant** de chaque période sont calculées à l’aide de la valeur **Coût unitaire moyen**.</span><span class="sxs-lookup"><span data-stu-id="a616e-249">The **On-hand value** value and the **Amount** value in each period bucket are calculated by using the **Average unit cost** value.</span></span>

- <span data-ttu-id="a616e-250">Le rapport détermine la quantité en stock pour chaque groupe de périodes en résumant la quantité totale des stocks reçus pour chaque groupe de période.</span><span class="sxs-lookup"><span data-stu-id="a616e-250">The report determines the on-hand quantity for each period bucket by summarizing the total received inventory quantity for each period bucket.</span></span> <span data-ttu-id="a616e-251">Il applique ensuite le principe du premier entré, premier sorti (FIFO) pour déduire la quantité totale délivrée, quel que soit le modèle de stock utilisé par les articles.</span><span class="sxs-lookup"><span data-stu-id="a616e-251">It then applies the first in, first out (FIFO) principle to deduct the total issued quantity, regardless of the inventory model that the items use.</span></span>

<span data-ttu-id="a616e-252">Si vous exécutez à nouveau le même rapport, mais cette fois, vous définissez à la fois les champs **Site** et **Entrepôt** sur *Afficher*, le nouveau rapport ressemblera à l’exemple suivant.</span><span class="sxs-lookup"><span data-stu-id="a616e-252">If you run the same report again, but this time you set both the **Site** and **Warehouse** fields to *View*, the new report will resemble the following example.</span></span>

<table>
<thead>
<tr>
    <th rowspan="2"><span data-ttu-id="a616e-253">numéro d’article</span><span class="sxs-lookup"><span data-stu-id="a616e-253">Item number</span></span></th>
    <th rowspan="2"><span data-ttu-id="a616e-254">Site</span><span class="sxs-lookup"><span data-stu-id="a616e-254">Site</span></span></th>
    <th rowspan="2"><span data-ttu-id="a616e-255">Entrepôt</span><span class="sxs-lookup"><span data-stu-id="a616e-255">Warehouse</span></span></th>
    <th rowspan="2"><span data-ttu-id="a616e-256">Quantité disponible</span><span class="sxs-lookup"><span data-stu-id="a616e-256">On-hand quantity</span></span></th>
    <th rowspan="2"><span data-ttu-id="a616e-257">Valeur disponible</span><span class="sxs-lookup"><span data-stu-id="a616e-257">On-hand value</span></span></th>
    <th rowspan="2"><span data-ttu-id="a616e-258">Quantité de valeur en stock</span><span class="sxs-lookup"><span data-stu-id="a616e-258">Inventory value quantity</span></span></th>
    <th rowspan="2"><span data-ttu-id="a616e-259">Valeur en stock</span><span class="sxs-lookup"><span data-stu-id="a616e-259">Inventory value</span></span></th>
    <th rowspan="2"><span data-ttu-id="a616e-260">Coût unitaire moyen</span><span class="sxs-lookup"><span data-stu-id="a616e-260">Average unit cost</span></span></th>
    <th colspan="2"><span data-ttu-id="a616e-261">08/05/2020 - 01/05/2020</span><span class="sxs-lookup"><span data-stu-id="a616e-261">5/8/2020 - 5/1/2020</span></span></th>
    <th colspan="2"><span data-ttu-id="a616e-262">30/04/2020 - 01/04/2020</span><span class="sxs-lookup"><span data-stu-id="a616e-262">4/30/2020 - 4/1/2020</span></span></th>
    <th colspan="2"><span data-ttu-id="a616e-263">31/03/2020 - 01/03/2020</span><span class="sxs-lookup"><span data-stu-id="a616e-263">3/31/2020 - 3/1/2020</span></span></th>
</tr>
<tr>
    <th><span data-ttu-id="a616e-264">P1:Quantité</span><span class="sxs-lookup"><span data-stu-id="a616e-264">P1:Quantity</span></span></th>
    <th><span data-ttu-id="a616e-265">P1:Montant</span><span class="sxs-lookup"><span data-stu-id="a616e-265">P1:Amount</span></span></th>
    <th><span data-ttu-id="a616e-266">P2:Quantité</span><span class="sxs-lookup"><span data-stu-id="a616e-266">P2:Quantity</span></span></th>
    <th><span data-ttu-id="a616e-267">P2:Montant</span><span class="sxs-lookup"><span data-stu-id="a616e-267">P2:Amount</span></span></th>
    <th><span data-ttu-id="a616e-268">P3:Quantité</span><span class="sxs-lookup"><span data-stu-id="a616e-268">P3:Quantity</span></span></th>
    <th><span data-ttu-id="a616e-269">P3:Montant</span><span class="sxs-lookup"><span data-stu-id="a616e-269">P3:Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
    <td><span data-ttu-id="a616e-270">1000</span><span class="sxs-lookup"><span data-stu-id="a616e-270">1000</span></span></td>
    <td><span data-ttu-id="a616e-271">1</span><span class="sxs-lookup"><span data-stu-id="a616e-271">1</span></span></td>
    <td><span data-ttu-id="a616e-272">11</span><span class="sxs-lookup"><span data-stu-id="a616e-272">11</span></span></td>
    <td><span data-ttu-id="a616e-273">10</span><span class="sxs-lookup"><span data-stu-id="a616e-273">10</span></span></td>
    <td><span data-ttu-id="a616e-274">916.67</span><span class="sxs-lookup"><span data-stu-id="a616e-274">916.67</span></span></td>
    <td><span data-ttu-id="a616e-275">14</span><span class="sxs-lookup"><span data-stu-id="a616e-275">14</span></span></td>
    <td><span data-ttu-id="a616e-276">1,283.33</span><span class="sxs-lookup"><span data-stu-id="a616e-276">1,283.33</span></span></td>
    <td><span data-ttu-id="a616e-277">91.67</span><span class="sxs-lookup"><span data-stu-id="a616e-277">91.67</span></span></td>
    <td></td>
    <td></td>
    <td><span data-ttu-id="a616e-278">5.00</span><span class="sxs-lookup"><span data-stu-id="a616e-278">5.00</span></span></td>
    <td><span data-ttu-id="a616e-279">458.33</span><span class="sxs-lookup"><span data-stu-id="a616e-279">458.33</span></span></td>
    <td><span data-ttu-id="a616e-280">5.00</span><span class="sxs-lookup"><span data-stu-id="a616e-280">5.00</span></span></td>
    <td><span data-ttu-id="a616e-281">458.33</span><span class="sxs-lookup"><span data-stu-id="a616e-281">458.33</span></span></td>
</tr>
<tr>
    <td><span data-ttu-id="a616e-282">1000</span><span class="sxs-lookup"><span data-stu-id="a616e-282">1000</span></span></td>
    <td><span data-ttu-id="a616e-283">1</span><span class="sxs-lookup"><span data-stu-id="a616e-283">1</span></span></td>
    <td><span data-ttu-id="a616e-284">12</span><span class="sxs-lookup"><span data-stu-id="a616e-284">12</span></span></td>
    <td><span data-ttu-id="a616e-285">4</span><span class="sxs-lookup"><span data-stu-id="a616e-285">4</span></span></td>
    <td><span data-ttu-id="a616e-286">366.67</span><span class="sxs-lookup"><span data-stu-id="a616e-286">366.67</span></span></td>
    <td><span data-ttu-id="a616e-287">14</span><span class="sxs-lookup"><span data-stu-id="a616e-287">14</span></span></td>
    <td><span data-ttu-id="a616e-288">1,283.33</span><span class="sxs-lookup"><span data-stu-id="a616e-288">1,283.33</span></span></td>
    <td><span data-ttu-id="a616e-289">91.67</span><span class="sxs-lookup"><span data-stu-id="a616e-289">91.67</span></span></td>
    <td><span data-ttu-id="a616e-290">4.00</span><span class="sxs-lookup"><span data-stu-id="a616e-290">4.00</span></span></td>
    <td><span data-ttu-id="a616e-291">366.67</span><span class="sxs-lookup"><span data-stu-id="a616e-291">366.67</span></span></td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
</tr>
<tr>
    <td><span data-ttu-id="a616e-292">1000</span><span class="sxs-lookup"><span data-stu-id="a616e-292">1000</span></span></td>
    <td><span data-ttu-id="a616e-293">2</span><span class="sxs-lookup"><span data-stu-id="a616e-293">2</span></span></td>
    <td></td>
    <td><span data-ttu-id="a616e-294">10</span><span class="sxs-lookup"><span data-stu-id="a616e-294">10</span></span></td>
    <td><span data-ttu-id="a616e-295">2,000.00</span><span class="sxs-lookup"><span data-stu-id="a616e-295">2,000.00</span></span></td>
    <td><span data-ttu-id="a616e-296">10</span><span class="sxs-lookup"><span data-stu-id="a616e-296">10</span></span></td>
    <td><span data-ttu-id="a616e-297">2,000.00</span><span class="sxs-lookup"><span data-stu-id="a616e-297">2,000.00</span></span></td>
    <td><span data-ttu-id="a616e-298">200.00</span><span class="sxs-lookup"><span data-stu-id="a616e-298">200.00</span></span></td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
    <td><span data-ttu-id="a616e-299">10.00</span><span class="sxs-lookup"><span data-stu-id="a616e-299">10.00</span></span></td>
    <td><span data-ttu-id="a616e-300">2,000.00</span><span class="sxs-lookup"><span data-stu-id="a616e-300">2,000.00</span></span></td>
</tr>
</tbody>
<tfoot>
<tr>
    <td><span data-ttu-id="a616e-301"><strong>Nombre total : 1000</strong></span><span class="sxs-lookup"><span data-stu-id="a616e-301"><strong>1000 Totals</strong></span></span></td>
    <td></td>
    <td></td>
    <td><span data-ttu-id="a616e-302"><strong>24.00</strong></span><span class="sxs-lookup"><span data-stu-id="a616e-302"><strong>24.00</strong></span></span></td>
    <td><span data-ttu-id="a616e-303"><strong>3,283.33</strong></span><span class="sxs-lookup"><span data-stu-id="a616e-303"><strong>3,283.33</strong></span></span></td>
    <td></td>
    <td></td>
    <td></td>
    <td><span data-ttu-id="a616e-304"><strong>4.00</strong></span><span class="sxs-lookup"><span data-stu-id="a616e-304"><strong>4.00</strong></span></span></td>
    <td><span data-ttu-id="a616e-305"><strong>366.67</strong></span><span class="sxs-lookup"><span data-stu-id="a616e-305"><strong>366.67</strong></span></span></td>
    <td><span data-ttu-id="a616e-306"><strong>5.00</strong></span><span class="sxs-lookup"><span data-stu-id="a616e-306"><strong>5.00</strong></span></span></td>
    <td><span data-ttu-id="a616e-307"><strong>458.33</strong></span><span class="sxs-lookup"><span data-stu-id="a616e-307"><strong>458.33</strong></span></span></td>
    <td><span data-ttu-id="a616e-308"><strong>15</strong></span><span class="sxs-lookup"><span data-stu-id="a616e-308"><strong>15</strong></span></span></td>
    <td><span data-ttu-id="a616e-309"><strong>2,458.33</strong></span><span class="sxs-lookup"><span data-stu-id="a616e-309"><strong>2,458.33</strong></span></span></td>
</tr>
</tfoot>
</table>

<span data-ttu-id="a616e-310">Cette fois, le site 1 est divisé en deux lignes, une pour l’entrepôt 11 et une pour l’entrepôt 12.</span><span class="sxs-lookup"><span data-stu-id="a616e-310">This time, site 1 is split into two rows, one for warehouse 11 and one for warehouse 12.</span></span> <span data-ttu-id="a616e-311">Cependant, les valeurs **Quantité de valeur du stock**, **Valeur du stock** et **Coût unitaire moyen** sont identiques, car **Entrepôt** n’est pas une dimension de stock financier.</span><span class="sxs-lookup"><span data-stu-id="a616e-311">However, the **Inventory value quantity**, **Inventory value**, and **Average unit cost** values are the same, because **Warehouse** isn't a financial inventory dimension.</span></span>

<span data-ttu-id="a616e-312">En outre, notez que la distribution des quantités du site 1 est différente.</span><span class="sxs-lookup"><span data-stu-id="a616e-312">Additionally, notice that the quantity distribution of site 1 is different.</span></span> <span data-ttu-id="a616e-313">Dans le premier rapport que vous avez exécuté, le système a ignoré l’ordre de transfert qui s’est produit sur le même site et a déduit la quantité de la facture de vente de la plage de périodes **31/03/2020 - 01/03/2020** dans le site 1.</span><span class="sxs-lookup"><span data-stu-id="a616e-313">In the first report that you ran, the system ignored the transfer order that occurred in the same site and deducted the quantity of the sales invoice from the **3/31/2020 - 3/1/2020** period bucket in site 1.</span></span> <span data-ttu-id="a616e-314">Cependant, dans le nouveau rapport, le système déduit la quantité de la facture de vente de la plage de périodes **08/05/2020 - 01/05/2020** dans l’entrepôt 12.</span><span class="sxs-lookup"><span data-stu-id="a616e-314">However, in the new report, the system deducts the quantity of the sales invoice from the **5/8/2020 - 5/1/2020** period bucket in warehouse 12.</span></span>

## <a name="effects-of-inventory-closing"></a><span data-ttu-id="a616e-315">Effets de la clôture des stocks</span><span class="sxs-lookup"><span data-stu-id="a616e-315">Effects of inventory closing</span></span>

<span data-ttu-id="a616e-316">Si vous exécutez la clôture des stocks pour mai, puis réexécutez le rapport précédent, mais que vous définissez le champ **À partir du** sur le *31 mai 2020*, vous remarquerez les résultats suivants :</span><span class="sxs-lookup"><span data-stu-id="a616e-316">If you run the inventory closing for May and then run the previous report again, but you set the **As of date** field to *May 31, 2020*, you will notice the following results:</span></span>

- <span data-ttu-id="a616e-317">Les valeurs **Valeur de stock** et **Coût unitaire moyen** sont mises à jour.</span><span class="sxs-lookup"><span data-stu-id="a616e-317">The **Inventory value** and **Average unit cost** values are updated.</span></span>
- <span data-ttu-id="a616e-318">La valeur **Valeur disponible** et toutes les valeurs **Montant** de chaque période sont mises à jour en conséquence.</span><span class="sxs-lookup"><span data-stu-id="a616e-318">The **On-hand value** value and all the **Amount** values in every period bucket are updated accordingly.</span></span>

<span data-ttu-id="a616e-319">Le nouveau rapport ressemblera à l’exemple ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="a616e-319">The new report will resemble the following example.</span></span>

<table>
<thead>
<tr>
    <th rowspan="2"><span data-ttu-id="a616e-320">numéro d’article</span><span class="sxs-lookup"><span data-stu-id="a616e-320">Item number</span></span></th>
    <th rowspan="2"><span data-ttu-id="a616e-321">Site</span><span class="sxs-lookup"><span data-stu-id="a616e-321">Site</span></span></th>
    <th rowspan="2"><span data-ttu-id="a616e-322">Entrepôt</span><span class="sxs-lookup"><span data-stu-id="a616e-322">Warehouse</span></span></th>
    <th rowspan="2"><span data-ttu-id="a616e-323">Quantité disponible</span><span class="sxs-lookup"><span data-stu-id="a616e-323">On-hand quantity</span></span></th>
    <th rowspan="2"><span data-ttu-id="a616e-324">Valeur disponible</span><span class="sxs-lookup"><span data-stu-id="a616e-324">On-hand value</span></span></th>
    <th rowspan="2"><span data-ttu-id="a616e-325">Quantité de valeur en stock</span><span class="sxs-lookup"><span data-stu-id="a616e-325">Inventory value quantity</span></span></th>
    <th rowspan="2"><span data-ttu-id="a616e-326">Valeur en stock</span><span class="sxs-lookup"><span data-stu-id="a616e-326">Inventory value</span></span></th>
    <th rowspan="2"><span data-ttu-id="a616e-327">Coût unitaire moyen</span><span class="sxs-lookup"><span data-stu-id="a616e-327">Average unit cost</span></span></th>
    <th colspan="2"><span data-ttu-id="a616e-328">31/05/2020 - 01/05/2020</span><span class="sxs-lookup"><span data-stu-id="a616e-328">5/31/2020 - 5/1/2020</span></span></th>
    <th colspan="2"><span data-ttu-id="a616e-329">30/04/2020 - 01/04/2020</span><span class="sxs-lookup"><span data-stu-id="a616e-329">4/30/2020 - 4/1/2020</span></span></th>
    <th colspan="2"><span data-ttu-id="a616e-330">31/03/2020 - 01/03/2020</span><span class="sxs-lookup"><span data-stu-id="a616e-330">3/31/2020 - 3/1/2020</span></span></th>
</tr>
<tr>
    <th><span data-ttu-id="a616e-331">P1:Quantité</span><span class="sxs-lookup"><span data-stu-id="a616e-331">P1:Quantity</span></span></th>
    <th><span data-ttu-id="a616e-332">P1:Montant</span><span class="sxs-lookup"><span data-stu-id="a616e-332">P1:Amount</span></span></th>
    <th><span data-ttu-id="a616e-333">P2:Quantité</span><span class="sxs-lookup"><span data-stu-id="a616e-333">P2:Quantity</span></span></th>
    <th><span data-ttu-id="a616e-334">P2:Montant</span><span class="sxs-lookup"><span data-stu-id="a616e-334">P2:Amount</span></span></th>
    <th><span data-ttu-id="a616e-335">P3:Quantité</span><span class="sxs-lookup"><span data-stu-id="a616e-335">P3:Quantity</span></span></th>
    <th><span data-ttu-id="a616e-336">P3:Montant</span><span class="sxs-lookup"><span data-stu-id="a616e-336">P3:Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
    <td><span data-ttu-id="a616e-337">1000</span><span class="sxs-lookup"><span data-stu-id="a616e-337">1000</span></span></td>
    <td><span data-ttu-id="a616e-338">1</span><span class="sxs-lookup"><span data-stu-id="a616e-338">1</span></span></td>
    <td><span data-ttu-id="a616e-339">11</span><span class="sxs-lookup"><span data-stu-id="a616e-339">11</span></span></td>
    <td><span data-ttu-id="a616e-340">10</span><span class="sxs-lookup"><span data-stu-id="a616e-340">10</span></span></td>
    <td><span data-ttu-id="a616e-341">910.70</span><span class="sxs-lookup"><span data-stu-id="a616e-341">910.70</span></span></td>
    <td><span data-ttu-id="a616e-342">14</span><span class="sxs-lookup"><span data-stu-id="a616e-342">14</span></span></td>
    <td><span data-ttu-id="a616e-343">1,275.00</span><span class="sxs-lookup"><span data-stu-id="a616e-343">1,275.00</span></span></td>
    <td><span data-ttu-id="a616e-344">91.07</span><span class="sxs-lookup"><span data-stu-id="a616e-344">91.07</span></span></td>
    <td><span data-ttu-id="a616e-345">0,00</span><span class="sxs-lookup"><span data-stu-id="a616e-345">0.00</span></span></td>
    <td></td>
    <td><span data-ttu-id="a616e-346">5.00</span><span class="sxs-lookup"><span data-stu-id="a616e-346">5.00</span></span></td>
    <td><span data-ttu-id="a616e-347">455.36</span><span class="sxs-lookup"><span data-stu-id="a616e-347">455.36</span></span></td>
    <td><span data-ttu-id="a616e-348">5.00</span><span class="sxs-lookup"><span data-stu-id="a616e-348">5.00</span></span></td>
    <td><span data-ttu-id="a616e-349">455.36</span><span class="sxs-lookup"><span data-stu-id="a616e-349">455.36</span></span></td>
</tr>
<tr>
    <td><span data-ttu-id="a616e-350">1000</span><span class="sxs-lookup"><span data-stu-id="a616e-350">1000</span></span></td>
    <td><span data-ttu-id="a616e-351">1</span><span class="sxs-lookup"><span data-stu-id="a616e-351">1</span></span></td>
    <td><span data-ttu-id="a616e-352">12</span><span class="sxs-lookup"><span data-stu-id="a616e-352">12</span></span></td>
    <td><span data-ttu-id="a616e-353">4</span><span class="sxs-lookup"><span data-stu-id="a616e-353">4</span></span></td>
    <td><span data-ttu-id="a616e-354">364.29</span><span class="sxs-lookup"><span data-stu-id="a616e-354">364.29</span></span></td>
    <td><span data-ttu-id="a616e-355">14</span><span class="sxs-lookup"><span data-stu-id="a616e-355">14</span></span></td>
    <td><span data-ttu-id="a616e-356">1,275.00</span><span class="sxs-lookup"><span data-stu-id="a616e-356">1,275.00</span></span></td>
    <td><span data-ttu-id="a616e-357">91.07</span><span class="sxs-lookup"><span data-stu-id="a616e-357">91.07</span></span></td>
    <td><span data-ttu-id="a616e-358">4.00</span><span class="sxs-lookup"><span data-stu-id="a616e-358">4.00</span></span></td>
    <td><span data-ttu-id="a616e-359">364.29</span><span class="sxs-lookup"><span data-stu-id="a616e-359">364.29</span></span></td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
</tr>
<tr>
    <td><span data-ttu-id="a616e-360">1000</span><span class="sxs-lookup"><span data-stu-id="a616e-360">1000</span></span></td>
    <td><span data-ttu-id="a616e-361">2</span><span class="sxs-lookup"><span data-stu-id="a616e-361">2</span></span></td>
    <td></td>
    <td><span data-ttu-id="a616e-362">10</span><span class="sxs-lookup"><span data-stu-id="a616e-362">10</span></span></td>
    <td><span data-ttu-id="a616e-363">2,000.00</span><span class="sxs-lookup"><span data-stu-id="a616e-363">2,000.00</span></span></td>
    <td><span data-ttu-id="a616e-364">10</span><span class="sxs-lookup"><span data-stu-id="a616e-364">10</span></span></td>
    <td><span data-ttu-id="a616e-365">2,000.00</span><span class="sxs-lookup"><span data-stu-id="a616e-365">2,000.00</span></span></td>
    <td><span data-ttu-id="a616e-366">200.00</span><span class="sxs-lookup"><span data-stu-id="a616e-366">200.00</span></span></td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
    <td><span data-ttu-id="a616e-367">10.00</span><span class="sxs-lookup"><span data-stu-id="a616e-367">10.00</span></span></td>
    <td><span data-ttu-id="a616e-368">2,000.00</span><span class="sxs-lookup"><span data-stu-id="a616e-368">2,000.00</span></span></td>
</tr>
</tbody>
<tfoot>
<tr>
    <td><span data-ttu-id="a616e-369"><strong>Nombre total : 1000</strong></span><span class="sxs-lookup"><span data-stu-id="a616e-369"><strong>1000 Totals</strong></span></span></td>
    <td></td>
    <td></td>
    <td><span data-ttu-id="a616e-370"><strong>24.00</strong></span><span class="sxs-lookup"><span data-stu-id="a616e-370"><strong>24.00</strong></span></span></td>
    <td><span data-ttu-id="a616e-371"><strong>3,275.00</strong></span><span class="sxs-lookup"><span data-stu-id="a616e-371"><strong>3,275.00</strong></span></span></td>
    <td></td>
    <td></td>
    <td></td>
    <td><span data-ttu-id="a616e-372"><strong>4.00</strong></span><span class="sxs-lookup"><span data-stu-id="a616e-372"><strong>4.00</strong></span></span></td>
    <td><span data-ttu-id="a616e-373"><strong>364.29</strong></span><span class="sxs-lookup"><span data-stu-id="a616e-373"><strong>364.29</strong></span></span></td>
    <td><span data-ttu-id="a616e-374"><strong>5.00</strong></span><span class="sxs-lookup"><span data-stu-id="a616e-374"><strong>5.00</strong></span></span></td>
    <td><span data-ttu-id="a616e-375"><strong>455.36</strong></span><span class="sxs-lookup"><span data-stu-id="a616e-375"><strong>455.36</strong></span></span></td>
    <td><span data-ttu-id="a616e-376"><strong>15</strong></span><span class="sxs-lookup"><span data-stu-id="a616e-376"><strong>15</strong></span></span></td>
    <td><span data-ttu-id="a616e-377"><strong>2,455.36</strong></span><span class="sxs-lookup"><span data-stu-id="a616e-377"><strong>2,455.36</strong></span></span></td>
</tr>
</tfoot>
</table>
