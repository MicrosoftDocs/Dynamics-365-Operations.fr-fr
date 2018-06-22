---
title: "Synchroniser les estimations de projet dans Project Service Automation directement avec les prévisions de projet dans Finance and Operations"
description: "Cette rubrique décrit les modèles et les tâches sous-jacentes qui sont utilisés pour synchroniser les estimations des heures du projet et les estimations des dépenses du projet directement entre Microsoft Dynamics 365 for Project Service Automation et Microsoft Dynamics 365 for Finance and Operations."
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
ms.dyn365.ops.version: AX 7.3.0
ms.translationtype: HT
ms.sourcegitcommit: bd8feff598cf80ca675c7d2b5dda636799b19e29
ms.openlocfilehash: 90501f40da0fdc66ad087b3bd746c908cc25711b
ms.contentlocale: fr-fr
ms.lasthandoff: 05/29/2018

---
# <a name="synchronize-project-estimates-from-project-service-automation-directly-to-project-forecasts-in-finance-and-operations"></a>Synchroniser les estimations de projet dans Project Service Automation directement avec les prévisions de projet dans Finance and Operations

Cette rubrique décrit les modèles et les tâches sous-jacentes qui sont utilisés pour synchroniser les estimations des heures du projet et les estimations des dépenses du projet directement entre Microsoft Dynamics 365 for Project Service Automation et Microsoft Dynamics 365 for Finance and Operations.

> [!NOTE]
> L'intégration des tâches de projet, les catégories de transaction de dépense, les estimations des heures, les estimations des dépenses et le verrouillage des fonctionnalités sont disponibles dans la version 8.0 de Dynamics 365 for Finance and Operations.


## <a name="data-flow-for-project-service-automation-to-finance-and-operations"></a>Flux de données pour Project Service Automation et Finance and Operations

La solution d'intégration de Project Service Automation avec Finance and Operations utilise la fonction Intégration des données pour synchroniser les données entre les instances de Project Service Automation et de Finance and Operations. Les modèles d'intégration disponibles avec la fonction Intégration des données activent le flux de données sur les estimations des heures du projet et les estimations des dépenses du projet entre Project Service Automation et Finance and Operations.

L'illustration suivante indique comment les données sont synchronisées entre Project Service Automation et Finance and Operations.

[![Flux de données pour l'intégration de Project Service Automation avec Finance and Operations](./media/ProjectEstimatesFlow.png)](./media/ProjectEstimatesFlow.png)


## <a name="templates-and-tasks"></a>Modèles et tâches

Pour accéder aux modèles disponibles, dans le centre d'administrateur de Microsoft PowerApps, sélectionnez **Projets**, puis, dans le coin supérieur droit, sélectionnez **Nouveau projet** pour sélectionner des modèles publics.

Le modèle et les tâches sous-jacentes ci-après sont utilisés pour synchroniser les estimations des heures du projet entre Project Service Automation et Finance and Operations :

-  **Nom du modèle dans le module Intégration des données :** Estimations des heures du projet (PSA vers Fin and Ops)

-  **Nom des tâches du projet :** 
    - Relations de transaction 
    - Estimations des dépenses

## <a name="entity-set"></a>Ensemble d'entités

| Project Service Automation      | Finance and Operations                          |
|---------------------------------|-------------------------------------------------|
| Tâches de projet                   | Entité d'intégration des estimations des heures du projet   |

## <a name="entity-flow"></a>Flux d'entité

Les estimations des heures du projet sont gérées dans Project Service Automation, et elles sont synchronisées avec Finance and Operations en tant que prévisions des heures du projet.

## <a name="preconditions"></a>Conditions préalables

Avant toute synchronisation des estimations des heures du projet, vous devez synchroniser les projets, les tâches de projet et les catégories de transaction de dépense de projet.

## <a name="power-query"></a>Power Query

Vous devez utiliser Microsoft Power Query dans le modèle Estimations des heures du projet pour :
- Définir l'**ID du modèle de prévision** qui est utilisé lorsque l'intégration crée de nouvelles prévisions en heures.
- Filtrer les enregistrements spécifiques aux ressources dans la tâche qui font échouer l'intégration en prévisions en heures
- Filtrer les lignes de catégorie de transaction vides. Sinon, vous risquez de générer des prévisions en heures incorrectes.

### <a name="forecast-model-id"></a>ID du modèle de prévision
Pour mettre à jour l'ID du modèle de prévision par défaut dans le modèle, cliquez sur la flèche **Mettre en correspondance** pour ouvrir la fenêtre de mise en correspondance. Sélectionnez pour ouvrir l'écran Requête et filtrage avancés.
- Si vous utilisez le modèle Estimations des heures Microsoft Project (PSA vers Fin and Ops) par défaut, sélectionnez la **Condition insérée** dans la section **Étapes appliquées**. Dans l'entrée **Fonction**, remplacez **O_forecast** par le nom de l'**ID du modèle de prévision** qui doit être utilisé avec l'intégration. Le modèle par défaut a un ID de modèle de prévision provenant des données de démonstration.
- Si vous créez un modèle, vous devez ajouter cette colonne. Sélectionnez **Ajouter une colonne conditionnelle** et attribuez un nom à la colonne, par exemple ModelID. Entrez la condition pour la colonne selon laquelle si la tâche de projet n'a pas la valeur null, alors <enter the forecast model ID> ; sinon, null.

### <a name="filter-out-resource-specific-records"></a>Filtrer les enregistrements spécifiques aux ressources
Le modèle Estimations des heures du projet (PSA vers Fin and Ops) a un filtre par défaut qui supprime les enregistrements spécifiques aux ressources. Si vous créez votre propre modèle, vous devez ajouter ce filtre. Dans l'écran Requête et filtrage avancés, sélectionnez pour filtrer la colonne **msdyn_islinetask** pour inclure uniquement les enregistrements de type **False**.

### <a name="filter-out-empty-transaction-category-rows"></a>Filtrer les lignes de catégorie de transaction vides
Vous devez ajouter un filtre pour supprimer les lignes contenant des catégories de transaction vides. Cela est nécessaire, que vous utilisiez le modèle par défaut ou créiez votre propre modèle. Ce filtre supprime les lignes récapitulatives provenant de Project Service Automation qui rendent les prévisions en heures dans Finance and Operations incorrectes. Dans l'écran Requête et filtrage avancés, sélectionnez pour filtrer les enregistrements nuls dans la colonne **msdyn_transactioncategory_value**.

## <a name="template-mapping-in-data-integration"></a>Mise en correspondance de modèles dans l'intégration de données

L'illustration suivante présente un exemple de mise en correspondance des tâches du modèle dans le module Intégration des données. La mise en correspondance indique les informations de champ qui sont synchronisées entre Project Service Automation et Finance and Operations.

[![Mise en correspondance des modèles](./media/ProjectHourEstimatesMapping.jpg)](./media/ProjectHourEstimatesMapping.jpg)

Le modèle et la tâche sous-jacente ci-après sont utilisés pour synchroniser les estimations des dépenses du projet entre Project Service Automation et Finance and Operations :

-  **Nom du modèle dans le module Intégration des données :** Estimations des dépenses du projet (PSA vers Fin and Ops)
-  **Nom des tâches du projet :** 
     - Relations de transaction 
     - Estimations des dépenses

## <a name="entity-set"></a>Ensemble d'entités

| Project Service Automation      | Finance and Operations                                     |
|---------------------------------|------------------------------------------------------------|
| Connexions aux transactions         | Entité d'intégration des relations de transaction du projet.   |
| Lignes d'estimation                  | Entité d'intégration des estimations des dépenses du projet.           |

## <a name="entity-flow"></a>Flux d'entité

Les estimations des dépenses du projet sont gérées dans Project Service Automation, et elles sont synchronisées avec Finance and Operations en tant que prévisions des dépenses du projet.

## <a name="prerequisites"></a>Logiciels requis

Avant toute synchronisation des estimations des dépenses du projet, vous devez synchroniser les projets, les tâches de projet et les catégories de transaction de dépense de projet.

## <a name="power-query"></a>Power Query

Vous devez utiliser Microsoft Power Query dans le modèle Estimations des dépenses du projet pour :
- Appliquer un filtre pour inclure uniquement les enregistrements de la ligne d'estimation des dépenses
- Définir l'**ID du modèle de prévision** qui est utilisé lorsque l'intégration crée de nouvelles prévisions en heures.
- Transformer les types de facturation.
- Transformer les types de transactions.

### <a name="filter-to-include-only-expense-estimate-lines"></a>Appliquer un filtre pour inclure uniquement les lignes d'estimation des dépenses
Le modèle Estimations des dépense du projet (PSA vers Fin and Ops) a un filtre par défaut pour inclure uniquement les lignes de dépense dans l'intégration. Si vous créez votre propre modèle, vous devez ajouter ce filtre. Sélectionnez la tâche Relations de transaction et cliquez sur la flèche **Mettre en correspondance**. Sélectionnez **Requête et filtrage avancés**. Filtrez la colonne **msdyn_transactiontype1** pour inclure uniquement **msdyn_estimateline**.

### <a name="forecast-model-id"></a>ID du modèle de prévision
Pour mettre à jour l'ID du modèle de prévision par défaut dans le modèle, pour la tâche Estimations des dépenses, cliquez sur la flèche **Mettre en correspondance** pour ouvrir la fenêtre de mise en correspondance. Sélectionnez pour ouvrir l'écran Requête et filtrage avancés.
- Si vous utilisez le modèle Estimations des dépenses Microsoft Project par défaut (PSA vers Fin and Ops), sélectionnez la première **Condition insérée** dans la section **Étapes appliquées**. Dans l'entrée **Fonction**, remplacez **O_forecast** par le nom de l'**ID du modèle de prévision** qui doit être utilisé avec l'intégration. Le modèle par défaut a un ID de modèle de prévision provenant des données de démonstration.
- Si vous créez un modèle, vous devez ajouter cette colonne. Sélectionnez **Ajouter une colonne conditionnelle** et attribuez un nom à la colonne, par exemple ModelID. Entrez la condition pour la colonne selon laquelle si l'ID de la ligne d'estimation n'a pas la valeur null, alors < entrez l'ID du modèle de prévision > ; sinon, null.

### <a name="transform-the-billing-types"></a>Transformer les types de facturation
Une colonne conditionnelle est ajoutée au modèle Estimations des dépenses du projet (PSA vers Fin and Ops) pour transformer les types de facturation reçus de Project Service Automation lors de l'intégration.
- Si vous créez votre propre modèle, vous devez ajouter cette colonne conditionnelle. Dans l'écran Requête et filtrage avancés, sélectionnez **Ajouter une colonne conditionnelle**. Attribuez un nom à la nouvelle colonne, par exemple « BillingType ». La condition à entrer se présente comme suit :

    Si **msdyn_billingtype** = 192350000, alors **NonChargeable**, si **msdyn_billingtype** = 192350001, alors **Chargeable**, si **msdyn_billingtype** = 192350002, alors **Complimentary** ; sinon, **NotAvailable**

### <a name="transform-the-transaction-types"></a>Transformer les types de transactions
Une colonne conditionnelle est ajoutée au modèle Estimations des dépenses du projet (PSA vers Fin and Ops) pour transformer les types de transactions reçus de Project Service Automation lors de l'intégration.
- Si vous créez votre propre modèle, vous devez ajouter cette colonne conditionnelle. Dans l'écran Requête et filtrage avancés, sélectionnez **Ajouter une colonne conditionnelle**. Attribuez un nom à la nouvelle colonne, par exemple « TransactionType ». La condition à entrer se présente comme suit : si **msdyn_transactiontypecode** = 192350000, alors **Cost**, si **msdyn_transactiontypecode** = 192350005, alors **Sales** ; sinon **null**

## <a name="template-mapping-in-data-integration"></a>Mise en correspondance de modèles dans l'intégration de données

Les illustrations suivantes présentent des exemples de mise en correspondance des tâches du modèle dans le module Intégration des données. La mise en correspondance indique les informations de champ qui sont synchronisées entre Project Service Automation et Finance and Operations.

[![Mise en correspondance des modèles](./media/ExpenseEstimateTransactionRelationshipsMapping.jpg)](./media/ExpenseEstimateTransactionRelationshipsMapping.jpg)

[![Mise en correspondance des modèles](./media/ExpenseEstimatesMapping.jpg)](./media/ExpenseEstimatesMapping.jpg)




