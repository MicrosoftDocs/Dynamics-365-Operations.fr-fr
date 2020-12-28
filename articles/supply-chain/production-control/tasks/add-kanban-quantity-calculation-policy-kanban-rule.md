---
title: Ajouter une stratégie de calcul de quantité kanban à une règle de kanban
description: Cette procédure est orientée sur la création d'une stratégie de calcul de quantité de kanban et le fait de l'ajouter à une règle de kanban optimise la taille et les quantités de kanban.
author: ChristianRytt
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: KanbanQuantityPolicy, KanbanRules, KanbanQuantityCalculation
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 039c4aaa355cf2b850ded06913e8e39ee8cac543
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4427621"
---
# <a name="add-a-kanban-quantity-calculation-policy-to-a-kanban-rule"></a><span data-ttu-id="89f00-103">Ajouter une stratégie de calcul de quantité kanban à une règle de kanban</span><span class="sxs-lookup"><span data-stu-id="89f00-103">Add a kanban quantity calculation policy to a kanban rule</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="89f00-104">Cette procédure est orientée sur la création d'une stratégie de calcul de quantité de kanban et le fait de l'ajouter à une règle de kanban optimise la taille et les quantités de kanban.</span><span class="sxs-lookup"><span data-stu-id="89f00-104">This procedure focuses on creating a kanban quantity calculation policy and adding it to a kanban rule to optimize the kanban size and quantities.</span></span> <span data-ttu-id="89f00-105">Les données fictives utilisées pour créer cette procédure correspondent à la société USMF.</span><span class="sxs-lookup"><span data-stu-id="89f00-105">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="89f00-106">Cette procédure est destinée au responsable de la chaîne de valeur.</span><span class="sxs-lookup"><span data-stu-id="89f00-106">This procedure is intended for the value stream manager.</span></span> <span data-ttu-id="89f00-107">Cette procédure doit impérativement être effectuée avant de créer la procédure Calculer des suggestions de quantité de kanban.</span><span class="sxs-lookup"><span data-stu-id="89f00-107">This procedure is a prerequisite for creating the procedure Calculate kanban quantity suggestions.</span></span> 


## <a name="create-a-kanban-quantity-calculation-policy"></a><span data-ttu-id="89f00-108">Créer une stratégie de calcul de quantité de kanban</span><span class="sxs-lookup"><span data-stu-id="89f00-108">Create a kanban quantity calculation policy</span></span>
1. <span data-ttu-id="89f00-109">Accédez à Contrôle de la production > Tâches périodiques > Calcul de quantité de kanban > Stratégies de calcul de quantité de kanban.</span><span class="sxs-lookup"><span data-stu-id="89f00-109">Go to Production control > Periodic tasks > Kanban quantity calculation > Kanban quantity calculation policies.</span></span>
2. <span data-ttu-id="89f00-110">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="89f00-110">Click New.</span></span>
3. <span data-ttu-id="89f00-111">Tapez une valeur dans le champ Nom.</span><span class="sxs-lookup"><span data-stu-id="89f00-111">In the Name field, type a value.</span></span>
    * <span data-ttu-id="89f00-112">Par exemple, tapez Speaker2016.</span><span class="sxs-lookup"><span data-stu-id="89f00-112">For example, type Speaker2016.</span></span>  
4. <span data-ttu-id="89f00-113">Dans le champ Plan général, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="89f00-113">In the Master plan field, click the drop-down button to open the lookup.</span></span>
5. <span data-ttu-id="89f00-114">Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="89f00-114">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="89f00-115">Sélectionnez StaticPlan pour calculer la demande.</span><span class="sxs-lookup"><span data-stu-id="89f00-115">Select StaticPlan to calculate demand.</span></span>  
6. <span data-ttu-id="89f00-116">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="89f00-116">In the list, click the link in the selected row.</span></span>
7. <span data-ttu-id="89f00-117">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="89f00-117">Click Save.</span></span>
8. <span data-ttu-id="89f00-118">Entrez 1 dans le champ Quantité de kanban minimale.</span><span class="sxs-lookup"><span data-stu-id="89f00-118">In the Minimum kanban quantity field, enter '1'.</span></span>
    * <span data-ttu-id="89f00-119">Il s'agit du nombre de kanbans supplémentaires inclus au calcul de la quantité de kanban.</span><span class="sxs-lookup"><span data-stu-id="89f00-119">This is the additional number of kanbans that is included in the kanban quantity calculation.</span></span>  
9. <span data-ttu-id="89f00-120">Définissez le facteur de sécurité sur 1.</span><span class="sxs-lookup"><span data-stu-id="89f00-120">Set Safety factor to '1'.</span></span>
    * <span data-ttu-id="89f00-121">Il s'agit du facteur utilisé pour calculer la quantité de stock de sécurité supplémentaire.</span><span class="sxs-lookup"><span data-stu-id="89f00-121">This is the factor that is used to calculate additional quantity of safety stock.</span></span>  
10. <span data-ttu-id="89f00-122">Entrez 30 dans le champ Jours restants.</span><span class="sxs-lookup"><span data-stu-id="89f00-122">In the Days ahead field, enter '30'.</span></span>
    * <span data-ttu-id="89f00-123">Il s'agit du nombre de jours précédant la date de calcul de la quantité de kanban à laquelle la demande est incluse dans le calcul.</span><span class="sxs-lookup"><span data-stu-id="89f00-123">This is the number of days prior to the kanban quantity calculation date that is included in the demand calculation.</span></span>  
11. <span data-ttu-id="89f00-124">Entrez 30 dans le champ Jours passés.</span><span class="sxs-lookup"><span data-stu-id="89f00-124">In the Days behind field, enter '30'.</span></span>
    * <span data-ttu-id="89f00-125">Il s'agit du nombre de jours restants à partir de la date de calcul de la quantité de kanban à laquelle la demande sera incluse dans le calcul</span><span class="sxs-lookup"><span data-stu-id="89f00-125">This is the number of days forward from the kanban quantity calculation date that is included in the demand calculation.</span></span>  <span data-ttu-id="89f00-126">La formule utilisée pour le calcul est désignée par les valeurs actuelles.</span><span class="sxs-lookup"><span data-stu-id="89f00-126">The formula used for the calculation is shown with the actual values.</span></span> <span data-ttu-id="89f00-127">Par exemple, quantité de kanban = ((Demande quotidienne moyenne x délai x 2,00) / Quantité de produits par unité de manutention) + 1</span><span class="sxs-lookup"><span data-stu-id="89f00-127">For example,  Kanban quantity = ((Average daily demand x lead time x 2.00) / Product quantity per handling unit) + 1</span></span>  
12. <span data-ttu-id="89f00-128">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="89f00-128">Close the page.</span></span>

## <a name="add-the-kanban-quantity-calculation-policy-to-a-kanban-rule"></a><span data-ttu-id="89f00-129">Ajouter une stratégie de calcul de quantité de kanban à la règle de kanban</span><span class="sxs-lookup"><span data-stu-id="89f00-129">Add the kanban quantity calculation policy to a kanban rule</span></span>
1. <span data-ttu-id="89f00-130">Accédez à Gestion des informations sur les produits > Lean manufacturing > Règles de kanban.</span><span class="sxs-lookup"><span data-stu-id="89f00-130">Go to Product information management > Lean manufacturing > Kanban rules.</span></span>
2. <span data-ttu-id="89f00-131">Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="89f00-131">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="89f00-132">Sélectionnez la règle de kanban 000020 pour cette procédure.</span><span class="sxs-lookup"><span data-stu-id="89f00-132">Select kanban rule 000020 for this procedure.</span></span>  
3. <span data-ttu-id="89f00-133">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="89f00-133">In the list, click the link in the selected row.</span></span>
4. <span data-ttu-id="89f00-134">Activez ou désactivez l'extension de la section Stratégies de calcul de quantité de kanban.</span><span class="sxs-lookup"><span data-stu-id="89f00-134">Toggle the expansion of the Kanban quantity calculation policies section.</span></span>
5. <span data-ttu-id="89f00-135">Cliquez sur Ajouter.</span><span class="sxs-lookup"><span data-stu-id="89f00-135">Click Add.</span></span>
    * <span data-ttu-id="89f00-136">Ajoutez la stratégie de calcul de quantité de kanban que vous venez de créer dans la sous-tâche précédente.</span><span class="sxs-lookup"><span data-stu-id="89f00-136">Add the kanban quantity calculation policy that you have just created in the previous sub-task.</span></span>  
6. <span data-ttu-id="89f00-137">Dans la liste, marquez la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="89f00-137">In the list, mark the selected row.</span></span>
7. <span data-ttu-id="89f00-138">Dans le champ Nom, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="89f00-138">In the Name field, click the drop-down button to open the lookup.</span></span>
8. <span data-ttu-id="89f00-139">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="89f00-139">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="89f00-140">Sélectionnez la stratégie Speaker2016 que vous venez de créer dans la sous-tâche précédente.</span><span class="sxs-lookup"><span data-stu-id="89f00-140">Select the policy Speaker2016 that you have just created in the previous sub-task.</span></span>  

