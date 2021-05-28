---
title: Le champ Date du dernier test n'est pas mis à jour lorsque plusieurs commandes de qualité sont créées
description: Le champ Date du dernier test n'est pas mis à jour lorsque plusieurs commandes de qualité sont créées.
author: niwang
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: InventBatch
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: smnatara
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: 6f796bdaa88d32b1c58dd8a4bca19f0ce4f3943d
ms.sourcegitcommit: c011a2ef66b38e71ddaf003f7d243677bb2707c5
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/12/2021
ms.locfileid: "6026518"
---
# <a name="the-last-tested-date-field-isnt-updated-when-multiple-quality-orders-are-created"></a>Le champ Date du dernier test n'est pas mis à jour lorsque plusieurs commandes de qualité sont créées

Numéro de la base de connaissances : 4612803

## <a name="symptoms"></a>Symptômes

Le champ **Date du dernier test** n'est pas mis à jour lorsque plusieurs commandes de qualité sont créées.

## <a name="resolution"></a>Résolution

Le système se comporte comme prévu. La dernière date testée n'est pas liée aux commandes de qualité. Il stocke la date à laquelle les produits finis ont été achetés ou fabriqués pour la première fois. Cette date est utilisée pour calculer la date d'avis de durée de conservation.
