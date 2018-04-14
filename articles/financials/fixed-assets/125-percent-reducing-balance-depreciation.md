---
title: "Amortissement dégressif de 125 %"
description: "Cet article donne une vue d'ensemble de la méthode d'amortissement dégressif de 125 %."
author: saraschi2
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: AssetDepreciationProfile
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 13871
ms.assetid: 3abc263e-59d6-4f1a-986d-1be388948bd3
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: 59ee71f3f7cd3bab39e9cd3c8bee64eef9ee6a11
ms.contentlocale: fr-fr
ms.lasthandoff: 04/13/2018

---

# <a name="125-percent-reducing-balance-depreciation"></a><span data-ttu-id="9d418-103">Amortissement dégressif de 125 %</span><span class="sxs-lookup"><span data-stu-id="9d418-103">125 percent reducing balance depreciation</span></span>

[!INCLUDE [banner](../includes/banner.md)]

<span data-ttu-id="9d418-104">Cet article donne une vue d'ensemble de la méthode d'amortissement dégressif de 125 %.</span><span class="sxs-lookup"><span data-stu-id="9d418-104">This article gives an overview of the 125 percent reducing balance method of depreciation.</span></span>

<span data-ttu-id="9d418-105">Si vous définissez un profil d'amortissement d'immobilisation, puis sélectionnez **Amortissement dégressif de 125 %** dans le champ **Méthode** de la page **Profils d'amortissement**, les immobilisations affectées à ce profil d'amortissement sont amorties par le même pourcentage pour chaque période d'amortissement.</span><span class="sxs-lookup"><span data-stu-id="9d418-105">When you set up a fixed asset depreciation profile and select **125% reducing balance** in the **Method** field on the **Depreciation profiles** page, fixed assets that are assigned to the depreciation profile are depreciated by the same percentage in each depreciation period.</span></span> <span data-ttu-id="9d418-106">Ce pourcentage est calculé sur la base de la durée de vie de l'immobilisation.</span><span class="sxs-lookup"><span data-stu-id="9d418-106">This percentage is calculated based on the service life of the asset.</span></span> <span data-ttu-id="9d418-107">Par exemple, si une immobilisation a une durée de vie de cinq ans, la valeur de pourcentage calculée est de 25 pourcent (125 % ÷ 5).</span><span class="sxs-lookup"><span data-stu-id="9d418-107">For example, if an asset has a service life of five years, the percentage is calculated as 25 percent (125% ÷ 5).</span></span>

<span data-ttu-id="9d418-108">Pour paramétrer un amortissement dégressif de 125 %, vous devez également sélectionner des options dans les champs **Année d'amortissement** et **Fréquence** sur la page **Profils d'amortissement**.</span><span class="sxs-lookup"><span data-stu-id="9d418-108">To set up 125% reducing balance depreciation, you must also select options in the **Depreciation year** field and the **Period frequency** field on the **Depreciation profiles** page.</span></span> <span data-ttu-id="9d418-109">Les options disponibles dans le champ **Fréquence** varient en fonction de la valeur sélectionnée dans le champ **Année d'amortissement**.</span><span class="sxs-lookup"><span data-stu-id="9d418-109">The options that are available in the **Period frequency** field vary, depending on the value that is selected in the **Depreciation year** field.</span></span>

## <a name="select-a-depreciation-year"></a><span data-ttu-id="9d418-110">Sélectionner une année d'amortissement</span><span class="sxs-lookup"><span data-stu-id="9d418-110">Select a depreciation year</span></span>
<span data-ttu-id="9d418-111">Vous pouvez sélectionner soit **Calendrier** soit **Exercice** dans le champ **Année d'amortissement** de la page **Profils d'amortissement**.</span><span class="sxs-lookup"><span data-stu-id="9d418-111">You can select either **Calendar** or **Fiscal** in the **Depreciation year** field on the **Depreciation profiles** page.</span></span> <span data-ttu-id="9d418-112">La valeur par défaut est **Calendrier**.</span><span class="sxs-lookup"><span data-stu-id="9d418-112">The default value is **Calendar**.</span></span> 

<span data-ttu-id="9d418-113">Votre sélection détermine les options disponibles dans le champ **Fréquence**.</span><span class="sxs-lookup"><span data-stu-id="9d418-113">Your selection determines the options that are available in the **Period frequency** field.</span></span> <span data-ttu-id="9d418-114">Ce champ définit les dates et les montants de validation de régularisation des amortissements au cours de l'année civile.</span><span class="sxs-lookup"><span data-stu-id="9d418-114">This field defines the depreciation accrual posting dates and amounts throughout the calendar year.</span></span>

### <a name="calendar"></a><span data-ttu-id="9d418-115">Calendrier</span><span class="sxs-lookup"><span data-stu-id="9d418-115">Calendar</span></span>

<span data-ttu-id="9d418-116">Vous pouvez décider de conserver la valeur par défaut du champ **Année d'amortissement**, **Calendrier**.</span><span class="sxs-lookup"><span data-stu-id="9d418-116">You can keep the default value in the **Depreciation year** field, **Calendar**.</span></span> 

<span data-ttu-id="9d418-117">L'option **Calendrier** met à jour la base d'amortissement le 1er janvier de chaque année.</span><span class="sxs-lookup"><span data-stu-id="9d418-117">The **Calendar** option updates the depreciation base on January 1 of each year.</span></span> <span data-ttu-id="9d418-118">Généralement, la base d'amortissement est la valeur nette moins la valeur de mise au rebut.</span><span class="sxs-lookup"><span data-stu-id="9d418-118">Typically, the depreciation base is the net book value minus the scrap value.</span></span> <span data-ttu-id="9d418-119">Dans les exemples plus loin dans cette rubrique, la base d'amortissement est le numérateur de la première expression de la colonne Calcul.</span><span class="sxs-lookup"><span data-stu-id="9d418-119">In the examples later in this topic, the depreciation base is the numerator in the first expression in the calculations column.</span></span> 

<span data-ttu-id="9d418-120">Si vous sélectionnez **Calendrier** comme année d'amortissement, les options suivantes sont disponibles dans le champ **Fréquence** :</span><span class="sxs-lookup"><span data-stu-id="9d418-120">If you select **Calendar** as the depreciation year, the following options are available in the **Period frequency** field:</span></span>

-   <span data-ttu-id="9d418-121">**Annuel** valide un montant le 31 décembre.</span><span class="sxs-lookup"><span data-stu-id="9d418-121">**Yearly** posts an amount on December 31.</span></span>
-   <span data-ttu-id="9d418-122">**Mensuel** valide un montant mensuel à la fin de chaque mois du calendrier.</span><span class="sxs-lookup"><span data-stu-id="9d418-122">**Monthly** posts a monthly amount at the end of each calendar month.</span></span>
-   <span data-ttu-id="9d418-123">**Trimestriel** valide un montant trimestriel à la fin de chaque trimestre du calendrier (31 mars, 30 juin, 30 septembre et 31 décembre).</span><span class="sxs-lookup"><span data-stu-id="9d418-123">**Quarterly** posts a quarterly amount at the end of each calendar quarter (March 31, June 30, September 30, and December 31).</span></span>
-   <span data-ttu-id="9d418-124">**Semestriel** valide un montant semestriel à la fin de chaque semestre du calendrier (30 juin et 31 décembre).</span><span class="sxs-lookup"><span data-stu-id="9d418-124">**Half-Yearly** posts a half-yearly amount at the calendar half year (June 30 and December 31).</span></span>
-   <span data-ttu-id="9d418-125">**Quotidien** valide le montant d'amortissement pour la méthode d'amortissement quotidien en utilisant une transaction par jour.</span><span class="sxs-lookup"><span data-stu-id="9d418-125">**Daily** posts the depreciation amount for the daily depreciation method by using one transaction for each day.</span></span>

### <a name="fiscal"></a><span data-ttu-id="9d418-126">Exercice</span><span class="sxs-lookup"><span data-stu-id="9d418-126">Fiscal</span></span>

<span data-ttu-id="9d418-127">Si vous sélectionnez **Exercice** dans le champ **Année d'amortissement**, l'amortissement dégressif de 125 % est calculé sur la base de l'exercice du calendrier fiscal spécifié pour le registre, ou pour le calendrier fiscal sélectionné sur la page **Comptabilité**.</span><span class="sxs-lookup"><span data-stu-id="9d418-127">If you select **Fiscal** in the **Depreciation year** field, 125% reducing depreciation is calculated based on the fiscal year for the fiscal calendar that is specified for the book, or for the fiscal calendar that is selected on the **Ledger** page.</span></span> <span data-ttu-id="9d418-128">Les calendriers fiscaux sont paramétrés sur la page **Calendriers fiscaux**.</span><span class="sxs-lookup"><span data-stu-id="9d418-128">Fiscal calendars are set up on the **Fiscal calendars** page.</span></span> 

<span data-ttu-id="9d418-129">Par exemple, pour l'exercice allant du 1er juillet au 30 juin, le calcul de l'amortissement commence le 1er juillet.</span><span class="sxs-lookup"><span data-stu-id="9d418-129">For example, for the fiscal year July 1 through June 30, the depreciation calculation starts on July 1.</span></span> <span data-ttu-id="9d418-130">L'exercice peut avoir une longueur supérieure ou inférieure à 12 mois.</span><span class="sxs-lookup"><span data-stu-id="9d418-130">The fiscal year can be longer or shorter than 12 months.</span></span> <span data-ttu-id="9d418-131">L'amortissement est automatiquement ajusté en fonction de chaque période fiscale et la longueur de l'exercice suivant est déterminé par la définition des périodes fiscales sur la page **Calendriers fiscaux**.</span><span class="sxs-lookup"><span data-stu-id="9d418-131">The depreciation is automatically adjusted for each period, and the length of the next fiscal year is determined by the setup of periods on the **Fiscal calendars** page.</span></span> 

<span data-ttu-id="9d418-132">Si vous sélectionnez **Exercice** comme année d'amortissement, les options suivantes sont disponibles dans le champ **Fréquence** :</span><span class="sxs-lookup"><span data-stu-id="9d418-132">If you select **Fiscal** as the depreciation year, the following options are available in the **Period frequency** field:</span></span>

-   <span data-ttu-id="9d418-133">**Annuel** valide le montant total de l'amortissement calculé pour l'exercice comme montant unique, le dernier jour de l'exercice.</span><span class="sxs-lookup"><span data-stu-id="9d418-133">**Yearly** posts the total amount of the depreciation that is calculated for the fiscal year as one amount, on the last day of the fiscal year.</span></span>
-   <span data-ttu-id="9d418-134">**Période fiscale**valide le montant total de l'amortissement calculé pour l'exercice.</span><span class="sxs-lookup"><span data-stu-id="9d418-134">**Fiscal period** posts the total amount of the depreciation that is calculated for the fiscal year.</span></span> <span data-ttu-id="9d418-135">Ce montant est régularisé dans les périodes fiscales définies sur la page **Calendriers fiscaux**.</span><span class="sxs-lookup"><span data-stu-id="9d418-135">This amount is accrued into the fiscal periods that are defined on the **Fiscal calendars** page.</span></span>

## <a name="example-of-125-reducing-balance-depreciation"></a><span data-ttu-id="9d418-136">Exemple d'amortissement dégressif de 125 %</span><span class="sxs-lookup"><span data-stu-id="9d418-136">Example of 125% reducing balance depreciation</span></span>

|                                |        |
|--------------------------------|--------|
| <span data-ttu-id="9d418-137">Prix d'acquisition</span><span class="sxs-lookup"><span data-stu-id="9d418-137">Acquisition cost</span></span>               | <span data-ttu-id="9d418-138">11 000</span><span class="sxs-lookup"><span data-stu-id="9d418-138">11,000</span></span> |
| <span data-ttu-id="9d418-139">Valeur résiduelle</span><span class="sxs-lookup"><span data-stu-id="9d418-139">Salvage value</span></span>                  | <span data-ttu-id="9d418-140">1 000</span><span class="sxs-lookup"><span data-stu-id="9d418-140">1,000</span></span>  |
| <span data-ttu-id="9d418-141">Base d'amortissement</span><span class="sxs-lookup"><span data-stu-id="9d418-141">Depreciation base</span></span>              | <span data-ttu-id="9d418-142">10 000</span><span class="sxs-lookup"><span data-stu-id="9d418-142">10,000</span></span> |
| <span data-ttu-id="9d418-143">Années de durée de vie</span><span class="sxs-lookup"><span data-stu-id="9d418-143">Service life years</span></span>             | <span data-ttu-id="9d418-144">5</span><span class="sxs-lookup"><span data-stu-id="9d418-144">5</span></span>      |
| <span data-ttu-id="9d418-145">Pourcentage d'amortissement annuel</span><span class="sxs-lookup"><span data-stu-id="9d418-145">Yearly depreciation percentage</span></span> | <span data-ttu-id="9d418-146">25 %</span><span class="sxs-lookup"><span data-stu-id="9d418-146">25%</span></span>    |

<span data-ttu-id="9d418-147">La méthode d'amortissement dégressif de 125 % divise 125 % par le nombre d'années de durée de vie.</span><span class="sxs-lookup"><span data-stu-id="9d418-147">The 125% reducing balance method divides 125 percent by the service life years.</span></span> <span data-ttu-id="9d418-148">Le pourcentage ainsi obtenu est multiplié par la valeur comptable nette de l'actif afin de déterminer le montant d'amortissement pour chaque année.</span><span class="sxs-lookup"><span data-stu-id="9d418-148">That percentage will be multiplied by the net book value of the asset to determine the depreciation amount for the year.</span></span>

| <span data-ttu-id="9d418-149">Période</span><span class="sxs-lookup"><span data-stu-id="9d418-149">Period</span></span> | <span data-ttu-id="9d418-150">Calcul du montant d'amortissement annuel</span><span class="sxs-lookup"><span data-stu-id="9d418-150">Calculation of the yearly depreciation amount</span></span> | <span data-ttu-id="9d418-151">Valeur comptable</span><span class="sxs-lookup"><span data-stu-id="9d418-151">Book value</span></span>                    | <span data-ttu-id="9d418-152">Valeur comptable nette à la fin de l'exercice</span><span class="sxs-lookup"><span data-stu-id="9d418-152">Net book value at the end of the year</span></span> |
|--------|-----------------------------------------------|-------------------------------|---------------------------------------|
| <span data-ttu-id="9d418-153">Année 1</span><span class="sxs-lookup"><span data-stu-id="9d418-153">Year 1</span></span> | <span data-ttu-id="9d418-154">(11 000 - 1 000) x 25 % = 2 500</span><span class="sxs-lookup"><span data-stu-id="9d418-154">(11,000 – 1,000) × 25% = 2,500</span></span>                | <span data-ttu-id="9d418-155">(11 000 - 2 500) = 8 500</span><span class="sxs-lookup"><span data-stu-id="9d418-155">(11,000 – 2,500) = 8,500</span></span>      | <span data-ttu-id="9d418-156">(11 000 - 1 000 - 2 500) = 7 500</span><span class="sxs-lookup"><span data-stu-id="9d418-156">(11,000 – 1,000 – 2,500) = 7,500</span></span>      |
| <span data-ttu-id="9d418-157">Année 2</span><span class="sxs-lookup"><span data-stu-id="9d418-157">Year 2</span></span> | <span data-ttu-id="9d418-158">7 500 × 25 % = 1 875</span><span class="sxs-lookup"><span data-stu-id="9d418-158">7,500 × 25% = 1,875</span></span>                           | <span data-ttu-id="9d418-159">(8 500 - 1 875) = 6 625</span><span class="sxs-lookup"><span data-stu-id="9d418-159">(8,500 – 1,875) = 6,625</span></span>       | <span data-ttu-id="9d418-160">(7 500 - 1 875) = 5 625</span><span class="sxs-lookup"><span data-stu-id="9d418-160">(7,500 – 1,875) = 5,625</span></span>               |
| <span data-ttu-id="9d418-161">Année 3</span><span class="sxs-lookup"><span data-stu-id="9d418-161">Year 3</span></span> | <span data-ttu-id="9d418-162">5 625 × 25 % = 1 406,25</span><span class="sxs-lookup"><span data-stu-id="9d418-162">5,625 × 25% = 1,406.25</span></span>                        | <span data-ttu-id="9d418-163">(6 625 - 1 406,25) = 5 218,75</span><span class="sxs-lookup"><span data-stu-id="9d418-163">(6,625 – 1,406.25) = 5,218.75</span></span> | <span data-ttu-id="9d418-164">(5 625 - 1 406,25) = 4 218,75</span><span class="sxs-lookup"><span data-stu-id="9d418-164">(5,625 – 1,406.25) = 4,218.75</span></span>         |

> [!NOTE] 
> <span data-ttu-id="9d418-165">Généralement, si le montant calculé via la méthode d'amortissement dégressif de 125 % est inférieur au montant calculé via la méthode linéaire, passer à la méthode linéaire pour la durée de vie restante reste possible.</span><span class="sxs-lookup"><span data-stu-id="9d418-165">Typically, when the amount that is calculated by using the 125% reducing balance depreciation method becomes less than the amount that would be calculated by using the straight line method, there is a conversion to the straight line method for the remaining life.</span></span>




