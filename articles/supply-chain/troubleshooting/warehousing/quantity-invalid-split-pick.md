---
title: Quantité non valide pour l'unité %1 lors de l'exécution d'un prélèvement fractionné
description: Lorsque vous effectuez un prélèvement fractionné sur plusieurs lots, vous pouvez recevoir une erreur indiquant que la quantité n'est pas valide pour l'unité %1. Cette page permet de résoudre le problème.
author: perlynne
ms.date: 06/24/2021
ms.topic: troubleshooting
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 4627db7400d6ccd81f25f100de4696058ce35c42
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/07/2021
ms.locfileid: "7476293"
---
# <a name="quantity-is-not-valid-when-performing-a-split-pick-across-multiple-batches"></a>La quantité n'est pas valide lors de l'exécution d'un prélèvement fractionné sur plusieurs lots

## <a name="symptoms"></a>Symptômes

Lorsque vous essayez d’effectuer un *prélèvement fractionné* sur plusieurs lots, vous recevez le message d'erreur suivant :

> La quantité n'est pas valide pour l'unité %1.

## <a name="resolution"></a>Résolution

Le magasinier doit utiliser le processus *Prélèvement partiel* dans l’application mobile Warehouse Management. Si vous essayez de sélectionner plusieurs lots au même endroit, vous pouvez également utiliser l’option **Complet** dans l’application.
