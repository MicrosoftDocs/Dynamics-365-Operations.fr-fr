---
title: Module Menu de navigation
description: Cette rubrique couvre les modules de menu de navigation et décrit comment les ajouter aux pages du site dans Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 09/15/2020
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
ms.openlocfilehash: 91239bd1db3f5819b7ad8d45ccfd8ab0d88b1b41
ms.sourcegitcommit: 8028fbc5b9585e87d3331ea02577ff82ede090af
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/16/2020
ms.locfileid: "3817872"
---
# <a name="navigation-menu-module"></a><span data-ttu-id="776e8-103">Module Menu de navigation</span><span class="sxs-lookup"><span data-stu-id="776e8-103">Navigation menu module</span></span>

[!include [banner](includes/banner.md)]
[!include [banner](includes/preview-banner.md)]

<span data-ttu-id="776e8-104">Cette rubrique couvre les modules de menu de navigation et décrit comment les ajouter aux pages du site dans Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="776e8-104">This topic covers navigation menu modules and describes how to add them to site pages in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="776e8-105">Vue d’ensemble</span><span class="sxs-lookup"><span data-stu-id="776e8-105">Overview</span></span>

<span data-ttu-id="776e8-106">L’objectif principal des modules de menu de navigation est de permettre aux utilisateurs du site de parcourir les produits et les pages du site en fonction de la hiérarchie de navigation des canaux définie dans le siège Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="776e8-106">The primary purpose of navigation menu modules is to allow site users to browse products and site pages according to the channel navigation hierarchy defined in Dynamics 365 Commerce headquarters.</span></span> <span data-ttu-id="776e8-107">Les éléments configurés dans un module de menu de navigation apparaissent en tant que navigation dans l’en-tête du site.</span><span class="sxs-lookup"><span data-stu-id="776e8-107">Items configured in a navigation menu module appear as site header navigation.</span></span> <span data-ttu-id="776e8-108">Les modules de menu de navigation prennent également en charge les éléments de menu statiques qui renvoient à d’autres pages d’un site d’e-commerce.</span><span class="sxs-lookup"><span data-stu-id="776e8-108">Navigation menu modules also support static menu items that link to other pages on an e-Commerce site.</span></span>

<span data-ttu-id="776e8-109">Le module de menu de navigation peut être ajouté au module d’en-tête d’une page.</span><span class="sxs-lookup"><span data-stu-id="776e8-109">The navigation menu module can be added to the header module of a page.</span></span> <span data-ttu-id="776e8-110">Dans le thème Fabrikam, le menu de navigation affiche deux niveaux par défaut.</span><span class="sxs-lookup"><span data-stu-id="776e8-110">In the Fabrikam theme, the navigation menu shows two levels by default.</span></span> <span data-ttu-id="776e8-111">Dans le thème Starter, le menu de navigation affiche trois niveaux par défaut.</span><span class="sxs-lookup"><span data-stu-id="776e8-111">In the Starter theme, the navigation menu shows three levels by default.</span></span> <span data-ttu-id="776e8-112">Pour modifier le nombre de niveaux, une extension de vue est requise sur le thème.</span><span class="sxs-lookup"><span data-stu-id="776e8-112">To change to the number of levels, a view extension is required on the theme.</span></span>

<span data-ttu-id="776e8-113">L’illustration suivante montre un exemple de menu de navigation pour le site Fabrikam avec deux niveaux de hiérarchie de catégories et des éléments de menu statiques.</span><span class="sxs-lookup"><span data-stu-id="776e8-113">The following illustration shows an example of a navigation menu for the Fabrikam site with two levels of category hierarchy and some static menu items.</span></span>
<span data-ttu-id="776e8-114">![Exemple de module de menu de navigation](./media/ecommerce-header.png)</span><span class="sxs-lookup"><span data-stu-id="776e8-114">![Example of a navigation meu module](./media/ecommerce-header.png)</span></span>

## <a name="navigation-menu-module-properties"></a><span data-ttu-id="776e8-115">Propriétés du module Menu de navigation</span><span class="sxs-lookup"><span data-stu-id="776e8-115">Navigation menu module properties</span></span>

| <span data-ttu-id="776e8-116">Nom de la propriété</span><span class="sxs-lookup"><span data-stu-id="776e8-116">Property name</span></span>             | <span data-ttu-id="776e8-117">Valeur</span><span class="sxs-lookup"><span data-stu-id="776e8-117">Value</span></span>                 | <span data-ttu-id="776e8-118">Description</span><span class="sxs-lookup"><span data-stu-id="776e8-118">Description</span></span> |
|---------------------------|-----------------------|-------------|
| <span data-ttu-id="776e8-119">Source</span><span class="sxs-lookup"><span data-stu-id="776e8-119">Source</span></span>                  | <span data-ttu-id="776e8-120">**Vente au détail**, **Création manuelle**, **Vente au détail et création manuelle**</span><span class="sxs-lookup"><span data-stu-id="776e8-120">**Retail**, **Manual authoring**, **Retail and manual authoring**</span></span> | <span data-ttu-id="776e8-121">La valeur **Vente au détail** permet d’afficher la hiérarchie de navigation des canaux depuis le siège Commerce dans le menu de navigation.</span><span class="sxs-lookup"><span data-stu-id="776e8-121">The **Retail** value allows the channel navigation hierarchy from Commerce headquarters to be displayed on the navigation menu.</span></span> <span data-ttu-id="776e8-122">La valeur **Création manuelle** permet aux éléments de menu statiques d’être organisés.</span><span class="sxs-lookup"><span data-stu-id="776e8-122">The **Manual authoring** value allows static menu items to be curated.</span></span> <span data-ttu-id="776e8-123">La valeur **Vente au détail et création manuelle** permet un mélange des deux.</span><span class="sxs-lookup"><span data-stu-id="776e8-123">The **Retail and manual authoring** value allows a mix of both.</span></span> |
| <span data-ttu-id="776e8-124">Afficher les images des catégories</span><span class="sxs-lookup"><span data-stu-id="776e8-124">Show category images</span></span> | <span data-ttu-id="776e8-125">**Vrai** ou **Faux**</span><span class="sxs-lookup"><span data-stu-id="776e8-125">**True** or **False**</span></span>    | <span data-ttu-id="776e8-126">Lorsqu’elle est activée, cette propriété affiche les images de catégorie dans le menu de navigation, telles que définies dans le siège Commerce pour chaque catégorie.</span><span class="sxs-lookup"><span data-stu-id="776e8-126">When enabled, this property displays category images on the navigation menu as defined in Commerce headquarters for each category.</span></span> <span data-ttu-id="776e8-127">Ajouté dans la version 10.0.14 de Commerce.</span><span class="sxs-lookup"><span data-stu-id="776e8-127">Added in Commerce release 10.0.14.</span></span> |
| <span data-ttu-id="776e8-128">Élément de menu statique</span><span class="sxs-lookup"><span data-stu-id="776e8-128">Static menu item</span></span>| <span data-ttu-id="776e8-129">Tableau de valeurs</span><span class="sxs-lookup"><span data-stu-id="776e8-129">Array of values</span></span>| <span data-ttu-id="776e8-130">Éléments de menu statiques qui associent un nom d’élément de menu à un lien vers une page de site statique.</span><span class="sxs-lookup"><span data-stu-id="776e8-130">Static menu items that associate a menu item name with a link to a static site page.</span></span> <span data-ttu-id="776e8-131">Vous pouvez créer des éléments de menu sous d’autres éléments de menu.</span><span class="sxs-lookup"><span data-stu-id="776e8-131">You can create menu items below other menu items.</span></span> <span data-ttu-id="776e8-132">Par défaut, les menus statiques apparaissent au niveau racine et seront ajoutés à la hiérarchie de navigation des canaux si elle existe.</span><span class="sxs-lookup"><span data-stu-id="776e8-132">By default, static menus appear at the root level and will be appended to the channel navigation hierarchy if it exists.</span></span> |

<span data-ttu-id="776e8-133">L’illustration suivante montre un exemple d’image de catégorie affichée dans le menu de navigation du site Fabrikam.</span><span class="sxs-lookup"><span data-stu-id="776e8-133">The following illustration shows an example of a category image displayed on the navigation menu for the Fabrikam site.</span></span>
<span data-ttu-id="776e8-134">![Exemple de module de navigation avec images de catégories](./media/ecommerce-categoryimages.PNG)</span><span class="sxs-lookup"><span data-stu-id="776e8-134">![Example of a navigation meu module with category images](./media/ecommerce-categoryimages.PNG)</span></span>

## <a name="add-a-navigation-menu-module-to-a-header-module"></a><span data-ttu-id="776e8-135">Ajouter un module de menu de navigation à un module d’en-tête</span><span class="sxs-lookup"><span data-stu-id="776e8-135">Add a navigation menu module to a header module</span></span>

<span data-ttu-id="776e8-136">Pour plus d’informations sur l’ajout d’un module de menu de navigation à un module d’en-tête, voir [Module d’en-tête](author-header-module.md).</span><span class="sxs-lookup"><span data-stu-id="776e8-136">For details about how to add a navigation menu module to a header module, see [Header module](author-header-module.md).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="776e8-137">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="776e8-137">Additional resources</span></span>

[<span data-ttu-id="776e8-138">Présentation de la bibliothèque de modules</span><span class="sxs-lookup"><span data-stu-id="776e8-138">Module library overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="776e8-139">Module Zone d’achat</span><span class="sxs-lookup"><span data-stu-id="776e8-139">Buy box module</span></span>](add-buy-box.md)

[<span data-ttu-id="776e8-140">Conformité des cookies</span><span class="sxs-lookup"><span data-stu-id="776e8-140">Cookie compliance</span></span>](cookie-compliance.md)

[<span data-ttu-id="776e8-141">Module En-tête</span><span class="sxs-lookup"><span data-stu-id="776e8-141">Header module</span></span>](author-header-module.md)
