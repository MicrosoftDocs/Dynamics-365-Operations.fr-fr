---
title: Traiter les lettres de relance
description: Cette rubrique indique comment créer, imprimer et valider les lettres de relance.
author: ShivamPandey-msft
manager: AnnBe
ms.date: 07/01/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CustPosting, CustCollectionLetterNote
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2018-12-01
ms.dyn365.ops.version: 8.1.3
ms.openlocfilehash: 326d9375670cb4f4990a4f7070bf923a28b2c025
ms.sourcegitcommit: a368682f9cf3897347d155f1a2d4b33e555cc2c4
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/08/2019
ms.locfileid: "1867653"
---
# <a name="process-collection-letters"></a><span data-ttu-id="f5554-103">Traiter les lettres de relance</span><span class="sxs-lookup"><span data-stu-id="f5554-103">Process collection letters</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="f5554-104">Cette rubrique indique comment créer, imprimer et valider les lettres de relance.</span><span class="sxs-lookup"><span data-stu-id="f5554-104">This topic shows how to create, print, and post collection letters.</span></span> <span data-ttu-id="f5554-105">La société fictive USMF est citée en exemple dans cette tâche.</span><span class="sxs-lookup"><span data-stu-id="f5554-105">This task uses the USMF demo company.</span></span>

## <a name="set-up-a-collection-letter-sequence-on-the-posting-profile"></a><span data-ttu-id="f5554-106">Configuration d'une séquence de lettres de relance sur le profil de validation</span><span class="sxs-lookup"><span data-stu-id="f5554-106">Set up a collection letter sequence on the posting profile</span></span>
1. <span data-ttu-id="f5554-107">Accédez au **Volet de navigation > Modules > Crédit et recouvrements > Paramétrage > Profils de validation des clients**.</span><span class="sxs-lookup"><span data-stu-id="f5554-107">Go to **Navigation pane > Modules > Credit and collections > Setup > Customer posting profiles**.</span></span>
2. <span data-ttu-id="f5554-108">Cliquez sur **Modifier**.</span><span class="sxs-lookup"><span data-stu-id="f5554-108">Click **Edit**.</span></span>
3. <span data-ttu-id="f5554-109">Sélectionnez une séquence de lettres de relance dans la liste déroulante.</span><span class="sxs-lookup"><span data-stu-id="f5554-109">Select a collection letter sequence from the drop-down list.</span></span> <span data-ttu-id="f5554-110">Si vous ne souhaitez pas générer de lettres de relance pour les transactions utilisant ce profil de validation, laissez le champ vide.</span><span class="sxs-lookup"><span data-stu-id="f5554-110">If you do not want to generate collection letters for transactions using this posting profile, leave the field blank.</span></span>  
4. <span data-ttu-id="f5554-111">Développez l'onglet **Restrictions de table** pour modifier la manière dont les lettres de relance sont traitées.</span><span class="sxs-lookup"><span data-stu-id="f5554-111">Expand the **Table restrictions** tab to change the way that collection letters are processed.</span></span> <span data-ttu-id="f5554-112">Si ce champ est défini sur **Oui**, les lettres de relance sont créées pour ce profil de validation.</span><span class="sxs-lookup"><span data-stu-id="f5554-112">If this field is set to **Yes**, then collection letters will be created for this posting profile.</span></span>  

## <a name="create-collection-letters"></a><span data-ttu-id="f5554-113">Créer des lettres de relance</span><span class="sxs-lookup"><span data-stu-id="f5554-113">Create collection letters</span></span>
1. <span data-ttu-id="f5554-114">Accédez au **Volet de navigation > Modules > Crédit et relances > Lettre de relance > Créer des lettres de relance**.</span><span class="sxs-lookup"><span data-stu-id="f5554-114">Go to **Navigation pane > Modules > Credit and collections > Collection letter > Create collection letters**.</span></span>
2. <span data-ttu-id="f5554-115">Sélectionnez les types de transaction pour lesquels vous allez recueillir des lettres.</span><span class="sxs-lookup"><span data-stu-id="f5554-115">Select the transaction types for which you will collect letters.</span></span> <span data-ttu-id="f5554-116">Toutes les transactions en cours pour ces types sont incluses dans le calcul de ces montants.</span><span class="sxs-lookup"><span data-stu-id="f5554-116">All of the open transactions for these types will be included in the calculation.</span></span>  
3. <span data-ttu-id="f5554-117">Dans le champ **Lettre de relance**, sélectionnez une option.</span><span class="sxs-lookup"><span data-stu-id="f5554-117">In the **Collection letter** field, select an option.</span></span>
4. <span data-ttu-id="f5554-118">Dans le champ **Date de la lettre de relance**, entrez la date de la lettre de relance.</span><span class="sxs-lookup"><span data-stu-id="f5554-118">In the **Collection letter date** field, enter the date of the collection letter.</span></span>
5. <span data-ttu-id="f5554-119">Sélectionnez un profil de validation si vous avez remplacé **Origine du profil de validation** par **Sélectionner**.</span><span class="sxs-lookup"><span data-stu-id="f5554-119">Select a posting profile if you changed **Use posting profile from** to **Select**.</span></span> <span data-ttu-id="f5554-120">Il existe deux options de profil de validation :</span><span class="sxs-lookup"><span data-stu-id="f5554-120">There are two posting profile options:</span></span>   

   - <span data-ttu-id="f5554-121">**Compte** : Utilisez le profil de validation affecté au compte client pour chaque note d'intérêt.</span><span class="sxs-lookup"><span data-stu-id="f5554-121">**Account** – Use the posting profile that is assigned to the customer account for each interest note.</span></span>   
   - <span data-ttu-id="f5554-122">**Sélectionner** : Utilisez le profil de validation sélectionné dans le champ **Profil de validation**.</span><span class="sxs-lookup"><span data-stu-id="f5554-122">**Select** – Use the posting profile that you select in the **Posting profile** field.</span></span>  

6. <span data-ttu-id="f5554-123">Développez la section **Enregistrements à inclure**.</span><span class="sxs-lookup"><span data-stu-id="f5554-123">Expand the **Records to include** section.</span></span>
7. <span data-ttu-id="f5554-124">Sélectionnez **Filtrer**.</span><span class="sxs-lookup"><span data-stu-id="f5554-124">Select **Filter**.</span></span>
8. <span data-ttu-id="f5554-125">Dans le champ **Critères**, entrez un ID client.</span><span class="sxs-lookup"><span data-stu-id="f5554-125">In the **Criteria** field, enter a Customer ID.</span></span> <span data-ttu-id="f5554-126">Par exemple, entrez US-001.</span><span class="sxs-lookup"><span data-stu-id="f5554-126">For example, enter 'US-001'.</span></span>
9. <span data-ttu-id="f5554-127">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="f5554-127">Select **OK**.</span></span>
10. <span data-ttu-id="f5554-128">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="f5554-128">Select **OK**.</span></span>

## <a name="print-collection-letters"></a><span data-ttu-id="f5554-129">Imprimer/valider des lettres de relance</span><span class="sxs-lookup"><span data-stu-id="f5554-129">Print collection letters</span></span>
1. <span data-ttu-id="f5554-130">Accédez au **Volet de navigation > Modules > Crédit et relances > Lettre de relance > Examiner et traiter les lettres de relance**.</span><span class="sxs-lookup"><span data-stu-id="f5554-130">Go to **navigation pane > Modules > Credit and collections > Collection letter > Review and process collection letters**.</span></span>
2. <span data-ttu-id="f5554-131">Dans le champ **Statut**, sélectionnez **Créé**.</span><span class="sxs-lookup"><span data-stu-id="f5554-131">In the **Status** field, select **Created**.</span></span>
3. <span data-ttu-id="f5554-132">Dans le champ **Imprimé**, sélectionnez **Non imprimé**.</span><span class="sxs-lookup"><span data-stu-id="f5554-132">In the **Printed** field, select **Not printed**.</span></span>
4. <span data-ttu-id="f5554-133">Sélectionnez **Imprimer**.</span><span class="sxs-lookup"><span data-stu-id="f5554-133">Select **Print**.</span></span>
5. <span data-ttu-id="f5554-134">Sélectionnez **Note de lettre de relance**.</span><span class="sxs-lookup"><span data-stu-id="f5554-134">Select **Collection letter note**.</span></span>
6. <span data-ttu-id="f5554-135">Dans la section **Paramètres**, entrez la date limite pour les validations.</span><span class="sxs-lookup"><span data-stu-id="f5554-135">In the **Parameters** section, enter the cutoff date for postings.</span></span>
7. <span data-ttu-id="f5554-136">Développez la section **Enregistrements à inclure** et entrez les détails de la lettre de relance.</span><span class="sxs-lookup"><span data-stu-id="f5554-136">Expand the **Records to include** section and enter the details of the Collection letter note.</span></span>
8. <span data-ttu-id="f5554-137">Sélectionnez **OK** pour imprimer la lettre de relance.</span><span class="sxs-lookup"><span data-stu-id="f5554-137">Select **OK** to print the collection letter.</span></span>
9. <span data-ttu-id="f5554-138">Validez la lettre de relance.</span><span class="sxs-lookup"><span data-stu-id="f5554-138">Post the collection letter.</span></span>

    1. <span data-ttu-id="f5554-139">Sélectionnez **Valider**.</span><span class="sxs-lookup"><span data-stu-id="f5554-139">Select **Post**.</span></span>
    1. <span data-ttu-id="f5554-140">Entrer la date de validation pour la lettre de relance.</span><span class="sxs-lookup"><span data-stu-id="f5554-140">Enter the posting date for the collection letter.</span></span>
    1. <span data-ttu-id="f5554-141">Développez la section **Enregistrements à inclure**.</span><span class="sxs-lookup"><span data-stu-id="f5554-141">Expand the **Records to include** section.</span></span>
    1. <span data-ttu-id="f5554-142">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="f5554-142">Select **OK**.</span></span>
    1. <span data-ttu-id="f5554-143">Dans le champ **Statut**, sélectionnez **Validé**.</span><span class="sxs-lookup"><span data-stu-id="f5554-143">In the **Status** field, select **Posted**.</span></span>
    1. <span data-ttu-id="f5554-144">Dans le champ **Imprimé**, sélectionnez une option.</span><span class="sxs-lookup"><span data-stu-id="f5554-144">In the **Printed** field, select an option.</span></span>

## <a name="control-collection-letters-at-the-customer-level"></a><span data-ttu-id="f5554-145">Contrôler les lettres de relance au niveau du client</span><span class="sxs-lookup"><span data-stu-id="f5554-145">Control collection letters at the customer level</span></span>
<span data-ttu-id="f5554-146">Vous pouvez également paramétrer des lettres de relance au niveau du client afin que le code lettre de relance de chaque transaction soit suivi, mais le processus de lettre de relance sera basé sur un niveau de lettre de relance unique stocké pour le client.</span><span class="sxs-lookup"><span data-stu-id="f5554-146">You can also set up collection letters at the customer level so that the collection letter code for each transaction is tracked, but the collection letter processing will be based on a single collection letter level that is stored for the customer.</span></span> <span data-ttu-id="f5554-147">La lettre de relance unique contiendra toutes les transactions en retard pour le client.</span><span class="sxs-lookup"><span data-stu-id="f5554-147">The single collection letter will contain all transactions that are overdue for the customer.</span></span> <span data-ttu-id="f5554-148">Comme les jours de grâce sont désormais suivis au niveau du client, la prochaine lettre de relance ne sera pas envoyée tant que le nombre de jours de grâce ne sera pas dépassé pour la lettre de relance suivante de la série, même si les transactions sont en retard après l'envoi de la dernière lettre de relance.</span><span class="sxs-lookup"><span data-stu-id="f5554-148">Because the grace days are now tracked on the customer level, the next collection letter will not be sent until the number of grace days has passed for the next collection letter in the sequence, even though transactions become overdue after the last collection letter was sent.</span></span> <span data-ttu-id="f5554-149">Cette option permet de réduire le nombre de lettres de relance que vous envoyez par client.</span><span class="sxs-lookup"><span data-stu-id="f5554-149">This option reduces the number of collection letters you will send per customer.</span></span> 

### <a name="set-up-the-customer-to-control-collection-letters-at-the-customer-level"></a><span data-ttu-id="f5554-150">Paramétrer le client pour contrôler les lettres de relance au niveau du client</span><span class="sxs-lookup"><span data-stu-id="f5554-150">Set up the customer to control collection letters at the customer level</span></span>
1.  <span data-ttu-id="f5554-151">Accédez au **Volet de navigation > Modules > Crédit et relances > Paramétrage > Paramètres de la comptabilité client** et sélectionnez l'onglet **Recouvrements**.</span><span class="sxs-lookup"><span data-stu-id="f5554-151">Go to **Navigation pane > Modules > Credit and collections > Setup > Accounts receivable parameters** and select the **Collections** tab.</span></span> 
2.  <span data-ttu-id="f5554-152">Modifiez la valeur de **Créer une lettre de relance par** avec **Client**.</span><span class="sxs-lookup"><span data-stu-id="f5554-152">Change the value of **Create collection letter per** to **Customer**.</span></span> 
3.  <span data-ttu-id="f5554-153">Accédez au **Volet de navigation > Modules > Crédit et relances > Lettre de relance > Examiner et traiter les lettres de relance**.</span><span class="sxs-lookup"><span data-stu-id="f5554-153">Go to **navigation pane > Modules > Credit and collections > Collection letter > Review and process collection letters**.</span></span> <span data-ttu-id="f5554-154">Une seule lettre de relance est générée pour un client avec toutes les transactions en retard.</span><span class="sxs-lookup"><span data-stu-id="f5554-154">Only one collection letter will be generated for a customer with all the overdue transactions.</span></span>

## <a name="ignore-payments-and-credit-memos-when-calculating-the-collection-letter-code"></a><span data-ttu-id="f5554-155">Ignorer les paiements et les avoirs lors du calcul du code lettre de relance</span><span class="sxs-lookup"><span data-stu-id="f5554-155">Ignore payments and credit memos when calculating the collection letter code</span></span>
<span data-ttu-id="f5554-156">Si vous incluez des paiements et des avoirs dans les transactions à inclure dans les lettres de relance, vous pouvez avoir des paiements ou des avoirs qui déclenchent une lettre de relance.</span><span class="sxs-lookup"><span data-stu-id="f5554-156">If you include payments and credit memos in the transactions that will be included in the collection letters, you may have payments or credit memos that will trigger a collection letter.</span></span> <span data-ttu-id="f5554-157">Vous pouvez contrôler la façon dont les paiements et les avoirs contrôlent le code lettre de relance en modifiant la valeur du paramètre **Ignorer les paiements et les avoirs lors du calcul du code lettre de relance**.</span><span class="sxs-lookup"><span data-stu-id="f5554-157">You can control how payments and credit memos control the collection letter code by changing the value of the **Ignore payments and credit memos when calculating the collection letter code** parameter.</span></span> 

<span data-ttu-id="f5554-158">Pour ignorer les paiements et les avoirs lors du calcul du code lettre de relance, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="f5554-158">To ignore payments and credit memos when calculating the collection letter code, do the following.</span></span>

1. <span data-ttu-id="f5554-159">Accédez au **Volet de navigation > Modules > Crédit et relances > Paramétrage > Paramètres de la comptabilité client** et sélectionnez l'onglet **Recouvrements**.</span><span class="sxs-lookup"><span data-stu-id="f5554-159">Go to **Navigation pane > Modules > Credit and collections > Setup > Accounts receivable parameters** and click the **Collections** tab.</span></span> 
2. <span data-ttu-id="f5554-160">Modifiez la valeur de **Ignorer les paiements et les avoirs lors du calcul du code lettre de relance** avec **Oui**.</span><span class="sxs-lookup"><span data-stu-id="f5554-160">Change the value of **Ignore payments and credit memos when calculating the collection letter code** to **Yes**.</span></span>
