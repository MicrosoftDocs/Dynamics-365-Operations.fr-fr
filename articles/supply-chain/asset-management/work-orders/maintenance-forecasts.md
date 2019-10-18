---
title: Prévisions en matière de maintenance
description: Cette rubrique explique les prévisions en matière de maintenance dans le module Gestion des actifs.
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
ms.openlocfilehash: 383c910b40199f2da863144c6dc85a579d0091e9
ms.sourcegitcommit: f87de0f949b5d60993b19e0f61297f02d42b5bef
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/24/2019
ms.locfileid: "2024497"
---
# <a name="maintenance-forecasts"></a><span data-ttu-id="83e6d-103">Prévisions en matière de maintenance</span><span class="sxs-lookup"><span data-stu-id="83e6d-103">Maintenance forecasts</span></span>

[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]


<span data-ttu-id="83e6d-104">Lorsque vous créez un ordre de travail, vous créez des tâches de l'ordre de travail avec des actifs et des types de tâches de maintenance associés.</span><span class="sxs-lookup"><span data-stu-id="83e6d-104">When you create a work order, you create work order jobs with related assets and maintenance job types.</span></span> <span data-ttu-id="83e6d-105">Lorsque vous sélectionnez un type de tâche de maintenance contenant les prévisions en matière de maintenance, les prévisions sont automatiquement copiées vers l'ordre de travail.</span><span class="sxs-lookup"><span data-stu-id="83e6d-105">When you select a maintenance job type containing maintenance forecasts, the forecasts are automatically copied to the work order.</span></span>

<span data-ttu-id="83e6d-106">Vous pouvez être en mesure d'ajouter ou de supprimer des lignes de prévisions sur un ordre de travail.</span><span class="sxs-lookup"><span data-stu-id="83e6d-106">You may be able to add or delete forecast lines on a work order.</span></span> <span data-ttu-id="83e6d-107">La configuration d'un état du cycle de vie de l'ordre de travail, le type de projet associé et les règles de stade liées au type de projet déterminent si vous êtes en mesure d'ajouter ou de modifier les lignes de prévision.</span><span class="sxs-lookup"><span data-stu-id="83e6d-107">The setup of a work order lifecycle state, the related project type, and the stage rules related to the project type determines if you are able to add or edit forecast lines.</span></span> 

1. <span data-ttu-id="83e6d-108">Cliquez sur **Gestion des actifs** > **Commun** > **Ordre de travail** > **Tous les ordres de travail** ou **Ordres de travail actifs**.</span><span class="sxs-lookup"><span data-stu-id="83e6d-108">Click **Asset management** > **Common** > **Work orders** > **All work orders** or **Active work orders**.</span></span>

2. <span data-ttu-id="83e6d-109">Sélectionnez l'ordre de travail dans la liste et cliquez sur **Prévisions**.</span><span class="sxs-lookup"><span data-stu-id="83e6d-109">Select the work order in the list, and click **Forecast**.</span></span> <span data-ttu-id="83e6d-110">Dans **Prévisions en matière de maintenance de l'ordre de travail**, les lignes de prévision du type de tâche de maintenance sélectionné sur la tâche de l'ordre de travail sont affichées.</span><span class="sxs-lookup"><span data-stu-id="83e6d-110">In **Work order maintenance forecast**, forecast lines from the maintenance job type selected on the work order job are displayed.</span></span>


## <a name="add-hours-forecast-to-a-work-order"></a><span data-ttu-id="83e6d-111">Ajouter des prévisions horaires à un ordre de travail</span><span class="sxs-lookup"><span data-stu-id="83e6d-111">Add hours forecast to a work order</span></span>

1. <span data-ttu-id="83e6d-112">Sélectionnez la tâche de l'ordre de travail auquel vous souhaitez ajouter une prévision.</span><span class="sxs-lookup"><span data-stu-id="83e6d-112">Select the work order job to which you want to add a forecast.</span></span>

2. <span data-ttu-id="83e6d-113">Dans l'organisateur **Heures**, cliquez sur **Ajouter** pour créer une ligne.</span><span class="sxs-lookup"><span data-stu-id="83e6d-113">On the **Hours** FastTab, click **Add** to create a new line.</span></span>

3. <span data-ttu-id="83e6d-114">Sélectionnez une catégorie dans le champ **Catégorie**.</span><span class="sxs-lookup"><span data-stu-id="83e6d-114">Select a category in the **Category** field.</span></span>

4. <span data-ttu-id="83e6d-115">Insérez le nombre d'heures prévues dans le champ **Heures**.</span><span class="sxs-lookup"><span data-stu-id="83e6d-115">Insert number of forecasted hours in the **Hours** field.</span></span>

5. <span data-ttu-id="83e6d-116">Dans le champ **Propriété de ligne**, sélectionnez le type de frais à utiliser sur la ligne.</span><span class="sxs-lookup"><span data-stu-id="83e6d-116">In the **Line property** field, select the charge type to be used on the line.</span></span>


## <a name="add-items-forecast-to-a-work-order"></a><span data-ttu-id="83e6d-117">Ajouter des prévisions d'articles à un ordre de travail</span><span class="sxs-lookup"><span data-stu-id="83e6d-117">Add items forecast to a work order</span></span>

<span data-ttu-id="83e6d-118">Il existe trois façons d'ajouter des articles à des prévisions en matière de maintenance à un ordre de travail : vous pouvez créer des lignes pour les articles (pièces détachées) qui ne sont pas inclus dans la liste des pièces détachées ou la nomenclature des actifs, vous pouvez sélectionner des pièces détachées depuis la liste des pièces détachées approuvées, et vous pouvez sélectionner les articles depuis la nomenclature des actifs.</span><span class="sxs-lookup"><span data-stu-id="83e6d-118">There are three ways to add items to a work order maintenance forecast: You can create lines for items (spare parts) that are not included in the spare parts list or asset BOM, you can select spare parts from the approved spare parts list, and you can select items from the asset BOM.</span></span>

1. <span data-ttu-id="83e6d-119">Sélectionnez la tâche de l'ordre de travail auquel vous souhaitez ajouter une prévision.</span><span class="sxs-lookup"><span data-stu-id="83e6d-119">Select the work order job to which you want to add a forecast.</span></span>

2. <span data-ttu-id="83e6d-120">Sélectionnez l'organisateur **Articles**.</span><span class="sxs-lookup"><span data-stu-id="83e6d-120">Select the **Items** FastTab.</span></span>

3. <span data-ttu-id="83e6d-121">Cliquez sur **Ajouter** pour créer une ligne pour une pièce détachée qui n'est pas sur la liste des pièces détachées ou la liste de nomenclature des actifs.</span><span class="sxs-lookup"><span data-stu-id="83e6d-121">Click **Add** to create a new line for a spare part that is not on the spare parts list or the asset BOM list.</span></span>

4. <span data-ttu-id="83e6d-122">Sélectionnez l'élément dans le champ **Numéro d'article**.</span><span class="sxs-lookup"><span data-stu-id="83e6d-122">Select the item in the **Item number** field.</span></span>

5. <span data-ttu-id="83e6d-123">Insérez la quantité dans le champ **Quantité vendue**, puis sélectionnez une unité de quantité dans le champ **Unité**.</span><span class="sxs-lookup"><span data-stu-id="83e6d-123">Insert quantity in the **Sales quantity** field, and select a quantity unit in the **Unit** field.</span></span>

6. <span data-ttu-id="83e6d-124">Insérez le prix de revient et la devise dans les champs appropriés, puis sélectionnez **Propriété de ligne**.</span><span class="sxs-lookup"><span data-stu-id="83e6d-124">Insert cost price and currency in the relevant fields, and select a **Line property**.</span></span>

7. <span data-ttu-id="83e6d-125">Si vous souhaitez modifier la liste des dimensions affichées dans les lignes d'article, cliquez sur **Stock** > **Dimensions d'affichage**, sélectionnez les dimensions, et sélectionnez « Oui » sur le bouton à bascule **Enregistrer le paramétrage**.</span><span class="sxs-lookup"><span data-stu-id="83e6d-125">If you want to change the list of dimensions displayed on the item lines, click **Inventory** > **Display dimensions**, select the dimensions, and select "Yes" on the **Save setup** toggle button.</span></span>

8. <span data-ttu-id="83e6d-126">Si vous souhaitez ajouter une pièce détachée approuvée aux prévisions en matière de maintenance, cliquez sur **Ajoutez des pièces détachées**, sélectionnez la pièce détachée, modifiez les informations associées au besoin, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="83e6d-126">If you want to add an approved spare part to the maintenance forecast, click **Add spare parts**, select the spare part, edit related information if required, and click **OK**.</span></span>

9. <span data-ttu-id="83e6d-127">Si vous voulez ajouter des articles de nomenclature des actifs aux prévisions, cliquez sur **Ajouter des articles de nomenclature**, sélectionnez l'article, modifiez les informations associées au besoin, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="83e6d-127">If you want to add asset BOM items to the forecast, click **Add BOM items**, select the item, edit related information if required, and click **OK**.</span></span>

10. <span data-ttu-id="83e6d-128">Cliquez sur **Cas d'emploi d'article** si vous souhaitez obtenir une vue d'ensemble de l'emplacement d'utilisation de l'article sur la ligne sélectionnée dans le module Gestion des actifs, en ce qui concerne les actifs, le type de tâche de maintenance par défaut, les pièces détachées et les ordres de travail.</span><span class="sxs-lookup"><span data-stu-id="83e6d-128">Click **Item where used** if you want to get an overview of where the item on the selected line is used in Asset Management in relation to assets, maintenance job type defaults, spare parts, and work orders.</span></span> 



## <a name="add-expense-forecast-to-a-work-order"></a><span data-ttu-id="83e6d-129">Ajouter des prévisions de dépense à un ordre de travail</span><span class="sxs-lookup"><span data-stu-id="83e6d-129">Add expense forecast to a work order</span></span>

1. <span data-ttu-id="83e6d-130">Cette rubrique explique comment ajouter des prévisions de dépense à un ordre de travail.</span><span class="sxs-lookup"><span data-stu-id="83e6d-130">This topic explains how to add an expense forecast to a work order.</span></span> <span data-ttu-id="83e6d-131">À gauche de l'écran, sélectionnez la tâche de l'ordre de travail à laquelle vous souhaitez ajouter une prévision.</span><span class="sxs-lookup"><span data-stu-id="83e6d-131">In the left-hand side of the form, select the work order job to which you want to add a forecast.</span></span>

2. <span data-ttu-id="83e6d-132">Sélectionnez l'organisateur **Dépense**.</span><span class="sxs-lookup"><span data-stu-id="83e6d-132">Select the **Expense** FastTab.</span></span>

3. <span data-ttu-id="83e6d-133">Cliquez sur **Ajouter** pour créer une ligne.</span><span class="sxs-lookup"><span data-stu-id="83e6d-133">Click **Add** to create a new line.</span></span>

4. <span data-ttu-id="83e6d-134">Sélectionnez une catégorie dans le champ **Catégorie**.</span><span class="sxs-lookup"><span data-stu-id="83e6d-134">Select a category in the **Category** field.</span></span>

5. <span data-ttu-id="83e6d-135">Insérez la quantité dans le champ **Quantité**.</span><span class="sxs-lookup"><span data-stu-id="83e6d-135">Insert quantity in the **Quantity** field.</span></span>

6. <span data-ttu-id="83e6d-136">Insérez le prix de revient, la devise de vente et le prix de vente dans les champs appropriés.</span><span class="sxs-lookup"><span data-stu-id="83e6d-136">Insert cost price, sales currency, and sales price in the relevant fields.</span></span>

7. <span data-ttu-id="83e6d-137">Dans le champ **Propriété de ligne**, sélectionnez le type de frais à utiliser sur la ligne.</span><span class="sxs-lookup"><span data-stu-id="83e6d-137">In the **Line property** field, select the charge type to be used on the line.</span></span>

>[!NOTE]
><span data-ttu-id="83e6d-138">Dans l'organisateur **Totaux de prévisions de maintenance**, vous voyez une vue d'ensemble du nombre de lignes créées sous chaque onglet, pour la tâche de l'ordre de travail sélectionnée et pour l'ordre de travail.</span><span class="sxs-lookup"><span data-stu-id="83e6d-138">On the **Maintenance forecast totals** FastTab, you can see an overview of the number of lines created on each tab, for the selected work order job and for the work order.</span></span> <span data-ttu-id="83e6d-139">En outre, vous pouvez également voir une somme des heures de travail prévues pour la tâche de l'ordre de travail et pour l'ordre de travail.</span><span class="sxs-lookup"><span data-stu-id="83e6d-139">Also, you can see a sum of forecasted work hours for the work order job and for the work order.</span></span>

![Figure 1](media/06-work-orders.png)


## <a name="automatic-update-of-work-order-forecasts"></a><span data-ttu-id="83e6d-141">Mise à jour automatique des prévisions de l'ordre de travail</span><span class="sxs-lookup"><span data-stu-id="83e6d-141">Automatic update of work order forecasts</span></span>

<span data-ttu-id="83e6d-142">Dans le module Gestion des actifs, vous pouvez automatiquement mettre à jour les modifications dans les prévisions de l'ordre de travail concernant les coûts horaires, les coûts d'article et les dépenses, qui ont été mises à jour dans d'autres modules.</span><span class="sxs-lookup"><span data-stu-id="83e6d-142">In Asset Management, you can automatically update any changes in work order forecasts regarding hour costs, item costs, and expenses, which have been updated in other modules.</span></span> <span data-ttu-id="83e6d-143">Cela est possible pour veiller à ce que les derniers prix de revient soient toujours utilisés dans vos prévisions d'ordre de travail.</span><span class="sxs-lookup"><span data-stu-id="83e6d-143">This is done to ensure that the latest cost prices are always used in your work order forecasts.</span></span> <span data-ttu-id="83e6d-144">Il est également possible d'effectuer des mises à jour similaires pour [prévisions de type de tâche de maintenance](../setup-for-work-orders/job-groups-and-job-types-variants-trades-and-checklists.md).</span><span class="sxs-lookup"><span data-stu-id="83e6d-144">It is also possible to make similar updates for [maintenance job type forecasts](../setup-for-work-orders/job-groups-and-job-types-variants-trades-and-checklists.md).</span></span>

1. <span data-ttu-id="83e6d-145">Cliquez sur **Gestion des actifs** > **Périodique** > **Prévisions** > **Mettre à jour les prévisions de l'ordre de travail**.</span><span class="sxs-lookup"><span data-stu-id="83e6d-145">Click **Asset management** > **Periodic** > **Forecast** > **Update work order forecast**.</span></span>

2. <span data-ttu-id="83e6d-146">Dans la boîte de dialogue de menu déroulant **Mettre à jour les prévisions de l'ordre de travail**, vous pouvez ajouter des sélections concernant les ordres de travail spécifiques ou des tâches d'ordre de travail, si nécessaire.</span><span class="sxs-lookup"><span data-stu-id="83e6d-146">In the **Update work order forecast** drop-down dialog, you can add selections regarding specific work orders or work order jobs, if required.</span></span> <span data-ttu-id="83e6d-147">Cliquez sur **Filtre** pour effectuer ces sélections.</span><span class="sxs-lookup"><span data-stu-id="83e6d-147">Click **Filter** to make those selections.</span></span>

3. <span data-ttu-id="83e6d-148">Le cas échéant, vous pouvez configurer la mise à jour automatique comme traitement par lots sur l'organisateur **Exécuter à l'arrière-plan**.</span><span class="sxs-lookup"><span data-stu-id="83e6d-148">If required, you can set up the automatic update as a batch job on the **Run in the background** FastTab.</span></span>

4. <span data-ttu-id="83e6d-149">Cliquez sur **OK** pour démarrer la mise à jour des prévisions.</span><span class="sxs-lookup"><span data-stu-id="83e6d-149">Click **OK** to start the forecast update.</span></span>


![Figure 2](media/07-work-orders.png)

