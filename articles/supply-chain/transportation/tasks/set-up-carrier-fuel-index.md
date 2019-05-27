---
title: Paramétrer un index de carburant du transporteur
description: Ce guide indique comment créer une région de l'index de carburant, un index de carburant et un index de carburant du transporteur.
author: ShylaThompson
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: b6f72de7ad54a2b2dc1bf40fd8cb86d8b055e2d1
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/15/2019
ms.locfileid: "1552090"
---
# <a name="set-up-a-carrier-fuel-index"></a><span data-ttu-id="e766b-103">Paramétrer un index de carburant du transporteur</span><span class="sxs-lookup"><span data-stu-id="e766b-103">Set up a carrier fuel index</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="e766b-104">Ce guide indique comment créer une région de l'index de carburant, un index de carburant et un index de carburant du transporteur.</span><span class="sxs-lookup"><span data-stu-id="e766b-104">This guide shows how to create a fuel index region, a fuel index and a carrier fuel index.</span></span> <span data-ttu-id="e766b-105">La région d'index de carburant spécifie à quelle région l'index doit s'appliquer, et l'index de carburant spécifie un prix du carburant pour une période spécifique.</span><span class="sxs-lookup"><span data-stu-id="e766b-105">The fuel index region specifies which region the fuel index should apply to, and the fuel index specifies a fuel price for a particular period of time.</span></span> <span data-ttu-id="e766b-106">Pour refléter la modification des prix du carburant au fil du temps, vous pouvez associer une région à plusieurs index de carburant à un transporteur.</span><span class="sxs-lookup"><span data-stu-id="e766b-106">To reflect the change in fuel prices over time, you can associate multiple fuel indexes with a carrier.</span></span>  <span data-ttu-id="e766b-107">Ces tâches sont normalement effectuées par un coordinateur de transport.</span><span class="sxs-lookup"><span data-stu-id="e766b-107">These tasks are normally done by a transportation coordinator.</span></span> <span data-ttu-id="e766b-108">Vous pouvez utiliser cette procédure dans les données de démonstration de la société fictive USMF ou utiliser vos propres données.</span><span class="sxs-lookup"><span data-stu-id="e766b-108">You can use this procedure in demo data company USMF or using your own data.</span></span>


## <a name="create-a-fuel-index-region"></a><span data-ttu-id="e766b-109">Créer la région de l'index de carburant</span><span class="sxs-lookup"><span data-stu-id="e766b-109">Create a fuel index region</span></span>
1. <span data-ttu-id="e766b-110">Allez dans Gestion du transport > Configuration > Index de carburant > Régions de l'index de carburant.</span><span class="sxs-lookup"><span data-stu-id="e766b-110">Go to Transportation management > Setup > Fuel indexes > Fuel index regions.</span></span>
    * <span data-ttu-id="e766b-111">Vous devez tout d'abord créer différentes régions, dans lesquelles vous allez traiter et calculer différents suppléments de carburant.</span><span class="sxs-lookup"><span data-stu-id="e766b-111">First you have to create the different regions, where you operate and calculate different fuel surcharges.</span></span>  
2. <span data-ttu-id="e766b-112">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="e766b-112">Click New.</span></span>
3. <span data-ttu-id="e766b-113">Tapez une valeur dans le champ Région.</span><span class="sxs-lookup"><span data-stu-id="e766b-113">In the Region field, type a value.</span></span>
4. <span data-ttu-id="e766b-114">Tapez une valeur dans le champ Nom.</span><span class="sxs-lookup"><span data-stu-id="e766b-114">In the Name field, type a value.</span></span>
5. <span data-ttu-id="e766b-115">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="e766b-115">Click Save.</span></span>

## <a name="create-a-fuel-index"></a><span data-ttu-id="e766b-116">Créer un index de carburant</span><span class="sxs-lookup"><span data-stu-id="e766b-116">Create a fuel index</span></span>
1. <span data-ttu-id="e766b-117">Allez dans Gestion du transport > Configuration > Index de carburant > Index de carburant.</span><span class="sxs-lookup"><span data-stu-id="e766b-117">Go to Transportation management > Setup > Fuel indexes > Fuel indexes.</span></span>
    * <span data-ttu-id="e766b-118">Pour les régions que vous avez paramétrées, vous devez entrer les prix actuels pour le carburant.</span><span class="sxs-lookup"><span data-stu-id="e766b-118">For the regions you have set up you need to enter the current prices for the fuel.</span></span>  
2. <span data-ttu-id="e766b-119">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="e766b-119">Click New.</span></span>
3. <span data-ttu-id="e766b-120">Dans le champ Région, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="e766b-120">In the Region field, click the drop-down button to open the lookup.</span></span>
4. <span data-ttu-id="e766b-121">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="e766b-121">In the list, click the link in the selected row.</span></span>
5. <span data-ttu-id="e766b-122">Entrez un nombre dans le champ Prix par litre.</span><span class="sxs-lookup"><span data-stu-id="e766b-122">In the Price per gallon field, enter a number.</span></span>
6. <span data-ttu-id="e766b-123">Entrez une date et une heure dans le champ Date et heure de début effectives.</span><span class="sxs-lookup"><span data-stu-id="e766b-123">In the Effective start date and time field, enter a date and time.</span></span>
7. <span data-ttu-id="e766b-124">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="e766b-124">Click Save.</span></span>

## <a name="create-a-carrier-fuel-index"></a><span data-ttu-id="e766b-125">Créer un index de carburant du transporteur</span><span class="sxs-lookup"><span data-stu-id="e766b-125">Create a Carrier fuel index</span></span>
1. <span data-ttu-id="e766b-126">Allez dans Gestion du transport > Configuration > Index de carburant > Index de carburant du transporteur.</span><span class="sxs-lookup"><span data-stu-id="e766b-126">Go to Transportation management > Setup > Fuel indexes > Carrier fuel indexes.</span></span>
2. <span data-ttu-id="e766b-127">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="e766b-127">Click New.</span></span>
3. <span data-ttu-id="e766b-128">Saisissez une valeur dans le champ Index de carburant du transporteur.</span><span class="sxs-lookup"><span data-stu-id="e766b-128">In the Carrier fuel index field, type a value.</span></span>
4. <span data-ttu-id="e766b-129">Dans le champ Description, entrez une valeur.</span><span class="sxs-lookup"><span data-stu-id="e766b-129">In the Description field, type a value.</span></span>
5. <span data-ttu-id="e766b-130">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="e766b-130">Click New.</span></span>
6. <span data-ttu-id="e766b-131">Entrez une date et une heure dans le champ Date et heure de début effectives.</span><span class="sxs-lookup"><span data-stu-id="e766b-131">In the Effective start date and time field, enter a date and time.</span></span>
7. <span data-ttu-id="e766b-132">Entrez un nombre dans le champ PPG de départ.</span><span class="sxs-lookup"><span data-stu-id="e766b-132">In the PPG From field, enter a number.</span></span>
    * <span data-ttu-id="e766b-133">Dans cet exemple, vous pouvez définir le champ PPG de départ sur 1,95.</span><span class="sxs-lookup"><span data-stu-id="e766b-133">In this example, you can set PPG From field to 1.95.</span></span>  
8. <span data-ttu-id="e766b-134">Entrez un nombre dans le champ PPG de fin.</span><span class="sxs-lookup"><span data-stu-id="e766b-134">In the PPG To field, enter a number.</span></span>
    * <span data-ttu-id="e766b-135">Dans cet exemple, vous pouvez définir le champ PPG de fin sur 2.</span><span class="sxs-lookup"><span data-stu-id="e766b-135">In this example you can set the PPG To field to 2.</span></span>  
9. <span data-ttu-id="e766b-136">Entrez un nombre dans le champ Pourcentage.</span><span class="sxs-lookup"><span data-stu-id="e766b-136">In the Percentage field, enter a number.</span></span>
    * <span data-ttu-id="e766b-137">Dans cet exemple, vous pouvez définir le pourcentage sur 3.</span><span class="sxs-lookup"><span data-stu-id="e766b-137">In this example you can set the percentage to 3.</span></span>  
10. <span data-ttu-id="e766b-138">Dans le champ Devise, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="e766b-138">In the Currency field, click the drop-down button to open the lookup.</span></span>
11. <span data-ttu-id="e766b-139">Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="e766b-139">In the list, find and select the desired record.</span></span>
12. <span data-ttu-id="e766b-140">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="e766b-140">In the list, click the link in the selected row.</span></span>
13. <span data-ttu-id="e766b-141">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="e766b-141">Click Save.</span></span>

