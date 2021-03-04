---
title: Dépannage de la gestion des coûts
description: Cette rubrique décrit comment résoudre les problèmes que vous pourriez rencontrer lors de l'utilisation de la gestion des coûts.
author: riluan
manager: tfehr
ms.date: 10/13/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventAgingStorage, InventAgingStorageChart, InventAgingStorageDetails, InventValueProcess, InventValueReportSetup, InventClosing
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: riluan
ms.search.validFrom: 2020-10-13
ms.dyn365.ops.version: Release 10.0.15
ms.openlocfilehash: e84bb167395c06295b0e8ef8b9fd98aa4bc0cc14
ms.sourcegitcommit: aeee39c01d3f93a6dfcf2013965fa975a740596a
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/28/2020
ms.locfileid: "4428333"
---
# <a name="troubleshoot-cost-management"></a>Dépannage de la gestion des coûts

Cette rubrique décrit comment résoudre les problèmes que vous pourriez rencontrer lors de l'utilisation de la gestion des coûts.

## <a name="functional-gaps-between-the-inventory-valueaging-reports-and-their-storage-versions"></a>Écarts fonctionnels entre les rapports de valeur d'inventaire/chronologiques et leurs versions de stockage

Les fonctionnalités [Stockage des rapports sur la chronologie du stock](inventory-aging-report-storage.md) et [Rapport de stockage de la valeur de stock](inventory-value-report-storage.md) permettent à Supply Chain Management d'afficher de grands volumes de transactions de stock. Dans chaque cas, les résultats du rapport sont enregistrés pour la navigation et l'exportation, contrairement aux versions sans stockage de ces rapports. Cependant, certaines fonctionnalités qui existent dans les versions sans stockage de ces rapports n'existent pas dans les versions de stockage. Les sous-sections suivantes résument les différences et proposent des solutions.

### <a name="storage-reports-dont-include-subtotals-even-if-they-are-enabled-in-the-report-layout"></a>Les rapports de stockage n'incluent pas les sous-totaux, même s'ils sont activés dans la disposition du rapport

Les sous-totaux peuvent entraîner des problèmes lors de l'exportation du résultat, en particulier si les utilisateurs modifient la séquence d'enregistrement.

Pour vérifier les sous-totaux, vous pouvez exporter le résultat dans Microsoft Excel. Sinon, si vous souhaitez vérifier les sous-totaux dans Supply Chain Management, utilisez [Gestion des fonctionnalités](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) pour activer les fonctionnalités *Nouveau contrôle du réseau* et *(Aperçu) Regroupement en grilles*, qui offrent un moyen beaucoup plus flexible de voir le sous-total pour tout groupe par colonne. Pour plus d’informations, voir [Capacités de grille](../../fin-ops-core/fin-ops/get-started/grid-capabilities.md).

### <a name="inventory-value-storage-report-doesnt-support-ledger-account-information"></a>Le rapport de stockage de la valeur de stock ne prend pas en charge les informations du compte général

Vous pouvez exécuter la balance comptable pour obtenir le solde des comptes de stock et le comparer au rapport **Stockage de valeur de stock**.

## <a name="warnings-or-errors-are-shown-when-changing-a-ledger-period-status-without-closing-inventory"></a>Des avertissements ou des erreurs s'affichent lors de la modification du statut d'une période comptable sans clôture de stock

Microsoft a introduit les validations suivantes pour éviter les problèmes causés par un processus de fin de période incorrect autour des coûts. Si vous rencontrez l'un des messages d'erreur suivants, reportez-vous à [KB 4561987](https://fix.lcs.dynamics.com/Issue/Details?kb=4561987&bugId=445351&dbType=3&qc=f514f2adcddcddceec43af58c26ae8a9020effdc7cdfe085d9d0deeb8cc7b6a3) pour plus d'informations sur la résolution de ces problèmes.

- Vous êtes sur le point d'exécuter un recalcul avec une date %1 (10-02-2019). Le dernier recalcul enregistré a été exécuté dans une période précédente avec une date %2 (20-01-2019). Aucune exécution d'une clôture de stock avec une date %3 (31-01-2019) correspondant à la fin de la période a été enregistrée. N'oubliez pas d'exécuter une clôture de stock à partir du %3 (31-01-2019) correspondant à la fin de la période. L'évaluation des stocks, le coût des marchandises vendues et les écarts peuvent ne pas être corrects dans la comptabilité auxiliaire ou la comptabilité tant que cela n'a pas été exécuté.

- Vous êtes sur le point de modifier le statut de la période comptable %1 à %2. Aucune exécution d'une clôture de stock avec une date %3 correspondant à la fin de la période a été enregistrée. Exécutez une clôture d'inventaire le %3 correspondant à la fin de la période avant de changer le statut. L'évaluation des stocks, le coût des marchandises vendues et les écarts peuvent ne pas être corrects dans la comptabilité auxiliaire ou la comptabilité tant que cela n'a pas été exécuté. Déclaré par une entité juridique %4. Pour le moment, cette action est indiquée à titre d’information, mais vous devrez l’effectuer à l’avenir.

- La structure du compte %1 a été modifié. Un ou plusieurs comptes principaux %2 n'existe plus. Ces comptes principaux sont requis par le %3 avec une date %4. Ajoutez ces comptes principaux à la structure du compte %1 avant de pouvoir reprendre la tâche %3. Pour le moment, cette action est indiquée à titre d’information, mais vous devrez l’effectuer à l’avenir.

- Vous êtes sur le point d'exécuter une clôture de stock avec une date %1 (31-01-2019). Aucune exécution d'un calcul de comptabilité à rebours avec une date %2 (31-01-2019) correspondant à la fin de la période a été enregistrée. N'oubliez pas d'exécuter un calcul de comptabilité à rebours avec une date de %3 (31-01-2019) correspondant à la fin de la période. L'évaluation des stocks, le coût des marchandises vendues et les écarts peuvent ne pas être corrects dans la comptabilité auxiliaire ou la comptabilité tant que cela n'a pas été exécuté.

- Vous êtes sur le point d'exécuter un calcul de comptabilité à rebours avec une date %1 (28-02-2019). Le dernier calcul de comptabilité à rebours enregistré a été exécuté dans une période précédente avec une date %2 (31-01-2019). Aucune exécution d'une clôture de stock avec une date %3 (31-01-2019) correspondant à la fin d'une période a été enregistrée.
N'oubliez pas d'exécuter une clôture de stock à partir du %3 (31-01-2019) correspondant à une fin de la période. L'évaluation des stocks, le coût des marchandises vendues et les écarts peuvent ne pas être corrects dans la comptabilité auxiliaire ou la comptabilité tant que la clôture de stock n'a pas été exécuté.

## <a name="inventory-aging-report-discrepancies"></a>Écarts des états de balance âgée

Le **Rapport de vieillissement du stock** affiche des valeurs différentes lorsqu'elles sont visualisées à différentes dimensions de stockage (telles que le site ou l'entrepôt). Pour plus d'informations sur la logique de création de rapports, voir [Exemples de rapport de vieillissement du stock et logique](inventory-aging-report.md).


[!INCLUDE[footer-include](../../includes/footer-banner.md)]