---
title: "Planification de la demande pour la couverture de site et d&quot;entrepôt, entrepôt non obligatoire"
description: "Cette rubrique décrit comment un article disposant d&quot;un site et d&quot;un entrepôt comme dimensions de couverture est planifié. La dimension d&quot;entrepôt n&quot;est pas obligatoire."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: EcoResStorageDimensionGroup, ReqItemTable
audience: Application User
ms.reviewer: YuyuScheller
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 2514
ms.assetid: 92d47bdd-df68-4f60-ac9a-96aa08236c26
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: roxanad
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 9ccbe5815ebb54e00265e130be9c82491aebabce
ms.openlocfilehash: 3671024dc097c94638b1579d7cacc8447c49e97b
ms.lasthandoff: 03/31/2017


---

# <a name="master-planning-for-site-and-warehouse-coverage-warehouse-not-mandatory"></a>Planification de la demande pour la couverture de site et d'entrepôt, entrepôt non obligatoire

Cette rubrique décrit comment un article disposant d'un site et d'un entrepôt comme dimensions de couverture est planifié. La dimension d'entrepôt n'est pas obligatoire.

Ce scénario de planification implique les conditions suivantes :

-   La dimension de site est définie sur obligatoire et doit être entrée dans la transaction de demande. Ce paramètre ne peut pas être modifié.
-   La dimension d'entrepôt n'est pas obligatoire. L'entrepôt peut être connu mais n'est pas utilisé dans le calcul de planification.
-   Les dimensions de site et d'entrepôt sont définies pour la planification de la couverture. D'autres dimensions peuvent également être définies pour la planification de la couverture. Elles ne sont toutefois pas affectées par la fonctionnalité multisite.

Le graphique suivant illustre l'exécution du calcul de planification. Les paramètres indiqués dans le graphique, et leurs emplacements, sont les suivants :
-   L'entrepôt est défini sur Manuel. Cliquez sur ** entrepôts &gt; de répartition &gt; de stock Paramétrage &gt; de Gestion des stocks **. Dans l'organisateur **Planification**, voir le champ **Manuel**.
-   La couverture d'article est définie pour l'article. Cliquez sur ** produits lancés de produits &gt; de gestion&gt; des informations sur le produit **. Sélectionnez l'article, puis, dans le volet Actions, sous ** plan ** l'onglet, cliquez sur ** couverture de l'article **.
-   Des relations de rechargement sont définies pour l'entrepôt. Cliquez sur ** entrepôts &gt; de répartition &gt; de stock Paramétrage &gt; de Gestion des stocks **. Dans l'organisateur **Planification**, voir le groupe de champs **Entrepôt principal**.
-   Le type de commande par défaut est défini à Production, Commande fournisseur, ou Kanban. Cliquez sur ** produits lancés de produits &gt; de gestion&gt; des informations sur le produit **. Sélectionnez l'article, puis, dans le volet Actions, sous ** plan ** l'onglet, cliquez sur ** transférez les paramètres d'ordre **. Dans l'écran **Paramètres de commande par défaut**, voir le **Type de commande par défaut**.

![Demande pour le site et l'entrepôt, pas l'entrepôt](./media/multisitedemandexplosionscenarioforsiteandwarehousecoveragewarehousenotmandatory.jpg)

 
-



<a name="see-also"></a>Voir également :
--------

[Master planning and multisite functionality](master-plan-multisite-functionality.md)

[Planification - couverture du site et de l'entrepôt, entrepôt obligatoire](master-plan-site-warehouse-coverage-warehouse-mandatory.md)

[Planification - couverture du site, entrepôt obligatoire](master-plan-site-coverage-warehouse-mandatory.md)

[Planification - couverture du site, entrepôt no obligatoire](master-plan-site-coverage-warehouse-not-mandatory.md)

[Planification - Méthode de détermination de la version de nomenclature](master-plan-bom-version-determined.md)


