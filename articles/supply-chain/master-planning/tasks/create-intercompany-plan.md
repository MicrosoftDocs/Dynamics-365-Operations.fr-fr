--- 
title: "Créer un plan intersociétés"
description: "Cette procédure indique comment créer un plan intersociétés."
author: YuyuScheller
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
ms.author: yuyus
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: b5ed1b47e3e0142a18761f5a47ca12a388305308
ms.contentlocale: fr-fr
ms.lasthandoff: 04/13/2018

---
# <a name="create-an-intercompany-plan"></a><span data-ttu-id="13a86-103">Créer un plan intersociétés</span><span class="sxs-lookup"><span data-stu-id="13a86-103">Create an intercompany plan</span></span>

[!INCLUDE [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="13a86-104">Cette procédure indique comment créer un plan intersociétés.</span><span class="sxs-lookup"><span data-stu-id="13a86-104">This procedure shows how to create an intercompany plan.</span></span> <span data-ttu-id="13a86-105">Les données fictives utilisées pour créer cette procédure correspondent à la société USMF.</span><span class="sxs-lookup"><span data-stu-id="13a86-105">The demo data company used to create this procedure is USMF.</span></span>


## <a name="set-up-an-intercompany-planning-group"></a><span data-ttu-id="13a86-106">Paramétrer un groupe de planification intersociétés</span><span class="sxs-lookup"><span data-stu-id="13a86-106">Set up an intercompany planning group</span></span> 
1. <span data-ttu-id="13a86-107">Accédez à Groupes de planification intersociétés.</span><span class="sxs-lookup"><span data-stu-id="13a86-107">Go to Intercompany planning groups.</span></span>
    * <span data-ttu-id="13a86-108">Planification > Configuration > Groupes de planification intersociétés</span><span class="sxs-lookup"><span data-stu-id="13a86-108">Master planning > Setup > Intercompany planning groups</span></span>  
2. <span data-ttu-id="13a86-109">Utilisez le Filtre rapide pour rechercher les enregistrements.</span><span class="sxs-lookup"><span data-stu-id="13a86-109">Use the Quick Filter to find records.</span></span> <span data-ttu-id="13a86-110">Par exemple, filtrez sur le champ Nom avec une valeur de « 10 ».</span><span class="sxs-lookup"><span data-stu-id="13a86-110">For example, filter on the Name field with a value of '10'.</span></span>
3. <span data-ttu-id="13a86-111">Dans la liste, marquez la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="13a86-111">In the list, mark the selected row.</span></span>
4. <span data-ttu-id="13a86-112">Cliquez sur Supprimer.</span><span class="sxs-lookup"><span data-stu-id="13a86-112">Click Delete.</span></span>
    * <span data-ttu-id="13a86-113">Cette étape est nécessaire pour raccourcir l'exécution de la planification intersociétés.</span><span class="sxs-lookup"><span data-stu-id="13a86-113">This step is necessary in order to shorten the intercompany planning run.</span></span>   <span data-ttu-id="13a86-114">La planification intersociétés exécute la planification dans toutes les sociétés d'un groupe de planification, en commençant par la séquence de planification la plus faible.</span><span class="sxs-lookup"><span data-stu-id="13a86-114">Intercompany planning will run master planning in all the companies in a planning group, starting from the lowest scheduling sequence.</span></span>  
5. <span data-ttu-id="13a86-115">Cliquez sur Oui.</span><span class="sxs-lookup"><span data-stu-id="13a86-115">Click Yes.</span></span>
6. <span data-ttu-id="13a86-116">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="13a86-116">Close the page.</span></span>

## <a name="create-an-intercompany-plan"></a><span data-ttu-id="13a86-117">Créer un plan intersociétés</span><span class="sxs-lookup"><span data-stu-id="13a86-117">Create an intercompany plan</span></span>
1. <span data-ttu-id="13a86-118">Cliquez sur Planification intersociétés.</span><span class="sxs-lookup"><span data-stu-id="13a86-118">Click Intercompany master planning.</span></span>
    * <span data-ttu-id="13a86-119">Cela figure dans l'espace de travail Planification.</span><span class="sxs-lookup"><span data-stu-id="13a86-119">This is on the Master planning workspace.</span></span>  
2. <span data-ttu-id="13a86-120">Dans le champ Groupe de planification intersociétés, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="13a86-120">In the Intercompany planning group field, click the drop-down button to open the lookup.</span></span>
3. <span data-ttu-id="13a86-121">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="13a86-121">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="13a86-122">Sélectionnez le groupe de planification intersociétés 10.</span><span class="sxs-lookup"><span data-stu-id="13a86-122">Select intercompany planning group 10.</span></span>  
4. <span data-ttu-id="13a86-123">Dans le champ Nombre d'itérations de planification intersociétés, entrez « 2 ».</span><span class="sxs-lookup"><span data-stu-id="13a86-123">In the Number of intercompany planning iterations field, enter '2'.</span></span>
    * <span data-ttu-id="13a86-124">Le groupe de planification intersociétés 10 a deux membres.</span><span class="sxs-lookup"><span data-stu-id="13a86-124">Intercompany planning group 10 has two members.</span></span> <span data-ttu-id="13a86-125">Afin de propager les retards de la société source (USMF) à la société cliente (DEMF), vous devez exécuter deux fois le module intersociétés dans les deux sociétés.</span><span class="sxs-lookup"><span data-stu-id="13a86-125">In order to propagate the delays from the source company (USMF) to the customer company (DEMF), you will need to run intercompany in both companies two times.</span></span> <span data-ttu-id="13a86-126">La première itération propage la demande et identifie les retards dans la société source (USMF).</span><span class="sxs-lookup"><span data-stu-id="13a86-126">The first iteration will propagate the demand and identify the delays in the source company (USMF).</span></span> <span data-ttu-id="13a86-127">La deuxième itération propage les retards d'USMF à DEMF.</span><span class="sxs-lookup"><span data-stu-id="13a86-127">The second iteration will propagate the delays from USMF to DEMF.</span></span>  
5. <span data-ttu-id="13a86-128">Dans le champ Première itération, sélectionnez une option.</span><span class="sxs-lookup"><span data-stu-id="13a86-128">In the First iteration field, select an option.</span></span>
6. <span data-ttu-id="13a86-129">Dans le champ Première itération, sélectionnez « Régénération ».</span><span class="sxs-lookup"><span data-stu-id="13a86-129">In the First iteration field, select 'Regeneration'.</span></span>
7. <span data-ttu-id="13a86-130">Dans le champ Itérations suivantes, sélectionnez « Régénération ».</span><span class="sxs-lookup"><span data-stu-id="13a86-130">In the Subsequent iterations field, select 'Regeneration'.</span></span>
8. <span data-ttu-id="13a86-131">Entrez un nombre dans le champ Nombre de threads.</span><span class="sxs-lookup"><span data-stu-id="13a86-131">In the Number of threads field, enter a number.</span></span>
    * <span data-ttu-id="13a86-132">Représente le nombre de threads parallèles utilisés pour la planification.</span><span class="sxs-lookup"><span data-stu-id="13a86-132">This represents the number of parallel threads used for planning.</span></span>  
9. <span data-ttu-id="13a86-133">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="13a86-133">Click OK.</span></span>

## <a name="view-the-result-of-the-plan"></a><span data-ttu-id="13a86-134">Afficher le résultat du plan</span><span class="sxs-lookup"><span data-stu-id="13a86-134">View the result of the plan</span></span>
1. <span data-ttu-id="13a86-135">Dans le champ Régime, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="13a86-135">In the Plan field, click the drop-down button to open the lookup.</span></span>
2. <span data-ttu-id="13a86-136">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="13a86-136">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="13a86-137">Cliquez sur le lien de StaticPlan.</span><span class="sxs-lookup"><span data-stu-id="13a86-137">Click the link for StaticPlan.</span></span> <span data-ttu-id="13a86-138">Vous devez être dans la société USMF.</span><span class="sxs-lookup"><span data-stu-id="13a86-138">You need to be in company USMF.</span></span>  
3. <span data-ttu-id="13a86-139">Cliquez sur Ordres prévisionnels.</span><span class="sxs-lookup"><span data-stu-id="13a86-139">Click Planned orders.</span></span>


