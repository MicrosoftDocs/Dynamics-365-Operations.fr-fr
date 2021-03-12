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
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 16f604d5e06859b15c6f610e7a5c822ef2089ea3
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4966903"
---
# <a name="create-a-default-product-lifecycle-state"></a><span data-ttu-id="e9475-103">Créer un état du cycle de vie des produits par défaut</span><span class="sxs-lookup"><span data-stu-id="e9475-103">Create a default product lifecycle state</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="e9475-104">Cette procédure décrit comment créer un état du cycle de vie des produits par défaut. Elle indique aussi comment associer l'état par défaut à des produits lancés.</span><span class="sxs-lookup"><span data-stu-id="e9475-104">This procedure shows how to create a default product lifecycle state as well as how to associate the default state with released products.</span></span>


## <a name="create-a-default-lifecycle-state"></a><span data-ttu-id="e9475-105">Créer un état du cycle de vie par défaut</span><span class="sxs-lookup"><span data-stu-id="e9475-105">Create a default lifecycle state</span></span>
1. <span data-ttu-id="e9475-106">Accédez à Gestion des informations sur les produits > Paramétrage > État du cycle de vie des produits.</span><span class="sxs-lookup"><span data-stu-id="e9475-106">Go to Product information management > Setup > Product lifecycle state.</span></span>
2. <span data-ttu-id="e9475-107">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="e9475-107">Click New.</span></span>
3. <span data-ttu-id="e9475-108">Dans le champ État, tapez une valeur.</span><span class="sxs-lookup"><span data-stu-id="e9475-108">In the State field, type a value.</span></span>
4. <span data-ttu-id="e9475-109">Sélectionnez Oui dans le champ Valeur par défaut en cas de lancement dans une entité juridique.</span><span class="sxs-lookup"><span data-stu-id="e9475-109">Select Yes in the Default when released to legal entity field.</span></span>
5. <span data-ttu-id="e9475-110">Dans le champ Description, entrez une valeur.</span><span class="sxs-lookup"><span data-stu-id="e9475-110">In the Description field, type a value.</span></span>
6. <span data-ttu-id="e9475-111">Sélectionnez Non dans le champ Est actif pour la planification.</span><span class="sxs-lookup"><span data-stu-id="e9475-111">Select No in the Is active for planning field.</span></span>

> [!NOTE]
> <span data-ttu-id="e9475-112">Si un nouveau produit lancé ne doit pas être inclus dans la planification, sélectionnez Non.</span><span class="sxs-lookup"><span data-stu-id="e9475-112">If a new released product should not be included in Master planning, select No.</span></span> <span data-ttu-id="e9475-113">Dans le cas contraire, laissez le contrôle sur sa valeur par défaut Oui.</span><span class="sxs-lookup"><span data-stu-id="e9475-113">If it should be included in Master planning, leave the control at its default value Yes.</span></span>  

## <a name="create-a-new-released-product"></a><span data-ttu-id="e9475-114">Créer un produit lancé</span><span class="sxs-lookup"><span data-stu-id="e9475-114">Create a new released product</span></span>
1. <span data-ttu-id="e9475-115">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="e9475-115">Close the page.</span></span>
2. <span data-ttu-id="e9475-116">Allez à Gestion des informations sur les produits > Produits > Produits lancés.</span><span class="sxs-lookup"><span data-stu-id="e9475-116">Go to Product information management > Products > Released products.</span></span>
3. <span data-ttu-id="e9475-117">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="e9475-117">Click New.</span></span>
4. <span data-ttu-id="e9475-118">Dans le champ Numéro du produit, saisissez une valeur.</span><span class="sxs-lookup"><span data-stu-id="e9475-118">In the Product number field, type a value.</span></span>
5. <span data-ttu-id="e9475-119">Dans le champ Nom du produit, saisissez une valeur.</span><span class="sxs-lookup"><span data-stu-id="e9475-119">In the Product name field, type a value.</span></span>
6. <span data-ttu-id="e9475-120">Dans le champ Rechercher, tapez une valeur.</span><span class="sxs-lookup"><span data-stu-id="e9475-120">In the Search name field, type a value.</span></span>
7. <span data-ttu-id="e9475-121">Saisissez ou sélectionnez une valeur dans le champ Groupe de modèles d'article.</span><span class="sxs-lookup"><span data-stu-id="e9475-121">In the Item model group field, enter or select a value.</span></span>
8. <span data-ttu-id="e9475-122">Dans le champ Groupe d'articles, entrez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="e9475-122">In the Item group field, enter or select a value.</span></span>
9. <span data-ttu-id="e9475-123">Saisissez ou sélectionnez une valeur dans le champ Groupe de dimension de stockage.</span><span class="sxs-lookup"><span data-stu-id="e9475-123">In the Storage dimension group field, enter or select a value.</span></span>
10. <span data-ttu-id="e9475-124">Saisissez ou sélectionnez une valeur dans le champ Groupe de dimension de suivi.</span><span class="sxs-lookup"><span data-stu-id="e9475-124">In the Tracking dimension group field, enter or select a value.</span></span>
11. <span data-ttu-id="e9475-125">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="e9475-125">Click OK.</span></span>

> [!NOTE]
> <span data-ttu-id="e9475-126">L'état du cycle de vie des produits par défaut est une définition globale.</span><span class="sxs-lookup"><span data-stu-id="e9475-126">The default product lifecycle state is a global definition.</span></span>  

## <a name="change-the-product-to-an-active-state"></a><span data-ttu-id="e9475-127">Modifier le produit sur un état actif</span><span class="sxs-lookup"><span data-stu-id="e9475-127">Change the product to an active state</span></span>
1. <span data-ttu-id="e9475-128">Dans le champ État du cycle de vie des produits, entrez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="e9475-128">In the Product lifecycle state field, enter or select a value.</span></span>

> [!NOTE]
> <span data-ttu-id="e9475-129">Supposons que vous ayez paramétré un état actif, vous pouvez désormais sélectionner l'état actif pour pouvoir utiliser le produit dans la planification et le calcul au niveau de la nomenclature.</span><span class="sxs-lookup"><span data-stu-id="e9475-129">Assume that you have set up an active state, you can now select the active state to allow the product to be used in Master planning and BOM-level calculation.</span></span> <span data-ttu-id="e9475-130">Évidemment, cette utilisation n'a de sens que si tous les détails du produit nécessaires à une planification cohérente sont spécifiés.</span><span class="sxs-lookup"><span data-stu-id="e9475-130">Obviously, this only makes sense if all the product details that are required for consistent planning are specified.</span></span>  

