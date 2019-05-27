---
title: Rapprocher manuellement les frais de transport
description: Cette procédure indique comment rapprocher manuellement les frais de transport.
author: ShylaThompson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSLoadPlanningWorkbench, TMSFreightBillDetail, TMSInvoiceTable, TMSFreightBillInvoiceReconcile, TMSInvoiceJournal, LedgerJournalTable, LedgerJournalTransDaily
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: ee2d114b0a725b947add3e155cc6445021fee998
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/15/2019
ms.locfileid: "1556732"
---
# <a name="reconcile-freight-manually"></a><span data-ttu-id="d1552-103">Rapprocher manuellement les frais de transport</span><span class="sxs-lookup"><span data-stu-id="d1552-103">Reconcile freight manually</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="d1552-104">Cette procédure indique comment rapprocher manuellement les frais de transport.</span><span class="sxs-lookup"><span data-stu-id="d1552-104">This procedure shows how to reconcile freight manually.</span></span> <span data-ttu-id="d1552-105">Cette opération est généralement réalisée par un coordinateur transport.</span><span class="sxs-lookup"><span data-stu-id="d1552-105">This is typically done by a transportation coordinator.</span></span> <span data-ttu-id="d1552-106">Vous pouvez utiliser cette procédure dans les données fictives de la société USMF.</span><span class="sxs-lookup"><span data-stu-id="d1552-106">You can use this procedure in the USMF demo data company.</span></span>


## <a name="select-a-load-to-reconcile"></a><span data-ttu-id="d1552-107">Sélectionner une charge à rapprocher</span><span class="sxs-lookup"><span data-stu-id="d1552-107">Select a load to reconcile</span></span>
1. <span data-ttu-id="d1552-108">Accédez à Gestion du transport > Planning > Console de planification des charges.</span><span class="sxs-lookup"><span data-stu-id="d1552-108">Go to Transportation management > Planning > Load planning workbench.</span></span>
2. <span data-ttu-id="d1552-109">Désactivez la case à cocher Masquer les éléments expédiés et reçus.</span><span class="sxs-lookup"><span data-stu-id="d1552-109">Clear the Hide shipped and received check box.</span></span> 
3. <span data-ttu-id="d1552-110">Dans la liste, sélectionnez la charge dont l'ID de charge est 00006.</span><span class="sxs-lookup"><span data-stu-id="d1552-110">In the list, select the load that has load ID 00006.</span></span>

## <a name="create-a-carrier-invoice"></a><span data-ttu-id="d1552-111">Créer une facture transporteur</span><span class="sxs-lookup"><span data-stu-id="d1552-111">Create a carrier invoice</span></span>
    * <span data-ttu-id="d1552-112">Si vous rapprochez manuellement les frais de transport et ne recevez pas automatiquement les factures du transporteur, vous pouvez créer une facture sur la base de la facture des frais de transport.</span><span class="sxs-lookup"><span data-stu-id="d1552-112">If you reconcile freight manually and don’t receive carrier invoices automatically, you can create an invoice based on the freight bill.</span></span>  
1. <span data-ttu-id="d1552-113">Cliquez sur Informations associées.</span><span class="sxs-lookup"><span data-stu-id="d1552-113">Click Related information.</span></span>
2. <span data-ttu-id="d1552-114">Cliquez sur Détails de la facture des frais de transport.</span><span class="sxs-lookup"><span data-stu-id="d1552-114">Click Freight bill details.</span></span>
3. <span data-ttu-id="d1552-115">Cliquez sur Générer la facture de transport.</span><span class="sxs-lookup"><span data-stu-id="d1552-115">Click Generate freight bill invoice.</span></span>
4. <span data-ttu-id="d1552-116">Tapez une valeur dans le champ Facture.</span><span class="sxs-lookup"><span data-stu-id="d1552-116">In the Invoice field, type a value.</span></span>
5. <span data-ttu-id="d1552-117">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="d1552-117">Click OK.</span></span>

## <a name="reconcile-the-invoice"></a><span data-ttu-id="d1552-118">Rapprocher la facture</span><span class="sxs-lookup"><span data-stu-id="d1552-118">Reconcile the invoice</span></span>
    * <span data-ttu-id="d1552-119">Lorsque vous rapprochez une facture du transporteur et une facture des frais de transport, cette procédure est effectuée ligne par ligne.</span><span class="sxs-lookup"><span data-stu-id="d1552-119">When you reconcile a carrier invoice and a freight bill, this is done line by line.</span></span>  
1. <span data-ttu-id="d1552-120">Cliquez sur Mettre en correspondance les facture des frais de transport et les factures.</span><span class="sxs-lookup"><span data-stu-id="d1552-120">Click Match freight bills and invoices.</span></span>
2. <span data-ttu-id="d1552-121">Développez la section Détails de la facture.</span><span class="sxs-lookup"><span data-stu-id="d1552-121">Expand the Invoice details section.</span></span>
3. <span data-ttu-id="d1552-122">Développez la section Détails de la facture des frais de transport non rapprochés.</span><span class="sxs-lookup"><span data-stu-id="d1552-122">Expand the Unmatched freight bill details section.</span></span>
4. <span data-ttu-id="d1552-123">Dans la liste, marquer la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="d1552-123">In the list, mark the selected row.</span></span>
5. <span data-ttu-id="d1552-124">Cliquez sur Correspondance.</span><span class="sxs-lookup"><span data-stu-id="d1552-124">Click Match.</span></span>
6. <span data-ttu-id="d1552-125">Développez la section Détails de la facture des frais de transport rapprochés.</span><span class="sxs-lookup"><span data-stu-id="d1552-125">Expand the Matched freight bill details section.</span></span>

## <a name="submit-the-invoice-for-approval"></a><span data-ttu-id="d1552-126">Soumettre la facture pour approbation</span><span class="sxs-lookup"><span data-stu-id="d1552-126">Submit the invoice for approval</span></span>
1. <span data-ttu-id="d1552-127">Cliquez sur Soumettre pour approbation.</span><span class="sxs-lookup"><span data-stu-id="d1552-127">Click Submit for approval.</span></span>
2. <span data-ttu-id="d1552-128">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="d1552-128">Close the page.</span></span>
3. <span data-ttu-id="d1552-129">Désactivez la case à cocher Masquer l'approbation.</span><span class="sxs-lookup"><span data-stu-id="d1552-129">Clear the Hide approved check box.</span></span> 
4. <span data-ttu-id="d1552-130">Cliquez sur Journaux des factures fournisseur.</span><span class="sxs-lookup"><span data-stu-id="d1552-130">Click Vendor invoice journals.</span></span>
5. <span data-ttu-id="d1552-131">Cliquez pour suivre le lien dans le champ Numéro du journal de référence.</span><span class="sxs-lookup"><span data-stu-id="d1552-131">Click to follow the link in the Reference journal number field.</span></span>
6. <span data-ttu-id="d1552-132">Cliquez sur Lignes.</span><span class="sxs-lookup"><span data-stu-id="d1552-132">Click Lines.</span></span>

