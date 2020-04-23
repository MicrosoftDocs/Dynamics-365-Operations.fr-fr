---
title: Paramétrer un index de carburant du transporteur
description: Ce guide indique comment créer une région de l'index de carburant, un index de carburant et un index de carburant du transporteur.
author: ShylaThompson
manager: tfehr
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 69bf6e3a896e560b1dbb96c8f997f6ee8dbb9ec1
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/02/2020
ms.locfileid: "3214916"
---
# <a name="set-up-a-carrier-fuel-index"></a><span data-ttu-id="7011b-103">Paramétrer un index de carburant du transporteur</span><span class="sxs-lookup"><span data-stu-id="7011b-103">Set up a carrier fuel index</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="7011b-104">Ce guide indique comment créer une région de l'index de carburant, un index de carburant et un index de carburant du transporteur.</span><span class="sxs-lookup"><span data-stu-id="7011b-104">This guide shows how to create a fuel index region, a fuel index and a carrier fuel index.</span></span> <span data-ttu-id="7011b-105">La région d'index de carburant spécifie à quelle région l'index doit s'appliquer, et l'index de carburant spécifie un prix du carburant pour une période spécifique.</span><span class="sxs-lookup"><span data-stu-id="7011b-105">The fuel index region specifies which region the fuel index should apply to, and the fuel index specifies a fuel price for a particular period of time.</span></span> <span data-ttu-id="7011b-106">Pour refléter la modification des prix du carburant au fil du temps, vous pouvez associer une région à plusieurs index de carburant à un transporteur.</span><span class="sxs-lookup"><span data-stu-id="7011b-106">To reflect the change in fuel prices over time, you can associate multiple fuel indexes with a carrier.</span></span>  <span data-ttu-id="7011b-107">Ces tâches sont normalement effectuées par un coordinateur de transport.</span><span class="sxs-lookup"><span data-stu-id="7011b-107">These tasks are normally done by a transportation coordinator.</span></span> <span data-ttu-id="7011b-108">Vous pouvez utiliser cette procédure dans les données de démonstration de la société fictive USMF ou utiliser vos propres données.</span><span class="sxs-lookup"><span data-stu-id="7011b-108">You can use this procedure in demo data company USMF or using your own data.</span></span>


## <a name="create-a-fuel-index-region"></a><span data-ttu-id="7011b-109">Créer la région de l'index de carburant</span><span class="sxs-lookup"><span data-stu-id="7011b-109">Create a fuel index region</span></span>
1. <span data-ttu-id="7011b-110">Allez dans Gestion du transport > Configuration > Index de carburant > Régions de l'index de carburant.</span><span class="sxs-lookup"><span data-stu-id="7011b-110">Go to Transportation management > Setup > Fuel indexes > Fuel index regions.</span></span>
    * <span data-ttu-id="7011b-111">Vous devez tout d'abord créer différentes régions, dans lesquelles vous allez traiter et calculer différents suppléments de carburant.</span><span class="sxs-lookup"><span data-stu-id="7011b-111">First you have to create the different regions, where you operate and calculate different fuel surcharges.</span></span>  
2. <span data-ttu-id="7011b-112">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="7011b-112">Click New.</span></span>
3. <span data-ttu-id="7011b-113">Tapez une valeur dans le champ Région.</span><span class="sxs-lookup"><span data-stu-id="7011b-113">In the Region field, type a value.</span></span>
4. <span data-ttu-id="7011b-114">Tapez une valeur dans le champ Nom.</span><span class="sxs-lookup"><span data-stu-id="7011b-114">In the Name field, type a value.</span></span>
5. <span data-ttu-id="7011b-115">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="7011b-115">Click Save.</span></span>

## <a name="create-a-fuel-index"></a><span data-ttu-id="7011b-116">Créer un index de carburant</span><span class="sxs-lookup"><span data-stu-id="7011b-116">Create a fuel index</span></span>
1. <span data-ttu-id="7011b-117">Allez dans Gestion du transport > Configuration > Index de carburant > Index de carburant.</span><span class="sxs-lookup"><span data-stu-id="7011b-117">Go to Transportation management > Setup > Fuel indexes > Fuel indexes.</span></span>
    * <span data-ttu-id="7011b-118">Pour les régions que vous avez paramétrées, vous devez entrer les prix actuels pour le carburant.</span><span class="sxs-lookup"><span data-stu-id="7011b-118">For the regions you have set up you need to enter the current prices for the fuel.</span></span>  
2. <span data-ttu-id="7011b-119">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="7011b-119">Click New.</span></span>
3. <span data-ttu-id="7011b-120">Dans le champ Région, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="7011b-120">In the Region field, click the drop-down button to open the lookup.</span></span>
4. <span data-ttu-id="7011b-121">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="7011b-121">In the list, click the link in the selected row.</span></span>
5. <span data-ttu-id="7011b-122">Entrez un nombre dans le champ Prix par litre.</span><span class="sxs-lookup"><span data-stu-id="7011b-122">In the Price per gallon field, enter a number.</span></span>
6. <span data-ttu-id="7011b-123">Entrez une date et une heure dans le champ Date et heure de début effectives.</span><span class="sxs-lookup"><span data-stu-id="7011b-123">In the Effective start date and time field, enter a date and time.</span></span>
7. <span data-ttu-id="7011b-124">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="7011b-124">Click Save.</span></span>

## <a name="create-a-carrier-fuel-index"></a><span data-ttu-id="7011b-125">Créer un index de carburant du transporteur</span><span class="sxs-lookup"><span data-stu-id="7011b-125">Create a Carrier fuel index</span></span>
1. <span data-ttu-id="7011b-126">Allez dans Gestion du transport > Configuration > Index de carburant > Index de carburant du transporteur.</span><span class="sxs-lookup"><span data-stu-id="7011b-126">Go to Transportation management > Setup > Fuel indexes > Carrier fuel indexes.</span></span>
2. <span data-ttu-id="7011b-127">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="7011b-127">Click New.</span></span>
3. <span data-ttu-id="7011b-128">Saisissez une valeur dans le champ Index de carburant du transporteur.</span><span class="sxs-lookup"><span data-stu-id="7011b-128">In the Carrier fuel index field, type a value.</span></span>
4. <span data-ttu-id="7011b-129">Dans le champ Description, entrez une valeur.</span><span class="sxs-lookup"><span data-stu-id="7011b-129">In the Description field, type a value.</span></span>
5. <span data-ttu-id="7011b-130">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="7011b-130">Click New.</span></span>
6. <span data-ttu-id="7011b-131">Entrez une date et une heure dans le champ Date et heure de début effectives.</span><span class="sxs-lookup"><span data-stu-id="7011b-131">In the Effective start date and time field, enter a date and time.</span></span>
7. <span data-ttu-id="7011b-132">Entrez un nombre dans le champ PPG de départ.</span><span class="sxs-lookup"><span data-stu-id="7011b-132">In the PPG From field, enter a number.</span></span>
    * <span data-ttu-id="7011b-133">Dans cet exemple, vous pouvez définir le champ PPG de départ sur 1,95.</span><span class="sxs-lookup"><span data-stu-id="7011b-133">In this example, you can set PPG From field to 1.95.</span></span>  
8. <span data-ttu-id="7011b-134">Entrez un nombre dans le champ PPG de fin.</span><span class="sxs-lookup"><span data-stu-id="7011b-134">In the PPG To field, enter a number.</span></span>
    * <span data-ttu-id="7011b-135">Dans cet exemple, vous pouvez définir le champ PPG de fin sur 2.</span><span class="sxs-lookup"><span data-stu-id="7011b-135">In this example you can set the PPG To field to 2.</span></span>  
9. <span data-ttu-id="7011b-136">Entrez un nombre dans le champ Pourcentage.</span><span class="sxs-lookup"><span data-stu-id="7011b-136">In the Percentage field, enter a number.</span></span>
    * <span data-ttu-id="7011b-137">Dans cet exemple, vous pouvez définir le pourcentage sur 3.</span><span class="sxs-lookup"><span data-stu-id="7011b-137">In this example you can set the percentage to 3.</span></span>  
10. <span data-ttu-id="7011b-138">Dans le champ Devise, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="7011b-138">In the Currency field, click the drop-down button to open the lookup.</span></span>
11. <span data-ttu-id="7011b-139">Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="7011b-139">In the list, find and select the desired record.</span></span>
12. <span data-ttu-id="7011b-140">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="7011b-140">In the list, click the link in the selected row.</span></span>
13. <span data-ttu-id="7011b-141">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="7011b-141">Click Save.</span></span>

