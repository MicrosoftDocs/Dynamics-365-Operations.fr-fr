---
title: Lancement des ordres de fabrication
description: "Un ordre de fabrication lancé est une commande qui a été autorisée pour la production. Le terme Lancé permet de décrire un état du cycle de vie de l&quot;ordre de fabrication où l&quot;ordre de fabrication est disponible pour l&quot;exécution dans l&quot;atelier de production et pour les processus d&quot;entrepôt."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: ProdParmRelease
audience: Application User
ms.reviewer: annbe
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 2414
ms.assetid: 50c2257b-2924-44f5-b7c1-11f498092053
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: 1b033e4bf6705b3c9a33f2184666158049909a80
ms.contentlocale: fr-fr
ms.lasthandoff: 05/25/2017


---

# <a name="release-production-orders"></a>Lancement des ordres de fabrication

[!include[banner](../includes/banner.md)]


Un ordre de fabrication lancé est une commande qui a été autorisée pour la production. Le terme Lancé permet de décrire un état du cycle de vie de l'ordre de fabrication où l'ordre de fabrication est disponible pour l'exécution dans l'atelier de production et pour les processus d'entrepôt. 

<a name="characteristics-of-the-released-state"></a>Caractéristiques de l'état Lancé
-------------------------------------

L'état **Lancé** est un état du cycle de vie de l'ordre de fabrication. Les ordres de fabrication dont l'état est **Lancé** sont disponibles pour exécution dans l'atelier de production et pour les processus de l'entrepôt. L'état **Lancé** a les caractéristiques suivantes :

-   Un ordre de fabrication peut passer à l'état **Lancé** à partir de l'ordre de fabrication ou à l'aide d'un processus de traitement par lots. L'ordre de fabrication peut être également mis à jour automatiquement à partir des ordres de fabrication prévisionnels qui sont confirmés à l'aide du champ **Plage de gestion de la confirmation** sur la page **Plan général**.
-   L'état **Lancé**est le signal pour les opérateurs de l'atelier (opérateurs) afin de démarrer l'exécution des tâches de production dans l'atelier.
-   Les documents de production tels que les fiches production, les tâches de gamme et les bons de travail offrent les informations relatives aux tâches de production et peuvent être publiés.
-   Pour les matières réservées physiquement, le travail à l'entrepôt est généré pour prélever les matières pour l'ordre de fabrication.

## <a name="releasing-jobs-to-the-shop-floor"></a>Lancement des tâches à l'atelier
Une fois un ordre de fabrication lancé, les tâches de production concernant l'ordre sont visibles et prêts à être enregistrés. Les opérateurs peuvent effectuer des enregistrements des tâches, tels que le début, l'arrêt et l'achèvement, sur la page **Terminal des bons de travail** ou **Périphérique pour le bon de travail**. Le temps et la quantité enregistrés sont automatiquement transférés depuis les pages d'enregistrement vers les journaux de production pour permettre le suivi du temps et de la quantité consommés.

## <a name="route-cards"></a>Fiches productions
Une fiche production offre une vue d'ensemble des informations qui viennent du paramétrage des gammes et des opérations et des méthodes de planification des tâches.

## <a name="route-jobs"></a>Tâches de gamme
Une tâche de gamme répertorie en détails chaque tâche d'une opération, notamment les temps de réglage, de traitement, d'attente et de transport. Par exemple, une opération de peinture peut nécessiter des tâches individuelles comme les temps de paramétrage et d'exécution pour le processus de peinture et le temps d'attente pour le séchage.

## <a name="job-cards"></a>Bons de travail
Un bon de travail répertorie les numéros de travail individuels d'une opération particulière. Une tâche apparaît dans chaque page. Les tâches incluses sur un bon de travail, et leurs temps estimés, viennent des informations de paramétrage de la gamme et de l'opération. Depuis un bon de travail, vous pouvez ouvrir la page **Lignes de journal de production**, **bon de travail**. Les personnes qui exécutent des ressources opérationnelles peuvent donner leur avis sur le processus de production. Il existe des champs dans lesquels vous pouvez entrer des statistiques et des informations de consommation telles que la quantité d'erreurs.

## <a name="warehouse-work-for-raw-material-picking"></a>Travail d'entrepôt pour le prélèvement des matières premières
Le travail pour le prélèvement des matières premières est généré lors du lancement. Le travail est généré uniquement pour la quantité des matières physiquement réservées pour l'ordre de fabrication, avant le lancement de l'ordre. Le paramétrage suivant est nécessaire pour générer le travail d'entrepôt pour le prélèvement des matières premières :

-   Une directive d'emplacement pour le prélèvement des matières premières qui détermine où prélever les matériaux dans l'entrepôt
-   Un modèle de vague pour les matières premières, où sont configurées les stratégies d'exécution du travail d'entrepôt
-   Un emplacement d'entrée en production qui détermine où sont déposées les matières





