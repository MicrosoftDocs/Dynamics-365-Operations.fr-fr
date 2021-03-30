---
title: Créer et affecter une stratégie de distribution des coûts à une unité de contrôle des coûts
description: Les règles de distribution des coûts sont utilisées pour distribuer les coûts qui ont été financièrement comptabilisés sur un centre de coût collectif.
author: ShylaThompson
manager: AnnBe
ms.date: 06/27/2017
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CAMCostDistributionRule
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 946d188652e8f5b45d5c31a5aa0640d5362ef554
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5208677"
---
# <a name="create-and-assign-a-cost-distribution-policy-to-a-cost-control-unit"></a><span data-ttu-id="6896d-103">Créer et affecter une stratégie de distribution des coûts à une unité de contrôle des coûts</span><span class="sxs-lookup"><span data-stu-id="6896d-103">Create and assign a cost distribution policy to a cost control unit</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="6896d-104">Les règles de distribution des coûts sont utilisées pour distribuer les coûts qui ont été financièrement comptabilisés sur un centre de coût collectif.</span><span class="sxs-lookup"><span data-stu-id="6896d-104">Cost distribution rules are used to distribute costs that have been financially counted on a collective cost center.</span></span> <span data-ttu-id="6896d-105">Le comptable s’assure que le coût est distribué sur les centres de coût, selon la base de répartition sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="6896d-105">The cost accountant makes sure that the cost is distributed to the cost centers, based on the selected allocation base.</span></span> <span data-ttu-id="6896d-106">Une stratégie et les règles correspondantes sont affectées à une unité de contrôle des coûts.</span><span class="sxs-lookup"><span data-stu-id="6896d-106">A policy and the corresponding rules are assigned to a cost control unit.</span></span> <span data-ttu-id="6896d-107">Ce guide de tâche utilise un exemple pour indiquer comment créer une stratégie de distribution des coûts et les règles correspondantes.</span><span class="sxs-lookup"><span data-stu-id="6896d-107">This task guide uses an example to show how to create a cost distribution policy and the corresponding rules.</span></span>


## <a name="create-a-policy"></a><span data-ttu-id="6896d-108">Créer une stratégie</span><span class="sxs-lookup"><span data-stu-id="6896d-108">Create a policy</span></span>
1. <span data-ttu-id="6896d-109">Accédez à Contrôle de gestion > Stratégies > Stratégies de distribution des coûts.</span><span class="sxs-lookup"><span data-stu-id="6896d-109">Go to Cost accounting > Policies > Cost distribution policies.</span></span>
2. <span data-ttu-id="6896d-110">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="6896d-110">Click New.</span></span>
3. <span data-ttu-id="6896d-111">Dans le champ Nom de la stratégie, tapez une valeur.</span><span class="sxs-lookup"><span data-stu-id="6896d-111">In the Policy name field, type a value.</span></span>
4. <span data-ttu-id="6896d-112">Dans le champ Description, entrez une valeur.</span><span class="sxs-lookup"><span data-stu-id="6896d-112">In the Description field, type a value.</span></span>
5. <span data-ttu-id="6896d-113">Dans le champ Hiérarchie des dimensions d’objet de coût, entrez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="6896d-113">In the Cost object dimension hierarchy field, enter or select a value.</span></span>
    * <span data-ttu-id="6896d-114">Sélectionnez Organisation.</span><span class="sxs-lookup"><span data-stu-id="6896d-114">Select Organization.</span></span>  
6. <span data-ttu-id="6896d-115">Dans le champ Hiérarchie des dimensions d’élément de coût, entrez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="6896d-115">In the Cost element dimension hierarchy field, enter or select a value.</span></span>
    * <span data-ttu-id="6896d-116">Sélectionnez CDS P/L.</span><span class="sxs-lookup"><span data-stu-id="6896d-116">Select CDS P/L.</span></span>  
7. <span data-ttu-id="6896d-117">Dans le champ Dimension statistique, entrez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="6896d-117">In the Statistical dimension field, enter or select a value.</span></span>
    * <span data-ttu-id="6896d-118">Sélectionnez Éléments statistiques.</span><span class="sxs-lookup"><span data-stu-id="6896d-118">Select Statistical elements.</span></span>  
8. <span data-ttu-id="6896d-119">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="6896d-119">Click Save.</span></span>

## <a name="create-rules-for-the-policy"></a><span data-ttu-id="6896d-120">Créer des règles pour la stratégie</span><span class="sxs-lookup"><span data-stu-id="6896d-120">Create rules for the policy</span></span>
1. <span data-ttu-id="6896d-121">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="6896d-121">Click New.</span></span>
2. <span data-ttu-id="6896d-122">Dans la liste, marquez la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="6896d-122">In the list, mark the selected row.</span></span>
3. <span data-ttu-id="6896d-123">Dans le champ Nœud de hiérarchie des dimensions d’objet de coût, entrez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="6896d-123">In the Cost object dimension hierarchy node field, enter or select a value.</span></span>
    * <span data-ttu-id="6896d-124">Développez la hiérarchie pour sélectionner 094.</span><span class="sxs-lookup"><span data-stu-id="6896d-124">Expand the hierarchy to select 094.</span></span>  
4. <span data-ttu-id="6896d-125">Dans le champ Nœud de hiérarchie des dimensions d’élément de coût, entrez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="6896d-125">In the Cost element dimension hierarchy node field, enter or select a value.</span></span>
    * <span data-ttu-id="6896d-126">Sélectionnez Autres dépenses d’exploitation, puis sélectionnez 605110 Nettoyage.</span><span class="sxs-lookup"><span data-stu-id="6896d-126">Select Other operating expenses and then select 605110 Cleaning.</span></span>  
5. <span data-ttu-id="6896d-127">Dans le champ Comportement de coûts, sélectionnez une option.</span><span class="sxs-lookup"><span data-stu-id="6896d-127">In the Cost behavior field, select an option.</span></span>
    * <span data-ttu-id="6896d-128">Sélectionnez Coût fixe.</span><span class="sxs-lookup"><span data-stu-id="6896d-128">Select Fixed cost.</span></span>  
6. <span data-ttu-id="6896d-129">Dans le champ Base de répartition, entrez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="6896d-129">In the Allocation base field, enter or select a value.</span></span>
7. <span data-ttu-id="6896d-130">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="6896d-130">Click New.</span></span>
8. <span data-ttu-id="6896d-131">Dans la liste, marquer la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="6896d-131">In the list, mark the selected row.</span></span>
9. <span data-ttu-id="6896d-132">Dans le champ Nœud de hiérarchie des dimensions d’objet de coût, entrez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="6896d-132">In the Cost object dimension hierarchy node field, enter or select a value.</span></span>
    * <span data-ttu-id="6896d-133">Développez la hiérarchie pour sélectionner 094.</span><span class="sxs-lookup"><span data-stu-id="6896d-133">Expand the hierarchy to select 094.</span></span>  
10. <span data-ttu-id="6896d-134">Dans le champ Nœud de hiérarchie des dimensions d’élément de coût, entrez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="6896d-134">In the Cost element dimension hierarchy node field, enter or select a value.</span></span>
    * <span data-ttu-id="6896d-135">Sélectionnez Autres dépenses d’exploitation, puis sélectionnez 605150 Loyer.</span><span class="sxs-lookup"><span data-stu-id="6896d-135">Select Other operating expenses and then select 605150 Rent.</span></span>  
11. <span data-ttu-id="6896d-136">Dans le champ Comportement de coûts, sélectionnez une option.</span><span class="sxs-lookup"><span data-stu-id="6896d-136">In the Cost behavior field, select an option.</span></span>
    * <span data-ttu-id="6896d-137">Sélectionnez Coût fixe.</span><span class="sxs-lookup"><span data-stu-id="6896d-137">Select Fixed cost.</span></span>  
12. <span data-ttu-id="6896d-138">Dans le champ Base de répartition, entrez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="6896d-138">In the Allocation base field, enter or select a value.</span></span>
13. <span data-ttu-id="6896d-139">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="6896d-139">Click Save.</span></span>

## <a name="assign-rules-to-a-cost-control-unit"></a><span data-ttu-id="6896d-140">Affecter des règles à une unité de contrôle des coûts</span><span class="sxs-lookup"><span data-stu-id="6896d-140">Assign rules to a cost control unit</span></span>
1. <span data-ttu-id="6896d-141">Cliquez sur Affectations de stratégie pour l’unité de contrôle des coûts.</span><span class="sxs-lookup"><span data-stu-id="6896d-141">Click Policy assignments for cost control unit.</span></span>
2. <span data-ttu-id="6896d-142">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="6896d-142">Click New.</span></span>
3. <span data-ttu-id="6896d-143">Dans la liste, marquez la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="6896d-143">In the list, mark the selected row.</span></span>
4. <span data-ttu-id="6896d-144">Dans le champ Valide à partir de la date comptable, entrez une date.</span><span class="sxs-lookup"><span data-stu-id="6896d-144">In the Valid from accounting date field, enter a date.</span></span>
    * <span data-ttu-id="6896d-145">Sélectionnez le 1er septembre dans l’exercice valide.</span><span class="sxs-lookup"><span data-stu-id="6896d-145">Select September 1 in the valid fiscal year.</span></span>  
5. <span data-ttu-id="6896d-146">Dans le champ Unité de contrôle des coûts, entrez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="6896d-146">In the Cost control unit field, enter or select a value.</span></span>
6. <span data-ttu-id="6896d-147">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="6896d-147">Click Save.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]