---
title: Moyenne mobile
description: La moyenne de déplacement est une méthode d’évaluation des coûts définitive basée sur le principe de moyenne, où les coûts des sorties de stock ne changent pas lorsque le coût d’achat est modifié. La différence est capitalisée et est basée sur un calcul proportionnel. Le montant restant est mis en dépenses.
author: JennySong-SH
ms.date: 08/28/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: InventModelGroup
audience: Application User
ms.reviewer: kamaybac
ms.custom: 65531
ms.assetid: dfd10099-8f7f-44b1-917e-df37c2fe8773
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: yanansong
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 0be72c8ba3c123300be83513531d2f805dc8f5e3
ms.sourcegitcommit: 9166e531ae5773f5bc3bd02501b67331cf216da4
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/03/2022
ms.locfileid: "8676101"
---
# <a name="moving-average"></a>Moyenne mobile

[!include [banner](../includes/banner.md)]

La moyenne de déplacement est une méthode d’évaluation des coûts définitive basée sur le principe de moyenne, où les coûts des sorties de stock ne changent pas lorsque le coût d’achat est modifié. La différence est capitalisée et est basée sur un calcul proportionnel. Le montant restant est mis en dépenses.

Lorsque vous utilisez la moyenne de déplacement, les règlements de stock et le marquage du stock ne sont pas pris en charge. La clôture du stock n’affecte pas les produits qui ont une moyenne de déplacement comme le groupe de modèles de stock et elle ne génère pas de règlement entre les transactions.

Voici les conditions préalables à respecter lorsque vous utilisez le coût de la moyenne de déplacement en tant que méthode d’évaluation des coûts.

1. Sur la page **Groupes de modèles d’article**, paramétrez un groupe de modèles d’article ayant une **moyenne mobile** sélectionnée dans le champ **Modèle de stock**.

    > [!NOTE]
    > Par défaut, lorsque la **moyenne mobile** est sélectionnée, les champs **Valider le stock physique** et **Valider le stock financier** sont également sélectionnés.

1. Sur la page **Validation**, attribuez des comptes à la **Différence de prix pour la moyenne mobile**. Vous utilisez le compte **Différence de prix pour la moyenne mobile** lorsque le coût doit être proportionnellement dépensé. Cela se produit dans les deux scénarios suivants :
    - Il existe une différence de coût entre un reçu d’achat et la facture d’achat, en raison d’une différence entre la quantité de stock d’origine et la quantité disponible actuelle.
    - Les transactions font passer le stock de négatif à zéro, et il y a une différence entre le coût de transaction et le coût moyen mobile actuel.

1. Sur la page **Validation**, affectez des comptes aux comptes **Différence de prix pour la moyenne mobile** sur l’onglet **Stock**. Utilisez le compte **Réévaluation des coûts pour la moyenne de déplacement** lorsque vous souhaitez ajuster le coût moyen mobile pour un produit avec un nouveau prix unique.

1. Sur la page **Produits lancés**, affectez le groupe de modèles d’article de la moyenne de déplacement au produit.

    > [!NOTE]
    > Le processus de clôture de stock clôture uniquement la période comptable. Il n’affecte pas les produits auxquels une moyenne de déplacement a été affectée en tant que groupe de modèles d’article.

## <a name="convert-to-the-moving-average-costing-method"></a>Convertir en méthode d’évaluation des coûts de la moyenne de déplacement

Les produits peuvent être convertis pour utiliser la méthode d’évaluation de stock de la moyenne de déplacement. Ce type de conversion est généralement effectué à la fin de l’année, après la clôture du dernier mois de l’exercice en cours. Il est exécuté à l’aide du modèle d’évaluation des coûts actuel du produit. Vous pouvez convertir votre méthode d’évaluation des coûts du stock en passant d’une méthode d’évaluation des coûts basée sur le coût moyen ou standard à une méthode basée sur la moyenne de déplacement.

Si vous passez d’une méthode d’évaluation des coûts standard à une méthode de moyenne de déplacement, vous devez effectuer les tâches suivantes :

1. Effectuer des ajustements pour obtenir des quantités et des valeurs de stock nulles.
1. Une fois que la valeur et la quantité du stock sont nulles, convertissez le groupe de modèles d’article en moyenne de déplacement.
1. Effectuer des ajustements pour que la quantité et la valeur soient réintégrées dans le stock.

Vous ne pouvez pas modifier votre méthode d’évaluation des coûts du stock en passant d’une méthode de moyenne de déplacement à une méthode FIFO (« dernier entré, premier sorti ») ou à une méthode de moyenne pondérée.

> [!NOTE]
> La conversion du coût standard en moyenne pondérée est un processus manuel.

Les exemples suivants illustrent les conséquences de l’utilisation de la méthode d’évaluation des coûts de la moyenne de déplacement. Il existe quatre configurations :

- Commande fournisseur et différence de coût mis en dépenses de façon proportionnelle
- Produit de la moyenne de déplacement et ajustement du stock
- Moyenne de déplacement avec production
- Moyenne de déplacement avec une transaction antidatée

## <a name="purchase-order-and-proportionally-expensed-cost-difference"></a>Commande fournisseur et différence de coût mis en dépenses de façon proportionnelle

Avec la moyenne de déplacement, le coût du produit est déterminé par le reçu d’achat. Lorsque la facture d’achat est validée, s’il y a une différence de coût entre le reçu d’achat et la facture d’achat, la différence est ajustée de façon proportionnelle aux produits actuels en stock et les montants restants sont mis en dépenses.

Dans cet exemple, une commande fournisseur est créée et reçue avec un certain coût, et la facture d’achat est validée avec un coût différent.

1. Créez une commande fournisseur pour une quantité de 2 et un prix unitaire de 10,00.
1. Créez un reçu d’achat du produit.
1. Créez une commande client pour une quantité de 1 et un prix unitaire de 10,00.
1. Créez une facture d’achat pour une quantité de 2 et un prix unitaire de 12,00.

La différence entre le prix unitaire, 2,00, est validée sur le compte Différence de prix pour la moyenne de déplacement lorsque la facture d’achat est validée. Cela est dû au fait que les deux produits ont été achetés pour un coût de 20,00. L’un des produits a été vendu au prix unitaire de 10,00. La facture d’achat a été validée à un prix unitaire de 12,00 avec une quantité de 2. Le prix unitaire du produit ne peut pas être validé avec la valeur 14,00.

## <a name="moving-average-product-and-inventory-adjustment"></a>Produit de la moyenne de déplacement et ajustement du stock

Si vous devez ajuster le coût de la moyenne de déplacement d’un produit, des ajustements du stock sont autorisés à partir de la date du jour. Vous ne pouvez pas antidater un ajustement de stock pour corriger le coût de la moyenne de déplacement d’un produit. Le coût ne peut pas transiter via des transactions qui se suivent.

Dans cet exemple, le coût de la moyenne de déplacement est ajusté pour un produit.

1. Sélectionnez le produit pour lequel ajuster le coût de la moyenne mobile. 

 > [!NOTE]
 > La page **Réévaluation de la moyenne de déplacement** examine le stock disponible pour un produit. Le produit sélectionné est associé à une quantité de 1, une valeur validée de 12,00, un coût unitaire validé de 12,00 et un coût unitaire de 12,00.
    
1. Mettez à présent à jour le champ **Coût unitaire** sur 16,00. Le système calcule les autres champs.
1. L’ajustement est validé.

> [!NOTE]
> Vous pouvez uniquement ajuster le coût de la moyenne de déplacement à partir de la date du jour.

Sur la page **Règlement pour le N° document**, vous pouvez afficher un ajustement de 4,00 validé dans le compte Réévaluation des coûts pour la moyenne de déplacement.

## <a name="moving-average-with-production"></a>Moyenne de déplacement avec production

La moyenne de déplacement prend en charge les articles produits. Si vous envisagez d’utiliser la moyenne mobile dans un environnement de production, sélectionnez **Utiliser le prix de revient estimé** sur la page **Paramètres de contrôle de la production**. Cela signifie que le prix de revient calculé durant l’estimation est utilisé à la place du prix de revient réel de calcul de nomenclature.

## <a name="moving-average-with-a-backdated-transaction"></a>Moyenne de déplacement avec une transaction antidatée

Le coût actuel de la moyenne de déplacement est affecté aux transactions antidatées et la quantité physique du produit est mise à jour, mais le coût de la moyenne de déplacement du produit n’est pas affecté. Dans cet exemple de moyenne de déplacement, une transaction antidatée pour un produit de moyenne de déplacement est validée.

1. Créez un ajustement du stock du produit de la moyenne de déplacement pour une quantité de 1 et un coût de 20,00.
1. L’historique des transactions de stock pour le produit se présente de la manière suivante :
    - Un mouvement de stock de 1, un coût de 16,00, une date de validation au 15 janvier et une date de transaction au 15 janvier.
    - Un ajustement de stock de 1, un coût de 20,00, une date de validation au 1 janvier et une date de transaction au 15 janvier.
1. Validez l’ajustement.

Sur la page **Mouvements de stock**, vous pouvez voir qu’une valeur de 4,00 mise en dépenses comme moyenne de déplacement actuelle du produit est 16,00. Vous pouvez valider à une date passée, mais la différence de coût est mise en dépenses de sorte que le coût de la moyenne de déplacement n’est pas affecté.

## <a name="negative-inventory-balances"></a>Soldes de stock négatifs

Les transactions sont gérées différemment selon que la nouvelle quantité en stock après la transaction est négative, nulle ou positive.

### <a name="new-balance-is-negative-or-zero"></a>Le nouveau solde est négatif ou nul

Si la nouvelle quantité en stock est négative ou nulle, la transaction est valorisée aux coûts moyens actuels. S’il y a une différence entre le prix d’achat et les coûts moyens actuels, elle est enregistrée dans **Différence de prix pour la moyenne mobile**.

### <a name="new-balance-is-positive"></a>Le nouveau solde est positif

Si la nouvelle quantité en stock est positive après la transaction, la transaction est divisée en deux parties et évaluée différemment, comme le résume le tableau suivant.

| Pièce | Description |
|---|---|
| Quantité de négatif à zéro | Le stock utilise le coût moyen mobile actuel de l’article plutôt que le coût de transaction pour la partie de la quantité de réception qui fait passer le solde en stock de négatif à zéro. La différence entre le coût de transaction et le coût de la moyenne de déplacement actuel est validée sur **Différence de prix pour la moyenne mobile**. |
| Quantité de zéro à négatif | Le stock utilise le coût de transaction pour la partie de la quantité de réception qui fait passer le solde en stock de zéro à positif.                                                  |

## <a name="inventory-value-report"></a>État de valeur de stock

Dans cet exemple de moyenne de déplacement, l’état Valeur en stock est imprimé pour prendre en charge le calcul actuel de la moyenne de déplacement pour un produit. La valeur du stock peut imprimer les transactions dans l’ordre chronologique, ainsi que le coût, pour prendre en charge le calcul du coût de la moyenne de déplacement d’un produit. L’état affiche le coût de la moyenne de déplacement du produit. Dans la boîte de dialogue **États de valeur de stock**, un intervalle de dates vous permet de sélectionner **Heure de la transaction** ou **Date de validation** pour le tri de l’état. L’option **Date de validation** permet de voir comment l’état est généralement imprimé. L’option **Heure de transaction** est la date réelle à laquelle la transaction est déclarée et le coût de la moyenne de déplacement du produit est mis à jour. Vous pouvez imprimer la valeur du stock à l’aide de l’option **Tri par heure de transaction** si vous souhaitez voir le calcul du coût de la moyenne de déplacement au fil du temps. Le tableau suivant affiche les transactions pour le produit pour lequel l’état est imprimé lorsque l’option de tri **Tri par heure de transaction** est utilisée.

| Heure de transaction | Date         | Type de transaction           | la quantité ; | Montant | Coût unitaire moyen |
|------------------|--------------|----------------------------|----------|--------|-------------------|
|                  | 1 octobre    | Solde d’ouverture          | 0        | 0,00   | 0,00              |
| 8 octobre        | 28 septembre | Réception postdatée          | 1        | 16,00  | 16,00             |
| 3 octobre        | 3 octobre    | Reçu d’achat           | 2        | 20,00  | 12,00             |
| 5 octobre        | 5 octobre    | commande client                | -1       | -10,00 | 13,00             |
| 7 octobre        | 7 octobre    | Facture d’achat           |          | 2,00   | 14,00             |
| 8 octobre        | 8 octobre    | Réévaluation de la moyenne mobile |          | 4.00   | 16.00             |
|                  | 31 octobre   | Total                      | 2        | 32.00  | 16.00             |

> [!NOTE]
> Vous ne pouvez pas rapprocher la comptabilité avec le stock à l’aide de l’option de tri **Tri par heure de transaction**. L’état doit être imprimé à l’aide de l’option **Date de validation**.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]