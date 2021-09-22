---
title: Avertissements ou erreurs lors de la modification du statut d’une période comptable sans clôture des stocks
description: Avertissements ou erreurs lors de la modification du statut d’une période comptable sans clôture des stocks
author: AndersGirke
ms.date: 05/31/2021
ms.topic: troubleshooting
ms.search.form: InventAgingStorage, InventAgingStorageChart, InventAgingStorageDetails, InventValueProcess, InventValueReportSetup, InventClosing
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: aevengir
ms.search.validFrom: 2021-05-31
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: 05851753e29da75f014d2cc77e2b8df259620eee
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/07/2021
ms.locfileid: "7476322"
---
# <a name="warnings-or-errors-on-changing-ledger-period-status-without-closing-inventory"></a>Avertissements ou erreurs lors de la modification du statut d’une période comptable sans clôture des stocks

Microsoft a introduit les validations suivantes pour éviter les problèmes causés par un processus de fin de période incorrect autour des coûts. Si vous rencontrez l’un des messages d’erreur suivants, reportez-vous à [KB 4561987](https://fix.lcs.dynamics.com/Issue/Details?kb=4561987&bugId=445351&dbType=3&qc=f514f2adcddcddceec43af58c26ae8a9020effdc7cdfe085d9d0deeb8cc7b6a3) pour plus d’informations sur la résolution de ces problèmes.

- Vous êtes sur le point d’exécuter un recalcul avec une date %1 (10-02-2019). Le dernier recalcul enregistré a été exécuté dans une période précédente avec une date %2 (20-01-2019). Aucune exécution d’une clôture de stock avec une date %3 (31-01-2019) correspondant à la fin de la période a été enregistrée. N’oubliez pas d’exécuter une clôture de stock à partir du %3 (31-01-2019) correspondant à la fin de la période. L’évaluation des stocks, le coût des marchandises vendues et les écarts peuvent ne pas être corrects dans la comptabilité auxiliaire ou la comptabilité générale tant que cette opération n’a pas été exécutée.

- Vous êtes sur le point de modifier le statut de la période comptable %1 à %2. Aucune exécution d’une clôture de stock avec une date %3 correspondant à la fin de la période a été enregistrée. Exécutez une clôture d’inventaire le %3 correspondant à la fin de la période avant de changer le statut. L’évaluation des stocks, le coût des marchandises vendues et les écarts peuvent ne pas être corrects dans la comptabilité auxiliaire ou la comptabilité générale tant que cette opération n’a pas été exécutée. Déclaré par une entité juridique %4. Pour le moment, cette action est indiquée à titre d’information, mais vous devrez l’effectuer à l’avenir.

- La structure du compte %1 a été modifié. Un ou plusieurs comptes principaux %2 n’existe plus. Ces comptes principaux sont requis par le %3 avec une date %4. Ajoutez ces comptes principaux à la structure du compte %1 avant de pouvoir reprendre la tâche %3. Pour le moment, cette action est indiquée à titre d’information, mais vous devrez l’effectuer à l’avenir.

- Vous êtes sur le point d’exécuter une clôture de stock avec une date %1 (31-01-2019). Aucune exécution d’un calcul de comptabilité à rebours avec une date %2 (31-01-2019) correspondant à la fin de la période a été enregistrée. N’oubliez pas d’exécuter un calcul de comptabilité à rebours avec une date de %3 (31-01-2019) correspondant à la fin de la période. L’évaluation des stocks, le coût des marchandises vendues et les écarts peuvent ne pas être corrects dans la comptabilité auxiliaire ou la comptabilité générale tant que cette opération n’a pas été exécutée.

- Vous êtes sur le point d’exécuter un calcul de comptabilité à rebours avec une date %1 (28-02-2019). Le dernier calcul de comptabilité à rebours enregistré a été exécuté dans une période précédente avec une date %2 (31-01-2019). Aucune exécution d’une clôture de stock avec une date %3 (31-01-2019) correspondant à la fin d’une période a été enregistrée.

N’oubliez pas d’exécuter une clôture de stock à partir du %3 (31-01-2019) correspondant à une fin de la période. L’évaluation des stocks, le coût des marchandises vendues et les écarts peuvent ne pas être corrects dans la comptabilité auxiliaire ou la comptabilité tant que la clôture de stock n’a pas été exécuté.