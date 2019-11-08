---
title: Modifier l'ordre de tri pour les entités de promotion des ventes
description: Cette rubrique explique les concepts relatifs aux contrôle de l'ordre d'affichage pour différentes entités associées à un événement de promotion des ventes dans Dynamics 365 Retail.
author: josaw1
manager: AnnBe
ms.date: 08/05/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: Category, Retail product hierarchy, Navigation hierarchy
audience: Application User, Merchandising manager, Catalog manager
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 268444
ms.search.region: global
ms.search.industry: Retail
ms.author: rubendel
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: c159ff869d6c504fdebbef1fa68115a410c81d85
ms.sourcegitcommit: f87de0f949b5d60993b19e0f61297f02d42b5bef
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/24/2019
ms.locfileid: "2019414"
---
# <a name="change-the-sort-order-for-merchandising-entities"></a>Modifier l'ordre de tri pour les entités de promotion des ventes


[!include [banner](includes/banner.md)]

Les détaillants considèrent que la découverte d'un produit est l'outil principal pour l'interaction de clients entre les canaux de vente au détail. Différentes fonctionnalités peuvent aider les clients à découvrir facilement des produits. Ils peuvent par exemple parcourir des catégories, faire des recherches, et filtrer.

Cette rubrique explique les concepts relatifs aux contrôle de l'ordre d'affichage pour différentes entités associées à un événement de promotion des ventes. Elle décrit également comment modifier l'ordre de tri.

## <a name="overview"></a>Présentation

La prise en charge du tri de différentes entités associées à un événement de promotion des ventes a été améliorée. Cette prise en charge correspond désormais mieux aux scénarios client existants qui nécessitaient auparavant des extensions de la part des partenaires d'implémentation.

Dans les versions de Retail qui sont antérieures à la version 10.0.5, la commande de tri pour les catégories de la hiérarchie de navigation était dans l'ordre alphabétique. La nouvelle fonctionnalité d'ordre de tri personnalisée permet aux responsables des ventes de configurer la commande de tri pour différentes entités associées à un événement de promotion des ventes entre tous les clients de l'utilisateur final. Ces clients incluent les sièges sociaux et les centres d'appels.

## <a name="configure-the-display-order-for-categories-in-the-retail-product-hierarchy"></a>Configuration de l'ordre d'affichage des catégories de la hiérarchie des produits vendus au détail

Avant de pouvoir exécuter cette procédure, les données de démonstration doivent être installées dans votre environnement.

1. Accédez à **Vente au détail \> Produits et catégories \> Hiérarchie des produits vendus au détail**.
2. Cliquez sur **Modifier la hiérarchie de la catégorie**.
3. Cliquez sur **Modifier**.
4. Dans l'arborescence, développez **ALL \> Action Sports**.
5. Dans l'arborescence, développez **ALL \> Team Sports**.
6. Entrez un nombre dans le champ **Ordre d'affichage**. (Ce nombre peut être négatif.)
7. Répétez les étapes 4 à 6 pour toutes les catégories supplémentaires dont vous souhaitez modifier l'ordre.

L'ordre d'affichage pour la hiérarchie de navigation du canal est reportée dans le siège pour la hiérarchie des produits vendus au détail et les produits lancés par catégorie.

![Hiérarchie des produits vendus au détail personnalisée triée par des valeurs négatives](./media/RetailProductHierarchyCustomSortedWithNegativeValues.png)

![Tri personnalisé des produits lancés par catégorie selon la hiérarchie des produits vendus au détail](./media/ReleasedProductsByCategoryCustomSortedBasedOnRetailProductHierarchy.png)

## <a name="configure-the-display-order-for-categories-in-the-channel-navigation-hierarchy"></a>Configuration de l'ordre d'affichage des catégories de la hiérarchie de navigation du canal

Avant de pouvoir exécuter cette procédure, les données de démonstration doivent être installées dans votre environnement.

1. Allez dans **Vente au détail \> Produits et catégories \> Catégories de navigation du canal**.
2. Dans la liste, sélectionnez la hiérarchie **Navigation de mode**.
3. Cliquez sur **Modifier la hiérarchie de la catégorie**.
4. Cliquez sur **Modifier**.
5. Dans l'arborescence, sélectionnez **Fashion \> Womenswear \> Tops**.
6. Entrez un nombre dans le champ **Ordre d'affichage**.
7. Dans l'arborescence, sélectionnez **Fashion \> Womenswear \> Tops**.

    De même, vous pouvez définir l'ordre de tri pour les sous-catégories.

8. Dans l'arborescence, sélectionnez **Fashion \> Menswear \> Casual Shirts**.
9. Entrez un nombre dans le champ **Ordre d'affichage**.
10. Dans l'arborescence, sélectionnez **Fashion \> Menswear \> Coats & Jackets**.
11. Entrez un nombre dans le champ **Ordre d'affichage**.
12. Répétez pour toutes les catégories supplémentaires dont vous souhaitez modifier l'ordre.

L'ordre d'affichage pour la hiérarchie de navigation du canal apparaît dans le siège, le catalogue, puis les canaux de vente au détail.

![Tri de la hiérarchie de navigation du canal personnalisée](./media/ChannelNavCustomSorted.png)

![Tri de la hiérarchie de navigation du canal personnalisée selon la hiérarchie de navigation du canal](./media/CatalogNavHierarchyCustomSortedBasedOnChannelNav.png)

![PDV avec des catégories triées par personnalisation](./media/POSChannelCategoriesCustomSorted.png)

> [!NOTE]
> Par défaut, la fonctionnalité d'ordre de tri personnalisé est désactivée. Pour savoir comment activer cette fonctionnalité et les autres, consultez [Gestion des fonctionnalités](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/get-started/feature-management/feature-management-overview).