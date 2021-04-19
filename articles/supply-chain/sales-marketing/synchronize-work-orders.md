---
title: Synchroniser les ordres de travail avec un projet entre Field Service et Supply Chain Management
description: Cette rubrique présente les modèles et la tâche sous-jacente utilisés pour synchroniser les ordres d’exécution avec un nombre de projets depuis Dynamics 365 Field Service vers la commande client dans Dynamics 365 Supply Chain Management.
author: ChristianRytt
ms.date: 03/12/2019
ms.topic: article
ms.prod: ''
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
ms.openlocfilehash: d733bf3256fa1f6c572bd0aa35c228490d409bbc
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5836492"
---
# <a name="synchronize-work-orders-with-project-from-field-service-to-supply-chain-management"></a>Synchroniser les ordres de travail avec un projet entre Field Service et Supply Chain Management

[!include[banner](../includes/banner.md)]

Cette rubrique présente les modèles et la tâche sous-jacente utilisés pour synchroniser les ordres d’exécution avec un nombre de projets depuis Dynamics 365 Field Service vers la commande client dans Dynamics 365 Supply Chain Management.

[![Synchronisation des processus d’entreprise entre Supply Chain Management et Field Service](./media/FSSOprojectOW.png)](./media/FSSOprojectOW.png)

Le modèle **Ordres de travail avec projet (Field Service vers Supply Chain Management)** utilisé est basé sur le modèle **Ordres de travail (Field Service vers Supply Chain Management)**. Pour en savoir plus, voir [Synchroniser les ordres de travail de Field Service avec les commandes client dans Supply Chain Management](https://docs.microsoft.com/dynamics365/unified-operations/supply-chain/sales-marketing/field-service-work-order).

Cette rubrique décrit uniquement les différences entre les deux modèles :
- **Ordres de travail avec Projet (Field Service vers Supply Chain Management)**
- **Ordres de travail (Field Service vers Supply Chain Management)**

La différence principale réside dans le fait que ce modèle inclut la mise en correspondance du numéro de projet attribué à l’ordre de travail dans Field Service, en vérifiant que la commande client créée dans Supply Chain Management comporte bien le numéro de projet et que la facturation peut avoir lieu dans le projet associé. Outre cela, ce modèle utilise la fonctionnalité Requête et filtrage avancés.

## <a name="templates-and-tasks"></a>Modèles et tâches

**Nom du modèle dans l’intégration des données :**

- Ordres de travail avec Projet (Field Service vers Supply Chain Management)

**Nom de la tâche dans le projet d’intégration de données :**

- WorkOrderHeader
- WorkOrderHeaderProject
- WorkOrderProduct
- WorkOrderService

## <a name="field-service-crm-solution"></a>Solution Field Service CRM
Le champ **Projet externe** a été ajouté à l’entité Ordre d’exécution. Ce champ est un champ de recherche et, en référençant votre ordre de travail avec un projet, la commande client est ensuite connectée à un projet dans Supply Chain Management. Une fois que le **Statut du système** passe d’En cours - En cours (690,970,000) à un statut plus élevé, le champ **Projet externe** est verrouillé et vous ne pouvez pas ajouter, supprimer ou modifier la valeur.

## <a name="template-mapping-in-data-integration"></a>Mise en correspondance de modèles dans l’intégration de données

Les illustrations suivantes présentent la mise en correspondance de modèles dans le module Intégration des données.

### <a name="work-orders-with-project-field-service-to-supply-chain-management-workorderheader"></a>Ordres de travail avec Projet (Field Service vers Supply Chain Management) : WorkOrderHeader

[![Mise en correspondance de modèles dans l’intégration de données](./media/FSWOP1.png)](./media/FSWOP1.png)

### <a name="work-orders-with-project-field-service-to-supply-chain-management-workorderheaderproject"></a>Ordres de travail avec Projet (Field Service vers Supply Chain Management) : WorkOrderHeaderProject

[![Mise en correspondance de modèles dans l’intégration de données](./media/FSWOP2.png)](./media/FSWOP2.png)

### <a name="work-orders-with-project-field-service-to-supply-chain-management-workorderproduct"></a>Ordres de travail avec Projet (Field Service vers Supply Chain Management) : WorkOrderProduct

[![Mise en correspondance de modèles dans l’intégration de données](./media/FSWOP3.png)](./media/FSWOP3.png)

### <a name="work-orders-with-project-field-service-to-supply-chain-management-workorderservice"></a>Ordres de travail avec Projet (Field Service vers Supply Chain Management) : WorkOrderService

[![Mise en correspondance de modèles dans l’intégration de données](./media/FSWOP4.png)](./media/FSWOP4.png)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]