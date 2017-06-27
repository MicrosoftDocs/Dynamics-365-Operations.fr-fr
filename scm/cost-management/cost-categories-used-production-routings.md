---
title: "Catégories de coûts utilisées dans l'acheminement de la production"
description: "Cet article fournit des informations sur les catégories de coûts qui s'appliquent aux environnements de fabrication qui utilisent l'acheminement."
author: YuyuScheller
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: ProjCategory, RouteCostCategoryPrice
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 78153
ms.assetid: a3fdc76c-0a27-4723-b1c7-4322f707d89e
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: mguada
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: 12e712e0a28ada0716d35b7105fb20c354d1bc18
ms.contentlocale: fr-fr
ms.lasthandoff: 05/25/2017


---

# <a name="cost-categories-used-in-production-routing"></a>Catégories de coûts utilisées dans l'acheminement de la production

[!include[banner](../includes/banner.md)]


Cet article fournit des informations sur les catégories de coûts qui s'appliquent aux environnements de fabrication qui utilisent l'acheminement.

Des catégories de coûts s'appliquent aux environnements de fabrication qui utilisent l'acheminement. Elles sont affectées aux ressources opérationnelles et aux opérations d'acheminement afin de définir des coûts horaires et de segmenter les contributions de coûts dans les coûts calculés d'un article fabriqué. Les groupes de coûts affectés à des catégories de coûts classifient les contributions des coûts de fabrication selon les ressources opérationnelles et le type d'activité, comme les temps de réglage et d'exécution. La spécificité des affectations des groupes de coûts permet de calculer les frais généraux de fabrication en fonction des informations d'acheminement. 

**Remarque:** Dans les environnements de fabrication, les catégories de coûts ont plusieurs synonymes, comme les codes taux de main d'œuvre ou les codes taux de machine. 

Chaque catégorie de coût dispose d'enregistrements de coûts associés et d'un groupe de coûts affecté. Des catégories de coûts différentes sont nécessaires pour prendre en charge différents objectifs de production.

-   Affecter différents coûts horaires, selon la ressource opérationnelle. Par exemple, les coûts peuvent différer pour différents types de qualifications de travail, les machines ou les cellules de production.
-   Affecter différents coûts horaires pour le temps de réglage ou d'exécution associé à une opération de gamme.
-   Affecter des coûts de ressources opérationnelles sur la base de la quantité sortante plutôt que sur la base des coûts horaires, comme le taux à la pièce pour le paiement de la main d'œuvre.
-   Fournir la segmentation du groupe de coûts des contributions de coût pour le coût d'un article fabriqué. Par exemple, vous pouvez segmenter les coûts de travail et de machine.
-   Proposer la base du groupe de coûts pour les formules de calcul des frais généraux de fabrication, comme les formules pour les frais généraux liés à la main d'œuvre et aux machines ou ceux liés aux temps de réglage et d'exécution.

Une catégorie de coûts peut être affectée au temps de réglage, au temps d'exécution et à la quantité pour une opération d'acheminement. Lorsque, par exemple, la segmentation des coûts ou des groupes de coûts diffère entre le temps de réglage et le temps d'exécution, des catégories de coûts différentes doivent être définies et affectées aux temps de réglage et d'exécution. L'usage sélectif des catégories de coûts pour le temps de réglage, le temps d'exécution et la quantité est déterminé par le groupe de gammes affecté à une opération. L'affectation de catégories de coûts au temps et à la quantité peut être autorisée par des stratégies au niveau de la société qui sont définies dans la page **Paramètres de contrôle de la production**. 

Chaque catégorie de coûts dispose de coûts associés basés sur la définition des enregistrements des coûts dans une version d'évaluation des coûts. Utilisez la page **Prix des catégories de coûts** pour définir les enregistrements de coûts associés à une version d'évaluation des coûts et à un site spécifiques. Lorsque l'enregistrement des coûts pour une catégorie de coûts est entré au départ avec un statut **En attente** et une date d'effet choisie. Lorsque vous activez l'enregistrement des coûts, le statut est mis à jour sur **Actuellement actif**, et la date d'effet est mise à jour sur la date d'activation. Différents enregistrements de coûts peuvent refléter des sites, des dates d'effet ou des statuts différents. Les calculs de nomenclature (BOM) pour une date future ou passée utilisent les enregistrements de coûts possédant la date d'effet appropriée. L'enregistrement des coûts actuellement actif sera utilisé pour estimer les coûts des ordres de fabrication et évaluer le temps déclaré par rapport à un ordre de fabrication. 

L'enregistrement des coûts associé à une catégorie de coûts peut être spécifique à un site ou à une société. Pour effectuer un enregistrement des coûts spécifique à un site, lui affecter un site. Sinon, une valeur vide indique que l'enregistrement des coûts s'applique à tous les sites de la société. Comme les coûts peuvent différer entre plusieurs sites par exemple, les enregistrements de coûts doivent être définis comme étant spécifiques à un site. 

Généralement, une opération de gamme hérite des catégories de coûts affectées à la ressource opérationnelle ou à l'opération principale. Lors de la création d'un ordre de fabrication, les opérations de gamme de la gamme de production reflètent la version de gamme sélectionnée. Vous pouvez remplacer les catégories de coûts qui sont affectées aux opérations de la gamme de production. 

Certains types de travaux de production peuvent s'appliquer aux générations d'états et aux estimations de temps du projet. Dans ce cas, une catégorie de coûts est requise à des fins de production et de projet. Vous devez définir des informations supplémentaires relatives à un projet lorsqu'une catégorie de coûts est balisée à des fins d'utilisation dans des projets.




