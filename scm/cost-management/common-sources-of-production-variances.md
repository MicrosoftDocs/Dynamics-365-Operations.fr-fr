---
title: "Sources courantes des écarts de production"
description: "Cet article décrit diverses sources typiques de chaque type d&quot;écart de production."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: InventCostTrans
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 79753
ms.assetid: 14ac7db4-fb40-43c1-bb0d-1d51fc91d24f
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: mguada
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: fd3392eba3a394bd4b92112093c1f1f9b894426d
ms.openlocfilehash: 2961e5b9ffe727fba8c61c947de3db46518c5035
ms.contentlocale: fr-fr
ms.lasthandoff: 04/25/2017


---

# <a name="common-sources-of-production-variances"></a>Sources courantes des écarts de production

[!include[banner](../includes/banner.md)]


Cet article décrit diverses sources typiques de chaque type d'écart de production. 

Voici quelques sources typiques d'écart de **taille de lot** :

-   La quantité correcte d'un ordre de fabrication diffère de la quantité de calcul utilisée dans le calcul de coût standard. La quantité fournit la base pour l'amortissement des coûts constants.
-   La valeur des coûts constants de l'ordre de fabrication diffère des coûts constants utilisés dans le calcul du coût standard. Les coûts constants de l'ordre de fabrication peuvent être différents pour plusieurs raisons. Par exemple, les coûts constants peuvent refléter les facteurs suivants :
    -   les modifications manuelles apportées à la nomenclature de production ou gamme ;
    -   la sélection d'une autre version de nomenclature ou version de gamme lors de la création de l'ordre de fabrication ;
    -   des modifications d'ingénierie planifiées à la version de nomenclature ou version de gamme affectée à l'article.

Voici quelques sources typiques d'écart de **prix de production** :

-   La catégorie de coûts (et son prix de catégorie de coûts) pour la consommation déclarée d'une opération d'acheminement diffère de la catégorie de coûts utilisée dans le calcul de coûts standard.
-   Le coût actif pour le prix de la catégorie de coûts diffère du prix de la catégorie de coûts utilisé dans le calcul du coût standard.

Voici quelques sources typiques d'écart de **quantité de production** :

-   Vous effectuez une sortie excessive ou insuffisante d'un composant de matériau.
-   Vous déclarez des heures excessives ou insuffisantes pour une opération d'acheminement.
-   Vous déclarez la réception de manière excédentaire ou insuffisante de la quantité correcte de l'article parent par rapport à la quantité commandée. Toutefois, vous sortez les composants et déclarez les opérations selon la quantité de la commande pour l'ordre de fabrication.

Voici quelques sources typiques d'écart d'une **substitution de production** :

-   Vous sortez un composant de matériau absent de la nomenclature de production.
-   Vous ajoutez manuellement un composant à la nomenclature de production et déclarez ce composant comme étant consommé.
-   Vous déclarez un article comme étant consommé sans l'ajouter manuellement à la nomenclature de production.
-   Vous ajoutez manuellement une opération à la gamme de production et déclarez cette opération comme étant consommée.
-   Lorsque vous créez l'ordre de fabrication, vous sélectionnez une version de nomenclature différente de celle utilisée dans le calcul de coûts standard.
-   Lorsque vous créez l'ordre de fabrication, vous sélectionnez une version de gamme différente de celle utilisée dans le calcul de coûts standard.





