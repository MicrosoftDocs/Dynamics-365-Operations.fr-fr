---
title: Indexer les données de facturation dans la comptabilité fournisseur à l’aide d’un journal d’approbation
description: Cette rubrique explique comment utiliser le registre des factures pour créer des factures et utiliser le journal d’approbation pour mettre à jour les comptes de dépenses.
author: abruer
manager: AnnBe
ms.date: 08/08/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerJournalTable, LedgerJournalTransInvoiceRegister, HcmWorkerLookUp, LedgerJournalTransApprove, LedgerJournalTransApproveFetchVouchers, LedgerTransVoucher
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: abruer
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: f19c31a3ca20ad4b11e2529bdcb9db351c37f6c2
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4971876"
---
# <a name="key-invoice-data-into-accounts-payable-using-an-approval-journal"></a><span data-ttu-id="d0be0-103">Indexer les données de facturation dans la comptabilité fournisseur à l’aide d’un journal d’approbation</span><span class="sxs-lookup"><span data-stu-id="d0be0-103">Key invoice data into accounts payable using an approval journal</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="d0be0-104">Cette rubrique explique comment utiliser le registre des factures pour créer des factures et utiliser le journal d’approbation pour mettre à jour les comptes de dépenses.</span><span class="sxs-lookup"><span data-stu-id="d0be0-104">This topic explains how to use the invoice register to create invoices and then use the approval journal to update the expense accounts.</span></span>

## <a name="create-and-post-and-invoice"></a><span data-ttu-id="d0be0-105">Créer et valider une facture</span><span class="sxs-lookup"><span data-stu-id="d0be0-105">Create and post and invoice</span></span>
1. <span data-ttu-id="d0be0-106">Dans le volet de navigation, accédez **Modules > Comptabilité fournisseur > Factures > Registre des factures**.</span><span class="sxs-lookup"><span data-stu-id="d0be0-106">In the navigation pan, go to **Modules > Accounts payable > Invoices > Invoice register**.</span></span>
2. <span data-ttu-id="d0be0-107">Sélectionnez **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="d0be0-107">Select **New**.</span></span>
3. <span data-ttu-id="d0be0-108">Sélectionnez le nom du registre des factures à utiliser.</span><span class="sxs-lookup"><span data-stu-id="d0be0-108">Select the name of the invoice register that you want to use.</span></span>
4. <span data-ttu-id="d0be0-109">Sélectionnez **Lignes** pour ouvrir le registre, puis entrez des lignes de dépense.</span><span class="sxs-lookup"><span data-stu-id="d0be0-109">Select **Lines** to open the register and enter expense lines.</span></span>
5. <span data-ttu-id="d0be0-110">Sélectionnez un fournisseur.</span><span class="sxs-lookup"><span data-stu-id="d0be0-110">Select a vendor.</span></span> <span data-ttu-id="d0be0-111">Par exemple, entrez ou sélectionnez `US-104`.</span><span class="sxs-lookup"><span data-stu-id="d0be0-111">For example, enter or select `US-104`.</span></span>
6. <span data-ttu-id="d0be0-112">Dans le champ **Facture**, tapez une valeur.</span><span class="sxs-lookup"><span data-stu-id="d0be0-112">In the **Invoice** field, type a value.</span></span>
7. <span data-ttu-id="d0be0-113">Tapez une valeur dans le champ **Description**.</span><span class="sxs-lookup"><span data-stu-id="d0be0-113">In the **Description** field, type a value.</span></span>
8. <span data-ttu-id="d0be0-114">Dans le champ **Crédit**, entrez un numéro.</span><span class="sxs-lookup"><span data-stu-id="d0be0-114">In the **Credit** field, enter a number.</span></span>
9. <span data-ttu-id="d0be0-115">Dans le champ **Approuvé par**, sélectionnez un approbateur dans le menu déroulant.</span><span class="sxs-lookup"><span data-stu-id="d0be0-115">In the **Approved by** field, select an approver from the drop-down menu.</span></span>
10. <span data-ttu-id="d0be0-116">Sélectionnez **Valider**.</span><span class="sxs-lookup"><span data-stu-id="d0be0-116">Select **Post**.</span></span>

## <a name="approve-an-invoice"></a><span data-ttu-id="d0be0-117">Approuver une facture</span><span class="sxs-lookup"><span data-stu-id="d0be0-117">Approve an invoice</span></span>
1. <span data-ttu-id="d0be0-118">Dans le volet de navigation, accédez à **Modules > Comptabilité fournisseur > Factures > Approbation des factures**.</span><span class="sxs-lookup"><span data-stu-id="d0be0-118">In the navigation pane, go to **Modules > Accounts payable > Invoices > Invoice approval**.</span></span>
2. <span data-ttu-id="d0be0-119">Sélectionnez **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="d0be0-119">Select **New**.</span></span>
3. <span data-ttu-id="d0be0-120">Sélectionnez le nom du journal d’approbation des factures à utiliser.</span><span class="sxs-lookup"><span data-stu-id="d0be0-120">Select the name of the invoice approval journal that you want to use.</span></span>
4. <span data-ttu-id="d0be0-121">Sélectionnez **Lignes** pour afficher la page sur laquelle vous pourrez sélectionner les factures que vous souhaitez approuver.</span><span class="sxs-lookup"><span data-stu-id="d0be0-121">Select **Lines** to display a page where you will be able to select the invoices that you want to approve.</span></span>
5. <span data-ttu-id="d0be0-122">Sélectionnez **Rechercher des N° documents** pour afficher toutes les factures prêtes pour approbation.</span><span class="sxs-lookup"><span data-stu-id="d0be0-122">Select **Find Vouchers** to display all of the invoices that are ready for approval.</span></span>
6. <span data-ttu-id="d0be0-123">Marquez la facture que vous avez créée, puis cliquez sur **Sélectionner**.</span><span class="sxs-lookup"><span data-stu-id="d0be0-123">Mark the invoice that you created, then click **Select**.</span></span> <span data-ttu-id="d0be0-124">Les N° documents sélectionnés précédemment sont déplacés vers cette liste une fois que vous les avez sélectionnés.</span><span class="sxs-lookup"><span data-stu-id="d0be0-124">The vouchers that you selected above are moved to this list after you select them.</span></span>  
7. <span data-ttu-id="d0be0-125">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="d0be0-125">Select **OK**.</span></span>
8. <span data-ttu-id="d0be0-126">Sélectionnez le champ **Numéro de compte** pour ajouter un compte de dépenses à la facture.</span><span class="sxs-lookup"><span data-stu-id="d0be0-126">Select the **account number** field to add an expense account to the invoice.</span></span>
9. <span data-ttu-id="d0be0-127">Entrez un numéro de compte et appuyez sur la touche de tabulation pour quitter le champ.</span><span class="sxs-lookup"><span data-stu-id="d0be0-127">Enter an account number and tab off of the field.</span></span> <span data-ttu-id="d0be0-128">Par exemple, entrez `600120`.</span><span class="sxs-lookup"><span data-stu-id="d0be0-128">For example, enter `600120`.</span></span>
10. <span data-ttu-id="d0be0-129">Sélectionnez **Valider**.</span><span class="sxs-lookup"><span data-stu-id="d0be0-129">Select **Post**.</span></span>
11. <span data-ttu-id="d0be0-130">Sélectionnez **N° document** pour afficher les entrées qui ont été validées.</span><span class="sxs-lookup"><span data-stu-id="d0be0-130">Select **Voucher** to view the entries that were posted.</span></span> <span data-ttu-id="d0be0-131">Le compte Factures en attente d’approbation est contrepassé et remplacé par le compte de dépenses actif.</span><span class="sxs-lookup"><span data-stu-id="d0be0-131">The Invoice Pending Approval account is reversed and replaced with the actual expense account.</span></span>  

