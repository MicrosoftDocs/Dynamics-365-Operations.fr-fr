---
title: Créer une demande qui emploie un appel d'offre
description: Cette rubrique explique comment ajouter le prix et les informations sur le fournisseur à une demande d'achat à partir d'un processus d'appel d'offre.
author: mkirknel
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: PurchReqTableListPage, PurchReqCreate, PurchReqTable, PurchReqLineRelatedDocuments, EcoResCategorySingleLookup, PurchReqWorkflowDropDialog, WorkflowSubmitDialog, WorkflowStatus, WorkflowWorkItemActionDialog, WorkflowUserListLookup, PurchReqCopyRFQ, SysDataAreaSelectLookup, PurchRFQCaseTable, PurchRFQEditLines, PurchRFQReplyTable, UnitOfMeasureLookup
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: abe6745682030766eabcd4411121866c9d890be0
ms.sourcegitcommit: fcb27d6a46cd544feef34f6ec7607bdd46b0c12b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/18/2020
ms.locfileid: "3149621"
---
# <a name="create-a-requisition-that-uses-an-rfq"></a><span data-ttu-id="04bce-103">Créer une demande qui emploie un appel d'offre</span><span class="sxs-lookup"><span data-stu-id="04bce-103">Create a requisition that uses an RFQ</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="04bce-104">Cette rubrique explique comment ajouter le prix et les informations sur le fournisseur à une demande d'achat à partir d'un processus d'appel d'offre.</span><span class="sxs-lookup"><span data-stu-id="04bce-104">This topic explains how to add price and vendor information to a purchase requisition from an RFQ process.</span></span> <span data-ttu-id="04bce-105">L'exemple indiqué dans ce guide peut être utilisé dans la société fictive USMF, et vous devez être connecté en tant qu'Admin pour accomplir toutes les étapes.</span><span class="sxs-lookup"><span data-stu-id="04bce-105">The example shown in this guide can be used in the USMF demo data company, and you must be logged in as an Admin to complete all the steps.</span></span> <span data-ttu-id="04bce-106">Les tâches de ce guide seraient généralement effectuées par des professionnels de l'approvisionnement.</span><span class="sxs-lookup"><span data-stu-id="04bce-106">The tasks in this guide would typically be done by procurement professionals.</span></span>


## <a name="create-a-requisition"></a><span data-ttu-id="04bce-107">Créer une demande</span><span class="sxs-lookup"><span data-stu-id="04bce-107">Create a requisition</span></span>
1. <span data-ttu-id="04bce-108">Dans le volet de navigation allez dans **Modules > Approvisionnement > Demandes d'achat > Demandes d'achat préparées par moi**.</span><span class="sxs-lookup"><span data-stu-id="04bce-108">In the navigation pane, go to **Modules > Procurement and sourcing > Purchase requisitions > Purchase requisitions prepared by me**.</span></span>
2. <span data-ttu-id="04bce-109">Sélectionnez **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="04bce-109">Select **New**.</span></span>
3. <span data-ttu-id="04bce-110">Tapez une valeur dans le champ **Nom**.</span><span class="sxs-lookup"><span data-stu-id="04bce-110">In the **Name** field, type a value.</span></span>
4. <span data-ttu-id="04bce-111">Dans le champ **Date demandée**, entrez une date.</span><span class="sxs-lookup"><span data-stu-id="04bce-111">In the **Requested date** field, enter a date.</span></span>
5. <span data-ttu-id="04bce-112">Dans le champ **Date comptable**, entrez une date.</span><span class="sxs-lookup"><span data-stu-id="04bce-112">In the **Accounting date** field, enter a date.</span></span>
6. <span data-ttu-id="04bce-113">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="04bce-113">Select **OK**.</span></span>
7. <span data-ttu-id="04bce-114">Saisissez ou sélectionnez une valeur dans le champ **Motif**.</span><span class="sxs-lookup"><span data-stu-id="04bce-114">In the **Reason** field, enter or select a value.</span></span>
8. <span data-ttu-id="04bce-115">Sélectionnez **Ajouter la ligne**.</span><span class="sxs-lookup"><span data-stu-id="04bce-115">Select **Add line**.</span></span>
9. <span data-ttu-id="04bce-116">Dans le champ **Catégorie d'approvisionnement**, choisissez une catégorie dans l'arborescence, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="04bce-116">In the **Procurement category** field, select a category in the tree, and then select **OK**.</span></span>
10. <span data-ttu-id="04bce-117">Dans le champ **Nom du produit**, saisissez une valeur.</span><span class="sxs-lookup"><span data-stu-id="04bce-117">In the **Product name** field, type a value.</span></span>
11. <span data-ttu-id="04bce-118">Entrez un nombre dans le champ **Quantité**.</span><span class="sxs-lookup"><span data-stu-id="04bce-118">In the **Quantity** field, enter a number.</span></span>
12. <span data-ttu-id="04bce-119">Saisissez ou sélectionnez une valeur dans le champ **Unité**.</span><span class="sxs-lookup"><span data-stu-id="04bce-119">In the **Unit** field, enter or select a value.</span></span>
13. <span data-ttu-id="04bce-120">Sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="04bce-120">Select **Save**.</span></span>
14. <span data-ttu-id="04bce-121">Sélectionnez **Workflow** pour ouvrir la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="04bce-121">Select **Workflow** to open the drop dialog.</span></span>
15. <span data-ttu-id="04bce-122">Sélectionnez **Soumettre**.</span><span class="sxs-lookup"><span data-stu-id="04bce-122">Select **Submit**.</span></span>
16. <span data-ttu-id="04bce-123">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="04bce-123">Close the page.</span></span>
17. <span data-ttu-id="04bce-124">Sélectionnez **Soumettre**.</span><span class="sxs-lookup"><span data-stu-id="04bce-124">Select **Submit**.</span></span>

## <a name="reassign-a-workflow-task"></a><span data-ttu-id="04bce-125">Réaffecter une tâche de workflow</span><span class="sxs-lookup"><span data-stu-id="04bce-125">Reassign a workflow task</span></span>
<span data-ttu-id="04bce-126">La prochaine tâche consiste à créer un appel d'offre pour obtenir des offres des fournisseurs pour le produit.</span><span class="sxs-lookup"><span data-stu-id="04bce-126">The next task is to create an RFQ to get bids from vendors for the product.</span></span> <span data-ttu-id="04bce-127">Dans les données fictives de la société USMF, le workflow de demande est défini avec une règle de sorte que si un fournisseur n'est pas choisi, ou si le prix unitaire est 0 pour une ligne, une tâche est affectée à un travailleur spécifique pour créer un appel d'offre.</span><span class="sxs-lookup"><span data-stu-id="04bce-127">In USMF demo data, the requisition workflow is set up with a rule so that if a vendor is not selected, or the unit price is 0 for a line, a task is assigned to a specific worker to create an RFQ.</span></span> <span data-ttu-id="04bce-128">Pour poursuivre avec ce guide, vous devez attribuer à nouveau cette tâche à un autre utilisateur (vous-même).</span><span class="sxs-lookup"><span data-stu-id="04bce-128">To continue with this guide, you need to re-assign that task to another user (yourself).</span></span> <span data-ttu-id="04bce-129">Vous pouvez seulement le faire si vous êtes connecté en tant qu'Admin.</span><span class="sxs-lookup"><span data-stu-id="04bce-129">You can only do this if you are logged in as an Admin.</span></span>  

1. <span data-ttu-id="04bce-130">Sélectionnez **Workflow** pour ouvrir la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="04bce-130">Select **Workflow** to open the drop dialog.</span></span>
2. <span data-ttu-id="04bce-131">Sélectionnez **Afficher l'historique**.</span><span class="sxs-lookup"><span data-stu-id="04bce-131">Select **View history**.</span></span>
3. <span data-ttu-id="04bce-132">Actualisez la page.</span><span class="sxs-lookup"><span data-stu-id="04bce-132">Refresh the page.</span></span>
4. <span data-ttu-id="04bce-133">Développez la section **Détails du suivi**.</span><span class="sxs-lookup"><span data-stu-id="04bce-133">Expand the **Tracking details** section.</span></span>
5. <span data-ttu-id="04bce-134">Dans l'arborescence, choisissez la ligne qui commence par « Workflow de ligne activé le ».</span><span class="sxs-lookup"><span data-stu-id="04bce-134">In the tree, select the line that starts with "Line workflow activated on".</span></span>
6. <span data-ttu-id="04bce-135">Sélectionnez **Afficher les détails du flux de travail**.</span><span class="sxs-lookup"><span data-stu-id="04bce-135">Select **View workflow details**.</span></span>
7. <span data-ttu-id="04bce-136">Développez la section **Éléments de travail**.</span><span class="sxs-lookup"><span data-stu-id="04bce-136">Expand the **Work items** section.</span></span>
8. <span data-ttu-id="04bce-137">Sélectionnez **Réaffecter**.</span><span class="sxs-lookup"><span data-stu-id="04bce-137">Select **Reassign**.</span></span>
9. <span data-ttu-id="04bce-138">Dans le champ **Utilisateur**, sélectionnez **Admin**.</span><span class="sxs-lookup"><span data-stu-id="04bce-138">In the **User** field, select **Admin**.</span></span>
10. <span data-ttu-id="04bce-139">Sélectionnez **Réaffecter**.</span><span class="sxs-lookup"><span data-stu-id="04bce-139">Select **Reassign**.</span></span>
11. <span data-ttu-id="04bce-140">Fermez les deux pages.</span><span class="sxs-lookup"><span data-stu-id="04bce-140">Close the two pages.</span></span>

## <a name="create-an-rfq"></a><span data-ttu-id="04bce-141">Créer un appel d'offre</span><span class="sxs-lookup"><span data-stu-id="04bce-141">Create an RFQ</span></span>

1. <span data-ttu-id="04bce-142">Actualisez la page.</span><span class="sxs-lookup"><span data-stu-id="04bce-142">Refresh the page.</span></span>
2. <span data-ttu-id="04bce-143">Sélectionnez **Appel d'offre**.</span><span class="sxs-lookup"><span data-stu-id="04bce-143">Select **Request for quotation**.</span></span>
3. <span data-ttu-id="04bce-144">Dans le champ **Entité juridique acheteuse**, sélectionnez **USMF**.</span><span class="sxs-lookup"><span data-stu-id="04bce-144">In the **Buying legal entity** field, select **USMF**.</span></span> <span data-ttu-id="04bce-145">Vous devez choisir la même entité juridique qui celle de la ligne de demande.</span><span class="sxs-lookup"><span data-stu-id="04bce-145">You must select the same legal entity that's on the requisition line.</span></span>  
4. <span data-ttu-id="04bce-146">Dans la liste, marquer la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="04bce-146">In the list, mark the selected row.</span></span> <span data-ttu-id="04bce-147">Si vous avez plusieurs lignes sur votre demande d'achat, choisissez toutes les lignes que vous voulez ajouter à l'appel d'offre.</span><span class="sxs-lookup"><span data-stu-id="04bce-147">If you had multiple lines on your purchase requisition, select all the lines that you want to add to the RFQ.</span></span>  
5. <span data-ttu-id="04bce-148">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="04bce-148">Select **OK**.</span></span>
6. <span data-ttu-id="04bce-149">Actualisez la page.</span><span class="sxs-lookup"><span data-stu-id="04bce-149">Refresh the page.</span></span>
7. <span data-ttu-id="04bce-150">Vérifiez que le récapitulatif est ouvert, puis développez la section **Documents associés**.</span><span class="sxs-lookup"><span data-stu-id="04bce-150">Ensure that the FactBox is open, then expand the **Related documents** section.</span></span>
8. <span data-ttu-id="04bce-151">Cliquez sur le lien dans le champ **Appel d'offre** pour ouvrir l'appel d'offre qui vient d'être créé.</span><span class="sxs-lookup"><span data-stu-id="04bce-151">Select the link in the **Request for quotation** field to open the RFQ that was just created.</span></span>
9. <span data-ttu-id="04bce-152">Sélectionnez **En-tête**.</span><span class="sxs-lookup"><span data-stu-id="04bce-152">Select **Header**.</span></span>
10. <span data-ttu-id="04bce-153">Sélectionnez **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="04bce-153">Select **Add**.</span></span>
11. <span data-ttu-id="04bce-154">Dans le champ **Compte fournisseur**, saisissez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="04bce-154">In the **Vendor account** field, enter or select a value.</span></span>
12. <span data-ttu-id="04bce-155">Sélectionnez **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="04bce-155">Select **Add**.</span></span>
13. <span data-ttu-id="04bce-156">Dans le champ **Compte fournisseur**, saisissez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="04bce-156">In the **Vendor account** field, enter or select a value.</span></span>
14. <span data-ttu-id="04bce-157">Sélectionnez **Envoyer**.</span><span class="sxs-lookup"><span data-stu-id="04bce-157">Select **Send**.</span></span>
15. <span data-ttu-id="04bce-158">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="04bce-158">Select **OK**.</span></span>
16. <span data-ttu-id="04bce-159">Sélectionnez **Entrer une réponse**.</span><span class="sxs-lookup"><span data-stu-id="04bce-159">Select **Enter reply**.</span></span>
17. <span data-ttu-id="04bce-160">Dans le volet Actions, sélectionnez **Répondre**.</span><span class="sxs-lookup"><span data-stu-id="04bce-160">On the Action Pane, select **Reply**.</span></span>
18. <span data-ttu-id="04bce-161">Sélectionnez **Copier des données dans la réponse**.</span><span class="sxs-lookup"><span data-stu-id="04bce-161">Select **Copy data to reply**.</span></span> <span data-ttu-id="04bce-162">Cette opération copie des données, telles que la quantité et les dates, de l'appel d'offre à la réponse.</span><span class="sxs-lookup"><span data-stu-id="04bce-162">This copies data, such as the quantity and dates, from the RFQ to the reply.</span></span>  
19. <span data-ttu-id="04bce-163">Entrez un nombre dans le champ **Prix unitaire**.</span><span class="sxs-lookup"><span data-stu-id="04bce-163">In the **Unit price** field, enter a number.</span></span> <span data-ttu-id="04bce-164">C'est le prix que vous avez reçu du fournisseur.</span><span class="sxs-lookup"><span data-stu-id="04bce-164">This is the price that you've received from the vendor.</span></span> <span data-ttu-id="04bce-165">Vous pourriez également vouloir entrer des informations supplémentaires à partir du fournisseur.</span><span class="sxs-lookup"><span data-stu-id="04bce-165">You might also want to enter additional information from the vendor.</span></span>  
20. <span data-ttu-id="04bce-166">Sélectionner **Accepter**.</span><span class="sxs-lookup"><span data-stu-id="04bce-166">Select **Accept**.</span></span>
21. <span data-ttu-id="04bce-167">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="04bce-167">Select **OK**.</span></span>

## <a name="verify-that-vendor-and-price-have-been-transferred-to-the-requisition"></a><span data-ttu-id="04bce-168">Vérifiez que le prix et le fournisseur ont été transférés dans la demande.</span><span class="sxs-lookup"><span data-stu-id="04bce-168">Verify that vendor and price have been transferred to the requisition</span></span>
1. <span data-ttu-id="04bce-169">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="04bce-169">Close the page.</span></span>
2. <span data-ttu-id="04bce-170">Sélectionnez **Lignes**.</span><span class="sxs-lookup"><span data-stu-id="04bce-170">Select **Lines**.</span></span>
3. <span data-ttu-id="04bce-171">Sélectionnez **Informations associées**.</span><span class="sxs-lookup"><span data-stu-id="04bce-171">Select **Related information**.</span></span>
4. <span data-ttu-id="04bce-172">Sélectionnez **Demande d'achat**.</span><span class="sxs-lookup"><span data-stu-id="04bce-172">Select **Purchase requisition**.</span></span>
5. <span data-ttu-id="04bce-173">Choisissez la ligne qui a été transférée à l'appel d'offre.</span><span class="sxs-lookup"><span data-stu-id="04bce-173">Select the line that was transferred to the RFQ.</span></span> <span data-ttu-id="04bce-174">Vérifiez que le prix et le fournisseur ont été copiés dans la demande.</span><span class="sxs-lookup"><span data-stu-id="04bce-174">Verify that the price and vendor have been copied to the requisition.</span></span>  
6. <span data-ttu-id="04bce-175">Sélectionnez **Workflow** pour ouvrir la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="04bce-175">Select **Workflow** to open the drop dialog.</span></span>
7. <span data-ttu-id="04bce-176">Sélectionnez Terminer.</span><span class="sxs-lookup"><span data-stu-id="04bce-176">Select Complete.</span></span>
8. <span data-ttu-id="04bce-177">Sélectionnez la page.</span><span class="sxs-lookup"><span data-stu-id="04bce-177">Select the page.</span></span>
9. <span data-ttu-id="04bce-178">Sélectionnez Terminer.</span><span class="sxs-lookup"><span data-stu-id="04bce-178">Select Complete.</span></span>

