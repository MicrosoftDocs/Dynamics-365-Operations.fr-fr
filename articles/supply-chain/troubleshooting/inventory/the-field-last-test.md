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
ms.openlocfilehash: 46523c55f4fd42b0985397752f0c62a3e1a55e177f2308e20b7064e339758269
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6742026"
---
# <a name="the-last-tested-date-field-isnt-updated-when-multiple-quality-orders-are-created"></a>Le champ Date du dernier test n'est pas mis à jour lorsque plusieurs commandes de qualité sont créées

Numéro de la base de connaissances : 4612803

## <a name="symptoms"></a>Symptômes

Le champ **Date du dernier test** n'est pas mis à jour lorsque plusieurs commandes de qualité sont créées.

## <a name="resolution"></a>Résolution

Le système se comporte comme prévu. La dernière date testée n'est pas liée aux commandes de qualité. Il stocke la date à laquelle les produits finis ont été achetés ou fabriqués pour la première fois. Cette date est utilisée pour calculer la date d'avis de durée de conservation.
