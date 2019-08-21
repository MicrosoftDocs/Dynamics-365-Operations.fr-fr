---
title: Auditer les factures et les données clé dans le système de comptabilité fournisseur
description: Lorsque vous recevez une facture d'un fournisseur pour des marchandises ou des services sur une commande fournisseur, il est possible que les processus entreprise demandent que les marchandises ou les services soient reçus avant que la facture ne soit approuvée pour paiement.
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
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: c6e8967fe4db67ff98fc7093792bdb82b73a33d9
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/01/2019
ms.locfileid: "1834972"
---
# <a name="audit-invoices-and-key-data-in-ap-system"></a><span data-ttu-id="dddab-103">Auditer les factures et les données clé dans le système de comptabilité fournisseur</span><span class="sxs-lookup"><span data-stu-id="dddab-103">Audit invoices and key data in AP system</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="dddab-104">Lorsque vous recevez une facture d'un fournisseur pour des marchandises ou des services sur une commande fournisseur, il est possible que les processus entreprise demandent que les marchandises ou les services soient reçus avant que la facture ne soit approuvée pour paiement.</span><span class="sxs-lookup"><span data-stu-id="dddab-104">When you receive an invoice from a vendor for goods or services on a purchase order, the business processes might require that the goods or services be received before the invoice can be approved for payment.</span></span> <span data-ttu-id="dddab-105">Avant de commencer, vérifiez que la clé de configuration Rapprochement de factures est sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="dddab-105">Before you begin, make sure that the Invoice matching configuration key is selected.</span></span> 

<span data-ttu-id="dddab-106">Dans la page Comptabilité fournisseur, vérifiez que l'option Activer le contrôle de rapprochement de factures est sélectionnée, que le champ Valider la facture avec les non-correspondances est bien défini sur Demander une approbation, et que le champ Stratégie de rapprochement des lignes est défini sur Rapprochement à trois facteurs.</span><span class="sxs-lookup"><span data-stu-id="dddab-106">In the Accounts payable parameters page, ensure that the Enable invoice matching validation option is selected, the Post invoice with discrepancies field is set to Require approval, and the Line matching policy field is set to Three-way matching.</span></span>

<span data-ttu-id="dddab-107">La société fictive USMF sert d'exemple dans cette procédure.</span><span class="sxs-lookup"><span data-stu-id="dddab-107">This procedure uses the USMF demo company.</span></span> <span data-ttu-id="dddab-108">Les différentes étapes seront effectuées par le responsable comptabilité fournisseur ou le gestionnaire comptable.</span><span class="sxs-lookup"><span data-stu-id="dddab-108">The accounts payable manager or accounting manager role would perform these steps.</span></span>


## <a name="create-a-purchase-order"></a><span data-ttu-id="dddab-109">Créer une commande fournisseur</span><span class="sxs-lookup"><span data-stu-id="dddab-109">Create a purchase order</span></span>
1. <span data-ttu-id="dddab-110">Accédez à **Toutes les commandes fournisseur**.</span><span class="sxs-lookup"><span data-stu-id="dddab-110">Go to **All purchase orders**.</span></span>
2. <span data-ttu-id="dddab-111">Cliquez sur **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="dddab-111">Click **New**.</span></span>
3. <span data-ttu-id="dddab-112">Dans le champ **Compte fournisseur**, tapez une valeur.</span><span class="sxs-lookup"><span data-stu-id="dddab-112">In the **Vendor account** field, type a value.</span></span>
4. <span data-ttu-id="dddab-113">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="dddab-113">Click **OK**.</span></span>
5. <span data-ttu-id="dddab-114">Cliquez sur **Ajouter une ligne**.</span><span class="sxs-lookup"><span data-stu-id="dddab-114">Click **Add line**.</span></span>
6. <span data-ttu-id="dddab-115">Dans le champ **Numéro d'article**, tapez une valeur.</span><span class="sxs-lookup"><span data-stu-id="dddab-115">In the **Item number** field, type a value.</span></span>
7. <span data-ttu-id="dddab-116">Dans le volet Actions, cliquez sur **Achat**.</span><span class="sxs-lookup"><span data-stu-id="dddab-116">On the Action Pane, click **Purchase**.</span></span>
8. <span data-ttu-id="dddab-117">Cliquez sur **Confirmer**.</span><span class="sxs-lookup"><span data-stu-id="dddab-117">Click **Confirm**.</span></span>

## <a name="post-a-product-receipt"></a><span data-ttu-id="dddab-118">Valider un accusé de réception de marchandises</span><span class="sxs-lookup"><span data-stu-id="dddab-118">Post a product receipt</span></span>
1. <span data-ttu-id="dddab-119">Dans le volet Action, cliquez sur **Recevoir**.</span><span class="sxs-lookup"><span data-stu-id="dddab-119">On the Action Pane, click **Receive**.</span></span>
2. <span data-ttu-id="dddab-120">Cliquez sur **Accusé de réception de marchandises**.</span><span class="sxs-lookup"><span data-stu-id="dddab-120">Click **Product receipt**.</span></span>
3. <span data-ttu-id="dddab-121">Dans le champ **Accusé de réception de marchandises**, tapez une valeur.</span><span class="sxs-lookup"><span data-stu-id="dddab-121">In the **Product receipt** field, type a value.</span></span>
4. <span data-ttu-id="dddab-122">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="dddab-122">Click **OK**.</span></span>

## <a name="record-and-match-a-vendor-invoice-to-a-product-receipt"></a><span data-ttu-id="dddab-123">Enregistrer et mettre en correspondance une facture fournisseur avec un accusé de réception de marchandises</span><span class="sxs-lookup"><span data-stu-id="dddab-123">Record and match a vendor invoice to a product receipt</span></span>
1. <span data-ttu-id="dddab-124">Dans le volet Actions, cliquez sur **Facture > Facture**.</span><span class="sxs-lookup"><span data-stu-id="dddab-124">On the Action Pane, click **Invoice > Invoice**.</span></span>
2. <span data-ttu-id="dddab-125">Dans le champ **Nombre**, tapez une valeur.</span><span class="sxs-lookup"><span data-stu-id="dddab-125">In the **Number** field, type a value.</span></span>
3. <span data-ttu-id="dddab-126">Cliquez sur **Valeur par défaut de : Quantité commandée** pour ouvrir la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="dddab-126">Click **Default from: Ordered quantity** to open the drop dialog.</span></span>
4. <span data-ttu-id="dddab-127">Dans le champ **Quantité par défaut pour les lignes**, sélectionnez une option.</span><span class="sxs-lookup"><span data-stu-id="dddab-127">In the **Default quantity for lines** field, select an option.</span></span>
5. <span data-ttu-id="dddab-128">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="dddab-128">Click **OK**.</span></span>
6. <span data-ttu-id="dddab-129">Cliquez sur **Oui**.</span><span class="sxs-lookup"><span data-stu-id="dddab-129">Click **Yes**.</span></span>
7. <span data-ttu-id="dddab-130">Cliquez sur **Mettre en correspondance les accusés de réception de marchandises**.</span><span class="sxs-lookup"><span data-stu-id="dddab-130">Click **Match product receipts**.</span></span>
8. <span data-ttu-id="dddab-131">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="dddab-131">Click **OK**.</span></span>
9. <span data-ttu-id="dddab-132">Cliquez sur **Revoir** dans le volet Actions.</span><span class="sxs-lookup"><span data-stu-id="dddab-132">On the Action Pane, click **Review**.</span></span>
10. <span data-ttu-id="dddab-133">Cliquez sur **Mise en correspondance des détails**.</span><span class="sxs-lookup"><span data-stu-id="dddab-133">Click **Matching details**.</span></span>

