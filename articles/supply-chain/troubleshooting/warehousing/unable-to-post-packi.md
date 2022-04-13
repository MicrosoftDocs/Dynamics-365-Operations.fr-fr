---
title: Impossible de valider le bon de livraison pour une ligne de commande client arrêtée
description: Vous ne parvenez pas à valider le bon de livraison pour une ligne de commande client arrêtée
author: smithanataraj
ms.date: 03/07/2022
ms.topic: article
ms.search.form: WHSLoadTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mfp
ms.search.validFrom: 2022-03-07
ms.dyn365.ops.version: 10.0.26
ms.openlocfilehash: 115cfe79e075eb36f73203818acdbb5e31fc0bad
ms.sourcegitcommit: c0f7ee7f8837fec881e97b2a3f12e7f63cf96882
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/22/2022
ms.locfileid: "8462850"
---
# <a name="cant-post-packing-slip-for-a-stopped-a-sales-order-line"></a>Impossible de valider le bon de livraison pour une ligne de commande client arrêtée

Code d’erreur : SYS13203

## <a name="symptoms"></a>Symptômes

Lorsque vous essayez de valider un bon de livraison pour un chargement, le système affiche le message d’erreur suivant :

> Impossible de valider le bon de livraison lors de l’arrêt d’une ligne de commande client après confirmation de l’expédition sortante. Une quantité ne peut pas être prélevée.

## <a name="cause"></a>Cause

Une ou plusieurs des lignes de commande client associées peuvent être arrêtées, ce qui signifie que le système empêchera la poursuite du traitement de cette commande client. Entre autres choses, cela signifie que le système ne validera pas de bon de livraison pour la commande.

Par exemple, un utilisateur peut avoir décidé d’arrêter une ou plusieurs lignes de commande parce que le client a rappelé et annulé sa commande. Cependant, si l’expédition sortante avait déjà été confirmée, l’expédition contenant la commande client aurait déjà physiquement quitté l’entrepôt, ce qui signifie que l’arrêt des lignes de commande client n’aurait aucun effet. Puisqu’il n’est plus possible d’arrêter physiquement l’expédition, vous pouvez également débloquer les lignes afin de pouvoir valider le bon de livraison. Vous devrez alors traiter la commande annulée comme un retour.

## <a name="resolution"></a>Résolution

Pour pouvoir valider le bon de livraison, assurez-vous qu’aucune des lignes de commande client concernées n’est arrêtée en procédant comme suit.

1. Accédez à **Toutes les commandes client \> Ventes et marketing \> Toutes les commandes client**.
1. Recherchez et ouvrez la commande client qui vous pose problème.
1. Dans le raccourci **Lignes de commande client**, sélectionnez une ligne de commande client.
1. Sur le raccourci **Détails de la ligne**, ouvrez l’onglet **Général** et assurez-vous que le champ **Arrêté** est défini sur *Non*.
1. Continuez à travailler jusqu’à ce que toutes les lignes de vente concernées ne soient plus arrêtées.
1. Réessayez de valider le bon de livraison pour le chargement ou la commande client.
