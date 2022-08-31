---
title: Clés de réduction des prévisions
description: Cet article fournit des exemples qui indiquent comment paramétrer une clé de réduction. Il inclut des informations sur les différents paramètres de clé de réduction et les résultats de chacun d’entre eux. Vous pouvez utiliser une clé de réduction pour définir la méthode permettant de réduire les besoins de prévision.
author: t-benebo
ms.date: 04/15/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ReqPlanSched, ReqReduceKeyDefaultDataWizard, ReqReduceKey
audience: Application User
ms.reviewer: kamaybac
ms.custom: 19251
ms.assetid: aa9e0dfb-6052-4a2e-9378-89507c02fdf2
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: benebotg
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: b7eaf57e0f02c0b9dd6454a58184db7bb3f58c04
ms.sourcegitcommit: 203c8bc263f4ab238cc7534d4dd902fd996d2b0f
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/23/2022
ms.locfileid: "9337134"
---
# <a name="forecast-reduction-keys"></a>Clés de réduction des prévisions

[!include [banner](../includes/banner.md)]

Cette section fournit des informations sur les différentes méthodes utilisées pour réduire les besoins prévisionnels. Elle présente des exemples de résultats de chaque méthode. Elle décrit également comment créer, paramétrer et utiliser une clé de réduction des prévisions. Certaines méthodes utilisent une clé de réduction de prévision pour réduire les besoins prévisionnels.

## <a name="methods-that-are-used-to-reduce-forecast-requirements"></a>Méthodes utilisées pour réduire les besoins prévisionnels

Lorsque vous incluez une prévision dans un plan général, vous pouvez sélectionner la façon dont les besoins prévisionnels sont réduits lors de l’inclusion de la demande réelle. Notez que la planification principale exclut les besoins de prévision du passé, à savoir tous les besoins de prévision avant la date d’aujourd’hui.

Pour inclure une prévision dans un plan général et sélectionner la méthode utilisée pour réduire les besoins prévisionnels, accédez à **Planification \> Paramétrage \> Plans \> Plans généraux**. Dans le champ **Modèle de prévision**, sélectionnez un modèle de prévision. Dans le champ **Méthode utilisée pour réduire les besoins prévisionnels**, sélectionnez une méthode. Les options disponibles sont les suivantes :

- Aucune
- Pourcentage – clé de réduction
- Transactions – clé de réduction
- Transactions – période dynamique

Les sections suivantes fournissent des informations supplémentaires sur chaque option.

### <a name="none"></a>Aucune

Si vous sélectionnez **Aucun(e)**, les besoins prévisionnels ne sont pas réduits lors du calcul PDP/MRP. Dans ce cas, la planification crée des ordres prévisionnels pour livrer la demande prévue (les besoins prévisionnels). Ces ordres prévisionnels conservent la quantité suggérée, indépendamment d’autres types de demande. Par exemple, si des commandes client sont passées, la planification crée des ordres prévisionnels supplémentaires pour fournir les commandes client. La quantité des besoins prévisionnels n’est pas réduite.

### <a name="percent--reduction-key"></a>Pourcentage – clé de réduction

Si vous sélectionnez **Pourcentage - clé de réduction**, les besoins prévisionnels sont réduits en fonction des pourcentages et périodes définis par la clé de réduction. Dans ce cas, la planification crée des ordres prévisionnels où la quantité est calculée comme quantité prévue × clé de réduction sur chaque période. S’il existe d’autres types de demande, la planification crée également des ordres prévisionnels pour fournir cette demande.

#### <a name="example-percent--reduction-key"></a>Exemple : Pourcentage – clé de réduction

Cet exemple décrit la manière dont une clé de réduction réduit les besoins de prévision de la demande en fonction des pourcentages et périodes définis par la clé de réduction.

Pour cet exemple, incluez la prévision de la demande suivante dans un plan général.

| Mois    | Prévision de la demande |
|----------|-----------------|
| Janvier  | 1 000           |
| Février | 1 000           |
| Mars    | 1 000           |
| Avril    | 1 000           |

Dans la page **Clés de réduction**, paramétrez les lignes suivantes.

| Monnaie | Unité  | Pourcentage |
|--------|-------|---------|
| 1      | Mois | 100     |
| 2      | Mois | 75      |
| 3      | Mois | 50      |
| 4      | Mois | 25      |

Affectez la clé de réduction au groupe de couverture de l’article. Ensuite, dans la page **Plans généraux**, dans le champ **Méthode utilisée pour réduire les besoins prévisionnels**, sélectionnez **Pourcentage - clé de réduction**.

Dans ce cas, si vous lancez le calendrier des prévisions le 1er janvier, les besoins de prévision de la demande sont utilisés en fonction des pourcentages définis dans la page **Clés de réduction**. Les quantités requises suivantes sont transférées vers le plan général.

| Mois                | Quantité d’ordre prévisionnel | Calcul    |
|----------------------|------------------------|----------------|
| Janvier              | 0                      | = 0 % × 1000   |
| Février             | 250                    | = 25 % × 1000  |
| Mars                | 500                    | = 50 % × 1000  |
| Avril                | 750                    | = 75 % × 1000  |
| Mai à décembre | 1 000                  | = 100 % × 1000 |

### <a name="transactions--reduction-key"></a>Transactions – clé de réduction

Si vous définissez le champ **Méthode utilisée pour réduire les besoins prévisionnels** sur *Transactions - clé de réduction*, les besoins prévisionnels sont réduits par les transactions de demande qualifiées qui se produisent pendant les périodes définies par la clé de réduction.

La demande qualifiée est définie par le champ **Réduire les prévisions de** sur la page **Groupes de couverture**. Si vous définissez le champ **Réduire les prévisions de** sur *Commandes*, seules les transactions de commande client sont considérées comme des demandes qualifiées. Si vous la définissez sur *Toutes les transactions*, toutes les transactions de sortie de stock autres qu’intersociétés sont considérées comme une demande qualifiée. Si les commandes client intersociétés doivent également être considérées comme une demande qualifiée, définissez l’option **Inclure les commandes intersociétés** sur *Oui*.

La réduction des prévisions commence avec le premier (le plus ancien) enregistrement de prévision de la demande dans la période de la clé de réduction. Si la quantité des transactions de stock qualifiées est supérieure à la quantité des lignes de prévision de la demande dans la même période de clé de réduction, le solde de la quantité des transactions de stock sera utilisé pour réduire la quantité de prévision de la demande dans la période précédente (s’il y a une prévision non consommée).

S’il ne reste aucune prévision non consommée dans la période de la clé de réduction précédente, le solde de la quantité des transactions de stock sera utilisé pour réduire la quantité prévue le mois suivant (s’il existe une prévision non consommée).

La valeur du champ **Pour cent** sur les lignes clés de réduction n’est pas utilisée lorsque le champ **Méthode utilisée pour réduire les besoins prévisionnels** est défini sur *Transactions - clé de réduction*. Seules les dates sont utilisées pour définir la période de clé de réduction.

> [!NOTE]
> Toute prévision publiée à la date du jour ou avant sera ignorée et ne sera pas utilisée pour créer des commandes planifiées. Par exemple, si votre prévision de la demande pour le mois est générée le 1er janvier et que vous exécutez une planification générale qui inclut la prévision de la demande du 2 janvier, le calcul ignorera la ligne de prévision de la demande datée du 1er janvier.

#### <a name="example-transactions--reduction-key"></a>Exemple : Transactions - clé de réduction

Cet exemple décrit la manière dont les commandes réelles, qui se produisent durant les périodes définies par la clé de réduction, réduisent les besoins de prévision de la demande.

Pour cet exemple, sélectionnez **Transactions - clé de réduction** dans le champ **Méthode utilisée pour réduire les besoins prévisionnels**, de la page **Plans généraux**.

Les commandes client suivantes sont prises en compte le 1er janvier.

| Mois    | Nombre de pièces commandées |
|----------|--------------------------|
| Janvier  | 956                      |
| Février | 1 176                    |
| Mars    | 451                      |
| Avril    | 119                      |

Si vous utilisez les mêmes prévisions de la demande de 1000 pièces par mois utilisées dans l’exemple précédent, les quantités requises suivantes sont transférées vers le plan général.

| Mois                | Nombre de pièces requises |
|----------------------|---------------------------|
| Janvier              | 44                        |
| Février             | 0                         |
| Mars                | 549                       |
| Avril                | 881                       |
| Mai à décembre | 1 000                     |

### <a name="transactions--dynamic-period"></a>Transactions – période dynamique

Si vous sélectionnez **Transactions - période dynamique**, les besoins prévisionnels sont réduits par les transactions de commande actuelles qui interviennent au cours de la période dynamique. La période dynamique couvre les dates de prévision actuelles et se termine au début de la prochaine prévision. Dans ce cas, la planification crée des ordres prévisionnels pour livrer la demande prévue (les besoins prévisionnels). Toutefois, lorsque des transactions de commande réelles sont passées, les besoins prévisionnels sont réduits. Les transactions réelles consomment une partie des besoins prévisionnels.

Lorsque cette option est utilisée, le comportement suivant se produit :

- Les clés de réduction ne sont pas requises ou ne sont pas utilisées. 
- Si la prévision est réduite complètement, les besoins prévisionnels actuels passent à 0 (zéro).
- En l’absence de prévision à venir, les besoins de la dernière prévision entrée sont réduits.
- La plage de gestion de la réduction de la prévision de la demande n’est pas incluse dans le calcul de la réduction de la prévision. Au lieu de cela, la plage horaire du groupe de couverture est utilisée pour la réduction des prévisions.
- Les jours positifs sont inclus dans le calcul de réduction des prévisions.
- Si les transactions de commande réelles dépassent les besoins prévisionnels, les transactions restantes ne sont pas expédiées à la période suivante de prévision.

#### <a name="example-1-transactions--dynamic-period"></a>Exemple 1 : Transactions - période dynamique

Voici un exemple simple qui montre le fonctionnement de la méthode **Transactions - période dynamique**.

Pour cet exemple, incluez la prévision de la demande suivante dans un plan général.

| Date       | Prévision de la demande |
|------------|-----------------|
| 1er janvier  | 1 000           |
| 1 février | 1 000             |

Créez également les commandes client suivantes.

| Date        | Quantité de la commande client |
|-------------|----------------------|
| 15 janvier  | 200                  |
| 15 février | 400                  |

Dans ce cas, les ordres prévisionnels suivants sont créés.

| Date de prévision de la demande | Quantité | Explication                           |
|--------------------- |----------|---------------------------------------|
| 1er janvier            | 800      | Besoins prévisionnels (= 1000 – 200) |
| 15 janvier           | 200      | Besoins pour les commandes client             |
| 1 février           | 600      | Besoins prévisionnels (= 1000 – 400) |
| 15 février          | 400      | Besoins pour les commandes client             |

#### <a name="example-2-transactions--dynamic-period"></a>Exemple 2 : Transactions - période dynamique

Dans la plupart des cas, les systèmes sont paramétrés de telle sorte que les transactions réduisent la prévision de la demande durant des périodes prévisionnelles spécifiques : semaines, mois, etc. Ces périodes sont définies dans la clé de réduction. Toutefois, la durée entre deux lignes de prévision de la demande peut également *impliquer* une période.

Pour cet exemple, créez une prévision de la demande pour les dates et les quantités suivantes.

| Date       | Prévision de la demande |
|------------|-----------------|
| 1er janvier  | 1 000           |
| 5 janvier  | 500             |
| 12 janvier | 1 000           |

Notez que, dans cette prévision, il n’existe pas de période précise entre les dates de prévision. La première et la deuxième date sont séparées par quatre jours, et la deuxième et la troisième date sont séparées par sept jours. Ces durées sont les périodes dynamiques.

Créez également les lignes de commande client suivantes.

| Date                             | Quantité de la commande client |
|----------------------------------|----------------------|
| 15 décembre de l’année précédente | 500                  |
| 3 janvier                        | 100                  |
| 10 janvier                       | 200                  |

Dans ce cas, la prévision est réduite de la façon suivante :

- Comme la première commande client n’est pas effectuée dans une période donnée, elle ne réduit aucune prévision.
- Comme la deuxième commande client est effectuée entre le 1er et le 5 janvier, elle réduit la prévision du 1er janvier de 100.
- Comme la troisième commande client est effectuée entre le 5 et le 12 janvier, elle réduit la prévision du 5 janvier de 200.

Par conséquent, les ordres prévisionnels suivants sont créés.

| Date de prévision de la demande             | Quantité | Explication                                                         |
|----------------------------------|----------|---------------------------------------------------------------------|
| 15 décembre de l’année précédente | 500      | Besoins de commande client                                            |
| 1er janvier                        | 900      | Besoins prévisionnels pour la période du 1er janvier au 5 janvier (= 1000 – 100) |
| 3 janvier                        | 100      | Besoins de commande client                                            |
| 5 janvier                        | 300      | Besoins prévisionnels pour la période du 5 janvier au 10 janvier (= 500 – 200)  |
| 12 janvier                       | 1 000    | Besoins prévisionnels pour la période du 12 janvier à fin janvier                      |

## <a name="create-and-set-up-a-forecast-reduction-key"></a>Création et paramétrage d’une clé de réduction de la prévision

Une clé de réduction des prévisions est utilisée dans les méthodes **Transactions - clé de réduction** et **Pourcentage - clé de réduction** pour réduire les besoins prévisionnels. Procédez comme suit pour créer et paramétrer une clé de réduction.

1. Accédez à **Planification \> Paramétrage \> Couverture \> Clés de réduction**.
2. Sélectionnez **Nouveau** pour créer une clé de réduction.
3. Dans le champ **Clé de réduction**, entrez un identificateur unique pour la clé de réduction des prévisions. Entrez ensuite un nom dans le champ **Nom**. 
4. Définissez les périodes et le pourcentage de clé de réduction dans chaque période :

    - Le champ **Date d’effet** indique la date de début de création de la période. Lorsque l’option **Utiliser la date d’effet** est définie sur **Oui**, la période débute à la date d’effet. Lorsqu’elle est définie **Non**, la période débute à la date d’exécution de la planification.
    - Définissez les périodes auxquelles la réduction des prévisions doit avoir lieu.
    - Pour une période spécifique, indiquez les pourcentages de réduction qui doivent être appliqués aux besoins prévisionnels. Vous pouvez entrer des valeurs positives pour réduire les besoins ou des valeurs négatives pour augmenter les besoins.

## <a name="use-a-reduction-key"></a>Utilisation d’une clé de réduction

Une clé de réduction des prévisions doit être affectée au groupe de couverture de l’article. Procédez comme suit pour affecter une clé de réduction au groupe de couverture d’un article.

1. Accédez à **Planification \> Paramétrage \> Couverture \> Groupes de couverture**.
2. Dans l’organisateur **Autres**, dans le champ **Clé de réduction**, sélectionnez la clé de réduction à affecter au groupe de couverture. La clé de réduction s’applique ensuite à tous les articles appartenant au groupe de couverture.
3. Pour utiliser une clé de réduction afin de calculer la réduction des prévisions lors du calcul PDP/MRP, vous devez définir ce paramètre dans le paramétrage du programme prévisionnel ou du plan général. Accédez à l’un des emplacements suivants :

    - Planification \> Paramétrage \> Plans \> Programmes prévisionnels
    - Planification \> Paramétrage \> Plans \> Plans généraux

4. Dans la page **Programmes prévisionnels** ou **Plans généraux**, sous l’organisateur **Général**, dans le champ **Méthode utilisée pour réduire les besoins prévisionnels**, sélectionnez **Pourcentage - clé de réduction** ou **Transactions - clé de réduction**.

## <a name="reduce-a-forecast-by-transactions"></a>Réduction de la prévision par les transactions

Lorsque vous sélectionnez **Transactions - clé de réduction** ou **Transactions - période dynamique** comme méthode de réduction des besoins prévisionnels, vous pouvez spécifier quelles transactions réduisent la prévision. Dans la page **Groupes de couverture**, sous l’organisateur **Autre**, dans le champ **Soustraire des prévisions**, sélectionnez **Toutes les transactions** si toutes les transactions doivent réduire la prévision ou **Commandes** si seules les commandes client doivent diminuer la prévision.

## <a name="additional-resources"></a>Ressources supplémentaires

[Vue d’ensemble des plans généraux](master-plans.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
