---
title: LIFO avec valeur physique et marquage
description: Dernier entré, premier sorti (Last In, First Out ou LIFO) est un modèle de stock dans lequel les dernières réceptions sont sorties en premier. Les sorties de stock sont réglées avec les dernières réceptions, en fonction de la date du mouvement de stock.
author: AndersGirke
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: InventJournalLossProfit, InventMarking, InventModelGroup, SalesTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: 55021
ms.assetid: 49c492b0-b018-44e0-928f-9671e54eee20
ms.search.region: Global
ms.search.industry: Retail
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: dcac72a60eac6abb29a017eb4ce02a71dca572d3
ms.sourcegitcommit: c08a9d19eed1df03f32442ddb65a2adf1473d3b6
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/06/2021
ms.locfileid: "6344542"
---
# <a name="lifo-with-physical-value-and-marking"></a>LIFO avec valeur physique et marquage

[!include [banner](../includes/banner.md)]

Dernier entré, premier sorti (Last In, First Out ou LIFO) est un modèle de stock dans lequel les dernières réceptions sont sorties en premier. Les sorties de stock sont réglées avec les dernières réceptions, en fonction de la date du mouvement de stock. 

Dans le modèle de stock Dernier entré, premier sorti (Last In, Last Out, ou LIFO), les dernières réceptions (les plus récentes) sortent du stock en premier. Les sorties de stock sont réglées avec les dernières réceptions, en fonction de la date du mouvement de stock. Lorsque vous utilisez la méthode LIFO, il n’est pas nécessaire d’utiliser la règle LIFO. Vous pouvez marquer des mouvements de stock de manière ce qu’une sortie d’article spécifique soit réglée avec une réception spécifique. Si vous utilisez le modèle de stock LIFO, nous vous recommandons une clôture de stock périodique. 

Les exemples suivants illustrent l’impact du modèle LIFO dans trois configurations différentes :

-   LIFO sans l’option **Inclure la valeur physique**
-   LIFO avec l’option **Inclure la valeur physique**
-   LIFO avec marquage

## <a name="lifo-without-the-include-physical-value-option"></a>LIFO sans l’option Inclure la valeur physique.
Dans cet exemple, le groupe de modèles d’article n’est pas marqué pour inclure la valeur physique. La figure suivante illustre ces transactions :

-   1a. Réception physique en stock pour une quantité de 1 à un coût de 10,00 EUR chacune.
-   1b. Réception financière en stock pour une quantité de 1 à un coût de 10,00 EUR chacune.
-   2a. Réception physique en stock pour une quantité de 1 à un coût de 20,00 EUR chacune.
-   2b. Réception financière en stock pour une quantité de 1 à un coût de 20,00 EUR chacune.
-   3a. Réception physique en stock pour une quantité de 1 à un coût de 25,00 EUR chacune.
-   4a. Réception physique en stock pour une quantité de 1 à un coût de 30,00 EUR chacune.
-   4b. Réception financière en stock pour une quantité de 1 à un coût de 30,00 EUR chacune.
-   5a. Sortie physique de stock pour une quantité de 1 à un prix de revient de 20,00 EUR (prix de revient moyen en vigueur des transactions mises à jour financièrement).
-   5b. Sortie financière de stock pour une quantité de 1 à un prix de revient de 20,00 EUR (prix de revient moyen en vigueur des transactions mises à jour financièrement).
-   6. La clôture du stock est effectuée. Selon la méthode LIFO, la dernière sortie mise à jour financièrement sera réglée par rapport à la dernière réception mise à jour financièrement. Un ajustement de 10,00 EUR sera effectué sur la transaction de sortie.

Le nouveau prix de revient moyen en vigueur reflète la moyenne des transactions mises à jour financièrement, 15,00 EUR. L’illustration suivante indique l’impact du modèle de stock LIFO sur cette série de transactions lorsque l’option **Inclure la valeur physique** n’est pas utilisée. 

![LIFO Sans Inclure la valeur physique.](./media/lifowithoutincludephysicalvalue.gif) 

**Clés du diagramme**

- Les mouvements de stock sont représentés par les flèches verticales.
- Les réceptions en stock sont représentées par les flèches verticales au-dessus de la ligne temporelle.
- Les sorties de stock sont représentées par les flèches verticales en dessous de la ligne temporelle.
- Au-dessus (ou en dessous) de chaque flèche verticale, la valeur du mouvement de stock est spécifiée au format Quantité@Prix unitaire.
- La valeur d’un mouvement de stock entre parenthèses indique que le mouvement de stock est physiquement validé dans le stock.
- La valeur d’un mouvement de stock qui n’est pas entre parenthèses indique que le mouvement de stock est financièrement validé dans le stock.
- Chaque nouvelle transaction de réception ou de sortie est désignée par un nouveau libellé.
- Chaque flèche verticale est marquée par un identificateur séquentiel, comme *1a*. Les identificateurs indiquent l’ordre des validations des mouvements de stock sur la ligne temporelle.
- Les clôtures de stock sont représentées par une ligne pointillée verticale rouge et le libellé *Clôture du stock*.
- Les règlements effectués par clôture de stock sont représentés par des flèches rouges en diagonale d’une réception vers une sortie.

## <a name="lifo-with-the-include-physical-value-option"></a>LIFO avec l’option Inclure la valeur physique
Si la case à cocher **Inclure la valeur physique** est activée pour un article dans la page **Groupes de modèles d’article**, le système utilise à la fois les transactions de réception physique et financière pour calculer le prix de revient moyen en cours. Au besoin, le système ajuste la transaction de sortie mise à jour physiquement. Si la case à cocher **Inclure la valeur physique** est désactivée, la clôture de stock avec le modèle de stock LIFO ne règle que les transactions financièrement mises à jour. 

La figure suivante illustre ces transactions :

-   1a. Réception physique en stock pour une quantité de 1 à un coût de 10,00 EUR chacune.
-   1b. Réception financière en stock pour une quantité de 1 à un coût de 10,00 EUR chacune.
-   2a. Réception physique en stock pour une quantité de 1 à un coût de 20,00 EUR chacune.
-   2b. Réception financière en stock pour une quantité de 1 à un coût de 20,00 EUR chacune.
-   3a. Réception physique en stock pour une quantité de 1 à un coût de 25,00 EUR chacune.
-   4a. Réception physique en stock pour une quantité de 1 à un coût de 30,00 EUR chacune.
-   4b. Réception financière en stock pour une quantité de 1 à un coût de 30,00 EUR chacune.
-   5a. Sortie physique de stock pour une quantité de 1 à un prix de revient de 21,25 EUR chacune (prix de revient moyen en vigueur des transactions mises à jour financièrement et physiquement).
-   5b. Sortie financière de stock pour une quantité de 1 à un prix de revient de 21,25 EUR (prix de revient moyen en vigueur des transactions mises à jour financièrement et physiquement).
-   6a. Sortie physique de stock pour une quantité 1 à un prix de revient unitaire de 21,25 EUR.
-   7. La clôture du stock est effectuée. Selon la méthode LIFO, la dernière transaction de sortie sera ajustée ou réglée par rapport à la dernière réception mise à jour.

La transaction 6a sera ajustée sur la transaction de réception 4b. Le système ne règlera pas ces transactions car la mise à jour de la réception s’effectue au niveau physique mais pas au niveau financier. La transaction de sortie physique fera l’objet d’un ajustement de 8,75 EUR. La transaction 5b sera ajustée sur la transaction de réception physique 3a. Le système ne règlera pas ces transactions parce qu’elles ne sont pas mises à jour financièrement. À la place, cette transaction de sortie fera l’objet d’un ajustement de –3,75 EUR. Le nouveau prix de revient moyen en vigueur reflète la moyenne des transactions mises à jour financièrement et physiquement, soit 20,00 EUR. 

Les illustrations suivantes indiquent l’impact du modèle de stock LIFO sur cette série de transactions lorsque l’option **Inclure la valeur physique** n’est pas utilisée. 

![LIFO avec Inclure la valeur physique.](./media/lifowithincludephysicalvalue.gif) 

**Clés du diagramme**

- Les mouvements de stock sont représentés par les flèches verticales.
- Les réceptions en stock sont représentées par les flèches verticales au-dessus de la ligne temporelle.
- Les sorties de stock sont représentées par les flèches verticales en dessous de la ligne temporelle.
- Au-dessus (ou en dessous) de chaque flèche verticale, la valeur du mouvement de stock est spécifiée au format Quantité@Prix unitaire.
- La valeur d’un mouvement de stock entre parenthèses indique que le mouvement de stock est physiquement validé dans le stock.
- La valeur d’un mouvement de stock qui n’est pas entre parenthèses indique que le mouvement de stock est financièrement validé dans le stock.
- Chaque nouvelle transaction de réception ou de sortie est désignée par un nouveau libellé.
- Chaque flèche verticale est marquée par un identificateur séquentiel, comme *1a*. Les identificateurs indiquent l’ordre des validations des mouvements de stock sur la ligne temporelle.
- Les clôtures de stock sont représentées par une ligne pointillée verticale rouge et le libellé *Clôture du stock*.
- Les règlements effectués par clôture de stock sont représentés par des flèches rouges en diagonale d’une réception vers une sortie.

## <a name="lifo-with-marking"></a>LIFO avec marquage
Le marquage est un processus qui vous permet de lier, ou de marquer, une transaction de sortie à une transaction de réception. Cette opération peut être effectuée avant ou après la validation d’une transaction. Vous pouvez utiliser le marquage si vous voulez être sûr du coût exact du stock lors de la validation de la transaction ou de l’exécution de la clôture de stock. Par exemple, le service à la clientèle a accepté une commande urgente d’un client important. Comme il s’agit d’une commande urgente, vous devez payer plus cher pour cet article afin de satisfaire la demande de votre client. 

Vous devez vous assurer que le coût de cet article en stock se reflètera dans la marge, ou le coût des marchandises vendues (COGS), pour la facture de cette commande client. Lorsque la commande fournisseur est validée, le stock est reçu à un coût de 120,00 EUR. Si ce document de commande client est marqué par rapport à la commande fournisseur avant la validation du bon de livraison ou de la facture, le coût des marchandises vendues sera de 120,00 EUR, et non le coût moyen en vigueur de l’article. Si le bon de livraison ou la facture de la commande client est validée avant le marquage, le coût des marchandises vendues sera validé au prix de revient moyen en vigueur. 

Avant d’exécuter la clôture de stock, ces deux transactions peuvent encore être marquées l’une par rapport à l’autre. 

Vous pouvez marquer une transaction de sortie par rapport à une réception avant la validation de la transaction. Vous pouvez le faire à partir d’une ligne de commande client dans la page **Détails de la commande client**. Les transactions de réception en cours sont affichées sur la page **Marquage**. 

Vous pouvez également marquer une transaction de sortie par rapport à une réception après la validation de la transaction. Vous pouvez faire correspondre ou marquer une transaction de sortie par rapport à une transaction de réception en cours pour un article inventorié dans un journal d’ajustement de stock validé. 

La figure suivante illustre ces transactions :

-   1a. Réception physique en stock pour une quantité de 1 à un coût de 10,00 EUR chacune.
-   1b. Réception financière en stock pour une quantité de 1 à un coût de 10,00 EUR chacune.
-   2a. Réception physique en stock pour une quantité de 1 à un coût de 20,00 EUR chacune.
-   2b. Réception financière en stock pour une quantité de 1 à un coût de 20,00 EUR chacune.
-   3a. Réception physique en stock pour une quantité de 1 à un coût de 25,00 EUR chacune.
-   4a. Réception physique en stock pour une quantité de 1 à un coût de 30,00 EUR chacune.
-   4b. Réception financière en stock pour une quantité de 1 à un coût de 30,00 EUR chacune.
-   5a. Sortie physique de stock pour une quantité de 1 à un prix de revient de 21,25 EUR chacune (prix de revient moyen en vigueur des transactions mises à jour financièrement et physiquement).
-   5b. Sortie financière de stock pour une quantité 1 marquée par rapport à la réception en stock 2b avant la validation de la transaction. Cette transaction est validée avec un prix de revient de 20,00 EUR chacune.
-   6a. Sortie physique de stock pour une quantité 1 à un prix de revient unitaire de 21,25 EUR.
-   7. La clôture du stock est effectuée. Étant donné que la transaction FIFO mise à jour financièrement est marquée par rapport à une réception existante, ces transactions sont réglées les unes avec les autres et aucun ajustement n’est effectué.

Le nouveau prix de revient moyen en vigueur reflète la moyenne des transactions mises à jour financièrement et physiquement, soit 27,50 EUR. 

Les illustrations suivantes montrent les effets du modèle de stock LIFO sur cette série de transactions quand le marquage entre les sorties et les réceptions est utilisé. 

![LIFO avec marquage.](./media/lifowithmarking.gif) 

**Clés du diagramme**

- Les mouvements de stock sont représentés par les flèches verticales.
- Les réceptions en stock sont représentées par les flèches verticales au-dessus de la ligne temporelle.
- Les sorties de stock sont représentées par les flèches verticales en dessous de la ligne temporelle.
- Au-dessus (ou en dessous) de chaque flèche verticale, la valeur du mouvement de stock est spécifiée au format Quantité@Prix unitaire.
- La valeur d’un mouvement de stock entre parenthèses indique que le mouvement de stock est physiquement validé dans le stock.
- La valeur d’un mouvement de stock qui n’est pas entre parenthèses indique que le mouvement de stock est financièrement validé dans le stock.
- Chaque nouvelle transaction de réception ou de sortie est désignée par un nouveau libellé.
- Chaque flèche verticale est marquée par un identificateur séquentiel, comme *1a*. Les identificateurs indiquent l’ordre des validations des mouvements de stock sur la ligne temporelle.
- Les clôtures de stock sont représentées par une ligne pointillée verticale rouge et le libellé *Clôture du stock*.
- Les règlements effectués par clôture de stock sont représentés par des flèches rouges en diagonale d’une réception vers une sortie.



[!INCLUDE[footer-include](../../includes/footer-banner.md)]