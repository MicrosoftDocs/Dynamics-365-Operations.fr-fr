---
title: Résoudre les problèmes liés aux hiérarchies de réservation de lots et de série en entrepôt
description: Cette rubrique décrit comment résoudre les problèmes courants que vous pourriez rencontrer lors de l’utilisation de hiérarchies de réservation qui utilisent des dimensions de lot ou de série.
author: perlynne
ms.date: 3/12/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application user
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 3/12/2021
ms.openlocfilehash: 1cd4883cdd95a97f821e0103da910e2c0346a08d
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2021
ms.locfileid: "6022544"
---
# <a name="troubleshoot-warehouse-batch-and-serial-reservation-hierarchies"></a>Résoudre les problèmes liés aux hiérarchies de réservation de lots et de série en entrepôt

[!include [banner](../includes/banner.md)]

Cette rubrique décrit comment résoudre les problèmes courants que vous pourriez rencontrer lors de l’utilisation de hiérarchies de réservation qui utilisent des dimensions de lot ou de série.

Pour plus d’informations, voir [Stratégie flexible de réservation de dimension au niveau de l’entrepôt](flexible-warehouse-level-dimension-reservation.md).

La hiérarchie de réservation d’un article dicte l’exigence de dimensions de stockage à respecter pour attribuer un emplacement à un ordre de demande. Ces dimensions peuvent être décrites comme *dimensions au-dessus de l’emplacement*, pour toutes les dimensions qui doivent être respectées avant l’attribution d’un emplacement, et *dimensions au-dessous de l’emplacement*, pour les dimensions qui peuvent être allouées après qu’un emplacement a été affecté à l’ordre de demande. Ces hiérarchies de réservation sont également appelées hiérarchies de réservation *batch-above* (lot au-dessus) et *batch-below* (lot au-dessous), ou *serial-above* (série au-dessus) et *serial-below* (série au-dessous).

L’inventaire ne peut être alloué avec succès que s’il n’y a pas de lacunes dans les dimensions au-dessus de l’emplacement. Par exemple, dans une hiérarchie de réservation *batch-above*, vous attendez que les dimensions **Site**, **Entrepôt** et **Numéro de lot** soient précisées sur l’ordre de demande. Si l’une de ces dimensions est manquante, le processus d’allocation échouera. En revanche, dans une hiérarchie de réservation *batch-below* ou *serial-below*, un numéro de lot ou de série peut être spécifié sur l’ordre de demande, mais le processus d’allocation ne l’exige pas.

## <a name="i-receive-the-following-error-message-to-be-assigned-to-wave-load-lines-must-specify-the-dimensions-above-the-location-to-assign-these-dimensions-reserve-and-recreate-the-load-line"></a>Je reçois le message d’erreur suivant : "Pour être affectés à la vague, les lignes de charge doivent spécifier les dimensions au-dessus de l’emplacement. Pour attribuer ces dimensions, réservez et recréez la ligne de charge. »

### <a name="issue-description"></a>Description du problème

Lorsque vous utilisez un article qui a une hiérarchie de réservation *batch-above*, la commande **Libération dans l’entrepôt** de la page **Atelier de planification des chargements** ne fonctionnera pas si vous essayez de charger une quantité partielle. Vous recevez ce message d’erreur et aucun travail n’est créé pour la quantité partielle.

Toutefois, lorsque vous utilisez un article qui a une hiérarchie de réservation *batch-below*, vous pouvez lancer une charge pour une quantité partielle à partir de la page **Atelier de planification des chargements**.

### <a name="issue-cause"></a>Cause du problème

Lorsqu’une dimension est au-dessus de la dimension **Emplacement** dans la hiérarchie de réservation, elle doit être spécifiée avant le lancement vers l’entrepôt. Les quantités partielles ne peuvent pas être libérées si une ou plusieurs dimensions au-dessus de **Emplacement** ne sont pas spécifiés.

## <a name="the-auto-reservation-prompt-for-a-batch-number-is-triggered-even-though-there-is-available-inventory"></a>L’invite de réservation automatique pour un numéro de lot est déclenchée même s’il y a un inventaire disponible.

### <a name="issue-description"></a>Description du problème

Lorsque vous utilisez un élément qui a une hiérarchie de réservation *batch-above* dans un entrepôt qui n’a pas activé les processus d’entrepôt, et que la réservation automatique est activée, l’invite de réservation automatique pour un numéro de lot s’affiche même si un seul lot est disponible pour le prélèvement.

Cependant, lorsque vous utilisez le même article dans un entrepôt où les processus d’entrepôt sont activés, l’invite de réservation automatique ne s’affiche pas.

### <a name="issue-cause"></a>Cause du problème

Si une hiérarchie de réservation est définie comme *batch-above* ou *serial-above*, la dimension référencée (**Numéro de lot** ou **Numéro de série**) doit toujours être spécifié sur les ordres de demande. Les processus d’entrepôt peuvent être en mesure de compléter les informations si un seul lot ou numéro de série est disponible. Cependant, comme l’entrepôt n’est pas activé pour les processus d’entrepôt, l’utilisateur doit toujours spécifier toutes les dimensions au-dessus de **Emplacement**.

## <a name="slotting-templates-that-have-the-consider-on-hand-slot-criterion-dont-consider-current-on-hand-inventory-for-batch-enabled-items"></a>Les modèles de positionnement qui ont le critère d’emplacement Considérer comme disponible ne prennent pas en compte le stock disponible actuel pour les articles activés pour les lots.

Pour plus d’informations, voir [Créneaux de l’entrepôt](warehouse-slotting.md).

### <a name="issue-description"></a>Description du problème

Les modèles de positionnement qui ont le critère d’emplacement *Considérer comme disponible* ne prennent pas en compte le stock disponible actuel pour les articles *batch-above*. Ils ne le prennent en compte que si le numéro de lot est indiqué sur la ligne de commande client.

Cependant, lorsque vous utilisez des articles *batch-below*, l’inventaire disponible actuel est considéré comme attendu.

### <a name="issue-cause"></a>Cause du problème

L’en-tête du modèle de positionnement peut être défini pour les stratégies de demande *Commandé*, *Réservé*, ou *Libéré*. Pour la stratégie de demande *Commandé*, les mêmes exigences de hiérarchie de réservation s’appliquent que celles qui s’appliquent aux processus de réservation ou de lancement vers l’entrepôt. Par conséquent, pour les articles qui ont des hiérarchies de réservation *batch-above* et *serial-below*, le numéro de lot ou de série doit être indiqué sur l’ordre de demande (vente ou transfert). Alternativement, la stratégie de demande *Réservé* peut être utilisée pour sélectionner le numéro de lot ou de série avant que la demande de positionnement d’entrepôt ne soit générée.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
