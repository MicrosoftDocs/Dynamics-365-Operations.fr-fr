---
title: La dernière ligne de travail clôturée doit être un placement.
description: La dernière ligne de travail clôturée doit être un placement.
author: perlynne
ms.date: 04/15/2021
ms.topic: troubleshooting
ms.search.form: WHSWorkTable_WHSWorkCancel, WHSWorkTableListPage_WHSWorkCancel
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-05-15
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: a5b78154b51252b3ac96ba28c254e823caf87019
ms.sourcegitcommit: 5f5afb46431e1abd8fb6e92e0189914b598dc7fd
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/21/2021
ms.locfileid: "5924373"
---
# <a name="the-last-closed-work-line-must-be-a-put"></a>La dernière ligne de travail clôturée doit être un placement.

Code d’erreur : WAX1285

## <a name="symptoms"></a>Symptômes

Le système affiche le message d'erreur suivant :

> La dernière ligne de travail clôturée doit être un placement.

## <a name="cause"></a>Cause

Le travail ne peut pas être annulé dans son état actuel.

Sur la dernière ligne de travail, le champ **Statut de travail** est défini sur *Clôturé*, mais le champ **Type de travail** n'est pas défini sur *Placement*.

## <a name="resolution"></a>Résolution

Pour annuler le travail, procédez comme suit :

1. Allez dans **Gestion des entrepôts \> Tâches périodiques \> Nettoyer \> Annuler le travail**.
1. Dans le champ **ID de travail**, spécifiez l'ID du travail que vous souhaitez annuler.
1. Cliquez sur **OK**.
1. Sélectionnez **Oui** pour confirmer que vous souhaitez annuler le travail.

Pour en savoir plus, voir [Annuler le travail en entrepôt pour la gestion des exceptions](../../warehousing/cancel-warehouse-work.md).
