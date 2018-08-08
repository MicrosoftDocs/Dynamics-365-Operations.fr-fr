--- 
title: "Auditer les factures et les données clés dans la comptabilité fournisseur"
description: "Lorsque vous recevez une facture d'un fournisseur pour des marchandises ou des services sur une commande fournisseur, il est possible que les processus entreprise demandent que les marchandises ou les services soient reçus avant que la facture ne soit approuvée pour paiement."
author: saraschi2
manager: AnnBe
ms.date: 02/16/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Operations
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: d9747ba144d56c9410846769e5465372c89ea111
ms.openlocfilehash: c928edee086835479ab6d150b1dd86df1824226f
ms.contentlocale: fr-fr
ms.lasthandoff: 08/07/2018

---
# <a name="audit-invoices-and-key-data-in-accounts-payable"></a><span data-ttu-id="57291-103">Auditer les factures et les données clés dans la comptabilité fournisseur</span><span class="sxs-lookup"><span data-stu-id="57291-103">Audit invoices and key data in accounts payable</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="57291-104">Lorsque vous recevez une facture d'un fournisseur pour des marchandises ou des services sur une commande fournisseur, il est possible que les processus entreprise demandent que les marchandises ou les services soient reçus avant que la facture ne soit approuvée pour paiement.</span><span class="sxs-lookup"><span data-stu-id="57291-104">When you receive an invoice from a vendor for goods or services on a purchase order, the business processes might require that the goods or services be received before the invoice can be approved for payment.</span></span> <span data-ttu-id="57291-105">Avant de commencer, vérifiez que la clé de configuration Rapprochement de factures est sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="57291-105">Before you begin, make sure that the Invoice matching configuration key is selected.</span></span> 

<span data-ttu-id="57291-106">Dans la page Comptabilité fournisseur, vérifiez que l'option Activer le contrôle de rapprochement de factures est sélectionnée, que le champ Valider la facture avec les non-correspondances est bien défini sur Demander une approbation, et que le champ Stratégie de rapprochement des lignes est défini sur Rapprochement à trois facteurs.</span><span class="sxs-lookup"><span data-stu-id="57291-106">In the Accounts payable parameters page, ensure that the Enable invoice matching validation option is selected, the Post invoice with discrepancies field is set to Require approval, and the Line matching policy field is set to Three-way matching.</span></span>

<span data-ttu-id="57291-107">La société fictive USMF sert d'exemple dans cette procédure.</span><span class="sxs-lookup"><span data-stu-id="57291-107">This procedure uses the USMF demo company.</span></span> <span data-ttu-id="57291-108">Les différentes étapes seront effectuées par le responsable comptabilité fournisseur ou le gestionnaire comptable.</span><span class="sxs-lookup"><span data-stu-id="57291-108">The accounts payable manager or accounting manager role would perform these steps.</span></span>


## <a name="create-a-purchase-order"></a><span data-ttu-id="57291-109">Créer une commande fournisseur</span><span class="sxs-lookup"><span data-stu-id="57291-109">Create a purchase order</span></span>
1. <span data-ttu-id="57291-110">Allez dans Toutes les commandes fournisseur.</span><span class="sxs-lookup"><span data-stu-id="57291-110">Go to All purchase orders.</span></span>
2. <span data-ttu-id="57291-111">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="57291-111">Click New.</span></span>
3. <span data-ttu-id="57291-112">Dans le champ Compte fournisseur, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="57291-112">In the Vendor account field, click the drop-down button to open the lookup.</span></span>
4. <span data-ttu-id="57291-113">Tapez une valeur dans le champ Compte fournisseur.</span><span class="sxs-lookup"><span data-stu-id="57291-113">In the Vendor account field, type a value.</span></span>
5. <span data-ttu-id="57291-114">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="57291-114">Click OK.</span></span>
6. <span data-ttu-id="57291-115">Cliquez sur Ajouter une ligne.</span><span class="sxs-lookup"><span data-stu-id="57291-115">Click Add line.</span></span>
7. <span data-ttu-id="57291-116">Tapez une valeur dans le champ Numéro d'article.</span><span class="sxs-lookup"><span data-stu-id="57291-116">In the Item number field, type a value.</span></span>
8. <span data-ttu-id="57291-117">Cliquez sur Achats dans le volet Actions.</span><span class="sxs-lookup"><span data-stu-id="57291-117">On the Action Pane, click Purchase.</span></span>
9. <span data-ttu-id="57291-118">Cliquez sur Confirmer.</span><span class="sxs-lookup"><span data-stu-id="57291-118">Click Confirm.</span></span>

## <a name="post-a-product-receipt"></a><span data-ttu-id="57291-119">Valider un accusé de réception de marchandises</span><span class="sxs-lookup"><span data-stu-id="57291-119">Post a product receipt</span></span>
1. <span data-ttu-id="57291-120">Dans le volet Actions, cliquez sur Recevoir.</span><span class="sxs-lookup"><span data-stu-id="57291-120">On the Action Pane, click Receive.</span></span>
2. <span data-ttu-id="57291-121">Cliquez sur Accusé de réception de marchandises.</span><span class="sxs-lookup"><span data-stu-id="57291-121">Click Product receipt.</span></span>
3. <span data-ttu-id="57291-122">Dans la liste, marquez la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="57291-122">In the list, mark the selected row.</span></span>
4. <span data-ttu-id="57291-123">Tapez une valeur dans le champ Accusé de réception de marchandises.</span><span class="sxs-lookup"><span data-stu-id="57291-123">In the Product receipt field, type a value.</span></span>
5. <span data-ttu-id="57291-124">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="57291-124">Click OK.</span></span>

## <a name="record-and-match-a-vendor-invoice-to-a-product-receipt"></a><span data-ttu-id="57291-125">Enregistrer et mettre en correspondance une facture fournisseur avec un accusé de réception de marchandises</span><span class="sxs-lookup"><span data-stu-id="57291-125">Record and match a vendor invoice to a product receipt</span></span>
1. <span data-ttu-id="57291-126">Dans le volet Actions, cliquez sur Facture.</span><span class="sxs-lookup"><span data-stu-id="57291-126">On the Action Pane, click Invoice.</span></span>
2. <span data-ttu-id="57291-127">Cliquez sur Facture.</span><span class="sxs-lookup"><span data-stu-id="57291-127">Click Invoice.</span></span>
3. <span data-ttu-id="57291-128">Tapez une valeur dans le champ Nombre.</span><span class="sxs-lookup"><span data-stu-id="57291-128">In the Number field, type a value.</span></span>
4. <span data-ttu-id="57291-129">Cliquez sur Valeur par défaut de : Quantité commandée pour ouvrir la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="57291-129">Click Default from: Ordered quantity to open the drop dialog.</span></span>
5. <span data-ttu-id="57291-130">Sélectionnez une option dans le champ Quantité par défaut pour les lignes.</span><span class="sxs-lookup"><span data-stu-id="57291-130">In the Default quantity for lines field, select an option.</span></span>
6. <span data-ttu-id="57291-131">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="57291-131">Click OK.</span></span>
7. <span data-ttu-id="57291-132">Cliquez sur Oui.</span><span class="sxs-lookup"><span data-stu-id="57291-132">Click Yes.</span></span>
8. <span data-ttu-id="57291-133">Cliquez sur Mettre en correspondance les accusés de réception de marchandises.</span><span class="sxs-lookup"><span data-stu-id="57291-133">Click Match product receipts.</span></span>
9. <span data-ttu-id="57291-134">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="57291-134">Click OK.</span></span>
10. <span data-ttu-id="57291-135">Cliquez sur Revoir dans le volet Actions.</span><span class="sxs-lookup"><span data-stu-id="57291-135">On the Action Pane, click Review.</span></span>
11. <span data-ttu-id="57291-136">Cliquez sur Mise en correspondance des détails.</span><span class="sxs-lookup"><span data-stu-id="57291-136">Click Matching details.</span></span>


