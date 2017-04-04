---
title: Consignation
description: Cette rubrique explique comment utiliser les processus de stock de consignation entrant.
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: ConsignmentDraftReplenishmentOrderJournal, ConsignmentProductReceiptLines, ConsignmentReplenishmentOrder, ConsignmentVendorPortalOnHand, InventJournalOwnershipChange, InventOnHandItemListPage, PurchTable, PurchVendorPortalConfirmedOrders
audience: Application User
ms.search.scope: Operations, Core
ms.custom: 220834
ms.assetid: 3c9d6de4-45d4-459a-aef7-0d9ad2c22b3a
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
translationtype: Human Translation
ms.sourcegitcommit: f77012e7b64b7f153103e9bbe91e8ded202b509a
ms.openlocfilehash: d9dcdd63649d6dbff96efe2eec7cad34025ab2ee
ms.lasthandoff: 03/31/2017


---

# <a name="consignment"></a>Consignation

Cette rubrique explique comment utiliser les processus de stock de consignation entrant.

Le stock de consignation est le stock qui appartient à un fournisseur, mais stocké à votre site. Lorsque vous êtes prêt à consommer ou à utiliser le stock, vous reprenez la propriété du stock. Cette rubrique comprend des informations sur la procédure recevoir physiquement le stock disponible appartenant à le fournisseur sans créer des transactions de comptabilité, comment démarrer un processus de production où le stock appartenant à le fournisseur peut être réservée physiquement. ou la modification de la propriété de la matière première afin de pouvoir traiter la consommation dans le cadre de le traitement d'ordre de fabrication. Il existe aussi des informations sur la manière dont les fournisseurs peuvent contrôler la consommation de leur stock à l'aide de l'interface de collaboration fournisseur. Pour plus d'informations sur l'activation et la configuration des processus de consignation entrante, voir [Paramétrage de la consignation](set-up-consignment.md).

## <a name="overview-of-the-consignment-process"></a>Vue d'ensemble du processus de consignation
Dans cet exemple de scénario, la société USMF a un accord de consignation avec le fournisseur US-104 pour la matière première M9211CI.

1.  Une commande de réapprovisionnement avec consignation est créé manuellement par un utilisateur de USMF, en fonction de la demande prévue. La commande est créée pour le fournisseur US-104 et une ligne est ajoutée pour l'article MS9211CI.
2.  Le fournisseur est informé de la livraison prévue. Cela peut se produire de l'une des trois manières suivantes :
    -   Une personne qui travaille chez USMF envoie des informations sur la commande au fournisseur.
    -   Le fournisseur peut contrôler le stock disponible prévu à l'aide de l'interface de collaboration fournisseur.
    -   Une personne qui travaille chez USMF filtre les données sur la page **Stock disponible** pour afficher uniquement les enregistrements du fournisseur US-104, lorsque le statut de réception est **Commandé**, et envoie ensuite ces informations au fournisseur.

3.  Le stock est livré de US-104 à USMF.
4.  Lorsque le matériel arrive chez USMF, la commande de réapprovisionnement avec consignation est mise à jour avec un accusé de réception de marchandises. Seuls les quantités physiques du stock appartenant au fournisseur sont enregistrées. Aucune transaction comptable n'est créée, car le stock appartient encore au fournisseur.
5.  Le fournisseur supervise les mises à jour du stock physique disponible sur la page **Stock de consignation disponible**.
6.  Maintenant que le stock physique est disponible, le processus de production réserver le stock appartenant au fournisseur et commence l'ordre de fabrication pour les produits finis qui vont consommer la matière première M9211CI.
7.  Le propriétaire des matières premières réservées qui vont être consommées dans la production du jour passe d'US-104 à USMF. Cela s'est effectue à l'aide d'un journal des modifications de propriété du stock. Ce processus crée des commandes fournisseur dont le champ **Origine** est défini sur **Consignation**.
8.  Le fournisseur surveille la consommation (transfert de propriété) sur la page **Produits reçus à partir du stock de consignation** et sort une facture basée sur les accords entre les deux sociétés.
9.  Le processus de production consomme la matière première en fonction du prélèvement de production. La réservation physique est automatiquement mise à jour pour refléter que le stock disponible appartient à USMF.
10. La facture d'US-104 est traitée par rapport aux commandes fournisseur générées automatiquement lorsque le journal de modification de propriété du stock a été traité. Le paiement est effectué au fournisseur US-104 pour le stock consommé.

USMF exécute des processus périodiques supplémentaires :

-   Le déplacement physique du stock appartenant au fournisseur entre différents entrepôts est traité à l'aide d'un journal de transferts.
-   Le stock physique disponible est mis à jour à l'aide d'un journal** Inventaire des articles**. L'inventaire peut également être utilisé par le fournisseur pour mettre à jour le stock disponible, s'il est autorisé à cela.

Le fournisseur, US-104, peut contrôler les mises à jour sur la page **Stock de consignation disponible**.

## <a name="consignment-replenishment-orders"></a>Commandes de réapprovisionnement avec consignation
Une commande de réapprovisionnement avec consignation est un document qui permet de demander et de faire le suivi des quantités de produits en stock qu'un fournisseur souhaite fournir dans un intervalle de dates donné en créant des mouvements de stock commandés. Généralement, cela aura lieu en fonction de la prévision et de la demande réelle des produits spécifiques. Le stock qui va être reçu par rapport à la commande de réapprovisionnement avec consignation reste la propriété du fournisseur. Seule la possession des produits liés à la mise à jour de réception physique est enregistrée et donc aucune mise à jour de la transaction comptable ne se produit. La dimension **Propriétaire** permet de séparer les informations sur le stock appartenant au fournisseur et sur celui appartenant à l'entité juridique de réception. Les lignes de commande de réapprovisionnement de consignation ont ** commande en cours ** le statut tant que la quantité complète des lignes n'a pas été reçue ou n'a pas été annulée. Lorsque la quantité totale a été reçue ou annulée, le statut devient ** terminé **. Le stock physique disponible associé à une commande de réapprovisionnement avec consignation peut être enregistré à l'aide d'un processus d'enregistrement ainsi que d'un processus de mise à jour d'accusé de réception de marchandises. L'enregistrement peut être effectué dans le cadre du processus d'arrivée d'article ou en mettant à jour manuellement les lignes de commande. Lorsque le processus de mise à jour d'accusé de réception de marchandises est utilisé, un enregistrement est créé dans le journal d'accusé de réception de marchandises, qui permet de confirmer la réception des marchandises aux fournisseurs. 

[consignation-réapprovisionnement-ordre d'![] (. /media/consignment-replenishment-order.png)](. /media/consignment-replenishment-order.png)

## <a name="inventory-ownership-change-journal"></a>Journal des modifications de propriété du stock
Le processus de modification du propriétaire du stock du fournisseur à l'entité juridique de réception s'effectue à l'aide d'un Journal des modifications de propriété du stock. Aucun mouvement de stock prévu n'est créé pour le journal. Les seules transactions de stock créées sont celles qui sont associées à un journal validé. Quand le journal est-il validé :

-   Le stock appartenant au fournisseur est publié via une référence **Modification de propriété** avec un statut **Vendu**.
-   Le stock disponible est ensuite reçu par l'entité juridique qui le consomme à l'aide d'un mouvement de stock mis à jour d'accusé de réception de marchandises sur la commande fournisseur. Ceci définit le statut de la commande sur **Reçu**. Les commandes fournisseur utilisées pour la consignation dont le champ **Origine** est défini sur **Consignation**.

Il n'est pas possible de mettre à jour la quantité sur les lignes de commande fournisseur avec consignation une fois la commande créée. 

[stock-propriété-modification-journal d'![] (. /media/inventory-ownership-change-journal.png)](. /media/inventory-ownership-change-journal.png)

## <a name="vendor-collaboration-in-consignment-processes"></a>Collaboration fournisseur dans les processus de consignation
L'interface de collaboration fournisseur comporte trois pages associées au processus de consignation entrante :

-   ** Commandes fournisseur ** ** consommant le stock de consignation ** - Commande fournisseur détaillée d'afficher les informations fiscales la modification de propriété du processus de consignation.
-   **Produits reçus à partir du stock de consignation** - Affiche des informations sur les articles et les quantités qui comportent des accusés de réception de marchandises mis à jour pendant le processus de modification de la propriété.
-   **Stock de consignation disponible** - Affiche des informations sur les articles avec consignation qu'ils prévoient de fournir, et les articles qui sont déjà physiquement disponibles sur le site du client.



