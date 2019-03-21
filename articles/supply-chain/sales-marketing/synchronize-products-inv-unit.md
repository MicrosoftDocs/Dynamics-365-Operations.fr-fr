---
title: Synchroniser les produits avec l'unité de stock entre Finance and Operations et Field Service
description: Cette rubrique présente les modèles et la tâche sous-jacente utilisés pour synchroniser les produits avec l'unité de stock depuis Microsoft Dynamics 365 for Finance and Operations vers Microsoft Dynamics 365 for Field Service.
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
ms.openlocfilehash: 8e421be79fde6103be6344040b6ae6cda0626c5a
ms.sourcegitcommit: d9ed934a142b88340d268fd2bd3753475a3712b0
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/12/2019
ms.locfileid: "836300"
---
# <a name="synchronize-products-with-inventory-unit-from-finance-and-operations-to-field-service"></a>Synchroniser les produits avec l'unité de stock entre Finance and Operations et Field Service

[!include[banner](../includes/banner.md)]

Cette rubrique présente les modèles et la tâche sous-jacente utilisés pour synchroniser les produits avec l'unité de stock depuis Microsoft Dynamics 365 for Finance and Operations vers Microsoft Dynamics 365 for Field Service.

[![Synchronisation des processus d'entreprise entre Finance and Operations et Field Service](./media/FSProductsOW.png)](./media/FSProductsOW.png)

Le modèle **Produits Field Service avec unité de stock (Finance and Operations vers Field Service)** est basé sur le modèle **Produits Field Service (Finance and Operations vers Field Service)**. Pour plus d'informations, voir [Produits Field Service (Finance and Operations vers Field Service)](field-service-product.md).

Cette rubrique décrit uniquement les différences entre les deux modèles : 
- **Produits Field Service avec l'unité de stock (Finance and Operations vers Sales)**
- **Produits Field Service (Finance and Operations vers Field Service)** 

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
