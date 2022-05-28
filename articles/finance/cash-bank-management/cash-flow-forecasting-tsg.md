---
title: Résoudre les problèmes de configuration des prévisions de trésorerie
description: Cette rubrique contient les réponses aux questions que vous vous posez lorsque vous configurez les prévisions de trésorerie. Elle répond aux questions fréquemment posées (FAQ) sur la configuration des flux de trésorerie, les mises à jour des flux de trésorerie et les flux de trésorerie Power BI.
author: panolte
ms.date: 03/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerCovParameters
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: panolte
ms.search.validFrom: 2020-12-30
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: e2b5a8df84ff5159a85526251a6367857afa1808
ms.sourcegitcommit: 631d2cea52590af15f208e9af584446e85540fcf
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/07/2022
ms.locfileid: "8724568"
---
# <a name="troubleshoot-cash-flow-forecasting-setup"></a>Résoudre les problèmes de configuration des prévisions de trésorerie

[!include [banner](../includes/banner.md)]

Cette rubrique contient les réponses aux questions que vous vous posez lorsque vous configurez les prévisions de trésorerie. Elle répond aux questions fréquemment posées (FAQ) sur la configuration des flux de trésorerie, les mises à jour des flux de trésorerie et les flux de trésorerie Power BI.

## <a name="why-is-cash-flow-shown-for-only-one-legal-entity"></a>Pourquoi les flux de trésorerie sont-ils affichés une seule entité juridique ?

La prévision des flux de trésorerie est configurée et calculée par entité juridique. Les rapports et la capacité de prévision des flux de trésorerie Power BI dans Finance Insights indiquent les résultats.

La prévision de flux de trésorerie doit être configurée pour chaque entité juridique pour laquelle vous souhaitez voir une prévision. Passez en revue la configuration des prévisions de trésorerie dans toutes vos entités juridiques. Vous pouvez également examiner la configuration de toutes les entités juridiques pour les prévisions de flux de trésorerie et vous assurer qu’elles sont définies comme vous le souhaitez.

## <a name="why-doesnt-power-bi-show-all-the-cash-flow-data"></a>Pourquoi Power BI n’affiche pas toutes les données de flux de trésorerie ?

Plusieurs étapes doivent être effectuées avant que les prévisions de flux de trésorerie puissent apparaître dans les vues Power BI. Passez en revue la liste de contrôle suivante et assurez-vous que chaque étape a été effectuée :

- Vous devez définir des flux de trésorerie pour chaque entité juridique.
- Dans les paramètres de Comptabilité, vous devez définir la devise du système et le type de taux de change du système.
- Vous devez définir la devise comptable et le type de taux de change.
- Vous devez entrer des taux de change entre la devise de la transaction et la devise comptable.
- Vous devez entrer des taux de change entre la devise comptable et la devise système.
- Vous devez entrer des taux de change entre la devise comptable et chaque devise bancaire.

## <a name="why-did-cash-flow-power-bi-work-in-previous-versions-but-is-now-blank"></a>Pourquoi les flux de trésorerie Power BI fonctionnaient dans les versions précédentes mais sont maintenant vides ?

Vérifiez que les mesures « Mesure de flux de trésorerie V2 » et « LedgerCovLiquidityMeasurement » du magasin d’entités ont été configurées. Pour plus d’informations sur l’utilisation des données dans un magasin d’entités, voir [Intégration de Power BI avec le magasin d’entités](../../fin-ops-core/dev-itpro/analytics/power-bi-integration-entity-store.md). Vérifiez que toutes les étapes requises pour afficher le contenu de Power BI ont été réalisées. Pour plus d’informations, voir [Contenu Power BI – Vue d’ensemble des disponibilités](Cash-Overview-Power-BI-content.md).

## <a name="have-the-entity-store-entities-been-refreshed"></a>Les entités du magasin d’entités ont-elles été actualisées ?

Vous devez actualiser périodiquement vos entités pour vous assurer que les données sont à jour et exactes. Pour actualiser manuellement une entité spécifique, accédez à **Administration système \> Paramétrage \> Magasin des entités**, sélectionnez l’entité, puis sélectionnez **Actualiser**. Les données peuvent également être mises à jour automatiquement. Sur la page **Magasin des entités**, définissez l’option **Actualisation automatique activée** sur **Oui**.

## <a name="which-calculation-method-should-be-used-when-calculating-cash-flow-forecasts"></a>Quelle méthode de calcul utiliser lors du calcul des prévisions de flux de trésorerie ?

La méthode de calcul des prévisions de flux de trésorerie comporte deux options de sélection importantes. L’option **Nouveau** calculera les prévisions de flux de trésorerie pour les nouveaux documents et les documents qui ont été modifiés depuis l’exécution du dernier traitement par lots. Cette option a tendance à s’exécuter plus rapidement car elle traite un sous-ensemble plus petit de documents. L’option **Total** recalculera les prévisions de flux de trésorerie pour chaque document du système. Cette option prend plus de temps car elle a plus de travail à accomplir.

### <a name="how-do-i-improve-the-performance-of-the-cash-flow-forecasting-recurring-batch-job"></a>Comment améliorer les performances du traitement par lots périodique de prévision de flux de trésorerie ?

Nous vous recommandons d’exécuter vos prévisions de flux de trésorerie une fois par jour pendant les heures creuses à l’aide de la méthode de calcul **Nouveau**. Nous vous recommandons d’appliquer cette démarche six jours par semaine. Ensuite, exécutez une prévision de flux de trésorerie une fois par semaine à l’aide de la méthode de calcul **Total**, le jour où l’activité est la plus faible.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]

