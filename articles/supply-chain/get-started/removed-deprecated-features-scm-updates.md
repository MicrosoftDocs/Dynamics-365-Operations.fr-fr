---
title: Fonctions supprimées ou obsolètes dans Dynamics 365 Supply Chain Management
description: Cette rubrique décrit les fonctions qui ont été supprimées, ou qu'il est prévu de supprimer de Dynamics 365 Supply Chain Management.
author: kamaybac
manager: tfehr
ms.date: 12/07/2020
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
ms.openlocfilehash: d4d2805e36f132660152370cbeee856862ad6faa
ms.sourcegitcommit: 069ed5789517b550065e5e2317658fec4027359e
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/07/2020
ms.locfileid: "4689522"
---
# <a name="removed-or-deprecated-features-in-dynamics-365-supply-chain-management"></a>Fonctions supprimées ou obsolètes dans Dynamics 365 Supply Chain Management

[!include [banner](../includes/banner.md)]

Cette rubrique sera mise à jour à mesure que de nouvelles fonctionnalités supprimées ou obsolètes sont documentées pour Dynamics 365 Supply Chain Management.

- Une fonction *supprimée* n'est plus disponible dans le produit.
- Une fonction *déconseillée* n'est pas en développement actif et peut être supprimée dans une prochaine mise à jour.

Cette liste est conçue pour vous aider à prendre en compte ces suppressions et abandons pour votre propre planification.

> [!NOTE]
> Des informations détaillées sur les objets dans les applications Finance and Operations sont disponibles dans les [États de référence technique](https://mbs.microsoft.com/customersource/northamerica/AX/downloads/reports/axtechrefrep). Vous pouvez comparer les différentes versions de ces états pour en savoir plus sur les objets qui ont été modifiés ou supprimés dans chaque version des applications Finance and Operations.

## <a name="features-removed-or-deprecated-in-the-supply-chain-management-10015-release"></a>Fonctions supprimées ou obsolètes dans Supply Chain Management version 10.0.15

### <a name="internet-explorer-11-support-for-dynamics-365-is-deprecated"></a>La prise en charge d'Internet Explorer 11 pour Dynamics 365 est obsolète

|   |  |
|------------|--------------------|
| **Motif de l’abandon/de la suppression** | Depuis décembre 2020, la prise en charge de tous les produits Dynamics 365 dans Microsoft Internet Explorer 11 est obsolète et Internet Explorer 11 ne sera plus pris en charge après août 2021.<br><br>Cela aura un impact sur les clients qui utilisent des produits Dynamics 365 conçus pour être utilisés via une interface Internet Explorer 11. Après août 2021, Internet Explorer 11 ne sera pas pris en charge pour ces produits Dynamics 365. |
| **Remplacé par une autre fonctionnalité ?**   | Nous recommandons aux clients de passer à Microsoft Edge.|
| **Zones de produit affectées**         | Tous les produits Dynamics 365 |
| **Option de déploiement**              | Tous|
| **État**                         | Obsolète. Internet Explorer 11 ne sera plus pris en charge après août 2021.|

### <a name="use-of-built-in-supply-chain-management-master-planning-engine-for-manufacturing-scenarios"></a>Utilisation du moteur de planification Supply Chain Management intégré à des fins de fabrication

|   |  |
|------------|--------------------|
| **Motif de l’abandon/de la suppression** | Pour améliorer les performances et minimiser la charge de la base de données SQL lors des exécutions de planification, le moteur de planification de Supply Chain Management intégré est remplacé par l'Optimisation de la planification. Optimisation de la planification permet des cycles de planification rapides qui peuvent être effectués même pendant les heures de bureau. Cela permet aux planificateurs de réagir immédiatement aux changements de la demande ou des paramètres de planification. |
| **Remplacé par une autre fonctionnalité ?**   | Oui, Optimisation de la planification remplacera le moteur de planification de Supply Chain Management existant. |
| **Zones de produit affectées**         | Supply Chain Management - Planification |
| **Option de déploiement**              | Cloud uniquement. Notez que Optimisation n'est pas pris en charge avec les déploiements locaux. |
| **État**                         | Obsolète. À partir du 1er octobre 2021, les scénarios de fabrication ne seront plus pris en charge avec le moteur de planification Dynamics 365 Supply Chain Management intégré. Pour les scénarios de fabrication, les clients doivent utiliser Optimisation de la planification pour les calculs de planification. Pour plus d'informations, voir [Documentation relative à Optimisation de la planification](https://go.microsoft.com/fwlink/?linkid=2105830). Les clients avec des déploiements locaux de Dynamics 365 Supply Chain Management peuvent continuer à utiliser le moteur de planification de Supply Chain Management pour les scénarios de fabrication après octobre 2021. Cependant, aucune amélioration supplémentaire des fonctionnalités ne sera fournie. |

## <a name="features-removed-or-deprecated-in-the-supply-chain-management-10011-release"></a>Fonctions supprimées ou obsolètes dans Supply Chain Management version 10.0.11

### <a name="use-of-built-in-supply-chain-management-master-planning-engine-for-distribution-scenarios"></a>Utilisation du moteur de planification Supply Chain Management intégré à des fins de distribution

|   |  |
|------------|--------------------|
| **Motif de l'abandon/de la suppression** | Pour améliorer les performances et minimiser la charge de la base de données SQL lors des exécutions de planification, le moteur de planification de Supply Chain Management intégré est remplacé par l'Optimisation de la planification. Optimisation de la planification permet des cycles de planification rapides qui peuvent être effectués même pendant les heures de bureau. Cela permet aux planificateurs de réagir immédiatement aux changements de la demande ou des paramètres de planification. |
| **Remplacé par une autre fonctionnalité ?**   | Oui, Optimisation de la planification remplacera le moteur de planification de Supply Chain Management existant. |
| **Zones de produit affectées**         | Supply Chain Management - Planification |
| **Option de déploiement**              | Cloud uniquement. Notez que Optimisation n'est pas pris en charge avec les déploiements locaux. |
| **État**                         | Obsolète. À partir du 1er avril 2021, les scénarios de distribution ne seront plus pris en charge avec le moteur de planification Dynamics 365 Supply Chain Management intégré. Pour les scénarios de distribution, les clients doivent utiliser Optimisation de la planification pour les calculs de planification. Pour plus d'informations, voir [Documentation relative à Optimisation de la planification](https://go.microsoft.com/fwlink/?linkid=2105830). Les clients avec des déploiements locaux de Dynamics 365 Supply Chain Management peuvent continuer à utiliser le moteur de planification de Supply Chain Management pour les scénarios de distribution après avril 2021. Cependant, aucune amélioration supplémentaire des fonctionnalités ne sera fournie. |

## <a name="previous-announcements-about-removed-or-deprecated-features"></a>Annonces précédentes sur les fonctions supprimées ou obsolètes

Pour en savoir plus sur les fonctionnalités supprimées ou obsolètes dans les versions précédentes, consultez [Fonctionnalités supprimées ou obsolètes dans les versions précédentes](../../fin-ops-core/dev-itpro/migration-upgrade/deprecated-features.md).


[!INCLUDE[footer-include](../../includes/footer-banner.md)]