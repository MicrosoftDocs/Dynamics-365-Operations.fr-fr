---
title: Créer une entrée de journal à l’aide d’un modèle
description: Les N° document du journal validés peuvent être enregistrés comme Modèles de n° document et être appliqués dans un nouveau N° document de journal.
author: aprilolson
manager: AnnBe
ms.date: 07/01/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerJournalTable, LedgerJournalTransDaily, LedgerJournalTransVoucherTemplate
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 360df29e6349fd4d42d6d14af646e929b73943bd
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4443246"
---
# <a name="create-a-journal-entry-using-template"></a><span data-ttu-id="fb430-103">Créer une entrée de journal à l’aide d’un modèle</span><span class="sxs-lookup"><span data-stu-id="fb430-103">Create a journal entry using template</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="fb430-104">Les N° document du journal validés peuvent être enregistrés comme Modèles de n° document et être appliqués dans un nouveau N° document de journal.</span><span class="sxs-lookup"><span data-stu-id="fb430-104">Posted journal vouchers can be saved as Voucher templates and applied in a new journal voucher.</span></span> <span data-ttu-id="fb430-105">La société fictive USMF sert d’exemple dans cette procédure.</span><span class="sxs-lookup"><span data-stu-id="fb430-105">This procedure uses the USMF demo company.</span></span>

1. <span data-ttu-id="fb430-106">Allez dans le **Volet de navigation > Modules > Comptabilité > Entrées de journal > Journaux des opérations diverses**.</span><span class="sxs-lookup"><span data-stu-id="fb430-106">Go to **Navigation pane > Modules > General ledger > Journal entries > General journals**.</span></span>
2. <span data-ttu-id="fb430-107">Dans le **volet Actions**, cliquez sur **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="fb430-107">On the **Action pane**, click **New**.</span></span> <span data-ttu-id="fb430-108">Cette procédure commence par la création et la validation d’un N° document de journal, mais n’importe quel N° document de journal validé précédemment peut être enregistré comme modèle.</span><span class="sxs-lookup"><span data-stu-id="fb430-108">This procedure starts by creating and posting a journal voucher, but any previously posted journal voucher can be saved as a template.</span></span>  
3. <span data-ttu-id="fb430-109">Dans le champ **Nom**, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="fb430-109">In the **Name** field, click the drop-down button to open the lookup.</span></span>
4. <span data-ttu-id="fb430-110">Dans la liste, recherchez et sélectionnez l’enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="fb430-110">In the list, find and select the desired record.</span></span>
5. <span data-ttu-id="fb430-111">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="fb430-111">In the list, click the link in the selected row.</span></span>
6. <span data-ttu-id="fb430-112">Cliquez sur **Lignes**.</span><span class="sxs-lookup"><span data-stu-id="fb430-112">Click **Lines**.</span></span>
7. <span data-ttu-id="fb430-113">Dans le champ **Type de compte**, tapez une valeur.</span><span class="sxs-lookup"><span data-stu-id="fb430-113">In the **Account type** field, type a value.</span></span>
8. <span data-ttu-id="fb430-114">Tapez une valeur dans le champ **Description**.</span><span class="sxs-lookup"><span data-stu-id="fb430-114">In the **Description** field, type a value.</span></span>
9. <span data-ttu-id="fb430-115">Dans le champ **Débit**, tapez une valeur.</span><span class="sxs-lookup"><span data-stu-id="fb430-115">In the **Debit** field, type a value.</span></span>
10. <span data-ttu-id="fb430-116">Cliquez sur **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="fb430-116">Click **New**.</span></span>
11. <span data-ttu-id="fb430-117">Dans le champ **Type de compte**, tapez une valeur.</span><span class="sxs-lookup"><span data-stu-id="fb430-117">In the **Account type** field, type a value.</span></span>
12. <span data-ttu-id="fb430-118">Tapez une valeur dans le champ **Description**.</span><span class="sxs-lookup"><span data-stu-id="fb430-118">In the **Description** field, type a value.</span></span>
13. <span data-ttu-id="fb430-119">Dans le champ **Débit**, tapez une valeur.</span><span class="sxs-lookup"><span data-stu-id="fb430-119">In the **Debit** field, type a value.</span></span>
14. <span data-ttu-id="fb430-120">Cliquez sur **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="fb430-120">Click **New**.</span></span>
14. <span data-ttu-id="fb430-121">Dans le champ **Compte**, spécifiez les valeurs souhaitées.</span><span class="sxs-lookup"><span data-stu-id="fb430-121">In the **Account** field, specify the desired values.</span></span>
15. <span data-ttu-id="fb430-122">Tapez une valeur dans le champ **Description**.</span><span class="sxs-lookup"><span data-stu-id="fb430-122">In the **Description** field, type a value.</span></span>
16. <span data-ttu-id="fb430-123">Dans le champ **Crédit**, tapez une valeur pour solder le document.</span><span class="sxs-lookup"><span data-stu-id="fb430-123">In the **Credit** field, type a value to balance the voucher.</span></span>
17. <span data-ttu-id="fb430-124">Dans le volet **Actions**, cliquez sur **Valider**.</span><span class="sxs-lookup"><span data-stu-id="fb430-124">On the **Action pane**, click **Post**.</span></span>
18. <span data-ttu-id="fb430-125">Cliquez sur **Fonctions**.</span><span class="sxs-lookup"><span data-stu-id="fb430-125">Click **Functions**.</span></span>
19. <span data-ttu-id="fb430-126">Cliquez sur **Enregistrer le modèle de n° document**.</span><span class="sxs-lookup"><span data-stu-id="fb430-126">Click **Save voucher** template.</span></span>
20. <span data-ttu-id="fb430-127">Cette procédure suppose un type de **modèle de pourcentage**.</span><span class="sxs-lookup"><span data-stu-id="fb430-127">This procedure assumes a **Percent Template** type.</span></span> <span data-ttu-id="fb430-128">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="fb430-128">Click OK.</span></span>
    - <span data-ttu-id="fb430-129">Pourcentage : Les montants du document sont convertis en facteurs de pourcentage, ce qui permet d’appliquer n’importe quel montant lorsque le modèle de document est sélectionné.</span><span class="sxs-lookup"><span data-stu-id="fb430-129">Percent: The amounts in the voucher are converted into percentage factors, which allows any amount to be applied when the Voucher template is selected.</span></span>
    - <span data-ttu-id="fb430-130">Montant : Les montants effectifs sont enregistrés et appliqués.</span><span class="sxs-lookup"><span data-stu-id="fb430-130">Amount: The actual amounts will be stored and applied.</span></span>  
21. <span data-ttu-id="fb430-131">Cliquez sur **Journaux des opérations diverses**.</span><span class="sxs-lookup"><span data-stu-id="fb430-131">Click **General journals**.</span></span>
22. <span data-ttu-id="fb430-132">Cliquez sur **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="fb430-132">Click **New**.</span></span>
23. <span data-ttu-id="fb430-133">Dans le champ **Nom**, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="fb430-133">In the **Name** field, click the drop-down button to open the lookup.</span></span>
24. <span data-ttu-id="fb430-134">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="fb430-134">In the list, click the link in the selected row.</span></span>
25. <span data-ttu-id="fb430-135">Cliquez sur **Lignes**.</span><span class="sxs-lookup"><span data-stu-id="fb430-135">Click **Lines**.</span></span>
26. <span data-ttu-id="fb430-136">Cliquez sur **Fonctions**.</span><span class="sxs-lookup"><span data-stu-id="fb430-136">Click **Functions**.</span></span>
27. <span data-ttu-id="fb430-137">Cliquez sur **Sélectionner le modèle de n° document**.</span><span class="sxs-lookup"><span data-stu-id="fb430-137">Click **Select voucher template**.</span></span>
28. <span data-ttu-id="fb430-138">Recherchez le modèle créé précédemment.</span><span class="sxs-lookup"><span data-stu-id="fb430-138">Find the template that you created earlier.</span></span> <span data-ttu-id="fb430-139">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="fb430-139">Click **OK**.</span></span> <span data-ttu-id="fb430-140">Vous devrez peut-être cliquer sur **Étape précédente**, puis sélectionner le modèle correct si d’autres modèles existent.</span><span class="sxs-lookup"><span data-stu-id="fb430-140">You may need to click **Previous step** and then select the correct template if other templates exist.</span></span>  
29. <span data-ttu-id="fb430-141">Dans le champ **Montant**, entrez le montant à appliquer au document.</span><span class="sxs-lookup"><span data-stu-id="fb430-141">In the **Amount** field, enter the amount to be applied to the voucher.</span></span> <span data-ttu-id="fb430-142">Le champ **Montant** est affiché uniquement si le type du modèle de n° document est Pourcentage.</span><span class="sxs-lookup"><span data-stu-id="fb430-142">The **Amount** field is only displayed if the voucher template is of type Percent.</span></span>  
30. <span data-ttu-id="fb430-143">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="fb430-143">Click **OK**.</span></span>

