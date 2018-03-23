---
title: "Gestion des catégories de produit"
description: "Cette rubrique décrit comment les responsables des opérations commerciales peuvent utiliser des catégories de produit vendus au détail pour gérer les relations entre la hiérarchie des produits vendus au détail et les détails du produit lancé."
author: ashishmsft
manager: AnnBe
ms.date: 10/23/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
ms.search.form: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations, Retail
ms.custom: 
ms.assetid: c7ed2ba5-87c6-4d99-9728-2a83e6d95ca9
ms.search.region: global
ms.search.industry: Retail
ms.author: asharchw
ms.search.validFrom: 2017-09-01
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: 25fa39dc81fc721d7593a25a102ce47041ebc5f0
ms.openlocfilehash: 4b7ef962b777a31e1da238a8ec1be9a42ec5bb5f
ms.contentlocale: fr-fr
ms.lasthandoff: 03/13/2018

---


# <a name="enhanced-product-and-category-management"></a><span data-ttu-id="a0502-103">Gestion des catégories et des produits améliorée</span><span class="sxs-lookup"><span data-stu-id="a0502-103">Enhanced product and category management</span></span>

[!include[banner](./includes/banner.md)]

<span data-ttu-id="a0502-104">Cette rubrique décrit une manière améliorée de gérer des catégories de produits vendus au détail et des produits vendus au détail dans Dynamics 365 for Retail.</span><span class="sxs-lookup"><span data-stu-id="a0502-104">This topic describes an enhanced way to manage Retail product categories and products in Dynamics 365 for Retail.</span></span> <span data-ttu-id="a0502-105">Ces améliorations permettent aux responsables des ventes d'afficher une structure commune de propriétés de produit entre la hiérarchie des produits de détail et les détails des produits lancés.</span><span class="sxs-lookup"><span data-stu-id="a0502-105">These enhancements let merchandising managers view a common structure of product properties between Retail product hierarchy and released product details.</span></span>

<span data-ttu-id="a0502-106">Pour en savoir plus sur la gestion des catégories de produits vendus au détail, accédez à **Hiérarchie des produits vendus au détail** dans l'espace de travail **Gestion des catégories et des produits**, et prenez note de la structure améliorée de la page **Catégorie de produits vendus au détail**.</span><span class="sxs-lookup"><span data-stu-id="a0502-106">To learn more about managing Retail product categories, go to **Retail product hierarchy** from the **Category and product management** workspace, and note the enhanced structure of the **Retail product category** page.</span></span>

![Espace de travail Gestion des catégories et des produits](media/LaunchRetailProductHierarchy.png)

<span data-ttu-id="a0502-108">Dans les versions précédentes, les propriétés du produit étaient divisées en **propriétés de base du produit** et en **propriétés du produit vendu au détail**, en fonction de l'étendue de leur applicabilité.</span><span class="sxs-lookup"><span data-stu-id="a0502-108">In previous versions, product properties were divided into **Basic product properties** and **Retail product properties**, based on the scope of their applicability.</span></span> <span data-ttu-id="a0502-109">Les **propriétés du produit vendu au détail** étaient *globales* en fonction de l'étendue de leur applicabilité, ce qui signifie que pour une **propriété de produit vendu au détail** donné, la même valeur est partagée entre toutes les entités juridiques.</span><span class="sxs-lookup"><span data-stu-id="a0502-109">**Retail product properties** were *global* by scope of applicability, which means that for a given **Retail product property**, the same value is shared across all legal entities.</span></span> <span data-ttu-id="a0502-110">Les **propriétés de produit de base** sont *spécifiques à une entité juridique*.</span><span class="sxs-lookup"><span data-stu-id="a0502-110">**Basic product properties** are *legal entity specific*.</span></span> <span data-ttu-id="a0502-111">En d'autres termes, pour une **propriété de produit de base** donnée, la valeur peut être différente entre les entités juridiques, selon les exigences de l'entreprise.</span><span class="sxs-lookup"><span data-stu-id="a0502-111">In other words, for a given **Basic product property** the value can differ across legal entities, based on individual business requirements.</span></span>

<span data-ttu-id="a0502-112">Dans la structure de la catégorie de produit vendu au détail améliorée, les propriétés du produit sont séparées de manière logique en fonction de leur applicabilité au sein d'un groupe, afin de refléter la structure des écrans de détails de produit.</span><span class="sxs-lookup"><span data-stu-id="a0502-112">In the enhanced Retail product category structure, product properties are logically separated based on their applicability within a group, to reflect the released product details form structure.</span></span>

![Regroupement des champs selon leur portée d'applicabilité](media/NoticeGroupingOfFieldsBasedOnTheirScope.PNG)

<span data-ttu-id="a0502-114">Vous pouvez basculer entre la gestion des propriétés spécifiques à l'entité juridique dans toutes les entités juridiques et leur gestion pour une entité juridique spécifique.</span><span class="sxs-lookup"><span data-stu-id="a0502-114">You can switch between managing legal-entity specific properties across all legal entities and managing them for a specific legal entity.</span></span> <span data-ttu-id="a0502-115">Pour cela, sélectionnez **Afficher ou modifier pour toutes les entités juridiques** ou **Afficher/Modifier pour une entité juridique spécifique**.</span><span class="sxs-lookup"><span data-stu-id="a0502-115">To do this, select either **View/Edit for all legal entities** or **View/Edit for a specific legal entity**.</span></span>

![Basculer entre la vue d'un individu et toutes les entités juridiques](media/ToggleBackToEditForSpecificLegalEntity.PNG)

![Basculer entre la vue d'un individu et toutes les entités juridiques](media/ToggleToEditForAllLegalEntities.PNG)  

<span data-ttu-id="a0502-118">Comparée aux versions précédentes, dans la nouvelle structure de la catégories de produits vendus au détail, responsable de vente peut également définir des valeurs par défaut pour un ensemble de propriétés de produit supplémentaires à un niveau de catégorie individuel.</span><span class="sxs-lookup"><span data-stu-id="a0502-118">Compared to previous versions, in the new Retail product category structure a merchandising manager can also define default values for an additional set of product properties at an individual category level.</span></span> <span data-ttu-id="a0502-119">Lors de la création du produit, ces valeurs de propriété de produit par défaut sont héritées par un produit, selon son association à une catégorie individuelle de la hiérarchie des produits vendus au détail.</span><span class="sxs-lookup"><span data-stu-id="a0502-119">At the time of product creation, these default product property values are inherited by a product, based on their association with an individual category from Retail product hierarchy.</span></span> <span data-ttu-id="a0502-120">Ces propriétés de produit héritées peuvent également être modifiées pour chaque produit, afin de répondre aux exigences de l'entreprise.</span><span class="sxs-lookup"><span data-stu-id="a0502-120">These inherited product properties can also be modified for each product, to meet individual business requirements.</span></span>

## <a name="select-properties-to-update-products-from-the-retail-product-category-form"></a><span data-ttu-id="a0502-121">Sélectionner les propriétés pour mettre à jour les produits du formulaire de la catégorie de produits vendus au détail</span><span class="sxs-lookup"><span data-stu-id="a0502-121">Select properties to update products from the Retail product category form</span></span> 
 
<span data-ttu-id="a0502-122">Vous pouvez utiliser cette nouvelle structure améliorées pour les propriétés de produit afin de sélectionner les propriétés de produit mises à jour devant être incluses dans les produits associés.</span><span class="sxs-lookup"><span data-stu-id="a0502-122">You can use this new enhanced structure for product properties to select which updated product properties must be pushed to associated products.</span></span> 

![Nouvelle vue améliorée de Mettre à jour les produits](media/NewUpdateProductsEnhancedView.PNG) 

<span data-ttu-id="a0502-124">Les responsables des ventes peuvent modifier ces propriétés de produit héritées pour chaque produit, afin de répondre aux exigences de l'entreprise.</span><span class="sxs-lookup"><span data-stu-id="a0502-124">Merchandising managers can modify these inherited product properties for each product, to meet individual business requirements.</span></span>


