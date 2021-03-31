---
title: Enregistrer une facture fournisseur dans le journal des factures
description: Ce guide de tâche indique comment enregistrer des factures fournisseur qui ne sont pas associées à des commandes fournisseur.
author: abruer
manager: AnnBe
ms.date: 07/11/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: VendInvoiceWorkspace, LedgerJournalTable, LedgerJournalTransVendInvoice
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: abruer
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: a60a5959046ca9e953bac80aaeb382d07a267643
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5227134"
---
# <a name="record-a-vendor-invoice-in-the-invoice-journal"></a><span data-ttu-id="76d81-103">Enregistrer une facture fournisseur dans le journal des factures</span><span class="sxs-lookup"><span data-stu-id="76d81-103">Record a vendor invoice in the invoice journal</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="76d81-104">Ce guide de tâche indique comment enregistrer des factures fournisseur qui ne sont pas associées à des commandes fournisseur.</span><span class="sxs-lookup"><span data-stu-id="76d81-104">This task guide will show how to record vendor invoices that are not associated with purchase orders.</span></span> <span data-ttu-id="76d81-105">Parmi les exemples de ce type de facture on trouve des dépenses pour les approvisionnements ou les services.</span><span class="sxs-lookup"><span data-stu-id="76d81-105">Examples of this type of invoice include expenses for supplies or services.</span></span>  <span data-ttu-id="76d81-106">La société fictive USMF sert d’exemple dans cet enregistrement.</span><span class="sxs-lookup"><span data-stu-id="76d81-106">This recording uses the USMF demo company.</span></span>

1. <span data-ttu-id="76d81-107">Allez dans **Volet de navigation > Modules > Comptabilité fournisseur > Espaces de travail > Saisie de facture fournisseur**.</span><span class="sxs-lookup"><span data-stu-id="76d81-107">Go to **Navigation pane > Modules > Accounts payable > Workspaces > Vendor invoice entry**.</span></span>
2. <span data-ttu-id="76d81-108">Dans le **Volet Actions**, cliquez sur **Nouveau journal des factures**.</span><span class="sxs-lookup"><span data-stu-id="76d81-108">On the **Action pane**, click **New invoice journal**.</span></span>
3. <span data-ttu-id="76d81-109">Cliquez sur **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="76d81-109">Click **New**.</span></span>
4. <span data-ttu-id="76d81-110">Entrez le nom du journal dans le champ **Nom** ou cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="76d81-110">In the **Name** field, enter the journal name or click the drop down button to open the lookup.</span></span>
5. <span data-ttu-id="76d81-111">Tapez une valeur dans le champ **Description**.</span><span class="sxs-lookup"><span data-stu-id="76d81-111">In the **Description** field, type a value.</span></span>
6. <span data-ttu-id="76d81-112">Dans le **Volet Actions**, cliquez sur **Lignes**.</span><span class="sxs-lookup"><span data-stu-id="76d81-112">On the **Action pane**, click **Lines**.</span></span> <span data-ttu-id="76d81-113">Dans le champ **Date**, entrez la date de validation qui mettra la comptabilité à jour.</span><span class="sxs-lookup"><span data-stu-id="76d81-113">In the **Date** field, enter the posting date that will update General Ledger.</span></span>  
7. <span data-ttu-id="76d81-114">Spécifiez le **Compte fournisseur** dans le champ **Compte**.</span><span class="sxs-lookup"><span data-stu-id="76d81-114">In the **Account** field, specify the **Vendor account**.</span></span>
8. <span data-ttu-id="76d81-115">Entrez le numéro de la facture dans le champ **Facture**.</span><span class="sxs-lookup"><span data-stu-id="76d81-115">In the **Invoice** field, enter the invoice number.</span></span>
9. <span data-ttu-id="76d81-116">Tapez une valeur dans le champ **Description**.</span><span class="sxs-lookup"><span data-stu-id="76d81-116">In the **Description** field, type a value.</span></span>
10. <span data-ttu-id="76d81-117">Dans le champ **Crédit**, entrez un numéro.</span><span class="sxs-lookup"><span data-stu-id="76d81-117">In the **Credit** field, enter a number.</span></span>
11. <span data-ttu-id="76d81-118">Entrez le numéro de compte dans le champ **Compte de contrepartie** ou cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="76d81-118">In the **Offset account** field, enter the account number or click the drop down button to open the lookup</span></span>
    * <span data-ttu-id="76d81-119">Le **Groupe de taxe** est par défaut celui du compte fournisseur.</span><span class="sxs-lookup"><span data-stu-id="76d81-119">The **Sales tax group** will be default from the vendor account.</span></span>  
    * <span data-ttu-id="76d81-120">Le **Groupe de taxe d’article** est par défaut celui du compte principal spécifié dans le champ **Compte de contrepartie**.</span><span class="sxs-lookup"><span data-stu-id="76d81-120">The **Item sales tax group** will be default from the main account specified in the **Offset account** field.</span></span>  
    * <span data-ttu-id="76d81-121">La **Date d’échéance** sera calculée sur la base des conditions de paiement.</span><span class="sxs-lookup"><span data-stu-id="76d81-121">The **Due date** will be calculated based on the Terms of payment.</span></span>  
    * <span data-ttu-id="76d81-122">L’**Escompte de règlement** est par défaut celui du compte fournisseur.</span><span class="sxs-lookup"><span data-stu-id="76d81-122">The **Cash discount** will default from the Vendor account.</span></span>
12. <span data-ttu-id="76d81-123">Si vous avez activé le workflow du journal des factures fournisseur, cliquez sur **Workflow > Envoyer**.</span><span class="sxs-lookup"><span data-stu-id="76d81-123">If you have enabled Vendor invoice journal workflow, click **Workflow > Submit**.</span></span>
    * <span data-ttu-id="76d81-124">Lorsque votre soumission est approuvée, la date sera avancée au premier jour de la prochaine période ouverte, si la date de comptabilisation de la transaction tombe dans une période qui est en attente ou fermée pour la comptabilisation.</span><span class="sxs-lookup"><span data-stu-id="76d81-124">When your submission is approved, the date will be advanced to the first day of the next open period, if the transaction posting date falls within a period that is On hold or Closed for ledger posting.</span></span>
12. <span data-ttu-id="76d81-125">Cliquez sur **Valider**.</span><span class="sxs-lookup"><span data-stu-id="76d81-125">Click **Post**.</span></span>
13. <span data-ttu-id="76d81-126">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="76d81-126">Close the page.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]