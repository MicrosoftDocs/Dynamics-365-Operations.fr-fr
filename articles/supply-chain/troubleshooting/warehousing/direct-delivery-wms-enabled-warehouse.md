---
title: Livraison directe impossible à traiter pour un entrepôt activé pour la WMS
description: Si la WMS est activée dans l'entrepôt, celui-ci ne prend pas en charge la livraison directe. Pour utiliser la livraison directe, vous devez sélectionner un article et un entrepôt non liés à la WMS.
author: perlynne
ms.date: 06/24/2021
ms.topic: troubleshooting
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 090e17091e9fb92c2065679bb9b04637214e2eea
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/07/2021
ms.locfileid: "7476388"
---
# <a name="direct-delivery-not-able-to-process-for-wms-enabled-warehouse"></a>Livraison directe impossible à traiter pour un entrepôt activé pour la WMS

## <a name="symptoms"></a>Symptômes

Si un article est ajouté à une ligne de vente pour une livraison directe à partir d'un entrepôt activé pour la gestion d'entrepôt (WMS), vous recevez le message d'erreur suivant lorsque la ligne de vente est mise à jour :

> La livraison directe ne peut pas être traitée pour l’entrepôt 1% car la gestion d’entrepôt est activée. Spécifiez un autre entrepôt qui n’est pas activé pour la gestion d’entrepôt.

## <a name="resolution"></a>Résolution

Microsoft a évalué ce problème et a déterminé qu’il s’agissait d’une limitation de fonctionnalité. Actuellement, WMS ne prend pas en charge la livraison directe. Par conséquent, pour utiliser la livraison directe, vous devez sélectionner un article et un entrepôt non WMS.
