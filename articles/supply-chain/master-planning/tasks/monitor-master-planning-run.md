--- 
title: "Surveiller l'exécution d'une planification générale"
description: "Le responsable de production veut voir si une exécution de la planification est en cours."
author: ShylaThompson
manager: AnnBe
ms.date: 8/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: DefaultDashboard, ReqCreatePlanWorkspace, ReqTransPlanCard, SysQueryForm, InventItemIdLookupSimple, ReqLog, ReqProcessTaskTrace
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 32d71167fdad65cb1dec37671999a497759ca484
ms.openlocfilehash: b85366534e12bbeb0dc4d41c898ffe0317d77cc0
ms.contentlocale: fr-fr
ms.lasthandoff: 09/11/2018

---
# <a name="monitor-a-master-planning-run"></a><span data-ttu-id="c1ee8-103">Surveiller l'exécution d'une planification générale</span><span class="sxs-lookup"><span data-stu-id="c1ee8-103">Monitor a master planning run</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="c1ee8-104">Le responsable de production veut voir si une exécution de la planification est en cours.</span><span class="sxs-lookup"><span data-stu-id="c1ee8-104">The production planner wants to see if a master planning run is in progress.</span></span> <span data-ttu-id="c1ee8-105">Utilisez les données fictives de la société USMF pour réaliser cette procédure.</span><span class="sxs-lookup"><span data-stu-id="c1ee8-105">Use the demo data company USMF to complete this procedure.</span></span>


## <a name="run-master-planning"></a><span data-ttu-id="c1ee8-106">Exécuter la planification générale</span><span class="sxs-lookup"><span data-stu-id="c1ee8-106">Run master planning</span></span>
1. <span data-ttu-id="c1ee8-107">Cliquez sur Planification.</span><span class="sxs-lookup"><span data-stu-id="c1ee8-107">Click Master planning.</span></span>
    * <span data-ttu-id="c1ee8-108">Vous trouverez cela dans le tableau de bord par défaut.</span><span class="sxs-lookup"><span data-stu-id="c1ee8-108">You'll find this on the default dashboard.</span></span>  
2. <span data-ttu-id="c1ee8-109">Dans le champ Régime, saisissez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="c1ee8-109">In the Plan field, enter or select a value.</span></span>
    * <span data-ttu-id="c1ee8-110">Exemple : StaticPlan</span><span class="sxs-lookup"><span data-stu-id="c1ee8-110">Example: StaticPlan</span></span>  
3. <span data-ttu-id="c1ee8-111">Cliquez sur Exécuter.</span><span class="sxs-lookup"><span data-stu-id="c1ee8-111">Click Run.</span></span>
4. <span data-ttu-id="c1ee8-112">Dans le champ Suivre la durée du traitement, sélectionnez Oui.</span><span class="sxs-lookup"><span data-stu-id="c1ee8-112">Select Yes in the Track processing time field.</span></span>
    * <span data-ttu-id="c1ee8-113">Si le champ est déjà sélectionné, ignorez cette étape.</span><span class="sxs-lookup"><span data-stu-id="c1ee8-113">If the field is already selected, skip this step.</span></span>  
5. <span data-ttu-id="c1ee8-114">Entrez un nombre dans le champ Nombre de threads.</span><span class="sxs-lookup"><span data-stu-id="c1ee8-114">In the Number of threads field, enter a number.</span></span>
6. <span data-ttu-id="c1ee8-115">Développez les enregistrements pour inclure la section.</span><span class="sxs-lookup"><span data-stu-id="c1ee8-115">Expand the Records to include section.</span></span>
7. <span data-ttu-id="c1ee8-116">Cliquez sur Filtre.</span><span class="sxs-lookup"><span data-stu-id="c1ee8-116">Click Filter.</span></span>
8. <span data-ttu-id="c1ee8-117">Dans la liste, marquez la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="c1ee8-117">In the list, mark the selected row.</span></span>
    * <span data-ttu-id="c1ee8-118">Marquez la ligne où Champ = Numéro d'article.</span><span class="sxs-lookup"><span data-stu-id="c1ee8-118">Mark the row where Field = Item number.</span></span>  
9. <span data-ttu-id="c1ee8-119">Dans le champ Critères, saisissez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="c1ee8-119">In the Criteria field, enter or select a value.</span></span>
    * <span data-ttu-id="c1ee8-120">Exemple : T0001</span><span class="sxs-lookup"><span data-stu-id="c1ee8-120">Example: T0001</span></span>  
10. <span data-ttu-id="c1ee8-121">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="c1ee8-121">Click OK.</span></span>
11. <span data-ttu-id="c1ee8-122">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="c1ee8-122">Click OK.</span></span>

## <a name="monitor-the-master-planning-run"></a><span data-ttu-id="c1ee8-123">Surveiller l'exécution d'une planification générale</span><span class="sxs-lookup"><span data-stu-id="c1ee8-123">Monitor the master planning run</span></span>
1. <span data-ttu-id="c1ee8-124">Cliquez sur Historique.</span><span class="sxs-lookup"><span data-stu-id="c1ee8-124">Click History.</span></span>
2. <span data-ttu-id="c1ee8-125">Cliquez sur Recherches.</span><span class="sxs-lookup"><span data-stu-id="c1ee8-125">Click Inquiries.</span></span>
3. <span data-ttu-id="c1ee8-126">Cliquez sur Durée de tâche du processus.</span><span class="sxs-lookup"><span data-stu-id="c1ee8-126">Click Process task duration.</span></span>
4. <span data-ttu-id="c1ee8-127">Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="c1ee8-127">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="c1ee8-128">Pour chaque article vous pouvez obtenir une vue d'ensemble de la durée nécessaire pour réaliser chaque étape de planification.</span><span class="sxs-lookup"><span data-stu-id="c1ee8-128">For each item you can get an overview of how long it took to complete each planning step.</span></span>  


