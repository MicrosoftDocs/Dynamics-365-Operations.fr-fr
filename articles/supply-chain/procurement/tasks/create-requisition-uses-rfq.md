---
title: Créer une demande qui emploie un appel d'offre
description: Ce guide montre comment ajouter le prix et les informations sur le fournisseur à une demande d'achat à partir d'un processus d'appel d'offre.
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
ms.openlocfilehash: 9d80f84c148ff26bf008a97b06098bfd18c9062d
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/01/2019
ms.locfileid: "1844151"
---
# <a name="create-a-requisition-that-uses-an-rfq"></a><span data-ttu-id="413cc-103">Créer une demande qui emploie un appel d'offre</span><span class="sxs-lookup"><span data-stu-id="413cc-103">Create a requisition that uses an RFQ</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="413cc-104">Ce guide montre comment ajouter le prix et les informations sur le fournisseur à une demande d'achat à partir d'un processus d'appel d'offre.</span><span class="sxs-lookup"><span data-stu-id="413cc-104">This guide shows how to add price and vendor information to a purchase requisition from an RFQ process.</span></span> <span data-ttu-id="413cc-105">L'exemple indiqué dans ce guide peut être utilisé dans la société fictive USMF, et vous devez être connecté en tant qu'Admin pour accomplir toutes les étapes.</span><span class="sxs-lookup"><span data-stu-id="413cc-105">The example shown in this guide can be used in the USMF demo data company, and you must be logged in as an Admin to complete all the steps.</span></span> <span data-ttu-id="413cc-106">Les tâches de ce guide seraient généralement effectuées par des professionnels de l'approvisionnement.</span><span class="sxs-lookup"><span data-stu-id="413cc-106">The tasks in this guide would typically be done by procurement professionals.</span></span>


## <a name="create-a-requisition"></a><span data-ttu-id="413cc-107">Créer une demande</span><span class="sxs-lookup"><span data-stu-id="413cc-107">Create a requisition</span></span>
1. <span data-ttu-id="413cc-108">Accédez à Approvisionnement > Demandes d'achat > Demandes d'achat préparées par moi.</span><span class="sxs-lookup"><span data-stu-id="413cc-108">Go to Procurement and sourcing > Purchase requisitions > Purchase requisitions prepared by me.</span></span>
2. <span data-ttu-id="413cc-109">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="413cc-109">Click New.</span></span>
3. <span data-ttu-id="413cc-110">Tapez une valeur dans le champ Nom.</span><span class="sxs-lookup"><span data-stu-id="413cc-110">In the Name field, type a value.</span></span>
4. <span data-ttu-id="413cc-111">Dans le champ Date demandée, entrez une date.</span><span class="sxs-lookup"><span data-stu-id="413cc-111">In the Requested date field, enter a date.</span></span>
5. <span data-ttu-id="413cc-112">Dans le champ Comptabilité, entrez une date.</span><span class="sxs-lookup"><span data-stu-id="413cc-112">In the Accounting date field, enter a date.</span></span>
6. <span data-ttu-id="413cc-113">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="413cc-113">Click OK.</span></span>
7. <span data-ttu-id="413cc-114">Dans le champ Motif, saisissez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="413cc-114">In the Reason field, enter or select a value.</span></span>
8. <span data-ttu-id="413cc-115">Cliquez sur Ajouter une ligne.</span><span class="sxs-lookup"><span data-stu-id="413cc-115">Click Add line.</span></span>
9. <span data-ttu-id="413cc-116">Dans le champ Catégorie d'approvisionnement, choisissez une catégorie dans l'arborescence, puis cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="413cc-116">In the Procurement category field, select a category in the tree, and then click OK.</span></span>
10. <span data-ttu-id="413cc-117">Dans le champ Produit, saisissez une valeur.</span><span class="sxs-lookup"><span data-stu-id="413cc-117">In the Product name field, type a value.</span></span>
11. <span data-ttu-id="413cc-118">Dans le champ Quantité, entrer un numéro.</span><span class="sxs-lookup"><span data-stu-id="413cc-118">In the Quantity field, enter a number.</span></span>
12. <span data-ttu-id="413cc-119">Saisissez ou sélectionnez une valeur dans le champ Unité.</span><span class="sxs-lookup"><span data-stu-id="413cc-119">In the Unit field, enter or select a value.</span></span>
13. <span data-ttu-id="413cc-120">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="413cc-120">Click Save.</span></span>
14. <span data-ttu-id="413cc-121">Cliquer sur Workflow pour ouvrir la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="413cc-121">Click Workflow to open the drop dialog.</span></span>
15. <span data-ttu-id="413cc-122">Cliquez sur Soumettre.</span><span class="sxs-lookup"><span data-stu-id="413cc-122">Click Submit.</span></span>
16. <span data-ttu-id="413cc-123">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="413cc-123">Close the page.</span></span>
17. <span data-ttu-id="413cc-124">Cliquez sur Soumettre.</span><span class="sxs-lookup"><span data-stu-id="413cc-124">Click Submit.</span></span>

## <a name="reassign-a-workflow-task"></a><span data-ttu-id="413cc-125">Réaffecter une tâche de workflow</span><span class="sxs-lookup"><span data-stu-id="413cc-125">Reassign a workflow task</span></span>
    * <span data-ttu-id="413cc-126">La prochaine tâche consiste à créer un appel d'offre pour obtenir des offres des fournisseurs pour le produit.</span><span class="sxs-lookup"><span data-stu-id="413cc-126">The next task is to create an RFQ to get bids from vendors for the product.</span></span> <span data-ttu-id="413cc-127">Dans les données fictives de la société USMF, le workflow de demande est défini avec une règle de sorte que si un fournisseur n'est pas choisi, ou si le prix unitaire est 0 pour une ligne, une tâche est affectée à un travailleur spécifique pour créer un appel d'offre.</span><span class="sxs-lookup"><span data-stu-id="413cc-127">In USMF demo data, the requisition workflow is set up with a rule so that if a vendor is not selected, or the unit price is 0 for a line, a task is assigned to a specific worker to create an RFQ.</span></span> <span data-ttu-id="413cc-128">Pour poursuivre avec ce guide, vous devez attribuer à nouveau cette tâche à un autre utilisateur (vous-même).</span><span class="sxs-lookup"><span data-stu-id="413cc-128">To continue with this guide, you need to re-assign that task to another user (yourself).</span></span> <span data-ttu-id="413cc-129">Vous pouvez seulement le faire si vous êtes connecté en tant qu'Admin.</span><span class="sxs-lookup"><span data-stu-id="413cc-129">You can only do this if you are logged in as an Admin.</span></span>  
1. <span data-ttu-id="413cc-130">Cliquer sur Workflow pour ouvrir la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="413cc-130">Click Workflow to open the drop dialog.</span></span>
2. <span data-ttu-id="413cc-131">Cliquez sur Afficher l'historique.</span><span class="sxs-lookup"><span data-stu-id="413cc-131">Click View history.</span></span>
3. <span data-ttu-id="413cc-132">Actualisez la page.</span><span class="sxs-lookup"><span data-stu-id="413cc-132">Refresh the page.</span></span>
4. <span data-ttu-id="413cc-133">Développez la section Détails du suivi.</span><span class="sxs-lookup"><span data-stu-id="413cc-133">Expand the Tracking details section.</span></span>
5. <span data-ttu-id="413cc-134">Dans l'arborescence, choisissez la ligne qui commence par « Workflow de ligne activé le ».</span><span class="sxs-lookup"><span data-stu-id="413cc-134">In the tree, select 'the line that starts with “Line workflow activated on”'.</span></span>
6. <span data-ttu-id="413cc-135">Cliquez sur Afficher les détails du workflow.</span><span class="sxs-lookup"><span data-stu-id="413cc-135">Click View workflow details.</span></span>
7. <span data-ttu-id="413cc-136">Développez la section Éléments de travail.</span><span class="sxs-lookup"><span data-stu-id="413cc-136">Expand the Work items section.</span></span>
8. <span data-ttu-id="413cc-137">Cliquez sur Réaffecter.</span><span class="sxs-lookup"><span data-stu-id="413cc-137">Click Reassign.</span></span>
9. <span data-ttu-id="413cc-138">Dans le champ Utilisateur, sélectionnez Admin.</span><span class="sxs-lookup"><span data-stu-id="413cc-138">In the User field, select Admin.</span></span>
10. <span data-ttu-id="413cc-139">Cliquez sur Réaffecter.</span><span class="sxs-lookup"><span data-stu-id="413cc-139">Click Reassign.</span></span>
11. <span data-ttu-id="413cc-140">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="413cc-140">Close the page.</span></span>
12. <span data-ttu-id="413cc-141">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="413cc-141">Close the page.</span></span>

## <a name="create-an-rfq"></a><span data-ttu-id="413cc-142">Créer un appel d'offre</span><span class="sxs-lookup"><span data-stu-id="413cc-142">Create an RFQ</span></span>
1. <span data-ttu-id="413cc-143">Actualisez la page.</span><span class="sxs-lookup"><span data-stu-id="413cc-143">Refresh the page.</span></span>
2. <span data-ttu-id="413cc-144">Cliquez sur Réponse de l'appel d'offre.</span><span class="sxs-lookup"><span data-stu-id="413cc-144">Click Request for quotation.</span></span>
3. <span data-ttu-id="413cc-145">Sélectionnez USMF dans le champ Entité juridique acheteuse.</span><span class="sxs-lookup"><span data-stu-id="413cc-145">In the Buying legal entity field, select USMF.</span></span>
    * <span data-ttu-id="413cc-146">Vous devez choisir la même entité juridique qui celle de la ligne de demande.</span><span class="sxs-lookup"><span data-stu-id="413cc-146">You must select the same legal entity that’s on the requisition line.</span></span>  
4. <span data-ttu-id="413cc-147">Dans la liste, marquez la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="413cc-147">In the list, mark the selected row.</span></span>
    * <span data-ttu-id="413cc-148">Si vous avez plusieurs lignes sur votre demande d'achat, choisissez toutes les lignes que vous voulez ajouter à l'appel d'offre.</span><span class="sxs-lookup"><span data-stu-id="413cc-148">If you had multiple lines on your purchase requisition, select all the lines that you want to add to the RFQ.</span></span>  
5. <span data-ttu-id="413cc-149">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="413cc-149">Click OK.</span></span>
6. <span data-ttu-id="413cc-150">Actualisez la page.</span><span class="sxs-lookup"><span data-stu-id="413cc-150">Refresh the page.</span></span>
7. <span data-ttu-id="413cc-151">Ouvrez le Récapitulatif, puis augmentez la section Documents associés.</span><span class="sxs-lookup"><span data-stu-id="413cc-151">Open the FactBox and then expand the Related documents section.</span></span>
    * <span data-ttu-id="413cc-152">Le Récapitulatif est peut-être déjà ouvert.</span><span class="sxs-lookup"><span data-stu-id="413cc-152">You may already have the FactBox open.</span></span> <span data-ttu-id="413cc-153">Recherchez l'icône dotée d'une flèche, à droite des boutons à bascule Lignes/En-tête.</span><span class="sxs-lookup"><span data-stu-id="413cc-153">Look for the icon with an arrow on it, to the right of the Lines/Header toggle buttons.</span></span> <span data-ttu-id="413cc-154">Si la flèche pointe vers la droite, le récapitulatif est déjà ouvert.</span><span class="sxs-lookup"><span data-stu-id="413cc-154">If the arrow is pointing to the right, the FactBox is already open.</span></span> <span data-ttu-id="413cc-155">Si la flèche pointe vers la gauche, cliquez sur le récapitulatif pour l'ouvrir.</span><span class="sxs-lookup"><span data-stu-id="413cc-155">If the arrow points to the left, click it to open the FactBox.</span></span>  
8. <span data-ttu-id="413cc-156">Cliquez sur le lien dans le champ Appel d'offre pour ouvrir l'appel d'offre qui vient d'être créé.</span><span class="sxs-lookup"><span data-stu-id="413cc-156">Click the link in the Request for quotation field to open the RFQ that was just created.</span></span>
9. <span data-ttu-id="413cc-157">Cliquez sur En-tête.</span><span class="sxs-lookup"><span data-stu-id="413cc-157">Click Header.</span></span>
10. <span data-ttu-id="413cc-158">Cliquez sur Ajouter.</span><span class="sxs-lookup"><span data-stu-id="413cc-158">Click Add.</span></span>
11. <span data-ttu-id="413cc-159">Dans le champ Compte fournisseur, saisissez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="413cc-159">In the Vendor account field, enter or select a value.</span></span>
12. <span data-ttu-id="413cc-160">Cliquez sur Ajouter.</span><span class="sxs-lookup"><span data-stu-id="413cc-160">Click Add.</span></span>
13. <span data-ttu-id="413cc-161">Dans le champ Compte fournisseur, saisissez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="413cc-161">In the Vendor account field, enter or select a value.</span></span>
14. <span data-ttu-id="413cc-162">Cliquez sur Envoyer.</span><span class="sxs-lookup"><span data-stu-id="413cc-162">Click Send.</span></span>
15. <span data-ttu-id="413cc-163">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="413cc-163">Click OK.</span></span>
16. <span data-ttu-id="413cc-164">Cliquez sur Entrer une réponse.</span><span class="sxs-lookup"><span data-stu-id="413cc-164">Click Enter reply.</span></span>
17. <span data-ttu-id="413cc-165">Cliquez sur Répondre dans le volet Actions.</span><span class="sxs-lookup"><span data-stu-id="413cc-165">On the Action Pane, click Reply.</span></span>
18. <span data-ttu-id="413cc-166">Cliquez sur Copier des données dans la réponse.</span><span class="sxs-lookup"><span data-stu-id="413cc-166">Click Copy data to reply.</span></span>
    * <span data-ttu-id="413cc-167">Cette opération copie des données, telles que la quantité et les dates, de l'appel d'offre à la réponse.</span><span class="sxs-lookup"><span data-stu-id="413cc-167">This copies data, such as the quantity and dates, from the RFQ to the reply .</span></span>  
19. <span data-ttu-id="413cc-168">Entrez un nombre dans le champ Prix unitaire.</span><span class="sxs-lookup"><span data-stu-id="413cc-168">In the Unit price field, enter a number.</span></span>
    * <span data-ttu-id="413cc-169">C'est le prix que vous avez reçu du fournisseur.</span><span class="sxs-lookup"><span data-stu-id="413cc-169">This is the price that you’ve received from the vendor.</span></span> <span data-ttu-id="413cc-170">Vous pourriez également vouloir entrer des informations supplémentaires à partir du fournisseur.</span><span class="sxs-lookup"><span data-stu-id="413cc-170">You might also want to enter additional information from the vendor.</span></span>  
20. <span data-ttu-id="413cc-171">Cliquez sur Accepter.</span><span class="sxs-lookup"><span data-stu-id="413cc-171">Click Accept.</span></span>
21. <span data-ttu-id="413cc-172">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="413cc-172">Click OK.</span></span>

## <a name="verify-that-vendor-and-price-have-been-transferred-to-the-requisition"></a><span data-ttu-id="413cc-173">Vérifiez que le prix et le fournisseur ont été transférés dans la demande.</span><span class="sxs-lookup"><span data-stu-id="413cc-173">Verify that vendor and price have been transferred to the requisition</span></span>
1. <span data-ttu-id="413cc-174">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="413cc-174">Close the page.</span></span>
2. <span data-ttu-id="413cc-175">Cliquez sur Lignes.</span><span class="sxs-lookup"><span data-stu-id="413cc-175">Click Lines.</span></span>
3. <span data-ttu-id="413cc-176">Cliquez sur Informations associées.</span><span class="sxs-lookup"><span data-stu-id="413cc-176">Click Related information.</span></span>
4. <span data-ttu-id="413cc-177">Cliquez sur Demande d'achat.</span><span class="sxs-lookup"><span data-stu-id="413cc-177">Click Purchase requisition.</span></span>
5. <span data-ttu-id="413cc-178">Choisissez la ligne qui a été transférée à l'appel d'offre.</span><span class="sxs-lookup"><span data-stu-id="413cc-178">Select the line that was transferred to the RFQ.</span></span>
    * <span data-ttu-id="413cc-179">Vérifiez que le prix et le fournisseur ont été copiés dans la demande.</span><span class="sxs-lookup"><span data-stu-id="413cc-179">Verify that the price and vendor have been copied to the requisition.</span></span>  
6. <span data-ttu-id="413cc-180">Cliquer sur Workflow pour ouvrir la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="413cc-180">Click Workflow to open the drop dialog.</span></span>
7. <span data-ttu-id="413cc-181">Cliquez sur Terminé.</span><span class="sxs-lookup"><span data-stu-id="413cc-181">Click Complete.</span></span>
8. <span data-ttu-id="413cc-182">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="413cc-182">Close the page.</span></span>
9. <span data-ttu-id="413cc-183">Cliquez sur Terminé.</span><span class="sxs-lookup"><span data-stu-id="413cc-183">Click Complete.</span></span>

