---
title: Regroupements d'ordres de travail
description: Cette rubrique décrit comment utiliser les regroupements d'ordres de travail dans le module Gestion des actifs.
author: josaw1
manager: AnnBe
ms.date: 08/15/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2019-08-15
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 069fa02073808fd7bbaac9bc1603e49ce4d450eb
ms.sourcegitcommit: f5bfa3212bc3ef7d944a358ef08fe8863fd93b91
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/16/2019
ms.locfileid: "1875652"
---
# <a name="work-order-pools"></a><span data-ttu-id="2a6c2-103">Regroupements d'ordres de travail</span><span class="sxs-lookup"><span data-stu-id="2a6c2-103">Work order pools</span></span>


[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]


<span data-ttu-id="2a6c2-104">Vous pouvez utiliser les regroupements d'ordres de travail pour regrouper les ordres de travail qui ont un événement commun.</span><span class="sxs-lookup"><span data-stu-id="2a6c2-104">You can use work order pools to group work orders that have something in common.</span></span> <span data-ttu-id="2a6c2-105">Par exemple, vous pouvez créer des regroupements d'ordres de travail selon</span><span class="sxs-lookup"><span data-stu-id="2a6c2-105">For example, you can create work order pools for</span></span>

- <span data-ttu-id="2a6c2-106">les équipes de travail, par exemple, Équipe de maintenance A, Équipe de maintenance B</span><span class="sxs-lookup"><span data-stu-id="2a6c2-106">work crews, for example, Maintenance Crew A, Maintenance Crew B</span></span>  

- <span data-ttu-id="2a6c2-107">les qualifications professionnelles, par exemple, électriciens ou plombiers</span><span class="sxs-lookup"><span data-stu-id="2a6c2-107">professional skills, for example, electricians or plumbers</span></span>  

- <span data-ttu-id="2a6c2-108">les emplacements physiques</span><span class="sxs-lookup"><span data-stu-id="2a6c2-108">physical locations</span></span>  

- <span data-ttu-id="2a6c2-109">les calendriers, par exemple, semaines ou autres périodes</span><span class="sxs-lookup"><span data-stu-id="2a6c2-109">time schedules, for example, weeks or other periods</span></span>  


<span data-ttu-id="2a6c2-110">Si nécessaire, un ordre de travail peut être placé dans de nombreux regroupements d'ordres de travail.</span><span class="sxs-lookup"><span data-stu-id="2a6c2-110">If required, one work order can be placed in many work order pools.</span></span>


## <a name="create-work-order-pool"></a><span data-ttu-id="2a6c2-111">Créer un regroupement d'ordres de travail</span><span class="sxs-lookup"><span data-stu-id="2a6c2-111">Create work order pool</span></span>

<span data-ttu-id="2a6c2-112">Dans le champ **Tous les regroupements d'ordres de travail** ou **Regroupements d'ordres de travail actifs**, vous pouvez obtenir une vue d'ensemble de vos regroupements d'ordres de travail et créer de nouveaux regroupements.</span><span class="sxs-lookup"><span data-stu-id="2a6c2-112">In **All work order pools** or **Active work order pools**, you can get an overview of your work order pools and create new pools.</span></span>

1. <span data-ttu-id="2a6c2-113">Cliquez sur **Gestion des actifs** > **Commun** > **Regroupements d'ordres de travail** > **Tous les regroupements d'ordres de travail** ou **Regroupements d'ordres de travail actifs**.</span><span class="sxs-lookup"><span data-stu-id="2a6c2-113">Click **Asset management** > **Common** > **Work order pools** > **All work order pools** or **Active work order pools**.</span></span>

2. <span data-ttu-id="2a6c2-114">Cliquez sur **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="2a6c2-114">Click **New**.</span></span>

3. <span data-ttu-id="2a6c2-115">Insérez un ID de regroupement d'ordres de travail dans le champ **Regroupement**, et un nom de compteur dans le champ **Nom**.</span><span class="sxs-lookup"><span data-stu-id="2a6c2-115">Insert a work order pool ID in the **Pool** field and a name in the **Name** field.</span></span>

4. <span data-ttu-id="2a6c2-116">Sélectionnez « Oui » sur le bouton à bascule **Actif** pour indiquer que le regroupement des ordres de travail est actif.</span><span class="sxs-lookup"><span data-stu-id="2a6c2-116">Select "Yes" on the **Active** toggle button to indicate that the work order pool is active.</span></span>

5. <span data-ttu-id="2a6c2-117">Sélectionnez « Oui » sur le bouton à bascule **Supprimer les relations des ordres de travail** si vous souhaitez que les ordres de travail soient automatiquement supprimés du regroupement des ordres de travail.</span><span class="sxs-lookup"><span data-stu-id="2a6c2-117">Select "Yes" on the **Delete work order relations** toggle button if you want work orders to be automatically removed from the work order pool.</span></span>

6. <span data-ttu-id="2a6c2-118">Dans le champ **Supprimer l'état du cycle de vie**, sélectionnez l'état du cycle de vie de l'ordre de travail.</span><span class="sxs-lookup"><span data-stu-id="2a6c2-118">In the **Delete lifecycle state** field, select the work order lifecycle state.</span></span> <span data-ttu-id="2a6c2-119">Par exemple, l'état du cycle de vie de l'ordre de travail pour exécuter un ordre de travail peut être défini pour supprimer automatiquement les relations avec les regroupements d'ordres de travail.</span><span class="sxs-lookup"><span data-stu-id="2a6c2-119">For example, the work order lifecycle state for completing a work order could be set to automatically delete relations to work order pools.</span></span>

7. <span data-ttu-id="2a6c2-120">Vous pouvez commencer à ajouter immédiatement des ordres de travail à votre regroupement d'ordres de travail.</span><span class="sxs-lookup"><span data-stu-id="2a6c2-120">You can start adding work orders to your work order pool right away.</span></span> <span data-ttu-id="2a6c2-121">Dans l'organisateur **Ordres de travail**, cliquez sur **Ajouter une ligne**.</span><span class="sxs-lookup"><span data-stu-id="2a6c2-121">On the **Work orders** FastTab, click **Add line**.</span></span>

8. <span data-ttu-id="2a6c2-122">Sélectionnez un ordre de travail dans le champ **Ordre de travail**.</span><span class="sxs-lookup"><span data-stu-id="2a6c2-122">Select a work order in the **Work order** field.</span></span> <span data-ttu-id="2a6c2-123">Les champs associés sont alors mis à jour automatiquement.</span><span class="sxs-lookup"><span data-stu-id="2a6c2-123">The related fields are automatically updated.</span></span>

9. <span data-ttu-id="2a6c2-124">Répétez les étapes 7-8 si vous souhaitez ajouter plus d'ordres de travail.</span><span class="sxs-lookup"><span data-stu-id="2a6c2-124">Repeat steps 7-8 if you want to add more work orders.</span></span>

10. <span data-ttu-id="2a6c2-125">Dans le champ **Ordre de tri**, vous pouvez indiquer si les ordres de travail doivent être effectués dans un certain ordre.</span><span class="sxs-lookup"><span data-stu-id="2a6c2-125">In the **Sort order** field, you can indicate if the work orders should be carried out in a certain order.</span></span> <span data-ttu-id="2a6c2-126">Insérez des chiffres 1, 2, 3, etc. pour indiquer un ordre spécifique pour les ordres de travail sélectionnés.</span><span class="sxs-lookup"><span data-stu-id="2a6c2-126">Insert numbers 1, 2, 3, and so on to indicate a specific sequence for the selected work orders.</span></span>

11. <span data-ttu-id="2a6c2-127">Cliquez sur le bouton **Ordres de travail** pour voir une liste de tous les ordres de travail inclus dans le regroupement d'ordres de travail.</span><span class="sxs-lookup"><span data-stu-id="2a6c2-127">Click the **Work orders** button to see a list of all the work orders included in the work order pool.</span></span>

12. <span data-ttu-id="2a6c2-128">Cliquez sur le bouton **Capacité maximale** pour ouvrir **Capacité maximale** afin de calculer et d'afficher la capacité maximale pour le programme de maintenance, les ordres de travail non planifiés et les ordres de travail planifiés.</span><span class="sxs-lookup"><span data-stu-id="2a6c2-128">Click the **Capacity load** button to open **Capacity load** to calculate and view capacity load for maintenance schedule, not-scheduled work orders, and scheduled work orders.</span></span>

13. <span data-ttu-id="2a6c2-129">Cliquez sur le bouton **Prévision d'article** pour ouvrir **Prévision d'article** afin de calculer et d'afficher les prévisions pour les articles (pièces détachées et autres articles requis) associées au programme de maintenance, aux ordres de travail non planifiés et aux ordres de travail planifiés.</span><span class="sxs-lookup"><span data-stu-id="2a6c2-129">Click the **Item forecast** button to open **Item forecast** to calculate and view forecasts for items (spare parts and other required items) related to maintenance schedule, not-scheduled work orders, and scheduled work orders.</span></span>

14. <span data-ttu-id="2a6c2-130">Cliquez sur le bouton **Demande d'achat de l'ordre de travail** pour ouvrir la liste **Demande d'achat de l'ordre de travail** et voir une liste des demandes d'achat en lien avec les ordres de travail dans le regroupement d'ordres de travail.</span><span class="sxs-lookup"><span data-stu-id="2a6c2-130">Click the **Work order purchase requisition** button to open the **Work order purchase requisition** list to see a list of purchase requisitions related to the work orders in the work order pool.</span></span>

15. <span data-ttu-id="2a6c2-131">Cliquez sur le bouton **Achat de l'ordre de travail** pour ouvrir la liste **Achat de l'ordre de travail** et voir une liste des commandes fournisseur en lien avec les ordres de travail dans le regroupement d'ordres de travail.</span><span class="sxs-lookup"><span data-stu-id="2a6c2-131">Click the **Work order purchase** button to open the **Work order purchase** list to see a list of purchase orders related to the work orders in the work order pool.</span></span>

>[!NOTE]
><span data-ttu-id="2a6c2-132">Lorsqu'un regroupement d'ordres de travail n'est plus approprié pour la planification de votre travail, définissez la case **Actif** pour ce regroupement sur « Non » dans la vue de liste **Regroupement des ordres de travail**.</span><span class="sxs-lookup"><span data-stu-id="2a6c2-132">When a work order pool is no longer relevant for your work planning, set the **Active** check box for that pool to "No" in the **Work order pool** list view.</span></span>

<span data-ttu-id="2a6c2-133">Cochez la case **Supprimer les relations de l'ordre de travail** si vous souhaitez supprimer toutes les lignes de l'ordre de travail, par exemple pour créer un regroupement vide que vous pouvez ensuite utiliser pour d'autres ordres de travail.</span><span class="sxs-lookup"><span data-stu-id="2a6c2-133">Select the **Delete work order relations** check box if you want to delete all work order lines, for example to create an empty pool that you can later use for other work orders.</span></span> <span data-ttu-id="2a6c2-134">Pensez à activer la case à cocher **Supprimer les relations de l'ordre de travail** si vous souhaitez utiliser le regroupement des ordres de travail pour créer ultérieurement des relations de l'ordre de travail.</span><span class="sxs-lookup"><span data-stu-id="2a6c2-134">Remember to clear the **Delete work order relations** check box if you want to use the work order pool to create new work order relations later.</span></span>


![Figure 1](media/22-work-orders.png)


## <a name="add-work-order-to-a-work-order-pool"></a><span data-ttu-id="2a6c2-136">Ajouter un ordre de travail à un regroupement d'ordres de travail</span><span class="sxs-lookup"><span data-stu-id="2a6c2-136">Add work order to a work order pool</span></span>

<span data-ttu-id="2a6c2-137">Comme décrit dans la section ci-dessus, vous pouvez ajouter des ordres de travail à un regroupement d'ordres de travail lorsque vous créez le regroupement.</span><span class="sxs-lookup"><span data-stu-id="2a6c2-137">As described in the section above, you can add work orders to a work order pool when you create the pool.</span></span> <span data-ttu-id="2a6c2-138">Vous pouvez également ajouter un ordre de travail à un regroupement d'ordres de travail depuis une liste **Tous les ordres de travail**.</span><span class="sxs-lookup"><span data-stu-id="2a6c2-138">You can also add a work order to a work order pool from one of the **All work orders** list.</span></span>

1. <span data-ttu-id="2a6c2-139">Cliquez sur **Gestion des actifs** > **Commun** > **Ordre de travail** > **Tous les ordres de travail** ou **Ordres de travail actifs**.</span><span class="sxs-lookup"><span data-stu-id="2a6c2-139">Click **Asset management** > **Common** > **Work orders** > **All work orders** or **Active work orders**.</span></span>

2. <span data-ttu-id="2a6c2-140">Sélectionnez l'ordre de travail dans la liste et cliquez sur **Regroupement d'ordres de travail**.</span><span class="sxs-lookup"><span data-stu-id="2a6c2-140">Select the work order in the list, and click **Work order pool**.</span></span>

3. <span data-ttu-id="2a6c2-141">Sélectionnez « Ajouter » dans le champ **Ajouter/supprimer**.</span><span class="sxs-lookup"><span data-stu-id="2a6c2-141">Select "Add" in the **Add/remove** field.</span></span>

4. <span data-ttu-id="2a6c2-142">Sélectionnez le regroupement d'ordres de travail dans le champ **Regroupement**.</span><span class="sxs-lookup"><span data-stu-id="2a6c2-142">Select the work order pool in the **Pool** field.</span></span>

5. <span data-ttu-id="2a6c2-143">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="2a6c2-143">Click **OK**.</span></span>

6. <span data-ttu-id="2a6c2-144">Après avoir ajouté un ordre de travail à un regroupement d'ordres de travail, si vous souhaitez placer l'ordre de travail dans un ordre spécifique dans le regroupement : ouvrez une des pages de liste de regroupement des ordres de travail, sélectionnez le regroupement et cliquez sur **Modifier**, et ajuster l'ordre de tri des ordres de travail inclus dans le regroupement sur l'écran **Regroupement des ordres de travail** > organisateur **Ordre de travail** > champ **Ordre de tri**.</span><span class="sxs-lookup"><span data-stu-id="2a6c2-144">After you have added a work order to a work order pool, if you want to place the work order in a specific sequence in the pool: Open one of the work order pools list pages, select the pool and click **Edit**, and adjust the sort order of the work orders included in pool in the **Work order pool** form > **Work orders** FastTab > **Sort order** field.</span></span>

<span data-ttu-id="2a6c2-145">Si vous souhaitez supprimer l'ordre de travail sélectionné depuis un regroupement d'ordres de travail, sélectionnez « Supprimer » à l'étape 3.</span><span class="sxs-lookup"><span data-stu-id="2a6c2-145">If you want to remove the selected work order from a work order pool, select "Remove" in step 3.</span></span>

