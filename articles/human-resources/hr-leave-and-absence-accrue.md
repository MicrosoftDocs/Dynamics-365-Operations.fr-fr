---
title: Régulariser les plans de congé et d’absence
description: Vous pouvez provisionner les congés et les absences dans Dynamics 365 Human Resources pour plusieurs employés ou pour un employé individuel.
author: andreabichsel
manager: tfehr
ms.date: 06/01/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: LeavePlanFormPart, LeaveAbsenceWorkspace
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: aed36a38c5d50767b5ac14ae82ca424f0c835ae0
ms.sourcegitcommit: 18e626c49ccfdb12c1484b985e3a275e51f61320
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2021
ms.locfileid: "5116090"
---
# <a name="accrue-leave-and-absence-plans"></a><span data-ttu-id="22b5d-103">Régulariser les plans de congé et d’absence</span><span class="sxs-lookup"><span data-stu-id="22b5d-103">Accrue leave and absence plans</span></span>

<span data-ttu-id="22b5d-104">Vous pouvez provisionner les congés et les absences dans Dynamics 365 Human Resources pour plusieurs employés ou pour un employé individuel.</span><span class="sxs-lookup"><span data-stu-id="22b5d-104">You can accrue leave and absence in Dynamics 365 Human Resources for multiple employees or for an individual.</span></span>

## <a name="accrue-leave-and-absence-for-multiple-employees"></a><span data-ttu-id="22b5d-105">Provisionner les congés et les absences pour plusieurs employés</span><span class="sxs-lookup"><span data-stu-id="22b5d-105">Accrue leave and absence for multiple employees</span></span>

1. <span data-ttu-id="22b5d-106">Dans la page **Plans de congé et d’absence**, sélectionnez l’onglet **Liens**.</span><span class="sxs-lookup"><span data-stu-id="22b5d-106">On the **Leave and absence** page, select the **Links** tab.</span></span>

2. <span data-ttu-id="22b5d-107">Sous **Gérer les congés**, sélectionnez **Provisionner les plans de congé et d’absence**.</span><span class="sxs-lookup"><span data-stu-id="22b5d-107">Under **Manage leave**, select **Accrue leave and absence plans**.</span></span>

3. <span data-ttu-id="22b5d-108">La boîte de dialogue **Régulariser les plans de congé et d’absence** apparaît.</span><span class="sxs-lookup"><span data-stu-id="22b5d-108">The **Accrue leave and absence plans** dialog box appears.</span></span> <span data-ttu-id="22b5d-109">Dans **Provisionner pour le**, sélectionnez **Date du jour** ou **Date personnalisée** et entrez une date personnalisée.</span><span class="sxs-lookup"><span data-stu-id="22b5d-109">In **Accrue as of**, either select **Today's date** or select **Custom date** and enter a custom date.</span></span>

4. <span data-ttu-id="22b5d-110">Si vous souhaitez exécuter des régularisations pour toutes les sociétés, sélectionnez **Toutes les entreprises**.</span><span class="sxs-lookup"><span data-stu-id="22b5d-110">If you want to run accruals for all companies, select **All companies**.</span></span> <span data-ttu-id="22b5d-111">Si vous souhaitez traiter les régularisations pour un plan de congé unique, sélectionnez **Non** pour **Tous les plans**, puis sélectionnez un **Plan de congé**.</span><span class="sxs-lookup"><span data-stu-id="22b5d-111">If you want to process accruals for a single leave plan, select **No** for **All plans**, and then select a **Leave plan**.</span></span> <span data-ttu-id="22b5d-112">Si vous sélectionnez toutes les sociétés, vous ne pouvez pas sélectionner un plan de congé individuel.</span><span class="sxs-lookup"><span data-stu-id="22b5d-112">If you select all companies, you can't select an individual leave plan.</span></span> 

5. <span data-ttu-id="22b5d-113">Si vous souhaitez exécuter le processus de provision en arrière-plan, sélectionnez **Exécuter à l’arrière-plan** et effectuez les tâches suivantes :</span><span class="sxs-lookup"><span data-stu-id="22b5d-113">If you want to run the accrual process in the background, select **Run in the background** and do the following tasks:</span></span>

   1. <span data-ttu-id="22b5d-114">Entrez les informations pour le processus de provision.</span><span class="sxs-lookup"><span data-stu-id="22b5d-114">Enter information for the accrual process.</span></span>

   2. <span data-ttu-id="22b5d-115">Pour configurer une tâche récurrente, sélectionnez **Récurrence**, saisissez les informations de récurrence et sélectionnez **OK**.</span><span class="sxs-lookup"><span data-stu-id="22b5d-115">To set up a recurring job, select **Recurrence**, enter the recurrence information, and the select **OK**.</span></span>

   3. <span data-ttu-id="22b5d-116">Pour configurer une alerte emploi, sélectionnez **Alertes**, sélectionnez les alertes à recevoir, puis sélectionnez **OK**.</span><span class="sxs-lookup"><span data-stu-id="22b5d-116">To set up a job alert, select **Alerts**, select the alerts to receive, and then select **OK**.</span></span>

   4. <span data-ttu-id="22b5d-117">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="22b5d-117">Select **OK**.</span></span> <span data-ttu-id="22b5d-118">Le processus de provisionnement s’exécutera avec les paramètres que vous définissez.</span><span class="sxs-lookup"><span data-stu-id="22b5d-118">The accrual process will run with the parameters you set.</span></span>

## <a name="accrue-leave-and-absence-for-an-employee"></a><span data-ttu-id="22b5d-119">Provisionner les congés et les absences pour un employé</span><span class="sxs-lookup"><span data-stu-id="22b5d-119">Accrue leave and absence for an employee</span></span>

1. <span data-ttu-id="22b5d-120">Dans le dossier de l’employé, sélectionnez **Congé**.</span><span class="sxs-lookup"><span data-stu-id="22b5d-120">On the employee's record, select **Leave**.</span></span>

2. <span data-ttu-id="22b5d-121">Sélectionnez **Provisionner les congés et les absences**.</span><span class="sxs-lookup"><span data-stu-id="22b5d-121">Select **Accrue leave and absence**.</span></span>

3. <span data-ttu-id="22b5d-122">La boîte de dialogue **Régulariser les plans de congé et d’absence** apparaît.</span><span class="sxs-lookup"><span data-stu-id="22b5d-122">The **Accrue leave and absence plans** dialog box appears.</span></span> <span data-ttu-id="22b5d-123">Dans **Provisionner pour le**, sélectionnez **Date du jour** ou **Date personnalisée** et entrez une date personnalisée.</span><span class="sxs-lookup"><span data-stu-id="22b5d-123">In **Accrue as of**, either select **Today's date** or select **Custom date** and enter a custom date.</span></span>

4. <span data-ttu-id="22b5d-124">Si vous souhaitez exécuter des régularisations pour toutes les sociétés, sélectionnez **Toutes les entreprises**.</span><span class="sxs-lookup"><span data-stu-id="22b5d-124">If you want to run accruals for all companies, select **All companies**.</span></span> <span data-ttu-id="22b5d-125">Si vous souhaitez traiter les régularisations pour un plan de congé unique, sélectionnez **Non** pour **Tous les plans**, puis sélectionnez un **Plan de congé**.</span><span class="sxs-lookup"><span data-stu-id="22b5d-125">If you want to process accruals for a single leave plan, select **No** for **All plans**, and then select a **Leave plan**.</span></span> <span data-ttu-id="22b5d-126">Si vous sélectionnez toutes les sociétés, vous ne pouvez pas sélectionner un plan de congé individuel.</span><span class="sxs-lookup"><span data-stu-id="22b5d-126">If you select all companies, you can't select an individual leave plan.</span></span> 

5. <span data-ttu-id="22b5d-127">Si vous souhaitez exécuter le processus de provision en arrière-plan, sélectionnez **Exécuter à l’arrière-plan** et effectuez les tâches suivantes :</span><span class="sxs-lookup"><span data-stu-id="22b5d-127">If you want to run the accrual process in the background, select **Run in the background** and do the following tasks:</span></span>

   1. <span data-ttu-id="22b5d-128">Entrez les informations pour le processus de provision.</span><span class="sxs-lookup"><span data-stu-id="22b5d-128">Enter information for the accrual process.</span></span>

   2. <span data-ttu-id="22b5d-129">Pour configurer une tâche récurrente, sélectionnez **Récurrence**, saisissez les informations de récurrence et sélectionnez **OK**.</span><span class="sxs-lookup"><span data-stu-id="22b5d-129">To set up a recurring job, select **Recurrence**, enter the recurrence information, and the select **OK**.</span></span>

   3. <span data-ttu-id="22b5d-130">Pour configurer une alerte emploi, sélectionnez **Alertes**, sélectionnez les alertes à recevoir, puis sélectionnez **OK**.</span><span class="sxs-lookup"><span data-stu-id="22b5d-130">To set up a job alert, select **Alerts**, select the alerts to receive, and then select **OK**.</span></span>

   4. <span data-ttu-id="22b5d-131">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="22b5d-131">Select **OK**.</span></span> <span data-ttu-id="22b5d-132">Le processus de provisionnement s’exécutera avec les paramètres que vous définissez.</span><span class="sxs-lookup"><span data-stu-id="22b5d-132">The accrual process will run with the parameters you set.</span></span>

## <a name="delete-leave-and-absence-accruals-for-multiple-employees"></a><span data-ttu-id="22b5d-133">Supprimer les régularisations de congé et d’absence pour plusieurs employés</span><span class="sxs-lookup"><span data-stu-id="22b5d-133">Delete leave and absence accruals for multiple employees</span></span>

<span data-ttu-id="22b5d-134">Supprimez les enregistrements de provisions pour un plan et une plage de dates spécifiques.</span><span class="sxs-lookup"><span data-stu-id="22b5d-134">Delete accrual records for a specific plan and date range.</span></span> <span data-ttu-id="22b5d-135">Les dates de provision doivent correspondre à la date du jour ou au lendemain.</span><span class="sxs-lookup"><span data-stu-id="22b5d-135">Accrual dates must be dated today or in the future.</span></span>

1. <span data-ttu-id="22b5d-136">Dans la page **Plans de congé et d’absence**, sélectionnez l’onglet **Liens**.</span><span class="sxs-lookup"><span data-stu-id="22b5d-136">On the **Leave and absence** page, select the **Links** tab.</span></span>

2. <span data-ttu-id="22b5d-137">Sous **Gérer les congés**, sélectionnez **Supprimer les provisions de plans de congé et d’absence**.</span><span class="sxs-lookup"><span data-stu-id="22b5d-137">Under **Manage leave**, select **Delete leave and absence plan accruals**.</span></span>

3. <span data-ttu-id="22b5d-138">Dans la boîte de dialogue **Supprimer les provisions de plans de congé et d’absence**, sélectionnez **Plan de congé**.</span><span class="sxs-lookup"><span data-stu-id="22b5d-138">In the **Delete leave and absence plan accruals** dialog box, select the **Leave plan**.</span></span> 

4. <span data-ttu-id="22b5d-139">Le cas échéant, choisissez **Supprimer les ajustements de solde**.</span><span class="sxs-lookup"><span data-stu-id="22b5d-139">If applicable, choose **Delete balance adjustments**.</span></span>

5. <span data-ttu-id="22b5d-140">Saisissez ou sélectionnez une **Date de provision de congés**.</span><span class="sxs-lookup"><span data-stu-id="22b5d-140">Enter or select a **Leave accrual date**.</span></span> <span data-ttu-id="22b5d-141">Cette date doit être soit aujourd’hui soit une date à venir.</span><span class="sxs-lookup"><span data-stu-id="22b5d-141">This date has to be either today or in the future.</span></span> 

6. <span data-ttu-id="22b5d-142">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="22b5d-142">Select **OK**.</span></span> <span data-ttu-id="22b5d-143">Le processus de régularisation supprimera les provisions et les paramètres que vous définissez.</span><span class="sxs-lookup"><span data-stu-id="22b5d-143">The accrual process will delete accruals with the parameters you set.</span></span> 

## <a name="delete-leave-and-absence-accruals-for-a-single-employee"></a><span data-ttu-id="22b5d-144">Supprimer les provisions de congés et d’absences pour un seul employé</span><span class="sxs-lookup"><span data-stu-id="22b5d-144">Delete leave and absence accruals for a single employee</span></span>

1. <span data-ttu-id="22b5d-145">Dans le dossier de l’employé, sélectionnez **Congé**.</span><span class="sxs-lookup"><span data-stu-id="22b5d-145">On the employee's record, select **Leave**.</span></span>

2. <span data-ttu-id="22b5d-146">Sélectionnez **Supprimer les provisions de plans de congés et d’absences**.</span><span class="sxs-lookup"><span data-stu-id="22b5d-146">Select **Delete leave and absence plan accruals**.</span></span>

3. <span data-ttu-id="22b5d-147">Dans la boîte de dialogue **Supprimer les provisions de plans de congé et d’absence**, sélectionnez **Plan de congé**.</span><span class="sxs-lookup"><span data-stu-id="22b5d-147">In the **Delete leave and absence plan accruals** dialog box, select **Leave plan**.</span></span> 

4. <span data-ttu-id="22b5d-148">Le cas échéant, choisissez **Supprimer les ajustements de solde**.</span><span class="sxs-lookup"><span data-stu-id="22b5d-148">If applicable, choose **Delete balance adjustments**.</span></span>

5. <span data-ttu-id="22b5d-149">Saisissez ou sélectionnez une **Date de provision de congés**.</span><span class="sxs-lookup"><span data-stu-id="22b5d-149">Enter or select a **Leave accrual date**.</span></span> <span data-ttu-id="22b5d-150">Cette date doit être soit aujourd’hui soit une date à venir.</span><span class="sxs-lookup"><span data-stu-id="22b5d-150">This date must be either today or in the future.</span></span> 

6. <span data-ttu-id="22b5d-151">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="22b5d-151">Select **OK**.</span></span> <span data-ttu-id="22b5d-152">Le processus de régularisation supprimera les provisions et les paramètres que vous définissez.</span><span class="sxs-lookup"><span data-stu-id="22b5d-152">The accrual process will delete accruals with the parameters you set.</span></span> 

## <a name="review-leave-accrual-and-deletion-processes"></a><span data-ttu-id="22b5d-153">Examiner les processus de régularisation et de suppression des congés</span><span class="sxs-lookup"><span data-stu-id="22b5d-153">Review leave accrual and deletion processes</span></span>

<span data-ttu-id="22b5d-154">**Audit des provisions de congés** s’affiche chaque fois que vous exécutez ou supprimez une provision pour un ou tous les employés.</span><span class="sxs-lookup"><span data-stu-id="22b5d-154">**Leave accrual audit** displays each time you run or delete an accrual for one or all employees.</span></span> <span data-ttu-id="22b5d-155">La date et la personne qui ont effectué l’action s’affichent également.</span><span class="sxs-lookup"><span data-stu-id="22b5d-155">The date and person who performed the action also displays.</span></span>

1. <span data-ttu-id="22b5d-156">Dans la page **Plans de congé et d’absence**, sélectionnez l’onglet **Liens**.</span><span class="sxs-lookup"><span data-stu-id="22b5d-156">On the **Leave and absence** page, select the **Links** tab.</span></span>

2. <span data-ttu-id="22b5d-157">Sous **Gérer les congés**, sélectionnez **Supprimer l’audit de provision de congés**.</span><span class="sxs-lookup"><span data-stu-id="22b5d-157">Under **Manage leave**, select **Delete leave accrual audit**.</span></span>

## <a name="see-also"></a><span data-ttu-id="22b5d-158">Voir également :</span><span class="sxs-lookup"><span data-stu-id="22b5d-158">See also</span></span>

[<span data-ttu-id="22b5d-159">Vue d’ensemble des congés et des absences</span><span class="sxs-lookup"><span data-stu-id="22b5d-159">Leave and absence overview</span></span>](hr-leave-and-absence-overview.md)</br>
[<span data-ttu-id="22b5d-160">Créer un plan de congé et d’absence</span><span class="sxs-lookup"><span data-stu-id="22b5d-160">Create a leave and absence plan</span></span>](hr-leave-and-absence-plans.md)
