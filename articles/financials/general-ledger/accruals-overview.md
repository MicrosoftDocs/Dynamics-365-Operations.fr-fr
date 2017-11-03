---
title: "Vue d'ensemble des régularisations"
description: "Cet article décrit les régularisations, et fournit des informations sur leur paramétrage pour créer des transactions."
author: aprilolson
manager: AnnBe
ms.date: 08/01/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: LedgerAccuralTable
audience: Application User
ms.reviewer: robinr
ms.search.scope: Core, Operations
ms.custom: 14131
ms.assetid: 0489b59a-37a7-4a78-87bf-4b597e9efad9
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: 00ecc493e6dcf59ab61e7082297c95516a248b58
ms.contentlocale: fr-fr
ms.lasthandoff: 11/03/2017

---

# <a name="accruals-overview"></a><span data-ttu-id="72fea-103">Vue d'ensemble des régularisations</span><span class="sxs-lookup"><span data-stu-id="72fea-103">Accruals overview</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="72fea-104">Cet article décrit les régularisations, et fournit des informations sur leur paramétrage pour créer des transactions.</span><span class="sxs-lookup"><span data-stu-id="72fea-104">This article describes accruals, and provides information about how to set them up and create transactions.</span></span>

<span data-ttu-id="72fea-105">Les régularisations sont utilisées dans la comptabilité d'exercice pour suivre le produit identifié dans la période à laquelle il a été acquis, et non lorsque le paiement est reçu, et pour suivre les dépenses (coûts) identifiées lorsqu'ils surviennent, et non lors du paiement.</span><span class="sxs-lookup"><span data-stu-id="72fea-105">Accruals are used in accrual accounting to track revenue that is recognized in the period that it's earned in, not when payment is received, and to track expenses (costs) that are recognized when they occur, not when payment is made.</span></span>

## <a name="accrual-schemes"></a><span data-ttu-id="72fea-106">Plans de régularisation</span><span class="sxs-lookup"><span data-stu-id="72fea-106">Accrual schemes</span></span>
<span data-ttu-id="72fea-107">Des plans de régularisation permettent de paramétrer le produit et les coûts différés, et le même plan de régularisation peut être utilisé pour le produit et les coûts.</span><span class="sxs-lookup"><span data-stu-id="72fea-107">Accrual schemes are used to set up the deferred revenue and costs, and the same accrual scheme can be used for both revenue and costs.</span></span> <span data-ttu-id="72fea-108">La régularisation des comptes redistribue les coûts ou le produit d'une ligne de journal à reconnaître dans les périodes appropriées.</span><span class="sxs-lookup"><span data-stu-id="72fea-108">Ledger accruals redistribute the costs or revenue of a journal line so that the costs and revenues are recognized in the appropriate periods.</span></span> <span data-ttu-id="72fea-109">Dans la page **Plan de régularisation**, spécifiez les comptes débiteurs et créditeurs qui seront utilisés lors de l'application du plan de régularisation.</span><span class="sxs-lookup"><span data-stu-id="72fea-109">On the **Accrual scheme** page, you specify the debit and the credit accounts that will be used when the accrual scheme is applied.</span></span>

-   <span data-ttu-id="72fea-110">**Débit** – Le compte principal que vous définissez remplace le compte principal de débit dans la ligne de N° document de journal.</span><span class="sxs-lookup"><span data-stu-id="72fea-110">**Debit** – The main account that you define will replace the debit main account on the journal voucher line.</span></span> <span data-ttu-id="72fea-111">Ce compte est également utilisé pour la contrepassation des différés, selon les transactions de régularisation des comptes.</span><span class="sxs-lookup"><span data-stu-id="72fea-111">This account will also be used for the reversal of the deferral, based on the ledger accrual transactions.</span></span>
-   <span data-ttu-id="72fea-112">**Crédit** – Le compte principal que vous définissez remplace le compte principal de crédit dans la ligne de N° document de journal.</span><span class="sxs-lookup"><span data-stu-id="72fea-112">**Credit** – the main account that you define will replace the credit main account on the journal voucher line.</span></span> <span data-ttu-id="72fea-113">Ce compte est également utilisé pour la contrepassation des différés, selon les transactions de régularisation des comptes.</span><span class="sxs-lookup"><span data-stu-id="72fea-113">This account will also be used for the reversal of the deferral, based on the ledger accrual transactions.</span></span>

<span data-ttu-id="72fea-114">Après avoir déterminé les comptes à utiliser, vous pouvez spécifier comment le n° document est créé lorsque des transactions de régularisation sont créées.</span><span class="sxs-lookup"><span data-stu-id="72fea-114">After you determine which accounts to use, you can specify how the voucher number is created when accrual transactions are created.</span></span> <span data-ttu-id="72fea-115">Vous pouvez également spécifier la fréquence à laquelle les transactions ont lieu, le nombre de fois que des transactions sont créées, et le moment où les transactions sont validées.</span><span class="sxs-lookup"><span data-stu-id="72fea-115">You can also specify how often the transactions occur, the number of times that the transactions are created, and when the transactions are posted.</span></span> <span data-ttu-id="72fea-116">Une fois le plan de régularisation créé, vous pouvez l'utiliser dans certains journaux à l'aide de la fonction de régularisation des comptes.</span><span class="sxs-lookup"><span data-stu-id="72fea-116">After the accrual scheme has been created, you can use it in some of the journals by using the Ledger accruals function.</span></span>

## <a name="ledger-accruals"></a><span data-ttu-id="72fea-117">Charges et produits constatés d'avance</span><span class="sxs-lookup"><span data-stu-id="72fea-117">Ledger accruals</span></span>
<span data-ttu-id="72fea-118">Lorsque vous entrez un journal, vous pouvez cliquer sur **Régularisation des comptes** dans le menu **Fonctions**.</span><span class="sxs-lookup"><span data-stu-id="72fea-118">When you enter a journal, you can click **Ledger accruals** on the **Functions** menu.</span></span> <span data-ttu-id="72fea-119">Puis, lorsque vous sélectionnez le plan de régularisation, vous verrez le montant de base du journal qui sera réparti sur la période, comme déterminé par le plan de régularisation.</span><span class="sxs-lookup"><span data-stu-id="72fea-119">Then, when you select the accrual scheme, you will see the base amount from the journal that will be spread over the period, as determined by the accrual scheme.</span></span> <span data-ttu-id="72fea-120">Par exemple, si vous payez l'assurance de l'employé pour toute l'année en janvier, et le montant est 12 000, vous devez identifier cette dépense chaque mois.</span><span class="sxs-lookup"><span data-stu-id="72fea-120">For example, if you pay an employee's insurance for the whole year in January, and the amount is 12,000, you must recognize that expense each month.</span></span> <span data-ttu-id="72fea-121">Vous pouvez sélectionner la date de début.</span><span class="sxs-lookup"><span data-stu-id="72fea-121">You can select the start date.</span></span> <span data-ttu-id="72fea-122">Vous pouvez également indiquer si le montant qui est à recevoir est basée sur le compte ou le compte de contrepartie.</span><span class="sxs-lookup"><span data-stu-id="72fea-122">You can also specify whether the amount that is accrued is based on the account or the offset account.</span></span> <span data-ttu-id="72fea-123">Après avoir effectué vos sélections, cliquez sur **Transactions** pour afficher toutes les transactions créées selon le plan de régularisation.</span><span class="sxs-lookup"><span data-stu-id="72fea-123">After you make your selections, click **Transactions** to view all the transactions that have been created based on the accrual scheme.</span></span> <span data-ttu-id="72fea-124">Par exemple, si vous étalez les 12 000 dans des dépenses d'assurance au cours de l'année, vous verrez 1 000 pour chaque mois.</span><span class="sxs-lookup"><span data-stu-id="72fea-124">For example, if you spread the 12,000 in insurance expenses over the year, you will see 1,000 for each month.</span></span> <span data-ttu-id="72fea-125">Après avoir validé le journal, vous pouvez afficher les transactions à l'aide de la page de recherche **Transactions de N° document**.</span><span class="sxs-lookup"><span data-stu-id="72fea-125">After you post the journal, you can view the transactions by using the **Voucher transactions** inquiry page.</span></span> <span data-ttu-id="72fea-126">Si un plan de régularisation ne peut pas être appliqué (par exemple, lorsqu'une facture de commande client ou une facture de commande fournisseur est impliquée), vous pouvez créditer le montant payé d'avance et débiter le montant des dépenses.</span><span class="sxs-lookup"><span data-stu-id="72fea-126">If an accrual scheme can't be applied (for example, when a sales order invoice or purchase order invoice is involved), you can credit the prepaid amount and debit the expense amount.</span></span> <span data-ttu-id="72fea-127">Vous pouvez ensuite sélectionner **Contrepartie** lorsque vous appliquez le plan de régularisation.</span><span class="sxs-lookup"><span data-stu-id="72fea-127">You can then select **Offset** when you apply the accrual scheme.</span></span>


<span data-ttu-id="72fea-128">Pour plus d'informations, voir [Créer des plans de régularisation](tasks/create-accrual-schemes.md) et [Créer des transactions de régularisation des comptes](tasks/create-ledger-accrual-transactions.md).</span><span class="sxs-lookup"><span data-stu-id="72fea-128">For more information, see [Create accrual schemes](tasks/create-accrual-schemes.md) and [Create ledger accrual transactions](tasks/create-ledger-accrual-transactions.md).</span></span>

