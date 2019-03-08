---
title: Créer une nomenclature de numéro de produit pour les variantes de produit prédéfinies
description: Ce guide décrit comment paramétrer une nomenclature de numéros de produit pour des variantes de produit prédéfinies et comment l'affecter au groupe de dimensions de produit approprié.
author: ShylaThompson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: DefaultDashboard, EcoResProductVariantMaintainWorkspace, EcoResNomenclature, EcoResProductDimensionGroup
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 4b49e96677b94d5f669ea41861f64e62e118938c
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/29/2019
ms.locfileid: "364877"
---
# <a name="create-a-product-number-nomenclature-for-predefined-product-variants"></a><span data-ttu-id="c794c-103">Créer une nomenclature de numéro de produit pour les variantes de produit prédéfinies</span><span class="sxs-lookup"><span data-stu-id="c794c-103">Create a product number nomenclature for predefined product variants</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="c794c-104">Ce guide décrit comment paramétrer une nomenclature de numéros de produit pour des variantes de produit prédéfinies et comment l'affecter au groupe de dimensions de produit approprié.</span><span class="sxs-lookup"><span data-stu-id="c794c-104">This guide shows you how to set up a product number nomenclature for predefined product variants, and how you assign it to the appropriate product dimension group.</span></span> <span data-ttu-id="c794c-105">Les données fictives utilisées pour créer cette procédure correspondent à la société USMF.</span><span class="sxs-lookup"><span data-stu-id="c794c-105">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="c794c-106">La nouvelle nomenclature de numéros de produit est affectée au groupe de dimensions de produit Couleur et Taille.</span><span class="sxs-lookup"><span data-stu-id="c794c-106">The new product number nomenclature is assigned to the Color and Size product dimension group.</span></span> <span data-ttu-id="c794c-107">Cette tâche est généralement effectuée par un concepteur de produit.</span><span class="sxs-lookup"><span data-stu-id="c794c-107">This task would typically be done by a product designer.</span></span>


## <a name="create-a-product-number-nomenclature"></a><span data-ttu-id="c794c-108">Créer une nomenclature de numéros de produit</span><span class="sxs-lookup"><span data-stu-id="c794c-108">Create a product number nomenclature</span></span>
1. <span data-ttu-id="c794c-109">Cliquez sur Définition du modèle de variante de produit.</span><span class="sxs-lookup"><span data-stu-id="c794c-109">Click Product variant model definition.</span></span>
2. <span data-ttu-id="c794c-110">Cliquez sur Nomenclature produit.</span><span class="sxs-lookup"><span data-stu-id="c794c-110">Click Product nomenclature.</span></span>
3. <span data-ttu-id="c794c-111">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="c794c-111">Click New.</span></span>
4. <span data-ttu-id="c794c-112">Dans le champ Nom, entrez un nom de nomenclature qui permet d'identifier le groupe de dimensions de produit cible, par exemple, ColorSize.</span><span class="sxs-lookup"><span data-stu-id="c794c-112">In the Name field, enter a nomenclature name that helps to identify the target product dimension group, for example, ColorSize..</span></span>
5. <span data-ttu-id="c794c-113">Dans le champ Description, entrez une valeur.</span><span class="sxs-lookup"><span data-stu-id="c794c-113">In the Description field, type a value.</span></span>
6. <span data-ttu-id="c794c-114">Cliquez sur Ajouter.</span><span class="sxs-lookup"><span data-stu-id="c794c-114">Click Add.</span></span>
7. <span data-ttu-id="c794c-115">Cliquez sur Numéro du produit générique.</span><span class="sxs-lookup"><span data-stu-id="c794c-115">Click Product master number.</span></span>
8. <span data-ttu-id="c794c-116">Cliquez sur Ajouter.</span><span class="sxs-lookup"><span data-stu-id="c794c-116">Click Add.</span></span>
9. <span data-ttu-id="c794c-117">Cliquez sur Constante de texte.</span><span class="sxs-lookup"><span data-stu-id="c794c-117">Click Text constant.</span></span>
10. <span data-ttu-id="c794c-118">Tapez une valeur dans le champ Texte.</span><span class="sxs-lookup"><span data-stu-id="c794c-118">In the Text field, type a value.</span></span>
11. <span data-ttu-id="c794c-119">Cliquez sur Ajouter.</span><span class="sxs-lookup"><span data-stu-id="c794c-119">Click Add.</span></span>
12. <span data-ttu-id="c794c-120">Cliquez sur Couleur.</span><span class="sxs-lookup"><span data-stu-id="c794c-120">Click Color.</span></span>
13. <span data-ttu-id="c794c-121">Cliquez sur Ajouter.</span><span class="sxs-lookup"><span data-stu-id="c794c-121">Click Add.</span></span>
14. <span data-ttu-id="c794c-122">Cliquez sur Constante de texte.</span><span class="sxs-lookup"><span data-stu-id="c794c-122">Click Text constant.</span></span>
15. <span data-ttu-id="c794c-123">Tapez une valeur dans le champ Texte.</span><span class="sxs-lookup"><span data-stu-id="c794c-123">In the Text field, type a value.</span></span>
16. <span data-ttu-id="c794c-124">Cliquez sur Ajouter.</span><span class="sxs-lookup"><span data-stu-id="c794c-124">Click Add.</span></span>
17. <span data-ttu-id="c794c-125">Cliquez sur Taille.</span><span class="sxs-lookup"><span data-stu-id="c794c-125">Click Size.</span></span>
18. <span data-ttu-id="c794c-126">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="c794c-126">Close the page.</span></span>

## <a name="assign-the-nomenclature-to-a-product-master"></a><span data-ttu-id="c794c-127">Affecter la nomenclature à un produit générique</span><span class="sxs-lookup"><span data-stu-id="c794c-127">Assign the nomenclature to a product master</span></span>
1. <span data-ttu-id="c794c-128">Cliquez sur Groupes de dimensions de produit.</span><span class="sxs-lookup"><span data-stu-id="c794c-128">Click Product dimension groups.</span></span>
2. <span data-ttu-id="c794c-129">Sélectionnez le groupe de dimensions de produit SizeCol.</span><span class="sxs-lookup"><span data-stu-id="c794c-129">Select the SizeCol product dimension group.</span></span>
3. <span data-ttu-id="c794c-130">Cliquez sur Modifier.</span><span class="sxs-lookup"><span data-stu-id="c794c-130">Click Edit.</span></span>
4. <span data-ttu-id="c794c-131">Sélectionnez Oui dans le champ Utiliser la nomenclature.</span><span class="sxs-lookup"><span data-stu-id="c794c-131">Select Yes in the Use nomenclature field.</span></span>
5. <span data-ttu-id="c794c-132">Dans le champ Nomenclature de numéros de variante de produit, entrez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="c794c-132">In the Product variant number nomenclature field, enter or select a value.</span></span>
6. <span data-ttu-id="c794c-133">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="c794c-133">Close the page.</span></span>

