---
title: Synchroniser la liste des projets entre Finance and Operations et Field Service
description: "Cette rubrique présente les modèles et les tâches sous-jacentes utilisés pour synchroniser les projets entre Microsoft Dynamics 365 for Finance and Operations et Microsoft Dynamics 365 for Field Service."
author: ChristianRytt
manager: AnnBe
ms.date: 12/20/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: 
audience: Application User, IT Pro
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 
ms.assetid: 
ms.search.region: global
ms.search.industry: 
ms.author: crytt
ms.dyn365.ops.version: 8.1.3
ms.search.validFrom: 2018-12-01
ms.translationtype: HT
ms.sourcegitcommit: 8c6cb481f1a3fe48d329c5936118d8df88a4175b
ms.openlocfilehash: adcb1c1b241ce2b073cd26cf2a8a8d64931c8b0f
ms.contentlocale: fr-fr
ms.lasthandoff: 12/20/2018

---

# <a name="synchronize-project-list-from-finance-and-operations-to-field-service"></a>Synchroniser la liste des projets entre Finance and Operations et Field Service

[!include[banner](../includes/banner.md)]

Cette rubrique présente les modèles et les tâches sous-jacentes utilisés pour synchroniser les projets entre Microsoft Dynamics 365 for Finance and Operations et Microsoft Dynamics 365 for Field Service.

[![Synchronisation des processus d'entreprise entre Finance and Operations et Field Service](./media/FSProjectOW.png)](./media/FSProjectOW.png)

## <a name="templates-and-tasks"></a>Modèles et tâches
Les modèle et les tâches sous-jacentes suivants sont utilisés pour exécuter la synchronisation des projets de Microsoft Dynamics 365 for Finance and Operations vers Microsoft Microsoft Dynamics 365 for Field Service.

**Nom du modèle dans l'intégration des données :**
- Projets (Finance and Operations vers Field Service)

**Noms des tâches dans le projet d'intégration de données :**
- Projets

Les tâches de synchronisation suivantes sont requises avant que la synchronisation de la liste de projets puisse avoir lieu :
- Comptes (Sales vers Finance and Operations) 

## <a name="entity-set"></a>Ensemble d'entités
Field Service   Finance and Operations

| Field Service           | Finance and Operations  |
|-------------------------|-------------------------|
|msdynce_externalprojects | Projets                |

## <a name="entity-flow"></a>Flux d'entité
Les projets sont créés dans Finance and Operations. Les projets avec un **Type de projet** Régie et un **Stade de projet** En cours se synchroniseront sur l'entité **Projet externe** de Field Service, notamment le numéro de projet, le nom du projet, le stade du projet et des informations sur le compte client. La liste **Projet externe** est utilisée pour jumeler les ordres d'exécution Field Service aux projets Finance and Operations.
Solution Field Service CRM Le projet externe est une nouvelle entité qui reçoit tous les projets d'Operations.
Le champ Projet externe a été ajouté à l'entité Ordre d'exécution. Ce champ est un champ de recherche et en référençant votre ordre d'exécution avec un projet, la commande client est ensuite connectée à un projet dans Operations. Une fois que le statut du système passe d'En cours - En cours(690,970,000) à un statut plus élevé, le champ Projet externe est verrouillé et vous ne pouvez pas ajouter, supprimer ou modifier la valeur.

## <a name="prerequisites-and-mapping-setup"></a>Conditions préalables et paramétrage de mise en correspondance
### <a name="in-finance-and-operations"></a>Dans Finance and Operations
Activer le suivi des modifications pour les projets d'entité de données

## <a name="template-mapping-in-data-integration"></a>Mise en correspondance de modèles dans l'intégration de données


### <a name="projects-finance-and-operations-to-field-service-projects"></a>Projets (Finance and Operations vers Field Service) : Projets

[![Mise en correspondance de modèles dans l'intégration de données](./media/FSProject1.png)](./media/FSProject1.png)

