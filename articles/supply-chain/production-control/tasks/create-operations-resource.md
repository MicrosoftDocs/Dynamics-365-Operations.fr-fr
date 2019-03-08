---
title: Création d'une ressource opérationnelle
description: Une ressource opérationnelle réalise les activités d'un projet ou d'un processus de production.
author: sorenva
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WrkCtrTable
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: sorenand
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: f9d8f13e29ea813eb9721ddca795b67837e2aa5e
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/29/2019
ms.locfileid: "350065"
---
# <a name="create-an-operations-resource"></a><span data-ttu-id="67006-103">Création d'une ressource opérationnelle</span><span class="sxs-lookup"><span data-stu-id="67006-103">Create an operations resource</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="67006-104">Une ressource opérationnelle réalise les activités d'un projet ou d'un processus de production.</span><span class="sxs-lookup"><span data-stu-id="67006-104">An operations resource performs the activities of a project or a production process.</span></span> <span data-ttu-id="67006-105">Ces procédures vous indiquent comment définir une ressource opérationnelle.</span><span class="sxs-lookup"><span data-stu-id="67006-105">This procedures shows you how to define an operations resource.</span></span> <span data-ttu-id="67006-106">Vous pouvez parcourir cette procédure dans la société fictive USMF ou utiliser vos propres données.</span><span class="sxs-lookup"><span data-stu-id="67006-106">You can walk through this procedure in demo data company USMF, or using your own data.</span></span>

1. <span data-ttu-id="67006-107">Allez dans Ressources.</span><span class="sxs-lookup"><span data-stu-id="67006-107">Go to Resources.</span></span>
2. <span data-ttu-id="67006-108">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="67006-108">Click New.</span></span>
3. <span data-ttu-id="67006-109">Tapez une valeur dans le champ Ressource.</span><span class="sxs-lookup"><span data-stu-id="67006-109">In the Resource field, type a value.</span></span>
4. <span data-ttu-id="67006-110">Dans le champ Description, entrez une valeur.</span><span class="sxs-lookup"><span data-stu-id="67006-110">In the Description field, type a value.</span></span>

## <a name="define-capacity-and-consumption-parameters"></a><span data-ttu-id="67006-111">Définir des paramètres de consommation et de capacité</span><span class="sxs-lookup"><span data-stu-id="67006-111">Define capacity and consumption parameters</span></span>
1. <span data-ttu-id="67006-112">Développez la section Opération.</span><span class="sxs-lookup"><span data-stu-id="67006-112">Expand the Operation section.</span></span>
2. <span data-ttu-id="67006-113">Entrez un nombre dans le champ Pourcentage de rebut.</span><span class="sxs-lookup"><span data-stu-id="67006-113">In the Scrap percentage field, enter a number.</span></span>
3. <span data-ttu-id="67006-114">Saisissez ou sélectionnez une valeur dans le champ Catégorie de paramétrage.</span><span class="sxs-lookup"><span data-stu-id="67006-114">In the Setup category field, enter or select a value.</span></span>
    * <span data-ttu-id="67006-115">Spécifiez la catégorie de coûts qui définit comment prendre en compte le coût du paramétrage.</span><span class="sxs-lookup"><span data-stu-id="67006-115">Specify the cost category that defines how to account for the cost of setup.</span></span>  
4. <span data-ttu-id="67006-116">Saisissez ou sélectionnez une valeur dans le champ Catégorie de temps d'exécution.</span><span class="sxs-lookup"><span data-stu-id="67006-116">In the Run time category field, enter or select a value.</span></span>
    * <span data-ttu-id="67006-117">Spécifiez la catégorie de coûts qui définit comment prendre en compte le coût du temps d'exécution.</span><span class="sxs-lookup"><span data-stu-id="67006-117">Specify the cost category that defines how to account for the cost of run time.</span></span>  
5. <span data-ttu-id="67006-118">Saisissez ou sélectionnez une valeur dans le champ Catégorie de quantité.</span><span class="sxs-lookup"><span data-stu-id="67006-118">In the Quantity category field, enter or select a value.</span></span>
    * <span data-ttu-id="67006-119">Spécifiez la catégorie de coûts qui définit comment prendre en compte le coût de la ressource selon la quantité produite.</span><span class="sxs-lookup"><span data-stu-id="67006-119">Specify the cost category that defines how to account for the resource cost based on the output quantity.</span></span>  
6. <span data-ttu-id="67006-120">Sélectionnez une option dans le champ Capacité disponible.</span><span class="sxs-lookup"><span data-stu-id="67006-120">In the Capacity unit field, select an option.</span></span>
    * <span data-ttu-id="67006-121">Spécifiez l'unité dans laquelle exprimer la capacité de la ressource opérationnelle.</span><span class="sxs-lookup"><span data-stu-id="67006-121">Specify the unit in which to express the capacity of the operations resource.</span></span>  
7. <span data-ttu-id="67006-122">Entrez un nombre dans le champ Capacité.</span><span class="sxs-lookup"><span data-stu-id="67006-122">In the Capacity field, enter a number.</span></span>
8. <span data-ttu-id="67006-123">Entrez un nombre dans le champ Pourcentage de rendement.</span><span class="sxs-lookup"><span data-stu-id="67006-123">In the Efficiency percentage field, enter a number.</span></span>
    * <span data-ttu-id="67006-124">Spécifiez le rendement attendu de la ressource opérationnelle.</span><span class="sxs-lookup"><span data-stu-id="67006-124">Specify the efficiency that you expect from the operations resource.</span></span> <span data-ttu-id="67006-125">Le pourcentage d'efficacité règle le débit de la ressource opérationnelle et affecte le temps réservé pour celle-ci.</span><span class="sxs-lookup"><span data-stu-id="67006-125">The efficiency percentage adjusts the throughput of the operations resource and affects the time that is reserved for the resource.</span></span>  
9. <span data-ttu-id="67006-126">Entrez un nombre dans le champ Pourcentage d'ordonnancement.</span><span class="sxs-lookup"><span data-stu-id="67006-126">In the Operations scheduling percentage field, enter a number.</span></span>
    * <span data-ttu-id="67006-127">Spécifiez le pourcentage maximal de la capacité de la ressource opérationnelle à utiliser dans la planification d'opérations.</span><span class="sxs-lookup"><span data-stu-id="67006-127">Specify the maximum percentage of capacity of the operations resource that you want to use in operations scheduling.</span></span>  
10. <span data-ttu-id="67006-128">Sélectionnez Oui dans le champ Capacité finie.</span><span class="sxs-lookup"><span data-stu-id="67006-128">Select Yes in the Finite capacity field.</span></span>
    * <span data-ttu-id="67006-129">Définissez cette option sur Oui si la ressource opérationnelle est planifiée en fonction de la capacité réelle disponible, et si les réservations de capacité existantes sont prises en compte.</span><span class="sxs-lookup"><span data-stu-id="67006-129">Set this option to Yes if the operations resource should be scheduled based on the actual capacity that is available, and if existing capacity reservations should be considered.</span></span> <span data-ttu-id="67006-130">Si cette option est définie sur Non, la ressource opérationnelle est supposée avoir une capacité infinie, et elle peut être surréservée.</span><span class="sxs-lookup"><span data-stu-id="67006-130">If this option is set to No, the operations resource is assumed to have infinite capacity, and the resource might be overbooked.</span></span>  
11. <span data-ttu-id="67006-131">Sélectionnez Oui dans le champ Ressource critique.</span><span class="sxs-lookup"><span data-stu-id="67006-131">Select Yes in the Bottleneck resource field.</span></span>

## <a name="define-working-times"></a><span data-ttu-id="67006-132">Définir des temps de travail</span><span class="sxs-lookup"><span data-stu-id="67006-132">Define working times</span></span>
1. <span data-ttu-id="67006-133">Développez la section Calendriers.</span><span class="sxs-lookup"><span data-stu-id="67006-133">Expand the Calendars section.</span></span>
2. <span data-ttu-id="67006-134">Cliquez sur Ajouter.</span><span class="sxs-lookup"><span data-stu-id="67006-134">Click Add.</span></span>
3. <span data-ttu-id="67006-135">Saisissez ou sélectionnez une valeur dans le champ Calendrier.</span><span class="sxs-lookup"><span data-stu-id="67006-135">In the Calendar field, enter or select a value.</span></span>
    * <span data-ttu-id="67006-136">Spécifiez le calendrier de temps de travail qui définit la capacité (en heures) de la ressource.</span><span class="sxs-lookup"><span data-stu-id="67006-136">Specify the working time calendar that defines the capacity (in hours) of the resource.</span></span>  
4. <span data-ttu-id="67006-137">Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="67006-137">In the list, find and select the desired record.</span></span>
5. <span data-ttu-id="67006-138">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="67006-138">In the list, click the link in the selected row.</span></span>

## <a name="define-resource-capabilities"></a><span data-ttu-id="67006-139">Définir des capacités de ressources</span><span class="sxs-lookup"><span data-stu-id="67006-139">Define resource capabilities</span></span>
1. <span data-ttu-id="67006-140">Développez la section Capacités.</span><span class="sxs-lookup"><span data-stu-id="67006-140">Expand the Capabilities section.</span></span>
2. <span data-ttu-id="67006-141">Cliquez sur Ajouter.</span><span class="sxs-lookup"><span data-stu-id="67006-141">Click Add.</span></span>
    * <span data-ttu-id="67006-142">Une capacité est la capacité d'une ressource opérationnelle à exercer une activité spécifique.</span><span class="sxs-lookup"><span data-stu-id="67006-142">A capability is the ability of an operations resource to perform a particular activity.</span></span> <span data-ttu-id="67006-143">Le moteur de planification alloue les ressources en faisant correspondre les demandes de ressources de chaque activité aux capacités des ressources opérationnelles disponibles.</span><span class="sxs-lookup"><span data-stu-id="67006-143">The scheduling engine allocates resources by matching the resource requirements of each activity to the capabilities of the available operations resources.</span></span>  
3. <span data-ttu-id="67006-144">Saisissez ou sélectionnez une valeur dans le champ Capacité.</span><span class="sxs-lookup"><span data-stu-id="67006-144">In the Capability field, enter or select a value.</span></span>
4. <span data-ttu-id="67006-145">Dans le champ Niveau, entrez un nombre.</span><span class="sxs-lookup"><span data-stu-id="67006-145">In the Level field, enter a number.</span></span>
    * <span data-ttu-id="67006-146">Spécifiez le niveau de qualification utilisé par la ressource pour traiter la capacité.</span><span class="sxs-lookup"><span data-stu-id="67006-146">Specify the level of proficiency by which the resource processes the capability.</span></span>  
5. <span data-ttu-id="67006-147">Dans le champ Priorité, entrer un numéro.</span><span class="sxs-lookup"><span data-stu-id="67006-147">In the Priority field, enter a number.</span></span>
    * <span data-ttu-id="67006-148">Spécifiez la priorité de la ressource opérationnelle par rapport à la capacité.</span><span class="sxs-lookup"><span data-stu-id="67006-148">Specify the priority of the operations resource with respect to the capability.</span></span> <span data-ttu-id="67006-149">En planifiant par priorité, la ressource opérationnelle ayant la priorité la plus élevée (la valeur numérique la plus faible) est sélectionnée en premier.</span><span class="sxs-lookup"><span data-stu-id="67006-149">When scheduling by priority, the operations resource with the highest priority (lowest numeric value) is selected first.</span></span>  

## <a name="assign-resource-to-resource-group"></a><span data-ttu-id="67006-150">Affecter une ressource au groupe de ressources</span><span class="sxs-lookup"><span data-stu-id="67006-150">Assign resource to resource group</span></span>
1. <span data-ttu-id="67006-151">Développez la section Groupes de ressources.</span><span class="sxs-lookup"><span data-stu-id="67006-151">Expand the Resource groups section.</span></span>
2. <span data-ttu-id="67006-152">Cliquez sur Ajouter.</span><span class="sxs-lookup"><span data-stu-id="67006-152">Click Add.</span></span>
    * <span data-ttu-id="67006-153">Le groupe de ressources définit le site, l'unité de production et le contexte d'entrepôt pour les ressources opérationnelles.</span><span class="sxs-lookup"><span data-stu-id="67006-153">The resource group defines the site, production unit, and warehouse context for operations resources.</span></span> <span data-ttu-id="67006-154">Les ressources opérationnelles peuvent uniquement être attribuées à un groupe de ressources et uniquement sur le site où se trouve le groupe de ressources.</span><span class="sxs-lookup"><span data-stu-id="67006-154">The operations resource can only be scheduled when assigned to a resource group, and only on the site where the resource group is located.</span></span>  
3. <span data-ttu-id="67006-155">Saisissez ou sélectionnez une valeur dans le champ Groupe de ressources.</span><span class="sxs-lookup"><span data-stu-id="67006-155">In the Resource group field, enter or select a value.</span></span>
4. <span data-ttu-id="67006-156">Saisissez ou sélectionnez une valeur dans le champ Emplacement de l'entrée.</span><span class="sxs-lookup"><span data-stu-id="67006-156">In the Input location field, enter or select a value.</span></span>
    * <span data-ttu-id="67006-157">Spécifiez l'emplacement d'entrepôt d'où la ressource opérationnelle consomme des matières.</span><span class="sxs-lookup"><span data-stu-id="67006-157">Specify the warehouse location from where the operations resource is consuming materials.</span></span>  

