---
title: Date de moyenne pondérée avec Inclure valeur physique et marquage
description: La date moyenne pondérée est un modèle de stock basé sur le principe de moyenne pondérée, dans lequel les sorties de stock correspondent à la valeur moyenne des articles reçus en stock pour chaque jour de la période de clôture du stock.
author: JennySong-SH
ms.date: 03/04/2022
ms.topic: article
ms.search.form: InventJournalLossProfit, InventMarking, InventModelGroup, SalesTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: 28991
ms.search.region: Global
ms.author: yanansong
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 1497cb08f4cc5a455c832b9bf125c309cd90aa3d
ms.sourcegitcommit: 9166e531ae5773f5bc3bd02501b67331cf216da4
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/03/2022
ms.locfileid: "8672120"
---
# <a name="weighted-average-date-with-include-physical-value-and-marking"></a>Date de moyenne pondérée avec Inclure valeur physique et marquage

[!include [banner](../includes/banner.md)]

La *Date de moyenne pondérée* est un modèle d’inventaire basé sur une moyenne qui résulte de la multiplication de chaque composant (transaction article) par un facteur (prix de revient) reflétant son importance (quantité) chaque jour de la période. En d’autres termes, cette moyenne pondérée est un modèle d’inventaire qui attribue le coût des transactions d’émission en fonction de la valeur moyenne de tous les stocks reçus au cours de la période, plus tout stock disponible du jour précédent.

Lorsque vous exécutez une clôture de stock à l’aide du modèle de stock de date de moyenne pondérée, il existe deux façons de créer un règlement. En général, toutes les réceptions sont réglées avec une sortie virtuelle, contenant la valeur et la quantité totales reçues. À cette sortie virtuelle correspond une réception virtuelle à partir de laquelle les sorties sont réglées. De cette manière, toutes les sorties obtiennent le même coût moyen chaque jour. L’émission virtuelle et le reçu virtuel peuvent être considérés comme un transfert virtuel. Ce transfert virtuel est appelé *transfert de clôture de stock de moyenne pondérée*. Par conséquent, ce mode de règlement s’appelle un *règlement résumé moyen pondéré*. S’il n’existe qu’une seule réception, toutes les sorties peuvent être réglées à partir de celle-ci et le transfert virtuel n’est pas créé. Cette méthode de règlement est appelée *règlement direct*. Tout stock disponible après la clôture du stock est évalué à la moyenne pondérée du dernier jour de la période précédente et inclus dans le calcul de la date de moyenne pondérée de la période suivante.

Vous pouvez ignorer le principe de date de moyenne pondérée en marquant les mouvements de stock de manière ce qu’une réception d’article spécifique soit réglée avec une sortie spécifique. Une clôture d’inventaire périodique est requise lorsque vous utilisez le modèle d’inventaire de date de moyenne pondérée pour créer des règlements et ajuster la valeur des sorties selon le principe de date de moyenne pondérée. Jusqu’à ce que vous exécutiez le processus de clôture de stock, les transactions de sortie sont évaluées à la moyenne en vigueur lorsque les mises à jour physiques et financières ont eu lieu. À moins que vous n’utilisiez le marquage, la moyenne en vigueur est calculée lors de la mise à jour physique ou financière.

La méthode d’évaluation des stocks de date de moyenne pondérée est calculée grâce à la formule suivante chaque jour :

*Coût* = \[(*Q*<sub>*b*</sub> × *P*<sub>*b*</sub>) + &#x2211;<sub>*n*</sub>(*Q*<sub>*n*</sub> × *P*<sub>*n*</sub>)\] ÷ (*Q*<sub>*b*</sub> + &#x2211;<sub>*n*</sub>*Q*<sub>*n*</sub>)

- *Q* = quantité de la transaction
- *P* = prix de la transaction

En d’autres termes, le coût moyen pondéré est égal à la quantité de départ multipliée par le prix de départ, plus la somme de chaque quantité de réception multipliée par son prix de réception, le tout divisé par la quantité de départ plus la somme des quantités de réception.

Pendant la clôture du stock, le calcul est exécuté quotidiennement via la période de clôture.

> [!NOTE]
> Pour plus d’informations concernant les règlements, voir [Clôture de stock](inventory-close.md).

Les exemples suivants illustrent l’impact du modèle de date de moyenne pondérée avec cinq configurations :

- Règlement direct à la date moyenne pondérée sans l’option **Inclure la valeur physique**
- Règlement récapitulatif à la date moyenne pondérée sans l’option **Inclure la valeur physique**
- Règlement direct à la date moyenne pondérée avec l’option **Inclure la valeur physique**
- Règlement récapitulatif à la date moyenne pondérée avec l’option **Inclure la valeur physique**
- Date moyenne pondérée avec marquage

## <a name="weighted-average-date-direct-settlement-when-the-include-physical-value-option-isnt-used"></a>Règlement direct à la date moyenne pondérée sans l’option Inclure la valeur physique

Le principe de règlement direct crée des règlements directement entre les réceptions et les sorties sans créer de transactions de stock supplémentaires. Le système utilise ce principe de règlement direct dans les situations suivantes :

- Une seule réception et une ou plusieurs sorties ont été validées au cours de la période.
- Seules des sorties ont été validées au cours de la période et le stock contient des articles disponibles d’une clôture précédente.

Dans cet exemple, la case à cocher **Inclure la valeur physique** est décochée sur la page **groupe de modèles d’élément** pour le produit lancé. Le diagramme suivant illustre ces transactions :

**Jour 1:**

- 1a. Réception physique en stock pour une quantité de 10 à un coût de 10,00 EUR chacune.
- 1b. Réception financière en stock pour une quantité de 10 à un coût de 10,00 EUR chacune.
- 2a. Réception physique en stock pour une quantité de 10 à un coût de 20,00 EUR chacune.
- 3a. Sortie physique de stock pour une quantité de 1 à un prix de revient de 10,00 EUR (prix de revient moyen en vigueur des transactions validées financièrement).
- 3b. Sortie financière de stock pour une quantité de 1 à un prix de revient de 10,00 EUR (prix de revient moyen en vigueur des transactions mises à jour financièrement).

**Jour 2:**

- 4a. Réception physique en stock pour une quantité 1 au coût unitaire de 25,00 EUR.
- 5a. Réception physique en stock pour une quantité de 1 à un coût de 30,00 EUR chacune.
- 5b. Réception financière en stock pour une quantité de 1 à un coût de 30,00 EUR chacune.
- 6a. Sortie financière de stock pour une quantité de 1 à un prix de revient de 20,00 EUR (prix de revient moyen en vigueur des transactions mises à jour financièrement).

**Jour 3:**

- 7\. La clôture du stock est effectuée. Basé sur la méthode de la date de moyenne pondérée, le système utilise la méthode de règlement direct depuis le 30 décembre (30/12), car un seul encaissement est financièrement mis à jour le 30/12. Dans cet exemple, un règlement est créé entre les transactions 1b et 3b. Un ajustement de 10,00 USD est effectué pour porter la valeur de la transaction 3b à 20,00. Aucun ajustement ou règlement n’est effectué au 31 décembre (31/12), car il n’y a pas d’émission financièrement mise à jour au 31/12.

Le diagramme suivant illustre cette série de transactions avec les effets du choix du modèle de stock à moyenne pondérée et le principe de règlement direct sans l’option **Inclure la valeur physique**.

![Règlement direct à la date moyenne pondérée sans l’option Inclure la valeur physique.](media/weighted-average-date-direct-settlement-without-include-physical-value.png)

**Clés du diagramme :**

- Les mouvements de stock sont représentés par les flèches verticales.
- Les transactions physiques sont représentées par des flèches gris clair plus courtes.
- Les transactions financières sont représentées par des flèches noires plus longues.
- Les réceptions en stock sont représentées par les flèches verticales au-dessus de l’axe.
- Les sorties de stock sont représentées par les flèches verticales en dessous de l’axe.
- Chaque nouvelle transaction de réception ou de sortie est désignée par un nouveau libellé.
- Chaque flèche verticale est marquée par un identificateur séquentiel, comme *1a*. Les identificateurs indiquent l’ordre des validations des mouvements de stock sur la ligne temporelle.
- Les dates sont séparées par de fines lignes verticales noires. Les dates sont notées en bas du schéma.
- Les clôtures de stock sont représentées par des lignes pointillées verticales rouges.
- Les règlements effectués par clôture de stock sont représentés par des flèches rouges en diagonale d’une réception vers une sortie.

## <a name="weighted-average-date-summarized-settlement-when-the-include-physical-value-option-isnt-used"></a>Règlement récapitulatif à la date moyenne pondérée sans l’option Inclure la valeur physique

Lorsquil y a plusieurs réceptions dans une période, la date de moyenne pondérée utilise le principe de règlement résumé lorsque toutes les réceptions d’une seule journée sont résumées dans une transaction appelée *Clôture de stock à moyenne pondérée*. Toutes les réceptions d’une journée sont réglées avec la sortie de la transaction de stock créée. Toutes les sorties de la journée seront réglées avec la réception de la nouvelle transaction de stock. S’il y a une valeur restante de stock disponible après la clôture de stock, la valeur de stock disponible est incluse dans la transaction de réception des transactions de clôture de stock de moyenne pondérée.

Le diagramme suivant illustre ces transactions :

**Jour 1:**

- 1a. Réception physique en stock pour une quantité de 1 à un coût de 10,00 EUR chacune.
- 1b. Réception financière en stock pour une quantité de 1 à un coût de 10,00 EUR chacune.
- 2a. Réception physique en stock pour une quantité de 1 à un coût de 20,00 EUR chacune.
- 2b. Réception financière en stock pour une quantité de 1 à un coût de 22,00 EUR chacune.
- 3a. Sortie physique de stock pour une quantité de 1 à un prix de revient de 16,00 EUR (prix de revient moyen en vigueur des transactions validées financièrement).
- 3b. Sortie financière de stock pour une quantité de 1 à un prix de revient de 16,00 EUR (prix de revient moyen en vigueur des transactions mises à jour financièrement).

**Jour 2:**

- 4a. Réception physique en stock pour une quantité 1 au coût unitaire de 25,00 EUR.
- 5a. Réception physique en stock pour une quantité de 1 à un coût de 30,00 EUR chacune.
- 5b. Réception financière en stock pour une quantité de 1 à un coût de 30,00 EUR chacune.
- 6a. Sortie physique de stock pour une quantité de 1 à un prix de revient de 23,00 EUR (prix de revient moyen en vigueur des transactions validées financièrement).

**Jour 3:**

- 7\. La clôture du stock est effectuée.
- 7a. La sortie financière de transaction de clôture de stock à moyenne pondérée est créée pour récapituler les règlements de toutes les réceptions financières du stock.

    - La transaction 1b est réglée pour une quantité de 1 avec un montant réglé de 10,00 USD.
    - La transaction 2b est réglée pour une quantité de 1 avec un montant réglé de 22,00 EUR.
    - La transaction 7a est créée pour une quantité de 2 avec un montant réglé de 32,00 EUR. Cette transaction compense la somme des deux transactions de réception mises à jour financièrement dans la période.

- 7b. Une réception financière de transaction de clôture de stock à moyenne pondérée est créée comme contrepartie aux sorties financièrement validées.

    - La transaction 3b est réglée pour une quantité de 1 avec un montant réglé de 16,00 EUR. Cette transaction n’est pas ajustée, car il s’agit de la moyenne pondérée des transactions financières publiées au 1er décembre (12/1).
    - La transaction 7b est créée pour une quantité de 2 avec un montant financier de 32,00 USD et un montant réglé de 16,00 USD pour compenser la transaction 3b. Cette transaction compense la somme de la transactions à une sortie mise à jour financièrement dans la période. La transaction reste ouverte, car il en reste une en cours.

Le diagramme suivant illustre cette série de transactions avec les effets du choix du modèle de stock à moyenne pondérée et le principe de règlement récapitulatif sans l’option **Inclure la valeur physique**.

![Règlement récapitulatif à la date moyenne pondérée sans l’option Inclure la valeur physique.](media/weighted-average-date-summarized-settlement-without-include-physical-value.png)

**Clés du diagramme :**

- Les mouvements de stock sont représentés par les flèches verticales.
- Les transactions physiques sont représentées par des flèches gris clair plus courtes.
- Les transactions financières sont représentées par des flèches noires plus longues.
- Les réceptions en stock sont représentées par les flèches verticales au-dessus de l’axe.
- Les sorties de stock sont représentées par les flèches verticales en dessous de l’axe.
- Chaque nouvelle transaction de réception ou de sortie est désignée par un nouveau libellé.
- Chaque flèche verticale est marquée par un identificateur séquentiel, comme *1a*. Les identificateurs indiquent l’ordre des validations des mouvements de stock sur la ligne temporelle.
- Les dates sont séparées par de fines lignes verticales noires. Les dates sont notées en bas du schéma.
- Les clôtures de stock sont représentées par des lignes pointillées verticales rouges.
- Les règlements effectués par clôture de stock sont représentés par des flèches rouges en diagonale d’une réception vers une sortie.

## <a name="weighted-average-date-direct-settlement-when-the-include-physical-value-option-is-used"></a>Règlement direct à la date moyenne pondérée avec l’option Inclure la valeur physique

Dans la version actuelle du produit, l’option **Inclure la valeur physique** fonctionne différemment par rapport au modèle de stock de date de moyenne pondérée des versions précédentes du produit. Si vous cochez la case **Inclure la valeur physique** pour un article sur la page **Groupe de modèles d’article**, le système utilise les réceptions mises à jour physiquement lors du calcul du prix de revient estimé, ou moyen en vigueur. Les sorties sont validées sur la base de ce prix de revient estimé au cours de la période. Lors de la clôture du stock, seules les réceptions mises à jour financièrement seront prises en compte dans le calcul de la moyenne pondérée.

Le diagramme suivant illustre ces transactions :

**Jour 1:**

- 1a. Réception physique en stock pour une quantité de 10 à un coût de 10,00 EUR chacune.
- 1b. Réception financière en stock pour une quantité de 10 à un coût de 10,00 EUR chacune.
- 2a. Réception physique en stock pour une quantité de 10 à un coût de 20,00 EUR chacune.
- 3a. Sortie physique de stock pour une quantité de 1 à un prix de revient de 15,00 EUR (prix de revient moyen en vigueur des transactions validées financièrement et physiquement).
- 3b. Sortie financière de stock pour une quantité de 1 à un prix de revient de 15,00 EUR (prix de revient moyen en vigueur des transactions validées financièrement et physiquement).

**Jour 2:**

- 4a. Réception physique en stock pour une quantité 1 au coût unitaire de 25,00 EUR.
- 5a. Réception physique en stock pour une quantité de 1 à un coût de 30,00 EUR chacune.
- 5b. Réception financière en stock pour une quantité de 1 à un coût de 30,00 EUR chacune.
- 6a. Sortie physique de stock pour une quantité de 1 à un prix de revient de 21,25 EUR (prix de revient moyen en vigueur des transactions validées financièrement et physiquement).

**Jour 3:**

- 7\. La clôture du stock est effectuée. Basé sur la méthode de la date de moyenne pondérée, le système utilise la méthode de règlement direct depuis le 30 décembre (30/12), car un seul encaissement est financièrement mis à jour le 30/12. Dans cet exemple, un règlement est créé entre les transactions 1b et 3b. Aucun ajustement n’est apporté à l’émission du 30/12. En outre, aucun ajustement ou règlement n’est effectué au 31 décembre (31/12), car il n’y a pas d’émission financièrement mise à jour au 31/12.

Le diagramme suivant illustre cette série de transactions avec les effets du choix du modèle de stock à moyenne pondérée et le principe de règlement direct avec l’option **Inclure la valeur physique**.

![Règlement direct à la moyenne pondérée avec l’option Inclure la valeur physique.](media/weighted-average-date-direct-settlement-with-include-physical-value.png)

**Clés du diagramme :**

- Les mouvements de stock sont représentés par les flèches verticales.
- Les transactions physiques sont représentées par des flèches gris clair plus courtes.
- Les transactions financières sont représentées par des flèches noires plus longues.
- Les réceptions en stock sont représentées par les flèches verticales au-dessus de l’axe.
- Les sorties de stock sont représentées par les flèches verticales en dessous de l’axe.
- Chaque nouvelle transaction de réception ou de sortie est désignée par un nouveau libellé.
- Chaque flèche verticale est marquée par un identificateur séquentiel, comme *1a*. Les identificateurs indiquent l’ordre des validations des mouvements de stock sur la ligne temporelle.
- Les dates sont séparées par de fines lignes verticales noires. Les dates sont notées en bas du schéma.
- Les clôtures de stock sont représentées par des lignes pointillées verticales rouges.
- Les règlements effectués par clôture de stock sont représentés par des flèches rouges en diagonale d’une réception vers une sortie.

## <a name="weighted-average-date-summarized-settlement-when-the-include-physical-value-option-is-used"></a>Règlement récapitulatif à la date moyenne pondérée avec l’option Inclure la valeur physique

Dans la version actuelle du produit, l’option **Inclure la valeur physique** fonctionne différemment par rapport au modèle de stock de date de moyenne pondérée des versions précédentes du produit. Si vous cochez la case **Inclure la valeur physique** pour un article sur la page **Groupe de modèles d’article**, le système utilise les réceptions mises à jour physiquement lors du calcul du prix de revient estimé, ou moyen en vigueur. Les sorties sont validées sur la base de ce prix de revient estimé au cours de la période. Lors de la clôture du stock, seules les réceptions mises à jour financièrement seront prises en compte dans le calcul de la moyenne pondérée. Si vous utilisez le modèle de stock de moyenne pondérée, nous vous recommandons une clôture de stock mensuelle. Dans cet exemple de règlement récapitulatif à la date de moyenne pondérée, le groupe de modèles de stock est marqué pour inclure la valeur physique.

Le diagramme suivant illustre ces transactions :

**Jour 1:**

- 1a. Réception physique en stock pour une quantité de 1 à un coût de 10,00 EUR chacune.
- 1b. Réception financière en stock pour une quantité de 1 à un coût de 10,00 EUR chacune.
- 2a. Réception physique en stock pour une quantité de 1 à un coût de 20,00 EUR chacune.
- 2b. Réception financière en stock pour une quantité de 1 à un coût de 22,00 EUR chacune.
- 3a. Sortie physique de stock pour une quantité de 1 à un prix de revient de 16,00 EUR (prix de revient moyen en vigueur des transactions validées financièrement et physiquement).
- 3b. Sortie financière de stock pour une quantité de 1 à un prix de revient de 16,00 EUR (prix de revient moyen en vigueur des transactions validées financièrement et physiquement).

**Jour 2:**

- 4a. Réception physique en stock pour une quantité 1 au coût unitaire de 25,00 EUR.
- 5a. Réception physique en stock pour une quantité de 1 à un coût de 30,00 EUR chacune.
- 5b. Réception financière en stock pour une quantité de 1 à un coût de 30,00 EUR chacune.
- 6a. Sortie physique de stock pour une quantité de 1 à un prix de revient de 23,67 EUR (prix de revient moyen en vigueur des transactions validées financièrement et physiquement).

**Jour 3:**

- 7\. La clôture du stock est effectuée.
- 7a. La sortie financière de transaction de clôture de stock à moyenne pondérée est créée pour récapituler les règlements de toutes les réceptions financières du stock.

    - La transaction 1b est réglée pour une quantité de 1 avec un montant réglé de 10,00 USD.
    - La transaction 2b est réglée pour une quantité de 1 avec un montant réglé de 22,00 EUR.
    - La transaction 7a est créée pour une quantité de 2 avec un montant réglé de 32,00 EUR. Cette transaction compense la somme des deux transactions de réception mises à jour financièrement dans la période.

- 7b. Une réception financière de transaction de clôture de stock à moyenne pondérée est créée comme contrepartie aux sorties financièrement validées.

    - La transaction 3b est réglée pour une quantité de 1 avec un montant réglé de 16,00 EUR. Cette transaction n’est pas ajustée, car il s’agit de la moyenne pondérée des transactions financières publiées au 1er décembre (12/1).
    - La transaction 7b est créée pour une quantité de 2 avec un montant financier de 32,00 USD et un montant réglé de 16,00 USD pour compenser la transaction 3b. Cette transaction compense la somme de la transactions à une sortie mise à jour financièrement dans la période. La transaction reste ouverte, car il en reste une en cours.

Le diagramme suivant illustre cette série de transactions avec les effets du choix du modèle de stock à moyenne pondérée et le principe de règlement direct sans l’option **Inclure la valeur physique**.

![Règlement récapitulatif à la moyenne pondérée avec l’option Inclure la valeur physique.](media/weighted-average-date-summarized-settlement-with-include-physical-value.png)

**Clés du diagramme :**

- Les mouvements de stock sont représentés par les flèches verticales.
- Les transactions physiques sont représentées par des flèches gris clair plus courtes.
- Les transactions financières sont représentées par des flèches noires plus longues.
- Les réceptions en stock sont représentées par les flèches verticales au-dessus de l’axe.
- Les sorties de stock sont représentées par les flèches verticales en dessous de l’axe.
- Chaque nouvelle transaction de réception ou de sortie est désignée par un nouveau libellé.
- Chaque flèche verticale est marquée par un identificateur séquentiel, comme *1a*. Les identificateurs indiquent l’ordre des validations des mouvements de stock sur la ligne temporelle.
- Les dates sont séparées par de fines lignes verticales noires. Les dates sont notées en bas du schéma.
- Les clôtures de stock sont représentées par des lignes pointillées verticales rouges.
- Les règlements effectués par clôture de stock sont représentés par des flèches rouges en diagonale d’une réception vers une sortie.

## <a name="weighted-average-date-when-marking-is-used"></a>Date moyenne pondérée avec marquage

Le marquage est un processus qui vous permet de lier, ou de marquer, une transaction de sortie à une transaction de réception. Cette opération peut être effectuée avant ou après la validation d’une transaction. Vous pouvez utiliser le marquage si vous voulez être sûr du coût exact du stock lors de la validation de la transaction ou de l’exécution de la clôture de stock.

Par exemple, votre service à la clientèle a accepté une commande urgente d’un client important. Puisqu’il s’agit d’une commande urgente, vous devrez payer plus cher pour cet article pour satisfaire la demande de votre client. Vous devez vous assurer que le coût de cet article en stock se reflètera dans la marge, ou le coût des marchandises vendues (COGS), pour la facture de cette commande client.

Lorsque la commande fournisseur est validée, le stock est reçu à un coût de 120,00 EUR. Si ce document de commande client est marqué par rapport à la commande fournisseur avant la validation du bon de livraison ou de la facture, le coût des marchandises vendues sera de 120,00 EUR, et non le coût moyen en vigueur de l’article. Si le marquage survient une fois le bon de livraison ou la facture de la commande client validé(e), le coût des marchandises vendues sera validé au prix de revient moyen en vigueur.

Avant d’exécuter la clôture de stock, ces deux transactions peuvent encore être marquées l’une par rapport à l’autre.

Lorsqu’une transaction de réception correspond à une transaction de sortie, la méthode d’évaluation définie dans le groupe de modèles d’article est ignorée et le système règle ces transactions les unes avec les autres.

Vous pouvez marquer une transaction de sortie par rapport à une réception avant la validation de la transaction. Vous pouvez le faire à partir d’une ligne de commande client dans la page **Détails de la commande client**. Les transactions de réception en cours sont affichées dans la page **Marquage**.

Vous pouvez également marquer une transaction de sortie par rapport à une réception après la validation de la transaction. Vous pouvez faire correspondre ou marquer une transaction de sortie par rapport à une transaction de réception en cours pour un article inventorié dans un journal d’ajustement de stock validé.

Le diagramme suivant illustre ces transactions :

**Jour 1:**

- 1a. Réception physique en stock pour une quantité de 1 à un coût de 10,00 EUR chacune.
- 1b. Réception financière en stock pour une quantité de 1 à un coût de 10,00 EUR chacune.
- 2a. Réception physique en stock pour une quantité de 1 à un coût de 20,00 EUR chacune.
- 2b. Réception financière en stock pour une quantité de 1 à un coût de 22,00 EUR chacune.
- 3a. Sortie physique de stock pour une quantité de 1 à un prix de revient de 16,00 EUR (prix de revient moyen en vigueur des transactions validées financièrement).
- 3b. Sortie financière de stock pour une quantité de 1 à un prix de revient de 16,00 EUR (prix de revient moyen en vigueur des transactions mises à jour financièrement).
- 3c. La sortie financière de stock pour la transaction 3b est marquée comme sortie financière de stock pour la transaction 2b.

**Jour 2:**

- 4a. Réception physique en stock pour une quantité 1 au coût unitaire de 25,00 EUR.
- 5a. Réception physique en stock pour une quantité de 1 à un coût de 30,00 EUR chacune.
- 5b. Réception financière en stock pour une quantité de 1 à un coût de 30,00 EUR chacune.
- 6a. Sortie physique de stock pour une quantité de 1 à un prix de revient de 23,00 EUR (prix de revient moyen en vigueur des transactions validées financièrement).

**Jour 3:**

- 7\. La clôture du stock est effectuée. Selon le principe de marquage qui utilise la méthode de moyenne pondérée, les transactions marquées sont réglées les unes par rapport aux autres. Dans cet exemple, la transaction 3b est réglée sur la transaction 2b, et un ajustement pour 6,00 EUR est posté sur la transaction 3b pour ramener la valeur à 22,00 EUR. Dans cet exemple, aucun règlement supplémentaire n’est effectué, car la clôture crée des règlements uniquement pour les transactions financièrement mises à jour.

Le diagramme suivant illustre cette série de transactions avec les effets du choix du modèle de stock de moyenne pondérée avec marquage.

![Moyenne pondérée avec marquage.](media/weighted-average-date-with-marking.png)

**Clés du diagramme :**

- Les mouvements de stock sont représentés par les flèches verticales.
- Les transactions physiques sont représentées par des flèches gris clair plus courtes.
- Les transactions financières sont représentées par des flèches noires plus longues.
- Les réceptions en stock sont représentées par les flèches verticales au-dessus de l’axe.
- Les sorties de stock sont représentées par les flèches verticales en dessous de l’axe.
- Chaque nouvelle transaction de réception ou de sortie est désignée par un nouveau libellé.
- Chaque flèche verticale est marquée par un identificateur séquentiel, comme *1a*. Les identificateurs indiquent l’ordre des validations des mouvements de stock sur la ligne temporelle.
- Les dates sont séparées par de fines lignes verticales noires. Les dates sont notées en bas du schéma.
- Les clôtures de stock sont représentées par des lignes pointillées verticales rouges.
- Les règlements effectués par clôture de stock sont représentés par des flèches rouges en diagonale d’une réception vers une sortie.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
