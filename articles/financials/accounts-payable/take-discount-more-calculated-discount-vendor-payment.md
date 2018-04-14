---
title: "Utilisation d'une remise supérieure à la remise calculée pour un paiement fournisseur"
description: "Cet article vous fait parcourir un scénario où un escompte de règlement est pris pour un montant qui est supérieur à la remise qui était initialement disponible sur la facture. Ce scénario peut se produire si une organisation parvient à un accord avec le fournisseur pour payer un montant plus bas sur la facture."
author: ShivamPandey-msft
manager: AnnBe
ms.date: 08/22/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: LedgerJournalTransVendPaym, VendOpenTrans
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 14281
ms.assetid: 7f0a4197-95dd-4969-ade9-154815cf659e
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: 757a917311a9c0f1226a452e9fb59e05018f1635
ms.contentlocale: fr-fr
ms.lasthandoff: 04/13/2018

---

# <a name="take-a-discount-that-is-more-than-the-calculated-discount-for-a-vendor-payment"></a><span data-ttu-id="bded9-104">Utilisation d'une remise supérieure à la remise calculée pour un paiement fournisseur</span><span class="sxs-lookup"><span data-stu-id="bded9-104">Take a discount that is more than the calculated discount for a vendor payment</span></span>

[!INCLUDE [banner](../includes/banner.md)]

<span data-ttu-id="bded9-105">Cet article vous fait parcourir un scénario où un escompte de règlement est pris pour un montant qui est supérieur à la remise qui était initialement disponible sur la facture.</span><span class="sxs-lookup"><span data-stu-id="bded9-105">This article walks you through a scenario where a cash discount is taken for an amount that is more than the discount that was originally available on the invoice.</span></span> <span data-ttu-id="bded9-106">Ce scénario peut se produire si une organisation parvient à un accord avec le fournisseur pour payer un montant plus bas sur la facture.</span><span class="sxs-lookup"><span data-stu-id="bded9-106">This scenario might occur if an organization comes to an agreement with the vendor to pay a smaller amount on the invoice.</span></span> 

<span data-ttu-id="bded9-107">Le fournisseur 3051 accorde à Fabrikam un escompte de règlement de 4 % si la facture est payée sous sept jours.</span><span class="sxs-lookup"><span data-stu-id="bded9-107">Vendor 3051 gives Fabrikam a cash discount of 4 percent if an invoice is paid in seven days.</span></span> <span data-ttu-id="bded9-108">Le 29 juin, April entre une facture d'un montant de 1 000,00.</span><span class="sxs-lookup"><span data-stu-id="bded9-108">On June 29, April enters an invoice for 1,000.00.</span></span> <span data-ttu-id="bded9-109">Le fournisseur permet à April de bénéficier d'une remise de 60,00 au lieu de la remise par défaut de 40,00 disponible pour la facture.</span><span class="sxs-lookup"><span data-stu-id="bded9-109">The vendor lets April take a discount of 60.00 instead of the default discount of 40.00 that is available for the invoice.</span></span> <span data-ttu-id="bded9-110">April enregistre un paiement unique à l'aide du journal des paiements Achats.</span><span class="sxs-lookup"><span data-stu-id="bded9-110">April records a one-off payment by using the Accounts payable payment journal.</span></span> <span data-ttu-id="bded9-111">Elle entre le fournisseur pour le paiement puis ouvre la page **Régler les transactions**.</span><span class="sxs-lookup"><span data-stu-id="bded9-111">She enters the vendor for the payment and then opens the **Settle transactions** page.</span></span> <span data-ttu-id="bded9-112">Elle marque la facture et remplace la valeur du champ **Montant de l'escompte de règlement** par **60,00**.</span><span class="sxs-lookup"><span data-stu-id="bded9-112">She marks the invoice and changes the value in the **Cash discount amount** field to **60.00**.</span></span>

| <span data-ttu-id="bded9-113">Marquer</span><span class="sxs-lookup"><span data-stu-id="bded9-113">Mark</span></span>     | <span data-ttu-id="bded9-114">Utiliser un escompte de règlement</span><span class="sxs-lookup"><span data-stu-id="bded9-114">Use cash discount</span></span> | <span data-ttu-id="bded9-115">N° document</span><span class="sxs-lookup"><span data-stu-id="bded9-115">Voucher</span></span>   | <span data-ttu-id="bded9-116">Compte</span><span class="sxs-lookup"><span data-stu-id="bded9-116">Account</span></span> | <span data-ttu-id="bded9-117">Date</span><span class="sxs-lookup"><span data-stu-id="bded9-117">Date</span></span>      | <span data-ttu-id="bded9-118">Date d'échéance</span><span class="sxs-lookup"><span data-stu-id="bded9-118">Due date</span></span>  | <span data-ttu-id="bded9-119">Facture</span><span class="sxs-lookup"><span data-stu-id="bded9-119">Invoice</span></span> | <span data-ttu-id="bded9-120">Montant dans la devise de transaction</span><span class="sxs-lookup"><span data-stu-id="bded9-120">Amount in transaction currency</span></span> | <span data-ttu-id="bded9-121">Devise</span><span class="sxs-lookup"><span data-stu-id="bded9-121">Currency</span></span> | <span data-ttu-id="bded9-122">Montant à régler</span><span class="sxs-lookup"><span data-stu-id="bded9-122">Amount to settle</span></span> |
|----------|-------------------|-----------|---------|-----------|-----------|---------|--------------------------------|----------|------------------|
| <span data-ttu-id="bded9-123">Sélectionné</span><span class="sxs-lookup"><span data-stu-id="bded9-123">Selected</span></span> | <span data-ttu-id="bded9-124">Standard</span><span class="sxs-lookup"><span data-stu-id="bded9-124">Normal</span></span>            | <span data-ttu-id="bded9-125">Inv-10040</span><span class="sxs-lookup"><span data-stu-id="bded9-125">Inv-10040</span></span> | <span data-ttu-id="bded9-126">3051</span><span class="sxs-lookup"><span data-stu-id="bded9-126">3051</span></span>    | <span data-ttu-id="bded9-127">6/29/2015</span><span class="sxs-lookup"><span data-stu-id="bded9-127">6/29/2015</span></span> | <span data-ttu-id="bded9-128">7/29/2015</span><span class="sxs-lookup"><span data-stu-id="bded9-128">7/29/2015</span></span> | <span data-ttu-id="bded9-129">10040</span><span class="sxs-lookup"><span data-stu-id="bded9-129">10040</span></span>   | <span data-ttu-id="bded9-130">1 000,00</span><span class="sxs-lookup"><span data-stu-id="bded9-130">1,000.00</span></span>                       | <span data-ttu-id="bded9-131">USD</span><span class="sxs-lookup"><span data-stu-id="bded9-131">USD</span></span>      | <span data-ttu-id="bded9-132">940,00</span><span class="sxs-lookup"><span data-stu-id="bded9-132">940.00</span></span>           |

<span data-ttu-id="bded9-133">Les informations de remise s'affichent au bas de la page **Règlement des transactions**.</span><span class="sxs-lookup"><span data-stu-id="bded9-133">Discount information appears at the bottom of the **Settle transactions** page.</span></span>

|                              |           |
|------------------------------|-----------|
| <span data-ttu-id="bded9-134">Date d'escompte de règlement</span><span class="sxs-lookup"><span data-stu-id="bded9-134">Cash discount date</span></span>           | <span data-ttu-id="bded9-135">7/12/2015</span><span class="sxs-lookup"><span data-stu-id="bded9-135">7/12/2015</span></span> |
| <span data-ttu-id="bded9-136">Montant de l'escompte de règlement</span><span class="sxs-lookup"><span data-stu-id="bded9-136">Cash discount amount</span></span>         | <span data-ttu-id="bded9-137">60,00</span><span class="sxs-lookup"><span data-stu-id="bded9-137">60.00</span></span>     |
| <span data-ttu-id="bded9-138">Utiliser un escompte de règlement</span><span class="sxs-lookup"><span data-stu-id="bded9-138">Use cash discount</span></span>            | <span data-ttu-id="bded9-139">Standard</span><span class="sxs-lookup"><span data-stu-id="bded9-139">Normal</span></span>    |
| <span data-ttu-id="bded9-140">Escompte de règlement appliqué</span><span class="sxs-lookup"><span data-stu-id="bded9-140">Cash discount taken</span></span>          | <span data-ttu-id="bded9-141">0,00</span><span class="sxs-lookup"><span data-stu-id="bded9-141">0.00</span></span>      |
| <span data-ttu-id="bded9-142">Montant de l'escompte de règlement à accepter</span><span class="sxs-lookup"><span data-stu-id="bded9-142">Cash discount amount to take</span></span> | <span data-ttu-id="bded9-143">60,00</span><span class="sxs-lookup"><span data-stu-id="bded9-143">60.00</span></span>     |

<span data-ttu-id="bded9-144">Elle valide ensuite le journal des paiements.</span><span class="sxs-lookup"><span data-stu-id="bded9-144">April posts the payment journal.</span></span> <span data-ttu-id="bded9-145">La facture est entièrement réglée avec un paiement de 940,00 et une remise de 60,00.</span><span class="sxs-lookup"><span data-stu-id="bded9-145">The invoice is fully settled by using a payment of 940.00 and a discount of 60.00.</span></span>




