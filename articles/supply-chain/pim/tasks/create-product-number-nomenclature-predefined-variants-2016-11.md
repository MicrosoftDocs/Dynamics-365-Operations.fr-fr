---
title: Créer une nomenclature de numéro de produit pour les variantes de produit prédéfinies
description: Cette rubrique explique comment paramétrer une nomenclature de numéros de produit pour des variantes de produit prédéfinies et comment l'affecter au groupe de dimensions de produit approprié.
author: ShylaThompson
manager: tfehr
ms.date: 08/20/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: DefaultDashboard, EcoResProductVariantMaintainWorkspace, EcoResNomenclature, EcoResProductDimensionGroup
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 3a15d1f4ecbf85e22bfadc1dd680d24bc56d807f
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/15/2021
ms.locfileid: "5007539"
---
# <a name="create-a-product-number-nomenclature-for-predefined-product-variants"></a><span data-ttu-id="0d3dc-103">Créer une nomenclature de numéro de produit pour les variantes de produit prédéfinies</span><span class="sxs-lookup"><span data-stu-id="0d3dc-103">Create a product number nomenclature for predefined product variants</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="0d3dc-104">Cette rubrique explique comment paramétrer une nomenclature de numéros de produit pour des variantes de produit prédéfinies et comment l'affecter au groupe de dimensions de produit approprié.</span><span class="sxs-lookup"><span data-stu-id="0d3dc-104">This topic explains how to set up a product number nomenclature for predefined product variants, and how you assign it to the appropriate product dimension group.</span></span> <span data-ttu-id="0d3dc-105">Les données fictives utilisées pour créer cette procédure correspondent à la société USMF.</span><span class="sxs-lookup"><span data-stu-id="0d3dc-105">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="0d3dc-106">La nouvelle nomenclature de numéros de produit est affectée au groupe de dimensions de produit Couleur et Taille.</span><span class="sxs-lookup"><span data-stu-id="0d3dc-106">The new product number nomenclature is assigned to the Color and Size product dimension group.</span></span> <span data-ttu-id="0d3dc-107">Cette tâche est généralement effectuée par un concepteur de produit.</span><span class="sxs-lookup"><span data-stu-id="0d3dc-107">This task would typically be done by a product designer.</span></span>


## <a name="create-a-product-number-nomenclature"></a><span data-ttu-id="0d3dc-108">Créer une nomenclature de numéros de produit</span><span class="sxs-lookup"><span data-stu-id="0d3dc-108">Create a product number nomenclature</span></span>
1. <span data-ttu-id="0d3dc-109">Sélectionnez **Définition du modèle de variante de produit**.</span><span class="sxs-lookup"><span data-stu-id="0d3dc-109">Select **Product variant model definition**.</span></span>
2. <span data-ttu-id="0d3dc-110">Sélectionnez **Nomenclature produit**.</span><span class="sxs-lookup"><span data-stu-id="0d3dc-110">Select **Product nomenclature**.</span></span>
3. <span data-ttu-id="0d3dc-111">Sélectionnez **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="0d3dc-111">Select **New**.</span></span>
4. <span data-ttu-id="0d3dc-112">Dans le champ **Nom**, entrez un nom de nomenclature qui permet d'identifier le groupe de dimensions de produit cible, par exemple, `ColorSize`.</span><span class="sxs-lookup"><span data-stu-id="0d3dc-112">In the **Name** field, enter a nomenclature name that helps to identify the target product dimension group, for example, `ColorSize`.</span></span>
5. <span data-ttu-id="0d3dc-113">Tapez une valeur dans le champ **Description**.</span><span class="sxs-lookup"><span data-stu-id="0d3dc-113">In the **Description** field, type a value.</span></span>
6. <span data-ttu-id="0d3dc-114">Sélectionnez **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="0d3dc-114">Select **Add**.</span></span>
7. <span data-ttu-id="0d3dc-115">Sélectionnez **Numéro du produit générique**.</span><span class="sxs-lookup"><span data-stu-id="0d3dc-115">Select **Product master** number.</span></span>
8. <span data-ttu-id="0d3dc-116">Sélectionnez **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="0d3dc-116">Select **Add**.</span></span>
9. <span data-ttu-id="0d3dc-117">Sélectionnez **Texte constant**.</span><span class="sxs-lookup"><span data-stu-id="0d3dc-117">Select **Text constant**.</span></span>
10. <span data-ttu-id="0d3dc-118">Tapez une valeur dans le champ **Texte**.</span><span class="sxs-lookup"><span data-stu-id="0d3dc-118">In the **Text** field, type a value.</span></span>
11. <span data-ttu-id="0d3dc-119">Sélectionnez **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="0d3dc-119">Select **Add**.</span></span>
12. <span data-ttu-id="0d3dc-120">Sélectionnez **Couleur**.</span><span class="sxs-lookup"><span data-stu-id="0d3dc-120">Select **Color**.</span></span>
13. <span data-ttu-id="0d3dc-121">Sélectionnez **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="0d3dc-121">Select **Add**.</span></span>
14. <span data-ttu-id="0d3dc-122">Sélectionnez **Texte constant**.</span><span class="sxs-lookup"><span data-stu-id="0d3dc-122">Select **Text constant**.</span></span>
15. <span data-ttu-id="0d3dc-123">Tapez une valeur dans le champ **Texte**.</span><span class="sxs-lookup"><span data-stu-id="0d3dc-123">In the **Text** field, type a value.</span></span>
16. <span data-ttu-id="0d3dc-124">Sélectionnez **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="0d3dc-124">Select **Add**.</span></span>
17. <span data-ttu-id="0d3dc-125">Sélectionnez **Taille**.</span><span class="sxs-lookup"><span data-stu-id="0d3dc-125">Select **Size**.</span></span>
18. <span data-ttu-id="0d3dc-126">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="0d3dc-126">Close the page.</span></span>

## <a name="assign-the-nomenclature-to-a-product-master"></a><span data-ttu-id="0d3dc-127">Affecter la nomenclature à un produit générique</span><span class="sxs-lookup"><span data-stu-id="0d3dc-127">Assign the nomenclature to a product master</span></span>
1. <span data-ttu-id="0d3dc-128">Sélectionnez **Groupes de dimensions de produit**.</span><span class="sxs-lookup"><span data-stu-id="0d3dc-128">Select **Product dimension groups**.</span></span>
2. <span data-ttu-id="0d3dc-129">Sélectionnez le groupe de **dimensions de produit SizeCol**.</span><span class="sxs-lookup"><span data-stu-id="0d3dc-129">Select the **SizeCol product dimension** group.</span></span>
3. <span data-ttu-id="0d3dc-130">Sélectionnez **Modifier**.</span><span class="sxs-lookup"><span data-stu-id="0d3dc-130">Select **Edit**.</span></span>
4. <span data-ttu-id="0d3dc-131">Sélectionnez **Oui** dans le champ **Utiliser la nomenclature**.</span><span class="sxs-lookup"><span data-stu-id="0d3dc-131">Select **Yes** in the **Use nomenclature** field.</span></span>
5. <span data-ttu-id="0d3dc-132">Entrez ou sélectionnez une valeur dans le champ **Nomenclature de numéros de variante de produit**.</span><span class="sxs-lookup"><span data-stu-id="0d3dc-132">In the **Product variant number nomenclature** field, enter or select a value.</span></span>
6. <span data-ttu-id="0d3dc-133">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="0d3dc-133">Close the page.</span></span>

