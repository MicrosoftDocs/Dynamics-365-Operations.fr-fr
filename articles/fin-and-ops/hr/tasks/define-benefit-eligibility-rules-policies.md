--- 
title: "Définir les règles d'admissibilité et les stratégies relatives aux avantages"
description: "Cet enregistrement vous indique comment créer des règles et des stratégies de droit aux avantages, puis comment affecter les règles aux avantages."
author: kherr75
manager: AnnBe
ms.date: 06/10/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: rschloma
ms.search.scope: Operations
ms.search.region: Global
ms.author: kherr
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f827b4787506cfdec8b9a91c4a68f3293190158a
ms.openlocfilehash: c570574d15bbc55b4d0d79b8e62d74adcc15b387
ms.contentlocale: fr-fr
ms.lasthandoff: 09/29/2017

---
# <a name="define-benefit-eligibility-rules-and-policies"></a><span data-ttu-id="c14d0-103">Définir les règles d'admissibilité et les stratégies relatives aux avantages</span><span class="sxs-lookup"><span data-stu-id="c14d0-103">Define benefit eligibility rules and policies</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="c14d0-104">Cet enregistrement vous indique comment créer des règles et des stratégies de droit aux avantages, puis comment affecter les règles aux avantages.</span><span class="sxs-lookup"><span data-stu-id="c14d0-104">This recording will show you how you can create benefit eligibility rules and policies and then assign rules to Benefits.</span></span>  

<span data-ttu-id="c14d0-105">Les données fictives utilisées pour créer cet enregistrement correspondent à la société USMF.</span><span class="sxs-lookup"><span data-stu-id="c14d0-105">The demo data company used to create this recording is USMF.</span></span>


## <a name="create-benefit-eligibility-policy-rule-type"></a><span data-ttu-id="c14d0-106">Créer un type de règles de stratégie de droit aux avantages</span><span class="sxs-lookup"><span data-stu-id="c14d0-106">Create benefit eligibility policy rule type</span></span>
1. <span data-ttu-id="c14d0-107">Allez dans Ressources humaines > Avantages > Admissibilité > Types de règles de stratégie de droit aux avantages.</span><span class="sxs-lookup"><span data-stu-id="c14d0-107">Go to Human resources > Benefits > Eligibility > Benefit eligibility policy rule types.</span></span>
2. <span data-ttu-id="c14d0-108">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="c14d0-108">Click New.</span></span>
3. <span data-ttu-id="c14d0-109">Tapez une valeur dans le champ Nom de la règle.</span><span class="sxs-lookup"><span data-stu-id="c14d0-109">In the Rule name field, type a value.</span></span>
4. <span data-ttu-id="c14d0-110">Dans le champ Description, entrez une valeur.</span><span class="sxs-lookup"><span data-stu-id="c14d0-110">In the Description field, type a value.</span></span>
5. <span data-ttu-id="c14d0-111">Dans le champ Nom de la requête, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="c14d0-111">In the Query name field, click the drop-down button to open the lookup.</span></span>
6. <span data-ttu-id="c14d0-112">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="c14d0-112">In the list, click the link in the selected row.</span></span>
7. <span data-ttu-id="c14d0-113">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="c14d0-113">Click Save.</span></span>
8. <span data-ttu-id="c14d0-114">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="c14d0-114">Close the page.</span></span>

## <a name="benefit-eligibility-policy"></a><span data-ttu-id="c14d0-115">Stratégie de droit aux avantages</span><span class="sxs-lookup"><span data-stu-id="c14d0-115">Benefit eligibility policy</span></span>
1. <span data-ttu-id="c14d0-116">Allez dans Ressources humaines > Avantages > Admissibilité > Stratégies de droit aux avantages.</span><span class="sxs-lookup"><span data-stu-id="c14d0-116">Go to Human resources > Benefits > Eligibility > Benefit eligibility policies.</span></span>
2. <span data-ttu-id="c14d0-117">Sélectionnez une stratégie de droit existante.</span><span class="sxs-lookup"><span data-stu-id="c14d0-117">Select an existing benefit policy.</span></span>
3. <span data-ttu-id="c14d0-118">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="c14d0-118">In the list, click the link in the selected row.</span></span>
4. <span data-ttu-id="c14d0-119">Activez ou désactivez l'extension des sections Organisations de stratégie.</span><span class="sxs-lookup"><span data-stu-id="c14d0-119">Toggle the expansion of the Policy organizations sections.</span></span>  <span data-ttu-id="c14d0-120">Vous pouvez alors ajouter ou supprimer toutes les organisations à inclure dans la stratégie.</span><span class="sxs-lookup"><span data-stu-id="c14d0-120">Here you can add or remove any organizations you want to include in the policy.</span></span>
5. <span data-ttu-id="c14d0-121">Développez ou réduisez la section Règles de stratégie.</span><span class="sxs-lookup"><span data-stu-id="c14d0-121">Expand or collapse the Policy rules section.</span></span>
6. <span data-ttu-id="c14d0-122">Dans la liste, recherchez la règle de stratégie créée précédemment.</span><span class="sxs-lookup"><span data-stu-id="c14d0-122">In the list find the policy rule previously created.</span></span>
7. <span data-ttu-id="c14d0-123">Cliquez sur Créer une règle de stratégie.</span><span class="sxs-lookup"><span data-stu-id="c14d0-123">Click Create policy rule.</span></span>
8. <span data-ttu-id="c14d0-124">Dans le champ Date d'effet, entrez la date à laquelle vous souhaitez que la stratégie prenne effet.</span><span class="sxs-lookup"><span data-stu-id="c14d0-124">In the Effective date field, enter the date in which you want the policy to become effective.</span></span>
    * <span data-ttu-id="c14d0-125">La définition des dates d'effet et de fin vous permet d'apporter de futures modifications aux règles de stratégie et de supprimer la nécessité de rétablir la stratégie lorsque vous souhaitez que ces modifications prennent effet.</span><span class="sxs-lookup"><span data-stu-id="c14d0-125">Setting effective and end dates allows you to make future changes to policy rules and removing the need to come back to the policy when you want those changes to take effect.</span></span>  
9. 
    * <span data-ttu-id="c14d0-126">Par exemple si vous souhaitez que la règle s'applique uniquement aux directeurs des ventes, vous pouvez créer la clause Where comme ceci : Où la description du poste est égale au responsable des ventes.</span><span class="sxs-lookup"><span data-stu-id="c14d0-126">For example if you wanted the rule to only apply to Sales Managers you could create the Where clause to say: Where position description equals Sales Manager.</span></span>  <span data-ttu-id="c14d0-127">Vous pouvez avoir des instructions Where multiples dans la règle.</span><span class="sxs-lookup"><span data-stu-id="c14d0-127">You can And or Or multiple Where statements together in the rule.</span></span>  
10. <span data-ttu-id="c14d0-128">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="c14d0-128">Click OK.</span></span>
11. <span data-ttu-id="c14d0-129">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="c14d0-129">Close the page.</span></span>
12. <span data-ttu-id="c14d0-130">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="c14d0-130">Close the page.</span></span>

## <a name="assign-rule-to-benefit"></a><span data-ttu-id="c14d0-131">Affecter une règle à un avantage</span><span class="sxs-lookup"><span data-stu-id="c14d0-131">Assign rule to benefit</span></span>
1. <span data-ttu-id="c14d0-132">Accédez à Ressources humaines > Avantages > Avantages.</span><span class="sxs-lookup"><span data-stu-id="c14d0-132">Go to Human resources > Benefits > Benefits.</span></span>
2. <span data-ttu-id="c14d0-133">Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="c14d0-133">In the list, find and select the desired record.</span></span>
3. <span data-ttu-id="c14d0-134">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="c14d0-134">In the list, click the link in the selected row.</span></span>
4. <span data-ttu-id="c14d0-135">Développez ou réduisez la section Règles d'admissibilité.</span><span class="sxs-lookup"><span data-stu-id="c14d0-135">Expand or collapse the Eligibility rules section.</span></span>
5. <span data-ttu-id="c14d0-136">Cliquez sur Modifier.</span><span class="sxs-lookup"><span data-stu-id="c14d0-136">Click Edit.</span></span>
6. <span data-ttu-id="c14d0-137">Dans le champ Admissibilité, sélectionnez Selon les règles dans la liste.</span><span class="sxs-lookup"><span data-stu-id="c14d0-137">In the Eligibility field, select Rule based from the list.</span></span>
7. <span data-ttu-id="c14d0-138">Dans le champ Type de règle, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="c14d0-138">In the Rule type field, click the drop down button to open the lookup.</span></span>
8. <span data-ttu-id="c14d0-139">Dans la liste, recherchez et sélectionnez la règle créée précédemment.</span><span class="sxs-lookup"><span data-stu-id="c14d0-139">In the list find and select the rule you previously created.</span></span>
9. <span data-ttu-id="c14d0-140">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="c14d0-140">In the list, click the link in the selected row.</span></span>
10. <span data-ttu-id="c14d0-141">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="c14d0-141">Click Save.</span></span>
11. <span data-ttu-id="c14d0-142">Permet de fermer l'écran.</span><span class="sxs-lookup"><span data-stu-id="c14d0-142">Close the form.</span></span>


