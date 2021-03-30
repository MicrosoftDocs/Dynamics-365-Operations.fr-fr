---
title: Auditer les factures et indexer les données dans la comptabilité fournisseur
description: Cette rubrique montre comment auditer les factures et les données clés de la comptabilité fournisseur.
author: saraschi2
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: PurchTable, PurchCreateOrder, PurchEditLines, VendEditInvoice, VendEditInvoiceDefaultQuantityForLinesDropDialog,  VendJournalMatch_PackingSlip, VendInvoiceMatchingDetails
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 6188b10327e4827cf5752fa56c3d491ef315b955
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5204759"
---
# <a name="audit-invoices-and-key-data-in-accounts-payable"></a><span data-ttu-id="e0e1d-103">Auditer les factures et indexer les données dans la comptabilité fournisseur</span><span class="sxs-lookup"><span data-stu-id="e0e1d-103">Audit invoices and key data in accounts payable</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="e0e1d-104">Lorsque vous recevez une facture d’un fournisseur pour des marchandises ou des services sur une commande fournisseur, il est possible que les processus entreprise demandent que les marchandises ou les services soient reçus avant que la facture ne soit approuvée pour paiement.</span><span class="sxs-lookup"><span data-stu-id="e0e1d-104">When you receive an invoice from a vendor for goods or services on a purchase order, the business processes might require that the goods or services be received before the invoice can be approved for payment.</span></span> <span data-ttu-id="e0e1d-105">Avant de commencer, vérifiez que la clé de configuration Rapprochement de factures est sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="e0e1d-105">Before you begin, make sure that the Invoice matching configuration key is selected.</span></span> 

<span data-ttu-id="e0e1d-106">Dans la page **Comptabilité fournisseur**, vérifiez que l’option Activer le contrôle de rapprochement de factures est sélectionnée, que le champ **Valider la facture avec les non-correspondances** est bien défini sur **Demander une approbation**, et que le champ **Stratégie de rapprochement des lignes** est défini sur **Rapprochement à trois facteurs**.</span><span class="sxs-lookup"><span data-stu-id="e0e1d-106">In the **Accounts payable parameters** page, ensure that the Enable invoice matching validation option is selected, the **Post invoice with discrepancies** field is set to **Require approval**, and the **Line matching policy** field is set to **Three-way matching**.</span></span>

<span data-ttu-id="e0e1d-107">La société fictive USMF sert d’exemple dans cette procédure.</span><span class="sxs-lookup"><span data-stu-id="e0e1d-107">This procedure uses the USMF demo company.</span></span> <span data-ttu-id="e0e1d-108">Les différentes étapes seront effectuées par le responsable comptabilité fournisseur ou le gestionnaire comptable.</span><span class="sxs-lookup"><span data-stu-id="e0e1d-108">The accounts payable manager or accounting manager role would perform these steps.</span></span>


## <a name="create-a-purchase-order"></a><span data-ttu-id="e0e1d-109">Créer une commande fournisseur</span><span class="sxs-lookup"><span data-stu-id="e0e1d-109">Create a purchase order</span></span>
1. <span data-ttu-id="e0e1d-110">Accédez à **Toutes les commandes fournisseur**.</span><span class="sxs-lookup"><span data-stu-id="e0e1d-110">Go to **All purchase orders**.</span></span>
2. <span data-ttu-id="e0e1d-111">Cliquez sur **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="e0e1d-111">Click **New**.</span></span>
3. <span data-ttu-id="e0e1d-112">Dans le champ **Compte fournisseur**, tapez une valeur.</span><span class="sxs-lookup"><span data-stu-id="e0e1d-112">In the **Vendor account** field, type a value.</span></span>
4. <span data-ttu-id="e0e1d-113">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="e0e1d-113">Click **OK**.</span></span>
5. <span data-ttu-id="e0e1d-114">Cliquez sur **Ajouter une ligne**.</span><span class="sxs-lookup"><span data-stu-id="e0e1d-114">Click **Add line**.</span></span>
6. <span data-ttu-id="e0e1d-115">Dans le champ **Numéro d’article**, tapez une valeur.</span><span class="sxs-lookup"><span data-stu-id="e0e1d-115">In the **Item number** field, type a value.</span></span>
7. <span data-ttu-id="e0e1d-116">Dans le volet Actions, cliquez sur **Achat**.</span><span class="sxs-lookup"><span data-stu-id="e0e1d-116">On the Action Pane, click **Purchase**.</span></span>
8. <span data-ttu-id="e0e1d-117">Cliquez sur **Confirmer**.</span><span class="sxs-lookup"><span data-stu-id="e0e1d-117">Click **Confirm**.</span></span>

## <a name="post-a-product-receipt"></a><span data-ttu-id="e0e1d-118">Valider un accusé de réception de marchandises</span><span class="sxs-lookup"><span data-stu-id="e0e1d-118">Post a product receipt</span></span>
1. <span data-ttu-id="e0e1d-119">Dans le volet Action, cliquez sur **Recevoir**.</span><span class="sxs-lookup"><span data-stu-id="e0e1d-119">On the Action Pane, click **Receive**.</span></span>
2. <span data-ttu-id="e0e1d-120">Cliquez sur **Accusé de réception de marchandises**.</span><span class="sxs-lookup"><span data-stu-id="e0e1d-120">Click **Product receipt**.</span></span>
3. <span data-ttu-id="e0e1d-121">Dans le champ **Accusé de réception de marchandises**, tapez une valeur.</span><span class="sxs-lookup"><span data-stu-id="e0e1d-121">In the **Product receipt** field, type a value.</span></span>
4. <span data-ttu-id="e0e1d-122">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="e0e1d-122">Click **OK**.</span></span>

## <a name="record-and-match-a-vendor-invoice-to-a-product-receipt"></a><span data-ttu-id="e0e1d-123">Enregistrer et mettre en correspondance une facture fournisseur avec un accusé de réception de marchandises</span><span class="sxs-lookup"><span data-stu-id="e0e1d-123">Record and match a vendor invoice to a product receipt</span></span>
1. <span data-ttu-id="e0e1d-124">Dans le volet Actions, cliquez sur **Facture > Facture**.</span><span class="sxs-lookup"><span data-stu-id="e0e1d-124">On the Action Pane, click **Invoice > Invoice**.</span></span>
2. <span data-ttu-id="e0e1d-125">Dans le champ **Nombre**, tapez une valeur.</span><span class="sxs-lookup"><span data-stu-id="e0e1d-125">In the **Number** field, type a value.</span></span>
3. <span data-ttu-id="e0e1d-126">Cliquez sur **Valeur par défaut de : Quantité commandée** pour ouvrir la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="e0e1d-126">Click **Default from: Ordered quantity** to open the drop dialog.</span></span>
4. <span data-ttu-id="e0e1d-127">Dans le champ **Quantité par défaut pour les lignes**, sélectionnez une option.</span><span class="sxs-lookup"><span data-stu-id="e0e1d-127">In the **Default quantity for lines** field, select an option.</span></span>
5. <span data-ttu-id="e0e1d-128">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="e0e1d-128">Click **OK**.</span></span>
6. <span data-ttu-id="e0e1d-129">Cliquez sur **Oui**.</span><span class="sxs-lookup"><span data-stu-id="e0e1d-129">Click **Yes**.</span></span>
7. <span data-ttu-id="e0e1d-130">Cliquez sur **Mettre en correspondance les accusés de réception de marchandises**.</span><span class="sxs-lookup"><span data-stu-id="e0e1d-130">Click **Match product receipts**.</span></span>
8. <span data-ttu-id="e0e1d-131">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="e0e1d-131">Click **OK**.</span></span>
9. <span data-ttu-id="e0e1d-132">Cliquez sur **Revoir** dans le volet Actions.</span><span class="sxs-lookup"><span data-stu-id="e0e1d-132">On the Action Pane, click **Review**.</span></span>
10. <span data-ttu-id="e0e1d-133">Cliquez sur **Mise en correspondance des détails**.</span><span class="sxs-lookup"><span data-stu-id="e0e1d-133">Click **Matching details**.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]