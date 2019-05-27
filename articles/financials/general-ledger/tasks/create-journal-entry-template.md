---
title: Créer une entrée de journal à l'aide d'un modèle
description: Les N° document du journal validés peuvent être enregistrés comme Modèles de n° document et être appliqués dans un nouveau N° document de journal.
author: aprilolson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerJournalTable, LedgerJournalTransDaily, LedgerJournalTransVoucherTemplate
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 4a749740b62e39202d502a112f947679f85ca085
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/15/2019
ms.locfileid: "1562497"
---
# <a name="create-a-journal-entry-using-template"></a><span data-ttu-id="2f831-103">Créer une entrée de journal à l'aide d'un modèle</span><span class="sxs-lookup"><span data-stu-id="2f831-103">Create a journal entry using template</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="2f831-104">Les N° document du journal validés peuvent être enregistrés comme Modèles de n° document et être appliqués dans un nouveau N° document de journal.</span><span class="sxs-lookup"><span data-stu-id="2f831-104">Posted journal vouchers can be saved as Voucher templates and applied in a new journal voucher.</span></span> <span data-ttu-id="2f831-105">La société fictive USMF sert d'exemple dans cette procédure.</span><span class="sxs-lookup"><span data-stu-id="2f831-105">This procedure uses the USMF demo company.</span></span>

1. <span data-ttu-id="2f831-106">Comptabilité > Entrées de journal > Journaux des opérations diverses.</span><span class="sxs-lookup"><span data-stu-id="2f831-106">General ledger > Journal entries > General journals.</span></span> <span data-ttu-id="2f831-107">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="2f831-107">Click New.</span></span>
    * <span data-ttu-id="2f831-108">Cette procédure commence par la création et la validation d'un N° document de journal, mais n'importe quel N° document de journal validé précédemment peut être enregistré comme modèle.</span><span class="sxs-lookup"><span data-stu-id="2f831-108">This procedure starts by creating and posting a journal voucher, but any previously posted journal voucher can be saved as a template.</span></span>  
2. <span data-ttu-id="2f831-109">Dans le champ Nom, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="2f831-109">In the Name field, click the drop-down button to open the lookup.</span></span>
3. <span data-ttu-id="2f831-110">Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="2f831-110">In the list, find and select the desired record.</span></span>
4. <span data-ttu-id="2f831-111">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="2f831-111">In the list, click the link in the selected row.</span></span>
5. <span data-ttu-id="2f831-112">Cliquez sur Lignes.</span><span class="sxs-lookup"><span data-stu-id="2f831-112">Click Lines.</span></span>
6. <span data-ttu-id="2f831-113">Entrez un compte pour le type Compte.</span><span class="sxs-lookup"><span data-stu-id="2f831-113">Enter an account for the Account type.</span></span>
7. <span data-ttu-id="2f831-114">Dans le champ Description, entrez une valeur.</span><span class="sxs-lookup"><span data-stu-id="2f831-114">In the Description field, type a value.</span></span>
8. <span data-ttu-id="2f831-115">Entrez le montant dans le champ Débit.</span><span class="sxs-lookup"><span data-stu-id="2f831-115">Enter an amount in the Debit field.</span></span>
9. <span data-ttu-id="2f831-116">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="2f831-116">Click New.</span></span>
10. <span data-ttu-id="2f831-117">Entrez un compte différente pour le type Compte.</span><span class="sxs-lookup"><span data-stu-id="2f831-117">Enter a different account for the Account type.</span></span>
11. <span data-ttu-id="2f831-118">Dans le champ Description, entrez une valeur.</span><span class="sxs-lookup"><span data-stu-id="2f831-118">In the Description field, type a value.</span></span>
12. <span data-ttu-id="2f831-119">Entrez le montant dans le champ Débit.</span><span class="sxs-lookup"><span data-stu-id="2f831-119">Enter an amount in the Debit field.</span></span>
13. <span data-ttu-id="2f831-120">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="2f831-120">Click New.</span></span>
14. <span data-ttu-id="2f831-121">Dans le champ Compte, spécifiez les valeurs souhaitées.</span><span class="sxs-lookup"><span data-stu-id="2f831-121">In the Account field, specify the desired values.</span></span>
15. <span data-ttu-id="2f831-122">Tapez une valeur dans le champ Description.</span><span class="sxs-lookup"><span data-stu-id="2f831-122">In the Description field, type a value.</span></span>
16. <span data-ttu-id="2f831-123">Entrez un montant dans le champ Crédit pour solder le document.</span><span class="sxs-lookup"><span data-stu-id="2f831-123">Enter an amount in the Credit field to balance the voucher.</span></span>
17. <span data-ttu-id="2f831-124">Cliquez sur Valider.</span><span class="sxs-lookup"><span data-stu-id="2f831-124">Click Post.</span></span>
18. <span data-ttu-id="2f831-125">Cliquez sur Fonctions.</span><span class="sxs-lookup"><span data-stu-id="2f831-125">Click Functions.</span></span>
19. <span data-ttu-id="2f831-126">Cliquez sur Enregistrer le modèle de n° document.</span><span class="sxs-lookup"><span data-stu-id="2f831-126">Click Save voucher template.</span></span>
20. <span data-ttu-id="2f831-127">Cette procédure suppose un type de modèle de pourcentage.</span><span class="sxs-lookup"><span data-stu-id="2f831-127">This procedure assumes a Percent Template type.</span></span> <span data-ttu-id="2f831-128">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="2f831-128">Click OK.</span></span>
    * <span data-ttu-id="2f831-129">• Pourcentage : Les montants du document sont convertis en facteurs de pourcentage, ce qui permet d'appliquer n'importe quel montant lorsque le modèle de document est sélectionné.</span><span class="sxs-lookup"><span data-stu-id="2f831-129">• Percent: The amounts in the voucher are converted into percentage factors, which allows any amount to be applied when the Voucher template is selected.</span></span>  <span data-ttu-id="2f831-130">• Montant : Les montants effectifs sont enregistrés et appliqués.</span><span class="sxs-lookup"><span data-stu-id="2f831-130">• Amount: The actual amounts will be stored and applied.</span></span>  
21. <span data-ttu-id="2f831-131">Cliquez sur Journaux des opérations diverses.</span><span class="sxs-lookup"><span data-stu-id="2f831-131">Click General journals.</span></span>
22. <span data-ttu-id="2f831-132">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="2f831-132">Click New.</span></span>
23. <span data-ttu-id="2f831-133">Dans le champ Nom, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="2f831-133">In the Name field, click the drop-down button to open the lookup.</span></span>
24. <span data-ttu-id="2f831-134">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="2f831-134">In the list, click the link in the selected row.</span></span>
25. <span data-ttu-id="2f831-135">Cliquez sur Lignes.</span><span class="sxs-lookup"><span data-stu-id="2f831-135">Click Lines.</span></span>
26. <span data-ttu-id="2f831-136">Cliquez sur Fonctions.</span><span class="sxs-lookup"><span data-stu-id="2f831-136">Click Functions.</span></span>
27. <span data-ttu-id="2f831-137">Cliquez sur Sélectionner le modèle de n° document.</span><span class="sxs-lookup"><span data-stu-id="2f831-137">Click Select voucher template.</span></span>
28. <span data-ttu-id="2f831-138">Recherchez le modèle créé précédemment.</span><span class="sxs-lookup"><span data-stu-id="2f831-138">Find the template that you created earlier.</span></span> <span data-ttu-id="2f831-139">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="2f831-139">Click OK.</span></span>
    * <span data-ttu-id="2f831-140">Vous devrez peut-être cliquer sur Étape précédente, puis sélectionner le modèle correct si d'autres modèles existent.</span><span class="sxs-lookup"><span data-stu-id="2f831-140">You may need to click Previous step and then select the correct template if other templates exist.</span></span>  
29. <span data-ttu-id="2f831-141">Dans le champ Montant, entrez le montant à appliquer au document.</span><span class="sxs-lookup"><span data-stu-id="2f831-141">In the Amount field, enter the amount to be applied to the voucher.</span></span>
    * <span data-ttu-id="2f831-142">Le champ Montant est affiché uniquement si le type du modèle de n° document est Pourcentage.</span><span class="sxs-lookup"><span data-stu-id="2f831-142">The amount field is only displayed if the voucher template is of type Percent.</span></span>  
30. <span data-ttu-id="2f831-143">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="2f831-143">Click OK.</span></span>

