---
title: Créer un produit fini (février 2016)
description: Cette tâche consiste à créer un produit fini.
author: ShylaThompson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EcoResProductDetailsExtended, EcoResProductCreate, InventItemOrderSetup
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 44b3bf17c69f37e7a96c75345a3e4f27ba9eab50
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/29/2019
ms.locfileid: "349720"
---
# <a name="create-a-finished-product-february-2016"></a><span data-ttu-id="4827e-103">Créer un produit fini (février 2016)</span><span class="sxs-lookup"><span data-stu-id="4827e-103">Create a finished product (February 2016)</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="4827e-104">Cette tâche consiste à créer un produit fini.</span><span class="sxs-lookup"><span data-stu-id="4827e-104">This task focuses on creating a finished product.</span></span> <span data-ttu-id="4827e-105">Il s'agit de la première tâche dans la série de calculs des nomenclatures.</span><span class="sxs-lookup"><span data-stu-id="4827e-105">It is the first task in the BOM calculation series.</span></span> <span data-ttu-id="4827e-106">Les données fictives utilisées pour créer cette tâche correspondent à la société USMF.</span><span class="sxs-lookup"><span data-stu-id="4827e-106">The demo data company used to create this task is USMF.</span></span>

1. <span data-ttu-id="4827e-107">Allez à Gestion des informations sur les produits > Produits > Produits lancés.</span><span class="sxs-lookup"><span data-stu-id="4827e-107">Go to Product information management > Products > Released products.</span></span>
2. <span data-ttu-id="4827e-108">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="4827e-108">Click New.</span></span>
3. <span data-ttu-id="4827e-109">Dans le champ Numéro du produit, saisissez une valeur.</span><span class="sxs-lookup"><span data-stu-id="4827e-109">In the Product number field, type a value.</span></span>
    * <span data-ttu-id="4827e-110">Pour la démonstration, entrez BOM_1.</span><span class="sxs-lookup"><span data-stu-id="4827e-110">For the demonstration, type BOM_1.</span></span>  
4. <span data-ttu-id="4827e-111">Saisissez ou sélectionnez une valeur dans le champ Groupe de modèles d'article.</span><span class="sxs-lookup"><span data-stu-id="4827e-111">In the Item model group field, enter or select a value.</span></span>
    * <span data-ttu-id="4827e-112">Sélectionnez STD.</span><span class="sxs-lookup"><span data-stu-id="4827e-112">Select STD.</span></span> <span data-ttu-id="4827e-113">STD représente le coût standard et est le modèle le plus fréquemment utilisé lors de l'utilisation des calculs de coûts.</span><span class="sxs-lookup"><span data-stu-id="4827e-113">STD stands for standard cost and is the most commonly used model when working with cost calculations.</span></span>  
5. <span data-ttu-id="4827e-114">Dans le champ Groupe d'articles, entrez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="4827e-114">In the Item group field, enter or select a value.</span></span>
    * <span data-ttu-id="4827e-115">Par exemple, sélectionnez Audio.</span><span class="sxs-lookup"><span data-stu-id="4827e-115">For example, select Audio.</span></span> <span data-ttu-id="4827e-116">Cela n'a aucun impact sur les calculs de coûts.</span><span class="sxs-lookup"><span data-stu-id="4827e-116">This has no impact on cost calculations.</span></span>  
6. <span data-ttu-id="4827e-117">Saisissez ou sélectionnez une valeur dans le champ Groupe de dimension de stockage.</span><span class="sxs-lookup"><span data-stu-id="4827e-117">In the Storage dimension group field, enter or select a value.</span></span>
    * <span data-ttu-id="4827e-118">Sélectionnez SiteWH.</span><span class="sxs-lookup"><span data-stu-id="4827e-118">Select SiteWH.</span></span> <span data-ttu-id="4827e-119">Seul Site et entrepôt sera utilisé pour la démonstration.</span><span class="sxs-lookup"><span data-stu-id="4827e-119">Only Site and Warehouse will be used for the demonstration.</span></span>  
7. <span data-ttu-id="4827e-120">Saisissez ou sélectionnez une valeur dans le champ Groupe de dimension de suivi.</span><span class="sxs-lookup"><span data-stu-id="4827e-120">In the Tracking dimension group field, enter or select a value.</span></span>
    * <span data-ttu-id="4827e-121">Les dimensions de suivi ne seront pas utilisées pour cet exemple, sélectionnez Aucun.</span><span class="sxs-lookup"><span data-stu-id="4827e-121">Tracking dimensions will not be used for this example, select None.</span></span>  
8. <span data-ttu-id="4827e-122">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="4827e-122">Click OK.</span></span>
9. <span data-ttu-id="4827e-123">Dans le volet Actions, cliquez sur Gérer le stock.</span><span class="sxs-lookup"><span data-stu-id="4827e-123">On the Action Pane, click Manage inventory.</span></span>
10. <span data-ttu-id="4827e-124">Cliquez sur Paramètres de commande par défaut.</span><span class="sxs-lookup"><span data-stu-id="4827e-124">Click Default order settings.</span></span>
11. <span data-ttu-id="4827e-125">Dans le champ Type de commande par défaut, sélectionnez Production.</span><span class="sxs-lookup"><span data-stu-id="4827e-125">In the Default order type field, select 'Production'.</span></span>
    * <span data-ttu-id="4827e-126">Comme c'est un produit fini qui sera produit, sélectionnez Production.</span><span class="sxs-lookup"><span data-stu-id="4827e-126">Because this is a finished product that will be produced, select Production.</span></span>  
12. <span data-ttu-id="4827e-127">Dans le champ Site d'achat, saisissez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="4827e-127">In the Purchase site field, enter or select a value.</span></span>
    * <span data-ttu-id="4827e-128">Pour la démonstration, sélectionnez Site 1.</span><span class="sxs-lookup"><span data-stu-id="4827e-128">For the demonstration, select Site 1.</span></span>  
13. <span data-ttu-id="4827e-129">Dans le champ Site de stock, saisissez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="4827e-129">In the Inventory site field, enter or select a value.</span></span>
    * <span data-ttu-id="4827e-130">Pour cet exemple, sélectionnez Site 1.</span><span class="sxs-lookup"><span data-stu-id="4827e-130">For this example, select Site 1.</span></span>  
14. <span data-ttu-id="4827e-131">Dans le champ Site de vente, entrez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="4827e-131">In the Sales site field, enter or select a value.</span></span>
    * <span data-ttu-id="4827e-132">Pour cet exemple, sélectionnez Site 1.</span><span class="sxs-lookup"><span data-stu-id="4827e-132">For this example, select Site 1.</span></span>  
15. <span data-ttu-id="4827e-133">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="4827e-133">Close the page.</span></span>

