--- 
title: Valider un flux de production et une version
description: "Cette procédure montre comment créer un flux de production et une première version pour la lean manufacturing."
author: ChristianRytt
manager: AnnBe
ms.date: 8/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: LeanProductionFlow
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 32d71167fdad65cb1dec37671999a497759ca484
ms.openlocfilehash: 555a7564c3fc976bdf89d2295518ba9f687e258d
ms.contentlocale: fr-fr
ms.lasthandoff: 09/11/2018

---
# <a name="validate-a-production-flow-and-version"></a><span data-ttu-id="ac974-103">Valider un flux de production et une version</span><span class="sxs-lookup"><span data-stu-id="ac974-103">Validate a production flow and version</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="ac974-104">Cette procédure montre comment créer un flux de production et une première version pour la lean manufacturing.</span><span class="sxs-lookup"><span data-stu-id="ac974-104">This procedure shows how to create a new production flow and a first version for lean manufacturing.</span></span> <span data-ttu-id="ac974-105">Conditions préalables : les paramètres de production pour la lean manufacturing et les unités de mesure du temps des classes doivent être définis.</span><span class="sxs-lookup"><span data-stu-id="ac974-105">Prerequisites: The production parameters for Lean manufacturing and the units of measure for class time must be defined.</span></span> <span data-ttu-id="ac974-106">Vous devez également définir une Chaîne de valeur et un Groupe de production.</span><span class="sxs-lookup"><span data-stu-id="ac974-106">You need to define a Value stream and a Production group.</span></span> <span data-ttu-id="ac974-107">Consultez les livres blancs sur la lean manufacturing pour vous familiariser avec les concepts des flux de production et des activités.</span><span class="sxs-lookup"><span data-stu-id="ac974-107">Refer to the white papers on Lean manufacturing to familiarize yourself with the concepts of production flows and activities.</span></span> <span data-ttu-id="ac974-108">Cette procédure fait référence à l'entité juridique USMF dans les données de démonstration.</span><span class="sxs-lookup"><span data-stu-id="ac974-108">This procedure refers to the legal entity USMF in demo data.</span></span> <span data-ttu-id="ac974-109">Toutefois, en supposant que l'entité juridique est configurée pour la lean manufacturing, il est possible d'utiliser d'autres entités juridiques.</span><span class="sxs-lookup"><span data-stu-id="ac974-109">However, assuming that the legal entity is configured for Lean manufacturing, other legal entities can be used.</span></span>


## <a name="create-a-production-flow"></a><span data-ttu-id="ac974-110">Création d'un flux de production</span><span class="sxs-lookup"><span data-stu-id="ac974-110">Create a production flow</span></span>
1. <span data-ttu-id="ac974-111">Accédez à Contrôle de la production > Paramétrage > Flux de production lean > Flux de production.</span><span class="sxs-lookup"><span data-stu-id="ac974-111">Go to Production control > Setup > Lean production flow > Production flows.</span></span>
2. <span data-ttu-id="ac974-112">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="ac974-112">Click New.</span></span>
3. <span data-ttu-id="ac974-113">Tapez une valeur dans le champ Nom.</span><span class="sxs-lookup"><span data-stu-id="ac974-113">In the Name field, type a value.</span></span>
4. <span data-ttu-id="ac974-114">Dans le champ Description, entrez une valeur.</span><span class="sxs-lookup"><span data-stu-id="ac974-114">In the Description field, type a value.</span></span>
5. <span data-ttu-id="ac974-115">Dans le champ Nom, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="ac974-115">In the Name field, click the drop-down button to open the lookup.</span></span>
6. <span data-ttu-id="ac974-116">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="ac974-116">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="ac974-117">Une chaîne de valeur est une unité opérationnelle qui couvre tous les activités et flux de la chaîne de valeur.</span><span class="sxs-lookup"><span data-stu-id="ac974-117">A value stream is an operating unit that spans over all activities and flows of the value stream.</span></span>   <span data-ttu-id="ac974-118">À ce stade, les unités opérationnelles sont limitées à une entité juridique et n'ont aucune fonctionnalité supplémentaire.</span><span class="sxs-lookup"><span data-stu-id="ac974-118">At this stage, operating units are limited to a legal entity and have no further functionality.</span></span>  
7. <span data-ttu-id="ac974-119">Dans le champ Groupe de production, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="ac974-119">In the Production group field, click the drop-down button to open the lookup.</span></span>
8. <span data-ttu-id="ac974-120">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="ac974-120">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="ac974-121">Les groupes de production permettent de définir les matières, le travail, et les comptes de travaux en cours pour un processus de production.</span><span class="sxs-lookup"><span data-stu-id="ac974-121">Production groups allow the definition of material, labor, and WIP accounts for a production process.</span></span> <span data-ttu-id="ac974-122">Pour associer le contexte de comptabilité à un flux de production, il convient de créer un groupe de production.</span><span class="sxs-lookup"><span data-stu-id="ac974-122">To associate the accounting context to a production flow, a production group must be selected.</span></span>  
9. <span data-ttu-id="ac974-123">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="ac974-123">Click Save.</span></span>

## <a name="create-a-production-flow-version"></a><span data-ttu-id="ac974-124">Créer une version de flux de production</span><span class="sxs-lookup"><span data-stu-id="ac974-124">Create a production flow version</span></span>
1. <span data-ttu-id="ac974-125">Cliquez sur Ajouter.</span><span class="sxs-lookup"><span data-stu-id="ac974-125">Click Add.</span></span>
2. <span data-ttu-id="ac974-126">Entrez une date et une heure dans le champ Date d'expiration.</span><span class="sxs-lookup"><span data-stu-id="ac974-126">In the Expiration date field, enter a date and time.</span></span>
    * <span data-ttu-id="ac974-127">Vous pouvez mettre à jour la date d'expiration de la version à tout moment, même pour les versions actives.</span><span class="sxs-lookup"><span data-stu-id="ac974-127">You can update the Expiration date of the version at any given time, even for active versions.</span></span> <span data-ttu-id="ac974-128">Utilisez l'expiration de la version pour planifier une suppression progressive d'une version.</span><span class="sxs-lookup"><span data-stu-id="ac974-128">Use the expiration of the version to plan for a phase out of a version.</span></span>  
3. <span data-ttu-id="ac974-129">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="ac974-129">Click OK.</span></span>
4. <span data-ttu-id="ac974-130">Dans la liste, marquez la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="ac974-130">In the list, mark the selected row.</span></span>
5. <span data-ttu-id="ac974-131">Dans le champ Unité, tapez une valeur.</span><span class="sxs-lookup"><span data-stu-id="ac974-131">In the Unit field, type a value.</span></span>
6. <span data-ttu-id="ac974-132">Sélectionner l'unité de takt.</span><span class="sxs-lookup"><span data-stu-id="ac974-132">Select the Takt unit.</span></span>
7. <span data-ttu-id="ac974-133">Dans le champ Takt time moyen, entrez un nombre.</span><span class="sxs-lookup"><span data-stu-id="ac974-133">In the Average takt time field, enter a number.</span></span>
    * <span data-ttu-id="ac974-134">Pour le contrôle takt de la version du flux de production, définissez un takt time moyen cible.</span><span class="sxs-lookup"><span data-stu-id="ac974-134">For the takt control of the production flow version, define a targeted average takt time.</span></span>   <span data-ttu-id="ac974-135">Le takt est défini comme une quantité par période.</span><span class="sxs-lookup"><span data-stu-id="ac974-135">The takt is defined as quantity  per time period.</span></span>  <span data-ttu-id="ac974-136">Dans l'exemple, le takt time est de 0,2 heures par 10 pièces.</span><span class="sxs-lookup"><span data-stu-id="ac974-136">In the given example, the takt time is 0.2 hours per 10 pieces.</span></span> <span data-ttu-id="ac974-137">Pour une durée de travail de 8 heures, cela correspond à une capacité de production journalière de 400 pièces.</span><span class="sxs-lookup"><span data-stu-id="ac974-137">For a working time of 8 hours, this corresponds to a daily throughput capacity of 400 pieces.</span></span>  
8. <span data-ttu-id="ac974-138">Entrez un numéro dans le champ Quantité par cycle.</span><span class="sxs-lookup"><span data-stu-id="ac974-138">In the Quantity per cycle field, enter a number.</span></span>
9. <span data-ttu-id="ac974-139">Développez ou réduisez la section Détails de la version.</span><span class="sxs-lookup"><span data-stu-id="ac974-139">Expand or collapse the Version details section.</span></span>
10. <span data-ttu-id="ac974-140">Dans le champ Takt time minimal, entrez un nombre.</span><span class="sxs-lookup"><span data-stu-id="ac974-140">In the Minimum takt time field, enter a number.</span></span>
    * <span data-ttu-id="ac974-141">Le takt time minimal doit être inférieur ou égal au takt time moyen.</span><span class="sxs-lookup"><span data-stu-id="ac974-141">The minimum takt time must be less than or equal to the average takt time.</span></span>  
11. <span data-ttu-id="ac974-142">Dans le champ Takt time maximal, entrez un nombre.</span><span class="sxs-lookup"><span data-stu-id="ac974-142">In the Maximum takt time field, enter a number.</span></span>
    * <span data-ttu-id="ac974-143">Le takt time maximal doit être supérieur ou égal au takt time moyen.</span><span class="sxs-lookup"><span data-stu-id="ac974-143">The maximum takt time must be higher than or equal to the Average takt time.</span></span>  
12. <span data-ttu-id="ac974-144">Entrez un nombre de jours dans la période pour la durée de cycle réelle.</span><span class="sxs-lookup"><span data-stu-id="ac974-144">Enter a number of days in the Period for actual cycle time</span></span>
    * <span data-ttu-id="ac974-145">La période pour la durée de cycle réelle est le nombre de jours pendant lesquels les tâches sont regroupées à rebours à partir de la minute actuelle pour calculer la durée de cycle réelle.</span><span class="sxs-lookup"><span data-stu-id="ac974-145">The period for actual cycle time is the number of days that jobs are aggregated from the actual minute backwards to calculate the actual cycle time.</span></span> <span data-ttu-id="ac974-146">Cette valeur peut être modifiée à tout moment et n'est utilisée que pour le calcul des durées de cycle réelles.</span><span class="sxs-lookup"><span data-stu-id="ac974-146">The value can be changed at any time and is only used for the calculation of the actual cycle times.</span></span>  
13. <span data-ttu-id="ac974-147">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="ac974-147">Click Save.</span></span>


