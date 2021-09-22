---
title: Impossible de libérer la charge pour une quantité partielle avec une hiérarchie de type « batch-above » (lot au-dessus)
description: Lors de l’utilisation d’un article avec la hiérarchie de réservation de type « batch-above » (lot au-dessus), les lignes de charge doivent spécifier des dimensions au-dessus de l’emplacement pour que le stock soit alloué.
author: perlynne
ms.date: 06/24/2021
ms.topic: troubleshooting
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: eb7e71cc271903cb689c33777b72862246f2dd42
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/07/2021
ms.locfileid: "7476311"
---
# <a name="cant-release-a-load-for-partial-quantity-with-batch-above-reservation-hierarchy"></a>Impossible de libérer une charge pour une quantité partielle avec une hiérarchie de réservation de type « batch-above » (lot au-dessus)

## <a name="symptoms"></a>Symptômes

Lorsque vous utilisez un article qui a une hiérarchie de réservation *batch-above*, la commande **Libération dans l’entrepôt** de la page **Atelier de planification des chargements** ne fonctionnera pas si vous essayez de charger une quantité partielle. Vous recevez le message d’erreur suivant :

> Pour être affectées à la vague, les lignes de charge doivent spécifier les dimensions au-dessus de l’emplacement. Pour attribuer ces dimensions, réservez et recréez la ligne de charge.

Toutefois, lorsque vous utilisez un article qui a une hiérarchie de réservation *batch-below*, vous pouvez lancer une charge pour une quantité partielle à partir de la page **Atelier de planification des chargements**.

## <a name="cause"></a>Cause

Lorsqu’une dimension est au-dessus de la dimension **Emplacement** dans la hiérarchie de réservation, elle doit être spécifiée avant le lancement vers l’entrepôt. L’inventaire ne peut être alloué avec succès que s’il n’y a pas de lacunes dans les dimensions au-dessus de l’emplacement.

## <a name="resolution"></a>Résolution

Assurez-vous que toutes les dimensions au-dessus de **Emplacement** ont été attribués en réservant et en recréant la ligne de charge.
