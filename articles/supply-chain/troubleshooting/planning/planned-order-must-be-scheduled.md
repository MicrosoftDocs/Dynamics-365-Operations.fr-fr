---
title: L’ordre de fabrication prévisionnel doit être planifié avant de pouvoir être confirmé
description: Lorsque vous essayez de confirmer une commande planifiée, vous recevez un message d’erreur indiquant que la commande doit être planifiée avant de pouvoir être confirmée.
author: ankubik
ms.date: 06/10/2021
ms.topic: troubleshooting
ms.search.form: ReqTransPo
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: ankubik
ms.search.validFrom: 2021-06-10
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: a360cb3cbd26e1bc1ebb1baf1a6a4d8282c28c5c
ms.sourcegitcommit: 18ca2df785e9656fdd4e8c0734eca2b2624fda10
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/22/2021
ms.locfileid: "6294078"
---
# <a name="planned-production-order-must-be-scheduled-before-it-can-be-firmed"></a>L’ordre de fabrication prévisionnel doit être planifié avant de pouvoir être confirmé

Code d’erreur : SYS309802

## <a name="symptoms"></a>Symptômes

Lorsque vous essayez de confirmer une commande planifiée, vous recevez le message d’erreur suivant :

> L’ordre de fabrication prévisionnel doit être planifié avant de pouvoir être confirmé.

## <a name="cause"></a>Cause

Les dates de début et de fin planifiées ne peuvent pas être vides.

## <a name="resolution"></a>Résolution

Pour spécifier les dates de début et de fin de la commande planifiée, procédez comme suit.

1. Accédez à **Planification \> Planification \> Ordres prévisionnels**.
1. Ouvrez la commande planifiée concernée.
1. Dans le raccourci **Général**, dans la section **Planifié**, précisez les dates dans les champs **Date de début** et **Date de fin**.
