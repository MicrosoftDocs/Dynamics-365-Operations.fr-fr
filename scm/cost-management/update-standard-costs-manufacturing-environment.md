---
title: "Mise à jour des coûts standard dans un environnement de fabrication"
description: "Cet article fournit des instructions sur la mise à jour des coûts standard dans un environnement de fabrication."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: CostingVersion, InventStdCostConv
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 79663
ms.assetid: 3a7c3d13-8dbc-442d-a281-ac0ebe99ec83
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: mguada
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: 74ad59504d6bbea0c604e0f0b83e74c915e84019
ms.contentlocale: fr-fr
ms.lasthandoff: 05/25/2017


---

# <a name="update-standard-costs-in-a-manufacturing-environment"></a>Mise à jour des coûts standard dans un environnement de fabrication

[!include[banner](../includes/banner.md)]


Cet article fournit des instructions sur la mise à jour des coûts standard dans un environnement de fabrication. 

Les mises à jour peuvent refléter les nouveaux articles, les catégories de coûts ou les formules de calcul des coûts indirects. Elles peuvent également refléter des corrections et des modifications de coûts. Le type de mise à jour affecte les étapes nécessaires à exécuter pour mettre à jour les coûts standard, comme illustré dans les cas suivants :

-   Entrez les modifications prévues des coûts standard pour les articles achetés, puis modifiez le statut des enregistrements des coûts des articles à **Actif** à la date appropriée. Toutefois, ne recalculez pas les coûts des articles fabriqués qui utilisent les articles achetés.
-   Entrez les coûts standard pour un nouvel article acheté mais ne recalculez pas les coûts des articles fabriqués avec une version de nomenclature qui contient le nouvel article acheté comme composant.
-   Corrigez ou modifiez le coût d'un article acheté ou modifiez le groupe de coûts attribué à un article acheté et calculez le coût de tous les articles fabriqués avec une version de nomenclature qui contient l'article acheté comme composant.
-   Modifiez le coût pour une catégorie de coûts et calculez le coût de tous les articles fabriqués avec une version de gamme qui contient les opérations de gamme qui utilisent la catégorie de coûts.
-   Modifiez les catégories de coûts qui sont affectées aux opérations de gamme ou au groupe de coûts affecté aux catégories de coûts. Puis calculez le coût de tous les articles fabriqués avec une version de gamme qui contient les opérations de gamme qui utilisent la catégorie de coûts.
-   Modifiez une formule de calcul de coûts indirects et calculez le coût de tous les articles fabriqués concernés par la modification.
-   Modifiez ou ajoutez un site de fabrication pour un article fabriqué et calculez le coût de fabrication de l'article pour le site.
-   Calculez, ou recalculez, le coût d'un article fabriqué et recalculez le coût de tous les articles fabriqués avec une version de nomenclature qui contient l'article fabriqué comme composant.
-   Calculez les coûts pour un nouvel article fabriqué sur la base de sa nomenclature définie, approuvée et active et de ses informations de gamme.

Chaque cas nécessite un examen attentif de la façon de mettre à jour les coûts standard.




