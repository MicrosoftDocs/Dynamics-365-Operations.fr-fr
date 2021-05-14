---
title: Créer une nomenclature de numéro de produit pour les variantes de produit prédéfinies
description: Cette rubrique explique comment paramétrer une nomenclature de numéros de produit pour des variantes de produit prédéfinies et comment l’affecter au groupe de dimensions de produit approprié.
author: ShylaThompson
ms.date: 08/20/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: DefaultDashboard, EcoResProductVariantMaintainWorkspace, EcoResNomenclature, EcoResProductDimensionGroup
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 4bb73854f52525c0722683086d1b4f1dd7173306
ms.sourcegitcommit: fa99a36c3d30d0c0577fd3f63ed6bf2f71599e40
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/20/2021
ms.locfileid: "5920655"
---
# <a name="create-a-product-number-nomenclature-for-predefined-product-variants"></a><span data-ttu-id="04dd7-103">Créer une nomenclature de numéro de produit pour les variantes de produit prédéfinies</span><span class="sxs-lookup"><span data-stu-id="04dd7-103">Create a product number nomenclature for predefined product variants</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="04dd7-104">Cette rubrique explique comment paramétrer une nomenclature de numéros de produit pour des variantes de produit prédéfinies et comment l’affecter au groupe de dimensions de produit approprié.</span><span class="sxs-lookup"><span data-stu-id="04dd7-104">This topic explains how to set up a product number nomenclature for predefined product variants, and how you assign it to the appropriate product dimension group.</span></span> <span data-ttu-id="04dd7-105">Les données fictives utilisées pour créer cette procédure correspondent à la société USMF.</span><span class="sxs-lookup"><span data-stu-id="04dd7-105">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="04dd7-106">La nouvelle nomenclature de numéros de produit est affectée au groupe de dimensions de produit Couleur et Taille.</span><span class="sxs-lookup"><span data-stu-id="04dd7-106">The new product number nomenclature is assigned to the Color and Size product dimension group.</span></span> <span data-ttu-id="04dd7-107">Cette tâche est généralement effectuée par un concepteur de produit.</span><span class="sxs-lookup"><span data-stu-id="04dd7-107">This task would typically be done by a product designer.</span></span>


## <a name="create-a-product-number-nomenclature"></a><span data-ttu-id="04dd7-108">Créer une nomenclature de numéros de produit</span><span class="sxs-lookup"><span data-stu-id="04dd7-108">Create a product number nomenclature</span></span>

1. <span data-ttu-id="04dd7-109">Accédez à **Gestion des informations sur les produits \> Configuration \> Nomenclature produit**.</span><span class="sxs-lookup"><span data-stu-id="04dd7-109">Go to **Product information management \> Setup \> Product nomenclature**.</span></span>
1. <span data-ttu-id="04dd7-110">Sélectionnez **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="04dd7-110">Select **New**.</span></span>
1. <span data-ttu-id="04dd7-111">Dans le champ **Nom**, entrez un nom de nomenclature qui permet d’identifier le groupe de dimensions de produit cible, par exemple, `ColorSize`.</span><span class="sxs-lookup"><span data-stu-id="04dd7-111">In the **Name** field, enter a nomenclature name that helps to identify the target product dimension group, for example, `ColorSize`.</span></span>
1. <span data-ttu-id="04dd7-112">Tapez une valeur dans le champ **Description**.</span><span class="sxs-lookup"><span data-stu-id="04dd7-112">In the **Description** field, type a value.</span></span>
1. <span data-ttu-id="04dd7-113">Sélectionnez **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="04dd7-113">Select **Add**.</span></span>
1. <span data-ttu-id="04dd7-114">Sélectionnez **Numéro du produit générique**.</span><span class="sxs-lookup"><span data-stu-id="04dd7-114">Select **Product master** number.</span></span>
1. <span data-ttu-id="04dd7-115">Sélectionnez **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="04dd7-115">Select **Add**.</span></span>
1. <span data-ttu-id="04dd7-116">Sélectionnez **Texte constant**.</span><span class="sxs-lookup"><span data-stu-id="04dd7-116">Select **Text constant**.</span></span>
1. <span data-ttu-id="04dd7-117">Tapez une valeur dans le champ **Texte**.</span><span class="sxs-lookup"><span data-stu-id="04dd7-117">In the **Text** field, type a value.</span></span>
1. <span data-ttu-id="04dd7-118">Sélectionnez **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="04dd7-118">Select **Add**.</span></span>
1. <span data-ttu-id="04dd7-119">Sélectionnez **Couleur**.</span><span class="sxs-lookup"><span data-stu-id="04dd7-119">Select **Color**.</span></span>
1. <span data-ttu-id="04dd7-120">Sélectionnez **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="04dd7-120">Select **Add**.</span></span>
1. <span data-ttu-id="04dd7-121">Sélectionnez **Texte constant**.</span><span class="sxs-lookup"><span data-stu-id="04dd7-121">Select **Text constant**.</span></span>
1. <span data-ttu-id="04dd7-122">Tapez une valeur dans le champ **Texte**.</span><span class="sxs-lookup"><span data-stu-id="04dd7-122">In the **Text** field, type a value.</span></span>
1. <span data-ttu-id="04dd7-123">Sélectionnez **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="04dd7-123">Select **Add**.</span></span>
1. <span data-ttu-id="04dd7-124">Sélectionnez **Taille**.</span><span class="sxs-lookup"><span data-stu-id="04dd7-124">Select **Size**.</span></span>
1. <span data-ttu-id="04dd7-125">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="04dd7-125">Close the page.</span></span>

## <a name="assign-the-nomenclature-to-a-product-master"></a><span data-ttu-id="04dd7-126">Affecter la nomenclature à un produit générique</span><span class="sxs-lookup"><span data-stu-id="04dd7-126">Assign the nomenclature to a product master</span></span>

1. <span data-ttu-id="04dd7-127">Sélectionnez **Groupes de dimensions de produit**.</span><span class="sxs-lookup"><span data-stu-id="04dd7-127">Select **Product dimension groups**.</span></span>
2. <span data-ttu-id="04dd7-128">Sélectionnez le groupe de **dimensions de produit SizeCol**.</span><span class="sxs-lookup"><span data-stu-id="04dd7-128">Select the **SizeCol product dimension** group.</span></span>
3. <span data-ttu-id="04dd7-129">Sélectionnez **Modifier**.</span><span class="sxs-lookup"><span data-stu-id="04dd7-129">Select **Edit**.</span></span>
4. <span data-ttu-id="04dd7-130">Sélectionnez **Oui** dans le champ **Utiliser la nomenclature**.</span><span class="sxs-lookup"><span data-stu-id="04dd7-130">Select **Yes** in the **Use nomenclature** field.</span></span>
5. <span data-ttu-id="04dd7-131">Entrez ou sélectionnez une valeur dans le champ **Nomenclature de numéros de variante de produit**.</span><span class="sxs-lookup"><span data-stu-id="04dd7-131">In the **Product variant number nomenclature** field, enter or select a value.</span></span>
6. <span data-ttu-id="04dd7-132">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="04dd7-132">Close the page.</span></span>


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]