---
title: Le workflow du journal de stock ne se termine jamais et le journal ne peut pas être traité
description: Une fois que vous avez envoyé un workflow d’approbation de journal, le traitement du workflow cesse de répondre et vous ne pouvez pas modifier ou traiter vos journaux.
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
ms.openlocfilehash: 5e8168a20a1fa4f52d28129eebb9931b31157ced
ms.sourcegitcommit: ab690bc897699ff8a4c489e749251fe0367050ca
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/26/2022
ms.locfileid: "8488965"
---
# <a name="inventory-journal-workflow-never-completes-and-the-journal-cant-be-processed"></a>Le workflow du journal de stock ne se termine jamais et le journal ne peut pas être traité

## <a name="symptoms"></a>Symptômes

Une fois que vous avez envoyé un workflow d’approbation de journal, le traitement du workflow cesse de répondre et vous ne pouvez pas modifier ou traiter vos journaux.

## <a name="resolution"></a>Résolution

Le traitement du workflow peut ne pas se terminer pour plusieurs raisons. Recherchez les problèmes suivants :

- Accédez à **Gestion des stocks &gt; Paramétrage &gt; Workflow de gestion des stocks** et examinez la configuration du workflow affecté. Pour plus d’informations, voir [Workflow d’approbation du journal d’inventaire](../../inventory/inventory-journal-workflow.md).
- Le workflow peut rencontrer une exception ou une erreur. Révisez l’historique des éléments de travail du workflow affecté pour voir s’il inclut une erreur d’application qui termine le workflow.
- Le journal d’inventaire ne peut être mis à jour ou modifié que s’il est approuvé. Si le rappel est actif, vous pouvez essayer de rappeler le journal. L’exécution de la tâche de traitement par lots du workflow peut être suspendue pour plusieurs raisons. Certaines de ces raisons peuvent être causées par le problème de structure du workflow.
