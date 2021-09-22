---
title: L'emplacement de la dimension ne peut pas être vide si le numéro de série est défini
description: Si vous recevez cette erreur lors de la confirmation d'une expédition après avoir créé un ordre de transfert pour un article en série, le champ Emplacement de réception par défaut est vide.
author: perlynne
ms.date: 06/24/2021
ms.topic: troubleshooting
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 6f58c72438d5d1d93e59e46525debd65d44d9a76
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/07/2021
ms.locfileid: "7476372"
---
# <a name="error-when-confirming-shipment-after-creating-a-transfer-order-for-a-serial-item"></a>Erreur lors de la confirmation de l'expédition après la création d'un ordre de transfert pour un article en série

## <a name="symptoms"></a>Symptômes

Si vous créez un ordre de transfert pour un article de série à l’aide d’un entrepôt activé pour la gestion avancée des entrepôts (WMS), puis qu'une fois le travail terminé, vous essayez de confirmer l’expédition, vous recevez le message d'erreur suivant :

> L'emplacement de la dimension ne peut pas être laissé vide si le numéro de série de dimension est défini.

## <a name="cause"></a>Cause

Cela se produit parce que le champ **Emplacement de réception par défaut** est vierge pour un entrepôt de transit de l’entrepôt « Expéditeur ».

## <a name="resolution"></a>Résolution

Pour résoudre ce problème, spécifiez un emplacement de réception par défaut dans l’entrepôt de transit. Assurez-vous que cet emplacement est contrôlé par contenant.
