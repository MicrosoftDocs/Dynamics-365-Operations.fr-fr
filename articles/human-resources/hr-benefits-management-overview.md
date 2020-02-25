---
title: Vue d'ensemble de la gestion des avantages
description: Présentation de la fonction d'aperçu de la gestion des avantages dans Dynamics 365 Human Resources. Offrez à vos employés des options d'avantages étendues avec une expérience en ligne facile à utiliser.
author: andreabichsel
manager: AnnBe
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: BenefitWorkspace
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 63db1b55bae9150dd87d9981136b96d72ffd0c59
ms.sourcegitcommit: 523049c363a999050c58d20695f1c7d151b3fd3e
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "3029461"
---
# <a name="benefits-management-overview"></a><span data-ttu-id="49e6c-104">Vue d'ensemble de la gestion des avantages</span><span class="sxs-lookup"><span data-stu-id="49e6c-104">Benefits management overview</span></span>

[!include [banner](includes/preview-feature.md)]

<span data-ttu-id="49e6c-105">Pour rester compétitif, vous devez offrir un riche ensemble d'avantages pour attirer et retenir vos meilleurs employés.</span><span class="sxs-lookup"><span data-stu-id="49e6c-105">To remain competitive, you must offer a rich set of benefits to attract and retain your best employees.</span></span> <span data-ttu-id="49e6c-106">En plus des avantages standard comme la couverture médicale et dentaire, vous voudrez peut-être également offrir des services étendus comme l'aide à l'adoption, les programmes de loisirs et les allocations vestimentaires.</span><span class="sxs-lookup"><span data-stu-id="49e6c-106">In addition to standard benefits like medical and dental coverage, you might also want to offer expanded services like adoption assistance, recreation programs, and clothing allowances.</span></span> <span data-ttu-id="49e6c-107">La fonction d'aperçu de la gestion des avantages dans Microsoft Dynamics 365 Human Resources vous offre une solution flexible qui prend en charge une grande variété d'options d'avantages.</span><span class="sxs-lookup"><span data-stu-id="49e6c-107">The Benefits management preview feature in Microsoft Dynamics 365 Human Resources provides you with a flexible solution that supports a wide variety of benefit options.</span></span> <span data-ttu-id="49e6c-108">Human resources inclut également une expérience utilisateur facile à utiliser qui met en valeur vos offres.</span><span class="sxs-lookup"><span data-stu-id="49e6c-108">Human Resources also includes an easy-to-use employee experience that showcases your offerings.</span></span>

- <span data-ttu-id="49e6c-109">Les plans d'avantages améliorés vous permettent de créer et de gérer des plans d'avantages uniques et de prendre en charge des tableaux de taux d'avantages complexes et des niveaux imbriqués.</span><span class="sxs-lookup"><span data-stu-id="49e6c-109">Enhanced benefits plans let you create and manage unique benefit plans and support complex benefit rate tables and nested tiers.</span></span> <span data-ttu-id="49e6c-110">Vous pouvez facilement créer des programmes d'avantages, des offres groupées et des règles d'inscription automatique pour une expérience utilisateur plus facile.</span><span class="sxs-lookup"><span data-stu-id="49e6c-110">You can easily create benefit programs, bundles, and auto-enrollment rules for an easier employee experience.</span></span>

- <span data-ttu-id="49e6c-111">Les programmes de crédits flexibles vous permettent de répartir au prorata la retraite et d'autres événements de vie.</span><span class="sxs-lookup"><span data-stu-id="49e6c-111">Flex credit programs let you prorate to support retirement and other life events.</span></span>

- <span data-ttu-id="49e6c-112">Des règles d'éligibilité étendues garantissent que vous offrez les bons avantages aux bons employés.</span><span class="sxs-lookup"><span data-stu-id="49e6c-112">Extensive eligibility rules ensure you make the right benefits available to the right employees.</span></span>

- <span data-ttu-id="49e6c-113">L'inscription aux avantages en ligne offre une expérience facile à vos employés.</span><span class="sxs-lookup"><span data-stu-id="49e6c-113">Online benefits enrollment provides an easy experience for your employees.</span></span>

- <span data-ttu-id="49e6c-114">Le traitement des événements de vie qualifiés s'intègre au libre-service employé et prend également en charge les événements de vie futurs.</span><span class="sxs-lookup"><span data-stu-id="49e6c-114">Qualified life event processing integrates with Employee self service, and also supports future life events.</span></span>

<span data-ttu-id="49e6c-115">Si vous souhaitez accéder aux données de démonstration, vous devrez redéployer votre environnement de bac à sable.</span><span class="sxs-lookup"><span data-stu-id="49e6c-115">If you would like to access the demo data, you'll need to redeploy your sandbox environment.</span></span>

<span data-ttu-id="49e6c-116">Vous pouvez envoyer des commentaires directs ou signaler des problèmes à : D365BenefitsPreview@microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="49e6c-116">You can provide direct feedback or report issues to:  D365BenefitsPreview@microsoft.com.</span></span>

## <a name="benefits-management-known-issues"></a><span data-ttu-id="49e6c-117">Problèmes connus liés à la gestion des avantages</span><span class="sxs-lookup"><span data-stu-id="49e6c-117">Benefits management known issues</span></span>

### <a name="eligibility-processing"></a><span data-ttu-id="49e6c-118">Traitement de l'éligibilité</span><span class="sxs-lookup"><span data-stu-id="49e6c-118">Eligibility processing</span></span>

<span data-ttu-id="49e6c-119">Lors de l'exécution de l'éligibilité aux avantages qui utilisent un salaire de 1 à 5X, un pourcentage du salaire et un montant forfaitaire, vous devez définir la date **Détails de l'avantage** sur la **Date de début de contrat de l'employé** dans l'**Historique des emplois**.</span><span class="sxs-lookup"><span data-stu-id="49e6c-119">When running eligibility for benefits that use a 1-5X Salary, % of Salary, and Flat Amount coverage amount, you must set the **Benefit details** date to the **Employee start date** in **Employment history**.</span></span> <span data-ttu-id="49e6c-120">Vous devez également inclure **Heures travaillées**, **Fréquence de paiement** et **Montant du salaire annuel des avantages**.</span><span class="sxs-lookup"><span data-stu-id="49e6c-120">You must also include **Hours worked**, **Payment frequency**, and **Annual benefits salary amount**.</span></span> <span data-ttu-id="49e6c-121">Si le collaborateur a une rémunération fixe, entrez **Heures travaillées**et **Fréquence de paiement**.</span><span class="sxs-lookup"><span data-stu-id="49e6c-121">If the worker has fixed compensation, enter **Hours worked** and **Payment frequency**.</span></span> <span data-ttu-id="49e6c-122">Le montant du salaire annuel sera calculé.</span><span class="sxs-lookup"><span data-stu-id="49e6c-122">The annual salary amount will calculate.</span></span> <span data-ttu-id="49e6c-123">Si l'employé est salarié, il est inutile d'entrer les **Heures travaillées**.</span><span class="sxs-lookup"><span data-stu-id="49e6c-123">If the employee is salaried, you don't need to enter **Hours worked**.</span></span> <span data-ttu-id="49e6c-124">Nous recommandons que lors de la création de nouveaux employés, vous entriez d'abord la rémunération fixe.</span><span class="sxs-lookup"><span data-stu-id="49e6c-124">We recommend that when creating new workers, enter fixed compensation first.</span></span> <span data-ttu-id="49e6c-125">Pour mettre à jour l'enregistrement des détails des avantages, accédez à **Collaborateur > Historique du collaborateur > Détails de l'emploi**.</span><span class="sxs-lookup"><span data-stu-id="49e6c-125">To update the benefit details record, navigate to **Worker > Worker history > Employment details**.</span></span> <span data-ttu-id="49e6c-126">Ajustez la date selon la date de début du collaborateur.</span><span class="sxs-lookup"><span data-stu-id="49e6c-126">Adjust the date to the worker's start date.</span></span>

### <a name="employee-self-service"></a><span data-ttu-id="49e6c-127">Libre service employé</span><span class="sxs-lookup"><span data-stu-id="49e6c-127">Employee self-service</span></span>

<span data-ttu-id="49e6c-128">Le montant de l'employé n'est pas calculé lors de la mise à jour du montant de la couverture d'assurance-vie.</span><span class="sxs-lookup"><span data-stu-id="49e6c-128">Employee amount doesn't calculate when updating the coverage amount for life insurance.</span></span> <span data-ttu-id="49e6c-129">Par exemple, lorsqu'un employé se voit proposer un régime d'assurance-vie, il peut sélectionner jusqu'à 50 000 $ de couverture au coût de 0,36 $ par 1 000 $ de couverture.</span><span class="sxs-lookup"><span data-stu-id="49e6c-129">For example, when an employee is offered a life insurance plan, they can select up to $50,000 in coverage at a cost of $.36 per $1,000 of coverage.</span></span>  <span data-ttu-id="49e6c-130">Lorsque l'employé met à jour le montant de la couverture, le coût associé pour l'employé reste nul.</span><span class="sxs-lookup"><span data-stu-id="49e6c-130">When the employee updates the coverage amount, the employee’s associated cost remains at zero.</span></span>

<span data-ttu-id="49e6c-131">Pour un plan d'avantages qui ne permet qu'une seule sélection de ce type de plan, l'utilisateur reçoit une erreur s'il tente de renoncer à un plan après l'avoir sélectionné.</span><span class="sxs-lookup"><span data-stu-id="49e6c-131">For a benefit plan that only allows a single selection of that plan type, the user receives an error if they attempt to waive a plan after selecting a plan.</span></span> <span data-ttu-id="49e6c-132">Par exemple, un utilisateur sélectionne un plan médical et le place dans son panier.</span><span class="sxs-lookup"><span data-stu-id="49e6c-132">For example, a user selects a medical plan and places it in their cart.</span></span> <span data-ttu-id="49e6c-133">L'utilisateur sélectionne ensuite **Renoncer** pour un autre plan médical.</span><span class="sxs-lookup"><span data-stu-id="49e6c-133">The user then selects **Waive** for another medical plan.</span></span> <span data-ttu-id="49e6c-134">L'utilisateur recevra une erreur.</span><span class="sxs-lookup"><span data-stu-id="49e6c-134">The user will receive an error.</span></span>

## <a name="enable-benefits-management"></a><span data-ttu-id="49e6c-135">Activation de la gestion des avantages</span><span class="sxs-lookup"><span data-stu-id="49e6c-135">Enable Benefits management</span></span>

<span data-ttu-id="49e6c-136">La gestion des avantages est une fonction d'aperçu et elle n'est disponible que dans les environnements **Bac à sable**.</span><span class="sxs-lookup"><span data-stu-id="49e6c-136">Benefits management is a preview feature, and is only available in **Sandbox** environments.</span></span> <span data-ttu-id="49e6c-137">Ces articles décrivent comment activer les fonctionnalités d'aperçu dans Human Resources.</span><span class="sxs-lookup"><span data-stu-id="49e6c-137">These articles describe how to turn on preview features in Human Resources.</span></span> <span data-ttu-id="49e6c-138">Ils indiquent également les fonctionnalités existantes dans Human Resources que la gestion des avantages remplace ou qui sont désactivées une fois que vous avez activé la gestion des avantages.</span><span class="sxs-lookup"><span data-stu-id="49e6c-138">They also tell which existing features in Human Resources that Benefits management replaces or are disabled once you turn on Benefits management.</span></span>

- [<span data-ttu-id="49e6c-139">Gérer les fonctionnalités</span><span class="sxs-lookup"><span data-stu-id="49e6c-139">Manage features</span></span>](hr-admin-manage-features.md)
- [<span data-ttu-id="49e6c-140">Fonctionnalité en préversion : gestion des avantages</span><span class="sxs-lookup"><span data-stu-id="49e6c-140">Preview feature: Benefits management</span></span>](hr-admin-manage-features.md?preview-feature-benefits-management)

## <a name="configure-benefits-management"></a><span data-ttu-id="49e6c-141">Configuration de la gestion des avantages</span><span class="sxs-lookup"><span data-stu-id="49e6c-141">Configure Benefits management</span></span>

<span data-ttu-id="49e6c-142">Avant de pouvoir créer des plans d'avantages pour vos employés, vous devez configurer les options des plans.</span><span class="sxs-lookup"><span data-stu-id="49e6c-142">Before you can create benefit plans for your employees, you need to configure options for the plans.</span></span>

- [<span data-ttu-id="49e6c-143">Configuration des paramètres de gestion des avantages</span><span class="sxs-lookup"><span data-stu-id="49e6c-143">Set Benefits management parameters</span></span>](hr-benefits-setup-parameters.md)
- [<span data-ttu-id="49e6c-144">Configuration des règles et des options d'admissibilité</span><span class="sxs-lookup"><span data-stu-id="49e6c-144">Configure eligibility rules and options</span></span>](hr-benefits-setup-eligibility-rules.md)
- [<span data-ttu-id="49e6c-145">configuration des options d'éligibilité des contacts personnels</span><span class="sxs-lookup"><span data-stu-id="49e6c-145">Configure personal contact eligibility options</span></span>](hr-benefits-setup-contact-eligibility-options.md)
- [<span data-ttu-id="49e6c-146">Créer des options de couverture</span><span class="sxs-lookup"><span data-stu-id="49e6c-146">Create coverage options</span></span>](hr-benefits-setup-coverage-options.md)
- [<span data-ttu-id="49e6c-147">Paramétrage des fréquences de paiement</span><span class="sxs-lookup"><span data-stu-id="49e6c-147">Set up payment frequencies</span></span>](hr-benefits-setup-payment-frequencies.md)
- [<span data-ttu-id="49e6c-148">Configuration des types d'événements de vie</span><span class="sxs-lookup"><span data-stu-id="49e6c-148">Configure life event types</span></span>](hr-benefits-setup-life-event-types.md)
- [<span data-ttu-id="49e6c-149">Création de types de plan</span><span class="sxs-lookup"><span data-stu-id="49e6c-149">Create plan types</span></span>](hr-benefits-setup-plan-types.md)
- [<span data-ttu-id="49e6c-150">Paramétrer des codes motif</span><span class="sxs-lookup"><span data-stu-id="49e6c-150">Set up reason codes</span></span>](hr-benefits-setup-reason-codes.md)
- [<span data-ttu-id="49e6c-151">Paramétrage des codes de niveau</span><span class="sxs-lookup"><span data-stu-id="49e6c-151">Set up tier codes</span></span>](hr-benefits-setup-tier-codes.md)
- [<span data-ttu-id="49e6c-152">Configuration des taux</span><span class="sxs-lookup"><span data-stu-id="49e6c-152">Configure rates</span></span>](hr-benefits-setup-rates.md)
- [<span data-ttu-id="49e6c-153">Configuration des déductions</span><span class="sxs-lookup"><span data-stu-id="49e6c-153">Configure deductions</span></span>](hr-benefits-setup-deductions.md)
- [<span data-ttu-id="49e6c-154">Configuration des jours d'attente</span><span class="sxs-lookup"><span data-stu-id="49e6c-154">Configure waiting days</span></span>](hr-benefits-setup-waiting-days.md)
- [<span data-ttu-id="49e6c-155">Configuration des périodes d'attente</span><span class="sxs-lookup"><span data-stu-id="49e6c-155">Configure waiting periods</span></span>](hr-benefits-setup-waiting-periods.md)
- [<span data-ttu-id="49e6c-156">Paramétrage des règles d'arrondi</span><span class="sxs-lookup"><span data-stu-id="49e6c-156">Set up rounding rules</span></span>](hr-benefits-setup-rounding-rules.md)
- [<span data-ttu-id="49e6c-157">Création de catégories d'emploi</span><span class="sxs-lookup"><span data-stu-id="49e6c-157">Create employment categories</span></span>](hr-benefits-setup-employment-categories.md)
- [<span data-ttu-id="49e6c-158">Configuration des types d'emploi</span><span class="sxs-lookup"><span data-stu-id="49e6c-158">Set up employment types</span></span>](hr-benefits-setup-employment-types.md)
- [<span data-ttu-id="49e6c-159">Configuration du libre-service employé</span><span class="sxs-lookup"><span data-stu-id="49e6c-159">Configure employee self service</span></span>](hr-benefits-setup-employee-self-service.md)

## <a name="create-benefit-plans"></a><span data-ttu-id="49e6c-160">Création de plans d'avantages</span><span class="sxs-lookup"><span data-stu-id="49e6c-160">Create benefit plans</span></span>

<span data-ttu-id="49e6c-161">Ces articles montrent comment créer des plans d'avantages, y compris des offres groupées et des programmes de crédits flexibles.</span><span class="sxs-lookup"><span data-stu-id="49e6c-161">These articles show how to create benefit plans, including bundles and flex credit programs.</span></span>

- [<span data-ttu-id="49e6c-162">Paramétrage de plans d'avantages</span><span class="sxs-lookup"><span data-stu-id="49e6c-162">Set up benefit plans</span></span>](hr-benefits-plans-setup.md)
- [<span data-ttu-id="49e6c-163">Création de plans d'avantages pour les collaborateurs</span><span class="sxs-lookup"><span data-stu-id="49e6c-163">Create worker benefit plans</span></span>](hr-benefits-plans-worker.md)
- [<span data-ttu-id="49e6c-164">Configuration de programmes de crédits flexibles</span><span class="sxs-lookup"><span data-stu-id="49e6c-164">Set up flex credit programs</span></span>](hr-benefits-plans-flex-credit-programs.md)
- [<span data-ttu-id="49e6c-165">Configuration des événements de vie futurs</span><span class="sxs-lookup"><span data-stu-id="49e6c-165">Configure future life events</span></span>](hr-benefits-plans-future-life-events.md)

## <a name="process-benefit-plans"></a><span data-ttu-id="49e6c-166">Traitement des plans d'avantages</span><span class="sxs-lookup"><span data-stu-id="49e6c-166">Process benefit plans</span></span>

<span data-ttu-id="49e6c-167">Vous devez traiter certaines de vos modifications pour les rendre actives.</span><span class="sxs-lookup"><span data-stu-id="49e6c-167">You need to process some of your changes to make them active.</span></span>

- [<span data-ttu-id="49e6c-168">Processus d'éligibilité à l'inscription</span><span class="sxs-lookup"><span data-stu-id="49e6c-168">Process enrollment eligibility</span></span>](hr-benefits-process-enrollment-eligibility.md)
- [<span data-ttu-id="49e6c-169">Traitement des événements de vie</span><span class="sxs-lookup"><span data-stu-id="49e6c-169">Process life events</span></span>](hr-benefits-process-life-events.md)
- [<span data-ttu-id="49e6c-170">Traitement des changements d'événement de vie</span><span class="sxs-lookup"><span data-stu-id="49e6c-170">Process life event changes</span></span>](hr-benefits-process-life-event-changes.md)
- [<span data-ttu-id="49e6c-171">Processus d'éligibilité à un événement de vie</span><span class="sxs-lookup"><span data-stu-id="49e6c-171">Process life event eligibility</span></span>](hr-benefits-process-life-event-eligibility.md)
- [<span data-ttu-id="49e6c-172">Traitement des modifications de taux</span><span class="sxs-lookup"><span data-stu-id="49e6c-172">Process rate changes</span></span>](hr-benefits-process-rate-changes.md)

