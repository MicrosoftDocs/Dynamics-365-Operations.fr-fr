---
title: configuration des options d’éligibilité des contacts personnels
description: Configurez les options d’éligibilité pour les contacts personnels dans Microsoft Dynamics 365 Human Resources. Les contacts personnels peuvent être des bénéficiaires ou des personnes à charge.
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
ms.openlocfilehash: 2f300ac917ac21db9fffbffcc6eb8589357c0a3e
ms.sourcegitcommit: 6affb3316be757c99e1fe9c7c7b312b93c483408
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/17/2021
ms.locfileid: "5466204"
---
# <a name="configure-personal-contact-eligibility-options"></a><span data-ttu-id="b405c-104">configuration des options d’éligibilité des contacts personnels</span><span class="sxs-lookup"><span data-stu-id="b405c-104">Configure personal contact eligibility options</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="b405c-105">Cet article vous montre comment configurer les types de contacts personnels à utiliser dans les avantages de Microsoft Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="b405c-105">This article shows you how to configure types of personal contacts to use in benefits in Microsoft Dynamics 365 Human Resources.</span></span> <span data-ttu-id="b405c-106">Les contacts personnels peuvent être des bénéficiaires ou des personnes à charge.</span><span class="sxs-lookup"><span data-stu-id="b405c-106">Personal contacts can be beneficiaries or dependents.</span></span> 

1. <span data-ttu-id="b405c-107">Dans l’espace de travail **Gestion des avantages**, sous **Installer**, sélectionnez **Options d’éligibilité des contacts personnels**.</span><span class="sxs-lookup"><span data-stu-id="b405c-107">In the **Benefits management** workspace, under **Setup**, select **Personal contact eligibility options**.</span></span>

2. <span data-ttu-id="b405c-108">Sélectionnez **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="b405c-108">Select **New**.</span></span>

3. <span data-ttu-id="b405c-109">Spécifiez les valeurs les champs suivants :</span><span class="sxs-lookup"><span data-stu-id="b405c-109">Specify values for the following fields:</span></span>

   | <span data-ttu-id="b405c-110">Champ</span><span class="sxs-lookup"><span data-stu-id="b405c-110">Field</span></span> | <span data-ttu-id="b405c-111">Description</span><span class="sxs-lookup"><span data-stu-id="b405c-111">Description</span></span> |
   | --- | --- |
   | <span data-ttu-id="b405c-112">**Option d’éligibilité**</span><span class="sxs-lookup"><span data-stu-id="b405c-112">**Eligibility option**</span></span> | <span data-ttu-id="b405c-113">Nom ou code d’option d’éligibilité unique pour identifier l’option d’éligibilité.</span><span class="sxs-lookup"><span data-stu-id="b405c-113">A unique eligibility option name or code to identify the eligibility option.</span></span> |
   | <span data-ttu-id="b405c-114">**Description**</span><span class="sxs-lookup"><span data-stu-id="b405c-114">**Description**</span></span> | <span data-ttu-id="b405c-115">Brève description de l’option d’éligibilité.</span><span class="sxs-lookup"><span data-stu-id="b405c-115">A brief description of the eligibility option.</span></span> |
   | <span data-ttu-id="b405c-116">**Code d’éligibilité du contact**</span><span class="sxs-lookup"><span data-stu-id="b405c-116">**Contact eligibility code**</span></span> | <span data-ttu-id="b405c-117">Code système qui décrit le mieux l’option d’éligibilité personnelle.</span><span class="sxs-lookup"><span data-stu-id="b405c-117">The system code that best describes the personal eligibility option.</span></span> <span data-ttu-id="b405c-118">Vous pouvez sélectionner l’une des valeurs suivantes :</span><span class="sxs-lookup"><span data-stu-id="b405c-118">You can choose from:</span></span> <ul><li><span data-ttu-id="b405c-119">Relation</span><span class="sxs-lookup"><span data-stu-id="b405c-119">Relationship</span></span></li><li><span data-ttu-id="b405c-120">Étudiant</span><span class="sxs-lookup"><span data-stu-id="b405c-120">Student</span></span></li><li><span data-ttu-id="b405c-121">Couverture des personnes à charge</span><span class="sxs-lookup"><span data-stu-id="b405c-121">Overage dependent</span></span></li><li><span data-ttu-id="b405c-122">Personne à charge présentant un handicap et dépassant l’âge requis</span><span class="sxs-lookup"><span data-stu-id="b405c-122">Over-aged disabled dependent</span></span></li></ul> |
   | <span data-ttu-id="b405c-123">**État**</span><span class="sxs-lookup"><span data-stu-id="b405c-123">**Status**</span></span> | <span data-ttu-id="b405c-124">Statut de l’option d’éligibilité.</span><span class="sxs-lookup"><span data-stu-id="b405c-124">The status of the eligibility option.</span></span> <span data-ttu-id="b405c-125">Si le statut d’une option d’éligibilité est défini sur inactif, vous ne pouvez pas sélectionner cette option d’éligibilité pour les contacts personnels.</span><span class="sxs-lookup"><span data-stu-id="b405c-125">If the status for an eligibility option is set to inactive, then you can’t select that personal contact eligibility option for personal contacts.</span></span> |
   | <span data-ttu-id="b405c-126">**Relation**</span><span class="sxs-lookup"><span data-stu-id="b405c-126">**Relationship**</span></span> | <span data-ttu-id="b405c-127">Spécifie la relation entre le contact personnel et l’employé.</span><span class="sxs-lookup"><span data-stu-id="b405c-127">Specifies the relationship between the personal contact and the employee.</span></span> <span data-ttu-id="b405c-128">Ce champ n’est actif que si le code d’éligibilité du contact est défini sur Relation.</span><span class="sxs-lookup"><span data-stu-id="b405c-128">This field is only active if the contact eligibility code is set to Relationship.</span></span> |
   | <span data-ttu-id="b405c-129">**Âge**</span><span class="sxs-lookup"><span data-stu-id="b405c-129">**Age**</span></span> | <span data-ttu-id="b405c-130">Âge maximum d’un contact personnel éligible pour le plan d’avantages.</span><span class="sxs-lookup"><span data-stu-id="b405c-130">The maximum age of an eligible personal contact for the benefit plan.</span></span> <span data-ttu-id="b405c-131">Ce champ n’est actif que si vous sélectionnez une relation.</span><span class="sxs-lookup"><span data-stu-id="b405c-131">This field is only active if you select a relationship.</span></span> <span data-ttu-id="b405c-132">Cet âge est comparé à l’âge calculé du contact personnel.</span><span class="sxs-lookup"><span data-stu-id="b405c-132">This age is compared with the calculated age of the personal contact.</span></span> <span data-ttu-id="b405c-133">L’âge calculé est le suivant : (date de couverture - date de naissance du contact personnel / 365).</span><span class="sxs-lookup"><span data-stu-id="b405c-133">Calculated age is: (Coverage date – personal contact birth date / 365).</span></span> <span data-ttu-id="b405c-134">Ce nombre est toujours un entier.</span><span class="sxs-lookup"><span data-stu-id="b405c-134">This number is always an integer.</span></span> |

4. <span data-ttu-id="b405c-135">Sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="b405c-135">Select **Save**.</span></span> 


[!INCLUDE[footer-include](../includes/footer-banner.md)]