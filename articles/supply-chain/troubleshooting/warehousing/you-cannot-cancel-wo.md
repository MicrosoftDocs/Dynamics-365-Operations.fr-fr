---
title: Vous ne pouvez pas annuler un travail affecté à un utilisateur.
description: Vous ne pouvez pas annuler un travail affecté à un utilisateur.
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
ms.openlocfilehash: e5f6912cfb1d5be8e46b7989856af99f8a611c11
ms.sourcegitcommit: 5f5afb46431e1abd8fb6e92e0189914b598dc7fd
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/21/2021
ms.locfileid: "5924399"
---
# <a name="you-cant-cancel-work-that-is-on-a-user"></a>Vous ne pouvez pas annuler un travail affecté à un utilisateur.

Code d’erreur : WAX708

## <a name="symptoms"></a>Symptômes

Le système affiche le message d'erreur suivant :

> Vous ne pouvez pas annuler un travail affecté à un utilisateur.

## <a name="cause"></a>Cause

Le travail est verrouillé par un utilisateur et ne peut pas être annulé. Pour confirmer cela, ouvrez l'ID de travail, puis ouvrez l'onglet **Général**. Si le travail est verrouillé, le champ **Statut du travail** est défini sur *En cours*, et le champ **Verrouillé par** est défini sur un ID utilisateur.

## <a name="resolution"></a>Résolution

Pour annuler le travail, procédez comme suit :

1. Allez dans **Gestion des entrepôts \> Tâches périodiques \> Nettoyer \> Annuler le travail**.
1. Dans le champ **ID de travail**, spécifiez l'ID du travail que vous souhaitez annuler.
1. Cliquez sur **OK**.
1. Sélectionnez **Oui** pour confirmer que vous souhaitez annuler le travail.

Pour en savoir plus, voir [Annuler le travail en entrepôt pour la gestion des exceptions](../../warehousing/cancel-warehouse-work.md).
