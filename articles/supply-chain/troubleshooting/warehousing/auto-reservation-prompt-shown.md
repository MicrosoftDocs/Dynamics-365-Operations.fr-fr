---
title: L'invite de réservation automatique s'affiche avec le stock disponible
description: Lorsque vous utilisez un article dans un entrepôt où les processus d’entrepôt ne sont pas activés, l’invite de réservation automatique s’affiche. Spécifiez toutes les dimensions au-dessus de Emplacement.
author: perlynne
ms.date: 06/24/2021
ms.topic: troubleshooting
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: a15502ce8c5bc61d37cedd746985176408a2f362
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/07/2021
ms.locfileid: "7476373"
---
# <a name="auto-reservation-prompt-for-batch-number-is-shown-even-with-available-inventory"></a>L'invite de réservation automatique pour les numéros de lot s'affiche même avec le stock disponible

## <a name="symptoms"></a>Symptômes

Lorsque vous utilisez un élément qui a une hiérarchie de réservation *batch-above* dans un entrepôt qui n’a pas activé les processus d’entrepôt, et que la réservation automatique est activée, l’invite de réservation automatique pour un numéro de lot s’affiche même si un seul lot est disponible pour le prélèvement.

Cependant, lorsque vous utilisez le même article dans un entrepôt où les processus d’entrepôt sont activés, l’invite de réservation automatique ne s’affiche pas.

## <a name="resolution"></a>Résolution

Si une hiérarchie de réservation est définie comme *batch-above* ou *serial-above*, la dimension référencée (**Numéro de lot** ou **Numéro de série**) doit toujours être spécifié sur les ordres de demande. Les processus d’entrepôt peuvent être en mesure de compléter les informations si un seul lot ou numéro de série est disponible. Cependant, comme l’entrepôt n’est pas activé pour les processus d’entrepôt, l’utilisateur doit toujours spécifier toutes les dimensions au-dessus de **Emplacement**.
