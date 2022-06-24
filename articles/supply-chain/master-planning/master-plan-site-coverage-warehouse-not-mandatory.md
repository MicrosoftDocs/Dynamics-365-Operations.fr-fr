---
title: Planification pour couverture de site, entrepôt non obligatoire
description: Cet article décrit comment un article disposant de la dimension du site comme couverture est planifié.
author: t-benebo
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EcoResStorageDimensionGroup, ReqItemTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: 2474
ms.assetid: 316da918-67ae-43c5-baea-00ae559e29b0
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: benebotg
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 327bb259cc108f1fad068c847441229dcaee7ff1
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8859225"
---
# <a name="master-planning-for-site-coverage-warehouse-not-mandatory"></a>Planification pour couverture de site, entrepôt non obligatoire

[!include [banner](../includes/banner.md)]

Cet article décrit comment un article disposant de la dimension du site comme couverture est planifié.

Ce scénario de planification implique les conditions suivantes :

-   La dimension de site est définie sur obligatoire et doit être entrée dans la transaction de demande.
-   La dimension d’entrepôt n’est pas obligatoire. L’entrepôt peut être connu mais n’est pas utilisé dans le calcul de planification.
-   La dimension de site est définie pour la planification de la couverture.
-   La dimension d’entrepôt n’est pas définie pour la planification de la couverture. Par conséquent, l’offre et la demande sont agrégées par site (et d’autres dimensions planifiées, éventuellement).

Le graphique suivant illustre l’exécution du calcul de planification. Les paramètres indiqués dans le graphique, et leurs emplacements, sont les suivants :
-   La couverture d’article est définie pour l’article. Cliquez sur **Gestion des informations sur les produits &gt; Produits &gt; Produits lancés**. Sélectionnez l’article, puis cliquez sur **Plan &gt; Couverture de l’article**.
-   Des relations de rechargement sont définies pour l’entrepôt. Cliquez sur **Gestion des stocks &gt; Paramétrage &gt; Décomposition du stock &gt; Entrepôts**. Dans l’onglet **Planification**, voir le groupe de champs **Entrepôt principal**.
-   Par défaut, le type de commande est défini sur Production, Commande fournisseur ou Kanban. Cliquez sur **Gestion des informations sur les produits &gt; Produits &gt; Produits lancés**. Sélectionnez l’article, puis cliquez sur **Plan &gt; Paramètres de commande par défaut**. Dans l’écran **Paramètres de commande par défaut**, consultez le champ **Type de commande par défaut**.

![Demande pour l’entrepôt de couverture du site non obligatoire.](./media/multisitedemandexplosionscenarioforsitecoveragewarehousenotmandatory.jpg)



## <a name="additional-resources"></a>Ressources supplémentaires

[Vue d’ensemble de planification générale et fonctionnalité multisite](master-plan-multisite-functionality.md)

[Planification de couverture de site et d’entrepôt, entrepôt obligatoire](master-plan-site-coverage-warehouse-mandatory.md)

[Planification pour couverture de site, entrepôt obligatoire](master-plan-site-warehouse-coverage-warehouse-not-mandatory.md)

[Planification pour couverture de site, entrepôt non obligatoire](master-plan-site-warehouse-coverage-warehouse-mandatory.md)

[Déterminer la version de nomenclature](master-plan-bom-version-determined.md)





[!INCLUDE[footer-include](../../includes/footer-banner.md)]