---
title: Prix de revient moyen en cours
description: La clôture du stock règle les transactions de sortie avec des transactions de réception sur la base du modèle d'évaluation du stock sélectionné dans le groupe de modèles d'article associé à l'article. Toutefois, avant d'exécuter la clôture du stock, le système calcule un prix de revient moyen en cours qui est généralement utilisé lorsque les transactions de sortie sont validées.
author: AndersGirke
manager: tfehr
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventModelGroup, InventOnhandItem, InventTrans
audience: Application User
ms.reviewer: kamaybac
ms.custom: 79003
ms.assetid: adc3f245-dc9d-4327-88fb-6a579194a5fe
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: mguada
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 776f886fc0dfccf1b2675c9d54d44c16c6df4f09
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4963761"
---
# <a name="running-average-cost-price"></a>Prix de revient moyen en cours

[!include [banner](../includes/banner.md)]

La clôture du stock règle les transactions de sortie avec des transactions de réception sur la base du modèle d'évaluation du stock sélectionné dans le groupe de modèles d'article associé à l'article. Toutefois, avant d'exécuter la clôture du stock, le système calcule un prix de revient moyen en cours qui est généralement utilisé lorsque les transactions de sortie sont validées.

Le système estime ce prix de revient moyen en cours pour un article à l'aide de la formule suivante : 

Prix estimé = (montant physique + montant financier) / (quantité physique + quantité financière)

## <a name="using-the-running-average-cost-price"></a>Utiliser le prix de revient moyen en cours
Le tableau suivant montre quand le système valide les transactions de stock en utilisant le prix de revient moyen en cours et quand il utilise plutôt le prix de revient défini dans l'enregistrement principal de l'article.

| Condition                                               | Le système utilise le prix de revient moyen en cours estimé | Le système utilise le prix de revient défini dans l'enregistrement principal de l'article |
|---------------------------------------------------------|----------------------------------------------------------|-------------------------------------------------------------------|
| Le numérateur\* et le dénominateur\*\* sont tous les deux positifs.  | Oui                                                      | N°                                                                |
| Le numérateur\*, le dénominateur\*\*, ou les deux sont négatifs. | N°                                                       | Oui                                                               |
| Le dénominateur\*\* est 0 (zéro).                        | N°                                                       | Oui                                                               |

\* Numérateur = (montant physique + montant financier) \*\* Dénominateur = (quantité physique + quantité financière) 

**Remarque :** si l'option **Inclure la valeur physique** n'est pas sélectionnée pour un article, le système utilise 0 (zéro) pour le montant physique et la quantité physique. Pour plus d'informations sur cette option, voir [Inclure la valeur physique](include-physical-value.md).

## <a name="avoiding-pricing-amplification"></a>Éviter l'amplification de la tarification
Rarement, le système estime plusieurs sorties avant d'avoir les réceptions suffisantes sur lesquelles baser un prix. Ce scénario peut entraîner le gonflement excessif des estimations du prix de revient moyen en cours. Toutefois, certaines mesures permettent d'éviter cette amplification de tarification ou d'en limiter l'impact quand elle survient. **Scénario** Les transactions suivantes ont lieu pour un article pour lequel vous avez sélectionné l'option **Inclure la valeur physique** :

1.  Vous recevez financièrement une quantité de 100 à 100,00 EUR.
2.  Vous sortez financièrement une quantité de 200.
3.  Vous recevez physiquement une quantité de 101 à 202,00 EUR.

Lorsque vous analysez le prix de revient moyen en cours estimé de l'article, vous vous attendez à un prix de revient à 1,51 EUR. Au lieu de cela, vous découvrez un prix moyen en cours estimé de 102,00 EUR basé sur la formule suivante : prix estimé = \[202 + (-100)\] ÷ \[101 + (-100)\] = 102 ÷ 1 = 102 Cette amplification de tarification se produit car, lorsque 200 articles sont sortis financièrement à l'étape 2, le système doit évaluer le prix de 100 articles avant d'avoir toutes les réceptions correspondantes. Cette situation entraîne un stock négatif. Le système estime ensuite un prix unitaire de 1,00 EUR, comme que nous pouvions le prévoir. Toutefois, lorsque les 100 réceptions correspondantes arrivent, elles sont au prix unitaire de 2,00 EUR chacune. 

**Remarque :** Bien que les sorties créent un stock négatif, le stock est positif lorsque le prix de sortie est calculé. Par conséquent, le prix de revient en cours est utilisé à la place du prix de l'enregistrement principal de l'article. À ce stade, le système a un décalage de valeur en stock de 100,00 EUR. Bien que cette valeur ait été déterminée pour 100 pièces, alors que chacune valait 1,00 EUR, il ne reste qu'une seule pièce en stock. Par conséquent, la valeur de 100,00 EUR est affectée à cette unique pièce, Cela provoque la surestimation du prix de revient. 

**Remarque :** À titre de comparaison, notez que si les étapes 2 et 3 sont contrepassées dans le scénario, 200 articles seront sortis au prix unitaire de 1,51 EUR et une pièce restera au prix unitaire de 1,51 EUR. Comme ce scénario d'amplification de tarification peut se produire avec un stock négatif, il est difficile à éviter dans les cas suivants :

-   Vous devez estimer les prix de sortie sur la valeur et la quantité disponibles.
-   vous devez ajuster la valeur et la quantité disponibles sur les sorties et les réceptions.
-   Votre modèle commercial vous autorise la sortie ou la tarification de plus de pièces que vous n'en possédez.
-   Vous devez accepter toutes les valeurs et les quantités de réception qui vous sont soumises.

Toutefois, si votre modèle commercial les autorise, les pratiques suivantes vous permettent d'éviter les quantités négatives qui favorisent le scénario d'amplification de tarification :

-   Si vous sélectionnez l'option **Inclure la valeur physique** pour un article, désactivez la case à cocher **Stock physique négatif** dans la page **Groupes de modèles d'article**.
-   Si vous ne sélectionnez *pas* l'option **Inclure la valeur physique** pour un article, désactivez l'option **Stock physique négatif** dans la page **Groupes de modèles d'article**.

En outre, souvenez-vous que la valeur maximale de votre stock physique est limitée par le nombre de transactions physiques et la différence entre les prix physiques et financiers. À condition que l'ensemble des transactions physiques soit mis à jour financièrement à terme, la valeur physique ne peut pas atteindre des niveaux extrêmes. Enfin, notez que l'effet d'amplification diminue considérablement lorsque la valeur cumulée est répartie sur plusieurs pièces disponibles et non pas sur une seule.





[!INCLUDE[footer-include](../../includes/footer-banner.md)]