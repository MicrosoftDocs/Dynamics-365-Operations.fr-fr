---
title: Définir les règles d’admissibilité et les stratégies relatives aux avantages
description: Cet article montre comment créer des règles et des stratégies de droit aux avantages, puis comment affecter les règles aux avantages.
author: andreabichsel
manager: tfehr
ms.date: 02/03/2020
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SysPolicySourceDocumentRuleType, SysPolicyListPage, SysPolicy, HcmBenefitEligibilityPolicy, HcmBenefit, BenefitWorkspace, HcmBenefitSummaryPart
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Version 7.0.0, Human Resources
ms.openlocfilehash: 39a9a1c96ae2a12a32b3c5fbc67571bcf983c898
ms.sourcegitcommit: 6affb3316be757c99e1fe9c7c7b312b93c483408
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/17/2021
ms.locfileid: "5467985"
---
# <a name="define-benefit-eligibility-rules-and-policies"></a><span data-ttu-id="ab6eb-103">Définir les règles d’admissibilité et les stratégies relatives aux avantages</span><span class="sxs-lookup"><span data-stu-id="ab6eb-103">Define benefit eligibility rules and policies</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="ab6eb-104">Cette rubrique montre comment créer des règles et des stratégies de droit aux avantages, puis comment affecter les règles aux avantages.</span><span class="sxs-lookup"><span data-stu-id="ab6eb-104">This topic shows you how you can create benefit eligibility rules and policies and then assign rules to benefits.</span></span>  

## <a name="create-benefit-eligibility-policy-rule-type"></a><span data-ttu-id="ab6eb-105">Créer un type de règles de stratégie de droit aux avantages</span><span class="sxs-lookup"><span data-stu-id="ab6eb-105">Create benefit eligibility policy rule type</span></span>

1. <span data-ttu-id="ab6eb-106">Allez dans **Ressources humaines > Avantages > Admissibilité > Types de règles de stratégie de droit aux avantages**.</span><span class="sxs-lookup"><span data-stu-id="ab6eb-106">Go to **Human resources > Benefits > Eligibility > Benefit eligibility policy rule types**.</span></span>
2. <span data-ttu-id="ab6eb-107">Sélectionnez **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="ab6eb-107">Select **New**.</span></span>
3. <span data-ttu-id="ab6eb-108">Entrez une valeur dans le champ **Nom de la règle**.</span><span class="sxs-lookup"><span data-stu-id="ab6eb-108">In the **Rule name** field, enter a value.</span></span>
4. <span data-ttu-id="ab6eb-109">Dans le champ **Description**, entrez une valeur.</span><span class="sxs-lookup"><span data-stu-id="ab6eb-109">In the **Description** field, enter a value.</span></span>
5. <span data-ttu-id="ab6eb-110">Cliquez sur le bouton de liste déroulante pour ouvrir la recherche dans le champ **Nom de la requête**.</span><span class="sxs-lookup"><span data-stu-id="ab6eb-110">In the **Query name** field, select the drop-down button to open the lookup.</span></span>
6. <span data-ttu-id="ab6eb-111">Dans la liste, sélectionnez le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="ab6eb-111">In the list, select the link in the selected row.</span></span>
7. <span data-ttu-id="ab6eb-112">Sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="ab6eb-112">Select **Save**.</span></span>
8. <span data-ttu-id="ab6eb-113">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="ab6eb-113">Close the page.</span></span>

## <a name="benefit-eligibility-policy"></a><span data-ttu-id="ab6eb-114">Stratégie de droit aux avantages</span><span class="sxs-lookup"><span data-stu-id="ab6eb-114">Benefit eligibility policy</span></span>

1. <span data-ttu-id="ab6eb-115">Allez dans **Ressources humaines > Avantages > Admissibilité > Stratégies de droit aux avantages**.</span><span class="sxs-lookup"><span data-stu-id="ab6eb-115">Go to **Human resources > Benefits > Eligibility > Benefit eligibility policies**.</span></span>
2. <span data-ttu-id="ab6eb-116">Sélectionnez une stratégie de droit existante.</span><span class="sxs-lookup"><span data-stu-id="ab6eb-116">Select an existing benefit policy.</span></span>
3. <span data-ttu-id="ab6eb-117">Dans la liste, sélectionnez le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="ab6eb-117">In the list, select the link in the selected row.</span></span>
4. <span data-ttu-id="ab6eb-118">Activez ou désactivez l’extension des sections **Organisations de stratégie**.</span><span class="sxs-lookup"><span data-stu-id="ab6eb-118">Toggle the expansion of the **Policy organizations** sections.</span></span> <span data-ttu-id="ab6eb-119">Vous pouvez ajouter ou supprimer toutes les organisations à inclure dans la stratégie.</span><span class="sxs-lookup"><span data-stu-id="ab6eb-119">You can add or remove any organizations you want to include in the policy.</span></span>
5. <span data-ttu-id="ab6eb-120">Développez ou réduisez la section **Règles de stratégie**.</span><span class="sxs-lookup"><span data-stu-id="ab6eb-120">Expand or collapse the **Policy rules** section.</span></span>
6. <span data-ttu-id="ab6eb-121">Dans la liste, recherchez la règle de stratégie créée précédemment.</span><span class="sxs-lookup"><span data-stu-id="ab6eb-121">In the list, find the policy rule previously created.</span></span>
7. <span data-ttu-id="ab6eb-122">Sélectionnez **Créer une règle de stratégie**.</span><span class="sxs-lookup"><span data-stu-id="ab6eb-122">Select **Create policy rule**.</span></span>
8. <span data-ttu-id="ab6eb-123">Dans le champ **Date d’effet**, entrez la date à laquelle vous souhaitez que la stratégie prenne effet.</span><span class="sxs-lookup"><span data-stu-id="ab6eb-123">In the **Effective date** field, enter the date in which you want the policy to become effective.</span></span>
    * <span data-ttu-id="ab6eb-124">La définition des dates d’effet et de fin vous permet d’apporter de futures modifications aux règles de stratégie, ainsi vous n’avez pas à rétablir la stratégie lorsque vous souhaitez que ces modifications prennent effet.</span><span class="sxs-lookup"><span data-stu-id="ab6eb-124">Setting effective end dates allows you to make future changes to policy rules so you don't need to come back to the policy when you want those changes to take effect.</span></span>  
9. <span data-ttu-id="ab6eb-125">Si nécessaire, ajoutez une clause where au champ **Ajouter une condition**.</span><span class="sxs-lookup"><span data-stu-id="ab6eb-125">If needed, add a where clause to the **Add condition** field.</span></span>
    * <span data-ttu-id="ab6eb-126">Par exemple si vous souhaitez que la règle s’applique uniquement aux directeurs des ventes, vous pouvez créer la clause where comme ceci : Où la description du poste est égale au responsable des ventes.</span><span class="sxs-lookup"><span data-stu-id="ab6eb-126">For example if you wanted the rule to only apply to Sales Managers you could create the where clause to say: Where position description equals Sales Manager.</span></span> <span data-ttu-id="ab6eb-127">Vous pouvez ajouter plusieurs instructions where dans la règle.</span><span class="sxs-lookup"><span data-stu-id="ab6eb-127">You can add multiple where statements together in the rule.</span></span>  
10. <span data-ttu-id="ab6eb-128">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="ab6eb-128">Select **OK**.</span></span>
11. <span data-ttu-id="ab6eb-129">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="ab6eb-129">Close the page.</span></span>

## <a name="assign-rule-to-benefit"></a><span data-ttu-id="ab6eb-130">Affecter une règle à un avantage</span><span class="sxs-lookup"><span data-stu-id="ab6eb-130">Assign rule to benefit</span></span>

1. <span data-ttu-id="ab6eb-131">Accédez à **Ressources humaines > Avantages > Avantages**.</span><span class="sxs-lookup"><span data-stu-id="ab6eb-131">Go to **Human resources > Benefits > Benefits**.</span></span>
2. <span data-ttu-id="ab6eb-132">Dans la liste, recherchez et sélectionnez l’enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="ab6eb-132">In the list, find and select the desired record.</span></span>
3. <span data-ttu-id="ab6eb-133">Dans la liste, sélectionnez le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="ab6eb-133">In the list, select the link in the selected row.</span></span>
4. <span data-ttu-id="ab6eb-134">Développez ou réduisez la section **Règles d’admissibilité**.</span><span class="sxs-lookup"><span data-stu-id="ab6eb-134">Expand or collapse the **Eligibility rules** section.</span></span>
5. <span data-ttu-id="ab6eb-135">Sélectionnez **Modifier**.</span><span class="sxs-lookup"><span data-stu-id="ab6eb-135">Select **Edit**.</span></span>
6. <span data-ttu-id="ab6eb-136">Sélectionnez la règle dans le champ **Admissibilité**.</span><span class="sxs-lookup"><span data-stu-id="ab6eb-136">In the **Eligibility** field, select the rule.</span></span>
7. <span data-ttu-id="ab6eb-137">Sélectionnez la règle créée précédemment dans le champ **Type de règle**.</span><span class="sxs-lookup"><span data-stu-id="ab6eb-137">In the **Rule type** field, select the rule you previously created.</span></span>
9. <span data-ttu-id="ab6eb-138">Dans la liste, sélectionnez le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="ab6eb-138">In the list, select the link in the selected row.</span></span>
10. <span data-ttu-id="ab6eb-139">Sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="ab6eb-139">Select **Save**.</span></span>
11. <span data-ttu-id="ab6eb-140">Permet de fermer l’écran.</span><span class="sxs-lookup"><span data-stu-id="ab6eb-140">Close the form.</span></span>



[!INCLUDE[footer-include](../includes/footer-banner.md)]