---
title: "Synchroniser les produits avec l'unité de stock entre Finance and Operations et Field Service"
description: "Cette rubrique présente les modèles et les tâches sous-jacentes utilisés pour synchroniser les produits avec l'unité de stock entre Microsoft Dynamics 365 for Finance and Operations et Microsoft Dynamics 365 for Field Service."
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
ms.openlocfilehash: 5d3767c1a499f3d888d8fc2ce06c2837442e39f0
ms.contentlocale: fr-fr
ms.lasthandoff: 12/20/2018

---

# <a name="synchronize-products-with-inventory-unit-from-finance-and-operations-to-field-service"></a>Synchroniser les produits avec l'unité de stock entre Finance and Operations et Field Service

[!include[banner](../includes/banner.md)]

Cette rubrique présente les modèles et les tâches sous-jacentes utilisés pour synchroniser les produits avec l'unité de stock entre Microsoft Dynamics 365 for Finance and Operations et Microsoft Dynamics 365 for Field Service.

[![Synchronisation des processus d'entreprise entre Finance and Operations et Field Service](./media/FSProductsOW.png)](./media/FSProductsOW.png)

Le modèle **Produits Field Service (Finance and Operations vers Field Service)** utilisé est basé sur le modèle **Produits (Finance and Operations vers Sales) – Direct** de Prospect en disponibilités. Pour plus d'informations, voir [Produits (entre Finance and Operations et Sales) - Direct](products-template-mapping-direct.md).

Cette rubrique décrit les différences entre les modèles **Produits Field Service (Finance and Operations vers Field Service)** et **Produits Field Service (Finance and Operations vers Field Service)**.

## <a name="templates-and-tasks"></a>Modèles et tâches

**Nom du modèle dans l'intégration des données :**

- Produits Field Service avec l'unité de stock (Finance and Operations vers Sales)

**Nom de la tâche dans le projet d'intégration de données :**

- Produits

Le modèle **Produits Field Service avec unité de stock (Finance and Operations vers Field Service)** comprend une mise en correspondance qui n'est pas incluse dans le modèle **Produits Field Service (Finance and Operations vers Field Service)**. Cette mise en correspondance garantit que l'unité de stock nécessaire pour la synchronisation de niveau de stock est incluse.

```
INVENTORYUNITSYMBOL [INVENTORYUNITSYMBOL]         Fn        msdynce_inventoryunit.name [Inventory Unit(Name)] 
```

## <a name="template-mapping-in-data-integration"></a>Mise en correspondance de modèles dans l'intégration de données

Les illustrations suivantes présentent la mise en correspondance de modèles dans le module Intégration des données.

### <a name="field-service-products-with-inventory-unit-finance-and-operations-to-field-service-products"></a>Produits Field Service avec unité de stock (Finance and Operations vers Field Service) : Produits

[![Mise en correspondance de modèles dans l'intégration de données](./media/FSProduct1.png)](./media/FSProduct1.png)

