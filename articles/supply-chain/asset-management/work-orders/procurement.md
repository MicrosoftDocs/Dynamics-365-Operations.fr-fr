---
title: Approvisionnement
description: Cette rubrique explique l'approvisionnement dans le module Gestion des actifs.
author: josaw1
manager: tfehr
ms.date: 10/15/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EntAssetWorkOrderPurchaseListPagePreviewPane, EntAssetWorkOrderPurchaseListPage, EntAssetWorkOrderPurchaseLineAmountInfoPart, EntAssetWorkOrderPurchReqListPage
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2019-09-30
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 552b1b211460ae86af06e183af91c062a3ee569a
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4428084"
---
# <a name="procurement"></a><span data-ttu-id="0e53a-103">Approvisionnement</span><span class="sxs-lookup"><span data-stu-id="0e53a-103">Procurement</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="0e53a-104">Dans le module Gestion des actifs, vous pouvez obtenir une vue d'ensemble des demandes d'achat et des commandes fournisseur associées aux ordres de travail.</span><span class="sxs-lookup"><span data-stu-id="0e53a-104">In Asset Management, you can get an overview of purchase requisitions and purchase orders that are related to work orders.</span></span> <span data-ttu-id="0e53a-105">Il est également possible de créer une commande fournisseur ou une demande d'achat depuis un ordre de travail.</span><span class="sxs-lookup"><span data-stu-id="0e53a-105">You can also create a purchase order or a purchase requisition from a work order.</span></span>

<span data-ttu-id="0e53a-106">La page de liste **Demande d'achat de l'ordre de travail** (**Gestion des actifs** > **Commun** > **Approvisionnement** > **Demande d'achat de l'ordre de travail**) affiche une liste des demandes d'achat associées aux ordres de travail.</span><span class="sxs-lookup"><span data-stu-id="0e53a-106">The **Work order purchase requisition** list page (**Asset management** > **Common** > **Procurement** > **Work order purchase requisition**) shows a list of purchase requisitions that are related to work orders.</span></span> <span data-ttu-id="0e53a-107">Lorsque vous sélectionnez une tâche d'ordre de travail dans cette page, vous pouvez utiliser les boutons du groupe **Afficher** sous l'onglet du volet d'action **Demande d'achat d'ordres de travail** pour exécuter différentes actions :</span><span class="sxs-lookup"><span data-stu-id="0e53a-107">When you select a work order job on this page, you can use the buttons in the **Show** group on the **Work order purchase requisition** Action Pane tab to perform various actions:</span></span>

- <span data-ttu-id="0e53a-108">Pour ouvrir la demande d'achat associée, sélectionnez **Demande d'achat**.</span><span class="sxs-lookup"><span data-stu-id="0e53a-108">To open the related purchase requisition, select **Purchase requisition**.</span></span> 
- <span data-ttu-id="0e53a-109">Pour ouvrir l'ordre de travail associé, sélectionnez **Ordre de travail**.</span><span class="sxs-lookup"><span data-stu-id="0e53a-109">To open the related work order, select **Work order**.</span></span>
- <span data-ttu-id="0e53a-110">Pour avoir une vue d'ensemble de l'emplacement d'utilisation de l'article sur la ligne sélectionnée, en ce qui concerne les actifs, les valeurs par défaut du type de tâche de maintenance, les pièces détachées et les ordres de travail dans Gestion des actifs, sélectionnez **Cas d'emploi d'article**.</span><span class="sxs-lookup"><span data-stu-id="0e53a-110">To get an overview that shows where the item on the selected line is used in relation to assets, maintenance job type defaults, spare parts, and work orders in Asset Management, select **Item where used**.</span></span> <span data-ttu-id="0e53a-111">Pour plus d'informations sur cette vue d'ensemble, voir [Cas d'emploi d'article](../controlling-and-reporting/item-where-used.md).</span><span class="sxs-lookup"><span data-stu-id="0e53a-111">For more information about this overview, see [Item where used](../controlling-and-reporting/item-where-used.md).</span></span>

<span data-ttu-id="0e53a-112">L'illustration suivante présente un exemple de la liste de page **Demande d'achat de l'ordre de travail**.</span><span class="sxs-lookup"><span data-stu-id="0e53a-112">The illustration below shows an example of the **Work order purchase requisition** list page.</span></span>

![Figure 1](media/08-work-orders.png)


<span data-ttu-id="0e53a-114">La page de liste **Achats de l'ordre de travail** (**Gestion des actifs** > **Commun** > **Approvisionnement** > **Achats de l'ordre de travail**) affiche une liste des commandes fournisseur associées aux ordres de travail.</span><span class="sxs-lookup"><span data-stu-id="0e53a-114">The **Work order purchase** list page (**Asset management** > **Common** > **Procurement** > **Work order purchase**) shows a list of purchase orders that are related to work orders.</span></span> <span data-ttu-id="0e53a-115">Lorsque vous sélectionnez une tâche d'ordre de travail dans cette page, vous pouvez utiliser les boutons du groupe **Afficher** sous l'onglet du volet d'action **Achats d'ordres de travail** pour exécuter différentes actions :</span><span class="sxs-lookup"><span data-stu-id="0e53a-115">When you select a work order job on this page, you can use the buttons in the **Show** group on the **Work order purchase** tab of the Action Pane to perform various actions:</span></span>

- <span data-ttu-id="0e53a-116">Pour ouvrir la commande fournisseur associée, sélectionnez **Commande fournisseur**.</span><span class="sxs-lookup"><span data-stu-id="0e53a-116">To open the related purchase order, select **Purchase order**.</span></span> 
- <span data-ttu-id="0e53a-117">Pour ouvrir l'ordre de travail associé, sélectionnez **Ordre de travail**.</span><span class="sxs-lookup"><span data-stu-id="0e53a-117">To open the related work order, select **Work order**.</span></span>
- <span data-ttu-id="0e53a-118">Pour avoir une vue d'ensemble de l'emplacement d'utilisation de l'article sur la ligne sélectionnée, en ce qui concerne les actifs, les valeurs par défaut du type de tâche de maintenance, les pièces détachées et les ordres de travail dans Gestion des actifs, sélectionnez **Cas d'emploi d'article**.</span><span class="sxs-lookup"><span data-stu-id="0e53a-118">To get an overview that shows where the item on the selected line is used in relation to assets, maintenance job type defaults, spare parts, and work orders in Asset Management, select **Item where used**.</span></span> <span data-ttu-id="0e53a-119">Pour plus d'informations sur cette vue d'ensemble, voir [Cas d'emploi d'article](../controlling-and-reporting/item-where-used.md).</span><span class="sxs-lookup"><span data-stu-id="0e53a-119">For more information about this overview, see [Item where used](../controlling-and-reporting/item-where-used.md).</span></span>

<span data-ttu-id="0e53a-120">L'illustration suivante présente un exemple de la liste de page **Achats de l'ordre de travail**.</span><span class="sxs-lookup"><span data-stu-id="0e53a-120">The illustration below shows an example of the **Work order purchase** list page.</span></span>

![Figure 2](media/09-work-orders.png)


<span data-ttu-id="0e53a-122">Sur la page de liste **Achats de l'ordre de travail** et la page de liste **Demande d'achat de l'ordre de travail**, un symbole lié au contrôle de la date de livraison s'affiche à droite de chaque ligne.</span><span class="sxs-lookup"><span data-stu-id="0e53a-122">On both the **Work order purchase** list page and the **Work order purchase requisition** list page, a symbol that is related to delivery date control appears on the right side of each line.</span></span> <span data-ttu-id="0e53a-123">Si le symbole est un point d'exclamation dans un cercle rouge, la livraison de la commande fournisseur ou de la demande d'achat associée peut être retardée.</span><span class="sxs-lookup"><span data-stu-id="0e53a-123">If the symbol is an exclamation point in a red circle, delivery of the related purchase order or purchase requisition might be delayed.</span></span>

<span data-ttu-id="0e53a-124">Pour une commande fournisseur, la date associée à la ligne de commande fournisseur est utilisée pour calculer un retard possible.</span><span class="sxs-lookup"><span data-stu-id="0e53a-124">For a purchase order, the date that is related to the purchase order line is used to calculate a possible delay.</span></span> <span data-ttu-id="0e53a-125">Pour afficher cette date, sur la page **Commande fournisseur**, sélectionnez la ligne de commande fournisseur.</span><span class="sxs-lookup"><span data-stu-id="0e53a-125">To view this date, on the **Purchase order** page, select the purchase order line.</span></span> <span data-ttu-id="0e53a-126">La date est affichée dans le champ **Date de livraison confirmée** sur l'onglet **Paramétrage** de l'organisateur **Détails de ligne**.</span><span class="sxs-lookup"><span data-stu-id="0e53a-126">The date is shown in the **Confirmed delivery date** field on the **Setup** tab of the **Line details** FastTab.</span></span> <span data-ttu-id="0e53a-127">Si le champ **Date de livraison confirmée** n'est pas défini, la date dans le champ **Date de livraison** sur l'organisateur **En-tête de commande fournisseur** est utilisée pour le calcul.</span><span class="sxs-lookup"><span data-stu-id="0e53a-127">If the **Confirmed delivery date** field isn't set, the date in the **Delivery date** field on the **Purchase order header** FastTab is used for the calculation.</span></span> <span data-ttu-id="0e53a-128">Une de ces dates est comparée à la date disponible sur l'ordre de travail ou à la tâche de l'ordre de travail dans l'ordre suivant :</span><span class="sxs-lookup"><span data-stu-id="0e53a-128">One of those dates is compared to the available date on the work order or work order job, in the following order:</span></span>

1. <span data-ttu-id="0e53a-129">Date de début réelle sur l'ordre de travail</span><span class="sxs-lookup"><span data-stu-id="0e53a-129">Actual start date on the work order</span></span>  

2. <span data-ttu-id="0e53a-130">Date de début prévue sur la tâche de l'ordre de travail associée</span><span class="sxs-lookup"><span data-stu-id="0e53a-130">Scheduled start date on the related work order job</span></span> 

3. <span data-ttu-id="0e53a-131">Date de début planifiée sur l'ordre de travail</span><span class="sxs-lookup"><span data-stu-id="0e53a-131">Scheduled start date on the work order</span></span> 

4. <span data-ttu-id="0e53a-132">Date de début prévue sur l'ordre de travail, ou</span><span class="sxs-lookup"><span data-stu-id="0e53a-132">Expected start date on the work order</span></span> 

<span data-ttu-id="0e53a-133">Pour une demande d'achat, la date du champ **Date demandée** sur l'organisateur **En-tête de demande d'achat** de la page **Demandes d'achat** est utilisée pour calculer un retard possible.</span><span class="sxs-lookup"><span data-stu-id="0e53a-133">For a purchase requisition, the date in the **Requested date** field on the **Purchase requisition header** FastTab of the **Purchase requisitions** page is used to calculate a possible delay.</span></span> <span data-ttu-id="0e53a-134">La date de ce champ est comparée à la date disponible sur l'ordre de travail ou à la tâche de l'ordre de travail dans le même ordre que celui utilisé pour une commande fournisseur.</span><span class="sxs-lookup"><span data-stu-id="0e53a-134">The date in that field is compared to the available date on the work order or work order job, in the same order that is used for a purchase order.</span></span>


## <a name="create-a-purchase-order-from-a-work-order"></a><span data-ttu-id="0e53a-135">Création d'une commande fournisseur à partir d'un ordre de travail</span><span class="sxs-lookup"><span data-stu-id="0e53a-135">Create a purchase order from a work order</span></span>

<span data-ttu-id="0e53a-136">Sur la page de liste **Tous les ordres de travail**, vous pouvez sélectionner une tâche de l'ordre de travail, puis créer une commande fournisseur ou une demande d'achat associée.</span><span class="sxs-lookup"><span data-stu-id="0e53a-136">On the **All work orders** list page, you can select a work order job, and then create a related purchase order or a related purchase requisition.</span></span> <span data-ttu-id="0e53a-137">Ainsi, vous garantissez que des relations de projet existent entre la commande fournisseur ou la demande d'achat et l'ordre de travail.</span><span class="sxs-lookup"><span data-stu-id="0e53a-137">In this way, you help guarantee that project relations exist between the purchase order or purchase requisition and the work order.</span></span>

1. <span data-ttu-id="0e53a-138">Sélectionnez **Gestion des actifs** > **Commun** > **Ordre de travail** > **Tous les ordres de travail** ou **Ordres de travail actifs**.</span><span class="sxs-lookup"><span data-stu-id="0e53a-138">Select **Asset management** > **Common** > **Work orders** > **All work orders** or **Active work orders**.</span></span>

2. <span data-ttu-id="0e53a-139">Sélectionnez l'ordre de travail pour lequel créer une commande fournisseur, puis sélectionnez **Modifier**.</span><span class="sxs-lookup"><span data-stu-id="0e53a-139">Select the work order to create a purchase order for, and then select **Edit**.</span></span>

3. <span data-ttu-id="0e53a-140">Sur l'organisateur **Tâches de maintenance de l'ordre de travail**, sélectionnez la tâche de l'ordre de travail pour laquelle créer la commande fournisseur.</span><span class="sxs-lookup"><span data-stu-id="0e53a-140">On the **Work order maintenance jobs** FastTab, select the work order job to create the purchase order for.</span></span>

4. <span data-ttu-id="0e53a-141">Sélectionnez **Tâches d'article** > **Commande fournisseur de la tâche de l'ordre de travail**.</span><span class="sxs-lookup"><span data-stu-id="0e53a-141">Select **Item tasks** > **Purchase order from work order job**.</span></span>

5. <span data-ttu-id="0e53a-142">Sur la page de liste **Commandes fournisseur de projet**, cliquez sur **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="0e53a-142">On the **Project purchase orders** list page, click **New**.</span></span>

6. <span data-ttu-id="0e53a-143">Créez la commande fournisseur.</span><span class="sxs-lookup"><span data-stu-id="0e53a-143">Create the purchase order.</span></span>

>[!NOTE]
><span data-ttu-id="0e53a-144">Pour créer une demande d'achat associée, suivez les mêmes étapes.</span><span class="sxs-lookup"><span data-stu-id="0e53a-144">To create a related purchase requisition, follow the same steps.</span></span> <span data-ttu-id="0e53a-145">Toutefois, sélectionnez **Tâches d'article** > **Demande d'achat de la tâche de l'ordre de travail** à l'étape 4.</span><span class="sxs-lookup"><span data-stu-id="0e53a-145">However, select **Item tasks** > **Purchase requisition from work order job** in step 4.</span></span>


## <a name="project-relation-between-work-order-and-purchase-order-or-purchase-requisition"></a><span data-ttu-id="0e53a-146">Relation de projet entre l'ordre de travail et la commande fournisseur ou la demande d'achat</span><span class="sxs-lookup"><span data-stu-id="0e53a-146">Project relation between work order and purchase order or purchase requisition</span></span>

<span data-ttu-id="0e53a-147">Une ligne de commande fournisseur ou une ligne de demande d'achat est associée à une tâche de l'ordre de travail via le projet de l'ordre de travail et le numéro d'activité de projet associé.</span><span class="sxs-lookup"><span data-stu-id="0e53a-147">A purchase order line or purchase requisition line is related to a work order job via the work order project and the related project activity number.</span></span> <span data-ttu-id="0e53a-148">Lorsque vous créez une commande fournisseur ou une demande d'achat d'une tâche de l'ordre de travail, le numéro d'activité de projet associé est obligatoire.</span><span class="sxs-lookup"><span data-stu-id="0e53a-148">When you create a purchase order or purchase requisition from a work order job, the related project activity number is mandatory.</span></span> <span data-ttu-id="0e53a-149">Si toutes les tâches d'ordre de travail de l'ordre de travail associé contiennent le même type de tâche de maintenance, le numéro d'activité de projet est automatiquement entré sur la commande fournisseur ou la demande d'achat.</span><span class="sxs-lookup"><span data-stu-id="0e53a-149">If all the work order jobs in the related work order have the same maintenance job type, the project activity number is automatically entered on the purchase order or purchase requisition.</span></span> <span data-ttu-id="0e53a-150">Si les tâches d'ordre de travail ont des types de tâches de maintenance différents, vous devez entrer manuellement le numéro d'activité de projet sur la commande fournisseur ou la demande d'achat.</span><span class="sxs-lookup"><span data-stu-id="0e53a-150">If the work order jobs have different maintenance job types, you must manually enter the project activity number on the purchase order or purchase requisition.</span></span>

<span data-ttu-id="0e53a-151">Pour afficher ou entrer le numéro d'activité associé à une ligne de commande fournisseur, sur la page de liste **Journal des ordres de travail**, sélectionnez l'enregistrement de commande fournisseur, puis, dans la colonne **Commande fournisseur**, sélectionnez le lien vers la commande fournisseur.</span><span class="sxs-lookup"><span data-stu-id="0e53a-151">To view or enter the activity number that is related to a purchase order line, on the **Work order purchase** list page, select the purchase order record, and then, in the **Purchase order** column, select the link for the purchase order.</span></span> <span data-ttu-id="0e53a-152">Vous pouvez trouver le champ **Numéro d'activité** sur l'onglet **Projet** de l'organisateur **Détails de ligne**.</span><span class="sxs-lookup"><span data-stu-id="0e53a-152">You can find the **Activity number** field on the **Project** tab of the **Line details** FastTab.</span></span>

<span data-ttu-id="0e53a-153">L'illustration suivante présente un exemple de la page **Commande fournisseur**, avec un focus sur le **Numéro d'activité**.</span><span class="sxs-lookup"><span data-stu-id="0e53a-153">The illustration below shows an example of the **Purchase order** page, with focus on the **Activity number**.</span></span>

![Figure 3](media/10-work-orders.png)

<span data-ttu-id="0e53a-155">De même, pour afficher ou entrer le numéro d'activité associé à une ligne de demande d'achat d'ordre de travail, sur la page de liste **Demande d'achat d'ordre de travail**, sélectionnez l'enregistrement de la demande d'achat, puis, dans la colonne **Demande d'achat**, sélectionnez le lien vers la demande d'achat.</span><span class="sxs-lookup"><span data-stu-id="0e53a-155">Likewise, to view or enter the activity number that is related to a work order purchase requisition line, on the **Work order purchase requisition** list page, select the purchase requisition record, and then, in the **Purchase requisition** column, select the link for the purchase requisition.</span></span> <span data-ttu-id="0e53a-156">Vous pouvez trouver le champ **Numéro d'activité** sur l'onglet **Projet** de l'organisateur **Détails de ligne**.</span><span class="sxs-lookup"><span data-stu-id="0e53a-156">You can find the **Activity number** field on the **Project** tab of the **Line details** FastTab.</span></span>

