---
title: Créer un état du cycle de vie des produits par défaut
description: Cette procédure décrit comment créer un état du cycle de vie des produits par défaut. Elle indique aussi comment associer l'état par défaut à des produits lancés.
author: cvocph
manager: tfehr
ms.date: 12/05/2017
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Operations
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 8766208f0dff0cf24db7335ef00c42749811f8fd
ms.sourcegitcommit: 708ca25687a4e48271cdcd6d2d22d99fb94cf140
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/10/2020
ms.locfileid: "3985435"
---
# <a name="create-a-default-product-lifecycle-state"></a><span data-ttu-id="bba99-103">Créer un état du cycle de vie des produits par défaut</span><span class="sxs-lookup"><span data-stu-id="bba99-103">Create a default product lifecycle state</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="bba99-104">Cette procédure décrit comment créer un état du cycle de vie des produits par défaut. Elle indique aussi comment associer l'état par défaut à des produits lancés.</span><span class="sxs-lookup"><span data-stu-id="bba99-104">This procedure shows how to create a default product lifecycle state as well as how to associate the default state with released products.</span></span>


## <a name="create-a-default-lifecycle-state"></a><span data-ttu-id="bba99-105">Créer un état du cycle de vie par défaut</span><span class="sxs-lookup"><span data-stu-id="bba99-105">Create a default lifecycle state</span></span>
1. <span data-ttu-id="bba99-106">Accédez à Gestion des informations sur les produits > Paramétrage > État du cycle de vie des produits.</span><span class="sxs-lookup"><span data-stu-id="bba99-106">Go to Product information management > Setup > Product lifecycle state.</span></span>
2. <span data-ttu-id="bba99-107">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="bba99-107">Click New.</span></span>
3. <span data-ttu-id="bba99-108">Dans le champ État, tapez une valeur.</span><span class="sxs-lookup"><span data-stu-id="bba99-108">In the State field, type a value.</span></span>
4. <span data-ttu-id="bba99-109">Sélectionnez Oui dans le champ Valeur par défaut en cas de lancement dans une entité juridique.</span><span class="sxs-lookup"><span data-stu-id="bba99-109">Select Yes in the Default when released to legal entity field.</span></span>
5. <span data-ttu-id="bba99-110">Dans le champ Description, entrez une valeur.</span><span class="sxs-lookup"><span data-stu-id="bba99-110">In the Description field, type a value.</span></span>
6. <span data-ttu-id="bba99-111">Sélectionnez Non dans le champ Est actif pour la planification.</span><span class="sxs-lookup"><span data-stu-id="bba99-111">Select No in the Is active for planning field.</span></span>

> [!NOTE]
> <span data-ttu-id="bba99-112">Si un nouveau produit lancé ne doit pas être inclus dans la planification, sélectionnez Non.</span><span class="sxs-lookup"><span data-stu-id="bba99-112">If a new released product should not be included in Master planning, select No.</span></span> <span data-ttu-id="bba99-113">Dans le cas contraire, laissez le contrôle sur sa valeur par défaut Oui.</span><span class="sxs-lookup"><span data-stu-id="bba99-113">If it should be included in Master planning, leave the control at its default value Yes.</span></span>  

## <a name="create-a-new-released-product"></a><span data-ttu-id="bba99-114">Créer un produit lancé</span><span class="sxs-lookup"><span data-stu-id="bba99-114">Create a new released product</span></span>
1. <span data-ttu-id="bba99-115">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="bba99-115">Close the page.</span></span>
2. <span data-ttu-id="bba99-116">Allez à Gestion des informations sur les produits > Produits > Produits lancés.</span><span class="sxs-lookup"><span data-stu-id="bba99-116">Go to Product information management > Products > Released products.</span></span>
3. <span data-ttu-id="bba99-117">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="bba99-117">Click New.</span></span>
4. <span data-ttu-id="bba99-118">Dans le champ Numéro du produit, saisissez une valeur.</span><span class="sxs-lookup"><span data-stu-id="bba99-118">In the Product number field, type a value.</span></span>
5. <span data-ttu-id="bba99-119">Dans le champ Nom du produit, saisissez une valeur.</span><span class="sxs-lookup"><span data-stu-id="bba99-119">In the Product name field, type a value.</span></span>
6. <span data-ttu-id="bba99-120">Dans le champ Rechercher, tapez une valeur.</span><span class="sxs-lookup"><span data-stu-id="bba99-120">In the Search name field, type a value.</span></span>
7. <span data-ttu-id="bba99-121">Saisissez ou sélectionnez une valeur dans le champ Groupe de modèles d'article.</span><span class="sxs-lookup"><span data-stu-id="bba99-121">In the Item model group field, enter or select a value.</span></span>
8. <span data-ttu-id="bba99-122">Dans le champ Groupe d'articles, entrez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="bba99-122">In the Item group field, enter or select a value.</span></span>
9. <span data-ttu-id="bba99-123">Saisissez ou sélectionnez une valeur dans le champ Groupe de dimension de stockage.</span><span class="sxs-lookup"><span data-stu-id="bba99-123">In the Storage dimension group field, enter or select a value.</span></span>
10. <span data-ttu-id="bba99-124">Saisissez ou sélectionnez une valeur dans le champ Groupe de dimension de suivi.</span><span class="sxs-lookup"><span data-stu-id="bba99-124">In the Tracking dimension group field, enter or select a value.</span></span>
11. <span data-ttu-id="bba99-125">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="bba99-125">Click OK.</span></span>

> [!NOTE]
> <span data-ttu-id="bba99-126">L'état du cycle de vie des produits par défaut est une définition globale.</span><span class="sxs-lookup"><span data-stu-id="bba99-126">The default product lifecycle state is a global definition.</span></span>  

## <a name="change-the-product-to-an-active-state"></a><span data-ttu-id="bba99-127">Modifier le produit sur un état actif</span><span class="sxs-lookup"><span data-stu-id="bba99-127">Change the product to an active state</span></span>
1. <span data-ttu-id="bba99-128">Dans le champ État du cycle de vie des produits, entrez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="bba99-128">In the Product lifecycle state field, enter or select a value.</span></span>

> [!NOTE]
> <span data-ttu-id="bba99-129">Supposons que vous ayez paramétré un état actif, vous pouvez désormais sélectionner l'état actif pour pouvoir utiliser le produit dans la planification et le calcul au niveau de la nomenclature.</span><span class="sxs-lookup"><span data-stu-id="bba99-129">Assume that you have set up an active state, you can now select the active state to allow the product to be used in Master planning and BOM-level calculation.</span></span> <span data-ttu-id="bba99-130">Évidemment, cette utilisation n'a de sens que si tous les détails du produit nécessaires à une planification cohérente sont spécifiés.</span><span class="sxs-lookup"><span data-stu-id="bba99-130">Obviously, this only makes sense if all the product details that are required for consistent planning are specified.</span></span>  

