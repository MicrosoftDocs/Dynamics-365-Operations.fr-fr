---
title: Origine des besoins au plus juste pour les commandes client
description: Cette procédure traite de la validation de l’arborescence d’origine des besoins d’une ligne de vente où l’article est produit avec des kanbans.
author: ChristianRytt
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SalesTableListPage, SalesCreateOrder, SalesTable, LeanPeggingTree
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: a6a18d24be85e20a7e5824c334855aa94fe61cb5
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5245970"
---
# <a name="lean-pegging-from-sales-orders"></a><span data-ttu-id="a89cf-103">Origine des besoins au plus juste pour les commandes client</span><span class="sxs-lookup"><span data-stu-id="a89cf-103">Lean pegging from sales orders</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="a89cf-104">Cette procédure traite de la validation de l’arborescence d’origine des besoins d’une ligne de vente où l’article est produit avec des kanbans.</span><span class="sxs-lookup"><span data-stu-id="a89cf-104">This procedure focuses on validating the pegging tree from a sales line where the item is produced with kanbans.</span></span> <span data-ttu-id="a89cf-105">Après la validation de l’arborescence d’origine des besoins, toutes les tâches de kanban sont planifiées.</span><span class="sxs-lookup"><span data-stu-id="a89cf-105">After validating the pegging tree, all the kanban jobs are planned.</span></span> <span data-ttu-id="a89cf-106">Cela est utile pour les scénarios de commande dans lesquels le responsable de la commande doit vérifier que la production peut démarrer immédiatement.</span><span class="sxs-lookup"><span data-stu-id="a89cf-106">This is useful for order scenarios where the order taker needs to ensure that production can start right away.</span></span> <span data-ttu-id="a89cf-107">Les données fictives utilisées pour créer cette procédure correspondent à la société USMF.</span><span class="sxs-lookup"><span data-stu-id="a89cf-107">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="a89cf-108">Cette procédure est destinée au responsable avancé des commandes travaillant pour une société fonctionnant selon le concept « au plus juste ».</span><span class="sxs-lookup"><span data-stu-id="a89cf-108">This procedure is intended for the advanced order taker working in a lean company.</span></span>


## <a name="create-a-sales-order-for-a-kanban-controlled-item"></a><span data-ttu-id="a89cf-109">Créer une commande client pour un article contrôlé par kanban</span><span class="sxs-lookup"><span data-stu-id="a89cf-109">Create a sales order for a kanban controlled item</span></span>
1. <span data-ttu-id="a89cf-110">Allez dans Toutes les commandes client.</span><span class="sxs-lookup"><span data-stu-id="a89cf-110">Go to All sales orders.</span></span>
2. <span data-ttu-id="a89cf-111">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="a89cf-111">Click New.</span></span>
3. <span data-ttu-id="a89cf-112">Entrez ou sélectionnez une valeur dans le champ Compte client.</span><span class="sxs-lookup"><span data-stu-id="a89cf-112">In the Customer account field, enter or select a value.</span></span>
    * <span data-ttu-id="a89cf-113">Utilisez US-001.</span><span class="sxs-lookup"><span data-stu-id="a89cf-113">Use US-001.</span></span>  
4. <span data-ttu-id="a89cf-114">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="a89cf-114">Click OK.</span></span>
5. <span data-ttu-id="a89cf-115">Entrez « L0001 » dans le champ Numéro d’article.</span><span class="sxs-lookup"><span data-stu-id="a89cf-115">In the Item number field, type 'L0001'.</span></span>
6. <span data-ttu-id="a89cf-116">Définir la Quantité sur « 30 ».</span><span class="sxs-lookup"><span data-stu-id="a89cf-116">Set Quantity to '30'.</span></span>
    * <span data-ttu-id="a89cf-117">Il est important que la quantité soit supérieure à 24 afin de déclencher la règle de kanban d’événement.</span><span class="sxs-lookup"><span data-stu-id="a89cf-117">It is important that the quantity is higher than 24 in order to trigger the event kanban rule.</span></span>  

## <a name="open-a-pegging-tree"></a><span data-ttu-id="a89cf-118">Ouvrir une arborescence d’origine des besoins</span><span class="sxs-lookup"><span data-stu-id="a89cf-118">Open a pegging tree</span></span> 
1. <span data-ttu-id="a89cf-119">Cliquez sur Produit et approvisionnement.</span><span class="sxs-lookup"><span data-stu-id="a89cf-119">Click Product and supply.</span></span>
2. <span data-ttu-id="a89cf-120">Cliquez sur Afficher l’arborescence d’origine des besoins.</span><span class="sxs-lookup"><span data-stu-id="a89cf-120">Click View pegging tree.</span></span>
    * <span data-ttu-id="a89cf-121">Notez que l’arborescence d’origine des besoins affiche tous les niveaux de l’origine des besoins nécessaire pour la ligne de commande client.</span><span class="sxs-lookup"><span data-stu-id="a89cf-121">Notice that the pegging tree shows all levels of the pegging needed for the sales order line.</span></span> <span data-ttu-id="a89cf-122">Dans ce cas, il existe deux niveaux de kanbans et de tous les composants nécessaires.</span><span class="sxs-lookup"><span data-stu-id="a89cf-122">In this case, there are two levels of kanbans and all the required components.</span></span>  

## <a name="plan-the-pegging-tree"></a><span data-ttu-id="a89cf-123">Planifier l’arborescence de l’origine des besoins</span><span class="sxs-lookup"><span data-stu-id="a89cf-123">Plan the pegging tree</span></span>
1. <span data-ttu-id="a89cf-124">Dans l’arborescence, sélectionnez « Ligne de vente 000832\Kanban 000558 ».</span><span class="sxs-lookup"><span data-stu-id="a89cf-124">In the tree, select 'Sales line 000832\Kanban 000558'.</span></span>
2. <span data-ttu-id="a89cf-125">Développez la section Tâches de kanban.</span><span class="sxs-lookup"><span data-stu-id="a89cf-125">Expand the Kanban jobs section.</span></span>
    * <span data-ttu-id="a89cf-126">Notez que le statut de la tâche de kanban est Non planifiée.</span><span class="sxs-lookup"><span data-stu-id="a89cf-126">Notice that the job status for the kanban job is Not planned.</span></span>  
3. <span data-ttu-id="a89cf-127">Cliquez sur Planifier l’ensemble de l’arborescence des événements de l’origine des besoins.</span><span class="sxs-lookup"><span data-stu-id="a89cf-127">Click Plan entire pegging tree.</span></span>
    * <span data-ttu-id="a89cf-128">Cela planifiera toutes les tâches de kanban dans l’arborescence d’origine des besoins, modifiant le statut de la tâche de Non planifiée à Planifiée.</span><span class="sxs-lookup"><span data-stu-id="a89cf-128">This will plan all kanban jobs in the pegging tree, changing the Job status from Not planned to Planned.</span></span>  
4. <span data-ttu-id="a89cf-129">Actualisez la page.</span><span class="sxs-lookup"><span data-stu-id="a89cf-129">Refresh the page.</span></span>
    * <span data-ttu-id="a89cf-130">Notez que le statut de la tâche de kanban est passé de Non planifiée à Planifiée.</span><span class="sxs-lookup"><span data-stu-id="a89cf-130">Notice that the kanban Job status changed from Not planned to Planned.</span></span>  
5. <span data-ttu-id="a89cf-131">Dans l’arborescence, sélectionnez « Ligne de vente 000832\Kanban 000558\Stock en sortie pour L0001\Kanban 000559 ».</span><span class="sxs-lookup"><span data-stu-id="a89cf-131">In the tree, select 'Sales line 000832\Kanban 000558\Issue for L0001\Kanban 000559'.</span></span>
    * <span data-ttu-id="a89cf-132">La tâche pour le deuxième kanban est également planifiée, car l’intégralité de l’arborescence d’origine des besoins est planifiée.</span><span class="sxs-lookup"><span data-stu-id="a89cf-132">The job for the second kanban is also planned, because the entire pegging tree is planned.</span></span> <span data-ttu-id="a89cf-133">Notez que le statut de la tâche de kanban est passé de Non planifiée à Planifiée.</span><span class="sxs-lookup"><span data-stu-id="a89cf-133">Notice that the kanban job status is changed from Not planned to Planned.</span></span>  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]