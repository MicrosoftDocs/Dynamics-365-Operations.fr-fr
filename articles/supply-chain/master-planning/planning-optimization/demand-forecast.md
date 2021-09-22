---
title: Planification avec prévisions de la demande
description: Cette rubrique explique comment inclure des prévisions de demande lors de la planification avec l’Optimisation de la planification.
author: ChristianRytt
ms.date: 12/02/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ReqPlanSched, ReqGroup, ReqReduceKey, ForecastModel
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2020-12-02
ms.dyn365.ops.version: AX 10.0.13
ms.openlocfilehash: 0f322dd63cb2dee6a9048e6ed086dc075cc0e1b9
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/07/2021
ms.locfileid: "7474842"
---
# <a name="master-planning-with-demand-forecasts"></a>Planification avec prévisions de la demande

[!include [banner](../../includes/banner.md)]

Vous pouvez utiliser une prévision de la demande avec l’Optimisation de la planification pour tenir compte de la demande prévue dans votre planification. Vous pouvez créer manuellement une prévision de la demande, l’importer ou la générer à l’aide de la fonctionnalité de prévision de la demande de Microsoft Dynamics 365 Supply Chain Management. Pour plus d’informations sur la prévision de la demande, voir [Présentation de la prévision de la demande](../introduction-demand-forecasting.md).

> [!NOTE]
> La planification des prévisions distincte n’est pas prise en charge avec l’Optimisation de la planification. Par conséquent, le paramètre **Planification prévisionnelle actuelle** sur la page **Paramètres de planification** n’a aucun effet lorsque vous utilisez l’Optimisation de la planification.

## <a name="set-up-a-master-plan-to-include-a-demand-forecast"></a>Mettre en place un plan directeur pour inclure une prévision de la demande

Pour configurer un plan directeur afin qu’il inclue une prévision de la demande, procédez comme suit.

1. Accédez à **Planification \> Paramétrage \> Plans \> Plans généraux**.
1. Sélectionnez un plan existant ou créez un plan.
1. Dans l’organisateur **Général**, définissez les champs suivants :

    - **Modèle de prévision** – Sélectionnez le modèle de prévision à appliquer. Ce modèle sera pris en compte lorsqu’une proposition d’approvisionnement est générée pour le plan directeur actuel.
    - **Inclure la prévision de la demande** – Définissez cette option sur *Oui* pour inclure la prévision de la demande dans le plan général actuel. Si vous le définissez sur *Non*, les transactions de prévision de la demande ne seront pas incluses dans le plan directeur.
    - **Méthode utilisée pour réduire les besoins prévisionnels** – Sélectionnez la méthode à utiliser pour réduire les besoins prévisionnels. Pour plus d’informations, voir la section [Clés de réduction des prévisions](#reduction-keys) située plus loin dans cette rubrique.

1. Sur le raccourci **Plage de temps en jours**, vous pouvez définir les champs suivants pour spécifier la période pendant laquelle la prévision de la demande est incluse :

    - **Plan prévisionnel** – Réglez cette option sur *Oui* pour remplacer la plage de temps du plan prévisionnel qui provient des groupes de couverture individuels. Réglez-le sur *Non* pour utiliser les valeurs des groupes de couverture individuels pour le plan directeur actuel.
    - **Période de prévision** – Si vous définissez l’option **Plan prévisionnel** sur *Oui*, spécifiez le nombre de jours (à partir de la date d’aujourd’hui) pendant lesquels la prévision de la demande doit être appliquée.

    > [!IMPORTANT]
    > Le paramètre **Plan prévisionnel** n’est pas pris en charge avec l’Optimisation de la planification.

## <a name="set-up-a-coverage-group-to-include-a-demand-forecast"></a>Mettre en place un groupe de couverture pour inclure une prévision de la demande

Pour configurer un groupe de couverture afin qu’il inclue une prévision de la demande, procédez comme suit.

1. Accédez à **Planification \> Paramétrage \> Plans \> Groupes de couverture**.
1. Sélectionnez un groupe de couverture existant ou créez un groupe.
1. Dans l’organisateur **Autres**, définissez les champs suivants :

    - **Période du plan de prévision** – Saisissez le nombre de jours (à partir de la date d’aujourd’hui) pendant lesquels la prévision de la demande doit être appliquée. Cette valeur peut être remplacée en utilisant l’option **Plan prévisionnel** sur le plan directeur, comme décrit dans la section précédente.
    - **Clé de réduction** – Sélectionnez la clé de réduction à appliquer. Pour plus d’informations, consultez les sections [Créer et configurer une clé de réduction des prévisions](#create-reduction-key) et [Utiliser une clé de réduction](#use-reduction-key) plus loin dans cette rubrique.
    - **Réduire les prévisions de** – Pour les plans directeurs où le champ **Méthode utilisée pour réduire les besoins de prévision** est défini sur *Transactions – clé de réduction* ou *Transactions – période dynamique*, spécifiez les transactions qui devraient réduire la prévision. Vous devez sélectionner l’une des valeurs suivantes :

        - **Toutes transactions** – Toutes les transactions doivent réduire les prévisions.
        - **Commandes** – Seules les commandes client devraient réduire la prévision.

        > [!NOTE]
        > Si vous sélectionnez *Toutes transactions*, les transactions qui ont à la fois la demande et l’offre dans les mêmes dimensions de stock sont considérées comme neutres et sont ignorées pendant la réduction prévue. Par exemple, si la dimension de planification est définie sur site uniquement, pas sur entrepôt, un ordre de transfert entre le site 1, l’entrepôt 11 et le site 1, l’entrepôt 13, sera ignoré et ne réduira pas la prévision de la demande restante.

    - **Inclure les commandes intersociétés** – Réglez cette option sur *Oui* si les commandes intersociétés doivent être incluses lorsque la prévision est réduite. Sinon, réglez-le sur *Non*.
    - **Inclure les prévisions client dans la prévision de la demande** – Indiquez si une prévision client doit être incluse dans la prévision globale. Cette option détermine la façon dont la demande réelle réduit la demande prévue. Utilisez-le pour vérifier que la planification couvre l’approvisionnement en articles achetés par des clients spécifiques.

        - Définissez cette option sur *Oui* pour inclure une prévision client dans la prévision globale. Dans ce cas, la demande réelle du client réduit à la fois la prévision client et la prévision globale. La planification génère des ordres prévisionnels pour couvrir uniquement la quantité de prévision globale.
        - Définissez cette option sur *Non* si vous ne souhaitez pas inclure une prévision client dans la prévision globale. Dans ce cas, la demande réelle du client réduit uniquement les prévisions du client. La planification génère des ordres prévisionnels pour couvrir la quantité globale de prévision et la prévision pour chaque quantité du client.

## <a name="forecast-reduction-keys"></a><a name="reduction-keys"></a>Clés de réduction des prévisions

Cette section fournit des informations sur les différentes méthodes utilisées pour réduire les besoins prévisionnels. Elle présente des exemples de résultats de chaque méthode. Elle décrit également comment créer, paramétrer et utiliser une clé de réduction des prévisions. Certaines méthodes utilisent une clé de réduction de prévision pour réduire les besoins prévisionnels.

### <a name="methods-that-are-used-to-reduce-forecast-requirements"></a>Méthodes utilisées pour réduire les besoins prévisionnels

Lorsque vous incluez une prévision dans un plan général, vous pouvez sélectionner la façon dont les besoins prévisionnels sont réduits lors de l’inclusion de la demande réelle. Notez que la planification principale exclut les besoins de prévision du passé, à savoir tous les besoins de prévision avant la date d’aujourd’hui.

Pour inclure une prévision dans un plan général et sélectionner la méthode utilisée pour réduire les besoins prévisionnels, accédez à **Planification \> Paramétrage \> Plans \> Plans généraux**. Dans le champ **Modèle de prévision**, sélectionnez un modèle de prévision. Dans le champ **Méthode utilisée pour réduire les besoins prévisionnels**, sélectionnez une méthode. Les options suivantes sont disponibles :

- None
- Pourcentage – clé de réduction
- Transactions – clé de réduction (pas encore prise en charge avec l’Optimisation de la planification)
- Transactions – période dynamique

Les sections suivantes fournissent des informations supplémentaires sur chaque option.

#### <a name="none"></a>Aucune

Si vous sélectionnez **Aucun(e)**, les besoins prévisionnels ne sont pas réduits lors du calcul PDP/MRP. Dans ce cas, la planification crée des ordres prévisionnels pour livrer la demande prévue (les besoins prévisionnels). Ces ordres prévisionnels conservent la quantité suggérée, indépendamment d’autres types de demande. Par exemple, si des commandes client sont passées, la planification crée des ordres prévisionnels supplémentaires pour fournir les commandes client. La quantité des besoins prévisionnels n’est pas réduite.

#### <a name="percent--reduction-key"></a>Pourcentage – clé de réduction

Si vous sélectionnez **Pourcentage - clé de réduction**, les besoins prévisionnels sont réduits en fonction des pourcentages et périodes définis par la clé de réduction. Dans ce cas, la planification crée des ordres prévisionnels où la quantité est calculée comme quantité prévue × clé de réduction sur chaque période. S’il existe d’autres types de demande, la planification crée également des ordres prévisionnels pour fournir cette demande.

##### <a name="example-percent--reduction-key"></a>Exemple : Pourcentage – clé de réduction

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

#### <a name="transactions--reduction-key"></a>Transactions – clé de réduction

Si vous définissez le champ **Méthode utilisée pour réduire les besoins prévisionnels** sur *Transactions - clé de réduction*, les besoins prévisionnels sont réduits par les transactions de demande qualifiées qui se produisent pendant les périodes définies par la clé de réduction.

La demande qualifiée est définie par le champ **Réduire les prévisions de** sur la page **Groupes de couverture**. Si vous définissez le champ **Réduire les prévisions de** sur *Commandes*, seules les transactions de commande client sont considérées comme des demandes qualifiées. Si vous la définissez sur *Toutes les transactions*, toutes les transactions de sortie de stock autres qu'intersociétés sont considérées comme une demande qualifiée. Si les commandes client intersociétés doivent également être considérées comme une demande qualifiée, définissez l'option **Inclure les commandes intersociétés** sur *Oui*.

La réduction des prévisions commence avec le premier (le plus ancien) enregistrement de prévision de la demande dans la période de la clé de réduction. Si la quantité des transactions de stock qualifiées est supérieure à la quantité des lignes de prévision de la demande dans la même période de clé de réduction, le solde de la quantité des transactions de stock sera utilisé pour réduire la quantité de prévision de la demande dans la période précédente (s'il y a une prévision non consommée).

S'il ne reste aucune prévision non consommée dans la période de la clé de réduction précédente, le solde de la quantité des transactions de stock sera utilisé pour réduire la quantité prévue le mois suivant (s'il existe une prévision non consommée).

La valeur du champ **Pour cent** sur les lignes clés de réduction n'est pas utilisée lorsque le champ **Méthode utilisée pour réduire les besoins prévisionnels** est défini sur *Transactions - clé de réduction*. Seules les dates sont utilisées pour définir la période de clé de réduction.

> [!NOTE]
> Toute prévision publiée à la date du jour ou avant sera ignorée et ne sera pas utilisée pour créer des commandes planifiées. Par exemple, si votre prévision de la demande pour le mois est générée le 1er janvier et que vous exécutez une planification générale qui inclut la prévision de la demande du 2 janvier, le calcul ignorera la ligne de prévision de la demande datée du 1er janvier.

##### <a name="example-transactions--reduction-key"></a>Exemple : Transactions - clé de réduction

Cet exemple décrit la manière dont les commandes réelles, qui se produisent durant les périodes définies par la clé de réduction, réduisent les besoins de prévision de la demande.

[![Commandes réelles et prévisions avant l'exécution de la planification générale.](media/forecast-reduction-keys-1-small.png)](media/forecast-reduction-keys-1.png)

Pour cet exemple, sélectionnez *Transactions - clé de réduction* dans le champ **Méthode utilisée pour réduire les besoins prévisionnels**, de la page **Plans généraux**.

Les lignes de prévision de la demande suivantes existent au 1er avril.

| Date     | Nombre de pièces prévu |
|----------|-----------------------------|
| 5 avril  | 100                         |
| 12 avril | 100                         |
| 19 avril | 100                         |
| 26 avril | 100                         |
| mai 3    | 100                         |
| mai 10   | 100                         |
| mai 17   | 100                         |

Les lignes de commande client suivantes existent en avril.

| Date     | Nombre de pièces demandé |
|----------|----------------------------|
| 27 avril | 240                        |

[![Approvisionnement prévu généré sur la base des commandes d'avril.](media/forecast-reduction-keys-2-small.png)](media/forecast-reduction-keys-2.png)

Les quantités de besoin suivantes sont transférées au plan général lors de l'exécution de la planification générale le 1er avril. Comme vous le voyez, les transactions prévues d'avril ont été réduites de la quantité demandée de 240 dans une séquence, à partir de la première de ces transactions.

| Date     | Nombre de pièces requises |
|----------|---------------------------|
| 5 avril  | 0                         |
| 12 avril | 0                         |
| 19 avril | 60                        |
| 26 avril | 100                       |
| 27 avril | 240                       |
| mai 3    | 100                       |
| mai 10   | 100                       |
| mai 17   | 100                       |

Maintenant, supposons que de nouvelles commandes ont été importées pour la période de mai.

Les lignes de commande client suivantes existent en mai.

| Date   | Nombre de pièces demandé |
|--------|----------------------------|
| mai 4  | 80                         |
| mai 11 | 130                        |

[![Approvisionnement prévu généré sur la base des commandes d'avril et de mai.](media/forecast-reduction-keys-3-small.png)](media/forecast-reduction-keys-3.png)

Les quantités de besoin suivantes sont transférées au plan général lors de l'exécution de la planification générale le 1er avril. Comme vous le voyez, les transactions prévues d'avril ont été réduites de la quantité demandée de 240 dans une séquence, à partir de la première de ces transactions. Cependant, les transactions de prévision de mai ont été réduites de 210 au total, à partir de la première transaction de prévision de la demande en mai. Cependant, les totaux par période sont conservés (400 en avril et 300 en mai).

| Date     | Nombre de pièces requises |
|----------|---------------------------|
| 5 avril  | 0                         |
| 12 avril | 0                         |
| 19 avril | 60                        |
| 26 avril | 100                       |
| 27 avril | 240                       |
| mai 3    | 0                         |
| mai 4    | 80                        |
| mai 10   | 0                         |
| mai 11   | 130                       |
| mai 17   | 90                        |

#### <a name="transactions--dynamic-period"></a>Transactions – période dynamique

Si vous sélectionnez **Transactions - période dynamique**, les besoins prévisionnels sont réduits par les transactions de commande actuelles qui interviennent au cours de la période dynamique. La période dynamique couvre les dates de prévision actuelles et se termine au début de la prochaine prévision. Dans ce cas, la planification crée des ordres prévisionnels pour livrer la demande prévue (les besoins prévisionnels). Toutefois, lorsque des transactions de commande réelles sont passées, les besoins prévisionnels sont réduits. Les transactions réelles consomment une partie des besoins prévisionnels.

Lorsque cette option est utilisée, le comportement suivant se produit :

- Les clés de réduction ne sont pas requises ou ne sont pas utilisées. 
- Si la prévision est réduite complètement, les besoins prévisionnels actuels passent à 0 (zéro).
- En l’absence de prévision à venir, les besoins de la dernière prévision entrée sont réduits.
- Les plages de gestion sont incluses dans le calcul de réduction des prévisions.
- Les jours positifs sont inclus dans le calcul de réduction des prévisions.
- Si les transactions de commande réelles dépassent les besoins prévisionnels, les transactions restantes ne sont pas expédiées à la période suivante de prévision.

##### <a name="example-1-transactions--dynamic-period"></a>Exemple 1 : Transactions - période dynamique

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

##### <a name="example-2-transactions--dynamic-period"></a>Exemple 2 : Transactions - période dynamique

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

### <a name="create-and-set-up-a-forecast-reduction-key"></a><a name="create-reduction-key"></a>Création et paramétrage d’une clé de réduction de la prévision

Une clé de réduction des prévisions est utilisée dans les méthodes **Transactions - clé de réduction** et **Pourcentage - clé de réduction** pour réduire les besoins prévisionnels. Procédez comme suit pour créer et paramétrer une clé de réduction.

1. Accédez à **Planification \> Paramétrage \> Couverture \> Clés de réduction**.
2. Sélectionnez **Nouveau** pour créer une clé de réduction.
3. Dans le champ **Clé de réduction**, entrez un identificateur unique pour la clé de réduction des prévisions. Entrez ensuite un nom dans le champ **Nom**. 
4. Définissez les périodes et le pourcentage de clé de réduction dans chaque période :

    - Le champ **Date d’effet** indique la date de début de création de la période. Lorsque l’option **Utiliser la date d’effet** est définie sur **Oui**, la période débute à la date d’effet. Lorsqu’elle est définie **Non**, la période débute à la date d’exécution de la planification.
    - Définissez les périodes auxquelles la réduction des prévisions doit avoir lieu.
    - Pour une période spécifique, indiquez les pourcentages de réduction qui doivent être appliqués aux besoins prévisionnels. Vous pouvez entrer des valeurs positives pour réduire les besoins ou des valeurs négatives pour augmenter les besoins.

### <a name="use-a-reduction-key"></a><a name="use-reduction-key"></a>Utilisation d’une clé de réduction

Une clé de réduction des prévisions doit être affectée au groupe de couverture de l’article. Procédez comme suit pour affecter une clé de réduction au groupe de couverture d’un article.

1. Accédez à **Planification \> Paramétrage \> Couverture \> Groupes de couverture**.
2. Dans l’organisateur **Autres**, dans le champ **Clé de réduction**, sélectionnez la clé de réduction à affecter au groupe de couverture. La clé de réduction s’applique ensuite à tous les articles appartenant au groupe de couverture.
3. Pour utiliser une clé de réduction afin de calculer la réduction des prévisions lors du calcul PDP/MRP, vous devez définir ce paramètre dans le paramétrage du programme prévisionnel ou du plan général. Accédez à l’un des emplacements suivants :

    - **Planification \> Paramétrage \> Plans \> Programmes prévisionnels**
    - **Planification \> Paramétrage \> Plans \> Plans généraux**

4. Dans la page **Programmes prévisionnels** ou **Plans généraux**, sous l’organisateur **Général**, dans le champ **Méthode utilisée pour réduire les besoins prévisionnels**, sélectionnez **Pourcentage - clé de réduction** ou **Transactions - clé de réduction**.

### <a name="reduce-a-forecast-by-transactions"></a>Réduction de la prévision par les transactions

Lorsque vous sélectionnez **Transactions - clé de réduction** ou **Transactions - période dynamique** comme méthode de réduction des besoins prévisionnels, vous pouvez spécifier quelles transactions réduisent la prévision. Dans la page **Groupes de couverture**, sous l’organisateur **Autre**, dans le champ **Soustraire des prévisions**, sélectionnez **Toutes les transactions** si toutes les transactions doivent réduire la prévision ou **Commandes** si seules les commandes client doivent diminuer la prévision.

## <a name="forecast-models-and-submodels"></a>Modèles et sous-modèles de prévision

Cette section décrit comment créer des modèles de prévision et comment combiner plusieurs modèles de prévision en configurant des sous-modèles.

Un *modèle de prévision* nomme et identifie une prévision spécifique. Après avoir créé le modèle de prévision, vous pouvez y ajouter des lignes de prévision. Pour ajouter des lignes de prévision pour plusieurs articles, utilisez la page **Lignes de prévision de la demande**. Pour ajouter des lignes de prévision pour un article sélectionné spécifique, utilisez la page **Produits lancés**.

Un modèle de prévision peut inclure des prévisions d’autres modèles de prévision. Pour obtenir ce résultat, vous ajoutez d’autres modèles de prévision comme *sous-modèles* d’un modèle de prévision parent. Vous devez créer chaque modèle pertinent avant de pouvoir l’ajouter en tant que sous-modèle d’un modèle de prévision parent.

La structure résultante vous offre un moyen puissant de contrôler les prévisions, car elle vous permet de combiner (agréger) les entrées de plusieurs prévisions individuelles. Par conséquent, du point de vue de la planification, il est facile de combiner les prévisions pour les simulations. Par exemple, vous pouvez configurer une simulation basée sur la combinaison d’une prévision régulière avec la prévision d’une promotion de printemps.

### <a name="submodel-levels"></a>Niveaux de sous-modèle

Il n’y a pas de limite au nombre de sous-modèles pouvant être ajoutés à un modèle de prévision parent. Cependant, la structure ne peut avoir qu’un seul niveau de profondeur. En d’autres termes, un modèle de prévision qui est un sous-modèle d’un autre modèle de prévision ne peut pas avoir ses propres sous-modèles. Lorsque vous ajoutez des sous-modèles à un modèle de prévision, le système vérifie si ce modèle de prévision est déjà un sous-modèle d’un autre modèle de prévision.

Si la planification principale rencontre un sous-modèle qui a ses propres sous-modèles, vous recevez un message d’erreur.

#### <a name="submodel-levels-example"></a>Exemple de niveaux de sous-modèle

Le modèle de prévision A a le modèle de prévision B comme sous-modèle. Par conséquent, le modèle de prévision B ne peut pas avoir ses propres sous-modèles. Si vous essayez d’ajouter un sous-modèle au modèle de prévision B, le message d’erreur suivant s’affiche : « Le modèle de prévision B est un sous-modèle pour le modèle A. »

### <a name="aggregating-forecasts-across-forecast-models"></a>Agrégation des prévisions à travers les modèles de prévision

Les lignes de prévision qui se produisent le même jour seront agrégées dans leur modèle de prévision et ses sous-modèles.

#### <a name="aggregation-example"></a>Exemple d’agrégation

Le modèle de prévision A a les modèles de prévision B et C comme sous-modèles.

- Le modèle de prévision A comprend une prévision de la demande pour 2 unités le 15 juin.
- Le modèle de prévision B comprend une prévision de la demande pour 3 unités le 15 juin.
- Le modèle de prévision C comprend une prévision de la demande pour 4 unités le 15 juin.

La prévision de la demande qui en résultera sera une demande unique de 9 unités (2 + 3 + 4) le 15 juin.

> [!NOTE]
> Chaque sous-modèle de prévision utilise ses propres paramètres et non ceux du modèle de prévision de niveau parent.

### <a name="create-a-forecast-model"></a>Création d’un modèle de prévision

Pour créer un modèle de prévision, procédez comme suit.

1. Aller à **Planification \> Installer \> Prévision de la demande \> Modèles de prévision**.
1. Dans le volet Actions, sélectionnez **Nouveau**.
1. Définissez les champs suivants pour le nouveau modèle de prévision :

    - **Modèle** – Permet d’entrer un identificateur unique pour le modèle.
    - **Nom** – Entrez un nom descriptif pour le modèle.
    - **Arrêté** - Habituellement, vous devez définir cette option sur *Non*. Réglez-le sur *Oui* uniquement si vous souhaitez empêcher la modification de toutes les lignes de prévision affectées au modèle.

    > [!NOTE]
    > Le champ **Inclure dans les prévisions de trésorerie** et les champs sur le raccourci **Projet** n’est pas lié à la planification générale. Par conséquent, vous pouvez les ignorer dans ce contexte. Vous ne devez les prendre en compte que lorsque vous travaillez avec des prévisions pour le module **Gestion de projet et comptabilité**.

### <a name="assign-submodels-to-a-forecast-model"></a>Affectation de sous-modèles de prévision

Pour affecter des sous-modèles à un modèle de prévision, procédez comme suit.

1. Aller à **Gestion de l’inventaire \> Installer \> Prévoir \> Modèles de prévision**.
1. Dans le volet de liste, sélectionnez le modèle de prévision pour paramétrer un sous-modèle.
1. Sous l’organisateur **Sous-modèles**, sélectionnez **Ajouter** pour ajouter une ligne dans la grille.
1. Dans la nouvelle ligne, définissez les champs suivants :

    - **Sous-modèle** – Sélectionnez le modèle de prévision à ajouter comme sous-modèle. Ce modèle de prévision doit déjà exister, et il ne doit pas avoir de sous-modèles propre.
    - **Nom** – Entrez un nom descriptif pour le sous-modèle. Par exemple, ce nom peut indiquer la relation du sous-modèle avec le modèle de prévision parent.

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]

