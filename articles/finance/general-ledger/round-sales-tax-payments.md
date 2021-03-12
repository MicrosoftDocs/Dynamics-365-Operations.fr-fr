---
title: Règles d’arrondissement et de paiements de taxe
description: Cet article explique le fonctionnement du paramétrage de la règle d’arrondi sur les administrations fiscales et de l’arrondi du solde de taxe au cours de la tâche Régler et valider la taxe.
author: ShylaThompson
manager: AnnBe
ms.date: 04/20/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TaxAuthority
audience: Application User
ms.reviewer: roschlom
ms.custom: 6134
ms.assetid: 7dcd3cf5-ebdf-4a9f-806c-1296c7da0331
ms.search.region: Global
ms.author: riluan
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: e8d7e402614b35a77a0283d31377a073b0a6b357
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4990187"
---
# <a name="sales-tax-payments-and-rounding-rules"></a><span data-ttu-id="301f5-103">Règles d’arrondissement et de paiements de taxe</span><span class="sxs-lookup"><span data-stu-id="301f5-103">Sales tax payments and rounding rules</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="301f5-104">Cet article explique le fonctionnement du paramétrage de la règle d’arrondi sur les administrations fiscales et de l’arrondi du solde de taxe au cours de la tâche Régler et valider la taxe.</span><span class="sxs-lookup"><span data-stu-id="301f5-104">This article explains how the rounding rule setup on the Sales tax authorities works and rounding the sales tax balance during the Settle and post sales tax job.</span></span>

<span data-ttu-id="301f5-105">Régulièrement, la taxe doit être déclarée et payée à l’administration fiscale.</span><span class="sxs-lookup"><span data-stu-id="301f5-105">Periodically, sales tax needs to be reported and paid to tax authorities.</span></span> <span data-ttu-id="301f5-106">Pour ce faire, exécutez le processus de règlement et de validation de la taxe sur la page Taxe.</span><span class="sxs-lookup"><span data-stu-id="301f5-106">This can be done by running the settle and post sales tax process in the Sales tax page.</span></span> <span data-ttu-id="301f5-107">La taxe pour une période sera réglée pour des comptes de taxe et le solde de taxe sera validé dans le compte de règlement de la taxe.</span><span class="sxs-lookup"><span data-stu-id="301f5-107">Sales tax for a period will be settled against the sales tax accounts and the sales tax balance will be posted to the Sales tax settlement account.</span></span> <span data-ttu-id="301f5-108">Le solde de la taxe, qui est validé sur le compte de règlement de la taxe, peut être arrondi comme requis par l’administration fiscale en définissant une règle d’arrondissement sur la page Taxe.</span><span class="sxs-lookup"><span data-stu-id="301f5-108">The sales tax balance, which is posted on the Sales tax settlement account, can be rounded as required by tax authorities by setting up a rounding rule on the Sales tax page.</span></span> 

<span data-ttu-id="301f5-109">La différence d’arrondissement est validée sur le compte d’arrondissement de la taxe qui est sélectionné dans le champ Comptes pour transactions automatiques dans la comptabilité.</span><span class="sxs-lookup"><span data-stu-id="301f5-109">The rounding difference is posted to the Sales tax rounding account that is selected in the Accounts for automatic transactions field in the General ledger.</span></span>

<span data-ttu-id="301f5-110">L’exemple ci-dessous illustre la manière dont la règle d’arrondissement fonctionne dans l’administration fiscale.</span><span class="sxs-lookup"><span data-stu-id="301f5-110">The below example illustrates how the rounding rule on Sales tax authority works.</span></span>

## <a name="examples"></a><span data-ttu-id="301f5-111">Exemples</span><span class="sxs-lookup"><span data-stu-id="301f5-111">Examples</span></span>

<span data-ttu-id="301f5-112">La taxe totale pour une période indique un solde de -98 765,43.</span><span class="sxs-lookup"><span data-stu-id="301f5-112">The total sales tax for a period shows a credit balance of -98,765.43.</span></span> <span data-ttu-id="301f5-113">L’entité juridique a collecté plus de taxes qu’elle n’en a payé.</span><span class="sxs-lookup"><span data-stu-id="301f5-113">The legal entity collected more sales taxes than it paid.</span></span> <span data-ttu-id="301f5-114">C’est pourquoi, l’entité juridique doit de l’argent à l’administration fiscale.</span><span class="sxs-lookup"><span data-stu-id="301f5-114">Therefore, the legal entity owes money to the tax authority.</span></span> 

<span data-ttu-id="301f5-115">L’entité juridique veut utiliser une méthode d’arrondi qui arrondit le solde à l’entier le plus proche.</span><span class="sxs-lookup"><span data-stu-id="301f5-115">The legal entity wants to use a rounding method that rounds the balance to the nearest 1.00.</span></span> <span data-ttu-id="301f5-116">L’utilisateur responsable de la comptabilité des taxes procède comme suit.</span><span class="sxs-lookup"><span data-stu-id="301f5-116">The user who is responsible for sales tax accounting performs the following steps.</span></span>

1. <span data-ttu-id="301f5-117">Cliquez sur **Taxe** > **Taxes indirectes** > **Taxe** > **Administrations fiscales**.</span><span class="sxs-lookup"><span data-stu-id="301f5-117">Click **Tax** > **Indirect taxes** > **Sales tax** > **Sales tax authorities**.</span></span>
2. <span data-ttu-id="301f5-118">Sur l’organisateur **Général**, dans le champ **Type d’arrondi**, sélectionnez **Normal**.</span><span class="sxs-lookup"><span data-stu-id="301f5-118">On the **General** FastTab, in the **Rounding form** field, select **Normal**.</span></span>
3. <span data-ttu-id="301f5-119">Dans le champ **Arrondi**, saisissez 1,00.</span><span class="sxs-lookup"><span data-stu-id="301f5-119">In the **Round-off** field, enter 1.00.</span></span>
4. <span data-ttu-id="301f5-120">Au moment de payer les taxes à l’administration fiscale, accédez à la page **Taxe** > **Déclarations** > **Taxe** > **Régler et valider la taxe**.</span><span class="sxs-lookup"><span data-stu-id="301f5-120">When it is time to pay the sales taxes to the tax authority, go to **Tax** > **Declarations** > **Sales tax** > **Settle and post sale tax**.</span></span> <span data-ttu-id="301f5-121">Dans le compte de règlement de la taxe, vous pouvez voir que le montant de l’impôt à payer de **98 765,43** est arrondi à **98 765**.</span><span class="sxs-lookup"><span data-stu-id="301f5-121">On the sales tax settlement account, you can see that the tax liability amount of **98,765.43** is rounded to **98,765**.</span></span>

<span data-ttu-id="301f5-122">Le tableau suivant montre comment un montant de 98 765,43 est arrondi à l’aide de chaque méthode d’arrondi disponible dans le champ **Type d’arrondi** de la page **Administrations fiscales**.</span><span class="sxs-lookup"><span data-stu-id="301f5-122">The following table shows how an amount of 98,765.43 is rounded by using each rounding method that is available in the **Rounding form** field in the **Sales tax authorities** page.</span></span>

> [!NOTE]                                                                                  
> <span data-ttu-id="301f5-123">Si la valeur d’arrondi est définie sur 0,00, alors :</span><span class="sxs-lookup"><span data-stu-id="301f5-123">If the round-off value is set as 0.00, then:</span></span>
>
> - <span data-ttu-id="301f5-124">Pour l’arrondi normal, le comportement d’arrondi est le même que pour **Arrondi = 0,01**.</span><span class="sxs-lookup"><span data-stu-id="301f5-124">For normal rounding, the rounding behavior is the same as for **Round-off = 0.01**.</span></span>
> - <span data-ttu-id="301f5-125">Pour les **Options de type d’arrondi**, **Arrondi au chiffre inférieur**, **Arrondi au chiffre supérieur**, et **Avantage**, le comportement est le même que pour **Arrondi = 1,00**.</span><span class="sxs-lookup"><span data-stu-id="301f5-125">For the **Rounding form options**, **Downward**, **Rounding-up**, and **Own advantage**, the behavior is the same as for **Round-off = 1.00**.</span></span>

| <span data-ttu-id="301f5-126">Option du type d’arrondi</span><span class="sxs-lookup"><span data-stu-id="301f5-126">Rounding form option</span></span>                | <span data-ttu-id="301f5-127">Valeur d’arrondi = 0,01</span><span class="sxs-lookup"><span data-stu-id="301f5-127">Round-off value = 0.01</span></span> | <span data-ttu-id="301f5-128">Valeur d’arrondi = 0,10</span><span class="sxs-lookup"><span data-stu-id="301f5-128">Round-off value = 0.10</span></span> | <span data-ttu-id="301f5-129">Valeur d’arrondi = 1,00</span><span class="sxs-lookup"><span data-stu-id="301f5-129">Round-off value = 1.00</span></span> | <span data-ttu-id="301f5-130">Valeur d’arrondi = 100,00</span><span class="sxs-lookup"><span data-stu-id="301f5-130">Round-off value = 100.00</span></span> | <span data-ttu-id="301f5-131">Valeur d’arrondi = 0,00</span><span class="sxs-lookup"><span data-stu-id="301f5-131">Round-off value = 0.00</span></span>   |
|-------------------------------------|------------------------|------------------------|------------------------|--------------------------|--------------------------|
| <span data-ttu-id="301f5-132">Normal</span><span class="sxs-lookup"><span data-stu-id="301f5-132">Normal</span></span>                              | <span data-ttu-id="301f5-133">98,765.43</span><span class="sxs-lookup"><span data-stu-id="301f5-133">98,765.43</span></span>              | <span data-ttu-id="301f5-134">98,765.40</span><span class="sxs-lookup"><span data-stu-id="301f5-134">98,765.40</span></span>              | <span data-ttu-id="301f5-135">98,765.00</span><span class="sxs-lookup"><span data-stu-id="301f5-135">98,765.00</span></span>              | <span data-ttu-id="301f5-136">98,800.00</span><span class="sxs-lookup"><span data-stu-id="301f5-136">98,800.00</span></span>                | <span data-ttu-id="301f5-137">98,765.43</span><span class="sxs-lookup"><span data-stu-id="301f5-137">98,765.43</span></span>                |
| <span data-ttu-id="301f5-138">Inférieur</span><span class="sxs-lookup"><span data-stu-id="301f5-138">Downward</span></span>                            | <span data-ttu-id="301f5-139">98,765.43</span><span class="sxs-lookup"><span data-stu-id="301f5-139">98,765.43</span></span>              | <span data-ttu-id="301f5-140">98,765.40</span><span class="sxs-lookup"><span data-stu-id="301f5-140">98,765.40</span></span>              | <span data-ttu-id="301f5-141">98,765.00</span><span class="sxs-lookup"><span data-stu-id="301f5-141">98,765.00</span></span>              | <span data-ttu-id="301f5-142">98,700.00</span><span class="sxs-lookup"><span data-stu-id="301f5-142">98,700.00</span></span>                | <span data-ttu-id="301f5-143">98,765.00</span><span class="sxs-lookup"><span data-stu-id="301f5-143">98,765.00</span></span>                |
| <span data-ttu-id="301f5-144">Supérieur</span><span class="sxs-lookup"><span data-stu-id="301f5-144">Rounding-up</span></span>                         | <span data-ttu-id="301f5-145">98,765.43</span><span class="sxs-lookup"><span data-stu-id="301f5-145">98,765.43</span></span>              | <span data-ttu-id="301f5-146">98,765.50</span><span class="sxs-lookup"><span data-stu-id="301f5-146">98,765.50</span></span>              | <span data-ttu-id="301f5-147">98,766.00</span><span class="sxs-lookup"><span data-stu-id="301f5-147">98,766.00</span></span>              | <span data-ttu-id="301f5-148">98,800.00</span><span class="sxs-lookup"><span data-stu-id="301f5-148">98,800.00</span></span>                | <span data-ttu-id="301f5-149">98,766.00</span><span class="sxs-lookup"><span data-stu-id="301f5-149">98,766.00</span></span>                |
| <span data-ttu-id="301f5-150">Avantage, pour un solde créditeur</span><span class="sxs-lookup"><span data-stu-id="301f5-150">Own advantage, for a credit balance</span></span> | <span data-ttu-id="301f5-151">98,765.43</span><span class="sxs-lookup"><span data-stu-id="301f5-151">98,765.43</span></span>              | <span data-ttu-id="301f5-152">98,765.40</span><span class="sxs-lookup"><span data-stu-id="301f5-152">98,765.40</span></span>              | <span data-ttu-id="301f5-153">98,765.00</span><span class="sxs-lookup"><span data-stu-id="301f5-153">98,765.00</span></span>              | <span data-ttu-id="301f5-154">98,700.00</span><span class="sxs-lookup"><span data-stu-id="301f5-154">98,700.00</span></span>                | <span data-ttu-id="301f5-155">98,765.00</span><span class="sxs-lookup"><span data-stu-id="301f5-155">98,765.00</span></span>                |
| <span data-ttu-id="301f5-156">Avantage, pour un solde débiteur</span><span class="sxs-lookup"><span data-stu-id="301f5-156">Own advantage, for a debit balance</span></span>  | <span data-ttu-id="301f5-157">98,765.43</span><span class="sxs-lookup"><span data-stu-id="301f5-157">98,765.43</span></span>              | <span data-ttu-id="301f5-158">98,765.50</span><span class="sxs-lookup"><span data-stu-id="301f5-158">98,765.50</span></span>              | <span data-ttu-id="301f5-159">98,766.00</span><span class="sxs-lookup"><span data-stu-id="301f5-159">98,766.00</span></span>              | <span data-ttu-id="301f5-160">98,800.00</span><span class="sxs-lookup"><span data-stu-id="301f5-160">98,800.00</span></span>                | <span data-ttu-id="301f5-161">98,766.00</span><span class="sxs-lookup"><span data-stu-id="301f5-161">98,766.00</span></span>                |

### <a name="normal-round-and-round-precision-is-001"></a><span data-ttu-id="301f5-162">Arrondi normal, et précision d’arrondi 0,01</span><span class="sxs-lookup"><span data-stu-id="301f5-162">Normal round, and round precision is 0.01</span></span>

<table>
  <tr>
    <td><span data-ttu-id="301f5-163">Arrondi</span><span class="sxs-lookup"><span data-stu-id="301f5-163">Rounding</span></span>
    </td>
    <td><span data-ttu-id="301f5-164">Processus de calcul</span><span class="sxs-lookup"><span data-stu-id="301f5-164">Calculation process</span></span>
    </td>
  </tr>
    <tr>
    <td><span data-ttu-id="301f5-165">round(1,015, 0,01) = 1,02</span><span class="sxs-lookup"><span data-stu-id="301f5-165">round(1.015, 0.01) = 1.02</span></span>
    </td>
    <td>
      <ol>
        <li><span data-ttu-id="301f5-166">round(1,015 / 0,01, 0) = round(101,5, 0) = 102</span><span class="sxs-lookup"><span data-stu-id="301f5-166">round(1.015 / 0.01, 0) = round(101.5, 0) = 102</span></span>
        </li>
        <li><span data-ttu-id="301f5-167">102 \* 0,01 = 1,02</span><span class="sxs-lookup"><span data-stu-id="301f5-167">102 \* 0.01 = 1.02</span></span>
        </li>
      </ol>
    </td>
  </tr>
    <tr>
    <td><span data-ttu-id="301f5-168">round(1,014, 0,01) = 1,01</span><span class="sxs-lookup"><span data-stu-id="301f5-168">round(1.014, 0.01) = 1.01</span></span>
    </td>
    <td> <ol>
        <li><span data-ttu-id="301f5-169">round(1,014 / 0,01, 0) = round(101,4, 0) = 101</span><span class="sxs-lookup"><span data-stu-id="301f5-169">round(1.014 / 0.01, 0) = round(101.4, 0) = 101</span></span>
        </li>
        <li><span data-ttu-id="301f5-170">101 \* 0,01 = 1,01</span><span class="sxs-lookup"><span data-stu-id="301f5-170">101 \* 0.01 = 1.01</span></span>
        </li>
      </ol>
    </td>
  </tr>
    <tr>
    <td><span data-ttu-id="301f5-171">round(1,011, 0,02) = 1,02</span><span class="sxs-lookup"><span data-stu-id="301f5-171">round(1.011, 0.02) = 1.02</span></span>
    </td>
    <td> <ol>
        <li><span data-ttu-id="301f5-172">round(1,011 / 0,02, 0) = round(50,55, 0) = 51</span><span class="sxs-lookup"><span data-stu-id="301f5-172">round(1.011 / 0.02, 0) = round(50.55, 0) = 51</span></span>
        </li>
        <li><span data-ttu-id="301f5-173">51 \* 0,02 = 1,02</span><span class="sxs-lookup"><span data-stu-id="301f5-173">51 \* 0.02 = 1.02</span></span>
        </li>
      </ol>
    </td>
  </tr>
    <tr>
    <td><span data-ttu-id="301f5-174">round(1,009, 0,02) = 1,00</span><span class="sxs-lookup"><span data-stu-id="301f5-174">round(1.009, 0.02) = 1.00</span></span>
    </td>
    <td> <ol>
        <li><span data-ttu-id="301f5-175">round(1,009 / 0,02, 0) = round(50,45, 0) = 50</span><span class="sxs-lookup"><span data-stu-id="301f5-175">round(1.009 / 0.02, 0) = round(50.45, 0) = 50</span></span>
        </li>
        <li><span data-ttu-id="301f5-176">50 \* 0,02 = 1,00</span><span class="sxs-lookup"><span data-stu-id="301f5-176">50 \* 0.02 = 1.00</span></span>
        </li>
      </ol>
    </td>
  </tr>
</table>

> [!NOTE]                                                                                  
> <span data-ttu-id="301f5-177">Si vous sélectionnez Avantage, l’arrondi est toujours à l’avantage de l’entité juridique.</span><span class="sxs-lookup"><span data-stu-id="301f5-177">If you select Own advantage, the rounding is always to the advantage of the legal entity.</span></span> 

<span data-ttu-id="301f5-178">Pour plus d’informations, voir les rubriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="301f5-178">For more information, see the following topics:</span></span>
- [<span data-ttu-id="301f5-179">Vue d’ensemble des taxes</span><span class="sxs-lookup"><span data-stu-id="301f5-179">Sales tax overview</span></span>](indirect-taxes-overview.md)
- [<span data-ttu-id="301f5-180">Créer un paiement de taxe</span><span class="sxs-lookup"><span data-stu-id="301f5-180">Create a sales tax payment</span></span>](tasks/create-sales-tax-payment.md)
- [<span data-ttu-id="301f5-181">Créer des transactions de taxe sur les documents</span><span class="sxs-lookup"><span data-stu-id="301f5-181">Create sales tax transactions on documents</span></span>](tasks/create-sales-tax-transactions-documents.md)
- [<span data-ttu-id="301f5-182">Afficher les transactions de taxe validées</span><span class="sxs-lookup"><span data-stu-id="301f5-182">View posted sales tax transactions</span></span>](tasks/view-posted-sales-tax-transactions.md)
- [<span data-ttu-id="301f5-183">Fonction round</span><span class="sxs-lookup"><span data-stu-id="301f5-183">round Function</span></span>](https://msdn.microsoft.com/library/aa850656.aspx)


