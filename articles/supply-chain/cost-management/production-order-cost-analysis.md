---
title: Analyse du coût de l'ordre de fabrication
description: Cet article fournit des informations sur l'analyse des coûts que vous pouvez effectuer pour les ordres de fabrication terminés et en cours. Analysez les coûts estimés et réels à l'aide de la page Calcul des prix ou les estimations des coûts ou de l'état Estimations et évaluations des coûts. Vous pouvez afficher les informations relatives aux coûts estimés et réels (et à la quantité) pour chaque composant, opération de gamme et coût indirect.
author: AndersGirke
manager: tfehr
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventCostTrans, ProdCalcTrans, ProdTableJour, ProdTableListPage
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: 79634
ms.assetid: ded5da04-f787-49f7-b5e5-75c2a2b92930
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: mguada
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 8d18ca6d76016380feb4503b7f2778ba068f5eca
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/02/2020
ms.locfileid: "3214548"
---
# <a name="production-order-cost-analysis"></a>Analyse du coût de l'ordre de fabrication

[!include [banner](../includes/banner.md)]

Cet article fournit des informations sur l'analyse des coûts que vous pouvez effectuer pour les ordres de fabrication terminés et en cours. Analysez les coûts estimés et réels à l'aide de la page Calcul des prix ou les estimations des coûts ou de l'état Estimations et évaluations des coûts. Vous pouvez afficher les informations relatives aux coûts estimés et réels (et à la quantité) pour chaque composant, opération de gamme et coût indirect.

Les coûts réels pour un ordre de fabrication sont basés sur la consommation déclarée de matériaux et d'opérations de gamme. Vous pouvez accéder à des transactions détaillées sur la consommation des matières, les opérations d'acheminement et les coûts indirects déclarés correspondant à un ordre de fabrication dans la page **Validation de la production**.

## <a name="variance-analysis-for-a-completed-production-order"></a>Analyse d'écart pour un ordre de fabrication terminé
Les écarts reflètent une comparaison des activités de production déclarées et le calcul des coûts standard pour la fabrication de l'article. Les écarts ne reflètent pas une comparaison par rapport aux coûts estimés de l'ordre de fabrication. Les activités de production déclarées incluent la consommation de matières et d'opérations de gamme, ainsi que les coûts indirects associés et la quantité qui est déclarée terminée. Les quatre types d'écart suivants sont calculés :

-   Écart de taille de lot
-   Écart de quantité de production
-   Écart de prix de production
-   Écart de substitution de production

Le diagramme suivant présente les quatre écarts pris en compte pour la différence entre les coûts réels d'un ordre de fabrication et les coûts calculés dans l'enregistrement des coûts de l'article lorsque l'ordre de fabrication est terminé. 

![Écarts qui expliquent les différences dans un ordre de fabrication terminé](./media/control.jpg) 

Vous pouvez analyser les écarts de production à l'aide de la page **Écart** ou de l'état **Écart de production**. Les options d'affichage permettent de visualiser les écarts détaillés par article et ressource opérationnelle, ou par groupe de coûts. La stratégie d'analyse des coûts figurant dans les paramètres de stock détermine si les écarts sont suivis par groupe de coûts. Vous pouvez également utiliser les options d'affichage **simple**, **multi** et **total** pour voir les écarts résumés. Les informations d'écart détaillées vous permettent de comprendre la source de chaque écart. Afin d'anticiper les écarts avant la fin d'un ordre de fabrication, analysez les informations détaillées fournies dans l'état **Estimations et évaluations des coûts**.

## <a name="cost-analysis-for-current-production-orders"></a>Analyse des coûts pour les ordres de fabrication en cours
Des états séparés présentent des informations sur chaque type de transaction. Ces états permettent d'analyser les coûts des activités de production déclarées. Les informations s'affichent uniquement pour les ordres de fabrication en cours ayant le statut **Commencé** ou**Déclaré terminé**.

-   **Matières en cours**− Cet état répertorie les transactions de prélèvements déclarées pour les ordres de fabrication en cours à partir d'une date de transaction spécifiée. L'état indique la quantité d'un composant qui a été sortie et le montant des coûts pour chaque transaction. Utilisez les critères de sélection pour un composant unique. Vous pouvez par exemple imprimer les informations relatives à la quantité émise du composant pour les ordres de fabrication applicables. La quantité émise n'est pas mise à jour par les quantités déclarées comme terminées pour l'article parent. Par conséquent, la quantité réelle de matières premières en cours peut être exagérée.
-   **Travail en cours**− Cet état répertorie les transactions de gamme (ou tâches déclarées) qui sont déclarées pour les ordres de fabrication en cours à partir d'une date de transaction spécifiée. L'état indique les heures, le montant et la quantité (la quantité correcte et la quantité erronée) qui sont déclarés pour chaque transaction. Il inclut également des informations telles que le numéro d'opération, l'ID opération et la ressource opérationnelle. En outre, cet état affiche les temps et les montant totaux pour toutes les transactions pour un ordre de fabrication ainsi que la quantité déclarée comme terminée.
-   **Coûts indirects en cours**− Cet état répertorie les coûts indirects encourus pour les ordres de fabrication. Ces données sont fondées sur la consommation déclarée d'opérations de gamme et de composants à partir d'une date de transaction spécifiée. L'état indique le type de coût indirect (surcharge ou taux), le code feuille de coûts pour les coûts indirects et le montant des coûts pour chaque transaction. Cet état ne fournit aucune information concernant la fiche production, ni la transaction de prélèvement qui a généré des coûts indirects.
-   **Évaluation de la production en cours**− Cet état répertorie la consommation combinée des matières, des opérations d'acheminement et les coûts indirects pour les ordres de fabrication à partir d'une date de transaction spécifiée.
-   **Articles finis en cours**− Cet état répertorie les ordres de fabrication en cours et les transactions déclarées terminées à partir d'une date de transaction spécifiée.


<a name="additional-resources"></a>Ressources supplémentaires
--------

[Sources courantes des écarts de production](common-sources-of-production-variances.md)



