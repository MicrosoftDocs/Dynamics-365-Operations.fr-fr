--- 
title: "Créer un numéro de produit pour les variantes de produit prédéfinies"
description: "Ce guide décrit comment paramétrer une nomenclature de numéros de produit pour des variantes de produit prédéfinies et comment l'affecter au groupe de dimensions de produit approprié."
author: BibiSp
manager: AnnBe
ms.date: 11/03/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bis
ms.search.scope: Operations
ms.search.region: Global
ms.author: bis
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 3a1bfd4bd5f396c05277159ac112eaa8197d5818
ms.openlocfilehash: c423aab341ddad9383c4c95b9dbb63c9875c99ef
ms.contentlocale: fr-fr
ms.lasthandoff: 11/06/2017

---
# <a name="create-a-product-number-for-predefined-product-variants"></a><span data-ttu-id="77c70-103">Créer un numéro de produit pour les variantes de produit prédéfinies</span><span class="sxs-lookup"><span data-stu-id="77c70-103">Create a product number for predefined product variants</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="77c70-104">Ce guide décrit comment paramétrer une nomenclature de numéros de produit pour des variantes de produit prédéfinies et comment l'affecter au groupe de dimensions de produit approprié.</span><span class="sxs-lookup"><span data-stu-id="77c70-104">This guide shows you how to set up a product number nomenclature for predefined product variants, and how you assign it to the appropriate product dimension group.</span></span> <span data-ttu-id="77c70-105">Les données fictives utilisées pour créer cette procédure correspondent à la société USMF.</span><span class="sxs-lookup"><span data-stu-id="77c70-105">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="77c70-106">La nouvelle nomenclature de numéros de produit est affectée au groupe de dimensions de produit Couleur et Taille.</span><span class="sxs-lookup"><span data-stu-id="77c70-106">The new product number nomenclature is assigned to the Color and Size product dimension group.</span></span> <span data-ttu-id="77c70-107">Cette tâche est généralement effectuée par un concepteur de produit.</span><span class="sxs-lookup"><span data-stu-id="77c70-107">This task would typically be done by a product designer.</span></span>


## <a name="create-a-product-number-nomenclature"></a><span data-ttu-id="77c70-108">Créer une nomenclature de numéros de produit</span><span class="sxs-lookup"><span data-stu-id="77c70-108">Create a product number nomenclature</span></span>
1. <span data-ttu-id="77c70-109">Cliquez sur Définition du modèle de variante de produit.</span><span class="sxs-lookup"><span data-stu-id="77c70-109">Click Product variant model definition.</span></span>
2. <span data-ttu-id="77c70-110">Cliquez sur Nomenclature produit.</span><span class="sxs-lookup"><span data-stu-id="77c70-110">Click Product nomenclature.</span></span>
3. <span data-ttu-id="77c70-111">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="77c70-111">Click New.</span></span>
4. <span data-ttu-id="77c70-112">Dans le champ Nom, entrez un nom de nomenclature qui permet d'identifier le groupe de dimensions de produit cible, par exemple, ColorSize.</span><span class="sxs-lookup"><span data-stu-id="77c70-112">In the Name field, enter a nomenclature name that helps to identify the target product dimension group, for example, ColorSize.</span></span>
5. <span data-ttu-id="77c70-113">Dans le champ Description, entrez une valeur.</span><span class="sxs-lookup"><span data-stu-id="77c70-113">In the Description field, type a value.</span></span>
6. <span data-ttu-id="77c70-114">Cliquez sur Ajouter.</span><span class="sxs-lookup"><span data-stu-id="77c70-114">Click Add.</span></span>
7. <span data-ttu-id="77c70-115">Cliquez sur Numéro du produit générique.</span><span class="sxs-lookup"><span data-stu-id="77c70-115">Click Product master number.</span></span>
8. <span data-ttu-id="77c70-116">Cliquez sur Ajouter.</span><span class="sxs-lookup"><span data-stu-id="77c70-116">Click Add.</span></span>
9. <span data-ttu-id="77c70-117">Cliquez sur Constante de texte.</span><span class="sxs-lookup"><span data-stu-id="77c70-117">Click Text constant.</span></span>
10. <span data-ttu-id="77c70-118">Tapez une valeur dans le champ Texte.</span><span class="sxs-lookup"><span data-stu-id="77c70-118">In the Text field, type a value.</span></span>
11. <span data-ttu-id="77c70-119">Cliquez sur Ajouter.</span><span class="sxs-lookup"><span data-stu-id="77c70-119">Click Add.</span></span>
12. <span data-ttu-id="77c70-120">Cliquez sur Couleur.</span><span class="sxs-lookup"><span data-stu-id="77c70-120">Click Color.</span></span>
13. <span data-ttu-id="77c70-121">Cliquez sur Ajouter.</span><span class="sxs-lookup"><span data-stu-id="77c70-121">Click Add.</span></span>
14. <span data-ttu-id="77c70-122">Cliquez sur Constante de texte.</span><span class="sxs-lookup"><span data-stu-id="77c70-122">Click Text constant.</span></span>
15. <span data-ttu-id="77c70-123">Tapez une valeur dans le champ Texte.</span><span class="sxs-lookup"><span data-stu-id="77c70-123">In the Text field, type a value.</span></span>
16. <span data-ttu-id="77c70-124">Cliquez sur Ajouter.</span><span class="sxs-lookup"><span data-stu-id="77c70-124">Click Add.</span></span>
17. <span data-ttu-id="77c70-125">Cliquez sur Taille.</span><span class="sxs-lookup"><span data-stu-id="77c70-125">Click Size.</span></span>
18. <span data-ttu-id="77c70-126">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="77c70-126">Close the page.</span></span>

## <a name="assign-the-nomenclature-to-a-product-master"></a><span data-ttu-id="77c70-127">Affecter la nomenclature à un produit générique</span><span class="sxs-lookup"><span data-stu-id="77c70-127">Assign the nomenclature to a product master</span></span>
1. <span data-ttu-id="77c70-128">Cliquez sur Groupes de dimensions de produit.</span><span class="sxs-lookup"><span data-stu-id="77c70-128">Click Product dimension groups.</span></span>
2. <span data-ttu-id="77c70-129">Sélectionnez le groupe de dimensions de produit SizeCol.</span><span class="sxs-lookup"><span data-stu-id="77c70-129">Select the SizeCol product dimension group.</span></span>
3. <span data-ttu-id="77c70-130">Cliquez sur Modifier.</span><span class="sxs-lookup"><span data-stu-id="77c70-130">Click Edit.</span></span>
4. <span data-ttu-id="77c70-131">Sélectionnez Oui dans le champ Utiliser la nomenclature.</span><span class="sxs-lookup"><span data-stu-id="77c70-131">Select Yes in the Use nomenclature field.</span></span>
5. <span data-ttu-id="77c70-132">Dans le champ Nomenclature de numéros de variante de produit, entrez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="77c70-132">In the Product variant number nomenclature field, enter or select a value.</span></span>
6. <span data-ttu-id="77c70-133">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="77c70-133">Close the page.</span></span>


