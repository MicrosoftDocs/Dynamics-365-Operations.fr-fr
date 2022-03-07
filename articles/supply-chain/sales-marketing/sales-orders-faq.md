---
title: Foire aux questions sur les commandes clients
description: Cette page répond aux questions fréquemment posées lors de l’utilisation des commandes client dans Dynamics 365 Supply Chain Management.
author: SmithaNataraj
ms.date: 06/24/2021
ms.topic: troubleshooting
ms.search.form: SalesTable, SalesTableListPage, SalesTableListPage_SalesCancelOrder
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: smnatara
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: d75022dcc476052040b16c9033cf5ff2a697ae6c
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/07/2021
ms.locfileid: "7476327"
---
# <a name="sales-order-faqs"></a>FAQ Commande client

Cette page répond aux questions fréquemment posées lors de l’utilisation des commandes client dans Dynamics 365 Supply Chain Management.

## <a name="can-i-link-a-purchase-order-to-a-sales-order-to-fulfill-demand"></a>Puis-je lier une commande fournisseur à une commande client pour répondre à la demande ?

Vous pouvez créer une commande fournisseur à partir d’une commande client. Pour plus d’informations, voir [Créer une commande fournisseur à partir d’une commande client](/dynamics365/supply-chain/sales-marketing/tasks/create-purchase-order-sales-order).

## <a name="can-i-cancel-or-delete-a-sales-order-or-return-order"></a>Puis-je annuler ou supprimer une commande client ou un ordre de retour ?

Vous ne pouvez annuler que les commandes client et les ordres de retour qui se trouvent dans l’état *Créé*. Pour plus d’informations, voir [Annuler un ordre de retour](/dynamics365/supply-chain/service-management/cancel-return-order).

## <a name="can-i-restore-an-invoiced-sales-order-that-was-deleted"></a>Puis-je restaurer une commande client facturée qui a été supprimée ?

Si une commande client facturée a été supprimée par erreur, vous pouvez la restaurer ou en afficher les détails.

Accédez à **Compte client \> Transactions \> Document d’origine \> Afficher les détails**. Recherchez la facture que vous recherchez et sélectionnez-la pour afficher ses détails. Ces détails incluent la référence de la commande client. Vous devriez également pouvoir accéder aux détails de la commande client à partir de cette page.

## <a name="how-do-i-delete-orphaned-sales-order-records"></a>Comment puis-je supprimer les enregistrements de commande client orphelins ?

Pour nettoyer les enregistrements de commande client orphelins, exécutez la tâche périodique *Suppression de commandes client* en accédant à l’un des emplacements suivants :

- Ventes et marketing \> Tâches périodiques \> Nettoyage \> Supprimer des commandes clients
- Retail et Commerce \> IT Retail et Commerce \> Nettoyage \> Supprimer des commandes client

## <a name="is-there-a-way-to-calculate-commissions-on-invoices-that-have-already-been-posted"></a>Existe-t-il un moyen de calculer les commissions sur les factures déjà validées ?

Supply Chain Management ne prend actuellement pas en charge le calcul des commissions pour les factures validées.
