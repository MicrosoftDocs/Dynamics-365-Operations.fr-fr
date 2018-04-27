---
title: "Paramétrage des taux d'intérêt pour un code intérêt"
description: "Les codes intérêt contiennent des paramètres qui déterminent quand les intérêts sont facturés et comment ils sont calculés sur les comptes qui présentent des retards."
author: ShivamPandey-msft
manager: AnnBe
ms.date: 01/12/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: Interest
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 59402
ms.assetid: 3b945333-1eaf-4658-ab5a-1a7791a7eb40
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: c0e80bae4716d2b12f515f38d3b641de24680571
ms.contentlocale: fr-fr
ms.lasthandoff: 04/13/2018

---

# <a name="set-up-interest-rates-for-an-interest-code"></a><span data-ttu-id="c0480-103">Paramétrage des taux d'intérêt pour un code intérêt</span><span class="sxs-lookup"><span data-stu-id="c0480-103">Set up interest rates for an interest code</span></span>

[!INCLUDE [banner](../includes/banner.md)]

<span data-ttu-id="c0480-104">Les codes intérêt contiennent des paramètres qui déterminent quand les intérêts sont facturés et comment ils sont calculés sur les comptes qui présentent des retards.</span><span class="sxs-lookup"><span data-stu-id="c0480-104">Interest codes contain settings that determine when interest is charged and how it is calculated on overdue accounts.</span></span>

<span data-ttu-id="c0480-105">Vous pouvez paramétrer un seul code intérêt et l'appliquer à plusieurs profils de validation client, codes de facturation ou à des lignes de factures spécifiques.</span><span class="sxs-lookup"><span data-stu-id="c0480-105">You can set up a single interest code and apply it to multiple customer posting profiles, billing codes, or to specific invoice lines.</span></span> <span data-ttu-id="c0480-106">Lorsque les détails du code intérêt sont modifiés, toutes les fonctionnalités qui utilisent le code appliquent automatiquement les modifications aux nouvelles transactions.</span><span class="sxs-lookup"><span data-stu-id="c0480-106">When the interest code details are changed, all features that use the code will automatically implement the changes on new transactions.</span></span> <span data-ttu-id="c0480-107">Vous pouvez paramétrer deux types de taux pour chaque code intérêt :</span><span class="sxs-lookup"><span data-stu-id="c0480-107">For each interest code, you can set up two types of rates:</span></span>
-   <span data-ttu-id="c0480-108">Taux pour les intérêts créditeurs − Ils représentent des revenus gagnés en facturant des intérêts sur les factures ou les notes d'intérêt.</span><span class="sxs-lookup"><span data-stu-id="c0480-108">Rates for interest earnings − These represent revenue that is earned by charging interest on invoices or interest notes.</span></span>
-   <span data-ttu-id="c0480-109">Taux pour les intérêts payés − Ils représentent un coût payé pour les intérêts sur les avoirs.</span><span class="sxs-lookup"><span data-stu-id="c0480-109">Rates for interest payments − These represent a cost that is paid for interest on credit notes.</span></span>

<span data-ttu-id="c0480-110">Ces deux types de taux peuvent exister simultanément et dans le même code intérêt.</span><span class="sxs-lookup"><span data-stu-id="c0480-110">Both of these rate types can exist at the same time and in the same interest code.</span></span> <span data-ttu-id="c0480-111">Les taux d'intérêt peuvent être basés sur trois types de calcul :</span><span class="sxs-lookup"><span data-stu-id="c0480-111">Interest rates can be based on three calculation types:</span></span>
-   <span data-ttu-id="c0480-112">Intérêts par pourcentage.</span><span class="sxs-lookup"><span data-stu-id="c0480-112">Interest by percentage.</span></span>
-   <span data-ttu-id="c0480-113">Intérêts par montant.</span><span class="sxs-lookup"><span data-stu-id="c0480-113">Interest by amount.</span></span>
-   <span data-ttu-id="c0480-114">Intérêts par tranche, qui résulte en un pourcentage ou montant unique.</span><span class="sxs-lookup"><span data-stu-id="c0480-114">Interest by range, which results in a single percentage or amount.</span></span>

<span data-ttu-id="c0480-115">Lorsqu'un code intérêt est utilisé pour calculer des intérêts, une note d'intérêt séparée est créée pour chaque taux d'intérêt qui prend effet lorsque le paiement est effectué après la date d'échéance de la transaction.</span><span class="sxs-lookup"><span data-stu-id="c0480-115">When an interest code is used to calculate interest, a separate interest note is created for each interest rate that is in effect during the time that the payment has exceeded the transaction due date.</span></span> <span data-ttu-id="c0480-116">L'onglet **Rémunérations** de la page **Code intérêt** vous permet de paramétrer les taux d'intérêt pour les intérêts que vous obtenez en facturant un intérêt.</span><span class="sxs-lookup"><span data-stu-id="c0480-116">You use the **Earnings** tab on the **Interest code** page to set up interest rates for interest that you earn by charging interest.</span></span> <span data-ttu-id="c0480-117">L'onglet **Paiements** vous permet de paramétrer les taux d'intérêt pour les intérêts que vous payez.</span><span class="sxs-lookup"><span data-stu-id="c0480-117">Use the **Payments** tab to set up interest rates for interest that you pay.</span></span>

## <a name="interest-rates-based-on-a-percentage"></a><span data-ttu-id="c0480-118">Taux d'intérêt basés sur un pourcentage</span><span class="sxs-lookup"><span data-stu-id="c0480-118">Interest rates based on a percentage</span></span>
<span data-ttu-id="c0480-119">Vous pouvez paramétrer des taux d'intérêt qui calculent un pourcentage spécifié.</span><span class="sxs-lookup"><span data-stu-id="c0480-119">You can set up interest rates that calculate a specified percentage.</span></span>

- <span data-ttu-id="c0480-120">Le montant des intérêts s'applique à toutes les devises.</span><span class="sxs-lookup"><span data-stu-id="c0480-120">Interest amount applies to all currencies.</span></span>
- <span data-ttu-id="c0480-121">Vous pouvez spécifier des limites du montant des intérêts facultatives.</span><span class="sxs-lookup"><span data-stu-id="c0480-121">Optional interest amount limits can be entered.</span></span>
- <span data-ttu-id="c0480-122">L'option <strong>Pourcentage</strong> est sélectionnée** <strong>dans le champ **Calculer les intérêts sur base de</strong> de la page <strong>Paramétrer les codes intérêt</strong>.</span><span class="sxs-lookup"><span data-stu-id="c0480-122"><strong>Percentage</strong> is selected** <strong>in the **Calculate interest based on</strong> field on the <strong>Set up Interest codes</strong> page.</span></span>

<span data-ttu-id="c0480-123">Par exemple, pour paramétrer un code intérêt qui évalue 5 % d'intérêts pour chaque période de deux mois après la date d'échéance de la transaction pour le paiement de la facture, entrez 2 dans le champ **Calculer les intérêts tous les** et sélectionnez **Mois**.</span><span class="sxs-lookup"><span data-stu-id="c0480-123">For example, to set up an interest code that assesses 5 percent interest for every two months that the invoice payment exceeds the transaction due date, you would enter 2 in the **Calculate interest every** field and select **Month**.</span></span>

## <a name="interest-rates-based-on-amounts"></a><span data-ttu-id="c0480-124">Taux d'intérêt basés sur des montants</span><span class="sxs-lookup"><span data-stu-id="c0480-124">Interest rates based on amounts</span></span>
<span data-ttu-id="c0480-125">Vous pouvez paramétrer des taux d'intérêt qui calculent un montant spécifié par devise.</span><span class="sxs-lookup"><span data-stu-id="c0480-125">You can set up interest rates that calculate a specified amount per currency.</span></span>
- <span data-ttu-id="c0480-126">Un montant des intérêts est spécifié pour chaque devise dans le code intérêt.</span><span class="sxs-lookup"><span data-stu-id="c0480-126">An interest amount is specified for each currency in the interest code.</span></span>
- <span data-ttu-id="c0480-127">Vous pouvez spécifier des limites du montant des intérêts facultatives.</span><span class="sxs-lookup"><span data-stu-id="c0480-127">Optional interest amount limits can be entered.</span></span>
- <span data-ttu-id="c0480-128">L'option <strong>Montant** est sélectionnée dans le champ **Calculer les intérêts sur base de</strong> de la page <strong>Paramétrer les codes intérêt</strong>.</span><span class="sxs-lookup"><span data-stu-id="c0480-128"><strong>Amount **is selected in the **Calculate interest based on</strong> field on the <strong>Set up Interest codes</strong> page.</span></span>

<span data-ttu-id="c0480-129">Par exemple, pour paramétrer un code intérêt qui évalue un intérêt de 25,00 pour chaque période de 20 jours après la date d'échéance de la transaction pour le paiement de la facture, entrez 20 dans le champ **Calculer les intérêts tous les** et sélectionnez **Jour**.</span><span class="sxs-lookup"><span data-stu-id="c0480-129">For example, to set up an interest code that assesses interest of 25.00 for every 20 days that the invoice payment exceeds the transaction due date, you would enter 20 in the **Calculate interest every** field and select **Day**.</span></span>

## <a name="interest-rates-based-on-ranges"></a><span data-ttu-id="c0480-130">Taux d'intérêt basés sur des plages</span><span class="sxs-lookup"><span data-stu-id="c0480-130">Interest rates based on ranges</span></span>
<span data-ttu-id="c0480-131">Vous pouvez paramétrer des taux d'intérêt qui varient selon le montant en retard, le nombre de jours de retard de paiement, ou le nombre de mois de retard de paiement.</span><span class="sxs-lookup"><span data-stu-id="c0480-131">You can set up interest rates that vary depending on the overdue amount, the number of days that the amount is late, or the number of months that the amount is late.</span></span>
-   <span data-ttu-id="c0480-132">L'onglet **Bénéfices par devise** permet de définir des paramètres d'intérêt spécifiques pour chaque devise.</span><span class="sxs-lookup"><span data-stu-id="c0480-132">You can use the **Earnings by Currency** tab to define specific interest settings for each currency.</span></span> <span data-ttu-id="c0480-133">Il vous permet également de définir la tranche.</span><span class="sxs-lookup"><span data-stu-id="c0480-133">This is also where you will define the range.</span></span>
-   <span data-ttu-id="c0480-134">Utilisez le bouton **Plages** pour ajouter des lignes qui représentent les plages à paramétrer.</span><span class="sxs-lookup"><span data-stu-id="c0480-134">Use the **Ranges** button to add lines that represent the ranges that you want to set up.</span></span> <span data-ttu-id="c0480-135">La valeur **De** représente le début de la plage et le nombre **Valeur des intérêts** représente soit un pourcentage soit un montant, en fonction de la sélection du champ **Calculer les intérêts sur base de** de la page **Paramétrer les codes intérêt**.</span><span class="sxs-lookup"><span data-stu-id="c0480-135">The **From** value represents the beginning of the range and the **Interest value** number represents either a percentage or an amount, depending on the selection in the **Calculate interest based on** field on the **Set up Interest codes** page.</span></span>

## <a name="example-1-interest-by-range--amount"></a><span data-ttu-id="c0480-136">Exemple 1 : Intérêts par tranche = montant</span><span class="sxs-lookup"><span data-stu-id="c0480-136">Example 1: Interest by range = Amount</span></span>
<span data-ttu-id="c0480-137">Vous paramétrez un code intérêt qui évalue un intérêt une fois pour chaque période de trois mois après la date d'échéance de la transaction pour le paiement de la facture.</span><span class="sxs-lookup"><span data-stu-id="c0480-137">You set up an interest code that assesses interest one time for every three months that the invoice payment exceeds the transaction due date.</span></span> <span data-ttu-id="c0480-138">Vous souhaitez baser le calcul sur une valeur d'intérêts par pourcentage, selon des intervalles de montants par paliers.</span><span class="sxs-lookup"><span data-stu-id="c0480-138">You want to base the calculation on a percentage interest value, according to stepped amount intervals.</span></span> <span data-ttu-id="c0480-139">La valeur des intérêts est 1 % pour les montants de facture jusqu'à 1 000,00, 2 % pour les montants compris entre 1 001,00 et 5 000,00, et 3 % pour les montants supérieurs à 5 000,00.</span><span class="sxs-lookup"><span data-stu-id="c0480-139">The interest value will be 1 percent for invoice amounts up to 1,000.00, 2 percent for amounts from 1,001.00 to 5,000.00, and 3 percent for amounts larger than 5,000.00.</span></span> <span data-ttu-id="c0480-140">Vous paramétrez les valeurs du champ Code intérêt comme suit.</span><span class="sxs-lookup"><span data-stu-id="c0480-140">You set up the interest code field values as follows.</span></span>

| <span data-ttu-id="c0480-141">**Nom de champ**</span><span class="sxs-lookup"><span data-stu-id="c0480-141">**Field name**</span></span>                  | <span data-ttu-id="c0480-142">**Valeur de champ**</span><span class="sxs-lookup"><span data-stu-id="c0480-142">**Field value**</span></span> |
|---------------------------------|-----------------|
| <span data-ttu-id="c0480-143">**Code intérêt**</span><span class="sxs-lookup"><span data-stu-id="c0480-143">**Interest code**</span></span>               | <span data-ttu-id="c0480-144">3M%ByAmt</span><span class="sxs-lookup"><span data-stu-id="c0480-144">3M%ByAmt</span></span>        |
| <span data-ttu-id="c0480-145">**Calculer chaque intérêt**</span><span class="sxs-lookup"><span data-stu-id="c0480-145">**Calculate interest every**</span></span>    | <span data-ttu-id="c0480-146">3/Mois</span><span class="sxs-lookup"><span data-stu-id="c0480-146">3/Month</span></span>         |
| <span data-ttu-id="c0480-147">**Intérêts par tranche**</span><span class="sxs-lookup"><span data-stu-id="c0480-147">**Interest by range**</span></span>           | <span data-ttu-id="c0480-148">Montant</span><span class="sxs-lookup"><span data-stu-id="c0480-148">Amount</span></span>          |
| <span data-ttu-id="c0480-149">**Calculer les intérêts sur base de**</span><span class="sxs-lookup"><span data-stu-id="c0480-149">**Calculate interest based on**</span></span> | <span data-ttu-id="c0480-150">Pourcentage</span><span class="sxs-lookup"><span data-stu-id="c0480-150">Percentage</span></span>      |

<span data-ttu-id="c0480-151">Vous devez paramétrer les informations de tranches comme suit.</span><span class="sxs-lookup"><span data-stu-id="c0480-151">You set up the range information as follows.</span></span>

| <span data-ttu-id="c0480-152">**Valeur de début**</span><span class="sxs-lookup"><span data-stu-id="c0480-152">**From value**</span></span> | <span data-ttu-id="c0480-153">**Valeur des intérêts**</span><span class="sxs-lookup"><span data-stu-id="c0480-153">**Interest value**</span></span> |
|----------------|--------------------|
| <span data-ttu-id="c0480-154">0</span><span class="sxs-lookup"><span data-stu-id="c0480-154">0</span></span>              | <span data-ttu-id="c0480-155">1</span><span class="sxs-lookup"><span data-stu-id="c0480-155">1</span></span>                  |
| <span data-ttu-id="c0480-156">1,001</span><span class="sxs-lookup"><span data-stu-id="c0480-156">1,001</span></span>          | <span data-ttu-id="c0480-157">2</span><span class="sxs-lookup"><span data-stu-id="c0480-157">2</span></span>                  |
| <span data-ttu-id="c0480-158">5,001</span><span class="sxs-lookup"><span data-stu-id="c0480-158">5,001</span></span>          | <span data-ttu-id="c0480-159">3</span><span class="sxs-lookup"><span data-stu-id="c0480-159">3</span></span>                  |


## <a name="example-2-interest-by-range--days"></a><span data-ttu-id="c0480-160">Exemple 2 : Intérêts par tranche = jours</span><span class="sxs-lookup"><span data-stu-id="c0480-160">Example 2: Interest by range = Days</span></span>
--------------------------------------------------

<span data-ttu-id="c0480-161">Vous paramétrez un code intérêt qui évalue un intérêt une fois pour chaque période de 15 jours après la date d'échéance de la transaction pour le paiement de la facture.</span><span class="sxs-lookup"><span data-stu-id="c0480-161">You set up an interest code that assesses interest one time for every 15 days that the invoice payment exceeds the transaction due date.</span></span> <span data-ttu-id="c0480-162">Vous souhaitez baser le calcul sur une valeur d'intérêts par montant, selon des intervalles de jours par paliers.</span><span class="sxs-lookup"><span data-stu-id="c0480-162">You want to base the calculation on an amount interest value, according to stepped day intervals.</span></span> <span data-ttu-id="c0480-163">La valeur des intérêts est 10,00 par période de 15 jours pendant les 60 premiers jours, 15,00 par période de 15 jours pendant les jours 61 à 90 et 20,00 par période de 15 jours après le 91e jour.</span><span class="sxs-lookup"><span data-stu-id="c0480-163">The interest value will be 10.00 per 15 days during the first 60 days, 15.00 per 15 days during days 61 to 90, and 20.00 per 15 days from day 91 and after.</span></span> <span data-ttu-id="c0480-164">Vous paramétrez les valeurs du champ Code intérêt comme suit.</span><span class="sxs-lookup"><span data-stu-id="c0480-164">You set up the interest code field values as follows.</span></span>

| <span data-ttu-id="c0480-165">**Nom de champ**</span><span class="sxs-lookup"><span data-stu-id="c0480-165">**Field name**</span></span>                  | <span data-ttu-id="c0480-166">**Valeur de champ**</span><span class="sxs-lookup"><span data-stu-id="c0480-166">**Field value**</span></span> |
|---------------------------------|-----------------|
| <span data-ttu-id="c0480-167">**Code intérêt**</span><span class="sxs-lookup"><span data-stu-id="c0480-167">**Interest code**</span></span>               | <span data-ttu-id="c0480-168">15DAmtXDay</span><span class="sxs-lookup"><span data-stu-id="c0480-168">15DAmtXDay</span></span>      |
| <span data-ttu-id="c0480-169">**Calculer chaque intérêt**</span><span class="sxs-lookup"><span data-stu-id="c0480-169">**Calculate interest every**</span></span>    | <span data-ttu-id="c0480-170">15/Jour</span><span class="sxs-lookup"><span data-stu-id="c0480-170">15/Day</span></span>          |
| <span data-ttu-id="c0480-171">**Intérêts par tranche**</span><span class="sxs-lookup"><span data-stu-id="c0480-171">**Interest by range**</span></span>           | <span data-ttu-id="c0480-172">Jours</span><span class="sxs-lookup"><span data-stu-id="c0480-172">Days</span></span>            |
| <span data-ttu-id="c0480-173">**Calculer les intérêts sur base de**</span><span class="sxs-lookup"><span data-stu-id="c0480-173">**Calculate interest based on**</span></span> | <span data-ttu-id="c0480-174">Montant</span><span class="sxs-lookup"><span data-stu-id="c0480-174">Amount</span></span>          |

<span data-ttu-id="c0480-175">Vous devez paramétrer les informations de tranches comme suit.</span><span class="sxs-lookup"><span data-stu-id="c0480-175">You set up the range information as follows.</span></span>

| <span data-ttu-id="c0480-176">**Valeur de début**</span><span class="sxs-lookup"><span data-stu-id="c0480-176">**From value**</span></span> | <span data-ttu-id="c0480-177">**Valeur des intérêts**</span><span class="sxs-lookup"><span data-stu-id="c0480-177">**Interest value**</span></span> |
|----------------|--------------------|
| <span data-ttu-id="c0480-178">0</span><span class="sxs-lookup"><span data-stu-id="c0480-178">0</span></span>              | <span data-ttu-id="c0480-179">10</span><span class="sxs-lookup"><span data-stu-id="c0480-179">10</span></span>                 |
| <span data-ttu-id="c0480-180">61</span><span class="sxs-lookup"><span data-stu-id="c0480-180">61</span></span>             | <span data-ttu-id="c0480-181">15</span><span class="sxs-lookup"><span data-stu-id="c0480-181">15</span></span>                 |
| <span data-ttu-id="c0480-182">91</span><span class="sxs-lookup"><span data-stu-id="c0480-182">91</span></span>             | <span data-ttu-id="c0480-183">20</span><span class="sxs-lookup"><span data-stu-id="c0480-183">20</span></span>                 |


## <a name="example-3-interest-by-range--months"></a><span data-ttu-id="c0480-184">Exemple 3 : Intérêts par tranche = mois</span><span class="sxs-lookup"><span data-stu-id="c0480-184">Example 3: Interest by range = Months</span></span>
----------------------------------------------------

<span data-ttu-id="c0480-185">Vous paramétrez un code intérêt qui évalue un intérêt une fois pour chaque mois après la date d'échéance de la transaction pour le paiement de la facture.</span><span class="sxs-lookup"><span data-stu-id="c0480-185">You set up an interest code that assesses interest one time for every month that the invoice payment exceeds the transaction due date.</span></span> <span data-ttu-id="c0480-186">Vous souhaitez baser le calcul sur une valeur d'intérêts par pourcentage, selon des intervalles de mois par paliers.</span><span class="sxs-lookup"><span data-stu-id="c0480-186">You want to base the calculation on a percentage interest value, according to stepped month intervals.</span></span> <span data-ttu-id="c0480-187">La valeur des intérêts sera de 1,5 % par mois pendant les trois premiers mois de retard, 2,0 % par mois pour les trois mois suivants, et 2,5 % par mois au delà des six premiers mois.</span><span class="sxs-lookup"><span data-stu-id="c0480-187">The interest value will be 1.5 percent per month for the first three overdue months, 2.0 percent per month for the second three months, and 2.5 percent per month for each month beyond the first six months.</span></span> <span data-ttu-id="c0480-188">Vous paramétrez les valeurs du champ Code intérêt comme suit.</span><span class="sxs-lookup"><span data-stu-id="c0480-188">You set up the interest code field values as follows.</span></span>

| <span data-ttu-id="c0480-189">**Nom de champ**</span><span class="sxs-lookup"><span data-stu-id="c0480-189">**Field name**</span></span>                  | <span data-ttu-id="c0480-190">**Valeur de champ**</span><span class="sxs-lookup"><span data-stu-id="c0480-190">**Field value**</span></span> |
|---------------------------------|-----------------|
| <span data-ttu-id="c0480-191">**Code intérêt**</span><span class="sxs-lookup"><span data-stu-id="c0480-191">**Interest code**</span></span>               | <span data-ttu-id="c0480-192">1M%ByMth</span><span class="sxs-lookup"><span data-stu-id="c0480-192">1M%ByMth</span></span>        |
| <span data-ttu-id="c0480-193">**Calculer chaque intérêt**</span><span class="sxs-lookup"><span data-stu-id="c0480-193">**Calculate interest every**</span></span>    | <span data-ttu-id="c0480-194">1/Mois</span><span class="sxs-lookup"><span data-stu-id="c0480-194">1/Month</span></span>         |
| <span data-ttu-id="c0480-195">**Intérêts par tranche**</span><span class="sxs-lookup"><span data-stu-id="c0480-195">**Interest by range**</span></span>           | <span data-ttu-id="c0480-196">Mois</span><span class="sxs-lookup"><span data-stu-id="c0480-196">Months</span></span>          |
| <span data-ttu-id="c0480-197">**Calculer les intérêts sur base de**</span><span class="sxs-lookup"><span data-stu-id="c0480-197">**Calculate interest based on**</span></span> | <span data-ttu-id="c0480-198">Pourcentage</span><span class="sxs-lookup"><span data-stu-id="c0480-198">Percentage</span></span>      |

<span data-ttu-id="c0480-199">Vous devez paramétrer les informations de tranches comme suit.</span><span class="sxs-lookup"><span data-stu-id="c0480-199">You set up the range information as follows.</span></span>

| <span data-ttu-id="c0480-200">**Valeur de début**</span><span class="sxs-lookup"><span data-stu-id="c0480-200">**From value**</span></span> | <span data-ttu-id="c0480-201">**Valeur des intérêts**</span><span class="sxs-lookup"><span data-stu-id="c0480-201">**Interest value**</span></span> |
|----------------|--------------------|
| <span data-ttu-id="c0480-202">0</span><span class="sxs-lookup"><span data-stu-id="c0480-202">0</span></span>              | <span data-ttu-id="c0480-203">1.5</span><span class="sxs-lookup"><span data-stu-id="c0480-203">1.5</span></span>                |
| <span data-ttu-id="c0480-204">4</span><span class="sxs-lookup"><span data-stu-id="c0480-204">4</span></span>              | <span data-ttu-id="c0480-205">2</span><span class="sxs-lookup"><span data-stu-id="c0480-205">2</span></span>                  |
| <span data-ttu-id="c0480-206">7</span><span class="sxs-lookup"><span data-stu-id="c0480-206">7</span></span>              | <span data-ttu-id="c0480-207">2,5</span><span class="sxs-lookup"><span data-stu-id="c0480-207">2.5</span></span>                |

## <a name="new-versions"></a><span data-ttu-id="c0480-208">Nouvelles versions</span><span class="sxs-lookup"><span data-stu-id="c0480-208">New versions</span></span>
<span data-ttu-id="c0480-209">Les codes intérêt sont soumis à la date d'effet.</span><span class="sxs-lookup"><span data-stu-id="c0480-209">Interest codes are date effective.</span></span> <span data-ttu-id="c0480-210">Si vous souhaitez modifier le taux d'intérêt, vous pouvez créer une **nouvelle version** effective à une date ultérieure.</span><span class="sxs-lookup"><span data-stu-id="c0480-210">If you want to modify the interest rate, you can create a **new version** that is effective as of a future date.</span></span>

<span data-ttu-id="c0480-211">Pour afficher des versions différentes, vous pouvez utiliser la sélection de menu **À partir du** pour sélectionner la date limite.</span><span class="sxs-lookup"><span data-stu-id="c0480-211">To view different versions, you can use the **As of Date** menu choice to select the cutoff date.</span></span> <span data-ttu-id="c0480-212">Vous pouvez également sélectionner **Afficher tous les enregistrements** pour afficher tous les codes intérêt sur la page.</span><span class="sxs-lookup"><span data-stu-id="c0480-212">You can also select the **Display all records** to view all interest codes in the page.</span></span>




