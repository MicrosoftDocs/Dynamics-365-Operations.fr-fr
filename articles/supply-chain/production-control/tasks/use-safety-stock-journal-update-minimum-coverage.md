--- 
title: "Utiliser le journal du stock de sécurité pour mettre à jour la couverture minimale"
description: "Cette procédure montre comment calculer des propositions de couverture minimale basées sur des transactions historiques et comment mettre à jour la couverture d'article avec ces propositions."
author: ChristianRytt
manager: AnnBe
ms.date: 8/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: ReqItemJournalName, ReqItemJournalSafetyStock, EcoResProductInformationDialog, EcoResProductDetailsExtended, ReqItemTable
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 32d71167fdad65cb1dec37671999a497759ca484
ms.openlocfilehash: 5199d5270a6ec709f76ddb05fda3d98d3df02384
ms.contentlocale: fr-fr
ms.lasthandoff: 09/11/2018

---
# <a name="use-the-safety-stock-journal-to-update-minimum-coverage"></a><span data-ttu-id="15285-103">Utiliser le journal du stock de sécurité pour mettre à jour la couverture minimale</span><span class="sxs-lookup"><span data-stu-id="15285-103">Use the safety stock journal to update minimum coverage</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="15285-104">Cette procédure montre comment calculer des propositions de couverture minimale basées sur des transactions historiques et comment mettre à jour la couverture d'article avec ces propositions.</span><span class="sxs-lookup"><span data-stu-id="15285-104">This procedure shows how to calculate minimum coverage proposals based on historical transactions and then update the item coverage with the proposals.</span></span> <span data-ttu-id="15285-105">Cette opération est effectuée à l'aide du journal du stock de sécurité.</span><span class="sxs-lookup"><span data-stu-id="15285-105">This is done using the safety stock journal.</span></span> <span data-ttu-id="15285-106">Les données fictives utilisées pour créer cette tâche correspondent à la société USMF.</span><span class="sxs-lookup"><span data-stu-id="15285-106">The demo data company used to create this task is USMF.</span></span> <span data-ttu-id="15285-107">Cette tâche est destinée au responsable de production, pour aider à maintenir la couverture minimale.</span><span class="sxs-lookup"><span data-stu-id="15285-107">This task is intended for the production planner, to help maintain minimum coverage.</span></span>


## <a name="create-a-new-safety-stock-journal-name"></a><span data-ttu-id="15285-108">Créer un nouveau nom de journal de stock</span><span class="sxs-lookup"><span data-stu-id="15285-108">Create a new safety stock journal name</span></span>
1. <span data-ttu-id="15285-109">Allez dans Noms du journal du stock de sécurité.</span><span class="sxs-lookup"><span data-stu-id="15285-109">Go to Safety stock journal names.</span></span>
2. <span data-ttu-id="15285-110">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="15285-110">Click New.</span></span>
3. <span data-ttu-id="15285-111">Tapez Matériel dans le champ Nom.</span><span class="sxs-lookup"><span data-stu-id="15285-111">In the Name field, type 'Material'.</span></span>
4. <span data-ttu-id="15285-112">Tapez Matériel dans le champ Description.</span><span class="sxs-lookup"><span data-stu-id="15285-112">In the Description field, type 'Material'.</span></span>
5. <span data-ttu-id="15285-113">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="15285-113">Close the page.</span></span>

## <a name="create-a-safety-stock-journal"></a><span data-ttu-id="15285-114">Créer un journal du stock de sécurité</span><span class="sxs-lookup"><span data-stu-id="15285-114">Create a safety stock journal</span></span>
1. <span data-ttu-id="15285-115">Allez dans Calcul du stock de sécurité.</span><span class="sxs-lookup"><span data-stu-id="15285-115">Go to Safety stock calculation.</span></span>
2. <span data-ttu-id="15285-116">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="15285-116">Click New.</span></span>
3. <span data-ttu-id="15285-117">Saisissez ou sélectionnez une valeur dans le champ Nom.</span><span class="sxs-lookup"><span data-stu-id="15285-117">In the Name field, enter or select a value.</span></span>
    * <span data-ttu-id="15285-118">Choisissez le nom du journal de stock de sécurité que vous avez créé, par exemple, Matériel.</span><span class="sxs-lookup"><span data-stu-id="15285-118">Select the safety stock journal name that you created, for example, Material.</span></span>  
4. <span data-ttu-id="15285-119">Cliquez sur Créer des lignes.</span><span class="sxs-lookup"><span data-stu-id="15285-119">Click Create lines.</span></span>
5. <span data-ttu-id="15285-120">Entrez une date dans le champ Date de début.</span><span class="sxs-lookup"><span data-stu-id="15285-120">In the From date field, enter a date.</span></span>
    * <span data-ttu-id="15285-121">Définissez la date 02/01/2015.</span><span class="sxs-lookup"><span data-stu-id="15285-121">Set the date to '2015-01-02'.</span></span>  
6. <span data-ttu-id="15285-122">Entrez une date dans le champ Date de fin.</span><span class="sxs-lookup"><span data-stu-id="15285-122">In the To date field, enter a date.</span></span>
    * <span data-ttu-id="15285-123">Définissez la date 30/12/2015.</span><span class="sxs-lookup"><span data-stu-id="15285-123">Set the date to '2015-12-30'.</span></span>  
7. <span data-ttu-id="15285-124">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="15285-124">Click OK.</span></span>
    * <span data-ttu-id="15285-125">Ceci créera des lignes pour les dimensions qui ont des mouvements de stock.</span><span class="sxs-lookup"><span data-stu-id="15285-125">This will create lines for the dimensions that have inventory transactions.</span></span>  

## <a name="calculate-proposal"></a><span data-ttu-id="15285-126">Calculer la proposition</span><span class="sxs-lookup"><span data-stu-id="15285-126">Calculate proposal</span></span>
1. <span data-ttu-id="15285-127">Cliquez sur Calculer la proposition.</span><span class="sxs-lookup"><span data-stu-id="15285-127">Click Calculate proposal.</span></span>
2. <span data-ttu-id="15285-128">Sélectionnez l'option Utiliser la sortie moyenne pendant le délai.</span><span class="sxs-lookup"><span data-stu-id="15285-128">Select the Use average issue during lead time option.</span></span>
3. <span data-ttu-id="15285-129">Définissez le facteur de multiplication sur 10.</span><span class="sxs-lookup"><span data-stu-id="15285-129">Set Multiplication factor to '10'.</span></span>
    * <span data-ttu-id="15285-130">Le facteur de multiplication est employé pour ajuster la proposition.</span><span class="sxs-lookup"><span data-stu-id="15285-130">The Multiply factor is used to adjust the proposal.</span></span> <span data-ttu-id="15285-131">Les données de démonstration ne contiennent que quelques transactions, vous devrez donc définir le facteur pour obtenir une proposition réaliste.</span><span class="sxs-lookup"><span data-stu-id="15285-131">Because demo data only has a few transactions, you will need to set the factor to get a realistic proposal.</span></span>  
4. <span data-ttu-id="15285-132">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="15285-132">Click OK.</span></span>
    * <span data-ttu-id="15285-133">Faites défiler vers le bas jusqu'à M0002 et M0003.</span><span class="sxs-lookup"><span data-stu-id="15285-133">Scroll down to find M0002 and M0003.</span></span> <span data-ttu-id="15285-134">Affichez la colonne Quantité minimale calculée.</span><span class="sxs-lookup"><span data-stu-id="15285-134">View the Calculated minimum quantity column.</span></span>   

## <a name="update-minimum-quantity"></a><span data-ttu-id="15285-135">Mettre à jour la quantité minimale</span><span class="sxs-lookup"><span data-stu-id="15285-135">Update minimum quantity</span></span>
1. <span data-ttu-id="15285-136">Entrez un nombre dans le champ Nouvelle quantité minimale.</span><span class="sxs-lookup"><span data-stu-id="15285-136">In the New minimum quantity field, enter a number.</span></span>
    * <span data-ttu-id="15285-137">Mettre à jour la nouvelle quantité minimale pour correspondre à la valeur de la quantité minimale calculée.</span><span class="sxs-lookup"><span data-stu-id="15285-137">Update the New minimum quantity to match the value in the Calculated minimum quantity.</span></span> <span data-ttu-id="15285-138">Si le minimum calculé est zéro, vous pouvez entrer la valeur future désirée.</span><span class="sxs-lookup"><span data-stu-id="15285-138">If the Calculated minimum is zero,  you can enter the desired future value.</span></span> <span data-ttu-id="15285-139">Par exemple, vous pouvez entrer la quantité minimale calculée dans ce champ pour M0002 qui a l'entrepôt 12.</span><span class="sxs-lookup"><span data-stu-id="15285-139">For example, you can enter the Calculated minimum quantity in this field for M0002 that has warehouse 12.</span></span>  
2. <span data-ttu-id="15285-140">Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="15285-140">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="15285-141">Par exemple, vous pouvez choisir M0002 qui a l'entrepôt 12.</span><span class="sxs-lookup"><span data-stu-id="15285-141">For example, you can select M0002 that has warehouse 12.</span></span>  
3. <span data-ttu-id="15285-142">Entrez un nombre dans le champ Nouvelle quantité minimale.</span><span class="sxs-lookup"><span data-stu-id="15285-142">In the New minimum quantity field, enter a number.</span></span>
    * <span data-ttu-id="15285-143">Mettre à jour la nouvelle quantité minimale pour correspondre à la valeur de la quantité minimale calculée.</span><span class="sxs-lookup"><span data-stu-id="15285-143">Update the New minimum quantity to match the value in the Calculated minimum quantity.</span></span> <span data-ttu-id="15285-144">Si le minimum calculé est zéro, vous pouvez entrer la valeur future désirée.</span><span class="sxs-lookup"><span data-stu-id="15285-144">If the Calculated minimum is zero you can enter the desired future value.</span></span>  

## <a name="post-the-new-minimum-quantity-and-validate-the-result"></a><span data-ttu-id="15285-145">Valider la nouvelle quantité minimale et contrôler le résultat</span><span class="sxs-lookup"><span data-stu-id="15285-145">Post the new minimum quantity and validate the result</span></span>
1. <span data-ttu-id="15285-146">Cliquez sur Valider.</span><span class="sxs-lookup"><span data-stu-id="15285-146">Click Post.</span></span>
2. <span data-ttu-id="15285-147">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="15285-147">Click OK.</span></span>
3. <span data-ttu-id="15285-148">Cliquez pour suivre le lien dans le champ Numéro d'article.</span><span class="sxs-lookup"><span data-stu-id="15285-148">Click to follow the link in the Item number field.</span></span>
4. <span data-ttu-id="15285-149">Cliquez pour suivre le lien dans le champ Numéro d'article.</span><span class="sxs-lookup"><span data-stu-id="15285-149">Click to follow the link in the Item number field.</span></span>
5. <span data-ttu-id="15285-150">Cliquez sur Planifier dans le volet Actions.</span><span class="sxs-lookup"><span data-stu-id="15285-150">On the Action Pane, click Plan.</span></span>
6. <span data-ttu-id="15285-151">Cliquez sur Couverture de l'article.</span><span class="sxs-lookup"><span data-stu-id="15285-151">Click Item coverage.</span></span>
    * <span data-ttu-id="15285-152">Notez que la quantité minimale a été mise à jour avec la nouvelle quantité minimale du journal du stock de sécurité.</span><span class="sxs-lookup"><span data-stu-id="15285-152">Notice that the Minimum quantity has been updated with the new minimum quantity from the safety stock journal.</span></span>  


