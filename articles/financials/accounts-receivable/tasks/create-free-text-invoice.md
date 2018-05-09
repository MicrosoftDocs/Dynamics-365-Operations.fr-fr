--- 
title: "Créer une facture financière"
description: "Ce guide de tâche illustre la création d'une facture financière."
author: mikefalkner
manager: AnnBe
ms.date: 10/26/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Operations
ms.search.region: Global
ms.author: mfalkner
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: 16fd3c6459389d20c59047d37ec8ca40424c62d2
ms.contentlocale: fr-fr
ms.lasthandoff: 05/08/2018

---
# <a name="create-a-free-text-invoice"></a><span data-ttu-id="c20ca-103">Créer une facture financière</span><span class="sxs-lookup"><span data-stu-id="c20ca-103">Create a free text invoice</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="c20ca-104">Ce guide de tâche illustre la création d'une facture financière.</span><span class="sxs-lookup"><span data-stu-id="c20ca-104">This task guide demonstrates creating a free text invoice.</span></span> <span data-ttu-id="c20ca-105">La société fictive USMF est citée en exemple dans cette tâche.</span><span class="sxs-lookup"><span data-stu-id="c20ca-105">This task uses the USMF demo company.</span></span>

1. <span data-ttu-id="c20ca-106">Accédez à Comptabilité client > Factures > Toutes factures financières.</span><span class="sxs-lookup"><span data-stu-id="c20ca-106">Go to Accounts receivable > Invoices > All free text invoices.</span></span>
2. <span data-ttu-id="c20ca-107">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="c20ca-107">Click New.</span></span>
3. <span data-ttu-id="c20ca-108">Sélectionnez une valeur dans le champ Compte client.</span><span class="sxs-lookup"><span data-stu-id="c20ca-108">In the Customer account field, select a value.</span></span>
    * <span data-ttu-id="c20ca-109">Le compte de facturation sera par défaut identique à celui utilisé pour le compte client.</span><span class="sxs-lookup"><span data-stu-id="c20ca-109">The invoice account will default to the same account used for the customer account.</span></span>   
    * <span data-ttu-id="c20ca-110">Le statut comptable commence par En cours si la facture n'est pas validée.</span><span class="sxs-lookup"><span data-stu-id="c20ca-110">The accounting status starts with In process if the invoice is not posted.</span></span>   
    * <span data-ttu-id="c20ca-111">Le numéro de facture sera affecté lors de la validation de la facture.</span><span class="sxs-lookup"><span data-stu-id="c20ca-111">The invoice number will be assigned when the invoice is posted.</span></span>  
    * <span data-ttu-id="c20ca-112">Si vous utilisez des mandats SEPA, le mandat de débit direct sera automatiquement complété avec un mandat lorsque vous sélectionnez le compte client.</span><span class="sxs-lookup"><span data-stu-id="c20ca-112">If you are using SEPA mandates, the direct debit mandate will be automatically populated with a mandate when you select the customer account.</span></span>  
4. <span data-ttu-id="c20ca-113">Dans le champ Description, entrez une valeur.</span><span class="sxs-lookup"><span data-stu-id="c20ca-113">In the Description field, type a value.</span></span>
5. <span data-ttu-id="c20ca-114">Spécifiez un numéro de compte sans dimensions dans le champ Compte principal.</span><span class="sxs-lookup"><span data-stu-id="c20ca-114">In the Main account field, specify an account number without dimensions.</span></span>
    * <span data-ttu-id="c20ca-115">Vous pouvez également entrer un ou plusieurs caractères pour le compte principal et utiliser la recherche pour trouver votre compte.</span><span class="sxs-lookup"><span data-stu-id="c20ca-115">You can also enter one or more characters for the main account and use the lookup to find your account.</span></span> <span data-ttu-id="c20ca-116">Vous entrerez des dimensions ultérieurement dans ce guide.</span><span class="sxs-lookup"><span data-stu-id="c20ca-116">You will enter dimensions later on in this guide.</span></span>  
6. <span data-ttu-id="c20ca-117">Développez le raccourci Détails de ligne afin de pouvoir ajouter des dimensions à votre compte principal.</span><span class="sxs-lookup"><span data-stu-id="c20ca-117">Expand the Line details fasttab so you can add dimensions to your main account.</span></span>
7. <span data-ttu-id="c20ca-118">Cliquez sur l'onglet Ligne de dimension financière.</span><span class="sxs-lookup"><span data-stu-id="c20ca-118">Click the Financial dimensions line tab.</span></span>
    * <span data-ttu-id="c20ca-119">Les dimensions concernent la ligne sélectionnée uniquement.</span><span class="sxs-lookup"><span data-stu-id="c20ca-119">The dimensions are for the selected line only.</span></span>    
    * <span data-ttu-id="c20ca-120">Le contenu du groupe de taxe provient du client.</span><span class="sxs-lookup"><span data-stu-id="c20ca-120">The sales tax group is populated from the customer.</span></span> <span data-ttu-id="c20ca-121">Si le client n'a pas de groupe de taxe, celui du compte principal est utilisé.</span><span class="sxs-lookup"><span data-stu-id="c20ca-121">If the customer does not have a sales tax group, the sales tax group from the main account is used.</span></span>  
    * <span data-ttu-id="c20ca-122">Le contenu du groupe de taxe des articles est rempli à partir du compte principal.</span><span class="sxs-lookup"><span data-stu-id="c20ca-122">The items sales tax group is populated from the main account.</span></span> <span data-ttu-id="c20ca-123">Si le compte principal n'a pas de groupe de taxe d'article, le groupe de taxe d'article des paramètres de taxe de comptabilité est utilisé.</span><span class="sxs-lookup"><span data-stu-id="c20ca-123">If the main account does not have an item sales tax group, then the item sales tax group in the General ledger sales tax parameters is used.</span></span>    
8. <span data-ttu-id="c20ca-124">Dans le champ Quantité, entrer un numéro.</span><span class="sxs-lookup"><span data-stu-id="c20ca-124">In the Quantity field, enter a number.</span></span>
    * <span data-ttu-id="c20ca-125">La quantité est facultative.</span><span class="sxs-lookup"><span data-stu-id="c20ca-125">The quantity is optional.</span></span>  
9. <span data-ttu-id="c20ca-126">Entrez un nombre dans le champ Prix unitaire.</span><span class="sxs-lookup"><span data-stu-id="c20ca-126">In the Unit price field, enter a number.</span></span>
    * <span data-ttu-id="c20ca-127">Le prix unitaire est facultatif.</span><span class="sxs-lookup"><span data-stu-id="c20ca-127">The unit price is optional.</span></span>  
    * <span data-ttu-id="c20ca-128">Le montant est calculé comme suit : quantité multipliée par prix unitaire.</span><span class="sxs-lookup"><span data-stu-id="c20ca-128">The amount is calculated as the quantity times the unit price.</span></span> <span data-ttu-id="c20ca-129">Toutefois, vous pouvez remplacer ce calcul et entrer un montant.</span><span class="sxs-lookup"><span data-stu-id="c20ca-129">However, you can override that calculation and enter an amount.</span></span>  
10. <span data-ttu-id="c20ca-130">Cliquez sur Taxe pour afficher les taxes calculées pour votre facture.</span><span class="sxs-lookup"><span data-stu-id="c20ca-130">Click on Sales tax to view the sales tax calculated for your invoice.</span></span>
    * <span data-ttu-id="c20ca-131">Vous pouvez afficher les montants de taxe sur cette page ou remplacer les montants sous l'onglet Ajustement.</span><span class="sxs-lookup"><span data-stu-id="c20ca-131">View the sales tax amounts in this page or you can override the amounts on the Adjustment tab.</span></span>  
11. <span data-ttu-id="c20ca-132">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="c20ca-132">Click OK.</span></span>
12. <span data-ttu-id="c20ca-133">Cliquez sur Frais pour ajouter des frais à votre facture.</span><span class="sxs-lookup"><span data-stu-id="c20ca-133">Click Charges to add a charge to your invoice.</span></span> 
13. <span data-ttu-id="c20ca-134">Tapez une valeur dans le champ Codes frais.</span><span class="sxs-lookup"><span data-stu-id="c20ca-134">In the Charges code field, type a value.</span></span>
14. <span data-ttu-id="c20ca-135">Entrez un nombre dans le champ Valeur des frais.</span><span class="sxs-lookup"><span data-stu-id="c20ca-135">In the Charges value field, enter a number.</span></span>
15. <span data-ttu-id="c20ca-136">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="c20ca-136">Close the page.</span></span>
16. <span data-ttu-id="c20ca-137">Cliquez sur Totaux pour afficher les totaux et les détails de la facture de synthèse.</span><span class="sxs-lookup"><span data-stu-id="c20ca-137">Click Totals to view the summary invoice details and totals.</span></span>
17. <span data-ttu-id="c20ca-138">Cliquez sur Fermer.</span><span class="sxs-lookup"><span data-stu-id="c20ca-138">Click Close.</span></span>
18. <span data-ttu-id="c20ca-139">Cliquez sur Valider pour valider la facture.</span><span class="sxs-lookup"><span data-stu-id="c20ca-139">Click Post to post the invoice.</span></span> <span data-ttu-id="c20ca-140">Vous pourrez annuler avant de valider.</span><span class="sxs-lookup"><span data-stu-id="c20ca-140">You will be able to cancel before you post.</span></span>
    * <span data-ttu-id="c20ca-141">Pour modifier l'échéance d'impression de la facture : sélectionnez Actuel pour imprimer chaque facture dès qu'elle est mise à jour ou Après pour imprimer toutes les factures une fois qu'elles ont été mises à jour.</span><span class="sxs-lookup"><span data-stu-id="c20ca-141">To change the timing of your invoice printing:  Select Current to print each invoice as it is updated   or  Select After to print after all invoices have been updated.</span></span>  
    * <span data-ttu-id="c20ca-142">Si vous souhaitez modifier la manière dont la limite de crédit du client est activée avant la validation, modifiez le type de limite de crédit.</span><span class="sxs-lookup"><span data-stu-id="c20ca-142">If you want to change how the customer's credit limit is checked before posting, change the Credit limit type.</span></span>  
    * <span data-ttu-id="c20ca-143">Pour imprimer la facture, sélectionnez Oui.</span><span class="sxs-lookup"><span data-stu-id="c20ca-143">If you want to print the invoice, select Yes.</span></span>  
    * <span data-ttu-id="c20ca-144">Pour valider la facture, sélectionnez Oui.</span><span class="sxs-lookup"><span data-stu-id="c20ca-144">If you want to post the invoice, select Yes.</span></span> <span data-ttu-id="c20ca-145">Vous pouvez imprimer la facture sans la valider.</span><span class="sxs-lookup"><span data-stu-id="c20ca-145">You can print the invoice without posting.</span></span>  
19. <span data-ttu-id="c20ca-146">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="c20ca-146">Click OK.</span></span>


