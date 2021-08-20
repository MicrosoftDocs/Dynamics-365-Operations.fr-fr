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
ms.openlocfilehash: 424ad46281612f6a3e8cb4c90478a39f757d5416c3ce1d77ed6ff6dba7b20dcb
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6723453"
---
# <a name="when-a-catch-weight-quantity-is-split-minimum-quantity-is-used-instead-of-nominal-quantity"></a>Lorsqu'une quantité de poids de capture est fractionnée, la quantité minimale est utilisée au lieu de la quantité nominale

Numéro de la base de connaissances : 4612073

## <a name="symptoms"></a>Symptômes

Lorsqu'une quantité de poids variable est divisée en lots, le champ **Choisir la quantité** utilise la quantité minimale définie pour l'article, et non la quantité nominale.

## <a name="resolution"></a>Résolution

Le système se comporte comme prévu. Le système utilise la configuration de quantité minimale de chaque article pour le prélèvement.
