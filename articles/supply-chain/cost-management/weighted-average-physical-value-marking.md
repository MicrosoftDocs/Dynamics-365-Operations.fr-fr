---
title: "Moyenne pondérée avec valeur physique et marquage"
description: "La moyenne pondérée est un modèle de stock basé sur le principe de moyenne pondérée, dans lequel les sorties de stock correspondent à la valeur moyenne des articles reçus en stock au cours de la période de clôture du stock, plus le stock disponible éventuel de la période précédente."
author: AndersGirke
manager: AnnBe
ms.date: 10/25/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: InventJournalLossProfit, InventMarking, InventModelGroup, SalesTable
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, Operations, Retail
ms.custom: 65501
ms.assetid: 25041ff0-bafe-484d-a94a-e1772ad43204
ms.search.region: Global
ms.search.industry: Retail
ms.author: yuyus
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: ec7f1ef643d864a2729642d78d19fc43d5f6a7fb
ms.contentlocale: fr-fr
ms.lasthandoff: 04/13/2018

---

# <a name="weighted-average-with-physical-value-and-marking"></a>Moyenne pondérée avec valeur physique et marquage

[!INCLUDE [banner](../includes/banner.md)]

[!INCLUDE [retail name](../includes/retail-name.md)]

La moyenne pondérée est un modèle de stock basé sur le principe de moyenne pondérée, dans lequel les sorties de stock correspondent à la valeur moyenne des articles reçus en stock au cours de la période de clôture du stock, plus le stock disponible éventuel de la période précédente.

Lorsque vous exécutez une clôture de stock, toutes les réceptions sont réglées avec une sortie virtuelle, contenant la valeur et la quantité totales reçues. À cette sortie virtuelle correspond une réception virtuelle à partir de laquelle les sorties sont réglées. De cette manière, toutes les sorties obtiennent le même coût moyen. La sortie et la réception virtuelles peuvent être considérées comme un transfert virtuel, appelé « transfert de clôture du stock moyen pondéré ».

S'il n'existe qu'une seule réception, toutes les sorties peuvent être réglées à partir de celle-ci et le transfert virtuel n'est pas créé. 

Lorsque vous utilisez une moyenne pondérée, vous pouvez marquer les mouvements de stock de manière à régler une réception d'article spécifique avec une sortie spécifique au lieu d'utiliser la règle de moyenne pondérée. 

Si vous utilisez le modèle de stock de moyenne pondérée, nous vous recommandons une clôture de stock mensuelle. 

La méthode d'évaluation des stocks de moyenne pondérée est calculée grâce à la formule suivante :
-   Moyenne pondérée = (Q1\*P1 + Q2\*P2 + Qn\*Pn) / (Q1 + Q2 + Qn)

Les mouvements de sortie du stock, notamment les commandes client, les journaux de stock et les ordres de fabrication, s'effectuent à un prix de revient estimé à la date de la validation. Ce prix est également appelé prix de revient moyen en vigueur. Lors de la clôture de stock, le système analyse les mouvements de stock pour les périodes précédentes et pour la période actuelle et détermine lequel des principes de clôture suivants utiliser.
-   Règlement direct
-   Règlement récapitulatif

Les règlements correspondent à des validations de clôture du stock qui ajustent les sorties à la moyenne pondérée correcte depuis la date de clôture. Les exemples suivants illustrent l'impact du modèle de moyenne pondérée avec cinq configurations différentes :
-   Règlement direct à la moyenne pondérée sans l'option Inclure la valeur physique
-   Règlement récapitulatif à la moyenne pondérée sans l'option Inclure la valeur physique
-   Règlement direct à la moyenne pondérée avec l'option Inclure la valeur physique
-   Règlement récapitulatif à la moyenne pondérée avec l'option Inclure la valeur physique
-   Moyenne pondérée avec marquage

## <a name="weighted-average-direct-settlement-without-include-physical-value"></a>Règlement direct à la moyenne pondérée sans l'option Inclure la valeur physique
Le principe de règlement direct est le même que celui utilisé pour la moyenne pondérée dans les versions précédentes. Le système règle directement les réceptions avec les sorties. Le système utilise ce principe de règlement direct dans certaines situations spécifiques :
-   Une seule réception et une ou plusieurs sorties ont été validées au cours de la période
-   Seules des sorties ont été validées au cours de la période et le stock contient des articles disponibles d'une clôture précédente

Dans le scénario décrit dans les sections suivantes, une réception et une sortie mises à jour financièrement ont été validées. Pendant la clôture du stock, le système règle la réception directement avec la sortie et aucun ajustement au prix de revient n'est nécessaire pour la sortie. Les transactions suivantes sont illustrées dans le graphique.
-   1a. Réception physique en stock mise à jour pour une quantité de 5 à un coût de 10,00 EUR chacune
-   1b. Réception financière en stock mise à jour pour une quantité de 5 à un coût de 10,00 EUR chacune
-   2a. Sortie physique en stock mise à jour pour une quantité de 2 à un coût de 10,00 EUR chacune
-   2b. Sortie financière en stock mise à jour pour une quantité de 2 à un coût de 10,00 EUR chacune
-   3. La clôture du stock est effectuée à l'aide de la méthode de règlement direct permettant de régler la réception financière du stock avec la sortie financière du stock.

Le diagramme suivant illustre cette série de transactions avec les effets du choix du modèle de stock à moyenne pondérée et le principe de règlement direct sans l'option Inclure la valeur physique. 

![Règlement direct de moyenne pondérée sans Inclure la valeur physique](./media/weightedaveragedirectsettlementwithoutincludephysicalvalue.gif) 

**Clés du diagramme**
- Les mouvements de stock sont représentés par les flèches verticales.
- Les réceptions en stock sont représentées par les flèches verticales au-dessus de la ligne temporelle.
- Les sorties de stock sont représentées par les flèches verticales en dessous de la ligne temporelle.
- Au-dessus (ou en dessous) de chaque flèche verticale, la valeur du mouvement de stock est spécifiée au format Quantity@Unitprice.
- La valeur d'un mouvement de stock entre parenthèses indique que le mouvement de stock est physiquement validé dans le stock.
- La valeur d'un mouvement de stock sans parenthèses indique que le mouvement de stock est financièrement validé dans le stock.
- Chaque nouvelle transaction de réception ou de sortie est désignée par un nouveau libellé.
- Chaque flèche verticale est marquée par un identificateur séquentiel, comme *1a*. Les identificateurs indiquent l'ordre des validations des mouvements de stock sur la ligne temporelle.
- Les clôtures de stock sont représentées par une ligne pointillée verticale rouge et le libellé Clôture du stock.
- Les règlements effectués par clôture de stock sont représentés par des flèches rouges en pointillé, en diagonale, d'une réception vers une sortie.

## <a name="weighted-average-summarized-settlement-without-the-include-physical-value-option"></a>Règlement récapitulatif à la moyenne pondérée sans l'option Inclure la valeur physique
La moyenne pondérée se base sur le principe que toutes les réceptions d'une période de clôture sont résumées dans une transaction appelée Clôture de stock à moyenne pondérée. Toutes les réceptions d'une période sont réglées avec la sortie de la transaction de transfert de stock créée. Toutes les sorties de la période seront réglées avec la réception de la nouvelle transaction de transfert de stock. Si le stock disponible est positif après la clôture de stock, ce stock disponible et la valeur du stock sont résumés sur la nouvelle transaction de transfert de stock (réception). Si le stock disponible est négatif après la clôture de stock, le stock disponible et la valeur du stock correspondent à la somme des différentes sorties qui n'ont pas été complètement réglées. Dans le scénario ci-dessous, plusieurs réceptions et une sortie mises à jour financièrement ont été validées. 

Au cours de la clôture de stock, le système génère et valide la transaction de transfert de stock récapitulative et règle toutes les réceptions pour la période avec la transaction de sortie de transfert de stock récapitulative. Toutes les sorties validées de la période seront réglées avec la transaction de réception de transfert de stock récapitulative. La moyenne pondérée est calculée à 15,00 EUR. Dans la mesure où la sortie a initialement été validée avec un prix de revient estimé de 14,67 EUR, un ajustement négatif de 0,33 EUR est créé et validé sur la sortie. À partir de la date de clôture de stock, le stock disponible est de 3 pièces avec une valeur de 45,00 EUR. 

Les transactions suivantes sont illustrées dans le graphique ci-dessous :
-   1a. Réception physique en stock mise à jour pour une quantité de 2 à un coût de 11,00 EUR chacune.
-   1b. Réception financière en stock mise à jour pour une quantité de 2 à un coût de 14,00 EUR chacune.
-   2a. Réception physique en stock mise à jour pour une quantité de 1 à un coût de 12,00 EUR chacune.
-   2b. Réception financière en stock mise à jour pour une quantité de 1 à un coût de 16,00 EUR chacune.
-   3a. Sortie physique de stock mise à jour pour une quantité de 1 à un coût de 14,67 EUR chacune (prix de revient moyen en vigueur).
-   3b. Sortie financière de stock mise à jour pour une quantité de 1 à un coût de 14,67 EUR chacune (prix de revient moyen en vigueur).
-   4a. Réception physique en stock mise à jour pour une quantité de 1 à un coût de 14,00 EUR chacune.
-   4b. Réception financière en stock pour une quantité de 1 à un coût de 16,00 EUR chacune.
-   5. La clôture du stock est effectuée.
-   6a. La sortie financière de transaction de clôture de stock à moyenne pondérée est créée pour récapituler les règlements de toutes les réceptions financières du stock.
-   6b. La réception financière de transaction de clôture de stock à moyenne pondérée est créée comme contrepartie de 5a.

Le diagramme suivant illustre cette série de transactions avec les effets du choix du modèle de stock à moyenne pondérée et le principe de règlement récapitulatif sans l'option Inclure la valeur physique. 

![Règlement récapitulatif de moyenne pondérée sans Inclure la valeur physique](./media/weightedaveragesummarizedsettlementwithoutincludephysicalvalue.gif) 

**Clés du diagramme**
- Les mouvements de stock sont représentés par les flèches verticales.
- Les réceptions en stock sont représentées par les flèches verticales au-dessus de la ligne temporelle.
- Les sorties de stock sont représentées par les flèches verticales en dessous de la ligne temporelle.
- Au-dessus (ou en dessous) de chaque flèche verticale, la valeur du mouvement de stock est spécifiée au format Quantity@Unitprice.
- La valeur d'un mouvement de stock entre parenthèses indique que le mouvement de stock est physiquement validé dans le stock.
- La valeur d'un mouvement de stock sans parenthèses indique que le mouvement de stock est financièrement validé dans le stock.
- Chaque nouvelle transaction de réception ou de sortie est désignée par un nouveau libellé.
- Chaque flèche verticale est marquée par un identificateur séquentiel, comme *1a*. Les identificateurs indiquent l'ordre des validations des mouvements de stock sur la ligne temporelle.
- Les clôtures de stock sont représentées par une ligne pointillée verticale rouge et le libellé Clôture du stock.
- Les règlements effectués par clôture de stock sont représentés par des flèches rouges en pointillé, en diagonale, d'une réception vers une sortie.
- Les flèches rouges illustrent les transactions de réception réglées avec la transaction de sortie créées par le système.
- La flèche verte représente la transaction de réception générée par le système de contrepartie avec laquelle la transaction de sortie validée est réglée.

## <a name="weighted-average-direct-settlement-with-the-include-physical-value-option"></a>Règlement direct à la moyenne pondérée avec l'option Inclure la valeur physique
Le paramètre Inclure la valeur physique fonctionne différemment par rapport au modèle de stock de moyenne pondérée des versions précédentes du produit. Activez la case à cocher Inclure la valeur physique pour un article dans l'écran Groupe de modèles d'article. Par la suite, le système utilisera les réceptions mises à jour physiquement lors du calcul du prix de revient estimé, ou moyen en vigueur. Les sorties sont validées sur la base de ce prix de revient estimé au cours de la période. Lors de la clôture du stock, seules les réceptions mises à jour financièrement seront prises en compte dans le calcul de la moyenne pondérée. Si vous utilisez le modèle de stock de moyenne pondérée, nous vous recommandons une clôture de stock mensuelle. Dans cet exemple de règlement direct à la moyenne pondérée, le groupe de modèles d'articles est marqué pour inclure la valeur physique. 

Les transactions suivantes sont illustrées dans le graphique ci-dessous :
-   1a. Réception physique en stock mise à jour pour une quantité de 1 à un coût de 11,00 EUR chacune.
-   1b. Réception financière en stock mise à jour pour une quantité de 1 à un coût de 10,00 EUR chacune.
-   2a. Réception physique en stock mise à jour pour une quantité de 1 à un coût de 15,00 EUR chacune.
-   3a. Sortie physique de stock mise à jour pour une quantité de 1 à un coût de 12,50 EUR chacune (prix de revient moyen en vigueur, dans la mesure où la valeur de la réception physique est prise en considération).
-   3b. Sortie financière de stock mise à jour pour une quantité de 1 à un coût de 12,50 EUR chacune (prix de revient moyen en vigueur, dans la mesure où la valeur de la réception physique est prise en considération).
-   4. La clôture du stock est effectuée. Au cours de la clôture de stock, le système ignore tous les mouvements de stock qui ont uniquement été mis à jour physiquement. À la place, le principe de règlement direct est utilisé car une seule réception financière existe. Un ajustement de 2,50 EUR est validé dans le mouvement de stock qui a été sorti financièrement à partir de la date de clôture du stock. Après la clôture du stock, le stock disponible aura la quantité 1 avec un prix de revient moyen en vigueur de 15,00 EUR.

Le diagramme suivant illustre cette série de transactions avec les effets du choix du modèle de stock à moyenne pondérée et le principe de règlement direct avec l'option Inclure la valeur physique. 

![Règlement direct de moyenne pondérée avec Inclure la valeur physique](./media/weightedaveragedirectsettlementwithincludephysicalvalue.gif) 

**Clés du diagramme**
- Les mouvements de stock sont représentés par les flèches verticales.
- Les réceptions en stock sont représentées par les flèches verticales au-dessus de la ligne temporelle.
- Les sorties de stock sont représentées par les flèches verticales en dessous de la ligne temporelle.
- Au-dessus (ou en dessous) de chaque flèche verticale, la valeur du mouvement de stock est spécifiée au format Quantity@Unitprice.
- La valeur d'un mouvement de stock entre parenthèses indique que le mouvement de stock est physiquement validé dans le stock.
- La valeur d'un mouvement de stock sans parenthèses indique que le mouvement de stock est financièrement validé dans le stock.
- Chaque nouvelle transaction de réception ou de sortie est désignée par un nouveau libellé.
- Chaque flèche verticale est marquée par un identificateur séquentiel, comme *1a*. Les identificateurs indiquent l'ordre des validations des mouvements de stock sur la ligne temporelle.
- Les clôtures de stock sont représentées par une ligne pointillée verticale rouge et le libellé Clôture du stock.
- Les règlements effectués par clôture de stock sont représentés par des flèches rouges en pointillé, en diagonale, d'une réception vers une sortie.

## <a name="weighted-average-summarized-settlement-with-the-include-physical-value-option"></a>Règlement récapitulatif à la moyenne pondérée avec l'option Inclure la valeur physique
Dans cette version de , le paramètre Inclure la valeur physique fonctionne différemment par rapport au modèle de stock de moyenne pondérée des versions précédentes du programme. Activez la case à cocher Inclure la valeur physique pour un article dans la page Groupe de modèles d'article. Par la suite, le système utilisera les réceptions mises à jour physiquement lors du calcul du prix de revient estimé, ou moyen en vigueur. Les sorties sont validées sur la base de ce prix de revient estimé au cours de la période. Lors de la clôture du stock, seules les réceptions mises à jour financièrement seront prises en compte dans le calcul de la moyenne pondérée. Si vous utilisez le modèle de stock de moyenne pondérée, nous vous recommandons une clôture de stock mensuelle. Dans cet exemple de règlement récapitulatif à la moyenne pondérée, le groupe de modèles de stock est marqué pour inclure la valeur physique. 

Les transactions suivantes sont illustrées dans le graphique ci-dessous :
-   1a. Réception physique en stock mise à jour pour une quantité de 2 à un coût de 11,00 EUR chacune.
-   1b. Réception financière en stock mise à jour pour une quantité de 2 à un coût de 14,00 EUR chacune.
-   2. Réception physique en stock mise à jour pour une quantité de 1 à un coût de 10,00 EUR chacune.
-   3a. Réception physique en stock mise à jour pour une quantité de 1 à un coût de 12,00 EUR chacune.
-   3b. Réception financière en stock pour une quantité de 1 à un coût de 16,00 EUR chacune.
-   4a. Sortie physique de stock mise à jour pour une quantité de 1 à un coût de 13,50 EUR chacune (prix de revient moyen en vigueur, dans la mesure où la valeur de la réception physique est prise en considération).
-   4b. Sortie financière de stock mise à jour pour une quantité de 1 à un coût de 13,50 EUR chacune (prix de revient moyen en vigueur, dans la mesure où la valeur de la réception physique est prise en considération).
-   5a. Réception physique en stock mise à jour pour une quantité de 1 à un coût de 14,00 EUR chacune.
-   5b. Réception financière en stock pour une quantité de 1 à un coût de 16,00 EUR chacune.
-   6. La clôture du stock est effectuée. Au cours de la clôture de stock, le système ignore tous les mouvements de stock qui sont uniquement mis à jour physiquement. Le principe de règlement récapitulatif est utilisé car une seule réception financière existe. Un ajustement de 1,50 EUR est validé dans le mouvement de stock qui a été sorti financièrement à partir de la date de clôture du stock. Après la clôture du stock, le stock disponible aura la quantité 3 avec un prix de revient moyen en vigueur de 15,00 EUR.
-   7a. La sortie financière de transaction de clôture de stock à moyenne pondérée est créée pour récapituler les règlements de toutes les réceptions financières du stock.
-   7b. La réception financière de transaction de clôture de stock à moyenne pondérée est créée comme contrepartie de 5a.

Le diagramme suivant illustre cette série de transactions avec les effets du choix du modèle de stock à moyenne pondérée et le principe de règlement récapitulatif sans l'option Inclure la valeur physique. 

![Règlement récapitulatif de moyenne pondérée avec Inclure la valeur physique](./media/weightedaveragesummarizedsettlementwithincludephysicalvalue.gif) 

**Clés du diagramme**
- Les mouvements de stock sont représentés par les flèches verticales.
- Les réceptions en stock sont représentées par les flèches verticales au-dessus de la ligne temporelle.
- Les sorties de stock sont représentées par les flèches verticales en dessous de la ligne temporelle.
- Au-dessus (ou en dessous) de chaque flèche verticale, la valeur du mouvement de stock est spécifiée au format Quantity@Unitprice.
- La valeur d'un mouvement de stock entre parenthèses indique que le mouvement de stock est physiquement validé dans le stock.
- La valeur d'un mouvement de stock sans parenthèses indique que le mouvement de stock est financièrement validé dans le stock.
- Chaque nouvelle transaction de réception ou de sortie est désignée par un nouveau libellé.
- Chaque flèche verticale est marquée par un identificateur séquentiel, comme 1a. Les identificateurs indiquent l'ordre des validations des mouvements de stock sur la ligne temporelle.
- Les clôtures de stock sont représentées par une ligne pointillée verticale rouge et le libellé Clôture du stock.
- Les règlements effectués par clôture de stock sont représentés par des flèches rouges en pointillé, en diagonale, d'une réception vers une sortie.
- Les flèches rouges illustrent les transactions de réception réglées avec la transaction de sortie créées par le système.
- La flèche verte représente la transaction de réception générée par le système de contrepartie avec laquelle la transaction de sortie validée est réglée.

## <a name="weighted-average-with-marking"></a>Moyenne pondérée avec marquage
Le marquage est un processus qui vous permet de lier, ou de marquer, une transaction de sortie à une transaction de réception. Cette opération peut être effectuée avant ou après la validation d'une transaction. Vous pouvez utiliser le marquage si vous voulez être sûr du coût exact du stock lors de la validation de la transaction ou de l'exécution de la clôture de stock. 

Par exemple, votre service à la clientèle a accepté une commande urgente d'un client important. Puisqu'il s'agit d'une commande urgente, vous devrez payer plus cher pour cet article pour satisfaire la demande de votre client. Vous devez être certain que le coût de cet article en stock se reflètera dans la marge, ou le coût des marchandises vendues, pour la facture de cette commande client. 

Lorsque la commande fournisseur est validée, le stock est reçu à un coût de 120,00 EUR. Par exemple, ce document de commande client est marqué par rapport à la commande fournisseur avant la validation du bon de livraison ou de la facture. Le coût des marchandises vendues sera donc de 120,00 EUR au lieu du coût moyen en vigueur de l'article. Si le bon de livraison ou la facture de la commande client est validée avant le marquage, le coût des marchandises vendues sera validé au prix de revient moyen en vigueur. 

Avant d'exécuter la clôture de stock, ces deux transactions peuvent encore être marquées l'une par rapport à l'autre. 

Une transaction de réception est marquée par rapport à une transaction de sortie. La méthode d'évaluation sélectionnée pour le groupe de modèles de stock de l'article est ignorée et le système règle ces transactions les unes avec les autres. 

Vous pouvez marquer une transaction de sortie par rapport à une réception avant la validation de la transaction. Vous pouvez le faire à partir d'une ligne de commande client dans la page Détails de la commande client. Les transactions de réception en cours sont affichées dans la page Marquage. 

Vous pouvez marquer une transaction de sortie par rapport à une réception après la validation de la transaction. Vous pouvez faire correspondre ou marquer une transaction de sortie par rapport à une transaction de réception en cours pour un article inventorié dans un journal d'ajustement de stock validé. 

Les transactions suivantes sont illustrées dans le graphique ci-dessous :
-   1a. Réception physique en stock pour une quantité de 1 à un coût de 10,00 EUR chacune.
-   1b. Réception financière en stock pour une quantité de 1 à un coût de 10,00 EUR chacune.
-   2a. Réception physique en stock pour une quantité de 1 à un coût de 20,00 EUR chacune.
-   2b. Réception financière en stock pour une quantité de 1 à un coût de 20,00 EUR chacune.
-   3a. Réception physique en stock pour une quantité de 1 à un coût de 25,00 EUR chacune.
-   4a. Réception physique en stock pour une quantité de 1 à un coût de 30,00 EUR chacune.
-   4b. Réception financière en stock pour une quantité de 1 à un coût de 30,00 EUR chacune.
-   5a. Sortie physique de stock pour une quantité de 1 à un prix de revient de 21,25 EUR (prix de revient moyen en vigueur des transactions mises à jour financièrement et physiquement).
-   5b. La sortie financière de stock pour une quantité de 1 est marquée par rapport à la réception en stock 2b avant la validation de la transaction. Cette transaction est validée avec un prix de revient de 20,00 EUR.
-   6a. Sortie physique de stock pour une quantité de 1 à un prix de revient de 21,25 EUR chacune.
-   7. La clôture du stock est effectuée. Étant donné que la transaction mise à jour financièrement est marquée par rapport à une réception existante, ces transactions sont réglées les unes avec les autres et aucun ajustement n'est effectué.

Le nouveau prix de revient moyen en vigueur reflète la moyenne des transactions mises à jour financièrement et physiquement à 27,50 EUR. 

Le diagramme suivant illustre cette série de transactions avec les effets du choix du modèle de stock de moyenne pondérée avec marquage. 

![Moyenne pondérée avec marquage](./media/weightedaveragewithmarking.gif) 

**Clés du diagramme**
- Les mouvements de stock sont représentés par les flèches verticales.
- Les réceptions en stock sont représentées par les flèches verticales au-dessus de la ligne temporelle.
- Les sorties de stock sont représentées par les flèches verticales en dessous de la ligne temporelle.
- Au-dessus (ou en dessous) de chaque flèche verticale, la valeur du mouvement de stock est spécifiée au format Quantité@"Unitprice".
- La valeur d'un mouvement de stock entre parenthèses indique que le mouvement de stock est physiquement validé dans le stock.
- La valeur d'un mouvement de stock sans parenthèses indique que le mouvement de stock est financièrement validé dans le stock.
- Chaque nouvelle transaction de réception ou de sortie est désignée par un nouveau libellé.
- Chaque flèche verticale est marquée par un identificateur séquentiel, comme *1a*. Les identificateurs indiquent l'ordre des validations des mouvements de stock sur la ligne temporelle.
- Les clôtures de stock sont représentées par une ligne pointillée verticale rouge et le libellé Clôture du stock.
- Les règlements effectués par clôture de stock sont représentés par des flèches rouges en pointillé, en diagonale, d'une réception vers une sortie.






