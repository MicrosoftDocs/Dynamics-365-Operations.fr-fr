---
title: Date moyenne pondérée
description: La date moyenne pondérée est un modèle de stock basé sur le principe de moyenne pondérée, dans lequel les sorties de stock correspondent à la valeur moyenne des articles reçus en stock pour chaque jour de la période de clôture du stock.
author: AndersGirke
ms.date: 10/25/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: InventJournalLossProfit, InventMarking, InventModelGroup, SalesTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: 28991
ms.assetid: 945d5088-a99d-4e54-bc42-d2bd61c61e22
ms.search.region: Global
ms.search.industry: Retail
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 563fa291754f7f795fa64d530de49b9fe4083c56
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5821295"
---
# <a name="weighted-average-date"></a>Date moyenne pondérée

[!include [banner](../includes/banner.md)]

La date moyenne pondérée est un modèle de stock basé sur le principe de moyenne pondérée. Concernant le principe de la moyenne pondérée, les sorties de stock correspondent à la valeur moyenne des articles reçus en stock pour chaque jour de la période de clôture du stock. 

Lorsque vous exécutez une clôture de stock avec une date moyenne pondérée, toutes les réceptions quotidiennes sont réglées avec une sortie virtuelle. Celle-ci contient la quantité totale reçue et la valeur pour cette journée. À cette sortie virtuelle correspond une réception virtuelle à partir de laquelle les sorties seront réglées. De cette manière, toutes les sorties obtiennent le même coût moyen. La sortie et la réception virtuelles peuvent être considérées comme un transfert virtuel appelé *transfert de clôture du stock moyen pondéré*. 

Si une seule réception a été effectuée à cette date ou précédemment, il n’est pas nécessaire d’évaluer la moyenne. Cela est dû au fait que toutes les sorties sont réglées à partir de celle-ci et que le transfert virtuel n’est pas créé. De même, si seules des sorties ont lieu à cette date, il n’existe aucune réception à partir de laquelle évaluer la moyenne, et le transfert virtuel n’est pas créé. Lorsque vous utilisez une moyenne pondérée, vous pouvez marquer les mouvements de stock de manière ce qu’une réception d’article spécifique soit réglée avec une sortie spécifique. Cela signifie que vous n’utilisez pas la règle de date moyenne pondérée. Si vous utilisez le modèle de stock de date moyenne pondérée, nous vous recommandons une clôture de stock mensuelle. 

La formule suivante est utilisée pour calculer la méthode d’évaluation des coûts de date moyenne pondérée : 

Moyenne pondérée = (\[Q1 × P1\] + \[Q2 × P2\] + \[Q *n* × P *n*\]) ÷ (Q1 + Q2 + Q *n*) 

Pendant la clôture du stock, le calcul est exécuté quotidiennement via la période de clôture, comme montré dans l’illustration suivante. 

![Modèle de calcul quotidien de date moyenne pondérée](./media/weightedaveragedatedailycalculationmodel.gif) 

Les mouvements de sortie du stock, notamment les commandes client, les journaux de stock, les avoirs sur achat et les ordres de fabrication, sont effectués à un prix de revient estimé à la date de validation. Ce prix de revient estimé est également appelé prix de revient moyen en cours. À la date de la clôture de stock, le système analyse les mouvements de stock des périodes précédentes, des jours précédents et du jour actuel. Cette analyse vise à déterminer les principes de clôture suivants à utiliser :

-   Règlement direct
-   Règlement récapitulatif

Les règlements correspondent à des validations de clôture du stock qui ajustent les sorties à la moyenne pondérée correcte depuis la date de clôture. 

**Remarque :** pour plus d’informations sur les règlements, voir l’article concernant la clôture de stock. Les exemples suivants illustrent l’impact du modèle de moyenne pondérée avec cinq configurations :

-   Règlement direct à la date moyenne pondérée sans l’option **Inclure la valeur physique**
-   Règlement récapitulatif à la date moyenne pondérée sans l’option **Inclure la valeur physique**
-   Règlement direct à la date moyenne pondérée avec l’option **Inclure la valeur physique**
-   Règlement récapitulatif à la date moyenne pondérée avec l’option **Inclure la valeur physique**
-   Date moyenne pondérée avec marquage

## <a name="weighted-average-date-direct-settlement-when-the-include-physical-value-option-isnt-used"></a>Règlement direct à la date moyenne pondérée sans l’option Inclure la valeur physique
Le principe de règlement direct utilisé dans la version actuelle est le même que celui utilisé pour la moyenne pondérée dans les versions précédentes. Le système règle directement les réceptions avec les sorties. Le système utilise ce principe de règlement direct dans certaines situations spécifiques :

-   Une seule réception et une ou plusieurs sorties ont été validées au cours de la période
-   Seules des sorties ont été validées au cours de la période et le stock contient des articles disponibles d’une clôture précédente.

Dans le scénario ci-dessous, une réception et une sortie mises à jour financièrement ont été validées. Pendant la clôture du stock, le système règle la réception directement avec la sortie et aucun ajustement au prix de revient n’est nécessaire pour la sortie. 

Les transactions suivantes sont illustrées dans le graphique ci-dessous :

-   1a. Réception physique en stock mise à jour pour une quantité de 5 à un coût de 10,00 EUR chacune.
-   1b. Réception financière en stock mise à jour pour une quantité de 5 à un coût de 10,00 EUR chacune.
-   2a. Sortie physique de stock mise à jour pour une quantité de 2 à un coût de 10,00 EUR chacune.
-   2b. Sortie financière de stock mise à jour pour une quantité de 2 à un coût de 10,00 EUR chacune.
-   3. La clôture du stock est effectuée à l’aide de la méthode de règlement direct permettant de régler la réception financière du stock avec la sortie financière du stock.

![Règlement direct à la date moyenne pondérée sans l’option Inclure la valeur physique](./media/weightedaveragedatedirectsettlementwithoutincludephysicalvalue.gif) 

**Clé à l’illustration :**

-   Les mouvements de stock sont représentés par les flèches verticales.
-   Les réceptions en stock sont représentées par les flèches verticales au-dessus de la ligne temporelle.
-   Les sorties de stock sont représentées par les flèches verticales en dessous de la ligne temporelle.
-   Au-dessus (ou en dessous) de chaque flèche verticale, la valeur du mouvement de stock est spécifiée sous la forme *Quantité*@*Prix unitaire*.
-   La valeur d’un mouvement de stock entre parenthèses indique que le mouvement de stock est physiquement validé dans le stock.
-   La valeur d’un mouvement de stock sans parenthèses indique que le mouvement de stock est financièrement validé dans le stock.
-   Chaque nouvelle transaction de réception ou de sortie est désignée par un nouveau libellé.
-   Chaque flèche verticale est marquée par un identificateur séquentiel, comme *1a*. Les identificateurs indiquent l’ordre des validations des mouvements de stock sur la ligne temporelle.
-   Les clôtures de stock sont représentées par une ligne pointillée verticale rouge et le libellé *Clôture du stock*.
-   Les règlements effectués par clôture de stock sont représentés par des flèches rouges en pointillé, en diagonale, d’une réception vers une sortie.

## <a name="weighted-average-date-summarized-settlement-when-the-include-physical-value-option-isnt-used"></a>Règlement récapitulatif à la date moyenne pondérée sans l’option Inclure la valeur physique
La moyenne pondérée se base sur le principe que toutes les réceptions d’une période de clôture sont résumées dans une nouvelle transaction de transfert de stock. Cette transaction est nommée C *lôture de stock à moyenne pondérée*. Toutes les réceptions d’un jour sont réglées avec la sortie de la transaction de transfert de stock créée. Toutes les sorties d’un jour sont réglées avec la réception de la transaction de transfert de stock créée. Si le stock disponible est positif après la clôture de stock, ce stock disponible et la valeur du stock sont résumés sur la nouvelle transaction de transfert de stock (réception). Si le stock disponible est négatif après la clôture de stock, le stock disponible et la valeur du stock correspondent à la somme des différentes sorties qui n’ont pas été complètement réglées. 

Dans le scénario ci-dessous, plusieurs réceptions et sorties mises à jour financièrement ont été validées au cours de la période. Lors de la clôture du stock, le système évalue chaque jour afin de déterminer comment traiter chacun à la clôture. 

Les transactions suivantes sont illustrées dans le graphique ci-dessous : 

**Jour 1:**

-   1a. Réception physique en stock mise à jour pour une quantité de 3 à un coût de 15,00 EUR chacune.
-   1b. Réception financière en stock mise à jour pour une quantité de 3 à un coût de 15,00 EUR chacune.
-   2a. Sortie physique de stock pour une quantité de 1 à un coût moyen en vigueur de 15,00 EUR.
-   2b. Sortie financière de stock pour une quantité de 1 à un coût moyen en vigueur de 15,00 EUR.

Le système utilise l’approche de règlement direct pour le jour 1. 

**Jour 2:**

-   3a. Sortie physique de stock pour une quantité de 1 à un coût moyen en vigueur de 15,00 EUR.
-   3b. Sortie financière de stock pour une quantité de 1 à un coût moyen en vigueur de 15,00 EUR.

Le système utilise l’approche de règlement direct pour le jour 2. 

**Jour 3:**

-   4a. Sortie physique de stock pour une quantité de 1 à un coût moyen en vigueur de 15,00 EUR.
-   4b. Sortie financière de stock pour une quantité de 1 à un coût moyen en vigueur de 15,00 EUR.
-   5a. Réception physique en stock pour une quantité de 1 à un coût de 17,00 EUR chacune.
-   5b. Réception financière en stock pour une quantité de 1 à un coût de 17,00 EUR chacune.

La clôture du stock est effectuée. Le règlement direct devra être utilisé car plusieurs réceptions concernent plusieurs jours.

-   7a. Une sortie financière de transaction de clôture de stock à moyenne pondérée est créée pour une quantité de 2 à un coût de 32,00 EUR pour récapituler les règlements de toutes les réceptions financières du stock qui n’ont pas encore été clôturées.
-   7b. Une réception financière de transaction de clôture de stock à moyenne pondérée est créée comme contrepartie à 7a.

Le système génère et valide la transaction de transfert de stock récapitulative. De même, le système règle toutes les réceptions de la journée et le stock disponible des jours précédents avec la transaction de sortie de transfert de stock récapitulative. Toutes les sorties du jour seront réglées avec la transaction de réception de transfert de stock récapitulative. Le prix de revient à moyenne pondérée est calculé à 16,00 EUR. La sortie aura un ajustement de 1,00 EUR afin de l’ajuster au coût à moyenne pondérée. Le nouveau prix de revient moyen en vigueur est de 16,00 EUR. 

Le diagramme suivant illustre cette série de transactions avec les effets du choix du modèle de stock à moyenne pondérée et le principe de règlement récapitulatif sans l’option **Inclure la valeur physique**. 

![Règlement récapitulatif à la date moyenne pondérée sans l’option Inclure la valeur physique](./media/weightedaveragedatesummarizedsettlementwithoutincludephysicalvalue.gif) 

**Clé à l’illustration :**

-   Les mouvements de stock sont représentés par les flèches verticales.
-   Les réceptions en stock sont représentées par les flèches verticales au-dessus de la ligne temporelle.
-   Les sorties de stock sont représentées par les flèches verticales en dessous de la ligne temporelle.
-   Au-dessus (ou en dessous) de chaque flèche verticale, la valeur du mouvement de stock est spécifiée sous la forme *Quantité*@*Prix unitaire*.
-   La valeur d’un mouvement de stock entre parenthèses indique que le mouvement de stock est physiquement validé dans le stock.
-   La valeur d’un mouvement de stock sans parenthèses indique que le mouvement de stock est financièrement validé dans le stock.
-   Chaque nouvelle transaction de réception ou de sortie est désignée par un nouveau libellé.
-   Chaque flèche verticale est marquée par un identificateur séquentiel, comme *1a*. Les identificateurs indiquent l’ordre des validations des mouvements de stock sur la ligne temporelle.
-   Les clôtures de stock sont représentées par une ligne pointillée verticale rouge et le libellé *Clôture du stock*.
-   Les règlements effectués par clôture de stock sont représentés par des flèches rouges en pointillé, en diagonale, d’une réception vers une sortie.
-   Les flèches diagonales de couleur rouge illustrent les transactions de réception réglées avec la transaction de sortie créées par le système.
-   La flèche diagonale de couleur verte représente la transaction de réception générée par le système de contrepartie avec laquelle la transaction de sortie validée est réglée.

## <a name="weighted-average-date-direct-settlement-when-the-include-physical-value-option-is-used"></a>Règlement direct à la date moyenne pondérée avec l’option Inclure la valeur physique
Le principe de règlement direct utilisé pour la date moyenne pondérée dans la version actuelle est le même que celui utilisé dans les versions précédentes. Le système règle directement les réceptions avec les sorties. Le système utilise ce principe de règlement direct dans certaines situations spécifiques :

-   Une seule réception et une ou plusieurs sorties ont été validées au cours de la période
-   Seules des sorties ont été validées au cours de la période et le stock contient un stock disponible d’une clôture précédente.

Si vous cochez la case **Inclure la valeur physique** pour un article sur la page **Groupe de modèles d’article**, le système utilise les réceptions mises à jour physiquement lors du calcul du prix de revient estimé, ou moyen en vigueur. Les sorties sont validées sur la base de ce prix de revient estimé au cours de la période. Lors de la clôture du stock, seules les réceptions mises à jour financièrement seront prises en compte dans le calcul de la moyenne pondérée.

## <a name="weighted-average-date-summarized-settlement-when-the-include-physical-value-option-is-used"></a>Règlement récapitulatif à la date moyenne pondérée avec l’option Inclure la valeur physique
Si vous cochez la case **Inclure la valeur physique** pour un article sur la page **Groupe de modèles d’article**, le système utilise les réceptions mises à jour physiquement lors du calcul du prix de revient estimé, ou moyen en vigueur. Les sorties sont validées sur la base de ce prix de revient estimé au cours de la période. Lors de la clôture du stock, seules les réceptions mises à jour financièrement seront prises en compte dans le calcul de la moyenne pondérée. Le règlement de la moyenne pondérée se base sur le principe selon lequel les réceptions d’une période de clôture sont résumées dans une nouvelle transaction de transfert de stock nommée *Clôture de stock à moyenne pondérée*. Toutes les réceptions d’un jour sont réglées avec la sortie de la transaction de transfert de stock créée. Toutes les sorties d’un jour sont réglées avec la réception de la transaction de transfert de stock créée. Si le stock disponible est positif après la clôture de stock, ce stock disponible et la valeur du stock sont résumés sur la nouvelle transaction de transfert de stock (réception). Si le stock disponible est négatif après la clôture de stock, le stock disponible et la valeur du stock correspondent à la somme des différentes sorties qui n’ont pas été complètement réglées.

## <a name="weighted-average-date-when-marking-is-used"></a>Date moyenne pondérée avec marquage
Le marquage est un processus qui vous permet de lier une transaction de sortie à une transaction de réception. Cette opération peut être effectuée avant ou après la validation d’une transaction. Vous pouvez utiliser le marquage si vous voulez être sûr du coût exact du stock lors de la validation de la transaction ou de l’exécution de la clôture de stock. 

Par exemple, votre service à la clientèle a accepté une commande urgente d’un client important. Puisqu’il s’agit d’une commande urgente, vous devrez payer plus cher pour cet article pour satisfaire la demande de votre client. Vous devez être certain que le coût de cet article en stock se reflètera dans la marge, ou le coût des marchandises vendues, pour la facture de cette commande client. Lorsque la commande fournisseur est validée, le stock est reçu à un coût de 120,00 EUR. Le document de commande client est marqué par rapport à la commande fournisseur avant la validation du bon de livraison ou de la facture. Le coût des marchandises vendues sera donc de 120,00 EUR au lieu du coût moyen en vigueur de l’article. Si le bon de livraison ou la facture de la commande client est validée avant le marquage, le coût des marchandises vendues sera validé au prix de revient moyen en vigueur. Avant d’exécuter la clôture de stock, ces deux transactions peuvent encore être marquées l’une par rapport à l’autre. Lorsqu’une transaction de réception correspond à une transaction de sortie, la méthode d’évaluation définie dans le groupe de modèles de stock de l’article est ignorée. Au lieu de cela, le système règle ces transactions les unes avec les autres. 

Vous pouvez marquer une transaction de sortie par rapport à une réception avant la validation de la transaction. Vous pouvez le faire à partir d’une ligne de commande client dans la page **Détails de la commande client**. Les transactions de réception en cours sont affichées sur la page **Marquage**. Vous pouvez marquer une transaction de sortie par rapport à une réception après la validation de la transaction. Vous pouvez faire correspondre ou marquer une transaction de sortie par rapport à une transaction de réception en cours pour un article inventorié dans un journal d’ajustement de stock validé. Les transactions suivantes sont illustrées dans le graphique ci-dessous :

-   1a. Réception physique en stock pour une quantité de 1 à un prix de revient de 10,00 EUR chacune.
-   1b. Réception financière en stock pour une quantité de 1 à un prix de revient de 10,00 EUR chacune.
-   2a. Réception physique en stock pour une quantité de 1 à un prix de revient de 20,00 EUR chacune.
-   2b. Réception financière en stock pour une quantité de 1 à un prix de revient de 20,00 EUR chacune.
-   3a. Réception physique en stock pour une quantité de 1 à un prix de revient de 25,00 EUR chacune.
-   4a. Réception physique en stock pour une quantité de 1 à un prix de revient de 30,00 EUR chacune.
-   4b. Réception financière en stock pour une quantité de 1 à un prix de revient de 30,00 EUR chacune.
-   5a. Sortie physique de stock pour une quantité de 1 à un prix de revient de 21,25 EUR (prix de revient moyen en vigueur des transactions mises à jour financièrement et physiquement).
-   5b. La sortie financière de stock pour une quantité de 1 est marquée par rapport à la réception en stock 2b avant la validation de la transaction. Cette transaction est validée à un prix de revient de 20,00 EUR.
-   6a. Sortie physique de stock pour une quantité de 1 à un prix de revient de 21,25 EUR.
-   7. La clôture du stock est effectuée. Étant donné que la transaction mise à jour financièrement est marquée par rapport à une réception existante, ces transactions sont réglées les unes avec les autres et aucun ajustement n’est effectué.

Le nouveau prix de revient moyen en vigueur reflète la moyenne des transactions mises à jour financièrement et physiquement à 27,50 EUR. Le diagramme suivant illustre cette série de transactions avec les effets du choix du modèle de stock de moyenne pondérée avec marquage.

![date moyenne pondérée avec marquage.](./media/weightedaveragedatewithmarking.gif) 

**Clé à l’illustration :**

-   Les mouvements de stock sont représentés par les flèches verticales.
-   Les réceptions en stock sont représentées par les flèches verticales au-dessus de la ligne temporelle.
-   Les sorties de stock sont représentées par les flèches verticales en dessous de la ligne temporelle.
-   Au-dessus (ou en dessous) de chaque flèche verticale, la valeur du mouvement de stock est spécifiée sous la forme *Quantité*@*Prix unitaire*.
-   La valeur d’un mouvement de stock entre parenthèses indique que le mouvement de stock est physiquement validé dans le stock.
-   La valeur d’un mouvement de stock sans parenthèses indique que le mouvement de stock est financièrement validé dans le stock.
-   Chaque nouvelle transaction de réception ou de sortie est désignée par un nouveau libellé.
-   Chaque flèche verticale est marquée par un identificateur séquentiel, comme *1a*. Les identificateurs indiquent l’ordre des validations des mouvements de stock sur la ligne temporelle.
-   Les clôtures de stock sont représentées par une ligne pointillée verticale rouge et le libellé *Clôture du stock*.
-   Les règlements effectués par clôture de stock sont représentés par des flèches rouges en pointillé, en diagonale, d’une réception vers une sortie.






[!INCLUDE[footer-include](../../includes/footer-banner.md)]