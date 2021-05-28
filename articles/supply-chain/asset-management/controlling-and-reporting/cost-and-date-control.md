---
title: Contrôle de date et de coût
description: Cette rubrique explique le contrôle de date et de coût dans le module Gestion des actifs.
author: johanhoffmann
ms.date: 08/23/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EntAssetBICostControlWorkspace, EntAssetWorkOrderDateControl, EntAssetWorkOrderForecastCostInfoPart, EntAssetMaintenanceCostTrans, EntAssetWorkOrderDateControlCalcDialog, EntAssetCostControl, EntAssetCostObjectCalendar, EntAssetWorkOrderCostInfoPart
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: c09dee94891fb78c22e8cf9f203cb7f5531bb968
ms.sourcegitcommit: 51cad1ce3ed44ebf7eb9bdf553ee2df4c1f03135
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/10/2021
ms.locfileid: "6016130"
---
# <a name="cost-and-date-control"></a>Contrôle de date et de coût

[!include [banner](../../includes/banner.md)]

Dans le module Gestion des actifs, vous pouvez calculer des coûts pour obtenir une vue d’ensemble des coûts réels comparés aux coûts budgétaires des actifs, des postes techniques et des ordres de travail. Les coûts réels sont basés sur des transactions validées.

Vous pouvez également effectuer un calcul de date si vous souhaitez comparer les dates de début et de fin prévues par rapport aux dates de début et de fin réelles sur les ordres de travail.

## <a name="cost-control-for-assets-functional-locations-and-work-orders"></a>Contrôle des coûts pour des actifs, des postes techniques et des ordres de travail

Les calculs effectués pour les actifs, les postes techniques et les ordres de travail sont quasiment identiques. La seule différence réside dans le fait que pour les actifs et les postes techniques, vous pouvez également inclure les sous-actifs et les sous-postes dans votre calcul. La date est la date de transaction à laquelle l’enregistrement a été enregistré.

1. Cliquez sur **Gestion des actifs** > **Recherches** > **Actifs** > **Contrôle des coûts d’actif** ou **Contrôle des coûts du poste technique** ou **Gestion des actifs** > **Recherches** > **Ordres de travail** > **Contrôle des coûts des ordres de travail**.

2. Dans la boîte de dialogue **Contrôle des coûts d’actif** / **Contrôle des coûts du poste technique** / **Contrôle des coûts des ordres de travail**, sélectionnez une plage de dates à calculer.

3. Si nécessaire, sélectionnez un ensemble de dimensions financières à inclure dans le calcul.

4. Sélectionnez « Oui » sur le bouton bascule **Ignorer lignes nulles** si vous ne souhaitez pas afficher les résultats ayant des coûts supérieurs à zéro.

5. Vous pouvez utiliser le champ **Niveau** pour indiquer quel niveau de détail vous souhaitez dans les lignes de contrôle de coût en fonction des postes techniques. 

    Par exemple, si vous insérez le chiffre 1 dans le champ, et que vous avez une hiérarchie de postes techniques à plusieurs niveaux, toutes les lignes de contrôle des coûts pour un poste technique s’affichent dans le niveau supérieur et il est donc possible d’ajouter les heures sur une ligne à partir des postes techniques situés à un niveau inférieur.

    Par exemple, si vous insérez le chiffre 0 dans le champ **Niveau**, un résultat détaillé s’affiche et indique toutes les lignes de contrôle de coût sur tout le niveau du poste technique auquel elles sont liées.

6. Sélectionnez « Oui » sur le bouton bascule **Afficher les coûts engagés en cours** pour inclure cette colonne dans le calcul.

7. Sélectionnez « Oui » sur le bouton à bascule **Inclure les sous-actifs** pour afficher les coûts associés aux sous-actifs comme lignes distinctes.

8. Pour limiter la recherche, vous pouvez sélectionner des actifs/postes techniques/ordres de travail sur l’organisateur **Enregistrements à inclure**.

9. Cliquez sur **OK** pour démarrer le calcul.

    L’illustration suivante présente un exemple de la boîte de dialogue **Contrôle des coûts d’actif**.

    ![Boîte de dialogue Contrôle des coûts des actifs](media/01-controlling-and-reporting.png)

10. Sur la page **Contrôle des coûts d’actif**, cliquez sur le bouton **Grouper par**, cliquez sur les boutons appropriés à afficher le niveau requis de détail du calcul. Les boutons **Grouper par** sélectionnés sont mis en surbrillance. Cliquez sur un bouton pour l’activer ou le désactiver.

## <a name="example-of-calculation-results-in-asset-cost-control"></a>Exemples de résultats de calcul dans Contrôle des coûts d’actif

La capture d’écran suivante présente un exemple de résultats du calcul dans **Contrôle des coûts d’actif**.

- Le champ **Budget d’origine** indique les coûts budgétaires à partir des prévisions de l’ordre de travail. 
- Le champ **Coût engagé** indique le montant total de dépenses que l’entité juridique s’est engagée à payer. 
- Le champ **Coûts engagés en cours** indique les engagements à payer des articles, des heures, et des services commandés ou reçus mais pas encore réglés. 
- Le champ **Coût réel** affiche les coûts associés lorsque tous les enregistrements de consommation ont été validés.

![Exemples de résultats de calcul dans Contrôle des coûts d’actif](media/02-controlling-and-reporting.png)

Une autre manière d’effectuer un calcul du coût est de choisir plusieurs actifs dans **Tous les actifs** ou **Actifs actifs**. Cliquez ensuite sur le bouton **Contrôle des coûts** sur l’onglet **Général** . Dans la boîte de dialogue **Contrôle des coûts d’actif**, les actifs sélectionnés sont insérés automatiquement dans le champ **Actif** sur l’organisateur **Enregistrements à inclure**. Cliquez sur **OK** et un calcul des coûts pour les actifs sélectionnés s’affiche. La même procédure peut être effectuée pour les postes techniques dans **Tous les postes techniques** ou **Postes techniques actifs**, et pour les ordres de travail dans **Tous les ordres de travail** ou **Ordres de travail actifs**.

## <a name="work-order-date-control"></a>Contrôle de la date de l’ordre de travail

Cette page permet d’obtenir une vue d’ensemble des dates de début et de fin attendues par rapport aux dates de début et de fin réelles sur les ordres de travail.

1. Cliquez sur **Gestion des actifs** > **Recherches** > **Ordres de travail** > **Contrôle de date d’ordre de travail**.

2. Cliquez sur **Calculer.**

3. Sélectionnez un poste technique dans le champ **Poste technique**.

4. Insérez la plage pour laquelle vous souhaitez effectuer le calcul dans les champs **Date de début** et **Date de fin**. Tous les ordres de travail avec la date de début prévue dans la plage seront inclus.

5. Cliquez sur **OK**.

6. Cliquez sur les boutons **Grouper par** pour afficher le niveau requis de détail du calcul. Les boutons **Grouper par** sélectionnés sont mis en surbrillance. Cliquez sur un bouton pour l’activer ou le désactiver.

## <a name="example-of-calculation-results-in-work-order-date-control"></a>Exemples de résultats de calcul dans Contrôle de la date de l’ordre de travail

La capture d’écran suivante présente un exemple des résultats des calculs dans **Contrôle de date d’ordre de travail**.

- Le champ **Retard de début moyen** indique la différence en jours entre la date de début prévue pour un bon de travail par rapport à la date de début réelle. Si, par exemple, la date de début réelle était deux jours avant la date de début prévue, « -2 » s’affichera dans ce champ.  
- Le champ **Retard de fin moyen** indique la différence en jours entre la date de fin prévue pour un bon de travail par rapport à la date de fin réelle. Si, par exemple, la date de fin réelle était trois jours après la date de fin prévue, « -3 » s’affichera dans ce champ.  
- Les champs **Occurrences** indiquent le nombre d’écarts entre les dates de début et de fin prévues et celles de début et de fin réelles sur les ordres de travail.

![Exemples de résultats de calcul dans Contrôle de la date de l’ordre de travail](media/03-controlling-and-reporting.png)




[!INCLUDE[footer-include](../../../includes/footer-banner.md)]