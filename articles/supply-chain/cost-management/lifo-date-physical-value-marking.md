---
title: Date LIFO avec valeur physique et marquage
description: "Date LIFO (dernier entré, premier sorti) est un modèle de stock basé sur le principe LIFO. Les sorties de stock sont réglées avec les dernières réceptions, en fonction de la date du mouvement de stock. En utilisant Date LIFO, s'il n'y a aucune réception avant la sortie, la sortie est réglée avec les réceptions intervenant après la date de sortie. Plusieurs sorties intervenant à la même date peuvent être réglées dans l'ordre Dernière sortie, dernière réception."
author: AndersGirke
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: InventJournalLossProfit, InventMarking, InventModelGroup, SalesTable
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, Operations, Retail
ms.custom: 51592
ms.assetid: d9f13274-3268-444f-85c8-b686fd39286d
ms.search.region: Global
ms.search.industry: Retail
ms.author: yuyus
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 116d2f34c0317f3246b8d9c6569430603e2cd2c6
ms.contentlocale: fr-fr
ms.lasthandoff: 09/29/2017

---

# <a name="lifo-date-with-physical-value-and-marking"></a>Date LIFO avec valeur physique et marquage

[!include[banner](../includes/banner.md)]

[!include[retail name](../includes/retail-name.md)]


Date LIFO (dernier entré, premier sorti) est un modèle de stock basé sur le principe LIFO. Les sorties de stock sont réglées avec les dernières réceptions, en fonction de la date du mouvement de stock. En utilisant Date LIFO, s'il n'y a aucune réception avant la sortie, la sortie est réglée avec les réceptions intervenant après la date de sortie. Plusieurs sorties intervenant à la même date peuvent être réglées dans l'ordre Dernière sortie, dernière réception. 

Lorsque vous utilisez le modèle de stock Date LIFO (dernier entré, premier sorti), s'il n'y a aucune réception avant la sortie, la sortie est réglée en fonction des réceptions intervenant après la date de sortie. Plusieurs sorties intervenant à la même date peuvent être réglées dans l'ordre Dernière sortie, dernière réception. Lorsque vous utilisez la date LIFO, il n'est pas nécessaire d'utiliser la règle de date LIFO. Vous pouvez marquer les mouvements de stock de manière ce qu'une réception d'article spécifique soit réglée avec une sortie spécifique. 

Si vous utilisez le modèle de stock Date LIFO, nous vous recommandons une clôture de stock périodique. 

Les exemples suivants illustrent l'impact du modèle Date LIFO dans trois configurations différentes :

-   Date LIFO sans l'option **Inclure la valeur physique**
-   Date LIFO avec l'option**Inclure la valeur physique**
-   Date LIFO avec marquage

## <a name="lifo-date-without-the-include-physical-value-option"></a>Date LIFO sans l'option Inclure la valeur physique
Dans cet exemple, le groupe de modèles d'article n'est pas marqué pour inclure la valeur physique. La figure suivante illustre ces transactions :

-   1a. Réception physique en stock pour une quantité de 1 à un coût de 10,00 EUR chacune.
-   1b. Réception financière en stock pour une quantité de 1 à un coût de 10,00 EUR chacune.
-   2a. Réception physique en stock pour une quantité de 1 à un coût de 20,00 EUR chacune.
-   2b. Réception financière en stock pour une quantité de 1 à un coût de 20,00 EUR chacune.
-   3a. Réception physique en stock pour une quantité de 1 à un coût de 25,00 EUR chacune.
-   4a. Sortie physique de stock pour une quantité de 1 à un prix de revient de 15,00 EUR (prix de revient moyen en vigueur des transactions mises à jour financièrement).
-   4b. Sortie financière de stock pour une quantité de 1 à un prix de revient de 15,00 EUR (prix de revient moyen en vigueur des transactions mises à jour financièrement).
-   5a. Réception physique en stock pour une quantité de 1 à un coût de 30,00 EUR chacune.
-   5b. Réception financière en stock pour une quantité de 1 à un coût de 30,00 EUR chacune.
-   6. La clôture du stock est effectuée. Selon la méthode Date LIFO, la dernière sortie mise à jour financièrement est réglée en fonction de la dernière réception mise à jour financièrement par date. Un ajustement de 5,00 EUR est effectué sur la transaction de sortie. Ces transactions sont réglées les unes en fonction des autres.

Le nouveau prix de revient moyen en vigueur reflète la moyenne des transactions mises à jour financièrement à 15,00 EUR. 

La figure suivante indique l'impact du modèle de stock Date LIFO lorsque l'option **Inclure la valeur physique** n'est pas utilisée. ![Date LIFO avec Inclure la valeur physique](./media/lifodatewithoutincludephysicalvalue.gif) 

**Clés du diagramme**

-   Les mouvements de stock sont représentés par les flèches verticales.
-   Les réceptions en stock sont représentées par les flèches verticales au-dessus de la ligne temporelle.
-   Les sorties de stock sont représentées par les flèches verticales en dessous de la ligne temporelle.
-   Au-dessus (ou en dessous) de chaque flèche verticale, la valeur du mouvement de stock est spécifiée au format Quantity@Unitprice.
-   La valeur d'un mouvement de stock entre parenthèses indique que le mouvement de stock est physiquement validé dans le stock.
-   La valeur d'un mouvement de stock qui n'est pas entre parenthèses indique que le mouvement de stock est financièrement validé dans le stock.
-   Chaque nouvelle transaction de réception ou de sortie est désignée par un nouveau libellé.
-   Chaque flèche verticale est marquée par un identificateur séquentiel, comme *1a*. Les identificateurs indiquent l'ordre des validations des mouvements de stock sur la ligne temporelle.
-   Les clôtures de stock sont représentées par une ligne pointillée verticale rouge et le libellé *Clôture du stock*.
-   Les règlements effectués par clôture de stock sont représentés par des flèches rouges en diagonale d'une réception vers une sortie.

## <a name="lifo-date-with-the-include-physical-value-option"></a>Date LIFO avec l'option Inclure la valeur physique
Vous pouvez activer la case à cocher **Inclure la valeur physique** pour un article dans la page **Groupe de modèles d'article**. Dans ce cas, le système utilise des transactions de réception tant physique que financière pour calculer le prix de revient moyen en vigueur. Au besoin, le système ajuste la transaction de sortie mise à jour physiquement. Si la case à cocher **Inclure la valeur physique** est désactivée, la clôture de stock qui utilise le modèle de stock Date LIFO ne règle que les transactions financièrement mises à jour. 

Dans cette exemple, le groupe de modèles d'article est marqué pour inclure la valeur physique. 

La figure suivante illustre ces transactions :

-   1a. Réception physique en stock pour une quantité de 1 à un coût de 10,00 EUR chacune.
-   1b. Réception financière en stock pour une quantité de 1 à un coût de 10,00 EUR chacune.
-   2a. Réception physique en stock pour une quantité de 1 à un coût de 20,00 EUR chacune.
-   2b. Réception financière en stock pour une quantité de 1 à un coût de 20,00 EUR chacune.
-   3a. Réception physique en stock pour une quantité de 1 à un coût de 25,00 EUR chacune.
-   4a. Sortie physique de stock pour une quantité de 1 à un prix de revient de 18,33 EUR (prix de revient moyen en vigueur des transactions mises à jour financièrement).
-   4b. Sortie financière de stock pour une quantité de 1 à un prix de revient de 18,33 EUR (prix de revient moyen en vigueur des transactions mises à jour financièrement).
-   5a. Réception physique en stock pour une quantité de 1 à un coût de 30,00 EUR chacune.
-   5b. Réception financière en stock pour une quantité de 1 à un coût de 30,00 EUR chacune.
-   6. La clôture du stock est effectuée. Selon la méthode Date LIFO, la dernière sortie mise à jour est ajustée ou réglée en fonction de la dernière réception mise à jour par date. Ces transactions ne sont pas réglées les unes avec les autres, car la transaction de réception financière est ajustée par rapport à une transaction mise à jour physiquement. À la place, seul un ajustement de 6,67 EUR est effectué sur la transaction de sortie.

Le nouveau prix de revient moyen en vigueur reflète la moyenne des transactions mises à jour financièrement à 20,00 EUR. 

La figure suivante indique l'impact du modèle de stock LIFO lorsque l'option **Inclure la valeur physique** est utilisée. ![Date LIFO avec Inclure la valeur physique](./media/lifodatewithincludephysicalvalue.gif) 

**Clés du diagramme**

-   Les mouvements de stock sont représentés par les flèches verticales.
-   Les réceptions en stock sont représentées par les flèches verticales au-dessus de la ligne temporelle.
-   Les sorties de stock sont représentées par les flèches verticales en dessous de la ligne temporelle.
-   Au-dessus (ou en dessous) de chaque flèche verticale, la valeur du mouvement de stock est spécifiée au format Quantity@Unitprice.
-   La valeur d'un mouvement de stock entre parenthèses indique que le mouvement de stock est physiquement validé dans le stock.
-   La valeur d'un mouvement de stock qui n'est pas entre parenthèses indique que le mouvement de stock est financièrement validé dans le stock.
-   Chaque nouvelle transaction de réception ou de sortie est désignée par un nouveau libellé.
-   Chaque flèche verticale est marquée par un identificateur séquentiel, comme *1a*. Les identificateurs indiquent l'ordre des validations des mouvements de stock sur la ligne temporelle.
-   Les clôtures de stock sont représentées par une ligne pointillée verticale rouge et le libellé *Clôture du stock*.
-   Les règlements effectués par clôture de stock sont représentés par des flèches rouges en diagonale d'une réception vers une sortie.

## <a name="lifo-date-with-marking"></a>Date LIFO avec marquage
Le marquage est un processus qui vous permet de lier, ou de marquer, une transaction de sortie à une transaction de réception. Cette opération peut être effectuée avant ou après la validation d'une transaction. Vous pouvez utiliser le marquage si vous voulez être sûr du coût exact du stock lors de la validation de la transaction ou de l'exécution de la clôture de stock. 

Par exemple, le service à la clientèle a accepté une commande urgente d'un client important. Puisqu'il s'agit d'une commande urgente, vous devrez payer plus cher pour cet article pour satisfaire la demande de votre client. Vous devez vous assurer que le coût de cet article en stock se reflètera dans la marge, ou le coût des marchandises vendues (COGS), pour la facture de cette commande client. 

Lorsque la commande fournisseur est validée, le stock est reçu à un coût de 120,00 EUR. Si ce document de commande client est marqué par rapport à la commande fournisseur avant la validation du bon de livraison ou de la facture, le coût des marchandises vendues sera de 120,00 EUR, et non le coût moyen en vigueur de l'article. Si le bon de livraison ou la facture de la commande client est validée avant le marquage, le coût des marchandises vendues sera validé au prix de revient moyen en vigueur. 

Avant d'exécuter la clôture de stock, ces deux transactions peuvent encore être marquées l'une par rapport à l'autre. 

Par exemple, une transaction de réception est marquée pour une transaction de sortie. Dans ce cas, la méthode d'évaluation définie dans le groupe de modèles d'article associé à l'article est ignorée et le système règle ces transactions les unes en fonction des autres. 

Vous pouvez marquer une transaction de sortie par rapport à une réception avant la validation de la transaction. Vous pouvez le faire à partir d'une ligne de commande client dans la page **Détails de la commande client**. Les transactions de réception en cours sont affichées sur la page **Marquage**. 

Vous pouvez également marquer une transaction de sortie par rapport à une réception après la validation de la transaction. Vous pouvez faire correspondre ou marquer une transaction de sortie par rapport à une transaction de réception en cours pour un article inventorié dans un journal d'ajustement de stock validé. 

La figure suivante illustre ces transactions :

-   1a. Réception physique en stock pour une quantité de 1 à un coût de 10,00 EUR chacune.
-   1b. Réception financière en stock pour une quantité de 1 à un coût de 10,00 EUR chacune.
-   2a. Réception physique en stock pour une quantité de 1 à un coût de 20,00 EUR chacune.
-   2b. Réception financière en stock pour une quantité de 1 à un coût de 20,00 EUR chacune.
-   3a. Réception physique en stock pour une quantité de 1 à un coût de 25,00 EUR chacune.
-   4a. Réception physique en stock pour une quantité de 1 à un coût de 30,00 EUR chacune.
-   4b. Réception financière en stock pour une quantité de 1 à un coût de 30,00 EUR chacune.
-   5a. Sortie physique de stock pour une quantité de 1 à un prix de revient de 21,25 EUR chacune (prix de revient moyen en vigueur des transactions mises à jour financièrement et physiquement).
-   5a. Sortie financière de stock pour une quantité 1 marquée par rapport à la réception en stock 2b avant la validation de la transaction. Cette transaction est validée avec un prix de revient de 20,00 EUR chacune.
-   6a. Sortie physique de stock pour une quantité 1 à un prix de revient unitaire de 21,25 EUR.
-   7. La clôture du stock est effectuée. Étant donné que la transaction FIFO mise à jour financièrement est marquée par rapport à une réception existante, ces transactions sont réglées les unes avec les autres et aucun ajustement n'est effectué.

Le nouveau prix de revient moyen en vigueur reflète la moyenne des transactions mises à jour financièrement et physiquement à 27,50 EUR. 

La figure suivante illustre les effets du modèle de stock LIFO lorsque le marquage entre les sorties et les réceptions est utilisé. ![Date LIFO avec marquage](./media/lifodatewithmarking.gif) 

**Clés du diagramme**

-   Les mouvements de stock sont représentés par les flèches verticales.
-   Les réceptions en stock sont représentées par les flèches verticales au-dessus de la ligne temporelle.
-   Les sorties de stock sont représentées par les flèches verticales en dessous de la ligne temporelle.
-   Au-dessus (ou en dessous) de chaque flèche verticale, la valeur du mouvement de stock est spécifiée au format Quantity@Unitprice.
-   La valeur d'un mouvement de stock entre parenthèses indique que le mouvement de stock est physiquement validé dans le stock.
-   La valeur d'un mouvement de stock qui n'est pas entre parenthèses indique que le mouvement de stock est financièrement validé dans le stock.
-   Chaque nouvelle transaction de réception ou de sortie est désignée par un nouveau libellé.
-   Chaque flèche verticale est marquée par un identificateur séquentiel, comme *1a*. Les identificateurs indiquent l'ordre des validations des mouvements de stock sur la ligne temporelle.
-   Les clôtures de stock sont représentées par une ligne pointillée verticale rouge et le libellé *Clôture du stock*.
-   Les règlements effectués par clôture de stock sont représentés par des flèches rouges en diagonale d'une réception vers une sortie.





