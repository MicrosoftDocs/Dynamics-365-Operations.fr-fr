---
title: FIFO avec valeur physique et marquage
description: Premier entré, premier sorti (First In, First Out, ou FIFO) est un modèle de stock selon lequel les premières réceptions en stock sont sorties en premier. Les sorties de stock mises à jour financièrement sont réglées avec les premières réceptions en stock, en fonction de la date financière du mouvement de stock.
author: AndersGirke
ms.date: 02/02/2022
ms.topic: article
ms.search.form: InventJournalLossProfit, InventMarking, InventModelGroup, SalesTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: 54682
ms.search.region: Global
ms.author: aevengir
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 5280498a23df26873dda1f380f686796f5e1055f
ms.sourcegitcommit: fefe93f3f44d8aa0b7e6d54cc4a3e5eca6e64feb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2022
ms.locfileid: "8092138"
---
# <a name="fifo-with-physical-value-and-marking"></a>FIFO avec valeur physique et marquage

[!include [banner](../includes/banner.md)]


Le premier entré, le premier sorti (FIFO) désigne une méthode de gestion et d’évaluation des stocks dans laquelle les stocks qui sont produits ou acquis en premier sont vendus, utilisés ou éliminés en premier. Pendant le processus de clôture de l’inventaire dans Microsoft Dynamics 365 Supply Chain Management, le système crée des règlements où la première réception correspond à la première sortie, et ainsi de suite.

Le principe de règlement et de mise en correspondance est basé sur la date comptable des transactions d’inventaire. Une évaluation préliminaire des règlements et des ajustements peut être effectuée en exécutant le processus de recalcul de l’inventaire.

Vous pouvez ignorer le principe FIFO en marquant les mouvements de stock de manière ce qu’une réception d’article spécifique soit réglée avec une sortie spécifique. Une clôture d’inventaire périodique est requise lorsque vous utilisez le modèle d’inventaire FIFO pour créer des règlements et ajuster la valeur des sorties selon le principe FIFO. Jusqu’à ce que vous exécutiez le processus de clôture de stock, les transactions de sortie sont évaluées à la moyenne en vigueur lorsque les mises à jour physiques et financières ont eu lieu. À moins que vous n’utilisiez le marquage, la moyenne en vigueur est calculée lors de la mise à jour physique ou financière. Les exemples suivants illustrent l’impact du modèle FIFO dans trois configurations différentes :

- FIFO sans l’option **Inclure la valeur physique**
- FIFO avec l’option **Inclure la valeur physique**
- FIFO avec marquage

## <a name="fifo-without-the-include-physical-value-option"></a>FIFO sans l’option Inclure la valeur physique

Dans cet exemple, la case à cocher **Inclure la valeur physique** est décochée sur le groupe de modèles d’élément pour le produit lancé. La figure suivante illustre ces transactions :

- 1a. Réception physique en stock pour une quantité de 1 à un coût de 10,00 EUR chacune.
- 1b. Réception financière en stock pour une quantité de 1 à un coût de 10,00 EUR chacune.
- 2a. Réception physique en stock pour une quantité de 1 à un coût de 20,00 EUR chacune.
- 2b. Réception financière en stock pour une quantité de 1 à un coût de 22,00 EUR chacune.
- 3a. Sortie physique de stock pour une quantité de 1 à un prix de revient de 16,00 EUR (prix de revient moyen en vigueur des transactions validées financièrement).
- 3b. Sortie financière de stock pour une quantité de 1 à un prix de revient de 16,00 EUR (prix de revient moyen en vigueur des transactions mises à jour financièrement).
- 4a. Réception physique en stock pour une quantité 1 au coût unitaire de 25,00 EUR.
- 5a. Réception physique en stock pour une quantité de 1 à un coût de 30,00 EUR chacune.
- 5b. Réception financière en stock pour une quantité de 1 à un coût de 30,00 EUR chacune.
- 6a. Sortie physique de stock pour une quantité de 1 à un prix de revient de 23,00 EUR (prix de revient moyen en vigueur des transactions validées financièrement)
- 7\. La clôture du stock est effectuée. Selon la méthode FIFO, la première sortie mise à jour financièrement est réglée par rapport à la première réception mise à jour financièrement, etc. Dans cet exemple, un règlement est créé entre 1b et 3b. Un ajustement de -6,00 EUR sera effectué en 3b et le coût final résultant s’élèvera à 10,00 EUR.

Le nouveau prix de revient moyen en vigueur reflète la moyenne des transactions mises à jour financièrement. Les illustrations suivantes indiquent l’impact du modèle de stock FIFO sur cette série de transactions lorsque l’option **Inclure la valeur physique** n’est pas utilisée.

![FIFO sans l’option Inclure la valeur physique.](./media/fifo-without-include-physical-value.png)

**Clés du diagramme**

- Les mouvements de stock sont représentés par les flèches verticales.
- Les transactions physiques sont représentées par des flèches gris clair plus courtes.
- Les transactions financières sont représentées par des flèches noires plus longues.
- Les réceptions en stock sont représentées par les flèches verticales au-dessus de la ligne temporelle.
- Les sorties de stock sont représentées par les flèches verticales en dessous de la ligne temporelle.
- Chaque nouvelle transaction de réception ou de sortie est désignée par un nouveau libellé.
- Chaque flèche verticale est marquée par un identificateur séquentiel, comme *1a*. Les identificateurs indiquent l’ordre des validations des mouvements de stock sur la ligne temporelle.
- Chaque date du diagramme est séparée par une fine ligne verticale noire. La date est notée en bas du schéma.
- Les clôtures de stock sont représentées par une ligne pointillée verticale rouge.
- Les règlements effectués par clôture de stock sont représentés par des flèches rouges en diagonale d’une réception vers une sortie.

## <a name="fifo-with-the-include-physical-value-option"></a>FIFO avec l’option Inclure la valeur physique

Si la case à cocher **Inclure la valeur physique** est activée pour un article dans la page **Groupe de modèles d’article**, le système utilise à la fois les transactions de réception physique et financière pour calculer le prix de revient moyen en cours. Au besoin, le système ajuste la transaction de sortie mise à jour physiquement. La clôture de stock qui utilise le modèle de stock FIFO ne règle que les transactions financièrement mises à jour. La figure suivante illustre ces transactions :

- 1a. Réception physique en stock pour une quantité de 1 à un coût de 10,00 EUR chacune.
- 1b. Réception financière en stock pour une quantité de 1 à un coût de 10,00 EUR chacune.
- 2a. Réception physique en stock pour une quantité de 1 à un coût de 20,00 EUR chacune.
- 2b. Réception financière en stock pour une quantité de 1 à un coût de 22,00 EUR chacune.
- 3a. Sortie physique de stock pour une quantité de 1 à un prix de revient de 16,00 EUR (prix de revient moyen en vigueur des transactions validées financièrement et physiquement).
- 3b. Sortie financière de stock pour une quantité de 1 à un prix de revient de 16,00 EUR (prix de revient moyen en vigueur des transactions validées financièrement et physiquement).
- 4a. Réception physique en stock pour une quantité 1 au coût unitaire de 25,00 EUR.
- 5a. Réception physique en stock pour une quantité de 1 à un coût de 30,00 EUR chacune.
- 5b. Réception financière en stock pour une quantité de 1 à un coût de 30,00 EUR chacune.
- 6a. Sortie physique de stock pour une quantité de 1 à un prix de revient de 23,67 EUR (prix de revient moyen en vigueur des transactions validées financièrement et physiquement).
- 7\. La clôture du stock est effectuée. Selon la méthode FIFO, la première sortie mise à jour financièrement est réglée par rapport à la première réception mise à jour financièrement, etc. Dans cet exemple, un règlement est créé entre 1b et 3b. Un ajustement de -6,00 EUR sera effectué en 3b et le coût final résultant s’élèvera à 10,00 EUR. En outre, la transaction 6a sera ajustée sur le coût de la transaction de réception en 2b. Le système ne règlera pas ces transactions car la mise à jour de la réception s’effectue au niveau physique mais pas au niveau financier. Au lieu de cela, seul un ajustement de -1,67 EUR sera comptabilisé sur la transaction d’émission physique, et le coût ajusté résultant sera de 22,00 EUR.

![FIFO avec l’option Inclure la valeur physique.](./media/fifo-with-include-physical-value.png)

Notez que le résultat de l’exécution du processus de clôture de stock est le même, que vous sélectionniez ou non l’option **Inclure la valeur physique** sur la page **Groupe de modèles d’article**. L’option **Inclure la valeur physique** n’affecte que la moyenne en vigueur.

**Clés du diagramme**

- Les mouvements de stock sont représentés par les flèches verticales.
- Les transactions physiques sont représentées par des flèches gris clair plus courtes.
- Les transactions financières sont représentées par des flèches noires plus longues.
- Les réceptions en stock sont représentées par les flèches verticales au-dessus de la ligne temporelle.
- Les sorties de stock sont représentées par les flèches verticales en dessous de la ligne temporelle.
- Chaque nouvelle transaction de réception ou de sortie est désignée par un nouveau libellé.
- Chaque flèche verticale est marquée par un identificateur séquentiel, comme *1a*. Les identificateurs indiquent l’ordre des validations des mouvements de stock sur la ligne temporelle.
- Chaque date du diagramme est séparée par une fine ligne verticale noire. La date est notée en bas du schéma.
- Les clôtures de stock sont représentées par une ligne pointillée verticale rouge.
- Les règlements effectués par clôture de stock sont représentés par des flèches rouges en diagonale d’une réception vers une sortie.

## <a name="fifo-with-marking"></a>FIFO avec marquage

Le marquage est un processus qui vous permet de lier, ou de marquer, une transaction de sortie à une transaction de réception. Cette opération peut être effectuée avant ou après la validation d’une transaction. Vous pouvez utiliser le marquage si vous voulez être sûr du coût exact du stock lors de la validation de la transaction ou de l’exécution de la clôture de stock.

Par exemple, le service à la clientèle a accepté une commande urgente d’un client important. Comme il s’agit d’une commande urgente, vous devez payer plus cher pour cet article afin de satisfaire la demande de votre client. Vous devez vous assurer que le coût de cet article en stock se reflètera dans la marge, ou le coût des marchandises vendues (COGS), pour la facture de cette commande client. Lorsque la commande fournisseur est validée, le stock est reçu à un coût de 120,00 EUR. Si ce document de commande client est marqué par rapport à la commande fournisseur avant la validation du bon de livraison ou de la facture, le coût des marchandises vendues sera de 120,00 EUR, et non le coût moyen en vigueur de l’article. Si le bon de livraison ou la facture de la commande client est validée avant le marquage, le coût des marchandises vendues sera validé au prix de revient moyen en vigueur. Avant d’exécuter la clôture de stock, ces deux transactions peuvent encore être marquées l’une par rapport à l’autre.

Lorsqu’une transaction de réception correspond à une transaction de sortie, la méthode d’évaluation définie dans le groupe de modèles d’article est ignorée et le système règle ces transactions les unes avec les autres. Vous pouvez marquer manuellement une transaction par rapport à une ligne de commande client sur la page **Détails de la commande client** en sélectionnant **Inventaire \> Marquage** sur le raccourci **Lignes de commande client**. Les transactions de réception en cours sont affichées sur la page **Marquage**. Vous pouvez faire correspondre ou marquer une transaction de sortie par rapport à une transaction de réception en cours pour un article inventorié dans un journal d’ajustement de stock validé. La figure suivante illustre ces transactions :

- 1a. Réception physique en stock pour une quantité de 1 à un coût de 10,00 EUR chacune.
- 1b. Réception financière en stock pour une quantité de 1 à un coût de 10,00 EUR chacune.
- 2a. Réception physique en stock pour une quantité de 1 à un coût de 20,00 EUR chacune.
- 2b. Réception financière en stock pour une quantité de 1 à un coût de 22,00 EUR chacune.
- 3a. Sortie physique de stock pour une quantité de 1 à un prix de revient de 16,00 EUR (prix de revient moyen en vigueur des transactions validées financièrement).
- 3b. Sortie financière de stock pour une quantité de 1 à un prix de revient de 16,00 EUR (prix de revient moyen en vigueur des transactions mises à jour financièrement).
- 3c. La sortie financière de stock pour 3b est marquée comme sortie financière de stock pour 2b.
- 4a. Réception physique en stock pour une quantité 1 au coût unitaire de 25,00 EUR.
- 5a. Réception physique en stock pour une quantité de 1 à un coût de 30,00 EUR chacune.
- 5b. Réception financière en stock pour une quantité de 1 à un coût de 30,00 EUR chacune.
- 6a. Sortie physique de stock pour une quantité de 1 à un prix de revient de 23,00 EUR (prix de revient moyen en vigueur des transactions validées financièrement)
- 7\. La clôture du stock est effectuée. Selon le principe de marquage qui utilise la méthode FIFO, les transactions marquées sont réglées les unes par rapport aux autres. Dans cet exemple, 3b est réglé sur 2b, et un ajustement pour 6,00 EUR est posté sur 3b pour ramener la valeur à 22,00 EUR. Dans cet exemple, aucun règlement supplémentaire n’est effectué, car la clôture crée des règlements uniquement pour les transactions financièrement mises à jour.

Les illustrations suivantes montrent les effets du modèle de stock FIFO sur cette série de transactions quand le marquage entre les sorties et les réceptions est utilisé.

![FIFO avec marquage.](./media/fifo-with-marking.png)

**Clés du diagramme**

- Les mouvements de stock sont représentés par les flèches verticales.
- Les transactions physiques sont représentées par des flèches gris clair plus courtes.
- Les transactions financières sont représentées par des flèches noires plus longues.
- Les réceptions en stock sont représentées par les flèches verticales au-dessus de la ligne temporelle.
- Les sorties de stock sont représentées par les flèches verticales en dessous de la ligne temporelle.
- Chaque nouvelle transaction de réception ou de sortie est désignée par un nouveau libellé.
- Chaque flèche verticale est marquée par un identificateur séquentiel, comme *1a*. Les identificateurs indiquent l’ordre des validations des mouvements de stock sur la ligne temporelle.
- Chaque date du diagramme est séparée par une fine ligne verticale noire. La date est notée en bas du schéma.
- Les clôtures de stock sont représentées par une ligne pointillée verticale rouge.
- Les règlements et marquages effectués par clôture de stock sont représentés par des flèches rouges en diagonale d’une réception vers une sortie.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
