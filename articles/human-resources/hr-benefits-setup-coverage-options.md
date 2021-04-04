---
title: Créer des options de couverture
description: Les options de couverture dans Microsoft Dynamics 365 Human Resources sont les niveaux de couverture pour le choix d’un participant dans un régime de prestations sociales.
author: andreabichsel
manager: tfehr
ms.date: 04/06/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: BenefitWorkspace, HcmBenefitSummaryPart
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 2e1d5fc80d93e41626da8eb5bdf8f389fb0bd531
ms.sourcegitcommit: 6affb3316be757c99e1fe9c7c7b312b93c483408
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/17/2021
ms.locfileid: "5466180"
---
# <a name="create-coverage-options"></a><span data-ttu-id="179b6-103">Créer des options de couverture</span><span class="sxs-lookup"><span data-stu-id="179b6-103">Create coverage options</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="179b6-104">Les options de couverture dans Microsoft Dynamics 365 Human Resources sont les niveaux de couverture pour le choix d’un participant dans un régime de prestations sociales.</span><span class="sxs-lookup"><span data-stu-id="179b6-104">Coverage options in Microsoft Dynamics 365 Human Resources are levels of coverage for a participant's election in a benefit plan or program.</span></span> <span data-ttu-id="179b6-105">Par exemple, les options de couverture pourraient inclure **Employé seulement** pour un plan médical, ou **2x Salaire** pour un régime d’assurance-vie.</span><span class="sxs-lookup"><span data-stu-id="179b6-105">For example, coverage options could include **Employee Only** for a medical plan, or **2x Salary** for a life insurance plan.</span></span> <span data-ttu-id="179b6-106">Une fois défini, vous pouvez réutiliser les options de couverture des avantages.</span><span class="sxs-lookup"><span data-stu-id="179b6-106">Once defined, you can reuse benefit coverage options.</span></span> <span data-ttu-id="179b6-107">Vous pouvez associer une option avec un ou plusieurs plans.</span><span class="sxs-lookup"><span data-stu-id="179b6-107">You can associate an option with one or more plans.</span></span>

<span data-ttu-id="179b6-108">Après avoir défini les options de couverture, associez les options de couverture à un type de régime de prestations sociales.</span><span class="sxs-lookup"><span data-stu-id="179b6-108">After you define coverage options, attach the coverage options to a benefit plan type.</span></span> <span data-ttu-id="179b6-109">Le type de plan est ensuite associé à un régime de prestations sociales.</span><span class="sxs-lookup"><span data-stu-id="179b6-109">The plan type is then associated with a benefit plan or program.</span></span> <span data-ttu-id="179b6-110">Les options de couverture associées à un type de plan sont disponibles pour tous les plans créés avec ce type de plan.</span><span class="sxs-lookup"><span data-stu-id="179b6-110">Coverage options that are associated with a plan type are available to all plans that are created with that plan type.</span></span> 

1. <span data-ttu-id="179b6-111">Dans l’espace de travail **Gestion des avantages**, sous **Installer**, sélectionnez **Options de couverture**.</span><span class="sxs-lookup"><span data-stu-id="179b6-111">In the **Benefits management** workspace, under **Setup**, select **Coverage options**.</span></span>

2. <span data-ttu-id="179b6-112">Sélectionnez **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="179b6-112">Select **New**.</span></span>

3. <span data-ttu-id="179b6-113">Spécifiez les valeurs les champs suivants :</span><span class="sxs-lookup"><span data-stu-id="179b6-113">Specify values for the following fields:</span></span>

   | <span data-ttu-id="179b6-114">Champ</span><span class="sxs-lookup"><span data-stu-id="179b6-114">Field</span></span> | <span data-ttu-id="179b6-115">Description</span><span class="sxs-lookup"><span data-stu-id="179b6-115">Description</span></span> |
   | --- | --- |
   | <span data-ttu-id="179b6-116">**Option de couverture**</span><span class="sxs-lookup"><span data-stu-id="179b6-116">**Coverage option**</span></span> | <span data-ttu-id="179b6-117">Un nom d’option de couverture unique.</span><span class="sxs-lookup"><span data-stu-id="179b6-117">A unique coverage option name.</span></span> |
   | <span data-ttu-id="179b6-118">**Description**</span><span class="sxs-lookup"><span data-stu-id="179b6-118">**Description**</span></span> | <span data-ttu-id="179b6-119">La description de l’option de couverture.</span><span class="sxs-lookup"><span data-stu-id="179b6-119">A description of the coverage option.</span></span> |
   | <span data-ttu-id="179b6-120">**Code couverture**</span><span class="sxs-lookup"><span data-stu-id="179b6-120">**Coverage code**</span></span> | <span data-ttu-id="179b6-121">Les codes de couverture attribuent des montants minimum et maximum pour chaque type de personne couverte éligible.</span><span class="sxs-lookup"><span data-stu-id="179b6-121">Coverage codes assign minimum and maximum amounts for each eligible covered person type.</span></span> <span data-ttu-id="179b6-122">Un code de couverture indique qui est couvert ou le montant de couverture autorisé pour un type de plan.</span><span class="sxs-lookup"><span data-stu-id="179b6-122">A coverage code indicates who is covered or the amount of coverage allowed for a plan type.</span></span> <span data-ttu-id="179b6-123">Vous pouvez exprimer le montant de la couverture sous forme de montant ou de pourcentage.</span><span class="sxs-lookup"><span data-stu-id="179b6-123">You can express the amount of coverage as a dollar amount or a percentage.</span></span> <span data-ttu-id="179b6-124">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="179b6-124">For example:</span></span></br></br><span data-ttu-id="179b6-125">- **Emp + 1** - pour être qualifié, le salarié doit avoir sélectionné une personne à charge (si plus d’une personne est sélectionnée, il ne sera plus qualifié).</span><span class="sxs-lookup"><span data-stu-id="179b6-125">- **Emp+1** – to be qualified, the employee must have one dependent selected (if more than one is selected, they no longer qualify).</span></span></br></br><span data-ttu-id="179b6-126">- **Emp + famille** - pour être qualifié, le salarié doit avoir sélectionné au moins deux personnes à charge.</span><span class="sxs-lookup"><span data-stu-id="179b6-126">- **Emp+family** – to be qualified, the employee must have at least two dependents selected.</span></span> |
   | <span data-ttu-id="179b6-127">**Nombre maximal**</span><span class="sxs-lookup"><span data-stu-id="179b6-127">**Maximum number**</span></span> | <span data-ttu-id="179b6-128">Nombre maximal de personnes à charge</span><span class="sxs-lookup"><span data-stu-id="179b6-128">The maximum number of dependents.</span></span> |
   | <span data-ttu-id="179b6-129">**État**</span><span class="sxs-lookup"><span data-stu-id="179b6-129">**Status**</span></span> | <span data-ttu-id="179b6-130">Statut de l’option de couverture.</span><span class="sxs-lookup"><span data-stu-id="179b6-130">The status of the coverage option.</span></span> <span data-ttu-id="179b6-131">Si l’état de l’option de couverture est défini sur Inactif, l’option de couverture ne peut pas être sélectionnée sur les types de plan.</span><span class="sxs-lookup"><span data-stu-id="179b6-131">If the Coverage option status is set to Inactive, the Coverage option can’t be selected on plan types.</span></span> |
   | <span data-ttu-id="179b6-132">**Pourcentage**</span><span class="sxs-lookup"><span data-stu-id="179b6-132">**Percent**</span></span> | <span data-ttu-id="179b6-133">Montant du pourcentage.</span><span class="sxs-lookup"><span data-stu-id="179b6-133">The percent amount.</span></span> <span data-ttu-id="179b6-134">Ce champ n’est actif que si % x Salaire a été sélectionné dans le champ Code de couverture.</span><span class="sxs-lookup"><span data-stu-id="179b6-134">This field is only active if % x Salary was selected in the Coverage code field.</span></span> |
   | <span data-ttu-id="179b6-135">**Diviseur**</span><span class="sxs-lookup"><span data-stu-id="179b6-135">**Divisor**</span></span> | <span data-ttu-id="179b6-136">Diviseur à utiliser dans le calcul lorsque vous sélectionnez le code de couverture % x salaire.</span><span class="sxs-lookup"><span data-stu-id="179b6-136">The divisor to use in the calculation when you select the coverage code % x salary.</span></span> |
   | <span data-ttu-id="179b6-137">**Pourcentage minimum**</span><span class="sxs-lookup"><span data-stu-id="179b6-137">**Percent minimum**</span></span> | <span data-ttu-id="179b6-138">Le pourcentage minimum lorsque vous sélectionnez le code de couverture en pourcentage.</span><span class="sxs-lookup"><span data-stu-id="179b6-138">The minimum percentage when you select the Percentage coverage code.</span></span> |
   | <span data-ttu-id="179b6-139">**Pourcentage maximal**</span><span class="sxs-lookup"><span data-stu-id="179b6-139">**Percent maximum**</span></span> | <span data-ttu-id="179b6-140">Le pourcentage maximum lorsque vous sélectionnez le code de couverture en pourcentage.</span><span class="sxs-lookup"><span data-stu-id="179b6-140">The maximum percentage when you select the Percentage coverage code.</span></span> |

4. <span data-ttu-id="179b6-141">Sous **Options d’éligibilité des contacts personnels**, associez l’option d’éligibilité des contacts personnels appropriée à chaque option de couverture.</span><span class="sxs-lookup"><span data-stu-id="179b6-141">Under **Personal contact eligibility options**, attach the appropriate personal contacts eligibility option to each coverage option.</span></span>

5. <span data-ttu-id="179b6-142">Sous **Libre-service**, spécifiez des valeurs pour les champs suivants :</span><span class="sxs-lookup"><span data-stu-id="179b6-142">Under **Self service**, specify values for the following fields:</span></span>

   | <span data-ttu-id="179b6-143">Champ</span><span class="sxs-lookup"><span data-stu-id="179b6-143">Field</span></span> | <span data-ttu-id="179b6-144">Description</span><span class="sxs-lookup"><span data-stu-id="179b6-144">Description</span></span> |
   | --- | --- |
   | <span data-ttu-id="179b6-145">**Autoriser le montant de la contribution de l’employé**</span><span class="sxs-lookup"><span data-stu-id="179b6-145">**Allow employee contribution amount**</span></span> | <span data-ttu-id="179b6-146">Indique s’il faut autoriser les employés à modifier le montant de la contribution sur le libre-service des avantages lorsqu’ils sélectionnent des avantages.</span><span class="sxs-lookup"><span data-stu-id="179b6-146">Specifies whether to allow employees to modify the contribution amount on benefits self-service when they select benefits.</span></span> <span data-ttu-id="179b6-147">Si vous cochez cette case, le système calculera les paramètres du régime de prestations en fonction du montant de cotisation que l’employé saisit dans le libre-service des avantages.</span><span class="sxs-lookup"><span data-stu-id="179b6-147">If you select this check box, the system will calculate benefit plan parameters based on the contribution amount the employee enters on benefits self-service.</span></span> |
   | <span data-ttu-id="179b6-148">**Autoriser le montant de la couverture de l’employé**</span><span class="sxs-lookup"><span data-stu-id="179b6-148">**Allow employee coverage amount**</span></span> | <span data-ttu-id="179b6-149">Indique s’il faut autoriser les employés à modifier le montant de la couverture sur le libre-service des avantages lorsqu’ils sélectionnent des avantages.</span><span class="sxs-lookup"><span data-stu-id="179b6-149">Specifies whether to allow employees to modify the coverage amount on benefits self-service when they select benefits.</span></span> <span data-ttu-id="179b6-150">Si vous cochez cette case, le système calculera les paramètres du régime de prestations en fonction du montant de couverture que l’employé saisit dans le Libre-service employé.</span><span class="sxs-lookup"><span data-stu-id="179b6-150">If you select this check box, the system will calculate benefit plan parameters based on the coverage amount the employee enters in Employee self service.</span></span> |

6. <span data-ttu-id="179b6-151">Sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="179b6-151">Select **Save**.</span></span> 


[!INCLUDE[footer-include](../includes/footer-banner.md)]