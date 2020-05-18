---
title: Vue d'ensemble d'Optimisation de la planification
description: Cette rubrique fournit une vue d'ensemble de la fonctionnalité Optimisation de la planification.
author: ChristianRytt
manager: tfehr
ms.date: 10/31/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ReqCreatePlanWorkspace
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: AX 10.0.5
ms.openlocfilehash: 110045d4c7e4f32c29b73096dd4df3a09b5434ac
ms.sourcegitcommit: 68092ed283bfbb7b6f611cce1b62c791f9b6a208
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/30/2020
ms.locfileid: "3323391"
---
# <a name="planning-optimization-overview"></a>Vue d'ensemble d'Optimisation de la planification

[!include [banner](../../includes/banner.md)]

Le complément d'Optimisation de la planification pour Microsoft Dynamics 365 Supply Chain Management permet le calcul de planification en dehors de Dynamics 365 Supply Chain Management et de la base de données SQL associée. Les avantages associés à la fonctionnalité Optimisation de la planification incluent des performances améliorées et un impact minimum sur la base de données SQL pendant l'exécution de la planification. De rapides exécutions de la planification peuvent être effectuées même pendant les heures de bureau, afin que les planificateurs puissent réagir immédiatement aux modifications de la demande ou des paramètres.

Pour utiliser Optimisation de a planification, vous devez installer le complément d'Optimisation de la planification depuis votre projet dans Microsoft Dynamics Lifecycle Services (LCS) et activer la fonctionnalité Optimisation de la planification dans Supply Chain Management. Pour plus d'informations, voir [Prise en main d'Optimisation de la planification](get-started.md).

L'illustration suivante présente l'avantage d'exécuter Optimisation de la planification pendant les heures de bureau.

![Avantage d'exécuter Optimisation de la planification pendant les heures de bureau](media/PlanningOptimization1.png)

## <a name="improved-performance"></a>Performances améliorées

Optimisation de la planification peut être utilisée dans des scénarios impliquant des plans généraux à long terme. Elle est spécialement conçue pour les calculs très rapides impliquant des volumes de données très importants. Puisqu'elle est intégrée comme service à plusieurs locataires ultra-évolutif, plusieurs instances peuvent travailler ensemble en simultané pour calculer le plan. En outre, le service de planification supprime la charge de la planification de votre système et fonctionne avec un flux de données qui réduit la charge du serveur.

Optimisation de la planification peut vous aider à atteindre les objectifs suivants :

- Améliorer les performances de planification via une exécution à plus court terme.
- Réduire l'impact sur d'autres processus pendant l'exécution de la planification.
- Effectuer des exécutions de planification plus fréquentes. (Vous n'êtes pas limité aux exécutions quotidiennes.)
- S'assurer que la future croissance de l'entreprise ne surcharge pas le système de planification.

## <a name="architecture-and-data-flow"></a>Architecture et flux de données

Lorsque le complément de l'optimisation de la planification est installé depuis LCS, une connexion sûre au service Optimisation de la planification est établie. Le service se situe dans le même pays ou la même région du centre de données que l'instance Supply Chain Management associée. Une fois l'optimisation de la planification configurée, lorsque la planification est exécutée, les données principales et de transaction sont envoyées de Supply Chain Management vers le service Optimisation de la planification.

Si le complément d'Optimisation de la planification est désinstallé, toutes les données associées au service d'Optimisation de la planification sont supprimées.

### <a name="high-level-data-flow-for-regeneration-runs"></a>Flux de données de haut niveau pour les exécutions de régénération

1. Le client Supply Chain Management envoie un signal pour demander l'exécution d'une planification depuis l'Optimisation de la planification.
2. L'Optimisation de la planification demande les données nécessaires via le connecteur intégré.
3. La base de données SQL envoie les informations requises concernant les données de configuration, générales et de transaction à l'Optimisation de la planification via le connecteur. Le connecteur traduit les informations entre Supply Chain Management et le service d'Optimisation de la planification.
4. Le service d'Optimisation de la planification mémorise les données relatives à la planification et effectue les calculs requis.
5. Le résultat de la planification est envoyé à la base de données Supply Chain Management via le connecteur. Les résultats incluent des informations telles que les ordres prévisionnels et les informations sur l'origine des besoins. L'Optimisation de la planification envoie un signal à Supply Chain Management pour indiquer que l'exécution de la planification est terminée. Elle envoie également des messages et avertissements appropriés.

L'illustration suivante présente le flux de données.

![Flux de données pour les exécutions de régénération](media/PlanningOptimization2.png)

## <a name="related-resources"></a>Ressources associées

[Prise en main de l'Optimisation de la planification](get-started.md)

[Analyse de concordance d'optimisation de la planification](planning-optimization-fit-analysis.md)

[Afficher l'historique du plan et les journaux de planification](plan-history-logs.md)

[Appliquer les filtres à un plan](plan-filters.md)

[Annuler une tâche de planification](cancel-planning-job.md)
