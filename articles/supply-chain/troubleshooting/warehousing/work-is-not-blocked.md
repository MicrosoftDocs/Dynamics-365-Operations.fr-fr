---
title: Le travail n'est pas bloqué
description: Le travail n'est pas bloqué
author: perlynne
ms.date: 04/15/2021
ms.topic: troubleshooting
ms.search.form: WHSWorkTable_WHSWorkUnblocking
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-05-15
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: d64ab282972e46e8857581b59e5705dd15667328
ms.sourcegitcommit: 5f5afb46431e1abd8fb6e92e0189914b598dc7fd
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/21/2021
ms.locfileid: "5924202"
---
# <a name="work-isnt-blocked"></a>Le travail n'est pas bloqué

Code d'erreur : WHSUnblockNotBlockedWorkErrorMessage

## <a name="symptoms"></a>Symptômes

Le système affiche le message d'erreur suivant :

> Le travail avec l'ID %1 n'est pas bloqué.

## <a name="cause"></a>Cause

L'option **Vague bloquée** sur la vague est définie sur *Non*. Le travail ne peut pas être débloqué car il n'est actuellement pas bloqué.

## <a name="resolution"></a>Résolution

 Seul un travail pour lequel l'option **Vague bloquée** est définie sur *Oui* peut être débloqué.
