---
title: "Clés de réduction"
description: "Cet article fournit des exemples qui indiquent comment paramétrer une clé de réduction. Il inclut des informations sur les différents paramètres de clé de réduction et les résultats de chacun d'entre eux. Vous pouvez utiliser une clé de réduction pour définir la méthode permettant de réduire les besoins de prévision."
author: roxanadiaconu
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: ReqPlanSched
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 19251
ms.assetid: aa9e0dfb-6052-4a2e-9378-89507c02fdf2
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: roxanad
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: 30634b0af343ad171c385a95c4ba0934180f70cf
ms.contentlocale: fr-fr
ms.lasthandoff: 08/29/2017

---

# <a name="reduction-keys"></a><span data-ttu-id="6bc98-105">Clés de réduction</span><span class="sxs-lookup"><span data-stu-id="6bc98-105">Reduction keys</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="6bc98-106">Cet article fournit des exemples qui indiquent comment paramétrer une clé de réduction.</span><span class="sxs-lookup"><span data-stu-id="6bc98-106">This articles provides examples that show how to set up a reduction key.</span></span> <span data-ttu-id="6bc98-107">Il inclut des informations sur les différents paramètres de clé de réduction et les résultats de chacun d'entre eux.</span><span class="sxs-lookup"><span data-stu-id="6bc98-107">It includes information about the various reduction key settings and the results of each.</span></span> <span data-ttu-id="6bc98-108">Vous pouvez utiliser une clé de réduction pour définir la méthode permettant de réduire les besoins de prévision.</span><span class="sxs-lookup"><span data-stu-id="6bc98-108">You can use a reduction key to define how to reduce forecast requirements.</span></span>

<a name="example-1-percent---reduction-key-forecast-reduction-principle"></a><span data-ttu-id="6bc98-109">Exemple 1 : Pourcentage - principe de réduction prévisionnelle de la clé de réduction</span><span class="sxs-lookup"><span data-stu-id="6bc98-109">Example 1: Percent - reduction key forecast reduction principle</span></span>
---------------------------------------------------------------

<span data-ttu-id="6bc98-110">Cet exemple décrit la manière dont une clé de réduction réduit les besoins de prévision de la demande en fonction des pourcentages et périodes définis par la clé de réduction.</span><span class="sxs-lookup"><span data-stu-id="6bc98-110">This example shows how a reduction key reduces demand forecast requirements according to the percentages and periods that are defined by the reduction key.</span></span>

1.  <span data-ttu-id="6bc98-111">Dans la page **Clés de réduction**, paramétrez les lignes suivantes.</span><span class="sxs-lookup"><span data-stu-id="6bc98-111">On the **Reduction keys** page, set up the following lines.</span></span>
    | <span data-ttu-id="6bc98-112">Monnaie</span><span class="sxs-lookup"><span data-stu-id="6bc98-112">Change</span></span> | <span data-ttu-id="6bc98-113">Unité</span><span class="sxs-lookup"><span data-stu-id="6bc98-113">Unit</span></span>  | <span data-ttu-id="6bc98-114">Pourcentage</span><span class="sxs-lookup"><span data-stu-id="6bc98-114">Percent</span></span> |
    |--------|-------|---------|
    | <span data-ttu-id="6bc98-115">1</span><span class="sxs-lookup"><span data-stu-id="6bc98-115">1</span></span>      | <span data-ttu-id="6bc98-116">Mois</span><span class="sxs-lookup"><span data-stu-id="6bc98-116">Month</span></span> | <span data-ttu-id="6bc98-117">100</span><span class="sxs-lookup"><span data-stu-id="6bc98-117">100</span></span>     |
    | <span data-ttu-id="6bc98-118">2</span><span class="sxs-lookup"><span data-stu-id="6bc98-118">2</span></span>      | <span data-ttu-id="6bc98-119">Mois</span><span class="sxs-lookup"><span data-stu-id="6bc98-119">Month</span></span> | <span data-ttu-id="6bc98-120">75</span><span class="sxs-lookup"><span data-stu-id="6bc98-120">75</span></span>      |
    | <span data-ttu-id="6bc98-121">3</span><span class="sxs-lookup"><span data-stu-id="6bc98-121">3</span></span>      | <span data-ttu-id="6bc98-122">Mois</span><span class="sxs-lookup"><span data-stu-id="6bc98-122">Month</span></span> | <span data-ttu-id="6bc98-123">50</span><span class="sxs-lookup"><span data-stu-id="6bc98-123">50</span></span>      |
    | <span data-ttu-id="6bc98-124">4</span><span class="sxs-lookup"><span data-stu-id="6bc98-124">4</span></span>      | <span data-ttu-id="6bc98-125">Mois</span><span class="sxs-lookup"><span data-stu-id="6bc98-125">Month</span></span> | <span data-ttu-id="6bc98-126">25</span><span class="sxs-lookup"><span data-stu-id="6bc98-126">25</span></span>      |

2.  <span data-ttu-id="6bc98-127">Liez la clé de réduction au groupe de couverture de l'article.</span><span class="sxs-lookup"><span data-stu-id="6bc98-127">Link the reduction key to the item's coverage group.</span></span>
3.  <span data-ttu-id="6bc98-128">Dans la page **Plans généraux**, dans le champ **Principe de réduction**, sélectionnez **Pourcentage - clé de réduction**.</span><span class="sxs-lookup"><span data-stu-id="6bc98-128">On the **Master plans** page, in the **Reduction principle** field, select **Percent - reduction key**.</span></span>
4.  <span data-ttu-id="6bc98-129">Créez une prévision de la demande de 1 000 pièces par mois.</span><span class="sxs-lookup"><span data-stu-id="6bc98-129">Create a demand forecast of 1,000 pieces per month.</span></span>

<span data-ttu-id="6bc98-130">Si vous lancez le calendrier des prévisions le 1er janvier, les besoins de prévision de la demande sont utilisés en fonction des pourcentages définis dans la page **Clés de réduction**.</span><span class="sxs-lookup"><span data-stu-id="6bc98-130">If you run forecast scheduling on January 1, the demand forecast requirements are consumed according to the percentages that you set up on the **Reduction keys** page.</span></span> <span data-ttu-id="6bc98-131">Les quantités requises suivantes sont transférées vers le plan général.</span><span class="sxs-lookup"><span data-stu-id="6bc98-131">The following requirement quantities are transferred to the master plan.</span></span>

| <span data-ttu-id="6bc98-132">Mois</span><span class="sxs-lookup"><span data-stu-id="6bc98-132">Month</span></span>                | <span data-ttu-id="6bc98-133">Nombre de pièces requises</span><span class="sxs-lookup"><span data-stu-id="6bc98-133">Number of pieces required</span></span> |
|----------------------|---------------------------|
| <span data-ttu-id="6bc98-134">Janvier</span><span class="sxs-lookup"><span data-stu-id="6bc98-134">January</span></span>              | <span data-ttu-id="6bc98-135">0</span><span class="sxs-lookup"><span data-stu-id="6bc98-135">0</span></span>                         |
| <span data-ttu-id="6bc98-136">Février</span><span class="sxs-lookup"><span data-stu-id="6bc98-136">February</span></span>             | <span data-ttu-id="6bc98-137">250</span><span class="sxs-lookup"><span data-stu-id="6bc98-137">250</span></span>                       |
| <span data-ttu-id="6bc98-138">Mars</span><span class="sxs-lookup"><span data-stu-id="6bc98-138">March</span></span>                | <span data-ttu-id="6bc98-139">500</span><span class="sxs-lookup"><span data-stu-id="6bc98-139">500</span></span>                       |
| <span data-ttu-id="6bc98-140">Avril</span><span class="sxs-lookup"><span data-stu-id="6bc98-140">April</span></span>                | <span data-ttu-id="6bc98-141">750</span><span class="sxs-lookup"><span data-stu-id="6bc98-141">750</span></span>                       |
| <span data-ttu-id="6bc98-142">Mai à décembre</span><span class="sxs-lookup"><span data-stu-id="6bc98-142">May through December</span></span> | <span data-ttu-id="6bc98-143">1 000</span><span class="sxs-lookup"><span data-stu-id="6bc98-143">1,000</span></span>                     |

## <a name="example-2-transactions--reduction-key-forecast-reduction-principle"></a><span data-ttu-id="6bc98-144">Exemple 2 : Transactions  principe de réduction prévisionnelle de la clé de réduction</span><span class="sxs-lookup"><span data-stu-id="6bc98-144">Example 2: Transactions  reduction key forecast reduction principle</span></span>
<span data-ttu-id="6bc98-145">Cet exemple décrit la manière dont les commandes réelles, qui se produisent durant les périodes définies par la clé de réduction, réduisent les besoins de prévision de la demande.</span><span class="sxs-lookup"><span data-stu-id="6bc98-145">This example shows how actual orders that occur during the periods that are defined by the reduction key reduce demand forecast requirements.</span></span>

-   <span data-ttu-id="6bc98-146">Dans la page **Plans généraux**, dans le champ **Principe de réduction**, sélectionnez **Transactions - clé de réduction**.</span><span class="sxs-lookup"><span data-stu-id="6bc98-146">On the **Master plans** page, in the **Reduction principle** field, select **Transactions - reduction key**.</span></span>

<span data-ttu-id="6bc98-147">Les commandes client suivantes sont prises en compte le 1er janvier.</span><span class="sxs-lookup"><span data-stu-id="6bc98-147">The following sales orders exist on January 1.</span></span>

| <span data-ttu-id="6bc98-148">Mois</span><span class="sxs-lookup"><span data-stu-id="6bc98-148">Month</span></span>    | <span data-ttu-id="6bc98-149">Nombre de pièces commandées</span><span class="sxs-lookup"><span data-stu-id="6bc98-149">Number of pieces ordered</span></span> |
|----------|--------------------------|
| <span data-ttu-id="6bc98-150">Janvier</span><span class="sxs-lookup"><span data-stu-id="6bc98-150">January</span></span>  | <span data-ttu-id="6bc98-151">956</span><span class="sxs-lookup"><span data-stu-id="6bc98-151">956</span></span>                      |
| <span data-ttu-id="6bc98-152">Février</span><span class="sxs-lookup"><span data-stu-id="6bc98-152">February</span></span> | <span data-ttu-id="6bc98-153">1 176</span><span class="sxs-lookup"><span data-stu-id="6bc98-153">1,176</span></span>                    |
| <span data-ttu-id="6bc98-154">Mars</span><span class="sxs-lookup"><span data-stu-id="6bc98-154">March</span></span>    | <span data-ttu-id="6bc98-155">451</span><span class="sxs-lookup"><span data-stu-id="6bc98-155">451</span></span>                      |
| <span data-ttu-id="6bc98-156">Avril</span><span class="sxs-lookup"><span data-stu-id="6bc98-156">April</span></span>    | <span data-ttu-id="6bc98-157">119</span><span class="sxs-lookup"><span data-stu-id="6bc98-157">119</span></span>                      |

<span data-ttu-id="6bc98-158">Si vous utilisez les mêmes prévisions de la demande de 1 000 pièces par mois, les quantités requises suivantes sont transférées vers le plan général.</span><span class="sxs-lookup"><span data-stu-id="6bc98-158">If you use the same demand forecast of 1,000 pieces per month, the following requirement quantities are transferred to the master plan.</span></span>

| <span data-ttu-id="6bc98-159">Mois</span><span class="sxs-lookup"><span data-stu-id="6bc98-159">Month</span></span>                | <span data-ttu-id="6bc98-160">Nombre de pièces requises</span><span class="sxs-lookup"><span data-stu-id="6bc98-160">Number of pieces required</span></span> |
|----------------------|---------------------------|
| <span data-ttu-id="6bc98-161">Janvier</span><span class="sxs-lookup"><span data-stu-id="6bc98-161">January</span></span>              | <span data-ttu-id="6bc98-162">44</span><span class="sxs-lookup"><span data-stu-id="6bc98-162">44</span></span>                        |
| <span data-ttu-id="6bc98-163">Février</span><span class="sxs-lookup"><span data-stu-id="6bc98-163">February</span></span>             | <span data-ttu-id="6bc98-164">0</span><span class="sxs-lookup"><span data-stu-id="6bc98-164">0</span></span>                         |
| <span data-ttu-id="6bc98-165">Mars</span><span class="sxs-lookup"><span data-stu-id="6bc98-165">March</span></span>                | <span data-ttu-id="6bc98-166">549</span><span class="sxs-lookup"><span data-stu-id="6bc98-166">549</span></span>                       |
| <span data-ttu-id="6bc98-167">Avril</span><span class="sxs-lookup"><span data-stu-id="6bc98-167">April</span></span>                | <span data-ttu-id="6bc98-168">881</span><span class="sxs-lookup"><span data-stu-id="6bc98-168">881</span></span>                       |
| <span data-ttu-id="6bc98-169">Mai à décembre</span><span class="sxs-lookup"><span data-stu-id="6bc98-169">May through December</span></span> | <span data-ttu-id="6bc98-170">1 000</span><span class="sxs-lookup"><span data-stu-id="6bc98-170">1,000</span></span>                     |

## <a name="example-3-transactions--dynamic-period-forecast-reduction-principle"></a><span data-ttu-id="6bc98-171">Exemple 3 : Transactions  principe de réduction prévisionnelle de la période dynamique</span><span class="sxs-lookup"><span data-stu-id="6bc98-171">Example 3: Transactions  dynamic period forecast reduction principle</span></span>
<span data-ttu-id="6bc98-172">Dans la plupart des cas, les systèmes sont paramétrés de telle sorte que les transactions réduisent la prévision de la demande durant des périodes prévisionnelles spécifiques : semaines, mois, etc.</span><span class="sxs-lookup"><span data-stu-id="6bc98-172">In most cases, systems are set up so that transactions reduce demand forecast within specific forecast periods: weeks, months, and so on.</span></span> <span data-ttu-id="6bc98-173">Ces périodes sont définies dans la clé de réduction.</span><span class="sxs-lookup"><span data-stu-id="6bc98-173">These periods are defined in the reduction key.</span></span> <span data-ttu-id="6bc98-174">Toutefois, la durée entre deux lignes de prévision de la demande peut également *impliquer* une période.</span><span class="sxs-lookup"><span data-stu-id="6bc98-174">However, the time between two demand forecast lines can also *imply* a period.</span></span>

1.  <span data-ttu-id="6bc98-175">Créez une prévision de la demande pour les dates et les quantités suivantes.</span><span class="sxs-lookup"><span data-stu-id="6bc98-175">Create a demand forecast for the following dates and quantities.</span></span>
    | <span data-ttu-id="6bc98-176">Date</span><span class="sxs-lookup"><span data-stu-id="6bc98-176">Date</span></span>       | <span data-ttu-id="6bc98-177">Prévision de la demande</span><span class="sxs-lookup"><span data-stu-id="6bc98-177">Demand forecast</span></span> |
    |------------|-----------------|
    | <span data-ttu-id="6bc98-178">1er janvier</span><span class="sxs-lookup"><span data-stu-id="6bc98-178">January 1</span></span>  | <span data-ttu-id="6bc98-179">1.000</span><span class="sxs-lookup"><span data-stu-id="6bc98-179">1,000</span></span>           |
    | <span data-ttu-id="6bc98-180">5 janvier</span><span class="sxs-lookup"><span data-stu-id="6bc98-180">January 5</span></span>  | <span data-ttu-id="6bc98-181">500</span><span class="sxs-lookup"><span data-stu-id="6bc98-181">500</span></span>             |
    | <span data-ttu-id="6bc98-182">12 janvier</span><span class="sxs-lookup"><span data-stu-id="6bc98-182">January 12</span></span> | <span data-ttu-id="6bc98-183">1.000</span><span class="sxs-lookup"><span data-stu-id="6bc98-183">1,000</span></span>           |

    <span data-ttu-id="6bc98-184">Dans cette prévision, il n'y a pas de période précise entre les dates de prévision : entre les première et deuxième dates, il y a une période de quatre jours, et entre les deuxième et troisième dates, il y a une période de sept jours.</span><span class="sxs-lookup"><span data-stu-id="6bc98-184">In this forecast, there isn't a clear period between the forecast dates: between the first and second dates there is a four-day span, and between the second and third dates there is a seven-day span.</span></span> <span data-ttu-id="6bc98-185">Ces différentes périodes sont les périodes dynamiques.</span><span class="sxs-lookup"><span data-stu-id="6bc98-185">These various spans are the dynamic periods.</span></span>
2.  <span data-ttu-id="6bc98-186">Créez des lignes de commande client comme suit.</span><span class="sxs-lookup"><span data-stu-id="6bc98-186">Create sales order lines as follows.</span></span>
    | <span data-ttu-id="6bc98-187">Date</span><span class="sxs-lookup"><span data-stu-id="6bc98-187">Date</span></span>                             | <span data-ttu-id="6bc98-188">Quantité de la commande client</span><span class="sxs-lookup"><span data-stu-id="6bc98-188">Sales order quantity</span></span> |
    |----------------------------------|----------------------|
    | <span data-ttu-id="6bc98-189">15 décembre de l'année précédente</span><span class="sxs-lookup"><span data-stu-id="6bc98-189">December 15 in the previous year</span></span> | <span data-ttu-id="6bc98-190">500</span><span class="sxs-lookup"><span data-stu-id="6bc98-190">500</span></span>                  |
    | <span data-ttu-id="6bc98-191">3 janvier</span><span class="sxs-lookup"><span data-stu-id="6bc98-191">January 3</span></span>                        | <span data-ttu-id="6bc98-192">100</span><span class="sxs-lookup"><span data-stu-id="6bc98-192">100</span></span>                  |
    | <span data-ttu-id="6bc98-193">10 janvier</span><span class="sxs-lookup"><span data-stu-id="6bc98-193">January 10</span></span>                       | <span data-ttu-id="6bc98-194">200</span><span class="sxs-lookup"><span data-stu-id="6bc98-194">200</span></span>                  |

<span data-ttu-id="6bc98-195">La prévision est réduite comme suit :</span><span class="sxs-lookup"><span data-stu-id="6bc98-195">The forecast will be reduced as follows:</span></span>

-   <span data-ttu-id="6bc98-196">La première commande client n'est pas effectuée dans une période donnée, elle ne réduit donc aucune prévision.</span><span class="sxs-lookup"><span data-stu-id="6bc98-196">The first sales order isn't within any period, so it won't reduce any forecast.</span></span>
-   <span data-ttu-id="6bc98-197">La deuxième commande client est effectuée entre le 1er et le 5 janvier, elle réduit donc la prévision du 1er janvier de 100.</span><span class="sxs-lookup"><span data-stu-id="6bc98-197">The second sales order is between January 1 and January 5, so it will reduce the forecast for January 1 by 100.</span></span>
-   <span data-ttu-id="6bc98-198">La troisième commande client est effectuée entre le 5 et le 12 janvier, elle réduit donc la prévision du 5 janvier de 200.</span><span class="sxs-lookup"><span data-stu-id="6bc98-198">The third sales order is between January 5 and January 12, so it will reduce the forecast for January 5 by 200.</span></span>

<span data-ttu-id="6bc98-199">L'ordre prévisionnel suivant est créé pour exécuter la prévision.</span><span class="sxs-lookup"><span data-stu-id="6bc98-199">The following planned order will be created to fulfill the forecast.</span></span>

| <span data-ttu-id="6bc98-200">Date de prévision de la demande</span><span class="sxs-lookup"><span data-stu-id="6bc98-200">Demand forecast date</span></span> | <span data-ttu-id="6bc98-201">Quantité réduite</span><span class="sxs-lookup"><span data-stu-id="6bc98-201">Reduced quantity</span></span> |
|----------------------|------------------|
| <span data-ttu-id="6bc98-202">1er janvier</span><span class="sxs-lookup"><span data-stu-id="6bc98-202">January 1</span></span>            | <span data-ttu-id="6bc98-203">900</span><span class="sxs-lookup"><span data-stu-id="6bc98-203">900</span></span>              |
| <span data-ttu-id="6bc98-204">5 janvier</span><span class="sxs-lookup"><span data-stu-id="6bc98-204">January 5</span></span>            | <span data-ttu-id="6bc98-205">300</span><span class="sxs-lookup"><span data-stu-id="6bc98-205">300</span></span>              |
| <span data-ttu-id="6bc98-206">12 janvier</span><span class="sxs-lookup"><span data-stu-id="6bc98-206">January 12</span></span>           | <span data-ttu-id="6bc98-207">1.000</span><span class="sxs-lookup"><span data-stu-id="6bc98-207">1,000</span></span>            |

<span data-ttu-id="6bc98-208">Voici un résumé de la réduction **Transactions - période dynamique** :</span><span class="sxs-lookup"><span data-stu-id="6bc98-208">Here is a summary of **Transactions - dynamic period** reduction:</span></span>

-   <span data-ttu-id="6bc98-209">Les besoins prévisionnels sont réduits par les transactions de commande réelles qui surviennent dans la période dynamique.</span><span class="sxs-lookup"><span data-stu-id="6bc98-209">Forecast requirements are reduced by the actual order transactions that occur during the dynamic period.</span></span> <span data-ttu-id="6bc98-210">La période dynamique couvre les dates de prévision actuelles et se termine au début de la prochaine prévision.</span><span class="sxs-lookup"><span data-stu-id="6bc98-210">The dynamic period covers the current forecast dates and ends at the start of the next forecast.</span></span>
-   <span data-ttu-id="6bc98-211">Cette méthode n'utilise pas ou ne nécessite pas une clé de réduction.</span><span class="sxs-lookup"><span data-stu-id="6bc98-211">This method doesn't use or require a reduction key.</span></span>
-   <span data-ttu-id="6bc98-212">Lorsque cette option est utilisée, le comportement suivant se produit :</span><span class="sxs-lookup"><span data-stu-id="6bc98-212">When this option is used, the following behavior occurs:</span></span>
    -   <span data-ttu-id="6bc98-213">Si la prévision est réduite complètement, les besoins prévisionnels actuels passent à 0 (zéro).</span><span class="sxs-lookup"><span data-stu-id="6bc98-213">If the forecast is reduced completely, the forecast requirements for the current forecast become 0 (zero).</span></span>
    -   <span data-ttu-id="6bc98-214">En l'absence de prévision à venir, les besoins de la dernière prévision entrée sont réduits.</span><span class="sxs-lookup"><span data-stu-id="6bc98-214">If there is no future forecast, forecast requirements from the last forecast that was entered are reduced.</span></span>
    -   <span data-ttu-id="6bc98-215">Les plages de gestion sont incluses dans le calcul de réduction des prévisions.</span><span class="sxs-lookup"><span data-stu-id="6bc98-215">Time fences are included in the forecast reduction calculation.</span></span>
    -   <span data-ttu-id="6bc98-216">Les jours positifs sont inclus dans le calcul de réduction des prévisions.</span><span class="sxs-lookup"><span data-stu-id="6bc98-216">Positive days are included in the forecast reduction calculation.</span></span>
    -   <span data-ttu-id="6bc98-217">Si les transactions de commande réelles dépassent les besoins prévisionnels, les transactions restantes ne sont pas expédiées à la période suivante de prévision.</span><span class="sxs-lookup"><span data-stu-id="6bc98-217">If actual order transactions exceed the forecasted requirements, the remaining transactions aren't forwarded to the next forecast period.</span></span>


<a name="see-also"></a><span data-ttu-id="6bc98-218">Voir également :</span><span class="sxs-lookup"><span data-stu-id="6bc98-218">See also</span></span>
--------

[<span data-ttu-id="6bc98-219">Plans généraux</span><span class="sxs-lookup"><span data-stu-id="6bc98-219">Master plans</span></span>](master-plans.md)




