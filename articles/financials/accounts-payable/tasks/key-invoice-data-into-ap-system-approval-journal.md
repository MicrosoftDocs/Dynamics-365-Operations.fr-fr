---
title: Données de facture clés dans le système de comptabilité fournisseur à l'aide du journal d'approbation
description: Ce guide de tâche vous indique comment utiliser le registre des factures pour créer des factures et utiliser le journal d'approbation pour mettre à jour les comptes de dépenses.
author: abruer
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerJournalTable, LedgerJournalTransInvoiceRegister, HcmWorkerLookUp, LedgerJournalTransApprove, LedgerJournalTransApproveFetchVouchers, LedgerTransVoucher
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: abruer
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 048eda77064b6aa3f666e998a8e551d2f7adc385
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/29/2019
ms.locfileid: "363520"
---
# <a name="key-invoice-data-into-ap-system-using-approval-journal"></a><span data-ttu-id="baba4-103">Données de facture clés dans le système de comptabilité fournisseur à l'aide du journal d'approbation</span><span class="sxs-lookup"><span data-stu-id="baba4-103">Key invoice data into AP system using approval journal</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="baba4-104">Ce guide de tâche vous indique comment utiliser le registre des factures pour créer des factures et utiliser le journal d'approbation pour mettre à jour les comptes de dépenses.</span><span class="sxs-lookup"><span data-stu-id="baba4-104">This task guide will show you how to use the invoice register to create invoices and then use the approval journal to update the expense accounts.</span></span>


## <a name="create-and-post-and-invoice"></a><span data-ttu-id="baba4-105">Créer et valider une facture</span><span class="sxs-lookup"><span data-stu-id="baba4-105">Create and post and invoice</span></span>
1. <span data-ttu-id="baba4-106">Accédez à Comptabilité fournisseur > Factures > Registre des factures.</span><span class="sxs-lookup"><span data-stu-id="baba4-106">Go to Accounts payable > Invoices > Invoice register.</span></span>
2. <span data-ttu-id="baba4-107">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="baba4-107">Click New.</span></span>
3. <span data-ttu-id="baba4-108">Sélectionnez le nom du registre des factures à utiliser.</span><span class="sxs-lookup"><span data-stu-id="baba4-108">Select the name of the invoice register that you want to use.</span></span>
4. <span data-ttu-id="baba4-109">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="baba4-109">In the list, click the link in the selected row.</span></span>
5. <span data-ttu-id="baba4-110">Cliquez sur Lignes pour ouvrir le registre, puis entrez des lignes de dépense.</span><span class="sxs-lookup"><span data-stu-id="baba4-110">Click on Lines to open the register and enter expense lines.</span></span>
6. <span data-ttu-id="baba4-111">Sélectionnez un fournisseur.</span><span class="sxs-lookup"><span data-stu-id="baba4-111">Select a vendor.</span></span> <span data-ttu-id="baba4-112">Par exemple, entrez ou sélectionnez US-104</span><span class="sxs-lookup"><span data-stu-id="baba4-112">For example, enter or select US-104</span></span>
7. <span data-ttu-id="baba4-113">Tapez une valeur dans le champ Facture.</span><span class="sxs-lookup"><span data-stu-id="baba4-113">In the Invoice field, type a value.</span></span>
8. <span data-ttu-id="baba4-114">Tapez une valeur dans le champ Description.</span><span class="sxs-lookup"><span data-stu-id="baba4-114">In the Description field, type a value.</span></span>
9. <span data-ttu-id="baba4-115">Entrez un numéro dans le champ Crédit.</span><span class="sxs-lookup"><span data-stu-id="baba4-115">In the Credit field, enter a number.</span></span>
10. <span data-ttu-id="baba4-116">Dans le champ Approbateur, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="baba4-116">In the Approved by field, click the drop-down button to open the lookup.</span></span>
11. <span data-ttu-id="baba4-117">Mettez un approbateur en surbrillance et cliquez sur Sélectionner pour le sélectionner.</span><span class="sxs-lookup"><span data-stu-id="baba4-117">Highlight an approver and click Select to select that approver.</span></span>
12. <span data-ttu-id="baba4-118">Cliquez sur Valider.</span><span class="sxs-lookup"><span data-stu-id="baba4-118">Click Post.</span></span>
13. <span data-ttu-id="baba4-119">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="baba4-119">Close the page.</span></span>
14. <span data-ttu-id="baba4-120">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="baba4-120">Close the page.</span></span>

## <a name="approve-an-invoice"></a><span data-ttu-id="baba4-121">Approuver une facture</span><span class="sxs-lookup"><span data-stu-id="baba4-121">Approve an invoice</span></span>
1. <span data-ttu-id="baba4-122">Accédez à Comptabilité fournisseur > Factures > Approbation de facture.</span><span class="sxs-lookup"><span data-stu-id="baba4-122">Go to Accounts payable > Invoices > Invoice approval.</span></span>
2. <span data-ttu-id="baba4-123">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="baba4-123">Click New.</span></span>
3. <span data-ttu-id="baba4-124">Sélectionnez le nom du journal d'approbation des factures à utiliser.</span><span class="sxs-lookup"><span data-stu-id="baba4-124">Select the name of the invoice approval journal that you want to use.</span></span>
4. <span data-ttu-id="baba4-125">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="baba4-125">In the list, click the link in the selected row.</span></span>
5. <span data-ttu-id="baba4-126">Cliquez sur les lignes pour afficher la page dans laquelle vous pourrez sélectionner les factures que vous souhaitez approuver.</span><span class="sxs-lookup"><span data-stu-id="baba4-126">Click lines to display a page where you will be able to select the invoices that you want to approve.</span></span>
6. <span data-ttu-id="baba4-127">Sélectionnez Rechercher des N° documents pour afficher toutes les factures prêtes pour approbation.</span><span class="sxs-lookup"><span data-stu-id="baba4-127">Select Find Vouchers to display all of the invoices that are ready for approval.</span></span>
7. <span data-ttu-id="baba4-128">Marquez la facture que vous avez créée.</span><span class="sxs-lookup"><span data-stu-id="baba4-128">Mark the invoice that you created.</span></span>
8. <span data-ttu-id="baba4-129">Cliquez sur Sélectionner.</span><span class="sxs-lookup"><span data-stu-id="baba4-129">Click Select.</span></span>
    * <span data-ttu-id="baba4-130">Les N° documents sélectionnés précédemment sont déplacés vers cette liste une fois que vous les avez sélectionnés.</span><span class="sxs-lookup"><span data-stu-id="baba4-130">The vouchers that you selected above are moved to this list after you select them.</span></span>  
9. <span data-ttu-id="baba4-131">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="baba4-131">Click OK.</span></span>
10. <span data-ttu-id="baba4-132">Cliquez sur le champ Numéro de compte pour ajouter un compte de dépenses à la facture.</span><span class="sxs-lookup"><span data-stu-id="baba4-132">Click on the account number field to add an expense account to the invoice.</span></span>
11. <span data-ttu-id="baba4-133">Entrez un numéro de compte et appuyez sur la touche de tabulation pour quitter le champ.</span><span class="sxs-lookup"><span data-stu-id="baba4-133">Enter an account number and tab off of the field.</span></span> <span data-ttu-id="baba4-134">Par exemple, entrez 600120.</span><span class="sxs-lookup"><span data-stu-id="baba4-134">For example, enter 600120.</span></span>
12. <span data-ttu-id="baba4-135">Cliquez sur Valider.</span><span class="sxs-lookup"><span data-stu-id="baba4-135">Click Post.</span></span>
13. <span data-ttu-id="baba4-136">Cliquez sur N° document pour afficher les entrées qui ont été validées.</span><span class="sxs-lookup"><span data-stu-id="baba4-136">Click Voucher to view the entries that were posted.</span></span>
    * <span data-ttu-id="baba4-137">Le compte Factures en attente d'approbation est contrepassé et remplacé par le compte de dépenses actif.</span><span class="sxs-lookup"><span data-stu-id="baba4-137">The Invoice Pending Approval account is reversed and replaced with the actual expense account.</span></span>  

