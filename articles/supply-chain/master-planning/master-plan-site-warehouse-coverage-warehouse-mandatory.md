---
title: Planification pour la couverture du site et de l’entrepôt, entrepôt obligatoire
description: Cet article décrit comment un article disposant d’un site et d’un entrepôt comme dimensions de couverture est planifié. La dimension d’entrepôt n’est pas obligatoire.
author: t-benebo
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EcoResStorageDimensionGroup, ReqItemTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: 2554
ms.assetid: 3211e95f-b91a-4d27-8d92-f328ae2bcf12
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: benebotg
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: adcb2d41ff70714b6bc9c28f3e23ce95f5292f2e
ms.sourcegitcommit: 491ab9ae2b6ed991b4eb0317e396fef542d3a21b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/03/2022
ms.locfileid: "9740057"
---
# <a name="master-planning-for-site-and-warehouse-coverage-warehouse-mandatory"></a>Planification pour la couverture du site et de l’entrepôt, entrepôt obligatoire

[!include [banner](../includes/banner.md)]

Cet article décrit comment un article disposant d’un site et d’un entrepôt comme dimensions de couverture est planifié. La dimension d’entrepôt n’est pas obligatoire.

Ce scénario de planification implique les conditions suivantes :

-   La dimension de site est définie sur obligatoire et doit être entrée dans la transaction de demande.
-   La dimension d’entrepôt est définie sur obligatoire et doit être entrée dans la transaction de demande.
-   Les dimensions de site et d’entrepôt sont définies pour la planification de la couverture. D’autres dimensions peuvent également être définies pour la planification de la couverture. Elles ne sont toutefois pas affectées par la fonctionnalité multisite.

Le graphique suivant illustre l’exécution du calcul de planification. Les paramètres indiqués dans le graphique, et leurs emplacements, sont les suivants :
-   L’entrepôt est défini sur **Manuel**. Cliquez sur **Gestion des stocks &gt; Paramétrage &gt; Décomposition du stock &gt; Entrepôts**. Dans l’organisateur **Planification**, voir le champ **Manuel**.
-   La couverture d’article est définie pour l’article. Cliquez sur **Gestion des informations sur les produits &gt; Produits &gt; Produits lancés**. Sélectionnez l’article, puis dans le volet Actions, sous l’onglet **Planifier**, cliquez sur **Couverture de l’article**.
-   Des relations de rechargement sont définies pour l’entrepôt. Cliquez sur **Gestion des stocks &gt; Paramétrage &gt; Décomposition du stock &gt; Entrepôts**. Dans l’organisateur **Planification**, voir le groupe de champs **Entrepôt principal**.
-   Le type de commande par défaut est défini à Production, Commande fournisseur, ou Kanban. Cliquez sur **Gestion des informations sur les produits &gt; Produits &gt; Produits lancés**. Sélectionnez l’article, puis dans le volet Actions, sous l’onglet **Planifier**, cliquez sur **Paramètres de commande par défaut**. Dans l’écran **Paramètres de commande par défaut**, voir le **Type de commande par défaut**.

![Couverture de l’entrepôt et du site de la demande en cas d’obligation.](./media/multisitedemandexplosionscenarioforsiteandwarehousecoveragewarehousemandatory.jpg)



## <a name="additional-resources"></a>Ressources supplémentaires

- [Vue d’ensemble de planification générale et fonctionnalité multisite](master-plan-multisite-functionality.md)
- [Planification pour couverture de site, entrepôt obligatoire](master-plan-site-coverage-warehouse-mandatory.md)
- [Planification pour couverture de site, entrepôt non obligatoire](master-plan-site-coverage-warehouse-not-mandatory.md)
- [Planification de couverture de site et d’entrepôt, entrepôt non obligatoire](master-plan-site-warehouse-coverage-warehouse-not-mandatory.md)
- [Déterminer la version de nomenclature](master-plan-bom-version-determined.md)





[!INCLUDE[footer-include](../../includes/footer-banner.md)]