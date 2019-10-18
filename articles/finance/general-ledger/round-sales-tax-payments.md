---
title: Règles d'arrondissement et de paiements de taxe
description: Cet article explique le fonctionnement du paramétrage de la règle d'arrondi sur les administrations fiscales et de l'arrondi du solde de taxe au cours de la tâche Régler et valider la taxe.
author: ShylaThompson
manager: AnnBe
ms.date: 05/30/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TaxAuthority
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 6134
ms.assetid: 7dcd3cf5-ebdf-4a9f-806c-1296c7da0331
ms.search.region: Global
ms.author: yijialuan
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 168c2fb9edfc994617ef6764a5b9f5949d599882
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/27/2019
ms.locfileid: "2186323"
---
# <a name="sales-tax-payments-and-rounding-rules"></a><span data-ttu-id="0cbfa-103">Règles d'arrondissement et de paiements de taxe</span><span class="sxs-lookup"><span data-stu-id="0cbfa-103">Sales tax payments and rounding rules</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="0cbfa-104">Cet article explique le fonctionnement du paramétrage de la règle d'arrondi sur les administrations fiscales et de l'arrondi du solde de taxe au cours de la tâche Régler et valider la taxe.</span><span class="sxs-lookup"><span data-stu-id="0cbfa-104">This article explains how the rounding rule setup on the Sales tax authorities works and rounding the sales tax balance during the Settle and post sales tax job.</span></span>

<span data-ttu-id="0cbfa-105">Régulièrement, la taxe doit être déclarée et payée à l'administration fiscale.</span><span class="sxs-lookup"><span data-stu-id="0cbfa-105">Periodically, sales tax needs to be reported and paid to tax authorities.</span></span> <span data-ttu-id="0cbfa-106">Pour ce faire, exécutez le processus de règlement et de validation de la taxe sur la page Taxe.</span><span class="sxs-lookup"><span data-stu-id="0cbfa-106">This can be done by running the settle and post sales tax process in the Sales tax page.</span></span> <span data-ttu-id="0cbfa-107">La taxe pour une période sera réglée pour des comptes de taxe et le solde de taxe sera validé dans le compte de règlement de la taxe.</span><span class="sxs-lookup"><span data-stu-id="0cbfa-107">Sales tax for a period will be settled against the sales tax accounts and the sales tax balance will be posted to the Sales tax settlement account.</span></span> <span data-ttu-id="0cbfa-108">Le solde de la taxe, qui est validé sur le compte de règlement de la taxe, peut être arrondi comme requis par l'administration fiscale en définissant une règle d'arrondissement sur la page Taxe.</span><span class="sxs-lookup"><span data-stu-id="0cbfa-108">The sales tax balance, which is posted on the Sales tax settlement account, can be rounded as required by tax authorities by setting up a rounding rule on the Sales tax page.</span></span> 

<span data-ttu-id="0cbfa-109">La différence d'arrondissement est validée sur le compte d'arrondissement de la taxe qui est sélectionné dans le champ Comptes pour transactions automatiques dans la comptabilité.</span><span class="sxs-lookup"><span data-stu-id="0cbfa-109">The rounding difference is posted to the Sales tax rounding account that is selected in the Accounts for automatic transactions field in the General ledger.</span></span>

<span data-ttu-id="0cbfa-110">L'exemple ci-dessous illustre la manière dont la règle d'arrondissement fonctionne dans l'administration fiscale.</span><span class="sxs-lookup"><span data-stu-id="0cbfa-110">The below example illustrates how the rounding rule on Sales tax authority works.</span></span>

## <a name="examples"></a><span data-ttu-id="0cbfa-111">Exemples</span><span class="sxs-lookup"><span data-stu-id="0cbfa-111">Examples</span></span>

<span data-ttu-id="0cbfa-112">La taxe totale pour une période indique un solde de -98 765,43.</span><span class="sxs-lookup"><span data-stu-id="0cbfa-112">The total sales tax for a period shows a credit balance of -98,765.43.</span></span> <span data-ttu-id="0cbfa-113">L'entité juridique a collecté plus de taxes qu'elle n'en a payé.</span><span class="sxs-lookup"><span data-stu-id="0cbfa-113">The legal entity collected more sales taxes than it paid.</span></span> <span data-ttu-id="0cbfa-114">C'est pourquoi, l'entité juridique doit de l'argent à l'administration fiscale.</span><span class="sxs-lookup"><span data-stu-id="0cbfa-114">Therefore, the legal entity owes money to the tax authority.</span></span> 

<span data-ttu-id="0cbfa-115">L'entité juridique veut utiliser une méthode d'arrondi qui arrondit le solde à l'entier le plus proche.</span><span class="sxs-lookup"><span data-stu-id="0cbfa-115">The legal entity wants to use a rounding method that rounds the balance to the nearest 1.00.</span></span> <span data-ttu-id="0cbfa-116">L'utilisateur responsable de la comptabilité des taxes procède comme suit.</span><span class="sxs-lookup"><span data-stu-id="0cbfa-116">The user who is responsible for sales tax accounting performs the following steps.</span></span>

1.  <span data-ttu-id="0cbfa-117">Cliquez sur &gt; Taxes indirectes &gt; Taxe &gt; Administrations fiscales</span><span class="sxs-lookup"><span data-stu-id="0cbfa-117">Click Tax &gt; Indirect taxes &gt; Sales tax &gt; Sales tax authorities</span></span>
2.  <span data-ttu-id="0cbfa-118">Sur l'organisateur Général, sélectionnez Normal dans le champ Type d'arrondi.</span><span class="sxs-lookup"><span data-stu-id="0cbfa-118">On the General FastTab, select Normal in the Rounding form field.</span></span>
3.  <span data-ttu-id="0cbfa-119">Entrez un nombre dans le champ Arrondi, saisissez 1,00.</span><span class="sxs-lookup"><span data-stu-id="0cbfa-119">In the Round-off field, enter 1.00.</span></span>
4.  <span data-ttu-id="0cbfa-120">Au moment de payer les taxes à l'administration fiscale, ouvrez la page Régler et valider la taxe.</span><span class="sxs-lookup"><span data-stu-id="0cbfa-120">When it is time to pay the sales taxes to the tax authority, open the Settle and post sales tax page.</span></span> <span data-ttu-id="0cbfa-121">(Cliquez sur &gt; Déclarations &gt; Taxe &gt; Régler et valider la taxe.)</span><span class="sxs-lookup"><span data-stu-id="0cbfa-121">(Click Tax &gt; Declarations &gt; Sales tax &gt; Settle and post sales tax.)</span></span>
5.  <span data-ttu-id="0cbfa-122">Dans le compte de règlement de la taxe, le montant de l'impôt à payer de 98 765,43 est arrondi à 98 765.</span><span class="sxs-lookup"><span data-stu-id="0cbfa-122">On the sales tax settlement account, the tax liability amount of 98,765.43 is rounded to 98,765.</span></span>

<span data-ttu-id="0cbfa-123">Le tableau suivant montre comment un montant de 98 765,43 est arrondi à l'aide de chaque méthode d'arrondi disponible dans le champ Type d'arrondi de la page Administrations fiscales.</span><span class="sxs-lookup"><span data-stu-id="0cbfa-123">The following table shows how an amount of 98,765.43 is rounded by using each rounding method that is available in the Rounding form field in the Sales tax authorities page.</span></span>

| <span data-ttu-id="0cbfa-124">Option du type d'arrondi</span><span class="sxs-lookup"><span data-stu-id="0cbfa-124">Rounding form option</span></span>                | <span data-ttu-id="0cbfa-125">Valeur d'arrondi = 0,01</span><span class="sxs-lookup"><span data-stu-id="0cbfa-125">Round-off value = 0.01</span></span> | <span data-ttu-id="0cbfa-126">Valeur d'arrondi = 0,10</span><span class="sxs-lookup"><span data-stu-id="0cbfa-126">Round-off value = 0.10</span></span> | <span data-ttu-id="0cbfa-127">Valeur d'arrondi = 1,00</span><span class="sxs-lookup"><span data-stu-id="0cbfa-127">Round-off value = 1.00</span></span> | <span data-ttu-id="0cbfa-128">Valeur d'arrondi = 100,00</span><span class="sxs-lookup"><span data-stu-id="0cbfa-128">Round-off value = 100.00</span></span> |
|-------------------------------------|------------------------|------------------------|------------------------|--------------------------|
| <span data-ttu-id="0cbfa-129">Standard</span><span class="sxs-lookup"><span data-stu-id="0cbfa-129">Normal</span></span>                              | <span data-ttu-id="0cbfa-130">98 765,43</span><span class="sxs-lookup"><span data-stu-id="0cbfa-130">98,765.43</span></span>              | <span data-ttu-id="0cbfa-131">98 765,40</span><span class="sxs-lookup"><span data-stu-id="0cbfa-131">98,765.40</span></span>              | <span data-ttu-id="0cbfa-132">98 765,00</span><span class="sxs-lookup"><span data-stu-id="0cbfa-132">98,765.00</span></span>              | <span data-ttu-id="0cbfa-133">98 800,00</span><span class="sxs-lookup"><span data-stu-id="0cbfa-133">98,800.00</span></span>                |
| <span data-ttu-id="0cbfa-134">Inférieur</span><span class="sxs-lookup"><span data-stu-id="0cbfa-134">Downward</span></span>                            | <span data-ttu-id="0cbfa-135">98 765,43</span><span class="sxs-lookup"><span data-stu-id="0cbfa-135">98,765.43</span></span>              | <span data-ttu-id="0cbfa-136">98 765,40</span><span class="sxs-lookup"><span data-stu-id="0cbfa-136">98,765.40</span></span>              | <span data-ttu-id="0cbfa-137">98 765,00</span><span class="sxs-lookup"><span data-stu-id="0cbfa-137">98,765.00</span></span>              | <span data-ttu-id="0cbfa-138">98 700,00</span><span class="sxs-lookup"><span data-stu-id="0cbfa-138">98,700.00</span></span>                |
| <span data-ttu-id="0cbfa-139">Supérieur</span><span class="sxs-lookup"><span data-stu-id="0cbfa-139">Rounding-up</span></span>                         | <span data-ttu-id="0cbfa-140">98 765,43</span><span class="sxs-lookup"><span data-stu-id="0cbfa-140">98,765.43</span></span>              | <span data-ttu-id="0cbfa-141">98 765,50</span><span class="sxs-lookup"><span data-stu-id="0cbfa-141">98,765.50</span></span>              | <span data-ttu-id="0cbfa-142">98 766,00</span><span class="sxs-lookup"><span data-stu-id="0cbfa-142">98,766.00</span></span>              | <span data-ttu-id="0cbfa-143">98 800,00</span><span class="sxs-lookup"><span data-stu-id="0cbfa-143">98,800.00</span></span>                |
| <span data-ttu-id="0cbfa-144">Avantage, pour un solde créditeur</span><span class="sxs-lookup"><span data-stu-id="0cbfa-144">Own advantage, for a credit balance</span></span> | <span data-ttu-id="0cbfa-145">98 765,43</span><span class="sxs-lookup"><span data-stu-id="0cbfa-145">98,765.43</span></span>              | <span data-ttu-id="0cbfa-146">98 765,40</span><span class="sxs-lookup"><span data-stu-id="0cbfa-146">98,765.40</span></span>              | <span data-ttu-id="0cbfa-147">98 765,00</span><span class="sxs-lookup"><span data-stu-id="0cbfa-147">98,765.00</span></span>              | <span data-ttu-id="0cbfa-148">98 700,00</span><span class="sxs-lookup"><span data-stu-id="0cbfa-148">98,700.00</span></span>                |
| <span data-ttu-id="0cbfa-149">Avantage, pour un solde débiteur</span><span class="sxs-lookup"><span data-stu-id="0cbfa-149">Own advantage, for a debit balance</span></span>  | <span data-ttu-id="0cbfa-150">98,765.43</span><span class="sxs-lookup"><span data-stu-id="0cbfa-150">98,765.43</span></span>              | <span data-ttu-id="0cbfa-151">98,765.50</span><span class="sxs-lookup"><span data-stu-id="0cbfa-151">98,765.50</span></span>              | <span data-ttu-id="0cbfa-152">98,766.00</span><span class="sxs-lookup"><span data-stu-id="0cbfa-152">98,766.00</span></span>              | <span data-ttu-id="0cbfa-153">98,800.00</span><span class="sxs-lookup"><span data-stu-id="0cbfa-153">98,800.00</span></span>                |


### <a name="no-rounding-at-all-since-the-round-off-is-000"></a><span data-ttu-id="0cbfa-154">Aucun arrondi du tout, car la précision d'arrondi est 0,00</span><span class="sxs-lookup"><span data-stu-id="0cbfa-154">No rounding at all, since the round-off is 0.00</span></span>

<span data-ttu-id="0cbfa-155">round(1,0151, 0,00) = 1,0151 round(1,0149, 0,00) = 1,0149</span><span class="sxs-lookup"><span data-stu-id="0cbfa-155">round(1.0151, 0.00) = 1.0151 round(1.0149, 0.00) = 1.0149</span></span>

### <a name="normal-round-and-round-precision-is-001"></a><span data-ttu-id="0cbfa-156">Arrondi normal, et précision d'arrondi 0,01</span><span class="sxs-lookup"><span data-stu-id="0cbfa-156">Normal round, and round precision is 0.01</span></span>

<table>
  <tr>
    <td><span data-ttu-id="0cbfa-157">Arrondi</span><span class="sxs-lookup"><span data-stu-id="0cbfa-157">Rounding</span></span>
    </td>
    <td><span data-ttu-id="0cbfa-158">Processus de calcul</span><span class="sxs-lookup"><span data-stu-id="0cbfa-158">Calculation process</span></span>
    </td>
  </tr>
    <tr>
    <td><span data-ttu-id="0cbfa-159">round(1,015, 0,01) = 1,02</span><span class="sxs-lookup"><span data-stu-id="0cbfa-159">round(1.015, 0.01) = 1.02</span></span>
    </td>
    <td>
      <ol>
        <li><span data-ttu-id="0cbfa-160">round(1,015 / 0,01, 0) = round(101,5, 0) = 102</span><span class="sxs-lookup"><span data-stu-id="0cbfa-160">round(1.015 / 0.01, 0) = round(101.5, 0) = 102</span></span>
        </li>
        <li><span data-ttu-id="0cbfa-161">102 \* 0,01 = 1,02</span><span class="sxs-lookup"><span data-stu-id="0cbfa-161">102 \* 0.01 = 1.02</span></span>
        </li>
      </ol>
    </td>
  </tr>
    <tr>
    <td><span data-ttu-id="0cbfa-162">round(1,014, 0,01) = 1,01</span><span class="sxs-lookup"><span data-stu-id="0cbfa-162">round(1.014, 0.01) = 1.01</span></span>
    </td>
    <td> <ol>
        <li><span data-ttu-id="0cbfa-163">round(1,014 / 0,01, 0) = round(101,4, 0) = 101</span><span class="sxs-lookup"><span data-stu-id="0cbfa-163">round(1.014 / 0.01, 0) = round(101.4, 0) = 101</span></span>
        </li>
        <li><span data-ttu-id="0cbfa-164">101 \* 0,01 = 1,01</span><span class="sxs-lookup"><span data-stu-id="0cbfa-164">101 \* 0.01 = 1.01</span></span>
        </li>
      </ol>
    </td>
  </tr>
    <tr>
    <td><span data-ttu-id="0cbfa-165">round(1,011, 0,02) = 1,02</span><span class="sxs-lookup"><span data-stu-id="0cbfa-165">round(1.011, 0.02) = 1.02</span></span>
    </td>
    <td> <ol>
        <li><span data-ttu-id="0cbfa-166">round(1,011 / 0,02, 0) = round(50,55, 0) = 51</span><span class="sxs-lookup"><span data-stu-id="0cbfa-166">round(1.011 / 0.02, 0) = round(50.55, 0) = 51</span></span>
        </li>
        <li><span data-ttu-id="0cbfa-167">51 \* 0,02 = 1,02</span><span class="sxs-lookup"><span data-stu-id="0cbfa-167">51 \* 0.02 = 1.02</span></span>
        </li>
      </ol>
    </td>
  </tr>
    <tr>
    <td><span data-ttu-id="0cbfa-168">round(1,009, 0,02) = 1,00</span><span class="sxs-lookup"><span data-stu-id="0cbfa-168">round(1.009, 0.02) = 1.00</span></span>
    </td>
    <td> <ol>
        <li><span data-ttu-id="0cbfa-169">round(1,009 / 0,02, 0) = round(50,45, 0) = 50</span><span class="sxs-lookup"><span data-stu-id="0cbfa-169">round(1.009 / 0.02, 0) = round(50.45, 0) = 50</span></span>
        </li>
        <li><span data-ttu-id="0cbfa-170">50 \* 0,02 = 1,00</span><span class="sxs-lookup"><span data-stu-id="0cbfa-170">50 \* 0.02 = 1.00</span></span>
        </li>
      </ol>
    </td>
  </tr>
</table>

> [!NOTE]                                                                                  
> <span data-ttu-id="0cbfa-171">Si vous sélectionnez Avantage, l'arrondi est toujours à l'avantage de l'entité juridique.</span><span class="sxs-lookup"><span data-stu-id="0cbfa-171">If you select Own advantage, the rounding is always to the advantage of the legal entity.</span></span> 

<span data-ttu-id="0cbfa-172">Pour plus d'informations, voir les rubriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="0cbfa-172">For more information, see the following topics:</span></span>
- [<span data-ttu-id="0cbfa-173">Vue d'ensemble des taxes</span><span class="sxs-lookup"><span data-stu-id="0cbfa-173">Sales tax overview</span></span>](indirect-taxes-overview.md)
- [<span data-ttu-id="0cbfa-174">Créer un paiement de taxe</span><span class="sxs-lookup"><span data-stu-id="0cbfa-174">Create a sales tax payment</span></span>](tasks/create-sales-tax-payment.md)
- [<span data-ttu-id="0cbfa-175">Créer des transactions de taxe sur les documents</span><span class="sxs-lookup"><span data-stu-id="0cbfa-175">Create sales transactions on documents</span></span>](tasks/create-sales-tax-transactions-documents.md)
- [<span data-ttu-id="0cbfa-176">Afficher les transactions de taxe validées</span><span class="sxs-lookup"><span data-stu-id="0cbfa-176">View posted sales tax transactions</span></span>](tasks/view-posted-sales-tax-transactions.md)
- [<span data-ttu-id="0cbfa-177">Fonction round</span><span class="sxs-lookup"><span data-stu-id="0cbfa-177">round Function</span></span>](https://msdn.microsoft.com/library/aa850656.aspx)


