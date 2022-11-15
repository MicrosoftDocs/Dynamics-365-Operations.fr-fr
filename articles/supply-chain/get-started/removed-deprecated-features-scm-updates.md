---
title: Fonctions supprimées ou déconseillées dans Dynamics 365 Supply Chain Management
description: Cet article décrit les fonctions qui ont été supprimées, ou qu’il est prévu de supprimer de Dynamics 365 Supply Chain Management.
author: kamaybac
ms.date: 06/29/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2020-03-03
ms.dyn365.ops.version: Platform update 33
ms.openlocfilehash: 722b34e89a54715db39259549c11a78d69d2b4d3
ms.sourcegitcommit: 491ab9ae2b6ed991b4eb0317e396fef542d3a21b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/03/2022
ms.locfileid: "9739868"
---
# <a name="removed-or-deprecated-features-in-dynamics-365-supply-chain-management"></a>Fonctions supprimées ou déconseillées dans Dynamics 365 Supply Chain Management

[!include [banner](../includes/banner.md)]

Cet article sera mise à jour à mesure que de nouvelles fonctionnalités supprimées ou obsolètes sont documentées pour Dynamics 365 Supply Chain Management.

- Une fonction *supprimée* n’est plus disponible dans le produit.
- Une fonction *déconseillée* n’est pas en développement actif et peut être supprimée dans une prochaine mise à jour.

Cette liste est conçue pour vous aider à prendre en compte ces suppressions et abandons pour votre propre planification.

> [!NOTE]
> Des informations détaillées sur les objets dans les applications de finances et d’opérations peuvent être consultés dans les [États de référence technique](/dynamics/s-e/). Vous pouvez comparer les différentes versions de ces états pour en savoir plus sur les objets qui ont été modifiés ou supprimés de chaque version des applications de finances et d’opérations.

## <a name="features-removed-or-deprecated-in-the-supply-chain-management-10029-release"></a>Fonctions supprimées ou obsolètes dans Supply Chain Management version 10.0.29

### <a name="stock-transfer-orders-that-have-tax-on-the-transfer-price"></a>Ordres de transfert des stocks avec taxe sur le prix de transfert

| &nbsp;  | &nbsp;  |
|---|---|
| **Motif de l’abandon/de la suppression** | La fonctionnalité [Ordres de transfert de stock qui ont une taxe sur le prix de transfert](../../finance/localizations/apac-ind-gst-stock-transfer-transactions.md) est remplacée par la fonctionnalité [Ordres de transfert de stock pour l'Inde](../../finance/localizations/apac-ind-stock-transfer.md). |
| **Remplacé par une autre fonctionnalité ?**   | Oui, la fonctionnalité [Ordres de transfert de stock qui ont une taxe sur le prix de transfert](../../finance/localizations/apac-ind-gst-stock-transfer-transactions.md) est remplacée par la fonctionnalité [Ordres de transfert de stock pour l'Inde](../../finance/localizations/apac-ind-stock-transfer.md). |
| **Zones de produit affectées** | Supply Chain Management - inventaire |
| **Option de déploiement** | Cloud et sur site |
| **Status** | <p>Être obsolète. La fonctionnalité *Ordres de transfert de stock qui ont une taxe sur le prix de transfert* ne recevra pas de support avec les correctifs de bogues et les correctifs de sécurité.</p><p>Après avril 2023, les clients seront invités à utiliser la fonctionnalité améliorée, *Ordres de transfert de stock pour l'Inde*, par défaut. Après octobre 2023, la fonctionnalité *Ordres de transfert de stock qui ont une taxe sur le prix de transfert* ne sera plus disponible, et les clients seront invités à passer à la fonctionnalité améliorée *Ordres de transfert de stock pour l'Inde*.</p><p>Pour plus d'informations, voir [Ordres de transfert de stock pour l'Inde](../../finance/localizations/apac-ind-stock-transfer.md).</p> |

## <a name="features-removed-or-deprecated-in-the-supply-chain-management-10019-release"></a>Fonctions supprimées ou obsolètes dans Supply Chain Management version 10.0.19

### <a name="job-card-device"></a>Périphérique pour le bon de travail

| &nbsp;  | &nbsp;  |
|---|---|
| **Motif de l’abandon/de la suppression** | Le [périphérique de bon de travail](../production-control/config-job-card-device.md) est remplacé par la nouvelle [interface d’exécution de l’atelier de production](../production-control/production-floor-execution-configure.md). |
| **Remplacé par une autre fonctionnalité ?**   | Oui, le [périphérique de bon de travail](../production-control/config-job-card-device.md) va être remplacé par la nouvelle [interface d’exécution de l’atelier de production](../production-control/production-floor-execution-configure.md). |
| **Zones de produit affectées** | Supply Chain Management - contrôle de la production |
| **Option de déploiement** | Cloud et sur site |
| **État** | Obsolète. Le périphérique du bon de travail bénéficiera d’un support avec correctifs de sécurité et de bogues, mais les améliorations de fonctionnalités ne seront plus fournies. Après avril 2022, le périphérique du bon de travail ne sera plus prise en charge et les clients seront invités à passer à la nouvelle interface d’exécution de l’atelier de production. |

## <a name="features-removed-or-deprecated-in-the-supply-chain-management-10018-release"></a>Fonctions supprimées ou obsolètes dans Supply Chain Management version 10.0.18

### <a name="supply-chain-management--warehousing-the-warehouse-app"></a><a name="wma"></a>Supply Chain Management – Entrepôts (application des entrepôts)

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Motif de l’abandon/de la suppression** | À compter d’avril 2021, *Supply Chain Management – Warehousing* (l’application d’entrepôt) est obsolète et ne sera plus prise en charge après avril 2022. Elle est maintenant remplacée par l’*Application mobile Gestion des entrepôts*, qui a été publiée avec la version 10.0.17 de Supply Chain Management. La nouvelle application est un remplacement complet, mais elle utilise la même infrastructure sous-jacente, ce qui facilite la migration. Si nécessaire, les deux applications peuvent être utilisées côte à côte pour aider les utilisateurs à s’adapter à mesure qu’ils apprennent à utiliser la nouvelle application.<br><br>Pour plus d’informations sur la nouvelle application mobile Gestion des entrepôts, voir [Application mobile Gestion des entrepôts](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-supply-chain-management/warehouse-management-mobile-application) et [Installer et connecter l’application mobile Gestion des entrepôts](../warehousing/install-configure-warehouse-management-app.md). |
| **Remplacé par une autre fonctionnalité ?**   | Oui, remplacé par la nouvelle application mobile Gestion des entrepôts. |
| **Zones de produit affectées**         | Supply Chain Management - application d’entrepôt |
| **Option de déploiement**              | Cloud et sur site |
| **État**                         | Obsolète. L’application d’entrepôt bénéficiera d’un support avec correctifs de sécurité et de bogues, mais les améliorations de fonctionnalités ne seront plus fournies. Après avril 2022, l’ancienne application d’entrepôt ne sera plus prise en charge et les clients seront invités à passer à la nouvelle application mobile Gestion des entrepôts. L’ancienne application d’entrepôt sera ensuite supprimée du Microsoft Store et du Google Play Store.  |

## <a name="features-removed-or-deprecated-in-the-supply-chain-management-10015-release"></a>Fonctions supprimées ou obsolètes dans Supply Chain Management version 10.0.15

### <a name="internet-explorer-11-support-for-dynamics-365-is-deprecated"></a>La prise en charge d’Internet Explorer 11 pour Dynamics 365 est obsolète

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Motif de l’abandon/de la suppression** | Depuis décembre 2020, la prise en charge de tous les produits Dynamics 365 dans Microsoft Internet Explorer 11 est obsolète et Internet Explorer 11 ne sera plus pris en charge après août 2021.<br><br>Cela aura un impact sur les clients qui utilisent des produits Dynamics 365 conçus pour être utilisés via une interface Internet Explorer 11. Après août 2021, Internet Explorer 11 ne sera pas pris en charge pour ces produits Dynamics 365. |
| **Remplacé par une autre fonctionnalité ?**   | Nous recommandons aux clients de passer à Microsoft Edge.|
| **Zones de produit affectées**         | Tous les produits Dynamics 365 |
| **Option de déploiement**              | Tous|
| **État**                         | Obsolète. Internet Explorer 11 ne sera plus pris en charge après août 2021.|

### <a name="use-of-built-in-supply-chain-management-master-planning-engine-for-manufacturing-scenarios"></a>Utilisation du moteur de planification Supply Chain Management intégré à des fins de fabrication

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Motif de l’abandon/de la suppression** | Pour améliorer les performances et minimiser la charge de la base de données SQL lors des exécutions de planification, le moteur de planification de Supply Chain Management intégré est remplacé par l’Optimisation de la planification. Optimisation de la planification permet des cycles de planification rapides qui peuvent être effectués même pendant les heures de bureau. Cela permet aux planificateurs de réagir immédiatement aux changements de la demande ou des paramètres de planification. |
| **Remplacé par une autre fonctionnalité ?**   | Oui, Optimisation de la planification remplacera le moteur de planification de Supply Chain Management existant. |
| **Zones de produit affectées**         | Supply Chain Management - Planification |
| **Option de déploiement**              | Cloud uniquement. Notez que Optimisation n’est pas pris en charge avec les déploiements locaux. |
| **État**                         | Obsolète. À partir du 1er avril 2022, les scénarios de fabrication ne seront plus pris en charge avec le moteur de planification Supply Chain Management intégré. À partir de cette date, Microsoft arrêtera tout développement actif sur les scénarios de fabrication pour le moteur de planification intégré, ne publiera aucune nouvelle fonctionnalité et ne publiera que des correctifs de bogues critiques. Après cette date, toutes les entreprises nécessitant une prise en charge des scénarios de fabrication doivent utiliser l’optimisation de la planification pour leurs calculs de planification générale. L’optimisation de la planification devrait prendre pleinement en charge les scénarios de fabrication d’ici octobre 2022. Pour plus d’informations, consultez [Présentation de la planification générale déprécié](../master-planning/deprecated-master-planning-overview.md).<br><br>Les entreprises avec des déploiements locaux de Supply Chain Management peuvent continuer à utiliser le moteur de planification intégré pour les scénarios de fabrication après avril 2022. Cependant, aucune amélioration supplémentaire des fonctionnalités ne sera fournie. |

## <a name="features-removed-or-deprecated-in-the-supply-chain-management-10011-release"></a>Fonctions supprimées ou obsolètes dans Supply Chain Management version 10.0.11

### <a name="use-of-built-in-supply-chain-management-master-planning-engine-for-distribution-scenarios"></a>Utilisation du moteur de planification Supply Chain Management intégré à des fins de distribution

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Motif de l’abandon/de la suppression** | Pour améliorer les performances et minimiser la charge de la base de données SQL lors des exécutions de planification, le moteur de planification de Supply Chain Management intégré est remplacé par l’Optimisation de la planification. Optimisation de la planification permet des cycles de planification rapides qui peuvent être effectués même pendant les heures de bureau. Cela permet aux planificateurs de réagir immédiatement aux changements de la demande ou des paramètres de planification. |
| **Remplacé par une autre fonctionnalité ?**   | Oui, Optimisation de la planification remplacera le moteur de planification de Supply Chain Management existant. |
| **Zones de produit affectées**         | Supply Chain Management - Planification |
| **Option de déploiement**              | Cloud uniquement. Notez que Optimisation n’est pas pris en charge avec les déploiements locaux. |
| **État**                         | Obsolète. À partir du 1er avril 2021, les scénarios de distribution ne seront plus pris en charge avec le moteur de planification Dynamics 365 Supply Chain Management intégré. Pour les scénarios de distribution, les clients doivent utiliser Optimisation de la planification pour les calculs de planification. Pour plus d’informations, consultez [Présentation de la planification générale déprécié](../master-planning/deprecated-master-planning-overview.md). Les clients avec des déploiements locaux de Dynamics 365 Supply Chain Management peuvent continuer à utiliser le moteur de planification de Supply Chain Management pour les scénarios de distribution après avril 2021. Cependant, aucune amélioration supplémentaire des fonctionnalités ne sera fournie. |

## <a name="previous-announcements-about-removed-or-deprecated-features"></a>Annonces précédentes sur les fonctions supprimées ou obsolètes

Pour en savoir plus sur les fonctionnalités supprimées ou obsolètes dans les versions précédentes, consultez [Fonctionnalités supprimées ou obsolètes dans les versions précédentes](../../fin-ops-core/dev-itpro/migration-upgrade/deprecated-features.md).


[!INCLUDE[footer-include](../../includes/footer-banner.md)]

