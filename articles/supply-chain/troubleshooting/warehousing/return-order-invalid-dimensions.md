---
title: Impossible de créer une ligne de charge en raison de dimensions d’inventaire non valides
description: Lorsque vous essayez de libérer une commande client de retour vers l’entrepôt, vous pouvez recevoir une erreur concernant des dimensions de stock non valides. Retirez-les de la ligne de commande.
author: perlynne
ms.date: 06/24/2021
ms.topic: troubleshooting
audience: Application User
ms.reviewer: kamaybac58
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 3cb728f6a989cdac63c91d49baaea094bace59e4
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/07/2021
ms.locfileid: "7476352"
---
# <a name="cant-create-load-line-for-return-sales-order-due-to-invalid-inventory-dimensions"></a>Impossible de créer une ligne de charge pour la commande client de retour en raison de dimensions d’inventaire non valides

## <a name="symptoms"></a>Symptômes

Le message d’erreur suivant est susceptible de s’afficher lorsque vous essayez de lancer une commande client de retour vers l’entrepôt :

> Vous ne pouvez pas créer une ligne de chargement pour cette ligne de commande car elle contient des dimensions de stock qui ne sont pas valides. Vous ne pouvez pas référencer les dimensions de stock situées sous la dimension d’emplacement dans la hiérarchie de réservation. Supprimez les dimensions non valides de la ligne de commande.

## <a name="resolution"></a>Résolution

Malheureusement, le produit ne prend pas en charge le traitement de la charge pour un processus de retour des ventes. Par conséquent, vous ne pouvez pas valider le retour de la commande client à l’entrepôt.

Sur les transactions de commande client, vous ne pouvez pas référencer les dimensions de stock situées sous la dimension d’**emplacement** dans la hiérarchie de réservation. La résolution consiste à supprimer les dimensions non valides de la ligne de commande.
