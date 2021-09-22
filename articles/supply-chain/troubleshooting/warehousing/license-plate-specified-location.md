---
title: Un contenant doit être spécifié pour cet emplacement
description: Si vous recevez cette erreur après avoir créé un ordre de transfert pour un entrepôt où la WMS est activée, l'emplacement de réception par défaut est vierge pour un entrepôt de transit.
author: perlynne
ms.date: 06/24/2021
ms.topic: troubleshooting
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 2e562ad2b41dd149f215adc83bd2d54e55dccc05
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/07/2021
ms.locfileid: "7476303"
---
# <a name="license-plate-specification-error-when-confirming-shipment-for-a-transfer-order"></a>Erreur de spécification de contenant lors de la confirmation de l'expédition pour un ordre de transfert

## <a name="symptoms"></a>Symptômes

Si vous créez un ordre de transfert à l’aide d’un entrepôt qui n’est pas activé pour la gestion avancée des entrepôts (WMS), puis, que vous essayez de confirmer l’expédition une fois le travail terminé, vous pouvez recevoir le message d'erreur suivant :

> Un contenant doit être spécifié pour cet emplacement.

## <a name="cause"></a>Cause

Cela se produit parce que le champ **Emplacement de réception par défaut** est vierge pour un entrepôt de transit de l’entrepôt « Expéditeur ».

## <a name="resolution"></a>Résolution

Pour résoudre ce problème, spécifiez un emplacement de réception par défaut dans l’entrepôt de transit. Assurez-vous que cet emplacement est contrôlé par contenant.
