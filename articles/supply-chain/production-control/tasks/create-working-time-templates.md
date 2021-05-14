---
title: Création de modèles de temps de travail
description: Les modèles de temps de travail définissent les heures de travail au cours d’une semaine et permettent de générer des temps de travail pour une période.
author: sorenva
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: OpResLifeCycleManagementWorkspace, WorkTimeTable, WorkTimeCopyDayDialog, WorkPeriodTemplate
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: sorenand
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: ed1981b7c1427c902f237f0aa95f63e89bc345ab
ms.sourcegitcommit: fa99a36c3d30d0c0577fd3f63ed6bf2f71599e40
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/20/2021
ms.locfileid: "5920927"
---
# <a name="create-working-time-templates"></a><span data-ttu-id="d9bdf-103">Création de modèles de temps de travail</span><span class="sxs-lookup"><span data-stu-id="d9bdf-103">Create working time templates</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="d9bdf-104">Les modèles de temps de travail définissent les heures de travail au cours d’une semaine et permettent de générer des temps de travail pour une période.</span><span class="sxs-lookup"><span data-stu-id="d9bdf-104">Working time templates define the working hours throughout a week and are used to generate working times for a period of time.</span></span> <span data-ttu-id="d9bdf-105">Cette procédure vous indique comment définir un modèle de temps de travail à l’aide des propriétés de la planification du temps de travail pour classer les intervalles de temps de travail par catégorie.</span><span class="sxs-lookup"><span data-stu-id="d9bdf-105">This procedure shows you how to define a working time template using working time scheduling properties for categorizing working time intervals.</span></span> <span data-ttu-id="d9bdf-106">Vous pouvez parcourir cette procédure dans la société fictive USMF ou utiliser vos propres données.</span><span class="sxs-lookup"><span data-stu-id="d9bdf-106">You can walk through this procedure in demo data company USMF, or using your own data.</span></span>

1. <span data-ttu-id="d9bdf-107">Accédez à **Espaces de travail > Gestion des cycles de vie des ressources**.</span><span class="sxs-lookup"><span data-stu-id="d9bdf-107">Go to **Workspaces > Resource lifecycle management**.</span></span>
1. <span data-ttu-id="d9bdf-108">Sélectionnez **Modèles de temps de travail**.</span><span class="sxs-lookup"><span data-stu-id="d9bdf-108">Select **Working time templates**.</span></span>

## <a name="create-working-time-template"></a><span data-ttu-id="d9bdf-109">Créer un modèle de temps de travail</span><span class="sxs-lookup"><span data-stu-id="d9bdf-109">Create working time template</span></span>

1. <span data-ttu-id="d9bdf-110">Sélectionnez **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="d9bdf-110">Select **New**.</span></span>
1. <span data-ttu-id="d9bdf-111">Dans le champ **Modèle de temps de travail**, tapez une valeur.</span><span class="sxs-lookup"><span data-stu-id="d9bdf-111">In the **Working time template** field, type a value.</span></span>
1. <span data-ttu-id="d9bdf-112">Tapez une valeur dans le champ **Nom**.</span><span class="sxs-lookup"><span data-stu-id="d9bdf-112">In the **Name** field, type a value.</span></span>
1. <span data-ttu-id="d9bdf-113">Développez la section **Lundi**.</span><span class="sxs-lookup"><span data-stu-id="d9bdf-113">Expand the **Monday** section.</span></span>
1. <span data-ttu-id="d9bdf-114">Sélectionnez **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="d9bdf-114">Select **Add**.</span></span>
1. <span data-ttu-id="d9bdf-115">Dans le champ **De**, entrez une heure.</span><span class="sxs-lookup"><span data-stu-id="d9bdf-115">In the **From** field, enter a time.</span></span>
    * <span data-ttu-id="d9bdf-116">Spécifiez l’heure à laquelle le travail commence le matin.</span><span class="sxs-lookup"><span data-stu-id="d9bdf-116">Specify the time when work begins in the morning.</span></span>  
1. <span data-ttu-id="d9bdf-117">Dans le champ **À**, entrez une heure.</span><span class="sxs-lookup"><span data-stu-id="d9bdf-117">In the **To** field, enter a time.</span></span>
    * <span data-ttu-id="d9bdf-118">Spécifiez l’heure à laquelle les collaborateurs prennent leur pause déjeuner.</span><span class="sxs-lookup"><span data-stu-id="d9bdf-118">Specify the time when workers break for lunch.</span></span>  
1. <span data-ttu-id="d9bdf-119">Sélectionnez **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="d9bdf-119">Select **Add**.</span></span>
1. <span data-ttu-id="d9bdf-120">Dans le champ **De**, entrez une heure.</span><span class="sxs-lookup"><span data-stu-id="d9bdf-120">In the **From** field, enter a time.</span></span>
    * <span data-ttu-id="d9bdf-121">Spécifiez l’heure à laquelle le travail reprend après le déjeuner.</span><span class="sxs-lookup"><span data-stu-id="d9bdf-121">Specify the time when work resumes after lunch.</span></span>  
1. <span data-ttu-id="d9bdf-122">Dans le champ **À**, entrez une heure.</span><span class="sxs-lookup"><span data-stu-id="d9bdf-122">In the **To** field, enter a time.</span></span>
    * <span data-ttu-id="d9bdf-123">Spécifiez la fin de la journée de travail.</span><span class="sxs-lookup"><span data-stu-id="d9bdf-123">Specify the end of the work day.</span></span>  

## <a name="replicate-working-times-to-all-week-days"></a><span data-ttu-id="d9bdf-124">Répliquer les temps de travail à tous les jours de la semaine</span><span class="sxs-lookup"><span data-stu-id="d9bdf-124">Replicate working times to all week days</span></span>

1. <span data-ttu-id="d9bdf-125">Sélectionnez **Copier jour**.</span><span class="sxs-lookup"><span data-stu-id="d9bdf-125">Select **Copy day**.</span></span>
    * <span data-ttu-id="d9bdf-126">Copiez les définitions de temps de travail de lundi à mardi.</span><span class="sxs-lookup"><span data-stu-id="d9bdf-126">Copy the working times definitions from Monday to Tuesday.</span></span>  
1. <span data-ttu-id="d9bdf-127">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="d9bdf-127">Select **OK**.</span></span>
1. <span data-ttu-id="d9bdf-128">Sélectionnez **Copier jour**.</span><span class="sxs-lookup"><span data-stu-id="d9bdf-128">Select **Copy day**.</span></span>
    * <span data-ttu-id="d9bdf-129">Copiez les définitions de temps de travail de lundi à mercredi.</span><span class="sxs-lookup"><span data-stu-id="d9bdf-129">Copy the working times definitions from Monday to Wednesday.</span></span>  
1. <span data-ttu-id="d9bdf-130">Dans le champ **Au**, sélectionnez une option.</span><span class="sxs-lookup"><span data-stu-id="d9bdf-130">In the **To weekday** field, select an option.</span></span>
1. <span data-ttu-id="d9bdf-131">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="d9bdf-131">Select **OK**.</span></span>
1. <span data-ttu-id="d9bdf-132">Sélectionnez **Copier jour**.</span><span class="sxs-lookup"><span data-stu-id="d9bdf-132">Select **Copy day**.</span></span>
    * <span data-ttu-id="d9bdf-133">Copiez les définitions de temps de travail de lundi à jeudi.</span><span class="sxs-lookup"><span data-stu-id="d9bdf-133">Copy the working times definitions from Monday to Thursday.</span></span>  
1. <span data-ttu-id="d9bdf-134">Dans le champ **Au**, sélectionnez une option.</span><span class="sxs-lookup"><span data-stu-id="d9bdf-134">In the **To weekday** field, select an option.</span></span>
1. <span data-ttu-id="d9bdf-135">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="d9bdf-135">Select **OK**.</span></span>
1. <span data-ttu-id="d9bdf-136">Sélectionnez **Copier jour**.</span><span class="sxs-lookup"><span data-stu-id="d9bdf-136">Select **Copy day**.</span></span>
    * <span data-ttu-id="d9bdf-137">Copiez les définitions de temps de travail de lundi à vendredi.</span><span class="sxs-lookup"><span data-stu-id="d9bdf-137">Copy the working times definitions from Monday to Friday.</span></span>  
1. <span data-ttu-id="d9bdf-138">Dans le champ **Au**, sélectionnez une option.</span><span class="sxs-lookup"><span data-stu-id="d9bdf-138">In the **To weekday** field, select an option.</span></span>
1. <span data-ttu-id="d9bdf-139">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="d9bdf-139">Select **OK**.</span></span>

## <a name="define-time-slots-for-special-operations"></a><span data-ttu-id="d9bdf-140">Définir des créneaux horaires pour les opérations spéciales</span><span class="sxs-lookup"><span data-stu-id="d9bdf-140">Define time slots for special operations</span></span>

1. <span data-ttu-id="d9bdf-141">Développez la section **Vendredi**.</span><span class="sxs-lookup"><span data-stu-id="d9bdf-141">Expand the **Friday** section.</span></span>
1. <span data-ttu-id="d9bdf-142">Dans la liste, recherchez et sélectionnez l’enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="d9bdf-142">In the list, find and select the desired record.</span></span>
1. <span data-ttu-id="d9bdf-143">Dans le champ **Propriété**, saisissez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="d9bdf-143">In the **Property** field, enter or select a value.</span></span>
1. <span data-ttu-id="d9bdf-144">Dans la liste, recherchez et sélectionnez l’enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="d9bdf-144">In the list, find and select the desired record.</span></span>
1. <span data-ttu-id="d9bdf-145">Dans le champ **Propriété**, saisissez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="d9bdf-145">In the **Property** field, enter or select a value.</span></span>

## <a name="mark-weekend-days-as-closed-for-pickup"></a><span data-ttu-id="d9bdf-146">Marquer les jours de week-end comme clôturés pour le prélèvement</span><span class="sxs-lookup"><span data-stu-id="d9bdf-146">Mark weekend days as closed for pickup</span></span>

1. <span data-ttu-id="d9bdf-147">Développez la section **Samedi**.</span><span class="sxs-lookup"><span data-stu-id="d9bdf-147">Expand the **Saturday** section.</span></span>
1. <span data-ttu-id="d9bdf-148">Sélectionnez *Oui* dans le champ **Clôturé pour prélèvement**.</span><span class="sxs-lookup"><span data-stu-id="d9bdf-148">Select *Yes* in the **Closed for pickup** field.</span></span>
1. <span data-ttu-id="d9bdf-149">Développez la section **Dimanche**.</span><span class="sxs-lookup"><span data-stu-id="d9bdf-149">Expand the **Sunday** section.</span></span>
1. <span data-ttu-id="d9bdf-150">Sélectionnez *Oui* dans le champ **Clôturé pour prélèvement**.</span><span class="sxs-lookup"><span data-stu-id="d9bdf-150">Select *Yes* in the **Closed for pickup** field.</span></span>


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]