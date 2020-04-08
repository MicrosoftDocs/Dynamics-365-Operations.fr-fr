---
title: Indexer les données de facturation dans la comptabilité fournisseur à l'aide d'un registre de factures
description: Cette rubrique décrit comment utiliser le registre des factures pour créer des factures.
author: abruer
manager: AnnBe
ms.date: 07/31/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Operations
ms.search.region: Global
ms.author: abruer
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: cd6de42dda650d42d703e905f8d48f73b9e4afd6
ms.sourcegitcommit: 57e1dafa186fec77ddd8ba9425d238e36e0f0998
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/18/2020
ms.locfileid: "3143809"
---
# <a name="key-invoice-data-into-the-ap-system-using-invoice-pool"></a><span data-ttu-id="2d12e-103">Indexer les données de facturation dans la comptabilité fournisseur à l'aide d'un registre de factures</span><span class="sxs-lookup"><span data-stu-id="2d12e-103">Key invoice data into the AP system using invoice pool</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="2d12e-104">Cette rubrique décrit comment utiliser le registre des factures pour créer des factures.</span><span class="sxs-lookup"><span data-stu-id="2d12e-104">This topic describes how to use the invoice register to create invoices.</span></span> <span data-ttu-id="2d12e-105">Utilisez ensuite le regroupement de factures pour mettre en correspondance la facture avec une commande fournisseur et finalisez la dépense dans la page de facture fournisseur.</span><span class="sxs-lookup"><span data-stu-id="2d12e-105">Then use the invoice pool to match the invoice to a purchase order and finalize the expense in the vendor invoice page.</span></span>


## <a name="create-a-purchase-order"></a><span data-ttu-id="2d12e-106">Créer une commande fournisseur</span><span class="sxs-lookup"><span data-stu-id="2d12e-106">Create a purchase order</span></span>
1. <span data-ttu-id="2d12e-107">Dans le volet de navigation, accédez à **Modules > Comptabilité fournisseur > Commandes fournisseur > Commandes fournisseur**.</span><span class="sxs-lookup"><span data-stu-id="2d12e-107">In the navigation pane, go to **Modules > Accounts payable > Purchase orders > Purchase orders**.</span></span>
2. <span data-ttu-id="2d12e-108">Sélectionnez **Nouveau** pour créer une commande fournisseur.</span><span class="sxs-lookup"><span data-stu-id="2d12e-108">Select **New** to create a purchase order.</span></span>
3. <span data-ttu-id="2d12e-109">Dans le champ **Compte fournisseur**, sélectionnez un fournisseur depuis la liste déroulante.</span><span class="sxs-lookup"><span data-stu-id="2d12e-109">In the **Vendor account** field, select a vendor for the drop-down list.</span></span> <span data-ttu-id="2d12e-110">Par exemple, sélectionnez le fournisseur **1001**.</span><span class="sxs-lookup"><span data-stu-id="2d12e-110">For example, select vendor **1001**.</span></span>
4. <span data-ttu-id="2d12e-111">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="2d12e-111">Select **OK**.</span></span>
5. <span data-ttu-id="2d12e-112">Dans le champ **Numéro d'article**, sélectionnez le numéro d'article de services dans la liste déroulante.</span><span class="sxs-lookup"><span data-stu-id="2d12e-112">In the **Item number** field, select the services item number in the drop-down list.</span></span> <span data-ttu-id="2d12e-113">Par exemple, sélectionnez **S0001**.</span><span class="sxs-lookup"><span data-stu-id="2d12e-113">For example, select **S0001**.</span></span> <span data-ttu-id="2d12e-114">Le montant HT est de 75,00 €.</span><span class="sxs-lookup"><span data-stu-id="2d12e-114">The net amount is 75.00.</span></span>  <span data-ttu-id="2d12e-115">Il s'agit du montant attendu sur la facture.</span><span class="sxs-lookup"><span data-stu-id="2d12e-115">That is the amount that we will expect on the invoice.</span></span>  
6. <span data-ttu-id="2d12e-116">Dans le volet Actions, sélectionnez **Achat**.</span><span class="sxs-lookup"><span data-stu-id="2d12e-116">On the action pane, select **Purchase**.</span></span>
7. <span data-ttu-id="2d12e-117">Sélectionnez **Confirmer**.</span><span class="sxs-lookup"><span data-stu-id="2d12e-117">Select **Confirm**.</span></span>

## <a name="create-and-post-and-invoice"></a><span data-ttu-id="2d12e-118">Créer et valider une facture</span><span class="sxs-lookup"><span data-stu-id="2d12e-118">Create and post and invoice</span></span>
1. <span data-ttu-id="2d12e-119">Dans le volet de navigation, accédez à **Modules > Comptabilité fournisseur > Factures > Registre des factures**.</span><span class="sxs-lookup"><span data-stu-id="2d12e-119">In the navigation pane, go to **Modules > Accounts payable > Invoices > Invoice register**.</span></span>
2. <span data-ttu-id="2d12e-120">Sélectionnez **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="2d12e-120">Select **New**.</span></span>
3. <span data-ttu-id="2d12e-121">Ouvrez la recherche pour sélectionner le nom du registre des factures à utiliser.</span><span class="sxs-lookup"><span data-stu-id="2d12e-121">Open the lookup to select the name of the invoice register that you want to use.</span></span>
4. <span data-ttu-id="2d12e-122">Sélectionnez le nom du registre des factures à utiliser.</span><span class="sxs-lookup"><span data-stu-id="2d12e-122">Select the name of the invoice register that you want to use.</span></span>
5. <span data-ttu-id="2d12e-123">Sélectionnez **Lignes** pour ouvrir le registre, puis entrez des lignes de dépense.</span><span class="sxs-lookup"><span data-stu-id="2d12e-123">Select **Lines** to open the register and enter expense lines.</span></span>
6. <span data-ttu-id="2d12e-124">Sélectionnez un fournisseur dans le champ de recherche.</span><span class="sxs-lookup"><span data-stu-id="2d12e-124">In the lookup, select a vendor.</span></span> <span data-ttu-id="2d12e-125">Par exemple, sélectionnez le fournisseur **1001**.</span><span class="sxs-lookup"><span data-stu-id="2d12e-125">For example, select vendor **1001**.</span></span>
7. <span data-ttu-id="2d12e-126">Entrez le numéro de la facture dans le champ **Facture**.</span><span class="sxs-lookup"><span data-stu-id="2d12e-126">In the **Invoice** field, enter the invoice number.</span></span>
8. <span data-ttu-id="2d12e-127">Tapez une valeur dans le champ **Description**.</span><span class="sxs-lookup"><span data-stu-id="2d12e-127">In the **Description** field, type a value.</span></span>
9. <span data-ttu-id="2d12e-128">Dans le champ **Crédit**, entrez un numéro.</span><span class="sxs-lookup"><span data-stu-id="2d12e-128">In the **Credit** field, enter a number.</span></span>
10. <span data-ttu-id="2d12e-129">Dans le champ **Commande fournisseur**, ouvrez la liste déroulante pour sélectionner la commande fournisseur créée précédemment.</span><span class="sxs-lookup"><span data-stu-id="2d12e-129">In the **Purchase order** field, open the drop-down list to select the purchase order that you created earlier.</span></span>
11. <span data-ttu-id="2d12e-130">Dans le champ **Approuvé par**, sélectionnez un approbateur dans la liste déroulante et cliquez sur **Sélectionner** pour sélectionner l'approbateur.</span><span class="sxs-lookup"><span data-stu-id="2d12e-130">In the **Approved by** field, highlight an approver in the drop-down list and click **Select** to select that approver.</span></span>
12. <span data-ttu-id="2d12e-131">Sélectionnez **Valider**.</span><span class="sxs-lookup"><span data-stu-id="2d12e-131">Select **Post**.</span></span>

## <a name="open-an-invoice-from-the-pool-and-match-it-to-a-purchase-order-to-complete-the-invoice-process"></a><span data-ttu-id="2d12e-132">Ouvrez une facture à partir du regroupement et faites-la correspondre à une commande fournisseur pour terminer le processus de facturation.</span><span class="sxs-lookup"><span data-stu-id="2d12e-132">Open an invoice from the pool and match it to a purchase order to complete the invoice process</span></span>
1. <span data-ttu-id="2d12e-133">Dans le volet de navigation, accédez à **Modules > Comptabilité fournisseur > Factures > Registre des factures**.</span><span class="sxs-lookup"><span data-stu-id="2d12e-133">In the navigation pane, go to **Modules > Accounts payable > Invoices > Invoice pool**.</span></span>
2. <span data-ttu-id="2d12e-134">Sélectionnez **Commande fournisseur** pour créer une facture fournisseur à partir de la facture dans le registre.</span><span class="sxs-lookup"><span data-stu-id="2d12e-134">Select **Purchase order** to create a vendor invoice from the invoice in the pool.</span></span>
3. <span data-ttu-id="2d12e-135">Sélectionnez la facture que vous souhaitez réviser.</span><span class="sxs-lookup"><span data-stu-id="2d12e-135">Select the invoice that you want to review.</span></span>
4. <span data-ttu-id="2d12e-136">Sélectionnez **Mettre à jour le statut de rapprochement** pour terminer le rapprochement.</span><span class="sxs-lookup"><span data-stu-id="2d12e-136">Select **Update match status** to complete the matching.</span></span>
5. <span data-ttu-id="2d12e-137">Dans le volet Actions, sélectionnez **Options**.</span><span class="sxs-lookup"><span data-stu-id="2d12e-137">On the action pane, select **Options**.</span></span>
6. <span data-ttu-id="2d12e-138">Sélectionnez **Modifier la vue**.</span><span class="sxs-lookup"><span data-stu-id="2d12e-138">Select **Change view**.</span></span>
7. <span data-ttu-id="2d12e-139">Sélectionnez **Vue Grille**.</span><span class="sxs-lookup"><span data-stu-id="2d12e-139">Select **Grid view**.</span></span>
8. <span data-ttu-id="2d12e-140">Sélectionnez **Valider**.</span><span class="sxs-lookup"><span data-stu-id="2d12e-140">Select **Post**.</span></span>
9. <span data-ttu-id="2d12e-141">Permet de fermer l'écran.</span><span class="sxs-lookup"><span data-stu-id="2d12e-141">Close the form.</span></span>
10. <span data-ttu-id="2d12e-142">Dans le volet de navigation, accédez à **Modules > Comptabilité fournisseur > Fournisseurs > Fournisseurs**.</span><span class="sxs-lookup"><span data-stu-id="2d12e-142">In the navigation pane, go to **Modules > Accounts payable > Vendors > Vendors**.</span></span>
11. <span data-ttu-id="2d12e-143">Sélectionnez le fournisseur qui était sur la commande fournisseur.</span><span class="sxs-lookup"><span data-stu-id="2d12e-143">Select the vendor that was on the purchase order.</span></span> <span data-ttu-id="2d12e-144">Par exemple, sélectionnez le fournisseur **1001**.</span><span class="sxs-lookup"><span data-stu-id="2d12e-144">For example, select vendor **1001**.</span></span>
12. <span data-ttu-id="2d12e-145">Dans la volet Actions, sélectionnez **Fournisseur**.</span><span class="sxs-lookup"><span data-stu-id="2d12e-145">On the action pane, select **Vendor**.</span></span>
13. <span data-ttu-id="2d12e-146">Sélectionnez les **transactions**.</span><span class="sxs-lookup"><span data-stu-id="2d12e-146">Select **Transactions**.</span></span>
14. <span data-ttu-id="2d12e-147">Sélectionnez la facture que vous avez créée.</span><span class="sxs-lookup"><span data-stu-id="2d12e-147">Select the invoice that you created.</span></span> <span data-ttu-id="2d12e-148">La régularisation du registre des factures a été contrepassée et validée dans le compte de dépenses approprié.</span><span class="sxs-lookup"><span data-stu-id="2d12e-148">The invoice register accrual was reversed and posted to the appropriate expense account.</span></span>  

