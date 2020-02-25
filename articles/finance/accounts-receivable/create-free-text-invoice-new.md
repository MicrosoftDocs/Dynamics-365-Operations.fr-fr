---
title: Créer une facture financière
description: Cette rubrique explique comment créer des factures financières.
author: mikefalkner
manager: AnnBe
ms.date: 08/24/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Operations
ms.search.region: Global
ms.author: mfalkner
ms.search.validFrom: 2018-08-30
ms.dyn365.ops.version: 8.0.4
ms.openlocfilehash: 909dd5bcaf1fa3b82adb44d265e312f9acc607d2
ms.sourcegitcommit: 9168621ca9b5061c65f3e05dbc5918b6a11d53d5
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/31/2020
ms.locfileid: "3000068"
---
# <a name="create-a-free-text-invoice"></a><span data-ttu-id="e0e0d-103">Créer une facture financière</span><span class="sxs-lookup"><span data-stu-id="e0e0d-103">Create a free text invoice</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="e0e0d-104">Cette rubrique explique comment créer des factures financières.</span><span class="sxs-lookup"><span data-stu-id="e0e0d-104">This topic explains how to create free text invoices.</span></span> <span data-ttu-id="e0e0d-105">Pour la procédure, utilisez la société fictive **USMF**.</span><span class="sxs-lookup"><span data-stu-id="e0e0d-105">For the procedure, use the **USMF** demo company.</span></span>

## <a name="create-a-free-text-invoice"></a><span data-ttu-id="e0e0d-106">Créer une facture financière</span><span class="sxs-lookup"><span data-stu-id="e0e0d-106">Create a free text invoice</span></span>

1. <span data-ttu-id="e0e0d-107">Allez dans **Comptabilité client \> Factures \> Toutes factures financières**.</span><span class="sxs-lookup"><span data-stu-id="e0e0d-107">Go to **Accounts receivable \> Invoices \> All free text invoices**.</span></span>
2. <span data-ttu-id="e0e0d-108">Sélectionnez **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="e0e0d-108">Select **New**.</span></span>
3. <span data-ttu-id="e0e0d-109">Dans le champ **Compte client**, sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="e0e0d-109">In the **Customer account** field, select a value.</span></span>

    * <span data-ttu-id="e0e0d-110">Par défaut, le compte sélectionné comme compte client est utilisé comme compte de facturation.</span><span class="sxs-lookup"><span data-stu-id="e0e0d-110">By default, the account that is selected as the customer account is used as the invoice account.</span></span>
    * <span data-ttu-id="e0e0d-111">Si la facture n'est pas validée, le statut comptable commence par **En cours**.</span><span class="sxs-lookup"><span data-stu-id="e0e0d-111">If the invoice isn't posted, the accounting status starts with **In process**.</span></span>
    * <span data-ttu-id="e0e0d-112">Le numéro de facture sera affecté lors de la validation de la facture.</span><span class="sxs-lookup"><span data-stu-id="e0e0d-112">The invoice number will be assigned when the invoice is posted.</span></span>
    * <span data-ttu-id="e0e0d-113">Si vous utilisez des mandats SEPA (Espace unique de paiement en euros), le mandat de débit direct est automatiquement entré lorsque vous sélectionnez le compte client.</span><span class="sxs-lookup"><span data-stu-id="e0e0d-113">If you're using Single Euro Payments Area (SEPA) mandates, the direct debit mandate is automatically entered when you select the customer account.</span></span>

4. <span data-ttu-id="e0e0d-114">Dans le champ **Description**, entrez une valeur.</span><span class="sxs-lookup"><span data-stu-id="e0e0d-114">In the **Description** field, enter a value.</span></span>
5. <span data-ttu-id="e0e0d-115">Dans le champ **Compte principal**, spécifiez un numéro de compte sans dimensions.</span><span class="sxs-lookup"><span data-stu-id="e0e0d-115">In the **Main account** field, specify an account number that doesn't have dimensions.</span></span> <span data-ttu-id="e0e0d-116">Vous entrerez des dimensions plus loin dans cette rubrique.</span><span class="sxs-lookup"><span data-stu-id="e0e0d-116">You will enter dimensions later in this topic.</span></span>

    <span data-ttu-id="e0e0d-117">Vous pouvez également entrer un ou plusieurs caractères pour le compte principal et utiliser la fonction de recherche pour trouver le compte.</span><span class="sxs-lookup"><span data-stu-id="e0e0d-117">You can also enter one or more characters for the main account, and use the lookup to find the account.</span></span>

6. <span data-ttu-id="e0e0d-118">Sélectionnez l'organisateur **Détails de ligne** pour ajouter des dimensions au compte principal.</span><span class="sxs-lookup"><span data-stu-id="e0e0d-118">Select the **Line details** FastTab to add dimensions to the main account.</span></span>
7. <span data-ttu-id="e0e0d-119">Sélectionnez l'onglet **Ligne de dimension financière**.</span><span class="sxs-lookup"><span data-stu-id="e0e0d-119">Select the **Financial dimensions line** tab.</span></span>

    * <span data-ttu-id="e0e0d-120">Les dimensions concernent la ligne sélectionnée uniquement.</span><span class="sxs-lookup"><span data-stu-id="e0e0d-120">The dimensions are for the selected line only.</span></span>
    * <span data-ttu-id="e0e0d-121">Le groupe de taxe est renseigné à partir du client.</span><span class="sxs-lookup"><span data-stu-id="e0e0d-121">The sales tax group is filled in from the customer.</span></span> <span data-ttu-id="e0e0d-122">Si le client n'a pas de groupe de taxe, celui du compte principal est utilisé.</span><span class="sxs-lookup"><span data-stu-id="e0e0d-122">If the customer doesn't have a sales tax group, the sales tax group from the main account is used.</span></span>
    * <span data-ttu-id="e0e0d-123">Le groupe de taxe d'article est renseigné à partir du compte principal.</span><span class="sxs-lookup"><span data-stu-id="e0e0d-123">The items sales tax group is filled in from the main account.</span></span> <span data-ttu-id="e0e0d-124">Si le compte principal n'a pas de groupe de taxe d'article, celui spécifié dans les paramètres de taxe du module Comptabilité est utilisé.</span><span class="sxs-lookup"><span data-stu-id="e0e0d-124">If the main account doesn't have an item sales tax group, the item sales tax group that is specified in the sales tax parameters in General ledger is used.</span></span>

8. <span data-ttu-id="e0e0d-125">Facultatif : dans le champ **Quantité**, entrez un nombre.</span><span class="sxs-lookup"><span data-stu-id="e0e0d-125">Optional: In the **Quantity** field, enter a number.</span></span>
9. <span data-ttu-id="e0e0d-126">Facultatif : dans le champ **Prix unitaire**, entrez un nombre.</span><span class="sxs-lookup"><span data-stu-id="e0e0d-126">Optional: In the **Unit price** field, enter a number.</span></span>

    <span data-ttu-id="e0e0d-127">Le montant est calculé comme suit : quantité multipliée par prix unitaire.</span><span class="sxs-lookup"><span data-stu-id="e0e0d-127">The amount is calculated as the quantity times the unit price.</span></span> <span data-ttu-id="e0e0d-128">Toutefois, vous pouvez remplacer ce calcul en entrant un montant.</span><span class="sxs-lookup"><span data-stu-id="e0e0d-128">However, you can override that calculation by entering an amount.</span></span>

10. <span data-ttu-id="e0e0d-129">Sélectionnez **Taxe** pour afficher la taxe calculée pour la facture.</span><span class="sxs-lookup"><span data-stu-id="e0e0d-129">Select **Sales tax** to view the sales tax that is calculated for the invoice.</span></span>

    <span data-ttu-id="e0e0d-130">Vous pouvez afficher les montants de taxe sur cette page ou remplacer les montants sous l'onglet **Ajustement**.</span><span class="sxs-lookup"><span data-stu-id="e0e0d-130">You can view the sales tax amounts on this page, or you can override the amounts on the **Adjustment** tab.</span></span>

11. <span data-ttu-id="e0e0d-131">Sélectionnez **OK**.</span><span class="sxs-lookup"><span data-stu-id="e0e0d-131">Select **OK**.</span></span>
12. <span data-ttu-id="e0e0d-132">Sélectionnez **Frais** pour ajouter des frais à la facture.</span><span class="sxs-lookup"><span data-stu-id="e0e0d-132">Select **Charges** to add a charge to the invoice.</span></span>
13. <span data-ttu-id="e0e0d-133">Dans le champ **Code frais**, entrez une valeur.</span><span class="sxs-lookup"><span data-stu-id="e0e0d-133">In the **Charges code** field, enter a value.</span></span>
14. <span data-ttu-id="e0e0d-134">Dans le champ **Valeur des frais**, entrez un nombre.</span><span class="sxs-lookup"><span data-stu-id="e0e0d-134">In the **Charges value** field, enter a number.</span></span>
15. <span data-ttu-id="e0e0d-135">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="e0e0d-135">Close the page.</span></span>
16. <span data-ttu-id="e0e0d-136">Sélectionnez **Totaux** pour afficher un résumé des détails et des totaux de la facture.</span><span class="sxs-lookup"><span data-stu-id="e0e0d-136">Select **Totals** to view a summary of the invoice details and totals.</span></span>
17. <span data-ttu-id="e0e0d-137">Sélectionnez **Fermer**.</span><span class="sxs-lookup"><span data-stu-id="e0e0d-137">Select **Close**.</span></span>
18. <span data-ttu-id="e0e0d-138">Sélectionnez **Valider** pour valider la facture.</span><span class="sxs-lookup"><span data-stu-id="e0e0d-138">Select **Post** to post the invoice.</span></span> <span data-ttu-id="e0e0d-139">Vous aurez toujours la possibilité d'annuler l'opération avant de la valider réellement.</span><span class="sxs-lookup"><span data-stu-id="e0e0d-139">You will still have an opportunity to cancel before you actually post.</span></span>

    * <span data-ttu-id="e0e0d-140">Vous pouvez modifier l'échéance d'impression de la facture.</span><span class="sxs-lookup"><span data-stu-id="e0e0d-140">You can change the timing of invoice printing.</span></span> <span data-ttu-id="e0e0d-141">Sélectionnez **Actuel** pour imprimer chaque facture dès qu'elle est mise à jour.</span><span class="sxs-lookup"><span data-stu-id="e0e0d-141">Select **Current** to print each invoice as it's updated.</span></span> <span data-ttu-id="e0e0d-142">Sélectionnez **Après** pour imprimer toutes les factures une fois qu'elles ont été mises à jour.</span><span class="sxs-lookup"><span data-stu-id="e0e0d-142">Select **After** to print after all invoices have been updated.</span></span>
    * <span data-ttu-id="e0e0d-143">Pour modifier la façon dont la limite de crédit du client est vérifiée avant la validation de la facture, modifiez la valeur dans le champ **Type de limite de crédit**.</span><span class="sxs-lookup"><span data-stu-id="e0e0d-143">To change how the customer's credit limit is verified before the invoice is posted, change the value in the **Credit limit type** field.</span></span>
    * <span data-ttu-id="e0e0d-144">Pour imprimer la facture, définissez l'option sur **Oui**.</span><span class="sxs-lookup"><span data-stu-id="e0e0d-144">To print the invoice, set the option to **Yes**.</span></span>
    * <span data-ttu-id="e0e0d-145">Pour valider la facture, définissez l'option sur **Oui**.</span><span class="sxs-lookup"><span data-stu-id="e0e0d-145">To post the invoice, set the option to **Yes**.</span></span> <span data-ttu-id="e0e0d-146">Vous pouvez imprimer la facture sans la valider.</span><span class="sxs-lookup"><span data-stu-id="e0e0d-146">You can print the invoice without posting it.</span></span>

19. <span data-ttu-id="e0e0d-147">Sélectionnez **OK**.</span><span class="sxs-lookup"><span data-stu-id="e0e0d-147">Select **OK**.</span></span>

## <a name="copy-lines"></a><span data-ttu-id="e0e0d-148">Copier lignes</span><span class="sxs-lookup"><span data-stu-id="e0e0d-148">Copy lines</span></span>
<span data-ttu-id="e0e0d-149">Pour copier des lignes d'une facture financière, sélectionnez une ou plusieurs lignes, puis sélectionnez **Copier les lignes sélectionnées**.</span><span class="sxs-lookup"><span data-stu-id="e0e0d-149">To copy lines on a free text invoice, select one or more lines, and then select **Copy selected lines**.</span></span> <span data-ttu-id="e0e0d-150">Vous pouvez spécifier le nombre de copies à effectuer, et vous pouvez également copier des notes et des pièces jointes.</span><span class="sxs-lookup"><span data-stu-id="e0e0d-150">You can specify the number of copies to make, and you can also copy notes and attachments.</span></span> <span data-ttu-id="e0e0d-151">Vous pouvez copier les répartitions ou les recréer lors de la validation.</span><span class="sxs-lookup"><span data-stu-id="e0e0d-151">You can either copy the distributions or let them be re-created when you post.</span></span>

<span data-ttu-id="e0e0d-152">Après avoir copié des lignes, vous pouvez modifier les informations si nécessaire.</span><span class="sxs-lookup"><span data-stu-id="e0e0d-152">After you copy lines, you can edit the information as you require.</span></span>

## <a name="create-a-free-text-invoice-from-a-template"></a><span data-ttu-id="e0e0d-153">Créer une facture financière à partir d'un modèle</span><span class="sxs-lookup"><span data-stu-id="e0e0d-153">Create a free text invoice from a template</span></span>
<span data-ttu-id="e0e0d-154">Vous pouvez créer une facture financière à partir d'un modèle.</span><span class="sxs-lookup"><span data-stu-id="e0e0d-154">You can create a free text invoice from a template.</span></span> <span data-ttu-id="e0e0d-155">Lorsque vous sélectionnez **Nouveau à partir d'un modèle** sous l'onglet **Facture**, vous pouvez sélectionner un nom de modèle et le compte client pour la nouvelle facture financière.</span><span class="sxs-lookup"><span data-stu-id="e0e0d-155">When you select **New from template** on the **Invoice** tab, you can select a template name and the customer account for the new free text invoice.</span></span> <span data-ttu-id="e0e0d-156">Les valeurs par défaut telles que les conditions de paiement et le mode de paiement peuvent être automatiquement renseignées à partir du client, ou vous pouvez utiliser les valeurs enregistrées dans le modèle.</span><span class="sxs-lookup"><span data-stu-id="e0e0d-156">Default values, such as the terms of payment and method of payment, can be automatically filled in from the customer, or you can use the values that were saved in the template.</span></span>

<span data-ttu-id="e0e0d-157">Une facture financière est créée et vous pouvez modifier les valeurs si nécessaire.</span><span class="sxs-lookup"><span data-stu-id="e0e0d-157">A new free text invoice is created, and you can edit the values as you require.</span></span>
