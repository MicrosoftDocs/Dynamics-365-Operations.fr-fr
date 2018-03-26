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


# <a name="enhanced-product-and-category-management"></a>Gestion des catégories et des produits améliorée

[!include[banner](./includes/banner.md)]

Cette rubrique décrit une manière améliorée de gérer des catégories de produits vendus au détail et des produits vendus au détail dans Dynamics 365 for Retail. Ces améliorations permettent aux responsables des ventes d'afficher une structure commune de propriétés de produit entre la hiérarchie des produits de détail et les détails des produits lancés.

Pour en savoir plus sur la gestion des catégories de produits vendus au détail, accédez à **Hiérarchie des produits vendus au détail** dans l'espace de travail **Gestion des catégories et des produits**, et prenez note de la structure améliorée de la page **Catégorie de produits vendus au détail**.

![Espace de travail Gestion des catégories et des produits](media/LaunchRetailProductHierarchy.png)

Dans les versions précédentes, les propriétés du produit étaient divisées en **propriétés de base du produit** et en **propriétés du produit vendu au détail**, en fonction de l'étendue de leur applicabilité. Les **propriétés du produit vendu au détail** étaient *globales* en fonction de l'étendue de leur applicabilité, ce qui signifie que pour une **propriété de produit vendu au détail** donné, la même valeur est partagée entre toutes les entités juridiques. Les **propriétés de produit de base** sont *spécifiques à une entité juridique*. En d'autres termes, pour une **propriété de produit de base** donnée, la valeur peut être différente entre les entités juridiques, selon les exigences de l'entreprise.

Dans la structure de la catégorie de produit vendu au détail améliorée, les propriétés du produit sont séparées de manière logique en fonction de leur applicabilité au sein d'un groupe, afin de refléter la structure des écrans de détails de produit.

![Regroupement des champs selon leur portée d'applicabilité](media/NoticeGroupingOfFieldsBasedOnTheirScope.PNG)

Vous pouvez basculer entre la gestion des propriétés spécifiques à l'entité juridique dans toutes les entités juridiques et leur gestion pour une entité juridique spécifique. Pour cela, sélectionnez **Afficher ou modifier pour toutes les entités juridiques** ou **Afficher/Modifier pour une entité juridique spécifique**.

![Basculer entre la vue d'un individu et toutes les entités juridiques](media/ToggleBackToEditForSpecificLegalEntity.PNG)

![Basculer entre la vue d'un individu et toutes les entités juridiques](media/ToggleToEditForAllLegalEntities.PNG)  

Comparée aux versions précédentes, dans la nouvelle structure de la catégories de produits vendus au détail, responsable de vente peut également définir des valeurs par défaut pour un ensemble de propriétés de produit supplémentaires à un niveau de catégorie individuel. Lors de la création du produit, ces valeurs de propriété de produit par défaut sont héritées par un produit, selon son association à une catégorie individuelle de la hiérarchie des produits vendus au détail. Ces propriétés de produit héritées peuvent également être modifiées pour chaque produit, afin de répondre aux exigences de l'entreprise.

## <a name="select-properties-to-update-products-from-the-retail-product-category-form"></a>Sélectionner les propriétés pour mettre à jour les produits du formulaire de la catégorie de produits vendus au détail 
 
Vous pouvez utiliser cette nouvelle structure améliorées pour les propriétés de produit afin de sélectionner les propriétés de produit mises à jour devant être incluses dans les produits associés. 

![Nouvelle vue améliorée de Mettre à jour les produits](media/NewUpdateProductsEnhancedView.PNG) 

Les responsables des ventes peuvent modifier ces propriétés de produit héritées pour chaque produit, afin de répondre aux exigences de l'entreprise.


