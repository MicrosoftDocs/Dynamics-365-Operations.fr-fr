---
title: La mise à jour Déclarer terminé échoue avec une erreur de quantité manquante
description: Si vous essayez de mettre fin à un ordre de fabrication pendant que vous signalez la quantité d’erreur, mais pas la quantité de temps ou de matière, la mise à jour Déclarer terminé échoue.
author: SmithaNataraj
ms.date: 06/24/2021
ms.topic: troubleshooting
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: smnatara
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 7785549c47063727f2749749940c1a96a351e70f
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/07/2021
ms.locfileid: "7476307"
---
# <a name="report-as-finished-update-fails-with-a-missing-quantity-error"></a>La mise à jour Déclarer terminé échoue avec une erreur de quantité manquante

## <a name="symptoms"></a>Symptômes

Vous essayez de déclarer un ordre de fabrication comme terminé pendant que vous signalez la quantité d’erreur, mais pas pendant que vous signalez la quantité de temps ou de matière. La mise à jour Déclarer terminé échoue lorsque vous essayez de mettre fin à l’ordre de fabrication et vous recevez le message d’erreur suivant :

> Quantité déclarée terminée manquante.

## <a name="resolution"></a>Résolution

Si vous signalez la quantité d’erreur sur un ordre de fabrication, vous devez également déclarer la quantité correcte.
