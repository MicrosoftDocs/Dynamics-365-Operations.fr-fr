---
title: La quantité ne peut pas être réduite lorsqu’une commande client est annulée
description: La quantité ne peut pas être réduite lorsqu’une commande client est annulée.
author: hja-ms
ms.date: 5/17/2021
ms.topic: troubleshooting
ms.search.form: SalesTable_SalesCancelOrder, SalesTableListPage_SalesCancelOrder
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: hja
ms.search.validFrom: 2021-05-17
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 1a2cc9c9fd3d085508fc652bc9ee0a352d869dee
ms.sourcegitcommit: a02d3d64c899f8554b74342d5a1856d824bf1abe
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/11/2021
ms.locfileid: "6230834"
---
# <a name="the-quantity-cant-be-reduced-when-a-sales-order-is-canceled"></a>La quantité ne peut pas être réduite lorsqu’une commande client est annulée

Code d’erreur : SYS138831

## <a name="symptoms"></a>Symptômes

Le système affiche le message d’erreur suivant :

> La quantité ne peut pas être réduite. Le nombre de mouvements de stock sur la commande est trop faible car la quantité ou une partie de celle-ci est référencée par un ordre de sortie ou un ordre de fabrication ou est marquée par rapport à d’autres transactions.

## <a name="cause"></a>Cause

Si le travail est associé à une commande client, vous ne pouvez pas annuler la commande client tant que le travail n’est pas annulé et contrepassé. Cette exigence s’applique même si le travail associé à la commande client est clôturé.

## <a name="resolution"></a>Résolution

Pour résoudre ce problème, effectuez les tâches suivantes :

1. Annulez le travail ouvert.
1. Supprimez le chargement.
1. Réduisez la quantité prélevée.

### <a name="cancel-open-work"></a>Annuler le travail ouvert

Pour annuler le travail ouvert, procédez comme suit :

1. Allez dans **Gestion des entrepôts \> Tâches périodiques \> Nettoyer \> Annuler le travail**.
1. Dans le champ **ID de travail**, spécifiez l’ID de travail que vous souhaitez annuler et dont le **Statut de travail** est actuellement *Ouvert*, *En cours*, *Annulé*, *Combiné* ou *Fermé*.
1. Cliquez sur **OK**.
1. Sélectionnez **Oui** pour confirmer que vous souhaitez annuler le travail.

### <a name="delete-the-load"></a>Supprimer le chargement

Pour supprimer un chargement, procédez comme suit.

1. Accédez à **Ventes et marketing \> Commandes client \> Toutes les commandes client**.
1. Ouvrez les commandes clients concernées.
1. Dans le raccourci **Lignes de commande client**, sélectionnez **Entrepôt \> Détails du travail**.
1. Sur la page **Travail**, dans le volet Actions, sur l’onglet **Travail**, dans le groupe **Travail**, sélectionnez **Annuler le travail**.
1. Confirmez que le champ **Statut du travail** est défini sur *Annulé*.
1. Fermez la page **Travail**.
1. Sur la page des détails de la commande client, dans le raccourci **Lignes de commande client**, sélectionnez **Entrepôt \> Détails du chargement**.
1. Dans le volet Actions, sélectionnez **Supprimer**.
1. Sélectionnez **Oui** pour confirmer que vous souhaitez supprimer le chargement.
1. Fermez la page **Chargement**.

### <a name="reduce-the-picked-quantity"></a>Réduire la quantité prélevée

Une fois tous les travaux annulés, suivez ces étapes pour réduire la quantité prélevée.

1. Accédez à **Ventes et marketing \> Commandes client \> Toutes les commandes client**.
1. Ouvrez les commandes clients concernées.
1. Dans le raccourci **Lignes de commande client**, sélectionnez **Mettre à jour la ligne \> Prélever** dans la barre d’outils.
1. Sur la page **Prélever**, dans la section **Transactions**, sélectionnez la ligne où le champ **Statut de sortie** est défini sur *Prélevé*.
1. Dans la section **Transactions**, sélectionnez **Ajouter une ligne de prélèvement** dans la barre d’outils.
1. Dans la section **Lignes de prélèvement**, sélectionnez **Confirmer Prélever tout** dans la barre d’outils.
1. Fermez la page **Prélèvement**.
1. Dans la page des détails de la commande, dans le volet Actions, sous l’onglet **Commande client**, dans le groupe **Tenir à jour**, sélectionnez **Annuler**.
1. Sélectionnez **Oui** pour confirmer que vous souhaitez annuler la commande client.
