---
title: "Planification pour la couverture du site et de l'entrepôt, entrepôt non obligatoire"
description: "Cette rubrique décrit comment un article disposant d'un site et d'un entrepôt comme dimensions de couverture est planifié. La dimension d'entrepôt n'est pas obligatoire."
author: roxanadiaconu
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
ms.custom: 2514
ms.assetid: 92d47bdd-df68-4f60-ac9a-96aa08236c26
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: roxanad
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: ec5150abd297a7c00ac180db581adb30bef65b3f
ms.contentlocale: fr-fr
ms.lasthandoff: 05/25/2017

---

# <a name="master-planning-for-site-and-warehouse-coverage-warehouse-not-mandatory"></a>Planification pour la couverture du site et de l'entrepôt, entrepôt non obligatoire

[!include[banner](../includes/banner.md)]


Cette rubrique décrit comment un article disposant d'un site et d'un entrepôt comme dimensions de couverture est planifié. La dimension d'entrepôt n'est pas obligatoire.

Ce scénario de planification implique les conditions suivantes :

-   La dimension de site est définie sur obligatoire et doit être entrée dans la transaction de demande. Ce paramètre ne peut pas être modifié.
-   La dimension d'entrepôt n'est pas obligatoire. L'entrepôt peut être connu mais n'est pas utilisé dans le calcul de planification.
-   Les dimensions de site et d'entrepôt sont définies pour la planification de la couverture. D'autres dimensions peuvent également être définies pour la planification de la couverture. Elles ne sont toutefois pas affectées par la fonctionnalité multisite.

Le graphique suivant illustre l'exécution du calcul de planification. Les paramètres indiqués dans le graphique, et leurs emplacements, sont les suivants :
-   L'entrepôt est défini sur Manuel. Cliquez sur **Gestion des stocks &gt; Paramétrage &gt; Décomposition du stock &gt; Entrepôts**. Dans l'organisateur **Planification**, voir le champ **Manuel**.
-   La couverture d'article est définie pour l'article. Cliquez sur **Gestion des informations sur les produits &gt; Produits &gt; Produits lancés**. Sélectionnez l'article, puis dans le volet Actions, sous l'onglet **Planifier**, cliquez sur **Couverture de l'article**.
-   Des relations de rechargement sont définies pour l'entrepôt. Cliquez sur **Gestion des stocks &gt; Paramétrage &gt; Décomposition du stock &gt; Entrepôts**. Dans l'organisateur **Planification**, voir le groupe de champs **Entrepôt principal**.
-   Le type de commande par défaut est défini à Production, Commande fournisseur, ou Kanban. Cliquez sur **Gestion des informations sur les produits &gt; Produits &gt; Produits lancés**. Sélectionnez l'article, puis dans le volet Actions, sous l'onglet **Planifier**, cliquez sur **Paramètres de commande par défaut**. Dans l'écran **Paramètres de commande par défaut**, voir le **Type de commande par défaut**.

![Demande pour le site et l'entrepôt, pas l'entrepôt](./media/multisitedemandexplosionscenarioforsiteandwarehousecoveragewarehousenotmandatory.jpg)

 
-



<a name="see-also"></a>Voir également :
--------

[Planification et fonctionnalité multisite](master-plan-multisite-functionality.md)

[Planification - couverture du site et de l'entrepôt, entrepôt obligatoire](master-plan-site-warehouse-coverage-warehouse-mandatory.md)

[Planification - couverture du site, entrepôt obligatoire](master-plan-site-coverage-warehouse-mandatory.md)

[Planification - couverture du site, entrepôt no obligatoire](master-plan-site-coverage-warehouse-not-mandatory.md)

[Planification - Méthode de détermination de la version de nomenclature](master-plan-bom-version-determined.md)



