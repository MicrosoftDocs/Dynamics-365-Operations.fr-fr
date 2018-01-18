---
title: Calculs de nomenclature
description: "Les calculs de repositionnement des coûts et des prix de vente sont qualifiés de calculs de la nomenclature et vous pouvez les exécuter à partir de la page Calculs. Cette rubrique fournit des informations sur les calculs BOM."
author: AndersGirke
manager: AnnBe
ms.date: 04/10/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: BOMCalcDialog, BOMCalcTable, CostingVersion, InventItemPrice, SalesQuotationTable, SalesTable, SMAServiceOrderTable
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 273763
ms.assetid: c6fa3348-eafa-4847-9132-e65c5f55cbf4
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: yuyus
ms.dyn365.ops.version: AX 7.0.0
ms.search.validFrom: 2016-02-28
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: ad00a3b5e41892aaa705fd8eafa52cc199e1d806
ms.contentlocale: fr-fr
ms.lasthandoff: 11/06/2017

---

# <a name="bom-calculations"></a>Calculs de nomenclature

[!include[banner](../includes/banner.md)]


Les calculs de repositionnement des coûts et des prix de vente sont qualifiés de calculs de la nomenclature et vous pouvez les exécuter à partir de la page Calculs. Cette rubrique fournit des informations sur les calculs BOM.

Les calculs de repositionnement des coûts et des prix de vente sont qualifiés de calculs de la nomenclature et vous pouvez les exécuter à partir de la page **Calculs**. Utilisez la page **Calculs** pour exécuter les tâches suivantes :

-   Calculez le coût d'un article fabriqué et générez un enregistrement de coût d'article associé dans une version d'évaluation des coûts.
-   Calculez le prix de vente d'un produit fabriqué et générez un prix de vente de produit associé sous une version d'évaluation des coûts.

La façon dont vous utilisez la page **Calculs** varie légèrement, selon la façon dont vous lancez les calculs de nomenclature. L'utilisation de la page **Calculs** varie aussi si les calculs de nomenclature impliquent une version d'évaluation des coûts pour les coûts standard ou pour les coûts planifiés, et en fonction de plusieurs stratégies définies dans la version d'évaluation des coûts employée pour les calculs de nomenclature. **Remarque :** une variante de la page **Calculs** est utilisée dans le contexte d'une ligne de commande client, d'un devis de vente ou d'une commande de service. Ces calculs sont appelés calculs de nomenclature spécifiques à une commande. Un calcul de nomenclature spécifique à la commande ne génère pas un enregistrement des coûts d'un article dans une version d'évaluation des coûts. Au lieu de cela, il génère un enregistrement de calcul qui apparaît sur la page **Détails de calcul de nomenclature**. L'enregistrement de calcul comprend un coût calculé et un prix de vente calculé. Il est possible d'accéder à la page **Calculs** pour un article fabriqué ou pour une version d'évaluation des coûts :

-   Pour calculer les coûts d'un article fabriqué spécifique, lancez les calculs de nomenclature dans la page **Prix de l'article**. La page **Calculs** hérite de l'identificateur d'article. La version d'évaluation des coûts, la version de nomenclature, la version de gamme, la quantité du calcul, la date du calcul, et le site doivent être spécifiés.
    -   Par défaut, la version de nomenclature et la version de gamme sont les versions actives pour l'article, le site, la date, et la quantité du calcul. Toutefois, vous pouvez remplacer les valeurs par défaut par des versions approuvées.
    -   Par défaut, la quantité calculée est la quantité de commande standard de l'article. Toutefois, l'utilisateur peut remplacer la valeur par défaut.
    -   La date ou le site de calcul peut être mandaté par la version d'évaluation des coûts ou autoriser les valeurs spécifiées par l'utilisateur lorsque la date ou le site n'est pas mandaté dans la version d'évaluation des coûts. Une date de calcul future détermine la façon dont les enregistrements de coût en attente sont utilisés. Dans ce cas, les calculs de nomenclature s'effectueront sur un enregistrement de coût en attente ayant une date de début proche ou antérieure à la date de calcul.
-   La page **Paramétrage de la version d'évaluation des coûts** ou la page **Mise à jour de la version d'évaluation des coûts** permet d'effectuer des calculs de nomenclature afin de calculer les coûts de tous les articles fabriqués ou des articles sélectionnés, ou afin de mettre à jour des articles pour un cas d'emploi. La page **Calculs** hérite de la version d'évaluation des coûts.
    -   Pour ces calculs, vous devez disposer de la version de nomenclature et de la version de gamme en vigueur pour un article fabriqué (et pour le site, la date et la quantité correspondants) sauf si un composant fabriqué possède une sous-nomenclature et une sous-version spécifiée.
    -   Pour les calculs, il est supposé que la quantité de commande standard est utilisée pour les articles fabriqués. La quantité de commande standard sert de base au calcul de quantités de composants, à la détermination des versions de nomenclature et des versions de gamme appropriées (lorsque vous employez des nomenclatures et des gammes pour lesquelles la quantité est importante) et à l'amortissement de coûts constants. Toutefois, ces exigences ne s'appliquent pas lorsqu'un composant fabriqué possède un type de ligne de **Production** ou **Fournisseur** ou lorsque vous utilisez le mode Éclatement de création dans la commande pour les calculs de nomenclature, car les quantités reflèteront la quantité de calcul spécifiée.
    -   La date ou le site de calcul peut être mandaté par la version d'évaluation des coûts ou autoriser les valeurs spécifiées par l'utilisateur lorsque la date ou le site n'est pas mandaté dans la version d'évaluation des coûts.

D'autres variations de calculs de nomenclature reflètent le type d'évaluation des coûts et les restrictions de la version d'évaluation des coûts :

-   Les calculs de nomenclature qui utilisent des coûts standard doivent être limités par des stratégies de version d'évaluation des coûts, car les restrictions ainsi appliquées garantissent le respect des principes d'évaluation des coûts standard. Ces derniers requièrent l'application de restrictions relatives à l'utilisation de coûts standard pour les articles achetés, un mode d'éclatement à un seul niveau et l'ajout de frais divers dans les coûts unitaires.
-   Les calculs de nomenclature qui utilisent des coûts planifiés ne doivent pas nécessairement respecter les principes d'évaluation des coûts standard. Ils peuvent employer des modes d'éclatement différents, d'autres sources de données de coûts pour les articles achetés et, le cas échéant, appliquer des restrictions dans le cadre de la version d'évaluation des coûts.

### <a name="bom-calculations-that-use-standard-costs"></a>Calculs de nomenclature qui utilisent des coûts standard.

Les stratégies de la version d'évaluation des coûts (pour les coûts standard) peuvent mandater la mise en œuvre de cinq stratégies de calcul de nomenclature. Dans la version d'évaluation des coûts, l'option **Restrictions d'enregistrement** permet de mandater l'une de ces stratégies pour que les frais divers soient inclus dans le prix unitaire. Les frais divers des articles achetés peuvent être entrés manuellement, alors que les frais divers des articles fabriqués reflètent l'amortissement calculé des coûts constants. Dans la version d'évaluation des coûts, l'option **Restrictions de calcul** permet de mandater les quatre autres stratégies de calcul de nomenclature.

-   La source des contributions aux coûts pour les articles achetés doit s'appuyer sur des coûts standard. En d'autres termes, les calculs de nomenclature doivent utiliser les enregistrements de coût d'article dans la version d'évaluation des coûts spécifiée ou dans la version de secours qui contient les coûts standard.
-   Le mode Éclatement doit posséder un niveau unique pour garantir la précision et l'exactitude des calculs de coûts standard.
-   Le paramètre de profit doit être mandaté afin d'obtenir des résultats cohérents lors du calcul du prix de vente des articles. La version d'évaluation des coûts doit autoriser le contenu des prix de vente afin d'utiliser le paramètre de profit et de générer les enregistrements de prix de vente d'article.
-   Le principe de secours doit être mandaté et sa valeur peut être **Aucun**, **Actif** (pour les enregistrements de coût actifs) ou **Version d'évaluation des coûts** (pour une version d'évaluation des coûts spécifique).

### <a name="bom-calculations-that-use-planned-costs"></a>Calculs de nomenclature qui utilisent des coûts planifiés

Les stratégies de la version d'évaluation des coûts (pour les coûts planifiés) peuvent éventuellement mandater la mise en œuvre de cinq stratégies de calcul de nomenclature. Sinon, les stratégies peuvent simplement fournir des valeurs par défaut. Dans la version d'évaluation des coûts, l'option **Restrictions d'enregistrement** détermine si la stratégie de calcul de nomenclature sur les frais divers sera mandatée ou agira comme valeur par défaut. Le cas échéant, les frais divers peuvent être inclus dans le prix unitaire. Dans la version d'évaluation des coûts, l'option **Restrictions de calcul** détermine si les quatre autres stratégies de calcul de nomenclature seront mandatées ou agiront comme valeurs par défaut.

-   La source des contributions de coût pour un article acheté peut être les enregistrements de coût d'article dans une version d'évaluation des coûts. Sinon, la source peut être définie par le groupe de calcul de nomenclature affecté à l'article. Par exemple, le groupe de calcul de nomenclature peut définir des accords commerciaux sur les prix d'achat comme source de données de contribution de coût.
-   Le mode Éclatement peut comporter un ou plusieurs niveaux, s'appliquer à la création dans la commande ou s'appuyer sur une ligne de nomenclature. Le mode Éclatement du type de ligne de nomenclature duplique la logique de calcul des coûts pour les estimations d'ordre de fabrication.
-   Le paramètre de profit peut être mandaté ou correspondre à une valeur par défaut. La version d'évaluation des coûts doit autoriser le contenu des prix de vente afin d'utiliser le paramètre de profit et de générer les enregistrements de prix de vente d'article.
-   Le principe de secours peut être mandaté ou correspondre à une valeur par défaut. La valeur du principe de secours peut être **Aucun**, **Actif** (pour les enregistrements de coût actifs) ou **Version d'évaluation des coûts** (pour une version d'évaluation des coûts spécifique).

Les calculs de nomenclature génèrent des messages d'avertissement et des messages d'autres types. Plusieurs stratégies de calculs de nomenclature déterminent les types de messages. Les conditions d'avertissement en vigueur sont définies pour le groupe de calcul de nomenclature affecté aux articles. Toutefois, cous pouvez ignorer ces conditions d'avertissement lorsque vous exécutez un calcul de nomenclature. Lors de l'utilisation du principe de secours, il est souvent précieux d'afficher les informations correspondantes sous forme de messages. Lors des tentatives de mise à jour de coûts calculés pour des articles sans enregistrement de coût, il est également utile d'identifier sous la forme de messages les articles qui n'ont pas été mis à jour.

## <a name="bom-calculations-that-use-the-fallback-principle"></a>Calculs de nomenclature qui utilisent le principe de secours
Les situations suivantes illustrent deux utilisations du principe de secours :

-   **Approche à deux versions pour les mises à jour des coûts standard** – Une version d'évaluation des coûts peut contenir des modifications incrémentielles des coûts standard, telles que les enregistrements des coûts en attente qui représentent de nouveaux articles ou changements de coût. Dans ce cas, le principe de secours peut identifier l'utilisation des coûts standard actifs contenus dans d'autres versions d'évaluation des coûts.
-   **Simulation de l'effet de changements des coûts avec les coûts planifiés** − Une version d'évaluation des coûts planifiés peut contenir des modifications incrémentielles à des fins de simulation. Cette version d'évaluation des coûts peut inclure des enregistrements des coûts en attente qui représentent les changements de coût simulés pour des articles, des catégories de coûts et des formules de calcul des coûts indirects. Dans ce cas, le principe de secours peut identifier l'utilisation des coûts standard actifs contenus dans d'autres versions d'évaluation des coûts.

## <a name="bom-calculation-of-a-suggested-sales-price"></a>Calcul de nomenclature d'un prix de vente suggéré
Avec une approche du prix de revient majoré, le prix de vente calculé de l'article reflète la série de pourcentages de profits spécifiés pour le calcul de nomenclature et les coûts associés à ses composants, à ses opérations de gamme et à ses frais généraux de fabrication applicables. La majoration reflète les pourcentages de profits affectés aux groupes de coûts et les groupes de coûts affectés aux articles, aux catégories de coûts pour les opérations de gamme et les formules de calcul des coûts indirects pour les frais généraux de fabrication. Les séries de pourcentages de profits sont libellées **Standard**, **Profit 1**, **Profit 2**, et **Profit 3**. Dans la série Profit 1, par exemple, un pourcentage de profit de 50 pour cent peut être défini pour un groupe de coûts qui est affecté à des matériaux achetés et un pourcentage de profit de 80 pour cent peut être défini pour un groupe de coûts qui est affecté aux catégories de coûts pour les opérations de gamme. Le contexte du calcul de nomenclature détermine comment les résultats d'un prix de vente calculé sont gérés.

-   **Calcul de nomenclature pour un article et une version d'évaluation des coûts spécifiée** − Le calcul de nomenclature génère un enregistrement de prix de vente en attente dans la version d'évaluation des coûts. Cet enregistrement de prix de vente fournit le point de départ pour l'affichage des détails du calcul (par exemple, pour la page **Calculer le coût de l'article**). L'enregistrement du prix de vente est tout d'abord une information de référence et il ne sert pas de base à un prix de vente sur les commandes client.
-   **Calcul de nomenclature spécifique aux commandes** − Un écart dans la page **Calcul de nomenclature** est utilisé dans le contexte d'une ligne de commande client, de devis de vente ou de commande de service. Un calcul de nomenclature spécifique à une commande ne génère pas d'enregistrement dans une version d'évaluation des coûts. Au lieu de cela, il génère un enregistrement de calcul qui apparaît sur la page **Résultats du calcul de nomenclature**. Cet enregistrement de calcul fournit le point de départ pour l'affichage des détails du calcul (par exemple, pour la page **Calculer le coût de l'article**). Les informations relatives à l'enregistrement de calcul sélectionné peuvent être transférées vers la ligne d'origine. Par exemple, le prix de vente calculé peut être transféré vers la ligne de commande client.

## <a name="order-specific-bom-calculations"></a>Calculs de nomenclature spécifiques à la commande
Un calcul de nomenclature spécifique à la commande représente une variation d'un calcul de nomenclature pour un article fabriqué. Il est réalisé dans le cadre d'une ligne de commande client, de devis de vente ou de commande de service. Un calcul de nomenclature spécifique à la commande génère un enregistrement de calcul qui apparaît sur la page **Résultats du calcul de nomenclature**. Cet enregistrement comprend un poids calculé, un coût calculé basé sur les enregistrements de coûts actifs et un prix de vente calculé. Chaque calcul de nomenclature spécifique à la commande génère un enregistrement de calcul dans la page **Résultats du calcul de formule**, qui est identifié de manière unique par un numéro de calcul. Les résultats d'un enregistrement de calcul peuvent éventuellement être transférés vers la ligne d'origine. Un calcul de nomenclature spécifique à la commande se distingue d'un calcul de nomenclature pour un article fabriqué de deux façons :

-   Un calcul de nomenclature spécifique à la commande ne génère pas un enregistrement des coûts d'un article dans une version d'évaluation des coûts. Par conséquent, les stratégies de calcul de nomenclature ne s'appliquent pas à la création d'un enregistrement des coûts d'un article ni au remplacement d'un enregistrement des coûts.
-   Un calcul de nomenclature spécifique à la commande utilise toujours des enregistrements de coûts actifs pour les formules de calcul des coûts indirects, composants et catégories de coûts.






