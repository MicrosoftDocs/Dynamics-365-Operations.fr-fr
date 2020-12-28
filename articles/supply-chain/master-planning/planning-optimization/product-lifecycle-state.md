---
title: Exclure les produits avec des états du cycle de vie des produits spécifiques
description: Cette rubrique explique comment exclure des produits en fonction de leur état de cycle de vie lorsque la fonctionnalité d'optimisation de planification est utilisée.
author: ChristianRytt
manager: tfehr
ms.date: 11/13/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ReqCreatePlanWorkspace
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2019-11-13
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: 371d98eefa482fc3e430f2f0977ddffb9dd0d30e
ms.sourcegitcommit: deb711c92251ed48cdf20ea514d03461c26a2262
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/25/2020
ms.locfileid: "4645090"
---
# <a name="exclude-products-that-have-specific-product-lifecycle-states"></a><span data-ttu-id="2a7dc-103">Exclure les produits avec des états du cycle de vie des produits spécifiques</span><span class="sxs-lookup"><span data-stu-id="2a7dc-103">Exclude products that have specific product lifecycle states</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="2a7dc-104">Les produits lancés et les versions de produits lancés incluent un champ **État du cycle de vie du produit**.</span><span class="sxs-lookup"><span data-stu-id="2a7dc-104">Released products and released product versions include a **Product lifecycle state** field.</span></span> <span data-ttu-id="2a7dc-105">Ce champ vous permet de contrôler, entre autres, quels produits sont inclus lors de la planification.</span><span class="sxs-lookup"><span data-stu-id="2a7dc-105">This field lets you control, among other things, which products are included during master planning.</span></span> <span data-ttu-id="2a7dc-106">Vous pouvez ajouter, supprimer et modifier les états du cycle de vie selon vos besoins en accédant à **Gestion des informations produit \> Configurer \> État du cycle de vie du produit**.</span><span class="sxs-lookup"><span data-stu-id="2a7dc-106">You can add, remove, and edit lifecycle states as required by going to **Product information management \> Setup \> Product lifecycle state**.</span></span> <span data-ttu-id="2a7dc-107">Pour chaque état du cycle de vie du produit, définissez l'option **Actif pour la planification** sur *Oui* si les produits qui ont cet état doivent être inclus lors de la planification.</span><span class="sxs-lookup"><span data-stu-id="2a7dc-107">For each product lifecycle state, set the **Is active for planning** option to *Yes* if products that have that state should be included during master planning.</span></span> <span data-ttu-id="2a7dc-108">Lorsque l'option est définie sur *Non*, les produits et variantes associés seront exclus de toute planification et de tous les calculs au niveau de la nomenclature (BOM).</span><span class="sxs-lookup"><span data-stu-id="2a7dc-108">When the option is set to *No*, the associated products and variants will be excluded from all master planning and all calculations at the bill of materials (BOM) level.</span></span>

<span data-ttu-id="2a7dc-109">Produits lancés et variantes où le champ **État du cycle de vie du produit** est laissé vide sont traités comme s'ils avaient un état du cycle de vie du produit où l'option **Actif pour la planification** est définie sur *Oui*.</span><span class="sxs-lookup"><span data-stu-id="2a7dc-109">Released products and variants where the **Product lifecycle state** field is left blank are treated as though they have a product lifecycle state where the **Is active for planning** option is set to *Yes*.</span></span> <span data-ttu-id="2a7dc-110">En d'autres termes, ils seront inclus lors de la planification.</span><span class="sxs-lookup"><span data-stu-id="2a7dc-110">In other words, they will be included during master planning.</span></span>

> [!NOTE]
> <span data-ttu-id="2a7dc-111">Pour éviter les suggestions d'approvisionnement inutiles, nous vous recommandons vivement d'associer tous les produits et variantes obsolètes à un état du cycle de vie du produit où l'option **Actif pour la planification** est définie sur *Non*.</span><span class="sxs-lookup"><span data-stu-id="2a7dc-111">To help avoid unnecessary supply suggestions, we strongly recommend that you associate all obsolete released products and variants with a product lifecycle state where the **Is active for planning** option is set to *No*.</span></span> <span data-ttu-id="2a7dc-112">Cette approche est particulièrement importante lorsque vous travaillez avec des variantes de configuration de produit qui ne sont pas réutilisables, car elle permet d'éviter le gaspillage.</span><span class="sxs-lookup"><span data-stu-id="2a7dc-112">This approach is especially important when you work with product configuration variants that aren't reusable, because it will help prevent waste.</span></span>

## <a name="related-resources"></a><span data-ttu-id="2a7dc-113">Ressources associées</span><span class="sxs-lookup"><span data-stu-id="2a7dc-113">Related resources</span></span>

<span data-ttu-id="2a7dc-114">Pour plus d’informations sur les états du cycle de vie du produit, voir [Vue d’ensemble des états du cycle de vie du produit](../../pim/product-lifecycle.md).</span><span class="sxs-lookup"><span data-stu-id="2a7dc-114">For more information about product lifecycle states, see [Product lifecycle state overview](../../pim/product-lifecycle.md).</span></span>

<span data-ttu-id="2a7dc-115">Pour des informations détaillées avec étapes sur l'utilisation des états du cycle de vie des produits pour exclure des produits de la planification et des calculs au niveau de la nomenclature, voir [Créer un état du cycle du vie des produits pour exclure des produits de la planification](../../pim/tasks/exclude-products-master-planning.md).</span><span class="sxs-lookup"><span data-stu-id="2a7dc-115">For detailed information that includes steps for using product lifecycle states to exclude products from master planning and BOM-level calculations, see [Create a product lifecycle state to exclude products from Master planning](../../pim/tasks/exclude-products-master-planning.md).</span></span>
