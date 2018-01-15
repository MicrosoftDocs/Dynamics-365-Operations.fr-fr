--- 
title: "Créer une relation d'activité - Successeur"
description: "Le flux des activités dans un flux de production lean est documenté via les relations d'activités."
author: cvocph
manager: AnnBe
ms.date: 11/11/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: conradv
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f827b4787506cfdec8b9a91c4a68f3293190158a
ms.openlocfilehash: 75a76252cc3cb6f3e7516309a7d9a6f2d1934ccd
ms.contentlocale: fr-fr
ms.lasthandoff: 11/06/2017

---
# <a name="create-activity-relation-successor"></a><span data-ttu-id="08179-103">Créer une relation d'activité : Successeur</span><span class="sxs-lookup"><span data-stu-id="08179-103">Create activity relation: Successor</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="08179-104">Le flux des activités dans un flux de production lean est documenté via les relations d'activités.</span><span class="sxs-lookup"><span data-stu-id="08179-104">The flow of activities in a lean production flow is documented through activity relations.</span></span> <span data-ttu-id="08179-105">Cet enregistrement indique comment créer une relation d'activité.</span><span class="sxs-lookup"><span data-stu-id="08179-105">This recording shows how to create an activity relation.</span></span>

<span data-ttu-id="08179-106">Conditions préalables :</span><span class="sxs-lookup"><span data-stu-id="08179-106">Prerequisites:</span></span>

- <span data-ttu-id="08179-107">Un flux de production et une version à l'état de brouillon.</span><span class="sxs-lookup"><span data-stu-id="08179-107">A production flow and version in draft mode.</span></span> 

- <span data-ttu-id="08179-108">Deux activités qui se suivent dans le flux de production sont créées mais ne sont pas liées.</span><span class="sxs-lookup"><span data-stu-id="08179-108">Two activities that follow each other in the production flow are created but not related.</span></span>


## <a name="find-the-production-flow-version"></a><span data-ttu-id="08179-109">Cherchez la version du flux de production.</span><span class="sxs-lookup"><span data-stu-id="08179-109">Find the production flow version</span></span> 
1. <span data-ttu-id="08179-110">Accédez à Contrôle de la production > Paramétrage > Flux de production lean > Flux de production.</span><span class="sxs-lookup"><span data-stu-id="08179-110">Go to Production control > Setup > Lean production flow > Production flows.</span></span>
2. <span data-ttu-id="08179-111">Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="08179-111">In the list, find and select the desired record.</span></span>
3. <span data-ttu-id="08179-112">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="08179-112">In the list, click the link in the selected row.</span></span>
4. <span data-ttu-id="08179-113">Dans la liste, marquez la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="08179-113">In the list, mark the selected row.</span></span>
5. <span data-ttu-id="08179-114">Dans la liste, sélectionnez une version à l'état de brouillon.</span><span class="sxs-lookup"><span data-stu-id="08179-114">In the list, select a draft version.</span></span>
    * <span data-ttu-id="08179-115">Des relations d'activité peuvent être ajoutées aussi bien à la version active qu'à la version de brouillon d'un flux de production.</span><span class="sxs-lookup"><span data-stu-id="08179-115">Activity relations can be added to both draft or active versions of a production flow.</span></span>  

## <a name="open-the-activity-overview"></a><span data-ttu-id="08179-116">Ouvrir la vue d'ensemble des activités</span><span class="sxs-lookup"><span data-stu-id="08179-116">Open the activity overview</span></span>
1. <span data-ttu-id="08179-117">Cliquez sur Activités.</span><span class="sxs-lookup"><span data-stu-id="08179-117">Click Activities.</span></span>
    * <span data-ttu-id="08179-118">Notez que l'écran affiche toutes les activités du flux de production qui sont affectées à la version des flux de production dans lesquels vous travaillez.</span><span class="sxs-lookup"><span data-stu-id="08179-118">Note that the form shows all activities of the production flow that are allocated to the Version of the production flows that you are working in.</span></span>  

## <a name="add-a-successor"></a><span data-ttu-id="08179-119">Ajouter un successeur</span><span class="sxs-lookup"><span data-stu-id="08179-119">Add a Successor</span></span>
1. <span data-ttu-id="08179-120">Cliquez sur Ajouter un successeur.</span><span class="sxs-lookup"><span data-stu-id="08179-120">Click Add successor.</span></span>
2. <span data-ttu-id="08179-121">Dans le champ Activité, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="08179-121">In the Activity field, click the drop-down button to open the lookup.</span></span>
3. <span data-ttu-id="08179-122">Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="08179-122">In the list, find and select the desired record.</span></span>
4. <span data-ttu-id="08179-123">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="08179-123">In the list, click the link in the selected row.</span></span>
5. <span data-ttu-id="08179-124">Cochez la case Contrainte.</span><span class="sxs-lookup"><span data-stu-id="08179-124">Select the Constraint check box.</span></span>
6. <span data-ttu-id="08179-125">Entrez un nombre dans le champ Valeur de la contrainte.</span><span class="sxs-lookup"><span data-stu-id="08179-125">In the Constraint value field, enter a number.</span></span>
    * <span data-ttu-id="08179-126">Le temps de contrainte est la durée à programmer entre la fin prévue du prédécesseur (date et heure d'échéance) et le début prévu du successeur.</span><span class="sxs-lookup"><span data-stu-id="08179-126">The constraint time is the time to be scheduled between the scheduled end of the predecessor (due date and time) and the scheduled start of the successor.</span></span>  
7. <span data-ttu-id="08179-127">Dans le champ Unités, tapez une valeur.</span><span class="sxs-lookup"><span data-stu-id="08179-127">In the Units field, type a value.</span></span>
8. <span data-ttu-id="08179-128">Entrez un nombre dans le champ Ratio de durée de cycle.</span><span class="sxs-lookup"><span data-stu-id="08179-128">In the Cycle time ratio field, enter a number.</span></span>
    * <span data-ttu-id="08179-129">Si les deux activités fonctionnent au même takt, le ratio de durée de cycle doit être 1.</span><span class="sxs-lookup"><span data-stu-id="08179-129">If both activities run at the same takt, the cycle time ratio should be 1.</span></span> <span data-ttu-id="08179-130">Si le prédécesseur s'exécute à la vitesse double de celle du successeur, le ratio doit être 2.</span><span class="sxs-lookup"><span data-stu-id="08179-130">If the predecessor runs at the double speed of the successor, the ratio should be 2.</span></span>   <span data-ttu-id="08179-131">Les ratios de durée de cycle permettent de calculer les durées de cycle individuelles des activités de flux de production.</span><span class="sxs-lookup"><span data-stu-id="08179-131">The cycle time ratios are used to calculate the individual cycle times of the production flow activities.</span></span>  
9. <span data-ttu-id="08179-132">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="08179-132">Click OK.</span></span>
10. <span data-ttu-id="08179-133">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="08179-133">Close the page.</span></span>
11. <span data-ttu-id="08179-134">Cliquez sur l'onglet Volet de grille.</span><span class="sxs-lookup"><span data-stu-id="08179-134">Click the GridPanel tab.</span></span>
12. <span data-ttu-id="08179-135">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="08179-135">Close the page.</span></span>
13. <span data-ttu-id="08179-136">Actualisez la page.</span><span class="sxs-lookup"><span data-stu-id="08179-136">Refresh the page.</span></span>

