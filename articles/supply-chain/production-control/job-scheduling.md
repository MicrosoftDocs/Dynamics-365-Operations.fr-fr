---
title: Planification de tâche
description: Cet article fournit des informations sur la planification des tâches, qui constitue une forme plus détaillée de planification que la planification d'opérations. La planification des tâches permet de programmer des tâches ou ordres d'atelier, et de contrôler l'environnement de fabrication.
author: ChristianRytt
manager: tfehr
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ProdSchedule
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: 19431
ms.assetid: aef37341-91d8-4263-80eb-35d9584be156
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: bff966a68001d479b8631e13caa18c9ec8d2bf4c
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4428116"
---
# <a name="job-scheduling"></a>Planification de tâche

[!include [banner](../includes/banner.md)]

Cet article fournit des informations sur la planification des tâches, qui constitue une forme plus détaillée de planification que la planification d'opérations. La planification des tâches permet de programmer des tâches ou ordres d'atelier, et de contrôler l'environnement de fabrication.

La planification des tâches permet de programmer des tâches ou ordres d'atelier, et de contrôler l'environnement de fabrication. Elle décompose chaque opération en tâches individuelles. Ces tâches sont ensuite affectées aux ressources opérationnelles qui les effectueront. La planification des tâches vous permet également de synchroniser toutes les tâches qui sont référencées par la tâche sélectionnée. Vous pouvez spécifier des date et heure de début et de fin pour la tâche, puis effectuer la planification. L'heure spécifiée peut être une heure de début ou de fin, en fonction de la direction de planification. Cette fonctionnalité est utile, par exemple, si une tâche ne peut être exécutée que sur une machine à la fois, ou pour optimiser la tâche qui est exécutée pour chaque ressource.

## <a name="tasks-in-the-job-scheduling-process"></a>Tâches du processus de planification des tâches
Le processus de planification des tâches inclut les tâches suivantes :

-   Diviser les opérations en tâches.
-   Programmer les tâches basées sur les dates et heures pour les ressources spécifiées pour l'opération associée.
-   Calculer les heures de début et de fin de chaque tâche. Vous pouvez utiliser une capacité finie pour vous assurer qu'aucune heure ne se chevauche.
-   Déterminer sur quelles ressources du groupe de ressources exécuter la tâche. Cette tâche nécessite qu'un groupe de ressources soit spécifié pour une opération. La planification des tâches sélectionne les ressources ou les groupes de ressources en fonction du délai le plus court et prend en compte les réservations précédentes sur les ressources.
-   Éclater les opérations en tâches lorsque vous exécutez la planification des tâches. Les tâches sont planifiées par date et heure dans l'ordre indiqué par la gamme de production. Le paramétrage de l'opération détermine quelles tâches sont éclatées au cours de la planification. Le groupe de gammes affecté à l'opération contrôle la génération ou non des tâches. Une tâche est générée uniquement si elle a une durée spécifique. Par exemple, une tâche de temps de transport est générée si un temps de transport est indiqué pour l'opération sélectionnée.

## <a name="scheduling-direction"></a>Direction de la planification
Vous pouvez programmer en avant ou en arrière.

-   **En avant** - Utilisez le mode de planification « en avant » afin de commencer la production le plus tôt possible. Ce mode est également appelé méthode « Push » car la production est « poussée en avant » tout au long du processus de production. La production est planifiée de manière à démarrer et se terminer le plus tôt possible.
-   **En arrière** - Utilisez le mode de planification « en arrière » afin de commencer la production le plus tard possible. Ce mode est également appelée méthode en continu, car elle dépend de la date de fin de la production. La planification en arrière effectue un décompte en arrière vers la date la plus tardive à laquelle la production peut commencer en vue de respecter le délai prévu.

## <a name="finite-capacity"></a>Capacité finie
Vous pouvez programmer des tâches avec une capacité finie. Lorsque vous utilisez une capacité finie, la capacité prévue ne peut pas être supérieure à la capacité disponible pour la ressource. Le temps disponible correspond à l'intervalle de temps pendant lequel la ressource est disponible et aucune autre réservation de capacité n'existe. La planification basée sur la capacité limitée garantit que les heures de début et de fin d'une opération ne se chevauchent pas à une date particulière. La capacité de la ressource déjà réservée est prise en compte, ainsi que les chevauchements entre ces heures de début et de fin. La capacité finie détermine le montant de capacité devant être disponible pour la ressource afin de garantir une utilisation optimale de cette ressource. Cette détermination est équilibrée avec un calcul du délai le plus court possible entre des opérations.

## <a name="finite-materials"></a>Matières limitées
La planification des tâches basée sur des matières limitées garantit la disponibilité des matières requises au début de l'opération. Les règles de couverture des articles définissent ces limites. La planification utilise un éclatement des besoins pour déterminer si les composants sont disponibles. Si vous planifiez des tâches sans définir de matières limitées, le système part du principe que tous les articles sont disponibles lorsqu'ils sont requis.

## <a name="finite-properties"></a>Propriétés limitées
La planification basée sur des propriétés spéciales implique de spécifier des propriétés pour les opérations de la gamme de production. Vous devez définir ces propriétés afin de pouvoir réserver de la capacité.

## <a name="references"></a>Références
La planification des tâches planifie toutes les productions référencées par la production actuelle. Si une production est composée d'une ou de plusieurs sous-productions, celles-ci doivent être planifiées en même temps que la production principale, car il est impossible de lancer la production principale tant que les sous-productions afférentes ne sont pas terminées.

## <a name="schedule-resources"></a>Programmer les ressources
Le moteur de planification examine les combinaisons de ressources pour identifier celles qui sont conformes aux demandes. Vous pouvez spécifier des critères de sélection en sélectionnant l'une des valeurs suivantes dans le champ **Sélection de ressource primaire** sur la page **Paramètres de planification** :

-   **Durée** - Le moteur de planification sélectionne la ressource avec le délai le plus court. **Remarque :** La planification par durée peut réduire les performances lorsque le même groupe de ressources contient de nombreuses ressources et que des opérations secondaires sont utilisées. Vous pouvez planifier un nombre maximal de 32 ressources par opération. Si vous dépassez cette quantité, un message Infos s'affiche et le système de planification des tâches ne trouve pas la meilleure ressource de remplacement.
-   **Priorité** -  Le moteur de planification sélectionne la ressource dotée de la priorité la plus élevée lorsqu'au moins deux ressources ont des capacités et des niveaux identiques. La ressource dont la valeur numérique est la plus basse dans ce champ a la priorité la plus élevée.

Lors de l'exécution de la planification des tâches, le système planifie les ressources sur la base des limites définies dans les paramètres de ressource. Vous pouvez contrôler la capacité des ressources à l'aide des paramètres de calendrier. Le système calcule les charges relatives aux ressources lors du processus de planification. **Remarque :** Pour les productions utilisant la fonction d'ordonnancement, vous pouvez exécuter la planification des tâches après l'ordonnancement. Si vous n'utilisez pas l'ordonnancement, vous pouvez exécuter la planification des tâches seule.

## <a name="maximum-capacities-for-resources-per-job-order"></a>Capacités maximales des ressources par ordre de travail
Des ressources sont affectées aux tâches lors de la planification des tâches. Vous pouvez établir des capacités maximales des ressources par ordre de travail. Par exemple, vous pouvez paramétrer le système pour restreindre à 50 pour cent au plus la capacité totale d'un ordre de fabrication. Vous gagnez ainsi un meilleur contrôle de la planification des ressources au niveau de la planification des tâches. Par conséquent, vous évitez des problèmes en cas de capacité insuffisante pour exécuter plusieurs productions simultanément.

## <a name="resource-efficiency"></a>Rendement des ressources
La planification des tâches prend en compte les pourcentages de rendement spécifiés pour les ressources. Les pourcentages de rendement augmentent ou diminuent le temps réservé pour la ressource. Ainsi, le délai est également augmenté ou réduit. La formule suivante est utilisée pour le calcul : Planification du temps = Temps × 100 ÷ Pourcentage de rendement où le *Temps* inclut le temps d'exécution et le temps de réglage.



