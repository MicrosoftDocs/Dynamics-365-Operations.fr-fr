---
title: La valeur de délai n’est pas mise à jour lorsque vous replanifiez un ordre prévisionnel
description: La valeur de délai n’est pas mise à jour lorsque vous replanifiez un ordre prévisionnel
author: ChristianRytt
ms.date: 05/31/2021
ms.topic: troubleshooting
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: crytt
ms.search.validFrom: 2021-05-31
ms.dyn365.ops.version: 10.0.13
ms.openlocfilehash: 566702913774cf002ab38e367f690a479d968657
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/07/2021
ms.locfileid: "7476359"
---
# <a name="the-delay-value-isnt-updated-when-you-reschedule-a-planned-order"></a>La valeur de délai n’est pas mise à jour lorsque vous replanifiez un ordre prévisionnel

## <a name="symptoms"></a>Symptômes

La valeur de délai n’est pas mise à jour lorsque vous replanifiez un ordre prévisionnel.

## <a name="resolution"></a>Résolution

Pour mettre à jour le délai des ordres planifiés, ouvrez la boîte de dialogue **Replanification** pour l’ordre planifié. Dans l’organisateur **Répartition**, assurez-vous que l’option **Traiter la vague au lancement dans l’entrepôt** est définie sur *Oui*.
