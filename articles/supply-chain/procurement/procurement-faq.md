---
title: FAQ sur l'approvisionnement
description: Cette rubrique fournit des réponses aux questions fréquemment posées (FAQ) sur la fonctionnalité d'approvisionnement de Supply Chain Management
author: kamaybac
ms.date: 05/31/2021
ms.topic: article
ms.search.form: PurchTable, PurchTablePart, PurchRFQTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: yanansong
ms.search.validFrom: 2021-05-31
ms.dyn365.ops.version: 10.0.13
ms.openlocfilehash: 09c99b88bc47609158805cdba1291ae462cda178
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/07/2021
ms.locfileid: "7476285"
---
# <a name="procurement-faq"></a>FAQ sur l'approvisionnement

[!include [banner](../includes/banner.md)]

Cette rubrique fournit des réponses aux questions fréquemment posées (FAQ) sur la fonctionnalité d'approvisionnement de Supply Chain Management.

## <a name="can-i-show-only-purchase-orders-that-i-created"></a>Puis-je afficher uniquement les commandes fournisseur que j’ai créées ?

Cette fonctionnalité n’est pas disponible actuellement.

## <a name="can-i-reserve-inventory-and-create-transactions-against-registered-inventory-on-a-purchase-order"></a>Puis-je réserver du stock et créer des transactions par rapport au stock enregistré sur une commande fournisseur ?

### <a name="issue-description"></a>Description du problème

Même lorsque les articles sont dans un état *Enregistré* sur une commande fournisseur, vous pouvez toujours réserver le stock. En d’autres termes, vous pouvez créer des transactions par rapport au stock enregistré.

### <a name="reproduce-the-issue"></a>Reproduire le problème

La procédure suivante montre comment reproduire le problème.

1. Création d’une commande fournisseur.
2. Enregistrez la ligne de commande fournisseur.
3. Notez que vous pouvez générer des réservations ou des transactions par rapport au stock enregistré.

### <a name="issue-resolution"></a>Résolution du problème

Ce comportement est fait exprès. On s’attend à ce que les articles enregistrés soient physiquement arrivés dans l’entrepôt ou dans le stock, et qu’ils soient donc disponibles pour réservation.

## <a name="can-i-find-the-user-who-canceled-a-purchase-order"></a>Puis-je trouver l’utilisateur qui a annulé une commande fournisseur ?

Ces informations ne sont suivies que si la commande fournisseur fait l’objet d’une gestion des modifications. Si vous utilisez la gestion des modifications, vous pouvez voir qui a envoyé la modification (l’annulation) et qui l’a approuvée.

## <a name="why-cant-i-link-a-purchase-agreement-to-an-existing-purchase-order"></a>Pourquoi ne puis-je pas lier un contrat d'achat à une commande fournisseur existante ?

Un contrat d’achat doit être associé à une ligne de commande fournisseur quand le bon de commande est créé. Sinon, les lignes de la commande fournisseur ne peuvent pas être associées aux lignes du contrat d’achat.

## <a name="what-check-triggers-the-update-prices-and-discounts-entered-manually-or-external-document-message"></a>Quel contrôle déclenche le message "Mettre à jour les prix et remises saisis manuellement ou via un document externe" ?

Lorsque vous modifiez la date d’expédition, vous pouvez recevoir un message indiquant "Mettre à jour les prix et les remises saisis manuellement ou via un document externe". Vous recevez ce message car, si la date d’expédition est modifiée, un autre accord de vente ou commercial peut être déclenché et entraîner une modification de prix. Une modification de la date d’expédition peut également affecter les planning d’entrepôt et d’autres informations connexes.

Le message est déclenché chaque fois que l’une des dates ou certains autres paramètres sont modifiés. Le but du message est de vous assurer que vous êtes au courant des changements de prix qui peuvent survenir en raison de ces changements.

Le message est l’invite d’évaluation de l’accord commercial (TAE). Pour une description complète, voir [Politiques d’évaluation des accords commerciaux](/dynamicsax-2012/appuser-itpro/trade-agreement-evaluation-policies-white-paper).

## <a name="why-cant-i-post-more-than-one-invoice-for-a-purchase-order-line-that-has-category-based-items"></a>Pourquoi ne puis-je pas valider plus d’une facture pour une ligne de commande fournisseur contenant des articles basés sur la catégorie ?

Une quantité est obligatoire si vous souhaitez valider des factures. Par conséquent, si la quantité totale d’une ligne n’a été facturée que pour un montant partiel, vous ne pourrez pas facturer le montant restant sur une autre facture.
