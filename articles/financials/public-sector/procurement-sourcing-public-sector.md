---
title: Approvisionnements dans le secteur public
description: "Cette vue d'ensemble présente la fonctionnalité d'approvisionnements disponible pour le secteur public. Cela inclut les codes de commande fournisseur, les types de certification des fournisseurs, la fonctionnalité de classification de contrat d'achat, et les montants de ligne de commande fournisseur."
author: twheeloc
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: AgreementClassification, BudgetParameters, ProcCategoryHierarchyManagement, PurchTableListPage, smmActivities, VendCertificationType, VendTableListPage
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 19681
ms.assetid: c99b2aeb-4ac2-4abe-b8b9-786b664c103d
ms.search.region: Global
ms.search.industry: Public sector
ms.author: brpotter
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: b00c7f2ee619bcae03f427a41162ad11999d68f5
ms.contentlocale: fr-fr
ms.lasthandoff: 11/06/2017

---

# <a name="procurement-and-sourcing-in-the-public-sector"></a><span data-ttu-id="fac80-104">Approvisionnements dans le secteur public</span><span class="sxs-lookup"><span data-stu-id="fac80-104">Procurement and sourcing in the public sector</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="fac80-105">Cette vue d'ensemble présente la fonctionnalité d'approvisionnements disponible pour le secteur public.</span><span class="sxs-lookup"><span data-stu-id="fac80-105">This overview introduces you to the public sector Procurement and sourcing functionality.</span></span> <span data-ttu-id="fac80-106">Cela inclut les codes de commande fournisseur, les types de certification des fournisseurs, la fonctionnalité de classification de contrat d'achat, et les montants de ligne de commande fournisseur.</span><span class="sxs-lookup"><span data-stu-id="fac80-106">This includes purchase order codes, vendor certification types, purchase agreement classification functionality, and purchase order line amounts.</span></span>

<span data-ttu-id="fac80-107">Cet article décrit la fonctionnalité d'approvisionnements disponible pour le secteur public.</span><span class="sxs-lookup"><span data-stu-id="fac80-107">This article describes the Procurement and sourcing functionality that is available for the public sector.</span></span> 

## <a name="what-are-the-prerequisites-for-setting-up-procurement-and-sourcing-in-the-public-sector"></a><span data-ttu-id="fac80-108">Quelles sont les conditions préalables au paramétrage des approvisionnements dans le secteur public ?</span><span class="sxs-lookup"><span data-stu-id="fac80-108">What are the prerequisites for setting up Procurement and sourcing in the public sector?</span></span>
<span data-ttu-id="fac80-109">Avant de commencer à ajuster les paramètres et à entrer vos données, vous devez effectuer les opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="fac80-109">Before you begin to adjust the settings and input your data, you should:</span></span>

-   <span data-ttu-id="fac80-110">Paramétrage des fournisseurs</span><span class="sxs-lookup"><span data-stu-id="fac80-110">Set up vendors</span></span>
-   <span data-ttu-id="fac80-111">Paramétrer le système de numérotation pour les fournisseurs, les commandes fournisseur, etc.</span><span class="sxs-lookup"><span data-stu-id="fac80-111">Set up the numbering system for vendors, purchase orders, and so on</span></span>
-   <span data-ttu-id="fac80-112">Spécifier les types de certification des fournisseurs</span><span class="sxs-lookup"><span data-stu-id="fac80-112">Specify vendor certification types</span></span>

<span data-ttu-id="fac80-113">Vous devez peut-être paramétrer les fonctionnalités d'approvisionnement suivantes pour les organisations du secteur public :</span><span class="sxs-lookup"><span data-stu-id="fac80-113">You may need to set up the following Procurement and sourcing features for public sector organizations:</span></span>

-    <span data-ttu-id="fac80-114">[Codes de commandes fournisseur du secteur public](purchase-order-codes-public-sector.md) Créez des codes et des messages spéciaux pour la confirmation des commandes fournisseur.</span><span class="sxs-lookup"><span data-stu-id="fac80-114">[Public sector purchase order codes](purchase-order-codes-public-sector.md) Create codes and special messages for confirming purchase orders.</span></span> <span data-ttu-id="fac80-115">Une commande fournisseur de confirmation permet de contourner le processus d'achat habituel.</span><span class="sxs-lookup"><span data-stu-id="fac80-115">A confirming purchase order circumvents the typical purchasing process.</span></span>

> [!NOTE]
> <span data-ttu-id="fac80-116">Cela s'applique également à la comptabilité fournisseur.</span><span class="sxs-lookup"><span data-stu-id="fac80-116">This also applies to Accounts payable.</span></span>

-   [<span data-ttu-id="fac80-117">Comptabilité du secteur public en France</span><span class="sxs-lookup"><span data-stu-id="fac80-117">Public sector accounting in France</span></span>](../localizations/emea-fra-public-sector-accounting.md) 

<span data-ttu-id="fac80-118">Pour les organisations françaises, des étapes supplémentaires peuvent être nécessaires pour le secteur public.</span><span class="sxs-lookup"><span data-stu-id="fac80-118">For French organizations, additional steps may be required for the public sector.</span></span>

<span data-ttu-id="fac80-119">Les sections suivantes décrivent les fonctionnalités d'approvisionnements disponible pour le secteur public.</span><span class="sxs-lookup"><span data-stu-id="fac80-119">The following sections describe the Procurement and sourcing features that are available for the public sector.</span></span>

## <a name="what-are-vendor-certification-types"></a><span data-ttu-id="fac80-120">Que sont les types de certification des fournisseurs ?</span><span class="sxs-lookup"><span data-stu-id="fac80-120">What are vendor certification types?</span></span>
<span data-ttu-id="fac80-121">Vous pouvez créer et affecter aux organisations de fournisseurs n'importe quels types de certification que les fournisseurs détiennent.</span><span class="sxs-lookup"><span data-stu-id="fac80-121">You can create and assign to vendor organizations any types of certification that the vendors hold.</span></span> <span data-ttu-id="fac80-122">Il s'agit non seulement d'informations d'identification professionnelles, comme la licence d'un ingénieur professionnel ou la certification Microsoft SQL Server, mais également de déterminer s'ils détiennent une assurance en responsabilité civile, un statut de minorité ou s'ils sont en conformité avec diverses normes de sécurité relatives à l'environnement ou au consommateur.</span><span class="sxs-lookup"><span data-stu-id="fac80-122">This includes not only professional credentials, such as a professional engineer’s license or Microsoft SQL Server Certification, but also whether they have liability insurance, minority status, or are in compliance with various environmental or consumer safety standards.</span></span> 

<span data-ttu-id="fac80-123">La page **Type de certification** de la comptabilité fournisseur vous permet de spécifier le type et la description de la certification.</span><span class="sxs-lookup"><span data-stu-id="fac80-123">You use the **Certification type** page in Accounts payable to enter the certification type and the description.</span></span>

## <a name="what-do-i-need-to-know-about-purchase-or-sales-agreement-classifications"></a><span data-ttu-id="fac80-124">Que dois-je savoir sur les classifications de contrat d'achat ou de vente ?</span><span class="sxs-lookup"><span data-stu-id="fac80-124">What do I need to know about purchase or sales agreement classifications?</span></span>
<span data-ttu-id="fac80-125">Lorsque les utilisateurs créent un contrat d'achat ou de vente, ils doivent toujours sélectionner son type.</span><span class="sxs-lookup"><span data-stu-id="fac80-125">When users create a new purchase agreement or sales agreement, they must always select the type of purchase agreement or sales agreement.</span></span> <span data-ttu-id="fac80-126">Les contrôles supplémentaires du secteur public sont disponibles sur les pages **Classifications de contrat**.</span><span class="sxs-lookup"><span data-stu-id="fac80-126">Additional public sector controls are available on the **Agreement classifications** pages.</span></span> 

<span data-ttu-id="fac80-127">Pour créer et spécifier des classifications de contrat, utilisez la page **Classification de contrat d'achat** dans le module Approvisionnements ou la page **Classification de contrat de vente** dans le module Ventes et marketing.</span><span class="sxs-lookup"><span data-stu-id="fac80-127">To create and specify agreement classifications, you use the **Purchase agreement classification** page in Procurement and sourcing or the **Sales agreement classification** page in Sales and marketing.</span></span> 

<span data-ttu-id="fac80-128">Prenez en compte les informations suivantes lorsque vous spécifiez les détails des classifications de contrat d'achat ou de vente.</span><span class="sxs-lookup"><span data-stu-id="fac80-128">Take the following information into account when specifying details for purchase or sales agreement classifications.</span></span>

### <a name="how-do-i-enter-information-about-subcontractors-on-purchase-agreements"></a><span data-ttu-id="fac80-129">Comment saisir les informations sur les sous-traitants dans les contrats d'achat ?</span><span class="sxs-lookup"><span data-stu-id="fac80-129">How do I enter information about subcontractors on purchase agreements?</span></span>

<span data-ttu-id="fac80-130">Sélectionnez l'option **Sous-traitants**.</span><span class="sxs-lookup"><span data-stu-id="fac80-130">Select the **Subcontractors** option.</span></span>

### <a name="how-do-i-enter-information-about-insurance-policies-and-bonds-on-purchase-agreements"></a><span data-ttu-id="fac80-131">Comment spécifier les informations sur les polices d'assurance et les obligations dans les contrats d'achat ?</span><span class="sxs-lookup"><span data-stu-id="fac80-131">How do I enter information about insurance policies and bonds on purchase agreements?</span></span>

<span data-ttu-id="fac80-132">Sélectionnez l'option **Certifications**.</span><span class="sxs-lookup"><span data-stu-id="fac80-132">Select the **Certifications** option.</span></span> <span data-ttu-id="fac80-133">Les informations peuvent servir à générer un état qui vous permet de contrôler la conformité des fournisseurs avec les conditions de certification.</span><span class="sxs-lookup"><span data-stu-id="fac80-133">The information can be used to generate a report that you can use to monitor vendor compliance with certification requirements.</span></span> <span data-ttu-id="fac80-134">(Pour générer l'état, accéder accédez à la page **Conformité de la certification des contrats d'achat**.)</span><span class="sxs-lookup"><span data-stu-id="fac80-134">(To generate the report, go to the **Purchase agreement certification compliance** page.)</span></span>

### <a name="how-do-i-enter-information-about-milestones-and-tasks-on-purchase-agreements"></a><span data-ttu-id="fac80-135">Comment saisir les informations sur les jalons et les tâches dans les contrats d'achat ?</span><span class="sxs-lookup"><span data-stu-id="fac80-135">How do I enter information about milestones and tasks on purchase agreements?</span></span>

<span data-ttu-id="fac80-136">Sélectionnez l'option **Activités**.</span><span class="sxs-lookup"><span data-stu-id="fac80-136">Select the **Activities** option.</span></span>

### <a name="how-do-i-require-direct-invoicing-and-prevent-the-use-of-release-orders-with-purchase-agreements"></a><span data-ttu-id="fac80-137">Comment imposer une facturation directe et empêcher l'utilisation d'ordres de lancement pour les contrats d'achat ?</span><span class="sxs-lookup"><span data-stu-id="fac80-137">How do I require direct invoicing and prevent the use of release orders with purchase agreements?</span></span>

<span data-ttu-id="fac80-138">Sélectionnez l'option **Exiger une facturation directe**.</span><span class="sxs-lookup"><span data-stu-id="fac80-138">Select the **Require direct invoicing** option.</span></span> 

## <a name="can-i-view-purchase-order-line-amounts"></a><span data-ttu-id="fac80-139">Puis-je afficher les montants de la ligne de commande fournisseur ?</span><span class="sxs-lookup"><span data-stu-id="fac80-139">Can I view purchase order line amounts?</span></span>
<span data-ttu-id="fac80-140">Oui.</span><span class="sxs-lookup"><span data-stu-id="fac80-140">Yes.</span></span> <span data-ttu-id="fac80-141">Vous pouvez afficher les montants de ligne d'une commande fournisseur (notamment le montant commandé actuel, les montants reçus ou facturés).</span><span class="sxs-lookup"><span data-stu-id="fac80-141">Line amounts for a purchase order can be viewed, including the current ordered amount and any amounts that have been received or invoiced.</span></span> <span data-ttu-id="fac80-142">Vous pouvez également afficher les montants restant à facturer ou ceux des factures en attente.</span><span class="sxs-lookup"><span data-stu-id="fac80-142">They can also view any amounts that remain to be invoiced or amounts for pending invoices.</span></span>

### <a name="tip"></a><span data-ttu-id="fac80-143">Conseil</span><span class="sxs-lookup"><span data-stu-id="fac80-143">Tip</span></span>

<span data-ttu-id="fac80-144">Supposons que vous affichiez une ligne de commande fournisseur contenant des achats validés dans deux comptes généraux.</span><span class="sxs-lookup"><span data-stu-id="fac80-144">Let’s say you view a purchase order line with purchases posted to two ledger accounts.</span></span> <span data-ttu-id="fac80-145">Le premier inclut le mobilier de bureau commandé auprès d'un fournisseur.</span><span class="sxs-lookup"><span data-stu-id="fac80-145">One ledger account is for office furniture ordered from a vendor.</span></span> <span data-ttu-id="fac80-146">Le second inclut les fournitures de bureau.</span><span class="sxs-lookup"><span data-stu-id="fac80-146">The second ledger account is for office supplies.</span></span> <span data-ttu-id="fac80-147">Le montant commandé est égal à la somme des montants facturés, des montants des factures en attente, et des montants restants à facturer.</span><span class="sxs-lookup"><span data-stu-id="fac80-147">The ordered amount is equal to the sum of the invoiced amounts, pending invoice amounts, and invoice remaining amounts.</span></span> <span data-ttu-id="fac80-148">Le montant reçu correspond à la partie du montant commandé reçu du fournisseur.</span><span class="sxs-lookup"><span data-stu-id="fac80-148">The received amount is the portion of the ordered amount that has been received from the vendor.</span></span>

<table style="width:100%;">

<col width="16%" />
<col width="16%" />
<col width="16%" />
<col width="16%" />
<col width="16%" />
<col width="16%" />

<tbody>
<tr class="odd">
<td><span data-ttu-id="fac80-149"><strong>Compte général</strong></span><span class="sxs-lookup"><span data-stu-id="fac80-149"><strong>Ledger account</strong></span></span></td>
<td><span data-ttu-id="fac80-150"><strong>Commandé</strong></span><span class="sxs-lookup"><span data-stu-id="fac80-150"><strong>Ordered</strong></span></span></td>
<td><span data-ttu-id="fac80-151"><strong>Reçu</strong></span><span class="sxs-lookup"><span data-stu-id="fac80-151"><strong>Received</strong></span></span></td>
<td><span data-ttu-id="fac80-152"><strong>Facturé</strong></span><span class="sxs-lookup"><span data-stu-id="fac80-152"><strong>Invoiced</strong></span></span></td>
<td><span data-ttu-id="fac80-153"><strong>Facture en attente</strong></span><span class="sxs-lookup"><span data-stu-id="fac80-153"><strong>Pending invoice</strong></span></span></td>
<td><span data-ttu-id="fac80-154"><strong>Reste de la facture</strong></span><span class="sxs-lookup"><span data-stu-id="fac80-154"><strong>Invoice remaining</strong></span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="fac80-155">60010 (mobilier de bureau)</span><span class="sxs-lookup"><span data-stu-id="fac80-155">60010 (office furniture)</span></span></td>
<td><p><span data-ttu-id="fac80-156">1 200,00</span><span class="sxs-lookup"><span data-stu-id="fac80-156">1,200.00</span></span></p></td>
<td><span data-ttu-id="fac80-157">250,00</span><span class="sxs-lookup"><span data-stu-id="fac80-157">250.00</span></span></td>
<td><span data-ttu-id="fac80-158">350,00</span><span class="sxs-lookup"><span data-stu-id="fac80-158">350.00</span></span></td>
<td><span data-ttu-id="fac80-159">200,00</span><span class="sxs-lookup"><span data-stu-id="fac80-159">200.00</span></span></td>
<td><p><span data-ttu-id="fac80-160">650,00</span><span class="sxs-lookup"><span data-stu-id="fac80-160">650.00</span></span></p></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="fac80-161">60020 (fournitures de bureau)</span><span class="sxs-lookup"><span data-stu-id="fac80-161">60020 (office supplies)</span></span></td>
<td><p><span data-ttu-id="fac80-162">750,00</span><span class="sxs-lookup"><span data-stu-id="fac80-162">750.00</span></span></p></td>
<td><span data-ttu-id="fac80-163">150,00</span><span class="sxs-lookup"><span data-stu-id="fac80-163">150.00</span></span></td>
<td><span data-ttu-id="fac80-164">400,00</span><span class="sxs-lookup"><span data-stu-id="fac80-164">400.00</span></span></td>
<td></td>
<td><p><span data-ttu-id="fac80-165">350,00</span><span class="sxs-lookup"><span data-stu-id="fac80-165">350.00</span></span></p></td>
</tr>
<tr class="even">
<td><span data-ttu-id="fac80-166">Totaux</span><span class="sxs-lookup"><span data-stu-id="fac80-166">Totals</span></span></td>
<td><p><span data-ttu-id="fac80-167">1 950,00</span><span class="sxs-lookup"><span data-stu-id="fac80-167">1,950.00</span></span></p></td>
<td><span data-ttu-id="fac80-168">400,00</span><span class="sxs-lookup"><span data-stu-id="fac80-168">400.00</span></span></td>
<td><span data-ttu-id="fac80-169">750,00</span><span class="sxs-lookup"><span data-stu-id="fac80-169">750.00</span></span></td>
<td><span data-ttu-id="fac80-170">200,00</span><span class="sxs-lookup"><span data-stu-id="fac80-170">200.00</span></span></td>
<td><p><span data-ttu-id="fac80-171">1 000,00</span><span class="sxs-lookup"><span data-stu-id="fac80-171">1,000.00</span></span></p></td>
</tr>
</tbody>
</table>

 

<span data-ttu-id="fac80-172">Pour plus d'informations, voir [Approvisionnements](../../supply-chain/procurement/procurement-sourcing-overview.md) et [Comptabilité fournisseur dans le secteur public](accounts-payable-public-sector.md).</span><span class="sxs-lookup"><span data-stu-id="fac80-172">For more information, see [Procurement and sourcing](../../supply-chain/procurement/procurement-sourcing-overview.md) and [Accounts payable in the public sector](accounts-payable-public-sector.md).</span></span>




