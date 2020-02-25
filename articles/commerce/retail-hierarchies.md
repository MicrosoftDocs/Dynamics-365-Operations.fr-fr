---
title: Hiérarchies des ventes au détail
description: Cet article décrit les hiérarchies des ventes au détail dans Dynamics 365 Commerce.
author: jblucher
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: OMHierarchyManager
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 15851
ms.assetid: dfa11d41-2a0c-4cde-99b6-058c49176c94
ms.search.region: global
ms.search.industry: Retail
ms.author: jeffbl
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.openlocfilehash: cf8db2c828f99dfd4c220966e31894dcd6eda572
ms.sourcegitcommit: 81a647904dd305c4be2e4b683689f128548a872d
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/01/2020
ms.locfileid: "3022552"
---
# <a name="retail-hierarchies"></a>Hiérarchies des ventes au détail

[!include [banner](includes/banner.md)]

Cet article décrit les hiérarchies dans Dynamics 365 Commerce.

Vous pouvez créer une hiérarchie de catégories pour organiser les produits que vous vendez par vos canaux. Vous pouvez utiliser les hiérarchies de produits pour classer par catégorie ou regrouper les produits. Vous pouvez ensuite utiliser ces produits pour créer des assortiments de produits et des programmes de fidélisation des clients. Vous pouvez également affecter des attributs et des propriétés de produit, affecter une structure de tarification, inclure les produits dans des promotions de produit et utiliser les produits pour la génération d'états. Vous pouvez créer une hiérarchie de catégories pour représenter tous les produits et toutes les catégories dans votre organisation, puis utiliser cette hiérarchie de catégories à plusieurs fins. Sinon, vous pouvez créer plusieurs hiérarchies de catégories à des fins particulières, telles que les promotions de produit. Lorsque vous créez une hiérarchie de produits, vous devez affecter un type de hiérarchie de catégories pour identifier l'objectif de la hiérarchie de catégories. Par exemple, seules les hiérarchies de produits affectées au type **Hiérarchie de navigation de commerce** sont référencées lorsque vous parcourez les produits par catégorie en ligne ou dans le point de vente (PDV).

## <a name="hierarchy-types"></a>Types de hiérarchie

Le tableau suivant répertorie les types de hiérarchie de catégories disponibles et l'utilisation générale de chaque type.

| Type de hiérarchie de catégories       | Objectif |
|-------------------------------|---------|
| Hiérarchie de produit      | Ce type de hiérarchie permet de définir la hiérarchie des produits globale pour votre organisation. Vous pouvez utiliser ce type de hiérarchie pour le commerce, la tarification et les promotions, la génération d'états et la planification d'assortiment. Seule une hiérarchie de produits peut être affectée à ce type de hiérarchie. |
| Hiérarchie supplémentaire | Utilisez ce type de hiérarchie pour toutes les hiérarchies de catégories supplémentaires que vous souhaitez créer. Par exemple, au printemps, vous bénéficiez d'une promotion sur les vêtements de natation. Par conséquent, vous devez inclure vos vêtements de natation dans une hiérarchie de catégories distincte et appliquer la tarification promotionnelle aux différentes catégories de produit. |
| Hiérarchie de navigation   | Utilisez ce type de hiérarchie pour regrouper et organiser les produits en catégories afin de pouvoir les parcourir en ligne ou dans un point de vente. |

À l'aide d'une hiérarchie de catégories pour structurer vos produits, vous pouvez configurer et tenir à jour les attributs de produit et les propriétés au niveau de la catégorie. Ces attributs et propriétés incluent des paramètres pour les dimensions de produit et les paramètres du point de vente. Tous les produits que vous affectez aux catégories héritent automatiquement des attributs et des propriétés que vous définissez. Vous pouvez également copier en même temps les paramètres de propriété de tout produit pour plusieurs produits dans une catégorie sélectionnée.
