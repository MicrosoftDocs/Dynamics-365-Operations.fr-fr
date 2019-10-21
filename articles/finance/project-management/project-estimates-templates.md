---
title: Synchroniser les estimations de projet directement de Project Service Automation vers Finance and Operations
description: Cette rubrique décrit les modèles et les tâches sous-jacentes utilisés pour synchroniser les estimations d'heure projet et les estimations de dépense projet directement depuis Microsoft Dynamics 365 Project Service Automation vers Dynamics 365 Finance.
author: KimANelson
manager: AnnBe
ms.date: 07/20/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 87983
ms.assetid: b454ad57-2fd6-46c9-a77e-646de4153067
ms.search.region: Global
ms.author: knelson
ms.search.validFrom: 2016-11-28
ms.dyn365.ops.version: AX 7.3.0
ms.openlocfilehash: 3b885610ac9ca8645358ba8ab6d46ab82143a534
ms.sourcegitcommit: 2460d0da812c45fce67a061386db52e0ae46b0f3
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/30/2019
ms.locfileid: "2250482"
---
# <a name="synchronize-project-estimates-directly-from-project-service-automation-to-finance-and-operations"></a>Synchroniser les estimations de projet directement de Project Service Automation vers Finance and Operations

[!include[banner](../includes/banner.md)]

Cette rubrique décrit les modèles et les tâches sous-jacentes utilisés pour synchroniser les estimations d'heure projet et les estimations de dépense projet directement depuis Dynamics 365 Project Service Automation vers Dynamics 365 Finance.

> [!NOTE]
> - L'intégration des tâches de projet, les catégories de transaction de dépense, les estimations des heures, les estimations des dépenses et le verrouillage des fonctionnalités sont disponibles dans la version 8.0.
> - L'intégration des chiffres réels est disponible dans version 8.0.1 ou version ultérieure.

## <a name="data-flow-for-project-service-automation-to-finance"></a>Flux de données pour Project Service Automation et Finance

La solution d'intégration de Project Service Automation avec Finance utilise la fonction Intégration des données pour synchroniser les données entre les instances de Project Service Automation et de Finance. Les modèles d'intégration disponibles avec la fonction Intégration des données activent le flux de données sur les estimations des heures du projet et les estimations des dépenses du projet entre Project Service Automation et Finance.

L'illustration suivante indique comment les données sont synchronisées entre Project Service Automation et Finance.

[![Flux de données pour l'intégration de Project Service Automation avec Finance](./media/ProjectEstimatesFlow.png)](./media/ProjectEstimatesFlow.png)

## <a name="project-hour-estimates"></a>Estimations en heures de projet

### <a name="template-and-tasks"></a>Modèle et tâches

Pour accéder aux modèles disponibles, dans le centre d'administrateur de Microsoft PowerApps, sélectionnez **Projets**, puis, dans le coin supérieur droit, sélectionnez **Nouveau projet** pour sélectionner des modèles publics.

Le modèle et les tâches sous-jacentes ci-après sont utilisés pour synchroniser les estimations des heures du projet entre Project Service Automation et Finance :

- **Nom du modèle dans le module Intégration des données :** Estimations des heures du projet (PSA vers Fin and Ops)
- **Nom des tâches du projet :**

    - Relations de transaction
    - Estimations des dépenses

### <a name="entity-set"></a>Ensemble d'entités

| Project Service Automation | Finances                                       |
|----------------------------|-----------------------------------------------|
| Tâches de projet              | Entité d'intégration des estimations des heures du projet |

### <a name="entity-flow"></a>Flux d'entité

Les estimations des heures du projet sont gérées dans Project Service Automation, et elles sont synchronisées avec Finance en tant que prévisions des heures du projet.

### <a name="prerequisites"></a>Conditions préalables

Avant toute synchronisation des estimations des heures du projet, vous devez synchroniser les projets, les tâches de projet et les catégories de transaction de dépense de projet.

### <a name="power-query"></a>Power Query

Dans le modèle des estimations en heures de projet, vous devez utiliser Microsoft Power Query pour Excel pour effectuer ces tâches :

- Définir l'ID du modèle de prévision par défaut qui est utilisé lorsque l'intégration crée de nouvelles prévisions en heures.
- Filtrer les enregistrements spécifiques aux ressources dans la tâche qui font échouer l'intégration en prévisions en heures.
- Filtrer les lignes de catégorie de transaction vides. Sinon, vous risquez de générer des prévisions en heures incorrectes.

#### <a name="set-the-default-forecast-model-id"></a>Définir l'ID de modèle de prévision par défaut

Pour mettre à jour l'ID du modèle de prévision par défaut dans le modèle, cliquez sur la flèche **Mettre en correspondance** pour ouvrir la fenêtre de mise en correspondance. Puis, sélectionnez le lien **Requête et filtrage avancés**.

- Si vous utilisez le modèle Estimations des heures Project (PSA vers Fin and Ops) par défaut, sélectionnez la **Condition insérée** dans la liste des **Étapes appliquées**. Dans l'entrée **Fonction**, remplacez **O\_forecast** par le nom de l'ID du modèle de prévision qui doit être utilisé avec l'intégration. Le modèle par défaut a un ID de modèle de prévision provenant des données de démonstration.
- Si vous créez un modèle, vous devez ajouter cette colonne. Dans Power Query, sélectionnez **Ajouter une colonne conditionnelle** et entrez un nom pour la nouvelle colonne, par exemple **ModelID**. Entrez la condition pour la colonne, selon laquelle si la tâche de projet n'a pas la valeur null, alors \<entrez l'ID du modèle de prévision\> ; sinon, null.

#### <a name="filter-out-resource-specific-records"></a>Filtrer les enregistrements spécifiques aux ressources

Le modèle Estimations des heures du projet (PSA vers Fin and Ops) a un filtre par défaut qui supprime les enregistrements spécifiques aux ressources. Si vous créez votre propre modèle, vous devez ajouter ce filtre. Sélectionnez le lien **Requête et filtrage avancés** pour filtrer la colonne **msdyn\_islinetask** afin d'inclure uniquement les enregistrements de type **False**.

#### <a name="filter-out-empty-transaction-category-rows"></a>Filtrer les lignes de catégorie de transaction vides

Vous devez ajouter un filtre pour supprimer les lignes qui contiennent des catégories de transaction vides. Cette tâche est obligatoire, que vous utilisiez le modèle par défaut ou créiez votre propre modèle. Ce filtre supprime les lignes récapitulatives de Project Service Automation susceptibles de rendre les prévisions en heures dans Finance incorrectes. Sélectionnez le lien **Requête et filtrage avancés** pour filtrer les enregistrements nuls dans la colonne **msdyn\_transactioncategory\_value**.

### <a name="template-mapping-in-data-integration"></a>Mise en correspondance de modèles dans l'intégration de données

L'illustration suivante présente un exemple de mise en correspondance des tâches du modèle dans le module Intégration des données. La mise en correspondance indique les informations de champ qui sont synchronisées entre Finance et Project Service Automation.

[![Mise en correspondance des modèles](./media/ProjectHourEstimatesMapping.jpg)](./media/ProjectHourEstimatesMapping.jpg)

## <a name="project-expense-estimates"></a>Estimations des dépenses de projet

### <a name="template-and-tasks"></a>Modèle et tâches

Le modèle et les tâches sous-jacentes ci-après sont utilisés pour synchroniser les estimations des dépenses du projet entre Project Service Automation et Finance :

- **Nom du modèle dans le module Intégration des données :** Estimations des dépenses du projet (PSA vers Fin and Ops)
- **Nom des tâches du projet :**

    - Relations de transaction 
    - Estimations des dépenses

### <a name="entity-set"></a>Ensemble d'entités

| Project Service Automation | Finances                                                  |
|----------------------------|----------------------------------------------------------|
| Connexions aux transactions    | Entité d'intégration des relations de transaction du projet |
| Lignes d'estimation             | Entité d'intégration des estimations des dépenses du projet         |

### <a name="entity-flow"></a>Flux d'entité

Les estimations des dépenses du projet sont gérées dans Project Service Automation, et elles sont synchronisées avec Finance en tant que prévisions des dépenses du projet.

### <a name="prerequisites"></a>Conditions préalables

Avant toute synchronisation des estimations des dépenses du projet, vous devez synchroniser les projets, les tâches de projet et les catégories de transaction de dépense de projet.

### <a name="power-query"></a>Power Query

Dans le modèle d'estimation des dépenses du projet, vous devez utiliser Power Query pour effectuer les tâches suivantes :

- Appliquer un filtre pour inclure uniquement les enregistrements de la ligne d'estimation des dépenses.
- Définir l'ID du modèle de prévision par défaut qui est utilisé lorsque l'intégration crée de nouvelles prévisions en heures.
- Transformer les types de facturation.
- Transformer les types de transactions.

#### <a name="filter-to-include-only-expense-estimate-lines"></a>Appliquer un filtre pour inclure uniquement les lignes d'estimation des dépenses

Le modèle Estimations des dépense du projet (PSA vers Fin and Ops) a un filtre par défaut qui inclut uniquement les lignes de dépense dans l'intégration. Si vous créez votre propre modèle, vous devez ajouter ce filtre. Sélectionnez la tâche **Relations de transaction**, puis cliquez sur la flèche **Mettre en correspondance** pour ouvrir la mise en correspondance. Sélectionnez le lien **Requête et filtrage avancés**. Filtrez la colonne **msdyn\_transactiontype1** afin d'inclure uniquement **msdyn\_estimateline**.

#### <a name="set-the-default-forecast-model-id"></a>Définir l'ID de modèle de prévision par défaut

Pour mettre à jour l'ID du modèle de prévision par défaut dans le modèle, sélectionnez la tâche **Estimations des dépenses**, puis cliquez sur la flèche **Mettre en correspondance** pour ouvrir la fenêtre de mise en correspondance. Sélectionnez le lien **Requête et filtrage avancés**.

- Si vous utilisez le modèle Estimations des dépenses de projet par défaut (PSA vers Fin and Ops) dans Power Query, sélectionnez la première **Condition insérée** de la section **Étapes appliquées**. Dans l'entrée **Fonction**, remplacez **O\_forecast** par le nom de l'ID du modèle de prévision qui doit être utilisé avec l'intégration. Le modèle par défaut a un ID de modèle de prévision provenant des données de démonstration.
- Si vous créez un modèle, vous devez ajouter cette colonne. Dans Power Query, sélectionnez **Ajouter une colonne conditionnelle** et entrez un nom pour la nouvelle colonne, par exemple **ModelID**. Entrez la condition pour la colonne où, si l'ID de la ligne d'estimation n'a pas la valeur null, alors \<entrez l'ID du modèle de prévision\> ; sinon, null.

#### <a name="transform-the-billing-types"></a>Transformer les types de facturation

Une colonne conditionnelle est incluse dans le modèle Estimations des dépenses du projet (PSA vers Fin and Ops) permettant de transformer les types de facturation reçus de Project Service Automation lors de l'intégration. Si vous créez votre propre modèle, vous devez ajouter cette colonne conditionnelle. Sélectionnez le lien **Requête et filtrage avancés**, puis **Ajouter une colonne conditionnelle**. Entrez un nom pour la nouvelle colonne, comme **Type de facturation**. Ensuite, entrez la condition suivante :

Si **msdyn\_billingtype** = 192350000, alors **NonChargeable**  
sinon si **msdyn\_billingtype** = 192350001, alors **Chargeable**  
sinon si **msdyn\_billingtype** = 192350002, alors **Complimentary**  
sinon **NotAvailable**

#### <a name="transform-the-transaction-types"></a>Transformer les types de transactions

Une colonne conditionnelle est incluse dans le modèle Estimations des dépenses du projet (PSA vers Fin and Ops) permettant de transformer les types de transaction reçus de Project Service Automation lors de l'intégration. Si vous créez votre propre modèle, vous devez ajouter cette colonne conditionnelle. Sélectionnez le lien **Requête et filtrage avancés**, puis **Ajouter une colonne conditionnelle**. Entrez un nom pour la nouvelle colonne, comme **Type de transaction**. Ensuite, entrez la condition suivante :

Si **msdyn\_transactiontypecode** = 192350000, alors **Cost**  
sinon si **msdyn\_transactiontypecode** = 192350005, alors **Sales**  
sinon **null**

### <a name="template-mapping-in-data-integration"></a>Mise en correspondance de modèles dans l'intégration de données

Les illustrations suivantes présentent des exemples de mise en correspondance des tâches du modèle dans le module Intégration des données. La mise en correspondance indique les informations de champ qui sont synchronisées entre Finance et Project Service Automation.

[![Mise en correspondance des modèles](./media/ExpenseEstimateTransactionRelationshipsMapping.jpg)](./media/ExpenseEstimateTransactionRelationshipsMapping.jpg)

[![Mise en correspondance des modèles](./media/ExpenseEstimatesMapping.jpg)](./media/ExpenseEstimatesMapping.jpg)
