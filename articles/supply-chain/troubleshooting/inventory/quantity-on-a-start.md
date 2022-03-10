---
title: La quantité d'une commande de quarantaine lancée n'est pas mise à jour lorsque la commande est fractionnée
description: Lorsque vous créez une commande de quarantaine et que vous essayez de la fractionner, la quantité de commande n'est pas mise à jour avec la quantité restante fractionnée.
author: niwang
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: InventQuarantineOrder
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: shawan
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: 4625570cb706199dca78f23b1864ca1d81cc66e896cf10d6d5f16cf1a9d1dc16
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6713492"
---
# <a name="quantity-on-a-started-quarantine-order-isnt-updated-when-the-order-is-split"></a>La quantité d'une commande de quarantaine lancée n'est pas mise à jour lorsque la commande est fractionnée

Numéro de la base de connaissances : 4613113

## <a name="symptoms"></a>Symptômes

Lorsque vous créez une commande de quarantaine et que vous essayez de la fractionner, la quantité de commande n'est pas mise à jour avec la quantité restante après le fractionnement.

## <a name="resolution"></a>Résolution

Le système ne modifie pas la quantité d'origine d'une commande de quarantaine pour garantir que vous pouvez suivre la quantité d'origine qui a été créée pour cette commande de quarantaine. Cependant, le système effectue le suivi de la quantité fractionnée à partir d'une commande de quarantaine. Pour effectuer ce suivi, il utilise un champ de base de données nommé `QuantityThatHasSplitIntoOtherQuarantineOrders`. Cependant, ce champ n'est pas visible dans l'interface utilisateur (UI).
