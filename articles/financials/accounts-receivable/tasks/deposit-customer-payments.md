--- 
title: "Déposer les paiements client"
description: "Déposez des paiements client."
author: ShivamPandey-msft
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: LedgerJournalTable, LedgerJournalTransCustPaym, CustTableLookup
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 0312b8cfadd45f8e59225e9daba78b9e216cff51
ms.openlocfilehash: f58cebce20e8516dc918e0bad1e020ffd7f791ee
ms.contentlocale: fr-fr
ms.lasthandoff: 09/14/2018

---
# <a name="deposit-customer-payments"></a><span data-ttu-id="949d1-103">Déposer les paiements client</span><span class="sxs-lookup"><span data-stu-id="949d1-103">Deposit customer payments</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="949d1-104">Déposez des paiements client.</span><span class="sxs-lookup"><span data-stu-id="949d1-104">Deposit customer payments.</span></span> <span data-ttu-id="949d1-105">La société fictive USMF est citée en exemple dans cette tâche.</span><span class="sxs-lookup"><span data-stu-id="949d1-105">This task uses the USMF demo company.</span></span>

1. <span data-ttu-id="949d1-106">Accédez à Comptabilité client > Paiements > Journal des paiements.</span><span class="sxs-lookup"><span data-stu-id="949d1-106">Go to Accounts receivable > Payments > Payment journal.</span></span>
2. <span data-ttu-id="949d1-107">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="949d1-107">Click New.</span></span>
3. <span data-ttu-id="949d1-108">Dans le champ Nom, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="949d1-108">In the Name field, click the drop-down button to open the lookup.</span></span>
4. <span data-ttu-id="949d1-109">Sélectionnez le journal de paiement.</span><span class="sxs-lookup"><span data-stu-id="949d1-109">Select the payment journal.</span></span> 
5. <span data-ttu-id="949d1-110">Cliquez sur Lignes.</span><span class="sxs-lookup"><span data-stu-id="949d1-110">Click Lines.</span></span>
6. <span data-ttu-id="949d1-111">Dans le champ Compte, sélectionnez le client pour lequel vous enregistrez le paiement.</span><span class="sxs-lookup"><span data-stu-id="949d1-111">In the Account field, select the Customer for whom you are recording the payment.</span></span>
7. <span data-ttu-id="949d1-112">Dans le champ Crédit, entrez le montant du paiement.</span><span class="sxs-lookup"><span data-stu-id="949d1-112">In the Credit field, enter the amount of the payment.</span></span>
    * <span data-ttu-id="949d1-113">Vous pouvez choisir de laisser le montant de ce champ vide, et laisser le système le calculer en sélectionnant les factures qui ont été payées.</span><span class="sxs-lookup"><span data-stu-id="949d1-113">You can choose to leave the amount blank, and have the system calculate it by selecting the invoices which were paid.</span></span>  
8. <span data-ttu-id="949d1-114">Tapez une valeur dans le champ Référence de paiement.</span><span class="sxs-lookup"><span data-stu-id="949d1-114">In the Payment reference field, type a value.</span></span>
    * <span data-ttu-id="949d1-115">La référence de paiement peut être le numéro de chèque pour le paiement que vous entrez.</span><span class="sxs-lookup"><span data-stu-id="949d1-115">The payment reference could be the check number for the payment you are entering.</span></span> <span data-ttu-id="949d1-116">La référence de paiement est requise pour inclure le paiement sur un bordereau de remise.</span><span class="sxs-lookup"><span data-stu-id="949d1-116">The payment reference is required in order to include the payment on a deposit slip.</span></span>  
9. <span data-ttu-id="949d1-117">Cochez la case Utiliser un bordereau de remise.</span><span class="sxs-lookup"><span data-stu-id="949d1-117">Mark the box Use a deposit slip.</span></span>
    * <span data-ttu-id="949d1-118">Si le paiement doit être inclus dans le dépôt, définissez ce paramètre sur Oui.</span><span class="sxs-lookup"><span data-stu-id="949d1-118">If the payment should be included in the deposit, change this setting to Yes.</span></span>  
10. <span data-ttu-id="949d1-119">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="949d1-119">Click New.</span></span>
11. <span data-ttu-id="949d1-120">Dans le champ Compte, sélectionnez le client pour le paiement suivant.</span><span class="sxs-lookup"><span data-stu-id="949d1-120">In the Account field, select the Customer for the next payment.</span></span>
12. <span data-ttu-id="949d1-121">Dans le champ Crédit, entrez le montant du paiement.</span><span class="sxs-lookup"><span data-stu-id="949d1-121">In the Credit field, enter the payment amount.</span></span>
13. <span data-ttu-id="949d1-122">Tapez une valeur dans le champ Référence de paiement.</span><span class="sxs-lookup"><span data-stu-id="949d1-122">In the Payment reference field, type a value.</span></span>
14. <span data-ttu-id="949d1-123">Cochez la case Utiliser un bordereau de remise.</span><span class="sxs-lookup"><span data-stu-id="949d1-123">Mark the box Use a deposit slip.</span></span>
15. <span data-ttu-id="949d1-124">Cliquez sur Valider.</span><span class="sxs-lookup"><span data-stu-id="949d1-124">Click Post.</span></span>
    * <span data-ttu-id="949d1-125">Les paiements doivent être validés avant que le bordereau de remise puisse être généré.</span><span class="sxs-lookup"><span data-stu-id="949d1-125">Payments must be posted before the deposit slip can be generated.</span></span> <span data-ttu-id="949d1-126">Cela permet de garantir que les paiements ne changent pas une fois le bordereau de remise généré.</span><span class="sxs-lookup"><span data-stu-id="949d1-126">This is to ensure that the payments don't change after the deposit slip is generated.</span></span>  
16. <span data-ttu-id="949d1-127">Cliquez sur Fonctions.</span><span class="sxs-lookup"><span data-stu-id="949d1-127">Click Functions.</span></span>
17. <span data-ttu-id="949d1-128">Cliquez sur Bordereau de remise.</span><span class="sxs-lookup"><span data-stu-id="949d1-128">Click Deposit slip.</span></span>
18. <span data-ttu-id="949d1-129">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="949d1-129">Click OK.</span></span>
    * <span data-ttu-id="949d1-130">La première page permet de créer le bordereau de remise.</span><span class="sxs-lookup"><span data-stu-id="949d1-130">The first page is used to create the deposit slip.</span></span>  
19. <span data-ttu-id="949d1-131">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="949d1-131">Click OK.</span></span>
    * <span data-ttu-id="949d1-132">La deuxième étape consiste à imprimer le bordereau de remise, mais cette étape n'est pas nécessaire.</span><span class="sxs-lookup"><span data-stu-id="949d1-132">The second step is to print the deposit slip, but this step is not required.</span></span>  


