---
title: Prendre plus que la remise calculée pour un paiement fournisseur
description: Cet article vous fait parcourir un scénario où un escompte de règlement est pris pour un montant qui est supérieur à la remise qui était initialement disponible sur la facture. Ce scénario peut se produire si une organisation parvient à un accord avec le fournisseur pour payer un montant plus bas sur la facture.
author: abruer
ms.date: 08/22/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerJournalTransVendPaym, VendOpenTrans
audience: Application User
ms.reviewer: roschlom
ms.custom: 14281
ms.assetid: 7f0a4197-95dd-4969-ade9-154815cf659e
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 62f2088ff04a0ef5ffe6ffe47b85f47e6957264d
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5810244"
---
# <a name="take-more-than-the-calculated-discount-for-a-vendor-payment"></a><span data-ttu-id="66aaa-104">Prendre plus que la remise calculée pour un paiement fournisseur</span><span class="sxs-lookup"><span data-stu-id="66aaa-104">Take more than the calculated discount for a vendor payment</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="66aaa-105">Cet article vous fait parcourir un scénario où un escompte de règlement est pris pour un montant qui est supérieur à la remise qui était initialement disponible sur la facture.</span><span class="sxs-lookup"><span data-stu-id="66aaa-105">This article walks you through a scenario where a cash discount is taken for an amount that is more than the discount that was originally available on the invoice.</span></span> <span data-ttu-id="66aaa-106">Ce scénario peut se produire si une organisation parvient à un accord avec le fournisseur pour payer un montant plus bas sur la facture.</span><span class="sxs-lookup"><span data-stu-id="66aaa-106">This scenario might occur if an organization comes to an agreement with the vendor to pay a smaller amount on the invoice.</span></span> 

<span data-ttu-id="66aaa-107">Le fournisseur 3051 accorde à Fabrikam un escompte de règlement de 4 % si la facture est payée sous sept jours.</span><span class="sxs-lookup"><span data-stu-id="66aaa-107">Vendor 3051 gives Fabrikam a cash discount of 4 percent if an invoice is paid in seven days.</span></span> <span data-ttu-id="66aaa-108">Le 29 juin, April entre une facture d’un montant de 1 000,00.</span><span class="sxs-lookup"><span data-stu-id="66aaa-108">On June 29, April enters an invoice for 1,000.00.</span></span> <span data-ttu-id="66aaa-109">Le fournisseur permet à April de bénéficier d’une remise de 60,00 au lieu de la remise par défaut de 40,00 disponible pour la facture.</span><span class="sxs-lookup"><span data-stu-id="66aaa-109">The vendor lets April take a discount of 60.00 instead of the default discount of 40.00 that is available for the invoice.</span></span> <span data-ttu-id="66aaa-110">April enregistre un paiement unique à l’aide du journal des paiements Achats.</span><span class="sxs-lookup"><span data-stu-id="66aaa-110">April records a one-off payment by using the Accounts payable payment journal.</span></span> <span data-ttu-id="66aaa-111">Elle entre le fournisseur pour le paiement puis ouvre la page **Régler les transactions**.</span><span class="sxs-lookup"><span data-stu-id="66aaa-111">She enters the vendor for the payment and then opens the **Settle transactions** page.</span></span> <span data-ttu-id="66aaa-112">Elle marque la facture et remplace la valeur du champ **Montant de l’escompte de règlement** par **60,00**.</span><span class="sxs-lookup"><span data-stu-id="66aaa-112">She marks the invoice and changes the value in the **Cash discount amount** field to **60.00**.</span></span>

| <span data-ttu-id="66aaa-113">Marquer</span><span class="sxs-lookup"><span data-stu-id="66aaa-113">Mark</span></span>     | <span data-ttu-id="66aaa-114">Utiliser un escompte de règlement</span><span class="sxs-lookup"><span data-stu-id="66aaa-114">Use cash discount</span></span> | <span data-ttu-id="66aaa-115">N° document</span><span class="sxs-lookup"><span data-stu-id="66aaa-115">Voucher</span></span>   | <span data-ttu-id="66aaa-116">Compte</span><span class="sxs-lookup"><span data-stu-id="66aaa-116">Account</span></span> | <span data-ttu-id="66aaa-117">Date</span><span class="sxs-lookup"><span data-stu-id="66aaa-117">Date</span></span>      | <span data-ttu-id="66aaa-118">Date d’échéance</span><span class="sxs-lookup"><span data-stu-id="66aaa-118">Due date</span></span>  | <span data-ttu-id="66aaa-119">Facture</span><span class="sxs-lookup"><span data-stu-id="66aaa-119">Invoice</span></span> | <span data-ttu-id="66aaa-120">Montant dans la devise de transaction</span><span class="sxs-lookup"><span data-stu-id="66aaa-120">Amount in transaction currency</span></span> | <span data-ttu-id="66aaa-121">Devise</span><span class="sxs-lookup"><span data-stu-id="66aaa-121">Currency</span></span> | <span data-ttu-id="66aaa-122">Montant à régler</span><span class="sxs-lookup"><span data-stu-id="66aaa-122">Amount to settle</span></span> |
|----------|-------------------|-----------|---------|-----------|-----------|---------|--------------------------------|----------|------------------|
| <span data-ttu-id="66aaa-123">Sélectionné</span><span class="sxs-lookup"><span data-stu-id="66aaa-123">Selected</span></span> | <span data-ttu-id="66aaa-124">Standard</span><span class="sxs-lookup"><span data-stu-id="66aaa-124">Normal</span></span>            | <span data-ttu-id="66aaa-125">Inv-10040</span><span class="sxs-lookup"><span data-stu-id="66aaa-125">Inv-10040</span></span> | <span data-ttu-id="66aaa-126">3051</span><span class="sxs-lookup"><span data-stu-id="66aaa-126">3051</span></span>    | <span data-ttu-id="66aaa-127">6/29/2015</span><span class="sxs-lookup"><span data-stu-id="66aaa-127">6/29/2015</span></span> | <span data-ttu-id="66aaa-128">7/29/2015</span><span class="sxs-lookup"><span data-stu-id="66aaa-128">7/29/2015</span></span> | <span data-ttu-id="66aaa-129">10040</span><span class="sxs-lookup"><span data-stu-id="66aaa-129">10040</span></span>   | <span data-ttu-id="66aaa-130">1 000,00</span><span class="sxs-lookup"><span data-stu-id="66aaa-130">1,000.00</span></span>                       | <span data-ttu-id="66aaa-131">USD</span><span class="sxs-lookup"><span data-stu-id="66aaa-131">USD</span></span>      | <span data-ttu-id="66aaa-132">940,00</span><span class="sxs-lookup"><span data-stu-id="66aaa-132">940.00</span></span>           |

<span data-ttu-id="66aaa-133">Les informations de remise s’affichent au bas de la page **Règlement des transactions**.</span><span class="sxs-lookup"><span data-stu-id="66aaa-133">Discount information appears at the bottom of the **Settle transactions** page.</span></span>

| <span data-ttu-id="66aaa-134">Champ</span><span class="sxs-lookup"><span data-stu-id="66aaa-134">Field</span></span>                        | <span data-ttu-id="66aaa-135">Valeur</span><span class="sxs-lookup"><span data-stu-id="66aaa-135">Value</span></span>     |
|------------------------------|-----------|
| <span data-ttu-id="66aaa-136">Date d’escompte de règlement</span><span class="sxs-lookup"><span data-stu-id="66aaa-136">Cash discount date</span></span>           | <span data-ttu-id="66aaa-137">7/12/2015</span><span class="sxs-lookup"><span data-stu-id="66aaa-137">7/12/2015</span></span> |
| <span data-ttu-id="66aaa-138">Montant de l’escompte de règlement</span><span class="sxs-lookup"><span data-stu-id="66aaa-138">Cash discount amount</span></span>         | <span data-ttu-id="66aaa-139">60.00</span><span class="sxs-lookup"><span data-stu-id="66aaa-139">60.00</span></span>     |
| <span data-ttu-id="66aaa-140">Utiliser un escompte de règlement</span><span class="sxs-lookup"><span data-stu-id="66aaa-140">Use cash discount</span></span>            | <span data-ttu-id="66aaa-141">Standard</span><span class="sxs-lookup"><span data-stu-id="66aaa-141">Normal</span></span>    |
| <span data-ttu-id="66aaa-142">Escompte de règlement appliqué</span><span class="sxs-lookup"><span data-stu-id="66aaa-142">Cash discount taken</span></span>          | <span data-ttu-id="66aaa-143">0,00</span><span class="sxs-lookup"><span data-stu-id="66aaa-143">0.00</span></span>      |
| <span data-ttu-id="66aaa-144">Montant de l’escompte de règlement à accepter</span><span class="sxs-lookup"><span data-stu-id="66aaa-144">Cash discount amount to take</span></span> | <span data-ttu-id="66aaa-145">60,00</span><span class="sxs-lookup"><span data-stu-id="66aaa-145">60.00</span></span>     |

<span data-ttu-id="66aaa-146">Elle valide ensuite le journal des paiements.</span><span class="sxs-lookup"><span data-stu-id="66aaa-146">April posts the payment journal.</span></span> <span data-ttu-id="66aaa-147">La facture est entièrement réglée avec un paiement de 940,00 et une remise de 60,00.</span><span class="sxs-lookup"><span data-stu-id="66aaa-147">The invoice is fully settled by using a payment of 940.00 and a discount of 60.00.</span></span>





[!INCLUDE[footer-include](../../includes/footer-banner.md)]