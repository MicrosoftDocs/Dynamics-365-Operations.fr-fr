---
title: Blocage du stock
description: Cette rubrique fournit une vue d'ensemble du blocage du stock qui fait partie du processus d'inspection de qualité dans Supply Chain Management. Vous pouvez utiliser le blocage du stock pour empêcher des articles d'être traités ou consommés.
author: perlynne
manager: tfehr
ms.date: 01/17/2020
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
ms.openlocfilehash: 646ddc231b1ee25b13fdeb779b2bbeae6dd8c2a9
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/15/2021
ms.locfileid: "5011595"
---
# <a name="inventory-blocking"></a>Blocage du stock

[!include [banner](../includes/banner.md)]

Cette rubrique fournit une vue d'ensemble du blocage du stock qui fait partie du processus d'inspection de qualité dans Supply Chain Management. Vous pouvez utiliser le blocage du stock pour empêcher des articles d'être traités ou consommés.

Les méthodes suivantes permettent de bloquer les articles en stock :
-   Manuellement
-   création d'un ordre de qualité ;
-   utilisation d'un processus permettant de générer un ordre de qualité.
-   En utilisant le blocage du statut du stock

## <a name="blocking-items-manually"></a>Blocage manuel des articles
Vous pouvez bloquer la quantité d'un article en créant une transaction sur la page **Blocage du stock**. Seuls les articles compris dans le stock disponible peuvent être bloqués manuellement. Pour les quantités bloquées manuellement, vous devez décider si vous souhaitez inclure la quantité bloquée dans les activités de planification en tant que quantité en stock. Les réceptions prévues sont des articles bloqués qui seront disponibles en stock après l'inspection. Vous pouvez mettre à jour la date prévue. Pour les articles bloqués via un ordre de qualité, l'option **Réceptions prévues** est sélectionnée pour les articles qui sont bloqués via un ordre de qualité. Vous pouvez annuler un blocage manuel défini sur une quantité en supprimant la transaction sur la page **Blocage du stock**.

## <a name="blocking-items-by-creating-a-quality-order"></a>Blocage d'articles via la création d'un ordre de qualité
Vous pouvez spécifier les articles qui doivent être inspectés en créant un ordre de qualité sur la page **Ordres de qualité**. Lors de la création d'un ordre de qualité, la quantité spécifiée d'un article est bloquée. C'est pourquoi le programme d'échantillonnage d'article associé à l'ordre de qualité contrôle la quantité d'articles qui doivent être inspectés et non pas la quantité qui est bloquée. Indépendamment de la quantité envoyée pour inspection, telle que spécifiée par le programme d'échantillonnage, la quantité d'article entrée dans l'ordre de qualité correspond à la quantité bloquée.

> [!NOTE]
> L'utilisation de la date d'expiration du lot et des fonctions de blocage du statut du stock n'est pas prise en charge par la planification principale. Cela pourrait entraîner une double exclusion de l'inventaire disponible, ce qui peut se produire lors de la planification générale. Nous vous conseillons de vous fier aux codes de disposition des lots, au lieu du statut du stock, pour bloquer les lots expirés.

## <a name="blocking-items-by-using-a-process-that-generates-a-quality-order"></a>Blocage d'articles via un processus permettant de générer un ordre de qualité
Si une quantité d'article spécifie qu'un article doit être inspecté, une quantité de l'article est bloquée automatiquement. Par conséquent, lorsqu'un ordre de qualité est généré automatiquement, le programme d'échantillonnage d'article associé à l'ordre de qualité contrôle la quantité d'articles bloquée et la quantité d'articles à inspecter. Si l'option **Blocage total** de la page **Échantillonnage d'article** est sélectionnée, la quantité complète (d'une ligne de commande fournisseur, par exemple) est bloquée au cours de l'inspection, indépendamment de la quantité d'échantillonnage d'article.
### <a name="example"></a>Exemple

Dans l'exemple suivant, un ordre de qualité est généré lors de la validation d'un bon de livraison de commande fournisseur. Sur la page **Associations de qualité**, vous avez spécifié que la validation d'un bon de livraison de commande fournisseur est spécifiée en tant que processus qui active l'ordre de qualité.

|Configuration                                                                     |Action utilisateur                 |Résultat             |
|--------------------------------------------------------------------------|----------------------------|-------------------|
| Une association de qualité spécifie qu'un ordre de qualité doit être généré dès la validation d'un bon de livraison de commande fournisseur. Le paramétrage de l'échantillonnage d'article de l'ordre de qualité spécifie que 10 % de la quantité de ligne de commande fournisseur doivent être inspectés. En outre, lorsque l'option **Blocage total** est sélectionnée, le paramétrage de l'échantillonnage d'article indique que la quantité complète de la ligne de commande fournisseur doit être bloquée au cours de l'inspection, indépendamment de la quantité envoyée à cette fin. | Le bon de livraison est validé. | Un ordre de qualité est généré. 10 % de la quantité de commande fournisseur de l'article sont envoyés pour inspection. La quantité complète de la ligne de commande fournisseur est bloquée. |

## <a name="blocking-items-by-using-inventory-status-blocking"></a>Blocage des articles en utilisant le blocage du statut du stock
Vous pouvez spécifier quels statuts du stock sont des statuts de blocage à l'aide du paramètre **Blocage du stock** sur la page **Statuts du stock**.  Vous ne pouvez pas utiliser les statuts de stock comme statuts de blocage pour les ordres de fabrication, les commandes client, les ordres de transfert, les transactions sortantes ou les intégrations de projets. Pour un travail sortant, utilisez les articles qui ont un statut de stock disponible. Si vous avez des articles ayant un statut **Cassé**, et si la planification est effectuée sur ces articles, les articles sont considérés comme manquants et le stock est automatiquement réapprovisionné.



<a name="additional-resources"></a>Ressources supplémentaires
--------

[Créer et tenir à jour un blocage du stock](tasks/create-maintain-inventory-blocking.md)

[Processus de gestion de la qualité](quality-management-processes.md)

[Inspecter la qualité des marchandises](tasks/inspect-quality-goods.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]