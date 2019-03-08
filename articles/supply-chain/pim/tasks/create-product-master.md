---
title: Créer un produit générique
description: Créez un produit générique pour les variantes prédéfinies.
author: ShylaThompson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EcoResProductListPage, EcoResProductCreate, EcoResProductDetails, EcoResProductInventoryDimensionGroups
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 6e34f7c630e872468d888938e0f1aa57f3f0d4c4
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/29/2019
ms.locfileid: "326076"
---
# <a name="create-a-product-master"></a><span data-ttu-id="71139-103">Créer un produit générique</span><span class="sxs-lookup"><span data-stu-id="71139-103">Create a product master</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="71139-104">Créez un produit générique pour les variantes prédéfinies.</span><span class="sxs-lookup"><span data-stu-id="71139-104">Create a product master for the predefined variants.</span></span> <span data-ttu-id="71139-105">Les données fictives utilisées pour créer cette procédure correspondent à la société USMF.</span><span class="sxs-lookup"><span data-stu-id="71139-105">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="71139-106">Cette procédure est destinée au concepteur de produit.</span><span class="sxs-lookup"><span data-stu-id="71139-106">This procedure is intended for the product designer.</span></span>


## <a name="create-a-new-product-master"></a><span data-ttu-id="71139-107">Créer un produit générique</span><span class="sxs-lookup"><span data-stu-id="71139-107">Create a new product master</span></span>
1. <span data-ttu-id="71139-108">Accédez à Gestion des informations sur les produits > Produits > Produits génériques.</span><span class="sxs-lookup"><span data-stu-id="71139-108">Go to Product information management > Products > Product masters.</span></span>
2. <span data-ttu-id="71139-109">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="71139-109">Click New.</span></span>
3. <span data-ttu-id="71139-110">Dans le champ Numéro du produit, saisissez une valeur.</span><span class="sxs-lookup"><span data-stu-id="71139-110">In the Product number field, type a value.</span></span>
    * <span data-ttu-id="71139-111">Le nombre doit être unique.</span><span class="sxs-lookup"><span data-stu-id="71139-111">The number must be unique.</span></span> <span data-ttu-id="71139-112">Il est possible de définir une séquence de nombres pour le champ Numéro du produit.</span><span class="sxs-lookup"><span data-stu-id="71139-112">A number sequence can be set for the Product number field.</span></span> <span data-ttu-id="71139-113">Dans ce cas, il n'est pas nécessaire que l'utilisateur entre de valeur.</span><span class="sxs-lookup"><span data-stu-id="71139-113">In this case, the user doesn't have to enter a value.</span></span>  
4. <span data-ttu-id="71139-114">Dans le champ Nom du produit, saisissez une valeur.</span><span class="sxs-lookup"><span data-stu-id="71139-114">In the Product name field, type a value.</span></span>
    * <span data-ttu-id="71139-115">Saisissez un nom décrivant le produit.</span><span class="sxs-lookup"><span data-stu-id="71139-115">Enter a descriptive product name.</span></span> <span data-ttu-id="71139-116">Par défaut, la valeur utilisée correspond au nom de recherche, mais il peut être modifié par l'utilisateur.</span><span class="sxs-lookup"><span data-stu-id="71139-116">The value defaults to the search name, but this can be changed by the user.</span></span>  
5. <span data-ttu-id="71139-117">Dans le champ Groupe de dimensions de produit, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="71139-117">In the Product dimension group field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="71139-118">Le groupe Dimension du produit détermine les dimensions pouvant être utilisées pour créer des variantes du produit.</span><span class="sxs-lookup"><span data-stu-id="71139-118">The product dimension group determines which of the 4 product dimensions that can be used to create product variants.</span></span> <span data-ttu-id="71139-119">Cet exemple utilise un groupe avec la couleur et la taille.</span><span class="sxs-lookup"><span data-stu-id="71139-119">This example uses a group with color and size.</span></span>  
6. <span data-ttu-id="71139-120">Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="71139-120">In the list, find and select the desired record.</span></span>
7. <span data-ttu-id="71139-121">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="71139-121">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="71139-122">La technologie de configuration par défaut est Variante prédéfinie.</span><span class="sxs-lookup"><span data-stu-id="71139-122">The default configuration technology is Predefined variant.</span></span> <span data-ttu-id="71139-123">Elle est utilisée pour cet exemple.</span><span class="sxs-lookup"><span data-stu-id="71139-123">This will be used for this example.</span></span>  
8. <span data-ttu-id="71139-124">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="71139-124">Click OK.</span></span>

## <a name="select-product-dimension-groups"></a><span data-ttu-id="71139-125">Sélectionner des groupes de dimensions de produit</span><span class="sxs-lookup"><span data-stu-id="71139-125">Select product dimension groups</span></span>
1. <span data-ttu-id="71139-126">Dans le champ Groupe de couleurs, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="71139-126">In the Color group field, click the drop-down button to open the lookup.</span></span>
2. <span data-ttu-id="71139-127">Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="71139-127">In the list, find and select the desired record.</span></span>
3. <span data-ttu-id="71139-128">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="71139-128">In the list, click the link in the selected row.</span></span>
4. <span data-ttu-id="71139-129">Dans le champ Groupe de tailles, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="71139-129">In the Size group field, click the drop-down button to open the lookup.</span></span>
5. <span data-ttu-id="71139-130">Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="71139-130">In the list, find and select the desired record.</span></span>
6. <span data-ttu-id="71139-131">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="71139-131">In the list, click the link in the selected row.</span></span>

## <a name="add-dimension-groups"></a><span data-ttu-id="71139-132">Ajouter des groupes de dimensions</span><span class="sxs-lookup"><span data-stu-id="71139-132">Add dimension groups</span></span>
1. <span data-ttu-id="71139-133">Dans le volet Actions, cliquez sur Produit.</span><span class="sxs-lookup"><span data-stu-id="71139-133">On the Action Pane, click Product.</span></span>
2. <span data-ttu-id="71139-134">Cliquez sur Groupes de dimensions pour ouvrir la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="71139-134">Click Dimension groups to open the drop dialog.</span></span>
3. <span data-ttu-id="71139-135">Dans le champ Groupe de dimensions de stockage, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="71139-135">In the Storage dimension group field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="71139-136">Les dimensions de stockage facilitent le contrôle du mode de stockage et de prélèvement sur le stock.</span><span class="sxs-lookup"><span data-stu-id="71139-136">The storage dimensions help you control how items are stored and taken from inventory.</span></span> <span data-ttu-id="71139-137">Par exemple, une dimension de stockage peut inclure le site et l'entrepôt.</span><span class="sxs-lookup"><span data-stu-id="71139-137">For example, a storage dimension can include Site and Warehouse.</span></span>  
4. <span data-ttu-id="71139-138">Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="71139-138">In the list, find and select the desired record.</span></span>
5. <span data-ttu-id="71139-139">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="71139-139">In the list, click the link in the selected row.</span></span>
6. <span data-ttu-id="71139-140">Dans le champ Groupe de dimensions de suivi, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="71139-140">In the Tracking dimension group field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="71139-141">Le groupe de dimensions de suivi détermine les dimensions de suivi que vous pouvez ajouter à un produit.</span><span class="sxs-lookup"><span data-stu-id="71139-141">The tracking dimension group determines which tracking dimensions you can add to a product.</span></span> <span data-ttu-id="71139-142">Par exemple, le numéro de lot et le numéro de série sont utilisés pour suivre les articles en stock.</span><span class="sxs-lookup"><span data-stu-id="71139-142">For example, the batch number and serial number are used to track inventory items.</span></span>  
7. <span data-ttu-id="71139-143">Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="71139-143">In the list, find and select the desired record.</span></span>
8. <span data-ttu-id="71139-144">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="71139-144">In the list, click the link in the selected row.</span></span>
9. <span data-ttu-id="71139-145">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="71139-145">Click OK.</span></span>
10. <span data-ttu-id="71139-146">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="71139-146">Click Save.</span></span>
11. <span data-ttu-id="71139-147">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="71139-147">Close the page.</span></span>

