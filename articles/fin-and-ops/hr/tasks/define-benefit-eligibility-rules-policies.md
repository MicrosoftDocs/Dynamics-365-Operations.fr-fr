--- 
title: "Définir les règles d'admissibilité et les stratégies relatives aux avantages"
description: "Cet enregistrement vous indique comment créer des règles et des stratégies de droit aux avantages, puis comment affecter les règles aux avantages."
author: kherr75
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: SysPolicySourceDocumentRuleType, SysPolicyListPage, SysPolicy, HcmBenefitEligibilityPolicy, HcmBenefit
audience: Application User
ms.reviewer: rschloma
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: kherr
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 0312b8cfadd45f8e59225e9daba78b9e216cff51
ms.openlocfilehash: d346c3277e8f19020d6aa96cf6961c4c52ac28fb
ms.contentlocale: fr-fr
ms.lasthandoff: 09/14/2018

---
# <a name="define-benefit-eligibility-rules-and-policies"></a><span data-ttu-id="1e5e8-103">Définir les règles d'admissibilité et les stratégies relatives aux avantages</span><span class="sxs-lookup"><span data-stu-id="1e5e8-103">Define benefit eligibility rules and policies</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="1e5e8-104">Cet enregistrement vous indique comment créer des règles et des stratégies de droit aux avantages, puis comment affecter les règles aux avantages.</span><span class="sxs-lookup"><span data-stu-id="1e5e8-104">This recording will show you how you can create benefit eligibility rules and policies and then assign rules to Benefits.</span></span>  

<span data-ttu-id="1e5e8-105">Les données fictives utilisées pour créer cet enregistrement correspondent à la société USMF.</span><span class="sxs-lookup"><span data-stu-id="1e5e8-105">The demo data company used to create this recording is USMF.</span></span>


## <a name="create-benefit-eligibility-policy-rule-type"></a><span data-ttu-id="1e5e8-106">Créer un type de règles de stratégie de droit aux avantages</span><span class="sxs-lookup"><span data-stu-id="1e5e8-106">Create benefit eligibility policy rule type</span></span>
1. <span data-ttu-id="1e5e8-107">Allez dans Ressources humaines > Avantages > Admissibilité > Types de règles de stratégie de droit aux avantages.</span><span class="sxs-lookup"><span data-stu-id="1e5e8-107">Go to Human resources > Benefits > Eligibility > Benefit eligibility policy rule types.</span></span>
2. <span data-ttu-id="1e5e8-108">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="1e5e8-108">Click New.</span></span>
3. <span data-ttu-id="1e5e8-109">Tapez une valeur dans le champ Nom de la règle.</span><span class="sxs-lookup"><span data-stu-id="1e5e8-109">In the Rule name field, type a value.</span></span>
4. <span data-ttu-id="1e5e8-110">Dans le champ Description, entrez une valeur.</span><span class="sxs-lookup"><span data-stu-id="1e5e8-110">In the Description field, type a value.</span></span>
5. <span data-ttu-id="1e5e8-111">Dans le champ Nom de la requête, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="1e5e8-111">In the Query name field, click the drop-down button to open the lookup.</span></span>
6. <span data-ttu-id="1e5e8-112">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="1e5e8-112">In the list, click the link in the selected row.</span></span>
7. <span data-ttu-id="1e5e8-113">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="1e5e8-113">Click Save.</span></span>
8. <span data-ttu-id="1e5e8-114">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="1e5e8-114">Close the page.</span></span>

## <a name="benefit-eligibility-policy"></a><span data-ttu-id="1e5e8-115">Stratégie de droit aux avantages</span><span class="sxs-lookup"><span data-stu-id="1e5e8-115">Benefit eligibility policy</span></span>
1. <span data-ttu-id="1e5e8-116">Allez dans Ressources humaines > Avantages > Admissibilité > Stratégies de droit aux avantages.</span><span class="sxs-lookup"><span data-stu-id="1e5e8-116">Go to Human resources > Benefits > Eligibility > Benefit eligibility policies.</span></span>
2. <span data-ttu-id="1e5e8-117">Sélectionnez une stratégie de droit existante.</span><span class="sxs-lookup"><span data-stu-id="1e5e8-117">Select an existing benefit policy.</span></span>
3. <span data-ttu-id="1e5e8-118">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="1e5e8-118">In the list, click the link in the selected row.</span></span>
4. <span data-ttu-id="1e5e8-119">Activez ou désactivez l'extension des sections Organisations de stratégie.</span><span class="sxs-lookup"><span data-stu-id="1e5e8-119">Toggle the expansion of the Policy organizations sections.</span></span>  <span data-ttu-id="1e5e8-120">Vous pouvez alors ajouter ou supprimer toutes les organisations à inclure dans la stratégie.</span><span class="sxs-lookup"><span data-stu-id="1e5e8-120">Here you can add or remove any organizations you want to include in the policy.</span></span>
5. <span data-ttu-id="1e5e8-121">Développez ou réduisez la section Règles de stratégie.</span><span class="sxs-lookup"><span data-stu-id="1e5e8-121">Expand or collapse the Policy rules section.</span></span>
6. <span data-ttu-id="1e5e8-122">Dans la liste, recherchez la règle de stratégie créée précédemment.</span><span class="sxs-lookup"><span data-stu-id="1e5e8-122">In the list find the policy rule previously created.</span></span>
7. <span data-ttu-id="1e5e8-123">Cliquez sur Créer une règle de stratégie.</span><span class="sxs-lookup"><span data-stu-id="1e5e8-123">Click Create policy rule.</span></span>
8. <span data-ttu-id="1e5e8-124">Dans le champ Date d'effet, entrez la date à laquelle vous souhaitez que la stratégie prenne effet.</span><span class="sxs-lookup"><span data-stu-id="1e5e8-124">In the Effective date field, enter the date in which you want the policy to become effective.</span></span>
    * <span data-ttu-id="1e5e8-125">La définition des dates d'effet et de fin vous permet d'apporter de futures modifications aux règles de stratégie et de supprimer la nécessité de rétablir la stratégie lorsque vous souhaitez que ces modifications prennent effet.</span><span class="sxs-lookup"><span data-stu-id="1e5e8-125">Setting effective and end dates allows you to make future changes to policy rules and removing the need to come back to the policy when you want those changes to take effect.</span></span>  
9. 
    * <span data-ttu-id="1e5e8-126">Par exemple si vous souhaitez que la règle s'applique uniquement aux directeurs des ventes, vous pouvez créer la clause Where comme ceci : Où la description du poste est égale au responsable des ventes.</span><span class="sxs-lookup"><span data-stu-id="1e5e8-126">For example if you wanted the rule to only apply to Sales Managers you could create the Where clause to say: Where position description equals Sales Manager.</span></span>  <span data-ttu-id="1e5e8-127">Vous pouvez avoir des instructions Where multiples dans la règle.</span><span class="sxs-lookup"><span data-stu-id="1e5e8-127">You can And or Or multiple Where statements together in the rule.</span></span>  
10. <span data-ttu-id="1e5e8-128">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="1e5e8-128">Click OK.</span></span>
11. <span data-ttu-id="1e5e8-129">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="1e5e8-129">Close the page.</span></span>
12. <span data-ttu-id="1e5e8-130">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="1e5e8-130">Close the page.</span></span>

## <a name="assign-rule-to-benefit"></a><span data-ttu-id="1e5e8-131">Affecter une règle à un avantage</span><span class="sxs-lookup"><span data-stu-id="1e5e8-131">Assign rule to benefit</span></span>
1. <span data-ttu-id="1e5e8-132">Accédez à Ressources humaines > Avantages > Avantages.</span><span class="sxs-lookup"><span data-stu-id="1e5e8-132">Go to Human resources > Benefits > Benefits.</span></span>
2. <span data-ttu-id="1e5e8-133">Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="1e5e8-133">In the list, find and select the desired record.</span></span>
3. <span data-ttu-id="1e5e8-134">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="1e5e8-134">In the list, click the link in the selected row.</span></span>
4. <span data-ttu-id="1e5e8-135">Développez ou réduisez la section Règles d'admissibilité.</span><span class="sxs-lookup"><span data-stu-id="1e5e8-135">Expand or collapse the Eligibility rules section.</span></span>
5. <span data-ttu-id="1e5e8-136">Cliquez sur Modifier.</span><span class="sxs-lookup"><span data-stu-id="1e5e8-136">Click Edit.</span></span>
6. <span data-ttu-id="1e5e8-137">Dans le champ Admissibilité, sélectionnez Selon les règles dans la liste.</span><span class="sxs-lookup"><span data-stu-id="1e5e8-137">In the Eligibility field, select Rule based from the list.</span></span>
7. <span data-ttu-id="1e5e8-138">Dans le champ Type de règle, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="1e5e8-138">In the Rule type field, click the drop down button to open the lookup.</span></span>
8. <span data-ttu-id="1e5e8-139">Dans la liste, recherchez et sélectionnez la règle créée précédemment.</span><span class="sxs-lookup"><span data-stu-id="1e5e8-139">In the list find and select the rule you previously created.</span></span>
9. <span data-ttu-id="1e5e8-140">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="1e5e8-140">In the list, click the link in the selected row.</span></span>
10. <span data-ttu-id="1e5e8-141">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="1e5e8-141">Click Save.</span></span>
11. <span data-ttu-id="1e5e8-142">Permet de fermer l'écran.</span><span class="sxs-lookup"><span data-stu-id="1e5e8-142">Close the form.</span></span>


