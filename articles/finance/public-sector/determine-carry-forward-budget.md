---
title: Mettre à jour le report de budget après réductions des bons de commande et des factures
description: Cet article décrit comment contrôler ce qu’il advient du report de budget lorsque les bons de commande sont annulés ou réduits, et lorsque les factures sont réduites.
author: TaylorVH
ms.date: ''
ms.topic: article
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: v-savanh
ms.search.validFrom: 2022-02-01
ms.dyn365.ops.version: Version 1611
ms.search.form: LedgerFund
ms.openlocfilehash: f51839b6890e39a2f2c5867977f3935ab43e2c5d
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/12/2022
ms.locfileid: "9280527"
---
# <a name="update-the-carry-forward-budget-after-reductions-in-purchase-orders-and-invoices"></a>Mettre à jour le report de budget après réductions des bons de commande et des factures

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

Cet article décrit comment contrôler ce qu’il advient du report de budget lorsque les bons de commande sont annulés ou réduits, et lorsque les factures sont réduites.

Pour plus d’informations sur la façon dont les bons de commande sont traités à la fin de l’exercice, voir [Traiter les bons de commande à la fin de l’exercice](/dynamicsax-2012/appuser-itpro/process-purchase-orders-at-year-end).

## <a name="turn-carry-forward-budget-reductions-for-invoice-variances-on-or-off"></a>Activer ou désactiver les réductions de report de budget pour les écarts de facture

Le système peut toujours mettre à jour le report de budget lorsqu’une commande fournisseur est annulée ou réduite. Toutefois, si vous souhaitez mettre à jour le report de budget lorsqu’une facture est réduite, vous devez activer la fonctionnalité *Réduire le report de budget lorsqu’une facture par rapport à une commande fournisseur est réduite avec un écart*. Les administrateurs peuvent activer ou désactiver cette fonctionnalité en la recherchant dans l’espace de travail **[Gestion des fonctions](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md)**.

## <a name="purchase-order-reductions-and-cancellations"></a>Réductions et annulations de bons de commande

Que la fonctionnalité *Réduire le report de budget lorsqu’une facture par rapport à une commande fournisseur est réduite avec un écart* soit activée ou non, le report de budget est toujours mis à jour lorsqu’un bon de commande éligible est annulé ou réduit. Vous pouvez paramétrer chaque fonds en comptabilité pour qu’il réponde de l’une des manières suivantes :

- Conserver le report de budget tel qu’il a été créé.
- Ajuster automatiquement le report de budget pour supprimer le montant annulé ou réduit.

Seules les lignes de commande fournisseur dont les distributions incluent un fonds sont disponibles pour l’ajustement automatique du budget. L’ajustement automatique du budget se produit lorsque le bon de commande est finalisé ou qu’une réduction de bon de commande est confirmée.

## <a name="invoice-reductions"></a>Réductions de facture

Lorsque la fonctionnalité *Réduire le report de budget lorsqu’une facture par rapport à une commande fournisseur est réduite avec un écart* est activée, vous pouvez spécifier si chaque fonds doit réduire ou non le report de budget lorsqu’une facture est réduite, lorsqu’une commande fournisseur reportée est annulée ou réduite. La facture doit concerner un bon de commande dont le budget est reporté. Parmi les réductions figurent les écarts de prix, les écarts de frais et les écarts de taxe. Lorsqu’une commande fournisseur reportée est réduite lors de la facturation, un écart est créé. Lorsque la facture est validée, l’engagement de la commande fournisseur sera réduit du montant de l’écart. La fonctionnalité créera également l’ajustement budgétaire automatique pour le montant de l’écart.

Lorsque la fonctionnalité *Réduire le report de budget lorsqu’une facture par rapport à une commande fournisseur est réduite avec un écart* est désactivée, le report de budget n’est pas réduit dans ce scénario. Par conséquent, le report de budget restant pour le montant de l’écart est laissé de côté.

## <a name="configure-the-carry-forward-budget-options-for-each-fund"></a>Configurer les options de report de budget pour chaque fonds

Suivez ces étapes pour chaque fonds en comptabilité qui devrait pouvoir réduire le report de budget lorsqu’un bon de commande est réduit ou une facture est réduite.

1. Accédez à **Comptabilité \> Plan comptable \> Fonds \> Fonds**.
1. Sélectionnez le fonds que vous souhaitez configurer.
1. Sous **Processus de fin d’exercice de commande fournisseur**, assurez-vous que l’option **Ignorer l’option de fin d’exercice sélectionnée** est définie sur *Oui*.
1. Sous **Statut du report de budget**, définissez le champ **Rétablir le budget lorsqu’une commande fournisseur reportée est annulée ou réduite** selon vos besoins. Les paramètres ont des effets légèrement différents, selon que la fonctionnalité *Réduire le report de budget lorsqu’une facture par rapport à une commande fournisseur est réduite avec un écart* est activée ou non dans votre système.

    - Lorsque la fonctionnalité est désactivée, le système ne réagit qu’aux bons de commande annulés ou réduits. Les paramètres d’option fonctionnent de la manière suivante :

        - *Non* : Le système crée une écriture de registre budgétaire pour le solde restant des bons de commande qui ont été annulés ou réduits.
        - *Oui* : Le système permet d’annuler ou de réduire les bons de commande, mais ne crée pas d’écriture de registre budgétaire. Le budget reporté reste disponible pour être consommé par d’autres pièces.

    - Lorsque la fonctionnalité est activée, le système réagit à la fois aux écarts de facture et aux bons de commande annulés ou réduits. Les paramètres d’option fonctionnent de la manière suivante :

        - *Non* : Pour les écarts de facture, le système crée une écriture de registre budgétaire sur le bon de commande pour le montant de réduction de l’écart. Pour les bons de commande annulés ou réduits, ce paramètre a le même effet que lorsque la fonctionnalité est désactivée.
        - *Oui* : Pour les écarts de facture, le système autorise la réduction de facture mais ne crée pas d’écriture de registre budgétaire. Le budget reporté reste disponible pour être consommé par d’autres pièces. Pour les bons de commande annulés ou réduits, ce paramètre a le même effet que lorsque la fonctionnalité est désactivée.

## <a name="additional-resources"></a>Ressources supplémentaires

- [Traitement des commandes fournisseur en fin d’exercice](/dynamicsax-2012/appuser-itpro/process-purchase-orders-at-year-end)
- [Tenir à jour les réservations budgétaires générales](general-budget-reservation-tasks.md)
- [Fonds dans le secteur public](funds-public-sector.md)
- [Paramétrer un fonds dans le secteur public](tasks/set-up-fund-public-sector.md)
