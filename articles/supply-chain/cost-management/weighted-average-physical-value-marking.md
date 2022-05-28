---
title: Moyenne pondérée avec valeur physique et marquage
description: La moyenne pondérée est un modèle de stock basé sur le principe de moyenne pondérée, dans lequel les sorties de stock correspondent à la valeur moyenne des articles reçus en stock au cours de la période de clôture du stock, plus le stock disponible éventuel de la période précédente.
author: JennySong-SH
ms.date: 02/21/2022
ms.topic: article
ms.search.form: InventJournalLossProfit, InventMarking, InventModelGroup, SalesTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: 65501
ms.search.region: Global
ms.author: yanansong
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 41c80dcdc08432bb68478827c8763735e644aa4a
ms.sourcegitcommit: 9166e531ae5773f5bc3bd02501b67331cf216da4
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/03/2022
ms.locfileid: "8675261"
---
# <a name="weighted-average-with-physical-value-and-marking"></a>Moyenne pondérée avec valeur physique et marquage

[!include [banner](../includes/banner.md)]

La moyenne pondérée est un modèle d’inventaire basé sur une moyenne qui résulte de la multiplication de chaque composant (transaction article) par un facteur (prix de revient) reflétant son importance (quantité). Une autre façon de dire cela est que la moyenne pondérée est un modèle d’inventaire qui attribue le coût des transactions d’émission en fonction de la valeur moyenne de tous les stocks reçus au cours de la période, plus tout stock disponible de la période précédente.

Lorsque vous exécutez une clôture de stock à l’aide du modèle de stock moyen pondéré, il existe deux façons de créer un règlement. En général, toutes les réceptions sont réglées avec une sortie virtuelle, contenant la valeur et la quantité totales reçues. À cette sortie virtuelle correspond une réception virtuelle à partir de laquelle les sorties sont réglées. De cette manière, toutes les sorties obtiennent le même coût moyen. La sortie et la réception virtuelles peuvent être considérées comme un transfert virtuel, appelé *transfert de clôture du stock moyen pondéré*. Cette méthode de règlement s’appelle un *règlement résumé moyen pondéré*. S’il n’existe qu’une seule réception, toutes les sorties peuvent être réglées à partir de celle-ci et le transfert virtuel n’est pas créé. Cette méthode de règlement est appelée *règlement direct*. Tout stock disponible après la clôture du stock est évalué à la moyenne pondérée de la période précédente et inclus dans le calcul de la moyenne pondérée de la période suivante.

Vous pouvez ignorer le principe de moyenne pondérée en marquant les mouvements de stock de manière ce qu’une réception d’article spécifique soit réglée avec une sortie spécifique. Une clôture d’inventaire périodique est requise lorsque vous utilisez le modèle d’inventaire de moyenne pondérée pour créer des règlements et ajuster la valeur des sorties selon le principe de moyenne pondérée. Jusqu’à ce que vous exécutiez le processus de clôture de stock, les transactions de sortie sont évaluées à la moyenne en vigueur lorsque les mises à jour physiques et financières ont eu lieu. À moins que vous n’utilisiez le marquage, la moyenne en vigueur est calculée lors de la mise à jour physique ou financière.

La méthode d’évaluation des stocks de moyenne pondérée est calculée grâce à la formule suivante :

- Moyenne pondérée = (\[Q1 × P1\] + \[Q2 × P2\] + \[Q *n* × P *n*\]) ÷ (Q1 + Q2 + Q *n*)

Q = quantité de la transaction  
P = prix de la transaction

Les règlements correspondent à des validations de clôture du stock qui ajustent les sorties à la moyenne pondérée correcte depuis la date de clôture. Les exemples suivants illustrent l’impact du modèle de moyenne pondérée avec cinq configurations différentes :

- Règlement direct à la moyenne pondérée sans l’option **Inclure la valeur physique**
- Règlement récapitulatif à la moyenne pondérée sans l’option **Inclure la valeur physique**
- Règlement direct à la moyenne pondérée avec l’option **Inclure la valeur physique**
- Règlement récapitulatif à la moyenne pondérée avec l’option **Inclure la valeur physique**
- Moyenne pondérée avec marquage

## <a name="weighted-average-direct-settlement-without-include-physical-value"></a>Règlement direct à la moyenne pondérée sans l’option Inclure la valeur physique

Le principe de règlement direct crée des règlements directement entre les réceptions et les sorties sans créer de transactions de stock supplémentaires. Le système utilise ce principe de règlement direct dans les situations suivantes :

- Une seule réception et une ou plusieurs sorties ont été validées au cours de la période.
- Seules des sorties ont été validées au cours de la période et le stock contient des articles disponibles d’une clôture précédente.

Dans cet exemple, la case à cocher **Inclure la valeur physique** est décochée sur le **groupe de modèles d’élément** pour le produit lancé. La figure suivante illustre ces transactions :

- 1a. Réception physique en stock pour une quantité de 10 à un coût de 10,00 EUR chacune.
- 1b. Réception financière en stock pour une quantité de 10 à un coût de 10,00 EUR chacune.
- 2a. Réception physique en stock pour une quantité de 10 à un coût de 20,00 EUR chacune.
- 3a. Sortie physique de stock pour une quantité de 1 à un prix de revient de 10,00 EUR (prix de revient moyen en vigueur des transactions validées financièrement).
- 3b. Sortie financière de stock pour une quantité de 1 à un prix de revient de 10,00 EUR (prix de revient moyen en vigueur des transactions mises à jour financièrement).
- 4a. Sortie physique de stock pour une quantité de 1 à un prix de revient de 10,00 EUR (prix de revient moyen en vigueur des transactions validées financièrement).
- 4b. Sortie financière de stock pour une quantité de 1 à un prix de revient de 10,00 EUR (prix de revient moyen en vigueur des transactions mises à jour financièrement).
- 5a. Sortie physique de stock pour une quantité de 1 à un prix de revient de 10,00 EUR (prix de revient moyen en vigueur des transactions validées financièrement).
- 6\. La clôture du stock est effectuée. Basé sur la méthode de la moyenne pondérée, le système utilise la méthode de règlement direct, car un seul encaissement est financièrement mis à jour dans la période. Dans cet exemple, un règlement est créé entre 1b et 3b, et un autre entre 1b et 4b. Aucun ajustement n’est effectué, car la moyenne mobile est la même que la moyenne pondérée.

Le diagramme suivant illustre cette série de transactions avec les effets du choix du modèle de stock à moyenne pondérée et le principe de règlement direct sans l’option **Inclure la valeur physique**.

![WeightedAverage DS sans Inclure la valeur physique.](media/weighted-average-direct-settlement-without-include-physical-value.png)

**Clés du diagramme**

- Les mouvements de stock sont représentés par les flèches verticales.
- Les transactions physiques sont représentées par des flèches gris clair plus courtes.
- Les transactions financières sont représentées par des flèches noires plus longues.
- Les réceptions en stock sont représentées par les flèches verticales au-dessus de l’axe.
- Les sorties de stock sont représentées par les flèches verticales en dessous de l’axe.
- Chaque nouvelle transaction de réception ou de sortie est désignée par un nouveau libellé.
- Chaque flèche verticale est marquée par un identificateur séquentiel, comme *1a*. Les identificateurs indiquent l’ordre des validations des mouvements de stock sur la ligne temporelle.
- Chaque date du diagramme est séparée par une fine ligne verticale noire. La date est notée en bas du schéma.
- Les clôtures de stock sont représentées par une ligne pointillée verticale rouge.
- Les règlements effectués par clôture de stock sont représentés par des flèches rouges en diagonale d’une réception vers une sortie.

## <a name="weighted-average-summarized-settlement-without-the-include-physical-value-option"></a>Règlement récapitulatif à la moyenne pondérée sans l’option Inclure la valeur physique

Lorsquil y a plusieurs réceptions dans une période, la moyenne pondérée utilise le principe de règlement résumé lorsque toutes les réceptions d’une période de clôture sont résumées dans une transaction appelée *Clôture de stock à moyenne pondérée*. Toutes les réceptions d’une période sont réglées avec la sortie de la transaction de stock créée. Toutes les sorties de la période seront réglées avec la réception de la nouvelle transaction de stock. S’il y a une valeur restante de stock disponible après la clôture de stock, la valeur de stock disponible est incluse dans la transaction de réception des transactions de clôture de stock de moyenne pondérée.

Les transactions suivantes sont illustrées dans le graphique ci-dessous :

- 1a. Réception physique en stock pour une quantité de 1 à un coût de 10,00 EUR chacune.
- 1b. Réception financière en stock pour une quantité de 1 à un coût de 10,00 EUR chacune.
- 2a. Réception physique en stock pour une quantité de 1 à un coût de 20,00 EUR chacune.
- 2b. Réception financière en stock pour une quantité de 1 à un coût de 22,00 EUR chacune.
- 3a. Sortie physique de stock pour une quantité de 1 à un prix de revient de 16,00 EUR (prix de revient moyen en vigueur des transactions validées financièrement).
- 3b. Sortie financière de stock pour une quantité de 1 à un prix de revient de 16,00 EUR (prix de revient moyen en vigueur des transactions mises à jour financièrement).
- 4a. Réception physique en stock pour une quantité 1 au coût unitaire de 25,00 EUR.
- 5a. Réception physique en stock pour une quantité de 1 à un coût de 30,00 EUR chacune.
- 5b. Réception financière en stock pour une quantité de 1 à un coût de 30,00 EUR chacune.
- 6a. Sortie physique de stock pour une quantité de 1 à un prix de revient de 23,00 EUR (prix de revient moyen en vigueur des transactions validées financièrement).
- 7\. La clôture du stock est effectuée.
- 7a. La sortie financière de transaction de clôture de stock à moyenne pondérée est créée pour récapituler les règlements de toutes les réceptions financières du stock.
  - La transaction 1b est réglée pour une quantité de 1 avec un montant réglé de 10,00 USD.
  - La transaction 2b est réglée pour une quantité de 1 avec un montant réglé de 22,00 EUR.
  - La transaction 5b est réglée pour une quantité de 1 avec un montant réglé de 30,00 EUR.
  - Transation 7a. est créée pour une quantité de 3 avec un montant réglé de 62,00 EUR. Cette transaction compense la somme des trois transactions de réception mises à jour financièrement dans la période.
- 7b. Une réception financière de transaction de clôture de stock à moyenne pondérée est créée comme contrepartie aux sorties financièrement validées.
  - La transaction 3b est réglée pour une quantité de 1 avec un montant réglé de 20,67 EUR. Cette transaction est ajustée par 4,67 EUR pour ramener la valeur d’origine de 16,00 à 20,67 EUR qui est la moyenne pondérée des transactions comptabilisées financièrement pour la période.
  - Transaction 7b. est créée pour une quantité de 1 avec un montant réglé de 20,67 EUR pour compenser 3b. Cette transaction compense la somme de la transactions à une sortie mise à jour financièrement dans la période.

Le diagramme suivant illustre cette série de transactions avec les effets du choix du modèle de stock à moyenne pondérée et le principe de règlement récapitulatif sans l’option **Inclure la valeur physique**.

![Règlement récapitulatif de moyenne pondérée sans Inclure la valeur physique.](media/weighted-average-summarized-settlement-without-include-physical-value.png)

**Clés du diagramme**

- Les mouvements de stock sont représentés par les flèches verticales.
- Les transactions physiques sont représentées par des flèches gris clair plus courtes.
- Les transactions financières sont représentées par des flèches noires plus longues.
- Les réceptions en stock sont représentées par les flèches verticales au-dessus de l’axe.
- Les sorties de stock sont représentées par les flèches verticales en dessous de l’axe.
- Chaque nouvelle transaction de réception ou de sortie est désignée par un nouveau libellé.
- Chaque flèche verticale est marquée par un identificateur séquentiel, comme *1a*. Les identificateurs indiquent l’ordre des validations des mouvements de stock sur la ligne temporelle.
- Chaque date du diagramme est séparée par une fine ligne verticale noire. La date est notée en bas du schéma.
- Les clôtures de stock sont représentées par une ligne pointillée verticale rouge.
- Les règlements effectués par clôture de stock sont représentés par des flèches rouges en diagonale d’une réception vers une sortie.

## <a name="weighted-average-direct-settlement-with-the-include-physical-value-option"></a>Règlement direct à la moyenne pondérée avec l’option Inclure la valeur physique

Le paramètre **Inclure la valeur physique** fonctionne différemment par rapport au modèle de stock de moyenne pondérée des versions précédentes du produit. Si vous cochez la case **Inclure la valeur physique** pour un article sur le formulaire **Groupe de modèles d’article**, le système utilise les réceptions mises à jour physiquement lors du calcul du prix de revient estimé, ou moyen en vigueur. Les sorties sont validées sur la base de ce prix de revient estimé au cours de la période. Lors de la clôture du stock, seules les réceptions mises à jour financièrement seront prises en compte dans le calcul de la moyenne pondérée.

Les transactions suivantes sont illustrées dans le graphique ci-dessous :

- 1a. Réception physique en stock pour une quantité de 10 à un coût de 10,00 EUR chacune.
- 1b. Réception financière en stock pour une quantité de 10 à un coût de 10,00 EUR chacune.
- 2a. Réception physique en stock pour une quantité de 10 à un coût de 20,00 EUR chacune.
- 3a. Sortie physique de stock pour une quantité de 1 à un prix de revient de 15,00 EUR (prix de revient moyen en vigueur des transactions validées financièrement et physiquement).
- 3b. Sortie financière de stock pour une quantité de 1 à un prix de revient de 15,00 EUR (prix de revient moyen en vigueur des transactions validées financièrement et physiquement).
- 4a. Sortie physique de stock pour une quantité de 1 à un prix de revient de 15,00 EUR (prix de revient moyen en vigueur des transactions validées financièrement et physiquement).
- 4b. Sortie financière de stock pour une quantité de 1 à un prix de revient de 15,00 EUR (prix de revient moyen en vigueur des transactions validées financièrement et physiquement).
- 5a. Sortie physique de stock pour une quantité de 1 à un prix de revient de 15,00 EUR (prix de revient moyen en vigueur des transactions validées financièrement et physiquement).
- 6\. La clôture du stock est effectuée. Basé sur la méthode de la moyenne pondérée, le système utilise la méthode de règlement direct, car un seul encaissement est financièrement mis à jour dans la période. Dans cet exemple, un règlement est créé entre 1b et 3b, et un autre entre 1b et 4b. Les transactions 3b et 4b sont chacune ajustées de -5,00 EUR pour amener la valeur à 10,00 EUR.

Le diagramme suivant illustre cette série de transactions avec les effets du choix du modèle de stock à moyenne pondérée et le principe de règlement direct avec l’option **Inclure la valeur physique**.

![Règlement direct de moyenne pondérée avec Inclure la valeur physique.](media/weighted-average-direct-settlement-with-include-physical-value.png)

**Clés du diagramme**

- Les mouvements de stock sont représentés par les flèches verticales.
- Les transactions physiques sont représentées par des flèches gris clair plus courtes.
- Les transactions financières sont représentées par des flèches noires plus longues.
- Les réceptions en stock sont représentées par les flèches verticales au-dessus de l’axe.
- Les sorties de stock sont représentées par les flèches verticales en dessous de l’axe.
- Chaque nouvelle transaction de réception ou de sortie est désignée par un nouveau libellé.
- Chaque flèche verticale est marquée par un identificateur séquentiel, comme *1a*. Les identificateurs indiquent l’ordre des validations des mouvements de stock sur la ligne temporelle.
- Chaque date du diagramme est séparée par une fine ligne verticale noire. La date est notée en bas du schéma.
- Les clôtures de stock sont représentées par une ligne pointillée verticale rouge.
- Les règlements effectués par clôture de stock sont représentés par des flèches rouges en diagonale d’une réception vers une sortie.

## <a name="weighted-average-summarized-settlement-with-the-include-physical-value-option"></a>Règlement récapitulatif à la moyenne pondérée avec l’option Inclure la valeur physique

Le paramètre **Inclure la valeur physique** fonctionne différemment par rapport au modèle de stock de moyenne pondérée des versions précédentes du programme. Activez la case à cocher **Inclure la valeur physique** pour un article dans la page **Groupe de modèles d’article**. Par la suite, le système utilisera les réceptions mises à jour physiquement lors du calcul du prix de revient estimé, ou moyen en vigueur. Les sorties sont validées sur la base de ce prix de revient estimé au cours de la période. Lors de la clôture du stock, seules les réceptions mises à jour financièrement seront prises en compte dans le calcul de la moyenne pondérée. Si vous utilisez le modèle de stock de moyenne pondérée, nous vous recommandons une clôture de stock mensuelle. Dans cet exemple de règlement récapitulatif à la moyenne pondérée, le groupe de modèles de stock est marqué pour inclure la valeur physique.

Les transactions suivantes sont illustrées dans le graphique ci-dessous :

- 1a. Réception physique en stock pour une quantité de 1 à un coût de 10,00 EUR chacune.
- 1b. Réception financière en stock pour une quantité de 1 à un coût de 10,00 EUR chacune.
- 2a. Réception physique en stock pour une quantité de 1 à un coût de 20,00 EUR chacune.
- 2b. Réception financière en stock pour une quantité de 1 à un coût de 22,00 EUR chacune.
- 3a. Sortie physique de stock pour une quantité de 1 à un prix de revient de 16,00 EUR (prix de revient moyen en vigueur des transactions validées financièrement et physiquement).
- 3b. Sortie financière de stock pour une quantité de 1 à un prix de revient de 16,00 EUR (prix de revient moyen en vigueur des transactions validées financièrement et physiquement).
- 4a. Réception physique en stock pour une quantité 1 au coût unitaire de 25,00 EUR.
- 5a. Réception physique en stock pour une quantité de 1 à un coût de 30,00 EUR chacune.
- 5b. Réception financière en stock pour une quantité de 1 à un coût de 30,00 EUR chacune.
- 6a. Sortie physique de stock pour une quantité de 1 à un prix de revient de 23,67 EUR (prix de revient moyen en vigueur des transactions validées financièrement et physiquement).
- 7\. La clôture du stock est effectuée.
- 7a. La sortie financière de transaction de clôture de stock à moyenne pondérée est créée pour récapituler les règlements de toutes les réceptions financières du stock.
  - La transaction 1b est réglée pour une quantité de 1 avec un montant réglé de 10,00 USD.
  - La transaction 2b est réglée pour une quantité de 1 avec un montant réglé de 22,00 EUR.
  - La transaction 5b est réglée pour une quantité de 1 avec un montant réglé de 30,00 EUR.
  - Transation 7a. est créée pour une quantité de 3 avec un montant réglé de 62,00 EUR.  
- 7b. Une réception financière de transaction de clôture de stock à moyenne pondérée est créée comme contrepartie aux transactions de sortie financièrement clôturées.
  - La transaction 3b est réglée pour une quantité de 1 avec un montant réglé de 20,67 EUR. Cette transaction est ajustée par 4,67 EUR pour ramener la valeur d’origine de 16,00 à 20,67 EUR qui est la moyenne pondérée des transactions comptabilisées financièrement pour la période.
  - Transaction 7b. est créée pour une quantité de 1 avec un montant réglé de 20,67 EUR pour compenser 3b.

Le diagramme suivant illustre cette série de transactions avec les effets du choix du modèle de stock à moyenne pondérée et le principe de règlement récapitulatif sans l’option **Inclure la valeur physique**.

![WeightedAverage SS avec Inclure la valeur physique.](media/weighted-average-summarized-settlement-with-include-physical-value.png)

**Clés du diagramme**

- Les mouvements de stock sont représentés par les flèches verticales.
- Les transactions physiques sont représentées par des flèches gris clair plus courtes.
- Les transactions financières sont représentées par des flèches noires plus longues.
- Les réceptions en stock sont représentées par les flèches verticales au-dessus de l’axe.
- Les sorties de stock sont représentées par les flèches verticales en dessous de l’axe.
- Chaque nouvelle transaction de réception ou de sortie est désignée par un nouveau libellé.
- Chaque flèche verticale est marquée par un identificateur séquentiel, comme *1a*. Les identificateurs indiquent l’ordre des validations des mouvements de stock sur la ligne temporelle.
- Chaque date du diagramme est séparée par une fine ligne verticale noire. La date est notée en bas du schéma.
- Les clôtures de stock sont représentées par une ligne pointillée verticale rouge.
- Les règlements effectués par clôture de stock sont représentés par des flèches rouges en diagonale d’une réception vers une sortie.

## <a name="weighted-average-with-marking"></a>Moyenne pondérée avec marquage

Le marquage est un processus qui vous permet de lier, ou de marquer, une transaction de sortie à une transaction de réception. Cette opération peut être effectuée avant ou après la validation d’une transaction. Vous pouvez utiliser le marquage si vous voulez être sûr du coût exact du stock lors de la validation de la transaction ou de l’exécution de la clôture de stock.

Par exemple, votre service à la clientèle a accepté une commande urgente d’un client important. Puisqu’il s’agit d’une commande urgente, vous devrez payer plus cher pour cet article pour satisfaire la demande de votre client. Vous devez être certain que le coût de cet article en stock se reflètera dans la marge, ou le coût des marchandises vendues, pour la facture de cette commande client.

Lorsque la commande fournisseur est validée, le stock est reçu à un coût de 120,00 EUR. Par exemple, ce document de commande client est marqué par rapport à la commande fournisseur avant la validation du bon de livraison ou de la facture. Le coût des marchandises vendues sera donc de 120,00 EUR au lieu du coût moyen en vigueur de l’article. Si le bon de livraison ou la facture de la commande client est validée avant le marquage, le coût des marchandises vendues sera validé au prix de revient moyen en vigueur.

Avant d’exécuter la clôture de stock, ces deux transactions peuvent encore être marquées l’une par rapport à l’autre.

Une transaction de réception est marquée par rapport à une transaction de sortie. La méthode d’évaluation sélectionnée pour le groupe de modèles de stock de l’article est ignorée et le système règle ces transactions les unes avec les autres.

Vous pouvez marquer une transaction de sortie par rapport à une réception avant la validation de la transaction. Vous pouvez le faire à partir d’une ligne de commande client dans la page **Détails de la commande client**. Les transactions de réception en cours sont affichées dans la page **Marquage**.

Vous pouvez marquer une transaction de sortie par rapport à une réception après la validation de la transaction. Vous pouvez faire correspondre ou marquer une transaction de sortie par rapport à une transaction de réception en cours pour un article inventorié dans un journal d’ajustement de stock validé.

Les transactions suivantes sont illustrées dans le graphique ci-dessous :

- 1a. Réception physique en stock pour une quantité de 1 à un coût de 10,00 EUR chacune.
- 1b. Réception financière en stock pour une quantité de 1 à un coût de 10,00 EUR chacune.
- 2a. Réception physique en stock pour une quantité de 1 à un coût de 20,00 EUR chacune.
- 2b. Réception financière en stock pour une quantité de 1 à un coût de 22,00 EUR chacune.
- 3a. Sortie physique de stock pour une quantité de 1 à un prix de revient de 16,00 EUR (prix de revient moyen en vigueur des transactions validées financièrement).
- 3b. Sortie financière de stock pour une quantité de 1 à un prix de revient de 16,00 EUR (prix de revient moyen en vigueur des transactions mises à jour financièrement).
- 3c. La sortie financière de stock pour 3b est marquée comme sortie financière de stock pour 2b.
- 4a. Réception physique en stock pour une quantité 1 au coût unitaire de 25,00 EUR.
- 5a. Réception physique en stock pour une quantité de 1 à un coût de 30,00 EUR chacune.
- 5b. Réception financière en stock pour une quantité de 1 à un coût de 30,00 EUR chacune.
- 6a. Sortie physique de stock pour une quantité de 1 à un prix de revient de 23,00 EUR (prix de revient moyen en vigueur des transactions validées financièrement).
- 7\. La clôture du stock est effectuée. Selon le principe de marquage qui utilise la méthode de moyenne pondérée, les transactions marquées sont réglées les unes par rapport aux autres. Dans cet exemple, 3b est réglé sur 2b, et un ajustement pour 6,00 EUR est posté sur 3b pour ramener la valeur à 22,00 EUR. Dans cet exemple, aucun règlement supplémentaire n’est effectué, car la clôture crée des règlements uniquement pour les transactions financièrement mises à jour.

Le diagramme suivant illustre cette série de transactions avec les effets du choix du modèle de stock de moyenne pondérée avec marquage.

![Moyenne pondérée avec marquage.](media/weighted-average-with-marking.png)

**Clés du diagramme**

- Les mouvements de stock sont représentés par les flèches verticales.
- Les transactions physiques sont représentées par des flèches gris clair plus courtes.
- Les transactions financières sont représentées par des flèches noires plus longues.
- Les réceptions en stock sont représentées par les flèches verticales au-dessus de l’axe.
- Les sorties de stock sont représentées par les flèches verticales en dessous de l’axe.
- Chaque nouvelle transaction de réception ou de sortie est désignée par un nouveau libellé.
- Chaque flèche verticale est marquée par un identificateur séquentiel, comme *1a*. Les identificateurs indiquent l’ordre des validations des mouvements de stock sur la ligne temporelle.
- Chaque date du diagramme est séparée par une fine ligne verticale noire. La date est notée en bas du schéma.
- Les clôtures de stock sont représentées par une ligne pointillée verticale rouge.
- Les règlements effectués par clôture de stock sont représentés par des flèches rouges en diagonale d’une réception vers une sortie.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
