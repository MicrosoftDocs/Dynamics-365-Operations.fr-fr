---
title: "Planification de la demande pour la couverture de site, entrepôt obligatoire"
description: "Cette rubrique décrit comment un article disposant du site comme dimension de couverture est planifié. L&quot;entrepôt est une dimension obligatoire."
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
ms.custom: 2454
ms.assetid: aa135030-f98c-48bf-902c-e52f680dc247
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: roxanad
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 9ccbe5815ebb54e00265e130be9c82491aebabce
ms.openlocfilehash: 4c595aa9809e37ba752b76f559ef909c071eb303
ms.lasthandoff: 03/31/2017


---

# <a name="master-planning-for-site-coverage-mandatory-warehouse"></a>Planification de la demande pour la couverture de site, entrepôt obligatoire

Cette rubrique décrit comment un article disposant du site comme dimension de couverture est planifié. L'entrepôt est une dimension obligatoire.

Ce scénario de planification implique les conditions suivantes :

-   La dimension de site est définie sur obligatoire et doit être entrée dans la transaction de demande. Ce paramètre ne peut pas être modifié.
-   La dimension d'entrepôt est définie sur obligatoire et doit être entrée dans la transaction de demande.
-   La dimension de site est définie pour la planification de la couverture. D'autres dimensions peuvent également être définies pour la planification de la couverture. Elles ne sont toutefois pas affectées par la fonctionnalité multisite.
-   La dimension d'entrepôt n'est pas définie pour la planification de la couverture. Par conséquent, l'offre et la demande sont agrégées par site (et d'autres dimensions planifiées, éventuellement).

Le graphique suivant illustre l'exécution du calcul de planification. Les paramètres indiqués dans le graphique, et leurs emplacements, sont les suivants :
-   La couverture d'article est définie pour l'article. Cliquez sur ** produits lancés de produits &gt; de gestion&gt; des informations sur le produit **. Sélectionnez l'article, puis cliquez sur ** couverture &gt; de l'article de plan **.
-   Des relations de rechargement sont définies pour l'entrepôt. Cliquez sur ** entrepôts &gt; de répartition &gt; de stock Paramétrage &gt; de Gestion des stocks **. Dans l'onglet **Planification**, voir le groupe de champs **Entrepôt principal**.
-   Le type de commande par défaut est défini à Production, Commande fournisseur, ou Kanban. Cliquez sur ** produits lancés de produits &gt; de gestion&gt; des informations sur le produit **. Sélectionnez l'article, puis cliquez sur ** planifier &gt; des paramètres de commande par défaut **. Dans l'écran **Paramètres de commande par défaut**, voir le **Type de commande par défaut**.

![Demande pour l'entrepôt de couverture du site obligatoire](./media/multisitedemandexplosionscenarioforsitecoveragewarehousemandatory.jpg)



<a name="see-also"></a>Voir également :
--------

[Master planning and multisite functionality](master-plan-multisite-functionality.md)

[Planification - couverture du site et de l'entrepôt, entrepôt obligatoire](master-plan-site-warehouse-coverage-warehouse-mandatory.md)

[Planification - couverture de site. entrepôt obligatoire] (master-plan-site-coverage-warehouse-mandatory.md)

[Planification - couverture du site et de l'entrepôt, entrepôt non obligatoire](master-plan-site-warehouse-coverage-warehouse-not-mandatory.md)

[Planification - Méthode de détermination de la version de nomenclature](master-plan-bom-version-determined.md)


