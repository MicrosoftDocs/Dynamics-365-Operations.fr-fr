---
title: Détails des transactions de stock
description: Cet article fournit une vue d'ensemble de la page Détails des transactions qui affiche les détails d'une transaction de stock sélectionnée.
author: rachel-profitt
ms.date: 04/25/2022
ms.topic: article
ms.search.form: InventTrans, InventTransDetails
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: raprofit
ms.search.validFrom: 2022-04-25
ms.dyn365.ops.version: 10.0.27
ms.openlocfilehash: 55e29d5804f57cd86fb5ddac5d6c5576b7ea5f61
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8859385"
---
# <a name="inventory-transaction-details"></a>Détails des transactions de stock

Utilisez la page **Détails des transactions** pour afficher les détails de toute transaction de stock sélectionnée.

## <a name="open-the-transaction-details-page"></a>Ouvrir la page Détails des transactions

Pour ouvrir la page **Détails des transactions**, suivez ces étapes.

1. Accédez à **Gestion des stocks \> Recherches et états \> Transactions**.
1. Sélectionnez la transaction que vous souhaitez inspecter.
1. Dans le volet Actions, sélectionnez **Détails des transactions**.

## <a name="fasttabs-overview"></a>Présentation des raccourcis

La page **Détails des transactions** est divisée en plusieurs raccourcis. Le tableau suivant décrit l'objectif de chaque raccourci.

| Organisateur | Description |
|---|---|
| Généralités | Ce raccourci affiche des informations de base sur la transaction de stock sélectionnée. En plus des champs qui apparaissent sur la page **Transactions de stock**, elle inclut les champs supplémentaires décrits plus loin dans cet article. |
| Mises à jour | Ce raccourci affiche des informations liées aux aspects physiques, financiers et de règlement de la transaction de stock sélectionnée. Selon l'état actuel de la transaction, certains champs peuvent être vides. Cependant, ces champs seront automatiquement définis lorsque les transactions seront comptabilisées. En plus des champs qui apparaissent sur la page **Transactions de stock**, ce raccourci inclut les champs supplémentaires décrits plus loin dans cet article. |
| Validations dans la comptabilité | Ce raccourci affiche le type de validation et le compte général utilisés pour la mise à jour physique, la mise à jour financière, les revenus physiques, les charges physiques, les revenus financiers et les frais financiers liés à la transaction de stock sélectionnée. |
| Références | Ce raccourci affiche des informations supplémentaires sur la transaction source qui a créé la transaction de stock sélectionnée. Par exemple, ces informations peuvent inclure des détails du bon de commande ou de la commande client. |
| Informations associées | Ce raccourci affiche des informations supplémentaires sur la transaction de stock sélectionnée. Ces champs peuvent ne pas être définis si vous n'utilisez pas certaines fonctionnalités, telles que les catégories d'approvisionnement ou les projets. |
| Dimensions financières - physique | Ce raccourci affiche les valeurs de dimension financière qui ont été utilisées lors de la publication de la mise à jour physique. Si la mise à jour physique n'a pas été publiée, les champs seront vides. |
| Dimensions financières - financier | Ce raccourci affiche les valeurs de dimension financière qui ont été utilisées lors de la publication de la mise à jour financière. Si la mise à jour financière n'a pas été publiée, les champs seront vides. |
| Dimensions de stock | Ce raccourci affiche les valeurs de dimension de stock affectées à la transaction de stock sélectionnée. Ces valeurs incluent le site, l'entrepôt, la taille, la couleur, la configuration, l'emplacement, le numéro de lot, le numéro de série, l'état de l'inventaire, la plaque d'immatriculation et le propriétaire. |

## <a name="fields-on-the-general-fasttab"></a>Champs du raccourci Général

Le tableau suivant décrit les champs du raccourci **Général** qui n'apparaissent pas également sur la page **Transactions de stock**.

| Champ | Description |
|---|---|
| Tiers | Le nom de la partie concernée pour la transaction de stock sélectionnée. Par exemple, une transaction de bon de commande affiche le nom du fournisseur sur le bon de commande, et une transaction de commande client affiche le nom du client. Ce champ n'est pas disponible pour tous les types de transactions de stock. |
| Référence du stock | Si une autre transaction de stock est liée à la transaction de stock sélectionnée, le type de cette autre transaction. Par exemple, si une commande fournisseur est marquée par rapport à une commande client, le champ **Référence du stock** de la transaction du bon de commande sera défini sur *Commande client*. Le marquage se produit automatiquement pour les commandes de livraison directe et les commandes intersociétés. Lorsque vous utilisez le marquage avec des méthodes d'évaluation des coûts autres que *coût standard* et *moyenne mobile*, le système créera des règlements et des ajustements pour les transactions exactes qui sont marquées. De cette manière, vous pouvez obtenir un coût "réel" qui remplace la logique du premier entré, premier sorti (FIFO) ; dernier entré, premier sorti (LIFO) ; ou moyenne pondérée. |
| Numéro de stock | Transaction spécifique liée à la transaction de stock sélectionnée. Par exemple, si une commande fournisseur est marquée par rapport à une commande client, le champ **Numéro de stock** de la transaction de la commande fournisseur sera défini sur le numéro de la commande client. |
| ID projet | Si la transaction de stock sélectionnée est liée à un projet, ce champ est défini sur le numéro de projet. |
| N° de traitement | L'ID de lot unique que le système a attribué à la transaction de stock sélectionnée. |
| Lot de référence | Si une autre transaction de stock est liée à la transaction de stock sélectionnée, l'ID de lot de cette autre transaction. Par exemple, si une commande fournisseur est marquée par rapport à une commande client, le champ **Lot de référence** de la transaction de commande fournisseur sera la valeur **ID de lot** de la transaction de stock de la ligne de commande client. |
| Numéro de dimension | ID unique qui représente la combinaison de toutes les valeurs de dimension de stock affectées à la transaction de stock sélectionnée. |
| Valeur en cours | Une valeur qui indique si la transaction de stock sélectionnée a été réglée par le processus de clôture de stock. Si ce champ est défini sur *Oui*, la transaction n'est pas encore complètement réglée. |
| Date prévue | Pour les transactions de réception, la date à laquelle la réception de stock est censée avoir lieu. Par exemple, ce champ peut afficher la date de réception prévue sur un ordre de blocage de stock ou la date de livraison sur une ligne de commande fournisseur. |
| Date du stock | Ce champ est défini lorsqu'une transaction d'enregistrement a été effectuée sur l'ordre de réception avant qu'une réception physique ne soit validée. |
| Transfert non financier | Une valeur qui indique si la transaction de stock sélectionnée est un transfert non financier. Un transfert non financier se produit lorsqu'une modification des dimensions de stock n'est pas suivie financièrement sur la page **Groupe de modèles d'article**. |
| N° de traitement du transfert | Si la transaction de stock sélectionnée est un transfert non financier, ce champ prend la valeur **ID de lot** de l'autre transaction de stock sur laquelle la transaction sélectionnée est réglée. |

## <a name="fields-on-the-updates-fasttab"></a>Champs du raccourci Mises à jour

Le tableau suivant décrit les champs du raccourci **Mises à jour** qui n'apparaissent pas également sur la page **Transactions de stock**.

| Champ | Description |
|---|---|
| N° document physique | Le numéro de document du grand livre où la validation physique pour la transaction de stock sélectionnée a été générée. |
| Route | Itinéraire spécifique lié à la transaction de stock sélectionnée. Ce champ est défini uniquement pour les transactions de liste de prélèvement de production où la nomenclature ou la ligne de formule est liée à un article spécifique. |
| Bon de livraison | Le numéro de bon de livraison qui a été saisi pour une transaction d'accusé de réception de marchandises de commande fournisseur. |
| Montant du coût physique | Le montant qui a été validé dans la comptabilité pour la mise à jour physique. Pour un produit à coût standard, ce montant représente le coût standard. Pour les autres méthodes d'établissement des coûts, il représente la moyenne pondérée du produit au moment de la publication. |
| Produit physique | Le montant du revenu qui a été validé dans la comptabilité pour la mise à jour physique. |
| ID chargement | Si la transaction en cours est liée à un chargement dans la gestion du transport, ce champ affiche le numéro unique du chargement qui comprenait l'article. |
| Physiquement validée | Une valeur qui indique si la transaction de stock sélectionnée a été validée physiquement. Si la transaction en cours est enregistrée dans le grand livre, il y aura également un bon physique. |
| Financièrement validée | Une valeur qui indique si la transaction de stock sélectionnée a été validée financièrement. Si la transaction en cours est enregistrée dans le grand livre, il y aura également un bon financier. |
| Frais physiques validés | Une valeur qui indique si les frais physiques liés à la transaction de stock sélectionnée ont été validés. |
| Frais financiers validés | Une valeur qui indique si les frais financiers liés à la transaction de stock sélectionnée ont été validés. |
| N° document financier | Le numéro de pièce justificative dans le grand livre où la comptabilisation financière a été générée. |
| Facture | Le numéro de facture qui a été généré, par exemple, pour un bon de commande ou une commande client. |
| Ajustement | Le montant qui a été ajusté sur la transaction de stock sélectionnée à partir du processus de clôture et d'ajustement de stock. |
| Résultat, montant validé | Le montant de la transaction de stock sélectionnée qui a été validée dans le compte de résultat. |
| Facture non validée | Le numéro de facture d'un bon de commande connexe qui apparaît sur la page **Facture fournisseur en attente**. |
| Financièrement clôturée | Date à laquelle la transaction a été entièrement réglée. |
| Quantité marquée en PV | La quantité de poids variable couverte par le règlement. |
| Quantité réglée | La quantité réglée pour le mouvement de stock sélectionné. |
| Montant lettré | La valeur réglée pour le mouvement de stock sélectionné. |
