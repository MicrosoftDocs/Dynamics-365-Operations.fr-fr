---
title: Synchroniser les ordres de travail avec un projet entre Field Service et Finance and Operations
description: Cette rubrique présente les modèles et la tâche sous-jacente utilisés pour synchroniser les ordres d'exécution avec un nombre de projets depuis Microsoft Dynamics 365 for Field Service vers la commande client dans Microsoft Dynamics 365 for Finance and Operations.
author: ChristianRytt
manager: AnnBe
ms.date: 03/12/2019
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
ms.openlocfilehash: 5ca01b085315d916a18c512af28fc7534ce76ee8
ms.sourcegitcommit: d9ed934a142b88340d268fd2bd3753475a3712b0
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/12/2019
ms.locfileid: "836440"
---
# <a name="synchronize-work-orders-with-project-from-field-service-to-finance-and-operations"></a>Synchroniser les ordres de travail avec un projet entre Field Service et Finance and Operations

[!include[banner](../includes/banner.md)]

Cette rubrique présente les modèles et la tâche sous-jacente utilisés pour synchroniser les ordres d'exécution avec un nombre de projets depuis Microsoft Dynamics 365 for Field Service vers la commande client dans Microsoft Dynamics 365 for Finance and Operations.

[![Synchronisation des processus d'entreprise entre Finance and Operations et Field Service](./media/FSSOprojectOW.png)](./media/FSSOprojectOW.png)

Le modèle **Ordres de travail avec projet (Field Service vers Finance and Operations)** utilisé est basé sur le modèle **Ordres de travail (Field Service vers Finance and Operations)**. Pour en savoir plus, voir [Synchroniser les ordres d'exécution de Field Service sur les commandes client de Finance and Operations](https://docs.microsoft.com/en-us/dynamics365/unified-operations/supply-chain/sales-marketing/field-service-work-order).

Cette rubrique décrit uniquement les différences entre les deux modèles :
- **Ordres de travail avec projet (Field Service vers Finance and Operations)**
- **Ordres de travail (Field Service vers Finance and Operations)**

La différence principale est que ce modèle inclut la mise en correspondance du numéro de projet affect à l'ordre de travail dans Field Service, en vérifiant que la commande client créée dans Finance and Operations incluent le numéro de projet et que la facturation peut se produire dans le projet associé. Outre cela, ce modèle utilise la fonctionnalité Requête et filtrage avancés.

## <a name="templates-and-tasks"></a>Modèles et tâches

**Nom du modèle dans l'intégration des données :**

- Ordres de travail avec projet (Field Service vers Finance and Operations)

**Nom de la tâche dans le projet d'intégration de données :**

- WorkOrderHeader
- WorkOrderHeaderProject
- WorkOrderProduct
- WorkOrderService

## <a name="field-service-crm-solution"></a>Solution Field Service CRM
Le champ **Projet externe** a été ajouté à l'entité Ordre d'exécution. Ce champ est un champ de recherche et en référençant votre ordre d'exécution avec un projet, la commande client est ensuite connectée à un projet dans Finance and Operations. Une fois que le **statut du système** passe d'En cours - En cours(690,970,000) à un statut plus élevé, le champ **Projet externe** est verrouillé et vous ne pouvez pas ajouter, supprimer ou modifier la valeur.

## <a name="template-mapping-in-data-integration"></a>Mise en correspondance de modèles dans l'intégration de données

Les illustrations suivantes présentent la mise en correspondance de modèles dans le module Intégration des données.

### <a name="work-orders-with-project-field-service-to-fin-and-ops-workorderheader"></a>Ordres de travail avec projet (Field Service vers Finance and Operations) : WorkOrderHeader

[![Mise en correspondance de modèles dans l'intégration de données](./media/FSWOP1.png)](./media/FSWOP1.png)

### <a name="work-orders-with-project-field-service-to-fin-and-ops-workorderheaderproject"></a>Ordres de travail avec projet (Field Service vers Finance and Operations) : WorkOrderHeaderProject

[![Mise en correspondance de modèles dans l'intégration de données](./media/FSWOP2.png)](./media/FSWOP2.png)

### <a name="work-orders-with-project-field-service-to-fin-and-ops-workorderproduct"></a>Ordres de travail avec projet (Field Service vers Finance and Operations) : WorkOrderProduct

[![Mise en correspondance de modèles dans l'intégration de données](./media/FSWOP3.png)](./media/FSWOP3.png)

### <a name="work-orders-with-project-field-service-to-fin-and-ops-workorderservice"></a>Ordres de travail avec projet (Field Service vers Finance and Operations) : WorkOrderService

[![Mise en correspondance de modèles dans l'intégration de données](./media/FSWOP4.png)](./media/FSWOP4.png)
