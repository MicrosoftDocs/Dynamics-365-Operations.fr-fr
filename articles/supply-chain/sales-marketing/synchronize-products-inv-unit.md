---
title: Synchroniser les produits avec l'unité de stock entre Supply Chain Management et Field Service
description: Cette rubrique présente les modèles et la tâche sous-jacente utilisés pour synchroniser les produits avec l'unité de stock depuis Dynamics 365 Supply Chain Management vers Dynamics 365 Field Service.
author: ChristianRytt
manager: AnnBe
ms.date: 03/13/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: crytt
ms.dyn365.ops.version: 8.1.3
ms.search.validFrom: 2018-12-01
ms.openlocfilehash: 8b65e9640106c5d351270074e39c121e70917228
ms.sourcegitcommit: 2460d0da812c45fce67a061386db52e0ae46b0f3
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/30/2019
ms.locfileid: "2251222"
---
# <a name="synchronize-products-with-inventory-unit-from-supply-chain-management-to-field-service"></a>Synchroniser les produits avec l'unité de stock entre Supply Chain Management et Field Service

[!include[banner](../includes/banner.md)]

Cette rubrique présente les modèles et la tâche sous-jacente utilisés pour synchroniser les produits avec l'unité de stock depuis Dynamics 365 Supply Chain Management vers Dynamics 365 Field Service.

[![Synchronisation des processus d'entreprise entre Supply Chain Management et Field Service](./media/FSProductsOW.png)](./media/FSProductsOW.png)

Le modèle **Produits Field Service avec unité de stock (Supply Chain Management vers Field Service)** est basé sur le modèle **Produits Field Service (Supply Chain Management vers Field Service)**. Pour plus d'informations, voir [Produits Field Service (Supply Chain Management vers Field Service)](field-service-product.md).

Cette rubrique décrit uniquement les différences entre les deux modèles : 
- **Produits Field Service avec unité de stock (Supply Chain Management vers Sales)**
- **Produits Field Service (Supply Chain Management vers Field Service)** 

## <a name="templates-and-tasks"></a>Modèles et tâches

**Nom du modèle dans l'intégration des données :**

- Produits Field Service avec unité de stock (Supply Chain Management vers Sales)

**Nom de la tâche dans le projet d'intégration de données :**

- Produits

Le modèle **Produits Field Service avec unité de stock (Supply Chain Management vers Field Service)** inclut une mise en correspondance qui n'est pas incluse dans le modèle **Produits Field Service (Supply Chain Management vers Field Service)**. Cette mise en correspondance garantit que l'unité de stock nécessaire pour la synchronisation de niveau de stock est incluse.

```
INVENTORYUNITSYMBOL [INVENTORYUNITSYMBOL]         Fn        msdynce_inventoryunit.name [Inventory Unit(Name)] 
```

## <a name="template-mapping-in-data-integration"></a>Mise en correspondance de modèles dans l'intégration de données

Les illustrations suivantes présentent la mise en correspondance de modèles dans le module Intégration des données.

### <a name="field-service-products-with-inventory-unit-supply-chain-management-to-field-service-products"></a>Produits Field Service avec unité de stock (Supply Chain Management vers Field Service) : Produits

[![Mise en correspondance de modèles dans l'intégration de données](./media/FSProduct1.png)](./media/FSProduct1.png)
