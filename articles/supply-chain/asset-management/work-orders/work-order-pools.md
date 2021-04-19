---
title: Regroupements d’ordres de travail
description: Cette rubrique décrit comment utiliser les regroupements d’ordres de travail dans le module Gestion des actifs.
author: johanhoffmann
ms.date: 10/15/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EntAssetWorkOrderTablePoolPart, EntAssetWorkOrderPoolReferenceInfoPart, EntAssetWorkOrderPool, EntAssetWorkOrderPoolPreviewPart
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2019-09-30
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: f07415cc0e2ba80c332387ce86e09ba8aa840f8a
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5839533"
---
# <a name="work-order-pools"></a><span data-ttu-id="f6aed-103">Regroupements d’ordres de travail</span><span class="sxs-lookup"><span data-stu-id="f6aed-103">Work order pools</span></span>

[!include [banner](../../includes/banner.md)]


<span data-ttu-id="f6aed-104">Vous pouvez utiliser les regroupements d’ordres de travail pour regrouper les ordres de travail qui ont un événement commun.</span><span class="sxs-lookup"><span data-stu-id="f6aed-104">You can use work order pools to group work orders that have something in common.</span></span> <span data-ttu-id="f6aed-105">Voici quelques exemples de ce pour quoi vous pouvez créer des regroupements d’ordres de travail :</span><span class="sxs-lookup"><span data-stu-id="f6aed-105">Here are some examples of things that you can create  work order pools for:</span></span>

- <span data-ttu-id="f6aed-106">Les équipes de travail, par exemple, Équipe de maintenance A ou Équipe de maintenance B</span><span class="sxs-lookup"><span data-stu-id="f6aed-106">Work crews, for example, Maintenance Crew A or Maintenance Crew B</span></span>  

- <span data-ttu-id="f6aed-107">Les qualifications professionnelles, par exemple, électriciens ou plombiers</span><span class="sxs-lookup"><span data-stu-id="f6aed-107">Professional skills, such as electricians or plumbers</span></span>  

- <span data-ttu-id="f6aed-108">Les emplacements physiques</span><span class="sxs-lookup"><span data-stu-id="f6aed-108">Physical locations</span></span>  

- <span data-ttu-id="f6aed-109">Les calendriers, comme les semaines ou autres périodes</span><span class="sxs-lookup"><span data-stu-id="f6aed-109">Time schedules, such as weeks or other periods</span></span>  

<span data-ttu-id="f6aed-110">Au besoin, vous pouvez placer un ordre de travail dans plusieurs regroupements d’ordres de travail.</span><span class="sxs-lookup"><span data-stu-id="f6aed-110">As you require, you can put one work order in multiple work order pools.</span></span>


## <a name="create-a-work-order-pool"></a><span data-ttu-id="f6aed-111">Créer un regroupement d’ordres de travail</span><span class="sxs-lookup"><span data-stu-id="f6aed-111">Create a work order pool</span></span>

<span data-ttu-id="f6aed-112">Sur la page de liste **Tous les regroupements d’ordres de travail** ou **Regroupements d’ordres de travail actifs**, vous pouvez obtenir une vue d’ensemble de vos regroupements d’ordres de travail et créer de nouveaux regroupements.</span><span class="sxs-lookup"><span data-stu-id="f6aed-112">On the **All work order pools** or **Active work order pools** list page, you can get an overview of your work order pools and create new pools.</span></span>

1. <span data-ttu-id="f6aed-113">Sélectionnez **Gestion des actifs** > **Commun** > **Regroupements d’ordres de travail** > **Tous les regroupements d’ordres de travail** ou **Regroupements d’ordres de travail actifs**.</span><span class="sxs-lookup"><span data-stu-id="f6aed-113">Select **Asset management** > **Common** > **Work order pools** > **All work order pools** or **Active work order pools**.</span></span>

2. <span data-ttu-id="f6aed-114">Sélectionnez **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="f6aed-114">Select **New**.</span></span>

3. <span data-ttu-id="f6aed-115">Dans le champ **Regroupement**, entrez un ID pour le regroupements d’ordres de travail.</span><span class="sxs-lookup"><span data-stu-id="f6aed-115">In the **Pool** field, enter an ID for the work order pool.</span></span>

4. <span data-ttu-id="f6aed-116">Dans le champ **Nom**, entrez un nom.</span><span class="sxs-lookup"><span data-stu-id="f6aed-116">the **Name** field, enter a name.</span></span>

5. <span data-ttu-id="f6aed-117">Définissez l’option **Active** sur **Oui** pour indiquer que le regroupement des ordres de travail est actif.</span><span class="sxs-lookup"><span data-stu-id="f6aed-117">Set the **Active** option to **Yes** to indicate that the work order pool is active.</span></span>

6. <span data-ttu-id="f6aed-118">Définissez l’option **Supprimer les relations des ordres de travail** sur **Oui** si vous souhaitez que les ordres de travail soient automatiquement supprimés du regroupement des ordres de travail.</span><span class="sxs-lookup"><span data-stu-id="f6aed-118">Set the **Delete work order relations** option to **Yes** if work orders should automatically be removed from the work order pool.</span></span>

7. <span data-ttu-id="f6aed-119">Dans le champ **Supprimer l’état du cycle de vie**, sélectionnez l’état du cycle de vie de l’ordre de travail.</span><span class="sxs-lookup"><span data-stu-id="f6aed-119">In the **Delete lifecycle state** field, select the work order lifecycle state.</span></span> <span data-ttu-id="f6aed-120">Par exemple, l’état du cycle de vie de l’ordre de travail pour exécuter un ordre de travail peut être défini pour supprimer automatiquement les relations avec les regroupements d’ordres de travail.</span><span class="sxs-lookup"><span data-stu-id="f6aed-120">For example, the work order lifecycle state for completing a work order could be set to automatically delete relations to work order pools.</span></span>

    <span data-ttu-id="f6aed-121">Vous pouvez commencer à ajouter immédiatement des ordres de travail à votre regroupement d’ordres de travail.</span><span class="sxs-lookup"><span data-stu-id="f6aed-121">You can start adding work orders to your work order pool right away.</span></span>

8. <span data-ttu-id="f6aed-122">Dans l’organisateur **Ordres de travail**, sélectionnez **Ajouter une ligne**.</span><span class="sxs-lookup"><span data-stu-id="f6aed-122">On the **Work orders** FastTab, select **Add line**.</span></span>

9. <span data-ttu-id="f6aed-123">Dans le champ **Ordre de travail**, sélectionnez un ordre de travail.</span><span class="sxs-lookup"><span data-stu-id="f6aed-123">In the **Work order** field, select a work order.</span></span> <span data-ttu-id="f6aed-124">Les champs associés sont alors mis à jour automatiquement.</span><span class="sxs-lookup"><span data-stu-id="f6aed-124">The related fields are automatically updated.</span></span>

10. <span data-ttu-id="f6aed-125">Répétez les étapes 8 à 9 pour ajouter d’autres ordres de travail.</span><span class="sxs-lookup"><span data-stu-id="f6aed-125">Repeat steps 8 through 9 to add more work orders.</span></span>

11. <span data-ttu-id="f6aed-126">Si les ordres de travail que vous avez ajoutés doivent être effectués dans un ordre spécifique, dans le champ **Ordre de tri**, vous pouvez entrer les numéros **1**, **2**, **3**, etc. pour spécifier cet ordre.</span><span class="sxs-lookup"><span data-stu-id="f6aed-126">If the work orders that you added should be done in a specific order, in the **Sort order** field, you can enter the numbers **1**, **2**, **3**, and so on, to specify that order.</span></span>

12. <span data-ttu-id="f6aed-127">Pour afficher une liste de tous les ordres de travail inclus dans le regroupement des ordres de travail, dans le volet Actions, sous l’onglet **Regroupement des ordres de travail**, dans le groupe **Afficher le regroupement des ordres de travail associés**, sélectionnez **Ordre de travail** pour ouvrir la page de liste **Tous les ordres de travail**.</span><span class="sxs-lookup"><span data-stu-id="f6aed-127">To view a list of all the work orders that are included in the work order pool, on the Action Pane, on the **Work order pool** tab, in the **View work order pool related** group, select **Work orders** to open the **All work orders** list page.</span></span>

13. <span data-ttu-id="f6aed-128">Pour calculer et afficher la charge maximale du programme de maintenance, les ordres de travail non-programmés, et les ordres de travail prévus, dans le volet Actions, sous l’onglet **Regroupement des ordres de travail**, dans le groupe **Afficher le regroupement des ordres de travail associés**, sélectionnez **Charge maximale** pour ouvrir la boîte de dialogue **Calculer la charge maximale**.</span><span class="sxs-lookup"><span data-stu-id="f6aed-128">To calculate and view capacity load for the maintenance schedule, unscheduled work orders, and scheduled work orders, on the Action Pane, on the **Work order pool** tab, in the **View work order pool related** group, select **Capacity load** to open the **Calculate capacity load** dialog.</span></span>

14. <span data-ttu-id="f6aed-129">Pour calculer et afficher des prévisions d’articles (pièces détachées ou autres articles requis) associées au programme de maintenance, les ordres de travail non-programmés, et les ordres de travail prévus, dans le volet Actions, sous l’onglet **Regroupement des ordres de travail**, dans le groupe **Afficher le regroupement des ordres de travail associés**, sélectionnez **Prévision d’article** pour ouvrir la boîte de dialogue **Calculer la prévision d’article**.</span><span class="sxs-lookup"><span data-stu-id="f6aed-129">To calculate and view forecasts for items (spare parts and other required items) that are related to maintenance schedule, unscheduled work orders, and scheduled work orders, on the Action Pane, on the **Work order pool** tab, in the **View work order pool related** group, select **Item forecast** to open the **Calculate item forecast** dialog.</span></span>

15. <span data-ttu-id="f6aed-130">Pour afficher une liste des demandes d’achat associées aux ordres de travail du regroupements des ordres de travail, dans le volet Actions, sous l’onglet **Regroupement des ordres de travail**, dans le groupe **Approvisionnement**, sélectionnez **Demande d’achat de l’ordre de travail** pour ouvrir la page de liste **Demande d’achat de l’ordre de travail**.</span><span class="sxs-lookup"><span data-stu-id="f6aed-130">To view a list of purchase requisitions that are related to the work orders in the work order pool, on the Action Pane, on the **Work order pool** tab, in the **Procurement** group, select **Work order purchase requisition** to open the **Work order purchase requisition** list page.</span></span>

16. <span data-ttu-id="f6aed-131">Pour afficher une liste des commandes fournisseur associées aux ordres de travail du regroupements des ordres de travail, dans le volet Actions, sous l’onglet **Regroupement des ordres de travail**, dans le groupe **Approvisionnement**, sélectionnez **Achats de l’ordre de travail** pour ouvrir la page de liste **Achats de l’ordre de travail**.</span><span class="sxs-lookup"><span data-stu-id="f6aed-131">To view a list of purchase orders that are related to the work orders in the work order pool, on the Action Pane, on the **Work order pool** tab, in the **Procurement** group, select **Work order purchase** to open the **Work order purchase** list page.</span></span>

>[!NOTE]
><span data-ttu-id="f6aed-132">Lorsqu’un regroupement d’ordres de travail n’est plus approprié pour la planification de votre travail, définissez l’option **Actif** pour ce regroupement sur **Non** dans la vue de liste de la page **Regroupement des ordres de travail**.</span><span class="sxs-lookup"><span data-stu-id="f6aed-132">When a work order pool is no longer relevant to your work planning, set the **Active** option for that pool to **No** in the list view of the **Work order pool** page.</span></span>

<span data-ttu-id="f6aed-133">Pour supprimer toutes les lignes d’ordre de travail, définissez l’option **Supprimer les relations des ordres de travail** sur **Oui**.</span><span class="sxs-lookup"><span data-stu-id="f6aed-133">To delete all worker order lines, set the **Delete work order relations** option to **Yes**.</span></span> <span data-ttu-id="f6aed-134">Cette option est utile si, par exemple, pour créer un regroupement vide que vous pouvez utiliser ultérieurement pour d’autres ordres de travail.</span><span class="sxs-lookup"><span data-stu-id="f6aed-134">This option is useful if, for example, you want to create an empty pool that you can use later for other work orders.</span></span> <span data-ttu-id="f6aed-135">Si vous êtes prêt à utiliser le regroupement des ordres de travail pour créer ultérieurement des relations de l’ordre de travail, n’oubliez pas de définir l’option **Supprimer les relations des ordres de travail** sur **Non**.</span><span class="sxs-lookup"><span data-stu-id="f6aed-135">When you're ready to use the work order pool to create new work order relations later, remember to set the **Delete work order relations** option to **No**.</span></span>

<span data-ttu-id="f6aed-136">L’illustration suivante présente un exemple de la liste de page **Regroupement des ordres de travail**.</span><span class="sxs-lookup"><span data-stu-id="f6aed-136">The illustration below shows an example of the **Work order pool** list page.</span></span>

![Figure 1](media/22-work-orders.png)


## <a name="add-a-work-order-to-a-work-order-pool"></a><span data-ttu-id="f6aed-138">Ajouter un ordre de travail à un regroupement d’ordres de travail</span><span class="sxs-lookup"><span data-stu-id="f6aed-138">Add a work order to a work order pool</span></span>

<span data-ttu-id="f6aed-139">Comme décrit dans la section précédente, vous pouvez ajouter des ordres de travail à un regroupement d’ordres de travail lorsque vous créez ce regroupement.</span><span class="sxs-lookup"><span data-stu-id="f6aed-139">As described in the previous section, you can add work orders to a work order pool when you create that pool.</span></span> <span data-ttu-id="f6aed-140">Vous pouvez également ajouter des ordres de travail à un regroupement des ordres de travail dans la page de liste **Tous les ordres de travail** ou **Ordres de travail actifs**.</span><span class="sxs-lookup"><span data-stu-id="f6aed-140">You can also add work orders to a work order pool on the **All work orders** or **Active work orders** list page.</span></span>

1. <span data-ttu-id="f6aed-141">Sélectionnez l’ordre de travail puis, dans le volet Actions, sous l’onglet **Ordre de travail**, dans le groupe **Tenir à jour**, sélectionnez **Regroupement des ordres de travail**.</span><span class="sxs-lookup"><span data-stu-id="f6aed-141">Select the work order, and then, on the Action Pane, on the **Work order** tab, in the **Maintain** group, select **Work order pool**.</span></span>

2. <span data-ttu-id="f6aed-142">Sélectionnez l’ordre de travail dans la liste et cliquez sur **Regroupement d’ordres de travail**.</span><span class="sxs-lookup"><span data-stu-id="f6aed-142">Select the work order in the list, and click **Work order pool**.</span></span>

3. <span data-ttu-id="f6aed-143">Dans la boîte de dialogue **Tenir à jour le regroupement des ordres de travail**, dans le champ **Ajouter/supprimer**, sélectionnez **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="f6aed-143">In the **Maintain work order pool** dialog, in the **Add/remove** field, select **Add**.</span></span>

4. <span data-ttu-id="f6aed-144">Dans le champ **Regroupement**, sélectionnez le regroupement des ordres de travail.</span><span class="sxs-lookup"><span data-stu-id="f6aed-144">In the **Pool** field, select the work order pool.</span></span>

5. <span data-ttu-id="f6aed-145">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="f6aed-145">Select **OK**.</span></span>

6. <span data-ttu-id="f6aed-146">Pour mettre l’ordre de travail que vous avez ajouté dans un ordre spécifique dans le regroupement des ordres de travail, dans la page de liste **Tous les regroupements des ordres de travail** ou **Regroupements des ordres de travail actifs**, sélectionnez le regroupement, puis sélectionnez **Modifier**.</span><span class="sxs-lookup"><span data-stu-id="f6aed-146">To put the work order that you added in a specific order in the work order pool, on the **All work order pools** or **Active work order pools** list page, select the pool, and then select **Edit**.</span></span> <span data-ttu-id="f6aed-147">Puis, dans la page **Regroupement des ordres de travail**, sous l’organisateur **Ordres de travail**, utilisez le champ **Ordre de tri** pour ajuster l’ordre de tri des ordres de travail inclus dans le regroupement.</span><span class="sxs-lookup"><span data-stu-id="f6aed-147">Then, on the **Work order pool** page, on the **Work orders** FastTab, use the **Sort order** field to adjust the sort order of the work orders that are included in pool.</span></span>

<span data-ttu-id="f6aed-148">Pour supprimer un ordre de travail depuis un regroupement d’ordres de travail, répétez ces étapes, mais sélectionnez **Supprimer** à l’étape 3.</span><span class="sxs-lookup"><span data-stu-id="f6aed-148">To remove a work order from a work order pool, repeat these steps, but select **Remove** in step 3.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]