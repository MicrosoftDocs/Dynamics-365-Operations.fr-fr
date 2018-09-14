--- 
title: "Créer une règle de kanban de quantité fixe pour la fabrication"
description: "Cette procédure consiste à réaliser le paramétrage nécessaire pour créer une règle de kanban de fabrication fixe pour déclencher des activités de transformation, au niveau de la cellule de travail, dans un environnement lean."
author: ChristianRytt
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: KanbanRules, LeanProductionFlowActivityLookup, InventItemIdLookupSimple, UnitOfMeasureLookup, KanbanCreate
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 0312b8cfadd45f8e59225e9daba78b9e216cff51
ms.openlocfilehash: 9e0f58d1e265fb001474eb572b9bc325cf08790c
ms.contentlocale: fr-fr
ms.lasthandoff: 09/14/2018

---
# <a name="create-a-fixed-quantity-kanban-rule-for-manufacturing"></a><span data-ttu-id="64269-103">Créer une règle de kanban de quantité fixe pour la fabrication</span><span class="sxs-lookup"><span data-stu-id="64269-103">Create a fixed quantity kanban rule for manufacturing</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="64269-104">Cette procédure consiste à réaliser le paramétrage nécessaire pour créer une règle de kanban de fabrication fixe pour déclencher des activités de transformation, au niveau de la cellule de travail, dans un environnement lean.</span><span class="sxs-lookup"><span data-stu-id="64269-104">This procedure focuses on the setup needed to create a fixed manufacturing kanban rule for triggering transforming activities, at a work cell, in a lean environment.</span></span> <span data-ttu-id="64269-105">Les données fictives utilisées pour créer cette procédure correspondent à la société USMF.</span><span class="sxs-lookup"><span data-stu-id="64269-105">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="64269-106">Cette procédure est destinée à l'ingénieur processus ou au responsable de la chaîne de valeur, car ils préparent la production d'un produit nouveau ou modifié.</span><span class="sxs-lookup"><span data-stu-id="64269-106">This procedure is intended for the Process Engineer or the Value Stream Manager, as they prepare production of a new or modified product.</span></span>


## <a name="create-new-kanban-rule"></a><span data-ttu-id="64269-107">Créer une règle de kanban</span><span class="sxs-lookup"><span data-stu-id="64269-107">Create new kanban rule</span></span>
1. <span data-ttu-id="64269-108">Accédez aux règles de kanban.</span><span class="sxs-lookup"><span data-stu-id="64269-108">Go to Kanban rules.</span></span>
2. <span data-ttu-id="64269-109">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="64269-109">Click New.</span></span>
    * <span data-ttu-id="64269-110">Notez que le type par défaut est Fabrication et que la stratégie de réapprovisionnement est fixée.</span><span class="sxs-lookup"><span data-stu-id="64269-110">Notice that the default Type is Manufacturing and Replenishment strategy is Fixed.</span></span> <span data-ttu-id="64269-111">Il est inutile de modifier ces paramètres.</span><span class="sxs-lookup"><span data-stu-id="64269-111">You do not have to change these parameters.</span></span>  
3. <span data-ttu-id="64269-112">Entrez ou sélectionnez une valeur dans le champ Première activité de plan.</span><span class="sxs-lookup"><span data-stu-id="64269-112">In the First plan activity field, enter or select a value.</span></span>
    * <span data-ttu-id="64269-113">Il s'agit de l'activité qui sera exécutée pour les kanbans créés selon cette règle de kanban.</span><span class="sxs-lookup"><span data-stu-id="64269-113">This is the activity that will be performed for kanbans created based on this kanban rule.</span></span>  <span data-ttu-id="64269-114">Sélectionnez « SpeakerTestAndPackaging ».</span><span class="sxs-lookup"><span data-stu-id="64269-114">Select 'SpeakerTestAndPackaging'.</span></span>  
4. <span data-ttu-id="64269-115">Développez la section Détails.</span><span class="sxs-lookup"><span data-stu-id="64269-115">Expand the Details section.</span></span>
5. <span data-ttu-id="64269-116">Dans le champ Produit, saisissez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="64269-116">In the Product field, enter or select a value.</span></span>
    * <span data-ttu-id="64269-117">Sélectionnez L0050.</span><span class="sxs-lookup"><span data-stu-id="64269-117">Select L0050.</span></span>  
6. <span data-ttu-id="64269-118">Dans le champ Unité de mesure, saisissez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="64269-118">In the Unit of measure field, enter or select a value.</span></span>
    * <span data-ttu-id="64269-119">Sélectionnez Minutes.</span><span class="sxs-lookup"><span data-stu-id="64269-119">Select minutes.</span></span>  
7. <span data-ttu-id="64269-120">Entrez un nombre dans le champ Délai.</span><span class="sxs-lookup"><span data-stu-id="64269-120">In the Lead time field, enter a number.</span></span>
    * <span data-ttu-id="64269-121">Entrez 5.</span><span class="sxs-lookup"><span data-stu-id="64269-121">Enter 5.</span></span>  

## <a name="set-quantities"></a><span data-ttu-id="64269-122">Définir les quantités</span><span class="sxs-lookup"><span data-stu-id="64269-122">Set quantities</span></span>
1. <span data-ttu-id="64269-123">Développez la section Quantités.</span><span class="sxs-lookup"><span data-stu-id="64269-123">Expand the Quantities section.</span></span>
2. <span data-ttu-id="64269-124">Définissez la quantité par défaut sur 10.</span><span class="sxs-lookup"><span data-stu-id="64269-124">Set Default quantity to '10'.</span></span>
    * <span data-ttu-id="64269-125">Il s'agit de la quantité qui sera transférée pour chaque kanban.</span><span class="sxs-lookup"><span data-stu-id="64269-125">This is the quantity that will be transferred for each kanban.</span></span>  
3. <span data-ttu-id="64269-126">Activez la case à cocher Écart de quantité de produits.</span><span class="sxs-lookup"><span data-stu-id="64269-126">Select the Product quantity variance check box.</span></span>
    * <span data-ttu-id="64269-127">Ainsi, les kanbans sélectionnés peuvent être menés à bien avec un écart par rapport à la quantité par défaut.</span><span class="sxs-lookup"><span data-stu-id="64269-127">With this, selected kanbans can be completed with a variance from the default quantity.</span></span>  <span data-ttu-id="64269-128">Pour autoriser que les kanbans soient exécutés avec une quantité de 8 à 12, définissez les deux écarts à 2.</span><span class="sxs-lookup"><span data-stu-id="64269-128">To allow kanbans to be completed with a quantity from 8 to 12, set both variances to 2.</span></span>  
4. <span data-ttu-id="64269-129">Définissez l'écart ci-dessous à « 2 ».</span><span class="sxs-lookup"><span data-stu-id="64269-129">Set Variance below to '2'.</span></span>
    * <span data-ttu-id="64269-130">Cela permettra de terminer jusqu'aussi bas que 10 - 2 = 8</span><span class="sxs-lookup"><span data-stu-id="64269-130">This will allow completing down to 10 - 2 = 8</span></span>  
5. <span data-ttu-id="64269-131">Définissez l'écart ci-dessus à « 2 ».</span><span class="sxs-lookup"><span data-stu-id="64269-131">Set Variance above to '2'.</span></span>
    * <span data-ttu-id="64269-132">Cela permettra de terminer jusqu'aussi haut que 10 + 2 = 12</span><span class="sxs-lookup"><span data-stu-id="64269-132">This will allow completing up to 10 + 2 = 12</span></span>  
6. <span data-ttu-id="64269-133">Dans le champ Quantité de kanban fixée, entrez un nombre.</span><span class="sxs-lookup"><span data-stu-id="64269-133">In the Fixed kanban quantity field, enter a number.</span></span>
    * <span data-ttu-id="64269-134">Il s'agit de la quantité de kanbans qui doivent être actifs.</span><span class="sxs-lookup"><span data-stu-id="64269-134">This is the amount of kanbans that should be active.</span></span> <span data-ttu-id="64269-135">Dans ce cas, 5 kanbans qui traitent 10 unités chacun.</span><span class="sxs-lookup"><span data-stu-id="64269-135">In this case, 5 kanbans processing 10 each.</span></span>  
7. <span data-ttu-id="64269-136">Dans le champ Limite d'alerte minimale, entrez « 2 ».</span><span class="sxs-lookup"><span data-stu-id="64269-136">In the Alert boundary minimum field, enter '2'.</span></span>
    * <span data-ttu-id="64269-137">Permet de tenir à jour la quantité minimale de kanbans complets qui doivent être à la destination.</span><span class="sxs-lookup"><span data-stu-id="64269-137">Used to keep track of the minimum amount of full kanbans that should be at the destination.</span></span> <span data-ttu-id="64269-138">Par exemple, cela sert dans la vue d'ensemble de la quantité de kanban.</span><span class="sxs-lookup"><span data-stu-id="64269-138">For example, this is used on the kanban quantity overview.</span></span>  
8. <span data-ttu-id="64269-139">Dans le champ Limite d'alerte maximale, entrez « 4 ».</span><span class="sxs-lookup"><span data-stu-id="64269-139">In the Alert boundary maximum field, enter '4'.</span></span>
    * <span data-ttu-id="64269-140">Permet de tenir à jour la quantité maximale de kanbans complets qui doivent être à la destination.</span><span class="sxs-lookup"><span data-stu-id="64269-140">Used to keep track of the maximum amount of full kanbans that should be at the destination.</span></span> <span data-ttu-id="64269-141">Par exemple, cela sert dans la vue d'ensemble de la quantité de kanban.</span><span class="sxs-lookup"><span data-stu-id="64269-141">For example, this is used on the kanban quantity overview.</span></span>  
9. <span data-ttu-id="64269-142">Dans le champ Quantité de planification automatique, entrez « 1 ».</span><span class="sxs-lookup"><span data-stu-id="64269-142">In the Automatic planning quantity field, enter '1'.</span></span>
    * <span data-ttu-id="64269-143">Le fait définir cette valeur sur 1 signifie que chaque kanban sera prévu automatiquement.</span><span class="sxs-lookup"><span data-stu-id="64269-143">Setting this to 1 means that every kanban will be automatically planned.</span></span>   <span data-ttu-id="64269-144">Si nous entrions 3, les kanbans ne seraient pas prévus tant que 3 kanbans vides ne sont pas prêts à la planification.</span><span class="sxs-lookup"><span data-stu-id="64269-144">If we entered 3, the kanbans would not be planned until 3 empty kanbans are ready for planning.</span></span> <span data-ttu-id="64269-145">Cela est utile pour regrouper le travail et réduire le besoin de paramétrage.</span><span class="sxs-lookup"><span data-stu-id="64269-145">This is useful for grouping work and avoiding too much setup.</span></span>  

## <a name="create-kanbans"></a><span data-ttu-id="64269-146">Créer des kanbans</span><span class="sxs-lookup"><span data-stu-id="64269-146">Create Kanbans</span></span>
1. <span data-ttu-id="64269-147">Développer la section Kanbans.</span><span class="sxs-lookup"><span data-stu-id="64269-147">Expand the Kanbans section.</span></span>
2. <span data-ttu-id="64269-148">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="64269-148">Click Save.</span></span>
    * <span data-ttu-id="64269-149">La règle de kanban doit être enregistrée avant que les kanbans puissent être créés.</span><span class="sxs-lookup"><span data-stu-id="64269-149">The kanban rule needs to be saved before kanbans can be created.</span></span>  
3. <span data-ttu-id="64269-150">Cliquez sur Ajouter.</span><span class="sxs-lookup"><span data-stu-id="64269-150">Click Add.</span></span>
    * <span data-ttu-id="64269-151">Notez qu'il n'existe aucun kanban actif, parce que le « Nombre suggéré de nouveaux kanbans » vaut 5.</span><span class="sxs-lookup"><span data-stu-id="64269-151">Note that there are no active kanbans, due to this the suggested 'Number of new kanbans' are 5.</span></span> <span data-ttu-id="64269-152">Cela est égal à la « quantité fixe de kanban ».</span><span class="sxs-lookup"><span data-stu-id="64269-152">This is equal to the 'Fixed kanban quantity'.</span></span>  
4. <span data-ttu-id="64269-153">Cliquez sur Créer.</span><span class="sxs-lookup"><span data-stu-id="64269-153">Click Create.</span></span>
    * <span data-ttu-id="64269-154">Cette opération crée 5 kanbans.</span><span class="sxs-lookup"><span data-stu-id="64269-154">This will create 5 kanbans.</span></span>  
    * <span data-ttu-id="64269-155">Notez que 5 kanbans, chacun pour 10 unités, ont été créés pour cette règle de kanban de fabrication.</span><span class="sxs-lookup"><span data-stu-id="64269-155">Note that 5 kanbans, for 10 each, was created for this manufacturing kanban rule.</span></span> <span data-ttu-id="64269-156">Il s'agit de la dernière étape de cette procédure.</span><span class="sxs-lookup"><span data-stu-id="64269-156">This is the last step in this procedure.</span></span>  


