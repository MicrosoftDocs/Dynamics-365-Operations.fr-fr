---
title: Générer un plan avec contrainte
description: Cette rubrique indique comment créer un plan qui prend en compte des contraintes en termes de matière et de capacité.
author: ShylaThompson
manager: tfehr
ms.date: 08/02/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: DefaultDashboard, ReqCreatePlanWorkspace, ReqTransPlanCard, ReqPlanSched
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: d4af946a8dd4e5311bcb90386c88d5e7f205c4eb
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4999854"
---
# <a name="generate-a-constrained-plan"></a><span data-ttu-id="72e10-103">Générer un plan avec contrainte</span><span class="sxs-lookup"><span data-stu-id="72e10-103">Generate a constrained plan</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="72e10-104">Cette rubrique indique comment créer un plan qui prend en compte des contraintes en termes de matière et de capacité.</span><span class="sxs-lookup"><span data-stu-id="72e10-104">This topic explains how to create a plan that takes into account both material and capacity constraints.</span></span> <span data-ttu-id="72e10-105">Le plan vérifie que la fabrication ne démarre pas avant que les matières soient disponibles et que des ressources ne soient pas surréservées.</span><span class="sxs-lookup"><span data-stu-id="72e10-105">The plan ensures that manufacturing doesn't start before materials are available and resources are not overbooked.</span></span> 

<span data-ttu-id="72e10-106">Les données fictives utilisées pour créer cette procédure correspondent à la société USMF.</span><span class="sxs-lookup"><span data-stu-id="72e10-106">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="72e10-107">Cette procédure est destinée au gestionnaire de production.</span><span class="sxs-lookup"><span data-stu-id="72e10-107">This procedure is intended for the production planner.</span></span>


## <a name="set-up-a-constrained-plan"></a><span data-ttu-id="72e10-108">Paramétrer un plan avec contrainte</span><span class="sxs-lookup"><span data-stu-id="72e10-108">Set up a constrained plan</span></span>
1. <span data-ttu-id="72e10-109">Dans la page d'accueil, sélectionnez l'espace de travail **Planification**.</span><span class="sxs-lookup"><span data-stu-id="72e10-109">In the home page, select the **Master planning** workspace.</span></span>
2. <span data-ttu-id="72e10-110">Sélectionnez **Plans généraux** dans la liste des liens dans la partie droite de l'espace de travail.</span><span class="sxs-lookup"><span data-stu-id="72e10-110">Select **Master plans** in the list of links on the far right side of the workspace.</span></span>
3. <span data-ttu-id="72e10-111">Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="72e10-111">In the list, find and select the desired record.</span></span> <span data-ttu-id="72e10-112">Exemple : **StaticPlan**</span><span class="sxs-lookup"><span data-stu-id="72e10-112">Example: **StaticPlan**</span></span>  
4. <span data-ttu-id="72e10-113">Sélectionnez **Oui** dans le champ **Capacité finie**.</span><span class="sxs-lookup"><span data-stu-id="72e10-113">Select **Yes** in the **Finite capacity** field.</span></span>
5. <span data-ttu-id="72e10-114">Entrez `30` dans le champ **Plage de gestion de la capacité finie**.</span><span class="sxs-lookup"><span data-stu-id="72e10-114">In the **Finite capacity time fence** field, enter `30`.</span></span>
6. <span data-ttu-id="72e10-115">Développez la section **Plages de gestion en jours**.</span><span class="sxs-lookup"><span data-stu-id="72e10-115">Expand the **Time fences in days** section.</span></span>
7. <span data-ttu-id="72e10-116">Sélectionnez **Oui** dans le champ **Capacité**.</span><span class="sxs-lookup"><span data-stu-id="72e10-116">Select **Yes** in the **Capacity** field.</span></span>
8. <span data-ttu-id="72e10-117">Entrez un nombre dans le champ **Plage de gestion de planification de capacité (jours)**.</span><span class="sxs-lookup"><span data-stu-id="72e10-117">In the **Capacity scheduling time fence (days)** field, enter a number.</span></span> <span data-ttu-id="72e10-118">Exemple : `60`</span><span class="sxs-lookup"><span data-stu-id="72e10-118">Example: `60`</span></span>  
9. <span data-ttu-id="72e10-119">Sélectionnez **Oui** dans le champ **Retards calculés**.</span><span class="sxs-lookup"><span data-stu-id="72e10-119">Select **Yes** in the **Calculated delays** field.</span></span>
10. <span data-ttu-id="72e10-120">Entrez un nombre dans le champ **Calculer la plage de gestion des retards (jours)**.</span><span class="sxs-lookup"><span data-stu-id="72e10-120">In the **Calculate delays time fence (days)** field, enter a number.</span></span> <span data-ttu-id="72e10-121">Exemple : `60`</span><span class="sxs-lookup"><span data-stu-id="72e10-121">Example: `60`</span></span> 
11. <span data-ttu-id="72e10-122">Développez la section **Retards calculés**.</span><span class="sxs-lookup"><span data-stu-id="72e10-122">Expand the **Calculated delays** section.</span></span>
12. <span data-ttu-id="72e10-123">Sélectionnez **Oui** dans tous les champs **Ajouter le retard calculé à la date de besoin**.</span><span class="sxs-lookup"><span data-stu-id="72e10-123">Select **Yes** in all **Add the calculated delay to the requirement date** fields.</span></span>
13. <span data-ttu-id="72e10-124">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="72e10-124">Close the page.</span></span>

## <a name="create-a-constrained-plan"></a><span data-ttu-id="72e10-125">Créer un plan avec contrainte</span><span class="sxs-lookup"><span data-stu-id="72e10-125">Create a constrained plan</span></span>
1. <span data-ttu-id="72e10-126">Sélectionnez **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="72e10-126">Select **Run**.</span></span>
2. <span data-ttu-id="72e10-127">Dans le champ **Plan général**, entrez ou sélectionnez le plan pour lequel vous avez paramétré les contraintes.</span><span class="sxs-lookup"><span data-stu-id="72e10-127">In the **Master plan** field, enter or select the plan for which you have set up constraints.</span></span>  
3. <span data-ttu-id="72e10-128">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="72e10-128">Select **OK**.</span></span>
4. <span data-ttu-id="72e10-129">Sélectionnez **Ordres prévisionnels**.</span><span class="sxs-lookup"><span data-stu-id="72e10-129">Select **Planned orders**.</span></span>

