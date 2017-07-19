---
title: "Planification pour couverture de site, entrepôt obligatoire"
description: "Cette rubrique décrit comment un article disposant du site comme dimension de couverture est planifié. L'entrepôt est une dimension obligatoire."
author: YuyuScheller
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: EcoResStorageDimensionGroup, ReqItemTable
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 2454
ms.assetid: aa135030-f98c-48bf-902c-e52f680dc247
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: roxanad
ms.search.validFrom: 2016-02-28T00:00:00.000Z
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: a1bf8f2253c63e4b6ca8fee02ec6b1cfb8aad73c
ms.contentlocale: fr-fr
ms.lasthandoff: 05/25/2017

---

# <a name="master-planning-for-site-coverage-mandatory-warehouse"></a>Planification pour couverture de site, entrepôt obligatoire

[!include[banner](../includes/banner.md)]


Cette rubrique décrit comment un article disposant du site comme dimension de couverture est planifié. L'entrepôt est une dimension obligatoire.

Ce scénario de planification implique les conditions suivantes :

-   La dimension de site est définie sur obligatoire et doit être entrée dans la transaction de demande. Ce paramètre ne peut pas être modifié.
-   La dimension d'entrepôt est définie sur obligatoire et doit être entrée dans la transaction de demande.
-   La dimension de site est définie pour la planification de la couverture. D'autres dimensions peuvent également être définies pour la planification de la couverture. Elles ne sont toutefois pas affectées par la fonctionnalité multisite.
-   La dimension d'entrepôt n'est pas définie pour la planification de la couverture. Par conséquent, l'offre et la demande sont agrégées par site (et d'autres dimensions planifiées, éventuellement).

Le graphique suivant illustre l'exécution du calcul de planification. Les paramètres indiqués dans le graphique, et leurs emplacements, sont les suivants :
-   La couverture d'article est définie pour l'article. Cliquez sur **Gestion des informations sur les produits &gt; Produits &gt; Produits lancés**. Sélectionnez l'article, puis cliquez sur **Plan &gt; Couverture de l'article**.
-   Des relations de rechargement sont définies pour l'entrepôt. Cliquez sur **Gestion des stocks &gt; Paramétrage &gt; Décomposition du stock &gt; Entrepôts**. Dans l'onglet **Planification**, voir le groupe de champs **Entrepôt principal**.
-   Le type de commande par défaut est défini à Production, Commande fournisseur, ou Kanban. Cliquez sur **Gestion des informations sur les produits &gt; Produits &gt; Produits lancés**. Sélectionnez l'article, puis cliquez sur **Plan &gt; Paramètres de commande par défaut**. Dans l'écran **Paramètres de commande par défaut**, voir le **Type de commande par défaut**.

![Demande pour l'entrepôt de couverture du site obligatoire](./media/multisitedemandexplosionscenarioforsitecoveragewarehousemandatory.jpg)



<a name="see-also"></a>Voir également :
--------

[Planification et fonctionnalité multisite](master-plan-multisite-functionality.md)

[Planification - couverture du site et de l'entrepôt, entrepôt obligatoire](master-plan-site-warehouse-coverage-warehouse-mandatory.md)

[Planification - couverture du site. entrepôt obligatoire](master-plan-site-coverage-warehouse-mandatory.md)

[Planification - couverture du site et de l'entrepôt, entrepôt non obligatoire](master-plan-site-warehouse-coverage-warehouse-not-mandatory.md)

[Planification - Méthode de détermination de la version de nomenclature](master-plan-bom-version-determined.md)




