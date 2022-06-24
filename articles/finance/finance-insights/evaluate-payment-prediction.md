---
title: Évaluer le modèle de prédiction de paiement client initial
description: Cet article décrit les étapes que vous pouvez suivre pour comprendre le modèle de prédiction de paiement client et évaluer son efficacité.
author: ShivamPandey-msft
ms.date: 05/02/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.custom: 14151
ms.assetid: 3d43ba40-780c-459a-a66f-9a01d556e674
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2020-05-28
ms.dyn365.ops.version: AX 10.0.8
ms.openlocfilehash: fcdf276505cf58267a38e9d6174a155ad307653b
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8847000"
---
# <a name="evaluate-the-initial-customer-payment-prediction-model"></a>Évaluer le modèle de prédiction de paiement client initial

[!include [banner](../includes/banner.md)]

Cet article explique comment évaluer un modèle de prédiction après avoir activé Finance Insights, puis généré et formé votre premier modèle. Cet article traite des modèles de prévision des paiements des clients. Elle décrit les étapes que vous pouvez suivre pour comprendre le modèle de prédiction de paiement client et évaluer son efficacité.

## <a name="getting-details-about-the-model"></a>Obtenir des détails sur le modèle

Sur la page **Paramètres Finance Insights** dans Microsoft Dynamics 365 Finance, un lien **Améliorer la précision du modèle** apparaît à côté du score de précision.

[![Lien Améliorer la précision du modèle.](./media/prediction-model.png)](./media/prediction-model.png)

Ce lien vous amène à AI Builder, où vous pouvez en savoir plus sur le modèle actuel et prendre des mesures pour l’améliorer. L’illustration suivante présente la page ouverte.

[![AI Builder.](./media/what-to-predict.png)](./media/what-to-predict.png)

La page ouverte affiche les informations suivantes :

- Dans la section **Performance**, la note de performance du modèle fournit une perspective sur la qualité du modèle. Pour plus d’informations sur cette note, voir [Performances du modèle de prédiction](/ai-builder/prediction-performance) dans la documentation AI Builder.
- La section **Données les plus influentes** montre l’importance des différents types d’entrée de données pour votre modèle. Vous pouvez évaluer cette liste et les pourcentages correspondants pour déterminer si les informations sont cohérentes avec ce que vous savez sur votre entreprise et votre marché.

    [![Sections de performances et de données les plus influentes pour le modèle de prédiction.](./media/models.png)](./media/models.png)

- Dans la section **Performance**, sélectionnez **Voir les détails** pour en savoir plus sur la note et d’autres considérations. Dans l’illustration suivante, les détails montrent que le modèle utilise moins d’informations que ce qui est recommandé. Par conséquent, le système a généré un message d’avertissement.

    [![Avertissements sur les performances du modèle.](./media/details.png)](./media/details.png)

## <a name="digging-deeper"></a>Approfondir

Bien que la précision soit un bon point de départ pour évaluer un modèle et que la note de performance offre une perspective, AI Builder fournit des mesures plus détaillées que vous pouvez utiliser pour votre évaluation. Pour télécharger les détails, dans la section **Performance**, sélectionnez le bouton points de suspension (**...**) à côté du bouton **Utiliser le modèle**, puis sélectionnez **Télécharger des métriques détaillées**.

[![Commande Télécharger les métriques détaillées.](./media/performance.png)](./media/performance.png)

L’illustration suivante montre le format dans lequel vous pouvez télécharger les données.

[![Format des données téléchargées.](./media/data-format.png)](./media/data-format.png)

Pour une analyse plus approfondie des résultats, un bon point de départ est de revoir la métrique "Matrice de confusion". Par exemple, voici les données affichées pour cette métrique dans l’illustration précédente.

`{"name": "Confusion Matrix", "value": {"schema_type": "confusion_matrix", "schema_version": "1.0.0", "data": {"class_labels": ["0", "1", "2"], "matrix": [[71, 9, 21], [5, 0, 27], [2, 0, 45]]}}, "type": "dictionaryNumericalList", "isGlobalScore": false}`

Vous pouvez développer ces données de la manière suivante.

| &nbsp;                   | Prédiction à l’heure | Prédiction tardive | Prédiction très tardive |
|--------------------------|-------------------|----------------|---------------------|
| Paiement à temps réel   | **71**            | 0              | 21                  |
| Paiement tardif réel      | 5                 | **0**          | 27                  |
| Paiement très tardif réel | 2                 | 0              | **45**              |

La matrice de confusion montre les résultats d’un jeu de données de test sélectionné au hasard à partir du processus de formation. Étant donné que ces factures fermées n’ont pas été utilisées pour entraîner le modèle, ce sont de bons cas de test pour le modèle. De plus, comme l’état réel de la facture est connu, les performances du modèle peuvent également être vues.

La première chose à rechercher est la valeur réelle la plus courante. Bien que cette valeur ne soit pas parfaitement alignée avec l’ensemble de données global, il s’agit d’une approximation raisonnable. Dans ce cas, **Paiement à temps réel** se produit pour 92 des 171 factures totales et est la valeur réelle la plus courante. C’est donc une bonne base pour votre modèle. Si vous aviez deviné juste que toutes les factures seraient à l’heure, vous auriez raison 92 fois sur 171 (soit 54 %% du temps).

Il est important que vous compreniez à quel point votre jeu de données est équilibré. Dans ce cas, 92 factures sur 171 ont été payées à temps, 32 ont été payées en retard et 47 ont été payées très tard. Ces valeurs indiquent un jeu de données raisonnablement équilibré, car il y a des résultats non triviaux dans chaque classification. Une situation où l’un des états a très peu de résultats peut être difficile pour un modèle Machine Learning.

La précision du modèle indique le nombre de prédictions correctes pour le jeu de données de test. Ces prédictions correctes sont les valeurs affichées en gras dans l’exemple précédent. Dans ce cas, les valeurs produisent une précision calculée de 67,8 %% (= \[71 + 0 + 45\] ÷ 171). Cette valeur représente une amélioration de 14 %% par rapport à l’estimation de base de 54 %% et est un indicateur de la qualité du modèle.

Si vous examinez de plus près la matrice de confusion, vous remarquerez que le modèle fait un bon travail de prédiction des paiements de factures à temps et très tardifs. Cependant, les 32 factures ont été payées en retard (mais pas très en retard). Ce résultat suggère qu’une exploration et une amélioration supplémentaires du modèle sont nécessaires.

Le score F1 Macro est un nombre qui représente mieux les performances du modèle que la précision. Ce score prend en compte les résultats de chaque état de classification (ponctuel, tardif et très tardif). Par exemple, voici les données affichées pour cette métrique "macro F1" dans l’illustration précédente.

`{"name": "F1 Macro", "value": 0.4927170868347339, "type": "percentage", "isGlobalScore": false}`

Dans ce cas, le score Macro F1 d’environ 49,3 %% indique que le modèle ne fournit pas de prédictions efficaces pour chaque état, malgré un score de précision global qui semble raisonnablement élevé.

## <a name="improving-the-model"></a>Améliorer le modèle

Une fois que vous aurez mieux compris les résultats de votre premier modèle, vous souhaiterez peut-être améliorer le modèle en ajoutant ou en supprimant des colonnes d’entités, ou en filtrant toutes les parties du jeu de données qui ne prennent pas en charge les prédictions précises. Fermez AI Builder, puis utilisez le lien **Améliorer le modèle** dans Dynamics 365 Finance pour redémarrer le processus AI Builder. Vous pouvez expérimenter différentes caractéristiques sans affecter le modèle publié. Le modèle publié n’est affecté que lorsque vous sélectionnez **Publier**. N’oubliez pas qu’un seul modèle est utilisé pour votre instance de Dynamics 365 Finance. Par conséquent, vous devez examiner attentivement tout nouveau modèle avant de le publier.

## <a name="for-more-information"></a>Plus d’informations

Pour plus d’information sur l’évaluation des modèles de prédiction, voir [Résultats des modèles Machine Learning](confusion-matrix.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
