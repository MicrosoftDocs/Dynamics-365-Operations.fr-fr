---
title: "Effectuer un amortissement dégressif"
description: "Cet article donne une vue d'ensemble de la méthode d'amortissement dégressif."
author: twheeloc
manager: AnnBe
ms.date: 04/25/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: AssetDepreciationProfile
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 3281
ms.assetid: 1b86763d-d47c-4a6a-a9a6-d97a736750da
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: 20d28e22e4e89d0d864a0cbeaadeb568e73e223e
ms.openlocfilehash: 9416af0efdf9b33b1de559d302a1ff4c5f530dce
ms.contentlocale: fr-fr
ms.lasthandoff: 06/29/2017


---

# <a name="reduce-balance-depreciation"></a><span data-ttu-id="0e775-103">Effectuer un amortissement dégressif</span><span class="sxs-lookup"><span data-stu-id="0e775-103">Reduce balance depreciation</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="0e775-104">Cet article donne une vue d'ensemble de la méthode d'amortissement dégressif.</span><span class="sxs-lookup"><span data-stu-id="0e775-104">This article gives an overview of the Reducing balance method of depreciation.</span></span>

<span data-ttu-id="0e775-105">Si vous définissez un profil d'amortissement d'immobilisation, puis sélectionnez Dégressif dans le champ Méthode de la page Profils d'amortissement, les immobilisations auxquelles ce profil d'amortissement a été affecté sont amorties par le même pourcentage pour chaque période d'amortissement.</span><span class="sxs-lookup"><span data-stu-id="0e775-105">When you set up a fixed asset depreciation profile and select Reducing balance in the Method field in the Depreciation profiles page, the assets that have this depreciation profile assigned to them are depreciated by the same percentage in each depreciation period.</span></span>

<span data-ttu-id="0e775-106">Pour paramétrer l'amortissement dégressif, vous devez également effectuer des sélections dans l'organisateur Général de la page Profils d'amortissement.</span><span class="sxs-lookup"><span data-stu-id="0e775-106">To set up reducing balance depreciation, you must also make selections in fields on the General FastTab of the Depreciation profiles page.</span></span> <span data-ttu-id="0e775-107">Commencez par sélectionner une année dans le champ Année d'amortissement.</span><span class="sxs-lookup"><span data-stu-id="0e775-107">First, select a year in the Depreciation year field.</span></span> <span data-ttu-id="0e775-108">En fonction de la sélection, différentes options s'affichent dans le champ Période fréquence, comme expliqué dans les sections ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="0e775-108">Depending on the selection, different options appear in the Period frequency field, as explained in the following sections.</span></span> 

<span data-ttu-id="0e775-109">Vous devez également entrer une valeur dans le champ Pourcentage du profil d'amortissement.</span><span class="sxs-lookup"><span data-stu-id="0e775-109">You must also enter a value in the Percentage field for the depreciation profile.</span></span> <span data-ttu-id="0e775-110">Si vous sélectionnez l'option Amortissement complet, la base d'amortissement restante est prise dans la dernière période d'amortissement et peut représenter un montant important.</span><span class="sxs-lookup"><span data-stu-id="0e775-110">If you select the Full depreciation option, the remaining depreciation basis is taken in the last depreciation period and could be a large amount.</span></span> <span data-ttu-id="0e775-111">Certains pays/régions n'utilisent pas de basculement vers une méthode linéaire.</span><span class="sxs-lookup"><span data-stu-id="0e775-111">Some countries/regions do not use a switchover to a straight line method.</span></span> <span data-ttu-id="0e775-112">Un basculement se produit lorsque le montant de la méthode alternative d'amortissement est supérieur ou égal au montant du profil d'amortissement principal, et que le montant d'amortissement pris en compte est le montant alternatif.</span><span class="sxs-lookup"><span data-stu-id="0e775-112">Switchover occurs when the alternative depreciation method amount is greater than or equal to the primary depreciation profile amount, and the depreciation amount taken is the alternative method amount.</span></span> 

<span data-ttu-id="0e775-113">Puisqu'une immobilisation ne sera jamais totalement amortie sur la base d'un calcul de pourcentage, vous devez sélectionner l'option Amortissement complet pour amortir complètement une immobilisation.</span><span class="sxs-lookup"><span data-stu-id="0e775-113">Because an asset will never be fully depreciated based on a percentage calculation, you must select the Full depreciation option to fully depreciate an asset.</span></span>

## <a name="select-a-depreciation-year"></a><span data-ttu-id="0e775-114">Sélection d'une année d'amortissement</span><span class="sxs-lookup"><span data-stu-id="0e775-114">Select a depreciation year</span></span>
<span data-ttu-id="0e775-115">Vous pouvez sélectionner soit Calendrier soit Exercice dans le champ Année d'amortissement de la page Profils d'amortissement.</span><span class="sxs-lookup"><span data-stu-id="0e775-115">You can select either Calendar or Fiscal in the Depreciation year field in the Depreciation profiles page.</span></span> <span data-ttu-id="0e775-116">La sélection effectuée détermine les options disponibles dans le champ Période fréquence.</span><span class="sxs-lookup"><span data-stu-id="0e775-116">The selection defines the options that are available in the Period frequency field.</span></span> <span data-ttu-id="0e775-117">L'option par défaut est Calendrier.</span><span class="sxs-lookup"><span data-stu-id="0e775-117">The default option is Calendar.</span></span>

### <a name="calendar"></a><span data-ttu-id="0e775-118">Calendrier</span><span class="sxs-lookup"><span data-stu-id="0e775-118">Calendar</span></span>

<span data-ttu-id="0e775-119">L'option Calendrier met à jour la base d'amortissement (généralement la valeur comptable nette moins la valeur de mise au rebut) le premier janvier de chaque année.</span><span class="sxs-lookup"><span data-stu-id="0e775-119">The Calendar option updates the depreciation base, which is typically the net book value minus the scrap value, on January 1 of each year.</span></span> <span data-ttu-id="0e775-120">Dans l'exemple d'amortissement dégressif donné plus loin dans cette rubrique, la base d'amortissement est le numérateur de la première expression des calculs de la colonne de calcul.</span><span class="sxs-lookup"><span data-stu-id="0e775-120">In the reducing balance depreciation example later in this topic, the depreciation base is the numerator in the first expression in the calculations column.</span></span> 

<span data-ttu-id="0e775-121">Si vous sélectionnez Calendrier, les options suivantes sont disponibles dans le champ Période fréquence qui définit les dates et les montants de validation de régularisation des amortissements au cours de l'année civile :</span><span class="sxs-lookup"><span data-stu-id="0e775-121">If you select Calendar, the following options are available in the Period frequency field, which defines the depreciation accrual posting dates and amounts throughout the calendar year:</span></span>

-   <span data-ttu-id="0e775-122">L'option Annuel valide annuellement le 31 décembre.</span><span class="sxs-lookup"><span data-stu-id="0e775-122">Yearly posts on December 31.</span></span>
-   <span data-ttu-id="0e775-123">L'option Mensuellement valide un montant mensuel à la fin de chaque mois du calendrier.</span><span class="sxs-lookup"><span data-stu-id="0e775-123">Monthly posts a monthly amount at the end of each calendar month.</span></span>
-   <span data-ttu-id="0e775-124">L'option Trimestriel valide un montant trimestriel à la fin de chaque trimestre du calendrier (31 mars, 30 juin, 30 septembre et 31 décembre).</span><span class="sxs-lookup"><span data-stu-id="0e775-124">Quarterly posts a quarterly amount at the end of each calendar quarter (March 31, June 30, September 30, and December 31).</span></span>
-   <span data-ttu-id="0e775-125">L'option Semestriel valide un montant semestriel à la fin de chaque semestre du calendrier (30 juin et 31 décembre).</span><span class="sxs-lookup"><span data-stu-id="0e775-125">Half-Yearly posts a half-yearly amount at the end of each calendar half-year (June 30 and December 31).</span></span>
-   <span data-ttu-id="0e775-126">L'option Quotidien valide le montant d'amortissement pour la méthode d'amortissement quotidien à l'aide d'une transaction par jour.</span><span class="sxs-lookup"><span data-stu-id="0e775-126">Daily posts the depreciation amount for the daily depreciation method using one transaction for each day.</span></span>

<span data-ttu-id="0e775-127">Par exemple, si vous sélectionnez Annuel, l'amortissement annuel n'est validé qu'une seule fois, le 31 décembre de chaque année.</span><span class="sxs-lookup"><span data-stu-id="0e775-127">For example, if you select Yearly, the yearly depreciation is posted only one time, on December 31 of each year.</span></span> <span data-ttu-id="0e775-128">Si vous sélectionnez Mensuellement, l'amortissement mensuel est validé chaque mois comme 1/12 du montant d'amortissement annuel.</span><span class="sxs-lookup"><span data-stu-id="0e775-128">If you select Monthly, the monthly depreciation is posted each month as 1/12 of the yearly depreciation amount.</span></span>

### <a name="fiscal"></a><span data-ttu-id="0e775-129">Exercice</span><span class="sxs-lookup"><span data-stu-id="0e775-129">Fiscal</span></span>

<span data-ttu-id="0e775-130">Si vous sélectionnez Exercice dans le champ Année d'amortissement, la méthode d'amortissement linéaire est utilisée.</span><span class="sxs-lookup"><span data-stu-id="0e775-130">If you select Fiscal in the Depreciation year field, the straight line depreciation method is used.</span></span> <span data-ttu-id="0e775-131">Elle est calculée en fonction de l'exercice, qui est paramétré dans la page Calendriers fiscaux pour le calendrier fiscal sélectionné dans la page Comptabilité .</span><span class="sxs-lookup"><span data-stu-id="0e775-131">It is calculated based on the fiscal year, which is set up in the Fiscal calendars page for the fiscal calendar that is selected in the Ledger page.</span></span> <span data-ttu-id="0e775-132">Par exemple, pour l'exercice allant du 1er juillet au 30 juin, le calcul de l'amortissement commence le 1er juillet.</span><span class="sxs-lookup"><span data-stu-id="0e775-132">For example, for fiscal year July 1 through June 30, the depreciation calculation starts on July 1.</span></span> <span data-ttu-id="0e775-133">L'exercice peut avoir une longueur supérieure ou inférieure à 12 mois.</span><span class="sxs-lookup"><span data-stu-id="0e775-133">The fiscal year can be longer or shorter than 12 months.</span></span> <span data-ttu-id="0e775-134">L'amortissement est ajusté en fonction de chaque période fiscale.</span><span class="sxs-lookup"><span data-stu-id="0e775-134">The depreciation is adjusted for each fiscal period.</span></span> <span data-ttu-id="0e775-135">La longueur de l'exercice suivant est basée sur les périodes fiscales paramétrées lors de la création d'un exercice dans la page Calendriers fiscaux.</span><span class="sxs-lookup"><span data-stu-id="0e775-135">The length of the next fiscal year is based on the fiscal periods that you set up when you create a new fiscal year in the Fiscal calendars page.</span></span>


<span data-ttu-id="0e775-136">Si vous sélectionnez Fiscal, les options suivantes sont disponibles dans le champ Période fréquence :</span><span class="sxs-lookup"><span data-stu-id="0e775-136">If you select Fiscal, the following options are available in the Period frequency field:</span></span>

-   <span data-ttu-id="0e775-137">Annuel valide le montant total de l'amortissement calculé pour l'exercice comme montant unique le dernier jour de l'exercice.</span><span class="sxs-lookup"><span data-stu-id="0e775-137">Yearly posts the total amount of the depreciation calculated for the fiscal year as one amount on the last day of the fiscal year.</span></span>
-   <span data-ttu-id="0e775-138">Période fiscale valide le montant total de l'amortissement calculé pour l'exercice, qui est provisionné dans les périodes fiscales définies pour le calendrier fiscal sélectionné dans la page Comptabilité, ou pour le calendrier fiscal sélectionné pour le registre pour une immobilisation.</span><span class="sxs-lookup"><span data-stu-id="0e775-138">Fiscal period posts the total amount of the depreciation calculated for the fiscal year, which is accrued into the fiscal periods that are defined for the fiscal calendar that is selected in the Ledger page, or for the fiscal calendar that is selected for the book for a fixed asset.</span></span>

## <a name="example-of-reducing-balance-depreciation"></a><span data-ttu-id="0e775-139">Exemple d'amortissement dégressif</span><span class="sxs-lookup"><span data-stu-id="0e775-139">Example of reducing balance depreciation</span></span>

<span data-ttu-id="0e775-140">Supposons que le prix d'acquisition d'immobilisation soit 11 000, la valeur de mise au rebut 1 000 et le pourcentage d'amortissement 30.</span><span class="sxs-lookup"><span data-stu-id="0e775-140">Suppose that the fixed asset acquisition price is 11,000, the scrap value is 1,000, and the depreciation percentage factor is 30.</span></span> 

<span data-ttu-id="0e775-141">En utilisant la méthode d'amortissement dégressif, les 30 % de la base d'amortissement (valeur nette moins valeur de mise au rebut) sont calculés à la fin de la période d'amortissement précédente.</span><span class="sxs-lookup"><span data-stu-id="0e775-141">Using the Reducing balance method, 30 percent of the depreciation base (net book value minus scrap value) is calculated at the end of the previous depreciation period.</span></span> <span data-ttu-id="0e775-142">L'amortissement pour les trois premières années est indiqué dans le tableau suivant.</span><span class="sxs-lookup"><span data-stu-id="0e775-142">Depreciation for the first three years is shown in the following table.</span></span>

| <span data-ttu-id="0e775-143">Période</span><span class="sxs-lookup"><span data-stu-id="0e775-143">Period</span></span> | <span data-ttu-id="0e775-144">Calcul du montant d'amortissement annuel</span><span class="sxs-lookup"><span data-stu-id="0e775-144">Calculation of yearly depreciation amount</span></span> | <span data-ttu-id="0e775-145">Valeur comptable nette à la fin de l'exercice</span><span class="sxs-lookup"><span data-stu-id="0e775-145">Net book value at the end of the year</span></span> |
|--------|-------------------------------------------|---------------------------------------|
| <span data-ttu-id="0e775-146">Année 1</span><span class="sxs-lookup"><span data-stu-id="0e775-146">Year 1</span></span> | <span data-ttu-id="0e775-147">(11 000 - 1 000) \* 30 % = 3 000</span><span class="sxs-lookup"><span data-stu-id="0e775-147">(11,000 - 1,000) \* 30% = 3,000</span></span>           | <span data-ttu-id="0e775-148">(11 000 - 1 000) - 3 000 = 7 000</span><span class="sxs-lookup"><span data-stu-id="0e775-148">(11,000 - 1,000) - 3,000 = 7,000</span></span>      |
| <span data-ttu-id="0e775-149">Année 2</span><span class="sxs-lookup"><span data-stu-id="0e775-149">Year 2</span></span> | <span data-ttu-id="0e775-150">(7 000 - 1 000) \* 30 % = 1 800</span><span class="sxs-lookup"><span data-stu-id="0e775-150">(7,000 - 1,000) \* 30% = 1,800</span></span>            | <span data-ttu-id="0e775-151">(7 000 -1 800) = 5 200</span><span class="sxs-lookup"><span data-stu-id="0e775-151">(7,000 -1,800) = 5,200</span></span>                |
| <span data-ttu-id="0e775-152">Année 3</span><span class="sxs-lookup"><span data-stu-id="0e775-152">Year 3</span></span> | <span data-ttu-id="0e775-153">(5 200 - 1 000) \* 30 % = 1 260</span><span class="sxs-lookup"><span data-stu-id="0e775-153">(5,200 - 1,000) \* 30% = 1,260</span></span>            | <span data-ttu-id="0e775-154">(5 200 - 1 260) = 3 940</span><span class="sxs-lookup"><span data-stu-id="0e775-154">(5,200 - 1,260) = 3,940</span></span>               |

 
-






