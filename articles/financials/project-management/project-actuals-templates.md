---
title: Synchroniser les transactions réelles du projet directement dans Project Service Automation avec le journal d'intégration des projets pour la validation dans Finance and Operations
description: Cette rubrique décrit les modèles et les tâches sous-jacentes utilisés pour synchroniser les chiffres réels de projet directement depuis Microsoft Dynamics 365 for Project Service Automation vers Microsoft Dynamics 365 for Finance and Operations.
author: KimANelson
manager: AnnBe
ms.date: 07/20/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 87983
ms.assetid: b454ad57-2fd6-46c9-a77e-646de4153067
ms.search.region: Global
ms.author: knelson
ms.search.validFrom: 2016-11-28
ms.dyn365.ops.version: AX 7.3.0
ms.openlocfilehash: 0a965e8de596decf39a15977e6df8a6aa9dd35b0
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/15/2019
ms.locfileid: "1571098"
---
# <a name="synchronize-project-actuals-directly-from-project-service-automation-to-the-project-integration-journal-for-posting-in-finance-and-operations"></a>Synchroniser les transactions réelles du projet directement dans Project Service Automation avec le journal d'intégration des projets pour la validation dans Finance and Operations

[!include[banner](../includes/banner.md)]

Cette rubrique décrit les modèles et les tâches sous-jacentes utilisés pour synchroniser les chiffres réels de projet directement depuis Microsoft Dynamics 365 for Project Service Automation vers Microsoft Dynamics 365 for Finance and Operations.

Le modèle synchronise les transactions de Project Service Automation dans une table intermédiaire de Finance and Operations. Une fois la synchronisation terminée, vous **devez** importer les données de la table intermédiaire dans le journal d'intégration.

> [!NOTE]
> - L'intégration des chiffres réels de projet est disponible dans Microsoft Dynamics 365 for Finance and Operations version 8.0.1 ou version ultérieure.
> - Si vous utilisez Microsoft Dynamics 365 for Finance and Operations, Enterprise edition 7.3.0, après avoir installé KB 4132657 et KB 4132660, vous pourrez utiliser les modèles pour intégrer les tâches de projet, les catégories de transaction de dépense, les estimations des heures, les estimations des dépenses et les transactions réelles, ainsi que pour configurer le verrouillage des fonctionnalités. Si vous devez réinitialiser les répartitions comptables, nous vous recommandons d'installer également KB 4131710.
> - Si vous utilisez Finance and Operations 7.3.0, et que vous apportez des transactions de frais de Project Service Automation, vous devez installer KB 4345320 pour inclure ces frais de la facture de projet.
> - Si vous entrez les montants de taxe des transactions de temps et de dépense dans Project Service Automation, vous devez installer la mise à jour 7 de Project Service Automation. Sinon, les montants réels de taxe ne seront pas liés aux transactions réelles de temps ou de dépense associées et ne seront pas synchronisés avec Finance and Operations. Pour plus d'informations, contactez le support.

## <a name="data-flow-for-project-service-automation-to-finance-and-operations"></a>Flux de données pour Project Service Automation et Finance and Operations

La solution d'intégration de Project Service Automation avec Finance and Operations utilise la fonction Intégration des données pour synchroniser les données entre les instances de Project Service Automation et de Finance and Operations. Les modèles d'intégration disponibles avec la fonction Intégration des données activent le flux de données sur les transactions réelles du projet entre Project Service Automation et Finance and Operations.

L'illustration suivante indique comment les données sont synchronisées entre Project Service Automation et Finance and Operations.

[![Flux de données pour l'intégration de Project Service Automation avec Finance and Operations](./media/ProjectActualsFlow.jpg)](./media/ProjectActualsFlow.jpg)

## <a name="project-actuals-from-project-service-automation"></a>Transactions réelles du projet à partir de Project Service Automation

### <a name="template-and-tasks"></a>Modèle et tâches

Pour accéder aux modèles disponibles, dans le centre d'administrateur de Microsoft PowerApps, sélectionnez **Projets**, puis, dans le coin supérieur droit, sélectionnez **Nouveau projet** pour sélectionner des modèles publics.

Le modèle et les tâches sous-jacentes ci-après sont utilisés pour synchroniser les transactions réelles du projet entre Project Service Automation et Finance and Operations :

- **Nom du modèle dans le module Intégration des données :** Transactions réelles du projet (PSA vers Fin and Ops)
- **Nom des tâches du projet :**

    - Chiffres réels
    - TransactionConnections

### <a name="entity-set"></a>Ensemble d'entités

| Project Service Automation | Finance and Operations                                   |
|----------------------------|----------------------------------------------------------|
| Chiffres réels                    | Entité d'intégration pour les chiffres réels du projet                   |
| Connexions aux transactions    | Entité d'intégration des relations de transaction du projet |

### <a name="entity-flow"></a>Flux d'entité

Les transactions réelles du projet sont gérées dans Project Service Automation, et elles sont synchronisées pour le journal d'intégration des projets avec Finance and Operations. La comptabilité est appliquée sur la base des dimensions financières et des paramètres de validation par défaut.

### <a name="prerequisites"></a>Logiciels requis

Avant la synchronisation des transactions réelles, vous devez configurer les paramètres d'intégration de Project Service Automation et synchroniser les projets, les tâches de projet et les catégories de transaction de dépense de projet.

### <a name="power-query"></a>Power Query

Dans le modèle Mise à jour des transactions réelles du projet, vous devez utiliser Microsoft Power Query pour Excel pour effectuer ces tâches :

- Transformer le type de transaction dans Project Service Automation en type de transaction approprié dans Finance and Operations. Cette transformation est déjà définie dans le modèle Transactions réelles du projet (PSA vers Fin and Ops).
- Transformer le type de facturation dans Project Service Automation en type de facturation approprié dans Finance and Operations. Cette transformation est déjà définie dans le modèle Transactions réelles du projet (PSA vers Fin and Ops). Le type de facturation est ensuite mis en correspondance avec la propriété de ligne en fonction de la configuration sur la page des **paramètres d'intégration de Project Service Automation**.
- Filtrer les Unités d'organisation des ressources spécifiques qui doivent être synchronisées avec ce modèle.
- Si les transactions réelles de temps ou de dépense intersociétés sont synchronisées avec Finance and Operations, vous devez transformer l'unité d'organisation des contrats en entité juridique appropriée dans Finance and Operations. Dans le modèle Transactions réelles du projet (PSA vers Fin and Ops), une colonne conditionnelle est définie en fonction des données de démonstration. Vous devez mettre à jour la dernière colonne conditionnelle insérée pour les entités juridiques appropriées. Sinon, une erreur d'intégration peut se produire, ou des transactions réelles incorrectes peuvent être importées dans Finance and Operations.
- Si les transactions de temps ou de dépense intersociétés ne sont pas synchronisées avec Finance and Operations, vous devez supprimer la dernière colonne conditionnelle insérée de votre modèle. Sinon, une erreur d'intégration peut se produire, ou des transactions réelles incorrectes peuvent être importées dans Finance and Operations.

#### <a name="contract-organizational-unit"></a>Unité d'organisation des contrats
Pour mettre à jour la colonne conditionnelle insérée dans le modèle, cliquez sur la flèche **Mettre en correspondance** pour ouvrir la fenêtre de mise en correspondance. Sélectionnez le lien **Requête et filtrage avancés** pour ouvrir Power Query.

- Si vous utilisez le modèle Transactions réelles Project par défaut (PSA vers Fin and Ops) dans Power Query, sélectionnez la dernière **Condition insérée** de la section **Étapes appliquées**. Dans l'entrée **Fonction**, remplacez **USSI** par le nom de l'entité juridique qui doit être utilisée avec l'intégration. Ajoutez des conditions supplémentaires à l'entrée **Fonction**, au besoin, et mettez à jour la condition **else** de **USMF** sur l'entité juridique appropriée.
- Si vous créez un modèle, vous devez ajouter la colonne pour prendre en charge le temps et les dépenses intersociétés. Sélectionnez **Ajouter une colonne conditionnelle** et entrez un nom pour la colonne, par exemple **LegalEntity**. Entrez une condition pour la colonne, où, si **msdyn\_contractorganizationalunitid.msdyn\_nom** est \<unité organisationnelle\>, alors \<entrez l'entité juridique\>; else null.

### <a name="template-mapping-in-data-integration"></a>Mise en correspondance de modèles dans l'intégration de données

Les illustrations suivantes présentent un exemple de mise en correspondance des tâches du modèle dans le module Intégration des données. La mise en correspondance indique les informations de champ qui sont synchronisées entre Project Service Automation et Finance and Operations.

[![Mise en correspondance des modèles](./media/ActualsMapping.jpg)](./media/ActualsMapping.jpg)

[![Mise en correspondance des modèles](./media/TransactionConnections.jpg)](./media/TransactionConnections.jpg)

## <a name="import-from-staging-table-after-integration-from-project-service-automation"></a>Importer à partir de la table intermédiaire après l'intégration dans Project Service Automation

Le processus périodique Importer à partir de la table intermédiaire doit être exécuté après la synchronisation des transactions réelles entre Project Service Automation et Finance and Operations. Ce processus importe les transactions du projet de la table intermédiaire vers le journal d'intégration de Project Service Automation, où la comptabilité est appliquée et les transactions importées peuvent être validées. Nous vous recommandons d'exécuter ce processus en mode de traitement par lots, et il est possible de le paramétrer pour l'exécuter en tant que traitement par lots récurrent.

## <a name="update-actuals-from-finance-and-operations"></a>Mettre à jour les chiffres réels à partir de Finance and Operations

### <a name="template-and-tasks"></a>Modèle et tâches

Le modèle et les tâches sous-jacentes ci-après sont utilisés pour synchroniser le numéro de document et les taxes des transactions de projet validées entre Finance and Operations et Project Service Automation :

- **Nom du modèle dans le module Intégration des données :** Mise à jour des transactions réelles du projet (Fin Ops vers PSA)
- **Nom des tâches du projet :**

    - Chiffres réels 
    - TransactionConnections

### <a name="entity-set"></a>Ensemble d'entités

| Finance and Operations                                   | Project Service Automation |
|----------------------------------------------------------|----------------------------|
| Entité d'intégration pour les chiffres réels du projet                   | Chiffres réels                    |
| Entité d'intégration des relations de transaction du projet | Connexions aux transactions    |

### <a name="entity-flow"></a>Flux d'entité

Les transactions réelles du projet sont gérées dans Project Service Automation, et elles sont synchronisées pour le journal d'intégration des projets avec Finance and Operations. Une fois les chiffres réels validées dans Finance and Operations, ils sont mis à jour dans Project Service Automation avec le numéro de document de Finance and Operations. Si des taxes ont été ajoutées dans Finance and Operations, de nouvelles transactions réelles de taxe sont créées dans Project Service Automation.

### <a name="power-query"></a>Power Query

Dans le modèle de mise à jour des transactions réelles du projet, vous devez utiliser Power Query pour effectuer ces tâches :

- Transformer le type de transaction dans Finance and Operations en type de transaction approprié dans Project Service Automation. Cette transformation est déjà définie dans le modèle Mise à jour des transactions réelles du projet (Fin and Ops vers PSA).
- Transformer le type de facturation dans Finance and Operations en type de facturation approprié dans Project Service Automation. Cette transformation est déjà définie dans le modèle Mise à jour des transactions réelles du projet (Fin and Ops vers PSA).

### <a name="template-mapping-in-data-integration"></a>Mise en correspondance de modèles dans l'intégration de données

Les illustrations suivantes présentent des exemples de mise en correspondance des tâches du modèle dans le module Intégration des données. La mise en correspondance indique les informations de champ qui sont synchronisées entre Finance and Operations et Project Service Automation.

[![Mise en correspondance des modèles](./media/ActualsUpdateMapping.jpg)](./media/ActualsUpdateMapping.jpg)

[![Mise en correspondance des modèles](./media/TransactionConnectionsUpdate.jpg)](./media/TransactionConnectionsUpdate.jpg)
