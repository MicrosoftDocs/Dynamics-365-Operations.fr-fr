---
title: Prix de revient moyen en cours
description: "La clôture du stock règle les transactions de sortie avec des transactions de réception, en fonction de la méthode d&quot;évaluation du stock sélectionné dans le groupe de modèles d&quot;article. Toutefois, avant d&quot;exécuter la clôture du stock, le système calcule un prix de revient moyen en cours généralement utilisé lorsque des transactions de sortie sont validées."
author: YuyuScheller
manager: AnnBe
ms.date: 2016-04-07 15 - 11 - 47
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: InventModelGroup, InventOnhandItem, InventTrans
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 79003
ms.assetid: adc3f245-dc9d-4327-88fb-6a579194a5fe
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: mguada
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 9ccbe5815ebb54e00265e130be9c82491aebabce
ms.openlocfilehash: 685dfaa877699db3c36cc1ea77d956461f8e68ec
ms.lasthandoff: 03/29/2017


---

# <a name="running-average-cost-price"></a>Prix de revient moyen en cours

La clôture du stock règle les transactions de sortie avec des transactions de réception, en fonction de la méthode d'évaluation du stock sélectionné dans le groupe de modèles d'article. Toutefois, avant d'exécuter la clôture du stock, le système calcule un prix de revient moyen en cours généralement utilisé lorsque des transactions de sortie sont validées.

Le système estime ce prix de revient moyen en cours pour un article à l'aide de la formule suivante : Prix estimé = (montant physique + montant financier) ÷ Produit (Quantité physique + quantité financière)

## <a name="using-the-running-average-cost-price"></a>Utiliser le prix de revient moyen en cours
Le tableau suivant affiche lorsque le système contrôle des mouvements de stock à l'aide de le prix de revient moyen en cours, et quand il utilise le prix de revient défini dans l'enregistrement de base de données d'articles à la place.

| Condition                                               | Le système utilise le prix de revient moyen en cours estimé | Le système utilise le prix de revient défini dans l'enregistrement principal de l'article |
|---------------------------------------------------------|----------------------------------------------------------|-------------------------------------------------------------------|
| Le numérateur\* et le dénominateur\*\* sont positifs.  | Oui                                                      | N°                                                                |
| Le numérateur\*, le dénominateur\*\*, ou les deux sont négatifs. | N°                                                       | Oui                                                               |
| Le dénominateur\*\* est 0 (zéro).                        | N°                                                       | Oui                                                               |

numérateur d'\* = (montant physique + montant financier) dénominateur d'\*\* = (quantité physique + quantité financière) ** note : ** Si ** Inclure la valeur physique ** l'option n'est pas sélectionnée pour un article, le système utilise 0 (zéro) pour le montant physique et la quantité physique. Pour plus d'informations sur cette option, voir [Inclure la valeur physique](include-physical-value.md).

## <a name="avoiding-pricing-amplification"></a>Éviter l'amplification de la tarification
Rares occasions, les prix système plusieurs sorties avant d'avoir suffisamment de réceptions pour baser le prix. Ce scénario peut entraîner le gonflement excessif des estimations du prix de revient moyen en cours. Toutefois, certaines mesures permettent d'éviter cette amplification de tarification ou d'en limiter l'impact quand elle survient. **Scénario** Les transactions suivantes ont lieu pour un article pour lequel vous avez sélectionné l'option **Inclure la valeur physique** :

1.  Vous recevez financièrement une quantité de 100 à 100,00 EUR.
2.  Vous sortez financièrement une quantité de 200.
3.  Vous recevez physiquement une quantité de 101 à 202,00 EUR.

Lorsque vous analysez le prix de revient moyen en cours estimé de l'article, vous vous attendez à un prix de revient à 1,51 EUR. Au lieu de cela, vous remarquez une moyen en cours estimé de 102,00 EUR, basé sur la formule suivante : Prix estimé = \[202 + (- 100) \[101 ÷\] + (- 100)\] = 102 ÷ 1 = 102 que cette amplification de tarification se produit car, lorsque 200 articles sont sortis financièrement à l'étape 2, le système doit le prix pour 100 articles avant d'avoir les réceptions correspondantes. Cette situation entraîne un stock négatif. Le système estime ensuite un prix unitaire de 1,00 EUR, comme on pouvait s'la prévision. Toutefois, lorsque les 100 réceptions correspondantes arrivent, elles sont au prix unitaire de 2,00 EUR chacune. **Remarque :** Bien que les sorties créent un stock négatif, le stock est positif lorsque le prix de sortie est calculé. Par conséquent, le prix de revient en cours est utilisé à la place du prix de l'enregistrement principal de l'article. À ce stade, le système a une valeur en stock de 100,00 USD. Bien que cette valeur ait été déterminée pour 100 pièces, alors que chacune valait 1,00 EUR, il ne reste qu'une seule pièce en stock. Par conséquent, la valeur de 100,00 EUR est affectée à cette unique pièce, Cela provoque la surestimation du prix de revient. **Remarque :** À titre de comparaison, notez que si les étapes 2 et 3 sont contrepassées dans le scénario, 200 articles seront sortis au prix unitaire de 1,51 EUR et une pièce restera au prix unitaire de 1,51 EUR. Comme ce scénario d'amplification de tarification peut se produire avec un stock négatif, il est difficile à éviter dans les cas suivants :

-   Vous devez estimer les prix de sortie sur la valeur et la quantité disponibles.
-   vous devez ajuster la valeur et la quantité disponibles sur les sorties et les réceptions.
-   Votre modèle commercial vous autorise la sortie ou la tarification de plus de pièces que vous n'en possédez.
-   Vous devez accepter toutes les valeurs et les quantités de réception qui vous sont soumises.

Toutefois, si votre modèle commercial les autorise, les pratiques suivantes vous permettent d'éviter les quantités négatives qui favorisent le scénario d'amplification de tarification :

-   Si vous sélectionnez l'option **Inclure la valeur physique** pour un article, désactivez la case à cocher **Stock physique négatif** dans la page **Groupes de modèles d'article**.
-   Si vous ne sélectionnez *pas* l'option **Inclure la valeur physique** pour un article, désactivez l'option **Stock physique négatif** dans la page **Groupes de modèles d'article**.

En outre, souvenez-vous que la valeur maximale de votre stock physique est limitée par le nombre de transactions physiques et la différence entre les prix physiques et financiers. À condition que l'ensemble des transactions physiques soit mis à jour financièrement à terme, la valeur physique ne peut pas atteindre des niveaux extrêmes. Enfin, notez que l'effet d'amplification diminue considérablement lorsque la valeur cumulée est répartie sur plusieurs pièces disponibles et non pas sur une seule.


