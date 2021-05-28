---
title: Exemple Traiter les lettres de relance
description: Cette rubrique présente un exemple illustrant le processus de création, d’impression et de publication de lettres de relance.
author: JodiChristiansen
ms.date: 02/03/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: CustPosting, CustCollectionLetterNote
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: jchrist
ms.search.validFrom: 2021-02-03
ms.dyn365.ops.version: 10.0.16
ms.openlocfilehash: fb2651644efd2cadfccb91e48c34dfddc8383e1f
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2021
ms.locfileid: "6021414"
---
# <a name="process-collection-letters-example"></a><span data-ttu-id="1276e-103">Exemple Traiter les lettres de relance</span><span class="sxs-lookup"><span data-stu-id="1276e-103">Process collection letters example</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="1276e-104">Cette rubrique présente un exemple illustrant le processus de création, d’impression et de publication de lettres de relance.</span><span class="sxs-lookup"><span data-stu-id="1276e-104">This topic goes through an example that shows the process of creating, printing, and posting collection letters.</span></span> <span data-ttu-id="1276e-105">L’exemple est basé sur l’option **Ignorer les paiements et les avoirs lors du calcul du code de lettre de relance** dans Crédit et relances.</span><span class="sxs-lookup"><span data-stu-id="1276e-105">The example is based on the **Ignore payments and credit memos when calculating collection letter code** option in Credit and collections.</span></span> <span data-ttu-id="1276e-106">Il utilise les données de la société fictive USMF et d’un nouveau client, US-045.</span><span class="sxs-lookup"><span data-stu-id="1276e-106">It uses data in the USMF demo company and a new customer, US-045.</span></span>

<span data-ttu-id="1276e-107">Pour commencer, accédez à **Comptabilité client \> Clients \> Tous les clients**, sélectionnez **Nouveau**, puis entrez les informations requises pour créer le client US-045.</span><span class="sxs-lookup"><span data-stu-id="1276e-107">To begin, go to **Accounts receivable \> Customers \> All customers**, select **New**, and then enter the required information to create customer US-045.</span></span>

<span data-ttu-id="1276e-108">Lorsque vous avez terminé, vous devez suivre les étapes suivantes.</span><span class="sxs-lookup"><span data-stu-id="1276e-108">When you've finished, follow these steps.</span></span>

1. <span data-ttu-id="1276e-109">Accédez à **Crédit et relances \> Lettre de relance \> Paramétrer la série de lettres de relance** et paramétrez la série de lettres de relance comme indiqué dans le tableau suivant affecté au profil de validation client.</span><span class="sxs-lookup"><span data-stu-id="1276e-109">Go to **Credit and collections \> Collection letter \> Setup collection letter sequence**, and set up the collection letter sequence as shown in the following table that is assigned to the customer posting profile.</span></span>

|     <span data-ttu-id="1276e-110">Code lettre de relance</span><span class="sxs-lookup"><span data-stu-id="1276e-110">Collection   letter code</span></span>      |     <span data-ttu-id="1276e-111">Description</span><span class="sxs-lookup"><span data-stu-id="1276e-111">Description</span></span>                           |     <span data-ttu-id="1276e-112">Devise</span><span class="sxs-lookup"><span data-stu-id="1276e-112">Currency</span></span>      |     <span data-ttu-id="1276e-113">Compte principal</span><span class="sxs-lookup"><span data-stu-id="1276e-113">Main   account</span></span>        |     <span data-ttu-id="1276e-114">Frais en devise</span><span class="sxs-lookup"><span data-stu-id="1276e-114">Fee   in currency</span></span>     |     <span data-ttu-id="1276e-115">Minimum au-dessus</span><span class="sxs-lookup"><span data-stu-id="1276e-115">Minimum   over</span></span>        |     <span data-ttu-id="1276e-116">Bloc de jours</span><span class="sxs-lookup"><span data-stu-id="1276e-116">Days   Block</span></span>      |
|---------------------------------  |---------------------------------------    |-----------------  |-----------------------    |-------------------------- |-----------------------    |---------------------  |
|     <span data-ttu-id="1276e-117">Lettre de relance 1</span><span class="sxs-lookup"><span data-stu-id="1276e-117">Collection   letter 1</span></span>         |     <span data-ttu-id="1276e-118">Deuxième notification avec frais</span><span class="sxs-lookup"><span data-stu-id="1276e-118">Second   notification with fee</span></span>        |     <span data-ttu-id="1276e-119">USD</span><span class="sxs-lookup"><span data-stu-id="1276e-119">USD</span></span>           |                           |     <span data-ttu-id="1276e-120">0,00</span><span class="sxs-lookup"><span data-stu-id="1276e-120">0.00</span></span>                  |     <span data-ttu-id="1276e-121">0,00</span><span class="sxs-lookup"><span data-stu-id="1276e-121">0.00</span></span>                  |     <span data-ttu-id="1276e-122">2</span><span class="sxs-lookup"><span data-stu-id="1276e-122">2</span></span>                 |
|     <span data-ttu-id="1276e-123">Lettre de relance 2</span><span class="sxs-lookup"><span data-stu-id="1276e-123">Collection   letter 2</span></span>         |     <span data-ttu-id="1276e-124">Deuxième notification avec frais</span><span class="sxs-lookup"><span data-stu-id="1276e-124">Second   notification with fee</span></span>        |     <span data-ttu-id="1276e-125">USC</span><span class="sxs-lookup"><span data-stu-id="1276e-125">USC</span></span>           |     <span data-ttu-id="1276e-126">403150</span><span class="sxs-lookup"><span data-stu-id="1276e-126">403150</span></span>                |     <span data-ttu-id="1276e-127">20.00</span><span class="sxs-lookup"><span data-stu-id="1276e-127">20.00</span></span>                 |     <span data-ttu-id="1276e-128">10.00</span><span class="sxs-lookup"><span data-stu-id="1276e-128">10.00</span></span>                 |     <span data-ttu-id="1276e-129">3</span><span class="sxs-lookup"><span data-stu-id="1276e-129">3</span></span>                 |
|     <span data-ttu-id="1276e-130">Relance</span><span class="sxs-lookup"><span data-stu-id="1276e-130">Collection</span></span>                    |     <span data-ttu-id="1276e-131">Notification finale avec frais</span><span class="sxs-lookup"><span data-stu-id="1276e-131">Final   notification with fee</span></span>         |     <span data-ttu-id="1276e-132">USD</span><span class="sxs-lookup"><span data-stu-id="1276e-132">USD</span></span>           |     <span data-ttu-id="1276e-133">403150</span><span class="sxs-lookup"><span data-stu-id="1276e-133">403150</span></span>                |     <span data-ttu-id="1276e-134">50.00</span><span class="sxs-lookup"><span data-stu-id="1276e-134">50.00</span></span>                 |     <span data-ttu-id="1276e-135">100.00</span><span class="sxs-lookup"><span data-stu-id="1276e-135">100.00</span></span>                |     <span data-ttu-id="1276e-136">15</span><span class="sxs-lookup"><span data-stu-id="1276e-136">15</span></span>                |

<span data-ttu-id="1276e-137">L’illustration suivante montre les informations contenues dans le tableau telles qu’elles apparaissent sur la page **Lettres de relance**.</span><span class="sxs-lookup"><span data-stu-id="1276e-137">The following illustration shows the information that's in the table as it would appear on the **Collection letters** page.</span></span> 

<span data-ttu-id="1276e-138">[![Paramétrage d’une série de lettres de relance](./media/Ignore-payments-creditmemos-1.PNG)](./media/Ignore-payments-creditmemos-1.PNG)</span><span class="sxs-lookup"><span data-stu-id="1276e-138">[![Setting up a collection letter sequence](./media/Ignore-payments-creditmemos-1.PNG)](./media/Ignore-payments-creditmemos-1.PNG)</span></span>

 <span data-ttu-id="1276e-139">Vous devez maintenant définir les deux paramètres requis pour cet exemple.</span><span class="sxs-lookup"><span data-stu-id="1276e-139">You must now set the two parameters that are required for this example.</span></span>

2. <span data-ttu-id="1276e-140">Accédez à **Crédit et relances \> Paramétrage \> Paramètres de la comptabilité client** et procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="1276e-140">Go to **Credit and collections \> Setup \> Accounts receivable parameters**, and follow these steps:</span></span>

    1. <span data-ttu-id="1276e-141">Dans l’onglet **Relance**, définissez l’option **Ignorer les paiements et les avoirs lors du calcul du code de lettre de relance** dans sur **Oui**.</span><span class="sxs-lookup"><span data-stu-id="1276e-141">On the **Collections** tab, set the **Ignore payments and credit memos when calculating collection letter code** option to **Yes**.</span></span>
    2. <span data-ttu-id="1276e-142">Assurez-vous que le champ **Créer une lettre de relance par** est défini sur **Client**.</span><span class="sxs-lookup"><span data-stu-id="1276e-142">Make sure that the **Create collection letter per** field is set to **Customer**.</span></span>

    <span data-ttu-id="1276e-143">[![Paramétrage des paramètres de Comptabilité client pour les crédits et relances](./media/Ignore-payments-creditmemos-2.PNG)](./media/Ignore-payments-creditmemos-2.PNG)</span><span class="sxs-lookup"><span data-stu-id="1276e-143">[![Setting Accounts receivable parameters for Credit collections](./media/Ignore-payments-creditmemos-2.PNG)](./media/Ignore-payments-creditmemos-2.PNG)</span></span>

3. <span data-ttu-id="1276e-144">Accédez à **Comptabilité client \> Factures \> Toutes factures financières**, sélectionnez **Nouveau**, puis procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="1276e-144">Go to **Accounts receivable \> Invoices \> All free text invoices**, select **New**, and then follow these steps:</span></span>

    1. <span data-ttu-id="1276e-145">Dans le champ **Compte client**, sélectionnez **US-045**.</span><span class="sxs-lookup"><span data-stu-id="1276e-145">In the **Customer account** field select **US-045**.</span></span>
    2. <span data-ttu-id="1276e-146">Dans le champ **Date de facture**, entrez **15/01/2021**.</span><span class="sxs-lookup"><span data-stu-id="1276e-146">In the **Invoice date** field, enter **1/15/2021**.</span></span>
    3. <span data-ttu-id="1276e-147">Dans le champ **Date d’échéance**, entrez **16/01/2021**.</span><span class="sxs-lookup"><span data-stu-id="1276e-147">In the **Due date** field, enter **1/16/2021**.</span></span>
    4. <span data-ttu-id="1276e-148">Sur le raccourci **Lignes de facture**, dans le champ **Compte principal**, entrez **401100**.</span><span class="sxs-lookup"><span data-stu-id="1276e-148">On the **Invoice lines** FastTab, in the **Main account** field, enter **401100**.</span></span>
    5. <span data-ttu-id="1276e-149">Dans le champ **Prix unitaire**, entrez **500.00**.</span><span class="sxs-lookup"><span data-stu-id="1276e-149">In the **Unit price** field, enter **500.00**.</span></span>
    6. <span data-ttu-id="1276e-150">Sélectionnez **Valider**.</span><span class="sxs-lookup"><span data-stu-id="1276e-150">Select **Post**.</span></span>

    <span data-ttu-id="1276e-151">Vous devez maintenant saisir deux avoirs pour le client.</span><span class="sxs-lookup"><span data-stu-id="1276e-151">You must now enter two credit notes for the customer.</span></span>

4. <span data-ttu-id="1276e-152">Sélectionnez **Nouveau**, puis procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="1276e-152">Select **New**, and then follow these steps:</span></span>

    1. <span data-ttu-id="1276e-153">Dans le champ **Compte client**, sélectionnez **US-045**.</span><span class="sxs-lookup"><span data-stu-id="1276e-153">In the **Customer account** field, select **US-045**.</span></span>
    2. <span data-ttu-id="1276e-154">Dans le champ **Date de facture**, entrez **15/01/2021**.</span><span class="sxs-lookup"><span data-stu-id="1276e-154">In the **Invoice date** field, enter **1/15/2021**.</span></span>
    3. <span data-ttu-id="1276e-155">Dans le champ **Date d’échéance**, entrez **16/01/2021**.</span><span class="sxs-lookup"><span data-stu-id="1276e-155">In the **Due date** field, enter **1/16/2021**.</span></span>
    4. <span data-ttu-id="1276e-156">Sur le raccourci **Lignes de facture**, dans le champ **Compte principal**, entrez **401100**.</span><span class="sxs-lookup"><span data-stu-id="1276e-156">On the **Invoice lines** FastTab, in the **Main account** field, enter **401100**.</span></span>
    5. <span data-ttu-id="1276e-157">Dans le champ **Prix unitaire**, entrez **-100,00**.</span><span class="sxs-lookup"><span data-stu-id="1276e-157">In the **Unit price** field, enter **-100.00**.</span></span>
    6. <span data-ttu-id="1276e-158">Sélectionnez **Valider**.</span><span class="sxs-lookup"><span data-stu-id="1276e-158">Select **Post**.</span></span>

5. <span data-ttu-id="1276e-159">Répétez l’étape 4, mais entrez **-200,00** dans le champ **Prix unitaire**.</span><span class="sxs-lookup"><span data-stu-id="1276e-159">Repeat step 4, but enter **-200.00** in the **Unit price** field.</span></span>
6. <span data-ttu-id="1276e-160">Accédez à **Comptabilité client \> Clients \> Tous les clients** et sélectionnez le client **US-045**.</span><span class="sxs-lookup"><span data-stu-id="1276e-160">Go to **Accounts receivable \> Customers \> All customers**, and select customer **US-045**.</span></span> <span data-ttu-id="1276e-161">Ensuite, dans le volet Actions, sélectionnez **Transactions \> Transactions** pour vérifier les transactions client que vous avez validées précédemment.</span><span class="sxs-lookup"><span data-stu-id="1276e-161">Then, on the Action Pane, select **Transactions \> Transactions** to review the customer transactions that you posted earlier.</span></span>

    <span data-ttu-id="1276e-162">[![Vérification des transactions client validées](./media/Ignore-payments-creditmemos-3.PNG)](./media/Ignore-payments-creditmemos-3.PNG)</span><span class="sxs-lookup"><span data-stu-id="1276e-162">[![Reviewing the posted customer transactions](./media/Ignore-payments-creditmemos-3.PNG)](./media/Ignore-payments-creditmemos-3.PNG)</span></span>

    <span data-ttu-id="1276e-163">Vous devez maintenant créer des lettres de relance pour le client US-045.</span><span class="sxs-lookup"><span data-stu-id="1276e-163">You must now create collection letters for customer US-045.</span></span>

7. <span data-ttu-id="1276e-164">Accédez à **Crédit et relances \> Lettre de relance \> Créer des lettres de relance** et procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="1276e-164">Go to **Credit and collections \> Collection letter \> Create collection letters**, and follow these steps:</span></span>

    1. <span data-ttu-id="1276e-165">Définissez les options **Facture** et **Avoir** sur **Oui**.</span><span class="sxs-lookup"><span data-stu-id="1276e-165">Set the **Invoice** and **Credit note** options to **Yes**.</span></span>

        <span data-ttu-id="1276e-166">Par défaut, le champ **Lettre de relance** doit être défini sur **Lettre de relance par client**.</span><span class="sxs-lookup"><span data-stu-id="1276e-166">By default, the **Collection letter** field should be set to **Collection per customer**.</span></span>

    2. <span data-ttu-id="1276e-167">Dans le champ **Date de la lettre de relance**, saisissez **19/01/2021**.</span><span class="sxs-lookup"><span data-stu-id="1276e-167">In the **Collection letter date** field, enter **1/19/2021**.</span></span>
    3. <span data-ttu-id="1276e-168">Sur le raccourci **Enregistrements à inclure**, sélectionnez **Filtre**, puis, dans le champ **Compte client**, ajoutez le client **US-045**.</span><span class="sxs-lookup"><span data-stu-id="1276e-168">On the **Records to include** FastTab, select **Filter**, and then, in the **Customer account** field, add customer **US-045**.</span></span>
    4. <span data-ttu-id="1276e-169">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="1276e-169">Select **OK**.</span></span>
    5. <span data-ttu-id="1276e-170">Sélectionnez **OK** pour créer des lettres de relance.</span><span class="sxs-lookup"><span data-stu-id="1276e-170">Select **OK** to create collection letters.</span></span>

8. <span data-ttu-id="1276e-171">Accédez à **Crédit et relances \> Lettre de relance \> Examiner et traiter les lettres de relance** et procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="1276e-171">Go to **Credit and collections \> Collection letter \> Review and process collection letters**, and follow these steps:</span></span>

    1. <span data-ttu-id="1276e-172">Notez que le code de la lettre de relance sur l’en-tête et les lignes de transaction est **Lettre de relance 1**, car cette lettre de relance est la première de la série.</span><span class="sxs-lookup"><span data-stu-id="1276e-172">Notice that the collection letter code on both the header and the transaction lines is **Collection letter 1**, because this collection letter is the first collection letter in the sequence.</span></span> <span data-ttu-id="1276e-173">(Pour afficher les lignes de transaction, vous devrez peut-être sélectionner le raccourci **Transactions**.)</span><span class="sxs-lookup"><span data-stu-id="1276e-173">(To view the transaction lines, you might have to select the **Transactions** FastTab.)</span></span>

   <span data-ttu-id="1276e-174">[![Vérification que le même code de lettre de relance apparaît sur l’en-tête et les lignes](./media/Ignore-payments-creditmemos-4.PNG)](./media/Ignore-payments-creditmemos-4.PNG)</span><span class="sxs-lookup"><span data-stu-id="1276e-174">[![Verifying that the same collection letter code appears on the header and the lines](./media/Ignore-payments-creditmemos-4.PNG)](./media/Ignore-payments-creditmemos-4.PNG)</span></span>

    2. <span data-ttu-id="1276e-175">Dans le volet Actions, sélectionnez **Valider**.</span><span class="sxs-lookup"><span data-stu-id="1276e-175">On the Action Pane, select **Post**.</span></span>
    3. <span data-ttu-id="1276e-176">Dans le champ **Date de validation**, entrez **19/01/2021**.</span><span class="sxs-lookup"><span data-stu-id="1276e-176">In the **Posting date** field, enter **1/19/2021**.</span></span>

    <span data-ttu-id="1276e-177">Vous devez maintenant créer à nouveau des lettres de relance pour le client US-045.</span><span class="sxs-lookup"><span data-stu-id="1276e-177">You must now create collection letters again for customer US-045.</span></span>

9. <span data-ttu-id="1276e-178">Accédez à **Crédit et relances \> Lettre de relance \> Créer des lettres de relance** et procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="1276e-178">Go to **Credit and collections \> Collection letter \> Create collection letters**, and follow these steps:</span></span>

    1. <span data-ttu-id="1276e-179">Définissez les options **Facture** et **Avoir** sur **Oui**.</span><span class="sxs-lookup"><span data-stu-id="1276e-179">Set the **Invoice** and **Credit note** options to **Yes**.</span></span>

        <span data-ttu-id="1276e-180">Par défaut, le champ **Lettre de relance** doit être défini sur **Lettre de relance par client**.</span><span class="sxs-lookup"><span data-stu-id="1276e-180">By default, the **Collection letter** field should be set to **Collection per customer**.</span></span>

    2. <span data-ttu-id="1276e-181">Dans le champ **Date de la lettre de relance**, saisissez **23/01/2021**.</span><span class="sxs-lookup"><span data-stu-id="1276e-181">In the **Collection letter date** field, enter **1/23/2021**.</span></span>
    3. <span data-ttu-id="1276e-182">Sur le raccourci **Enregistrements à inclure**, sélectionnez **Filtre**, puis, dans le champ **Compte client**, ajoutez le client **US-045**.</span><span class="sxs-lookup"><span data-stu-id="1276e-182">On the **Records to include** FastTab, select **Filter**, and then, in the **Customer account** field, add customer **US-045**.</span></span>
    4. <span data-ttu-id="1276e-183">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="1276e-183">Select **OK**.</span></span>
    5. <span data-ttu-id="1276e-184">Sélectionnez **OK** pour créer des lettres de relance.</span><span class="sxs-lookup"><span data-stu-id="1276e-184">Select **OK** to create collection letters.</span></span>

10. <span data-ttu-id="1276e-185">Accédez à **Crédit et relances \> Lettre de relance \> Examiner et traiter les lettres de relance** et procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="1276e-185">Go to **Credit and collections \> Collection letter \> Review and process collection letters**, and follow these steps:</span></span>

    1. <span data-ttu-id="1276e-186">Notez que le code de lettre de relance sur l’en-tête est **Lettre de relance 1**.</span><span class="sxs-lookup"><span data-stu-id="1276e-186">Notice that the collection letter code on the header is **Collection letter 1**.</span></span> <span data-ttu-id="1276e-187">Cependant, le code sur les lignes de transaction est **Lettre de relance 2**.</span><span class="sxs-lookup"><span data-stu-id="1276e-187">However, the code on the transaction lines is **Collection letter 2**.</span></span>

   <span data-ttu-id="1276e-188">[![Vérifie que différents codes de lettre de relance apparaissent sur l’en-tête et sur les lignes](./media/Ignore-payments-creditmemos-5.PNG)](./media/Ignore-payments-creditmemos-5.PNG)</span><span class="sxs-lookup"><span data-stu-id="1276e-188">[![Verifies that different collection letter codes appear on the header and the lines](./media/Ignore-payments-creditmemos-5.PNG)](./media/Ignore-payments-creditmemos-5.PNG)</span></span>

  <span data-ttu-id="1276e-189">Les codes sont différents, car l’option **Ignorer les paiements et les avoirs lors du calcul du code de lettre de relance** est définie sur **Oui**.</span><span class="sxs-lookup"><span data-stu-id="1276e-189">The codes differ because the **Ignore payments and credit memos when calculating collection letter code** option is to **Yes**.</span></span>

  2. <span data-ttu-id="1276e-190">Ne validez pas cette lettre de relance.</span><span class="sxs-lookup"><span data-stu-id="1276e-190">Don't post this collection letter.</span></span>

11. <span data-ttu-id="1276e-191">Accédez à **Crédit et relances \> Paramétrage \> Paramètres de la comptabilité client**, puis, sur l’onglet **Recouvrement**, définissez l’option **Ignorer les paiements et les avoirs lors du calcul du code de lettre de relance** sur **Non**.</span><span class="sxs-lookup"><span data-stu-id="1276e-191">Go to **Credit and collections \> Setup \> Accounts receivable parameters**, and then, on the **Collections** tab, set the **Ignore payments and credit memos when calculating collection letter code** option to **No**.</span></span>

    <span data-ttu-id="1276e-192">[![Paramétrage de l’option Ignorer les paiements et les avoirs lors du calcul du code lettre de relance sur Non.](./media/Ignore-payments-creditmemos-6.PNG)](./media/Ignore-payments-creditmemos-6.PNG)</span><span class="sxs-lookup"><span data-stu-id="1276e-192">[![Setting the Ignore payments and credit memos when calculating collection letter code option to No](./media/Ignore-payments-creditmemos-6.PNG)](./media/Ignore-payments-creditmemos-6.PNG)</span></span>

    <span data-ttu-id="1276e-193">Vous devez maintenant créer à nouveau des lettres de relance pour le client US-045.</span><span class="sxs-lookup"><span data-stu-id="1276e-193">You must now create collection letters again for customer US-045.</span></span>

12. <span data-ttu-id="1276e-194">Accédez à **Crédit et relances \> Lettre de relance \> Créer des lettres de relance** et procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="1276e-194">Go to **Credit and collections \> Collection letter \> Create collection letters**, and follow these steps:</span></span>

    1. <span data-ttu-id="1276e-195">Définissez les options **Facture** et **Avoir** sur **Oui**.</span><span class="sxs-lookup"><span data-stu-id="1276e-195">Set the **Invoice** and **Credit note** options to **Yes**.</span></span>

        <span data-ttu-id="1276e-196">Par défaut, le champ **Lettre de relance** doit être défini sur **Lettre de relance par client**.</span><span class="sxs-lookup"><span data-stu-id="1276e-196">By default, the **Collection letter** field should be set to **Collection per customer**.</span></span>

    2. <span data-ttu-id="1276e-197">Dans le champ **Date de la lettre de relance**, saisissez **23/01/2021**.</span><span class="sxs-lookup"><span data-stu-id="1276e-197">In the **Collection letter date** field, enter **1/23/2021**.</span></span>
    3. <span data-ttu-id="1276e-198">Sur le raccourci **Enregistrements à inclure**, sélectionnez **Filtre**, puis, dans le champ **Compte client**, ajoutez le client **US-045**.</span><span class="sxs-lookup"><span data-stu-id="1276e-198">On the **Records to include** FastTab, select **Filter**, and then, in the **Customer account** field, add customer **US-045**.</span></span>
    4. <span data-ttu-id="1276e-199">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="1276e-199">Select **OK**.</span></span>
    5. <span data-ttu-id="1276e-200">Sélectionnez **OK** pour créer des lettres de relance.</span><span class="sxs-lookup"><span data-stu-id="1276e-200">Select **OK** to create collection letters.</span></span>

13. <span data-ttu-id="1276e-201">Accédez à **Crédit et relances \> Lettre de relance \> Examiner et traiter les lettres de relance** et notez que le code de la lettre de relance sur l’en-tête et les lignes de transaction est **Lettre de relance 2**.</span><span class="sxs-lookup"><span data-stu-id="1276e-201">Go to **Credit and collections \> Collection letter \> Review and process collection letters**, and notice that the collection letter code on both the header and the transaction lines is **Collection letter 2**.</span></span>

    <span data-ttu-id="1276e-202">[![Nouvel affichage. Le même code de lettre de relance apparaît sur l’en-tête et les lignes](./media/Ignore-payments-creditmemos-7.PNG)](./media/Ignore-payments-creditmemos-7.PNG)</span><span class="sxs-lookup"><span data-stu-id="1276e-202">[![Showing again that the same collection letter code appears on the header and the lines](./media/Ignore-payments-creditmemos-7.PNG)](./media/Ignore-payments-creditmemos-7.PNG)</span></span>

    <span data-ttu-id="1276e-203">Le même code s’affiche aux deux endroits, car l’option **Ignorer les paiements et les avoirs lors du calcul du code de lettre de relance** est maintenant définie sur **Non**.</span><span class="sxs-lookup"><span data-stu-id="1276e-203">The same code appears in both places because the **Ignore payments and credit memos when calculating collection letter code** option is now set to **No**.</span></span>
