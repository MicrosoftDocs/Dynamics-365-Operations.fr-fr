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
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 1a3fb750e04fb134fc9ac38d9a47201803566113
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/01/2019
ms.locfileid: "1846629"
---
# <a name="create-a-journal-entry-using-template"></a><span data-ttu-id="f5a62-103">Créer une entrée de journal à l'aide d'un modèle</span><span class="sxs-lookup"><span data-stu-id="f5a62-103">Create a journal entry using template</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="f5a62-104">Les N° document du journal validés peuvent être enregistrés comme Modèles de n° document et être appliqués dans un nouveau N° document de journal.</span><span class="sxs-lookup"><span data-stu-id="f5a62-104">Posted journal vouchers can be saved as Voucher templates and applied in a new journal voucher.</span></span> <span data-ttu-id="f5a62-105">La société fictive USMF sert d'exemple dans cette procédure.</span><span class="sxs-lookup"><span data-stu-id="f5a62-105">This procedure uses the USMF demo company.</span></span>

1. <span data-ttu-id="f5a62-106">Comptabilité > Entrées de journal > Journaux des opérations diverses.</span><span class="sxs-lookup"><span data-stu-id="f5a62-106">General ledger > Journal entries > General journals.</span></span> <span data-ttu-id="f5a62-107">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="f5a62-107">Click New.</span></span>
    * <span data-ttu-id="f5a62-108">Cette procédure commence par la création et la validation d'un N° document de journal, mais n'importe quel N° document de journal validé précédemment peut être enregistré comme modèle.</span><span class="sxs-lookup"><span data-stu-id="f5a62-108">This procedure starts by creating and posting a journal voucher, but any previously posted journal voucher can be saved as a template.</span></span>  
2. <span data-ttu-id="f5a62-109">Dans le champ Nom, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="f5a62-109">In the Name field, click the drop-down button to open the lookup.</span></span>
3. <span data-ttu-id="f5a62-110">Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="f5a62-110">In the list, find and select the desired record.</span></span>
4. <span data-ttu-id="f5a62-111">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="f5a62-111">In the list, click the link in the selected row.</span></span>
5. <span data-ttu-id="f5a62-112">Cliquez sur Lignes.</span><span class="sxs-lookup"><span data-stu-id="f5a62-112">Click Lines.</span></span>
6. <span data-ttu-id="f5a62-113">Entrez un compte pour le type Compte.</span><span class="sxs-lookup"><span data-stu-id="f5a62-113">Enter an account for the Account type.</span></span>
7. <span data-ttu-id="f5a62-114">Dans le champ Description, entrez une valeur.</span><span class="sxs-lookup"><span data-stu-id="f5a62-114">In the Description field, type a value.</span></span>
8. <span data-ttu-id="f5a62-115">Entrez le montant dans le champ Débit.</span><span class="sxs-lookup"><span data-stu-id="f5a62-115">Enter an amount in the Debit field.</span></span>
9. <span data-ttu-id="f5a62-116">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="f5a62-116">Click New.</span></span>
10. <span data-ttu-id="f5a62-117">Entrez un compte différente pour le type Compte.</span><span class="sxs-lookup"><span data-stu-id="f5a62-117">Enter a different account for the Account type.</span></span>
11. <span data-ttu-id="f5a62-118">Dans le champ Description, entrez une valeur.</span><span class="sxs-lookup"><span data-stu-id="f5a62-118">In the Description field, type a value.</span></span>
12. <span data-ttu-id="f5a62-119">Entrez le montant dans le champ Débit.</span><span class="sxs-lookup"><span data-stu-id="f5a62-119">Enter an amount in the Debit field.</span></span>
13. <span data-ttu-id="f5a62-120">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="f5a62-120">Click New.</span></span>
14. <span data-ttu-id="f5a62-121">Dans le champ Compte, spécifiez les valeurs souhaitées.</span><span class="sxs-lookup"><span data-stu-id="f5a62-121">In the Account field, specify the desired values.</span></span>
15. <span data-ttu-id="f5a62-122">Tapez une valeur dans le champ Description.</span><span class="sxs-lookup"><span data-stu-id="f5a62-122">In the Description field, type a value.</span></span>
16. <span data-ttu-id="f5a62-123">Entrez un montant dans le champ Crédit pour solder le document.</span><span class="sxs-lookup"><span data-stu-id="f5a62-123">Enter an amount in the Credit field to balance the voucher.</span></span>
17. <span data-ttu-id="f5a62-124">Cliquez sur Valider.</span><span class="sxs-lookup"><span data-stu-id="f5a62-124">Click Post.</span></span>
18. <span data-ttu-id="f5a62-125">Cliquez sur Fonctions.</span><span class="sxs-lookup"><span data-stu-id="f5a62-125">Click Functions.</span></span>
19. <span data-ttu-id="f5a62-126">Cliquez sur Enregistrer le modèle de n° document.</span><span class="sxs-lookup"><span data-stu-id="f5a62-126">Click Save voucher template.</span></span>
20. <span data-ttu-id="f5a62-127">Cette procédure suppose un type de modèle de pourcentage.</span><span class="sxs-lookup"><span data-stu-id="f5a62-127">This procedure assumes a Percent Template type.</span></span> <span data-ttu-id="f5a62-128">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="f5a62-128">Click OK.</span></span>
    * <span data-ttu-id="f5a62-129">• Pourcentage : Les montants du document sont convertis en facteurs de pourcentage, ce qui permet d'appliquer n'importe quel montant lorsque le modèle de document est sélectionné.</span><span class="sxs-lookup"><span data-stu-id="f5a62-129">• Percent: The amounts in the voucher are converted into percentage factors, which allows any amount to be applied when the Voucher template is selected.</span></span>  <span data-ttu-id="f5a62-130">• Montant : Les montants effectifs sont enregistrés et appliqués.</span><span class="sxs-lookup"><span data-stu-id="f5a62-130">• Amount: The actual amounts will be stored and applied.</span></span>  
21. <span data-ttu-id="f5a62-131">Cliquez sur Journaux des opérations diverses.</span><span class="sxs-lookup"><span data-stu-id="f5a62-131">Click General journals.</span></span>
22. <span data-ttu-id="f5a62-132">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="f5a62-132">Click New.</span></span>
23. <span data-ttu-id="f5a62-133">Dans le champ Nom, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="f5a62-133">In the Name field, click the drop-down button to open the lookup.</span></span>
24. <span data-ttu-id="f5a62-134">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="f5a62-134">In the list, click the link in the selected row.</span></span>
25. <span data-ttu-id="f5a62-135">Cliquez sur Lignes.</span><span class="sxs-lookup"><span data-stu-id="f5a62-135">Click Lines.</span></span>
26. <span data-ttu-id="f5a62-136">Cliquez sur Fonctions.</span><span class="sxs-lookup"><span data-stu-id="f5a62-136">Click Functions.</span></span>
27. <span data-ttu-id="f5a62-137">Cliquez sur Sélectionner le modèle de n° document.</span><span class="sxs-lookup"><span data-stu-id="f5a62-137">Click Select voucher template.</span></span>
28. <span data-ttu-id="f5a62-138">Recherchez le modèle créé précédemment.</span><span class="sxs-lookup"><span data-stu-id="f5a62-138">Find the template that you created earlier.</span></span> <span data-ttu-id="f5a62-139">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="f5a62-139">Click OK.</span></span>
    * <span data-ttu-id="f5a62-140">Vous devrez peut-être cliquer sur Étape précédente, puis sélectionner le modèle correct si d'autres modèles existent.</span><span class="sxs-lookup"><span data-stu-id="f5a62-140">You may need to click Previous step and then select the correct template if other templates exist.</span></span>  
29. <span data-ttu-id="f5a62-141">Dans le champ Montant, entrez le montant à appliquer au document.</span><span class="sxs-lookup"><span data-stu-id="f5a62-141">In the Amount field, enter the amount to be applied to the voucher.</span></span>
    * <span data-ttu-id="f5a62-142">Le champ Montant est affiché uniquement si le type du modèle de n° document est Pourcentage.</span><span class="sxs-lookup"><span data-stu-id="f5a62-142">The amount field is only displayed if the voucher template is of type Percent.</span></span>  
30. <span data-ttu-id="f5a62-143">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="f5a62-143">Click OK.</span></span>

