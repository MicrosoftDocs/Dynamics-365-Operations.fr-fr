---
title: Votre journal de stock est verrouillé et la tâche de traitement par lots du workflow ne fonctionne pas
description: L’un de vos journaux de stock est verrouillé par une opération et n’est pas débloqué
author: sherry-zheng
ms.date: 05/31/2021
ms.topic: troubleshooting
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2021-05-31
ms.dyn365.ops.version: 10.0.16
ms.openlocfilehash: 8b21ec2e2b3b8546dcb138422c5540053392c179
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/07/2021
ms.locfileid: "7476309"
---
# <a name="your-inventory-journal-is-locked-and-the-workflow-batch-job-doesnt-work"></a>Votre journal de stock est verrouillé et la tâche de traitement par lots du workflow ne fonctionne pas

## <a name="symptoms"></a>Symptômes

L’un de vos journaux d’inventaire est verrouillé par une opération et n’est pas lancé. Par exemple, si une erreur inconnue se produit lors de la validation (qui est une opération de verrouillage du système), le journal peut rester à l’état verrouillé par le système. Dans ce cas, le gestionnaire des éléments de travail du workflow générera une erreur lors de la validation du verrouillage.

## <a name="resolution"></a>Résolution

Connectez-vous à l’instance de SQL Server pour Supply Chain Management et vérifiez si **InventJournalTable.SystemBlocked** est défini sur *1*. Si tel est le cas, assurez-vous que le journal n’est pas à l’état verrouillé, puis redéfinissez **InventJournalTable.SystemBlocked** sur *0*.
