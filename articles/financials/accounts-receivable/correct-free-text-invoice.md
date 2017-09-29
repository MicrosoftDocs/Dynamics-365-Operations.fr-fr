---
title: "Correction d'une facture financière"
description: "Cet article explique comment corriger une facture financière validée et en émettre une nouvelle comme facture corrigée."
author: ShivamPandey-msft
manager: AnnBe
ms.date: 08/22/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: CustFreeInvoice
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 13991
ms.assetid: 2a0a4789-8619-4974-bef9-0923cc848420
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: a353db68c2223d62cd8e5048f0e953ed134c0803
ms.contentlocale: fr-fr
ms.lasthandoff: 08/29/2017

---

# <a name="correct-a-free-text-invoice"></a><span data-ttu-id="3d7a2-103">Correction d'une facture financière</span><span class="sxs-lookup"><span data-stu-id="3d7a2-103">Correct a free text invoice</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="3d7a2-104">Cet article explique comment corriger une facture financière validée et en émettre une nouvelle comme facture corrigée.</span><span class="sxs-lookup"><span data-stu-id="3d7a2-104">This article explains how to correct a free text invoice that has been posted and reissue it as a corrected invoice.</span></span>

<span data-ttu-id="3d7a2-105">Pour corriger une facture financière qui a déjà été validée, ouvrez la facture financière validée.</span><span class="sxs-lookup"><span data-stu-id="3d7a2-105">To correct a free text invoice that has already been posted, open the posted free text invoice.</span></span> <span data-ttu-id="3d7a2-106">Sur la page **Facture**, sélectionnez **Annuler**, puis **Corriger la facture**.</span><span class="sxs-lookup"><span data-stu-id="3d7a2-106">On the **Invoice** page, select **Cancel**, and then select **Correct invoice**.</span></span> <span data-ttu-id="3d7a2-107">Sélectionnez un code motif, ajoutez des commentaires, puis sélectionnez la date de la nouvelle facture corrigée.</span><span class="sxs-lookup"><span data-stu-id="3d7a2-107">Select a reason code, add comments, and select the date for new corrected invoice.</span></span> <span data-ttu-id="3d7a2-108">Vous pouvez modifier la facture corrigée, puis la valider.</span><span class="sxs-lookup"><span data-stu-id="3d7a2-108">You can modify the corrected invoice, and post it.</span></span> 

<span data-ttu-id="3d7a2-109">Lorsque vous validez la facture corrigée, une facture d'annulation est créée pour un montant de crédit qui est égal au montant de la facture d'origine.</span><span class="sxs-lookup"><span data-stu-id="3d7a2-109">When you post the corrected invoice, a canceling invoice is created for a credit amount that equals the original invoice amount.</span></span> <span data-ttu-id="3d7a2-110">Par conséquent, le solde combiné de la factures d'origine et de la facture d'annulation est 0 (zéro).</span><span class="sxs-lookup"><span data-stu-id="3d7a2-110">Therefore, the combined balance of the original invoice and the canceling invoice is 0 (zero).</span></span> <span data-ttu-id="3d7a2-111">La facture d'annulation est réglée par rapport à la facture d'origine.</span><span class="sxs-lookup"><span data-stu-id="3d7a2-111">The canceling invoice is settled against the original invoice.</span></span> 

<span data-ttu-id="3d7a2-112">Après avoir validé la facture corrigée, vous avez trois factures :</span><span class="sxs-lookup"><span data-stu-id="3d7a2-112">After you post the corrected invoice, you will have three invoices:</span></span>

-   <span data-ttu-id="3d7a2-113">**Facture d'origine** – Facture contenant les informations que vous corrigez.</span><span class="sxs-lookup"><span data-stu-id="3d7a2-113">**Original invoice** – The invoice that includes the information that you're correcting.</span></span>
-   <span data-ttu-id="3d7a2-114">**Facture d'annulation** – Facture de crédit générée par le système pour annuler la facture la plus récemment corrigée.</span><span class="sxs-lookup"><span data-stu-id="3d7a2-114">**Canceling invoice** – The system-generated credit invoice that was created to cancel the invoice that was most recently corrected.</span></span>
-   <span data-ttu-id="3d7a2-115">**Facture corrigée** – Facture contenant les informations de facture corrigées.</span><span class="sxs-lookup"><span data-stu-id="3d7a2-115">**Corrected invoice** – The invoice that contains the corrected invoice information.</span></span>

<span data-ttu-id="3d7a2-116">Vous pouvez identifier les factures d'annulation et les factures corrigées de deux manières :</span><span class="sxs-lookup"><span data-stu-id="3d7a2-116">You can identify canceling and correcting invoices in two ways:</span></span>

-   <span data-ttu-id="3d7a2-117">La page **Toutes les factures financières** inclut une colonne **Correction**, dans laquelle vous pouvez voir quelles factures sont des factures d'annulations et des factures corrigées.</span><span class="sxs-lookup"><span data-stu-id="3d7a2-117">The **All free text invoices** page includes a **Correction** column, where you can see which invoices are canceling invoices and corrected invoices.</span></span>
-   <span data-ttu-id="3d7a2-118">L'en-tête de la facture financière affiche le statut **Facture d'annulation '\[numéro de facture\]'** ou **Facture corrigée '\[numéro de facture\]'**.</span><span class="sxs-lookup"><span data-stu-id="3d7a2-118">The header of the free text invoice shows a status of **Cancelling invoice '\[invoice number\]'** or **Corrected invoice '\[invoice number\]'**.</span></span>

> [!NOTE]
> <span data-ttu-id="3d7a2-119">Cette fonctionnalité est uniquement disponible si la clé de configuration **Correction de la facture financière** est sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="3d7a2-119">This feature is available only if the **Free text invoice correction** configuration key is selected.</span></span>




