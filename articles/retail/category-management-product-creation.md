---
title: Gérer les catégories de produits vendus au détail et les produits
description: Cette rubrique décrit comment les responsables des opérations commerciales peuvent utiliser des catégories de produit vendus au détail pour gérer les relations entre la hiérarchie des produits vendus au détail et les détails du produit lancé.
author: ashishmsft
manager: AnnBe
ms.date: 10/23/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations, Retail
ms.custom: ''
ms.assetid: c7ed2ba5-87c6-4d99-9728-2a83e6d95ca9
ms.search.region: global
ms.search.industry: Retail
ms.author: asharchw
ms.search.validFrom: 2017-09-01
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.openlocfilehash: 0bcc5989edd9913fce414c0c24068f111d8c1aeb
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/29/2019
ms.locfileid: "344683"
---
# <a name="manage-retail-product-categories-and-products"></a><span data-ttu-id="21cc6-103">Gérer les catégories de produits vendus au détail et les produits</span><span class="sxs-lookup"><span data-stu-id="21cc6-103">Manage Retail product categories and products</span></span>

[!include [banner](./includes/banner.md)]

<span data-ttu-id="21cc6-104">Cette rubrique décrit une manière améliorée de gérer des catégories de produits vendus au détail et des produits vendus au détail dans Microsoft Dynamics 365 for Retail.</span><span class="sxs-lookup"><span data-stu-id="21cc6-104">This topic describes an enhanced way to manage Retail product categories and products in Microsoft Dynamics 365 for Retail.</span></span> <span data-ttu-id="21cc6-105">Les améliorations permettent aux responsables des ventes d'afficher une structure de propriétés de produit partagées entre la hiérarchie des produits vendus au détail et les détails du produit lancé.</span><span class="sxs-lookup"><span data-stu-id="21cc6-105">The enhancements let merchandising managers view a structure of product properties that is shared between the Retail product hierarchy and released product details.</span></span>

<span data-ttu-id="21cc6-106">Pour en savoir plus sur la gestion des catégories de produits vendus au détail, dans l'espace de travail **Gestion des catégories et des produits**, sélectionnez la vignette **Hiérarchie des produits vendus au détail**.</span><span class="sxs-lookup"><span data-stu-id="21cc6-106">To learn more about how to manage Retail product categories, in the **Category and product management** workspace, select the **Retail product hierarchy** tile.</span></span>

<span data-ttu-id="21cc6-107">Notez la structure améliorée de la page **Hiérarchie des produits vendus au détail** qui s'affiche.</span><span class="sxs-lookup"><span data-stu-id="21cc6-107">Notice the enhanced structure of the **Retail product hierarchy** page that appears.</span></span> <span data-ttu-id="21cc6-108">Dans les versions précédentes de Retail, les propriétés du produit étaient divisées en *propriétés de base du produit* et en *propriétés du produit vendu au détail*, en fonction de l'étendue de leur applicabilité.</span><span class="sxs-lookup"><span data-stu-id="21cc6-108">In previous versions of Retail, product properties were divided into *basic product properties* and *Retail product properties*, based on the scope of their applicability.</span></span> <span data-ttu-id="21cc6-109">Les propriétés du produit vendu au détail sont *globales* dans leur portée d'applicabilité.</span><span class="sxs-lookup"><span data-stu-id="21cc6-109">Retail product properties are *global* in their scope of applicability.</span></span> <span data-ttu-id="21cc6-110">En d'autres termes, pour une propriété de produit Retail donnée, la même valeur est partagée pour toutes les entités juridiques.</span><span class="sxs-lookup"><span data-stu-id="21cc6-110">In other words, for a given Retail product property, the same value is shared across all legal entities.</span></span> <span data-ttu-id="21cc6-111">Par opposition, les propriétés de produit de base sont *spécifiques à une entité juridique*.</span><span class="sxs-lookup"><span data-stu-id="21cc6-111">By contrast, basic product properties are *legal entity–specific*.</span></span> <span data-ttu-id="21cc6-112">En d'autres termes, pour une propriété de produit de base donnée, la valeur peut être différente entre les entités juridiques, selon les exigences de l'entreprise de chaque entité juridique.</span><span class="sxs-lookup"><span data-stu-id="21cc6-112">In other words, for a given basic product property, the value can differ across legal entities, depending on the individual business requirements of each legal entity.</span></span>

<span data-ttu-id="21cc6-113">Dans la structure de la catégorie de produit vendu au détail améliorée, les propriétés du produit sont séparées de manière logique en fonction de leur applicabilité au sein d'un groupe, afin de refléter la structure des écrans de détails de produit.</span><span class="sxs-lookup"><span data-stu-id="21cc6-113">In the enhanced Retail product category structure, product properties are logically separated based on their applicability in a group, to reflect the structure of the released product details form structure.</span></span>

![Regroupement des champs selon leur portée d'applicabilité de leurs propriétés](media/NoticeGroupingOfFieldsBasedOnTheirScope.PNG)

<span data-ttu-id="21cc6-115">Vous pouvez basculer entre la gestion des propriétés spécifiques à l'entité juridique dans toutes les entités juridiques et leur gestion pour une entité juridique spécifique.</span><span class="sxs-lookup"><span data-stu-id="21cc6-115">You can switch between managing legal entity–specific properties across all legal entities and managing them for a specific legal entity.</span></span>

<span data-ttu-id="21cc6-116">Pour gérer les propriétés de toutes les entités juridiques, sélectionnez **Afficher pour toutes les entités juridiques** (ou **Modifier pour toutes les entités juridiques**).</span><span class="sxs-lookup"><span data-stu-id="21cc6-116">To manage properties across all legal entities, select **View for all legal entities** (or **Edit for all legal entities**).</span></span>

![Afficher ou modifier pour toutes les entités juridiques](media/ToggleBackToEditForSpecificLegalEntity.PNG)

<span data-ttu-id="21cc6-118">Pour gérer les propriétés d'une entité juridique spécifique, sélectionnez **Afficher pour une entité juridique spécifique** (ou **Modifier pour une entité juridique spécifique**).</span><span class="sxs-lookup"><span data-stu-id="21cc6-118">To manage properties for a specific legal entity, select **View for a specific legal entity** (or **Edit for a specific legal entity**).</span></span>

![Afficher/modifier une entité juridique spécifique](media/ToggleToEditForAllLegalEntities.PNG)

<span data-ttu-id="21cc6-120">De plus, dans la structure de la catégories de produits vendus au détail améliorée, un responsable de vente peut désormais définir des valeurs par défaut pour un ensemble de propriétés de produit supplémentaires au niveau de la catégorie individuelle.</span><span class="sxs-lookup"><span data-stu-id="21cc6-120">Additionally, in the enhanced Retail product category structure, a merchandising manager can now define default values for an additional set of product properties at the level of the individual category.</span></span> <span data-ttu-id="21cc6-121">Ensuite, lors de la création des produits, ces valeurs de propriété de produit par défaut sont héritées par un produit, selon l'association de ces propriétés à une catégorie individuelle de la hiérarchie des produits vendus au détail.</span><span class="sxs-lookup"><span data-stu-id="21cc6-121">Then, when products are created, they inherit default values for their product properties, based on the association of those properties with an individual category in Retail product hierarchy.</span></span> <span data-ttu-id="21cc6-122">Ces propriétés de produit héritées peuvent également être modifiées pour chaque produit, afin de répondre aux exigences de l'entreprise.</span><span class="sxs-lookup"><span data-stu-id="21cc6-122">These inherited product properties can also be modified for each product to meet individual business requirements.</span></span>

## <a name="selecting-properties-to-update-products-on-the-retail-product-hierarchy-page"></a><span data-ttu-id="21cc6-123">Sélection des propriétés pour mettre à jour les produits sur la page de la hiérarchie de produits vendus au détail</span><span class="sxs-lookup"><span data-stu-id="21cc6-123">Selecting properties to update products on the Retail product hierarchy page</span></span>

<span data-ttu-id="21cc6-124">Vous pouvez utiliser la nouvelle structure améliorées pour les propriétés de produit afin de sélectionner les propriétés de produit mises à jour devant être incluses dans les produits associés.</span><span class="sxs-lookup"><span data-stu-id="21cc6-124">You can use the new enhanced structure for product properties to select updated product properties that must be pushed to the associated products.</span></span> <span data-ttu-id="21cc6-125">Dans la page **Hiérarchie des produits vendus au détail**, dans le volet Actions, sélectionnez **Catégorie**, puis **Mettre à jour les produits** pour ouvrir la boîte de dialogue **Mettre à jour les produits**.</span><span class="sxs-lookup"><span data-stu-id="21cc6-125">On the **Retail product hierarchy** page, on the Action Pane, select **Category**, and then select **Update products** to open the **Update products** dialog box.</span></span>

![Boîte de dialogue Mettre à jour les produits](media/NewUpdateProductsEnhancedView.PNG)
