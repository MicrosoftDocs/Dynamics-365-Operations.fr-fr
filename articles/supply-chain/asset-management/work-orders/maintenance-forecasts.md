---
title: Prévisions en matière de maintenance
description: Cette rubrique explique les prévisions en matière de maintenance dans le module Gestion des actifs.
author: josaw1
manager: AnnBe
ms.date: 10/15/2019
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
ms.search.validFrom: 2019-09-30
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: a1596b283c3eaffca25ff7f03c722a2bcce109fb
ms.sourcegitcommit: deb87e518a151d8bb084891851a39758938a96e4
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/15/2019
ms.locfileid: "2626291"
---
# <a name="maintenance-forecasts"></a><span data-ttu-id="4b851-103">Prévisions en matière de maintenance</span><span class="sxs-lookup"><span data-stu-id="4b851-103">Maintenance forecasts</span></span>

[!include [banner](../../includes/banner.md)]



<span data-ttu-id="4b851-104">Lorsque vous créez un ordre de travail, vous créez des tâches de l'ordre de travail avec des actifs et des types de tâches de maintenance associés.</span><span class="sxs-lookup"><span data-stu-id="4b851-104">When you create a work order, you create work order jobs that have related assets and maintenance job types.</span></span> <span data-ttu-id="4b851-105">Lorsque vous sélectionnez un type de tâche de maintenance contenant les prévisions en matière de maintenance, les prévisions sont automatiquement copiées vers l'ordre de travail.</span><span class="sxs-lookup"><span data-stu-id="4b851-105">When you select a maintenance job type that contains maintenance forecasts, the forecasts are automatically copied to the work order.</span></span>

<span data-ttu-id="4b851-106">Vous pouvez ajouter des lignes de prévision à un ordre de travail ou les supprimer d'un ordre de travail.</span><span class="sxs-lookup"><span data-stu-id="4b851-106">You might be able to add forecast lines to a work order or delete them from a work order.</span></span> <span data-ttu-id="4b851-107">La configuration de l'état du cycle de vie de l'ordre de travail, le type de projet associé et les règles de stade liées au type de projet déterminent si vous pouvez ajouter ou modifier les lignes de prévision.</span><span class="sxs-lookup"><span data-stu-id="4b851-107">The setup of the work order lifecycle state, the related project type, and the stage rules that are related to the project type determine whether you can add or edit forecast lines.</span></span> <span data-ttu-id="4b851-108">Pour plus d'informations sur les états du cycle de vie de l'ordre de travail et les étapes du projet associé, consultez [Prévisions, ordres de travail et projets](../integration-to-project-management-and-accounting/forecasts-work-orders-and-projects.md).</span><span class="sxs-lookup"><span data-stu-id="4b851-108">For more information about work order lifecycle states and related project stages, see [Forecasts, work orders, and projects](../integration-to-project-management-and-accounting/forecasts-work-orders-and-projects.md).</span></span>

1. <span data-ttu-id="4b851-109">Sélectionnez **Gestion des actifs** > **Commun** > **Ordre de travail** > **Tous les ordres de travail** ou **Ordres de travail actifs**.</span><span class="sxs-lookup"><span data-stu-id="4b851-109">Select **Asset management** > **Common** > **Work orders** > **All work orders** or **Active work orders**.</span></span>

2. <span data-ttu-id="4b851-110">Sélectionnez l'ordre de travail dans la liste, puis, dans le volet Actions > onglet **Ordre de travail** > groupe **Projet**, sélectionnez **Prévision**.</span><span class="sxs-lookup"><span data-stu-id="4b851-110">Select the work order in the list, and then, on the Action Pane > **Work order** tab > the **Project** group, select **Forecast**.</span></span> <span data-ttu-id="4b851-111">La page **Prévisions en matière de maintenance de l'ordre de travail** affiche les lignes de prévision du type de tâche de maintenance sélectionné sur la tâche de l'ordre de travail.</span><span class="sxs-lookup"><span data-stu-id="4b851-111">The **Work order maintenance forecast** page shows forecast lines from the maintenance job type that is selected on the work order job.</span></span>


## <a name="add-an-hours-forecast-to-a-work-order"></a><span data-ttu-id="4b851-112">Ajouter une prévision horaire à un ordre de travail</span><span class="sxs-lookup"><span data-stu-id="4b851-112">Add an hours forecast to a work order</span></span>

1. <span data-ttu-id="4b851-113">Dans la page **Prévisions en matière de maintenance de l'ordre de travail**, sélectionnez la tâche d'ordre de travail à laquelle ajouter une prévision.</span><span class="sxs-lookup"><span data-stu-id="4b851-113">On the **Work order maintenance forecast** page, select the work order job to add a forecast to.</span></span>

2. <span data-ttu-id="4b851-114">Dans l'organisateur **Heures**, sélectionnez **Ajouter** pour créer une ligne.</span><span class="sxs-lookup"><span data-stu-id="4b851-114">On the **Hours** FastTab, select **Add** to create a new line.</span></span>

3. <span data-ttu-id="4b851-115">Dans le champ **Catégorie**, sélectionnez une catégorie.</span><span class="sxs-lookup"><span data-stu-id="4b851-115">In the **Category** field, select a category.</span></span>

4. <span data-ttu-id="4b851-116">Dans le champ **Heures**, insérez le nombre d'heures prévues.</span><span class="sxs-lookup"><span data-stu-id="4b851-116">In the **Hours** field, enter the number of forecasted hours.</span></span>

5. <span data-ttu-id="4b851-117">Dans le champ **Propriété de ligne**, sélectionnez le type de frais à utiliser sur la ligne.</span><span class="sxs-lookup"><span data-stu-id="4b851-117">In the **Line property** field, select the type of charge that should be used on the line.</span></span>


## <a name="add-an-items-forecast-to-a-work-order"></a><span data-ttu-id="4b851-118">Ajouter une prévision d'articles à un ordre de travail</span><span class="sxs-lookup"><span data-stu-id="4b851-118">Add an items forecast to a work order</span></span>

<span data-ttu-id="4b851-119">Il existe trois manières d'ajouter des articles à une prévisions en matière de maintenance d'ordre de travail.</span><span class="sxs-lookup"><span data-stu-id="4b851-119">There are three ways to add items to a work order maintenance forecast.</span></span> <span data-ttu-id="4b851-120">Vous pouvez créer des lignes pour les articles (pièces détachées) qui ne sont pas inclus dans la liste des pièces détachées ou la nomenclature des actifs, vous pouvez sélectionner des pièces détachées depuis la liste des pièces détachées approuvées, ou vous pouvez sélectionner les articles depuis la nomenclature des actifs.</span><span class="sxs-lookup"><span data-stu-id="4b851-120">You can create lines for items (spare parts) that aren't included on the spare parts list or the asset bill of materials (BOM), you can select spare parts from the approved spare parts list, or you can select items from the asset BOM.</span></span>

- <span data-ttu-id="4b851-121">Dans la page **Prévisions en matière de maintenance de l'ordre de travail**, sélectionnez la tâche d'ordre de travail à laquelle ajouter une prévision.</span><span class="sxs-lookup"><span data-stu-id="4b851-121">On the **Work order maintenance forecast** page, select the work order job to to add a forecast to.</span></span>

- <span data-ttu-id="4b851-122">Dans l'organisateur **Articles**, ajoutez des articles à la prévisions en matière de maintenance à l'aide de la méthode approprié.</span><span class="sxs-lookup"><span data-stu-id="4b851-122">On the **Items** FastTab, add items to the maintenance forecast by using the appropriate method.</span></span>

<span data-ttu-id="4b851-123">Pour créer une ligne pour une pièce détachée qui n'est pas sur la liste des pièces détachées ou la liste de nomenclature des actifs, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="4b851-123">To create a line for a spare part that isn't on the spare parts list or the asset BOM, follow these steps:</span></span>

1. <span data-ttu-id="4b851-124">Sélectionnez **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="4b851-124">Select **Add**.</span></span>
2. <span data-ttu-id="4b851-125">Dans le champ **Numéro d'article**, sélectionnez l'article.</span><span class="sxs-lookup"><span data-stu-id="4b851-125">In the **Item number** field, select the item.</span></span>
3. <span data-ttu-id="4b851-126">Dans le champ **Quantité vendue**, entrez la quantité.</span><span class="sxs-lookup"><span data-stu-id="4b851-126">In the **Sales quantity** field, enter the quantity.</span></span>
4. <span data-ttu-id="4b851-127">Dans le champ **Unité**, sélectionnez l'unité de mesure pour la quantité.</span><span class="sxs-lookup"><span data-stu-id="4b851-127">In the **Unit** field, select the unit of measure for the quantity.</span></span>
5. <span data-ttu-id="4b851-128">Dans les champs **Prix de revient** et **Devise**, entrez les valeurs appropriées.</span><span class="sxs-lookup"><span data-stu-id="4b851-128">In the **Cost price** and **Currency** fields, enter appropriate values.</span></span>
6. <span data-ttu-id="4b851-129">Dans le champ **Propriété de ligne**, sélectionnez une propriété de ligne.</span><span class="sxs-lookup"><span data-stu-id="4b851-129">In the **Line property** field, select a line property.</span></span>
7. <span data-ttu-id="4b851-130">Pour modifier la liste des dimensions affichées dans les lignes d'article, sélectionnez **Stock** > **Dimensions d'affichage**, sélectionnez les dimensions, et puis définissez **Enregistrer le paramétrage** sur **Oui**.</span><span class="sxs-lookup"><span data-stu-id="4b851-130">To change the list of dimensions that is shown on the item lines, select **Inventory** > **Display dimensions**, select the dimensions, and then set the **Save setup** option to **Yes**.</span></span>

<span data-ttu-id="4b851-131">Pour ajouter une pièce détachée d'une liste des parties disponibles approuvées, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="4b851-131">To add a spare part from an approved spare parts list, follow these steps:</span></span>

1. <span data-ttu-id="4b851-132">Sélectionnez **Ajouter des pièces détachées**.</span><span class="sxs-lookup"><span data-stu-id="4b851-132">Select **Add spare parts**.</span></span>
2. <span data-ttu-id="4b851-133">Sélectionnez la pièce détachée, et modifiez les informations associées comme vous le souhaitez.</span><span class="sxs-lookup"><span data-stu-id="4b851-133">Select the spare part, and edit the related information as you require.</span></span>
3. <span data-ttu-id="4b851-134">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="4b851-134">Select **OK**.</span></span>

<span data-ttu-id="4b851-135">Pour ajouter un article de la nomenclature d'immobilisation, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="4b851-135">To add an item from the asset BOM, follow these steps:</span></span>

1. <span data-ttu-id="4b851-136">Sélectionnez **Ajouter des articles de nomenclature**.</span><span class="sxs-lookup"><span data-stu-id="4b851-136">Select **Add BOM items**.</span></span>
2. <span data-ttu-id="4b851-137">Sélectionnez l'article, et modifiez les informations associées comme vous le souhaitez.</span><span class="sxs-lookup"><span data-stu-id="4b851-137">Select the item, and edit the related information as you require.</span></span>
3. <span data-ttu-id="4b851-138">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="4b851-138">Select **OK**.</span></span>

<span data-ttu-id="4b851-139">Pour avoir une vue d'ensemble de l'emplacement d'utilisation de l'article sur la ligne sélectionnée, en ce qui concerne les actifs, les valeurs par défaut du type de tâche de maintenance, les pièces détachées et les ordres de travail dans Gestion des actifs, sélectionnez **Cas d'emploi d'article**.</span><span class="sxs-lookup"><span data-stu-id="4b851-139">To get an overview that shows where the item on the selected line is used in relation to assets, maintenance job type defaults, spare parts, and work orders in Asset Management, select **Item where used**.</span></span> <span data-ttu-id="4b851-140">Pour plus d'informations sur cette vue d'ensemble, voir [Cas d'emploi d'article](../controlling-and-reporting/item-where-used.md).</span><span class="sxs-lookup"><span data-stu-id="4b851-140">For more information about this overview, see [Item where used](../controlling-and-reporting/item-where-used.md).</span></span>


## <a name="add-an-expense-forecast-to-a-work-order"></a><span data-ttu-id="4b851-141">Ajouter une prévision de dépense à un ordre de travail</span><span class="sxs-lookup"><span data-stu-id="4b851-141">Add an expense forecast to a work order</span></span>

1. <span data-ttu-id="4b851-142">Dans la page **Prévisions en matière de maintenance de l'ordre de travail**, sélectionnez la tâche d'ordre de travail à laquelle ajouter une prévision.</span><span class="sxs-lookup"><span data-stu-id="4b851-142">On the **Work order maintenance forecast** page, select the work order job to add a forecast to.</span></span>

2. <span data-ttu-id="4b851-143">Dans l'organisateur **Dépense**, sélectionnez **Ajouter** pour créer une ligne.</span><span class="sxs-lookup"><span data-stu-id="4b851-143">On the **Expense** FastTab, select **Add** to create a line.</span></span>

3. <span data-ttu-id="4b851-144">Dans le champ **Catégorie**, sélectionnez une catégorie.</span><span class="sxs-lookup"><span data-stu-id="4b851-144">In the **Category** field, select a category.</span></span>

4. <span data-ttu-id="4b851-145">Dans le champ **Quantité**, entrez la quantité.</span><span class="sxs-lookup"><span data-stu-id="4b851-145">In the **Quantity** field, enter the quantity.</span></span>

5. <span data-ttu-id="4b851-146">Dans les champs **Prix de revient**, **Devise de vente** et **Prix de vente**, entrez les valeurs appropriées.</span><span class="sxs-lookup"><span data-stu-id="4b851-146">In the **Cost price**, **Sales currency**, and **Sales price** fields, enter appropriate values.</span></span>

6. <span data-ttu-id="4b851-147">Dans le champ **Propriété de ligne**, sélectionnez le type de frais à utiliser sur la ligne.</span><span class="sxs-lookup"><span data-stu-id="4b851-147">In the **Line property** field, select the type of charge that should be used on the line.</span></span>

>[!NOTE]
><span data-ttu-id="4b851-148">L'organisateur **Totaux de prévisions de maintenance** affiche une vue d'ensemble du nombre de lignes créées, pour la tâche de l'ordre de travail sélectionnée et pour l'ordre de travail, sous chaque organisateur.</span><span class="sxs-lookup"><span data-stu-id="4b851-148">The **Maintenance forecast totals** FastTab shows an overview of the number of lines that have been created, for the selected work order job and for the work order, on each FastTab.</span></span> <span data-ttu-id="4b851-149">Il affiche également le total des heures de travail prévues pour la tâche de l'ordre de travail et pour l'ordre de travail.</span><span class="sxs-lookup"><span data-stu-id="4b851-149">It also shows the total forecasted work hours for the work order job and the work order.</span></span>

<span data-ttu-id="4b851-150">L'illustration suivante présente un exemple de la liste de page **Prévisions en matière de maintenance de l'ordre de travail**.</span><span class="sxs-lookup"><span data-stu-id="4b851-150">The illustration below shows an example of the **Work order maintenance forecast** page.</span></span>

![Figure 1](media/06-work-orders.png)


## <a name="automatic-update-of-work-order-forecasts"></a><span data-ttu-id="4b851-152">Mise à jour automatique des prévisions de l'ordre de travail</span><span class="sxs-lookup"><span data-stu-id="4b851-152">Automatic update of work order forecasts</span></span>

<span data-ttu-id="4b851-153">Si les coûts horaires, les coûts d'article et les dépenses sont mises à jour dans d'autres modules dans Microsoft Dynamics 365 for Finance and Operations, les prévisions de l'ordre de travail dans Gestion des actifs peut automatiquement être mis à jour pour refléter ces modifications.</span><span class="sxs-lookup"><span data-stu-id="4b851-153">If hour costs, item costs, and expenses are updated in other modules in Microsoft Dynamics 365 for Finance and Operations, work order forecasts in Asset Management can automatically be updated to reflect those changes.</span></span> <span data-ttu-id="4b851-154">Cette capacité permet de garantir que les derniers prix de revient soient toujours utilisés dans vos prévisions d'ordre de travail.</span><span class="sxs-lookup"><span data-stu-id="4b851-154">This capability helps guarantee that the latest cost prices are always used in your work order forecasts.</span></span> <span data-ttu-id="4b851-155">Vous pouvez également effectuer des mises à jour similaires pour [prévisions de type de tâche de maintenance](../setup-for-work-orders/job-groups-and-job-types-variants-trades-and-checklists.md).</span><span class="sxs-lookup"><span data-stu-id="4b851-155">You can also do similar updates for [maintenance job type forecasts](../setup-for-work-orders/job-groups-and-job-types-variants-trades-and-checklists.md).</span></span>

1. <span data-ttu-id="4b851-156">Sélectionnez **Gestion des actifs** > **Périodique** > **Prévisions** > **Mettre à jour les prévisions de l'ordre de travail**.</span><span class="sxs-lookup"><span data-stu-id="4b851-156">Select **Asset management** > **Periodic** > **Forecast** > **Update work order forecast**.</span></span>

2. <span data-ttu-id="4b851-157">Dans la boîte de dialogue **Mettre à jour les prévisions de l'ordre de travail**, sur l'organisateur **Enregistrements à inclure**, vous pouvez ajouter des sélections concernant les ordres de travail spécifiques ou des tâches d'ordre de travail, si nécessaire.</span><span class="sxs-lookup"><span data-stu-id="4b851-157">In the **Update work order forecast** dialog, on the **Records to include** FastTab, you can add selections regarding specific work orders or work order jobs, as you require.</span></span> <span data-ttu-id="4b851-158">Cliquez sur **Filtrer** pour effectuer les sélections appropriées.</span><span class="sxs-lookup"><span data-stu-id="4b851-158">Click **Filter** to make the relevant selections.</span></span>

3. <span data-ttu-id="4b851-159">Sous le raccourci **Exécuter à l'arrière-plan**, vous pouvez configurer la mise à jour automatique comme traitement par lots comme vous le souhaitez.</span><span class="sxs-lookup"><span data-stu-id="4b851-159">On the **Run in the background** FastTab, you can set up the automatic update as a batch job, as you require.</span></span>

4. <span data-ttu-id="4b851-160">Cliquez sur **OK** pour démarrer la mise à jour des prévisions.</span><span class="sxs-lookup"><span data-stu-id="4b851-160">Select **OK** to start the forecast update.</span></span>


<span data-ttu-id="4b851-161">L'illustration suivante présente un exemple de la boîte de dialogue **Mettre à jour les prévisions de l'ordre de travail**.</span><span class="sxs-lookup"><span data-stu-id="4b851-161">The illustration below shows an example of the **Update work order forecast** dialog.</span></span>

![Figure 2](media/07-work-orders.png)
