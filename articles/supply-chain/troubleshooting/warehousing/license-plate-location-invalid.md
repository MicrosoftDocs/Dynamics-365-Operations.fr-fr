---
title: Erreur de contenant ou d'emplacement non valide dans l'application mobile
description: Lorsque vous numérisez un ID de contenant ou un emplacement, vous pouvez recevoir une erreur indiquant qu'il n'est pas valide. Assurez-vous que l’ID de contenant n’est pas réservé par autre chose.
author: perlynne
ms.date: 06/24/2021
ms.topic: troubleshooting
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: f9f10dbade0d13b8fc4b0fc92981d84e6e28e83e
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/07/2021
ms.locfileid: "7476387"
---
# <a name="invalid-license-plate-or-location-error-when-scanning-in-the-mobile-app"></a>Erreur de contenant ou d'emplacement non valide lors de la numérisation dans l'application mobile

## <a name="symptoms"></a>Symptômes

Lorsque vous numérisez un ID de contenant ou un emplacement, vous pouvez recevoir le message d'erreur suivant :

> Le contenant ou l'emplacement n'est pas valide.

## <a name="resolution"></a>Résolution

Assurez-vous que l’ID de contenant n’est pas réservé par autre chose. Ce problème se produisait lorsque la valeur numérisée par un utilisateur dans l’application mobile Warehouse Management était à la fois un emplacement valide et un ID de contenant valide. Cependant, ce problème a été résolu dans la version 10.0.11.
