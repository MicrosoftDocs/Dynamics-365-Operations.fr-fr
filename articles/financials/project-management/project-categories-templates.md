---
title: "Synchroniser les catégories de dépense de projet entre Finance and Operations et Project Service Automation"
description: "Cette rubrique décrit les modèles et les tâches sous-jacentes qui sont utilisés pour synchroniser les catégories de dépense de projet entre Microsoft Dynamics 365 for Finance and Operations et Microsoft Dynamics 365 for Project Service Automation."
author: KimANelson
manager: AnnBe
ms.date: 07/20/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 87983
ms.assetid: b454ad57-2fd6-46c9-a77e-646de4153067
ms.search.region: Global
ms.author: knelson
ms.search.validFrom: 2016-11-28
ms.dyn365.ops.version: AX 8.0.0
ms.translationtype: HT
ms.sourcegitcommit: d9747ba144d56c9410846769e5465372c89ea111
ms.openlocfilehash: c4d09fde2cf4335553243c136590f9f3135db97a
ms.contentlocale: fr-fr
ms.lasthandoff: 08/08/2018

---

# <a name="synchronize-project-expense-categories-between-finance-and-operations-and-project-service-automation"></a>Synchroniser les catégories de dépense de projet entre Finance and Operations et Project Service Automation

[!include[banner](../includes/banner.md)]

Cette rubrique décrit les modèles et les tâches sous-jacentes qui sont utilisés pour synchroniser les catégories de dépense de projet entre Microsoft Dynamics 365 for Finance and Operations et Microsoft Dynamics 365 for Project Service Automation.

> [!NOTE]
> - L'intégration de tâche de projet, les catégories de transaction de dépense, les estimations des heures, les estimations des dépenses et le verrouillage des fonctionnalités sont disponibles dans la version 8.0 de Microsoft Dynamics 365 for Finance and Operations.
> - L'intégration des transactions réelles est disponible dans la version 8.01 de Microsoft Dynamics 365 for Finance and Operations ou ultérieure.
> - Si vous utilisez Microsoft Dynamics 365 for Finance and Operations, Enterprise edition 7.3.0, après avoir installé KB 4132657 et KB 4132660, vous pourrez utiliser les modèles pour intégrer les tâches de projet, les catégories de transaction de dépense, les estimations des heures, les estimations des dépenses et les transactions réelles, ainsi que pour configurer le verrouillage des fonctionnalités. Si vous devez réinitialiser les répartitions comptables, nous vous recommandons d'installer également KB 4131710.

## <a name="data-flow-for-project-service-automation-and-finance-and-operations"></a>Flux de données pour Project Service Automation et Finance and Operations

La solution d'intégration de Project Service Automation avec Finance and Operations utilise la fonction Intégration des données pour synchroniser les données entre les instances de Project Service Automation et de Finance and Operations. Les modèles d'intégration disponibles avec la fonction Intégration des données activent le flux de données sur les catégories de transaction de dépense du projet entre Finance and Operations et Project Service Automation.

Si les catégories de dépense de projet sont gérées dans Finance and Operations, le flux d'intégration s'effectue d'abord de Finance and Operations vers Project Service Automation. Les ID d'intégration des catégories de dépenses du projet sont ensuite mis à jour par la synchronisation de Project Service Automation vers Finance and Operations.

Si les catégories de dépense de projet sont gérées dans Project Service Automation, le flux d'intégration s'effectue d'abord de Project Service Automation vers Finance and Operations. Les catégories de projet doivent déjà être configurées dans Finance and Operations avant la synchronisation à partir de Project Service Automation. Effectuez ensuite la synchronisation de Finance and Operations vers Project Service Automation, puis de Project Service Automation vers Finance and Operations. Ainsi, vous garantissez que les catégories sont liées, et qu'aucun double n'est créé.

> [!NOTE]
> Généralement, les catégories de dépense de projet sont gérées dans Finance and Operations. Toutefois, si elles ne sont pas gérées dans Finance and Operations, ou si des catégories de dépenses ont déjà été créées dans Project Service Automation, vous devez d'abord synchroniser à l'aide du modèle des catégories de transaction de dépense de projet (PSA vers Fin and Ops). Ensuite, effectuez la synchronisation à l'aide du modèle des catégories de transaction de dépense de projet (Fin and Ops vers PSA). Vous devez ensuite exécuter la synchronisation de Project Service Automation vers Finance and Operations une fois encore.
>
> Si vous synchronisez d'abord depuis Project Service Automation, les conditions suivantes doivent être remplies dans Finance and Operations avant que la synchronisation soit exécutée :
>
> - La catégorie partagée correspondant à la catégorie de projet paramétrée dans Project Service Automation doit exister, et elle doit être activée pour **Projet** et **Dépenses**.
> - Pour chaque entité juridique Finance and Operations qui doit y être intégrée, les catégories de projet suivantes doivent exister :
>
>     - **Catégorie de projet** existe. 
>     - **Utiliser dans Dépense** est activé.
>     - **Actif/active dans les journaux** est activé.
>     - **Type de transaction** est défini sur **Dépense**.

L'illustration suivante indique comment les données sont synchronisées entre Project Service Automation et Finance and Operations.

[![Flux de données pour l'intégration de Project Service Automation avec Finance and Operations](./media/ProjectExpenseCategoriesFlow.png)](./media/ProjectExpenseCategoriesFlow.png)

## <a name="project-expense-category-synchronization-from-finance-and-operations-to-project-service-automation"></a>Synchronisation de la catégorie de dépense de projet entre Finance and Operations et Project Service Automation

### <a name="template-and-task"></a>Modèle et tâche

Pour accéder au modèle, dans le centre d'administrateur de Microsoft PowerApps, sélectionnez **Projets**, puis, dans le coin supérieur droit, sélectionnez **Nouveau projet** pour sélectionner des modèles publics.

Le modèle et la tâche sous-jacente ci-après sont utilisés pour synchroniser les catégories de dépense de projet entre Finance and Operations et Project Service Automation :

- **Nom du modèle dans le module Intégration des données :** Catégories de transaction de dépense de projet (Fin and Ops vers PSA)
- **Nom de la tâche dans le projet :** Synchroniser les catégories avec PSA

### <a name="entity-set"></a>Ensemble d'entités

| Finance and Operations            | Project Service Automation |
|-----------------------------------|----------------------------|
| Entité d'intégration des catégories | Catégories de transaction     |

### <a name="entity-flow"></a>Flux d'entité

Les catégories de dépense de projet sont gérées dans Finance and Operations, et elles sont synchronisées avec Project Service Automation en tant que catégories de transaction.

### <a name="power-query"></a>Power Query

Lors de la synchronisation avec Project Service Automation, vous devez utiliser Microsoft Power Query pour Excel pour définir le type de facturation sur la catégorie de transaction. Une colonne par défaut et une mise en correspondance sont fournies pour le modèle Catégories de transaction de dépense de projet (Fin and Ops vers PSA). Si vous créez votre propre modèle, vous devez ajouter une colonne conditionnelle dans Power Query. Procédez comme suit.

1. Cliquez sur la flèche pour ouvrir la mise en correspondance de la tâche des catégories de dépenses de projet dans le modèle de catégories de transaction de dépense de projet (Fin and Ops vers PSA).
2. Cliquez sur le lien **Requête et filtrage avancés** pour ouvrir Power Query.
2. Sélectionnez **Ajouter une colonne conditionnelle**.
3. Entrez un nom pour la nouvelle colonne, comme **Type de facturation**.
4. Entrez la condition suivante : **si CATEGORYID n'est pas égal à null, alors 19235001 ; sinon null**.
5. Cliquez sur **OK** dans la colonne.
6. Veillez à mettre en correspondance cette nouvelle colonne sur la page de mise en correspondance.

L'illustration suivante présente un exemple de mise en correspondance des tâches du modèle dans le module Intégration des données. La mise en correspondance indique les informations de champ qui sont synchronisées entre Finance and Operations et Project Service Automation.

[![Mise en correspondance des modèles](./media/ProjectExpenseCategoriesToPSAMapping.jpg)](./media/ProjectExpenseCategoriesToPSAMapping.jpg)

## <a name="project-expense-category-synchronization-from-project-service-automation-to-finance-and-operations"></a>Synchronisation de la catégorie de dépense de projet de Project Service Automation vers Finance and Operations.

### <a name="template-and-task"></a>Modèle et tâche

Le modèle et la tâche sous-jacente ci-après sont utilisés pour synchroniser les catégories de dépense de projet de Project Service Automation vers Finance and Operations :

- **Nom du modèle dans le module Intégration des données :** Catégories de transaction de dépense de projet (PSA vers Fin and Ops)
- **Nom de la tâche dans le projet :** Synchroniser les catégories vers Fin Ops

### <a name="entity-set"></a>Ensemble d'entités

| Project Service Automation | Finance and Operations            |
|----------------------------|-----------------------------------|
| Catégories de transaction     | Entité d'intégration des catégories |

### <a name="entity-flow"></a>Flux d'entité

Les catégories de dépense de projet sont gérées dans Finance and Operations, et elles sont synchronisées avec Project Service Automation en tant que catégories de transaction. La synchronisation avec Finance and Operations met à jour la catégorie de projet dans Finance and Operations avec l'ID d'intégration de Project Service Automation.

### <a name="template-mapping-in-data-integration"></a>Mise en correspondance de modèles dans l'intégration de données

L'illustration suivante présente un exemple de mise en correspondance des tâches du modèle dans le module Intégration des données.

> [!NOTE]
> La mise en correspondance indique les informations de champ qui sont synchronisées entre Project Service Automation et Finance and Operations.

[![Mise en correspondance des modèles](./media/ProjectExpenseCategoriesToFinOpsMapping.jpg)](./media/ProjectExpenseCategoriesToFinOpsMapping.jpg)

