---
title: Module Menu de navigation
description: Cette rubrique couvre les modules de menu de navigation et décrit comment les ajouter aux pages du site dans Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 10/01/2020
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
ms.search.industry: ''
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.14
ms.openlocfilehash: b0e8168ca9ec9ca68011650a73cc09983deca645
ms.sourcegitcommit: 765056b5dc1d0a8c27e56ff2cbd310ad3349ff09
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/20/2020
ms.locfileid: "4055735"
---
# <a name="navigation-menu-module"></a><span data-ttu-id="e8dfc-103">Module Menu de navigation</span><span class="sxs-lookup"><span data-stu-id="e8dfc-103">Navigation menu module</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="e8dfc-104">Cette rubrique couvre les modules de menu de navigation et décrit comment les ajouter aux pages du site dans Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="e8dfc-104">This topic covers navigation menu modules and describes how to add them to site pages in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="e8dfc-105">Vue d’ensemble</span><span class="sxs-lookup"><span data-stu-id="e8dfc-105">Overview</span></span>

<span data-ttu-id="e8dfc-106">L’objectif principal des modules de menu de navigation est de permettre aux utilisateurs du site de parcourir les produits et les pages du site en fonction de la hiérarchie de navigation des canaux définie dans le siège Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="e8dfc-106">The primary purpose of navigation menu modules is to allow site users to browse products and site pages according to the channel navigation hierarchy defined in Dynamics 365 Commerce headquarters.</span></span> <span data-ttu-id="e8dfc-107">Les éléments configurés dans un module de menu de navigation apparaissent en tant que navigation dans l’en-tête du site.</span><span class="sxs-lookup"><span data-stu-id="e8dfc-107">Items configured in a navigation menu module appear as site header navigation.</span></span> <span data-ttu-id="e8dfc-108">Les modules de menu de navigation prennent également en charge les éléments de menu statiques qui renvoient à d’autres pages d’un site d’e-commerce.</span><span class="sxs-lookup"><span data-stu-id="e8dfc-108">Navigation menu modules also support static menu items that link to other pages on an e-Commerce site.</span></span>

<span data-ttu-id="e8dfc-109">Le module de menu de navigation peut être ajouté au module d’en-tête d’une page.</span><span class="sxs-lookup"><span data-stu-id="e8dfc-109">The navigation menu module can be added to the header module of a page.</span></span> <span data-ttu-id="e8dfc-110">Dans le thème Fabrikam, le menu de navigation affiche deux niveaux par défaut.</span><span class="sxs-lookup"><span data-stu-id="e8dfc-110">In the Fabrikam theme, the navigation menu shows two levels by default.</span></span> <span data-ttu-id="e8dfc-111">Dans le thème Starter, le menu de navigation affiche trois niveaux par défaut.</span><span class="sxs-lookup"><span data-stu-id="e8dfc-111">In the Starter theme, the navigation menu shows three levels by default.</span></span> <span data-ttu-id="e8dfc-112">Pour modifier le nombre de niveaux, une extension de vue est requise sur le thème.</span><span class="sxs-lookup"><span data-stu-id="e8dfc-112">To change to the number of levels, a view extension is required on the theme.</span></span>

<span data-ttu-id="e8dfc-113">L’illustration suivante montre un exemple de menu de navigation pour le site Fabrikam avec deux niveaux de hiérarchie de catégories et des éléments de menu statiques.</span><span class="sxs-lookup"><span data-stu-id="e8dfc-113">The following illustration shows an example of a navigation menu for the Fabrikam site with two levels of category hierarchy and some static menu items.</span></span>
<span data-ttu-id="e8dfc-114">![Exemple de module de menu de navigation](./media/ecommerce-header.png)</span><span class="sxs-lookup"><span data-stu-id="e8dfc-114">![Example of a navigation meu module](./media/ecommerce-header.png)</span></span>

## <a name="navigation-menu-module-properties"></a><span data-ttu-id="e8dfc-115">Propriétés du module Menu de navigation</span><span class="sxs-lookup"><span data-stu-id="e8dfc-115">Navigation menu module properties</span></span>

| <span data-ttu-id="e8dfc-116">Nom de la propriété</span><span class="sxs-lookup"><span data-stu-id="e8dfc-116">Property name</span></span>             | <span data-ttu-id="e8dfc-117">Valeur</span><span class="sxs-lookup"><span data-stu-id="e8dfc-117">Value</span></span>                 | <span data-ttu-id="e8dfc-118">Description</span><span class="sxs-lookup"><span data-stu-id="e8dfc-118">Description</span></span> |
|---------------------------|-----------------------|-------------|
| <span data-ttu-id="e8dfc-119">Source</span><span class="sxs-lookup"><span data-stu-id="e8dfc-119">Source</span></span>                  | <span data-ttu-id="e8dfc-120">**Vente au détail** , **Création manuelle** , **Vente au détail et création manuelle**</span><span class="sxs-lookup"><span data-stu-id="e8dfc-120">**Retail** , **Manual authoring** , **Retail and manual authoring**</span></span> | <span data-ttu-id="e8dfc-121">La valeur **Vente au détail** permet d’afficher la hiérarchie de navigation des canaux depuis le siège Commerce dans le menu de navigation.</span><span class="sxs-lookup"><span data-stu-id="e8dfc-121">The **Retail** value allows the channel navigation hierarchy from Commerce headquarters to be displayed on the navigation menu.</span></span> <span data-ttu-id="e8dfc-122">La valeur **Création manuelle** permet aux éléments de menu statiques d’être organisés.</span><span class="sxs-lookup"><span data-stu-id="e8dfc-122">The **Manual authoring** value allows static menu items to be curated.</span></span> <span data-ttu-id="e8dfc-123">La valeur **Vente au détail et création manuelle** permet un mélange des deux.</span><span class="sxs-lookup"><span data-stu-id="e8dfc-123">The **Retail and manual authoring** value allows a mix of both.</span></span> |
| <span data-ttu-id="e8dfc-124">Afficher les images des catégories</span><span class="sxs-lookup"><span data-stu-id="e8dfc-124">Show category images</span></span> | <span data-ttu-id="e8dfc-125">**Vrai** ou **Faux**</span><span class="sxs-lookup"><span data-stu-id="e8dfc-125">**True** or **False**</span></span>    | <span data-ttu-id="e8dfc-126">Lorsqu’elle est activée, cette propriété affiche les images de catégorie dans le menu de navigation, telles que définies dans le siège Commerce pour chaque catégorie.</span><span class="sxs-lookup"><span data-stu-id="e8dfc-126">When enabled, this property displays category images on the navigation menu as defined in Commerce headquarters for each category.</span></span> <span data-ttu-id="e8dfc-127">Ajouté dans la version 10.0.14 de Commerce.</span><span class="sxs-lookup"><span data-stu-id="e8dfc-127">Added in Commerce release 10.0.14.</span></span> |
| <span data-ttu-id="e8dfc-128">Activer le menu de navigation à plusieurs niveaux</span><span class="sxs-lookup"><span data-stu-id="e8dfc-128">Enable multi-level navigation menu</span></span> | <span data-ttu-id="e8dfc-129">**Vrai** ou **Faux**</span><span class="sxs-lookup"><span data-stu-id="e8dfc-129">**True** or **False**</span></span> | <span data-ttu-id="e8dfc-130">Lorsque cette propriété est activée, le menu de navigation peut afficher plusieurs niveaux de la hiérarchie de navigation.</span><span class="sxs-lookup"><span data-stu-id="e8dfc-130">When this property is enabled, the navigation menu can show multiple levels of the navigation hierarchy.</span></span> <span data-ttu-id="e8dfc-131">Cette fonction est disponible dans Dynamics 365 Commerce version 10.0.15.</span><span class="sxs-lookup"><span data-stu-id="e8dfc-131">This feature is available in the Dynamics 365 Commerce 10.0.15 release.</span></span> |
| <span data-ttu-id="e8dfc-132">Nombre de niveaux</span><span class="sxs-lookup"><span data-stu-id="e8dfc-132">Number of levels</span></span> | <span data-ttu-id="e8dfc-133">entier</span><span class="sxs-lookup"><span data-stu-id="e8dfc-133">integer</span></span> | <span data-ttu-id="e8dfc-134">Cette propriété définit le nombre de niveaux à afficher si la propriété **Activer le menu de navigation à plusieurs niveaux** est définie sur **True**.</span><span class="sxs-lookup"><span data-stu-id="e8dfc-134">This property defines the numbers of levels that should be shown if the **Enable multilevel navigation menu** property is set to **True**.</span></span> |
| <span data-ttu-id="e8dfc-135">Élément de menu statique</span><span class="sxs-lookup"><span data-stu-id="e8dfc-135">Static menu item</span></span>| <span data-ttu-id="e8dfc-136">Tableau de valeurs</span><span class="sxs-lookup"><span data-stu-id="e8dfc-136">Array of values</span></span>| <span data-ttu-id="e8dfc-137">Éléments de menu statiques qui associent un nom d’élément de menu à un lien vers une page de site statique.</span><span class="sxs-lookup"><span data-stu-id="e8dfc-137">Static menu items that associate a menu item name with a link to a static site page.</span></span> <span data-ttu-id="e8dfc-138">Vous pouvez créer des éléments de menu sous d’autres éléments de menu.</span><span class="sxs-lookup"><span data-stu-id="e8dfc-138">You can create menu items below other menu items.</span></span> <span data-ttu-id="e8dfc-139">Par défaut, les menus statiques apparaissent au niveau racine et seront ajoutés à la hiérarchie de navigation des canaux si elle existe.</span><span class="sxs-lookup"><span data-stu-id="e8dfc-139">By default, static menus appear at the root level and will be appended to the channel navigation hierarchy if it exists.</span></span> |
| <span data-ttu-id="e8dfc-140">Afficher le menu racine</span><span class="sxs-lookup"><span data-stu-id="e8dfc-140">Show root menu</span></span> | <span data-ttu-id="e8dfc-141">**Vrai** ou **Faux**</span><span class="sxs-lookup"><span data-stu-id="e8dfc-141">**True** or **False**</span></span> | <span data-ttu-id="e8dfc-142">Lorsque cette propriété est activée, le menu de navigation peut être défini sous une racine personnalisée (par exemple, **Acheter maintenant** ).</span><span class="sxs-lookup"><span data-stu-id="e8dfc-142">When this property is enabled, the navigation menu can be defined under a custom root (for example, **Shop now** ).</span></span> <span data-ttu-id="e8dfc-143">Cette fonction est disponible dans Dynamics 365 Commerce version 10.0.15.</span><span class="sxs-lookup"><span data-stu-id="e8dfc-143">This feature is available in the Dynamics 365 Commerce 10.0.15 release.</span></span> |
| <span data-ttu-id="e8dfc-144">Menu racine</span><span class="sxs-lookup"><span data-stu-id="e8dfc-144">Root menu</span></span> | <span data-ttu-id="e8dfc-145">chaîne</span><span class="sxs-lookup"><span data-stu-id="e8dfc-145">string</span></span> | <span data-ttu-id="e8dfc-146">Cette propriété peut être utilisée pour définir le texte d'une racine personnalisée si la propriété **Afficher le menu racine** est définie sur **True**.</span><span class="sxs-lookup"><span data-stu-id="e8dfc-146">This property can be used to define text for a custom root if the **Show root menu** property is set to **True**.</span></span> |

<span data-ttu-id="e8dfc-147">L’illustration suivante montre un exemple d’image de catégorie affichée dans le menu de navigation du site Fabrikam.</span><span class="sxs-lookup"><span data-stu-id="e8dfc-147">The following illustration shows an example of a category image displayed on the navigation menu for the Fabrikam site.</span></span>
<span data-ttu-id="e8dfc-148">![Exemple de module de navigation avec images de catégories](./media/ecommerce-categoryimages.PNG)</span><span class="sxs-lookup"><span data-stu-id="e8dfc-148">![Example of a navigation meu module with category images](./media/ecommerce-categoryimages.PNG)</span></span>

## <a name="add-a-navigation-menu-module-to-a-header-module"></a><span data-ttu-id="e8dfc-149">Ajouter un module de menu de navigation à un module d’en-tête</span><span class="sxs-lookup"><span data-stu-id="e8dfc-149">Add a navigation menu module to a header module</span></span>

<span data-ttu-id="e8dfc-150">Pour plus d’informations sur l’ajout d’un module de menu de navigation à un module d’en-tête, voir [Module d’en-tête](author-header-module.md).</span><span class="sxs-lookup"><span data-stu-id="e8dfc-150">For details about how to add a navigation menu module to a header module, see [Header module](author-header-module.md).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="e8dfc-151">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="e8dfc-151">Additional resources</span></span>

[<span data-ttu-id="e8dfc-152">Vue d’ensemble de la bibliothèque de modules</span><span class="sxs-lookup"><span data-stu-id="e8dfc-152">Module library overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="e8dfc-153">Module de barre de navigation</span><span class="sxs-lookup"><span data-stu-id="e8dfc-153">Breadcrumb module</span></span>](add-breadcrumb.md)

[<span data-ttu-id="e8dfc-154">Module Sélecteur de site</span><span class="sxs-lookup"><span data-stu-id="e8dfc-154">Site selector module</span></span>](site-selector.md)

[<span data-ttu-id="e8dfc-155">Module Zone d’achat</span><span class="sxs-lookup"><span data-stu-id="e8dfc-155">Buy box module</span></span>](add-buy-box.md)

[<span data-ttu-id="e8dfc-156">Conformité des cookies</span><span class="sxs-lookup"><span data-stu-id="e8dfc-156">Cookie compliance</span></span>](cookie-compliance.md)

[<span data-ttu-id="e8dfc-157">Module En-tête</span><span class="sxs-lookup"><span data-stu-id="e8dfc-157">Header module</span></span>](author-header-module.md)
