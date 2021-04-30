---
title: Créer un plan intersociétés
description: Cette procédure indique comment créer un plan intersociétés.
author: ChristianRytt
ms.date: 08/13/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: ReqIntercompanyPlanningGroupSetup,  ReqCreatePlanWorkspace
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: f8cf4ed879b6b2202d0b0f1f45052f5e21452967
ms.sourcegitcommit: 9b07d536b4bd8addfbdba42d2429c9fedb664635
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/07/2021
ms.locfileid: "5867348"
---
# <a name="create-an-intercompany-plan"></a><span data-ttu-id="e1521-103">Créer un plan intersociétés</span><span class="sxs-lookup"><span data-stu-id="e1521-103">Create an intercompany plan</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="e1521-104">Cette procédure indique comment créer un plan intersociétés.</span><span class="sxs-lookup"><span data-stu-id="e1521-104">This procedure shows how to create an intercompany plan.</span></span> <span data-ttu-id="e1521-105">Les données fictives utilisées pour créer cette procédure correspondent à la société USMF.</span><span class="sxs-lookup"><span data-stu-id="e1521-105">The demo data company used to create this procedure is USMF.</span></span>

## <a name="set-up-an-intercompany-planning-group"></a><span data-ttu-id="e1521-106">Paramétrer un groupe de planification intersociétés</span><span class="sxs-lookup"><span data-stu-id="e1521-106">Set up an intercompany planning group</span></span>

1. <span data-ttu-id="e1521-107">Dans le **Volet de navigation**, allez dans **Modules > Planification > Paramétrage > Groupes de planification intersociétés**.</span><span class="sxs-lookup"><span data-stu-id="e1521-107">In the **Navigation pane**, go to **Modules > Master planning > Setup > Intercompany planning groups**.</span></span>
2. <span data-ttu-id="e1521-108">Utilisez le Filtre rapide pour rechercher les enregistrements.</span><span class="sxs-lookup"><span data-stu-id="e1521-108">Use the Quick Filter to find records.</span></span> <span data-ttu-id="e1521-109">Par exemple, filtrez sur le champ Nom avec une valeur de « 10 ».</span><span class="sxs-lookup"><span data-stu-id="e1521-109">For example, filter on the Name field with a value of '10'.</span></span>
3. <span data-ttu-id="e1521-110">Dans la liste, marquer la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="e1521-110">In the list, mark the selected row.</span></span>
4. <span data-ttu-id="e1521-111">Sélectionnez **Supprimer**.</span><span class="sxs-lookup"><span data-stu-id="e1521-111">Select **Delete**.</span></span> <span data-ttu-id="e1521-112">Cette étape est nécessaire pour raccourcir l’exécution de la planification intersociétés.</span><span class="sxs-lookup"><span data-stu-id="e1521-112">This step is necessary in order to shorten the intercompany planning run.</span></span>   <span data-ttu-id="e1521-113">La planification intersociétés exécute la planification dans toutes les sociétés d’un groupe de planification, en commençant par la séquence de planification la plus faible.</span><span class="sxs-lookup"><span data-stu-id="e1521-113">Intercompany planning will run master planning in all the companies in a planning group, starting from the lowest scheduling sequence.</span></span>  
5. <span data-ttu-id="e1521-114">Cliquez sur **Oui**.</span><span class="sxs-lookup"><span data-stu-id="e1521-114">Select **Yes**.</span></span>
6. <span data-ttu-id="e1521-115">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="e1521-115">Close the page.</span></span>

## <a name="create-an-intercompany-master-plan"></a><span data-ttu-id="e1521-116">Créer une planification générale intersociétés</span><span class="sxs-lookup"><span data-stu-id="e1521-116">Create an intercompany master plan</span></span>

1. <span data-ttu-id="e1521-117">Dans le **Volet de navigation**, allez dans **Modules > Planification > Espaces de travail > Planification**.</span><span class="sxs-lookup"><span data-stu-id="e1521-117">In the **Navigation pane**, go to **Modules > Master planning > Workspaces > Master planning**.</span></span>
2. <span data-ttu-id="e1521-118">Sélectionnez **Planification générale intersociétés**.</span><span class="sxs-lookup"><span data-stu-id="e1521-118">Select **Intercompany master planning**.</span></span>  
3. <span data-ttu-id="e1521-119">Dans le champ **Groupe de planification intersociétés**, sélectionnez le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="e1521-119">In the **Intercompany planning group** field, select the drop-down button to open the lookup.</span></span>
4. <span data-ttu-id="e1521-120">Dans la liste, sélectionnez le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="e1521-120">In the list, select the link in the selected row.</span></span> <span data-ttu-id="e1521-121">Sélectionnez le groupe de planification intersociétés 10.</span><span class="sxs-lookup"><span data-stu-id="e1521-121">Select intercompany planning group 10.</span></span>  
5. <span data-ttu-id="e1521-122">Entrez « 2 » dans le champ **Nombre d’itérations de planification intersociétés**.</span><span class="sxs-lookup"><span data-stu-id="e1521-122">In the **Number of intercompany planning iterations** field, enter '2'.</span></span> <span data-ttu-id="e1521-123">Le groupe de planification intersociétés 10 a deux membres.</span><span class="sxs-lookup"><span data-stu-id="e1521-123">Intercompany planning group 10 has two members.</span></span> <span data-ttu-id="e1521-124">Afin de propager les retards de la société source (USMF) à la société cliente (DEMF), vous devez exécuter deux fois le module intersociétés dans les deux sociétés.</span><span class="sxs-lookup"><span data-stu-id="e1521-124">In order to propagate the delays from the source company (USMF) to the customer company (DEMF), you will need to run intercompany in both companies two times.</span></span> <span data-ttu-id="e1521-125">La première itération propage la demande et identifie les retards dans la société source (USMF).</span><span class="sxs-lookup"><span data-stu-id="e1521-125">The first iteration will propagate the demand and identify the delays in the source company (USMF).</span></span> <span data-ttu-id="e1521-126">La deuxième itération propage les retards d’USMF à DEMF.</span><span class="sxs-lookup"><span data-stu-id="e1521-126">The second iteration will propagate the delays from USMF to DEMF.</span></span>  
6. <span data-ttu-id="e1521-127">Sélectionnez « Régénération » dans le champ **Première itération**.</span><span class="sxs-lookup"><span data-stu-id="e1521-127">In the **First iteration** field, select 'Regeneration'.</span></span>
7. <span data-ttu-id="e1521-128">Sélectionnez « Régénération » dans le champ **Itérations suivantes**.</span><span class="sxs-lookup"><span data-stu-id="e1521-128">In the **Subsequent iterations** field, select 'Regeneration'.</span></span>
8. <span data-ttu-id="e1521-129">Entrez un nombre dans le champ **Nombre de threads**.</span><span class="sxs-lookup"><span data-stu-id="e1521-129">In the **Number of threads** field, enter a number.</span></span> <span data-ttu-id="e1521-130">Représente le nombre de threads parallèles utilisés pour la planification.</span><span class="sxs-lookup"><span data-stu-id="e1521-130">This represents the number of parallel threads used for planning.</span></span>  
9. <span data-ttu-id="e1521-131">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="e1521-131">Select **OK**.</span></span>

## <a name="view-the-result-of-the-plan"></a><span data-ttu-id="e1521-132">Afficher le résultat du plan</span><span class="sxs-lookup"><span data-stu-id="e1521-132">View the result of the plan</span></span>

1. <span data-ttu-id="e1521-133">Dans le champ **Régime**, sélectionnez le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="e1521-133">In the **Plan** field, select the drop-down button to open the lookup.</span></span>
2. <span data-ttu-id="e1521-134">Dans la liste, sélectionnez le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="e1521-134">In the list, select the link in the selected row.</span></span> <span data-ttu-id="e1521-135">Sélectionnez le lien de StaticPlan.</span><span class="sxs-lookup"><span data-stu-id="e1521-135">Select the link for StaticPlan.</span></span> <span data-ttu-id="e1521-136">Vous devez être dans la société USMF.</span><span class="sxs-lookup"><span data-stu-id="e1521-136">You need to be in company USMF.</span></span>  
3. <span data-ttu-id="e1521-137">Sélectionnez **Ordres prévisionnels**.</span><span class="sxs-lookup"><span data-stu-id="e1521-137">Select **Planned orders**.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]