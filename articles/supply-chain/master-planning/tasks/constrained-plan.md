---
title: Générer un plan avec contrainte
description: Cette procédure indique comment créer un plan qui prend en compte des contraintes en termes de matière et de capacité.
author: ShylaThompson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: DefaultDashboard, ReqCreatePlanWorkspace, ReqTransPlanCard, ReqPlanSched
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 72cddd58b7068e08cddf24df83da8da2f7af7168
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/01/2019
ms.locfileid: "1845289"
---
# <a name="generate-a-constrained-plan"></a><span data-ttu-id="7b859-103">Générer un plan avec contrainte</span><span class="sxs-lookup"><span data-stu-id="7b859-103">Generate a constrained plan</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="7b859-104">Cette procédure indique comment créer un plan qui prend en compte des contraintes en termes de matière et de capacité.</span><span class="sxs-lookup"><span data-stu-id="7b859-104">This procedure shows how to create a plan that takes into account both material and capacity constraints.</span></span> <span data-ttu-id="7b859-105">Le plan vérifie que la fabrication ne démarre pas avant que les matières soient disponibles et que des ressources ne soient pas surréservées.</span><span class="sxs-lookup"><span data-stu-id="7b859-105">The plan ensures that manufacturing doesn't start before materials are available and resources are not overbooked.</span></span> 

<span data-ttu-id="7b859-106">Les données fictives utilisées pour créer cette procédure correspondent à la société USMF.</span><span class="sxs-lookup"><span data-stu-id="7b859-106">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="7b859-107">Cette procédure est destinée au gestionnaire de production.</span><span class="sxs-lookup"><span data-stu-id="7b859-107">This procedure is intended for the production planner.</span></span>


## <a name="set-up-a-constrained-plan"></a><span data-ttu-id="7b859-108">Paramétrer un plan avec contrainte</span><span class="sxs-lookup"><span data-stu-id="7b859-108">Set up a constrained plan</span></span>
1. <span data-ttu-id="7b859-109">Cliquez sur Planification.</span><span class="sxs-lookup"><span data-stu-id="7b859-109">Click Master planning.</span></span>
2. <span data-ttu-id="7b859-110">Cliquez sur Plans généraux.</span><span class="sxs-lookup"><span data-stu-id="7b859-110">Click Master plans.</span></span>
3. <span data-ttu-id="7b859-111">Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="7b859-111">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="7b859-112">Exemple : StaticPlan</span><span class="sxs-lookup"><span data-stu-id="7b859-112">Example: StaticPlan</span></span>  
4. <span data-ttu-id="7b859-113">Sélectionnez Oui dans le champ Capacité finie.</span><span class="sxs-lookup"><span data-stu-id="7b859-113">Select Yes in the Finite capacity field.</span></span>
5. <span data-ttu-id="7b859-114">Entrez 30 dans le champ Plage de gestion de la capacité finie.</span><span class="sxs-lookup"><span data-stu-id="7b859-114">In the Finite capacity time fence field, enter '30'.</span></span>
6. <span data-ttu-id="7b859-115">Développez les plages de gestion dans la section des jours.</span><span class="sxs-lookup"><span data-stu-id="7b859-115">Expand the Time fences in days section.</span></span>
7. <span data-ttu-id="7b859-116">Sélectionnez Oui dans le champ Capacité.</span><span class="sxs-lookup"><span data-stu-id="7b859-116">Select Yes in the Capacity field.</span></span>
8. <span data-ttu-id="7b859-117">Entrez un nombre dans le champ Plage de gestion de planification de capacité (jours).</span><span class="sxs-lookup"><span data-stu-id="7b859-117">In the Capacity scheduling time fence (days) field, enter a number.</span></span>
    * <span data-ttu-id="7b859-118">Exemple : 60</span><span class="sxs-lookup"><span data-stu-id="7b859-118">Example: 60</span></span>  
9. <span data-ttu-id="7b859-119">Sélectionnez Oui dans le champ Retards calculés.</span><span class="sxs-lookup"><span data-stu-id="7b859-119">Select Yes in the Calculated delays field.</span></span>
10. <span data-ttu-id="7b859-120">Entrez un nombre dans le champ Calculer la plage de gestion des retards (jours).</span><span class="sxs-lookup"><span data-stu-id="7b859-120">In the Calculate delays time fence (days) field, enter a number.</span></span>
    * <span data-ttu-id="7b859-121">Exemple : 60</span><span class="sxs-lookup"><span data-stu-id="7b859-121">Example: 60</span></span>  
11. <span data-ttu-id="7b859-122">Développez la section Retards calculés.</span><span class="sxs-lookup"><span data-stu-id="7b859-122">Expand the Calculated delays section.</span></span>
12. <span data-ttu-id="7b859-123">Sélectionnez Oui dans le champ Ajouter le retard calculé à la date de besoin.</span><span class="sxs-lookup"><span data-stu-id="7b859-123">Select Yes in the Add the calculated delay to the requirement date field.</span></span>
13. <span data-ttu-id="7b859-124">Sélectionnez Oui dans le champ Ajouter le retard calculé à la date de besoin.</span><span class="sxs-lookup"><span data-stu-id="7b859-124">Select Yes in the Add the calculated delay to the requirement date field.</span></span>
14. <span data-ttu-id="7b859-125">Sélectionnez Oui dans le champ Ajouter le retard calculé à la date de besoin.</span><span class="sxs-lookup"><span data-stu-id="7b859-125">Select Yes in the Add the calculated delay to the requirement date field.</span></span>
15. <span data-ttu-id="7b859-126">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="7b859-126">Close the page.</span></span>

## <a name="create-a-constrained-plan"></a><span data-ttu-id="7b859-127">Créer un plan avec contrainte</span><span class="sxs-lookup"><span data-stu-id="7b859-127">Create a constrained plan</span></span>
1. <span data-ttu-id="7b859-128">Cliquez sur Exécuter.</span><span class="sxs-lookup"><span data-stu-id="7b859-128">Click Run.</span></span>
2. <span data-ttu-id="7b859-129">Saisissez ou sélectionnez une valeur dans le champ Plan général.</span><span class="sxs-lookup"><span data-stu-id="7b859-129">In the Master plan field, enter or select a value.</span></span>
    * <span data-ttu-id="7b859-130">Sélectionnez le plan pour lequel vous avez défini des contraintes.</span><span class="sxs-lookup"><span data-stu-id="7b859-130">Select the plan for which you have set up constraints.</span></span>  
3. <span data-ttu-id="7b859-131">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="7b859-131">Click OK.</span></span>
    * <span data-ttu-id="7b859-132">Cette opération peut prendre du temps.</span><span class="sxs-lookup"><span data-stu-id="7b859-132">This may take a while.</span></span>  
4. <span data-ttu-id="7b859-133">Cliquez sur Ordres prévisionnels.</span><span class="sxs-lookup"><span data-stu-id="7b859-133">Click Planned orders.</span></span>

