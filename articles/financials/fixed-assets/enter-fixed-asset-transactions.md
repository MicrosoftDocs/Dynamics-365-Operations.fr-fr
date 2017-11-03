---
title: Options des transactions d'immobilisation
description: "Cet article décrit les différentes méthodes disponibles pour créer des transactions d'immobilisation."
author: twheeloc
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: AssetTable, PurchCreateOrder
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 23061
ms.assetid: 338c495b-a4d8-461e-b85b-a83faf673730
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: 18352ad921c2e2d110a7535f979272685105662f
ms.contentlocale: fr-fr
ms.lasthandoff: 11/03/2017

---

# <a name="fixed-asset-transaction-options"></a><span data-ttu-id="94297-103">Options des transactions d'immobilisation</span><span class="sxs-lookup"><span data-stu-id="94297-103">Fixed asset transaction options</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="94297-104">Cet article décrit les différentes méthodes disponibles pour créer des transactions d'immobilisation.</span><span class="sxs-lookup"><span data-stu-id="94297-104">This article describes the different methods available to create fixed asset transactions.</span></span>

<span data-ttu-id="94297-105">Vous pouvez paramétrer le module Immobilisations pour qu'il s'intègre avec les modules Comptabilité, Achats, Ventes et Approvisionnements.</span><span class="sxs-lookup"><span data-stu-id="94297-105">You can set up Fixed assets for integration with Accounts payable, Accounts receivable, Procurement and sourcing, and General ledger.</span></span> <span data-ttu-id="94297-106">Vous pouvez également transférer des articles du module Gestion des stocks dans le module Immobilisations si vous souhaitez utiliser ces articles en interne.</span><span class="sxs-lookup"><span data-stu-id="94297-106">You can also transfer items in Inventory management to Fixed assets if you want to use those items internally.</span></span>

## <a name="accounts-payable"></a><span data-ttu-id="94297-107">Module Comptabilité fournisseur</span><span class="sxs-lookup"><span data-stu-id="94297-107">Accounts payable</span></span>
<span data-ttu-id="94297-108">Vous pouvez entrer les transactions d'immobilisation dans la page N° document de journal.</span><span class="sxs-lookup"><span data-stu-id="94297-108">You can enter Fixed assets transactions in the Journal voucher page.</span></span> <span data-ttu-id="94297-109">Cette page est accessible à partir de la page Journal des factures.</span><span class="sxs-lookup"><span data-stu-id="94297-109">This page can be opened from the Invoice journal page.</span></span> <span data-ttu-id="94297-110">Vous pouvez également ouvrir la page N° document de journal dans la page du journal des approbations de facture.</span><span class="sxs-lookup"><span data-stu-id="94297-110">You can also open the Journal voucher page from the Invoice approval journal page.</span></span> <span data-ttu-id="94297-111">Dans le champ Type de compte de contrepartie, sélectionnez Immobilisations.</span><span class="sxs-lookup"><span data-stu-id="94297-111">In the Offset account type field, select Fixed assets.</span></span> <span data-ttu-id="94297-112">Ensuite, dans le champ Compte de contrepartie, sélectionnez un numéro d'immobilisation.</span><span class="sxs-lookup"><span data-stu-id="94297-112">Then, in the Offset account field, select a fixed asset number.</span></span> <span data-ttu-id="94297-113">Sous l'onglet Immobilisations, entrez les valeurs dans les champs Type de transaction et Registre.</span><span class="sxs-lookup"><span data-stu-id="94297-113">On the Fixed assets tab, enter values in the Transaction type and Book fields.</span></span>

## <a name="accounts-receivable"></a><span data-ttu-id="94297-114">Module Comptabilité client</span><span class="sxs-lookup"><span data-stu-id="94297-114">Accounts receivable</span></span>
<span data-ttu-id="94297-115">Vous pouvez entrer des transactions d'immobilisations dans la page Facture financière.</span><span class="sxs-lookup"><span data-stu-id="94297-115">You can enter Fixed assets transactions in the Free text invoice page.</span></span>  <span data-ttu-id="94297-116">Dans la page Facture financière, dans la grille Lignes de facture, sélectionnez une ligne.</span><span class="sxs-lookup"><span data-stu-id="94297-116">In the Free text invoice page, in the Invoice lines grid, select a line item.</span></span> <span data-ttu-id="94297-117">Cliquez sur l'organisateur Détails de ligne.</span><span class="sxs-lookup"><span data-stu-id="94297-117">Click the Line details FastTab.</span></span> <span data-ttu-id="94297-118">Entrez le numéro de l'immobilisation et le registre pour la transaction de cession.</span><span class="sxs-lookup"><span data-stu-id="94297-118">Enter the fixed asset number and book for the disposal transaction.</span></span> <span data-ttu-id="94297-119">Pour les factures financières, le type de transaction d'immobilisation est toujours Cession - vente.</span><span class="sxs-lookup"><span data-stu-id="94297-119">For free text invoices, the fixed asset transaction type is always Disposal - sale.</span></span>

## <a name="procurement-and-sourcing"></a><span data-ttu-id="94297-120">Approvisionnements</span><span class="sxs-lookup"><span data-stu-id="94297-120">Procurement and sourcing</span></span>
<span data-ttu-id="94297-121">Vous pouvez entrer les transactions d'immobilisation dans la page Commande fournisseur.</span><span class="sxs-lookup"><span data-stu-id="94297-121">You can enter Fixed assets transactions in the Purchase order page.</span></span> <span data-ttu-id="94297-122">Entrez les informations requises pour créer une commande fournisseur, puis cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="94297-122">Enter the required information to create a purchase order, and then click OK.</span></span> <span data-ttu-id="94297-123">Dans la page Commande fournisseur, cliquez sur l'organisateur Détails de ligne.</span><span class="sxs-lookup"><span data-stu-id="94297-123">In the Purchase order page, click the Line details FastTab.</span></span> <span data-ttu-id="94297-124">Puis, sous l'onglet Immobilisations, entrez des informations sur l'immobilisation.</span><span class="sxs-lookup"><span data-stu-id="94297-124">Then, on the Fixed assets tab, enter information about the fixed asset.</span></span> 

<span data-ttu-id="94297-125">Pour valider une transaction d'acquisition pour une immobilisation existante, spécifiez le numéro de l'immobilisation, le registre et le type de transaction.</span><span class="sxs-lookup"><span data-stu-id="94297-125">To post an acquisition transaction for an existing fixed asset, specify the fixed asset number, book, and transaction type.</span></span> <span data-ttu-id="94297-126">L'immobilisation ne peut pas être validée si certaines de ces informations sont manquantes.</span><span class="sxs-lookup"><span data-stu-id="94297-126">The fixed asset cannot be posted if any of this information is missing.</span></span> <span data-ttu-id="94297-127">Pour valider une transaction d'acquisition pour une nouvelle immobilisation, sélectionnez l'option Nouvelle immobilisation ?, puis sélectionnez le groupe d'immobilisations auquel attribuer la nouvelle immobilisation.</span><span class="sxs-lookup"><span data-stu-id="94297-127">To post an acquisition transaction for a new fixed asset, select the New fixed asset? option, and then select the fixed asset group to assign the new asset to.</span></span> <span data-ttu-id="94297-128">Toutefois, aucun champ d'immobilisation pour une ligne n'est disponible si l'article se trouve dans un groupe de modèles de stock qui utilise un modèle de stock de coûts standard.</span><span class="sxs-lookup"><span data-stu-id="94297-128">However, no fixed asset fields are available for a line if the item is in an inventory model group that uses a standard cost inventory model.</span></span> <span data-ttu-id="94297-129">En outre, les options définies dans la page Paramètres des immobilisations déterminent également si vous pouvez valider les transactions d'acquisition à partir des modules Achats.</span><span class="sxs-lookup"><span data-stu-id="94297-129">Additionally, the options that are defined in the Fixed assets parameters page determine whether you can post acquisition transactions from the purchasing modules.</span></span> 

<span data-ttu-id="94297-130">Lorsque le journal Commande fournisseur ou le journal Stock vers immobilisations est utilisé pour acquérir des immobilisations, la valeur du stock est affectée.</span><span class="sxs-lookup"><span data-stu-id="94297-130">When a purchase order or the Inventory to fixed assets journal is used to acquire fixed assets, the inventory value is affected.</span></span>

## <a name="general-ledger"></a><span data-ttu-id="94297-131">Comptabilité</span><span class="sxs-lookup"><span data-stu-id="94297-131">General ledger</span></span>
<span data-ttu-id="94297-132">Vous pouvez valider tout type de transaction d'immobilisation dans la page Journal des opérations diverses.</span><span class="sxs-lookup"><span data-stu-id="94297-132">Any fixed asset transaction type can be posted in the General journal page.</span></span> <span data-ttu-id="94297-133">Vous pouvez également utiliser les journaux dans le module Immobilisations pour valider les transactions d'immobilisation.</span><span class="sxs-lookup"><span data-stu-id="94297-133">You can also use journals in Fixed assets to post fixed asset transactions.</span></span>

## <a name="options-for-entering-fixed-asset-transaction-types"></a><span data-ttu-id="94297-134">Options de saisie des types de transactions d'immobilisation</span><span class="sxs-lookup"><span data-stu-id="94297-134">Options for entering fixed asset transaction types</span></span>


| <span data-ttu-id="94297-135">Type de transaction</span><span class="sxs-lookup"><span data-stu-id="94297-135">Transaction type</span></span>                    | <span data-ttu-id="94297-136">Module</span><span class="sxs-lookup"><span data-stu-id="94297-136">Module</span></span>                   | <span data-ttu-id="94297-137">Options</span><span class="sxs-lookup"><span data-stu-id="94297-137">Options</span></span>                                   |
|-------------------------------------|--------------------------|-------------------------------------------|
| <span data-ttu-id="94297-138">Acquisition, Ajustement d'acquisition</span><span class="sxs-lookup"><span data-stu-id="94297-138">Acquisition, Acquisition adjustment</span></span> | <span data-ttu-id="94297-139">Immobilisations</span><span class="sxs-lookup"><span data-stu-id="94297-139">Fixed assets</span></span>             | <span data-ttu-id="94297-140">Immobilisations, stock vers immobilisation</span><span class="sxs-lookup"><span data-stu-id="94297-140">Fixed assets, Inventory to fixed assets</span></span>   |
|                                     | <span data-ttu-id="94297-141">Comptabilité</span><span class="sxs-lookup"><span data-stu-id="94297-141">General ledger</span></span>           | <span data-ttu-id="94297-142">Journal des opérations diverses</span><span class="sxs-lookup"><span data-stu-id="94297-142">General journal</span></span>                           |
|                                     | <span data-ttu-id="94297-143">Module Comptabilité fournisseur</span><span class="sxs-lookup"><span data-stu-id="94297-143">Accounts payable</span></span>         | <span data-ttu-id="94297-144">Journal des factures, journal d'approbation des factures</span><span class="sxs-lookup"><span data-stu-id="94297-144">Invoice journal, Invoice approval journal</span></span> |
|                                     | <span data-ttu-id="94297-145">Approvisionnements</span><span class="sxs-lookup"><span data-stu-id="94297-145">Procurement and sourcing</span></span> | <span data-ttu-id="94297-146">Commande fournisseur</span><span class="sxs-lookup"><span data-stu-id="94297-146">Purchase order</span></span>                            |
| <span data-ttu-id="94297-147">Amortissement</span><span class="sxs-lookup"><span data-stu-id="94297-147">Depreciation</span></span>                        | <span data-ttu-id="94297-148">Immobilisations</span><span class="sxs-lookup"><span data-stu-id="94297-148">Fixed assets</span></span>             | <span data-ttu-id="94297-149">Immobilisations</span><span class="sxs-lookup"><span data-stu-id="94297-149">Fixed assets</span></span>                              |
|                                     | <span data-ttu-id="94297-150">Comptabilité</span><span class="sxs-lookup"><span data-stu-id="94297-150">General ledger</span></span>           | <span data-ttu-id="94297-151">Journal des opérations diverses</span><span class="sxs-lookup"><span data-stu-id="94297-151">General journal</span></span>                           |
| <span data-ttu-id="94297-152">Cession</span><span class="sxs-lookup"><span data-stu-id="94297-152">Disposal</span></span>                            | <span data-ttu-id="94297-153">Immobilisations</span><span class="sxs-lookup"><span data-stu-id="94297-153">Fixed assets</span></span>             | <span data-ttu-id="94297-154">Immobilisations</span><span class="sxs-lookup"><span data-stu-id="94297-154">Fixed assets</span></span>                              |
| <span data-ttu-id="94297-155">** **</span><span class="sxs-lookup"><span data-stu-id="94297-155">** **</span></span>                               | <span data-ttu-id="94297-156">Comptabilité</span><span class="sxs-lookup"><span data-stu-id="94297-156">General ledger</span></span>           | <span data-ttu-id="94297-157">Journal des opérations diverses</span><span class="sxs-lookup"><span data-stu-id="94297-157">General journal</span></span>                           |
| <span data-ttu-id="94297-158">** **</span><span class="sxs-lookup"><span data-stu-id="94297-158">** **</span></span>                               | <span data-ttu-id="94297-159">Module Comptabilité client</span><span class="sxs-lookup"><span data-stu-id="94297-159">Accounts receivable</span></span>      | <span data-ttu-id="94297-160">Facture financière</span><span class="sxs-lookup"><span data-stu-id="94297-160">Free text invoice</span></span>                         |



<span data-ttu-id="94297-161">Pour plus d'informations, voir [Intégration des immobilisations](fixed-asset-integration.md).</span><span class="sxs-lookup"><span data-stu-id="94297-161">For more information, see [Fixed assets integration](fixed-asset-integration.md).</span></span>




