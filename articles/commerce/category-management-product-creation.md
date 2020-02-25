---
title: Gérer les produits et catégories de produits
description: Cette rubrique décrit comment les gestionnaires du commerce peuvent utiliser des catégories de produit pour gérer les relations entre la hiérarchie des produits Commerce et les détails du produit lancé.
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
ms.openlocfilehash: 6e0c6a8048b5a2ef9a48495cd5e2609a1324a6e2
ms.sourcegitcommit: 81a647904dd305c4be2e4b683689f128548a872d
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/01/2020
ms.locfileid: "3022485"
---
# <a name="manage-product-categories-and-products"></a>Gérer les produits et catégories de produits

[!include [banner](./includes/banner.md)]

Cette rubrique décrit une manière améliorée de gérer des catégories de produits et des produits dans Dynamics 365 Commerce. Les améliorations permettent aux responsables des ventes d'afficher une structure de propriétés de produit partagées entre la hiérarchie des produits Retail et les détails du produit lancé.

Pour en savoir plus sur la gestion des catégories de produits, dans l'espace de travail **Gestion des catégories et des produits**, sélectionnez la vignette **Hiérarchie des produits Commerce**.

Notez la structure améliorée de la page **Hiérarchie des produits Commerce** qui s'affiche. Dans les versions précédentes de l'application, les propriétés du produit étaient divisées en *propriétés de base du produit* et *propriétés du produit vendu au détail*, en fonction de l'étendue de leur applicabilité. Les propriétés du produit vendu au détail sont *globales* dans leur portée d'applicabilité. En d'autres termes, pour une propriété de produit donnée, la même valeur est partagée pour toutes les entités juridiques. Par opposition, les propriétés de produit de base sont *spécifiques à une entité juridique*. En d'autres termes, pour une propriété de produit de base donnée, la valeur peut être différente entre les entités juridiques, selon les exigences de l'entreprise de chaque entité juridique.

Dans la structure de la catégorie de produit améliorée, les propriétés du produit sont séparées de manière logique en fonction de leur applicabilité au sein d'un groupe, afin de refléter la structure des écrans de détails de produit.

![Regroupement des champs selon leur portée d'applicabilité de leurs propriétés](media/NoticeGroupingOfFieldsBasedOnTheirScope.PNG)

Vous pouvez basculer entre la gestion des propriétés spécifiques à l'entité juridique dans toutes les entités juridiques et leur gestion pour une entité juridique spécifique.

Pour gérer les propriétés de toutes les entités juridiques, sélectionnez **Afficher pour toutes les entités juridiques** (ou **Modifier pour toutes les entités juridiques**).

![Afficher ou modifier pour toutes les entités juridiques](media/ToggleBackToEditForSpecificLegalEntity.PNG)

Pour gérer les propriétés d'une entité juridique spécifique, sélectionnez **Afficher pour une entité juridique spécifique** (ou **Modifier pour une entité juridique spécifique**).

![Afficher/modifier une entité juridique spécifique](media/ToggleToEditForAllLegalEntities.PNG)

De plus, dans la structure de la catégorie de produits améliorée, un gestionnaire du commerce peut désormais définir des valeurs par défaut pour un ensemble de propriétés de produit supplémentaires au niveau de la catégorie individuelle. Ensuite, lors de la création des produits, ces valeurs de propriété de produit par défaut sont héritées par un produit, selon l'association de ces propriétés à une catégorie individuelle de la hiérarchie des produits. Ces propriétés de produit héritées peuvent également être modifiées pour chaque produit, afin de répondre aux exigences de l'entreprise.

## <a name="selecting-properties-to-update-products-on-the-commerce-product-hierarchy-page"></a>Sélection des propriétés pour mettre à jour les produits sur la page de la hiérarchie de produits Commerce

Vous pouvez utiliser la nouvelle structure améliorées pour les propriétés de produit afin de sélectionner les propriétés de produit mises à jour devant être incluses dans les produits associés. Dans la page **Hiérarchie des produits Commerce**, dans le volet Actions, sélectionnez **Catégorie**, puis **Mettre à jour les produits** pour ouvrir la boîte de dialogue **Mettre à jour les produits**.

![Boîte de dialogue Mettre à jour les produits](media/NewUpdateProductsEnhancedView.PNG)
