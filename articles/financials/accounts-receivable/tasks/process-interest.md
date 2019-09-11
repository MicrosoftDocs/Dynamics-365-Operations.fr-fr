---
title: Traiter les intérêts
description: Cette procédure permet d'indiquer comment créer, imprimer, et valider les notes d'intérêt.
author: ShivamPandey-msft
manager: AnnBe
ms.date: 08/08/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CustPosting, SysQueryForm, CustInterestNote, SrsReportViewerForm
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 7170a7a14237058064ed3091e9437cae312e6bd5
ms.sourcegitcommit: cbcf344b3b552acca56c3e27606eac7f2f124afe
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/22/2019
ms.locfileid: "1916274"
---
# <a name="process-interest"></a><span data-ttu-id="8726d-103">Traiter les intérêts</span><span class="sxs-lookup"><span data-stu-id="8726d-103">Process interest</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="8726d-104">Cette procédure permet d'indiquer comment créer, imprimer, et valider les notes d'intérêt.</span><span class="sxs-lookup"><span data-stu-id="8726d-104">This procedure shows how to create, print, and post interest notes.</span></span> <span data-ttu-id="8726d-105">La société fictive USMF est citée en exemple dans cette tâche.</span><span class="sxs-lookup"><span data-stu-id="8726d-105">This task uses the USMF demo company.</span></span>


## <a name="set-up-interest-on-the-posting-profile"></a><span data-ttu-id="8726d-106">Paramétrer des intérêts dans le profil de validation</span><span class="sxs-lookup"><span data-stu-id="8726d-106">Set up interest on the posting profile</span></span>
1. <span data-ttu-id="8726d-107">Dans le **Volet de navigation**, accédez à **Modules > Crédit et recouvrements > Paramétrage > Profils de validation des clients**.</span><span class="sxs-lookup"><span data-stu-id="8726d-107">In the **Navigation pane**, go to **Modules > Credit and collections > Setup > Customer posting profiles**.</span></span>
2. <span data-ttu-id="8726d-108">Cliquez sur **Modifier**.</span><span class="sxs-lookup"><span data-stu-id="8726d-108">Click **Edit**.</span></span>
3. <span data-ttu-id="8726d-109">Dans l'**organisateur Paramétrage**, dans le champ **Code d'intérêt**, sélectionnez un code d'intérêt dans la liste déroulante.</span><span class="sxs-lookup"><span data-stu-id="8726d-109">In the **Setup fastTab**, in the **Interest code** field, select an interest code from the drop-down list.</span></span> <span data-ttu-id="8726d-110">Si vous ne souhaitez pas calculer d'intérêts pour les transactions utilisant ce profil de validation, laissez le champ vide.</span><span class="sxs-lookup"><span data-stu-id="8726d-110">If you do not want interest calculated for transactions using this posting profile, leave the field blank.</span></span> <span data-ttu-id="8726d-111">L'organisateur **Restriction de table** vous permet de modifier la manière dont les intérêts sont traités.</span><span class="sxs-lookup"><span data-stu-id="8726d-111">The **Table restriction** fastTab allows you to change the way that interest is processed.</span></span> <span data-ttu-id="8726d-112">Si ce champ est défini sur Oui, les intérêts sont calculés pour ce profil de validation.</span><span class="sxs-lookup"><span data-stu-id="8726d-112">If this field is set to Yes, then interest will be calculated for this posting profile.</span></span>  

## <a name="calculate-interest"></a><span data-ttu-id="8726d-113">Calculer les intérêts</span><span class="sxs-lookup"><span data-stu-id="8726d-113">Calculate interest</span></span>
1. <span data-ttu-id="8726d-114">Dans le **Volet de navigation**, accédez à **Modules > Crédit et recouvrements > Intérêt > Créer des notes d'intérêt**.</span><span class="sxs-lookup"><span data-stu-id="8726d-114">In the **Navigation pane**, go to **Modules > Credit and collections > Interest > Create interest notes**.</span></span>
2. <span data-ttu-id="8726d-115">Vous devez sélectionner les types de transaction pour lesquels vous voulez calculer les intérêts.</span><span class="sxs-lookup"><span data-stu-id="8726d-115">You must select the transaction types for which you will calculate interest.</span></span> <span data-ttu-id="8726d-116">Toutes les transactions en cours pour ces types sont incluses dans le calcul de ces montants.</span><span class="sxs-lookup"><span data-stu-id="8726d-116">All of the open transactions for these types will be included in the calculation.</span></span>  
3. <span data-ttu-id="8726d-117">Si vous définissez **Intérêt** sur « Oui », vous calculerez les intérêts sur les intérêts.</span><span class="sxs-lookup"><span data-stu-id="8726d-117">If you set **Interest** to 'Yes', you will calculate interest on interest.</span></span> <span data-ttu-id="8726d-118">Vous pouvez vérifier les règles régissant le calcul des intérêts sur les intérêts avant de les inclure pour ces transactions.</span><span class="sxs-lookup"><span data-stu-id="8726d-118">You may want to check the laws governing the calculation of interest on interest before including these transactions.</span></span>  
4. <span data-ttu-id="8726d-119">Dans le champ **Date de début**, entrez une date à partir de laquelle cet intérêt est calculé.</span><span class="sxs-lookup"><span data-stu-id="8726d-119">In the **From date** field, enter a date from which the interest will be calculated.</span></span> <span data-ttu-id="8726d-120">Si vous ne spécifiez pas de **Date de début**, alors toutes les notes d'intérêt non validées sont annulées et les intérêts sont recalculés à partir de la date de la transaction.</span><span class="sxs-lookup"><span data-stu-id="8726d-120">If you do not specific a **From date**, then all unposted interest notes will be canceled and interest will be recalculated from the transaction date.</span></span>
5. <span data-ttu-id="8726d-121">Dans le champ **Date de fin**, entrez une date de fin à laquelle cet intérêt est calculé.</span><span class="sxs-lookup"><span data-stu-id="8726d-121">In the **To date** field, enter a date to which the interest would be calculated.</span></span>
6. <span data-ttu-id="8726d-122">Dans le champ **Origine du profil de validation**, sélectionnez une option.</span><span class="sxs-lookup"><span data-stu-id="8726d-122">In the **Use posting profile from** field, select an option.</span></span> <span data-ttu-id="8726d-123">Il existe trois options de profil de validation :</span><span class="sxs-lookup"><span data-stu-id="8726d-123">There are three posting profile options:</span></span>
    - <span data-ttu-id="8726d-124">Compte : Utilisez le profil de validation affecté au compte client pour chaque note d'intérêt.</span><span class="sxs-lookup"><span data-stu-id="8726d-124">Account – Use the posting profile that is assigned to the customer account for each interest note.</span></span> 
    - <span data-ttu-id="8726d-125">Sélectionner : Utilisez le profil de validation sélectionné dans le champ Profil de validation.</span><span class="sxs-lookup"><span data-stu-id="8726d-125">Select – Use the posting profile that you select in the Posting profile field.</span></span>
    - <span data-ttu-id="8726d-126">Transaction : Utilisez le profil de validation individuel des transactions sur lesquelles les intérêts sont calculés pour chaque note d'intérêt.</span><span class="sxs-lookup"><span data-stu-id="8726d-126">Transaction – Use the individual posting profile from transactions on which interest is calculated for each interest note.</span></span> <span data-ttu-id="8726d-127">Les transactions auxquelles vous n'avez attribué aucun profil de validation emploient le profil de validation spécifié dans la zone Comptabilité et taxe de l'écran Paramètres de la comptabilité client.</span><span class="sxs-lookup"><span data-stu-id="8726d-127">Transactions that do not have an assigned posting profile will use the posting profile that is specified in the Ledger and sales tax area of the Accounts receivable parameters form.</span></span>  
7. <span data-ttu-id="8726d-128">Développez l'organisateur **Enregistrements à inclure**.</span><span class="sxs-lookup"><span data-stu-id="8726d-128">Expand the **Records to include** fastTab.</span></span>
8. <span data-ttu-id="8726d-129">Cliquez sur **Filtre**.</span><span class="sxs-lookup"><span data-stu-id="8726d-129">Click **Filter**.</span></span>
9. <span data-ttu-id="8726d-130">Dans le champ **Critères**, entrez un ID client.</span><span class="sxs-lookup"><span data-stu-id="8726d-130">In the **Criteria** field, enter a Customer ID.</span></span> <span data-ttu-id="8726d-131">Par exemple, entrez US-001.</span><span class="sxs-lookup"><span data-stu-id="8726d-131">For example, enter 'US-001'.</span></span>
6. <span data-ttu-id="8726d-132">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="8726d-132">Click **OK**.</span></span>
7. <span data-ttu-id="8726d-133">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="8726d-133">Click **OK**.</span></span>

## <a name="print-interest-notes"></a><span data-ttu-id="8726d-134">Imprimer des notes d'intérêt</span><span class="sxs-lookup"><span data-stu-id="8726d-134">Print interest notes</span></span>
1. <span data-ttu-id="8726d-135">Dans le **Volet de navigation**, accédez à **Modules > Crédit et recouvrements > Intérêt > Examiner et traiter les notes d'intérêt**.</span><span class="sxs-lookup"><span data-stu-id="8726d-135">In the **Navigation pane**, go to **Modules > Credit and collections > Interest > Review and process interest notes**.</span></span>
2. <span data-ttu-id="8726d-136">Dans le champ **Statut**, sélectionnez « Créé ».</span><span class="sxs-lookup"><span data-stu-id="8726d-136">In the **Status** field, select 'Created'.</span></span>
3. <span data-ttu-id="8726d-137">Dans le champ **Imprimé**, sélectionnez « Non imprimé ».</span><span class="sxs-lookup"><span data-stu-id="8726d-137">In the **Printed** field, select 'Not printed'.</span></span>
4. <span data-ttu-id="8726d-138">Cliquez sur **Imprimer**.</span><span class="sxs-lookup"><span data-stu-id="8726d-138">Click **Print**.</span></span>
5. <span data-ttu-id="8726d-139">Développez l'organisateur **Enregistrements à inclure**.</span><span class="sxs-lookup"><span data-stu-id="8726d-139">Expand the **Records to include** fastTab.</span></span>
6. <span data-ttu-id="8726d-140">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="8726d-140">Click **OK**.</span></span>
7. <span data-ttu-id="8726d-141">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="8726d-141">Close the page.</span></span>

## <a name="post-the-interest-note"></a><span data-ttu-id="8726d-142">Valider la note d'intérêt</span><span class="sxs-lookup"><span data-stu-id="8726d-142">Post the interest note</span></span>
1. <span data-ttu-id="8726d-143">Sélectionnez une note d'intérêt qui est prête à valider (le statut est créé).</span><span class="sxs-lookup"><span data-stu-id="8726d-143">Select an interest note that is ready to post (status is created).</span></span>
2. <span data-ttu-id="8726d-144">Cliquez sur **Valider**.</span><span class="sxs-lookup"><span data-stu-id="8726d-144">Click **Post**.</span></span>
3. <span data-ttu-id="8726d-145">Entrez la date de validation pour la note d'intérêt.</span><span class="sxs-lookup"><span data-stu-id="8726d-145">Enter the posting date for the interest note.</span></span> <span data-ttu-id="8726d-146">Sélectionnez Oui pour créer une écriture comptable générale pour chaque note d'intérêt.</span><span class="sxs-lookup"><span data-stu-id="8726d-146">Select Yes to create a general ledger transaction for each interest note.</span></span> <span data-ttu-id="8726d-147">Si vous ne sélectionnez pas Oui, les intérêts de toutes les notes d'intérêt du client sont cumulés et validés dans une transaction de la Comptabilité.</span><span class="sxs-lookup"><span data-stu-id="8726d-147">If you do not select Yes, the interest on all interest notes to the customer is accumulated and posted to the general ledger in one transaction.</span></span>  
4. <span data-ttu-id="8726d-148">Développez l'organisateur **Enregistrements à inclure**.</span><span class="sxs-lookup"><span data-stu-id="8726d-148">Expand the **Records to include** fastTab.</span></span>
5. <span data-ttu-id="8726d-149">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="8726d-149">Click **OK**.</span></span>
6. <span data-ttu-id="8726d-150">Dans le champ **Statut**, sélectionnez « Validé ».</span><span class="sxs-lookup"><span data-stu-id="8726d-150">In the **Status** field, select 'Posted'.</span></span>

