---
title: Synchroniser les contrats de projet et les projets directement de Project Service Automation vers Finance and Operations
description: Cette rubrique décrit le modèle et les tâches sous-jacentes utilisés pour synchroniser les contrats de projet et les projets directement depuis Microsoft Dynamics 365 Project Service Automation vers Dynamics 365 Finance.
author: KimANelson
manager: AnnBe
ms.date: 09/09/2019
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
ms.search.validFrom: 2017-12-13
ms.dyn365.ops.version: AX 7.3.0
ms.openlocfilehash: 76c62f3a503ff2a8c93143390fc91ef81fbf7d0f
ms.sourcegitcommit: 2460d0da812c45fce67a061386db52e0ae46b0f3
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/30/2019
ms.locfileid: "2250459"
---
# <a name="synchronize-project-contracts-and-projects-directly-from-project-service-automation-to-finance-and-operations"></a>Synchroniser les contrats de projet et les projets directement de Project Service Automation vers Finance and Operations

[!include[banner](../includes/banner.md)]

Cette rubrique décrit le modèle et les tâches sous-jacentes utilisés pour synchroniser les contrats de projet et les projets directement depuis Dynamics 365 Project Service Automation vers Dynamics 365 Finance.

> [!NOTE] 
> Si vous utilisez Enterprise Edition 7.3.0, vous devez installer KB 4074835.

## <a name="data-flow-for-project-service-automation-to-finance"></a>Flux de données pour Project Service Automation et Finance

> [!NOTE]
> Avant d'utiliser la solution d'intégration de Project Service Automation avec Finance and Operations, vous devez être familiarisé avec la fonction Intégration des données de Dynamics 365.

La solution d'intégration de Project Service Automation avec Finance utilise la fonction Intégration des données pour synchroniser les données entre les instances de Project Service Automation et de Finance. Le modèle d'intégration disponible avec la fonction Intégration des données active le flux de données sur les contrats de projet, les projets, les lignes de contrat de projet et les jalons de la ligne de contrat de projet entre Project Service Automation et Finance.

L'illustration suivante indique comment les données sont synchronisées entre Project Service Automation et Finance.

[![Flux de données pour l'intégration de Project Service Automation avec Finance](./media/ProjectsAndContractsFlow.JPG)](./media/ProjectsAndContractsFlow.JPG)

## <a name="templates-and-tasks"></a>Modèles et tâches

Pour accéder aux modèles disponibles, dans le centre d'administrateur de Microsoft PowerApps, sélectionnez **Projets**, puis, dans le coin supérieur droit, sélectionnez **Nouveau projet** pour sélectionner des modèles publics.

Les modèles suivants sont utilisés pour synchroniser les contrats de projet et les projets entre Project Service Automation et Finance :

### <a name="integrating-with-dynamics-365-project-service-automation-v2x"></a>Intégration avec Dynamics 365 Project Service Automation v2.x
- **Nom du modèle dans le module Intégration des données :** Projets et contrats (PSA vers Fin and Ops)
- **Nom des tâches du projet :**

    - Contrats de projet de PSA vers Fin and Ops
    - Projets de PSA vers Fin and Ops
    - Lignes de contrat de projet de PSA vers Fin and Ops
    - Jalons de la ligne de contrat de projet de PSA vers Fin and Ops
  
### <a name="integrating-with-dynamics-365-project-service-automation-v3x"></a>Intégration avec Dynamics 365 Project Service Automation v3.x
Il existe un changement de schéma dans Project Service Automation qui a un impact sur le modèle de ligne de contrat du projet et l'utilisation de la version v2 du modèle est requise pour intégrer Project Service Automation v3.x avec Dynamics 365.

- **Nom du modèle dans le module Intégration des données :** Projets et Contrats (PSA 3.x vers Fin and Ops) - v2
- **Nom des tâches du projet :**

    - Contrats de projet de PSA vers Fin and Ops
    - Projets de PSA vers Fin and Ops
    - Lignes de contrat de projet de PSA vers Fin and Ops
    - Jalons de la ligne de contrat de projet de PSA vers Fin and Ops

Avant toute synchronisation des contrats de projet et des projets, vous devez synchroniser les comptes.

## <a name="entity-set"></a>Ensemble d'entités

| Project Service Automation       | Finances                                                |
|----------------------------------|--------------------------------------------------------|
| Commandes                           | Entité d'intégration du contrat de projet                |
| Projets                         | Entité d'intégration du projet                         |
| Lignes de commande                      | Entité d'intégration de la ligne de contrat de projet           |
| Jalons de la ligne de contrat de projet | Entité d'intégration des jalons de la ligne de contrat de projet |

## <a name="entity-flow"></a>Flux d'entité

Les contrats de projet sont gérés dans Project Service Automation, et ils sont synchronisés avec Finance en tant que contrats de projet. Dans le cadre du modèle d'intégration, vous pouvez définir la source d'intégration dans Finance pour le contrat de projet.

Les projets à prix fixe et de projet en régie sont gérés dans Project Service Automation, et ils sont synchronisés avec Finance en tant que projets. Dans le cadre du modèle d'intégration, vous pouvez définir la source d'intégration dans Finance pour le projet.

Les lignes de contrat de projet sont gérées dans Project Service Automation, et elles sont synchronisées avec Finance en tant que règles de facturation de contrat de projet. Si la méthode de facturation est différente du type de projet par défaut, la synchronisation met à jour le type de projet pour le projet de ligne de contrat et le groupe de projets.

Les jalons de la ligne de contrat de projet sont gérés dans Project Service Automation, et ils sont synchronisés avec Finance en tant que jalons de la règle de facturation de contrat de projet.

## <a name="project-service-automation-to-finance-integration-solution"></a>Solution d'intégration de Project Service Automation avec Finance

Le champ **ID contrat de projet** est disponible sur la page **Contrats de projet**. Une clé naturelle et unique a été créée pour ce champ pour prendre en charge l'intégration.

Lorsqu'un contrat de projet est créé, si une valeur **ID contrat de projet** n'existe pas déjà, elle est automatiquement générée à l'aide d'une souche de numéros. La valeur est composée de **ORD**, suivi d'une souche de numéros d'incrémentation et d'un suffixe de six caractères. Voici un exemple : **ORD-01022-Z4M9Q0**.

Le champ **Numéro de projet** est disponible sur la page **Projets**. Une clé naturelle et unique a été créée pour ce champ pour prendre en charge l'intégration.

Lorsqu'un projet est créé, si une valeur **Numéro de projet** n'existe pas déjà, elle est automatiquement générée à l'aide d'une souche de numéros. La valeur est composée de **PRJ**, suivi d'une souche de numéros d'incrémentation et d'un suffixe de six caractères. Voici un exemple : **PRJ-01049-CCNID0**.

Lorsque la solution d'intégration de Project Service Automation avec Finance est appliquée, un script de mise à niveau définit le champ **ID contrat de projet** pour les contrats de projet existants et le champ **Numéro de projet** pour les projets existants dans Project Service Automation.

## <a name="prerequisites-and-mapping-setup"></a>Conditions préalables et paramétrage de mise en correspondance

- Avant toute synchronisation des contrats de projet et des projets, vous devez synchroniser les comptes.
- Dans votre ensemble de connexions, ajoutez une mise en correspondance des champs de clé d'intégration pour **msdyn\_organizationalunits** à **msdyn\_name \[Name\]**. Vous pouvez d'abord devoir ajouter un projet à l'ensemble de connexions. Pour plus d'informations, voir la section [Intégration des données dans Common Data Service pour les applications](https://docs.microsoft.com/powerapps/administrator/data-integrator).
- Dans votre ensemble de connexions, ajoutez une mise en correspondance des champs de clé d'intégration pour **msdyn\_projects** à **msdynce\_projectnumber \[Project Number\]**. Vous pouvez d'abord devoir ajouter un projet à l'ensemble de connexions. Pour plus d'informations, voir la section [Intégration des données dans Common Data Service pour les applications](https://docs.microsoft.com/powerapps/administrator/data-integrator).
- **SourceDataID** pour les contrats de projet et les projets peut être mis à jour sur une autre valeur ou supprimé de la mise en correspondance. La valeur de modèle par défaut est **Project Service Automation**.
- La mise en correspondance **PaymentTerms** doit être mise à jour pour refléter les conditions de paiement valides dans Finance. Vous pouvez également supprimer la mise en correspondance de la tâche de projet. La mise en correspondance des valeurs par défaut a des valeurs par défaut pour les données de démonstration. Le tableau suivant indique les valeurs dans Project Service Automation.

    | Valeur | Description   |
    |-------|---------------|
    | 1     | Net 30        |
    | 2     | 2 % 10, Net 30 |
    | 3     | Net 45        |
    | 4     | Net 60        |

## <a name="power-query"></a>Power Query

Vous devez utiliser Microsoft Power Query pour Excel pour filtrer les données si les conditions suivantes sont réunies :

- Des commandes client sont disponibles dans Dynamics 365 Sales.
- Plusieurs unités d'organisation sont disponibles dans Project Service Automation, et ces unités d'organisation sont mises en correspondance avec plusieurs entités juridiques dans Finance.

Si vous devez utiliser Power Query, suivez les instructions ci-après :

- Le modèle Projets et contrats (PSA vers Fin and Ops) a un filtre par défaut qui n'inclut que les commandes client du type **Élément de travail (msdyn\_ordertype = 192350001)**. Ce filtre garantit que les contrats de projet ne sont pas créés pour les commandes client dans Finance. Si vous créez votre propre modèle, vous devez ajouter ce filtre.
- Vous devez créer un filtre Power Query qui n'inclut que les organisations contractuelles qui doivent être synchronisées avec l'entité juridique de l'ensemble de connexions d'intégration. Par exemple, les contrats de projet avec l'unité d'organisation des contrats de Contoso US doivent être synchronisés avec l'entité juridique USSI, mais les contrats de projet avec l'unité d'organisation des contrats de Contoso Global doivent être synchronisés dans l'entité juridique USMF. Si vous n'ajoutez pas ce filtre à votre mise en correspondance des tâches, tous les contrats de projet sont synchronisés avec l'entité juridique définie pour l'ensemble de connexions, indépendamment de l'unité d'organisation des contrats.

## <a name="template-mapping-in-data-integration"></a>Mise en correspondance de modèles dans l'intégration de données

> [!NOTE] 
> Les champs **CustomerReference**, **AddressCity**, **AddressCountryRegionID**, **AddressDescription**, **AddressLine1**, **AddressLine2**, **AddressState** et **AddressZipCode** ne sont pas inclus dans la mise en correspondance par défaut pour les contrats de projet. Vous pouvez ajouter les mises en correspondance si ces données doivent être synchronisées pour les contrats de projet.
>
> Les champs **Description**, **ParentID**, **ProjectGroup**, **ProjectManagerPersonnelNumber** et **ProjectType** ne sont pas inclus dans la mise en correspondance par défaut pour les projets. Vous pouvez ajouter les mises en correspondance si ces données doivent être synchronisées pour les projets.

Les illustrations suivantes présentent des exemples de mise en correspondance des tâches du modèle dans le module Intégration des données. La mise en correspondance indique les informations de champ qui sont synchronisées entre Finance et Project Service Automation.

[![Mise en correspondance des modèles](./media/ProjectContractTemplateMapping.JPG)](./media/ProjectContractTemplateMapping.JPG)

[![Mise en correspondance des modèles](./media/ProjectTemplateMapping.JPG)](./media/ProjectTemplateMapping.JPG)

[![Mise en correspondance des modèles](./media/ProjectContractLinesMapping.JPG)](./media/ProjectContractLinesMapping.JPG)

[![Mise en correspondance des modèles](./media/ProjectContractLineMilestonesMapping.JPG)](./media/ProjectContractLineMilestonesMapping.JPG)

#### <a name="project-contract-line-milestone-mapping-in-the-projects-and-contracts-psa-3x-to-dynamics---v2-template"></a>Mise en correspondance de ligne de contrat de projet dans Projets et Contrats (PSA 3.x vers Dynamics) - modèle v2 :

[![Mise en correspondance des modèles](./media/ProjectContractLineMilestoneMapping_v2.jpg)](./media/ProjectContractLineMilestoneMapping_v2.jpg)