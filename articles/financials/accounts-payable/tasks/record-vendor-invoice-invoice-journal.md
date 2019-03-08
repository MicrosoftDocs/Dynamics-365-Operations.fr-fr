---
title: Enregistrer une facture fournisseur dans le journal des factures
description: Ce guide de tâche indique comment enregistrer des factures fournisseur qui ne sont pas associées à des commandes fournisseur.
author: abruer
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: VendInvoiceWorkspace, LedgerJournalTable, LedgerJournalTransVendInvoice
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: abruer
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 775f3764d34cecbfc071ff7420d32c7832b42308
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/29/2019
ms.locfileid: "348938"
---
# <a name="record-a-vendor-invoice-in-the-invoice-journal"></a><span data-ttu-id="94799-103">Enregistrer une facture fournisseur dans le journal des factures</span><span class="sxs-lookup"><span data-stu-id="94799-103">Record a vendor invoice in the invoice journal</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="94799-104">Ce guide de tâche indique comment enregistrer des factures fournisseur qui ne sont pas associées à des commandes fournisseur.</span><span class="sxs-lookup"><span data-stu-id="94799-104">This task guide will show how to record vendor invoices that are not associated with purchase orders.</span></span> <span data-ttu-id="94799-105">Parmi les exemples de ce type de facture on trouve des dépenses pour les approvisionnements ou les services.</span><span class="sxs-lookup"><span data-stu-id="94799-105">Examples of this type of invoice include expenses for supplies or services.</span></span>  <span data-ttu-id="94799-106">La société fictive USMF sert d'exemple dans cet enregistrement.</span><span class="sxs-lookup"><span data-stu-id="94799-106">This recording uses the USMF demo company.</span></span>

1. <span data-ttu-id="94799-107">Accédez à Comptabilité fournisseur > Espaces de travail > Saisie de facture fournisseur.</span><span class="sxs-lookup"><span data-stu-id="94799-107">Go to Accounts payable > Workspaces > Vendor invoice entry.</span></span>
2. <span data-ttu-id="94799-108">Cliquez sur Nouveau journal des factures.</span><span class="sxs-lookup"><span data-stu-id="94799-108">Click New invoice journal.</span></span>
3. <span data-ttu-id="94799-109">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="94799-109">Click New.</span></span>
4. <span data-ttu-id="94799-110">Entrez le nom du journal dans le champ Nom ou cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="94799-110">In the Name field, enter the journal name or click the drop down button to open the lookup.</span></span>
5. <span data-ttu-id="94799-111">Dans le champ Description, entrez une valeur.</span><span class="sxs-lookup"><span data-stu-id="94799-111">In the Description field, type a value.</span></span>
6. <span data-ttu-id="94799-112">Cliquez sur Lignes.</span><span class="sxs-lookup"><span data-stu-id="94799-112">Click Lines.</span></span>
    * <span data-ttu-id="94799-113">Dans le champ Date, entrez la date de validation qui mettra la comptabilité à jour.</span><span class="sxs-lookup"><span data-stu-id="94799-113">In the Date field, enter the posting date that will update General Ledger.</span></span>  
7. <span data-ttu-id="94799-114">Spécifiez le compte fournisseur dans le champ Compte.</span><span class="sxs-lookup"><span data-stu-id="94799-114">In the Account field, specify the Vendor account.</span></span>
8. <span data-ttu-id="94799-115">Entrez le numéro de la facture dans le champ Facture.</span><span class="sxs-lookup"><span data-stu-id="94799-115">In the Invoice field, enter the invoice number.</span></span>
9. <span data-ttu-id="94799-116">Tapez une valeur dans le champ Description.</span><span class="sxs-lookup"><span data-stu-id="94799-116">In the Description field, type a value.</span></span>
10. <span data-ttu-id="94799-117">Entrez un numéro dans le champ Crédit.</span><span class="sxs-lookup"><span data-stu-id="94799-117">In the Credit field, enter a number.</span></span>
11. <span data-ttu-id="94799-118">Entrez le numéro de compte dans le champ Compte de contrepartie ou cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="94799-118">In the Offset account field, enter the account number or click the drop down button to open the lookup</span></span>
    * <span data-ttu-id="94799-119">Le groupe Taxe est par défaut celui du compte fournisseur.</span><span class="sxs-lookup"><span data-stu-id="94799-119">The Sales tax group will default from the vendor account.</span></span>  
    * <span data-ttu-id="94799-120">Le groupe Taxe d'article est par défaut celui du compte principal spécifié dans le champ Compte de contrepartie.</span><span class="sxs-lookup"><span data-stu-id="94799-120">The Item sales tax group will default from the main account specified in the Offset account field.</span></span>  
    * <span data-ttu-id="94799-121">La date d'échéance sera calculée sur la base des conditions de paiement.</span><span class="sxs-lookup"><span data-stu-id="94799-121">The Due date will be calculated based on the Terms of payment.</span></span>  
    * <span data-ttu-id="94799-122">L'escompte de règlement est par défaut celui du compte fournisseur.</span><span class="sxs-lookup"><span data-stu-id="94799-122">The Cash discount will default from the Vendor account.</span></span>  
12. <span data-ttu-id="94799-123">Cliquez sur Valider.</span><span class="sxs-lookup"><span data-stu-id="94799-123">Click Post.</span></span>
13. <span data-ttu-id="94799-124">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="94799-124">Close the page.</span></span>

