---
title: "Gestion et création des catégories de produit"
description: "Cette rubrique décrit les améliorations apportées à l'expérience de gestion des catégories de produits vendus au détail. Ces améliorations permettent aux responsables des ventes d'établir une corrélation entre la hiérarchie des produits de détail et les détails des produits lancés."
author: ashishmsft
manager: AnnBe
ms.date: 09/01/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
ms.search.form: RetailCategoryAndProductWorkspace, RetailCategory
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.search.region: Global
ms.search.industry: retail
ms.author: asharchw
ms.search.validFrom: 2017-09-01
ms.dyn365.ops.version: 
ms.translationtype: HT
ms.sourcegitcommit: ea07d8e91c94d9fdad4c2d05533981e254420188
ms.openlocfilehash: 74a8fa863736177bcf8cb4b3d90911c78122252b
ms.contentlocale: fr-fr
ms.lasthandoff: 02/07/2018

---

# <a name="product-category-management-and-creation"></a><span data-ttu-id="66059-104">Gestion et création des catégories de produit</span><span class="sxs-lookup"><span data-stu-id="66059-104">Product category management and creation</span></span>

[!include[banner](./includes/banner.md)]

<span data-ttu-id="66059-105">Les améliorations apportées à l'expérience de gestion des catégories de produits de vente au détail ont permis aux responsables des ventes d'établir une corrélation entre la hiérarchie des produits de détail et les détails des produits lancés.</span><span class="sxs-lookup"><span data-stu-id="66059-105">Enhancements that have been made to the management experience for Retail product categories let merchandising managers have a correlation between Retail product hierarchy and released product details.</span></span> <span data-ttu-id="66059-106">Pour visualiser ces améliorations, dans l'espace de travail **Gestion des catégories et des produits**, sélectionnez **Hiérarchie des produits vendus au détail** pour ouvrir la page **Nouvelle structure des catégories de produits vendus au détail**.</span><span class="sxs-lookup"><span data-stu-id="66059-106">To view these enhancements, in the **Category & product management**  workspace, select **Retail product hierarchy** to open the **New structure of Retail product category** page.</span></span> 

<span data-ttu-id="66059-107">Dans les versions précédentes, les propriétés du produit étaient divisées en propriétés de base du produit et en propriétés du produit de détail, en fonction de l'étendue de leur applicabilité.</span><span class="sxs-lookup"><span data-stu-id="66059-107">In previous releases, product properties were divided into Basic product properties and Retail product properties, based on the scope of their applicability.</span></span> <span data-ttu-id="66059-108">Les propriétés des produits vendus au détail étaient *globales*.</span><span class="sxs-lookup"><span data-stu-id="66059-108">Retail product properties were *global*.</span></span> <span data-ttu-id="66059-109">En d'autres termes, pour une propriété de produit donnée, la même valeur est partagée pour toutes les entités juridiques.</span><span class="sxs-lookup"><span data-stu-id="66059-109">In other words, for a given product property, the same value is shared across all legal entities.</span></span> <span data-ttu-id="66059-110">Les propriétés de produit de base étaient *spécifiques à une entité juridique*.</span><span class="sxs-lookup"><span data-stu-id="66059-110">Basic product properties were *legal entity–specific*.</span></span> <span data-ttu-id="66059-111">En d'autres termes, une propriété de produit donnée peut être différente dans les entités juridiques, selon les exigences de l'entreprise.</span><span class="sxs-lookup"><span data-stu-id="66059-111">In other words, a given product property might differ across legal entities, based on individual business requirements.</span></span>

<span data-ttu-id="66059-112">Grâce à ces améliorations, pour les propriétés du produit dans la catégorie de produits vendus au détail, nous continuons à séparer les champs, en fonction de leur applicabilité au sein d'un groupe, afin de refléter la structure des écrans de détails de produit.</span><span class="sxs-lookup"><span data-stu-id="66059-112">With these enhancements, for product properties in the Retail product category, we continue to separate the fields, based on their applicability within a group, to reflect the released product details form structure.</span></span>

<span data-ttu-id="66059-113">Vous pouvez basculer entre la gestion des propriétés spécifiques à l'entité juridique dans toutes les entités juridiques et leur gestion pour une entité juridique spécifique.</span><span class="sxs-lookup"><span data-stu-id="66059-113">You can switch between managing legal-entity specific properties across all legal entities and managing them for a specific legal entity.</span></span> <span data-ttu-id="66059-114">Sélectionnez simplement **Afficher ou modifier pour toutes les entités juridiques** ou **Afficher/Modifier pour une entité juridique spécifique** comme vous le souhaitez.</span><span class="sxs-lookup"><span data-stu-id="66059-114">Just select **View/Edit for all legal entities** or **View/Edit for a specific legal entity** as you require.</span></span>

<span data-ttu-id="66059-115">Les responsables des ventes peuvent également définir des valeurs par défaut pour un autre ensemble de propriétés de produit au niveau d'une catégorie individuelle.</span><span class="sxs-lookup"><span data-stu-id="66059-115">Merchandising managers can also define default values for an additional set of product properties at the level of an individual category.</span></span> <span data-ttu-id="66059-116">Ces valeurs de propriété sont héritées par un produit, selon leur association avec une catégorie au moment de la création du produit.</span><span class="sxs-lookup"><span data-stu-id="66059-116">These property values are inherited by a product, based on their association with a category at the time of product creation.</span></span>

## <a name="select-properties-to-update-products-from-the-retail-product-category-form"></a><span data-ttu-id="66059-117">Sélectionner les propriétés pour mettre à jour les produits du formulaire de la catégorie de produits vendus au détail</span><span class="sxs-lookup"><span data-stu-id="66059-117">Select properties to update products from the Retail product category form</span></span>

<span data-ttu-id="66059-118">Vous pouvez utiliser les propriétés de regroupement logique pour sélectionner les propriétés du produit mises à jour qui doivent être transmises aux produits associés.</span><span class="sxs-lookup"><span data-stu-id="66059-118">You can use logical grouping properties to select which updated product properties should be pushed to associated products.</span></span>

<span data-ttu-id="66059-119">Les responsables des ventes peuvent modifier ces propriétés de produit héritées pour chaque produit, afin de répondre aux exigences de l'entreprise.</span><span class="sxs-lookup"><span data-stu-id="66059-119">Merchandising managers can modify these inherited product properties for each product, to meet individual business requirements.</span></span>

