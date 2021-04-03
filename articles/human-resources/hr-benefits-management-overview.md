---
title: Vue d’ensemble de la gestion des avantages
description: Présentation de la fonction de gestion des avantages dans Dynamics 365 Human Resources. Offrez à vos employés des options d’avantages étendues avec une expérience en ligne facile à utiliser.
author: andreabichsel
manager: tfehr
ms.date: 09/17/2020
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
ms.openlocfilehash: ba6623102431eb45bf5d0c96b6583615663d1081
ms.sourcegitcommit: 6affb3316be757c99e1fe9c7c7b312b93c483408
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/17/2021
ms.locfileid: "5464324"
---
# <a name="benefits-management-overview"></a><span data-ttu-id="266dc-104">Vue d’ensemble de la gestion des avantages</span><span class="sxs-lookup"><span data-stu-id="266dc-104">Benefits management overview</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="266dc-105">Pour rester compétitif, vous devez offrir un riche ensemble d’avantages pour attirer et retenir vos meilleurs employés.</span><span class="sxs-lookup"><span data-stu-id="266dc-105">To remain competitive, you must offer a rich set of benefits to attract and retain your best employees.</span></span> <span data-ttu-id="266dc-106">En plus des avantages standard comme la couverture médicale et dentaire, vous voudrez peut-être également offrir des services étendus comme l’aide à l’adoption, les programmes de loisirs et les allocations vestimentaires.</span><span class="sxs-lookup"><span data-stu-id="266dc-106">In addition to standard benefits like medical and dental coverage, you might also want to offer expanded services like adoption assistance, recreation programs, and clothing allowances.</span></span> <span data-ttu-id="266dc-107">La fonction de gestion des avantages dans Microsoft Dynamics 365 Human Resources vous offre une solution flexible qui prend en charge une grande variété d’options d’avantages.</span><span class="sxs-lookup"><span data-stu-id="266dc-107">Benefits management in Microsoft Dynamics 365 Human Resources provides you with a flexible solution that supports a wide variety of benefit options.</span></span> <span data-ttu-id="266dc-108">Human resources inclut également une expérience utilisateur facile à utiliser qui met en valeur vos offres.</span><span class="sxs-lookup"><span data-stu-id="266dc-108">Human Resources also includes an easy-to-use employee experience that showcases your offerings.</span></span>

- <span data-ttu-id="266dc-109">Les plans d’avantages améliorés vous permettent de créer et de gérer des plans d’avantages uniques et de prendre en charge des tableaux de taux d’avantages complexes et des niveaux imbriqués.</span><span class="sxs-lookup"><span data-stu-id="266dc-109">Enhanced benefits plans let you create and manage unique benefit plans and support complex benefit rate tables and nested tiers.</span></span> <span data-ttu-id="266dc-110">Vous pouvez facilement créer des programmes d’avantages, des offres groupées et des règles d’inscription automatique pour une expérience utilisateur plus facile.</span><span class="sxs-lookup"><span data-stu-id="266dc-110">You can easily create benefit programs, bundles, and auto-enrollment rules for an easier employee experience.</span></span>

- <span data-ttu-id="266dc-111">Les programmes de crédits flexibles vous permettent de répartir au prorata la retraite et d’autres événements de vie.</span><span class="sxs-lookup"><span data-stu-id="266dc-111">Flex credit programs let you prorate to support retirement and other life events.</span></span>

- <span data-ttu-id="266dc-112">Des règles d’éligibilité étendues garantissent que vous offrez les bons avantages aux bons employés.</span><span class="sxs-lookup"><span data-stu-id="266dc-112">Extensive eligibility rules ensure you make the right benefits available to the right employees.</span></span>

- <span data-ttu-id="266dc-113">L’inscription aux avantages en ligne offre une expérience facile à vos employés.</span><span class="sxs-lookup"><span data-stu-id="266dc-113">Online benefits enrollment provides an easy experience for your employees.</span></span>

- <span data-ttu-id="266dc-114">Le traitement des événements de vie qualifiés prend en charge les événements de vie futurs.</span><span class="sxs-lookup"><span data-stu-id="266dc-114">Qualified life event processing supports future life events.</span></span>

<span data-ttu-id="266dc-115">Si vous souhaitez accéder aux données de démonstration, vous devrez redéployer votre environnement de bac à sable.</span><span class="sxs-lookup"><span data-stu-id="266dc-115">If you would like to access the demo data, you'll need to redeploy your sandbox environment.</span></span>

## <a name="enable-benefits-management"></a><span data-ttu-id="266dc-116">Activation de la gestion des avantages</span><span class="sxs-lookup"><span data-stu-id="266dc-116">Enable Benefits management</span></span>

<span data-ttu-id="266dc-117">Cette rubrique décrit comment activer les fonctionnalités dans Human Resources.</span><span class="sxs-lookup"><span data-stu-id="266dc-117">This topic describes how to turn on features in Human Resources.</span></span> <span data-ttu-id="266dc-118">Il indique également les fonctionnalités existantes dans Human Resources que la gestion des avantages remplace ou qui sont désactivées une fois que vous avez activé la gestion des avantages.</span><span class="sxs-lookup"><span data-stu-id="266dc-118">It also tells which existing features in Human Resources that Benefits management replaces or are disabled once you turn on Benefits management.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="266dc-119">Après avoir activé la gestion des avantages dans un environnement de type **Production**, vous ne pouvez pas le désactiver.</span><span class="sxs-lookup"><span data-stu-id="266dc-119">After you enable Benefits management in a **Production** environment, you can't disable it.</span></span> <span data-ttu-id="266dc-120">Nous vous recommandons d’activer et de tester la gestion des avantages dans un environnement de type **Bac à sable** avant de l’activer dans un environnement de type **Production**.</span><span class="sxs-lookup"><span data-stu-id="266dc-120">We recommend enabling and testing Benefits management in a **Sandbox** environment before enabling it in a **Production** environment.</span></span> <span data-ttu-id="266dc-121">Il existe des différences importantes entre l’ancienne fonctionnalité Avantage et la nouvelle fonctionnalité de gestion des avantages qui nécessitent une configuration supplémentaire et doivent être testées avant d’être mises en production.</span><span class="sxs-lookup"><span data-stu-id="266dc-121">There are significant differences between the legacy Benefit functionality and new Benefits management functionality that require additional setup and should be tested prior to being placed into production.</span></span>

- [<span data-ttu-id="266dc-122">Gérer les fonctionnalités</span><span class="sxs-lookup"><span data-stu-id="266dc-122">Manage features</span></span>](hr-admin-manage-features.md)

## <a name="configure-employee-information"></a><span data-ttu-id="266dc-123">Configurer des informations relatives aux employés</span><span class="sxs-lookup"><span data-stu-id="266dc-123">Configure employee information</span></span>

<span data-ttu-id="266dc-124">Avant de pouvoir inscrire des employés aux avantages sociaux, vous devez fournir les informations requises.</span><span class="sxs-lookup"><span data-stu-id="266dc-124">Before you can enroll employees in benefits, you must provide required information.</span></span> <span data-ttu-id="266dc-125">Vous devez inscrire un employé dans un **Plan de rémunération fixe** à leur date de début, et vous devez sélectionner une **Fréquence de versement des avantages** dans **Détails de l’emploi** sur le formulaire **Collaborateur**.</span><span class="sxs-lookup"><span data-stu-id="266dc-125">You must enroll an employee in a **Fixed compensation plan** on their start date, and you must select a **Benefit pay frequency** in **Employment details** on the **Worker** form.</span></span>

<span data-ttu-id="266dc-126">Si vous avez un employé qui reçoit une rémunération supplémentaire, comme des commissions, vous pouvez ajouter un montant **Salaire annuel des avantages sociaux** depuis l’enregistrement de l’employé.</span><span class="sxs-lookup"><span data-stu-id="266dc-126">If you have an employee who receives supplemental compensation like commissions, you can add a **Benefits annual salary** amount from the employee record.</span></span> <span data-ttu-id="266dc-127">Human Resources utilise le montant **Salaire annuel des avantages sociaux** lors de la détermination des montants de couverture, au lieu du montant annuel de la rémunération fixe.</span><span class="sxs-lookup"><span data-stu-id="266dc-127">Human Resources will use the **Benefits annual salary** amount when determining coverage amounts, instead of the fixed compensation annual amount.</span></span> <span data-ttu-id="266dc-128">Le **Salaire annuel des avantages sociaux** doit être valide à la date de début de l’employé ou au début de la période de prestation, selon quelle date est la plus récente.</span><span class="sxs-lookup"><span data-stu-id="266dc-128">The **Benefits annual salary** must be valid as of the employee’s start date or the beginning of the benefit period, whichever is latest.</span></span> <span data-ttu-id="266dc-129">Si une rémunération fixe et un montant de salaire annuel des avantages sociaux sont enregistrés pour un employé, le salaire annuel des avantages sociaux sera utilisé pour déterminer les montants de couverture.</span><span class="sxs-lookup"><span data-stu-id="266dc-129">If both a fixed compensation and benefits annual salary amount is recorded for an employee, the benefits annual salary will be used in determining coverage amounts.</span></span>

<span data-ttu-id="266dc-130">Lorsque vous créez un régime de prestations qui utilise des taux basés sur le sexe ou l’âge, vous devez saisir une date de naissance et un sexe pour l’employé afin de calculer le coût des avantages.</span><span class="sxs-lookup"><span data-stu-id="266dc-130">When you create a benefit plan that uses rates that are based on gender or age, you must enter a birth date and gender for the employee to calculate the benefit cost.</span></span>

## <a name="configure-benefits-management"></a><span data-ttu-id="266dc-131">Configurer la gestion des avantages</span><span class="sxs-lookup"><span data-stu-id="266dc-131">Configure Benefits management</span></span>

<span data-ttu-id="266dc-132">Avant de pouvoir créer des plans d’avantages pour vos employés, vous devez configurer les options des plans.</span><span class="sxs-lookup"><span data-stu-id="266dc-132">Before you can create benefit plans for your employees, you need to configure options for the plans.</span></span>

- [<span data-ttu-id="266dc-133">Configuration des paramètres de gestion des avantages</span><span class="sxs-lookup"><span data-stu-id="266dc-133">Set Benefits management parameters</span></span>](hr-benefits-setup-parameters.md)
- [<span data-ttu-id="266dc-134">Configuration des règles et des options d’admissibilité</span><span class="sxs-lookup"><span data-stu-id="266dc-134">Configure eligibility rules and options</span></span>](hr-benefits-setup-eligibility-rules.md)
- [<span data-ttu-id="266dc-135">Configurer les options d’éligibilité des contacts personnels</span><span class="sxs-lookup"><span data-stu-id="266dc-135">Configure personal contact eligibility options</span></span>](hr-benefits-setup-contact-eligibility-options.md)
- [<span data-ttu-id="266dc-136">Créer des options de couverture</span><span class="sxs-lookup"><span data-stu-id="266dc-136">Create coverage options</span></span>](hr-benefits-setup-coverage-options.md)
- [<span data-ttu-id="266dc-137">Configurer les fréquences de paiement</span><span class="sxs-lookup"><span data-stu-id="266dc-137">Set up payment frequencies</span></span>](hr-benefits-setup-payment-frequencies.md)
- [<span data-ttu-id="266dc-138">Configurer les types d’événements de vie</span><span class="sxs-lookup"><span data-stu-id="266dc-138">Configure life event types</span></span>](hr-benefits-setup-life-event-types.md)
- [<span data-ttu-id="266dc-139">Créer des types de plan</span><span class="sxs-lookup"><span data-stu-id="266dc-139">Create plan types</span></span>](hr-benefits-setup-plan-types.md)
- [<span data-ttu-id="266dc-140">Paramétrer des codes motif</span><span class="sxs-lookup"><span data-stu-id="266dc-140">Set up reason codes</span></span>](hr-benefits-setup-reason-codes.md)
- [<span data-ttu-id="266dc-141">Configurer les codes de niveau</span><span class="sxs-lookup"><span data-stu-id="266dc-141">Set up tier codes</span></span>](hr-benefits-setup-tier-codes.md)
- [<span data-ttu-id="266dc-142">Configurer les taux</span><span class="sxs-lookup"><span data-stu-id="266dc-142">Configure rates</span></span>](hr-benefits-setup-rates.md)
- [<span data-ttu-id="266dc-143">Configurer les déductions</span><span class="sxs-lookup"><span data-stu-id="266dc-143">Configure deductions</span></span>](hr-benefits-setup-deductions.md)
- [<span data-ttu-id="266dc-144">Configurer les jours d’attente</span><span class="sxs-lookup"><span data-stu-id="266dc-144">Configure waiting days</span></span>](hr-benefits-setup-waiting-days.md)
- [<span data-ttu-id="266dc-145">Configurer les périodes d’attente</span><span class="sxs-lookup"><span data-stu-id="266dc-145">Configure waiting periods</span></span>](hr-benefits-setup-waiting-periods.md)
- [<span data-ttu-id="266dc-146">Configurer les règles d’arrondi</span><span class="sxs-lookup"><span data-stu-id="266dc-146">Set up rounding rules</span></span>](hr-benefits-setup-rounding-rules.md)
- [<span data-ttu-id="266dc-147">Créer des catégories d’emploi</span><span class="sxs-lookup"><span data-stu-id="266dc-147">Create employment categories</span></span>](hr-benefits-setup-employment-categories.md)
- [<span data-ttu-id="266dc-148">Configuration des types d’emploi</span><span class="sxs-lookup"><span data-stu-id="266dc-148">Set up employment types</span></span>](hr-benefits-setup-employment-types.md)
- [<span data-ttu-id="266dc-149">Configuration du libre-service employé</span><span class="sxs-lookup"><span data-stu-id="266dc-149">Configure employee self service</span></span>](hr-benefits-setup-employee-self-service.md)

## <a name="create-benefit-plans"></a><span data-ttu-id="266dc-150">Création de plans d’avantages</span><span class="sxs-lookup"><span data-stu-id="266dc-150">Create benefit plans</span></span>

<span data-ttu-id="266dc-151">Ces articles montrent comment créer des plans d’avantages, y compris des offres groupées et des programmes de crédits flexibles.</span><span class="sxs-lookup"><span data-stu-id="266dc-151">These articles show how to create benefit plans, including bundles and flex credit programs.</span></span>

- [<span data-ttu-id="266dc-152">Configurer des plans d’avantages</span><span class="sxs-lookup"><span data-stu-id="266dc-152">Set up benefit plans</span></span>](hr-benefits-plans-setup.md)
- [<span data-ttu-id="266dc-153">Configurer des programmes de crédit flexibles</span><span class="sxs-lookup"><span data-stu-id="266dc-153">Set up flex credit programs</span></span>](hr-benefits-plans-flex-credit-programs.md)

## <a name="process-benefit-plans"></a><span data-ttu-id="266dc-154">Traiter les plans d’avantages</span><span class="sxs-lookup"><span data-stu-id="266dc-154">Process benefit plans</span></span>

<span data-ttu-id="266dc-155">Vous devez traiter certaines de vos modifications pour les rendre actives.</span><span class="sxs-lookup"><span data-stu-id="266dc-155">You need to process some of your changes to make them active.</span></span>

- [<span data-ttu-id="266dc-156">Processus d’éligibilité à l’inscription</span><span class="sxs-lookup"><span data-stu-id="266dc-156">Process enrollment eligibility</span></span>](hr-benefits-process-enrollment-eligibility.md)
- [<span data-ttu-id="266dc-157">Traitement des événements de vie</span><span class="sxs-lookup"><span data-stu-id="266dc-157">Process life events</span></span>](hr-benefits-process-life-events.md)
- [<span data-ttu-id="266dc-158">Traitement des changements d’événement de vie</span><span class="sxs-lookup"><span data-stu-id="266dc-158">Process life event changes</span></span>](hr-benefits-process-life-event-changes.md)
- [<span data-ttu-id="266dc-159">Processus d’éligibilité à un événement de vie</span><span class="sxs-lookup"><span data-stu-id="266dc-159">Process life event eligibility</span></span>](hr-benefits-process-life-event-eligibility.md)
- [<span data-ttu-id="266dc-160">Traitement des modifications de taux</span><span class="sxs-lookup"><span data-stu-id="266dc-160">Process rate changes</span></span>](hr-benefits-process-rate-changes.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]