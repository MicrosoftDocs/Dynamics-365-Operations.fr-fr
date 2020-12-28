---
title: Création d'une ressource opérationnelle
description: Une ressource opérationnelle réalise les activités d'un projet ou d'un processus de production.
author: sorenva
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WrkCtrTable
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: sorenand
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: e2e59b1e6a83d902df98a0b40ee6c572a6567f05
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4427606"
---
# <a name="create-an-operations-resource"></a><span data-ttu-id="2cc0e-103">Création d'une ressource opérationnelle</span><span class="sxs-lookup"><span data-stu-id="2cc0e-103">Create an operations resource</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="2cc0e-104">Une ressource opérationnelle réalise les activités d'un projet ou d'un processus de production.</span><span class="sxs-lookup"><span data-stu-id="2cc0e-104">An operations resource performs the activities of a project or a production process.</span></span> <span data-ttu-id="2cc0e-105">Ces procédures vous indiquent comment définir une ressource opérationnelle.</span><span class="sxs-lookup"><span data-stu-id="2cc0e-105">This procedures shows you how to define an operations resource.</span></span> <span data-ttu-id="2cc0e-106">Vous pouvez parcourir cette procédure dans la société fictive USMF ou utiliser vos propres données.</span><span class="sxs-lookup"><span data-stu-id="2cc0e-106">You can walk through this procedure in demo data company USMF, or using your own data.</span></span>

1. <span data-ttu-id="2cc0e-107">Allez dans Ressources.</span><span class="sxs-lookup"><span data-stu-id="2cc0e-107">Go to Resources.</span></span>
2. <span data-ttu-id="2cc0e-108">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="2cc0e-108">Click New.</span></span>
3. <span data-ttu-id="2cc0e-109">Tapez une valeur dans le champ Ressource.</span><span class="sxs-lookup"><span data-stu-id="2cc0e-109">In the Resource field, type a value.</span></span>
4. <span data-ttu-id="2cc0e-110">Dans le champ Description, entrez une valeur.</span><span class="sxs-lookup"><span data-stu-id="2cc0e-110">In the Description field, type a value.</span></span>

## <a name="define-capacity-and-consumption-parameters"></a><span data-ttu-id="2cc0e-111">Définir des paramètres de consommation et de capacité</span><span class="sxs-lookup"><span data-stu-id="2cc0e-111">Define capacity and consumption parameters</span></span>
1. <span data-ttu-id="2cc0e-112">Développez la section Opération.</span><span class="sxs-lookup"><span data-stu-id="2cc0e-112">Expand the Operation section.</span></span>
2. <span data-ttu-id="2cc0e-113">Entrez un nombre dans le champ Pourcentage de rebut.</span><span class="sxs-lookup"><span data-stu-id="2cc0e-113">In the Scrap percentage field, enter a number.</span></span>
3. <span data-ttu-id="2cc0e-114">Saisissez ou sélectionnez une valeur dans le champ Catégorie de paramétrage.</span><span class="sxs-lookup"><span data-stu-id="2cc0e-114">In the Setup category field, enter or select a value.</span></span>
    * <span data-ttu-id="2cc0e-115">Spécifiez la catégorie de coûts qui définit comment prendre en compte le coût du paramétrage.</span><span class="sxs-lookup"><span data-stu-id="2cc0e-115">Specify the cost category that defines how to account for the cost of setup.</span></span>  
4. <span data-ttu-id="2cc0e-116">Saisissez ou sélectionnez une valeur dans le champ Catégorie de temps d'exécution.</span><span class="sxs-lookup"><span data-stu-id="2cc0e-116">In the Run time category field, enter or select a value.</span></span>
    * <span data-ttu-id="2cc0e-117">Spécifiez la catégorie de coûts qui définit comment prendre en compte le coût du temps d'exécution.</span><span class="sxs-lookup"><span data-stu-id="2cc0e-117">Specify the cost category that defines how to account for the cost of run time.</span></span>  
5. <span data-ttu-id="2cc0e-118">Saisissez ou sélectionnez une valeur dans le champ Catégorie de quantité.</span><span class="sxs-lookup"><span data-stu-id="2cc0e-118">In the Quantity category field, enter or select a value.</span></span>
    * <span data-ttu-id="2cc0e-119">Spécifiez la catégorie de coûts qui définit comment prendre en compte le coût de la ressource selon la quantité produite.</span><span class="sxs-lookup"><span data-stu-id="2cc0e-119">Specify the cost category that defines how to account for the resource cost based on the output quantity.</span></span>  
6. <span data-ttu-id="2cc0e-120">Sélectionnez une option dans le champ Capacité disponible.</span><span class="sxs-lookup"><span data-stu-id="2cc0e-120">In the Capacity unit field, select an option.</span></span>
    * <span data-ttu-id="2cc0e-121">Spécifiez l'unité dans laquelle exprimer la capacité de la ressource opérationnelle.</span><span class="sxs-lookup"><span data-stu-id="2cc0e-121">Specify the unit in which to express the capacity of the operations resource.</span></span>  
7. <span data-ttu-id="2cc0e-122">Entrez un nombre dans le champ Capacité.</span><span class="sxs-lookup"><span data-stu-id="2cc0e-122">In the Capacity field, enter a number.</span></span>
8. <span data-ttu-id="2cc0e-123">Entrez un nombre dans le champ Pourcentage de rendement.</span><span class="sxs-lookup"><span data-stu-id="2cc0e-123">In the Efficiency percentage field, enter a number.</span></span>
    * <span data-ttu-id="2cc0e-124">Spécifiez le rendement attendu de la ressource opérationnelle.</span><span class="sxs-lookup"><span data-stu-id="2cc0e-124">Specify the efficiency that you expect from the operations resource.</span></span> <span data-ttu-id="2cc0e-125">Le pourcentage d'efficacité règle le débit de la ressource opérationnelle et affecte le temps réservé pour celle-ci.</span><span class="sxs-lookup"><span data-stu-id="2cc0e-125">The efficiency percentage adjusts the throughput of the operations resource and affects the time that is reserved for the resource.</span></span>  
9. <span data-ttu-id="2cc0e-126">Entrez un nombre dans le champ Pourcentage d'ordonnancement.</span><span class="sxs-lookup"><span data-stu-id="2cc0e-126">In the Operations scheduling percentage field, enter a number.</span></span>
    * <span data-ttu-id="2cc0e-127">Spécifiez le pourcentage maximal de la capacité de la ressource opérationnelle à utiliser dans la planification d'opérations.</span><span class="sxs-lookup"><span data-stu-id="2cc0e-127">Specify the maximum percentage of capacity of the operations resource that you want to use in operations scheduling.</span></span>  
10. <span data-ttu-id="2cc0e-128">Sélectionnez Oui dans le champ Capacité finie.</span><span class="sxs-lookup"><span data-stu-id="2cc0e-128">Select Yes in the Finite capacity field.</span></span>
    * <span data-ttu-id="2cc0e-129">Définissez cette option sur Oui si la ressource opérationnelle est planifiée en fonction de la capacité réelle disponible, et si les réservations de capacité existantes sont prises en compte.</span><span class="sxs-lookup"><span data-stu-id="2cc0e-129">Set this option to Yes if the operations resource should be scheduled based on the actual capacity that is available, and if existing capacity reservations should be considered.</span></span> <span data-ttu-id="2cc0e-130">Si cette option est définie sur Non, la ressource opérationnelle est supposée avoir une capacité infinie, et elle peut être surréservée.</span><span class="sxs-lookup"><span data-stu-id="2cc0e-130">If this option is set to No, the operations resource is assumed to have infinite capacity, and the resource might be overbooked.</span></span>  
11. <span data-ttu-id="2cc0e-131">Sélectionnez Oui dans le champ Ressource critique.</span><span class="sxs-lookup"><span data-stu-id="2cc0e-131">Select Yes in the Bottleneck resource field.</span></span>

## <a name="define-working-times"></a><span data-ttu-id="2cc0e-132">Définir des temps de travail</span><span class="sxs-lookup"><span data-stu-id="2cc0e-132">Define working times</span></span>
1. <span data-ttu-id="2cc0e-133">Développez la section Calendriers.</span><span class="sxs-lookup"><span data-stu-id="2cc0e-133">Expand the Calendars section.</span></span>
2. <span data-ttu-id="2cc0e-134">Cliquez sur Ajouter.</span><span class="sxs-lookup"><span data-stu-id="2cc0e-134">Click Add.</span></span>
3. <span data-ttu-id="2cc0e-135">Saisissez ou sélectionnez une valeur dans le champ Calendrier.</span><span class="sxs-lookup"><span data-stu-id="2cc0e-135">In the Calendar field, enter or select a value.</span></span>
    * <span data-ttu-id="2cc0e-136">Spécifiez le calendrier de temps de travail qui définit la capacité (en heures) de la ressource.</span><span class="sxs-lookup"><span data-stu-id="2cc0e-136">Specify the working time calendar that defines the capacity (in hours) of the resource.</span></span>  
4. <span data-ttu-id="2cc0e-137">Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="2cc0e-137">In the list, find and select the desired record.</span></span>
5. <span data-ttu-id="2cc0e-138">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="2cc0e-138">In the list, click the link in the selected row.</span></span>

## <a name="define-resource-capabilities"></a><span data-ttu-id="2cc0e-139">Définir des capacités de ressources</span><span class="sxs-lookup"><span data-stu-id="2cc0e-139">Define resource capabilities</span></span>
1. <span data-ttu-id="2cc0e-140">Développez la section Capacités.</span><span class="sxs-lookup"><span data-stu-id="2cc0e-140">Expand the Capabilities section.</span></span>
2. <span data-ttu-id="2cc0e-141">Cliquez sur Ajouter.</span><span class="sxs-lookup"><span data-stu-id="2cc0e-141">Click Add.</span></span>
    * <span data-ttu-id="2cc0e-142">Une capacité est la capacité d'une ressource opérationnelle à exercer une activité spécifique.</span><span class="sxs-lookup"><span data-stu-id="2cc0e-142">A capability is the ability of an operations resource to perform a particular activity.</span></span> <span data-ttu-id="2cc0e-143">Le moteur de planification alloue les ressources en faisant correspondre les demandes de ressources de chaque activité aux capacités des ressources opérationnelles disponibles.</span><span class="sxs-lookup"><span data-stu-id="2cc0e-143">The scheduling engine allocates resources by matching the resource requirements of each activity to the capabilities of the available operations resources.</span></span>  
3. <span data-ttu-id="2cc0e-144">Saisissez ou sélectionnez une valeur dans le champ Capacité.</span><span class="sxs-lookup"><span data-stu-id="2cc0e-144">In the Capability field, enter or select a value.</span></span>
4. <span data-ttu-id="2cc0e-145">Dans le champ Niveau, entrez un nombre.</span><span class="sxs-lookup"><span data-stu-id="2cc0e-145">In the Level field, enter a number.</span></span>
    * <span data-ttu-id="2cc0e-146">Spécifiez le niveau de qualification utilisé par la ressource pour traiter la capacité.</span><span class="sxs-lookup"><span data-stu-id="2cc0e-146">Specify the level of proficiency by which the resource processes the capability.</span></span>  
5. <span data-ttu-id="2cc0e-147">Dans le champ Priorité, entrer un numéro.</span><span class="sxs-lookup"><span data-stu-id="2cc0e-147">In the Priority field, enter a number.</span></span>
    * <span data-ttu-id="2cc0e-148">Spécifiez la priorité de la ressource opérationnelle par rapport à la capacité.</span><span class="sxs-lookup"><span data-stu-id="2cc0e-148">Specify the priority of the operations resource with respect to the capability.</span></span> <span data-ttu-id="2cc0e-149">En planifiant par priorité, la ressource opérationnelle ayant la priorité la plus élevée (la valeur numérique la plus faible) est sélectionnée en premier.</span><span class="sxs-lookup"><span data-stu-id="2cc0e-149">When scheduling by priority, the operations resource with the highest priority (lowest numeric value) is selected first.</span></span>  

## <a name="assign-resource-to-resource-group"></a><span data-ttu-id="2cc0e-150">Affecter une ressource au groupe de ressources</span><span class="sxs-lookup"><span data-stu-id="2cc0e-150">Assign resource to resource group</span></span>
1. <span data-ttu-id="2cc0e-151">Développez la section Groupes de ressources.</span><span class="sxs-lookup"><span data-stu-id="2cc0e-151">Expand the Resource groups section.</span></span>
2. <span data-ttu-id="2cc0e-152">Cliquez sur Ajouter.</span><span class="sxs-lookup"><span data-stu-id="2cc0e-152">Click Add.</span></span>
    * <span data-ttu-id="2cc0e-153">Le groupe de ressources définit le site, l'unité de production et le contexte d'entrepôt pour les ressources opérationnelles.</span><span class="sxs-lookup"><span data-stu-id="2cc0e-153">The resource group defines the site, production unit, and warehouse context for operations resources.</span></span> <span data-ttu-id="2cc0e-154">Les ressources opérationnelles peuvent uniquement être attribuées à un groupe de ressources et uniquement sur le site où se trouve le groupe de ressources.</span><span class="sxs-lookup"><span data-stu-id="2cc0e-154">The operations resource can only be scheduled when assigned to a resource group, and only on the site where the resource group is located.</span></span>  
3. <span data-ttu-id="2cc0e-155">Saisissez ou sélectionnez une valeur dans le champ Groupe de ressources.</span><span class="sxs-lookup"><span data-stu-id="2cc0e-155">In the Resource group field, enter or select a value.</span></span>
4. <span data-ttu-id="2cc0e-156">Saisissez ou sélectionnez une valeur dans le champ Emplacement de l'entrée.</span><span class="sxs-lookup"><span data-stu-id="2cc0e-156">In the Input location field, enter or select a value.</span></span>
    * <span data-ttu-id="2cc0e-157">Spécifiez l'emplacement d'entrepôt d'où la ressource opérationnelle consomme des matières.</span><span class="sxs-lookup"><span data-stu-id="2cc0e-157">Specify the warehouse location from where the operations resource is consuming materials.</span></span>  

