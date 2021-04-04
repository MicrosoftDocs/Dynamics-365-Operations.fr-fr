---
title: Paramétrage des taux d’intérêt pour un code intérêt
description: Les codes intérêt contiennent des paramètres qui déterminent quand les intérêts sont facturés et comment ils sont calculés sur les comptes qui présentent des retards.
author: ShivamPandey-msft
manager: AnnBe
ms.date: 02/17/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: Interest
audience: Application User
ms.reviewer: roschlom
ms.custom: 59402
ms.assetid: 3b945333-1eaf-4658-ab5a-1a7791a7eb40
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 5d9ff856e34eb894c5d0ab5fe17c8e95f62fff57
ms.sourcegitcommit: 88babb2fffe97e93bbde543633fc492120f2a4fc
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/06/2021
ms.locfileid: "5555363"
---
# <a name="set-up-interest-rates-for-an-interest-code"></a><span data-ttu-id="bd0c9-103">Paramétrage des taux d’intérêt pour un code intérêt</span><span class="sxs-lookup"><span data-stu-id="bd0c9-103">Set up interest rates for an interest code</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="bd0c9-104">Les codes intérêt contiennent des paramètres qui déterminent quand les intérêts sont facturés et comment ils sont calculés sur les comptes qui présentent des retards.</span><span class="sxs-lookup"><span data-stu-id="bd0c9-104">Interest codes contain settings that determine when interest is charged and how it is calculated on overdue accounts.</span></span>

<span data-ttu-id="bd0c9-105">Vous pouvez paramétrer un seul code intérêt et l’appliquer à plusieurs profils de validation client, codes de facturation ou à des lignes de factures spécifiques.</span><span class="sxs-lookup"><span data-stu-id="bd0c9-105">You can set up a single interest code and apply it to multiple customer posting profiles, billing codes, or to specific invoice lines.</span></span> <span data-ttu-id="bd0c9-106">Lorsque les détails du code intérêt sont modifiés, toutes les fonctionnalités qui utilisent le code appliquent automatiquement les modifications aux nouvelles transactions.</span><span class="sxs-lookup"><span data-stu-id="bd0c9-106">When the interest code details are changed, all features that use the code will automatically implement the changes on new transactions.</span></span> <span data-ttu-id="bd0c9-107">Vous pouvez paramétrer deux types de taux pour chaque code intérêt :</span><span class="sxs-lookup"><span data-stu-id="bd0c9-107">For each interest code, you can set up two types of rates:</span></span>
-   <span data-ttu-id="bd0c9-108">Taux pour les intérêts créditeurs − Ils représentent des revenus gagnés en facturant des intérêts sur les factures ou les notes d’intérêt.</span><span class="sxs-lookup"><span data-stu-id="bd0c9-108">Rates for interest earnings − These represent revenue that is earned by charging interest on invoices or interest notes.</span></span>
-   <span data-ttu-id="bd0c9-109">Taux pour les intérêts payés − Ils représentent un coût payé pour les intérêts sur les avoirs.</span><span class="sxs-lookup"><span data-stu-id="bd0c9-109">Rates for interest payments − These represent a cost that is paid for interest on credit notes.</span></span>

<span data-ttu-id="bd0c9-110">Ces deux types de taux peuvent exister simultanément et dans le même code intérêt.</span><span class="sxs-lookup"><span data-stu-id="bd0c9-110">Both of these rate types can exist at the same time and in the same interest code.</span></span> <span data-ttu-id="bd0c9-111">Les taux d’intérêt peuvent être basés sur trois types de calcul :</span><span class="sxs-lookup"><span data-stu-id="bd0c9-111">Interest rates can be based on three calculation types:</span></span>
-   <span data-ttu-id="bd0c9-112">Intérêts par pourcentage.</span><span class="sxs-lookup"><span data-stu-id="bd0c9-112">Interest by percentage.</span></span>
-   <span data-ttu-id="bd0c9-113">Intérêts par montant.</span><span class="sxs-lookup"><span data-stu-id="bd0c9-113">Interest by amount.</span></span>
-   <span data-ttu-id="bd0c9-114">Intérêts par tranche, qui résulte en un pourcentage ou montant unique.</span><span class="sxs-lookup"><span data-stu-id="bd0c9-114">Interest by range, which results in a single percentage or amount.</span></span>

<span data-ttu-id="bd0c9-115">Lorsqu’un code intérêt est utilisé pour calculer des intérêts, une note d’intérêt séparée est créée pour chaque taux d’intérêt qui prend effet lorsque le paiement est effectué après la date d’échéance de la transaction.</span><span class="sxs-lookup"><span data-stu-id="bd0c9-115">When an interest code is used to calculate interest, a separate interest note is created for each interest rate that is in effect during the time that the payment has exceeded the transaction due date.</span></span> <span data-ttu-id="bd0c9-116">L’onglet **Rémunérations** de la page **Code intérêt** vous permet de paramétrer les taux d’intérêt pour les intérêts que vous obtenez en facturant un intérêt.</span><span class="sxs-lookup"><span data-stu-id="bd0c9-116">You use the **Earnings** tab on the **Interest code** page to set up interest rates for interest that you earn by charging interest.</span></span> <span data-ttu-id="bd0c9-117">L’onglet **Paiements** vous permet de paramétrer les taux d’intérêt pour les intérêts que vous payez.</span><span class="sxs-lookup"><span data-stu-id="bd0c9-117">Use the **Payments** tab to set up interest rates for interest that you pay.</span></span>

## <a name="interest-rates-based-on-a-percentage"></a><span data-ttu-id="bd0c9-118">Taux d’intérêt basés sur un pourcentage</span><span class="sxs-lookup"><span data-stu-id="bd0c9-118">Interest rates based on a percentage</span></span>
<span data-ttu-id="bd0c9-119">Vous pouvez paramétrer des taux d’intérêt qui calculent un pourcentage spécifié.</span><span class="sxs-lookup"><span data-stu-id="bd0c9-119">You can set up interest rates that calculate a specified percentage.</span></span>

- <span data-ttu-id="bd0c9-120">Le montant des intérêts s’applique à toutes les devises.</span><span class="sxs-lookup"><span data-stu-id="bd0c9-120">Interest amount applies to all currencies.</span></span>
- <span data-ttu-id="bd0c9-121">Vous pouvez spécifier des limites du montant des intérêts facultatives.</span><span class="sxs-lookup"><span data-stu-id="bd0c9-121">Optional interest amount limits can be entered.</span></span>
- <span data-ttu-id="bd0c9-122">L’option **Pourcentage** est sélectionnée dans le champ **Calculer les intérêts sur base de** de la page **Paramétrer les codes intérêt**.</span><span class="sxs-lookup"><span data-stu-id="bd0c9-122">**Percentage** is selected in the **Calculate interest based on** field on the **Set up Interest codes** page.</span></span>

<span data-ttu-id="bd0c9-123">Par exemple, pour paramétrer un code intérêt qui évalue 5 % d’intérêts pour chaque période de deux mois après la date d’échéance de la transaction pour le paiement de la facture, entrez 2 dans le champ **Calculer les intérêts tous les** et sélectionnez **Mois**.</span><span class="sxs-lookup"><span data-stu-id="bd0c9-123">For example, to set up an interest code that assesses 5 percent interest for every two months that the invoice payment exceeds the transaction due date, you would enter 2 in the **Calculate interest every** field and select **Month**.</span></span>

> [!NOTE] 
> <span data-ttu-id="bd0c9-124">Le nouvel algorithme de calcul des notes d’intérêt est ajouté à l’aide de la gestion des fonctionnalités.</span><span class="sxs-lookup"><span data-stu-id="bd0c9-124">The new algorithm for interest note calculation is added using Feature management.</span></span> <span data-ttu-id="bd0c9-125">Pour utiliser cet algorithme, activez la fonctionnalité **(GBL) Permet de calculer les intérêts par jour en pourcentage annuel divisé par 365**.</span><span class="sxs-lookup"><span data-stu-id="bd0c9-125">To use this algorithm, enable the **(GBL) Allow to calculate interest per day as yearly percent divided by 365** feature.</span></span> <span data-ttu-id="bd0c9-126">Pour obtenir des informations sur l’activation de la fonctionnalité, voir [Présentation de la gestion des fonctionnalités](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).</span><span class="sxs-lookup"><span data-stu-id="bd0c9-126">For information about how to enable the feature, see [Feature management overview](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).</span></span>
> 
> <span data-ttu-id="bd0c9-127">La formule de calcul du montant de la note d’intérêt est la suivante :</span><span class="sxs-lookup"><span data-stu-id="bd0c9-127">The formula for the calculation for the interest note amount is:</span></span> 
>  
> <span data-ttu-id="bd0c9-128">Montant de la note d’intérêt = Montant dû \* % Intérêt annuel / 365 \* Nombre de jours de retard</span><span class="sxs-lookup"><span data-stu-id="bd0c9-128">Interest note amount = Amount owed \* Yearly interest % / 365 \* Number of days late</span></span>
>  
> <span data-ttu-id="bd0c9-129">Cette fonctionnalité est disponible dans la version 10.0.18 et les versions ultérieures.</span><span class="sxs-lookup"><span data-stu-id="bd0c9-129">This feature is available in version 10.0.18 or later.</span></span>    
 
## <a name="interest-rates-based-on-amounts"></a><span data-ttu-id="bd0c9-130">Taux d’intérêt basés sur des montants</span><span class="sxs-lookup"><span data-stu-id="bd0c9-130">Interest rates based on amounts</span></span>
<span data-ttu-id="bd0c9-131">Vous pouvez paramétrer des taux d’intérêt qui calculent un montant spécifié par devise.</span><span class="sxs-lookup"><span data-stu-id="bd0c9-131">You can set up interest rates that calculate a specified amount per currency.</span></span>
- <span data-ttu-id="bd0c9-132">Un montant des intérêts est spécifié pour chaque devise dans le code intérêt.</span><span class="sxs-lookup"><span data-stu-id="bd0c9-132">An interest amount is specified for each currency in the interest code.</span></span>
- <span data-ttu-id="bd0c9-133">Vous pouvez spécifier des limites du montant des intérêts facultatives.</span><span class="sxs-lookup"><span data-stu-id="bd0c9-133">Optional interest amount limits can be entered.</span></span>
- <span data-ttu-id="bd0c9-134">L’option **Montant** est sélectionnée dans le champ **Calculer les intérêts sur base de** de la page **Paramétrer les codes intérêt**.</span><span class="sxs-lookup"><span data-stu-id="bd0c9-134">**Amount** is selected in the **Calculate interest based on** field on the **Set up Interest codes** page.</span></span>

<span data-ttu-id="bd0c9-135">Par exemple, pour paramétrer un code intérêt qui évalue un intérêt de 25,00 pour chaque période de 20 jours après la date d’échéance de la transaction pour le paiement de la facture, entrez 20 dans le champ **Calculer les intérêts tous les** et sélectionnez **Jour**.</span><span class="sxs-lookup"><span data-stu-id="bd0c9-135">For example, to set up an interest code that assesses interest of 25.00 for every 20 days that the invoice payment exceeds the transaction due date, you would enter 20 in the **Calculate interest every** field and select **Day**.</span></span>

## <a name="interest-rates-based-on-ranges"></a><span data-ttu-id="bd0c9-136">Taux d’intérêt basés sur des plages</span><span class="sxs-lookup"><span data-stu-id="bd0c9-136">Interest rates based on ranges</span></span>
<span data-ttu-id="bd0c9-137">Vous pouvez paramétrer des taux d’intérêt qui varient selon le montant en retard, le nombre de jours de retard de paiement, ou le nombre de mois de retard de paiement.</span><span class="sxs-lookup"><span data-stu-id="bd0c9-137">You can set up interest rates that vary depending on the overdue amount, the number of days that the amount is late, or the number of months that the amount is late.</span></span>
-   <span data-ttu-id="bd0c9-138">L’onglet **Bénéfices par devise** permet de définir des paramètres d’intérêt spécifiques pour chaque devise.</span><span class="sxs-lookup"><span data-stu-id="bd0c9-138">You can use the **Earnings by Currency** tab to define specific interest settings for each currency.</span></span> <span data-ttu-id="bd0c9-139">Il vous permet également de définir la tranche.</span><span class="sxs-lookup"><span data-stu-id="bd0c9-139">This is also where you will define the range.</span></span>
-   <span data-ttu-id="bd0c9-140">Utilisez le bouton **Plages** pour ajouter des lignes qui représentent les plages à paramétrer.</span><span class="sxs-lookup"><span data-stu-id="bd0c9-140">Use the **Ranges** button to add lines that represent the ranges that you want to set up.</span></span> <span data-ttu-id="bd0c9-141">La valeur **De** représente le début de la plage et le nombre **Valeur des intérêts** représente soit un pourcentage soit un montant, en fonction de la sélection du champ **Calculer les intérêts sur base de** de la page **Paramétrer les codes intérêt**.</span><span class="sxs-lookup"><span data-stu-id="bd0c9-141">The **From** value represents the beginning of the range and the **Interest value** number represents either a percentage or an amount, depending on the selection in the **Calculate interest based on** field on the **Set up Interest codes** page.</span></span>

## <a name="example-1-interest-by-range--amount"></a><span data-ttu-id="bd0c9-142">Exemple 1 : Intérêts par tranche = montant</span><span class="sxs-lookup"><span data-stu-id="bd0c9-142">Example 1: Interest by range = Amount</span></span>
<span data-ttu-id="bd0c9-143">Vous paramétrez un code intérêt qui évalue un intérêt une fois pour chaque période de trois mois après la date d’échéance de la transaction pour le paiement de la facture.</span><span class="sxs-lookup"><span data-stu-id="bd0c9-143">You set up an interest code that assesses interest one time for every three months that the invoice payment exceeds the transaction due date.</span></span> <span data-ttu-id="bd0c9-144">Vous souhaitez baser le calcul sur une valeur d’intérêts par pourcentage, selon des intervalles de montants par paliers.</span><span class="sxs-lookup"><span data-stu-id="bd0c9-144">You want to base the calculation on a percentage interest value, according to stepped amount intervals.</span></span> <span data-ttu-id="bd0c9-145">La valeur des intérêts est 1 % pour les montants de facture jusqu’à 1 000,00, 2 % pour les montants compris entre 1 001,00 et 5 000,00, et 3 % pour les montants supérieurs à 5 000,00.</span><span class="sxs-lookup"><span data-stu-id="bd0c9-145">The interest value will be 1 percent for invoice amounts up to 1,000.00, 2 percent for amounts from 1,001.00 to 5,000.00, and 3 percent for amounts larger than 5,000.00.</span></span> <span data-ttu-id="bd0c9-146">Vous paramétrez les valeurs du champ Code intérêt comme suit.</span><span class="sxs-lookup"><span data-stu-id="bd0c9-146">You set up the interest code field values as follows.</span></span>

| <span data-ttu-id="bd0c9-147">**Nom de champ**</span><span class="sxs-lookup"><span data-stu-id="bd0c9-147">**Field name**</span></span>                  | <span data-ttu-id="bd0c9-148">**Valeur de champ**</span><span class="sxs-lookup"><span data-stu-id="bd0c9-148">**Field value**</span></span> |
|---------------------------------|-----------------|
| <span data-ttu-id="bd0c9-149">**Code intérêt**</span><span class="sxs-lookup"><span data-stu-id="bd0c9-149">**Interest code**</span></span>               | <span data-ttu-id="bd0c9-150">3M%ByAmt</span><span class="sxs-lookup"><span data-stu-id="bd0c9-150">3M%ByAmt</span></span>        |
| <span data-ttu-id="bd0c9-151">**Calculer chaque intérêt**</span><span class="sxs-lookup"><span data-stu-id="bd0c9-151">**Calculate interest every**</span></span>    | <span data-ttu-id="bd0c9-152">3/Mois</span><span class="sxs-lookup"><span data-stu-id="bd0c9-152">3/Month</span></span>         |
| <span data-ttu-id="bd0c9-153">**Intérêts par tranche**</span><span class="sxs-lookup"><span data-stu-id="bd0c9-153">**Interest by range**</span></span>           | <span data-ttu-id="bd0c9-154">Montant</span><span class="sxs-lookup"><span data-stu-id="bd0c9-154">Amount</span></span>          |
| <span data-ttu-id="bd0c9-155">**Calculer les intérêts sur base de**</span><span class="sxs-lookup"><span data-stu-id="bd0c9-155">**Calculate interest based on**</span></span> | <span data-ttu-id="bd0c9-156">Pourcentage</span><span class="sxs-lookup"><span data-stu-id="bd0c9-156">Percentage</span></span>      |

<span data-ttu-id="bd0c9-157">Vous devez paramétrer les informations de tranches comme suit.</span><span class="sxs-lookup"><span data-stu-id="bd0c9-157">You set up the range information as follows.</span></span>

| <span data-ttu-id="bd0c9-158">**Valeur de début**</span><span class="sxs-lookup"><span data-stu-id="bd0c9-158">**From value**</span></span> | <span data-ttu-id="bd0c9-159">**Valeur des intérêts**</span><span class="sxs-lookup"><span data-stu-id="bd0c9-159">**Interest value**</span></span> |
|----------------|--------------------|
| <span data-ttu-id="bd0c9-160">0</span><span class="sxs-lookup"><span data-stu-id="bd0c9-160">0</span></span>              | <span data-ttu-id="bd0c9-161">1</span><span class="sxs-lookup"><span data-stu-id="bd0c9-161">1</span></span>                  |
| <span data-ttu-id="bd0c9-162">1,001</span><span class="sxs-lookup"><span data-stu-id="bd0c9-162">1,001</span></span>          | <span data-ttu-id="bd0c9-163">2</span><span class="sxs-lookup"><span data-stu-id="bd0c9-163">2</span></span>                  |
| <span data-ttu-id="bd0c9-164">5,001</span><span class="sxs-lookup"><span data-stu-id="bd0c9-164">5,001</span></span>          | <span data-ttu-id="bd0c9-165">3</span><span class="sxs-lookup"><span data-stu-id="bd0c9-165">3</span></span>                  |


## <a name="example-2-interest-by-range--days"></a><span data-ttu-id="bd0c9-166">Exemple 2 : Intérêts par tranche = jours</span><span class="sxs-lookup"><span data-stu-id="bd0c9-166">Example 2: Interest by range = Days</span></span>
--------------------------------------------------

<span data-ttu-id="bd0c9-167">Vous paramétrez un code intérêt qui évalue un intérêt une fois pour chaque période de 15 jours après la date d’échéance de la transaction pour le paiement de la facture.</span><span class="sxs-lookup"><span data-stu-id="bd0c9-167">You set up an interest code that assesses interest one time for every 15 days that the invoice payment exceeds the transaction due date.</span></span> <span data-ttu-id="bd0c9-168">Vous souhaitez baser le calcul sur une valeur d’intérêts par montant, selon des intervalles de jours par paliers.</span><span class="sxs-lookup"><span data-stu-id="bd0c9-168">You want to base the calculation on an amount interest value, according to stepped day intervals.</span></span> <span data-ttu-id="bd0c9-169">La valeur des intérêts est 10,00 par période de 15 jours pendant les 60 premiers jours, 15,00 par période de 15 jours pendant les jours 61 à 90 et 20,00 par période de 15 jours après le 91e jour.</span><span class="sxs-lookup"><span data-stu-id="bd0c9-169">The interest value will be 10.00 per 15 days during the first 60 days, 15.00 per 15 days during days 61 to 90, and 20.00 per 15 days from day 91 and after.</span></span> <span data-ttu-id="bd0c9-170">Vous paramétrez les valeurs du champ Code intérêt comme suit.</span><span class="sxs-lookup"><span data-stu-id="bd0c9-170">You set up the interest code field values as follows.</span></span>

| <span data-ttu-id="bd0c9-171">**Nom de champ**</span><span class="sxs-lookup"><span data-stu-id="bd0c9-171">**Field name**</span></span>                  | <span data-ttu-id="bd0c9-172">**Valeur de champ**</span><span class="sxs-lookup"><span data-stu-id="bd0c9-172">**Field value**</span></span> |
|---------------------------------|-----------------|
| <span data-ttu-id="bd0c9-173">**Code intérêt**</span><span class="sxs-lookup"><span data-stu-id="bd0c9-173">**Interest code**</span></span>               | <span data-ttu-id="bd0c9-174">15DAmtXDay</span><span class="sxs-lookup"><span data-stu-id="bd0c9-174">15DAmtXDay</span></span>      |
| <span data-ttu-id="bd0c9-175">**Calculer chaque intérêt**</span><span class="sxs-lookup"><span data-stu-id="bd0c9-175">**Calculate interest every**</span></span>    | <span data-ttu-id="bd0c9-176">15/Jour</span><span class="sxs-lookup"><span data-stu-id="bd0c9-176">15/Day</span></span>          |
| <span data-ttu-id="bd0c9-177">**Intérêts par tranche**</span><span class="sxs-lookup"><span data-stu-id="bd0c9-177">**Interest by range**</span></span>           | <span data-ttu-id="bd0c9-178">Jours</span><span class="sxs-lookup"><span data-stu-id="bd0c9-178">Days</span></span>            |
| <span data-ttu-id="bd0c9-179">**Calculer les intérêts sur base de**</span><span class="sxs-lookup"><span data-stu-id="bd0c9-179">**Calculate interest based on**</span></span> | <span data-ttu-id="bd0c9-180">Montant</span><span class="sxs-lookup"><span data-stu-id="bd0c9-180">Amount</span></span>          |

<span data-ttu-id="bd0c9-181">Vous devez paramétrer les informations de tranches comme suit.</span><span class="sxs-lookup"><span data-stu-id="bd0c9-181">You set up the range information as follows.</span></span>

| <span data-ttu-id="bd0c9-182">**Valeur de début**</span><span class="sxs-lookup"><span data-stu-id="bd0c9-182">**From value**</span></span> | <span data-ttu-id="bd0c9-183">**Valeur des intérêts**</span><span class="sxs-lookup"><span data-stu-id="bd0c9-183">**Interest value**</span></span> |
|----------------|--------------------|
| <span data-ttu-id="bd0c9-184">0</span><span class="sxs-lookup"><span data-stu-id="bd0c9-184">0</span></span>              | <span data-ttu-id="bd0c9-185">10</span><span class="sxs-lookup"><span data-stu-id="bd0c9-185">10</span></span>                 |
| <span data-ttu-id="bd0c9-186">61</span><span class="sxs-lookup"><span data-stu-id="bd0c9-186">61</span></span>             | <span data-ttu-id="bd0c9-187">15</span><span class="sxs-lookup"><span data-stu-id="bd0c9-187">15</span></span>                 |
| <span data-ttu-id="bd0c9-188">91</span><span class="sxs-lookup"><span data-stu-id="bd0c9-188">91</span></span>             | <span data-ttu-id="bd0c9-189">20</span><span class="sxs-lookup"><span data-stu-id="bd0c9-189">20</span></span>                 |


## <a name="example-3-interest-by-range--months"></a><span data-ttu-id="bd0c9-190">Exemple 3 : Intérêts par tranche = mois</span><span class="sxs-lookup"><span data-stu-id="bd0c9-190">Example 3: Interest by range = Months</span></span>
----------------------------------------------------

<span data-ttu-id="bd0c9-191">Vous paramétrez un code intérêt qui évalue un intérêt une fois pour chaque mois après la date d’échéance de la transaction pour le paiement de la facture.</span><span class="sxs-lookup"><span data-stu-id="bd0c9-191">You set up an interest code that assesses interest one time for every month that the invoice payment exceeds the transaction due date.</span></span> <span data-ttu-id="bd0c9-192">Vous souhaitez baser le calcul sur une valeur d’intérêts par pourcentage, selon des intervalles de mois par paliers.</span><span class="sxs-lookup"><span data-stu-id="bd0c9-192">You want to base the calculation on a percentage interest value, according to stepped month intervals.</span></span> <span data-ttu-id="bd0c9-193">La valeur des intérêts sera de 1,5 % par mois pendant les trois premiers mois de retard, 2,0 % par mois pour les trois mois suivants, et 2,5 % par mois au delà des six premiers mois.</span><span class="sxs-lookup"><span data-stu-id="bd0c9-193">The interest value will be 1.5 percent per month for the first three overdue months, 2.0 percent per month for the second three months, and 2.5 percent per month for each month beyond the first six months.</span></span> <span data-ttu-id="bd0c9-194">Vous paramétrez les valeurs du champ Code intérêt comme suit.</span><span class="sxs-lookup"><span data-stu-id="bd0c9-194">You set up the interest code field values as follows.</span></span>

| <span data-ttu-id="bd0c9-195">**Nom de champ**</span><span class="sxs-lookup"><span data-stu-id="bd0c9-195">**Field name**</span></span>                  | <span data-ttu-id="bd0c9-196">**Valeur de champ**</span><span class="sxs-lookup"><span data-stu-id="bd0c9-196">**Field value**</span></span> |
|---------------------------------|-----------------|
| <span data-ttu-id="bd0c9-197">**Code intérêt**</span><span class="sxs-lookup"><span data-stu-id="bd0c9-197">**Interest code**</span></span>               | <span data-ttu-id="bd0c9-198">1M%ByMth</span><span class="sxs-lookup"><span data-stu-id="bd0c9-198">1M%ByMth</span></span>        |
| <span data-ttu-id="bd0c9-199">**Calculer chaque intérêt**</span><span class="sxs-lookup"><span data-stu-id="bd0c9-199">**Calculate interest every**</span></span>    | <span data-ttu-id="bd0c9-200">1/Mois</span><span class="sxs-lookup"><span data-stu-id="bd0c9-200">1/Month</span></span>         |
| <span data-ttu-id="bd0c9-201">**Intérêts par tranche**</span><span class="sxs-lookup"><span data-stu-id="bd0c9-201">**Interest by range**</span></span>           | <span data-ttu-id="bd0c9-202">Mois</span><span class="sxs-lookup"><span data-stu-id="bd0c9-202">Months</span></span>          |
| <span data-ttu-id="bd0c9-203">**Calculer les intérêts sur base de**</span><span class="sxs-lookup"><span data-stu-id="bd0c9-203">**Calculate interest based on**</span></span> | <span data-ttu-id="bd0c9-204">Pourcentage</span><span class="sxs-lookup"><span data-stu-id="bd0c9-204">Percentage</span></span>      |

<span data-ttu-id="bd0c9-205">Vous devez paramétrer les informations de tranches comme suit.</span><span class="sxs-lookup"><span data-stu-id="bd0c9-205">You set up the range information as follows.</span></span>

| <span data-ttu-id="bd0c9-206">**Valeur de début**</span><span class="sxs-lookup"><span data-stu-id="bd0c9-206">**From value**</span></span> | <span data-ttu-id="bd0c9-207">**Valeur des intérêts**</span><span class="sxs-lookup"><span data-stu-id="bd0c9-207">**Interest value**</span></span> |
|----------------|--------------------|
| <span data-ttu-id="bd0c9-208">0</span><span class="sxs-lookup"><span data-stu-id="bd0c9-208">0</span></span>              | <span data-ttu-id="bd0c9-209">1.5</span><span class="sxs-lookup"><span data-stu-id="bd0c9-209">1.5</span></span>                |
| <span data-ttu-id="bd0c9-210">4</span><span class="sxs-lookup"><span data-stu-id="bd0c9-210">4</span></span>              | <span data-ttu-id="bd0c9-211">2</span><span class="sxs-lookup"><span data-stu-id="bd0c9-211">2</span></span>                  |
| <span data-ttu-id="bd0c9-212">7</span><span class="sxs-lookup"><span data-stu-id="bd0c9-212">7</span></span>              | <span data-ttu-id="bd0c9-213">2,5</span><span class="sxs-lookup"><span data-stu-id="bd0c9-213">2.5</span></span>                |

## <a name="new-versions"></a><span data-ttu-id="bd0c9-214">Nouvelles versions</span><span class="sxs-lookup"><span data-stu-id="bd0c9-214">New versions</span></span>
<span data-ttu-id="bd0c9-215">Les codes intérêt sont soumis à la date d’effet.</span><span class="sxs-lookup"><span data-stu-id="bd0c9-215">Interest codes are date effective.</span></span> <span data-ttu-id="bd0c9-216">Si vous souhaitez modifier le taux d’intérêt, vous pouvez créer une **nouvelle version** effective à une date ultérieure.</span><span class="sxs-lookup"><span data-stu-id="bd0c9-216">If you want to modify the interest rate, you can create a **new version** that is effective as of a future date.</span></span>

<span data-ttu-id="bd0c9-217">Pour afficher des versions différentes, vous pouvez utiliser la sélection de menu **À partir du** pour sélectionner la date limite.</span><span class="sxs-lookup"><span data-stu-id="bd0c9-217">To view different versions, you can use the **As of Date** menu choice to select the cutoff date.</span></span> <span data-ttu-id="bd0c9-218">Vous pouvez également sélectionner **Afficher tous les enregistrements** pour afficher tous les codes intérêt sur la page.</span><span class="sxs-lookup"><span data-stu-id="bd0c9-218">You can also select the **Display all records** to view all interest codes in the page.</span></span>





[!INCLUDE[footer-include](../../includes/footer-banner.md)]
