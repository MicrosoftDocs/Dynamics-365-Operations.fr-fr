--- 
title: "Créer une facture financière"
description: "Cet article décrit comment créer une facture financière."
author: mikefalkner
manager: AnnBe
ms.date: 05/29/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Operations
ms.search.region: Global
ms.author: mfalkner
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: d9747ba144d56c9410846769e5465372c89ea111
ms.openlocfilehash: e6f89a6d77ff8e1cd88632df0d9a72915086ee1e
ms.contentlocale: fr-fr
ms.lasthandoff: 08/07/2018

---

# <a name="create-a-free-text-invoice"></a><span data-ttu-id="db5a4-103">Créer une facture financière</span><span class="sxs-lookup"><span data-stu-id="db5a4-103">Create a free text invoice</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="db5a4-104">Cet article décrit comment créer une facture financière.</span><span class="sxs-lookup"><span data-stu-id="db5a4-104">This article demonstrates how to create a free text invoice.</span></span> <span data-ttu-id="db5a4-105">Pour cette procédure, utilisez la société fictive USMF.</span><span class="sxs-lookup"><span data-stu-id="db5a4-105">For this procedure, use the USMF demo company.</span></span>

## <a name="create-a-free-text-invoice"></a><span data-ttu-id="db5a4-106">Créer une facture financière</span><span class="sxs-lookup"><span data-stu-id="db5a4-106">Create a free text invoice</span></span>

1. <span data-ttu-id="db5a4-107">Accédez à Comptabilité client > Factures > Toutes factures financières.</span><span class="sxs-lookup"><span data-stu-id="db5a4-107">Go to Accounts receivable > Invoices > All free text invoices.</span></span>
2. <span data-ttu-id="db5a4-108">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="db5a4-108">Click New.</span></span>
3. <span data-ttu-id="db5a4-109">Sélectionnez une valeur dans le champ Compte client.</span><span class="sxs-lookup"><span data-stu-id="db5a4-109">In the Customer account field, select a value.</span></span>
    * <span data-ttu-id="db5a4-110">Le compte de facturation sera par défaut identique à celui utilisé pour le compte client.</span><span class="sxs-lookup"><span data-stu-id="db5a4-110">The invoice account will default to the same account used for the customer account.</span></span>   
    * <span data-ttu-id="db5a4-111">Le statut comptable commence par En cours si la facture n'est pas validée.</span><span class="sxs-lookup"><span data-stu-id="db5a4-111">The accounting status starts with In process if the invoice is not posted.</span></span>   
    * <span data-ttu-id="db5a4-112">Le numéro de facture sera affecté lors de la validation de la facture.</span><span class="sxs-lookup"><span data-stu-id="db5a4-112">The invoice number will be assigned when the invoice is posted.</span></span>  
    * <span data-ttu-id="db5a4-113">Si vous utilisez des mandats SEPA, le mandat de débit direct sera automatiquement complété avec un mandat lorsque vous sélectionnez le compte client.</span><span class="sxs-lookup"><span data-stu-id="db5a4-113">If you are using SEPA mandates, the direct debit mandate will be automatically populated with a mandate when you select the customer account.</span></span>  
4. <span data-ttu-id="db5a4-114">Dans le champ Description, entrez une valeur.</span><span class="sxs-lookup"><span data-stu-id="db5a4-114">In the Description field, type a value.</span></span>
5. <span data-ttu-id="db5a4-115">Spécifiez un numéro de compte sans dimensions dans le champ Compte principal.</span><span class="sxs-lookup"><span data-stu-id="db5a4-115">In the Main account field, specify an account number without dimensions.</span></span>
    * <span data-ttu-id="db5a4-116">Vous pouvez également entrer un ou plusieurs caractères pour le compte principal et utiliser la recherche pour trouver votre compte.</span><span class="sxs-lookup"><span data-stu-id="db5a4-116">You can also enter one or more characters for the main account and use the lookup to find your account.</span></span> <span data-ttu-id="db5a4-117">Vous entrerez des dimensions ultérieurement dans ce guide.</span><span class="sxs-lookup"><span data-stu-id="db5a4-117">You will enter dimensions later on in this guide.</span></span>  
6. <span data-ttu-id="db5a4-118">Développez le raccourci Détails de ligne afin de pouvoir ajouter des dimensions à votre compte principal.</span><span class="sxs-lookup"><span data-stu-id="db5a4-118">Expand the Line details fasttab so you can add dimensions to your main account.</span></span>
7. <span data-ttu-id="db5a4-119">Cliquez sur l'onglet Ligne de dimension financière.</span><span class="sxs-lookup"><span data-stu-id="db5a4-119">Click the Financial dimensions line tab.</span></span>
    * <span data-ttu-id="db5a4-120">Les dimensions concernent la ligne sélectionnée uniquement.</span><span class="sxs-lookup"><span data-stu-id="db5a4-120">The dimensions are for the selected line only.</span></span>    
    * <span data-ttu-id="db5a4-121">Le contenu du groupe de taxe provient du client.</span><span class="sxs-lookup"><span data-stu-id="db5a4-121">The sales tax group is populated from the customer.</span></span> <span data-ttu-id="db5a4-122">Si le client n'a pas de groupe de taxe, celui du compte principal est utilisé.</span><span class="sxs-lookup"><span data-stu-id="db5a4-122">If the customer does not have a sales tax group, the sales tax group from the main account is used.</span></span>  
    * <span data-ttu-id="db5a4-123">Le contenu du groupe de taxe des articles est rempli à partir du compte principal.</span><span class="sxs-lookup"><span data-stu-id="db5a4-123">The items sales tax group is populated from the main account.</span></span> <span data-ttu-id="db5a4-124">Si le compte principal n'a pas de groupe de taxe d'article, le groupe de taxe d'article des paramètres de taxe de comptabilité est utilisé.</span><span class="sxs-lookup"><span data-stu-id="db5a4-124">If the main account does not have an item sales tax group, then the item sales tax group in the General ledger sales tax parameters is used.</span></span>    
8. <span data-ttu-id="db5a4-125">Dans le champ Quantité, entrer un numéro.</span><span class="sxs-lookup"><span data-stu-id="db5a4-125">In the Quantity field, enter a number.</span></span>
    * <span data-ttu-id="db5a4-126">La quantité est facultative.</span><span class="sxs-lookup"><span data-stu-id="db5a4-126">The quantity is optional.</span></span>  
9. <span data-ttu-id="db5a4-127">Entrez un nombre dans le champ Prix unitaire.</span><span class="sxs-lookup"><span data-stu-id="db5a4-127">In the Unit price field, enter a number.</span></span>
    * <span data-ttu-id="db5a4-128">Le prix unitaire est facultatif.</span><span class="sxs-lookup"><span data-stu-id="db5a4-128">The unit price is optional.</span></span>  
    * <span data-ttu-id="db5a4-129">Le montant est calculé comme suit : quantité multipliée par prix unitaire.</span><span class="sxs-lookup"><span data-stu-id="db5a4-129">The amount is calculated as the quantity times the unit price.</span></span> <span data-ttu-id="db5a4-130">Toutefois, vous pouvez remplacer ce calcul et entrer un montant.</span><span class="sxs-lookup"><span data-stu-id="db5a4-130">However, you can override that calculation and enter an amount.</span></span>  
10. <span data-ttu-id="db5a4-131">Cliquez sur Taxe pour afficher les taxes calculées pour votre facture.</span><span class="sxs-lookup"><span data-stu-id="db5a4-131">Click on Sales tax to view the sales tax calculated for your invoice.</span></span>
    * <span data-ttu-id="db5a4-132">Vous pouvez afficher les montants de taxe sur cette page ou remplacer les montants sous l'onglet Ajustement.</span><span class="sxs-lookup"><span data-stu-id="db5a4-132">View the sales tax amounts in this page or you can override the amounts on the Adjustment tab.</span></span>  
11. <span data-ttu-id="db5a4-133">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="db5a4-133">Click OK.</span></span>
12. <span data-ttu-id="db5a4-134">Cliquez sur Frais pour ajouter des frais à votre facture.</span><span class="sxs-lookup"><span data-stu-id="db5a4-134">Click Charges to add a charge to your invoice.</span></span> 
13. <span data-ttu-id="db5a4-135">Tapez une valeur dans le champ Codes frais.</span><span class="sxs-lookup"><span data-stu-id="db5a4-135">In the Charges code field, type a value.</span></span>
14. <span data-ttu-id="db5a4-136">Entrez un nombre dans le champ Valeur des frais.</span><span class="sxs-lookup"><span data-stu-id="db5a4-136">In the Charges value field, enter a number.</span></span>
15. <span data-ttu-id="db5a4-137">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="db5a4-137">Close the page.</span></span>
16. <span data-ttu-id="db5a4-138">Cliquez sur Totaux pour afficher les totaux et les détails de la facture de synthèse.</span><span class="sxs-lookup"><span data-stu-id="db5a4-138">Click Totals to view the summary invoice details and totals.</span></span>
17. <span data-ttu-id="db5a4-139">Cliquez sur Fermer.</span><span class="sxs-lookup"><span data-stu-id="db5a4-139">Click Close.</span></span>
18. <span data-ttu-id="db5a4-140">Cliquez sur Valider pour valider la facture.</span><span class="sxs-lookup"><span data-stu-id="db5a4-140">Click Post to post the invoice.</span></span> <span data-ttu-id="db5a4-141">Vous pourrez annuler avant de valider.</span><span class="sxs-lookup"><span data-stu-id="db5a4-141">You will be able to cancel before you post.</span></span>
    * <span data-ttu-id="db5a4-142">Pour modifier l'échéance d'impression de la facture : sélectionnez Actuel pour imprimer chaque facture dès qu'elle est mise à jour ou Après pour imprimer toutes les factures une fois qu'elles ont été mises à jour.</span><span class="sxs-lookup"><span data-stu-id="db5a4-142">To change the timing of your invoice printing:  Select Current to print each invoice as it is updated   or  Select After to print after all invoices have been updated.</span></span>  
    * <span data-ttu-id="db5a4-143">Si vous souhaitez modifier la manière dont la limite de crédit du client est activée avant la validation, modifiez le type de limite de crédit.</span><span class="sxs-lookup"><span data-stu-id="db5a4-143">If you want to change how the customer's credit limit is checked before posting, change the Credit limit type.</span></span>  
    * <span data-ttu-id="db5a4-144">Pour imprimer la facture, sélectionnez Oui.</span><span class="sxs-lookup"><span data-stu-id="db5a4-144">If you want to print the invoice, select Yes.</span></span>  
    * <span data-ttu-id="db5a4-145">Pour valider la facture, sélectionnez Oui.</span><span class="sxs-lookup"><span data-stu-id="db5a4-145">If you want to post the invoice, select Yes.</span></span> <span data-ttu-id="db5a4-146">Vous pouvez imprimer la facture sans la valider.</span><span class="sxs-lookup"><span data-stu-id="db5a4-146">You can print the invoice without posting.</span></span>  
19. <span data-ttu-id="db5a4-147">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="db5a4-147">Click OK.</span></span>

## <a name="copy-lines"></a><span data-ttu-id="db5a4-148">Copier lignes</span><span class="sxs-lookup"><span data-stu-id="db5a4-148">Copy lines</span></span>
<span data-ttu-id="db5a4-149">Pour copier des lignes de la facture financière, sélectionnez une ou plusieurs lignes, puis cliquez sur Copier les lignes sélectionnées.</span><span class="sxs-lookup"><span data-stu-id="db5a4-149">To copy lines on the free text invoice, select one or more lines and then click Copy selected lines.</span></span> <span data-ttu-id="db5a4-150">Vous pouvez spécifier le nombre de copies à effectuer, et vous pouvez également copier des notes et des pièces jointes.</span><span class="sxs-lookup"><span data-stu-id="db5a4-150">You can specify the number of copies that you want to make, and you can also copy notes and attachments.</span></span> <span data-ttu-id="db5a4-151">Vous pouvez copier les répartitions ou autoriser leur recréation lors de la validation.</span><span class="sxs-lookup"><span data-stu-id="db5a4-151">You can copy the distributions or allow them to be recreated when you post.</span></span> <span data-ttu-id="db5a4-152">Une fois que vous copiez les lignes, vous pouvez modifier les informations au besoin.</span><span class="sxs-lookup"><span data-stu-id="db5a4-152">Once you copy the lines, you can edit the information as needed.</span></span> 

## <a name="create-a-free-text-invoice-from-a-template"></a><span data-ttu-id="db5a4-153">Créer une facture financière à partir d'un modèle</span><span class="sxs-lookup"><span data-stu-id="db5a4-153">Create a free text invoice from a template</span></span>
<span data-ttu-id="db5a4-154">Vous pouvez créer une facture financière à partir d'un modèle.</span><span class="sxs-lookup"><span data-stu-id="db5a4-154">You can create a free text invoice from a template.</span></span> <span data-ttu-id="db5a4-155">Lorsque vous sélectionnez Nouveau à partir d'un modèle sous l'onglet Facture, vous pouvez sélectionner un nom de modèle et le compte client pour la nouvelle facture financière.</span><span class="sxs-lookup"><span data-stu-id="db5a4-155">When you select New from template from the Invoice tab, you can select a template name and the customer account for the new free text invoice.</span></span> <span data-ttu-id="db5a4-156">Vous pouvez également choisir d'utiliser les valeurs par défaut telles que les conditions de paiement et le mode de paiement du client ou utiliser les valeurs enregistrées avec le modèle.</span><span class="sxs-lookup"><span data-stu-id="db5a4-156">You can also choose to default values such as the terms of payment and method of payment from the customer or use the values that were saved with the template.</span></span> <span data-ttu-id="db5a4-157">Une facture financière est créée et vous pouvez modifier les valeurs qui lui sont associées.</span><span class="sxs-lookup"><span data-stu-id="db5a4-157">A new free text invoice will be created and you can edit the values in that invoice.</span></span> 


