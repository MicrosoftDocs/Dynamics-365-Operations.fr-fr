---
title: Surveiller l'exécution d'une planification générale
description: Le responsable de production veut voir si une exécution de la planification est en cours.
author: ShylaThompson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: DefaultDashboard, ReqCreatePlanWorkspace, ReqTransPlanCard, SysQueryForm, InventItemIdLookupSimple, ReqLog, ReqProcessTaskTrace
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 7c2e158d8cbad1f5d4f377f6a8eb43487b34ffdc
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/15/2019
ms.locfileid: "1565605"
---
# <a name="monitor-a-master-planning-run"></a><span data-ttu-id="e1fe6-103">Surveiller l'exécution d'une planification générale</span><span class="sxs-lookup"><span data-stu-id="e1fe6-103">Monitor a master planning run</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="e1fe6-104">Le responsable de production veut voir si une exécution de la planification est en cours.</span><span class="sxs-lookup"><span data-stu-id="e1fe6-104">The production planner wants to see if a master planning run is in progress.</span></span> <span data-ttu-id="e1fe6-105">Utilisez les données fictives de la société USMF pour réaliser cette procédure.</span><span class="sxs-lookup"><span data-stu-id="e1fe6-105">Use the demo data company USMF to complete this procedure.</span></span>


## <a name="run-master-planning"></a><span data-ttu-id="e1fe6-106">Exécuter la planification générale</span><span class="sxs-lookup"><span data-stu-id="e1fe6-106">Run master planning</span></span>
1. <span data-ttu-id="e1fe6-107">Cliquez sur Planification.</span><span class="sxs-lookup"><span data-stu-id="e1fe6-107">Click Master planning.</span></span>
    * <span data-ttu-id="e1fe6-108">Vous trouverez cela dans le tableau de bord par défaut.</span><span class="sxs-lookup"><span data-stu-id="e1fe6-108">You'll find this on the default dashboard.</span></span>  
2. <span data-ttu-id="e1fe6-109">Dans le champ Régime, saisissez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="e1fe6-109">In the Plan field, enter or select a value.</span></span>
    * <span data-ttu-id="e1fe6-110">Exemple : StaticPlan</span><span class="sxs-lookup"><span data-stu-id="e1fe6-110">Example: StaticPlan</span></span>  
3. <span data-ttu-id="e1fe6-111">Cliquez sur Exécuter.</span><span class="sxs-lookup"><span data-stu-id="e1fe6-111">Click Run.</span></span>
4. <span data-ttu-id="e1fe6-112">Dans le champ Suivre la durée du traitement, sélectionnez Oui.</span><span class="sxs-lookup"><span data-stu-id="e1fe6-112">Select Yes in the Track processing time field.</span></span>
    * <span data-ttu-id="e1fe6-113">Si le champ est déjà sélectionné, ignorez cette étape.</span><span class="sxs-lookup"><span data-stu-id="e1fe6-113">If the field is already selected, skip this step.</span></span>  
5. <span data-ttu-id="e1fe6-114">Entrez un nombre dans le champ Nombre de threads.</span><span class="sxs-lookup"><span data-stu-id="e1fe6-114">In the Number of threads field, enter a number.</span></span>
6. <span data-ttu-id="e1fe6-115">Développez les enregistrements pour inclure la section.</span><span class="sxs-lookup"><span data-stu-id="e1fe6-115">Expand the Records to include section.</span></span>
7. <span data-ttu-id="e1fe6-116">Cliquez sur Filtre.</span><span class="sxs-lookup"><span data-stu-id="e1fe6-116">Click Filter.</span></span>
8. <span data-ttu-id="e1fe6-117">Dans la liste, marquez la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="e1fe6-117">In the list, mark the selected row.</span></span>
    * <span data-ttu-id="e1fe6-118">Marquez la ligne où Champ = Numéro d'article.</span><span class="sxs-lookup"><span data-stu-id="e1fe6-118">Mark the row where Field = Item number.</span></span>  
9. <span data-ttu-id="e1fe6-119">Dans le champ Critères, saisissez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="e1fe6-119">In the Criteria field, enter or select a value.</span></span>
    * <span data-ttu-id="e1fe6-120">Exemple : T0001</span><span class="sxs-lookup"><span data-stu-id="e1fe6-120">Example: T0001</span></span>  
10. <span data-ttu-id="e1fe6-121">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="e1fe6-121">Click OK.</span></span>
11. <span data-ttu-id="e1fe6-122">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="e1fe6-122">Click OK.</span></span>

## <a name="monitor-the-master-planning-run"></a><span data-ttu-id="e1fe6-123">Surveiller l'exécution d'une planification générale</span><span class="sxs-lookup"><span data-stu-id="e1fe6-123">Monitor the master planning run</span></span>
1. <span data-ttu-id="e1fe6-124">Cliquez sur Historique.</span><span class="sxs-lookup"><span data-stu-id="e1fe6-124">Click History.</span></span>
2. <span data-ttu-id="e1fe6-125">Cliquez sur Recherches.</span><span class="sxs-lookup"><span data-stu-id="e1fe6-125">Click Inquiries.</span></span>
3. <span data-ttu-id="e1fe6-126">Cliquez sur Durée de tâche du processus.</span><span class="sxs-lookup"><span data-stu-id="e1fe6-126">Click Process task duration.</span></span>
4. <span data-ttu-id="e1fe6-127">Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="e1fe6-127">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="e1fe6-128">Pour chaque article vous pouvez obtenir une vue d'ensemble de la durée nécessaire pour réaliser chaque étape de planification.</span><span class="sxs-lookup"><span data-stu-id="e1fe6-128">For each item you can get an overview of how long it took to complete each planning step.</span></span>  

