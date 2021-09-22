---
title: Écarts fonctionnels entre les rapports de valeur d’inventaire/chronologiques et leurs versions de stockage
description: Écarts fonctionnels entre les rapports de valeur d’inventaire/chronologiques et leurs versions de stockage
author: AndersGirke
ms.date: 05/31/2021
ms.topic: troubleshooting
ms.search.form: InventAgingStorage, InventAgingStorageChart, InventAgingStorageDetails
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: aevengir
ms.search.validFrom: 2021-05-31
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: a72e2d32e755e137cebbc0bf7afb0bed08fb93f2
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/07/2021
ms.locfileid: "7476360"
---
# <a name="functional-gaps-between-inventory-valueaging-reports-and-their-storage-versions"></a>Écarts fonctionnels entre les rapports de valeur d’inventaire/chronologiques et leurs versions de stockage

Les fonctionnalités [Stockage des rapports sur la chronologie du stock](/dynamics365/supply-chain/cost-management/inventory-aging-report-storage.md) et [Rapport de stockage de la valeur de stock](/dynamics365/supply-chain/cost-management/inventory-value-report-storage.md) permettent à Supply Chain Management d’afficher de grands volumes de transactions de stock. Dans chaque cas, les résultats du rapport sont enregistrés pour la navigation et l’exportation, contrairement aux versions sans stockage de ces rapports. Cependant, certaines fonctionnalités qui existent dans les versions sans stockage de ces rapports n’existent pas dans les versions de stockage. Les sous-sections suivantes résument les différences et proposent des solutions.

## <a name="storage-reports-dont-include-subtotals-even-if-they-are-enabled-in-the-report-layout"></a>Les rapports de stockage n’incluent pas les sous-totaux, même s’ils sont activés dans la disposition du rapport

Les sous-totaux peuvent entraîner des problèmes lors de l’exportation du résultat, en particulier si les utilisateurs modifient la séquence d’enregistrement.

Pour vérifier les sous-totaux, vous pouvez exporter le résultat dans Microsoft Excel. Sinon, si vous souhaitez vérifier les sous-totaux dans Supply Chain Management, utilisez [Gestion des fonctionnalités](/dynamics365/fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) pour activer les fonctionnalités *Nouveau contrôle du réseau* et *Regroupement en grilles*, qui offrent un moyen beaucoup plus flexible de voir le sous-total pour tout groupe par colonne. Pour plus d’informations, voir [Capacités de grille](/dynamics365/fin-ops-core/fin-ops/get-started/grid-capabilities.md).

## <a name="inventory-value-storage-report-doesnt-support-ledger-account-information"></a>Le rapport de stockage de la valeur de stock ne prend pas en charge les informations du compte général

Vous pouvez exécuter la balance comptable pour obtenir le solde des comptes de stock et le comparer au rapport **Stockage de valeur de stock**.
