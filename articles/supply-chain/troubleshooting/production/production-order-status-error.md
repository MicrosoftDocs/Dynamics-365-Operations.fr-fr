---
title: Erreur lors du changement de statut de Déclaré terminé à Fin
description: Vous pouvez recevoir une erreur lorsque vous modifiez le statut d'un ordre de fabrication de Déclaré terminé en Fin. Cette page explique comment atténuer le problème.
author: SmithaNataraj
ms.date: 06/24/2021
ms.topic: troubleshooting
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: smnatara
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 744637f5cccffe44b85f77c1a9df2034012fac40
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/07/2021
ms.locfileid: "7476342"
---
# <a name="error-when-changing-status-of-production-order-from-reported-as-finished-to-end"></a>Erreur lors du changement de statut d'un ordre de fabrication de Déclaré terminé à Fin

## <a name="symptoms"></a>Symptômes

Lorsque le statut d’un ordre de fabrication passe de Déclaré terminé à Fin, vous recevez l'un des messages d’erreur suivants :

> Conflit de mise à jour. Le coût standard ne correspond pas à la valeur de stock financière après la mise à jour.

> Une erreur critique s’est produite dans la fonction InventCostMovement.checkVariance.

## <a name="cause"></a>Cause

Ce problème se produit car les données sous-jacentes ont été modifiées par un autre processus. Le processus essaiera de mettre à jour les données jusqu’à cinq fois. Si le conflit persiste après cinq tentatives, vous recevrez l'un des messages d’erreur répertoriés ci-dessus.

## <a name="resolution"></a>Résolution

Ce comportement est fait exprès. Pour corriger le problème, reprenez le traitement par lots. Il devrait finir de s’exécuter.

Si le traitement par lots échoue systématiquement après sa reprise, vérifiez que la précision d’arrondi de la devise par défaut de la comptabilité est conforme à l’arrondi appliqué aux valeurs de la table InventSum. Si la précision d’arrondi a été remplacée par une valeur non conforme, vous devrez probablement la remettre à une valeur conforme. Recherchez **ModifiedDateTime**. Dans ce cas, la valeur indiquera généralement que la précision d’arrondi a été récemment modifiée.
