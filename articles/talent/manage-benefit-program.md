---
title: "Définir et gérer un programme social"
description: "Les ressources humaines proposent un ensemble d'outils pouvant servir à paramétrer et à mettre à jour les avantages, les déductions et les plans de compensation des collaborateurs qu'une organisation offre ou gère pour ses collaborateurs. Cet article fournit des informations sur la manière de paramétrer et de gérer les avantages."
author: kherr75
manager: AnnBe
ms.date: 11/01/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-talent
ms.technology: 
ms.search.form: HcmBenefitEligibilityDetail, HcmBenefitSelection, SysPolicyListPage, SysPolicySourceDocumentRuleType
audience: Application User
ms.reviewer: rschloma
ms.search.scope: Core, Operations, Talent
ms.custom: 15681
ms.assetid: 6aee97ac-29f7-4b3c-8aa1-c65810de3090
ms.search.region: Global
ms.author: kherr
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Talent July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: fc325b519299098a4f8257c013bce0842237f9ea
ms.contentlocale: fr-fr
ms.lasthandoff: 08/08/2018

---

# <a name="define-and-manage-a-benefits-program"></a><span data-ttu-id="0b946-104">Définir et gérer un programme social</span><span class="sxs-lookup"><span data-stu-id="0b946-104">Define and manage a benefits program</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="0b946-105">Les ressources humaines proposent un ensemble d'outils pouvant servir à paramétrer et à mettre à jour les avantages, les déductions et les plans de compensation des collaborateurs qu'une organisation offre ou gère pour ses collaborateurs.</span><span class="sxs-lookup"><span data-stu-id="0b946-105">Human resources provides a set of tools that can be used to set up and maintain benefits, deductions, and workers' compensation plans that an organization offers or processes for its workers.</span></span> <span data-ttu-id="0b946-106">Cette rubrique fournit des informations sur la manière de paramétrer et de gérer les avantages.</span><span class="sxs-lookup"><span data-stu-id="0b946-106">This topic provides information about how to set up and manage benefits.</span></span>

<a name="benefit-setup"></a><span data-ttu-id="0b946-107">Paramétrer les avantages</span><span class="sxs-lookup"><span data-stu-id="0b946-107">Benefit setup</span></span>
-------------

<span data-ttu-id="0b946-108">Avant que les collaborateurs puissent être inscrits à des avantages, vous devez créer les éléments de chaque avantage.</span><span class="sxs-lookup"><span data-stu-id="0b946-108">Before workers can be enrolled in benefits, you must create the elements of each benefit.</span></span> <span data-ttu-id="0b946-109">Ces éléments combinent des plans d'avantages similaires et définissent les paramètres par défaut, tels que les taux de déduction et les détails comptables.</span><span class="sxs-lookup"><span data-stu-id="0b946-109">These elements combine similar benefit plans and define default settings, such as deduction rates and accounting details.</span></span> <span data-ttu-id="0b946-110">Plusieurs de ces paramètres peuvent être ajustés lors de l'inscription ultérieure des collaborateurs à l'avantage.</span><span class="sxs-lookup"><span data-stu-id="0b946-110">Many of these settings can be adjusted when workers are later enrolled in the benefit.</span></span> <span data-ttu-id="0b946-111">Pour chaque plan d'avantages, une organisation peut proposer plusieurs options d'inscription. Un collaborateur peut également renoncer à son inscription au plan.</span><span class="sxs-lookup"><span data-stu-id="0b946-111">For each benefit plan, an organization can offer several enrollment options, or a worker can waive enrollment in the plan.</span></span> 

<span data-ttu-id="0b946-112">[![Avantage du flux de processus](./media/benefit-process-flow1.png)](./media/benefit-process-flow1.png)</span><span class="sxs-lookup"><span data-stu-id="0b946-112">[![Benefit process flow](./media/benefit-process-flow1.png)](./media/benefit-process-flow1.png)</span></span>

## <a name="benefit-elements"></a><span data-ttu-id="0b946-113">Détails des avantages</span><span class="sxs-lookup"><span data-stu-id="0b946-113">Benefit elements</span></span>
<span data-ttu-id="0b946-114">Avant de commencer à créer des avantages et à y inscrire des collaborateurs, vous devez définir les éléments qui constituent un avantage : le type, le régime et les options.</span><span class="sxs-lookup"><span data-stu-id="0b946-114">Before you begin to create to create benefits and enroll workers in them, you must define the elements that make up a benefit: the type, plan, and options.</span></span>

-   <span data-ttu-id="0b946-115">**Type** – Ensemble de régimes pour un avantage spécifique, par exemple une prise en charge médicale ou une place de stationnement.</span><span class="sxs-lookup"><span data-stu-id="0b946-115">**Type** – A collection of plans for a specific benefit, such as medical or parking.</span></span>
-   <span data-ttu-id="0b946-116">**Régime** – Un avantage spécifique contracté auprès d'un fournisseur.</span><span class="sxs-lookup"><span data-stu-id="0b946-116">**Plan** – A specific benefit that is contracted from a provider.</span></span>
-   <span data-ttu-id="0b946-117">**Option** – Le niveau de couverture, comme par exemple « l'employé uniquement » ou « l'employé et le (la) conjoint(e)/partenaire ».</span><span class="sxs-lookup"><span data-stu-id="0b946-117">**Option** – The coverage level, such as employee only, or employee and spouse/partner.</span></span>

<span data-ttu-id="0b946-118">Pour chaque type d'avantage, tel que les soins ophtalmologiques ou dentaires, une organisation peut offrir un ou plusieurs régimes à ses collaborateurs.</span><span class="sxs-lookup"><span data-stu-id="0b946-118">For each type of benefit, such as vision or dental, an organization can offer one or more plans to its workers.</span></span> <span data-ttu-id="0b946-119">Pour chaque régime, l'organisation peut proposer différentes options.</span><span class="sxs-lookup"><span data-stu-id="0b946-119">For each plan, the organization can offer different options.</span></span> <span data-ttu-id="0b946-120">Par exemple, les collaborateurs peuvent acheter une couverture d'assurance vie supplémentaire équivalent à une, deux ou trois fois leur salaire annuel.</span><span class="sxs-lookup"><span data-stu-id="0b946-120">For example, workers can buy additional term life insurance coverage at one, two, or three times their yearly salary.</span></span> <span data-ttu-id="0b946-121">Chaque combinaison d'un régime et d'options forme un avantage auquel les collaborateurs peuvent s'inscrire.</span><span class="sxs-lookup"><span data-stu-id="0b946-121">Each combination of a plan and options becomes a benefit that workers can enroll in.</span></span> 

<span data-ttu-id="0b946-122">[![illustration d'avantage](./media/benefit-pic.png)](./media/benefit-pic.png)</span><span class="sxs-lookup"><span data-stu-id="0b946-122">[![benefit pic](./media/benefit-pic.png)](./media/benefit-pic.png)</span></span>

## <a name="eligibility"></a><span data-ttu-id="0b946-123">Admissibilité</span><span class="sxs-lookup"><span data-stu-id="0b946-123">Eligibility</span></span>
<span data-ttu-id="0b946-124">Plusieurs facteurs déterminent le droit des collaborateurs aux différents types d'avantages qu'un employeur offre.</span><span class="sxs-lookup"><span data-stu-id="0b946-124">Many factors determine worker eligibility for the various types of benefits that an employer offers.</span></span> <span data-ttu-id="0b946-125">Lorsque vous créez un avantage dans Microsoft Talent, vous pouvez définir le type de droit qui s'applique à cet avantage.</span><span class="sxs-lookup"><span data-stu-id="0b946-125">When you create a benefit in Microsoft Talent, you can set the type of eligibility that applies to that benefit.</span></span> 

<span data-ttu-id="0b946-126">Vous pouvez rendre un avantage accessible à tous les collaborateurs.</span><span class="sxs-lookup"><span data-stu-id="0b946-126">You can make a benefit available to all workers.</span></span> <span data-ttu-id="0b946-127">Par exemple, certaines entreprises offrent des cartes de parking à tous les employés comme avantage en nature.</span><span class="sxs-lookup"><span data-stu-id="0b946-127">For example, some companies offer parking passes to all employees as a fringe benefit.</span></span> <span data-ttu-id="0b946-128">Lorsque vous créez cet avantage, vous définissez le droit sur **Tous les collaborateurs sont éligibles**.</span><span class="sxs-lookup"><span data-stu-id="0b946-128">When you create this benefit, you set the eligibility to **All workers are eligible**.</span></span> 

<span data-ttu-id="0b946-129">Pour d'autres avantages, tels que les saisies-arrêts et les prélèvements de taxe, l'éligibilité ne s'applique pas.</span><span class="sxs-lookup"><span data-stu-id="0b946-129">For other benefits, such as garnishments and tax levies, eligibility doesn't apply.</span></span> <span data-ttu-id="0b946-130">Lorsque vous créez ces types d'avantages, vous définissez le droit sur **Ignorer le processus d'éligibilité**.</span><span class="sxs-lookup"><span data-stu-id="0b946-130">Whey you create these types of benefits, you set the eligibility to **Bypass eligibility process**.</span></span> 

<span data-ttu-id="0b946-131">Enfin, le droit à l'avantage peut être basé sur une règle.</span><span class="sxs-lookup"><span data-stu-id="0b946-131">Finally, benefit eligibility can be rule-based.</span></span> <span data-ttu-id="0b946-132">Par exemple, une entreprise offre deux types d'avantage Assurance-vie à ses employés.</span><span class="sxs-lookup"><span data-stu-id="0b946-132">For example, a company offers two types of life insurance benefit to employees.</span></span> <span data-ttu-id="0b946-133">Les cadres ont droit à un régime d'assurance-vie tandis que les autres employés à temps plein ont droit à un autre régime d'assurance-vie.</span><span class="sxs-lookup"><span data-stu-id="0b946-133">Executive employees are eligible for one life insurance plan, whereas all other full-time employees are eligible for the other life insurance plan.</span></span> <span data-ttu-id="0b946-134">Dans Talent, vous pouvez créer une règle de droit à un avantage pour trouver tous les cadres et une autre règle pour trouver tous les autres employés à temps plein, puis appliquer ces règles à l'avantage concerné</span><span class="sxs-lookup"><span data-stu-id="0b946-134">In Talent, you can create a benefit eligibility rule to find all executive employees and another rule to find all other full-time employees, and then apply those rules to the appropriate benefit.</span></span>

## <a name="enrollment"></a><span data-ttu-id="0b946-135">Inscription</span><span class="sxs-lookup"><span data-stu-id="0b946-135">Enrollment</span></span>
<span data-ttu-id="0b946-136">Après avoir créé les avantages que votre organisation propose et déterminé l'éligibilité, vous pouvez inscrire vos collaborateurs aux avantages.</span><span class="sxs-lookup"><span data-stu-id="0b946-136">After you've created the benefits that your organization offers and determined eligibility, you can enroll your workers in benefits.</span></span> <span data-ttu-id="0b946-137">Vous pouvez inscrire un seul collaborateur à des avantages. Vous pouvez également inscrire plusieurs collaborateurs à un ou plusieurs avantages dans le cadre d'un seul et même processus.</span><span class="sxs-lookup"><span data-stu-id="0b946-137">You can enroll a single worker in benefits, or you can enroll many workers in one or more benefits during a single process.</span></span> 

<span data-ttu-id="0b946-138">Parfois, une organisation cesse d'offrir certains avantages.</span><span class="sxs-lookup"><span data-stu-id="0b946-138">Sometimes, an organization stops offering certain benefits.</span></span> <span data-ttu-id="0b946-139">Dans ce cas, vous devez mettre à jour l'avantage et les collaborateurs qui y sont inscrits.</span><span class="sxs-lookup"><span data-stu-id="0b946-139">In this case, you must update the benefit and the workers who are enrolled in.</span></span> <span data-ttu-id="0b946-140">L'expiration de l'avantage collectif vous permet de modifier la date d'échéance d'un avantage et l'inscription des collaborateurs à cet avantage.</span><span class="sxs-lookup"><span data-stu-id="0b946-140">Mass benefit expiration lets you change the expiration date of both a benefit and the worker enrollments for that benefit at the same time.</span></span> <span data-ttu-id="0b946-141">Vous pouvez également sélectionner plusieurs collaborateurs inscrits à un avantage et modifier la date de fin de leur couverture.</span><span class="sxs-lookup"><span data-stu-id="0b946-141">You can also select multiple workers who are enrolled in a benefit and change the ending date of their coverage.</span></span> 

<span data-ttu-id="0b946-142">De même, l'extension de l'avantage collectif vous permet de prolonger la date d'expiration d'un avantage ainsi que l'inscription des collaborateurs à cet avantage si vous décidez d'offrir un avantage plus longtemps que prévu.</span><span class="sxs-lookup"><span data-stu-id="0b946-142">Similarly, mass benefit extension lets you extend the expiration date of both a benefit and the worker enrollments for that benefit if you decide to offer a benefit longer than you originally planned.</span></span>

<a name="additional-resources"></a><span data-ttu-id="0b946-143">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="0b946-143">Additional resources</span></span>
--------

[<span data-ttu-id="0b946-144">Stratégies de droit aux avantages</span><span class="sxs-lookup"><span data-stu-id="0b946-144">Benefit eligibility policies</span></span>](benefit-eligibility-policies.md)




