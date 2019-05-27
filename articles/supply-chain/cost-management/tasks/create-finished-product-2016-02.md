---
title: Créer un produit fini (février 2016 uniquement)
description: Cette tâche consiste à créer un produit fini.
author: ShylaThompson
manager: AnnBe
ms.date: 02/07/2017
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 44f9693e04160ffe9307de5e454d8269ca883679
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/15/2019
ms.locfileid: "1570855"
---
# <a name="create-a-finished-product-february-2016-only"></a><span data-ttu-id="d63bb-103">Créer un produit fini (février 2016 uniquement)</span><span class="sxs-lookup"><span data-stu-id="d63bb-103">Create a finished product (February 2016 only)</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="d63bb-104">Cette tâche consiste à créer un produit fini.</span><span class="sxs-lookup"><span data-stu-id="d63bb-104">This task focuses on creating a finished product.</span></span> <span data-ttu-id="d63bb-105">Il s'agit de la première tâche dans la série de calculs des nomenclatures.</span><span class="sxs-lookup"><span data-stu-id="d63bb-105">It is the first task in the BOM calculation series.</span></span> <span data-ttu-id="d63bb-106">Les données fictives utilisées pour créer cette tâche correspondent à la société USMF.</span><span class="sxs-lookup"><span data-stu-id="d63bb-106">The demo data company used to create this task is USMF.</span></span>

1. <span data-ttu-id="d63bb-107">Allez à Gestion des informations sur les produits > Produits > Produits lancés.</span><span class="sxs-lookup"><span data-stu-id="d63bb-107">Go to Product information management > Products > Released products.</span></span>
2. <span data-ttu-id="d63bb-108">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="d63bb-108">Click New.</span></span>
3. <span data-ttu-id="d63bb-109">Dans le champ Numéro du produit, saisissez une valeur.</span><span class="sxs-lookup"><span data-stu-id="d63bb-109">In the Product number field, type a value.</span></span>
    * <span data-ttu-id="d63bb-110">Pour la démonstration, entrez BOM_1.</span><span class="sxs-lookup"><span data-stu-id="d63bb-110">For the demonstration, type BOM_1.</span></span>  
4. <span data-ttu-id="d63bb-111">Saisissez ou sélectionnez une valeur dans le champ Groupe de modèles d'article.</span><span class="sxs-lookup"><span data-stu-id="d63bb-111">In the Item model group field, enter or select a value.</span></span>
    * <span data-ttu-id="d63bb-112">Sélectionnez STD.</span><span class="sxs-lookup"><span data-stu-id="d63bb-112">Select STD.</span></span> <span data-ttu-id="d63bb-113">STD représente le coût standard et est le modèle le plus fréquemment utilisé lors de l'utilisation des calculs de coûts.</span><span class="sxs-lookup"><span data-stu-id="d63bb-113">STD stands for standard cost and is the most commonly used model when working with cost calculations.</span></span>  
5. <span data-ttu-id="d63bb-114">Dans le champ Groupe d'articles, entrez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="d63bb-114">In the Item group field, enter or select a value.</span></span>
    * <span data-ttu-id="d63bb-115">Par exemple, sélectionnez Audio.</span><span class="sxs-lookup"><span data-stu-id="d63bb-115">For example, select Audio.</span></span> <span data-ttu-id="d63bb-116">Cela n'a aucun impact sur les calculs de coûts.</span><span class="sxs-lookup"><span data-stu-id="d63bb-116">This has no impact on cost calculations.</span></span>  
6. <span data-ttu-id="d63bb-117">Saisissez ou sélectionnez une valeur dans le champ Groupe de dimension de stockage.</span><span class="sxs-lookup"><span data-stu-id="d63bb-117">In the Storage dimension group field, enter or select a value.</span></span>
    * <span data-ttu-id="d63bb-118">Sélectionnez SiteWH.</span><span class="sxs-lookup"><span data-stu-id="d63bb-118">Select SiteWH.</span></span> <span data-ttu-id="d63bb-119">Seul Site et entrepôt sera utilisé pour la démonstration.</span><span class="sxs-lookup"><span data-stu-id="d63bb-119">Only Site and Warehouse will be used for the demonstration.</span></span>  
7. <span data-ttu-id="d63bb-120">Saisissez ou sélectionnez une valeur dans le champ Groupe de dimension de suivi.</span><span class="sxs-lookup"><span data-stu-id="d63bb-120">In the Tracking dimension group field, enter or select a value.</span></span>
    * <span data-ttu-id="d63bb-121">Les dimensions de suivi ne seront pas utilisées pour cet exemple, sélectionnez Aucun.</span><span class="sxs-lookup"><span data-stu-id="d63bb-121">Tracking dimensions will not be used for this example, select None.</span></span>  
8. <span data-ttu-id="d63bb-122">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="d63bb-122">Click OK.</span></span>
9. <span data-ttu-id="d63bb-123">Dans le volet Actions, cliquez sur Gérer le stock.</span><span class="sxs-lookup"><span data-stu-id="d63bb-123">On the Action Pane, click Manage inventory.</span></span>
10. <span data-ttu-id="d63bb-124">Cliquez sur Paramètres de commande par défaut.</span><span class="sxs-lookup"><span data-stu-id="d63bb-124">Click Default order settings.</span></span>
11. <span data-ttu-id="d63bb-125">Dans le champ Type de commande par défaut, sélectionnez Production.</span><span class="sxs-lookup"><span data-stu-id="d63bb-125">In the Default order type field, select 'Production'.</span></span>
    * <span data-ttu-id="d63bb-126">Comme c'est un produit fini qui sera produit, sélectionnez Production.</span><span class="sxs-lookup"><span data-stu-id="d63bb-126">Because this is a finished product that will be produced, select Production.</span></span>  
12. <span data-ttu-id="d63bb-127">Dans le champ Site d'achat, saisissez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="d63bb-127">In the Purchase site field, enter or select a value.</span></span>
    * <span data-ttu-id="d63bb-128">Pour la démonstration, sélectionnez Site 1.</span><span class="sxs-lookup"><span data-stu-id="d63bb-128">For the demonstration, select Site 1.</span></span>  
13. <span data-ttu-id="d63bb-129">Dans le champ Site de stock, saisissez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="d63bb-129">In the Inventory site field, enter or select a value.</span></span>
    * <span data-ttu-id="d63bb-130">Pour cet exemple, sélectionnez Site 1.</span><span class="sxs-lookup"><span data-stu-id="d63bb-130">For this example, select Site 1.</span></span>  
14. <span data-ttu-id="d63bb-131">Dans le champ Site de vente, entrez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="d63bb-131">In the Sales site field, enter or select a value.</span></span>
    * <span data-ttu-id="d63bb-132">Pour cet exemple, sélectionnez Site 1.</span><span class="sxs-lookup"><span data-stu-id="d63bb-132">For this example, select Site 1.</span></span>  
15. <span data-ttu-id="d63bb-133">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="d63bb-133">Close the page.</span></span>

