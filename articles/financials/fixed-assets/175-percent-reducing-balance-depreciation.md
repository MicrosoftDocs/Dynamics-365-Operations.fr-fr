---
title: Amortissement dégressif de 175 %
description: Cette rubrique donne une vue d'ensemble de la méthode d'amortissement dégressif de 175 %.
author: saraschi2
manager: AnnBe
ms.date: 10/30/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: AssetDepreciationProfile
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 13911
ms.assetid: cc5d001f-bcfe-4602-9ec1-9e265e9fd188
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 2a63293dbf24c27733f8013947aeab5792fa0db9
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/29/2019
ms.locfileid: "320165"
---
# <a name="175-percent-reducing-balance-depreciation"></a><span data-ttu-id="b288a-103">Amortissement dégressif de 175 %</span><span class="sxs-lookup"><span data-stu-id="b288a-103">175 percent reducing balance depreciation</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="b288a-104">Cette rubrique donne une vue d'ensemble de la méthode d'amortissement dégressif de 175 %.</span><span class="sxs-lookup"><span data-stu-id="b288a-104">This topic gives an overview of the 175 percent reducing balance method of depreciation.</span></span>

<span data-ttu-id="b288a-105">Si vous définissez un profil d'amortissement d'immobilisation, puis sélectionnez **Amortissement dégressif de 175 %** dans le champ **Méthode** de la page **Profils d'amortissement**, les immobilisations qui sont affectées à ce profil d'amortissement sont amorties par le même pourcentage pour chaque période d'amortissement.</span><span class="sxs-lookup"><span data-stu-id="b288a-105">When you set up a fixed asset depreciation profile and select **175% reducing balance** in the **Method** field on the **Depreciation profiles** page, fixed assets that are assigned the depreciation profile are depreciated by the same percentage in each depreciation period.</span></span> 

<span data-ttu-id="b288a-106">Pour paramétrer un amortissement dégressif de 175 %, vous devez également sélectionner des options dans les champs **Année d'amortissement** et **Fréquence** sur la page **Profils d'amortissement**.</span><span class="sxs-lookup"><span data-stu-id="b288a-106">To set up 175% reducing balance depreciation, you must also select options in the **Depreciation year** field and the **Period frequency** field on the **Depreciation profiles** page.</span></span> <span data-ttu-id="b288a-107">Les options disponibles dans le champ **Fréquence** varient en fonction de la valeur sélectionnée dans le champ **Année d'amortissement**.</span><span class="sxs-lookup"><span data-stu-id="b288a-107">The options that are available in the **Period frequency** field vary, depending on the value that is selected in the **Depreciation year** field.</span></span>

## <a name="select-a-depreciation-year"></a><span data-ttu-id="b288a-108">Sélectionner une année d'amortissement</span><span class="sxs-lookup"><span data-stu-id="b288a-108">Select a depreciation year</span></span>
<span data-ttu-id="b288a-109">Vous pouvez sélectionner soit **Calendrier** soit **Exercice** dans le champ **Année d'amortissement** de la page **Profils d'amortissement**.</span><span class="sxs-lookup"><span data-stu-id="b288a-109">You can select either **Calendar** or **Fiscal** in the **Depreciation year** field on the **Depreciation profiles** page.</span></span> <span data-ttu-id="b288a-110">La valeur par défaut est **Calendrier**.</span><span class="sxs-lookup"><span data-stu-id="b288a-110">The default value is **Calendar**.</span></span> 

<span data-ttu-id="b288a-111">Votre sélection détermine les options disponibles dans le champ **Fréquence**.</span><span class="sxs-lookup"><span data-stu-id="b288a-111">Your selection determines the options that are available in the **Period frequency** field.</span></span> <span data-ttu-id="b288a-112">Ce champ définit les dates et les montants de validation de régularisation des amortissements au cours de l'année civile.</span><span class="sxs-lookup"><span data-stu-id="b288a-112">This field defines the depreciation accrual posting dates and amounts throughout the calendar year.</span></span>

### <a name="calendar"></a><span data-ttu-id="b288a-113">Calendrier</span><span class="sxs-lookup"><span data-stu-id="b288a-113">Calendar</span></span>

<span data-ttu-id="b288a-114">Vous pouvez décider de conserver la valeur par défaut du champ **Année d'amortissement**, **Calendrier**.</span><span class="sxs-lookup"><span data-stu-id="b288a-114">You can keep the default value in the **Depreciation year** field, **Calendar**.</span></span> 

<span data-ttu-id="b288a-115">L'option **Calendrier** met à jour la base d'amortissement le 1er janvier de chaque année.</span><span class="sxs-lookup"><span data-stu-id="b288a-115">The **Calendar** option updates the depreciation base on January 1 of each year.</span></span> <span data-ttu-id="b288a-116">Généralement, la base d'amortissement est la valeur nette moins la valeur de mise au rebut.</span><span class="sxs-lookup"><span data-stu-id="b288a-116">Typically, the depreciation base is the net book value minus the scrap value.</span></span> <span data-ttu-id="b288a-117">Dans les exemples plus loin dans cette rubrique, la base d'amortissement est le numérateur de la première expression de la colonne Calcul.</span><span class="sxs-lookup"><span data-stu-id="b288a-117">In the examples later in this topic, the depreciation base is the numerator in the first expression in the calculations column.</span></span> 

<span data-ttu-id="b288a-118">Si vous sélectionnez **Calendrier** comme année d'amortissement, les options suivantes sont disponibles dans le champ **Fréquence** :</span><span class="sxs-lookup"><span data-stu-id="b288a-118">If you select **Calendar** as the depreciation year, the following options are available in the **Period frequency** field:</span></span>

-   <span data-ttu-id="b288a-119">**Annuel** valide un montant le 31 décembre.</span><span class="sxs-lookup"><span data-stu-id="b288a-119">**Yearly** posts an amount on December 31.</span></span>
-   <span data-ttu-id="b288a-120">**Mensuel** valide un montant mensuel à la fin de chaque mois du calendrier.</span><span class="sxs-lookup"><span data-stu-id="b288a-120">**Monthly** posts a monthly amount at the end of each calendar month.</span></span>
-   <span data-ttu-id="b288a-121">**Trimestriel** valide un montant trimestriel à la fin de chaque trimestre du calendrier (31 mars, 30 juin, 30 septembre et 31 décembre).</span><span class="sxs-lookup"><span data-stu-id="b288a-121">**Quarterly** posts a quarterly amount at the end of each calendar quarter (March 31, June 30, September 30, and December 31).</span></span>
-   <span data-ttu-id="b288a-122">**Semestriel** valide un montant semestriel à la fin de chaque semestre du calendrier (30 juin et 31 décembre).</span><span class="sxs-lookup"><span data-stu-id="b288a-122">**Half-Yearly** posts a half-yearly amount at the calendar half year (June 30 and December 31).</span></span>
-   <span data-ttu-id="b288a-123">**Quotidien** valide le montant d'amortissement pour la méthode d'amortissement quotidien en utilisant une transaction par jour.</span><span class="sxs-lookup"><span data-stu-id="b288a-123">**Daily** posts the depreciation amount for the daily depreciation method by using one transaction for each day.</span></span>

### <a name="fiscal"></a><span data-ttu-id="b288a-124">Exercice</span><span class="sxs-lookup"><span data-stu-id="b288a-124">Fiscal</span></span>

<span data-ttu-id="b288a-125">Si vous sélectionnez **Exercice** dans le champ **Année d'amortissement**, l'amortissement dégressif de 175 % est calculé sur la base de l'exercice du calendrier fiscal spécifié pour le registre, ou pour le calendrier fiscal sélectionné sur la page **Comptabilité**.</span><span class="sxs-lookup"><span data-stu-id="b288a-125">If you select **Fiscal** in the **Depreciation year** field, 175% reducing balance depreciation is calculated based on the fiscal year for the fiscal calendar that is specified for the book, or for the fiscal calendar that is selected on the **Ledger** page.</span></span> <span data-ttu-id="b288a-126">Les calendriers fiscaux sont paramétrés sur la page **Calendriers fiscaux**.</span><span class="sxs-lookup"><span data-stu-id="b288a-126">Fiscal calendars are set up on the **Fiscal calendars** page.</span></span> <span data-ttu-id="b288a-127">Pour plus d'informations, voir [Calendriers fiscaux, exercices, et périodes.](../budgeting/fiscal-calendars-fiscal-years-periods.md).</span><span class="sxs-lookup"><span data-stu-id="b288a-127">For more information, see [Fiscal calendars, fiscal years, and periods](../budgeting/fiscal-calendars-fiscal-years-periods.md).</span></span>

<span data-ttu-id="b288a-128">Par exemple, pour l'exercice allant du 1er juillet au 30 juin, le calcul de l'amortissement commence le 1er juillet.</span><span class="sxs-lookup"><span data-stu-id="b288a-128">For example, for the fiscal year July 1 through June 30, the depreciation calculation starts on July 1.</span></span> <span data-ttu-id="b288a-129">L'exercice peut avoir une longueur supérieure ou inférieure à 12 mois.</span><span class="sxs-lookup"><span data-stu-id="b288a-129">The fiscal year can be longer or shorter than 12 months.</span></span> <span data-ttu-id="b288a-130">L'amortissement est automatiquement ajusté en fonction de chaque période fiscale et la longueur de l'exercice suivant est déterminé par la définition des périodes fiscales sur la page **Calendriers fiscaux**.</span><span class="sxs-lookup"><span data-stu-id="b288a-130">The depreciation is automatically adjusted for each period, and the length of the next fiscal year is determined by the setup of periods on the **Fiscal calendars** page.</span></span> 

<span data-ttu-id="b288a-131">Si vous sélectionnez **Exercice** comme année d'amortissement, les options suivantes sont disponibles dans le champ **Fréquence** :</span><span class="sxs-lookup"><span data-stu-id="b288a-131">If you select **Fiscal** as the depreciation year, the following options are available in the **Period frequency** field:</span></span>

-   <span data-ttu-id="b288a-132">**Annuel** valide le montant total de l'amortissement calculé pour l'exercice le dernier jour de l'exercice.</span><span class="sxs-lookup"><span data-stu-id="b288a-132">**Yearly** posts the total amount of the depreciation that is calculated for the fiscal year on the last day of the fiscal year.</span></span>
-   <span data-ttu-id="b288a-133">**Période fiscale** calcule le montant total de l'amortissement pour l'exercice.</span><span class="sxs-lookup"><span data-stu-id="b288a-133">**Fiscal period** calculates the total amount of the depreciation for the fiscal year.</span></span> <span data-ttu-id="b288a-134">Ce montant est régularisé dans les périodes fiscales définies sur la page **Calendriers fiscaux**.</span><span class="sxs-lookup"><span data-stu-id="b288a-134">This amount is accrued into the fiscal periods that are defined on the **Fiscal calendars** page.</span></span>

## <a name="example-of-175-reducing-balance-depreciation"></a><span data-ttu-id="b288a-135">Exemple d'amortissement dégressif de 175 %</span><span class="sxs-lookup"><span data-stu-id="b288a-135">Example of 175% reducing balance depreciation</span></span>

|                                |        |
|--------------------------------|--------|
| <span data-ttu-id="b288a-136">Prix d'acquisition</span><span class="sxs-lookup"><span data-stu-id="b288a-136">Acquisition cost</span></span>               | <span data-ttu-id="b288a-137">11 000</span><span class="sxs-lookup"><span data-stu-id="b288a-137">11,000</span></span> |
| <span data-ttu-id="b288a-138">Valeur résiduelle</span><span class="sxs-lookup"><span data-stu-id="b288a-138">Salvage value</span></span>                  | <span data-ttu-id="b288a-139">1 000</span><span class="sxs-lookup"><span data-stu-id="b288a-139">1,000</span></span>  |
| <span data-ttu-id="b288a-140">Base d'amortissement</span><span class="sxs-lookup"><span data-stu-id="b288a-140">Depreciation base</span></span>              | <span data-ttu-id="b288a-141">10 000</span><span class="sxs-lookup"><span data-stu-id="b288a-141">10,000</span></span> |
| <span data-ttu-id="b288a-142">Années de durée de vie</span><span class="sxs-lookup"><span data-stu-id="b288a-142">Service life years</span></span>             | <span data-ttu-id="b288a-143">5</span><span class="sxs-lookup"><span data-stu-id="b288a-143">5</span></span>      |
| <span data-ttu-id="b288a-144">Pourcentage d'amortissement annuel</span><span class="sxs-lookup"><span data-stu-id="b288a-144">Yearly depreciation percentage</span></span> | <span data-ttu-id="b288a-145">35 %.</span><span class="sxs-lookup"><span data-stu-id="b288a-145">35%</span></span>    |

<span data-ttu-id="b288a-146">La méthode d'amortissement régressif de 175 % divise 175 % par le nombre d'années de durée de vie.</span><span class="sxs-lookup"><span data-stu-id="b288a-146">The 175% reducing balance depreciation method divides 175 percent by the service life years.</span></span> <span data-ttu-id="b288a-147">Le pourcentage ainsi obtenu est multiplié par la valeur comptable nette de l'actif afin de déterminer le montant d'amortissement pour chaque année.</span><span class="sxs-lookup"><span data-stu-id="b288a-147">That percentage will be multiplied by the net book value of the asset to determine the depreciation amount for the year.</span></span>

| <span data-ttu-id="b288a-148">Période</span><span class="sxs-lookup"><span data-stu-id="b288a-148">Period</span></span> | <span data-ttu-id="b288a-149">Calcul du montant d'amortissement annuel</span><span class="sxs-lookup"><span data-stu-id="b288a-149">Calculation of the yearly depreciation amount</span></span> | <span data-ttu-id="b288a-150">Valeur comptable</span><span class="sxs-lookup"><span data-stu-id="b288a-150">Book value</span></span>                  | <span data-ttu-id="b288a-151">Valeur comptable nette à la fin de l'exercice</span><span class="sxs-lookup"><span data-stu-id="b288a-151">Net book value at the end of the year</span></span> |
|--------|-----------------------------------------------|-----------------------------|---------------------------------------|
| <span data-ttu-id="b288a-152">Année 1</span><span class="sxs-lookup"><span data-stu-id="b288a-152">Year 1</span></span> | <span data-ttu-id="b288a-153">(11 000 – 1 000) × 35 % = 3 500</span><span class="sxs-lookup"><span data-stu-id="b288a-153">(11,000 – 1,000) × 35% = 3,500</span></span>                | <span data-ttu-id="b288a-154">11 000 – 3 500 = 7 500</span><span class="sxs-lookup"><span data-stu-id="b288a-154">11,000 – 3,500 = 7,500</span></span>      | <span data-ttu-id="b288a-155">11 000 – 1 000 – 3 500 = 6 500</span><span class="sxs-lookup"><span data-stu-id="b288a-155">11,000 – 1,000 – 3,500 = 6,500</span></span>        |
| <span data-ttu-id="b288a-156">Année 2</span><span class="sxs-lookup"><span data-stu-id="b288a-156">Year 2</span></span> | <span data-ttu-id="b288a-157">6 500 × 35 % = 2 275</span><span class="sxs-lookup"><span data-stu-id="b288a-157">6,500 × 35% = 2,275</span></span>                           | <span data-ttu-id="b288a-158">7 500 – 2 275 = 5 225</span><span class="sxs-lookup"><span data-stu-id="b288a-158">7,500 – 2,275 = 5,225</span></span>       | <span data-ttu-id="b288a-159">6 500 – 2 275 = 4 225</span><span class="sxs-lookup"><span data-stu-id="b288a-159">6,500 – 2,275 = 4,225</span></span>                 |
| <span data-ttu-id="b288a-160">Année 3</span><span class="sxs-lookup"><span data-stu-id="b288a-160">Year 3</span></span> | <span data-ttu-id="b288a-161">4 225 × 35 % = 1 478,75</span><span class="sxs-lookup"><span data-stu-id="b288a-161">4,225 × 35% = 1,478.75</span></span>                        | <span data-ttu-id="b288a-162">5 225 – 1 478,75 = 3 746,25</span><span class="sxs-lookup"><span data-stu-id="b288a-162">5,225 – 1,478.75 = 3,746.25</span></span> | <span data-ttu-id="b288a-163">4 225 – 1 478,75 = 2 746,25</span><span class="sxs-lookup"><span data-stu-id="b288a-163">4,225 – 1,478.75 = 2,746.25</span></span>           |

> [!NOTE] 
> <span data-ttu-id="b288a-164">Généralement, si le montant calculé via la méthode d'amortissement dégressif de 175 % est inférieur au montant calculé via la méthode linéaire, passer à la méthode linéaire pour la durée de vie restante reste possible.</span><span class="sxs-lookup"><span data-stu-id="b288a-164">Typically, when the amount that is calculated by using the 175% reducing balance depreciation method becomes less than the amount that would be calculated by using the straight line method, there is a conversion to the straight line method for the remaining life.</span></span>



