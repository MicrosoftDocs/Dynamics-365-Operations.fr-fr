---
title: Créer un groupe de variantes
description: Cette rubrique décrit comment créer un groupe de variantes de taille, de style ou de couleur pour un produit dans Microsoft Dynamics 365 Commerce.
author: samjarawan
manager: annbe
ms.date: 01/27/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: samjar
ms.search.validFrom: 2020-01-20
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: b9acd41c000b22e6c74b0d636a7f58917e4b5ac5
ms.sourcegitcommit: 81a647904dd305c4be2e4b683689f128548a872d
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/01/2020
ms.locfileid: "3001873"
---
# <a name="create-a-variant-group"></a><span data-ttu-id="84ca3-103">Créer un groupe de variantes</span><span class="sxs-lookup"><span data-stu-id="84ca3-103">Create a variant group</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="84ca3-104">Cette rubrique décrit comment créer un groupe de variantes de taille, de style ou de couleur pour un produit dans Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="84ca3-104">This topic describes how to create a size, style, or color variant group for a product in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="84ca3-105">Vue d'ensemble</span><span class="sxs-lookup"><span data-stu-id="84ca3-105">Overview</span></span>

<span data-ttu-id="84ca3-106">Dynamics 365 Commerce prend en charge plusieurs variantes pour les produits.</span><span class="sxs-lookup"><span data-stu-id="84ca3-106">Dynamics 365 Commerce supports multiple variants for products.</span></span> <span data-ttu-id="84ca3-107">Il est idéal de configurer des groupes de variantes pour différentes catégories de produits.</span><span class="sxs-lookup"><span data-stu-id="84ca3-107">It is ideal to set up variant groups for different product categories.</span></span> <span data-ttu-id="84ca3-108">Par exemple, un groupe de tailles peut être créé pour les t-shirts de tailles XS, S, M, L et XL, ou un groupe de couleurs peut être créé pour inclure toutes les couleurs disponibles d'un produit.</span><span class="sxs-lookup"><span data-stu-id="84ca3-108">For example, a size group can be created for t-shirts with sizes extra small, small, medium, large, and extra large, or a color group could be created to include all available colors of a product.</span></span> <span data-ttu-id="84ca3-109">Les groupes de variantes doivent être ajoutés avant l'ajout de produits.</span><span class="sxs-lookup"><span data-stu-id="84ca3-109">Variant groups should be added before products are added.</span></span>

<span data-ttu-id="84ca3-110">Dans cette rubrique, un groupe de tailles sera créé et configuré.</span><span class="sxs-lookup"><span data-stu-id="84ca3-110">In this topic, a size group will be created and configured.</span></span> <span data-ttu-id="84ca3-111">Des procédures similaires peuvent être utilisées pour ajouter et configurer des groupes de styles et des groupes de couleurs.</span><span class="sxs-lookup"><span data-stu-id="84ca3-111">Similar procedures can be used for adding and configuring style groups and color groups.</span></span>

## <a name="create-a-size-group"></a><span data-ttu-id="84ca3-112">Créer un groupe de tailles</span><span class="sxs-lookup"><span data-stu-id="84ca3-112">Create a size group</span></span>

<span data-ttu-id="84ca3-113">Pour créer un groupe de tailles, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="84ca3-113">To create a size group, follow these steps.</span></span>
 
1. <span data-ttu-id="84ca3-114">Dans le Volet de navigation, accédez à **Modules \> Commerce et vente au détail \> Produits et catégories \> Groupes de variantes \> Groupes de tailles**.</span><span class="sxs-lookup"><span data-stu-id="84ca3-114">In the navigation pane, go to **Modules \> Retail and commerce \> Products and categories \> Variant groups \> Size groups**.</span></span>
1. <span data-ttu-id="84ca3-115">Dans le volet Actions, sélectionnez **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="84ca3-115">On the action pane, select **New**.</span></span>
1. <span data-ttu-id="84ca3-116">Dans la zone **Groupe de tailles**, entrez un nom unique pour le groupe de tailles.</span><span class="sxs-lookup"><span data-stu-id="84ca3-116">In the **Size group** box, enter a name for the size group.</span></span>
1. <span data-ttu-id="84ca3-117">Entrez une description adéquate dans la zone **Description**.</span><span class="sxs-lookup"><span data-stu-id="84ca3-117">In the **Description** box, enter an appropriate description.</span></span>
1. <span data-ttu-id="84ca3-118">Dans le volet Actions, sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="84ca3-118">On the action pane, select **Save**.</span></span>

## <a name="add-attributes-to-the-size-group"></a><span data-ttu-id="84ca3-119">Ajouter des attributs au groupe de tailles</span><span class="sxs-lookup"><span data-stu-id="84ca3-119">Add attributes to the size group</span></span>

<span data-ttu-id="84ca3-120">Pour ajouter des attributs à un groupe de tailles procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="84ca3-120">To add attributes to a size group, follow these steps.</span></span>

1. <span data-ttu-id="84ca3-121">Dans le Volet de navigation, accédez à **Modules \> Commerce et vente au détail \> Produits et catégories \> Groupes de variantes \> Groupes de tailles**.</span><span class="sxs-lookup"><span data-stu-id="84ca3-121">In the navigation pane, go to **Modules \> Retail and commerce \> Products and categories \> Variant groups \> Size groups**</span></span>
1. <span data-ttu-id="84ca3-122">Dans le volet de navigation, sélectionnez un groupe de tailles.</span><span class="sxs-lookup"><span data-stu-id="84ca3-122">In the navigation pane, select a size group.</span></span>
1. <span data-ttu-id="84ca3-123">Sous **Lignes de groupe de tailles**, sélectionnez **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="84ca3-123">Under **Size group lines**, select **Add**.</span></span>
1. <span data-ttu-id="84ca3-124">Dans la zone **Taille**, entrez une chaîner représentant la taille (par exemple, « XL »).</span><span class="sxs-lookup"><span data-stu-id="84ca3-124">In the **Size** box, enter a string representing the size (for example, "XL").</span></span>
1. <span data-ttu-id="84ca3-125">Dans la zone **Nom de la taille**, entrez un nom pour la taille (par exemple, « Extra Large »).</span><span class="sxs-lookup"><span data-stu-id="84ca3-125">In the **Size name** box, enter a name for the size (for example, "Extra Large").</span></span>
1. <span data-ttu-id="84ca3-126">Dans la zone **Poids de réapprovisionnement**, entrez un nombre représentant le poids de réapprovisionnement.</span><span class="sxs-lookup"><span data-stu-id="84ca3-126">In the **Replenishment weight** box, enter a number representing the replenishment weight.</span></span>
1. <span data-ttu-id="84ca3-127">Dans la zone **Numéro dans le code-barres**, entrez un nombre représentant le code-barres.</span><span class="sxs-lookup"><span data-stu-id="84ca3-127">In the **Number in bar code** box, enter a number representing the bar code.</span></span>
1. <span data-ttu-id="84ca3-128">Dans la zone **Ordre d'affichage**, entrez un nombre représentant l'ordre d'affichage.</span><span class="sxs-lookup"><span data-stu-id="84ca3-128">In the **Display order** box, enter a number representing the display order.</span></span>
1. <span data-ttu-id="84ca3-129">Lorsque vous avez terminé d'ajouter des tailles, sélectionnez **Enregister** dans le volet Actions.</span><span class="sxs-lookup"><span data-stu-id="84ca3-129">When finished adding sizes, select **Save** on the action pane.</span></span>

<span data-ttu-id="84ca3-130">L'image suivante montre un exemple de groupe de tailles pour « Tailles de chemises décontractées ».</span><span class="sxs-lookup"><span data-stu-id="84ca3-130">The following image shows an example of a size group for "casual shirt sizes".</span></span>

![Créer un groupe de tailles](media/create-variant-group.png)

## <a name="additional-resources"></a><span data-ttu-id="84ca3-132">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="84ca3-132">Additional resources</span></span>

[<span data-ttu-id="84ca3-133">Vue d'ensemble des informations sur le produit</span><span class="sxs-lookup"><span data-stu-id="84ca3-133">Product information overview</span></span>](../supply-chain/pim/product-information.md?toc=/dynamics365/commerce/toc.json)

[<span data-ttu-id="84ca3-134">Paramétrer les produits vendus au détail</span><span class="sxs-lookup"><span data-stu-id="84ca3-134">Set up retail products</span></span>](set-up-retail-products.md)

[<span data-ttu-id="84ca3-135">Dimensions de produit</span><span class="sxs-lookup"><span data-stu-id="84ca3-135">Product dimensions</span></span>](../supply-chain/pim/product-dimensions.md?toc=/dynamics365/commerce/toc.json)
