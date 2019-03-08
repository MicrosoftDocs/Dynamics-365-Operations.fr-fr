---
title: Synchroniser les ordres de travail avec un projet entre Field Service et Finance and Operations
description: Cette rubrique présente les modèles et la tâche sous-jacente utilisés pour synchroniser les ordres d'exécution avec un nombre de projets depuis Microsoft Dynamics 365 for Field Service vers la commande client dans Microsoft Dynamics 365 for Finance and Operations.
author: ChristianRytt
manager: AnnBe
ms.date: 12/20/2018
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
ms.openlocfilehash: 6b61411a5a235e2d0aad8bb25ae4a3bfcf1248d1
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/29/2019
ms.locfileid: "329848"
---
# <a name="synchronize-work-orders-with-project-from-field-service-to-finance-and-operations"></a>Synchroniser les ordres de travail avec un projet entre Field Service et Finance and Operations

[!include[banner](../includes/banner.md)]

Cette rubrique présente les modèles et la tâche sous-jacente utilisés pour synchroniser les ordres d'exécution avec un nombre de projets depuis Microsoft Dynamics 365 for Field Service vers la commande client dans Microsoft Dynamics 365 for Finance and Operations.

[![Synchronisation des processus d'entreprise entre Finance and Operations et Field Service](./media/FSSOprojectOW.png)](./media/FSSOprojectOW.png)

Le modèle **Produits Field Service (Finance and Operations vers Field Service)** utilisé est basé sur le modèle **Produits (Finance and Operations vers Sales) – Direct** de Prospect en disponibilités. Pour plus d'informations, voir [Produits (entre Finance and Operations et Sales) - Direct](https://docs.microsoft.com/en-us/dynamics365/unified-operations/supply-chain/sales-marketing/products-template-mapping-direct).

Cette rubrique décrit les différences entre les modèles **Produits Field Service (Finance and Operations vers Field Service)** et **Produits Field Service (Finance and Operations vers Field Service)**.

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

### <a name="work-orders-with-project-field-service-to-finance-and-operations-workorderheader"></a>Ordres de travail avec projet (Field Service vers Finance and Operations) : WorkOrderHeader

[![Mise en correspondance de modèles dans l'intégration de données](./media/FSWOP1.png)](./media/FSWOP1.png)

### <a name="work-orders-with-project-field-service-to-finance-and-operations-workorderheaderproject"></a>Ordres de travail avec projet (Field Service vers Finance and Operations) : WorkOrderHeaderProject

[![Mise en correspondance de modèles dans l'intégration de données](./media/FSWOP2.png)](./media/FSWOP2.png)

### <a name="work-orders-with-project-field-service-to-finance-and-operations-workorderproduct"></a>Ordres de travail avec projet (Field Service vers Finance and Operations) : WorkOrderProduct

[![Mise en correspondance de modèles dans l'intégration de données](./media/FSWOP3.png)](./media/FSWOP3.png)

### <a name="work-orders-with-project-field-service-to-finance-and-operations-workorderservice"></a>Ordres de travail avec projet (Field Service vers Finance and Operations) : WorkOrderService

[![Mise en correspondance de modèles dans l'intégration de données](./media/FSWOP4.png)](./media/FSWOP4.png)
