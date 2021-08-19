---
title: Les commandes confirmées directement dérivées sont traitées par un flux de travail en révision
description: Les commandes confirmées directement dérivées sont traitées par un flux de travail avec le statut En révision.
author: ChristianRytt
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: ReqTransPo
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: ilebedev
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: d20f1c1d6e8fc83dd996b04bf0321a41f7b39290f306d1ac9f4fcd17514832e6
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6721173"
---
# <a name="directly-derived-firmed-orders-are-processed-by-an-in-review-workflow"></a>Les commandes confirmées directement dérivées sont traitées par un flux de travail en révision

Numéro de la base de connaissances : 4612450

## <a name="symptoms"></a>Symptômes

Les commandes confirmées directement dérivées sont traitées par un flux de travail avec le statut *En révision*.

## <a name="resolution"></a>Résolution

Lorsque le suivi des modifications est activé, le statut *En révision* est attribué aux commandes dérivées confirmées (commandes d'achat de sous-traitance). Par conséquent, si une commande fournisseur est dérivée (une commande fournisseur de sous-traitance), elle est uniquement soumise à un workflow. Si une commande d'achat est une commande d'achat planifiée confirmée, elle est automatiquement approuvée pour garantir que le moteur de planification ne crée pas de nouvelles commandes planifiées tant que la commande d'achat est toujours en cours avec le statut *Brouillon*.
