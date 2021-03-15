---
title: Synchroniser la liste de projet depuis Supply Chain Management vers Field Service
description: Cette rubrique présente les modèles et les tâches sous-jacentes utilisés pour synchroniser les projets depuis Dynamics 365 Supply Chain Management vers Dynamics 365 Field Service.
author: ChristianRytt
manager: tfehr
ms.date: 03/13/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: crytt
ms.dyn365.ops.version: 8.1.3
ms.search.validFrom: 2018-12-01
ms.openlocfilehash: 12708b35be87baf1ad13296b56507f3246f96394
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/15/2021
ms.locfileid: "5010870"
---
# <a name="synchronize-project-list-from-supply-chain-management-to-field-service"></a>Synchroniser la liste de projet depuis Supply Chain Management vers Field Service

[!include[banner](../includes/banner.md)]

Cette rubrique présente les modèles et les tâches sous-jacentes utilisés pour synchroniser les projets depuis Dynamics 365 Supply Chain Management vers Dynamics 365 Field Service.

[![Synchronisation des processus d'entreprise entre Supply Chain Management et Field Service](./media/FSProjectOW.png)](./media/FSProjectOW.png)

## <a name="templates-and-tasks"></a>Modèles et tâches
Le modèle et les tâches sous-jacentes suivants sont utilisés pour synchroniser les projets depuis Supply Chain Management vers Field Service.

**Modèle dans l'intégration de données**
- Projets (Supply Chain Management vers Field Service)

**Tâche du projet d'intégration des données**
- Projets

Les tâches de synchronisation suivantes sont requises avant que la synchronisation de la liste de projets puisse avoir lieu :
- Comptes (Sales vers Supply Chain Management) 

## <a name="entity-set"></a>Ensemble d'entités
| Field Service           | Gestion de la chaîne d'approvisionnement  |
|-------------------------|-------------------------|
|msdynce_externalprojects | Projets                |

## <a name="entity-flow"></a>Flux d'entité
Les projets sont créés dans Supply Chain Management. Les projets avec un **Type de projet** défini sur **Régie** et **Stade de projet** défini sur **En cours** se synchroniseront sur l'entité **Projet externe** de Field Service, notamment le numéro de projet, le nom du projet, le stade du projet et des informations sur le compte client. La liste **Projet externe** est utilisée pour jumeler les ordres d'exécution Field Service aux projets Supply Chain Management.

## <a name="field-service-crm-solution"></a>Solution Field Service CRM
L'entité **Projet externe** reçoit tous les projets depuis Supply Chain Management. Le champ **Projet externe** a été ajouté à l'entité **Ordre d'exécution**. Ce champ est un champ de recherche et en référençant votre ordre d'exécution avec un projet, la commande client est ensuite connectée à un projet dans Supply Chain Management. Une fois que le **statut du système** passe d'**En cours - En cours(690,970,000)** à un statut plus élevé, le champ **Projet externe** est verrouillé et vous ne pouvez plus ajouter, supprimer ou modifier la valeur.

## <a name="prerequisites-and-mapping-setup"></a>Conditions préalables et paramétrage de mise en correspondance
### <a name="supply-chain-management"></a>Gestion de la chaîne d'approvisionnement
Activer le suivi des modifications pour les projets d'entité de données

## <a name="template-mapping-in-data-integration"></a>Mise en correspondance de modèles dans l'intégration de données


### <a name="projects-supply-chain-management-to-field-service-projects"></a>Projets (Supply Chain Management vers Field Service) : Projets

[![Mise en correspondance de modèles dans l'intégration de données](./media/FSProject1.png)](./media/FSProject1.png)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]