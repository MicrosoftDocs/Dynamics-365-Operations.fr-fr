---
title: "Synchroniser les transactions réelles du projet dans Project Service Automation directement avec le journal d'intégration des projets pour la validation dans Finance and Operations"
description: "Cette rubrique décrit les modèles et les tâches sous-jacentes qui sont utilisés pour synchroniser les transactions réelles du projet directement entre Microsoft Dynamics 365 for Project Service Automation et Dynamics 365 for Finance and Operations."
author: KimANelson
manager: AnnBe
ms.date: 05/21/2018
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
ms.openlocfilehash: 85ff049852e0b00623f47a12fb66e2c9bb9c4151
ms.contentlocale: fr-fr
ms.lasthandoff: 05/29/2018

---
# <a name="synchronize-project-actuals-from-project-service-automation-directly-to-the-project-integration-journal-for-posting-in-finance-and-operations"></a>Synchroniser les transactions réelles du projet dans Project Service Automation directement avec le journal d'intégration des projets pour la validation dans Finance and Operations

Cette rubrique décrit les modèles et les tâches sous-jacentes qui sont utilisés pour synchroniser les transactions réelles du projet directement entre Microsoft Dynamics 365 for Project Service Automation et Dynamics 365 for Finance and Operations.

Le modèle synchronise les transactions de Project Service Automation dans une table intermédiaire de Finance and Operations. Une fois la synchronisation effectuée, vous devez les importer de la table intermédiaire vers le journal d'intégration.

> [!NOTE]
> L'intégration des transactions réelles du projet est disponible dans la version 8.01 de Dynamics 365 for Finance and Operations.

> [!NOTE]
> Si vous entrez les montants de taxe des transactions de temps et de dépense dans Project Service Automation, vous devez installer la mise à jour 7 de Project Service Automation. Si cette mise à jour n'est pas installée, les montants réels de taxe ne sont pas liés aux transactions réelles de temps ou de dépense associées et ne sont pas synchronisés avec Finance and Operations. Contactez le support pour plus d'informations.


## <a name="data-flow-for-project-service-automation-to-finance-and-operations"></a>Flux de données pour Project Service Automation et Finance and Operations

La solution d'intégration de Project Service Automation avec Finance and Operations utilise la fonction Intégration des données pour synchroniser les données entre les instances de Project Service Automation et de Finance and Operations. Les modèles d'intégration disponibles avec la fonction Intégration des données activent le flux de données sur les transactions réelles du projet entre Project Service Automation et Finance and Operations.

L'illustration suivante indique comment les données sont synchronisées entre Project Service Automation et Finance and Operations.

[![Flux de données pour l'intégration de Project Service Automation avec Finance and Operations](./media/ProjectActualsFlow.jpg)](./media/ProjectActualsFlow.jpg)


## <a name="templates-and-tasks"></a>Modèles et tâches

Pour accéder aux modèles disponibles, dans le centre d'administrateur de Microsoft PowerApps, sélectionnez **Projets**, puis, dans le coin supérieur droit, sélectionnez **Nouveau projet** pour sélectionner des modèles publics.

Le modèle et les tâches sous-jacentes ci-après sont utilisés pour synchroniser les transactions réelles du projet entre Project Service Automation et Finance and Operations :

-  **Nom du modèle dans le module Intégration des données :** Transactions réelles du projet (PSA vers Fin and Ops)

-  **Nom des tâches du projet :** 
    - Chiffres réels 
    - TransactionConnections

## <a name="entity-set"></a>Ensemble d'entités

| Project Service Automation      | Finance and Operations                                      |
|---------------------------------|-------------------------------------------------------------|
| Chiffres réels                         | Entité d'intégration pour les chiffres réels du projet                      |
| Connexions aux transactions         | Entité d'intégration des relations de transaction du projet    |

## <a name="entity-flow"></a>Flux d'entité

Les transactions réelles du projet sont gérées dans Project Service Automation, et elles sont synchronisées avec Finance and Operations pour le journal d'intégration des projets. La comptabilité est appliquée sur la base des dimensions financières et des paramètres de validation par défaut.

## <a name="preconditions"></a>Conditions préalables

Avant la synchronisation des transactions réelles, vous devez configurer les paramètres d'intégration de Project Service Automation et synchroniser les projets, les tâches de projet et les catégories de transaction de dépense de projet.

## <a name="power-query"></a>Power Query

Vous devez utiliser Microsoft Power Query dans le modèle Transactions réelles du projet pour :
- Transformer le **type de transaction** de Project Service Automation en **type de transaction** approprié dans Finance and Operations. Cette transformation est déjà définie pour le modèle Transactions réelles du projet (PSA vers Fin and Ops).
- Transformer le **type de facturation** de Project Service Automation en **type de facturation** approprié dans Finance and Operations. Cette transformation est déjà définie pour le modèle Transactions réelles du projet (PSA vers Fin and Ops). Le type de facturation est ensuite mis en correspondance avec la **propriété de ligne** en fonction de la configuration dans l'écran des paramètres d'intégration de Dynamics 365 for Project Service Automation.
- Filtrer les **Unités d'organisation des ressources** spécifiques qui doivent être synchronisées avec ce modèle.
- Si les **transactions réelles de temps ou de dépense intersociétés** sont synchronisées avec Finance and Operations, vous devez transformer l'**unité d'organisation des contrats** en **entité juridique** appropriée dans Finance and Operations. Une colonne conditionnelle est définie pour le modèle Transactions réelles du projet (PSA vers Fin and Ops) en fonction des données de démonstration. Vous devez mettre à jour la dernière colonne de condition insérée pour les entités juridiques appropriées. Sinon, une erreur d'intégration ou des transactions réelles incorrectes sont importées dans Finance and Operations.
- Si les **transactions de temps ou de dépense intersociétés** ne sont pas synchronisées avec Finance and Operations, vous devez supprimer la dernière colonne de condition insérée de votre modèle. Sinon, une erreur d'intégration ou des transactions réelles incorrectes sont importées dans Finance and Operations.

### <a name="contract-organizational-unit"></a>Unité d'organisation des contrats
Pour mettre à jour la colonne de condition insérée dans le modèle, cliquez sur la flèche **Mettre en correspondance** pour ouvrir la fenêtre de mise en correspondance. Sélectionnez pour ouvrir l'écran Requête et filtrage avancés.
- Si vous utilisez le modèle Transactions réelles Microsoft Project par défaut (PSA vers Fin and Ops), sélectionnez la **Condition insérée** dans la section **Étapes appliquées**. Dans l'entrée **Fonction**, remplacez **USSI** par le nom de l'**Entité juridique** qui doit être utilisée avec l'intégration. Ajoutez si nécessaire des conditions supplémentaires à l'entrée **Fonction** et mettez à jour la condition **else** de **USMF** sur l'**Entité juridique** appropriée.
- Si vous créez un modèle, vous devez ajouter cette colonne pour prendre en charge le temps et les dépenses intersociétés. Sélectionnez **Ajouter une colonne conditionnelle** et attribuez un nom à la colonne, par exemple LegalEntity. Entrez la condition pour la colonne selon laquelle si msdyn_contractorganizationalunitid.msdyn_name correspond à <organizational unit>, alors <enter the Legal entity> ; sinon, null.

## <a name="template-mapping-in-data-integration"></a>Mise en correspondance de modèles dans l'intégration de données

L'illustration suivante présente un exemple de mise en correspondance des tâches du modèle dans le module Intégration des données. La mise en correspondance indique les informations de champ qui sont synchronisées entre Project Service Automation et Finance and Operations.

[![Mise en correspondance des modèles](./media/ActualsMapping.jpg)](./media/ActualsMapping.jpg)

[![Mise en correspondance des modèles](./media/TransactionConnections.jpg)](./media/TransactionConnections.jpg)

## <a name="import-from-staging-table"></a>Importer à partir de la table intermédiaire

Le processus périodique Importer à partir de la table intermédiaire doit être exécuté après la synchronisation des transactions réelles entre Project Service Automation et Finance and Operations. Ce processus importe les transactions du projet de la table intermédiaire vers le journal d'intégration de Project Service Automation, où la comptabilité est appliquée et les transactions importées peuvent être validées. Il est recommandé d'exécuter ce processus en mode de traitement par lots, et il est possible de le paramétrer pour l'exécuter en tant que traitement par lots récurrent.

## <a name="update-actuals"></a>Mettre à jour les transactions réelles

Le modèle et les tâches sous-jacentes ci-après sont utilisés pour synchroniser le numéro de document et les taxes des transactions de projet validées entre Finance and Operations et Project Service Automation :

-  **Nom du modèle dans le module Intégration des données :** Mise à jour des transactions réelles du projet (Fin Ops vers PSA)
-  **Nom des tâches du projet :** 
     - Chiffres réels 
     - TransactionConnections

## <a name="entity-set"></a>Ensemble d'entités

| Finance and Operations                                         | Project Service Automation        |
|----------------------------------------------------------------|-----------------------------------|
| Entité d'intégration pour les chiffres réels du projet                         | Chiffres réels                           |
| Entité d'intégration des relations de transaction du projet       | Connexions aux transactions           |

## <a name="entity-flow"></a>Flux d'entité

Les transactions réelles du projet sont gérées dans Project Service Automation, et elles sont synchronisées avec Finance and Operations pour le journal d'intégration des projets. Une fois validées dans Finance and Operations, les transactions réelles sont mises à jour dans Project Service Automation avec le numéro de document de Finance and Operations. Si des taxes ont été ajoutées dans Finance and Operations, de nouvelles transactions réelles de taxe sont créées dans Project Service Automation.

## <a name="power-query"></a>Power Query

Vous devez utiliser Microsoft Power Query dans le modèle Mise à jour des transactions réelles du projet pour :
- Transformer le **type de transaction** de Finance and Operations en **type de transaction** approprié dans Project Service Automation. Cette transformation est déjà définie pour le modèle Mise à jour des transactions réelles du projet (Fin Ops vers PSA).
- Transformer le **type de facturation** de Finance and Operations en **type de facturation** approprié dans Project Service Automation. Cette transformation est déjà définie pour le modèle Mise à jour des transactions réelles du projet (Fin Ops vers PSA).

## <a name="template-mapping-in-data-integration"></a>Mise en correspondance de modèles dans l'intégration de données

Les illustrations suivantes présentent des exemples de mise en correspondance des tâches du modèle dans le module Intégration des données. La mise en correspondance indique les informations de champ qui sont synchronisées entre Finance and Operations et Project Service Automation.

[![Mise en correspondance des modèles](./media/ActualsUpdateMapping.jpg)](./media/ActualsUpdateMapping.jpg)

[![Mise en correspondance des modèles](./media/TransactionConnectionsUpdate.jpg)](./media/TransactionConnectionsUpdate.jpg)




