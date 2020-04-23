---
title: Vue d'ensemble de la gestion des avantages
description: Présentation de la fonction de gestion des avantages dans Dynamics 365 Human Resources. Offrez à vos employés des options d'avantages étendues avec une expérience en ligne facile à utiliser.
author: andreabichsel
manager: AnnBe
ms.date: 04/06/2020
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
ms.openlocfilehash: 91a4425b4f020f90843bb3b0b280b7ee28463670
ms.sourcegitcommit: a9461650d11d6845e1942865ebf7e35f75f61ad3
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/06/2020
ms.locfileid: "3230152"
---
# <a name="benefits-management-overview"></a><span data-ttu-id="f156f-104">Vue d'ensemble de la gestion des avantages</span><span class="sxs-lookup"><span data-stu-id="f156f-104">Benefits management overview</span></span>

<span data-ttu-id="f156f-105">Pour rester compétitif, vous devez offrir un riche ensemble d'avantages pour attirer et retenir vos meilleurs employés.</span><span class="sxs-lookup"><span data-stu-id="f156f-105">To remain competitive, you must offer a rich set of benefits to attract and retain your best employees.</span></span> <span data-ttu-id="f156f-106">En plus des avantages standard comme la couverture médicale et dentaire, vous voudrez peut-être également offrir des services étendus comme l'aide à l'adoption, les programmes de loisirs et les allocations vestimentaires.</span><span class="sxs-lookup"><span data-stu-id="f156f-106">In addition to standard benefits like medical and dental coverage, you might also want to offer expanded services like adoption assistance, recreation programs, and clothing allowances.</span></span> <span data-ttu-id="f156f-107">La fonction de gestion des avantages dans Microsoft Dynamics 365 Human Resources vous offre une solution flexible qui prend en charge une grande variété d'options d'avantages.</span><span class="sxs-lookup"><span data-stu-id="f156f-107">Benefits management in Microsoft Dynamics 365 Human Resources provides you with a flexible solution that supports a wide variety of benefit options.</span></span> <span data-ttu-id="f156f-108">Human resources inclut également une expérience utilisateur facile à utiliser qui met en valeur vos offres.</span><span class="sxs-lookup"><span data-stu-id="f156f-108">Human Resources also includes an easy-to-use employee experience that showcases your offerings.</span></span>

- <span data-ttu-id="f156f-109">Les plans d'avantages améliorés vous permettent de créer et de gérer des plans d'avantages uniques et de prendre en charge des tableaux de taux d'avantages complexes et des niveaux imbriqués.</span><span class="sxs-lookup"><span data-stu-id="f156f-109">Enhanced benefits plans let you create and manage unique benefit plans and support complex benefit rate tables and nested tiers.</span></span> <span data-ttu-id="f156f-110">Vous pouvez facilement créer des programmes d'avantages, des offres groupées et des règles d'inscription automatique pour une expérience utilisateur plus facile.</span><span class="sxs-lookup"><span data-stu-id="f156f-110">You can easily create benefit programs, bundles, and auto-enrollment rules for an easier employee experience.</span></span>

- <span data-ttu-id="f156f-111">Les programmes de crédits flexibles vous permettent de répartir au prorata la retraite et d'autres événements de vie.</span><span class="sxs-lookup"><span data-stu-id="f156f-111">Flex credit programs let you prorate to support retirement and other life events.</span></span>

- <span data-ttu-id="f156f-112">Des règles d'éligibilité étendues garantissent que vous offrez les bons avantages aux bons employés.</span><span class="sxs-lookup"><span data-stu-id="f156f-112">Extensive eligibility rules ensure you make the right benefits available to the right employees.</span></span>

- <span data-ttu-id="f156f-113">L'inscription aux avantages en ligne offre une expérience facile à vos employés.</span><span class="sxs-lookup"><span data-stu-id="f156f-113">Online benefits enrollment provides an easy experience for your employees.</span></span>

- <span data-ttu-id="f156f-114">Le traitement des événements de vie qualifiés prend en charge les événements de vie futurs.</span><span class="sxs-lookup"><span data-stu-id="f156f-114">Qualified life event processing supports future life events.</span></span>

<span data-ttu-id="f156f-115">Si vous souhaitez accéder aux données de démonstration, vous devrez redéployer votre environnement de bac à sable.</span><span class="sxs-lookup"><span data-stu-id="f156f-115">If you would like to access the demo data, you'll need to redeploy your sandbox environment.</span></span>

## <a name="benefits-management-known-issues"></a><span data-ttu-id="f156f-116">Problèmes connus liés à la gestion des avantages</span><span class="sxs-lookup"><span data-stu-id="f156f-116">Benefits management known issues</span></span>

### <a name="flex-credit-programs"></a><span data-ttu-id="f156f-117">Programmes de crédit flexible</span><span class="sxs-lookup"><span data-stu-id="f156f-117">Flex credit programs</span></span>

<span data-ttu-id="f156f-118">La valeur totale du crédit définie pour un programme de crédit flexible ne s'affiche pas dans le formulaire **Plans d'avantages des collaborateurs**.</span><span class="sxs-lookup"><span data-stu-id="f156f-118">The total credit value defined for a flex credit program doesn't display in the **Worker benefit plans** form.</span></span> <span data-ttu-id="f156f-119">De plus, si vous définissez un programme de crédit flexible comme ayant une règle de prorata définie sur **Aucune**, vous obtenez une erreur dans le formulaire **Plans d'avantages pour les collaborateurs** lors de la sélection et de la confirmation des plans.</span><span class="sxs-lookup"><span data-stu-id="f156f-119">Also, if you set a flex credit program to have a proration rule of **None**, you get an error in the **Worker benefit plan** form when selecting and confirming plans.</span></span>

## <a name="enable-benefits-management"></a><span data-ttu-id="f156f-120">Activation de la gestion des avantages</span><span class="sxs-lookup"><span data-stu-id="f156f-120">Enable Benefits management</span></span>

<span data-ttu-id="f156f-121">Cet article décrit comment activer les fonctionnalités dans Human Resources.</span><span class="sxs-lookup"><span data-stu-id="f156f-121">This article describes how to turn on features in Human Resources.</span></span> <span data-ttu-id="f156f-122">Il indique également les fonctionnalités existantes dans Human Resources que la gestion des avantages remplace ou qui sont désactivées une fois que vous avez activé la gestion des avantages.</span><span class="sxs-lookup"><span data-stu-id="f156f-122">It also tells which existing features in Human Resources that Benefits management replaces or are disabled once you turn on Benefits management.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f156f-123">Après avoir activé la gestion des avantages dans un environnement de type **Production**, vous ne pouvez pas le désactiver.</span><span class="sxs-lookup"><span data-stu-id="f156f-123">After you enable Benefits management in a **Production** environment, you can't disable it.</span></span> <span data-ttu-id="f156f-124">Nous vous recommandons d'activer et de tester la gestion des avantages dans un environnement de type **Bac à sable** avant de l'activer dans un environnement de type **Production**.</span><span class="sxs-lookup"><span data-stu-id="f156f-124">We recommend enabling and testing Benefits management in a **Sandbox** environment before enabling it in a **Production** environment.</span></span> <span data-ttu-id="f156f-125">Il existe des différences importantes entre l'ancienne fonctionnalité Avantage et la nouvelle fonctionnalité de gestion des avantages qui nécessitent une configuration supplémentaire et doivent être testées avant d'être mises en production.</span><span class="sxs-lookup"><span data-stu-id="f156f-125">There are significant differences between the legacy Benefit functionality and new Benefits management functionality that require additional setup and should be tested prior to being placed into production.</span></span>

- [<span data-ttu-id="f156f-126">Gérer les fonctionnalités</span><span class="sxs-lookup"><span data-stu-id="f156f-126">Manage features</span></span>](hr-admin-manage-features.md)

## <a name="configure-employee-information"></a><span data-ttu-id="f156f-127">Configurer des informations relatives aux employés</span><span class="sxs-lookup"><span data-stu-id="f156f-127">Configure employee information</span></span>

<span data-ttu-id="f156f-128">Avant de pouvoir inscrire des employés aux avantages sociaux, vous devez fournir les informations requises.</span><span class="sxs-lookup"><span data-stu-id="f156f-128">Before you can enroll employees in benefits, you must provide required information.</span></span> <span data-ttu-id="f156f-129">Vous devez inscrire un employé dans un **Plan de rémunération fixe** à leur date de début, et vous devez sélectionner une **Fréquence de versement des avantages** dans **Détails de l'emploi** sur le formulaire **Collaborateur**.</span><span class="sxs-lookup"><span data-stu-id="f156f-129">You must enroll an employee in a **Fixed compensation plan** on their start date, and you must select a **Benefit pay frequency** in **Employment details** on the **Worker** form.</span></span>

<span data-ttu-id="f156f-130">Lorsque vous créez un plan d'avantages qui utilise des taux basés sur le sexe ou l'âge, vous devez saisir une date de naissance et un sexe pour l'employé afin de calculer le coût des avantages.</span><span class="sxs-lookup"><span data-stu-id="f156f-130">When you create a benefit plan that uses rates that are based on gender or age, you must enter a birth date and gender for the employee to calculate the benefit cost.</span></span>

## <a name="configure-benefits-management"></a><span data-ttu-id="f156f-131">Configurer la gestion des avantages</span><span class="sxs-lookup"><span data-stu-id="f156f-131">Configure Benefits management</span></span>

<span data-ttu-id="f156f-132">Avant de pouvoir créer des plans d'avantages pour vos employés, vous devez configurer les options des plans.</span><span class="sxs-lookup"><span data-stu-id="f156f-132">Before you can create benefit plans for your employees, you need to configure options for the plans.</span></span>

- [<span data-ttu-id="f156f-133">Configuration des paramètres de gestion des avantages</span><span class="sxs-lookup"><span data-stu-id="f156f-133">Set Benefits management parameters</span></span>](hr-benefits-setup-parameters.md)
- [<span data-ttu-id="f156f-134">Configuration des règles et des options d'admissibilité</span><span class="sxs-lookup"><span data-stu-id="f156f-134">Configure eligibility rules and options</span></span>](hr-benefits-setup-eligibility-rules.md)
- [<span data-ttu-id="f156f-135">Configurer les options d'éligibilité des contacts personnels</span><span class="sxs-lookup"><span data-stu-id="f156f-135">Configure personal contact eligibility options</span></span>](hr-benefits-setup-contact-eligibility-options.md)
- [<span data-ttu-id="f156f-136">Créer des options de couverture</span><span class="sxs-lookup"><span data-stu-id="f156f-136">Create coverage options</span></span>](hr-benefits-setup-coverage-options.md)
- [<span data-ttu-id="f156f-137">Configurer les fréquences de paiement</span><span class="sxs-lookup"><span data-stu-id="f156f-137">Set up payment frequencies</span></span>](hr-benefits-setup-payment-frequencies.md)
- [<span data-ttu-id="f156f-138">Configurer les types d'événements de vie</span><span class="sxs-lookup"><span data-stu-id="f156f-138">Configure life event types</span></span>](hr-benefits-setup-life-event-types.md)
- [<span data-ttu-id="f156f-139">Créer des types de plan</span><span class="sxs-lookup"><span data-stu-id="f156f-139">Create plan types</span></span>](hr-benefits-setup-plan-types.md)
- [<span data-ttu-id="f156f-140">Paramétrer des codes motif</span><span class="sxs-lookup"><span data-stu-id="f156f-140">Set up reason codes</span></span>](hr-benefits-setup-reason-codes.md)
- [<span data-ttu-id="f156f-141">Configurer les codes de niveau</span><span class="sxs-lookup"><span data-stu-id="f156f-141">Set up tier codes</span></span>](hr-benefits-setup-tier-codes.md)
- [<span data-ttu-id="f156f-142">Configurer les taux</span><span class="sxs-lookup"><span data-stu-id="f156f-142">Configure rates</span></span>](hr-benefits-setup-rates.md)
- [<span data-ttu-id="f156f-143">Configurer les déductions</span><span class="sxs-lookup"><span data-stu-id="f156f-143">Configure deductions</span></span>](hr-benefits-setup-deductions.md)
- [<span data-ttu-id="f156f-144">Configurer les jours d'attente</span><span class="sxs-lookup"><span data-stu-id="f156f-144">Configure waiting days</span></span>](hr-benefits-setup-waiting-days.md)
- [<span data-ttu-id="f156f-145">Configurer les périodes d'attente</span><span class="sxs-lookup"><span data-stu-id="f156f-145">Configure waiting periods</span></span>](hr-benefits-setup-waiting-periods.md)
- [<span data-ttu-id="f156f-146">Configurer les règles d'arrondi</span><span class="sxs-lookup"><span data-stu-id="f156f-146">Set up rounding rules</span></span>](hr-benefits-setup-rounding-rules.md)
- [<span data-ttu-id="f156f-147">Créer des catégories d'emploi</span><span class="sxs-lookup"><span data-stu-id="f156f-147">Create employment categories</span></span>](hr-benefits-setup-employment-categories.md)
- [<span data-ttu-id="f156f-148">Configuration des types d'emploi</span><span class="sxs-lookup"><span data-stu-id="f156f-148">Set up employment types</span></span>](hr-benefits-setup-employment-types.md)
- [<span data-ttu-id="f156f-149">Configuration du libre-service employé</span><span class="sxs-lookup"><span data-stu-id="f156f-149">Configure employee self service</span></span>](hr-benefits-setup-employee-self-service.md)

## <a name="create-benefit-plans"></a><span data-ttu-id="f156f-150">Création de plans d'avantages</span><span class="sxs-lookup"><span data-stu-id="f156f-150">Create benefit plans</span></span>

<span data-ttu-id="f156f-151">Ces articles montrent comment créer des plans d'avantages, y compris des offres groupées et des programmes de crédits flexibles.</span><span class="sxs-lookup"><span data-stu-id="f156f-151">These articles show how to create benefit plans, including bundles and flex credit programs.</span></span>

- [<span data-ttu-id="f156f-152">Configurer des plans d'avantages</span><span class="sxs-lookup"><span data-stu-id="f156f-152">Set up benefit plans</span></span>](hr-benefits-plans-setup.md)
- [<span data-ttu-id="f156f-153">Configurer des programmes de crédit flexibles</span><span class="sxs-lookup"><span data-stu-id="f156f-153">Set up flex credit programs</span></span>](hr-benefits-plans-flex-credit-programs.md)

## <a name="process-benefit-plans"></a><span data-ttu-id="f156f-154">Traiter les plans d'avantages</span><span class="sxs-lookup"><span data-stu-id="f156f-154">Process benefit plans</span></span>

<span data-ttu-id="f156f-155">Vous devez traiter certaines de vos modifications pour les rendre actives.</span><span class="sxs-lookup"><span data-stu-id="f156f-155">You need to process some of your changes to make them active.</span></span>

- [<span data-ttu-id="f156f-156">Processus d'éligibilité à l'inscription</span><span class="sxs-lookup"><span data-stu-id="f156f-156">Process enrollment eligibility</span></span>](hr-benefits-process-enrollment-eligibility.md)
- [<span data-ttu-id="f156f-157">Traitement des événements de vie</span><span class="sxs-lookup"><span data-stu-id="f156f-157">Process life events</span></span>](hr-benefits-process-life-events.md)
- [<span data-ttu-id="f156f-158">Traitement des changements d'événement de vie</span><span class="sxs-lookup"><span data-stu-id="f156f-158">Process life event changes</span></span>](hr-benefits-process-life-event-changes.md)
- [<span data-ttu-id="f156f-159">Processus d'éligibilité à un événement de vie</span><span class="sxs-lookup"><span data-stu-id="f156f-159">Process life event eligibility</span></span>](hr-benefits-process-life-event-eligibility.md)
- [<span data-ttu-id="f156f-160">Traitement des modifications de taux</span><span class="sxs-lookup"><span data-stu-id="f156f-160">Process rate changes</span></span>](hr-benefits-process-rate-changes.md)

