---
title: Lorsqu'une quantité de poids de capture est fractionnée, la quantité minimale est utilisée au lieu de la quantité nominale
description: Lorsqu'une quantité de poids variable est divisée en lots, le champ Choisir la quantité utilise la quantité minimale définie pour l'article, et non la quantité nominale.
author: niwang
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: WMSPickingRegistration
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: smnatara
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: 185365ced5c4516d8fcdbdca88794d0078615888
ms.sourcegitcommit: c011a2ef66b38e71ddaf003f7d243677bb2707c5
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/12/2021
ms.locfileid: "6026516"
---
# <a name="when-a-catch-weight-quantity-is-split-minimum-quantity-is-used-instead-of-nominal-quantity"></a>Lorsqu'une quantité de poids de capture est fractionnée, la quantité minimale est utilisée au lieu de la quantité nominale

Numéro de la base de connaissances : 4612073

## <a name="symptoms"></a>Symptômes

Lorsqu'une quantité de poids variable est divisée en lots, le champ **Choisir la quantité** utilise la quantité minimale définie pour l'article, et non la quantité nominale.

## <a name="resolution"></a>Résolution

Le système se comporte comme prévu. Le système utilise la configuration de quantité minimale de chaque article pour le prélèvement.
