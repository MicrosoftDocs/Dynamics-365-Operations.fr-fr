---
title: Blocage du stock
description: Cette rubrique fournit une vue d’ensemble du blocage du stock qui fait partie du processus d’inspection de qualité dans Supply Chain Management. Vous pouvez utiliser le blocage du stock pour empêcher des articles d’être traités ou consommés.
author: perlynne
manager: tfehr
ms.date: 03/02/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventBlocking, InventQualityOrderTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: 2094
ms.assetid: 1968e32f-eff9-4c17-8f7f-a870f0c38fbc
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: d1d4b006f37904c0ae20691aaa98c75f1d5833b7
ms.sourcegitcommit: 105f65468b45799761c26e5d0ad9df4ff162c38d
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/04/2021
ms.locfileid: "5487895"
---
# <a name="inventory-blocking"></a>Blocage du stock

[!include [banner](../includes/banner.md)]

Cette rubrique fournit une vue d’ensemble du blocage du stock qui fait partie du processus d’inspection de qualité dans Supply Chain Management. Vous pouvez utiliser le blocage du stock pour empêcher des articles d’être traités ou consommés.

Les méthodes suivantes permettent de bloquer les articles en stock :

- Manuellement
- création d’un ordre de qualité ;
- utilisation d’un processus permettant de générer un ordre de qualité.
- En utilisant le blocage du statut du stock

## <a name="blocking-items-manually"></a>Blocage manuel des articles

Vous pouvez bloquer la quantité d’un article en créant une transaction sur la page **Blocage du stock**. Seuls les articles compris dans le stock disponible peuvent être bloqués manuellement. Pour les quantités bloquées manuellement, vous devez décider si vous souhaitez inclure la quantité bloquée dans les activités de planification en tant que quantité en stock. Les réceptions prévues sont des articles bloqués qui seront disponibles en stock après l’inspection. Vous pouvez mettre à jour la date prévue. Pour les articles bloqués via un ordre de qualité, l’option **Réceptions prévues** est sélectionnée pour les articles qui sont bloqués via un ordre de qualité. Vous pouvez annuler un blocage manuel défini sur une quantité en supprimant la transaction sur la page **Blocage du stock**.

## <a name="blocking-items-by-creating-a-quality-order"></a>Blocage d’articles via la création d’un ordre de qualité

Vous pouvez spécifier les articles qui doivent être inspectés en créant un ordre de qualité sur la page **Ordres de qualité**. Lors de la création d’un ordre de qualité, la quantité spécifiée d’un article est bloquée. C’est pourquoi le programme d’échantillonnage d’article associé à l’ordre de qualité contrôle la quantité d’articles qui doivent être inspectés et non pas la quantité qui est bloquée. Indépendamment de la quantité envoyée pour inspection, telle que spécifiée par le programme d’échantillonnage, la quantité d’article entrée dans l’ordre de qualité correspond à la quantité bloquée.

> [!NOTE]
> L’utilisation de la date d’expiration du lot et des fonctions de blocage du statut du stock n’est pas prise en charge par la planification principale. Cela pourrait entraîner une double exclusion de l’inventaire disponible, ce qui peut se produire lors de la planification générale. Nous vous conseillons de vous fier aux codes de disposition des lots, au lieu du statut du stock, pour bloquer les lots expirés.

## <a name="blocking-items-by-using-a-process-that-generates-a-quality-order"></a>Blocage d’articles via un processus permettant de générer un ordre de qualité

Si une quantité d’article spécifie qu’un article doit être inspecté, une quantité de l’article est bloquée automatiquement. Par conséquent, lorsqu’un ordre de qualité est généré automatiquement, le programme d’échantillonnage d’article associé à l’ordre de qualité contrôle la quantité d’articles bloquée et la quantité d’articles à inspecter. Si l’option **Blocage total** de la page **Échantillonnage d’article** est sélectionnée, la quantité complète (d’une ligne de commande fournisseur, par exemple) est bloquée au cours de l’inspection, indépendamment de la quantité d’échantillonnage d’article.

### <a name="example"></a>Exemple

Dans l’exemple suivant, un ordre de qualité est généré lors de la validation d’un bon de livraison de commande fournisseur. Sur la page **Associations de qualité**, vous avez spécifié que la validation d’un bon de livraison de commande fournisseur est spécifiée en tant que processus qui active l’ordre de qualité.

|Configuration |Action utilisateur |Résultat |
|----|---|---|
| Une association de qualité spécifie qu’un ordre de qualité doit être généré dès la validation d’un bon de livraison de commande fournisseur. Le paramétrage de l’échantillonnage d’article de l’ordre de qualité spécifie que 10 % de la quantité de ligne de commande fournisseur doivent être inspectés. En outre, lorsque l’option **Blocage total** est sélectionnée, le paramétrage de l’échantillonnage d’article indique que la quantité complète de la ligne de commande fournisseur doit être bloquée au cours de l’inspection, indépendamment de la quantité envoyée à cette fin. | Le bon de livraison est validé. | Un ordre de qualité est généré. 10 % de la quantité de commande fournisseur de l’article sont envoyés pour inspection. La quantité complète de la ligne de commande fournisseur est bloquée. |

## <a name="blocking-items-by-using-inventory-status-blocking"></a>Blocage des articles en utilisant le blocage du statut du stock

Vous pouvez spécifier quels statuts du stock sont des statuts de blocage à l’aide du paramètre **Blocage du stock** sur la page **Statuts du stock**. Vous ne pouvez pas utiliser les statuts de stock comme statuts de blocage pour les ordres de fabrication, les commandes client, les ordres de transfert, les transactions sortantes ou les intégrations de projets. Pour un travail sortant, utilisez les articles qui ont un statut de stock disponible. Si vous avez des articles ayant un statut **Cassé**, et si la planification est effectuée sur ces articles, les articles sont considérés comme manquants et le stock est automatiquement réapprovisionné.

## <a name="take-care-when-blocking-items-that-use-both-inventory-status-blocking-and-quality-order-blocking"></a>Faites attention lorsque vous bloquez des articles qui utilisent à la fois le blocage du statut des stocks et le blocage des commandes de qualité

Vous pouvez créer un ordre de qualité associé à un inventaire ayant un statut d’inventaire qui a son paramètre **Blocage d’inventaire** activé. Dans ce cas, l’ordre de qualité générera un enregistrement de blocage d’inventaire supplémentaire en plus de celui créé par le statut de l’inventaire. Parce que le blocage de l’inventaire des ordres de qualité aura le paramètre **Réceptions prévues** activé, cela génère une transaction *Inventaire commandé* supplément qui est également bloquée par son état d’inventaire. Cette combinaison peut entraîner des difficultés dans la compréhension de la signification des transactions de stock générées, car il semblera que la quantité totale bloquée est supérieure à la quantité totale disponible. Examinons les transactions sur un exemple de réception de 10 pièces de l’article A0001 avec un ordre de qualité généré pour prélever 1 unité. Le comportement dépendra également du fait que l’option **Réserver les articles commandés** est activé sur la page **Paramètres de gestion des stocks et des entrepôts**.

>[!NOTE]
>Si vous utilisez conjointement le blocage du statut des stocks et les commandes de qualité, nous vous recommandons fortement d’avoir l’option **Réserver les articles commandés** activée.

### <a name="example-with-reserve-ordered-items-enabled"></a>Exemple avec "Réserver les articles commandés" activé

Lorsque **Réserver les articles commandés** est activé, toutes les transactions de blocage d’inventaire auront le statut soit *Réservé physique* ou *Réservé commandé*.

| Référence de transaction de stock | Reçu | Sortie | Quantité | Site | Entrepôt | Statut du stock | Entrepôt | Contenant | Commentaire |
|---|---|---|---|---|---|---|---|---|---|
| Commande fournisseur | Acheté | | 10 unités | 2 | 24 | Blocage | RECV | reçuLp1 | | 
| Blocage du stock | | Physique réservé | -9 unités | 2 | 24 | Blocage | | | Transaction générée par le blocage du statut des stocks |
| Blocage du stock | | Physique réservé | -1 unité | 2 | 24 | Blocage | RECV | reçuLp1 | Transaction générée par le blocage d’échantillonnage de l’ordre de qualité |
| Blocage du stock | Commandée | | 1 unité | 2 | 24 | Blocage | RECV | reçuLp1 | Reçus attendus du blocage d’échantillonnage de l’ordre de qualité |
| Blocage du stock | | Commandé réservé | 1 unité | 2 | 24 | Blocage | | | Transaction générée par le blocage du statut des stocks

### <a name="example-with-reserve-ordered-items-disabled"></a>Exemple avec "Réserver les articles commandés" désactivé

Lorsque **Réserver les articles commandés** est désactivé, les réceptions prévues ne peuvent pas être réservés car ils sont en statut *Commandé*, donc certains blocages resteront en état *À la commande*.

| Référence de transaction de stock | Reçu | Sortie | Quantité | Site | Entrepôt | Statut du stock | Entrepôt | Contenant | Commentaire |
|---|---|---|---|---|---|---|---|---|---|
| Commande fournisseur | Acheté | | 10 unités | 2 | 24 | Blocage | RECV | reçuLp1 | |
| Blocage du stock | | Physique réservé | -9 unités | 2 | 24 | Blocage | | | Transaction générée par le blocage du statut des stocks |
| Blocage du stock | | Physique réservé | -1 unité | 2 | 24 | Blocage | RECV | reçuLp1 | Transaction générée par le blocage d’échantillonnage de l’ordre de qualité |
| Blocage du stock | Commandée | | 1 unité | 2 | 24 | Blocage | RECV | reçuLp1 | Reçus attendus du blocage d’échantillonnage de l’ordre de qualité |
| Blocage du stock | | En commande | 1 unité | 2 | 24 | Blocage | RECV | reçuLp1 | Transaction générée par le blocage du statut des stocks

Notez la différence de statut de transaction et de dimensions entre les deux cas. Pour cette raison, nous vous recommandons d’activer l’option **Réserver les articles commandés**.

<!-- KFM: (Enable this section when the feature leaves private preview)

### Disable expected receipts from quality orders that sample blocked inventory feature

To simplify the inventory transactions in the case of quality orders that sample inventory blocked as a consequence of inventory status, the system provides a feature that disables expected receipts from such quality orders. As the expected receipt is in any case immediately blocked by inventory status blocking, there is no reduction of on-hand inventory because of this change.

-->

## <a name="additional-resources"></a>Ressources supplémentaires

[Créer et tenir à jour un blocage du stock](tasks/create-maintain-inventory-blocking.md)

[Processus de gestion de la qualité](quality-management-processes.md)

[Inspecter la qualité des marchandises](tasks/inspect-quality-goods.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]