---
title: "Versions d'évaluation des coûts"
description: "Cet article fournit des informations sur les versions d'évaluation des coûts, comment les tenir à jour, et les types de données que vous pouvez y inclure. L'objectif principal d'une version d'évaluation de coûts est de contenir des enregistrements de coûts relatifs aux articles, des catégories de coûts et des formules de calcul pour les coûts indirects."
author: AndersGirke
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: BOMCalcDialog, BOMCalcTable, CostingVersion
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 54532
ms.assetid: cd239da5-f434-4d1b-8196-5414c888d76d
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: yuyus
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 5d22abca3f55ffbe162060bd75191c480992d485
ms.contentlocale: fr-fr
ms.lasthandoff: 09/29/2017

---

# <a name="costing-versions"></a>Versions d'évaluation des coûts

[!include[banner](../includes/banner.md)]


Cet article fournit des informations sur les versions d'évaluation des coûts, comment les tenir à jour, et les types de données que vous pouvez y inclure. L'objectif principal d'une version d'évaluation de coûts est de contenir des enregistrements de coûts relatifs aux articles, des catégories de coûts et des formules de calcul pour les coûts indirects.

Une version d'évaluation des coûts peut servir un ou plusieurs objectifs, en fonction des données contenues dans la version d'évaluation des coûts. L'objectif principal d'une version d'évaluation de coûts est de contenir des enregistrements de coûts relatifs aux articles, des catégories de coûts et des formules de calcul pour les coûts indirects. Une version d'évaluation de coûts peut contenir une série d'enregistrements de coûts standard ou une série d'enregistrements de coûts planifiés basés sur le type d'évaluation des coûts qui lui est attribué.

## <a name="costing-versions-for-standard-or-planned-costs"></a>Versions d'évaluation des coûts pour des coûts standard ou planifiés.
### <a name="standard-costs"></a>Coûts standard

Une version d'évaluation de coûts peut prendre en charge un modèle de stock de coûts standard pour les articles, dans la mesure où la version d'évaluation de coûts contient une série d'enregistrements de coûts standard relatifs aux articles et aux processus de fabrication. Les données de coût relatives aux processus de fabrication sont exprimées en termes de catégories de coûts pour les opérations de gamme et de formules de calcul pour les frais généraux de fabrication.

### <a name="planned-costs"></a>Coûts planifiés

Une version d'évaluation des coûts peut contenir un ensemble d'enregistrements de coûts planifiés sur les articles et les processus de fabrication. Une version d'évaluation des coûts qui contient des coûts planifiés sert souvent à prendre en charge des simulations de calcul des coûts, telles que la simulation des effets provoqués par la modification des coûts sur les matières achetées ou la simulation des processus de fabrication sur les coûts calculés des articles fabriqués. Les enregistrements des coûts d'articles pour les coûts planifiés peuvent également servir à prendre en charge un modèle de stock de coûts réels en fournissant les valeurs initiales pour les coûts d'articles. Ces valeurs incluent le calcul des coûts planifiés pour les articles fabriqués.

## <a name="entering-costs"></a>Saisie des coûts
La mise à jour des données pour les enregistrements des coûts dans une version d'évaluation des coûts implique la saisie des coûts pour les articles achetés et pour les articles transférés entre les sites. Une mise à jour supplémentaire des données pour les fabricants implique la saisie des coûts pour les catégories de coûts associées aux opérations d'acheminement, la saisie de formules de calcul pour les coûts indirects reflétant les frais généraux de fabrication et le calcul des coûts pour les articles fabriqués. 

Les données de coûts d'articles dans une version d'évaluation des coûts sont constituées d'un ou de plusieurs enregistrements de coûts pour chaque article. La première fois qu'un enregistrement de coûts d'articles est saisi, il est doté du statut **En attente** et une date d'effet choisie. Lorsque vous activez l'enregistrement des coûts d'articles, le statut est mis à jour sur **Actif**, et la date d'effet est mise à jour sur la date d'activation. Différents enregistrements de coûts d'articles peuvent refléter différents sites, différentes dates d'effet ou différents statuts. Lorsque vous calculez les coûts pour les articles fabriqués pour une date future, le calcul de nomenclature utilise les enregistrements de coûts dotés de la date d'effet appropriée, que le statut soit **En attente** ou **Actif**. L'enregistrement de coûts actif en cours d'un article permet d'estimer les coûts d'un ordre de fabrication et d'évaluer les mouvements de stock via un modèle de stock de coûts standard. La mise à jour des enregistrements de coûts pour les catégories de coûts et les formules de calcul des coûts indirects ressemble à la mise à jour des enregistrements des coûts d'article. 

Deux stratégies de blocage pour une version d'évaluation des coûts déterminent si les coûts en attente peuvent être mis à jour et si les coûts en attente peuvent être activés. Les stratégies de blocage permettent d'autoriser la mise à jour des données et ensuite d'empêcher la mise à jour des données pour les enregistrements de coûts dans une version d'évaluation des coûts. 

À des fins de calcul de nomenclature, une version d'évaluation des coûts peut également contenir des données sur les prix de vente ou les prix d'achat des articles.

## <a name="item-sales-prices-for-bom-calculations"></a>Prix de vente des articles pour les calculs de nomenclature
Le motif principal pour inclure des données relatives aux prix de vente est de conserver le prix de vente calculé d'un article fabriqué. Le prix de vente calculé peut ensuite être analysé pour déterminer la manière dont les composants, les opérations de gamme, et les frais généraux contribuent au coût et au prix de vente. 

Un motif secondaire pour inclure des données relatives aux prix de vente est de définir les enregistrements de prix de vente pour les composants. Ces enregistrements peuvent ensuite être utilisés pour calculer le prix de vente des articles fabriqués. Vous définissez d'abord le modèle de prix de vente qui est intégré à un groupe de calcul de nomenclature, puis affectez ce groupe à des articles achetés. Puis, lorsque vous exécutez des calculs de nomenclature utilisant des coûts planifiés, sélectionnez le modèle de prix de revient du groupe de calcul de nomenclature. 

Sinon, les enregistrements de prix de vente pour les articles servent uniquement d'informations de référence, qu'ils soient saisis manuellement ou calculés. En activant l'enregistrement de prix de vente d'un article, vous pouvez mettre à jour le prix de vente de base de l'article. Cependant, le prix de vente de base n'est pas spécifique à un site et peut être remplacé manuellement. Le prix de vente de base de l'article sert de prix de vente par défaut pour les commandes client et les devis de vente.

## <a name="item-purchase-prices-for-bom-calculations"></a>Prix d'achat des articles pour les calculs de nomenclature
Le motif principal pour l'activation des données de prix d'achat est de définir des enregistrements de prix d'achat pour des composants, qui peuvent ensuite servir à calculer les coûts des articles fabriqués. Les enregistrements de prix d'achat doivent être entrés manuellement. 

Pour ce faire, vous devez d'abord définir un groupe de calcul de nomenclature qui contient un modèle de prix de revient pour le prix d'achat de l'article, puis affecter le groupe de calcul de nomenclature aux articles achetés. Vous devez ensuite utiliser un modèle de prix de revient pour le groupe de calcul de nomenclature lors des calculs de nomenclature qui utilisent des coûts planifiés afin de calculer le prix de vente des articles fabriqués. 

Les enregistrements de prix d'achat des articles servent également d'informations de référence. En modifiant le statut d'un enregistrement de prix d'achat d'article pour le faire passer de **En attente** à **Actif**, vous pouvez mettre à jour le prix d'achat de base de l'article. Toutefois, le prix d'achat de base n'est pas spécifique à un site et peut être remplacé manuellement. Le prix d'achat de base de l'article sert de prix d'achat par défaut pour les commandes fournisseur.




