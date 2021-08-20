---
title: Le numéro de lot est effacé lorsqu'un nouvel ID de lot est sélectionné
description: Lorsque vous consultez une ligne de journal de liste de prélèvement, la valeur du champ Numéro de lot est effacée si vous sélectionnez une nouvelle valeur dans le champ ID de lot.
author: johanhoffmann
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: ProdJournalTransBOM
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: datra
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: 6d71720b1d3a34a31639db0f829dee300d6f96d53fd61c0a8740be9f2306d6dd
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6738817"
---
# <a name="batch-number-is-cleared-when-a-new-lot-id-is-selected"></a>Le numéro de lot est effacé lorsqu'un nouvel ID de lot est sélectionné

Numéro de la base de connaissances : 4613107

## <a name="symptoms"></a>Symptômes

Lorsque vous consultez une ligne de journal de liste de prélèvement, la valeur du champ **Numéro de lot** est effacée si vous sélectionnez une nouvelle valeur dans le champ **ID de lot**.

## <a name="resolution"></a>Résolution

Le système se comporte comme prévu. Si vous modifiez l'ID de lot, vous modifiez le contexte de l'article. Par conséquent, le numéro de lot est réinitialisé.

Pour associer le numéro de lot à un ID de lot, vous devez d'abord définir l'ID de lot.
