---
title: Correction d’une facture financière
description: Cet article explique comment corriger une facture financière validée et en émettre une nouvelle comme facture corrigée.
author: ShivamPandey-msft
ms.date: 08/22/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CustFreeInvoice
audience: Application User
ms.reviewer: roschlom
ms.custom: 13991
ms.assetid: 2a0a4789-8619-4974-bef9-0923cc848420
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: f04e70c9afb66be015ce18cebebd711f00d764b7
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5827576"
---
# <a name="correct-a-free-text-invoice"></a><span data-ttu-id="f63fc-103">Correction d’une facture financière</span><span class="sxs-lookup"><span data-stu-id="f63fc-103">Correct a free text invoice</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="f63fc-104">Cet article explique comment corriger une facture financière validée et en émettre une nouvelle comme facture corrigée.</span><span class="sxs-lookup"><span data-stu-id="f63fc-104">This article explains how to correct a free text invoice that has been posted and reissue it as a corrected invoice.</span></span>

<span data-ttu-id="f63fc-105">Pour corriger une facture financière qui a déjà été validée, ouvrez la facture financière validée.</span><span class="sxs-lookup"><span data-stu-id="f63fc-105">To correct a free text invoice that has already been posted, open the posted free text invoice.</span></span> <span data-ttu-id="f63fc-106">Sur la page **Facture**, sélectionnez **Annuler**, puis **Corriger la facture**.</span><span class="sxs-lookup"><span data-stu-id="f63fc-106">On the **Invoice** page, select **Cancel**, and then select **Correct invoice**.</span></span> <span data-ttu-id="f63fc-107">Sélectionnez un code motif, ajoutez des commentaires, puis sélectionnez la date de la nouvelle facture corrigée.</span><span class="sxs-lookup"><span data-stu-id="f63fc-107">Select a reason code, add comments, and select the date for new corrected invoice.</span></span> <span data-ttu-id="f63fc-108">Vous pouvez modifier la facture corrigée, puis la valider.</span><span class="sxs-lookup"><span data-stu-id="f63fc-108">You can modify the corrected invoice, and post it.</span></span> 

<span data-ttu-id="f63fc-109">Lorsque vous validez la facture corrigée, une facture d’annulation est créée pour un montant de crédit qui est égal au montant de la facture d’origine.</span><span class="sxs-lookup"><span data-stu-id="f63fc-109">When you post the corrected invoice, a canceling invoice is created for a credit amount that equals the original invoice amount.</span></span> <span data-ttu-id="f63fc-110">Par conséquent, le solde combiné de la factures d’origine et de la facture d’annulation est 0 (zéro).</span><span class="sxs-lookup"><span data-stu-id="f63fc-110">Therefore, the combined balance of the original invoice and the canceling invoice is 0 (zero).</span></span> <span data-ttu-id="f63fc-111">La facture d’annulation est réglée par rapport à la facture d’origine.</span><span class="sxs-lookup"><span data-stu-id="f63fc-111">The canceling invoice is settled against the original invoice.</span></span> 

<span data-ttu-id="f63fc-112">Après avoir validé la facture corrigée, vous avez trois factures :</span><span class="sxs-lookup"><span data-stu-id="f63fc-112">After you post the corrected invoice, you will have three invoices:</span></span>

-   <span data-ttu-id="f63fc-113">**Facture d’origine** – Facture contenant les informations que vous corrigez.</span><span class="sxs-lookup"><span data-stu-id="f63fc-113">**Original invoice** – The invoice that includes the information that you're correcting.</span></span>
-   <span data-ttu-id="f63fc-114">**Facture d’annulation** – Facture de crédit générée par le système pour annuler la facture la plus récemment corrigée.</span><span class="sxs-lookup"><span data-stu-id="f63fc-114">**Canceling invoice** – The system-generated credit invoice that was created to cancel the invoice that was most recently corrected.</span></span>
-   <span data-ttu-id="f63fc-115">**Facture corrigée** – Facture contenant les informations de facture corrigées.</span><span class="sxs-lookup"><span data-stu-id="f63fc-115">**Corrected invoice** – The invoice that contains the corrected invoice information.</span></span>

<span data-ttu-id="f63fc-116">Vous pouvez identifier les factures d’annulation et les factures corrigées de deux manières :</span><span class="sxs-lookup"><span data-stu-id="f63fc-116">You can identify canceling and correcting invoices in two ways:</span></span>

-   <span data-ttu-id="f63fc-117">La page **Toutes les factures financières** inclut une colonne **Correction**, dans laquelle vous pouvez voir quelles factures sont des factures d’annulations et des factures corrigées.</span><span class="sxs-lookup"><span data-stu-id="f63fc-117">The **All free text invoices** page includes a **Correction** column, where you can see which invoices are canceling invoices and corrected invoices.</span></span>
-   <span data-ttu-id="f63fc-118">L’en-tête de la facture financière affiche le statut **Facture d’annulation ’\[numéro de facture\]’** ou **Facture corrigée ’\[numéro de facture\]’**.</span><span class="sxs-lookup"><span data-stu-id="f63fc-118">The header of the free text invoice shows a status of **Cancelling invoice '\[invoice number\]'** or **Corrected invoice '\[invoice number\]'**.</span></span>

> [!NOTE]
> <span data-ttu-id="f63fc-119">Cette fonctionnalité est uniquement disponible si la clé de configuration **Correction de la facture financière** est sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="f63fc-119">This feature is available only if the **Free text invoice correction** configuration key is selected.</span></span> <span data-ttu-id="f63fc-120">Pour plus d’informations sur l’activation des clés de configuration, reportez-vous à la section Activer (ou désactiver) les clés de configuration dans la rubrique [Mode de maintenance](../../fin-ops-core/dev-itpro/sysadmin/maintenance-mode.md).</span><span class="sxs-lookup"><span data-stu-id="f63fc-120">For more information on how to enable Configuration keys refer to the Enable (or disable) configuration keys section in the [Maintenance mode](../../fin-ops-core/dev-itpro/sysadmin/maintenance-mode.md) topic.</span></span> 





[!INCLUDE[footer-include](../../includes/footer-banner.md)]