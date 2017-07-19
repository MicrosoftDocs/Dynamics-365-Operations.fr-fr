---
title: Ordonnancement
description: Cette rubrique fournit des informations sur l'ordonnancement. Vous pouvez utiliser l'ordonnancement pour fournir une estimation globale du processus de production dans le temps.
author: YuyuScheller
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: ProdSchedule
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 198073
ms.assetid: 12c28b11-80aa-4668-b15b-724cb24890bd
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2016-02-28T00:00:00.000Z
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: eb9a9aa3fa0d1928101204e7c902a6777bbbef5b
ms.contentlocale: fr-fr
ms.lasthandoff: 05/25/2017

---

# <a name="operations-scheduling"></a>Ordonnancement

[!include[banner](../includes/banner.md)]


Cette rubrique fournit des informations sur l'ordonnancement. Vous pouvez utiliser l'ordonnancement pour fournir une estimation globale du processus de production dans le temps.

Vous pouvez planifier la production au niveau des opérations et des tâches. Contrairement à la planification de tâche, la planification d'opérations n'éclate pas les opérations de la gamme de production en tâches. Si vous souhaitez inclure davantage de détails dans la planification, tels que des informations sur la capacité actuelle, vous pouvez exécuter la planification des tâches après avoir exécuté l'ordonnancement. Vous pouvez également exécuter uniquement une planification de tâches. La planification des tâches concerne généralement la planification de tâches individuelles dans l'atelier et se déroule normalement immédiatement ou à court terme.

## <a name="components-of-operations-scheduling"></a>Composants de l'ordonnancement
Les principaux composants de l'ordonnancement sont la direction de planification, la capacité des ressources et l'optimisation des matières. L'ordonnancement permet d'atteindre les objectifs suivants :

-   Contrôler la méthode de planification en effectuant une planification en avant ou en arrière à partir d'une date donnée.
-   Optimiser l'utilisation des ressources en planifiant des productions en fonction de la capacité des ressources. Cette approche permet également d'identifier à quel moment utiliser d'autres ressources.
-   Optimiser l'utilisation des matières en planifiant des productions en fonction de la disponibilité des matières requises.
-   Planifier et synchroniser les productions de référence. Les dates des productions de référence sont ajustées lorsque la planification des ordres de fabrication est modifiée.

Vous devez estimer le coût d'un ordre de fabrication avant d'exécuter l'ordonnancement. Si vous n'avez pas exécuté d'estimation, elle sera exécutée automatiquement avant le début du processus d'ordonnancement. L'ordonnancement spécifie les informations suivantes :

-   Produit dont la production est planifiée
-   Configuration du produit
-   Quantités impliquées dans la production
-   Dates de début et de fin de la production
-   Réservations de capacité pour les ressources qui exercent les activités de production

Le temps de réglage et le temps d'exécution sont définis pour les opérations de la production. Après avoir exécuté l'ordonnancement, le statut de l'ordre de fabrication est **Prévu** et toutes les opérations sont planifiées dans l'ordre spécifié par la gamme de production. Toutefois, seule la durée de l'opération est prise en considération. Les heures de début et de fin ne sont pas planifiées.

## <a name="scheduling-direction-and-date"></a>Direction et date de planification
La direction de planification est un aspect fondamental du processus de planification. La production peut être planifiée en avant ou en arrière à partir d'une date quelconque, en fonction des besoins de planification et d'échéance.

-   **En avant à partir de la date de planification** – Vous pouvez planifier de démarrer la production le plus tôt possible. Celle-ci peut être démarrée aujourd'hui, demain ou à une date ultérieure quelconque. La production est planifiée en avant dans les délais, c'est-à-dire à la date de fin la plus proche possible.
-   **En arrière à partir de la date de planification** – Vous pouvez planifier de démarrer la production le plus tard possible. La planification en arrière est basée sur la date à laquelle la production doit être terminée. La planification effectue un décompte en arrière à partir de cette date vers la date la plus tardive à laquelle la production peut commencer en vue de respecter le délai prévu.

## <a name="resource-scheduling"></a>Planification de ressource
Lorsque vous exécutez un ordonnancement, chaque opération de la gamme de production est planifiée pour la ressource spécifiée pour l'opération. En outre, la durée de chaque opération est spécifiée sur la gamme de production. Si un groupe de ressources est spécifié pour une opération, la planification réserve la capacité sur le groupe. Toutefois, à la différence de la planification des tâches, l'ordonnancement ne sélectionne pas les ressources spécifiques dans le groupe. Si vous travaillez avec une capacité finie, la planification dépend de la disponibilité des ressources requises pour effectuer la production. L'ordonnancement suit l'ordre des opérations spécifié dans la gamme de production. La planification réserve la capacité des groupes de ressources en fonction des durées d'opération définies pour la gamme de production. La somme de la capacité disponible dans les ressources impliquées détermine la capacité du groupe de ressources. Les réservations de capacité existantes pour les ressources sont considérées comme capacité non disponible. Si la capacité disponible est insuffisante pour la production, les ordres de fabrication peuvent être retardés ou arrêtés. Vous pouvez également spécifier le rendement que vous prévoyez des ressources impliquées dans la production. Vous spécifiez le rendement en pourcentage de la ressource. Le pourcentage de rendement règle le débit de la ressource. Cet ajustement affecte le temps réservé pour la ressource. Le délai des opérations qui utilisent la ressource est également ajusté en conséquence.

## <a name="operations-scheduling-and-master-planning"></a>Ordonnancement et calcul PDP/MRP
L'ordonnancement détermine également la planification, qui établit les calculs des besoins en matières. L'ordonnancement prend en compte les informations suivantes :

-   **Productions retardées** – Produits planifiés, lancés ou démarrés
-   **Disponibilité des matières** – Stock, sous-productions et fournisseurs
-   **Disponibilité de la capacité** – Ressources requises pour la production

## <a name="cancellations"></a>Annulations
Lorsque vous exécutez l'ordonnancement, vous pouvez annuler certaines parties de l'acheminement. Cela inclut le temps d'attente, le temps de réglage, le temps d'exécution, la période de chevauchement et les heures de transport.

## <a name="finite-materials"></a>Matières limitées
Si vous utilisez des matières limitées, la planification dépend également de la disponibilité des matières requises pour la production. Si les composants disponibles ne sont pas suffisants pour la production, la production peut être retardée. Vous pouvez baser la planification sur l'utilisation des matières en spécifiant les matières qui doivent être disponibles pour la production. Lorsque vous optimisez la capacité de la ressource et la disponibilité des matières, la production est calculée selon ces restrictions. Un ordre de fabrication ne peut pas être planifié tant que la capacité et les matières ne sont pas disponibles simultanément et dans les quantités requises.

<a name="see-also"></a>Voir également :
--------

[Options d'ordonnancement](operation-scheduling-options.md)




