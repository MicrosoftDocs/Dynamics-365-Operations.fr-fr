---
title: Effectuer des ajustements manuels sur la prévision de base
description: Cette rubrique explique comment effectuer des ajustements manuels sur une prévision de base et afficher les détails de la prévision.
author: roxanadiaconu
ms.date: 01/07/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ReqDemPlanForecastViewer
audience: Application User
ms.reviewer: kamaybac
ms.custom: 72704
ms.assetid: e7c5d44e-07bc-40b1-a4b3-8ba46483ef9e
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 56069b1d2cf72eb29737b0aa7d066c998c0c423c
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5833639"
---
# <a name="make-manual-adjustments-to-the-baseline-forecast"></a>Effectuer des ajustements manuels sur la prévision de base

[!include [banner](../includes/banner.md)]

Cette rubrique explique comment effectuer des ajustements manuels sur une prévision de base et afficher les détails de la prévision. 

Avant d’effectuer des ajustements manuels, il est important que vous compreniez certains concepts dans diverses pages.

## <a name="grid-on-the-adjusted-demand-forecast-page"></a>Grille dans la page Ajustement de la prévision de demande
La page **Ajustement de la prévision de demande** inclut une grille avec la structure suivante :

-   La première colonne affiche les articles, les clés de répartition par article, les sociétés, etc., pour lesquels cette prévision a été générée. Le sous-titre de la page fournit une description des dimensions de prévision existantes qui sont affichées dans la grille. Par exemple, si le sous-titre de la page est **Société / Site / Clé de répartition par article**, et qu’une des en-têtes de ligne dans la grille est **USMF / 1 / D\_Alloc**, la ligne indique la prévision pour la société USMF, le site 1, et la clé de répartition par article **D\_Alloc**.
-   Les colonnes suivantes représentent les intervalles de prévision pour lesquels la prévision a été générée. Chaque en-tête de colonne est la permière date de l’intervalle de prévision que la colonne affiche.
-   Les valeurs des cellules représentent la prévision pour un article, une clé de répartition par article, etc., pour cet intervalle de prévision spécifique.

## <a name="forecast-aggregation-and-de-aggregation"></a>Agrégation et désagrégation de prévision
Le sous-titre de la page affiche le niveau d’agrégation de prévision. 

Par exemple, si le sous-titre de la page est **Société/site/clé de répartition/numéro d’article/couleur/taille/configuration/style**, il n’existe aucune agrégation de prévision, et la prévision est indiquée au niveau de l’article et de ses dimensions. Pour modifier l’agrégation, utilisez la page **Modifier les dimensions de prévision**, que vous pouvez ouvrir à partir du menu de l’application. 

Pour modifier la prévision, cliquez sur l’une des cellules disponibles, et tapez la valeur de prévision ajustée. La cellule modifiée devient immédiatement grasse pour indiquer que la prévision indiquée n’est pas la prévision que le service de prévision de la demande a créé, mais qu’elle a été ajustée manuellement. 

Si vous modifiez l’agrégation pour que la page affiche plus de données agrégées, vous pouvez utiliser la page **Lignes de prévision de la demande** pour afficher les différentes lignes de prévision qui constituent la prévision agrégée. 

Par exemple, vous avez généré la prévision au niveau de l’article, mais vous savez que la demande de cet article augmentera sur tous les sites en raison d’une promotion ou d’un autre événement similaire. Dans ce cas, vous pouvez définir l’agrégation sur **Société/clé de répartition par article/article** sur la page **Modifier les dimensions de prévision**. Vous pouvez ajuster la prévision globale pour l’article dans l’ensemble des sites dans la grille **Ajustement de la prévision de demande**. Pour afficher l’effet de la modification sur tous les sites, ouvrez la page **Lignes de prévision de la demande**. Dans cette page, vous verrez une ligne pour l’article pour chaque site, la quantité de prévision ajustée, et la quantité de prévision d’origine. 

Lorsque l’ajustement de la quantité prévue est effectué à un niveau agrégé, le système utilise une répartition pondérée pour répartir la modification entre les lignes qui créent l’agrégation. 

Vous pouvez également effectuer des ajustements manuels dans la page **Lignes de prévision de la demande** en modifiant la valeur **Quantité totale** ou les cellules **Quantité** dans la grille de désagrégation.

## <a name="viewing-details-of-the-forecast"></a>Affichage des détails de la prévision
Vous pouvez ouvrir la page **Détails de prévision de la demande** pour afficher des informations supplémentaires sur la prévision. 

La page **Détails de prévision de la demande** affiche les informations suivantes dans des formats graphiques et tabulaires :

-   La demande historique sur laquelle les prévisions de prévision sont basées.
-   La prévision actuelle utilisé par la planification.
-   Les nouvelles valeurs de prévision de la demande et les montants des ajustements manuels.
-   L’intervalle de confiance pour les valeurs prévues.
-   Le modèle de prévision utilisé pour générer la prévision. Si vous affichez les données agrégées, vous verrez la liste de toutes les méthodes qui ont été utilisées pour toutes les séries chronologiques agrégées.
-   La précision du modèle interne (MAPE). Pour plus d’informations sur la précision de la prévision, voir [Surveiller la précision de la prévision](monitor-forecast-accuracy.md).

**Remarques :**

-   Si vous activez **Sélection du modèle de prévision sur les détails de prévision de la demande** à partir de Gestion des fonctionnalités, vous pourrez sélectionner les modèles de prévision à inclure, pour la prévision historique, sur la page **Détails des prévisions de la demande**.
-   L’intervalle de confiance qui apparaît dans la section **Prévision** de la page représente la différence entre la limite supérieure de l’intervalle de confiance et la limite inférieure de l’intervalle de confiance. Pour afficher des valeurs pour les limites supérieures et inférieures, pointez sur le graphique dans la section **Prévisions et demandes historiques représentées graphiquement**.
-   Si vous utilisez Microsoft Azure Machine Learning pour la prévision de la demande, vous pouvez spécifier le pourcentage de niveau de confiance que la prévision générée doit avoir. Un intervalle de confiance comporte une plage de valeurs qui constitue une bonne estimation des prévisions de la demande. Un pourcentage de niveau de confiance à 95 % indique qu’il existe un risque de 5 % que les prévisions de la demande se trouvent en dehors de l’intervalle de confiance.

Vous pouvez également effectuer des ajustements manuels de la prévision dans la page **Détails de prévision de la demande**, en modifiant les valeurs dans la ligne **Prévision** dans la section **Prévision**.

<a name="additional-resources"></a>Ressources supplémentaires
--------

[Contrôler la précision de la prévision](monitor-forecast-accuracy.md)

[Générer des prévisions de base statistiques](generate-statistical-baseline-forecast.md)





[!INCLUDE[footer-include](../../includes/footer-banner.md)]