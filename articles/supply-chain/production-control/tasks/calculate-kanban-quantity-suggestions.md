--- 
title: "Calculer des suggestions de quantité de kanban"
description: "Cette procédure est orientée sur l'optimisation de la taille et des quantités de kanban pour une règle de kanban spécifique à l'aide du calcul de quantité de kanban."
author: ChristianRytt
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
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: a817dbc02890d863f68c5bf2a6cc11b9a5328060
ms.contentlocale: fr-fr
ms.lasthandoff: 08/29/2017

---
# <a name="calculate-kanban-quantity-suggestions"></a><span data-ttu-id="93e78-103">Calculer des suggestions de quantité de kanban</span><span class="sxs-lookup"><span data-stu-id="93e78-103">Calculate kanban quantity suggestions</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="93e78-104">Cette procédure est orientée sur l'optimisation de la taille et des quantités de kanban pour une règle de kanban spécifique à l'aide du calcul de quantité de kanban.</span><span class="sxs-lookup"><span data-stu-id="93e78-104">This procedure focuses on optimizing the kanban size and quantities for a specific kanban rule by using the kanban quantity calculation.</span></span> <span data-ttu-id="93e78-105">Les données fictives utilisées pour créer cette procédure correspondent à la société USMF.</span><span class="sxs-lookup"><span data-stu-id="93e78-105">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="93e78-106">Cette procédure est destinée au responsable de la chaîne de valeur.</span><span class="sxs-lookup"><span data-stu-id="93e78-106">This procedure is intended for the value stream manager.</span></span> <span data-ttu-id="93e78-107">Vous devez absolument avoir effectué la procédure Ajouter une stratégie de calcul de quantité kanban à une règle de kanban.</span><span class="sxs-lookup"><span data-stu-id="93e78-107">It is a prerequisite that you have completed the procedure Add a new kanban quantity calculation policy to a kanban rule.</span></span>


## <a name="create-a-kanban-quantity-calculation"></a><span data-ttu-id="93e78-108">Créer un calcul de quantité de kanban</span><span class="sxs-lookup"><span data-stu-id="93e78-108">Create a kanban quantity calculation</span></span>
1. <span data-ttu-id="93e78-109">Accédez à Contrôle de la production > Tâches périodiques > Calcul de quantité de kanban > Calculer la quantité de kanban.</span><span class="sxs-lookup"><span data-stu-id="93e78-109">Go to Production control > Periodic tasks > Kanban quantity calculation > Calculate kanban quantity.</span></span>
2. <span data-ttu-id="93e78-110">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="93e78-110">Click New.</span></span>
3. <span data-ttu-id="93e78-111">Saisissez « Speaker2016 » dans le champ Nom.</span><span class="sxs-lookup"><span data-stu-id="93e78-111">In the Name field, type 'Speaker2016'.</span></span>
4. <span data-ttu-id="93e78-112">Dans le champ Nom, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="93e78-112">In the Name field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="93e78-113">Sélectionnez la stratégie que vous avez créée dans la procédure Ajouter une stratégie de calcul de quantité kanban à une règle de kanban.</span><span class="sxs-lookup"><span data-stu-id="93e78-113">Select the policy that you have created in the procedure Add a new kanban quantity calculation policy to a kanban rule.</span></span> <span data-ttu-id="93e78-114">Par exemple, Speaker2016.</span><span class="sxs-lookup"><span data-stu-id="93e78-114">For example, Speaker2016.</span></span>  
5. <span data-ttu-id="93e78-115">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="93e78-115">In the list, click the link in the selected row.</span></span>
6. <span data-ttu-id="93e78-116">Dans le champ Date d'activation de la règle, définissez la date et l'heure comme suit : « 17-12-2012T08:00:00 ».</span><span class="sxs-lookup"><span data-stu-id="93e78-116">In the Rule active as of date field, set the date and time to '2012-12-17T08:00:00'.</span></span>
    * <span data-ttu-id="93e78-117">Cette date sert de base à la détermination des règles de kanban fixes à inclure dans le calcul de la quantité de kanban.</span><span class="sxs-lookup"><span data-stu-id="93e78-117">This date serves as the basis for determining which fixed kanban rules are included in the kanban quantity calculation.</span></span>  
7. <span data-ttu-id="93e78-118">Dans le champ Date de début de la période pour les demandes satisfaites, définissez la date et l'heure comme suit « 17-11-2012T09:00:00 ».</span><span class="sxs-lookup"><span data-stu-id="93e78-118">In the Fulfilled demand period start date field, set the date and time to '2012-11-17T09:00:00'.</span></span>
    * <span data-ttu-id="93e78-119">La date à partir de laquelle les transactions des demandes passées sont incluses dans le calcul de la quantité de kanban.</span><span class="sxs-lookup"><span data-stu-id="93e78-119">The date from when past demand transactions are included to calculate the kanban quantity.</span></span>  
8. <span data-ttu-id="93e78-120">Dans le champ Date de fin de la période pour les demandes satisfaites, définissez la date et l'heure comme suit « 17-12-2012T07:59:59 ».</span><span class="sxs-lookup"><span data-stu-id="93e78-120">In the Fulfilled demand period end date field, set the date and time to '2012-12-17T07:59:59'.</span></span>
    * <span data-ttu-id="93e78-121">La date jusqu'à laquelle les transactions des demandes passées sont incluses dans le calcul de la quantité de kanban.</span><span class="sxs-lookup"><span data-stu-id="93e78-121">The date until when past demand transactions are included to calculate the kanban quantity.</span></span>  
9. <span data-ttu-id="93e78-122">Dans le champ Date de début de la période de demande, définissez la date et l'heure comme suit « 17-12-2012T08:00:00 ».</span><span class="sxs-lookup"><span data-stu-id="93e78-122">In the Demand period start date field, set the date and time to '2012-12-17T08:00:00'.</span></span>
    * <span data-ttu-id="93e78-123">La date à partir de laquelle les transactions des demandes actuelles sont incluses dans le calcul de la quantité de kanban.</span><span class="sxs-lookup"><span data-stu-id="93e78-123">The date from when current demand transactions are included to calculate the kanban quantity.</span></span>  
10. <span data-ttu-id="93e78-124">Dans le champ Date de fin de la période de demande, définissez la date et l'heure comme suit « 16-01-2013T07:59:59 ».</span><span class="sxs-lookup"><span data-stu-id="93e78-124">In the Demand period end date field, set the date and time to '2013-01-16T07:59:59'.</span></span>
    * <span data-ttu-id="93e78-125">La date jusqu'à laquelle les transactions des demandes actuelles sont incluses dans le calcul de la quantité de kanban.</span><span class="sxs-lookup"><span data-stu-id="93e78-125">The date until when current demand transactions are included to calculate the kanban quantity.</span></span>  

## <a name="generate-kanban-quantity-proposal"></a><span data-ttu-id="93e78-126">Générer une proposition de quantité de kanban</span><span class="sxs-lookup"><span data-stu-id="93e78-126">Generate kanban quantity proposal</span></span>
1. <span data-ttu-id="93e78-127">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="93e78-127">Click Save.</span></span>
2. <span data-ttu-id="93e78-128">Cliquez sur Générer.</span><span class="sxs-lookup"><span data-stu-id="93e78-128">Click Generate.</span></span>
    * <span data-ttu-id="93e78-129">Cela génère une ligne de proposition de quantité de kanban pour la règle de kanban 000020.</span><span class="sxs-lookup"><span data-stu-id="93e78-129">This generates a kanban quantity proposal line for the kanban rule 000020.</span></span>  

## <a name="run-kanban-quantity-calculation"></a><span data-ttu-id="93e78-130">Exécuter un calcul de quantité de kanban</span><span class="sxs-lookup"><span data-stu-id="93e78-130">Run kanban quantity calculation</span></span>
1. <span data-ttu-id="93e78-131">Cliquez sur Calculer.</span><span class="sxs-lookup"><span data-stu-id="93e78-131">Click Calculate.</span></span>
    * <span data-ttu-id="93e78-132">Cette opération permet de calculer la proposition de quantité de kanban.</span><span class="sxs-lookup"><span data-stu-id="93e78-132">This calculates the kanban quantity proposal.</span></span>  
2. <span data-ttu-id="93e78-133">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="93e78-133">Click OK.</span></span>
3. <span data-ttu-id="93e78-134">Dans la liste, marquez la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="93e78-134">In the list, mark the selected row.</span></span>
    * <span data-ttu-id="93e78-135">Notez que la quantité de kanban suggérée est de 2.</span><span class="sxs-lookup"><span data-stu-id="93e78-135">Notice the suggested kanban quantity is 2.</span></span>  

## <a name="change-product-quantity-and-calculate-again"></a><span data-ttu-id="93e78-136">Modifier la quantité de produits et calculer à nouveau</span><span class="sxs-lookup"><span data-stu-id="93e78-136">Change product quantity and calculate again</span></span>
1. <span data-ttu-id="93e78-137">Définissez la quantité de produit sur 5.</span><span class="sxs-lookup"><span data-stu-id="93e78-137">Set Product quantity to '5'.</span></span>
2. <span data-ttu-id="93e78-138">Cliquez sur Calculer.</span><span class="sxs-lookup"><span data-stu-id="93e78-138">Click Calculate.</span></span>
3. <span data-ttu-id="93e78-139">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="93e78-139">Click OK.</span></span>
    * <span data-ttu-id="93e78-140">Notez qu'avec une quantité de kanban de 5, la suggestion est alors une quantité de kanban de 4.</span><span class="sxs-lookup"><span data-stu-id="93e78-140">Notice that with a kanban quantity of 5, the suggestion is changed to a kanban quantity of 4.</span></span>  
    * <span data-ttu-id="93e78-141">Cela est dû au fait qu'avec une quantité de produits moindre, il faut plus de kanbans pour répondre à la demande.</span><span class="sxs-lookup"><span data-stu-id="93e78-141">This is caused by the fact that with a lower product quantity, we need more kanbans to fulfill the demand.</span></span>  

## <a name="update-kanban-rule"></a><span data-ttu-id="93e78-142">Mettre à jour la règle de kanban</span><span class="sxs-lookup"><span data-stu-id="93e78-142">Update kanban rule</span></span>
1. <span data-ttu-id="93e78-143">Entrez une date et une heure dans le champ Date d'effet de la règle.</span><span class="sxs-lookup"><span data-stu-id="93e78-143">In the Rule effective date field, enter a date and time.</span></span>
    * <span data-ttu-id="93e78-144">Définissez « Date d'activation de la règle » sur une date dans le futur.</span><span class="sxs-lookup"><span data-stu-id="93e78-144">Set the 'Rule active as of date' to a date in the future.</span></span> <span data-ttu-id="93e78-145">Par exemple, la date du jour + un an.</span><span class="sxs-lookup"><span data-stu-id="93e78-145">For example, today + one year.</span></span>  
2. <span data-ttu-id="93e78-146">Cliquez sur Mise à jour.</span><span class="sxs-lookup"><span data-stu-id="93e78-146">Click Update.</span></span>
3. <span data-ttu-id="93e78-147">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="93e78-147">Click OK.</span></span>
4. <span data-ttu-id="93e78-148">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="93e78-148">Close the page.</span></span>

## <a name="validate-change-on-kanban-rule"></a><span data-ttu-id="93e78-149">Valider la modification de la règle de kanban</span><span class="sxs-lookup"><span data-stu-id="93e78-149">Validate change on kanban rule</span></span>
1. <span data-ttu-id="93e78-150">Accédez à Gestion des informations sur les produits > Lean manufacturing > Règles de kanban.</span><span class="sxs-lookup"><span data-stu-id="93e78-150">Go to Product information management > Lean manufacturing > Kanban rules.</span></span>
2. <span data-ttu-id="93e78-151">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="93e78-151">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="93e78-152">Sélectionnez la règle de kanban créée dans la tâche précédente.</span><span class="sxs-lookup"><span data-stu-id="93e78-152">Select the kanban rule that was created in the previous sub-task.</span></span> <span data-ttu-id="93e78-153">Il doit s'agir de la première règle de kanban de la liste triée par numéro.</span><span class="sxs-lookup"><span data-stu-id="93e78-153">This should be the first kanban rule in the list sorted by number.</span></span>  
3. <span data-ttu-id="93e78-154">Activez ou désactivez l'extension de la section Détails.</span><span class="sxs-lookup"><span data-stu-id="93e78-154">Toggle the expansion of the Details section.</span></span>
    * <span data-ttu-id="93e78-155">Notez la date d'effet, qui indique que cette règle n'est pas activée jusqu'à cette date.</span><span class="sxs-lookup"><span data-stu-id="93e78-155">Notice the effective date, which means that this rule is not activated until this date.</span></span>  
4. <span data-ttu-id="93e78-156">Activez ou désactivez l'extension de la section Quantités.</span><span class="sxs-lookup"><span data-stu-id="93e78-156">Toggle the expansion of the Quantities section.</span></span>
    * <span data-ttu-id="93e78-157">Notez qu'il s'agit de la quantité par défaut entrée dans le calcul de quantité de kanban.</span><span class="sxs-lookup"><span data-stu-id="93e78-157">Notice this is the default quantity that you entered on the kanban quantity calculation.</span></span>  
    * <span data-ttu-id="93e78-158">Notez qu'il s'agit de la quantité de 4 kanban fixe provenant du calcul de quantité de kanban.</span><span class="sxs-lookup"><span data-stu-id="93e78-158">Notice this is the fixed kanban quantity of 4 from the kanban quantity calculation.</span></span>  
5. <span data-ttu-id="93e78-159">Cliquez sur l'onglet ListPanel.</span><span class="sxs-lookup"><span data-stu-id="93e78-159">Click the ListPanel tab.</span></span>


