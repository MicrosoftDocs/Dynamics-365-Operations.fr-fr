---
title: Résoudre les problèmes de configuration des prévisions de trésorerie
description: Cette rubrique contient les réponses aux questions que vous vous posez lorsque vous configurez les prévisions de trésorerie. Elle répond aux questions fréquemment posées (FAQ) sur la configuration des flux de trésorerie, les mises à jour des flux de trésorerie et les flux de trésorerie Power BI.
author: panolte
manager: AnnBe
ms.date: 12/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerCovParameters
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: panolte
ms.search.validFrom: 2020-12-30
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: d1cde9321259753bd0cacab3706c7f8455598ff3
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5232487"
---
# <a name="troubleshoot-cash-flow-forecasting-setup"></a>Résoudre les problèmes de configuration des prévisions de trésorerie

[!include [banner](../includes/banner.md)]

Cette rubrique contient les réponses aux questions que vous vous posez lorsque vous configurez les prévisions de trésorerie. Elle répond aux questions fréquemment posées (FAQ) sur la configuration des flux de trésorerie, les mises à jour des flux de trésorerie et les flux de trésorerie Power BI.

## <a name="why-is-cash-flow-shown-for-only-one-legal-entity"></a>Pourquoi les flux de trésorerie sont-ils affichés une seule entité juridique ?

La prévision des flux de trésorerie est configurée et calculée par entité juridique. Les rapports et la capacité de prévision des flux de trésorerie Power BI dans Finance Insights indiquent les résultats.

La prévision de flux de trésorerie doit être configurée pour chaque entité juridique pour laquelle vous souhaitez voir une prévision. Passez en revue la configuration des prévisions de trésorerie dans toutes vos entités juridiques. Vous pouvez également examiner la configuration de toutes les entités juridiques pour les prévisions de flux de trésorerie et vous assurer qu'elles sont définies comme vous le souhaitez.

## <a name="why-doesnt-power-bi-show-all-the-cash-flow-data"></a>Pourquoi Power BI n'affiche pas toutes les données de flux de trésorerie ?

Plusieurs étapes doivent être effectuées avant que les prévisions de flux de trésorerie puissent apparaître dans les vues Power BI. Passez en revue la liste de contrôle suivante et assurez-vous que chaque étape a été effectuée :

- Vous devez définir des flux de trésorerie pour chaque entité juridique.
- Dans les paramètres de Comptabilité, vous devez définir la devise du système et le type de taux de change du système.
- Vous devez définir la devise comptable et le type de taux de change.
- Vous devez entrer des taux de change entre la devise de la transaction et la devise comptable.
- Vous devez entrer des taux de change entre la devise comptable et la devise système.
- Vous devez entrer des taux de change entre la devise comptable et chaque devise bancaire.

## <a name="why-did-cash-flow-power-bi-work-in-previous-versions-but-is-now-blank"></a>Pourquoi les flux de trésorerie Power BI fonctionnaient dans les versions précédentes mais sont maintenant vides ?

Vérifiez que les mesures « Mesure de flux de trésorerie V2 » et « LedgerCovLiquidityMeasurement » du magasin d'entités ont été configurées. Pour plus d'informations sur l'utilisation des données dans le magasin d'entités, consultez [Intégration de Power BI avec le magasin des entités](../../fin-ops-core/dev-itpro/analytics/power-bi-integration-entity-store.md) Vérifiez que toutes les étapes requises pour afficher le contenu Power BI ont bien été effectuées. Pour plus d’informations, voir [Contenu Power BI - Vue d’ensemble des disponibilités](Cash-Overview-Power-BI-content.md).

## <a name="have-the-entity-store-entities-been-refreshed"></a>Les entités du magasin d'entités ont-elles été actualisées ?

Vous devez actualiser périodiquement vos entités pour vous assurer que les données sont à jour et exactes. Pour actualiser manuellement une entité spécifique, accédez à **Administration système \> Paramétrage \> Magasin des entités**, sélectionnez l'entité, puis sélectionnez **Actualiser**. Les données peuvent également être mises à jour automatiquement. Sur la page **Magasin des entités**, définissez l'option **Actualisation automatique activée** sur **Oui**.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]