---
title: Nouveautés ou modifications dans Dynamics 365 Supply Chain Management 10.0.24 (février 2022)
description: Cet article décrit les fonctionnalités qui sont nouvelles ou ont été modifiées dans Microsoft Dynamics 365 Supply Chain Management 10.0.24.
author: kamaybac
ms.date: 12/03/2021
ms.topic: article
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2021-12-03
ms.dyn365.ops.version: 10.0.24
ms.openlocfilehash: 94e465616338b0c905ccf6b8244324c18c7a59e8
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8849443"
---
# <a name="whats-new-or-changed-in-dynamics-365-supply-chain-management-10024-february-2022"></a>Nouveautés ou modifications dans Dynamics 365 Supply Chain Management 10.0.24 (février 2022)

[!include [banner](../includes/banner.md)]

Cet article répertorie les fonctionnalités qui sont nouvelles ou ont été modifiées dans Microsoft Dynamics 365 Supply Chain Management, version 10.0.24. Cette version a un numéro de build de 10.0.1084 et est disponible comme suit :

- **Version préliminaire :** décembre 2021
- **Disponibilité générale de la version (auto-mise à jour) :** janvier 2022
- **Disponibilité générale de la version (mise à jour automatique) :** février 2022

## <a name="features-included-in-this-release"></a>Fonctionnalités incluses dans cette version

Le tableau suivant répertorie les fonctionnalités incluses dans cette version. Il se peut que nous mettions à jour de cet article pour inclure des fonctionnalités qui auront été intégrées à la version après la publication initiale de cet article.

| Fonctionnalités | Fonction | Plus d’informations | Activé par |
|---|---|---|---|
| Topologie hybride distribuée | [Charges de travail d’exécution de l’entrepôt améliorées sur les unités d’échelle](/dynamics365-release-plan/2021wave2/finance-operations/dynamics365-supply-chain-management/enhanced-warehouse-execution-workloads-scale-units) | [Charges de gestion d’entrepôt pour les unités d’échelle Cloud et périphérie](../cloud-edge/cloud-edge-workload-warehousing.md) | Activé par défaut. |
| Topologie hybride distribuée | [Démarrer l’ordre de fabrication sur la charge de travail de gestion d’entrepôt pour l’unité d’échelle cloud ou périphérique](/dynamics365-release-plan/2021wave2/finance-operations/dynamics365-supply-chain-management/enhanced-manufacturing-execution-workloads-scale-units) | [Charges de travail de fabrication pour les unités d’échelle Cloud et périphérie](../cloud-edge/cloud-edge-workload-manufacturing.md) | Gestion des fonctionnalités (*Démarrer l’ordre de fabrication sur la charge de travail de gestion d’entrepôt pour l’unité d’échelle cloud ou périphérique*)  |
| Planification | [Prise en charge de l’optimisation de la planification pour la marge de renouvellement et marge de sortie](/dynamics365-release-plan/2021wave2/finance-operations/dynamics365-supply-chain-management/planning-optimization-support-reorder-margin-issue-margin) | [Marges de sécurité](../master-planning/planning-optimization/safety-margins.md) | Activé par défaut. |

## <a name="feature-enhancements-included-in-this-release"></a>Améliorations de fonctionnalités incluses dans cette version

Le tableau suivant répertorie les améliorations de fonctionnalités incluses dans cette version. Chacune d’elles apporte une amélioration incrémentielle à une fonctionnalité existante. Comme il ne s’agit que d’améliorations, elles ne sont pas répertoriées dans le [plan de version](/dynamics365-release-plan/2021wave2/finance-operations/dynamics365-supply-chain-management/planned-features). Cependant, pour s’assurer que ces améliorations n’entrent pas en conflit avec vos personnalisations ou préférences existantes, chacune d’elles est désactivée par défaut (sauf indication contraire).

Si vous souhaitez activer ou désactiver l’une de ces fonctionnalités, vous devez le faire explicitement dans [Gestion des fonctionnalités](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

| Module | Nom de la fonction dans la Gestion des fonctionnalités | Plus d’informations |
|---|---|---|
| Contrôle de la production | Vérification de la disponibilité des matériaux à la demande pour les ordres de fabrication | Cette fonctionnalité accélère l’ouverture de la page **Ordres de fabrication à lancer**, qui est disponible à partir de l’espace de travail **Gestion de l’atelier de production**. Sans cette fonctionnalité, le système vérifie automatiquement si des articles sont disponibles pour tous les ordres de fabrication répertoriés dès que vous ouvrez la page, ce qui peut prendre un temps considérable si vous avez un grand nombre de commandes. Lorsque cette fonctionnalité est activée, le système fournit à la place un bouton de barre d’outils, que vous pouvez utiliser pour lancer la vérification des matériaux uniquement pour les commandes sélectionnées et en cas de besoin. |
| Contrôle de la production | (Version préliminaire) Enregistrer la consommation des matériaux sur l’interface d’exécution de l’atelier de production (autre que WMS) | Cette fonctionnalité permet aux travailleurs d’utiliser l’interface d’exécution de l’atelier de production pour enregistrer la consommation de matériaux, les numéros de lot et les numéros de série. Cette fonctionnalité prend uniquement en charge les articles qui ne sont pas activés pour utiliser les processus d’entrepôt avancés (WMS). La prise en charge des éléments compatibles WMS est prévue pour une prochaine version.<p>Certains fabricants, en particulier ceux des industries de transformation, doivent enregistrer explicitement la quantité de matière consommée pour chaque lot ou ordre de fabrication. Par exemple, les travailleurs peuvent utiliser une balance pour peser la quantité de matière consommée pendant qu’ils travaillent. Pour assurer une traçabilité totale des matériaux, ces organisations doivent également enregistrer les numéros de lots consommés lors de la fabrication de chaque produit. |
| Contrôle de la production | Déclaration de fin sur la charge de travail de gestion d’entrepôt pour l’unité d’échelle cloud ou périphérique | Cette fonctionnalité permet aux travailleurs d’utiliser l’application mobile Warehouse Management pour déclarer une commande de production ou de lot comme terminée lorsque l’application s’exécute sur une charge de travail de gestion d’entrepôt sur une unité d’échelle cloud ou périphérique. Pour plus d’informations, voir [Déclarer comme terminé et rangé sur une unité d’échelle](../cloud-edge/cloud-edge-workload-manufacturing.md#RAF). |
| Gestion des entrepôts | Nouvelles pages de l’atelier de planification des chargements | Active les deux nouvelles pages de l’atelier de planification des chargements : **Atelier de planification des chargements entrants** et **Atelier de planification des chargements sortants**. |

## <a name="new-and-updated-documentation-resources"></a>Ressources de documentation nouvelles et mises à jour

Nous avons récemment ajouté ou mis à jour de manière significative les articles d'aide suivants. Ces articles ne sont pas nécessairement liés aux nouvelles fonctionnalités ajoutées pour cette version, comme indiqué dans la section précédente. Cependant, elles peuvent vous aider à tirer le meilleur parti des fonctionnalités existantes.

| Fonctionnalités | Articles nouveaux ou mis à jour |
|---|---|
| Gestion des coûts | [États de valeur de stock](../cost-management/inventory-value-report-storage.md) |
| Gestion des coûts | [Exemples et logique de l’état de valeur des stocks](../cost-management/inventory-value-report-examples.md) |
| Planification générale | [Paramètres de date et d’heure utilisés par l’optimisation de la planification](../master-planning/planning-optimization/date-time-used.md) |
| Planification générale | [Paramétrage de la prévision de la demande](../master-planning/demand-forecasting-setup.md) |
| Planification générale | [Utiliser le journal du stock de sécurité pour mettre à jour la couverture minimale pour les articles](../master-planning/safety-stock-journal.md) |
| Contrôle de la production | [Personnaliser l’interface d’exécution de l’atelier de production](../production-control/production-floor-execution-customize.md) |
| Contrôle de la production | [Appliquer un style à l’interface d’exécution de l’atelier de production](../production-control/production-floor-execution-styles.md) |
| Ventes et marketing | [Planifier le nettoyage des données de l’historique des ventes](../sales-marketing/sales-update-history-cleanup-performance-improvements.md) |
| Gestion des entrepôts | [Comptes d’utilisateur d’appareil mobile](../warehousing/mobile-device-work-users.md) |

## <a name="additional-resources"></a>Ressources supplémentaires

### <a name="platform-updates-for-finance-and-operations-apps"></a>Mises à jour de plateforme pour les applications Finance et Opérations

Microsoft Dynamics 365 Supply Chain Management 10.0.24 inclut les mises à jour de plateforme. Pour en savoir plus, consultez [Mises à jour de plateforme pour les applications Finance et Opérations, version 10.0.24 (février 2022)](../../fin-ops-core/dev-itpro/get-started/whats-new-platform-updates-10-0-24.md).

### <a name="bug-fixes"></a>Correctifs de bogue

Pour plus d’informations sur les correctifs de bogues inclus dans chacune des mises à jour qui font partie de 10.0.24, connectez-vous à Lifecycle Services (LCS) et consultez l’[Article de la base de connaissances](https://fix.lcs.dynamics.com/Issue/Details?bugId=641306&dbType=3&qc=5b1d5e49c96b8a5cfb5601889a413e6f3773ba6500f9bc47310dcc5c54fff42f).

### <a name="dynamics-365-and-industry-clouds-2021-release-wave-2-plan"></a>Dynamics 365 et les clouds du secteur : plan de la 2e vague de lancement 2021

Vous souhaitez connaître les fonctionnalités à venir et récemment publiées dans nos applications ou notre plateforme d’entreprise ?

Consultez [Dynamics 365 et les clouds du secteur : plan de la 2e vague de lancement 2021](/dynamics365-release-plan/2021wave2/). Nous avons capturé tous les détails, de bout en bout, de haut en bas, dans un document unique que vous pouvez utiliser pour la planification.

### <a name="removed-and-deprecated-supply-chain-management-features"></a>Fonctionnalités de Supply Chain Management supprimées et obsolètes

L'article [Fonctionnalités supprimées ou obsolètes dans Dynamics 365 Supply Chain Management](removed-deprecated-features-scm-updates.md) décrit les fonctionnalités qui ont été, ou qui doivent être supprimées ou déconseillées pour Supply Chain Management.

- Une fonction *supprimée* n’est plus disponible dans le produit.
- Une fonction *déconseillée* n’est pas en développement actif et peut être supprimée dans une prochaine mise à jour.

Avant que toute fonctionnalité ne soit supprimée du produit, l’avis d’obsolescence sera annoncé dans l'article [Fonctionnalités supprimées ou obsolètes dans Dynamics 365 Supply Chain Management](removed-deprecated-features-scm-updates.md) 12 mois avant le retrait.

Pour les dernières modifications qui n’affectent que le temps de compilation, mais qui sont compatibles d’un point de vue binaire avec les environnements sandbox et de production, le temps d’obsolescence sera inférieur à 12 mois. Ce sont généralement des mises à jour fonctionnelles qui doivent être apportées au compilateur.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
