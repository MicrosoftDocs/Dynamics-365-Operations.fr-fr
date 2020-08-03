---
title: Exemples et logique du rapport de vieillissement des stocks
description: Cette rubrique présente quelques exemples qui montrent comment interpréter les résultats d'un rapport de vieillissement des stocks.
author: RichardLuan
manager: tfehr
ms.date: 5/29/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CostAdminWorkspace, CostAnalysisWorkspace
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
ms.openlocfilehash: cb7b7a055c26b53ee3acc3b872acf04fcf089eca
ms.sourcegitcommit: f64fce03ec52f844b05a9e8cac286cb201385002
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/16/2020
ms.locfileid: "3597238"
---
# <a name="inventory-aging-report-examples-and-logic"></a><span data-ttu-id="eb9f3-103">Exemples et logique du rapport de vieillissement des stocks</span><span class="sxs-lookup"><span data-stu-id="eb9f3-103">Inventory aging report examples and logic</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="eb9f3-104">Cette rubrique présente quelques exemples qui montrent comment interpréter les résultats d'un rapport sur le **vieillissement des stocks**.</span><span class="sxs-lookup"><span data-stu-id="eb9f3-104">This topic presents some examples that show how to interpret the results of an **Inventory aging** report.</span></span> <span data-ttu-id="eb9f3-105">Ce rapport classe les quantités en stock et les valeurs de stock pour un article ou un groupe d'articles sélectionné dans plusieurs plages de périodes.</span><span class="sxs-lookup"><span data-stu-id="eb9f3-105">This report categorizes on-hand quantity and inventory values for a selected item or item group into several period buckets.</span></span> <span data-ttu-id="eb9f3-106">Cette rubrique montre également la logique interne du rapport.</span><span class="sxs-lookup"><span data-stu-id="eb9f3-106">This topic also shows the internal logic of the report.</span></span>

<span data-ttu-id="eb9f3-107">Les exemples de cette rubrique montrent les résultats présentés dans un rapport **Vieillissement des stocks** standard.</span><span class="sxs-lookup"><span data-stu-id="eb9f3-107">The examples in this topic show results that are presented on a standard **Inventory aging** report.</span></span> <span data-ttu-id="eb9f3-108">Cependant, en général, nous vous recommandons d'utiliser la version de ce rapport [Stockage des rapports de vieillissement des stocks](inventory-aging-report-storage.md), en particulier lorsque de nombreux articles et entrepôts doivent être traités.</span><span class="sxs-lookup"><span data-stu-id="eb9f3-108">However, in general, we recommend that you use the [Inventory aging report storage](inventory-aging-report-storage.md) version of this report, especially when you have many items and warehouses that must be processed.</span></span> <span data-ttu-id="eb9f3-109">Le stockage des rapports de vieillissement des stocks enregistre chaque rapport que vous générez, affiche les résultats sous forme de page interactive et de graphique et vous permet d'exporter n'importe quel rapport enregistré.</span><span class="sxs-lookup"><span data-stu-id="eb9f3-109">Inventory aging report storage saves each report that you generate, shows the results as an interactive page and a chart, and lets you export any saved report.</span></span>

## <a name="sample-data-that-is-used-in-these-examples"></a><span data-ttu-id="eb9f3-110">Exemples de données utilisées</span><span class="sxs-lookup"><span data-stu-id="eb9f3-110">Sample data that is used in these examples</span></span>

<span data-ttu-id="eb9f3-111">Les exemples de cette rubrique sont basés sur les exemples de données de transaction de stock décrits dans cette section.</span><span class="sxs-lookup"><span data-stu-id="eb9f3-111">The examples in this topic are based on the sample inventory transaction data that is described in this section.</span></span>

### <a name="storage-dimension-setup"></a><span data-ttu-id="eb9f3-112">Configuration de la dimension de stockage</span><span class="sxs-lookup"><span data-stu-id="eb9f3-112">Storage dimension setup</span></span>

<span data-ttu-id="eb9f3-113">L'exemple de système contient la configuration suivante des dimensions de stockage.</span><span class="sxs-lookup"><span data-stu-id="eb9f3-113">The example system contains the following setup of storage dimensions.</span></span>

| <span data-ttu-id="eb9f3-114">Nom</span><span class="sxs-lookup"><span data-stu-id="eb9f3-114">Name</span></span>      | <span data-ttu-id="eb9f3-115">Actifs</span><span class="sxs-lookup"><span data-stu-id="eb9f3-115">Active</span></span> | <span data-ttu-id="eb9f3-116">Stock physique</span><span class="sxs-lookup"><span data-stu-id="eb9f3-116">Physical inventory</span></span> | <span data-ttu-id="eb9f3-117">Stock financier</span><span class="sxs-lookup"><span data-stu-id="eb9f3-117">Financial inventory</span></span> |
|-----------|--------|--------------------|---------------------|
| <span data-ttu-id="eb9f3-118">Site</span><span class="sxs-lookup"><span data-stu-id="eb9f3-118">Site</span></span>      | <span data-ttu-id="eb9f3-119">Oui</span><span class="sxs-lookup"><span data-stu-id="eb9f3-119">Yes</span></span>    | <span data-ttu-id="eb9f3-120">Oui</span><span class="sxs-lookup"><span data-stu-id="eb9f3-120">Yes</span></span>                | <span data-ttu-id="eb9f3-121">Oui</span><span class="sxs-lookup"><span data-stu-id="eb9f3-121">Yes</span></span>                 |
| <span data-ttu-id="eb9f3-122">Entrepôt</span><span class="sxs-lookup"><span data-stu-id="eb9f3-122">Warehouse</span></span> | <span data-ttu-id="eb9f3-123">Oui</span><span class="sxs-lookup"><span data-stu-id="eb9f3-123">Yes</span></span>    | <span data-ttu-id="eb9f3-124">Oui</span><span class="sxs-lookup"><span data-stu-id="eb9f3-124">Yes</span></span>                | <span data-ttu-id="eb9f3-125">N°</span><span class="sxs-lookup"><span data-stu-id="eb9f3-125">No</span></span>                  |

### <a name="inventory-model"></a><span data-ttu-id="eb9f3-126">Modèle de stock</span><span class="sxs-lookup"><span data-stu-id="eb9f3-126">Inventory model</span></span>

<span data-ttu-id="eb9f3-127">Pour l'exemple de système, le modèle de stock pour les produits lancés est *FIFO*, et le paramètre **Prix de revient** du modèle de stock est *Inclure une valeur physique*.</span><span class="sxs-lookup"><span data-stu-id="eb9f3-127">For the example system, the inventory model for the released products is *FIFO*, and the **Cost price** setting for the inventory model is *Include physical value*.</span></span>

### <a name="inventory-transactions"></a><span data-ttu-id="eb9f3-128">Mouvements de stock</span><span class="sxs-lookup"><span data-stu-id="eb9f3-128">Inventory transactions</span></span>

<span data-ttu-id="eb9f3-129">L'exemple de système contient les transactions de stock suivantes pour un produit lancé portant le numéro d'article *1000*.</span><span class="sxs-lookup"><span data-stu-id="eb9f3-129">The example system contains the following inventory transactions for a released product that has the item number *1000*.</span></span>

| <span data-ttu-id="eb9f3-130">Référence</span><span class="sxs-lookup"><span data-stu-id="eb9f3-130">Reference</span></span>      | <span data-ttu-id="eb9f3-131">Site</span><span class="sxs-lookup"><span data-stu-id="eb9f3-131">Site</span></span> | <span data-ttu-id="eb9f3-132">Entrepôt</span><span class="sxs-lookup"><span data-stu-id="eb9f3-132">Warehouse</span></span> | <span data-ttu-id="eb9f3-133">Reçu</span><span class="sxs-lookup"><span data-stu-id="eb9f3-133">Receipt</span></span>   | <span data-ttu-id="eb9f3-134">Sortie</span><span class="sxs-lookup"><span data-stu-id="eb9f3-134">Issue</span></span> | <span data-ttu-id="eb9f3-135">Date physique</span><span class="sxs-lookup"><span data-stu-id="eb9f3-135">Physical date</span></span> | <span data-ttu-id="eb9f3-136">Date financière</span><span class="sxs-lookup"><span data-stu-id="eb9f3-136">Financial date</span></span> | <span data-ttu-id="eb9f3-137">Quantité</span><span class="sxs-lookup"><span data-stu-id="eb9f3-137">Quantity</span></span> | <span data-ttu-id="eb9f3-138">Coût</span><span class="sxs-lookup"><span data-stu-id="eb9f3-138">Cost amount</span></span> | <span data-ttu-id="eb9f3-139">Montant du coût physique</span><span class="sxs-lookup"><span data-stu-id="eb9f3-139">Physical cost amount</span></span> |
|----------------|------|-----------|-----------|-------|---------------|----------------|----------|-------------|----------------------|
| <span data-ttu-id="eb9f3-140">Commande fournisseur</span><span class="sxs-lookup"><span data-stu-id="eb9f3-140">Purchase order</span></span> | <span data-ttu-id="eb9f3-141">1</span><span class="sxs-lookup"><span data-stu-id="eb9f3-141">1</span></span>    | <span data-ttu-id="eb9f3-142">11</span><span class="sxs-lookup"><span data-stu-id="eb9f3-142">11</span></span>        | <span data-ttu-id="eb9f3-143">Acheté</span><span class="sxs-lookup"><span data-stu-id="eb9f3-143">Purchased</span></span> |       | <span data-ttu-id="eb9f3-144">15 mars</span><span class="sxs-lookup"><span data-stu-id="eb9f3-144">March 15</span></span>      | <span data-ttu-id="eb9f3-145">15 mars</span><span class="sxs-lookup"><span data-stu-id="eb9f3-145">March 15</span></span>       | <span data-ttu-id="eb9f3-146">10</span><span class="sxs-lookup"><span data-stu-id="eb9f3-146">10</span></span>       | <span data-ttu-id="eb9f3-147">1 000</span><span class="sxs-lookup"><span data-stu-id="eb9f3-147">1,000</span></span>       | <span data-ttu-id="eb9f3-148">1 000</span><span class="sxs-lookup"><span data-stu-id="eb9f3-148">1,000</span></span>                |
| <span data-ttu-id="eb9f3-149">Commande fournisseur</span><span class="sxs-lookup"><span data-stu-id="eb9f3-149">Purchase order</span></span> | <span data-ttu-id="eb9f3-150">2</span><span class="sxs-lookup"><span data-stu-id="eb9f3-150">2</span></span>    | <span data-ttu-id="eb9f3-151">21</span><span class="sxs-lookup"><span data-stu-id="eb9f3-151">21</span></span>        | <span data-ttu-id="eb9f3-152">Acheté</span><span class="sxs-lookup"><span data-stu-id="eb9f3-152">Purchased</span></span> |       | <span data-ttu-id="eb9f3-153">15 mars</span><span class="sxs-lookup"><span data-stu-id="eb9f3-153">March 15</span></span>      | <span data-ttu-id="eb9f3-154">15 mars</span><span class="sxs-lookup"><span data-stu-id="eb9f3-154">March 15</span></span>       | <span data-ttu-id="eb9f3-155">10</span><span class="sxs-lookup"><span data-stu-id="eb9f3-155">10</span></span>       | <span data-ttu-id="eb9f3-156">2,000</span><span class="sxs-lookup"><span data-stu-id="eb9f3-156">2,000</span></span>       | <span data-ttu-id="eb9f3-157">2,000</span><span class="sxs-lookup"><span data-stu-id="eb9f3-157">2,000</span></span>                |
| <span data-ttu-id="eb9f3-158">Commande fournisseur</span><span class="sxs-lookup"><span data-stu-id="eb9f3-158">Purchase order</span></span> | <span data-ttu-id="eb9f3-159">1</span><span class="sxs-lookup"><span data-stu-id="eb9f3-159">1</span></span>    | <span data-ttu-id="eb9f3-160">11</span><span class="sxs-lookup"><span data-stu-id="eb9f3-160">11</span></span>        | <span data-ttu-id="eb9f3-161">Reçu(e)</span><span class="sxs-lookup"><span data-stu-id="eb9f3-161">Received</span></span>  |       | <span data-ttu-id="eb9f3-162">15 avril</span><span class="sxs-lookup"><span data-stu-id="eb9f3-162">April 15</span></span>      |                | <span data-ttu-id="eb9f3-163">5</span><span class="sxs-lookup"><span data-stu-id="eb9f3-163">5</span></span>        |             | <span data-ttu-id="eb9f3-164">375</span><span class="sxs-lookup"><span data-stu-id="eb9f3-164">375</span></span>                  |
| <span data-ttu-id="eb9f3-165">Ordre de transfert</span><span class="sxs-lookup"><span data-stu-id="eb9f3-165">Transfer order</span></span> | <span data-ttu-id="eb9f3-166">1</span><span class="sxs-lookup"><span data-stu-id="eb9f3-166">1</span></span>    | <span data-ttu-id="eb9f3-167">11</span><span class="sxs-lookup"><span data-stu-id="eb9f3-167">11</span></span>        |           | <span data-ttu-id="eb9f3-168">Vendu</span><span class="sxs-lookup"><span data-stu-id="eb9f3-168">Sold</span></span>  | <span data-ttu-id="eb9f3-169">mai 2</span><span class="sxs-lookup"><span data-stu-id="eb9f3-169">May 2</span></span>         | <span data-ttu-id="eb9f3-170">mai 2</span><span class="sxs-lookup"><span data-stu-id="eb9f3-170">May 2</span></span>          | <span data-ttu-id="eb9f3-171">-5</span><span class="sxs-lookup"><span data-stu-id="eb9f3-171">-5</span></span>       | <span data-ttu-id="eb9f3-172">-458,33</span><span class="sxs-lookup"><span data-stu-id="eb9f3-172">-458.33</span></span>     | <span data-ttu-id="eb9f3-173">-458,33</span><span class="sxs-lookup"><span data-stu-id="eb9f3-173">-458.33</span></span>              |
| <span data-ttu-id="eb9f3-174">Ordre de transfert</span><span class="sxs-lookup"><span data-stu-id="eb9f3-174">Transfer order</span></span> | <span data-ttu-id="eb9f3-175">1</span><span class="sxs-lookup"><span data-stu-id="eb9f3-175">1</span></span>    | <span data-ttu-id="eb9f3-176">12</span><span class="sxs-lookup"><span data-stu-id="eb9f3-176">12</span></span>        | <span data-ttu-id="eb9f3-177">Acheté</span><span class="sxs-lookup"><span data-stu-id="eb9f3-177">Purchased</span></span> |       | <span data-ttu-id="eb9f3-178">mai 2</span><span class="sxs-lookup"><span data-stu-id="eb9f3-178">May 2</span></span>         | <span data-ttu-id="eb9f3-179">mai 2</span><span class="sxs-lookup"><span data-stu-id="eb9f3-179">May 2</span></span>          | <span data-ttu-id="eb9f3-180">5</span><span class="sxs-lookup"><span data-stu-id="eb9f3-180">5</span></span>        | <span data-ttu-id="eb9f3-181">458.33</span><span class="sxs-lookup"><span data-stu-id="eb9f3-181">458.33</span></span>      | <span data-ttu-id="eb9f3-182">458.33</span><span class="sxs-lookup"><span data-stu-id="eb9f3-182">458.33</span></span>               |
| <span data-ttu-id="eb9f3-183">Commandes client</span><span class="sxs-lookup"><span data-stu-id="eb9f3-183">Sales order</span></span>    | <span data-ttu-id="eb9f3-184">1</span><span class="sxs-lookup"><span data-stu-id="eb9f3-184">1</span></span>    | <span data-ttu-id="eb9f3-185">12</span><span class="sxs-lookup"><span data-stu-id="eb9f3-185">12</span></span>        |           | <span data-ttu-id="eb9f3-186">Vendu</span><span class="sxs-lookup"><span data-stu-id="eb9f3-186">Sold</span></span>  | <span data-ttu-id="eb9f3-187">mai 3</span><span class="sxs-lookup"><span data-stu-id="eb9f3-187">May 3</span></span>         | <span data-ttu-id="eb9f3-188">mai 3</span><span class="sxs-lookup"><span data-stu-id="eb9f3-188">May 3</span></span>          | <span data-ttu-id="eb9f3-189">-1</span><span class="sxs-lookup"><span data-stu-id="eb9f3-189">-1</span></span>       | <span data-ttu-id="eb9f3-190">-91,67</span><span class="sxs-lookup"><span data-stu-id="eb9f3-190">-91.67</span></span>      | <span data-ttu-id="eb9f3-191">-91,67</span><span class="sxs-lookup"><span data-stu-id="eb9f3-191">-91.67</span></span>               |

## <a name="how-quantities-and-amounts-in-each-period-bucket-are-calculated"></a><span data-ttu-id="eb9f3-192">Comment les quantités et les montants de chaque période sont calculés</span><span class="sxs-lookup"><span data-stu-id="eb9f3-192">How quantities and amounts in each period bucket are calculated</span></span>

<span data-ttu-id="eb9f3-193">En utilisant les exemples de données décrits dans les sections précédentes, vous pouvez exécuter un rapport **Vieillissement des stocks** contenant les paramètres suivants :</span><span class="sxs-lookup"><span data-stu-id="eb9f3-193">By using the sample data that is described in the previous sections, you can run an **Inventory aging** report that has the following settings:</span></span>

- <span data-ttu-id="eb9f3-194">**À ce jour :** *9 mai 2020*</span><span class="sxs-lookup"><span data-stu-id="eb9f3-194">**As of date:** *May 9, 2020*</span></span>
- <span data-ttu-id="eb9f3-195">**Site :** *Vue*</span><span class="sxs-lookup"><span data-stu-id="eb9f3-195">**Site:** *View*</span></span>
- <span data-ttu-id="eb9f3-196">**Entrepôt :** *Non*</span><span class="sxs-lookup"><span data-stu-id="eb9f3-196">**Warehouse:** *No*</span></span>
- <span data-ttu-id="eb9f3-197">**Numéro d'article :** *Total*</span><span class="sxs-lookup"><span data-stu-id="eb9f3-197">**Item number:** *Total*</span></span>
- <span data-ttu-id="eb9f3-198">**Période de vieillissement :** Définissez ce champ pour générer des compartiments mensuels.</span><span class="sxs-lookup"><span data-stu-id="eb9f3-198">**Aging period:** Set this field to generate monthly buckets.</span></span>

<span data-ttu-id="eb9f3-199">Dans ce cas, le contenu du rapport généré ressemblera à l'exemple suivant.</span><span class="sxs-lookup"><span data-stu-id="eb9f3-199">In this case, the content of the report that is generated will resemble the following example.</span></span>

<table>
<thead>
<tr>
    <th rowspan="2"><span data-ttu-id="eb9f3-200">numéro d'article</span><span class="sxs-lookup"><span data-stu-id="eb9f3-200">Item number</span></span></th>
    <th rowspan="2"><span data-ttu-id="eb9f3-201">Site</span><span class="sxs-lookup"><span data-stu-id="eb9f3-201">Site</span></span></th>
    <th rowspan="2"><span data-ttu-id="eb9f3-202">Quantité disponible</span><span class="sxs-lookup"><span data-stu-id="eb9f3-202">On-hand quantity</span></span></th>
    <th rowspan="2"><span data-ttu-id="eb9f3-203">Valeur disponible</span><span class="sxs-lookup"><span data-stu-id="eb9f3-203">On-hand value</span></span></th>
    <th rowspan="2"><span data-ttu-id="eb9f3-204">Quantité de valeur en stock</span><span class="sxs-lookup"><span data-stu-id="eb9f3-204">Inventory value quantity</span></span></th>
    <th rowspan="2"><span data-ttu-id="eb9f3-205">Valeur en stock</span><span class="sxs-lookup"><span data-stu-id="eb9f3-205">Inventory value</span></span></th>
    <th rowspan="2"><span data-ttu-id="eb9f3-206">Coût unitaire moyen</span><span class="sxs-lookup"><span data-stu-id="eb9f3-206">Average unit cost</span></span></th>
    <th colspan="2"><span data-ttu-id="eb9f3-207">08/05/2020 - 01/05/2020</span><span class="sxs-lookup"><span data-stu-id="eb9f3-207">5/8/2020 - 5/1/2020</span></span></th>
    <th colspan="2"><span data-ttu-id="eb9f3-208">30/04/2020 - 01/04/2020</span><span class="sxs-lookup"><span data-stu-id="eb9f3-208">4/30/2020 - 4/1/2020</span></span></th>
    <th colspan="2"><span data-ttu-id="eb9f3-209">31/03/2020 - 01/03/2020</span><span class="sxs-lookup"><span data-stu-id="eb9f3-209">3/31/2020 - 3/1/2020</span></span></th>
</tr>
<tr>
    <th><span data-ttu-id="eb9f3-210">P1:Quantité</span><span class="sxs-lookup"><span data-stu-id="eb9f3-210">P1:Quantity</span></span></th>
    <th><span data-ttu-id="eb9f3-211">P1:Montant</span><span class="sxs-lookup"><span data-stu-id="eb9f3-211">P1:Amount</span></span></th>
    <th><span data-ttu-id="eb9f3-212">P2:Quantité</span><span class="sxs-lookup"><span data-stu-id="eb9f3-212">P2:Quantity</span></span></th>
    <th><span data-ttu-id="eb9f3-213">P2:Montant</span><span class="sxs-lookup"><span data-stu-id="eb9f3-213">P2:Amount</span></span></th>
    <th><span data-ttu-id="eb9f3-214">P3:Quantité</span><span class="sxs-lookup"><span data-stu-id="eb9f3-214">P3:Quantity</span></span></th>
    <th><span data-ttu-id="eb9f3-215">P3:Montant</span><span class="sxs-lookup"><span data-stu-id="eb9f3-215">P3:Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
    <td><span data-ttu-id="eb9f3-216">1000</span><span class="sxs-lookup"><span data-stu-id="eb9f3-216">1000</span></span></td>
    <td><span data-ttu-id="eb9f3-217">1</span><span class="sxs-lookup"><span data-stu-id="eb9f3-217">1</span></span></td>
    <td><span data-ttu-id="eb9f3-218">14</span><span class="sxs-lookup"><span data-stu-id="eb9f3-218">14</span></span></td>
    <td><span data-ttu-id="eb9f3-219">1,283.33</span><span class="sxs-lookup"><span data-stu-id="eb9f3-219">1,283.33</span></span></td>
    <td><span data-ttu-id="eb9f3-220">14</span><span class="sxs-lookup"><span data-stu-id="eb9f3-220">14</span></span></td>
    <td><span data-ttu-id="eb9f3-221">1,283.33</span><span class="sxs-lookup"><span data-stu-id="eb9f3-221">1,283.33</span></span></td>
    <td><span data-ttu-id="eb9f3-222">91.67</span><span class="sxs-lookup"><span data-stu-id="eb9f3-222">91.67</span></span></td>
    <td></td>
    <td></td>
    <td><span data-ttu-id="eb9f3-223">5.00</span><span class="sxs-lookup"><span data-stu-id="eb9f3-223">5.00</span></span></td>
    <td><span data-ttu-id="eb9f3-224">458.33</span><span class="sxs-lookup"><span data-stu-id="eb9f3-224">458.33</span></span></td>
    <td><span data-ttu-id="eb9f3-225">9.00</span><span class="sxs-lookup"><span data-stu-id="eb9f3-225">9.00</span></span></td>
    <td><span data-ttu-id="eb9f3-226">825.00</span><span class="sxs-lookup"><span data-stu-id="eb9f3-226">825.00</span></span></td>
</tr>
<tr>
    <td><span data-ttu-id="eb9f3-227">1000</span><span class="sxs-lookup"><span data-stu-id="eb9f3-227">1000</span></span></td>
    <td><span data-ttu-id="eb9f3-228">2</span><span class="sxs-lookup"><span data-stu-id="eb9f3-228">2</span></span></td>
    <td><span data-ttu-id="eb9f3-229">10</span><span class="sxs-lookup"><span data-stu-id="eb9f3-229">10</span></span></td>
    <td><span data-ttu-id="eb9f3-230">2,000.00</span><span class="sxs-lookup"><span data-stu-id="eb9f3-230">2,000.00</span></span></td>
    <td><span data-ttu-id="eb9f3-231">10</span><span class="sxs-lookup"><span data-stu-id="eb9f3-231">10</span></span></td>
    <td><span data-ttu-id="eb9f3-232">2,000.00</span><span class="sxs-lookup"><span data-stu-id="eb9f3-232">2,000.00</span></span></td>
    <td><span data-ttu-id="eb9f3-233">200.00</span><span class="sxs-lookup"><span data-stu-id="eb9f3-233">200.00</span></span></td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
    <td><span data-ttu-id="eb9f3-234">10.00</span><span class="sxs-lookup"><span data-stu-id="eb9f3-234">10.00</span></span></td>
    <td><span data-ttu-id="eb9f3-235">2,000.00</span><span class="sxs-lookup"><span data-stu-id="eb9f3-235">2,000.00</span></span></td>
</tr>
</tbody>
<tfoot>
<tr>
    <td><span data-ttu-id="eb9f3-236"><strong>Nombre total : 1000</strong></span><span class="sxs-lookup"><span data-stu-id="eb9f3-236"><strong>1000 Totals</strong></span></span></td>
    <td></td>
    <td><span data-ttu-id="eb9f3-237"><strong>24.00</strong></span><span class="sxs-lookup"><span data-stu-id="eb9f3-237"><strong>24.00</strong></span></span></td>
    <td><span data-ttu-id="eb9f3-238"><strong>3,283.33</strong></span><span class="sxs-lookup"><span data-stu-id="eb9f3-238"><strong>3,283.33</strong></span></span></td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
    <td><span data-ttu-id="eb9f3-239"><strong>5.00</strong></span><span class="sxs-lookup"><span data-stu-id="eb9f3-239"><strong>5.00</strong></span></span></td>
    <td><span data-ttu-id="eb9f3-240"><strong>458.33</strong></span><span class="sxs-lookup"><span data-stu-id="eb9f3-240"><strong>458.33</strong></span></span></td>
    <td><span data-ttu-id="eb9f3-241"><strong>19</strong></span><span class="sxs-lookup"><span data-stu-id="eb9f3-241"><strong>19</strong></span></span></td>
    <td><span data-ttu-id="eb9f3-242"><strong>2,825.00</strong></span><span class="sxs-lookup"><span data-stu-id="eb9f3-242"><strong>2,825.00</strong></span></span></td>
</tr>
</tfoot>
</table>

<span data-ttu-id="eb9f3-243">Notez les détails suivants dans cet exemple de rapport :</span><span class="sxs-lookup"><span data-stu-id="eb9f3-243">Note the following details in this example report:</span></span>

- <span data-ttu-id="eb9f3-244">Les valeurs **Quantité de valeur du stock**, **Valeur du stock** et **Coût unitaire moyen** indiquées dans le rapport sont des valeurs pour la dimension de stock financier (**Site**, dans ce cas).</span><span class="sxs-lookup"><span data-stu-id="eb9f3-244">The **Inventory value quantity**, **Inventory value**, and **Average unit cost** values that are shown on the report are values for the financial inventory dimension (**Site**, in this case).</span></span>

    <span data-ttu-id="eb9f3-245">Par exemple, pour le site 1, le rapport affiche les informations suivantes :</span><span class="sxs-lookup"><span data-stu-id="eb9f3-245">For example, for site 1, the report shows the following information:</span></span>

    - <span data-ttu-id="eb9f3-246">La valeur **Quantité de valeur du stock** est *14* (= 10 + 5 – 5 + 5 – 1).</span><span class="sxs-lookup"><span data-stu-id="eb9f3-246">The **Inventory value quantity** value is *14* (= 10 + 5 – 5 + 5 – 1).</span></span>
    - <span data-ttu-id="eb9f3-247">La valeur **Quantité du stock** est *1 283,33* (= 1 000 + 375 – 458,33 + 458,33 – 91,67).</span><span class="sxs-lookup"><span data-stu-id="eb9f3-247">The **Inventory value** value is *1,283.33* (= 1,000 + 375 – 458.33 + 458.33 – 91.67).</span></span>
    - <span data-ttu-id="eb9f3-248">La valeur du **Coût unitaire moyen** est *91,67*.</span><span class="sxs-lookup"><span data-stu-id="eb9f3-248">The **Average unit cost** value is *91.67*.</span></span>
    - <span data-ttu-id="eb9f3-249">Les valeurs **Valeur disponible** et **Montant** de chaque période sont calculées à l'aide de la valeur **Coût unitaire moyen**.</span><span class="sxs-lookup"><span data-stu-id="eb9f3-249">The **On-hand value** value and the **Amount** value in each period bucket are calculated by using the **Average unit cost** value.</span></span>

- <span data-ttu-id="eb9f3-250">Le rapport détermine la quantité en stock pour chaque groupe de périodes en résumant la quantité totale des stocks reçus pour chaque groupe de période.</span><span class="sxs-lookup"><span data-stu-id="eb9f3-250">The report determines the on-hand quantity for each period bucket by summarizing the total received inventory quantity for each period bucket.</span></span> <span data-ttu-id="eb9f3-251">Il applique ensuite le principe du premier entré, premier sorti (FIFO) pour déduire la quantité totale délivrée, quel que soit le modèle de stock utilisé par les articles.</span><span class="sxs-lookup"><span data-stu-id="eb9f3-251">It then applies the first in, first out (FIFO) principle to deduct the total issued quantity, regardless of the inventory model that the items use.</span></span>

<span data-ttu-id="eb9f3-252">Si vous exécutez à nouveau le même rapport, mais cette fois, vous définissez à la fois les champs **Site** et **Entrepôt** sur *Afficher*, le nouveau rapport ressemblera à l'exemple suivant.</span><span class="sxs-lookup"><span data-stu-id="eb9f3-252">If you run the same report again, but this time you set both the **Site** and **Warehouse** fields to *View*, the new report will resemble the following example.</span></span>

<table>
<thead>
<tr>
    <th rowspan="2"><span data-ttu-id="eb9f3-253">numéro d'article</span><span class="sxs-lookup"><span data-stu-id="eb9f3-253">Item number</span></span></th>
    <th rowspan="2"><span data-ttu-id="eb9f3-254">Site</span><span class="sxs-lookup"><span data-stu-id="eb9f3-254">Site</span></span></th>
    <th rowspan="2"><span data-ttu-id="eb9f3-255">Entrepôt</span><span class="sxs-lookup"><span data-stu-id="eb9f3-255">Warehouse</span></span></th>
    <th rowspan="2"><span data-ttu-id="eb9f3-256">Quantité disponible</span><span class="sxs-lookup"><span data-stu-id="eb9f3-256">On-hand quantity</span></span></th>
    <th rowspan="2"><span data-ttu-id="eb9f3-257">Valeur disponible</span><span class="sxs-lookup"><span data-stu-id="eb9f3-257">On-hand value</span></span></th>
    <th rowspan="2"><span data-ttu-id="eb9f3-258">Quantité de valeur en stock</span><span class="sxs-lookup"><span data-stu-id="eb9f3-258">Inventory value quantity</span></span></th>
    <th rowspan="2"><span data-ttu-id="eb9f3-259">Valeur en stock</span><span class="sxs-lookup"><span data-stu-id="eb9f3-259">Inventory value</span></span></th>
    <th rowspan="2"><span data-ttu-id="eb9f3-260">Coût unitaire moyen</span><span class="sxs-lookup"><span data-stu-id="eb9f3-260">Average unit cost</span></span></th>
    <th colspan="2"><span data-ttu-id="eb9f3-261">08/05/2020 - 01/05/2020</span><span class="sxs-lookup"><span data-stu-id="eb9f3-261">5/8/2020 - 5/1/2020</span></span></th>
    <th colspan="2"><span data-ttu-id="eb9f3-262">30/04/2020 - 01/04/2020</span><span class="sxs-lookup"><span data-stu-id="eb9f3-262">4/30/2020 - 4/1/2020</span></span></th>
    <th colspan="2"><span data-ttu-id="eb9f3-263">31/03/2020 - 01/03/2020</span><span class="sxs-lookup"><span data-stu-id="eb9f3-263">3/31/2020 - 3/1/2020</span></span></th>
</tr>
<tr>
    <th><span data-ttu-id="eb9f3-264">P1:Quantité</span><span class="sxs-lookup"><span data-stu-id="eb9f3-264">P1:Quantity</span></span></th>
    <th><span data-ttu-id="eb9f3-265">P1:Montant</span><span class="sxs-lookup"><span data-stu-id="eb9f3-265">P1:Amount</span></span></th>
    <th><span data-ttu-id="eb9f3-266">P2:Quantité</span><span class="sxs-lookup"><span data-stu-id="eb9f3-266">P2:Quantity</span></span></th>
    <th><span data-ttu-id="eb9f3-267">P2:Montant</span><span class="sxs-lookup"><span data-stu-id="eb9f3-267">P2:Amount</span></span></th>
    <th><span data-ttu-id="eb9f3-268">P3:Quantité</span><span class="sxs-lookup"><span data-stu-id="eb9f3-268">P3:Quantity</span></span></th>
    <th><span data-ttu-id="eb9f3-269">P3:Montant</span><span class="sxs-lookup"><span data-stu-id="eb9f3-269">P3:Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
    <td><span data-ttu-id="eb9f3-270">1000</span><span class="sxs-lookup"><span data-stu-id="eb9f3-270">1000</span></span></td>
    <td><span data-ttu-id="eb9f3-271">1</span><span class="sxs-lookup"><span data-stu-id="eb9f3-271">1</span></span></td>
    <td><span data-ttu-id="eb9f3-272">11</span><span class="sxs-lookup"><span data-stu-id="eb9f3-272">11</span></span></td>
    <td><span data-ttu-id="eb9f3-273">10</span><span class="sxs-lookup"><span data-stu-id="eb9f3-273">10</span></span></td>
    <td><span data-ttu-id="eb9f3-274">916.67</span><span class="sxs-lookup"><span data-stu-id="eb9f3-274">916.67</span></span></td>
    <td><span data-ttu-id="eb9f3-275">14</span><span class="sxs-lookup"><span data-stu-id="eb9f3-275">14</span></span></td>
    <td><span data-ttu-id="eb9f3-276">1,283.33</span><span class="sxs-lookup"><span data-stu-id="eb9f3-276">1,283.33</span></span></td>
    <td><span data-ttu-id="eb9f3-277">91.67</span><span class="sxs-lookup"><span data-stu-id="eb9f3-277">91.67</span></span></td>
    <td></td>
    <td></td>
    <td><span data-ttu-id="eb9f3-278">5.00</span><span class="sxs-lookup"><span data-stu-id="eb9f3-278">5.00</span></span></td>
    <td><span data-ttu-id="eb9f3-279">458.33</span><span class="sxs-lookup"><span data-stu-id="eb9f3-279">458.33</span></span></td>
    <td><span data-ttu-id="eb9f3-280">5.00</span><span class="sxs-lookup"><span data-stu-id="eb9f3-280">5.00</span></span></td>
    <td><span data-ttu-id="eb9f3-281">458.33</span><span class="sxs-lookup"><span data-stu-id="eb9f3-281">458.33</span></span></td>
</tr>
<tr>
    <td><span data-ttu-id="eb9f3-282">1000</span><span class="sxs-lookup"><span data-stu-id="eb9f3-282">1000</span></span></td>
    <td><span data-ttu-id="eb9f3-283">1</span><span class="sxs-lookup"><span data-stu-id="eb9f3-283">1</span></span></td>
    <td><span data-ttu-id="eb9f3-284">12</span><span class="sxs-lookup"><span data-stu-id="eb9f3-284">12</span></span></td>
    <td><span data-ttu-id="eb9f3-285">4</span><span class="sxs-lookup"><span data-stu-id="eb9f3-285">4</span></span></td>
    <td><span data-ttu-id="eb9f3-286">366.67</span><span class="sxs-lookup"><span data-stu-id="eb9f3-286">366.67</span></span></td>
    <td><span data-ttu-id="eb9f3-287">14</span><span class="sxs-lookup"><span data-stu-id="eb9f3-287">14</span></span></td>
    <td><span data-ttu-id="eb9f3-288">1,283.33</span><span class="sxs-lookup"><span data-stu-id="eb9f3-288">1,283.33</span></span></td>
    <td><span data-ttu-id="eb9f3-289">91.67</span><span class="sxs-lookup"><span data-stu-id="eb9f3-289">91.67</span></span></td>
    <td><span data-ttu-id="eb9f3-290">4.00</span><span class="sxs-lookup"><span data-stu-id="eb9f3-290">4.00</span></span></td>
    <td><span data-ttu-id="eb9f3-291">366.67</span><span class="sxs-lookup"><span data-stu-id="eb9f3-291">366.67</span></span></td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
</tr>
<tr>
    <td><span data-ttu-id="eb9f3-292">1000</span><span class="sxs-lookup"><span data-stu-id="eb9f3-292">1000</span></span></td>
    <td><span data-ttu-id="eb9f3-293">2</span><span class="sxs-lookup"><span data-stu-id="eb9f3-293">2</span></span></td>
    <td></td>
    <td><span data-ttu-id="eb9f3-294">10</span><span class="sxs-lookup"><span data-stu-id="eb9f3-294">10</span></span></td>
    <td><span data-ttu-id="eb9f3-295">2,000.00</span><span class="sxs-lookup"><span data-stu-id="eb9f3-295">2,000.00</span></span></td>
    <td><span data-ttu-id="eb9f3-296">10</span><span class="sxs-lookup"><span data-stu-id="eb9f3-296">10</span></span></td>
    <td><span data-ttu-id="eb9f3-297">2,000.00</span><span class="sxs-lookup"><span data-stu-id="eb9f3-297">2,000.00</span></span></td>
    <td><span data-ttu-id="eb9f3-298">200.00</span><span class="sxs-lookup"><span data-stu-id="eb9f3-298">200.00</span></span></td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
    <td><span data-ttu-id="eb9f3-299">10.00</span><span class="sxs-lookup"><span data-stu-id="eb9f3-299">10.00</span></span></td>
    <td><span data-ttu-id="eb9f3-300">2,000.00</span><span class="sxs-lookup"><span data-stu-id="eb9f3-300">2,000.00</span></span></td>
</tr>
</tbody>
<tfoot>
<tr>
    <td><span data-ttu-id="eb9f3-301"><strong>Nombre total : 1000</strong></span><span class="sxs-lookup"><span data-stu-id="eb9f3-301"><strong>1000 Totals</strong></span></span></td>
    <td></td>
    <td></td>
    <td><span data-ttu-id="eb9f3-302"><strong>24.00</strong></span><span class="sxs-lookup"><span data-stu-id="eb9f3-302"><strong>24.00</strong></span></span></td>
    <td><span data-ttu-id="eb9f3-303"><strong>3,283.33</strong></span><span class="sxs-lookup"><span data-stu-id="eb9f3-303"><strong>3,283.33</strong></span></span></td>
    <td></td>
    <td></td>
    <td></td>
    <td><span data-ttu-id="eb9f3-304"><strong>4.00</strong></span><span class="sxs-lookup"><span data-stu-id="eb9f3-304"><strong>4.00</strong></span></span></td>
    <td><span data-ttu-id="eb9f3-305"><strong>366.67</strong></span><span class="sxs-lookup"><span data-stu-id="eb9f3-305"><strong>366.67</strong></span></span></td>
    <td><span data-ttu-id="eb9f3-306"><strong>5.00</strong></span><span class="sxs-lookup"><span data-stu-id="eb9f3-306"><strong>5.00</strong></span></span></td>
    <td><span data-ttu-id="eb9f3-307"><strong>458.33</strong></span><span class="sxs-lookup"><span data-stu-id="eb9f3-307"><strong>458.33</strong></span></span></td>
    <td><span data-ttu-id="eb9f3-308"><strong>15</strong></span><span class="sxs-lookup"><span data-stu-id="eb9f3-308"><strong>15</strong></span></span></td>
    <td><span data-ttu-id="eb9f3-309"><strong>2,458.33</strong></span><span class="sxs-lookup"><span data-stu-id="eb9f3-309"><strong>2,458.33</strong></span></span></td>
</tr>
</tfoot>
</table>

<span data-ttu-id="eb9f3-310">Cette fois, le site 1 est divisé en deux lignes, une pour l'entrepôt 11 et une pour l'entrepôt 12.</span><span class="sxs-lookup"><span data-stu-id="eb9f3-310">This time, site 1 is split into two rows, one for warehouse 11 and one for warehouse 12.</span></span> <span data-ttu-id="eb9f3-311">Cependant, les valeurs **Quantité de valeur du stock**, **Valeur du stock** et **Coût unitaire moyen** sont identiques, car **Entrepôt** n'est pas une dimension de stock financier.</span><span class="sxs-lookup"><span data-stu-id="eb9f3-311">However, the **Inventory value quantity**, **Inventory value**, and **Average unit cost** values are the same, because **Warehouse** isn't a financial inventory dimension.</span></span>

<span data-ttu-id="eb9f3-312">En outre, notez que la distribution des quantités du site 1 est différente.</span><span class="sxs-lookup"><span data-stu-id="eb9f3-312">Additionally, notice that the quantity distribution of site 1 is different.</span></span> <span data-ttu-id="eb9f3-313">Dans le premier rapport que vous avez exécuté, le système a ignoré l'ordre de transfert qui s'est produit sur le même site et a déduit la quantité de la facture de vente de la plage de périodes **31/03/2020 - 01/03/2020** dans le site 1.</span><span class="sxs-lookup"><span data-stu-id="eb9f3-313">In the first report that you ran, the system ignored the transfer order that occurred in the same site and deducted the quantity of the sales invoice from the **3/31/2020 - 3/1/2020** period bucket in site 1.</span></span> <span data-ttu-id="eb9f3-314">Cependant, dans le nouveau rapport, le système déduit la quantité de la facture de vente de la plage de périodes **08/05/2020 - 01/05/2020** dans l'entrepôt 12.</span><span class="sxs-lookup"><span data-stu-id="eb9f3-314">However, in the new report, the system deducts the quantity of the sales invoice from the **5/8/2020 - 5/1/2020** period bucket in warehouse 12.</span></span>

## <a name="effects-of-inventory-closing"></a><span data-ttu-id="eb9f3-315">Effets de la clôture des stocks</span><span class="sxs-lookup"><span data-stu-id="eb9f3-315">Effects of inventory closing</span></span>

<span data-ttu-id="eb9f3-316">Si vous exécutez la clôture des stocks pour mai, puis réexécutez le rapport précédent, mais que vous définissez le champ **À partir du** sur le *31 mai 2020*, vous remarquerez les résultats suivants :</span><span class="sxs-lookup"><span data-stu-id="eb9f3-316">If you run the inventory closing for May and then run the previous report again, but you set the **As of date** field to *May 31, 2020*, you will notice the following results:</span></span>

- <span data-ttu-id="eb9f3-317">Les valeurs **Valeur de stock** et **Coût unitaire moyen** sont mises à jour.</span><span class="sxs-lookup"><span data-stu-id="eb9f3-317">The **Inventory value** and **Average unit cost** values are updated.</span></span>
- <span data-ttu-id="eb9f3-318">La valeur **Valeur disponible** et toutes les valeurs **Montant** de chaque période sont mises à jour en conséquence.</span><span class="sxs-lookup"><span data-stu-id="eb9f3-318">The **On-hand value** value and all the **Amount** values in every period bucket are updated accordingly.</span></span>

<span data-ttu-id="eb9f3-319">Le nouveau rapport ressemblera à l'exemple ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="eb9f3-319">The new report will resemble the following example.</span></span>

<table>
<thead>
<tr>
    <th rowspan="2"><span data-ttu-id="eb9f3-320">numéro d'article</span><span class="sxs-lookup"><span data-stu-id="eb9f3-320">Item number</span></span></th>
    <th rowspan="2"><span data-ttu-id="eb9f3-321">Site</span><span class="sxs-lookup"><span data-stu-id="eb9f3-321">Site</span></span></th>
    <th rowspan="2"><span data-ttu-id="eb9f3-322">Entrepôt</span><span class="sxs-lookup"><span data-stu-id="eb9f3-322">Warehouse</span></span></th>
    <th rowspan="2"><span data-ttu-id="eb9f3-323">Quantité disponible</span><span class="sxs-lookup"><span data-stu-id="eb9f3-323">On-hand quantity</span></span></th>
    <th rowspan="2"><span data-ttu-id="eb9f3-324">Valeur disponible</span><span class="sxs-lookup"><span data-stu-id="eb9f3-324">On-hand value</span></span></th>
    <th rowspan="2"><span data-ttu-id="eb9f3-325">Quantité de valeur en stock</span><span class="sxs-lookup"><span data-stu-id="eb9f3-325">Inventory value quantity</span></span></th>
    <th rowspan="2"><span data-ttu-id="eb9f3-326">Valeur en stock</span><span class="sxs-lookup"><span data-stu-id="eb9f3-326">Inventory value</span></span></th>
    <th rowspan="2"><span data-ttu-id="eb9f3-327">Coût unitaire moyen</span><span class="sxs-lookup"><span data-stu-id="eb9f3-327">Average unit cost</span></span></th>
    <th colspan="2"><span data-ttu-id="eb9f3-328">31/05/2020 - 01/05/2020</span><span class="sxs-lookup"><span data-stu-id="eb9f3-328">5/31/2020 - 5/1/2020</span></span></th>
    <th colspan="2"><span data-ttu-id="eb9f3-329">30/04/2020 - 01/04/2020</span><span class="sxs-lookup"><span data-stu-id="eb9f3-329">4/30/2020 - 4/1/2020</span></span></th>
    <th colspan="2"><span data-ttu-id="eb9f3-330">31/03/2020 - 01/03/2020</span><span class="sxs-lookup"><span data-stu-id="eb9f3-330">3/31/2020 - 3/1/2020</span></span></th>
</tr>
<tr>
    <th><span data-ttu-id="eb9f3-331">P1:Quantité</span><span class="sxs-lookup"><span data-stu-id="eb9f3-331">P1:Quantity</span></span></th>
    <th><span data-ttu-id="eb9f3-332">P1:Montant</span><span class="sxs-lookup"><span data-stu-id="eb9f3-332">P1:Amount</span></span></th>
    <th><span data-ttu-id="eb9f3-333">P2:Quantité</span><span class="sxs-lookup"><span data-stu-id="eb9f3-333">P2:Quantity</span></span></th>
    <th><span data-ttu-id="eb9f3-334">P2:Montant</span><span class="sxs-lookup"><span data-stu-id="eb9f3-334">P2:Amount</span></span></th>
    <th><span data-ttu-id="eb9f3-335">P3:Quantité</span><span class="sxs-lookup"><span data-stu-id="eb9f3-335">P3:Quantity</span></span></th>
    <th><span data-ttu-id="eb9f3-336">P3:Montant</span><span class="sxs-lookup"><span data-stu-id="eb9f3-336">P3:Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
    <td><span data-ttu-id="eb9f3-337">1000</span><span class="sxs-lookup"><span data-stu-id="eb9f3-337">1000</span></span></td>
    <td><span data-ttu-id="eb9f3-338">1</span><span class="sxs-lookup"><span data-stu-id="eb9f3-338">1</span></span></td>
    <td><span data-ttu-id="eb9f3-339">11</span><span class="sxs-lookup"><span data-stu-id="eb9f3-339">11</span></span></td>
    <td><span data-ttu-id="eb9f3-340">10</span><span class="sxs-lookup"><span data-stu-id="eb9f3-340">10</span></span></td>
    <td><span data-ttu-id="eb9f3-341">910.70</span><span class="sxs-lookup"><span data-stu-id="eb9f3-341">910.70</span></span></td>
    <td><span data-ttu-id="eb9f3-342">14</span><span class="sxs-lookup"><span data-stu-id="eb9f3-342">14</span></span></td>
    <td><span data-ttu-id="eb9f3-343">1,275.00</span><span class="sxs-lookup"><span data-stu-id="eb9f3-343">1,275.00</span></span></td>
    <td><span data-ttu-id="eb9f3-344">91.07</span><span class="sxs-lookup"><span data-stu-id="eb9f3-344">91.07</span></span></td>
    <td><span data-ttu-id="eb9f3-345">0,00</span><span class="sxs-lookup"><span data-stu-id="eb9f3-345">0.00</span></span></td>
    <td></td>
    <td><span data-ttu-id="eb9f3-346">5.00</span><span class="sxs-lookup"><span data-stu-id="eb9f3-346">5.00</span></span></td>
    <td><span data-ttu-id="eb9f3-347">455.36</span><span class="sxs-lookup"><span data-stu-id="eb9f3-347">455.36</span></span></td>
    <td><span data-ttu-id="eb9f3-348">5.00</span><span class="sxs-lookup"><span data-stu-id="eb9f3-348">5.00</span></span></td>
    <td><span data-ttu-id="eb9f3-349">455.36</span><span class="sxs-lookup"><span data-stu-id="eb9f3-349">455.36</span></span></td>
</tr>
<tr>
    <td><span data-ttu-id="eb9f3-350">1000</span><span class="sxs-lookup"><span data-stu-id="eb9f3-350">1000</span></span></td>
    <td><span data-ttu-id="eb9f3-351">1</span><span class="sxs-lookup"><span data-stu-id="eb9f3-351">1</span></span></td>
    <td><span data-ttu-id="eb9f3-352">12</span><span class="sxs-lookup"><span data-stu-id="eb9f3-352">12</span></span></td>
    <td><span data-ttu-id="eb9f3-353">4</span><span class="sxs-lookup"><span data-stu-id="eb9f3-353">4</span></span></td>
    <td><span data-ttu-id="eb9f3-354">364.29</span><span class="sxs-lookup"><span data-stu-id="eb9f3-354">364.29</span></span></td>
    <td><span data-ttu-id="eb9f3-355">14</span><span class="sxs-lookup"><span data-stu-id="eb9f3-355">14</span></span></td>
    <td><span data-ttu-id="eb9f3-356">1,275.00</span><span class="sxs-lookup"><span data-stu-id="eb9f3-356">1,275.00</span></span></td>
    <td><span data-ttu-id="eb9f3-357">91.07</span><span class="sxs-lookup"><span data-stu-id="eb9f3-357">91.07</span></span></td>
    <td><span data-ttu-id="eb9f3-358">4.00</span><span class="sxs-lookup"><span data-stu-id="eb9f3-358">4.00</span></span></td>
    <td><span data-ttu-id="eb9f3-359">364.29</span><span class="sxs-lookup"><span data-stu-id="eb9f3-359">364.29</span></span></td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
</tr>
<tr>
    <td><span data-ttu-id="eb9f3-360">1000</span><span class="sxs-lookup"><span data-stu-id="eb9f3-360">1000</span></span></td>
    <td><span data-ttu-id="eb9f3-361">2</span><span class="sxs-lookup"><span data-stu-id="eb9f3-361">2</span></span></td>
    <td></td>
    <td><span data-ttu-id="eb9f3-362">10</span><span class="sxs-lookup"><span data-stu-id="eb9f3-362">10</span></span></td>
    <td><span data-ttu-id="eb9f3-363">2,000.00</span><span class="sxs-lookup"><span data-stu-id="eb9f3-363">2,000.00</span></span></td>
    <td><span data-ttu-id="eb9f3-364">10</span><span class="sxs-lookup"><span data-stu-id="eb9f3-364">10</span></span></td>
    <td><span data-ttu-id="eb9f3-365">2,000.00</span><span class="sxs-lookup"><span data-stu-id="eb9f3-365">2,000.00</span></span></td>
    <td><span data-ttu-id="eb9f3-366">200.00</span><span class="sxs-lookup"><span data-stu-id="eb9f3-366">200.00</span></span></td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
    <td><span data-ttu-id="eb9f3-367">10.00</span><span class="sxs-lookup"><span data-stu-id="eb9f3-367">10.00</span></span></td>
    <td><span data-ttu-id="eb9f3-368">2,000.00</span><span class="sxs-lookup"><span data-stu-id="eb9f3-368">2,000.00</span></span></td>
</tr>
</tbody>
<tfoot>
<tr>
    <td><span data-ttu-id="eb9f3-369"><strong>Nombre total : 1000</strong></span><span class="sxs-lookup"><span data-stu-id="eb9f3-369"><strong>1000 Totals</strong></span></span></td>
    <td></td>
    <td></td>
    <td><span data-ttu-id="eb9f3-370"><strong>24.00</strong></span><span class="sxs-lookup"><span data-stu-id="eb9f3-370"><strong>24.00</strong></span></span></td>
    <td><span data-ttu-id="eb9f3-371"><strong>3,275.00</strong></span><span class="sxs-lookup"><span data-stu-id="eb9f3-371"><strong>3,275.00</strong></span></span></td>
    <td></td>
    <td></td>
    <td></td>
    <td><span data-ttu-id="eb9f3-372"><strong>4.00</strong></span><span class="sxs-lookup"><span data-stu-id="eb9f3-372"><strong>4.00</strong></span></span></td>
    <td><span data-ttu-id="eb9f3-373"><strong>364.29</strong></span><span class="sxs-lookup"><span data-stu-id="eb9f3-373"><strong>364.29</strong></span></span></td>
    <td><span data-ttu-id="eb9f3-374"><strong>5.00</strong></span><span class="sxs-lookup"><span data-stu-id="eb9f3-374"><strong>5.00</strong></span></span></td>
    <td><span data-ttu-id="eb9f3-375"><strong>455.36</strong></span><span class="sxs-lookup"><span data-stu-id="eb9f3-375"><strong>455.36</strong></span></span></td>
    <td><span data-ttu-id="eb9f3-376"><strong>15</strong></span><span class="sxs-lookup"><span data-stu-id="eb9f3-376"><strong>15</strong></span></span></td>
    <td><span data-ttu-id="eb9f3-377"><strong>2,455.36</strong></span><span class="sxs-lookup"><span data-stu-id="eb9f3-377"><strong>2,455.36</strong></span></span></td>
</tr>
</tfoot>
</table>
