---
title: FIFO avec valeur physique et marquage
description: Premier entré, premier sorti (First In, First Out, ou FIFO) est un modèle de stock selon lequel les premières réceptions en stock sont sorties en premier. Les sorties de stock mises à jour financièrement sont réglées avec les premières réceptions en stock, en fonction de la date financière du mouvement de stock.
author: AndersGirke
manager: tfehr
ms.date: 06/15/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventJournalLossProfit, InventMarking, InventModelGroup, SalesTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: 54682
ms.assetid: dc0e2855-83a0-41a7-a398-3c7852597d1a
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 8e01300a4932cb6797905072b913b70db3700184
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5205418"
---
# <a name="fifo-with-physical-value-and-marking"></a>FIFO avec valeur physique et marquage

[!include [banner](../includes/banner.md)]

Premier entré, premier sorti (First In, First Out, ou FIFO) est un modèle de stock selon lequel les premières réceptions en stock sont sorties en premier. Les sorties de stock mises à jour financièrement sont réglées avec les premières réceptions en stock, en fonction de la date financière du mouvement de stock. 

Lorsque vous utilisez la méthode FIFO, il n’est pas nécessaire d’utiliser la règle FIFO. Vous pouvez marquer les mouvements de stock de manière ce qu’une réception d’article spécifique soit réglée avec une sortie spécifique. Si vous utilisez le modèle de stock FIFO, nous vous recommandons une clôture de stock périodique. Les exemples suivants illustrent l’impact du modèle FIFO dans trois configurations différentes :

-   FIFO sans l’option **Inclure la valeur physique**
-   FIFO avec l’option **Inclure la valeur physique**
-   FIFO avec marquage

## <a name="fifo-without-the-include-physical-value-option"></a>FIFO sans l’option Inclure la valeur physique
Dans cet exemple, le groupe de modèles d’article n’est pas marqué pour inclure la valeur physique. La figure suivante illustre ces transactions :

-   1a. Réception physique en stock pour une quantité de 1 à un coût de 10,00 EUR chacune.
-   1b. Réception financière en stock pour une quantité de 1 à un coût de 10,00 EUR chacune.
-   2a. Réception physique en stock pour une quantité de 2 à un coût de 10,00 EUR chacune.
-   2b. Réception financière en stock pour une quantité de 2 à un coût de 10,00 EUR chacune.
-   3a. Réception physique en stock pour une quantité 1 au coût unitaire de 25,00 EUR.
-   4a. Réception physique en stock pour une quantité de 1 à un coût de 30,00 EUR chacune.
-   4b. Réception financière en stock pour une quantité de 1 à un coût de 30,00 EUR chacune.
-   5a. Sortie physique de stock pour une quantité de 1 à un prix de revient de 20,00 EUR (prix de revient moyen en vigueur des transactions mises à jour financièrement).
-   5b. Sortie financière de stock pour une quantité de 1 à un prix de revient de 15,00 EUR (prix de revient moyen en vigueur des transactions mises à jour financièrement).
-   6. La clôture du stock est effectuée. Selon la méthode FIFO, la première sortie mise à jour financièrement est réglée par rapport à la première réception mise à jour financièrement. Un ajustement de 5,00 EUR sera effectué sur la transaction de sortie.

Le nouveau prix de revient moyen en vigueur reflète la moyenne des transactions mises à jour financièrement. Les illustrations suivantes indiquent l’impact du modèle de stock FIFO sur cette série de transactions lorsque l’option **Inclure la valeur physique** n’est pas utilisée. 

![FIFO Sans Inclure la valeur physique](./media/fifowithoutincludephysicalvalue.gif) 

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

## <a name="fifo-with-the-include-physical-value-option"></a>FIFO avec l’option Inclure la valeur physique
Si la case à cocher **Inclure la valeur physique** est activée pour un article dans la page **Groupe de modèles d’article**, le système utilise à la fois les transactions de réception physique et financière pour calculer le prix de revient moyen en cours. Au besoin, le système ajuste la transaction de sortie mise à jour physiquement. Si la case à cocher **Inclure la valeur physique** est désactivée, la clôture de stock avec le modèle de stock FIFO ne règle que les transactions financièrement mises à jour. La figure suivante illustre ces transactions :

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
-   7. La clôture du stock est effectuée. Selon la méthode FIFO, la première transaction de sortie financière sera ajustée ou réglée par rapport à la première réception mise à jour, qu’elle soit financière ou physique.

La transaction 5b sera réglée en fonction de la transaction de réception 1b. Un ajustement de -11,25 EUR est effectué sur cette transaction de sortie. Le nouveau prix de revient moyen en vigueur reflète la moyenne des transactions mises à jour financièrement et physiquement, soit 27,50 EUR. Les illustrations suivantes indiquent l’impact du modèle de stock FIFO sur cette série de transactions lorsque l’option **Inclure la valeur physique** n’est pas utilisée. 

![FIFO avec Inclure la valeur physique](./media/fifowithincludephysicalvalue.gif) 

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

## <a name="fifo-with-marking"></a>FIFO avec marquage
Le marquage est un processus qui vous permet de lier, ou de marquer, une transaction de sortie à une transaction de réception. Cette opération peut être effectuée avant ou après la validation d’une transaction. Vous pouvez utiliser le marquage si vous voulez être sûr du coût exact du stock lors de la validation de la transaction ou de l’exécution de la clôture de stock. Par exemple, le service à la clientèle a accepté une commande urgente d’un client important. Comme il s’agit d’une commande urgente, vous devez payer plus cher pour cet article afin de satisfaire la demande de votre client. Vous devez vous assurer que le coût de cet article en stock se reflètera dans la marge, ou le coût des marchandises vendues (COGS), pour la facture de cette commande client. Lorsque la commande fournisseur est validée, le stock est reçu à un coût de 120,00 EUR. Si ce document de commande client est marqué par rapport à la commande fournisseur avant la validation du bon de livraison ou de la facture, le coût des marchandises vendues sera de 120,00 EUR, et non le coût moyen en vigueur de l’article. Si le bon de livraison ou la facture de la commande client est validée avant le marquage, le coût des marchandises vendues sera validé au prix de revient moyen en vigueur. Avant d’exécuter la clôture de stock, ces deux transactions peuvent encore être marquées l’une par rapport à l’autre. Lorsqu’une transaction de réception correspond à une transaction de sortie, la méthode d’évaluation définie dans le groupe de modèles d’article est ignorée et le système règle ces transactions les unes avec les autres. Vous pouvez marquer une transaction de sortie par rapport à une réception avant la validation de la transaction. Vous pouvez le faire à partir d’une ligne de commande client dans la page **Détails de la commande client**. Les transactions de réception en cours sont affichées sur la page **Marquage**. Vous pouvez également marquer une transaction de sortie par rapport à une réception après la validation de la transaction. Vous pouvez faire correspondre ou marquer une transaction de sortie par rapport à une transaction de réception en cours pour un article inventorié dans un journal d’ajustement de stock validé. La figure suivante illustre ces transactions :

-   1a. Réception physique en stock pour une quantité de 1 à un coût de 10,00 EUR chacune.
-   1b. Réception financière en stock pour une quantité de 1 à un coût de 10,00 EUR chacune.
-   2a. Réception physique en stock pour une quantité de 1 à un coût de 20,00 EUR chacune.
-   2b. Réception financière en stock pour une quantité de 1 à un coût de 20,00 EUR chacune.
-   3a. Réception physique en stock pour une quantité de 1 à un coût de 25,00 EUR chacune.
-   4a. Réception physique en stock pour une quantité de 1 à un coût de 30,00 EUR chacune.
-   4b. Réception financière en stock pour une quantité de 1 à un coût de 30,00 EUR chacune.
-   5a. Sortie physique de stock pour une quantité de 1 à un prix de revient de 21,25 EUR chacune (prix de revient moyen en vigueur des transactions mises à jour financièrement et physiquement).
-   5b. Sortie financière de stock pour une quantité 1 marquée par rapport à la réception en stock 2b avant la validation de la transaction. Cette transaction est validée à un prix de revient unitaire de 20,00 EUR.
-   6a. Sortie physique de stock pour une quantité 1 à un prix de revient unitaire de 21,25 EUR.
-   7. La clôture du stock est effectuée. Étant donné que la transaction FIFO mise à jour financièrement est marquée par rapport à une réception existante, ces transactions sont réglées les unes avec les autres et aucun ajustement n’est effectué.

Le nouveau prix de revient moyen en vigueur reflète la moyenne des transactions mises à jour financièrement et physiquement, soit 27,50 EUR. Les illustrations suivantes montrent les effets du modèle de stock FIFO sur cette série de transactions quand le marquage entre les sorties et les réceptions est utilisé. 

![FIFO avec marquage](./media/fifowithmarking.gif) 

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