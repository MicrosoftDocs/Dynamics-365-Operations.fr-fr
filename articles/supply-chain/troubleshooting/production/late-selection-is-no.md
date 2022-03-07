---
title: La sélection tardive n'est pas respectée lorsque les ordres de fabrication sont réinitialisés via un travail par lots
description: Lorsque vous utilisez un travail par lots récurrent pour réinitialiser le statut d'un ordre de fabrication, les sélections tardives ne sont pas respectées.
author: johanhoffmann
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: ProdTableListPage
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: e53198f427f4060421a4f0078277682c43db1320
ms.sourcegitcommit: c011a2ef66b38e71ddaf003f7d243677bb2707c5
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/12/2021
ms.locfileid: "6026501"
---
# <a name="late-selection-isnt-respected-when-production-orders-are-reset-via-a-batch-job"></a>La sélection tardive n'est pas respectée lorsque les ordres de fabrication sont réinitialisés via un travail par lots

Numéro de la base de connaissances : 4614634

## <a name="symptoms"></a>Symptômes

Lorsque vous utilisez un travail par lots récurrent pour réinitialiser le statut d'un ordre de fabrication, les sélections tardives ne sont pas respectées.

## <a name="resolution"></a>Résolution

La conception actuelle ne prend pas en charge l'utilisation de sélections tardives pour le processus *Statut de réinitialisation*.
