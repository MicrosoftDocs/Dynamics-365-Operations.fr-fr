---
title: Espace de travail de facturation de collaboration fournisseur
description: Cette rubrique explique comment afficher des factures fournisseur et envoyer des factures depuis l'espace de travail de facturation de collaboration fournisseur.
author: ShivamPandey-msft
manager: AnnBe
ms.date: 08/22/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 221534
ms.assetid: c4ed62f3-d351-41d7-a2ad-790576cde4ab
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: 506dd06790f40fbba272811a59281add1a86b179
ms.contentlocale: fr-fr
ms.lasthandoff: 11/06/2017

---

# <a name="vendor-collaboration-invoicing-workspace"></a><span data-ttu-id="4e820-103">Espace de travail de facturation de collaboration fournisseur</span><span class="sxs-lookup"><span data-stu-id="4e820-103">Vendor collaboration invoicing workspace</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="4e820-104">Cette rubrique explique comment afficher des factures fournisseur et envoyer des factures depuis l'espace de travail de facturation de collaboration fournisseur.</span><span class="sxs-lookup"><span data-stu-id="4e820-104">This topic explains how you can view vendor invoices and submit invoices from the vendor collaboration invoicing workspace.</span></span>

<span data-ttu-id="4e820-105">L'espace de travail de **facturation de collaboration fournisseur** permet d'afficher les informations de facture fournisseur et d'envoyer des factures à Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition à l'aide des fonctionnalités de workflow.</span><span class="sxs-lookup"><span data-stu-id="4e820-105">The **Vendor collaboration invoicing** workspace can be used to view vendor invoice information and to submit invoices to Microsoft Dynamics 365 for Finance and Operations, Enterprise edition using workflow capabilities.</span></span>


<a name="vendor-collaboration-invoicing-workspace"></a><span data-ttu-id="4e820-106">Espace de travail de facturation de collaboration fournisseur</span><span class="sxs-lookup"><span data-stu-id="4e820-106">Vendor collaboration invoicing workspace</span></span>
----------------------------------------

### <a name="summary-tiles"></a><span data-ttu-id="4e820-107">Vignettes récapitulatives</span><span class="sxs-lookup"><span data-stu-id="4e820-107">Summary tiles</span></span>

<span data-ttu-id="4e820-108">Les vignettes **Synthèse** fournissent une vue d'ensemble des factures du fournisseur sélectionné.</span><span class="sxs-lookup"><span data-stu-id="4e820-108">The **Summary** tiles give an overview of the invoices for the selected vendor.</span></span> <span data-ttu-id="4e820-109">Vous pouvez afficher les factures selon leur état.</span><span class="sxs-lookup"><span data-stu-id="4e820-109">You can view invoices by their state.</span></span>
-   <span data-ttu-id="4e820-110">Les brouillons de factures n'ont pas été envoyés au workflow.</span><span class="sxs-lookup"><span data-stu-id="4e820-110">Draft invoices have not been submitted to workflow.</span></span>
-   <span data-ttu-id="4e820-111">Les factures soumises et non approuvées sont les factures que le fournisseur a envoyées, mais qui n'ont pas été validées dans Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="4e820-111">Submitted, not approved invoices are those invoices that the vendor has submitted, but they have not been posted in Finance and Operations.</span></span>
-   <span data-ttu-id="4e820-112">Les factures approuvées et non réglées sont celles qui ont été validées dans Finance and Operations, mais qui n'ont pas été entièrement réglées.</span><span class="sxs-lookup"><span data-stu-id="4e820-112">Approved, not paid invoices are those that have been posted in Finance and Operations, but they have not yet been fully paid.</span></span>
-   <span data-ttu-id="4e820-113">Les factures payées sont celles qui ont été complètement réglées dans Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="4e820-113">Paid invoices are those that have been fully paid in Finance and Operations.</span></span>

<span data-ttu-id="4e820-114">Cliquez sur une vignette pour ouvrir une vue filtrée de la page **Liste des factures**.</span><span class="sxs-lookup"><span data-stu-id="4e820-114">Clicking on a tile will open a filtered view of the **Invoices list** page.</span></span>
### <a name="tabular-lists"></a><span data-ttu-id="4e820-115">Listes tabulaires</span><span class="sxs-lookup"><span data-stu-id="4e820-115">Tabular lists</span></span>

<span data-ttu-id="4e820-116">Dans la section **Listes tabulaires**, le statut de la facturation est réparti de manière similaire aux vignettes de synthèse : listes Brouillon et Envoyées, non approuvées.</span><span class="sxs-lookup"><span data-stu-id="4e820-116">In the **Tabular lists** section, the status of the invoicing is broken down in similar ways as the summary tiles: Draft and Submitted, not approved lists.</span></span> <span data-ttu-id="4e820-117">Tandis que dans l'état Brouillon, une facture peut être envoyée au workflow ou être supprimée.</span><span class="sxs-lookup"><span data-stu-id="4e820-117">While in the Draft state, an invoice can be submitted to workflow or deleted.</span></span> <span data-ttu-id="4e820-118">La dernière liste tabulaire est un moyen de rechercher des factures.</span><span class="sxs-lookup"><span data-stu-id="4e820-118">The last tabular list is an option to find invoices.</span></span> <span data-ttu-id="4e820-119">Vous pouvez définir les filtres au fil de la recherche, afin d'accélérer celle-ci.</span><span class="sxs-lookup"><span data-stu-id="4e820-119">You can filter as you search, to allow for faster searches.</span></span>
<span data-ttu-id="4e820-120">Page de liste Toutes les factures fournisseur</span><span class="sxs-lookup"><span data-stu-id="4e820-120">All vendor invoices list page</span></span>
-----------------------------

<span data-ttu-id="4e820-121">Vous pouvez afficher toutes les factures fournisseurs validées ou non validées dans la page de liste **Factures de la collaboration du fournisseur**.</span><span class="sxs-lookup"><span data-stu-id="4e820-121">You can view all posted and unposted vendor invoices on the **Vendor collaboration invoices** list page.</span></span> <span data-ttu-id="4e820-122">Vous pouvez utiliser cette page de liste pour afficher le statut de paiement des factures.</span><span class="sxs-lookup"><span data-stu-id="4e820-122">You can use this list page to view the payment status of the invoices.</span></span> <span data-ttu-id="4e820-123">Les statuts de règlement incluent Non validée, Impayée, Partiellement payée, et totalement payée.</span><span class="sxs-lookup"><span data-stu-id="4e820-123">The payment statuses include Unposted, Unpaid, Partially paid, and Fully paid.</span></span>
<span data-ttu-id="4e820-124">Création d'une facture à partir d'une commande fournisseur</span><span class="sxs-lookup"><span data-stu-id="4e820-124">Creating a new invoice from a purchase order</span></span>
--------------------------------------------

<span data-ttu-id="4e820-125">Vous pouvez créer une nouvelle facture fournisseur en sélectionnant l'action **Nouveau** sous l'espace de travail de **facturation de collaboration fournisseur**.</span><span class="sxs-lookup"><span data-stu-id="4e820-125">You can create a new vendor invoice by selecting the **New** action on the **Vendor collaboration invoicing** workspace.</span></span> <span data-ttu-id="4e820-126">Le numéro de commande fournisseur et le numéro de facture doivent être fournis par le fournisseur.</span><span class="sxs-lookup"><span data-stu-id="4e820-126">The purchase order number and invoice number must be provided by the vendor.</span></span> <span data-ttu-id="4e820-127">Par défaut, toutes les lignes de la commande du fournisseur s'afficheront sur la nouvelle facture.</span><span class="sxs-lookup"><span data-stu-id="4e820-127">By default, all of the lines from the vendor's purchase order will appear on the new invoice.</span></span> <span data-ttu-id="4e820-128">Les informations sur la quantité et le coût peuvent être modifiées avant d'envoyer la facture fournisseur au workflow.</span><span class="sxs-lookup"><span data-stu-id="4e820-128">The quantity and cost information can be edited prior to submitting the vendor invoice to workflow.</span></span> <span data-ttu-id="4e820-129">Vous pouvez joindre des fichiers, des notes, des images, et des URL à une facture avant de l'envoyer.</span><span class="sxs-lookup"><span data-stu-id="4e820-129">You can attach files, notes, images, and URLs to an invoice before submitting it.</span></span>



<span data-ttu-id="4e820-130">Pour plus d'informations, voir [Collaborer avec des fournisseurs à l'aide du portail Fournisseur](../../supply-chain/procurement/collaborate-vendors-vendor-portal.md)</span><span class="sxs-lookup"><span data-stu-id="4e820-130">For more information, see [Collaborating with vendors by using the Vendor portal](../../supply-chain/procurement/collaborate-vendors-vendor-portal.md)</span></span>




