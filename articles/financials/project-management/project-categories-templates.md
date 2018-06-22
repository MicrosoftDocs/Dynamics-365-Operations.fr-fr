---
title: "Synchroniser les catégories de dépense de projet à partir de Project Service Automation"
description: "Cette rubrique décrit les modèles et les tâches sous-jacentes qui sont utilisés pour synchroniser les catégories de dépense de projet entre Microsoft Dynamics 365 for Finance and Operations et Dynamics 365 for Project Service Automation."
author: KimANelson
manager: AnnBe
ms.date: 04/02/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 87983
ms.assetid: b454ad57-2fd6-46c9-a77e-646de4153067
ms.search.region: Global
ms.author: knelson
ms.search.validFrom: 2016-11-28
ms.dyn365.ops.version: AX 8.0.0
ms.translationtype: HT
ms.sourcegitcommit: bd8feff598cf80ca675c7d2b5dda636799b19e29
ms.openlocfilehash: dcdb9b6ec296073d511c069cdceb1c61080b6d97
ms.contentlocale: fr-fr
ms.lasthandoff: 05/29/2018

---

# <a name="synchronize-project-expense-categories-between-finance-and-operations-and-project-service-automation"></a>Synchroniser les catégories de dépense de projet entre Finance and Operations et Project Service Automation

Cette rubrique décrit les modèles et les tâches sous-jacentes qui sont utilisés pour synchroniser les catégories de dépense de projet entre Microsoft Dynamics 365 for Finance and Operations et Dynamics 365 for Project Service Automation.

> [!NOTE]
> L'intégration des tâches de projet, les catégories de transaction de dépense, les estimations des heures, les estimations des dépenses et le verrouillage des fonctionnalités sont disponibles dans la version 8.0 de Dynamics 365 for Finance and Operations.

## <a name="data-flow-for-project-service-automation-and-finance-and-operations"></a>Flux de données pour Project Service Automation et Finance and Operations

La solution d'intégration de Project Service Automation avec Finance and Operations utilise la fonction Intégration des données pour synchroniser les données entre les instances de Project Service Automation et de Finance and Operations. Les modèles d'intégration disponibles avec la fonction Intégration des données activent le flux de données sur les catégories de transaction de dépense du projet entre Finance and Operations et Project Service Automation.

Si les catégories de dépense de projet sont gérées dans Finance and Operations, le flux d'intégration s'effectue d'abord de Finance and Operations vers Project Service Automation, puis les ID d'intégration des catégories de dépense de projet sont mis à jour par synchronisation entre Project Service Automation et Finance and Operations.

Si les catégories de dépense de projet sont gérées dans Project Service Automation, le flux d'intégration s'effectue d'abord de Project Service Automation vers Finance and Operations. Les catégories de projet doivent déjà être configurées dans Finance and Operations avant la synchronisation à partir de Project Service Automation. Effectuez ensuite la synchronisation de Finance and Operations vers Project Service Automation, puis de Project Service Automation vers Finance and Operations. Cela garantit que les catégories sont liées et que des doublons ne sont pas créés.

> [!NOTE]
> Généralement, les catégories de dépense de projet sont gérées dans Finance and Operations. Si tel n'est pas votre cas, ou si des catégories de dépense sont déjà créées dans Project Service Automation, vous devez d'abord effectuer la synchronisation à l'aide des catégories de transaction de dépense de projet (PSA vers Fin and Ops), puis effectuer la synchronisation à l'aide des catégories de transaction de dépense de projet (Fin and Ops vers PSA). Vous devez ensuite effectuer la synchronisation de PSA vers Fin and Ops encore une fois.

> Si vous effectuez la synchronisation à partir de Project Service Automation, les catégories de projet doivent déjà être paramétrées dans Finance and Operations, et les catégories de projet devant être synchronisées avec les catégories de transaction de Project Service Automation doivent être paramétrées comme **Actives dans les journaux**.

L'illustration suivante indique comment les données sont synchronisées entre Project Service Automation et Finance and Operations.

[![Flux de données pour l'intégration de Project Service Automation avec Finance and Operations](./media/ProjectExpenseCategoriesFlow.png)](./media/ProjectExpenseCategoriesFlow.png)


## <a name="templates-and-tasks"></a>Modèles et tâches

Pour accéder aux modèles disponibles, dans le centre d'administrateur de Microsoft PowerApps, sélectionnez **Projets**, puis, dans le coin supérieur droit, sélectionnez **Nouveau projet** pour sélectionner des modèles publics.

Le modèle et la tâche sous-jacente ci-après sont utilisés pour synchroniser les catégories de dépense de projet entre Finance and Operations et Project Service Automation :

-  **Nom du modèle dans le module Intégration des données :** Catégories de transaction de dépense de projet (Fin and Ops vers PSA)
-  **Nom de la tâche dans le projet :** Synchroniser les catégories avec PSA

## <a name="entity-set"></a>Ensemble d'entités

| Finance and Operations               | Project Service Automation    |
|--------------------------------------|-------------------------------|
| Entité d'intégration des catégories    | Catégories de transaction        |

## <a name="entity-flow"></a>Flux d'entité

Les catégories de dépense de projet sont gérées dans Finance and Operations, et elles sont synchronisées avec Project Service Automation en tant que catégories de transaction.

## <a name="power-query"></a>Power Query

Vous devez utiliser Microsoft Power Query pour définir le type de facturation sur la catégorie de transaction lors de la synchronisation avec Project Service Automation. Une colonne par défaut et une mise en correspondance sont déjà fournies pour le modèle Catégories de transaction de dépense de projet (Fin and Ops vers PSA). Si vous créez votre propre modèle, vous devez ajouter une colonne conditionnelle dans Power Query.
- Ouvrez l'écran Requête et filtrage avancés dans la mise en correspondance de la tâche de catégories de dépense de projet.
- Sélectionnez **Ajouter une colonne conditionnelle**.
- Attribuez un nom à la nouvelle colonne, par exemple BillingType.
- Entrez la condition suivante : si **CATEGORYID n'est pas égal à null, alors 19235001 ; sinon null**.
- Cliquez sur **OK** dans la colonne.
- Veillez à mettre en correspondance cette nouvelle colonne dans la page de mise en correspondance.

L'illustration suivante présente un exemple de mise en correspondance des tâches du modèle dans le module Intégration des données. La mise en correspondance indique les informations de champ qui sont synchronisées entre Finance and Operations et Project Service Automation.

[![Mise en correspondance des modèles](./media/ProjectExpenseCategoriesToPSAMapping.jpg)](./media/ProjectExpenseCategoriesToPSAMapping.jpg)

Le modèle et la tâche sous-jacente ci-après sont utilisés pour synchroniser les catégories de dépense de projet entre Project Service Automation et Finance and Operations :

-**Nom du modèle dans le module Intégration des données :** Catégories de transaction de dépense de projet (PSA vers Fin and Ops) -**Nom de la tâche dans le projet :** Synchroniser les catégories avec Fin Ops

## <a name="entity-set"></a>Ensemble d'entités

| Project Service Automation      | Finance and Operations             |
|---------------------------------|------------------------------------|
| Catégories de transaction          | Entité d'intégration des catégories  | 

## <a name="entity-flow"></a>Flux d'entité

Les catégories de dépense de projet sont gérées dans Finance and Operations, et elles sont synchronisées avec Project Service Automation en tant que catégories de transaction. La synchronisation avec Finance and Operations met à jour l'ID d'intégration de Project Service Automation sur la catégorie de projet Finance and Operations.

L'illustration suivante présente un exemple de mise en correspondance des tâches du modèle dans le module Intégration des données.

> [!NOTE]
> La mise en correspondance indique les informations de champ qui sont synchronisées entre Project Service Automation et Finance and Operations.

[![Mise en correspondance des modèles](./media/ProjectExpenseCategoriesToFinOpsMapping.jpg)](./media/ProjectExpenseCategoriesToFinOpsMapping.jpg)

