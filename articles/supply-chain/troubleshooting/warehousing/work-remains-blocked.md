---
title: Le travail reste bloqué
description: Le travail reste bloqué
author: perlynne
ms.date: 04/15/2021
ms.topic: troubleshooting
ms.search.form: WHSWorkTableListPage_WHSWorkUnblocking
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-05-15
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: f85364d1ecfadc36b26c3395ab4402d3cb3b1603
ms.sourcegitcommit: 5f5afb46431e1abd8fb6e92e0189914b598dc7fd
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/21/2021
ms.locfileid: "5924128"
---
# <a name="work-remains-blocked"></a>Le travail reste bloqué

Code d'erreur : WHSWorkBlockingExecutingWaveReason_ErrorMessage

## <a name="symptoms"></a>Symptômes

Le système affiche le message d'erreur suivant :

> Le travail %1 reste bloqué, car la vague associée %2 présente le statut %3.

## <a name="cause"></a>Cause

Le travail est en cours de traitement dans une vague et ne peut pas être débloqué, comme l'indique l'une des conditions suivantes :

- Dans l'onglet **Motifs de blocage**, le champ **Motif de blocage de travail** pour une ou plusieurs lignes est défini sur *Traitement de la vague*.
- Lorsque vous sélectionnez **Vague** dans le groupe **Informations associées** de l'onglet **Informations associées** du volet Actions, le champ **Statut de la vague** est défini sur *Traitement*.

## <a name="resolution"></a>Résolution

Dans le volet Actions, sous l’onglet **Informations associées**, dans le groupe **Informations associées**, cliquez sur **Vague**. Puis, sur la page **Vagues**, dans le volet Actions, sous l’onglet **Vague**, dans le groupe **Vague**, sélectionnez **Nettoyage des données de vague**.

## <a name="workaround"></a>Solution de contournement

Si les étapes précédentes n'ont pas résolu le problème, vous pouvez annuler le travail en suivant ces étapes.

1. Allez dans **Gestion des entrepôts \> Tâches périodiques \> Nettoyer \> Annuler le travail**.
1. Dans le champ **ID de travail**, spécifiez l'ID de travail que vous souhaitez annuler et dont le **Statut de travail** est actuellement *Ouvert*, *En cours*, *Annulé*, *Combiné* ou *Fermé*.
1. Cliquez sur **OK**.
1. Sélectionnez **Oui** pour confirmer que vous souhaitez annuler le travail.

Pour en savoir plus, voir [Annuler le travail en entrepôt pour la gestion des exceptions](../../warehousing/cancel-warehouse-work.md).
