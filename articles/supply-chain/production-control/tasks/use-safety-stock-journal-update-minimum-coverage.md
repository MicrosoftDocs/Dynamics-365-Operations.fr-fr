---
title: Utiliser le journal du stock de sécurité pour mettre à jour la couverture minimale
description: Cette procédure montre comment calculer des propositions de couverture minimale basées sur des transactions historiques et comment mettre à jour la couverture d'article avec ces propositions.
author: ChristianRytt
manager: tfehr
ms.date: 08/09/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ReqItemJournalName, ReqItemJournalSafetyStock, EcoResProductInformationDialog, EcoResProductDetailsExtended, ReqItemTable
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 0d69daf3d307ba72ff6017d91849e3d22bd0bd85
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/02/2020
ms.locfileid: "3210316"
---
# <a name="use-the-safety-stock-journal-to-update-minimum-coverage"></a><span data-ttu-id="d0625-103">Utiliser le journal du stock de sécurité pour mettre à jour la couverture minimale</span><span class="sxs-lookup"><span data-stu-id="d0625-103">Use the safety stock journal to update minimum coverage</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="d0625-104">Cette procédure montre comment calculer des propositions de couverture minimale basées sur des transactions historiques et comment mettre à jour la couverture d'article avec ces propositions.</span><span class="sxs-lookup"><span data-stu-id="d0625-104">This procedure shows how to calculate minimum coverage proposals based on historical transactions and then update the item coverage with the proposals.</span></span> <span data-ttu-id="d0625-105">Cette opération est effectuée à l'aide du journal du stock de sécurité.</span><span class="sxs-lookup"><span data-stu-id="d0625-105">This is done using the safety stock journal.</span></span> <span data-ttu-id="d0625-106">Les données fictives utilisées pour créer cette tâche correspondent à la société USMF.</span><span class="sxs-lookup"><span data-stu-id="d0625-106">The demo data company used to create this task is USMF.</span></span> <span data-ttu-id="d0625-107">Cette tâche est destinée au responsable de production, pour aider à maintenir la couverture minimale.</span><span class="sxs-lookup"><span data-stu-id="d0625-107">This task is intended for the production planner, to help maintain minimum coverage.</span></span>


## <a name="create-a-new-safety-stock-journal-name"></a><span data-ttu-id="d0625-108">Créer un nouveau nom de journal de stock</span><span class="sxs-lookup"><span data-stu-id="d0625-108">Create a new safety stock journal name</span></span>
1. <span data-ttu-id="d0625-109">Dans le **Volet de navigation**, allez dans **Planification > Paramétrage > Noms du journal du stock de sécurité**.</span><span class="sxs-lookup"><span data-stu-id="d0625-109">In the **Navigation pane**, go to **Master planning > Setup > Safety stock journal names**.</span></span>
2. <span data-ttu-id="d0625-110">Cliquez sur **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="d0625-110">Click **New**.</span></span>
3. <span data-ttu-id="d0625-111">Dans le champ **Nom**, tapez « Matériel ».</span><span class="sxs-lookup"><span data-stu-id="d0625-111">In the **Name** field, type 'Material'.</span></span>
4. <span data-ttu-id="d0625-112">Dans le champ **Description**, tapez « Matériel ».</span><span class="sxs-lookup"><span data-stu-id="d0625-112">In the **Description** field, type 'Material'.</span></span>
5. <span data-ttu-id="d0625-113">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="d0625-113">Close the page.</span></span>

## <a name="create-a-safety-stock-journal"></a><span data-ttu-id="d0625-114">Créer un journal du stock de sécurité</span><span class="sxs-lookup"><span data-stu-id="d0625-114">Create a safety stock journal</span></span>
1. <span data-ttu-id="d0625-115">Dans le **Volet de navigation**, allez dans **Planification > Planification > Exécuter > Calcul du stock de sécurité**.</span><span class="sxs-lookup"><span data-stu-id="d0625-115">In the **Navigation pane**, go to **Master planning > Master planning > Run > Safety stock calculation**.</span></span>
2. <span data-ttu-id="d0625-116">Cliquez sur **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="d0625-116">Click **New**.</span></span>
3. <span data-ttu-id="d0625-117">Dans le champ **Nom**, saisissez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="d0625-117">In the **Name** field, enter or select a value.</span></span> <span data-ttu-id="d0625-118">Choisissez le nom du journal de stock de sécurité que vous avez créé, par exemple, Matériel.</span><span class="sxs-lookup"><span data-stu-id="d0625-118">Select the safety stock journal name that you created, for example, Material.</span></span>  
4. <span data-ttu-id="d0625-119">Cliquez sur **Créer des lignes**.</span><span class="sxs-lookup"><span data-stu-id="d0625-119">Click **Create lines**.</span></span>
5. <span data-ttu-id="d0625-120">Entrez une date dans le champ **Date de début**.</span><span class="sxs-lookup"><span data-stu-id="d0625-120">In the **From date** field, enter a date.</span></span>  
6. <span data-ttu-id="d0625-121">Entrez une date dans le champ **Date de fin**.</span><span class="sxs-lookup"><span data-stu-id="d0625-121">In the **To date** field, enter a date.</span></span>
7. <span data-ttu-id="d0625-122">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="d0625-122">Click **OK**.</span></span> <span data-ttu-id="d0625-123">Ceci créera des lignes pour les dimensions qui ont des mouvements de stock.</span><span class="sxs-lookup"><span data-stu-id="d0625-123">This will create lines for the dimensions that have inventory transactions.</span></span>  

## <a name="calculate-proposal"></a><span data-ttu-id="d0625-124">Calculer la proposition</span><span class="sxs-lookup"><span data-stu-id="d0625-124">Calculate proposal</span></span>
1. <span data-ttu-id="d0625-125">Cliquez sur **Calculer la proposition**.</span><span class="sxs-lookup"><span data-stu-id="d0625-125">Click **Calculate proposal**.</span></span>
2. <span data-ttu-id="d0625-126">Sélectionnez l'option **Utiliser la sortie moyenne pendant le délai**.</span><span class="sxs-lookup"><span data-stu-id="d0625-126">Select the **Use average issue during lead time** option.</span></span>
3. <span data-ttu-id="d0625-127">Définissez le **facteur de multiplication** sur « 10 ».</span><span class="sxs-lookup"><span data-stu-id="d0625-127">Set **Multiplication factor** to '10'.</span></span> <span data-ttu-id="d0625-128">Le facteur de multiplication est employé pour ajuster la proposition.</span><span class="sxs-lookup"><span data-stu-id="d0625-128">The Multiply factor is used to adjust the proposal.</span></span> <span data-ttu-id="d0625-129">Les données de démonstration ne contiennent que quelques transactions, vous devrez donc définir le facteur pour obtenir une proposition réaliste.</span><span class="sxs-lookup"><span data-stu-id="d0625-129">Because demo data only has a few transactions, you will need to set the factor to get a realistic proposal.</span></span>  
4. <span data-ttu-id="d0625-130">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="d0625-130">Click **OK**.</span></span> <span data-ttu-id="d0625-131">Faites défiler vers le bas jusqu'à M0002 et M0003.</span><span class="sxs-lookup"><span data-stu-id="d0625-131">Scroll down to find M0002 and M0003.</span></span> <span data-ttu-id="d0625-132">Affichez la colonne **Quantité minimale calculée**.</span><span class="sxs-lookup"><span data-stu-id="d0625-132">View the **Calculated minimum** quantity column.</span></span>   

## <a name="update-minimum-quantity"></a><span data-ttu-id="d0625-133">Mettre à jour la quantité minimale</span><span class="sxs-lookup"><span data-stu-id="d0625-133">Update minimum quantity</span></span>
1. <span data-ttu-id="d0625-134">Entrez un nombre dans le champ **Nouvelle quantité minimale**.</span><span class="sxs-lookup"><span data-stu-id="d0625-134">In the **New minimum quantity** field, enter a number.</span></span> <span data-ttu-id="d0625-135">Mettre à jour la nouvelle quantité minimale pour correspondre à la valeur de la quantité minimale calculée.</span><span class="sxs-lookup"><span data-stu-id="d0625-135">Update the New minimum quantity to match the value in the Calculated minimum quantity.</span></span> <span data-ttu-id="d0625-136">Si le minimum calculé est zéro, vous pouvez entrer la valeur future désirée.</span><span class="sxs-lookup"><span data-stu-id="d0625-136">If the Calculated minimum is zero,  you can enter the desired future value.</span></span> <span data-ttu-id="d0625-137">Par exemple, vous pouvez entrer la quantité minimale calculée dans ce champ pour M0002 qui a l'entrepôt 12.</span><span class="sxs-lookup"><span data-stu-id="d0625-137">For example, you can enter the Calculated minimum quantity in this field for M0002 that has warehouse 12.</span></span>  
2. <span data-ttu-id="d0625-138">Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="d0625-138">In the list, find and select the desired record.</span></span> <span data-ttu-id="d0625-139">Par exemple, vous pouvez choisir M0002 qui a l'entrepôt 12.</span><span class="sxs-lookup"><span data-stu-id="d0625-139">For example, you can select M0002 that has warehouse 12.</span></span>  
3. <span data-ttu-id="d0625-140">Entrez un nombre dans le champ **Nouvelle quantité minimale**.</span><span class="sxs-lookup"><span data-stu-id="d0625-140">In the **New minimum quantity** field, enter a number.</span></span> <span data-ttu-id="d0625-141">Mettre à jour la nouvelle quantité minimale pour correspondre à la valeur de la quantité minimale calculée.</span><span class="sxs-lookup"><span data-stu-id="d0625-141">Update the New minimum quantity to match the value in the Calculated minimum quantity.</span></span> <span data-ttu-id="d0625-142">Si le minimum calculé est zéro, vous pouvez entrer la valeur future désirée.</span><span class="sxs-lookup"><span data-stu-id="d0625-142">If the Calculated minimum is zero you can enter the desired future value.</span></span>  

## <a name="post-the-new-minimum-quantity-and-validate-the-result"></a><span data-ttu-id="d0625-143">Valider la nouvelle quantité minimale et contrôler le résultat</span><span class="sxs-lookup"><span data-stu-id="d0625-143">Post the new minimum quantity and validate the result</span></span>
1. <span data-ttu-id="d0625-144">Cliquez sur **Valider**.</span><span class="sxs-lookup"><span data-stu-id="d0625-144">Click **Post**.</span></span>
2. <span data-ttu-id="d0625-145">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="d0625-145">Click **OK**.</span></span>
3. <span data-ttu-id="d0625-146">Cliquez pour suivre le lien dans le champ **Numéro d'article**.</span><span class="sxs-lookup"><span data-stu-id="d0625-146">Click to follow the link in the **Item number** field.</span></span>
4. <span data-ttu-id="d0625-147">Cliquez pour suivre le lien dans le champ **Numéro d'article**.</span><span class="sxs-lookup"><span data-stu-id="d0625-147">Click to follow the link in the **Item number** field.</span></span>
5. <span data-ttu-id="d0625-148">Dans le **volet Actions**, cliquez sur Plan.</span><span class="sxs-lookup"><span data-stu-id="d0625-148">On the **Action Pane**, click Plan.</span></span>
6. <span data-ttu-id="d0625-149">Cliquez sur **Couverture de l'article**.</span><span class="sxs-lookup"><span data-stu-id="d0625-149">Click **Item coverage**.</span></span> <span data-ttu-id="d0625-150">Notez que la **quantité minimale** a été mise à jour avec la nouvelle quantité minimale du journal du stock de sécurité.</span><span class="sxs-lookup"><span data-stu-id="d0625-150">Notice that the **Minimum quantity** has been updated with the new minimum quantity from the safety stock journal.</span></span>  

