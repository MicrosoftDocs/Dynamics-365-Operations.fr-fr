---
title: Modifier l’ordre de tri pour les entités de promotion des ventes
description: Cet article explique les concepts relatifs aux contrôle de l’ordre d’affichage pour différentes entités associées à un événement de promotion des ventes dans Dynamics 365 Commerce.
author: josaw1
ms.date: 08/11/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: Category, Retail product hierarchy, Navigation hierarchy
audience: Application User, Merchandising manager, Catalog manager
ms.reviewer: josaw
ms.custom: 268444
ms.search.region: global
ms.search.industry: Retail
ms.author: brshoo
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 80586597f4f60476b341e4cf1cfd90f3681e15c0
ms.sourcegitcommit: 52e31b1ef2b3ed8675de931d06090cd57e057fc2
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/12/2022
ms.locfileid: "9265834"
---
# <a name="change-the-sort-order-for-merchandising-entities"></a>Modifier l’ordre de tri pour les entités de promotion des ventes


[!Include [banner](includes/banner.md)]

Les détaillants considèrent que la découverte d’un produit est l’outil principal pour l’interaction de clients entre les canaux. Plusieurs fonctionnalités peuvent aider les clients à découvrir facilement les produits. Ils peuvent par exemple parcourir des catégories, faire des recherches, et filtrer.

Cet article explique les concepts relatifs aux contrôle de l’ordre d’affichage pour différentes entités associées à un événement de promotion des ventes. Elle décrit également comment modifier l’ordre de tri.

## <a name="overview"></a>Présentation

Dans Commerce, le tri des différentes entités liées au merchandising est aligné sur les scénarios clients existants et ne nécessite plus d’extensions de la part des partenaires d’exécution.

Dans les versions Commerce version 10.0.5 et antérieures, la commande de tri pour les catégories de la hiérarchie de navigation était dans l’ordre alphabétique. La fonctionnalité actuelle d’ordre de tri personnalisée permet aux responsables des ventes de configurer la commande de tri pour différentes entités associées à un événement de promotion des ventes entre tous les clients de l’utilisateur final. Ces clients incluent les sièges sociaux et les centres d’appels.

## <a name="configure-the-display-order-for-categories-in-the-product-hierarchy"></a>Configuration de l’ordre d’affichage des catégories de la hiérarchie des produits

Avant de pouvoir exécuter cette procédure, les données de démonstration doivent être installées dans votre environnement.

1. Accédez à **Commerce et vente au détail \> Produits et catégories \> Hiérarchie des produits Commerce**.
2. Cliquez sur **Modifier la hiérarchie de la catégorie**.
3. Cliquez sur **Modifier**.
4. Dans l’arborescence, développez **ALL \> Action Sports**.
5. Dans l’arborescence, développez **ALL \> Team Sports**.
6. Entrez un nombre dans le champ **Ordre d’affichage**. (Ce nombre peut être négatif.)
7. Répétez les étapes 4 à 6 pour toutes les catégories supplémentaires dont vous souhaitez modifier l’ordre.

L’ordre d’affichage pour la hiérarchie de navigation du canal est reportée dans le siège pour la hiérarchie des produits Commerce et les produits lancés par catégorie.

![Hiérarchie des produits personnalisée triée par des valeurs négatives.](./media/RetailProductHierarchyCustomSortedWithNegativeValues.png)

![Tri personnalisé des produits lancés par catégorie selon la hiérarchie des produits.](./media/ReleasedProductsByCategoryCustomSortedBasedOnRetailProductHierarchy.png)

## <a name="configure-the-display-order-for-categories-in-the-channel-navigation-hierarchy"></a>Configuration de l’ordre d’affichage des catégories de la hiérarchie de navigation du canal

Avant de pouvoir exécuter cette procédure, les données de démonstration doivent être installées dans votre environnement.

1. Allez dans **Commerce et vente au détail \> Produits et catégories \> Catégories de navigation du canal**.
2. Dans la liste, sélectionnez la hiérarchie **Navigation de mode**.
3. Cliquez sur **Modifier la hiérarchie de la catégorie**.
4. Cliquez sur **Modifier**.
5. Dans l’arborescence, sélectionnez **Fashion \> Vêtements pour femmes \> Chaussures pour femme**.
6. Entrez un nombre dans le champ **Ordre d’affichage**.
7. Dans l’arborescence, sélectionnez **Fashion \> Womenswear \> Tops**.

De même, vous pouvez définir l’ordre de tri pour les sous-catégories.

8. Dans l’arborescence, sélectionnez **Fashion \> Menswear \> Casual Shirts**.
9. Entrez un nombre dans le champ **Ordre d’affichage**.
10. Dans l’arborescence, sélectionnez **Fashion \> Menswear \> Coats & Jackets**.
11. Entrez un nombre dans le champ **Ordre d’affichage**.
12. Répétez pour toutes les catégories supplémentaires dont vous souhaitez modifier l’ordre.

L’ordre d’affichage pour la hiérarchie de navigation du canal apparaît dans le siège, le catalogue, puis les canaux.

![Tri de la hiérarchie de navigation du canal personnalisée.](./media/ChannelNavCustomSorted.png)

![Tri de la hiérarchie de navigation du canal personnalisée selon la hiérarchie de navigation du canal.](./media/CatalogNavHierarchyCustomSortedBasedOnChannelNav.png)

![PDV avec des catégories triées par personnalisation.](./media/POSChannelCategoriesCustomSorted.png)

> [!NOTE]
> Par défaut, la fonctionnalité **Activer l’ordre d’affichage pour les entités de merchandising** est désactivée. Utilisez [Gestion des fonctionnalités](../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) pour l’activer. Une fois la fonctionnalité activée, exécutez la tâche CDX **Configuration globale -1110** dans le programme de distribution.
> Si l’ordre de vos catégories dans le PDV n’est pas mis à jour, réactivez l’appareil. Les informations de catégorie sont récupérées lors de l’activation de l’appareil, de sorte que l’appareil peut avoir besoin de récupérer les informations de catégorie avec des commandes d’affichage mises à jour. 

[!INCLUDE[footer-include](../includes/footer-banner.md)]
