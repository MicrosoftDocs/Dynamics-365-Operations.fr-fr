---
title: Régimes de rémunération
description: Les gestionnaires de rémunération et avantages peuvent utiliser la gestion des rémunérations pour tenir à jour et traiter les régimes de rémunération fixes et variables des employés de l’organisation.
author: andreabichsel
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: HcmCompensationLevel, HRCCompGrid, HRMCompFixedAction, HRMCompFixedBudget, HRMCompFixedPlanTable, HcmCompensationWorkspace
audience: Application User
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: 3b953d5f-6325-4c9e-8b9b-6ab0458a73f8
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Human Resources
ms.openlocfilehash: b773b12b7eb3a8a59627d011f2469a98c5dde58a
ms.sourcegitcommit: 879ee8a10e6158885795dce4b3db5077540eec41
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/18/2021
ms.locfileid: "6058918"
---
# <a name="compensation-plans"></a><span data-ttu-id="02c34-103">Régimes de rémunération</span><span class="sxs-lookup"><span data-stu-id="02c34-103">Compensation plans</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="02c34-104">Les gestionnaires de rémunération et avantages peuvent utiliser la gestion des rémunérations pour tenir à jour et traiter les régimes de rémunération fixes et variables des employés de l’organisation.</span><span class="sxs-lookup"><span data-stu-id="02c34-104">Compensation and Benefits Managers can use Compensation management to maintain and process fixed and variable compensation plans for the organization's employees.</span></span>

### <a name="introduction"></a><span data-ttu-id="02c34-105">Introduction</span><span class="sxs-lookup"><span data-stu-id="02c34-105">Introduction</span></span>

<span data-ttu-id="02c34-106">La gestion des rémunérations est utilisée pour contrôler la rémunération de base et les primes.</span><span class="sxs-lookup"><span data-stu-id="02c34-106">Compensation management is used to control the delivery of base pay and awards.</span></span> <span data-ttu-id="02c34-107">Le salaire de base fixe et les augmentations pour mérite d’un employé sont contrôlés via les régimes de rémunération fixe.</span><span class="sxs-lookup"><span data-stu-id="02c34-107">An employee's fixed base pay and merit increases are controlled through fixed compensation plans.</span></span> <span data-ttu-id="02c34-108">Le paiement des primes (primes liées aux résultats, options d’achat d’actions et octrois d’actions), ainsi que les primes exceptionnelles, est contrôlé via les régimes de rémunération variable.</span><span class="sxs-lookup"><span data-stu-id="02c34-108">The payment of incentive pay, such as bonus payments, performance awards, stock options, and grants, and also one-time awards, are controlled through variable compensation plans.</span></span> 

<span data-ttu-id="02c34-109">Vous pouvez associer les employés à un ou plusieurs de ces régimes.</span><span class="sxs-lookup"><span data-stu-id="02c34-109">Employees can be enrolled in one or more plans of both types.</span></span> <span data-ttu-id="02c34-110">Pour prétendre à l’enregistrement dans un régime de rémunération, l’employé doit remplir les conditions suivantes :</span><span class="sxs-lookup"><span data-stu-id="02c34-110">An employee must meet the following requirements in order to be eligible for enrollment in a compensation plan:</span></span>
-   <span data-ttu-id="02c34-111">L’employé doit avoir une affectation de poste active.</span><span class="sxs-lookup"><span data-stu-id="02c34-111">The employee must have an active position assignment.</span></span>
-   <span data-ttu-id="02c34-112">L’employé doit satisfaire aux exigences définies dans les règles d’admissibilité à un régime de rémunération.</span><span class="sxs-lookup"><span data-stu-id="02c34-112">The employee must meet the criteria that are defined by eligibility rules for a compensation plan.</span></span>

## <a name="compensation-setup"></a><span data-ttu-id="02c34-113">Paramétrage de la rémunération</span><span class="sxs-lookup"><span data-stu-id="02c34-113">Compensation setup</span></span>
<span data-ttu-id="02c34-114">Le tableau suivant répertorie les composants du processus de rémunération pouvant être intégrés au paramétrage des régimes de rémunération de votre société.</span><span class="sxs-lookup"><span data-stu-id="02c34-114">The following table lists components of the compensation process that can be integral in setting up your company's compensation plans.</span></span>

<table>
<thead>
<tr class="header">
<th><span data-ttu-id="02c34-115">Composant</span><span class="sxs-lookup"><span data-stu-id="02c34-115">Component</span></span></th>
<th><span data-ttu-id="02c34-116">Plus d’informations...</span><span class="sxs-lookup"><span data-stu-id="02c34-116">More information…</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="02c34-117">Actions de rémunération fixe</span><span class="sxs-lookup"><span data-stu-id="02c34-117">Fixed compensation actions</span></span></td>
<td><span data-ttu-id="02c34-118">Les actions de rémunération fixe ont deux objectifs :</span><span class="sxs-lookup"><span data-stu-id="02c34-118">Fixed compensation actions accomplish two purposes:</span></span>
<ul>
<li><span data-ttu-id="02c34-119">Les actions peuvent spécifier le type d’informations qui doivent être enregistrées lorsque la rémunération d’un employé change.</span><span class="sxs-lookup"><span data-stu-id="02c34-119">Actions can specify the kind of information that must be recorded when an employee’s compensation changes.</span></span> <span data-ttu-id="02c34-120">Par exemple, vous pouvez exiger que le motif d’une modification, telle qu’une promotion ou une rétrogradation, soit enregistré.</span><span class="sxs-lookup"><span data-stu-id="02c34-120">For example, you can require that the reason a change, such as a promotion or a demotion be recorded.</span></span></li>
<li><span data-ttu-id="02c34-121">Les actions permettent de garantir qu’un calcul est appliqué lorsque les régimes de rémunération fixe sont traités.</span><span class="sxs-lookup"><span data-stu-id="02c34-121">Actions can ensure that a calculation is applied when fixed compensation plans are processed.</span></span>  <span data-ttu-id="02c34-122">Par exemple, les actions de type Capitaux propres compareront le salaire des employés au point de référence minimal par rapport au niveau de l’employé et garantiront que l’employé est rémunéré au moins au niveau minimal.</span><span class="sxs-lookup"><span data-stu-id="02c34-122">For example, actions of type Equity will compare the employees pay to the minimum reference point for the level on the employee&#39;s and ensure the employee is getting paid at least the minimum.</span></span></li>
</ul></td>
</tr>
<tr class="even">
<td><span data-ttu-id="02c34-123">Niveaux</span><span class="sxs-lookup"><span data-stu-id="02c34-123">Levels</span></span></td>
<td><span data-ttu-id="02c34-124">Les niveaux sont associés aux tâches et aux postes liés à la référence d’une tâche.</span><span class="sxs-lookup"><span data-stu-id="02c34-124">Levels are associated with jobs and any positions that are related to a job reference.</span></span> <span data-ttu-id="02c34-125">Vous pouvez créer des niveaux distincts pour les trois types de régimes de rémunération : Niveau, Structure et Échelon.</span><span class="sxs-lookup"><span data-stu-id="02c34-125">You can create discrete levels for the three types of compensation plans: Grade, Band, and Step.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="02c34-126">Matrice d’utilisation de tranche</span><span class="sxs-lookup"><span data-stu-id="02c34-126">Range utilization matrix</span></span></td>
<td><span data-ttu-id="02c34-127">Une matrice de plage d’utilisation vous permet de faire passer les employés au point de contrôle pour leurs tâches.</span><span class="sxs-lookup"><span data-stu-id="02c34-127">A range utilization matrix helps you transition employees to the control point for their jobs.</span></span> <span data-ttu-id="02c34-128">Vous pouvez également vous servir de la plage d’utilisation pour contrôler l’équité des niveaux de rémunération au sein de la société sans tenir compte des performances individuelles de l’employé ou des performances globales de la société.</span><span class="sxs-lookup"><span data-stu-id="02c34-128">You can also use range utilization to control pay rate equity in the company without regard to an individual employee&#39;s performance or the overall performance of the company.</span></span> <span data-ttu-id="02c34-129">Par exemple, les employés qui ont les salaires les plus bas de leur plage bénéficient d’augmentations supérieures en termes de pourcentage que les employés de la même plage qui sont payés davantage.</span><span class="sxs-lookup"><span data-stu-id="02c34-129">For example, employees who are paid lower in their range get higher percentage increases than employees who are paid higher in the range.</span></span> <span data-ttu-id="02c34-130">De cette manière, il est possible d’atténuer les différences de manière systématique.</span><span class="sxs-lookup"><span data-stu-id="02c34-130">In this manner, you can systematically offset equity differences.</span></span> <span data-ttu-id="02c34-131">La plage d’utilisation est calculée comme suit : (taux de salaire fixe – plage minimale) ÷ (plage maximale – plage minimale).</span><span class="sxs-lookup"><span data-stu-id="02c34-131">The range utilization is calculated as follows: (Fixed Pay Rate - Range Minimum) ÷ (Range Maximum - Range Minimum).</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="02c34-132">Paramétrages de point de référence</span><span class="sxs-lookup"><span data-stu-id="02c34-132">Reference point setups</span></span></td>
<td><span data-ttu-id="02c34-133">Un paramétrage de points de référence inclut un ensemble de points de référence représentant des plages dans une matrice.</span><span class="sxs-lookup"><span data-stu-id="02c34-133">A reference point setup includes a set of reference points that represent ranges in a matrix.</span></span> <span data-ttu-id="02c34-134">Chaque plage peut être associée à un taux de salaire.</span><span class="sxs-lookup"><span data-stu-id="02c34-134">Each range can be associated with a pay rate.</span></span> <span data-ttu-id="02c34-135">Par exemple, les plans de niveau ont souvent des points de référence Minimal, Point moyen et Maximal.</span><span class="sxs-lookup"><span data-stu-id="02c34-135">For example, grade plans will often have reference points of Minimum, Midpoint, and Maximum.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="02c34-136">Matrice de rémunération</span><span class="sxs-lookup"><span data-stu-id="02c34-136">Compensation matrix</span></span></td>
<td><span data-ttu-id="02c34-137">Une matrice de rémunération est l’ensemble de points de référence et de niveaux utilisés pour créer une structure de rémunération.</span><span class="sxs-lookup"><span data-stu-id="02c34-137">A compensation matrix is the set of reference points and levels that you use to create a compensation structure.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="02c34-138">Structure des rémunérations</span><span class="sxs-lookup"><span data-stu-id="02c34-138">Compensation structure</span></span></td>
<td><span data-ttu-id="02c34-139">Une structure de rémunération est une matrice de rémunération dotée de taux de salaire associés aux points de référence pour chaque niveau.</span><span class="sxs-lookup"><span data-stu-id="02c34-139">A compensation structure is a compensation matrix that has pay rates associated with the reference points for each level.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="02c34-140">Règles d’admissibilité</span><span class="sxs-lookup"><span data-stu-id="02c34-140">Eligibility rules</span></span></td>
<td><span data-ttu-id="02c34-141">Des règles d’admissibilité permettent d’identifier les employés rattachés à certains types de tâches, tâches, fonctions de tâche, départements, syndicats ou régions de rémunération qui sont concernés par les régimes de rémunération spécifiques.</span><span class="sxs-lookup"><span data-stu-id="02c34-141">Eligibility rules are used to identify employees in specific jobs, job functions, job types, departments, labor unions, or compensation regions that are covered by specific compensation plans.</span></span> <span data-ttu-id="02c34-142">Vous devez créer des règles d’admissibilité pour les régimes de rémunération variables et fixes afin d’inscrire les employés dans le régime.</span><span class="sxs-lookup"><span data-stu-id="02c34-142">You must create eligibility rules for both variable and fixed compensation plans in order to enroll employees in the plan.</span></span> <span data-ttu-id="02c34-143">Une fois les règles d’admissibilité d’un régime de rémunération paramétrées, vous pouvez définir les niveaux devant s’appliquer aux tâches qu’il englobe.</span><span class="sxs-lookup"><span data-stu-id="02c34-143">After eligibility rules are specified for a compensation plan, you can define the levels that should apply to the jobs that are covered by the plan.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="02c34-144">Fréquences de paiement</span><span class="sxs-lookup"><span data-stu-id="02c34-144">Pay frequencies</span></span></td>
<td><span data-ttu-id="02c34-145">Les fréquences de paiement permettent de définir la période pour laquelle la rémunération est spécifiée.</span><span class="sxs-lookup"><span data-stu-id="02c34-145">Pay frequencies are used to define the time period for which the compensation is specified.</span></span>  <span data-ttu-id="02c34-146">Par exemple, les fréquences de paiement vous aident à comprendre si le montant de rémunération est spécifié comme un salaire annuel ou comme un taux de salaire horaire.</span><span class="sxs-lookup"><span data-stu-id="02c34-146">For example, the pay frequency helps you understand if the compensation amount is specified as an annual salary versus an hourly pay rate.</span></span> <span data-ttu-id="02c34-147">Les fréquences de paiement permettent également de paramétrer des facteurs de conversion pour convertir les montants de rémunération mensuelle, hebdomadaire, bi-hebdomadaire et horaire en paiement annuel.</span><span class="sxs-lookup"><span data-stu-id="02c34-147">Pay frequencies are also used to set up conversion factors to convert compensation amounts from monthly, weekly, biweekly and hourly pay frequencies to an annual pay frequency.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="02c34-148">Régions de rémunération</span><span class="sxs-lookup"><span data-stu-id="02c34-148">Compensation regions</span></span></td>
<td><span data-ttu-id="02c34-149">Les régions de rémunération permettent de spécifier la rémunération de l’employé en fonction de l’emplacement du lieu de travail.</span><span class="sxs-lookup"><span data-stu-id="02c34-149">Compensation regions are used to specify employee compensation based on the location of the workplace.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="02c34-150">Point de contrôle</span><span class="sxs-lookup"><span data-stu-id="02c34-150">Control point</span></span></td>
<td><span data-ttu-id="02c34-151">Le point de contrôle définit ce que vous considérez comme le taux de salaire idéal pour tous les employés appartenant à un niveau de rémunération.</span><span class="sxs-lookup"><span data-stu-id="02c34-151">The control point defines what you consider to be the ideal pay rate for all employees at a compensation level.</span></span> <span data-ttu-id="02c34-152">Pour les structures de régime de niveau, les points de contrôle correspondent généralement au centre de la plage.</span><span class="sxs-lookup"><span data-stu-id="02c34-152">For grade plan structures, control points are typically the midpoint of the ranges.</span></span> <span data-ttu-id="02c34-153">Les structures utilisent rarement les points de contrôle.</span><span class="sxs-lookup"><span data-stu-id="02c34-153">Band structures rarely use control points.</span></span> <span data-ttu-id="02c34-154">Vous pouvez spécifier le point de contrôle pour un régime de rémunération fixe dans l’écran Régimes de rémunération fixe.</span><span class="sxs-lookup"><span data-stu-id="02c34-154">You can specify the control point for a fixed compensation plan in the Fixed compensation plans form.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="02c34-155">Fonctions</span><span class="sxs-lookup"><span data-stu-id="02c34-155">Job functions</span></span></td>
<td><span data-ttu-id="02c34-156">Les fonctions de tâche permettent de classer et de filtrer les régimes de rémunération par rapport à des tâches spécifiques.</span><span class="sxs-lookup"><span data-stu-id="02c34-156">Job functions are used to classify and filter compensation plans to specific jobs.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="02c34-157">Types de missions</span><span class="sxs-lookup"><span data-stu-id="02c34-157">Job types</span></span></td>
<td><span data-ttu-id="02c34-158">Les types de tâche permettent de classer et de filtrer les régimes de rémunération par rapport à des tâches spécifiques.</span><span class="sxs-lookup"><span data-stu-id="02c34-158">Job types are used to classify and filter compensation plans to specific jobs.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="02c34-159">Types de rémunérations variables</span><span class="sxs-lookup"><span data-stu-id="02c34-159">Variable compensation types</span></span></td>
<td><span data-ttu-id="02c34-160">Les types de rémunérations variables, tels que les primes sous forme d’actions ou les primes en espèces, sont paramétrés dans les régimes de rémunération variable.</span><span class="sxs-lookup"><span data-stu-id="02c34-160">Variable compensation types, such as stock awards or cash award bonuses, are set up in variable compensation plans.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="02c34-161">Grilles de rémunération</span><span class="sxs-lookup"><span data-stu-id="02c34-161">Compensation grids</span></span></td>
<td><span data-ttu-id="02c34-162">Les grilles de rémunération contiennent la structure de rémunération.</span><span class="sxs-lookup"><span data-stu-id="02c34-162">Compensation grids contain the compensation structure.</span></span>  <span data-ttu-id="02c34-163">Elles peuvent être utilisées par un ou plusieurs régimes de rémunération.</span><span class="sxs-lookup"><span data-stu-id="02c34-163">Compensation grids can be used by one or more compensation plans.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="02c34-164">Régime basé sur les résultats</span><span class="sxs-lookup"><span data-stu-id="02c34-164">Performance plans</span></span></td>
<td><span data-ttu-id="02c34-165">Les régimes basés sur les résultats permettent d’associer les performances à une matrice de répartition, de manière à utiliser le régime dans une stratégie de rémunération en fonction des résultats.</span><span class="sxs-lookup"><span data-stu-id="02c34-165">Performance plans are used to associate performance with an allocation matrix, so that you can use the plan in a pay-for-performance strategy.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="02c34-166">Classements de résultats</span><span class="sxs-lookup"><span data-stu-id="02c34-166">Performance ratings</span></span></td>
<td><span data-ttu-id="02c34-167">Les classements de résultats sont utilisés dans les régimes basés sur les résultats afin de déterminer le montant d’une prime au mérite ou d’une prime liée aux résultats.</span><span class="sxs-lookup"><span data-stu-id="02c34-167">Performance ratings are used in performance plans to determine the amount of a merit award or performance award.</span></span></td>
</tr>
</tbody>
</table>

## <a name="process-events"></a><span data-ttu-id="02c34-168">Événements de processus</span><span class="sxs-lookup"><span data-stu-id="02c34-168">Process events</span></span>
<span data-ttu-id="02c34-169">Un événement des traitements de données calcule les informations de rémunération d’une période spécifique pour tous les employés inscrits à un ou plusieurs régimes de rémunération fixe ou variable.</span><span class="sxs-lookup"><span data-stu-id="02c34-169">A process event calculates compensation information for a specific period for all employees who are enrolled in one or more fixed or variable compensation plans.</span></span> <span data-ttu-id="02c34-170">Vous pouvez exécuter un événement des traitements de données à plusieurs reprises pour tester ou mettre à jour les résultats de la rémunération.</span><span class="sxs-lookup"><span data-stu-id="02c34-170">You can run a process event repeatedly to test or update calculated compensation results.</span></span>

<a name="compensation-events"></a><span data-ttu-id="02c34-171">Événements de rémunération</span><span class="sxs-lookup"><span data-stu-id="02c34-171">Compensation events</span></span>
-------------------

<span data-ttu-id="02c34-172">Chaque fois qu’un événement de processus est exécuté, un événement de rémunération est créé.</span><span class="sxs-lookup"><span data-stu-id="02c34-172">Each time a process event is run, a compensation event is created.</span></span>  <span data-ttu-id="02c34-173">Les événements de rémunération contiennent les résultats du processus de rémunération pour chaque employé inclus dans cet événement de processus.</span><span class="sxs-lookup"><span data-stu-id="02c34-173">Compensation events contain the results of the compensation process for each employee included in that process event.</span></span>  <span data-ttu-id="02c34-174">Lorsque les calculs sont corrects, vous pouvez charger l’événement de rémunération pour mettre à jour les enregistrements de rémunération pour les employés affectés par l’événement de processus.</span><span class="sxs-lookup"><span data-stu-id="02c34-174">When the calculations are correct, you can load the compensation event to update the compensation records for the employees who are affected by the process event.</span></span>

## <a name="recommendations"></a><span data-ttu-id="02c34-175">Recommandations</span><span class="sxs-lookup"><span data-stu-id="02c34-175">Recommendations</span></span>
<span data-ttu-id="02c34-176">Après avoir exécuté un événement des traitements de données, vous pouvez recommander des ajustements au montant de la prime et à l’augmentation pour mérite d’un employé, sur la base des résultats du calcul de l’événement des traitements de données.</span><span class="sxs-lookup"><span data-stu-id="02c34-176">After you run a process event, you can recommend adjustments to an employee’s merit increase or award amount, based on the calculated guidelines of the process event.</span></span> <span data-ttu-id="02c34-177">Pour être en mesure d’émettre des recommandations pour les employés, vous devez autoriser les recommandations lorsque vous paramétrez les régimes de rémunération ou l’événement des traitements de données.</span><span class="sxs-lookup"><span data-stu-id="02c34-177">To make recommendations for employees, you must enable recommendations when you set up compensation plans or when you set up the process event.</span></span>





[!INCLUDE[footer-include](../includes/footer-banner.md)]