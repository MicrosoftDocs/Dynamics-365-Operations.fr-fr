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
ms.openlocfilehash: 7be9be728a6515bb1fc1c9bc90938a3d33ea8da8
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5204952"
---
# <a name="sales-tax-payments-and-rounding-rules"></a><span data-ttu-id="166c2-103">Règles d’arrondissement et de paiements de taxe</span><span class="sxs-lookup"><span data-stu-id="166c2-103">Sales tax payments and rounding rules</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="166c2-104">Cet article explique le fonctionnement du paramétrage de la règle d’arrondi sur les administrations fiscales et de l’arrondi du solde de taxe au cours de la tâche Régler et valider la taxe.</span><span class="sxs-lookup"><span data-stu-id="166c2-104">This article explains how the rounding rule setup on the Sales tax authorities works and rounding the sales tax balance during the Settle and post sales tax job.</span></span>

<span data-ttu-id="166c2-105">Régulièrement, la taxe doit être déclarée et payée à l’administration fiscale.</span><span class="sxs-lookup"><span data-stu-id="166c2-105">Periodically, sales tax needs to be reported and paid to tax authorities.</span></span> <span data-ttu-id="166c2-106">Pour ce faire, exécutez le processus de règlement et de validation de la taxe sur la page Taxe.</span><span class="sxs-lookup"><span data-stu-id="166c2-106">This can be done by running the settle and post sales tax process in the Sales tax page.</span></span> <span data-ttu-id="166c2-107">La taxe pour une période sera réglée pour des comptes de taxe et le solde de taxe sera validé dans le compte de règlement de la taxe.</span><span class="sxs-lookup"><span data-stu-id="166c2-107">Sales tax for a period will be settled against the sales tax accounts and the sales tax balance will be posted to the Sales tax settlement account.</span></span> <span data-ttu-id="166c2-108">Le solde de la taxe, qui est validé sur le compte de règlement de la taxe, peut être arrondi comme requis par l’administration fiscale en définissant une règle d’arrondissement sur la page Taxe.</span><span class="sxs-lookup"><span data-stu-id="166c2-108">The sales tax balance, which is posted on the Sales tax settlement account, can be rounded as required by tax authorities by setting up a rounding rule on the Sales tax page.</span></span> 

<span data-ttu-id="166c2-109">La différence d’arrondissement est validée sur le compte d’arrondissement de la taxe qui est sélectionné dans le champ Comptes pour transactions automatiques dans la comptabilité.</span><span class="sxs-lookup"><span data-stu-id="166c2-109">The rounding difference is posted to the Sales tax rounding account that is selected in the Accounts for automatic transactions field in the General ledger.</span></span>

<span data-ttu-id="166c2-110">L’exemple ci-dessous illustre la manière dont la règle d’arrondissement fonctionne dans l’administration fiscale.</span><span class="sxs-lookup"><span data-stu-id="166c2-110">The below example illustrates how the rounding rule on Sales tax authority works.</span></span>

## <a name="examples"></a><span data-ttu-id="166c2-111">Exemples</span><span class="sxs-lookup"><span data-stu-id="166c2-111">Examples</span></span>

<span data-ttu-id="166c2-112">La taxe totale pour une période indique un solde de -98 765,43.</span><span class="sxs-lookup"><span data-stu-id="166c2-112">The total sales tax for a period shows a credit balance of -98,765.43.</span></span> <span data-ttu-id="166c2-113">L’entité juridique a collecté plus de taxes qu’elle n’en a payé.</span><span class="sxs-lookup"><span data-stu-id="166c2-113">The legal entity collected more sales taxes than it paid.</span></span> <span data-ttu-id="166c2-114">C’est pourquoi, l’entité juridique doit de l’argent à l’administration fiscale.</span><span class="sxs-lookup"><span data-stu-id="166c2-114">Therefore, the legal entity owes money to the tax authority.</span></span> 

<span data-ttu-id="166c2-115">L’entité juridique veut utiliser une méthode d’arrondi qui arrondit le solde à l’entier le plus proche.</span><span class="sxs-lookup"><span data-stu-id="166c2-115">The legal entity wants to use a rounding method that rounds the balance to the nearest 1.00.</span></span> <span data-ttu-id="166c2-116">L’utilisateur responsable de la comptabilité des taxes procède comme suit.</span><span class="sxs-lookup"><span data-stu-id="166c2-116">The user who is responsible for sales tax accounting performs the following steps.</span></span>

1. <span data-ttu-id="166c2-117">Cliquez sur **Taxe** > **Taxes indirectes** > **Taxe** > **Administrations fiscales**.</span><span class="sxs-lookup"><span data-stu-id="166c2-117">Click **Tax** > **Indirect taxes** > **Sales tax** > **Sales tax authorities**.</span></span>
2. <span data-ttu-id="166c2-118">Sur l’organisateur **Général**, dans le champ **Type d’arrondi**, sélectionnez **Normal**.</span><span class="sxs-lookup"><span data-stu-id="166c2-118">On the **General** FastTab, in the **Rounding form** field, select **Normal**.</span></span>
3. <span data-ttu-id="166c2-119">Dans le champ **Arrondi**, saisissez 1,00.</span><span class="sxs-lookup"><span data-stu-id="166c2-119">In the **Round-off** field, enter 1.00.</span></span>
4. <span data-ttu-id="166c2-120">Au moment de payer les taxes à l’administration fiscale, accédez à la page **Taxe** > **Déclarations** > **Taxe** > **Régler et valider la taxe**.</span><span class="sxs-lookup"><span data-stu-id="166c2-120">When it is time to pay the sales taxes to the tax authority, go to **Tax** > **Declarations** > **Sales tax** > **Settle and post sale tax**.</span></span> <span data-ttu-id="166c2-121">Dans le compte de règlement de la taxe, vous pouvez voir que le montant de l’impôt à payer de **98 765,43** est arrondi à **98 765**.</span><span class="sxs-lookup"><span data-stu-id="166c2-121">On the sales tax settlement account, you can see that the tax liability amount of **98,765.43** is rounded to **98,765**.</span></span>

<span data-ttu-id="166c2-122">Le tableau suivant montre comment un montant de 98 765,43 est arrondi à l’aide de chaque méthode d’arrondi disponible dans le champ **Type d’arrondi** de la page **Administrations fiscales**.</span><span class="sxs-lookup"><span data-stu-id="166c2-122">The following table shows how an amount of 98,765.43 is rounded by using each rounding method that is available in the **Rounding form** field in the **Sales tax authorities** page.</span></span>

> [!NOTE]                                                                                  
> <span data-ttu-id="166c2-123">Si la valeur d’arrondi est définie sur 0,00, alors :</span><span class="sxs-lookup"><span data-stu-id="166c2-123">If the round-off value is set as 0.00, then:</span></span>
>
> - <span data-ttu-id="166c2-124">Pour l’arrondi normal, le comportement d’arrondi est le même que pour **Arrondi = 0,01**.</span><span class="sxs-lookup"><span data-stu-id="166c2-124">For normal rounding, the rounding behavior is the same as for **Round-off = 0.01**.</span></span>
> - <span data-ttu-id="166c2-125">Pour les **Options de type d’arrondi**, **Arrondi au chiffre inférieur**, **Arrondi au chiffre supérieur**, et **Avantage**, le comportement est le même que pour **Arrondi = 1,00**.</span><span class="sxs-lookup"><span data-stu-id="166c2-125">For the **Rounding form options**, **Downward**, **Rounding-up**, and **Own advantage**, the behavior is the same as for **Round-off = 1.00**.</span></span>

| <span data-ttu-id="166c2-126">Option du type d’arrondi</span><span class="sxs-lookup"><span data-stu-id="166c2-126">Rounding form option</span></span>                | <span data-ttu-id="166c2-127">Valeur d’arrondi = 0,01</span><span class="sxs-lookup"><span data-stu-id="166c2-127">Round-off value = 0.01</span></span> | <span data-ttu-id="166c2-128">Valeur d’arrondi = 0,10</span><span class="sxs-lookup"><span data-stu-id="166c2-128">Round-off value = 0.10</span></span> | <span data-ttu-id="166c2-129">Valeur d’arrondi = 1,00</span><span class="sxs-lookup"><span data-stu-id="166c2-129">Round-off value = 1.00</span></span> | <span data-ttu-id="166c2-130">Valeur d’arrondi = 100,00</span><span class="sxs-lookup"><span data-stu-id="166c2-130">Round-off value = 100.00</span></span> | <span data-ttu-id="166c2-131">Valeur d’arrondi = 0,00</span><span class="sxs-lookup"><span data-stu-id="166c2-131">Round-off value = 0.00</span></span>   |
|-------------------------------------|------------------------|------------------------|------------------------|--------------------------|--------------------------|
| <span data-ttu-id="166c2-132">Normal</span><span class="sxs-lookup"><span data-stu-id="166c2-132">Normal</span></span>                              | <span data-ttu-id="166c2-133">98,765.43</span><span class="sxs-lookup"><span data-stu-id="166c2-133">98,765.43</span></span>              | <span data-ttu-id="166c2-134">98,765.40</span><span class="sxs-lookup"><span data-stu-id="166c2-134">98,765.40</span></span>              | <span data-ttu-id="166c2-135">98,765.00</span><span class="sxs-lookup"><span data-stu-id="166c2-135">98,765.00</span></span>              | <span data-ttu-id="166c2-136">98,800.00</span><span class="sxs-lookup"><span data-stu-id="166c2-136">98,800.00</span></span>                | <span data-ttu-id="166c2-137">98,765.43</span><span class="sxs-lookup"><span data-stu-id="166c2-137">98,765.43</span></span>                |
| <span data-ttu-id="166c2-138">Inférieur</span><span class="sxs-lookup"><span data-stu-id="166c2-138">Downward</span></span>                            | <span data-ttu-id="166c2-139">98,765.43</span><span class="sxs-lookup"><span data-stu-id="166c2-139">98,765.43</span></span>              | <span data-ttu-id="166c2-140">98,765.40</span><span class="sxs-lookup"><span data-stu-id="166c2-140">98,765.40</span></span>              | <span data-ttu-id="166c2-141">98,765.00</span><span class="sxs-lookup"><span data-stu-id="166c2-141">98,765.00</span></span>              | <span data-ttu-id="166c2-142">98,700.00</span><span class="sxs-lookup"><span data-stu-id="166c2-142">98,700.00</span></span>                | <span data-ttu-id="166c2-143">98,765.00</span><span class="sxs-lookup"><span data-stu-id="166c2-143">98,765.00</span></span>                |
| <span data-ttu-id="166c2-144">Supérieur</span><span class="sxs-lookup"><span data-stu-id="166c2-144">Rounding-up</span></span>                         | <span data-ttu-id="166c2-145">98,765.43</span><span class="sxs-lookup"><span data-stu-id="166c2-145">98,765.43</span></span>              | <span data-ttu-id="166c2-146">98,765.50</span><span class="sxs-lookup"><span data-stu-id="166c2-146">98,765.50</span></span>              | <span data-ttu-id="166c2-147">98,766.00</span><span class="sxs-lookup"><span data-stu-id="166c2-147">98,766.00</span></span>              | <span data-ttu-id="166c2-148">98,800.00</span><span class="sxs-lookup"><span data-stu-id="166c2-148">98,800.00</span></span>                | <span data-ttu-id="166c2-149">98,766.00</span><span class="sxs-lookup"><span data-stu-id="166c2-149">98,766.00</span></span>                |
| <span data-ttu-id="166c2-150">Avantage, pour un solde créditeur</span><span class="sxs-lookup"><span data-stu-id="166c2-150">Own advantage, for a credit balance</span></span> | <span data-ttu-id="166c2-151">98,765.43</span><span class="sxs-lookup"><span data-stu-id="166c2-151">98,765.43</span></span>              | <span data-ttu-id="166c2-152">98,765.40</span><span class="sxs-lookup"><span data-stu-id="166c2-152">98,765.40</span></span>              | <span data-ttu-id="166c2-153">98,765.00</span><span class="sxs-lookup"><span data-stu-id="166c2-153">98,765.00</span></span>              | <span data-ttu-id="166c2-154">98,700.00</span><span class="sxs-lookup"><span data-stu-id="166c2-154">98,700.00</span></span>                | <span data-ttu-id="166c2-155">98,765.00</span><span class="sxs-lookup"><span data-stu-id="166c2-155">98,765.00</span></span>                |
| <span data-ttu-id="166c2-156">Avantage, pour un solde débiteur</span><span class="sxs-lookup"><span data-stu-id="166c2-156">Own advantage, for a debit balance</span></span>  | <span data-ttu-id="166c2-157">98,765.43</span><span class="sxs-lookup"><span data-stu-id="166c2-157">98,765.43</span></span>              | <span data-ttu-id="166c2-158">98,765.50</span><span class="sxs-lookup"><span data-stu-id="166c2-158">98,765.50</span></span>              | <span data-ttu-id="166c2-159">98,766.00</span><span class="sxs-lookup"><span data-stu-id="166c2-159">98,766.00</span></span>              | <span data-ttu-id="166c2-160">98,800.00</span><span class="sxs-lookup"><span data-stu-id="166c2-160">98,800.00</span></span>                | <span data-ttu-id="166c2-161">98,766.00</span><span class="sxs-lookup"><span data-stu-id="166c2-161">98,766.00</span></span>                |

### <a name="normal-round-and-round-precision-is-001"></a><span data-ttu-id="166c2-162">Arrondi normal, et précision d’arrondi 0,01</span><span class="sxs-lookup"><span data-stu-id="166c2-162">Normal round, and round precision is 0.01</span></span>

<table>
  <tr>
    <td><span data-ttu-id="166c2-163">Arrondi</span><span class="sxs-lookup"><span data-stu-id="166c2-163">Rounding</span></span>
    </td>
    <td><span data-ttu-id="166c2-164">Processus de calcul</span><span class="sxs-lookup"><span data-stu-id="166c2-164">Calculation process</span></span>
    </td>
  </tr>
    <tr>
    <td><span data-ttu-id="166c2-165">round(1,015, 0,01) = 1,02</span><span class="sxs-lookup"><span data-stu-id="166c2-165">round(1.015, 0.01) = 1.02</span></span>
    </td>
    <td>
      <ol>
        <li><span data-ttu-id="166c2-166">round(1,015 / 0,01, 0) = round(101,5, 0) = 102</span><span class="sxs-lookup"><span data-stu-id="166c2-166">round(1.015 / 0.01, 0) = round(101.5, 0) = 102</span></span>
        </li>
        <li><span data-ttu-id="166c2-167">102 \* 0,01 = 1,02</span><span class="sxs-lookup"><span data-stu-id="166c2-167">102 \* 0.01 = 1.02</span></span>
        </li>
      </ol>
    </td>
  </tr>
    <tr>
    <td><span data-ttu-id="166c2-168">round(1,014, 0,01) = 1,01</span><span class="sxs-lookup"><span data-stu-id="166c2-168">round(1.014, 0.01) = 1.01</span></span>
    </td>
    <td> <ol>
        <li><span data-ttu-id="166c2-169">round(1,014 / 0,01, 0) = round(101,4, 0) = 101</span><span class="sxs-lookup"><span data-stu-id="166c2-169">round(1.014 / 0.01, 0) = round(101.4, 0) = 101</span></span>
        </li>
        <li><span data-ttu-id="166c2-170">101 \* 0,01 = 1,01</span><span class="sxs-lookup"><span data-stu-id="166c2-170">101 \* 0.01 = 1.01</span></span>
        </li>
      </ol>
    </td>
  </tr>
    <tr>
    <td><span data-ttu-id="166c2-171">round(1,011, 0,02) = 1,02</span><span class="sxs-lookup"><span data-stu-id="166c2-171">round(1.011, 0.02) = 1.02</span></span>
    </td>
    <td> <ol>
        <li><span data-ttu-id="166c2-172">round(1,011 / 0,02, 0) = round(50,55, 0) = 51</span><span class="sxs-lookup"><span data-stu-id="166c2-172">round(1.011 / 0.02, 0) = round(50.55, 0) = 51</span></span>
        </li>
        <li><span data-ttu-id="166c2-173">51 \* 0,02 = 1,02</span><span class="sxs-lookup"><span data-stu-id="166c2-173">51 \* 0.02 = 1.02</span></span>
        </li>
      </ol>
    </td>
  </tr>
    <tr>
    <td><span data-ttu-id="166c2-174">round(1,009, 0,02) = 1,00</span><span class="sxs-lookup"><span data-stu-id="166c2-174">round(1.009, 0.02) = 1.00</span></span>
    </td>
    <td> <ol>
        <li><span data-ttu-id="166c2-175">round(1,009 / 0,02, 0) = round(50,45, 0) = 50</span><span class="sxs-lookup"><span data-stu-id="166c2-175">round(1.009 / 0.02, 0) = round(50.45, 0) = 50</span></span>
        </li>
        <li><span data-ttu-id="166c2-176">50 \* 0,02 = 1,00</span><span class="sxs-lookup"><span data-stu-id="166c2-176">50 \* 0.02 = 1.00</span></span>
        </li>
      </ol>
    </td>
  </tr>
</table>

> [!NOTE]                                                                                  
> <span data-ttu-id="166c2-177">Si vous sélectionnez Avantage, l’arrondi est toujours à l’avantage de l’entité juridique.</span><span class="sxs-lookup"><span data-stu-id="166c2-177">If you select Own advantage, the rounding is always to the advantage of the legal entity.</span></span> 

<span data-ttu-id="166c2-178">Pour plus d’informations, voir les rubriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="166c2-178">For more information, see the following topics:</span></span>
- [<span data-ttu-id="166c2-179">Vue d’ensemble des taxes</span><span class="sxs-lookup"><span data-stu-id="166c2-179">Sales tax overview</span></span>](indirect-taxes-overview.md)
- [<span data-ttu-id="166c2-180">Créer un paiement de taxe</span><span class="sxs-lookup"><span data-stu-id="166c2-180">Create a sales tax payment</span></span>](tasks/create-sales-tax-payment.md)
- [<span data-ttu-id="166c2-181">Créer des transactions de taxe sur les documents</span><span class="sxs-lookup"><span data-stu-id="166c2-181">Create sales tax transactions on documents</span></span>](tasks/create-sales-tax-transactions-documents.md)
- [<span data-ttu-id="166c2-182">Afficher les transactions de taxe validées</span><span class="sxs-lookup"><span data-stu-id="166c2-182">View posted sales tax transactions</span></span>](tasks/view-posted-sales-tax-transactions.md)
- [<span data-ttu-id="166c2-183">Fonction round</span><span class="sxs-lookup"><span data-stu-id="166c2-183">round Function</span></span>](https://msdn.microsoft.com/library/aa850656.aspx)




[!INCLUDE[footer-include](../../includes/footer-banner.md)]