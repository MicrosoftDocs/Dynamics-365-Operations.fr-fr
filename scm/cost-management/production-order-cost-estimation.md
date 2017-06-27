---
title: "Estimation de coût de l'ordre de fabrication"
description: "Cet article fournit des informations sur l'estimation du coût de production. L'estimation du coût de production fournit les coûts de consommation de matière et de capacité projetés liés à la production d'un article dans la quantité de l'ordre de fabrication planifiée."
author: YuyuScheller
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: BOMCalcTrans, InventCostTrans, ProdCalcTrans, ProdTableJour, ProdTableListPage
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 80633
ms.assetid: b4625d10-c852-4fda-b718-79df458de0d4
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: mguada
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: 9ae0bbb641d7517d33ad087faec231cb0bda3f78
ms.contentlocale: fr-fr
ms.lasthandoff: 05/25/2017


---

# <a name="production-order-cost-estimation"></a>Estimation de coût de l'ordre de fabrication

[!include[banner](../includes/banner.md)]


Cet article fournit des informations sur l'estimation du coût de production. L'estimation du coût de production fournit les coûts de consommation de matière et de capacité projetés liés à la production d'un article dans la quantité de l'ordre de fabrication planifiée. 

Après avoir créé un ordre de fabrication, vous devez estimer les coûts de production. L'objectif consiste à évaluer la consommation d'article et de gamme pour le processus de production parce que ces estimations sont utilisées en guise de base des processus de planification et de fabrication suivants.

## <a name="production-cost-estimation"></a>Estimation de coût de production
Les estimations des coûts de production sont basées sur les informations suivantes :

-   La quantité figurant sur l'ordre de fabrication
-   Les composants figurant sur les nomenclatures de production
-   Les opérations d'acheminement de la gamme de production
-   Les coûts indirects qui s'appliquent aux composants et aux opérations
-   Les données actives de coûts à la date du calcul

S'il y a une ligne fantôme dans les nomenclatures de production, les calculs reflètent les composants et les opérations de gamme du fantôme. Vous pouvez utiliser la tâche d'estimation pour recalculer les coûts estimés afin qu'ils reflètent les informations mises à jour. Par exemple, les informations mises à jour peuvent être des modifications de la quantité de l'ordre de fabrication, les composants des nomenclatures de production, les opérations de gamme dans la gamme de production, les coûts indirects qui s'appliquent à ces composants et opérations ou les données actives de coûts telles que la date de recalcul. Les calculs des coûts estimés suggèrent également un prix de vente pour l'article de production basé sur une approche coût plus marge sur coûts d'achat. Les calculs des coûts estimés peuvent éventuellement s'appliquer aux documents de référence qui reflètent les autres ordres de fabrication associés à l'ordre de fabrication.

## <a name="view-the-estimated-costs"></a>Afficher les coûts estimés
Après avoir exécuté l'estimation, vous pouvez afficher les résultats sur la page **Calcul du prix**. L'estimation calcule les valeur suivantes :

-   **Coût de production** : le coût de production correspond à la ligne supérieure de l'estimation. Elle présente le coût complet de l'exécution de l'ordre de fabrication et le prix de vente total de la production. C'est la somme de toutes les lignes de coût de l'estimation.
-   **Coûts de gamme ou de ressource** : les coûts de gamme ou de ressources correspondent aux coûts des opérations de production. Ils incluent le coût d'éléments comme le temps de réglage, le temps d'exécution, et les frais généraux.
-   **Coûts des matières** : les coûts des matières correspondent aux coûts et aux prix des composants de la nomenclature nécessaires pour produire l'article. Ces coûts ont été précédemment établis et entrés dans le système.

## <a name="other-uses-of-cost-estimation"></a>Autres usages d'une estimation des coûts
Une estimation des coûts fournit également les informations suivantes :

-   des devis significatifs ;
-   des estimations de la rentabilité de la commande ;
-   des estimations de l'utilisation de matières premières ;
-   des comparaisons d'informations de coûts à partir de productions précédentes ;
-   des informations de budget et de prévision ;
-   des estimations de la taille de production requise pour maintenir un coût particulier.





