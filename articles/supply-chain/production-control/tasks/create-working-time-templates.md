---
title: Création de modèles de temps de travail
description: Les modèles de temps de travail définissent les heures de travail au cours d'une semaine et permettent de générer des temps de travail pour une période.
author: sorenva
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: OpResLifeCycleManagementWorkspace, WorkTimeTable, WorkTimeCopyDayDialog, WorkPeriodTemplate
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: sorenand
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 10e8e43900fd25f0051124d761dc7b06d4f9313a
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/15/2021
ms.locfileid: "5006814"
---
# <a name="create-working-time-templates"></a><span data-ttu-id="cb279-103">Création de modèles de temps de travail</span><span class="sxs-lookup"><span data-stu-id="cb279-103">Create working time templates</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="cb279-104">Les modèles de temps de travail définissent les heures de travail au cours d'une semaine et permettent de générer des temps de travail pour une période.</span><span class="sxs-lookup"><span data-stu-id="cb279-104">Working time templates define the working hours throughout a week and are used to generate working times for a period of time.</span></span> <span data-ttu-id="cb279-105">Cette procédure vous indique comment définir un modèle de temps de travail à l'aide des propriétés de la planification du temps de travail pour classer les intervalles de temps de travail par catégorie.</span><span class="sxs-lookup"><span data-stu-id="cb279-105">This procedure shows you how to define a working time template using working time scheduling properties for categorizing working time intervals.</span></span> <span data-ttu-id="cb279-106">Vous pouvez parcourir cette procédure dans la société fictive USMF ou utiliser vos propres données.</span><span class="sxs-lookup"><span data-stu-id="cb279-106">You can walk through this procedure in demo data company USMF, or using your own data.</span></span>

1. <span data-ttu-id="cb279-107">Accédez à Tous les espaces de travail > Gestion des cycles de vie des ressources.</span><span class="sxs-lookup"><span data-stu-id="cb279-107">Go to All workspaces > Resource lifecycle management.</span></span>
2. <span data-ttu-id="cb279-108">Cliquez sur Modèles de temps de travail.</span><span class="sxs-lookup"><span data-stu-id="cb279-108">Click Working time templates.</span></span>

## <a name="create-working-time-template"></a><span data-ttu-id="cb279-109">Créer un modèle de temps de travail</span><span class="sxs-lookup"><span data-stu-id="cb279-109">Create working time template</span></span>
1. <span data-ttu-id="cb279-110">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="cb279-110">Click New.</span></span>
2. <span data-ttu-id="cb279-111">Dans le champ Modèle de temps de travail, tapez une valeur.</span><span class="sxs-lookup"><span data-stu-id="cb279-111">In the Working time template field, type a value.</span></span>
3. <span data-ttu-id="cb279-112">Tapez une valeur dans le champ Nom.</span><span class="sxs-lookup"><span data-stu-id="cb279-112">In the Name field, type a value.</span></span>
4. <span data-ttu-id="cb279-113">Développez la section Lundi.</span><span class="sxs-lookup"><span data-stu-id="cb279-113">Expand the Monday section.</span></span>
5. <span data-ttu-id="cb279-114">Cliquez sur Ajouter.</span><span class="sxs-lookup"><span data-stu-id="cb279-114">Click Add.</span></span>
6. <span data-ttu-id="cb279-115">Dans le champ De, entrez une heure.</span><span class="sxs-lookup"><span data-stu-id="cb279-115">In the From field, enter a time.</span></span>
    * <span data-ttu-id="cb279-116">Spécifiez l'heure à laquelle le travail commence le matin.</span><span class="sxs-lookup"><span data-stu-id="cb279-116">Specify the time when work begins in the morning.</span></span>  
7. <span data-ttu-id="cb279-117">Dans le champ À, entrez une heure.</span><span class="sxs-lookup"><span data-stu-id="cb279-117">In the To field, enter a time.</span></span>
    * <span data-ttu-id="cb279-118">Spécifiez l'heure à laquelle les collaborateurs prennent leur pause déjeuner.</span><span class="sxs-lookup"><span data-stu-id="cb279-118">Specify the time when workers break for lunch.</span></span>  
8. <span data-ttu-id="cb279-119">Cliquez sur Ajouter.</span><span class="sxs-lookup"><span data-stu-id="cb279-119">Click Add.</span></span>
9. <span data-ttu-id="cb279-120">Dans le champ De, entrez une heure.</span><span class="sxs-lookup"><span data-stu-id="cb279-120">In the From field, enter a time.</span></span>
    * <span data-ttu-id="cb279-121">Spécifiez l'heure à laquelle le travail reprend après le déjeuner.</span><span class="sxs-lookup"><span data-stu-id="cb279-121">Specify the time when work resumes after lunch.</span></span>  
10. <span data-ttu-id="cb279-122">Dans le champ À, entrez une heure.</span><span class="sxs-lookup"><span data-stu-id="cb279-122">In the To field, enter a time.</span></span>
    * <span data-ttu-id="cb279-123">Spécifiez la fin de la journée de travail.</span><span class="sxs-lookup"><span data-stu-id="cb279-123">Specify the end of the work day.</span></span>  

## <a name="replicate-working-times-to-all-week-days"></a><span data-ttu-id="cb279-124">Répliquer les temps de travail à tous les jours de la semaine</span><span class="sxs-lookup"><span data-stu-id="cb279-124">Replicate working times to all week days</span></span>
1. <span data-ttu-id="cb279-125">Cliquez sur Copier jour</span><span class="sxs-lookup"><span data-stu-id="cb279-125">Click Copy day.</span></span>
    * <span data-ttu-id="cb279-126">Copiez les définitions de temps de travail de lundi à mardi.</span><span class="sxs-lookup"><span data-stu-id="cb279-126">Copy the working times definitions from Monday to Tuesday.</span></span>  
2. <span data-ttu-id="cb279-127">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="cb279-127">Click OK.</span></span>
3. <span data-ttu-id="cb279-128">Cliquez sur Copier jour</span><span class="sxs-lookup"><span data-stu-id="cb279-128">Click Copy day.</span></span>
    * <span data-ttu-id="cb279-129">Copiez les définitions de temps de travail de lundi à mercredi.</span><span class="sxs-lookup"><span data-stu-id="cb279-129">Copy the working times definitions from Monday to Wednesday.</span></span>  
4. <span data-ttu-id="cb279-130">Dans le champ Au, sélectionnez une option.</span><span class="sxs-lookup"><span data-stu-id="cb279-130">In the To weekday field, select an option.</span></span>
5. <span data-ttu-id="cb279-131">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="cb279-131">Click OK.</span></span>
6. <span data-ttu-id="cb279-132">Cliquez sur Copier jour</span><span class="sxs-lookup"><span data-stu-id="cb279-132">Click Copy day.</span></span>
    * <span data-ttu-id="cb279-133">Copiez les définitions de temps de travail de lundi à jeudi.</span><span class="sxs-lookup"><span data-stu-id="cb279-133">Copy the working times definitions from Monday to Thursday.</span></span>  
7. <span data-ttu-id="cb279-134">Dans le champ Au, sélectionnez une option.</span><span class="sxs-lookup"><span data-stu-id="cb279-134">In the To weekday field, select an option.</span></span>
8. <span data-ttu-id="cb279-135">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="cb279-135">Click OK.</span></span>
9. <span data-ttu-id="cb279-136">Cliquez sur Copier jour</span><span class="sxs-lookup"><span data-stu-id="cb279-136">Click Copy day.</span></span>
    * <span data-ttu-id="cb279-137">Copiez les définitions de temps de travail de lundi à vendredi.</span><span class="sxs-lookup"><span data-stu-id="cb279-137">Copy the working times definitions from Monday to Friday.</span></span>  
10. <span data-ttu-id="cb279-138">Dans le champ Au, sélectionnez une option.</span><span class="sxs-lookup"><span data-stu-id="cb279-138">In the To weekday field, select an option.</span></span>
11. <span data-ttu-id="cb279-139">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="cb279-139">Click OK.</span></span>

## <a name="define-time-slots-for-special-operations"></a><span data-ttu-id="cb279-140">Définir des créneaux horaires pour les opérations spéciales</span><span class="sxs-lookup"><span data-stu-id="cb279-140">Define time slots for special operations</span></span>
1. <span data-ttu-id="cb279-141">Développez la section Vendredi.</span><span class="sxs-lookup"><span data-stu-id="cb279-141">Expand the Friday section.</span></span>
2. <span data-ttu-id="cb279-142">Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="cb279-142">In the list, find and select the desired record.</span></span>
3. <span data-ttu-id="cb279-143">Dans le champ Propriété, saisissez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="cb279-143">In the Property field, enter or select a value.</span></span>
4. <span data-ttu-id="cb279-144">Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="cb279-144">In the list, find and select the desired record.</span></span>
5. <span data-ttu-id="cb279-145">Dans le champ Propriété, saisissez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="cb279-145">In the Property field, enter or select a value.</span></span>

## <a name="mark-weekend-days-as-closed-for-pickup"></a><span data-ttu-id="cb279-146">Marquer les jours de week-end comme clôturés pour le prélèvement</span><span class="sxs-lookup"><span data-stu-id="cb279-146">Mark weekend days as closed for pickup</span></span>
1. <span data-ttu-id="cb279-147">Développez la section Samedi.</span><span class="sxs-lookup"><span data-stu-id="cb279-147">Expand the Saturday section.</span></span>
2. <span data-ttu-id="cb279-148">Sélectionnez Oui dans le champ Clôturé pour prélèvement.</span><span class="sxs-lookup"><span data-stu-id="cb279-148">Select Yes in the Closed for pickup field.</span></span>
3. <span data-ttu-id="cb279-149">Développez la section Dimanche.</span><span class="sxs-lookup"><span data-stu-id="cb279-149">Expand the Sunday section.</span></span>
4. <span data-ttu-id="cb279-150">Sélectionnez Oui dans le champ Clôturé pour prélèvement.</span><span class="sxs-lookup"><span data-stu-id="cb279-150">Select Yes in the Closed for pickup field.</span></span>

