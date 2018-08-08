--- 
title: "Traiter les intérêts"
description: "Cette procédure permet d'indiquer comment créer, imprimer, et valider les notes d'intérêt."
author: ShivamPandey-msft
manager: AnnBe
ms.date: 11/10/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Operations
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: d9747ba144d56c9410846769e5465372c89ea111
ms.openlocfilehash: 3264ea08b93f8c9ed7dc2792db2e3878cae188a4
ms.contentlocale: fr-fr
ms.lasthandoff: 08/07/2018

---
# <a name="process-interest"></a><span data-ttu-id="4a116-103">Traiter les intérêts</span><span class="sxs-lookup"><span data-stu-id="4a116-103">Process interest</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="4a116-104">Cette procédure permet d'indiquer comment créer, imprimer, et valider les notes d'intérêt.</span><span class="sxs-lookup"><span data-stu-id="4a116-104">This procedure shows how to create, print, and post interest notes.</span></span> <span data-ttu-id="4a116-105">La société fictive USMF est citée en exemple dans cette tâche.</span><span class="sxs-lookup"><span data-stu-id="4a116-105">This task uses the USMF demo company.</span></span>


## <a name="set-up-interest-on-the-posting-profile"></a><span data-ttu-id="4a116-106">Paramétrer des intérêts dans le profil de validation</span><span class="sxs-lookup"><span data-stu-id="4a116-106">Set up interest on the posting profile</span></span>
1. <span data-ttu-id="4a116-107">Accédez à Crédit et relances > Paramétrage > Profils de validation client.</span><span class="sxs-lookup"><span data-stu-id="4a116-107">Go to Credit and collections > Setup > Customer posting profiles.</span></span>
2. <span data-ttu-id="4a116-108">Cliquez sur Modifier.</span><span class="sxs-lookup"><span data-stu-id="4a116-108">Click Edit.</span></span>
    * <span data-ttu-id="4a116-109">Sélectionnez un code d'intérêt dans la liste déroulante.</span><span class="sxs-lookup"><span data-stu-id="4a116-109">Select an interest code from the drop-down list.</span></span> <span data-ttu-id="4a116-110">Si vous ne souhaitez pas calculer d'intérêts pour les transactions utilisant ce profil de validation, laissez le champ vide.</span><span class="sxs-lookup"><span data-stu-id="4a116-110">If you do not want interest calculated for transactions using this posting profile, leave the field blank.</span></span>  
    * <span data-ttu-id="4a116-111">L'onglet Restrictions de table vous permet de modifier la manière dont les intérêts sont traités.</span><span class="sxs-lookup"><span data-stu-id="4a116-111">The Table restriction tab allows you to change the way that interest is processed.</span></span> <span data-ttu-id="4a116-112">Si ce champ est défini sur Oui, les intérêts sont calculés pour ce profil de validation.</span><span class="sxs-lookup"><span data-stu-id="4a116-112">If this field is set to Yes, then interest will be calculated for this posting profile.</span></span>  

## <a name="calculate-interest"></a><span data-ttu-id="4a116-113">Calculer les intérêts</span><span class="sxs-lookup"><span data-stu-id="4a116-113">Calculate interest</span></span>
1. <span data-ttu-id="4a116-114">Accédez à Crédit et relances > Intérêts > Création de notes d'intérêt.</span><span class="sxs-lookup"><span data-stu-id="4a116-114">Go to Credit and collections > Interest > Create interest notes.</span></span>
    * <span data-ttu-id="4a116-115">Vous devez sélectionner les types de transaction pour lesquels vous voulez calculer les intérêts.</span><span class="sxs-lookup"><span data-stu-id="4a116-115">You must select the transaction types for which you will calculate interest.</span></span> <span data-ttu-id="4a116-116">Toutes les transactions en cours pour ces types sont incluses dans le calcul de ces montants.</span><span class="sxs-lookup"><span data-stu-id="4a116-116">All of the open transactions for these types will be included in the calculation.</span></span>  
    * <span data-ttu-id="4a116-117">Si vous sélectionnez Intérêt, vous calculerez les intérêts sur les intérêts.</span><span class="sxs-lookup"><span data-stu-id="4a116-117">If you select Interest, you will calculate interest on interest.</span></span> <span data-ttu-id="4a116-118">Vous pouvez vérifier les règles régissant le calcul des intérêts sur les intérêts avant de les inclure pour ces transactions.</span><span class="sxs-lookup"><span data-stu-id="4a116-118">You may want to check the laws governing the calculation of interest on interest before including these transactions.</span></span>  
    * <span data-ttu-id="4a116-119">Les intérêts seront calculés à compter de cette date jusqu'à aujourd'hui.</span><span class="sxs-lookup"><span data-stu-id="4a116-119">Interest will be calculated from this date to the "To date".</span></span> <span data-ttu-id="4a116-120">Si vous ne spécifiez pas de « Date de début », alors toutes les notes d'intérêt non validées sont annulées et les intérêts sont recalculés à partir de la date de la transaction.</span><span class="sxs-lookup"><span data-stu-id="4a116-120">If you do not specific a "From date", then all unposted interest notes will be canceled and interest will be recalculated from the transaction date.</span></span>  
2. <span data-ttu-id="4a116-121">Entrez la date de la note d'intérêt.</span><span class="sxs-lookup"><span data-stu-id="4a116-121">Enter the date of the interest note.</span></span>
    * <span data-ttu-id="4a116-122">Il existe trois options de profil de validation : Compte : Utilisez le profil de validation affecté au compte client pour chaque note d'intérêt.</span><span class="sxs-lookup"><span data-stu-id="4a116-122">There are three posting profile options:   Account – Use the posting profile that is assigned to the customer account for each interest note.</span></span>   <span data-ttu-id="4a116-123">Sélectionner : Utilisez le profil de validation sélectionné dans le champ Profil de validation.</span><span class="sxs-lookup"><span data-stu-id="4a116-123">Select – Use the posting profile that you select in the Posting profile field.</span></span>   <span data-ttu-id="4a116-124">Transaction : Utilisez le profil de validation individuel des transactions sur lesquelles les intérêts sont calculés pour chaque note d'intérêt.</span><span class="sxs-lookup"><span data-stu-id="4a116-124">Transaction – Use the individual posting profile from transactions on which interest is calculated for each interest note.</span></span> <span data-ttu-id="4a116-125">Les transactions auxquelles vous n'avez attribué aucun profil de validation emploient le profil de validation spécifié dans la zone Comptabilité et taxe de l'écran Paramètres de la comptabilité client.</span><span class="sxs-lookup"><span data-stu-id="4a116-125">Transactions that do not have an assigned posting profile will use the posting profile that is specified in the Ledger and sales tax area of the Accounts receivable parameters form.</span></span>  
    * <span data-ttu-id="4a116-126">Sélectionnez un profil de validation ici si vous avez remplacé « Origine du profil de validation » par « Sélectionner ».</span><span class="sxs-lookup"><span data-stu-id="4a116-126">Select a posting profile here if you changed "Use posting profile from" to "Select".</span></span>  
3. <span data-ttu-id="4a116-127">Développez ou réduisez la section Enregistrements à inclure.</span><span class="sxs-lookup"><span data-stu-id="4a116-127">Expand or collapse the Records to include section.</span></span>
4. <span data-ttu-id="4a116-128">Cliquez sur Filtre.</span><span class="sxs-lookup"><span data-stu-id="4a116-128">Click Filter.</span></span>
5. <span data-ttu-id="4a116-129">Entrez un ID client dans le champ Critères.</span><span class="sxs-lookup"><span data-stu-id="4a116-129">In the Criteria field, enter a Customer ID.</span></span> <span data-ttu-id="4a116-130">Par exemple, entrez US-001.</span><span class="sxs-lookup"><span data-stu-id="4a116-130">For example, enter 'US-001'..</span></span>
6. <span data-ttu-id="4a116-131">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="4a116-131">Click OK.</span></span>
7. <span data-ttu-id="4a116-132">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="4a116-132">Click OK.</span></span>

## <a name="print-interest-notes"></a><span data-ttu-id="4a116-133">Imprimer des notes d'intérêt</span><span class="sxs-lookup"><span data-stu-id="4a116-133">Print interest notes</span></span>
1. <span data-ttu-id="4a116-134">Accédez à Crédit et relances > Intérêts > Examiner et traiter les notes d'intérêt.</span><span class="sxs-lookup"><span data-stu-id="4a116-134">Go to Credit and collections > Interest > Review and process interest notes.</span></span>
2. <span data-ttu-id="4a116-135">Sélectionnez Créé dans le champ Statut.</span><span class="sxs-lookup"><span data-stu-id="4a116-135">In the Status field, select 'Created'.</span></span>
3. <span data-ttu-id="4a116-136">Dans le champ Imprimé, sélectionnez « Non imprimé ».</span><span class="sxs-lookup"><span data-stu-id="4a116-136">In the Printed field, select 'Not printed'.</span></span>
4. <span data-ttu-id="4a116-137">Cliquez sur Imprimer.</span><span class="sxs-lookup"><span data-stu-id="4a116-137">Click Print.</span></span>
5. <span data-ttu-id="4a116-138">Développez ou réduisez la section Enregistrements à inclure.</span><span class="sxs-lookup"><span data-stu-id="4a116-138">Expand or collapse the Records to include section.</span></span>
6. <span data-ttu-id="4a116-139">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="4a116-139">Click OK.</span></span>
7. <span data-ttu-id="4a116-140">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="4a116-140">Close the page.</span></span>

## <a name="post-the-interest-note"></a><span data-ttu-id="4a116-141">Valider la note d'intérêt</span><span class="sxs-lookup"><span data-stu-id="4a116-141">Post the interest note</span></span>
1. <span data-ttu-id="4a116-142">Sélectionnez une note d'intérêt qui est prête à valider (le statut est créé).</span><span class="sxs-lookup"><span data-stu-id="4a116-142">Select an interest note that is ready to post (status is created).</span></span>
2. <span data-ttu-id="4a116-143">Cliquez sur Valider.</span><span class="sxs-lookup"><span data-stu-id="4a116-143">Click Post.</span></span>
3. <span data-ttu-id="4a116-144">Entrez la date de validation pour la note d'intérêt.</span><span class="sxs-lookup"><span data-stu-id="4a116-144">Enter the posting date for the interest note.</span></span>
    * <span data-ttu-id="4a116-145">Sélectionnez Oui pour créer une écriture comptable générale pour chaque note d'intérêt.</span><span class="sxs-lookup"><span data-stu-id="4a116-145">Select Yes to create a general ledger transaction for each interest note.</span></span>     <span data-ttu-id="4a116-146">Si vous ne sélectionnez pas Oui, les intérêts de toutes les notes d'intérêt du client sont cumulés et validés dans une transaction de la Comptabilité.</span><span class="sxs-lookup"><span data-stu-id="4a116-146">If you do not select Yes, the interest on all interest notes to the customer is accumulated and posted to the general ledger in one transaction.</span></span>  
4. <span data-ttu-id="4a116-147">Développez ou réduisez la section Enregistrements à inclure.</span><span class="sxs-lookup"><span data-stu-id="4a116-147">Expand or collapse the Records to include section.</span></span>
5. <span data-ttu-id="4a116-148">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="4a116-148">Click OK.</span></span>
6. <span data-ttu-id="4a116-149">Sélectionnez Validé dans le champ Statut.</span><span class="sxs-lookup"><span data-stu-id="4a116-149">In the Status field, select 'Posted'.</span></span>


