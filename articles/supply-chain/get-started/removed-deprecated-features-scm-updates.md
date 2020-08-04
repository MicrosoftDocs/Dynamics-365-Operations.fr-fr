---
title: Fonctions supprimées ou obsolètes dans Dynamics 365 Supply Chain Management
description: Cette rubrique décrit les fonctions qui ont été supprimées, ou qu'il est prévu de supprimer de Dynamics 365 Supply Chain Management.
author: kamaybac
manager: tfehr
ms.date: 04/30/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2020-03-03
ms.dyn365.ops.version: Platform update 33
ms.openlocfilehash: 07f37488747766dcca96884e204339b425bbd201
ms.sourcegitcommit: f64fce03ec52f844b05a9e8cac286cb201385002
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/16/2020
ms.locfileid: "3597114"
---
# <a name="removed-or-deprecated-features-in-dynamics-365-supply-chain-management"></a>Fonctions supprimées ou obsolètes dans Dynamics 365 Supply Chain Management

[!include [banner](../includes/banner.md)]

Cette rubrique sera mise à jour à mesure que de nouvelles fonctionnalités supprimées ou obsolètes sont documentées pour Dynamics 365 Supply Chain Management.

- Une fonction *supprimée* n'est plus disponible dans le produit.
- Une fonction *déconseillée* n'est pas en développement actif et peut être supprimée dans une prochaine mise à jour.

Cette liste est conçue pour vous aider à prendre en compte ces suppressions et abandons pour votre propre planification.

> [!NOTE]
> Des informations détaillées sur les objets dans les applications Finance and Operations sont disponibles dans les [États de référence technique](https://mbs.microsoft.com/customersource/northamerica/AX/downloads/reports/axtechrefrep). Vous pouvez comparer les différentes versions de ces états pour en savoir plus sur les objets qui ont été modifiés ou supprimés dans chaque version des applications Finance and Operations.

## <a name="features-removed-or-deprecated-in-the-supply-chain-management-10011-release"></a>Fonctions supprimées ou obsolètes dans Supply Chain Management version 10.0.11

### <a name="use-of-built-in-supply-chain-management-master-planning-engine-for-distribution-scenarios"></a>Utilisation du moteur de planification Supply Chain Management intégré à des fins de distribution

|   |  |
|------------|--------------------|
| **Motif de l'abandon/de la suppression** | Pour améliorer les performances et minimiser la charge de la base de données SQL lors des exécutions de planification, le moteur de planification de Supply Chain Management intégré est remplacé par l'Optimisation de la planification. Optimisation de la planification permet des cycles de planification rapides qui peuvent être effectués même pendant les heures de bureau. Cela permet aux planificateurs de réagir immédiatement aux changements de la demande ou des paramètres de planification. |
| **Remplacé par une autre fonctionnalité ?**   | Oui, Optimisation de la planification remplacera le moteur de planification de Supply Chain Management existant. |
| **Zones de produit affectées**         | Supply Chain Management - Planification |
| **Option de déploiement**              | Cloud uniquement. Notez que Optimisation n'est pas pris en charge avec les déploiements locaux. |
| **État**                         | Obsolète. En avril 2021, les scénarios de distribution ne seront plus pris en charge avec le moteur de planification Dynamics 365 Supply Chain Management intégré. Pour les scénarios de distribution, les clients doivent utiliser Optimisation de la planification pour les calculs de planification. Pour plus d'informations, voir [Documentation relative à Optimisation de la planification](https://go.microsoft.com/fwlink/?linkid=2105830). Les clients avec des déploiements locaux de Dynamics 365 Supply Chain Management peuvent continuer à utiliser le moteur de planification de Supply Chain Management pour les scénarios de distribution après avril 2021. Cependant, aucune amélioration supplémentaire des fonctionnalités ne sera fournie. |

## <a name="previous-announcements-about-removed-or-deprecated-features"></a>Annonces précédentes sur les fonctions supprimées ou obsolètes

Pour en savoir plus sur les fonctionnalités supprimées ou obsolètes dans les versions précédentes, consultez [Fonctionnalités supprimées ou obsolètes dans les versions précédentes](../../fin-ops-core/dev-itpro/migration-upgrade/deprecated-features.md).
