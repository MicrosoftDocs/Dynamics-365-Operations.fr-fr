---
title: La taxe n'est pas calculée ou le montant de la taxe est égal à zéro
description: Cette rubrique fournit des informations sur la résolution des problèmes qui peuvent vous aider lorsque le montant de la taxe est égal à 0 (zéro) ou lorsque la taxe n'est pas calculée.
author: shtao
ms.date: 04/01/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application user
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: wangchen
ms.search.validFrom: 2021-04-01
ms.dyn365.ops.version: 10.0.1
ms.openlocfilehash: ead979081692d4dcee9812c89f5f10c7879d3f7e
ms.sourcegitcommit: 57668404d61359b33e0c0280f2f7c4eb829b1ed2
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/27/2021
ms.locfileid: "5947638"
---
# <a name="tax-isnt-calculated-or-the-tax-amount-is-zero"></a><span data-ttu-id="37463-103">La taxe n'est pas calculée ou le montant de la taxe est égal à zéro</span><span class="sxs-lookup"><span data-stu-id="37463-103">Tax isn't calculated or the tax amount is zero</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="37463-104">Une transaction peut avoir un montant de ligne différent de 0 (zéro), mais la taxe n'est pas calculée ou le montant de la taxe calculé est de 0.</span><span class="sxs-lookup"><span data-stu-id="37463-104">A transaction might have a line amount that isn't 0 (zero), but either tax isn't calculated or the calculated tax amount is 0.</span></span> <span data-ttu-id="37463-105">Pour résoudre ce problème, suivez les étapes des sections suivantes selon les besoins.</span><span class="sxs-lookup"><span data-stu-id="37463-105">To troubleshoot this issue, follow the steps in the following sections as required.</span></span>

## <a name="verify-that-tax-codes-are-correctly-selected-by-the-transaction"></a><span data-ttu-id="37463-106">Vérifiez que les codes de taxe sont correctement sélectionnés par la transaction</span><span class="sxs-lookup"><span data-stu-id="37463-106">Verify that tax codes are correctly selected by the transaction</span></span>

<span data-ttu-id="37463-107">Si la transaction ne sélectionne pas les bons codes de taxe, ou si elle ne sélectionne aucun code de taxe, les taxes ne seront pas calculées dessus.</span><span class="sxs-lookup"><span data-stu-id="37463-107">If the transaction doesn't select the correct tax codes, or if it doesn't select any tax codes, taxes won't be calculated on it.</span></span> <span data-ttu-id="37463-108">Pour vérifier que les codes de taxe sont correctement sélectionnés par la transaction, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="37463-108">Follow these steps to verify that tax codes are correctly selected by the transaction.</span></span> 

1. <span data-ttu-id="37463-109">Sur la ligne de transaction, sur le raccourci **Détails de ligne** de l'onglet **Paramétrage**, dans la section **Taxe**, vérifiez que les groupes de taxes corrects sont sélectionnés dans les champs **Groupe de taxes d’article** et **Groupe de taxes**.</span><span class="sxs-lookup"><span data-stu-id="37463-109">On the transaction line, on the **Line details** FastTab, on the **Setup** tab, in the **Sales tax** section, verify that the correct tax groups are selected in the **Item sales tax group** and **Sales tax group** fields.</span></span> <span data-ttu-id="37463-110">Si les groupes de taxes corrects ne sont pas sélectionnés, sélectionnez-les.</span><span class="sxs-lookup"><span data-stu-id="37463-110">If the correct tax groups aren't selected, select them.</span></span>

    <span data-ttu-id="37463-111">[![Champs Groupe de taxes d’article et Groupe de taxes](./media/tax-not-calculated-tax-amount-zero-Picture1.png)](./media/tax-not-calculated-tax-amount-zero-Picture1.png)</span><span class="sxs-lookup"><span data-stu-id="37463-111">[![Item sales tax group and Sales tax group fields](./media/tax-not-calculated-tax-amount-zero-Picture1.png)](./media/tax-not-calculated-tax-amount-zero-Picture1.png)</span></span>

2. <span data-ttu-id="37463-112">Accédez à **Taxe** \> **Taxes indirectes** \> **Taxe** \> **Groupes de taxes**.</span><span class="sxs-lookup"><span data-stu-id="37463-112">Go to **Tax** \> **Indirect taxes** \> **Sales tax** \> **Sales tax groups**.</span></span>
3. <span data-ttu-id="37463-113">Sélectionnez le groupe de taxes de vente approprié, puis sur le raccourci **Paramétrage**, notez le code de taxe dans le champ **Code taxe**.</span><span class="sxs-lookup"><span data-stu-id="37463-113">Select the appropriate sales tax group, and then, on the **Setup** FastTab, make a note of the tax code in the **Sales tax code** field.</span></span>

    <span data-ttu-id="37463-114">[![Page Groupes de taxes](./media/tax-not-calculated-tax-amount-zero-Picture2.png)](./media/tax-not-calculated-tax-amount-zero-Picture2.png)</span><span class="sxs-lookup"><span data-stu-id="37463-114">[![Sales tax groups page](./media/tax-not-calculated-tax-amount-zero-Picture2.png)](./media/tax-not-calculated-tax-amount-zero-Picture2.png)</span></span>

4. <span data-ttu-id="37463-115">Accédez à **Taxe** \> **Taxes indirectes** \> **Taxe** \> **Groupes de taxes d’article**.</span><span class="sxs-lookup"><span data-stu-id="37463-115">Go to **Tax** \> **Indirect taxes** \> **Sales tax** \> **Item sales tax groups**.</span></span>
5. <span data-ttu-id="37463-116">Sélectionnez le groupe de taxes sur les articles approprié, puis sur le raccourci **Paramétrage**, vérifiez que le code de taxe dans le champ **Code taxe** correspond à celui du groupe de taxes de vente.</span><span class="sxs-lookup"><span data-stu-id="37463-116">Select the appropriate item sales tax group, and then, on the **Setup** FastTab, verify that the tax code in the **Sales tax code** field matches the tax code of the sales tax group.</span></span>

    <span data-ttu-id="37463-117">[![Page Groupes de taxes d’article](./media/tax-not-calculated-tax-amount-zero-Picture3.png)](./media/tax-not-calculated-tax-amount-zero-Picture3.png)</span><span class="sxs-lookup"><span data-stu-id="37463-117">[![Item sales tax groups page](./media/tax-not-calculated-tax-amount-zero-Picture3.png)](./media/tax-not-calculated-tax-amount-zero-Picture3.png)</span></span>

6. <span data-ttu-id="37463-118">Si les codes de taxe ne correspondent pas, mettez à jour le code de taxe de vente pour l'un des groupes.</span><span class="sxs-lookup"><span data-stu-id="37463-118">If the tax codes don't match, update the sales tax code for one of the groups.</span></span>

## <a name="verify-that-the-selected-tax-codes-arent-exempt-and-that-they-have-the-correct-tax-rate-value"></a><span data-ttu-id="37463-119">Vérifiez que les codes de taxe sélectionnés ne sont pas exonérés et qu'ils ont la valeur de taux de taxe correcte</span><span class="sxs-lookup"><span data-stu-id="37463-119">Verify that the selected tax codes aren't exempt and that they have the correct tax rate value</span></span>

<span data-ttu-id="37463-120">Si les codes de taxe sont exonérés ou si le taux de taxe est 0 (zéro), le résultat du calcul de la taxe sera 0.</span><span class="sxs-lookup"><span data-stu-id="37463-120">If the tax codes are exempt, or if the tax rate is 0 (zero), the tax calculation result will be 0.</span></span> <span data-ttu-id="37463-121">Suivez ces étapes pour déterminer si les codes de taxe sélectionnés sont exonérés et pour vérifier que le taux de taxe correct leur est appliqué.</span><span class="sxs-lookup"><span data-stu-id="37463-121">Follow these steps to determine whether the selected tax codes are exempt and to verify that the correct tax rate is applied to them.</span></span>

1. <span data-ttu-id="37463-122">Accédez à **Taxe** \> **Taxes indirectes** \> **Taxe** \> **Groupes de taxes**.</span><span class="sxs-lookup"><span data-stu-id="37463-122">Go to **Tax** \> **Indirect taxes** \> **Sales tax** \> **Sales tax groups**.</span></span>
2. <span data-ttu-id="37463-123">Sélectionnez le groupe de taxes approprié, puis sur le raccourci **Paramétrage**, vérifiez que la case à cocher **Exonéré** est désactivée.</span><span class="sxs-lookup"><span data-stu-id="37463-123">Select the appropriate sales tax group, and then, on the **Setup** FastTab, verify that the **Exempt** check box is cleared.</span></span> <span data-ttu-id="37463-124">Si elle est cochée, décochez-la.</span><span class="sxs-lookup"><span data-stu-id="37463-124">If it's selected, clear it.</span></span>

    <span data-ttu-id="37463-125">[![Case à cocher Exonéré sur la page Groupes de taxes](./media/tax-not-calculated-tax-amount-zero-Picture4.png)](./media/tax-not-calculated-tax-amount-zero-Picture4.png)</span><span class="sxs-lookup"><span data-stu-id="37463-125">[![Exempt check box on the Sales tax groups page](./media/tax-not-calculated-tax-amount-zero-Picture4.png)](./media/tax-not-calculated-tax-amount-zero-Picture4.png)</span></span>

3. <span data-ttu-id="37463-126">Accédez à **Taxe** \> **Taxes indirectes** \> **Taxe** \> **Codes taxe**.</span><span class="sxs-lookup"><span data-stu-id="37463-126">Go to **Tax** \> **Indirect taxes** \> **Sales tax** \> **Sales tax codes**.</span></span>
4. <span data-ttu-id="37463-127">Sélectionnez le code de taxe approprié, puis vérifiez que la valeur du taux de taxe dans le champ **Valeur** n'est pas 0 (zéro).</span><span class="sxs-lookup"><span data-stu-id="37463-127">Select the appropriate sales tax code, and then verify that the tax rate value in the **Value** field isn't 0 (zero).</span></span> <span data-ttu-id="37463-128">S'il est égal à 0, mettez à jour le champ afin qu'il soit défini sur le taux de taxe correct.</span><span class="sxs-lookup"><span data-stu-id="37463-128">If it's 0, update the field so that it's set to the correct tax rate.</span></span>

    <span data-ttu-id="37463-129">[![Champ Valeur sur la page Valeurs de code taxe](./media/tax-not-calculated-tax-amount-zero-Picture5.png)](./media/tax-not-calculated-tax-amount-zero-Picture5.png)</span><span class="sxs-lookup"><span data-stu-id="37463-129">[![Value field on the Sales tax code values page](./media/tax-not-calculated-tax-amount-zero-Picture5.png)](./media/tax-not-calculated-tax-amount-zero-Picture5.png)</span></span>

## <a name="determine-whether-zero-is-the-correct-tax-amount"></a><span data-ttu-id="37463-130">Déterminer si zéro est le montant de taxe correct</span><span class="sxs-lookup"><span data-stu-id="37463-130">Determine whether zero is the correct tax amount</span></span>

<span data-ttu-id="37463-131">Dans certains scénarios, un montant de taxe de 0 (zéro) est correct.</span><span class="sxs-lookup"><span data-stu-id="37463-131">In some scenarios, a tax amount of 0 (zero) is correct.</span></span> <span data-ttu-id="37463-132">Suivez ces étapes pour déterminer si 0 est le montant de taxe correct pour votre transaction.</span><span class="sxs-lookup"><span data-stu-id="37463-132">Follow these steps to determine whether 0 is the correct tax amount for your transaction.</span></span>

1. <span data-ttu-id="37463-133">Accédez à **Comptabilité** \> **Paramétrage de la comptabilité** \> **Paramètres de comptabilité**.</span><span class="sxs-lookup"><span data-stu-id="37463-133">Go to **General ledger** \> **Ledger setup** \> **General ledger parameters**.</span></span>
2. <span data-ttu-id="37463-134">Sur l'onglet **Taxe**, dans le champ **Méthode de calcul**, vérifiez que **Total** est sélectionné.</span><span class="sxs-lookup"><span data-stu-id="37463-134">On the **Sales tax** tab, in the **Calculation method** field, verify that **Total** is selected.</span></span>

    <span data-ttu-id="37463-135">[![Champ Méthode de calcul sur la page Paramètres de Comptabilité](./media/tax-not-calculated-tax-amount-zero-Picture6.png)](./media/tax-not-calculated-tax-amount-zero-Picture6.png)</span><span class="sxs-lookup"><span data-stu-id="37463-135">[![Calculation method field on the General ledger parameters page](./media/tax-not-calculated-tax-amount-zero-Picture6.png)](./media/tax-not-calculated-tax-amount-zero-Picture6.png)</span></span>

3. <span data-ttu-id="37463-136">Accédez à **Taxe** \> **Taxes indirectes** \> **Taxe** \> **Codes taxe**.</span><span class="sxs-lookup"><span data-stu-id="37463-136">Go to **Tax** \> **Indirect taxes** \> **Sales tax** \> **Sales tax codes**.</span></span>
4. <span data-ttu-id="37463-137">Sélectionnez le code de taxe approprié, sélectionnez **Calcul** \> **Base marginale**, et vérifiez que la base marginale est définie sur **Montant HT du solde de la facture** ou **Facture totale, autres taxe incluses**.</span><span class="sxs-lookup"><span data-stu-id="37463-137">Select the appropriate sales tax code, select **Calculation** \> **Marginal base**, and verify that the marginal base is set to **Net amount of invoice balance** or **Invoice total incl. other sales tax amounts**.</span></span> <span data-ttu-id="37463-138">Pour plus d'informations, consultez [Facture totale, autres taxe incluses](marginal-base-field.md#invoice-total-incl-other-sales-tax-amounts).</span><span class="sxs-lookup"><span data-stu-id="37463-138">For more information, see the [Invoice total incl. other sales tax amounts](marginal-base-field.md#invoice-total-incl-other-sales-tax-amounts).</span></span>
5. <span data-ttu-id="37463-139">Si les valeurs correctes sont définies aux étapes 2 et 4, déterminez si le montant total de la transaction est 0 (zéro).</span><span class="sxs-lookup"><span data-stu-id="37463-139">If the correct values are set in steps 2 and 4, determine whether the total amount of the transaction is 0 (zero).</span></span> <span data-ttu-id="37463-140">Si le montant total est de 0, un montant de taxe de 0 est le résultat attendu.</span><span class="sxs-lookup"><span data-stu-id="37463-140">If the total amount is 0, a tax amount of 0 is the expected result.</span></span> <span data-ttu-id="37463-141">Étant donné que le calcul de la taxe est basé sur le montant total du solde de la facture et que ce montant n'est pas ligne par ligne, le montant de la taxe de 0 sera attribué à chaque ligne après le calcul de la taxe.</span><span class="sxs-lookup"><span data-stu-id="37463-141">Because the tax calculation is based on the total amount of the invoice balance, and that amount isn't line by line, the tax amount of 0 will be allocated to each line after the tax calculation.</span></span>

## <a name="determine-whether-customization-exists"></a><span data-ttu-id="37463-142">Déterminer si la personnalisation existe</span><span class="sxs-lookup"><span data-stu-id="37463-142">Determine whether customization exists</span></span>

<span data-ttu-id="37463-143">Si vous avez terminé les étapes des sections précédentes mais que vous n'avez trouvé aucun problème, déterminez s'il existe une personnalisation.</span><span class="sxs-lookup"><span data-stu-id="37463-143">If you've completed the steps in the previous sections but have found no issue, determine whether customization exists.</span></span> <span data-ttu-id="37463-144">Si aucune personnalisation n'existe, créez une demande de service Microsoft pour une assistance supplémentaire.</span><span class="sxs-lookup"><span data-stu-id="37463-144">If no customization exists, create a Microsoft service request for further support.</span></span>

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
