---
title: Planification avec prévisions d’approvisionnement
description: Cet article décrit comment les prévisions d’approvisionnement sont prises en compte lors de la planification générale.
author: t-benebo
ms.date: 09/21/2022
ms.topic: article
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2022-09-21
ms.dyn365.ops.version: 10.0.30
ms.openlocfilehash: 2bac9355bb1ac00f697ec459f494a64553e0eacc
ms.sourcegitcommit: 491ab9ae2b6ed991b4eb0317e396fef542d3a21b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/03/2022
ms.locfileid: "9740139"
---
# <a name="master-planning-with-supply-forecasts"></a>Planification avec prévisions d’approvisionnement

[!include [banner](../../includes/banner.md)]

Les prévisions d’approvisionnement vous permettent de spécifier l’approvisionnement dont vous pensez avoir besoin au cours d’une période future. En règle générale, vous baserez l’estimation sur l’historique des ventes de l’année précédente, puis vous utiliserez les prévisions à des fins de budgétisation. Vous pouvez également configurer vos plans directeurs pour tenir compte des prévisions lors de la planification.

## <a name="set-up-a-master-plan-to-consider-supply-forecasts"></a>Mettre en place un plan directeur pour tenir compte des prévisions d’approvisionnement

Vous pouvez spécifier si chaque plan directeur doit tenir compte des prévisions lors de son exécution. Utilisez la procédure suivante pour définir les options de prévision pour chaque plan.

1. Accédez à **Planification \> Paramétrage \> Plans \> Plans généraux**.
1. Sélectionnez un plan directeur existant dans le volet Liste ou sélectionnez **Nouveau** dans le volet Actions pour en créer un.
1. Dans l’organisateur **Général**, définissez les champs suivants :

    - **Modèle de prévision** : sélectionnez le modèle qui contient les prévisions d’approvisionnement et/ou de demande qui doivent être prises en compte par le plan directeur.
    - **Inclure la prévision de l’approvisionnement** – Définissez cette option sur *Oui* si le plan directeur doit tenir compte des prévisions d’approvisionnement.
    - **Inclure la prévision de la demande** : définissez cette option sur *Oui* si le plan directeur doit tenir compte des prévisions de la demande. Bien que ce réglage soit indépendant du paramètre **Inclure la prévision d’approvisionnement**, certains des autres paramètres de la page s’appliquent à la fois aux prévisions d’approvisionnement et aux prévisions de demande. Pour plus d’informations sur la planification qui tient compte des prévisions de la demande, voir [Planification générale avec prévisions de la demande](demand-forecast.md).
    - **Méthode utilisée pour réduire les besoins prévisionnels** – Sélectionnez la méthode à utiliser pour réduire les besoins prévisionnels pendant la planification générale :

        - *Aucun* : les besoins prévisionnels ne sont pas réduits lors de la planification générale.
        - *Pourcentage - clé de réduction* : les besoins prévisionnels sont réduits en fonction des pourcentages et périodes définis par la clé de réduction.
        - *Transactions - Clé de réduction* : les besoins prévisionnels sont réduits par les transactions qui surviennent au cours de périodes définies par la clé de réduction.
        - *Transactions - période dynamique* : les besoins prévisionnels sont réduits par les transactions de commande actuelles qui interviennent au cours de la période dynamique. La période dynamique couvre les dates de prévision actuelles et se termine au début de la prochaine prévision. La méthode *Transactions – période dynamique* n’utilise pas ou ne nécessite pas de clé de réduction, et lorsque vous l’utilisez, les conditions suivantes s’appliquent :

            - Si la prévision est réduite complètement, les besoins prévisionnels actuels passent à 0 (zéro).
            - En l’absence de prévision à venir, les besoins de la dernière prévision entrée sont réduits.
            - Les plages de gestion sont incluses dans le calcul de réduction des prévisions.
            - Les jours positifs sont inclus dans le calcul de réduction des prévisions.
            - Si les transactions de commande réelles dépassent les besoins prévisionnels, les transactions restantes ne sont pas expédiées à la période suivante de prévision.

        > [!NOTE]
        > Le paramètre **Méthode utilisée pour réduire les besoins prévisionnels** s’applique également aux prévisions de la demande si vous les avez activées pour le plan directeur, et il les affecte de la même manière. Pour plus d’informations, voir [Planification avec prévisions de la demande](demand-forecast.md).

## <a name="set-reduction-options-for-coverage-groups"></a>Définir les options de réduction pour les groupes de couverture

Pour définir des options qui contrôlent la manière dont un groupe de couverture réduit ses besoins prévisionnels pour les plans directeurs qui utilisent la réduction basée sur les transactions, procédez comme suit.

1. Accédez à **Planification \> Paramétrage \> Plans \> Groupes de couverture**.
1. Sélectionnez un groupe de couverture existant dans le volet de liste ou sélectionnez **Nouveau** dans le volet Actions pour en créer un.
1. Sur le raccourci **Autre**, dans le champ **Réduire les prévisions de**, spécifiez comment réduire les besoins de prévision d’approvisionnement pour les articles dans le groupe de couverture, pour les plans directeurs où le champ **Méthode utilisée pour réduire les besoins de prévision** est défini sur *Transactions - clé de réduction* ou *Transactions - période dynamique*. Sélectionnez l’une des valeurs suivantes :

    - *Toutes transactions* – Toutes les transactions doivent réduire les prévisions.
    - *Commandes* – Seules les commandes du même type devraient réduire la prévision.

    Par exemple, les paramètres de commande par défaut d’un article indiquent qu’il doit être produit. Il existe une ligne de prévision d’approvisionnement pour une quantité de 50 et une commande fournisseur existante pour une quantité de 20. Si le champ **Réduire les prévisions de** est défini sur *Commandes*, un ordre de fabrication prévisionnel est créé pour une quantité de 50. S’il est réglé sur *Toutes transactions*, l’ordre de fabrication planifié est réduit à une quantité de 30.

    Ce paramètre s’applique également à la réduction de la prévision de la demande. Pour plus d’informations, voir [Planification avec prévisions de la demande](demand-forecast.md).

## <a name="enter-a-supply-forecast-for-a-product"></a>Saisir une prévision d’approvisionnement pour un produit

Pour saisir une prévision d’approvisionnement pour un produit, procédez comme suit.

1. Allez à **Gestion des informations sur les produits \> Produits \> Produits lancés**.
1. Sélectionnez le produit pour lequel saisir une prévision.
1. Dans le volet Actions, sur l’onglet **Plan**, sélectionnez **Prévision d’approvisionnement**.
1. Sur la page **Prévision d’approvisionnement**, sur le volet Actions, sélectionnez **Nouveau** pour ajouter une prévision à la grille.
1. Saisissez les informations requises sur la nouvelle ligne pour spécifier votre prévision.

## <a name="plan-for-an-item-with-supply-forecast-lines"></a>Planifier un article avec des lignes de prévision d’approvisionnement

Lorsque vous exécutez un plan directeur qui inclut un article pour lequel une prévision d’approvisionnement existe, le système crée un bon de commande pour les lignes d’approvisionnement saisies. Les paramètres de commande par défaut de l’article sont respectés. Si ces paramètres de commande par défaut spécifient une valeur **Type de commande par défaut** définie sur *Commande fournisseur*, et qu’aucun compte fournisseur n’est spécifié sur la ligne de prévision d’approvisionnement, le système utilise le fournisseur par défaut pour l’article.

## <a name="check-whether-a-planned-order-is-a-supply-forecast-order"></a>Vérifier si un ordre planifié est un ordre de prévision d’approvisionnement

Utilisez la procédure suivante pour savoir si un ordre planifié a été créé à la suite d’une prévision d’approvisionnement.

1. Accédez à **Planification \> Planification \> Ordres prévisionnels**.
1. Ouvrez la commande planifiée que vous souhaitez inspecter.
1. Sur le raccourci **Général**, regardez la valeur du champ **Prévision d’approvisionnement**. Si la commande a été créée pour couvrir une prévision d’approvisionnement, ce champ est défini sur *Oui*.

## <a name="examples-of-master-planning-with-supply-forecasts"></a>Exemples de planification générale avec prévisions d’approvisionnement

Cette section fournit plusieurs exemples qui montrent comment la prévision d’approvisionnement affecte la planification générale.

### <a name="example-1-supply-forecast-for-an-item"></a>Exemple 1 : Prévision d’approvisionnement pour un article

Vous avez un article dont le type de commande par défaut est *Commande fournisseur* et le fournisseur par défaut est *US-002*. Il a la ligne de prévision d’approvisionnement suivante.

| Modèle    | Date     | Compte fournisseur | Groupe de fournisseurs | Quantity | Unité | Site | Entrepôt |
|----------|----------|----------------|--------------|----------|------|------|-----------|
| CurrentF | 10/10/22 |                |              | 35       | unité(s)   | 1    | 11        |

Lorsque vous exécutez la planification générale, une commande fournisseur prévisionnelle est créée pour *35 unités* du vendeur *US-002*.

### <a name="example-2-several-supply-forecast-lines-with-and-without-a-vendor"></a>Exemple 2 : Plusieurs lignes de prévision d’approvisionnement, avec et sans fournisseur

Vous avez un article dont le type de commande par défaut est *Commande fournisseur* et le fournisseur par défaut est *US-002*. Il a les lignes de prévision d’approvisionnement suivantes.

| Modèle    | Date     | Compte fournisseur | Groupe de fournisseurs | Quantity | Unité | Site | Entrepôt |
|----------|----------|----------------|--------------|----------|------|------|-----------|
| CurrentF | 10/10/22 |                |              | 35       | unité(s)   | 1    | 11        |
| CurrentF | 10/10/22 | US-101         |              | 25       | unité(s)   | 1    | 11        |

Dans ce cas, le système traite la ligne qui ne spécifie pas de fournisseur comme une prévision générique, et il suppose que la ligne qui spécifie un fournisseur doit être soustraite de la prévision générique. Par conséquent, la planification crée les ordres d’achat prévisionnels suivants pour l’article :

- Une commande d’achat prévisionnelle pour une quantité de *25 unités* du vendeur *US-101* (Le fournisseur et la quantité spécifiés sur la ligne de prévision sont utilisés.)
- Une commande d’achat prévisionnelle pour une quantité de *10 unités* du vendeur *US-002* (Étant donné qu’aucun fournisseur n’a été spécifié sur l’autre ligne de prévision, le fournisseur par défaut est utilisé et la quantité de cette ligne de prévision est réduite de la quantité de la ligne de prévision spécifique au fournisseur.)

### <a name="example-3-plans-that-use-the-transactions---dynamic-period-reduction-method-in-a-single-forecast-period"></a>Exemple 3 : Plans qui utilisent la méthode Transactions - réduction de période dynamique dans une seule période de prévision

Pour les schémas directeurs qui utilisent *Transactions - période dynamique* en tant que méthode de réduction des prévisions, la planification générale réduit les quantités prévues s’il existe des transactions existantes qui correspondent à ces caractéristiques d’approvisionnement.

Par exemple, vous avez un article dont le type de commande par défaut est *Commande fournisseur*. Il a la ligne de prévision d’approvisionnement suivante.

| Modèle    | Date     | Compte fournisseur | Groupe de fournisseurs | Quantity | Unité | Site | Entrepôt |
|----------|----------|----------------|--------------|----------|------|------|-----------|
| CurrentF | 10/10/22 | US-101         |              | 25       | unité(s)   | 1    | 11        |

Comme il n’y a qu’une seule ligne de prévision d’approvisionnement, il n’y a qu’une seule période de prévision.

Lorsque vous exécutez un plan directeur configuré pour utiliser *Transactions – période dynamique* comme méthode de réduction, l’un des résultats suivants peut se produire :

- Si un bon de commande existe pour le fournisseur *US-101* et une quantité de *10 unités*, et le champ **Prévision d’approvisionnement** champ est défini sur *Oui*, la planification crée une nouvelle commande d’achat prévisionnelle pour la quantité restante de *10 unités*. La ligne de prévision est réduite, car le fournisseur correspond à la commande fournisseur existante.
- Si un bon de commande existe pour le fournisseur *US-102*, le site *1*, l’entrepôt *11* et une quantité de *10 unités*, et le champ **Prévision d’approvisionnement** est défini sur *Oui*, la planification crée une nouvelle commande d’achat prévisionnelle pour la quantité restante de *25 unités*. La ligne de prévision ne peut pas être réduite, car elle a un fournisseur différent de celui de la commande fournisseur existante.

> [!NOTE]
> Cette situation peut se produire pour les commandes fournisseur planifiées, car un fournisseur leur est associé. Cependant, pour les ordres de transfert et les ordres de fabrication, les montants des prévisions d’approvisionnement sont toujours réduits des commandes existantes, car aucun fournisseur n’est spécifié pour ces types d’ordres.

### <a name="example-4-plans-that-use-the-transactions---dynamic-period-reduction-method-over-several-forecast-periods"></a>Exemple 4 : Plans qui utilisent la méthode Transactions - réduction de période dynamique dans plusieurs périodes de prévision

Vous avez un article dont le type de commande par défaut est *Commande fournisseur*. Il a les lignes de prévision d’approvisionnement suivantes.

| Modèle    | Date     | Compte fournisseur | Groupe de fournisseurs | Quantity | Unité | Site | Entrepôt |
|----------|----------|----------------|--------------|----------|------|------|-----------|
| CurrentF | 10/10/22 | US-101         |              | 25       | unité(s)   | 1    | 11        |
| CurrentF | 15/10/22 | US-101         |              | 25       | unité(s)   | 1    | 11        |

Dans cet exemple, il y a deux lignes de prévision, chacune ayant une date différente. Par conséquent, les dates établissent les limites des périodes de prévision. La première période est du 10 octobre au 14 octobre 2022 (10/10/22–14/10/22). La seconde est à partir du 15 octobre 2022 (15/10/22).

Il existe une commande fournisseur existante pour le fournisseur *US-101*, une quantité de *10 unités*, et la date *12/10/22* (12 octobre 2022). Lorsque vous exécutez un plan directeur configuré pour utiliser *Transactions – période dynamique* comme méthode de réduction, l’un des ordres suivants est généré :

- Un ordre planifié pour une quantité de *15 unités* et la date *10/10/22* (La quantité est réduite par la commande fournisseur existante datée de la même période de prévision.)
- Un ordre planifié pour une quantité de *25 unités* et la date *15/10/22* (La quantité correspond à la quantité totale de la prévision.)

### <a name="example-5-plans-that-use-no-reduction"></a>Exemple 5 : Plans qui n’utilisent aucune réduction

Lorsque vous exécutez un plan où la méthode de réduction des prévisions est définie *Aucune*, la planification générale crée toujours un approvisionnement planifié pour toutes les lignes de prévision d’approvisionnement. Une fois que cet approvisionnement planifié a été approuvé, il réduit les futurs ordres planifiés. Cependant, les commandes fournisseur ne réduisent pas les lignes de prévision d’approvisionnement.

Par exemple, vous avez un article dont le type de commande par défaut est *Commande fournisseur*. Il a la ligne de prévision d’approvisionnement suivante.

| Modèle    | Date     | Compte fournisseur | Groupe de fournisseurs | Quantity | Unité | Site | Entrepôt |
|----------|----------|----------------|--------------|----------|------|------|-----------|
| CurrentF | 10/10/22 | US-101         |              | 25       | unité(s)   | 1    | 11        |

Il existe une commande fournisseur existante pour le fournisseur *US-101*, le site *1*, l’entrepôt *11*, une quantité de *25 unités*, et la date *10/10/22*. 

Lorsque vous exécutez un plan directeur configuré pour n’utiliser *Aucune* méthode de réduction, il génère une commande fournisseur prévisionnelle pour le fournisseur *US-101*, le site *1*, l’entrepôt *11*, une quantité de *25 unités* et la date *10/10/22*. En d’autres termes, la commande fournisseur existante n’est pas réduite, car la méthode de réduction prévisionnelle est définie sur *Aucune*.

Vous traitez maintenant la commande fournisseur prévisionnelle qui a été créée après la dernière planification et modifiez la quantité sur *15 unités*. Vous approuvez ensuite la commande. La prochaine fois que vous exécutez le plan directeur, il génère une commande fournisseur prévisionnelle pour le fournisseur *US-101*, le site *1*, l’entrepôt *11*, une quantité de *10 unités* et la date *10/10/22*. Cette fois, la quantité est réduite pour refléter la quantité de la commande approuvée existante de l’exécution de planification précédente.

## <a name="differences-between-planning-optimization-and-the-deprecated-master-planning-engine"></a>Différences entre l’optimisation de la planification et le moteur de planification générale déprécié

Les prévisions d’approvisionnement fonctionnent de manière légèrement différente, selon le moteur de planification générale que vous utilisez (optimisation de la planification ou moteur de planification générale déprécié). Cette section décrit les différences.

### <a name="vendor-groups"></a>Groupes de fournisseurs

Lorsque vous ajoutez une ligne de prévision, vous pouvez spécifier un fournisseur et un groupe de fournisseurs. Dans le moteur de planification générale déprécié, les ordres planifiés qui sont créés sont regroupés selon la combinaison des valeurs de fournisseur et de groupe de fournisseurs. Dans l’optimisation de la planification, les ordres planifiés sont regroupés par fournisseur.

Le tableau suivant fournit quelques exemples de lignes de prévision d’approvisionnement pour un article.

| Modèle    | Date     | Compte fournisseur | Groupe de fournisseurs | Quantity | Unité | Site | Entrepôt |
|----------|----------|----------------|--------------|----------|------|------|-----------|
| CurrentF | 10/10/22 |                | VendorGroupA | 5        | unité(s)   | 1    | 11        |
| CurrentF | 10/10/22 |                | VendorGroupA | 6        | unité(s)   | 1    | 11        |
| CurrentF | 10/10/22 |                |              | 7        | unité(s)   | 1    | 11        |

Le fournisseur *VendorA* est le fournisseur par défaut pour le groupe de fournisseurs *VendorGroupA*. Il s’agit également du fournisseur par défaut pour l’article.

Le moteur de planification générale déprécié créera les commandes suivantes :

- Une commande fournisseur prévisionnelle pour le fournisseur *VendorA*, le groupe de fournisseurs *VendorGroupA*, et une quantité définie sur *11*
- Une commande fournisseur prévisionnelle pour le fournisseur *VendorA* et une quantité définie sur *7*

L’optimisation de la planification crée une seule commande :

- Une commande fournisseur prévisionnelle pour le fournisseur *VendorA*, le groupe de fournisseurs *VendorGroupA*, et une quantité définie sur *18*

### <a name="reduction-of-general-forecasts-by-more-specific-forecasts"></a>Réduction des prévisions générales par des prévisions plus spécifiques

Dans le moteur de planification générale déprécié, le résultat est imprévisible si certaines prévisions ont un fournisseur, mais pas d’autres.

Dans l’optimisation de la planification, les prévisions générales sont toujours réduites par des prévisions plus spécifiques, comme le montre l’exemple suivant.

Le tableau suivant fournit quelques exemples de lignes de prévision d’approvisionnement pour un article.

| Date       | Quantity | Fournisseur   | Groupe de fournisseurs  |
|------------|----------|----------|---------------|
| 11/02/2022 | 5.00     | Vendor-A | VendorGroup-A |
| 11/02/2022 | 6,00     | Vendor-A | VendorGroup-A |
| 11/02/2022 | 15.00    |          |               |

La prévision générale (pour 15 pièces) est diminuée des prévisions plus spécifiques (pour 5 + 6 = 11 pièces). Le reste est affecté au fournisseur par défaut. Le tableau suivant présente les ordres planifiés.

| Date       | Quantity | Fournisseur   | Groupe de fournisseurs  |
|------------|----------|----------|---------------|
| 11/02/2022 | 11.00    | Vendor-A | VendorGroup-A |
| 11/02/2022 | 4.00     | Vendor-A | VendorGroup-A |

### <a name="respect-for-default-order-settings-when-planned-orders-are-generated"></a>Respect des paramètres de commande par défaut lors de la génération des ordres planifiés

Chaque article peut avoir des paramètres de commande par défaut, comme une quantité minimale de commande fournisseur. Le moteur de planification générale déprécié ignore ces paramètres et convertit donc les prévisions en ordres planifiés ayant la même quantité. L’optimisation de planification respecte ces paramètres lorsque les ordres planifiés sont générés à partir des prévisions d’approvisionnement. 

### <a name="aggregation-of-planned-orders-as-a-result-of-reduction-by-approved-orders"></a>Agrégation d’ordres planifiés suite à une réduction par des ordres approuvés

Le moteur de planification générale déprécié suppose qu’une seule commande réduit la prévision d’approvisionnement existante. Ainsi, si plusieurs commandes correspondent à une ligne de prévision d’approvisionnement, seule la première commande la réduit. Dans l’optimisation de la planification, toutes les commandes qui correspondent à la ligne de prévision d’approvisionnement la réduisent.

### <a name="reduction-of-forecasts-by-matching-vendors-only"></a>Réduction des prévisions en ne faisant correspondre que les fournisseurs

Lorsque le moteur de planification générale déprécié réduit une prévision par des commandes fournisseur lancées existantes, il ne garantit pas que le fournisseur de la commande fournisseur corresponde au fournisseur de la prévision. L’optimisation de la planification réduit les prévisions uniquement par les commandes fournisseur qui ont une valeur correspondante dans le champ fournisseur.

Pour les ordres de transfert et de production, le champ fournisseur est toujours ignoré, car il n’est pas pertinent pour ces types d’ordres.

### <a name="reduction-of-forecasts-by-transfer-orders"></a>Réduction des prévisions par ordres de transfert

Si le type de commande par défaut pour un article est *Transférer*, les prévisions ne peuvent être réduites que par des ordres de transfert planifiés existants. Cependant, pour les ordres de fabrication et les commandes fournisseur, seuls les ordres lancés réduisent la prévision d’approvisionnement.

Le moteur de planification générale déprécié réduit pour tous les états d’ordre de transfert, tandis que l’optimisation de la planification réduit les prévisions uniquement par les ordres de transfert définis à l’état *Lancé*.
