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
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: 2246024d7d70947690173f3d0768292abe43efd7
ms.contentlocale: fr-fr
ms.lasthandoff: 04/13/2018

---

# <a name="manage-retail-product-categories-and-products"></a>Gérer les catégories de produits vendus au détail et les produits

[!include [banner](./includes/banner.md)]

Cette rubrique décrit une manière améliorée de gérer des catégories de produits vendus au détail et des produits vendus au détail dans Microsoft Dynamics 365 for Retail. Les améliorations permettent aux responsables des ventes d'afficher une structure de propriétés de produit partagées entre la hiérarchie des produits vendus au détail et les détails du produit lancé.

Pour en savoir plus sur la gestion des catégories de produits vendus au détail, dans l'espace de travail **Gestion des catégories et des produits**, sélectionnez la vignette **Hiérarchie des produits vendus au détail**.

Notez la structure améliorée de la page **Hiérarchie des produits vendus au détail** qui s'affiche. Dans les versions précédentes de Retail, les propriétés du produit étaient divisées en *propriétés de base du produit* et en *propriétés du produit vendu au détail*, en fonction de l'étendue de leur applicabilité. Les propriétés du produit vendu au détail sont *globales* dans leur portée d'applicabilité. En d'autres termes, pour une propriété de produit Retail donnée, la même valeur est partagée pour toutes les entités juridiques. Par opposition, les propriétés de produit de base sont *spécifiques à une entité juridique*. En d'autres termes, pour une propriété de produit de base donnée, la valeur peut être différente entre les entités juridiques, selon les exigences de l'entreprise de chaque entité juridique.

Dans la structure de la catégorie de produit vendu au détail améliorée, les propriétés du produit sont séparées de manière logique en fonction de leur applicabilité au sein d'un groupe, afin de refléter la structure des écrans de détails de produit.

![Regroupement des champs selon leur portée d'applicabilité de leurs propriétés](media/NoticeGroupingOfFieldsBasedOnTheirScope.PNG)

Vous pouvez basculer entre la gestion des propriétés spécifiques à l'entité juridique dans toutes les entités juridiques et leur gestion pour une entité juridique spécifique.

Pour gérer les propriétés de toutes les entités juridiques, sélectionnez **Afficher pour toutes les entités juridiques** (ou **Modifier pour toutes les entités juridiques**).

![Afficher ou modifier pour toutes les entités juridiques](media/ToggleBackToEditForSpecificLegalEntity.PNG)

Pour gérer les propriétés d'une entité juridique spécifique, sélectionnez **Afficher pour une entité juridique spécifique** (ou **Modifier pour une entité juridique spécifique**).

![Afficher/modifier une entité juridique spécifique](media/ToggleToEditForAllLegalEntities.PNG)

De plus, dans la structure de la catégories de produits vendus au détail améliorée, un responsable de vente peut désormais définir des valeurs par défaut pour un ensemble de propriétés de produit supplémentaires au niveau de la catégorie individuelle. Ensuite, lors de la création des produits, ces valeurs de propriété de produit par défaut sont héritées par un produit, selon l'association de ces propriétés à une catégorie individuelle de la hiérarchie des produits vendus au détail. Ces propriétés de produit héritées peuvent également être modifiées pour chaque produit, afin de répondre aux exigences de l'entreprise.

## <a name="selecting-properties-to-update-products-on-the-retail-product-hierarchy-page"></a>Sélection des propriétés pour mettre à jour les produits sur la page de la hiérarchie de produits vendus au détail

Vous pouvez utiliser la nouvelle structure améliorées pour les propriétés de produit afin de sélectionner les propriétés de produit mises à jour devant être incluses dans les produits associés. Dans la page **Hiérarchie des produits vendus au détail**, dans le volet Actions, sélectionnez **Catégorie**, puis **Mettre à jour les produits** pour ouvrir la boîte de dialogue **Mettre à jour les produits**.

![Boîte de dialogue Mettre à jour les produits](media/NewUpdateProductsEnhancedView.PNG)


