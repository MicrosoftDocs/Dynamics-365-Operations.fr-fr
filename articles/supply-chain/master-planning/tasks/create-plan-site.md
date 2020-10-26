---
title: Créer un plan pour un site
description: Le gestionnaire de production calcule les besoins en matériaux et en capacité pour la production d'un article spécifique.
author: ShylaThompson
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: DefaultDashboard, ReqCreatePlanWorkspace, ReqTransPlanCard, ReqTransPOUrgentFormPart, SysQueryForm
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 52721d948554d4853f9e1d4dec45e45e619a4829
ms.sourcegitcommit: 708ca25687a4e48271cdcd6d2d22d99fb94cf140
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/10/2020
ms.locfileid: "3985679"
---
# <a name="create-a-plan-for-a-site"></a><span data-ttu-id="cbac8-103">Créer un plan pour un site</span><span class="sxs-lookup"><span data-stu-id="cbac8-103">Create a plan for a site</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="cbac8-104">Le gestionnaire de production calcule les besoins en matériaux et en capacité pour la production d'un article spécifique.</span><span class="sxs-lookup"><span data-stu-id="cbac8-104">The production planner calculates the material and capacity requirements for the production of a specific item.</span></span> <span data-ttu-id="cbac8-105">Une fois les suggestions d'approvisionnement créées, il recherche les commandes sur le site pour lequel il effectue la planification et confirme les commandes, en commençant par celles qui sont urgentes.</span><span class="sxs-lookup"><span data-stu-id="cbac8-105">After the sourcing suggestions are created, he finds the orders at the site for which he is planning and firms the orders, starting from the urgent ones.</span></span> <span data-ttu-id="cbac8-106">Les commandes les plus urgentes sont celles qui doivent être confirmées à la date actuelle.</span><span class="sxs-lookup"><span data-stu-id="cbac8-106">The most urgent orders are the ones that need to be firmed on the current date.</span></span> <span data-ttu-id="cbac8-107">Utilisez les données fictives de société USMF pour effectuer ces tâches.</span><span class="sxs-lookup"><span data-stu-id="cbac8-107">Use the demo data company USMF to perform these tasks.</span></span>


## <a name="create-a-materials-and-capacity-plan-for-an-item"></a><span data-ttu-id="cbac8-108">Créer un plan pour les matériaux et la capacité pour un article</span><span class="sxs-lookup"><span data-stu-id="cbac8-108">Create a materials and capacity plan for an item</span></span>
1. <span data-ttu-id="cbac8-109">Cliquez sur Planification.</span><span class="sxs-lookup"><span data-stu-id="cbac8-109">Click Master planning.</span></span>
    * <span data-ttu-id="cbac8-110">Vous devez accéder au tableau de bord par défaut.</span><span class="sxs-lookup"><span data-stu-id="cbac8-110">You need to navigate to the default Dashboard.</span></span>  
2. <span data-ttu-id="cbac8-111">Cliquez sur Exécuter.</span><span class="sxs-lookup"><span data-stu-id="cbac8-111">Click Run.</span></span>
3. <span data-ttu-id="cbac8-112">Développez les enregistrements pour inclure la section.</span><span class="sxs-lookup"><span data-stu-id="cbac8-112">Expand the Records to include section.</span></span>
4. <span data-ttu-id="cbac8-113">Cliquez sur Filtre.</span><span class="sxs-lookup"><span data-stu-id="cbac8-113">Click Filter.</span></span>
5. <span data-ttu-id="cbac8-114">Dans la liste, marquez la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="cbac8-114">In the list, mark the selected row.</span></span>
6. <span data-ttu-id="cbac8-115">Tapez une valeur dans le champ Critères.</span><span class="sxs-lookup"><span data-stu-id="cbac8-115">In the Criteria field, type a value.</span></span>
    * <span data-ttu-id="cbac8-116">Exemple : D0001</span><span class="sxs-lookup"><span data-stu-id="cbac8-116">Example: D0001</span></span>  
7. <span data-ttu-id="cbac8-117">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="cbac8-117">Click OK.</span></span>
8. <span data-ttu-id="cbac8-118">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="cbac8-118">Click OK.</span></span>
    * <span data-ttu-id="cbac8-119">Ce processus peut prendre quelques minutes.</span><span class="sxs-lookup"><span data-stu-id="cbac8-119">This may take a few minutes.</span></span>  
9. <span data-ttu-id="cbac8-120">Actualisez la page.</span><span class="sxs-lookup"><span data-stu-id="cbac8-120">Refresh the page.</span></span>

## <a name="identify-the-urgent-planned-orders-for-the-item"></a><span data-ttu-id="cbac8-121">Identifier les ordres prévisionnels urgents pour l'article</span><span class="sxs-lookup"><span data-stu-id="cbac8-121">Identify the urgent planned orders for the item</span></span>
1. <span data-ttu-id="cbac8-122">Ouvrez le filtre de la colonne Numéro d'article.</span><span class="sxs-lookup"><span data-stu-id="cbac8-122">Open Item number column filter.</span></span>
2. <span data-ttu-id="cbac8-123">Appliquez un filtre sur le champ Numéro d'article, avec la valeur D0001, à l'aide de l'opérateur de filtre commence par.</span><span class="sxs-lookup"><span data-stu-id="cbac8-123">Apply a filter on the "Item number" field, with a value of "D0001", using the "begins with" filter operator.</span></span>
3. <span data-ttu-id="cbac8-124">Ouvrez le filtre de la colonne Date de commande.</span><span class="sxs-lookup"><span data-stu-id="cbac8-124">Open Order date column filter.</span></span>
4. <span data-ttu-id="cbac8-125">Appliquez un filtre sur le champ « Date de commande » avec une valeur de date du jour, à l'aide de l'opérateur de filtre « est exactement ».</span><span class="sxs-lookup"><span data-stu-id="cbac8-125">Apply a filter on the "Order date" field, with a value of current date, using the "is exactly" filter operator.</span></span>

## <a name="firm-all-the-urgent-orders-for-the-item"></a><span data-ttu-id="cbac8-126">Confirmer les ordres urgents pour l'article</span><span class="sxs-lookup"><span data-stu-id="cbac8-126">Firm all the urgent orders for the item</span></span>
1. <span data-ttu-id="cbac8-127">Dans la liste, cochez ou décochez toutes les lignes.</span><span class="sxs-lookup"><span data-stu-id="cbac8-127">In the list, mark or unmark all rows.</span></span>
2. <span data-ttu-id="cbac8-128">Cliquez sur Confirmer.</span><span class="sxs-lookup"><span data-stu-id="cbac8-128">Click Firm.</span></span>
3. <span data-ttu-id="cbac8-129">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="cbac8-129">Click OK.</span></span>

