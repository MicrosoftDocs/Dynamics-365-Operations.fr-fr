---
title: "Hiérarchies des ventes au détail"
description: "Cet article décrit les hiérarchies de ventes au détail dans Microsoft Dynamics 365 for Retail."
author: jblucher
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations, Retail
ms.custom: 15851
ms.assetid: dfa11d41-2a0c-4cde-99b6-058c49176c94
ms.search.region: global
ms.search.industry: Retail
ms.author: jeffbl
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.translationtype: Human Translation
ms.sourcegitcommit: 59b51840c05fe649cf322bfa64737a321728a5aa
ms.openlocfilehash: a425680fb4d2e2da8d96acd843694ea9a07e29f0
ms.contentlocale: fr-fr
ms.lasthandoff: 06/20/2017

---

# <a name="retail-hierarchies"></a>Hiérarchies des ventes au détail

[!include[banner](includes/banner.md)]


Cet article décrit les hiérarchies de ventes au détail dans Microsoft Dynamics 365 for Retail.

Vous pouvez créer une hiérarchie de catégories de vente au détail pour organiser les produits que vous vendez via vos canaux de vente au détail. Vous pouvez utiliser les hiérarchies des produits vendus au détail pour classer par catégorie ou regrouper les produits. Vous pouvez ensuite utiliser ces produits pour créer des assortiments de produits et des programmes de fidélisation des clients. Vous pouvez également affecter des attributs et des propriétés de produit, affecter une structure de tarification, inclure les produits dans des promotions de produit et utiliser les produits pour la génération d'états. Vous pouvez créer une hiérarchie de catégories de vente au détail pour représenter tous les produits et toutes les catégories dans votre organisation, puis utiliser cette hiérarchie de catégories à plusieurs fins. Sinon, vous pouvez créer plusieurs hiérarchies de catégories de vente au détail à des fins particulières, telles que les promotions de produit. Lorsque vous créez une hiérarchie des produits vendus au détail, vous devez affecter un type de hiérarchie de catégories pour identifier l'objectif de la hiérarchie de catégories. Par exemple, seules les hiérarchies de produit qui sont affectées au type **Hiérarchie de navigation de vente au détail** sont référencées lorsque vous parcourez les produits par catégorie en ligne ou dans le point de vente.

## <a name="retail-hierarchy-types"></a>Types de hiérarchie de vente au détail
Le tableau suivant répertorie les types de hiérarchies de catégories de vente au détail disponibles et l'utilisation générale de chaque type.

| Type de hiérarchie de catégories       | Objectif                                                                                                                                                                                                                                                                                                            |
|-------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Hiérarchie des produits vendus au détail      | Ce type de hiérarchie permet de définir la hiérarchie des produits globale pour votre organisation. Vous pouvez utiliser ce type de hiérarchie pour le commerce, la tarification et les promotions, la génération d'états et la planification d'assortiment. Seule une hiérarchie des produits vendus au détail peut être affectée à ce type de hiérarchie.                                       |
| Hiérarchie supplémentaire des ventes au détail | Utilisez ce type de hiérarchie pour toute hiérarchie de catégories de vente au détail supplémentaire que vous souhaitez créer. Par exemple, au printemps, vous bénéficiez d'une promotion sur les vêtements de natation. Par conséquent, vous devez inclure vos vêtements de natation dans une hiérarchie de catégories distincte et appliquer la tarification promotionnelle aux différentes catégories de produit. |
| Hiérarchie de navigation de vente au détail   | Utilisez ce type de hiérarchie pour regrouper et organiser les produits en catégories afin de pouvoir les parcourir en ligne ou dans un point de vente.                                                                                                                                                                                       |

À l'aide d'une hiérarchie de catégories de vente au détail pour structurer vos produits, vous pouvez paramétrer et tenir à jour les attributs de produit et les propriétés au niveau de la catégorie. Ces attributs et propriétés incluent des paramètres pour les dimensions de produit et les paramètres du point de vente. Tous les produits que vous affectez aux catégories héritent automatiquement des attributs et des propriétés que vous définissez. Vous pouvez également copier en même temps les paramètres de propriété de tout produit pour plusieurs produits dans une catégorie sélectionnée.



