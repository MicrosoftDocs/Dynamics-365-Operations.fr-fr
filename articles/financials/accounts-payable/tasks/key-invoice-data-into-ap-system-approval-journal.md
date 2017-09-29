--- 
title: "Indexer les données de facturation dans la comptabilité fournisseur à l'aide d'un journal d'approbation"
description: "Ce guide de tâche vous indique comment utiliser le registre des factures pour créer des factures et utiliser le journal d'approbation pour mettre à jour les comptes de dépenses."
author: abruer
manager: AnnBe
ms.date: 11/15/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Operations
ms.search.region: Global
ms.author: abruer
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: 604345d357e5019e334017b2b6d0413f40818acc
ms.contentlocale: fr-fr
ms.lasthandoff: 08/29/2017

---
# <a name="key-invoice-data-into-accounts-payable-using-an-approval-journal"></a><span data-ttu-id="bca70-103">Indexer les données de facturation dans la comptabilité fournisseur à l'aide d'un journal d'approbation</span><span class="sxs-lookup"><span data-stu-id="bca70-103">Key invoice data into accounts payable using an approval journal</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="bca70-104">Ce guide de tâche vous indique comment utiliser le registre des factures pour créer des factures et utiliser le journal d'approbation pour mettre à jour les comptes de dépenses.</span><span class="sxs-lookup"><span data-stu-id="bca70-104">This task guide will show you how to use the invoice register to create invoices and then use the approval journal to update the expense accounts.</span></span>


## <a name="create-and-post-and-invoice"></a><span data-ttu-id="bca70-105">Créer et valider une facture</span><span class="sxs-lookup"><span data-stu-id="bca70-105">Create and post and invoice</span></span>
1. <span data-ttu-id="bca70-106">Accédez à Comptabilité fournisseur > Factures > Registre des factures.</span><span class="sxs-lookup"><span data-stu-id="bca70-106">Go to Accounts payable > Invoices > Invoice register.</span></span>
2. <span data-ttu-id="bca70-107">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="bca70-107">Click New.</span></span>
3. <span data-ttu-id="bca70-108">Sélectionnez le nom du registre des factures à utiliser.</span><span class="sxs-lookup"><span data-stu-id="bca70-108">Select the name of the invoice register that you want to use.</span></span>
4. <span data-ttu-id="bca70-109">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="bca70-109">In the list, click the link in the selected row.</span></span>
5. <span data-ttu-id="bca70-110">Cliquez sur Lignes pour ouvrir le registre, puis entrez des lignes de dépense.</span><span class="sxs-lookup"><span data-stu-id="bca70-110">Click on Lines to open the register and enter expense lines.</span></span>
6. <span data-ttu-id="bca70-111">Sélectionnez un fournisseur.</span><span class="sxs-lookup"><span data-stu-id="bca70-111">Select a vendor.</span></span> <span data-ttu-id="bca70-112">Par exemple, entrez ou sélectionnez US-104</span><span class="sxs-lookup"><span data-stu-id="bca70-112">For example, enter or select US-104</span></span>
7. <span data-ttu-id="bca70-113">Tapez une valeur dans le champ Facture.</span><span class="sxs-lookup"><span data-stu-id="bca70-113">In the Invoice field, type a value.</span></span>
8. <span data-ttu-id="bca70-114">Tapez une valeur dans le champ Description.</span><span class="sxs-lookup"><span data-stu-id="bca70-114">In the Description field, type a value.</span></span>
9. <span data-ttu-id="bca70-115">Entrez un numéro dans le champ Crédit.</span><span class="sxs-lookup"><span data-stu-id="bca70-115">In the Credit field, enter a number.</span></span>
10. <span data-ttu-id="bca70-116">Dans le champ Approbateur, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="bca70-116">In the Approved by field, click the drop-down button to open the lookup.</span></span>
11. <span data-ttu-id="bca70-117">Mettez un approbateur en surbrillance et cliquez sur Sélectionner pour le sélectionner.</span><span class="sxs-lookup"><span data-stu-id="bca70-117">Highlight an approver and click Select to select that approver.</span></span>
12. <span data-ttu-id="bca70-118">Cliquez sur Valider.</span><span class="sxs-lookup"><span data-stu-id="bca70-118">Click Post.</span></span>
13. <span data-ttu-id="bca70-119">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="bca70-119">Close the page.</span></span>
14. <span data-ttu-id="bca70-120">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="bca70-120">Close the page.</span></span>

## <a name="approve-an-invoice"></a><span data-ttu-id="bca70-121">Approuver une facture</span><span class="sxs-lookup"><span data-stu-id="bca70-121">Approve an invoice</span></span>
1. <span data-ttu-id="bca70-122">Accédez à Comptabilité fournisseur > Factures > Approbation de facture.</span><span class="sxs-lookup"><span data-stu-id="bca70-122">Go to Accounts payable > Invoices > Invoice approval.</span></span>
2. <span data-ttu-id="bca70-123">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="bca70-123">Click New.</span></span>
3. <span data-ttu-id="bca70-124">Sélectionnez le nom du journal d'approbation des factures à utiliser.</span><span class="sxs-lookup"><span data-stu-id="bca70-124">Select the name of the invoice approval journal that you want to use.</span></span>
4. <span data-ttu-id="bca70-125">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="bca70-125">In the list, click the link in the selected row.</span></span>
5. <span data-ttu-id="bca70-126">Cliquez sur les lignes pour afficher la page dans laquelle vous pourrez sélectionner les factures que vous souhaitez approuver.</span><span class="sxs-lookup"><span data-stu-id="bca70-126">Click lines to display a page where you will be able to select the invoices that you want to approve.</span></span>
6. <span data-ttu-id="bca70-127">Sélectionnez Rechercher des N° documents pour afficher toutes les factures prêtes pour approbation.</span><span class="sxs-lookup"><span data-stu-id="bca70-127">Select Find Vouchers to display all of the invoices that are ready for approval.</span></span>
7. <span data-ttu-id="bca70-128">Marquez la facture que vous avez créée.</span><span class="sxs-lookup"><span data-stu-id="bca70-128">Mark the invoice that you created.</span></span>
8. <span data-ttu-id="bca70-129">Cliquez sur Sélectionner.</span><span class="sxs-lookup"><span data-stu-id="bca70-129">Click Select.</span></span>
    * <span data-ttu-id="bca70-130">Les N° documents sélectionnés précédemment sont déplacés vers cette liste une fois que vous les avez sélectionnés.</span><span class="sxs-lookup"><span data-stu-id="bca70-130">The vouchers that you selected above are moved to this list after you select them.</span></span>  
9. <span data-ttu-id="bca70-131">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="bca70-131">Click OK.</span></span>
10. <span data-ttu-id="bca70-132">Cliquez sur le champ Numéro de compte pour ajouter un compte de dépenses à la facture.</span><span class="sxs-lookup"><span data-stu-id="bca70-132">Click on the account number field to add an expense account to the invoice.</span></span>
11. <span data-ttu-id="bca70-133">Entrez un numéro de compte et appuyez sur la touche de tabulation pour quitter le champ.</span><span class="sxs-lookup"><span data-stu-id="bca70-133">Enter an account number and tab off of the field.</span></span> <span data-ttu-id="bca70-134">Par exemple, entrez 600120.</span><span class="sxs-lookup"><span data-stu-id="bca70-134">For example, enter 600120.</span></span>
12. <span data-ttu-id="bca70-135">Cliquez sur Valider.</span><span class="sxs-lookup"><span data-stu-id="bca70-135">Click Post.</span></span>
13. <span data-ttu-id="bca70-136">Cliquez sur N° document pour afficher les entrées qui ont été validées.</span><span class="sxs-lookup"><span data-stu-id="bca70-136">Click Voucher to view the entries that were posted.</span></span>
    * <span data-ttu-id="bca70-137">Le compte Factures en attente d'approbation est contrepassé et remplacé par le compte de dépenses actif.</span><span class="sxs-lookup"><span data-stu-id="bca70-137">The Invoice Pending Approval account is reversed and replaced with the actual expense account.</span></span>  


