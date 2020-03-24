---
title: Créer des options de couverture
description: Les options de couverture dans Microsoft Dynamics 365 Human Resources sont les niveaux de couverture selon le choix d'un participant dans un régime ou un programme d'avantages sociaux, comme Employé seulement pour un régime médical ou 2x Salaire pour un régime d'assurance-vie.
author: andreabichsel
manager: AnnBe
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 0af2b6ae0853b4c7f64c4d4f04299c87089d622b
ms.sourcegitcommit: f38302b9430f2ab3efe91d0a7beff946bc610e8f
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/28/2020
ms.locfileid: "3092704"
---
# <a name="create-coverage-options"></a><span data-ttu-id="6f4d1-103">Créer des options de couverture</span><span class="sxs-lookup"><span data-stu-id="6f4d1-103">Create coverage options</span></span>

[!include [banner](includes/preview-feature.md)]

<span data-ttu-id="6f4d1-104">Les options de couverture dans Microsoft Dynamics 365 Human Resources sont les niveaux de couverture selon le choix d'un participant dans un régime ou un programme d'avantages sociaux, comme Employé seulement pour un régime médical ou 2x Salaire pour un régime d'assurance-vie.</span><span class="sxs-lookup"><span data-stu-id="6f4d1-104">Coverage options in Microsoft Dynamics 365 Human Resources are levels of coverage for a participant's election in a benefit plan or program, such as Employee Only for a medical plan, or 2x Salary for a life insurance plan.</span></span> <span data-ttu-id="6f4d1-105">Une fois définies, les options de couverture des prestations sont réutilisables et vous pouvez associer une option à un ou plusieurs plans.</span><span class="sxs-lookup"><span data-stu-id="6f4d1-105">Once defined, benefit coverage options are re-usable and you can associate an option with one or more plans.</span></span>

<span data-ttu-id="6f4d1-106">Une fois les options de couverture définies, associez les options de couverture à un type de régime d'avantages sociaux.</span><span class="sxs-lookup"><span data-stu-id="6f4d1-106">Once the coverage options are defined, attach the coverage options to a benefit plan type.</span></span> <span data-ttu-id="6f4d1-107">Le type de plan est ensuite associé à un plan ou programme d'avantages.</span><span class="sxs-lookup"><span data-stu-id="6f4d1-107">The plan type is then associated with a benefit plan or program.</span></span> <span data-ttu-id="6f4d1-108">Les options de couverture associées à un type de plan seront disponibles pour tous les plans créés avec ce type de plan.</span><span class="sxs-lookup"><span data-stu-id="6f4d1-108">Coverage options that are associated with a plan type will be available to all plans that are created with that plan type.</span></span> 

1. <span data-ttu-id="6f4d1-109">Dans l'espace de travail **Gestion des avantages**, sous **Installer**, sélectionnez **Options de couverture**.</span><span class="sxs-lookup"><span data-stu-id="6f4d1-109">In the **Benefits management** workspace, under **Setup**, select **Coverage options**.</span></span>

2. <span data-ttu-id="6f4d1-110">Sélectionnez **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="6f4d1-110">Select **New**.</span></span>

3. <span data-ttu-id="6f4d1-111">Spécifiez les valeurs les champs suivants :</span><span class="sxs-lookup"><span data-stu-id="6f4d1-111">Specify values for the following fields:</span></span>

   | <span data-ttu-id="6f4d1-112">Champ</span><span class="sxs-lookup"><span data-stu-id="6f4d1-112">Field</span></span> | <span data-ttu-id="6f4d1-113">Description</span><span class="sxs-lookup"><span data-stu-id="6f4d1-113">Description</span></span> |
   | --- | --- |
   | <span data-ttu-id="6f4d1-114">**Option de couverture**</span><span class="sxs-lookup"><span data-stu-id="6f4d1-114">**Coverage option**</span></span> | <span data-ttu-id="6f4d1-115">Un nom d'option de couverture unique.</span><span class="sxs-lookup"><span data-stu-id="6f4d1-115">A unique coverage option name.</span></span> |
   | <span data-ttu-id="6f4d1-116">**Description**</span><span class="sxs-lookup"><span data-stu-id="6f4d1-116">**Description**</span></span> | <span data-ttu-id="6f4d1-117">La description de l'option de couverture.</span><span class="sxs-lookup"><span data-stu-id="6f4d1-117">A description of the coverage option.</span></span> |
   | <span data-ttu-id="6f4d1-118">**Code couverture**</span><span class="sxs-lookup"><span data-stu-id="6f4d1-118">**Coverage code**</span></span> | <span data-ttu-id="6f4d1-119">Les codes de couverture attribuent des montants minimum et maximum pour chaque type de personne couverte éligible.</span><span class="sxs-lookup"><span data-stu-id="6f4d1-119">Coverage codes assign minimum and maximum amounts for each eligible covered person type.</span></span> <span data-ttu-id="6f4d1-120">Un code de couverture indique qui est couvert ou le montant de couverture autorisé pour un type de plan.</span><span class="sxs-lookup"><span data-stu-id="6f4d1-120">A coverage code indicates who is covered or the amount of coverage allowed for a plan type.</span></span> <span data-ttu-id="6f4d1-121">Vous pouvez exprimer le montant de la couverture sous forme de montant ou de pourcentage.</span><span class="sxs-lookup"><span data-stu-id="6f4d1-121">You can express the amount of coverage as a dollar amount or a percentage.</span></span> <span data-ttu-id="6f4d1-122">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="6f4d1-122">For example:</span></span></br></br><span data-ttu-id="6f4d1-123">- **Emp + 1** - pour être qualifié, le salarié doit avoir sélectionné une personne à charge (si plus d'une personne est sélectionnée, il ne sera plus qualifié).</span><span class="sxs-lookup"><span data-stu-id="6f4d1-123">- **Emp+1** – to be qualified, the employee must have one dependent selected (if more than one is selected, they no longer qualify).</span></span></br></br><span data-ttu-id="6f4d1-124">- **Emp + famille** - pour être qualifié, le salarié doit avoir sélectionné au moins deux personnes à charge.</span><span class="sxs-lookup"><span data-stu-id="6f4d1-124">- **Emp+family** – to be qualified, the employee must have at least two dependents selected.</span></span> |
   | <span data-ttu-id="6f4d1-125">**Nombre maximal**</span><span class="sxs-lookup"><span data-stu-id="6f4d1-125">**Maximum number**</span></span> | <span data-ttu-id="6f4d1-126">Nombre maximal de personnes à charge</span><span class="sxs-lookup"><span data-stu-id="6f4d1-126">The maximum number of dependents.</span></span> |
   | <span data-ttu-id="6f4d1-127">**État**</span><span class="sxs-lookup"><span data-stu-id="6f4d1-127">**Status**</span></span> | <span data-ttu-id="6f4d1-128">Statut de l'option de couverture.</span><span class="sxs-lookup"><span data-stu-id="6f4d1-128">The status of the coverage option.</span></span> <span data-ttu-id="6f4d1-129">Si l'état de l'option de couverture est défini sur Inactif, l'option de couverture ne peut pas être sélectionnée sur les types de plan.</span><span class="sxs-lookup"><span data-stu-id="6f4d1-129">If the Coverage option status is set to Inactive, the Coverage option can’t be selected on plan types.</span></span> |
   | <span data-ttu-id="6f4d1-130">**Pourcentage**</span><span class="sxs-lookup"><span data-stu-id="6f4d1-130">**Percent**</span></span> | <span data-ttu-id="6f4d1-131">Montant du pourcentage.</span><span class="sxs-lookup"><span data-stu-id="6f4d1-131">The percent amount.</span></span> <span data-ttu-id="6f4d1-132">Ce champ n'est actif que si % x Salaire a été sélectionné dans le champ Code de couverture.</span><span class="sxs-lookup"><span data-stu-id="6f4d1-132">This field is only active if % x Salary was selected in the Coverage code field.</span></span> |
   | <span data-ttu-id="6f4d1-133">**Diviseur**</span><span class="sxs-lookup"><span data-stu-id="6f4d1-133">**Divisor**</span></span> | <span data-ttu-id="6f4d1-134">Diviseur à utiliser dans le calcul lorsque vous sélectionnez le code de couverture % x salaire.</span><span class="sxs-lookup"><span data-stu-id="6f4d1-134">The divisor to use in the calculation when you select the coverage code % x salary.</span></span> |
   | <span data-ttu-id="6f4d1-135">**Pourcentage minimum**</span><span class="sxs-lookup"><span data-stu-id="6f4d1-135">**Percent minimum**</span></span> | <span data-ttu-id="6f4d1-136">Le pourcentage minimum lorsque vous sélectionnez le code de couverture en pourcentage.</span><span class="sxs-lookup"><span data-stu-id="6f4d1-136">The minimum percentage when you select the Percentage coverage code.</span></span> |
   | <span data-ttu-id="6f4d1-137">**Pourcentage maximal**</span><span class="sxs-lookup"><span data-stu-id="6f4d1-137">**Percent maximum**</span></span> | <span data-ttu-id="6f4d1-138">Le pourcentage maximum lorsque vous sélectionnez le code de couverture en pourcentage.</span><span class="sxs-lookup"><span data-stu-id="6f4d1-138">The maximum percentage when you select the Percentage coverage code.</span></span> |

4. <span data-ttu-id="6f4d1-139">Sous **Options d'éligibilité des contacts personnels**, associez l'option d'éligibilité des contacts personnels appropriée à chaque option de couverture.</span><span class="sxs-lookup"><span data-stu-id="6f4d1-139">Under **Personal contact eligibility options**, attach the appropriate personal contacts eligibility option to each coverage option.</span></span>

5. <span data-ttu-id="6f4d1-140">Sous **Libre-service**, spécifiez des valeurs pour les champs suivants :</span><span class="sxs-lookup"><span data-stu-id="6f4d1-140">Under **Self service**, specify values for the following fields:</span></span>

   | <span data-ttu-id="6f4d1-141">Champ</span><span class="sxs-lookup"><span data-stu-id="6f4d1-141">Field</span></span> | <span data-ttu-id="6f4d1-142">Description</span><span class="sxs-lookup"><span data-stu-id="6f4d1-142">Description</span></span> |
   | --- | --- |
   | <span data-ttu-id="6f4d1-143">**Autoriser le montant de la contribution de l'employé**</span><span class="sxs-lookup"><span data-stu-id="6f4d1-143">**Allow employee contribution amount**</span></span> | <span data-ttu-id="6f4d1-144">Indique s'il faut autoriser les employés à modifier le montant de la contribution sur le libre-service des avantages lorsqu'ils sélectionnent des avantages.</span><span class="sxs-lookup"><span data-stu-id="6f4d1-144">Specifies whether to allow employees to modify the contribution amount on benefits self-service when they select benefits.</span></span> <span data-ttu-id="6f4d1-145">Si vous cochez cette case, le système calculera les paramètres du régime d'avantages en fonction du montant de cotisation que l'employé saisit dans le libre-service des avantages.</span><span class="sxs-lookup"><span data-stu-id="6f4d1-145">If you select this check box, the system will calculate benefit plan parameters based on the contribution amount the employee enters on benefits self-service.</span></span> |
   | <span data-ttu-id="6f4d1-146">**Autoriser le montant de la couverture de l'employé**</span><span class="sxs-lookup"><span data-stu-id="6f4d1-146">**Allow employee coverage amount**</span></span> | <span data-ttu-id="6f4d1-147">Indique s'il faut autoriser les employés à modifier le montant de la couverture sur le libre-service des avantages lorsqu'ils sélectionnent des avantages.</span><span class="sxs-lookup"><span data-stu-id="6f4d1-147">Specifies whether to allow employees to modify the coverage amount on benefits self-service when they select benefits.</span></span> <span data-ttu-id="6f4d1-148">Si vous cochez cette case, le système calculera les paramètres du régime d'avantages en fonction du montant de couverture que l'employé saisit dans le Libre-service employé.</span><span class="sxs-lookup"><span data-stu-id="6f4d1-148">If you select this check box, the system will calculate benefit plan parameters based on the coverage amount the employee enters in Employee self service.</span></span> |

6. <span data-ttu-id="6f4d1-149">Sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="6f4d1-149">Select **Save**.</span></span> 
