---
title: "Chèques postdatés"
description: "Cet article fournit des informations sur la prise en charge des chèques postdatés dans Microsoft Dynamics 365 for Finance and Operations, Enterprise edition. Les chèques postdatés sont des chèques émis à des fins d'émission ou de réception de paiements à une date future. Par conséquent, le chèque ne peut pas être encaissé avant la date spécifiée."
author: twheeloc
manager: AnnBe
ms.date: 01/12/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: VendPostDatedChecks, CustPostDatedChecks
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 21741
ms.assetid: 4eb7c7da-1e6b-4d35-9f41-373b66103229
ms.search.region: Global
ms.author: leguo
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 029511634e56aec7fdd91bad9441cd12951fbd8d
ms.openlocfilehash: 4462b9b9df9a14deba05c43d3f87321d263f42f6
ms.contentlocale: fr-fr
ms.lasthandoff: 01/17/2018

---

# <a name="postdated-checks"></a><span data-ttu-id="24624-105">Chèques postdatés</span><span class="sxs-lookup"><span data-stu-id="24624-105">Postdated checks</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="24624-106">Cet article fournit des informations sur la prise en charge des chèques postdatés dans Microsoft Dynamics 365 for Finance and Operations, Enterprise edition.</span><span class="sxs-lookup"><span data-stu-id="24624-106">This article provides information about support for postdated checks in Microsoft Dynamics 365 for Finance and Operations, Enterprise edition.</span></span> <span data-ttu-id="24624-107">Les chèques postdatés sont des chèques émis à des fins d'émission ou de réception de paiements à une date future.</span><span class="sxs-lookup"><span data-stu-id="24624-107">Postdated checks are checks that are issued to make and receive payments on a future date.</span></span> <span data-ttu-id="24624-108">Par conséquent, le chèque ne peut pas être encaissé avant la date spécifiée.</span><span class="sxs-lookup"><span data-stu-id="24624-108">Therefore, the check can't be cashed until the specified date.</span></span>

<span data-ttu-id="24624-109">Microsoft Dynamics 365 for Finance and Operations prend en charge le cycle de gestion complet pour les chèques postdatés dans Comptabilité client et Comptabilité fournisseur, comme indiqué dans le tableau suivant.</span><span class="sxs-lookup"><span data-stu-id="24624-109">Microsoft Dynamics 365 for Finance and Operations supports the full management cycle for postdated checks in both Accounts receivable and Accounts payable, as shown in the following table.</span></span>
<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="24624-110">Scénario</span><span class="sxs-lookup"><span data-stu-id="24624-110">Scenario</span></span></th>
<th><span data-ttu-id="24624-111">Détails</span><span class="sxs-lookup"><span data-stu-id="24624-111">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="24624-112">Paramétrage de chèques postdatés</span><span class="sxs-lookup"><span data-stu-id="24624-112">Set up postdated checks</span></span></td>
<td><span data-ttu-id="24624-113">Vous devez paramétrer un nouveau mode de paiement, puis spécifier la routine de paiement sur des comptes de compensation pour les chèques émis, les chèques reçus, et la retenue à la source.</span><span class="sxs-lookup"><span data-stu-id="24624-113">You must set up a new payment method, and specify the payment routine for clearing accounts for issued checks, received checks, and withholding tax.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="24624-114">Enregistrement et validation d'un chèque postdaté pour un fournisseur</span><span class="sxs-lookup"><span data-stu-id="24624-114">Register and post a postdated check for a vendor</span></span></td>
<td><span data-ttu-id="24624-115">Enregistrez les détails d'un chèque postdaté avant sa remise à un fournisseur.</span><span class="sxs-lookup"><span data-stu-id="24624-115">Register the details of a postdated check that you issue to a vendor.</span></span> <span data-ttu-id="24624-116">Lorsque le paiement est validé, le passif du fournisseur est identifié, mais le compte bancaire n'est pas encore crédité.</span><span class="sxs-lookup"><span data-stu-id="24624-116">When the payment is posted, the vendor liability is recognized, but the bank account isn’t yet credit.</span></span> <span data-ttu-id="24624-117">Au lieu de cela, un compte de compensation est utilisé à cet effet.</span><span class="sxs-lookup"><span data-stu-id="24624-117">Instead, a clearing account is used for this purpose.</span></span> </td>
</tr>
<tr class="odd">
<td><span data-ttu-id="24624-118">Enregistrer et valider un chèque postdaté pour un client</span><span class="sxs-lookup"><span data-stu-id="24624-118">Register and post a postdated check for a customer</span></span></td>
<td><span data-ttu-id="24624-119">Enregistrez les informations relatives à un chèque postdaté reçu d'un client.</span><span class="sxs-lookup"><span data-stu-id="24624-119">Register the details of a postdated check that you receive from a customer.</span></span> <span data-ttu-id="24624-120">Lorsque le paiement est validé, le montant à recevoir du client est identifié, mais le compte bancaire n'est pas encore débité.</span><span class="sxs-lookup"><span data-stu-id="24624-120">When the payment is posted, the customer receivable is credit, but the bank account isn’t yet debit.</span></span> <span data-ttu-id="24624-121">Au lieu de cela, un compte de compensation est utilisé à cet effet.</span><span class="sxs-lookup"><span data-stu-id="24624-121">Instead, a clearing account is used for this purpose.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="24624-122">Enregistrement et validation d'un chèque postdaté de remplacement pour un client ou un fournisseur</span><span class="sxs-lookup"><span data-stu-id="24624-122">Register and post a replacement postdated check for a customer or a vendor</span></span></td>
<td>
<span data-ttu-id="24624-123">Si votre chèque d'origine à un fournisseur ou émis par un client est perdu ou endommagé, vous pouvez émettre un chèque postdaté de remplacement.</span><span class="sxs-lookup"><span data-stu-id="24624-123">If your original check to a vendor or from a customer is lost or damaged, you can issue a replacement postdated check.</span></span> <span data-ttu-id="24624-124">Lorsque vous enregistrez les détails du chèque, fournissez une référence au chèque d'origine et indiquez que celui-ci est remplacé par ce nouveau chèque.</span><span class="sxs-lookup"><span data-stu-id="24624-124">When you register the check details, provide a reference to the original check, and indicate that the new check is a replacement for the original.</span></span> <span data-ttu-id="24624-125">Vous pouvez également valider le chèque de remplacement.</span><span class="sxs-lookup"><span data-stu-id="24624-125">You can also post the replacement check.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="24624-126">Transfert d'un chèque client postdaté à un fournisseur</span><span class="sxs-lookup"><span data-stu-id="24624-126">Transfer a customer postdated check to a vendor</span></span></td>
<td><span data-ttu-id="24624-127">Lorsque vous recevez un chèque postdaté d'un client, vous pouvez le transférer à un fournisseur en tant que paiement.</span><span class="sxs-lookup"><span data-stu-id="24624-127">When you receive a postdated check from a customer, you can transfer that check to a vendor as a payment.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="24624-128">Règlement d'un chèque postdaté pour un client ou un fournisseur</span><span class="sxs-lookup"><span data-stu-id="24624-128">Settle a postdated check for a customer or a vendor</span></span></td>
<td><span data-ttu-id="24624-129">Réglez un chèque postdaté validé dans le compte d'attente d'un client ou d'un fournisseur lorsque le chèque est enfin échu.</span><span class="sxs-lookup"><span data-stu-id="24624-129">Settle a postdated check that is posted to a bridging account for a customer or a vendor when the check finally matures.</span></span> <span data-ttu-id="24624-130">Lorsque le chèque est réglé, la banque débite ou crédite finalement le compte de compensation utilisé précédemment.</span><span class="sxs-lookup"><span data-stu-id="24624-130">When the check is settled, the bank is finally debit or credit against the clearing account that was used earlier.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="24624-131">Annulation d'un chèque postdaté pour un fournisseur</span><span class="sxs-lookup"><span data-stu-id="24624-131">Cancel a postdated check for a vendor</span></span></td>
<td><span data-ttu-id="24624-132">Vous pouvez annuler un chèque postdaté validé dans les situations suivantes : - Le chèque est retourné par la banque.</span><span class="sxs-lookup"><span data-stu-id="24624-132">You can cancel a posted postdated check in these situations: - The check is returned by the bank.</span></span>
<span data-ttu-id="24624-133">- Le chèque est appliqué à une facture incorrecte.</span><span class="sxs-lookup"><span data-stu-id="24624-133">- The check is applied to an incorrect invoice.</span></span>
<span data-ttu-id="24624-134">- Le montant du chèque est réglé par un paiement en espèces.</span><span class="sxs-lookup"><span data-stu-id="24624-134">- A cash payment is made against the check.</span></span>
</td>
</tr>
<tr class="even">
<td><span data-ttu-id="24624-135">Arrêt du paiement d'un chèque postdaté</span><span class="sxs-lookup"><span data-stu-id="24624-135">Stop payment for a postdated check</span></span></td>
<td><span data-ttu-id="24624-136">Vous pouvez arrêter le paiement sur un chèque postdaté émis auprès d'un fournisseur pour diverses raisons (fonds insuffisants, modifications des conditions de l'accord avec le fournisseur, livraison de marchandises défectueuses par le fournisseur, retour de marchandises au fournisseur, etc.).</span><span class="sxs-lookup"><span data-stu-id="24624-136">You can stop payment on a postdated check that was issued to a vendor, for reasons such as not sufficient funds, changes in the terms of the agreement with the vendor, supply of defective goods by the vendor, or return of goods to the vendor.</span></span> <span data-ttu-id="24624-137">Seul le paiement des chèques non compensés peut être arrêté.</span><span class="sxs-lookup"><span data-stu-id="24624-137">You can stop payment only on checks that haven’t cleared.</span></span></td>
</tr>
</tbody>
</table>



<span data-ttu-id="24624-138">Pour plus d'informations, voir les rubriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="24624-138">For more information, see the following topics:</span></span>

[<span data-ttu-id="24624-139">Paramétrer des chèques postdatés</span><span class="sxs-lookup"><span data-stu-id="24624-139">Set up postdated checks</span></span>](tasks/set-up-postdated-checks.md)

[<span data-ttu-id="24624-140">Enregistrer et valider un chèque postdaté pour un client</span><span class="sxs-lookup"><span data-stu-id="24624-140">Register and post a postdated check for a customer</span></span>](tasks/register-post-postdated-check-customer.md)

[<span data-ttu-id="24624-141">Régler un chèque postdaté provenant d'un client</span><span class="sxs-lookup"><span data-stu-id="24624-141">Settle a postdated check from a customer</span></span>](tasks/settle-postdated-check-customer.md)

[<span data-ttu-id="24624-142">Enregistrer et valider un chèque postdaté pour un fournisseur</span><span class="sxs-lookup"><span data-stu-id="24624-142">Register and post a postdated check for a vendor</span></span>](tasks/register-post-postdated-check-vendor.md) 

[<span data-ttu-id="24624-143">Régler un chèque postdaté pour un fournisseur</span><span class="sxs-lookup"><span data-stu-id="24624-143">Settle a postdated check for a vendor</span></span>](tasks/settle-postdated-check-vendor.md)




