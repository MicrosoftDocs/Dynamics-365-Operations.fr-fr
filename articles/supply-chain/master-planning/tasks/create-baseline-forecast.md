--- 
title: "Créer une prévision de base"
description: "Un responsable de production peut créer une prévision de base à l'aide des modèles de prévision de série chronologiques ou en copiant la demande historique."
author: YuyuScheller
manager: AnnBe
ms.date: 10/27/2016
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
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: e6363ee48c0d13c79a6c623205dfa10f50d6070f
ms.contentlocale: fr-fr
ms.lasthandoff: 09/29/2017

---
# <a name="create-a-baseline-forecast"></a><span data-ttu-id="df93a-103">Créer une prévision de base</span><span class="sxs-lookup"><span data-stu-id="df93a-103">Create a baseline forecast</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="df93a-104">Un responsable de production peut créer une prévision de base à l'aide des modèles de prévision de série chronologiques ou en copiant la demande historique.</span><span class="sxs-lookup"><span data-stu-id="df93a-104">A production planner can create a baseline forecast either by using time series forecast models or by copying the historical demand.</span></span> <span data-ttu-id="df93a-105">Cette procédure indique comment copier la demande historique pour créer une prévision de base pour tous les produits à l'aide d'une clé de répartition par article.</span><span class="sxs-lookup"><span data-stu-id="df93a-105">This procedure shows how to copy the historical demand to create a baseline forecast for all products using one item allocation key.</span></span> 


## <a name="set-up-an-item-allocation-key"></a><span data-ttu-id="df93a-106">Paramétrer une clé de répartition par article</span><span class="sxs-lookup"><span data-stu-id="df93a-106">Set up an item allocation key</span></span>
1. <span data-ttu-id="df93a-107">Accédez à Planification > Paramétrage > Groupes de planification intersociétés.</span><span class="sxs-lookup"><span data-stu-id="df93a-107">Go to Master planning > Setup > Intercompany planning groups.</span></span>
2. <span data-ttu-id="df93a-108">Utilisez le Filtre rapide pour rechercher les enregistrements.</span><span class="sxs-lookup"><span data-stu-id="df93a-108">Use the Quick Filter to find records.</span></span> <span data-ttu-id="df93a-109">Par exemple, filtrez sur le champ Nom avec une valeur de « 10 ».</span><span class="sxs-lookup"><span data-stu-id="df93a-109">For example, filter on the Name field with a value of '10'.</span></span>
    * <span data-ttu-id="df93a-110">Les prévisions de la demande fonctionnent dans les entités juridiques.</span><span class="sxs-lookup"><span data-stu-id="df93a-110">Demand forecasting runs across legal entities.</span></span> <span data-ttu-id="df93a-111">C'est pourquoi vous devez paramétrer toutes les sociétés pour lesquelles vous souhaitez générer des prévisions à un groupe de planification intersociétés.</span><span class="sxs-lookup"><span data-stu-id="df93a-111">That's why you need to set up all the companies for which you want to generate forecasts in one intercompany planning group.</span></span>  
3. <span data-ttu-id="df93a-112">Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="df93a-112">In the list, find and select the desired record.</span></span>
4. <span data-ttu-id="df93a-113">Cliquez sur Clés de répartition par article.</span><span class="sxs-lookup"><span data-stu-id="df93a-113">Click Item allocation keys.</span></span>
    * <span data-ttu-id="df93a-114">Sélectionnez toutes les clés de répartition par article pour lesquelles vous souhaitez créer des prévisions.</span><span class="sxs-lookup"><span data-stu-id="df93a-114">Select all the item allocation keys for which you want to create forecasts.</span></span>  
5. <span data-ttu-id="df93a-115">Dans la liste, marquez la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="df93a-115">In the list, mark the selected row.</span></span>
    * <span data-ttu-id="df93a-116">Sélectionnez la clé de répartition par article D_Aloc.</span><span class="sxs-lookup"><span data-stu-id="df93a-116">Select D_Aloc item allocation key.</span></span>  
6. <span data-ttu-id="df93a-117">Cliquer sur >.</span><span class="sxs-lookup"><span data-stu-id="df93a-117">Click >.</span></span>
7. <span data-ttu-id="df93a-118">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="df93a-118">Close the page.</span></span>
8. <span data-ttu-id="df93a-119">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="df93a-119">Close the page.</span></span>

## <a name="set-up-the-demand-forecasting-paramters"></a><span data-ttu-id="df93a-120">Définir des paramètres de prévision de la demande </span><span class="sxs-lookup"><span data-stu-id="df93a-120">Set up the demand forecasting paramters</span></span>
1. <span data-ttu-id="df93a-121">Accédez à Planification > Paramétrage> Prévision de la demande > Paramètres de prévision de la demande.</span><span class="sxs-lookup"><span data-stu-id="df93a-121">Go to Master planning > Setup > Demand forecasting > Demand forecasting parameters.</span></span>
2. <span data-ttu-id="df93a-122">Développez la section Paramètres de l'algorithme de prévision.</span><span class="sxs-lookup"><span data-stu-id="df93a-122">Expand the Forecast algorithm parameters section.</span></span>
3. <span data-ttu-id="df93a-123">Dans le champ Stratégie de génération de la prévision, sélectionnez Copier sur la demande historique.</span><span class="sxs-lookup"><span data-stu-id="df93a-123">In the Forecast generation strategy field, select 'Copy over historical demand'.</span></span>
4. <span data-ttu-id="df93a-124">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="df93a-124">Click Save.</span></span>

## <a name="create-a-baseline-forecast"></a><span data-ttu-id="df93a-125">Créer une prévision de base</span><span class="sxs-lookup"><span data-stu-id="df93a-125">Create a baseline forecast</span></span>
1. <span data-ttu-id="df93a-126">Accédez à Planification > Prévisions > Prévision de la demande > Générer des prévisions de base statistiques.</span><span class="sxs-lookup"><span data-stu-id="df93a-126">Go to Master planning > Forecasting > Demand forecasting > Generate statistical baseline forecast.</span></span>
2. <span data-ttu-id="df93a-127">Entrez une date dans le champ Date de début.</span><span class="sxs-lookup"><span data-stu-id="df93a-127">In the From date field, enter a date.</span></span>
    * <span data-ttu-id="df93a-128">Si vous avez des commandes client à partir du 1er janvier 2015, entrez cette date.</span><span class="sxs-lookup"><span data-stu-id="df93a-128">If you have sales orders starting from January 1, 2015, enter this date.</span></span> <span data-ttu-id="df93a-129">Si ce n'est pas le cas, entrez la date de vos commandes client la plus proche.</span><span class="sxs-lookup"><span data-stu-id="df93a-129">If you don't, enter the earliest date of your sales orders.</span></span>  
3. <span data-ttu-id="df93a-130">Entrez une date dans le champ Date de fin.</span><span class="sxs-lookup"><span data-stu-id="df93a-130">In the To date field, enter a date.</span></span>
    * <span data-ttu-id="df93a-131">Entrez la dernière date de vos commandes client, par exemple « 31-03-2015 ».</span><span class="sxs-lookup"><span data-stu-id="df93a-131">Enter the last date of your sales orders, for example '2015-03-31'.</span></span>  
4. <span data-ttu-id="df93a-132">Entrez une date dans le champ Date de début.</span><span class="sxs-lookup"><span data-stu-id="df93a-132">In the From date field, enter a date.</span></span>
    * <span data-ttu-id="df93a-133">Entrez « 01-04-2015 ».</span><span class="sxs-lookup"><span data-stu-id="df93a-133">Enter '2015-04-01'.</span></span> <span data-ttu-id="df93a-134">Cette date est automatiquement calculée comme date de début pour la prévision suivante.</span><span class="sxs-lookup"><span data-stu-id="df93a-134">This date will be automatically calculated as the start date of the next forecasting bucket.</span></span>  
5. <span data-ttu-id="df93a-135">Développez les enregistrements pour inclure la section.</span><span class="sxs-lookup"><span data-stu-id="df93a-135">Expand the Records to include section.</span></span>
6. <span data-ttu-id="df93a-136">Cliquez sur Filtre.</span><span class="sxs-lookup"><span data-stu-id="df93a-136">Click Filter.</span></span>
7. <span data-ttu-id="df93a-137">Dans la liste, marquez la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="df93a-137">In the list, mark the selected row.</span></span>
    * <span data-ttu-id="df93a-138">Marquez la ligne où Champ = Groupe de planification intersociétés.</span><span class="sxs-lookup"><span data-stu-id="df93a-138">Mark the row where Field = Intercompany planning group.</span></span>  
8. <span data-ttu-id="df93a-139">Tapez une valeur dans le champ Critères.</span><span class="sxs-lookup"><span data-stu-id="df93a-139">In the Criteria field, type a value.</span></span>
    * <span data-ttu-id="df93a-140">Tapez le groupe de planification intersociétés, par exemple, 10, que vous avez utilisé dans la première tâche.</span><span class="sxs-lookup"><span data-stu-id="df93a-140">Type the intercompany planning group, for example, 10, that you used in the first task.</span></span>  
9. <span data-ttu-id="df93a-141">Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="df93a-141">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="df93a-142">Sélectionnez la ligne de champ = clé de répartition par article.</span><span class="sxs-lookup"><span data-stu-id="df93a-142">Select the row where Field = Item allocation key.</span></span>  
10. <span data-ttu-id="df93a-143">Tapez une valeur dans le champ Critères.</span><span class="sxs-lookup"><span data-stu-id="df93a-143">In the Criteria field, type a value.</span></span>
11. <span data-ttu-id="df93a-144">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="df93a-144">Click OK.</span></span>
12. <span data-ttu-id="df93a-145">Développez la section Paramètres avancés.</span><span class="sxs-lookup"><span data-stu-id="df93a-145">Expand the Advanced parameters section.</span></span>
13. <span data-ttu-id="df93a-146">Sélectionnez Mois dans le champ Intervalle de prévision.</span><span class="sxs-lookup"><span data-stu-id="df93a-146">In the Forecast bucket field, select 'Month'.</span></span>
14. <span data-ttu-id="df93a-147">Entrez 3 dans le champ Horizon de prévision.</span><span class="sxs-lookup"><span data-stu-id="df93a-147">In the Forecast horizon field, enter '3'.</span></span>
15. <span data-ttu-id="df93a-148">Entrez 1 dans le champ Limite de période du gel.</span><span class="sxs-lookup"><span data-stu-id="df93a-148">In the Freeze time fence field, enter '1'.</span></span>
16. <span data-ttu-id="df93a-149">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="df93a-149">Click OK.</span></span>

## <a name="visualize-the-demand-forecast"></a><span data-ttu-id="df93a-150">Visualiser la prévision de la demande</span><span class="sxs-lookup"><span data-stu-id="df93a-150">Visualize the demand forecast</span></span>
1. <span data-ttu-id="df93a-151">Accédez à Planification > Prévisions > Prévision de la demande > Prévision de la demande ajustée.</span><span class="sxs-lookup"><span data-stu-id="df93a-151">Go to Master planning > Forecasting > Demand forecasting > Adjusted demand forecast.</span></span>
2. <span data-ttu-id="df93a-152">Dans la table de vue d'ensemble regroupée, sélectionnez la cellule de la ligne 1, colonne 2.</span><span class="sxs-lookup"><span data-stu-id="df93a-152">In the aggregated view table, select the cell in row 1, column 2.</span></span> <span data-ttu-id="df93a-153">Il s'agit de la cellule pour le deuxième mois pour lequel vous avez créé une prévision.</span><span class="sxs-lookup"><span data-stu-id="df93a-153">This is the second month for which you have created forecast.</span></span>
3. <span data-ttu-id="df93a-154">Définissez QtyCell sur « 400 ".</span><span class="sxs-lookup"><span data-stu-id="df93a-154">Set QtyCell to '400'.</span></span>
    * <span data-ttu-id="df93a-155">Dans la cellule, entrez un nombre différent de celui qui a été planifié, par exemple, 400.</span><span class="sxs-lookup"><span data-stu-id="df93a-155">In the cell, enter a different number than the one that was forecasted, for example, 400.</span></span>  
4. <span data-ttu-id="df93a-156">Vous avez effectué un ajustement manuel dans la prévision.</span><span class="sxs-lookup"><span data-stu-id="df93a-156">You have made a manual adjustment to the forecast.</span></span> <span data-ttu-id="df93a-157">Notez l'indication graphique dans l'étape suivante.</span><span class="sxs-lookup"><span data-stu-id="df93a-157">Notice the graphical indication in the next step.</span></span>
5. <span data-ttu-id="df93a-158">Cliquez sur Détails des lignes de prévision.</span><span class="sxs-lookup"><span data-stu-id="df93a-158">Click Forecast line details.</span></span>
    * <span data-ttu-id="df93a-159">Dans cette page, vous pouvez voir les valeurs de précision, la demande historique et la prévision.</span><span class="sxs-lookup"><span data-stu-id="df93a-159">In this page, you can see the accuracy values, historical demand, and forecast.</span></span> <span data-ttu-id="df93a-160">Vous pouvez également apporter des modifications aux prévisions.</span><span class="sxs-lookup"><span data-stu-id="df93a-160">You can make changes to the forecast as well.</span></span>  


