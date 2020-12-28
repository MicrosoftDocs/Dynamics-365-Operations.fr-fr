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
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4427869"
---
# <a name="inventory-aging-report-examples-and-logic"></a><span data-ttu-id="475a0-103">Exemples et logique du rapport de vieillissement des stocks</span><span class="sxs-lookup"><span data-stu-id="475a0-103">Inventory aging report examples and logic</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="475a0-104">Cette rubrique présente quelques exemples qui montrent comment interpréter les résultats d’un rapport sur le **vieillissement des stocks**.</span><span class="sxs-lookup"><span data-stu-id="475a0-104">This topic presents some examples that show how to interpret the results of an **Inventory aging** report.</span></span> <span data-ttu-id="475a0-105">Ce rapport classe les quantités en stock et les valeurs de stock pour un article ou un groupe d’articles sélectionné dans plusieurs plages de périodes.</span><span class="sxs-lookup"><span data-stu-id="475a0-105">This report categorizes on-hand quantity and inventory values for a selected item or item group into several period buckets.</span></span> <span data-ttu-id="475a0-106">Cette rubrique montre également la logique interne du rapport.</span><span class="sxs-lookup"><span data-stu-id="475a0-106">This topic also shows the internal logic of the report.</span></span>

<span data-ttu-id="475a0-107">Les exemples de cette rubrique montrent les résultats présentés dans un rapport **Vieillissement des stocks** standard.</span><span class="sxs-lookup"><span data-stu-id="475a0-107">The examples in this topic show results that are presented on a standard **Inventory aging** report.</span></span> <span data-ttu-id="475a0-108">Cependant, en général, nous vous recommandons d’utiliser la version de ce rapport [Stockage des rapports de vieillissement des stocks](inventory-aging-report-storage.md), en particulier lorsque de nombreux articles et entrepôts doivent être traités.</span><span class="sxs-lookup"><span data-stu-id="475a0-108">However, in general, we recommend that you use the [Inventory aging report storage](inventory-aging-report-storage.md) version of this report, especially when you have many items and warehouses that must be processed.</span></span> <span data-ttu-id="475a0-109">Le stockage des rapports de vieillissement des stocks enregistre chaque rapport que vous générez, affiche les résultats sous forme de page interactive et de graphique et vous permet d’exporter n’importe quel rapport enregistré.</span><span class="sxs-lookup"><span data-stu-id="475a0-109">Inventory aging report storage saves each report that you generate, shows the results as an interactive page and a chart, and lets you export any saved report.</span></span>

## <a name="sample-data-that-is-used-in-these-examples"></a><span data-ttu-id="475a0-110">Exemples de données utilisées</span><span class="sxs-lookup"><span data-stu-id="475a0-110">Sample data that is used in these examples</span></span>

<span data-ttu-id="475a0-111">Les exemples de cette rubrique sont basés sur les exemples de données de transaction de stock décrits dans cette section.</span><span class="sxs-lookup"><span data-stu-id="475a0-111">The examples in this topic are based on the sample inventory transaction data that is described in this section.</span></span>

### <a name="storage-dimension-setup"></a><span data-ttu-id="475a0-112">Configuration de la dimension de stockage</span><span class="sxs-lookup"><span data-stu-id="475a0-112">Storage dimension setup</span></span>

<span data-ttu-id="475a0-113">L’exemple de système contient la configuration suivante des dimensions de stockage.</span><span class="sxs-lookup"><span data-stu-id="475a0-113">The example system contains the following setup of storage dimensions.</span></span>

| <span data-ttu-id="475a0-114">Nom</span><span class="sxs-lookup"><span data-stu-id="475a0-114">Name</span></span>      | <span data-ttu-id="475a0-115">Actifs</span><span class="sxs-lookup"><span data-stu-id="475a0-115">Active</span></span> | <span data-ttu-id="475a0-116">Stock physique</span><span class="sxs-lookup"><span data-stu-id="475a0-116">Physical inventory</span></span> | <span data-ttu-id="475a0-117">Stock financier</span><span class="sxs-lookup"><span data-stu-id="475a0-117">Financial inventory</span></span> |
|-----------|--------|--------------------|---------------------|
| <span data-ttu-id="475a0-118">Site</span><span class="sxs-lookup"><span data-stu-id="475a0-118">Site</span></span>      | <span data-ttu-id="475a0-119">Oui</span><span class="sxs-lookup"><span data-stu-id="475a0-119">Yes</span></span>    | <span data-ttu-id="475a0-120">Oui</span><span class="sxs-lookup"><span data-stu-id="475a0-120">Yes</span></span>                | <span data-ttu-id="475a0-121">Oui</span><span class="sxs-lookup"><span data-stu-id="475a0-121">Yes</span></span>                 |
| <span data-ttu-id="475a0-122">Entrepôt</span><span class="sxs-lookup"><span data-stu-id="475a0-122">Warehouse</span></span> | <span data-ttu-id="475a0-123">Oui</span><span class="sxs-lookup"><span data-stu-id="475a0-123">Yes</span></span>    | <span data-ttu-id="475a0-124">Oui</span><span class="sxs-lookup"><span data-stu-id="475a0-124">Yes</span></span>                | <span data-ttu-id="475a0-125">N°</span><span class="sxs-lookup"><span data-stu-id="475a0-125">No</span></span>                  |

### <a name="inventory-model"></a><span data-ttu-id="475a0-126">Modèle de stock</span><span class="sxs-lookup"><span data-stu-id="475a0-126">Inventory model</span></span>

<span data-ttu-id="475a0-127">Pour l’exemple de système, le modèle de stock pour les produits lancés est *FIFO*, et le paramètre **Prix de revient** du modèle de stock est *Inclure une valeur physique*.</span><span class="sxs-lookup"><span data-stu-id="475a0-127">For the example system, the inventory model for the released products is *FIFO*, and the **Cost price** setting for the inventory model is *Include physical value*.</span></span>

### <a name="inventory-transactions"></a><span data-ttu-id="475a0-128">Mouvements de stock</span><span class="sxs-lookup"><span data-stu-id="475a0-128">Inventory transactions</span></span>

<span data-ttu-id="475a0-129">L’exemple de système contient les transactions de stock suivantes pour un produit lancé portant le numéro d’article *1000*.</span><span class="sxs-lookup"><span data-stu-id="475a0-129">The example system contains the following inventory transactions for a released product that has the item number *1000*.</span></span>

| <span data-ttu-id="475a0-130">Référence</span><span class="sxs-lookup"><span data-stu-id="475a0-130">Reference</span></span>      | <span data-ttu-id="475a0-131">Site</span><span class="sxs-lookup"><span data-stu-id="475a0-131">Site</span></span> | <span data-ttu-id="475a0-132">Entrepôt</span><span class="sxs-lookup"><span data-stu-id="475a0-132">Warehouse</span></span> | <span data-ttu-id="475a0-133">Reçu</span><span class="sxs-lookup"><span data-stu-id="475a0-133">Receipt</span></span>   | <span data-ttu-id="475a0-134">Sortie</span><span class="sxs-lookup"><span data-stu-id="475a0-134">Issue</span></span> | <span data-ttu-id="475a0-135">Date physique</span><span class="sxs-lookup"><span data-stu-id="475a0-135">Physical date</span></span> | <span data-ttu-id="475a0-136">Date financière</span><span class="sxs-lookup"><span data-stu-id="475a0-136">Financial date</span></span> | <span data-ttu-id="475a0-137">Quantité</span><span class="sxs-lookup"><span data-stu-id="475a0-137">Quantity</span></span> | <span data-ttu-id="475a0-138">Coût</span><span class="sxs-lookup"><span data-stu-id="475a0-138">Cost amount</span></span> | <span data-ttu-id="475a0-139">Montant du coût physique</span><span class="sxs-lookup"><span data-stu-id="475a0-139">Physical cost amount</span></span> |
|----------------|------|-----------|-----------|-------|---------------|----------------|----------|-------------|----------------------|
| <span data-ttu-id="475a0-140">Commande fournisseur</span><span class="sxs-lookup"><span data-stu-id="475a0-140">Purchase order</span></span> | <span data-ttu-id="475a0-141">1</span><span class="sxs-lookup"><span data-stu-id="475a0-141">1</span></span>    | <span data-ttu-id="475a0-142">11</span><span class="sxs-lookup"><span data-stu-id="475a0-142">11</span></span>        | <span data-ttu-id="475a0-143">Acheté</span><span class="sxs-lookup"><span data-stu-id="475a0-143">Purchased</span></span> |       | <span data-ttu-id="475a0-144">15 mars</span><span class="sxs-lookup"><span data-stu-id="475a0-144">March 15</span></span>      | <span data-ttu-id="475a0-145">15 mars</span><span class="sxs-lookup"><span data-stu-id="475a0-145">March 15</span></span>       | <span data-ttu-id="475a0-146">10</span><span class="sxs-lookup"><span data-stu-id="475a0-146">10</span></span>       | <span data-ttu-id="475a0-147">1 000</span><span class="sxs-lookup"><span data-stu-id="475a0-147">1,000</span></span>       | <span data-ttu-id="475a0-148">1 000</span><span class="sxs-lookup"><span data-stu-id="475a0-148">1,000</span></span>                |
| <span data-ttu-id="475a0-149">Commande fournisseur</span><span class="sxs-lookup"><span data-stu-id="475a0-149">Purchase order</span></span> | <span data-ttu-id="475a0-150">2</span><span class="sxs-lookup"><span data-stu-id="475a0-150">2</span></span>    | <span data-ttu-id="475a0-151">21</span><span class="sxs-lookup"><span data-stu-id="475a0-151">21</span></span>        | <span data-ttu-id="475a0-152">Acheté</span><span class="sxs-lookup"><span data-stu-id="475a0-152">Purchased</span></span> |       | <span data-ttu-id="475a0-153">15 mars</span><span class="sxs-lookup"><span data-stu-id="475a0-153">March 15</span></span>      | <span data-ttu-id="475a0-154">15 mars</span><span class="sxs-lookup"><span data-stu-id="475a0-154">March 15</span></span>       | <span data-ttu-id="475a0-155">10</span><span class="sxs-lookup"><span data-stu-id="475a0-155">10</span></span>       | <span data-ttu-id="475a0-156">2,000</span><span class="sxs-lookup"><span data-stu-id="475a0-156">2,000</span></span>       | <span data-ttu-id="475a0-157">2,000</span><span class="sxs-lookup"><span data-stu-id="475a0-157">2,000</span></span>                |
| <span data-ttu-id="475a0-158">Commande fournisseur</span><span class="sxs-lookup"><span data-stu-id="475a0-158">Purchase order</span></span> | <span data-ttu-id="475a0-159">1</span><span class="sxs-lookup"><span data-stu-id="475a0-159">1</span></span>    | <span data-ttu-id="475a0-160">11</span><span class="sxs-lookup"><span data-stu-id="475a0-160">11</span></span>        | <span data-ttu-id="475a0-161">Reçu(e)</span><span class="sxs-lookup"><span data-stu-id="475a0-161">Received</span></span>  |       | <span data-ttu-id="475a0-162">15 avril</span><span class="sxs-lookup"><span data-stu-id="475a0-162">April 15</span></span>      |                | <span data-ttu-id="475a0-163">5</span><span class="sxs-lookup"><span data-stu-id="475a0-163">5</span></span>        |             | <span data-ttu-id="475a0-164">375</span><span class="sxs-lookup"><span data-stu-id="475a0-164">375</span></span>                  |
| <span data-ttu-id="475a0-165">Ordre de transfert</span><span class="sxs-lookup"><span data-stu-id="475a0-165">Transfer order</span></span> | <span data-ttu-id="475a0-166">1</span><span class="sxs-lookup"><span data-stu-id="475a0-166">1</span></span>    | <span data-ttu-id="475a0-167">11</span><span class="sxs-lookup"><span data-stu-id="475a0-167">11</span></span>        |           | <span data-ttu-id="475a0-168">Vendu</span><span class="sxs-lookup"><span data-stu-id="475a0-168">Sold</span></span>  | <span data-ttu-id="475a0-169">mai 2</span><span class="sxs-lookup"><span data-stu-id="475a0-169">May 2</span></span>         | <span data-ttu-id="475a0-170">mai 2</span><span class="sxs-lookup"><span data-stu-id="475a0-170">May 2</span></span>          | <span data-ttu-id="475a0-171">-5</span><span class="sxs-lookup"><span data-stu-id="475a0-171">-5</span></span>       | <span data-ttu-id="475a0-172">-458,33</span><span class="sxs-lookup"><span data-stu-id="475a0-172">-458.33</span></span>     | <span data-ttu-id="475a0-173">-458,33</span><span class="sxs-lookup"><span data-stu-id="475a0-173">-458.33</span></span>              |
| <span data-ttu-id="475a0-174">Ordre de transfert</span><span class="sxs-lookup"><span data-stu-id="475a0-174">Transfer order</span></span> | <span data-ttu-id="475a0-175">1</span><span class="sxs-lookup"><span data-stu-id="475a0-175">1</span></span>    | <span data-ttu-id="475a0-176">12</span><span class="sxs-lookup"><span data-stu-id="475a0-176">12</span></span>        | <span data-ttu-id="475a0-177">Acheté</span><span class="sxs-lookup"><span data-stu-id="475a0-177">Purchased</span></span> |       | <span data-ttu-id="475a0-178">mai 2</span><span class="sxs-lookup"><span data-stu-id="475a0-178">May 2</span></span>         | <span data-ttu-id="475a0-179">mai 2</span><span class="sxs-lookup"><span data-stu-id="475a0-179">May 2</span></span>          | <span data-ttu-id="475a0-180">5</span><span class="sxs-lookup"><span data-stu-id="475a0-180">5</span></span>        | <span data-ttu-id="475a0-181">458.33</span><span class="sxs-lookup"><span data-stu-id="475a0-181">458.33</span></span>      | <span data-ttu-id="475a0-182">458.33</span><span class="sxs-lookup"><span data-stu-id="475a0-182">458.33</span></span>               |
| <span data-ttu-id="475a0-183">Commandes client</span><span class="sxs-lookup"><span data-stu-id="475a0-183">Sales order</span></span>    | <span data-ttu-id="475a0-184">1</span><span class="sxs-lookup"><span data-stu-id="475a0-184">1</span></span>    | <span data-ttu-id="475a0-185">12</span><span class="sxs-lookup"><span data-stu-id="475a0-185">12</span></span>        |           | <span data-ttu-id="475a0-186">Vendu</span><span class="sxs-lookup"><span data-stu-id="475a0-186">Sold</span></span>  | <span data-ttu-id="475a0-187">mai 3</span><span class="sxs-lookup"><span data-stu-id="475a0-187">May 3</span></span>         | <span data-ttu-id="475a0-188">mai 3</span><span class="sxs-lookup"><span data-stu-id="475a0-188">May 3</span></span>          | <span data-ttu-id="475a0-189">-1</span><span class="sxs-lookup"><span data-stu-id="475a0-189">-1</span></span>       | <span data-ttu-id="475a0-190">-91,67</span><span class="sxs-lookup"><span data-stu-id="475a0-190">-91.67</span></span>      | <span data-ttu-id="475a0-191">-91,67</span><span class="sxs-lookup"><span data-stu-id="475a0-191">-91.67</span></span>               |

## <a name="how-quantities-and-amounts-in-each-period-bucket-are-calculated"></a><span data-ttu-id="475a0-192">Comment les quantités et les montants de chaque période sont calculés</span><span class="sxs-lookup"><span data-stu-id="475a0-192">How quantities and amounts in each period bucket are calculated</span></span>

<span data-ttu-id="475a0-193">En utilisant les exemples de données décrits dans les sections précédentes, vous pouvez exécuter un rapport **Vieillissement des stocks** contenant les paramètres suivants :</span><span class="sxs-lookup"><span data-stu-id="475a0-193">By using the sample data that is described in the previous sections, you can run an **Inventory aging** report that has the following settings:</span></span>

- <span data-ttu-id="475a0-194">**À ce jour :** *9 mai 2020*</span><span class="sxs-lookup"><span data-stu-id="475a0-194">**As of date:** *May 9, 2020*</span></span>
- <span data-ttu-id="475a0-195">**Site :** *Vue*</span><span class="sxs-lookup"><span data-stu-id="475a0-195">**Site:** *View*</span></span>
- <span data-ttu-id="475a0-196">**Entrepôt :** *Non*</span><span class="sxs-lookup"><span data-stu-id="475a0-196">**Warehouse:** *No*</span></span>
- <span data-ttu-id="475a0-197">**Numéro d’article :** *Total*</span><span class="sxs-lookup"><span data-stu-id="475a0-197">**Item number:** *Total*</span></span>
- <span data-ttu-id="475a0-198">**Période de vieillissement :** Définissez ce champ pour générer des compartiments mensuels.</span><span class="sxs-lookup"><span data-stu-id="475a0-198">**Aging period:** Set this field to generate monthly buckets.</span></span>

<span data-ttu-id="475a0-199">Dans ce cas, le contenu du rapport généré ressemblera à l’exemple suivant.</span><span class="sxs-lookup"><span data-stu-id="475a0-199">In this case, the content of the report that is generated will resemble the following example.</span></span>

<table>
<thead>
<tr>
    <th rowspan="2"><span data-ttu-id="475a0-200">numéro d’article</span><span class="sxs-lookup"><span data-stu-id="475a0-200">Item number</span></span></th>
    <th rowspan="2"><span data-ttu-id="475a0-201">Site</span><span class="sxs-lookup"><span data-stu-id="475a0-201">Site</span></span></th>
    <th rowspan="2"><span data-ttu-id="475a0-202">Quantité disponible</span><span class="sxs-lookup"><span data-stu-id="475a0-202">On-hand quantity</span></span></th>
    <th rowspan="2"><span data-ttu-id="475a0-203">Valeur disponible</span><span class="sxs-lookup"><span data-stu-id="475a0-203">On-hand value</span></span></th>
    <th rowspan="2"><span data-ttu-id="475a0-204">Quantité de valeur en stock</span><span class="sxs-lookup"><span data-stu-id="475a0-204">Inventory value quantity</span></span></th>
    <th rowspan="2"><span data-ttu-id="475a0-205">Valeur en stock</span><span class="sxs-lookup"><span data-stu-id="475a0-205">Inventory value</span></span></th>
    <th rowspan="2"><span data-ttu-id="475a0-206">Coût unitaire moyen</span><span class="sxs-lookup"><span data-stu-id="475a0-206">Average unit cost</span></span></th>
    <th colspan="2"><span data-ttu-id="475a0-207">08/05/2020 - 01/05/2020</span><span class="sxs-lookup"><span data-stu-id="475a0-207">5/8/2020 - 5/1/2020</span></span></th>
    <th colspan="2"><span data-ttu-id="475a0-208">30/04/2020 - 01/04/2020</span><span class="sxs-lookup"><span data-stu-id="475a0-208">4/30/2020 - 4/1/2020</span></span></th>
    <th colspan="2"><span data-ttu-id="475a0-209">31/03/2020 - 01/03/2020</span><span class="sxs-lookup"><span data-stu-id="475a0-209">3/31/2020 - 3/1/2020</span></span></th>
</tr>
<tr>
    <th><span data-ttu-id="475a0-210">P1:Quantité</span><span class="sxs-lookup"><span data-stu-id="475a0-210">P1:Quantity</span></span></th>
    <th><span data-ttu-id="475a0-211">P1:Montant</span><span class="sxs-lookup"><span data-stu-id="475a0-211">P1:Amount</span></span></th>
    <th><span data-ttu-id="475a0-212">P2:Quantité</span><span class="sxs-lookup"><span data-stu-id="475a0-212">P2:Quantity</span></span></th>
    <th><span data-ttu-id="475a0-213">P2:Montant</span><span class="sxs-lookup"><span data-stu-id="475a0-213">P2:Amount</span></span></th>
    <th><span data-ttu-id="475a0-214">P3:Quantité</span><span class="sxs-lookup"><span data-stu-id="475a0-214">P3:Quantity</span></span></th>
    <th><span data-ttu-id="475a0-215">P3:Montant</span><span class="sxs-lookup"><span data-stu-id="475a0-215">P3:Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
    <td><span data-ttu-id="475a0-216">1000</span><span class="sxs-lookup"><span data-stu-id="475a0-216">1000</span></span></td>
    <td><span data-ttu-id="475a0-217">1</span><span class="sxs-lookup"><span data-stu-id="475a0-217">1</span></span></td>
    <td><span data-ttu-id="475a0-218">14</span><span class="sxs-lookup"><span data-stu-id="475a0-218">14</span></span></td>
    <td><span data-ttu-id="475a0-219">1,283.33</span><span class="sxs-lookup"><span data-stu-id="475a0-219">1,283.33</span></span></td>
    <td><span data-ttu-id="475a0-220">14</span><span class="sxs-lookup"><span data-stu-id="475a0-220">14</span></span></td>
    <td><span data-ttu-id="475a0-221">1,283.33</span><span class="sxs-lookup"><span data-stu-id="475a0-221">1,283.33</span></span></td>
    <td><span data-ttu-id="475a0-222">91.67</span><span class="sxs-lookup"><span data-stu-id="475a0-222">91.67</span></span></td>
    <td></td>
    <td></td>
    <td><span data-ttu-id="475a0-223">5.00</span><span class="sxs-lookup"><span data-stu-id="475a0-223">5.00</span></span></td>
    <td><span data-ttu-id="475a0-224">458.33</span><span class="sxs-lookup"><span data-stu-id="475a0-224">458.33</span></span></td>
    <td><span data-ttu-id="475a0-225">9.00</span><span class="sxs-lookup"><span data-stu-id="475a0-225">9.00</span></span></td>
    <td><span data-ttu-id="475a0-226">825.00</span><span class="sxs-lookup"><span data-stu-id="475a0-226">825.00</span></span></td>
</tr>
<tr>
    <td><span data-ttu-id="475a0-227">1000</span><span class="sxs-lookup"><span data-stu-id="475a0-227">1000</span></span></td>
    <td><span data-ttu-id="475a0-228">2</span><span class="sxs-lookup"><span data-stu-id="475a0-228">2</span></span></td>
    <td><span data-ttu-id="475a0-229">10</span><span class="sxs-lookup"><span data-stu-id="475a0-229">10</span></span></td>
    <td><span data-ttu-id="475a0-230">2,000.00</span><span class="sxs-lookup"><span data-stu-id="475a0-230">2,000.00</span></span></td>
    <td><span data-ttu-id="475a0-231">10</span><span class="sxs-lookup"><span data-stu-id="475a0-231">10</span></span></td>
    <td><span data-ttu-id="475a0-232">2,000.00</span><span class="sxs-lookup"><span data-stu-id="475a0-232">2,000.00</span></span></td>
    <td><span data-ttu-id="475a0-233">200.00</span><span class="sxs-lookup"><span data-stu-id="475a0-233">200.00</span></span></td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
    <td><span data-ttu-id="475a0-234">10.00</span><span class="sxs-lookup"><span data-stu-id="475a0-234">10.00</span></span></td>
    <td><span data-ttu-id="475a0-235">2,000.00</span><span class="sxs-lookup"><span data-stu-id="475a0-235">2,000.00</span></span></td>
</tr>
</tbody>
<tfoot>
<tr>
    <td><span data-ttu-id="475a0-236"><strong>Nombre total : 1000</strong></span><span class="sxs-lookup"><span data-stu-id="475a0-236"><strong>1000 Totals</strong></span></span></td>
    <td></td>
    <td><span data-ttu-id="475a0-237"><strong>24.00</strong></span><span class="sxs-lookup"><span data-stu-id="475a0-237"><strong>24.00</strong></span></span></td>
    <td><span data-ttu-id="475a0-238"><strong>3,283.33</strong></span><span class="sxs-lookup"><span data-stu-id="475a0-238"><strong>3,283.33</strong></span></span></td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
    <td><span data-ttu-id="475a0-239"><strong>5.00</strong></span><span class="sxs-lookup"><span data-stu-id="475a0-239"><strong>5.00</strong></span></span></td>
    <td><span data-ttu-id="475a0-240"><strong>458.33</strong></span><span class="sxs-lookup"><span data-stu-id="475a0-240"><strong>458.33</strong></span></span></td>
    <td><span data-ttu-id="475a0-241"><strong>19</strong></span><span class="sxs-lookup"><span data-stu-id="475a0-241"><strong>19</strong></span></span></td>
    <td><span data-ttu-id="475a0-242"><strong>2,825.00</strong></span><span class="sxs-lookup"><span data-stu-id="475a0-242"><strong>2,825.00</strong></span></span></td>
</tr>
</tfoot>
</table>

<span data-ttu-id="475a0-243">Notez les détails suivants dans cet exemple de rapport :</span><span class="sxs-lookup"><span data-stu-id="475a0-243">Note the following details in this example report:</span></span>

- <span data-ttu-id="475a0-244">Les valeurs **Quantité de valeur du stock**, **Valeur du stock** et **Coût unitaire moyen** indiquées dans le rapport sont des valeurs pour la dimension de stock financier (**Site**, dans ce cas).</span><span class="sxs-lookup"><span data-stu-id="475a0-244">The **Inventory value quantity**, **Inventory value**, and **Average unit cost** values that are shown on the report are values for the financial inventory dimension (**Site**, in this case).</span></span>

    <span data-ttu-id="475a0-245">Par exemple, pour le site 1, le rapport affiche les informations suivantes :</span><span class="sxs-lookup"><span data-stu-id="475a0-245">For example, for site 1, the report shows the following information:</span></span>

    - <span data-ttu-id="475a0-246">La valeur **Quantité de valeur du stock** est *14* (= 10 + 5 – 5 + 5 – 1).</span><span class="sxs-lookup"><span data-stu-id="475a0-246">The **Inventory value quantity** value is *14* (= 10 + 5 – 5 + 5 – 1).</span></span>
    - <span data-ttu-id="475a0-247">La valeur **Quantité du stock** est *1 283,33* (= 1 000 + 375 – 458,33 + 458,33 – 91,67).</span><span class="sxs-lookup"><span data-stu-id="475a0-247">The **Inventory value** value is *1,283.33* (= 1,000 + 375 – 458.33 + 458.33 – 91.67).</span></span>
    - <span data-ttu-id="475a0-248">La valeur du **Coût unitaire moyen** est *91,67*.</span><span class="sxs-lookup"><span data-stu-id="475a0-248">The **Average unit cost** value is *91.67*.</span></span>
    - <span data-ttu-id="475a0-249">Les valeurs **Valeur disponible** et **Montant** de chaque période sont calculées à l’aide de la valeur **Coût unitaire moyen**.</span><span class="sxs-lookup"><span data-stu-id="475a0-249">The **On-hand value** value and the **Amount** value in each period bucket are calculated by using the **Average unit cost** value.</span></span>

- <span data-ttu-id="475a0-250">Le rapport détermine la quantité en stock pour chaque groupe de périodes en résumant la quantité totale des stocks reçus pour chaque groupe de période.</span><span class="sxs-lookup"><span data-stu-id="475a0-250">The report determines the on-hand quantity for each period bucket by summarizing the total received inventory quantity for each period bucket.</span></span> <span data-ttu-id="475a0-251">Il applique ensuite le principe du premier entré, premier sorti (FIFO) pour déduire la quantité totale délivrée, quel que soit le modèle de stock utilisé par les articles.</span><span class="sxs-lookup"><span data-stu-id="475a0-251">It then applies the first in, first out (FIFO) principle to deduct the total issued quantity, regardless of the inventory model that the items use.</span></span>

<span data-ttu-id="475a0-252">Si vous exécutez à nouveau le même rapport, mais cette fois, vous définissez à la fois les champs **Site** et **Entrepôt** sur *Afficher*, le nouveau rapport ressemblera à l’exemple suivant.</span><span class="sxs-lookup"><span data-stu-id="475a0-252">If you run the same report again, but this time you set both the **Site** and **Warehouse** fields to *View*, the new report will resemble the following example.</span></span>

<table>
<thead>
<tr>
    <th rowspan="2"><span data-ttu-id="475a0-253">numéro d’article</span><span class="sxs-lookup"><span data-stu-id="475a0-253">Item number</span></span></th>
    <th rowspan="2"><span data-ttu-id="475a0-254">Site</span><span class="sxs-lookup"><span data-stu-id="475a0-254">Site</span></span></th>
    <th rowspan="2"><span data-ttu-id="475a0-255">Entrepôt</span><span class="sxs-lookup"><span data-stu-id="475a0-255">Warehouse</span></span></th>
    <th rowspan="2"><span data-ttu-id="475a0-256">Quantité disponible</span><span class="sxs-lookup"><span data-stu-id="475a0-256">On-hand quantity</span></span></th>
    <th rowspan="2"><span data-ttu-id="475a0-257">Valeur disponible</span><span class="sxs-lookup"><span data-stu-id="475a0-257">On-hand value</span></span></th>
    <th rowspan="2"><span data-ttu-id="475a0-258">Quantité de valeur en stock</span><span class="sxs-lookup"><span data-stu-id="475a0-258">Inventory value quantity</span></span></th>
    <th rowspan="2"><span data-ttu-id="475a0-259">Valeur en stock</span><span class="sxs-lookup"><span data-stu-id="475a0-259">Inventory value</span></span></th>
    <th rowspan="2"><span data-ttu-id="475a0-260">Coût unitaire moyen</span><span class="sxs-lookup"><span data-stu-id="475a0-260">Average unit cost</span></span></th>
    <th colspan="2"><span data-ttu-id="475a0-261">08/05/2020 - 01/05/2020</span><span class="sxs-lookup"><span data-stu-id="475a0-261">5/8/2020 - 5/1/2020</span></span></th>
    <th colspan="2"><span data-ttu-id="475a0-262">30/04/2020 - 01/04/2020</span><span class="sxs-lookup"><span data-stu-id="475a0-262">4/30/2020 - 4/1/2020</span></span></th>
    <th colspan="2"><span data-ttu-id="475a0-263">31/03/2020 - 01/03/2020</span><span class="sxs-lookup"><span data-stu-id="475a0-263">3/31/2020 - 3/1/2020</span></span></th>
</tr>
<tr>
    <th><span data-ttu-id="475a0-264">P1:Quantité</span><span class="sxs-lookup"><span data-stu-id="475a0-264">P1:Quantity</span></span></th>
    <th><span data-ttu-id="475a0-265">P1:Montant</span><span class="sxs-lookup"><span data-stu-id="475a0-265">P1:Amount</span></span></th>
    <th><span data-ttu-id="475a0-266">P2:Quantité</span><span class="sxs-lookup"><span data-stu-id="475a0-266">P2:Quantity</span></span></th>
    <th><span data-ttu-id="475a0-267">P2:Montant</span><span class="sxs-lookup"><span data-stu-id="475a0-267">P2:Amount</span></span></th>
    <th><span data-ttu-id="475a0-268">P3:Quantité</span><span class="sxs-lookup"><span data-stu-id="475a0-268">P3:Quantity</span></span></th>
    <th><span data-ttu-id="475a0-269">P3:Montant</span><span class="sxs-lookup"><span data-stu-id="475a0-269">P3:Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
    <td><span data-ttu-id="475a0-270">1000</span><span class="sxs-lookup"><span data-stu-id="475a0-270">1000</span></span></td>
    <td><span data-ttu-id="475a0-271">1</span><span class="sxs-lookup"><span data-stu-id="475a0-271">1</span></span></td>
    <td><span data-ttu-id="475a0-272">11</span><span class="sxs-lookup"><span data-stu-id="475a0-272">11</span></span></td>
    <td><span data-ttu-id="475a0-273">10</span><span class="sxs-lookup"><span data-stu-id="475a0-273">10</span></span></td>
    <td><span data-ttu-id="475a0-274">916.67</span><span class="sxs-lookup"><span data-stu-id="475a0-274">916.67</span></span></td>
    <td><span data-ttu-id="475a0-275">14</span><span class="sxs-lookup"><span data-stu-id="475a0-275">14</span></span></td>
    <td><span data-ttu-id="475a0-276">1,283.33</span><span class="sxs-lookup"><span data-stu-id="475a0-276">1,283.33</span></span></td>
    <td><span data-ttu-id="475a0-277">91.67</span><span class="sxs-lookup"><span data-stu-id="475a0-277">91.67</span></span></td>
    <td></td>
    <td></td>
    <td><span data-ttu-id="475a0-278">5.00</span><span class="sxs-lookup"><span data-stu-id="475a0-278">5.00</span></span></td>
    <td><span data-ttu-id="475a0-279">458.33</span><span class="sxs-lookup"><span data-stu-id="475a0-279">458.33</span></span></td>
    <td><span data-ttu-id="475a0-280">5.00</span><span class="sxs-lookup"><span data-stu-id="475a0-280">5.00</span></span></td>
    <td><span data-ttu-id="475a0-281">458.33</span><span class="sxs-lookup"><span data-stu-id="475a0-281">458.33</span></span></td>
</tr>
<tr>
    <td><span data-ttu-id="475a0-282">1000</span><span class="sxs-lookup"><span data-stu-id="475a0-282">1000</span></span></td>
    <td><span data-ttu-id="475a0-283">1</span><span class="sxs-lookup"><span data-stu-id="475a0-283">1</span></span></td>
    <td><span data-ttu-id="475a0-284">12</span><span class="sxs-lookup"><span data-stu-id="475a0-284">12</span></span></td>
    <td><span data-ttu-id="475a0-285">4</span><span class="sxs-lookup"><span data-stu-id="475a0-285">4</span></span></td>
    <td><span data-ttu-id="475a0-286">366.67</span><span class="sxs-lookup"><span data-stu-id="475a0-286">366.67</span></span></td>
    <td><span data-ttu-id="475a0-287">14</span><span class="sxs-lookup"><span data-stu-id="475a0-287">14</span></span></td>
    <td><span data-ttu-id="475a0-288">1,283.33</span><span class="sxs-lookup"><span data-stu-id="475a0-288">1,283.33</span></span></td>
    <td><span data-ttu-id="475a0-289">91.67</span><span class="sxs-lookup"><span data-stu-id="475a0-289">91.67</span></span></td>
    <td><span data-ttu-id="475a0-290">4.00</span><span class="sxs-lookup"><span data-stu-id="475a0-290">4.00</span></span></td>
    <td><span data-ttu-id="475a0-291">366.67</span><span class="sxs-lookup"><span data-stu-id="475a0-291">366.67</span></span></td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
</tr>
<tr>
    <td><span data-ttu-id="475a0-292">1000</span><span class="sxs-lookup"><span data-stu-id="475a0-292">1000</span></span></td>
    <td><span data-ttu-id="475a0-293">2</span><span class="sxs-lookup"><span data-stu-id="475a0-293">2</span></span></td>
    <td></td>
    <td><span data-ttu-id="475a0-294">10</span><span class="sxs-lookup"><span data-stu-id="475a0-294">10</span></span></td>
    <td><span data-ttu-id="475a0-295">2,000.00</span><span class="sxs-lookup"><span data-stu-id="475a0-295">2,000.00</span></span></td>
    <td><span data-ttu-id="475a0-296">10</span><span class="sxs-lookup"><span data-stu-id="475a0-296">10</span></span></td>
    <td><span data-ttu-id="475a0-297">2,000.00</span><span class="sxs-lookup"><span data-stu-id="475a0-297">2,000.00</span></span></td>
    <td><span data-ttu-id="475a0-298">200.00</span><span class="sxs-lookup"><span data-stu-id="475a0-298">200.00</span></span></td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
    <td><span data-ttu-id="475a0-299">10.00</span><span class="sxs-lookup"><span data-stu-id="475a0-299">10.00</span></span></td>
    <td><span data-ttu-id="475a0-300">2,000.00</span><span class="sxs-lookup"><span data-stu-id="475a0-300">2,000.00</span></span></td>
</tr>
</tbody>
<tfoot>
<tr>
    <td><span data-ttu-id="475a0-301"><strong>Nombre total : 1000</strong></span><span class="sxs-lookup"><span data-stu-id="475a0-301"><strong>1000 Totals</strong></span></span></td>
    <td></td>
    <td></td>
    <td><span data-ttu-id="475a0-302"><strong>24.00</strong></span><span class="sxs-lookup"><span data-stu-id="475a0-302"><strong>24.00</strong></span></span></td>
    <td><span data-ttu-id="475a0-303"><strong>3,283.33</strong></span><span class="sxs-lookup"><span data-stu-id="475a0-303"><strong>3,283.33</strong></span></span></td>
    <td></td>
    <td></td>
    <td></td>
    <td><span data-ttu-id="475a0-304"><strong>4.00</strong></span><span class="sxs-lookup"><span data-stu-id="475a0-304"><strong>4.00</strong></span></span></td>
    <td><span data-ttu-id="475a0-305"><strong>366.67</strong></span><span class="sxs-lookup"><span data-stu-id="475a0-305"><strong>366.67</strong></span></span></td>
    <td><span data-ttu-id="475a0-306"><strong>5.00</strong></span><span class="sxs-lookup"><span data-stu-id="475a0-306"><strong>5.00</strong></span></span></td>
    <td><span data-ttu-id="475a0-307"><strong>458.33</strong></span><span class="sxs-lookup"><span data-stu-id="475a0-307"><strong>458.33</strong></span></span></td>
    <td><span data-ttu-id="475a0-308"><strong>15</strong></span><span class="sxs-lookup"><span data-stu-id="475a0-308"><strong>15</strong></span></span></td>
    <td><span data-ttu-id="475a0-309"><strong>2,458.33</strong></span><span class="sxs-lookup"><span data-stu-id="475a0-309"><strong>2,458.33</strong></span></span></td>
</tr>
</tfoot>
</table>

<span data-ttu-id="475a0-310">Cette fois, le site 1 est divisé en deux lignes, une pour l’entrepôt 11 et une pour l’entrepôt 12.</span><span class="sxs-lookup"><span data-stu-id="475a0-310">This time, site 1 is split into two rows, one for warehouse 11 and one for warehouse 12.</span></span> <span data-ttu-id="475a0-311">Cependant, les valeurs **Quantité de valeur du stock**, **Valeur du stock** et **Coût unitaire moyen** sont identiques, car **Entrepôt** n’est pas une dimension de stock financier.</span><span class="sxs-lookup"><span data-stu-id="475a0-311">However, the **Inventory value quantity**, **Inventory value**, and **Average unit cost** values are the same, because **Warehouse** isn't a financial inventory dimension.</span></span>

<span data-ttu-id="475a0-312">En outre, notez que la distribution des quantités du site 1 est différente.</span><span class="sxs-lookup"><span data-stu-id="475a0-312">Additionally, notice that the quantity distribution of site 1 is different.</span></span> <span data-ttu-id="475a0-313">Dans le premier rapport que vous avez exécuté, le système a ignoré l’ordre de transfert qui s’est produit sur le même site et a déduit la quantité de la facture de vente de la plage de périodes **31/03/2020 - 01/03/2020** dans le site 1.</span><span class="sxs-lookup"><span data-stu-id="475a0-313">In the first report that you ran, the system ignored the transfer order that occurred in the same site and deducted the quantity of the sales invoice from the **3/31/2020 - 3/1/2020** period bucket in site 1.</span></span> <span data-ttu-id="475a0-314">Cependant, dans le nouveau rapport, le système déduit la quantité de la facture de vente de la plage de périodes **08/05/2020 - 01/05/2020** dans l’entrepôt 12.</span><span class="sxs-lookup"><span data-stu-id="475a0-314">However, in the new report, the system deducts the quantity of the sales invoice from the **5/8/2020 - 5/1/2020** period bucket in warehouse 12.</span></span>

## <a name="effects-of-inventory-closing"></a><span data-ttu-id="475a0-315">Effets de la clôture des stocks</span><span class="sxs-lookup"><span data-stu-id="475a0-315">Effects of inventory closing</span></span>

<span data-ttu-id="475a0-316">Si vous exécutez la clôture des stocks pour mai, puis réexécutez le rapport précédent, mais que vous définissez le champ **À partir du** sur le *31 mai 2020*, vous remarquerez les résultats suivants :</span><span class="sxs-lookup"><span data-stu-id="475a0-316">If you run the inventory closing for May and then run the previous report again, but you set the **As of date** field to *May 31, 2020*, you will notice the following results:</span></span>

- <span data-ttu-id="475a0-317">Les valeurs **Valeur de stock** et **Coût unitaire moyen** sont mises à jour.</span><span class="sxs-lookup"><span data-stu-id="475a0-317">The **Inventory value** and **Average unit cost** values are updated.</span></span>
- <span data-ttu-id="475a0-318">La valeur **Valeur disponible** et toutes les valeurs **Montant** de chaque période sont mises à jour en conséquence.</span><span class="sxs-lookup"><span data-stu-id="475a0-318">The **On-hand value** value and all the **Amount** values in every period bucket are updated accordingly.</span></span>

<span data-ttu-id="475a0-319">Le nouveau rapport ressemblera à l’exemple ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="475a0-319">The new report will resemble the following example.</span></span>

<table>
<thead>
<tr>
    <th rowspan="2"><span data-ttu-id="475a0-320">numéro d’article</span><span class="sxs-lookup"><span data-stu-id="475a0-320">Item number</span></span></th>
    <th rowspan="2"><span data-ttu-id="475a0-321">Site</span><span class="sxs-lookup"><span data-stu-id="475a0-321">Site</span></span></th>
    <th rowspan="2"><span data-ttu-id="475a0-322">Entrepôt</span><span class="sxs-lookup"><span data-stu-id="475a0-322">Warehouse</span></span></th>
    <th rowspan="2"><span data-ttu-id="475a0-323">Quantité disponible</span><span class="sxs-lookup"><span data-stu-id="475a0-323">On-hand quantity</span></span></th>
    <th rowspan="2"><span data-ttu-id="475a0-324">Valeur disponible</span><span class="sxs-lookup"><span data-stu-id="475a0-324">On-hand value</span></span></th>
    <th rowspan="2"><span data-ttu-id="475a0-325">Quantité de valeur en stock</span><span class="sxs-lookup"><span data-stu-id="475a0-325">Inventory value quantity</span></span></th>
    <th rowspan="2"><span data-ttu-id="475a0-326">Valeur en stock</span><span class="sxs-lookup"><span data-stu-id="475a0-326">Inventory value</span></span></th>
    <th rowspan="2"><span data-ttu-id="475a0-327">Coût unitaire moyen</span><span class="sxs-lookup"><span data-stu-id="475a0-327">Average unit cost</span></span></th>
    <th colspan="2"><span data-ttu-id="475a0-328">31/05/2020 - 01/05/2020</span><span class="sxs-lookup"><span data-stu-id="475a0-328">5/31/2020 - 5/1/2020</span></span></th>
    <th colspan="2"><span data-ttu-id="475a0-329">30/04/2020 - 01/04/2020</span><span class="sxs-lookup"><span data-stu-id="475a0-329">4/30/2020 - 4/1/2020</span></span></th>
    <th colspan="2"><span data-ttu-id="475a0-330">31/03/2020 - 01/03/2020</span><span class="sxs-lookup"><span data-stu-id="475a0-330">3/31/2020 - 3/1/2020</span></span></th>
</tr>
<tr>
    <th><span data-ttu-id="475a0-331">P1:Quantité</span><span class="sxs-lookup"><span data-stu-id="475a0-331">P1:Quantity</span></span></th>
    <th><span data-ttu-id="475a0-332">P1:Montant</span><span class="sxs-lookup"><span data-stu-id="475a0-332">P1:Amount</span></span></th>
    <th><span data-ttu-id="475a0-333">P2:Quantité</span><span class="sxs-lookup"><span data-stu-id="475a0-333">P2:Quantity</span></span></th>
    <th><span data-ttu-id="475a0-334">P2:Montant</span><span class="sxs-lookup"><span data-stu-id="475a0-334">P2:Amount</span></span></th>
    <th><span data-ttu-id="475a0-335">P3:Quantité</span><span class="sxs-lookup"><span data-stu-id="475a0-335">P3:Quantity</span></span></th>
    <th><span data-ttu-id="475a0-336">P3:Montant</span><span class="sxs-lookup"><span data-stu-id="475a0-336">P3:Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
    <td><span data-ttu-id="475a0-337">1000</span><span class="sxs-lookup"><span data-stu-id="475a0-337">1000</span></span></td>
    <td><span data-ttu-id="475a0-338">1</span><span class="sxs-lookup"><span data-stu-id="475a0-338">1</span></span></td>
    <td><span data-ttu-id="475a0-339">11</span><span class="sxs-lookup"><span data-stu-id="475a0-339">11</span></span></td>
    <td><span data-ttu-id="475a0-340">10</span><span class="sxs-lookup"><span data-stu-id="475a0-340">10</span></span></td>
    <td><span data-ttu-id="475a0-341">910.70</span><span class="sxs-lookup"><span data-stu-id="475a0-341">910.70</span></span></td>
    <td><span data-ttu-id="475a0-342">14</span><span class="sxs-lookup"><span data-stu-id="475a0-342">14</span></span></td>
    <td><span data-ttu-id="475a0-343">1,275.00</span><span class="sxs-lookup"><span data-stu-id="475a0-343">1,275.00</span></span></td>
    <td><span data-ttu-id="475a0-344">91.07</span><span class="sxs-lookup"><span data-stu-id="475a0-344">91.07</span></span></td>
    <td><span data-ttu-id="475a0-345">0,00</span><span class="sxs-lookup"><span data-stu-id="475a0-345">0.00</span></span></td>
    <td></td>
    <td><span data-ttu-id="475a0-346">5.00</span><span class="sxs-lookup"><span data-stu-id="475a0-346">5.00</span></span></td>
    <td><span data-ttu-id="475a0-347">455.36</span><span class="sxs-lookup"><span data-stu-id="475a0-347">455.36</span></span></td>
    <td><span data-ttu-id="475a0-348">5.00</span><span class="sxs-lookup"><span data-stu-id="475a0-348">5.00</span></span></td>
    <td><span data-ttu-id="475a0-349">455.36</span><span class="sxs-lookup"><span data-stu-id="475a0-349">455.36</span></span></td>
</tr>
<tr>
    <td><span data-ttu-id="475a0-350">1000</span><span class="sxs-lookup"><span data-stu-id="475a0-350">1000</span></span></td>
    <td><span data-ttu-id="475a0-351">1</span><span class="sxs-lookup"><span data-stu-id="475a0-351">1</span></span></td>
    <td><span data-ttu-id="475a0-352">12</span><span class="sxs-lookup"><span data-stu-id="475a0-352">12</span></span></td>
    <td><span data-ttu-id="475a0-353">4</span><span class="sxs-lookup"><span data-stu-id="475a0-353">4</span></span></td>
    <td><span data-ttu-id="475a0-354">364.29</span><span class="sxs-lookup"><span data-stu-id="475a0-354">364.29</span></span></td>
    <td><span data-ttu-id="475a0-355">14</span><span class="sxs-lookup"><span data-stu-id="475a0-355">14</span></span></td>
    <td><span data-ttu-id="475a0-356">1,275.00</span><span class="sxs-lookup"><span data-stu-id="475a0-356">1,275.00</span></span></td>
    <td><span data-ttu-id="475a0-357">91.07</span><span class="sxs-lookup"><span data-stu-id="475a0-357">91.07</span></span></td>
    <td><span data-ttu-id="475a0-358">4.00</span><span class="sxs-lookup"><span data-stu-id="475a0-358">4.00</span></span></td>
    <td><span data-ttu-id="475a0-359">364.29</span><span class="sxs-lookup"><span data-stu-id="475a0-359">364.29</span></span></td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
</tr>
<tr>
    <td><span data-ttu-id="475a0-360">1000</span><span class="sxs-lookup"><span data-stu-id="475a0-360">1000</span></span></td>
    <td><span data-ttu-id="475a0-361">2</span><span class="sxs-lookup"><span data-stu-id="475a0-361">2</span></span></td>
    <td></td>
    <td><span data-ttu-id="475a0-362">10</span><span class="sxs-lookup"><span data-stu-id="475a0-362">10</span></span></td>
    <td><span data-ttu-id="475a0-363">2,000.00</span><span class="sxs-lookup"><span data-stu-id="475a0-363">2,000.00</span></span></td>
    <td><span data-ttu-id="475a0-364">10</span><span class="sxs-lookup"><span data-stu-id="475a0-364">10</span></span></td>
    <td><span data-ttu-id="475a0-365">2,000.00</span><span class="sxs-lookup"><span data-stu-id="475a0-365">2,000.00</span></span></td>
    <td><span data-ttu-id="475a0-366">200.00</span><span class="sxs-lookup"><span data-stu-id="475a0-366">200.00</span></span></td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
    <td><span data-ttu-id="475a0-367">10.00</span><span class="sxs-lookup"><span data-stu-id="475a0-367">10.00</span></span></td>
    <td><span data-ttu-id="475a0-368">2,000.00</span><span class="sxs-lookup"><span data-stu-id="475a0-368">2,000.00</span></span></td>
</tr>
</tbody>
<tfoot>
<tr>
    <td><span data-ttu-id="475a0-369"><strong>Nombre total : 1000</strong></span><span class="sxs-lookup"><span data-stu-id="475a0-369"><strong>1000 Totals</strong></span></span></td>
    <td></td>
    <td></td>
    <td><span data-ttu-id="475a0-370"><strong>24.00</strong></span><span class="sxs-lookup"><span data-stu-id="475a0-370"><strong>24.00</strong></span></span></td>
    <td><span data-ttu-id="475a0-371"><strong>3,275.00</strong></span><span class="sxs-lookup"><span data-stu-id="475a0-371"><strong>3,275.00</strong></span></span></td>
    <td></td>
    <td></td>
    <td></td>
    <td><span data-ttu-id="475a0-372"><strong>4.00</strong></span><span class="sxs-lookup"><span data-stu-id="475a0-372"><strong>4.00</strong></span></span></td>
    <td><span data-ttu-id="475a0-373"><strong>364.29</strong></span><span class="sxs-lookup"><span data-stu-id="475a0-373"><strong>364.29</strong></span></span></td>
    <td><span data-ttu-id="475a0-374"><strong>5.00</strong></span><span class="sxs-lookup"><span data-stu-id="475a0-374"><strong>5.00</strong></span></span></td>
    <td><span data-ttu-id="475a0-375"><strong>455.36</strong></span><span class="sxs-lookup"><span data-stu-id="475a0-375"><strong>455.36</strong></span></span></td>
    <td><span data-ttu-id="475a0-376"><strong>15</strong></span><span class="sxs-lookup"><span data-stu-id="475a0-376"><strong>15</strong></span></span></td>
    <td><span data-ttu-id="475a0-377"><strong>2,455.36</strong></span><span class="sxs-lookup"><span data-stu-id="475a0-377"><strong>2,455.36</strong></span></span></td>
</tr>
</tfoot>
</table>
