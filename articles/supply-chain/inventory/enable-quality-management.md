---
title: Activer la gestion de la qualité et de la non-conformité
description: Cette rubrique fournit une vue d'ensemble du processus de configuration et de paramétrage des fonctionnalités de gestion de la qualité et des non-conformités dans Microsoft Dynamics 365 Supply Chain Management.
author: yufeihuang
ms.date: 03/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: InventTestAssociationTable, InventTestGroup, InventTestItemQualityGroup, InventTestTable, InventTestVariable, InventTestVariableOutcome, InventParameters, InventProblemType, InventProblemTypeSetup, InventQuarantineZone, InventTestDiagnosticType, InventTestReportSetup, SysUserManagement, InventTestRelatedOperations
audience: Application User
ms.reviewer: kamaybac
ms.custom: 94003
ms.assetid: a1d9417b-268f-4334-8ab6-8499d6c3acf0
ms.search.region: Global
ms.search.industry: Distribution
ms.author: yufeihuang
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 7c2c8b7e9a1a8d7692e1d2215e38de1b0f4d2d82
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/29/2021
ms.locfileid: "7567413"
---
# <a name="enable-quality-and-nonconformance-management"></a>Activer la gestion de la qualité et de la non-conformité

[!include [banner](../includes/banner.md)]

Cette rubrique fournit une vue d'ensemble du processus de configuration et de paramétrage des fonctionnalités de gestion de la qualité et des non-conformités dans Microsoft Dynamics 365 Supply Chain Management.

## <a name="enable-quality-and-nonconformance-management"></a><a name="enable-qm"></a>Activer la gestion de la qualité et de la non-conformité

Suivez ces étapes pour activer la gestion de la qualité sur votre système.

1. Allez dans **Gestion des stocks \> Configuration \> Paramètres de gestion des stocks et des entrepôts**.
1. Sur l'onglet **Gestion de la qualité**, définissez l'option **Utiliser la gestion de la qualité** sur *Oui*.
1. Dans le champ **Taux horaire**, entrez un taux horaire de main-œuvre dans la devise locale. Le taux horaire permet de calculer les coûts des opérations associées à une non-conformité. Le taux horaire et les coûts calculés fournissent des informations de référence pour une non-conformité. Ils n’interagissent pas avec les autres fonctionnalités.
1. Sélectionnez **Paramétrage d’état**.
1. Ajoutez de nouvelles lignes pour les différents types d'état et sélectionnez le type de document à utiliser pour chaque état.
1. Fermez la page.
1. Fermez la page.

## <a name="quality-management-configuration-process"></a>Processus de configuration de la gestion de la qualité

Avant de pouvoir commencer à utiliser les fonctionnalités de gestion de la qualité et générer des ordres de qualité, vous devez configurer le système et le paramétrer. Voici la liste des étapes requises pour configurer la gestion de la qualité.

1. [Activer la gestion de la qualité et de la non-conformité](#enable-qm).
1. Optionnel : [Configurer les instruments de test](quality-test-instruments.md).
1. [Configurer les tests](quality-tests.md).
1. [Configurer les variables de test et les résultats](quality-test-variables.md).
1. [Configurer les groupes de test](quality-test-groups.md).
1. Optionnel : [Configurer les groupes de qualité et créer des liens vers les produits](quality-groups.md).
1. Optionnel : [Configurer les associations de qualité](quality-associations.md).

Une fois la configuration terminée, vous pouvez commencer à créer et à traiter des ordres de qualité. Pour plus d’informations sur la création et l’utilisation des ordres de qualité, consultez [Ordres de qualité](quality-orders.md).

## <a name="nonconformance-management-configuration-process"></a>Processus de configuration de la gestion de la non-conformité

Avant de pouvoir commencer à utiliser les fonctionnalités de gestion de la non-conformité et générer des non-conformités, vous devez configurer le système et le paramétrer. Voici la liste des étapes requises pour configurer la gestion de la non-conformité.

1. [Activer la gestion de la qualité et de la non-conformité](#enable-qm).
1. [Configurer les collaborateurs chargés d'approuver les non-conformités](quality-responsible-workers.md).
1. [Configurer les types de problèmes](quality-problem-types.md).
1. [Configurer les zones de mise en quarantaine](quality-quarantine-zones.md).
1. [Configurer les types de diagnostics](quality-diagnostic-types.md).
1. [Configurer les opérations](quality-operations.md).
1. Optionnel : [Configurer les frais de qualité](quality-charges.md).

Une fois la configuration terminée, vous pouvez commencer à créer et à traiter des non-conformités. Pour plus d'informations sur la création et le traitement des non-conformités, voir [Création et traitement des non-conformités](tasks/create-process-non-conformance.md).

## <a name="additional-resources"></a>Ressources supplémentaires

- [Vue d’ensemble de la gestion de la qualité](quality-management-processes.md)
- [Activer la gestion de la qualité et de la non-conformité](enable-quality-management.md)
- [Gestion de la qualité pour les processus d'entrepôt](quality-management-for-warehouses-processes.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
