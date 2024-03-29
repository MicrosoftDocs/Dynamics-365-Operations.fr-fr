---
title: Contenu Power BI Performances d’entrepôt
description: Cet article décrit les données incluses dans le contenu Power BI pour les performances de l’entrepôt.
author: Mirzaab
ms.date: 12/18/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.custom: 272953
ms.assetid: 4e4d4323-78cf-4ffa-8d5a-05e856c33db6
ms.search.form: WHSWarehousePerformancePowerBI
ms.openlocfilehash: 82f43f45b43df864cbda8ba372dbed46d8f4c7e4
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/12/2022
ms.locfileid: "9289844"
---
# <a name="warehouse-performance-power-bi-content"></a>Contenu Power BI Performances d’entrepôt

[!include [banner](../includes/banner.md)]

Cet article décrit les données incluses dans le contenu **Performances de l’entrepôt** de Microsoft Power BI. Elle explique également comment accéder aux états Power BI, et fournit des informations sur le modèle de données et les entités qui permettent de créer le contenu.

## <a name="overview"></a>Présentation

Le contenu Power BI **Performances de l’entrepôt** a été créé afin que les responsables de l’entrepôt et des opérations puissent surveiller les entrants, sortants et mesures de stock importants. Il utilise la gestion des entrepôts, les produits, ainsi que d’autres données transactionnelles de votre système, et fournit à la fois une vue globale des performances d’entrepôt et une répartition pour les fournisseurs, les groupes de produits et les produits, les sites et les entrepôts.

Les responsables d’entrepôt peuvent utiliser le contenu Power BI **Performances de l’entrepôt** pour mesurer les trois performances suivantes :

- **Performances entrants** : mesure à quel point un fournisseur est performant par rapport aux exigences du client (autrement dit, indique les mesures de performance de livraison), et les performances de rangement, de sorte que vous puissiez identifier les problèmes susceptibles d’augmenter les besoins en travailleurs ou articles au cours d’une période. Il est important de savoir si les fournisseurs livrent à temps, en avance, ou en retard, de sorte que vous puissiez déterminer comment les performances du fournisseur affectent les performances générales de rangement. Un fournisseur qui livre en dehors de dates qui ont été acceptées peut exercer une pression supplémentaire sur l’entrepôt, en raison du travail inattendu, et peut augmenter le temps moyen de rangement.
- **Performances d’expédition** : indique si votre entrepôt expédie entièrement et à temps les articles aux clients (autrement dit, mesure les performances des sortants d’expédition et de livraison), afin que vous puissiez identifier les problèmes qui affectent des produits, des sites, des entrepôts, ou des clients dédiés. Si vous découvrez que vous livrez avec du retard des zones ou des villes spécifiques, vous devez prêter une plus grande attention à la gestion du transport ou du compte.
- **Précision du stock d’emplacement** : la précision du stock est une donnée Business Intelligence (BI) interne importante pour l’entrepôt. Il est primordial que vous déterminiez le degré de précision du comptage en général. Toutefois, il est également important que vous déterminiez le degré de précision avec lequel vous stockez les articles dans les emplacements corrects, et que vous identifiez les écarts, afin de rechercher de meilleurs emplacements pour des articles ou lanciez un comptage total de certains articles spécifiques. (Actuellement, la nouvelle fonctionnalité de comptage d’articles est fournie sous la forme d’un correctif.) Si vous utilisez ce contenu Power BI pour déterminer l’exactitude du stock disponible par entrepôt, vous pouvez également prévenir le vol dans vos magasins. Vous pouvez également déterminer si des emplacements disposent de quantités disponibles qui diffèrent des données de planification des ressources d’entreprise (ERP). Ces emplacements peuvent être trop grands, ou impossibles à compter. Autre cas de figure, certains emplacements physiques peuvent être incorrects, de sorte qu’il est difficile de conserver un seul type d’article synchronisé avec les données disponibles.

## <a name="accessing-the-power-bi-content-pack"></a>Accès au pack de contenu Power BI
Le contenu Power BI **Performances d’entrepôt** s’affiche sur la page **Performances d’entrepôt** (**Gestion des entrepôts** \> **Recherches et états** \> **Analyse des performances d’entrepôt** \> **Performances d’entrepôt**).

## <a name="metrics-that-are-included-in-the-power-bi-content"></a>Mesures incluses dans le pack de contenu Power BI
Le contenu Power BI **Performances de l’entrepôt** inclut un état. Cet état contient un ensemble de mesures visualisées sous forme de graphiques, de vignettes et de tables. Le tableau suivant donne une vue d’ensemble des visualisations dans le contenu Power BI **Performances d’entrepôt**.

| Page d’état                 | Graphiques                                   | Description |
|-----------------------------|------------------------------------------|-------------|
| Performances entrants         | Total des rangements                          | Nombre de lignes de travail de rangement traitées au cours d’un délai imparti. |
| Performances entrants         | Temps moyen de rangement                    | Le temps moyen, en heures, pour toutes les lignes de rangement de commande fournisseur qui sont traitées, de l’enregistrement des articles jusqu’au dernier rangement. |
| Performances entrants         | Reçu en avance                           | Nombre de lignes de commandes fournisseur reçues en avance. |
| Performances entrants         | Reçu à temps                         | Nombre de lignes de commandes fournisseur reçues à temps. |
| Performances entrants         | Réception en retard                            | Nombre de lignes de commandes fournisseur reçues en retard. |
| Performances entrants         | Performances (à temps) par fournisseur                        | Une vue du pourcentage des lignes de commandes fournisseur reçues d’un fournisseur ou d’un groupe de fournisseurs en avance, à temps, et ultérieurement. |
| Performances entrants         | Rangement moyen réception-stockage (heures) | Le temps moyen de rangement réception-stockage en heures au fil du temps. |
| Performances entrants         | Rangement moyen par collaborateur               | Le temps moyen, en heures, qu’un collaborateur met pour traiter le rangement des lignes de commandes fournisseur. |
| Performances entrants         | Rangement moyen l’heure par fournisseur          | Le temps moyen de rangement en heures par fournisseur ou groupe de fournisseurs. |
| Performances entrants         | Rangement moyen l’heure par produit         | Le temps moyen de rangement en heures par article ou groupe d’articles. |
| Précision du stock à l’emplacement | Nombre total                              | Nombre de lignes de comptage traitées au cours d’une période. |
| Précision du stock à l’emplacement | Taux d’écart                         | Le taux d’écart total est le pourcentage de toutes les lignes qui sont comptées pour une période donnée. |
| Précision du stock à l’emplacement | Comptage sans écart                | Sur le nombre total de lignes de comptage traitées, le nombre de lignes traitées sans aucun écart. |
| Précision du stock à l’emplacement | Articles comptés au fil du temps                  | Pourcentage des articles qui sont comptés avec et sans écart au fil du temps. |
| Précision du stock à l’emplacement | Écart de quantité d’articles supérieur à % | Tableau des lignes comptées avec un écart supérieur à un pourcentage spécifié. Le tableau inclut des informations sur les emplacements, les articles, l’écart moyen, les lignes de comptage totales, le nombre de lignes de comptage avec des écarts pour l’emplacement, la quantité moyenne qui est comptée, la quantité totale attendue qui sera comptée, et la quantité réelle d’articles comptés. |
| Précision du stock à l’emplacement | Nombre d’articles par collaborateur                     | Performances de comptage des collaborateurs. Les performances sont exprimées en pourcentage des lignes de comptage avec ou sans écarts. |
| Précision du stock à l’emplacement | Nombre d’articles par site/entrepôt           | Performances de comptage par nombre de lignes de comptage traitées par site ou entrepôt avec ou sans écart. |
| Précision du stock à l’emplacement | Taux d’écart par produit              | Taux d’écart pour les performances de comptage. Le taux est exprimé en pourcentage des lignes de comptage traitées par article ou groupe d’articles. |
| Performances d’expédition        | Lignes expédiées                            | Nombre total de lignes d’expédition expédiées au cours d’une période. |
| Performances d’expédition        | En avance                                    | Pourcentage des lignes d’expédition qui sont expédiées en avance. |
| Performances d’expédition        | À temps                                  | Pourcentage des lignes d’expédition qui sont expédiées à temps. |
| Performances d’expédition        | En retard                                     | Pourcentage des lignes d’expédition qui sont expédiées en retard. |
| Performances d’expédition        | Expéditions au fil du temps                      | Pourcentage des lignes d’expédition qui sont expédiées à temps, en avance, ou en retard au cours d’une période donnée. Une ligne affiche la tendance pour les lignes qui sont expédiées à temps. |
| Performances d’expédition        | Expéditions en tard par ville                     | Une carte qui affiche les villes et zones concernées par les expéditions en retard. |
| Performances d’expédition        | Expéditions par produit                       | Pourcentage qui est expédié en avance, à temps, ou en retard par article ou groupe d’articles. |
| Performances d’expédition        | Expéditions par client                      | Pourcentage qui est expédié en avance, à temps, ou en retard par client ou groupe de clients. |
| Performances d’expédition        | Expéditions par site/entrepôt              | Pourcentage qui est expédié en avance, à temps, ou en retard par site ou entrepôt. |

## <a name="understanding-the-data-model-and-calculations"></a>Compréhension du modèle de données et des calculs
Les données suivantes sont utilisées pour remplir les pages d’état dans le contenu Power BI **Performances d’entrepôt**. Ces données sont représentées sous la forme de mesures globales indexées dans le magasin des entités. Le magasin des entités est une base de données Microsoft SQL Server optimisée pour les analyses. Pour plus d’informations, voir [Intégration de Power BI au magasin d’entité](power-bi-integration-entity-store.md).

Les mesures globales clés suivantes sont utilisées comme base du contenu.

| Page d’état                 | Graphiques                                   | Tables                                | Descriptions du calcul |
|-----------------------------|------------------------------------------|---------------------------------------|--------------------------|
| Performances entrants         | Total des rangements                          | WHSWorkLine                           | Nombre de lignes de travail dans lesquelles le type de travail est **ranger**. |
| Performances entrants         | Temps moyen de rangement                    | WHSWorkLine                           | Somme des délais max. des lignes de travail divisée par le nombre de délais max. des lignes de travail, où les délais max. des lignes de travail correspondent à l’écart maximal entre la date de création du travail et la date clôturée. |
| Performances entrants         | Reçu en avance                           | WHSWorkLine                           | Nombre de lignes de travail dont la date de création du travail est antérieure à la date de livraison utilisée. Si la date confirmée par livraison n’est pas définie, utilisez la date de livraison par défaut. |
| Performances entrants         | Reçu à temps                         | WHSWorkLine                           | Nombre de lignes de travail dont la date de création du travail est égale à la date de livraison utilisée. Si la date confirmée par livraison n’est pas définie, utilisez la date de livraison par défaut. |
| Performances entrants         | Réception en retard                            | WHSWorkLine                           | Nombre de lignes de travail dont la date de création du travail est postérieure à la date de livraison utilisée. Si la date confirmée par livraison n’est pas définie, utilisez la date de livraison par défaut. |
| Performances entrants         | Performances (à temps) par fournisseur                        | WHSWorkLine                           | Reçues en avance, reçus à temps, et reçues en retard (voir les descriptions plus haut dans cette table). |
| Performances entrants         | Rangement moyen réception-stockage (heures)   | WHSWorkLine                           | Temps moyen de rangement (voir la description plus haut dans cette table). |
| Performances entrants         | Rangement moyen par collaborateur               | WHSWorkLine                           | Temps moyen de rangement (voir la description plus haut dans cette table). |
| Performances entrants         | Rangement moyen l’heure par fournisseur          | WHSWorkLine                           | Temps moyen de rangement (voir la description plus haut dans cette table). |
| Performances entrants         | Rangement moyen l’heure par produit         | WHSWorkLine                           | Temps moyen de rangement (voir la description plus haut dans cette table). |
| Précision du stock à l’emplacement | Nombre total                              | WHSWorkLineCycleCount                 | Inventaires tournants où l’écart absolu en quantité est égal ou supérieur à 0 (zéro). |
| Précision du stock à l’emplacement | Taux d’écart                         | WHSWorkLineCycleCount                 | Inventaires tournants qui ont des écarts, divisés par le nombre total. Un inventaire tournant est considéré comme ayant des écarts si l’écart absolu en quantité est supérieur à 0 (zéro). |
| Précision du stock à l’emplacement | Comptage sans écart                | WHSWorkLineCycleCount                 | Inventaires tournants où l’écart absolu en quantité est supérieur à 0 (zéro). |
| Précision du stock à l’emplacement | Comptage avec écart                   | WHSWorkLineCycleCount                 | Inventaires tournants où l’écart absolu en quantité est égal à 0 (zéro). |
| Précision du stock à l’emplacement | Articles comptés au fil du temps                  | WHSWorkLineCycleCount                 | Nombre sans écart et nombre avec écart (voir les descriptions plus haut dans cette table.) |
| Précision du stock à l’emplacement | Écart de quantité d’articles supérieur à % | WHSWorkLineCycleCount                 | L’écart moyen est l’écart absolu en quantité divisé par la quantité prévue où l’écart absolu en quantité est supérieur à 0 (zéro). L’écart moyen en quantité est l’écart absolu moyen en quantité où l’écart absolu en quantité est supérieur à 0 (zéro). Comptage avec écart, nombre total, quantité prévue, et quantité comptée où la quantité complète est regroupée par article et emplacement (voir les descriptions plus haut dans cette table). |
| Précision du stock à l’emplacement | Nombre d’articles par collaborateur                     | WHSWorkLineCycleCount                 | Nombre sans écart et nombre avec écart (voir les descriptions plus haut dans cette table). |
| Précision du stock à l’emplacement | Nombre d’articles par site/entrepôt           | WHSWorkLineCycleCount                 | Nombre sans écart et nombre avec écart (voir les descriptions plus haut dans cette table). |
| Précision du stock à l’emplacement | Taux d’écart par produit              | WHSWorkLineCycleCount                 | Taux d’écart (voir la description plus haut dans cette table). |
| Performances d’expédition        | Lignes expédiées                            | SalesLine               | Nombre de lignes de vente dont les lignes de vente sont expédiées. |
| Performances d’expédition        | En avance                                    | CustPackingSlipOnTimeStatus           | Lignes de vente dont le statut de la date d’expédition est **1 (En avance)**. En avance signifie que la date d’expédition du bon de livraison est antérieure à la date d’expédition confirmée sur la ligne de vente. Si la date d’expédition confirmée n’est pas définie, utilisez la date d’expédition demandée. |
| Performances d’expédition        | À temps                                  | CustPackingSlipOnTimeStatus           | Lignes de vente dont le statut de la date d’expédition est **2 (À temps)**. À temps signifie que la date d’expédition du bon de livraison est égale à la date d’expédition confirmée sur la ligne de vente. Si la date d’expédition confirmée n’est pas définie, utilisez la date d’expédition demandée. |
| Performances d’expédition        | En retard                                     | CustPackingSlipOnTimeStatus           | Lignes de vente dont le statut de la date d’expédition est **3 (En retard)**. En retard signifie que la date d’expédition du bon de livraison est postérieure à la date d’expédition confirmée sur la ligne de vente. Si la date d’expédition confirmée n’est pas définie, utilisez la date d’expédition demandée. |
| Performances d’expédition        | Expéditions au fil du temps                      | SalesLine CustPackingSlipOnTimeStatus | Commandes qui sont totalement expédiées, où la totalité de la ligne de vente est expédiée, plus En avance, À temps et En retard |
| Performances d’expédition        | Expéditions en tard par ville                     | CustPackingSlipOnTimeStatus           | En retard (voir les descriptions plus haut dans cette table). |
| Performances d’expédition        | Expéditions par produit                       | CustPackingSlipOnTimeStatus           | En avance, À temps, et En retard (voir les descriptions plus haut dans cette table). |
| Performances d’expédition        | Expéditions par client                      | CustPackingSlipOnTimeStatus           | En avance, À temps, et En retard (voir les descriptions plus haut dans cette table). |
| Performances d’expédition        | Expéditions par site/entrepôt              | CustPackingSlipOnTimeStatus           | En avance, À temps, et En retard (voir les descriptions plus haut dans cette table). |


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
