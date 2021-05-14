---
title: Le travail ne peut pas être annulé car il est bloqué
description: Le travail ne peut pas être annulé car il est bloqué
author: perlynne
ms.date: 04/15/2021
ms.topic: troubleshooting
ms.search.form: WHSWorkTable_WHSWorkCancel
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-05-15
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: a7ab4c7263947767164702fb7dd6da7573175253
ms.sourcegitcommit: 5f5afb46431e1abd8fb6e92e0189914b598dc7fd
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/21/2021
ms.locfileid: "5924277"
---
# <a name="work-cant-be-canceled-because-its-blocked"></a>Le travail ne peut pas être annulé car il est bloqué

Code d'erreur : WHSCancellationOfWorkBlockedByExecutingWave_ErrorMessage

## <a name="symptoms"></a>Symptômes

Le système affiche le message d'erreur suivant :

> Le travail %1 ne peut pas être annulé car il est bloqué par le type de motif %2. Le travail doit être débloqué avant de pouvoir être annulé.

## <a name="cause"></a>Cause

Le travail est bloqué par un utilisateur et ne peut pas être annulé.

Sur la page **Travail**, sur l'onglet **Général**, l'option **Bloqué** est définie sur *Oui*. Ce paramètre indique que le travail est bloqué. L'onglet **Motifs de blocage** montre pourquoi le travail a été bloqué.

## <a name="resolution"></a>Résolution

Pour débloquer le travail, sélectionnez l'onglet **Motifs de blocage**, puis suivez l'une de ces étapes :

- Si le champ **Motif de blocage de travail** est défini sur *Raison indéfinie* : Dans le volet Actions, sur l'onglet **Travail**, dans le groupe **Travail**, sélectionnez **Débloquer le travail**.
- Si le champ **Motif de blocage de travail** est défini sur *Traitement de la vague* : Dans le volet Actions, sous l’onglet **Informations associées**, dans le groupe **Informations associées**, sélectionnez **Vague**. Puis, sur la page **Vagues**, dans le volet Actions, sous l’onglet **Vague**, dans le groupe **Vague**, sélectionnez **Nettoyage des données de vague**.

## <a name="workaround"></a>Solution de contournement

Si les étapes précédentes n'ont pas résolu le problème, vous pouvez annuler le travail en suivant ces étapes.

1. Allez dans **Gestion des entrepôts \> Tâches périodiques \> Nettoyer \> Annuler le travail**.
1. Dans le champ **ID de travail**, spécifiez l'ID de travail que vous souhaitez annuler et dont le **Statut de travail** est actuellement *Ouvert*, *En cours*, *Annulé*, *Combiné* ou *Fermé*.
1. Cliquez sur **OK**.
1. Sélectionnez **Oui** pour confirmer que vous souhaitez annuler le travail.

Pour en savoir plus, voir [Annuler le travail en entrepôt pour la gestion des exceptions](../../warehousing/cancel-warehouse-work.md).
