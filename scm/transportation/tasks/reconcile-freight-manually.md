--- 
title: Rapprocher manuellement les frais de transport
description: "Cette procédure indique comment rapprocher manuellement les frais de transport."
author: BibiSp
manager: AnnBe
ms.date: 10/13/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bis
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: bis
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: 15148725664d839694ede8419213d881c7be83dd
ms.contentlocale: fr-fr
ms.lasthandoff: 08/29/2017

---
# <a name="reconcile-freight-manually"></a><span data-ttu-id="04b87-103">Rapprocher manuellement les frais de transport</span><span class="sxs-lookup"><span data-stu-id="04b87-103">Reconcile freight manually</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="04b87-104">Cette procédure indique comment rapprocher manuellement les frais de transport.</span><span class="sxs-lookup"><span data-stu-id="04b87-104">This procedure shows how to reconcile freight manually.</span></span> <span data-ttu-id="04b87-105">Cette opération est généralement réalisée par un coordinateur transport.</span><span class="sxs-lookup"><span data-stu-id="04b87-105">This is typically done by a transportation coordinator.</span></span> <span data-ttu-id="04b87-106">Vous pouvez utiliser cette procédure dans les données fictives de la société USMF.</span><span class="sxs-lookup"><span data-stu-id="04b87-106">You can use this procedure in the USMF demo data company.</span></span>


## <a name="select-a-load-to-reconcile"></a><span data-ttu-id="04b87-107">Sélectionner une charge à rapprocher</span><span class="sxs-lookup"><span data-stu-id="04b87-107">Select a load to reconcile</span></span>
1. <span data-ttu-id="04b87-108">Accédez à Gestion du transport > Planning > Console de planification des charges.</span><span class="sxs-lookup"><span data-stu-id="04b87-108">Go to Transportation management > Planning > Load planning workbench.</span></span>
2. <span data-ttu-id="04b87-109">Désactivez la case à cocher Masquer les éléments expédiés et reçus.</span><span class="sxs-lookup"><span data-stu-id="04b87-109">Clear the Hide shipped and received check box.</span></span> 
3. <span data-ttu-id="04b87-110">Dans la liste, sélectionnez la charge dont l'ID de charge est 00006.</span><span class="sxs-lookup"><span data-stu-id="04b87-110">In the list, select the load that has load ID 00006.</span></span>

## <a name="create-a-carrier-invoice"></a><span data-ttu-id="04b87-111">Créer une facture transporteur</span><span class="sxs-lookup"><span data-stu-id="04b87-111">Create a carrier invoice</span></span>
    * <span data-ttu-id="04b87-112">Si vous rapprochez manuellement les frais de transport et ne recevez pas automatiquement les factures du transporteur, vous pouvez créer une facture sur la base de la facture des frais de transport.</span><span class="sxs-lookup"><span data-stu-id="04b87-112">If you reconcile freight manually and don’t receive carrier invoices automatically, you can create an invoice based on the freight bill.</span></span>  
1. <span data-ttu-id="04b87-113">Cliquez sur Informations associées.</span><span class="sxs-lookup"><span data-stu-id="04b87-113">Click Related information.</span></span>
2. <span data-ttu-id="04b87-114">Cliquez sur Détails de la facture des frais de transport.</span><span class="sxs-lookup"><span data-stu-id="04b87-114">Click Freight bill details.</span></span>
3. <span data-ttu-id="04b87-115">Cliquez sur Générer la facture de transport.</span><span class="sxs-lookup"><span data-stu-id="04b87-115">Click Generate freight bill invoice.</span></span>
4. <span data-ttu-id="04b87-116">Tapez une valeur dans le champ Facture.</span><span class="sxs-lookup"><span data-stu-id="04b87-116">In the Invoice field, type a value.</span></span>
5. <span data-ttu-id="04b87-117">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="04b87-117">Click OK.</span></span>

## <a name="reconcile-the-invoice"></a><span data-ttu-id="04b87-118">Rapprocher la facture</span><span class="sxs-lookup"><span data-stu-id="04b87-118">Reconcile the invoice</span></span>
    * <span data-ttu-id="04b87-119">Lorsque vous rapprochez une facture du transporteur et une facture des frais de transport, cette procédure est effectuée ligne par ligne.</span><span class="sxs-lookup"><span data-stu-id="04b87-119">When you reconcile a carrier invoice and a freight bill, this is done line by line.</span></span>  
1. <span data-ttu-id="04b87-120">Cliquez sur Mettre en correspondance les facture des frais de transport et les factures.</span><span class="sxs-lookup"><span data-stu-id="04b87-120">Click Match freight bills and invoices.</span></span>
2. <span data-ttu-id="04b87-121">Développez la section Détails de la facture.</span><span class="sxs-lookup"><span data-stu-id="04b87-121">Expand the Invoice details section.</span></span>
3. <span data-ttu-id="04b87-122">Développez la section Détails de la facture des frais de transport non rapprochés.</span><span class="sxs-lookup"><span data-stu-id="04b87-122">Expand the Unmatched freight bill details section.</span></span>
4. <span data-ttu-id="04b87-123">Dans la liste, marquer la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="04b87-123">In the list, mark the selected row.</span></span>
5. <span data-ttu-id="04b87-124">Cliquez sur Correspondance.</span><span class="sxs-lookup"><span data-stu-id="04b87-124">Click Match.</span></span>
6. <span data-ttu-id="04b87-125">Développez la section Détails de la facture des frais de transport rapprochés.</span><span class="sxs-lookup"><span data-stu-id="04b87-125">Expand the Matched freight bill details section.</span></span>

## <a name="submit-the-invoice-for-approval"></a><span data-ttu-id="04b87-126">Soumettre la facture pour approbation</span><span class="sxs-lookup"><span data-stu-id="04b87-126">Submit the invoice for approval</span></span>
1. <span data-ttu-id="04b87-127">Cliquez sur Soumettre pour approbation.</span><span class="sxs-lookup"><span data-stu-id="04b87-127">Click Submit for approval.</span></span>
2. <span data-ttu-id="04b87-128">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="04b87-128">Close the page.</span></span>
3. <span data-ttu-id="04b87-129">Désactivez la case à cocher Masquer l'approbation.</span><span class="sxs-lookup"><span data-stu-id="04b87-129">Clear the Hide approved check box.</span></span> 
4. <span data-ttu-id="04b87-130">Cliquez sur Journaux des factures fournisseur.</span><span class="sxs-lookup"><span data-stu-id="04b87-130">Click Vendor invoice journals.</span></span>
5. <span data-ttu-id="04b87-131">Cliquez pour suivre le lien dans le champ Numéro du journal de référence.</span><span class="sxs-lookup"><span data-stu-id="04b87-131">Click to follow the link in the Reference journal number field.</span></span>
6. <span data-ttu-id="04b87-132">Cliquez sur Lignes.</span><span class="sxs-lookup"><span data-stu-id="04b87-132">Click Lines.</span></span>


