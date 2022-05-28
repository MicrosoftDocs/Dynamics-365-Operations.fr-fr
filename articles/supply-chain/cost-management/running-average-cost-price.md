---
title: Prix de revient moyen en cours
description: La clôture du stock règle les transactions de sortie avec des transactions de réception sur la base du modèle d’évaluation du stock sélectionné dans le groupe de modèles d’article associé à l’article. Toutefois, avant d’exécuter la clôture du stock, le système calcule un prix de revient moyen en cours qui est généralement utilisé lorsque les transactions de sortie sont validées.
author: JennySong-SH
ms.date: 02/02/2022
ms.topic: article
ms.search.form: InventModelGroup, InventOnhandItem, InventTrans
audience: Application User
ms.reviewer: kamaybac
ms.custom: 79003
ms.search.region: Global
ms.author: yanansong
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 3d324324312ce9e47b07de8e3de952b8d7c53647
ms.sourcegitcommit: 9166e531ae5773f5bc3bd02501b67331cf216da4
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/03/2022
ms.locfileid: "8672176"
---
# <a name="running-average-cost-price"></a>Prix de revient moyen en cours

[!include [banner](../includes/banner.md)]

La clôture du stock règle les transactions de sortie avec des transactions de réception sur la base du modèle d’évaluation du stock sélectionné dans le groupe de modèles d’article associé à l’article. Toutefois, avant d’exécuter la clôture du stock, le système calcule un prix de revient moyen en cours qui est généralement utilisé lorsque les transactions de sortie sont validées.

Le système estime ce prix de revient moyen en cours pour un article à l’aide de la formule suivante :

Prix estimé = (montant physique + montant financier) / (quantité physique + quantité financière)

## <a name="default-item-cost"></a>Coût de l’article par défaut

Le coût de l’article par défaut pour un produit lancé peut être configuré de deux manières sur la page **Détails des produits lancés** :

- Créez un coût standard en sélectionnant **Prix de l’article** dans le groupe **Paramétrer** sur l’onglet **Gérer les coûts** du volet Actions. Si vous utilisez cette méthode, vous devez utiliser une version d’évaluation du coût de revient standard et le coût doit être activé.
- Définissez un prix de revient d’article par défaut pour un produit lancé en saisissant une valeur dans le champ **Prix** sur le raccourci **Gérer les coûts**.

Outre la saisie ou la création d’un prix, vous pouvez cocher la case **Utiliser le dernier prix de revient** sur le raccourci **Gérer les coûts** de la page **Détails des produits lancés**. Dans ce cas, le système mettra automatiquement à jour le champ **Prix** lorsque vous publiez une mise à jour financière. Par exemple, si vous validez une facture de bon de commande, le champ sera défini sur le prix d’achat de cette facture.

Si vous avez un prix de revient dans une version d’évaluation des coûts active et que vous saisissez un prix sur le raccourci **Gérer les coûts**, le système utilisera le prix de la version d’évaluation des coûts active avant d’utiliser le prix défini sur le raccourci **Gérer les coûts**.

## <a name="using-the-running-average-cost-price"></a>Utiliser le prix de revient moyen en cours

Le tableau suivant montre quand le système valide les transactions de stock en utilisant le prix de revient moyen en cours et quand il utilise plutôt le prix de revient défini dans l’enregistrement principal de l’article.

| Condition | Le système utilise le prix de revient moyen en cours estimé | Le système utilise le prix de revient de l’article par défaut |
| --- | --- | --- |
| Le numérateur\* et le dénominateur\*\* sont tous les deux positifs. | Oui | N° |
| Le numérateur\*, le dénominateur\*\*, ou les deux sont négatifs. | Non | Oui |
| Le dénominateur\*\* est 0 (zéro). | Non | Oui |

\* Numérateur = (Montant physique + Montant financier)  
\*\* Dénominateur = (Quantité physique + Quantité financière)

> [!NOTE]
> Si l’option **Inclure la valeur physique** n’est pas sélectionnée pour un article, le système utilise 0 (zéro) pour le montant physique et la quantité physique. Pour plus d’informations sur cette option, voir [Inclure la valeur physique](include-physical-value.md).

## <a name="avoiding-pricing-amplification"></a>Éviter l’amplification de la tarification

Rarement, le système estime plusieurs sorties avant d’avoir les réceptions suffisantes sur lesquelles baser un prix. Ce scénario peut entraîner le gonflement excessif des estimations du prix de revient moyen en cours. Toutefois, certaines mesures permettent d’éviter cette amplification de tarification ou d’en limiter l’impact quand elle survient.

**Scénario :** Les transactions suivantes ont lieu pour un article pour lequel vous avez sélectionné l’option **Inclure la valeur physique** :

1. Vous recevez financièrement une quantité de 100 à 100,00 EUR.
2. Vous sortez financièrement une quantité de 200.
3. Vous recevez physiquement une quantité de 101 à 202,00 EUR.

Lorsque vous analysez le prix de revient moyen en cours estimé de l’article, vous vous attendez à un prix de revient à 1,51 EUR. Au lieu de cela, vous découvrez un prix moyen en cours estimé de 102,00 EUR basé sur la formule suivante :

Prix estimé = \[202 + (-100)\] ÷ \[101 + (-100)\] = 102 ÷ 1 = 102

Cette amplification du prix se produit, car, lorsque 200 articles sont sortis financièrement à l’étape 2, le système doit fixer un prix pour 100 articles avant d’avoir les réceptions correspondantes, Cette situation entraîne un stock négatif. Le système estime ensuite un prix unitaire de 1,00 EUR, comme que nous pouvions le prévoir. Toutefois, lorsque les 100 réceptions correspondantes arrivent, elles sont au prix unitaire de 2,00 EUR chacune.

> [!NOTE]
> Bien que les sorties créent un stock négatif, le stock est positif lorsque le prix de sortie est calculé. Par conséquent, le prix de revient en cours est utilisé à la place du prix de l’enregistrement principal de l’article. À ce stade, le système a un décalage de valeur en stock de 100,00 EUR. Bien que cette valeur ait été déterminée pour 100 pièces, alors que chacune valait 1,00 EUR, il ne reste qu’une seule pièce en stock. Par conséquent, la valeur de 100,00 EUR est affectée à cette unique pièce, Cela provoque la surestimation du prix de revient.
>
> À titre de comparaison, notez que si les étapes 2 et 3 sont contrepassées dans le scénario, 200 articles seront sortis au prix unitaire de 1,51 EUR et une pièce restera au prix unitaire de 1,51 EUR. Comme ce scénario d’amplification de tarification peut se produire avec un stock négatif, il est difficile à éviter dans les cas suivants :
>
> - Vous devez estimer les prix de sortie sur la valeur et la quantité disponibles.
> - vous devez ajuster la valeur et la quantité disponibles sur les sorties et les réceptions.
> - Votre modèle commercial vous autorise la sortie ou la tarification de plus de pièces que vous n’en possédez.
> - Vous devez accepter toutes les valeurs et les quantités de réception qui vous sont soumises.

Toutefois, si votre modèle commercial les autorise, les pratiques suivantes vous permettent d’éviter les quantités négatives qui favorisent le scénario d’amplification de tarification :

- Si vous sélectionnez l’option **Inclure la valeur physique** pour un article, désactivez la case à cocher **Stock physique négatif** dans la page **Groupes de modèles d’article**.
- Si vous ne sélectionnez **pas** l’option **Inclure la valeur physique** pour un article, désactivez l’option **Stock physique négatif** dans la page **Groupes de modèles d’article**.

En outre, souvenez-vous que la valeur maximale de votre stock physique est limitée par le nombre de transactions physiques et la différence entre les prix physiques et financiers. À condition que l’ensemble des transactions physiques soit mis à jour financièrement à terme, la valeur physique ne peut pas atteindre des niveaux extrêmes. Enfin, notez que l’effet d’amplification diminue considérablement lorsque la valeur cumulée est répartie sur plusieurs pièces disponibles et non pas sur une seule.

## <a name="avoid-a-zero-cost-price-on-issues"></a>Éviter un prix de revient nul sur les sorties

Quand l’option **Inclure la valeur physique** n’est pas sélectionnée sur la page **Groupe de modèles d’article**, une sortie de stock peut avoir un prix de revient nul s’il n’y a pas de réception financièrement mise à jour dans le stock. Pour éviter un tel scénario, envisagez les options suivantes :

- Sélectionnez l’option **Inclure la valeur physique** sur la page **Groupe de modèles d’article**. Cette option empêchera un prix de revient nul sur une sortie, à condition que le ticket de caisse soit physiquement mis à jour. Si vous n’autorisez pas l’inventaire physique négatif, les sorties calculeront la moyenne courante à partir des transactions physiquement mises à jour.
- Créez un prix de revient d’article par défaut en activant une version d’évaluation des coûts ayant un coût standard, ou entrez le prix sur le raccourci **Gérer les coûts** de la page **Détails des produits lancés**. Cette option est préférable lorsque l’option **Inclure la valeur physique** n’est pas sélectionnée sur la page **Groupe de modèles d’article**, car le système aura toujours un prix de secours à utiliser.
- Sélectionnez l’option **Utiliser le dernier prix de revient** sur le raccourci **Gérer les coûts** de la page **Détails des produits lancés**. Cette option conservera le champ **Prix** à jour chaque fois que vous mettez à jour financièrement une réception. Si vous sélectionnez cette option, mais que vous ne saisissez pas de prix par défaut ou n’activez pas de coût dans une version d’évaluation des coûts standard, vous pouvez toujours avoir un coût nul sur une sortie.

Si vous avez des transactions de sortie sans aucun coût, le processus *Clôture et ajustement des stocks* corrige le prix de revient en créant un ajustement après la mise à jour financière des réceptions. Gardez à l’esprit que la période financière au cours de laquelle cette mise à jour se produit peut différer de la période financière au cours de laquelle les éléments ont été physiquement reçus ou émis.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
