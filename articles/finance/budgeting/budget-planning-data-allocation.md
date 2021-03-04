---
title: Répartition de données de planification budgétaire
description: Cet sujet décrit les différentes méthodes de répartition disponibles dans Microsoft Dynamics 365 Finance et comment elles peuvent être utilisées.
author: ShylaThompson
manager: AnnBe
ms.date: 03/05/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: BudgetPlanningConfiguration
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 15191
ms.assetid: 89a918e8-59a4-4711-a2e9-b41989ddd0f1
ms.search.region: Global
ms.author: sigitac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: ceddeda5760d961568d58e7e4805955ea972c586
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4443299"
---
# <a name="budget-planning-data-allocation"></a>Répartition de données de planification budgétaire

[!include [banner](../includes/banner.md)]

Cet sujet décrit les différentes méthodes de répartition disponibles dans Microsoft Dynamics 365 Finance et comment elles peuvent être utilisées.  

Vous pouvez répartir les données dans un plan budgétaire de plusieurs manières afin d’illustrer précisément les montants projetés.

## <a name="allocation-methods"></a>Modes de répartition
Trois méthodes de répartition (Répartir par le biais de périodes, Répartir vers les dimensions et Utiliser les règles de répartition comptable) permettent de créer les lignes de plan budgétaire basées sur les lignes du même plan budgétaire. Trois autres méthodes (Regrouper, Distribuer et Copier à partir du plan budgétaire) permettent de créer des lignes de plan budgétaire dans d’autres plans budgétaires. Pour chacune des six méthodes de répartition, vous devez préciser le scénario de destination. Le scénario de destination peut être identique ou non au scénario source. En outre, vous pouvez préciser si de nouvelles lignes sont ajoutées au plan budgétaire ou remplacer les lignes actuelles du plan budgétaire.

> [!NOTE] 
> Un scénario unique doit être utilisé pour l’agrégation, différent du scénario qui a été utilisé pour la distribution ou d’autres modifications précédemment effectuées dans le plan parent.  

[![Méthode de répartition Répartir par le biais de périodes](./media/allocateacrossperiods-300x259.png)](./media/allocateacrossperiods.png)
**Répartir par le biais de périodes** – Une catégorie de répartition par période est utilisée pour répartir les lignes de plan budgétaire à partir du scénario de plan budgétaire source sur les périodes du scénario de destination. Le montant source est réparti sur plusieurs lignes du scénario de destination, selon le pourcentage et la date définis dans la catégorie de répartition par période.         

[![Méthode de répartition Répartir vers les dimensions](./media/allocatetodimensions.jpg)](./media/allocatetodimensions.jpg)
**Répartir vers les dimensions** – Les lignes du plan budgétaire sont réparties depuis le scénario de planification budgétaire source vers une ou plusieurs lignes du scénario de destination, en fonction des pourcentages et des dimensions financières définies dans une condition de répartition budgétaire.           

![Graphique Regrouper](./media/aggregatechart-300x230.png)
**Regrouper** – Les lignes de plan budgétaire sont regroupées depuis le scénario de plan budgétaire source dans les plans budgétaires (enfants) associés vers le scénario de destination dans le plan budgétaire parent. Cette méthode active les montants budgétaires préparés à un niveau inférieur de l’organisation pour les consolider à un niveau supérieur.          

[![Graphique Distribuer](./media/distributechart-300x230.png)](./media/distributechart.png)
**Distribuer** – Les lignes de plan budgétaires sont distribuées depuis le scénario de planification budgétaire source dans le plan budgétaire parent vers le scénario de destination dans les plans budgétaires (enfants) associés, selon les dimensions financières des unités organisationnelles des plans associés. Cette méthode active les montants budgétaires préparés à un niveau supérieur de l’organisation afin de les répartir pour une révision plus localisée.           

[![Règles de répartition comptable](./media/ledgerallocationrules-300x202.png)](./media/ledgerallocationrules.png)
**Utiliser les règles de répartition comptable** – Les lignes de plan budgétaire sont distribuées depuis le scénario de planification budgétaire source vers le scénario de destination, selon la règle de répartition comptable sélectionnée. 

[![Copier à partir du plan budgétaire](./media/copyfrombudgetplan-187x300.png)](./media/copyfrombudgetplan.png)
**Copier à partir du plan budgétaire** – À l’instar de la méthode de répartition par distribution, les lignes de plan budgétaire sont créées dans la destination, en fonction des lignes d’un plan budgétaire associé. Toutefois, pour cette méthode, le plan budgétaire source n’a pas à être le parent, mais peut se situer à n’importe quel niveau supérieur dans la hiérarchie du plan budgétaire. Cette méthode de répartition est utile si les montants consolidés sont initialement budgétés à un niveau beaucoup plus haut et doivent être transférés à un niveau inférieur de l’organisation pour une révision détaillée et un ajustement avant de pouvoir obtenir une approbation de niveau supérieur.          

## <a name="using-allocation-methods-in-a-budget-plan"></a>Utilisation des méthodes de répartition dans un plan budgétaire
Pour exécuter des répartitions sur la page du plan budgétaire, sélectionnez les lignes à répartir, puis cliquez sur **Répartir le budget**.

[![Bouton Répartir le budget](./media/allocatebudgetbutton-300x84.png)](./media/allocatebudgetbutton.png) 

Puis, sélectionnez une méthode de répartition. Les champs restants sont alors définis selon la méthode sélectionnée. Ces champs comprennent la source et la destination des données du plan budgétaire, ainsi qu’une option vous permettant de multiplier la source par un facteur spécifié lorsque les montants de destination sont créés, afin de simplifier l’ajustement en bloc. Vous pouvez également définir l’option **Ajouter au plan**. Sélectionnez **Non** pour remplacer les lignes existantes du plan budgétaire, ou sélectionnez **Oui** pour conserver les lignes existantes du plan budgétaire et ajouter de nouvelles lignes pour les montants répartis.

## <a name="automating-allocations-during-a-workflow"></a>Automatisation des répartitions au cours d’un workflow
Une fonctionnalité puissante permet d’activer les répartitions automatiques dans le cadre d’un workflow de planification budgétaire. Au fur et à mesure qu’un plan budgétaire progresse dans son workflow, les tâches automatiques peuvent demander une répartition à un moment spécifique de la planification budgétaire. 

Pour paramétrer une répartition automatique, vous devez tout d’abord créer un programme de répartition sur la page **Configuration de la planification budgétaire**. Le programme de répartition définit la méthode de répartition à utiliser lorsque la répartition automatique est effectuée, ainsi que les valeurs des diverses options de répartition (voir la section précédente pour les descriptions). 

Ensuite, vous créez une répartition de stade sur la page **Configuration de la planification budgétaire**. La répartition de stade attribue un programme de répartition au stade et au workflow de planification budgétaire. 

Enfin, ajoutez une tâche automatique pour le stade de planification budgétaire au stade de workflow souhaité. Dans l’exemple suivant, deux répartitions de stade de planification budgétaire (décrites en rouge) ont été insérées dans le workflow.

[![Répartitions de stade de planification budgétaire](./media/budgetplanningstageallocations-300x300.png)](./media/budgetplanningstageallocations.png)





[!INCLUDE[footer-include](../../includes/footer-banner.md)]