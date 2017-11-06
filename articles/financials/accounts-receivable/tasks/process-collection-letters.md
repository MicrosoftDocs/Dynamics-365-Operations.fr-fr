--- 
title: Traiter les lettres de relance
description: "Cette procédure indique comment créer, imprimer, et valider les lettres de relance."
author: ShivamPandey-msft
manager: AnnBe
ms.date: 10/23/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Operations
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: dc837ea6513992a5f94e48baa366e279df297866
ms.contentlocale: fr-fr
ms.lasthandoff: 11/06/2017

---
# <a name="process-collection-letters"></a><span data-ttu-id="086e0-103">Traiter les lettres de relance</span><span class="sxs-lookup"><span data-stu-id="086e0-103">Process collection letters</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="086e0-104">Cette procédure indique comment créer, imprimer, et valider les lettres de relance.</span><span class="sxs-lookup"><span data-stu-id="086e0-104">This procedure shows how to create, print, and post collection letters.</span></span> <span data-ttu-id="086e0-105">La société fictive USMF est citée en exemple dans cette tâche.</span><span class="sxs-lookup"><span data-stu-id="086e0-105">This task uses the USMF demo company.</span></span>


## <a name="set-up-a-collection-letter-sequence-on-the-posting-profile"></a><span data-ttu-id="086e0-106">Configuration d'une séquence de lettres de relance sur le profil de validation</span><span class="sxs-lookup"><span data-stu-id="086e0-106">Set up a collection letter sequence on the posting profile</span></span>
1. <span data-ttu-id="086e0-107">Accédez à Crédit et relances > Paramétrage > Profils de validation client.</span><span class="sxs-lookup"><span data-stu-id="086e0-107">Go to Credit and collections > Setup > Customer posting profiles.</span></span>
2. <span data-ttu-id="086e0-108">Cliquez sur Modifier.</span><span class="sxs-lookup"><span data-stu-id="086e0-108">Click Edit.</span></span>
    * <span data-ttu-id="086e0-109">Sélectionnez une séquence de lettres de relance dans la liste déroulante.</span><span class="sxs-lookup"><span data-stu-id="086e0-109">Select a collection letter sequence from the drop-down list.</span></span> <span data-ttu-id="086e0-110">Si vous ne souhaitez pas générer de lettres de relance pour les transactions utilisant ce profil de validation, laissez le champ vide.</span><span class="sxs-lookup"><span data-stu-id="086e0-110">If you do not want generate collection letters for transactions using this posting profile, leave the field blank.</span></span>  
    * <span data-ttu-id="086e0-111">L'onglet Restrictions de table vous permet de modifier la manière dont les lettres de relance sont traitées.</span><span class="sxs-lookup"><span data-stu-id="086e0-111">The table restriction tab allows you to change the way that collection letters are processed.</span></span> <span data-ttu-id="086e0-112">Si ce champ est défini sur Oui, les lettres de relance sont créées pour ce profil de validation.</span><span class="sxs-lookup"><span data-stu-id="086e0-112">If this field is set to Yes, then collection letters will be created for this posting profile.</span></span>  
3. <span data-ttu-id="086e0-113">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="086e0-113">Close the page.</span></span>

## <a name="create-collection-letters"></a><span data-ttu-id="086e0-114">Créer des lettres de relance</span><span class="sxs-lookup"><span data-stu-id="086e0-114">Create collection letters</span></span>
1. <span data-ttu-id="086e0-115">Accédez à Crédit et relances > Lettre de relance > Créer des lettres de relance.</span><span class="sxs-lookup"><span data-stu-id="086e0-115">Go to Credit and collections > Collection letter > Create collection letters.</span></span>
    * <span data-ttu-id="086e0-116">Vous devez sélectionner les types de transaction pour lesquels vous allez recueillir des lettres.</span><span class="sxs-lookup"><span data-stu-id="086e0-116">You must select the transaction types for which you will collect letters.</span></span> <span data-ttu-id="086e0-117">Toutes les transactions en cours pour ces types sont incluses dans le calcul de ces montants.</span><span class="sxs-lookup"><span data-stu-id="086e0-117">All of the open transactions for these types will be included in the calculation.</span></span>  
2. <span data-ttu-id="086e0-118">Dans le champ Lettre de relance, sélectionnez une option.</span><span class="sxs-lookup"><span data-stu-id="086e0-118">In the Collection letter field, select an option.</span></span>
3. <span data-ttu-id="086e0-119">Spécifiez la date de la lettre de relance.</span><span class="sxs-lookup"><span data-stu-id="086e0-119">Enter the date of the collection letter.</span></span>
    * <span data-ttu-id="086e0-120">Il existe deux options de profil de validation : Compte : utilisez le profil de validation affecté au compte client pour chaque note d'intérêt.</span><span class="sxs-lookup"><span data-stu-id="086e0-120">There are two posting profile options:   Account – Use the posting profile that is assigned to the customer account for each interest note.</span></span>   <span data-ttu-id="086e0-121">Sélectionner : Utilisez le profil de validation sélectionné dans le champ Profil de validation.</span><span class="sxs-lookup"><span data-stu-id="086e0-121">Select – Use the posting profile that you select in the Posting profile field.</span></span>  
    * <span data-ttu-id="086e0-122">Sélectionnez un profil de validation si vous avez remplacé « Origine du profil de validation » par « Sélectionner ».</span><span class="sxs-lookup"><span data-stu-id="086e0-122">Select a posting profile if you changed "Use posting profile from" to "Select".</span></span>  
4. <span data-ttu-id="086e0-123">Développez les enregistrements pour inclure la section.</span><span class="sxs-lookup"><span data-stu-id="086e0-123">Expand the Records to include section.</span></span>
5. <span data-ttu-id="086e0-124">Cliquez sur Filtre.</span><span class="sxs-lookup"><span data-stu-id="086e0-124">Click Filter.</span></span>
6. <span data-ttu-id="086e0-125">Dans le champ Critères, entrez un ID client.</span><span class="sxs-lookup"><span data-stu-id="086e0-125">In the Criteria field, In the Criteria field, enter a Customer ID.</span></span> <span data-ttu-id="086e0-126">Par exemple, entrez US-001.</span><span class="sxs-lookup"><span data-stu-id="086e0-126">For example, enter 'US-001'..</span></span>
7. <span data-ttu-id="086e0-127">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="086e0-127">Click OK.</span></span>
8. <span data-ttu-id="086e0-128">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="086e0-128">Click OK.</span></span>

## <a name="print-collection-letters"></a><span data-ttu-id="086e0-129">Imprimer/valider des lettres de relance</span><span class="sxs-lookup"><span data-stu-id="086e0-129">Print collection letters</span></span>
1. <span data-ttu-id="086e0-130">Accédez à Crédit et relances > Lettre de relance > Examiner et traiter les lettres de relance.</span><span class="sxs-lookup"><span data-stu-id="086e0-130">Go to Credit and collections > Collection letter > Review and process collection letters.</span></span>
2. <span data-ttu-id="086e0-131">Sélectionnez Créé dans le champ Statut.</span><span class="sxs-lookup"><span data-stu-id="086e0-131">In the Status field, select 'Created'.</span></span>
3. <span data-ttu-id="086e0-132">Dans le champ Imprimé, sélectionnez « Non imprimé ».</span><span class="sxs-lookup"><span data-stu-id="086e0-132">In the Printed field, select 'Not printed'.</span></span>
4. <span data-ttu-id="086e0-133">Cliquez sur Imprimer.</span><span class="sxs-lookup"><span data-stu-id="086e0-133">Click Print.</span></span>
5. <span data-ttu-id="086e0-134">Cliquez sur Note de lettre de relance.</span><span class="sxs-lookup"><span data-stu-id="086e0-134">Click Collection letter note.</span></span>
6. <span data-ttu-id="086e0-135">Développez les enregistrements pour inclure la section.</span><span class="sxs-lookup"><span data-stu-id="086e0-135">Expand the Records to include section.</span></span>
7. <span data-ttu-id="086e0-136">Spécifiez la date limite pour les validations.</span><span class="sxs-lookup"><span data-stu-id="086e0-136">Enter the cutoff date for postings</span></span>
8. <span data-ttu-id="086e0-137">Cliquez sur OK pour imprimer la lettre de relance.</span><span class="sxs-lookup"><span data-stu-id="086e0-137">Click OK to print the collection letter.</span></span>

## <a name="post-the-collection-letter"></a><span data-ttu-id="086e0-138">Valider la lettre de relance</span><span class="sxs-lookup"><span data-stu-id="086e0-138">Post the collection letter</span></span>
1. <span data-ttu-id="086e0-139">Cliquez sur Valider.</span><span class="sxs-lookup"><span data-stu-id="086e0-139">Click Post.</span></span>
2. <span data-ttu-id="086e0-140">Entrer la date de validation pour la lettre de relance.</span><span class="sxs-lookup"><span data-stu-id="086e0-140">Enter the posting date for the collection letter.</span></span>
3. <span data-ttu-id="086e0-141">Développez les enregistrements pour inclure la section.</span><span class="sxs-lookup"><span data-stu-id="086e0-141">Expand the Records to include section.</span></span>
4. <span data-ttu-id="086e0-142">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="086e0-142">Click OK.</span></span>
5. <span data-ttu-id="086e0-143">Sélectionnez Validé dans le champ Statut.</span><span class="sxs-lookup"><span data-stu-id="086e0-143">In the Status field, select 'Posted'.</span></span>
6. <span data-ttu-id="086e0-144">Dans le champ Imprimé, sélectionnez une option.</span><span class="sxs-lookup"><span data-stu-id="086e0-144">In the Printed field, select an option.</span></span>


