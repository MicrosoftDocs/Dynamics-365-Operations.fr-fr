---
title: "Clés de réduction"
description: "Cet article fournit des exemples qui indiquent comment paramétrer une clé de réduction. Il inclut des informations sur les différents paramètres de clé de réduction et les résultats de chacun d'entre eux. Vous pouvez utiliser une clé de réduction pour définir la méthode permettant de réduire les besoins de prévision."
author: roxanadiaconu
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: ReqPlanSched
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 19251
ms.assetid: aa9e0dfb-6052-4a2e-9378-89507c02fdf2
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: roxanad
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: 4b7f4ebd635e02f3cfc6d0f620dad30e6b1a98a2
ms.contentlocale: fr-fr
ms.lasthandoff: 05/08/2018

---

# <a name="reduction-keys"></a>Clés de réduction

[!include [banner](../includes/banner.md)]

Cet article fournit des exemples qui indiquent comment paramétrer une clé de réduction. Il inclut des informations sur les différents paramètres de clé de réduction et les résultats de chacun d'entre eux. Vous pouvez utiliser une clé de réduction pour définir la méthode permettant de réduire les besoins de prévision.

<a name="example-1-percent---reduction-key-forecast-reduction-principle"></a>Exemple 1 : Pourcentage - principe de réduction prévisionnelle de la clé de réduction
---------------------------------------------------------------

Cet exemple décrit la manière dont une clé de réduction réduit les besoins de prévision de la demande en fonction des pourcentages et périodes définis par la clé de réduction.

1. Dans la page **Clés de réduction**, paramétrez les lignes suivantes.

   | Monnaie | Unité  | Pourcentage |
   |--------|-------|---------|
   |   1    | Mois |   100   |
   |   2    | Mois |   75    |
   |   3    | Mois |   50    |
   |   4    | Mois |   25    |


2. Liez la clé de réduction au groupe de couverture de l'article.
3. Dans la page **Plans généraux**, dans le champ **Principe de réduction**, sélectionnez **Pourcentage - clé de réduction**.
4. Créez une prévision de la demande de 1 000 pièces par mois.

Si vous lancez le calendrier des prévisions le 1er janvier, les besoins de prévision de la demande sont utilisés en fonction des pourcentages définis dans la page **Clés de réduction**. Les quantités requises suivantes sont transférées vers le plan général.

| Mois                | Nombre de pièces requises |
|----------------------|---------------------------|
| Janvier              | 0                         |
| Février             | 250                       |
| Mars                | 500                       |
| Avril                | 750                       |
| Mai à décembre | 1 000                     |

## <a name="example-2-transactions--reduction-key-forecast-reduction-principle"></a>Exemple 2 : Transactions  principe de réduction prévisionnelle de la clé de réduction
Cet exemple décrit la manière dont les commandes réelles, qui se produisent durant les périodes définies par la clé de réduction, réduisent les besoins de prévision de la demande.

-   Dans la page **Plans généraux**, dans le champ **Principe de réduction**, sélectionnez **Transactions - clé de réduction**.

Les commandes client suivantes sont prises en compte le 1er janvier.

| Mois    | Nombre de pièces commandées |
|----------|--------------------------|
| Janvier  | 956                      |
| Février | 1 176                    |
| Mars    | 451                      |
| Avril    | 119                      |

Si vous utilisez les mêmes prévisions de la demande de 1 000 pièces par mois, les quantités requises suivantes sont transférées vers le plan général.

| Mois                | Nombre de pièces requises |
|----------------------|---------------------------|
| Janvier              | 44                        |
| Février             | 0                         |
| Mars                | 549                       |
| Avril                | 881                       |
| Mai à décembre | 1 000                     |

## <a name="example-3-transactions--dynamic-period-forecast-reduction-principle"></a>Exemple 3 : Transactions  principe de réduction prévisionnelle de la période dynamique
Dans la plupart des cas, les systèmes sont paramétrés de telle sorte que les transactions réduisent la prévision de la demande durant des périodes prévisionnelles spécifiques : semaines, mois, etc. Ces périodes sont définies dans la clé de réduction. Toutefois, la durée entre deux lignes de prévision de la demande peut également *impliquer* une période.

1. Créez une prévision de la demande pour les dates et les quantités suivantes.

   | Date       | Prévision de la demande |
   |------------|-----------------|
   | 1er janvier  | 1.000           |
   | 5 janvier  | 500             |
   | 12 janvier | 1.000           |

   Dans cette prévision, il n'y a pas de période précise entre les dates de prévision : entre les première et deuxième dates, il y a une période de quatre jours, et entre les deuxième et troisième dates, il y a une période de sept jours. Ces différentes périodes sont les périodes dynamiques.
2. Créez des lignes de commande client comme suit.
   | Date                             | Quantité de la commande client |
   |----------------------------------|----------------------|
   | 15 décembre de l'année précédente | 500                  |
   | 3 janvier                        | 100                  |
   | 10 janvier                       | 200                  |

La prévision est réduite comme suit :

-   La première commande client n'est pas effectuée dans une période donnée, elle ne réduit donc aucune prévision.
-   La deuxième commande client est effectuée entre le 1er et le 5 janvier, elle réduit donc la prévision du 1er janvier de 100.
-   La troisième commande client est effectuée entre le 5 et le 12 janvier, elle réduit donc la prévision du 5 janvier de 200.

L'ordre prévisionnel suivant est créé pour exécuter la prévision.

| Date de prévision de la demande | Quantité réduite |
|----------------------|------------------|
| 1er janvier            | 900              |
| 5 janvier            | 300              |
| 12 janvier           | 1.000            |

Voici un résumé de la réduction **Transactions - période dynamique** :

-   Les besoins prévisionnels sont réduits par les transactions de commande réelles qui surviennent dans la période dynamique. La période dynamique couvre les dates de prévision actuelles et se termine au début de la prochaine prévision.
-   Cette méthode n'utilise pas ou ne nécessite pas une clé de réduction.
-   Lorsque cette option est utilisée, le comportement suivant se produit :
    -   Si la prévision est réduite complètement, les besoins prévisionnels actuels passent à 0 (zéro).
    -   En l'absence de prévision à venir, les besoins de la dernière prévision entrée sont réduits.
    -   Les plages de gestion sont incluses dans le calcul de réduction des prévisions.
    -   Les jours positifs sont inclus dans le calcul de réduction des prévisions.
    -   Si les transactions de commande réelles dépassent les besoins prévisionnels, les transactions restantes ne sont pas expédiées à la période suivante de prévision.


<a name="additional-resources"></a>Ressources supplémentaires
--------

[Plans généraux](master-plans.md)




