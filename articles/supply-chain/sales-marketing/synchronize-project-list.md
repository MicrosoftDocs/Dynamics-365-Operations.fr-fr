---
title: Synchroniser la liste des projets entre Finance and Operations et Field Service
description: Cette rubrique présente les modèles et les tâches sous-jacentes utilisés pour synchroniser les projets depuis Microsoft Dynamics 365 for Finance and Operations vers Microsoft Dynamics 365 for Field Service.
author: ChristianRytt
manager: AnnBe
ms.date: 03/13/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: crytt
ms.dyn365.ops.version: 8.1.3
ms.search.validFrom: 2018-12-01
ms.openlocfilehash: ea5c188891bb97ba73d2d022e86bbff50897381b
ms.sourcegitcommit: 2b890cd7a801055ab0ca24398efc8e4e777d4d8c
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/07/2019
ms.locfileid: "1525875"
---
# <a name="synchronize-project-list-from-finance-and-operations-to-field-service"></a>Synchroniser la liste des projets entre Finance and Operations et Field Service

[!include[banner](../includes/banner.md)]

Cette rubrique présente les modèles et les tâches sous-jacentes utilisés pour synchroniser les projets depuis Microsoft Dynamics 365 for Finance and Operations vers Microsoft Dynamics 365 for Field Service.

[![Synchronisation des processus d'entreprise entre Finance and Operations et Field Service](./media/FSProjectOW.png)](./media/FSProjectOW.png)

## <a name="templates-and-tasks"></a>Modèles et tâches
Le modèle suivant et les tâches sous-jacentes sont utilisées pour exécuter la synchronisation des projets de Microsoft Dynamics 365 for Finance and Operations vers Microsoft Dynamics 365 for Field Service.

**Modèle dans l'intégration de données**
- Projets (Fin and Ops vers Field Service)

**Tâche du projet d'intégration des données**
- Projets

Les tâches de synchronisation suivantes sont requises avant que la synchronisation de la liste de projets puisse avoir lieu :
- Comptes (Sales vers Fin and Ops) 

## <a name="entity-set"></a>Ensemble d'entités
| Field Service           | Finance and Operations  |
|-------------------------|-------------------------|
|msdynce_externalprojects | Projets                |

## <a name="entity-flow"></a>Flux d'entité
Les projets sont créés dans Finance and Operations. Les projets avec un **Type de projet** défini sur **Régie** et **Stade de projet** défini sur **En cours** se synchroniseront sur l'entité **Projet externe** de Field Service, notamment le numéro de projet, le nom du projet, le stade du projet et des informations sur le compte client. La liste **Projet externe** est utilisée pour jumeler les ordres d'exécution Field Service aux projets Finance and Operations.

## <a name="field-service-crm-solution"></a>Solution Field Service CRM
L'entité **Projet externe** reçoit tous les projets depuis Finance and Operations. Le champ **Projet externe** a été ajouté à l'entité **Ordre d'exécution**. Ce champ est un champ de recherche et en référençant votre ordre d'exécution avec un projet, la commande client est ensuite connectée à un projet dans Finance and Operations. Une fois que le **statut du système** passe d'**En cours - En cours(690,970,000)** à un statut plus élevé, le champ **Projet externe** est verrouillé et vous ne pouvez plus ajouter, supprimer ou modifier la valeur.

## <a name="prerequisites-and-mapping-setup"></a>Conditions préalables et paramétrage de mise en correspondance
### <a name="finance-and-operations"></a>Finance and Operations
Activer le suivi des modifications pour les projets d'entité de données

## <a name="template-mapping-in-data-integration"></a>Mise en correspondance de modèles dans l'intégration de données


### <a name="projects-fin-and-ops-to-field-service-projects"></a>Projets (Fin and Ops vers Field Service) : Projets

[![Mise en correspondance de modèles dans l'intégration de données](./media/FSProject1.png)](./media/FSProject1.png)
