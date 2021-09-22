---
title: Les travaux en cours se terminent lors du rapport de la quantité partielle sur le dernier travail
description: Lors de l'utilisation du périphérique de bon de travail pour signaler une quantité partielle sur le dernier travail d’un ordre de fabrication, tous les travaux précédents de cet ordre qui ont un statut En cours sont automatiquement terminés.
author: SmithaNataraj
ms.date: 06/24/2021
ms.topic: troubleshooting
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: smnatara
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 11511d4ac7524facdd0d647e9bc38fe09c282be1
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/07/2021
ms.locfileid: "7476378"
---
# <a name="previous-in-progress-jobs-are-ended-when-reporting-partial-quantity-on-last-job"></a>Les travaux en cours précédents sont arrêtés lors du rapport de la quantité partielle sur le dernier travail

## <a name="symptoms"></a>Symptômes

Lors de l'utilisation du périphérique de bon de travail pour signaler une quantité partielle sur le dernier travail d’un ordre de fabrication, tous les travaux précédents de cet ordre qui ont un statut En cours sont automatiquement terminés.

## <a name="resolution"></a>Résolution

Ce comportement est fait exprès. Sur la page **Valeurs par défaut de l’ordre de fabrication**, sur l’onglet **Signaler comme terminé**, il existe une option nommée **Déclarer la gamme finie**. Si cette rubrique est définie sur *Oui*, un journal de fiches production est publié lorsqu’un collaborateur utilise le périphérique des bons de travail ou le terminal de bons de travail pour signaler la dernière opération. Ce journal marque toutes les opérations comme terminées et met fin à tous les travaux de production. Quand l’option **Déclarer la gamme finie** est définie sur *Oui*, le système ne prend pas en compte le statut du travail que le collaborateur a sélectionné lorsqu’il a signalé la dernière opération. Le système ne considère pas non plus si le collaborateur déclare une quantité totale ou partielle.
