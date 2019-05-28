---
title: Conventions d'amortissement des immobilisations
description: Cette rubrique fournit une vue d'ensemble des conventions d'amortissement des immobilisations.
author: saraschi2
manager: AnnBe
ms.date: 03/21/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: AssetDepreciationProfile
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 13891
ms.assetid: 36d1112d-921c-4fff-abe0-0ff2429848d3
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 6880a4b97af0a819684dac7e0132ae10a8997533
ms.sourcegitcommit: 2b890cd7a801055ab0ca24398efc8e4e777d4d8c
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/07/2019
ms.locfileid: "1514299"
---
# <a name="fixed-asset-depreciation-conventions"></a>Conventions d'amortissement des immobilisations

[!include [banner](../includes/banner.md)]

Les conventions d'amortissement sont utilisées pour déterminer quand et comment l'amortissement est calculé pour l'année où l'immobilisation est acquise et l'année où l'immobilisation est cédée.

Les conventions d'amortissement peuvent être affectées au paramétrage pour un registre de groupe d'immobilisations. Pour afficher ou affecter la convention d'amortissement, dans la zone de paramétrage des immobilisations, sélectionnez **Groupes d'immobilisations**. Sélectionnez le bouton **Registres**. Dans ce cas, les conventions d'amortissement affectées sont utilisées comme valeurs par défaut lorsque les registres d'immobilisations sont créés. Les conventions d'amortissement peuvent également être définies sur un registre d'immobilisations individuel. Pour ce faire, sélectionnez **Registres** dans la zone de paramétrage des immobilisations, puis sélectionnez le bouton **Groupes d'immobilisations**.


|  Convention d'amortissement  |   Description  |
|---------------------------|-----------------|
|           Aucune            |  Les actifs commencent à s'amortir à la date de <strong>Mise en service</strong>.|
|         Semestre         |  Déduisez un semestre d'amortissement pour la première année et la dernière année d'amortissement de la propriété. Déduisez une année complète d'amortissement un an sur deux au cours du délai de récupération. |
|        Mois complet         | Les actifs ayant une date de <strong>Mise en service</strong> survenant à tout moment au début du mois commencent à s'amortir le premier jour de ce mois. Les actifs désaffectés à tout moment du mois sont considérés comme désaffectés à des fins d'amortissement le dernier jour du mois précédent.  |
|        Mi-trimestre        | Pour calculer votre déduction d'amortissement pour l'exercice lorsque vous mettez la propriété en service, multipliez l'amortissement pour une année complète par le pourcentage du trimestre lorsque la propriété est mise en service, comme indiqué dans le tableau suivant.<table><thead><tr><th>Trimestre</th><th>Pourcentage</th></tr></thead><tbody><tr><td>Premier</td><td>87,5</td></tr><tr><td>Deuxième</td><td>62,5</td></tr><tr><td>Troisième</td><td>37,5</td></tr><tr><td>Quatrième</td><td>12,5</td></tr></tbody></table>Un demi-trimestre d'amortissement est pris du trimestre de cession (ou trimestre entièrement amorti). |
| Mi-mois (1er du mois)  | Les actifs dont la date de <strong>Mise en service</strong> se trouve dans la première moitié du mois (entre le 1er et le 15) commencent à s'amortir le premier jour du mois de la date de <strong>Mise en service</strong>. Les actifs dont la date de <strong>Mise en service</strong> se trouve dans la seconde moitié du mois (entre le 16 et la fin du mois) commencent à s'amortir le premier jour du mois suivant la date de <strong>Mise en service</strong>. Les actifs désaffectés au cours de la première moitié du mois (entre le 1er et le 15) sont considérés comme désaffectés à des fins d'amortissement le dernier jour du mois précédent. Les actifs désaffectés au cours de la seconde moitié du mois (entre le 16 et la fin du mois) sont considérés comme désaffectés à des fins d'amortissement le dernier jour du mois de mise hors service. |
| Mi-mois (15 du mois) |  Pour calculer votre déduction d'amortissement pour l'exercice lorsque vous mettez la propriété en service, multipliez l'amortissement pour une année complète par une fraction. Le numérateur (nombre supérieur) de cette fraction est le nombre de mois complets de l'année pendant lesquels la propriété est en service, plus 1/2 ou (0,5). Le dénominateur (nombre inférieur) est 12. Si vous cédez la propriété avant la fin de la période de récupération, utilisez la même méthode pour calculer votre déduction d'amortissement pour l'exercice de cession.   |
| Semestre (début d'exercice) | Les actifs dont la date de <strong>Mise en service</strong> se trouve dans la première moitié de l'année commencent à s'amortir le premier jour de l'exercice (année complète). Les actifs dont la date de <strong>Mise en service</strong> se trouve dans la seconde moitié de l'année commencent à s'amortir au milieu de l'année.|
|   Semestre (exercice suivant)   |   Les actifs dont la date de <strong>Mise en service</strong> se trouve dans la première moitié de l'année commencent à s'amortir le premier jour de l'exercice (année complète). Les actifs dont la date de <strong>Mise en service</strong> se trouve dans la seconde moitié de l'année commencent à s'amortir le premier jour de l'exercice suivant. Les actifs désaffectés au cours de la première moitié de l'année sont considérés comme désaffectés à des fins d'amortissement le dernier jour de l'année précédente. Tout amortissement validé pendant l'année en cours doit être contrepassé ou ajusté en sortie. Les actifs qui sont mis hors service au second semestre de l'année sont considérés comme désaffectés à des fins d'amortissement le dernier jour de l'année de la mise hors service.|

