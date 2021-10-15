---
title: Créer et tenir à jour un blocage du stock
description: Cette rubrique explique comment utiliser un blocage du stock pour éviter que le stock physique disponible soit réservé par d’autres documents sources sortants.
author: yufeihuang
ms.date: 03/23/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: InventBlocking, InventItemIdLookupSimple, InventLocationIdLookup
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: yufeihuang
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: bad7d4e5794dc543bd750912ef0d3e4460e611b1
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/29/2021
ms.locfileid: "7572839"
---
# <a name="create-and-maintain-an-inventory-blocking"></a>Créer et tenir à jour un blocage du stock

[!include [banner](../../includes/banner.md)]

Cette rubrique explique comment utiliser un blocage du stock pour éviter que le stock physique disponible soit réservé par d’autres documents sources sortants. Avant de commencer les procédures de cette rubrique, vous devez disposer d'un article dans le stock physique disponible.

## <a name="block-inventory"></a>Bloquer le stock

Pour créer un enregistrement de blocage de stock afin que le stock soit bloqué, procédez comme suit.

1. Accédez à **Gestion des stocks \> Tâches périodiques \> Blocage du stock**.
1. Dans le volet Actions, sélectionnez **Nouveau**.
1. Dans l'en-tête du nouvel enregistrement de blocage, définissez le **Numéro d'article** sur l'élément que vous souhaitez bloquer, puis saisissez une description.
1. Dans le raccourci **Général**, dans le champ **Quantité**, saisissez le nombre d'articles à bloquer.
1. Sur le raccourci **Dimensions de stock**, spécifiez le site et l'entrepôt où se trouvent actuellement les éléments que vous souhaitez bloquer.
1. Dans le volet Actions, sélectionnez **Enregistrer**.

## <a name="update-the-conditions-of-the-inventory-blocking"></a>Mettre à jour les conditions du blocage du stock

Pour mettre à jour un enregistrement de blocage de stock, procédez comme suit.

1. Accédez à **Gestion des stocks \> Tâches périodiques \> Blocage du stock**.
1. Dans le volet de liste, sélectionnez l’enregistrement du blocage pertinent.
1. Modifiez l'enregistrement comme requis. Par exemple, vous pouvez modifier la valeur du champ **Date prévue** pour indiquer à quel moment il est prévu que le stock bloqué devienne disponible pour réservation. Si l'option **Reçus attendus** est sélectionnée, la date apparaîtra sur la transaction attendue. (L'option **Reçus attendus** est sélectionnée par défaut lorsque vous créez manuellement un enregistrement de blocage.)
1. Dans le volet Actions, sélectionnez **Enregistrer**.

## <a name="unblock-inventory"></a>Débloquer le stock

Pour supprimer un enregistrement de blocage de stock afin que le stock soit débloqué, procédez comme suit.

1. Accédez à **Gestion des stocks \> Tâches périodiques \> Blocage du stock**.
1. Dans le volet de liste, sélectionnez l’enregistrement du blocage pertinent.
1. Dans le volet Actions, sélectionnez **Supprimer**.
1. Vous êtes invité à confirmer l'opération. Sélectionnez **Oui** pour continuer.
1. Fermez la page.

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
