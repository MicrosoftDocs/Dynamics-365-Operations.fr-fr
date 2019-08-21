---
title: Créer une règle de kanban de retrait
description: Cette procédure permet d'indiquer le paramétrage nécessaire pour créer une règle de kanban de prélèvement pour transférer les matériaux dans un environnement lean.
author: ChristianRytt
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: KanbanRules, LeanProductionFlowActivityLookup, InventItemIdLookupSimple, UnitOfMeasureLookup, KanbanCreate
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 5d8647a88773b3d4c0193d64307426736d0d085d
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/01/2019
ms.locfileid: "1837756"
---
# <a name="create-a-withdrawal-kanban-rule"></a><span data-ttu-id="fc9cc-103">Créer une règle de kanban de retrait</span><span class="sxs-lookup"><span data-stu-id="fc9cc-103">Create a withdrawal kanban rule</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="fc9cc-104">Cette procédure permet d'indiquer le paramétrage nécessaire pour créer une règle de kanban de prélèvement pour transférer les matériaux dans un environnement lean.</span><span class="sxs-lookup"><span data-stu-id="fc9cc-104">This procedure shows the setup that is needed to create a withdrawal kanban rule for transferring material in a lean environment.</span></span> <span data-ttu-id="fc9cc-105">Les données fictives utilisées pour créer cette procédure correspondent à la société USMF.</span><span class="sxs-lookup"><span data-stu-id="fc9cc-105">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="fc9cc-106">Cette procédure est destinée à l'ingénieur processus ou au responsable de la chaîne de valeur, car ils préparent le réapprovisionnement des matériaux nouveaux ou modifiés.</span><span class="sxs-lookup"><span data-stu-id="fc9cc-106">This procedure is intended for the Process Engineer or the Value Stream Manager, as they prepare replenishment of new or modified material.</span></span>


## <a name="create-new-kanban-rule"></a><span data-ttu-id="fc9cc-107">Créer une règle de kanban</span><span class="sxs-lookup"><span data-stu-id="fc9cc-107">Create new kanban rule</span></span>
1. <span data-ttu-id="fc9cc-108">Accédez aux règles de kanban.</span><span class="sxs-lookup"><span data-stu-id="fc9cc-108">Go to Kanban rules.</span></span>
2. <span data-ttu-id="fc9cc-109">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="fc9cc-109">Click New.</span></span>
3. <span data-ttu-id="fc9cc-110">Sélectionnez Prélèvement dans le champ Type.</span><span class="sxs-lookup"><span data-stu-id="fc9cc-110">In the Type field, select 'Withdrawal'.</span></span>
    * <span data-ttu-id="fc9cc-111">Le type Prélèvement est utilisé pour les règles de kanban pour transférer les matériaux ou les marchandises.</span><span class="sxs-lookup"><span data-stu-id="fc9cc-111">The Withdrawal type is used for kanban rules to transfer material or goods.</span></span>  
4. <span data-ttu-id="fc9cc-112">Entrez ou sélectionnez une valeur dans le champ Première activité de plan.</span><span class="sxs-lookup"><span data-stu-id="fc9cc-112">In the First plan activity field, enter or select a value.</span></span>
    * <span data-ttu-id="fc9cc-113">Sélectionnez ReplenishSpeakerComponents.</span><span class="sxs-lookup"><span data-stu-id="fc9cc-113">Select ReplenishSpeakerComponents.</span></span>   <span data-ttu-id="fc9cc-114">Cette activité est paramétrée pour déplacer les composants de l'entrepôt 11, emplacement 11 vers l'entrepôt 12 et l'emplacement 12.</span><span class="sxs-lookup"><span data-stu-id="fc9cc-114">This activity is set up to move components from warehouse 11, location 11 to warehouse 12, and location 12.</span></span>  
5. <span data-ttu-id="fc9cc-115">Dans le champ Produit, saisissez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="fc9cc-115">In the Product field, enter or select a value.</span></span>
    * <span data-ttu-id="fc9cc-116">Sélectionnez M0007.</span><span class="sxs-lookup"><span data-stu-id="fc9cc-116">Select M0007.</span></span>  
6. <span data-ttu-id="fc9cc-117">Entrez un nombre dans le champ Délai.</span><span class="sxs-lookup"><span data-stu-id="fc9cc-117">In the Lead time field, enter a number.</span></span>
    * <span data-ttu-id="fc9cc-118">Par exemple, 60.</span><span class="sxs-lookup"><span data-stu-id="fc9cc-118">For example, 60.</span></span>  
7. <span data-ttu-id="fc9cc-119">Dans le champ Unité de mesure, saisissez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="fc9cc-119">In the Unit of measure field, enter or select a value.</span></span>
    * <span data-ttu-id="fc9cc-120">Par exemple, Minutes.</span><span class="sxs-lookup"><span data-stu-id="fc9cc-120">For example, Minutes.</span></span>  

## <a name="set-quantities-for-kanban"></a><span data-ttu-id="fc9cc-121">Définir les quantités de kanban</span><span class="sxs-lookup"><span data-stu-id="fc9cc-121">Set quantities for kanban</span></span>
1. <span data-ttu-id="fc9cc-122">Définissez la quantité par défaut sur 5.</span><span class="sxs-lookup"><span data-stu-id="fc9cc-122">Set Default quantity to '5'.</span></span>
    * <span data-ttu-id="fc9cc-123">Il s'agit de la quantité qui sera transférée pour chaque kanban.</span><span class="sxs-lookup"><span data-stu-id="fc9cc-123">This is the quantity that will be transferred for each kanban.</span></span>  
2. <span data-ttu-id="fc9cc-124">Entrez 2 dans le champ Quantité de kanban fixe.</span><span class="sxs-lookup"><span data-stu-id="fc9cc-124">In the Fixed kanban quantity field, enter '2'.</span></span>
    * <span data-ttu-id="fc9cc-125">Il s'agit de la quantité de kanbans qui doivent être actifs.</span><span class="sxs-lookup"><span data-stu-id="fc9cc-125">This is the amount of kanbans that should be active.</span></span> <span data-ttu-id="fc9cc-126">Dans ce cas, 2 kanbans qui transfèrent 5 unités chacun.</span><span class="sxs-lookup"><span data-stu-id="fc9cc-126">In this case, 2 kanbans transferring 5 each.</span></span>  
3. <span data-ttu-id="fc9cc-127">Dans le champ Limite d'alerte minimale, entrez « 1 ».</span><span class="sxs-lookup"><span data-stu-id="fc9cc-127">In the Alert boundary minimum field, enter '1'.</span></span>
    * <span data-ttu-id="fc9cc-128">Permet de tenir à jour la quantité minimale de kanbans complets qui doivent être à la destination.</span><span class="sxs-lookup"><span data-stu-id="fc9cc-128">Used to keep track of the minimum amount of full kanbans that should be at the destination.</span></span> <span data-ttu-id="fc9cc-129">Par exemple, cela sert dans la vue d'ensemble de la quantité de kanban.</span><span class="sxs-lookup"><span data-stu-id="fc9cc-129">For example, this is used on the kanban quantity overview.</span></span>  
4. <span data-ttu-id="fc9cc-130">Dans le champ Limite d'alerte maximale, entrez « 2 ».</span><span class="sxs-lookup"><span data-stu-id="fc9cc-130">In the Alert boundary maximum field, enter '2'.</span></span>
    * <span data-ttu-id="fc9cc-131">Permet de tenir à jour la quantité maximale de kanbans complets qui doivent être à la destination.</span><span class="sxs-lookup"><span data-stu-id="fc9cc-131">Used to keep track of the maximum amount of full kanbans that should be at the destination.</span></span> <span data-ttu-id="fc9cc-132">Par exemple, cela sert dans la vue d'ensemble de la quantité de kanban.</span><span class="sxs-lookup"><span data-stu-id="fc9cc-132">For example, this is used on the kanban quantity overview.</span></span>  

## <a name="create-kanbans"></a><span data-ttu-id="fc9cc-133">Créer des kanbans</span><span class="sxs-lookup"><span data-stu-id="fc9cc-133">Create kanbans</span></span>
1. <span data-ttu-id="fc9cc-134">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="fc9cc-134">Click Save.</span></span>
    * <span data-ttu-id="fc9cc-135">La règle de kanban doit être enregistrée avant que les kanbans puissent être créés.</span><span class="sxs-lookup"><span data-stu-id="fc9cc-135">The kanban rule needs to be saved before kanbans can be created.</span></span>  
2. <span data-ttu-id="fc9cc-136">Cliquez sur Ajouter.</span><span class="sxs-lookup"><span data-stu-id="fc9cc-136">Click Add.</span></span>
    * <span data-ttu-id="fc9cc-137">Notez qu'il n'existe aucun kanban actif, parce que le « Nombre suggéré de nouveaux kanbans » est de 2. Cela est égal à la « quantité fixe de kanban ».</span><span class="sxs-lookup"><span data-stu-id="fc9cc-137">Note that there are no active kanbans because the suggested 'Number of new kanbans' is 2, which is equal to the 'Fixed kanban quantity'.</span></span>  
3. <span data-ttu-id="fc9cc-138">Cliquez sur Créer.</span><span class="sxs-lookup"><span data-stu-id="fc9cc-138">Click Create.</span></span>
    * <span data-ttu-id="fc9cc-139">Cette opération crée deux kanbans.</span><span class="sxs-lookup"><span data-stu-id="fc9cc-139">This will create two kanbans.</span></span>  
    * <span data-ttu-id="fc9cc-140">Notez que 2 kanbans, chacun pour 5 unités, ont été créés pour cette règle de kanban de prélèvement.</span><span class="sxs-lookup"><span data-stu-id="fc9cc-140">Note that 2 kanbans, for 5 each, was created for this withdrawal kanban rule.</span></span>  <span data-ttu-id="fc9cc-141">Il s'agit de la dernière étape de cette procédure.</span><span class="sxs-lookup"><span data-stu-id="fc9cc-141">This is the last step in this procedure.</span></span>  

