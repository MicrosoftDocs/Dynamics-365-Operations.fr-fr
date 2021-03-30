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
ms.openlocfilehash: f0fee32d9fd1ab89b1a8cedb2e1965674586d4e7
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5227182"
---
# <a name="key-invoice-data-into-accounts-payable-using-an-approval-journal"></a><span data-ttu-id="9b855-103">Indexer les données de facturation dans la comptabilité fournisseur à l’aide d’un journal d’approbation</span><span class="sxs-lookup"><span data-stu-id="9b855-103">Key invoice data into accounts payable using an approval journal</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="9b855-104">Cette rubrique explique comment utiliser le registre des factures pour créer des factures et utiliser le journal d’approbation pour mettre à jour les comptes de dépenses.</span><span class="sxs-lookup"><span data-stu-id="9b855-104">This topic explains how to use the invoice register to create invoices and then use the approval journal to update the expense accounts.</span></span>

## <a name="create-and-post-and-invoice"></a><span data-ttu-id="9b855-105">Créer et valider une facture</span><span class="sxs-lookup"><span data-stu-id="9b855-105">Create and post and invoice</span></span>
1. <span data-ttu-id="9b855-106">Dans le volet de navigation, accédez **Modules > Comptabilité fournisseur > Factures > Registre des factures**.</span><span class="sxs-lookup"><span data-stu-id="9b855-106">In the navigation pan, go to **Modules > Accounts payable > Invoices > Invoice register**.</span></span>
2. <span data-ttu-id="9b855-107">Sélectionnez **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="9b855-107">Select **New**.</span></span>
3. <span data-ttu-id="9b855-108">Sélectionnez le nom du registre des factures à utiliser.</span><span class="sxs-lookup"><span data-stu-id="9b855-108">Select the name of the invoice register that you want to use.</span></span>
4. <span data-ttu-id="9b855-109">Sélectionnez **Lignes** pour ouvrir le registre, puis entrez des lignes de dépense.</span><span class="sxs-lookup"><span data-stu-id="9b855-109">Select **Lines** to open the register and enter expense lines.</span></span>
5. <span data-ttu-id="9b855-110">Sélectionnez un fournisseur.</span><span class="sxs-lookup"><span data-stu-id="9b855-110">Select a vendor.</span></span> <span data-ttu-id="9b855-111">Par exemple, entrez ou sélectionnez `US-104`.</span><span class="sxs-lookup"><span data-stu-id="9b855-111">For example, enter or select `US-104`.</span></span>
6. <span data-ttu-id="9b855-112">Dans le champ **Facture**, tapez une valeur.</span><span class="sxs-lookup"><span data-stu-id="9b855-112">In the **Invoice** field, type a value.</span></span>
7. <span data-ttu-id="9b855-113">Tapez une valeur dans le champ **Description**.</span><span class="sxs-lookup"><span data-stu-id="9b855-113">In the **Description** field, type a value.</span></span>
8. <span data-ttu-id="9b855-114">Dans le champ **Crédit**, entrez un numéro.</span><span class="sxs-lookup"><span data-stu-id="9b855-114">In the **Credit** field, enter a number.</span></span>
9. <span data-ttu-id="9b855-115">Dans le champ **Approuvé par**, sélectionnez un approbateur dans le menu déroulant.</span><span class="sxs-lookup"><span data-stu-id="9b855-115">In the **Approved by** field, select an approver from the drop-down menu.</span></span>
10. <span data-ttu-id="9b855-116">Sélectionnez **Valider**.</span><span class="sxs-lookup"><span data-stu-id="9b855-116">Select **Post**.</span></span>

## <a name="approve-an-invoice"></a><span data-ttu-id="9b855-117">Approuver une facture</span><span class="sxs-lookup"><span data-stu-id="9b855-117">Approve an invoice</span></span>
1. <span data-ttu-id="9b855-118">Dans le volet de navigation, accédez à **Modules > Comptabilité fournisseur > Factures > Approbation des factures**.</span><span class="sxs-lookup"><span data-stu-id="9b855-118">In the navigation pane, go to **Modules > Accounts payable > Invoices > Invoice approval**.</span></span>
2. <span data-ttu-id="9b855-119">Sélectionnez **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="9b855-119">Select **New**.</span></span>
3. <span data-ttu-id="9b855-120">Sélectionnez le nom du journal d’approbation des factures à utiliser.</span><span class="sxs-lookup"><span data-stu-id="9b855-120">Select the name of the invoice approval journal that you want to use.</span></span>
4. <span data-ttu-id="9b855-121">Sélectionnez **Lignes** pour afficher la page sur laquelle vous pourrez sélectionner les factures que vous souhaitez approuver.</span><span class="sxs-lookup"><span data-stu-id="9b855-121">Select **Lines** to display a page where you will be able to select the invoices that you want to approve.</span></span>
5. <span data-ttu-id="9b855-122">Sélectionnez **Rechercher des N° documents** pour afficher toutes les factures prêtes pour approbation.</span><span class="sxs-lookup"><span data-stu-id="9b855-122">Select **Find Vouchers** to display all of the invoices that are ready for approval.</span></span>
6. <span data-ttu-id="9b855-123">Marquez la facture que vous avez créée, puis cliquez sur **Sélectionner**.</span><span class="sxs-lookup"><span data-stu-id="9b855-123">Mark the invoice that you created, then click **Select**.</span></span> <span data-ttu-id="9b855-124">Les N° documents sélectionnés précédemment sont déplacés vers cette liste une fois que vous les avez sélectionnés.</span><span class="sxs-lookup"><span data-stu-id="9b855-124">The vouchers that you selected above are moved to this list after you select them.</span></span>  
7. <span data-ttu-id="9b855-125">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="9b855-125">Select **OK**.</span></span>
8. <span data-ttu-id="9b855-126">Sélectionnez le champ **Numéro de compte** pour ajouter un compte de dépenses à la facture.</span><span class="sxs-lookup"><span data-stu-id="9b855-126">Select the **account number** field to add an expense account to the invoice.</span></span>
9. <span data-ttu-id="9b855-127">Entrez un numéro de compte et appuyez sur la touche de tabulation pour quitter le champ.</span><span class="sxs-lookup"><span data-stu-id="9b855-127">Enter an account number and tab off of the field.</span></span> <span data-ttu-id="9b855-128">Par exemple, entrez `600120`.</span><span class="sxs-lookup"><span data-stu-id="9b855-128">For example, enter `600120`.</span></span>
10. <span data-ttu-id="9b855-129">Sélectionnez **Valider**.</span><span class="sxs-lookup"><span data-stu-id="9b855-129">Select **Post**.</span></span>
11. <span data-ttu-id="9b855-130">Sélectionnez **N° document** pour afficher les entrées qui ont été validées.</span><span class="sxs-lookup"><span data-stu-id="9b855-130">Select **Voucher** to view the entries that were posted.</span></span> <span data-ttu-id="9b855-131">Le compte Factures en attente d’approbation est contrepassé et remplacé par le compte de dépenses actif.</span><span class="sxs-lookup"><span data-stu-id="9b855-131">The Invoice Pending Approval account is reversed and replaced with the actual expense account.</span></span>  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]