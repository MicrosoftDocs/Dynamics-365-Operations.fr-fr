---
title: L'annulation du rapport comme terminé crée une transaction en cours inattendue
description: L'annulation du reporting comme terminé avec marquage crée une transaction en cours où la quantité contrepassée a les mêmes dimensions de stock que la transaction contrepassée.
author: niwang
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: ProdTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: smnatara
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: 73ebc45ee83516f573c3f73ef8106da9ae44c590c05d8dbd08520bc5ef19e49a
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6714208"
---
# <a name="reversal-of-reporting-as-finished-creates-an-unexpected-open-transaction"></a>L'annulation du rapport comme terminé crée une transaction en cours inattendue

Numéro de la base de connaissances : 4612469

## <a name="symptoms"></a>Symptômes

Si vous annulez le reporting comme terminé avec marquage, le système crée une transaction en cours dans laquelle la quantité contrepassée a les mêmes dimensions de stock que la transaction qui a été contrepassée.

## <a name="resolution"></a>Résolution

Lorsque vous annulez une opération d'état comme terminé, la dimension de stock est initialisée à partir du journal de production. Par conséquent, il obtient le numéro de lot. En raison du marquage, les transactions de commande client hériteront du numéro de lot.

La dimension peut être réinitialisée lorsque le rapport terminé est validé.
