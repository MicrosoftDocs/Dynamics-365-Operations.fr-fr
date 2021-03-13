---
title: Créer des budgets de maintenance
description: Cette rubrique explique comment créer un budget de maintenance dans le module Gestion des actifs.
author: josaw1
manager: tfehr
ms.date: 08/13/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EntAssetBudgetLineAdjust, EntAssetBudget, EntAssetBudgetRecalc, EntAssetBudgetCopy, EntAssetBudgetLine, EntAssetBudgetCreate, EntAssetBudgetApprove, EntAssetBudgetCalculateActualCost
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: riluan
ms.search.validFrom: 2019-08-30
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 602a00060c1e56285d9954981d019bececaf90fd
ms.sourcegitcommit: deac22ba5377a912d93fe408c5ae875706378c2d
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/16/2021
ms.locfileid: "5020987"
---
# <a name="create-maintenance-budgets"></a><span data-ttu-id="e3303-103">Créer des budgets de maintenance</span><span class="sxs-lookup"><span data-stu-id="e3303-103">Create maintenance budgets</span></span>

[!include [banner](../../includes/banner.md)]

 



<span data-ttu-id="e3303-104">Les budgets de maintenance sont utilisés pour fournir une vue d'ensemble des coûts prévus pour la maintenance préventive.</span><span class="sxs-lookup"><span data-stu-id="e3303-104">Maintenance budgets are used to provide an overview of expected costs for preventive maintenance.</span></span> <span data-ttu-id="e3303-105">Les lignes de budget sont calculées en fonction des lignes du programme de maintenance ayant une date de début prévue pendant la période de budget.</span><span class="sxs-lookup"><span data-stu-id="e3303-105">Budget lines are calculated based on maintenance schedule lines that have an expected start date during the budget period.</span></span>

<span data-ttu-id="e3303-106">Les budgets de maintenance sont basés sur les types de coûts utilisés dans le module Gestion des actifs : **Préventif**, **Correctif** et **Investissement**.</span><span class="sxs-lookup"><span data-stu-id="e3303-106">Maintenance budgets are based on the cost types that are used in Asset Management: **Preventive**, **Corrective**, and **Investment**.</span></span> <span data-ttu-id="e3303-107">Les coûts budgétaires pour la maintenance d'investissement sont inclus pour les actifs actifs qui ont une date de remplacement au cours de la période budgétaire et une valeur de remplacement associée.</span><span class="sxs-lookup"><span data-stu-id="e3303-107">Budget costs for investment maintenance are included for active assets that have a replacement date during the budget period and a related replacement value.</span></span> <span data-ttu-id="e3303-108">Les coûts budgétaires pour la maintenance corrective sont inclus si une ancienne date de correction est incluse dans le calcul du budget.</span><span class="sxs-lookup"><span data-stu-id="e3303-108">Budget costs for corrective maintenance are included if a past corrective date is included in the budget calculation.</span></span> <span data-ttu-id="e3303-109">Dans ce cas, les coûts correctifs d'une période précédente sont calculés pour la même période future que celle pour laquelle vous calculez le budget de maintenance.</span><span class="sxs-lookup"><span data-stu-id="e3303-109">In that case, corrective costs from an earlier period are calculated for the same future period that you calculate the maintenance budget for.</span></span>

## <a name="create-a-maintenance-budget"></a><span data-ttu-id="e3303-110">Créer un budget de maintenance</span><span class="sxs-lookup"><span data-stu-id="e3303-110">Create a maintenance budget</span></span>

1. <span data-ttu-id="e3303-111">Sélectionnez **Gestion des actifs** \> **Recherches** \> **Budget de maintenance** \> **Budget**.</span><span class="sxs-lookup"><span data-stu-id="e3303-111">Select **Asset management** \> **Inquiries** \> **Maintenance budget** \> **Budget**.</span></span>
2. <span data-ttu-id="e3303-112">Sélectionnez **Créer un budget**.</span><span class="sxs-lookup"><span data-stu-id="e3303-112">Select **Create budget**.</span></span>
3. <span data-ttu-id="e3303-113">Entrez un ID de budget dans le champ **Budget de maintenance**.</span><span class="sxs-lookup"><span data-stu-id="e3303-113">In the **Maintenance budget** field, enter a budget ID.</span></span>
4. <span data-ttu-id="e3303-114">Entrez une description dans le champ **Description**.</span><span class="sxs-lookup"><span data-stu-id="e3303-114">In the **Description** field, enter a description.</span></span>
4. <span data-ttu-id="e3303-115">Dans le raccourci **Période**, entrez les dates de début et de fin de la période budgétaire dans les champs **Date de début** et **Date de fin**.</span><span class="sxs-lookup"><span data-stu-id="e3303-115">On the **Period** FastTab, in the **From date** and **To date** fields, enter the start and end dates of the budget period.</span></span>
5. <span data-ttu-id="e3303-116">Pour inclure les coûts budgétaires correctifs calculés sur la base des coûts réels d'une période précédente, entrez la date de début de la période dans laquelle ces coûts doivent être inclus dans le champ **Date de début corrective**.</span><span class="sxs-lookup"><span data-stu-id="e3303-116">To include corrective budget costs that are calculated on the basis of actual costs from a previous period, in the **Corrective from date** field, enter the start date of the period that those costs should be included from.</span></span>
6. <span data-ttu-id="e3303-117">En fonction du niveau de détail requis dans le budget, définissez les options appropriées sur les cinq raccourcis **Grouper par**.</span><span class="sxs-lookup"><span data-stu-id="e3303-117">Depending on the level of detail that is required in the budget, set the relevant options on the five **Group by** FastTabs.</span></span>
7. <span data-ttu-id="e3303-118">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="e3303-118">Select **OK**.</span></span>
8. <span data-ttu-id="e3303-119">Sélectionnez **Lignes de budget** pour ouvrir la page **Lignes de budget de maintenance**, où vous pouvez afficher toutes les lignes de budget qui ont été créées pour la période.</span><span class="sxs-lookup"><span data-stu-id="e3303-119">Select **Budget lines** to open **Maintenance budget lines** page, where you can view all the budget lines that have been created for the period.</span></span>
9. <span data-ttu-id="e3303-120">Pour approuver le budget, sélectionnez-le dans la page **Budgets de maintenance**, puis sélectionnez **Approuver**.</span><span class="sxs-lookup"><span data-stu-id="e3303-120">To approve the budget, select it on the **Maintenance budgets** page, and then select **Approve**.</span></span> <span data-ttu-id="e3303-121">Puis, dans la boîte de dialogue **Approuver le budget**, sélectionnez **OK**.</span><span class="sxs-lookup"><span data-stu-id="e3303-121">Then, in the **Approve budget** dialog box, select **OK**.</span></span> <span data-ttu-id="e3303-122">Votre nom est alors entré dans le champ **Approuvé par** sur la page **Budgets de maintenance**.</span><span class="sxs-lookup"><span data-stu-id="e3303-122">Your name is entered in the **Approved by** field on the **Maintenance budgets** page.</span></span>

    > [!NOTE]
    > <span data-ttu-id="e3303-123">Après avoir approuvé un budget de maintenance, vous ne pouvez pas recalculer ou ajuster les lignes associées sur la page **Lignes de budget de maintenance** à moins de supprimer d'abord l'approbation.</span><span class="sxs-lookup"><span data-stu-id="e3303-123">After you've approved a maintenance budget, you can't recalculate or adjust the related lines on the **Maintenance budget lines** page unless you first remove the approval.</span></span> <span data-ttu-id="e3303-124">Pour supprimer l'approbation d'un budget de maintenance, sélectionnez-le dans la page **Budgets de maintenance**, puis sélectionnez **Approuver**.</span><span class="sxs-lookup"><span data-stu-id="e3303-124">To remove the approval of a maintenance budget, select it on the **Maintenance budgets** page, and then select **Approve**.</span></span> <span data-ttu-id="e3303-125">Puis, dans la boîte de dialogue **Approuver le budget**, sélectionnez **OK**.</span><span class="sxs-lookup"><span data-stu-id="e3303-125">Then, in the **Approve budget** dialog box, select **OK**.</span></span>

![Budgets de maintenance](media/01-maintenance-budgets.png)

<span data-ttu-id="e3303-127">Vous pouvez également créer un budget de maintenance en copiant un budget existant.</span><span class="sxs-lookup"><span data-stu-id="e3303-127">You can also create a new maintenance budget by copying an existing budget.</span></span> <span data-ttu-id="e3303-128">Sur la page **Budgets de maintenance**, sélectionnez le budget à copier, puis sélectionnez **Copier**.</span><span class="sxs-lookup"><span data-stu-id="e3303-128">On the **Maintenance budgets** page, select the budget to copy, and then select **Copy**.</span></span> <span data-ttu-id="e3303-129">Cette approche est utile si, par exemple, vous avez créé un budget pour un mois et que vous souhaitez le copier sur d'autres mois.</span><span class="sxs-lookup"><span data-stu-id="e3303-129">This approach is useful if, for example, you've created a budget for one month and want to copy it to other months.</span></span>

> [!NOTE]
> <span data-ttu-id="e3303-130">Le budget de maintenance calcule seulement les coûts budgétaires selon les lignes du programme de maintenance.</span><span class="sxs-lookup"><span data-stu-id="e3303-130">The maintenance budget calculates only budget costs based on maintenance schedule lines.</span></span> <span data-ttu-id="e3303-131">Pour calculer les coûts réels pour la même période, vous pouvez effectuer ce calcul dans la page **Contrôle des coûts d'actif**.</span><span class="sxs-lookup"><span data-stu-id="e3303-131">To calculate actual costs for the same period, you can do that calculation on the **Asset cost control** page.</span></span> 
