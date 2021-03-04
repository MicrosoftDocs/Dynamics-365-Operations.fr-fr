---
title: Résoudre les problèmes liés aux commandes client
description: Cette rubrique décrit comment résoudre les problèmes que vous pourriez rencontrer lors de l'utilisation des commandes client.
author: SmithaNataraj
manager: tfehr
ms.date: 09/16/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SalesTable, SalesTableListPage
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: smnatara
ms.search.validFrom: 2020-9-16
ms.dyn365.ops.version: Release 10.0.14
ms.openlocfilehash: 6e51723915892f465ce09d09ee9ed622bab9451e
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4427845"
---
# <a name="troubleshoot-sales-orders"></a>Résoudre les problèmes liés aux commandes client

Cette rubrique décrit comment résoudre les problèmes que vous pourriez rencontrer lors de l'utilisation des commandes client.

## <a name="the-tax-information-isnt-updated-if-i-change-the-location-on-a-sales-order-header"></a>Les informations fiscales ne sont pas mises à jour si je modifie l'emplacement sur un en-tête de commande client.

### <a name="issue-description"></a>Description du problème

Si le site, l'entrepôt ou l'adresse de livraison est modifiée sur un en-tête de commande client ou au niveau de la ligne, les informations fiscales concernées ne sont pas automatiquement mises à jour pour les lignes.

### <a name="issue-resolution"></a>Résolution du problème

Ce comportement est fait exprès. Le problème se produit car l'adresse de livraison, le site et l'entrepôt ne sont pas non plus automatiquement modifiés au niveau de la ligne. Vous devez les mettre à jour manuellement.

## <a name="if-there-are-two-trade-agreements-for-the-same-period-or-overlapping-periods-the-same-agreement-line-is-always-selected"></a>S'il existe deux accords commerciaux pour la même période ou des périodes qui se chevauchent, la même ligne d'accord est toujours sélectionnée.

### <a name="issue-description"></a>Description du problème

Si deux accords commerciaux sont définis pour la même période ou des périodes qui se chevauchent, le même accord commercial semble être sélectionné à chaque fois que vous créez des lignes de commande client contenant ces articles.

### <a name="issue-resolution"></a>Résolution du problème

S'il y a plus d'un accord commercial pour une date donnée, l'accord commercial qui a le prix le plus bas est toujours sélectionné. Pour plus d'informations, téléchargez le livre blanc suivant : [Accords commerciaux dans Microsoft Dynamics AX 2012](https://www.axug.com/HigherLogic/System/DownloadDocumentFile.ashx?DocumentFileKey=3396a3a8-1f48-4d85-8cd6-5fa982f62e90).

## <a name="can-i-link-a-purchase-order-to-a-sales-order-to-fulfill-demand"></a>Puis-je lier une commande fournisseur à une commande client pour répondre à la demande ?

Vous pouvez créer une commande fournisseur à partir d’une commande client. Pour plus d'informations, voir [Créer une commande fournisseur à partir d’une commande client](tasks/create-purchase-order-sales-order.md).

## <a name="i-cant-cancel-or-delete-a-return-order-or-a-sales-order"></a>Je ne peux pas annuler ou supprimer un ordre de retour ou une commande client.

Vous ne pouvez annuler que les commandes client et les ordres de retour qui se trouvent dans l'état *Créé*. Pour plus d'informations, voir [Annuler un ordre de retour](../service-management/cancel-return-order.md).

## <a name="when-i-try-to-cancel-a-sales-order-i-receive-a-reservations-cannot-be-removed-because-there-is-work-created-which-relies-on-the-reservations-error"></a>Lorsque j'essaie d'annuler une commande client, je reçois le message d'erreur "Impossible de supprimer les réservations, car un travail qui a été créé repose sur ces réservations".

Si le travail est associé à une commande client, vous ne pouvez pas annuler la commande client tant que le travail n'est pas annulé et contrepassé. Cette exigence s'applique même si le travail associé à la commande client est clôturé.

Pour régler ce problème, procédez comme suit.

1. Annulez le travail et remettez le stock à l'emplacement souhaité. Accédez au chargement approprié de la commande client et sélectionnez soit **Réduisez la quantité prélevée** sur la ligne de chargement ou **Contrepasser le travail** sur le volet Actions.

    Le travail a maintenant un statut *Annulé*, et un nouveau travail de mouvement de stock est automatiquement créé et traité pour remettre le stock à l'emplacement qui a été décrit au moment de l'annulation.

2. Supprimez le chargement. L'expédition est également supprimée.
3. Vous devriez maintenant pouvoir accéder à la commande client et l'annuler.

## <a name="i-cant-cancel-an-intercompany-purchase-order-that-is-linked-to-a-sales-order"></a>Je ne peux pas annuler une commande fournisseur intersociétés liée à une commande client.

### <a name="issue-description"></a>Description du problème

Si vous essayez d'annuler une commande fournisseur intersociétés liée à une commande client, le message d'erreur suivant peut s'afficher : "Impossible de réduire la quantité en raison du changement de signe de la quantité de mise à jour restante".

### <a name="issue-resolution"></a>Résolution du problème

Ce problème a été résolu dans Microsoft Dynamics 365 Supply Chain Management version 10.0.13. Dans cette version et les versions ultérieures, vous pouvez désormais annuler une commande fournisseur intersociétés liée à une commande client.

## <a name="can-i-restore-an-invoiced-sales-order-that-was-deleted"></a>Puis-je restaurer une commande client facturée qui a été supprimée ?

### <a name="issue-description"></a>Description du problème

Une commande client facturée a été supprimée par erreur et vous souhaitez la restaurer ou en afficher les détails.

### <a name="issue-resolution"></a>Résolution du problème

Si la commande client supprimée a déjà été facturée, accédez à **Compte client \> Transactions \> Document original \> Voir les détails**. Recherchez la facture que vous recherchez et sélectionnez-la pour afficher ses détails. Ces détails incluent la référence de la commande client. Vous devriez également pouvoir accéder aux détails de la commande client à partir de cette page.

## <a name="the-deadline-of-a-sales-order-header-cant-be-found-in-the-salesorderheaderv2entity-data-entity"></a>La date limite d'un en-tête de commande client est introuvable dans l'entité de données SalesOrderHeaderV2Entity.

Le champ Date limite n'existe pas sur l'entité *SalesOrderHeaderV2Entity*.

## <a name="i-must-delete-orphaned-sales-order-records"></a>Je dois supprimer les enregistrements de commande client orphelins.

Pour nettoyer les enregistrements de commande client orphelins, exécutez la tâche périodique *Suppression de commandes client* en accédant à l'un des emplacements suivants :

- Ventes et marketing \> Tâches périodiques \> Nettoyage \> Supprimer des commandes clients
- Retail et Commerce \> IT Retail et Commerce \> Nettoyage \> Supprimer des commandes client

## <a name="is-there-a-way-to-calculate-commissions-on-invoices-that-have-already-been-posted"></a>Existe-t-il un moyen de calculer les commissions sur les factures déjà validées ?

Supply Chain Management ne prend actuellement pas en charge le calcul des commissions pour les factures validées.

## <a name="a-bundle-item-isnt-supported-in-an-intercompany-process"></a>Un élément d'offre groupée n'est pas pris en charge dans un processus intersociétés.

L'élément d'offre groupée n'est pas disponible pour la commande fournisseur car, si vous examinez les lignes de commande client pour l'élément d'offre groupée, vous remarquerez que la quantité est *0* (zéro) et l'état est *Annulé*. Ce comportement est fait exprès. La commande client n'achète que les composants de l'élément d'offre groupée. Elle n'achète pas l'élément d'offre groupée lui-même.

Si vous devez acheter une offre groupée, déterminez si vous devez la marquer comme élément d'offre groupée, car cette fonctionnalité est en fait conçue pour les scénarios de constatation du produit. Pour plus d'informations sur les éléments d'offre groupée, voir [Offres groupées](../../finance/accounts-receivable/revenue-recognition-setup.md#bundles).


[!INCLUDE[footer-include](../../includes/footer-banner.md)]