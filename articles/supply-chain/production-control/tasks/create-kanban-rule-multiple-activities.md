---
title: Créer une règle de kanban pour des activités multiples
description: Cette procédure montre comment créer une règle de kanban qui inclut des activités multiples à partir d'un flux de production.
author: ChristianRytt
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: KanbanRules, LeanProductionFlowActivityLookup, KanbanFlowSelection, InventItemIdLookupSimple, KanbanCreateScheduled, Kanban
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 68cac0f581e786cdb3801e03fb60db7bc05ffb2f
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/02/2020
ms.locfileid: "3212215"
---
# <a name="create-a-kanban-rule-for-multiple-activities"></a><span data-ttu-id="0d70b-103">Créer une règle de kanban pour des activités multiples</span><span class="sxs-lookup"><span data-stu-id="0d70b-103">Create a kanban rule for multiple activities</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="0d70b-104">Cette procédure montre comment créer une règle de kanban qui inclut des activités multiples à partir d'un flux de production.</span><span class="sxs-lookup"><span data-stu-id="0d70b-104">This procedure shows how to create a kanban rule that includes multiple activities from a production flow.</span></span> <span data-ttu-id="0d70b-105">Les données fictives utilisées pour créer cette tâche correspondent à la société USMF.</span><span class="sxs-lookup"><span data-stu-id="0d70b-105">The demo data company used to create this task is USMF.</span></span> <span data-ttu-id="0d70b-106">Cette tâche est destinée à l'ingénieur processus ou au responsable de la chaîne de valeur, car ils préparent la production d'un produit nouveau ou modifié dans un environnement lean.</span><span class="sxs-lookup"><span data-stu-id="0d70b-106">This task is intended for the process engineer or the value stream manager, as they prepare production of a new or modified product in a lean environment.</span></span>


## <a name="create-a-new-kanban-rule"></a><span data-ttu-id="0d70b-107">Créer une règle de kanban</span><span class="sxs-lookup"><span data-stu-id="0d70b-107">Create a new kanban rule</span></span>
1. <span data-ttu-id="0d70b-108">Accédez à Gestion des informations sur les produits > Lean manufacturing > Règles de kanban.</span><span class="sxs-lookup"><span data-stu-id="0d70b-108">Go to Product information management > Lean manufacturing > Kanban rules.</span></span>
2. <span data-ttu-id="0d70b-109">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="0d70b-109">Click New.</span></span>
3. <span data-ttu-id="0d70b-110">Dans le champ Stratégie de réapprovisionnement, sélectionnez « Planifié ».</span><span class="sxs-lookup"><span data-stu-id="0d70b-110">In the Replenishment strategy field, select 'Scheduled'.</span></span>
4. <span data-ttu-id="0d70b-111">Entrez ou sélectionnez une valeur dans le champ Première activité de plan.</span><span class="sxs-lookup"><span data-stu-id="0d70b-111">In the First plan activity field, enter or select a value.</span></span>
    * <span data-ttu-id="0d70b-112">Sélectionnez SpeakerAssemblyAndPolish.</span><span class="sxs-lookup"><span data-stu-id="0d70b-112">Select SpeakerAssemblyAndPolish.</span></span>  
5. <span data-ttu-id="0d70b-113">Choisissez la case à cocher Plusieurs activités.</span><span class="sxs-lookup"><span data-stu-id="0d70b-113">Select the Multiple activities check box.</span></span>
    * <span data-ttu-id="0d70b-114">Le but est d'inclure plus d'une activité dans la règle de kanban.</span><span class="sxs-lookup"><span data-stu-id="0d70b-114">The purpose is to include more than one activity in the kanban rule.</span></span> <span data-ttu-id="0d70b-115">Vous devez choisir un chemin dans le flux de production quand vous choisissez la dernière activité du plan.</span><span class="sxs-lookup"><span data-stu-id="0d70b-115">You choose a path in the production flow when you select the last plan activity.</span></span>  
6. <span data-ttu-id="0d70b-116">Entrez ou sélectionnez une valeur dans le champ Dernière activité de plan.</span><span class="sxs-lookup"><span data-stu-id="0d70b-116">In the Last plan activity field, enter or select a value.</span></span>
    * <span data-ttu-id="0d70b-117">Sélectionnez « SpeakerTestAndPackaging ».</span><span class="sxs-lookup"><span data-stu-id="0d70b-117">Select SpeakerTestAndPackaging.</span></span> <span data-ttu-id="0d70b-118">Une page s'ouvre automatiquement quand vous avez sélectionné la valeur.</span><span class="sxs-lookup"><span data-stu-id="0d70b-118">After you select the value, a page automatically opens.</span></span> <span data-ttu-id="0d70b-119">Sélectionnez le flux kanban SpeakerAssemblyAndPolish > SpeakerTestAndPackaging.</span><span class="sxs-lookup"><span data-stu-id="0d70b-119">Select the kanban flow SpeakerAssemblyAndPolish > SpeakerTestAndPackaging.</span></span> <span data-ttu-id="0d70b-120">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="0d70b-120">Click OK.</span></span>  
7. <span data-ttu-id="0d70b-121">Développez la section Détails.</span><span class="sxs-lookup"><span data-stu-id="0d70b-121">Expand the Details section.</span></span>
8. <span data-ttu-id="0d70b-122">Dans le champ Produit, saisissez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="0d70b-122">In the Product field, enter or select a value.</span></span>
    * <span data-ttu-id="0d70b-123">Sélectionner l'article L0006.</span><span class="sxs-lookup"><span data-stu-id="0d70b-123">Select Item L0006.</span></span>  

## <a name="create-kanban-and-view-jobs"></a><span data-ttu-id="0d70b-124">Créer un kanban et afficher les tâches</span><span class="sxs-lookup"><span data-stu-id="0d70b-124">Create kanban and view jobs</span></span>
1. <span data-ttu-id="0d70b-125">Développer la section Kanbans.</span><span class="sxs-lookup"><span data-stu-id="0d70b-125">Expand the Kanbans section.</span></span>
2. <span data-ttu-id="0d70b-126">Cliquez sur Ajouter.</span><span class="sxs-lookup"><span data-stu-id="0d70b-126">Click Add.</span></span>
3. <span data-ttu-id="0d70b-127">Entrez 1 dans le champ Nombre de nouveaux kanbans.</span><span class="sxs-lookup"><span data-stu-id="0d70b-127">In the Number of new kanbans field, enter '1'.</span></span>
    * <span data-ttu-id="0d70b-128">Cette opération crée un kanban.</span><span class="sxs-lookup"><span data-stu-id="0d70b-128">This will create one kanban.</span></span>  
4. <span data-ttu-id="0d70b-129">Définissez la quantité de produit sur 3.</span><span class="sxs-lookup"><span data-stu-id="0d70b-129">Set Product quantity to '3'.</span></span>
    * <span data-ttu-id="0d70b-130">Kanban traitera 3 produits.</span><span class="sxs-lookup"><span data-stu-id="0d70b-130">Kanban will process 3 products.</span></span>  
5. <span data-ttu-id="0d70b-131">Entrez une date et une heure dans le champ Date/heure d'échéance.</span><span class="sxs-lookup"><span data-stu-id="0d70b-131">In the Due date/time field, enter a date and time.</span></span>
    * <span data-ttu-id="0d70b-132">Vous pouvez entrer Aujourd'hui.</span><span class="sxs-lookup"><span data-stu-id="0d70b-132">You can enter Today.</span></span>  
6. <span data-ttu-id="0d70b-133">Cliquez sur Créer.</span><span class="sxs-lookup"><span data-stu-id="0d70b-133">Click Create.</span></span>
7. <span data-ttu-id="0d70b-134">Cliquez sur Détails.</span><span class="sxs-lookup"><span data-stu-id="0d70b-134">Click Details.</span></span>
    * <span data-ttu-id="0d70b-135">Notez que le kanban a deux opérations de traitement à partir d'un flux de production.</span><span class="sxs-lookup"><span data-stu-id="0d70b-135">Notice that the kanban has two process jobs from the production flow.</span></span> <span data-ttu-id="0d70b-136">La première est SpeakerAssemblyAndPolish, et la deuxième est SpeakerTestAndPackaging.</span><span class="sxs-lookup"><span data-stu-id="0d70b-136">The first one is SpeakerAssemblyAndPolish, and the second one is SpeakerTestAndPackaging.</span></span>  
    * <span data-ttu-id="0d70b-137">Il s'agit de la dernière étape.</span><span class="sxs-lookup"><span data-stu-id="0d70b-137">This is the last step!</span></span>  

