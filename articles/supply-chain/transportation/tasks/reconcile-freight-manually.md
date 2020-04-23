---
title: Rapprocher manuellement les frais de transport
description: Cette procédure indique comment rapprocher manuellement les frais de transport.
author: ShylaThompson
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSLoadPlanningWorkbench, TMSFreightBillDetail, TMSInvoiceTable, TMSFreightBillInvoiceReconcile, TMSInvoiceJournal, LedgerJournalTable, LedgerJournalTransDaily
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 2a0ff9aa1070272dd2cee357fb4fc001ffff8df1
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/02/2020
ms.locfileid: "3206171"
---
# <a name="reconcile-freight-manually"></a><span data-ttu-id="da1c8-103">Rapprocher manuellement le transport de fret</span><span class="sxs-lookup"><span data-stu-id="da1c8-103">Reconcile freight manually</span></span>

<span data-ttu-id="da1c8-104">[!include [banner](../../includes/banner.md)]]</span><span class="sxs-lookup"><span data-stu-id="da1c8-104">[!include [banner](../../includes/banner.md)]]</span></span>

<span data-ttu-id="da1c8-105">Cette procédure indique comment rapprocher manuellement les frais de transport.</span><span class="sxs-lookup"><span data-stu-id="da1c8-105">This procedure shows how to reconcile freight manually.</span></span> <span data-ttu-id="da1c8-106">Cette opération est généralement réalisée par un coordinateur transport.</span><span class="sxs-lookup"><span data-stu-id="da1c8-106">This is typically done by a transportation coordinator.</span></span> <span data-ttu-id="da1c8-107">Vous pouvez utiliser cette procédure dans les données fictives de la société USMF.</span><span class="sxs-lookup"><span data-stu-id="da1c8-107">You can use this procedure in the USMF demo data company.</span></span>


## <a name="select-a-load-to-reconcile"></a><span data-ttu-id="da1c8-108">Sélectionner une charge à rapprocher</span><span class="sxs-lookup"><span data-stu-id="da1c8-108">Select a load to reconcile</span></span>
1. <span data-ttu-id="da1c8-109">Accédez à Gestion du transport > Planning > Console de planification des charges.</span><span class="sxs-lookup"><span data-stu-id="da1c8-109">Go to Transportation management > Planning > Load planning workbench.</span></span>
2. <span data-ttu-id="da1c8-110">Désactivez la case à cocher Masquer les éléments expédiés et reçus.</span><span class="sxs-lookup"><span data-stu-id="da1c8-110">Clear the Hide shipped and received check box.</span></span> 
3. <span data-ttu-id="da1c8-111">Dans la liste, sélectionnez la charge dont l'ID de charge est 00006.</span><span class="sxs-lookup"><span data-stu-id="da1c8-111">In the list, select the load that has load ID 00006.</span></span>

## <a name="create-a-carrier-invoice"></a><span data-ttu-id="da1c8-112">Créer une facture transporteur</span><span class="sxs-lookup"><span data-stu-id="da1c8-112">Create a carrier invoice</span></span>
<span data-ttu-id="da1c8-113">Si vous rapprochez manuellement les frais de transport et ne recevez pas automatiquement les factures du transporteur, vous pouvez créer une facture sur la base de la facture des frais de transport.</span><span class="sxs-lookup"><span data-stu-id="da1c8-113">If you reconcile freight manually and don't receive carrier invoices automatically, you can create an invoice based on the freight bill.</span></span>  
1. <span data-ttu-id="da1c8-114">Cliquez sur Informations associées.</span><span class="sxs-lookup"><span data-stu-id="da1c8-114">Click Related information.</span></span>
2. <span data-ttu-id="da1c8-115">Cliquez sur Détails de la facture des frais de transport.</span><span class="sxs-lookup"><span data-stu-id="da1c8-115">Click Freight bill details.</span></span>
3. <span data-ttu-id="da1c8-116">Cliquez sur Générer la facture de transport.</span><span class="sxs-lookup"><span data-stu-id="da1c8-116">Click Generate freight bill invoice.</span></span>
4. <span data-ttu-id="da1c8-117">Tapez une valeur dans le champ Facture.</span><span class="sxs-lookup"><span data-stu-id="da1c8-117">In the Invoice field, type a value.</span></span>
5. <span data-ttu-id="da1c8-118">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="da1c8-118">Click OK.</span></span>

## <a name="reconcile-the-invoice"></a><span data-ttu-id="da1c8-119">Rapprocher la facture</span><span class="sxs-lookup"><span data-stu-id="da1c8-119">Reconcile the invoice</span></span>
<span data-ttu-id="da1c8-120">Lorsque vous rapprochez une facture du transporteur et une facture des frais de transport, cette procédure est effectuée ligne par ligne.</span><span class="sxs-lookup"><span data-stu-id="da1c8-120">When you reconcile a carrier invoice and a freight bill, this is done line by line.</span></span>  
1. <span data-ttu-id="da1c8-121">Cliquez sur Mettre en correspondance les facture des frais de transport et les factures.</span><span class="sxs-lookup"><span data-stu-id="da1c8-121">Click Match freight bills and invoices.</span></span>
2. <span data-ttu-id="da1c8-122">Développez la section Détails de la facture.</span><span class="sxs-lookup"><span data-stu-id="da1c8-122">Expand the Invoice details section.</span></span>
3. <span data-ttu-id="da1c8-123">Développez la section Détails de la facture des frais de transport non rapprochés.</span><span class="sxs-lookup"><span data-stu-id="da1c8-123">Expand the Unmatched freight bill details section.</span></span>
4. <span data-ttu-id="da1c8-124">Dans la liste, marquer la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="da1c8-124">In the list, mark the selected row.</span></span>
5. <span data-ttu-id="da1c8-125">Cliquez sur Correspondance.</span><span class="sxs-lookup"><span data-stu-id="da1c8-125">Click Match.</span></span>
6. <span data-ttu-id="da1c8-126">Développez la section Détails de la facture des frais de transport rapprochés.</span><span class="sxs-lookup"><span data-stu-id="da1c8-126">Expand the Matched freight bill details section.</span></span>

## <a name="submit-the-invoice-for-approval"></a><span data-ttu-id="da1c8-127">Soumettre la facture pour approbation</span><span class="sxs-lookup"><span data-stu-id="da1c8-127">Submit the invoice for approval</span></span>
1. <span data-ttu-id="da1c8-128">Cliquez sur Soumettre pour approbation.</span><span class="sxs-lookup"><span data-stu-id="da1c8-128">Click Submit for approval.</span></span>
2. <span data-ttu-id="da1c8-129">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="da1c8-129">Close the page.</span></span>
3. <span data-ttu-id="da1c8-130">Désactivez la case à cocher Masquer l'approbation.</span><span class="sxs-lookup"><span data-stu-id="da1c8-130">Clear the Hide approved check box.</span></span> 
4. <span data-ttu-id="da1c8-131">Cliquez sur Journaux des factures fournisseur.</span><span class="sxs-lookup"><span data-stu-id="da1c8-131">Click Vendor invoice journals.</span></span>
5. <span data-ttu-id="da1c8-132">Cliquez pour suivre le lien dans le champ Numéro du journal de référence.</span><span class="sxs-lookup"><span data-stu-id="da1c8-132">Click to follow the link in the Reference journal number field.</span></span>
6. <span data-ttu-id="da1c8-133">Cliquez sur Lignes.</span><span class="sxs-lookup"><span data-stu-id="da1c8-133">Click Lines.</span></span>

